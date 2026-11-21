---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=fTUinMqA1XQ
speaker: AI Engineer
tags:
  - multiplayer-software-factory
  - concurrent-delivery
  - autonomous-agents
  - software-engineering
title: 多人软件工厂：应对多智能体并发交付的挑战与架构方案
summary: Patrick Debois 探讨了多人和多智能体同时在同一代码库交付时的张力与应对方案。引入智能体使 PR 数量剧增，传统串行 CI/CD 演化为并发交付，需借助工作切分、推测性合并队列及意图冲突检测；同时组织协作层面引入任务看板对话、决策日志、风险分级审查及工厂平台团队。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Patrick Debois
companies_orgs:
  - Tessl
  - Helix ML
products_models: []
media_books: []
status: evergreen
---
### 多人软件工厂的背景与演进

欢迎来到关于多人软件工厂（multiplayer software factories）的分享。在这里，我将带大家了解当多个人和多个智能体在同一软件交付流水线上工作时，会产生哪些张力以及存在怎样的解决方案。

软件交付流水线当然不是什么新鲜事物，在 AI 出现之前就已存在。大家所熟悉的典型流程是构建、测试，然后等待发布以及合并进 main 分支。这基本上是一个串行流程，它帮助我们实现了交付的自动化并提升了稳健性。

与此同时，人们正在构建软件工厂。我把那些在个人笔记本电脑上、在各种系统上、在各自的编码智能体内部构建的工厂称为“单人工厂”（solo factories）。人们越来越多地使用多个智能体并通过智能体进行交付。现在，人类通常仍需做出决策，也必须执行合并，在某种程度上扮演着核心角色，几乎就像必须负责保留正在进行的工作的记忆等等。

我这里谈论的不是单人玩家，而是多人协作。这中间可能存在演进阶段：目前人们在笔记本电脑上单机操作；随后人们在各自的工厂内共享配置，比如上下文、技能以及执行循环——这几乎是当前许多工厂的现状；接着是多人工厂，人们在同一看板上、在同一代码库上同时协同工作。这就是我今天将带大家探讨的内容。

在这当中，左侧的张力在于所有人都希望合并到 main 分支；右侧则是看板上有很多人，他们必须协同配合。这就是本次演讲的两个组成部分。让我们先从第一部分——代码开始，看看如何让代码成为智能体协同工作的核心。

<details>
<summary>Original English</summary>
Welcome to our session on multiplayer software factories where I'll walk you through what the tensions are, what the solutions are when multiple people and multiple agents are working on the same software delivery pipeline. Software delivery pipelines are of course not new and existed before uh uh AI and you know we have the typical build test and then kind of wait for the release and the merge to go out into main. uh this is pretty much a serial flow and it has helped us automate and be more robust in the delivery. At the same time, people are building factories and I call them solo factories on their laptops on their kind of systems uh within their coding agents and increasingly they're using multiple agents and doing kind of delivery with agents. Now they often have to still make the decisions and they also have to do the merges and they kind of are a little bit of this central piece or almost like they have to keep the memory what they're doing and so on. I'm talking not single player of not solo player but uh multiplayer and there's probably a gradation in between currently people doing it on our laptops then people sharing their setups like their context their skills their loops within their factories pretty much the state of many factories out there and then the multiplayer factories of people collaborating at the same time uh in the same kind of uh kind of ticket board uh on their same code base And that's what I'll work you through today. Now on the left, the tension is everybody wants to merge into main. On the right, there's multiple people on the board and they have to collaborate and work together. So that's kind of the two parts of this talk. Let's start with the first part, the code, and how to make that like a central piece of agents being able to work together.
</details>

### 从持续交付走向并发交付

启动工厂或多人工厂时，你首先会注意到的现象之一，就是拉取请求（PR）的数量必然会出现激增，合并进来的 PR 几乎增加到了原来的十倍左右。这很好，因为我们的生产力提高了，完成的变更也更多了，但这也积累起了一些张力。

举例来说，我们有了大量的合并操作，必须确保它们互不冲突；如果不走运，智能体还会在人类身边绕圈子：一个智能体修改了某处，另一个智能体又把它改了回去。开启多人工厂时，这些冲突是真实存在的。

其中最显而易见的现象就是，我们开始为了发布等待更久。因为当我们合并一项变更时，所有其他 PR 都需要进行 rebase，并且通常要重新运行各自的测试，大家就必须等待；同时这也意味着，由于多人协作的原因，CI/CD 系统的运行速度大大变慢，成本也变得更高，不过成本只是副作用之一。

