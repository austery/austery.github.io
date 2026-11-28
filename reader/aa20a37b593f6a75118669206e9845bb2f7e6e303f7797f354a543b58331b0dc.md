---
layout: post.njk
source: https://www.youtube.com/watch?v=SVOrURyOu_U
speaker: The Pragmatic Engineer
date: '2026-04-25'
tags:
  - distributed-systems
  - data-intensive-applications
  - formal-verification
  - local-first-software
  - cloud-native
title: 对话 Martin Kleppmann：重新审视数据密集型应用系统与 AI 时代的工程挑战
summary: 本访谈深入探讨了分布式系统权威专家 Martin Kleppmann 的职业生涯。从早期创业到在 LinkedIn 参与 Kafka 的开发，再到撰写享誉全球的《数据密集型应用系统设计》。他分享了该书第二版针对云原生环境的更新，并讨论了形式化验证在 AI 代码生成背景下的重要性，以及他在学术界推动的 local-first 软件和加密供应链验证等前沿研究。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Martin Kleppmann
companies_orgs:
  - LinkedIn
products_models:
  - Apache Kafka
  - Designing Data-Intensive Applications
media_books: []
status: evergreen
---
### 设计数据密集型应用
**旁白**: 我应该考虑多区域、多地域甚至多云的设置吗？你愿意承担多大的可用性风险，与之对应的是计算开销，以及实际设计和操作系统的人力开销？MapReduce 已经死了，没人再用它了。但我们增加覆盖范围的其他领域是支持人工智能的系统，比如向量索引。作为一名软件工程师，你是否不再有动力去理解底层？如果你依赖更高层次的抽象，你就不再思考底层的细节了。如果你在构建更高层次的业务逻辑，实际上我认为这完全没问题。大语言模型（LLM）增加了对这些形式化证明的需求，因为我们正在用 VIP 编写大量的东西。我认为形式化验证在未来可能变得更重要的原因之一是，《设计数据密集型应用》这本书已经成为任何构建大型后端系统的人的首选读物。在这本书出版9年后，第二版终于问世了。**Martin Kleppmann** 是这本划时代著作的作者。我与他进行了一次深入的交流，今天我们讨论了在 **LinkedIn** 从事 **Kafka** 相关工作的经历如何直接塑造了本书第一版的思想，第二版有哪些新内容，以及为什么像 **MapReduce** 这样的东西会从这个更新版本中被移除。我们还谈到了形式化方法、本地优先软件、去中心化访问等等。如果你关心大型系统是如何工作的，它们的发展方向，以及那些不变的基本原理，那么这一集就是为你准备的。本集由 **Statsig** 呈现，这是一个集功能开关、分析、实验等功能于一体的统一平台。

本集由 **Sonar** 为您带来。作为 **SonarQube** 的创造者，Sonar 深知代码质量不仅仅是避免语法错误，更是通过保护系统的结构完整性来实现长期可维护性。当 AI 代理大规模生成代码时，它们常常会忽略你系统的结构完整性。这会造成代码纠缠、重复代码以及其他可维护性问题。这些问题会将一个模块化的设计变成一团乱麻，使其越来越难以扩展。但这里有一个非常有用的东西：**SonarQube 的架构管理功能**。它将架构治理从静态的维基文档中解放出来，融入到你的自动化工作流中。它允许你可视化当前架构，定义架构边界，并实时管理架构问题。无论键盘前的是人类还是 AI 代理，Sonar 都能充当结构性衰退的“断路器”。它确保每一次提交都尊重系统的蓝图，保护你最复杂应用的长期健康。请访问 **sonarsource.com/pragmatic** 了解更多信息。

**Gergely Orosz**: 那么 Martin，欢迎来到这个播客。

<details>
<summary>Original English</summary>
**Narrator**: Should I consider a multizone, multi-region or even a multi-cloud setup? How much availability risk are you willing to take on versus the computational overheads, but also the human overheads actually designing and operating the system? MapReduce is dead. Nobody uses it anymore. But other areas where we've increased the coverage are systems in support of AI like vector indexes. Is there any risk as a software engineer that you're no longer incentivized to understand the underlying layer? If you rely on a higher level abstraction, you're no longer thinking about the lower level details. If you're building higher level business logic, actually, I think it's just fine. LLMs increase the need for these formal proofs because we're vibe coding a bunch of stuff. The reason I think that formal verification could become more important in the future. One is that **Designing Data Intensive Applications** has been the go-to book for anyone building large backend systems. 9 years after publishing this book, the second edition is here. **Martin Kleppmann** is the author of this generational book. I sat down with him and today we cover how working on **Kafka** at **LinkedIn** directly shaped ideas that became the first edition of the book, what's new in the second edition, and why things like **MapReduce** got removed from this updated version. Formal methods, local first software, decentralized access, and many more. If you care about how large systems work, where they're heading, and what the fundamentals are that don't change, this episode is for you. This episode is presented by **Statsig**, the unified platform for flags, analytics, experiments, and more. This episode is brought to you by **Sonar**. Sonar, the makers of **SonarQube**, understands that code quality is about more than just avoiding syntax errors. It's about long-term maintainability by protecting the structural integrity of the system. As agents generate code at massive scale, they often ignore your system's structural integrity. This creates tangles, duplicated code, and other maintainability issues. These issues turn a modular design into a big ball of mud, making it increasingly difficult to extend. But here's something that's really helpful: **SonarQube's architecture management**. It moves architectural governance out of static wikis and into your automated workflow. It allows you to visualize your current architecture, define architectural boundaries, and manage architectural issues in real time. Whether it's a human or an AI agent at the keyboard, Sonar acts as a circuit breaker for structural decay. It ensures every commit respects the system's blueprint protecting the long-term health of your most complex applications. Head to **sonarsource.com/pragmatic** to find out more. So Martin, welcome to the podcast.
</details>

**Martin Kleppmann**: 嗨，Gergely，很高兴来到这里。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Hi Ger, it's great to be here.
</details>

**Gergely Orosz**: 你能来真是太棒了。我想对许多软件工程师来说，包括我自己，你都无需介绍。你是我书架上这本标志性著作的作者，这本书大概在我书架上待了十年了，它问世没多久我就买了。在我们深入探讨这本书之前，我想先聊聊，你是如何进入科技领域的？

<details>
<summary>Original English</summary>
**Gergely Orosz**: It's amazing to to have you here. I don't think you need introduction to many software engineers, including myself. You're the author of this iconic book that I've had on my bookshelf for probably about 10 years, not not much longer after it came out. Before we get into this book, which we're going to talk about, how did you get into the technology field?
</details>

### 从学术到创业
**Martin Kleppmann**: 好的。嗯，我和许多人一样，读了计算机科学的本科。毕业后，我不太确定自己的人生该做什么，但我想，嗯，创业似乎是件有趣的事。于是，我创办了一家公司，当时完全不知道自己具体要做什么。最初一段时间，我四处寻找可能有趣的方向。第一个创业公司并不算太成功，但通过那次经历，我认识了一些人，他们后来成为了我第二次创业的联合创始人，那次创业就顺利多了。我们把那家公司卖给了 LinkedIn。之后，我开始对教授分布式系统概念产生兴趣，于是就开始写书。在写书期间，我也从工业界转回了学术界。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. Well, I did a undergraduate computer science like like many others. And then after that, I wasn't quite sure what to do with my life, but I thought, well, is like starting a startup seems like an interesting thing to try. So, I started a startup having no clue what I was going to actually do and then spent the first while searching around for things that might be interesting. The first startup didn't work out that well but through that I met some others who then became my co-founders for the second startup which worked better and uh we sold that one to LinkedIn and then after that I started being interested in like teaching these distributed systems concepts so that's when I got into writing the book and then during the writing of the book I also switched over from industry back to academia.
</details>

**Gergely Orosz**: 我们可以聊聊你的第一和第二个创业公司吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: can we talk a little bit about your first and second startup?
</details>

**Martin Kleppmann**: 当然，第一个是 Go Test It。那大约是在 2008 年左右。当时，人们在让 JavaScript 跨浏览器工作方面遇到了很大的困难。Internet Explorer 当时还很流行，Chrome 才刚刚问世。所有的浏览器都互不兼容。所以 **Go Test It** 是一个为网站提供跨浏览器自动化测试的服务，它基于一个至今仍然存在的开源项目 **Selenium**。它的理念是，你编写测试脚本来自动化用户在网站上的各种点击交互，然后检查行为是否正确。它基于 Selenium，但我们将其作为一个托管服务提供，这样人们就不必自己运行各种带有不同操作系统的虚拟机了。技术上是可行的，但我发现要获得用户采纳真的很难。很多做网站的人理论上都说，“哦，是的，这很棒，我们需要进行跨浏览器测试”，但在实践中，要让他们将其整合到工作流中，并养成使用和投入编写测试脚本的习惯，真的非常困难。所以，那个项目最终没有太大进展。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: yeah go test it this was like 2008 or something like that. It was the age where people were having really difficulties getting their JavaScript working cross browser. Internet Explorer was still pretty big at the time. Chrome had just come out. Uh all the browsers were incompatible with each other and so Go Test. It was a cross browser automated testing service for websites was based on **Selenium**, an open source project that still exists. And the idea is you would write like test scripts that automate the a user clicking through the various uh interactions with a website and then just check that the right behavior happens. And so yeah, it was based on selenium but just as it provided as a hosted service so people wouldn't have to run various VMs with various operating systems themselves. It worked technically but um I found it really hard to actually get adoption for it. A lot of uh people building websites like in theory said oh yeah this is great. we we need to test cross browser and in practice actually it was really difficult to get them to integrate it into their workflow and just get in the habit of using it and investing in writing the test scripts. So, so that ended up not really going anywhere.
</details>

**Gergely Orosz**: 所以，当时是没有商业模式，或者说无法产生有意义的收入吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: So, so like there wasn't like a business to be done or or like revenue to be generated in meaningful sense.
</details>

**Martin Kleppmann**: 嗯。嗯，至少还有一两家同一时代的公司确实成功地做成了生意。**Source Labs** 就是其中之一，他们成功了。但即使对他们来说，这也是一个相当缓慢发展的业务。我认为这门生意并不好做。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. Well, there's at least one other maybe two other companies from that same era that did manage to make a business. **Source Labs** is one that that managed to actually succeed. Um, but it even for them it was a pretty slow running business. I think it was not an easy business to be in.
</details>

**Gergely Orosz**: 你的初创公司是在英国创办的吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: And for the startup, were you in in the UK building it?
</details>

**Martin Kleppmann**: 当时我正在英国。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I was in the UK at the time.
</details>

**Gergely Orosz**: 公司是自筹资金的吗？你们有没有筹集过某种资金？团队有多大？我们可以想象一下当时的情景吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Was it was it bootstrapped? Did you raise some some kind of funding? How big was the team? How can we imagine this?
</details>

**Martin Kleppmann**: 大部分是自筹资金。我做了很多咨询工作来资助招聘一些人，然后以很低的薪酬雇佣了一些朋友来帮助构建产品。所以一切都做得很便宜。我有一笔非常少的天使投资，但主要是自筹资金。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: It was mostly bootstrapped. So I did a bunch of consulting in order to fund hiring some people and then hired some like friends uh on the cheap to help contribute to actually building the product. And so it was done all all very cheaply. I had a very small amount of uh of angel money in there but mostly bootstrapped.
</details>

**Gergely Orosz**: 嗯。那你决定不再继续这个项目后，下一个创业公司是怎么来的呢？是 **Rapportive**，对吧？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Mhm. And then when you decided to to not uh go forward with this, how did the next startup come? Uh reportive, right?
</details>

### Rapportive 与 Y Combinator
**Martin Kleppmann**: 是的，第二个是 **Rapportive**。那个项目顺利多了。基本上就是把社交媒体整合到 Gmail 里。想法是，如果你收到一个不认识的人发来的邮件，我们有一个小小的浏览器扩展，它会修改 Gmail 的网页界面，在邮件旁边显示一个社交资料摘要，包括从 LinkedIn 拉取的头像和职位，从 Twitter 拉取的最近推文，可能还有最近的 Facebook 帖子之类的东西。就是我们能找到的关于那个人的任何信息，然后把它作为一个社交摘要放在邮件旁边。我们大概是在 2010 年开始的，然后很快就变得相当受欢迎。因此，在此基础上，我们从 **Y Combinator** 筹集到了一些资金，当时 YC 还相当年轻。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, the second one was **Rapportive**. That went a lot better. So, uh, that was putting social media inside Gmail basically. So, the idea was that if you get an email from someone you don't know, we had a little browser extension which manipulated the Gmail web interface so that on the side next to the email, we'd show you a summary social profile with like a profile picture and like a job title pulled from LinkedIn and recent tweets pulled from Twitter and maybe recent Facebook post or things like that. just whatever we could find about that person uh and put that as a as a social summary next to the email. We started in 2010 or something like that. It was then pretty quickly became quite popular. Um and so on the back of that we were then able to raise some money from **Y Combinator** which was still fairly young at the time.
</details>

**Gergely Orosz**: 那时候非常年轻。你们一定是最早的几批之一。

<details>
<summary>Original English</summary>
**Gergely Orosz**: That was very young. That you must have been one of the very early batches.
</details>

**Martin Kleppmann**: 是的，我记不清他们具体是什么时候开始的了，但肯定是在早期。我记得 Y Combinator 当时已经建立了相当好的声誉，但规模还很小。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, I can't remember exactly when they started but it was um it was certainly in the early years. I think Y Combinator had already built up a quite a good reputation at the time, but it was still fairly small.
</details>

**Gergely Orosz**: 作为 Y Combinator 的一部分，你们是不是得从英国飞到旧金山参加那个为期十周（如果我没记错的话）的项目？

<details>
<summary>Original English</summary>
**Gergely Orosz**: And then as part of Y Combinator, did you have to fly you from from the UK to San Francisco to attend that 10e program if I remember?
</details>

**Martin Kleppmann**: 没错。是的。我们最初是为了参加 Y Combinator 那三个月左右的项目而来的，但后来我们成功地为自己申请到了美国工作签证，并在旧金山永久定居下来。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Exactly. Yes. So we um initially came for for the 3 months or whatever it was of the Y combinator but then we were able to get US work visas for ourselves and uh set up permanently uh in in San Francisco.
</details>

**Gergely Orosz**: 从英国（你在那里读大学、第一次创业以及第二次创业的初期）到旧金山的转变是怎样的？

<details>
<summary>Original English</summary>
**Gergely Orosz**: How was that shift from from the UK where you spent going to university your first startup the first part of this to coming to San Francisco?
</details>

**Martin Kleppmann**: 非常激动人心，因为感觉就像是来到了所有事情发生的核心地带。我们刚开始时完全不认识任何人，整个湾区大概只认识一两个人。但我们联系了他们，他们又把我们介绍给更多的人，如此循环。所以我们很快就建立起了一个关系网。我非常感激这一点，湾区对我们这样的外来者非常开放，我们基本上就是带着一个想法和一个早期创业公司就来了，并且成功筹集到了一些资金，在湾区站稳了脚跟。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: It was very exciting because uh you know it felt like you know going going to the the center of where it was all happening really and we at the started out not knowing anybody at all. we knew like one or two people in the entire Bay Area, but we like contacted them and they introduced us to more people and they introduced us to more people. And so we were able to pretty quickly actually build up a a network and that that's something that I I really appreciated that it was actually so open to outsiders like us who could just basically turn up with an idea and an early stage startup and we managed to raise some money and managed to like actually become somewhat established in the in the Bay Area.
</details>

**Gergely Orosz**: 你能告诉我公司是如何发展的吗？LinkedIn 是在什么时候提出收购要约的？我们可以想象一下当时的情况吗，你当时是公司的创始人。

<details>
<summary>Original English</summary>
**Gergely Orosz**: And can you tell me how the how the company grew and and at what point did the LinkedIn acquisition offer come and and how can we imagine even you were a founder of this company.
</details>

**Martin Kleppmann**: 我们大约在 2012 年卖掉了公司。当时我们团队只有五个人，所以规模还很小。虽然涉及的金额不大，但我认为对所有参与者来说，这都是一次成功。收购过程本身还算顺利。像这类交易一样，总会有波折和转折，有好几次我们以为一切都要泡汤了。当时我们的资金也快用完了，而且没能成功融到下一轮。所以我们当时的选择就是要不出售，要不关门。我们面临着相当大的压力。我们不能降低自己的工资，因为那样会违反我们的签证条件。是的。所以，考虑到我们在那种情况下缺乏筹码，我们处境有些被动。但实际上，我对最终的结果非常满意。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: It was about in 2012 that we sold it. Um and we were five people at the time. So it's all still pretty small. Um not vast amounts of money involved but it it was a success I would say uh for everybody involved. The acquisition process it itself was fine. is like as always with these kinds of transactions, there was like twists and turns and moments where we thought it would all fall apart and then we were almost running out of money and uh hadn't really succeeded in raising another round. So, we kind of had to sell or shut down. So, we were under quite a bit of pressure. We couldn't reduce our own salaries because to do so would have violated the conditions of our visas. Yes. Um so, we were in a slightly stuck situation given our lack of leverage in that situation. And actually I'm pretty happy with how it all turned out.
</details>

**Gergely Orosz**: 是啊，十多年后我们能坦诚地谈论这件事，感觉很好。因为很多时候你看到 LinkedIn 的收购案，你可能会去问创始人，他们会说这是他们的梦想或目标，或者说他们将一起做很多事情。但你很少听到的是，这其中也涉及到了压力。那么，你当时是因为看到情况有些棘手——要么需要进行新一轮融资，要么就得卖给别人——所以才打算出售公司的吗？然后你发现 LinkedIn 是最好的，或者是唯一的，或者是最佳的选择？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Yeah, it's nice that you know like for 10 plus years we can talk about this honestly because often times you see an acquisition by LinkedIn and of course you might ask the founders and they would say like this was our either our dream or our goal or we will do so many things together but some things that you don't often hear is well that there was a pressure involved as well. So, did you go into this wanting to sell the company because you saw that things were getting a little either you needed to raise a new round or you sell to someone and then you found LinkedIn to be the the best of or the only or or or the best option to to go into.
</details>

**Martin Kleppmann**: 我们曾尝试过一些创收的方案，但都没能真正成功。所以我们当时只是在烧钱，而且我们的用户增长还可以，但不足以去融一大笔钱。所以我们有点卡在那里了，出售公司在某种程度上似乎是当时最不坏的选择。而且我对结果很满意，因为你知道，LinkedIn 实际上很棒。他们对我们非常好。他们允许我们作为一个基本独立的团队在公司内部运作。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: We tried a little bit to see like what revenue generating options we had and hadn't really managed to make that work. So, we were just burning money and uh and our user growth was okay but not really enough to go and raise a big round. Um, so we were like a little bit stuck there and selling the company seemed like the least bad option there in a way. And I'm pretty happy with how it turned out because you know LinkedIn was great actually. They they were very good to us. They allowed us to operate as essentially like a independent team within the company.
</details>

**Gergely Orosz**: 所以你的团队还在一起？

<details>
<summary>Original English</summary>
**Gergely Orosz**: So So your team stayed together?
</details>

**Martin Kleppmann**: 我们的团队还在一起。我们继续在我们想做的产品上工作。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Our team stayed together. We continued working on the product that we wanted to make.
</details>

**Gergely Orosz**: 哦，你们还能继续做 Rapportive。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Oh, you you got to keep working on reportive.
</details>

**Martin Kleppmann**: 是的。嗯，实际上，Rapportive 这个 Gmail 浏览器扩展程序后来就处于维持状态了，但我们当时正在开发一个新产品，最终以 **LinkedIn Intro** 的名义发布了。它当时的反响有点奇怪，发布后不久就被关闭了。这背后有个更长的故事，但我仍然非常感谢 LinkedIn，他们给了我们这样做的自由，允许我们推出这个产品。尽管它没有成功，但他们在那整个过程中对我们都非常好。后来那个产品被关闭后，我们的团队也就解散了。但我们在 LinkedIn 内部开发这个产品的那段时间过得很好。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. Well, actually, so report of the Gmail browser extension uh sort of got put on life support, but we were working on a new product at the time, which did eventually get released under the name **LinkedIn Intro**. It kind of got a slightly weird reception at the time and it ended up getting shut down shortly after we released it. this kind of longer background story there, but um I'm still really happy with LinkedIn like how they gave us the freedom to do this and allowed us to launch this product and even though it didn't succeed, you know, they were very good to us throughout that process and then after that got shut down then our team got disbanded. Um but we had a good run within LinkedIn um building this product.
</details>

**Gergely Orosz**: 你当时用的技术栈是什么？你用了什么？

<details>
<summary>Original English</summary>
**Gergely Orosz**: What tech stack did you work at the time which what do you use?
</details>

**Martin Kleppmann**: Rapportive 的技术栈相当普通。它基本上就是一个 Rails 应用，配上一个 Postgres 数据库，还混用了一些 Redis 和类似的东西。所以实际上，你知道，没有什么特别革命性的东西。我们基本上是在 Postgres 之上构建了一个图数据库。所以那里有一些技术上的趣味，但你知道，并没有什么特别出格的。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: The reporter was fairly unexciting. It was a Rails app with a Postgress database basically and some Reddit and some similar things like that mixed in. So actually you know nothing particularly revolutionary. We essentially built a graph database on top of Postgres. So there was a a little bit of technical interest in there but you know nothing particularly outrageous.
</details>

**Gergely Orosz**: 在 LinkedIn Intro 之后，你还在 LinkedIn 工作了一段时间，据我所知，你从事的是数据基础设施方面的工作，对吧？

<details>
<summary>Original English</summary>
**Gergely Orosz**: And then you you spent time after LinkedIn intro you still work inside LinkedIn as I understand you worked on data infrastructure right?
</details>

### 在 LinkedIn 的经历与 Kafka
**Martin Kleppmann**: 是的，数据基础设施。我们团队解散后，我转到了流处理团队。当时 **Kafka** 刚刚在 LinkedIn 开发出来。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes data infrastructure. Um after our team got disbanded, I switched over to the uh stream processing team. So **Kafka** had just been developed at LinkedIn and had just
</details>

**Gergely Orosz**: 对，哦，它当时刚要开源。

<details>
<summary>Original English</summary>
**Gergely Orosz**: right. Oh, it was just being open sourced.
</details>

**Martin Kleppmann**: 是的，我想它刚刚开源，然后我开始参与 **Samza** 的工作，那是一个基于 Kafka 的流处理框架。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, I think it had just been open sourced and then uh I got to work on **Samza** which was a stream processing framework on top of Kafka.
</details>

**Gergely Orosz**: 我一直想问这个问题，现在正好有机会。为什么 LinkedIn 要构建或开发 Kafka？现在它已经成为一项如此基础的技术，我总是很好奇，为什么一家公司会觉得有必要去构建这样一个看起来相当通用，并且似乎每个人都需要的东西。

<details>
<summary>Original English</summary>
**Gergely Orosz**: I always wanted to ask this question so this comes here. Why did LinkedIn build Kafka or or develop Kafka? every time it's now such a fun foundational technology there always I was always curious like why did a company feel the necessity to build this thing that seems pretty generic and it seems everyone would have needed it.
</details>

**Martin Kleppmann**: 是的。我想 **Jay Kreps** 在那个时代写过一篇很好的博客文章，叫做《日志》（The Log），他在其中解释了他开发 Kafka 的动机，以及为什么要做成一个只支持追加的日志，而不是传统的消息队列之类的东西。我认为，当时的动机主要是为了数据整合。因为当时有一大堆数据库和事件生成系统，比如用户的活动事件，它们都在以流的形式生成数据。然后又有一堆下游系统想要消费这些数据，比如想把它导入数据仓库，想把它导入当时的 Hadoop 集群，以便进行机器学习等操作。当时就存在这样一个数据整合问题：如何从物理上将数据从一个系统取出并放入另一个系统。Jay 设计了 Kafka 作为这个整合点，它本质上是各种数据源和下游数据接收器之间的一个通用抽象，几乎是最低通用分母。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. So I think **Jay Kreps** has a pretty good uh blog post from from that era uh called the log where he explains his motivation behind Kafka and you know why why make it an appendon log rather than like a traditional message Q or something like that. I think the motivation was really about data integration because there were a whole bunch of databases and and like event generating systems you know like um activity events from users for example they were all generating data that in a sort of stream shape and then a bunch of downstream systems that wanted to consume this like wanted to get it into the data warehouse and wanted to be able to get it into the Hadoop cluster at the time in order to run like machine learning and things over it and there was just this data integration problem of actually like how do you physically get the data out of one system and into another and uh Jay designed Kafka as this integration point essentially like the almost the kind of lowest common denominator but still a general purpose abstraction uh for integrating v various data sources and to downstream data syncs.
</details>

**Gergely Orosz**: 在 LinkedIn 这样大规模的环境下，从事像 Kafka 这样的项目，你学到了什么？或者说，在这样大规模的系统上工作，有什么让你感到惊讶的？据我所知，这是你第一次亲手在真正的大型系统上工作，对吧？

<details>
<summary>Original English</summary>
**Gergely Orosz**: working at LinkedIn at at you know like Kafka and at LinkedIn scale what did you learn or what surprised you about working at this type of scale as I understand this was for the first time that you hands-on worked at a really large system, right?
</details>

**Martin Kleppmann**: 没错。是的。因为之前我工作过的最大的公司是 Rapportive，只有五个人。我们有一个相当大的数据库，但仍然是单实例数据库，从宏观上看并不算大。然后我突然到了 LinkedIn，哦，我们可以使用他们的大型 Hadoop 集群了。那很有趣，当时需要用 Java 手动编写 MapReduce 任务。所以我在那里学到了非常多的东西。特别是当流处理的思想出现，Jay 倡导使用 Kafka 以及可以用它做的各种事情时。这对我来说简直是一个启示，我突然觉得，啊，这下讲得通了。我开始理解这些不同的数据系统是如何组合在一起的，它们有什么共同点，以及基本原则是什么。所以，那段经历直接为我后来写书提供了素材。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: That's right. Yes. Because like previously the biggest company I had worked in was Reporter with five people. We had a sizable database but it was still like a single instance database and not really that big in the grand scheme of things. And then yet suddenly I was at LinkedIn and oh we got to get get to use their big Hadoop cluster. That was fun like hand coding map produce jobs in Java at the time and so I I learned a huge amount there. Um especially when the stream processing ideas uh came up and Jay was evangelizing the use of Kafka and the things you could do with it. That was kind of a revelation for me really where I suddenly like felt ah this this kind of makes sense like I'm I start to understand how these various data systems fit together what they have in common what the fundamental principles are and so that experience then fed directly into the writing of the book.
</details>

**Gergely Orosz**: 你是在什么时候决定离开 LinkedIn 的？在我看来，你的职业生涯轨迹是这样的：在英国起步，创办一家初创公司，再创办第二家，进入 Y Combinator，搬到旧金山，被 LinkedIn 收购。大多数人会设想的下一步是，在硅谷做更多事情，或者再创办一家公司等等。但你却决定离开 LinkedIn。

<details>
<summary>Original English</summary>
**Gergely Orosz**: At what point did you decide to leave LinkedIn? To me, in in your careers, I'm looking through the career, start out in the UK, do a startup, do a second startup, Y Cominator, move to San Francisco, get acquired by LinkedIn. The arc that most people would draw would be, okay, do something more in Silicon Valley or maybe start a second startup, etc. And and instead you decided to leave LinkedIn.
</details>

### 写作、学术与回归欧洲
**Martin Kleppmann**: 是的。所以，首先我决定搬回英国，并且继续为 LinkedIn 远程工作。好的。这主要是因为我当时的女朋友，也就是现在的妻子，还在英国，异地恋并不好玩。而且我并不觉得湾区很适合我，所以我也没有很鼓励她搬到湾区来。我觉得对我来说，回到欧洲更好。我对这个决定非常满意。我在湾区还有很多好朋友，我喜欢去那里旅行，但老实说，我不想住在那里。然后，我仍然在为 LinkedIn 远程工作，这在一段时间内进展得还不错。当我开始写书时，LinkedIn 甚至给了我 50% 的自由时间来写书，同时我还在履行我的软件工程职责，这真的很棒。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. So, first I decided to move back to the UK actually and I continued working for LinkedIn remotely. Okay. That was m mostly because my girlfriend at the time, now wife, was still in the UK and long-distance relationship is not a lot of fun and I didn't feel that at home in the Bay Area. So, I wasn't really encouraging her to move to the Bay Area either. I thought it was better for me to go back to Europe and I'm very happy with that decision. Like, I still have a lot of great friends in the Bay Area. I love it as a place to visit, but I wouldn't want to live here honestly. Then I was still remotely working for LinkedIn and that worked all right uh for a while. When I then started writing the book, LinkedIn even gave me 50% of my time free to work on my book alongside my software engineering duties, which is really great.
</details>

