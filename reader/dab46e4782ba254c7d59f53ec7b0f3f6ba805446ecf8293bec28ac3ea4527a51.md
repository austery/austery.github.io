---
author: AI Engineer
date: '2026-04-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-QFHIoCo-Ko
speaker: AI Engineer
tags:
  - agentic-workflow
  - human-in-the-loop
  - context-window-management
  - test-driven-development
  - software-architecture
title: AI编程实战：Matt Pocock的全栈AI辅助开发工作流
summary: 本讲座详细拆解了一套将AI（大语言模型）深度集成到软件开发全流程的实战方法论。讲师 Matt Pocock 提出，成功的关键在于将传统软件工程的智慧（如TDD、模块化设计）应用于与AI的协作中。他介绍了一个从“概念拷问”（Grilling）到“产品需求文档”（PRD），再到“看板驱动的AFK（Away From Keyboard）智能体”执行的完整工作流。核心在于通过“垂直切片”（Vertical Slices）和“深度模块”（Deep Modules）架构，为AI创造高效的反馈循环，从而在提升开发速度的同时，保证代码质量和架构健康度。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Martin Fowler
  - John Ousterhout
  - Frederick P. Brooks
companies_orgs: []
products_models: []
media_books:
  - Refactoring
  - The Pragmatic Programmer
  - A Philosophy of Software Design
  - The Design of Design
status: evergreen
---
### AI 编程的核心挑战：理解LLM的内在约束

在探讨如何与 AI 高效协作编程之前，我们必须首先理解大型语言模型（LLM）固有的两大奇特约束。这些约束是我们一切工作方法的基础。第一个核心概念由 Human Layer 公司的 Dex Hy 提出，即 LLM 存在一个 **“智能区”（Smart Zone）** 和一个 **“愚笨区”（Dumb Zone）**。当你开启一个全新的对话时，LLM 处于最智能的状态，因为此时上下文的“注意力关系”最不紧张。然而，每当你向上下文中添加一个 token，就好像往足球联赛里增加一支球队，比赛场次会呈二次方级增长。同样，LLM 中每个 token 之间都存在位置和语义上的注意力关系。这意味着，当上下文窗口被填充到一定程度（根据经验，大约在 100k token 左右，无论总上限是 200k 还是 100 万），模型就会开始“变笨”，做出一些愚蠢的决策。这种随着对话拉长、AI 性能下降的现象，相信很多人都深有体会。

因此，我们的任务设计必须适应这一现实：**确保每个任务的规模都能 comfortably 落在“智能区”内**，避免让 AI“贪多嚼不烂”。这与 Martin Fowler 在《重构》和《程序员修炼之道》中给予人类开发者的建议不谋而合：保持任务小巧，可以有效避免开发者自身陷入认知过载的“愚笨区”。

第二个核心约束是，LLM 就像电影《记忆碎片》（Memento）的主角，它们会 **持续性遗忘**。每当你清空上下文，它就会重置回最初的系统提示（System Prompt）状态，抹去之前所有的探索、实现和测试过程。许多开发者喜欢使用“压缩”（Compacting）功能，将冗长的对话历史总结成一小段文字保留在上下文中。但我极度厌恶这种做法，因为它会在上下文中累积“沉淀物”（sediment），污染后续的交互。我更倾向于让 AI 像《记忆碎片》的主角一样运作，每次都从一个干净、确定的初始状态开始。优化这种“清空并重来”的模式，使之高效，才是关键所在。

<details>
<summary>Original English Source</summary>

