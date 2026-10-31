---
author: Latent Space
date: '2026-07-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UwxxlTNPjWo
speaker: Latent Space
tags:
  - agent-experience
  - speculative-decoding
  - ai-infrastructure
  - serverless-gpu
  - sandboxing
title: 从开发体验到智能体体验：Modal CTO 解析 AI 时代的基础设施进化
summary: Modal 联合创始人兼 CTO Akshat Bubna 探讨了 AI 时代基础设施的演变。Modal 将团队重心从“开发者体验 (DX)”转向“智能体体验 (AX)”，推出了专为 AI 智能体设计的沙箱、GPU 状态快照等原生原语，并开源了投机采样系统 DFlash，以应对现代 AI 应用高弹性、高并发的重计算需求。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Modal
  - Ona
  - Midjourney
  - OpenAI
  - Anthropic
  - Databricks
  - Ramp
  - Cognition
products_models:
  - DFlash
  - vLLM
  - SGLang
media_books: []
status: evergreen
---
### 庆祝Series C

**主持人**: 在开始今天的节目之前，我有一条简短的消息要送给听众朋友们。谢谢大家。如果你们没有选择点击订阅并收听我们的内容，我们绝对无法为您呈现您所喜爱的 AI 工程、科学和娱乐内容。我们几乎每天都会收到赞助商的接洽。但幸运的是，有足够多的听众订阅了我们，使我们能够在没有广告的情况下保持这一项目的可持续发展，我们希望保持这种状态。不过，我有一件事想拜托大家。您可以做的最强大、完全免费的一件事就是点击那个订阅按钮。这是我唯一会拜托大家的事，这对我以及每周努力为您呈现 **Latent Space** 的团队来说意味着一切。如果您订阅了，我向您保证，我们绝不会停止努力，一定会把节目做得更好。现在，让我们进入正题。我们今天邀请到了 **Modal** 的联合创始人兼 CTO **Akshat**，以及 **Vibhu**。恭喜你们完成了 **Series C** 融资。

<details>
<summary>Original English</summary>

**Host**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you, and it means absolutely everything to me and my team that works so hard to bring the Latent Space to you each and every week. If you do it, I promise you, we'll never stop working to make the show even better. Now, let's get into it. We're here with Akshat of Modal, CTO of Modal, together with Vibhu. Congrats on your Series C.

</details>

**Akshat**: 谢谢。

<details>
<summary>Original English</summary>

**Akshat**: Thank you.

</details>

**主持人**: 昨天你们的派对简直太棒了。

<details>
<summary>Original English</summary>

**Host**: Uh your party yesterday was amazing.

</details>

**Akshat**: 是的。

<details>
<summary>Original English</summary>

**Akshat**: Yeah.

</details>

**主持人**: 各种照片和周边都很棒。

<details>
<summary>Original English</summary>

**Host**: All the photos and all the swag.

</details>

**Akshat**: 确实，我们布置了很多艺术装置，看到我们的产品被放在基座上，旁边放着像罗丹那样的雕塑，感觉挺有意思的。

<details>
<summary>Original English</summary>

**Akshat**: We we had a bunch of art installations which uh is kind of fun seeing like our products on pedestals next to like Rodan.

</details>

### Modal的起源

**主持人**: 非常棒。当你们刚创立这家公司时，它还不是一家 GPU 推理公司。或许在你脑海中是，但带我们回到最初的起源故事吧。

<details>
<summary>Original English</summary>

**Host**: Very nice. Very nice. Um when you started it was not the GPU inference company. I mean maybe it was in your mind. take us back to the origin story.

</details>

**Akshat**: 我最初是通过一位投资者认识了 CEO **Erik**。当时 Erik 已经在思考构建一种新型的运行时。他思考的出发点是：为什么工作流编排产品（比如 Airflow 等）那么难用？因为你必须在 **Kubernetes** 上运行它们。Kubernetes 很难管理，它不是为了应对突发计算和自定义镜像而设计的，而且开发者体验（DX）极其糟糕。

我为新听众补充一些背景。我们在两年前采访过 Erik，当时讲了更多关于他之前在 Spotify 时的故事。我第一次听说 Erik 是在 Data Council，因为他做了一个关于他们所做的无服务器容器栈（Serverless Container Stack）的演讲。那是我第一次觉得“天哪，我需要非常认真地对待 Modal”，但当时还是不太清楚：我自己搞数据管道真的需要这些吗？

是的，我们最初的想法是，如果能构建一个更好的运行时，这本身就是一个非常有用的原语。很多问题可以通过 Serverless 函数解决，比如你可以做 ETL、任务队列，以及各种突发性处理，而事实证明每个公司都有这种需求。但我们也把这看作是一个基础原语，可以在此基础上构建一整套非常高效的产品。

当时数据工程可能是第一个，但我们那时也考虑到了推理，只不过更偏向传统的推理，比如计算机视觉、运行 XGBoost 之类的。其实我们在 **ChatGPT** 问世前一年就在产品中加入了 GPU。我们当时只是没觉得这会有多大不了。

<details>
<summary>Original English</summary>

**Akshat**: Uh I actually first met Eric who's the CEO through an investor and um back then Eric was already thinking about building uh a new kind of runtime and he he got there thinking through why are workflow orchestration products so hard to use? It's because you have to run them on Kubernetes. Kubernetes is hard to manage. It's not built for burstiness and um custom images and has a terrible developer experience. And I I'll inject for for listeners uh who are new. Uh we interviewed Eric two years ago and there's a bit more of the story there from Spotify and all those things. And I I actually came across Eric through data council because he he did that talk on the the sort of serverless container stack that that you guys did which was like that was my first like okay I need to take models very seriously moment but it was still very unclear like do I actually need all this for just my data pipelines? Yeah, I mean initially what we were thinking about was if we build a better runtime. It's a very useful primitive in itself. It's um there's a lot of things that um get solved by serverless functions like you can do uh ETL stuff, you can do job queues, you can do all this like bursty processing which it turns out every company had needs for. Um but then we also were thinking about this as like um this is a primitive that we can build a whole collection of products on um which are very virt. So perhaps data engineering would have been the first one but we were thinking about inference back then it was more classical inference like computer vision stuff and running XGBoost and whatnot but we we added GPUs to the product a year before Chat GPT came out. We just didn't think it would be that big of a deal.

</details>

**主持人**: 是的，就像是“顺便加个 A100”。那么在早期有什么核心的关键问题真正促使了你们去构建它？

<details>
<summary>Original English</summary>

**Host**: Yeah. Just like add A100. Was there any like early key problem that really sparked off why you built it?

</details>

**Akshat**: 主要还是因为当时市面上没有任何工具是为优秀的开发体验而设计的。而且当时有一个大趋势，那就是我们看到的很多工作负载都非常偏向于重计算（Compute-heavy）。它们需要大量的资源，因此需要能够快速扩缩容，而 Kubernetes 主要是为缓慢扩展和 Web 服务器这类场景设计的。此外，在运行这些工作负载的环境上也存在更多的特化需求。比如有时它们需要硬件加速器，有时需要完全不同的系统镜像，这是我们在许多公司看到的普遍问题。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, primarily it's just um none of the tooling that that was out there was built for um one a really great developer experience and also there's a general trend of um a lot of the workloads that we were seeing were very we this is I wish there's a better word for it but compute heavy like they need um um one like need a lot more resources so you need to burst up and down a lot versus like Kubernetes designed for like slow scaling and uh more for like web server use cases And also there's just a lot more specialization in like what kinds of environments these workloads run in. Like we sometimes they need accelerators, sometimes need different kinds of images and this is just like a consistent thing that we saw across a lot of companies. That would be the the next step.

</details>

**主持人**: 对，这很棒。我不确定这在早期故事中占了多大比重，但我之前在 Temporal 时写过一篇关于软件定义基础设施（Software-Defined Infrastructure）的文章。

<details>
<summary>Original English</summary>

**Host**: Yeah. Be be nice. I don't know how much this factored into the early story, but I wrote a post when I was at Temporal about infrastructure software defined infrastructure or something like that.

</details>

**Akshat**: 自我配置的运行时（Self-provisioning runtime）。对。我甚至自己都不记得写过这篇了，然后你把它放在了你们的官网上。

<details>
<summary>Original English</summary>

**Akshat**: The self-provisioning self. Yeah. Yeah. I couldn't even remember my own post and then you put me on the landing page.

</details>

**主持人**: 是的，我们非常喜欢这个术语，所以我们就直接拿来用了。

<details>
<summary>Original English</summary>

**Host**: Yeah, we we really like uh the term and and so we we stole it

</details>

**Akshat**: 因为你有这种直觉，即所有的基础设施声明都可以通过装饰器（Decorators）与代码存放在一起，对吧？这是最开始故事的关键部分，还是仅仅是一个 DX 层？这确实非常关键，因为我们真的不希望人们花大把的时间去写 YAML 文件。把配置压缩到代码中可以让整个系统更有表现力和动态性，所以这一直是极其核心的一部分。

<details>
<summary>Original English</summary>

**Akshat**: because you had the insight that everything can just be in decorators next collocated with the code, right? Was that a big part of the original story or was just like a DX layer? that that that was uh really important because we really didn't want people to spend um so much time uh writing YAML and it seemed like you could really condense the surface area of what you're doing uh put it in code so you can actually operate on it just like you can operate in other code like build stuff that's more expressive and dynamic and so yeah that that was always a very important part

</details>

**主持人**: 那当时的反对意见可能是“这是一个领域特定语言（DSL），是闭源的，我被绑定到 Modal 上了”。

<details>
<summary>Original English</summary>

**Host**: then the push back is this is a DSL it's you're close source uh I am locked in to modal.

</details>

**Akshat**: 实际上我们从没有因为这个收到过什么反对意见。因为 Modal 最棒的地方在于你可以带上你原有的任何代码。诚然，我们的装饰器是一种用于指定硬件和扩缩容的配置层 DSL，但代码本身仍然是属于你自己的。即便我们现在在做推理，这也是我们故事中非常重要的一环。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, we we never really got push back for that because the nice thing about modal is you can bring whatever code you have and sure the DSL is that the sort of configuration layer for uh what hardware you're using, how you're scaling things up, but you still own the code. Uh and that's that's been an important um part of our story even as we do inference now.

</details>

### 转向智能体体验

**主持人**: 你觉得现在还有多少保留了下来？在今天构建应用时，开发体验依然重要，但我感觉因为智能体（Agents）和辅助编码工具的发展，很多东西都在发生改变，可以通过智能体直接调用工具实现。现在有许多“智能体原生”的原语，这与人类自己写代码很不一样，对吧？

<details>
<summary>Original English</summary>

**Host**: Yeah. How much of it do you think still stays the same today? Like if you were to build something today, DevX obviously very important, but I feel like you know a lot of this has kind of been changed with just hook it up to an agent, have cloud code, have codeex implement a tool. Um there's very agent native primitives that are kind of different than if I'm doing this myself, right?

</details>

**Akshat**: 我们实际上已经把我们的 SDK 团队的思考重心从开发者体验（DX）转向了**智能体体验（Agent Experience, AX）**。我们认为，DX 的各种优势同样适用于 AX。我们为什么非要让智能体去阅读成百上千行的 Kubernetes 文件并编写不带类型的 YAML，而只需要让它在代码中修改几行装饰器配置，就能获得一个自我配置的运行时，并直接看到修改的实时效果？从我们与客户的交流来看，他们确实发现与操作其他基础设施平台相比，智能体在 Modal 上运行要快得多。

<details>
<summary>Original English</summary>

**Akshat**: We've actually changed our SDK team to think about agent experience instead of uh developer experience. And and we think that the same benefits that apply for DX also actually apply for AX, which is why would you have an agent read through hundreds of Kubernetes files and like write YAML that's not even typed when it can basically make a couple changes in a decorator and it gets this sort of self-provisioning runtime of uh being able to see its changes live in action. Um yeah, it just seems from from the customers we talked to um they actually find the model is way faster used for agents versus operating on a different substrate.

</details>

**主持人**: 是的，因为你把基础设施需求直接和运行它的代码存放在了一起。

<details>
<summary>Original English</summary>

**Host**: Yeah. Because like you you again you collocate the infrastructure requirements to the code that runs it.

</details>

**Akshat**: 现在反向的论调是，因为没人会看代码了，所以代码怎么写也无所谓了。

<details>
<summary>Original English</summary>

**Akshat**: Well, the the the negative thesis now is that nobody's looking at their code anymore. So there's no point.

</details>

**主持人**: 是的，人们不看代码了。但有一点我们依然发现非常重要，那就是**可观测性（Observability）**。你的仪表盘有多好用？当然，我们把很多功能推到了命令行工具（CLI）上，以便智能体自己去做分析排查，但你仍然需要人类去理解发生了什么并做出决策。我觉得这比看代码本身还要重要。

<details>
<summary>Original English</summary>

**Host**: Yeah. I mean people aren't looking at code. Uh one thing we actually still see is is really important is observability. Yeah, how good is your dashboard? And of course, like we have um we push a lot of it to the CLI so the agents can do their own investigation, but you still need humans to go interpret what's going on and uh you know, make judgment calls and whatnot. Uh and that's I feel like um maybe more important now than looking at the code itself.

</details>

**Akshat**: 是的，因为你可以把代码当成黑盒，通过观察它产生的行为来促使代码的变更。

<details>
<summary>Original English</summary>

