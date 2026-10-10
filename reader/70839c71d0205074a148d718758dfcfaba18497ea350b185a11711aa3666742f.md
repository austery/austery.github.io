---
author: AI Engineer
date: '2026-06-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=SS-A8sE7hkw
speaker: AI Engineer
tags:
  - open-source-models
  - data-sovereignty
  - agentic-capabilities
  - edge-computing
  - model-fine-tuning
title: 主权逃逸速度：基于开源模型的所有权 —— Google DeepMind 深入解析 Gemma 4
summary: 在这场演讲中，Google DeepMind 团队介绍了全新开源模型 Gemma 4 家族，并深入探讨了企业与主权机构对“模型所有权”的刚需。演讲阐述了 Gemma 4（包括移动端的 E2B/E4B 和高效的 26B/31B 模型）如何在保障数据隐私、支持离线处理以及降低 Agentic 任务 token 成本方面赋能开发者，强调了本地部署对于系统主权与算力成本控制的战略级意义。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Gus Martins
  - Ian Ballantyne
companies_orgs:
  - Google DeepMind
  - Google
  - OpenRouter
products_models:
  - Gemma 4
  - Gemini
  - Medgema
  - LM Studio
  - Olama
media_books: []
status: evergreen
---
### 开场与介绍

**Gus Martins**: 大家好。大家能听到我说话吗？好的，能听到。嗨，不好意思，我们迟到了一分钟。我会尽量早点讲完，这样我的朋友就能给大家展示一些非常酷的演示了。我是 Gus，这位是 Ian。我们来自 **Google DeepMind**，我主要负责 **Gemma** 产品。大家有谁了解 Gemma 模型吗？好的，太棒了，非常感谢。

<details>
<summary>Original English</summary>

**Gus Martins**: Hi everyone. Uh, can you hear me? Yes, you can hear me. Hi. Sorry. Sorry we're 1 minute late. I'll try to do my best to finish earlier so my friend can do a pretty cool demos for you. I'm Gus. This is Ian. We are from the uh Google deep mind and I'm specifically I work on the Gemma product. Do any of you know what Gemma models are? Okay, perfect. Perfect. Thank you very much.

</details>

### Gemma 4 模型发布

**Gus Martins**: 今天我们将探讨一下**所有权（Ownership）**和**开源模型（Open Models）**。大家知道我们是谁了，上周四我们发布了全新的模型家族 **Gemma 4**，接下来我将简单介绍一下它们。明天 Omar 的演讲中会有更多信息，明天 CassD 也会有一场演讲并深入更多细节。今天我们只讲故事的一部分，但整体的故事其实更加宏大，我们会尽力为大家呈现。

<details>
<summary>Original English</summary>

**Gus Martins**: Uh so today we're going to talk a little bit about ownership and open models. Uh and well you know who we are. But the idea is uh last Thursday we released our new uh family of models Gemma 4. And I'm going to talk a little bit about them. Uh there's going to be more information tomorrow in the keynote by Omar and there's another talk by CassD also tomorrow that she go into even more details. We're going to tell a little bit of the story but the story is a little bit bigger. We'll try our best here.

</details>

### 为什么需要开源模型

**Gus Martins**: 为什么这件事很重要呢？如果你问我，我当然是为 **Google** 工作的。如果你问我最推荐尝试的、最容易使用的模型是什么，我会毫不犹豫地回答：**Gemini**。Gemini 是我们所拥有的最好的模型，它是一个极其强大的多模态模型，能做各种各样的事情。然而，除了仅仅拥有最强大的模型之外，故事还有另一面。在某些场景下，你需要**拥有这个模型**。你希望能够在**自己的硬件**上运行它，你希望能够去定制它，你希望能够向它发送**绝对不能离开你基础设施的专有数据**。因此，在许多场景中，即使是最好的闭源专有模型也无法直接帮助你。这时候你就可能需要一个开源模型，这也是 Gemma 诞生的原因。所以当你思考为什么 Google 会有两个模型家族时？答案是因为它们是**互补**的。Gemini 是最智能的，能做很多酷炫的事情，但它托管在 Google 的服务器上，你需要通过 API 访问。如果你需要更多的控制权和访问权限，你就需要一个开源模型。这就是我们推出 Gemma 的原因，我们也为其极高的质量感到非常自豪。稍后我们会讨论一些细节，但核心理念是你可以用它做很多很酷的事情。

<details>
<summary>Original English</summary>