So I want to talk about first the kind of weird constraints that LLMs have and those weird constraints are sort of what we have to base a lot of our work around. Now, there's a guy called Dex Hy who runs a company called Human Layer, and he came up with this idea, which is that when you're working with LLMs, they have a smart zone and a dumb zone. When you're first kind of like working with an LM and it's like you just started a new conversation, you start from nothing. That's when the LLM is going to do its best work because in that situation, the attention relationships are the least strained. Every time you add a token to an LLM, it's kind of like you're adding a team to a football league. You think of the number of matches that get added every time you add a team to a football league. It just go scales quadratically. And that's because you have attention relationships going from essentially each token to the other that are positional and the sort of meaning of the individual token. And so this means that by around sort of 40% or around I would say around 100k is kind of my new marker for this because it doesn't matter whether you're using 1 million uh context window or 200k. It's always going to be about this. It starts to just get dumber. So as you continually keep adding stuff to the same context window, it just gets dumber and dumber until it's making kind of stupid decisions. Raise your hand if that feels familiar to you. Yeah. Cool.

So this means that we kind of want to size our tasks in a way that sticks within the smart zone, right? We don't want the AI to bite off more than it can chew. And this goes back to old advice like Martin Fowler in refactoring uh like uh the pragmatic programmer talks about this. Don't bite off more than you can chew. Keep your tasks small so that you as a developer, a human developer don't freak out and don't start acting and going into the dumb zone.

Another weird constraint of LLM is LLM are kind of like the guy from Momento, right? They just continually forget. They could just keep resetting back to the base state. Let me pull up this diagram. I sort of I I I really should use slides, but I just prefer just like randomly scrolling around a infinite uh TL draw canvas. Thank you, Steve. Um, so let's say another concept I want you to have is that every session with an LLM kind of goes through the same stages. You have first of all the system prompt here. This gray box here is essentially the stuff that's always in your context. You want this to be as small as possible because if you have a ton of stuff in here, if you have 250k tokens, like I have seen people put in there, then that you're just going to go straight into the dumb zone without even being able to do anything. So you want this to be tiny. You then go into a kind of exploratory phase. This blue is sort of where the coding agent is going out and exploring the codebase. Then you go into implementation and then you go into testing and kind of making sure that it works, running your feedback loops and things like this. Raise your hand if that feels familiar based on what you've done. Yep. Sort of the like the the main cornerstones of any session. And when you clear the context, you go right back to the system prompt. Bof, you go right back there. So you delete everything that's come before.

And raise your hand if you've heard of compacting as well. Yeah. Okay. There are some people who've not heard of compacting. So let's just quickly show what that means. For instance, I've just been having a little chat with my LLM. ... And when I compact then it's going to squeeze all of that conversation which admittedly isn't very much into a much smaller space. And this in diagram terms kind of looks like this where you take all of the information from the session and you essentially create a history out of it, a written record of what happened.

And devs love compacting for some reason, but I hate it. I much prefer my AI to behave like the guy from Momento because this state is always the same. Always the same. Every time you do it, you clear and you go back to the beginning. And so if you're able to do that and you're able to optimize for that, then you're in a great spot. So that's kind of the two things I want you to think about with LLM, the two constraints that we're working with. They have a smart zone and a dumb zone. And they're like the guy from Momento.

</details>

### 达成共识：“拷问我”技能与共享设计理念的构建

在软件开发中，一个普遍存在的误区是所谓的 **“规范到代码”（Specs-to-Code）运动**。这种思想主张，你只需要写一份详尽的需求文档，然后把它扔给 AI，AI 就能生成代码。如果代码有问题，你不应该去修改代码，而是回去修改文档，如此循环。这本质上是另一种形式的“感觉编程”（vibe coding），它让你忽略了代码本身，而代码才是我们真正的战场。我曾尝试过这种方法，结论是：它行不通。你必须牢牢掌控代码，理解并塑造它。

为了解决这个问题，我创造了一个名为 **“拷问我”（Grill Me）** 的技能。这个技能的提示语非常简短精炼：“无情地就这个计划的每个方面对我进行访谈，直到我们达成共识。逐一探索设计树的每个分支，解决所有依赖项。针对每个问题，请提供你推荐的答案，并一次只问一个问题。”

这个技能的核心目的，是解决与 AI 协作时的“错位”（misalignment）问题。当我使用传统的计划模式时，我发现 AI 急于为我生成一个计划，但那并不是我真正需要的。我需要的是与我的 AI 代理达成一种 **共享的设计理念（Shared Design Concept）**。这个概念源于 Frederick P. Brooks 的《设计的设计》，指的是所有参与者共同构建的一个共享思想。我不需要一个计划文档这样的“资产”，我需要和 AI “在同一个波长上”。