**Akshat**: Yes. because like you know it's you can try to treat the code as a black box and then use sort of see the observable action that comes out of it and then just prompt a change.

</details>

### AI应用云平台

**主持人**: 对。而且我觉得保持克制、不去过度细分领域，而是保持通用性并发布一个新原语是很难得的。当人们问你们是做什么的，你们会说“我也不知道，我们啥都能做，沙箱、GPU、各种东西”。如果你要向别人介绍 Modal 是什么，你会怎么回答？

<details>
<summary>Original English</summary>

**Host**: Yeah. So I I think actually think it it takes a bit of restraint to not specialize to say I want to ship a new primitive and then just just be general purpose. People ask you what are you for you're like I don't know we can do this we can do that. Uh yeah, I'd be curious to say you know like okay if if we were to ask you like what is modal for even at a high level there's a lot you guys do sandboxes GPUs uh everything how do you answer

</details>

**Akshat**: Modal 是一个专为 **AI 应用**从头构建基础原语的云平台。目前它涵盖了推理、训练、批处理和沙箱工作负载，而且我们还在构建更多的功能。

<details>
<summary>Original English</summary>

**Akshat**: modal is a cloud platform that's built for uh where we've built the primitives from scratch for AI applications uh and right now it basically covers um inference training batch crossing uh and sandbox workloads but we're building a lot more and

</details>

**主持人**: 我注意到你没有提到 Web 服务器，所以对于那些“永远在线”的大规模 Kubernetes 类型应用来说，依然有生存空间。

<details>
<summary>Original English</summary>

**Host**: I noticed you didn't say web server so there there is still a role for like the always on large scale Kubernetes type of things.

</details>

**Akshat**: 是的，没错。我们并不想和 Render 这类服务竞争。对我们来说，分水岭在于我们需要应对那些需要特化计算和需要频繁伸缩的工作负载，它们的形态完全不同。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, absolutely. We're not trying to compete with the renders uh of of the world. Uh because yeah, we think the differentiator for us is the um our other workloads that need specialized compute, need to scale up and down a lot. Um yeah, they're shaped differently.

</details>

### 沙箱与弹性伸缩

**主持人**: 你们很多产品是和初创公司一起迭代构建的，他们创新速度极快。比如你们在 Series C 博客里提到的客户：**Cognition**、**Decagon**、**Ramp** 等等。他们一直在和你们共同创新，而这不是 AWS 能直接为他们做的。

<details>
<summary>Original English</summary>

**Host**: I think you're building a lot of it alongside the startups, right? They're innovating quite a bit. Um even in your like latest blog post like even even in the series see the the customers that you mentioned here uh the cognitions decagons ramps and whatnot they're they're innovating with you right and that's not something AWS is doing directly with

</details>

**Akshat**: 是的，我们是一个小团队，动作可以非常快。我们的工程师会直接和客户的开发人员在一起干活。

<details>
<summary>Original English</summary>

**Akshat**: yeah absolutely I think I mean this is again classic we're small team we can move really fast uh our engineers are working with their customers and figuring out

</details>

**主持人**: 我在 Cognition 的第一周，走进去看到有人穿着 Modal 的 T 恤，我还纳闷“你在这干嘛呢？”他们说：“噢，我直接在这里驻场开发。”

<details>
<summary>Original English</summary>

**Host**: my first week at cognition I walked in there was someone wearing a moto shirt I was like what are you doing here. They're like, "Yeah, I just I I am embedded inside of COG."

</details>

**Akshat**: 哈哈，那应该是 Payton。我们派他过去是因为其他沟通方式的延迟太高了。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, I think that was Payton. We we sent him over because uh the latency of communication was too high otherwise.

</details>

**主持人**: 懂了，分布式物理节点，必须放一个实体在客户旁边。我以前也有过类似的个人体验。三年前我开发小助手时，需要一些突发算力，就试了试 Modal，体验特别舒服。据说我当时还出现在了你们董事会的分析报告里？

<details>
<summary>Original English</summary>

**Host**: Um yeah, you know, distributed node. You have to put you have to place one in collocate. So actually, so I had a direct personal experience, right? So I worked on small developer 3 years ago. Uh it was inspired by cloud one. I think you onboarded me at some point like just before and I was like oh like I need some bursty compute like I was just going to try using modto and it was it was pretty pleasant experience. Uh apparently I showed up in the board meeting like the analytics.

</details>

**Akshat**: 是的，你在 Hacker News 上火了之后，给我们带来了很大的流量高峰。你当时是将 Modal 函数用于后台任务运行，那是一个很好的使用场景。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, you blew up on hackernews and and we got a big traffic spike. Uh I actually I think the way you you use small developer was modal functions for for running stuff. uh which which was like that was a good use case.

</details>

**主持人**: 对，那对我来说就是早期的 Cognition。如果我当时坚持做下去，技术路线图就是那样的。

<details>
<summary>Original English</summary>

**Host**: Yeah, that was so to me that was protocognition, right?

</details>

**Akshat**: 那时你离这个目标已经非常近了。

<details>
<summary>Original English</summary>

**Akshat**: If only I had like stuck to it like that that was like if you just like draw the tech tree out was like yeah like probably this will happen.

</details>

**主持人**: 确实很接近。

<details>
<summary>Original English</summary>

**Host**: Yeah, like he was so close to

</details>

**Akshat**: 那个时候的有趣故事是，在 2023 年，我们遇到很多客户需要类似**沙箱（Sandboxing）**的功能。我们在 2023 年 5 月就开发了沙箱，当时人们甚至还没意识到这会成为一个刚需。我们发布的第一个示例，就是把你的小助手放在循环里，让智能体进行自我迭代。

<details>
<summary>Original English</summary>

**Akshat**: um but but the funny story there is at the same time uh we were talking to a bunch of customers who needed something like sandboxing. This is like 2023. Uh so we need a new API right after that. Yeah, like we built sandboxes in May of 2023 before anyone was even knew this was going to be a thing. And the first example we published was uh we took small developer and put in a loop uh so the agent can iterate on itself.

</details>

**主持人**: 当时模型还没强大到能很好地处理这些，对吧？

<details>
<summary>Original English</summary>

**Host**: Uh loops are hard these days. Loops in when was this 2023? Yeah, small chick. Yeah, it's like mid 2023. I mean so I mean those sort of obviously for listeners like the problem was the models are not built for any of this, right? like you you're trying to like they're not postrained to understand like you know looping and like self correction and and tool calling was there but like also not that great.

</details>

**Akshat**: 我不记得那个例子里有没有用工具调用，但模型在迭代 10 次之后基本上就会发散，无法输出有意义的东西。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, I don't remember if you use tool calling in this one but yeah the models would just diverge after like 10 iterations and not produce anything meaningful.

</details>

**主持人**: 但现在回看，这一切就非常显而易见。那确实是你们沙箱旅程的开始，虽然它直到去年才真正爆发。

<details>
<summary>Original English</summary>

**Host**: Yeah, but like then so I mean okay like now talking to myself three years ago the answer is collect all the failures, build benchmark and then collect all the you know examples build the oral environment sell it for like $10 billion to Meta uh and then and then also train a model and then sell that for $60 billion to to Elon and this is a money machine like it's like it's actually not that hard. I mean, it's hard to have that kind of inherent conviction that this stuff will get that much better in retrospect. It's so [ __ ] obvious. Like, fair enough. Like, what else were we doing back then? I don't know. Um, anyway. Yeah. So, so, so I mean, so that that was the start of your sandboxing journey, right? Uh, I feel like it didn't blow up blow up until like last year.

</details>

**Akshat**: 确实。

<details>
<summary>Original English</summary>

**Akshat**: Yeah.

</details>

**主持人**: 所以中间经历了两年的沉寂期。

<details>
<summary>Original English</summary>

**Host**: So, there was like a couple years of quietness.

</details>

**Akshat**: 没错。

<details>
<summary>Original English</summary>

**Akshat**: Exactly. Yeah.

</details>

**主持人**: 这真的是一个被低估的产品价值。我和我的一位朋友在黑客松认识，他当时坚持要运行一个不想部署在别处的轻量模型，他就说“Modal 可以瞬间拉起一个 GPU 沙箱，扔个 Hugging Face 链接就能搞定”。这种瞬间部署、即用即走的价值在今天依然是我们需要的。

<details>
<summary>Original English</summary>

**Host**: very underrated product value like um my experience with modto Charles before he had joined Moto met this guy at a hackathon and he really insisted we wanted to run some small model you know not hosted anywhere and he's like ah there's this cool company modal they'll like spin up a GPU sandbox so we can throw it on there it'll take a hugging face link and you know like there's so much value just right there right like instant hosting spin it up spin it down it'll stay cold but you know we run the demo a few days later it'll come back up and All this stuff in retrospect like is still what we needed like today.

</details>

### 弹性推理与快照

**Akshat**: 没错，今天仍然需要。当然，工作负载的形态已经发生了很大变化。我们现在要为客户应对更大规模的生产级挑战。这里的问题不是从 0 到 1 的冷启动，而是如何在特定区域以极快的速度弹性地从 1000 个 GPU 扩展到 1500 个 GPU。它们在本质上是相同的问题。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, I mean it's still needed today. Obviously workload shapes have changed a lot as um we we run stuff for people with really massive production scale and uh there it's it's not about scaling from 0 to one but it's how do we scale really elastically uh from like,000 to 1500 GPUs very quickly in in a given region. It's the same shaped problem.

</details>

**主持人**: 比如 Cursor Composer 他们每隔几个小时就要对模型运行强化学习（RL），你们为此推出了 RL 推理沙箱（RL Inference Gym）。对于这种工作负载，需要每小时动态扩缩数千个 GPU，这确实是极度需要弹性扩展的例子。

<details>
<summary>Original English</summary>

**Host**: Okay. So you look at say cursor composer right they had a we'll do RL on a model every couple hours um you guys have a whole version of RL inference gym and whatnot when you look at workloads like that you're basically doing train runs where you need to scale up scale down every hour thousands of GPUs right um that's the example for we do need it right

</details>

**Akshat**: 没错。我们的核心用例是**弹性推理（Elastic Inference）**，最开始找到产品市场契合度（PMF）的是自定义模型的推理。所以我们早期其实避开了通用大语言模型（LLM）赛道，专注于服务音频的 Suno、视频的 Runway、机器人公司以及在其他地方训练模型并在 Modal 部署的计算生物学公司。

随着流量起伏，Modal 就像是部署和弹性扩缩的超级黑盒。我们看到所有这些公司的流量模式都极其不可预测。可能某天做个发布，流量就突然暴涨。而且他们不只部署一个模型，往往需要在不同地区部署许多不同的模型。这就让自动扩缩容变得非常困难，因为你必须在特定区域内进行扩缩，而且各个地区的时区偏移会导致峰值错开。

<details>
<summary>Original English</summary>

**Akshat**: yeah well actually I'll I'll take a step back and um maybe talk about like how how people use model today uh because our Our biggest use case actually is uh elastic inference and the thing we first found product market fit uh with was inference for custom models. So we kind of stayed away from the LM space. Uh and we were serving companies like Sunumo for audio, runway for video, robotics, uh comp bio companies that train their own model elsewhere. But modal is the best blackbox that for deployment um scaling to however many GPS you need as your traffic pattern changes. And we saw all of them actually um like have a very unpredict predict predictable uh traffic pattern. It's like dial it's um some days like the company will do launch and you know they'll need like u way more and it's not just one model that they deploy they all these companies deploy uh lots of different models in different regions and so the autoscaling problem becomes even harder because then you have to scale within a certain region and those cycles sort of are offset so different times you need to scale up in different regions. So that's like our sort of

</details>

**主持人**: 这本身就是一个巨大的品类。有很多推理托管商像 Fireworks、BaseTen 等提供了这类语言模型推理服务。

<details>
<summary>Original English</summary>

**Host**: and that you know that that in and of itself is a huge category. There's a bunch of inference providers which you know provide this fireworks does this as a service together whatnot base 10 um that's kind of carved into its own niche for language models at least right now.

</details>

**Akshat**: 我们的专业优势集中在**自动扩缩容（Autoscaling）**上。我们发现并非所有的服务商都能真正做好弹性自动扩缩。在技术层面，我们在产品中集成了 **GPU 状态快照（GPU Snapshotting）**。你可以直接把 GPU 的状态（比如经过 PyTorch 编译后的模型状态）进行快照保存，这样下次冷启动的速度就会极快。

所以，不仅是推理需要高弹性，许多在强化学习（RL）中做 Rollouts 的按需训练同样非常需要这种弹性。除了智能体，大家也在运行大量的批处理任务。在训练开始前，很多公司需要数千个 GPU 来做数据编码之类的处理。这些任务的弹性比智能体要高得多，而 RL 训练更是弹性需求的巅峰。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, I mean the thing that we we have actually specialized in is the autoscaling aspect. uh because we we we found that it's not universally true that everyone else can autoscale and we've gone deeper into it on the tech side but we've incorporated GPU snapshotting into the product so you can actually uh take the GPU state uh like your torch compiler model snapshot it and next cold starts way faster and so going back to your question it's um that's why you need a lot of burstiness for inference but then people also do a lot of on demand training like for RL stuff your rollouts are bursty as you said people also do a lot of batch jobs. So we'll see uh a lot of companies uh before they have a training run, they'll need thousands of GPUs to run encoding or something like that. And I think those things are much more bursty than I agree that agents are are not that bursty. Uh sandboxes are uh except when you're doing RL. RL is insanely bursty.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 是的，当你在进行 Rollouts 时，你有时需要同时启动 100,000 个沙箱。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. Like when when you're doing uh rollouts uh you you sometimes need 100,000 sandboxes.

