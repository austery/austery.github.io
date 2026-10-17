---
author: AI Engineer
date: '2026-07-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bRnoEpoK5m4
speaker: AI Engineer
tags:
  - adaptive-software
  - software-distribution
  - continuous-integration
  - runtime-adaptation
title: 流水线已死：自适应软件与软件分发的新纪元
summary: 本文探讨了传统软件分发流水线（CI/CD、冻结制品等）在 AI 时代下的消亡。随着软件生产成本骤降，开发与分发的边界正趋于模糊。未来软件将从“一人一版本”的冰封制品模式，演变为以“主干与分叉”为核心的实时自适应架构，在确保系统安全隔离的同时，为每个用户定制最适合的版本。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Differ
  - JFrog
products_models:
  - Excel
media_books: []
status: evergreen
---
### 冰封制品的终结与分发假设的动摇

在现代软件工程中，**CI/CD 流水线**（Continuous Integration/Continuous Deployment）、打包器、注册表、容器镜像以及应用商店审核等整套基础设施，其核心目的均在于解决同一个问题：将一个在构建端生成的、不可变的**冻结制品**（Frozen Artifact: 构建完成后不再更改的软件二进制或代码包），安全、可复现地分发到运行它的机器上。然而，这套庞大的体系建立在一个非常古老的假设之上，以至于我们早已将其视为理所当然，那就是：“所有人使用同一个版本的软件”。这种单版本分发模式并不是凭空产生的，它是软件生产成本高昂且伴随高风险的直接产物。在过去，由专业工程师编写、测试并确认一段正确的代码更改需要数小时甚至数天，因为代价昂贵，所以我们倾向于极少改动、集中验证、锁定版本，然后统一分发。

尽管冻结制品带来了可复现性、可预览性和回滚等诸多保障，并被我们冠以“可靠性”的美名，但它的代价是软件无法真正为特定的个人而设计。在此之前，我们从未在“一人一版本”和“统一版本”之间做过理性辩论，因为在当时，为每个用户维护独立的分叉代码库在经济和人力上是完全不可行的。然而，这个关于成本与预算的经济学底层逻辑在今天已经彻底改变。

<details>
<summary>Original English</summary>

As we're online today, you can't raise your hands, but just nod at your screen. How many of you have spent a significant part of your career making making software move from one computer to another? CI pipelines, packagers, registries, container images, app store reviews. That entire stack exists to solve exactly one problem. Get a frozen artifact, that code, from machine where it was built to the machine where it runs, safely, reproducibly, once. And here's what I think everyone is missing. That entire stack is built around one idea that is so old that is so old that we stopped seeing it as a choice. One version of your software for everyone. We've shipped it that way for so long that almost nobody asks why anymore.

I'm Iris. I'm one of the co-founders of **Differ**. My co-founder Noam was the first engineer at **JFrog**. He helped build the pipeline that I'm about to tell you is dying. I came at it from the other end. I spent a decade in fintech. I was early at a digital bank that we scaled and exited. Shipping software in the environments least willing to tolerate what I'm about to propose. So, I totally get any reservations and I've had them myself as well. However, I'm telling you it's coming anyway. And that's not a warning. It's the best thing that's happened to software in a long time.

Every piece of distribution infrastructure that you've touched encodes the same assumption. Software is produced in one place. It runs in another. Anything in the middle, the artifact, is frozen. And that assumption was correct. For decades, it was just true. Why? Because producing a correct change was expensive. It took skilled humans hours or days. So, you did it rarely. It was a central event. You verified it and froze it. And you shipped that frozen thing to everyone. So, the one-way pipeline is not arbitrary. It's the direct consequence of production of software being expensive and risky. And of course, the frozen artifact has some advantages. You get reproducibility, previewability, rollback. And every guarantee that we lean on in production flows from one fact. There is one artifact and it doesn't change after we ship it. That's the deal. One version for everyone, frozen. We call it reliability.

</details>

---

### 边际成本坍塌与实时自适应架构

