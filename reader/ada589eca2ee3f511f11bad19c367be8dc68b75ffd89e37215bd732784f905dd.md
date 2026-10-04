---
author: The MAD Podcast with Matt Turck
date: '2026-05-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Fgzs4FBmRYw
speaker: The MAD Podcast with Matt Turck
tags:
  - self-maintaining-software
  - ai-driven-development
  - observability
  - agentic-systems
  - code-maintenance
title: Ramp 如何构建自维护软件：AI 驱动的自动化与可观测性深度解析
summary: 本次分享深入探讨了 Ramp Labs 如何通过 AI 自动化软件开发生命周期，从代码编写转向维护，并介绍了其自研的 'Inspect' 代理及基于 'Monitors' 的动态可观测性系统。演讲者分享了构建自维护软件的关键洞察，强调了信号-噪声比、客户同理心以及构建软件工厂的重要性，为行业提供了前瞻性的视角。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Ramp Labs
products_models:
  - ramp sheets
  - Inspect
media_books: []
status: evergreen
---
### AI 驱动的软件维护与可观测性新范式

Alex 来自 Ramp Labs，分享了他们在自维护软件方面的开创性工作。随着 AI 承担了大部分代码编写任务，软件开发的瓶颈已转移到代码维护、调试及整个生命周期的自动化上。Ramp Labs 提出了一个全新的软件工程范式，旨在通过 AI 自动化这些非编码任务，从而加速软件交付和迭代。

<details>
<summary>Original English</summary>

Hey everyone, I'm Alex from Ramp Labs.

I'm very excited to share with you some of the work that I've been doing on self-maintaining software. So, first just a little bit of background about Ramp Labs. Um, Labs is the home for AI research at LAMP at RAMP. Uh, we've pushed out a lot of super cool experiments and products in the last few months. Uh, both on the applied side and also closer to the model weights. So, for example, we have ramp sheets. Uh it's an AI spreadsheet editor. It's like Excel, but we put an agent in it to do all the manual stuff for you. Uh we also put out latent briefing recently. It's a system for sharing context between agents. That was definitely a lot closer to the weights and the KV cache. Um also steer you might have seen um using steering vectors to essentially influence the output of uh chatbots towards specific topics. Um but I'm here to talk about project I worked on um how we made ramp sheets self-maintaining. Uh we posted this on Twitter maybe you've seen it. Uh this talk is going to be about the experiment in this article and uh essentially like what did we learn from it.
  </details>

### 深入剖析“Inspect”：AI 代理的沙盒化执行

为了实现这一目标，Ramp Labs 构建了一个名为 **Inspect** 的背景 AI 代理。Inspect 的核心优势在于其运行在一个沙盒环境中，该环境镜像了待处理的代码库。这种设计带来了显著的维护和审查优势，因为它允许代理直接测试实际运行的代码，从而发现静态分析可能遗漏的细微行为和潜在问题。Inspect 极大地提高了效率，因为它允许用户启动任意数量的会话，且不受本地机器限制，并预先集成了 GitHub、Data Dog、Sentry 等多种关键系统工具，省去了繁琐的配置工作。

<details>
<summary>Original English</summary>

So the story starts here. This is the data dog dashboard for ramp sheets. Uh in the past few months AI has handled all the coding for me. So now I spend most of my time uh focusing on non-coding tasks, right? It means I'm looking at a lot of stuff like this all the time. I'm looking at a dashboard um trying to get a signal tell me like what do I need to direct my coding agent at, right? What is the thing for me to work on? Um it became pretty clear to me that the bottleneck has shifted from writing code to uh code maintenance and the other parts of the software development life cycle. Um, and obviously as an engineer in 2026, I'm immediately thinking, um, how can I use AI to automate this, make this task go faster, right? Um, is there a way to automate the whole software life cycle, not just the coding part? Um, and how would I build this automation? Before I go any further though, I have to introduce um, Inspect, ramp inspect. Um, because all of the work I'm going to talk about was built on top of inspect. Um, inspect is a background coding agent that we built for ourselves at ramp. Um, the nice thing about inspect is it runs in a sandbox where the repo that we're trying to work on is actually built inside the environment. This is very useful from a review and maintenance perspective um because you can surface issues by testing the live code that you might not necessarily see um when you're just reading static files. Um so you can get these kind of subtle behaviors. Uh, it also scales out very well. I can start as many sessions as I want. Um, it's super easy to just spin up a new inspect session. Um, and I'm not constrained by a process running on my local machine. And it's already set up with all of our systems. So, GitHub, Data Dog, Sentry, Notion, Google, anything you can think of. Like, we already have the tools for to access. So, I don't need to waste time setting up tools, um, setting up a harness, like none of that. I have a suite in a box, uh, ready to go and do some work for me.
  </details>

