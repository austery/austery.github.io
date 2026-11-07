---
author: AI Engineer
date: '2026-07-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=31GUkCBD-Uc
speaker: AI Engineer
tags:
  - multimodal-agent
  - closed-loop-evals
  - prompt-optimization
  - computer-vision
  - quality-assurance
title: 大规模多模态智能体闭环评估系统的设计与实践
summary: 本文基于 Uber 计算机视觉团队在 Uber Eats 平台上的真实生产案例，详细阐述了如何为多模态图像编辑与审核智能体设计并构建闭环评估系统（Closed-Loop Evals）。内容涵盖多模态路由决策、基于人类金标数据的在线漂移诊断与自动化 Prompt 调优流程，以及多层级安全守门员（Swiss Cheese 审核模型）的架构设计与商业指标实践。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Uber
products_models: []
media_books: []
status: evergreen
---
### UberEats的规模与视觉挑战

**Jay**: 大家好，我是 **Jay**，今天我和 **Somya** 一起在这里。我们是 **Uber** 计算机视觉团队的成员。今天，我们将向大家分享一个真实的生产环境应用案例。噢，我的麦克风好像出问题了。好的，重新来一次。好的，别担心，我能搞定。现在能听到我说话了吗？

好的，今天我们将向大家介绍一个在真实生产环境中的应用案例，具体而言，我们将深入探讨我们是如何设计评估系统（**Evals**）以及评估循环（**Eval Loops**）的。

在正式进入智能体设计之前，我们先来聊一聊这个应用场景。作为我们的外卖配送市场，**Uber Eats** 目前的年交易额年化运行率（run rate）已经达到了约 **900亿美元**。我们每个月都在向这个平台添加数百万个新商品。我们正以同比 20% 的速度快速增长，并且在全球 **10000个城市** 开展运营。实际上，很多人并不知道，我们现在的配送市场（Uber Eats）在规模上已经和 Uber 的打车出行（Mobility）业务并驾齐驱了。

在提升用户体验方面，视觉内容其实起到了非常关键的作用。照片往往是消费者获得的第一信号，它直接决定了他们对商家的第一印象。因此，一张优质的照片甚至能决定一个用户是仅仅在信息流中刷过去，还是真正点击该商品并将其加入购物车。而且，我们越来越多地在 Uber Eats 上看到不同的媒介形式，尤其是**视频内容**。

但这本身是一个难题。我们那些规模较小的独立商家，其商品照片的质量往往无法真实反映消费者最终会拿到的实物。当我们在与商家沟通时，他们主要面临三个痛点：**缺乏时间**、**缺乏相关技术知识（know-how）**，以及**高昂的成本**，因为一次专业的照片拍摄实际上需要花费大量的资金。尤其是当商家需要随着时间推移不断更新菜单时，这个问题就会变得更加棘手。

因此，要在规模化（at scale）的场景下解决这个难题确实极具挑战性。因为我们的消费者想要看到真实、自然的实物照片，但也有相当一部分消费者其实对任何**人工智能生成（AI-generated）**的内容持有怀疑和不信任的态度。所以，当你打开 Uber Eats 应用程序时，你绝对不想看到在滑动浏览美食摄影时，所有的食物看起来都假得像 AI 生成的一样。

我们在这项工作中需要做到“穿针引线”般的精确平衡。我们必须能够对原始图像保持忠实（faithful），保留商家的品牌特征，同时还要避免千篇一律。如果我们在编辑每张照片时都使用完全相同的 Prompt，那么整个平台的商家多样性就会彻底崩塌。

此外，由于我们在全球范围内运营，平台上的图像质量呈现出非常典型的**长尾分布**。我们在这里准备了一些例子。你可能会看到各种低质量的美食摄影，比如清晰度很差、构图糟糕、拍摄主体没有居中，或者颜色失真。同时，平台上也存在大量用户生成内容（UGC）的图像质量光谱。

那么，我们在设计这些智能体（Agents）时的目标是什么？当大家思考这些目标时，或许也可以联想到自己正在构建的智能体系统。对我们而言，核心目标包括：第一，**维护真实性与信任度**；第二，在确有必要时**选择性地提升图像质量**；第三，进行**全局优化**，确保不会因为优化某些商家而蚕食了其他商家的流量；第四，**安全发布（ship safely）**，这也是我们今天分享的一个核心主题；第五，**持续学习**；第六，以**高成本效益**的方式在大规模场景下运营。

<details>
<summary>Original English</summary>

