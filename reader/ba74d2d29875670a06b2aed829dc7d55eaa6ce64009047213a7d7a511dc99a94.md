---
author: AI Engineer
date: '2026-09-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=buHC7bQE1X4
speaker: AI Engineer
tags:
  - agentic-workflow
  - software-engineering
  - multi-agent-systems
  - developer-tools
title: 不要挡模型的路：Google DeepMind 的 Antigravity 与智能协同扩展
summary: Google DeepMind 的 Kevin Hou 在 AI Engineer 峰会上分享了 Antigravity 2.0 的设计理念与未来演进路线。他提出核心准则「跟随智能扩展」，阐释了从自动化补全、单一智能体到多智能体团队（Agent Teams）的范式演变，深入剖析了动态子智能体、Sidecar 插件机制与生成式 UI 三大新原语，并展示了团队用 93 个子智能体在 12 小时内以不到 100 美元成本从零构建 OS 内核并运行 DOOM 的突破性实践。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Kevin Hou
companies_orgs:
  - Google DeepMind
products_models:
  - Antigravity
  - Gemini 1.5 Flash
media_books: []
status: evergreen
---
### 开场与核心隐喻：让你的明星球员放手去打

**主持人**: 好的，有请。

<details>
<summary>Original English</summary>

**[Speaker 0]**: Thank you.

</details>

**Kevin Hou**: 大家好。我是 **Kevin**，今天我将为大家分享关于 **Antigravity** 的内容。

在场的各位有世界杯球迷吗？想象一下，你是阿根廷国家队的主教练，比赛已经进入到了第 89 分钟，而你的球队阵容里拥有**梅西（Lionel Messi）**。这时候，你会布置什么战术？

这个战术的名字就叫做：“把球交给梅西，然后所有人都给我闪开！”

大语言模型（**LLM**）如今已经不再只是球队里的普通轮换角色了。如果你能围绕它们构建出合适的产品架构，它们完全能够成为你团队中的超级明星。而为了让这位超级明星球员能够尽情发挥、大展身手，你所要做的就是：**不要挡模型的路（Get out of the model's way）**。

我先确认一下幻灯片有没有切过来……哦，已经切好了，太棒了。

<details>
<summary>Original English</summary>

**[Speaker 1]**: Hello everyone. Um, my name is Kevin. I'm going to be talking about Antigravity. So are there any World Cup fans out there who imagine you are coaching Argentina and you're in the 89th minute, and you have Messi on your team. What play are you running? It's called: give Messi the ball and get the heck out of the way. LLMs aren't just role players anymore. They can be your star player, if you build the right product around them. And to let your star player cook,

**[Speaker 0]**: You have to get out of the model's way. Might want...

**[Speaker 1]**: Want to get the slides up. Oh, they are great.

</details>

### Antigravity 的演进与解耦架构

**Kevin Hou**: **Antigravity** 是 **Google** 专为技术人员与非技术用户打造的 **Agentic Coding（智能体编程）**产品。我们在 2025 年 11 月正式对外发布，自发布以来，无论是在 Google 内部还是在外部开发者社区中，它的采用率都在以惊人的速度持续攀升。我叫 **Kevin Hou**，负责领导 Antigravity 的部分工程团队。

现在让我们深入探讨一下 Antigravity 究竟是什么。从诞生之日起，我们就毫不掩饰、始终坚定地奉行**智能体优先（Agent First）**的原则。

去年，我们在首次推出 **Antigravity IDE** 时，引入了一个全新的 **Agent Manager（智能体管理器）**概念。它本质上是一个统一的平台，专门用于管理与编排多个协同工作的智能体。从那时起，我们进一步将底层智能体核心能力解耦抽离出来，发布了独立的 **Antigravity CLI** 工具。

在上个月举行的 **Google I/O** 大会上，我们非常荣幸地正式发布了 **Antigravity 2.0**。为了践行“不要挡模型的路”这一核心设计理念，我们做出了一个非常重大的架构重构：彻底将 IDE 与 Agent Manager **进行解耦**。

现在，你拥有了两个完全独立的应用程序。你可以将 Agent Manager 作为一个独立的应用程序来运行和使用。常言道，一图胜千言，这里展示的就是 Antigravity 2.0 实际运行过程中的应用截图。

大家可以看到，它不仅仅是你管理所有智能体与开发项目的专属**任务控制中心（Mission Control）**，它还完整集成了 **Subagents（子智能体）**系统、支持所有前沿模型、具备 **Worktrees（工作树隔离）**支持、**定时任务调度（Scheduled Tasks）**以及**语音交互模式（Voice Mode）**。

这个产品中有太多令人兴奋的特性可以展开拆解，但我今天并不打算把时间全部花在产品功能的罗列介绍上。我真正想要和大家分享的，是那些隐藏在幕后的核心思考、贯穿整个系统研发的设计原则，以及尤为关键的——究竟是哪些认知驱动了我们产品路线图的演进。

<details>
<summary>Original English</summary>

