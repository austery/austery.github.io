---
author: AI Engineer
date: '2026-06-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pmoDeA3RBZY
speaker: AI Engineer
tags:
  - ai-agents
  - development-workflow
  - software-engineering
  - automation
title: 暗黑工厂：AI 智能体接管下的高频代码交付与工程重构
summary: 本演讲探讨了 AI 编程智能体如何以极高速度重塑软件开发。演讲者提出工程师正从“手工作坊”向“工厂管理者”转型，介绍了通过管理多条“智能体泳道”实现单日数千次代码提交的极端工程实践，并强调在此模式下，开发流程与管理直觉比单纯的模型能力更重要。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenClaw
  - Nvidia
  - Anthropic
  - OpenAI
products_models:
  - Nemo Claw
  - Codex
media_books: []
status: evergreen
---
### 软件工程的“工业革命”与极致开发速度

在开源项目 **OpenClaw** 的开发中，一种以极速交付代码的全新模式正在涌现。这种开发速度极快，甚至超过了人类阅读代码差异（Diff）的速度。这种现象并非偶然或碰运气，而是工程实践的真实演进。如同历史上从家庭手工业向集中式工厂过渡的**工业革命**（Industrial Revolution: 描述生产方式从手工向大规模机器生产的质变）一样，软件工程也正在经历类似的转变。过去，生产的瓶颈在于织工的双手；现在，工程师在编辑器中手写代码的时代正在淡出，取而代之的是跨代码库运作的智能体集群。工程师的角色正在从“工厂工人”转变为“工厂管理者”，而新的瓶颈变为了工程师对代码逻辑和系统架构的**品味**（Taste）。

这种规模化的自主智能体应用已在行业内隐秘而广泛地展开。无论是构建新 C 编译器的企业，还是自称**氛围维护者**（Vibe Maintainer）的独立开发者，甚至是单日推送成百上千次提交的开源团队，都在印证这一趋势。在极致的状态下，单个核心维护者甚至能达到每天近 3000 次代码提交。这种天文数字般的交付速度预示着未来开发的常态，传统的代码审查机制在如此庞大的代码生成量面前将难以为继，必然要求全新的工程形式介入。

<details><summary>Original English Source</summary>

They've got it. Cool. Amazing. So, welcome everyone. I'm Vincent. Uh what do I do? I'm one of the core maintainers at OpenClaw working with Peter. And as you've heard before, I have a day job as well, same as Peter. He has a day job at OpenAI. Um but, you know, it's an open source project. Amazing things have been happening. I'm going to talk about what I call doc factories and how OpenClaw ships faster than you can read the diff.

Um this meme is absolutely hilarious. So, I think Peter posted this uh a week or two ago. I wake up, there's a new technological advancement. I wake up. It's this this joke that we're shipping at insane speed and the velocity is just absolutely phenomenal. And some of you might think, "Oh, this is some luck or we're just like Ralph flipping to the max." Um I think there's actual engineering work here and I'm going to talk about that.

Now, as I mentioned, I'm Vincent. I'm your friendly clan car. Uh this is me using VR goggles back in 2013. So, despite my accent that sounds somewhat Australian, I was born and raised in East London, not far from here. I actually went to to college just down the road in Westminster. And yeah, at some point decided to live in Australia and my accent changed. But, I used to love technology. I used to love being at the edge of technology. And this was like one of the first few sort of early um VR goggles that came out. Came in this big box with a big warning sign on it saying, "Hey, use for 5 minutes at a time." Cuz it didn't have like the anti-motion sickness built into it.

And the funny thing with this one here was that I didn't use it for 5 minutes. I used it for 3 hours. And I played Team Fortress 2, had an absolute blast, and then I vomited for 3 hours after that cuz my vision turned into bee visions. Um the what I'm trying to say here is that like anything on the edge is going to be janky, it's going to be horrible bit horrific. It's going to be uh uncharted territory. And working on OpenClaw and being part of the team that ships probably, you know, an insane velocity of commits to a point where I get rate limited by GitHub on an hourly basis uh is an interesting experience.