**Gergely Orosz**: 太棒了。是的，他们真是太好了。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Amazing. Yeah, that is so nice of them.
</details>

**Martin Kleppmann**: 当然。他们没有义务这么做。LinkedIn 并没有直接从中得到任何回报，除了可能有一本他们可以用于内部培训的书。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Absolutely. And there they don't have to do that. And LinkedIn didn't directly get anything out of it in response other than like a book that they could use for internal training purposes.
</details>

**Gergely Orosz**: 嗯，为 LinkedIn 的这种做法点赞。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Well, shout out shout out to LinkedIn for this.
</details>

**Martin Kleppmann**: 是的，一点没错。不过后来我发现，实际上，一边写书一边做软件工程工作，还要随叫随到，我根本做不到。上下文切换太频繁了，而且很容易被值班的紧急事情占据主导，然后就没有那种你需要创作新东西时所必需的自由了。所以过了一段时间，我决定，好吧，也许我最好全职专注于写书。于是我离开了 LinkedIn，休了一个无薪的学术休假，也就是失业，全心全意地投入到写书上。直到那之后，我才真正考虑进入学术界。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, absolutely. Though then I did find then that actually trying to write a book in parallel with doing a software engineering job and being on call etc. I just wasn't able to do it. It's just too much context switching and it's very easy for the urgent things from the on call to dominate and and then not to have the you know the freedom of that you need in order to to write something new. Um and so then after a while I decided okay like it's it's probably better if I focus full-time on the book. So I then left LinkedIn and just took a sbatical unpaid sobatical i.e. unemployment um to just focus full-time on the book for a while and then it's only after that that I actually even considered getting into academia.
</details>

**Gergely Orosz**: 写书的想法是怎么来的？你在哪个节点决定要写书？在你心里，你决定写什么？当时你脑海中已经有了这本书的蓝图和结构，还是只有一个初步的想法？

<details>
<summary>Original English</summary>
**Gergely Orosz**: So how did the idea of the book come? What was a point where you decided you would write and in your mind what were you deciding to write? What was was it already you know this this book with with with this layout or you had an early idea back then?
</details>

### 构思《设计数据密集型应用》
**Martin Kleppmann**: 我当时有个想法，当然最终的产品看起来有些不同，但我认为整体目标是一致的。我知道我想写一本宽泛的、概念性的综述。所以不是关于如何使用某一个特定的系统或工具，而是比较许多不同类型工具之间的权衡。而且我知道我希望它是面向实践者的，不是一本理论教科书，而是人们可以用来构建真实系统的东西。这基本上就是我着手时的目标。这正是我刚起步时，比如在 Rapportive 工作时，希望拥有的那本书。因为我们当时都像在黑暗中摸索，我们的数据库有性能问题，我们基本上不知道该怎么办，因为我们完全缺乏真正理解发生了什么以及如何诊断问题的基础知识。所以我觉得，如果我对这些数据系统内部如何工作有多一点背景知识，我就能对如何调试这类性能问题有直觉。后来，在我对数据系统工作原理了解更多之后，我想，好吧，是时候把这些写下来了，这样其他人就不必走弯路，而是可以希望能更好地了解这些系统的工作原理，从而更好地管理他们自己的数据系统。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I had an idea that it of course the final product ended up looking somewhat different but the the overall goal I think stayed the same. So what I knew I wanted to write something that was a broad conceptual overview. So not about how you use any one specific system or tool but comparing the trade-offs between many different types of tools. And I knew that I wanted to be practitioner focused like not a theoretical textbook but something that people could use to build real systems. That was basically like the the goal with which I appreciate approached it. And this was exactly the book that I wish I had had when I was starting out and uh working at Reportive for example because we were all like searching around in the dark where we're having performance problems with our database and we had no idea what to do basically because we were totally lacking the foundations to actually understand what was going on and how to diagnose the issues. And so I felt that well if I had had a bit more background on how these data systems actually work internally then I could have had an intuition about how to debug these kinds of performance issues. And then after a while after I'd learned more about how data systems work I thought well okay it's it's time to write this down so that others don't have to learn it the hard way um but can hopefully just get a better idea of how these systems work and thus be better at managing their their own data systems.
</details>

**Gergely Orosz**: 首先，你是如何学习例如数据库工作原理的？因为根据你在 Rapportive 的经历，你构建过系统，在较小规模上遇到过一些性能问题。然后在 LinkedIn，你看到了“香肠”是如何制作的，但我也认识很多走过这条路的软件工程师，他们仍然不真正了解基础系统的工作原理。他们只知道公司内部有一个平台团队，他们构建了它。我可以阅读 RFC，但这需要大量工作，或者规划文档，我可以查看源代码。在我看来，即使在那个时候，你也深入研究并试图挖掘。你用了哪些资源？你是如何发现那些后来被你写进书里的基础知识的？

<details>
<summary>Original English</summary>
**Gergely Orosz**: to start with how did you learn about for example how databases work because again from from your story at report if you you build systems you've had some performance issues at a smaller scale to to be fair compared to LinkedIn then you worked at LinkedIn and you saw a little bit of how the sausage was made but I know a lot of software engineers who have been in this path and they still don't really know how the fundamental systems work they just know okay we have a platform team inside our company and they build it I could read the RFC's but it's a lot of work or the planning docs I could look look at the source code it feels to me that even at that point you just went down and and tried to dig in. What resources did you use? How how did you find out those those basics which you later put into the book?
</details>

**Martin Kleppmann**: 很多时候，这只是出于好奇心，并与人交谈，问他们很多问题。在 LinkedIn，有一群资深的数据系统工程师，他们对自己的东西了如指掌，但可能不一定把这些知识写下来。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: A lot of of it was just kind of being curious and talking to people actually and just asking them lots of questions. And at LinkedIn there were like a bunch of senior data systems engineers who understood their stuff very well but hadn't maybe necessarily written it down.
</details>

**Gergely Orosz**: 嗯。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Mh.
</details>

**Martin Kleppmann**: 所以我就和他们中的一些人交谈，向他们请教，通过这种方式，我开始在自己的脑海中构建起这些东西是如何工作的图像。一旦我从这些对话中掌握了基础知识，我就能去阅读研究论文了。那些论文会更深入地详细解释事物为何以及如何被设计成那样。但你知道，阅读那些东西很耗时。所以后来我尝试做的就是，提炼出真正核心的思想。我也读了大量的博客文章。所以，你在书中每一章末尾看到那么多参考文献的原因是，那实际上就是我自己用来理解当时情况的资料。然后我想，好吧，如果我觉得这些东西有用，我也会在书中引用它们，作为任何想超越本书基础知识的读者进一步阅读的好资源。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: And so I just talked to a bunch of them and and quizzed them and that way started building a an image in my own mind of how this stuff works. And then once I sort of got the basics from these conversations, then I was able to go and read research papers for example. They go into much more detail of exactly how and why things are designed in such a way. Um but you know it is timeconuming to read those things. Um so so then what I tried to do was like pull out what what are really the essential ideas. I just read a ton of blog posts as well. Um and so the reason why you see so many references at the end of each chapter in the book is well that is actually the material that I myself used in order to uh understand what was going on. And then I thought well okay well if I found these things useful then I'll also cite them in the book as a way for anyone any reader who wants to go beyond the basics covered in the book here are some some good sources to further reading.
</details>

**Gergely Orosz**: 这本书（至少是第一版）的结构是：基础数据系统、分布式数据和派生数据。如果我理解得对，这是三个大的部分。你是在开始写书时就已经有了这个结构，还是在写作过程中形成的？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Yeah, the the structure of the book, this first book at least, it's foundational data systems, distributed data, and derived data. If I understood, these are three big parts. Did you already have a a structure in mind when you started writing the book or did it shape as you went?
</details>

**Martin Kleppmann**: 这个三部分结构在本书的设计中并不那么关键。那更像是我事后觉得，哦，好像我们可以把这些章节大致归入这样的结构。但章节的主题或多或少和我最初设想的一样。我知道我想谈谈事务到底是什么，我想谈谈复制，我想谈谈分片或分区，我想谈谈一致性和共识。这些高层次的主题，我想在我最初给出版商的书稿提案中就已经很清楚了。每一章的细节，则是我写到那一章时才经常想清楚的。我是一章一章写的，每一章的开始都会做大量的背景研究，以便自己能跟上这个主题的最新进展。通常只有到那时，比如对于复制这一章，我才决定，好吧，看来做这件事的三种主要方式是单主节点、多主节点或无主节点。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: This three-part structure is not that critical in the design of the of the design of the book really. That's sort of more after the fact I thought, oh, well, it seems like we can group the chapters into roughly this sort of structure. But the topics of the chapters were more or less what I had envisaged. So I um I knew that I wanted to talk about like what a transaction actually is. I knew that I want to talk about replication. Knew that I wanted to talk about sharding or partitioning. Knew that I want to talk about like consistency and consensus. Those the sort of highlevel topics I think uh were clear from like my initial book proposal to the publisher. the details within each chapter. That is something that I often figured out once I got to that chapter. So, I wrote one chapter at a time and started each chapter work with just a lot of background research to actually get up to speed on the topic myself. And it's often only then that say for then replication I decided okay well it seems like the three major ways of doing this are single leader, multi-leader or leaderless. Okay.
</details>

**Gergely Orosz**: 嗯。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Mhm.
</details>

**Martin Kleppmann**: 我基本上是在开始写每一章的时候决定这个结构的，然后试着把我想要表达的各个观点融入到这个叙事结构中。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I would decide on that structure at essentially when I started writing each chapter and then try to fit the various points I wanted to make into into this uh narrative structure.
</details>

**Gergely Orosz**: 作为一个也写过书的作者，我注意到估算一本书的写作时间和估算一个软件项目之间有一些相似之处，那就是你带着一个估算开始，如果你以前没做过，你的估算往往会错得离谱。你在写作过程中的经历是怎样的？另外，你还有出版商，出版商有点像项目经理。他们喜欢有时间表，喜欢让你按计划进行，喜欢问什么时候能完成。你是如何处理这部分的？最后，你开始时估计需要多长时间，实际又花了多长时间？

<details>
<summary>Original English</summary>
**Gergely Orosz**: As a as a fellow author who also wrote a book, one thing I've noticed there's a bit of parallels between estimating a book and estimating a software project in that you come in with a estimate and if you've never done it before you tend to be wildly off. How was this in your journey? And and addition, you also had a publisher and publishers are are a little bit like project managers. They, you know, they they like to have a a schedule. They like to try to keep you on track. They they like to ask what when is it done? How did you manage that part as well? And and in the end, how long did you estimate it would take when you started and how long did it actually take?
</details>

### 关于写作过程
**Martin Kleppmann**: 和往常一样，花费的时间比预期的要长得多。我认为这在软件项目和写作上都是一样的。我想我花了大约四年时间写完第一版，那不是四年全职工作，可能相当于两年半的全职工作量，但写作过程跨越了大约四年。所以这绝对花了很长时间。出版商的截止日期我错过了很多，我想我大概错过了两年半左右。但幸运的是，**O'Reilly** 对第一版相当宽容，他们很乐意让我慢慢来，把书做好。到了第二版，O'Reilly 在遵守截止日期方面就变得更积极、更催促了。我想那时候这本书已经很有名了，大家都在热切地等待第二版。所以我能理解他们想要加快进度的愿望，但同时，我真的很感激第一版时我能按照自己的节奏工作的自由。而在第二版时，这种自由就少了一些。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: As always, it takes vastly longer than expected. It's the same for software and projects as it is for writing, I think. So I think it took me about four years to write the first edition and that was not four years of full-time maybe like two and a half years of full-time equivalent or something like that but uh written over the course of about four years. So it definitely took a long time. The uh publisher deadline I missed by a ludicrous margin. I think I missed it by about 2 and a half years or something like that. Uh but fortunately **O'Reilly** were pretty laid-back with the with the second with the first edition and were happy for me to just take my time and make it good. Uh when it came to the second edition then actually O'Reilly got a bit more aggressive and pushy about uh sticking to deadlines. I guess by that point the book had been established and people were waiting eagerly for the second edition. So, I kind of understand the the desire to to want to accelerate it, but at the same time, I I really appreciated the the freedom that I had for the first edition to work on my own schedule. Um, and I had a bit less of that with the second.
</details>

**Gergely Orosz**: 第一版的副标题是“可靠、可扩展和可维护系统背后的重要思想”，我相信第二版也是如此。可靠、可扩展和可维护。这些目标对你意味着什么？

<details>
<summary>Original English</summary>
**Gergely Orosz**: The tagline for the first edition, which I believe is the same as second edition, the big ideas behind reliable, scalable, and maintainable systems. Reliable, scalable, and maintainable. What do these objectives mean to you?
</details>

### 可靠、可扩展与可维护
**Martin Kleppmann**: 是的。所以它们都有点模糊，对吧？所以没有一个正式的定义。但对我来说，**可靠性（reliability）** 主要意味着容错性。也就是说，一个系统即使在网络链接中断或节点崩溃等情况下，也应该能整体上继续工作。所以书中有很大一部分是关于支持容错的技术，比如复制。这就是可靠性。**可扩展性（scalability）** 是一个经常被使用的术语，它被用得太多了，以至于让东西变得可扩展听起来很时髦、很酷，因为它暗示着成功和数百万用户。所以当然人人都希望东西是可扩展的，因为人人都希望成功。在这本书里，我试图采取一种更冷静的方式，我说可扩展性只是我们用来应对负载变化的机制。如果负载增加，我们如何为系统增加计算能力，以使系统仍然能继续工作。然后你用来实现可扩展性的技术，比如分片。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. So they're all slightly vaguely defined, right? So there's there's not a a formal definition of those things. But uh for me, **reliability** means fall tolerance primarily. So meaning that a system should on the whole continue working even if like a network link is interrupted or a node crashes or something like that. So a lot of the book is about techniques that support fall tolerance like replication for example. Um so that's reliability. Uh **scalability** is one of those terms that gets thrown around a lot and it's sort of so much and it's it's like fashionable and cool to make things scalable, you know, because it's it suggests success and millions of users and so that's of course everyone wants things to be scalable because everyone wants success for this book. here tried to take a bit more dispassionate kind of approach and said scalability is just like what mechanisms we have for dealing with changes in load if load increases how can we add computing capacity to a system for example so that the system still continues working and then the techniques that you use to achieve scalability well they are like sharding for example and and
</details>

**Gergely Orosz**: 但在这种情况下，可扩展性，你的定义我是否可以理解为你主要指的是水平可扩展性，所以它们可以或多或少地向上或向下扩展计算能力？

<details>
<summary>Original English</summary>
**Gergely Orosz**: but in this case scalability your definition do I understand that you're mostly referring to horizontal scalability so they cannot compute up or down pretty much.
</details>

**Martin Kleppmann**: 是的，我猜是因为那是更有趣的一个。因为是的，你总是可以买一台更大的机器。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, I guess because that's the the more interesting one like yes, you can always buy a bigger machine and
</details>

**Gergely Orosz**: 这有什么有趣的呢？

<details>
<summary>Original English</summary>
**Gergely Orosz**: what's interesting about that
</details>

**Martin Kleppmann**: 确实，这没什么好说的。我的意思是，即使在单台机器上，也有如何扩展的细节，但我认为，现代云服务和一般后端服务变得有趣的部分在于它们如何引入了水平可扩展性和无共享系统的思想。所以我们可以构建能够应对非常高负载的系统，即使其单个组件只是相当便宜的商用机器。但也许可扩展性故事的一部分，我当时没有想太多，但最近开始更多地思考，不仅是向上扩展，还有向下扩展。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: and exactly there's just there's not that much to be said about it. I mean there are details of how you scale even on a single machine but I think like part of what is become interesting about like modern cloud services and just uh backend services in general is like how they've introduced this idea of horizontal scalability and uh shared nothing systems. So we can build uh systems that you know are able to cope with very high load even if the individual components are just fairly cheap commodity machines. But maybe sort of part of the scalability story which I wasn't thinking about as much at the time but started thinking about more recently is not just scaling up but scaling down as well.
</details>

**Gergely Orosz**: 那么，实际上，你如何以这样一种方式运行一个服务，使得当它负载非常小时，运行成本非常低廉。这在某种程度上与如何在高负载下继续运行一个服务是同一个问题。通常，你只希望成本和计算能力与你拥有的负载大致成比例。而在低端，这意味着实际上能够缩减到运行成本极低的状态。这并非理所当然。例如，对于本地部署的软件来说，这就很难做到，因为如果你有一台物理机器，那就像一个部署单元。是的，你可以把它分割成二十几个虚拟机，让这些小虚拟机运行，但这仍然需要某种资源分配。因此，一些无服务器系统之所以有趣，部分原因在于它们能够缩减规模，比如说，如果你每天只处理三个请求，那也完全没问题。

<details>
<summary>Original English</summary>
**Gergely Orosz**: So actually um how do you run a a service in such a way that if it has a very small amount of load it's really cheap to run it. That's sort of a in a way the same question as how do you continue running a service if it has very high load. Um generally like you just want the the cost and the computing capacity to be roughly proportional to the load that you have. And at the low end that means actually being able to scale down to something that is extremely cheap to run. And that's like not so necessarily a given. That's something that is hard with on premises software for example because like if you've got a machine a physical machine that's like a a unit of deployment and yes you could carve it up into two dozen virtual machines and make those small virtual machines but um it still requires like some sort of resource allocation. So so part of what's interesting about some serverless systems for example is actually their ability to scale down and say like okay if you're going to handle just three requests per day that's just fine as well.
</details>

**Gergely Orosz**: 你能告诉我关于第二版的情况吗？这个想法是什么时候出现的？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Can you tell me about the second edition? When did the idea come about?
</details>

### 第二版的新内容
**Martin Kleppmann**: 是的，几年前就很清楚需要出第二版了，因为第一版已经有点过时了。技术上的一些变化没有在第一版中反映出来。所以我想更新它，但你知道，我现在有了一份学术工作。我实际上在做研究和教学，这是我的主要工作，而更新这本书只是某种副业。所以实际上，要取得进展花了相当长的时间，因为我总是在做其他项目的同时进行这项工作，基本上又回到了我写第一版时遇到的那种上下文切换问题，只是现在我有了一份我不想放弃的学术工作，因为我实际上很享受它。最初，我在第二版上的进展非常缓慢，而且我有点意识到我已经与当前的行业实践脱节了，因为你知道，我已经转向了学术领域。我在理论上走得更深了，但我不再了解人们在数据湖或其他类似方面正在做什么。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, it it had been clear for a couple of years that the second edition was needed just because the first edition was getting a bit dated. There were changes in technology that just hadn't been reflected in the in the first edition. So, I I wanted to update it, but you know, I now have an academic job. I'm actually like doing research and teaching is my main thing, and updating the book is just a sort of sideline business on the side in some sense. So it actually took quite a while to make progress with that because I was always doing it alongside other projects and essentially back to that context switching problem that that I had while writing the first edition but just now um with an academic job that I didn't want to just drop um because actually quite enjoy it initially then I made very slow progress with the second edition and also I kind of realized that I had slightly lost touch with current industry practices because you know I'd switched over to the the academic side. I gone much deeper on the theory. Um, but I was no longer up to speed on like what people were doing with say data legs or things like that.
</details>

**Gergely Orosz**: 于是，在某个时候，我想起了 Chris Riccomini，他是 LinkedIn 的一位老同事。我曾和他一起做过流处理方面的工作。

<details>
<summary>Original English</summary>
**Gergely Orosz**: So then at some point it I remembered Chris Rkamini, an old colleague from LinkedIn. I had worked with him um on the stream processing stuff. Uh
</details>

**Martin Kleppmann**: 你和他一起工作过。他是《The Missing Readme》的作者。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: you work with him. He's he's the author of the missing readme.
</details>

**Gergely Orosz**: 正是。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Exactly.
</details>

**Martin Kleppmann**: 哇，世界真小。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Wow. What a small world.
</details>

**Gergely Orosz**: 是的。我读过克里斯的书《The Missing ReadMe》，觉得他是个很棒的作家。我和他作为软件工程师一起工作过，觉得他是个很棒的同事。而且他还一直在写一个名为《Materialized View》的时事通讯，内容是关于数据系统的最新趋势。他还成了那个领域的创业投资者。所以，在某个时候我想，嗯，实际上我得联系一下克里斯，问他是否愿意帮忙做第二版。他很乐意。那次合作非常成功，因为他对行业技术的最新动态了如指掌。而我对如何教学，也就是如何在书中解释事物，有很强的见解。我要确保我们用非常精确、经过仔细选择的词语来解释一切，但同时又要非常易于理解，以便读者能够轻松阅读。所以我们基本上是把我写作的风格和克里斯对最新行业趋势的知识结合起来，对书进行了更新，那是一次很棒的合作。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Yeah. And uh I I had read Chris's book, The Missing ReadMe, and thought, "Oh, he's a great writer." And I had worked with him as a software engineer and found him him a great colleague and also he had been writing this newsletter called materialized view on uh on like latest trends in data systems essentially uh and become a startup investor in in that space. Um, and so at some point I thought, well, actually I have to get in touch with Chris and ask him whether he wants to help out with the second edition. And he was keen to do that. And that turned into such a good collaboration because he was up to date on like what the cutting edge was in terms of uh technology in industry. Um, I had strong opinions on how to teach essentially. So how to explain things in the book, make sure that we were explaining everything in a in a way that was like very precise, very carefully chosen words, but at the same time very accessible so that it's hopefully easy to read. And so we took essentially like my writing style plus Chris's knowledge of latest industry trends to bring the book up to date and that was a a great collaboration.
</details>

**Martin Kleppmann**: 你们增加了哪些重要的内容？其中哪些是你们早就知道会缺失的，哪些是在写作过程中才意识到需要加进去的？

<details>
<summary>Original English</summary>
**Martin Kleppmann**: what are the big things that you added that and and which ones of these you knew would be missing and which ones did you realize during the writing process that okay this needs to be in here now
</details>

**Gergely Orosz**: 是的，我们从一开始就知道想要反映的是 **云原生系统架构**。这个词有点模糊，但我的意思是，基本上是在云服务之上构建数据系统，并将其作为基础抽象。在第一版中，假设基本上是你有一些机器，每台机器都有一些本地磁盘。你可以在一台机器上运行一个数据库实例，它会把数据写到本地磁盘上。如果你想把它复制到另一台机器上，那么数据库软件会在数据库层面把它复制到另一台机器上，那台机器也会把数据写到它的本地磁盘上。很长一段时间以来，计算机就是这样工作的。而现在，人们突然开始在对象存储之上构建数据库了。现在，复制发生在对象存储层面，而不再是数据库层面。或者可能在数据库层面仍然有一些复制，但如果你是在对象存储之上构建，这确实改变了事情的本质。这和在虚拟块设备（如 EBS 等）之上构建是不同的，因为这些块设备虽然是云服务，但它们仍然提供了一个类似于单节点操作系统的块设备抽象，你可以在其上运行文件系统。而对象存储则是一个全新的抽象，它看起来和文件系统不同，行为也不同。因此，在其之上构建作为基础抽象，是人们在第一版时开始做的事情，但自第一版以来，这种做法已经大行其道，现在有很多系统都是以这种方式构建的。所以，这是我们非常想融入的一个想法，并且我们把它贯穿了全书。所以它不只是这里的一个小节，而是我们整合到整个叙述中的一个想法。

<details>
<summary>Original English</summary>
**Gergely Orosz**: yeah so the thing we knew from the start that we wanted to reflect was uh **cloudnative systems architecture** it's it's a bit of a vague term um but what I mean with that is essentially building uh data systems on top of cloud services as the foundational abstraction in the first edition the assumption was basically that you have some machines. Each machine has some local discs. You can run a database instance on a machine. It will write its data to the local disk. If you want to replicate it to another machine, then well the database software will replicate it at the database level to another machine which will also write the data to its local discs. For a long time that was exactly the way computers worked. And now suddenly people are building databases on top of object stores for example. And now the replication happens at the object store level. No, no longer at the database level. or maybe there's still some replication at the database level but it really changes the the nature of things uh if you're building on top of an object store and this is different from say building on top of a virtual block device like EBS or so because these block devices although they are cloud services but they still offer the abstraction that is a sort of single node operating system abstraction of a block device on top of which you run a file system whereas an object store is just like a brand new abstraction it just looks different from a file system, it behaves differently. And so then building on top of that as a foundational abstraction is something that like people were starting to do at the time of the first edition, but since the first edition that has really taken off like a whole lot of system have have been built in that style now. And so that's an idea that we really wanted to incorporate and we weaved that in throughout the book. So it's not just like one section here. Um but it's it's sort of a an idea that we've integrated throughout the entire narrative.
</details>

**Martin Kleppmann**: 现在也有很多托管服务。我们使用的原生服务，但所有云提供商也使用很多托管服务。很多工程师经常直接使用托管服务，因为它们负责复制，有正常运行时间的 SLA 等等。但是当你构建在这些东西之上，并且你也把它们当作原生服务来使用时，作为软件工程师，你是否不再有动力去理解底层了？或者我们因为这个而构建了更好的系统？你对此有何看法？感觉因为云，抽象层次发生了变化，对吗？

<details>
<summary>Original English</summary>
**Martin Kleppmann**: There's now a lot of managed services as well. The per primitives that we use, but there's also so many managed services that all the cloud providers use and a lot of engineers, they often just use the managed services as is because they they take care of replication. They have SLAs for uptime and so on. But when you build on top of these things and you you kind of use those as a as primitives as well, is there any risk as a software engineer that you're no longer incentivized to understand the underlying layer or are we building better systems because of that? How do you think about this? It it feels there's a move of abstraction because of cloud, right?
</details>

### 云与抽象的演变
**Gergely Orosz**: 是的，这绝对是向不同且更高层次抽象的转变，但你知道，这从一开始就是整个计算行业的历史。就是构建新的抽象。所以，如果你依赖一个更高层次的抽象，你确实不再思考底层的细节了。这就像你使用带垃圾回收器的编程语言，你就不再考虑内存分配了。那么这是一种损失吗？嗯，也许吧。如果你在构建底层系统，你仍然需要关心内存分配。但如果你在构建更高层次的业务逻辑，实际上我认为人们不关心内存管理也完全没问题。所以我觉得在数据系统这里也有类似的情况，如果你在构建不需要特别关心底层基础设施的更高层次系统，那就没问题。就使用更高层次的抽象吧。那没什么错。但仍然需要有人从更低层次的组件来构建那些更低层次的抽象。总得有人去实现那些云服务。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Yeah, it's definitely a a shift to different and higher level abstractions, but you know that's been the story of the entire computing industry since the start. It's like building new abstractions. So it is true that like if you rely on a higher level abstraction, you're no longer thinking about the lower level details. And so it's you're using a a programming language with a garbage collector, you're no longer thinking about memory allocation. And so is that a loss? Well, maybe. Like if you if you're building low-level systems, you should still have to care about memory allocation. You're building higher level business logic. Actually, I think it's just fine for people not to care about memory management. So I think there's an analogous thing here with data systems that if you're building the higher level systems that don't need to particularly care about the underlying infrastructure, then that's fine. Just use the higher level abstractions. Nothing wrong with that. But somebody still has to build those lower level abstractions from lower level components. Somebody's got to implement the cloud services.
</details>

