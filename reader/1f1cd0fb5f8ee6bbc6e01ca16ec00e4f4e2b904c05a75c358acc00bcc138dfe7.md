---
author: 课代表立正
date: '2026-04-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Lt-lVe957hc
speaker: 课代表立正
tags:
  - llm-infrastructure
  - cost-optimization
  - product-development
  - llm-router
  - distributed-systems
title: GenAI全明星对话：贾扬清、Opus与Martian谈AI产品的成本、架构与未来
summary: 本场访谈汇集了硅谷顶尖AI专家，包括贾扬清（Lepton AI创始人）、Jay（Opus Clip CTO）和Jason（Martian创始工程师）。核心议题涵盖生成式AI与传统软件开发的本质差异、AI成本优化的供应链思维、计算历史中的中心化与去中心化博弈，以及在模糊输出环境下建立评估（Evaluation）与QA体系的挑战。嘉宾们强调，AI开发正从确定性的逻辑世界转向统计学驱动的模糊世界，领域上下文将成为初创公司的核心护城河。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - 贾扬清
companies_orgs:
  - Lepton AI
  - Martian
  - Opus Clip
  - OpenAI
  - Stasic
  - Meta
products_models:
  - PyTorch
  - Caffe2
  - GPT-4
  - Llama-3
media_books: []
status: evergreen
---
### 嘉宾介绍与活动开场

**主持人**: 大家好，欢迎来到由 **Stasic** 赞助的 AB Talk。Stasic 是一个为产品开发设计的现代数据平台，提供功能开关、实验和分析等核心工具。我们为许多 AI 公司（如 **OpenAI**、**Anthropic** 和 **Character.AI**）提供服务，因此我们希望从 AI 社区学习生成式 AI 时代产品开发的最佳实践。

今晚我们很荣幸邀请到了 **Hou**、**Jason**、**Yangqin (贾扬清)** 和 **Jay**。简单介绍一下，**Hou** 是硅谷的技术老兵，曾创办了 **WiW's** 的网络部门（现为数十亿美元业务），也曾在 **Greylock Partners** 担任驻点企业家，并在斯坦福授课。他最近创办了 YouTube 频道《Fight into Future》。

接下来是 **Yangqin (贾扬清)**，**Lepton AI** 的创始人兼 CEO。他曾是阿里巴巴副总裁和 Facebook（Meta）的 AI 基础设施总监。在伯克利期间他开发了 **Caffe**，后来领导了 **PyTorch** 的开发，这已成为最流行的机器学习框架。

**Jason** 是 **Martian** 的创始工程师，这是一家快速增长的 **LLM Router (大模型路由器)** 公司，旨在为任务选择最佳的 AI 解决方案。他曾在芝加哥大学的人机 AI 实验室和字节跳动进行研究，并领导着湾区最大的 AI 社区之一。

最后是 **Jay**，**Opus Clip** 的联合创始人兼 CTO。他的初创公司在 2023 年转型为 AI 视频剪辑产品，不到一年时间，年度经常性收入 (ARR) 就达到了 **1500 万美元**，增长速度惊人。

<details>
<summary>Original English</summary>

**Host**: Hi everyone, we're going to get started. Welcome to AB talk. This event is sponsored by our company, Stasic. Stasic is a modern data platform for product development and we offer essential tools such as feature gates, experimentation, and analytics. Stasic is hosting this event because we provide services to a lot of AI companies such as OpenAI, Anthropic, and Character.AI, so we want to learn from the AI community about the best practices in product development in the GenAI era.

Let me do a quick intro about our speakers tonight. First, **Hou** is a technology veteran in Silicon Valley with a career that began by founding WiW's Network division. His diverse experience spans founding startups, holding executive positions, serving as an entrepreneur in residence at Greylock Partners, and mentoring at Stanford University. He recently started a YouTube channel called "Fight into Future."

Next, I'm pleased to introduce **Yangqin (Jia Yangqing)**, the founder and CEO of **Lepton AI**. Prior to Lepton, Yangqin was a vice president at Alibaba and the director of AI infrastructure at Facebook. There he created **Caffe** and **Caffe2**, and he co-led the development of **PyTorch**, which has become the most popular machine learning framework.

Next, we have **Jason**, the founding engineer at **Martian**, a fast-growing **LLM router**. Martian router is about selecting the best AI solution for our tasks. Before Martian, Jason did research at Chicago Human+AI Lab and ByteDance. He leads one of the largest AI communities in the Bay Area.

And the last one, **Jay**, the co-founder and CTO of **Opus Clip**. His startup pivoted to the current AI video clipping product in 2023. In less than a year, Opus Clip is reaching **15 million annual recurring revenue (ARR)** and is growing fast.