现在，PR 队列中堆积的不仅仅是功能特性。正如我提到的，还有我们必须解决的智能体故障（agent incidents），另外还有工厂自身的维护工作，比如改进技能、改进我们一直在使用的循环等等，越来越多的工作需要由我们来审批。

那么，我们为什么不能扭转这一局面，将并发从例外状态变成日常常规呢？这就是我所说的“并发交付”（concurrent delivery）——从持续交付（continuous delivery）迈向并发交付，并针对人类与智能体在同一代码库上协同工作来进行设计。

<details>
<summary>Original English</summary>
You know, one of the first things when you turn on a factory or multiplayer factory, you'll see that there's definitely an increase in pull requests, you know, it almost like a factor 10 uh of more and more pull requests landing. Uh that's good because we're being more productive. We get more changes done and but that also builds up some of the tension.

For example, um we have a lot more merges and they have to make sure that they're not conflicting and if we're unlucky, the agents also spend time of going rounds around us. Uh you know, one agent changing something then the other agent changing it back. These conflicts are real when you turn on a multiplayer factory. And one of the most noticeable things is we start to wait more for releases because when we merge a change all the other PRs need to rebase and they typically rerun their tests uh and you'll have to wait and at the same time that means actually your CI/CD system is becoming a lot lot slower because of that multi- thing and also more costly but that's a side effect.

Now the PRQ is kind of building up not just with features. There's also the agent incidents that we have to solve as I mentioned and then there's factory maintenance on their own like the improvement of the skills the improvement of the loops that we've been using all more more and more work that needs to get approved by us. So why can't we flip this from being this concurrency and it being an exception to becoming the routine? And this is what I call conc concurrent delivery and going from continuous delivery to concurrent delivery and design for people to work and agents to work together on the same codebase.
</details>

### 工作拆分与隔离执行

我们能做的一件简单事情是：不再仅仅让智能体一股脑地并行运行，而是更加聪明地处理这个问题。这就好比我们按单元来拆分工作——你负责这项任务，你负责那项任务。拆分的方式有很多种，我们可以划分说：你负责身份验证（authentication），我负责支付，我再负责其他部分；甚至可以使用 AST 图来判断哪些部分可以很好地进行拆解。

接着，我们可以让智能体进入更细的粒度，明确到具体的文件、函数，甚至深入到某些文件中的特定按键操作来共同完成。这是一种在真正开始编写代码之前对工作进行更多切分的方式，也是规划变更的一种更好途径。

一旦开始规划并实际执行该计划，就像在 Scrum 看板上操作一样，你会申明“我来负责处理这个”，智能体也会记录并申领工单，表明自己要执行那个工单，这样其他智能体就无法在同一时间介入。同时，它还会声明自己将要修改哪些文件和变更。这有助于其他智能体在规划和执行过程中知晓情况，避免产生重叠。

为了确保它们能够持续执行，很多人使用 worktree 来进行相互隔离。从更广的维度来思考，其实可以做更多维度的切分。你基本上是在为智能体界定并冻结一个独立环境：为它们提供独立的机器，为它们提供特定切片的上下文，为它们提供锁定了的独立 API 版本；甚至数据库也能获得快照和测试数据，对外部世界采用数字孪生（digital twins）等方式确保一切都被 mock 起来，使它们在开展这些工作时不必承受外部世界的任何影响。

<details>
<summary>Original English</summary>
Now one of the simple things that we uh can do is instead of just running and running agents just in parallel we can get smarter about this uh almost like splitting up the work like we would do with units like you get to do this task you get to do that task and there's different ways of splitting this in a way that we can say well you work on authentication I work on payment I work on other parts and we can use even the ASD graph to determine which pieces are like able to split quite well and then we can go have the agents go on more granular level and they would do like hey this file this function and even they would go on certain keystrokes like in certain files doing together. So this is a way of kind of dealing with kind of more uh splitting of the work before you actually do uh the actual coding. This is a better way of planning the changes.

And then once uh you start planning and you start actually executing the plan uh much like you would do on your uh scrum board, you would say I'm going to take care of this and the agent writes and says it claims the ticket. It says I want to do that ticket. So no other agent can actually step in at the same time. And it also announces which files and which changes it's going to make. So this is something that is helpful for other agents to see that they're not starting to overlap during the planning and the execution.

