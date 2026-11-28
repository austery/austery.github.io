---
author: The Pragmatic Engineer
date: '2026-06-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2x0eq5oDOJY
speaker: The Pragmatic Engineer
tags:
  - kubernetes-deployment
  - gitops-concept
  - roll-forward
  - ci-cd-strategy
  - feature-toggles
title: Kubernetes、GitOps与CI/CD实践中的前沿思考
summary: 本文探讨了在实际工程中关于 Kubernetes 本地部署的场景，以及 GitOps 的本质及其对团队的适用性。文章重点讨论了回滚策略（倾向于向前滚动和功能开关），并分析了人工智能对 CI/CD 流程的影响，强调 AI 与开发流程的紧密耦合关系，以及如何利用功能开关来解耦发布与部署。
insight: ''
draft: true
series: ''
category: deployment
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books:
  - The Phoenix Project
  - Radical Candor
  - Diaspora
status: evergreen
---
### Kubernetes 与本地部署

**主持人**: 这有点意思。我们总说 Kubernetes 是云原生的，但实际上很多客户用它来跑本地部署。就在前几天，我和另一个客户聊天，他们的 Kubernetes 集群是跑在研究船上的。

<details>
<summary>Original English</summary>
**Host**: It's kind of funny. You know, we talk about Kubernetes being cloud native. The reality is a lot of customers actually use Kubernetes for running on premise. I was talking to another one of our customers actually just the other day. They've got Kubernetes clusters running on research vessels.
</details>

**罗伯特**: 研究，就像...

<details>
<summary>Original English</summary>
**Robert**: Research as in like
</details>

**主持人**: 就像船一样。

<details>
<summary>Original English</summary>
**Host**: as in boats
</details>

**罗伯特**: 在海上。

<details>
<summary>Original English</summary>
**Robert**: on the ocean.
</details>

**主持人**: 他们的 Kubernetes 集群就在公海上。

<details>
<summary>Original English</summary>
**Host**: They've got Kubernetes clusters out in the open sea.
</details>

### GitOps 的本质

**主持人**: 什么是 GitOps？

<details>
<summary>Original English</summary>
**Host**: What is GitOps?
</details>

**罗伯特**: GitOps 可能并非所有团队都必需。那种有时存在的绝对主义，可能并非必要。

<details>
<summary>Original English</summary>
**Robert**: GitOps is potentially not necessary for all teams. Some of this absolutism that sometimes exists may not be necessary.
</details>

### 回滚与向前滚动

**主持人**: 我很少听到关于回滚的讨论。

<details>
<summary>Original English</summary>
**Host**: I don't hear too much chatter about roll backs.
</details>

**罗伯特**: 回滚，这总是一个敏感话题。客户会说，“是啊，我们经常回滚。”但当你问他们，如果遇到数据库结构变更怎么办，他们就会停下来，意识到他们只是运气好，从来没碰到过。你应该避免谈论回滚。永远要向前滚动。

<details>
<summary>Original English</summary>
**Robert**: Roll backs. This is always a spicy one. Customers can go, "Yeah, we roll back all the time." And then when you ask them what do you do if you've got a schema change they kind of stop and realize that it's just sheer luck that they've never run into that. You want to avoid ever talking about roll back. It's always roll forward.
</details>

### AI 对 CI/CD 的影响

**主持人**: 说到 CI/CD 系统，你看到 AI 带来了哪些变化？

<details>
<summary>Original English</summary>
**Host**: When it comes to CI/CD systems, what are you seeing changing there because of AI?
</details>

**罗伯特**: 老实说，这是房间里的大象。

<details>
<summary>Original English</summary>
**Robert**: This is the elephant in the room to be honest.
</details>

### 开场与嘉宾介绍

**主持人**: CI/CD 仍然是软件工程中最难做对的事情之一。但为什么呢？**Rob Eris** 是一位 CI/CD 专家，在这个领域工作了十多年。2010 年代初，我们是 **Skype for Web** 团队的队友，后来 Rob 在 10 年前加入了 **Octopus Deploy**，成为其首批工程师之一。在今天的节目中，我们将涵盖实践中的渐进式交付、金丝雀部署、蓝绿部署，以及为什么功能开关通常仍然是更好的选择。什么是 GitOps，为什么它不关乎 Git，以及“万物皆在 Git”的思维模式在何处失效，为什么你应该少关注回滚，多关注向前滚动，以及更多内容。如果你想获得关于 CI/CD、渐进式交付以及随着 AI 改变我们向生产环境交付代码量所带来的影响的宝贵经验，那么这期节目就是为你准备的。

<details>
<summary>Original English</summary>
**Host**: CI/CD remains one of the hardest things to get right in software engineering. But why? Rob Eris is a CI/CD expert having worked in this field for more than a decade. In the early 2010s, we were teammates on the Skype for web team and then Rob joined Octopus Deploy as one of the first engineers 10 years ago. In today's episode, we cover progressive delivery in practice, Canary deployments, blue green, and why feature toggles are often still better. What is GitOps and why it's not about Git and where the everything in Git mindset breaks down, why you should prioritize roll backs less and focus on roll forwards and many more. If you want hard-earned lessons about CI/CD, progressive delivery, and what's coming as AI changes, how much code we ship to production, then this episode is for you.
</details>

**主持人**: 很高兴你能来参加播客。

<details>
<summary>Original English</summary>
**Host**: it's awesome to have you here on the podcast.
</details>

**罗伯特**: 你好，戈。很高兴来到这里。是的，我很喜欢阿姆斯特丹。距离我们一起工作已经过去 11、12 年了。

<details>
<summary>Original English</summary>
**Robert**: Hello go. It's good to be here. Yeah, I'm loving loving Amsterdam. Yeah, it's it's been like what 11 12 years since we walked worked together.
</details>

**主持人**: 是的，我想我是在 2014 或 2015 年离开英国的。嗯，有一阵子了。

<details>
<summary>Original English</summary>
**Host**: Yeah. Yeah. I think uh 2015 2014 2015 I think I left uh UK. Um yeah, a while
</details>

**罗伯特**: 还是在 Skype 还存在的时候。我们团队不知怎么接手了 **Outlook.com** 的插件，那个插件每月有大约 4 亿用户。

<details>
<summary>Original English</summary>
**Robert**: and Skype when there was still Skype. Our team somehow inherited the outlook.com plugin which had like 400 million users per month or something like that.
</details>

**主持人**: 那个规模太疯狂了。

<details>
<summary>Original English</summary>
**Host**: It was crazy the amount of
</details>

**罗伯特**: 规模。所以这是一份有趣的工作。部署基本上就是，你每周发布一次，并且必须去参加一个 **CAB** 会议，也就是变更咨询委员会，你必须获得签字和批准。

<details>
<summary>Original English</summary>
**Robert**: scale. So this was an interesting interesting job. deployments were very much a case of, you know, you ship once a week and you have to go to a um a CAB board, you know, a change advisory board and you have to get sign off and approval.
</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>
**Host**: Yeah.
</details>

**罗伯特**: 我一直觉得这很奇怪，对吧？我们在构建这个软件。它在网络上运行。我们可以随时发布。当时它运行在 **Azure** 上。所以，我们完全可以随时推送。我们整个星期都在做这些更改，但我想，我们不得不把它们保留下来，等到我们的经理 **Abdullah** 那里。

<details>
<summary>Original English</summary>
**Robert**: And I always found that really weird, right? Like we're building this piece of software. It runs on the web. We can ship it whenever we want. It it was running on Azure at the time. And so, you know, we've got full access to push whenever we want. And we make these changes through the week, but we'd kind of have to hold them back, I guess, to Abdullah, our manager, both of our managers at the time.
</details>

**罗伯特**: 嗯，我们算是绕过了这个系统。当代码准备好时，我们会在整个星期内构建并发布它。嗯，我对我整个团队共同建立的这个流程感到非常印象深刻和自豪，对吧？我们提交代码。测试会运行好几层，它会进入预发布环境等等。然后它会发布到生产环境。

<details>
<summary>Original English</summary>
**Robert**: Um we kind of I guess worked around the system. When the the code was ready, we'd build it and ship it through through the week. Um and I was really sort of impressed and proud at this process that the whole team had kind of put together, right? Where we'd, you know, commit the code. Uh the test would run several kind of layers of testing, it would go to staging, etc. And then it would get shipped to production.
</details>

**罗伯特**: 嗯，所以我们当时算是在执行一种持续交付的形式。然后我们每周自己发布一次。嗯，我总喜欢讲这个故事，当时，当我们有一个构建版本准备好时，我们会做一种金丝雀部署。也就是，你向一小部分客户群发布。我们总是发现，作为我们测试对象的客户群是**新西兰**。所以新西兰一直是我们的金丝雀。

<details>
<summary>Original English</summary>
**Robert**: Um so we're kind of I guess executing a form of I guess you know continuous um delivery at a time. And [clears throat] we would then ship ourselves, you know, once a week. Um I kind of always like to tell this story that um at the time, you know, when when we'd have a build ready to go, you know, we we do a form of canary deployments. And so this is where you kind of roll out to a small percentage of your customer base. And we always found that the the customer base that would be our test subjects was New Zealand. So New Zealand was always our our canary.
</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>
**Host**: Yep.
</details>

**罗伯特**: 原因有很多。你知道，他们是第一个到达新日期的国家。所以，他们总是第一批被发布到新时区的。

<details>
<summary>Original English</summary>
**Robert**: A bunch of reasons for that. you know, they're in the the you know, the the first country to kind of reach this, you know, new date. So, they're always the first ones to kind of roll out into a into a time
</details>

**主持人**: 当午夜来临，就像凌晨 1 点。第一个国家就是新西兰。

<details>
<summary>Original English</summary>
**Host**: when the it comes like, you know, like midnight passes. It's like 1:00 a.m. First country is New Zealand.
</details>

**罗伯特**: 没错。正是如此。所以，第一个规模可观的国家。嗯，他们说英语，所以如果有任何错误、问题或报告，很容易理解。但是，老实说，新西兰足够小，如果我们发布了一个错误并需要快速修复，没人会真的在意。所以，抱歉了，所有正在收听的新西兰人。是的，我认为这是一个很好的例子，展示了如何使用持续交付技术，以比我们进行大版本发布时更快的速度发布代码。我想整个过程让我大开眼界，让我明白了什么是渐进式交付，什么是好的 CI/CD。是的，从那以后，我在 Skype 又待了几年，最终我和妻子决定是时候回澳大利亚了。

<details>
<summary>Original English</summary>
**Robert**: Bang. Exactly. So, the first country that's of, you know, significant size. Um, they speak English, so if there's any bugs or issues or reports, it's kind of easy to understand. But, you know, to be honest, New Zealand is small enough that no one really cared if we shipped a bug and had to fix it quickly. So sorry to all the New Zealanders listening. Yeah, I I I think that's um kind of this this good example of using um a continuous delivery technique to um you know ship the code faster than what we otherwise could have if we had these kind of big bang releases. And this whole process I guess opened my eyes to you know what what progressive delivery what good CI/CD could be. And yeah, I guess from there I spent a few years there at Skype and eventually wife and I decided it was sort of time to come home to Australia.
</details>

**主持人**: 然后回到澳大利亚后，你开始为 **Octopus Deploy** 工作。

<details>
<summary>Original English</summary>
**Host**: And then back in Australia, you went to start to work at Octopus Aloy.
</details>

**罗伯特**: 嗯，是的，我最终回来了，实际上在一个朋友那里工作了一小段时间，只是为了重新站稳脚跟。嗯，我记得他们那里在用 **Octopus Deploy**。对于那些不知道的人来说，Octopus Deploy 是一个部署工具，最初是在布里斯班构建和开发的。所以，它和布里斯班有很强的联系。

<details>
<summary>Original English</summary>
**Robert**: Uh yeah, eventually I I came back and actually um worked at a a place with a friend of mine just for a little while just to kind of get back on the feet. Um and I remember they were using Octopus Deploy there. And so Octopus Deploy for those who don't know was is um a deployment tool was built and and sort of developed originally in Brisbane. So there was a strong kind of Brisbane
</details>

**主持人**: 联系。

<details>
<summary>Original English</summary>
**Host**: attachment
</details>

**罗伯特**: 对它的联系。是的，没错。所以当我发现他们在招聘时，我想，好吧，为什么不呢？我试试看。我喜欢 CI/CD。我喜欢这个领域。我认为这个领域有很多有趣的问题。嗯，所以我申请并加入了。当时我大概是第 8 或第 9 号员工。所以，它仍然很有创业文化。当然不是硅谷那种疯狂派对和荒谬开支的创业公司，而是和我一起工作的每个人都是工程师。即使是 CEO **Paul Stovell**，他也是工程师。这就是它的起源。所以，我们一起写代码。嗯，如果有人有个想法，你会聊一聊，然后发布它。所以，我们做营销，做支持，什么都做一点。嗯，是的，显然公司从那以后发展了很多。

<details>
<summary>Original English</summary>
**Robert**: attachment to it. Yeah, that's right. So when I found out that they were hiring, I thought okay, why not? I'll give it a go. I like CIC CD. I like this space. I think there's, you know, a lot of interesting problems in this space. Um so applied and joined and um at the time I was employee I think employee number eight or nine or something like that. So it was very much still a bit of a startup culture. Definitely not startup in the sense of, you know, Silicon Valley wild parties and, you know, ridiculous spending, but startup in the sense that everyone who I worked with was an engineer. Now, even Paul Stella, CEO, he's he's an engineer. This is kind of where it started from. And so, we'd all be working on on code together. Um, you have someone had an idea, you'd have a bit of a chat about it and ship it. So, we were the marketing, we were support, we were done a bit of everything. Um, and yeah, obviously the company has grown a lot since then.
</details>

### CI/CD 的成熟度阶段

**主持人**: 公司从一开始就专注于 Octopus Deploy，他们专注于部署，对吧？我们能不能谈谈，每当我想到部署，我总是说 CI/CD，持续集成/持续交付。为什么他们专注于部署？这和持续交付是一回事吗？

<details>
<summary>Original English</summary>
**Host**: The company was focused Octopus deployed from the start they were focused on deployments right can we talk a little bit on whenever I think about deployment I always say CI/CD continuous integration continuous delivery why was there a focus on deployments and is that the same as continuous delivery
</details>

**罗伯特**: 是的，有趣。嗯，你说得对，人们经常把 CI 和 CD 混为一谈，它们要么是可互换的，要么 CI/CD 这个词本身就是个名字。

<details>
<summary>Original English</summary>
**Robert**: yeah interesting so um you're right like quite often people talk about CI and CD as this kind of interchangeable they're either interchangeable or the word is CI/CD is like the name
</details>

**主持人**: 它只是附着在自己身上。我很难想象一个没有 CI（持续集成）的 CD。

<details>
<summary>Original English</summary>
**Host**: it's just attached to itself. And it's hard for me to imagine a CD without a CI, continuous integration.
</details>

**罗伯特**: 没错。我想看待它的方式是，软件团队在从最初阶段开始的发展过程中，有多个成熟度阶段。嗯，最初是 CI，也就是持续集成。

<details>
<summary>Original English</summary>
**Robert**: That's that's right. And I guess the way to look at it is um you know, you've got sort of multiple stages of maturity of of um software teams as they kind of move on their way from um you know, initially uh CI which continuous integration. This is the idea that
</details>

**主持人**: 嗯，最初是 **YOLO**。

<details>
<summary>Original English</summary>
**Host**: well initially it's YOLO.
</details>

**罗伯特**: 最初，没错。你直接部署到生产环境或某个机器上。我们都曾在这样做过的地方工作过，那是起点。所以你说得对，YOLO 是第一阶段的。第二阶段是持续集成，这个想法是你希望持续地将你的代码变更合并到一个单一分支，并持续地对其运行测试。

<details>
<summary>Original English</summary>
**Robert**: Initially it's right initially. You just deploy to prod or SSA like machine. We've all we've all worked in places where we've done that and that that's the starting point. So you're right, yolo is the first stage. The second stage is you know continuous integration and so this is this idea where um you want to keep you know integrating merging your code changes into a single um a single branch and you want to be continually running tests against it.
</details>

**罗伯特**: 现在，持续交付是下一个阶段，我们谈论测试我们的代码，有单元测试、集成测试等等。但你还真正需要测试的是你的部署流程本身，对吧？所以持续交付就是这个想法。好的，你希望确保在任何时候，当我点击部署按钮时，我希望它能发布到生产环境，一旦我们达到这个阶段。嗯，再下一个阶段，并非所有公司都能达到，是持续部署。对吧？这个想法是，你的变更不仅被合并到一起并准备就绪，而且它们基本上也被发布到了生产环境。

