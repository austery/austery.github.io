---
author: AI Engineer
date: '2026-11-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=7WUzHIF32vA
speaker: AI Engineer
tags:
  - model-evaluation
  - agentic-workflow
  - regression-testing
  - adversarial-testing
title: AI 评测方法论：测试完整工作流而非单一答案
summary: 演讲者探讨了高风险 AI 应用中评估体系（evals）面临的困境与构建原则。核心观点包括：设定最具野心的成功目标而非追求满分、评估整个工作流各步骤而非仅看最终输出、构建包含自动化流水线与博弈测试的多维评估体系、持续进行回归测试，并将现实生产故障转化为评估用例以兑现产品承诺。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ramakrishnan Lokanathan
companies_orgs:
  - Lawrence Berkeley Lab
  - London Business School
products_models:
  - eslams
  - GPT-3
  - ChatGPT
  - Gemini
  - Google Assistant
media_books: []
status: evergreen
---
### 为什么当前的 AI 评测体系存在问题

我想大家今天聚在这里，主要是因为目前的评估体系（evals）非常不尽如人意，对吧？这也正是我们想要探讨并理解如何解决的问题。

更多时候，我认为评估体系之所以不起作用，是因为我们把它搞得太复杂了，而且我们并没有真正理解它，对吧？我们常听到诸如“评估比模型更重要”、“评估比难度更重要”之类的说法，但评估到底是什么呢？这是我们大家都会面临的一个问题。当我与那些构建高风险应用的人交流时，我也经常碰壁，甚至很难从第一性原理的层面去理解究竟什么是评估，对吧？

<details>
<summary>Original English</summary>
I think why all of us are here primarily is because eval are currently very broken, right? And like that is what we're trying to explore and understand how to go about it.

More often than not, I think evals are broken because we overcomplicate it and we don't really understand, right? We hear things like the eval is more important than the model and the eval is more important than the hardness or whatnot, but what even is an eval, right? It's a question that we all sort of come to and like this is something that I consistently hit when I speak with people building high stake applications to even understand to the first principle level of what an eval is, right?
</details>

什么是评估（eval）？它其实就是评价（evaluation）这个词的缩写。我们对 evaluation 的理解，就像我们熟知的考试（examinations）一样，这是我们在人类身上完全能理解的概念。如果仔细想想，作为人类，我们一生中会经历各种各样的考试，比如考 SAT、GMAT、律师资格考试等等，不论我们从事什么行业。

你可以将同样的思路平行应用到评估（evals）中，把 evals 想象成针对 AI 系统的考试。你有 SWE-bench、人文学科法律考试等等各种测试。在很多层面上，这都是在尝试评估并了解一个模型或智能体（agent）在某项任务中的表现。归根结底，考试和评测都只是任务、标准和证据，用来评估并理解某样事物是否如你预期的那样运行。

<details>
<summary>Original English</summary>
And what is an eval is just a abbreviation of the term evaluation, right? And how we understand evaluation is like we know exams, which are examinations and this is a concept that we understand in human beings, right? And if you think about it, as people we write a variety of exams through our life, like we write the SATs, the GMAT, the bar exam and like regardless of what we do.

That is the same sort of idea you can apply as a parallel into evals and then you can think about evals as those examinations for AI systems, right? You have the SweetBench, the humanities law exam and all of this. In multiple ways, this is trying to evaluate and try to understand how a model or an agent will be working in something, right? At the end of the day, examinations and evals are just tasks, standards and evidences to sort of evaluate and understand how something is to perform on something as you expect, right?
</details>

### 单一测试不能代表全部能力

我认为这也引出了一个非常关键的区别。考试必须回答一个有明确边界的问题。以 SAT 为例，它是一门大学入学考试，能告诉你学生在语言和数学方面有多优秀，但这仅仅是衡量是否具备大学就读能力的**一个信号**。我来自印度，直到今天在印度，大学录取依然是通过单门考试来决定的。然而，如果你看美国的考试，SAT 只是大学就读能力的信号之一。

我认为这一点极其关键。你不应该只锚定在某一个评估或测试上，它应该只是衡量你平台就绪度的一个信号，而不是过度关注你的模型在人文学科考试或 SWE-bench 上表现非常出色。因此，没有任何一个评估或测试能衡量一个对象的完整能力，在进入这一领域时必须始终明确这一点。

