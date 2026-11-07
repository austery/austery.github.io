---
author: AI Engineer
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9-Y_oS9OBLc
speaker: AI Engineer
tags:
  - benchmarking
  - total-cost-of-ownership
  - inference
  - concurrency
  - hardware-optimization
title: 自建 AI 基础设施何时优于使用 API：imec 的基准测试与成本分析
summary: 比利时微电子研究中心（imec）的 Steven 探讨了企业从闭源 API 转向自建开源模型基础设施的经济性与技术权衡。基于 SWE-bench pro 等编程助手长周期任务的数千次基准测试，研究显示并发限制、KV 缓存及框架（harness）选择对 GPU 总拥有成本有决定性影响，例如 GLM 级别模型可实现约 24.5% 的成本节约。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - imec
products_models:
  - SWE-bench
  - Qwen
  - DeepSeek
  - GLM
  - Kimi k3
media_books: []
status: evergreen
---
### imec 的半导体背景与 AI 系统架构

我是 Steven，负责领导 imec 的 AI 部门。对于那些不了解 imec 的人来说，我们在 AI 领域其实并不是那么有名，但我们在半导体领域非常知名，有点被视作一颗低调的明珠。我们已经存在了四十多年，通常所做的是拥有全球最先进的研发无尘室，并与合作伙伴一起推动下一代半导体的发展。因此，我们在半导体领域产生的影响实际上相当巨大。我认为过去四十年中部署的几乎每一项晶体管技术，或多或少都是由我们在这种意义上发明的。所以从这个角度来看，我们确实是位于我故乡比利时的一颗隐秘明珠。那么，为什么一个半导体领域的极客会来谈论人工智能呢？因为我们做的事情远不止晶体管技术，我们一路延伸到系统层面，也一路覆盖到工作负载。这就是我所负责的部分，我们试图将 AI 工作负载与底层基础设施联系起来。

<details>
<summary>Original English</summary>
So my name is Steven. I'm leading the AI department at IMEC. For those of you who don't know what IMEC is, we're not that well known actually in the AI space, but we're very well known known in the semiconductor space. Been seen a little bit as the the hidden gem. We exist already for about more than four decades and what we typically do is we have the most advanced R&D clean room in the world and we actually run together with our partners next generation semiconductors in that sense. And so actually the impact that we've had in that semiconductor space is pretty huge. I think every single transistor technology that was more or less that is deployed now has been invented by us in the last four four decades in that that sense. So in that sense pretty much a hidden gem in in in Belgium where I'm where I'm from. So why is a a semiconductor nerd talking about artificial intelligence? Well, we do way more than just transistor technology. We go all the way up to systems. We go all the way up to the workloads as as well and that's where I'm responsible from for where we're trying to connect what AI workloads does to infrastructure in that that sense.
</details>

### AI 成熟度演进与走向自控基础设施

一方面，这也是因为我们在过去几年中亲身经历了这一过程。当然，在 imec 内部，我们也在大力使用 AI 来实现智能体工作流（agentic flows）。我们所经历的——我想过去几年我们很多人都经历过——其实是 AI 成熟度的不同阶段。我们在 2024、2025 年刚起步时，认为我们需要每一个前沿模型的最新、最强版本，最好的还不够好，我们需要更多、更强的模型。但与此同时，我们意识到价格模式开始演变，我们从基于订阅的定价逐渐转向了基于 token 的定价。随后在过去一年左右，我们越来越多地转向模型路由，试图为手头的任务匹配最合适的模型。我认为过去一年左右大家也都在做类似的事情。

<details>
<summary>Original English</summary>
On the one hand because we've lived that as well the last few few years. Of course within IMEC we're also working very much with with AI to kind of realize agentica flows as as well. And what we've experienced I think a lot of you of us have experienced at the last few few years is kind of a different stages of AI maturity. We we kind of started off in 2024 2025 thinking that we needed the latest and the greatest of every single frontier model and that the best wasn't good enough and that we needed more and more. But of course at the same time what we realized is that prices started evolve. We moved from more subscription based pricing to more token-based uh pricing. And then like the last year, we moved more and more towards model routing where we try to find the best type of model for the task at at hand. Things that I think all of us have been have been doing the last year or so as as as well.
</details>