<details>
<summary>Original English</summary>
**Robert**: Now continuous delivery is kind of the next stage where you know we talk about testing our code and there's you know unit test and integration tests etc. But what you also really need to test is your your deployment process itself. Right? So continuous delivery is this idea. Okay, you want to make sure that at any point in time when I click the button to deploy I want it to go to production once we kind of get to this place. Um the next stage beyond that which you know not all companies necessarily reach is uh continuous deployment. Right? And so this is the idea that not only are your your changes being merged and merged together at the same time and ready to go, but they're also being shipped to to production essentially.
</details>

**主持人**: 所以我们有的阶段是：第一 YOLO，然后是持续集成，然后是持续交付，最后是持续部署。

<details>
<summary>Original English</summary>
**Host**: So the stages we have is first yolo, then continuous integration, then continuous delivery and continuous deployment.
</details>

**罗伯特**: 没错。

<details>
<summary>Original English</summary>
**Robert**: That's right.
</details>

**主持人**: 持续交付和持续部署的区别是什么？

<details>
<summary>Original English</summary>
**Host**: What is the difference between continuous delivery and continuous deployment?
</details>

**罗伯特**: 我想最大的区别在于，你的变更是自动发布到生产环境吗？它是否在没有任何干预的情况下流动？

<details>
<summary>Original English</summary>
**Robert**: The big difference I guess is um the question of do your changes go out to production automated? does it kind of flow through without any um intervention I guess
</details>

**主持人**: 然后对于持续交付，它们会发布出去，但不一定是到生产环境，对吧？

<details>
<summary>Original English</summary>
**Host**: and then for continuous delivery they go out but not necessarily to production right
</details>

**罗伯特**: 没错，这就是为什么你会有像开发环境、测试环境或预发布环境之类的环境。嗯，现在，这个过程的某些部分可能仍然是手动的，比如你可能每周只更新一次测试环境，让测试人员可以再玩玩。嗯，但关键原则是，如果你愿意，你可以让它自动地贯穿整个过程。

<details>
<summary>Original English</summary>
**Robert**: that's right and so that's why you'll have environments like you know dev environment or testing or staging or whatever um now it's possible that you know some parts of that process may also still be manual you know maybe you only update the test environment once a week so the testers can play around with it again um but the key principle is that you you could you can kind of push it through sort of automatically the whole way through if you want
</details>

**主持人**: 哪些团队会不想做持续部署呢？因为在我看来，你希望达到持续交付，因为这样你就能获得越来越多的反馈，对吧？但然后，这是一个很好的问题，它应该立即发布出去吗？这是每个人都会问的问题，比如“它几乎准备好了，为什么我们不能直接推送到生产环境？”作为工程师，你希望尽快发布，它准备好了，对吧？现实是，它并不适合每家公司。嗯，有些公司可能仍然有审查委员会，你需要验证是否可以发布，特别是如果你在一个有很多法规和合规要求的行业，他们需要确保当它发布到生产环境时，是在正确的时间，有正确的人员在场等等。说每个人都应该采用持续部署并不一定正确。嗯，因为有时由于各种原因，这根本不可行。但如果你至少达到了那个点，你持续地看到你的变更通过所有测试，嗯，你将它提升到不同的环境，因此你也在测试流程本身。如果你只能每周点击一次按钮发布到生产环境，那也没问题。你已经完成了大部分艰苦的工作。你已经降低了风险，而这正是这个过程的意义所在，对吧？就是尽快发现痛苦。嗯，并消除任何可能出错的风险，直到最后那个点。

<details>
<summary>Original English</summary>
**Host**: and what teams would not want to do continuous deployment, right? Cuz it it seems to me continuous delivery you kind of want to get to because then you just get more and more feedback, right? But then it is a kind of a good question like should it go out immediately? This is this is the question you know everyone always sort of asks like it's almost ready to go out why can't we just push it to production put as engineers you want as soon as possible it's ready right the reality is it doesn't really suit every every every company right so um you know it may be the case that you know some some companies really do still have you know review boards where you need to validate is this good to go out um particularly if you're in an industry that has a lot of um regulation and and compliance problems problems, compliance requirements, and they need to make sure that when it does go out to production, it's it's sort of done at the right time with the right people available, etc., etc. It's not necessarily true to say that everyone should be going to continuous deployment. Um, because that's, you know, sometimes just not not viable for various reasons. But if you at least got to that point where you're sort of continually seeing your changes go through all the testing, uh, you know, you're promoting it through the different environments, which is, you know, you're therefore testing the process itself. If you can only click that button to go to production once a week or whatever, okay, that's fine. You know, you've done a lot of that hard work. You've mitigated risk, which is what a lot of this process is about, right? Is is fill the pain as soon as possible. Um, and and derisk anything that could go wrong right up until that that last point.
</details>

### Kubernetes 的崛起

**主持人**: 我知道你深入研究 CI/CD，持续集成、持续交付、持续部署。你已经做了大概 10 多年了，但当我查看 Octopus Deploy 时，我很惊讶地发现它写着“部署”。它写着“持续部署”、“持续交付”，但也写着“Kubernetes”。Kubernetes 是如何进入 CI/CD 和基础设施这个主题的？发生了什么？

<details>
<summary>Original English</summary>
**Host**: So I know you're deep into CI/CD uh where continuous integration, continuous delivery, continuous deployment. You've been doing this for like what 10 plus years now, but I was pretty surprised to see that when I checked Octopus deploy, it said deployment. It says continuous deployment, continuous delivery, but it also says Kubernetes. How has Kubernetes kind of arrived in the topic of CI/CD and in general infrastructure? What happened there?
</details>

**罗伯特**: 是的。Kubernetes 是当下的平台。如果我们退一步看，嗯，Kubernetes 出自谷歌，我想他们最初有 **Borg**，他们用它来托管和运行他们的基础设施。他们最终发布了 Kubernetes，嗯，部分原因是，我不打算假装能读懂他们的心思并确切知道为什么，但部分原因是为了帮助拉平他们和其他一些云供应商之间的竞争环境。

<details>
<summary>Original English</summary>
**Robert**: Yeah. Yeah. Kubernetes is is the the platform of of the moment. If we take a bit of a step back, uh, Kubernetes came out of, um, the, you know, Google, I guess they originally had Borg, you know, they were using it to to host and run their infrastructure. They ended up releasing Kubernetes, um, partly um, I'm not going to, you know, pretend I can read their minds and know exactly why, but, partly as a way of helping to level the playing field between them and some of the other cloud vendors.
</details>

**主持人**: 是的。所以，在 Kubernetes 之前，**AWS** 是明显的领导者。我和 **Katie Gamanji** 聊过，她来参加过播客，她在 Kubernetes 团队工作。她也推测，通过发布 Kubernetes，在 AWS 和 Google Cloud 之间迁移工作负载变得容易多了。所以，它拉平了竞争环境，现在有了一个理由去... 没错。

<details>
<summary>Original English</summary>
**Host**: Yeah. So, like before Kubernetes, AWS was a clear leader. And I I talked with Kat Co's growth who came to the podcast uh who's uh who works on the Kubernetes team. And again, she speculated that by releasing Kubernetes, it was a lot easier to to move workloads from between AWS and Google Cloud. So, it kind of leveled the playing field and now there was a reason to That's right.
</details>

**罗伯特**: 比如选择 Google Cloud 不再是一个那么大的风险，选择 Azure 也不再是那么大的风险，等等。

<details>
<summary>Original English</summary>
**Robert**: like choosing Google Cloud was no longer as big of a risk or choosing Azure was not as big a risk and so on.
</details>

**主持人**: 是的，没错。但它使得在供应商之间迁移变得简单。所以，嗯，作为这些平台之一的客户，如果你想迁移到 AWS，并且你正在使用容器，没问题。你只是把它放在一个新的地方。所以 Kubernetes 出现的时候，正是容器编排领域有很多竞争产品的时候。嗯，所以你有 **Nomad**，甚至 Docker...

<details>
<summary>Original English</summary>
**Host**: Yeah, that's right. But it kind of it made it simple to move between vendors. And so um as a as a customer of one of these um platforms, if you wanted to move to AWS and you're using containers, no problem. You're just sort of putting it in a new place. And so Kubernetes came along at the time when um there was a bunch of plays in the field for um container orchestration. Um so you know you had um you know Nomad even dock
</details>

**罗伯特**: 来自 HashiCorp。

<details>
<summary>Original English</summary>
**Robert**: from hashpform
</details>

**主持人**: 还有很多其他选择。因为 **Kelsey Hightower** 刚来过播客，他们构建了 **Fleet**，这是另一个容器编排工具，这一切都发生在 2012、2013、2014 年左右，然后 Kubernetes 出现了，不知何故它开始赢得市场份额。

<details>
<summary>Original English</summary>
**Host**: a bunch of other options are out there because at core o Kelsey high tower was just on the on the podcast they they built fleet which was another container orchestration and this was all around like 20 2012 2013 2014 and then Kubernetes came out and somehow it started to win market share.
</details>

**罗伯特**: 是的。我认为它提供的一些机制非常吸引工程师和 DevOps 团队，最终，特别是因为它非常易于跨平台使用，并且因为一些云供应商最终采用了它，它现在基本上已经成为这个领域的赢家。我知道即使在那个时候，甚至像 **Azure Service Fabric** 这样的非容器编排工具，也是另一种处理这个事实的尝试，即每个人都在构建微服务，他们希望将它们托管在一个单一平台上，以及如何编排它并处理依赖关系等等。嗯，但 Kubernetes 已经成为明确的赢家。

<details>
<summary>Original English</summary>
**Robert**: Yeah. Yeah. Yeah, I mean they I think the the um some of the um mechanics that it provided um kind of really appealed to to engineers and and I guess DevOps teams out there and eventually I think particularly because it was so easy to um use crossplatform and because some of the cloud vendors then did end up picking it up it kind of has ended up now being essentially the winner in this space. I know even back then even non-container orchestration tools like um Azure service fabric was another kind of attempt to to handle the the fact that you know this world everyone's building microservices and they want to host them in a single platform and how do you orchestrate that and deal with dependencies etc. uh but Kubernetes has become the clear winner.
</details>

**主持人**: 当你说赢家时，我理解，例如，当你有一堆后端服务器在一个服务上，比如你有一个网站，有一个大型后端。好的，我会为此使用 Kubernetes。但你说的是基础设施，对吧？或者你甚至在谈论像构建服务器这样的东西。

<details>
<summary>Original English</summary>
**Host**: And when you say winner, I understand that for example, when you have a bunch of backend servers on a service like you know you have a website, there's a large back end. Okay, I'll use Kubernetes for that. But you're talking about you're talking about infrastructure, right? Or you're talking about even things like build servers.
</details>

**罗伯特**: 没错。所以这有点意思，我们谈论 Kubernetes 是云原生的。这是你总能听到的词。它是云原生。

<details>
<summary>Original English</summary>
**Robert**: That's right. So it's kind of funny, you know, we talk about Kubernetes being, you know, cloudnative. This is what this is the term you always hear. It's cloud native.
</details>

**主持人**: 是的，他们是这么说的，对吧？

<details>
<summary>Original English</summary>
**Host**: Yeah, that's that's what they say, right?
</details>

**罗伯特**: 他们是这么说的。你看看采用它的供应商，是 Azure 和 AWS 等，它们在自己的平台上提供了它。但现实是，很多客户实际上使用 Kubernetes 来运行本地部署。嗯，所以，我们相当大一部分使用 Kubernetes 的客户，可能是在他们自己的服务器群上的虚拟机，或者他们可能在 AWS 或 Azure 上运行虚拟机，但他们自己维护 Kubernetes。嗯，这样做的好处是他们对运行的内容有更多的控制权。嗯，这在金融行业等领域尤其常见，在这些领域，完全控制流程并端到端地管理整个基础设施是他们的目标之一，但他们希望利用 Kubernetes 提供的能力，允许应用团队和运维团队以 Kubernetes 提供的声明式方式来构建和定义确切运行的内容以及运行方式等。所以他们选择 Kubernetes，因为这是他们能用来管理本地基础设施的最佳工具，并说，好的，我有这些物理机器，我想要这么多虚拟机，我想在这么多节点上运行数据库，以及一个内部 Web 服务器等等。所以它在这个领域也赢了。

<details>
<summary>Original English</summary>
**Robert**: That's what they say. And you know you look at the vendors that picked it up it's it's Azure and AWS and kind of the made it available on their platforms. The reality is a lot of customers actually use Kubernetes for running on premise. Um so you know a non-insignificant number of our customers who are doing Kubernetes are running on potentially their own VMs on their own server farms or maybe they're running VMs in AWS or Azure but they're maintaining Kubernetes itself. Um the idea being that they have a lot more control then over exactly what's running. Uh it's particularly common you'll find in things like financial industry and things like that where again wanting to fully sort of control the process and and um uh manage the whole sort of piece of infrastructure from end to end is kind of one of their goals but they want to leverage the capabilities that Kubernetes provides by you know allowing the the application team and the ops teams to just build and define kind of in that declarative fashion that Kubernetes provides um exactly what runs and and how does it run etc. So they they chose Kubernetes because this is the best tool they can manage their on-prem infrastructure and say like okay I have like these physical machines and I want this many virtual machines and I want to run a database on this many nodes and a internal web server or like whatever. So it it just won this area as well.
</details>

**主持人**: 是的。我的意思是，大约在 Kubernetes 出现的同时，或者实际上在此之前，有很多其他声明式工具。所以你有 **Terraform**，这是一个非常流行的工具，你可以精确地定义你想要的基础设施，你所做的本质上是定义期望状态，然后工具会应用它，还有 **Puppet** 等等。Kubernetes 也有类似的概念，对吧？你定义你希望你的基础设施看起来像什么，内部的 Kubernetes 控制器和操作符将基本上确保你要求的任何东西始终被应用。所以如果你说，你想要某个东西的三个副本，它会确保有三个副本。所以如果其中一个 Pod 死了，例如，它会启动另一个。所以它简化了这个过程，能够以声明式的方式精确地定义你作为应用团队需要什么来运行你的系统。

<details>
<summary>Original English</summary>
**Host**: Yeah. Yeah. I mean so there's around the same time that Kubernetes came out or actually before that there was a lot of these other kind of declarative type tools right. So you have uh you know terraform which is a really popular one you can define kind of exactly what infrastructure you want and and what you're doing is you're essentially defining the the desired state and then the tool kind of applies it and you know you've got puppet etc. And so Kubernetes has this similar concept right where you define what you want your sort of infrastructure to look like and the internal Kubernetes controllers and operators will basically ensure that whatever you've asked for always applies. So if you say you want, you know, three replicas of something, it will ensure that there's three like replicas of something. And so if one of those pods dies, for example, it will spin another one up. And so it simplifies this process of being able to find declarative declaratively kind of exactly what what you as a as a sort of application team uh need to run your your system.
</details>

### 本地 Kubernetes 的趣事

**主持人**: 这很吸引人，因为我总是假设 Kubernetes 已经赢得了云原生和超大规模云的市场。你能多告诉我一些它是如何在本地使用的吗？比如一些有趣的故事？你一定见过一些，因为你说你与那些管理大型本地 Kubernetes 或有趣环境的公司合作。

<details>
<summary>Original English</summary>
**Host**: It's fascinating because I I always assume that Kubernetes has won the the cloud native space and and Skyperscalers. Can you tell me a bit more about how it's being used on prem like some some interesting stories? You must have seen some because you said that you're working with companies who are managing like large on-rem Kubernetes or like interesting situations.
</details>

**罗伯特**: 是的，这是在像 Octopus 这样的公司工作的好处之一，对吧？我们与这么多不同的客户交谈和打交道，每个人的做法都略有不同，或者他们有略微不同的需求和条件。嗯，你会接触到很多不同的问题和模式。嗯，有时很容易迷失在会议上人们谈论的内容中，每个人都说一切都关于云，这是最佳实践，你应该这样做。但现实是，每个人都有自己的小问题，他们只想用他们需要的方式来解决它们。所以我们的一些客户，事实上，很多客户会运行所谓的“本地部署”的 Kubernetes。嗯，例如，我实际上和一位客户聊过...

<details>
<summary>Original English</summary>
**Robert**: Yeah, this is one of the nice things about working at a company like Octopus, right? We we talk to and deal with so many different customers and you know, everyone's doing things a little bit different or they've got slightly different needs and requirements. Um, and you kind of get exposed to a lot of different uh, you know, problems and patterns. Um, and it's easy to sometimes to get lost in, you know, what people are talking about in conferences and everyone's saying it's all about cloud and this is the, you know, best practice and you should be doing this. And the reality is, you know, everyone's kind of got their own little problems and they just want to solve them the way they kind of need to solve them. And so some of our customers, in fact, a lot of our customers will run Kubernetes kind of, you know, quote unquote on premise. Um, so for example, I was actually talking with one
</details>

**主持人**: 当你说本地部署时，你能说得更清楚一点吗？这是一个他们租用和托管的数据中心吗？还是实际上是我有自己的数据中心？或者是我在自己的壁橱里有自己的机器？