**Gus Martins**: Uh so why does it matter? Uh if you ask me I work for Google of course. If you ask me what's the best model for you to try the easiest one I will answer for you. Gemini. Gemini is the best model we have. pretty strong multi model can do all kinds of things. But then there is uh there's more to this story than just having the strongest model possible. In some situations, you want to own the model. You want to be able to run on your own hardware. You want to customize it. You want to be able to send your proprietary data that cannot leave your infrastructure. So there are many situations where even the best proprietary model will not be able to help you directly. That's when you might need an open model. That's where Gemma comes in. So when you think why does Google have two family of models? Because they complement each other. So Gemini is the most intelligent one. Can do a lot of cool stuff but it's hosted in Google servers. You need the API to access. If you need more control and access, you need an open model. That's why we have Gemma. That's why uh and and we are very proud that the quality is very very strong. We're going to go some details later but the idea is you would be able to do a lot of cool stuff with it.

</details>

### 移动端与边缘设备：E2B 与 E4B

**Gus Martins**: 在我们的发布中，我们推出了四个尺寸的版本。其中有两个是主要针对移动设备或物联网 (IoT) 及更小设备的，分别是 **E2B** 和 **E4B**。这些名字可能有点怪，我们是唯一使用这种命名方式的。这里的“E”代表**有效（Effective）**。它的核心理念是，模型在内存占用上和普通的 2B 模型一样大，但它实际的参数量比这个要大得多。E2B 实际上大约有 50 亿 (5B) 参数。那你可能会问，另外那 30 亿参数在内存里去哪了？有趣的是，它们并不真的是 Transformer 的参数，它们更像是用来映射 token 的。所以你可以把它们留在其他类型的内存中。因此，你**真正需要占用 GPU 显存的只有那 20 亿或 40 亿参数**。我们为什么要这么设计？为了让你能够在手机上——比如 Pixel 手机或你手头的任何手机上运行这些模型，而且它们依然非常强大。E2B 和 E4B 都支持文本、视觉和音频输入，但它们只输出文本。它们能进行思考、能够编写代码、调用函数，能做所有这些很酷的事情。所有这些现在就可以在你的手机上运行，你现在就可以去下载。

<details>
<summary>Original English</summary>

**Gus Martins**: Among the launches we did we released four sizes. Uh two are target to mobile let's say like that or or IoT or smaller devices. It's a E2B and a E4B. Uh these names is a little bit weird. We are the only ones that use this name. Uh and the E stands for effective. And the idea here is uh the model uh uses as much as 2B uh what a 2B model would use as memory but it's larger than that. The 2B is around 5B uh uh parameters. But then you say oh but where is these other 3B in memory the the fun fact is that they are not really parameters from the transformers. They are uh like mapping uh tokens. So you can leave them in other memory. So what you really need on your GPU memory is the 2 billion or the 4 billion. Why do we do that? So that you can run these models on a phone on a Pixel phone or B any phone you have there. You can run these models and they're very strong. The E2B E4B both of them have a text uh vision and audio input and they do only text output. They can do thinking, they can do coding, function calling, all this kind of cool things. This all running on your phone right now. You could download it right now. Right.

</details>

### 高性能大模型：26B 与 31B

**Gus Martins**: 我们还有两个更大尺寸的模型，分别是 **26B** 和 **31B**。26B 是一个**混合专家模型（Mixture of Experts）**，这意味着它就像是许多个其他模型在一起协同工作，而其中每一个专家模型就像是一个 4B 的模型。这有什么意义呢？意义在于，它拥有 260 亿个参数，但**在运行时只需要相当于一个 4B 模型的空间**。这使得它能够适配更多种类的硬件，让更多人可以使用，而且它依然非常强大。但我们最强大的模型是 **31B 稠密模型（Dense）**，这是一个实打实的 310 亿参数模型。它真的非常非常强大。如果我们看一下它在 **LMSYS Chatbot Arena (LM Marina)** 上的 ELO 评分，你可以看到我们的两个模型——我现在猜它们大概在开源模型中排名第四和第七，处于领先地位。如果你把它们与排名前 20 或 30 的模型进行比较，所有的竞争对手模型至少比我们的模型大两到三倍，在某些情况下甚至是大 20 倍。所以我们讨论的是一种**相对于体积而言极度不成比例的超高智能**。因此，31B 模型是我非常经常使用的一个模型。它基本上什么都能做，从写代码到所有多语言任务都不在话下。我强烈建议大家去试试。它们非常强大，这两个模型都非常适合作为云端部署的模型来使用。你可以在台式机上运行它，但如果你把它部署在服务器上作为端点来完成你的工作，效果也是相当出色的。

<details>
<summary>Original English</summary>