我们不仅在公司内部，在与沟通的客户中也观察到了更进一步的演进阶段。从这种意义上讲，模型路由或许只是为了在为任务匹配正确模型时获得良好优化所摘取的首个低垂果实。随着 token 消耗量的真正快速增长，我们越来越看到采取其他手段的需求，而这些手段基本上意味着掌控自己的技术栈。因此，我们看到客户以及我们自己都在走这条路径：首先，从只关注闭源 API、直接调用现有服务开始；第二阶段对我们而言更多是探索如何进行成本优化；而我们目前正处于第三阶段，深入研究如何托管开源权重模型，以及如何租赁基础设施，从长远来看甚至可能直接购买自建基础设施。

<details>
<summary>Original English</summary>
What we're actually seeing as well with both within the company but also with the customers that we're that we're talking about is that there's other stages to that as as well. Model routing is in that sense maybe the first just low-hanging fruits in in getting a good optimization of finding the right model to the right task. We're seeing more and more as as token consumption really really grows that there's a need for doing other things as well and doing other things basically means taking control of your own stack in that that cell. That sense. So we're seeing customers and we're as on that path as well moving from well, first of all, we started with just looking at closed APIs, just grabbing what we could do. Then second phase was for us more, okay, let's see how we can do cost optimization. We're very much ourself now in the the third phase where we're looking at how can we host open weights models and how can we lease our infrastructure in the long run maybe even buy our infrastructure as as well.
</details>

我特别想谈谈这其中的第三和第四阶段，看看这究竟意味着什么。因为调用一个 API 或仅通过 API 来消耗 token 是非常直截了当的，做起来很简单；但一旦迈向第三和第四阶段，设计空间瞬间就爆炸式扩张了。在第一阶段，我们只需关心针对特定模型的准确率或任务复杂度选择何种模型即可。但一旦开始拥有自己的基础设施，你突然需要考虑一大堆其他事情：我要采用什么模型？我如何信任这个模型？你需要考虑测试运行框架（harnesses），还需要考虑大量的硬件配置，比如我该使用怎样的硬件架构？CPU 与 GPU 的配比是多少？我该如何做 KV 缓存优化等等。因此，这正是我们 imec 期望未来的定位所在。在这个非常注重模型和应用框架的世界里，我们也确实看到了从这些模型与框架到底层基础设施之间存在着巨大的鸿沟。

<details>
<summary>Original English</summary>
I particularly want to talk about this third and fourth phase of of of all of this and see what it actually would would mean because running an API or just having an API for to for token consumption is pretty damn straightforward. It's pretty easy to to do but the moment you move towards this third and fourth phase, suddenly the design space starts blowing up as as well. In the first phase, we're just worried about what is the right type of model for the right type of model accuracy or for the right type of task complexity. But the moment you start owning your your infrastructure, you suddenly need to worry about a whole lot of other things as as well. What kind of model am I going to take? How can I trust this this model? Uh, you need to think about harnesses, but you also need to think about a lot of hardware configurations as as as well, such as what is the right hardware architecture that I would would use for for this? What is the CPU to GPU balance? How can I do KB cache optimization and uh, and all of that. And so that's where we want to position ourselves as I am going forward as well, where of course here in a in a world that is very much aware of models and harnesses, but we do see very much also a gap from those models and harnesses to that infrastructure as as as well.
</details>

### 面向 Agent 任务的软硬件基准测试方法

所以，在过去的几个月里我们做了一项基准测试研究，这也是我今天来这里分享的内容。我们在过去几个月里实际进行了成千上万次测试运行，以真正量化从 API 转向自有基础设施到底能带来什么——纯粹是从智能体 AI（Agentic AI）的角度来考量。也就是说，如果你有一个智能体 AI 任务并具备特定的任务性能表现，从 API 转向自己的基础设施成本会发生什么变化？这也意味着从基于 token 的成本订阅模式转向真正的总拥有成本（TCO）。此外，你应该如何配置基础设施？到底哪些测试框架是相关的？需要何种硬件？首选的推理引擎又是什么？

