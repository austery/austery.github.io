---
author: How I AI
date: '2026-06-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JoXbk2fm7jM
speaker: How I AI
tags:
  - prompt-engineering
  - agentic-workflow
  - loop-engineering
  - claude-code
  - automation
title: 从手动 Prompt 到 Agent 自动循环：Claire Vo 深度解析 AI 代理与循环工程
summary: 在本期《How I AI》播客中，ChatPRD 创始人 Claire Vo 深入拆解了从手动 Prompt 向 Agent 循环与 Goal-based 自动任务演进的趋势。她结合 Claude Code 和 Codeex 等前沿工具的实操演示，剖析了心跳、定时、生命周期钩子等自动 Prompt 触发形态，现场配置了每日老化 PR 自动托管以及复杂的元技能开发循环，并针对 Token 费用支出与评估标准的精准度提出了重要的避坑建议。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - WorkOS
  - Runway
products_models:
  - Claude Code
  - Codeex
  - ChatPRD
media_books: []
status: evergreen
---
### 什么是 Prompt 循环

**克莱尔 (Claire)**: 提示词（Prompts）已经过时，循环（Loops）才是未来！如果你的 Agent 还不能通过自动化自己生成 Prompt，那你到底在折腾些什么？在今天的节目中，我将用通俗易懂的“人话”教你什么是 Prompt 循环、如何编写它、它在什么时候有用，以及需要注意的陷阱。我们将在 **Codeex** 和 **Claude Code** 中进行实操演示。在节目结束时，你将成为那些能让 Agent 进行自主 Prompt 的“酷小孩”之一。让我们开始吧！

<details>
<summary>Original English</summary>

**Claire**: Prompts are out and loops are in. If your agent isn't able to prompt itself through an automation, what are you even doing? In today's episode, I'm going to teach you what a prompt is in normal person speak, how to write one, when it's useful, and some pitfalls to watch out for. We will be doing this in Codeex and in Claude Code. And at the end of this episode, you'll be one of the cool kids whose agents prompt itself. Let's get to it.

</details>

**克莱尔 (Claire)**: 本期节目由 **WorkOS** 赞助播出。AI 已经改变了我们的工作方式。各种工具正在帮助团队编写更好的代码、分析客户数据，甚至自动处理客服工单。但这里有一个问题：这些工具只有在能够深度访问公司系统时才能发挥最佳效果。你的 Co-pilot 需要查看你的整个代码库，你的聊天机器人需要检索内部文档。而对于企业买家来说，这引发了严重的安全性担忧。这就是为什么 these apps 从第一天起就面临着严苛的 IT 审查。为了通过审查，它们需要安全的身份验证、访问控制、审计日志等全套企业级功能。从头开始构建所有这些功能是一项巨大的工程。而这正是 WorkOS 的用武之地。WorkOS 为你提供开箱即用的企业级功能 API，让你的应用能够快速具备企业化能力并加速推向市场。你可以把它看作是企业级功能的 Stripe。OpenAI、Perplexity 和 Cursor 已经在运行 WorkOS 以实现更快的迭代并满足企业客户的需求。赶快加入它们以及其他数百家行业领军者的行列，访问 workos.com，今天就动起手来吧！

<details>
<summary>Original English</summary>

**Claire**: This episode is brought to you by work OS. AI has already changed how we work. Tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features. Building all that from scratch, it's a massive lift. That's where work OS comes in. Work OS gives you drop-in APIs for enterprise features so your app can become enterprise ready and scale up market faster. Think of it like Stripe for enterprise features. OpenAI, Perplexity, and Cursor are already using work OS to move faster and meet enterprise demands. Join them and hundreds of other industry leaders at workos.com. Start building today.

</details>

### 自动 Prompt 的三种形式

**克莱尔 (Claire)**: 好了，那为什么我们现在都在疯狂研究 Prompt 呢？当然，是 **Anthropic** 的 Pete（原视频语音转写为 Pete at Openenclaw）告诉我们，如果还在写 Prompt 的话，我们早就落伍了，我们真正需要做的是设计“循环”（Loops），让我们的 Agent 能够进行自我提示。这一个推特引发了大量关于什么是循环、如何使用循环的内容，但说实话，我觉得它们都没有解释得很清楚。所以，今天我在这里为大家解答关于循环的各种疑问：到底什么是循环？如何搭建一个循环？它真的那么好用吗？我真的应该让我的 Agent 自己提示自己吗？我想答案是肯定的，循环确实有大量的绝佳应用场景，我们今天就来聊聊你该如何使用它们，以及它们能带来什么好处，特别是在软件工程领域。不过，也有一些原因会让你不想使用循环。而且老实说，我自己偶尔也还会写点提示词。所以，如果你还没开始做“循环狂人”，不用担心，你依然处于很好的阶段，依然可以用 AI 搞定很多事情。

<details>
<summary>Original English</summary>

**Claire**: Okay, so why are we all prompt maxing? Of course, it's Pete at Openenclaw who told us we are old news if we are prompting and we really need to be designing loops where our agents can prompt themselves. Now, this one tweet spun off tons of content about what is a loop, how to use a loop, and to be honest, I don't think any of them explained it very well. So, I am here to answer your safe space questions about what is a loop, how do I get one set up, is it really that useful, and should I really be letting my agents prompt itself? I think the answer is yes and yes, there are tons of great use cases for loops and we're going to talk about how you can use those and how they can be beneficial, especially with software engineering. But there are some reasons why you wouldn't want to use loops. And honestly, I still do a little prompting. So don't worry if you are not loop maxing, you are in good company and you can still get a lot done with AI.

</details>

**克莱尔 (Claire)**: 为了解释什么是循环，我想给大家说得更简单明白一点。这可以追溯到我之前写的一篇关于 Claude 的文章，文章的主题是为什么 Claude 让人感觉有生命力，尽管它实际上并没有。那篇文章的核心在于解释：提示 AI 代理（Agent）的方法有很多种。我们通常只想到一种提示 Agent 的方式，但实际上，像 Claude Code、Codeex、ChatGPT 等等（在这里填入你最喜欢的 Agent 名字）有非常多元的被提示方式。我想带大家梳理一下这些方式。第一种是消息（Messages）。这是一种由人类触发的输入。这可能是我们大多数人提示 Agent 的方式：进入聊天机器人界面，输入某种提示词，等待回复，然后再输入下一条回复。这是一种基于消息轮次的提示策略。我仍然觉得这种提示方式很有用，我自己也随时在用，但这并不是我们今天所说的“循环”。

