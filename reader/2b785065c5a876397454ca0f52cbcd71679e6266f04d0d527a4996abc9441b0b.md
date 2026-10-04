---
author: AI Engineer
date: '2026-07-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ib5GBkD555M
speaker: AI Engineer
tags:
  - agentic-coding
  - software-factory
  - code-maintainability
  - reinforcement-learning
title: 为什么软件工厂会失败：超越 Harness 工程的智能体编码反思
summary: 本文探讨了 AI 智能体编码与自动化“软件工厂”面临的瓶颈。作者指出，仅靠增加 Token 消耗或改进 Harness 无法解决代码可维护性下降的问题，因为现有强化学习模型缺乏对设计与架构质量的评估。未来开发应将 AI 辅助前置规划与人工审查结合，以保证质量与效率。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - HumanLayer
products_models: []
media_books: []
status: evergreen
---
### 狂热与裂痕：AI编码的现实瓶颈

**中文解析**:
在当前的行业浪潮中，技术团队正竞相将 AI 编码引入生产环境。目前流行的叙事逻辑认为，我们应当无限制地进行 Token 消耗，因为“代码是免费的”，人类才是唯一的生产力瓶颈。甚至有公司如 **StrongDM** 尝试构建完全无需人工阅读代码的“无人值守软件工厂”，试图借此实现百倍的效率提升并彻底消灭代码审查。然而，这种盲目追求规模与速度的模式正暴露出严重的裂痕。行业观察表明，由于编码智能体失误导致的系统故障频发，代码库正以前所未有的速度崩溃。来自 **Faros AI** 的数据指出，自行业大规模引入 AI 编码工具以来，拉取请求的审查质量大幅下降，大量 PR 在未经任何审查的情况下被直接合并，导致每个开发者产生的 Bug 数量和线上事故率急剧攀升。

<details>
<summary>Original English</summary>

We're all racing to put AI coding into production and there's been lots been said about loop engineering and we should probably write more loops and yeah, I don't know, I guess we're doing loops now. StrongDM built a lights-off software factory where nobody even reads the code and the prevailing narrative is we should just spend more tokens. You are the bottleneck. The models are good enough. Code is free. Just ship more stuff. But at the same time, we are starting to see the cracks. Our friend Mario at AI Engineer Europe begged us to slow down because companies that should not be having outages because of coding agents are having outages due to coding agent mishaps. Code bases are falling apart faster than they ever have before. And our friends at Faros AI actually even did a report since we all picked up all these AI coding tools in January, maybe February. Pull request code review quality is way down. We're having more comments, longer comments, and tons of PRs being merged without any review at all. Incidents are way up, bugs per developer are way up. And many people will tell you that you're holding it wrong. That's the only reason. You're not. Well, maybe you are, but that's not the point.
</details>

### Harness局限：无法根治训练缺陷

**中文解析**:
面对智能体编码屡屡犯错的现状，许多人认为这只是“使用技巧问题”，主张通过 **Token 最大化**（Token Maxing: 通过增加 Token 消耗和多轮提示来强行解决问题）或精细的 **Harness 工程**（Harness Engineering: 围绕模型构建的脚手架、沙箱及调用循环工程）来解决。例如在 PR 机器人中添加所谓的“对抗性审查”等指令。但事实上，无论如何包装 Harness 或增加执行循环，都无法根治这个本质上属于模型训练维度的缺陷。要理解这一点，必须深入探讨编码模型的训练机制。现有的代码模型虽然在工具调用和单次执行上表现出色，但由于底层的强化学习缺乏对代码架构和长效维护性的评估，导致外部的工程包装无法越过模型能力的鸿沟。

<details>
<summary>Original English</summary>

