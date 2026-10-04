---
author: Best Partners TV
date: '2026-05-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HYrmB1rAHNw
speaker: Best Partners TV
tags:
  - ai-training
  - data-generation
  - model-capability
  - strategic-transparency
  - internal-data
title: Meta的AI训练策略：内部员工数据赋能
summary: 本文探讨了Meta利用内部高素质员工的数据（如编码和计算机操作记录）来训练AI模型，以获取行业竞争优势的策略。演讲者同时也回应了员工对设备追踪的关切，强调该数据用于模型训练而非个人监控，并指出在AI激烈竞争中平衡透明度与战略保密性的挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Meta
products_models: []
media_books: []
status: evergreen
---
### AI模型竞争的核心引擎

要理解当前**AI模型**（AI Model: 利用深度学习架构训练出的智能化系统）的发展逻辑，必须关注三个关键成分：**架构与研究**、**基础设施**（包括计算资源的数量与使用效率、可靠性、质量），以及最为核心的**数据学习**。

目前，Meta正处于通过观察高素质人才行为来优化AI能力的阶段。我们的一个核心假设是：相比于传统依赖外部**合同公司**（Contract Companies: 提供劳动力外包服务的第三方机构）生成的标注数据，公司内部人才的平均水平要高得多。通过让内部顶尖工程师在解决实际任务时留下操作数据，不仅能大幅提升AI的编码能力，还能让模型习得更高效的计算机操作逻辑。这种策略是Meta构建竞争壁垒的关键，尤其是在对手无法复制这种大规模顶尖人才库的情况下。

<details>
<summary>Original English</summary>

So, okay, let's talk about what we're doing. You know, like Alex just said, going into what makes these AI models great, right? There's basically a few key ingredients. There's getting the research and the architecture good. There's having good infrastructure which is both the quantity of compute but like as important if not more is is also just like how efficiently can you use it? How reliable is it? What like what is the the quality of that? And then the third piece which is in in some ways it's hard to say that any of these are more important than the other because they're all necessary is effectively the data and what knowledge it learns. 

So we're in a phase where basically the AI models learn from having really from watching really smart people do things. And if you're trying to get it to be able to be able to do certain capabilities, having it be able to observe really smart people doing those things is is very important. So there are a few examples of where we're trying to do this across the company because one um one basic insight and hypothesis that we have is that a lot of data generation across the field is done by these like contract companies. And Alex knows a bunch about this because he ran one before coming here, but in general, the average intelligence of the people who are at this company is significantly higher than the average set of people that you can get to do tasks if you're working through the contract through these contractors. 

So if we're trying to teach the models coding for example, then having people internally build tools that or solve tasks that help teach the model how to code, we think is going to dramatically increase our model's coding ability faster than what others in the industry have the capability to do who don't have thousands and thousands of extremely strong engineers at their company. So that's one example. 

</details>

### 数据采集与个人隐私界限

关于近期员工关心的**设备追踪**（Device Tracking: 对终端设备操作行为的记录与分析），我们需要明确其本质是训练系统而非个人监控。为了让AI系统精通计算机操作，必须观察专家是如何使用计算机的。

在实施过程中，我们并非在人工监视员工的操作内容。相关数据在采集时已被极大程度地“剥离”了敏感内容。这项工作绝对不用于绩效考核、员工监控或任何形式的追踪。其纯粹目的是获取海量的高质量操作行为数据，以教会AI模型如何像专家一样利用计算机达成目标。如果验证该策略有效，我们将将其推广至更多业务领域，持续利用内部高质量人才来训练AI系统。

<details>
<summary>Original English</summary>

Another thing that our system needs to be very good at is using computers. So the way that you get a system to be good at using computers is by having it watch really smart people use computers. So that's basically the essence of what we are trying to do here. We are rolling it out in a way that is like you know it's like we're basically we're not like actually no human or anything is looking at or watching what your what people are doing on their computers. Just the content is sort of stripped out in like as as as much as is possible. It's like none of the data is being used for like looking at what people are doing or surveillance or performance tracking or anything like that. It's purely just like we are using this to feed a very large amount of content into the AI model so that way it can learn how smart people use computers to accomplish tasks. I think that this is going to be a very big advantage if we can do it. So anyway, that's what we're trying to do. 

I think that there are going to be probably other things around the company where we basically try to enlist the fact that we have just like a very high quality set of people to teach the AI systems to do different things that we need to get them to be able to do over time. So this probably isn't the last thing like this. And I think it's this is like an interesting strategy. I think that we want to see how well it does. At this point it's somewhat of a hypothesis. Will actually be able to complete the loop to see how well these kinds of things actually improve it. If they don't, we won't do more things like it. If they do, then we'll probably do more things like it. So that's the basic thing. 

</details>

### 战略透明度与竞争保密

在AI行业史无前例的竞争背景下，如何在保障员工知情权与保护公司战略之间找到平衡，是一个极具挑战的难题。我们承认在最初的沟通方式上存在改进空间，未来会尽可能提升透明度。

然而，核心的张力在于：我们要清晰地阐述公司行为，但不能立即泄露具有**战略差异化**（Strategically Differentiating: 能够产生竞争壁垒的独有优势）的细节给竞争对手。作为一家大型公司，公开的信息极易外泄。对于那些并非定制化或核心的技术，泄露影响有限；但对于能够直接提升模型能力的AI技术，基于竞争现实，详细披露细节并不符合公司的战略利益。我们需要在动态的发展周期中，针对具体事项采取差异化的沟通策略，既要让大家理解方向，又要严格控制信息的深度，以应对这一极其复杂且动态的时期。

<details>
<summary>Original English</summary>

In terms of how we communicate about this, I mean, this stuff is tricky. I think when I was looking through the the details of this, there's like all these things that we could have done better. So, that yes, I mean yes, acknowledged and we will try to improve this. The kind of core tension on this is that we want to communicate as clearly as possible about what we're doing while not having all of the details of things that we think are going to be strategically differentiating leak immediately to the competitors. And so I think part of the challenge is like we are a pretty big company. If we post stuff publicly, it leaks. 

Some things matter more if they leak than others, right? Like if we're building something in our, you know, ad system for example or our infrastructure that's like bespoke to us and it's not something that other people are going to copy and it leaks, it's like not that big of a deal, right? Maybe it's kind of annoying. I think we know that AI is like one of the most competitive fields, right, in like probably in history. So anything that can give us that can make our the quality of our thing better is generally not something that I think it is in our strategic interest as a company to lay out the details in a lot of detail knowing the physics of the situation is that that stuff is going to leak. So I think you will have to we're just going to have to navigate that and it's going to be a little bit different on a thing by thing basis in terms of how we communicate. 

But I actually think it is like not strategically in your interest for us to communicate everything like in all the detail that we normally would on this. But I think we do need to try to make sure that we get this right. And communicate enough so that people understand what's going on. So this I think will be a continued thing that we're trying to navigate. It's part of the complexity of trying how do we navigate running the company through what is just this incredibly dynamic period. I think that there's like lots of things that I think people would like more certainty on than we have. Lots of things that people would like more details on that it's not necessarily like it's not that any it's bad for any one person to know, but it is bad if it leaks. And I don't know how we how we how we exactly navigate that. So that's the basic situation on that. 

</details>