<details>
<summary>Original English</summary>
Um, so what we did in the last few months and what I'm here to present today is a kind of benchmarking study that we did in the last few months. We did uh, really thousands of of runs to really really quantify what does that move from going from an API to really infrastructure really uh, give you. And so really from an Agentic AI perspective. So if you have an Agentic AI task, if you have a specific Agentic AI task performance, what would be the cost for you if you move from an API towards your own uh, infrastructure? So that also means moving from a more token-based cost subscription to really kind of total cost of of ownership. And also um, how should you then configure the infrastructure? Really from what kind of harnesses are relevant? Uh, what kind of hardware would you need? What is the inference engine of choice uh, for for all of this?
</details>

那么我们是如何展开测试的呢？我们非常希望在任务级别进行对比，因此专门选择了长周期任务（long horizon tasks）。因为如果你真正想拥有自己的基础设施，长周期任务是非常理想的切入场景。如果你做的是高实时交互式任务，其经济效益可能不尽相同；但对于长周期任务，我们认为这是掌控自身 AI 架构的首要原因或第一转折点。因此我们选定了一个具体基准，即 **SWE-bench pro** 任务集，它是针对编程助手的一套基准任务。我们所做的是对不同类型的编程框架进行验证或调整。我们为此选择了 Codex 以及 Claude Code 等，它们大致是目前用于编程辅助的三种最主流框架。然后，我们在此基础上测试了可以使用的不同模型类型，从传统的标准 API 环境开始，同时也涵盖了不同复杂度与参数规模的大量开源权重模型。

<details>
<summary>Original English</summary>
So how did we do this? Uh, we really wanted to compare at a task level, so we looked at uh, long horizon tasks specifically because long horizon tasks are really the perfect uh, um, if you really have your own infrastructure that you want to uh, to own. If you do do it very very interactive, it might not be the economies might not be the same, but for long horizon tasks, we think that that's the first reason or the first pivot point where um, taking a hold of your AI stack is really relevant. So we took one specific one being um, uh, the SWE-bench pro uh, tasks, which is set of benchmark tasks that exist um, uh, for coding assistance. And what we did is we kind of validate or kind of very different types of coding harnesses. We took Codex by and and Cloud Code for this, which are more or less the three most popular harnesses out there for for coding assistance. And then we kind of vary the different types of models that we could use on this as a as well. Starting with a traditional standard API environment, [clears throat] but then also looking at a wide range of different open weight models with different types of complexities and and parameter sizes as a as well.
</details>

不过，由于本场演讲讨论的是将这一过程转化为自建基础设施，我们自然也将其映射到了相应的硬件架构上，始终努力寻找既能满足大规模运行、又能支持多个并发用户的硬件架构。本质上，我们在增加硬件复杂度和模型复杂度的同时，也严格考察了整体的应用性能表现：任务的解决率（resolve rate）是多少？延迟是多少？成本又是多少？综合下来，我们进行了超过上千次不同的运行，搭建了完整的基准测试流水线，接下来我想带大家了解从中获得的各项结果。

<details>
<summary>Original English</summary>
But as this is a talk about translate translating this towards your own infrastructure, we of course also map this to the right hardware architecture at hand as well. Always trying to find the right type architecture that kind of is still sufficient enough to really do this at at at scale and it where you really have where you can have multiple concurrency concurrent users on on this. So in essence, we kind of increased the hardware complexity, increased the model complexity, but at the same time also looked at really the application performance of all of this. So what is the kind of the resolve rate of your task? What is the latency and what is the cost? All in all in all this was more than a thousands of different runs that we did. We set up a full benchmarking pipeline and I kind of want to run you run you down with the different results we got out of out of this.
</details>

### 模型性能与硬件成本的阶跃关系