**Gus Martins**: We also have other two models which are the larger ones. We have a 26B and a 31B. The 26 is a mixture of experts which means that uh it's as if we had many other models working together where where each of the where each one of those are like a 4B model. Why does it matter? Because it it has 26 billion parameters but it needs a space of a four billion parame to do the work. And this makes uh makes it accessible to way more hardware to way more people and it's still pretty strong. But our strongest model is the 31B dense which is 31 billion parameters model. And this is really really strong. If we look into our uh ELO score on LM Marina, you can see that both our models are they are I guess now they're fourth and seventh as the leads on open source models open models. And if you compare them to maybe the top 20 30 all of them are at least twice three times larger than our models in some cases 20 times larger. So we are talking about a disproportionate amount of intelligence per size. So our 31B model is the one I use very regularly. It can do basically anything from coging aic everything multilingual all of that. So I strongly recommend you try those. They are so strong that they are uh all both of them are really good to use on your on as a cloud deployed model. They can run on your desktop but if you use on your server as your endpoint to do uh your work they are pretty good.

</details>

### 参数效率与超高性价比

**Gus Martins**: 你可能会问，这是世界上最智能的模型吗？不，它不是。我非常偏心，我也很爱它们，但我清楚它们的能力边界。但问题在于，为了总结邮件、做一些基础的琐碎任务、辅助写代码，或者执行一些搜索和与文档交互的**智能体能力（Agentic Capabilities）**，你真的需要地球上最智能的模型吗？大概不需要。这也是为什么这些模型如此具有竞争力，因为它们**更便宜**。它们非常强大，而且运行成本更低。它们需要的硬件资源少得多。跑一个 31B 模型只需要单张 GPU。而竞争对手的模型需要 200GB 的显存，这可能意味着需要四到五张 GPU。所以你可以看到，这里的价格差异是非常非常巨大的。你可以很容易地在 **AI.dev** 上尝试这些模型，那里你可以体验 Gemini 的各种版本以及其他所有的模型，Gemma 的 26B 和 31B 也都在那里，你现在就可以免费试用。它们能做一些很酷的事情，我原本打算展示一个结合了视觉、思考加上代码执行同时进行的演示，但现在展示不了。我之后会尽量发些相关的内容，但核心思想是，你可以非常轻松地在平台上把玩这些模型。好了，现在先别去，等我们演讲结束了你们再去玩。正如我刚才所说，这些模型带来的“单位参数智能”是相当出色的，非常非常强。如果我们使用 Chatbot Arena (Lemarina) 的 ELO 评分，因为那是一个基于人类偏好的基准测试，我们也可以看看学术基准测试，表现同样非常强。但模型如何响应你的具体查询，这是非常重要的对吧？这关乎到你的客户将如何看待它，你将如何看待并与之互动。这就是为什么这一切如此重要。

<details>
<summary>Original English</summary>

**Gus Martins**: And you ask is this the most intelligent model? No it isn't. I'm going I'm I'm very biased and I love them but I know the capabilities. But the question is, do you need the most intelligent model of the planet to summarize your mail, to do some more minial tasks, to help you code, to do some agentic capabilities that are searching and interacting with docs? Probably not. That's why these models are so strong because they're cheaper. They're very strong, but they're cheaper to run. They require way less hardware. a 31B running one GPU. The competitors need 200 GB of memory which would be maybe four or five GPUs. So you can see that the price here is really really different. One easy place for you to try these models is on AI.dev where you can try Gemini models VO all the other mods but G gem are there both 26 and 31B you can try right now. They are free. You can play with it. uh and they can do I was I was going to show a demo but I can't now but they can do some cool stuff which is vision plus thinking plus code execution all at the same time right uh I try to post something about this later but the ideas you can play with the models pretty easily and right there right not now finish let's finish the the talk and then you play with it uh and as I was saying the the intelligence per parameter that these models bring is pretty good it's very very strong and if We use the ALO score for Lemarina because it's a benchmark that's a person's preference, right? We can look into academic benchmarks. They are very very strong. But the how the model responds to your queries, that's very important, right? That's how your customers will see how you will see and and interact with it. So this is why this is so important.

</details>

### 数据主权与商业许可痛点

**Gus Martins**: 为什么这些都很重要呢？我们如此关注它的原因之一是，你希望用户能够拥有**所有权（Ownership）**，更进一步说，我们正在赋予大家**主权（Sovereignty）**。主权的含义是，你真正拥有这个模型，你可以根据你的用例进行适配，而且你不用担心，比如，服务突然中断，或者某天有人说“不行，你不能再使用这个模型了”。这一切都完全由你掌控。我们去年做出的改变之一一直延续到 Gemma 以及其他模型上。我们曾有我们专属的许可证，也就是 Gemma 许可证，它挺不错的，对商业用途也很友好，但存在一个问题。如果你使用定制的许可证，我不知道在座有没有律师。如果我告诉你“哦，我们有一个定制许可证”，你们公司的律师肯定会用那种“我讨厌你，Gus”的眼神看着我，然后他们会花上 18 个月的时间走采购审批流程，去理解这个许可证并试图修改条款。而这根本行不通。所以，主权机构想要采用这类技术是非常困难的。这就是为什么我们在 Gemma 4 以及未来的版本中全面转向了 **Apache 2.0 许可证**。谢谢大家。这让我们的生活、也让你们的生活轻松了许多，你更容易去说服你们的法务部门，比如告诉他们：“看，我们拥有这个模型，我们可以自由使用。”所以这非常重要，它让许多主权机构能够使用我们的模型。我们有一些例子，比如，**乌克兰**就将 Gemma 用于他们部分的服务中，我们有一个针对保加利亚语进行微调的 Gemma 模型版本，它是作为该国家的大语言模型（LLM）来使用的，那是基于 Gemma 2 的，我们正在努力确保他们升级使用 Gemma 4。我们现在也有一个巴西版本，是基于 Gemma 3 针对葡萄牙语微调的。