归根结底，我们通过评估试图回答的是：在任何特定时间点，我们的表现是否兑现了向消费者或用户做出的承诺？这正是任何评估的任务——确保我们交付的产品或智能体所展现的性能，能够兑现给消费者的承诺。

<details>
<summary>Original English</summary>
And I think that brings us to a very key distinction here as well. An exam must answer a bounded question and let's take the example of the SATs.

Um it's a college entrance exam and it tells you how good a student is on language and math, but it's just one signal of a college readiness, right? I come from India and even today in India your college admissions are done with a single examination. However, let's say you look at the US exam, SAT is one signal of college readiness, right? And I think that's extremely key. You should not index on one eval or one test and it should just be one signal of your readiness to the platform rather than trying to sort of over index on your model being really good at humanities class exam or at W bench, right? So, no eval or no test is a measure of someone's complete abilities and that should always be clear going into that.

So, at the end of the day, what we try to answer with evals is is our performance matching the promise that we're making to the consumer or the user at any given point in time, right? And that's the job of any eval to make sure that we go ahead and ensure that the promise of the product of the agent that we're providing is meeting its performance to the consumer.
</details>

### 个人背景与经历

在继续之前，我想先简要介绍一下我自己。我是 Ramakrishnan，来自印度南部的科钦市（Cochin）。我很小就开始写代码，高中时就开始构建机器学习分类器等等。我的职业生涯始于一家印度教育科技独角兽企业。

这让我在 2021 年有机会看到了基于 GPT-3 的产品演示，展示如何改进我们的内容流。作为一个从小热爱机器学习的人，这彻底改变了我的认知，我觉得这真的会改变世界。而我的成名作，或者说我做对的事情，是在 2022 年 9 月，我们断定基于 GPT-3 API 将会涌现出一波全新的应用。在我们全职投入大约两个月后，OpenAI 发布了名为 ChatGPT 的 GPT-3.5 研究预览版，这彻底改变了我们的生活——它既验证了我们的方向，也杀死了我们原有的产品。

于是我们经历了几次转型，最终落脚在一个宠物护理 AI 助手上，并在其上通过电商和推荐引擎实现商业化。后来我们在印度被收购，那段旅程就此告一段落。在那之后，我一直对这些系统的演进非常感兴趣。由于我们很早就基于 GPT-3 进行构建，评估对我们来说至关重要。这促使我成为了 NeMo Tron 3 模型的红队测试人员（red teamer）。我现在在劳伦斯伯克利实验室（Lawrence Berkeley Lab）从事 AI 安全研究，同时也参与伦敦商学院（London Business School）的数据科学与 AI 项目。主要是为了广泛探索如何看待我们正在研究的新技术，以及我们如何去观察和探索。

我在这里不代表任何一方的利益，不会为任何供应商背书。这纯粹是为了理解如何思考评估、如何构建这些高风险应用，也是我长时间以来与多方交流，以及我们在数百万用户使用我们 AI 产品的多次落地实践中总结出的思考。

<details>
<summary>Original English</summary>
Before we move ahead, I wanted to sort of give a small brief on who I am. I'm Ramakrishnan. I come from the city called Cochin in in South of India. I started coding very early on and started building machine learning classifiers in high school and whatnot. And I started my career with an Indian EdTech unicorn which gave me the opportunity in '21 to get a demo of a GPT-3 based product on how to better our content flow. Which changed my mind being someone who really loved machine learning from an early age and I was like this is going to really change the world, right? And my claim to fame or like what I was right in doing was in September 2022 we decided that there is a new wave of applications that going to be possible that are going to be built on the GPT-3 API, right? And about two months after we went full-time, OpenAI released released their research preview for GPT-3.5 called ChatGPT and like that literally changed life for us and it validated us and killed us as well, right? So, went through multiple pivots and then we eventually landed on a pet care AI assistant and we monetized it using e-commerce and recommendation and engines on top of it and we got acquired in India and that was the end of that journey, right? Uh after that, I've been super interested in understanding how these systems evolve and because we were super early on building on GPT-3, evals were critical for us to build. So, that took me to being a red teamer at for the NeMo Tron 3 models. I work at the Lawrence Berkeley Lab right now on a AI safety research and also with the London Business School data science and AI initiative. Broadly to explore how to sort of look at the new technology that we are working on and then how we see and explore, right? So, I am not aligned or like, you know, with anybody here, so I'm not going to sponsor a vendor. It's just to understand how do you think about eval and like build these high-stake applications, right? And the consolidation of the conversations that I've had over time with multiple implementations that we have done with millions of users using our AI product, sorry.
</details>