我们不妨从最显而易见的一点开始：不同模型、不同模型复杂度以及不同的参数量，在这些任务上带来的准确率确实各不相同。我们实际上可以将这些模型划分为三大类：
- 第一类是较小的模型，这里所谓的较小是指参数量在几千亿以内，例如 **Qwen** 和 **DeepSeek** 都属于此类，它们达到的任务解决率大约在 **32.5% 到 40%** 之间，能够准确正确地完成任务；
- 第二类像 **GLM**，水平真正达到了与 Opus 相当的区间；
- 第三类是几个月前面世的 **Kimi k3**，其实际表现非常惊艳。坦白讲，这其中可能也有一部分原因在于它或许将部分测试集包含在了训练集中，但结果确实相当亮眼，达到了 **86%** 的解决率。

这些内容并不是什么在人工分析中查不到的东西，单看这些并没有带来太多额外洞察。

<details>
<summary>Original English</summary>
So let's start maybe with the most obvious one. Kind of different models, different model complexities, different model parameters sizes actually give you different accuracies of these of these tasks. We could actually really classify three main categories of of models. The more smaller ones and with smaller ones I would say up to a few hundred billion of parameters where Quen and and DeepSeeker are part of. They kind of got a got into a resolve rate of about 32 5 to 40% of tasks that really were able to achieve accurately correctly. Second one like GLM, um, was really at Opus level, uh, uh, range and then Kimik 3 that came out a few months ago, um, was, uh, really was really crushing it to, in all honesty, also probably because part of it has been probably in the training set as well, but still the the the results were quite, uh, substantial. Had a resolve rate of 86%. Now, all of this is not something that uh, is is something that you can easily find on artificial analysis as well. This doesn't really give you a lot of uh, uh, additional insights.
</details>

我认为真正更有意思的，是把基础设施和硬件的视角结合进来。在这个维度上，我们确实看到了相当大的差异。比如对比 Qwen 与 DeepSeek，两者的整体应用层表现在很大程度上处于同一水平；然而，如果再看运行 Qwen 与 DeepSeek 所需的硬件配置，在租用 GPU 成本方面会出现高达 **4 倍**的差距。类似地，如果仅从 GLM 模型转向 Kimi k3 模型，准确率虽然带来了约 **20%** 的提升，但总体而言在租用 GPU 成本上只增加了 **15%**。这说明了什么？它说明一旦迈向开源权重模型，全面考察其硬件约束和实际开销是极其重要的，并且这里面绝对不存在所谓的线性曲线。它往往是一个阶跃函数：你选择某个特定模型，即使只是换成稍好一点或性能稍弱一点的模型，都可能对所选硬件架构产生巨大影响。

<details>
<summary>Original English</summary>
What I think is really more interesting is if you add the infrastructure and hardware angle to it as well. And there we do see quite a bit of of of differences. What I think is interesting is if you compare for example Qwen with with DeepSeek that all in all the application performance of it is more or less on the same, uh, level. Although if you then look at what kind of hardware you would need for Qwen and DeepSeek, you're looking at a factor of four and in terms of renting GPUs that are is more expensive. Um, similarly if you just make the move from, um, a GLM model to, uh, a Kimik 3, uh, model, it gives you a bump of about 20% in in accuracy, but all in all it's just giving you only a 15% increase in cost in renting GPUs as well. So what does that tell you? It basically tells you that if you move this make this move towards open weight models that it's super super important to kind of look at the hardware constraints of this as well and also look look at the actual, um, costs of, uh, of all of this and there's definitely not a linear curve to be found here. So often it's just a step wise function where you where it might be that you're choosing a specific, uh, model and that just taking a slightly better or slightly, uh, less performant model would have a huge impact on the hardware architecture of choice as as well.
</details>

### 并发瓶颈与 KV 缓存开销

以上主要是从应用性能角度的观察。接下来我们换个角度来看，那就是并发能力。因为在使用 API 时，你可以获得某种稳定的 token 消耗表现，大致知道 token 延迟和 token 吞吐量会是多少；而一旦转向基于基础设施的自建方案，你就必须立刻考虑并发问题。换言之：在同一台机器上究竟能稳定承载多少并发用户，而不至于导致系统的延迟彻底崩溃？

