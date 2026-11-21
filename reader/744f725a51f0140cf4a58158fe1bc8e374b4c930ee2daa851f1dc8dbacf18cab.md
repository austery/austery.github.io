---
author: AI Engineer
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pz74r-4dGfQ
speaker: AI Engineer
tags:
  - self-improving-agent
  - software-factory
  - agent-evaluation
  - prompt-engineering
title: 构建自我改进的 AI Agent：利用评分与反思优化系统配置
summary: Warp 的 DevEx 工程主管 Ben Holmes 介绍了如何通过收集 Agent 会话轨迹、基于 Rubric 打分、并让自我改进 Agent 定期分析失败记录提出 PR，以此自动化优化 Agent 技能与配置。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ben Holmes
companies_orgs:
  - Warp
products_models:
  - Warp Factories
  - Skill Doctor
media_books: []
status: evergreen
---
### 自我改进型 Agent 与软件工厂

我是 Ben Holmes，在 Warp 担任 DevEx（开发者体验）工程主管。今天我将探讨构建自我改进型 Agent——即那些能够回顾自身过往工作，并找出如何改进自身配置的 Agent。作为一点背景介绍，我负责 Warp Factories 项目，这是一个开放灵活的基础设施，旨在帮助大家构建属于自己的软件工厂，而且至关重要的是，这些工厂能作为技术栈的一部分实现自我改进。今天我不会过多展开软件工厂的整体概念，而是聚焦于其中一个关键部分：让 Agent 内省自身在系统中所做的所有工作并提出改进建议，使 Agent 随着时间推移表现得越来越好。

<details>
<summary>Original English</summary>
I'm Ben Holmes and I'm a DevEx engineering lead at Warp and I'm going to be talking about building self-improving agents, agents that look through their past work and figure out how to improve their own setup. Uh so for a bit of context, I work on Warp Factories, which is open flexible infrastructure to help you all build software factories of your own and crucially ones that improve themselves as part of the stack. Uh I'm not going to be talking too much about software factories as a whole today, but I'm going to be talking about one crucial part of it, which is having agents introspect all of the work that they do inside of one of those systems and suggest improvements so that the agent performs better and better over time.
</details>

为了明确定义，我先从大家听到“软件工厂”时可能会想到的概念讲起。它是软件开发生命周期自动化的一种构想。你可能见过它被描述为一条流水线，由不同 Agent 执行不同任务并进行交接。你可能也见过它表现为一个轮环，就像这里展示的那样：从任务列表、看板、Slack 消息或任何跟踪工作的地方开始；然后由一队 Agent 流水线式地进行调研或分类（triage），也许还会与人类合作编写规范（spec），接着实现该变更，并引入计算机使用（computer use）来截屏和录屏，从而在最终产出一个真正优质的 Pull Request；其间可能还会穿插几轮对抗性代码审查（adversarial code review），确保其准备好接受人工检视。另一方面，还可以让 Agent 监控系统，如此循环往复。

<details>
<summary>Original English</summary>
Uh so I'm going to start by just presenting what you might think of when you hear the word software factory for a bit of definition setting. It's the idea of automating the software development life cycle. You may have seen this as an assembly line of different agents doing different things and handing off. You may have also seen it as a wheel as you see in this case where you start from a task list, a board, Slack messages, wherever you're tracking work and you have an assembly line of agents go through the process of researching it or triaging, maybe working with a human to write a spec, implementing that change, and bringing computer use into the picture to take screenshots and recordings so that it's actually a good pull request that you get on the other side. And also maybe doing rounds of adversarial code review in the mix uh to make sure that it's something that is ready for human eyes. Um and on the other hand you have agents monitor the system and around and around we go.
</details>

### 工厂工程与自我改进闭环

但我认为更有意思的部分，是围绕让这个轮环尽可能高效运转所进行的各种“元工程”（meta-engineering）。目前可能有一些词在流传，比如 meta engineering、gardening（修剪维护），或者我们一直在用的词——工厂工程（factory engineering）。它的核心理念是真正投入工程工作，去改进驱动 Agent 本身的系统。在这个系统中有许多可能想要优化的方面：可能是驱动 Agent 的技能（skills），可能是改进代码架构并进行静态分析以确保 Agent 在代码库的正确部分工作。我听到本届活动的赞助商比如 SonarQube 等在这方面做了很多探索。