**Narrator**: Martin 谈到了使用云服务带来的权衡。现在是时候谈谈我们本季的赞助商 **WorkOS** 了。如果你读过《设计数据密集型应用》，你就会知道，大规模构建系统完全是关于权衡的。但有一件事不是权衡——那就是企业级功能。当你赢得大客户的那一刻，你就需要 SSO、目录同步、RBAC、审计日志等所有他们期望开箱即用的功能。自己构建这些可能需要数月时间。WorkOS 给你提供了 API，让你可以在几天内交付这些功能，这样你就可以专注于你的核心产品。这就是为什么像 **OpenAI** 和 **Anthropic** 这样的公司都运行在 WorkOS 上。访问 **workos.com** 了解更多。我还想提一下我们的主要赞助商 **Statsig**。Statsig 构建了一个统一的平台，既能进行实验，又能持续交付。内置的实验功能意味着每一次发布都自动成为一个学习机会，通过适当的统计分析，精确地向你展示功能如何影响你的指标。功能开关让你能够自信地持续交付。而且因为这一切都在一个平台上，使用相同的产品数据，你组织内的团队可以协作并做出数据驱动的决策。要了解更多，请访问 **statsig.com/pragmatic**。现在，让我们回到 Martin 这里，继续讨论使用云服务所带来的权衡。

<details>
<summary>Original English</summary>
**Narrator**: Martin talked about trade-offs that come with using cloud services. And this is a good time to talk about our season sponsor **WorkOS**. If you've read designing data intensive applications, you know that building system at scale is all about trade-offs. But one thing isn't a trade-off. That's enterprise features. The moment you land bigger customers, you need SSO, directory sync, arbback, audit logs, all the things they expect out of the box. Building that yourself can take months. WorkOS gives you APIs to ship it in days so you can stay focused on your core product. That's why companies like **OpenAI** and **Antroic** run on WorkOS. Visit workos.com to learn more. I'd also like to mention our presenting sponsor **Statsig**. Statsig build a unified platform that enables both experimentation and continuous shipping. Built-in experimentation means that every roll out automatically becomes a learning opportunity with proper statistical analysis showing you exactly how features impact your metrics. Feature flags let you ship continuously with confidence. And because it's all in one platform with the same product data, teams across your organization can collaborate and make datadriven decisions. To learn more, head to statsig.com/pragmatic. With this, let's get back to Martin and the trade-offs that come with using cloud services.
</details>

**Gergely Orosz**: 所以那些人就必须更专注于如何设计这些云服务的细节，如何让它们可靠，如何运营它们等等。技能还在那里，只是发生了一些专业化分工，一些人可以专注于更高层次的事情，而不必关心底层的事情。而另一些人则专注于底层，并将更高层次的方面视为他们的客户。

<details>
<summary>Original English</summary>
**Gergely Orosz**: And so those people will have to then specialize even more in actually the details of how you engineer those cloud services, how you make them reliable, how you operate them and so on. The skills are still there. It's just a bit of specialization happening that some some people can worry about the higher level things without having to concern themselves with the lower level things. Some people focus on the lower level things and treat that higher level aspect as their customers.
</details>

**Martin Kleppmann**: 有趣。所以在我听来，如果你是一名大量使用这些服务的工程师，你可能不需要知道它们具体是如何工作的。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Interesting. So it it sounds to me that if you're an engineer who is utilizing a lot of these services, you might not need to know how they exactly work.
</details>

**Gergely Orosz**: 是的。我想说，整本书的基本理念是让人们对系统内部工作原理的本质有所了解。这样，如果他们开始遇到奇怪的性能行为，你就能对它为什么会这样做以及你可能如何解决它有一点直觉。例如，存储引擎那一章告诉你 B-tree 和日志结构化的 LSM 树存储引擎是如何工作的。这本书并非为那些要自己构建数据库和实现自己存储引擎的人准备的。如果你想那么做，你需要比这本书深入得多的知识。但它的理念是，作为一个应用开发者，如果你对存储引擎内部的工作原理有一点了解，你就能更好地以一种能给你带来好性能的方式来使用它，并能诊断任何问题。我们也把这个理念保留在了云服务的背景下，是的，云服务隐藏了一些应用开发者不再需要考虑的运维细节，但他们仍然应该对它们内部的工作原理有所了解，以便能有效地使用它们。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Yes. And I would say like the underlying philosophy of the entire book is to give people insights into just the sort of essence of how the systems work internally. So that if for example they start having weird performance behavior, you can have a bit of intuition for why it's doing that and how you might solve it. So for example, say the storage engine chapter tells you about how Bes work and how lock structured LSM trees storage engines work. And the book is not intended for people who are going to actually build their own databases and implement their own storage engines. If you want to do that, you have to go much much more much greater depth than this book covers. But the idea is that as an app developer, if you know just a little bit about how the storage engine works internally, you'll be in a much better place to use it in a way that is that gives you good performance for example and to diagnose any issues. That philosophy we've kept also in the context of cloud services where yes, like cloud service hides some of the operational details that app developers don't need to think about anymore, but they should still know a bit about how they work internally just so that they can use them effectively.
</details>

**Martin Kleppmann**: 我想，关键在于权衡，决定使用哪个服务，注意哪些特性。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I guess I argue about the trade-offs deciding on which which service to use, which characteristics to look out for. Yeah.
</details>

**Gergely Orosz**: 是的，针对你的用例，对吧？正是。你知道，比如说，如果你在做分析，使用行式存储还是列式存储，会有巨大的差异。这是一个有点技术性的区别，甚至需要一些背景阅读才能理解它意味着什么，但它对系统最终行为的性能有巨大的影响。所以，在那些地方，我觉得了解一点内部原理实际上是一种超能力。

<details>
<summary>Original English</summary>
**Gergely Orosz**: For for your use case, right? Exactly. And and you know, they're huge differences of say if you're doing analytics whether you're using row oriented storage or column oriented storage. That's a bit of a technical distinction and it takes a little bit of background reading to even understand what that means, but it has a massive performance implication in terms of the final behavior of the system. And so those are those places where I feel like knowing a bit about the the internals is actually like a superpower.
</details>

**Martin Kleppmann**: 我想工程师们至少有一件事是我们需要一直争论或者应该争论的，那就是成本与性能。我说的性能是指给用户的延迟，当然还有弹性，如果发生什么事，比如一个区域挂了，一个机器挂了，一个区域挂了，一个地区挂了，我们的产品会受到怎样的影响，以及什么是可以接受的。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. And I guess engineers the one thing that we always need to argue about or should need to argue about is at the very least cost versus performance. And by performance I mean latency to the user and of course resilience of if if something happens you know like a region go like a zone goes down a a machine goes down zone goes down region goes down how our product is affected and what's acceptable.
</details>

**Gergely Orosz**: 基本思想似乎是，你愿意承担多大的可用性风险，与之对应的是开销，包括系统本身的计算开销，以及实际设计和运营系统的人力开销和成本开销。

<details>
<summary>Original English</summary>
**Gergely Orosz**: The basic idea there seems to be like how much availability risk are you willing to take on versus the both like the overheads in terms of um the the system itself like the computational overheads but also the human overheads actually designing and operating the system and and the cost overhead.
</details>

**Martin Kleppmann**: 是的，一点没错。所以，你可以拥有一个更能容忍各种故障的系统，但设计和运营它的成本也更高；或者是一个更简单的系统，它可能会更频繁地宕机，但成本更低。这没有对错之分。每个人都需要自己弄清楚他们在这个权衡空间中的位置。我想说，多区域部署就像是朝着更高可用性的方向推进，因为它意味着你可以容忍整个区域的中断。但这样一来，它会对你在不同区域间所能获得的一致性模型产生影响。所以这是一个权衡，这本书试图非常明确地说明这一点，以帮助人们理清思路，为他们自己做出正确的选择。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, exactly. And so yes, you can have a a system that is more able to tolerate various types of faults but it which is more expensive to uh to design and operate versus a simpler system that you know might go down a bit more often but which is cheaper. And there's no right and wrong with that. You know it's a everyone needs to figure out where they sit on that uh on that trade-off space uh themselves. And I would say that like multi-reion is like pushing in the direction of like higher availability because it means you could tolerate the outage of an entire region. But then it has implications on the consistency model that you can get across different regions for example. So that's a trade-off that the book tries to make very explicit to help people reason that through of like what is the right choice for them.
</details>

### 多云与地缘政治风险
**Gergely Orosz**: 比如，关于多云，我最近一个月一直在思考一个问题，那就是欧洲对美国云服务的依赖。

<details>
<summary>Original English</summary>
**Gergely Orosz**: In terms of multicloud, for example, one thing that I've been uh concerned about just in the last month really is uh European dependence on US cloud services.
</details>

**Martin Kleppmann**: 是的。那么如果地缘政治局势恶化，紧张局势升级，欧洲突然发现自己被美国云服务拒之门外会怎样？我希望这不会发生。我仍然认为这相当不可能，但不再是不可想象的了。因此，从欧洲的角度出发，我一直在思考我们如何设计系统来抵御这类事情。你知道，这不仅仅是一个区域性中断，这本质上是一个商业风险。而多云的设置可以帮助减轻这类风险，这样至少，比如说，如果一家公司把你拒之门外，你仍然可以在另一家公司拥有系统。同样，这非常偏向于昂贵但高可用性风险降低的一端。但对于那些工作负载非常关键，并且认为这种地缘政治风险足够重大的人来说，我认为认真考虑这种设置是值得的。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. So what if geopolitics was to go horribly wrong and tensions escalate and Europe finds itself suddenly locked out of US cloud services? I hope that doesn't happen. I still think it's fairly unlikely, but it's no longer unthinkable. and and as a result I coming sort of from this European perspective have been thinking a fair bit about how can we engineer systems to be resilient against that sort of thing and that's you know not just like a regional outage but it's like a a business risk essentially and a multicloud sister uh setup could help mitigate against that sort of risk so that at least for example if one company locks you out then you could still have systems on on another company again that that's very much towards the uh expensive but uh high availability risk reduction end of the spectrum. But for the people who have you know really critical workloads where they think this sort of geopolitical risk is a significant enough risk I think it's seriously worth considering that kind of setup.
</details>

**Gergely Orosz**: 我认为我们确实有责任，因为还有谁会做这件事呢？

<details>
<summary>Original English</summary>
**Gergely Orosz**: I'm thinking that that as we do have the responsibility because because who else will will do this?
</details>

**Martin Kleppmann**: 是的，完全同意。但我也完全同意你说的，理解风险并沟通权衡将成为我们作为工程师前进的核心部分。也许随着人工智能越来越多地编写我们的代码，重点将不再是你在特定编程语言中如何表达逻辑的细节，而更多地是关于那些高层次的权衡。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes, totally. But I totally agree with you as well that this um understanding what the risks are and communicating what the trade-offs are I think is is going to be a core part of our role as engineers moving forward as well. Maybe as AI writes more and more code of our code, it's less about like the details of how you express logic in a particular programming language and much more about those kinds of highle trade-offs.
</details>

**Gergely Orosz**: 在这本书中，“规模”的定义是如何变化的？因为在我们谈论云之前，构建一个可扩展的系统听起来相当复杂，因为构建一个水平可扩展的系统很复杂，你需要把所有的部分都放进去。在第一本书中，你详细介绍了很多这方面的内容。有了云之后，很多服务实际上定义了它们如何允许水平扩展，权衡是什么。你是否觉得在使用这些原生服务时，对规模和可扩展性的推理变得容易多了？

<details>
<summary>Original English</summary>
**Gergely Orosz**: How has the definition of scale changed in this book? Because as we talk with cloud before cloud building a scalable system it sounded pretty involved because building a horizontally scalable system it's it's complicated all all the pieces you need to put it in in the first book you detail a lot of this with cloud a lot of the services actually they do define how they allow horizontal scaling what the tradeoffs are do you feel that it's made a lot easier to reason about scale scalability when you are using these primitives
</details>

**Martin Kleppmann**: 所以我认为，实现真正的高规模仍然具有挑战性。因为即使我们有像对象存储这样的云服务，它为你提供了这种非常有弹性的存储模型，至少你不再需要担心磁盘的容量规划和磁盘空间耗尽的问题。因为那些运维方面的事情都由它们负责了。但如果你需要分片（sharding），那实际上也会反映在应用代码上，你无法让它完全透明。所以当你达到足够大的规模时，分片是必需的，因为单台机器不足以处理你的工作负载。那时我认为即使使用云系统，你仍然需要做相当多的工程思考，来考虑如何实现它。我认为云真正有所帮助的，其实是在缩减规模的低端。如果你想拥有一个处理少量请求的非常轻量级的服务，我们通过无服务器系统能够非常快速地启动和关闭一个实例，非常轻量级，这是一个很好的创新，它使得那些非常低规模的服务成为可能。而如果没有云服务，这将要困难得多，因为你将不得不为特定的虚拟机静态分配一定量的内存和 CPU 资源。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: so I think achieving Being really high scale is still challenging because even though we have cloud services like object storage for example which uh provide you this very elastic storage model at least you don't have to worry about capacity planning on your discs anymore and running out of disk space because those kinds of operational things they're taking care of but if you need sharding for example that's something that actually does reflect on the application code as well you can't really make that entirely transparent and so you're at a sufficiently large scale The charting is required because a single machine is not powerful enough to process your workload. Then I think even with cloud systems you still have to do quite a bit of engineering thinking of u of how to realize that where I think the cloud has helped quite a bit is actually at the lower end of scaling down. Uh if you want to have a very lightweight service that processes only a small number of requests. what we've got with serverless systems being able to very quickly spin up and spin down uh an instance very lightweight that's quite a a good innovation that has enabled those those very low scale uh services and that's something that's would be much harder to do without cloud services because you would have to statically allocate a certain amount of memory and certain CPU resources to a particular virtual machine
</details>

**Gergely Orosz**: 我喜欢无服务器架构。我有一个小型网站就运行在无服务器上，我每个月的账单大概是 13 美分，因为它负载很小。

<details>
<summary>Original English</summary>
**Gergely Orosz**: I love serverless I I have a small website that runs on serverless and my bill is like 13 cents per month because it has very little load.
</details>

**Martin Kleppmann**: 当然。这只是更有效地利用了计算资源。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Absolutely. It's just making more efficient use of computational resources.
</details>

**Gergely Orosz**: 我们来谈谈分片（sharding）。在第一本书中，以及你写第一本书的时候，当我在 Uber 工作时，我们谈论了很多关于分片的话题，有很多内部实现或者面试都会问到分片，因为我们当时在设计分片系统。我确实感觉到，随着时间的推移，随着云系统开始提供更多的一站式解决方案，这些解决方案更像平台，你发送数据，它就负责处理这些事情。需要实际实现分片的工程师越来越少了。在你的研究中，对于云原生系统，你看到了什么？在哪些情况下，实施分片仍然很重要？又在哪些地方，它可能已经作为一个问题消失了？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Let's talk about sharding. In in the first book and when you wrote the first book when I was working at Uber, we talked a lot about sharding and there was a lot of internal implementations or interviews involved asking about sharding because we were designing systems that were sharding. I did sense that over time again as as cloud systems start to become available that give you turnkey solutions more that act more like platforms. You send the data and it takes care of of these things. Fewer engineers have to actually implement sharding with cloud native systems in your research. What have you seen? What what are the cases where putting sharding in place is still important and where are the places where it it might have just disappeared as a as a concern?
</details>

**Martin Kleppmann**: 我想这可能不是云的影响，更多的是硬件变得更强大了。哦，实际上，现在一台大型机器可以做很多事情，这意味着越来越多的工作负载你可以在单台机器上运行，这实际上足以实现相当大的规模了。当然，仍然存在如何有效利用单台机器上数百个 CPU 核心的问题，所以并行性仍然是需要考虑的事情，而分片是实现并行性的一种方式。但至少，跨多台机器的这种分片可能已经变得不那么紧迫了，因为越来越多的工作负载可以在单台机器上运行。当然，有些人仍然有非常大规模的工作负载，必须在多台机器上进行分片，所以它不会完全消失。而且，即使在较小的规模下，复制仍然是相关的，因为那是为了容错，而不是为了可扩展性。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I mean it's still nice to know but you might not have to implement it. I think it's probably less of an effect of cloud and more of just hardware getting more powerful that oh actually like a big machine nowadays can do a lot on a big machine you if you and that means that more and more workloads you can just run on a single machine and that is sufficient actually to achieve quite significant scale already there's still concerns of like how to actually efficiently make use of hundreds of CPU cores that you have on a single machine so there's still parallelism is still are a required thing to think about there and sharding is one way of achieving parallelism. But at least this sort of sharding across multiple machines is maybe become less of a pressing issue just because more and more workloads can just run on a single machine. Some people still have very large scale workloads that do have to be sharded across multiple machines but it's not going away entirely and uh replication is still relevant even at smaller scales because that's for fall tolerance that's not for scalability.
</details>

### 分布式系统的麻烦
**Gergely Orosz**: 你有一章叫做“分布式系统的麻烦”，其中讲了很多可能出错的事情。不详细讲整章内容，你能回忆起一些让你印象深刻或者你觉得很重要的点吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: You have a chapter called the troubles with distributed systems uh which goes through a lot of things that can go wrong without going through the whole chapter. Can you recall some of the things that are memorable to you or some of the things that you feel are are important to remember?
</details>

**Martin Kleppmann**: 是的。这一章的核心思想是，在分布式系统理论中，我们倾向于做一些假设。比如，我们只是假设消息通过网络传输的时间没有上限。你发送一条消息，它可能在 100 微秒内到达，也可能需要 10 年。分布式系统理论如果能避免的话，就根本不对这类时间做任何假设。或者说，有些理论确实做了这些假设，但这是一个危险的假设，因为网络延迟偶尔确实会变得比通常情况高得多。另一件事是关于崩溃。例如，分布式系统理论只说节点会崩溃，但这到底意味着什么？在实践中，一个节点变得不可用意味着什么？它可能是软件崩溃，但也可能是硬件故障。可能是有人拔掉了电源线。也可能是节点实际上还在运行，只是与网络断开了连接。这一章的重点实际上是为我们用来分析分布式系统的那些理论模型进行辩护和证明，并提供了大量的故事和案例研究，表明实际上会出很多问题。所以不要相信任何人说“哦，故障很少见，别担心，没事的”。这一章的寓意是，实际上，如果你想让系统可靠，你真的必须担心一大堆奇怪的、不寻常但确实可能发生的边缘情况。时间是另一个问题，你知道，很容易假设你的时钟是准确的，而且大多数时候时钟都相当准确，但我们就是不能依赖它，因为实际上它们整体上不够精确。所以很多时候，我们很容易做出某些假设，认为事情是良好运行的，但在分布式系统中，如果我们希望系统在出现问题时仍能可靠工作，我们就必须设法摆脱这些假设。但写这一章真的很有趣，因为你知道，它基本上是各种出错事件的大集合。所以我查阅了各家科技公司发布的事故报告，以了解事情出错的根本原因，以及我们可以从中吸取哪些适用于本书的教训。而且你知道，还有一些有趣的事情，比如鲨鱼咬断海底电缆并损坏它们，这就成了一个很棒的故事。然后我听说近年来海底电缆的屏蔽做得更好了，所以鲨鱼不再咬它们了。但相反，陆地上的牛会踩到电缆，偶尔也会导致网络中断。你知道，这类事情让它变得更有趣了。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. The whole idea of this chapter is that in distributed system theory there are certain things that we tend to assume. Like for example, we just assume that there's no upper bound on how long it might take for a message to go over the network. So you send a message, it might arrive within a 100 microsconds or it might take 10 years and distributed system theory just doesn't make any assumptions about that sort of timing if we can avoid it or rather some some theory does make those assumptions but it's an dangerous assumption to make because occasionally the network delay does become much higher than than what is typical. Another thing is about uh crashes. For example, the distributed system theory just says like nodes can crash but what does that actually mean? Like what in practice does it mean for a node to become unavailable because it might be a software crash but yes it might be a hardware failure. It might be somebody unplugging the power cable. It might be that the node is actually still running but it's just become disconnected from the network. The point of this book chapter really is to defend and justify those theoretical models that we use for analyzing distributed systems and just giving a lot of stories and case studies that show that you know actually tons of stuff does go wrong and like don't believe anyone who says oh failures are rare it's don't don't worry about it it's fine. Uh the the the moral of this chapter is really that actually know if you want to make things reliable, you really do have to worry about a whole bunch of weird unusual but but certainly possible edge cases. Timing is another one of those things like you know it's very easy to assume that your clocks are correct and most of the times the clocks are pretty correct but we just can't rely on it because actually they're just not precise enough uh on the whole and so a lot of it is about it's very tempting to make certain assumptions um that things are well behaved and and in distributed systems we just have to try to get away from those assumptions if we want the systems to work reliably even in the face of things going wrong but it was a really fun chapter to Right? Because you know it's it's essentially a big collection of stuff that has gone wrong. And so I went through a bunch of postmortems published by various tech companies for example in order to see okay what was the root cause of how things went wrong and what kind of lessons can we draw from this that apply to the the book in general. And uh you know there's some fun stuff like the the sharks biting undersea cables and damaging them that just you know makes for a great story. And then I I hear that in recent years the shielding of undersea cables has got better and therefore the sharks are not biting them anymore. But instead the cows on land are stepping on cables and occasionally causing network interruptions that way. And you know that sort of thing is just uh it makes it a bit more fun.
</details>

**Gergely Orosz**: 那一章也非常有趣，因为取决于你在什么样的团队工作，或者你和什么样的人交谈。当我和 S3 团队交谈时，对他们来说，那一整章就是他们的日常工作。这不是什么奇怪的事情，你知道，比如硬盘坏了，或者数据中心着火了，这可能是件奇怪的事，但他们对所有这些事情都做好了准备。他们所处的规模决定了这些事情会以固定的频率发生，因为他们是规模最大的之一。而在一个较小的公司，即使你读了这一章，你也会把它当作“嗯，这可能会发生”，但当它真的发生时，那将是十年一遇的大事。

<details>
<summary>Original English</summary>
**Gergely Orosz**: That chapter is so interesting also because when depending on what kind of teams you work on or what kind of people you talk with when I talk with the S3 team for them that whole chapter is just their dayto-day. It's it's they they don't it's not a weird thing when you know like a a hard drive goes up or or there might be okay it might be a weird thing to have a fire in a data center but they're prepared for all of those things. They're at the scale where these things just happen on a regular cadence because they're one of the the largest scales whereas at a smaller company even if you read this chapter and you know you will treat this as like well this could happen but when it h when it actually happens it will be a once in 10 year and it will be a big deal.
</details>

**Martin Kleppmann**: 是的。但我认为没有一个“正确”的答案。这广义上是风险和成本之间的权衡。这意味着企业需要就其希望在这一权衡中处于何种位置做出商业决策。因此，本章的目标实际上只是为人们提供信息，以便他们做出明智的决定。但我不想替人们做那个决定。那是由企业自己决定的。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. But I think there's there's no like right answer. It's a it's a trade-off between risk and cost broadly speaking. And that's means a business decision has to be made in terms of where the business wants to lie uh on that trade-off. And so the goal of this chapter is really just to give people the information in order to make an educated decision. But I don't want to make that decision for people. That's for businesses themselves to decide.
</details>

**Gergely Orosz**: 这一点非常清楚。你有没有遇到过在第一版书中提到，而现在第二版书中变得更受欢迎或更不受欢迎的概念或系统？随着时间的推移，你的读者对流处理系统、批处理或其他任何东西的引用是多了还是少了？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Uh that's very clear. Have you come across some concepts or sips as mentioned in the book in the first edition and now in the second edition that are becoming either more popular or less popular over time more or less referenced by your readers thinking about from things like streaming systems, batch processing or or anything else?
</details>

### MapReduce 已死，向量索引兴起
**Martin Kleppmann**: 是的。有些东西我们已经可以从书中删掉了，与第一版相比，特别是比如 MapReduce 的内容在第一版中相当详细，但基本上 MapReduce 已经死了，没人再用了。它的继承者，比如 Spark 和 Flink，还在被使用，所以我们在第二版中仍然提到了 MapReduce，但更多是作为一个学习工具，为了理解这些分区、分片的批处理系统是如何工作的。所以这是我们能够减少篇幅的一个地方。但我们增加篇幅的其他领域是，例如，支持人工智能的系统。所以，尽管这不是一本关于人工智能的书，但在需要支持人工智能应用时，仍然会出现数据系统方面的问题，一个典型的例子就是向量索引。因此，我们在存储引擎那一章增加了一些关于向量索引的内容。这非常契合，因为它本来就已经涵盖了各种不同的索引策略。所以向量索引，你知道，只是另一种索引策略。我们还增加了一些关于数据帧的内容。这不完全是人工智能的东西，但数据帧是训练数据的一个很好的数据表示方式。这是我们在第一版中没有讨论的数据模型，但我们决定在第二版中加入，因为它实际上已经成为人们在关系型、图和 JSON 文档等经典数据模型之外使用的非常重要的数据模型。所以在这些地方，我们只是扩大了一点覆盖范围，以反映人们正在构建的系统类型，例如支持人工智能的系统，而没有完全改变书的方向。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. So the some things that we've been able to take out uh out of the book compared to the the first edition in particular for example coverage of map reduce was quite detailed in the first edition but basically map reduceuce is dead nobody uses it it anymore. It's successors like in the form of spark and flink for example they are used and so we still reference map reduce in the second edition but more as a learning tool in order to understand how these kind of partition sharded batch processing systems work. So that's one thing where we've been able to reduce the coverage. Um, but other areas where we've increased the coverage are, for example, systems in support of AI. And so, even though this is not an AI book, but there are still data systems concerns that arise when needing to support AI applications, like a classic one is vector indexes, for example. And so, we've added some coverage of vector indexes to the storage engine chapter. Fit in really well there because it already covers various different indexing strategies anyway. Uh and so vector indexes, you know, it's just another indexing strategy. We also added some coverage of data frames, for example. That's not an exclusively AI thing. Um but data frames are quite a good data representation for training data, for example. And that was not one of the data models that we discussed in the first edition, but we decided to add to the second edition because it has actually become a very important data model that people are using alongside all of the classic data models like relational and graph and uh JSON documents and so on. And so there these these places where we've just expanded the coverage a bit to to reflect the kinds of systems people are building for example to support AI without it like changing the direction of the book entirely.
</details>

**Gergely Orosz**: 在第一版的最后几个小节，标题是“做正确的事”，而在第二版中，这成了一个独立的章节。最后一章是“做正确的事”，我引用其中的一小段话：“我们，构建这些系统的工程师，有责任仔细考虑这些后果，并有意识地决定我们想生活在一个什么样的世界里。”我们可以谈谈这一部分以及它的重要性吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: The final subsection in this first edition the first few I guess like sub parts were titled doing the right thing and in the second edition this has its own chapter. The final chapter is doing the right thing and I I quote a little bit from it. We the engineers building these systems have a responsibility to carefully consider those consequences and consciously decide what kind of world we want to live in. Can we talk a little bit about this section and the importance of it?
</details>

### 做正确的事：工程师的伦理责任
**Martin Kleppmann**: 当然可以。是的。在第一版中加入一个关于伦理的部分的动机是，我只是觉得在我的行业生涯中，这个问题一直被忽视。在初创公司尤其如此，人们非常专注于打造一个客户会喜欢的产品，而在这个过程中，这些伦理问题往往被放在了次要位置。例如，对于面向消费者的产品，它们可能非常倾向于数据收集，收集行为数据，因为这些数据可以以广告的形式变现。对于这些事情的好坏，似乎很少有人反思。所以我真的只是想鼓励大家对此进行一些思考。我并不想规定一种特定的方法，但至少要指出，你知道，现在有像数据保护法规这样的东西，我们在设计数据系统架构时必须考虑到这一点，并且我们有伦理责任。你知道，人们说你进入科技行业是为了改变世界。如果你想改变世界，那么思考你的技术对世界的影响就是你工作的一部分。这确实是一个非常重要的部分，而工程师们在专注于技术本身，而较少关注技术在现实世界中会产生的影响时，往往容易忽略这一点。所以这一章实际上只是试图让人们对此多一些思考。这也反映了我自己的思考过程，因为当我开始从事这些系统的工作时，我也没有特别考虑过伦理问题。所以我觉得我必须把那部分加进去，既为我自己，也为读者，因为这是我自己处理这些问题的一种方式。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Absolutely. Yeah. So the motivation for putting in an ethics section there in in the first edition was that I just felt it had been quite ignored as a concern during my time in industry. um that like especially in startups people were very focused on like building a product that their customers would love and really like deprioritizing these sort of ethical questions in the in the process. And so for example with the consumerf facing products it might be that the products are very much geared towards essentially data harvesting collecting behavioral data um because that's what can be monetized in the form of advertising and there seemed to be just very little reflection on what was good and bad about these sort of things. So I really just wanted to encourage a bit of thinking there. Um not really wanting to prescribe too much like a a particular approach there but at least to point out you know there there is this thing such as data protection legislation now which we do have to think about in the architecture of our data systems and there is an ethical responsibility. You know pe people say that uh you get into tech in order to change the world. If you want to change the world, then thinking about the impact that your technologies have on the world is part of your job. It's it's a really essential part really and something that engineers are often prone to ignoring as we focus just on the technology and less on the effects that that technology will have out in the real world. And so this chapter is really just an attempt to get people thinking about it a bit. And it's sort of a a reflection of my own process as well because as I started working on these systems, I didn't really think about ethical things particularly either. So I felt like um I had to put that section in there for myself as well as for the readers because it was my own way of of grappling with these questions a bit.
</details>