如今，生成正确且符合预期作用域的代码更改的成本正在迅速逼近于零。更重要的是，软件的生产不再需要提前在中央服务器一次性完成，它可以发生在服务器端、客户端，甚至是用户当前的实时会话中。当软件的修改成本变得和运行成本一样廉价时，曾经将开发与分发硬性剥离的边界开始消融。事实上，用户对个性化软件的需求已经存在了数十年：企业级软件中的专业服务（例如 **Salesforce** 繁复的定制化咨询）、工程师个人对编辑器配置与快捷键（Dotfiles）的执着，以及史上最成功的商业软件 **Excel** —— 它本质上就是数百万用户在静态程序上构建的个性化专属程序。过去我们不得不使用功能开关、用户分群或 A/B 测试来模拟这种分发差异，但这需要提前声明和规划用户组。

如今，借助更强大的 AI 编码智能体，我们可以在软件层真正实现**自适应软件**（Adaptive Software: 能够根据用户环境、行为及需求实时自动调整自身功能与界面的软件）。我们押注的未来架构不再是一个被各种功能开关门控的臃肿代码库，而是：开发者部署一个**主干代码**（Canonical Stem: 软件的共享核心逻辑），而每个用户在运行过程中产生自己的**实时分叉**（Live Divergences: 基于主干为单用户动态生成的隔离分支逻辑）。软件从服务于每个人的“最小公分母”，变成了针对特定个体的“最佳定制版”。

<details>
<summary>Original English</summary>

But the price was that the software couldn't really be for anyone in particular. And nobody ever made that decision. There was never a meeting where someone put one version for everyone versus a version for each person and picked the first one. And it wasn't because the second option of a version for each person was worse. It just wasn't an option. Giving to users different software meant forking the code base and hand maintaining both. A version per user at any real scale wasn't really a viable option. And one version for everyone never had to win an argument. It was just how it was. It was the only shape software could take. And we started treating it as a fact about software like gravity, like something that that is just true. But it was never really a fact about software. It was a fact about cost and budget and the economics and that cost just changed. 

Now, you might you might expect me to go into AI and code, but everyone has already said it and that's stable stakes and to me that's not really the interesting part. The interesting part is where and how cheap. The cost of producing a correct and scope change is collapsing towards zero and just as importantly the production of the software no longer has to happen in one place up front before anyone runs it. Part of it can be run on the server, part of it on the client, part in the user's live session. And as each step stops being a decision you freeze at build time and now starts becoming more of a real-time one that also means that each each each piece can be placed wherever it makes most sense including right in front of the user in their context.

And so this whole one-way pipeline existed because making software was the expensive, central, and rare event and running it was cheap. So you separated development from distribution. But now as making a change becomes as cheap as running one and it can happen in the same place as where you run it, the reason to separate them is dissolving. 

So far I've talked about the supply side. Producing code has become cheap easy. We can now make a change on a per user basis. But I also want to address the demand side. People have always wanted software that fits them and we have decades of proof for that. It just wasn't really possible for most types of software because of cost. To start with one example, the forward deployed engineer. Enterprise software has always had a line item called professional services and a whole industry exists around that. If you are a big client of a company like Salesforce, you probably have consultants that are helping you implement custom setups, configurations. You have an engineer living in your Slack channel, and it's not that smaller customers can't benefit from this type of customization. It just didn't make sense financially until today. To give another example that might resonate with you as engineers, think about your dot files, your editor config, key bindings. You rebuild every tool you touch into your tool by hand on every machine. It's another example of a demand for personalized software. And lastly, Excel, the most successful business software ever created. And Excel isn't really a static program. It's millions of people that all build their own programs on top of it. So, that's where. Give people the power to make software to make their software theirs, and they take it. Seen in the social feed that per user wins on wins from one size fits all on every metric that mattered. This is more of an example of content versus software. But now that we have better coding again now we have coding agents and better coding agents, we can move this also to the software layer. 

