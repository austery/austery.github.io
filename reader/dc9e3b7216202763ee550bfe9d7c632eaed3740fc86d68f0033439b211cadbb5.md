---
author: AI Engineer
date: '2026-05-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=W76woOYHlvY
speaker: AI Engineer
tags:
  - ai-agents
  - software-engineering
  - developer-productivity
  - agentic-workflow
  - startup-strategy
title: 软件工程的范式演变：从‘编写代码’转向‘计划与审查’
summary: Vibe Kanban 创始人 Louis Knight-Webb 探讨了 AI 时代软件工程师角色的本质转变。随着智能体（Agents）能力的增强，编码时间正被极度压缩，工程师的工作重心已转向前置的高质量计划与后置的深度审查。 Louis 结合自身创业经验，分享了如何管理多线程智能体工作流，并现场演示了用自己的 AI 产品关闭公司的过程，深刻剖析了 AI 辅助开发的未来趋势与商业现实。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Louis Knight-Webb
companies_orgs:
  - Vibe Canvas
  - OpenAI
  - AI Tinkers
products_models:
  - GitHub Copilot
  - Cursor
  - Claude Code
  - Codex
media_books: []
status: evergreen
---
### 角色重塑：从编码者到计划与审查官

Louis Knight-Webb（Vibe Canvas 创始人及 AI Tinkers 伦敦分会发起人）提出了一个核心论点：随着 AI 能力的飞速提升，**软件工程师**（Software Engineer: 传统的代码编写者）的日常工作正演变为单纯的“计划（Plan）”与“审查（Review）”。Louis 曾带领团队在 SweeBench 验证榜单上超越 OpenAI，他的研究表明，软件开发的工作流比例正在发生剧烈变化。

在 GitHub Copilot 出现之前，工程师的大部分时间用于亲手编写代码。而随着 ChatGPT、Cursor 直至 **Claude Code** 的迭代，编写代码的环节被不断压缩。这种变化并非意味着工程师的时间变多了，而是工作量发生了**置换（Displacement）**：原本用于敲击键盘的时间，现在被转移到了前期的逻辑架构设计和后期的代码质量把控上。

<details>
<summary>Original English Source</summary>

I think the real point behind this is like basically what are we all going to do after AI continues to get really, really good. Uh I'm Louie. I'm the founder of a startup called Vibe Canvas, and I also started the London chapter of AI Tinkers. And you should listen to me because I have done some stuff like get on the SweeBench verified leaderboard ahead of OpenAI.

The agenda for today, class, is we're going to uh I'm going to walk you through why I have arrived at the conclusion that basically all software engineers are going to do all day is plan and review stuff. Everything is plan and review. Work that we software engineers do: we plan stuff, we write code, we review code, and we review other people's code. Roughly, the work that we do. The ratios until GitHub Copilot hit the scene were a lot of it was writing code and not very much of it compared to that was planning and reviewing code. And what we see is over time with things like the first version of GitHub Copilot, that basically the writing code part starts to shrink. ChatGPT arrived, suddenly, you know, you can like generate functions and paste them in, and then Cursor arrives, and then it's like able to complete a whole page of code. Um and then you get Claude Code, and it's like, "Wow, you know, I actually am not really doing much code writing anymore."

So, it kind of poses an interesting question though, which is what, you know, say we were spending 4 hours a day coding before, does that mean I now get 4 hours back if I'm not doing any actual coding? The answer, of course, is no. It has displaced work. Work that you or time that was previously spent doing the coding has moved. It has moved to planning and reviewing.

</details>

### 开发策略博弈：计划驱动 vs 审查驱动

在与 AI 协作时，存在两种根本性的方法论。第一种是**计划驱动型**（Plan-based approach: 侧重于前置详细规格说明），即投入大量时间编写详尽的计划文档（Markdown 文件）或使用 **Spec 框架**。通过反复质询模型并穷尽所有边缘情况，这种“前期投资”可以极大地降低后期的审查成本，使得 AI 输出的代码更精准，减少往返修改的次数。