**[Speaker 1]**: Um, so Antigravity is Google's agentic coding product for technical and non-technical users. We launched back in November of 2025 and have been accelerating adoption both within Google and externally ever since. My name is Kevin Hou and I lead part of the engineering team on Antigravity. So let's talk a bit about what Antigravity is. We have and always will be unapologetically agent first. So we debuted the Antigravity IDE last year with a brand-new Agent Manager concept, and it was a platform to manage and orchestrate many agents. Since then, we've actually extracted our agent and launched our own Antigravity CLI. And last month at Google I/O, we had the pleasure of launching Antigravity 2.0. In the theme of getting the model out of the way, we actually decoupled the IDE from Agent Managers. So now you have two separate applications, and now you can use the Agent Manager in a standalone app. Since pictures are worth a thousand words, here's a screenshot of Antigravity 2.0 in action. As you can see, not only is that your own dedicated mission control for your agents and projects, you have subagents. You have all the new models, you have worktrees, scheduled tasks, voice mode. There are so many things to unpack with the product, but I don't want to spend today telling you about the product. I want to tell you a little bit more about the behind the scenes, some of the principles that went into it, and notably some of the things that led to its roadmap.

</details>

### 核心法则：跟随智能扩展（Scaling with Intelligence）

**Kevin Hou**: 对于在场一直关注 AI Engineer 社区的老朋友们来说，这其实已经是我第五次登上 AI Engineer 的讲台发表演讲了。我从 2022 年起就开始深耕开发者工具这一领域。在过去经历的所有探索与复盘中，有一条经验教训始终凌驾于其他所有认知之上，那就是：**跟随智能扩展（Scaling with Intelligence）**。

这句话的核心含义是：当底层模型变得越来越聪明、能力越来越强大时，你的上层产品形态必须随之同步进化。你所接入的任何前沿模型的最尖端能力边界，都应该在你的终端用户体验中直接、清晰地体现出来。

接下来，让我们通过具体的演变历程，来看看这句话究竟意味着什么。

如果大家在 X（原 Twitter）上关注过我，或者听过我过去四年里的各种公开碎碎念，你就会知道我一直在经历并推动这一系列年复一年的产品范式转型：

在 **2022 年**，我当时主要在做代码自动补全（Autocomplete）和聊天侧边栏（Chat Sidebar）。那时的技术完全是建立在 Embedding 规则文件、静态语法树解析（AST / Syntax Tree Parsing）等技术基础之上的。基本上，那个应用内部的所有逻辑都是**确定性的（Deterministic）**，因为在当时，那已经是底层模型能力所能够承受和处理的极限了。

到了 **2024 年**，当智能体（Agents）正式登上历史舞台时，它彻底颠覆了开发者完成工作的方式。随之诞生的是一整套崭新的系统原语，比如 **MCP（Model Context Protocol）**、**自定义工具（Custom Tools）**以及精细化的**权限控制系统（Permission Systems）**。

紧接着步入 **2025 年**，我们推出了 Antigravity 的 Agent Manager，业界随后也纷纷跟进并推出了类似形态的产品。用户的工作模式演变为在同一个界面中同时并行管理多个智能体。这一时期催生了 **Skills（技能包）**、**Hooks（事件钩子）**、**Artifacts（交付物产物）**等核心原语，正是这些构件共同定义了 2025 时代的技术特征。

那么，让我们把目光投向 **2026 年**：定义这个新时代的核心原语又将会是什么？

在回答这个问题之前，我想先带大家回顾几段与我们切身相关的、刻骨铭心的实战教训。因为“跟随智能扩展”这六个字，说起来轻巧，做起来却极其艰难。要亲手从用户手中夺走他们早已深爱且无比熟悉的旧交互模式，并引导他们走向一条潜在更优的道路，是一件阻力极大的事情。

请注意，“潜在”是一个非常关键的前提词。因为我们自己也不可能做到百分之百全知全能、次次正确。但在我准备今天这场演讲的幻灯片时，脑海中立刻浮现出了两个最典型的交锋案例。

<details>
<summary>Original English</summary>

**[Speaker 1]**: So as some of you for the long time AI Eng fans, this is actually my fifth time speaking at AI Eng. Um, and I've been building developer tools since 2022. And the one thing that has stood above all other lessons that I talk about is the idea of scaling with intelligence. This means as the model gets better, so should your product, and the frontier edge of whatever model you are serving should be apparent inside of your user's product experience. So let's get into more concrete examples of what this means. So for those of you that follow me on X or hear me just yap generally for the last four years, you'll know that I've been working on a number of these sort of transformations year over year over year. In 2022, I was working on autocomplete and chat sidebars. This was based on embedding rules files, syntax tree parsing, basically everything inside of that app is deterministic because that's all that the model could really handle. And in 2024, when agents came onto the scene, it completely changed how developers were going to do work. With it came new primitives like MCP, custom tools, and permission systems. And with 2025, we introduced Antigravity's Agent Manager with many other products following suit in that similar form factor with users managing many agents at once in parallel. And this led to things like skills, hooks, artifacts, and a couple other primitives. And that sort of defined the 2025 era. So let's talk a little bit about 2026 and what those primitives might be. Before we answer this question, I want to take you back to some of these battle scars that are a little bit closer to home. Scaling with intelligence really is not easy. It's really hard to take away something that users love and are familiar with to lead them down potentially—and that's a big keyword—a better path. We aren't right 100% of the time. But there are two that jumped to mind when I was putting together the slides for the talk.

</details>

### 实战交锋与认知突破：终端权限与侧边栏之争

**Kevin Hou**: 第一个案例，是**赋予 AI 终端操作权限（Giving AI a terminal）**。大家肯定都还记得早期的那种恐慌氛围，所有人都在极度担忧：AI 智能体会不会突然发疯，毫无征兆地删掉你整个代码库，对你的初创项目或公司系统造成不可挽回的灾难性破坏？