<details>
<summary>Original English</summary>

**Gus Martins**: And why does all this matter? One of the reasons that we care so much is because uh you want to you want to the user to have ownership and more than that we are enabling sovereignty and sovereignty means in terms of you own the model and you can adapt your use cases and you you are not susceptible to I don't know loss of service or for some kind of uh someone saying no you cannot use this model anymore it's all available to you and one of the changes we made last year until Gemma and others. We had our specific license, a Gemma license, which is pretty good, commercial friendly and all, but there's a problem. If you have a custom license, I don't know if you have any lawyers here. Uh, if I tell you, oh, we have this custom license, your lawyers will look at me with that face that I hate you, Gus, and then they will spend like 18 months doing procurement process to understand the license and trying to change. And that never works. So, it's pretty hard for sovereign institutions to adopt this kind of thing. That's why we move to a pass 2.0 you for for Gemma 4 and going forward and that makes thank you and that makes our life m your life much easier to to convince your legal department let's say like that that look we own this model we can use so this is pretty important and it enables many many uh sovereign institution to use our models we have some examples for example here for example uh Ukraine use Gemma to parts of their uh services we have a one version of the Gemma model that was fine-tuned for Bulgarian it was their uh LLM for the country that was based on Gemma 2. We are working to make sure they use Gemma 4. Now we also have a Brazilian version that is based on Gemma 3 was fine-tuned for Portuguese.

</details>

### 微调语言的收益递减

**Gus Martins**: 现如今这些模型面临的一个挑战是，如果你想针对某种特定语言微调 Gemma，这变得非常困难。而这个问题之所以困难，并不是因为工具链或类似的东西，而是因为**模型本身在这些语言上的表现已经非常强了**。因此，你试图获得的任何性能提升可能都无法实现。你可能花了大量的时间，结果只提升了 1%。所以，我不知道这是否是利用你时间的最佳方式。这同时也是件好事也是件坏事，好的一面是你可以自动在多种语言中使用它，你现在就可以去试试。如果你去查看不同语言的 Chatbot Arena 榜单，在许多语言中它都能排进前两三名，要知道这仅仅是一个 31B 的模型，它的体积非常非常小对吧？所以这真的非常出色。话虽如此，我将让我的同事继续为大家展示一些演示。

<details>
<summary>Original English</summary>

**Gus Martins**: And the challenge of these models today is that they if you want to fine-tune Gemma to a specific language, it's becoming very hard to do that. And the problem is hard because not the the tooling or anything because the model is pretty strong on those languages already. So any gains you try to have you might not get there. So you might spend a lot of time to get like 1%. And then maybe I don't know if it's the best use of your uh time. So this is good and bad at the same time because but it's good that you can automatically use in many language you can try right now and if you go into uh the marina for languages in many languages are top two three and look it's a 31B model. It's very very small right? So this is pretty good. That being said, uh I will let my colleague continue and show some demos.

</details>

### Agentic 能力与 Token 成本的博弈

**Ian Ballantyne**: 谢谢你，Gus。我认为关于这些模型，有一件非常重要的事情是，当你考虑使用开源模型时，你其实也是在对比使用专有闭源模型。我们现在看到了一个趋势，也就是向更多**智能体化（Agentic）能力**和我们试图完成的特定任务类型转变。伴随这种转变而来的是 token 的成本以及生成 token 的开销。所以，拥有模型所有权的一个巨大好处就是你拥有了控制权，或者在那些你已经投入了硬件沉没成本的场景下，你能够在现有的基础上进行迭代开发。右侧的这张图表来自 **OpenRouter** 发布的《人工智能现状报告》，它展示了目前人们在 OpenRouter 上执行的不同类型的任务，图表对你们来说可能有点小，但大家可以去看看那个链接。你会看到中间这里的这一项是编程任务，它恰恰处于中间位置，而这也是在**输入和输出总 token 生成量方面消耗最高的任务之一**。所以，当我们越来越多地让智能体去工作，让它们为我们执行这些高 token 生成成本的任务时，这就是你开始从完全控制模型所有权中获得更大收益的时候。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: Thank you, guests. So, uh one thing that's I think is really important about these models is that when you think about using open models, you think about like using proprietary models. We're move we're seeing a shift now to more kind of agentic capabilities and the kind of tasks that we're trying to do. And with that comes a cost in tokens and token generation. So one benefit of uh taking ownership of the models is your ability to control or in cases where you have sunken hardware cost uh to be able to iterate on top of that. Uh this graph on the right hand side is from the state of AI report that open router did and it shows the uh it's a bit small for you on this diagram but have a look at that link. Uh shows the different types of tasks that people are doing through open router at the moment and you'll see that the the one that's about here. This one here is programming is right in the middle and this is kind among some of the highest tasks in terms of token generation both input and output combined. So the more we have agents work and do these kind of tasks for us that have very high token generation costs that's when you start to get more benefit from being able to take control of that in itself.