**Jay**: My name is Jay and I'm here with Sonya. We are part of the computer vision team at Aruba. We're going to talk to you about a real world production use. Oh, my son done. Okay. Try again. Okay. Don't worry. I'll I'll manage. You hear me now? Okay, so we're going to talk to you today about a real world production use case and specifically we're going to dive into how we design the e-bows and the e-bow loops. So All right, cool. So just before we get into the agent design, we're going to talk about a little bit about the use case. So our delivery marketplace Uber Eats, we do about 90 billion run rate per year at the moment. We were adding millions of items to the marketplace each and every year. Sorry, every every month. We're growing at 20% year-on-year and and we operate in 10,000 cities globally. So not many people actually know this but our delivery marketplace is just as big as the mobility side on Uber today. Visual content actually plays a really important role for the user experience. So a photo is quite often the first signal that a customer gets that gives them that initial impression about a merchant. So a good photo can make the difference between someone scrolling through the feed and actually clicking on an item and adding to the cart. And more and more we're seeing different modalities on Uber Eats uh especially video content. But this is a problem. So, our smaller independent merchants simply just don't have the level of quality for their photos that reflect what the eater is actually going to get. And when we speak to our merchants, there are three themes that kind of emerge. Lack of time, lack of know-how, and costs cuz these professional um photo shoots actually cost a lot of money. And this can be especially problematic if the merchant is updating their menu over time. So, this problem is actually pretty challenging to solve for at scale, right? Because our consumers, they want authentic, real-looking photos, um but a meaningful fraction of uh consumers actually distrust anything that is AI-generated. So, if you open up the Uber Eats app, the last thing that you want is to be scrolling through uh you know, food photography that looks like AI's lock. So, we're threading the needle here. We need to be able to stay faithful to the original image, preserve the brand of the merchant, and avoid everything looking the same. If we have the same prompt for every photo that we're editing, the diversity of the marketplace is going to collapse. We also, because we operate globally, we also have this long-tail distribution of different quality that we see across the marketplace. Um so, we've got some examples here. You might see food photography that, you know, has poor sharpness, poor composition, not centered, uh or or poor colors as well. We also have a wide range of spectrum of user-generated content on the platform as well. So, what are our goals when we're designing these agents? When you think through these goals, you might actually be thinking through, you know, your own agents that you're building yourself. But for us, it's about one, preserving authenticity and trust. Two, improving the quality when we need to. So, we want to be able to improve quality selectively. We want to optimize globally for for the entire marketplace. We don't cannibalize certain merchants. We want to ship safely, and this is going to be an important theme throughout the talk. We want to learn continuously, and we want to operate at scale in a cost-efficient manner.

</details>

### 智能体设计的平衡艺术

**Jay**: 针对这个问题，智能体（Agents）其实非常适合来解决。如果我们设想一个光谱，在光谱的一端，是偏向**确定性（deterministic）**的方法。它更偏向于**基于规则（rules-based）**，你对它拥有更多的控制力，但这样的系统非常脆弱，很难真正推广到整个市场规模。而在光谱的另一端，你赋予了智能体极大的创意空间，它拥有很强的自主性（agency）。这确实是我们想要倾注和借助的力量，但我们绝不能让这种自主性处于完全不受约束的状态。因为我们必须遵守既定的安全机制和红线机制（guardrails）。所以我们必须在两者之间寻找一种平衡艺术。这也是我们思考和设计智能体及评估系统的基本原则。

<details>
<summary>Original English</summary>

**Jay**: So, agents are actually really well-suited to solve this problem. So, if you imagine a spectrum, on the one side, you've got something that's more deterministic. It's more rules-based. Um and uh you you have more control over it, but it's fairly it's a brittle system. It's not actually going to be able to scale for the entire marketplace. Imagine the other side, you provide an agent with obviously a lot of creativity, it has a lot of agency. Um and that's actually what we want to lean into, but we can't leave that unconstrained, right? Cuz we have certain safety and certain guardrails in place that we need to adhere to. So, we want to find a balancing act. Uh and that's kind of set the principle for the way that we think and design around agents and evals.

</details>

### 生产环境中的工作流

**Jay**: 接下来，我们将深入探讨一个虽然经过简化、但在生产环境中极具代表性的系统实例。我们会一步步剖析每个阶段以及我们如何对其进行评估，同时也会分享一些持续学习循环（continuous learning loops）。

首先，我们拥有一个被称为**图像理解与路由智能体（image understanding and routing agent）**的模块。在这里，多模态（multimodality）能力显得尤为关键。我们实际上会让大语言模型（LLM）去描述它在照片中看到了什么，并基于此生成结构化的输出。接着，我们将这个结构化数据发送给**路由器（router）**。

路由器会判断：我们是要对这张图片进行增强（enhance），还是直接跳过（skip）？如果决定跳过，我们将保留原始图片。如果选择增强，则会将其发送给下一个模块——**图像编辑智能体（image editing agent）**。