<details>
<summary>Original English</summary>
**Host**: when you say on premise, can you just be a bit more clear? Is this a data center where they're like renting and collocating? Is this actually like I have my own data center or is this like I actually have my own machines in my closet?
</details>

**罗伯特**: 是的。是的，我想是的。所以，

<details>
<summary>Original English</summary>
**Robert**: Yeah. Yes. And yes, I guess. So,
</details>

**主持人**: 甚至在壁橱里？我是在开玩笑。 [笑声]

<details>
<summary>Original English</summary>
**Host**: what even in a closet? That mean I was trying to joke there. [laughter]
</details>

**罗伯特**: 我敢肯定，仍然有一些团队在 Steve 的桌子底下运行着核心会计工具等等。但即使我们谈论小型计算机，我们的一些客户基本上在他们的销售点系统中拥有 Kubernetes 集群。所以，他们有数百家门店，里面运行着小型的 Kubernetes 集群，每个都是独立的，他们在这方面有自己的问题，特别是在规模上，当你有成千上万个集群时，嗯，这些客户遵循各种 GitOps 实践，他们从 Git 仓库拉取实际状态，所以 Git 仓库本身就成了瓶颈，或者他们开始被限流，嗯，所以他们不得不求助于其他机制来尝试缓解和解决这个问题。就在前几天，我在 **KubeCon** 上和另一个客户聊天，他们正在研究船上部署 Kubernetes 集群，那些研究船...

<details>
<summary>Original English</summary>
**Robert**: I'm I'm sure there are still uh teams out there that are running, you know, the the the core um accounting tools and etc. you under under Steve's desk. But even when we talk about, you know, um small computers, some of our customers have um Kubernetes clusters basically in their point of sale systems. So they have hundreds and hundreds of stores and they have little um Kubernetes clusters that essentially run in them and each one's independent and they you know run into their own problems with that because particularly at scale when you've got you know thousands and thousands of clusters um and you know these these um customers are you know following various GitOps practices etc where they're pulling the the actual state from from a git repository so the git repository itself becomes the bottleneck or they start getting throttled um and so they have to sort of resort to other mechanics to try to um sort of mitigate and work around that. I was talking to another one of our customers um actually just the other day at at KCOM there who they are deploying they they've got Kubernetes clusters running on research vessels and those research vessels
</details>

**主持人**: 研究，就像...

<details>
<summary>Original English</summary>
**Host**: research as in
</details>

**罗伯特**: 就像船一样。

<details>
<summary>Original English</summary>
**Robert**: like boats as in
</details>

**主持人**: 海上的船。

<details>
<summary>Original English</summary>
**Host**: ships on the ocean.
</details>

**罗伯特**: 没错。嗯，我不打算假装知道他们在那些船上具体做什么。我们没有深入讨论细节，但他们的 Kubernetes 集群就在公海上，对吧？这很符合 Kubernetes 的名字。但他们遇到的问题有点不同，对吧？对他们来说，嗯，那些船可能出海数周或数月。所以当你想进行部署时，船可能不在线。所以当船回到港口时，它需要获取更新，对吧？所以他们讨论的是如何实现这一点，以及这个过程如何运作。这非常有趣，我喜欢你通过与他们讨论如何进行部署，得以一窥这么多不同类型的团队，你可能也看到了他们正在做的其他事情，或者他们正在挣扎的事情。在你合作的从初创公司到金融公司再到这些研究船的广泛公司中，你看到了哪些行业趋势？

<details>
<summary>Original English</summary>
**Robert**: That's right. Um I'm not going to pretend to know exactly what they're doing on those ships. We didn't quite get into that detail, but they've got Kubernetes clusters out out in the open sea, right? Which is apps given Kubernetes name. The problems they run into though are a little bit different, right? So for them, um, you know, those boats might be out at sea for, I don't know, weeks, months at a time or whatever that might be. So when you want to do a deployment that the ship's not available. So when that ship comes back into port, it needs to get the update, right? So they'd be talking to how you would how you'd achieve this, right? And how that process would work. This is super interesting and I love how you kind of get a peak into so many different types of teams through the fact that you know like you're talking with them about how they do the deployments but you're you probably see some other things that they're doing or things they're struggling with. What are some trends you're seeing across the industry in terms of the this wide range of companies you work from startups to like finance companies to like these research vessels?
</details>

### GitOps 的四大支柱

**罗伯特**: 是的，我想当今的一大趋势是很多关注点都在 **GitOps** 上。那么什么是 GitOps？

<details>
<summary>Original English</summary>
**Robert**: Yeah, I guess one of the one of the big trends these days is a lot of focus on on GitOps. So GitOps is this what is GitOps?
</details>

**主持人**: 什么是 GitOps？这是个好问题。让我们退一步。我们之前提到了 Kubernetes。我们谈到了它内部有一个持续协调过程，你告诉集群“请启动五个 Pod”，它接受那个期望状态，并确保它在世界中始终为真。所以有很多产品在做类似的事情。Terraform 为基础设施做这个，等等。嗯，很多人开始想，为什么我们不能把这个过程再往前推一步，这样 Kubernetes 不仅处理期望状态，而且我们可以直接从 Git 中拉取它。嗯，这样我作为工程师，可以更改那个 Git 定义中的期望状态，然后有一些过程会将其推送到集群，并确保它始终与我的要求保持一致。所以 **GitOps** 这个词是由 **Weaveworks** 创造的，我想是在 2017 年左右，作为一种通用实践，它开始流行起来，特别是与 Kubernetes 齐头并进，因为 Kubernetes 的核心是非常声明式的。后来，在 2020 年代初，它被更正式地定义，有 GitOps 的四个关键支柱。第一个是，你希望你的状态是声明式的。这个想法是，你希望定义你的基础设施状态应该是什么样子。这基本上是为了让理解部署发生时的世界状态变得更简单。所以如果你考虑那些更命令式的部署，它有一个过程，最终结果是多个步骤的结果。嗯，但当你只想更新一些基础设施时，期望状态在 Kubernetes 领域效果非常好。在 GitOps 中，期望状态只是描述我想要多少个节点，或者我想要数据库有多少个副本，或者多少个 Web 服务器，或者负载均衡器如何连接等等。

<details>
<summary>Original English</summary>
**Robert**: What is GitOps? That's a that's a good question. Go G. Let's take a step back for a minute. So you know we mentioned we talked about Kubernetes earlier. We talked about the fact that it's kind of got this internal continuous reconciliation process where you say to the cluster uh please spin up you know five pods and um it takes that desired state and it ensures it always sort of is true in the in the world. And so there was a lot of products around there that were doing similar thing. You know Terraform does that for infrastructure etc. Um and a bunch of people started wondering why can't we sort of take that process and pull it back further so that um not only is Kubernetes just dealing with desired state but we can pull it sort of directly out of git um and so you know I can as as an engineer make changes to that uh that git definition that um desired state and I'd have some process that essentially pushes that to the cluster and and ensures that it it remains um in in line with what I'm asking what I'm expecting and so the term githops was coined by um by Weave Works in I think it was 2017 or so and as a as a general practice it sort of started picking up steam particularly in in tandem with Kubernetes because at its core Kubernetes is is very declarative right later on um sort of in the early you know 2020s um it was kind of formalized a bit more and there was sort of four key pillars of of GitOps the first being um uh essentially declar you want your state to be declarative so this is the idea that um you want to define what you want the state of your infrastructure to look like. This is to basically make things a lot I guess simpler to to understand what the state of the world is going to be when a deployment takes place. So if you think about um deployments that are a bit more imperative that has sort of a process, the end result is sort of the result of of multiple steps. Um but when you're wanting to just update some infrastructure, that desired state kind of works really well at um particularly in in the Kubernetes space. And then in GitOps the desired state will be just describing like how many nodes I want or like how many I don't know replicas do I want on a database or how many web servers or like load balancer how to be connected that kind of stuff.
</details>

**主持人**: 没错。所以它基本上是一种能够说出“我希望我的基础设施处于某种状态”的方式，嗯，然后 GitOps 代理，GitOps 产品，基本上确保这种情况保持不变。所以它们会持续将其应用到 Kubernetes。所以你会有这种情况，Kubernetes 保持其内部状态与现实同步，而现在你有这些 GitOps 工具，它们使声明式配置与 Kubernetes 的状态保持同步。

<details>
<summary>Original English</summary>
**Host**: That that's right. Yeah. So it's it's basically a way of being able to say I want my infrastructure to have whatever state it is um and then the the GitOps um agents the GitOps um products basically ensure that remains the case. So they'll keep applying it to Kubernetes. So you've kind of got this this um situation where Kubernetes keeps its internal status in sync with reality and now you've got these GitOps tools that take the declarative configuration in in sync with what Kubernetes is.
</details>

**罗伯特**: 所以它们会把我放在 Git 里的任何东西，无论我用什么格式，它们会把它翻译成对 Kubernetes 有意义的东西，然后 Kubernetes 就可以应用它。

<details>
<summary>Original English</summary>
**Robert**: So so they will take the whatever I put in Git and whatever format I use and they kind of translate it into something that makes sense for Kubernetes and now Kubernetes can apply it.
</details>

**主持人**: 是的。我的意思是，理想情况下，你希望它尽可能接近 Kubernetes 所期望的，因为...

<details>
<summary>Original English</summary>
**Host**: Yeah. Yeah. I mean, ideally, you want it as close as possible to what um sort of um I guess Kubernetes is expecting cuz
</details>

**罗伯特**: 它允许你。

<details>
<summary>Original English</summary>
**Robert**: allows you.
</details>

**主持人**: 没错。所以你描述的是持续协调。这个想法是，这些 GitOps 应用会像我们说的那样，获取那个状态并应用它，如果 Kubernetes 方面有任何漂移。例如，如果有人运行 `kubectl` 删除了一个 Pod 或一个部署，因为你的期望状态现在存储在 Git 中，在这种情况下，它会自我修复。嗯，GitOps 的第二个支柱是，你定义的期望状态应该存储在一个不可变且版本化的地方。这个想法是，一旦我说我想要这个状态，我想要有一个我可以指向的东西，可能是一个标签或一个提交哈希，我想用它来定义实际的状态应该是什么。我不希望它能够改变，对吧？否则就失去了部分意义。嗯，通过使其版本化和不可变，它也使得像审计这样的事情简单得多，对吧？你可以看到期望状态随时间的变化。但有趣的是，很多人会指着它说，“是的，版本化和不可变，我知道那是什么，那就是 Git。”

<details>
<summary>Original English</summary>
**Host**: That's right. And so what you're describing there, I guess, is the continuous reconciliation. And so this is the idea that um these these githops apps will um essentially as we said sort of take that state and apply it and if there's any drift from kubernetes side. So for example someone um you know runs cube control you know delete pod or or a delete deployment or whatever the case might be because your desired state is now stored in in git in this case that will kind of self-rep. Um the second uh pillar of githops is that that desired set you've sort of defined um should be um stored somewhere that's uh immutable and versioned. And so this is the idea that um once I say that I want to have this state, I want to have sort of something I can point to a pointer and that might be a tag or a commit show or whatever and I want to basically use that to define what what that actual state should be. And I don't want that to be able to change, right? Because otherwise that kind of defeats half the point. Um by having it versioned and immutable, it also um makes things like auditing a lot simpler, right? You can see the transition of that that that desired state over time. What's interesting though is a lot of people will point to that and go yes um version and immutable I know what that is that's git
</details>

**罗伯特**: 我正要这么说，因为 Git 确实给你版本控制，或者它给你提交历史，我不确定它是否给你版本控制和不可变性，我的意思是过去不能被改变...

<details>
<summary>Original English</summary>
**Robert**: I was about to say that because git gives you it definitely gives you versioning or it gives you commit history I'm not sure if it gives you versioning and immutable in the sense that I mean the past cannot be changed
</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>
**Host**: that's that's right
</details>

**罗伯特**: 或者实际上可以吗？因为你可以重写历史。

<details>
<summary>Original English</summary>
**Robert**: or actually can it because you can rewrite
</details>

**主持人**: 你说得对，所以取决于你如何配置你的 GitOps 代理，嗯，你当然可以重写历史。例如，如果你让它指向一个标签，你可以更改标签。所以这就是为什么有围绕这个的最佳实践。嗯，如果你使用标签来管理那种状态，可能会被批评。嗯，但有趣的是，这些支柱中实际上没有任何一个提到 Git。嗯，很快说一下，第三个支柱是拉取与推送。这个想法是你的 GitOps 代理会从 GitHub 或 Git 拉取状态，然后放入集群。第四个是持续协调。嗯，但这些支柱中没有一个真正谈论 Git。我认为 GitOps 的命名让人们对“一切皆在 Git”有了这种期望。

<details>
<summary>Original English</summary>
**Host**: history you're right so you depending on how you sort of configure your githops agent um you know you certainly can rewrite history if If you have it pointing at a tag, for example, you can change tags. And so that's why there's, you know, best practices around that. Um, I guess kind of, you know, wiggle the finger a bit if you're using tags to to manage that sort of state. Uh, but what's interesting though is really nothing in the in these pillars. Um, and very quickly, the third one being uh pull versus push. And so this is the idea that your um your GitOps agent will pull the state from GitHub and put or git, I should say, and put it into the cluster. and the fourth being continuous reconciliation. Uh but nothing in any of these sort of pillars actually talks about git. And I think that the naming of githops is kind of um kind of gets people to to already have this expectation that everything has to be in git.
</details>

**罗伯特**: 我的意思是，为什么不会有这种期望呢？我就是这么认为的。

<details>
<summary>Original English</summary>
**Robert**: I mean why would you not have that expectation? That's what I assumed.
</details>

**主持人**: 没错。但我认为问题在于，并非所有东西都应该放在 Git 里，对吧？所以在这个社区里，一直有关于你把秘密放在哪里的讨论。例如，没人，不不不，我们知道，就是不要把它放在 Git 里。

<details>
<summary>Original English</summary>
**Host**: That's right. I think the the problem though is um not everything should be in in Git, right? So you've got this constant kind of conversation within that community about you know where do you put secrets for example? So no one not g no no no no we know that right is that do not put it in git
</details>

**罗伯特**: 所以就是这样，所以有很多解决方案试图把它放在 Git 里，比如 **Sealed Secrets**，你加密它然后放在 Git 里。

<details>
<summary>Original English</summary>
**Robert**: and so that's the thing so you know there's been all these solutions to try to put it in git so there's things like sealed secrets where you encrypt it and put it in git um
</details>

**主持人**: 听起来是个糟糕的主意。

<details>
<summary>Original English</summary>
**Host**: sounds like a terrible idea
</details>

**罗伯特**: 但我想这真正凸显的是，有些东西不需要放在 Git 里，对吧？只要你能对其版本控制或不可变性有这种控制，那就完全没问题。

<details>
<summary>English</summary>
**Robert**: but I guess what's really this is highlighting is um the reality that some things don't need to be in git right as long as you can um have this sort of control over the versioning or immutability of it um then that's that's completely fine
</details>

**主持人**: 那么你看到的围绕 GitOps 的趋势是，更多的基础设施团队正在从“几年前他们可能只是为 Kubernetes 编写定义”转向 GitOps，也就是说，“我们希望以一种在版本控制中描述的方式来控制基础设施”。这是趋势吗？还是围绕 GitOps 的趋势是什么？

<details>
<summary>Original English</summary>
**Host**: and then the trend around githops is is what you're seeing that a lot more infra teams are moving from okay a few years ago they might have just like made definitions for Kubernetes and now they're moving over to GitOps so saying okay we'd like to control infra in in in a tool in a way that's that's described that's in version control is that the trend or what is the trend around githops
</details>

**罗伯特**: 嗯，我想更多的是 GitOps 在企业中整体增长的趋势。并非每家公司现在都在使用 Kubernetes，当他们接触 Kubernetes 并考虑如何执行部署、如何管理这个过程时，GitOps 成为了事实上的过程。在某种程度上，它也催生了使用它来管理 Kubernetes 之外的其他事物的想法，有一些项目和实验的例子会使用 Terraform 之类的东西，并有一个持续协调服务来保持你的实际状态同步。目前，焦点主要还是集中在 Kubernetes 上，它是 GitOps 的核心所在。嗯，我想更多的是 Kubernetes 自身的增长意味着 GitOps 也随之而来。

<details>
<summary>Original English</summary>
**Robert**: um I I guess it's more just the trend of of the growth in general of GitOps in in um enterprises right so not every uh company out there is using Kubernetes today um and as they sort approached Kubernetes and they're looking at well how do I how do I um you know perform the deployments how do I manage that process gitops becomes the sort of deacto process and to some extent it is um giving rise to this idea of using it to manage um other things outside of kubernetes and there are a few examples of uh projects and experiments that will use things like terraform and there's a a continuous reconciliation service that keeps your your actual state um outside in in sync at the moment it's really about the focus is on I guess Kubernetes is the core core place where it lives. Um and I guess it's more the growth of Kubernetes itself means that GitOps is is coming along for the ride.
</details>