<details>
<summary>Original English</summary>
Uh but the more interesting part I would say is all of the sort of meta-engineering that goes around making that wheel run as efficiently as it can. Um so a few terms have been maybe floating around right now like meta engineering, gardening, or something that we've been using which is factory engineering. It's the idea of actually putting in engineering work to improve the system that is driving the agents themselves. And there are a lot of things that you might want to optimize inside of that system. It may be the skills that are driving the agents, it may be improving the code architecture and doing static analysis to make sure the agents are working on the right parts of the code base. I've been hearing a lot about like SonarQube and other sponsors at this event that are doing things in this vein.
</details>

我们今天要讨论的改进闭环，专门围绕 Agent 的**技能**和**配置**展开。这个闭环大致是这样的：让 Agent 审查它们过往的会话。你可以设置一些评分 Agent，对这些会话的完成质量进行打分。可以把这理解为一种 LLM as a judge（大模型担任裁判），根据你定义的标准（rubric）在效率、代码质量或测试覆盖率等维度上进行评审。对团队所做工作的海量会话进行评分后，便能找出所有失败案例，查明这些失败发生的原因；接着，也许由一个通过定时任务（cron）唤醒的 Agent 提出改进建议。随后你可以继续评估、观察评分的变化，依此类推。

<details>
<summary>Original English</summary>
The improvement loop that we're going to be talking about is specifically around agent skills and configuration. And the loop is going to look something like this. It's the idea that you can have agents review their past conversations. You can set up some scoring agents to score the quality of how those conversations went. So, think of this like an LLM as a judge reviewing against rubrics that you define across tricks like efficiency or code quality or test coverage. And then once you graded a whole lot of conversations across all the work your team is doing, you could find all the failures, figure out reasons that those failures are happening, and then maybe an agent wakes up on a cron to suggest improvements. And then you can continue evaluating, seeing how the scores perform, and so on.
</details>

### 集中收集会话轨迹与元数据

接下来我将把这个轮环拆解为各个环节，逐一进行讲解。闭环的第一步，是将所有 Agent 会话集中到一处，以便 Agent 能对团队正在进行的所有工作进行推理。如果你使用的是 Claude Code、Codex 或 PI 等本地运行的 Agent，它们是以文件形式保存在系统中的。例如 Claude 会有一个 `.claude` 文件夹，Codex 也会有对应的文件夹。如果你只是想优化自己的单人（single-player）环境，这已经足够了。我其实跟一些团队聊过，他们设置了 S3 存储桶和自动化脚本，将每个人的 `.claude` 文件夹打包压缩上传到共享的 S3 实例中，仅仅是为了把大家的会话汇总到一处。这确实是一种做法。

<details>
<summary>Original English</summary>
So, I'm going to break down that wheel into the individual segments that we can talk about each of them individually. So, the first part of that loop that I showed you is getting all of your agent conversations in one place so that the agent can actually reason about all the work that your team is doing. If you're working with you know local agents like Claude code or codex or pie or any of those, those are going to be files on your system. So, Claude you're going to have a Claude folder world that lives, codex you're going to have a codex folder, and that works well enough if you want to sort of optimize your single player setup. I've actually talked to teams that set up an S3 bucket and an automation to like take everyone's dot Claude folders and zip them up and put them in a shared S3 instance just so we have everyone's conversations in one place. It It's a way of doing things.
</details>

不过还有其他方式可以集中这些信息。如果你使用的是软件工厂系统，这种能力某种程度上是随箱附带的。这里的设想是 Agent 运行在共享计算环境中，而不是每个人的独立笔记本电脑上；每个人都把任务发送到这个共享环境中。这可以像 Open Claw 上的长期运行计算实例，也可以是为每次运行单独启动的隔离沙盒。如果使用 Warp Factory 架构，则是为每个执行任务的 Agent 提供隔离的 Docker 沙盒。使用其他云端运行器（cloud runners），大致也是类似的系统架构。但核心思想一致：我们需要设法将全团队的所有会话收集到同一处，以便于内省并推导如何改进系统。如果所有任务都流经同一个云端运行器，这一切几乎是水到渠成的，因为所有 Agent 轨迹（traces）都归属于同一个实例。