### 从简单自动化到挑战：状态与复杂性

Ramp Labs 的首次尝试是构建一个简单的**夜间自动化**系统。此系统每天运行一次，执行预设任务，如扫描安全问题、进行核心功能健全性测试、对新合并的 PR 进行压力测试，并尝试发现潜在的未暴露 bug。为了确保修复的有效性，Inspect 会为发现的每个 bug 自动生成 Pull Request。然而，这一方法存在两个主要弊端：**无状态性**——每天都从头开始，导致效率递减；以及**处理大型可观测性表面**的困难——海量的遥测数据（日志、指标、Span）使得发现非显而易见的 bug（如 P90/P99 延迟或需要关联不同指标的细微问题）变得极其困难。

<details>
<summary>Original English</summary>

The first pass I took at uh creating a sort of self-maintaining software system uh was a simple nightly automation. So, uh every night I have an inspect session. It runs on cron um and it just uh has a preset prompt uh to go do things. I tell it to scan for security issues. Um make sure that all of our core functionality is still working. So, sanity testing um any recently merged PRs, stress test those. Um then also see maybe you can surface any bugs that are like latent in the system that we haven't seen yet. You know I don't want to wake up to problems. I want to wake up to solutions. So I made it a system of action where um inspect will autogenerate pull requests uh for every bug that it finds. The real power as I've said before is the sandbox. So we have real tests, real API requests against live running code. Um this has a lot of advantages for us. Um, it decreases noise because every error that I've seen has actually been reproduced inside the sandbox. Um, and it also improves the quality of the fixes because in order for a fix to go through, I say you have to pass your initial reproduction, right? So, I know every fix like actually works. Um, and this approach is very simple. It's effective. Um, and it found several real bugs uh every night we ran it. Uh, but there there were definitely some serious weaknesses. So the automation is uh completely stateless is one of one of these weaknesses. Um every night it starts fresh. So the agent just it just reverts to its default behavior. Um aside from any new PRs that were emerged in the past 24 hours, we're still checking the same stuff uh the same paths every night. And so uh we ke we see kind of diminishing returns on the number of useful issues surfaced um over time. Um, another issue is difficulty parsing uh a large observability service um surface. So um we just have like a large amount of telemetry that comes out of a production app, right? You have logs, metrics, spans, a ton of it. Um this volume of stuff to sort through leads to a lot of difficulty in finding non-obvious bugs, right? So we're we're very good at finding things that are obviously wrong. We have a big red error message, unhandled exception, etc. Like we'll get that every time. Um, but a lot of issues in production don't have very obvious signals that they're happening. Um, it could manifest itself in really bad P90 or P99 latency on a specific function. Um, you could even have an issue that you can only tell from the telemetry through the correlation of two different metrics, right? Um, so there there's a lot of subtle stuff that's very difficult to kind of divine out of this large observability surface. Um, so yeah, those are our two issues.
  </details>

### 引入“Monitors”：构建动态、有状态的可观测性系统

为解决状态缺失和复杂性问题，Ramp Labs 引入了 **Monitors** 作为关键抽象。Monitors 是持久化、云托管的实体，能够存储关于系统状态的信息，并可用于聚焦代理的工作范围。每个 Monitor 都针对特定问题创建，当其触发时，能即时告知开发者代码中导致问题的具体环节。通过自动化流程，当新的 Pull Request 合并时，Inspect 会自动为其设置 Monitors。一旦 Monitor 触发，Inspect 就会被激活以修复问题。这种方法极大地增强了代码库的可见性，并使响应成本极低，易于水平扩展，确保“异常”情况发生时能立即收到警报并获得修复建议。