这个编辑过程实际上是在一个循环中运行的。编辑智能体会从 **QA智能体** 获得反馈，在这个循环中不断进行编辑、自我修正并解决发现的问题。如果经过了设定次数的循环后系统仍然判定失败，我们便不会发布这张增强后的照片。

如果顺利通过了循环，图片将进入最终的**后处理与QA步骤（final post-processing and QA step）**。一切无误后，我们才会将其发布到商家的菜单上。

最后，至关重要的一点是，我们会**记录所有数据（log everything）**。关于日志，简单提一句。我不知道大家是否能看清这里的 JSON 数据，但你可能会注意到，在这个端到端的编排中，所有智能体的记录在 JSON 中都是一种**扁平化的结构（flat structure）**。这对于整个团队来说非常有用，因为无论是技术人员还是非技术的工程、产品人员，都能够直接深入查看特定案例进行诊断，或者将其汇总来进行聚合分析。

我们认为在项目伊始就重视日志记录是极其关键的。你必须从最开始就建立好日志系统，因为如果没有这些记录，你根本无法进行优化，更不用说建立自我学习循环了。在 Uber，我们也非常依赖我们自己的双眼去进行验证。

<details>
<summary>Original English</summary>

**Jay**: So, now we're going to actually like dive a little bit deeper into a simplified but representative example of what we have in production. And we're going to go through each stage and how we eval it, and then talk through some continuous learning loops as well. So, first up, we have what we call an image understanding and routing agent. So, this is where multimodality is is is pretty important. We actually ask the LLM to describe what it sees in the photo. Um and then we we create a structured output from that, and we send it to a router. The router will then determine, do we enhance it, or do we skip it? We skip it, we will keep the original. If we enhance it, we send it to our next agent, which is an image editing agent. And this can actually run in a loop. So, it gets feedback from a QA agent. Um it can edit uh in the in this loop and self-correct and fix things um as it goes. If it goes through a number of loops and it still fails, we we don't publish it. Then we actually send it to a final post-processing and QA step. If that's all good, we'll publish it to the menu. And the last thing that's really critical is we log everything. Just a quick note about logging. Don't know if you can actually read the JSON here, but you might notice that all of the agents in this end-to-end orchestration is within one It's It's basically a flat structure in this JSON. Um and so, this is actually incredibly useful for the entire team because anyone, be it non-technical uh technical um folks on engineering product, can actually dive in um and look at specific cases to diagnose and also roll up things to look in aggregates. Um and it's important to note here that, you know, we think this is important to start with. You want to start with your logging cuz if you don't start with it, you have nothing to optimize for, let alone set up a self-learning loop. And at Uber, we um we use our eyes. Cool.

</details>

### 路由智能体与评估指标

**Jay**: 我们再深入了解一下路由器的设计。路由器的逻辑其实非常直接。如前所述，我们输入多模态数据，结合图片本身的视觉特征和文本描述等元数据，让模型描述其看到的内容并输出结构化结果。有了这些结构化输出，我们就可以对照预设的评估细则（rubric）进行评分。这套细则包含了一系列的通过和失败标准。最后一步就是据此决策“增强”还是“跳过”。

我们该如何评估路由器的性能？你可以将其视作一个传统的**分类器（classifier）**。在这里我们使用**混淆矩阵（confusion matrix）**，相信许多人对此已经非常熟悉了。我们可以观测诸如真阳性（true positive）和假阴性（false negative）等指标。本质上，我们是在评估系统的**精确率与召回率（precision recall）**。

在实际应用中，路由器的设计可能会复杂得多。例如，为了降低成本并提升用户体验，我们可能会希望将图像路由给一个延迟较低的小模型，虽然这可能会在图像质量上带来一些折中。如果采用这种设计，混淆矩阵就不再是简单的 2x2 矩阵，而会变成一个 **N x N 矩阵**，矩阵中的每个格子都可以告诉我们路由器是否正确地将图像分流到了特定的分支。

现在，我将把麦克风交给 Somya，她将深入探讨我们如何应对数据漂移以及如何实现人类对齐。

<details>
<summary>Original English</summary>

**Jay**: We're going to dive um a bit deeper into the router. So, the router's actually pretty straightforward. If you remember, we we you know, we have this multimodality input. We look at certain text description metadata, the image itself. We ask it to to to to under um describe what it's seeing. We create structured output from that. With that structured output, we can then grade against a rubric. So, we have these pass and fail criteria. The last step is we want to decide whether or not we should enhance or skip. How do we actually eval this? This is you could think of this as a more sort of traditional classifier. So, here we we have a confusion matrix. You know, many of you are probably pretty familiar with this. Um but we can look at things like the true positive cases, the false negative negative cases, and so on and so forth. Essentially, what we're doing is we're measuring the precision recall. In practice, your routers might actually be much more sophisticated. So, for example, we might want to route an image to a lower latency smaller model to be able to save on cost and improve the user experience at the trade-off of quality. And if that's the case, instead of having a 2 by 2 matrix for your confusion matrix, you might actually have an n by n matrix. Where each grid is actually telling you whether or not you're correctly routing to that specific branch. So, I'm going to now hand over to Somya who's going to dive a little bit deeper into how we handle drift and human alignment.