<details>
<summary>Original English</summary>
Um but there are other ways that you can sort of centralize this information. Uh if you're using a software factory system, it kind of comes for free. This is the idea that agents are running inside of maybe a shared computer. So not on everyone's individual laptops, but like a shared computer that everyone's going to send tasks into. That might be like a long-running compute instance on Open Claw or it might be like isolated sandboxes that spin up for every run that you do. Uh if you're using Warp Factory setup, it would be isolated Docker sandboxes for each agent working on tasks. Using other cloud runners, you'll probably end up in the same sort of system. But it's all the same idea. We want to find a way to get everyone's team your whole team's conversations in one place so that they're easy to introspect and figure out how to improve your setup. And if you're doing it on one cloud runner where all the tasks flow through, you kind of get that for free cuz all the agent traces belong to a single instance.
</details>

在收集这些内容时，你需要确保一开始就拥有完整的信息。这不仅包括与 Agent 对话的文字记录（Agent 回复了什么、人类回复了什么），还需要所有周边的**元数据**。这意味着工具调用（tool calls）、文件系统调用、连接的 MCP（Model Context Protocol）——凡是将 Agent 与外部世界连接的一切，在开始分析时都应该包含在 Agent 轨迹中。此外，你还需要把**输出结果**也包含进来。这可以是每次会话中产生的代码差异（code diffs）；如果你锁定了 commit 并查看 diff，也可以是最终产出的实际 Pull Request。无论如何，你都要确保具备三样东西：
1. 记录了对话内容的**文本记录**（transcript）；
2. 显示 Agent 具体行为的**工具调用**（tool calls）；
3. 可供评估质量的**输出成果**（output）。

<details>
<summary>Original English</summary>
Um so that's something that's baked in. And inside of that, you're going to want to make sure you have all the information up front. So not just the like transcript talking to the agent, what did it send back, what did the human send back. You also want all of the metadata around it. So that means the tool calls, the file system calls, the MCPs that it's connecting to, everything that connects the agent to the outside world should also be inside of that agent trace when you start doing this analysis. And you also want the outputs to be in there. That can just be the code diffs that live inside of all of your conversations. It can also be the actual pull request on the other side if you like pin the commit and look at the diff. In any case, you just want to make sure that you have three things. You got the transcript of what was said, you've got the tool calls that show what the agent did, and then you have the output which is something that you may want to grade for quality purposes.
</details>

### 定义评分指标：冗余测试、啰嗦度与运行效率

拥有了这一切后，你就可以开始实际评估质量，或者更确切地说，可以让一个 Agent 开始进行质量评分。在这个环节我通常喜欢做个举手调查：在场有多少人觉得自己的 Agent 写的测试太多了？太多的测试。好吧，我以为会更多，但对于看转播的观众来说，现场大约有 40% 的人举手，这已经是个很大的比例了。而在我们团队，举手率几乎是 100%。这可能取决于你使用的模型，也取决于你的提示词指令。但假设你的团队注意到 Agent 编写了大量测试——可能包含多余的测试，或者你在端到端测试覆盖、集成测试覆盖与单元测试覆盖的配比上有自己的见解，大家都在做各种尝试。因此，你可以设置一个名为“冗余测试”（redundant test）的评分器，用于评估在每次会话中 Agent 写多余测试的频率。

<details>
<summary>Original English</summary>
Uh and once you have all of that, you can start actually scoring the quality or rather you can have an agent start scoring the quality. Um so, I like doing a a show of hands for this little part. Um how many people in here feel like their agents write too many tests? Too many tests. Okay, I expected more, but for those at home, it's about like 40% of people, which I think is a pretty big number. On our team, it was about 100% of hands. Uh it can depend on your model, and it can depend on your instructions. But, let's say that your team is noticing your agents are writing a lot of tests. Maybe extraneous ones, maybe you have your own opinions about do you need end-to-end test coverage versus integration coverage versus unit test coverage. People are experimenting with all sorts of things there. So, you might want to set up a scorer for that called redundant test that evaluates how often is the agent writing too many tests across each conversation that it has.
</details>

另一个你可能想评分的维度，是 Agent 与你沟通的方式。那么再做一次举手调查：有多少人觉得自己的 Agent 写的注释太多了？我对这个挺好奇的。好，我不点出具体模型名字了，但我心里有数。

>> [笑声]

>> 这可能有所不同。

但这同样是 Agent 的常见问题，这不仅关乎噪音或视觉观感，因为我们都知道，代码审查目前可以说是最大的瓶颈。Agent 表达变更的效果至关重要，无论是在总结变更时，还是在代码本身留下的注释中，因为这些都会成为快速完成代码审查的阻碍。