<details>
<summary>Original English</summary>

**Claire**: So to answer what a loop is, I'm just going to make this super simple for you all. And this goes back to one of the earliest articles I wrote on OpenClaw, which was this article about why OpenClaw feels alive even though it's not. And the core of this article was explaining that there are many ways you can prompt an AI agent. And often we only think about one way to prompt an agent, but actually there are many ways an agent like Claude Code, like Codeex, like Chat GBT, like name your favorite agent here can be prompted. And I want to go over what those ways are. First, there are messages. This is a human triggered input. This is probably how most of us are prompting our agents. We are going to a chatbot and we are typing in some sort of prompt, waiting for a response, and then typing another response. That is a message turnbased prompting strategy. I still think there's use for this kind of prompting. I use it all the time. But that is not what we're talking about when we're talking about loops.

</details>

**克莱尔 (Claire)**: 相反，当我们谈论“循环”时，我们说的是对 Agent 的**自动化 Prompt**。这可以通过几种不同的形态来实现。我这里顺便提醒一下大家这些形态是什么。我用 Claude 来做演示，是因为我认为它很好地展示了这些类型的提示循环，但它绝不是唯一能做到这一点的系统。

第一种形态是**心跳（Heartbeat）**。你可以设定一个时间间隔，比如每 30 分钟、每小时或每 5 分钟。在到达这个时间点时，它就会启动一个任务。比如，你会设定“每 5 分钟检查我是否有新的 Jira 工单，如果有，就启动一个开发 Agent 来分拣并修复它”。这就是心跳机制，每隔 5 分钟就执行一次。

第二种是**定时任务（Cron）**。Cron 是指在特定的时间或按照特定的日程做某事。比如可以是每天早上 9 点，可以是某个具体的时间，也可以是每周日晚上。这些 Cron 任务比心跳机制更具日程计划性——心跳是每隔固定时间重复，而 Cron 则是按照预设的具体时刻表运行。

最后一种我曾提到的是**钩子（Hooks）**。你可以根据内部生命周期来触发 Agent，比如某个工具被调用、会话启动、会话重置，或者通过外部钩子（如外部会话传来的 Webhook）。例如，“每当我收到一封邮件，我就希望触发一个 Webhook 并启动某种 Agent”。我提到这些是因为在 AI 出现之前，这些就是非常常见的自动化手段。早在 AI 诞生之前，我们就已经在用心跳、Cron 和 Hook 来做自动化了。而现在，你可以用这些技术来自动提示你的 AI。因此，我认为“循环”的核心概念，其实就是提醒大家：你不一定非要用自己人类的手指在键盘上输入 Prompt，才能让 Agent 代表你干活。

<details>
<summary>Original English</summary>

**Claire**: Instead, when we're talking about loops, we're talking about automated prompting of an agent. And there are a couple form factors that can take. And I just want to remind you what what those are. And I'm using OpenClaw because I think it demonstrates these types of prompt loops, but is not the only system that does them. So, the first one is a heartbeat. You can set a schedule like every 30 minutes, every hour, every 5 minutes. And on that schedule, it's going to kick off a task. And so you're going to say every 5 minutes check if I have a new Jira ticket and if so start a coding agent to triage and fix that Jira agent. That's sort of like on a heartbeat. Every 5 minutes I want it to do that. Then there is a cron. A cron is at this time or on this schedule do this. Um so it can be at 9:00 a.m. It can be at um a specific time. It can be every Sunday night. These crrons are a little bit more scheduled. a heartbeat is kind of on a regular basis. CRNs are more on a set defined schedule. And then the last thing that I've talked about are hooks. So you can prompt an agent based on an internal life cycle like a tool was called, a session was started, a session was reset, or an external hook like a web hook from an external session. Every time I receive an email, I want to get a web hook and kick off some sort of agent. And I only remind you of these things because these are common ways to do automations outside of AI. So we were doing automations on heartbeats, on crrons, on hooks way before AI even happened. But now you can do that in order to prompt your AI. And so I think this whole concept of a loop is really just reminding people you do not have to use your human fingers to type in a prompt in order for your agent to do work on your behalf.

</details>

### Goal：更智能的 Goal-based 循环

**克莱尔 (Claire)**: 现在，与我写那篇文章时相比，最大的不同在于，一种全新的循环类型已经作为一等公民内置到了 Claude Code 和 Codeex 中，那就是**目标（Goal）**。目标是一种设定最终成果的循环类型，它让 Agent 围绕该成果不断运行，直到成果能够被衡量和验证，或者 Agent 陷入阻塞。所以我认为，在 AI 编程领域中，这种循环形式正变得非常普遍，当然它还有很多其他的应用场景。简单来说，循环就是一种定时的或半自主的自动化机制，它允许 Agent 自我指导下一步该做什么，自我提示，并最终把工作搞定。

<details>
<summary>Original English</summary>

**Claire**: Now what's different between when I wrote this article and now is a new type of loop has been shipped as a first class citizen of both claude code and codeex which is a goal. A goal is a type of loop that sets an outcome and runs an agent against that outcome until the outcome can be measured and validated or the agent is blocked. And so I would say there's one more loop type that's becoming pretty common in AI coding in particular, although I think there's lots of use cases for it. But again, pretty simply, a loop is a scheduled or kind of semi-autonomous automation that allows an agent to instruct itself what to do, prompt itself, and get that work done.

</details>

### 循环工程的五个要素

