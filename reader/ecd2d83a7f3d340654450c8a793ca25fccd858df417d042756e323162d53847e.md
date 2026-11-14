---
author: AI Engineer
date: '2026-11-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=maitMe9HCvw
speaker: AI Engineer
tags:
  - multi-agent-system
  - inference-time-compute
  - code-generation
  - compute-allocation
title: 优化多智能体编码团队并降低70%成本
summary: Cohere研究员Nuha分享了通过多智能体协作扩展推理期算力的研究。实验表明，团队虽能超越单智能体，但成本高昂。通过将智能体算力集中分配至瓶颈阶段（如ProgramBench中的规划探索），并采用强主导模型搭配廉价工作模型的异构分工架构，团队能在达到前沿编码表现的同时降低70%的成本。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Nouha Dziri
companies_orgs:
  - Cohere
  - Mila
  - Allen Institute
products_models:
  - ProgramBench
  - Commit0
media_books: []
status: evergreen
---
### 推理期扩展的新维度：多智能体协作与成本挑战

大家好。我叫 Nuha，是 Cohere 的高级研究员、Mila 的行业准会员，同时也是艾伦人工智能研究所（Allen Institute）的兼职 PI。今天非常兴奋能向大家介绍如何优化你的智能体团队，并在降低 70% 成本的同时获得前沿的编码能力。这是我在 Cohere 完成的一项工作。

<details>
<summary>Original English</summary>
Hi everyone. My name is Nuha, I'm a senior researcher at Cohere and associate industry member at Mila and an adjunct PI at the Allen Institute to begin. So excited to tell you today about how to optimize your agent team and get frontier coding at 70% lower the cost. This is a work that I did at Cohere.
</details>

在传统方式中，通常有两种途径可以在推理期让智能体变得更强。首先，你可以让它思考更长时间，这意味着通过更长的推理链按顺序扩展算力。其次，你可以增加采样量。你在并行状态下运行多次独立尝试，然后对它们进行汇总聚合。

<details>
<summary>Original English</summary>
All right, so traditionally there are two ways to make an agent stronger at inference time. First, you can let it think longer, meaning you scale compute sequentially with longer chain of reasoning. And second, you can sample more. You run many independent attempts in parallel and then you aggregate them.
</details>

但随着智能体承担越来越长的任务，它们可以导航大型代码仓库、编辑代码，并且能在几个小时内持续调试自己的工作。这样一来可能会发生的情况是：上下文窗口可能会爆炸。

<details>
<summary>Original English</summary>
But as agents take on longer and longer task, they can navigate large repo, they can edit the code, they [snorts] can debug their own work over hours. So what can happen here is that the context window may blow up.
</details>

因此我们能看到，上下文窗口最终会被填满，运行时间越长，你等待的时间也就越长。而增加采样量也无法解决这个问题，因为这里的每次尝试仍然必须完全靠自己完成整个任务。对吧？那么，如果我们拆分工作会怎样？

<details>
<summary>Original English</summary>
And so we can see here that, you know, the context window eventually fills up and the longer it runs, the longer you wait. And sampling more doesn't either fix it because each attempt here still has to do the whole task on its own. Right? So what if we split the work?
</details>

在这种情况下，主导智能体（Lead）保留总任务并分发子任务，每个工作智能体（Worker）都从一个全新的上下文开始，因此它可以读取文件、运行测试、深挖日志等等，然后只传回一个紧凑的结果。这样，主导智能体掌握着全局图景；如果任务是可以分解的且智能体可以处理独立的部分，它就能完成得更快。

<details>
<summary>Original English</summary>
So here in this case the key the lead keeps the task and hands out subtask and each worker starts with a fresh context so it can read files, it can run tests, it can dig through logs, etc. etc. and then it can send back only a compact result. So here the lead keeps the full picture and it can finish faster if the task is decomposable and agents can work on independent pieces.
</details>

因此，我们这里讨论的是扩展推理期算力的新维度。像一个团队一样协作。你把任务交给一个编码智能体团队，看着它们为你完成任务。

<details>
<summary>Original English</summary>
And so here we're talking about a new axe for scaling inference time compute. You work as a team. You give a task to a team of coding agent and watch them do the task for you.
</details>

### 团队协调的困境与算力分配问题

但是，扩展团队的规模会非常迅速地变得十分昂贵。随着你加入更多智能体，你的 token 预算可能会爆炸。这实际上提出了一个更难的问题。首先，协调究竟是如何发生的？我们应该如何组织团队，让智能体能够协同工作？

<details>
<summary>Original English</summary>
But then scaling the team gets expensive very very quickly. And so as you add more agents, your token budget can blow up. And it can actually and it raises a harder question actually. So first, how does coordination actually happen? How should we organize the team so that agent can work together etc.
</details>

这就是我们着手要去解答的问题。一个团队应该如何编排，才能既**有效**又**高效**？我所说的**有效**，是指它能实际解决更多任务，从而让我们获得更高的回报。而我所说的**高效**，是指它在达成目标的过程中不会烧光你的预算。

<details>
<summary>Original English</summary>
And so, you know, this is the question that we set out to answer. How should a team be orchestrated to be both effective and efficient? By effective, I mean it actually solves more of the task so we get higher reward. And by efficient, I mean it doesn't burn through your budget getting there.
</details>

既然现在的这些模型极其强大，我就在想：如果我们把一个极其困难的编码任务抛给一个智能体群体，看看它们能做些什么，会怎么样？我们原本期望它们会自动形成清晰的分组，利落地拆分工作并共同构建，顺畅地沟通和协调等等。但实际发生的并非如此。在现实中，这些智能体更倾向于独自解决任务。每个人都走开去构建自己的版本。即使我们要求它们进行沟通，它们大多也只是在讨论一些有时并不重要的事情，而且有时还会不断互相踩脚、发生冲突。它们也更倾向于直接向主导智能体汇报。所以我们当时在思考：我们该如何设计团队，以便能在回报和成本方面，甚至在延迟方面，真正获得最佳效果？