**主持人**: 你提到了企业，这意味着像那些通常有成千上万员工或在受监管环境中的大公司，这就是我对企业的理解。你是否也看到较小的团队采用 GitOps？它是无处不在，还是某些类型的团队似乎对它更感兴趣？

<details>
<summary>Original English</summary>
**Host**: And you mentioned enterprises which means like these large companies with often times thousands of people or in regulated environments that's what I think of enterprises. Are you also seeing smaller teams pick up uh things like GitOps? Is it like everywhere or is it more there's certain types of teams that seem to be just more interested in that?
</details>

**罗伯特**: 这是个好问题。嗯，我想有时我们看到很多人去参加会议或阅读博客文章，他们听说 GitOps 是你应该做的。所以我想在这里指出的是，GitOps 可能并非对所有地点、所有环境、所有团队都是必需的，对吧？嗯，它当然有很多好处，但现实是，有一些事情你需要做，而不仅仅是 GitOps。你可能在你的过程的某些部分使用 GitOps 原则，但我认为有时存在的一些绝对主义可能并非必要。所以通常在你所谓的“部署”周围，你还会做很多其他过程。比如，你可能运行冒烟测试，或者你可能想在完成时发送通知，或者你可能想进行数据库更新之类的。这些步骤并不太适合这种“一切都是声明式的，一切都在 Git 中”的过程，对吧？这就是为什么会出现像 **Argo Workflows** 和 **Argo Rollouts** 这样的东西，试图将这个过程“GitOps 化”。这对某些人有效。但我想现实是，有些人真的执着于“一切皆 Git”的想法，所以他们找到了这个工具，因此一切都是钉子。

<details>
<summary>Original English</summary>
**Robert**: That's a good question. So um I guess sometimes what we see is a lot of people go go to conferences or they read blog posts and they hear that GitOps is what you should do. So I guess what I want to point out here is um GitHubs is potentially not necessary for all all locations, all environ all teams, right? Um there's certainly a bunch of benefits to it, but the reality is there's some things you need to do outside of just GitOps. You might use GitOps principles in parts of your process, but some of this absolutism I think that sometimes exists uh may not be necessary. So there's often a bunch of other processes you do around your actual sort of um you know, quote unquote deployment. So things like maybe you run smoke tests or maybe you want to send a notification when it's complete or maybe um you want to do a a database update or something like that. These kind of steps don't really lend themselves very well to kind of this declarative everything is is in git kind of process, right? And so that's why you get things like um Argo workflows and and and roll outs and things come out to try to kind of get opsify this this process. And that that works for for some people. But the reality I guess is that um um I think some people get really hung up on this idea that that everything is git so therefore they they found the tool and you know and so therefore everything is a nail.
</details>

**主持人**: 是的，我想那是...

<details>
<summary>Original English</summary>
**Host**: Yeah. I think that's
</details>

**罗伯特**: 就是这样，与客户交谈时，当我们经历这个过程，你知道你可以在 Octopus 中使用 GitOps，嗯，我们对各种与 Kubernetes 和 Argo 良好集成的机制有很多支持，但在这个过程中你还会做很多其他操作，这些操作不需要... 当你和他们谈论这个时，他们意识到他们最终想做的只是发布软件。所以，这又是你在会议上听到的“一切皆 Git，一切必须以这种特定格式”与现实之间的区别。对于大多数客户来说，他们只是想发布软件，对吧？他们不在乎你叫它什么。如果它是 GitOps，并且能端到端地工作并解决所有问题，那很好。如果他们想将 GitOps 作为过程的一部分，但随后使用其他更命令式的机制，那也很好。这就是现实，世界上有成千上万的公司正在进行软件交付。嗯，并非所有公司都去参加会议，也并非所有公司都处于最前沿。

<details>
<summary>Original English</summary>
**Robert**: and this is the thing like talking with with customers when we go through this process of you know you can use GitOps in Octopus um and you know we've got a bunch of support for various um mechanics that integrate well with Kubernetes and Argo but there's a bunch of other sort of operations you do around that process that that doesn't need and when you talk to them about it you know they realize that what they're trying to do is ultimately just ship software so again that difference between what you um hear when you talk at conferences and things where you know everything is everything is git and everything must be you know in in this particular format or whatever the case might be. The reality is for most customers they're just trying to ship software right and they don't care what name you give it. If it's GitOps and it works end to end and solves everything good. If they want to use GitOps as part of the process but then have other mechanics that are more sort of imperative um then then good. It's just sort of the reality of, you know, there's there's tens and tens of thousands of companies out there in the world that are doing software delivery. Um, and not all of them that are at conferences and not all them are at the the forefront. I guess
</details>

### 平台团队的兴起

**主持人**: 正如 Rob 所说，大多数团队不在乎你叫它 GitOps 还是别的什么。他们只想发布软件并知道它能用。我们之前谈到的另一个趋势是平台团队的兴起。你能谈谈你看到了什么吗？

<details>
<summary>Original English</summary>
**Host**: as Rob says, most teams don't care whether you call it GitOps or anything else. They just want to ship software and know that it works. Our presenting sponsor, Anticys, does exactly that. Is let you ship knowing that it works. Antithesis goes beyond code review. It runs your whole system inside a hostile simulation. By doing so, it finds every bug before your users do. And because the simulation is fully deterministic, antithesis doesn't only find bugs, it gives you a perfect reproduction of every issue. I know this sounds like science fiction, but it's actually hardcore engineering under the hood. Jane Streetfly.io and the CD community ship agent written code with full confidence because they know it's been verified by antithesis. To see more case studies and details, head to antithesis.com/pragmatic. That's antithesis.com/pragmatic. I also want to mention our season sponsor, Turbopuffer. Turbopuffer is exactly the thing that just works. A vector and full text search engine built on object storage. Fast, cheap, and extremely scalable. No exotic architecture required. Here's something I find interesting. The teams building the smartest AI products out there, cursor, notion, cognition, and tropic. They all run on turbo buffer. But why? Let's think about it. and LM without context, it can feel pretty dumb. I can still remember shortly after CantBT launched early 2023, how it felt both incredibly smart but also frustratingly stupid. If you asked it a question that was outside his training data, it just made things up. Fast forward to today and the models and their tools for retrieving context are much better, but hallucinations still happen frequently. Here's a typical way to integrate Turbuffer with an LM. Plug it behind your search tools, get fast responses and relevant context back. The neat thing is how it gives you the perfect blend of lowcost storage, fast retrieval, and a bunch of different search tools like vector, full text, and filtering. You can afford to index billions of documents, and then you can query it with different tools to get the most relevant handful of documents in milliseconds. This is how your LM feels smart. It gets the right context really fast without blowing through a bunch of tokens. Of course, you can use Turbopuffer to search anything, not just code. If you're building AI products, check out Turbopuffer at turbopuffer.com/pragmatic. With this, let's get back to Rob and talk about progressive delivery. Yeah. Another trend that we talked about just before is the rise of platform teams. Can you talk about what you're seeing?
</details>

**罗伯特**: 所以，平台团队在过去的几年里，已经成为一种新的标准组织结构，帮助团队管理他们的部署工作流和周围的基础设施。它源于 DevOps 的演变，对吧？我们之前提到过，在过去，你写一点代码，然后把它扔给运维团队。所以是开发团队和运维团队。

<details>
<summary>Original English</summary>
**Robert**: So, platform teams are kind of I I guess in the past several years, they've become this sort of new standard organizational structure to help teams manage their I guess deployment workflows, the a bunch of the infrastructure around it. And it's kind of come out of this evolution of of de DevOps, right? So, you know, we mentioned before in the old days, you'd write a bit of code um and you'd throw it over the wall to the ops team. So, it was dev teams and ops teams and you
</details>

**主持人**: 这就像在 2000 年代、2010 年代。

<details>
<summary>Original English</summary>
**Host**: this was like in the 2010s, 2000s
</details>

**罗伯特**: 在很久很久以前。嗯，然后 DevOps 成为了一种实践，每个人都意识到实际上我们希望工程团队参与并拥有部分运维过程。想法是，你得到更快的反馈循环。如果你感受到痛苦，你就会去修复，你知道那句老话，“你修复它，你发布它”。嗯，我们很多人都听说过。所以，很多团队都认真对待了这一点。这是好的，很好的实践。但随着规模扩大，你会发现最终又会形成一个 DevOps 团队，有时他们与另一个运维团队是分开的。所以开发和 DevOps 之间又出现了分离。这有点违背了 DevOps 试图打破的一些原则。但不仅如此，这些团队最终会有很多不同的方式进行部署。所以，你有一大堆应用团队，他们都有略微不同的需求，并且都是从零开始构建的。所以最终，无论你是拥有 DevOps 团队，还是它仍然在应用团队内部，都会有大量不同的做事方式，对吧？这在规模上变得困难。所以你很难在团队之间调动。

<details>
<summary>Original English</summary>
**Robert**: back in the back in the long long ago. Um and then DevOps became, you know, the the practice that everyone sort of realized that actually we want to have the the engineering teams be involved in and have ownership of part of that that operational um process. idea being, you know, you get faster feedback loops. You are able to kind of if you feel the pain, you you sort of fix, you know, it's that saying, you know, you fix it, you ship it. Um, you know, we've all kind of heard that. And so, um, a lot of teams, you know, took that to heart. That's that's good, great, uh, good practice. But as things start to scale up, what you'd find is that there would end up being like a DevOps team again, and sometimes sometimes they're separate to another ops team. And so there'd be this separation of of um development and DevOps. And it kind of goes against some of the principles of what DevOps was, you know, trying to destroy. But not only that, these teams then um end up um having lots of different ways of doing their um deployment. So you know, you've got every single, you know, a whole bunch of application teams and they've all got slightly different requirements and they're all building it from scratch. And so you'd end up with these these teams either whether you had the DevOps teams or it was still within the application teams where um there was just this this um large number of different ways of doing things, right? And that becomes difficult at scale. So um you know you can't really move between teams
</details>

**主持人**: 你说的规模，通常是指当有很多团队的时候，对吧？这是最简单的理解。

<details>
<summary>Original English</summary>
**Host**: and and by scale you mean typically when there's a lot of teams, right? That's the easiest.
</details>

**罗伯特**: 是的，没错。如果你有很多很多团队，每个团队都端到端地拥有那个过程，你就会得到过程的分散化，不仅如此，应用团队本身也开始出现上下文过载，对吧？他们现在需要考虑不同云工具的最佳实践。

<details>
<summary>Original English</summary>
**Robert**: Yeah, that's right. If you got if you got lots of lots of teams and each one is kind of owning that process end to end, you know, you sort of get this bifocation of processes and not only that the application teams themselves start kind of getting this this um context overload, right? They now need to think about what's be best practices of of the different cloud um tools.
</details>

**主持人**: 是的。而且很少有开发者愿意配置部署脚本并测试它们，测试很难。它不能真正进行单元测试。所以它现在是一份不同的工作。我记得在我早期的团队里，比如在一个移动团队，通常有五个人，我们中的一个人必须专门研究 Jenkins 配置，因为 Jenkins 经常是移动端的 CI/CD，这差不多需要半个人力，我们经常要抽签决定谁来做，因为我们都想写代码。

<details>
<summary>Original English</summary>
**Host**: Yeah. And there's of of devs rarely want to configure the deployment scripts and test them and testing is hard. It's you can't it's not really unit testable. So it's it's now a different job. I remember when I was on earlier teams where you know like typically on a mobile team like you have a you have a mobile team of five people and one of them one of us had to kind of specialize in Jenkins configurations because Jenkins is often times the or used to be the mobile CI/CD and it's kind of like half a person dedicated to that and it was more like draw you like we had to draw a stick on who's going to do it because we want to build
</details>

**罗伯特**: 你想写代码，对吧？你只想专注于写代码，所以如果你花大量时间管理基础设施和流水线之类的事情，嗯，这对任何人来说都没意思。

<details>
<summary>Original English</summary>
**Robert**: you want to write code right you just want to focus on writing code and so if you're spending a bunch of your time sort of managing infrastructure and pipelines and things um you know that that's no fun for anyone
</details>

**罗伯特**: 嗯，所以平台团队作为一种解决这个问题的新方式出现了，它不同于那种拥有整个过程的 DevOps 团队或运维团队的想法。他们更多的是定义最佳实践，并提供一个理想情况下是自助服务的机制，应用团队可以使用通常被称为 **IDP**（内部开发者平台）的东西，他们基本上可以自助服务，比如他们可能想启动一个新项目，他们可以使用平台团队生成的模板。这样平台团队就能在整个公司创建这些标准，他们可以负责定义那些流程、最佳实践以及如何实现它们。嗯，但实际运行运维元素的所有权仍然在团队内部，对吧？所以他们仍然能获得 DevOps 的好处，贴近实际代码，如果出现问题能感受到痛苦等等，但他们不需要花所有时间成为部署软件的各种方式的专家。所以这现在已经变得非常普遍，特别是当你的规模变大时，平台团队是解决这个问题的一个好方法。嗯，这并不是说每个公司都应该有一个平台团队。如果你是一家较小的公司，有时你只有应用团队，他们就在做所谓的 DevOps。嗯，但当你开始看到拥有多个团队或多个项目的大型组织时，这些平台团队基本上是为整个领域带来一些秩序、控制和焦点的一种方式。

<details>
<summary>Original English</summary>
**Robert**: Um and so platform teams have come about as a new way of solving that problem where it's different to kind of you know this idea of a devops team or ops team that kind of own the whole process. they they more sort of define best practices and they provide a um ideally a self-service mechanism where application teams can um essentially use um often what it's called as an IDP an internal development portal and they'll be able to essentially self-service and you know maybe they want to spin up a new project and they're able to use a template that the platform team have generated and so the platform team are able to sort of create these standards throughout the throughout the company and they can be responsible for sort of I guess the definitions of those pro processes and the best practices and how to achieve that. Um, but the ownership of the the actual running operational sort of element is still within the teams, right? So, they still get those benefits of of of, you know, DevOps, being close to the close to the real code and and feeling the pain if there's a problem and etc., etc., etc., but they don't need to spend all that time becoming experts in um, you know, all the different ways that you can deploy the software they've got. And so this has become um really common now where particularly as you sort of get to a larger size platform teams are a great way of of solving that problem. Now um that's not to say that every company everywhere should have a platform team. You know if you're a smaller company sometimes it's you you've just got the apps team and and they sort of are doing you know quote unquote DevOps. Um but this is certainly something that as as you sort of start seeing larger organizations with multiple teams or multiple projects, these platform teams are a way of basically bringing some some sanity and control and focus I guess to to the whole space.
</details>

### AI 对 CI/CD 的影响

**主持人**: 行业中的一个趋势当然是 AI。很难看到有哪个团队的开发者不使用 AI 代理来编码。产品经理也会使用这些东西，当然，结果是我们产生了更多的代码。说到 CI/CD 系统，你看到 AI 带来了哪些变化？

<details>
<summary>Original English</summary>
**Host**: One trend across the industry of course is AI. Everyone's it's hard to see any teams where devs are not using AI agents specifically to code. you know product managers will will be using these things and of course we have a lot more code produced as a result when it comes to CI/CD systems what are you seeing changing there because of AI
</details>

**罗伯特**: 这是房间里的大象，对吧？AI 如何影响这个？老实说，我认为现在还非常早。我认为对 CI/CD 的影响将与开发团队最终如何使用 AI 紧密相关。所以会有一个滞后过程。但我们发现很多团队开始在他们的开发过程中使用 AI。所以我们开始走出去，与客户交谈，了解他们在团队和应用团队中处理 AI 的方式，然后我们如何最好地利用 CI 方面来支持这一点。但除此之外，在流水线本身中正确使用 AI。在 Octopus，我们一直非常关注的一点是，在 KubeCon 上，我们可能是少数几家没有到处贴满 AI 的公司之一。我们试图保持谨慎，因为那是为了销售，对吧？

<details>
<summary>Original English</summary>
**Robert**: this is the this is the uh the elephant in the room right the how is AI affecting sort of this the reality is I think to be honest it's it's still very early I think what will happen is the impacts of CI/CD um are really tightly coupled to how development teams end up using AI. So there's going to be some sort of like um I guess a lagging process there. But we're finding a lot of um people a lot of teams are starting to use AI in their development process. And so we're starting this process of going out and looking and talking to customers and and learning what's the way that they're handling AI in their um in their in their teams and their application teams and then how we can best leverage sort of the CI side to um to support that. but then um in addition to that use AI within the the pipeline itself get in the right place. So one of the things we've been um I think pretty pretty um keen on at Octopus is this idea that um you know at CubeCon we were probably one of the few companies that that didn't have you know AI plastered all over it. Like we we tried to be very you know that's that's what gets the sales right.
</details>

**主持人**: 是的，现在这样反而让你脱颖而出。

<details>
<summary>Original English</summary>
**Host**: Yeah. That's you stand out now these days.
</details>

