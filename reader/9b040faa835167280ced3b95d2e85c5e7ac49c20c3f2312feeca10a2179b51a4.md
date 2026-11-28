---
author: AI Engineer
date: '2026-11-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iK9gmxXyBR0
speaker: AI Engineer
tags:
  - artificial-intelligence
  - autonomous-agent
  - self-improvement
  - career-path
title: 递归自我改进编程智能体与工程师职业路径
summary: Cline 创始工程师 Ara 探讨了递归自我改进（RSI）编程智能体的演进，分享了利用自动评估循环迭代优化测试框架及内核代码的实践案例，并建议软件工程师主动贴近 RSI 全链路闭环，选择受益于模型扩展且不易被模型单次发布淘汰的硬核问题。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ara Khan
companies_orgs:
  - Cline
  - OpenAI
products_models:
  - TerminalBench
media_books: []
status: evergreen
---
### 演讲主题与三大目标

大家好，我是 Era，Cline 的创始工程师。今天我将探讨递归自我改进型编程智能体（recursively self-improving coding agents）。这是一次非常引人入胜的交流，因为大家都渴望弄清楚什么是 RSI（递归自我改进）、我们如何实现它、经历的过程如何，以及它将对我们的职业生涯产生何种影响。

首先我列出本次交流的三个简单目标，这有助于大家理解我们能从中收获什么，以及该领域的未来图景。

第一个目标是**理解前沿实验室的真实意图**。前沿实验室之外的人总是在猜测：Anthropic、OpenAI 或 DeepMind 接下来会发布什么？他们究竟在构建什么？未来的走向如何？究竟谁率先攻克了 RSI？本次分享能帮大家梳理出他们技术路线图的大致轮廓。

第二个目标是：**在模型能力飞速迭代的当下，你该如何规划未来数年的职业生涯？** 这正是我们想要探明的问题。当脚下的技术基石快速变迁，曾经你可以在个人主页或 GitHub 上展示侧边项目来证明自己，而现在借助任何前沿编程智能体几乎都能一步到位单次搞定（one-shot）。随之而来的问题是：我们该如何展示工作证明（proof of work）？如何证明自己的实力？又该如何规划未来几年的职业路径？我们正身处一个极其特殊的时代。

第三个，也是最重要的目标：**避免沦为技术变革下的底层群体**。虽然这听起来像一句玩笑，但很多人确实在认真思考这一现实可能性。大家都在想：如果我们想做的所有事情都能被前沿模型轻松搞定，那我们的价值何在？软件产业将走向何方？技术的未来究竟在哪里？在这一切快速演进之际，我们又该何去何从？

市面上存在许多焦虑与恐慌，但大家的担忧确实有其合理性：如果全球的商业利润最终都流向制造前沿 GPU 的少数硬件巨头，以及打造最强模型的几家头部 AI 公司，其余的普通开发者该如何生存？我们能做些什么？

接下来我会列举几个具体案例和思路，希望能切实启发大家重新审视当下的职业路径、生活抉择与所选问题。这能帮助我们重新校准工作方向，选择那些经得起时间考验、并在心智与财务层面带来稳固回报的方向。

<details>
<summary>Original English</summary>
Hey guys, this is Era. I'm a founding engineer at Klein and today I'm going to be talking about recursively self-improving coding agents. So this is a very interesting conversation in the sense that everyone wants to understand what RSI is, how we accomplish it, how we go through it, and how it affects our career. So I'm going to start with giving you just three goals of this entire conversation, just three simple goals. And that would help you understand like what what we get out of it and what the future for this looks like. So the goal number first is that understanding the intent of Frontier Labs, right? Everyone who's outside of the Frontier Labs is always trying to speculate like, hey, what what what is Entropy in Open AI or what is Deep Mind going to come out with or what what are they trying to make? And what's the future going to look like? Who has cracked the RSI? So like this kind of helps you get get a rough outline of what their roadmap looks like. And the second thing is that like if the models are improving so fast, like how do you think about your career or the next few years, right? That is really what we want to understand. We want to understand like, okay, things are changing so fast, like the ground underneath us is shifting so quickly. Right now, like it's like there used to be a time when you could like demonstrate your side projects on your personal website or GitHub. And now it's just like you could literally one-shot them using any frontier coding agent. And with that, it's like it's like, oh, how how do we demonstrate proof of work? How do we demonstrate, you know, that that we know what we're doing and how do we think of our career for the next coming years, right? So it's very interesting times that we're living in. And then the third and the most important goal of the conversation is escaping the permanent underclass, right? So I know this seems like a joke, but this really a very valid possibility that people are contemplating. Everyone's like, oh, well, if everything that we want to be doing can potentially easily done by a frontier model, like what are we what are we good for? And like where does software go? Where where where is the future of technology going to go? And what are we going to do as as things evolve so fast, right? So I think that there's like a lot of like fear mongering, but also there's like some very valid merits where people are concerned that like if all the revenue of the planet is going to go to um a few hardware companies that make frontier GPUs and then a few few uh AI companies that that make the best models, like how are we how are the rest of us going to survive and what what are we going to do here? So I think I'll I'll walk you through a few examples and a few ideas that will like really really help you reconsider the career choices and the and and the life choices you're making and what your problems you're picking up. And then and then that would help you like realign what it is that we should be working on and what it is that you, you know, would would that you could work on that will stand the test of time and help you both just not just like on a psychological but like financial and other levels as well.
</details>