I've spoken a lot about how to hold it better when it comes to working with AI, probably a million views on YouTube at this point across a bunch of different talks. And the basic thing is like as engineers we've been told that if token maxing isn't working then it's a skill issue. You just need to spend more tokens, let go of reading the code. That with enough harness engineering, if we maybe sprinkle some magic words adversarial review on enough of our PR bots that we can get the best of both worlds, 10 to 100x faster, high quality, and nobody has to do that thing we all hate called code review. I'm here to convince you today that this is in fact not a scale issue. That no amount of harness engineering or loops maxing can solve what is fundamentally a model training issue. That's why we say the harness is not enough. And to understand this, we kind of have to grapple and dig into how coding models are trained.
</details>

### 演进与失控：无人值守的软件工厂

**中文解析**:
回顾 **软件工厂**（Software Factory: 系统化、工业化的软件生产体系）的历史，在 2022 年 AI 爆发前，典型的开发流程依赖于产品经理、工程师和领导层的协同。任务被记录在 Linear 或 Jira 等状态机中，由人工进行编码、测试，再通过代码审查和自动化检查流向生产环境。为了降低返工率，团队会提前进行大量的技术方案规划和设计对齐。而进入智能体时代后，这一流程中的“人工编码”被“智能体编码”取代，执行时间从几天缩短至几分钟。然而，随之而来的是代码审查和测试环节成为新的瓶颈。为了追求极致的速度，一些团队选择走向“无人值守软件工厂”，完全放弃代码审查，仅依赖监控与自动化回滚。这种对代码可维护性的放弃，最终会导致代码库质量失控，当智能体遇到无法解决的逻辑死锁时，开发者不得不重新面对已经无人能懂的代码泥潭。

<details>
<summary>Original English</summary>

I want to give you kind of like a brief history of the software factory. The term software factory was defined at a NATO conference in 1968. We're going to start around 2022, like right before AI started coming around. And basically in a typical 2022 software factory, you will have some people building stuff. You'll have engineers, you'll have PMs, maybe you have some sort of leadership team that is driving the vision here and they all decide that stuff needs to get done. And so you put it in a tracker, a Linear, a Jira, some sort of state machine that tracks what needs to be done. And then someone goes and grabs something off of there and they build the thing. And there may be some automated testing in that process, maybe some manual testing in that process. At a certain point, we make this pull request thing that says, "Okay, cool. We got to run a bunch of checks, automated stuff. A human's going to review the change and review the code. And perhaps we might even have a human pull it down and test it somehow. And if anything goes wrong here, we loop back to someone builds the thing." Uh, and eventually we're ready for prod, and so we ship it to production. And once it's in prod, it makes contact with our users. And users love to complain. They're going to ask for things, they're going to find bugs, they're going to file feature requests. And that goes back to your team. You might also add monitoring, and so you know, we want to wake up engineers at 3 in the morning when something breaks so they can get dragged out of bed to try to go fix it. And we go on and on in this loop and we ship a bunch of code.

And one thing that we noticed here is that teams figured this out decades ago is that this someone builds the thing step is usually going to take hours or days in most cases. And the review part will also take hours or days for large things. And so teams started doing these upfront planning, architecture, proposals, sprint planning, and they would collaborate on these things as a team with the hopes that we might decrease the percent chance that something would need to be reworked, that we would be able to reduce the time spent in reviewing every line of code because we aligned on everything ahead of time.

This brings us to the agentic software factory. Every company and their mother is talking about how they built a coding agent factory that ships 75% of their code. Now literally everybody. And so if we look at the software factory from 2022, we just replace someone builds the thing with an agent builds the thing. And we have an orchestration and a harness and a sandbox and a model and computer use, I'm not going to get into the details of that. But now the building part takes minutes or hours, but this human part still takes hours or days if you're going to review the code and you're going to test the changes. And so we bring in agentic code review and we bring in agentic regression testing, and it makes this part faster, but it's probably still the bottleneck. But we can do more loops here. Why not? Let's do some more loops. So, we can route all incidents straight into the factory. Why does someone need to get woken up and try to fix it when they could just wake up to a pull request and maybe that fixes the issue for you? You can take all the user feedback and just stick it straight into the factory so that people ask for stuff and it gets built. And now your only job is how much things can you stuff into the queue of stuff to do and how fast can you review and test the changes.