**罗伯特**: 没错。通过没有 AI。嗯，我的意思是，我们在 Octopus 里有 AI，但我们一直在思考的是，我们如何以对客户、对工程师真正有用的方式来使用它。嗯，所以我们一直在 Octopus 内部慢慢添加功能，以提供 AI 支持，无论是 **MCP 服务器**，还是一个可以审查日志和任务的恢复代理等等。但那是产品本身内部的。一些更大的变化将取决于，就像我说的，实际的应用团队如何使用 AI。我认为我们会发现的是，会有更多的速度。我认为这是最大的变化之一，就是会有更多的代码通过流水线。我认为其中一个问题是，这对你的流水线意味着什么？嗯，当流水线中有人为因素时，你经常谈论的一件事是加快周期以获得更快的反馈。你知道，如果有工程师坐在那里等待他们的代码运行测试，他们可以回去修复它，你能让这个反馈循环越短越好，因为他们不需要上下文切换等。我认为在一个大部分代码由 AI 开发的世界里，这可能会变得不那么重要。你知道，如果你能启动你的构建和测试过程，它需要 30 分钟而不是 20 分钟，如果工程师已经离开，转向下一个问题，而 AI 代理本身可以照看这个过程，审查出现的问题并发布新的修复，这真的重要吗？我想，对流水线本身速度的重视会降低，而更多地关注增加或降低风险，对吧？来自 AI 生成代码的风险。所以这个过程具体是什么样子，还有待观察。我认为我们会看到更多使用渐进式交付。我认为特别是**功能开关**将成为应用团队工具箱中非常常见的工具。部分原因是它允许你尽可能快地发布代码，但管理实际功能集或变更的发布，独立于部署。它在一定程度上将你的部署与你的发布解耦。所以在一个我们有更多 AI 代理生成代码并可能参与部分构建过程的世界里，这些代理本身能够使用开关来快速做出反应，我认为这将变得比我们今天看到的更加重要。

<details>
<summary>Original English</summary>
**Robert**: That's right. By not having AI. Um, I mean we we've got AI in Octopus, but what we've been trying to do is think about, well, how do we actually use it in a way that's actually useful for for for our customers, right, for for engineers, etc. Um, and so we've been slowly adding capabilities within Octopus to provide um, you know, AI support, whether it's a MCP server, uh, whether it's a a recovery agent that can review logs and tasks and all that sort of thing. But that's within the product itself. Some of the bigger changes will depend on like I said how how actual application teams um use use AI. What I think you know we're talking about we'll find is there's going to be a lot more velocity. I think that's one of the big big changes right is there's just going to be a lot more code coming through. I think one of the questions is okay what does that mean for your pipeline? Um one of the things you often talk about when you know human there's a human element to the pipeline is speeding up the cycle to get that feedback quicker. You know, if you got engineers sitting there waiting for their code to run tests, they can get back to it and fix it, the the shorter and shorter you can make that feedback loop, the the better it becomes because they don't need a context switch, etc. I think in a world where the majority of your code is being developed by AI, that becomes perhaps less important. you know, if you can um kick out your your build and test process um and it takes 30 minutes versus 20 minutes, does it really matter if the engineers are already long gone, moved on to the next problem and the the actual AI agent themselves itself can kind of babysit the process and review the problem that came up and issue a new fix. I guess there'll be a deemphasis, I think, on some of the speed of the pipeline itself and more on increasing sort of um or decreasing risk, right? the risk that comes from having AI items generate code. And so exactly what that process looks like, I guess, remains to be seen. I think what we'll see a lot more use of is things like progressive delivery. And I think particularly feature toggles um are going to be a really common tool in in the tool belt of application teams. Partly because it allows you to ship that code as as fast as you can or as fast as you want, but manage the roll out of the actual feature set or changes sort of independent of the deployment. sort of decouples your deployment from from your release. And so in a world where you know we've got a lot more AI agents generating code and being involved in perhaps part of the build process, those agents themselves being able to use toggles to react to it quickly, I think then become a lot more important um than perhaps what we see today.
</details>

### 渐进式交付与金丝雀部署

**主持人**: 我们能谈谈渐进式交付吗？它是什么，以及最常见的降低代码或软件发布风险的方式有哪些？

<details>
<summary>Original English</summary>
**Host**: Can we talk about progressive delivery? what it is and what are the most common ways to you know like to to derisk getting your code or your software out there.
</details>

**罗伯特**: 渐进式交付是持续交付之后的下一步进化。嗯，对于持续交付，这个想法是我对系统做了一个更改，我想把它发布到开发或预发布环境，或者通常，如果它到达生产环境，是一次性完成的。而渐进式交付，你试图做的是以更可控的方式发布这些更改，通常通过像**金丝雀部署**这样的方式。这就是你可能只部署你现有实例的一个子集。

<details>
<summary>Original English</summary>
**Robert**: So progressive delivery is the next evolution beyond continuous delivery. Um so you know with continuous delivery it's this idea that you know I've made a change to the system and I want to ship it to um dev or stage or typically you know if it gets to production sort of in one hit right with progressive delivery um you're what you're trying to do is basically release those changes in a little bit more of a controlled way typically through things like a canary deployment. So this is where you might deploy just some subset of of your instances that are out there.
</details>

**主持人**: 那么什么是金丝雀？什么是金丝雀部署？嗯，金丝雀部署基本上就是新西兰。新西兰是我们的金丝雀。所以就像我们之前说的，这个想法是你选择你客户群的一个子集，然后你通常会将流量路由到一个新实例。所以，你有一个版本一在运行，你想发布版本二。你基本上并排发布版本二，你可能会使用某种网络流量管理器，将一定比例的流量路由到那个新实例，然后逐渐增加比例。通常，如果你正确地执行这个过程，你应该有相当成熟的**可观测性**机制，以便你可以看到情况，从而增加或减少流量。

<details>
<summary>Original English</summary>
**Host**: So what is a canary? What is a canary? Um Canary deployment is this is New Zealand basically. New Zealand's our canary. So this is as we said before this idea where um you select some subset of your your customer base or or whatever that might be and you would typically route traffic to a new instance. So you'd ship you know you've got version one running and you want to release version two. You essentially ship version two side by side and you might use, you know, most common one would be some sort of network um traffic manager to route some percentage of your traffic to to that new instance and you gradually roll that up. Typically, you know, as you do sort of do this process properly, you you should have a fairly mature um observability um mechanisms in place to see that, you know, you can roll up or roll down.
</details>

**罗伯特**: 我想这整个概念来自“煤矿里的金丝雀”，对吧？

<details>
<summary>Original English</summary>
**Robert**: And I guess this whole thing comes from a canary in a coal mine, right?
</details>

**主持人**: 没错。是的。所以这个想法是，在过去，当你在煤矿里挖掘时，会释放出各种有毒气体，金丝雀对此要敏感得多。所以他们把一只小金丝雀放在笼子里，如果那只金丝雀死了，我想是倒下了。

<details>
<summary>Original English</summary>
**Host**: That's right. Yeah. Yeah. So the idea being that um you know in the old days when you'd be in a coal mine digging away and it would release um you know all sorts of toxic fumes and things like that canaries were um a lot more sensitive to it. So they have a little canary in a pa cage um and if that canary sort of died I guess got knocked down.
</details>

**罗伯特**: 据我所知，金丝雀会叽叽喳喳叫，然后当它停止叫的时候，它也死了。

<details>
<summary>Original English</summary>
**Robert**: I I think the canaries as I understand they were like chirping and then when it stopped chirping well it also died.
</details>

**主持人**: 哦，好吧。一样的结局。一样的结局，只是，你知道，一种更体面的离开方式。

<details>
<summary>Original English</summary>
**Host**: Oh okay. All right. Same same ending. Same ending, but just, you know, a nicer a nicer way to go out.
</details>

**罗伯特**: 他们需要出去。

<details>
<summary>Original English</summary>
**Robert**: They need to get out.
</details>

**主持人**: 是的。所以，这个想法是你得到那个提前警告，而不是你自己被毒气熏倒。所以，同样的原则被带到了软件中。嗯，还有其他各种机制，比如**蓝绿部署**。所以你的第一个版本仍然在接收流量，你的第二个版本已经启动并运行，你现在可以对其进行一些测试，验证它。也许你有直接访问它的 IP 细节。你可以基本上验证它是否工作。嗯，有时有一种方法可以避免冷启动之类的问题，因为那个过程可能需要初始化一堆东西，但当你完成验证并准备好后，你可以基本上交换流量。所以所有新流量都流向另一边。在某些方面，它就像做金丝雀部署，但直接到 100%，但你在它实际到达客户之前，在旁边做了一堆验证。在我看来，可能更有用的渐进式交付策略是**功能开关**。所以，这个想法是你有某种...

<details>
<summary>Original English</summary>
**Host**: Yeah. So, it's this idea that you get that advanced warning, I guess, that you know, rather than you getting knocked out by the the toxic gases, etc. Um, you know, you can get out of there sooner. So, it's that same principle, I guess, brought to the software. Um, there's various other mechanisms like blue green deployments. So you've got your first version there still receiving traffic and your second version is up and running and you can now do some tests against it, validate it. Maybe you've got sort of the the the um you know the IP details to access it directly. You can basically validate that it's working. Um sometimes there may be a way of avoiding cold starts and things because that process may need to you know initialize a bunch of stuff but then when you've sort of done that validation and you're ready you can essentially swap swap traffic around. So all the all the new traffic goes the other. In some ways, it's like doing a canary but straight to 100% but you're doing a bunch of validation um sort of on on the side before it actually reaches customers. In my in my view, probably the more um useful uh progressive delivery strategy is is feature toggles. So, this is the idea that you you've got some sort of
</details>

**罗伯特**: 功能标志也一样。

<details>
<summary>Original English</summary>
**Robert**: feature flags as well.
</details>

**主持人**: 功能标志、开关，是同一个东西。嗯，经常互换使用。嗯，所以，这个想法是，你的系统中有某种变量，嗯，它通常连接到某种外部服务，通过该特定变量的状态（真或假，开或关），你可以基本上让不同的代码路径生效。功能开关相比金丝雀发布有很多好处，特别是对于应用交付，因为功能开关的变更单位非常细粒度。它可以是单行代码，所以其他一切保持不变，你所做的只是调整那一行代码。而对于金丝雀或任何版本化的交付部署机制，你的变更单位是整个应用。所以，如果自上次发布以来有 20 次提交，那么你基本上是一次性测试所有 20 个东西。你定位实际客户的能力，在使用功能开关时要精确得多。所以你可以使用各种复杂的规则，比如，我不知道，所有来自德国、购物车中有这个特定产品的用户，都有这种体验，这通过网络流量规则很难做到，对吧？另一个是实际回滚的能力。嗯，从金丝雀回滚，希望你还处于金丝雀过程中，你可以回滚，嗯，那可能需要几分钟。也许你必须重新部署整个旧版本。那可能需要几分钟或更长时间。而使用功能开关，你可以在几秒钟内完成。按下按钮，立即生效。不仅如此，你还能更好地控制何时进行回滚。所以，对于通过标准版本化发布进行的部署，你受限于部署发生的时间，因为当部署发生时，你的新功能才可用。作为应用团队，这意味着你需要确切知道它何时发生，并确保在那时查看日志。也许你和另外 10 个同时发布东西的团队都在做同样的事情。而使用功能标志，你基本上可以控制它何时发生。所以你可以在周一发布实际的程序集之类的东西，但你在周二上班时才发布你的功能，那时你已经准备好日志，并审查了下一步。所以这真正使得将发布功能与部署软件解耦变得容易得多。通过金丝雀等方式进行的版本化部署非常有用，特别是当你进行基础设施类型的更改时，那里没有相关的应用开关，但你希望对基础设施或你的过程进行一些更改，或者可能涉及数据库结构变更的事情，而数据库结构变更是个大问题。

<details>
<summary>Original English</summary>
**Host**: Feature flags toggles the same thing. Yeah. Often used interchangeably. Um so, this is the idea that you've got, you know, some sort of uh variable in your system. um and it's linked to typically some sort of external service and through the state of that particular variable being sort of true or false on or off um you can essentially have different code paths essentially take effect and there's a bunch of benefits that feature toggles have over say canary um releases particularly for application um delivery where you know the the your unit of change with a feature toggle is is very granular. it can be, you know, single lines of code and so everything else remains the same and all you're doing is is tweaking that single line of code with a canary or any sort of versioned sort of delivery deployment mechanism. Um, your unit of change is the entire app. So if you've had, you know, 20 commits since uh the last sort of release went out, then you're essentially testing all 20 things in that one hit. Your ability to sort of target the actual customers, it's a lot more precise when you're using feature toggles. So you can you know use all sorts of complex rules um and say that I don't know everyone from Germany who has this particular product in their basket um has this kind of experience and that's you know really hard to do via network traffic rules right the other is your ability then to to actually roll back um so to roll back from a canary um hopefully you're still in the process where you're sort of going through that canary you know process and you can roll it back um that could take you know minutes Maybe you have to redeploy the whole old old version. That could be minutes or or more. With a feature toggle, you know, you can do that in seconds. That's pressing a button and it happens immediately. Not only that, but you've kind of you've got more control, I guess, on when you sort of do that. So, with the with a deployment that you're doing um via via a standard versioned release, you're sort of tied to when that deployment takes place because when it takes place, that's when essentially your new feature is available. And as an application team, that means you need to know about exactly when it's taking place and make sure you're watching the logs at that point. And maybe you and 10 other teams who are shipping things at the same time um are all doing the same thing. Whereas with feature flags, your control, you basically got control over when that takes place. So you might ship the actual, you know, the assemblies and and that sort of thing on the Monday, but you release your feature on on Tuesday when you come in and you you can you've got the logs ready and you you've kind of reviewed what the next steps are. So this really makes things a lot easier to decouple releasing a feature from from deploying software. You know version deployments uh through Canary etc. They're really useful uh particularly if you're doing like infrastructure type changes where there is no kind of application toggle that's that's relevant there but you want to violate some changes to your infrastructure or your your process or potentially you know things like um things that will involve um schema changes and schema changes are the big
</details>

### 回滚策略与向前滚动

**主持人**: 数据库结构变更，这是任何渐进式交付中的大问题，这就是为什么问题总是“你准备好进行渐进式交付了吗？”来处理数据库结构变更。我想这一点是，应用团队需要非常成熟，我不是指不开愚蠢的玩笑那种成熟，而是指理解与此相关的所有问题，并知道如何以渐进、可控的方式发布这类变更，并分多个阶段进行。讽刺的是，这对我们 Octopus 来说实际上相当困难，因为我们的软件既是 SaaS 托管的，也有本地部署版本。因为我们两者都有，我们算是拥有两个世界最好和最坏的一面。在云系统中，如果你有 SaaS 产品，你可以完全控制哪个版本去哪里，所以如果你想做“扩展和收缩”，你可以分阶段进行整个过程，你知道在进入下一阶段之前所有内容都已更新。另一方面，对于自托管应用，客户会在他们自己的基础设施上安装它，你不知道他们运行的是什么版本，他们从哪里升级，所以他们可能从版本一直接升级到版本六。嗯，所以你并没有真正强制他们经历那个扩展和收缩阶段。另一方面，他们对何时升级有更多的控制权。所以你可以更刻意地确保他们在更改前进行备份，也许他们可以管理迁移，并接受在迁移和更新期间比 SaaS 产品能接受的更多的停机时间。

<details>
<summary>Original English</summary>
**Host**: list schema change that's this is the big problem in any like to be fair in any um progressive delivery um and this is why you know the question always is are you ready for progressive delivery? Um to do schema changes. I guess this is the point that um application teams kind of need to be really mature and I don't mean mature in terms of you know not telling silly jokes but mature in terms of understand all the problems are in place with this and know how to release these sort of changes in a gradual controlled fashion and do it over multiple stages that you know ironically is actually quite hard for us um at Oculus because our software is both SAS hosted so we have a a SAS offering that customers can use and we have an on-remise vision and there's kind of because we have both both sides um we kind of have the best and worst of both worlds you know in the cloud system if you've got um a SAS product you have complete control over what versions go where so if you want to do an expand and contract you can stage the whole process you know that it's all been updated before you kind of move to the next stage on the other hand for a self-hosted um application where they go in and they install it on their own infrastructure somewhere you don't know what version they're running and what they're coming from so they might upgrade from version one straight to version six. Um, and so you're not really forcing them to go through that expand and contract phase. On the other hand, um, you know, they've got a lot more control over when they upgrade. And so you can kind of be a little bit more deliberate about, you know, making sure that they do backups before they change and and, you know, maybe the down maybe they can manage that migration and accept a little bit more um downtime during migrations and updates and things like that than would actually be, you know, acceptable in in a SAS product.
</details>

