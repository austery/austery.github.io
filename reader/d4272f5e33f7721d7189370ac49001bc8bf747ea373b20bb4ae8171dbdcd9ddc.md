---
author: AI Engineer
date: '2026-07-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZSQb5fzRFPw
speaker: AI Engineer
tags:
  - computer-use
  - agentic-infrastructure
  - accessibility-tree
  - reinforcement-learning
title: Computer-Use 2.0：解耦人机界面与智能体后台运行的全新架构
summary: 本篇双语档案整理自 Cua 团队的发布会演讲。CEO Francesco、CTO Dylan 及 Chief of Infra Rob 共同介绍了他们开源的底层驱动项目 Quad Driver、基准测试工具 KUBench 以及训练基础设施 KUA Fleet。系统展示了如何通过操作系统底层未公开 API 实现智能体的非抢占式后台运行，以及如何通过按需自动伸缩的沙箱温池最大化 GPU 训练能效。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cua
  - Microsoft
  - Snorkel AI
products_models:
  - Quad Driver
  - KUBench
  - KUA Fleet
media_books: []
status: evergreen
---
### 后台运行：重构智能体人机交互的底层驱动

在过去的计算机使用（Computer Use）智能体设计中，智能体通常需要完全接管用户的屏幕。这意味着当智能体在运行时，人类用户无法使用他们的电脑，这种交互模式被称为 **人类循环**（Human Loop），即智能体通过截取屏幕截图进行推理、规划，然后通过模拟鼠标点击、键盘输入和滚动页面等动作来实现对计算机的操作。我们将这种传统的交互方式定义为**计算机使用 1.0**（Computer Use 1.0）。

为了解决这一痛点，Cua 团队在两个月前开源了名为 **Quad Driver** 的项目。它的核心突破在于实现了“后台运行”，即智能体在执行任务时，完全不会抢占或干扰人类用户的当前屏幕。这一技术的背后涉及到对 Apple 框架中一些未公开 API（Undocumented API）的深度调用。Quad Driver 不仅适用于 macOS，还横跨 Windows 和 Linux 平台，是首个允许智能体直接与操作系统底层连接的通用驱动程序。在运行中，智能体通过获取窗口状态，读取**可访问性树**（Accessibility Tree: 操作系统为残障人士辅助工具提供的应用程序内部结构化文本表示）并结合窗口截图。智能体首先尝试利用可访问性树进行后台静默执行，如果该路径失败，系统则会启用底层技术，直接在后台进行像素级别的模拟点击（Pixel Background Click），从而确保智能体既能精准操作，又不会打扰用户的日常工作。

为了确保不同版本在快速迭代中不发生功能退化，团队构建了包含 8 个不同应用测试套件（Application Harnesses）的集成测试体系，在发布前进行严密验证。目前，包括 Clicky Mass、Queno 等公司在内的早期采用者已积极接入，并向 Quad Driver 的上游框架回馈了大量代码贡献。

<details>
<summary>Original English</summary>

