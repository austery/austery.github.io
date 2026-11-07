---
author: AI Engineer
date: '2026-09-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=g4SsanB0gMc
speaker: AI Engineer
tags:
  - model-serving
  - inference
  - architecture
  - benchmarking
title: 开源小模型自建推理服务与集群架构实践
summary: 演讲探讨了小型开源模型在专用任务中的性能优势及自建云端推理服务的挑战。主讲人提出通过拉取式网关架构、多模型混合打包与惰性加载，以及自动化研究闭环调优，在较小硬件上实现高吞吐、低延迟与显著降本。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Artificial Analysis
  - Nvidia
  - OpenAI
  - Hugging Face
products_models:
  - Qwen 36 27B
  - GLM 5.2
  - GPT 5.1
  - PyTorch
  - Candle
  - SGLang
media_books: []
status: evergreen
---
<!-- chunk 1/3 -->

好了，我想大家都能听到我说话。

<details><summary>Original English</summary>
All right, I think you guys can hear me.
</details>

我反正是能听清我自己的声音。

<details><summary>Original English</summary>
I can certainly hear myself.
</details>

嗯，谁坐得更靠前谁就能领到一件 T 恤。

<details><summary>Original English</summary>
Um, whoever came closer gets a t-shirt.
</details>

我是说真的。那边有一整包的 T 恤。呃，提问也是一样。也许最后会有一些提问环节。如果你提了问题，你也能拿到一件 T 恤。

<details><summary>Original English</summary>
I I meant it. There's like back full of t-shirts over here. Uh, and also for questions. Maybe there will be some questions at the end. If you ask a question, you get the t-shirt as well.
</details>

如果你能猜出这张幻灯片的背景上是什么，你也可以得到一件——你也可以拿到一件 T 恤。有谁猜得到吗？

<details><summary>Original English</summary>
And if you can guess what is on the background of this slide, you get a uh you get the t-shirt as well. Any guesses?
</details>

那是在把什么可视化？背景里的这张图？

<details><summary>Original English</summary>
What does that visualize? This picture in the background?
</details>

没有吗。有人见过 Transformer 模型吗？

<details><summary>Original English</summary>
No. Anybody has seen a transformer model?
</details>

>> 呃，对，位置编码（positional encoding）。非常棒。先生，你可以拿到一件 T 恤了。好的。

<details><summary>Original English</summary>
>> Uh yeah, positional encoding. Very good. You get the t-shirt, sir. All right.
</details>

### 开源小模型与自建推理

那么，今天我们基本上要讨论一下小型开源模型，以及它们现在有多出色，还有当你想在自己的云环境中提供一整套这类模型的推理服务时，它们会带来怎样独特的挑战。呃，我们要讨论的一切在某种程度上都是开源的。呃，完全可以自己动手做。

<details><summary>Original English</summary>
So, today we'll discuss u basically small open source models and how they are pretty good now and how they create unique challenges when you want to serve a bunch of them in your own cloud. Uh everything we'll discuss is kind kind of open source. Uh do it yourself.
</details>

这些内容属于那种你只需要运行一条命令就能掌控整套技术栈的东西。所以这里面没有任何专有的、所谓拼图里的专有组件。呃，让我们开始吧。

<details><summary>Original English</summary>
This is the kind of stuff you can just uh you know run a command and own the stack. So there is no proprietary uh you know pieces of the puzzle here. Uh let's get this uh underway.
</details>

好的，能翻页。行。那么，小模型。我们所说的小模型到底是什么意思？嗯，你知道这取决于你去问谁，我的看法基本上是指那些你可以在两三代以前的英伟达硬件上运行的模型。整个模型可以装进单张 GPU 里。

<details><summary>Original English</summary>
Well, this works. Okay. So small models. What do we mean by small models? Um you know depending who you ask, the way I think about it is basically models that you can run on two three generations old Nvidia hardware. The whole model fits into one GPU.
</details>

嗯，因此它们很容易进行服务部署，那些 GPU 随手可得，而且价格也很亲民。嗯，然后大多数人会想，好吧，小模型的话，在结果质量方面肯定会有某种权衡。希望在今天的演讲中，我能够很好地向大家证明，其实针对具体任务，你完全可以达到前沿、甚至超越前沿性能，并且获得所有其他显而易见的好处，对吧？呃，也就是成数量级的成本节约，当然还可能有非常显著的延迟降低或吞吐量提升。

<details><summary>Original English</summary>
um and therefore they are easy to serve those GPUs are available and they are affordable as well. Um and then most people think okay small models um there will be some kind of tradeoff in terms of um you know quality of the results and hopefully I'll be able to do a good job in this talk to convince you that actually for specific tasks you can be at frontier or beyond frontier performance and get all the other obvious benefits right uh orders of magnitudes of uh kind of cost savings and uh potentially quite big uh latency or throughput improvements of course.
</details>

嗯，所以这是我们喜欢展示的图表之一。这是 Artificial Analysis 的智能指数随时间变化的情况。

<details><summary>Original English</summary>
Um so this is kind of one of the charts we like to show. This is the artificial analysis intelligence index over time.
</details>

他们通常没有向你展示的是，你应该考虑的开源模型其实是有层级划分的，对吧？有像 GLM 5.2 等等那种前沿的开源模型，参数量比方说有 7500 亿。

<details><summary>Original English</summary>
And what they typically don't show you is that there is like a breakdown of the open source models you should think about right there is the GLM 5.2 and so on those kind of frontier open source models with let's say 750 billion parameters.
</details>

嗯，但随后还有那些紧跟大模型和前沿步伐的小型开源模型。你可以看到前沿模型如今在某种程度上正在遭遇收益递减，而小模型正在迎头赶上，对吧。所以，呃，你可以看到顶端出现了这种趋同、饱和，以及小型模型的这种增长。嗯，你知道，比如说 Qwen 36 27B，

<details><summary>Original English</summary>
Um but then there are the small open source models kind of trailing the big ones and trailing the frontier. You can see the frontier is kind of getting diminishing returns these days and the small models are catching up right. So uh you see this kind of convergence saturation on top and and kind of growth of the of the small models um and you know let's say quen 36 27b
</details>