### 测试框架自动化改进的实践案例

为了给出一个确切的范例，让我们从我亲身做过的一项具体工作讲起。几个月前，我在编程测试框架（coding harness）上实现了递归自我改进。这大概是业界首个公开的自动化评测优化案例。

具体来说，我们过去通常用基准测试得分来衡量编程智能体的能力表现。例如在 TerminalBench 2.1 上，Kimi k1.3 搭配 Cline 的得分通常在 60% 到 70% 左右，模型越强得分就越高。我们注意到 Kimi k1.3 刚发布时，我们的测试得分为 77.5%，这本身是不错的成绩。但我们当时在想：这真的代表该模型在此基准下的极限水平吗？模型发布报告中声称的最高得分又是多少？报告中指出其得分可达到 85% 甚至更高。我们意识到自己并没有发挥出这种水平。针对新发布的模型与 Cline，我们平时的做法往往是进行针对性调优，以最大化激发其能力。

当我们开始针对该模型进行爬山算法（hill climbing）优化时，我们意识到需要规范地推进诸多步骤，确保瞄准正确的痛点并以合理的方式执行。接着我们开始思考：既然这里包含大量繁琐的基础工作，我们能否将其实现自动化？这就是我们将其自动化的实际演示。我先在此做个铺垫，后续会详细剖析这一套针对 Cline 测试框架的自动改进循环究竟是如何运作的。其本质意味着：一套编程智能体的驱动框架能够在同一组问题集上持续自我迭代并变得愈发强大。

<details>
<summary>Original English</summary>
So uh to give you a very precise example, let's start with something very precise that I'd done. So uh a couple of months ago, I uh came up with recursive improvement improvements on a coding harness. So this was the first probably a public example of uh an automatic eval improvement. So to give an example, uh we used to do this thing where we would measure the quality of a coding agent using evaluation scores. So on terminal bench 2.1, Kimi K 3 with client would score um usually like, you know, um 60 70% and then depending on like how good the model is, like you get better scores on on terminal bench 2.1. So we noticed that when Kimi K 3 came out, our score was 77.5% which is a good score, but we were like, oh, is this is this truly is this truly the best score that this model can get on this benchmark? And also like what does the model release paper claim about what their best score is. So the model's release paper said that they could score up to 85% or even more. So we were just like, okay, okay. So we are not getting the sort of score and often what we do with model releases and clients is that we try to like optimize your score and try to get the best out of the model. So when we started hill climbing on the on the model like we we realized this we realized that like, you know, there's a lot of steps that we do such that we do it gracefully, such that we pursue the right kind of problems and do it the right way. And we started thinking like, okay, if we there's a lot of groundwork here, how do we automate it? And this is a demonstration of like how we automated it. So I'll I'll just leave that as a placeholder for now and we'll get get back to it later where we talk about in detail of like how does like this automatic improvement loop of a client harness works. So this basically means that like you have a coding agent harness that could just like basically improve itself and become better on on the same set of problems.
</details>

### 递归自我改进的概念与演进脉络

我们先从基础概念谈起：什么是递归自我改进？递归自我改进是指这样一个构想：一个 AI 系统协助构建出一个能力更强的新版本，由新版本重复该过程不断迭代，直至迈向通用人工智能（AGI）。系统不断演进提升，最终抵达技术奇点。最经典的范例莫过于**自我改进型编程智能体**——即能够对自身代码与机制进行持续改良的智能体。

大家可能会觉得这只是空中楼阁式的愿景，虽然听起来很酷，但它是如何一步步走到今天的？

如果回顾 Anthropic 在 2021 年的技术路线图，他们曾非常具体地指出：希望研发出一款通用的 AI 助手，能够通过对话形式与用户协作，完成软件的创建、修改与解释工作；它将展现出一名人类软件工程师同僚的全部能力，包括编写函数、定位缺陷、设计 API 以及探讨代码风格与最佳实践。他们当时表示并不期望一蹴而就，但这正是他们努力追求的方向。回想起来这已是五年前的构想，五年前人们便已预言，未来终将出现能像同事一样协同工作的通用智能助手，而这一愿景在今天已然实现。

紧接着在 2022 年，ChatGPT 横空出世。那是一个令人振奋的破局时刻，第一次点燃了整个领域的变革火花。

到了 2023 至 2024 年间，聊天模型首次获得了函数调用能力。最初仅限于简单操作，例如查询天气信息，或者在 Python 环境中运行某段计算逻辑并返回结果。

随后在 2024 年 Claude 3.5 发布之际，智能体才真正具备了调用实质性工具的能力，也就是我们如今所理解的工具操作：读取文件、编辑文件、进行网络检索、列出目录内容、以及在文件系统中搜索定位等。