**克莱尔 (Claire)**: 那么，要想写出高效的循环，你需要准备些什么呢？我很喜欢 Addie Osmani 写的那篇关于**循环工程（Loop Engineering）**的文章。我觉得写得很棒，拆解得十分透彻。你可以看到这篇文章很新，就是这个月才发表的。我最喜欢的部分就是它阐述了编写好循环所需具备的要素。要写一个高效的循环，你需要这五个要素。我很喜欢它在这一块的写法，它告诉你这个东西到底是什么、它的职责又是什么。例如对要执行的任务进行分拣，或者按照既定日程设置 Prompt。接着，它展示了 Codeex 和 Claude Code 是如何实现这一点的。对于 Codeex 来说，你的自动化功能可以直接从“自动化（Automations）”选项卡中配置，你可以在那里定义你的自动化规则 and 日程。而在 Claude Code 中，你可以配置定时任务（Scheduled Tasks）。两款工具都支持 `/goal` 命令，也都拥有不同的钩子和集成方式。Claude Code 对于工程师来说还有一个优势，那就是它能很好地配合 **GitHub Actions** 运行。但在可执行的自动化类型方面，这两者基本上是不相上下的。

<details>
<summary>Original English</summary>

**Claire**: Now, what do you need to write an effective loop? I like this article by Addie Osmani about loop engineering. I think it's really good. It does break this down pretty well. You can see it's fairly recent. It's from this month. But my favorite part about this article is what you need to write a good loop. To write an effective loop, you need these five things. I like how this is written out in this block in that it tells you what the thing is. It's an automation kind of what its job is. So it's like triage of a task to be done or a prompt to be set on a schedule. And then it shows you how codecs and cloud code do this. And so for codecs, your automations can can come out of the automations tab. And you can actually define your automation and the schedule there. And then in claude code you have scheduled tasks. Both of them have slashgoal and then they all have different hooks and integrations. Cloud code has the benefit of GitHub actions which I think is nice for engineers. Um but both of them are basically at par in terms of the types of automations that you can run.

</details>

### 循环生效的基础设施

**克莱尔 (Claire)**: 接下来是另外几个我认为在运行循环时非常管用的基础设施。在我们深入探讨它们具体是什么之前，先说说为什么这些东西有用？因为它们能让你的工作保持整洁。如果你打算在各个地方随便“YOLO”运行各种循环，你必然会希望在执行时保持一致性。你会需要干净的工作空间，需要解决并避免代码冲突。因此，所有这些工具都是为了让你的循环能真正发挥效力。那么，这些东西具体包括什么呢？

首先是**工作树（Work Trees）**。我觉得这期节目简直快变成 Git 101 基础课了，但工作树确实是一种能将工作有效隔离的方式，尤其是将某个 Agent 的编码工作与其他 Agent 的工作隔离开来，相当于放在沙盒（Sandbox）里。其次是**技能（Skills）**，这是执行常见任务的重复性方法——我们在去年它们刚推出时曾做过一整期节目来专门介绍技能。再次是**插件与连接器（Plugins and Connectors）**，它们是你的 Agent 能够访问的工具，比如 GitHub 连接器、Google Docs 和 Google日历连接器，再加上指导如何使用这些工具的插件说明。然后是**子代理（Sub-agents）**，Codeex 和 Claude Code 都允许你启动子代理。这是一种将任务从主线程分发出去的方式，以便子代理能执行特定任务，尤其是验证工作。最后是某种**状态跟踪方式**，基本上你可以把它看作是一个待办事项清单（To-do list）。你可以把它存为 Markdown 格式的 To-do 列表，也可以使用 Linear 这样的任务跟踪工具。Claude Code 和 Codeex 都支持这些。

所以，如果你把所有这些组合在一起，你实际上就拥有了一套能够启动自动 Prompt，并让该 Prompt 持续运行直到任务完成的机制。让它持续运行的方法是：要么让它按既定日程运行，要么给它设定一个目标（Goal），让它在达成该目标之前无法退出循环。然后，你通过提供必要的隔离环境（避免它们互相打架）以及它们干活所需的工具（包括子代理小军队），来给这个自主启动的 Agent 赋能。就是这么简单。

<details>
<summary>Original English</summary>

**Claire**: And then a couple other foundational things that I think are helpful when you're running loops. And why are these things helpful before we get into what they are? They just keep the work clean. If you are going to be yoloing loops all over the place, you're going to want some consistency in execution. You're going to want clean workspaces. You're going to want conflicts resolved and avoided. And so all these things are really to make those loops effective. And so what what are those things? They are work trees. I feel like this entire podcast could be git 101, but work trees are just basically a way to isolate the work, especially the coding work of an agent away from other agents work in a sandbox. There are skills, repeated ways to do common tasks. We have a full episode on what skills are from earlier um last year when they came out. Plugins and connectors. These are just the tools that your agent has access to. And so those can be like GitHub connectors, connectors to Google Docs and Google Calendar and plus plugins which are some instructions on how to use those tools. Sub agents, both codecs and cloud code allow you to kick off sub aents. This is just a way to federate out work from the main thread so that sub aents can do specific tasks especially validation. And then there's some way to track state. And um essentially just think of this as like a to-do list. So you can save it in a markdown to-do list. You could use linear as a task tracker. Both Cloud Code and Codeex use this. And so if you put all this together, basically what you have is a way to kick off an automatic prompt, a way to keep that prompt going until the job is done. And the way you keep it going is you can keep it scheduled or you can give it a goal and it can't exit the loop until it's hit that goal. And then you empower this agent that has been kicked off autonomously with the isolation it needs not to get in each other's way and the tools it needs to get the job done, including its little army of sub agents. That's it.

</details>

### 实战演示：非技术循环与日常简报

**克莱尔 (Claire)**: 正如我之前向大家承诺的那样，我再用最简单的话概括一下什么是循环：循环就是一种按照日程表或某种循环机制，自主启动一个带有一个或一组提示词的 Agent 并持续运行直到完成的方法。所谓“完成”，可以是因为时间到了，也可以是因为工作做完了。现在，人们会问：“那我应该用循环来做些什么呢？”当你在设计循环或设计 Agent 时，我会说：“现在是展示你管理才能的时候了。”你是在为它们设计一份工作。想象一下你在入职培训一名新员工，这名员工可以是一名行政助理（EA）、客服代表或者软件工程师。在培训他们时，你会说：“听着，EA，每周五我都希望你帮我梳理一下我的日历，看看谁取消了我的预约，我在哪里本可以更高效地利用时间，是否有任何需要跟进的事项，然后发一条 Slack 消息提醒我完成这些事。”并且你希望他们每周五都这么做。恭喜你！你刚刚为你的行政助理设计了一个“循环”。如果你对一名软件工程师说：“听着，每小时我都希望你检查一下是否有需要处理的 GitHub Issue。如果有，就去分拣它、写点代码、提交代码审查。”恭喜！你刚刚写出了一个循环。如果你对另一名软件工程师说：“每次你收到需要审查的 PR 时，我希望你不断迭代修改，直到它符合我们既定的代码规范，所有的 Lint 和校验都通过，且准备好部署为止。你只需一直盯着它，直到 GitHub PR 中的所有检查项都变绿。”你猜怎么着？这就是一个目标循环（Goal loop）。因此，我非常喜欢把循环看作是在为人们设计工作流和待办工作，只是恰好你可以把一个智能 Agent 放在这个循环里，让它自动运行。这就是循环。