<details>
<summary>Original English</summary>
All right. So, since these models now are extremely capable, I was wondering what if we throw an extremely challenging coding task as a society of agent and see what they can do. And so, we would expect them to automatically form clean groups, split up the work neatly, and build it together, communicate nicely, and coordinate, etc. etc. But that's not what not quite what happened actually. In reality, what happened the agent preferred to solve the task on their own. So, each went off and build their own version. Even when we asked them to communicate, they mostly discussed things, sometimes that didn't matter, and sometimes they kept also stepping on each other's toes. They also preferred to communicate back to the lead, etc. etc. So, here we were wondering, okay, how should we design a team so that, you know, we can actually get the best out of it in terms of reward and in terms of cost. And hopefully in terms of latency.
</details>

于是，我们着手弄清楚一个多智能体运行框架（Multi-agent harness）究竟应该是什么样子。我们在思考团队的设计。这里有很多设计选择，每一个选择都会改变团队的表现以及它的成本：
- 首先是**组织架构**：你如何构建团队结构？谁来主导？工作智能体到底应该在工作的哪一个阶段介入——规划（planning）、实现（implementation）还是验证（verification）？
- 第二是**通信方式**：智能体之间是应该直接互相交流，还是仅向主导智能体汇报？
- 第三是**团队规模**：多少个工作智能体才划算？应该是 1 个、2 个、16 个还是 100 个？
- 第四是**模型选择**：哪个模型应该扮演哪个角色？我们是否需要在每个地方都使用强模型，还是说更便宜的模型也能完成同样的工作？
- 最后，我们在意的是**软件工程的阶段**：我们应该把更多的工作智能体分配给规划、实现还是验证？

<details>
<summary>Original English</summary>
And so, you know, we set out to figure out what a multi-agent harness should actually look like. And like we were wondering about the team design. So, there are many design choices and each one changes how well the team does and how much it cost. So, first the organization, right? How do you structure the team? Who leads? And at which stage of the work, planning, implementation, or verification do actually workers come in? Um second thing uh is communication. Should agent talk to each other directly or only report to the lead? Third is the team size. How many workers is worth it? Like should it be 1 2 16 100 etc. And fourth, the models, right? Which model should play? Which role do we need, you know, a strong model everywhere, or, you know, can cheaper ones do the same work, right? And finally here that something that we cared about is the state of the software engineering, right? Should should, you know, we should allocate more workers towards planning, towards implementation, towards verification, etc.
</details>

因此，我们实际上将团队设计形式化为一个**算力分配问题**。我们关心的是：**相比于单智能体，每增加一美元所带来的回报**。从单智能体出发，我们要问的是：推理中投入的下一美元在哪里能换取最大的回报？这是我们所关心的。为此，我们定义了一个名为“效率（Efficiency）”的指标，它实际上是四个维度的函数：首先是阶段（工作智能体所处的阶段，是实现、规划、验证还是三者结合）；其次是工作智能体模型（是非常强大的模型还是能力较弱的模型）；然后是工作智能体的数量，以及主导智能体模型等等。

<details>
<summary>Original English</summary>
And so, we actually framed team design as a compute allocation problem. So, what we cared about is reward per added dollar over the solo agent, right? So, starting from a solo agent, we ask where does the next dollar of inference buy the most reward? This is what we cared about. And so, here we actually define a metric called efficiency, and it's actually a function four things. First, the stage, it's the the stage at which the worker is at, whether it's implementation, planning, or verification, or all of them together, we call it We also define that as a function of the worker model. Is it like a very capable model? Either is it a very, you know, you know, less capable model? The number of workers, the lead model, etc. Um, and all right.
</details>

### 分层框架设计与基准评测

为了回答这个问题，我们实际上将多智能体框架设计为一个自顶向下的分层结构。我们刻意构建了一个极简框架——一个轻量的智能体套件，它是分层级的。在这里，我们有一个主导智能体，它根据任务动态决定团队规模应该有多大以及谁该做什么。我们确保框架的每一个部分都是对外暴露的，这样我们一次只需改变一个变量，保持其他一切固定，以此观察每一个变量如何影响回报与成本。

<details>
<summary>Original English</summary>
So, basically, if we To answer this question, we actually design our multi-agent harness as a top-down hierarchy. We build deliberately a minimal harness, a mini suite agent, and it's a hierarchical, as I mentioned. Here, we have a lead, and based on the task, it decides dynamically how big that team should be and um, you know, who should do what. And so, here we made sure that every part of the harness is exposed. So, we could change one choice at a time. We keep everything else fixed and see how each one moves reward and cost.
</details>

更具体地说，一个编码智能体团队是如何开展工作的呢？每个智能体都在一个共享工作区中通过 bash 工具来工作。主导智能体接收任务，并通过我们称为 `delegate_agent` 的工具下发工作。工作智能体只看得到自己的子任务并向主导智能体汇报。它也可以直接与其他工作智能体沟通。主导智能体可以根据任务决定：“我需要启动一个实现工作智能体，还是验证工作智能体等等。”

<details>
<summary>Original English</summary>
Right? And so, here more closely, how does a team of coding agent do work? You can see here every agent works through a bash tool in one shared workspace. So, basically, the lead receives the task and hands out work with a tool we call delegate agent. And then the worker sees only its subtask and reports back to the lead. And it can also communicate directly to the other worker. And so, here basically, the lead can decide based on the task, oh, actually, I need to just, you know, power an implementation worker or the verification worker, etc.
</details>

主导智能体决定派生多少个工作智能体，以及如何合并与整合结果。它还具备恢复工作智能体、终止工作智能体，以及介入监督并告知工作智能体“你在这里犯了错误，修正它”等能力。大家可能会好奇：“当其他工作智能体在工作时，主导智能体在做什么？”我们实际上设计了两种变体：一种是我们所说的**阻塞式主导（Blocking Lead）**，另一种是**异步主导（Asynchronous Lead）**。阻塞式主导在分发子任务后会一直等待，直到每个工作智能体都汇报完毕，在等待期间它不做任何事；而异步主导在其他工作智能体的结果陆续返回时会继续工作，它可以监督其他工作智能体正在做什么，并向它们发送反馈等等。