同样在 2024 年，人们萌生了让聊天机器人相互交流的构想，进而促成了多智能体协作对话的出现。当时这类实现相当原始简陋，往往只是通过生硬的类结构、层级关系与调用链路拼接在一起，以一种非常僵硬的方式构建所谓的响应管线，试图让模型彼此通信。其流程在很大程度上偏向确定性，远不及如今这般流畅自如。这也催生了 AutoGen 等开源项目。

到了 2025 年，大家开始意识到：如果智能体的能力持续变强、速度越来越快、成本越来越低，局面将会如何？

随后在 2026 年，大家迎来了核心直觉：**如果智能体能够自我改进会怎样？** 这正是通盘演进的终极篇章。

<details>
<summary>Original English</summary>
So let's start with the ground terms. What is recursive self improvement? Recursive self self improvement is the idea that an AI system that helps [snorts] build a more capable successor which repeats the process, you know, until you hit our our our artificial general intelligence, right? You have better systems, you have better improvements, you have a better system and then, you know, you have singularity. So a classic example is like a self-improving coding agent, right? A self-improving coding agent is just like a coding agent that can improve itself. So you know, this this is all like a pie in the sky idea. Like it's like it's like, you know, yeah, sure, this looks cool. But how how did this even come out to be? Like how did we even get to here? So if you notice in the topic roadmap in 2021, in 2021's roadmap, they very specifically said that they want to develop a general AI assistant that can interact conversationally with a user to create, edit, and explain software. It would display all the capabilities of a software engineer colleague. It would write functions, it would identify bugs, it would design an API, discuss style and best practices, right? So we don't expect to reach this goal right away, but it's in the direction which we were striving. It's interesting how this was more than five years ago. More than five years ago, people had predicted that there would exist a day where you will have like a full blown journal assistant that can basically act like a colleague, which we do have right now. Then in 2022 ChatGPT got released. We all know how that happened. It was it was a fun moment. It was like the first time things got sparked for us. Then in 2023, 2024 there was the first time chats models could call functions. So these functions would be simple functions like hey, what's the weather or you know, what's the what's you know, what's this computation or what this computation result in Python? And then finally in 2024 when 3.5 was released, that was when the agents could like truly call like actual tools, the way we call like think of tools. So it's like reading a file, editing a file, you know, reading searching something on web, listing listing a folder, searching and grabbing through you know, a file system, things like that. So and in 2024 we had the intuition that like chatbot what if chatbots could actually talk to each other? You know, so then that's was the first time when we had like you know, multi-agent conversations. Now at the time these things were very janky, right? Like they were just like taped together in this like weird weird bizarre ways where you have just like these classes and these links and then like these hierarchies of classes and it was like it was all like kind of like a very janky attempt to like make us think that like these these models could like have this pipeline of flows of responses they can all communicate with each other. A lot [snorts] of it was like mostly deterministic and it was like even you know, it was not as free flowing as it is right now. So and you know, we started getting the intuition. So this was the autogen project, but like in only 2025 we we [snorts] started getting the agents like what if the agents just kept getting better and faster and cheaper? Like what what if that just kept happening? And then in 2026 we we had the intuition that like what if what if the agent could improve itself, which is like the final you know, the final part of the whole process.
</details>

### 从单轮问答到 TerminalBench 沙箱多任务评测

那么，智能体自我改进究竟意味着什么？过去我们在评测智能体时，往往习惯于单轮对话的形式。例如向模型抛出一个简单问题：“某种动物有多少只脚趾？”比如问“猫有多少只脚趾？”模型给出回答，我们来评判正误，答案可能是 10 只或 18 只——我自己其实并不知道猫到底有多少只脚趾，总之我们以此判定对错。

但在实际使用中，你要求智能体处理的任务要复杂得多。举个例子，你可以让它“帮我配置这个 MCP 服务”。这绝非单次交互就能轻松解决的琐碎任务：智能体需要去网上检索 MCP 的定义与配置规范，可能需要下载或编辑某些软件配置文件、添加数据库或更新 MCP 工具，还需要读取和修改本地文件，甚至运行一系列 Bash 命令。在它完成一系列操作并返回“我搞定了”之后，你需要运行一系列验证任务来评判：它是否真正达成了既定目标？

为了以更严谨的方式全方位测试智能体极限，我们在 Cline 大量使用了 TerminalBench。TerminalBench 是一个针对终端环境中的 AI 智能体的评测基准，是检验编程智能体能否胜任人类期望任务的核心工具之一。

一套完整的评测套件包含诸多模块。理想状态下，任务应当在独立的沙箱环境中运行。同时需要配备独立的判分器，对全流程进行监控：统计耗费了多少轮交互、消耗了多少 Token、耗时多久、调用了多少次工具、整体执行轨迹如何，并核查是否存在作弊走捷径的行为（如规避机制、直接联网搜索标准答案等）。

评测数据集通常包含一系列任务。在 TerminalBench 2.1 中共有 89 个任务。我们的做法是启动 89 个完全并行的容器沙箱，彼此隔离独立运行，各自尝试求解对应的任务。最终我们会汇总出一个综合得分。这一聚合得分不仅能反映模型的整体能力水平，还能暴露具体的失败模式。