And this experience Britain's gone through before. Um we had the Industrial Revolution when mills and cotton were being produced at extreme amounts of volume. And there's a lot of history here around production and productionization at scale uh in the UK and in Europe. And I feel like we're going through this moment again. Uh we're going through this moment of how do we build at scale? And the ways we used to work before just don't work anymore.

And it's kind of strange because in my day job, I kind of work in the space of Evals, which everything is sort of structured and there's telemetry and it has to be all perfect. And I work on a project where I'm I have this blind faith in the hardness. And it's this kind of two worlds, but they're starting to come together. We used to have handlooms in cottages, uh centralized mills everywhere. Uh craftsmen were the factory workers. But the bottleneck was the weaver's hands. We're now switching to a world where engineers writing code in editors, not so much. Uh swarms across repos. Uh engineers are becoming factory managers, which I'm going to talk to. And the bottleneck becomes taste, you know, that lovely word. Uh Italian mother's hands, yes.

So, in in context, like what does this mean? Like are you talking absolute nonsense and people building things at absolute scale? They are. What happened was um very similar to the ChatGPT era, where everyone denied it at scale that they were using ChatGPT. Everyone was in this absolute fear-mongering sort of world. But what the reality was that everyone was using it. Everyone in secret was just like, "Oh my god, what's going on? I need to talk to it." And the same thing is happening with these autonomous agents at scale. Some organizations have openly come up with it. So, for example, Anthropic with their recent work they did on building a new C compiler. Uh we had Spotify saying they're they're no longer writing code by hand, supposedly.

Um Steve Yegge, which I absolutely love, uh saying he pushes about 50 PRs a day total solo. He calls himself a vibe maintainer. I can kind of relate to that. And OpenClaw where we're pushing at the peak, we were doing 800 commits a day. And realistically, like there's about 10 to 15 core maintainers all with day jobs. It's kind of astronomical in terms of scale. And for me, this was March 15th. Um what was that? Like 2 3 weeks ago? Where I hit close to 3,000 commits per day. And if you actually took look, my commits actually stop when I go to sleep. So, if you if you want to see when I go to sleep and when I wake up and how many hours of sleep I have, you can just take a look at my commit history.

Yeah, it's astronomical. But the thing is, this is going to become the norm everywhere else. Like this is this is like a me telling you you need to wake up that, you know, that this scale of velocity is going to be normal. And trying to review PRs and go through all this nonsense may not work. But somewhere in the mix is engineering. There is a form of engineering that's going to happen. So, we did commit maxing. You know? Let's just go there. Smash as many commits as we can.

</details>

### 机器人循环与史诗级代码重构

在应对极高频的代码生成时，单纯依赖消耗 Token 让模型盲目尝试是低效的。这种毫无主见的暴力破解模式往往需要耗费数小时等待一个不可控的结果。为了提高工程效率，团队引入了一种更具指导性的方法——**机器人循环**（Bot Looping: 通过明确的奖励机制和预判引导智能体自主迭代），使智能体执行更加聪明和精准。在与 **Nvidia** 团队合作开发 **Nemo Claw** 时，这一策略被推向了极限。两名工程师并行运行了多达 60-70 个子智能体，在约 15 个主要的并发流程中同时处理代码逻辑。

在这种极高密度的协作环境下，一次对代码目录的普通移动操作，意外引发了一场被称为“伟大的重构”（The Great Refactor）的代码库灾难与重生。由于需要避免系统过度臃肿，防止盲目合并带来的“代码垃圾场”（Fire Dump），团队借助插件架构对代码库进行了彻底的模块化拆解。最终，智能体以令人窒息的速度完成了高达 2700 次提交、涉及百万行代码的重构，触及了核心代码库的 82%。在这次激进的重构中，往往被轻视的、存在严重**过拟合**（Over-fitting）的 AI 生成单元测试却发挥了意想不到的兜底作用。只要这些极度敏感的测试仍能保持通过（Green），工程师就能确信重构方向大致无误。