<details>
<summary>Original English</summary>
And so, as I mentioned also, the lead decides how many workers to sprout, how to combine, also consolidate the results. It also has the capability to resume a worker, to kill a worker, and to tap in and, for example, supervise and tell the worker that you have made [snorts] some errors here, fix it, etc. And so, yeah, and you may be wondering, "Okay, what is the lead doing while the other workers are working?" We actually have two variations. One is what we call the blocking lead, the other one is asynchronous lead. So, the blocking lead actually hands out subtask and waits until every worker reports back. It doesn't do anything, you know, in between. Uh whereas an async lead, it keeps actually working while, you know, the results keep coming from the other workers. It can supervise what other workers are doing, it can send them feedback, etc., etc.
</details>

我们是如何测试这一套体系的呢？我们在一个名为 **ProgramBench** 的基准上进行了测试，这基本上是一个逆向工程任务。智能体从一个空工作区开始，里面只有原始程序的可执行文件（智能体可以运行但不能阅读源码），同时它还会收到一些文档。目标是通过探测该程序来发现其接口、边界用例和行为，然后编写出一个行为完全一致的新实现。这里的任务极具挑战性，涵盖从 SQLite 到 PHP 解释器等。例如在官方网站的排行榜上，在 FFmpeg 任务中，表现最好的模型也只能通过 10% 的测试。这还是前沿模型做到的成绩。因此它非常具有挑战性，对于我们的调研来说是一个很好的测试集。

<details>
<summary>Original English</summary>
And so, how did we test this? We test this on a benchmark called program bench, which is basically a reverse engineering task. So, basically, the agent starts from an empty workspace with only the original program executable, which it can run but not read. And it also receives some documentation. So, here the goal is to basically probe the program to discover its interface, to discover the edge cases, the behavior, and then write a new implementation that behaves in the same way. And then, the task here were extremely challenging. They range from SQLite, sorry, uh for example, the PHP interpreter, and for example, you know, on the leaderboard on the official website, on the task FFmpeg, the best model only passes 10% of the test. So, this is also done by, you know, frontier model. So, it was quite challenging, and it was a good test data for for our, you know, investigation.
</details>

### 阻塞式与异步主导：团队能否击败单智能体？

这里的问题在于：团队能否击败单智能体，是还是否？答案是：**能**。它确实可以击败单智能体，但成本是后者的 4 到 7 倍。我们可以在图表中看到，在极简提示词（minimal prompt）下，带有阻塞式主导的团队比单智能体高出近 10 个百分点，但其成本大约是 4 到 7 倍。可以看到，阻塞式主导的实际表现优于异步主导，但成本更高，且完成时间也更长。

<details>
<summary>Original English</summary>
And so, the question here is that does a team beat a solo agent, yes or no? The answer is yes. It actually can beat a single agent, but at four to seven times the cost. And we can actually see here in the figure that you know, with a minimal prompt, uh a team with a blocking lead, actually, beats the solo agent by almost 10 points, but it costs about uh costs about 4 to 7 times as much. Now, you can see that the blocking actually performed better than the asynchronous, but costs higher, and it actually takes more time to complete.
</details>

我们在这里注意到的是：异步主导不知道在其工作智能体仍在探索时适时等待。在工作智能体的发现传回之前，它就基于自己的猜测开始构建；当报告最终送达时，它早已推进到了下一步。于是它要么忽略这些报告，要么不得不回过头去重做。

<details>
<summary>Original English</summary>
So, what we noticed here is that we noticed that the async lead doesn't know when to wait, when its workers are still exploring. It starts building on its own guesses before the workers finding come back, and then when the reports finally arrive, it has already moved on. And so, either it ignores them, or it has to go back and redo the work.
</details>

有时在工作智能体实际仍在运行时，它就单方面判定任务已经完成了。它会觉得：“好了，完成了，该提交工作了。”于是这些工作智能体的劳动就彻底白费了。而这种问题在阻塞式主导下从未出现过，因为它会等待所有工作智能体汇报完毕，然后再整合工作并提交。

<details>
<summary>Original English</summary>
And sometimes it just decides the task is done while the workers are still actually running. So, basically, it decides, "Okay, done. It's time to submit the work." And so, the work of these workers is simply lost. But then, you know, this problem never occurs with a blocking lead because it will wait until the workers report back, and then it actually consolidates the work and do the submission.
</details>

接下来我想强调的是**提示词工程**。在早期的结果中我们使用的是极简提示词。我们的智能体基于我们提供的提示词和指令来运作，本质上是按我们的要求行事。起初我们尽量做到极简，只告诉主导智能体任务内容、应该创建子工作智能体、向它们介绍任务并说明工具。我们从极简开始，是因为想看看智能体在没有过多干预时的自主行为表现：它们是需要大量指导，还是极简提示词就已足够？我们同时也在探索：如果我们给它一个非常详尽繁重的提示词（Heavy prompt），告诉模型具体应该做什么、遵循不同的规划路径、指导它在从探索规划到实现的整个过程中分发智能体、创建对抗性工作智能体并验证任务等等，会发生什么？这确实带来了巨大提升。

<details>
<summary>Original English</summary>
All right. So, the next thing I want to emphasize on is the prompt minimal. So, I I mentioned, okay, in the earlier results, I we used the minimal prompt, which is an earlier prompt, and I can't emphasize on this enough. This is how our agent operates. We give them prompt and instructions, and essentially, they do what we ask them. And so, the first one, we tried to go very, very minimal. We just told the lead about the task, you know, that it should create you know, sub workers and agents, and it should inform them about the task, and should tell them about the tools. We gave also the lead tools. We wanted to see why we started minimal because we wanted to see how the agent behave on their own. Do they need a lot of guidance, or is it is a minimal prompt enough, et cetera. And so, this is very minimal. We also were wondering, okay, what happens if we give it a very heavy prompt, meaning like, you know, what the model should exactly do. We tell it exactly about different tracks. Say, follow exactly this plan, or try to, you know, delegate agents, and you know, create agent throughout the whole process of the implementation from exploring and planning to implementation, create also adversarial workers, verify the task, etc. etc.
</details>