失败的原因多种多样：可能是 `read_file` 工具调用失败；有时是模型推理过于缓慢，导致智能体虽然在持续运转并尝试推进（有时是在兜圈子），却因耗时过长耗尽了任务限定的 45 分钟而直接超时中断。

在明确了测试结果并捕获到失败案例后，我们会对失败归因进行分类归档。例如：工具调用类错误有 10 起，模型推理超时或异常有 20 起。完成分类后，我们便尝试对驱动框架（harness）展开改进——思考框架本身是否存在缺陷，通过修复这些缺陷能否直接提升模型的基准得分。这是一个不断循环迭代的过程，爬山优化往往非常耗费人工精力。过去我们投入了大量时间进行手工调优，但这也让我们深入掌握了如何系统性提升模型表现。

<details>
<summary>Original English</summary>
So let me give an example like what does it mean for an agent to improve itself, right? So like it's like a lot of times when we think of like evaluating an agent, we initially used to think of evaluating an agent in the form of like just a single turn conversation. So we would tell we would tell like um um agents that like ask a simple question like how many toes does a dash animal has? Like it could be let's say how many toes does a cat have? And then I will go through and the element would like prepare a response and then we would grade the response. So like a cat has maybe 10 toes or 18 toes or whatever many. I don't I actually don't know how many toes a cat has. But anyway um yeah so then we grade the response as like a yes or no. But like when you work with an agent there's a ton of things that you're doing. So let me give an example. Let me give an example. So for example you can ask an agent like hey set up this MCP for me. So now it's not just like it's not just like you know a trivial one shattable like thing like it will like search online to go what's the MCP? What is the config? So I'll like edit and download some soft files. Like maybe I need to add database update the MCP tool. Maybe I need to read and edit some files. Maybe I need to run some bash commands, right? So you do all of that and then the agent responds like hey I did it. And then you grade that with a bunch of tasks to gauge like hey did the agent actually accomplish the thing that it said it would do? So to do that thing the second part which is like more intricate where you're actually like truly you know testing agents like uh to their best extent like it's like you know um we use a thing called terminal bench. Terminal bench is a benchmark for you know AI agents in terminal environments. And that is something that we are we have a lot of like experience with at Cline. And it's like a it's like one of the best ways to like really gauge like is your coding agent accomplishing in general the tasks that you're doing that you want to be doing with a H written model. So there's a couple there's many different parts of a like evaluation suite. So ideally you want that to run in um [snorts] you know you you want that to run in um individual sandboxes. Then you have like independent graders that like check everything like how many turns it took, how many tokens it took, how much latency it took, how many how many how many tool calls did it make, what was the trajectory looking like? And then creating all the results for things like hey, did you not reward hack? Did you not cheat through the solution? Did you not just like look up the solution online? Things like that. So we we basically like a lot of these data sets of evaluation problems have a set of tasks. So when is a terminal bench 2.1 they have 89 tasks. So what we do is like we spin up 89 parallel containers where they all run online and they run in parallel and they're sandboxed and then they each try to solve a problem. So then they're all in parallel and independent of each other and then at the end we get get a score. So our score could like give us measures like is is a is this is the model performing well and what kind of failures it has, right? So like you run the evaluation, you get a score. So you get an aggregate score and this aggregate score could reveal a set of failures. So failures could be of any kind. Failures could be hey, the read file tool is not working. Sometimes the inference is so slow that like you know, the agent's working, it's doing, it's making progress, maybe it's running in circle, but it's so slow that it literally like runs out of time, it runs out of like 45 minutes or whatever many that were given for the task and just like stops working. So once you do that, once you understand hey, this is what we ran, this is what the failures we got, we bucket head the failures in different categories. So like 10 failures of you know, this kind of tool got 20 failures of like say inference not working or something else, right? And then we once we bucket the failures into different categories where like we try to make an improvement to the harness because like what if there's like something wrong with the harness that we could change such that the model score would improve, right? And on and on and on. You do this iteratively, it takes a while. It's just like you know, hill climbing is like a very worky kind of process and you know, usually usually we we we took we used to take a lot of time trying to do this, but it was a great way for us to like learn how to improve models. So [snorts]
</details>

### 双层学习循环：主智能体自主优化测试框架 17 小时

在公开基准上进行爬山优化时，我们萌生了一个想法：能否部署一个长程运行的智能体，由它来自动提升模型的评测分数？这正是我们实际落地的方案。

我们让具备长程能力的模型主导全局，作为核心管理智能体，而目标模型则在底层运行评测任务。管理智能体的运作逻辑是：指令底层模型运行测试并获取分数，随后分析失败案例与症结所在，接着对 Cline 的框架代码实施修改，并重新运行评测进行迭代验证。

大家可以预见这个过程极易失控偏差：单次完整评测便需耗时约一个小时，智能体必须解读反馈数据，确保合理解析问题并对框架做出实质性修改，同时防范走捷径刷分的行为（reward hacking），在确保真实性能改进的前提下重新触发测试。