但随着底层模型推理能力的飞跃，以及工程团队在权限控制系统等关键原语上的持续深耕与投入，最终的结果是：用户不仅写代码的速度大幅加快，交付部署软件的频率显著提高，而且整个过程在安全防护机制的保障下进行得非常稳健，大家最终成功克服了这份恐惧。模型本身变得更加聪明，它们已经有能力在终端环境中自主做出更精准、更理性的安全判断，清楚地知道哪些命令应当执行，而哪些高危命令绝对不能碰。

第二个案例，就是屏幕上展示的这条推文。它非常传神地再现了我们当年从 **Windsurf** 中毅然移除传统聊天功能时，我所遭遇的铺天盖地的用户质疑与声讨。

当时，大批老用户对我们的团队愤怒质问，因为我们直接剥夺了他们极为依赖的核心入口——那个常驻界面的聊天侧边栏，并且彻底将其替换成了纯粹的智能体交互界面。在当时那个时间节点上，让用户告别习惯已久的舒适区，确实是一颗难以下咽的苦药。

然而，当我们今天站在当下的时间节点回望过去，事实证明了一切：大模型的能力实现了跃升，多步骤深度研究、智能体自主拆解与执行变成了全新的行业主导范式。今天在座的各位，正是这些前沿智能体产品最狂热的拥趸与受益者。

现在，我把大家带到我们今天正在面临的核心战役面前：当下正在发生着什么？

正如刚才提到的，我们把 Agent Manager 彻底从传统的 IDE 容器中解耦了出来。在 Antigravity 2.0 中，它们被拆分成了两个彼此独立、各司其职的独立应用。

在我们看来，**IDE 之于 Agent Manager，就如同当年的调试器（Debugger）之于 IDE**。你在绝大多数日常开发流程中并不需要时刻开着调试器；但只要你需要下潜到底层抽象栈中去进行深层次的排查与介入，有一个随时待命的调试器在手边就显得弥足珍贵。

我们的前瞻性判断是：这种全新的**智能体协同编排（Agent Orchestration）**模式——你可以将其称为**智能体团队（Agent Teams）**，也可以称作集群协同（Swarms），或者**软件自动化工厂（Software Factories）**——它必将代表软件工程的未来走向，而我们正全力以赴押注这一未来。

<details>
<summary>Original English</summary>

**[Speaker 1]**: The first one is giving AI a terminal. We all remember fears about sudden deletion of your entire codebase and doing catastrophic things to, you know, your startup, your company, etc. But as models got better and people invested in primitives such as permission systems, users ended up building faster, ended up shipping more, and they did so safely to overcome this. And as models got smarter, they're able to make better decisions about what they should and should not run in your terminal. The second instance is this tweet, which is very representative of sort of the yelling that I got when we removed chat from Windsurf. So a lot of users were yelling at our team because we took away something that was very dear to them, the chat sidebar, and replaced it with only an agent. Now at the time, this is something that was familiar and rather difficult to swallow. But when we look back, models have advanced, multi-step research, agentic research and execution became the new paradigm. And here we are today using and loving all these agentic products. And so now I bring you to today's battle. What is going on today? So we decoupled the Agent Manager from the IDE. And with Antigravity 2.0, we split them into separate applications. We believe that the IDE is to the Agent Manager what the debugger was to the IDE. You don't always need a debugger, but it definitely is helpful to have it if you need to go a layer beneath and go one step deeper into that abstraction stack. And our prediction is that this idea of agent orchestration—you can call it agent teams, you can call it swarms, you can call it software factories—is the future, and we're willing to bet on that future.

</details>

### 2026 智能体团队的核心原语

**Kevin Hou**: 接下来，我想正式揭晓我们所定义的 **2026 智能体团队时代（Agent Teams 2026 Era）**的核心构建原语。它们主要包含：**Subagents（动态子智能体）**、**Generative UI（即时生成式界面）**以及 **Sidecars（伴生进程插件系统）**。稍后我会具体剖析这些原语到底是如何构建的，并结合具体的实际案例展示它们在产品中是如何具象化呈现的。

但在深入技术细节之前，更重要的一点是首先想清楚背后的“为什么”：究竟是什么驱动了这些技术形态的剧变？模型底层究竟发生了哪些本质特性的突破，才孕育出了这些全新的系统级组件？

作为一个产品研发团队，面对新一代原语，你究竟应该去强推自己的产品设想，还是应该在每天深度使用、沉浸体验模型的过程中，让这些原语自然浮现？

答案其实是：二者兼而有之。

而身处 **Google DeepMind** 的巨大独特优势在于：我们的产品工程团队与底层模型研发团队之间，保持着极高频、极紧密的协同反哺闭环。大家还记得在 Antigravity 1.0 时代的核心精髓吗？那就是在并行调度管理多智能体的同时，始终确保人类处于核心驾驶位（Human in the driver seat）。在我的上一场技术演讲中，我重点阐述了这个飞轮模型背后的“搜索与产品协同飞轮”。

而正如我们当时向大家承诺的那样，得益于 Antigravity 真实业务场景与工程闭环的反哺，**Gemini** 模型如今已经在如何自主驾驭和协调一个多智能体团队方面，积累了深厚的技术直觉与系统能力。

当然，在构建更完备的多智能体协同、更高级的协作流以及更优异的任务递归分解能力上，未来依然存在巨大的探索天花板。但依靠 Gemini，我们已经牢牢确立了领先身位。我们把这些基础协同范式深度灌注进了基础模型本身，从而为孕育出 Antigravity 2.0 这样的划时代产品打下了坚实的地基。