### 评测的当下价值：弥合生产环境的落差

这是我坚信的一点：十年后，评估将不再重要。因为如果我们相信模型能力会持续提升，我们就不需要像现在这样进行如此多的评估。然而，在过渡的中期阶段，生产环境是无法等待的。

问题在于，如果你没有合理的评估体系，就会出现像麻省理工学院（MIT）关于生成式 AI 鸿沟报告中所描述的情况——95% 的企业无法获得任何回报，因为你在生产环境中无法兑现利用大语言模型试图给出的承诺。而这正是我们今天必须通过评估来解决的问题。在十年后，评估可能只是一种确认手段；但在今天，它的作用是确保你在生产环境中真正交付了所承诺的效果。

<details>
<summary>Original English</summary>
So, this is something I strongly believe. So, evals are not going to be relevant in a decade's time. Because if we are to believe that model capability is to keep improving, we will not have to have as much eval as we do. However, in the mid-term, like production cannot wait. The problem is if you don't have the right amount of eval structure, you get reports like the MIT GenAI divide where 95% of organizations are not able to get any returns because you are not delivering the promise in production that you're trying to make with the LLM, right? And that is what we have to solve with evals today and in 10 years time, evals is just going to be a validation of this. But today, it is to make sure that in production you are delivering the promise that you're going ahead for, right?
</details>

### 原则一：定义最具野心的成功目标

因此，在为高风险应用构建评估时，你需要考虑的第一件事，就是在设计任何测试之前，定义出最具野心的成功。比如设想在通用人工智能（AGI）的时代，你的 AI 智能体应该做什么？或者你能从中获得的最佳结果是什么？

确立这个目标能真正为你提供后续设计的边界。你要从任务本身出发。首先要问的简单问题是：**必须发生什么？** **绝对不能发生什么？** 以及**何时应该停止？** 你可以将这些延伸到其他 WH 疑问词和第一性原理，去思考能达成的最具野心的结果是什么。

要瞄准你所需的任务，而不是你能获得的分数。如果你的评估得了 100 分（满分 100 分），那你的评估就做错了。这说明你不够有野心，测试得不够充分。如果你看看当今的任何模型评估，大家的得分最高也就 85、86 分左右，没有人能拿 100 分。因此，你必须确保你的评估和野心超越当前的模型能力，从而对其进行压力测试，而不是让测试变得容易。

<details>
<summary>Original English</summary>
So, the first thing that you have to think about as you build evals for high-stake applications is to define the most ambitious success, right? Before designing any test. Like, assume in the world of AGI, what is your AI agent going to do? Or what is the best outcome you can get out of it, right?

And setting this goal really gives you the scope of what you can go ahead and design further, right? And you start with the job. And simple the first question that you ask is what must happen? And what must never happen? And when should it stop? And you can extend it into other WH questions and first principles to go ahead and think about what could be the most ambitious outcome that you can get out of it, right? And aim at the job you need and not the score you can get. If you have an eval that is scoring a 100 of a 100, your eval is wrong, right? And you're not ambitious enough and you're not testing enough, right? If you look at any model eval today, people are at like 85, 86 max. Nobody gets to 100. So, you have to make sure that the evaluation and your ambition is beyond what the model ability today is for you to make sure that you're putting it to the stress test and not making it easy, right?
</details>

### 原则二：测试整个工作流，而非仅看最终答案

一定要测试整个工作流，而不仅仅是最终的答案。以原图为例，我的要求仅仅是更换背景，如果我只看输出结果，输出确实将背景换成了米色背景，但现在它却多出了两个把手。所以必须非常清楚，你必须始终对工作流本身进行测试。

这是一个非常简化的例子。假设你的工作流包含 100 个步骤，每一步都必须针对其输入、输出以及预期结果进行评估。你不能只看起点和终点，然后说：“好的，如果对比起点和终点，背景确实改变了。”但这真的是你想达成的目标吗？所以在处理问题时，务必关注整个工作流。

<details>
<summary>Original English</summary>
And always test the whole workflow, right? And not just the final answer. And this is the original picture and my request would be only change the background, right? And I am just looking at the output and the output has changed the background to a cream background, but it has two handles now, right? So, it has to be very clear that you have to always test the work. And this is a very simplified example of this. Let's say you have a 100 steps in your workflow. Each step has to be evaluated for what goes into that step and what comes out of that step and what is the expected outcome.