**Gergely Orosz**: 这么说公平吗？作为构建这些系统的工程师，这些系统将对广泛的事物产生影响，可能是社会范围的影响，我们处于一个可以直接影响甚至改变方向的绝佳位置。所以我是否可以理解，这一部分是在提醒我们，通过构建它，我们有巨大的机会来塑造这些东西，我们可能有比监管者在多年后可能拥有的声音更强大的声音，甚至同样强大。对吗？

<details>
<summary>Original English</summary>
**Gergely Orosz**: Is it fair to say that as engineers building these systems that will have an impact on on a wide range of things potentially societal wide impact we are just in such a good position to directly influence and maybe even change course. So do I understand that this section is a bit of reminder that by building it we have a huge opportunity to shape these we probably have a lot stronger voices maybe as strong voices as later on the regulator might have years down the road. Right.
</details>

**Martin Kleppmann**: 没错。我认为工程师在这方面有非常强大的话语权。就像我们之前讨论的，工程师需要以一种方式阐明权衡，以便商业领袖能够就如何处理这些权衡做出明智的决定。而这些权衡的一部分就是指出风险。风险不仅包括技术风险，比如数据可能被损坏，也包括社会风险。例如，这项技术可能会产生什么样的负面影响，什么样的危害，可能会有什么意想不到的后果，或者如果技术被证明有一些有害影响，可能会有什么声誉损害的风险。这些都必须成为权衡讨论的一部分。我只是希望人们能对这类事情做出有意识和深思熟虑的决定，而不是把它掩盖起来。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Exactly. I think engineers have a very strong voice there and like we talked about earlier um engineers need to articulate trade-offs in such a way that uh business leaders can then make educated decisions about how to address those trade-offs. And part of those trade-offs is pointing out risks. And risks include not just technical risks like the data might get corrupted, but they include societal risks as well. For example, like um what negative uh effects, what harms might arise from this technology, what sort of unintended consequences possibly or what like uh risk for reputational damage if it turns out that a technology has some harmful effects. um you know that can reflect badly on the company that made it and that has to be part of the the trade-off discussion and I just want people to make intentional and deliberate decisions about this kind of things and not just sweep it under the carpet.
</details>

### AI 时代的软件正确性与形式化验证
**Gergely Orosz**: 最近的热门话题之一当然是人工智能，你去年十二月写了一篇非常有趣的文章，是关于**形式化验证（formal verification）**以及你为什么坚信它在人工智能时代会变得更重要。对于那些听说过形式化验证的用户，我们能谈谈这是什么吗？以及你如何预见它会变得更重要？

<details>
<summary>Original English</summary>
**Gergely Orosz**: One of the hot topics these days is of course AI and you've written a very interesting post about this just in December about **formal verification** and how your conviction that formal verification might be more important with AI. Can we talk for for those of users who have heard formal verification, can we talk about what this is and how you envision this becoming more important?
</details>

**Martin Kleppmann**: 是的。所以，形式化方法有很多种。一种方法是，例如，使用像 **TLA+** 或类似规范语言来描述系统在高级别上的预期行为，然后使用模型检查器——本质上是一个随机测试用例生成器——来模拟大量场景，看系统是否在所有不同场景下都具有所需的行为。这可以说是入门级的形式化验证。更高级的层次是使用实际的形式化证明。在这种情况下，你可以用一种形式化语言（通常使用数学符号）来编写某个系统的规范，然后做一个数学证明，证明某个算法或某个实现总是满足该规范。与测试的区别在于，测试只是尝试几个例子，给算法一些示例输入，然后检查在那些特定例子中是否得到预期的输出。但一个证明可以推理潜在的无限状态空间。所以它可以告诉你一些关于在整个宇宙中可能发生的每一件事，证明例如某个安全属性在任何情况下都是成立的。形式化验证工作量很大。我在工业界的时候从来没用过，因为它太耗时了。我是在学术界才开始接触形式化验证的，那时我才有时间花几个月来证明一个算法是正确的。但我开始发现这非常有用，特别是在我研究非常微妙的算法时，仅仅通过阅读实现很难判断它是否在所有可能的情况下都总是正确的。但如果这是一个重要的算法，例如，如果它有错误会导致数据损坏，或者有错误会导致安全漏洞，那么当风险很高时，我觉得进行形式化验证是值得的，以真正确保代码是正确的。所以我做了一些使用 **Isabelle** 证明助手（proof assistant）的形式化证明，当然还有其他一些，比如 Coq 和 Lean 等等。这些证明真的很难写。学习编写这些证明的语言需要很长时间。然后即使你掌握了语言，实际编写单个证明步骤也仍然非常费力。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. So there's a whole range of formal methods. Um, one approach is to for example use a specification language uh like FSBY or **TA+** or something like that to describe the expected behavior of a system at a at a high level and then use a model checker which is essentially like a randomized test case generator to just play through a lot of scenarios and see whether the the system has those desired behaviors in in all the different scenarios. That's like the sort of intro level formal verification. I would say the more advanced level is to use actual formal proof and in that case you can write a specification of some system in a formal language is usually using mathematical notation and then make a mathematical proof that a certain algorithm or certain implementation always satisfies that specification. And the distinction to testing there is that well in testing you just try through a couple of examples, give the algorithm some example inputs and check whether you get the expected output in those particular examples. But a proof can reason about potentially infinite state spaces. So it can tell you things about like every possible thing that could possibly happen in the entire universe show that for example a certain safety property is is always given in those formal verification is is a lot of work. Um, I never used it in my time in industry because it's just too too timeconuming basically. Um, I only got into formal verification when I was in academia and I could afford to take the time to spend a few months proving an algorithm correct. But there I've started finding this very useful especially if I was working on very subtle algorithms where it's very hard to tell just from reading the implementation whether this actually is always correct under all possible cases. But if it's an important algorithm where for example uh it will corrupt data if there's a mistake in it or it will have a security vulnerability if there's a mistake in it then when it's high stakes uh things like that then I feel it's worthwhile to have uh formal verification and to really make sure that the the code really is correct and so I've done some uh formal proofs using the **Isabelle** proof assistant for example there are a couple of others as well uh uh like rock and lean and uh so on. These proofs are really hard to write. It's it takes a long time to learn the language of writing those proofs. And then even once you know the language, it's just really laborious in order to actually write the individual proof steps.
</details>

**Gergely Orosz**: 你说它很难写，对于一个会编程、了解多种不同语言的人来说，你能解释一下“难写”是什么意思吗？它感觉像是一种有各种规则的严格编程语言，还是很多数学公式？是什么让你觉得学习和掌握它很困难？

<details>
<summary>Original English</summary>
**Gergely Orosz**: And when you say it's hard to write, just as someone I I know how to code, you know, all so many different different languages. Can you just explain what what it means to hard to write? Is is it does it feel like a a strict programming language with all sorts of rules or lots of math formulas? What what makes it hard for for you to to learn it and and get good at it?
</details>

**Martin Kleppmann**: 是的。所以，你是在试图证明一段代码总是满足某个属性。在某些情况下，这个属性可能很容易指定。举个很简单的例子，你有两个列表，你想把它们连接起来。然后你想证明连接后列表的长度等于两个单独列表长度的和。你知道，一个非常简单的属性。你会如何证明这样的事情呢？嗯，你会有一个连接两个列表的函数，然后你可能会对其中一个列表进行归纳证明，以表明，好吧，如果你有一个长度为 i 的列表和另一个长度为零的列表，那么两者的和就是 i。如果你有一个长度为 i 的列表与一个长度为 1 的列表相加，那么结果是 i + 1，以此类推。然后通过使用归纳证明，你就可以证明连接后列表的长度是 i + j，其中 i 和 j 是两个输入列表的长度，对于 i 和 j 的所有可能值都成立。这是你在测试用例中可能会测试 j 等于 0，j 等于 1 和 j 等于 5 的情况，然后就完成了。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. So, you're trying to make a proof that a certain piece of code always satisfies a certain property. In some cases, that property might be quite easy to to specify. Let's say as a really simple example, you have two lists and you want to concatenate them. And then you want to prove that the length of the concatenated list equals the sum of the two individual lists. You know, very very simple property. How would you prove something like this? Well, you would have a function that concatenates two lists and then you would probably do a proof by induction over one of the lists uh that shows that okay, well, if you have one list of length uh I and another list of length zero, well then the sum of the two is I. If you have a list of length i appended with a list of length one, well then it's i + one and so on. And then by using a proof by induction, you can then show that uh the length of the concatenated list is i + j where i and j are the lengths of two the two input lists for every possible value of i and j. And this is something that uh you know in a test case you would in tests you would maybe test it for the cases of j equals 0, j equals 1 and j equals 5. And then you're done.
</details>

**Gergely Orosz**: 还有 j 等于整数最大值。是的，边缘情况。我们就是这么做的。我就是这么写单元测试的。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Nj equals inter max. Yes, the edge case. That's what we do. That that's how I write my unit test.
</details>

**Martin Kleppmann**: 没错。所以这是一个微不足道的例子，比如列表连接。你可以很容易地阅读代码并说服自己它是正确的。但如果是一个更复杂的算法，那么我们的大脑就无法很好地理解它，以至于真正说服自己它是正确的，如果你不证明它的话。这就是这些证明变得有用的地方。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Exactly. And so this is a trivial example like list concatenation. You can easily just read the code and convince yourself that it's correct. But if it's a much more complex algorithm, then you our brains just can't like grock the algorithm well enough to really convince ourselves that it's correct if you don't prove it. And that's where these these proofs then become handy.
</details>

**Gergely Orosz**: 如果我是一名工程师，并且对开始学习形式化验证感兴趣，比如说因为我认为它在人工智能领域会更重要，而且写这些东西会更容易。你会建议工程师从哪里开始，或者你是如何进入这个领域的？

<details>
<summary>Original English</summary>
**Gergely Orosz**: If I'm I'm an engineer and I would I would be interested in getting started with formal verification for example because I have the notion that it will be more important with AI of course it will be easier to to write these things. Where would you point engineers to to get started or how did you get started in this field?
</details>

**Martin Kleppmann**: 我建议从模型检查开始。像 TLA+ 或 Alloy 这样的工具比像 Isabelle、Coq 和 Lean 这样的证明助手更容易上手。那些证明助手需要大量的额外知识，而且坦率地说，学习编写这些形式化证明的资源并不特别好。我也没有找到特别好的相关书籍。我学习的方式是和我们实验室的一些同事一起工作，他们通过多年的先前经验学会了这些。我就和他们坐在一起，在桌子旁结对编程，我描述我想要证明的东西，他们一步步地向我展示如何证明，如何分解它。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I would suggest starting with model checking. So something like TA plus or FSB are much friendlier to getting started with compared to proof assistants like Isabel Rock and Lean. that these proof assistants just require a whole lot of additional know knowledge and the resources for learning about writing these formal proofs are to be honest not particularly good. I haven't really found really great books on it as well. The way I learned it was by working with some colleagues uh in my lab who who had learned it through years of prior experience and I just sat down with them and paired with them at a desk where like I described the thing I was trying to prove and they showed me how to prove it step by step how to break it down.
</details>

**Gergely Orosz**: 我很想看看你的想法是否正确，那就是这件事会变得更主流，希望我们也会有更好的书籍和资源。

<details>
<summary>Original English</summary>
**Gergely Orosz**: I'm interested to see if if what if you're thinking will be correct which is this thing will go more mainstream and hopefully we'll have better books and resources for it as well.
</details>

**Martin Kleppmann**: 是的，我确实希望如此。我认为形式化验证在未来可能变得更重要有几个方面的原因。一个原因是 **LLM（大语言模型）** 越来越擅长编写这些证明。如果我们人类不必手动编写证明，那么在以前不经济的情况下做这些事情就变得可行了。但同时，LLM 也增加了对这些形式化证明的需求，因为你知道，我们正在大量地编写代码。如果我们必须手动审查所有这些代码，那么审查就会成为瓶颈。所以，如果我们真的想从人工智能中获益，我们也不能让人类来审查所有生成的代码。因此，我们需要某种自动化的方式来检查代码是否正确。编写大量的测试是一个非常好的起点。但证明能做到而测试做不到的是，考虑所有可能发生的事情。这在安全领域尤为重要，因为只要有一个小小的 bug，就可能造成一个漏洞，从而破坏整个系统的安全性。所以我感觉，在那些我们真正想要确保完全没有 bug 的领域，形式化验证才能真正大放异彩。我希望 LLM 实际上能让那些以前因为太难太贵而没有考虑过使用形式化验证的人更容易地接触到它。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes, I do hope so. So the the reason I think that um the I believe that this formal verification could become more important in the future is kind of several aspects to it. One is that the **LLMs** are getting increasingly good at writing these proofs and if we don't have to write the proofs by hand as humans, it just becomes feasible to do them in situations where previously it would have not been economical. But also, LLM increase the need for these formal proofs because, you know, we're vibe coding a bunch of stuff. If we have to manually review all of that code, then that will become the bottleneck. So, we can't really have humans reviewing all of the generated code either if we really want to get the the benefits of of AI. So, we need some automated way of checking whether the code is correct. And writing lots of tests is a very good starting point. But the thing that proof can do that tests can't is to consider absolutely every possible thing that could happen. And that's really important in a security context for example where it just takes one little bug want to create a vulnerability that destroys the security of the whole system. And so I feel for those domains where like really we want to ensure there's a complete absence of bugs that's the kind of of places where formal verification can really shine. And I'm hoping that LLMs will actually make that a lot more accessible to to people who would have previously not considered using formal verification because it was just too hard and too expensive.
</details>

### 学术界与工业界
**Gergely Orosz**: 你曾在工业界工作，然后进入了学术界。你能告诉我们两者之间的区别吗？我自己和大多数观众都在你所说的工业界工作，在科技行业或不同的公司工作。我们自力更生，或者只是在构建自己的东西。学术界与此有何不同？你和你的同事在学术界做什么？

<details>
<summary>Original English</summary>
**Gergely Orosz**: You've worked in the industry and then you went into academia. Can you tell us what the difference is between us? Myself and and most people watching work in what you would call industry and the tech industry or work at different companies. We're bootstrapping our own or we're just doing build building our things. How does academia contrast to to this? What what do you and your colleagues do inside of academia?
</details>

**Martin Kleppmann**: 是的，在学术界内部，实际上有很多不同的风格。不是只有一种。有些人完全走理论、数学路线，根本不关心现实世界，只想研究那些智力上有趣的东西。这没问题。有些人则非常偏向应用，希望做那些很可能对现实世界产生影响的研究。我更偏向应用端。那也没问题。但一个共同的区别是，学术界可以思考得更长远。你知道，如果你在创业，你必须在几个月内拿出东西来。你没法去思考十年后的未来。嗯，也许你会有某种长远愿景，并逐渐向它靠近，但你确实必须在相当短的时间内交付东西。在一家大公司，也许如果你在做基础设施之类的，你可以思考得更长远一些，因为对需要什么的要求可能理解得更透彻。在这种情况下，确保系统是可扩展的、运维稳健的等等，需求就很明确了。这时你仍然可以实现它，但在这种情况下，你可以思考得更长远一些。但在学术界，我真正欣赏的是可以自由地从事那些长期的、不立即具有商业可行性、或与商业公司激励机制不一致的事情。我从事的一个研究领域已经好几年了，我们称之为 **本地优先软件（local-first software）**，它的理念是，我们想从云运营商那里收回一些权力，还给最终用户。所以最终用户应该能更多地控制自己的数据，更少地依赖云服务来提供他们需要的应用程序和数据。而这对于公司来说是不自然的，对吧？因为软件即服务（SaaS）业务，比如说，它们之所以能收取订阅费，就是因为它们能够基本上用枪指着客户的头说：“付我们订阅费，否则我们就删除你所有的数据。”我完全理解导致这种情况的商业需求，但这也导致了人们一直被枪指着头的情况。在我看来，这并不是一个健康的状况。但要以一种方式改变这种情况，从客户头上拿走那把枪，如果你是一家收入依赖于维持这种锁定状况的公司，那就很难了。而在那里，我觉得在学术界，我有自由去做那些与公司商业激励相悖的事情，然后说，不，我将做我认为对用户正确的事情，我会说，制造软件的公司的商业模式是次要的。我能负担得起这样做，因为我不依赖这种商业模式。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, within academia, there are lots of different styles really. There's not not one thing. Um, some people go full-on theoretical, mathematical, don't care about the real world at all, just want to work on things that are intellectually interesting. And that's fine. And some people uh are at the very much at the applied end of wanting to do research that is likely to have a real world impact. I'm more on the applied end. And that's fine too. But a common distinction there is that academia can just think much longer term. So the you know if you're doing a startup you have to ship something within a few months. You can't afford to think 10 years into the future. Well, maybe you'll have sort of a a sort of long-term vision that you're gradually getting towards, but uh you do have to really ship things on a fairly short time scale. At a bigger company, maybe if you're working on infrastructure or so, you can think on a bit of a longer time scale because the the requirements of what are needed is are perhaps better understood. Um and in that case, uh you know, they're making sure that the system is like scalable, operationally robust, and so on. it's then fairly clear what the requirements are and it's still a matter of implementing it but in that case you can think a bit longer term but in academia what I really appreciate is the freedom to work on things that are long-term and which are not like immediately commercially viable or which are not aligned with the incentives of commercial companies. Um so one of research area that I've been on for several years now is what we call **local first software** which is this idea that we want to take away a bit of the power from cloud operators and give it back to end users. So end users should be more in control of their own data and less dependent on cloud services for providing the applications and the data that that the users need. And that's something that doesn't naturally come to companies, right? Because uh software as a service businesses, for example, the whole reason why they can charge a subscription is because they are able to essentially hold a gun to the customer's head and say, "Pay us your subscription, otherwise we will delete all your data." And I totally understand the the commercial imperatives that lead to that, but it also leads to this situation where like the people have a gun against their head all of the time. That isn't really a healthy situation to be in in my opinion. But changing that in such a way to take away that gun from customers heads is difficult if you're in a business whose revenue depends on perpetuating that kind of lock-in situation. And there I feel like in academia I have the freedom to work on things that go against this commercial incentive of companies and say like actually no I'm going to do what I think is right for the users and that I'm going to say the commercial model of the companies making the software is second priority and I can afford to do that because I'm I'm not dependent on this commercial model.
</details>

**Gergely Orosz**: 除此之外，这也是非常有趣且具有挑战性的工程问题。对吧。

<details>
<summary>Original English</summary>
**Gergely Orosz**: To add to this, it's very interesting and challenging engineering problems. Right.
</details>

**Martin Kleppmann**: 是的。能在从事有趣的工程和计算机科学问题的同时，追求这种更高层次的本地优先软件愿景，真是太棒了。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. And it's wonderful to get to work on interesting engineering and computer science problems while at the same time like trying to pursue this uh this higher level vision for local first for first software.
</details>

**Gergely Orosz**: 要实现更可行的本地优先软件，我们需要解决哪些真正有趣的工程挑战？比如说，笔记软件，这是一个很受欢迎的领域，对吧？

<details>
<summary>Original English</summary>
**Gergely Orosz**: What are some of these really interesting engineering challenges that we we will need to solve or or we need to solve to get to a more viable local first software? May that be like let's say note-taking. It's a very popular one, right?
</details>

### 本地优先与去中心化
**Martin Kleppmann**: 是的。所以，在我们本地优先软件的愿景中，我们试图摆脱对中心化云服务的依赖。可能仍然会有云服务参与同步你手机和笔记本电脑之间的数据，因为通常通过云服务是建立这种通信的最便捷方式。但我们只是不想必须信任某个云服务来提供特定功能。如果你能摆脱对这一个云服务的假设，你就可以，例如，同时在多个云提供商上拥有多个云服务，然后你只需与最先响应的那个同步，或者与所有同步，然后如果其中一个消失了，也没问题，因为你还有另一个。所以，如果我们摆脱了中心化云服务的假设，这将给我们带来巨大的自由和灵活性。但这引入了一大堆有趣的研究和工程挑战。我们最近一直在研究的一个问题就是访问控制。你知道，一个简单的问题，你有一个文档，你希望能够授予协作者访问权限，也希望能够撤销该访问权限。这又是一个非常明显，应该非常直接的问题。在中心化的云服务模型中，这确实非常直接。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. So with our vision of local first software, we're trying to get away from this dependency on centralized cloud services. There may still be cloud services involved in syncing data between your phone and your laptop say um because often going via cloud service is just the most convenient way of establishing that kind of communication. But we just don't want to have to trust on a cloud service providing a particular function. Then if you can get away from assuming this one cloud service, you could for example have multiple cloud services on multiple cloud providers side by side and you just sync by whichever happens to respond first or sync with all of them and then if one of them disappears, no problem because you've got the other one. And so it gives us a huge amount of freedom and flexibility if we get away from this assumption of centralized cloud services. But that introduces a whole bunch of interesting research and engineering challenges because uh so one thing that we've been working on lately say is access control. You know simple problem you have a document you want to be able to grant collaborators access and you want to be able to revoke that access. Again totally obvious to should be totally straightforward. In a centralized cloud service model it is totally straightforward because
</details>

**Gergely Orosz**: 你有规则，你确认那些东西，你检查正确的角色，然后就这样了。

<details>
<summary>Original English</summary>
**Gergely Orosz**: you have the rules you you you you confirm that those sort of things and you check for the right roles and that's it.
</details>

**Martin Kleppmann**: 是的。但如果你想在多个提供商上运行你的系统，甚至是在点对点的环境中，那么可能会发生这样的情况：一个用户的编辑权限被撤销了，而与此同时，该用户对刚刚更改了权限的文档进行了编辑。现在，一些设备可能先看到对文档的编辑，然后再看到撤销操作，所以它们会接受对文档的编辑。而另一个设备可能以相反的顺序看到，它们可能先看到撤销操作，然后再看到对文档的编辑，它们会丢弃对文档的编辑，因为它们认为这是未经授权的。现在，这些设备之间就变得不一致了，永久不一致。所以这意味着，如果我们真的想确保一致性，即使对于这个相当基本的设置，我们现在也必须想办法解决一个编辑与做出该编辑的用户权限被撤销同时发生的情况。在没有单一服务器可以做出决策的去中心化环境中解决这个问题，意味着……在中心化环境中，你知道，你只有一个服务器，它决定是文档编辑先来还是撤销先来，然后由那个服务器做出决定。但如果你有多个服务器，它们可能会做出不同的决定。所以你可以有一个共识协议，但共识协议很麻烦，因为它需要一些法定票数，并且要求节点在线。所以我们一直试图在不使用共识的情况下完成整件事。同时，还要保持高可用性，保持用户离线工作的能力，保持在没有任何服务器的情况下进行点对点同步的能力。例如，这使得工程挑战变得困难得多，但它是可以解决的。我们正在为 **Automerge**（我参与的 CRDT 库）接近解决它。但这比在中心化的情况下要复杂得多。但这是一个很好的例子，说明了从摆脱中心化服务的愿望中，如何产生了有趣的工程挑战。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah. But if you want to run your system over multiple providers or even in a peer-to-peer setting then well what could happen is that uh a user gets their edit permissions revoked and concurrently that user makes an edit to the document uh whose permissions have just changed and now some devices may see the edit to the document first and the revocation second and so they would accept the edit to the document and another device may see it the other way around. They may see the revocation first and then the edit to the document second and they'll drop the edit to the document because they think it's not authorized. And now those devices have become inconsistent with each other permanently inconsistent. So that means if we actually want to ensure consistency even for this fairly basic setup we now have to somehow figure out how to resolve this situation of an edit that is concurrent with the revocation of the user who made that edit. solving that problem then mean in in a decentralized setting where we don't have just a single server that can make that decision in a centralized setting you know you just have one server it decides did the edit to the document come first or did the revocation come first and that one decide server makes that decision but if you have multiple servers they might make different decisions so then you could have a consensus protocol but then consensus is messy because it requires like some quorum votes and requires nodes to be online um and so we've been trying to do the whole thing without doing consensus. But but while um so while preserving high availability, while preserving the ability for user to work offline, preserving the ability to uh synchronize peer-to-peer without any servers, for example, that just makes the engineering challenge a lot harder and it's solvable and we are close to solving it uh for **Automerge**, which is the the CLDT library that that I work on. Um, but it's uh it's just much less straightforward than it is in the in the centralized case. But that's a nice example of where interesting engineering challenges arise from this desire to get away from centralized services.
</details>

**Gergely Orosz**: 我们刚才还在谈论时钟。但一个显而易见的问题是，如果所有设备都有完全同步到微秒的时钟，你就可以用时钟，用时间戳。但正如你在分布式系统中所说，我们不能总是相信时钟是同步的。所以我猜，你一直在研究和写的很多东西，现在又回来了。

<details>
<summary>Original English</summary>
**Gergely Orosz**: And then we were just talking about clocks earlier. But an obvious thing that came to mind is well if if all of them had the same clock exactly to the microscond, you could just use a clock, you could use a time stamp, but as you said in distributed systems, we cannot always trust the the clocks are always synchronized. So I I assume like you just have these a lot of the things that you have been researching and writing about are just coming back to
</details>

**Martin Kleppmann**: 当然。在这个特定的场景中，比如一个用户的编辑权限被撤销，如果一个被撤销权限的用户还想破坏一个文档，他们完全可以把他们的编辑日期改到更早，给它一个更早的时间戳。所以在这里依赖时钟是完全没用的，因为人们可以伪造时钟的时间戳，从而可能破坏访问控制机制。所以在这种系统中，当操作来自最终用户设备时，我们还必须担心可能存在的恶意生成的操作。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Absolutely. And in this particular setting of like a user getting their edit permissions revoked if a revoked user still wants to say vandalize a document they can just backdate their edit give it an earlier time stamp. So relying on clocks is absolutely useless here because people can forge the time stamps from those clocks and thereby then potentially undermine the access control mechanism. So in this kind of system, we have to worry about potentially maliciously uh generated uh actions as well when the actions come from end user devices.
</details>

**Gergely Orosz**: 这太迷人了，因为在我看来，你正在解决一个比一些初创公司更难，甚至可能更难的工程挑战。因为初创公司会走捷径。他们会接受一个约束，在这种情况下是一个中心化的服务器，这在商业上和收入上都说得通。但因为你不这么做，你现在需要为一个更难的问题寻找解决方案。如果你解决了这个更难的问题，你就可以提供一个能推动整个行业前进的构建模块。为企业、个人或机构提供一个选择，不仅仅是使用中心化的，而是使用这种去中心化的本地优先方法，然后当然可以权衡利弊并决定哪个更有意义。

<details>
<summary>Original English</summary>
**Gergely Orosz**: This is fascinating because it feels to me that you're solving a hard or maybe even harder engineering challenge than some startups would do because the startups would go the easy route. They would take on a constraint in this case a centralized server which makes business sense, makes revenue sense. But because you are not doing this, you now need to look for a solution for a harder problem. And if you solve this harder problem, you can give a building block that can just move the industry forward. Just give a an option for either a business or an individual or an institution to you know like have an option not just to use centralized but use this decentralized local first approach and then of course reason about the trade-off and decide whichever makes sense.
</details>