性能大概在 GPT 5.1 左右。因此，如果你手头有一个工作流，如果你有一个可以借助 GPT 5.1 运行的流水线，现在你完全可以将其迁移到小模型上，并且获得我们刚刚讨论过的所有好处。所以小模型已经不再愚蠢了。

<details><summary>Original English</summary>
somewhere around the performance of GPT 5.1. So if you have a workflow, if you have a pipeline that uh you know can run with GPT 5.1, now you can move that to a small model and uh you know get all the all the benefits we discussed. So small models not dumb anymore.
</details>

### 专任务专用与模型集群的挑战

嗯，现在关键还在于你如何使用这些小模型，对吧？你不能仅仅把那个 270 亿参数的 Qwen 36 当作那种完全通用的、随便给个提示词就能做任何事情的模型。现在你需要采取一种策略，基本上是从通用模型的工作负载中拆分出一块块具体的任务，然后针对每项任务，在开源领域中找出最契合该任务的模型。你运行一些评估，可能还会进行一些我们稍后会讨论的适配调整，嗯，然后你就是通过这种方式来达到合适的质量，从而真正将其推向生产环境。

<details><summary>Original English</summary>
Um now it is also about how you use the small models, right? So you can't just treat that 27 billion parameter quen 36 as your kind of totally generalized I can prompt it to do anything kind of model. Now you need to adopt the approach where um you basically figure out slice of tasks from the generalized model workload and then per task you figure out which model in the open source fits the task the best. You run some evals maybe some adaptation we'll discuss um and then you know that's how you kind of reach the the right quality uh to actually push this into production.
</details>

这里有一个使用了九个不同模型的合同审查智能体示例。随着你转向在自身架构中使用小模型，你在你的工作负载和智能体中将会看到的就是这样一种形态。

<details><summary>Original English</summary>
So here is some example of a contract review agent that uses you know nine different models. This is the kind of shape that you will see in your workloads in your agents as you move to using small models for your um setup.
</details>

你会开始发现，好吧，你不再是用一堆不同的请求去反复冲击同一个 API 呃或者同一个模型，而是改用由一组模型组成的车队。那么你的问题就变成了：好吧，我该如何以一种不让我这边的基础架构人员抓狂的方式来为所有这些不同的东西提供服务，对吧？而这还仅仅是你在运行的其中一个智能体，在你们公司里可能还会存在 10 个这样的智能体。所以我们该如何——这可以说就是基础架构范畴的扩张。

<details><summary>Original English</summary>
you'll start to see that okay instead of kind of hammering one API with bunch of different requests uh or one model you rather use a fleet of models and then your problem is okay how do I serve all of these different things in a way that my infra people don't go crazy right and this is just one of the agents that you might be running and there might be you know 10 of these in your company so how do how do we sort of you know that's the kind of expansion of infrastructure scope let's say um
</details>

现在，针对我刚才提到的所有那些不同的任务，都正好有一个开源模型坐在那里等待被调用。嗯，从光学字符识别（OCR）、基于文档的问答，到图像标注、生成 SQL、审查代码，呃，都有针对这些任务进行过微调和训练的开源模型。呃，你知道，如果你使用一个专门训练来对越南语收据进行 OCR 的开源模型，那个项目见过的越南语收据就是最多的，对吧？有人花心思收集了尽可能多的数据，因而在那一项任务上，该模型的表现几乎会超越其他任何东西。

<details><summary>Original English</summary>
Now all of those different tasks that I mentioned there is an open source model that's uh sitting there waiting to be used um from you know OCR to question answering on top of documents to labeling images generating SQL you know reviewing code uh there are open source models fine-tuned and trained for those tasks uh you know if you use an open source model that's trained to do OCR on receipts in Vietnamese that project has seen the most receipts in Vietnamese, right? There's somebody who like took the time to gather as much data as possible and on that task that model will outperform pretty much anything else.
</details>

嗯，在 Hugging Face 上有成千上万个像那样的模型，对吧？所以，这些东西就摆在那里，而且基本都是免费的，大多数都有相当宽松的开源许可。所以模型是现成的，大家知道，瓶颈并不在模型本身。

<details><summary>Original English</summary>
Um, and there is, you know, hundreds of thousands of models on hagging phase that look like that, right? So, it's just uh it's all sitting there and it's all free basically mostly quite permissive licenses. So the models exist you know that that's not the bottleneck
</details>

而且大家知道，从 2024 年起我们就一直在谈论开源 AI 之类的事情，呃，但到目前为止它仍然没有真正发生。而在各家公司中，在它真正发生的范围内，基本上就等同于“开源 AI 等于 AWS Bedrock”，呃，除了一点：当你看一眼 Bedrock 里的模型目录，它在可用的模型类型上非常受限，这些模型很陈旧，呃，往往落后业界顶尖水平两到三年。嗯，而且当你在 Bedrock 中进行任何微调时，你实际上并不拥有微调或训练出来的产物。因此，你无法将其用作业务中的实际竞争壁垒。它基本上只能留在 Bedrock 的基础设施里提供服务。

<details><summary>Original English</summary>
and you know we've been talking about like open source AI since 2024 and uh it's so far still not really happening and to the extent it's happening in companies it basically equals like open source AI equals AWS bedrock uh except when you look at the model catalog in bedrock it's like very you know restrained in model types that are available these models are old uh often you two, three years behind the state-of-the-art. Um, and when you do any kind of fine-tuning in bedrock, you don't actually own the fine-tuned or trained artifacts. So, you can't, you know, use it as an actual advantage in your business. It kind of stays serving from the bedrock infra.
</details>

### 推理引擎调优与路由瓶颈