我知道人们很容易被那些复杂的动态工作流图表，或者社交媒体上那些吹嘘自己“在各个角落运行着成千上万个循环，从来不需要自己手写任何 Prompt”的博文给吓到。我想让大家觉得这门槛没那么高。如果你觉得每天或每小时都有某项固定的工作可以被自动执行，那么这就是使用循环的最佳时机。别再锁定闹钟爬起来，然后在 Codeex 或 Claude Code 里手动敲入提示词来启动任务了，直接让系统自己去启动它。而且有一点非常神奇的是，你可以创建循环，让你的 Agent 去触发其他的循环。你可以想象成一个人带着一个 Agent 团队，而每个 Agent 旗下又带着它们自己的 Agent 团队。你可以开始在这些循环的设计上发挥无限的创意。

不过，让我们直接动手建一个吧。我准备在 Claude Code 和 Codeex 中各建一个循环，一个是偏非技术的，另一个是偏技术的。最后我们再聊聊使用循环的一些注意事项。好的，我想先从一个非技术性的例子开始。我特意打开了 **Claude Co-work** 而不是 Claude Code，就是为了帮非技术背景的朋友们把这个概念彻底讲透。让我觉得好笑的是，Claude Co-work 的界面正中央就摆着一个循环，那就是我的“每日简报（Morning Briefing）”。所以，如果你在 Claude Co-work 中使用过定时任务，猜猜怎么着，宝贝？你其实早就写过循环了！这是一个定期启动的循环，它会自我提示需要执行哪些步骤，把工作做完，然后当我拿到每日简报时，这个循环的任务就结束了。因此，定时任务就是一种循环。虽然它不是“目标型”循环，但它本身确实是一个循环。所以，如果你想循序渐进地尝试循环，我会说 Co-work 的定时任务，或者在 Claude Code 中我们所说的“常规任务（Routines）”，是完美的入门选择。每日简报就是大家开始学习“循环 101”的绝佳案例。

<details>
<summary>Original English</summary>

**Claire**: So again, I promised you I'd explain it to you very basically what a loop is. A loop is a way to autonomously kick off an agent with a prompt or set of prompts on a schedule or on kind of a recurring basis until it's done. It could be done because the time's up, or it could be done because the job's done. Now, people are going to ask, "What should I use a loop for?" And when you're designing loops or designing agents, I say, "This is the time for the manager." You are designing a job. And so, just imagine that you're onboarding an employee. That employee could be an executive assistant. That employee could be a customer service agent. That employee could be a software engineer. you're onboarding this person and you're going to say, "You know what? Every Friday, EA, I would like you to review my calendar, see who canceled on me, where I could have used my time more effectively, if there are any follow-ups, and send me a Slack to get this done." Um, and I want you to do that every Friday. Guess what? You've just designed a loop for your executive assistant. If you have a software engineer and you say, "You know what? Every hour I want you to check if there's a GitHub issue that needs to be addressed. And if there is, triage it, write some code, put it up for code review. Congratulations. You just wrote a loop. And if you have another software engineer and you say, "Every time you get a PR to review, I want to make sure that you iterate over it until it meets our defined code standards, all the lints and checks are clean, and it's ready to deploy. and you just work on it until all the checks in the GitHub PR are clean. Guess what? That is a goal loop. So, I really like to think about loops as designing workflows and designing jobs to be done for people. It just happens to be that you can put this intelligent agent against the loop and then it's ready to go. So, that that's it. That that's a loop. And you know, I think people get intimidated by these complex like dynamic workflow diagrams and these hype boy posts about how they're running thousands of loops all over the place and they never prompt anything themselves. And again, I just want to make this really accessible for folks. If there is something where you feel like every day or every hour a set job can be done, that's a good time for a loop. And don't set your alarm and wake up and type into codeex or clawed code the prompt that would kick it off. Instead, set it up to do that itself. And the one magical thing I would let people know is you can create loops to have your agent prompt other loops. So again, you can think about a human with a team of agents who all have their own team of agents. And you can start to get really creative about what these loops are. But let's go ahead and build one. So I'm going to build one in cloud code and one in codeex. And I'm going to do one sort of non-technical one and one technical one. And then we will end with some warnings about using loops. Okay. I wanted to start with a non-technical example and I pulled up claude co-work instead of claude code just to really break this down for the people who are not technical. And what makes me laugh is there is a loop front and center here in Claude Co-work which is my morning briefing. And so if you have used a scheduled task in Cloud Co-work, guess what babe? You have written a loop. It's a loop that kicks off on a regular basis. It prompts itself on what it needs to do. It gets the job done and when I have my morning briefing, I am finished. And so scheduled tasks are a loop. Now it's not a goal style loop, but it is a loop itself. So if you are wanting to tiptoe your way into loops, I would say co-work scheduled tasks or in claude code, what we call routines are perfect ways to get started. So the morning briefing is a perfect loop 101 for you all to start.

</details>

### 实战演示：自动托管 Aging PRs

**克莱尔 (Claire)**: 不过，让我们实际把它变得更聪明一点。我准备在 Claude Code 中创建一个稍微偏技术性一点的循环，这也是给正在收看的开发和产品团队准备的。这并不是超级硬核的技术任务，但我认为它极其有用。我们要创建一个 Routine 任务。它可以运行在本地，也就是说它要在我的电脑上运行（这意味着我必须开着笔记本屏幕，不过没关系，我本来也一直开着），或者也可以运行在云端。这里我先让它在本地运行，命名为“每日老化 PR 审查（daily aging PR review）”。大家从名字就能猜到，这是一个能自动帮我们寻找那些开启超过 12 小时的 PR（Pull Request）的循环。它会一直“照看（babysit）”它们，直到它们可以被合并，或者在 PR 持续老化时警告团队。

