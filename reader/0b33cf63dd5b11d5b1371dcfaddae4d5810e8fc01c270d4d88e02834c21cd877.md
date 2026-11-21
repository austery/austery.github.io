---
author: AI Engineer
date: '2026-07-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Bck7ABCZRZI
speaker: AI Engineer
tags:
  - ai-inference
  - infrastructure-design
  - cost-optimization
  - open-source
title: 停止租用认知基础设施：何时走向AI推理自建之路？
summary: 本文探讨了在生成式 AI 推理费用暴涨的背景下，企业所面临的成本与技术主权痛点。通过对 Uber、大型零售商及作者自身项目的案例分析，指出了租用 API 模式在成本控制、安全性及合规性上的局限，并提出了“租用以学习，拥有以收益”的自建基础设施抉择模型。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - Uber
  - Kalmantic Labs
products_models:
  - DGX
  - just-token-max
  - headroom
media_books:
  - 'Peak Inference: Infraeconomics of AI Inference'
status: evergreen
---
### 停止租用认知基础设施：何时走向AI推理自建之路？

在当前的生成式人工智能浪潮中，企业往往低估了**推理成本**（Inference Cost：运行训练好的 AI 模型生成预测或内容所产生的计算费用）的增长速度。美国一家大型零售商在 **Anthropic** 的推理服务上花费了近 2 亿美元后，终于因成本完全失控，转而构建了自主的基础设施。同样，**Uber** 的首席技术官（CTO）曾透露，他们原本规划了整整一年的 Token 预算，结果在第四个月就全部耗尽。对于大多数人来说，随着使用时间的推移，算力成本的累积速度远超预期。

租用云端 AI 的计费模式与传统的包月电话账单完全不同。电话账单有明确的预算锚点，而这些被租用的智能平台更像是**预付费赌场**（Prepaid Casino：需要先充值点数再进行消费的模式）。用户不断往里面充值、拉动拉杆，在沉浸于 AI 能力的同时，会不知不觉地彻底突破心理预算防线。演讲者分享了自身的真实教训：他开发了一款名为 **Ultrazone**（或 Ulta Sono：一款逆向工程音乐生成提示词的工具）的应用。该应用的功能与著名的音乐生成平台 **Suno.com** 相反——给定一首歌曲，反向推导并生成可能产出该歌曲的文本提示词。由于该工具趣味性极强，在朋友间传播后迅速吸引了数十万用户，但随之而来的是推理费用的疯狂飙升，最终迫使作者支付了高达数十万美元的账单。

<details>
<summary>Original English</summary>

One of the largest retailers in the country spent close to $200 million on inference with Anthropic and decided that things got way out of hand and built their own infrastructure. I'm pretty sure most of you have read the news from Uber CTO on how they had planned a budget of their tokens for an entire year and it got over in month four. I'm also confident that half of you in this room have come to a very similar conclusion that as time goes by the cost of intelligence really built. Using inference feels like, you know, it's one of the most inexpensive thing. But then this is very different from using a phone where you get a bill once every month and then you have like a specific set of amount that you can actually anchor your mind to. But in case of using these rented intelligence platform, they are like prepaid. You load credits. It's almost as if you're loading credits inside a casino. You put some and then you pull it and then you are so addicted to it then you end up doing more and more of it and by some time you realize that you've blown past the threshold that you had mentally kept in mind. And I had this experience myself. I built an app called Ultrazone or I experienced the inference cost ballooning here. Suno.com has anybody heard about Suno.com? Yeah, Suno.com is is this application that allows a user to turn a text prompt into music. What I was interested in is is doing the reverse which is given a particular song, what prompt could have actually generated it. This is something that I wanted. So I built this. I was having a lot of fun using this application, shared it with a few friends and spread wide around. I had hundreds of thousands of users, but then the cost ballooned way more than what I had anticipated. Hundreds of thousands of dollars I had to spend on inference.
</details>

### 代理死循环、密钥防盗与「Token工厂」的本地替代

在技术落地层面，推理成本失控通常源于以下三大诱因：
首先，开发者往往忽略了对输入 Token 进行**Token压缩**（Token Compression：通过算法减少输入文本的 Token 数量以降低开销）和上下文管理。特别是当系统进入**智能体循环**（Agent Loops：AI 代理自主调用外部 API 并不断循环迭代的运行状态）时，会产生大量极其冗余和浪费的重复调用，而第三方推理平台对开发者的实际工作负载类型完全无感知，无法进行硬件层面的优化。
其次，云端 API 依赖还带来了严重的安全隐患。例如，演讲者的 API 密钥曾被黑客盗取并用于非授权请求，导致账单在极短时间内从 7,000 美元狂飙至 10,000 美元，幸得其负责研发的联合创始人及时截断，才避免了高达 10 万美元的灾难性损失。