“拷问我”技能非常有效。通过这种方式，AI 会就一个模糊的想法（比如“为平台增加游戏化功能”）提出一系列深刻且具体的问题，例如：“积分应该追溯计算吗？我们有历史数据，但这样做会很复杂。” 这些问题往往是我自己都未曾考虑到的。整个过程就像与一个领域专家进行头脑风暴，AI 甚至会给出推荐方案。这个过程可能很长，有时会持续一个小时，问答多达上百个问题。但最终，我们得到的是一个极其宝贵的对话历史，它本身就是我们共同创建的设计理念的完美记录。这个过程确保了在进入任何实际开发之前，人与AI对目标的理解已经高度一致。

<details>
<summary>Original English Source</summary>

The uh the sort of silent idea that I'm talking against here, that I'm arguing against is the specs to code movement. Has anyone heard of the specs to code movement? ... what it is is people say, okay, you can write a program or you want to build an app. The best way to build that app is to take some specifications. So to write some sort of like document and then turn that document into code. ... if there's something wrong with the resulting code. You don't look at the code, you look back at the specs, you change the specs and you sort of just keep going like this. This is kind of like vibe coding by another name where you're essentially ignoring the code. You don't need to worry about the code. You just sort of keep editing the specs and eventually you just keep going. And I tried this. I really tried it and it sucks. It doesn't work because you need to keep a handle on the code. You need to understand what's in it. You need to shape it because the code is your battleground.

...we're going to start by using a skill which is very close to my heart. It's the grill me skill. And this grill me skill is wonderfully small, wonderfully tiny. And it helps prevent one of I think the main issues when you're working with an AI, which is misalignment.
... I'm invoking the grill me skill. And what I'm going to do is I'm going to say grill me and I'm going to pass in the client brief.
... this is inside the repo so you can check it out. It's extremely short. Interview me relentlessly about every aspect of this plan until we reach a shared understanding. Walk down each branch of the design tree, resolving dependencies one by one. For each question, provide your recommended answer. Ask the questions one at a time. uh blah blah blah. What this does, and what I noticed when I was working with AI, especially in plan mode actually, is it would really eagerly try to produce a plan for me. It would say, "Okay, I think I've got enough. I'm just goof plan."

And what I found was that I was really trying to find the words for this for for what I wanted instead of that. And Frederick P. Brooks in the design of design he has a great quote uh talking about the design concept when you're working on something new with someone when you're uh all trying to build something together then there's this shared idea that's shared between all participants and that is the design concept and that's what I realized I needed with Claude I needed I needed to reach a shared understanding I didn't need an asset I didn't need a plan I needed to be on the same wavelength as the AI as my agent. And this is an extremely effective way of doing it.
... So, should points be retroactive? There are existing lessons progress records. We're completing out timestamps. This is a really nasty question, right? Should we actually go back and backfill all of the lesson progress events? This is a kind of question that you need to be aligned on if you're going to fulfill the feature properly. This is not something I considered and Sarah Chen certainly didn't consider.
... And this grill me skill this can last a long time. This can I've had it ask me 40 questions. I've had it ask me 80 questions. I've had some people it asks a hundred questions to literally you're sat there for an hour chatting to the AI. And what you end up with is essentially this conversation history that works really nicely and works really nicely as an asset of the design concept that you're creating.

</details>

### 从对齐到执行：PRD 与看板驱动的开发流程

经过“拷问”环节，我们与 AI 达成了对设计理念的深刻共识。下一步是将这个共享的理解转化为可执行的计划。这个过程分为两步：**创建产品需求文档（PRD）** 和 **构建看板（Kanban Board）**。