实际上这起到了很大帮助。相比极简提示词，单单通过更清晰的指令（例如告知它们“不要互相踩脚，这里有一个文件夹，往这个文件夹里写代码”等等），单智能体自身的成绩就跳升了近 6 个点。这包含了大量的引导和提示词微调，但这并不理想，因为我们在上面耗费了太多时间，而这些智能体理应足够聪明地自行找出解法。我们可以看到，无论是异步还是阻塞式团队的表现都在提升，异步主导团队也追赶上了阻塞式团队。一旦我们告知主导智能体如何协调，它就明白了何时该等待，这切实解决了前述的问题。然而，团队表现虽然优于单智能体，代价却是其 6 到 7 倍的成本。既然团队击败了单智能体但开销更高，若把团队视为扩展推理期算力的一种新途径，这下一美元到底该投向何处？我们能否优化智能体架构，在取得优异回报的同时大幅压缩成本？

<details>
<summary>Original English</summary>
And actually that helped a lot. We can see here, you know, compared to the minimal prompt, you know, we can see that the solo agent alone jumps almost six points just from better instructions and telling them, "Okay, don't step on each other's toes. I don't, you know, there is this folder, write in this folder, etc." So, lots lots of guidance and lots of prompt tuning, which is not ideal cuz we spent too much time there. And now these agents are supposed to be smart enough to figure out how to do it. And so, we can actually see that the teams, both, you know, async and blocking, both go up and we can see that the async lead now catches up with the blocking one, right? So, once we tell the lead how to coordinate, it knows when to wait. So, this actually really helped address the problem that I talked about earlier. But again, you know, we have a team that works better than the solo, but it's really really expensive. It costs six to seven times as much as the solo agent. So, we were wondering, now that a team beats a solo agent, but it costs more. So, if a team is a new way to spend inference time compute, where should the next dollar go, basically? Can we actually optimize our agent setup so that actually we get very good reward but at a very, you know, much cheaper cost.
</details>

### 算力配置实验：各阶段工作智能体的价值

为了回答这个问题，我们让同一个主导智能体仅在软件工程过程的**某一个特定阶段**使用工作智能体：
1. **规划与探索阶段（Planning）**：工作智能体仅负责规划和探索。主导智能体分配任务，各个工作智能体去探测二进制程序以明确规划方案，然后向主导智能体汇报计划，由主导智能体独自负责后续的实现和验证。
2. **实现阶段（Implementation）**：工作智能体仅负责实现。主导智能体负责制定计划并在工作智能体之间拆分、分发工作；工作智能体编写代码并向主导智能体汇报代码；主导智能体独自进行验证。
3. **验证阶段（Verification）**：主导智能体负责规划和实现，工作智能体只在最后的验证阶段介入，测试后向主导智能体汇报，由主导智能体决定是否提交。

<details>
<summary>Original English</summary>
So, to answer this question, actually we took the same lead and gave it workers at only one stage of the software engineering process. So, the first setup that we considered here, the workers are only responsible for the planning and exploration, right? So, basically here the lead will give them the task and then each of the workers will go and try to prompt the binary to discover, okay, what kind of plan I need to do, and then it will report the plan to the lead and the lead will take care of the implementation verification. The second one is, you know, workers are only responsible for implementation and so the lead is the one responsible for coming up with a plan, distributing that, splitting the work between workers. they will do the implementation, report back with the code actually to the to the lead. And so, basically and then the lead does the verification on its own. Now, the third actually set up that we had, the lead is responsible for both the planning and the implementation. And then here the workers are responsible to do the verification, which is the final stage and then they will report back to the lead and then the lead will decide whether to submit or not.
</details>

我们想观察额外的智能体究竟在哪个环节最能带来回报。我们的实验结论是：**在 ProgramBench 中，额外的智能体在规划阶段带来的回报最大**。从极简提示词的单智能体到全阶段指导（PIV）的单智能体已有显著提升；而在全阶段重度提示词下使用团队，性能会进一步增长。但是，当我们把更多智能体专门分配给规划阶段时，我们以大约一半的成本获得了与 PIV 几乎相当的性能。因此结论是：额外的智能体在规划阶段以及制约任务的瓶颈阶段能发挥最大效用。在本例中瓶颈正是规划，因为你必须弄清楚二进制程序的行为，并提出接下来首先应该实现什么的详细计划。

<details>
<summary>Original English</summary>
And so, Okay, we wanted to see where exactly extra agent will pay off the most and here are the conclusion of our results like extra agent pay off most in program bench in planning. So, here you can see okay, going from solo with minimal prompt to solo with PIV. PIV is the heavy prompt. Actually, we get like a jump already and then we go with a team of heavy prompting, we get extra, you know, increase and gain in performance. But then now when we allocate more agent towards the planning, right? We can see that we get almost the same performance as the PIV but at half the cost. So, Actually, the conclusion here is that, you know, the extra agent pay off the most in planning and um at at at the task that bottlenecks actually uh the the the task, which is planning in this case because you need to figure out how exactly what what's the binary behavior and come up with an detailed plan on what should you implement first, etc.
</details>

我们计算了前面提到的平均效率，可以看到它在前沿曲线上完全主导了 PIV。**投入在规划上的每一美元所带来的回报，几乎比投入在实现或验证等其他任何阶段高出 1.6 倍**。我们注意到，在实现阶段或验证阶段单纯加倍投入智能体数量并没有实质帮助，成本增加了，获得的性能却和单智能体相同，因而不划算。由于 ProgramBench 只提供黑盒可执行文件，探索发现就是瓶颈所在。规划智能体将这种探测过程并行化，带来了巨大的收益。

<details>
<summary>Original English</summary>
And so, here yeah, I Actually, we computed even, you know, the efficiency average that I discussed earlier and we can see that, you know, it dominates the PIV actually on the frontier. So, each planning dollar buys almost 1.6 more reward than any other stage that we have here, whether it's implementation or verification. And actually, we we we noticed that, you know, you know, doubling down on the number of agents in the implementation stage in the implementation or verification stage doesn't actually really help. We can see that it just increased the cost but we are actually getting the same performance as the solo, so it's not worth it. And so, again, like program Bench only exposes a black box executable, so discovery here is the bottleneck. So, planners paralyze this probing and it brings and they bring lots of benefits, right?
</details>