我们让这套系统自主运行了整整 17 个小时。在极为细致的 Prompt 引导下，系统展现出了货真价实的持续爬山改进。在基线得分为 27% 的测试场景中，智能体自主排查出了死循环问题（即框架在解决问题时陷入原地打转）、后台进程长期空转卡死问题，以及文件索引等工程缺陷。当我提到“我们发现”时，实际上完全是由该核心管理模型自主识别、归类并实施修复的。它主动修改框架代码并重新评测，在长达 17 小时内完全自主运作，无需任何人工介入。当我回来看结果时，它已经在诸多维度上显著优化了框架的整体表现。

这背后的含义是：我们已经达到了凭借实测经验自主改良框架的新阶段。这里形成了一个**双层学习循环（two-level learning loop）**：
1. **执行层**：测试框架执行操作、与环境交互，判断自身行为的对错并获得反馈奖励；
2. **元认知层**：外层的元智能体（meta-agent）全程监控主框架的运行轨迹，找出修改点并合并代码变更，从而实现能力提升。

在我看来，在实时在线环境中运行这一循环要困难得多，因为实时调整极易导致对特定具体问题的过拟合，或陷入局限性过强的方案中。但我坚信这种机制在更广阔的问题谱系上具有普适性。我们所追求的正是让框架修改具备更广泛的通用适用性，确保在当前任务中积累的改进能够外推至更广泛的复杂场景。

<details>
<summary>Original English</summary>
one way to hill climb on public Evals is that like you know, we we could have a thing where you know, we started doing this thing where we could just like what if we could have like a long long agent that runs for a while and automatically improves the model score and that's what we did. So, we ran GPT 5.6 all that led the work and that was like the main agent and then uh K 3 was just running so what it was doing is that like GPT 5.6 was like hey run these get these scores, let me look at the failures, let me look at where where it went wrong and then I'll make changes to client's harness and then I'll run these again and then I'll keep trying. So, again you can see how like very quickly this can like go off the rails because this is supposed to be like the running in evaluation itself takes like an hour, then you have to read the feedback, then you have to like see if you're properly interpreting the feedback to make reasonable changes to the harness that are like not reward hacking that are just like actual genuine improvements and then run the again. So, we ran that for 17 hours and when we ran that for 17 hours there was like a legitimate hill climbing and what we found that was very interesting this happened with a very detailed prompt that accomplished this is that like we had baseline scores 27% and then you know we we found issues like loop detection loop detection is when a harness just runs in circles around the problem, right? Uh we found like background process grinding where background processes would run too long. Uh we found some file index issues and other things as well. I mean when I say we what I've actually made is GPT 5.6 all, right? So, that found those issues that found and bucketed those issues was like hey how about I make those changes in the harness and I run the again and iteratively the hill climbing process completely autonomously on its own without my interference and 17 hours later when I come back to it it like it has improved the harness performance in so many ways. So, see what does that mean? What does that mean? It just it just basically means that like we are at a point where the experience could make the harness better that like there's like a two level learning loop where the harness does some action, interacts with the environment, understands whether or not it did the right thing or the wrong thing and gets some reward and and like almost and then has there's like a meta agent that's observing the main harness and finding the changes to it and just like incorporating those changes and improving. Now, it's I think in my personal opinion, it's much harder to do in real time because if you do it in real time, you over index on solving certain problems or you're just like too curtailed to a specific thing. But I do think that this is something that works like on a broader scale of like working on a wider range of problems. And you want to be able to like you want you want to be able to justify the changes you're making on a broader active applicability so that the changes you make here will apply to a broader range of problems as well. So, what does that mean? What am I trying to get at here?
</details>

### 从全栈系统闭环到人类纠错信号的价值

我想表达的核心观点是：**当前的模型能力已经强大到不仅能够优化测试框架，还能优化技术栈中的众多环节。**

模型还能改进什么？OpenAI 曾发布过相关成果：前沿大模型完全自主重写并优化了其线上的生产内核（production kernels），直接将端到端推理服务成本降低了 20%，同时 Token 生成效率提升了 15%。这一工作完全由模型独立达成。这意味着推理正变得愈发廉价。对于像 OpenAI 这样的机构而言，前沿模型服务成本降低 20% 就意味着数十亿美元的成本节省；而在个人或团队场景中，大家同样可以借助这种手段优化自研模型。

另一个有趣的现象来自 GPU 算子编写竞赛。在 CoreWeave 举办的内核编写比赛中，获胜者明确表示自己从未手写过任何 GPU 算子代码，完全是由智能体驱动生成的。大家可以看到，当今顶尖的推理优化与算子改进，已经完全且排他性地由智能体集群或智能体自主魔法驱动，从而换取更快速、更便宜的推理。

因此，自我改进所覆盖的范围远不止驱动框架本身，而是横跨整个技术栈：从基准评测、框架改进、训练数据构建、后训练（post-training），再到物理世界交互与模型推理。从电能输入计算设备、发出 API 请求、模型执行推理生成响应并返回结果，全流程的每一个环节都存在优化的空间。

整个 RSI 闭环涵盖了几个不同组成部分：
- **预训练阶段**：例如 Nemotron 利用 AI 筛选清洗的高质量预训练数据；
- **后训练阶段**：例如 Constitutional AI 在对齐优化中的应用；
- **推理与运行阶段**：例如模型自主重写算子降低成本；
- **评测与数据生成**：例如我们在测试框架中实现的自动迭代。