首先，我们会让 AI 基于“拷问”环节的对话内容，生成一份 **产品需求文档（PRD）**。这份文档 berfungsi a sebagai **“目的地文档”（Destination Document）**，它清晰地描绘了我们最终要实现的目标。PRD 通常包含问题陈述、解决方案、一系列用户故事（User Stories）、实现决策以及测试决策等。有趣的是，我通常 **不会** 去审查这份由 AI 生成的 PRD。因为在经过了彻底的“拷问”后，我与 AI 已经达成了高度共识，我知道 AI 擅长总结。此时去阅读文档，仅仅是在检查 AI 的总结能力，而非设计本身，这并没有太多价值。

有了目的地文档，我们接着需要规划 **“旅程文档”（Journey Document）**，即如何分步到达目的地。传统的做法是生成一个线性的、多阶段的计划（multi-phase plan）。但我现在更喜欢一种更优越的方式：**创建一个看板（Kanban Board）**。我们会让 AI 将 PRD 分解成一系列可以独立领取的、具有依赖关系的任务卡片。例如，一个任务可能是“实现游戏化服务的数据库 Schema”，它不依赖于任何其他任务；而另一个任务“将积分系统接入课程完成事件”则可能依赖于前一个任务。

这种看板模式远胜于线性计划，因为它天然支持 **并行化**。一个线性的计划只能由一个智能体按顺序执行。而一个看板，或者说一个 **有向无环图（DAG）**，允许多个智能体同时开工，只要它们领取的任务的前置依赖已经完成。这为我们后续引入并行开发的“夜班”模式奠定了基础。

<details>
<summary>Original English Source</summary>

So at this point now I have used 25k tokens and all of that or loads of that stuff is gold. I want to keep that around. I've I've got 25k great tokens there. And what I want to do is kind of summarize it in some kind of destination document. So this is um the next exercise where we're going to uh we're going to write a product requirements document. And the product requirements document or the PRD is essentially that's its function. It's the destination document. And it sort of doesn't matter what shape it is. I've got a shape that I prefer and that I quite like, but you can just choose your own shape or whatever your company uses. And all we're really doing is summarizing the design concept that we have so far.

... Should I be reviewing this document? Raise your hand if you think I should be reviewing the document. Yeah, I don't I don't look at these. The reason I don't look at these is because what am I testing at this point? ... I know that LLMs are great at summarization because they are they're really good at summarization. I have reached the same wavelength as the LLM, right? Using the grill me skill, we have a shared design concept. So if I have a shared design concept, all I'm doing is I'm just essentially checking the LLM's ability to summarize. So I don't tend to read these.

...we have our destination. ... How do we split it so that we don't put things into the dump zone? In other words, we have our number four. How do we split it into this kind of multi-phase plan? Well, probably what you would do at this point is you would say, "Okay, Claude, give me a multi-phase plan that gets me to this destination." Right? That sort of makes sense. This is what we've been doing before, but I have um a sort of better way of doing it now, which is that I like creating a canban board out of this. ... A camon board is essentially just a set of tickets that you put on the wall that have blocking relationships to each other. ... It has proposed that we split this setup into um five different tasks. Here we have the first one which is the schema and the gamification service. ... This is blocked by nothing. ... This one here is blocked by all of the tasks.

... this means that you can start to parallelize. You can start to get agents working at the same time on these tasks because yeah, this one needs to be done first and then these two can be grabbed at the same time by independent agents. ... this allows you um to turn those plans into optimally kind of like into directed asyclic graphs essentially where you just are able to um essentially have three phases here where you have phase one... Then phase two... And then phase three...
That's why I prefer a canon board set up like this to a sequential plan because a sequential plan can really only be picked up by one agent.

</details>

### 高效 AI 开发的关键：垂直切片与追踪弹

在将 PRD 分解为看板任务时，有一个极其重要的技巧，它直接决定了 AI 开发的效率和反馈速度。这个技巧源自《程序员修炼之道》中的经典理念：**“追踪弹”（Tracer Bullets）**，或者说 **“垂直切片”（Vertical Slices）**。