Which brings us of course to the lights off software factory where basically Dan Shapiro coined this is we no longer read the code. We say you know what this is going great, that code review thing, no thanks. We're just not going to do that anymore. And we invest into all these other parts of the system, your testing, your monitoring, your rollout, everything else. We just write more code and build those systems better. And now our job really is just how much stuff can we ask the agent to build. I am going to pause, that does not work. And this is why software factories fail.
</details>

### 强化学习盲区：设计质量难以评估

**中文解析**:
AI 智能体在面对维护周期超过 3 到 6 个月的代码库，即 **棕地系统**（Brownfield System: 存在历史技术债务和既有架构约束的代码库）时会开始挣扎。其根本原因在于强化学习在代码生成训练中的局限性。以 **SWE-bench** 等主流基准测试为例，它们的奖励信号是二元的：即运行测试，如果新旧测试全部通过则获得奖励，否则为零。在这种机制下，模型唯一的动力就是“让测试通过”，这导致了严重的 **散弹式手术**（Shotgun Surgery: 指为了实现单一变更而不得不对多处代码进行零碎修改的代码坏味道）倾向。模型会写出毫无必要且杂乱的 `try-catch` 块，或者进行生硬的类型强转，完全破坏了软件设计的健壮性。因为低劣的代码设计和逐渐流失的 **代码可维护性**（Code Maintainability: 代码易于阅读、修改且不易引入新 Bug 的特性）在几分钟的测试运行中是无法被评估和惩罚的，其恶果往往在数月或数年后才会显现。这种滞后的反馈循环使得我们很难将正确的奖励信号回传给模型。

<details>
<summary>Original English</summary>

At HumanLayer what we care about is how do we help people solve hard problems in complex codebases. We use the word brownfield a lot, which historically has meant like some 10-year-old Java thing. I actually think agents really start to struggle after maybe 3 to 6 months, especially with the pace at which we can ship now. In July 2025, we tried this. We went full lights off, and if you have tried this seriously for a number of months, you probably found at least one issue that the agent couldn't solve even with your most advanced prompting. You do research, you do reproductions, you just have to go and dig into that codebase that you stopped reading three months ago to try to figure out what's broken. And in the meantime, your site was down, your users were pissed, and you were, if you were like me, you were probably miserable reading all this slop code that you let slip into your system.

And what I want to get to is basically models have a shortcoming. They can't maintain and improve codebase quality over time, not without a decent amount of human steering. And when I say maintainability, I'm basically talking about issues like it becomes really really hard to make a change in one part of the codebase without breaking other parts of the codebase. This is Martin Fowler shotgun surgery textbook code smell.

But it brings us to this question of like why can't models do software maintainability. If you want to solve one-off problems or vibe code a new marketing site, yes, they got way better since 2025 and 2024, but as far as improving codebase quality, I think they have not gotten much better. Now, I cannot prove this because there are no good benchmarks for a model's ability to maintain codebase quality. But if you've worked with coding agents for a while, a lot of people are posting about this, it's just like you probably have this vibe that they generally make things worse over time and make the codebase harder to work in.

Why did Cloud Code go from nothing to four billion, and now they're at nine billion in revenue in under a year? Because they were the first time that a model lab trained a model against the harness that they were going to distribute it to users in. And it got really really good at calling these sorts of tools in an agentic loop. But LLMs are just next token predictors. Let's see if we can do coding agent reinforcement learning in 60 seconds. So, what we're going to do if we want to train a model to get better at tool calling, better at solving software problems. We're going to give it a problem and we're going to generate a bunch of traces, try to solve the problem a bunch of different times. We're going to score them all on correctness and did the test pass and all this stuff. And then we're going to reinforce. We're going to make the bad behavior less likely, and we're going to update the weights to make the good behavior more likely.