第二种是**审查驱动型**（Review-based approach: 侧重于快速迭代与后期修正），Louis 将其戏称为“YOLO”模式。你只需给出模糊指令（例如“给网页加个联系表单”），然后通过多轮次的交互来纠正样式和逻辑。虽然这种方式起步快，但在资源分配上，Louis 强烈建议转向**计划驱动**，因为与一个“只交付了一半”的智能体不断进行上下文切换是非常消耗精力的。

<details>
<summary>Original English Source</summary>

I think there's fundamentally two approaches that people take. The first way is the plan-based approach. Um this is where you spend a lot of time up front planning the work that you want a coding agent to do. The smells of whether you are doing this type of work would probably look like you're writing a very comprehensive plan doc, markdown file. You're maybe using like one of these spec frameworks. You're uh interrogating. So, you know, I've seen some cool stuff where the model asks you questions repeatedly until it's like completely exhausted all possible questions it could have about what the work is that needs to be done. The benefits of this, of course, are that you basically spend less time reviewing that work because you have invested time up front uh eliminating edge cases, giving the the the models as much information as possible. The outcome of that will be that the models less likely to [__] up, and you're going to get like better, better outputs, and probably, you know, fewer rounds of review.

The other way of doing this, uh the the other big way of working with AI is you don't define a very detailed plan, but instead, uh you let it, you know, run, and then you you end up spending more time reviewing that work. So, you know, benefits of this, you can just YOLO something, be like, "Ah, let's add a contact form to the webpage." And then, you know, the the the payback you have to do is like you're going to go back and forth a few times correcting the styles, figuring things out. I would say if you think about the valuable thing being your human time, and you have a choice, you always want to be doing the first of these behaviors, the planning the planning approach, basically, because it will save you a lot of time.

</details>

### 场景化架构矩阵：前端的局限与后端的自动化

Louis 提出了一个**决策矩阵**来指导不同任务的 AI 策略。他认为，**前端开发**（Frontend Development）由于其高度的**有状态性**（Stateful: 涉及复杂的交互、动画和样式），很难在前期完全 spec 清楚。因此，在做前端功能开发时，保持“人在回路”的实时反馈模式往往效果更好。

相比之下，**后端功能开发**、**重构**（Refactoring）以及**迁移工作**（Migrations）则非常适合“重计划”模式。通过**测试驱动开发**（Test-Driven Development: TDD），工程师可以完全脱离具体的执行细节，让 AI 独立完成任务。Louis 总结道：“5 分钟的细致计划，可以节省 30 分钟的 AI 代码审查时间。”

<details>
<summary>Original English Source</summary>

I think another way of breaking down the modes of work, where one is plan and one is review, is to think about the type of thing that you're working on. And I think feature development is actually very different from migrations and uh maintenance work. So, and front end is very different from back ends. This is the matrix I've come up with, where basically, if you're working on uh the front end and you're doing feature development, it's basically impossible to kind of really spec everything out. There's so many edge cases and you know, front end is very stateful. Uh there's like interactions, animations, styles, there's functionality. And so, personally, like I find it much better to kind of be in the loop with a coding agent. Uh but for everything else, I think it really is possible to be plan-heavy. So, back-end feature development, you can almost do test-driven development. And for anything like refactoring and migration-based, you certainly uh you certainly can be doing that, and you shouldn't be in the loop with any of that work at all, really. That should all be kind of test-driven development.

So, the I guess if you had to distill that long, meandering spiel into a sentence, it would be spending 5 minutes of planning saves you 30 minutes of reviewing AI-generated code. And that's basically the takeaway.

</details>

### 时间地平线的推移：从“秒级响应”到“深度思考”

随着 AI 智能体变得更加全能，其**执行时长**（Execution Time）正在显著增加。从早期 GitHub Copilot 的单行补全（数秒），到 Cursor 的单文件生成（30秒），再到如今 Claude Code 可以自主运行类型检查、测试甚至启动 **Playwright MCP**（模型上下文协议）进行自动化 UI 测试，任务的执行周期已经跨越到了 5 到 10 分钟。