我注意到，AI 有一种强烈的自然倾向，喜欢进行 **“水平编码”（Horizontal Coding）**。也就是说，它会按照系统的分层，一层一层地进行开发。比如，第一阶段，它会完成所有数据库相关的改动（Schema、迁移等）；第二阶段，完成所有 API 层的逻辑；第三阶段，再开发前端界面。这种做法最大的弊端在于，你必须等到最后一个阶段完成，才能得到一个真正可用的、贯穿所有层级的完整功能反馈。在那之前，你无法测试各个层面是否能真正协同工作。

**正确的做法是进行“垂直切片”**。我们应该将功能切分成一个个薄片，每个薄片都纵向贯穿所有必要的系统层级。例如，第一个垂直切片就应该包含最核心的数据库变更、最基础的后端服务逻辑，以及一个最简约的前端展现。这样做的好处是，在第一个切片完成时，我们就能立即获得一个端到端（end-to-end）的反馈，验证整个流程是否通畅。这就像在黑夜中射击时使用的追踪弹，每一发都能让你看到弹道，从而即时调整瞄准方向。

因此，在生成看板任务时，我会特别指示 AI 采用垂直切片的策略。如果它提出的第一个任务仅仅是“创建游戏化服务的数据库 Schema”，我就会驳回，并指出“第一个切片太水平了”。一个好的垂直切片应该是这样的：“为课程完成事件奖励积分，并在用户仪表盘上可见”。这个任务显然涉及了数据库、后端逻辑和前端展现，它是一个真正的、可提供即时反馈的“追踪弹”。这种方法能极大地提升 AI 的工作效率，避免它在没有反馈的情况下“盲目编码”。

<details>
<summary>Original English Source</summary>

There's a really, really important technique when you're kind of figuring out what the shape of this journey should look like. And it sort of comes to this very classic idea uh which comes from pragmatic programmer called tracer bullets or vertical slices.

Systems have layers, right? There are layers in your system. ... You might have a database, you might have an API, you might have a front end... Well, what I noticed is that AI loves to code horizontally. So it loves to code layer by layer. So in other words, in phase one, it will do all of the database stuff... Then it will go into phase two and do all of the API stuff. Then it will add the front end on top of that. Does can anyone tell me what's wrong with that picture? ... You don't get feedback on your work until you've really started or completed phase three. So what you really need to do is you're not until you get to phase three, you're not actually testing that all the layers work together.

You haven't got an integrated system that you can test against. And so instead you need to think about vertical layers. You need to think about thin slices of functionality that cross all of the layers that you need to. And this is a much better way to work, much better way for the AI to work too because it means at the end of phase one or during phase one, it can get feedback on its entire flow. So what this means to me is inside the PRD to issues skill up here I have got break a PRD into independently grabbable issues using vertical slices traceable...

...a traceable bullet by the way is... when you're like an anti-aircraft gunner... if you're just shooting normal bullets, you have no idea what you're firing at, right? ... Tracer bullets is they attach a tiny bit of phosphoresence or phosphor or something to make it glow as it goes. So, this means that every sixth bullet or something, you actually see a line in the sky. So, you have feedback on where you're aiming. So this is what this is the idea here is that we increase our level of feedback and we get near instant feedback on what we're building because without that the AI is kind of coding blind until it reaches the later phases.

So what I see here is that even though I've I've told it to do vertical slices, it's proposing to create the gamification service first on its own. That's just one slice there. And that to me feels like a horizontal slice. ... I want to see the schema changes... I want to see some new service being created and I want a minimal representation of that on the front end. ... So I'm going to give the AI a rollicking. ... the first slice is too horizontal. ... award points for lesson completion visible on dashboard. Yes, that's a beautiful vertical slice...

</details>

### AFK 智能体：自动化“夜班”执行与 TDD 的力量

一旦我们通过垂直切片构建了看板，人类在开发环中的主要任务就告一段落了。现在，我们进入 **“离座”（Away-From-Keyboard, AFK）** 模式，将执行工作交接给 AI 智能体。我把这个流程比作 **“白班”和“夜班”**：人类在“白班”负责规划、对齐、切分任务；而 AI 则在“夜班”期间，自主地领取看板上的任务并完成编码工作。