</details>

---

### 生成式 AI 产品开发的根本差异

**主持人**: 第一个问题给 Jay。开发生成式 AI 产品是否具有根本性的不同？

**Jay**: 确实有些事情变了，有些没变。不变的是你仍然需要深度理解用户需求，参考 **待办任务 (Jobs to Be Done)** 理论。设计和营销依然重要，很多人认为 AI 应用只需要一个类似 ChatGPT 的对话框，不需要设计，这在我的产品中是完全错误的。

不同之处在于，用户的**容忍度**通常更高，因为他们知道这是新技术，能带来巨大的生产力，所以能接受一些 Bug。但**成本**是一个巨大的挑战，我们最初处理每个用户的成本极高，如果不努力通过工程手段降低成本，我们基本上是在给 OpenAI 打工。此外，**提示词工程 (Prompt Engineering)** 成了新事物，它改变了协作方式。以前你需要硬核的 AI 研究员来训练模型，现在你需要产品经理或运营人员与 AI 工程师合作来调试提示词。

**Hou**: 我认为与上一代软件非常不同。对于企业软件来说，**精确性、正确性和可预测性**至关重要，而生成式 AI 应用几乎没有“可重现性”。如果模型 100 次里对 99 次，你还是得思考那错误的一百分之一。你必须限制输入和输出空间，让结果比原始 API 更可预测。

**QA (质量保证)** 也完全变了。在传统软件中，你可以测试“开心路径”和极端情况（如零或负数）。如果软件对 5、6、8 是正确的，它对 10、11 可能也是对的。但在生成式 AI 中，增加一个字符，输出可能就完全不同。我们需要重新思考企业软件的 QA 意味着什么。这也是为什么许多企业级应用还停留在实验阶段，因为在生产环境中保持一致性太难了。

**贾扬清**: 我用数学的方式总结一下。计算机科学过去是关于如何从模糊的需求（Sloppy input）快速进入一个逻辑世界（代码、JSON、API）。现在，AI 变成了一个黑盒，输出也变得随机（Sloppy output）。

这导致了两个趋势：一是我们开始在“模糊输入、模糊输出”的情况下构建应用，比如聊天机器人或生成式搜索。二是我们试图利用新技术回归逻辑世界，比如**代码生成**或 **Text-to-SQL**。这就是为什么我们看到很多工作在给大模型“戴上手铐”，比如要求 **JSON 输出**或 **Function Call**，因为我们底层仍然需要那个确定性的逻辑世界。

**Jason**: 我想补充两点。第一是**边际成本**的差异。传统软件的成本随用量增加是亚线性（Sublinear）的，买台 100 美元的服务器，服务 100 人或 1000 人成本几乎一样。但调用 GPT-4，一次 10 美分，两次 20 美分，是线性函数。这使得客户对价格非常敏感。

第二是**网络效应**。在 Google 或 Facebook，更多人用，推荐引擎就更强。但在使用 OpenAI API 时，你很难用自己的数据来提升你调用的 API 的性能。初创公司需要思考长期来看，真正的护城河在哪里。

<details>
<summary>Original English</summary>

**Jay**: Some things change, some stay the same. You still need to understand deeply what the user needs, refer to theorems such as **Jobs to Be Done**. Also design and marketing is still very important. People might think we just need a line of input like ChatGPT and you don't need design—that's pretty much wrong.

Of course, there are things that are different. User tolerance is typically higher compared to incumbent spaces. But cost can be a lot of concern. We started by having 5x or 10x more cost per processing power in the beginning and we tried really hard to bring it down, otherwise we would just be working for OpenAI basically. Something that is very different is **Prompt Engineering** becomes a thing. Before you might have research engineers, now you need people who can write prompts—could be PMs or Ops people working with your AI engineers.

**Hou**: I think it's very different from the last generation. For enterprise software, precision and correctness are very important. The predictability and reproducibility is very important, and there's no reproducibility with GenAI. You have to rethink how you do it. You limit the input space and output space to make the result a lot more predictable. QA is another aspect. In traditional software, you sort of do a happy path and then figure out some corner cases. But in generative, it's unclear to me if I add one character, maybe the output is totally different.

**Yangqin**: In the old days computer science is all about going from the sloppy input (our abstract needs) into a logical world (code, JSON, APIs). Now suddenly this whole thing changed with ChatGPT. You find that this AI has become a black box and gives some sort of sloppy random output. Basically two things started emerging: one is building applications on top of the sloppy input/sloppy output situation. The second thing is we are starting to solidify the old way but using the technology—we still want to go from a sloppy world to a fixed logical world, like code generation or language-to-SQL. That's why we see a lot of work putting "handcuffs" on LLMs like JSON output and function calls.

