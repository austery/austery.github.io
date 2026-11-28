---
author: AI Engineer
date: '2026-07-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ITMXwI6QL6A
speaker: AI Engineer
tags:
  - forward-deployed-engineering
  - ai-agent
  - enterprise-software
  - workflow-automation
  - scoping-methodology
title: 始终界定，用 Token 规模化：Ramp 的前沿部署工程实践
summary: 来自 Ramp 的工程总监 Leo Mehr 分享了前沿部署工程（Forward Deployed Engineering, FDE）在 Ramp 的核心定位与两大指导原则：始终进行需求界定（Always be scoping）与利用 Token 实施规模化（Scale with tokens）。通过将 FDE 融入研发组织、利用 AI 代理重构全生命周期的工作流，Ramp 展示了如何在服务大型企业客户的同时实现人效与产出的指数级增长。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Ramp
  - SAP
  - Notion
products_models: []
media_books: []
status: evergreen
---
### 《重构 FDE 定位：服务大客户的研发先锋》

在科技行业中，**前沿部署工程师**（Forward Deployed Engineer: 缩写为 FDE，直接面向客户并解决定制化与交付痛点的工程师）这一角色的定义常常被误解。许多人错误地将其视为技术支持或技术销售岗位的“终极形态”或“大 Boss 模式”，认为其核心工作就是对客户的所有需求盲目说“是”。然而，在 **Ramp**（Ramp: 美国金融科技独角兽企业，提供企业费用管理及发卡服务），FDE 团队被直接置于研发组织内部。我们的目标并非无底线地迎合客户，而是通过深入核心产品开发以及构建全新的**智能代理功能**（Agentic Features），帮助 Ramp 攻克高端市场（Upmarket），服务好我们最大的企业客户。FDE 必须保持卓越的工程品味与判断力，在深入客户场景的同时，坚持构建高质量、可复用的软件系统。

段落之间必须包含逻辑衔接句。在确立了 FDE 作为研发组织内部大客户突破先锋的定位后，我们在日常实践中总结出了两条最核心的指导原则，其中第一条便是如何通过科学的“需求界定”来避免陷入定制化开发的泥潭。

<details>
<summary>Original English Source</summary>
>> Awesome. Thank you, guys. Awesome. It's great to meet everyone. I mean, I hope that after the talk, you know, if you want to come out and we can chat, we'd love to. Um Cool. So, yeah, today my goal is to share with you guys the two most important principles from what we learned doing FDE at Ramp. So, just yeah, briefly a little bit about myself. Yeah, I'm a director of engineering at Ramp. Uh I joined the company 2 and 1/2 years ago when it was just you know, FDE was just two engineers at the time. And today, my org is about 30 engineers across four deployed developer API and our new AI services um business. So, I know this is kind of a running theme, but like no one knows what FDE is. So, I'm just going to spend a moment on that. So, yeah, I I I actually kind of like this meme. It's To me, it's kind of funny. Um I um but I I I actually think it's like totally wrong. I don't see this as the actual like true form of what FDE is. Um I don't see it as like the final evolution or like boss mode of technical go-to-market roles. Um now, this might be true at some companies, but at least at Ramp, it's a little bit different. So, FDE at Ramp, uh we live within the engineering organization. And our goal is to help Ramp win upmarket. So, with that in mind, what we do is we basically work on the core product and our new agentic features and make them work really well for our largest enterprise customers. So, that's just a little bit of intro context. I want to dig in and and today, like I said, there's just two things I'm going to share with you. Literally two things. Very easy talk. And these are the principles that I would say have really guided us and I would say probably the two most important things that we have. Always be scoping and scale with tokens. So, let's get with start with the first one. On scoping.
</details>

### 《始终界定需求：拒绝盲目逢迎的“火箭马”谬误》