**Martin Kleppmann**: 没错。这就是我所说的长期思考。这是一个例子，因为这是研究，我们可以采取这种理想主义的、有原则的立场。我说，是的，我们要解决这个更难的工程问题，因为我们认为去中心化是一个有价值的特性。我们非常清楚，大多数初创公司不会去解决这个问题，因为他们只会选择简单务实的方式，这对初创公司来说是正确的选择。但我们有一套不同的激励机制，我们可以投入时间去尝试解决那些难题。正如你所说，如果我们能解决它们，那么它就为任何使用这项技术的人创造了更多的选择。如果他们愿意，他们可以选择使用这种去中心化技术。当然，它仍然存在权衡，但至少如果他们不必从头开始发明，那么对于那些想用的人来说，采用这种去中心化技术就会容易得多。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Exactly. And that's what I mean with this long-term thinking. This is an example of it where because it's research we can afford to take this idealistic principled stance. I said yes we're going to solve this harder engineering problem because we think decentralization is a valuable feature and we know perfectly well that most startups are not going to solve this problem because they will just do the easy pragmatic thing which is the right thing for startups to do. Um, but we have a different set of incentives and we can afford to put in the time to try and solve those hard problems. And as you said, if we can solve them, then it creates more optionality for anyone, any users of this technology, they can if they want to choose to use this decentralized tech. And there's still trade-offs around it, but at least if they're not having to invent it from scratch, it'll be a lot easier to adopt this kind of uh decentralized tech for for those who want to use it.
</details>

**Gergely Orosz**: 在学术界，你也在教书。你教什么课程？

<details>
<summary>Original English</summary>
**Gergely Orosz**: So in inside academia you're also teaching. Uh what courses do you teach?
</details>

**Martin Kleppmann**: 目前我为本科生开设了一门并发与分布式系统课程，为硕士生开设了一门密码学协议工程课程。此外，今年我还开设了一门关于安全的研讨会课程，并教授本科生的操作系统课程。今年我的教学任务相当繁重。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: At the moment I have a concurrent and distributed systems course for the undergraduates and a cryptographic protocol engineering course for the master students. And then additionally this year I have a uh a seminar course on security and a uh and teaching also the undergraduate operating systems course. I've got quite a lot of teaching this year.
</details>

**Gergely Orosz**: 分布式系统课程在 YouTube 上有。你能总结一下，学习这门课程的人们会学到什么吗？这门课是免费的，感谢你和大学提供这个资源。他们在这门课中会学到什么？

<details>
<summary>Original English</summary>
**Gergely Orosz**: the distributed systems course, it's available on on YouTube. Can you summarize what people who would go through this course which again is freely available? Thank you for you and the university for making it available. What what what would they learn throughout those courses?
</details>

**Martin Kleppmann**: 是的。那门分布式系统课程比书中的内容更理论化一些。它更侧重于算法，以及我们如何说服自己，在分布式系统的假设下（比如节点可能崩溃、通信可能不可靠、时钟可能不准等等），这些算法的行为是正确的。所以这门课并不长，只有八节课的内容。但它在算法方面的细节比书本深入得多。例如，其中一节课完整地讲解了 Raft 共识算法，这个算法相当复杂。但我真的很想向学生们展示它究竟是如何工作的，因为它非常巧妙地阐释了分布式系统的挑战，以及我们需要采取的各种措施来处理可能发生的各种边缘情况和故障，并表明这些问题是可以克服的。这并不容易，算法非常微妙，也很容易出 bug，但确实有可能以一种行之有效的方式解决共识问题。所以这正是我希望通过这门课程传达的信息。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. So that distributed systems course, it's a bit more theoretical than what is in the book. So it's more focused on algorithms and sort of the how we convince ourselves that the algorithms behave correctly under the assumptions of distributed systems that we talked about of like nodes may crash, communication might be unreliable, uh clocks might be wrong, etc. So that's really it. It's it's not a very long course. It's just uh eight lectures worth of of material. But it's uh it goes into substantially more detail on the algorithms than the book. So for example, one of the lectures goes through the entire raft consensus algorithm which is pretty complex. Um but I really wanted to show the students exactly how it works because it's just such a nice illustration of the challenges of distributed systems and the various measures we need to take in order to handle the various types of edge cases and failures um that can happen and showing that those those problems can be overcome. It's not easy and the algorithms are very subtle and it's very easy to have bugs in them but it is possible to solve consensus in a in a way that works pretty well and uh and so that's really this the sort of message I'm trying to uh get across with this course.
</details>

**Gergely Orosz**: 你提到过，当你和克里斯一起写书时，你带来了很多行业见解和最新动态，而你也带来了你的教学经验和行之有效的方法。

<details>
<summary>Original English</summary>
**Gergely Orosz**: and you mentioned that when you're when you're writing the book together with Chris you brought a lot industry insight and being up to date and you brought your experience of of teaching and and what works
</details>

**Martin Kleppmann**: 我不认为我有什么特别独特的教学风格，只是在讲座中，我会讲解幻灯片。我喜欢在讲座期间手写注释幻灯片，在 iPad 上画画，让它更有互动性一些。但除此之外，它还是相当理论化的。这部分是剑桥大学体系的特点，它倾向于理论和纸笔课程，而不是实践性的实现课程。我认为当然可以开设一门关于这个的实践课程，我未来也可能会加入更多实践练习，但目前它主要是一门理论性的纸笔课程。这没问题。我教的密码学课程就更偏向动手实践了。那门课是关于让学生们从零开始实现一些椭圆曲线之类的东西。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I don't think I have a particularly like unique teaching style just uh in lectures I will go through slides. I I like to annotate the slides by hand uh during the lectures. I've just draw draw on an iPad to make it a little bit more interactive. But um other than that, it it is fairly theoretical. That's partly the way the Cambridge system works. It kind of favors theoretical and pen and paper courses over say implementation practical courses. I think it it would be possible certainly to do a practical course on this and I may incorporate a bit more practical exercise in the future but right now it's mostly a theoretical pen and paper course when that is fine. Uh the cryptography course that I do is that's much more uh hands-on. So that's about actually getting the students to like implement some elliptic curves from scratch for example.
</details>

### AI 对教育的影响
**Gergely Orosz**: 在你从事学术工作的这段时间里——现在已经是一段较长的时间了——你看到计算机科学教育发生了怎样的变化？你认为未来，尤其是在我们看到人工智能成为工业界乃至世界的一部分时，它可能会如何进一步改变？

<details>
<summary>Original English</summary>
**Gergely Orosz**: And how have you seen it in your time in in academia which has been it's now a longer time period. How have you seen computer science education changing? How do you think it might change further in in the future especially as we're seeing AI u be part of industry and probably the world as well?
</details>

**Martin Kleppmann**: 是的。我的意思是，在人工智能大爆发之前，计算机科学教学的变化速度其实非常慢。这部分可能和剑桥有关，你知道，剑桥有 800 多年历史了，每个人都用更长远的时间尺度来思考。人们不倾向于追逐最新的潮流，而是试图专注于基础，以及那些在 1930 年代就已经发展起来并且至今仍然正确的计算机科学基本思想。比如 lambda 演算之类的东西。所以我们相当注重那些基础，而不是追逐最新的时髦事物。话虽如此，人工智能已经彻底改变了我们评估课程作业的方式，因为现在我们当然可以尝试禁止人工智能，但实际上不可能强制执行这样的禁令。而且，这也有点适得其反，因为我们确实希望学生接触新技术，并弄清楚如何为自己有效地使用它们。但我们希望以一种支持他们学习而不是破坏他们学习的方式来做到这一点。那么，我们如何让学生以一种负责任的、成熟的方式使用人工智能呢？我们不能完全依赖学生自己足够成熟，知道什么是对人工智能的有益使用，什么是破坏他们学习的人工智能使用方式，因为他们中的一些人相当成熟，能够自己决定，但许多人不是。所以我们需要为他们提供一些指导。而且我们需要确保，当我们有评估作业时，它是公平的，并且被学生认为是公平的。如果学生觉得他们的一些同学不费吹灰之力就拿到了高分，那就会破坏对整个系统的信任。所以我们必须非常小心地处理这个问题。老实说，我们还没有很好的答案。所以我们现在，例如，在第一学年的一开始就为新生举办了一个训练营，向他们介绍基本的软件工程技能，比如版本控制、单元测试、生成式人工智能，以及每个人都应该熟悉的基本知识。然后希望是，他们会在整个学位期间使用这些，以提高他们所做的工作。但具体如何处理评估之类的事情，我们仍在摸索中。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, I mean prior to AI explosion happening actually rate of change is very slow in in computer science teaching. Partly that might be Cambridge, you know, Cambridge is over 800 years old like everyone thinks on longer time scales. People don't tend to rush into the latest fad and instead try to focus on the fundamentals and the ideas that a lot of the fundamentals of computer science were developed in the 1930s already and are still true today. and you know lambda calculus and those types of things for example and so we have quite a bit of a focus on those sort of fundamentals rather than chasing the latest uh fashionable thing. That said, AI has totally changed the way we can assess coursework, for example, because of course now we we can try banning AI, but it's impossible to actually enforce such a ban. And also, it's kind of counterproductive because we do want students to engage with new technologies and figure out how to use them productively for themselves. But we want to somehow do that in a way that supports their own learning and doesn't undermine it. So, how do we get the students to use AI in in a responsible way, in a way that's mature? And we can't necessarily rely on the students being mature enough to know for themselves what is a helpful use of AI and what is a form of use of AI that undermines their own learning because some of them are quite mature and able to decide that for themselves, but many are not and so we need to provide some guardrails for them. Um and we do need to make sure that when we have assessed work for example it's fair and it's perceived as fair by the students and if the students feel that some of their uh co- students are getting really good marks without doing any work that undermines the trust in the entire system and so we have to be very careful with how we approach this and to be honest we don't really have good answers yet. So we do uh now for example have a boot camp right at the start of the first year for the new students to expose them to basic software engineering skills which is like this is version control, this is unit testing, this is generative AI and the sort of basics that really everyone should be familiar with and then the hope is that they will use that throughout their degree in order to just improve the work that they do. But how exactly we handle things for assessment for example we're we're still in the process of figuring out.
</details>

**Gergely Orosz**: 听起来，变革的步伐在工业界会很快，在学术界也可能会采纳，我们会看到接下来会发生什么。

<details>
<summary>Original English</summary>
**Gergely Orosz**: So it it sounds like the the the pace of of change is going to be fast in the industry and also in academia we'll probably adopt it and we'll see you know like what what comes after.
</details>

**Martin Kleppmann**: 是的。但有一个区别，那就是期望的结果不同。我认为在工业界，期望的结果通常是一个能用的产品。而在学术界，学生们实际产出的东西，比如他们写的论文，其实并不是重点。我们让学生写论文，不是因为我们喜欢读他们精彩的论文。我们让他们写论文，是因为我们希望他们经历一个能帮助他们学习的思考过程。而那个思考过程和学习本身才是这里真正期望的结果。所以这意味着我们确实需要用稍微不同的方式来处理。因为在工业界，你知道，如果你能用人工智能更快地完成一项工作，并且得到相同的结果，那绝对应该去做，因为那才是期望的结果。而在教育领域，我们确实需要思考如何确保学习成果和思考过程仍然得以保留，以便学生能在智力上受益。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes. There's a difference though which is in the desired outcomes. I think with industry generally the desired outcome is like a working product for example. In academia the actual artifacts that the students produce like an essay that the students write that's not really the point. We don't ask the students to write essays because we love reading their amazing essays. We ask them to write essays because we want them to go through a thought process which helps them learn something. And it's that thought process and that learning which is really the the desired outcome here. And so that means that we do have to approach it a little differently because in generally in in industry, you know, if you can use AI to get a job done faster and you get to the an equivalent result, do it absolutely because yes, that that is the desired outcome. uh whereas in education we do have to think about how we ensure that the the learning outcomes and the thought processes are still preserved such that the the students benefit intellectually.
</details>

**Gergely Orosz**: 这非常切题，特别是 Anthropic 最近有一项研究，他们观察了初级工程师，其中一组使用了人工智能，另一组没有。他们发现，不出所料，正如你所解释的，使用人工智能的那组几乎没有学到什么，而没有使用的那组实际上学到了东西。

<details>
<summary>Original English</summary>
**Gergely Orosz**: It's very relevant especially entropic had a recent study where they looked at junior engineers they one of them used one group used AI the other one did not and they found unsurprisingly from what what you also explained that the group who used AI they had little to no learning whereas the group that did not they actually learned it.
</details>

**Martin Kleppmann**: 是的，我也看到了那项研究。我想，那项研究的详细方法我们或许可以商榷一下，但我认为其基本原理似乎是正确的。是的，有时候为了学习某样东西，你就是得和它斗争一番，但又不能斗争得太过火。所以如果人们被某个技术细节卡住了，他们可以用人工智能来解困，然后就能真正专注于主要的学习目标，那么我认为使用这类工具是好的。但如果重点是真正地去理解一些困难的想法，并在自己的头脑中把它们想通，那么我们仍然需要找到方法来确保学生们在这样做。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yes, I saw that study as well. I think the meth detailed methods of that study we might be able to quibble with a bit but I think the the general principle seems true that yes so sometimes in order to learn something you just have to struggle with it a bit not struggle too much so if people are stuck on some technicality and they can use AI to get unblocked and then be able to focus really on the the main learning outcome then I think uh it's good to use these types of tools but if if the point is to actually like grapple with some difficult ideas and think them through their own minds, then we need to still find ways to make sure the students are doing that.
</details>

### 学术界与工业界的相互学习
**Gergely Orosz**: 你同时在工业界和学术界工作。你认为工业界可以从学术界学到什么，学术界又可以从工业界学到什么？

<details>
<summary>Original English</summary>
**Gergely Orosz**: You work both in industry and academia. What what do you think industry could learn from academia and academia can learn from industry?
</details>

**Martin Kleppmann**: 这两者真的可以更紧密地结合在一起，因为它们常常互相看不起。工业界的人会说：“啊，那是理论，是学术，跟现实世界没关系。”他们真的错失了良机，因为实际上研究中有很多有趣的见解与现实世界非常相关，但它们不一定能跨越那道鸿沟。反过来，学术界的人会说：“哦，这工业界的东西，你知道，只是工程。”他们并没有真正做任何有趣的思考，只是在写一些例行公事的东西。我认为我的目标之一就是尝试在两个方向上建立更好的尊重，通过将研究中有趣的见解带入工业实践，也通过让现实世界中出现的问题来为我们的研究提供信息，这样就能更好地将这两者联系起来。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: The two really could be closer together because often they regard each other with uh sort of disrespect really like the the industry people will say, "Ah, that's theoretical, that's academic, it's got nothing to do with the real world." and they're really missing a trick there because actually there's a lot of interesting insights from research that are very relevant to the real world. Um but they're not necessarily making their way across that chasm. In the other direction, the academics will say, "Oh, this industry stuff, you know, that's just engineering." They're not actually doing any interesting thinking. It's just like writing routine stuff. I think I see it as one of my goals to try and build better respect across both in both directions by bringing interesting insights from research into industrial practice but also by informing our research uh by the problems that uh arise in in real world and so that way like joining those two things up a bit better.
</details>

**Gergely Orosz**: 你目前正在研究哪些课题，哪些让你感到兴奋？

<details>
<summary>Original English</summary>
**Gergely Orosz**: What are your current research topics that you're working on ones that you're excited about?
</details>

**Martin Kleppmann**: 我目前主要在两个领域工作。一个是本地优先软件。这个想法是，我们想要像 Google Docs、Figma 等那样的协作软件，但要以一种能更好地保护用户数据的方式，减少对单一云提供商的依赖，因为他们可以把你锁在文件之外，因此这种方式更具弹性，能给予用户更大的自主权和对自己数据的控制权。这是我过去十年左右一直在从事的领域，通过混合开源工作、算法开发和形式化验证等方式。我现在还试图在一个完全不同的主题上建立一个全新的研究领域，那就是利用密码学来证明关于物理世界的事情。我对与可持续性相关的事情特别感兴趣。例如，如果你想验证制造某个特定产品所涉及的碳排放量是 X，并且你想确定这个数字是正确的，因为也许你想把排放量作为你购买决策的一部分，并选择排放量较低的产品。要使这有意义，排放量数字必须是正确的。不幸的是，目前这些数字通常不正确，因为动机是撒谎和欺骗，以及使用创造性的会计技巧，所有这些都是为了“洗绿”。或者一个相关的事情正在欧盟发生，欧盟正在引入新的法规，以防止热带雨林的砍伐。所以，例如，进口到欧盟的咖啡、可可、棕榈油等，进口商需要证明它究竟来自哪块土地，然后对照卫星图像检查那块土地最近没有被砍伐过。所以我一直在研究使用密码学作为一种工具来证明这些实体产品供应链的事情，但又不泄露商业敏感信息。例如，一家公司不会想透露它的供应商是谁，以及它从哪个供应商那里购买了哪个成分，因为那可能会泄露它使用的秘密配方。所以这里的希望是，密码学可以让我们证明，例如，供应链上的会计核算是正确的，但又不必公开任何关于供应商或其他客户的敏感数据。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: I have two main areas I'm working on at the moment. Uh one is local first software. So that's this idea that we want collaborative software like Google Docs, like Figma, etc., but in a way that uh gives better protection to users data that's less dependent on a single cloud provider who can lock you out of your files and that's therefore more resilient. Uh gives users greater agency and greater autonomy over their own data. U so that's an area that I've been working on for the last 10 years or so through a mixture of open source work and algorithm development and formal verification and so on. I'm now also trying to set up a brand new research area in a totally different topic um which is on using cryptography to prove things about the physical world. So I'm interested there in especially sustainability related things. So for example, if you want to verify that the carbon emissions involved in manufacturing a particular product were X and you want to be sure that that number is correct because maybe you want to include emissions as part of your purchasing decision and choose the product with the lower emissions. For that to be meaningful, the emissions number has to be correct. And unfortunately at the moment the numbers are generally not correct because the incentives are to lie and cheat and to use creative accounting techniques all as a way of like greenwashing basically or a related thing is happening in the EU for example which is bringing in new regulations on preventing deforestation of tropical rainforests. So that's for example coffee, cocoa, palm oil etc imported into the EU. the importer needs to prove exactly which plot of land it actually came from and then check against satellite imagery that that was not recently deforested. And so I've been looking into using cryptography as a tool of proving things about the supply chains of these physical products but without revealing commercially sensitive information. For example, a a company will not want to reveal who its suppliers were and which ingredient to its process it purchased from which supplier, for example, because that might reveal something about its secret recipe that it uses. And so the hope here is that cryptography can allow us to prove that for example the the accounting has been done correctly across supply chains but without having to reveal publicly any of this sensitive data about suppliers or other customers.
</details>

**Gergely Orosz**: 从你的角度来看，你对人工智能对学术界（不仅仅是学生学习，还有更广泛的层面）以及工业界（通过你的行业联系）的影响有何看法？

<details>
<summary>Original English</summary>
**Gergely Orosz**: What is your view from your vantage point on the impact that AI is having on academia not not just for for students studying beyond that and also industry with your industry contacts?
</details>

**Martin Kleppmann**: 是的，我的意思是，我并没有那么深入地研究人工智能。我更多的是通过我的合作者们看到它，他们在软件开发方面，尤其是在使用人工智能工具方面，做得非常好。我个人现在写的代码很少，所以我并没有太多需要或机会亲自使用人工智能代理。在写散文，比如写书的时候，我更喜欢用老式的方法，就是每个字都亲手写。所以我没有让 AI 接触书的文本。我不知道这是否是正确的决定。这并不是原则问题，我并不认为这么做是错的。更多的是，对我自己来说，写作的过程是我弄清楚事情的方式，而弄清楚事情正是我在这里的目标。所以我试图在自己的头脑中弄清楚，为此我只能自己写。似乎没有其他办法。但使用人工智能作为一种获取想法反馈或探索一个想法是否经得起推敲的方式，似乎是一种非常高效的技术使用方式，这在工业界和学术界都适用。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, I mean I'm not not that deeply into um the AI things really. I'm seeing it more through my collaborators who are making very good use of of AI tools uh for for software development especially. I personally write very little code these days and so I haven't had that much need or occasion to actually use AI agents myself personally. When when writing pros like working on the book for example, I prefer to still do that the oldfashioned way of just write every word by hand. So I I haven't let AI anywhere near the text of the book for example. And I don't know if that's that's the right decision. It's not really a a principle thing that I I think it would be wrong to do so. It's more that for myself the process of writing is the way how I figure things out and figuring things out is really my goal here. So I'm I'm trying to figure it out in my own head and for that I just have to write it myself. Does there doesn't seem to be any way around it. But using AI as a way of like getting feedback on ideas or exploring like whether an idea really holds up to scrutiny or things like that seems like a very productive use of the technology and that applies for for both industry and academia I would say.
</details>

**Gergely Orosz**: 那么，作为结束语，对于一个正在学习并且考虑进入工业界或学术界的学生或年轻专业人士，你看到哪些人在其中一个或另一个领域蓬勃发展？

<details>
<summary>Original English</summary>
**Gergely Orosz**: So as as closing for a student or a young professional who is is still studying and considering the route into either industry or academia, what have you seen uh who thrives in one or the other?
</details>

**Martin Kleppmann**: 是的，我的感觉是它们并非完全相互排斥，或者说，我合作过的一些最好的博士生，实际上都有几年的行业经验。他们可能读了本科，也许读了硕士，然后在行业里待了几年，做真正的软件工程，了解现实世界，然后可能在某个时候觉得无聊了，想，哦，实际上，我想做一些更理想主义的事情，或者有更多自由来选择自己的研究课题，然后开始对攻读博士学位感兴趣。我发现这是一条相当健康的道路。确实有人从本科和硕士直接攻读博士学位，但有时这些人可能只是缺乏一点广阔的视野。所以我认为，即使他们想留在研究领域，见过一点现实世界的工程实践实际上对人们非常有帮助。但反过来，我认为也可以很好地运作，因为在学术界的研究中，我们能比工业界的人更仔细地思考问题。我觉得工业界的人常常有“短路思维”，可能不会从第一性原理出发把问题想透，而只是“哦，我在一个会议演讲上听过这个。我就用这个了。” 而学术界能教的，是这种细致入微、批判性的思维，去真正地权衡利弊，去真正地证明为什么某件事是正确的。所以我认为，如果人们能在工业界和学术界之间来回穿梭，而不是把它们看作是两个完全相互排斥的职业道路，而是能有一些转换，那真的很好。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Yeah, my feeling is they're not really that mutually exclusive or rather some of the best PhD students uh I've worked with for example actually have a few years of industry experience. So they might have done an undergraduate maybe done a masters then spent a few years in industry developing like actual doing real software engineering learning about the real world uh and then maybe at some point got bored and thought oh actually you know I want to work on maybe more idealistic things or have more freedom to choose uh their own research topics and then start getting interested in doing a PhD and that I find is is quite a healthy route. You do get people who go, you know, straight from their undergraduate degree and masters into doing a PhD, but sometimes those people can just lack a bit of the breadth of perspective. And so I think having seen a bit of just real world engineering is is actually really helpful for people even if they then want to stay in research. But in the opposite direction, I think it can work very well too because in in research research in academia, we just get to think things through a lot more carefully than people often do in industry. Often people in industry, I feel like sort of have short circuit reasoning, like don't maybe don't quite reason something through from first principles, but just like uh oh, I heard this from a conference talk. I'm just going to go with that. And oh yeah, what what academia can teach is this sort of uh nuanced and and critical thinking um to really reason through trade-offs, for example, and to really like justify why something is true. And so I think it's really good actually if people can weave in and out of industry and academia a bit and not regard it as like two totally mutually exclusive career paths, but actually have a bit of switching between the two.
</details>

**Gergely Orosz**: 嗯，Martin，非常感谢你。我原以为我们会更多地谈论你的书，我们也确实谈了，但我对你和其他人正在做的所有重要而有趣的学术工作有了新的好奇和敬意。所以非常感谢你。

<details>
<summary>Original English</summary>
**Gergely Orosz**: Well, Martin, thank you very much. Uh I expected us to talk a lot more about your book which we did but I I have a newfound curiosity and and respect for all the important and interesting academic work that you and everyone else is doing. So thank you so much for this.
</details>

**Martin Kleppmann**: 谢谢你的精彩采访。这真的很有趣。

<details>
<summary>Original English</summary>
**Martin Kleppmann**: Thank you for the great interview. This was really interesting.
</details>

### 结语
**Gergely Orosz**: 我希望你喜欢这次与 Martin Kleppmann 的难得对话。我发现了解到这本书的第一版假设你有带本地磁盘的机器，这很有趣。但实际上，今天大多数工程师已经不再这样构建系统了。像 S3 这样的云原生原生服务改变了你构建系统的方式，这就是为什么这本书需要更新。我也很欣赏 Martin 关于工程师在使用托管服务时是否仍需了解系统内部原理的看法。如果你在这些服务之上构建业务逻辑，你可能不需要知道每个细节，但能够深入了解可能会变得有用，尤其是在你需要调试系统时。在我们的谈话结束时，我对 Martin 正在做的学术研究产生了深深的敬意。本地优先软件的工作，去中心化系统中的访问控制问题，使用密码学验证供应链排放。这些都是很少有初创公司会去挑战的难题。很高兴能了解到学术界如何能很好地从事具有长期焦点的工作。请务必查看下面的节目说明，了解相关的《Pragmatic Engineer》深度剖析。如果你喜欢这个播客，请务必在你最喜欢的播客平台和 YouTube 上订阅。如果你也为节目留下评分，我将特别感谢。谢谢，我们下一集再见。

<details>
<summary>Original English</summary>
**Gergely Orosz**: I hope you enjoyed this rare conversation with Martin Clubman. I found it interesting to learn that the first edition of the book assumed that you have machines with local discs. But actually today this is not how most engineers build systems anymore. cloudnative primitives like S3 change how you build systems and this is why this book just needed a refresh. I also appreciated Martin's take on whether engineers still need to undertest system internals when they're using managed services. If you're building business logic on top of these services, you probably don't need to know every detail, but it can become useful to be able to look deeper, especially when you need to debug your system. By the end of our conversation, I gained a lot of appreciation for the academic research that Martin is doing. the local first software work, the access control problem in decentralized systems, using cryptography to verify supply chain emissions. A lot of these are hard engineuring problems that few startups would take on. It was nice to understand how academia is in a good position to do work that has a long-term focus. Do check out the show notes below for related to primatic engineer deep dives. If you've enjoyed this podcast, please do subscribe on your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show. Thanks and see you in the next one.
</details>

### 访谈开篇与核心观点

**主持人**: 我是否应该考虑**多可用区**（Multi-zone）、**多地域**（Multi-region）甚至**多云**（Multi-cloud）架构？你愿意承担多少可用性风险，来换取计算开销、以及设计和运行系统的人力开销？**MapReduce** 已经过时了，现在没人用了。但在其他领域，我们增加了覆盖范围，比如支持 AI 的系统，例如**向量索引**（Vector indexes）。作为软件工程师，如果依赖更高层次的抽象，不再考虑底层细节，是否会面临失去理解底层动力的问题？如果你正在构建更高层的业务逻辑，实际上我认为这没问题。**大语言模型**（LLMs）增加了对**形式化证明**的需求，因为我们正在通过“氛围编程”（vibe coding）搞出一堆东西。这就是我认为形式化验证在未来会变得更重要的原因之一。

<details>
<summary>Original English</summary>
**Host**: Should I consider multiszone, multi-reion or even a multi-cloud setup? How much availability risk are you willing to take on versus the computational overheads, but also the human overheads actually designing and operating the system? MapReduce is dead. Nobody uses it anymore. But other areas where we've increased the coverage are systems in support of AI like vector indexes. Is there any risk as a software engineer that you're no longer incentivized to understand the underlying layer? If you rely on a higher level abstraction, you're no longer thinking about the lower level details. If you're building higher level business logic, actually, I think it's just fine. LLMs increase the need for these formal proofs because we're vibe coding a bunch of stuff. The reason I think that formal verification could become more important in the future. One is that
</details>