<details>
<summary>Original English</summary>
Uh another thing that you may want to score is um the way the agent communicates with you. So, maybe another show of hands, how many people feel like their agents write too many comments? Curious about this one. Yeah, I'm not going to call out the model name, but I I have an idea. Uh

>> [laughter]

>> It it could depend. Uh but, this is also a common issue with agents, and it's not just for noise or for visuals, because we all know that code review is kind of the biggest bottleneck right now. It does matter how well the agent communicates changes, both summarizing them, and also in the comments that it leaves within the code itself, because they can be barriers to actually get a code change reviewed quickly.
</details>

因此，你可能会引入另一个指标，比如我们称之为“啰嗦度”（verbosity）：即 Agent 在与你交谈或编写代码时是否过于啰嗦？这两者本质上是同一件事的体现，即语言掌控力。你可以设置一个评分器来对此进行界定。

我想提及的第三个指标是 Agent 的**效率**（efficiency），这也正说明了在轨迹中保留工具调用和 MCP 调用的必要性。因为当你在某种程度上脱离人工介入（human-in-the-loop）运行系统时——让它们进行越来越长时间的自主运行，可能是在云端沙盒中运行，你并不会时刻盯视会话本身。这时就越来越容易忽略 Agent 执行的所有失败工具调用。现如今的 Agent 非常有韧性，遇到任何阻碍都会想方设法绕过去，而且它们不会把这些告诉你，只会直接汇报最终跑通了。

我们遇到的一个典型失败模式是：在我们的测试框架（test harness）中，技能定义里有大量过时的错误指令，但 Agent 绕过了它们，并且从未向我们报告；它只是通过尝试 ping 一堆端口号来探测环境，最终完成了代码编写。因此我们当时所能察觉的顶多是：“咦，这个 Agent 怎么比预期多花了大约 2 分钟？”但在引擎盖下，其实有巨大的改进空间。这就是你可以作为评分项来评估的内容：仅通过查看工具调用，分析它是高效地达成解决方案，还是在那里空转磨蹭？

<details>
<summary>Original English</summary>
Um so, you may have another metric like verbosity, which is what we call it, which is is the agent overly verbose when it's talking to you or when it's writing code? Both of those are examples of kind of the same thing, which is a handle on language. Um so, you could set up a scorer that sort of defines that. And a third one I like to bring up is just efficiency of the agent, and this speaks to the need for tool calls and MCP calls in your traces. Because when you're running things a little bit uh without a human in the loop, so you're sending them off on longer and longer runs, maybe they're running in a cloud sandbox, so you're not looking at the conversation itself. It becomes easier and easier to miss all of the failed tool calls that an agent does. Like, an agent these days are very persistent and will work around whatever roadblock that they run into, and they won't tell you about it. They'll just tell you that it worked on the other side. And one common failure mode that we ran into was like, in our test harness, there were a ton of bad instructions that were out of date in the skills, but the agent worked around them and never told us because it figured it out just by trying to ping a bunch of port numbers, figure out its environment, and then eventually start doing code. So, the most that we knew was like, "Oh, the agent takes like 2 minutes longer than maybe we expect." But, under the hood, there's actually a lot to be improved. So, that's something you can evaluate as a score to just say, looking through the tool calls, is it efficiently getting to the solution, or is it spinning its wheels a little bit?
</details>

### 评分标准（Rubric）的设计与应用

我可以向大家展示这样一个评分项长什么样。正如大家所料，它就是纯 Markdown。在我们的配置中，它有点像一个专用的技能定义，你可以在其中通过 LLM-as-a-judge 的方法定义要评分的内容。在此处的评分定义中，我们评估的是“效率”，判定 Agent 是直奔结果，还是在冗余步骤和不必要的往复沟通上浪费了精力。

接着我们设定一些标签，定义该标准下的成功与失败。如果你还记得高中写五段式论文时，老师给你的评分细则（rubric）：“如果你写满五段，且只用主动语态不用被动语态，就算好文章”之类。对于那些定义相对明确的事物——效率就是其中之一——让 Agent 按照这种步骤规范来进行检验依然非常有用。

我们设立了这样一个评分标准，让担任教师角色的 Agent 去审查并判定：你在效率上是拿到了良好评级，还是低于基准线？你可以自行决定及格和不及格的标准。在我们的例子中，分界线也许就在列表的正中间：如果是 0.4 或 0.2，就属于不及格等级，说明该会话中出了问题；而在其之上则是及格，大概率不需要进一步评估，过程基本正常。