Now to make sure that they can keep executing um a lot of people use work trees to kind of separate them. When you kind of think about this broader there is a lot more splitting that you could do. You basically are phrasing the world of an agent. You give them their own kind of machine. You give their their own phrase of the context. to give them their own version of the API that's being locked and even the database gets their snapshot their test data and even outside world like digital twins and uh kind of making sure that everything's mocked and that they can do these things without having to deal with any impact of the outside world.
</details>

### 冲突协商、语义冲突与推测性合并队列

当两个智能体在工作中发生冲突时，有几种应对策略：
- 它们可以开始相互等待，按先后顺序依次进行；
- 它们可以在等待后重试，表示“好吧，我先等待并重新入队，直到它完成”；
- 或者它们可以开始更改并优化计划，例如“你负责这个，我负责那个”，这本质上是一种重新协商。

也就是说，它们在执行过程中实时调整计划，以确保彼此不发生干扰。

遇到冲突时，你可以选择重新运行。在当前的 Git 工作流中，当你合并并发现冲突时，你会怎么做？通常是重新运行，看看重试后能否合并，这往往就是我们传统的 PR 变更方式；或者，你也可以让智能体代劳。这样一来，智能体不仅能按代码行进行合并，还能基于函数级别进行更智能的合并；随后智能体或许能修复合并问题，省得你再做一次。最终，它甚至能开始预判变更的到来——意识到“这个智能体很可能会修改这里，我已预见到这一点”，并在同一时间主动调整自己的代码。这是以并发思维替代串行变更思维。

现在可以看到的一点是，智能体已经被优化来处理合并事务，比如代码层面的合并很直观。但是，如果两个变更同时合入会怎样？假设在这种情况下，你修改了计算发票总额的函数，将单位从美元改成了美分；与此同时，另一个 PR 修改了报表输出逻辑。这两个合并在代码层面上完全可以一致合并，测试也能通过，但两者的意图（intent）却存在分歧——报表并不希望以欧分或美分的形式呈现。因此，它们在代码上没有冲突，但在意图上产生了冲突。我们可以让智能体去审查跨多个合并之间的意图是否依然一致，并在必要时向我们发出警告或相应调整 PR。

如果准备开始合并，各 PR 均符合合并条件，但如果其中一个合并失败了会怎样？通常情况下，所有其他 PR 都必须 rebase 并做重复返工。处理此类合并队列（merge trains）有一种更好的方式，即借助“推测性合并队列”（speculative merge trains）的概念：它会审视所有进来的 PR，观察哪些 PR 彼此兼容，并预先按两两配对进行检查；当某个 PR 正在合入、而另一个无法合入但其他 PR 依然可行时，流程就会走得更快，因为合并队列中所有其他能够通过的 PR 已经先行通过了。

这些只是处理合并、冲突、审查以及更优规划的新策略范例。我认为总体而言，一层新的基础设施层正在到来，你可以从各供应商那里看到这一点：这是一种全新的开发者基础设施，合并将以不同的方式处理，现在有了分析能力，有了更完善的规划，有了适用于各项事务的更好工具，这正是我们目前正在构建的方向。很多现存工厂仅仅是我们借助 CI/CD 所做的美化版执行循环，但并发量只会不断增长。

<details>
<summary>Original English</summary>
Now when two agents do collide during the work there's a couple of strategies they can either start like waiting for each other um one after the other they can retry after the wait they can say like okay I'm going to wait but I'll recue and I'll wait until it's done or they can start changing and optimizing the plan like you do this I do that and that's renegotiation uh in the end so they're changing actually the planning while they're doing the execution to make sure that they don't interfere with each other.

Now on a conflict you could rerun it. Um and within get you're merging today and you say okay there's a conflict. What do I do? You rerun and see if it merges on the rerun which was typically our PR uh change or you could just kind of make sure that the agents do that for you instead. So they can see whether they can merge instead of just by code lines. they can merge by function and it becomes smarter and then the agent maybe can fix [clears throat] the merge so you don't have to do that again and ultimately it can even start seeing changes coming so hey this agent is probably going to change this I'm going to see this coming and I'm already kind of adapting my code uh at the same time so this is thinking in concurrency instead of being kind of serial in the changes

