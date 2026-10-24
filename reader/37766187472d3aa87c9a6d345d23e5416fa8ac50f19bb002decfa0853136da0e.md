---
author: The Knowledge Project Podcast
date: '2026-05-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=QDYf0Xq-z4Q
speaker: The Knowledge Project Podcast
tags:
  - compute-scaling
  - infrastructure-strategy
  - ai-ethics
  - resource-allocation
  - ai-policy
title: 宏伟机器：Greg Brockman 谈算力霸权、基础设施与社会公平
summary: OpenAI 联合创始人 Greg Brockman 深入探讨了数据中心的战略地位及其作为“人类最宏伟机器”的本质。他分析了算力扩展面临的物理挑战（如太空数据中心的可能性）、算力分配的伦理困境（娱乐 vs. 科研），并强调 AI 监管应致力于确保技术收益的广泛分布与经济赋权。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Greg Brockman
companies_orgs:
  - OpenAI
products_models:
  - ChatGPT
media_books: []
status: evergreen
---
### 战略先见：数据中心作为竞争护城河

OpenAI 在数据中心建设上的早期重金投入，曾经备受竞争对手嘲讽，如今却转化成了无可置疑的**算力优势**。这种投入不仅是商业层面的防御，更是为了实现其使命：将先进技术交付给每一个人。在计算资源极度匮乏的今天，这种前瞻性的布局确保了公司在模型训练与推理上的领先地位，而那些曾经持怀疑态度的竞争对手，目前在**算力**（Compute：执行 AI 模型计算所需的处理能力）获取上正面临巨大挑战。

<details>
<summary>Original English Source</summary>
You guys were teased for putting so much effort, money into data centers. How do you think that's playing out now? Well, I think it's going to give us an advantage and I think it's going to be something that's an advantage not just for the business, but for actually delivering on the mission of bringing this technology to everyone cuz you guys like you saw that way in advance. You get teased for it by almost all of your competitors. Mhm. Who's laughing now? Yeah. I mean I I think our competitors are not having a good time on compute. Let me put it that way.
</details>

### 物理极限与宏伟愿景：从地面到太空

关于未来数据中心是否会部署在太空，这在技术上是一个“宏大挑战”，主要受限于极高的**维护成本**。现代数据中心是极其精密且脆弱的巨型机器，甚至电缆过紧导致的信号完整性问题都会引发故障。目前的维护高度依赖人工，未来必须向**机器人自动化**（Robotics）转型。尽管太空环境面临散热、维护等严峻挑战，但随着人类对算力需求呈指数级增长，探索包括太空在内的所有物理空间选项已成为必然。

<details>
<summary>Original English Source</summary>
Do you think we'll have data centers in space? I think we're going to have data centers everywhere. How far away do you think we are from that? Well, data centers in space has a lot of has many technical problems associated with it. Even for example, the data centers we build today are very finicky, right? They're these massive machines with very breakable, very expensive components. We've had many issues in the past where the cables were just too taut just literally like too too tight of cables and then you get signal integrity issues and the computer doesn't work and so figuring out how do you maintain systems today it's people go in physically pull them probably will move to robotics so I think figuring out how to solve some of these technical problems are going to be very important dependencies as we think about putting them in you know people talk about putting data center in you various difficult locations. Um, space feels like a like a grand challenge, but I think that that we are going to have such need for compute that we need to be thinking about all options.
</details>

### 底层本质：人类历史上最大的单体机器

数据中心不应被视为简单的机房，它是人类创造的**最大的单体机器**。这种机器存在的终极价值在于解决对人类至关重要的难题，例如攻克癌症或辅助商业运营。未来，我们可能会看到专门为特定科研目标（如肿瘤学研究）而设计的专用数据中心。当这种庞大的计算集群全量聚焦于单一问题时，其产生的突破性机遇是人类尚未完全内化的能力。

<details>
<summary>Original English Source</summary>
Do you think data centers eventually get dedicated towards a problem like you'll have a huge data center in North Dakota and it's just on solving cancer and that's all it's doing? Yes. How far away are we from that? I think that this kind of thing happening this year is not out of the question and it's really amazing if you think about it. having this giant machine, right? And have you have you been to any of these data centers? No, I've seen them online, but never in person. It is a very different experience to walk amongst these racks, right? To walk down the the rows and you look at the cables that are all perfectly exactly the right the right length and you just realize that what a data center is, it's a massive machine. These are maybe the biggest machines that humanity creates. And then you ask the question of why. Why do we build these machines? Why is it worthwhile? And it is because they have the potential to solve problems that matter for people, right? To solve, you know, come up with cures for cancer, to help people run businesses, to, you know, sometimes maybe it's mundane queries. The purpose in my mind is really about how do you deliver value? How do you deliver on people's goals? And I think the opportunity presented by these massive machines targeting one problem is something we have not yet really internalized.
</details>