FDE 面临的最大陷阱是成为盲目说“是”的应声虫。如果对客户的每一项定制化要求都全盘接受，我们最终构建出来的不会是像旧金山街头平稳运行的 **Waymo** 自动驾驶汽车那样优雅的系统，而会是一个给马腿上绑火箭的畸形怪胎。在 Ramp，经常会有销售代表在周五晚上跑来紧急求助，声称某个极其关键的战略客户只有在我们开发出 **SAP S/4HANA**（SAP S/4HANA: 德国软件巨头 SAP 的下一代智能企业 ERP 系统）集成方案的情况下才会签约。常规的研发反应是立刻去翻阅厚重的集成文档，但一个合格的 FDE 应该停下来思考：究竟是什么在推动这种紧迫性？是客户的真实痛点，还是销售代表为了在季度末冲业绩？我们需要穷尽一切替代方案，明确是否有临时手动工作流可以兜底，或者客户自身是否有技术资源可以直接对接我们的 **API**。更重要的是，FDE 必须超越这一个孤立的需求，评估是否有其他潜在客户也能从中受益，从而在更宏观的层面上做正确的研发决策。

段落之间必须包含逻辑衔接句。这种需求界定能力往往需要在失败的实操中汲取痛苦教训，正如我们早期在移动端重构过程中所经历的认知断层。

<details>
<summary>Original English Source</summary>
So, I would say there's this thing where like people many many people think that as an FDE, your job is to just say yes to the customer. But that's wrong. If you were just to say yes, you know, instead of like beautiful Waymos that we have driving us around in San Francisco, you'd have something like this, you know. Yeah, horses with like rockets strapped to their legs. And the point is you you want to help the customer be successful. You want to try to figure out a way to say yes. But you actually want to deliver good software. You need to build the right thing. So, you don't just endlessly say yes to people. And I I do want to share an example of something that I would say happens somewhat regularly in one form or another at Ramp. So, it's Friday night and an enterprise sales rep comes to us with an urgent request that this super important strategic logo is only going to close if we build out an SAP S/4HANA integration. And I think that the default engineering reflex is like, "Shit. Like, where are the SAP API docs? Like, where do I find them and how do I build this integration?" But what an what a well-trained FDE would do is like pause for a second and say, "Okay. First of all, like, what's driving the urgency here?" Like, one thing I've seen is I've seen sales reps who like go kind of crazy because it's like the end of the quarter and they're trying to hit their quota and close the deal and not because the customer is the one driving the urgency. So, that's like one example. But, you know, as an FDE, you're asking tons of questions to gather context about what's important um and what actually is the right thing to build. And so, you might ask like, "Who's using this integration? Have we exhausted all the different workarounds? Is there something manual that we can do in the meantime? Does the customer have like technical resources? Can they hit our API such that we don't have to build this thing?" But, I'd say the most important thing that an FDE does is also looks beyond this one request and looks at the other prospects that are coming down the pipeline and other customers to see if anyone else would benefit from this as well. And the point is that by gaining all this context, you can do a better job of building the right thing.
</details>

### 《从阵营错配到深度验证：移动端开发的血泪教训》

在 Ramp 成立初期，我们曾为一个大型企业客户的移动端报销需求付出了惨痛的代价。当时，我们的移动团队开发资源极度紧张，因此 FDE 决定卷起袖子亲自下场。我们派出了两位工程师从零开始学习 **iOS** 和 **Android** 开发。经历了数周的挑灯夜战与高强度攻坚后，我们兴奋地完成了双平台的开发工作。然而，当去向客户索要 Android 版的测试用户名单时，对方却冷冷地告知我们，公司有严格的安全规定，强制要求所有员工只能使用 iOS 设备。这次极具戏剧性的阵营错配让我们深刻认识到，即使是像“客户使用的是哪种手机系统”这样最基本的前提假设，也必须在立项前通过严密的**需求界定**（Scoping: 在开发前明确产品边界与技术约束的过程）进行验证。

段落之间必须包含逻辑衔接句。即便将“始终界定需求”视作圭臬，但在如今大模型能力爆发的时代，单纯依赖人力的传统开发模式依然无法应对海量增长的定制化诉求，这促使我们必须转向第二条黄金法则：用 Token 实施规模化。