这就解释了为什么规划工作智能体卓有成效，而验证或实现工作智能体却不然。正如我所提到的，ProgramBench 给你的是二进制程序和文档，在写任何代码之前，你必须推断出程序究竟做了什么。因此，**探索发现是真正的瓶颈**。你也可以从上下文窗口的角度来理解：单个智能体在自身上下文中孤军奋战、探索文件并进行探测，依然会遗漏边界情况；而多个工作智能体在各自全新的上下文中分别探索程序的不同部分，各自向主导智能体交回一份紧凑的报告，主导智能体由此了解到的信息远比单打独斗要多。

<details>
<summary>Original English</summary>
And so, yes. So, this is to explain why planning workers pay off and we were wondering why not, for example, verification or implementation. And, you know, as I mentioned, Program Bench will give you this binary and its documentation. So, before you write anything, you have to work out what the program actually does. So, discovery is the real bottleneck here. And you can also think about this in terms of context, right? So, we have one agent that's exploring, you know, alone files uh in its own context with probing and also still misses edge cases, right? And on the other hand, you know, we have several workers each explore different part of the program in a fresh context and each one hands back a compact report to the lead. So, basically here the lead, you know, learns more than it could do alone.
</details>

### 调用分布与实现阶段的协调失败

为了更直观地说明这个现象，我们分析了实验数据并观察主导智能体下发任务的时间点。我们在图表中展示了规划、实现、验证以及全阶段的情况。每一行代表一次运行，时间从左向右推进：黄色代表规划，蓝色代表实现，绿色代表验证，图中的每个点都代表主导智能体向工作智能体派发一次工作。在规划引导下，所有的任务下发都集中在最开始爆发式发生，在编写任何代码之前完成；工作智能体前去探索并汇报，然后由主导智能体统一构建。而在全阶段 PIV 指导下（没有指定智能体具体分配到哪里），虽然开头也有同样的集中爆发，但主导智能体在后续流程中仍持续不断地派发任务——额外调用了 830 次，但这些调用几乎毫无收益。它们只是增加了成本（大约 500 美元），性能却没有实际提升。两者在规划上获得了相同的回报，但按单次调用回报计算，集中规划策略测得的回报是其 2.4 倍。因此，真正奏效的是**前期集中的一次探索爆发**，而不是贯穿全程的持续派发。

<details>
<summary>Original English</summary>
And so, now, you know, this is also to explain better this phenomena and you can and we actually looked at our data. And we came up with these nice figure based on what we saw and we specifically looked at uh when the lead delegates, right? So, here we have planning, we have implementation and verification and we have all the stages as well. And so, every row that we can see here in the figure is one run uh and actually time goes left to right, right? So, the yellow is planning, the blue is implementation, the green is verification and every dot here that you see in the figure is the lead sending work to a worker. And so, with planning guidance, all the delegation happens in one burst at the very, very first of, you know, the the work before any code is written. So, basically here the the workers go explore and then they report back and then the lead builds. With a full um PIV guidance, where, you know, um there is no um specific guidance on where exactly the the the number of workers should be allocated, we get the same early burst, but then, if you You here, actually the lead keeps delegating all the way through. Another 830 calls and they buy nothing actually. They just increase the cost as we saw. It was around $500, but it didn't actually improve in performance. So, it's the same reward for planning we can see, but it's 2.4 times more reward per call that we we actually measured. And so, what pays off here is is one early burst of discovery and not delegating all the way through.
</details>

为什么实现工作智能体会表现不佳？首先，正如前面提到的，规划是瓶颈所在，如果底层规划没做好，后续就无法成立。在实现分组中只有主导智能体去探索，其发现全量二进制文件和边界用例的能力有限，导致基础薄弱。随后每个工作智能体只拿到狭窄的一小块切片，对全局任务缺乏视野，在各自实现功能时就已经频频出错；再加上它们建立在薄弱的基础之上，问题就更严重了。有人可能会问：“为什么不给工作智能体更多上下文？”我们尝试过，但发现当它们拥有更多上下文时，反而不再恪守具体任务的边界。它们变得过于兴奋，开始构建无人要求的额外功能，结果就是互相冲突踩脚。另一个问题在于通信：它们本应互相沟通以明确分工、避免冲突和重复劳动，但它们并没有这么做。它们各自为战，84% 的消息都直接发给了主导智能体，没有智能体能看到其他人正在做什么。这导致主导智能体不堪重负，无法向其他工作智能体清晰传达问题所在。当实现不够正确时，主导智能体就必须为差距买单，试图弥补重复工作并进行大量代码拼凑，最终导致延迟上升、回报下降且成本昂贵。

<details>
<summary>Original English</summary>
Right? So, why implement workers fall short? Here, first of all, as I mentioned, the plan was the bottleneck. And so, if you don't do it right, it's not going to work out. And so, here we have only the lead that explored. It had limited capacity to discover all, you know, the the edge cases and the full binary. And so, we had a weak foundation and then basically each worker got like a narrow slice. It doesn't have visibility over the entire task and basically they were already doing errors by implementing each feature on their own. That's one problem. And on top of that, they were building on a weak foundation. And also, we noticed that so, here you might ask me that, you know, why not give workers more context? We did. But, we noticed that when you they have more context, actually they didn't respect the boundaries of their specific task. They get excited and then they want to build extra features that nobody asked them for it. So, they just step on each other's toes, etc. The other issue that we noticed is that, you know, they are supposed to communicate together to figure out who's doing what to avoid conflicts and duplicated work, but they didn't do that. They actually they worked alone and 84 of messages go to the lead directly and nobody sees who's doing what. And sometimes here what happens is the lead gets overwhelmed and it doesn't know doesn't communicate well where the problem is to the other workers, etc. So, it can be actually quite challenging. And so, what happens here is that when, you know, implementation is not fully correct, you know, the the the lead pays for the gap. It actually tries to, you know, make up for that duplicated work and does lots of stitching. And so, here what happens is that the latency goes up, and also the reward goes down, and you know, it's also expensive.
</details>