<details><summary>Original English Source</summary>

And this reminds me of Ralph looping, right? This like this this this this guy where you're like, "Hey, I'm just going to like give you a task. I'm going to burn tokens for like 8 to 9 hours." And you're waiting, you know? Uh you're waiting. You're hoping something happens. Maybe something happens. I don't know. Um but what if we had a bit more of an opinionated approach to this? Um what if we call it bot looping? I don't know. One of the other maintainers gave me this idea. Maybe we'll coin it. Do we Do we need more than just tokens? Uh what does that reward mechanism look like?

How do we get a bit more opinionated? Yes, let's run loops, but let's be a bit more smart about how we do this. So, um right about the time you saw those 3,000 commits, uh this was the day before, I was at Nvidia with Peter and the gentleman you see on the left is is one of the other Nvidia gentlemen. And they were like, "Hey, we're building Nemo Claw." I'm like, "What?" What's going on? And uh let's help you build it. And I was in the room. I was like, "I can't work on a laptop for like hours on end. Can you bring me a screen?" They brought me a screen. Um Peter didn't have a screen, so that's his laptop on the left. He asked for a screen, so they gave him an even bigger screen than mine cuz, you know, why not?

And we just got to work. So, he's running about maybe 15 code sessions and he's got his Mac Studio at home he's VPN'd into. I'm running another like 10 or 15. And between collectively between us, we're probably running with sub agents included, maybe up to 60, 70 agents. Um but on the foreground, maybe 15 uh swim lanes, if you want to call it that. And we're just just going for it. Funny thing is, we're working on Nemo Claw on one side, but one maintainer decided, "I'm going to move some stuff around. I'm going to move a couple of folders around." And that was moving entire channels. So, like all our conversations with like MS Teams and Slack ended up moving to another location in the code base. And we were like, "Oh my goodness, we're going to have to change stuff."

Um and I found a really nice uh place to put my drink as well. The Nvidia people don't like this. So, what ended up happening is what we call the great refactor. Um essentially where we were like, "Hey, we have lots of people raising PRs. And what they actually want is to build features. The thing is, we don't want to give everyone every single feature that they want, in which case it becomes bloat. Uh you heard Peter say earlier on, the challenge becomes who do I say no to? It's not about saying yes. In a world where tokens are cheap, I can just say yes to absolutely everyone and merge everything in. But that's going to turn this code base into an absolute fire dump.

So, the vision was actually we need to cut this code base down. We need to We need to rip it into pieces. And a plugin architecture somewhat made sense. Imagine if you're OpenAI or Mistral or Anthropic, what if you own that piece of the provider code and it was handed to you and it was separate from everything else. So, this code change that occurred was like a catalyst for us. It was 2:00 in the morning. We're tired. We thought, "Why not refactor the entire code base?" Sounds like a splendid idea.

So, 2,700 commits later, uh close to a million lines of code change, uh touching 82% of the core code base, plugins were launched. Um the night before, I think it was like 1:00 in the morning. I'm trying to go to sleep. And the tests are not passing. And I was like, was I Icarus and did I fly too close to the sun? Um as we like to call it, did I did I vibe too hard? I I actually generally thought I vibe too hard. But as a team, we managed we managed to bring this code base back together again.

But the saving grace was these awful sort of unit tests that AI code loves to generate that actually ended up over-fitting on our code. So, when we completely ripped everything out, we still had these tests that were like extremely over-fitting. And as long as they would go green, we knew we were kind of somewhat close.

</details>

### 智能体工厂管理与工程师的新范式