</details>

### 人类金标与对齐

**Somya**: 刚才 Jay 介绍了我们如何评估路由决策，现在我想谈谈如何推出模型的第一代版本。

在我们的业务场景中，我们将**人类标注（human labels）**视为最权威的**黄金真值（golden source of truth）**。这也是我们希望模型去对齐（align）的目标。具体做法是：我们首先收集一个具有代表性的数据集，覆盖不同的菜品切片、地理区域、品类以及不同的初始图像质量类型。随后，我们将这些数据发送给人工标注团队，并向他们提供高度客观的标注指南。这一步是为了尽可能消除人工标注过程中的主观偏差和噪声。

一旦建立了这套标注系统，我们便开始着手微调（tuning）我们的模型。我们会运行智能体并获取其输出，接着将其与黄金数据集进行比对，评估其表现是否足够好以达到上线标准。如果达到了我们设定的红线指标（guardrail metrics），我们就会将其上线部署。如果没有达到，我们就会持续微调，直到指标达标。

在路由决策阶段，我们的核心红线指标是**召回率（recall）**。我们必须确保任何低质量的图片都不会漏网并溜进我们的系统中。

<details>
<summary>Original English</summary>

**Somya**: So, now that we spoke about how we eval the routing, I want to talk about how do you get the first version of the model out. For our use case, we consider human labels as the golden source of truth. And this is what we want to align our models to. The way we do about this is we go collect a dataset which is representative. So, you know, different cuts, geographies, dish type, image quality type. Send it to our human labelers and give them a very objective guideline to label on. This is to remove any subjective biases or any noise coming in from human labelers. Once we've got that system set up is when we start tuning our model. We take our agent, we go ahead get output from the agent, compare it to your golden dataset, evaluate if it's good enough to ship, if it meets your guardrail metrics, you go ahead and ship it. If

</details>

### 生产失败案例剖析

**Somya**: 我们来看几个在实际生产中遇到的典型失败案例。

在左侧，您可以看到一张质量非常高的芝士汉堡图片。但右侧的记录显示，路由智能体在这个案例上误判了。它判定该图的“技术质量较差”，并建议将其发送进行增强处理。这种误判会带来两个严峻挑战：第一，你为一次毫无质量提升空间（zero quality lift）的图片编辑付出了不必要的计算成本；第二，对于一张本身质量已经极高的图片，再次进行编辑和重构反而存在降低其画质的风险。

在光谱的另一端，则是召回率漏判（recall miss）的例子。左侧的实物图中明明只有六只鸡翅，但如果仔细查看右侧对应的商品名称，却写着“八只装鸡翅”。而我们的路由智能体竟然批准通过了这张图。这里面隐藏着巨大的风险：一旦你把这张只有六只鸡翅的图发送去做增强，模型在试图匹配文字描述时，就极其容易**幻觉（hallucinate）**出两只额外的鸡翅。这会严重违反我们之前向大家展示的“忠实度（faithfulness）”指标。

我想表达的更宏观的观点（meta point）是：即使你离线训练好了一个表现出色的模型，但在实际生产中，由于长尾效应的存在，模型依旧会不断遇到失败案例，静态模型在真实的动态系统里是行不通的。你必须拥有一种机制，让你的 Prompt、智能体乃至整个系统本身能够随着时间的推移**不断演进和自适应**。

<details>
<summary>Original English</summary>

**Somya**: not, then you go tune and you keep doing this until you meet your guardrail metrics. For routing, our guardrail metric is recall. We don't want any bad image to slip through our system. Here are some examples of the failures we've seen. Uh on your left you see a very good image of cheeseburger. Uh on the right you notice that the routing agent actually failed this. It said the technical is low ball and it will go send this image for enhancement. Now there's two challenges when you send this image for enhancement. Firstly, you pay the compute cost for a zero quality lift from this image. And secondly, uh there is a risk of degrading this image given it's already such a high quality image. And on the other end of the spectrum, you have a recall miss. So on your left you have an image with six chicken wings and on your right if you notice the dish name, it says eight pieces chicken wings. And your routing agent approved this image. That means So now there's a risk here if you send up send this image for enhancement and you only see six chicken wings, there's a chance your model's going to hallucinate these two extra wings to match the description. And that's also an that's a the cut we take at our faithfulness metric that Jay earlier showed us. So the meta point I'm trying to get here is you've trained your offline model, but there will be long cases where your model is going to continue to fail and the static model will not work in the real system. You need a way such that your prompts, agents, system itself is evolving over time.