广义而言，只要模型在执行某项任务时遭遇失败或未能达成预期，这就是优化的切入点。例如在日常协作中，你让模型执行一个看似并不复杂但在长上下文中容易出错的任务：为数据库新增一列、填充数据，并在前端架设缓存层。模型完成了整个过程，但在将缓存部署至数据库前端时配置失误。此时你会指出错误：“不要这样配置缓存，请将 TTL 设置为指定数值”。给出一个修正信号后，问题迎刃而解，你继续日常工作。

而我的理解视角是：**在数字化工作场景中，人类给出的每一次纠错，本质上都是待填补的差距增量（delta）的一部分。**

这意味着每次你触碰到模型的能力边界——无论是推理深度的瓶颈还是解题维度的限制——我们都在定位那个尚未弥合的差距，并推动技术前沿向前推移一步。这正是后训练的核心使命：寻找极具挑战的长程复杂任务，并借助闭环机制引导模型在这些问题上持续爬山迭代。

**任何具备可验证闭环（verifiable loop）的领域，均可被系统性优化。**

这种规律并不局限于软件世界，物理现实本身同样可以构建可验证闭环。举一个生动的例子：视频展示了一台正在自主敲击键盘打字的机器人，其打字内容非常耐人寻味——它正在输入自己如何攻克机器人学难题的思路。如果机器人自身能够解读执行结果并持续自我迭代，这实际上就已经具备了人工超级智能（ASI）机器人的雏形。

我个人生活中的另一个例子：我曾为女友准备过一个硬件小礼物，那是一块内置了视觉摄像头、扬声器与麦克风的计算芯片。在最初配置时我发现它响应缓慢、延迟偏高，其内部本身运行着一套智能体系统。于是我将该硬件接入电脑，部署编程智能体在该硬件环境上运行，由电脑自动向该硬件下发任务（例如提问“你当前看到了什么”），并实时监控端到端的推理响应延迟。结果智能体能够将高延迟、慢响应或算法不合理的每一个场景逐一细分拆解。随后我搭建了一套递归改进闭环：通过为编程智能体提供 OpenRouter API Key，令其自动更新底层固件、优化工具调用逻辑、更换推理模型乃至语音转文字（STT）模型。经过整夜由智能体自主执行的硬件调优实验，这块小巧精美的硬件设备得到了深度优化。这证明硬件系统同样能够融入 RSI 闭环。

将这些闭环逐一打通后会带来什么？更低廉的推理成本、更充裕的实验预算、更高质量的数据以及更强大的模型。这是否意味着奇点的临近？这是一个值得深思的问题。RSI 闭环的各个拼图碎片其实已经就位，我们距离全流程闭环已然近在咫尺。