<details>
<summary>Original English</summary>
And I can show you what one of these scores looks like. Uh it's just markdown, as you would probably expect. Uh in our setup here, it'll kind of be like a specialized skill definition, where you can define what thing you're trying to score with an LLM as a judge approach. Um so, here we're evaluating efficiency in this score, saying whether the agent worked towards the result or wasted effort on redundant steps and unnecessary back and forth. And then we set some labels that define what success and failure look like on that criteria. So, if you remember back in high school writing five-paragraph essays, and the teacher gives you a rubric of like, "You wrote a good essay if you have exactly five paragraphs, and you only use active voice instead of passive." That sort of thing. It is still kind of helpful to put an agent through those paces for things that can be pretty clearly defined, efficiency being one of them. Um so, we set up one of these rubrics to have that teacher agent go through and decide, do you get good marks on efficiency, or is it kind of below the bar? And you can decide what pass and fail look like. In our case, maybe the bound is halfway through this list, so if it's a 0.4 or 0.2, that's kind of a failing grade, something went wrong in that conversation, and above it, it is a passing grade, and probably doesn't need to be evaluated. Things went mostly okay.
</details>

下方则是对该评分标准含义的具体定义，它重申了你预期中的一些内容：消耗的人力、信息收集阶段、常规步骤开销等。你应当尽量保持简明扼要，随着使用逐步构建完善。这是我们提供给用户的模板，但你完全可以只用几个要点和你自己的评分规则来配置并自行测试。这与其说是一门科学，不如说更像一门艺术。

设置好所有这些评分规则后，就可以让 Agent 真正开始为会话打分了。以这里的示例会话为例，假设我们想让 Agent 查看一系列会话：比如 Agent 在全栈上下文中实现了一个身份验证（auth）服务。假设存在一个关于构建全栈实现的完整 Agent 会话，PR 已经合并，现在该由 Agent 去给该会话的表现打分了。

于是 Agent 启动。在我们的配置中，对应关系是一次 Agent 运行对应一次会话运行。为了节省 Token，你可以采用随机抽样；也可以针对每一场会话都运行，这完全取决于你的需求。

<details>
<summary>Original English</summary>
And then down here is the actual definition of what that rubric means and it's going to restate some stuff that you would expect. So, cost human, the information gathering phase, routine step overhead. And you should keep this as succinct as possible and just build it up as you go. Um this is a template that we like to give to people, but you can set it up with literally just like a couple bullet points and just your rubric and test it out yourself. It's more of an art than a science. Um but once you have all these scores set up, then you can start having agents actually grade the conversations. So, over here, let's say we have uh some sample sessions that we want agents to look through uh starting with like an off service that the agent implemented in a full stack context. Let's say that we had a full agent conversation about building a full stack implementation of this and the PR was merged and now it's time for an agent to go grade how that conversation went. Well, the agent will spin up. In our case, we're saying one agent per conversation or one agent run per conversation run. You can set it by random sampling for, you know, just the sake of tokens or you can run it across every conversation. Really depends.
</details>

假设在一次随机抽样中，系统挑出了这笔会话，并指示 Agent 按照各项标准逐项打分。按流程顺下来：
- 审查测试覆盖率时，它可能会发现：“针对 auth 服务写了大量的单元测试，而我们的指导准则明确说明应主要倾向于端到端测试。”因此，由于它没有很好地遵循预期指令，我们可能会给它判定为“不及格”（fail）。
- 接下来看啰嗦度，表现其实很清晰。它选用了一个不写代码注释的新模型（在座的有人用 GPT 吗？我不清楚）。总之它确实没有写太多冗余注释，PR 非常容易理解，因此得到了“及格”（pass）。
- 再看效率指标：假设它在测试环境中做了大量的摸索尝试，以查明最初应如何测试这项变更，而实际上它本应预先获得关于此项的指引。那么在该项评分上，它大概率也会得到不及格。

再次说明，及格与不及格仅仅取决于它是否低于我们在标准细则中设定的及格线。