我们在今年 4 月正式对外发布了 **Gemini 1.5 Flash**。这款模型把我们在后台与 Antigravity 长期打磨的大量核心能力直接带向了全球市场。现在的 Flash 不仅擅长端到端的单点任务执行，更令人惊艳的是，它展现出了极其卓越的团队领袖与协同调度能力。它以更快、更低廉的推演成本，直接把**智能水平、执行速度与部署成本**这三者之间的帕累托最优边界（Pareto Curve）推到了前所未有的全新高度。

将所有这些软硬件与模型能力整合在一起，我们无比激动地宣布：**Agent Teams（智能体团队模式）**正式在 Antigravity 中开启公开预览体验！

现在，你只需要在输入框中简单敲下一个快捷斜杠指令：`/teamwork`，你就能瞬间进入一个全新的工程工作模式，就此释放出成群结队的智能体集群，全力攻克眼前的复杂任务。

<details>
<summary>Original English</summary>

**[Speaker 1]**: So here are the primitives for what we're calling the Agent Teams 2026 era. These are things like subagents, Generative UI, and sidecars. And we'll talk more completely about what those things are and some examples of how they manifest inside of the product. But it's really important to first understand the why. What brought about these changes, and what model changes, what model properties actually led to the development of these new things? And as a product team, do you force the new era of primitives, or is it something that comes to you by using the model and experiencing the model? The answer is kind of both, right? And the privilege of being inside Google DeepMind is that we do have that relationship between the product and the model. So you remember the crux of Antigravity 1.0 is to manage agents in parallel to put the human in the driver seat. And if you remember my last talk, I talked a lot more about this search product flywheel. And now, as promised, because of the Antigravity product, Gemini has now learned a thing or two about how to manage a team of agents. There's still a lot of headroom to make multi-agent systems better, more collaborative, better at deconstructing tasks into smaller tasks. But we've got a really good head start with Gemini. And all the basics have been imbued into the model so that we could build a product like Antigravity 2.0. Gemini 1.5 Flash was launched back in April. And this brought to market a lot of those capabilities that we have been working on in the background with Antigravity. And Flash now isn't just good at executing tasks; it's actually really good at leading teams. It's faster and cheaper, pushing the Pareto curve of what is intelligent versus the speed and the cost at which you run those things. And putting this all together, we were really excited to announce Agent Teams in public preview inside of Antigravity. All you have to do is simply type the slash command `/teamwork`, and you'll see a new mode where you can enter and unleash swarms of agents onto the task at hand.

</details>

### 运作机制与实战标杆：从照片编辑器到自研 OS 内核运行 DOOM

**Kevin Hou**: 接下来，我向大家拆解一下它底层的具体运转流程。

作为用户，你首先需要提出你的任务需求。你的初始描述越详尽、越具体越好。但不必担心遗漏，因为这套全新的智能体通信机制自带反向沟通能力：如果它发现执行条件还不充分，它会在规划阶段主动向你发起澄清追问，直到所有前置条件和任务边界都被彻底厘清。

接着，你将与一位**主导智能体（Lead Agent）**展开直接协作，而由它在后台自主调度并管理一支规模任意伸缩的智能体团队去拆解并执行工作。我经常把这个工作场面比喻成现实版的**复仇者联盟（The Avengers）**：主智能体会动态实例化一系列具有高度专业分工的角色，比如前端工程师、后端工程师、基础设施专员、QA 测试专家、UI 设计师等等。这个名单可以根据实际需求无限延展，每一个子智能体都有无限的可能性去承接专门的职能。

每一个子智能体都是根据上下文**动态生成**并完全独立执行任务的。更绝妙的是，子智能体甚至可以根据任务特性，自主选用与主智能体截然不同的底层模型。这种按需智能路由，完全是由主智能体自主决策的。这再次印证了我们的核心信条：跟随智能扩展。

这里面最炫酷的特性之一，就是它对 **Generative UI（生成式界面）**的深度整合。配合速度快如闪电的 Gemini Flash 模型，整个界面的交互反馈几乎是瞬时生成的。

举个例子，如果你向它询问：“嘿，我的任务当前推进到什么状态了？给我看一眼看板试图。”或者你更习惯 Chrome 开发者工具风格的展示方式，希望能看到调用瀑布流或时序线（Timeline），它都能基于运行时上下文，当场为你动态生成原生交互界面呈现给你。因为系统完全具备了按需即时生成 UI 的底层支持。

现在我们来看看这个系统在实际测试中都独立完成了哪些真实工程项目：

我们让它从零构建过一个完整的**照片编辑器（Photo Editor）**，用户可以直接在浏览器端原生编辑 RAW 原始格式图片；我们还让它构建过一个功能完备的即时通讯应用，在座的不少人看到它的界面应该会觉得非常眼熟。在这些项目中，每次运行都需要消耗上百个动态子智能体，并且往往要持续全自动编码运算近半天的时间。

但为了真正逼出这套系统的极限潜能，我们团队完成了一次极具挑战性的标杆任务（Hero Run）：**完全从零构建一个完整的操作系统内核（OS Kernel）**！

这是我们在今年 Google I/O 大会上公开演示的高光成果：我们的智能体团队从零写出了完整的 OS 内核，并且**在这个自研内核上成功运行了《DOOM》（毁灭战士）游戏**！当时我的同事在现场为大家呈现了实机 Demo。

我们团队对这个里程碑式的突破感到无比自豪。不仅在于它极具震撼力，更在于它无可辩驳地证明了：只要你在正确的工程架构下，将更强的模型智能与多子智能体并行范式相结合，类似 Gemini 1.5 Flash 这样的模型不仅能以极其强大、高效的方式攻克前所未有的工程难题，而且它的**运行成本是完全可控、人人用得起的**！