now one of the things you can see is that you agents have been optimized to merge stuff, right? Like with the merging of code, this is clear. But what if two changes land at the same time? In this case, you're calculating and changing the function of calculating the the total for an invoice and say it's not just in dollars, but it in dollar cents. Now, at the same time, there is another PR that changes the fact of reporting out. Now two mergers that consistently could merge with the test succeeding but at the same time it was a different intent. The report don't want to have it in euro cents or in dollar cents. Right? So they're not conflicting in code but they're conflicting on intent. So we could have agents actually look at the intent whether they're still consistent across the multiple mergers and warn us or change the PR accordingly.

Now, if you want to kind start merging, um the PRs are able to merge, they're good to merge. Um but what if one of those mages uh merges doesn't uh merge well, right? Then you'll have typically rebase all the others, they'll have to do rework and so on. Now, there's a better way of dealing with these merge trains is by looking uh in a concept called speculative merge trains. And it looks at all the PRs coming in and it sees which ones are compatible with each other and it kind of already checks them in pairs. And then it says like when that is landing and this one isn't landing, but you could still do the others, it goes faster because all the others that can go through already go through in the merge cube.

Uh these are just some examples of kind of new strategies of dealing with merges and conflicts and reviews and better planning. I think in general there's a new kind of infra layer coming and you see that almost from the vendors you know it's a new developer infrastructure mergers are going to be handled differently there's now an analytics there's now a better planning there's now a better tool for anything and that's kind of what we're building up uh right now a lot of the factories are just glorified loops as we would do with the SCD but the concurrency will only increase
</details>

### 人类与智能体的协作：对话与工单演进

我说过这件事情还有另一面：不仅是智能体在工作，人类也在一起协同。通常的转变在于，大家在同一个任务看板上协作，所有人类都能看到即将到来的变更以及正在执行的任务。这带来了可见性；而在单人工厂中，这一切都是由你独自完成的，不会存在一个大家共同协作的中心看板。

现在，所有任务都需要你的关注，而关注度往往是最容易耗尽的，所以我们也希望减少智能体频繁呼叫人类所带来的注意力消耗。这是多个智能体同时工作带来的副作用。

非常好的特性之一——也是非常有趣的现象——是智能体可以加入你的聊天群，这是一种截然不同的编码方式。它不再是你单独去给提示词，而是你将智能体拉入对话之中。这种方式非常强大，因为智能体不仅从你这里捕捉线索，还同时从你的团队成员那里获取信息。

智能体实际在做的是根据所有输入来细化完善工单。这极其有效，因为你不仅能获得智能体之间的对抗性审查，还能在对话进行期间由多个人类针对同一个工单共同提供输入。

智能体非常擅长的一点，是向你提出问题以引导确认，而不是翻来覆去地询问所有事情。非常有帮助的一点在于，它能澄清测试是什么、应该做什么、必须满足哪些需求。工单实际上变得几乎类似于编码智能体中的“计划模式”（plan mode），但现在它成为了看板内共享的功能，用于审视所有需求。

更强大的是，参与者不必仅仅局限于工程师。可以回想一下过去：销售、市场、支持部门向工程团队提交工单，工单被挂在看板的某个地方，大家只能等待工程师处理，这往往需要数周时间。现在，我们在 Tessl 的工厂中所看到的，是大家直接在组织内部聊天沟通，智能体就在其中。非工程人员不需要频繁亲自构建代码；此前他们可能会尝试 vibe coding，但 vibe coding 的问题之一是不符合工程规范。

而在多人工厂中，大家使用的是同一套流水线、相同的知识、相同的技能和相同的执行循环，从而已经融入到了工程本身的流程当中。因此，他们可以进行实验，完善功能特性，甚至构建功能；以往我们需要等待，现在他们可以直接启动，工程人员再进行审查。这是一种非常强大的协作流程，让每个人都参与进来，并置身于同一个多人工厂的工作流中。

<details>
<summary>Original English</summary>
now I told you there was a flip side to this there's also the humans working together, not just the agents. And the typically the change is that you're working together in one kind of task board, right? And all the humans are being able to see what changes are coming, what tasks are being done. And this creates the visibility where in your solo factory, you would have that doing that all alone, but it wouldn't be a central kind of board that you're working on. Now, they all need your attention, and that's probably the easy part, right? So we want to reduce also that attention uh from the agents having to call you all the time. So this is a side effect of having multiple agents working at the same time.