嗯，以上是专有方案的情况。现在，如果你在开源基础设施上进行小模型服务——vLLM、SGLang 等不同的解决方案——你只要知道，这些工具并不是针对任何特定模型或任何特定的“硬件-模型”组合预先调优好的。你必须自己去调优，对吧？这就是自己动手的部分。所有这些工具都附带指南，介绍如何实际执行调优、参数扫描、根据你的流量特征进行定制等等。每当你尝试采用其中一种工具时，这都变成了一种开放式的研究项目。所以这真不是那种你拿过来、当成一个常规工程项目、一周之后就能拥有一套高性能服务基础设施的东西；它完全不是这么运作的。嗯，而那正是开源工具典型的通病，对吧？就是有点太过于凡事都得自己动手了。

<details><summary>Original English</summary>
Um, so that's on the proprietary. Now if you do small models serving on open source infrastructure blm sglank different solutions just know that these things are not tuned for any specific model or any specific hardware model combination you'll have to do the tuning right this is the do-it-yourself all of these tools ship with guides on how to actually do the tuning the parameter sweep tailoring to your traffic and so on. This is a kind of open-ended research project every time you try to adopt one of these tools. So this is not really something that sort of you you take it and it's like an engineering project and a week later you have a high performance surveying infrastructure doesn't work like that. Um and that's kind of the typical problem with open source tools, right? This kind of like a little bit too much do it yourself.
</details>

嗯，然后除了没有针对小模型进行预先调优之外，那些使用大量不同模型的小模型工作负载和流量，在某种程度上彻底颠覆了推理集群的运作法则，对吧？在通常情况下，当你尝试为一个大模型提供服务时，嗯，你的问题在于：我该如何在多个 GPU 之间共享该模型？我该如何在顶层放置一个能理解所有这些 worker 状态的路由器？比如掌握 KV 缓存状态等等，然后自顶向下做出路由决策，判定好吧，这个请求应该分配给这个 worker 或那组 worker 等等，对吧？这是一种非常自顶向下的架构。

<details><summary>Original English</summary>
Um, and then on top of this not being kind of pre-tuned for small models, the small model workloads and traffic that uses a bunch of different models kind of flips the equation for inference uh kind of clusters, right? So normally when you try to serve one big model, um, your problems are how do I share that model across multiple GPUs? How do I have a router sitting on top that understands the state of all these workers? you know the KV cache state and so on and then makes a top- down routing decision of okay this request goes to this worker or this group of workers and and so on right it's very top down setup
</details>

但如果你面对的是耗时短的小请求，并且请求量极大，那么这种自顶向下的路由就会成为瓶颈，对吧？因为路由器掌握的 worker 状态版本会稍微滞后，而且如果你依靠这种预先决策机制，要在平衡每个 worker 上的本地队列方面做到绝对精准，就真的非常困难，因为小请求实在太多了，对吧？嗯，而且我们针对小模型和这类流量在 vLLM 以及 SGLang 路由器上做过实验，在持续负载下，你很难让你的 GPU 利用率突破 20% 到 30%。问题就在于那些批次（batches）的大小根本无法合理构建，根源就是遇到了路由瓶颈。

<details><summary>Original English</summary>
but if you have small and fast requests and you have many of them the this this sort of top down routing becomes the bottleneck right because the router has a little bit obsolete version of the worker state and it's just really hard to saturate the workers if you have that kind of upfront decision on that's that has to get it perfectly right in terms of u you know balancing the local cues on each of these workers because there's many small requests right um and you know like we have experimented with the VLM and SGline routers for small models and this sort of traffic and it's very hard to get your GPU utilization beyond 20 30% under constant load and the problem is that those batches are just not correctly sized basically because you that routing bottleneck.
</details>

嗯，然后第三个问题是，使用小模型时，你能从 LoRA 以及通用的模型适配中获得巨大好处。因此，你必须承载的服务流量中，就会包含有人跑来找你并提出：“嘿，我有 10 个 LoRA，我该怎么把它用在我们现有的服务技术栈上？嗯，或者我……

<details><summary>Original English</summary>
Um, and then the third problem is that with small models, you benefit a lot from Loras and just model adaptation in general. And so the traffic that you have to serve, you know, contains, you know, people coming to you and saying, "Hey, I have 10 loras. How do I, you know, use this with our serving stack? Um, or I
</details>

<!-- chunk 2/3 -->

“……有这个我昨晚搞的自定义微调模型。你知道的，呃，我、我想把它部署到生产环境里。”而 AI 工程师和基础设施人员之间，为了把那些——你知道的，LoRA 上线、自定义模型上线——进行的沟通，才是耗费时间的事情。基本上，在组织运转速度方面，这种沟通就是主要的阻碍，对吧？理想情况下，你会希望基础设施工程师做自己的工作，也希望那些 AI 工程师做自己的工作，他们在日常工作模式下不需要为了维持运转而互相沟通。这样，你知道的，他们基本上就不会互相阻塞了。呃，对于小模型的这种模型适配需求，在某种程度上打破了这种状态，造成了大量的来回沟通，呃，这就是个问题，对吧？呃，所以这些就是面临的一些挑战，涉及比如：好，我们有一堆小模型，我们该怎么构建集群？我们该如何高效地提供推理服务？

<details><summary>Original English</summary>
 have

 this





custom

 fine

 tune

 I

 made

 last

 night.

 You





know,

 um,

 I

 I

 want

 to

 serve

 this

 in





production."

 And

 this

 conversation





between

 the

 AI

 engineer

 and

 the





infrastructure

 person

 in

 getting

 those





you

 know

 lauras

 up

 there

 custom

 models





up

 there

 that's

 the

 thing

 that

 takes





time

 and

 basically

 that's

 like

 the

 main





killer

 in

 organizational

 uh

 velocity

 is





talking

 right

 like

 ideally

 you

 would





want

 the

 infrastructure

 engineers

 to

 do





their

 job

 and

 you

 would

 want

 to

 those

 AI





engineers

 to

 do

 their

 job

 and

 they

 don't





have

 to

 talk

 to

 operate

 on

 the





day-to-day

 mode.

 So,

 so

 you

 know

 they





they

 are

 not

 blocking

 each

 other





basically.

 Um

 and

 this

 kind

 of

 model





adaptation

 desire

 around

 small

 models