You can't look at the start point and the end point and be like, "Okay, if you look at the start point and the end point, the background has changed." But is that the objective that you're trying to achieve, right? So, always for look at the whole workflow when you're approaching things, right?
</details>

### 原则三：构建全面的综合评估体系

第三点，我也想谈谈我在这方面做的一些工作：单一分数并不能代表系统，其核心在于构建一个全方位的综合评估体系。

在 2022 年和 2023 年刚接触模型时，你衡量的是代码能力，或者写作能力等。但如今你面对的是必须执行多项任务的具备智能体能力的持久化系统，因此你必须确保在任何时刻都在设计全面的评估体系。

该体系的第一项要素是：**自动化检查和评估成为 CI 流水线的一部分**。每次你的智能体经历生产部署流程时，都必须对其提出评估问题。将其纳入自动化检查，可以确保你并非只在选型模型的那一刻看一次评估分数。

第二项要素是：**持续进行人工审核**，确保结果合乎逻辑。不要在任何时候都完全依赖你的智能体来担当评估结果的审核者。你可以利用智能体来加速评估流程，但务必引入人工审核。

第三部分是**对抗性测试**。你在哪里能打破工作流，并将其置于充满挑战的情境中？哪里可以引入对抗性测试？

<details>
<summary>Original English</summary>
And the third thing, and I'm I'm going to talk a little bit about something I've been working on in this space as well, is one score is not the system, right? And the idea is to build a holistic evaluation system.

When you started off with models in 2022 and 2023, you were measuring for coding ability or let's say you were measuring for writing ability, etc. But today you have agentic persistent systems that have to do multiple things, right? So you have to make sure that you're designing a holistic evaluation system at all points in time.

And the first element of that is that automated checks and eval being part of your CI pipeline, right? And your eval questions have to be asked to your agent every time they are going through a production deployment process, right? So that being part of the automated checks make sure that it's not like one eval score you are taking at the time you're deciding the model.

Continuously human review and make sure that the results make sense. Don't rely on your agents to be the reviewer of your eval at any point always, right? You can fast-track your eval process with it, but make sure you're doing human review.

And the third part is adversarial test, right? Where can you break the workflow and like put it into challenging situations like where you can have adversarial testing?
</details>

### 通过博弈测试智能体的长链推理能力

我最近一直在研究并很想分享的一件事，就是如何根据测试所能揭示的故障来选择测试，也就是“能够反击的测试”这一理念。今天在 SWE-bench 上有一项任务，智能体或模型被要求执行一个任务并给出一个输出，但这里没有持续的思考或评估。

一次次得到一个正确答案，并不等同于做出一连串良好的连续决策，而你需要智能体动作、长链推理以及所有这些能力。长久以来，人类衡量智能体动作和长链推理的最佳标准一直是国际象棋和围棋等棋盘游戏。即使在模型评估的发展中，AlphaGo 也是 AI 发展中非常关键的一步，但它们是专门为了下围棋而训练的模型。

当今的通用大语言模型，我们并没有在围棋或象棋上对其进行测试，而这正是我试图通过一个名为 E play games（eslams）的开源代码库来解决的问题。你可以直接通过 Python 的 PyPI 安装该软件包，让你的智能体和模型去玩游戏，观察其表现并进行测试。假设你要用一个改进后的模型替换旧智能体，你可能会希望旧智能体和新智能体下盘棋。我并不是说比赛的赢家就是更好的模型，但它们如何进入那场对局并展开博弈，会向你展示更多关于如何运用该模型的信息。

因为在下国际象棋时，你需要改变策略、必须摆脱昏招，而且你走出的棋步在之后可能会变成你的劣势。因此，你的智能体如何进行推理，构成了综合评估之外的一个附加范式。这里的思路是进行代码评估、写作评估、人文学科期末考试，并尽可能拥有更多范式，这也正是我想通过 E Slams 构建的目标。

我们支持大约 50 款游戏和 90 家不同的提供商。我们有象棋和围棋，用以考查规划能力和可见状态；我们有扑克，它是基于隐藏信息的决策；我们有基于共同目标和协作的合作类游戏；我们还有街机游戏的测试。所有这些都能让你深入了解模型及其思考方式。