</details>

### 明确任务场景与硬件匹配

**Ian Ballantyne**: 举个例子，如果你有一台笔记本电脑，能够处理你需要执行的某项特定任务，比如处理文档、分析数据、做一些研究，或者像 Gus 提到的进行一些适合在上面运行的编程任务，那么你就可以利用你自己的 GPU 来完成这些工作。现在，跟 Gus 刚才说的相似，我们并不是说不需要最前沿的巨型模型了，前沿模型依然是用来执行最复杂任务的最佳选择。我不会让这个相对较小的模型去执行诸如完整系统架构设计或对你的应用程序进行全面重构的任务对吧，它不是用来做那个的。但它非常擅长做的是：**遵循非常具体的指令**去执行任务，例如重构、分析、或者以小型的、模块化的方式生成代码。你可以以这种方式将一大块工作下放给这类开源模型去完成，无论是在单张 GPU 上还是在你自己的个人硬件上。我们思考这个问题的方式是设立一系列的**阈值（Thresholds）**。即：什么时候我们达到了这样一个平衡点——这些模型既有能力完成任务，同时又能适配现有的硬件，并且能够根据任务需求以合适的延迟来完成？如果这是一个用户需要在一两秒内得到响应的交互任务，或者如果这是一个诸如批处理之类的任务，你对于响应时间的要求可能就有稍微不同的阈值标准。此外，还要考虑实际执行这些任务的成本是多少？如果你的基础设施已经有沉没成本，比如你已经拥有了硬件，或者准备进行一笔初期投入并在其上运营，又或者你是租赁 GPU 时间等等。这些都需要根据你试图实现的具体任务来具体分析。但开源模型赋予你的能力是，你可以非常仔细地去思考：“在这些任务中，哪些是我可以完全卸载到本地运行的？哪些是我可以完全控制的？”，而不是仅仅依赖于在云端使用最好的模型来完成所有的工作。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: So if for instance you have a laptop that is capable of doing a particular task that you need to be doing like processing a document or analyzing some data or doing some research or in the cases Gus talked about doing some coding that's suitable for that then you have a GPU that you can take advantage to do some of that stuff. Now similarity similar to what Gus said about you know we don't necessarily we still have frontier models for doing the best possible things. I wouldn't get this model to do like a you know a full systems architecture and redesign of your application right it's not kind of for that but what it is very good at doing is following very specific instructions about doing things like refactoring analyzing uh generating code in uh in small modular bits and you can offload a chunk of work in that style to these kind of models to be able to do that whether it's on a single GPU or on your own personal hardware um and the way that we kind of think about This is like a a set of thresholds like when do we get to the point where these models are capable of doing the task but then they also fit on the right hardware that they also uh can do it with the right amount of latency depending on the that if it's a task for a user needs to happen in a couple seconds if it's a task where you're doing things like batch processing you maybe have slightly different thresholds for like what needs to be done um and then also what the cost of actually doing that is so if you have a sunken cost in terms of like infrastructure that you already own or that you're prepared to uh outlay and then operating on that or whether you're leasing like GPU time or something else like that. So these are going to be very specific to the task that you're trying to achieve. But what uh what you can do with open models is you can think very carefully about like what which of these tasks can I can I fully offload or can I fully own compared to relying just on using the best possible models to do uh that in the cloud.

</details>

### 设备端运行：手机上的多模态智能体