kind

 of

 breaks

 that

 and

 creates

 a

 lot

 of





back

 and

 forth

 and

 uh

 that's

 a

 problem





right

 uh

 so

 these

 are

 some

 challenges





related

 to

 okay

 we

 have

 a

 bunch

 of

 small





models

 how

 do

 we

 have

 a

 cluster

 how

 do





we

 serve

 this

 efficiently
</details>

### 集群架构与开源

呃，所以我们琢磨这个问题已经有一段时间了。其实我是来自 Superl 的 Daniel，我刚才把自我介绍给跳过了。呃，我们是一家来自旧金山、有风投背景的公司，在过去几年里一直在构建由 AI 驱动的搜索、文档处理系统以及 Agent，而我们的主要痛点一直都是推理。呃，具体来说，就是我刚才描述的那些问题。因此我们不断迭代、不断探索各种集群拓扑结构，用于——你知道的——在不同的环境中运行庞大且广泛的小模型机群，因为有时候你需要与某个平台一起部署在某些谁也不知道那里有什么可用资源的环境中。呃，你知道，小模型让这变得更容易，因为在任何环境下，你都能搞到一些 L4 或者某种小型 GPU 配额，这要容易得多。所以，我接下来会大致描述一下我们最终收敛采用的集群拓扑结构。顺便说一下，这整套东西都是 Apache 2.0 协议的，所以是完全开源的。呃，你们可以直接拿去封装，然后摇身一变成为一家推理初创公司。呃，这是开源的，从某种意义上的控制平面一直到在 GPU 上运行的底层组件全都是。呃，所以我们没有做任何保留。

<details><summary>Original English</summary>
um

 so

 we

 have

 been

 playing

 with

 this





problem

 for

 a

 while

 I'm

 Daniel

 actually





from

 superl

 I

 kind

 of

 skip

 the

 intro

 um





so

 we

 are

 you

 know

 VC

 backed

 company

 out





of

 SF

 and

 we

 have

 been

 building

 AI





powered

 search

 and

 document

 processing





systems

 and

 and

 agents

 for

 the

 last





couple

 of

 years

 and

 our

 main

 painoint





has

 always

 been

 inference.

 um





specifically

 these

 problems

 that

 I

 have





described.

 And

 so

 we

 have

 iterated

 and





iterated

 and

 explored

 different





topologies

 for

 clusters

 for

 uh

 running





you

 know

 large

 wide

 fleets

 of

 small





models

 in

 different

 environments

 because





sometimes

 you

 need

 to

 deploy

 together





with

 some

 platform

 in

 some

 environment





where

 who

 knows

 what

 is

 available

 there.





um

 you

 know

 the

 small

 models

 make

 it





easier

 because

 in

 whatever

 environment





you

 can

 get

 some

 L4s

 or

 some

 kind

 of





small

 GPU

 quota

 is

 much

 easier.

 So

 this





is

 kind

 of

 I'll

 describe

 a

 little

 bit





about

 the

 topology

 of

 the

 cluster

 that





we

 have

 kind

 of

 converged

 to

 and

 by

 the





way

 this

 whole

 thing

 is

 Apache

 2.0

 So





completely

 open

 source.

 Um

 you

 guys

 can





just

 take

 it

 and

 wrap

 it

 and

 now

 we

 are





an

 inference

 startup.

 Um

 this

 is

 open





source

 from

 kind

 of

 the

 control

 plane





all

 the

 way

 down

 to

 the

 thing

 that

 runs





on

 the

 GPU.

 Um

 so

 we

 we

 didn't

 pull

 any





any

 punches.
</details>

呃，其拓扑结构基本上是：有一个网关；我们没有使用那种预先决定什么请求去往何处的路由器，而是设置了一个网关，它会解析一部分请求，为请求附加一些元数据，把该请求插入到一个共享队列以及一些侧通道中。对此我稍后会详细讲一点。然后 Worker 从那个中心化队列中拉取（pull），而不是把数据推送（push）给 Worker。通过这种方式，它们可以更好地打满自身的负载。然后 Worker 的——呃，设置，我想我有张幻灯片是讲这个的——呃，将会说明我们基本上是如何将不同模型架构的复杂性，收敛吸纳到一组连贯的 Worker 中的，你知道，这些 Worker 不会存在相互冲突的 Python 依赖项之类的问题。呃，大体上这就是整体的拓扑结构。

<details><summary>Original English</summary>
Uh

 and

 the

 topology

 is





basically

 there

 is

 a

 gateway

 and

 instead





of

 having

 a

 router

 that

 kind

 of





predecides

 what

 goes

 where

 there

 is

 a





gateway

 that

 parses

 some

 of

 the

 request





and

 attaches

 some

 metadata

 to

 the





request

 inserts

 that

 request

 into

 a





shared

 queue

 and

 into

 some

 side





channels.

 I'll

 go

 a

 little

 bit

 into

 that





and

 then

 the

 workers

 pull

 from

 that





centralized

 queue

 instead

 of

 kind

 of





pushing

 the

 data

 down

 to

 the

 workers.





And

 this

 way

 they

 can

 saturate





themselves

 better.

 And

 then

 the

 worker





um

 setup

 I

 think

 I

 have

 a

 slide

 for

 that





uh

 will

 describe

 how

 uh

 we

 basically





absorb

 the

 complexity

 of

 different

 model





architectures

 into

 kind

 of

 a

 coherent





set

 of

 workers

 that

 you

 know

 don't

 have





like

 competing

 Python

 requirements

 and





stuff

 like

 that.

 Um

 so

 that's

 kind

 of





the

 overall

 topology.
</details>

### 请求的生命周期与网关设计