So, my point is none of this is really new demand. We've seen it for decades. There have been predecessors like feature flags, segmentation, AB testing. There's an enormous industry around this, and we've been trying to make software diverge for many years. But we got forced into a specific shape, that of creating buckets and segments that you declare in advance. And now, for the first time, we can make software truly adaptive. So, to get back to the title of this talk, when the agent is the runtime, when the thing that runs your software can also modify it, development and distribution stop being two phases. The boundary blurs and it's gone. And the shape that we bet on at Differ is that instead of one code base gated by flags and shipped to everyone, you deploy one canonical stem and every user runs her own divergence of it. Same origin, but individually adapted live. It's going from the least first version for everyone to the best version for anyone.

</details>

---

### 控制爆炸半径：应对失控分叉的工程实践

许多管理者在面对这一设想时，直觉上会产生强烈的排斥。正如一位首席技术官（CTO）所提出的合理质疑：“我现在连维护一个 AI 生成的代码库都觉得费劲，你居然要我运行数百万个不同的版本？这简直是把我的噩梦放大了无数倍。”这种对不确定性的担忧是正确的，但它针对的失败模式有误。人们脑海中浮现的脆弱性，其实是单个代码包内部未加管理的混乱分叉——即文件冗长、边界模糊、代码耦合。

在主干与分叉的自适应架构中，事情恰恰相反。系统会将**爆炸半径**（Blast Radius: 故障发生时受影响的系统或用户范围）严格限制在单一用户的会话上下文中。每个用户的分叉修改是彼此隔离的，且是实时可逆的——坏的变体可以立刻静默回滚，不会污染主干，也不会波及其他用户。此外，开发者依然拥有绝对的控制权，能够设立刚性边界以指定哪些部分绝对不可被 AI 修改。例如，像身份验证（Auth）或支付（Payments）这样的敏感模块应始终被排除在自适应范围之外；而像前端的转化率表单，则可以允许 AI 动态调整。例如，CRM 系统的 AI 能够观察到某位投资人用户高频记录创始人引荐路径（Intro Path），并经常跳过不填的销售字段，进而自动重构表单界面以凸显核心数据，无需让开发者重新参与研发。

<details>
<summary>Original English</summary>

Now, if you're any of such a person, you might be a little worried. Your stomach might be turning because I have just deleted the frozen artifact and the frozen artifact was what was holding up the entire the the entire building. And I do we do get these objections, for example, from a call that I had with a CTO recently who is right to be skeptical. What he said roughly was, "I can already barely reason about one AI-generated code base. And you want me to run millions of these? You're not describing a capability. You're describing my worst problem multiplied." And if that's your reaction, that's not surprising. It's the right instinct, but perhaps aimed at the wrong target.

Here's the distinction that we make. The brittleness that you're picturing is a specific type of failure mode. It's unmanaged divergence inside a single artifact. Thousand-line files, everything can touch everything else, no boundaries. And that's not not that's not necessarily brittle because it's AI-generated. It's brittle because there's no structure separating things. In our In our vision, we've we're thinking about per-user divergences. And don't write that is the opposite of that. You've got a stem plus divergences. The divergences are bounded, isolated, and individually reversible. A bad variant can silently corrupt the stem or reach another user. Which means that the blast radius of a changes in the system is one context. And any single divergence can roll back live with no deploy. So, the answer to the previous objection isn't trust us, AI is good at coordination or coding. The honest answer is you're brittle because there's a tangled artifact with no boundaries. In our case, we don't ship you a thousand single artifacts. We ship one stem and bounded divergences. Each isolated, each reversible. The thing that you're afraid of is the thing that this architecture exists to prevent.