在管理如此庞大的代码生成机器时，**智能体工厂**（Agent Factory）的运作理念应运而生。工程师需要建立多条平行的**泳道**（Swim Lanes: 独立处理不同任务流的工作线），像厂长一样统筹全局。针对稳定性较高的重复性工作，可以放任智能体自主提交；而对于涉及核心架构逻辑（如 Docker 配置）的改动，则需要与智能体进行深入的对话引导；对于最高优先级的线上问题（P0/P1），智能体会结合外部数据流（如 GitHub 的实时事件日志）进行追踪。当开发并发规模无限扩展时，系统的瓶颈已不再是 API Token，而是底层的原生算力限制，以及工程师本人的**心智带宽**（Brain Space）。

为了维系这座庞大的虚拟工厂，工程师必须彻底优化本地的**智能体开发环境**（Agent Development Environment）。尝试通过大量的 **Git Worktrees** 来隔离并发任务往往会迅速耗尽机器资源，更可靠的做法是将单一会话指向多个独立的仓库克隆。与此同时，工程师与大模型的协作正在剥离僵硬的“规划模式”，转而依赖大量交互累积的直觉经验。正如电影《黑客帝国》中所展示的那样，工程师能够通过阅读大模型生成的“推理 Token”（Reasoning Tokens），敏锐地感知智能体是否在“胡编乱造”（Bullshitting）。管理成百上千个并发执行的智能体，本质上与管理规模庞大的人类工程师团队并无二致——核心在于建立一套不依赖单点信任的容错流程，以及敏锐的直觉判断。进入 2026 年后，软件工程的主命题已从对 Token 的盲目压榨，转向了极致的效率优化以及“人在环路”（Agent in the loop）下的流程重构。

<details><summary>Original English Source</summary>

So, how do we do this? You know? Um in my case, I call it my factory. It's many code sessions. Everyone asks me like, "What's this magic sauce? Like how how do you do this? What's this crazy insane thing? Like how are you guys building this?" Very simple. I have swim lanes. Um it could be five, it could be 10, it could be 20. But traditionally, they kind of cut themselves up into different pieces. So, like if I Does this work the laser? You can't really see it. But imagine you're a factory manager and you have a production line below. Essentially, you might have a case where you have

Let's just say CI to one side, you might have features on one side, you might have bugs on another. So, when I'm refactoring and doing stuff right now the code base is quite stable. I want to refactor some tests. Well, that might be swim lanes one and two. I don't need to really babysit them too much. I just told them, "Take your time. Make sure the test pass. Just commit. Just just push them through." Whereas with three and four, I might be looking at specific features and issues around say Docker or um one of our messaging channel channels. In which case, I'm having a conversation with those agents. They're going off investigating, doing the work, coming back. And then maybe five is actually um looking at new P0s and P1s. Um that might be using other data. It might be using GitHub. Uh we have agents that run inside of a Discord channel. So, when we do a release, we might be like, "Hey, what's happened in the last 2 hours that I need to be paying attention to?" And this will scale up and down.

But, what ends up becoming quite interesting is tokens are no longer the problem. Um depends who you ask. What really ends up becoming the problem is just raw compute and my brain space in order to sort of keep an eye on all of these sessions. So, in Harness we trust. What ends up happening is I don't have this really insanely complicated process. The one thing I have complicated in my life is adopting Git work trees and I kind of wish I hadn't. The only reason why I say this is when you're running an extremely heavy test harness, it ended up completely nuking my machine cuz I ended up running like every PR I touch ends up becoming a new Git work tree. I end up with like something close like 70 or 80 active Git work trees in any given day on my machine and that's kind of hell.

Um so, I had to actually build some like magic sauce around my my Codex session. So, my Codex is aware of Git work trees. If I hit the escape key, it crashes. It will self-heal, self-recover, get, you know, sparse stuff. But, realistically, I should have adopted what Peter and other people do is just like clone the repo 10 times and point 10 different, you know, Codex sessions to each one. But, the trick here is that like I haven't done any magical sauce. I don't use plan mode or spec mode. I have a conversation with the agent and we work through it and we find a way to make it work.