<details>
<summary>Original English</summary>
So that's one and that's looking at mainly from an application performance perspective. Um, let's take a different angle to it and that's concurrency. Um because when you're using an API, um you can um get a certain performance of of token consumption. You know, you know more or less what your token latency is going to be, and you know what your token's throughput is going to be. The moment you make the move towards a more infrastructure-based solution, suddenly you need to worry about concurrency as well. In other words, how many users can I reliably uh put on the same uh machine without the system completely deteriorating from a latency perspective in that that sense.
</details>

这里面既有显存容量的考量，也有延迟层面的考量。显存意味着大多数系统是受显存带宽与容量限制（memory bound）的，一方面模型参数规模必须塞入显存中，另一方面所有用户的 KV 缓存（KV cache）也必须存放在显存内；随着使用该系统的用户数量增加，对 KV 缓存的需求也会变得越来越大。因此，我们针对前面展示的几种方案进行了测试，观察系统到底能够充裕承载多少并发用户。结果相当令人意外，或者说至少对于真正的大模型而言并不怎么乐观。

<details>
<summary>Original English</summary>
There's a a memory size to it, but there's also a latency uh perspective to it. Uh memory means that uh on the one hand, the most systems are memory bound, and it means that on the one hand, your model parameter size need to fit your your your memory, but also your user's KV cache as a as well. And as you have an increasing number of um of users uh using this the system, your KV cache uh requirement will become bigger and bigger as a as well. So, what we did is we kind of tried to look at the different types of solutions I just already showed you, and look at how many concurrent users we were actually able to fit really comfortably in that uh that system. And the results were pretty um uh surprising, or at least also maybe not that positive for really the bigger models as a as as well.
</details>

需要注意的是，这些不同的模型各自都有针对其最优化的硬件架构。但如果观察能够达到的舒适并发水平，即使配置了更大的硬件架构，并发承载量也会显著下滑。并且在所有测试情形中，我们的表现都要比基线（即 Claude Code）慢得多。顺便提一下，我们在讨论的每个主题都有详细的博客文章，演讲中的每个二维码都可以直接跳转查看。这表明在某种意义上，并发甚至比准确率更关键：准确率决定了基准底线；但面对真正庞大的模型，特别是在编程辅助这类长周期任务中，运行一个 **Kimi k3** 模型仅能支持约 **4 个并发用户**在其上稳定运行，并且其延迟仍然比基线慢上 **3 倍**。

<details>
<summary>Original English</summary>
So, bear in mind, each of these different models have their own hardware architecture that is uh that is optimal for it. But if you then look at the comfortable concurrency levels that we were able to get, it really really dropped down very significantly, even with bigger hardware architectures as um as well. And in all cases, we were much slower than uh uh our baseline, which was uh Cloud Code in that that sense. By the way, I think you figured it all out already. Um we actually have a detailed blog post on each of the topics I'm I'm talking about. Every QR code actually leads you to to that as um as as well. So, this kind of shows you that uh concurrency is actually probably even more important than accuracy in the in this sense. Accuracy gives you the kind of baseline, but then even for the really big models and even if especially if you look at very long horizon tasks like code assistance, running a Kimi K3 model only gives you about four concurrent users that can really run reliably on a on this and still the latency is still a factor three slower.
</details>

### 总体拥有成本（TCO）与转换最佳平衡点

随后我们进行了完整的最佳平衡点（sweet spots）分析：在哪些情况下坚持使用 API 是真正有利的？在哪些情况下更适合向各类模型托管商租用 GPU？又在哪些情况下真正购买并投资自建基础设施、在本地机房进行部署会更有吸引力？当然，做出这种转变可能还有许多其他维度的原因，但我们这里是从总拥有成本（TCO）的角度来审视的。