到目前为止我谈论的都是 ProgramBench，但我们也在 **Commit0** 上运行了实验。这里的实验结果截然不同，团队的层级与配置会根据任务的不同而变化。因为 ProgramBench 的瓶颈在规划，向规划分配更多智能体大有裨益；但在 Commit0 中情况并非如此。Commit0 的瓶颈不在规划，因为任务已经给出了代码骨架，文档和单元测试对工作智能体都是已知的，规划方案基本已经摆在面前。要提升回报，瓶颈在于实现本身——你必须把代码实现写对。在 Commit0 中，当我们在实现阶段将智能体数量翻倍时，才观察到了最显著的提升。（我在此不展开展示这部分结果，详情请参阅论文附录。）因此这里的结论是：**你必须把更多智能体分配到制约你任务瓶颈的那个软件工程阶段上**。

<details>
<summary>Original English</summary>
Uh Okay, so basically so far I've been talking about program bench, but we also run experiments also on commit zero. And what I want to say here is that the result like are are different, and the hierarchy and the the allocation of the team is different according to the task. Because the bottleneck for program bench was planning. And so, allocating more agents there really really helped, but for commit zero it was not the case. The commit zero the bottleneck was not planning, because basically you're given the skeleton. So, the docs are known and the unit tests are actually known to the workers. So, the plan is basically given to you. And the the bottleneck was for the you know, for the reward to go up was the implementation. You need to get the implementation right. And so, here when we doubled the number of agent on the implementation stage, this is where we saw the biggest improvement. I'm not going to present results on this. Please check out the paper for for for these results. You'll find them in the appendix. So, the conclusion here is that you need to allocate more agents at the software engineering stage that bottleneck your task.
</details>

### 异构模型团队：强主导搭档廉价工作智能体

规划智能体已经让我们以一半的成本获得了相同的回报。我们进一步探究：能否做到更便宜、进一步削减成本？我们以 GPT-5.6 系列的三款模型 Luna、Terra、Sol 为例进行了实验，它们的能力和成本依次递增。我们提出的问题是：如果我们保持最强模型 Sol 作为主导，并使用廉价模型作为工作智能体，会发生什么？

<details>
<summary>Original English</summary>
All right, so planning already gets us the same reward at half the cost. So, we were wondering, can we go even cheaper than this? Can we cut the cost even further? And so, here we did some experiments, and we focused for example on three GPT-5.6 models, Luna, Terra, and Sol in a this increasing order of capability and cost. And so, like the question here is that what would happen if we keep Sol as the lead, like the strongest model, and then use the cheap models as the workers?
</details>

在此前的配置中，所有阶段都由 Sol 组成，其中主导智能体动态决定团队规模，平均会派生出 5 个智能体。当我们从 PIV 出发将更多智能体分配给规划时，如果把充当子工作智能体的 Sol 替换为像 Luna 这样的廉价模型，我们获得了几乎相同的性能，而**成本降低了 60%**。虽然在绝对性能上有微小损失，但它依然表现优异，相比单智能体最大化了回报并大幅降低了开销。

<details>
<summary>Original English</summary>
Right? So, remember here we used to have this. This is all the P here is the all Sol, you know, model. By the way, here the the the Sol the basic This is the version like of P where the lead dynamically decides on the size of the team and it ended up on average creating and spawning five agents, right? And so, basically here, we have this. We go from PIV, we actually allocate more agent towards P. And basically, when we replace the sole, you know, sub workers with cheap ones like Luna, we actually get almost, you know, same performance but 60% less the cost. Like just we lose a little bit on performance, but it's still good because we're actually maximizing reward compared to the solo and then we're we're getting less cost.
</details>

反过来我们也在想：主导智能体本身能否使用更便宜的模型？从纯单智能体的 Luna、Terra 到 Sol，性能和成本都在持续上升。而对于由同质模型组成的团队（如 Luna+Luna，Terra+Terra），模型能力越强结果越好的缩放定律依然成立。但我们注意到：当我们采用“强主导搭配弱工作智能体”（Sol + Luna）时，能以极低的成本获得与全强模型（Sol + Sol）相当的性能；然而反过来，**廉价的工作智能体无法弥补一个孱弱的主导智能体**。本质上，**主导智能体决定了上限，而工作智能体决定了价格**。在这里，Terra 带领 Luna 工作智能体的表现（51%）依然低于 Sol 单打独斗（57%）。这与 Meta 最近在元推理（Meta reasoning）方面的研究发现相契合：更好的控制器提升了相同工作智能体所能达到的产出上限。

<details>
<summary>Original English</summary>
And so, you know, now the other way around. We were wondering like can the lead be cheap, right? We just even get a cheaper lead. And so, already here, we can see that okay, you know, going from like a cheap lead like solo, Luna, Terra, sole, we keep increasing in performance and also in cost. And so, can we have like this homogeneous team like Luna plus Luna, Terra plus Terra. Already we can see the scaling law the same as the model gets more capable, we get better results. But then, actually, you know, we noticed that when we have a strong lead sole plus Luna, we can get the same performance as sole plus sole, but you know, at much lower the cost. But the other way around like cheap workers can't make up for a weak a weak lead. Basically, the lead sets the ceiling and the workers set the price. Here, Terra with Luna workers still feels sole working alone 51% versus 57%. So, essentially here, the lead sets, you know, basically this also matches Meta's Meta reasoning work recently. Like they just mentioned that a better controller raised what the same workers achieved.
</details>

在此之前，正如我提到的，都是由主导智能体动态决定派生多少个工作智能体，平均为 5 个。接着我们探究：如果我们亲自手动设定各阶段的智能体规模，强制规定团队大小会怎样？我们选用 Sol 作为主导、Luna 作为规划者（因为这是最佳的性价比组合），将规划者数量从 2 个逐步增加到 16 个。观察成本可以发现：**16 个规划者的团队比全 Sol 的规划团队便宜 38%，并且比全阶段使用工作智能体（PIV）便宜 70%**。