<details>
<summary>Original English</summary>
And one thing I've been recently working on and would love to talk about is um the idea of how you can choose the test for the failures it can reveal, right? And the idea of a test that can fight back. Today you have a task on SW bench, the agent or the model is asked to go ahead and perform one task and give an output. But there is no continuous thinking or evaluation, right?

And getting one right answer more and more is not the same as making a good sequence of decisions, and you need agentic action and long-chain reasoning and all of these things. For the longest time the best measure of agentic action and long-chain reasoning in human beings have been board games like chess and go. And even when you go ahead to um like like evaluation of like a model, AlphaGo is a very important step to AI development, but it they were very specifically trained models for playing go.

Today's general-purpose LLMs we don't test on Go or chess, and that is what I'm trying to solve with an open-source repo called E play games, right? So, you can just install the package. It's a Python PyPi package, and you can make your agent and your model play games and see how it works. And how can you put it to test, right? You have You're replacing an agent with an improved model. You might want your old agent to play with the new agent on on a chess game of chess. And let's say I don't I'm not saying the winner of that match is a better model, but how they enter that match and play that match will tell you a lot more about how to sort of go ahead with that model.

Because playing chess, you are changing your strategy, you have to get out of blunders, and move that you make can become liabilities for you in the past. So, how is your agent reasoning through that is an additional paradigm to the holistic evaluation you can have. And the idea here is do a coding evaluation, do a writing evaluation, do humanity's last exam, and try to have as many paradigms as possible, and that's what I'm trying to build with E Slams, right?

So, we support about 50 games and 90 different like providers. We have chess and Go, which looks at planning and visible state. We have poker, which is decision-based on hidden information. And we have cooperation games based on shared goals and cooperation. And we also have trials for arcade games, right? And all of this tells you a lot about models and how they think.
</details>

在我们的平台上，eslams.com 上有关于如何使用该代码库的预览。这里有一个 Fable 5.1 与 GPT-6 Astra 对弈井字棋（tic-tac-toe）的例子。你可以观察 Fable 和 Astra 如何看待彼此的回合，以及它们如何进行对弈。有趣的是，这场比赛以平局告终。在大多数情况下会有模型获胜，但 Fable 和 Astra 最终势均力敌。

假设你要在生产环境中部署智能体，你希望与这些 AI 模型对战并观察其表现，你可以访问 eslams.com，在你想玩的任何不同游戏中与这些 AI 模型对战。你可以使用这个开源代码库完成所有这些操作，让它与你自己的智能体对战并评估你的系统。我们还将在二月份举办 AI 大满贯赛（Grand Slams of AI），其理念是举办一场 AI 模型的奥林匹克运动会，让它们展开竞争，看看谁能在其中脱颖而出。欢迎大家访问 eslams 了解我们的进展，这可以成为你加入评估技术栈的一种模型评估新范式。

<details>
<summary>Original English</summary>
And on our platform, we have preview on eslams.com of how you can use the repo. And this is an example of Fable 5.1 playing tic-tac-toe against GPT-6 Astra, right? And you can look at how Fable and Astra are looking at each other's turn, and how they go ahead and play this. And this match, interestingly, ends in a tie. And in most cases, a model wins, but Fable and Astra ended up knocking their heads to each other, right? And let's say you are deploying an agent in production. You can You want to go ahead and play against these AI models and see how they are. You can come on Islam.com and like play against these AI models on any different game that you want to. And you can all do all of this using the open source repo and make it play with your own agents and like evaluate your systems, right?

And we are going to host the Grand Slams of AI on in February and the idea is to put an Olympics of for AI models to go ahead and compete and know who will stand out of all of this, right? So, please do check out Islam to know where we're going with it and this could be one paradigm of model evaluation you can add into your stack.
</details>

### 原则四：关注回归用例并持续提高门槛

回到主题，在完成这一切之后，随着系统不断演进并添加新的范式，关键在于确保你持续对评估工作流进行测试。其中最重要的部分，就是**在流程中保留原先有效的功能**。

关于这一点，我最好的例子就是 Google Assistant 迁移到 Gemini。我以前常用 Google Assistant 来设置所有提醒。有一天它变成了 Gemini，然后它就不再为我提供提醒功能了，并且说它是一个无法设置提醒的语言模型。在他们之前的旧版 Google Assistant 模型中这项功能非常好用，但在迁移到 Gemini 后它就失效了。这就是谷歌在推出 Gemini 产品时没有对过去有效功能进行评估的典型案例。

