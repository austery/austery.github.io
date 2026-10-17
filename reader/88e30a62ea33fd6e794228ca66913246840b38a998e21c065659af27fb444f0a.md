---
author: AI Engineer
date: '2026-06-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ILdE7FaAjVA
speaker: AI Engineer
tags:
  - cloud-infrastructure
  - gpu-computing
  - serverless
  - llm-deployment
title: 5分钟内部署LLM服务端点：RunPod的Serverless架构解析
summary: RunPod开发者详细演示了如何通过其Serverless平台与Hub生态，在5分钟内完成大语言模型（LLM）从配置到API端点生成的全过程。文章解析了RunPod解决GPU基础设施管理痛点的核心价值，并介绍了其涵盖Pods沙盒、自动扩缩容及训练集群的产品矩阵。
insight: ''
draft: true
series: ''
category: deployment
area: tech-engineering
project: []
people: []
companies_orgs:
  - RunPod
  - AWS
  - Hugging Face
products_models:
  - vLLM
  - Docker
media_books: []
status: evergreen
---
### RunPod的定位与核心价值

**RunPod** 是一家云端 AI 基础设施公司，提供 GPU 硬件资源，让开发者能够轻松部署自有私人模型或来自 **Hugging Face** 的开源模型。它解决的核心问题是简化基础设施的管理。过去，在 **AWS** 或 Google Cloud 普及之前，企业必须维护本地服务器（on-prem servers）；如今在 AI 领域，开发者同样乐于将繁琐的底层硬件维护交给专业的云平台。此外，当前全球正处于 GPU 供应短缺的阶段（类似于疫情期间的卫生纸抢购潮），获取 GPU 既缓慢又不透明。对于开发者而言，首要精力应该聚焦于构建带来业务价值的应用程序，而不是管理基础设施。

<details><summary>Original English Source</summary>
Audrey, um I am from RunPod. Um this is an intro to RunPod. Can I just get a quick hands to see how many people have already heard of RunPod or maybe even used RunPod before? Okay, newbies for everybody. Great.

Um So, RunPod, we are a cloud AI infrastructure company. So, we have the hardware, we have the GPUs, and we make it easy for developers to deploy um models. And that can be your own private model, it can be an open-source model from Hugging Face. Doesn't matter to us. You bring your code and we'll bring the rest.

Um just really quickly, what problems does RunPod solve? Like, why are we even here today? Um infrastructure can be hard, managing it. I think about back in the day before we had AWS, um Google Cloud, when everybody would have to have on-prem servers and manage those, maintain those. That [clears throat] is something that we don't want to have to do as developers. Those are things that we happily um have moved away from and given off to DevOps, and now it's even it's even more abstracted for us.

GPU access is slow and opaque. So, um I don't know if you if anybody has tried to buy a GPU recently, we're in a global supply crunch. Um it's a bit like in COVID when everybody went to the store and bought all the toilet paper because we didn't know how how long they would need to be at home for. We're a little bit in that right now. Um but we expect the market will recover um as customers, companies, people figure out a little bit better, uh get a little bit better at um estimating what kind of compute they need.

Um and then last, builder primary focus should be building. So, again, um we want to build we as software developers, uh we bring bring the value through the applications that we build, um not from managing the infrastructure.
</details>

### 从地下室矿机到千万营收的起源

RunPod 的起源故事非常贴近开发者社区。2022年，创始人 **Zenon** 和 **Pardeep** 在地下室拥有几台用于加密货币挖矿但最终失败的 GPU 矿机。他们随后在 Reddit 上发帖，邀请大家免费使用这些 GPU 并提供反馈，这便构成了 RunPod 的底层原型，并且公司从那时起就一直保持盈利。这个故事不仅体现了早期创业的自举（bootstrapping）精神，更表明 RunPod 始终坚持从构建者出发、与社区（Reddit, Discord）保持紧密互动的核心理念。目前，平台上已有超过 50 万名开发者，在全球拥有 30 多个数据中心（包括欧洲），年度经常性收入（ARR）已突破 1.2 亿美元。许多 AI 云原生公司也正是为了寻找灵活、可靠的 GPU 基础设施而成为他们的客户。