</details>

### 闭环自适应调优系统

**Somya**: 这正是我们在系统中所实现的能力。不仅是在路由决策上，我们系统中的每一个组件都能够在线对自身的漂移进行自适应微调。

具体而言，我们以固定的频率在生产环境中抽取样本数据，并在相同的标注指南下发送给人工标注团队。收集到这批新的人工标注数据后，我们对比智能体的输出与人工标注的结果，找出其中的不匹配（mismatch）。

如果出现不匹配，我们的**全局诊断智能体（umbrella diagnosis agent）**就会介入。它会吸收反馈信息，精准定位（localize）问题发生的核心节点，并触发我们的**自动化调优管线（auto-tuning pipeline）**。在完成智能体调优后，我们会再次对照前文提到的黄金数据集进行基准测试（benchmarking）。如果通过了我们在设计之初制定的各项指标，我们就会直接部署并上线这个新模型。如果没能通过，系统则会继续迭代调优。

这个流程完全是在生产数据上定期、自动运行的。最美妙的一点在于，它完全是由配置驱动（config driven）的，**不需要人工干预（no human in the loop）**。我们的诊断智能体能够自己编写配置文件，并自动触发这里的自动化调优管线。这是维持模型长期敏锐度的关键。离线训练的静态模型只是起点，而这套闭环系统才是让系统保持生命力的源泉。

稍后 Jay 会花更多时间讲解诊断端的设计。现在我想将焦点拉近，重点拆解一下自动化调优（auto-tuning）的具体技术细节。

同样，我们虽然以路由为例，但这一套方法被应用在微调系统中的每一个智能体上。当我们在已标注的目标数据中发现智能体输出与人类金标存在不匹配时，我们会调用一个**Prompt优化智能体（prompt optimizer agent）**。该智能体本身又由两个子智能体组成：**反射智能体（reflect agent）**和**合成智能体（synthesize agent）**。

反射智能体的任务是仔细分析不匹配的案例，试图滤除噪声，并找出数据集中存在的系统性问题。然后它会将这些反思与诊断反馈发送给合成智能体。合成智能体接收到反馈后，结合当前的智能体配置，基于反馈自动更新智能体的配置文件，并重新运行基准测试。一旦基准测试通过，系统就会将新版智能体注册到智能体仓库中。在下一次生产环境运行时，系统就会自动加载这个最新版本的智能体。

正如我提到的，这是一个完全闭环且无人工干预的系统。同时，我们对各项安全指标（guardrails）保留了极佳的可观测性，并且在系统出现任何异常时都设计了快速回滚（rollback）机制。

<details>
<summary>Original English</summary>

**Somya**: And that's what we've done uh for our system as well. And I'm talking more from the routing perspective, but every component in our system is able to tune itself uh for any drift online. So what we do is we sample production data at regular cadence, uh send this to the human labelers with the same guidelines that we have seen before. Once you've got that data, we compare our agents' output with the output we got from the labelers and see if there's a mismatch. If there's a mismatch, we have an umbrella diagnosis agent which takes in the feedback, localizes where this issue is happening, and triggers our auto-tuning pipeline. Once we tune this agent, we go and benchmark it against our golden data set that we saw earlier, and if we pass our golden data set on the metrics that we had designed, we go ahead and ship this model. Uh if not, then you kind of keep iterating. And this happens on a regular basis on production data set. Um the beauty of this is this is completely config driven and doesn't require human in the loop. Your diagnoser agent can write your config and trigger the auto-tuning pipeline here. And this is what will keep your model sharp over time. You will have one static model with the offline, but this is what is going to keep your system alive. Um so Jay is going to spend more time on the diagnosis side of it. What I want to do is zoom into the auto-tuning bit. And again, we're looking at routing, but this is how we tune every agent in our system. Uh so we start with a target agent, and we've already got these uh unseen eval samples from our humans. We go find out the mismatch and matches and call a prompt optimizer agent. Now, this itself is two sub-agents. There's the reflect agent and the up synthesize agent. What reflect does is it it just looks at the mismatches, tries to find remove any noise, find any systemic issues that might be in your data set, and reflect on it and send that feedback to the synthesize agent. Now, the synthesize agent takes this feedback. It has your agent config. It goes and updates your agent with the new config based on the feedback it's getting. And goes and benchmarks again. If this benchmark is passed, you actually register this new agent in the new agent store. And next time your production runs, you pick up the new version of the agent. And this is a closed-loop system as I mentioned, no human in the loop. We definitely have observability on the guardrails, quick rollback built in in case of any issues with the system itself.

</details>

### 图像增强与自修正循环

**Somya**: 接下来探讨我们编排工作流的下一个环节：图像增强阶段。这是一个分为三步的流程。