One of the classic benchmarks here is SWE-bench. They're about 15-minute tasks from open source repos. And they have binary one or zero rewards on did you fix the problem you were trying to fix and did you do it without breaking anything else. We have the agent go try to solve the problem. We store its patch, we undo all the changes it made to any test files because models comment out tests just to get things working. And then we're going to apply our golden test patch, and then we're going to run the test, and did the new test pass. And if they both pass then we get the reward otherwise we don't. And so models are trying to get the test to pass. There's no way in this system that we can penalize it for poor program design or for eroding the maintainability of our systems. That's why we get things like this try catches around things that probably don't need a try catch or casting things to other things just so the model can just get the test to pass. And so if you can't verify the maintainability of the code, it gets way harder to train on this stuff.

Verifying code quality and maintainability is orders of magnitude harder than the code runs and the test pass because the cost function of bad architecture is measured in months and years. If you have a coding episode and then you only find out months later that somebody vied this a little bit too hard. It's really hard to propagate that reward signal back across the gap.
</details>

### 评测新边界：探索代码可维护性

**中文解析**:
随着前沿代码能力的演进，如何科学评估代码的可维护性正成为新的焦点。尽管现有的评测与验证器有所不同，但其本质架构类似。目前行业正涌现出如 Abundant AI 推出的 **SWE Marathon**（包含克隆 Excel 所有功能的 400 小时超长复杂任务，配备复杂的奖励通道）、DataCurve 提出的 **DeepSuite**（利用真实世界中从未存在过的开源仓库任务以防模型作弊），以及 Cognition 推出的 **Frontier Code**（通过惩罚未致使旧代码失败的测试用例并引入裁判模型来严格把关代码规范）。然而，单纯依靠模型自身来充当裁判仍有其天然的局限性：如果模型本身就懂得什么是优秀的代码设计，它在第一步编写时就会直接写出好代码。因此，虽然审查智能体和增加 Token 可以拉高代码质量的底线，但目前我们依然无法脱离人工阅读和理解代码的阶段。

<details>
<summary>Original English</summary>

And now the frontier is getting better slowly. And since I know someone's going to be in the YouTube comments about this, yes, I know benchmarks and verifiers are different and they actually have to be separate data sets, but they're shaped the same and the structure of these benchmarks is directionally correct. So, we're going to look at these as like what is the future of evaluating code maintainability.

Um, there's a really cool one called SWE Marathon from Abundant AI where they do like 400-hour tasks of like clone all of Microsoft Excel, every single feature. And they have some sophisticated reward channel stuff. Deep Suite from Data Curve is also like large tasks on OSS repos that are not actually in the training set because they were never actually built in the real world. And then you have Frontier Code from Cognition which is multi-PR tasks. They do interesting things like hey if the model writes tests that don't fail on the pre-patch code then it gets penalized and we have a judge model that says okay did this follow all of our code quality rules.

Um, so we're getting better, but I think models judging quality can only go so far. Because if the model knew what good code looks like, it would probably write it in the first place. And review agents and throwing more tokens at the problem, it can raise the floor. Um, but we're still constrained by what we can teach during RL. And so I will posit that for now we're stuck reading the code. Uh, but we can still move pretty fast. And of course there's a world where this is solved in the future. And if you want to just keep yoloing prompts until you get to GPT-7, you don't have to think about this. By all means, please. But bitter lesson be damned. We've got some problems to solve. So, let's engineer our way out of this.
</details>

### 前置规划对齐：实现高效AI开发