Thank you for taking the time for coming over here. Um I'm Franchesco. I'm the CEO of the company. Uh alongside me, a couple of other folks. Um my co Dylan and my chief of infra Rob. They're going to walk on the stage in a while. Uh but before we do that, who's excited for some computer using agent talk happening now? Are you guys excited? Lovely. Um if I were to ask like what what was a computer using agent like one year ago, probably half the crowd would say I don't have any idea what really computer use mean. Um so um today I'm going to take you to a journey. Um basically like from our vision where um we come from so far on computer user um like this new shape of like agents are talking um and uh up to model intelligence. Um so we're going to start like with the vision of uh quad driver where we're coming from and uh if you how many of you guys been been working with computer use for one year. How about like two years? Lovely. Okay. So, our team has plenty of experience like we go all the way back uh our time on Microsoft. We were working on this type of guey agents we were calling them uh back in the days. Um and uh there is a um there's an example of like old-fashioned human uh agent loop. Um we basically refer um refer this as a human uh loop where you will have like an agent loop. You will have a um uh you will take a screenshot that the agents will have to reason and plan through and then um you will basically work with an action space in terms of like clicking, typing, scrolling around. So this is what we refer as as um um the old fashioned like computer use 1.0 you know, just to set the tone for for um for this talk and uh we come like a long um a long like way since this type of like um computer using agents. So this is this again like I'm going to skim over these slides but that's like the old fashioned way of like representing these agents loop as a human would do. Um we um here we go. Um over like two months ago we released a project in open source. It's called quad driver and uh um we um we made it working like in the background. That means that your computer user will will not take over your uh screen as like the computer use 1.0 um kind of like agent loop was doing back in the days. And uh um it all like started from uh um from like uh um from Codex releasing their computer use um model two months ago. So we kind of like take the challenge because we were already like working with this uh this type of background computer user. So over one weekend we act something together. And uh the trick here is really um not like having your agents like take over your screen. So there is a lot of like dark magic like happening behind the wood just to uh give you some context. Uh there are like some undocumented API um living in u um in the Apple framework that basically ships with your laptop and as you can see here like is in the demo you have like an I agent that is not taking over uh control of your your laptop. Um we made it working not only for Mac OS but also spanning like across Windows and Linux. where uh this is like the very first like driver that is uh living on your um laptop and uh it lets uh really any agents connect to the underlying operating system uh either like using accessibility trees or like a screenshot level approach. We kind of like take all um this is what really the agents see for what it concerns. Um you will have to install quad driver. Um the agents will uh will take a snapshot of the window state and uh you will have to observe um and uh we really like take take like one uh uh like different like action path to really make the ground computer use happening. So you really um have um to observe the space in this case just by calling like get window state you get a an accessibility tree representation plus a screenshot and then you will go and uh um try a background execution using accessibility tree and if that doesn't work we go all the way and uh make the heavy lifting for you and just try a pixel background click. This is like uh kind of like best step for background at this stage. It's not like behaving in the same way Mac OS, Windows and Linux. So uh we we do like some of the lifting for you so that your AI agent can uh can run and disturb on your uh on your MacBook. um how we manage like to not break anything between like release cycles. We have ex we have like a lot of investment happening uh behind the scene uh when we test like new releases. uh we have about like eight different uh application harnesses that are um that that that we that we use for making sure that we don't break anything uh among different releases. Um among our early adopters you can see like clicky mass queno h company and droid factory. uh like huge thanks to them for using quad driver and like um basically releasing a lot of like upstream contribution back in in our framework. Um without further ado, I'm just going to move to the next part of the presentation which is going to be intelligence. Um and I'm going to have our CTO Don cover that.

</details>

### 智能评测：KUBench 与物理级硬件仿真

在成功赋予智能体操作系统的“双手”之后，核心的挑战转移到了“信任”问题：如何确保智能体能够正确调用这些接口而不破坏现有的系统环境。为了解决智能体的评测难题，Cua 团队开发了 **KUBench** 评测基准。不同于仅包含字符界面的评测系统 Terminal Bench，KUBench 面向的是复杂的图形用户界面（GUI）。

在 KUBench 中，每个测试任务由三个核心部分组成：
* **初始化函数**（Setup Function）：负责将操作系统和软件环境初始化到特定状态。
* **真值函数**（Oracle Function）：提供该任务的标准操作轨迹（Golden Trajectory）。
* **评估器**（Evaluator）：在任务结束后对环境进行探针测试，验证智能体是否真正达成了目标状态。

由于桌面端需要适配多种操作系统，Cua 团队通过 KUBench SDK 将繁杂的环境配置及探针逻辑封装在单个 Python 文件中，实现了跨平台的轻量化运行。目前，KUBench 已经拥有超过 130 个可验证任务、42 个独立应用环境，覆盖 5 个不同的操作系统平台。此外，团队与 **Snorkel AI** 深度合作，推出了面向专业电子工程设计的基准测试 **KUBench KiCad**。该基准使用真实的专业电路设计软件 KiCad，评估器内部集成了电路仿真器，能够直接运行智能体生成的电路图并检查其物理电学特性。

评测结果揭示了当前模型能力的不足：在测试的顶级智能体中，仅能在 25 个任务中通过 6 个。而在这些成功的任务中，100% 均属于“修改已有原理图”；一旦任务要求从“空白原理图”开始设计，智能体的成功率则会直接跌至 0%。整个行业在这一专业基准下的表现十分平淡，尚无任何模型能够取得超过 30% 的任务奖励。

然而，KUBench 提供的评测指标为系统性能的优化指明了方向。例如在 KUBench 基础数据集的 4K 分辨率测试中，使用系统内置的默认计算机工具，智能体通过率为 62%；但当切换到 **KU Driver** 后，通过率大幅提升至 80%，同时**节省了 34% 的 Token 消耗**。这主要是因为 KU Driver 允许智能体将视觉焦点聚合在目标窗口上，而非处理整个庞大的桌面图像。为了确保评估器本身的可靠性，团队在引入新任务前，会先利用智能体矩阵进行**奖励黑客攻击**（Reward Hacking: 智能体通过非预期方式绕过逻辑获取高分的作弊行为）和破坏环境测试，只有通过此防线并自动生成代码审查报告的任务才能被归档至 KUBench 库中。