**Jason**: The first is the difference in **marginal cost**. In traditional software, the cost is a sublinear function of usage. But for LLM, it's a linear function—call GPT-4 one time is 10 cents, two times is 20 cents. Another thing is to what extent AI applications can have **network effects**. For someone using OpenAI API, it's very hard for you to use your own data to improve the performance of the AI API you're calling.

</details>

---

### 成本优化与 AI 供应链策略

**主持人**: 关于成本，Jay 提到了规模经济。贾扬清作为基础设施专家，你们有什么洞察来把成本曲线从线性变为亚线性？

**Jay**: 我们的方式类似于特斯拉。从昂贵的 Model S 开始，然后通过优化供应链和技术开发 Model 3 来降低成本。在 AI 领域，开始时用量低，OpenAI 不会给你折扣。随着规模扩大，你可以获得供应商的 **预留吞吐量 (Provisioned Throughput)** 折扣（5% 到 50% 不等）。此外，我们还聘请了音视频专家重写了 FFMPEG 代码，在渲染流水线上节省了 60% 到 80% 的成本。

**贾扬清**: 我不太担心成本。AI 供应链遵循一个简单规则：**可预测性换取低价**。就像去星巴克，你随机点一杯拿铁是 5 美元。但如果你告诉星巴克，未来一年每天早上 9 点我都要 100 杯咖啡送到公司，你会得到很大的折扣。目前的 AI 应用大多处于“随机零售”阶段，当采用度成熟、流量稳定后，供应链的常规智慧就会发挥作用，价格会大幅下降。

**Jason**: 没错。除了需求聚合，**智能路由 (Smart Routing)** 也是关键。比如数学应用中，90% 的问题很简单，GPT-3.5 就能处理，只有 10% 需要 GPT-4。GPT-4 比 3.5 贵 30 倍。通过自动识别问题的难度并路由到不同的模型，我们可以节省 85% 的成本。

**贾扬清**: 这就像医疗系统。你感冒了不会直接找专家，而是先找全科医生（Family Doctor）。全科医生做初步分析和路由，简单的开点阿司匹林，复杂的才转给专家。这在 AI 领域同样适用。

<details>
<summary>Original English</summary>

**Jay**: The way to look at optimizing the cost is basically the same as Tesla. They started out by building an expensive car and then optimized the supply chain to drive the cost down. OpenAI has a product called **Provisioned Throughput** where they give you a discount (5% up to 50%). In my case, I hired a superstar in audio/video engineering and he wrote code to replace my gigantic FFMPEG code and saved 60 to 80% during the rendering pipeline.

**Yangqin**: I'm not particularly worried about cost. There's one simple rule in supply chain: **predictability is rewarded with a lower price**. If you tell Starbucks for the next whole year every morning at 9 a.m. I'm going to be asking for 100 cups of coffee, you will be getting a very good discount. Conventional wisdom of supply chain just kicks in and price is going to be significantly dropping down.

**Jason**: Aggregating retail demand is one big problem, but we have another **smart routing** logic. Let's say 90% of the math problems are simple, it can be answered by GPT-3.5, and 10% are hard. GPT-4 is 30 times more expensive. For each new prompt, we automatically recognize whether it's a hard or easy problem. We can save 85% of the cost.

</details>

---

### 中心化与去中心化的博弈

**主持人**: 生成式 AI 会是中心化的还是去中心化的？计算历史似乎总是从中心化到分布式再回到中心化。

**Hou**: 过去 60 年，我们经历了从 IBM 大型机到 PC，再到云端的钟摆摆动。现在 Sam Altman 会告诉你，你们不需要折腾，直接用 OpenAI API 就行了。在很多情况下这可能是对的，但对于某些客户，他们绝不会交出数据，所以需要自己的模型。

历史总是在寻找“创新瓶颈”。当某人垄断一切时，人类的天性会让创新在别处爆发。我认为会有很多模型运行在边缘端（手机或 PC），因为 OpenAI 不可能涵盖所有用例。但在某个点，我们会意识到管理这么多模型太疯狂了，于是又会回到中心化。

**贾扬清**: 在 TOC（消费者）端，人们通常很懒，愿意付 20 美元直接用 ChatGPT。但在 TOB（企业）端，情况是高度去中心化的。没有所谓的“企业搜索领域的 Google”，只有各种各样的企业搜索解决方案。企业级 AI 也会如此，不仅有不同的提供商，还有各种内部构建的能力。Lepton AI 的目标就是帮助这些去中心化的需求能够顺畅运行。