</details>

### 投机采样与DFlash

**主持人**: 我很好奇你有没有看到“持续学习（Continual Learning）”的早期苗头？比如我们的朋友 engram 最近宣布了在这方面的尝试，这似乎也是一种非常不一样的工作负载。

<details>
<summary>Original English</summary>

**Host**: Yeah. I'm curious if you've seen early sparks of continual learning. There's some people like our friends engram recently announced this. They're they're trying to do training. That also seems like a different workload, right? If you're doing training 24/7, per se, there's a very weird dynamic of how you're using GPUs between people and whatnot, but seems like something you guys would work for.

</details>

**Akshat**: 我们很幸运能和许多处于前沿的客户合作，其中有些客户确实在用我们的原语尝试做像持续学习这样非常有趣的事情。随着这套技术路线愈发成熟，如果更多人有这种需求，我们也会将其作为我们核心产品的一部分。现在我们正在静观其变。

<details>
<summary>Original English</summary>

**Akshat**: As you said, we're we're fortunate to work with a number of uh customers at the frontier and grab some of our customers uh and and they are taking the primitives we have um and trying to use them in very interesting ways like continue learning. It's possible as the stuff gets better some of that will be part of uh you know our offering as well if you know more people need it. Um but we're just waiting to see how all this shakes out.

</details>

**主持人**: 在沙箱之后，你们还加入了什么新的核心原语吗？

<details>
<summary>Original English</summary>

**Host**: Is there a primitive that you added after sandboxing that was the next step in the story?

</details>

**Akshat**: 我们一直在深入 LLM 推理领域。因为我们意识到，我们在多区域自动扩缩容方面的优势在别处是找不到的。过去我们唯一的短板是只做黑盒托管，没有切入模型层。但我们意识到，通过引入顶尖的人才，我们在模型性能优化上也能达到前沿水平。

我们一直在积极开源我们的工作。最近我们分享了 **DFlash**，这是一个基于块（Block-based）的投机采样器（Speculator），并且已经全部开源。通过在你的工作负载中使用开源的 DFlash，你可以获得与那些商业闭源推理服务商完全一致的优化性能。

<details>
<summary>Original English</summary>

**Akshat**: I guess we've been going much deeper into LM inference because we realize that some of the advantages we have with like autoscaling again especially in different regions and whatnot uh are um not present elsewhere. And and the place where we had a gap was we weren't uh working on the model layer itself like we were a black box and uh we realized that uh we actually can get to frontier level model performance um uh with you know by having great people who who work on uh all of this and uh we've actually been open sourcing a lot of our work uh in terms of um recently we um shared our work on Dlash which is a block based uh uh speculator and we've open sourced uh all of it. So um you can get by using open source v flash you can get the same performance as you would with one of the proprietary providers. And the next thing we're thinking about here

</details>

**主持人**: 这是一篇非常有意思的博客文章，你在文章中强调了投机解码（Speculative Decoding）能带来巨大的效率提升。

<details>
<summary>Original English</summary>

**Host**: I thought this was actually an interesting blog post as well right like uh I think in here you make a claim that you know not a claim just that how how effective speculative decoding really just gets you anything you want to point out from this around you know what people should know.

</details>

**Akshat**: 是的。要不要我先给听众简单科普一下什么是投机解码？

虽然我们之前聊过其他类似的方案，但那是两年前的事了。

我觉得讲一下也没坏处。

投机解码就是使用一个较小的模型（称为草稿模型或 Draft Model）提前预测后续的 Token，然后让大模型在一次前向传播中同时验证这些预测的 Token。它之所以更快，是因为当你逐个预测 Token 时，性能受限于 GPU 的**内存带宽（Memory Bandwidth）**。但如果你可以批量验证草稿模型的预测结果，就能极大地提高算力利用率，从而大幅加快速度。只要草稿模型的预测被接受的比例（称为接受长度 Accept Length）足够高，你就可以在大模型无损质量的前提下，获得数倍的推理速度提升。

很多时候大家在讨论怎么优化算子核心（Kernels），但优化底层算子往往只能带来百分之几的提升，而提高投机采样的接受长度则是直接带来 2 到 4 倍的乘法级提速。

<details>
<summary>Original English</summary>

**Akshat**: Uh yeah absolutely I mean the high level summaries um would it help to describe what speculative decoding is? Yes, I think like we so we've covered like ego and all this like hydra and all those things but it was like two years ago I think it doesn't hurt right the speculative decoding is you have a smaller model uh called a draft model predict tokens ahead of the bigger model and then you have the bigger model uh verify all of this all the tokens are predicted and the reason it's faster is if you're predicting uh one token at once you're kind of u bound by memory bandwidth but if you can batch the verification of uh the draft model uh then you're much more efficient using compute and it's faster and as long as your draft model is producing a lot of tokens that can get accepted which is called the accept length you can get u speed up that's multiple times of um you know the original model speed uh and that's what we highlight here it's um like people talk a lot about we made these kernels faster and whatnot but improving kernel only give you like a few percentage points of improvement and increasing accept length literally is a multiplicative decrease in like 2 to 4x without much head-on performance.

</details>

**主持人**: 没错。但是你要同时运行第二个模型，所以这可能会消耗更多算力。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. I think it maybe I mean you you are running a second model, right? So maybe it's like more expensive in in the compute but

</details>

**Akshat**: 在输出的质量上是没有损失的。因为大模型作为检验者，绝不会接受任何有偏差的 Token，所以输出结果在数学上与大模型直接输出完全一致，甚至更好。

<details>
<summary>Original English</summary>

**Akshat**: I meant quality but yeah I mean I think so there's no drop in quality performance because you're always you're never accepting a token that better or same. Exactly. Yeah.

</details>

### 自动端点与控制

**主持人**: 明白。

<details>
<summary>Original English</summary>

**Host**: Right. Yeah.

</details>

**Akshat**: 我们一直在推进 DFlash 这个项目。除了开源这部分工作，我们下一步是帮助人们训练自己的草稿模型和自定义模型。传统上，这需要大量的全职员工（FTE）和部署工程师去协助客户。我们推出**自动端点（Auto Endpoints）**就是希望将前沿的推理性能普及给每个人。

在自动端点中，你可以直接在 UI 或 CLI 中拉起一个推理端点，所有的 DFlash 投机采样优化已经完全内置且对你完全透明。我们提供全部的底层代码，你可以自主运行。如果需要深度定制，你也可以直接导出成完整的 Modal 配置自己修改。它不是一个黑盒。下一步，当你的数据分布发生变化时，我们还将支持自动迭代和优化你的草稿模型。

<details>
<summary>Original English</summary>

**Akshat**: And so we've been working a bunch on Dlash which is a block based speculator. Uh so it's um uh instead of predicting uh one token at a time it's predicting a block and we we've been open sourcing our work with it. The the next thing for us here is for for helping people train speculators and custom models. Uh it's it's something that traditionally is very FTE driven support deployed engineer driven like you work with customers and help them do that. And our vision for this is why we launched auto endpoints is we want to make frontier level performance available to everyone. And so uh we mentioned this announcement we kind of teased it. The next thing we're we're launching is basically as you run an auto endpoint uh we we shadowed traffic and do you want to explain auto endpoints are high level? Yeah. Yeah. So um this is I guess going back to your modal is is you touch the code but uh sometimes people actually don't want to touch the code and they want to get started with an endpoint that works and has all the great performance and uh scalability that modal has. So we've made that easier with basically way to create an endpoint from our UI from the CLI um that has all of our optimizations that we talked about uh like the deflash stuff already baked in and there's full transparency. So we give you the code uh you can go run it yourself and if you want you can eject out into the full modal experience uh which we see as people get sophisticated they they do want to tweak the models uh they want to fine-tune stuff you you can still do all of that it's it's not a black box and yeah the next thing as we tease later in the post is how do we give you value even beyond this in terms of having your draft models evolve as your data distribution evolves again without having to talk to a person and um yeah

</details>

**主持人**: 假设我拿一个开源的模型，比如 Qwen，用 SGLang 或 vLLM 部署在同等算力的其他服务器上。使用你们的平台，除了弹性伸缩，最核心的差异化优势是什么？

<details>
<summary>Original English</summary>

**Host**: I guess just to kind of understand it directly I mean you know obviously you you have the GPUs you have an endpoint that's compatible you serve open model if someone was to do this themselves what's the delta that you guys provide so you do a lot of open- source great work on effective inference um how does it compare to say I take the same model GLM 5.2 2 FB8 take offtheshelf inference engine VLM SG lang um you know get compute of similar capacity similar cost what's the kind of delta that plugging into something this like this offers outside of the benefit of you know scaling

</details>

**Akshat**: 我们非常注重与开源社区的合作。我们与 **SGLang** 团队紧密协作，并将我们的很多优化直接贡献回了上游开源项目。我们的优势在于我们的团队在底层性能优化上拥有极深的积累。如果你有任何非标的、社区还没有解决的性能瓶颈，我们团队能够以最快的速度帮你攻关解决。

另外，正如我们前面提到的，我们的服务是极其弹性的，支持真正的“缩容至零（Scale to Zero）”。在实际生产中，这种极速弹性扩缩的能力往往比你在别处找几个卡直接跑代码要重要得多。

<details>
<summary>Original English</summary>

**Akshat**: it's kind of interesting because we we've taken the approach of open sourcing our contributions and upstreaming them we work closely with the SG lang team we we actually want the improvements that our team uh comes up with to be uh there and openour or for others to use even outside of modal. The benefit to us is we have a team that has significant expertise in terms of if you do have something that is not there our team can help you get that performance uh first. Um the the other thing is with these endpoints we are way more elastic as you said uh than uh anyone else and you have true scaling to zero uh you have true uh burstiness and in practice that matters a lot more to people than just finding uh the GPU and uh running model code on

</details>

**主持人**: 是的，很多事情往往是知易行难。对于普通人来说，要权衡和调整这一长串的软硬件配置和优化组合，难度实在太高了。

<details>
<summary>Original English</summary>

**Host**: yeah and I I will say it's actually not that straightforward to just like what I said is easier said than done, right? Um, it's I think still for the average person still hard to just gut check using different there's there's quite a bit of combinations you can make there. Um, the trade-offs aren't really known at face value.

</details>

**Akshat**: 没错，即便是排除了扩缩容，运行高吞吐、低延迟的生产级推理也是一个非常困难的工程问题。如何控制尾部延迟（Tail Latency），如何保证请求的可靠送达，这其中有非常多的工程细节。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, I mean it's it's not just that. I think it's it's that running production grade inference is a hard infer problem. uh even if you subtract out the autoscaling is uh controlling things like tail latency and um making sure every uh request is delivered at least once and whatnot.

</details>

### GPU与CPU协处理器

**主持人**: 没错。随着你们越来越像一个全功能的云平台，你们也在涉足别人的领地。有什么是你们绝对不做的吗？

<details>
<summary>Original English</summary>

**Host**: There's a lot of innovation that you can do here. I think uh it's very interesting that you're starting to encroach on like as you become a full cloud, you're starting to encroach on other people's turf.

</details>

**Akshat**: 嗯。

<details>
<summary>Original English</summary>

**Akshat**: Mhm.

</details>

**主持人**: 你们的分界线在哪里？

<details>
<summary>Original English</summary>

**Host**: What will you not do?

</details>

**Akshat**: 我们的原则是跟随用户的实际需求。目前我们聚焦在模型生命周期和智能体生命周期上。包括从数据准备、模型训练，到推理部署，再到智能体所需的沙箱和持久化存储等一系列周边配套。

<details>
<summary>Original English</summary>

**Akshat**: Well, we want to follow our users and um make sure they uh they get like a platform that has everything that works well together. Uh so right now we're kind of focused on the model life cycle and the agent uh life cycle. Uh so both like going from data prep to training to inference and then also if I want to deploy a background agent let's say you know sandbox to persistent storage a whole bunch of other stuff.

</details>

**主持人**: 我们之前和做 OpenInspect 的 Cole 聊过，他们也是在 Modal 上运行的。

<details>
<summary>Original English</summary>

**Host**: We talked to Cole uh who did uh open inspect. Yeah.

</details>

**Akshat**: 是的，Ramp 的 Inspect 也是跑在 Modal 上。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. And obviously real inspect also is on modal.

</details>

**主持人**: 这是一个很好的后台智能体（Background Agent）的成功范例。他们能够利用 Modal 的 Snapshot 和弹性缩容，构建出了极具响应力且十分可靠的应用。

<details>
<summary>Original English</summary>

**Host**: Yeah. So ramp inspect was was a a great example of a background agent that was really successful because they uh were able to use some of the primitives like snapshotting and fast scaling to this has something that feels really reactive and uh and works well.

</details>

**Akshat**: 对，Rahul（Ramp 的新任 CTO）在这方面做得很棒。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, Rahul. It was really really fun.

</details>