<details>
<summary>Original English</summary>
So, what we then did is a kind of full sweet spots analysis of okay, in which cases is it really interesting to stick to your API usage? In which cases would it make sense more for you to kind of move to renting out GPUs with the the various model providers that are out there and in which case would you really go for would it be more interesting for purchasing and really investing in your own infrastructure and building it out on prem. Of course, there can be a lot of other reasons as well to make that that switch but if we look at it from a total cost of ownership perspective.
</details>

在不涉及过多细节的情况下，我们在分析中发现：硬件架构系统的规格越低，从 API 转向自有基础设施的效果就越糟糕。在较低梯队模型及其对应的较低配置硬件架构下，你实际上需要大约 **89%** 的 GPU 利用率——这意味着 GPU 必须有 89% 的时间都在满载运转。类似地，如果换到更大的硬件系统上（抱歉我刚才说错了，这里应该是规格更高的硬件系统），例如 **8 张 B200** 的配置，你只需要 **15%** 的 GPU 利用率即可达到平衡；15% 是非常现实的目标，而在这种场景下要求 89% 的利用率在实际中根本不可行。如果综合平均来看，以 GLM 级别的应用为例，我们发现它正是从 API 走向自建基础设施变得更划算的最佳平衡点或临界阈值。在我们专门针对编程辅助这一应用所做的完整总拥有成本分析中，我们确实观察到了能够带来大约 **24.5%** 的成本节约。

<details>
<summary>Original English</summary>
So, without going into too much details what we saw there is that the lower your hardware architecture system actually is, the worse it is to move from API to your own infrastructure. We saw that if you really are at the lower tiers of of of models and as a result also at the lower tiers of the hardware architecture that you would need, you actually need an GPU utilization of about 89% so that means that your GPU needs to run at capacity at 89% of the of the time. Um, similarly if you actually move to more bigger hardware systems and I made a mistake there it should be a higher hardware systems. So, for example an 8 times B200s, you're okay with just 15% of of GPU utilization and that's really realistic and 89% is just completely infeasible in that that sense. If you then kind of average it out and if you look at for example GLM class applications, what we do see is that that's really the sweet spot or the threshold of when moving from API to infrastructure makes it more interesting as a as well. And in the full total cost of ownership analysis that we did specifically for this application being coding assistance, we really saw that you get into a kind of 24 5% of of cost saving.
</details>

### 测试框架对 Token 消耗与 GPU 用时的影响

以上完全是从基础设施的角度来看。接下来我们切换到测试框架（harnesses）的维度。我们也对测试框架进行了变量对比，观察了三种不同框架下的应用性能表现。乍看之下，各框架的应用性能其实没有太大变化，这或许有些出人意料：我们交付的每一个任务、采用的每种框架，基本上都把任务搞定了；对于不同类型的模型，在该基准测试上大致都取得了相似的应用准确率。因此初看之下你可能会说，框架根本没有任何影响，反正任务都完成了。如果是纯粹调用 API，情况可能确实如此；但如果转向自己的基础设施并按 GPU 使用时长付费，情况就截然不同了，因为此时 GPU 的实际运行时长（wall time）就变得至关重要。

<details>
<summary>Original English</summary>
So that's really infrastructure perspective. Let's kind of switch it over to harnesses. We also varied the amount the harnesses as a as as well and looked at what the application performance was for those three different harnesses. And on the first glance, the application performance actually didn't really change that much, which was maybe kind of surprising. Every single task we we gave every single harness we gave you more or less got it and every single for different kind of models, we kind of got into the same kind of application accuracy on this on this benchmark. So at the first glance, you could say, well, the harness actually doesn't have an impact whatsoever on that because it gets the job done. Well, that might be the case if you're going for an API only usage, but it's completely different if you're moving towards your own infrastructure and you actually pay for the GPU usage because then the wall time of your GPU really is is relevant.
</details>