<details>
<summary>Original English</summary>

>> Hello. So thank you Franchesco. Um with cooler driver we gave an agent hands but then the question becomes how can you trust the agent to use those hands correctly and not leave anything broken behind and to answer that we had to build kuab bench so for a show of hands who here has heard of terminal bench or harbor yeah so a few few of you have heard of it and uh if you've ever authored a task for terminal bench then this might look familiar but in kuabench a task is made of three pieces the setup setup function which sets up the machine to initial state. The oracle function which provides a golden trajectory for the task and the evaluator which probes the environment to check if the agent successfully completed the task. Uh unlike terminal bench the oracle here is guey actions. So it looks kind of like pile of gooey when you write that and writing environments takes scale and expertise. On desktop there's more than uh five platforms that we target and um we try to collapse that into a single Python file. So using the Kubaben SDK you can write a guey that works across every desktop platform in a single Python file and use the same SDK to probe that GUI to get usable agent data. Anyone or any agent can author one of these tasks and when you put that to work you get a real catalog. We have currently over 130 verifiable tasks, 42 environments, and across five platforms. And each of these are easily reproducible using our CLI. And the latest addition to our data sets is one that we're proud of. Uh with collaboration with Snorkel AI, we built KUBench Kyad, which tests computer use agents on electrical engineering tasks using software by real professionals and evaluator functions that actually simulate the circuits. But the results are humbling. The top agent that we tested only got a full pass on six out of 25 of these tasks. Of those six, 100% of them involved editing an existing schematic. And when we start the task from a blank schematic, the success rate drops to 0%. And across all the models that we tested, the leaderboard is flat. No model has achieved more than 30% reward. But once you can score something, you can improve it. If we take a look at the Kua bench basic data set scaled up to 4K resolution uh testing an agent they typically get around 62% pass rate but when you switch the agent computer tool from the built-in one to KU driver the pass rate jumps from 62% to 80% using 34% less tokens and this is primarily because KU driver focuses on a window rather than the entire desktop but our evals might say you can trust model XYZ at task whatever. But how can you know that the task how can you know that the eval can be trusted? So before we test a task against any agent, we first try to break the environment ourselves. We have a matrix of agents attempt to do reward hacking and attempting to break the environment and we take all that data and we compile it into a nice code rabbit style code review and only tasks that survive our pipeline can enter the data set. And if you ask us how we trust that agent, the answer is that it's just evows all the way down. But to measure the intelligence of an agent, you can't just measure its ability to successfully perform actions. You also have to measure its ability to understand the world that it's operating in. Every run that we record can be forked through any moment in its trajectory to give you the state of the computer at that moment. From there we can probe a model asking to predict the reward, the internal state or any other observation of the computer and compare it against the fork. And that prediction is the world model of the agent made measurable. And with that um I'll let Robert take the stage.

</details>

### 弹性算力：KUA Fleet 与异步沙箱温池

在强化学习（RL）训练中，传统的架构设计往往会在智能体执行完一个任务后，等待新的物理沙箱启动，或者等待当前沙箱重置。由于沙箱重置和冷启动时间较长，导致高昂的 GPU 算力长时间处于闲置（Idle）状态。在显卡成本极为高昂的当下，这种闲置带来了巨大的资金流失。

针对这个问题，Cua 团队推出了 **KUA Fleet** 基础设施。虽然可以通过优化容器镜像来缩短沙箱冷启动时间，但在实际的智能体开发中，研究人员经常会给出高达 40GB 以上的巨型环境镜像，这种体积导致快速冷启动在物理上变得不切实际。为此，KUA Fleet 引入了**按需自动伸缩的沙箱温池**（Demand-based Autoscaler with Warm Pool）：
* 基础设施实时感知当前有多少 GPU 节点需要运行沙箱。
* 动态调整并维持一个温热的沙箱池（Warm Pool），使得 GPU 节点一旦完成计算，可以立即连接到已经就绪的下一个沙箱，无需等待重置。
* 这种按需的温池容量调节完全自动化，可自适应长达数天的多机多卡训练任务（Multi-day Training Run）。