<details>
<summary>Original English</summary>
The point I'm trying to get at is that the models are so good right now that they can if they can improve the harness, they can improve a lot of other things. So that then what else can they improve? So this is this is a this is a post primarily from OpenAI where GPT 5.6 all autonomously re-wrote and optimized its own production kernels and those production kernel improvements remove the end-to-end serving costs by 20 percent, you know. It also had 15 percent higher token generation efficiency and this was like completely done by 5.6 all on itself, right? So what that means is that like inference is becoming much cheaper and that means that like if on if if for a company like OpenAI, if you're having 20 percent lower lower serving cost for a frontier model, that could be a billions of dollars of improvement in price and you could you could do that as well for your own models. Um, another interesting thing is that like when people have kernel writing competitions, so Core Auto is a company which has a kernel writing competitions and you'll notice that like they they mentioned that like the person who won the kernel writing competition, they explicitly said that I've never handwritten a GP operator. It's all an agent driven. So notice that like how like the best inference improvements, kernel improvements are at this point completely exclusively done by a swarm of agents or generally just like agents doing some magic to you know magic improve like the kernel kernel code and have faster inference, cheaper inference, um yeah. So basically like the improvement surface that you think of is not just like the harness improvement. It's literally the whole surface stack, right? So the whole stack from like evaluation to harness improvements to training data to post training to world interaction to inference. Like literally the entire part of pipe part of the pipeline. Like all the way from like electricity going through your machine to like making an error request, going through the model, models doing inference and making a response and getting back to you. Like every single part of the pipeline we can optimize it. So the whole RSI loop has like um there's a couple of different parts. So it's like pre-training um uh Nimo Tron examples of like you know AI curated uh pre-training data that was good. Um there's like post training examples which are you know where where there's like constitutional AI examples of like post training uh improvements then inference. I gave you the example of GPT 5.6. So for Evals and Eval generation I gave you our own example of how we improved ourselves on our own Evals. Um in general what you want to think of is that like anytime a model is trying to do something and it's like not able to do it or not able to accomplish it. So for example like imagine you're having a long conversation where you ask the model something obvious. So like it's like or something that you think is not necessarily obvious but it's like it's hard but you would assume that the model could potentially do it. So to give an example let's say you want to make add a new column to a database and then fill that column, right? And then put a cache in front of it. So what happens is that it does the whole thing but for some reason the way it pushes the cache in front of the whole database like it kind of doesn't do it right. So at that point you're like oh no set this cache differently, set this as the TTL and then you give like a correction signal and then that kind of like fixes your problem and you kind of go about your day. But the way I want to think of it is that I want to think of like every single time like a human correction to the digital landscape is a part of a delta that needs to be covered. And what that means is like every single time you're finding like the edge of model capabilities of like how far it can push for inference, how much it can push for this, how much it can push for you know solving your problems, you want to find the delta and we want to like push that frontier a little bit further, a little bit further. And that's what post training does, right? So post training is is is is in that post training. We find these like really interesting and really hard long horizon problems for uh for coding agents or for other kinds of problems and then just like slowly hill climb their models on on those kind of problems. So anything that has a verifiable loop can be optimized, but is this is not just limited to software. Like literally like the physical world itself could have a verifiable loop. So to give an example like let me let me give you a very funny kind of bizarre example where like it's like you you look at this and you um um look at this uh like robot and it's it's typing something and it's like really really like interesting what the robot is typing. So notice how like notice how the robot is itself typing like how it wants to like solve robotics and imagine if the robot itself could like interpret the results of of like the answers and just like keep improving, then that means that like this is you know basically like an ASI robot. Another example that I could give you from my uh personal life is that like yeah I have this um chip that has the ability to see and has a speaker and has a microphone inside of it. So I was trying to set up this uh with my machine and it was um a gift that I had for my girlfriend and what I found very interesting about this is as I was trying to set it up it was very slow, it was slow to respond, it had higher latency, it had an agent in enough itself, right? So what I did was I connected this step to my uh computer and I let um I let um coding agents run on this hardware and basically run on this hardware automatically make tasks to it. So like my computer would talk to my hardware, give it some tasks like, hey, do this, do that, and just like, what do you see right now? So then it would notice the end-to-end latency of like the inference response of like how fast uh my hardware is responding. And then um what I found is that like it was able to do the breakdown of like every single case and scenario where there was like higher latency, um slower response, or or just the algorithm wasn't right. And I could then set up a recursive loop where both the firmware could be updated, the um the tool calls, the inference model used, um the speech-to-text model used, all of those could be improved automatically with like an open router key which I'd given to a coding agent. And then overnight with self-running experiments with the hardware, uh my um this tiny little piece of beautiful hardware that I have was like deeply optimized. So it was this also like even hardware could be a part of the RSI loop. So what happens when you connect these loops, right? That's the next question. Like you could have cheaper inference, you could have like more experiments budget, you have like, you know, better data and better models. So is this single rarity? So a question to ask. And I think that the part is the parts of the loop are already there, right? Like we're we we are really we really are very close to parts of the RSI loop, right?
</details>

### 给软件工程师的职业建议：靠近 RSI 闭环并选择耐受扩展的难题

面对这样的技术变局，我们在职业与个人规划上该如何应对？

给所有听众的诚挚建议是：**请务必尽可能向 RSI 闭环靠拢。**

眼下许多人正忙于开发各种应用层软件，例如“面向建筑行业的 AI 智能体”、“面向某某细分领域的垂直 Agent”等。在我看来，这类方向往往是一叶障目，不见泰山。我们面对的是一项足以改变人类历史进程的造神级技术，然而很多人却缺乏足够的野心去挑战最硬核的命题。

问题不仅在于缺乏雄心，更在于大家所执着攻坚的许多方向，往往只要底层模型进行一次版本迭代，就可能被彻底抹平淘汰。此外，日复一日地坐在屏幕前让 AI 跑脚本（“Claude 帮我做这个、帮我做那个”），是否真的具有智力挑战性？这是否是一个人最高效、最深刻的智力投入方式？我们理应去攻坚更具前沿挑战性的难题，而我们的发展上限往往受限于自身的野心。

与其在琐碎细节中消耗精力，我的建议是：去追求你内心笃信的事业，并主动参与到能够推动你贴近 RSI 闭环的工作中。任何位于技术端到端闭环上的环节都值得深耕：模型在哪些环节尚存短板？是推理瓶颈、后训练优化、还是实体物理交互？亦或是构建端到端流水线、解决硬件底层挑战、攻克网络通信难题、建立技术社区等。选择那些能让你作为工程师直接承接模型进化红利的工作。

这里引用 Anthropic 的一张非常有见地的幻灯片。他们提出：**假设你只剩下 1 到 5 年的窗口期来为这个世界做出实质性的智慧贡献，你将如何选择？** 他们给出了极佳的策略建议：
- **优先开展野心勃勃、目标高度明确且快速推进的协作**；
- **大幅压缩时间规划**，缩短项目周期；
- 认真推演研判：如果你正在攻关的课题需要投入极高成本，**不妨权衡等待下一代前沿基础模型发布是否更为划算**；
- **专注于能够从模型规模扩展（scale）中受益的问题，同时坚决回避仅凭模型自身扩展就能被轻易解决的项目**。如果一个课题仅仅随着下一次大模型发布便迎刃而解，那么它大概率不值得你耗费精力。

我们需要在哲学层面深入反思：什么样的探索能够极大地承接模型进化带来的红利，同时又不会在模型迭代的浪潮中被直接抹去价值？更理想的状态是，这项探索本身能否成为模型自我改进链条中的一环？如今许多创业团队转向数据管道构建，或者投身物理硬件开发，均体现了这一趋势。