And as a developer, you can also set controls and boundaries. What can and cannot be adapted. To give a small example, um we can have a scenario where we've got a form and the form can be adapted in order to improve conversion rate, for example. However, as a developer, you can always indicate that specific fields can never be dropped or parts of your app, like off or payments, should always be out of um uh uh should always be off limits for any sort of adaptation. To give another example to make adaptive software a bit more concrete. Uh think of, for example, um a CRM. In this case, uh we've got an investor who's using a CRM. Whereas, the CRM was mostly built with a salesperson in mind. And as an investor, you might use it slightly differently. So, this investor, she often logs founder intros, and she's always logging who intro'd her to which deal. So, the system observes that and creates a um create creates a intro path. The system can also observe that she's always skipping specific fields. She never fills them out. So, over time, the system learns and doesn't surface those fields, but instead it surfaces fields that she that she cares about more. Another example can be the fact that she is always um always checking specific types of deals or founders, and it doesn't exactly follow the prioritization that the system sets by default. So, again, can can we learn and make that smarter so that the information that the user cares about is surfaced first. Not only can a system observe, but there is also that the user can proactively request changes, and as long as these changes are within the boundaries that the developer sets, and as long as they are within the spirit of the software, within the purpose of what the software was originally made for, it can be implemented without having to go back to the developer. So, you can imagine for a for a horizontal SaaS like a CRM, you can address a much wider number of customer personas without increasing your R&D spend.

</details>

---

### 规模化自适应软件面临的五大工程挑战

将这一全新概念推向实际生产环境，面临着极其复杂的底层工程挑战。我们在实践中将其总结为五个维度：

* **真理源与血缘关系 (Source of Truth & Lineage)**：当没有了单一的物理二进制文件时，什么是软件？它变成了“主干逻辑加上所有不可变分叉的图谱”。若要诊断一个特定的 Bug，我们需要通过图谱查询该用户正在运行哪一部分分叉代码、为什么生成，并且能够将每一段动态修改精确溯源到产生该推荐的上下文信号。
* **正确性与测试 (Correctness & Testing)**：在拥有海量不同用户自适应变体的环境下，我们无法进行传统的单元测试。我们必须设计出新的测试理论，能够在大规模发散的运行期，同时对主干和所有可能的分叉状态进行正确性推理与安全验证。
* **期望度与业务指标 (Desirability & Metrics)**：即便代码逻辑和 UI 生成在技术上完全正确，我们还必须衡量这种改变是否“令人期望”。也就是说，这次动态调整是否真正带来了业务指标上的提升。我们需要在系统底层建立精细的监测机制，追踪不同用户的流失率、支持工单数量以及转化率，以验证自适应机制是否切实赋能了业务目标。
* **自主性与控制力 (Autonomy vs. Control)**：最保守的做法是让 AI 只做修改建议，由开发者或用户确认。但这并非终极愿景。我们追求的是系统能够深度理解用户意图，从而无需每次都征得开发者许可便直接生效。工程上的难点在于，如何将系统的 legible（易读性）、可靠性提升到让身处闭环中的人类心甘情愿退居幕后的程度。
* **协同与传播 (Coordination & Propagation)**：如果每个人都在运行不同的版本，当开发者向主干推送新代码或功能升级时，如何确保这些更新能正确且无缝地同步到数百万个各不相同的用户变体中？答案是“不合并代码，只合并意图与结果”。不强制所有人运行完全一致的提交（Commit），而是通过各自独立的路径汇聚到相同的业务目标。

在这些挑战中，让大语言模型（LLM）去生成代码只是最初步的“前 80%”，而可观测性、运行时校验、可信度以及协同传播，才是定义整套自适应软件平台的底层基石，也是最具挑战性、最难攻克的关键业务所在。

<details>
<summary>Original English</summary>

Now, of course, there is there are many hard parts when it comes to bringing this to life. And I'm going to discuss a couple of hard challenges and problem and problems that we're uh that we're working on as we're making adaptive software real at scale. We haven't solved all of them, but we have a we have a point of view on each of them, and it's that it's exactly what we're working on day in, day out. So, what changes when there's no single artifact? 

Firstly, the source of truth. So, what when there's no single artifact, you can wonder what is the software? In our case, we consider the software to be the stem plus the plus all the mutual immutable divergences. But of course, that creates a lineage problem. What is this user running and why? That now becomes more of a graph query versus a version number. A bug report describes a program that exists for that specific user. How do you debug or inspect that? The answer is every divergence is immutable, inspectable, attributable. And we also need to trace any version back to the signal that to this specific recommendation and this exact adaptation. That's one of the parts that we're working on. 

