---
author: AI Engineer
date: '2026-07-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UlFB6efYN5Q
speaker: AI Engineer
tags:
  - ai-agents
  - typescript
  - python
  - application-layer
title: 类型与智能体之歌：为什么 TypeScript 正在赢得 AI 应用层之战
summary: 本文探讨了 AI 浪潮下 TypeScript 与 Python 在应用开发中的竞争。随着 AI 从模型训练的底层基础设施向“应用层”迁移，以“编码智能体”为代表的开发模式崛起，TypeScript 凭借其全栈语言一致性、丰富的 NPM 生态以及强类型契约（如 Zod），逐渐超越 Python 成为 AI 应用层开发的首选语言。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Ratel
  - GitHub
  - Anthropic
products_models:
  - Bun
  - ChatGPT
  - React
  - Zod
media_books: []
status: evergreen
---
### AI 开发的重心漂移：从底层模型走向应用层

大家好，感谢各位的光临。我是 **Roberto**，是 **Ratel**（**AI 智能体上下文层**（Context Layer: 为 AI 智能体提供上下文管理与数据整合的系统））的联合创始人兼 CTO，同时也是 **AI's Pratic**（一个全球 AI 开发者社区）的欧盟大使。今天，我将为大家带来一场关于“类型与智能体之歌”的分享。这是一场关于不同编程语言在 AI 领域争夺霸主地位的战争，而我个人认为，**TypeScript** 正在赢得这场战争。

回溯历史，几年前当人们在开发 AI 时，毫无疑问都会选择 **Python**，其他所有语言都向其复归与臣服。然而，自2022年 **ChatGPT** 发布以来，AI 开始冲破长久以来的学术和技术泡沫，变得更加雄心勃勃。伴随着这股浪潮，Python 的热度也水涨船高，并在2024年登顶成为 **GitHub** 上最受欢迎的编程语言。但就在大家以为 Python 的统治地位坚不可摧时，另一个强有力的竞争者——TypeScript——正在悄然崛起。

这种转变的本质在于，**AI 正在沿着技术栈向上移动**。AI 正在从机器学习、模型训练等**基础设施层**（Infrastructure Layer: 涉及模型训练、参数调优和硬件加速的底层系统）向**应用层**（Application Layer: 负责用户交互、业务逻辑和软件交付的上层系统）演进。这意味着 AI 不再只是需要反复训练的模型，而是成为需要集成并交付到实际应用中的功能。我们的应用程序开始拥有思考能力。然而，应用层从来就不是 Python 的天下，而是 TypeScript 的传统领地。尽管 Python 依然绝对掌控着 AI 的“大脑”——包括模型训练、学术研究和 GPU 服务端推理，但应用层的开发格局已经发生了根本性的改变。过去，在应用中嵌入 AI 必须使用 Python，而今天这已不再是唯一的选择。

<details>
<summary>Original English</summary>

Hello, and thank you for being here. I'm Roberto, and today I'm going to tell you this song of types and agents. Uh basically a song that speaks about languages that fight each other to conquer what's the throne in the AI realm. And how I think that TypeScript might actually be winning this war. But let's start from the beginning. A few years ago, whenever someone was building in AI, they were certainly using Python. Like there was no doubt. All the other languages were bowing to Python because of its dominion over the AI world. And then, when in 2022 ChatGPT was released, everybody started wondering and starting understanding that AI was becoming something more. Was going outside of the bubble that lived for years. And started to becoming something more ambitious. And together with it, Python, which was the standard language for AI, became more ambitious as well. And that's how in 2024 GitHub actually claimed the ladder and became the most popular language on GitHub. So, you know, everybody was happy. Python finally reached the top. But little did they know that there was another contender for the throne. Another contender that was rising to challenge the claim that Python had on the throne. And this contender, as you may have guessed by now, was indeed TypeScript. But, before talking about this, let me present myself. My name is Roberto. I'm the CTO and co-founder of Reto, a context layer for AI agents. And I'm also the EU ambassador for AI's Pratic, a global community of AI builders meeting once per month to discuss the latest news in AI. I'm also a long-time JavaScript then turned TypeScript developer. And that's basically why I am talking about TypeScript today. So, let's begin. As we said, AI started moving up to the stack. It was moving from the infrastructure layer of these models, machine learning, and all related ecosystem towards the application layer. This means that AI stopped being something that you train, and it started being something that you ship inside your application. Applications started featuring AI, starting having features powered by AI. Which basically means that we started having applications that think. And the application layer was not Python's. The application layer has been TypeScript's for pretty long time now. Don't get me wrong, like I still think that Python has its own application. Like I still think that the brain of the agent and all the AI world is actually still owned by Python. All the training, the research, the GPU serving is all Python's. Uh Has been Python's all along and it's going to be Python's for long time yet. And what's changing is actually the application layer. Like few years ago, if you wanted to build something with AI built in the application, you had to use Python. But today, that's not the case anymore. And that's all the shift is about.