呃，这就是一个请求的大致生命周期。也许我只——呃，挑出这里的几点讲一下。呃，我们——你知道，关于 OpenAI 那种 API 标准，我们不喜欢的其中一点就是 Base64 编码的 JSON，它对小模型不友好，对高吞吐量也不友好。因此我们全程使用 MessagePack 这种二进制格式。呃，通过这种方式，我们也可以将所有多模态数据直接推送到实际的 API 网关中。这样就不会出现像——嘿，你知道，二进制数据放在这边，然后请求放在那边，接着集群需要访问你的云存储才能开始加载某些二进制数据、图像或视频。我们基本上把它全部编码，然后推送到网关。呃，接着网关会分离出其中的一些较重部分，以免堵塞内部队列，并在请求处于排队中时，在传输途中将其暂存到云存储中。所以，它在某种程度上会把这些比如说超过 1 MB 的请求拆分开来，然后在后端使用云存储。呃，但作为用户，你把所有的 bits 和 bytes 都推送到 API 层，正因如此，它提供了一个相当整洁的接口。

<details><summary>Original English</summary>
Um

 and

 this

 is

 kind

 of

 life

 of

 a





request.

 So

 maybe

 just

 uh

 I'll

 call

 out





a

 couple

 of

 things

 from

 here.

 Um





we

 you

 know

 one

 of

 the

 things

 we

 don't





like

 about

 the

 OpenAI

 kind

 of

 API





standard

 is

 the

 B

 64

 encoded

 kind

 of





JSON

 not

 good

 for

 small

 models

 not

 good





for

 high

 throughput.

 So

 we

 use

 message





pack

 throughout

 like

 a

 binary

 format.

 Um





this

 way

 we

 can

 also

 push

 all

 the





multimodel

 data

 through

 the

 actual

 API





gateway.

 So

 there

 is

 no

 like

 hey

 you





know

 binary

 data

 over

 here

 and

 then





request

 over

 here

 and

 then

 the

 cluster





needs

 access

 to

 your

 cloud

 storage

 to





start

 loading

 some

 b

 some

 binary

 data





images

 or

 videos.

 We

 kind

 of

 encode

 it





all

 and

 we

 push

 it

 through

 the

 gateway.





Um

 and

 then

 the

 gateway

 kind

 of





separates

 some

 of

 these

 heavier

 pieces





to

 not

 clog

 the

 internal

 queue

 and





differs

 it

 on

 cloud

 storage

 kind

 of





inflight

 while

 the

 request

 is

 in

 Q.

 So





it

 kind

 of

 splits

 up

 some

 of

 these





requests

 that

 are

 let's

 say

 over

 a





megabyte

 and

 then

 uses

 cloud

 storage

 in





the

 back

 end.

 Um

 but

 as

 a

 user

 you

 push





all

 your

 bits

 and

 byes

 into

 the

 API





layer

 and

 it's

 kind

 of

 clean

 interface





because

 of

 that.
</details>

呃，基本上整个技术栈都是 REST。也就是网关是 REST，Worker 也是 REST，然后它在本地通过 Socket 连接到不同的运行时。作为运行时，我们基本上有 PyTorch、Candle 和 SGLang。呃，然后当我们做优化时——我稍后会大致讲一下——我们如何确保无论使用的是哪种运行时，以及无论在该运行时中运行的是哪种代码，都是最高效的。基本上我们为此设置了一个自动研究闭环。呃，不过是的，请求的生命周期大致就是这个样子的。还有一个细节就是，你一定要确保网关——也就是请求首先到达的那个组件——不要做太多的工作，因为那样的话它就会变成瓶颈，对吧？所以你甚至都不想去完整解析整个请求。你希望能做到直接查看数据包，并且呃，弄清楚即将到来的数据的总体轮廓，做好注解，然后不管你有多少个 Worker，上百个 GPU 的 Worker 会去查看队列状态，并从那里拉取。至于队列，我们使用的是 NATS JetStream，那东西可以处理——你知道的——每秒百万级请求，它很难成为瓶颈。

<details><summary>Original English</summary>
Um





basically

 the

 whole

 stack

 is

 rest.

 So





gateway

 rest

 the

 the

 worker

 is

 rest

 and





then

 over

 a

 socket

 locally

 it

 kind

 of





attaches

 to

 different

 runtimes

 and

 we





have

 basically

 pytorch

 kendle

 and

 sglank





on

 the

 as

 as

 a

 runtime

 um

 and

 and

 then





when

 we

 do

 the

 optimization

 I'll

 kind

 of





go

 into

 that

 on

 how

 we

 make

 sure

 that





whichever

 runtime

 we

 are

 using

 and





whichever

 code

 is

 running

 in

 that





runtime

 is

 the

 most

 efficient

 one.

 we





have

 an

 auto

 research

 loop

 for

 that





basically.

 Um

 but

 yeah,

 so

 so

 life

 of

 a





request

 kind

 of

 looks

 like

 that.

 And





like

 one

 tidbit

 is

 that

 you

 really

 want





to

 make

 sure

 that

 the

 gateway

 that's





kind

 of

 the

 first

 thing

 that

's

 hit

 by





the

 request

 doesn't

 do

 too

 much

 work





because

 then

 it

 becomes

 a

 bottleneck,





right?

 So

 you

 don't

 even

 want

 to

 parse





the

 whole

 request.

 You

 want

 to

 be

 able





to

 kind

 of

 look

 at

 the

 packets

 and

 uh





figure

 out

 the

 general

 shape

 of

 what's





coming.

 do

 the

 annotation

 and

 then

 you





have

 the

 workers

 however

 many

 workers





you

 have

 hundreds

 of

 GPUs

 that

 that

 uh





look

 at

 the

 queue

 state

 and

 then

 pull





from

 there

 and

 and

 the

 queue

 we

 use

 u





nats

 jetstream

 and

 that

 thing

 can

 do

 you





know

 million

 requests

 per

 second

 like





that's

 very

 hard

 for

 that

 to

 become

 a





bottleneck
</details>

### 中心化队列与批处理