<details>
<summary>Original English</summary>
Um but let's say in a random sampling, it pulled out this one and then told an agent to grade across each of those criteria. So, walking down the line, it might say, "Looking at the test coverage, it wrote a ton of unit test for the off service when our guidelines say that you should mostly prefer end-to-end test." And so, maybe we give it a fail because it didn't really follow the instructions that we expected. And then maybe for verbosity, it was actually pretty clear. It was using a new model selection that doesn't write code comments. Uh go GPT, anyone anyone in the room? I don't know. Uh but let's say that it didn't really write too many comments. It was very easy to understand the PR, so it gets a pass. And then moving on to efficiency, let's say it was trying to do a lot of exploration in its test environment to figure out how to test this change in the first place when really it should have had some upfront instruction on that. And that would probably be a failing grade on that score. And again, pass and fail is just did it fall below the line on the rubric that we set.
</details>

### 从聚合评分到自我改进：Skill Doctor 与实践案例

你可以对每一次 Agent 会话持续运行打分。通常以“PR 合并”作为触发器，启动一个 Agent 按照你的评分标准去审查会话。久而久之，你就会积累起关于会话表现的大量聚合数据。其中每一份记录都会包含通过率与失败率（即在各项定义下是及格还是不及格），并且还会由 Agent 说明具体是通过还是失败的原因。

这些分析结果随后便构成了上下文，供另一个 Agent 决定该实施哪些改进。回到前面提到的轮环，我们的设定方式是：会话一发生就立即进行打分；然后通过定时任务（cron job），比如每 24 小时对过去 24 小时内的会话样本进行遍历。假设有 200 场会话，系统将其筛选过滤出失败的案例，再将这些记录了“哪里失败以及为何失败”的报告输入给一个**自我改进 Agent**（self-improvement agent）。我们告诉它：“这 50 场会话失败了，这是每场会话留下的分析记录。请找出共性。如果你想做架构调整，这里为你开放技能仓库和代码库的访问权限。”

<details>
<summary>Original English</summary>
Uh and then you can just go through each of your agent conversations and continue scoring them. So, automatically, usually the trigger being a PR merged, kick in an agent to review that conversation across your grading criteria. And then over time, you'll start aggregating a lot of data on how conversations go. And each of these will include like the pass and failure rates. So, did it pass and fail across each definition? And then you also have an agent describe why one of those failures or passes happened. And then this becomes context that another agent can use to decide what improvements to make. So, the way that we set it up, going back to this wheel, is the idea you grade conversations as soon as they happen. And then maybe on a cron job, every 24 hours, go through a sampling of the past 24 hours of conversations. Maybe there's been like 200. Filter it down to the failures. And then pass in all of those failing reports that describe what failed and why to a self-improvement agent. And tell it these were the 50 conversations that failed. Here are the notes that were left on each conversation. Go ahead and find commonalities. Here's access to our skills repository and the code base if you want to make architecture changes.
</details>

在我展示的这个简短片段中，由于冗余测试在很多 PR 中频繁出现，它或许会添加一个测试金字塔（coverage pyramid）。我还可以展示另外几个例子，包括一个大家可以带回去使用的技能，以及我们在 Warp Factories 内部构建的自动化系统。对大家来说，最容易尝试的是一个叫作 **Skill Doctor** 的工具，访问 `warp.dev/skilldoctor` 即可找到，我稍后会展示链接。这是一个可以在单人环境中运行的技能，它能遍历 Claude、Codex 或其他工具中的所有 Agent 会话，完成一次性打分。如果你以前没用过这种方法，好奇自己的会话中藏着哪些盲点，可以直接在自己的环境里运行它看结果。这是我在构建当前项目的一些代码会话上运行的样本；从旁边可以看到，出于节省 Token 的考虑，它是分批次评分的，并针对我们关心的所有指标生成了评分报告。在这个测试环境中，它评估的指标包括效率和代码质量。

<details>
<summary>Original English</summary>
Um so, in this little snippet I showed, maybe it adds a coverage pyramid because redundant tests are popping up across a lot of PRs. And I can show you a couple other examples. Um both in a skill that you can take home, and also the automated system that we have inside of Warp Factories. So, this is going to be the easiest one that y'all get to try. Um so, it's called Skill Doctor. It's something you can find at warp.dev/skilldoctor. I'll show the link in a second. Um but this is a skill that you can run on your single-player setup, and it'll crawl through all of your agent conversations and Claude, Codex Buyer, whatever else, and just do a one-time grading. So, if you've been wondering about all the hidden gems in your conversations cuz you haven't done this approach before, you can just run this across your setup and see what happens. So, this was a sample I ran across some code sessions building this project here, and we can see on the side that it grades in batches for a little bit of token efficiency, and it came up with some score reports across all of the metrics that we care about. And this test environment has efficiency and code quality as the ones that it evaluates.
</details>