</details>

### 编码智能体的崛起与 TypeScript 的 GitHub 登顶

在确立了应用层的优势之后，TypeScript 的疆域开始向更深处延伸。**TypeScript** 不仅统治了前端 UI 和后端开发，更开始接管我们应用程序中的**智能体层**（Agentic Layer: 负责决策、规划以及工具调用的 AI 代理执行逻辑）。正是得益于这一趋势，在2025年8月，TypeScript 正式超越 Python，加冕为 GitHub 上最受欢迎的编程语言。有趣的是，GitHub 连续两年在其报告中给出了相同的归因：2024年报告指出是“AI 将 Python 推向巅峰”；而在2025年，报告则写道是“AI 将 TypeScript 推向了第一的位置”。

在这一年里，全球开发者数量呈现爆发式增长，2025年甚至达到了平均每秒就有一位新开发者加入 GitHub 的惊人速度。那么，在开发者基数如此庞大的背景下，究竟是什么促成了这一选择的转变？在2024年，无论是新手还是老手，大家都倾向于使用 Python；而到了2025年，人们却纷纷倒向了 TypeScript。这背后的核心催化剂就是**编码智能体**（Coding Agents: 能够自主编写、修改和调试代码的 AI 助手）的成熟。

以 **Lava Cloud Code**、**Cursor** 和 **Codex** 为代表的编码智能体已经成为我们构建软件的默认方式。而这些编码智能体在生成应用代码时，其默认且最擅长输出的语言正是 TypeScript。当今的绝大多数新应用本质上都具备某种智能体属性，因为它们需要集成 AI 和自主规划能力。这种在应用内部嵌入多重 AI 接口的爆发式需求，自然而然地落在了 TypeScript 的肩上，而非 Python。甚至连主流的 AI 构建工具链也早已向 TypeScript 靠拢，最典型的风向标事件莫过于去年12月，知名 AI 实验室 **Anthropic** 收购了高性能 JavaScript 运行时 **Bun**。

<details>
<summary>Original English</summary>

TypeScript doesn't just own, you know, the UI or the back end. Started owning also the agentic layer of our application. And that's why in August 2025, TypeScript actually passed Python as the most used language on GitHub. And the funny thing is that the reason that the GitHub reports gave was the same. Like in 2024, it said AI leads Python to the top language. While in 2025, it said AI leads TypeScript as the first language. And in both cases, as you can see, the global developers, the number of global developers were surging. In 2025, we even have one new developer joining GitHub every second. So, what actually changed in this year? Like yeah, we were flooded from like new developers. In 2024, these newcomers were reaching for Python, or even maybe existing developers were reaching for Python. And in 2025, they reached for TypeScript instead. What changed between 2024 and 2025 was actually coding agents. The coding agents grew up like we saw established um we saw the players establishing themselves like Lava Cloud Code, Cursor, Codex. They became the default way to build applications. And the default way to which these coding agents actually built the applications was TypeScript. And you know since every new app pretty much every new app is an agent today because they ship these AI and agentic capabilities, they are hungry to embed AI inside themselves. The demand to have more AI integrations, more and more AI integrations doesn't fall on through Python. It falls on TypeScript. And pretty much all the tools that we use to build AI today already run on TypeScript. We even saw an AI lab acquiring a JavaScript runtime like last December Anthropic acquired Bun.