在演示之前，先插播一条广告。本期节目由 **Runway** 赞助播出。Runway 是一个全新概念的创意平台，它能让你在同一个地方生成你想要的任何图片、视频或内容。有了 Runway，现在只需几分钟就能将初始创意转化为最终交付成果。无论是将低保真产品草图变成可直接用于营销宣传的高清图，还是制作宏大的品牌大片，Runway 都能帮助你的团队扩展创意构想，同时牢牢锁住预算和时间。Runway 汇聚了世界上最顶尖的 AI 模型，这就是为什么微软、Robinhood、亚马逊、Adobe 等大企业，以及狮门影业和传奇影业等大制片厂每天都在用 Runway 产出真实的工作成果。现在就可以去 runwayml.com/howiai 亲自体验，使用优惠码：how I AI。

好了，我们回到正题。我现在面临的问题是，因为我们到处在跑 Agent 和各种循环，所以我们提交了大量的 PR。但我慢慢对“人肉盯着这些 PR”感到厌倦了，大家也经常忘记及时去合并它们。导致现在我们可能有大概 40 多个 PR 堆在那里需要处理。我最担心的是那些大家做完后就转去忙别的事、任由其被搁置老化的 PR。所以我打算给 Agent 一些指示，对它说：“去看看 **ChatPRD** 应用程序上所有开启的 PR。如果发现任何开启超过 12 小时的 PR，请检查它们是否已做好合并准备。如果存在可以自动照看的 PR，请启动一个子线程去盯着它，直到所有的合并检查项（Merge checks）全部变绿。否则，在 product 频道中发一条 Slack 消息提醒团队有哪些待批准和合并的开放 PR。另外，发 Slack 消息时的语气要刻薄一点（Be mean）。”

好的，我把这些指令输了进去，并设置每天上午 10:15 运行。至于工作分支，设置在我的 `chatprd` 分支或 Base 分支都可以。接下来，我创建了这个自动化任务。现在，我们有了一个循环！关于这个循环，我想指出几点：它每天 10:15 定时触发。所以，它是按日程运行的，我不需要手动去问今天有什么 PR 需要审查，它自己就会在下一次运行时间点自动起来干活。还有一点大家应该能注意到，就是我之前说的“Agent 也可以拥有自己的 Agent”。我在指示里说，如果有任何 PR 需要盯着，就“启动一个子线程去照看该 PR”。这意味着并不是所有的工作都必须在主线程（Master thread）里运行。它完全可以启动子代理（Sub agents）或其他的独立线程来监视这些工作。

我不想在这里干等 4 分钟，所以现在手动点击立刻运行。一旦启动，它会带着我之前写在 Routine 里的初始 Prompt 跑起来，然后它就会非常独立自主地开始工作。我其实给它设定了两个目标：一是找出所有超过 12 小时的 PR，然后自己去监控并确保它们的合并检查都变绿；第二是使用我们的 Slack 连接器发送一条通知。我不会让大家在这里干看着，但你可以看到它完全在自己运行，不需要我花精力去盯着它。到今天结束时，我能得到的就是一堆已经准备好合并的 PR 列表，以及几条嘲讽我们忽视好 PR、没有把优秀的产品及时送到客户手中的刻薄 Slack 提醒。我想再次帮大家破除对循环的神秘感。它其实就是一种按照预设日程运行的东西。这是一个非常简单的基于时间的循环，它被配置了 GitHub 和 Slack 的访问权限。我觉得把这个 Agent 当成一位虚拟雇员是非常合适的，它的职责明确，注定会成功。

好吧，这里系统提示“未检测到 Slack MCP”。我需要确认 Slack 连接器是否已经开启。好了，打开了，现在应该一切正常了。

<details>
<summary>Original English</summary>

**Claire**: But let's actually make this a little bit more intelligent. I'm going to go into claude code and I am going to create a loop that's a little bit more technical but for the product folks that are watching. Okay. To start in claude code I'm going to write a loop or a routine that's a little helpful for the product managers engineering teams out there. It's not a super technical one but it's one I think is really useful. And so what I'm going to do is I'm going to create a routine. Um, it can run locally, which means it's going to run on my computer, which means I got to keep the uh laptop screen open, but don't worry, I do that anyways. Or it can work on the cloud. I'm just going to have it run locally. And I'm going to call it daily aging PR review. And so, if you can guess from the description, this is going to be a loop or a routine that looks for open PRs that have been open more than 12 hours. and um babysits them till they are ready for merge or alerts the team about aging.
This episode is brought to you by Runway, a new kind of creative platform that has everything you need to generate any image, video, or piece of content you want all in one place. With Runway, it's now possible to go from initial idea to a finished deliverable in a matter of minutes. From turning lowfidelity product shots into campaign ready imagery all the way through putting together big brand films, Runway can help your team scale your creative ambitions while keeping your budgets and timelines from doing the same. Runray brings together the world's most advanced AI models, which is why enterprises like Microsoft, Robin Hood, Amazon, and Adobe along with studios like Lionsgate, and Legendary all use Runway to ship real work every day. Try it yourself at runwayml.com/howiai. Promo code how I AI.
Okay, so the problem I'm having is that we ship a lot of PRs because we do agents everywhere and loops everywhere and then I kind of get bored of babysitting them and we forget to merge them in a timely basis. And so we probably have like I don't know 40 PRs that we need to go through. And the ones that I'm most worried about are the ones that like we kind of moved on from and are letting age. And so I'm going to give it some instructions and I am going to say look at the PRs open on the chat PRD app app. If there are any PRs open more than 12 hours, please review their merge readiness. If there is anything that you can babysit, spin up a thread to babysit that PR until all merge checks are green. Otherwise, send a slack in the product channel to the team about the open PRs that are ready for approval and merge. Be mean when you send the slack.
Okay. So, I am putting in that those instructions and I'm going to say I want this to run, let's see, daily at 9:00 a.m. That's fine. Actually, let's have it daily at 10:15 a.m. because it's about to be 10:15. Okay. And then I am going to have it work in my chatard branch on base is fine. And I'm going to create that automation. Now, there's a loop. And a couple things I want to call out about this loop. It happens every day at 10:15. So, it happens on a schedule. I don't have to come in and say what PRs do I need to review and it's going to tell me the next time it's going to run. And then one thing that I want to call out is you remember I said your agent can have agents. I called out here that if there are any PRs that need to be babysat, you can spin up a thread thread to babysit that PR until all merge checks are green. So not all the work has to happen in the one master thread. It can actually kick off sub agents or other threads to watch the work. And so I'm going to go ahead and not wait the 4 minutes and run this now. Okay. So once this is kicked off, yes, it's going to prompt with that original prompt that I put in the routine or automation. But then it's going to be pretty autonomous and work itself. And you know, I've given it basically two outcomes it needs to go after. It needs to identify anything over 12 hours that it can watch and actually monitor and make sure all the merge checks are green itself. That's success criteria one and then success criteria two is it would use our Slack connector to send us a message. Again, I'm not going to make you watch this, but you can see here it's going to work all by itself. I am not going to have to monitor it, and all I'm going to get at the end of the day is a good set of PRs that are ready to merge and some mean messages about how we're ignoring good PRs and not putting awesome product in the hands of our customers. So again, I wanted to demystify what a loop is. It is just something that happens on a schedule. Now, this is a very simple loop and it has access to a bunch of connectors. It has access to GitHub. It's going to have access to Slack that's already set up. So, I feel like this agent or this like pseudo employee with a job is well set up to be successful. But this is a perfect use case for a loop and a very very simple timebased one. Okay. Okay. And it says no Slack MCP surfaced. Um I'm going to make sure that Slack is turned on. There we go. Now it should be fine. Okay.