这个 AFK 智能体本质上是一个 **Ralph 循环**（基于《辛普森一家》的角色 Ralph Wiggum 的一个概念，意指通过一系列小步骤不断逼近最终目标）。它会按照预设的优先级（例如：先修复关键 Bug，再做追踪弹任务，最后是优化和重构）从看板上拾取任务。

在执行每个任务时，一个至关重要的技术是 **测试驱动开发（Test-Driven Development, TDD）**。我发现 TDD 对于从智能体那里获得高质量代码是绝对必要的。其流程是：首先编写一个失败的测试（Red），这个测试定义了我们想要实现的功能；然后，编写最少的代码让这个测试通过（Green）；最后，在测试保护下进行代码重构（Refactor）。

AI 在没有指导的情况下编写测试时，经常会“作弊”。它会先写完所有实现，然后再补上一堆看似覆盖了代码、但实际上可能什么都没测到的测试。而 TDD 强制它先定义期望的行为（通过失败的测试），然后再去实现它，这使得作弊变得困难得多。

更重要的是，**测试构成了 AI 最关键的反馈循环**。没有高质量、高覆盖率的测试，AI 就如同在盲目编码，你永远无法从它那里得到可靠的产出。你的反馈循环（测试、类型检查、Linting）的质量，直接决定了 AI 编码能力的上限。如果你的代码库难以测试，那么 AI 在其中也必然举步维艰。因此，将 TDD 作为 AFK 智能体工作流的核心部分，不仅能生成测试覆盖，更能从根本上保证 AI 实现的质量和正确性。

<details>
<summary>Original English Source</summary>

And it's at this point that the human leaves the loop. ... We can think of this as kind of like the day shift and the night shift. This is the day shift for the human, right? Planning everything, getting all the uh all the stuff ready and then once we kick it over to the night shift, the AI can just work AFK. But what does that look like?

...running your AFK agent. Now I've called this uh Ralph really because it is a it is essentially a Ralph loop and this prompt here I want to walk through this really closely. ... You're going to work on the AFK issues only. ... If all AFK tasks are complete, output this no more tasks thing. And then the next thing, pick the next task. So what we're doing here is we're essentially running a backlog or curating a backlog that our AFK agent is going to pick up. ... So, it's prioritizing critical bug fixes, development infrastructure, then traceable bullets, then polishing quick wins and refactors. ... we explore the repo, use TDD to complete the task.

Let's talk about TDD... TDD I found is absolutely essential for getting the most out of agents. Uh raise your hand if uh you know what TDD is. Cool. Okay. TDD is testdriven development. What it's essentially doing is it's doing a something called red green refactor. ... it's writing a failing test first. So it's saying, okay, I've broken down the idea of what I'm doing and I'm just going to write a single test that fails and then I need to make the implementation pass. I have found that first of all, this adds tests to the codebase and this this tends to add good tests to the codebase. ... I found that uh raise your hand if you've ever had AI write bad tests. Yeah, it tends to try to cheat at the tests because it's sort of doing it in layers. ... And using this technique, it generally is a lot harder to cheat because it's sort of instrumenting the code before it's then writing the code. So I find that TDD is so so good...

Now TDD is obviously really important and it's really important because these feedback loops are essential to AI essential to get AI to produce anything reasonable because without this AI is totally coding blind right you have to have to um if if your codebase doesn't have feedback loops you're never ever ever going to get decent AI decent output out of AI and often what you'll find is that the quality of your feedback back loops influences how good your AI can code. Essentially, that is the ceiling. So, if you're getting bad outputs from your AI, you often need to increase the quality of your feedback loops.

</details>

### 为 AI 协作构建健壮的架构：深度模块与灰盒思维

一个普遍的问题是：如果我的代码库本身就很糟糕、难以测试，AI 在里面也只会产出垃圾。那么，如何改善代码库以更好地支持 AI 协作？答案在于构建 John Ousterhout 在《软件设计的哲学》一书中所描述的 **“深度模块”（Deep Modules）**。