在闭环的另一端，自我改进 Agent 审查所有这些评分并产出一份报告。我们来看一下——我很喜欢展示这里的动效，大家都很喜欢。这就像一张技能成绩单，展示了 Agent 在我们定义的各项评分标准下的表现。同样，这是单次运行的结果；在实际环境中，你可能希望持续运行它，而不是只在有人想起来时才跑一次。但作为快速找出当前可优化点的初次尝试，它很适合用来摘取低垂的果实（low-hanging fruit）。在这个示例中，它按指标打分后发现某些指标略低于预期，但啰嗦度指标表现合格。

<details>
<summary>Original English</summary>
Uh and then on the other side, the self-improvement agent looks at all those scores and comes back with a report. Um so, let's go ahead and take a look at that. Uh I like to show the animation. We love it. Uh but this is like kind of your skill report card that shows how the agent performed across all of those rubrics that we defined. Again, this is one shot. It's probably something that you want to do continuously on your setup rather than whenever someone remembers. But as a first go to just see what you can optimize right now, it's nice to get some low-hanging fruit. Um so, in this example, it graded across these metrics and noticed that these were a little bit lower than expected, but verbosity was fine.
</details>

于是它查阅了评分 Agent 给出的所有批注，并对技能构成提出了若干修改建议。这正好呼应了我之前提到的情况：它注意到 Agent 在测试机器上总是在争抢端口号，并不真正理解环境是如何搭建的。因此，它建议对**端到端测试技能**进行修改，让 Agent 获得更明确的指引——先查找可用端口号再去操作，而不是一味死磕硬撞直到碰巧跑通。这有助于在工具调用上提升效率。

它还注意到，我总是希望用特定的表述来撰写变更日志（changelog），因此它重写了我的 changelog 技能，加入了更规范严格的行文规则。这样每当 Agent 提交 PR 时，我就不必每次都手动往复沟通调整了。

这些问题我自己也能发现，但尤其是端口号那个问题，因为我不会时刻紧盯追踪日志（traces）——如果你使用的是 Agent 测试框架，它通常隐藏在折叠面板后面，或者隐藏在云端——有机制能捕捉到类似问题，就不会将其漏掉。

<details>
<summary>Original English</summary>
Um so, it went through all of the notes that were given by the scoring agents, and then suggested some changes to the skill makeup. And this one is going to mirror what I was mentioning earlier, uh where it noticed that the agent was usually trying to fight for port numbers on the machine that it was testing, and it didn't really understand how the environment was set up. So, this proposed a change to the end-to-end testing skill to have the agent get better instructions on finding a port number first and then going for it instead of just banging against the wall until it got something running. Um so, that can save a little bit of efficiency uh in the tool calls. It also noticed that I constantly wanted to write a different changelog report with the language that was specified, and so it rewrote my changelog skill to have a more uh prescriptive language on how these things are written. So, I don't have to do that manual back and forth every time an agent opens a PR. Um and these were things that I could have gone and found myself, but especially this one on port numbers, since I'm not watching the traces super closely, it's usually just behind like a working toggle if you're using like an agent harness or it's behind the cloud, uh it's nice to pick up on things like this so you don't miss them.
</details>

### 持续监控与自动化 PR 落地

最后我想分享的，是如何让这套系统长期持续运转。哎呀糟糕，刚刚还在的，我失去了 staging 环境的访问权限。不过没关系，我至少可以用语言来描述一下。

那是一组针对已记录分数的图表。我之前在向一位在其测试框架中使用记忆（memory）系统的朋友解释这个概念：记忆系统确实是让 Agent 进行内省的非常有效的方式，你可能听说过让 Agent 在夜间“做梦”、思考白天的会话表现，这与我们今天讨论的内容非常相似。但这套机制唯一缺失的一环在于：Agent 到底做出了什么决定、从所有会话中提炼出了什么结论，过程是高度不可见的。

在使用评分机制时，拥有一个能够说明所有会话走势的实际仪表盘非常有价值。我在这里手绘一下：如果你拥有随时间变化的效率趋势图，聚合数据就变得非常容易。我还没现场演示过这个，来试试看。