<details><summary>Original English Source</summary>
And I think RunPod has a pretty unique story. These are These are our founders, Zenon and Pardeep. Um so, they had a couple of GPU rigs in their basement in 2022, um failed crypto mining, and then so they're like, "What are we going to do with our GPUs now?"

Um so, they prototyped what is now the foundations of RunPod. They posted on Reddit and said, "Hey, anyone want to use these GPUs for free? Just give us feedback on it." And that is literally how our company has started, and we have been um revenue generating ever since.

Um and the reason why I want to tell this story is um not because it's it's very like bootstrappy, but because um the origin origin story of RunPod has always started with uh builders and getting feedback from the community, and that is still true today. So, I won't promise that we'll be perfect, but um we are definitely very engaged with um our users on on Reddit, um on Reddit, on Discord. So, um we're always trying to stay engaged with y'all.

Um just at a glance to give you an idea of RunPod, we have over 500,000 developers on our platforms, 30-plus data centers across the world, including um Europe and the EU. Um and we've just passed a significant revenue milestone for us, 120 million in annual recurring revenue.

Uh these are just a few of our customers. Um you might be surprised to see some of the AI cloud-native companies on here, too, but um they come to us for the same reasons that most of our customers come to us. It's um because they need flexible and reliable GPU infrastructure.
</details>

### 核心产品矩阵：Pods、Serverless 与集群

在 RunPod 平台上，开发者可以根据不同的业务需求选择对应的计算资源模式：

*   **Pods**: 这是沙盒式的虚拟环境。平台为你启动一个容器并分配 GPU，你只需自带 **Dockerfiles** 和代码，平台负责管理其余部分。
*   **Serverless**: 这是一个自动扩缩容（Auto-scaling）产品，非常适合**实时推理**、突发性工作负载或批处理任务。与始终在线的容器不同，Serverless 架构下的工作节点（workers）在闲置时会自动缩减规模，让你无需为闲置时间付费，同时也免去了提前估算算力需求的麻烦。你可以自由设定最大工作节点数、支出上限，甚至配置保持“常驻开启（always on）”的节点以实现即时响应。
*   **Clusters**: 针对重型训练任务，RunPod 提供具备高速网络连接的多节点集群。
*   **Hub**: 这是一个类似于中央应用商店的 AI 仓库。里面包含了预先配置且经过审查的开源模型库，开发者可以一键 fork、收藏，并直接部署到 RunPod 环境中。

<details><summary>Original English Source</summary>
This is a really high-over high-level overview of um different ways you can build on RunPod. So, I would say our core at our core, um pods, it's our sandbox virtual environment. We spin up a container for you, um allocate GPUs to it, and we manage the rest. You just bring your um Dockerfiles, you bring your code.

Serverless, um it's our auto-scaling product. So, when you're thinking more about like bursty workloads or batch workloads, um serverless is really great because um instead of being always on like a container is, serverless um your workers spin down, and when they're idle you don't pay for anything.

Clusters, um if you were doing some heavy-duty training, there's a place for you as well on RunPod. Um multi-node clusters with high-speed networking.

And then the hub, which I'll I'll I'll switch to in a second, um it's kind of like our central repository for AI repos. Um these are already preconfigured, pre-vetted. Um we have a couple of examples of listings by RunPod for popular models, but also our community um contributes to them as well. So, there's repos that you can fork, you can watch, and then um you can star and deploy on RunPod.

Um so, today we're going to be talking mostly about serverless. Um so, serverless is best for real-time inference. I talked about the auto-scaling that comes with it. Um why teams use it is mostly because they don't need to um preempt and figure out how much compute they need ahead of time. Um You can set you can configure the number of max workers that you want to scale up to. You can set limits for caps, for spending caps. And you can also configure workers that are always on, so they're um already have your models downloaded, and they can respond to requests um immediately. For a lot of teams, serverless is the fastest way um if you want to start deploying a production-ready API.
</details>

### 5分钟部署实战：从Hub到API端点

通过 RunPod 的 Web 控制台，部署一个基于 Serverless 架构的大模型服务非常便捷。首先进入 **Hub** 选择一个目标 LLM 镜像仓库，这些底层通常是标准的 GitHub 仓库，内置了预先配置好的 Dockerfile 和默认参数。