**Jason**: 决定行业终态的是**规模经济**。Google 垄断搜索是因为更多人用，搜索就更强，这是经典的网络效应。早期我觉得 OpenAI 可能会吃掉全球 95% 的 GDP，但现在我发现训练技术变得更高效了，OpenAI 无法垄断所有的创意。比如 **Llama-3** 只有 80 亿参数，却比以前的大模型强得多。

此外，**AGI (通用人工智能)** 不可能由 OpenAI 一家建成，因为它需要具体的**上下文 (Context)** 和特定领域的知识。就像一个天才大学毕业生，他很聪明，但如果不了解公司的内部规则和人际关系，他也无法直接上手工作。未来的最佳方案不是最先进的底座模型，而是**复合 AI 系统 (Compound AI Systems)**，即在模型之上构建的代理 (Agents) 和推理链。这个过程本质上是去中心化的。

<details>
<summary>Original English</summary>

**Hou**: In computation history, we went from IBM mainframe to PC and then to the cloud—a pendulum swing. Sam Altman's argument is: just use OpenAI API, you don't need to have your own model. But for some customers, there's no way they give you the data. Innovation will happen somewhere else. I feel it's going to be a pendulum back and forth.

**Yangqin**: Centralization and decentralization could be discussed on a different dimension. In the TOC world, it's very centralized—it's Google. In the TOB world, it's massively decentralized. We actually don't have the "Google of Enterprise Search." I believe TOB world things are going to be massively decentralized.

**Jason**: What determines the end state of industry is the **economy of scale**. Llama-3 8B is a good example—it's way better than many previous models and it's not being produced by OpenAI. There's a declining marginal return in putting more compute and resource. Also, AGI requires context and specific knowledge to be useful in specific scenarios. The best results are not delivered by the latest cutting-edge foundation model but rather the **Compound AI Systems** (agents, chain of thought) built on top. That process will be decentralized.

</details>

---

### AI 时代的评估 (Evaluation) 与质量控制 (QA)

**观众问**: 很多公司正在尝试利用生成式 AI 赋能业务，但从原型到真实业务价值之间还有很大差距。你们认为哪些关键组件是必须做对的？

**Jay**: 最重要的是理解用户的真实痛点。不要拿着一个闪亮的新锤子（AI）去找钉子。去读读《创新者的窘境》或《待办任务》这类书。

**Jason**: 从工程实践来看，**评估 (Evaluation)** 是最重要的。很多公司甚至不知道如何评估他们的 AI 用例就直接上手。评估大模型就像评估人类一样难，我们需要一致且鲁棒的指标。在 Martian，我们结合了人工标注、机器辅助标注和自动化评估。

**Jay**: 我们现在大量使用 **“AI 评估 AI”**。比如我们要从 100 个候选视频片段中选出最好的 20%，我们不是靠神奇的提示词，而是用 GPT-3.5 这种便宜的模型，从多个维度（如开头是否吸引人、是否有故事性、是否有缺陷）对片段进行打分。这就像农场卖草莓，好的卖给超市，差的扔掉，中等的送去二线杂货店。

但要注意，AI 有时也看不出猫腻。我在 Twitter 上发过一个案例：一个 AI 生成的工匠图像，人头和脖子明显是断开的，但 GPT-4、Gemini 和 Claude 都说图像很正常。所以你不能 100% 依赖它，但它是一个很有帮助的框架。

**贾扬清**: 最后补充一点关于**数值稳定性**。分布式训练中，即便输入和参数固定，输出也可能有巨大差异，这让开发者很难调试。这在数值计算（HPC）领域其实是老问题了，AI 社区有时候表现得像个宠坏的孩子，不愿意去看现有的解决方案。我们需要接受这个世界已经变了：**AI 天生就是统计学的**，不再是“固定输入得到固定输出”的 API 世界。我们需要在这些统计性工具周围建立安全护栏。

<details>
<summary>Original English</summary>

**Jason**: **Evaluation** is probably the first and the foremost important thing. Evaluation for GenAI is very difficult—it's similar to how we evaluate humans. We need a consistent, robust metric. At Martian, we have a combination of the human annotation, machine-assisted annotation, and automated evaluation.

**Jay**: We outpace our competitors because we use AI to evaluate AI. We use GPT-3.5 (stupid but cheap) to evaluate the quality of clips with multiple dimensions (is it interesting, does it have defects like sudden ending). We rank the candidates and only pick the 20%.

**Yangqin**: Numerical stability is a very important thing. This is not a new problem; the scientific computation or HPC world already knows that when you are doing numerical computation, things are just not possible to reproduce. AI is naturally just statistical—it's no longer the world of fixed input and fixed output. We just need to accept it and build security fences around those things.

</details>