**主持人**: 哈哈，Rahul。这非常有意思。我最近一直在思考的一点是，在今年的 NVIDIA GTC 大会上，Jensen 提到了一个“推理拐点（Inference Inflection）”。在以前的机器学习任务中，GPU 与 CPU 的配比可能是 8:1。但在现在的智能体工作负载中，由于智能体经常会被 CPU 密集型的任务（比如运行代码、分析文件）阻塞，GPU 和 CPU 之间的限制因素在来回摇摆，比例几乎接近 1:1。所以，你必须将它们紧密地协同定位（Collocate）在一起。

<details>
<summary>Original English</summary>

**Host**: Um yeah, I mean you know I I think uh all very bullish like you know one of my reflections was also I did not originally cuz obviously when I met you guys you weren't that much in the GPU game and now you're all about uh inference and one of the points that I hinged on for Jensen's keynote at GTC this year was what we're calling like the inference inflection right that let's say in AI workloads or machine learning workloads it used to be like let's call 8:1 GPU to CPU and now it's more like 1:1 which is like a interesting like because of how much agents basically are blocked or call out to to CPU heavy stuff the actual like limiting factor like swings back and forth from GPU to CPU a lot more than it used to be all GPU and then occasional CPU GPU CPU and now it's like just constantly and you just have to collocate everything.

</details>

### 多云可靠性与时延

**Akshat**: 没错，这也是 Modal 吸引大家的一个地方。我们建立了一个跨越了 **17 个不同云服务商**的庞大算力池。我们非常擅长在全球不同的物理云基础设施上高效调度和运行任务。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. And and that's one of the things that um actually again we see is uh something appealing about modal which is we've built this capacity pool that spans uh 17 cloud providers. So we're very good at running on various kinds of cloud capacity across the world.

</details>

**主持人**: 也就是说你们没有自己的物理数据中心。

<details>
<summary>Original English</summary>

**Host**: You don't have your own data centers.

</details>

**Akshat**: 是的，我们不建数据中心。我们只是在全球各种 NeoClouds（新型算力云）和算力服务商的基础设施上调度运行。

<details>
<summary>Original English</summary>

**Akshat**: We don't have our own data centers. We we just run across a lot of NeoClouds and providers question.

</details>

**主持人**: 明白。那在什么时候，买卡的性价比会超过租用 NeoClouds？

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. You're running the math and you're like what's the cut over point where you're like

</details>

**Akshat**: 这是一个很好的问题。我们一直觉得我们的核心壁垒在软件层。保持资产轻量化可以让我们集中精力把软件做好，从而迭代得极快。到目前为止，这种策略运作得非常好，因为现在建设数据中心的资金太充沛了，有成百上千的人在建数据中心。我们只需要和他们合作，做好我们最擅长的事情。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. It's a good question. I mean part of it is we we see our differentiator in in the software layer and um being capital light and focusing on the software helps us move really fast. Uh so far it's worked out well because there are so many other people building data centers that we're able to work effectively with them and again focus on what makes us uh special.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 接入 17 个算力商还能让你触及很多本地化的算力节点。

<details>
<summary>Original English</summary>

**Akshat**: 17 gets you into like the local providers sometimes like

</details>

**主持人**: 哪个是最有意思的？其实新型算力云的丰富程度远超大家想象。但它们的可靠性可能参差不齐。因此，我们投入了巨大的精力在 Modal 上层构建了一套极强的**可靠性容错层（Reliability Layer）**。即便底层的 GPU 掉线或者遭遇总线故障，用户的任务也不会受到任何影响，这让我们可以极大地盘活那些对于单体用户来说不可用的非稳态算力资源。

<details>
<summary>Original English</summary>

**Host**: the who's the most interesting one. There actually a lot more Neo clouds than you expect and they all have various degrees of um various levels of reliability and uh that's why something we've invested a lot of time in is actually uh building our own reliability layer on top. Uh so if the GPU falls off the bus or something happens we uh user workloads are not affected and that that actually lets us use a lot more capacity than um you know you as a user would be able to.

</details>

**Akshat**: 这绝对是一个超级杀手锏。现在大家都知道了 Modal 在这个层面上起到的“多云桥梁”作用。这涉及到我们刚才谈到的协同定位（Collocation）。很多时候，客户来找我们是因为他们需要特定物理地理位置的 GPU 或 CPU，比如锁定在欧洲或美国。

<details>
<summary>Original English</summary>

**Akshat**: It's a useful thing to have because like now everyone knows like what layer you are and like you you sort of optimize for being the super cloud of all clouds. Yeah, that's that's uh that's the idea. Uh and so I guess when you mentioned collocation that's that's another interesting thing where um one thing we've seen is people come to us when they want uh very specifically located uh CPUs or GPUs uh like they want

</details>

**主持人**: 比如锁定在欧盟境内。

<details>
<summary>Original English</summary>

**Host**: oh the pin it in like EU

</details>

**Akshat**: 没错。

<details>
<summary>Original English</summary>

**Akshat**: exactly or EU US

</details>

**主持人**: 是因为数据合规还是延迟问题？

<details>
<summary>Original English</summary>

**Host**: data locality thing or performance or what

</details>

**Akshat**: 两者都有。如果他们在 Modal 上运行智能体沙箱，他们会希望沙箱和他们现有的数据库部署在极其贴近的同一物理网络内。

<details>
<summary>Original English</summary>

**Akshat**: it's either data locality or latency. Yeah, like you want your they're running sandboxes in modal. They want them to be right next to

</details>

**主持人**: 这确实在所有这些系统设计中都至关重要。你们相当于无意中（也许是刻意为之）为智能体构建了一个完美的原生运行底座。而且很有意思的是，智能体的发展路线最终都绕不过文件系统、CPU 等这些最传统的基础资源。

<details>
<summary>Original English</summary>

**Host**: that's a you know that is important in in in all those things and so like you've kind of accidentally I don't know if it's accident but like you've built the perfect primitive for agents to to express themselves and then you know like it's almost very funny how every extra development just involves more file system just involves more CPU

</details>

**Akshat**: 是的，就是这样。我们正在把计算、存储和网络这三个最核心的基石，以 AI 智能体时代所需要的全新形态重新组装。

<details>
<summary>Original English</summary>

**Akshat**: uh just like the things that you already have. I don't know much about if there's any like networking usages that are interesting, but you've also done some good work on networking. Yeah, I mean that's exactly right. Like we we're sort of just taking compute, storage, and networking and building stuff on that layer uh for again the stuff people need.

</details>

### 网络与Sidecar沙箱

**主持人**: 你们在网络层面也有很多出色的工作。

<details>
<summary>Original English</summary>

**Host**: We we see a few interesting network things coming up. Um one is people actually want sandboxes. Uh so we have a

</details>

**Akshat**: 是的，比如 Docker Compose 这类的多容器协同。

<details>
<summary>Original English</summary>

**Akshat**: for like a Docker cluster type thing. Sorry. Uh Docker swarm. [ __ ] So what is it called? Compose. Compose type thing.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 我们的沙箱现在支持 **Sidecar 模式**。沙箱在底层其实是一个容器组（类似于 Kubernetes 的 Pod），你可以同时在一个沙箱内运行多个容器。这在网络安全和网络控制上非常有用。例如，很多做 RL 或安全审计的客户需要对沙箱的所有外发网络请求（Egress）进行拦截和细粒度监控，注入访问凭证或限制特定域名的访问。为此我们不得不自己去写了很多底层的网络控制逻辑。

<details>
<summary>Original English</summary>

**Akshat**: So actually if you want docker compose uh our sandboxes now support uh this thing called sidecar. So you can a sandbox is actually a pod of containers and you can run multiple containers in uh the sandbox. Uh also useful because uh going back to networking people want a lot of control over um outbound networking from a sandbox. might want to run man in the middle proxy for like maybe logging stuff for RL or um controlling how egress can happen to a domain injecting credentials. Uh and yeah, so we've kind of had to build a lot of that stuff ourselves.

</details>

**主持人**: 明白。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 另外，我们还看到越来越多的人需要让分布在不同物理节点上的沙箱能够直接互通。我们之前因为别的原因支持了这个特性。

<details>
<summary>Original English</summary>

**Akshat**: Uh but then also sometimes people actually want um sandboxes spanning multiple nodes to talk to each other. Uh which is an emerging thing we're seeing. We have support for that for for a different reason and yeah we'll see if that becomes safe

</details>

**主持人**: 比如直接通过公开端口进行 MTLS 通信？

<details>
<summary>Original English</summary>

**Host**: like just a open socket it's a this is directly like NTLS

</details>

**Akshat**: 我们支持这种隧道模式，你可以在沙箱里暴露出一个端口，然后将其连接到公网。或者你也可以在上面加一层 HTTP 的鉴权。

但我们还有一个没有公开宣传过的底层原语——**I6PN**。这是一种基于 **IPv6** 的虚拟局域网（Overlay Network）。在同一个 Modal 空间下，开启了 I6PN 的容器可以通过特定的 IPv6 私网地址互相寻址和直接通信。这为容器提供了完全隔离的安全私有网络。

我们最初构建 I6PN 是为了我们的分布式训练产品服务。如果你在函数上加一个装饰器，你就可以拉起一个 GPU 集群，它们之间拥有 RDMA 高速网络连接，可以运行完全 serverless 的分布式训练任务。而 I6PN 就是用来处理这个集群底层的元数据寻址和控制通信的。但我们发现有很多客户在用它做其他事情。

<details>
<summary>Original English</summary>

**Akshat**: we do support that which is you can uh expose a tunnel inside a sandbox and then you can either expose public internet or it can be um mine you can add like a HTTP uh odd layer above it but we have this thing called I6PN which we haven't talked about uh which is this like overlay network using IPv6 addresses. Uh so if modal containers uh within the same workspace uh when this enabled can actually address each other using this private IP v6 address uh and no one else can uh it's like sort of private networking uh for containers. We actually built it because we needed it as a primitive for our distributed training product. Uh so we have this feature which is you can add a decorator to a function and you get a cluster of GPUs uh and they have RDA networking uh so you can run a dist training job uh that's truly serverless uh and we need the overlay network for that but then we've seen that people are using it for other reasons and I'm kind of intrigued to see

</details>

**主持人**: 让开发者拿到基本原语，然后看他们能玩出什么花样，对吧？

<details>
<summary>Original English</summary>

**Host**: yeah what would people do with it build primitives and let people figure it out right

</details>

**Akshat**: 哈哈，是的。很多用法连我们的文档里都没写，开发者自己摸索出来就在生产中用起来了。

<details>
<summary>Original English</summary>

**Akshat**: they're like they read the docs we pick let me use that for something that you never intended This is literally not even in our docs page. People somehow found it and they're using it.

</details>

### RDMA与多节点训练

**主持人**: 你们把 RDMA 和传统 TCP 的性能区别处理得非常好。在 RL 训练的大规模数据吞吐下，这种网络传输速度的变化对效率的影响是革命性的。

<details>
<summary>Original English</summary>

**Host**: Uh I mean the way you portrayed it with like RDMA versus TCP like very well laid out, but just the transfer speed change at scale for RL like Yeah, you have it you have it built in. I'm sure someone found it found it to be a lot more efficient before you actually made a thing out of it, right?

</details>

**Akshat**: 对。需要说明的是，I6PN 这个虚拟网本身其实是运行在 TCP 层面的。因为在建立 RDMA 高速互联网络之前，节点之间需要通过 TCP 虚拟网络先完成密钥和握手信息的交换（Key Exchange）。但开发者在这个过程中意外发现了我们暴露的 TCP 通信能力。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. And and not to split hairs, I guess the the overlay network actually is the TCP overlay network. Uh the reason we have that is you need that to do the key exchange for RDMA before you set up the RDMA network on top of that. But then people found the the TCP part.

</details>

**主持人**: 这真的解答了我的一个大疑惑。我之前为 World's Fair 评审了 2200 多份学术提交。其中有一篇来自 John Ousterhout 的论文（他是非常著名的高校教授，写过很多经典的系统设计书），那篇论文研究的正是 RDMA 在大模型推理中的应用。我当时还在想，一个传统的操作系统大牛怎么会突然开始关注 RDMA，现在一想完全合理。

<details>
<summary>Original English</summary>

**Host**: Can I tell you this is like a big aha moment for me because so I you know I reviewed 2,200 submissions for for the world's fair. Yeah. And then I got this from John Ousterhout who I don't know if do you know John Osterhalt by name. He published he's a well-known professor published a lot of interesting software design books and this is the talk he chose to submit it's on t it's on RDMA at imprint and I'm like you wouldn't think that this guy who is like kind of operating systems guy would care about RDMA I I mean it makes sense to me because cloud right yeah

</details>

**Akshat**: 确实。在大模型和强化学习中，如何高效地调度和传输 KV Cache、如何快速把训练好的模型权重从训练卡同步到推理卡，这背后涉及极高的工程自由度。这在本质上就是一个经典的高性能系统设计问题——关于内存搬运和任务调度。

<details>
<summary>Original English</summary>

**Akshat**: like like the way you move around your KV cache and how efficiently you can do it how efficiently you move um your weights from your training GPUs to your inference GPUs and RL is there's a lot of degrees of freedom and it is basically a systems problem of moving memory around scheduling

</details>

**主持人**: 这显示出我对底层网络的理解还很浅。这和 WireGuard 属于同一个领域的范畴吗？

<details>
<summary>Original English</summary>

**Host**: this shows you how primitive my understanding of networking stuff is is this like the domain of wire guard as well

</details>

**Akshat**: 不太一样，但它们在逻辑结构上是紧邻的。

<details>
<summary>Original English</summary>