**主持人**: 《**数据密集型应用系统设计**》（Designing Data-Intensive Applications）一直是任何构建大型后端系统的人必读的“圣经”。在这本书出版 9 年后，**第二版**终于面世了。**马丁·克莱普曼**（Martin Kleppmann）是这本具有代际影响力的著作的作者。我与他坐下来进行了交流，今天我们将涵盖：在 **LinkedIn** 开发 **Kafka** 的经历如何直接塑造了书的第一版构思；第二版有哪些新内容；以及为什么像 MapReduce 这样的内容在更新版中被移除。我们还将讨论**形式化方法**、**本地优先软件**（Local-first software）、**去中心化访问**等等。如果你关心大型系统如何运作、未来的走向，以及那些经久不变的基本原理，那么这一集就是为你准备的。

<details>
<summary>Original English</summary>
**Host**: Designing data intensive applications has been the go-to book for anyone building large backend systems. 9 years after publishing this book, the second edition is here. Martin Kleppmann is the author of this generational book. I sat down with him and today we cover how working on Kafka at LinkedIn directly shaped ideas that became the first edition of the book, what's new in the second edition, and why things like MapReduce got removed from this updated version. Formal methods, local first software, decentralized access, and many more. If you care about how large systems work, where they're heading, and what the fundamentals are that don't change, this episode is for you.
</details>

**主持人**: 本集节目由 **Statsig** 呈献，它是集功能开关、数据分析、实验等于一体的统一平台。同时由 **Sonar** 赞助。Sonar（SonarQube 的开发者）深知，代码质量不仅仅是避免语法错误，更关乎通过保护系统的结构完整性来实现长期的**可维护性**。随着智能体大规模生成代码，它们往往会忽略系统的结构完整性，从而导致代码纠缠、重复和其他维护性问题，使模块化设计变成“大泥球”，难以扩展。SonarQube 的**架构管理**非常有用，它将架构治理从静态 Wiki 移入自动化工作流，让你实时可视化当前架构、定义边界并管理架构问题。无论是人类还是 AI 智能体在编写代码，Sonar 都能作为结构退化的“断路器”，确保每次提交都遵循系统蓝图。

<details>
<summary>Original English</summary>
**Host**: This episode is presented by Statsig, the Unifi platform for flags, analytics, experiments, and more. This episode is brought to you by Sonar. Sonar, the makers of SonarQube, understands that code quality is about more than just avoiding syntax errors. It's about long-term maintainability by protecting the structural integrity of the system. As agents generate code at massive scale, they often ignore your system structural integrity. This creates tangles, duplicated code, and other maintainability issues. These issues turn a module design into a big ball of mud, making it increasingly difficult to extend. But here's something that's really helpful. SonarQube's architecture management. It moves architectural governance out of static wikis and into your automated workflow. It allows you to visualize your current architecture, define architectural boundaries, and manage architectural issues in real time. Whether it's a human or an AI agent at the keyboard, Sonar acts as a circuit breaker for structural decay. It ensures every commit respects the systems blueprint protecting the long-term health of your most complex applications. Head to sonarsource.com/pragmatic to find out more.
</details>

### 早期创业与技术积累

**主持人**: 那么，马丁，欢迎来到播客。

<details>
<summary>Original English</summary>
**Host**: So Martin, welcome to the podcast.
</details>

**马丁**: 嗨 Ger，很高兴来到这里。

<details>
<summary>Original English</summary>
**Martin**: Hi Ger, it's great to be here.
</details>

**主持人**: 能请到你真是太棒了。我想对许多软件工程师来说，你不需要介绍，包括我自己在内。你写了这本标志性的书，它在我书架上可能已经放了 10 年了，几乎是在它出版后不久我就买了。在我们深入讨论这本书之前，你是如何进入技术领域的？

<details>
<summary>Original English</summary>
**Host**: It's amazing to have you here. I don't think you need introduction to many software engineers, including myself. You're the author of this iconic book that I've had on my bookshelf for probably about 10 years, not much longer after it came out. Before we get into this book, which we're going to talk about, how did you get into the technology field?
</details>

**马丁**: 好的。和很多人一样，我本科读的是**计算机科学**。毕业后，我不太确定这辈子该做点什么，但我当时觉得，创办一家**初创公司**似乎是个有趣的尝试。于是，我在完全不知道该具体做什么的情况下就开始创业了，最初的一段时间都在到处寻找有趣的方向。第一家公司不太成功，但通过它我认识了其他人，他们后来成了我第二家初创公司的联合创始人。那家公司做得更顺，后来我们把它卖给了 **LinkedIn**。那之后，我开始对讲授这些**分布式系统**的概念产生兴趣，这就是我开始写书的契机。在写书的过程中，我也从工业界转回了学术界。

<details>
<summary>Original English</summary>
**Martin**: Yes. Well, I did a undergraduate computer science like like many others. And then after that, I wasn't quite sure what to do with my life, but I thought, well, is like starting a startup seems like an interesting thing to try. So, I started a startup having no clue what I was going to actually do and then spent the first while searching around for things that might be interesting. it the first startup didn't work out that well but through that I met some others who then became my co-founders for the second startup which worked better and uh we sold that one to LinkedIn and then after that I started being interested in like teaching these distributed systems concepts so that's when I got into writing the book and then during the writing of the book I also switched over from industry back to academia
</details>

**主持人**: 我们能聊聊你的第一家和第二家初创公司吗？

<details>
<summary>Original English</summary>
**Host**: can we talk a little bit about your first and second startup
</details>

**马丁**: 好的，第一家叫 **Go Test It**。那是在 2008 年左右，那个年代大家很难让 JavaScript 在不同浏览器上正常运行。**Internet Explorer** 当时仍然占据很大份额，**Chrome** 才刚问世。所有浏览器彼此都不兼容。所以，Go Test It 是一个网站的**跨浏览器自动化测试服务**，基于 **Selenium** 这个至今仍然存在的开源项目。核心想法是，你可以编写测试脚本，模拟用户点击网站的各种交互，然后检查行为是否正确。它作为托管服务提供，这样人们就不必自己运行安装了各种操作系统的虚拟机。技术上是可行的，但我发现很难让人们真正采用它。很多做网站的人理论上会说：“噢，这太棒了，我们需要跨浏览器测试”，但实际上，让他们将其集成到工作流中，并养成编写测试脚本的习惯，是非常困难的。所以，那家公司最后没能做起来。

<details>
<summary>Original English</summary>
**Martin**: yeah go test it this was like 2008 or something like that. It was the age where people were having really difficulties getting their JavaScript working cross browser. Internet Explorer was still pretty big at the time. Chrome had just come out. Uh all the browsers were incompatible with each other and so Go Test. It was a cross browser automated testing service for websites was based on Selenium, an open source project that still exists. And the idea is you would write like test scripts that automate the a user clicking through the various uh interactions with a website and then just check that the right behavior happens. And so yeah, it was based on selenium but just as it provided as a hosted service so people wouldn't have to run various VMs with various operating systems themselves. It worked technically but um I found it really hard to actually get adoption for it. A lot of uh people building websites like in theory said oh yeah this is great. we we need to test cross browser and in practice actually it was really difficult to get them to integrate it into their workflow and just get in the habit of using it and investing in writing the test scripts. So, so that ended up not really going anywhere.
</details>

**主持人**: 所以说，那当时并没有形成一个真正的业务，或者没有产生有意义的营收？

<details>
<summary>Original English</summary>
**Host**: So, so like there wasn't like a business to be done or or like revenue to be generated in meaningful sense.
</details>

**马丁**: 是的。不过同一时期至少有一两家其他公司成功建立起了业务，**Sauce Labs** 就是其中一家。但即使对他们来说，业务增长也是相当缓慢的，这不是一个容易做的行当。

<details>
<summary>Original English</summary>
**Martin**: Yeah. Well, there's at least one other maybe two other companies from that same era that did manage to make a business. Sauce Labs is one that that managed to actually succeed. Um, but it even for them it was a pretty slow running business. I think it was not an easy business to be in.
</details>

**主持人**: 至于那家初创公司，你当时是在英国做的吗？是自掏腰包（bootstrapped）还是拿了融资？团队有多大？

<details>
<summary>Original English</summary>
**Host**: And for the startup, were you in in the UK building it? Was it was it bootstrapped? Did you raise some some kind of funding? How big was the team? How can we imagine this?
</details>

**马丁**: 我当时在英国。基本是**自筹资金**，我通过做咨询来筹钱雇人，然后廉价雇了一些朋友来帮忙构建产品。一切都做得非常省钱。我只有极少量的天使投资，大部分是靠自筹。

<details>
<summary>Original English</summary>
**Martin**: I was in the UK at the time. It was mostly bootstrapped. So I did a bunch of consulting in order to fund hiring some people and then hired some like friends uh on the cheap to help contribute to actually building the product. And so it was done all all very cheaply. I had a very small amount of uh of angel money in there but mostly bootstrapped.
</details>

**主持人**: 那么当你决定不再继续这个项目时，下一家初创公司是怎么来的？是 **Rapportive** 对吧？

<details>
<summary>Original English</summary>
**Host**: Mhm. And then when you decided to to not uh go forward with this, how did the next startup come? Uh reportive, right?
</details>

**马丁**: 对，第二家是 Rapportive，进展顺利得多。它的核心是在 **Gmail** 内部整合社交媒体。想法是，如果你收到一封来自陌生人的邮件，我们有一个浏览器扩展插件，它会修改 Gmail 的 Web 界面，在邮件旁边显示一个**社交资料摘要**：包括从 LinkedIn 抓取的头像和职位，从 Twitter 抓取的最新推文，或者 Facebook 帖子等等——只要我们能找到的关于那个人的社交摘要都会放上去。我们是在 2010 年左右开始的，很快就变得非常流行。在此基础上，我们从 **Y Combinator** 拿到了一笔融资，YC 当时还非常年轻。

<details>
<summary>Original English</summary>
**Martin**: Yeah, the second one was reportive. That went a lot better. So, uh, that was putting social media inside Gmail basically. So, the idea was that if you get an email from someone you don't know, we had a little browser extension which manipulated the Gmail web interface so that on the side next to the email, we'd show you a summary social profile with like a profile picture and like a job title pulled from LinkedIn and recent tweets pulled from Twitter and maybe recent Facebook post or things like that. just whatever we could find about that person uh and put that as a as a social summary next to the email. We started in 2010 or something like that. It was then pretty quickly became quite popular. Um and so on the back of that we were then able to raise some money from my combinator which was still fairly young at the time.
</details>

**主持人**: 那确实非常早。你一定是第一批学员之一。

<details>
<summary>Original English</summary>
**Host**: That was very young. That you must have been one of the very early batches.
</details>

**马丁**: 是的，我不记得具体是什么时候开始的，但确实是在早期几年。我想 YC 当时已经建立起了很好的名声，但规模还比较小。

<details>
<summary>Original English</summary>
**Martin**: Yeah, I can't remember exactly when they started but it was um it was certainly in the early years. I think Y Combinator had already built up a quite a good reputation at the time, but it was still fairly small.
</details>

**主持人**: 作为 YC 项目的一部分，你当时必须从英国飞到旧金山去参加那个为期三个月的计划，我没记错吧？

<details>
<summary>Original English</summary>
**Host**: And then as part of Y Combinator, did you have to fly you from from the UK to San Francisco to attend that 10e program if I remember?
</details>

**马丁**: 没错。我们最初是来参加三个月的 YC 项目，但后来我们拿到了美国工作签证，并决定永久定居在**旧金山**。

<details>
<summary>Original English</summary>
**Martin**: Exactly. Yes. So we um initially came for for the 3 months or whatever it was of the Y combinator but then we were able to get US work visas for ourselves and uh set up permanently uh in in San Francisco.
</details>

**主持人**: 从你度过大学时代的第一家初创公司所在的英国，转到旧金山，这种转变感觉如何？

<details>
<summary>Original English</summary>
**Host**: How was that shift from from the UK where you spent going to university your first startup the first part of this to coming to San Francisco?
</details>

**马丁**: 非常令人兴奋，因为感觉就像进入了这一切发生的中心。刚开始我们在湾区一个人都不认识，后来联系到了一两个，他们又介绍更多人给我们。我非常欣赏那里对像我们这样的“局外人”如此开放，只要带着一个想法和早期初创公司过去，我们竟然真的筹到了钱，并在湾区站稳了脚跟。

<details>
<summary>Original English</summary>
**Martin**: It was very exciting because uh you know it felt like you know going going to the the center of where it was all happening really and we at the started out not knowing anybody at all. we knew like one or two people in the entire Bay Area, but we like contacted them and they introduced us to more people and they introduced us to more people. And so we were able to pretty quickly actually build up a a network and that that's something that I I really appreciated that it was actually so open to outsiders like us who could just basically turn up with an idea and an early stage startup and we managed to raise some money and managed to like actually become somewhat established in the in the Bay Area.
</details>

**主持人**: 能跟我说说公司是怎么发展的吗？LinkedIn 的收购邀约是在什么时候出现的？

<details>
<summary>Original English</summary>
**Host**: And can you tell me how the how the company grew and and at what point did the LinkedIn acquisition offer come and and how can we imagine even you were a founder of this company.
</details>

**马丁**: 我们是在 2012 年左右卖掉公司的。当时团队只有五个人，规模依然很小，涉及的金额也不大，但对所有相关人员来说都是一次成功。收购过程本身还算顺利，但像所有此类交易一样，充满了波折，有时候我们觉得会告吹。当时我们几乎快没钱了，也没能成功融到下一轮。所以，摆在面前的只有要么卖掉，要么关门。压力很大，我们甚至不能降低自己的工资，因为那样会违反签证条件。所以在那样的处境下，我们其实缺乏谈判筹码，但我对最终的结果非常满意。

<details>
<summary>Original English</summary>
**Martin**: It was about in 2012 that we sold it. Um and we were five people at the time. So it's all still pretty small. Um not vast amounts of money involved but it it was a success I would say uh for everybody involved. The acquisition process it itself was fine. is like as always with these kinds of transactions, there was like twists and turns and moments where we thought it would all fall apart and then we were almost running out of money and uh hadn't really succeeded in raising another round. So, we kind of had to sell or shut down. So, we were under quite a bit of pressure. We couldn't reduce our own salaries because to do so would have violated the conditions of our visas. Yes. Um so, we were in a slightly stuck situation given our lack of leverage in that situation. And actually I'm pretty happy how it all turned out.
</details>

**主持人**: 很高兴在 10 多年后我们能诚实地聊这个。通常我们看到被 LinkedIn 收购的消息，创始人会说这是梦想成真，但很少听到背后那种紧迫感。所以你是为了求生才卖掉公司的吗？

<details>
<summary>Original English</summary>
**Host**: Yeah, it's nice that you know like for 10 plus years we can talk about this honestly because often times you see an acquisition by LinkedIn and of course you might ask the founders and they would say like this was our either our dream or our goal or we will do so many things together but some things that you don't often hear is well that there was a pressure involved as well. So, did you go into this wanting to sell the company because you saw that things were getting a little either you needed to raise a new round or you sell to someone and then you found LinkedIn to be the the best of or the only or or or the best option to to go into.
</details>

**马丁**: 我们尝试了一些产生营收的方案，但没能奏效。所以我们一直在烧钱，用户增长虽然还可以，但不足以支撑我们去融一个大轮次。所以当时有点陷入困境，卖掉公司似乎是“最不坏”的选择。我对结果很满意，因为 LinkedIn 真的很棒，他们对我们很好，允许我们作为公司内部的一个**独立团队**运作。

<details>
<summary>Original English</summary>
**Martin**: We tried a little bit to see like what revenue generating options we had and hadn't really managed to make that work. So, we were just burning money and uh and our user growth was okay but not really enough to go and raise a big round. Um, so we were like a little bit stuck there and selling the company seemed like the least bad option there in a way. And I'm pretty happy how it turned out because you know LinkedIn was great actually. They they were very good to us. They allowed us to operate as essentially like a independent team within the company.
</details>

**主持人**: 所以你们的团队留在一起了？

<details>
<summary>Original English</summary>
**Host**: So So your team stayed together?
</details>

**马丁**: 留在一起了，继续做我们想做的产品。

<details>
<summary>Original English</summary>
**Martin**: Our team stayed together. We continued working on the product that we wanted to make.
</details>

**主持人**: 噢，你们可以继续做 Rapportive。

<details>
<summary>Original English</summary>
**Host**: Oh, you you got to keep working on reportive.
</details>

**马丁**: 其实 Rapportive 这个 Gmail 扩展插件当时进入了维持模式。我们当时在做一个新产品，后来以 **LinkedIn Intro** 的名字发布。它在当时的反响有点奇怪，发布后不久就被关掉了。背后有个很长的故事，但我依然很感谢 LinkedIn 给了我们自由去尝试和发布这个产品，尽管失败了，但整个过程中他们对我们都很好。后来项目被裁掉，我们的团队也就解散了。但在 LinkedIn 开发这款产品的日子，我们过得很愉快。

<details>
<summary>Original English</summary>
**Martin**: Yes. Well, actually, so report of the Gmail browser extension uh sort of got put on life support, but we were working on a new product at the time, which did eventually get released under the name LinkedIn intro. It kind of got a slightly weird reception at the time and it ended up getting shut down shortly after we released it. this kind of longer background story there, but um I'm still really happy with LinkedIn like how they gave us the freedom to do this and allowed us to launch this product and even though it didn't succeed, you know, they were very good to us throughout that process and then after that got shut down then our team got disbanded. Um but we had a good run within LinkedIn um building this product.
</details>

**主持人**: 你们当时用的是什么技术栈？

<details>
<summary>Original English</summary>
**Host**: What tech stack did you work at the time which what do you use?
</details>

**马丁**: Rapportive 的技术栈其实没什么特别的。基本上是一个 **Rails** 应用配上 **Postgres** 数据库，再加上一些 Redis 之类的东西。其实没什么革命性的。我们本质上是在 Postgres 之上构建了一个**图数据库**。里面有一点点技术趣味，但并不算太离谱。

<details>
<summary>Original English</summary>
**Martin**: The reporter was fairly unexciting. It was a Rails app with a Postgress database basically and some Reddit and some similar things like that mixed in. So actually you know nothing particularly revolutionary. We essentially built a graph database on top of Postgres. So there was a a little bit of technical interest in there but you know nothing particularly outrageous.
</details>

**主持人**: 然后在 LinkedIn Intro 之后，你留在 LinkedIn 内部工作，据我了解你当时是在做**数据基础设施**，对吧？

<details>
<summary>Original English</summary>
**Host**: And then you you spent time after LinkedIn intro you still work inside LinkedIn as I understand you worked on data infrastructure right?
</details>

**马丁**: 是的，数据基础设施。我们的团队解散后，我转到了**流处理**（Stream processing）团队。当时 **Kafka** 刚在 LinkedIn 被开发出来，正准备开源。

<details>
<summary>Original English</summary>
**Martin**: Yes data infrastructure. Um after our team got disbanded, I switched over to the uh stream processing team. So Kafka had just been developed at LinkedIn and had just right. Oh, it was just being open sourced.
</details>

**主持人**: 我一直想问这个问题：为什么 LinkedIn 会开发 Kafka？现在它已经是一项如此基础的技术，但我总是很好奇，为什么一家公司会觉得有必要开发一个看起来如此通用、而且似乎每个人都会需要的东西？

<details>
<summary>Original English</summary>
**Host**: yeah, I think it had just been open sourced and then uh I got to work on samsa which was a stream processing framework on top of Kafka. I always wanted to ask this question so this comes here. Why did LinkedIn build Kafka or or develop Kafka? every time it's now such a fun foundational technology there always I was always curious like why did a company feel the necessity to build this thing that seems pretty generic and it seems everyone would have needed it.
</details>

**马丁**: 我想 **Jay Kreps**（Kafka 共同作者）那一时期有一篇很好的博客文章叫《**日志**》（The Log），他在文中解释了开发 Kafka 的动机，以及为什么选择**追加式日志**（Append-only log）而不是传统的队列。我认为动机核心在于**数据集成**。当时有大量的数据库和事件生成系统，比如生成用户活动事件的系统，它们产生的数据都是流式的。而下游有很多系统想要消费这些数据：有的想导入数据仓库，有的想导入 **Hadoop** 集群进行机器学习。这里存在一个物理层面的数据集成挑战：你如何把数据从一个系统导向另一个系统？Jay 把 Kafka 设计成了一个**集成点**，本质上是一个最大公约数，一个通用的抽象，用于集成各种数据源和下游数据槽。

<details>
<summary>Original English</summary>
**Martin**: Yes. So I think Jay Kreps has a pretty good uh blog post from from that era uh called the log where he explains his motivation behind Kafka and you know why why make it an appendon log rather than like a traditional message Q or something like that. I think the mo motivation was really about data integration because there were a whole bunch of databases and and like event generating systems you know like um activity events from users for example they were all generating data that in a sort of stream shape and then a bunch of downstream systems that wanted to consume this like wanted to get it into the data warehouse and wanted to be able to get it into the Hadoop cluster at the time in order to run like machine learning and things over it and there was just this data integration problem of actually like how do you physically get the data out of one system and into another and uh Jay designed Kafka as this integration point essentially like the almost the kind of lowest common denominator but still a general purpose abstraction uh for integrating v various data sources and to downstream data syncs
</details>

**主持人**: 在 LinkedIn 开发 Kafka 这种级别的系统，并在 LinkedIn 的规模下工作，你学到了什么？或者说让你惊讶的是什么？据我了解，这是你第一次亲手处理真正的大型系统，对吧？

<details>
<summary>Original English</summary>
**Host**: working at LinkedIn at at you know like Kafka and at LinkedIn scale what did you learn or what surprised you about working at this type of scale as I understand this was for the first time that you hands-on worked at a really large system, right?
</details>

**马丁**: 没错。在那之前我工作过的最大公司就是 Rapportive，只有五个人。我们虽然有一个不小的数据库，但它只是个单实例数据库，在大环境下根本不算大。到了 LinkedIn，突然之间我们可以使用大型 Hadoop 集群了。那很有趣，当时还要用 Java 手写 **MapReduce** 任务。我学到了海量的知识，特别是当流处理的想法冒出来，Jay 正在到处宣传 Kafka 的各种用途时，对我来说那简直是一个启示。我突然感觉：“啊，这开始变得合理了”，我开始理解这些各种各样的数据系统是如何组合在一起的、它们的共同点以及**基本原理**。这段经历直接喂养了后来的书籍创作。

<details>
<summary>Original English</summary>
**Martin**: That's right. Yes. Because like previously the biggest company I had worked in was Reporter with five people. We had a sizable database but it was still like a single instance database and not really that big in the grand scheme of things. And then yet suddenly I was at LinkedIn and oh we got to get get to use their big Hadoop cluster. That was fun like hand coding map produce jobs in Java at the time and so I I learned a huge amount there. Um especially when the stream processing ideas uh came up and Jay was evangelizing the use of Kafka and the things you could do with it. That was kind of a revelation for me really where I suddenly like felt ah this this kind of makes sense like I'm I start to understand how these various data systems fit together what they have in common what the fundamental principles are and so that experience then fed directly into the writing of the book.
</details>

### 离开 LinkedIn 与写作之路

**主持人**: 你是在什么时候决定离开 LinkedIn 的？在大多数人看来，职业路径可能是留在硅谷再创个业之类的。但你却决定离开。

<details>
<summary>Original English</summary>
**Host**: At what point did you decide to leave LinkedIn? To me, in in your careers, I'm looking through the career, start out in the UK, do a startup, do a second startup, Y Cominator, move to San Francisco, get acquired by LinkedIn. The arc that most people would draw would be, okay, do something more in Silicon Valley or maybe start a second startup, etc. And and instead you decided to leave LinkedIn.
</details>

**马丁**: 是的。首先我决定搬回英国，并开始远程为 LinkedIn 工作。这主要是因为我当时的女友（现在的妻子）还在英国，远距离恋爱并不好玩，而且我对湾区并没有强烈的归属感。我不想劝她搬来湾区，我觉得回欧洲对我更好。我非常满意这个决定，虽然我在湾区有很多好朋友，也喜欢来这里旅游，但我真不想住在这儿。搬回去后我远程工作了一段时间。当我开始写书时，LinkedIn 甚至非常慷慨地给了我 **50% 的自由时间**，让我可以在完成工程师职责的同时写书，这真的很棒。

<details>
<summary>Original English</summary>
**Martin**: Yeah. So, first I decided to move back to the UK actually and I continued working for LinkedIn remotely. Okay. That was m mostly because my girlfriend at the time, now wife, was still in the UK and long-distance relationship is not a lot of fun and I didn't feel that at home in the Bay Area. So, I wasn't really encouraging her to move to the Bay Area either. I thought it was better for me to go back to Europe and I'm very happy with that decision. Like, I still have a lot of great friends in the Bay Area. I love it as a place to visit, but I wouldn't want to live here honestly. Then I was still remotely working for LinkedIn and that worked all right uh for a while. When I then started writing the book, LinkedIn even gave me 50% of my time free to work on my book alongside my software engineering duties, which is really great.
</details>

**主持人**: 确实很棒，LinkedIn 对你太好了。

<details>
<summary>Original English</summary>
**Host**: Amazing. Yeah, that is so nice of them.
</details>

**马丁**: 绝对是。他们完全没必要这么做。除了公司内部培训能用上这本书外，LinkedIn 并不能直接从中得到什么。我要为 LinkedIn 点赞。但后来我发现，一边做工程师还要轮值（on-call），一边写书，实在太难了。**上下文切换**太多了，轮值的紧急事务会占据主导地位，让你失去创作新东西所需的自由心态。所以一段时间后我决定，全职专注写书会更好。于是我离开了 LinkedIn，休了一个**无薪假期**（也就是失业），专心写了一段时间书。在那之后，我才开始考虑进入学术界。

<details>
<summary>Original English</summary>
**Martin**: Absolutely. And there they don't have to do that. And LinkedIn didn't directly get anything out of it in response other than like a book that they could use for internal training purposes. Well, shout out shout out to LinkedIn for this. yeah, absolutely. Though then I did find then that actually trying to write a book in parallel with doing a software engineering job and being on call etc. I just wasn't able to do it. It's just too much context switching and it's very easy for the urgent things from the on call to dominate and and then not to have the you know the freedom of that you need in order to to write something new. Um and so then after a while I decided okay like it's it's probably better if I focus full-time on the book. So I then left LinkedIn and just took a sbatical unpaid sobatical i.e. unemployment um to just focus full-time on the book for a while and then it's only after that that I actually even considered getting into academia.
</details>

### 创作 DDIA 的初衷

**主持人**: 写这本书的主意是怎么来的？你当时想写的是什么样的一本书？

<details>
<summary>Original English</summary>
**Host**: So how did the idea of the book come? What was a point where you decided you would write and in your minds what were you deciding to write? What was was it already you know this this book with with with this layout or you had an early idea back then?
</details>

**马丁**: 我最初的想法和最终的产品看起来有些不同，但总体目标是一致的。我确定我想写的是一个**广泛的概念性概览**：不是关于如何使用某个具体的系统或工具，而是比较许多不同类型工具之间的权衡。而且我希望它**面向实践者**——不是理论教科书，而是人们可以用来构建真实系统的东西。这本质上就是我希望自己在刚起步、在 Rapportive 工作时能读到的那本书。因为当时我们都在黑暗中摸索，数据库出现性能问题时我们完全不知道该怎么办，因为我们缺乏理解发生了什么以及如何诊断问题的基础。我觉得如果我当时多了解一点这些数据系统的内部运作原理，我就能有直觉去调试那些性能问题。所以，在学到更多之后，我想是时候把它们写下来了，这样别人就不必再走弯路，而是能更好地管理自己的数据系统。