第一步，我们针对特定图片生成专属的 Prompt。我们输入菜品的文本描述，以及从前面的路由智能体处获得的修改指令，进而为这张图片定制生成一份优化 Prompt，明确指出该图具体需要在哪些维度上进行提升，并在此基础上完成图像编辑。

紧接着，图片将面临 **QA闸门（QA gate）**的审核。这是一个多维度的评估关卡，会从摆盘（plating）、忠实度（faithfulness）和色彩（colors）等多个方面进行综合判定。如果审核通过，图片将直接发布上线。如果没有通过，系统会捕获来自 QA 闸门的具体反馈，并将其与最初的输入一同重新投递回 Prompt 生成模块，对 Prompt 进行修正并重新进行图像增强编辑。

这种机制会产生两种终极结果：要么系统在迭代了 K 次内通过了 QA 闸门并最终成功发布；要么为了安全而折损一定的覆盖率（coverage hit），选择彻底放弃对这张图片的增强并保留原图。

我们来看一个具体的例子。在左侧是一碗红薯条的原始照片。第一轮增强编辑后，我们的 QA 智能体拒绝了该图，原因是分量大小被修改得不正确，且整体摆盘看起来非常虚假和不自然。我们吸收了这些反馈，在第二轮迭代中进行了修正，图片顺利通过了审核并发布。我们用来衡量这一表现的指标是 **Pass at K**（即在第 K 次迭代时通过的比例）。理论上，随着允许迭代次数的增加，因为系统可以获得更丰富的纠错反馈，整体的通过率会显著提升。

现在，我将麦克风交还给 Jay。

<details>
<summary>Original English</summary>

**Somya**: Moving on to the next step of our orchestration flow. So we spoke about routing, moving on to the enhancement bit of it. It's a three-step process. What we do is the first step, we generate a prompt specific to this image. We take in the description, we take in the directives we were getting from our routing agent, and we go ahead and generate a prompt for this image. What needs improvement in this image specifically? And we go ahead and enhance this image. Then you've got the QA gate, which is a multi-dimensional gate, looks at multiple things like plating, faithfulness, colors. And if it passes is when you actually go ahead and publish this. If it doesn't pass, you take the feedback back from the QA gate, push it back to your generate prompt along with the initial inputs you sent it, and go ahead and enhance it again. So, there's two end results here. You either keep enhancing for K iterations and you pass your QA gate and you publish, or you take a coverage hit and you never enhance this image. Here's an example. On your left, you see a bowl of sweet potato fries. We send it up for the first iteration and our QA agent rejects it because the portion size is incorrect, the plating is very unrealistic. We take that feedback in, go for the second iteration, and we're actually able to pass it the second iteration. So, the metric we are measuring here is pass at K. Pass at K is essentially the pass rate at Kth iteration. And ideally with the more the iterations, your pass rate will increase because you're getting more feedback in. Now, I'll pass it on back to Jay to cover the rest of this.

</details>

### 定义“更好的图像”

**Jay**: 谢谢 Somya。在结束对评估指标生成的讨论之前，我想补充一点：我们在计算 Pass at K 指标时，内部使用的是**两两对比（pairwise comparison）**机制。这意味着我们会直接对比输入图像与输出图像，以此评估增强后的图像是否真的变好了。

但是，我们该如何定义什么是“更好”？这涉及很多关于产品、设计、政策及法务方面的要求。在 Uber，我们必须确保评估指标完美契合平台对图像质量、法律合规以及品牌调性的期望。

具体而言，我们会评估：图像是否忠实于食物本身？信息是否完整？观感是否自然？画面是否足够写实？此外还有一系列细化的考核指标。最终，这个评估步骤会输出一个明确的结论：“是（通过）”、“否（不通过）”或“不确定”。

<details>
<summary>Original English</summary>

**Jay**: Thanks Thanks, Somya. Um So, yeah, just before we end here on the um on on the generation of the vowels, we use what's called pairwise comparison, right, for our pass at K. So, it's looking at the input image and the the output image, and it's assessing whether or not it's better. But how do we actually find what's better? So, um we're not going to dive into too much of the details here cuz this is kind of like proprietary stuff, and so we'll just mention it at a higher level that this is where you sort of For least for us at Rue Ba, we have to make sure that we're aligning with product, design, policy, legal. And this is where we're baking in what we define as a better image on the platform into our Evals. Um so, examples here, is it faithful? Is it complete? Is it natural? Is it realistic? And there's a bunch of other things as well. The output of this is then uh a yes, no, or unsure.

</details>

### 多模态失败模式分析

**Jay**: 让我们来看几个典型的失败模式案例。