**Akshat**: not quite so adjacent um so explain everything sure sure uh how do we move memory around GPUs

</details>

**主持人**: 噢，抱歉，我们刚才已经跳到 GPU 内存寻址了。我是想问前几分钟你提到的虚拟 IPv6 网络寻址，它听起来类似于 VPN。

<details>
<summary>Original English</summary>

**Host**: oh sorry yeah that is memory sorry I I was talking more and maybe I was talking like 5 minutes back about the the private IPv6 uh addressing that you've set up

</details>

**Akshat**: 是的，它在逻辑上确实很像 VPN。从这个角度看，它和 WireGuard 解决的是相似的网络问题。

<details>
<summary>Original English</summary>

**Akshat**: is it's basically a VPN. Yeah, it's sort of like a VPN and yeah, WireGuard is is uh Yeah, you're right. It is it is um yeah, you already moved on to topics

</details>

**主持人**: 哈哈，看来我已经落后你们的讨论进度了。

<details>
<summary>Original English</summary>

**Host**: yeah, you already moved on to topics

</details>

**Akshat**: 主要的区别在于 WireGuard 会对所有数据流进行强加密，而我们的内网为了追求极致性能是没有加密的。它是纯 TCP 连接，我们通过在 Linux 内核中使用 **eBPF** 程序，根据容器的权限白名单动态拦截或放行连接。在以前，这需要像 Service Mesh 那样拉起一个繁重的 Sidecar 容器，但现在我们可以通过 eBPF 在内核级别无感处理。

<details>
<summary>Original English</summary>

**Akshat**: a similar in the same space wire guard is uh encrypted and and this is uh you don't need encryption. Yes, it's not encrypted. Uh that's the main difference. This is TCP and we have EBPF programs that will reject or allow the u the TCP connection based on whether you're allowed to do it. Used to involve a fullsize car but now you have EBPF in the Linux kernel.

</details>

**主持人**: 明白。这让我想到了我之前对“分布式训练”的一个质疑：现在人们花大价钱买最顶级的交换机和光纤去连 GPU，但网络连接依然是最大的瓶颈。你们的网络带宽足够支撑分布式训练吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. I don't know if this is a natural follow on to the topic of like my skepticism on distributed training is that well like people spend a lot of money on like cables to hook up GPUs and even that is not like fast enough and that's the bottleneck. Is your networking fast enough?

</details>

**Akshat**: 如果你指的是跨地域、跨公网的完全分布式训练（比如像 Decentralized Training 那样），网络确实无法支撑，那是带宽的极限。但如果是在单数据中心内的多机多卡训练，Modal 的 GPU 节点之间配置了极高规格的 RDMA 网络通道（例如 Mellanox 无限带宽技术 InfiniBand），可以直接绕过操作系统的 TCP 协议栈，实现极速的内存对拷。我们内部的数据中心网络达到了 **3 Terabits/s** 的内部互联带宽，完全满足业界多节点训练的标准。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. So I guess you're talking about sort of fully distributed training like a dialoc or something which is like cross that would be yes that's the extreme. Yeah. you're kind of in the middle and then other people would have like the Melanox cables up in in like their actual data center. when you run multeno training on on modal uh the RDMA uh I think Melanox uh is or infiniban is like a uh is you also use RDMA uh but basically it's a way to bypass the TCP networking stack and um transfer uh stuff much faster uh between one node uh to the other and and we we have I think like 3 terb per second uh internal networking which is the standard that's needed

</details>

**主持人**: 原来如此，看来我之前误解了底层的网络架构。这真的非常令人赞叹，意味着你们成功地将 Modal 简便易用的产品哲学延伸到了分布式训练集群上。

<details>
<summary>Original English</summary>

**Host**: okay so I misunderstood what part of the stack of TCP. Okay. Yeah. I mean, very impressive work. So, effectively you're you're extending sort of like the modal philosophy to the the trading cluster like Yeah.

</details>

**Akshat**: 没错。但我们并不打算去承接超大规模的基座模型预训练（Pre-training）任务。我们设计多节点分布式训练的出发点是为了支持中小规模的**后训练（Post-training）**微调。比如很多团队需要针对具体垂直业务，对中等尺寸的 Qwen 模型进行对齐微调以提升推理精度，这在 Modal 上是完美的契合点。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. And we're not going for obviously like large scale pre-training runs. Uh the thing that we've built multiode training for is uh we see a lot of u smaller scale post-training. uh like uh people are post training like mediumsiz quen models uh so they can uh get higher quality on inference uh this is a perfect fit uh for something like that.

</details>

### 自动化研究智能体

**主持人**: 这确实符合我的直觉。很多前沿实验室在做后训练的各种探索分支时，都需要这种弹性，最后再把效果好的模型合并回去。

<details>
<summary>Original English</summary>

**Host**: Yeah, that is my impression of how a lot of these labs explore branches in post training and then eventually merge whatever they find in

</details>

**Akshat**: 另一个典型用例是，即使实验室里有固定的独占 GPU 集群，研究员们依然要频繁运行很多小型的实验分支，弹性分配资源能成倍提升他们的效率。这实际上也是目前 AI 科学家和自动化研究（Auto Research）面临的最大瓶颈——你需要快速给智能体分配闲置的 GPU。我们之前发过一篇关于在 Modal 上运行 Auto Research 的技术博客，Modal 被证明是此类场景绝佳的运行底座。

<details>
<summary>Original English</summary>

**Akshat**: yeah the the other use case we've seen for mult training is even if you have a big cluster your researchers is still doing small runs and yes having elasticity there matters a lot more like this is actually like the current limiting factor for auto research which is like you you basically need to give your model some GPUs We have a blog post on auto research and modal is uh yeah like uh turns out to be a pretty good substrate for that.

</details>

**主持人**: 在我的印象中，目前的“自动化研究”很多还停留在学术比赛阶段（Science Fair），真正用于严肃生产的人应该不多吧？

<details>
<summary>Original English</summary>

**Host**: So my impression is auto research means many things like if anything coins right now still science fair right like not not not actually like I don't know how many people actually doing this. Yeah

</details>

**Akshat**: 我之前也这么觉得。

<details>
<summary>Original English</summary>

**Akshat**: I taught the same thing.

</details>

**主持人**: 哈哈，看来你最有发言权。

<details>
<summary>Original English</summary>

**Host**: Yeah you would know

</details>

**Akshat**: 但实际上，我们内部的推理优化团队和分布式训练团队已经在高频使用这类自动化流程了。我们内部有一个叫 `auto-inference` 的私有库。我们把原本需要工程专家（FTE）去手动调优性能的工作完全写成了自动化管道：智能体自己会拉起一整套实验网格进行参数搜索，甚至自动调用 NVIDIA Nsight Profiler 来定位性能瓶颈并自动调整代码配置。它能全自动地测试从 H200 到 B200 各种硬件上的配置表现，并最终给出最优的方案。这套系统在实际使用中效果出奇得好。

<details>
<summary>Original English</summary>

**Akshat**: we like our internal both training and inference teams actually use this sort of the general shape of this quite a bit. uh like we have this one internal repo called auto inference which is essentially we've automated our own FTE efforts using uh this harness which is um the agent will just spin up a sweep of different things. It'll even run like um Nvidia inside profiler and it'll like tweak configs and it'll arrive the right thing. Uh it'll change your GPUs from H200 to B200 and actually works really well.

</details>

### 智能体基础设施

**主持人**: 太酷了。我非常喜欢你们的“现场开发工程师”（FDE）具有极强的硬核技术背景，这和别家偏销售性质的客户服务很不一样。

<details>
<summary>Original English</summary>

**Host**: Nice. So, by the way, I enjoy that your FDE is so technical that you have to do these things. It's very different from FD from other people.

</details>

**Akshat**: 确实。我们团队里的 FDE 实际上就是应用推理研究员（Applied Inference Researchers）或应用训练研究员。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. Yeah. For our FDA team is uh essentially they're like applied inference researchers or applied training researchers.

</details>

**主持人**: 曾经有人和我说，这类工程师不仅要懂技术，还得懂销售。他们需要承担销售指标吗？还是主要负责售后？

<details>
<summary>Original English</summary>

**Host**: Someone told me like they have to be able to build but they also have to be able to sell. Do they have to sell or are they like they're good. This is like post sale type of thing.

</details>

**Akshat**: 确实需要具备与客户高频高效沟通的能力，但他们不需要背负任何销售性质的 KPI。我们会为他们配备专门的解决方案架构师（Solutions Architects）来处理前期的销售接入工作。

<details>
<summary>Original English</summary>

**Akshat**: It does. Being able to talk to a customer and engage effectively with them matters a lot. the same thing, you know, but it's it's not really a sort of sales uh thing. We we pair them with we have solutions architects as well that are more on the pre-sales side.

</details>

**主持人**: 好的，让我们在“自动化研究”这个话题上多花点时间。这是我今年关注的核心焦点之一。这套技术的未来在哪里？现在有很多人在研究通过强化来提升模型能力，这比传统的调参方式要抽象得多。我们应该把它看作是比传统训练高一个维度的抽象，还是更像是一种由 AI 驱动的超级超参数搜索（Hyperparameter Search）？

<details>
<summary>Original English</summary>

**Host**: Okay, let let's spend a bit more time on auto research. This is a big focus for me for for for this year. Where does this go? You know, like um have have people explored enough like you know there's all these beautiful charts of like improve improve then it sort of level off a bit and then you find the next thing. Is this basically sort of one abstraction up from normal training? Is that how we think about it or do you think about it differently like model level training versus basically like AIdriven hyperparameter search?

</details>

**主持人**: 有些人也叫它“神经架构搜索”（Neural Architecture Search, NAS），对吧？

<details>
<summary>Original English</summary>

**Host**: Uh some some people call it like neural architecture search or whatever, right? Like

</details>

**Akshat**: 是的。但我目前看到的实际应用中，还没有人能在底层的模型神经网络架构层面做自动搜索。大多数还是参数的微调，但这是一种融入了模型直觉的超参数搜索。所以它比你用传统的启发式规则跑随机搜索要高效得多。这本质上是在思考如何把算力投资分配在最容易获得边际效益的地方。如果你愿意在这里投入无限的预算，让几万只智能体去随机尝试，理论上最终总能撞出一部莎士比亚名著。

<details>
<summary>Original English</summary>

**Akshat**: yeah, I mean I so the the stuff I've seen people do with it is nowhere on the architecture level. It's pretty much tweaking parameters, but it's it's basically a hyperparameter sweep that's guided by some sort of model intuition. So it's like much more efficient than um whatever other sweeper you would have. Uh yeah, I mean, you know, it's just it's just a question of where you want to spend your computer, you know, right? Cuz yeah, you can just throw infinite amounts of money on this and somehow you'll bang on Shakespeare, you know.

</details>

**主持人**: 哈哈，打字机上的无限猴子。这对于 Modal 来说显然是一件大好事，因为这意味着智能体在自发地拉起更多的智能体，自发地配置和消耗更多的算力基础设施。另外，现在的 LLM 生成 Modal 配置代码的表现怎么样？你们有做过专门的微调吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Internet monkey. Uh yeah, I mean so like very good for modal uh and I think it's also very important that agents can spin up other agents. They can spin up their own infrastructure like very like very good for you. How good are LM at generating modal code? Like you know like the benefit of existing prel is that you are in the data.

</details>

**Akshat**: 表现好得令人吃惊。在 Claude 4 之前，很多模型在一次性（One-shot）生成 Modal 配置代码时还会掉链子。但现在最新一代的模型基本上都能开箱即用、一次写对。我们内部正在开发一个名为 `modal-bench` 的基准测试集，专门用来测试和收集那些目前大模型还无法直接搞定的高难度场景。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, they're they're actually surprisingly good. Uh I think like pre-Cloud 4 they were not and then now they're able to oneshot uh stuff out of the box. We're playing around with releasing like a modal bench for like the harder things uh that the LMS cannot do yet and and maybe

</details>

**主持人**: 能举个例子吗？比如模型在什么地方容易卡住？

<details>
<summary>Original English</summary>

**Host**: what's an example of that?

</details>

**Akshat**: 在缺乏特定技能提示和显式引导的前提下，智能体目前很难处理我们平台的高级可观测性。比如某个任务报错失败了，智能体很难自主地去关联和分析系统日志，并据此推断该如何修改对应的底层资源配置。这需要极强的推理和诊断逻辑。

<details>
<summary>Original English</summary>

**Akshat**: I think the the things that sometimes agents struggle with um without right guidance and a skill is um how to use the rest of our observability like how to something is failing like how do you look at the the logs and then update the right thing. It's sort of reasoning about that

</details>

**主持人**: 你不能直接给它外挂一个定制的技能模块（Skill）吗？

<details>
<summary>Original English</summary>

**Host**: yeah you can't just add a skill to it.

</details>

**Akshat**: 是的，所以我们现在推出了一个 Modal 官方的智能体技能库，这就是为什么我们要建 `modal-bench`。我们需要把大模型的这些短板找出来，然后有针对性地更新和微调我们的智能体开发技能。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. So, so we have a model skill now that which is kind of actually why we built this model bench. It's to find things like that so we can we we can address them in our tuning skill. Yeah.

</details>

### 算力策略与批处理

**主持人**: 明白。这真的很棒。在算力供应链方面，你们目前面临 GPU 资源的短缺吗？或者是 CPU 和内存的不足？