很多代码库由大量 **“浅层模块”（Shallow Modules）** 组成：一堆小文件，各自导出一些零碎的功能，依赖关系错综复杂。这种架构对人和 AI 来说都是一场噩梦，因为难以理解其间的依赖，更难以测试。你不知道应该在哪个粒度上划定测试边界。AI 在这种环境下，往往会倾向于为每个小函数编写独立的、脆弱的单元测试，而忽略了模块间的集成。

理想的架构则是由 **“深度模块”** 构成。一个深度模块拥有一个 **小而简单的接口**，但其内部封装了 **大量复杂的功能**。这种设计使得测试变得异常容易：你只需要围绕这个模块简单的公共接口编写测试，就能覆盖其内部所有复杂的逻辑，从而获得极高的测试回报。

更重要的是，这种架构帮助我们应对与 AI 协作带来的认知过载问题。随着 AI 越来越多地接管编码工作，我们对代码库的熟悉度会下降。通过设计深度模块，我们可以采取一种 **“灰盒思维”（Gray Box Thinking）**。我们作为架构师，负责设计模块的接口（它的“形状”和行为），而将具体的内部实现委托给 AI。我们不需要深入审查模块内的每一行代码，只需要通过测试确保它在特定条件下行为正确即可。我们了解它的功能和边界，但不必为内部实现的细节所累。

这种方式让我们既能保持对代码库宏观架构的掌控感，又能享受 AI 带来的开发速度。如果你发现自己的代码库难以与 AI 协作，不妨运行一个“改善代码库架构”的技能，让 AI 扫描你的项目，找出那些可以被整合、封装成“深度模块”的浅层模块集群，这会是提升 AI 协作效率的第一步，也是最重要的一步。

<details>
<summary>Original English Source</summary>

So let's go with um bad code first. In his book um the philosophy of software design, John Alistster talks about the ideal type of module. And let's imagine that you have a codebase that looks like this. Each of these uh blocks here are individual files. And these files export things from them. ... if these files are small and they don't kind of ex like export many things, then John would call these shallow modules essentially where they're not very um they kind of look like uh this. ... Now this is hard for the AI to navigate because it doesn't really understand the dependencies between everything. ... And it's then also hard to test this as well because where do you draw your test boundaries here?

... a good codebase looks like ... this where you have what John Asterhout calls deep modules. Modules that have a little interface on there that expose a small simple interface that have a lot of functionality inside them. Now what this means is that these are easy to test because you just let's say that there's a dependency between this one and this one. ... what you do is you just wrap a big test boundary around that one module around this one up here. And you're going to catch a lot of good stuff because there's lots of functionality that you're testing and really the caller, the person calling the module is going to have a simple interface to work from.

... raise your hands if you feel like you know your codebase less well than you used to. Yeah. This is a real thing. um because we're moving fast, because we're delegating more things, we end up losing a sense of our codebase. And if we lose the sense of our codebase, we're not going to be able to improve it. ... But then how do we make it so that we can move fast while still keeping enough space in our brains? I think that this is a way to do it because what you're doing here is not only are you thinking about creating big shapes in your codebase, big services.

What I think you should do is design the interface for these modules, but then delegate the implementation. In other words, these modules can become like gray boxes where you just need to know the shape of them. You need to know what they do and sort of how they behave, but you can delegate the implementation of those modules. I found this is really nice. I don't necessarily need to co-review everything inside that module. I don't necessarily need to know everything of what it's doing. I just need to know that it behaves a certain way under certain conditions and that it does its thing. So, it's kind of like, okay, I've got a big overview of my codebase and I understand kind of the shapes inside it, understand what the interfaces all do, but I can delegate what's inside. I found that has been a really nice way to retain my sense of the codebase while preserving my sanity.

And so you might ask, how do I take a codebase that looks like this and then turn it into a codebase that looks like this? How do I deepen the modules? Well, we have hopefully it's in here. Pretty sure it is. We have a skill and that skill is called improve codebase architecture.

</details>