<details>
<summary>Original English</summary>
**Martin**: I had an idea that it of course the final product ended up looking somewhat different but the the overall goal I think stayed the same. So what I knew I wanted to write something that was a broad conceptual overview. So not about how you use any one specific system or tool but comparing the trade-offs between many different types of tools. And I knew that I wanted to be practitioner focused like not a theoretical textbook but something that people could use to build real systems. That was basically like the the goal with which I appreciate approached it. And this was exactly the book that I wish I had had when I was starting out and uh working at Reportive for example because we were all like searching around in the dark where we're having performance problems with our database and we had no idea what to do basically because we were totally lacking the foundations to actually understand what was going on and how to diagnose the issues. And so I felt that well if I had had a bit more background on how these data systems actually work internally then I could have had an intuition about how to debug these kinds of performance issues. And then after a while after I'd learned more about how data systems work I thought well okay it's it's time to write this down so that others don't have to learn it the hard way um but can hopefully just get a better idea of how these systems work and thus be better at managing their their own data systems.
</details>

**主持人**: 你最初是如何学习数据库运作原理的？很多工程师在这个阶段也只是知道公司内部有个平台团队负责这些，虽然可以读 RFC 或源码，但那工作量巨大。你是怎么挖掘这些基础知识的？

<details>
<summary>Original English</summary>
**Host**: to start with how did you learn about for example how databases work because again from from your story at report if you you build systems you've had some performance issues at a smaller scale to to be fair compared to LinkedIn then you worked at LinkedIn and you saw a little bit of how the sausage was made but I know a lot of software engineers who have been in this path and they still don't really know how the fundamental systems work they just know okay we have a platform team inside our company and they build it I could read the RFC's but it's a lot of work or the planning docs I could look look at the source code it feels to me that even at that point you just went down and and tried to dig in. What resources did you use? How how did you find out those those basics which you later put into the book?
</details>

**马丁**: 很大程度上源于好奇心和与人交流，问他们很多问题。在 LinkedIn 有一批资深的数据系统工程师，他们对这些东西了如指掌，但可能还没写下来。于是我找他们请教，在脑海中勾勒出这些东西运作的图像。掌握了基础知识后，我就能去读**研究论文**了，论文会深入讨论具体的设计细节和原因。虽然读这些很耗时，但我尝试提炼出核心思想。我也读了海量的博客文章。之所以书里每章末尾都有那么多参考文献，是因为那确实是我自己用来理解这些内容所读过的资料。我心想，如果我觉得这些东西有用，那我就把它们引用在书里，作为读者深入学习的来源。

<details>
<summary>Original English</summary>
**Martin**: A lot of of it was just kind of being curious and talking to people actually and just asking them lots of questions. And at LinkedIn there were like a bunch of senior data systems engineers who understood their stuff very well but hadn't maybe necessarily written it down. Mh. And so I just talked to a bunch of them and and quizzed them and that way started building a an image in my own mind of how this stuff works. And then once I sort of got the basics from these conversations, then I was able to go and read research papers for example. They go into much more detail of exactly how and why things are designed in such a way. Um but you know it is timeconuming to read those things. Um so so then what I tried to do was like pull out what what are really the essential ideas. I just read a ton of blog posts as well. Um and so the reason why you see so many references at the end of each chapter in the book is well that is actually the material that I myself used in order to uh understand what was going on. And then I thought well okay well if I found these things useful then I'll also cite them in the book as a way for anyone any reader who wants to go beyond the basics covered in the book here are some some good sources to further reading.
</details>

**主持人**: 这本书（第一版）的结构是：基础数据系统、分布式数据、衍生数据。当你开始写的时候，已经有这个结构了吗？

<details>
<summary>Original English</summary>
**Host**: Yeah, the the structure of the book, this first book at least, it's foundational data systems, distributed data, and derived data. If I understood, these are three big parts. Did you already have a structure in mind when you started writing the book or did it shape as you went?
</details>

**马丁**: 这三个部分的划分其实在设计时并没那么关键，更多是事后总结，觉得可以把章节大致归入这些结构。但**章节的主题**基本上是我预想好的。我确定我想谈谈什么是**事务**，想谈谈**复制**（Replication），想谈谈**分片**（Sharding/Partitioning），想谈谈**一致性与共识**（Consistency and Consensus）。这些高层主题在我提交给出版商的最初提案里就很明确了。至于每章内部的细节，通常是我写到那一章时才弄清楚的。我一次写一章，每章开始都会做背景研究让自己进入状态。通常在那时我才会决定，比如关于“复制”，主要有三种方式：单主（Single-leader）、多主（Multi-leader）或无主（Leaderless）。我会根据这些在写作时确定具体的叙事结构。

<details>
<summary>Original English</summary>
**Martin**: This three-part structure is not that critical in the design of the of the design of the book really. That's sort of more after the fact I thought, oh, well, it seems like we can group the chapters into roughly this sort of structure. But the topics of the chapters were more or less what I had envisaged. So I um I knew that I wanted to talk about like what a transaction actually is. I knew that I want to talk about replication. Knew that I wanted to talk about sharding or partitioning. Knew that I want to talk about like consistency and consensus. Those the sort of highlevel topics I think uh were clear from like my initial book proposal to the publisher. the details within each chapter. That is something that I often figured out once I got to that chapter. So, I wrote one chapter at a time and started each chapter work with just a lot of background research to actually get up to speed on the topic myself. And it's often only then that say for then replication I decided okay well it seems like the three major ways of doing this are single leader, multi-leader or leaderless. Okay.
</details>

**主持人**: 作为一名同样写过书的作者，我发现估算写书的时间和估算软件项目很像，如果你没经验，往往会偏差巨大。你的经历是怎样的？出版商就像项目经理一样，会盯着你的进度。你最后实际花了多久？

<details>
<summary>Original English</summary>
**Host**: As a as a fellow author who also wrote a book, one thing I've noticed there's a bit of parallels between estimating a book and estimating a software project in that you come in with a estimate and if you've never done it before you tend to be wildly off. How was this in your journey? And and addition, you also had a publisher and publishers are a little bit like project managers. They, you know, they they like to have a a schedule. They like to try to keep you on track. They they like to ask what when is it done? How did you manage that part as well? And and in the end, how long did you estimate it would take when you started and how long did it actually take?
</details>

**马丁**: 一如既往，实际耗时比预期的要长得多。写书和软件项目是一样的。我想第一版我写了大约**四年**。那不是全职的四年，大概相当于全职两年半左右。我错过了出版商的截稿日期，而且错过得非常离谱——大概迟了两年半。幸运的是，**O'Reilly** 对第一版比较有耐心，乐意让我慢慢打磨。但在写第二版时，O'Reilly 变得更有攻击性了，催得很紧。我想那时候书已经出名了，大家都在急切等待第二版，所以我能理解。但我真的很感激第一版时所拥有的那种按自己进度工作的自由。

<details>
<summary>Original English</summary>
**Martin**: As always, it takes vastly longer than expected. It's the same for software and projects as it is for writing, I think. So I think it took me about four years to write the first edition and that was not four years of full-time maybe like two and a half years of full-time equivalent or something like that but uh written over the course of about four years. So it definitely took a long time. The uh publisher deadline I missed by a ludicrous margin. I think I missed it by about 2 and a half years or something like that. Uh but fortunately O'Reilly were pretty laid-back with the with the second with the first edition and were happy for me to just take my time and make it good. Uh when it came to the second edition then actually O'Reilly got a bit more aggressive and pushy about uh sticking to deadlines. I guess by that point the book had been established and people were waiting eagerly for the second edition. So, I kind of understand the the desire to to want to accelerate it, but at the same time, I I really appreciated the the freedom that I had for the first edition to work on my own schedule. Um, and I had a bit less of that with the second.
</details>

### 可靠性、可伸缩性与可维护性

**主持人**: 第一版的副标题是“构建**可靠**、**可伸缩**且**可维护**系统的核心思想”，第二版似乎也是如此。这三个目标对你来说意味着什么？

<details>
<summary>Original English</summary>
**Host**: The tagline for the first edition, which I believe is the same as second edition, the big ideas behind reliable, scalable, and maintainable systems. Reliable, scalable, and maintainable. What do these objectives mean to you?
</details>

**马丁**: 它们的定义其实都有点模糊。对我而言，“**可靠性**”主要意味着**容错性**（Fault tolerance）。也就是说，即使网络中断、节点崩溃，系统整体仍应继续工作。书中很多内容都是关于支持容错的技术，比如复制。“**可伸缩性**”是一个经常被挂在嘴边的词，让系统变得可伸缩很时髦，因为它暗示了成功和数百万用户。但在书中，我尝试用更客观的方式来定义它：可伸缩性是处理**负载变化**的机制。如果负载增加，我们如何增加计算能力使系统正常运行。实现它的技术包括分片等。

<details>
<summary>Original English</summary>
**Martin**: Yeah. So they're all slightly vaguely defined, right? So there's there's not a a formal definition of those things. But uh for me, reliability means fall tolerance primarily. So meaning that a system should on the whole continue working even if like a network link is interrupted or a node crashes or something like that. So a lot of the book is about techniques that support fall tolerance like replication for example. Um so that's reliability. Uh scalability is one of those terms that gets thrown around a lot and it's sort of so much and it's it's like fashionable and cool to make things scalable, you know, because it's it suggests success and millions of users and so that's of course everyone wants things to be scalable because everyone wants success for this book. here tried to take a bit more dispassionate kind of approach and said scalability is just like what mechanisms we have for dealing with changes in load if load increases how can we add computing capacity to a system for example so that the system still continues working and then the techniques that you use to achieve scalability well they are like sharding for example
</details>

**主持人**: 在可伸缩性方面，你的定义主要是指**水平扩展**吗？也就是不能仅通过提升单机性能来解决。

<details>
<summary>Original English</summary>
**Host**: and and but in this case scalability your definition do I understand that you're mostly referring to horizontal scalability so they cannot compute up or down pretty much.
</details>

**马丁**: 是和那台机器比，你当然可以买一台更大的机器，但这没什么好聊的。现代云服务和后端服务真正有趣的地方在于它们引入了水平扩展和“**无共享**”（Shared-nothing）系统。这样即使单个组件是廉价的通用机器，我们也能构建应对极高负载的系统。不过，最近我也在思考可伸缩性的另一面：不仅是向上扩展，还有**向下缩减**。

<details>
<summary>Original English</summary>
**Martin**: Yeah, I guess because that's the the more interesting one like yes, you can always buy a bigger machine and what's interesting about that and exactly there's just there's not that much to be said about it. I mean there are details of how you scale even on a single machine but I think like part of what is become interesting about like modern cloud services and just uh backend services in general is like how they've introduced this idea of hor horizontal scalability and uh shared nothing systems. So we can build uh systems that you know are able to cope with very high load even if the individual components are just fairly cheap commodity machines. But maybe sort of part of the scalability story which I wasn't thinking about as much at the time but started thinking about more recently is not just scaling up but scaling down as well.
</details>

**主持人**: 所以其实是关于，如果负载非常小，如何让运行成本变得非常低。

<details>
<summary>Original English</summary>
**Host**: So actually um how do you run a service in such a way that if it has a very small amount of load it's really cheap to run it.
</details>

**马丁**: 没错。这本质上和高负载下的运行是同一个问题。通常你希望成本和计算能力与负载大致成正比。在低负载端，这意味着能够缩减到极低成本。这并不是理所当然的，对于本地部署（on-premises）的软件很难做到，因为物理机是一个部署单元。这也是**无服务器**（Serverless）系统有趣的地方：它们有缩减到零的能力。如果你每天只处理三个请求，那成本也可以忽略不计。

<details>
<summary>Original English</summary>
**Martin**: That's sort of a in a way the same question as how do you continue running a service if it has very high load. Um generally like you just want the the cost and the computing capacity to be roughly proportional to the load that you have. And at the low end that means actually being able to scale down to something that is extremely cheap to run. And that's like not so necessarily a given. That's something that is hard with on premises software for example because like if you've got a machine a physical machine that's like a a unit of deployment and yes you could carve it up into two dozen virtual machines and make those small virtual machines but um it still requires like some sort of resource allocation. So so part of what's interesting about some serverless systems for example is actually their ability to scale down and say like okay if you're going to handle just three requests per day that's just fine as well.
</details>

### 第二版：云原生与深度合作

**主持人**: 谈谈第二版吧。这个想法是怎么产生的？

<details>
<summary>Original English</summary>
**Host**: Can you tell me about the second edition? When did the idea come about?
</details>

**马丁**: 几年前就很明确需要第二版了，因为第一版已经有点过时了，技术变革没能反映进去。但我现在有教职在身，科研和教学是我的主业，更新书籍成了副业。因为要兼顾其他项目，进展很慢。而且我也意识到，由于转入了学术界，我对最新的**工业界实践**（比如数据湖）有些脱节了。这时我想起了 LinkedIn 的老同事 **Chris Riccomini**。

<details>
<summary>Original English</summary>
**Martin**: Yeah, it it had been clear for a couple of years that the second edition was needed just because the first edition was getting a bit dated. There were changes in technology that just hadn't been reflected in the in the first edition. So, I I wanted to update it, but you know, I now have an academic job. I'm actually like doing research and teaching is my main thing, and updating the book is just a sort of sideline business on the side in some sense. So it actually took quite a while to make progress with that because I was always doing it alongside other projects and essentially back to that context switching problem that that I had while writing the first edition but just now um with an academic job that I didn't want to just drop um because actually quite enjoy it initially then I made very slow progress with the second edition and also I kind of realized that I had slightly lost touch with current industry practices because you know I'd switched over to the the academic side. I gone much deeper on the theory. Um, but I was no longer up to speed on like what people were doing with say data legs or things like that. So then at some point it I remembered Chris Riccomini, an old colleague from LinkedIn. I had worked with him um on the stream processing stuff.
</details>

**主持人**: 你和他共事过。他是《**缺失的 README**》（The Missing ReadMe）的作者。

<details>
<summary>Original English</summary>
**Host**: you work with him. He's he's the author of the missing readme.
</details>

**马丁**: 没错。我读过 Chris 的书，觉得他写得太棒了。作为同事他也很出色。他一直在写一个叫《**物化视图**》（Materialized View）的关于数据系统最新趋势的通讯，还是这个领域的初创公司投资者。所以我联系了他，问他是否愿意帮忙做第二版。他非常感兴趣。这是一次极好的协作：他紧跟工业界的最前沿技术，而我对“如何教学”有强烈见解——即如何让书中的解释既精确、遣词造句考究，又通俗易懂。我们将我的写作风格与 Chris 对工业界趋势的洞察结合起来，完成了更新。

<details>
<summary>Original English</summary>
**Martin**: Exactly. Wow. What a small world. Yeah. And uh I I had read Chris's book, The Missing ReadMe, and thought, "Oh, he's a great writer." And I had worked with him as a software engineer and found him him a great colleague and also he had been writing this newsletter called materialized view on uh on like latest trends in data systems essentially uh and become a startup investor in in that space. Um, and so at some point I thought, well, actually I have to get in touch with Chris and ask him whether he wants to help out with the second edition. And he was keen to do that. And that turned into such a good collaboration because he was up to date on like what the cutting edge was in terms of uh technology in industry. Um, I had strong opinions on how to teach essentially. So how to explain things in the book, make sure that we were explaining everything in a in a way that was like very precise, very carefully chosen words, but at the same time very accessible so that it's hopefully easy to read. And so we took essentially like my writing style plus Chris's knowledge of latest industry trends to bring the book up to date and that was a a great collaboration.
</details>

**主持人**: 你们增加了哪些大内容？哪些是你一开始就知道缺失的，哪些是写作过程中才发现需要的？

<details>
<summary>Original English</summary>
**Host**: what are the big things that you added that and and which ones of these you knew would be missing and which ones did you realize during the writing process that okay this needs to be in here now
</details>

**马丁**: 我们从一开始就知道要反映的是“**云原生系统架构**”。这个词有点笼统，但我指的本质是基于**云服务**作为基础抽象来构建数据系统。在第一版中，基本假设是你拥有一些机器，每台机器有本地磁盘，数据库写到本地磁盘，如果你要复制，那是在数据库层面完成的。长久以来电脑都是这么工作的。但现在，人们开始在**对象存储**（Object stores）之上构建数据库。复制现在发生在对象存储层，而不是数据库层。这完全改变了事物的本质。这不同于 EBS 这种虚拟块设备，因为块设备仍试图模拟单节点操作系统的抽象。而对象存储是一种全新的抽象，它的行为和文件系统完全不同。这种构建方式在第一版时才刚萌芽，现在已经蔚然成风。我们将这个理念编织进了全书，而不仅仅是作为一个单独的章节。

<details>
<summary>Original English</summary>
**Martin**: yeah so the thing we knew from the start that we wanted to reflect was uh cloudnative systems architecture it's it's a bit of a vague term um but what I mean with that is essentially building uh data systems on top of cloud services as the foundational abstraction in the first edition the assumption was basically that you have some machines. Each machine has some local discs. You can run a database instance on a machine. It will write its data to the local disk. If you want to replicate it to another machine, then well the database software will replicate it at the database level to another machine which will also write the data to its local discs. For a long time that was exactly the way computers worked. And now suddenly people are building databases on top of object stores for example. And now the replication happens at the object store level. No, no longer at the database level. or maybe there's still some replication at the database level but it really changes the the nature of things uh if you're building on top of an object store and this is different from say building on top of a virtual block device like EBS or so because these block devices although they are cloud services but they still offer the abstraction that is a sort of single node operating system abstraction of a block device on top of which you run a file system whereas an object store is just like a brand new abstraction it just looks different from a file system, it behaves differently. And so then building on top of that as a foundational abstraction is something that like people were starting to do at the time of the first edition, but since the first edition that has really taken off like a whole lot of system have have been built in that style now. And so that's an idea that we really wanted to incorporate and we weaved that in throughout the book. So it's not just like one section here. Um but it's it's sort of a an idea that we've integrated throughout the entire narrative.
</details>

### 托管服务与底层原理的博弈

**主持人**: 现在有很多**托管服务**，工程师往往直接使用，因为云厂商负责了复制、SLA 和可用性。当我们将这些作为原语使用时，作为软件工程师，是否会面临不再有动力去理解底层原理的风险？

<details>
<summary>Original English</summary>
**Host**: There's now a lot of managed services as well. The per primitives that we use, but there's also so many managed services that all the cloud providers use and a lot of engineers, they often just use the managed services as is because they they take care of replication. They have SLAs for uptime and so on. But when you build on top of these things and you you kind of use those as a as primitives as well, is there any risk as a software engineer that you're no longer incentivized to understand the underlying layer or are we building better systems because of that? How do you think about this? It it feels there's a move of abstraction because of cloud, right?
</details>

**马丁**: 抽象层次确实在提升，但这是整个计算工业自诞生以来的主旋律。依赖高层抽象确实会让你不再思考底层细节。如果你用带垃圾回收的语言，就不再思考内存分配。这是损失吗？也许吧。如果你在构建底层系统，你仍需关心；但如果你在构建高层业务逻辑，我觉得不关心内存管理也没问题。数据系统也是如此：如果你构建的高层系统不需要特别关心底层设施，那就直接用高层抽象，没毛病。但**总得有人**去从底层组件构建那些抽象，总得有人去实现云服务。

<details>
<summary>Original English</summary>
**Martin**: Yeah, it's definitely a a shift to different and higher level abstractions, but you know that's been the story of the entire computing industry since the start. It's like building new abstractions. So it is true that like if you rely on a higher level abstraction, you're no longer thinking about the lower level details. And so it's you're using a a programming language with a garbage collector, you're no longer thinking about memory allocation. And so is that a loss? Well, maybe. Like if you if you're building low-level systems, you should still have to care about memory allocation. You're building higher level business logic. Actually, I think it's just fine for people not to care about memory management. So I think there's an analogous thing here with data systems that if you're building the higher level systems that don't need to particularly care about the underlying infrastructure, then that fine. Just use the higher level abstractions. Nothing wrong with that. But somebody still has to build those lower level abstractions from lower level components. Somebody's got to implement the cloud services.
</details>

**马丁**: 那些实现云服务的人需要更加专精于如何工程化这些服务、如何保证可靠性、如何运行它们。技能依然存在，只是发生了**专业化分工**：一部分人专注于高层业务，不用担心底层；另一部分人专注于底层，并把高层作为他们的客户。

<details>
<summary>Original English</summary>
**Martin**: And so those people will have to then specialize even more in actually the details of how you engineer those cloud services, how you make them reliable, how you operate them and so on. The skills are still there. It's just a bit of specialization happening that some some people can worry about the higher level things without having to concern themselves with the lower level things. Some people focus on the lower level things and treat that higher level aspect as their customers.
</details>

**主持人**: 这听起来很有趣。如果你是使用这些服务的工程师，可能不需要精确了解它们的运作方式。

<details>
<summary>Original English</summary>
**Host**: Interesting. So it it sounds to me that if you're an engineer who is utilizing a lot of these services, you might not need to know how they exactly work.
</details>

**马丁**: 是的。但我认为整本书的底层哲学是：赋予人们洞察系统内部运作**本质**的能力。这样，如果出现奇怪的性能问题，你能有直觉知道为什么，以及如何解决。例如，存储引擎章节会告诉你 B 树和 **LSM 树**是如何工作的。这本书不是为了让人们真的去手写数据库，如果你想那样做，需要更深的研究。但作为应用开发者，如果你了解存储引擎内部的一点点知识，你就能更好地利用它来获得高性能。即使在云服务时代，这种哲学依然适用：虽然云服务隐藏了操作细节，但你仍应了解一点内部原理，以便高效使用。

<details>
<summary>Original English</summary>
**Martin**: Yes. And I would say like the underlying philosophy of the entire book is to give people insights into just the sort of essence of how the systems work internally. So that if for example they start having weird performance behavior, you can have a bit of intuition for why it's doing that and how you might solve it. So for example, say the storage engine chapter tells you about how Bes work and how lock structured LSM trees storage engines work. And the book is not intended for people who are going to actually build their own databases and implement their own storage engines. If you want to do that, you have to go much much more much greater depth than this book covers. But the idea is that as an app developer, if you know just a little bit about how the storage engine works internally, you'll be in a much better place to use it in a way that is that gives you good performance for example and to diagnose any issues. That philosophy we've kept also in the context of cloud services where yes, like cloud service hides some of the operational details that app developers don't need to think about anymore, but they should still know a bit about how they work internally just so that they can use them effectively.
</details>

### 权衡：性能、成本与地缘政治

**主持人**: 我想工程师总要争论（或应该争论）的至少是**成本与性能**。性能不仅指延迟，还包括弹性：如果一个区域宕机了，产品受影响程度是多少？

<details>
<summary>Original English</summary>
**Host**: I guess I argue about the trade-offs deciding on which which service to use, which characteristics to look out for. Yeah. For for your use case, right? Exactly. And and you know, they're huge differences of say if you're doing analytics whether you're using row oriented storage or column oriented storage. That's a bit of a technical distinction and it takes a little bit of background reading to even understand what that means, but it has a massive performance implication in terms of the final behavior of the system. And so those are those places where I feel like knowing a bit about the the internals is actually like a superpower. Yeah. And I guess engineers the one thing that we always need to argue about or should need to argue about is at the very least cost versus performance. And by performance I mean latency to the user and of course resilience of if if something happens you know like a region go like a zone goes down a machine goes down zone goes down region goes down how our product is affected and what's acceptable.
</details>

**马丁**: 没错。基本理念是：你愿意承担多少**可用性风险**，来换取系统本身的计算开销、以及设计和运营的人力与成本开销。你可以拥有一个更耐受各种故障的系统，但它设计和运行起来更贵。这没有绝对的对错，每个人需要根据自己的权衡空间来定位。**多地域**（Multi-region）是迈向更高可用性的方向，意味着你能容忍整个区域的停机，但这会影响不同地域之间的一致性模型。

<details>
<summary>Original English</summary>
**Martin**: The basic idea there seems to be like how much availability risk are you willing to take on versus the both like the overheads in terms of um the the system itself like the computational overheads but also the human overheads actually designing and operating the system and and the cost overhead. Yeah, exactly. And so yes, you can have a a system that is more able to tolerate various types of faults but it which is more expensive to uh to design and operate versus a simpler system that you know might go down a bit more often but which is cheaper. And there's no right and wrong with that. You know it's a everyone needs to figure out where they sit on that uh on that trade-off space uh themselves. And I would say that like multi-reion is like pushing in the direction of like higher availability because it means you could tolerate the outage of an entire region. But then it has implications on the consistency model that you can get across different regions for example. So that's a trade-off that the book tries to make very explicit to help people reason that through of like what is the right choice for them.
</details>

**马丁**: 关于**多云**（Multi-cloud），最近一个月我非常关注的一个点是：欧洲对美国云服务的依赖。如果地缘政治出现严重偏差，紧张局势升级，欧洲突然发现自己被锁定、无法使用美国云服务了怎么办？我希望这不会发生，但它已不再是“不可想象”的了。从欧洲的角度出发，我一直在思考如何工程化系统以抵御这类风险。这不仅是区域性停机，而是一种**商业风险**。多云架构可以缓解这种风险，哪怕一家公司锁定了你，你仍能在另一家公司运行。这当然属于昂贵但能降低高可用风险的极端方案，但对于那些拥有极关键业务的人来说，这种**地缘政治风险**是值得认真考虑的。

<details>
<summary>Original English</summary>
**Martin**: In terms of multicloud, for example, one thing that I've been uh concerned about just in the last month really is uh European dependence on US cloud services. Yes. So what if geopolitics was to go horribly wrong and tensions escalate and Europe finds itself suddenly locked out of US cloud services? I hope that doesn't happen. I still think it's fairly unlikely, but it's no longer unthinkable. and and as a result I coming sort of from this European perspective have been thinking a fair bit about how can we engineer systems to be resilient against that sort of thing and that's you know not just like a regional outage but it's like a a business risk essentially and a multicloud sister uh setup could help mitigate against that sort of risk so that at least for example if one company locks you out then you could still have systems on on another company again that that's very much towards the uh expensive but uh high availability risk reduction end of the spectrum. But for the people who have you know really critical workloads where they think this sort of geopolitical risk is a significant enough risk I think it's seriously worth considering that kind of setup.
</details>

### 分布式系统的困境与技术更迭

**主持人**: 分离这种风险和沟通权衡将成为工程师核心职责的一部分。随着 AI 编写越来越多的代码，我们作为工程师的价值可能更多在于这些高层权衡。在第二版中，“规模”的定义有什么变化？

<details>
<summary>Original English</summary>
**Host**: I'm thinking that that as we do have the responsibility because because who else will will do this? Yes, totally. But I totally agree with you as well that this um understanding what the risks are and communicating what the trade-offs are I think is is going to be a core part of our role as engineers moving forward as well. Maybe as AI writes more and more code of our code, it's less about like the details of how you express logic in a particular programming language and much more about those kinds of of highle trade-offs. How has the definition of scale changed in this book?
</details>

**马丁**: 实现极高规模依然具有挑战性。虽然云服务提供了弹性的对象存储，你不用再担心磁盘容量规划，但**分片**（Sharding）依然会反映在应用代码中。当规模大到单机无法处理时，分片是必须的。我认为云服务帮助最大的是“**缩减规模**”的一端。有了 Serverless，你可以快速启动和关闭实例，这让超轻量级服务变得非常经济。我有个小网站跑在 Serverless 上，每月账单只有 13 美分。

<details>
<summary>Original English</summary>
**Martin**: So I think achieving Being really high scale is still challenging because even though we have cloud services like object storage for example which uh provide you this very elastic storage model at least you don't have to worry about capacity planning on your discs anymore and running out of disk space because those kinds of operational things they're taking care of but if you need sharding for example that's something that actually does reflect on the application code as well you can't really make that entirely transparent and so you're at a sufficiently large scale The charting is required because a single machine is not powerful enough to process your workload. Then I think even with cloud systems you still have to do quite a bit of engineering thinking of u of how to realize that where I think the cloud has helped quite a bit is actually at the lower end of scaling down. Uh if you want to have a very lightweight service that processes only a small number of requests. what we've got with serverless systems being able to very quickly spin up and spin down uh an instance very lightweight that's quite a a good innovation that has enabled those those very low scale uh services and that's something that's would be much harder to do without cloud services because you would have to statically allocate a certain amount of memory and certain CPU resources to a particular virtual machine I love serverless I I have a small website that runs on serverless and my bill is like 13 cents per month because it has very little load.
</details>