**主持人**: 我们谈到了渐进式交付，你这样做是为了避免意外，如果出现回归、新错误或某些东西不工作，你希望尽早发现，希望只有少数客户遇到，或者即使不是 100%，你也有办法回去，如果是功能标志，你就隐藏它，如果是金丝雀部署，你就回到另一个版本。但还有一点，当事情出错时，你想进行回滚。我们能谈谈你见过的做得好的回滚，以及实际拥有一个真正的回滚策略需要什么吗？很多人谈论 CI/CD。有些人谈论功能标志。我很少听到关于回滚的讨论。

<details>
<summary>Original English</summary>
**Host**: So one thing about you know we talked about progressive delivery and you're kind of doing this to avoid surprises you know if if a regression goes out a new bug or something doesn't work you kind of want to c catch it early hopefully only a few customers have experienced it or even if it's not 100% you kind of and and and you have a way to go back uh to all you do is you you if it's a feature flag you you hide it if it's if it's a canary deployment you go back to the other one but There's also this thing where like when things do go wrong at some point you want to do a roll back. Can we talk about how have you seen roll backs done well and what does it take to actually have a real roll back strategy? Bunch of people talk about CI/CD. Some people talk about feature flags. I don't hear too much chatter about roll backs.
</details>

**罗伯特**: 是的，回滚。这总是一个敏感话题。我们有很多客户说，“为什么你们没有一个回滚按钮？我想回滚东西。为什么我们不能回滚东西？”就像在 Octopus 或其他部署软件中，他们说，“好吧，如果它能部署，我想做一个检查点，然后直接回滚。”

<details>
<summary>Original English</summary>
**Robert**: Yeah, roll backs. This is always a spicy one. We get a lot of customers who say, "Why don't you have a roll back button? I want to roll things back. Why can't we roll things back?" as as as in the deployment software like Octopus or anything else they like okay if it can deploy I want to like do checkoint and and like just just do a roll back
</details>

**主持人**: 没错，这能有多难？就做你...

<details>
<summary>Original English</summary>
**Host**: that's right how hard could it be just do what you
</details>

**罗伯特**: 能有多难？告诉我。

<details>
<summary>Original English</summary>
**Robert**: how could it be tell me
</details>

**主持人**: 能有多难？嗯，这就是问题所在。在一个完全无状态的系统中，这相当直接。如果你有一个完全无状态的系统，GitOps 在这方面非常擅长，你会在你的仓库中有那个定义，如果它是完全无状态的，你可以做一个 `git revert` 并推送，它就会回去。

<details>
<summary>Original English</summary>
**Host**: how could it be well this is the the problem right so um in a completely stateless system that's you know pretty straightforward if you've got a completely stateless system and you know this is something that githops is really good at where you'll have that definition sort somewhere in your repo if it's completely state stateless you can do a um a git revert and push it and it'll go back.
</details>

**罗伯特**: 现实是，对于大多数系统，你可能有一些状态。

<details>
<summary>Original English</summary>
**Robert**: The reality is for most systems out there, you've probably got some state
</details>

**主持人**: 状态指的是...

<details>
<summary>Original English</summary>
**Host**: state being
</details>

**罗伯特**: 状态指的是数据库。它可能是任何你不能轻易撤销的信息，因为如果你回滚，现在你的代码与不同步的数据库结构对话。如果你有数据库结构迁移，比如说在正常部署中，你可以同时提供一个辅助的“反迁移”来撤销更改，但同样，这并不总是可能的。你需要处理那个数据集。

<details>
<summary>Original English</summary>
**Robert**: state being databases. It could be um you know any sort of any sort of information that you can't necessarily just kind of undo I guess because if you roll it back and now you've got your code talking with the schema of the database that's not in sync you can uh provide schema uh if you've got a schema migration let's say in a normal deployment you can provide alongside that a secondary sort of anti-migration that kind of undoes the change but again that's not always possible. you need to do is what are you going to do with that data set?
</details>

**主持人**: 我们已经在基本上试图建议客户，你永远要避免谈论回滚。永远是向前滚动。

<details>
<summary>Original English</summary>
**Host**: We we've gotten pretty far in basically trying to um advise customers that you never you want to avoid ever talking about roll back. It's always roll forward.
</details>

**罗伯特**: 所以如果有错误，就向前滚动。做一个更改。尽快把你的更改放进去。这就是快速反馈循环重要的地方，对吧？这就是热修复流程的作用，对吧？我们都知道在标准流程中，你想走开发、预发布、生产，也许有审批流程会减慢速度。但如果你有一个重大错误需要“回滚”，有时最安全的做法实际上是制作那个版本的热修复，并尽快推送出去，你的瓶颈可能是构建流水线或其他什么，但根据你对风险的承受能力，你可以更快地解决它。现在，显然，如果失败本身只是来自部署过程中的某个机制或链条中更下游的地方，那么你的恢复时间会快得多。但这个想法是，如果我在版本二中遇到失败，我的回滚不是回到版本一。而是去到版本三，并确保我在版本三中包含了那个修复。这就是那种事情，当我们与客户交谈时，有些人会说，“是的，我们经常回滚，如果有问题的话。”然后当你问他们，如果遇到数据库结构变更怎么办，他们就会停下来，意识到他们只是运气好，从来没碰到过，对吧？

<details>
<summary>Original English</summary>
**Host**: So if there's a bug, okay, roll forward. Get a change. Yeah. Get get your change in um as soon as possible. This is where fast feedback loops are important, right? You know, this is what the hot fix processes are for, right? So we all know that in a standard process you want to go devstaging prod and maybe it's maybe you've got you know um approval processes and slows down etc. But if you've got a sign significant bug that you need to kind of quote unquote roll back sometimes the the safest thing to do is actually make a hot fix to that that version and and push it out sort of as quick as possible and your bottleneck might be the the build pipeline or whatever but depending on sort of your appetite for risk there you can resolve that sort of a lot quicker. Now obviously if you if the failure itself is just from some um mechanism in the deployment process itself or somewhere further down that chain then your your time to recover is going to be a lot quicker. But it's this idea that you know if I've got a failure in version um version two my roll back isn't to go to version one. It's to go to version three and make sure I've got that fix in in version three. It's the sort of thing that um you know when we we talk to customers and some of them go yeah we roll back you know we roll back all the time if there's a problem and then when you ask them what do you do if you've got a schema change they kind of stop and and realize that they've never it's just sheer luck that they've never sort of run into that right
</details>

**主持人**: 是否可以这样说，如果涉及到业务逻辑或非无状态的东西，你想要向前滚动？因为如果是无状态的，或者只是应用逻辑，你有一段代码说“如果这样，否则那样”，你意识到有一个错误，只要它不触及数据库结构或数据，你就可以直接还原它。

<details>
<summary>Original English</summary>
**Host**: is it fair to say that you want to roll forward if it involves business logic or something that is not stateless because if if it is stateless or if it's application logic you know you have a code that says if this else then and you realize there's a bug where you can just revert it as long as it doesn't, you know, touch the the schema or or the the data.
</details>

**罗伯特**: 是的。我的意思是，在理想情况下，你的还原是通过功能标志进行的，对吧？你点击一下，通过改变代码路径来还原。这就是为什么我总是说功能标志。所以，这是一个很好的工具，用于进行渐进式交付，因为，你知道，发布那个功能有多容易，通常回滚它就有多容易。现在，你仍然会遇到一些数据库结构问题等。如果你正在做一个更改，你的代码路径中有部分期望一个而不是另一个，你需要考虑到这一点。

<details>
<summary>Original English</summary>
**Robert**: Yeah. I mean, in an ideal world, you're reverting is through a feature flag, right, that you click and you're essentially reverting by changing the code path. And this is why I always say um feature flags. So, kind of a nice a nice tool to use for um doing this progressive delivery because, you know, it's just as easy just as easy it is to roll out that feature. You can typically roll it back. Now, you're still going to have some of those problems with schema issues, etc. If you know if you're making a change and you've got parts of your code path that expect one and not the other, you're going to need to account for that.
</details>

**主持人**: 但你甚至可以在功能标志内部处理这个问题。

<details>
<summary>Original English</summary>
**Host**: But you can even account for that inside the feature flag.
</details>

**罗伯特**: 没错。是的。所以这是你理想中管理它的方式，这样，关于你走哪条路径，功能标志与外部数据库结构的任何版本都是自洽的。

<details>
<summary>Original English</summary>
**Robert**: That's right. Yeah. So that that's the way you sort of ideally sort of manage that so that within regards to which path you go down the feature flag, it's kind of self-consistent with whatever version of the actual sort of database schema that's out there.
</details>

**主持人**: 所以我想，你使用的功能标志越多，你可能遇到的意外就越少，但构建和移除都需要额外的工作。

<details>
<summary>Original English</summary>
**Host**: So I guess the more feature flags you use, the fewer surprises you might have, but it's a bit of extra work both to build and also to remove.
</details>

**罗伯特**: 是的。一旦你开始大量使用，你的代码库中就会到处都是功能标志。我在 Uber 见过这种情况。

<details>
<summary>Original English</summary>
**Robert**: Yeah. you you get stuck with still feature flags all across your codebase once you start to use a lot. I saw this at Uber.
</details>

**主持人**: 是的。百分之百同意。所以当你给你的应用添加一个功能开关时，嗯，我们在 Octopus 显然在代码中大量使用功能开关，我们使用 **OpenFeature** 作为与之交互的框架和 SDK。但我们基本上围绕它构建了一个包装器，其中代码中的开关本身，我们提供了一些关于哪个团队拥有它的细节，嗯，那个团队会设置一个过期时间。当那个时间过去后，不会发生什么坏事，但通过 CI 过程的某些部分，如果那个时间已经过去，我们可以向那个团队发送通知，说“嘿，这个开关似乎不再使用了”。所以具体的机制不那么重要，更重要的是确保，如果你添加了功能开关，很容易忘记它，因为你开始推出它，然后就忘了。而且，你想把它留在那里一段时间以防万一，以防你需要回滚。能够了解一个开关存在了多久，是帮助维护这种卫生的关键部分。现实是，即使在 Octopus，我们也有很多，我知道我有很多在那里，我敢肯定如果我登录，我可能会收到一堆通知让我移除它们。你知道，当我们使用代码中的“园艺”比喻时，对吧？这是一种操作，这是“除草”，对吧？你需要持续关注它。甚至在 AI 方面也有一些机制，理想情况下，如果你使用功能开关，你可能有很多围绕它的可观测性、指标和日志记录，有一些工具可以让你跟踪一个开关最后一次被评估的时间。嗯，这给了你那个信号。嗯，类似地，你可能从代码中移除它，因为通常当你想要移除一个功能开关时，你希望先从代码中移除，然后再接触你的实际开关系统。所以有一个机制，一旦你从代码中移除它，嗯，它可能需要两周才能完全发布到生产环境。所以你不想在此之前删除它，到那时你已经忘记了移除它的事实。嗯，所以拥有跟踪那个变更通过系统的机制，当它到达实际使用它的生产环境时，可以显示“好的，那个代码已经发布出去了，移除开关是安全的”，因为功能开关信息存在于两个地方，对吧？它在代码中，也在你的平台中。

<details>
<summary>Original English</summary>
**Host**: Yes. Yes. 100 times. Yes. So when you've adding a feature toggle to your um app itself. Um so we at Ocus we obviously use feature toggles in our code quite a lot and we use open feature as like the um the the framework the SDK to interact with it. But we essentially have built a wrapper around it where um the the toggle itself within the code is um sort of we provide some details about which team owns it um and that team sets an expiry on it. Now the expiry itself when that time passes nothing bad will happen but through parts of the CI process if that time has passed we can send a notification to that team and say hey it looks like this toggle is no longer used. So the specific mechanics don't matter as much, but it's more a matter of making sure that, you know, if you're adding feature toggles, it's really easy to forget about it because you start rolling it out and you kind of forget about it. And you know, you want to keep it in there just in case for a while in case you need to roll it back. And having the ability to understand how long a toggle has been there, um, is a is kind of a key part of helping to maintain that that hygiene. Now the reality is even at Octopus we've got a bunch in I know I've got a bunch in there that um I'm sure if I was to log in I'd probably get a bunch of notifications to remove you know when we use that gardening metaphor in code right this is this is one of those sort of operations this is weeding right you need to just kind of keep on top of it there are some mechanisms around even in in lie of the AI side which will um you know ideally if you're using feature toggles you you probably got a bunch of um observability and metrics and logging around it and there are some system some tools out there that will allow you to keep track of when the last time a toggle was kind of evaluated. Um, and that kind of gives you that that signal. Um, similarly, you know, you might remove it from the code because typically when you want to remove a feature toggle, you want to remove from the code first before you touch your actual sort of toggle system. And so having a mechanism so that once you remove for it from the code, um, you know, it might take two weeks before it makes all the way out into production. So you don't want to delete it before then, by that time you've kind of forgotten about the fact you removed it. Oh yeah. Um and so having mechanisms that will keep track of that change I guess going through the system um and when it reaches the environment where um you know production where it's actually being used can kind of show okay that code's gone out that's you know remove the toggle it's it's fine and safe to actually remove the configuration because you've got that feature toggle information in two places right you've got it in the code and you've got it in your your your your platform
</details>

### 开发环境的演变

**主持人**: 我们能谈谈开发环境是如何演变的吗？我们谈到了 CI/CD，但我更感兴趣的是，你从只有一个环境，后来可能有预发布环境之类的，在你合作过的所有团队中，你看到了什么样的演变？

<details>
<summary>Original English</summary>
**Host**: can we talk about how development environments evolve we talked about CI/CD but I'm interested more in you know you you go from like you have one environment later you might have staging or something and what evolution have you seen across the all the teams that you work with all these hundreds or thousands of teams
</details>

**罗伯特**: 是的，我不确定是否有一个特定的模式。我的意思是，最常见的可能是开发、测试、生产。

<details>
<summary>Original English</summary>
**Robert**: yeah I'm not sure if there is one particular pattern there I mean I think you know most most common is you know dev test prod um
</details>

**主持人**: 所以这三个不同的环境。

<details>
<summary>Original English</summary>
**Host**: so these three different environments
</details>

**罗伯特**: 是的，我的意思是，即使这样，我认为也可能是对所有类型的严重简化。

<details>
<summary>Original English</summary>
**Robert**: yeah and I mean even that I think is probably a a a gross simplification of all the kind of
</details>

**主持人**: 开发指的是我的本地机器。

<details>
<summary>Original English</summary>
**Host**: and dev meaning my local machine.
</details>

**罗伯特**: 在 CD 的语境中，开发通常是第一个集成点。所以它有点像测试，通常客户会让测试与生产环境或某种清理过的数据源保持合理同步。这样，无论是 QA 测试人员、产品团队还是其他人，都可以去审查代码。开发几乎就像是第一个集成点，检查部署过程本身是否基本工作，或者是否有任何根本性的问题。我认为现在我们越来越多地发现开发在这方面不那么有用了，我们看到更多的是像**临时环境**这样的东西的增长。所以这个想法是，我作为一名工程师，在一个功能分支上开发某个功能，嗯，我想评估它是否真的在做我们期望它做的事情，但不仅如此，我希望我的团队其他成员也能看到它工作。嗯，如果它在我机器上运行，让别人访问并不容易，然后我可能想完全切换上下文，去做完全不同的事情。所以临时环境就是这个想法，从我的分支，在合并前，我想启动一个完整的环境，嗯，基本上从零开始，理想情况下包含运行我正在构建的这个特定组件所需的所有依赖项。嗯，然后我想把我的应用部署到那个环境中，就像它是一个正常的、功能齐全的环境一样。嗯，一旦可用，我想能够访问它，比如如果它是一个 Web 应用，也许它会给我一个 URL，我可以摆弄它，把它传给别人，其他人也可以评估。然后在我合并那个 PR 的那一刻，再把它拆除。你知道，拥有多个测试环境是很常见的，因为，我的流水线中有很多东西在跑，我有三个测试人员。所以，让我们有三个环境。嗯，这样他们可以同时各有一个，或者你经常会看到一个单一的测试环境和一堆测试，他们都需要协作看看谁当前有权限访问系统等等。而使用临时环境，你可以基本上每个功能都有一个功能齐全的部署。所以，这又是关于加快反馈过程，对吧？所有这些过程都是为了加快反馈过程，以便更早地发现那些失败、问题或错误。几年前，有一段时间云开发环境被广泛讨论，这个想法是，作为一名开发者，你在云中启动一个环境，比如你的 Visual Studio Code 连接到它，或者你只是在线登录，它就会启动所有依赖项，通常用容器完成，这也让我想起了这个，还有像预览环境之类的东西。但不知何故，感觉这两个讨论都平息了，也许是 AI，也许是别的东西。但我的意思是，技术就在那里，对吧？我们有容器。你可以把东西打包在一起。我敢肯定这取决于具体情况，但都是可行的。