**Ian Ballantyne**: 举个例子。刚才 Gus 提到了能够运行这些模型的不同硬件类型。现在我将在旁边运行一个小演示。我们现在拥有了可以直接在手机等移动设备和边缘设备上运行的模型。这里展示的这个例子是 Coremax 团队构建的。它展示了一套**在手机上运行的智能体技能集**。为了这个演示，我先把麦克风静音。你可以和这个模型对话，你可以给它展示图片，展示你周围的世界，你可以向它发送指令并与它聊天。这个演示展示的是，它可以查看一系列赋予它的关于手机本地的技能。所以它能够直接在设备本身执行操作，例如触发其他应用程序，比如打开日历应用，打开地图应用，或者你可以自己定义技能集。与我们看到的上一代模型相比，Gemma 4 模型现在的不同之处在于，它能够**推理自己需要采取什么行动，并且能够可靠地去调用那些已经定义好的函数（Function Calls）**。所以这个应用其实就像是一个游乐场一样让你去体验。这是 **Google AI Gallery**，你可以在 iOS 和 Android 上找到它，你可以去实验一下，看看这个尺寸的模型实际上能够做到什么程度。我认为这应该是 20 亿参数的版本，但也有 40 亿参数的版本，这取决于你手机的硬件配置。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: and uh an example. So Gus talked about the different types of hardware that can run these things. Now I'm just going to run this little demo in the side at the moment. So we now have models that will work directly on mobile and edge devices. Uh this example here built by Coremax team. Um is a set of agent skills that the model is running on a phone. So uh I'm going to mute the microphone for that. Um, so you can talk to the model, you can show it images, uh, you can show it the world around you, and you can prompt it and chat to it. And what this one is showing is that it can look through a set of skills that it has about things on the phone. So either it can take actions on the device itself. So trigger other applications like trigger calendar apps, trigger maps apps, or you can kind of define your own skill sets. And what's different now with the Gemma 4 models than we saw for the previous generation is that it's able to reason about what actions it needs to take and reliably uh make those function calls defined. So what this app will allow you to do is is kind of acts as like a playground. Uh so this is Google AI gallery and you can find it on iOS and Android and you can experiment to see what the models of this size are actually able to do. So I think this is the two billion parameter model, but there's also the 4 billion parameter model depending on uh the size of your hardware.

</details>

### 从 API 计费到能源成本计费的思维转变

**Ian Ballantyne**: 当我们来到台式机和单张 GPU 时，正如 Gus 提到的，这就是你可以在本地硬件上使用 26B 和 31B 模型的地方了。我稍后会展示如何做到这一点。但这里有一个非常关键的点：虽然我们不再是以 API token 的价格来为这些智能体或模型买单，但我们实际上是在以**能源消耗（Energy Costs）**的形式为它们买单。如果我们仔细思考一下，因为现在你需要考虑 GPU 的利用率，考虑硬件设备本身 MPU 的利用率。你打算什么时候执行这些任务？是当你拍摄某样东西时用户需要立即获得响应，还是某种你可以作为后台任务、等用户晚上把手机插上电源时离线处理的任务？所以我想说的是，当你转向设备端运行或拥有模型的所有权时，思考使用这些模型的方式和阈值也会发生相应的转变，因为你更多地需要思考它们是如何被执行的以及为什么要这样执行。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: And when we get to desktops and single GPUs, as Gus mentioned, that's where you can use the uh the 26 and the 31B models again on your local hardware. And I'll show you how to do that in a minute. But there's one kind of key point here is whereas we're not paying for uh the price of these agents or models within tokens, we're actually paying for them in terms of energy costs. If we think about it, because now you're thinking about utilization of GPUs, you're thinking about utilization of MPUs on the hardware itself. Uh when are you going to do these tasks? Does the user need to get a response right now when you're taking a picture of something or is it something that you can process offline as a background task when they plug their phone in at night? So the what I'm trying to say here is that the thresholds and how you think about the usage of these models kind of shifts when you come to ondevice or ownership because you think more about how theyre being executed and why theyre being executed.

</details>

### 企业级降本增效与私有数据微调

**Ian Ballantyne**: 嗯，对，太棒了。同样地，在企业应用方面，如果你没有能够运行比如 310 亿参数模型的硬件，你现在就可以考虑**缩减规模（Scaling down）**了。也许以前你想要使用一个 3000 多亿参数的庞然大物，你可能需要很多张 GPU。现在，你可以考虑使用单张 **H100 或 A100**，在某些情况下甚至只需一张 **L4**。随之而来的，相关的成本显然也就降下来了。所以这同样是一个你需要根据自己的具体用例来计算的数学题。但你现在有办法去横向扩展了。举个例子，你可以运行一个这样的模型来为一个小型团队或者整个公司提供服务，这取决于你究竟想做什么。最后一点是，你还有**微调（Fine-tuning）**这一手段，也就是因为这些模型是可以定制的，所以你可以部署你自己专属的版本。例如，我们有一个 Gemma 模型的变体叫做 **Medgema**，它是专门针对医疗领域用例的。所以，如果你想要一个可以在你完全控制的私有数据上运行的模型，你现在完全可以可行地将其部署到一两张 GPU 上，去为比如说一整家医院提供服务。所以这些都是在企业场景中非常值得考虑的维度。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: Um yeah, perfect. Uh and similarly on the enterprise side, if you don't have a piece of hardware that can you know run the 31 billion parameter model, you can now be thinking about scaling that down. So maybe if you wanted to use a 300 plus uh billion parameter model before you might have need multiple GPUs. Now you can think about using a single uh H100 or A100 or even in some cases like an L4. And then the costs obviously related to that also kind of go down. So again it's a calculation that you'll have to do depending on your use cases. But there's ways that you could scale. For instance, running one of these models to serve, you know, a small team or to serve a company um depending on uh what you're trying to do. And the and the and the final point is that you also have the fine-tuning component too, which is that because these models can be customized, you can deploy your own version of it. So for instance, we have a variant of Gemma models called Medgema, which is specialized for medical use cases. So if you wanted to have something that would operate on private data that you can control yourself, you can now re feasibly deploy this to like one or maybe two GPUs uh to run that for I don't know like a whole hospital for instance. So these are kind of worth considering for the enterprise case.