我们观察到，不同类型的框架对过程中的 token 消耗总量产生了巨大影响。特别是对于 Codex 框架搭配 GLM 模型的情况，它生成的 token 总量仅为其他框架的**一半**；由于 token 减少，占用 GPU 的实际运行时长同样缩减了**一半**。这意味着，尽管各框架给出了相当或几乎相同的应用性能表现，但最终产生的 GPU 账单却只有其他框架的一半。这非常清晰地表明，在自建基础设施的场景下，选择与模型相适配的框架虽然可能不影响应用端任务解决率，但会对 GPU 的总拥有成本产生极为实质的影响。

<details>
<summary>Original English</summary>
And what we saw there is that different kinds of harnesses actually had a huge impact on the amount of token consumption we had in the in this and then specifically in the case of of Codex, we had for a GLM only half of the of tokens that were actually being being generated. And as a result, also the wall time of using these GPUs actually was half of that as well. So that means that although the harnesses actually gave you the right type of application performance or more or less a similar level of application performance, the GPU bill you would in the end have would be half of of the other harnesses as well. So it really shows very clearly that in that case also the right harness to model choice might not have an impact on application performance, but it has really an impact on your total cost of ownership for your GPUs as a as well.
</details>

### 总结与产业软硬件生态联盟

这仅仅是我们过去几个月开展的第一项研究。那么我们未来将走向何方？我认为这里面有太多值得剖析的内容。显而易见的是，从 API 转向自有基础设施绝不是一个简单或线性的选择。我现在展示的仅仅是编程辅助这一个单一应用，而在真实的企业级混合场景中，往往包含着多种不同业务应用的组合，这会使问题变得更加复杂。同时我们也发现，框架、模型与基础设施之间存在着极其复杂的相互关联。此外我还没涉及诸如量化（quantization）该怎么做、推测解码（speculative decoding）等具体优化手段带来的影响——我们在测试中也应用了推测解码，但尚未展开详细分析。

<details>
<summary>Original English</summary>
So, this is just the first study that we're that we did in the last few few months on this. Where are we going with this? I think there's a lot to unpack. It's very clear that moving this from API to infrastructure that is just not very simple or very linear choice. And I have showed this now for one single application being coding assistance, but a real enterprise mix would often have a combination of a lot of difference of applications as as as well. And that actually complicates things even even further. We also saw that there's a very complex relationship between harnesses, between the models, between the infrastructure. And I haven't touched upon other things like what do we do in terms of quantization? What is the impact of specific optimizations like speculative decoding that we applied as well, but that we haven't configured into to detail.
</details>

第三个维度在于，这本身就是一个持续变动的目标：新模型不断推出，新的硬件架构选项也不断涌现。因此，我们正在将现有的基准测试流水线扩展为一个完整的基准测试数据集，并计划向全社会公开共享，以便在未来持续追踪这一动态演进的目标。然而，仅靠我们一家是无法完成这件事的。我们是一家非营利性质的科研机构，对我们而言最关键的职责就是推动这一生态系统的融合。我认为软件世界与硬件世界理应走得更近。因此，我们正在发起一个联盟，旨在将软件领域中对硬件优化感兴趣的人才聚集起来，并与我们现有的客户生态（涵盖新兴及成熟的芯片供应商和基础设施提供商）对接。如果大家对此感兴趣，欢迎在本次演讲后与我们取得联系。非常感谢大家！

<details>
<summary>Original English</summary>
And the third dimension is of course that it's very much a constantly moving target as well. New models are being being launched. New hardware architecture choices are there as as well. So, we're actually building out a kind of benchmarking pipeline that we already have. We're building this out to a full benchmarking data set as well that we're going to share publicly for for everyone and trying to keep track of this moving target moving moving forward. But at the same time we cannot do this alone. We're a research organization. We're a non-profit research organization and the biggest important part for us is trying to bring that ecosystem together. And I think that the software world and the hardware world deserves to be much closer together as well. So, we're actually launching a kind of alliance to bring people who are interested in this part, software people from the software who are interested in hardware optimization. We're bringing this together with our existing customer portfolio of new and existing chip providers and infrastructure providers as well. And if you would be interested in this, uh free to reach out, uh after this uh this talk. Thanks a lot.
</details>