<details>
<summary>Original English Source</summary>
So, I want to share another story that was really really painful for us in the early days. We had this large enterprise customer and they needed this reimbursement feature on mobile. Unfortunately, our mobile team was totally swamped. So, we basically just had to roll up our sleeves as FDEs and just get find out a way to get things done. And we had two of the engineers on the team just like learn how to do iOS and Android development. And it was awesome. We were super excited. We're like, "Okay, we're going to ship this feature. It's going to be so good. Like, hell yeah." So, we grinded for a couple weeks, got the feature done on both platforms. And we go to the customer and we're like, "Awesome. Like, can you send us your list of, you know, beta users for Android?" And that's when they told us they only they they they require they mandate all of their employees to use iOS devices. So, you're like, what the [ __ ] Like not not to the customer, you know, just internally. But like obviously it was super disappointing for us because we'd put all this effort in. And so, it was a a big lesson for us to remember the importance of scoping. Even some of the most basic assumptions like which you know mobile platform you build on it's it's super important um to validate them and and thus kind of emphasizes the importance of scoping up front. Now, Okay, so let's say that you and your team have become masters of scoping. You know, you're you're amazing. In today's world, this is not enough. So, unless you are scaling with model capabilities, you are going to fall behind. Now, I'm not going to belabor this point too much. I think like every talk in this uh in in this conference is probably some flavor of this, but like the point is that we basically have to reinvent our jobs constantly now. So, whatever work we are doing today, you know, for the most part it's knowledge work, we have to figure out how to have models and agents do it for us. And so, that brings me to the second half of this talk and the the other point that I want to convey today, which is all of us have to figure out how to scale with tokens.
</details>

### 《构建 AI 代理工厂：从需求阻塞到秒级自动化》

在知识工作不断被重塑的当下，如果不能利用模型能力进行升级，就注定会被淘汰。对于 FDE 而言，**用 Token 规模化**（Scale with tokens: 利用 AI 模型计算力与上下文处理能力来替代人力产出的研发范式）意味着对“获取背景、需求界定、撰写技术设计文档（Spec: 详细阐述功能实现方案的规格说明书）、功能实现”这一整条交付管线进行代理化（Agentic Transformation）改造。在 Ramp，我们有一个名为 `FDE Requests` 的 Slack 频道，专门收集客户经理解锁大客户时提出的各种阻塞性技术需求。以往，大客户的定制请求撰写水平参差不齐，有的只有简短的一句话，有的则很冗长，都需要 FDE 人工去梳理和对齐。为了提高人效，我们使用 **Notion 代理**（Notion Agents）构建了第一代自动化工具，通过预设的提示词与流程，自动向需求提交人进行多轮的追问与澄清，直到信息完整并可以直接生成技术文档。这一变革让客户的反馈延迟从“小时或天级”缩短到了“秒级”，直接为 FDE 团队节省了超过 20% 的需求界定时间。

段落之间必须包含逻辑衔接句。这种以 AI 代理自动化界定需求的方式，不仅极大地解放了工程师的生产力，更是我们探索下一代 FDE 代理化开发工厂的核心起点。

<details>
<summary>Original English Source</summary>
And the way that I interpret scaling with tokens for FDE is take a look at the whole life cycle of what an FDE does. From gathering context to scoping out a request to writing out a spec and then implementing the feature, each stage of that pipeline can be replaced with agents. And at first it seems kind of daunting. You're like, like how are you going to go and approach and like solve that? But if you break the problem down and then make progress on it, it's it's actually pretty tractable. And so, I'll share share with you guys one example of something Oops. Something that we um that we've done at Ramp. So, we have this internal Slack channel called FDE requests, and this is where account managers, solutions, uh sales reps will post whenever there is a blocker for a prospect or customer that's large enough, basically. And so, we get these requests. In this case, actually uh one of the CSMs on our team, Greg, posted here. And um if you were to It's actually a Notion workflow. If any of you work at Notion, by the way, thank you. We like use Notion so much. Um if you were to click open in Notion, you'd see like a pretty long request that has all the details of what what exactly it is. And the problem is there's a super high variance. Like, some people will submit like really detailed, good requests from the customer. And others are just going to submit like one line, like, "We need uh you know, we need this SAP integration." And before what would happen is we would have FDEs manually kind of go through this request. We'd read the whole thing, understand it, figure out what exists in the product, do a bunch of back and forth with the customer. And this is like exactly what the first half of the talk was about, always be scoping. You know, we would spend a lot of time really digging in and validating what exactly was uh you know, absolutely necessary. And so, you can see here what we what we did then was we basically um used Notion uh Notion agents to build a V1, which literally just took the request and asked a couple of questions. That was it. And um after It was kind of astonishing. Literally, after a couple of weeks, we found that it was like saving us a lot of time because, first of all, immediate like the latency of replies went from like hours or days to like, you know, seconds. And immediately, like the account reps that the account managers, the reps would start kind of engaging with this agent. And one of the things that we did was because it went so well, this this is actually um the more recent iteration of it. It's very cute, you know, the little penguin actually helps make it seem a little more friendly and approachable. Um and what it does is it actually goes and does several rounds of back and forth questioning with the submitter until it deems that it's ready to create a lot a spec, basically. And it's actually been incredible how helpful this has been for us. I I would say it's probably saved us like a large percentage, I don't know, 20% of the time that we'd spend on scoping out these requests.
</details>