呃，所以是的，理想情况下，你肯定不想在穿过所有这些不同组件时来回序列化、反序列化，这基本上属于显而易见的事情。呃，这是一段小动画，展示了中心化排队背后的理念，对吧？因此，与其由自上而下的路由器试图去——你知道的——恰到好处地填满本地队列（这基本上是不可能的），呃，你知道，其核心思路就是：嘿，我们能不能把排队以某种方式中心化？Worker 能不能改为自己承担起组建批次（Batch）的任务，由它们自己来预测该批次的开销，呃，进而——你知道的——变得高效得多？现在有一个细节和附带说明：一旦你开始研究这些东西，呃，你就会意识到，要预测呃从该共享队列中取走多少任务才能让批次大小真正达到、真正处于最优，实际上是非常困难的。因此你会希望有某种机制，在发现“噢，我好像拉取得有点太多了”的时候，允许你把一些东西放回队列中。而那是一次网络跳转，对吧？所以那是个问题。为此，针对本地拥有多个 GPU 的机器，我们做出了专门的优化，对吧？也就是说，存在一个额外的机器本地排队组件，它利用了这样一个事实：在同一台机器上的多个 GPU 上运行的本地进程，可以与队列进行稍微多一点的来回协商。而这要是走网络的话，你知道，那会增加几毫秒的额外开销。因此，呃，我们——我们不会走网络来做这件事，只有当我们将 Worker 协同部署在多 GPU 机器上时才会这样做。

<details><summary>Original English</summary>
um

 so

 yeah

 like

 ideally

 you

 don't

 want





to

 serialize

 this

 serialize

 as

 you

 go





through

 all

 of

 these

 different





components

 that's

 basically

 the

 kind

 of





obvious

 thing.

 Um

 this

 is

 a

 little





animation

 that

 shows

 the

 idea

 behind

 the





centralized

 queuing,

 right?

 So

 instead





of

 the

 top

 down

 router

 trying

 to

 uh

 you





know

 fill

 in

 the

 local

 cues

 just

 right,





which

 is

 basically

 impossible.

 um

 you





know

 the

 the

 whole

 idea

 is

 hey

 can

 we





somehow

 centralize

 the

 queueing

 and

 can





the

 workers

 uh

 rather

 pick

 up

 the

 task





of

 forming

 their

 own

 batches

 with

 their





own

 prediction

 of

 the

 cost

 of

 the

 batch





uh

 and

 and

 then

 you

 know

 become

 much





more

 efficient.

 Now

 one

 tidbit

 and

 kind





of

 side

 note

 once

 you

 kind

 of

 start





working

 on

 these

 things

 uh

 you

 realize





that

 it's

 actually

 really

 hard

 to





predict

 u

 how

 many

 things

 to

 pick

 up





from

 that

 share

 queue

 for

 the

 batch

 to





be

 really

 like

 really

 the

 optimal

 size





and

 so

 you

 would

 want

 some

 mechanism





that

 sort

 of

 allows

 you

 to

 put

 some





things

 back

 into

 the

 queue

 if

 you

 figure





out

 oh

 like

 I

 pulled

 a

 little

 bit

 too





much

 and

 that's

 a

 network

 hop

 right

 so





that's

 a

 problem

 and

 we

 have

 special





optimization

 for

 that

 for

 machines

 that





have

 multiple

 GPUs

 locally,

 right?

 So





there

 is

 a

 there

 is

 additional

 kind

 of





machine

 local

 queueing

 element

 that





takes

 advantage

 of

 the

 fact

 that

 the





local

 processes

 that

 run

 on

 the

 multiple





GPUs

 on

 one

 machine

 can

 kind

 of





negotiate

 with

 the

 queue

 a

 little

 bit





back

 and

 forth

 which

 over

 the

 network





you

 know

 there's

 like

 milliseconds

 extra





that

 that

 would

 add

 and

 so

 uh

 we

 we





don't

 do

 it

 over

 the

 network

 only

 when





we

 collocate

 the

 um

 workers

 on

 multiGPU





machines
</details>

而且你知道，我——我的意思是，我们这里谈论的可不是 5% 的差距，对吧？也就是说，你将队列中心化之后，现在集群的吞吐量翻了一倍。所以这——这是相当可观的。呃，我提到了三种不同的运行时。基本上，要么是——你知道——比方说对于纯编码器（encoder-only）模型，我们编写 PyTorch 代码并对其进行优化，而且我们有一个自动研究闭环来优化它。对于 Candle 也是一样。我们在不久前开始尝试使用 Candle。我们仍然无法让它的性能达到接近 PyTorch 的水平。所以它目前更像是一个研究项目。主要在于依赖项方面，比如，你知道，带有 PyTorch 的 Worker Docker 镜像大概有 12 GB，而基本上带有 Candle 的静态链接二进制文件的 Worker，体积大概只有它的 10%，对吧？如果你在乎从冷启动状态唤醒并将这些镜像加载到一堆不同的机器上，那么你知道，从 12 GB 降到 1 GB 左右，这会带来巨大的差异。所以这就是 Candle 背后的动力。只是要从它上面获得与 PyTorch 相同的性能，真、真的是非常困难。然后我们引入了 SGLang，作为一种首选的基准线；也就是说，在对我提到的所有那些参数进行最优调优的情况下，我们的性能至少应该达到和 SGLang 一样好，那些

<details><summary>Original English</summary>
and

 you

 know

 the

 I

 mean

 we

 are

 not





talking

 about

 like

 5%

 differences

 here





Right?

 So

 like

 you

 centralize

 the

 queue





and

 now

 you

 get

 double

 the

 throughput

 of





the

 cluster.

 So

 this

 is

 this

 is

 uh





significant.

 Uh

 I

 mentioned

 three





different

 runtimes.

 So

 basically

 it's





either

 you

 know

 we

 write

 let's

 say

 for





models

 that

 are

 encoder

 only

 we

 write





the

 the

 PyTorch

 code

 and

 we

 kind

 of





optimize

 it

 and

 we

 have

 a

 auto

 research





loop

 that

 optimizes

 it.

 Same

 for





Kendall.

 We

 started

 to

 play

 with

 Kendall





not

 too

 long

 ago.

 We

 still

 can't

 get

 it





to

 perform

 anywhere

 near

 the

 PyTorch





performance.

 So

 it's

 a

 little

 bit

 more





of

 a

 research

 project.

 It's

 just

 the





dependency

 like

 you

 know

 the

 worker