因此，确保你持续测试回归用例、已知任务和过去的失败点极其重要。因为一个比旧模型优秀得多的新模型，完全有可能无法完成旧模型做得很好的事情，比如设置提醒。

时刻引入全新的挑战用例，这呼应了我之前所说的设定最具野心的目标。关键在于你必须不断鞭策你的模型。如果你发现你的模型在评估测试中达到了 85 或 90 分，就到了改进评估并推进前沿的时候了，要确保你的模型受到挑战，并且存在无法达到预期的用例。

<details>
<summary>Original English</summary>
So, now coming back, the main key part after all of this, right? Like you keep evolving, you keep adding paradigms, is to make sure that you keep testing the evaluation workflow, right? And the most important part of that is keeping what works in the flow. And my best example of this is Google Assistant moving to Gemini. I used to use Google Assistant for all of my reminders. And one day moved to Gemini and it stopped giving me reminders and it said it's a language model that cannot set up reminders, right? So, it was excellent in the old Google Assistant model they had and before they moved it to Gemini and it stopped working and this is an example of Google not doing eval on what used to work, right? When they went ahead and launched the Gemini product. And that's extremely important to go ahead and make sure that you keep testing like the regression cases, right? And known task and past failures because a model that is extremely better than the old one could very well be incapable of something that the old one did very well, for example, setting a reminder.

Right? And um fresh challenge cases at all points goes back to what I was saying in terms of setting the most ambitious target. The idea is that you have to keep pushing your model. If you feel that your model your is getting to an 85 or a 90 on your eval test, it's time that you better your eval and like push the frontier, right? And make sure that your model is challenged and has cases where it is not able to perform to expectations.
</details>

### 原则五：将真实世界的故障转化为评估测试

在任何时候，正如整个软件发展史所证明的那样，你必须**将现实世界中的失败转化为未来的测试**。你的客户和用户是你智能体和模型最重要的评估者。

因此，每一次失败都应该有一套完善的流程纳入你的系统中。其一是要保持观察，有多种方法可以做到这一点：可以通过多种可观测性工具自动获取数据，也可以让用户通过简单的点赞或点踩向你反馈，收集尽可能多的数据，让客户告诉你流水线中何处出现了问题。

按照经典的软件 QA 流程，复现该问题，并尝试理解模型究竟在何处失败——是工具调用？还是你的评估套件中哪个环节在执行时失效了？对其进行复盘，并添加到流水线和评估流程中。保持这一反馈闭环极其重要，这样你才能不断触及在各个时刻被遗漏的新前沿。

我认为获得尽可能全面的评估主要有两种途径：
1. **持续进行流程的人工审核**；
2. **确保将客户反馈纳入你的评估流水线**。因为这些正是模型或现有评估框架可能无法捕捉到的最后 5% 的边缘用例。

<details>
<summary>Original English</summary>
And at all points, right? And I think this has been true in software throughout history is that you have to turn real-world failures into future tests, right? Your customer and your user is the most important evaluator of your agent and your model.

So, every failure should have a proper workflow for it to enter into your system and make sure that like be that, right? So, one is to keep observing and there are multiple ways of making sure that you can observe. There are multiple observability tools that give you automatic data, give option for your users to report it to you with your simple thumbs up or a thumbs down, and collect as much data where your customers are telling you where there is a failure in the pipeline, right?

Classic QA on software, go ahead and reproduce that issue, and try to understand where is the model failing. Is it a tool call? Is it Is it And what part of your eval suit failed in going ahead and doing that, right? And review it, add it to the pipeline, and add that to the eval pipeline. This becomes extremely important to keep this feedback loop going so that you go ahead and access new frontiers of things that you are missing out in every point in time. And I think the two ways to go ahead and get to eval that is as holistic as possible is one to consistently human review a process, and then ensure that your customer feedback is part of your eval pipeline, right? Because these are the last 5% edge cases that really come out which a model or an existing eval framework might not catch.
</details>

### 总结：构建高风险评估的思维框架

总结来说，**测试任务本身，而不仅仅是测试答案**，这对整个流程来说至关重要。