Now one of the nice features is and uh it's been kind of interesting to see that agents can join your chat and this is a different way of coding. It is not you prompting but it's you kind of pulling an agent into a conversation. Uh and that's really powerful because the agent is picking up clues not just from you from your team members at the same time. And what it's actually doing it is refining the ticket from all the input. And that is really powerful because you actually not only had like adversarial review by agents, but you also get multiple input by humans on the same ticket while during the conversation.

And what it's really good at is prompting you with questions instead of having to ask everything over and over again. So one thing that helpful is that it clarifies what is the test, what should it do, what are the requests uh requirements that it needs to do. And the ticket actually becomes almost like a plan the plan mode in your coding agent but now as a share feature within your board um of looking at all the requirements.

Now what's even more powerful is that it doesn't only have to be engineers. Think of this as in the past sales marketing support they were kind of filing tickets to the engineering that would get somewhere on a board and they all have to wait until an engineering comes that could have taken weeks. Right now what we see in our factory at Tesla is that people are just sharing and doing a chat within kind of the uh organization and the agent is there. Now they don't need to build um the uh uh the code all the time and before [clears throat] they were maybe doing vibe coding but one of the problems with the vibe coding is it didn't fit according to engineering practices. Now with a multiplayer factory people are using the same pipeline the same knowledge the same skills the same loops to actually already fit into that flow of engineering itself. So they can experiment, they can refine the feature and they can also even build the feature where before we would wait they can just kickstart it and engineering refused that. That's a very powerful flow of getting everybody on board and being in the flow of that one multiplayer factory.
</details>

### 人机回退机制、决策日志与风险分级审查

有时智能体在执行过程中会产生不确定感；你可能也会有类似感觉，觉得工厂里的工单模式有时较慢，而你希望进行快速迭代。当智能体卡住时，有一种混合式的处理方式。Helix ML 提出了一个非常有趣的理念：当智能体卡住时，它实际上会启动一个新的编码 IDE，其中包含智能体当时正在处理的完整上下文；你作为人类可以介入协助，在拥有所有可用上下文和全部可用文件的情况下帮助智能体理清思路；当你做出了正确的选择和实验后，再将其交还给智能体和工厂继续运行。这是一种在个人编码智能体的快速迭代与工厂化流程之间寻找平衡的优良方式，智能体也可以借助它来澄清疑问并寻求帮助。

我们真正想做的是减少智能体必须做出的抉择。非常有效的一点是，它向我们提出供决策的选项，而不是抛出“我该做什么”这类开放式问题。在各类编码智能体中也能看到这种情况：它提供几个选项供你选择，然后去执行。这非常强大，通过呈现选项，减少了一直需要向智能体交代该怎么做的高负荷。当然人类可以覆盖这些选项，但这确实是多人协作的一大亮点。

人类做出的每一项决策实际上都会记录到账本（ledger）上。这类似于你在本地编码智能体中拥有的上下文；但在多人工厂中，这些内容被共享记录在决策日志（decision log）中，既可供智能体使用，也可供人类查阅追溯，比如谁在何时做出了什么决定；当在接下来的会话中使用该上下文时，同样可以对其进行查询。

我们希望变更保持小巧，因为庞大的变更缺乏可读性。因此，尽管我在开头提到可以针对避免智能体冲突进行优化，但还有另一件事必须考虑，那就是人工审查：人类能够审查多大规模的变更？不过，你可以在多个主合并队列中构建独立的 PR，以便人们对这些内容进行快速审查。

许多人关注自动化审查以减少 PR 审查次数。第一部分通常是减少故障，这很好：我们希望提供更好的上下文、更优秀的工具，并在代码提交给我们之前由对抗性智能体进行检查，这是通过提高质量来降低风险的良好方式。

与此同时，我们正在优化以便能直观看到智能体做了什么：要求提供界面操作截图、视频、测试证明等一切有助于审查者的材料。

最终界限究竟在哪里？有人告诉我他们不再查看代码了，我问他们这对上线生产的影响是什么。有些文档的影响有限，有些系统没有真实客户，其影响确实不大；但如果深入思考，你实际上是在根据自身能够承受的风险来做筛选：
- 一些测试会表明，如果是文档部分的改动，可以直接推进；
- 如果是影响面更大的变更（例如身份验证相关），则需要人类进行更多审查；
- 有时也存在折中方案：该功能可以直接发布，通过渐进式发布来检查输出是否有错误。