尽管维护温区沙箱在基础设施端产生了一定成本，但由于沙箱主机的算力成本远低于 GPU Workers（通常便宜 2 到 4 倍），这种用低成本算力缓冲高成本算力的方法，成功实现了 GPU 计算资源的满载运行，大幅降低了训练的整体 TCO。目前，KUA Fleet 能够为 Windows、Linux 和 Android 系统提供即时的沙箱接入，而 macOS 的即时沙箱支持也已在开发计划中。

在最后的问答环节，团队针对 Android 生态的后台运行进行了探讨。Android 系统由于其 Activity 框架的灵活性，能够支持在容器（如 GUI Docker 或轻量 Ubuntu）内进行深度的后台应用测试，但目前该领域的实践更偏向于**工具调用**（Tool Use）而非单纯的屏幕像素控制。

<details>
<summary>Original English</summary>

>> Thank you Dylan. Uh hello everybody. Uh I am the chief infra officer at Kua and I'm here to talk to you about um how you're probably leaving a lot of money on the table uh with idle GPUs if you do RL training uh for computer use agents. So I kind of want to introduce this uh diagram to y'all. Uh could I get like is is there like general familiarity with this diagram or is this like something that most of us haven't seen before like any anyone? Awesome. Very niche. Um Almost everything on this is not really important for what we're talking about, but the blue portions are um and what those basically represent are GPUs uh generating tokens for um RL uh training. And if you zoom in on this a little bit, you can kind of see like how this typically looks like with a sandbox environment is you're going to be generating some tokens um and then you finish your task on a sandbox and then you're waiting for either like a new sandbox to spin up or for your existing one to reset. Uh the problem here is that like this is just pure cost. um your GPU really isn't doing anything useful here and you know I don't know if you've heard but GPU time is pretty expensive right now. So um as you're scaling this cost really compounds a lot and you really want to focus on minimizing this if possible. So one thing that you might try to do is uh minimize the startup time of your sandbox. And I mean you should do that like that's a great thing to do but uh you know especially for computer use style environments sometimes this can be a little bit impractical. Um you know your researchers might give you like a 40 gigabyte environment and that might just be necessary and it takes a long time to pull that down and start it up. So you know how do you how do you design your training infrastructure so that you can minimize the GPU startup or the minimize the startup time of the sandbox? uh even when the sandbox is like not well designed to be start up quickly. Um so the way we do the oh man is it not so the way we do this is a pool and this is supposed to be animated but it's not animating. So um I guess I'll just explain to you orally and what what that is is uh so we have like a a set of GPUs here which all want to use a sandbox and what we will do is that we use a demandbased autoscaler to detect um how many GPUs like currently need a sandbox and we can grow the pool to be that size uh on demand. And what that means is that uh if you have let's say like you have a warm pool that you want to allocate to your GPU cluster, you don't actually need to know upfront what that warm pool size is. We can figure out what that warm pool size should be for you um on demand. And that might even change over the course of your multi-day training run. Uh you might start needing a lot of sandboxes, but then as your generations get longer, you might need less. So these also could be like, you know, easily uh two to four times cheaper than your GPUs. So having a little bit of redundancy here, uh you still wind up saving money because you're maximizing the use of your GPU time. Um yeah, come see me after if you want to see the animation because it's it's cool. Um so yeah so now when you have like this like uh redundancy in your pool you're paying the cost of that startup time on the infrastructure side not on the GPU side so your GPU workers have full utilization um yeah and then because we use this we can give you instant sandboxes for your GPUs for Windows Windows Linux Android uh and Mac OS is coming up Um, and I'm going to hand it back to Franchesco to uh close it out for us. >> Lovely. Uh, thank you Don, thank you Rob for taking this over. Um, we do have like plenty of time for Q&A. So if you guys like have any questions like happy to um take them either for quad driver qua bench basically what Dylan presented or qua fleet uh which is like what uh Robert covered any questions otherwise we can wrap this up. Oh, I see. >> Um, so the story for mobile Android there is very far you can go. Um, we are talking with the arm team because they do have like an arness that runs on Android. I guess like if you're talking about background there is some level of like background that can happen if you containerize a workload and basically on Android you can even like run your own container or like sort of like Ubuntu or like GUI docker container uh within Android um but yeah the Android ecosystem especially compared to iOS is more inclined to that form of like background uh computer use but it's more towards like tool use than really like controlling GUI interface. Um we work with the activity framework and uh do tool use in the background. >> Cool. Thank you guys.

</details>