最后我想梳理一下我们讨论过的所有内容：
1. **始终定义最具野心的成功**：设想通用人工智能（AGI）时代的场景，设想一个毫无缺陷、能够完全像你试图模拟的人类那样行动的模型，并在这一过程中进行定义。
2. **在工作流的各个环节持续测试工作流**：不要对工作流中的环节做主观假设，也不要假设输入和输出就是整个结果。在测试工作流时，要确保你的测试是专门针对该工作流组件的功能而设计的。例如，如果在工作流中某个特定环节需要持续进行工具调用来获取信息，那么你的评估就必须针对工具调用本身进行设计，而不是去测试其他不相关的流程。因为在那个环节，目标是了解你的工具调用能力和准确率。因此，每次测试工作流时，都要针对该特定部分设计测试，并衡量该环节的成功率。
3. **全面且持续地收集证据**：在智能体时代，什么是智能体行动评估的有效证据，本身就在不断演进。游戏是我正在探索的一个方向，但还有许多不同的前沿领域可供探索。比如我在此期间接触到的并行搜索模型索引，以及模型从并行 AI 搜索索引中抓取搜索结果的能力。当你设计一个需要实时数据的模型时，对其进行评估就变得非常关键。因此，作为构建此类产品的企业或个人，务必持续寻找更多证据、更多场景和更多范式来评估模型，这是确保覆盖绝大多数边缘用例的必由之路。
4. **随时间推移不断演进测试**：确保将过去和未来的所有维度都纳入测试中。最简单的一点是，如果你的测试得分很高，达到了 85、90 分，那就说明该修改测试并增加难度了。最简单的道理是，如果你发现所有人都在 SAT 考试中取得了前 99% 的百分位成绩，那么测试本身就必须做出改变。
5. **始终向现实学习**：现实将是你最好的老师。正如我开篇所提到的，评估的核心理念是确保我们在生产环境中兑现向消费者和用户做出的承诺，而这最为鲜明地体现在客户反馈和实际发生的真实情况中。因此，在起步与推进的过程中，要不断思考如何将真实用户反馈和现实世界测试结合起来，如何将人工审核与人工测试融入工作流。

我认为，借助这五种思维方式以及“测试任务本身而非仅测答案”的核心理念，你将拥有一套良好的思维框架，去为高风险应用构建评估体系。感谢大家的到来，稍后我很乐意与大家交流并解答问题。

<details>
<summary>Original English</summary>
So, to conclude, test the job and not just the answer, right? And that's extremely key to the whole process.

And I'll just wrap up with all the things that we've discussed is one is always define your most ambitious success. Think about what life would be in AGI, right? And think about life in a model that has no inabilities and can absolutely perform like the human that you're trying to sort of emulate and try to define in this process, right?

Second is continuously test the workflow at every part of the workflow. Don't assume things in the workflow or like assume for an input and output to be the outcome of anything, right? And when you test the workflow, I think something I slightly missed on here is to make sure that your your tests are designed for what that element of the workflow does. For example, let's say in that in your workflow there's a specific part that is doing tool calls consistently to get the information, your eval has to be designed for tool calling and not for any different process separately, right? Because the objective in that workflow process is to know what is your tool callability and the tool tool call accuracy, right? At that at that point. So, every time make sure that when you're testing the workflow, you design the test to that specific part of the workflow and measure what is the success in that element of the workflow as well.

And continuously gather evidence holistically. In an agentic world, what evidence for agentic action eval is something that keeps evolving. Uh and games is something I'm exploring to see how it works out, but there are so many different frontiers for you to go ahead and look at, right? Something super interesting that I came across while here I'm here is the parallel search model index, right? And how models are good at fetching search from parallels like AI search index. And that becomes very important for you to evaluate when you are designing a model that needs real-time data, right? So, make sure that you as a company or a person building these products is consistently looking for more evidence and more arenas and more paradigms for you to evaluate your models and that is one sure shot way to making sure that you cover most edge cases.

The fourth one is to evolve the test as time flow and making sure that you cover all aspects from the past and the future into the test and the simplest thing is if your test is scoring high is it 85 90 that is the time you change your test and you have to make it harder. Right? The simplest thing is if you think everyone is scoring like in the 99th percentile for the SATs, it is time that the test have to change in the internet of itself, right? And always learn from reality. Reality is going to be your best teacher and the idea of eval that I started off with is to make sure that we deliver the promise that we are making to the consumer and the user in production and that is most defined in the customer feedback and the reality that really happens, right? So, consistently think about how you can incorporate real user feedback and real world test and how you can have human review and human testing into the workflow as you go ahead and get started. I think with these five thought processes and the idea that you go ahead and test the job and not just the answer, you will have a good mental framework to go ahead and build eval for high stake applications. Thank you for coming. I'm happy to catch up for questions afterwards.
</details>