在第一个例子中，左边是输入，右边是输出。仔细对比就会发现，模型在输出图中无中生有地添加了虾肉（shrimp），这在菜单描述中是完全没有的。因此，它未通过忠实性（faithfulness）测试。

而在另一个案例中，情况正好相反。输入的原始寿司图片底部配有一些酱汁，但增强后的输出图却将酱汁彻底抹去了。这导致其在完整性（completeness）审核上判定为失败。

第三个例子非常有意思。在首轮迭代中，编辑智能体尝试进行了一次非常有创意的修改。但是 QA 智能体判定“这不够好”。随后，编辑智能体在下一轮修改中出现了**过度修正（oversteer）**，变得极度保守，直接退回并套用了一个最普通的白色瓷碗。这就是典型的**奖励黑客攻击（reward hacking）**现象——尽管从像素级来看输入和输出发生了巨大的改变，但我们认为这并没有产生任何实质性或正向的图像质量提升。

再看一个例子，输出图像中盘子边缘奇怪地覆盖在了底部的酱汁盘之上。这是因为在编辑图像时，底层大模型的局限性直接渗透（leak）并影响到了我们的应用层，导致图像违反了基础的**物理合理性与物体相干性（object coherence and physics plausibility）**。对于这类底层模型问题，我们有时会与前沿基础模型团队协同，向他们反馈此类物理建模缺陷，共同寻求优化。

最后，为什么我们强调多模态能力非常关键？请看这个例子，在输入和输出图像中，我们仅凭肉眼根本无法看清盘子里的馄饨是不是刚好有 8 个。因此系统无法建立足够的置信度。在这种“不确定（unsure）”的情况下，生产系统会为了安全直接拒绝发布，从而保护消费者的信任。

<details>
<summary>Original English</summary>

**Jay**: So, here are some examples of failure modes. So, input and output on the right. The inputs on the left, outputs on the right-hand side. This might be a little bit uh difficult to to see at the first pass. We actually added shrimp here and we shouldn't be. So, we failed faithfulness. This is where we go the other way. So, the input um has some source at the bottom of the sushi. We actually remove it. So, we failed completeness. Here's actually a pretty interesting example where the agent actually attempted a more creative edit in the first iteration. Um and then the QA said, "Nope, it's not good enough." Uh and then it actually oversteers the other other way. And it becomes overly conservative. Sort of falls back to this generic ceramic plate uh ceramic bowl, sorry. So, this is an example of a reward hacking actually. And and this is a nugatory change, but something that we don't think is a meaningful or influential change despite the actual raw pixels of the input and output being pretty different. Here's another example where in the output the plate is covering the sauce. This is an example where for some some of the frontier models that we're using for the actual image editing, some of their um some of their problems will actually sort of leak up into our applied use case. Um and so, so object coherence and physics plausibility of the Evals that sometimes will coordinate with the frontier teams and and let them know about these problems and work together with them. Here's uh an example of why multimodality is is is pretty important. In the input and the output, we we can't actually see that there are eight pieces here of of the wontons. So, we're not confident, actually. We're not sure. And so, this is an example where we would actually reject it in production and and it wouldn't it wouldn't go through.

</details>

### 瑞士奶酪式终极防御

**Jay**: 在完成了上述的所有编辑与审核步骤后，图片要上线的最后一关就是后处理以及我们所说的“发布就绪 QA”（publish-ready QA）。这是决定图片能否发布到生产环境的终极闸门。

在此阶段，我们会执行严格的政策合规性检查（policy checks）以及多项质量复核。大家可能会好奇：既然在前面的编辑循环中已经做过 QA 了，为什么在发布前还要多此一举再做一次 QA？

原因在于，我们将整个防御体系视作一个**瑞士奶酪模型（Swiss Cheese model）**。没有任何一个审核环节是完美无缺的，每个智能体都像一片有孔洞的奶酪，但如果我们把多片奶酪叠在一起，这些孔洞被错开重叠后，差错漏网的概率就会被降到最低。因此，我们在架构设计中刻意引入了一定的**冗余性（redundancy）**，这能极大地降低低质甚至违规图片溜进生产环境的风险。这道最终闸门更具全局观，不仅能捕获遗漏的边缘案例，还能帮助我们监控并反向排查上游组件中应该被解决的缺陷。

<details>
<summary>Original English</summary>

**Jay**: So, the last step after all of that is a post-processing and what we refer to as the publish-ready QA. This is the final gate before we decide we want to publish something to production. Here, we do some policy checks. We also do some more quality checks. Um and you might be wondering, like, we've already done some QA. Like, why are we going to do another step of QA? The reason is because we think of this like a Swiss cheese model. So, we want to try and optimize for reducing the chance of a failure getting into production. And so, there is some redundancy here or there. And that's okay. Um and so, this QA gate is is a little bit more holistic. It captures more things. But, it also will try and flag things that we should have caught upstream, as well. All right.