因此，除了针对质量进行优化并降低故障发生的可能性之外，还可以从风险的角度进行考量。当代码离开生产环境或在生产中运行时，你也需要考虑如何缓解风险：如果可能造成数据丢失，是否有快速恢复策略？或者考虑当一个节点发生故障时能否快速回滚？这些同样是架构层面的决策。当出现问题时，必须让恢复或修复的代价足够低廉，这对于处理 PR 审查中的风险至关重要。

<details>
<summary>Original English</summary>
Now sometimes the agent while executing is unsure and you might have the same feeling that sometimes the ticket mode within a factory is slow and you want to do fast iteration. Now there's a way to do this hybridly when for example your agent is is stuck. Uh there was a very interesting ID from Helix ML where when your agent is stuck is actually starts a new kind of coding IDE with the exact context that the agent was working on you as a human almost jump in uh to help the agent figure out like with all the context available with all kind of the files available and then when you made the right choices when you did the right experiments you hand it actually back to the agent and the factory to continue. So this is a nice way of finding the middle ground between a personal coding agent fast iterations and still doing the factory uh and the agent can use it as well to kind of clarify and help uh and ask for help.

Now what we really want to do is reduce kind of the choices uh that it has to kind of make and what is really powerful is that it represents actually questions to us for decisions not just what should I do and open questions you know you see that in coding agents as well it gives you a couple of options that you can choose for and then it goes off this is really powerful and it is less trained on like having to tell the agent all the time what to do by presenting options there as well. Of course, you can override, but this is really a powerful multiplayer thing.

Now, every decision that people make actually goes onto a ledger. This is like your context locally maybe that you have in your coding agent. But if you are in a multiplayer factory, this is shared somewhere on a decision log and that can be used either by agents, it could be used by humans to find and you can trace things back like who made what decision uh and when that context is being used in the next session, you can also query that as well.

Now we want that to be small because big changes uh they are not very readable. So while I said in the beginning you could optimize for agent not being conflicting. There is also another kind of thing you have to think about which is the human review. How much change can a human review but you can build like separate Pars in multiple main merge trains for people to do fast reviewing of those things.

Now a lot of people are focused on kind of you know when the PR and we want to reduce the number of PR reviews is that there is some kind of automated review. Now the first part is typically to reduce the failures which is great right like we we want to provide better context better tools we have adversarial agents look at the code before it comes to us that is a good way of reducing kind of the risk uh by it being better quality now at the same time we're optimizing that we can actually see what it did we are asking for screen flow uh shots for videos for proof for testing all the things that could help a reviewer and then ultimately how far do you go several people tell me like hey I'm not looking at the code anymore and I asked them okay you know but what is the impact of this going to production some documentation that is limited impact maybe you know some don't have real customers which is also great right like the impact is not a lot but if you really start thinking about what you're doing is you're selecting by what risk you can take. So some of the tests will kind of say well if it's maybe in the documentation part you can go ahead if it's like a a more impact fail change like within authentication you kind of do more kind of review by human and sometimes there's a middle ground hey this feature can just roll out we'll check what the output is whether there's any errors like gradual releases. So instead of only optimizing for quality and reducing of the likelihood, you also kind of have a way of looking at it from a risk perspective. And when it moves out of production, you know, you can also see how you can mitigate the risk, right? Because if the impact is that you uh lose data, do you have a fast restore strategy? uh or you can think about this like what if one node fails or can I fast roll back those are architectural decisions as well. So what you want to do is when things go wrong you want to have it being cheap to restore or to fix and that is important in not only optimizing but there's multiple ways of kind of dealing with the risk on the PR review.
</details>

### 信息扩散、工厂团队与未来展望

在多人工厂中工作，一件很有意思的事情是：过去大家经常线下交流，例如我个人是远程办公，而团队大部分成员都在伦敦的集中办公地。他们聚在一起有很多面对面的讨论，身处远端的我有时的确很难跟上所有的变更动态。

而当你开启了多人工厂，所有人都需要跟上节奏。产生的代码如此之多，市场、支持等其他部门可能无法跟上，他们需要用符合自己领域语言的方式来获知发生的变更。因此，沟通与变更的辐射传递（radiating change）在多人工厂中是一项非常关键的特性。你如何针对自己的领域、自己的理解以及所负责的工作部分来跟上进展？