</details>

### 实战演示：让 Agent 自动生成验证循环

**克莱尔 (Claire)**: 现在我们来聊聊更高级的循环。刚才我在 Claude Code 中写的是一个定时执行的 Routine，比较简单。但我现在想把 Codeex 也拉进来，给大家展示另一个我认为非常有趣的循环。这个循环会稍微复杂一些，技术难度也稍微高一点。不过在开始编写之前，我想先提几个我非常喜欢的 Codeex 的设计细节，这些细节对于大家思考或学习如何编写循环很有帮助。在 Claude Code 中，这种任务被称为“Routines”；而在 Codeex 中，它们被称为“自动任务（Automations）”。Codeex 做得非常棒的一点是，他们提供了一系列模板（Templates）。它们实际上为你提供了好几个可以直接运行的、现成的循环/自动化模板。所以如果你在寻找灵感，我强烈建议去看看这些自动化模板。今天我也打算直接使用其中一个。它的名字大概是“根据最近的 PR 和审查建议下一步该深入学习哪些技能”。这可以说是一个非常有“元属性（meta）”的工具：去审查我们所有已经交付的代码，看所有的代码提交（commits）和审查评语（comments），然后为我们整个开发团队（包括人类工程师 and Agent 助手）推荐可以进一步深造学习的技能，从而深化我们的研发成果。

我选中了这个模板，将其设为每周五上午 10 点运行。我认为每周运行一次是比较合理的节奏，因为你需要给循环准备足够的数据，它才能做出一份扎实的、长期的分析结果。但我还想给它添加一点额外的信息。

这个模板自带的 Prompt 是：“根据最近的 PR 和审查提出需要深入研究的下一步技能，并设定基本原则。让每一项建议都锚定在具体的代码证据上，避免泛泛而谈的废话。确保每项建议都具备可操作性且具体。”但我实际上想让它更具针对性：“如果我们开发了任何可供 Agent 或开发者用来自动验证其工作成效的工具，请确保为这些工具创建相应的‘技能’。具体来说，凡是能让 Agent 或软件工程师在特定的用例下运行测试套件（test suite）或冒烟测试（smoke test）的命令行工具或 MCP，都非常值得我们围绕它们去构建‘技能’。”我还会往里多塞一条要求，用以展示子代理和自动化结合的巨大威力：“如果你识别出了一项新技能，请为它单独开启一个线程（thread），并在仓库的 Base 分支上运行该技能进行验证。我们要确信这个技能是真正管用且产出高质量内容的。”

大家发现了吗？这实际上是一个“带有子代理的循环”，并且这个循环还极有可能去生成它自己内部的循环。我甚至想强制它去生成它自己的内部循环，要求它：“在验证技能时必须使用‘目标’。”所以当它在提示子代理时，必须给子代理设定一个非常具体的、用于验证成效的目标。你懂的，一般来说你写一个循环、一个目标或者一个 Agent，只要大喊“验证循环目标！验证循环目标！”就能搞定了。但我们这里这个基础 Prompt 的意思是：“好吧，每周五我需要你去审查我合并的所有代码，识别遗漏的技能。其中有一些我们自己开发的内部工具相关的技能，我认为非常重要。一旦你发现有新技能，我希望你开启一个子线程（启动一个新聊天），通过目标型循环去验证那个技能。”因此，我们不仅在日程层面上设置了一个循环，还在该循环内部指派了子代理去处理具体任务，并且子代理由目标型循环（另一种循环形式）来指导以验证其工作。这是一个非常“元”的自动任务，但我认为它完美地展示了基于循环进行 Prompt 的强大之处。它表明循环不单单能按日程走，还可以配置成按日程去组建一个定时干活的团队，或者组建一个在循环中不断推进工作直到彻底完成的团队。好的，我现在就去创建这个自动化，并手动点击立即运行。接着，我们就能看到这个 Agent 跑起来，自动化正式开始。

<details>
<summary>Original English</summary>