面对租用云端智能的弊端，许多人转向了**Token工厂**（Token Factory：提供按每秒 Token 产出计费的去中心化或自建算力模式）这一替代方案。企业无需向 **Anthropic** 或 **OpenAI** 支付昂贵的租金，而是选择将开源模型部署到云端的**新型 GPU 云服务商**（Neo Clouds：专注于 AI 计算资源提供的新型云基础设施商）或推理终点服务商。更有甚者主张完全在本地构建 Token 工厂——通过采购多块 GPU 显卡自建算力节点。演讲者受到启发，购买了一台英伟达的 **DGX** 服务器，将 Ulta Sono 从 Anthropic 平台迁移到本地的 DGX Box 上运行。尽管遇到了显存（VRAM）不足这一硬件瓶颈，但这种尝试让自建算力支撑其研究实验室的 12 个智能体代理成为了可能。

<details>
<summary>Original English</summary>

Now, this happens for many reason. There are many talks that are there at AIE itself where people talk about how you need to manage your context better. And many people forget about doing compression of their input token. And when there are agent loops, then there are many of these calls that are happening which are very, very wasteful. The inference endpoint that is consuming this is is completely unaware of the workload shape and which is why this happens. And I have this other issue that had happened. 3 weeks ago, my key got stolen. Someone in China got hold of it and then was sucking my endpoint dry. I could see the cost rise up from 7,000 to 7,500 dollars to 8,000 and going and so forth. Thanks to my co-founder who heads the research and technology, we were able to arrest it at 10,000 dollars. Otherwise, it could have been 100,000 dollars. Now, many people suggest that the alternative to rented intelligence platform is is to use token factory. Token factory is is basically saying that why are you paying money to Anthropic and OpenAI? Instead, go open source, have these open source models that are already deployed somewhere in the cloud, and then they are provisioned as tokens per second. There are neo clouds and then there are inference endpoint providers who actually do this. In fact, there is also an argument saying that, you know, you can build this token factory locally. There are AI Twitter influencers who actually talk about building inference in your garage, in your basement. Buy GPU cards, rig them up together, and then you could actually run a local token factory. In fact, I was inspired by that a little bit. I bought my own DGX box and then I first moved Ulta Sono from Anthropic to DGX box. It worked well. I ran into this one issue of memory being the bottleneck. And then, it was good enough that I started building my next applications. I started having agents. I have some agents that I need for running my research lab. So, these agents started shaping up inside the DGX box, you know, two, six, eight, 12. And it worked all right.
</details>

### 企业痛点与抉择模型：租用以学习，拥有以收益

尽管本地方案解决了资源消耗的问题，但对于企业级应用而言，第三方 API 的租用模式还面临更深层的结构性障碍。主要体现在三个典型行业案例中：
1. **投资资金**（Investment Fund）：在一套基于邮件客户端架构的投资分析系统中，他们需要处理超大规模的数据，绝不希望由第三方 API 供应商来决定自己的**速率限制**（Rate Limits：系统在特定时间内允许处理的最大请求频次），控制权是他们的核心诉求。
2. **医疗机构**（Healthcare Provider）：某医院成功试点了一款 AI 应用，但在随后的合规性审计中，因为严重的第三方厂商依赖问题被直接划了红线，项目被迫停滞。
3. **税务事务所**（Tax Practice）：税务咨询对**可复现性**（Reproducibility：对于 AI 生成的决策能够进行精确回溯和重新解释的能力）有着极高的要求。如果无法深度访问和锁定模型底层的特定参数与权重，企业就无法稳定复现前期的推荐结论。

基于这些行业壁垒，演讲者提出了判断何时从“租用”转向“自建”的决策矩阵。这正如搬迁至新城市的生活选择：起初为了探索环境，你可以选择短期租房甚至预订 Airbnb 宿处，但如果要长期安家立业、抚养家庭，你最终必须买下属于自己的房子。同样的逻辑：
* 如果是**产品市场匹配**（Product-Market Fit：产品与市场需求的契合程度）之前的初创阶段，租用 API 以快速验证想法是合理的。
* 一旦跨越 PMF 阶段，或者企业已经为项目拨出了专款预算，自建推理基础设施就成了无法规避的硬性选择。