Second is correctness. Like how do you test that's the um how do you test that the code change that you've just implemented works, that UI is correct, and yeah, testing at a much larger scale of users means that you need to reason about the stem and also every possible divergence of it. 

And then there's desirability because perhaps you made a code change, it's perfectly correct and working, but you also need to know that whether whether this was desirable. Was it actually a good change? Because anyone can make a code change now, but the hard part is knowing whether you actually found an improvement, an uplift. And yeah, that that is something that is extremely important to to keep track of and to measure and to consider what the goals for the company are. And this is not going to be the same for every single piece of software. In some cases, it might be retention or less churn or lowering the number of support tickets. So, it's extremely important to keep track of what are what are the goals that we're chasing with adaptive software and do the adaptations reach to improve improve improve the metrics that matter. 

Next is autonomy versus control. And the conservative answer here would be start with just recommendations and don't make any autonomous changes. And that's not a wrong strategy, but in our case, it's not really our vision. The vision is a system that understands the user well enough to act without asking the developer for permission every time first. So, for us, the challenge isn't building more control. It's winning enough trust that you don't have to. And it's a hard problem, but also also very interesting one. And you know, how do you make a system good enough, legible enough, reliable enough that humans in the loop choose to step back. And that's certainly what we are building towards. 

And lastly, coordination. Everyone on their own version, how do you push new updates? How do how do changes propagate to like a million different versions? And this is one of the challenges that we've been thinking hardest about. Yeah, and the answer that we keep coming back to is don't merge code, merge intent, merge outcome. Which means not everyone has to run the same commit or this exact same piece of code, but everyone converges on the same goal through their own path. 

If it wasn't already clear, the challenges that I just addressed are the hard challenges. Generation has become easy, and I would say that's actually the easy 80%. Calling a model to write some code is something that everyone can do. The other part, observability, validation, coordination, that is the entire business. Anyone can call an LM, but the substrate is stem plus diver plus divergences, provenance, validation, that is really the hard part, and something that we're working on every single day.

</details>

---

### 展望未来：重塑软件分发的下个二十年

回顾历史，技术范式的演进轨迹总是惊人地相似。十多年前在金融科技领域，建立一家“没有实体网点”的银行在当时被广泛认为是鲁莽和不可思议的，而如今，拥有物理营业网点反而成为了罕见的异类。同样地，在构建软件工程流水线的最初阶段，Noam 也曾需要不断说服研发人员，解释为什么我们必须引入统一构建（Build）和持续集成（CI）。这些变革在尘埃落定前总是让人难以置信，但随后面临的则是全行业的常态化重组。

传统的单向流水线并没有“坏掉”，它依然运作良好，只不过促使它诞生的底层约束——“生成代码是稀缺且昂贵的”——已经不复存在。当实时改写代码变得和运行代码一样便宜时，分发与开发之间的楚河汉界也就失去了存在的意义。在过去的二十年里，我们致力于将“如何完美分发同一个版本给所有人”这一技能打磨到了极致。而在接下来的二十年里，我们的使命则是通过安全隔离和清晰的溯源机制，以一种可控而非令人恐惧的方式，将最精确的专属版本交付到每个人的手中。

<details>
<summary>Original English</summary>

To close off with, when I started out in fintech, a bank with no branches sounded reckless. A decade later, the the branch is the weird part. My co-founder, Noam, used to fight with engineers about why you need builds and CI. We've seen this We've seen these shifts before, and adaptive software is the same type of shift. It doesn't feel obvious until it does. To go back to the start of the talk, the pipeline didn't fail because it didn't work anymore, but the constraint it was built for went away. The assumption underlying of that software is expensive, so we need to freeze it and ship it once. That assumption stopped being true. And when making software get as cheap as running it, the line between distribution and development isn't a line anymore. We spent 20 years getting good at shipping one version for everyone. The next 20 years are about shipping the right version to anyone with the isolation and provenance that makes it safe instead of terrifying. I'm Iris, this is Different and that's what we're building. Thank you for watching.

</details>