### 社会博弈：稀缺算力的分配伦理

在算力受限的现实背景下，“**算力分配**”将成为社会面临的最重要课题：是让 AI 生成娱乐性图像，还是让它去攻克疾病？OpenAI 的核心信念是坚持**算力普惠**。他们拒绝走“象牙塔模式”（即由精英控制突破，再向下分发成果），而是通过提供免费层级的 **ChatGPT**，将技术直接交付到普通人手中。这种做法不仅是为了赋权个人实现目标，更是为了让大众在技术发展的早期就能参与塑造 AI 的形态。

<details>
<summary>Original English Source</summary>
But if we're computer constraint, like how do you decide who to serve? Like why are you serving me when I'm like trying to make an image over like solving cancer? Well, this is going to be the most important question for society to answer. Where does the compute go? What problems are worthy? And there's lots of worthy problems, but you need to prioritize them because you only have so much comput. And so one thing we really believe in is that everyone is going to need access to compute. And so that's why we have a free tier of chatbt. We've really put effort into making sure that people are able to use this technology that it's widely available because we believe that is core to what we're doing here. We think that putting this technology in people's hands that empowers them that lets them achieve goals. It helps them also understand the technology, right? It's something that helps them then shape how does this technology slot in. You could take a very different approach and say, well, it's all about the ivory tower. It's all about the just solve the problem and we will then distribute the technology breakthroughs in some way. And I think there's merit to that as well, but that's not where I'd put the the balance of of what we do. I think that that is very much a like we do want to make great strides on specific problems, but I think that that should be in service again of the we want the benefits of this technology to be broadly distributed.
</details>

### 监管与未来：确保收益的广泛分配

AI **监管**（Regulation）的核心目标应是确保技术直接改善个人的日常生活。由于 AI 可能会打破原有的职业稳定假设，社会必须建立相应的支持机制。政策制定者需重点关注：如何防止经济价值过度向少数机构集中，以及如何确保每个人都能获得算力。AI 的收益不应只是抽象的宏观经济指标，而应该是让每个人都能感受到生活质量的提升，并在创业和创作上获得真正的赋权。

<details>
<summary>Original English Source</summary>
What do you think regulation for AI should look like? Well, I think that there's a number of different pieces to what regulation for AI needs to accomplish. One I think is very important is we need to ultimately ensure this technology benefits people. Like it is very clear that institutions, jobs, just life paths that people thought would be stable, those assumptions may not hold anymore. And we need to make sure that we provide support that we're all there to support each other as this technology rolls out. And so what does that mean from a regulatory perspective? I think there's a lot of ideas whether it's things like everyone should have access to compute. How do we ensure that that's true? How do we ensure that as this technology starts to generate more economic value, it doesn't acrue to just one place, right? There should be something that actually everyone is benefiting from. This technology shouldn't just abstractly benefit the economy. it's very clearly going to do. It should directly be something that people feel in their daily lives that they themselves their life is better because this technology exists because they're using it because they're able to accomplish more.
</details>

### 基础设施的真实账本：电力、水耗与误区

针对公众对数据中心资源消耗的担忧，Greg 澄清了一些常见的**错误信息**。关于电力，OpenAI 承诺通过多种机制确保数据中心不会推高民用电价。在水资源方面，公众普遍认为数据中心是“耗水大户”，但实际上现代中心采用的是**闭环冷却系统**（Closed-loop System），只需循环使用固定量的水（类似于一个游泳池的水量），实际耗水量极低。消除这些认知隔阂，对于让民众理解数据中心的社会价值至关重要。

<details>
<summary>Original English Source</summary>
And you think about things like data centers that those are something where there's clearly been a lot of concern about questions like do they drive up electricity prices and we have a commitment to ensure that they do not. And I think that each of these things can be achieved through many different mechanisms. Sometimes it's through regulation, sometimes it's through commitments from the company, and sometimes it's just through people understanding the facts. Like a good example is data centers and water usage. Like that that's something that people talk about a lot, but actually our data centers use incredibly little water, right? That's actually misinformation that they use a lot. It's less than a household, isn't it? It's it is because it's a closed loop. You basically fill up a giant like, you know, think of it as like a swimming pool of water and you just circle it around. And so it's a fixed amount of water that's not very large. But I think people really understanding the why. Why are we building these things? Why is it worthwhile? How does it benefit me? And being able to give people that empowerment, whether it's helping them feel that they can be an entrepreneur now, that they can build a business, that they can create something, like all of that we have to solve for. We have to make sure that people feel it in their daily lives.
</details>