</details>

### LM Studio 本地部署演示

**Ian Ballantyne**: 我现在要直接跳到演示环节了。我已经给你们展示过手机上的演示了，现在我要在这里展示一个快速的演示。大家快举个手，有谁曾经使用过一个叫做 **LM Studio** 的工具？好的，大约有不到一半的人。LM Studio 是一个让你能在本地把玩各种模型的工具。这里我运行的是 26B 模型。所以，这是我们在两个较大模型中推理速度更快的一个，它在每次推理中只会激活 40 亿参数。此刻，包含上下文在内，它大概占用了我 26GB 的内存（RAM）。这是一台 **M4 Mac**，所以它使用的是统一内存架构。我总共有最高大约 48GB 的可用内存。因此，我可以在这台机器上直接运行它。我这就把这个终端运行起来。让我们试试看。哎呀，不小心提前剧透演示了。我们再来一次。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: Uh I'm going to jump straight to demos now. Um I shown you some demos on the phone. I'm going to show you a quick demo uh here. Who quick show of hands. Who's ever used uh a tool called LM Studio? Okay, just under half people. So, LM Studio is a way that you can play around with local models. And I have here I have this is the 26B model. So, this is our faster of the the two larger models with four billion activated parameters. And I'm at the moment, including the context, it's probably about 26 GB in RAM. And this is an M4 Mac. So, I've got unified memory. I've got up to about 48 gigabytes. Uh, so I can run it on this machine. And I'm just going to run this terminal right here. Let's give that a go. Oops. Pre-showing my demo. Let's try that again.

</details>

### 多智能体并行翻译展示

**Ian Ballantyne**: 好了，启动了。我打算运行一个小进程，在我的设备上执行一个非常快速的多任务翻译。它要做的就是，在这个界面的这一侧我有一个编排器（Orchestrator），它很快就会触发我的智能体。让我们先确保模型已经加载完毕。我们来看看 LM Studio 在做什么，对，它正在处理。接下来，它会把这个翻译任务分发给所有这些不同的窗口，其中**每一个窗口都代表着一个独立的子智能体（Sub-agent）**。所有这些都是在我的本地设备上运行的，它要一次性并行执行所有这些语言的翻译工作。我刚刚把 Gemma 4 的发布公告输入了进去，我就是想把它翻译成所有这些不同的语言。你马上就会看到，它会把任务发散出去。3、2、1，好的，我们应该马上就能生成所有的翻译结果了。出来了！

<details>
<summary>Original English</summary>

**Ian Ballantyne**: There we go. So, I'm just going to run a little process where I'm going to do some quick a trick quick translation on my device. So, what it's going to do is I've got an orchestrator on this side here, uh, which is going to hopefully kick off my agent in a minute. Let's make sure we are loaded. Let's see what LM Studio is doing. Yeah, it's just processing at the moment. And then it's going to farm out uh, this translation to all of these different uh, uh, windows and each one of them represents a different sub aent. So, this is running on my device uh, and it's going to basically execute all these translations in one go. So I've given it like the Gemma 4 announcement and I just want to want to translate to all these different languages. So you'll see in a second it should hopefully send it over there. 3 two one and hopefully we should be generating translations a second. There we go.

</details>

### 本地 Agentic 生态展望

**Ian Ballantyne**: 所以，你可以想象在你的本地机器上执行任何类型的**智能体任务（Agentic Task）**。你可以让它在后台处理文件，你可以让它做额外的数据分析。希望你们马上就能看到，它能够把所有的翻译结果编译整合回来，然后为我生成一个简单的网页，这样你就能通过网页直接看到所有语言的翻译结果了。看，就是这样。这也同时展示了模型强大的多语言能力。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: So so you can imagine doing any kind of aentic task on your local machine. uh you could have it like processing files, you could have it doing additional analysis and hopefully what you'll see in a minute is it will be able to compile all these back and then it will generate me a quick web page and then you can see the results through the translation. There you go. So there's the multilinguality of the model there as well.