我们显然不可能在日常业务中为了构建一个内核动辄消耗数千上万美元，但这项实战向所有人证明了工业级落地的可行性。

让我来给大家分享一下这次极限挑战跑出来的硬核数据：
* 全程共动态派生并调度了 **93 个子智能体（Subagents）**
* 历时连续运行 **12 个小时**
* 向底层模型发起了超过 **15,000 次 API 请求**
* 累计消耗了 **20 亿 Tokens（2 Billion Tokens）**
* 而最终产生的总 API 费用——**低于 100 美元**！

这正是这个项目最令人震撼、最具产业落地价值的关键所在。从这个标杆实战中大家可以清晰地看到：动态子智能体原语，构成了我们迈向 2026 智能体团队时代不可或缺的核心基石。

<details>
<summary>Original English</summary>

**[Speaker 1]**: So we'll talk a little bit about how this works. You as a user will specify your task. The more specific you are the better, though the nature of these agent communication styles is that if it needs something more, it can actually ask you for more until everything is basically clear. You'll work with that lead agent, and it will manage a team of arbitrary size to get that work done. And what I like to say, it's kind of like The Avengers, right? It'll take a bunch of specialized roles: it may take frontend engineers, backend engineers, infrastructure specialists, QA, design—the list goes on and on and on, and there are infinite possibilities for what each of those subagents could take on. Each subagent is dynamically generated and can operate independently, and it can even actually select a different model from what the main agent is using. And this is done so by that main agent. Again, we are scaling with intelligence. And one of the coolest aspects of this is that it can use Generative UI with a model that is as fast as Flash. Things can happen nearly instantaneously. If you ask, "Hey, what is the status of my task? Show me a Kanban of what's going on," or maybe you know you prefer something a little bit more like the Chrome debugger tool, it can show you a timeline. And all these things are generated on the fly because it's able to generate UI on demand. So some of the projects that the system has implemented: um, we've built a photo editor that can actually edit RAW photos directly inside of your browser. Um, we've also built a messaging app that might look a little bit familiar to those in the room. And each of these took hundreds of subagents and took almost half a day to run. But to really put it through its paces, one of the hero runs that we did was actually building an entire OS kernel. This is something that we've got to show off at Google I/O. But we built a complete OS kernel from scratch and actually played DOOM on it. And my colleague was able to demo this at Google I/O. We were super proud of this particular milestone, one because it really demonstrated that if you throw more intelligence, you throw more subagents at this sort of problem, a model like Gemini 1.5 Flash could do this in a way that was not only very, very powerful, but also scalable, and you know, mildly affordable. Obviously, we're not going to spend thousands and thousands of dollars to build an OS kernel every day, though it is possible. And some of the stats out of this: it took 93 subagents over the course of 12 hours, made 15,000 requests, 2 billion tokens, and it was under 100 dollars, which was one of the really cool aspects of this project. And so as you can see with this particular example, subagent primitives are one of the defining parts about building the 2026 era of agent teams.

</details>

### 内部研发落地：90% 自动化全栈模型评测

**Kevin Hou**: 智能体团队只是第一个代表性案例。接下来，我想向大家展示另一个在我们团队内部高频使用的核心工作流，它能更好地展现这套全新原语所迸发出的巨大生产力。

这个应用场景就是：**全流程自动化模型科研评测（Automating Research Tasks）**。

在日常工作中，我们直接扎根在 Gemini 模型工程团队内部，核心职责就是帮助 Gemini 模型在各种复杂的代码生成、工具调用以及智能体任务上变得越来越强大。而这正是让整个产品产生质变化学反应的起点。

我们在 Google 内部维护着一个专门面向科研人员、算法专家、核心工程师以及非技术协同人员的 Antigravity 内部特化版本。一旦大家掌握了 Antigravity 提供的这套基础原语，它就会瞬间演变成为自动化改造个人与团队日常工作流的无匹利器。

我们以模型算法研发中极为经典的 **Side-by-side（并排对比）评测分析** 为例。无论是在 DeepMind 内部，还是在整个人工智能前沿产业中，这都是极具普遍性的重度工作流：

在常规研发流程中，你通常需要对多个模型实验版本（Rollouts）进行横向对比，比如将两个、三个甚至四个候选版本放在一起跑评测集。你运行了一大批评估测试，得到了各自的数据集产出，这些数据通常会被整理存放在两张巨大的结构化数据表中。

在此之后，算法研究员必须对照着基准对照组（Control）和实验组（Experiment）的数据展开极其繁琐的交叉分析。你不仅需要算出具体的指标差异（Delta），更要抽丝剥茧地定位出到底是什么原因引发了这些指标波动，进而指导团队在下一个实验周期中进行精准调优与模型迭代。

在传统工作模式下，这一整套流程充斥着无穷无尽的 Jupyter Notebook 手工编码，算法科学家们不得不把海量的时间与体力耗费在这种机械的数据搬砖与统计绘图上。

但当你真正运用起 2026 时代的新原语时，整个工作流会变得前所未有的优雅与敏捷：

内部的研究员们如今只需要在界面中直接用日常自然语言向智能体提问，就能将**整个评测分析工作流中 90% 的繁琐步骤彻底实现自动化**！

由于智能体已经预先通过技能包（Skills）深度加载了专业知识，并且彻底通晓 Google 内部庞大复杂的 **Monorepo（单体代码仓库）**的代码架构与数据管线，它能够直接在后台跑通底层数据、完成指标精算，并在极短时间内为你计算并返回完整的差异对比。