**中文解析**:
为了在确保代码库自主权的同时大幅提升开发效率，我们必须将代码审查重新纳为核心流程，并采用 **模型辅助规划与对齐**（Model-Assisted Planning and Alignment: 利用 AI 辅助收集上下文并制定方案，在编码前通过前置沟通消除设计分歧的机制）。该方法倡导在编码执行前进行 30 分钟的前置规划，通过以下四个维度与 AI 深度对齐：
* **产品审查 (Product Review)**: 梳理业务痛点与期望行为，对齐原型设计；
* **系统架构 (System Architecture)**: 规范组件契约、数据模型及系统级约束；
* **程序设计 (Program Design)**: 明确方法签名、类型定义及调用栈结构（如借助调用图规划调用路径）；
* **垂直切片 (Vertical Slices)**: 拆解跨仓库的开发顺序，定义每个阶段的测试验证点。

提前进行这 30 分钟的对齐，能够消除大批因盲目编写而产生的糟糕 PR。因为一个优秀的 PR 本身应当逻辑严密且符合预期，使审查成为一种愉快的确认过程。即使是一个仅需 20% 重构的“AI Slop”代码，也会给审查者带来巨大的脑力负担。通过前置规划，AI 能快速整理上下文以缩短对齐时间，前置对齐能显著加快后续代码审查，而实际的代码实现则交给 AI 高速执行。这种模式让团队在真正掌控代码主权的前提下，实现了开发速度的爆发。

<details>
<summary>Original English</summary>

So, let's engineer our way out of this. So turning the lights back on, we're going to put the code review back. We're going to embrace this approach of like how do we plan up front to reduce the chance that we have a long or difficult review process. We're going to find leverage. We're going to use AI to help with this.

The first thing we're going to do is we're going to do some sort of product review. Understanding what problem we're solving, what's the desired behavior, maybe looking at mockups. Here's a product review I was working on yesterday with a mockup of a new feature. Once we have our product review, we're going to also do architecture, system architecture. A lot of people have been doing this for a while. Component contracts, data models, constraints. This is an example of a doc that we build to understand how these systems are going to fit together and what's like the high-level picture of it. From there, we do something that I think is really underemphasized in agentic coding these days, which is program design. I think people assume that once you get the architecture right, the model can just cook. But we often look into the types and the method signatures, the program layout and the call stacks. Dylan Mullroy from Cloudflare talks a lot about how he's using these call graphs as part of his planning process. I think this is exactly right. And then once we've done the program design, we can do this thing called vertical slices, which is the order of implementation, multi-repo coordination. How are we going to build this across our entire system and how are we going to check it along the way? If you want to learn more about this, you can go watch our talk from AI Engineer Miami. The main idea here is 30 minutes over here in pre-planning and alignment can save you hours in review and so it's actually feasible to still read every line of code.

Basically the summary here is like you don't have too many PRs. If you're drowning in PRs, you actually have too many bad PRs. Because a good PR is a joy to review. It's you're just reading through like, "Yep, this is great. This is what we discussed. This is what we talked about." But even if a PR needs 20% rework, which is generous for a lot of AI vibe-coded slop, it's an emotional and intellectual burden on both the reviewer and the submitter. And so if you use model-assisted planning and alignment, your alignment is shorter because you use AI to get all the information at once, your code review is faster because you aligned up front, and your coding is faster because AI did it. And so now you're actually really moving faster, but you're still reading everything and you're still owning the code.

Closing advice: it's easy to hear all this and be a little bummed out. I really like the world where we just yolo everything and we can just like not have to ever read code ever again. But we're engineers and these are just constraints and models are good at certain things and they're not good at other things. And so go figure out how to solve problems given a set of constraints. Use loops. They're great. Go solve hard problems. Seek leverage.

If you want to help with this, we're building HumanLayer. HumanLayer is an AI IDE and collaboration platform. It's building blocks for your software factory and soon to be better verifiers for software quality. We've got sort of a Figma for cloud code and collaborative workspace. It walks you through the workflows for doing this sort of work. And we are talking to design partners. We are hiring founding engineers here in San Francisco. And these slides are live. You can go get them right now. You can try HumanLayer at humanlayer.com. It's free for small teams. Go solve hard problems in complex codebases. Thank you all for your energy.
</details>