**Claire**: Now let's talk about a more advanced loop. So I wrote that one in Claude Code. It is a scheduled routine. It is pretty simple. But I'm going to also pull up Codeex and show you another loop that I think is really interesting that's a little bit more complicated and a little bit more technical. Before I go into writing a more complicated loop, I wanted to call out some of the things that I like in Codeex when you're thinking about or learning how to write loops. So, in Cloud Code, they're called routines. In Codeex, they're called automations. And what I like about what Codeex has done is they have these templates. And so, they actually have given you a couple good ideas of quote unquote loops, automations, routines that you can run. So, if you're looking for inspiration, I would really look at these automation templates. And I'm actually going to use one. I think it's this from recent PRs and reviews suggest next skills to deepen. And so this is sort of a meta tool um that I'm going to use, which is look at all the code we shipped, look at all the code commits and comments, and then come up with skills that our coding team, including agents, could use to deepen the work. And so I'm going to select that one. It's going to happen Fridays at 10:00 a.m. Um, it's going to happen weekly. I think weekly is right. Again, you want enough data in these loops for it to do a good long job, but I'm going to give it a little bit more information.
So, the prompt is out of the box from recent PRs and reviews. Suggest next skills to deepen grounding rules. Anchor each suggestion to concrete evidence. Avoid generic advice. Make each recommendation actionable and specific. I'm actually going to be more specific. If we have developed any tools for agents or developers to automatically validate their work, ensure that we have a skill for those tools. Specifically, command line tools or MCPs where an agent or a software engineer can run a test suite or smoke test against a specific use case are very important to build skills around. I'm going to add one more thing to the skill just to show the power of sub aents and automations. If you identify a skill, spin up its own thread and use that skill valid validated against the base branch of the repo. We want to confirm that the skill actually works and outputs high quality.
Okay, so this is like a sk a loop with sub aents that is probably going to generate its own loop. I'm actually gonna force it to generate its own loop by saying you should use a goal when validating the skill. So when you prompt the sub agent, make sure you prompt it with a very specific goal it can use to validate against. You know, basically when you write a loop or a goal or an agent, you just say validate loop goal validate loop goal and you're good to go. But this basic prompt is saying, okay, every Friday I want you to look at all the code I merged. I want you to identify skills that are missing. There are specific types of skills that I think are very important, which is skills to use some of the internal tools we've developed. If you see a new skill, I want you to spin up a sub thread, another chat, I want you to validate that skill with a goal loop. So, not only are we setting a loop at the schedule basis, we are setting up sub aents to work on specific things. And then we're using a goal in those sub aents, which is a different type of loop to validate the work. So, this is like a very meta task, but I think one that illustrates the power of loop-based prompting. It doesn't just have to be on a schedule. It can be on a schedule, set up a team that does work on a schedule, or on a schedule, set up a team that does work on a loop until it's done. And so, I'm going to go ahead and create that. And then again, I'm going to just run this now. Um, and we're going to see here that this agent is going to spin up. the automation is going to start.

</details>

**克莱尔 (Claire)**: Codeex 做的很有意思的一点在于，它会配置自己的专属记忆系统。所以你在这里能看到一些关于自动任务运行的骨架（scaffolding）逻辑，接着它开始输入提示词。接下来它会去搜索代码库、运行相关的命令、查询 GitHub，并且很有希望据此产出那些新的技能文档。理想情况下，我们应该能看到左侧的所有聊天列表中开启了新的线程，用于测试它认为需要运行的那些技能。看，它已经找到了一个很不错的自动化候选项目。我们看看它是否真的会启动线程去验证它。好的，它确实启动了！它识别出了一个“`chat smoke CLI`”技能。基本上，这是我之前为了测试聊天机器人而编写的一个命令行工具，这样就不用每次都去点 ChatPRD 的网页 UI 了。接着，它启动了一个专属的子代理去测试这个技能，并且设定了一个目标：在 Base 分支上测试并告知我们其操作指南在实际环境中是否真的站得住脚。看，它把这个 Agent 跑起来了，Agent 拥有一个简短的代号，并且有明确的目标。你可以看到它正在朝这个目标努力：“在 Base 分支上验证本地仓库的 `chatm smoke CLI` 技能”。它会一直循环，直到验证任务结束。因此，我们将能看到越来越多的子代理被唤醒。你可以点击这里的下拉菜单查看它们。我能看到 `Gaus` 正在测试我的 `smoke CLI` 技能；而 `Galileo` 正在处理另一项技能——`GitHub 评论地址处理技能`，也就是一个类似于“PR 自动托管 babysitter”的技能。

所以，我设置 the 定在周五触发的自动任务是这样的：它去检索我们的仓库，生成技能文档，然后再次启动带有“目标”的子代理来验证这些技能是否确实可行。它会这样一遍又一遍地做下去，直到把上周积攒的、值得做的技能全部处理完毕。这就是我今天在此处设计的“超级大循环”——说实话，在录制这期节目之前我根本没想到要这么做，这纯粹是现场灵光一现的产物。但它在日常工作中确实能帮我省去大量的琐碎时间。好，我就让它在后台默默运行吧。

<details>
<summary>Original English</summary>

**Claire**: One of the things that Codex does that's kind of interesting is it sets up its own memory. So you can see here a little bit of the scaffolding of what an automation looks like and then it just gives its own prompt. Now again, it's going to go ahead and search the code, run its own commands, it's going to look at GitHub, and it's hopefully going to create those new skills. Um, and then what I ideally we're going to see in the left hand side in these all chats is new threads being kicked off to test the skills that it's identified it needs to run. And so it found one strong automation candidate. Let's see if it actually kicks off a thread to validate it. Okay, so it did. It identified a chat smoke CLI skill. Basically, this is a command line tool I built to um sort of test chats without having to use the UI in chat prd. And it basically spawned a dedicated sub agent to test the skill with a goal um to test it against the base branch and tell us whether its instructions actually hold up in practice. So look, it spun up this agent. You can see agent, it's got a little key name, and it's given it a goal. So you can see here it's pursuing this goal which is validate the local repo chatm smoke CLI skill on the base branch and it's basically going to loop until that validation is done. So what we're going to see is more and more sub aents being kicked off. You can click them here um by clicking this little um drop down. So I see Gaus which is working on my smoke CLI skill. And then let's see Galileo is working on um a different skill. It's working on the GitHub address comment skill. So it's basically like a babysitter of PR skill. And so this automation that I've set up happens on a Friday. It's going to look at our repo. It's going to create skills and then it's going to create sub aents that are on again a goal, which is a type of loop to validate that those skill works. And it's just going to do it over and over again until it has done as many skills as it thinks is appropriate for the last week. And so that is like my mega loop that actually I I did not think to do until live on this episode. And it's going to be really useful for me on a regular basis. So I'm going to let that run.