<details>
<summary>Original English</summary>
**Robert**: Dev in the case of CD is often like the the first point of integration. So it's kind of um test often customers will keep test kind of reasonably in sync with let's say production or some sort of sanitized data source. So that way that whether it's the QA testers or the um product team or whatever can go and review the code. dev is almost like the first po point of of of integration that is it actually is the deployment process just at its core actually working or is anything fundamentally broken at all. I think more and more now we're finding that dev is less useful um in that respect and what we're seeing is more the um growth of things like ephemeral environments and so this is the idea that you know I as an engineer I'm running some sort of feature on a feature branch um and I want to kind of evaluate that it's actually doing what it what we're expecting it to do but not only that I need I want the rest of my team to be able to see it working and um you know if I've got it running on my machine it's not exactly easy to sort of um yeah give other people access I guess and then I want to move I may want to you know completely context change move on to something something completely different. So ephemeral ephemeral environments is this idea that from my my branch premerge I want to spin up a whole environment um essentially from scratch ideally with with whatever dependencies are required to sort of run this particular component that I've been building. Um, and then I want to basically deploy my um, app into that as if it was a normal full-fledged environment. Um, as once that's available, I want to sort of have access to, you know, if it's a web app, maybe it gives me the URL and I can poke around it and hand it around and and other people can kind of evaluate. And then the moment I kind of merge that PR, tear it down again. You know, it's quite common to have multiple test environments because, you know, I've got a lot of stuff going through my pipeline and I've got three testers. So, let's have three environments. Uh so they can all sort of have one at once or often you'll see a single test environment and a bunch of tests and they all kind of need to to um collaborate to see who's got access to the system at the moment etc etc. Whereas with ephemeral ephemeral environments it doesn't roll off the tongue. With ephemeral environments you can um essentially have a a full-fledged deployment per per feature. And so again, that's about speeding up that that feedback process, right? Again, all these processes are all about speeding up that feedback process to get the the the catch those failures or issues or or bugs or whatever. So sooner. There was a time a few years ago where cloud development environments were really talked about a lot which was the idea is as a developer you have an environment spin up in the cloud you're let's say your your visual studio code connects to it or or maybe you just log in online and it spins up all the dependencies often times done with containers which reminds me of this as well and there's also like like preview environments but somehow it feels that both that discussion and this one kind of died down maybe it's AI maybe it's something else But I mean the technology is there, right? We have containers. It's you can you can package things together. It's it's I'm sure it depends, but it's all doable.
</details>

**罗伯特**: 是的，它确实会变得棘手。这又是那种说起来容易做起来难的事情之一。嗯，对于简单的情况，它可能会变得棘手，当你知道，如果我的“环境”中不仅仅有一个应用，我如何确保它有我需要的所有数据来验证。所以它可能会变得棘手。

<details>
<summary>Original English</summary>
**Robert**: Yeah, it does get tricky. It's this is again one of those sort of things that's really easy to talk about. Um for simple cases, it it can get tricky when you know what if I've got more than just a single app in my kind of quote unquote environment and how do I make sure it's got all the data I need to validate. So it can get tricky. So
</details>

**主持人**: 或者如果你有一堆有状态的服务。

<details>
<summary>Original English</summary>
**Host**: or if you have a bunch of services that have state.
</details>

**罗伯特**: 没错。正是如此。所以它确实带来了一些复杂性，但我认为，作为一个应用团队，你获得的好处，特别是当你的团队中仍有工程师在编写代码时，就是加快了反馈过程。嗯，现在，随着 AI 代理无处不在，这甚至更好，因为从某种意义上说，验证的最佳方式之一，我们有代码审查，AI 代理生成代码，你查看代码，但直接确认这个东西能工作不是更好吗，特别是当它有 UI 的时候？

<details>
<summary>Original English</summary>
**Robert**: That's right. Exactly. So um there are sort of complications that it does bring but the I guess the the benefits that you get as a as an application team um particularly you know application team where you've still got engineers writing code um is is sort of speeding up that that feedback process I guess. Well, now with with AI agents everywhere, that's even better cuz uh in a sense that if one of the best ways to validate, you know, we have code reviews and AI agent generates and you look at the code, but isn't it not better to just confirm that this thing works, especially when it has a UI?
</details>

**主持人**: 没错。我认为即使在那个世界里，你有 AI 代理在构建代码和验证代码，任何你想要那个 AI 代理验证它做了什么的情景，嗯，你本质上是在谈论临时环境，即使它不暴露给人，因为它自己做测试和探索，无论它以何种形式进行，那仍然是这些环境之一，对吧？它是临时的，它启动，你有一些配置过程，嗯，然后理想情况下，一旦工作完成，你就把它拆除。

<details>
<summary>Original English</summary>
**Host**: That's right. I think even in that world where you've got AI AI agents kind of building the code and validating the code any sort of uh scenario where you want that AI agent to kind of validate what it's done um you're essentially talking about ephemeral environments even if it's not exposed to people because it's doing its own testing and poking around um in whatever shape or form um that it's doing that still is I guess one of these kind of environments right it it's ephemeral it spins up you've got some sort of provisioning process um and then ideally once the job's done you just kind of tear it down.
</details>

### 运营大型基础设施平台

**主持人**: 我有兴趣了解更多关于运营大型基础设施平台的现实情况，你正在做的一个大项目实际上是 Octopus Deploy 的 SaaS 产品。那是什么样的？运营一个运行所有这些部署流程、所有这些 CD 的东西，你可能有很多不同的事情，挑战是什么？

<details>
<summary>Original English</summary>
**Host**: I'm interested in learning more about the reality of operating a large infrastructure platform and you know one big one you're working on is actually Octopus deploys SAS offering. How does that look like and what are the challenges of of you know like running something where you're running all of these deploy processes all all these CD you probably have a bunch of different things. What is it like?
</details>

**罗伯特**: 嗯，目前我不在构建那个的团队里，但我可以从历史和背景中提供一些信息。最初，当我们决定提供 Octopus SaaS 产品时，我想大概是 2020 年左右。当时全是虚拟机。所以每个客户基本上都会得到一个启动的虚拟机，嗯，Octopus 自安装应用会安装到那个虚拟机上，他们会得到一个完整的虚拟机来运行工作负载等。嗯，那非常不划算。我们每个客户每月要花费大约 100 美元，而他们支付的大概是 20 美元一个月。但整个过程更像是一个实验，看看是否有需求。嗯，值得称赞的是，Paul 很乐意拿出信用卡来经历这个过程，看看这是否是我们想走的方向。这是否会成为公司的一个可行方向？因为这是一个很大的步骤，对吧？从构建你可以分发出去、让人们下载并自己管理的软件，到...

<details>
<summary>Original English</summary>
**Robert**: So um at the m at the moment I'm not on the team that sort of builds that but I can give some of the the context I guess from history and kind of um context there. Originally when we first sort of decided to sort of provide a Octopus SAS offering um I don't know I think it was 2020 or something like that. It was all VMs. So every customer would basically get a VM spun up and we would virtual machine virtual machine. Yep. and the um Octopus um you know self-installed app would basically get installed onto that VM and they'd get a whole VM for running workloads on etc. Um and that was very much not cost effective. It was costing us something like a hundred bucks per customer per month and they were paying I don't know $20 a month or whatever it was. But this whole process was more an experiment to see was there a demand. Um, and to his credit, Paul was happy to sort of hand, you know, pass out the credit card to kind of go through this process to see that is this actually the direction we we want to go. Is there a is is this something that going to turn into a viable sort of direction for the company? Because it's a big step, right? Going from building software that you can kind of hand out and people can download and manage themselves to
</details>

**主持人**: 它基本上就是自托管，或者在你自己的基础设施上运行。

<details>
<summary>Original English</summary>
**Host**: it was like pretty much self-hosted or like run on your own infrastructure.
</details>

**罗伯特**: 没错。是的，没错。所以需求是存在的。嗯，所以在第一次实验后不久，我们基本上又从零开始，我和其他几个工程师一起开始把它构建在 Kubernetes 上。嗯，Octopus 本身在那个领域，我们有所谓的“礁石”。你会发现 Octopus 里的一切都有章鱼或航海类的名字。所以“礁石”基本上是一种基于单元（cell）的架构，包含特定客户实例所需的所有资源。嗯，有些是共享的，但它被分解成独立的单元。所以一个“礁石”会包含集群、Azure 数据库等。嗯，每个客户实例现在都在那个集群的一个 Pod 中运行。在那个项目中，我当时在负责转换它，使其能在 Linux 和容器内运行，而另一个人在构建动态工作器基础设施。嗯，所以我们几个人就进去，真的把它启动并运行起来，这样我们就可以开始前进，我想，停止亏损。快进到今天，现在有一个完整的团队在支持它，我们有几千个客户在上面，我们每个月运行成千上万次部署。所以现在我们正在做的一个项目是让 Octopus 的部署过程本身更具弹性。这意味着，目前当一个部署启动时，过程中的很多步骤，因为它是一组命令式的步骤，很多都存储在内存中，这意味着每当我们想要升级时，我们需要停止运行任务一段时间，这样我们可以杀死它们的实例并重新启动一个。Octopus 本身目前在不同升级之间没有零停机时间。所以之间会有一点停机时间。我们想减少它，并尽可能接近零，同时认识到，从 5 分钟的停机时间降到 1 分钟，那只是工作，对吧？你可以移动东西，也许可以改变架构。但从 10 秒降到零是一个更大的转变。我不确定我们是否以及何时能达到，但嗯，是的，目前确实有这么大的努力，使整个过程更具弹性，以改善和减少发生的停机时间，以便能够更快地执行升级等。

<details>
<summary>Original English</summary>
**Robert**: Exactly. Yeah, that's right. And so the the demand was there. So um not long after that sort of first experiment we basically started from scratch again and I worked with a couple of the other engineers back then to start building it on um Kubernetes um and so octopus itself in in that space we have what we call kind of a reef. So what you'll find is everything in octopus we've always got of octopus or nautical kind of names around it. So a reef is basically a way of it's this cell-based architecture where contains all the resources that are needed for that particular customer's instance. Well, some of it's shared, but it's kind of broken down into individual cells. And so a reef will contain, you know, the cluster, an Azure database, etc. Um, and each customer instance is running now in a in a pod in that um cluster. And so as part of that project that was when um I think I was working on converting it so it could run on Linux and inside containers and someone else was building the dynamic worker infrastructure. So um there were a couple of us that kind of just um got in and yeah really just got it up and running so that way we could kind of start moving forward and and I guess stop stop losing money. Fast forward to today now there's an entire team that's kind of backs that and we've got you know several thousand customers on it and we run you know many many thousands of deployments um every every every month and so now what we're trying to do is there's a project at the moment to basically make the um Octopus deployment process itself more resilient so what that means is at the moment when a deployment kicks off a bunch of the the the process so as a it's kind of a um imperative set of steps a bunch of that is stored in memory which means that whenever we want to do an upgrade um we need to essentially um stop running tasks for some period of time so we can kill their instance and spit another one back up. Um Octopus itself at the moment um doesn't um sort of have zero downtime between upgrades. So there's a bit of downtime between that. We kind of want to reduce that and get that as close to as close to zero as possible with the realization that you know going from downtime of 5 minutes to 1 that's that's just work right that's you know you can move things around you can maybe change the architecture going from 10 seconds to zero is is a much bigger shift um I'm not sure if if and when we'll get there but um yeah there's definitely this this big effort at the moment to make the whole process a lot more resilient to basically improve and reduce the amount of downtime that takes place so can um kind of perform upgrades quicker etc.
</details>

### SaaS 与本地部署的挑战

**主持人**: 你们做的一件有趣的事情是，你们有 SaaS 产品，但也有本地部署产品。这带来了哪些有趣的工程挑战？很多公司决定只做 SaaS，因为现在他们可以集中控制一切。但显然，两者都做意味着更多的工作和更多的麻烦。

<details>
<summary>Original English</summary>
**Host**: One interesting thing you do is you have a SAS but you also have an on-prem offering. What are interesting engineering challenges that come from that? A lot of companies have decided to just like honestly just move to move to SAS because now they control everything centrally. I think Jer did this uh or may maybe they're they're doing it which is a well-known one but clearly it's just a lot more work and a lot more headache to have both.
</details>

**罗伯特**: 是的。我们之前稍微触及了一个大问题，那就是当我们想要推送任何更新到云端时，因为我们控制整个过程，我们可以推送出去。所以我们那里有一个逐步推出的过程。嗯，因为每个客户都在他们自己的实例上，我们可以逐个部署。嗯，发布一个更改可能需要几天时间。但本地部署就是另一回事了。嗯，实际上，我前段时间查了一些相关数据，发现平均需要大约 200 天，我们 50% 的本地部署客户才能获得，比如说，我今天发布一个新更改，平均需要 200 天才能让 50% 的客户获得。

<details>
<summary>Original English</summary>
**Robert**: Yeah. Yeah. And we touched on one of the big problems here a little earlier is that when we want to push out any updates, you know, to cloud because we control the whole process, we can push it out. And so we have a sort of a gradual roll out process there. Um because each customer is on their own instance, we can sort of deploy each one individually. Um and that may take I a few days to let's say roll out a change. On prem though is is kind of another matter. So um actually I was digging into some of the stats around this a little while ago and found it took about 200 days for on average% 50% of our customers on prem to to get let's say let's say I ship a new change today takes about 200 days for on average 50%.
</details>

**主持人**: 那是半年。

<details>
<summary>Original English</summary>
**Host**: It's half a year
</details>

**罗伯特**: 但然后那里几乎有一个指数衰减，需要 400 多天才能让 75% 的客户获得。所以就是这样一个曲线，我的意思是，我们有客户仍在运行 5、6、7 年前的 Octopus 版本。所以每当我们发布一个新更改时，我们需要基本上确保 Octopus 能从 2023.1 版本工作到 2026.4 版本，所以我们在数据库结构升级等方面有更多的包袱，并确保整个过程实际上是可行的。

<details>
<summary>Original English</summary>
**Robert**: but then there's kind of like almost an exponential decay there where it takes 400 and something days for 75% to get it. So just there's kind of this curve where I mean we've got customers that are still running you know versions of Octopus from 5 6 7 years ago. And so whenever we ship a new change we need to basically make sure Octopus will work from version you know 2023.1 to 2026.4 and so there's a bunch more baggage I guess that we have in terms of like um schema upgrades and making sure that that whole process actually is achievable.
</details>

**主持人**: 但你们为什么这么做呢？很多初创公司会说，“去他的，我们不支持所有版本。”这在移动端也会发生。这样做的好处是什么？感觉你们在这点上是在逆潮流而动。

<details>
<summary>Original English</summary>
**Host**: But why do you do it? A lot of startups will be like screw it, let's let's not support all versions. This even happens on on mobile. What's the what's the benefit? And this it feels like you're kind of swinging against the crowd with this one.
</details>

**罗伯特**: 我们的大多数客户仍然在使用本地部署。所以，这是银行、金融机构、政府等，他们希望完全控制系统。他们希望在自己的硬件上运行。他们可能使用自己的云或其他东西来运行，但他们希望管理整个过程，并控制升级、停机时间等。所以，这当然并不罕见，我认为短期内不会消失。至于升级支持，嗯，在过去的几年里，我们实际上正在经历这个过程，我们在弃用功能等方面变得更加自信，并砍掉旧的能力，部分原因是我们在那个过程中完全接受了功能开关。我认为我们在移除一些老客户可能会怀念的能力方面变得更大胆了，但我认为从长远来看，自托管不会消失。这又是那种事情，我经常听到“一切都在云端，我们都在云端”。但现实是，有很多公司，对他们来说，这没有意义，或不可行，或不符合合规要求等等。另外，我认为这也提醒我们，如果你构建也能在本地运行的基础设施软件，你的竞争可能会少得多，因为似乎有需求，公司会说，“我们想给你钱，以便我们能在本地运行。”

<details>
<summary>Original English</summary>
**Robert**: The majority of our customers are still on prem. And so this is, you know, you're talking about banks, um, financial institutions, governments, things like that where they want full control over the system. They want to run it on their own hardware. Now they may use their own cloud or whatever to run it, but they want to manage the whole process and be in control of, let's say, upgrades or downtime or or things like that. So, it's certainly um not it's certainly not uncommon and I don't think that's going away um anytime soon. As for the upgrade support, um we're kind of going through this process actually in the past couple years where we've been getting a lot more I guess confident with deprecating features and things like that and just kind of cutting cutting loose old capabilities and part of that has come from you know fully embracing feature toggles as part of that process. I think we're getting a little bit braver in terms of, you know, um, removing capabilities that perhaps older customers may may miss, but I don't think that in the long term self-hosted will will kind of go away. This is one of the sort of things again where I think it's it's really common to hear, you know, everything's in the cloud, we're all in the cloud. Again, the reality is there's a lot of companies out there where for them it's just doesn't make sense or it's not viable or it's not, you know, it doesn't meet compliance requirements or whatever the case may be. Also, it's kind of a reminder, I think, that you actually might have a lot less competition if you build infrastructure software that also runs on prem because it sounds like there's a demand where companies are like, we want to give you money
</details>