<details>
<summary>Original English</summary>

**Host**: No, no, I mean it's good. Uh are you facing any shortages? Uh you know like we talk a lot about GPU shortages but also CPU also memory.

</details>

**Akshat**: 我们的业务增长非常迅猛，所以我们必须在**主动容量规划（Proactive Capacity Planning）**上做得极其专业。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. We have had a lot of growth which means that uh there's a we've had to be much better about proactive capacity planning.

</details>

**主持人**: 我记得我们上次聊天时提过，这简直就是商学院高材生（MBA）梦寐以求的硬核规划岗位。

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh so we we have a which by the way like it's like an MBA's like dream job. It's like just planning this stuff. I think last time you and I talked about something maybe about this.

</details>

**Akshat**: 哈哈，没错。我们在 Modal 内部组建了一个非常专业的团队，我们称这个岗位为“**算力策略（Compute Strategy）**”。如果有听众对这个领域感兴趣，欢迎投递简历。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. I mean we have a really competent team of people that we call um the roles called comput strategy. Uh so yeah if anyone listening here wants to work on computer strategy. Yeah. Yeah.

</details>

**主持人**: 外界一般把这个岗位称作财务规划与分析（FP&A）吧？

<details>
<summary>Original English</summary>

**Host**: I like I mean the nor the normies call it FPNA or something.

</details>

**Akshat**: 它其实比传统的 FP&A 要复杂得多。这其中涉及大量极其有趣的量化金融问题。比如，一年期和三年期的预留算力（Reservations）应该按什么比例去配比？如何高精度地预测我们自己平台的弹性算力曲线？特别是由于我们底层的 GPU 类型和物理区域是可以灵活替换和套利的，我们需要对此建立复杂的数理模型。此外，你必须对全球半导体供应链的未来走向有极强的洞察和判断，并据此进行数十万乃至数百万美元的算力资产押注。

<details>
<summary>Original English</summary>

**Akshat**: Well it's more it's it's not FPNA. It's it's um there's a lot of interesting financial questions of like uh like what is the blend between one year and three year reservations? How do we forecast our own capacity? Uh how do we basically especially since our capacity is very funible across different GPU types and different regions. Uh like you basically have to model a lot of it. Uh and you also have to have an opinion on how the supply chain is going to evolve and then you have to like take bets uh based on that.

</details>

**主持人**: 没错，这简直是实体算力代币经济学（Tokenomics）。

<details>
<summary>Original English</summary>

**Host**: tokconomics.

</details>

**Akshat**: 是的，对于我们来说，算力调度业务的本质就是极其精细化的资产容量运营。这是我们拥有极佳的单元经济效益（Unit Economics）的原因，也让我们能为客户释放更多的性价比红利。比如，我们目前正在设计一个批处理层（Batch Tier）：如果客户对延迟不敏感，只需要在未来 24 小时内拿到结果，我们就能提供极便宜的折扣。因为我们掌控着底层的调度器（Scheduler）和全部软硬件技术栈，所以我们有足够的底层杠杆来实现这种套利调度。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, this is like probably not a real point, but uh I was trying to think about like what other industries I was trying to think about like you know we cannot be first to like these kinds of problems and what other industries have had this and I was like airlines with with fuel and like they have to hedge their fuel and like I think for a long time Southwest because they made like a hero fuel bet they like were like super low cost because compared to everyone else. Yeah, I had thought about that. We're having a fun time too, you know. Yeah, it's a lot of the the compute business in general uh for us is also about being very good about capacity management. That is how you have great unit economics uh but also over times how you can unlock more value for customers like um one of the things we're building now is like a way for customers to get um if they don't care about latency uh like get much cheaper pricing and they'll get results back in like next 24 hours or something uh like a batch tier essentially. Yeah. And those are levers we have because we control the whole stack and scheduling and whatnot to give people a sufficient

</details>

**主持人**: 确实。不过目前在业界，前沿大模型实验室提供的非即时批处理 API 的热度似乎没有大家预想的那么高。

<details>
<summary>Original English</summary>

**Host**: Yeah. I feel like they're not as popular like those like the the frontier labs have all those APIs. They're not as popular as they should be.

</details>

**Akshat**: 我们看到的对于批处理算力的强需求其实并不是来自 LLM 推理场景（虽然也有人拿它跑大规模模型评估和合成数据准备）。主要的需求来自很多传统的非 LLM 科技公司，比如做计算生物学（Computational Biology）的制药公司，他们需要跑极其庞大的冷数据模拟，且完全不在乎结果是下午出来还是明天半夜出来。

<details>
<summary>Original English</summary>

**Akshat**: The demand that we see for something like that is actually not for LMS. Uh although sometimes people want to run evals and do synthetic data prep in and there it makes sense. Okay. But it's uh from a lot of nonLM companies uh like people who are doing computational bio like they they haven't run really big batch jobs and they don't care about when they get it back.

</details>

**主持人**: 是的，这也关系到经典的图灵停机问题，即你需要确保这批后台任务最终能跑完。

<details>
<summary>Original English</summary>

**Host**: Yeah. And like they have a reasonable it's it's also like a cousin to the stopping problem of like will this finish in time.

</details>

**Akshat**: 没错。你可以在 SLA 协议里给客户一个时间边界的保证。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. You you can you can bound it like you can give people on it.

</details>

### 实时音视频路由

**主持人**: 懂了。现在 Modal 已经在前沿科技公司中树立了坚实的品牌知名度，大家对你们有了更高的期待。在最近的推理产品发布周（Inference Launch Week）之外，还有什么事情是大家需要知道的吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. I think what's what's interesting is like the the next phase of modal like what you know do people expect from you uh now that you're sort of established and you're like well-known computer player among all these leading companies. You had an inference launch week and we talked a little bit about the launches like what else what else should people know?

</details>

**Akshat**: 我们正在持续构建各种降低用户心智摩擦的底层原语。随着 LLM 推理走向平民化，成千上万家公司将开始后训练和微调他们自己的垂直大模型，并进行自主推理部署。我们正在为此设计最佳的产品路径：从我们的训练 Gym，到提供开箱即用、性能齐平商业推理服务的自动端点。

在其他垂直行业中，比如实时音视频处理，我们推出了**区域级智能路由（Regional Routing）**和故障自动切换机制。这使得客户能将视频流调度到离终端用户最近的 GPU 节点上，以实现低延迟的实时视频渲染和流媒体传输。

而在智能体生态中，我们正在和客户极其紧密地进行下一代原语的设计。除了安全沙箱和高并发持久文件系统之外，要在生产环境运行严肃的 AI 智能体，还有许多其他极其棘手的底层需求。我们正聚焦在这些新需求上。

<details>
<summary>Original English</summary>

**Akshat**: We are building primitives that make our our users lives much easier. So um I think for example with LM inference thousands more companies are going to post train their own models and deploy open source models for inference. So we're thinking a lot about what is the best product shape for that and uh that involves everything from our training gym to uh then uh endpoints that get frontier level performance. um you know again without having to talk to anyone it looks somewhat different on other verticals like uh we're also seeing a lot of real time uh audio video stuff in there um uh which is why like uh we're working on things like regional routing uh with with fallbacks so you can you can get sort of GPUs that are as close to users as possible uh so you you get like low latency for video streaming and and whatnot and then on the agent side it's Um, we're still sort of working very closely with our customers because stuff is changing so fast in terms of what they need and uh I think beyond sandboxes and persistent file systems uh there's a lot of other things people need from this agent stack as they build production agents. So yeah, we're thinking about those other things that fit in there.

</details>

**主持人**: 方便透露那些“其他底层需求”具体指什么吗？

<details>
<summary>Original English</summary>

**Host**: I want to ask what what the other things are.

</details>

**Akshat**: 哈哈，目前可能还不方便透露。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, probably share right now.

</details>

### 智能体系统与权限

**主持人**: 没关系。我平时也很关注传统云主机的三大核心要素：计算、存储、网络。在 AI 智能体时代，到底有什么东西发生了质的改变？

<details>
<summary>Original English</summary>

**Host**: I think okay so uh I do think a lot about the principal components of cloud and you do talk about comput storage networking because so far for me it's fine uh so far for I mean the first couple generations of cloud it's fine what's different qualitatively different about

</details>

**Akshat**: 确实。

<details>
<summary>Original English</summary>

**Akshat**: because so far for me it's fine

</details>

**主持人**: 智能体是否需要完全不同的权限模型？有些做 Cloud Code 的团队会采取比较激进的安全方案，比如直接通过指令白名单或者跨越沙箱边界去获取高权限。有时候他们会说“相信我的自主思考机制，我会帮你搞定这些系统调用”。这真的是未来的方向吗？还是说需要一种由大模型来调解和管理的全新操作系统权限机制？

<details>
<summary>Original English</summary>

**Host**: agents that you you need some new permission level like a lot of people you know obviously okay and I'll just kind of spew tokens at you until it like hopefully sparks something like the new level now is whatever cloud code does which is dangerously skip permissions or like allow list by command or like whatever, right? And and sometimes they're like, well, okay, well, we have like this adaptive thinking mode where like just just trust me, bro. I I will make the calls for you. Is that it? You know, like basically like sort of LM mediated permission.

</details>

**Akshat**: 在这个层面，你需要让它在沙箱里循环试错直到达成目标。

<details>
<summary>Original English</summary>

**Akshat**: Now you're looping it with a goal and flooding row.

</details>

**主持人**: 没错。对智能体进行基于 LLM 自主评估的权限管理，我其实非常怀疑。因为在沙箱隔离这个层面，你必须设立绝对不可逾越的物理安全边界，否则恶意的提示词注入能瞬间窃取或抹去所有资产。

<details>
<summary>Original English</summary>

**Host**: Yeah. I mean, I'm I'm skeptical of LM mediated permission for stuff that is at the sandbox level because you do want hard boundaries. Yeah, obviously someone can exfiltrate stuff.

</details>

**Akshat**: 是的，如果没有硬性的物理边界，系统会被轻易劫持。

<details>
<summary>Original English</summary>

**Akshat**: but like maybe maybe that's old school thinking. Maybe we're the dinosaurs. Maybe the AIOS or the LLM OS is really the kernel is a goddamn LM.

</details>

**主持人**: 但也许我们是保守的老古董了。在所谓的“AI 操作系统”里，也许底层的微内核本身就是由一个大语言模型组成的。

<details>
<summary>Original English</summary>

**Host**: Like it makes you feel uncomfortable, but that's what frosting the LM is. Like imagine a spherical cow perfect LLM,

</details>

**Akshat**: 哈哈。

<details>
<summary>Original English</summary>

**Akshat**: right?

</details>

**主持人**: 虽然听起来有些不切实际。

<details>
<summary>Original English</summary>

**Host**: Let it maybe

</details>

**Akshat**: 我愿意去探讨这个边界。

<details>
<summary>Original English</summary>

**Akshat**: I want to test the boundaries, right? Obviously, I don't believe that,

</details>

**主持人**: 尽管那目前还是非共识。

<details>
<summary>Original English</summary>

**Host**: but I want to see where I'm that's the non-conensus.

</details>

**Akshat**: 是的，我们的看法是，硬性的底层物理安全边界是不可妥协的底线，在此之上可以叠加一层基于 LLM 的自适应动态防护机制。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. I mean, I think you always need hard guard rails when you want um and you can pair those with softer guardrails, right? And ask a deal and mediate it.

</details>

### 托管智能体生态

**主持人**: 明白了。最后我们来聊聊 Modal 外部的行业生态。现在大家都在卷“托管智能体（Managed Agents）”。Gemini、OpenAI 和 Anthropic 都推出了自己的智能体托管方案。这对你们来说既是绝佳的流量来源，但也意味着他们在逐渐向你们的基础设施领地渗透。

<details>
<summary>Original English</summary>

**Host**: Yeah. I get end with a couple of your commentary on like the ecosystem outside of Moto. Manage agents. Everyone has one. Gemini OpenAI cloud uh very useful for you but also like it is their way of starting to edge into your space.

</details>

**Akshat**: 确实。

<details>
<summary>Original English</summary>

**Akshat**: Yeah.

</details>

**主持人**: 你们怎么看待这一格局变化？

<details>
<summary>Original English</summary>

**Host**: Uh what's going on?

</details>

**Akshat**: 我们非常高兴能和 Anthropic 以及其他头部大模型实验室开展合作。如果团队刚开始尝试构建智能体，调用大模型厂商的 API 接口是非常简单方便的起点。但随着业务逐步步入正轨、走向生产级别（比如 Ramp 就在 Modal 上运行他们的外部财务对账智能体），你就需要对智能体底层的系统原语拥有绝对的控制权。

比如智能体能接触到哪些关键敏感文件、如何快速对运行到一半的容器进行 Snapshot 并瞬间热恢复、如何精细化地设计出站网络防火墙，甚至在特定场景下智能体是否可以直接挂载独占的 GPU 资源。一旦你的需求复杂到这个层面，你就必须使用一个专业的、专为智能体量身定制的基础设施供应商，而这正是 Modal 致力于扮演的角色。我们对上面的智能体编排框架（Harness）没有特定偏好，不管你是在 Modal 之外的主机上调用 Modal 沙箱，还是直接把智能体编排系统跑在 Modal 容器内部，我们都完美支持。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. I mean, we're um very excited to partner with Anthropic and some of the other foundation labs belting is a great place to start if you're starting out building an agent and uh but but then when you get to um building something more production grade like you're a company that's like RAMP that's building their own uh RAM also runs their accounting agent on us. of their external facing agent. You need a lot more control over uh your compute primitive on things like um what sort of how do you process different files that the agent has access to and how do you snapshot and restore how do you control the networking um maybe you want GPUs when you get to that point you kind of want um specialized sandbox provider uh that gives you those things and that's the role that we are trying to play. We don't really have an opinion on the harness whether it runs in it's a cloud manage agent and you hook it up to modal sandbox you run the harness in modal sandbox. We'll see where people converge with that.