</details>

### 避坑指南：Tokens 消耗与目标设定

**克莱尔 (Claire)**: 在结束节目之前，我还想提醒大家注意几个关于循环的警告信号。循环听起来很迷人：我们都希望 Agent 随时按照我们的要求定时开工，去帮我们处理那些我们讨厌的繁琐工作。这很好。但它会带来什么问题呢？

首先，**循环的开销可能会变得非常高昂**。我刚刚启动的那个定时自动化任务干的活非常宽泛。它会自己决定什么时候生成子代理，并且采用基于循环的验证模式。这意味着它会疯狂消耗 Token，直到达到了它所认为的成功阈值。如果你没把这个循环写好，或者你设定的验证标准（validation criteria）太薄弱，你猜会发生什么？你的 Agent 会把你的 Token 烧得一干二净！特别是在用 Claude Code 或某些 Agent 框架时，我们经常能观察到这种情况：它们处理循环非常在行，干活极度勤勉，也确实能产出令人惊叹的成果，但是天啊，它们简直是无情的 Token 燃烧机器！因此，我认为循环是帮你花掉预算的绝佳方式（笑）。大家在应用循环时一定要多加斟酌，并且务必密切监控其搭建成本和运行效率。这就是第一点需要注意的。

<details>
<summary>Original English</summary>

**Claire**: But before I get you out of here, I just want to talk about a couple warning signals around loops. This is amazing. We all want our agents to work for us on a schedule whenever we want, doing work that we don't want to do. It's great. What are some of the problems? One, loops can get expensive. So, I just kicked off an automation that happens on a regular basis. It does wide ranging work. It decides when to spin off sub agents and it does loop-based validation, which means it's burning tokens until it hits a threshold that it decides is successful. If you do not write that loop well or your validation criteria is too thin, guess what? Your agent is going to burn tokens. I think we've seen this with OpenClaw in particular or some of these like agent harnesses is they're really good at loops. They're very diligent. They get interesting work done, but man, do they love to burn tokens. And so I think these loops are a great way to spend money. So just be thoughtful about where you apply it and then make sure you're monitoring it for both cost and efficiency of the setup. So I think that's thing number one.

</details>

**克莱尔 (Claire)**: 第二点是，我刚才手写的循环 Prompt 其实非常粗糙，甚至可以说有点烂，我不建议大家照抄。虽然它最后也能跑通，但我认为在设计循环时（尤其是基于目标的 Goal-based 循环），**极其精准地书写提示词（Prompt）**是至关重要的。OpenAI 为 Codex 的目标设定写过一份非常棒的指南，我经常查阅。而且在很多情况下，我其实会直接让 Codeex 自行去撰写它的目标规范。基于循环的 Prompt 设计有它自己独特的门道，特别是基于目标的 Prompt 设计，因为你必须对“评估标准”和“成功标准”定义得非常详尽、滴水不漏。如果你做不到这一点，你将会非常失望，白白烧掉一堆 Token 却得不到什么有实质价值的产出。因此，我再次强调：对待循环提示词，你需要比对待那些有人工实时监控的普通聊天会话要谨慎十倍。

<details>
<summary>Original English</summary>

**Claire**: Thing number two is I wrote actually pretty pretty poor loop prompts. I would not recommend people follow my prompting. It did fine, but I think loops, especially goal-based loops, are ones where writing the prompt really precisely is super super important. OpenAI has a great guide to writing goals for codecs. I use that all the time. And in fact, what I often have Codeex do is write its own goals. Loop-based prompting is just its own thing. goal-based prompting in specific is just its own thing because you have to be very precise about evaluation and success criteria. If you are not, you will be very disappointed and use a lot of tokens for not a lot of output. So again, I would be much more careful with loop-based prompting than I would be prompts or conversations where I am actually monitoring it myself.

</details>

### 总结与展望

**克莱尔 (Claire)**: 抛开这些问题不谈，我认为循环在生活和工作中还是有大量用武之地的。我刚才展示的例子大多偏向产品和工程研发，但你完全可以将目标和循环运用于各种各样的事务中。我们聊到了每日简报（定时循环），在之前的一期节目中，我还用目标循环来自动清理我的 Gmail 收件箱，那也是个非常棒的实用案例。你还可以让 Agent 自动检索最新资讯，一旦发现与你个人或企业利益高度相关的特定话题，就自动启动子代理进行深度研究。所以，你可以尽情发散思维：如何把你的 Agent 小帮手设置成定时开工？如何给这个勤劳的 Agent 布置一份可以根据目标进行结果验证的工作，然后安心放手，直到它把工作搞定？这就是循环。

以上就是今天的内容总结。我非常期待能在评论区读到大家的分享：你们正在用循环来自动化哪些工作？或者你们是否觉得这纯粹是多此一举、白白浪费 Token 的噱头？至少我个人觉得它非常有用，不过我很想听听你们的想法。感谢收看本期的《How I AI》。非常感谢大家的支持。如果你喜欢我们的节目，请在 YouTube 上点击赞和订阅；更欢迎在下方留下你的评论和想法。你也可以在 Apple Podcasts、Spotify 或你最常用的任何播客平台上找到我们。如果觉得有收获，请给我们留个好评，这能帮助更多人发现我们的节目。你可以在 howiaipod.com 上收看往期所有节目并了解详情。我们下期再见！

<details>
<summary>Original English</summary>

**Claire**: Other than that, I think there are lots of places where you can use loops. I gave some examples that are really more about product and engineering, but you can use goals and loops for all sorts of things. We talked about the morning brief. That's a scheduled loop. I used a goal loop in another episode to clean out my Gmail inbox. That's another great example. You can have agents that prompt themselves to do effective research and spawn off sub agents if a specific topic seems interesting to you personally or your business. And so I just think there are tons of ways for you to think about how could I put my little agent worker on a schedule or how could I give my little diligent agent a job that can be done and validated against a goal and then how can I leave it alone until that work's done. That is a loop. That is my summary.
I cannot wait to hear in the comments what you're using looping for or if you think this is just totally overbuilt stuff that's wasting tokens. I found it useful, but I'd love to hear what you think. Thanks for joining How I AI. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>