**主持人**: 为了让我们能在本地运行。我敢肯定，如果没有其他选择，他们中的一些人也会用 SaaS。但无论如何，构建 SaaS 更容易。所以竞争会更激烈。所以，如果你是一个企业家或软件工程师，想做生意或创业，这可能给你一个优势。

<details>
<summary>Original English</summary>
**Host**: in order for us to run on prem. And I'm sure some of them would do SAS if there's no other alternative. But for SAS, it's it's easier to to build anyway. So, there'll be more competition. So, if you're an entrepreneur or if you're a software engineer thinking to do a business or start a business, it might give you an edge. Yeah, that's that's right.
</details>

**罗伯特**: 听起来你们有很多客户，比如那些五年没有升级你们软件的客户，一方面你会说，“天哪，他们在干什么？”但他们可能只是对它很满意。如果他们作为企业继续付钱给你，他们是你最忠诚的客户。你明白我的意思吗？

<details>
<summary>Original English</summary>
**Robert**: It sounds like that a lot of your customers, you know, the ones who have not upgraded your software for, let's say, five years, on one end you say like, "Oh my gosh, what are they doing?" But they might just be happy with it. And if they keep paying you as as a business, those are some of the your most loyal customers. You see what I mean?
</details>

**主持人**: 没错。就是这样。我的意思是，我记得当我在之前的工作中使用 Octopus 时，或者我们任何人拥有任何其他正在运行、可能在你本地运行的软件时，如果它只是工作，为什么要碰它呢？所以，这有点是我们存在的祸根，因为它让我们烦恼。我们想发布功能，给他们所有这些很棒的新东西。嗯，但另一方面，对于像他们的部署系统这样关键的东西，很多客户一旦让它运行起来，他们就会退后一步，说，“好吧，就让它这样吧。”

<details>
<summary>Original English</summary>
**Host**: That that's right. And this is the thing. I mean, I remember when I worked in um like when I worked in the previous job that used Octopus or any of us who have any other sort of, you know, software that you've you've got running potentially you've got running locally, if it just works, why why why touch it, I guess? And so, it's kind of the bane of of our existence because it annoys us. We want to ship the features and give them all these great new things. Um, but on the flip side, you know, particularly for something as critical as, you know, their deployment system, a lot of customers once they've got it running, they kind of step away and and go, "Okay, let's let's just let it let it be."
</details>

**罗伯特**: 这在 AI 领域也在发生，例如，我刚读到 **Cursor**，他们最新的编码模型，好像每 5 小时升级一次，这太惊人了。它不断变得更好。然而，有些客户，一旦你有一个 LLM 并且它为你工作，你已经调整了它，你有指令，很好。但经常发生的情况是，一个新版本或大版本发布，它就不工作了。我假设会有更多的团队、公司、企业会说，“看，对我来说，花钱固定这个东西，或者在我自己的基础设施上运行它，让它保持原样，然后我决定什么时候想改变它，是值得的。”只要它，你知道，如果它没坏，就不要修它。

<details>
<summary>Original English</summary>
**Robert**: And it keeps happening with AI as well in the sense that uh, for example, I just read that cursor, their latest coding model, it's it's upgraded like I think every 5 hours, which is amazing. It keeps getting better. However, you know, there are customers who once you have an LLM and it works for you, you've kind of tuned it, you have the instructions, great. But often times what happens, a new version comes out of a model or major version and it stops working. And I I assume that there will be more teams, companies, businesses who are like, look, it would be worth for me money to kind of pin this thing or to run it on my own infra and just have it stay as is and then I will decide when I want to change it as long as it, you know, if if if it's if it ain't broken, don't fix it.
</details>

**主持人**: 没错。嗯，我认为值得称赞的是，Octopus 在帮助客户方面有着非常好的历史，即使他们使用的是较旧的版本，有时甚至到了支持团队想说“他们用的是旧实例，告诉他们升级才能修复”的地步。嗯，但支持团队在帮助意愿方面是首屈一指的，而且正如你所说，如果他们愿意付钱给我们，我有什么资格说不呢？

<details>
<summary>Original English</summary>
**Host**: That That's right. And um I think to Octopus' credit, I think we have a um a really good history at sort of helping customers even when they're kind of on those older sometimes to the extent of wanting to say the support team just they're on old instant like tell them that to to get the fixed upgrade. Um but support team are you know I think second to none in terms of their their willingness to help and as you said if they're willing to pay us who am I to to say no?
</details>

**罗伯特**: 是的。我的意思是，这是一种商业策略，但我认为它很好地提醒了我们，并非只有一种模式。尽管我认为 SaaS 正在吞噬世界，我们听到也看到了这一点，但很高兴看到并非只有这一种模式。

<details>
<summary>Original English</summary>
**Robert**: Yeah. I mean, it's it's a business strategy, but I think it's just a nice reminder that there's not just one size and like even though I think SAS is eating the world and we're hearing it and we're seeing it, it's nice to see that it's it's not just that.
</details>

### 给工程师的建议与书籍推荐

**主持人**: 作为结束语，如果我是一名软件工程师，想要超越持续交付、持续部署，进入渐进式交付，你能给我什么建议？

<details>
<summary>Original English</summary>
**Host**: As closing, uh, if I'm a software engineer and I would like to move beyond continuous delivery, continuous deployment and go into progressive delivery. What pointers can you give me?
</details>

**罗伯特**: 是的，我想就从某件事开始吧，对吧？从添加一个功能开关开始。一开始可能会害怕，“啊，它在生产环境。如果我切换这个，我会破坏生产环境。”你知道，知道你在运行系统的左侧，如果你发布代码，一切都会被测试捕获，这很舒服。但是，如果我切换它，会发生什么？这有点像毒品，对吧？一旦你开始做，你就不想停下来。这就是为什么我们有像功能开关这样的卫生问题，对吧？添加它们很容易，最终反而会出现相反的问题，即你如何控制自己？你如何停止？所以，我想说，就开始做吧。添加一个，并在你推出它时留意它，看看结果。现实是，我通过功能开关发布过带有错误的功能，对吧？发布一些东西并打开一个功能，然后说，“好的，酷。客户有了它。”这是一回事。当你做相反的事情时，情况就完全不同了。如果你发布了一些东西，但有问题，你可以立即找到开关并将其关闭。你知道，过去你有多少次这种恐慌，“哦，不，我发布了什么东西。我不知道哪里出了问题。”特别是当你处于那种状态时，也许你在凌晨 2 点被叫起来，因为你正在值班，你不知道下一步该做什么，你有点恐慌，我是构建一个新东西，还是以某种方式强制重新部署？所以，拥有能够拨动那个开关的能力，能让你立刻冷静下来，说，“好的，我已经止住了血，现在回来重新分析，理解哪里出了问题。”所以，一旦你体验过那种能力，并意识到它的价值——不仅仅是推出东西，而是将那个单独的功能回滚——你就会想在所有事情上都使用它。

<details>
<summary>Original English</summary>
**Robert**: Yeah, I guess just just start with something, right? for start with adding one feature toggle. It may be scary at first to kind of go, "Ah, it's in production. If I, you know, toggle this, I'm going to break something production." You know, it's nice and comfortable to know that you're kind of well to the left of of the running systems and if you ship code, everything will be caught by the test. But, you know, if I toggle it, what will happen? It's kind of like a drug, right? Once you start doing it, you don't want to stop. And that's that's why we've got this this hygiene problem for things like Vij toggles, right? It's really easy to add them and actually end up with the opposite problem of how do you how do you kind of control yourself? How do you stop? So, I'd say just just kind of start doing it. Add one and and keep an eye on kind of as you roll it out and you look at the results from it. And the reality is, you know, I've shipped features bind feature toggles where I've shipped a bug, right? And it's one thing to ship something and turn on a feature and go, "Okay, cool. Customers have it." It's a very different thing when you do the opposite. If you ship something and there's a problem and you can reach immediately for the toggle and switch it back off. you know, the amount of times you kind of in the past you had this kind of panic of, oh no, I've shipped something. It's I don't know what's going wrong. And particularly when you're in that state, you know, maybe you've got called up at 2 am because you've got an on call and you know, you don't know what the next step is to do and you kind of got a panic mind and should I, you know, build a new thing or do I somehow force a redeployment? So having the capability of being able to sort of flick that switch just allows you then calm right down and go, okay, I've stemmed the bleeding now come back and reanalyze it and understand what's wrong. So having that capability once you sort of experience that and realize the value that not just rolling things out but of I guess rolling that individual feature back off. Yeah. You'll you'll want to use it for everything.
</details>

**主持人**: 你会推荐哪一两本书？为什么？

<details>
<summary>Original English</summary>
**Host**: What's one or two books you would recommend and why?
</details>

**罗伯特**: 我会推荐两本技术类的，以及一本更有趣的。《**The Phoenix Project**》对我来说仍然是一本好书。这是其中一本。

<details>
<summary>Original English</summary>
**Robert**: I'll give two kind of I guess technical ones and and more of a fun Phoenix project is still for me a good one. This is one
</details>

**主持人**: 作者是 **Gene Kim**。是的。

<details>
<summary>Original English</summary>
**Host**: by Jean Kim. Yeah.
</details>

**罗伯特**: 是的。嗯，我记得我们在 Skype 时都读过这本书。这是 Abdullah 发给每个人的。

<details>
<summary>Original English</summary>
**Robert**: Yeah. And um I I can see uh you know you kind of remember that we got that in in in Skype. This was one that Abdella kind of gave to everyone.
</details>

**主持人**: 是的，我们的经理给了每个人。

<details>
<summary>Original English</summary>
**Host**: Yeah. Our our manager gave it to everyone.
</details>

**罗伯特**: 是的。嗯，你知道，书中的部分内容可能有点过时，一些实践也略有变化，但其核心思想——作为一名工程师，参与到你所发布内容的整个运维方面，以及这给你和公司带来的价值——是惊人的。所以我认为这本书是核心基础之一，为今天我们谈论的所有内容设定了背景。另一本，嗯，从组织和沟通方面来说，**Kim Scott** 的《**Radical Candor**》能让你更有效、更富有同情心地与你的同事和周围的人沟通。你知道，这很常见。我是一名工程师，所以我知道有时你回顾自己说过的话，会觉得，“好吧，也许我有点太直率了。”而《Radical Candor》教会我们思考，你希望那些沟通既能表达你的关心和同理心，又能直接了当，以及这样做的好处，以及它的反面，就像我说的，你可能非常直率。你对此很诚实，但你缺少了同理心。嗯，所以我觉得这本书非常有用和有趣，不仅仅作为一名工程师，而是作为一个与他人共事的人。从更有趣的方面来说，基本上是 **Greg Egan** 的任何作品。他是一位澳大利亚科幻作家。他写了一些非常疯狂、烧脑的硬科幻。所以如果你真的很喜欢，我建议读一下《**Diaspora**》或《**Schild's Ladder**》。它们是那种需要读第二遍才能读完的书。他也是一位数学家。所以，他有大量的背景和数学知识来解释他故事的某个特定部分为什么会这样。他写了一个完整的故事，前提是“如果光速不是绝对的会怎样”，然后它展开，这就是能量会发生什么，因此分子如何工作等等。作为一个技术宅，那种科学的东西真的很吸引我。同样，当科幻小说中涉及一些科学时，我发现它更有趣。

<details>
<summary>Original English</summary>
**Robert**: Yeah. And um you know it's it's you know parts of it are maybe a little bit outdated and you know some of the practices have changed a little bit but at its core this idea of as an engineer being involved in that whole um sort of operation side of your what you're shipping and and the value that gives to not just the company but to you is amazing. So I think that book has kind of a core when it's one of those core foundational ones that sets the sets the the the context for everything we talked about today. The other one um from a more um I guess organizational and communication side of things um radical cander by Kim Scott allows you to communicate more efficiently and with more compassion with um your peers and other people around you. It's, you know, really common. You know, I'm an engineer, so I I know sometimes it's really, you kind of look back on what you said and you feel like, okay, maybe I'm I can be a little bit blunt. Whereas radical candid teaches us to think about, you know, you want to have those communications that are both sharing that you're caring and empathetic, but also direct and, you know, the benefits of that and kind of the the inverse of that where, you know, you perhaps, like I said, you're very blunt. You're sort of being honest about it, but you're missing that that empathy. Um, so I found that book really useful and interesting as I guess not even just as as an engineer, but as a as a person working with other people. From the the more fun side, basically anything by Greg Egan. He's an Australian sci-fi author. He writes some pretty crazy mindbending hard um hard sci-fi. So if you're really into that, I'd say read um like Diaspora or um Charles's Letter. They're the sort of books that actually took a second read to get through. and he's he's a mathematician as well. So, you know, he's got a whole bunch of background and mathematics on why a certain certain part of his story goes the way it is. He wrote an entire story on the premise of um what if the speed of light wasn't absolute or something like this one premise and it kind of breaks out into and then this is what happens to to energy and therefore molecules work like this and D and um as a you know I'm a I'm a tech nerd um that sort of science stuff you know really appeals. Same same when when sci-fi there's some science involved that's actually way I find it way more fun
</details>

**主持人**: Rob，非常感谢你。

<details>
<summary>Original English</summary>
**Host**: Rob thanks very much
</details>

**罗伯特**: 谢谢你，戈。很棒。

<details>
<summary>Original English</summary>
**Robert**: thank you Got great
</details>

**主持人**: 多么有趣的对话。我希望你喜欢有像 Rob 这样的人，他十年来一直在构建和思考大规模 CI/CD。听他讲述在 Skype 时，我们的团队基本上在行业大多数人赶上之前很多年就实践了持续交付，以及我们如何通过每周悄悄地向新西兰发布新版本来做到这一点，将其作为我们的金丝雀国家，这真是一次有趣的回忆之旅。这提醒我们，许多现代软件实践早已被那些只想比变更咨询委员会允许的速度更快地发布软件的开发者们在实践中运行了。所以，我记下的另一件事是 Rob 关于回滚的看法。很多工程团队把回滚当作安全网来谈论。但一旦你加入了数据库结构变更，安全网在哪里？Rob 的建议是向前滚动，而不是向后，并使用功能开关作为打开或关闭功能的方式。这也提醒我们，投资功能标志通常非常有帮助。但如果你有功能标志，请确保在推出后清理它们，否则它们会变成一团糟。最后，我学到新东西的部分是关于 GitOps 的。我一直以为 GitOps 是关于 Git 的，但正如 Rob 指出的，GitOps 的四个实际支柱中没有一个要求使用 Git。这四个支柱是：第一，声明式；第二，版本化和不可变；第三，拉取而非推送；第四，持续协调。GitOps 这个名称导致整个行业有点教条主义，认为要把所有东西都放进 Git 仓库，甚至包括绝对不应该放在那里的秘密。Rob 的观点是，大多数团队只想发布软件。如果 GitOps 有助于这部分，那很好。但如果一个更实用的过程效果更好，那就用它。请查看下面的节目笔记，了解相关的《The Pragmatic Engineer》关于后端技术和其他相关主题的深度探讨。如果你喜欢这个播客，请在您最喜欢的播客平台和 YouTube 上订阅。如果你还能给节目留下评分，特别感谢你。谢谢，下次再见。

<details>
<summary>Original English</summary>
**Host**: what an interesting conversation I hope you enjoyed having someone like Rob who has been building and thinking about CI/CD at scale for a decade it was such a fun blast from the past story as he talked about how at Skype our team basically did continuous delivery [music] years before most of the industry caught up and how we did it by quietly shipping new bills to New Zealand every week using this as our canary country [music] it's a reminder that a lot modern software practices were already being run in the wild by devs who just wanted to ship software faster than our change advisory board would allow us to do [music] so. One other thing I took a note is Rob's take on roll backs. Lots of engineering teams talk about rollbacks as [music] if they're safety net. But the moment you have a database schema change in the mix, what's safety net? Rob's advice is to [music] roll forward, not back, and use feature toggles as a way to turn features off or on. This is also a reminder that investing feature flags is usually really helpful. But if you have feature flags, be sure to clean up after them after you've rolled them out, otherwise they become a big mess. Finally, a part where I learned something new was on GitOps. I've always assumed that GitOps was about well, Git, but as Rob pointed out, none of the four actual pillars of GitOps require Git at all. The four pillars are number one declarative, [music] number two version and immutable, number three pulled not pushed, number four continuously [music] reconciled. The name githops has caused the whole industry to get a bit dogmatic about putting everything into git repo, even things like secrets which absolutely should not be there. Rob's take is that most teams just want [music] to ship software. If githops helps with that part, great. But if a more practical process works better, just use that. Do check out the show notes below for related the pragmatic engineer deep dives on backend technologies and other related topics. If you've enjoyed this podcast, please do subscribe on your favorite podcast platform and on YouTube. A special thank you if [music] you also leave a rating on the show. Thanks and see you in the next
</details>