</details>

### 全栈一致性与 NPM 生态的合力优势

面对 TypeScript 席卷 AI 开发的现实，我们应当思考：在实际项目中，将 AI 智能体完全构建在 TypeScript 之上是否是明智的选择？答案是肯定的，这主要归结于以下五个核心技术优势：

首先是**智能体循环反馈优化**。因为 TypeScript 是当前编码智能体最主要的生成目标，随着越来越多的 TypeScript 代码库被建立，下一代 AI 编码模型在训练时将拥有更丰富的语料，从而产生质量更高的 TypeScript 代码输出。这种良性循环使得在 TypeScript 中构建智能体的效率持续提升。

其次是**无缝接入庞大的生态系统**。当 AI 功能走向应用层时，它必须与身份验证、支付流、复杂的 UI 交互及基础设施进行深度对接。而托管在 **NPM** 上的包管理器拥有目前世界上最成熟、最庞大的软件生态，能够极大简化这些非 AI 业务逻辑的集成工作。

第三，**全栈单一语言的极简架构**。如果选择 TypeScript，你可以在同一个项目中编写智能体循环、外部工具、后端微服务以及前端 UI，维持单一代码库的整洁。相反，如果使用 Python，你必须将系统分割为至少两个服务（例如使用 **FastAPI** 和 **Pydantic AI** 搭建后端，再搭配一个独立的 **React** 前端），这会无形中增加跨服务通信和部署的复杂度。

第四，**端到端一致的类型契约**。跨服务边界的类型同步往往是开发中的痛点。在全栈 TypeScript 架构下，开发者可以利用 **Zod**（**模式验证库**（Schema Validation Library: 用于在运行时对数据进行强类型验证的工具））定义一次数据 Schema，即可在 AI 模型输入输出、后端接口和前端界面中共享该类型。

最后，**蓬勃发展的 TypeScript AI 生态**。以 **Vercel AI SDK**（Vercel AI SDK: Vercel 开发的用于构建 AI 应用程序和流式交互界面的 TypeScript 软件开发包）为例，其周下载量在短短一年内从 160 万骤增至 1510 万，实现了近 10 倍的爆发式增长。这充分证明了社区对 TypeScript 在 AI 应用开发中的信心。

<details>
<summary>Original English</summary>

But still, you know, okay, everybody use is using TypeScript because of the coding agents and we are having more and more demand to build uh AI to embed AI inside TypeScript application. But does this mean that we should do it? Like this is a fair question, like it's an honest question and it's a question worth answering. And the answer in my opinion can be yes like for several reasons. The first one is that since TypeScript is the default language for coding agents today, we can expect that they will become better and better in in TypeScript because we are having more and more application in TypeScript, which are going to field the training of next coding agents. And then we are having deeper integrations and more native integrations from these coding agents towards TypeScript, and we can expect that the quality of the output in TypeScript is going to be better and better from these coding agents. Since we're building applications, and uh we want to have like the highest quality of these applications, might make sense to build agents, which are the new kind of applications in TypeScript. And also, if you use TypeScript, you are actually tapping into what is probably the richest package manager out there. NPM comes with everything, uh pretty much everything, like authentication, payments, UI, infra. Like it's uh the deepest up layer tail that there is. So, since again, AI is coming towards the application layer, we need to integrate with all these right now. And tapping inside NPM is a very convenient way to do that. Also, you have by building in TypeScript, you can have one single language throughout all your code base. You can have one single code base for the whole application. Because you can use TypeScript for your agent loop, for the tools, for the back end service, for the UI. While if you use Python, you probably have to split uh split it at least into two services. Which means, you know, one service with FastAPI, Pydantic AI, and whatever. And then another separate React application that you need to sync between between these two with a uh with a contract, which you have to maintain and synchronize. And speaking of contracts, with TypeScript, you can have one single consistent typing across all your all your application. While if you use Python instead, you at some point will stop at a boundary, cuz you will have your agent, maybe your back end, etc. with one consistent typing, and then you will have your React application or Vue or whatever with um another set of typing at which you need to synchronize between the two. So, if you use TypeScript, you can use Zod as a single schema throughout all your application, which is very convenient. You can define a type once. You can use this type in the back end and uh in the model, and you can use the same type in your UI. One type, checked and went. Also, like it makes sense to build in TypeScript today uh also in the AI ecosystem because we are seeing a very surge in in the AI ecosystem as well. Like take the Versatile AI SDK, for example, you can see that in just 1 year, it went from 1.6 million to 15.1 million downloads per week, which is between 9 and 10x in just 1 year.