简而言之，你可以进行大量的自动化，并会使用大量的技能、上下文以及更优的改进；而人类则留给处理异常情况。我希望大家思考的方式是：尽可能将能自动化的环节自动化，但确保能够路由给人类以做出正确决策。

随着整套基础设施以及协同工作模式的建立，一支新的团队正在逐步成型——这就像“工厂团队”（factory team），类似于此前管理 Kubernetes、集群或云平台的平台团队。但现在，他们管理的是编码智能体以及协同工作的编码织料（coding fabric）。他们确保技能的归属权明确、上下文保持最新，确保各组件正确连接，并负责整座工厂自身的维护与监控。

概括来说，主要体现在两个维度：
- 智能体在代码库中更多地协同工作，压力随之增加；
- 人类也与智能体以并发方式更紧密地协作，并在同一时间交付更多产出。

为了适应这一切，需要发生许多转变。我们目前正在探索的尝试之一，是不仅有编码智能体，不仅有看板上操作的人类，现在还有个人智能体（personal agents）参与看板工作。它们会代你做出决策，也会向其他智能体提供解答。这是一种全新的构建方式，也是一种将你在工厂中所做任务进行委派的新方式。

因此我的建议是做好准备，我们目前尚未完全达到那个阶段。编码智能体在单人工厂阶段迈出了很好的一步；而多人工厂将给智能体编码以及组织协同带来全新的动态。

非常感谢大家的聆听。如果需要幻灯片，可以通过 LinkedIn 私信联系我，我很乐意向大家提供以换取一些反馈。大家当然也可以体验 Tessl 工厂，我们正在那里实现并改进面向多人模式的循环、工厂和技能。我也在 concurrent.cd 网站上分享了相关研究，汇集了大家共同解决并发问题的工具与技术。非常感谢大家的收听，希望大家今天学到了新内容，欢迎留下评论，我很乐意查阅并回复。非常感谢！

<details>
<summary>Original English</summary>
Now, one of the funny things when you work in a multiplayer factory is that um you know before people were chatting and I personally for example work remote where most of the team is in a central place in London. Now they get together they do a lot of chats and so on and me sometimes from remote I had a hard time catching up what has changed. Now, when you turn on the multiplayer factory, everybody needs to keep up, right? There's so much code being produced that maybe marketing support and other places can't keep up. They need to have a translation in their changes that have happened in their language. So, communication and radiating change is actually a very important feature in a multiplayer factory. How do you keep up within your domain within your understanding for your part of the job?

Now in a nutshell you can do a lot of automation and you will use a lot of skills uh and that like context and better improvement uh on those pieces and you kind of reserve the people for the exceptions and that's the way that I want you to think about is automate what you can but make sure you are able to route to a human to make the right decision

with all that infrastructure with all those kind of ways of working together. Um there is kind of a new team that is forming which is almost like the factory team uh similar to a platform team that was dealing with a kubernetes or with a cluster or with the cloud but right now this is they are dealing with the coding agents and the coding fabric of working all together. They make sure that who owns the skills the context is up to date. they make sure that things are connected to the right pieces uh and that the whole factory also itself is being maintained uh and being monitored as well.

So this is a nutshell. There's a lot more to it, but this was in a nutshell two things like the pressure is building up on agents working more together in the codebase and then the humans also kind of working with the agents more and more together in a concurrent way and delivering more output at the same time. And for that there needs to be a lot of change. Now one of the things that we're playing now with is they're not just the coding agents. They're not just the people that do things in the board. Now they're being those personal agents and they will work in the uh board. They will make decisions for you. They will provide answers to other agents as well. This is a new way of building. This is a new way of kind of delegating some of the tasks that you are doing in the factory.

So my advice is brace yourself. We're not there yet. like the coding agent were a good step on your solo factories. Multiplayer factories will bring new dynamics both to the agents coding and both to the organizational working together. And that's it and thank you very much for listening. You can kind of find the slides by asking uh to me in DM on LinkedIn. I happily send you in exchange for some feedback. Um and you know you can of course try the Tesla factory where we implement and uh are working on kind of loops factories and skills uh for you uh being in a multiplayer mode and I'd also uh shared the research at a site on concurrent.cd where I find like people and uh tools and techniques that people are solving uh this concurrency all together. Thank you very very much for listening and I hope you learned some of the new things today and feel free to leave uh some comments and I'll happily have a look and respond to that. Thank you very much.
</details>