这种“更长的等待”换取的是“更高的准确率”，但同时也对人类的行为模式提出了挑战。当智能体运行超过 5 分钟时，人类无法再坐着观察日志，这必然导致**并行化开发**（Parallelism）的出现。工程师将不得不像职业经理人一样，同时管理多个并行的工作流，在不同的任务上下文之间平滑切换。

<details>
<summary>Original English Source</summary>

Coding agents become more capable, so as models get better, as tool calling improves, you go from calling a very small set of tools to now, you know, the the coding CLIs can call a a huge range of tools and do testing and things like that. The outcome of that is that every time you send off a prompt, you are waiting longer before it comes back to you.

Think back to GitHub Copilot. It completes a single line of code, and it takes seconds. Then you have like the original Cursor completing a single file, and that runs for, you know, 30 seconds. And then you have uh Claude Code, which, you know, last year would run for maybe a minute or two, and this year I've I've been, you know, getting some pretty good results with 5- or 10-minute executions. We've gone from uh you asking the AI to do something and it just responds to the AI running a type checker to the AI testing its change. I mean, this is like the frontier of things. And these things take increasing amounts of time. Running Playwright MCP is an order of magnitude slower. Um but it's worth doing because what you're trying to maximize for, again, is how much time you are spend or minimize, rather, is how much time you are spending working with the agent.

But this poses an interesting question, which is like, what happens when the average time that an agent is running for exceeds, say 5 minutes. You're not going to sit there for 20 minutes watching agent logs. You're going to have to think about coding and all the job of being a software developer in a very very different way. You run multiple of these things at once. Say each of them take 10 minutes to run. So, the way you get around the waiting problem is you have multiple of them on the go at any given time.

</details>

### 现场谢幕：Vibe Kanban 的商业反思与终结

Louis 在演讲的高潮部分，现场演示了使用 **Vibe Kanban**（他的智能体并行化管理平台）发布了一篇关闭公司的博客。尽管拥有 3 万月活用户和 2.5 万 GitHub 星标，Vibe Kanban 仍面临严重的商业困境：它既没有像大厂那样销售**企业级方案**（Enterprise），也没有通过**代售 Token**（Reselling tokens）获利。用户支付 30 美元的订阅费，却通过该平台在底层模型上消耗了价值 3000 美元的 Token，这种商业模式在当前环境下是不可持续的。

回顾创业历程，Louis 认为这段经历极大地提升了他的个人价值。他学到的核心教训包括：与顶级人才共事、深刻理解什么是真正的**勤奋**（Hard work: 如周六午夜依然与团队在办公室奋战的共鸣），以及在高度成熟的市场中，如果无法争取到领先地位，果断放手也是一种解脱。

<details>
<summary>Original English Source</summary>

I submitted this talk a few weeks ago. And on Tuesday, I decided to shut the company down. So, what I thought I'd do instead is we can actually shut the company down together. Please add a blog post to the website with this content. Okay, so we've got Vibe Kanban website. All right, that's going to go and do it. It's created a Git work tree. It has run a setup script to install the dependencies. I use uh Codex most of the time.

Am I sad? I think I've just done so much thinking about it. I'm kind of relieved. We have 30,000 monthly active users and 25,000 stars on GitHub. But it's actually very difficult uh to make money in the current environment. Uh the everybody who is making money is doing two things. They're selling to enterprise and they're reselling tokens. And we were doing neither of those things. People would spend like $30 with us and then press a button that helps them spend $3,000 with Codex. It's just like not sustainable. It's a mature market at this point and it's no fun playing for eighth place. So, we decided to shut things down.

Overall feeling when you look back is positive. I wouldn't do anything differently. It's increased my value as a human by doing this, so I would do it all again. Most valuable things... I mean, just work with great people. And hard work as well. It took us a while to learn like what hard work really was. Um and you get to a point that's like you're sitting there at midnight with the team in the office on a Saturday and everybody's kind of motivated. Looking back... I'd hire somebody who's really good at selling to Enterprise.

</details>