为了解决多层级的资源管理和成本优化难题，演讲者将自身的优化经验打包进了一个名为 **just-token-max** 的开源项目中。该项目可以作为 Netflix 开源框架 **headroom** 的高性能替代方案。此外，他也将相关洞察总结在新书《**推理巅峰：AI推理的基建经济学**》（Peak Inference: Infraeconomics of AI Inference）中。在当今每三到六个月就颠覆一次规则的 AI 市场中，虽然黄仁勋（Jensen Huang）宣扬 Token 工厂是未来，萨提亚·纳德拉（Satya Nadella）主张无计量且本地化的智能，新一代云厂商则鼓吹推理端点供应商的价值，但演讲者总结出的核心逻辑依然是：**“租用以学习，拥有以收益”**（Rent to learn, own to earn）。

<details>
<summary>Original English</summary>

The issue though is is that, you know, it may not be reliable for enterprise, which is what I exactly faced. Three enterprises reached out to me to replicate the same setup for them. But for enterprises, renting and leasing don't cut it. Bill is a problem, but then there are secondary set of problems that makes it extremely ineffective approach. The enterprises that I reached out to me, one was a fund, another a hospital, and the third a tax practice. And each of them had different wall that they had hit. The fund, it was an investment fund, they were running an investment analyst on an email client architecture, and they didn't want somebody else to dictate as to what the rate limit that they could consume. So, control become a big issue for them to actually go with token factories. Hospital had a different issue. They used the use case, it worked well, but later when they went through an audit, a third-party vendor dependency was redlined, and then they couldn't go forward. The tax practice was a completely different issue. In a tax practice, what is happening is this, when an intelligent generates a recommendation, you want to be able to recreate it. And when you don't have access to the in-depth of the model, you will not be able to do this, and that became the issue. So, that brings me to the most important point of this presentation. Where do you sit? When do you stop renting infrastructure? If you're a startup, if you're a founder who is doing pre-product market fit work, so you're still figuring out that the use case that you have, if there is demand for it, you can get by by renting. But if you're post-product market fit, you cannot afford to And if you're an enterprise who's already budgeted a project, which means you're telling that you are assuming that this particular use case has product market fit, then again, you cannot ignore to build your own infrastructure. Which is what I realized, and I said that this situation is this like, if you're going to a new city, you may initially start with saying that I don't want to buy a house. Let me actually rent and see. Sometimes you might even Airbnb. You experience the environment, you experience the city, the neighborhood, but then eventually you have to buy the house. You cannot raise a family in an Airbnb. As I went through this experience, I decided I came to the conclusion that I need to build my own inference infrastructure for the apps, the agents, and the scaling of the apps that I'm building. And I call this as just infra. And while I went through this exercise, I realized that there is optimization to be done at multiple layers. Even at the renting and the lease layer, you can do optimization around input cost to token management, and then, you know, context management, and so on and so forth. Some of those experiences that I've had in the last couple of months combined it into an open-source project and published it as just token max. If you have used headroom from Netflix, then this is an alternative to it. We benchmarked against headroom and on many parameters, just token maxes is far superior. If this is a thing that is of interest to you, give it a try, maybe a GitHub star if you like it. I also wrote the book called peak inference infraeconomics of AI inference when you have to think about building your own inference infrastructure. The AI market is is very different compared to the rest of the technology market that used to exist because here the rules of the game change every three to six months, which means it becomes a very noisy marketplace. You talk to someone like Jensen, he would say token factory is the future. You hear someone like a Satya Nadella, he will say unmetered intelligence is the future, it is going to be local. And then when you hear new clouds and inference endpoint providers, they'll say, \"Hey, inference endpoint providers are the ones that are going to capture the value in the marketplace.\" Now, my experience walking from application to agents to scaling them and then building my own inference infrastructure taught me that if you want to learn, you can rent, but if you want to earn, then you have to own. And if there was the one sentence that you had to take away from this entire presentation, it is that. Rent to learn, own to earn. But then, you have to come to your own answers. Thank you. And if any of these topics are of interest to you, then I'm happy to talk to you about renting, about just token max, about how to build your own inference infrastructure. I'm here at the AI Engineer's conference for the next 3 days. Hit me up on Twitter at mtraj or through my site mtrajcom.
</details>