</details>

**主持人**: 你们对最近流行的一些“元框架”（Meta Harnesses）有什么看法吗？也就是在大模型 API 之外包了一层虚拟智能体云的框架。

<details>
<summary>Original English</summary>

**Host**: Yeah. Do you any opinions on like the meta harnesses? Um it just another layer on top of these things.

</details>

**Akshat**: 你是指像 OpenPipe 这样的产品吗？

<details>
<summary>Original English</summary>

**Akshat**: You mean like the open pie and

</details>

**主持人**: OpenPipe 是一个。另外 Vercel 之前也推出过一个类似的框架，还有 Databricks 最近发布的 Omnien。这些都属于这种位于中间件生态的元框架。

<details>
<summary>Original English</summary>

**Host**: open pie is one. Um I think Versell had one which I can't remember the name of right now. Fred shot had one. Uh and then uh to me most recently was data data bricks that had Omnien. All these are sort of meta artists like kind of pseudo agent cloud type things.

</details>

**Akshat**: 我个人还没有去深入上手体验过这些元框架。

<details>
<summary>Original English</summary>

**Akshat**: I personally have not played around with them and built into that.

</details>

### 智能体云平台未来

**主持人**: 只要这些上层框架在最终运行时能为 Modal 带来更多的基础设施计算消费，对你们来说就都是利好，对吧？

<details>
<summary>Original English</summary>

**Host**: I mean everything's bullish modal as long as it consumes more infra.

</details>

**Akshat**: 是的，这就是我们之所以坚定不移地深耕基础设施底座层的原因。这不仅是我们团队最核心的技术壁垒所在，也是一个极其困难且有着漫长演进周期的工程方向。

<details>
<summary>Original English</summary>

**Akshat**: That's why we're focusing on the infra layer. It's um somewhere where our um relative competences and um also it's a hard problem to solve.

</details>

**主持人**: 确实。从一个不那么资深但同样身处该领域的从业者角度来看，现在毫无疑问是系统基础设施（Infra）最激动人心的黄金时代。而在过去很长一段时间里，数据基础设施其实非常枯燥，甚至无人问津。比如几年前 Erik 在 Data Council 做演讲，大家看完就看完了，根本没有人在意“Modal 到底能秒级拉起多少个沙箱”。

<details>
<summary>Original English</summary>

**Host**: Yeah. I mean I will say like just generally reflecting on I don't know if you if if there's other topics on model but like just generally reflecting as an infra person not as intense as you but in that field this has like been the most exciting time in infra like it was boring actually for for for a while and you couldn't really get people excited about data infrastructure like Eric would get on data council everyone just watched the video and like it's like look at how many sandboxes I spin up and no one gave a crap.

</details>

**Akshat**: 是的。

<details>
<summary>Original English</summary>

**Akshat**: Yeah.

</details>

**主持人**: 但现在，所有人都开始无比关注基础设施的底座表现了。

<details>
<summary>Original English</summary>

**Host**: And like now everyone gives a crap.

</details>

**Akshat**: 没错。这是一个非常令人振奋的阶段，而这一切的底层驱动力其实就是 AI 时代庞大到有些超乎想象的计算和调度规模。

<details>
<summary>Original English</summary>

**Akshat**: That's true. It is a very exciting time and I think a lot of that's driven by just uh the amount of scale all of this stuff needs.

</details>

**主持人**: 你们当时对产品技术路线的诸多前瞻性决策，在今天马后炮地来看都是无比正确的。虽然退回三年前，我自己肯定是想不出这些演进路线的。

<details>
<summary>Original English</summary>

**Host**: I think like a lot of your initiatives, a lot of your like product directions make sense in retrospect, which is like the best kind, but I wouldn't necessarily have thought about it myself which

</details>

**Akshat**: 我们需要能看清未来迷雾的规划。确实，很多底层水面之下的巨大工程难度是外界看不到的。现在我们同时支持高并发批处理、语音流处理和多模态调度。

<details>
<summary>Original English</summary>

**Akshat**: we need we need the predictions, you know? I mean, I think there's a lot that you just don't even see, right? like you have the batch, you have the voice, you have the multimodel. Um but what what else you know

</details>

**主持人**: 在这之外，未来还会有什么新动向？或者你们认为基础设施会往哪个方向演进？

<details>
<summary>Original English</summary>

**Host**: what else is coming up for us or where do you see things going?

</details>

### 拓展非LLM场景

**Akshat**: 业界正在发生深刻的范式转移。除了大家每天都在热议的大语言模型（LLM）推理，我们也花了很多时间在服务生物医药、药物研发领域的计算生物学公司。很多不可思议的变化正在那里悄然发生。另外，很多机器人（Robotics）公司正在将具身智能机器部署到真实的生产环境中，并跑出了很好的闭环效果。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, I mean in general it's it's clear that there's a obviously there's a huge shift happening. I I think one thing that's not as obvious to people because LM inference gets talked about so much and is also we work a lot of companies that are doing things like drug discovery and computational bio like the chai discoveries world big things are probably going to happen there uh we work a lot of robotics companies that are actually putting robots in in like active deployments and getting good results out of them.

</details>

**主持人**: 那你们有提供私有化（On-premise）或物理隔离网络（Air-gapped）的 Modal 企业私有版吗？

<details>
<summary>Original English</summary>

**Host**: Is there air gap modal? Is there is there a version that is like onrem airgapped whatever?

</details>

**Akshat**: 不提供，我们自始至终只提供统一的多云托管云服务（Cloud-only）。

<details>
<summary>Original English</summary>

**Akshat**: No, we we cloud only. Yeah. Okay.

</details>

**主持人**: 懂了。正因为你们只聚焦在最核心的基础原语上，你们才能无缝承接来自其他前沿科技领域的计算需求，这实际上起到了很好的风险对冲作用，让你们的算力池不会因为 LLM 一家赛道的变化而产生过大的震荡。

<details>
<summary>Original English</summary>

**Host**: But yeah, I mean uh so what you're saying is like because you're focused on primitives and they're good primitives, you find use cases and all these kinds of things. Actually probably diversifies you a little bit away from LM all the time.

</details>

**Akshat**: 没错。我们的愿景绝不仅仅是做一家大模型 API 托管商。我们在官网上展示了大量的非 LLM 案例，比如大规模音频渲染、高通量生物图像分析等，这背后有着极深的业务多样性。

<details>
<summary>Original English</summary>

**Akshat**: Yeah, absolutely. We our our goal isn't to only serve the L1 fist market just on the website. The audio the bolts on the bio images. Yeah. I mean there's a lot here. There's QITTS customizing. Oh, chatter box.

</details>

**主持人**: 是的，我记得你们官网上还有定制化 Whisper 语音转录的经典教程。

<details>
<summary>Original English</summary>

**Host**: um you know there was a customizing whisper.

</details>

**Akshat**: 没错。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. Yeah.

</details>

### 核心应用层控制

**主持人**: 这让我想起了一个已经退场的竞争对手——Replicate。

<details>
<summary>Original English</summary>

**Host**: This screen reminds me of a fallen competitor. Uh which replicate.

</details>

**Akshat**: 确实。

<details>
<summary>Original English</summary>

**Akshat**: Mhm.

</details>

**主持人**: 你对他们的落幕有什么复盘吗？

<details>
<summary>Original English</summary>

**Host**: um what's your postmortem on what happened?

</details>

**Akshat**: 我们自始至终都在刻意避免将 Modal 包装成一个简单的“模型 API 提供商”。因为只提供模型的 API 接入，最终吸引和服务的很大一部分是缺乏黏性、且生存率极低的个人玩具/业余爱好者市场。我们一开始就致力于为真正的商业级产品公司提供基础设施底座，他们需要的是代码级别的完全灵活性，而不仅仅是一个调用 API 的 Token。

<details>
<summary>Original English</summary>

**Akshat**: This is one thing we've kind of stayed away from is providing an API for models because I think providing model APIs is some of it ends up serving like a really hobbyist market which is much less sticky and we've always wanted to build for companies that are building sort of products and need sort of more flexibility that's not just an API and

</details>

**主持人**: 你的意思是，虽然开发者可以在你们这里拉起一个模型并封装成 API 暴露出去，但你更鼓励他们将这一层逻辑作为他们后端庞大复杂系统的有机代码组件去运行。

<details>
<summary>Original English</summary>

**Host**: which you you can build an API for a model and this is clearly what it is but you can but you're saying you can wrap it into more fully functioning back end that you that you run.

</details>

**Akshat**: 没错。所以你看我们在官网上展示的每一个例子，都不是“在这里点击部署并获取一个 API 密钥”，我们展示的全部是完整的、可运行的 Python 代码。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. So, actually all of our examples, it's not that spin up this model, here's an API token, use it. They're actually all code.

</details>

**主持人**: 相当于给开发者提供优秀的脚手架代码。

<details>
<summary>Original English</summary>

**Host**: Okay. starter code.

</details>

**Akshat**: 对，然后你可以肆无忌惮地去修改代码的每一个细节，以完全贴合你们公司在制药或工业场景下的垂直诉求。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. But you can you can tweak it however you want. And if you're like a company building a product like computational bio, whatnot. Yeah.

</details>

**主持人**: 很多听众可能还在好奇：什么时候这套系统仅仅是一个简单的 API 包装（Wrapper），而什么时候它才真正升级成为了你口中所说的“硬核云产品”？在这之中，除了代码行数的膨胀，开发者在底层代码里加入的最核心的、不可替代的工程资产到底是什么？

<details>
<summary>Original English</summary>

**Host**: I guess I'm trying to tease out for listeners. Yeah. when does it stop becoming oh you're just an API call and you're just a wrapper on an API to becoming what you call a product right like what is that layer like what like you know obviously more lines of code but like beyond that what what is the substance that people add that qualifies it to be something more

</details>

**Akshat**: 我觉得这里面有一个典型的筛选效应。那些选择深入到系统代码级的公司，往往在构建极其差异化的核心壁垒。例如在早期，很多接入 Modal 的大语言模型推理团队，在自己写一套极其前沿的后训练对齐微调框架。比如 Ramp 团队在早期，甚至会为了支持他们特定的边缘任务而自己重新编写分词器（Tokenizer），并把这个分词器热替换插入到 LLaVA 模型的视觉推理链路中。

<details>
<summary>Original English</summary>

**Akshat**: I think there's a little bit of like a selection effect of like a lot of companies who do want to get deeper into that level are probably building something that's more differentiated and um I think Um an example is like we with LM and friends originally we worked with companies that were building their own post- training frameworks or they were uh ramp actually early in the day was training their own tokenizer and like swapping out the tokenizer in lava and whatnot. I'm not saying that's that was successful um in that case.

</details>

### 视频编辑智能体

**Akshat**: 另一个典型的例子是，像 **Midjourney** 这样的公司，他们不使用 Modal 进行大模型的预训练，但他们所有的生成推理任务完全是跑在 Modal 的底层算力网络上的。因为他们有着完全非标的、高度自定义的算法网络模型架构，这迫使他们必须在系统底层代码层面对资源调度进行精细的介入。这绝不是一个标准化大模型推理 API 可以承接的。

<details>
<summary>Original English</summary>

**Akshat**: A better example is like um like let's say u because Midjourney does not use for training Mikey on a pod. Yeah. But they they use modal for all their inference and that's because they have like a custom they have completely custom model architecture and that means that they have to be at the code level and tweak things that are not um you know it's an API.

</details>

**主持人**: 这确实很有说服力。最近前沿视频模型生成团队的 Ethan 做了一个预言：未来的视频生成技术，其核心上限将不再是单体视频生成模型的迭代，而是一个能自发编写代码、熟练调用各种图形工具的超级智能体编排网络。智能体能够自发地使用工具，帮人类生成一段 6 分钟甚至更长的电影级长片，而不是现在单次生成 10 秒钟的碎片短视频。

<details>
<summary>Original English</summary>

**Host**: It's interesting as well like we had Ethan most recently on the XAI Grog team make a prediction that actually like the next tier in videog model it's a better model or agent that orchestrates video models. language model backbone that can use tools and write code like yes I can make my sixcond video or my 10-second video from grock but actually I want my 6 minute video and I'm not going there through normal video gen

</details>

**Akshat**: 这非常有洞察力。我们目前在 GPU 沙箱上，确实开始看到一些初创团队在开发能够直接自主操作专业视频编辑软件（如 Adobe Premier/After Effects 等进行音视频混剪和后期处理）的智能体。

<details>
<summary>Original English</summary>

**Akshat**: yeah that's interesting I actually so we have GPU sandboxes and recently have seen a few companies doing sort of agents that do video manipulation or give it f like that's not you need to give it Adobe.

</details>

**主持人**: 这需要赋予它一整套运行环境。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 没错。我之前还没把这两者关联起来，没有意识到这会发展成一套完全自动化的视频电影级生产链路。在我的认知里，这还只是一些局部的视频剪辑工具。