</details>

### 快速接入工作流与局限性探索

**Ian Ballantyne**: 好的，因为时间关系，我只想说，去探索和尝试这些模型的下一步其实非常简单，就像右边这段代码展示的一样。你可以使用你手头任何**兼容 OpenAI 格式的接口**，把它指向像 **Olama** 或者 **LM Studio** 这样的服务，然后你只要在配置里挑出 Gemma 模型，这就是你在代码层面为了尝试它而需要修改的全部内容。因此，我们建议你做的第一件事就是把它接入到你现有的工作流中，看看这个模型到底能处理到什么程度。例如，它在什么任务上表现得好？它在哪方面可能需要微调？又在何种复杂度的任务中显得力不从心？

<details>
<summary>Original English</summary>

**Ian Ballantyne**: Okay. Uh right. Uh so in the interest of time uh I just want to say that the the main next step for exploring and trying out these models is as simple as this code on the right hand side. Um you can take any open AI compatible interface that you've got and you can point it at a service like Olama or LM LM LM Studio and you can just pick out the gemma model and that's all you need to change codewise to at least uh try it out. So the first thing we recommend you do is to drop it into existing workflows that you have to then see what the model can handle. Like what is it working well at? What would it need tuning for? What is kind of out of its depth in terms of like the complexity of the task.

</details>

### 评估、成本与基础设施考量

**Ian Ballantyne**: 其次是要去强化你的评估测试套件。因为大家知道，基准测试虽然很棒，能够大体告诉你模型的通用能力处于什么水平，但现实是：**一个模型的好坏取决于它在你自己的特定任务上表现如何，而不是在别人的任务上表现如何。** 另外一件我刚才稍微提到过的事，就是仔细思考你最终要如何部署提供这些模型服务。如果你需要运行自己的 GPU 服务器，你需要亲自去托管它。没错，你可以完全控制它的开机、关机和运行时间，但随之而来的也是硬件的维护成本以及其他种种琐事。所以你必须要把比如“持续运营成本”以及为了实现这些所产生的前期基础设施硬件采购（CAPEX）等因素一并考虑在内。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: Um next is to kind of bolster your evaluation suites because you know benchmarks are great and everything for just saying what general capabilities are but the reality is that how good the model is depends on how well it does on your task and not anybody else's task. Um, the other thing I mentioned very briefly is thinking about how you actually serve these models in the end. So if you need to run your own GPU, you need to host it. Yes, you're in control of like uptown uptime and downtime, but then there's like maintenance costs and other stuff like that. So you have to be you have to consider that as like one of the factors like the ongoing costs as well as well as any upfront capex costs if you buy infrastructure or hardware to do that too.

</details>

### 总结与反馈

**Ian Ballantyne**: 例如，在移动设备上，你必须思考，如果我要把任务转移到手机上运行，我需要支持哪些硬件规格？手机里有哪些加速器硬件可用？它有多少内存？所以这些讨论会变得稍微复杂一些，但你换来的是解锁了大量全新的可能，比如完全离线工作，或者可以在**用户绝不离开设备的私人隐私数据上运行模型**。最后，如果你想把这种能力扩展到企业级规模，你就必须再次评估你所运行的基础设施类型，以及相应的持续运营成本。但开源模型确实开启了这扇大门。所以，总而言之，你可以以你能想到的几乎任何方式去使用这些模型。去尽情实验它能做哪些任务，参考一些基准测试来看看究竟可行性如何。但说真的，我们非常期待听到你们的反馈，想知道你们使用的感受，你们是如何进行微调的，以及在过程中遇到了哪些挑战。而且，我们也希望能在这个旅程中帮助到你们。所以，最后，非常感谢大家。

<details>
<summary>Original English</summary>

**Ian Ballantyne**: Um on mobile devices for instance you have to think about like if I'm going to offload stuff to a phone like what am I supporting? What accelerators do they have? What size RAM do they have? So the conversation becomes a little bit more complex but then there's a whole heap of things you can unlock like working offline or working on users private data that never leaves their device. Um and finally if you want to scale this up to enterprise levels you have to think then again about like the kind of infrastructure that you're running on and what the ongoing costs are of that as well. But it does kind of unlock that. So, uh, with that, the summary is that you can use these models in pretty much any way you can think about. Experiment what kind of tasks are possible with it. Use some of the benchmarks to kind of give you an indication of like what's feasible. But, uh, really we want to hear your feedback and how you get on with these and and how you fine-tune them and what kind of things you run into. And, uh, we want to help you on that journey as well. So, with that, thank you very much.

</details>