但真正令人拍案叫绝的硬核能力不仅止步于此——它没有把冰冷的数据差异直接甩给研究员就草草交差，而是**更进一步**：它在后台当场实例化了一名专门的“科研分析专家智能体”，由该智能体一口气头脑风暴并推导出了**多达 100 种可能导致指标波动的理论假说**！

紧接着，它迅速调度起子智能体集群，**为这 100 个假设各自独立派生出一个子智能体（Subagent）**，驱动它们在隔离环境中高并发、全并行地逐一深入特定的错误用例与代码堆栈中进行定向归因与证据挖掘，最终将所有并发分析结论聚合并映射为一份高度结构化的统一报告呈现在研究员面前：“嘿，根据我的穷尽式排查，我帮您定位到了这几个核心异常区间，这是生成的完整分析报告，请您审阅。”

更令人称道的是，它并没有止步于抛出一份静态 Markdown 文档，而是现场为研究员构建了一套**完全动态的生成式 UI 交互界面**！你可以直接在这个定制化看板里自由交互、点击下拉框、按标签多维筛选、切片对比数据分布，以最直观、最符合直觉的交互模式沉浸式探索数据。

在 Google 内部，我们极其重视此类深层工作流对模型研发与用户体验的迭代赋能。过去一个高度依赖人工、往往要耗费几天甚至数周的沉重工作流，现在只需要几分钟即可一键搞定。

过去你必须手工写大量胶水代码：自己拼装异步智能体并发池、自己配置大模型裁判（LLM Judges）、自己搭起一套复杂的数据清洗管道。而今天，所有这些曾经极其沉重的工程架构，全部都被平铺并直接沉淀为了我们在前文所确立的基础新原语：
* 一个具备完全自适应能力的**动态子智能体拓扑图谱（Dynamic Subagent Graph）**；
* 贯穿工作流终点的 **Generative UI**，能够以用户最易理解、最匹配其认知习惯的交互形态瞬时呈现深度洞察；
* 用户所需付出的全部成本，仅仅是挂载一个配置好的 `skills` 技能文件，然后直接在对话框中用自然语言发号施令即可。

<details>
<summary>Original English</summary>

**[Speaker 1]**: So agent teams are just that first example, and I want to show you another example that our team uses internally that sort of demonstrates some of these new primitives. Um, the second one is about automating research tasks. So we work inside of Gemini. We help sort of make Gemini better at coding-related tasks, agentic-related tasks. And this is where the real magic started happening with the product. We have an internal version of Antigravity that researchers, engineers, non-technical folks can use. And when they understand the primitives that Antigravity offers, it becomes a very, very powerful way to automate your own workflows. So you'll take the example of side-by-side eval analysis. So this is a very common workload, not only at DeepMind, but just generally in the industry. Essentially, you will take multiple rollouts—two, three, four rollouts—and you want to compare them. So you'll do some rollouts, you get some results, and they'll essentially be in two different tables. Now you'll look at the control, you'll look at the experiment, and you'll figure out not only what the difference was, but perhaps what are the reasons for those differences, and how can we actually iterate from there and make a better version for the next experiment? Now traditionally, this was a lot of Jupyter notebook elbow grease, essentially. But when you start working with the new primitives in 2026, you end up with a lot cleaner of a workflow. So researchers were able to automate 90% of this workflow by simply asking the agent about the evals in question using natural language. Then the agent, that is now primed with skills and an understanding of Google's massive monorepo codebase, is able to crunch the numbers and get back to you with a delta. Now what's really cool here is instead of just taking that delta and handing it back to the user, it went the extra step. It spun up a research agent specialist that proposes a hundred different hypotheses over why those deltas might occur. And then it uses subagents to then spin up one subagent for each hypothesis and basically drills into that particular case in parallel, mapping back to a single response and then telling the researcher, "Hey, here are some areas that I found. Now here's a report that you can review." And what's really cool is that it doesn't stop at just the report; it actually puts together a Generative UI for you to look through, interact, select dropdowns, filter, segment, slice, and actually interact richly with that data. And internally, we care a lot about this sort of workflow: improving the model, understanding the ways that users find success and failure internally at Google. So what used to be a very manual process now takes minutes. What used to be hand-engineering—you'd have to build your own async pool of agents, you'd have to set up your judges, you'd have to tape together data pipelines—all of this now starts becoming grounded in these new primitives that we established earlier in the slideshow. You have a subagent graph that is completely dynamic. The Generative UI comes in at the end to richly convey the findings in a way that the user best understands or caters to their learning style. And all of these things can be regenerated and redone on the fly. All the user had to do was load up a skills file and ask away.

</details>

### 三大支柱原语深度解析：动态子智能体、Sidecars 与生成式 UI

**Kevin Hou**: 结合刚才介绍的 `/teamwork` 智能体团队协作和模型评测分析这两个具有划时代意义的实战案例，我们终于清晰地推导并梳理出了我一再强调的 2026 核心原语。正是底层模型特性的根本性跃迁，迫使我们必须从第一性原理出发，彻底重构我们对开发者产品的设计与工程实现认知。

现在，让我们来逐一深入拆解这**三大支柱原语**：

#### 第一项原语：动态子智能体（Dynamic Subagents）

如果做进一步的延展说明，其核心本质在于：在我们的架构中，**没有任何两个子智能体是千篇一律的**。