</details>

### 多层级反馈与诊断器

**Jay**: 我们前面提到了好几种不同的反馈机制。总结来说，我们主要聊了第一种机制：模型微调循环（model loop），它主要用来应对在线数据漂移，并将模型表现与我们离线建立的人工标注黄金数据集进行对齐。

但实际上，我们的系统中还跑着更多的反馈循环。在 Uber，我们拥有非常优秀的**内部众测与试吃文化（dogfooding culture）**，新应用或新功能在正式发布给商家和消费者之前，会经过内部员工的大范围实测。而在图片增强功能上线后，我们同样设计了如何将生产环境中的真实用户和商家反馈，实时且顺畅地喂回给智能体，以持续校准智能体的行为。

随着引入的反馈循环越来越多，我们必须提升系统的泛化能力。为此，我们在整个系统之上构建了一层更高维度的抽象层，称之为**诊断器（diagnoser）**。

诊断器可以统一接收来自各种反馈渠道（如内部测试、生产报错、商家红线等）的所有输入数据。它能进行全局性的反思（reflect），精准识别出在复杂的级联智能体网络中，到底是哪一个具体的子智能体（如图像理解、路由、编辑或某个特定 QA 模块）需要被优化，并直接指派对应的微调管线去修改该智能体的配置。它既能微调单一智能体，也能同时优化多个智能体。

在我们的内部测试界面中，大家会经常看到我们为用户设计的“点赞（thumbs up）”和“踩（thumbs down）”按钮，同时也支持输入自由格式的文本反馈。这非常实用，因为我们可以直接从商家、设计团队以及 Uber 内部的其他产品团队那里收集到最直观的反馈，并将这些数据输入诊断步骤，让系统随着时间推移越用越聪明。整个微调流程与前文一致：复现被标记的成功与失败案例，并在发布配置更新前进行基准测试验证。

<details>
<summary>Original English</summary>

**Jay**: So, we've talked about a couple of feedback loops here. So, to summarize, we talked about predominantly this first one here, which is the model loop. And this is accounting for drifts and aligning with human labeled data set that we have and we've established offline. But, we actually have more feedback loops. So, we we have that Uber what we we have is a is a great sort of dog dog feeding culture. Um we will test apps before they go live. Um but, we also have when it goes live in production, how do we get that feedback back into our agent to be able to steer it appropriately? So, as we're adding more of these feedback loops, we want to be able to generalize the system. So, this is where we've actually created um a higher level of abstraction on top, which we call the diagnoser. So, the diagnoser can take in any input from these different feedback loops that we're capturing. It can reflect on what actual agent within the overall system needs to be optimized, and it can route that agent to be able to fix that configuration specifically. It could be one agent, it could be multiple agents. So, here's an example of internal dog fooding. You might see these in sort of different apps that you've got where you got the thumbs down and the thumbs up. We also take some free form feedback as well. Uh and this is actually great cuz we'll get feedback from merchants directly. We'll get feedback from, you know, design teams, other product teams uh at Uber. And we'll incorporate that feedback back into our diagnosis step and tune the system over time. Again, similar sort of workflow pattern here. We'll replay the examples that we know are those ones that have been flagged, be it good examples, be it bad examples, uh and then we'll benchmark the metrics before we push the latest config version.

</details>

### 生产指标与精细化运营

**Jay**: 最后一个环节就是将这套系统真正推向生产环境，并持续监控多项用来评估市场生态健康度的业务指标。

在这里，我重点分享一个核心商业指标——**转化率（conversion）**。我们会密切监控用户将商品添加至购物车、开始下单以及最终完成结账的整个流转效率。

选择这个指标是因为在 Uber Eats 的大规模生产环境下，我们积累了海量的数据，使我们有条件进行极其精细的**切片分析（slice and dice）**。我们可以将数据按地理区域、用户设备类型、菜品品类以及商家类型进行深度切片，观察每一类细分市场下的质量提升与转化率走势，并在特定业务细分领域进行针对性的优化与模型调优。

非常感谢大家参加我们今天的分享，谢谢！

<details>
<summary>Original English</summary>

**Jay**: The last step is is actually getting this into production. And and this is where we're looking for a whole heap of different metrics we track for for the marketplace quality and health. Uh I've just called out one here, which is conversion. So, we're looking for improvements in people adding to cart, converting, completing their orders. Um I think this one's actually an interesting one to call out because now at I mean, at least at Uber, but especially in production settings at scale, you have a lot of data that you can actually slice and dice. So, in this area as opposed to the others, what we can do is sort of slice by geos, by device type, by dish type, etc. And we can look at where things are improving in different segments and actually tune on certain segments as well. Cool, and that's it for our presentation. Appreciate it.

</details>