Docker

 image

 with

 PyTorch

 is

 like

 12

 GB





and

 the

 worker

 do

 basically

 binary





statically

 linked

 binary

 with

 Kendall

 is





maybe

 like

 10%

 of

 that

 right

 and

 if

 you





care

 about

 uh

 kind

 of

 waking

 up

 from

 the





cold

 state

 and

 loading

 these

 images

 on





bunch

 of

 different

 machines

 the

 you

 know





going

 from

 12

 gigs

 to

 a

 gigabyte

 or





something

 like

 this

 makes

 makes

 a

 huge





difference.

 So

 that's

 kind

 of

 the





motivation

 behind

 Kendall.

 It's

 just

 the





the

 getting

 the

 same

 performances

 from





PyTorch

 is

 is

 is

 really

 hard.

 And

 then





SG

 lang

 we

 have

 there

 as

 a

 kind

 of

 uh

 go





to

 baseline

 like

 we

 should

 perform

 as

 at





least

 as

 well

 as

 as

 SGANG

 with

 the





optimal

 tuning

 of

 all

 of

 those





parameters

 that

 I

 mentioned

 that

 you
</details>

<!-- chunk 3/3 -->

### 运行时抽象与基准测试拐点

必须进行调优。这里有一些数据。比如，当我们用套接字（socket）以及我们那种 Rust sidecar 来包装 SGLang 时，实际上我们能够比裸运行 SGLang 的性能有所提升，仅仅是因为我们在批处理（batching）方面做了一些 SGLang 原生并不做的事情。如果你为 SGLang 开发自定义插件之类的东西，大概也能做到，或许能达到和我们相同的性能，因为你可以直接把相同的逻辑推入 SGLang 核心服务器中。但这样一来，你开发的自定义代码就只能在 SGLang 上运行。而关于小模型，整个经验教训就在于运行环境（runtimes）极其多样，对吧？你并不一定想被绑定在任何单一特定运行时上，因为你知道，我们现在为不同模型参数化的大概有 50 种不同的适配器（adapters）。所以你必须以某种方式应对这种底层复杂性，而这大概不是靠为某一特定运行时构建一堆插件来实现的，大概需要某种抽象——在我们的案例中，就是这种 Rust sidecar 概念，以及后面的套接字。

<details><summary>Original English</summary>
have to do the tuning. Um here is some numbers. So for example when we wrap SG lang with the socket and with our kind of RAS side car um actually we can improve on the bare sglank performance just because we kind of uh do something on the batching side that natively sglang doesn't do and probably you can make it to do that if you do like if you develop custom plugins into sglang and stuff like that like probably you can match our performance because you know you can just push the same logic into the SG Glang core server uh but now you are developing custom code that only works with SGLAN and the whole lesson here from small models is that the runtimes are super diverse right you don't want to necessarily get staged with any one particular runtime because there is you know we have I think on the order of 50 different adapters now that that we parameterize for the different models and so you need to somehow deal with this kind of underlying complexity and it's probably not by building a bunch of plugins for one specific runtime it's probably some kind of abstraction uh which in our case is this rust site car concept and then the socket um
</details>

现在我来谈谈几个不同的数字。但在基准测试相关的术语方面，拐点（the knee）这个概念是指：当你增加服务器上的流量时，当你向它索取越来越多的吞吐量并且它也给你越来越多的吞吐量时，那是一个类似线性上升的阶段。然后到了某个点，你达到了这样一个位置：你要求更多，但更多的吞吐量并没有出来。于是吞吐量基本趋于平缓，而延迟上升。所以我们把那个点称为“拐点”（the knee），这是基准测试中一个很有用的概念。因为那可以说是饱和点，对吧？那是在不损害延迟的前提下的最大性能。

<details><summary>Original English</summary>
now I'll talk about couple different numbers but in terms of like language around benchmarking you know the knee is this concept of like when you ramp up traffic on a server uh when you sort of request more and more throughput from it and it gives you more and more throughput that's when you go kind of linearly up and And then at some point you hit this point where you kind of ask for more and more is not coming. So you kind of flatten out and the latency goes up. So we call that the the knee and it's it's like a useful concept in in benchmarking. Uh because that's kind of the point of saturation, right? That's that's kind of the maximal performance without hurting latency. Um
</details>

### 小硬件上的性能潜力：嵌入与生成任务

为了让大家了解在相对较小的硬件上可以实现什么，对吧？以及不同类型的小模型。这是在 RTX Pro 6000 上测得的。我们通常使用 Nvidia L4、A100、RTX Pro 6000、H100，大概就是这个范围。同样，这些 GPU 在任何云端按需获取都容易得多。基本上，大多数大洲都有配额，你知道的。在这类硬件上，对于嵌入模型，即使参数量达到比如数亿级别，基本上每秒也能将数十万个 token 编码为向量嵌入，对吧？所以想象一下，你现在坐在那里调用 OpenAI API 上的文本嵌入（text embedding 3）；相反，你完全可以拥有一块 GPU，每秒往里面推送 50 万个 token，并输出向量，对吧？

<details><summary>Original English</summary>
so just to give you some ideas of what is possible on relatively small hardware, right? And different types of small models. So this is measured on the RTX Pro 6000. We we kind of work with Nvidia L4, you know, A100's, RTX Pro 6000, H100, that sort of range. Um, again, those GPUs are much more readily available kind of on demand in any cloud. Basically, most continents have quota, you know. Um and on this kind of stuff uh you can basically get uh for embedding models even up to let's say uh hundreds of millions of parameters you can get hundreds of thousands of tokens per second encoded into the embedding right so imagine you are sitting there now like hitting your text embedding tree on open AAI API instead you could be like having one GPU and push half a million tokens per second into that thing and get the vectors out right
</details>