主导智能体完全具备自主编排与统领整个团队的最高权限。它根据实际任务拓扑，在运行时动态生成提示词、即时完成参数与工具链初始化，并在毫秒级完成子智能体的动态派生与配置。

这些子智能体不仅天然支持大规模全并发作业，而且能够按需安全入驻各类强隔离运行环境——不论是轻量级沙箱（Sandbox），还是远程分布式执行集群。更重要的是，它们能够根据上下文需要，随时扮演无限多样化的专门角色。

这里的工程扩展逻辑是极其显而易见的。正如大家从刚才那两个极具代表性的实战用例中所见证的那样：**随着底层模型智力水平的飞跃，你手下的这支智能体团队的分工将变得越来越细分、协作将变得越来越紧密无缝**。而这在终局层面上意味着：它们将有能力代替你全自动解决维度更高、上下文更复杂、架构更宏大的真实工程命题。

#### 第二项原语：伴生进程插件协议（Sidecars）

这是我们正在全力引入 Antigravity 的全新插件协议规范。

顾名思义，**Sidecar（伴生进程）本质上就是一个与宿主环境并行运行的常驻伴生服务进程**。这一极具工程感的命名本身，就非常精准地揭示了它在系统底层所扮演的角色。它是一个具备长生命周期、常驻内存的底层实用工具，其核心使命就是充当“监听哨兵”。

它赋能底层大模型真正具备了“感知与倾听外部客观物理世界”的核心能力，使模型能够针对外部环境中发生的各种异构事件自主注册并激活触发器。

在实际场景中，这个外部事件源可以极为丰富：它可以是一条刚收到的 **SMS 短信**、一个来自三方服务的 **Webhooks 回调**、一条定时轮询触发的 **Cron 计划任务**，或者与 **GitHub PR** 状态变更事件流的无缝挂钩……这里的集成空间是无限开阔的。

Sidecars 构成了 Antigravity 面向未来打造的通用插件抽象原语。Antigravity 系统当前内部所有与时钟和计划任务相关的功能特性——包括大家非常熟悉的定时任务 Cron 表达式调度机制——在系统最底层的工程实现上，全部都是无一例外地基于这套全新的 Sidecar 原语搭建起来的。

我们计划在今年夏天晚些时候正式对外发布 Sidecar 开放技术规范，届时全球所有的开发者都将能够基于这项全新原语，为 Antigravity 自由扩展、构建独一无二的专属插件与生态服务。在 Google 内部，大家已经基于这个机制探索出了许多令人赞叹的创新用法。

#### 第三项原语：生成式界面（Generative UI）

我们内部有一个非常前沿的推论：**人类预先手工编写、写死在系统里的专用交互界面，正在走向终结**。

在 Antigravity 强大的软硬件协同优化下，Gemini Flash 模型的端到端输出吞吐能够稳定飙升至**近 900 Tokens/秒**！这个生成速度，比市面上绝大多数前沿大模型的使用体验要**快上整整 10 倍以上**。

这意味着，在短短几秒钟之内，用户脑海中的任何一个模糊构想，都能立刻通过自然语言提示词，直接在你的对话视图中精准编译并渲染为一个专门针对当下任务场景量身定制的动态交互界面。

Antigravity 彻底摒弃了对生硬模板或静态 HTML 文件的依赖，它能够直接在对话主视流中**内联即时渲染（Render Inline）**出纯原生的交互式 UI。

正是基于这一突破，你才能够直接在界面里瞬时拉起窗口**当场畅玩《DOOM》**！但这绝不仅仅是一个极客炫技的玩具，这项能力能够极其自然地延伸到日常所有的生产力组件中：柱状图、动态折线趋势图、多维复杂交互表格，甚至是任何你希望即时下钻、做多维过滤与深入交互的复杂数据体。

所有这些视图，用户既可以将其导出为纯净的 Markdown 文档进行留存，也可以作为一种全新形态的对话式生成 UI 随用随抛、即时迭代。

<details>
<summary>Original English</summary>

**[Speaker 1]**: So with teamwork and this eval example, we start arriving at these 2026 primitives that I keep talking about. And these model characteristics really changed the way that we have to think about the product and how we have to develop the product. So the three examples that we talked about: first, we have the dynamic subagents. And to provide a little bit more color here, basically no two subagents are the same. The main agent is the one that is orchestrating this entirely on its own. It's configuring and prompting and seeding these subagents on the fly. They can operate in parallel, they can operate in different types of secure environments—be it a sandbox, be it a remote execution system—and they can all take on an infinite number of specialized roles. So the scaling story here is quite obvious. And from the last two examples, you can probably tell: as the model gets smarter, your team will become more specialized, it will become more collaborative, and ultimately that means it'll be capable of getting more complex work done for you. And now the second is this new concept. We've alluded to it slightly in the past, but it's called sidecars. This is a new plugin protocol that we're bringing to Antigravity. A sidecar process is essentially—it is a sidecar process. The naming sort of reflects what's going on under the hood, but it's a long-lived utility, and it's responsible for listening. It allows the model to listen to the outside world and set up its own triggers for things that might happen. For example, this could be SMS messages, this could be webhooks, cron jobs, hooking it up to GitHub PRs—the list goes on and on. But this is a generic plugin primitive. Antigravity already uses sidecars for things that are time-based. This is where the scheduled task cron concept comes from. But under the hood, this is all this new sidecar primitive. So we're releasing the spec for this so that you all can build on top of this new primitive later this summer. But there are some really, really cool ways that people internally have been using this sort of concept. And the third and final primitive is Generative UI. So we hypothesize that human-written, specialized UIs are kind of dead. Gemini Flash on Antigravity clocks in at almost 900 tokens a second. This is 10x faster than a lot of the other frontier model experiences. And in a matter of seconds, you're able to go from whatever you are thinking inside of your head into a prompt into a use case that is designed, embedded inside of your conversation view perfectly. And rather than rely on templates or even HTML files, Antigravity can render your generated UI inline. So you can do things like this and play DOOM. But this also extends to things like bar charts, graphs, tables, anything that you would want to interact with and maybe inspect a little bit further—just a markdown file,