So, realistically, it looks a little bit like this from the Matrix. Um and people go, "Oh, Vincent, like how do you know it's kind of working?" And this is going to sound somewhat little bit lunatic. It It If If anyone's watched The Matrix and seen the scene where Neo goes over is like, "How do you know? How do you read the text?" And the guy's like, "Oh, you know, I've been doing this for a while, so I can see like woman in red dress or guy walking dog." And you start to have this like relationship where you can feel the reasoning tokens. I know it sounds somewhat ludicrous, but there's times where I'm looking at the swim lane. I'm like, "This sounds off." It doesn't sound off because of what it's doing. It sounds off because of how it's explaining itself to me. It's waffling. It's not making sense. It doesn't seem to know what it's doing.

And this feels a lot like how I would manage people. Um if I had someone working for me and they started downright bullshitting, I'd be like, "Wait a minute. What's going on?" So, in these cases, I might just nuke the session and go, "You know, I'm not going to deal with this section of code. I'm going to leave that to another maintainer." Or I might come back to it four or five days later. But, that experience feels very much like intuitive and building that intuition, I've been able to get to because of the sheer volume of token maxing I've had to go through in the previous year.

So, there is engineering work. Uh I call this the agent development environment. Um essentially, the process goes I have skills. I call it dot skills, similar to dot um dot files. Both of my dot skills and dot files is available on GitHub. It's all open source. Go for it. Some of my skills are private, but there's skills in there for like writing technical documentation, for example, um that I've co-created with other um developer experience and other engineers in the market. Um you can use a skills gem, something like a Geppetto, which I'm also a contributor to. And or you could just say, "Go Codex." I've been using this skill in my last uh 2 weeks. Go through the Codex sessions, read the logs, make improvements to the skill. Um I would then take that skill and deploy that into my open core or take that into my you know, personal environment and I'll use something like vercel.skills.sh as like a mechanism to look this. I've added some other testing and other elements on top of this, but there's a process to how I manage and maintain my skills as an engineer.

The way we manage PRs has some level of engineering work to it. Um there's this kind of running joke that every maintainer that joins the project decides to try and tackle like, "Oh my god, we have 6,000 PRs. How are we going to solve it? I'm going to cluster everything and like figure this out." 60k? How many? 60k. There you go. There you go. Honor. Thank you very much. So, this was my flavor of like trying to solve this. This is like a semantic graphing, uh vector embedding on the entire GitHub stuff. This is one PR. Has 73 106 edges. What ends up happening is that everyone else has the same problem, so they decide to to send their flavor of the PR issue. Becomes utter noise.

So, there is even process around like how we even consume what we're going to work on. We might not call it a road map, but we have a way of kind of deduplicating and seeing what's out there. This might be a signal for me to say, "Okay, if there's enough pressure coming on one issue, it must be big enough that all these other clankers decided it's a big problem. Maybe I should go and address it."

There is evals, surprisingly. Um after all this refactoring work, we decided to make a fake Slack of sorts with both synthetic models and real models, so we can run evaluation loops to check that each of the providers and the channels work. And this question was asked to me recently. "How do you manage 10 plus agents?" And this is something that you're thinking. I asked them back, "How do you manage 10 plus staff?" And they had no answer for me. I'd worked in large organizations like airlines and other places like that managing large AI teams. I had experience managing up to 30, 40 people plus.

So, for me it was not like a a a new paradigm. But, I think for engineers and people working with these coding agents at scale, it's the soft skills that matter. It's how do you ask your agent, "What's going on?" How do you know when they're not bullshitting you? And how do you run that factory? So, it's no longer about the model or the agent. It's about the process. Uh 2025 was about token maxing. 2026 is about not wasting them. It's about token efficiency. It's about agent in the loop. Thank you.

</details>