大家能理解这种对比吗？你把每秒 50 万个 token 推入一块甚至都不算太大的单 GPU 中，为你的搜索系统输出向量嵌入；相比之下，如果把所有这些推到某处的托管嵌入端点，要多付几个数量级的钱，对吧？而且这些调用的延迟可以低至几十毫秒。如果你使用 Cohere、OpenAI API 等等，那些都是几百毫秒，对吧？这并不是什么高深莫测的技术，只需几块 GPU 和围绕它们搭建的一些基础设施，你就能获得巨大的成本节约、显著的延迟改善以及相对容易的运维，对吧？所以如果你要从某个切入点开始使用开源模型和小模型，嵌入绝对是不二之选，对吧？

<details><summary>Original English</summary>
like is this like connecting right you have half a million tokens that you are pushing into single GPU that's not even that big per second and you are getting out vector embeddings for your search system as opposed to like pushing all of that into a managed embeddings endpoint somewhere and paying like orders of magnitude more money right and you can get latencies like you know low tens of milliseconds for these calls like if you use uh you know cohhere openai APIs and so on these are hundreds of milliseconds right and and this is not rocket science you know you can have just like massive costsaving massive latency improvements and relatively e easy operation um with with like handful of GPUs and some some infra around them right so this is like really low hanging fruit if you start anywhere with open source models small models embeddings are like no-brainer, right?
</details>

但这还不止于此。假设你想做命名实体识别（NER），想做多向量搜索，甚至是文本或结构化输出的生成速率等等。针对特定任务的生成模型，每秒也能输出数千个 token；底部那块单 GPU 比如每秒能输出五百个 token。所以假设你在生成合成数据，在为微调或评估生成标注，千万不要在托管端点上做这些。这是个绝佳的任务，因为你对它有控制权，可以审查质量。对于在你自建基础设施上运行的开源模型来说，这再合适不过了。而且，如果你围绕那些 GPU 搭建的基础设施足够合理，性能会随着 GPU 数量呈线性扩展。

<details><summary>Original English</summary>
Uh but it doesn't end there. So let's say u you want to look at uh named entity recognition, you want to look at let's say multi vector search u even generation rate uh of text or structured outputs and so on. um you you can be getting you know thousands of tokens per second output from uh you know task specific generative models as well per uh like let's say half a thousand per second for for one GPU there at the bottom um and so let's say you are generating synthetic data you are generating annotations for your finetuning for your evals you know don't do that on a on a managed endpoint That's a perfect task because you have it kind of under control. You can survey the quality. That's a perfect task for uh open source model on your own infra. Um and then you like if the infra you have around those GPUs is like reasonable you'll get linear scaling with with the number of those GPUs. Um
</details>

### 服务架构与自动化研究循环

现在，如果你涉足小模型服务（serving），另一个思路是：通常每个模型都会有一个工作节点池（worker pool），对吧？你有一组 worker、一组节点，它们配有 GPU，你把它们启动，预加载模型；由于模型有数千亿参数，需要加载几十分钟；加载完后你很高兴，好的，终于加载好了，现在我有了一个 worker pool。这种思维方式对于小模型并不适用。对。对。快问一下，还剩多少时间？

<details><summary>Original English</summary>
now another sort of u idea if you are into small model serving uh is that you don't you know normally um you have kind of worker pool per model right you have a set of workers set of nodes uh they have GPUs you kind of bring those up you preload the models the models load for tens of minutes because there are hundreds of billions of parameters uh and so you're happy okay they finally loaded now I have a worker pool this mentality doesn't really work with small models. Yeah. Yeah. Quickly. How how what's the time left?
</details>

>> 已经超时了。

<details><summary>Original English</summary>
>> Over.
</details>

>> 噢，六分钟已经超时了。好的。行吧。所以，将多个模型打包在同一块 GPU 上速度更快。

<details><summary>Original English</summary>
>> Oh, six minutes is over. Okay. All right. So, pack models on the same GPU is faster.
</details>

这里讲的是：你依然希望固定（pin）某些模型，但你也希望基本上根据内存压力来进行惰性加载（lazy loading）和逐出（eviction）。你得想办法把这两者结合起来。这里稍微讲一点自动化研究（auto research）。我们有自动研究循环，用于添加对新模型的支持以及优化它们的性能。我们构建了许多内部工具来进行测量并输入到这些自动研究循环中，以此推动性能指标不断提升。也许最重要的一点是，当我们发布对某个模型的支持时，所有的调优工作都已就绪，对吧？不需要去搞参数寻优（parameter sweep）。我们基本上为整个集群端到端打包了一份配置。这是自动研究循环的架构设置。有一个元循环（meta loop）来构建测试框架，然后运行该循环，上面还有一个仪表板帮助你了解它是如何工作的。我们为此开发了定制 UI。

<details><summary>Original English</summary>
Um, this is a story of how you still want to pin some models, but you want to also do u basically uh lazy loading and eviction uh as a kind of function of memory pressure. You want to figure out how to combine the two. Um there is a little bit about kind of auto research. We have auto research loops for uh adding support for new models and for their performance. Um we build a lot of internal tooling to do the measurement to feed into those out research loops to basically push the numbers forward. Um and maybe perhaps most importantly when we ship support for a model it has all the tuning done right. So there is no okay let's do a parameter sweep. We bundle basically a config for end to end the whole cluster. Um this is a setup for the auto research loop. There is like a meta loop that builds the harness that then runs the loop and there is a dashboard on top that helps you understand how it works. Um, we have custom UIs for that. And
</details>

其中的产出之一是一个训练成本仅为 80 美分的 LoRA，作为概念验证，它将德语法律文本的检索质量提升了 18%。讲完了。所以小模型很好，它们相对容易提供服务，实际上便宜得多、速度更快、一样聪明。那个二维码通往我刚才介绍的集群系统的 GitHub 仓库。请给我们点个 star，祝自建托管愉快。谢谢。

[掌声]

<details><summary>Original English</summary>
one of the outputs of that was a Laura that took 80 cents to train and it improved 18 it improved quality of retrieval on German legalist STEX as a proof of concept by 18%. And that's it. So small models are good. They are relatively easy to serve. uh they are actually much cheaper, faster, is as smart and that QR code goes to the GitHub repo of our cluster that I just described. Give us a star and happy self-hosting. Thank you.

[applause]
</details>