**[Speaker 0]**: Or just a conversation... Generative UI.

</details>

### 告别“注塑死板”的产品设计哲学

**Kevin Hou**: 这种全新的设计哲学，在很多层面上都让我深深联想到了已故的**史蒂夫·乔布斯（Steve Jobs）**当年在旧金山发布初代 iPhone 时的那段经典演讲。

在解释苹果为什么下定决心彻底砍掉手机实体键盘时，乔布斯曾一针见血地指出：
> “当时市面上的那些智能手机，无论你到底需不需要键盘，那块键盘都死死地霸占在那里；它们的所有控制按键全都像**注塑塑料一样被永久固定死了（Fixed in plastic）**，无论面对什么样的应用程序，界面按键永远一成不变。”

以完全相通的哲学逻辑，我们在研发 Antigravity 时，坚定地选择让整套产品的形态能够随着底层智能体的发展诉求而进行动态伸缩扩展。

我们果断放弃了那些笨重僵化的专用基础设施和死板的机械式固定 UI 控件，转而全力拥抱 **Sidecars 与 Generative UI** 所构建的柔性系统。这使得我们打造出来的软件产品体验，彻底告别了那些“被固定在塑料里”的死板形态。

动态子智能体（Subagents）、Sidecar 伴生监听机制与生成式 UI（Generative UI）——这三大核心原语共同汇聚成了驱动 Antigravity 狂飙突进的最核心引擎。

从始至终，我们都在竭尽所能地克制产品设计的干预欲：**不要挡模型的路，让模型尽情发挥！**

如果你此时此刻正在尝试围绕 AI 智能体构建全新的软件产品，你最应该深入反思与拷问自己的核心命题就是：我的产品里究竟沉淀了哪些核心原语？当底层模型的智力水平呈现指数级跃升时，这些原语能否自然地跟随智能实现无缝扩展？

在今天这个时代，借助各种先进的 AI 工具，交付发布某几个特定的业务功能早已经不再是什么难事了。真正决定产品生死与胜负的核心，在于你所做出的架构取舍：你究竟应该向产品中引入哪些真正具备通用延展性的底层原语，才能确保当不可避免地迎来下一代**速度更快、推理更强、成本更低廉**的尖端模型发布时，你的整个产品架构能够毫不费力地顺势起飞？

只要你能找到并握紧那套正确的原语，无论你是一名一线开发者，还是一位把控全局的产品负责人，大模型所能爆发出的惊人潜能，都将一次又一次地彻底颠覆你的认知。

按照我们团队的经典老传统，只要我还没彻底把 Google 内部的 TPU 算力资源彻底榨干征服，我就会在以后的每一场演讲中继续挂出这张幻灯片！

欢迎大家在 Twitter（X）上随时关注我，也可以直接给我发私信交流反馈。我们永远在渴求最前沿、最具颠覆性的产品灵感与架构思路，期待与大家一起打造最新、最酷的未来之作。

感谢大家的聆听！非常感谢 Swix 和 Ben 的盛情邀请，每一次来到 AI Engineer 的现场都让我感到无比振奋！

稍后我将会前往会场外的 Antigravity 官方展台。如果大家希望就产品架构做进一步的深度面对面交流，或者想深入了解产品背后更多的技术内幕，我们的核心团队成员都会在展台现场等候大家。

非常感谢大家宝贵的时间！

**主持人**: 太精彩了，期待稍后在展台与大家深入碰面！

<details>
<summary>Original English</summary>

**[Speaker 1]**: In many ways, it reminds me of the quote that the late Steve Jobs said when unveiling the iPhone. He justifies the removal of the keyboard and says: they all have these keyboards, they are there whether you need them or not. And they all have these control buttons that are fixed in plastic and are the same for every application. And in an analogous way, we built our product to dynamically scale with the needs of the agent. We skipped having heavy infrastructure and mechanical UIs in favor of sidecars and Generative UI. And that creates a product experience that is not fixed in plastic. So subagents, sidecar triggers, and Generative UI are the latest primitives that are powering Antigravity. We've tried our best to stay out of the way and let the model cook. And if you're building a product around an agent, you should consider: what are the primitives that are in my product, and how might this scale with the model's intelligence? We all are familiar with shipping features is now quite easy with all of these new tools, and it's about deciding what features to actually add so that your products can scale with the next release, the next model, which will inevitably be faster, better, and cheaper. And so with the right primitives, you as a builder or you as a product owner, you might be surprised at what the models can do. And in classic fashion, I'm going to keep using this slide until I've actually conquered the TPU crunch. So you can find me on Twitter, um, you could DM me for feedback. We're always looking for new ideas on how to build the latest and greatest. Thank you for watching. Thank you Swix and Ben for having me. It's always a joy to be here and I'll be at the Antigravity booth. If you want to talk further, if you want to get to know the product a bit more, some team members will be there. So thank you so much for your time.

**[Speaker 0]**: Excited to meet all of you.

</details>