<details>
<summary>Original English</summary>

Uh, we need to have some way of keeping state inside of the system. Um, and I didn't want to solve, you know, general agent memory, you know, those like markdown file folders, like I didn't want to get into too much of that, uh, because that just rapidly increases the scope of what I'm building. And I also wanted some way of narrowing the agents focus to specific segments of our observability surface so that it doesn't have to start uh from scratch every time and kind of understand everything. um every 24 hours. An abstraction that was very useful for this is monitors. Um so monitors like on data dog for state there's a monitor description. This is persistent hosted in the cloud. Um it can hold information about the system and uh for focus narrowing the scope u every monitor is created against a specific issue right so a monitor goes off I know what's happening in the code that caused it to go off. Um, I set up an automation so that whenever a pull request merged in, uh, any of the ramp sheets code paths, uh, we would automatically call inspect and say put up monitors against this new PR and then when the monitor goes off, we kick off inspect and say fix the issue. Um, this is this is a very uh simple setup, but it it works very well. So, uh, it gives us remarkable visibility into the codebase. um we can scale out the number of monitors because responding to issues is now AIdriven and so the cost is very low um and it scales horizontally very well. The second anything out of the ordinary happens like we're alerted a fix is suggested. Um I have an example here there in the past we've caught employees of a certain company trying to benchmark ramp sheets essentially see how good it was. Um, and so we put a blanket ban on their emails, but the way we implemented it, uh, actually wasn't comprehensive. So, uh, a few weeks later, they came back and they were still able to log in successfully. Uh, and I got alerted, uh, right after this happened saying, here's what happened. Uh, here's the fix, right? And go merge it. We merged it in and it worked very well. Um, so that's one example of kind of this level of of very fine granularity visibility you have into the entire codebase.
  </details>

### 应对告警噪音：智能监控与三方协调模式

引入 Monitors 后，一个关键的挑战是如何控制**告警噪音**。最初的系统立即产生了大量“冗余”告警，主要原因包括**未校准的 Monitors**（触发但无实际问题）和**重复通知**（同一问题反复告警）。为解决此问题，Ramp Labs 采用了**三方协调模式**。对于噪音 Monitor，Inspect 会首先评估告警的实际价值，通过分析历史数据和整体范围来决定是调优还是删除该 Monitor。对于重复性告警，当 Inspect 提出修复方案后，它会编辑 Monitor 的描述，包含新创建的 PR 信息，从而使后续同类告警的 Inspect 会话保持静默，避免不必要的打扰。这种模式确保了只有真正有价值的告警能触达开发者。

<details>
<summary>Original English</summary>

The number one objection I got when I was planning the system is how are you going to control noise? Um, and this was absolutely justified. Um, I turned the system on and immediately just got assaulted with slop coming from the agent. Um, the biggest reasons for this were unccalibrated monitors. So, these are monitors that go off but nothing's actually broken, right? It's just a noisy signal. Um, and then the other one is duplicate notification. So, some monitors just go off a lot. Um, maybe it's a common problem. It's a super hot code path. Uh, and so I just get notified every time someone presses this button like, "Hey, this button's broken. I know we, you know, I'll get to it." Right? Uh, you don't need to keep sending me the same alert over and over again. So, um, we solve these issues with a triage pattern. So, for dealing with the noisy monitors, um, we say when the monitor goes off, inspect will first evaluate the merit of the alert. It'll look at historical data. It'll assess the the total scope of everything and it will decide is this noise, is this real, and then either tune or delete the monitor um if it's noise. For dealing with duplicates, uh when inspect puts up a fix for a real issue, it will um edit the monitor description to include the new PR that just created so that the next session that comes off for that same issue, uh it will already see that a fix has been put up. Um there's no need to alert and so it doesn't alert. It keeps itself silent essentially and um quits after a few agent turns.
  </details>

### 软件工厂与自我改进：迈向自动化软件生命周期