### 《迈向自主交付：评估、上下文与人类判断的融合》

需求界定的智能化只是构建“交付工厂”的第一步。目前在管线的末端，将一份界定清晰的技术文档转化为可工作的代码，对于目前的主流前沿模型（Frontier Models）而言，已经能够实现中等复杂度功能的一次性生成（One-shot Generation）。我们工作的核心痛点集中在最复杂、无序且难以塑形的中间地带：如何将大量的历史数据、产品细节以及产品经理（Product Manager: 缩写为 PM）脑海中的业务默会知识有效地沉淀为 AI 代理的**上下文**（Context）。这需要我们持续在开发工厂中投资，设计更精细的**评估标准**（Evals: 自动评测大模型输出质量的指标和用例集合）、系统化的考核标准（Rubrics）以及合理的人类反馈闭环。展望未来 6 到 12 个月，FDE 的日常工作将转型为维护和调优这一整条代理化流水线，而工程师最核心的价值将体现在对系统最终输出结果的**工程品味与判断力**。

段落之间必须包含逻辑衔接句。通过将极具远见的需求界定眼光与先进的 Token 规模化架构相结合，FDE 将在 AI 时代释放出远超以往的技术红利。

<details>
<summary>Original English Source</summary>
So, you know, this is this is a great example. For us, this has been really helpful. It's I'm super excited about this. It's going to help automate a lot of the work that we've been doing manually. But, um it's really just the first stage of this pipeline that I was alluding to. So, if you look at the first part here, like we've been able to make some progress on it. The last step as well, going from a a well-shaped spec to like a working product, obviously like Frontier models can like one-shot medium-size features. And so, the last part is also is is a lot easier for us. It's this middle part that I would say is super like gnarly and like unformed and difficult. And I'm I'm really excited about our team kind of investing a lot more and spending a lot more of our time just like building out this factory, building out agents to replace each one of these steps. And the thing is, if you look at if I were to say 6 to 12 months from now, like what does FDE at Ramp look like? Like these are the sorts of applied AI problems that we're going to be spending all of our time on, I think. Like, you know, making sure that the agent harness that's running each of those steps is running super smoothly. Um making sure that the the output quality of each of the outputs of the the pipeline is is actually good. That you know, with with evals, with rubrics, with human feedback. Um and there's of course like one of the biggest challenges, which is getting your agent the right context, you know, when you're making the alarm call, ensuring that it has the right context. So, there's like a lot of historical data, data about the the product. Imagine like all the knowledge that a product manager has in their head about their product. Like, how do you get that into an agent? Like, Notion docs and all your existing knowledge base and help articles only give you so much of that. Um yeah, skills, memories, tools. I could go on for a bit, but ultimately the most important thing here is that as an FD, we still have the responsibility of taste and judgment over the final output. So, that's going to be like the underlying kind of throughline. Okay. So, let's say that you've done an amazing job building out this factory. But the problem isn't to tie this to the first half of the talk. If you don't do a good job of scoping out requests or or building upon the principles of scoping things well, you're going to get a token maxing slop cannon. And so, the whole point is that you have to do these both because the other way around is actually quite bad as well. If you are, you know, amazing at scoping, but don't invest in building out this, you know, agent factory, you know, it's going to be over for you. Like, uh your your agent native competitors are just going to overtake you and outcompete. And so, that's why um in the end here, I want to close with the the the most important thing is that if you have both of these, it can set you up for success in the future. Always be scoping and scaling with tokens. The future of FD needs both. That's all. Thank you, guys. >> [applause] [music]
</details>