<details>
<summary>Original English</summary>
All right. So, so far the lead decided how many workers to spawn as I mentioned and it did on average five workers. Now, we were wondering what would happen. We want to scale ourselves the number of agent at each stage. So, we will impose the team size. So, here, uh going to, you know, work with Sol as a lead, Luna as planners because this was the best um reward cost um um uh relation and we go from two to 16 planners, right? Uh and so, here I can actually look at the cost. You know, the 16 planner team is 38% cheaper than all Sol planning team and actually 70% um cheaper than workers at every stage here for the PID, which is great
</details>

>> [抽鼻声]

>> 因为受限于预算，我们无法进一步扩大智能体数量，但曲线呈现持续上升趋势。显然这里会存在上限，但这种扩展确实非常有效，而且它的花费并没有超过将 5 个 Sol 智能体全部投入规划的成本。我们也尝试在实现和验证等其他变体上扩展团队规模，但完全没有效果。正如前面所见，由于基础脆弱等原因，在这些阶段堆砌智能体毫无帮助。

<details>
<summary>Original English</summary>
>> [snorts]

>> cuz here we and it seems we we you do some budget constraint, we couldn't like scale up the the number of agent further, but it seemed like going up and up and up. Obviously, there is a ceiling to it, but it's really helping and the good news is that it's not that expensive. It's not that it's not more expensive than the five Sol team uh all allocated towards planning. Now, we also uh try to see whether uh scaling up the number the size of the team for the other variants like implementation and verification and it didn't help at all. Uh we already saw that uh you know, allocating teams um agents toward in these stages is not helping because of, you know, the foundation was weak and other considerations.
</details>

### 通信拓扑分析与模型领导能力差异

最后，我们对于智能体之间是如何通信的感到好奇。我们在沙箱中为每个智能体提供了 `send_message` 工具以联系其他任何智能体。我们想探究通信是直接发生的还是经由主导智能体中转，以及通信究竟会带来更好的性能还是更差。首先，智能体之间是否会互相通信？其实不然。**它们基本上都在通过主导智能体进行沟通，84% 的消息来自工作智能体发往主导智能体**。工作智能体之间的直接通信非常少，平均每个任务不到一条消息。因此，即使赋予了互相交流的能力，它们的行为模式依然呈现出层级制：完成自己的任务，向上汇报，并指望主导智能体向对应的子智能体下达指令。这一模式在所有模型上都是一致的——主导智能体与工作智能体的对话频率远高于工作智能体之间的对话，在 Claude Opus 4.7 以及 Gemini 系列的实验中也是如此。

<details>
<summary>Original English</summary>
And so, the last thing we were actually curious about, how do agents communicate, right? And so, we gave every agent uh a send message tool to reach any other agent actually in the sandbox and we were curious whether communication uh happens directly or, you know, it happens through the lead and whether communication will lead to better performance or worse. And so, basically, the first thing is that are they communicating together? Not really. They are actually essentially communi- communicating through the lead. Like 84% of all messages went from a worker to the lead. Worker to worker, you can see that actually very little, less than one message per task. So, even when they can talk to each other, they actually behave like a hierarchy. Like, do your piece, you report up. Expect the lead to communicate back to the right sub-agent, etc. And you can also see this pattern consistent across all models. The lead takes much more talks Sorry, talks much more to workers than they talk to to each other, and this is also true for Cloud Opus 4.7. Also, we did the experiments on Gemini, etc.
</details>

关于回报方面，工作智能体之间额外的通信究竟是否有益？在我们的实验中，我们并未发现它有帮助，原因如下：首先，左图中大约有一半的 Luna 消息甚至根本无法送达，因为格式错误而被运行框架拦截；其次，中间图表显示 Sol 生成的消息文本量大约是 Luna 的 3 到 4 倍。在 PIV 指导下，能力更强的团队整体倾向于发送更多消息，主导智能体对工作智能体的引导也更多，这符合预期。但是右图显示，**说得更多并不意味着回报更高**。对于 Sol 和 Terra，加入消息传递机制带来的变化微乎其微；而 Luna 团队的分数反而下降了 4 到 7 个点，通信似乎只是分散了它们的注意力。我们发现通信主要是在向主导智能体汇报状态，而主导智能体横竖都会收到每个工作智能体的结果，因此这成了一种纯粹的开销，没有讨论任何实质性内容。我想在此明确说明：我并不是说点对点通信（Peer messaging）毫无必要或不应采用，随着智能体规模扩大，它们理应具备高效相互沟通的能力，事事都经由管理者中转并不符合团队协作的实际运作方式。当前这种现象一定程度上归因于我们构建的框架以及任务本身——主导智能体拆分了工作并确保子任务相互独立，工作智能体并不清楚沙箱中还有哪些智能体存在。虽然提供了通信工具，但它们缺乏对彼此存在的可见性，可能需要公告板之类的机制来激励它们主动沟通。我们将此留待未来工作探索。

<details>
<summary>Original English</summary>
And so, also, as I mentioned, we were curious about the reward. Does it, you know, does extra communication between workers help or not? In our experiments, we didn't find it helps, and I will explain why. Um so, first, already you can see, you know, on the left you can see that about half of Luna messages never even get through, like, because they're malformed and the harness reject them, etc. Um and so, we notice also in the middle figure that Sol writes about three to four times as much message text as as Luna. And under the PIV guidance, stronger teams, actually, we can see that they tend to send more messages overall, with leads steering their workers more, which is good. So, we can see that, you know, as the you know, capability of the model so, they message rather more. But then, on the right figure, you can see that more talking doesn't mean more reward. For example, for the Sol and Tora Terra, adding messaging changes nothing, basically, beyond noise. And Luna teams actually lose four to seven points. So, it just seems distracting to them. And we noticed that communication mostly carries status report to a lead, you know, who already receives each worker results, anyway. So, it it was just like an overhead. There was nothing important to be discussed. And I want to be clear here. I don't want to say that peer messaging is not necessary, and we should not do it. I do think it's necessary, and I do think as we scale the number of agents, they should be capable to communicate efficiently together, because it doesn't make sense to all the time communicate through your manager for you to work with your team members. No, it doesn't work like that. I think that it's also a product of our of the harness that we built, and also of the, you know, the task itself, because basically the lead was splitting the work and making sure that each work is independent of the others and so they give them that the lead gives them directly the task and so they are not also aware of other you know, agent in the same sandbox and so we gave them the tool only to communicate together but they had didn't have visibility who exists there and so they have to do extra efforts and maybe a message word would have solved the problem and so would incentivize them more to sort of communicate and to figure out oh, this actually agent is doing something similar to what I'm doing let me communicate or I need more help let me reach out to someone else. Anyways, we leave this to future work
</details>