<details>
<summary>Original English</summary>

**Akshat**: I hadn't put it together with like it would actually be a video production thing. Uh in in my mind, these things were going more towards editing and

</details>

**主持人**: 我平时经常会琢磨这些场景。

<details>
<summary>Original English</summary>

**Host**: Yeah. I think about this a lot obviously.

</details>

**Akshat**: 抱歉打断一下。

<details>
<summary>Original English</summary>

**Akshat**: Sorry.

</details>

**主持人**: Luma 公司的智能体正在朝这个方向探索，但也还只是小试牛刀。

<details>
<summary>Original English</summary>

**Host**: Um Luma Luma agent is a version of this for video production, but you know, it's a one-off.

</details>

### Ona与运行时沙箱

**主持人**: 我想听听你对最近其他业界新闻的看法。比如 **Gitpod**。虽然他们处于不尽相同的 CI/CD 和云端开发环境（CDE）市场，但他们在底层系统隔离的技术深度上是非常令人敬佩的。你之前有深度研究过他们吗？

<details>
<summary>Original English</summary>

**Host**: I was going to get your quick takes on uh on some other stuff that happens in recent news and see if you have anything interesting. GitPod very like somewhat like you know different market they they're in like sort of like the CI/CD market but actually technically very impressive. I don't know if you've like taken a real look at them.

</details>

**Akshat**: 研讨过。我们团队里的核心系统工程师经常和 Gitpod 的技术团队交流，他们是一群底层内功极其扎实的系统架构专家。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. Um we've um people on our team have talked to the Kipot team and they've they're technically very strong.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 我们在 Modal 内部其实也对云端 CI（持续集成）市场非常看好。因为在未来，随着自动写代码的智能体高频爆发，它们跑 CI 的频次和规模会呈指数级增长，而目前行业里的 CI 运行原语极其原始和低效。

<details>
<summary>Original English</summary>

**Akshat**: I I actually am we're very bullish at modal on the CI market as well because as there's more agents uh coding agents they're going to run a lot more CI and the primitives there can be much better.

</details>

**主持人**: 现在的 CI 构建过程中确实充斥着惊人的算力浪费。

<details>
<summary>Original English</summary>

**Host**: I think there's a lot of wasted CI.

</details>

**Akshat**: 没错。

<details>
<summary>Original English</summary>

**Akshat**: Yeah.

</details>

**主持人**: 在提升智能体 CI 构建效率这件事情上，最核心的杠杆点在哪里？

<details>
<summary>Original English</summary>

**Host**: So is it just like let's filter like what what is the highest order bit here in improving CI for agents?

</details>

**Akshat**: 目前传统的 CI 系统在拉起运行环境、拉取和编译依赖、以及依赖缓存的冷启动上浪费了绝大多数的时间。

虽然先进的增量编译系统能在一定程度上缓解这个问题，但如果基础设施直接提供底层的**内存快照与热恢复（Memory Snapshot & Restore）**原语，你就能在极短的毫秒级内直接从热态内存拉起 CI 容器，这能带来极其惊人的效率飞跃。

<details>
<summary>Original English</summary>

**Akshat**: Well, there there's a lot of wasted time in CI on like preparing your artifacts and like you know getting you to the basically um preparing your dependencies and whatnot and um obviously like build systems help with that but like if you have primitives that are like memory snapshot and restore can you just run CI more efficiently?

</details>

**主持人**: 噢，天哪，这确实太有想象空间了。这也是一种非常经典的按需突发计算（On-demand compute）。

<details>
<summary>Original English</summary>

**Host**: Oh oh okay okay interesting. Yeah. I mean another form of like you know on demand compute.

</details>

**Akshat**: 是的，它依赖完全相同的基础运行时原语架构。

<details>
<summary>Original English</summary>

**Akshat**: Yeah. Exactly.

</details>

**主持人**: 懂了。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Akshat**: 都是算力资源的最优调度。

<details>
<summary>Original English</summary>

**Akshat**: it it needs the same again platform.

</details>

**主持人**: 补充一个小背景，Gitpod 在最近正式宣布更名为了 **Ona**。我之前在 Cognition 内部也发出过预警，让他们必须高度警惕这家公司的技术底蕴，因为他们底层的系统设计能力极其拔尖。

但后来 Ona 团队被 OpenAI 整体并购了，我们应该很快就会看到 OpenAI 推出自己的 Codeex Cloud（智能体云环境）。Ona 团队在搭建网络隧道和隔离多租户安全容器边界上的技术积累，能帮助 OpenAI 让每一个智能体瞬间拥有完全独立的、极安全的私有运行云。

我想请教一下，你们和 Ona 的设计哲学有什么异同？在定位上，你觉得他们是不是在错误的时间切入了一个不那么性感的市场？而你们很幸运地直接撞上了智能体沙箱的爆发节点。

<details>
<summary>Original English</summary>

**Host**: Yeah. So so uh for those who don't know GitPod rebranded to owner. There was like there was this whole thing. I I got actually I I like sort of semi sounded the alarm at cognition. I was like you should take these guys seriously because they're infred very good. Yeah. uh and but you know then then they join OpenAI and uh presumably we'll we'll see codeex cloud from the owner team like which which I think would be very very strong to me like teams like that that can set up the networking and like the the secure boundaries for like and your like agents to have their own cloud each effectively is what you're doing kind of and I'm just trying to draw the analogy or or the differences if you have studied them like what is the philosophical difference you know

</details>

**Akshat**: 我觉得这里最微妙的区别在于，他们之前更偏向于“构建时沙箱（Build-time Sandboxes）”，而我们从一开始就在攻克“**运行时沙箱（Runtime Sandboxes）**”。随着智能体从“帮人类写代码”演进到“自己在后台独立运行”，运行时沙箱在当下成为了更具爆发力的生态位。

<details>
<summary>Original English</summary>

**Akshat**: My setting is yeah sandboxes work is sandbox it's just like buildtime sandboxes versus runtime sandboxes and actually it turned out runtime was better right

</details>

**主持人**: 没错。而这两者最本质的区别在于，运行时沙箱需要处理极其多维和动态的镜像挂载配置、高速数据持久卷的动态解绑与挂载、以及更严苛的出站网络监控过滤。

<details>
<summary>Original English</summary>

**Host**: and the difference there is runtime sandboxes have a different configuration surface of like how you configure images, how you like attach like storage and

</details>

### SDK与智能体体验

**主持人**: 这确实极其精彩。另外在 Python 和 Rust 生态里，近期也发生了很多大事。比如 Modular 团队被高通（Qualcomm）整体收购了。你对目前业界在 Python 之外去构建各种 AI 专用编译器和底层语言的尝试怎么看？

<details>
<summary>Original English</summary>

**Host**: yeah it's it's fascinating other people Astro also openai also like Python tooling ecosystem people are you still sort of bullish build building on top of Python also recently modular also got bought by by Qualcomm just any any of your takes there

</details>

**Akshat**: 我们最早选择 Python 作为我们的第一 SDK 语言，是因为当时所有的数据科学和机器学习资产全部是基于 Python 社区的。但实际上，我们今天已经推出了成熟的 Go 语言和 **TypeScript** SDK，而且 Modal 底层的调度运行时完全是用纯 **Rust** 编写的，在语言层面上是完全解耦和通用的。

在大模型推理和微调训练方面，Python 依然是不可动摇的霸主。但在上层智能体和工具调用的业务逻辑开发中，我们发现有很多开发者在极其高频地使用我们的 TypeScript SDK，因为上层的业务逻辑开发并不需要调用底层的 PyTorch 张量。在未来很长一段时间内，Python 和 TypeScript 仍将是整个科技界最重要的两大生产力支柱。

<details>
<summary>Original English</summary>

**Akshat**: yeah I mean we had Python as our first SDK language because that was the language that people did data and ML in. I actually now have go and typescript SDKs as well and our runtime is completely language. It isn't in Rust but it's it's not tied to Python by any means. We haven't seen I think with like inference and training stuff people are still very Python and the interesting thing with like the agent stuff is people use our TypeScript SDK a lot more because they're not actually doing anything than use ML. I don't think we'll have to go beyond that super soon because Python and TypeScript is still dominant.

</details>

**主持人**: 世界上最主流的两门核心语言。

<details>
<summary>Original English</summary>

**Host**: The last two languages in the world.

</details>

**Akshat**: 是的。

<details>
<summary>Original English</summary>

**Akshat**: Yeah,

</details>

**主持人**: 也就是它们了。

<details>
<summary>Original English</summary>

**Host**: that's it.

</details>

**Akshat**: 虽然也有人说未来的终极语言其实是英语和 Prompting。

<details>
<summary>Original English</summary>

**Akshat**: Well, English and prompting is

</details>

**主持人**: 哈哈，自然语言编程。我偶尔会遇到一些试图为 LLM 构建全新编程语言的理想主义者。比如 OpenAI 的董事会主席 Brett Taylor 之前就公开呼吁过我们急需一门智能体原生的新语言。但我至今没有看到任何成功的端倪。毕竟 Python 和 TypeScript 的生态和数据积累实在太深厚了。

在访谈的最后，我想总结一下：Modal 早期在开发者体验（DX）上进行了一场极其成功的押注，而现在你们正敏锐地把整个核心工程力量转向智能体体验（AX）。你认为未来真的有希望诞生完全构建在“提供卓越的智能体体验”这一单一维度的超级独角兽巨头吗？还是说，这依然需要依托其他更重度的算力变现链路？

<details>
<summary>Original English</summary>

**Host**: English and prompting. I occasionally talk to people who try to build new languages. They're like uh even um what's it say Brett Taylor uh who's chairman of open like we we need we need a new language for for LM so no one has come across one and I keep looking you know Python and Typescript are you have a lot of data plus but then also they are very imperfect as just as languages themselves then my close is I think modal used to be a big bet on developer experience and you've pivoted the team to agent experience is it like the way now like do you do Can entire companies and unicorns, multiunicorns be built on just having better agent experience? Do you need something else?

</details>

**Akshat**: 这已经深度融入了 Modal 的产品血脉。它绝对不仅仅指一些局部的、微小的技术改进（比如智能体怎么调用我们的 CLI）。它的本质在于，当一个智能体想要极速发布一个全新微服务或将最新的架构部署到生产环境时，它所面临的系统心智壁垒和迭代时延被压缩到了什么程度。在实际生产中，这种毫秒级部署和零运维开销的系统红利，对企业和智能体来说都是最核心的生产力。

<details>
<summary>Original English</summary>

**Akshat**: It's a big part of our identity. Uh it's not just the, you know, like the uh the very tactical how does an agent use the CLI? But it's also how easy is it to spin something up? Like what is your iteration time when you want to spin up a new service and uh you want to get something going in prod. uh in practice that matters a lot uh to people and uh I think it will continue to matter like uh people are building stuff even faster and if you give them ways to do it quickly and not have overhead then I think the debate for me has been do you do anything differently that is like very fundamentally different for developer experience versus agent experience you seem to be on the side of they're they they're like this they're like

</details>

**主持人**: 很多系统工程师经常会和我争论：DX 和 AX 在本质上到底有何不同？你的看法似乎是，这两者之间的重合度和技术共性极高。

<details>
<summary>Original English</summary>

**Host**: co have a blog post on that

</details>

**Akshat**: 它们的余弦相似度（Cosine Similarity）可能达到了 0.9 以上。

我们最近的一大核心工作确实就是围绕 `modal-bench` 来进行智能体的能力评估。一旦我们发现智能体在特定环节遇到了瓶颈或出现幻觉，我们就会迅速把这个产品反馈转化为系统原语的更新。比如以前我们只在 Web 控制台里暴露详细的日志和监控指标，现在我们把这些观测数据全部打包塞进了 CLI 里，方便智能体在无头模式下直接抓取和自主消费。

就是这么简单直接的工程闭环。

<details>
<summary>Original English</summary>

**Akshat**: cosign similarity on like 0.9 or whatever Yeah, I mean pretty much it's the um the main shift for us has been as I said like we built this uh benchmark modal bench uh to see where agents are lacking and yeah actually literally add surface area to a product if if they're reaching for something like maybe this should just be a CLI they yeah they hallucinate their own features yeah and sometimes it makes sense like if they're reaching for this thing it's product feedback like give it to them and then yeah actually moving we used to only have like logs and metrics in our UI just moving all those things with CLI as well so they're accessible in in in that form.

</details>

**主持人**: 大道至简。

<details>
<summary>Original English</summary>

**Host**: Simple as that.

</details>

**Akshat**: 谢谢。

<details>
<summary>Original English</summary>

**Akshat**: Cool.

</details>

**主持人**: 非常感谢你带来如此深度和前沿的行业洞察，我也终于理解了 Modal 之所以能取得如此巨大成功的底层逻辑。这是极其强烈的战略定力与极致工程执行力的完美结合。

<details>
<summary>Original English</summary>

**Host**: Thank you so much. Yeah, this is a great update and uh I can see why you guys have succeeded so much. Uh it it is really focus but also really good execution.

</details>

**Akshat**: 谢谢。我们依然长路漫漫。

<details>
<summary>Original English</summary>

**Akshat**: Thanks. I mean we have a long way to go.

</details>

**主持人**: 好的。谢谢大家收听，下期再见。

<details>
<summary>Original English</summary>

**Host**: All right. Thank you. Cool.

</details>