</details>

### 雅特伍德定律的新推论：智能体将全面转向 NPM

总结而言，将 AI 智能体构建在 TypeScript 之上，不仅可以最大化地发挥编码智能体的自动生成效率，还能通过全栈单一语言、统一的 Zod 类型契约以及 NPM 庞大的基础设施生态来降低开发维护成本。

事实上，这种发展趋势并非不可预测。早在近二十年前，Jeff Atwood 就提出了著名的**雅特伍德定律**（Atwood's Law: 任何可以用 JavaScript 编写的应用，最终都将用 JavaScript 编写）。在今天，这个定律延伸出了一个新的推论：**任何能用 JavaScript 编写的应用程序，最终都将用 TypeScript 编写**。在这个全新的智能体时代，这一法则依然适用：负责大模型核心训练和底层 GPU 推理的引擎仍然会使用 Python 并通过 pip 分发；但作为应用层核心、负责调度模型和执行复杂任务的智能体，将无可避免地向 NPM 和 TypeScript 转移。

这仅仅是一个开始。随着时间的推移，TypeScript 与 Python 在应用层开发上的差距只会进一步拉大。因此，我最后的建议是：你可以继续在 Python 中进行模型训练，因为这在短期内不会消失；但在开发智能体和集成应用时，请务必考虑使用 TypeScript。如果你依然选择忽略它，那么在接下来的智能应用时代，你将很有可能被时代抛在身后。

<details>
<summary>Original English</summary>

So, finally, I'd to put everything together. In my opinion, yes, it makes sense to build AI agents in TypeScript because you have like a uh you can leverage the the de facto default language for coding agent. You can have one single language for your whole application and your whole code base. You can tap into uh fast-growing AI ecosystem. You can have consistent typing uh across all your application. And you can tap into the richest package manager that there is, NPM. So, um you might ask was all this unpredictable? And the answer is actually no. Someone predicted this uh many years ago, almost 20 years ago. Jeff Atwood said, "Any application that can be written in JavaScript will eventually be written in JavaScript." And you know, as you as you probably know in the last few years, we have a corollary of this that any application that could be written in JavaScript will eventually be written in TypeScript. And so basically, we can say that any application, even the gigantic ones, will be written in TypeScript. And be mindful that what I showed you today is just the beginning. Like, we are just getting started. You can project this in a few years and you can see that on the application layer, the difference between TypeScript and Python is actually going to widen from here. So, um as I said, the model can still run on pip. But the agents, which is the application layer today, so the agent that called the models will probably ship on NPM. So, everything on the inference layer, you know, it's going to be Python. But everything else, probably all TypeScript. Let me leave you with one recommendation then. Um keep training in Python. As I said, I don't see that's one going away soon. But please consider building the agents and the applications in TypeScript. Because if you don't do that now, if you overlook TypeScript, you are probably going to fall behind. That was all on my side today. I thank you all for your listening. And please scan the QR code for the slides. Reach out to me if you agree or if you disagree, if you have any feedback, and let's get in touch. Thank you. Bye-bye.

</details>