Ramp Labs 提出的新监控范式，通过将高水平的监控投入统一应用于代码库的每个部分，实现了动态演进。这与传统的、仅覆盖关键部分的监控形成鲜明对比。演讲者强调，**信号-噪声比**至关重要，AI 驱动的系统若产生大量噪音，将被忽略。同时，**可观测性培养了客户同理心**，因为开发者能更直接地感受到用户痛点。展望未来，Ramp Labs 正在探索将 **Inspect** 构建成**软件工厂**的基石，其愿景是创建一个能够自动构建、部署和维护软件的流水线，其效率远超人工。更进一步，他们也在研究**自我改进**，即利用 AI 系统自主分析日志、反馈等数据，不断优化和增强应用程序的功能。

<details>
<summary>Original English</summary>

Let's see. Oh, I really like this graphic. Um the general idea here is that the old monitoring paradigm is on the left. Um these are like kind of loose broadstrokes monitors. Um essentially tell me if there's an unhandled exception part of the code. Tell me if our latency craters. Tell me if something's very obviously bad. Um there might be one super critical part of the code that's very highly instrumented, but that level of effort is not applied uniformly across the codebase. Um there are certain parts of your code that are essentially unwatched. It could break and you have no idea. And then the new monitoring paradigm that I'm proposing is on the right. Uh every single part of the codebase has a high level of monitoring effort applied to it. Uh the observability system is dynamic and it evolves with the code as you're uh as you're continuing to contribute to the codebase. Um, and anytime anything at all deviates from the expected behavior, you know about it and you have a fix ready to merge in. And so here are just some learnings from uh the experiment. Uh the number one thing is that signal to noise ratio is absolutely critical. Uh no one likes being bombarded by slop. Teams ignore noisy monitors already. Uh putting an AI on it is not going to make them not ignore it. uh people will ignore you if uh when you reach a human uh the alert is not actually worth uh investigating or or fixing. Making sure every time you touch a human you have high confidence that this is a real issue is probably the number one priority. Um another thing is that observability uh breeds customer empathy. So this kind of ties back into the point I had before about high visibility. I see everything that's wrong with the app. Um, and so whenever anything bad happens um that a user sees, I'm also seeing it. And so that just means that I feel the user pain uh a lot more acutely. Observability isn't one-sizefits-all. Uh became very apparent that there are a lot of ways to implement this sort of continuous observability regime. And obviously as the technology continues to evolve, the tools people plug into the technology continues to evolve um you know this type of setup uh will change uh and people will find I think newer better ways to to build um self self monitoring systems. Um and then inspect as a foundation uh is very important. So this entire experiment was just an inspect wrapper pretty light wrapper honestly on top of ramp inspect. Um, so it just shows you can get really really far by thinking of interesting patterns for wiring up inspect sessions with each other. Um, and I want to kind of stand this point as I go into the next slide here. Um, which it it just shows you that like wiring is a lot of where the alpha is, right? Inspect and these tools, I know there are other ones on the market that people are building are incredibly powerful. You know, it's a software engineer in a box. It can do any individual thing that you can do. And so now the productivity unlock is chaining these sessions together and wiring contexts together to uh take on bigger issues. Um you can almost think of inspect as like a unit of work that I can call through API right. Um I know a lot of people have been talking about um the software factory building a factory that that ships out software inspect or uh you know a background agent you can think of almost as the primitive of that factory like the building block and as we think about software factories it's important to shift our thinking from uh just building software to building the pipeline that builds software. Um, we've we've seen processes like this happen in the past. You know, back uh 500 years ago, if you wanted a pair of shoes, you had to make the shoes by hand. It take you like a week. And now we have factories that turn out like thousands of them every second. Um, and we can probably apply the same principle to software. Um, we can build a factory that ships and maintains code faster than any individual human or any team. Uh, probably by orders of magnitude, right? Um, and one more concept that we've been thinking about is uh self-improvement. So move from just keeping uh the application alive and reliable like maintenance to now can we make the application better uh using an agentic system right can we look at um our our logs can we look at feedback forms log rocket slack gong session replays all of this and somehow get things that people are struggling with with the product things that people want out of the product and build it autonomously. Um, so that's something we've been experimenting with as well. Just want to end with a quick plug of RAMPLabs, labs.ramp.com. Um, we're always working on new experiments. Feel free to reach out to us. We are hiring, by the way, as well. Also on the Applied AI team at RAMP. I think that's it. We're ready to open up for questions.
  </details>