你可以追踪效率得分随时间的波动情况。Agent 会不断对配置进行打分，平均得分可能在 50%、60% 左右；当你对 Agent 配置做出修改时，就能将其与分数的拐点对应起来。这样一来，你不仅让 Agent 实现了自我改进，还掌握了明确的佐证：“我上线了这项修改，并获得了这样的成果。”因此你可以确信，当合并了它提议的技能修改后，系统的另一侧确实产生了实质性的改变。你可以明确指出：“这里出现了一个拐点，这正是我合并该技能的时间点，可以看到效率随之提升了特定百分比。”通过将量化评分引入自我改进闭环，你就能获得这种清晰的全局视野。

<details>
<summary>Original English</summary>
Um so, last thing that I'll leave you with is how you can run this continuously over time. Uh oh, shoot, it was just there. No, I lost access to my staging. Uh well, I can at least describe with words what that was. Uh which is the set of sort of graphs on the scores that are written. Because one thing I was actually explaining this to someone who uses like a memory system in their harness. Uh and memories are a really useful way of having agents like introspect. Maybe you've heard of like dreaming overnight and thinking about how conversations went. It's very similar to what we talked about here, but the one part that's kind of missing from that is it's very invisible what the agent actually decided or what takeaways that it got from all the conversations. It's useful when you're using scoring to have an actual dashboard that explains how all of those conversations went. So, I'll kind of draw it out here where if you have like the efficiency over time, it's pretty easy to start aggregating data. I've not practiced this live. Let's try it. Uh where maybe you can actually track over time how the efficiency score has been fluctuating. So, the agent's constantly scoring setups and it's giving grades of like 50%, 60% on average, and you can attribute changes that you made in your agent setup to inflections in the score. So, not only are you having the agent improve themselves, you also have some proof points of like oh, I shipped this change and I got this result out of it. So, I actually know that when I merge that skill that it suggested something real happened on the other side. So, you could say oh, there was an inflection point here. This is when I merged the skill and I can see that efficiency went up by a certain percentage. By having scores in the loop with self-improvement, you can get that sort of view into things.
</details>

这是我们用来提议这些自我改进 PR 的仪表盘。在 Warp Factories 中，如果你用这套方案搭建软件工厂，Agent 便不再是一次性运行，而是无时无刻不在为会话打分。接着，通过定时任务，Agent 会审查这些评分，并提出用于改进环境配置的 PR。

这是目前需要我们团队审查的待办收件箱。这就是我们实际运行的 Agent 配置，涵盖了支撑我们团队运转的所有不同 Agent。

我们可以查看其中一个已经合并的 PR：它发现在**分诊技能**（triage skill）中存在问题，由于缺少允许其衍生子 Agent（sub-agents）的某些配置，导致它一直在死磕摸索“我该如何创建子 Agent”，白白浪费了大量工具调用。自我改进机制捕捉到了这一点并建议：“下次请在工厂配置中打上这部分补丁，这能帮你节省 Token。”这就是我们合并进去的众多示例之一，它们让我们的 Agent 变得更加高效、质量更高。

<details>
<summary>Original English</summary>
And this is the dashboard that we have for proposing those self-improvement PRs. So, in Warp Factories, if you set up like your software factory with this, instead of running it one time, the agent is continuously scoring conversations all the time. And then on a cron, an agent can look through the scores and suggest PRs to improve your setup. So, this is the inbox of things that need our team's review right now. This is actually our agent setup. So, this is across all of the different agents that back our team. And we can take a look at one of them that was merged, where it noticed an issue in the uh triage skill, where we were missing some config to let it spawn sub-agents. So, it was continuously like banging its head trying to figure out how do I make sub-agents? And it just waits a bunch of tool calls. This found it and suggested, "You want to patch that part of your factory config next time. That'll save you some tokens." Um so, this is one of many examples that we've merged in that just make our agents a little bit more efficient and higher quality.
</details>

如果大家对这些思路感兴趣，可以去了解一下 Warp Factories，直接通过 Google 搜索就能找到；或者也可以搜索 Warp Skill Doctor 来试用我提到的那个技能，在自己的环境中测试一下，看看能否带来切实的助益。非常感谢大家，祝大家参会愉快！

>> [掌声]

<details>
<summary>Original English</summary>
Um so, with that, uh if you're interested in any of these ideas, you can check out Warp Factories. It's an easy Google search. Um or you can search for Warp Skill Doctor to try out that skill I mentioned as just a way to try this out on your own setup and see if you get a little bit of benefit out of it. With that, uh thank you so much and enjoy the rest of conference.

>> [applause]
</details>