在点击部署前，你可以通过传递不同的环境变量来深度定制服务。例如，展开高级选项，调高 **Max Model Length**（最大模型长度）以适应更长的上下文窗口。这些配置选项最终会作为参数传递给底层的 **vLLM** 服务框架。

部署完成后，系统会为你提供一个标准的 HTTP API 端点。首次发送请求时，由于存在**冷启动（Cold Start）**现象——系统需要创建容器并下载数百GB的模型文件——你的请求可能会在队列中等待几十秒（例如演示中的 41 秒）。然而，一旦模型初始化完成进入运行状态，实际的推理执行时间仅需 1.5 秒左右，随后的请求将获得极高的响应速度。平台还提供了**遥测（Telemetry）**面板，实时监控请求数、执行时间和延迟等关键指标，确保服务端点的可观测性。整个过程从零开始到获得一个生产级别的 API 端点，耗时不到 5 分钟。

<details><summary>Original English Source</summary>
And now I'm going to switch over and just show y'all really quick how easy it is to get started and deploy something. Okay. Where are we? Okay. So, right now I'm um going to do everything via the console so that it's nice and pretty for you guys to see, but we also have um CLI support. We have skills um to help work with RunPod, everything that's ready for your agent so you don't have to read our documents, but since we're all humans here today, I'm going to show you via the console.

Um we'll start in the hub, which is if you're just trying to explore and see what's out there, what is something that you can get up and running right now, the hub is a great place to start. So, like I mentioned, these are already vetted open-source listings for um AI repos, and I am going to pick the LLM, um and I'll just open the underlying repository as well so you could guys can see what it is literally just a GitHub um repo. It tells you how to get set up for it. Um we can see there's already the Dockerfile here. It's already preconfigured for you. It's got some defaults for you um depending on the listing. You can um pass in different environmental variables um to configure it how you wish.

But I'm just going to go ahead and click deploy. And I have a model that I wanted I Let me see. I was going to just pick one. Looks well. This is going to download it from Hugging Face. I'm just expand the advanced options and look for the max model length, and I'm going to bump this up for the context window, and leave everything else as the defaults, but there's settings for max loras. Um all of these configuration options get passed as um as flags to the uh vLLM serve. And I'm going to spin it up as an endpoint here.

This might take a minute since or two since this is the very I just created it. I've got to initialize my workers. Let's check out. So, the default configuration here is it's going to deploy on some H100s, and A100s are the backup here. I have my pricing. This is fraction of a cent per second. Um like I mentioned before that this is only going to be charged for a while the worker is actually running and handling a request. Max workers is where I can bump this up if I want to have my workload scale up up to 15 workers at a time and I can set um some active workers, ones that I want always to be on that I don't want um the container to ever spin down. And I can save that.

Okay, so how do I how does one interact with the serverless endpoint? Um this is just an API uh HTTP endpoint right here. Um we provision this endpoint for you. You can send requests to this. Your customers can send requests to this. If I just hit run and I'm going to add a few Let's Which which should we ask the LLM today? Say one. Okay. How did I'm I'm American, so how did Bid Then get its name? I don't know.

>> [clears throat]
>> Um okay, well these requests are queued. Let me check on our workers. Okay. We have a handful that are in initializing. Um this is the container's being created. That's the model being downloaded. Um getting ready and the ones that are running, they've already finished. These are probably going to be the ones who are going to pick up those requests that we just added. I've got telemetry about um it's blank right now, but the number of requests, execution time, delay time, so you have observability into how your endpoints are operating.

>> [snorts]
>> And let's see. Okay, it's already done.
>> [snorts]
>> I got a request back and it sat in the queue for about 41 seconds. Um that's going to be a little bit longer than all of the subsequent requests because of some of the cold start time that I talked about, like downloading the model, um initializing the first container, but um execution time only about 1 and 1/2 seconds, so yeah, that was probably less than 5 minutes to get started and get something deployed um on serverless from a hub listing.

Does anyone have any questions? This is is a very short and sweet intro. Um we have another session later today at 4:00 um and that one is going to be focused on our Python um SDK and that one is going to be completely via the terminal. Um and I'm going to walk you through how I can spin up uh and deploy my code on my code as a remote remote function onto a GPU um and uh deploy in the end and make it like a production-ready endpoint here as well. Okay. But that's all I got for today, so yeah, thanks thanks for coming.
</details>