如果你是一名软件工程师，若你在日常工作中感到自己的智力投入与产出差距未能体现价值——即便你具备过硬才华，但基础模型一次交互就能抹平你的日间劳动成果——那么此刻非常值得你停下脚步，抽离出来审慎思考：究竟哪些领域的问题才需要你真正贡献实质价值，并能经得起时间的洗礼？

在当下完成这一维度的认知反思与方向重构，将在漫长的未来为你带来不可估量的长远回报。

非常感谢大家的聆听与宝贵时间。如果你坚持看到了最后，相信你必定在深入思考这场人类历史上最波澜壮阔的变革。这其中存在诸多深刻的哲学思辨，有人可能认为我对时间线的判断有偏差，或过于悲观、或过于乐观，我都非常期待听到大家的反馈。屏幕上是我的二维码，欢迎扫描交流探讨。再次感谢大家的时间！

<details>
<summary>Original English</summary>
And what do we do? Like what do we do about this? And it's like, how do we think of that in terms of like our career? And how do you think of that in terms of, you know, our lives and what do you want to do next? So here's my advice to everyone who is watching this, like please, please, please, please move closer to the RSI loop, right? So it's like right now like people are working on all these like different kinds of software which is like, you know, AI agents for, you know, construction, AI agents for this, AI agents for that. And it's like I think that you're you know, well the way I see those things is that like I think of those as like you're missing the forest for the for the trees. You really are. And it's like you have this like very interesting godlike technology that can change the course of humanity. And then we're not ambitious enough to pursue the best problems. We really are not. And we're just like I think that it's not just like the problem isn't just that we're not ambitious and we're also like what we're pursuing a lot of those things are just like one model release away from like being completely like wiped out, right? So like it's also like it's also like it may not be that intellectually stimulating because like all you're essentially all we're essentially doing is like sitting all day it's like hey cloud do this for me, hey cloud do this for me. And I don't know if that's like I don't know if that's like the most intellectually stimulating or like or like um thoughtful use of a person's time. Like maybe maybe you know we're supposed to be solving harder in more more frontier problems and I think that like it's like the ceiling is like our ambition. So instead of like working on these tiny things my suggestion to people is to like you know do things that of course like goes without saying but you should do things you believe in and you know I'm just a guy on the internet but do things that help you move closer to the RSA loop, right? So like anything that's just like the end-to-end pipeline of like hey this is where like the models are lacking like it's like whether that's inference, whether that's post-training, whether that's literally like physical interaction, whether that could be you know sending sending end-to-end pipelines of truly any kind, you know whether that's hardware problems, whether that's um networking problems, whether that's um building a sense of community, things that just you know um things that just like help um you as an engineer get closer to the benefits of the improvements um in in um um in in the model. So this is a very interesting slide from such a topic. So um um they mentioned that like you want to have like this you're in this space where it's like you know you only you only have like one to five years left to contribute luxury to the world, what do you do? Right? So it's like um they they give great suggestions where like prefer ambitious targeted and fast collaborations, right? And you know in general like the timescale, like, all the timelines that you give to yourself, like, they should be just a completely squeezed out. Should be completely squeezed out. Because it's like, a lot of times, and you also have to think through that, like, if if the model if the problem that you're working on is too ambitious, like, it's like, is it probably is it probably better to wait for just, like, the next next frontier model to come out or not? Like, that's that's something you also have to weigh through, right? And you you ideally want to work on problems that benefit from scale, and, you know, you also at the same time want to avoid projects that can be solved by scale alone because then, you know, if even if like it's like if you're working on a problem and then the next model release comes out it solves the problem. So that's not that's probably not a good thing to do. So it's very like you have to like think philosophically of like what is the endeavor that benefits greatly from model improvements but like isn't also completely wiped out from it. And then ideally like it's like if the if the endeavor could also be a part of the the like the improvement pipeline, that could be amazing. So you see a lot of companies raising on say making data pipelines and there's a lot of money there. There's a a lot of companies working on physical hardware and stuff. So I think if you're a software engineer watching this it's like I think that if you're if you feel like you're like here the delta of your intellect and ability in your day-to-day it's like not contributing as in like you have the intellect, you can make a difference, but like if Cloudflare is just like one shotting all those problems like in your day-to-day and you're just like kind of like becoming a it's worth to think through, take a step back and think through. It's like, okay, where are the problems where you're actually truly contributing and that they will stand the test of time. And then those that kind of reflection and realignment right now would I think like have like very interesting consequences for you in the long term. So yeah, so thank you so much, you know, thank you so much for your time. Like I think that I think that if you're watching this and if you've gone this far I think that you're definitely contemplating like one of the most interesting improvements in the course of humanity. And you know, know many philosophical arguments here. Some people might say hey you know I I think I'm maybe I'm off on the timelines or maybe maybe I'm I'm just being too pessimistic or maybe I'm being too optimistic, but I would love to hear all those thoughts. So this is you know my QR code. Please feel free to scan it and let me know all your thoughts. Thank you so much. Very kind of you to give me your time.
</details>