**主持人**: 谈到分片。在第一版问世时，我在 Uber 工作，当时面试总会问分片。但现在似乎更少工程师需要亲手实现分片，因为云平台提供了开箱即用的方案。你的研究发现了什么？

<details>
<summary>Original English</summary>
**Host**: Let's talk about sharding. In in the first book and when you wrote the first book when I was working at Uber, we talked a lot about sharding and there was a lot of internal implementations or interviews involved asking about sharding because we were designing systems that were sharding. I did sense that over time again as as cloud systems start to become available that give you turnkey solutions more that act more like platforms. You send the data and it takes care of of these things. Fewer engineers have to actually implement sharding with cloud native systems in your research. What have you seen? What what are the cases where putting sharding in place is still important and where are the places where it it might have just disappeared as a as a concern?
</details>

**马丁**: 这种变化与其说是云的影响，不如说是**硬件**变得越来越强大了。现在的单台大机器性能非常恐怖，这意味着越来越多的工作负载只需要单机就能跑，而且规模已经相当可观了。当然，你仍需考虑如何充分利用单机上的数百个 CPU 核心，所以**并行性**仍是必修课，而分片是实现并行的一种方式。但跨机器的分片确实没以前那么迫切了。不过，**复制**（Replication）在任何规模下都极其重要，因为它关乎容错，而非伸缩性。

<details>
<summary>Original English</summary>
**Martin**: I think it's probably less of an effect of cloud and more of just hardware getting more powerful that that oh actually like a big machine nowadays can do a lot on a big machine you if you and that means that more and more workloads you can just run on a single machine and that is sufficient actually to achieve quite significant scale already there's still concerns of like how to actually efficiently make use of hundreds of CPU cores that you have on a single machine so there's still parallelism is still are a required thing to think about there and sharding is one way of achieving parallelism. But at least this sort of sharding across multiple machines is maybe become less of a pressing issue just because more and more workloads can just run on a single machine. Some people still have very large scale workloads that do have to be sharded across multiple machines but it's not going away entirely and uh replication is still relevant even at smaller scales because that's for fall tolerance that's not for scalability.
</details>

**主持人**: 书中有一章叫《**分布式系统的麻烦**》，讲了各种可能出错的情况。有哪些令你印象深刻？

<details>
<summary>Original English</summary>
**Host**: You have a chapter called the troubles with distributed systems uh which goes through a lot of things that can go wrong without going through the whole chapter. Can you recall some of the things that are memorable to you or some of the things that you feel are are important to remember?
</details>

**马丁**: 这一章的核心是：分布式系统理论中我们往往会做一些假设，比如网络消息传输时间没有上限——可能 100 微秒到，也可能 10 年才到。如果你做出了过于乐观的假设是很危险的。另一件事是关于**崩溃**：在实践中，节点不可用可能意味着软件崩溃、硬件故障、掉电，或者节点还跑着但断网了。这一章是为了通过大量的案例研究（Case studies）来证明那些理论模型的价值，告诉大家：别相信任何人说的“故障很罕见”。如果你想让系统可靠，你必须担心各种离奇的边缘情况。**时钟同步**也是个坑，我们总倾向于认为时钟是准确的，但实际上它们精度不足且不可靠。

<details>
<summary>Original English</summary>
**Martin**: Yeah. The whole idea of this chapter is that in distributed system theory there are certain things that we tend to assume. Like for example, we just assume that there's no upper bound on how long it might take for a message to go over the network. So you send a message, it might arrive within a 100 microsconds or it might take 10 years and distributed system theory just doesn't make any assumptions about that sort of timing if we can avoid it or rather some some theory does make those assumptions but it's an dangerous assumption to make because occasionally the network delay does become much higher than than what is typical. Another thing is about uh crashes. For example, the distributed system theory just says like nodes can crash but what does that actually mean? Like what in practice does it mean for a node to become unavailable because it might be a software crash but yes it might be a hardware failure. It might be somebody unplugging the power cable. It might be that the node is actually still running but it's just become disconnected from the network. The point of this book chapter really is to defend and justify those theoretical models that we use for analyzing distributed systems and just giving a lot of stories and case studies that show that you know actually tons of stuff does go wrong and like don't believe anyone who says oh failures are rare it's don't don't worry about it it's fine. Uh the the the moral of this chapter is really that actually know if you want to make things reliable, you really do have to worry about a whole bunch of weird unusual but but certainly possible edge cases. Timing is another one of those things like you know it's very easy to assume that your clocks are correct and most of the times the clocks are pretty correct but we just can't rely on it because actually they're just not precise enough uh on the whole and so a lot of it is about it's very tempting to make certain assumptions um that things are well behaved and and in distributed systems we just have to try to get away from those assumptions if we want the systems to work reliably even in the face of things going wrong
</details>

**马丁**: 写这一章很有趣，因为它本质上是一个“翻车大赏”。我翻阅了各大科技公司的事故回顾（Post-mortems），比如**鲨鱼咬断海底光缆**导致损坏。听说最近几年海底光缆的屏蔽层改进了，鲨鱼不咬了，但现在变成了陆地上的**牛**会踩到电缆导致断网。这些故事让内容变得很有趣。

<details>
<summary>Original English</summary>
**Martin**: but it was a really fun chapter to Right? Because you know it's it's essentially a big collection of stuff that has gone wrong. And so I went through a bunch of postmortems published by various tech companies for example in order to see okay what was the root cause of how things went wrong and what kind of lessons can we draw from this that apply to the the book in general. And uh you know there's some fun stuff like the the sharks biting undersea cables and damaging them that just you know makes for a great story. And then I I hear that in recent years the shielding of undersea cables has got better and therefore the sharks are not biting them anymore. But instead the cows on land are stepping on cables and occasionally causing network interruptions that way. And you know that sort of thing is just uh it makes it a bit more fun.
</details>

**主持人**: 有哪些概念在第一版和第二版之间变得更流行或不再流行了？比如流处理、批处理等。

<details>
<summary>Original English</summary>
**Host**: Have you come across some concepts or sips as mentioned in the book in the first edition and now in the second edition that are becoming either more popular or less popular over time more or less referenced by your readers thinking about from things like streaming systems, batch processing or or anything else?
</details>

**马丁**: 有一些内容我们精简了。特别是 **MapReduce**，在第一版中讲得很细，但现在 **MapReduce 已经过时了**，没人用了。取而代之的是 **Spark** 和 **Flink**。我们在第二版中仍提到 MapReduce，但更多是作为理解分片式批处理系统的教学工具。另一方面，我们大大增加了关于 **AI 支持系统**的覆盖。虽然这不是一本 AI 书，但支持 AI 应用会带来数据系统方面的挑战。最典型的例子是**向量索引**（Vector indexes），我们将其加入到了存储引擎章节。此外，我们还增加了对 **DataFrame** 的介绍。它不仅在 AI 中很重要，在处理训练数据时也是一种极佳的数据表示形式。这些更新反映了人们当前构建系统的真实情况。

<details>
<summary>Original English</summary>
**Martin**: Yeah. So the some things that we've been able to take out uh out of the book compared to the first edition in particular for example coverage of map reduce was quite detailed in the first edition but basically map produceuce is dead nobody uses it anymore. It's successors like in the form of spark and flink for example they are used and so we still reference map reduce in the second edition but more as a learning tool in order to understand how these kind of partition sharded batch processing systems work. So that's one thing where we've been able to reduce the coverage. Um, but other areas where we've increased the coverage are, for example, systems in support of AI. And so, even though this is not an AI book, but there are still data systems concerns that arise when needing to support AI applications, like a classic one is vector indexes, for example. And so, we've added some coverage of vector indexes to the storage engine chapter. Fit in really well there because it already covers various different indexing strategies anyway. Uh and so vector indexes, you know, it's just another indexing strategy. We also added some coverage of data frames, for example. That's not an exclusively AI thing. Um but data frames are quite a good data representation for training data, for example. And that was not one of the data models that we discussed in the first edition, but we decided to add to the second edition because it has actually become a very important data model that people are using alongside all of the classic data models like relational and graph and uh JSON documents and so on. And so there these these places where we've just expanded the coverage a bit to to reflect the kinds of systems people are building for example to support AI without it like changing the direction of the book entirely.
</details>

### 做正确的事：工程师的伦理责任

**主持人**: 第一版末尾有个小节叫“做正确的事”，在第二版中它成了一个独立的章节。我想引用其中一句话：“作为构建这些系统的工程师，我们有责任仔细考虑那些后果，并自觉决定我们想要生活在什么样的世界里。”谈谈这一部分的重要性？

<details>
<summary>Original English</summary>
**Host**: The final subsection in this first edition the first few I guess like sub parts were titled doing the right thing and in the second edition this has its own chapter. The final chapter is doing the right thing and I I quote a little bit from it. We the engineers building these systems have a responsibility to carefully consider those consequences and consciously decide what kind of world we want to live in. Can we talk a little bit about this section and the importance of it?
</details>

**马丁**: 加入“**伦理**”章节的动机是，我发现在工业界，这一关切往往被忽视了。特别是在初创公司，人们非常专注于构建客户喜欢的产品，而降低了伦理问题的优先级。比如一些面向消费者的产品，本质上是为了数据收割（Data harvesting）而设计的，因为这可以通过广告变现。当时对这些做法的好坏几乎没有反思。所以我想鼓励大家思考：如果你想改变世界，那么思考你的技术对世界产生的影响，就是你工作的一部分。工程师往往容易只关注技术，而忽略了技术在现实世界中的副作用。这也反映了我个人的转变，因为我刚开始做系统时也没怎么想过伦理问题，写这一章也是为了我自己。

<details>
<summary>Original English</summary>
**Martin**: Absolutely. Yeah. So the motivation for putting in an ethics section there in in the first edition was that I just felt it had been quite ignored as a concern during my time in industry. um that like especially in startups people were very focused on like building a product that their customers would love and really like deprioritizing these sort of ethical questions in the in the process. And so for example with the consumerf facing products it might be that the products are very much geared towards essentially data harvesting collecting behavioral data um because that's what can be monetized in the form of advertising and there seemed to be just very little reflection on what was good and bad about these sort of things. So I really just wanted to encourage a bit of thinking there. Um not really wanting to prescribe too much like a a particular approach there but at least to point out you know there there is this thing such as data protection legislation now which we do have to think about in the architecture of our data systems and there is an ethical responsibility. You know pe people say that uh you get into tech in order to change the world. If you want to change the world, then thinking about the impact that your technologies have on the world is part of your job. It's it's a really essential part really and something that engineers are often prone to ignoring as we focus just on the technology and less on the effects that that technology will have out in the real world. And so this chapter is really just an attempt to get people thinking about it a bit. And it's sort of a a reflection of my own process as well because as I started working on these systems, I didn't really think about ethical things particularly either. So I felt like um I had to put that section in there for myself as well as for the readers because it was my own way of of grappling with these questions a bit.
</details>

### 形式化验证与 AI 的交汇

**主持人**: 作为构建这些系统的工程师，我们处于一个极佳的位置，可以影响甚至改变方向。你曾写过一篇关于**形式化验证**（Formal verification）的文章，认为在 AI 时代它将变得更重要。能解释一下什么是形式化验证吗？

<details>
<summary>Original English</summary>
**Host**: Is it fair to say that as engineers building these systems that will have an impact on on a wide range of things potentially societal wide impact we are just in such a good position to directly influence and maybe even change course. So do I understand that this section is a bit of reminder that by building it we have a huge opportunity to shape these we probably have a lot stronger voices maybe as strong voices as later on the regulator might have years down the road. Right. Exactly. I think engineers have a very strong voice there and like we talked about earlier um engineers need to articulate trade-offs in such a way that uh business leaders can then make educated decisions about how to address those trade-offs. And part of those trade-offs is pointing out risks. And risks include not just technical risks like the data might get corrupted, but they include societal risks as well. For example, like um what negative uh effects, what harms might arise from this technology, what sort of unintended consequences possibly or what like uh risk for reputational damage if it turns out that a technology has some harmful effects. um you know that can reflect badly on the company that made it and that has to be part of the the trade-off discussion and I just want people to make intentional and deliberate decisions about this kind of things and not just sweep it under the carpet. One of the hot topics these days is of course AI and you've written a very interesting post about this just in December about formal verification and how your conviction that formal verification might be more important with AI. Can we talk for for those of users who have heard formal verification, can we talk about what this is and how you envision this becoming more important?
</details>

**马丁**: 形式化方法有一系列手段。一种是使用规范语言（如 **TLA+**）在高层次描述系统的预期行为，然后用模型检查器自动测试各种场景。更进阶的是**形式化证明**，通过数学符号编写系统规范，并证明某个算法始终满足该规范。它与测试的区别在于：测试只是尝试几个例子，而证明可以对无限的状态空间进行推理，证明某种安全属性在任何可能的情况下都成立。

<details>
<summary>Original English</summary>
**Martin**: Yeah. So there's a whole range of formal methods. Um, one approach is to for example use a specification language uh like FSBY or TA+ or something like that to describe the expected behavior of a system at a at a high level and then use a model checker which is essentially like a randomized test case generator to just play through a lot of scenarios and see whether the the system has those desired behaviors in in all the different scenarios. That's like the sort of intro level formal verification. I would say the more advanced level is to use actual formal proof and in that case you can write a specification of some system in a formal language is usually using mathematical notation and then make a mathematical proof that a certain algorithm or certain implementation always satisfies that specification. And the distinction to testing there is that well in testing you just try through a couple of examples, give the algorithm some example inputs and check whether you get the expected output in those particular examples. But a proof can reason about potentially infinite state spaces. So it can tell you things about like every possible thing that could possibly happen in the entire universe show that for example a certain safety property is is always given in those
</details>

**马丁**: 形式化验证工作量巨大，我在工业界时从未用过，因为它太耗时了。只有进入学术界，我才能花几个月时间去证明一个算法的正确性。这在处理一些**极端微妙的算法**时非常有用，因为仅靠读代码很难确信它在所有情况下都正确。

<details>
<summary>Original English</summary>
**Martin**: formal verification is is a lot of work. Um, I never used it in my time in industry because it's just too too timeconuming basically. Um, I only got into formal verification when I was in academia and I could afford to take the time to spend a few months proving an algorithm correct. But there I've started finding this very useful especially if I was working on very subtle algorithms where it's very hard to tell just from reading the implementation whether this actually is always correct under all possible cases. But if it's an important algorithm where for example uh it will corrupt data if there's a mistake in it or it will have a security vulnerability if there's a mistake in it then when it's high stakes uh things like that then I feel it's worthwhile to have uh formal verification and to really make sure that the the code really is correct and so I've done some uh formal proofs using the Isabel proof assistant for example there are a couple of others as well uh uh like rock and lean and uh so on.
</details>

**主持人**: 你提到的“氛围编程”（**vibe coding**）让形式化验证变得更重要，为什么？

<details>
<summary>Original English</summary>
**Host**: When you say it's hard to write... Can you just explain what what it means to hard to write?
</details>

**马丁**: 因为 LLM 越来越擅长写这些证明。如果人类不用手写，它就在以前不经济的场景中变得可行。而且由于我们现在用 AI 快速生成大量代码（即所谓的“氛围编程”），如果让写代码成为瓶颈，那么人类手动审查所有生成的代码也会成为瓶颈。我们需要**自动化的方式**来检查代码是否正确。测试是一个好的起点，但证明能考虑到“绝对每一种可能发生的情况”。这在**安全领域**至关重要，哪怕一个小 Bug 都能摧毁整个系统。我希望 AI 能让那些以前觉得形式化验证太难、太贵的人也能使用它。

<details>
<summary>Original English</summary>
**Martin**: So the the reason I think that um the I believe that this formal verification could become more important in the future is kind of several aspects to it. One is that the LLMs are getting increasingly good at writing these proofs and if we don't have to write the proofs by hand as humans, it just becomes feasible to do them in situations where previously it would have not been economical. But also, LLM increase the need for these formal proofs because, you know, we're vibe coding a bunch of stuff. If we have to manually review all of that code, then that will become the bottleneck. So, we can't really have humans reviewing all of the generated code either if we really want to get the the benefits of of AI. So, we need some automated way of checking whether the code is correct. And writing lots of tests is a very good starting point. But the thing that proof can do that tests can't is to consider absolutely every possible thing that could happen. And that's really important in a security context for example where it just takes one little bug want to create a vulnerability that destroys the security of the whole system. And so I feel for those domains where like really we want to ensure there's a complete absence of bugs that's the kind of places where formal verification can really shine. And I'm hoping that LLMs will actually make that a lot more accessible to to people who would have previously not considered using formal verification because it was just too hard and too expensive.
</details>

### 学术研究：本地优先与主权数据

**主持人**: 从工业界转向学术界，这种转变感觉如何？学术界每天都在做些什么？

<details>
<summary>Original English</summary>
**Host**: You've worked in the industry and then you went into academia. Can you tell us what the difference is between us? What do you and your colleagues do inside of academia?
</details>

**马丁**: 学术界最大的魅力在于可以思考**更长远的问题**。在初创公司，你必须在几个月内交付，没法考虑 10 年后的事。学术界有自由去研究那些目前商业上尚不可行、或者与商业公司利益冲突的课题。我研究了好几年的一个领域叫“**本地优先软件**”（Local-first software）。核心想法是：我们想把权力从云运营商手中拿回来，还给终端用户。用户应该能控制自己的数据，而不是被迫依赖云服务来运行应用。

<details>
<summary>Original English</summary>
**Martin**: Yeah, within academia, there are lots of different styles really. A common distinction there is that academia can just think much longer term. So the you know if you're doing a startup you have to ship something within a few months. You can't afford to think 10 years into the future. But in academia what I really appreciate is the freedom to work on things that are long-term and which are not like immediately commercially viable or which are not aligned with the incentives of commercial companies. Um so one of research area that I've been on for several years now is what we call local first software which is this idea that we want to take away a bit of the power from cloud operators and give it back to end users. So end users should be more in control of their own data and less dependent on cloud services for providing the applications and the data that that the users need.
</details>

**马丁**: 这在商业公司里不常见，因为 **SaaS** 的订阅模式本质上是拿着枪抵着客户的头说：“付钱，否则我就删了你的数据。”我理解这种商业动力，但这种关系是不健康的。但在学术界，我可以优先考虑对用户正确的事。

<details>
<summary>Original English</summary>
**Martin**: And that's something that doesn't naturally come to companies, right? Because uh software as a service businesses, for example, the whole reason why they can charge a subscription is because they are able to essentially hold a gun to the customer's head and say, "Pay us your subscription, otherwise we will delete all your data." And I totally understand the the commercial imperatives that lead to that, but it also leads to this situation where like the people have a gun against their head all of the time. That isn't really a healthy situation to be in in my opinion. But changing that in such a way to take away that gun from customers heads is difficult if you're in a business whose revenue depends on perpetuating that kind of lock-in situation. And there I feel like in academia I have the freedom to work on things that go against this commercial incentive of companies and say like actually no I'm going to do what I think is right for the users and that I'm going to say the commercial model of the companies making the software is second priority and I can afford to do that because I'm I'm not dependent on this commercial model.
</details>

**主持人**: 这其中有哪些有趣的工程挑战？比如笔记应用？

<details>
<summary>Original English</summary>
**Host**: To add to this, it's very interesting and challenging engineering problems. What are some of these really interesting engineering challenges that we we will need to solve or or we need to solve to get to a more viable local first software? May that be like let's say note-taking. It's a very popular one, right?
</details>

**马丁**: 本地优先意味着脱离对中心化云服务的依赖。数据同步可能仍通过云，但我们不信任它提供核心功能。这就引入了巨大的挑战，比如**访问控制**。在中心化系统中这很简单，服务器说了算。但在去中心化或对等网络中，如果一个用户的编辑权限被撤销了，而他同时进行了一次编辑。有些设备可能先看到编辑，有些先看到撤销。这会导致设备间**永久性的不一致**。为了在不依赖共识协议（因为共识要求节点在线）的情况下解决这个问题，我们付出了巨大的努力。这是 **Automerge**（马丁参与的 CRDT 库）正在解决的问题。

<details>
<summary>Original English</summary>
**Martin**: Yeah. So with our vision of local first software, we're trying to get away from this dependency on centralized cloud services. There may still be cloud services involved in syncing data between your phone and your laptop say um because often going via cloud service is just the most convenient way of establishing that kind of communication. But we just don't want to have to trust on a cloud service providing a particular function. But that introduces a whole bunch of interesting research and engineering challenges because uh so one thing that we've been working on lately say is access control. You know simple problem you have a document you want to be able to grant collaborators access and you want to be able to revoke that access. In a centralized cloud service model it is totally straightforward because you have the rules you confirm that those sort of things and you check for the right roles and that's it. But if you want to run your system over multiple providers or even in a peer-to-peer setting then well what could happen is that uh a user gets their edit permissions revoked and concurrently that user makes an edit to the document uh whose permissions have just changed and now some devices may see the edit to the document first and the revocation second and so they would accept the edit to the document and another device may see it the other way around. They may see the revocation first and then the edit to the document second and they'll drop the edit to the document because they think it's not authorized. And now those devices have become inconsistent with each other permanently inconsistent. So that means if we actually want to ensure consistency even for this fairly basic setup we now have to somehow figure out how to resolve this situation of an edit that is concurrent with the revocation of the user who made that edit.
</details>

### 未来研究：可持续性与密码学

**主持人**: 除了本地优先，你还在研究什么新领域？

<details>
<summary>Original English</summary>
**Host**: What are your current research topics that you're working on ones that you're excited about?
</details>

**马丁**: 我正在开启一个全新的研究方向：使用**密码学**来证明物理世界的真相。特别是在**可持续性**方面。例如，如果你想验证制造某个产品的碳排放量，目前的数字往往是不准确的，因为各方有动力去撒谎、进行“洗绿”（greenwashing）。另一个例子是欧盟关于防止热带雨林毁林的法规。进口商需要证明咖啡、棕榈油等到底来自哪块土地，并对照卫星图像检查。我正在研究如何使用密码学来证明这些物理供应链的数据是真实的，同时又不泄露商业敏感信息（比如供应商是谁、秘方是什么）。

<details>
<summary>Original English</summary>
**Martin**: I'm now also trying to set up a brand new research area in a totally different topic um which is on using cryptography to prove things about the physical world. So I'm interested there in especially sustainability related things. So for example, if you want to verify that the carbon emissions involved in manufacturing a particular product were X and you want to be sure that that number is correct because maybe you want to include emissions as part of your purchasing decision and choose the product with the lower emissions. For that to be meaningful, the emissions number has to be correct. And unfortunately at the moment the numbers are generally not correct because the incentives are to lie and cheat and to use creative accounting techniques all as a way of like greenwashing basically or a related thing is happening in the EU for example which is bringing in new regulations on preventing deforestation of tropical rainforests. importer needs to prove exactly which plot of land it actually came from and then check against satellite imagery that that was not recently deforested. And so I've been looking into using cryptography as a tool of proving things about the supply chains of these physical products but without revealing commercially sensitive information.
</details>

### AI 对教育的影响

**主持人**: 作为老师，你如何看待 AI 对计算机科学教育的影响？

<details>
<summary>Original English</summary>
**Host**: How have you seen computer science education changing? How do you think it might change further in in the future especially as we're seeing AI u be part of industry and probably the world as well?
</details>

**马丁**: 过去计算机科学教育变化很慢，剑桥有 800 年历史，人们更关注 1930 年代奠定的基础。但 AI 彻底改变了我们评估课程作业的方式。**禁止 AI 是不可能且适得其反的**，我们希望学生能高效使用它。挑战在于，如何让学生以负责任且成熟的方式使用 AI，而不是用它来逃避学习。在学术界，产出的产物（如文章）不是重点，学生经历的思考过程和学习才是。

<details>
<summary>Original English</summary>
**Martin**: Yeah, I mean prior to AI explosion happening actually rate of change is very slow in in computer science teaching. Partly that might be Cambridge, you know, Cambridge is over 800 years old like everyone thinks on longer time scales. People don't tend to rush into the latest fad and instead try to focus on the fundamentals. That said, AI has totally changed the way we can assess coursework, for example, because of course now we we can try banning AI, but it's impossible to actually enforce such a ban. And also, it's kind of counterproductive because we do want students to engage with new technologies and figure out how to use them productively for themselves. But we want to somehow do that in a way that supports their own learning and doesn't undermine it. In academia the actual artifacts that the students produce like an essay that the students write that's not really the point. We ask them to write essays because we want them to go through a thought process which helps them learn something. And it's that thought process and that learning which is really the the desired outcome here.
</details>

### 寄语：工业界与学术界的互补

**主持人**: 最后，对于正在考虑进入工业界或学术界的年轻专业人士，你有什么建议？

<details>
<summary>Original English</summary>
**Host**: as closing for a student or a young professional who is is still studying and considering the route into either industry or academia, what have you seen uh who thrives in one or the other?
</details>

**马丁**: 我觉得这两者并不排斥。我带过一些最优秀的博士生，其实都有几年的**工业界经验**。这能给他们更广阔的视野。反之，学术界能教给人更细致和批判性的思维，去从第一性原理推导，去论证为什么某件事是真的。我希望大家能在这两者之间自由穿梭，而不是将它们视为互不相容的职业路径。

<details>
<summary>Original English</summary>
**Martin**: Yeah, my feeling is they're not really that mutually exclusive or rather some of the best PhD students uh I've worked with for example actually have a few years of industry experience. So I think having seen a bit of just real world engineering is actually really helpful for people even if they then want to stay in research. But in the opposite direction, I think it can work very well too because in in research research in academia, we just get to think things through a lot more carefully than people often do in industry. Often people in industry, I feel like sort of have short circuit reasoning. academia can teach is this sort of uh nuanced and and critical thinking um to really reason through trade-offs, for example, and to really like justify why something is true. And so i think it's really good actually if people can weave in and out of industry and academia a bit.
</details>

**主持人**: 好的，马丁，非常感谢。这次对话让我对你正在做的学术研究有了全新的好奇和敬意。

<details>
<summary>Original English</summary>
**Host**: Well, Martin, thank you very much. Uh I expected us to talk a lot more about your book which we did but I I have a newfound curiosity and and respect for all the important and interesting academic work that you and everyone else is doing. So thank you so much for this.
</details>

**马丁**: 谢谢，这是一次非常有趣的访谈。

<details>
<summary>Original English</summary>
**Martin**: Thank you for the great interview. This was really interesting.
</details>

**主持人 (结语)**: 希望你们喜欢这次与马丁·克莱普曼的难得对话。我发现有趣的一点是，书的第一版假设你有带本地磁盘的机器，而今天大多数工程师已经不再这样构建系统了。S3 等**云原生原语**改变了构建方式，这就是为什么这本书需要更新。我也很欣赏马丁关于在使用托管服务时是否仍需理解系统内部原理的看法：如果你在构建业务逻辑，可能不需要细节，但在调试时它会非常有用。最后，我非常敬佩马丁正在进行的学术研究：本地优先软件、去中心化系统的访问控制、以及用密码学验证排放。这些都是很少有初创公司会承担的艰巨工程问题。学术界在进行具有长期视角的研究方面处于优势地位。感谢收听，我们下期再见。

<details>
<summary>Original English</summary>
**Host (Outro)**: I hope you enjoyed this rare conversation with Martin Kleppmann. I found it interesting to learn that the first edition of the book assumed that you have machines with local discs. But actually today this is not how most engineers build systems anymore. cloudnative primitives like S3 change how you build systems and this is why this book just needed a refresh. I also appreciated Martin's take on whether engineers still need to undertest system internals when they're using managed services. If you're building business logic on top of these services, you probably don't need to know every detail, but it can become useful to be able to look deeper, especially when you need to debug your system. By the end of our conversation, I gained a lot of appreciation for the academic research that Martin is doing. the local first software work, the access control problem in decentralized systems, using cryptography to verify supply chain emissions. A lot of these are hard engineuring problems that few startups would take on. It was nice to understand how academia is in a good position to do work that has a long-term focus. Thanks and see you in the next one.
</details>