我们同样好奇其他前沿模型是否懂得如何担任主导。我们在相同的框架和相同工具下测试了另外 5 个模型家族（包括 Opus 4.8、4.7、5 以及 Gemini 家族）。我们注意到 5.6 团队经常进行任务分发，回报增加了多达 7 个点；Claude 的表现十分相似，获得了近 6 个点的提升；然而 Opus 4.7 极少下发任务，收益甚微；Haiku 和 Gemini 分发任务的频率与 5.6 相当，却几乎没有任何收益。因此这里的结论是，必须做好两件事：**主导智能体必须主动选择去分发任务**（由它决定谁来做工作至关重要），**并且它必须切实利用好反馈回来的结果，并在任务正确的阶段进行分发**。

<details>
<summary>Original English</summary>
and so the other thing that we also were curious about is like you know, whether other you know, models frontier models know how to lead. So we also run five other models family with the same harness with identical tools and so here I'm talking about office 4.8.4.7.5 also Gemini family. We noticed that 5.6 teams delegates often and it gained up to 7 points in reward. Cloud on the other hand actually behave much you know, the same gaining almost 6 points but then office 4.7 rarely delegated and actually gained very little. High crew and Gemini you know, delegated as really lead as 5.6 but then gained nothing and so what I want to say here the conclusion is that you know, two things have basically to to go right. The lead has to choose to delegate. This is important because it's actually deciding on who's going to do the work and it has to actually make use of what comes back and at which stage of the task do also delegate.
</details>

### 核心结论与未来展望

总结下来有三点核心启示需要牢记：
1. **多智能体团队是扩展推理期算力的真实新维度**，但代价是其成本会高出数倍。我们虽然获得了高达 10 个百分点的提升，但依然非常昂贵。
2. **把智能体放在何处比盲目堆砌数量更重要**。你必须找出瓶颈所在并在该环节进行团队扩展。
3. **团队无需全员都是顶尖模型**。强大的主导智能体搭配廉价的工作智能体，能以极小的成本代价获得接近前沿水准的表现。

<details>
<summary>Original English</summary>
All right, so here the takeaways three things to remember. The first thing is that teams are now a real new axe for instance and compute but the catch here is that they cost several times more. We got up to 10 points which is you know, great but still it's very very expensive. Now you know, we tried our best to optimize our teams of agent and we were successful to some extent. Still some work to be done, but essentially here the conclusion is that, you know, where you put agent matters more than how many. So, you need to find the bottleneck and scale the team there. This is what matters the most. And finally, the team does not have to all be strong. Like, a strong lead with cheap workers can get you near frontier results at actually a fraction of the cost.
</details>

接下来有哪些开放性问题？
- 首先是**层级制与自组织之辨**。我们在工作中测试了最多 16 个工作智能体的层级结构，但由数千个智能体组成的团队该如何组织、通信并分配算力？在给定任务、预算和截止日期的情况下，智能体能否自行设计团队架构？我们认为是可能的，但需要深入研究。
- 其次是**替代性的通信形式**。如前所述，84% 的消息流向主导，只有 4% 发生在工作智能体之间。当编码项目规模扩大到超出单个主导的管理能力时，有效的通信机制是否会自然涌现，还是需要专门训练？主导智能体又该如何适应不同任务？为每个任务花费大量时间调优提示词、撰写极详尽指令的做法是不可持续的，主导智能体应当自行领悟如何根据任务来组织团队。
- 最后是**多智能体的安全性与防护**。鉴于“Penny Lane 事件”等情况，这怎么强调都不为过。现在智能体团队能够 7x24 小时在无监督状态下自主运行，能力极其强大，且我们面对的已不仅是单个智能体，而是智能体团队乃至智能体集群。核心问题在于：我们如何保障系统和基础设施的安全？我们迫切需要找到对齐这些模型的方法。

感谢大家坚持听到最后。特别鸣谢第一作者 Kenan 和 Daniel 的辛勤付出。想要了解更多信息，请扫描二维码阅读论文和博客。非常感谢大家的聆听！

<details>
<summary>Original English</summary>
And so, what's next here? These are open questions that we are so curious and excited about. First, here we're excited about this hierarchy versus self-organization. We, in our work, we tested up to 16 workers in a hierarchical lead-worker structure, but then how should teams of thousands of agent be organized, communicate, and spend compute? Can agents design the team themselves given task, budget, and deadline? We think so. And so, but that requires, you know, careful investigation of the problem. Now, the second thing is that we think that there must be alternative forms of communication. As I mentioned, we observed 84% of messages going from workers to the lead and only 4% between workers. And so, as I think project outgrow, like coding project, you know, they can outgrow grow one lead, will effective communication here emerge, right? Will scale or like, should it be trained, right? How should the lead adapt to the task? It's not scalable to just for each task that we have, we spend, you know, a huge amount of time optimizing the prompt and giving very detailed instruction to the lead. That should not be the case. The lead should figure out how to actually, you know, organize the team according to the task that it has. Um now, finally, uh multi-agent safety and security. Um you know, uh this is I can't emphasize on this enough, especially given what happens with the Penny Lane incident. You know, right now we have teams of agents that can run autonomously 24/7 with no supervision. They're quite capable and we're not talking anymore about the single agent, but we talking about teams of agent and even swarm of agent. And so, here the the key question is that how do we secure our systems and our infra? And we need to urgently basically figure out ways on how to align these models. All right, with that I actually would like to thank you for making it to the end. I want to give a special shout out to the first author here, Kenan and Daniel, for their hard work on this. And for more information, please check out the paper and the blog using these QR codes. And thank you so much for listening.
</details>