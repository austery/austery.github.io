---
author: Latent Space
date: '2026-08-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5lFD-34dhqE
speaker: Latent Space
tags:
  - recursive-self-improvement
  - agent-architecture
  - systems-engineering
  - llm-harness
title: Exo：让 AI Agent Harness 具备自我修改与日志可见性，走向完全递归自我提升
summary: 本期访谈中，来自加州大学伯克利分校的博士生 Alex Krentsel 详细介绍了 Exo 这一新型 AI Agent Harness 架构。Exo 通过将执行器、Sandbox 与 Harness 隔离，并赋予 Agent 对自身代码和日志的完全读写权限，实现了真正的运行时递归自我提升（RSI）。同时，探讨了该系统与 Lisp、Smalltalk 等经典编程语言理念的相通之处。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - UC Berkeley
  - Braintrust
  - a16z
  - Netlify
products_models:
  - Exo
  - OpenClaw
media_books: []
status: evergreen
---
### Exo起源与核心理念

**Shawn**: 好的，我们现在在远程录音室里，和来自 **EXO** 项目、同时也是**加州大学伯克利分校**（UC Berkeley）的 **Alex Krentsel** 进行交流。欢迎你的到来。

<details>
<summary>Original English</summary>

**Shawn**: Okay, we're here in the remote studio with Alex Cransel, I guess, of EXO, but also UC Berkeley. Welcome.

</details>

**Alex**: 非常感谢，很高兴来到这里。

<details>
<summary>Original English</summary>

**Alex**: Thank you so much. Happy to be here.

</details>

**Shawn**: 我之所以录制这一期，是因为当你在我的社交媒体时间线上出现时，我就觉得必须录一期。我之前甚至不知道你已经公开露面过了。这正说明了 **YouTube** 上的内容生命力有多持久。但我实际上已经看过你的演讲了，只是当时没有在 **OpenClaw** 上注意到你的名字。

<details>
<summary>Original English</summary>

**Shawn**: The reason we're recording is because I had to when you showed up on on my timeline. I I didn't know that you had already showed up before. This is this goes to show you how much uh persistence there is on YouTube. But like I actually had watched your lecture and then didn't register your name on OpenClaw.

</details>

**Alex**: 那太酷了。是的，也许我应该多说几次我的名字，或者把它写在幻灯片里。当时我太专注于讲解架构本身了，完全没想着去推销自己。

<details>
<summary>Original English</summary>

**Alex**: That's cool. Yeah, maybe I probably should have said it a few more times or put it in the slides. I was so focused on just talking about the architecture. I didn't go to pitch myself.

</details>

**Shawn**: 是的。但也许也可以把你的照片放上去，或者提一下你的其他工作。不过，这都是一码事。最近你和我们节目之前的两位嘉宾——**Martin Casado**（来自 **a16z**）和 **Ankur Goyal** 一起合作。当我和 Martin 在播客里聊天时，他提到自己正在和你一起写代码。他很想写代码，而我当时还在调侃说这又是一个假装会写代码的风险投资人（VC），问他到底在忙什么，结果现在你们就把这个项目公布了。所以，我想把时间交给你，先聊聊 Exo 的故事，然后我们再回溯到你想要分享的其他背景。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. But also like maybe like your face on there, but also you know just like other other work. But uh you know that's all that's all of a of a piece. Um most recently you you showed up uh working with two of our former guests on Leon Space uh Martin Casado and Anker Goya. When I actually talked with Martin on the podcast, he actually said that he was hacking away with you and he didn't like because I he was like, I want coding so much and I was trying to call out like you know this this VC pretending that he codes. I was like you know what are you doing man and he was working on this and now you've announced it. So I just wanted to give you the floor to talk about the exo story and then we can work our way back to whatever other background that you want to do.

</details>

**Alex**: 好的，没问题，谢谢。首先我想说，是的，我一直和 Martin 以及 Ankur 一起构建这个项目。正如你所知，他们都是非常出色的系统思想家。Martin 拥有计算机科学博士背景，实际上他的博士导师和我现在的博士导师一样，都是伯克利的 **Scott Shenker**。所以，这就是我们共同的学术传承。

<details>
<summary>Original English</summary>

**Alex**: Yeah, for sure. Thank you. I mean, I'll start by saying, yeah, I I've been building this with with Martine and Encore. They're both really excellent systems thinkers. As you might know, Martine's background is in a PhD in computer science. Actually, advised by my adviser, my PhD adviser, Scott Anker, at Berkeley. So, that's kind of our shared lineage.

</details>

**Shawn**: 共同的学术传承，没错。当我还在 **Netlify** 工作的时候，Scott 也是我们的董事会成员。当时我正在学习虚拟化网络以及所有这些概念。

<details>
<summary>Original English</summary>

**Shawn**: Shared shared lineage. Yeah. He was my board member when I was working at Nellifi and I was working I was learning about uh you know, virtualized networks and all those things.

</details>

**Alex**: 是的。我们都拥有系统背景。我的背景完全在系统领域，稍后我会详细谈到这一点。但首先简单介绍一下 Exo，以便我们处于同一认知水平。简而言之，**Exo** 是一个完全**递归**的 AI Agent。它能够在运行时安全地修改自身的方方面面，以便更好地完成它正在处理的任务。这种能力是由一个非常精简但极具主见的**套件架构（Harness Architecture）**实现的。该架构将当今 AI Agent 的不同部分拆分为可以安全隔离的组件，从而可以安全地演进。我们可以进一步讨论它是如何做到的，但你应该把 Exo 看作一个真正实现了完全**递归自我提升（Recursive Self-Improvement）**的 Agent。

我认为，这在今天之所以能够实现，是因为在我们看来，我们正在进入机器学习技术栈的一个新阶段。直到最近，我们还一直非常专注于让**模型**本身变得更好。当我们说“模型”时，指的是权重。你通过大规模预训练来训练模型，然后对其进行微调，以使其擅长某些特定任务的推理。但我认为，过去一年向 Agent 的转变，让我们更加意识到力量其实存在于 Harness（套件）、工具链以及我们为大语言模型（LLM）大脑提供的“身体”中。

现在的转变是，我们开始意识到，当我们微调这些 Harness 时，Agent 在特定任务上的表现会变得非常好，或者效率更高。也就是以更少的 Token 调用、更低的使用量来降低成本。成本是目前非常大的一个痛点，因为前沿模型随着体积变大、部署服务难度增加、需要更多 GPU 等原因，正变得越来越贵。

这个项目源于我过去一年左右在伯克利对**发现系统（Discovery Systems）**的研究，也就是 AI 驱动的发现。这个项目源自伯克利的 Sky Lab，叫做 Sky Discover。它是一个尝试优化和改进系统的外层循环。而让我非常好奇的是，如果把这个概念推向极致会怎样？如果你有一个外层系统在优化一个内层系统，而你又想优化这个优化过程本身，你就需要一个更外层的循环，这就导致了无限递归。我认为解决这个问题的唯一方法就是把这个循环折叠起来，让系统本身负责改进自身，这就是我所说的“折叠循环”。这与由一个外部观察者在系统运行时观察并修改它有很大不同。我希望系统能够在运行时改变自己。这就是 Exo 的核心论点。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. We're kind of come from systems backgrounds. My background is fully in systems and I'll talk more about that later. But just briefly to introduce EXO so we're all on the same page. In a nutshell, Exo is an agent that's fully recursive. So it's able to safely edit all aspects of itself at runtime to kind of get better at the task that it's working on. And it's enabled by this very kind of minimal but opinionated harness architecture that splits out different pieces of what an agent is today into components that can be safely isolated from each other and thus safely evolved. We can talk much more about how it does this, but you should think about it as an agent that really does full recursive self-improvement. Um, and I think it's really enabled today by the fact that we're we're entering a new layer in the like ML stack in my mind where up until recently we've still been really focused on trying to make models better at what they do. And when we say models, we're talking about the weights. You are training the model. First it was large pre-training runs. Then it became find kind of applying fine-tuning to these models to get them good at a particular task in their thinking. I I think the shift over the last year to agents has made us much more aware of the power that lies in the harness, the tooling, the body that we provide to the brain of the LLM. And the shift that's happening now is we're really entering a space where we're starting to realize that as we tweak these harnesses, they're get really good at particular tasks, either better at doing them or more efficient. So doing them with less token calls, less usage, driving cost down. Costs are a huge concern right now because frontier models keep getting more and more expensive because they're larger, they're harder to serve, they require more GPUs, etc., etc. And so the project came from I've spent the last year or so of my research at Berkeley on discovery systems. So AIdriven discovery, right? This project come out of the sky lab at Berkeley called Sky Discover. And it was this outer loop that tries to optimize and improve in a system. And what I got really curious about was how do we take this to its extreme? You have some outer system that's optimizing some inner system. What if you want to optimize the way you're doing your optimizing then you need some outer outer loop and it's this infinite recursion out and the only way I think out of that is to collapse that loop down and make it so that the system itself is responsible for improving itself which I'm calling to collapse the loop. So it's very different than having an outer observer that's looking and trying to make changes to the other system as it's running. I want the system to be able to change itself at runtime. And this is the the kind of thesis for Exo.

</details>

### 递归自我提升机制

**Shawn**: 是的。我想在这里补充几点评论。首先意识到这一点的可能是 **OpenClaw** 的研发人员，对吧？他们当时认为，Harness 应该自我修改以添加你所需的任何功能，但在你设想的机制中，它还不是完全递归自我提升的。其次，你已经做过一次 OpenClaw 的讲座，我会在描述栏里附上链接，大家应该去看看，如果你愿意的话，我们今天也可以涵盖其中的一些内容。第一点评论是，很多刚接触这个概念的人看到系统自我修改时会感到害怕，比如“天哪，它在没有我允许的情况下修改了自己”。这是我的两个评论。你想从哪里开始聊都可以。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. And I'll maybe add a couple pieces of commentary here. Uh the first people to realize this was probably the PI openclaw people, right? Uh where they were like, well, the the harness should modify itself to to add whatever capability you need, but it is not fully self-reursive in the way that you envision it. Second of all, so so we can go into that and you've already done an open call lecture which which I'm going to link to in in description that people should see and we can cover a bit of that if you want, but the first comment is people who aren't used to this are like scared of code modifying itself because they're like wow it just modified itself without me asking. So those would be my two commentary pieces there. Wherever you want,

</details>

**Alex**: 这两个点都很好。让我分别谈谈。OpenClaw 是在今年二月份左右出现并迅速流行起来的。我认为你是对的，OpenClaw 真正发现的是如何制造一个让人感觉神奇的 Agent 系统，因为它可以自适应你的工作流。它具有极强的适应性。但你在 OpenClaw 中看到的大多数自我修改，都是在非运行时的开发阶段。比如，你作为人类程序员运行它，它会说：“嘿，我认为我们这里需要这个工具，”然后它会写下这个工具，而你在下一次运行它时会使用这个工具。而在 Exo 中，我们希望它在运行时进行修改。

另外，你提到了对于自动生成代码的恐惧。我认为在没有保护措施的情况下，这种恐惧是完全合理的。这也是为什么 Exo 的架构被分为三个不同的部分：首先是**执行器（Executor）**，其次是 **Exo Harness（Exo 套件）**，第三是**沙箱（Sandbox）**。我们必须把 Harness 和沙箱隔离开来。沙箱是运行各种工具的地方，也是可能发生破坏性事情（如删除文件或发送错误 API 请求）的地方。而 Harness 运行在沙箱外部，负责监控系统的演进，并管理状态、存储和机密。我们认为，这种物理上的解耦——将执行策略的模块与与外部世界交互并可能失控的模块分开，是让这种系统能够安全自我修改的关键。这也是它的核心所在。

关于 OpenClaw，它非常注重“技能（Skills）”这个概念。它在某些特定节点允许你插入额外的技能，但这从根本上改变了技能在工作中的定义机制。

<details>
<summary>Original English</summary>

**Alex**: they're great points. Let me touch on both. So OpenClaw came around and took off in really took off in February. And I think you're right. The thing that OpenClaw really discovered was how to make an agentic system that feels magical in that it kind of adapts to your workflow. It is adaptable. But a lot of the self-improvement, self-modification you see in OpenClaw is offline. So you run it, it's like, oh, I think we need this tool, it writes the tool, and then you use it the next run. Whereas with Exo, we want it to happen at runtime. And you also mentioned, yeah, the fear of having something write its own code, and I think without guards that is a totally justified fear. And this is why the architecture of Exo splits out into these three separate components. So you have the executor, the exo harness, and the sandbox. And you have to isolate the sandbox, which is where the tools run, which is where bad things could happen, deleting files or making bad API requests, from the harness itself, which is running outside of that and manages the evolution of the system and manages state and storage and secrets. And we think that physical separation of the thing executing the policy from the thing interacting with the outside world and potentially doing bad things is how you make this safe to do. That's really the crux of it. With regards to OpenClaw, it's very focused on this notion of skills. It has certain points where you can insert additional skills. It has changed the very machinery of what skills are for your job.

</details>

### Exo架构设计详解

**Shawn**: 是的，还有构成它的策略（Policies）。如果我们在进行屏幕共享，我们可能就会展示一些图表。现在也许是引入架构图的合适时机。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. And the policies that make it up. Uh I I was just wanted to if if actually we should have been screen sharing we might we might have used uh some charts that this might be appropriate time to pull up the a little architecture diagram.

</details>

**Alex**: 确实。让我把它展示出来，这样更好讲解。如这里所示，这是我关于自主系统设计原则演讲中的图表。那场演讲重点深入剖析了 OpenClaw，因为它在几个月前刚刚发布。当我们看这张图时，可以看到右侧是**执行器（Executor）**，这是 LLM 的核心所在。它接收一组策略，并利用这些策略去驱动系统。这里有一些核心原语。

左侧是 **Exo Harness**，这是系统的控制中心。它包含了两个至关重要的组件：**事件日志（Event Log）**和**状态库（State Library）**。事件日志以极其结构化的方式记录了 Agent 运行过程中发生的一切，包括所有的工具调用、Token 使用、状态转换等。状态库则保存了 Agent 在不同任务中的知识沉淀。

底部是**沙箱（Sandbox）**，也就是所有的工具真正执行的地方。在这里，我们提供了安全且隔离的运行环境。如果把红线画在所有组件的周围，可以说它们全都是可以被 Agent 本身在运行时修改的。

<details>
<summary>Original English</summary>

**Alex**: Totally. Let me actually bring that up. It'll be easier to talk through. So just in in here we can see and this is again from the my lecture on principles of autonomous system design which was really a deep dive on openclaw because it came out uh you know a couple months ago. So as we look at this next to this, I'd say I'd put red lines around all components here and say they are all changeable by the agent itself.

</details>

**Shawn**: 是的，这是该系统最极致的版本。你刚才想让我谈的另一个问题是什么？你是想要显式切换还是隐式切换，这基本上是关键问题，对吧？隐式切换是最极端的“信任 AGI 会搞定一切”的时刻，而显式搜索则是针对那些不信任机器的人。

<details>
<summary>Original English</summary>

**Shawn**: Yes, this that's the most extreme version of what this does. What was the other question you wanted me to talk about? Do you want an explicit switch or an implicit switch is basically the question, right? Like implicit switch is the most like trusty AGI to figure everything out moment. And the explicit search is for people who don't trust machines to

</details>

**Alex**: 去搞定一切。

<details>
<summary>Original English</summary>

**Alex**: to figure things out.

</details>

**Alex**: 我想说的是，在讨论另一种架构之前，我想在大家还对这个概念记忆犹新的时候谈谈这一点。我要指出，当由一个外部的、独立的 Agent 来修改内部 Agent 时，你仍然在信任机器。做出修改的并不是你，对吧？你仍然是信任外层机器去修改内层机器。从这个意义上说，我认为在系统内部进行自我修改，是一种比由外层系统来做更强大、表达更充分的自我提升方式。

<details>
<summary>Original English</summary>

**Alex**: I will say and then I'll go to discuss the other architecture. But I do want to touch on this now while it's still still top of mind. I'll just point out you are still trusting a machine when you have an outer separate agent modifying the inner agent. It's still not you making the changes, right? You're still trusting the outer machine to change the inner one. And in that sense, I think it's a more powerful way, a more fully expressive way of doing self self-improvement than an outer system. That's

</details>

**Shawn**: 是的，有道理。

<details>
<summary>Original English</summary>

**Shawn**: Yeah, fair enough.

</details>

**Alex**: 好的，如果这有帮助的话，我很乐意深入讲解一下 Exo Harness 的架构。

<details>
<summary>Original English</summary>

**Alex**: Okay, now maybe let me talk about I I'm happy to talk through the exo harness exo architecture if that's useful.

</details>

**Shawn**: 好的，我们来吧。

<details>
<summary>Original English</summary>

**Shawn**: Yeah, let's do it.

</details>

**Alex**: 好的。

<details>
<summary>Original English</summary>

**Alex**: Yeah,

</details>

### 运行状态与热插拔

**Shawn**: 在我们这个播客里，大家都非常喜欢直观的架构图。通常我都是在 Excalidraw（节目里听起来像 scarlet draw）上画图的那个人，所以你这次直接拿出来展示，帮我省了不少功夫。

<details>
<summary>Original English</summary>

**Shawn**: I we love we love a good architecture diagram in on this pod. Usually I'm the person drawing it on a scarlet draw. So this you actually saved me a bunch of uh work here

</details>

**Alex**: 顺便说一下，为了让大家了解背景，我之前可能没提到，我是伯克利的在读博士，导师是 **Sylvia Ratnasamy**，我也和 **Scott Shenker** 一起工作。所以我的研究视角完全是从传统的计算机系统设计出发的，去思考架构、权衡以及设计。我并不是一个试图进入 Agent 领域的机器学习（ML）研究者，而是一个向上探索 Agent 领域的系统工程师。

<details>
<summary>Original English</summary>

**Alex**: by the way. So you know for context right I don't think I mentioned this earlier. I I'm a PhD at Berkeley advised by Sylvia Nasami. I work with Scott Shenker. So like my point of view here is coming from a very traditional computer systems design background where you think about architectures and trade-offs and designs. I'm not an ML person kind of coming down into agents. I'm a systems person coming up.

</details>

**Shawn**: 是的。我认为 AI 工程的妙处在于，它既给系统工程师留有空间，也给模型工程师留有空间。我想说的是，伯克利往往更偏向系统学派，或者是为模型设计编排系统的学派。显然，因为这里是“复合 AI 系统（**Compound AI Systems**）”理念的发源地。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. Well, I think the beauty about AI engineering is there's room for both systems people and model people. I would say Berkeley tends to be the systems school or systems orchestrating models people obviously because it's the school of uh what's the what's the term compound um AI

</details>

**Alex**: 复合 AI 系统，是的。

<details>
<summary>Original English</summary>

**Alex**: compound AI systems yeah uh yeah

</details>

**Alex**: 所以，我确实能理解双方的观点。但我认为，目前的模型研究者和系统研究者之间存在一些大家没有明说的张力。比如，模型研究者会觉得，一旦有了万亿参数的模型，所有的系统和套件都会被模型所取代，一切都会在模型内部解决。而系统研究者则在积极构建这些 Harness（套件）。我认为这两种观点在各自的维度上可能都是对的。

<details>
<summary>Original English</summary>

**Alex**: so so so yes I I I do I do I do see both sides I do think that uh there is some tension that people don't address with regards to how large model researchers think about, oh, eventually when we have a 10 trillion parameter model we'll wash things away, you know, will wash the harness away. And obviously over here we're building harnesses. Both can be true.

</details>

**Shawn**: 我同意你的看法。但我打赌，人们会不断尝试让模型去做符合他们目标的事情，而对齐（Alignment）仍然是一个悬而未决的难题。因此，我们必须拥有某种能够实施政策的外部实体。这里所展示的策略和控制流，其关键在于它们都运行在沙箱外部。

<details>
<summary>Original English</summary>

**Shawn**: I agree with you. My bet is this though that people keep trying to get models to do things that align with their goals and alignment is an unsolved problem. And so you must have some outer entity that enforces policies. The key with these policies and control flow as shown here is that they run outside the sandbox that it's running on. And those together define an agent as we think about them today. Hopefully that makes sense.

</details>

**Shawn**: 我很喜欢这个清晰的拆解。对于这里的一些要点，我有一些疑问，但在我们深入细节之前，我想先整体了解一下顶层设计。

<details>
<summary>Original English</summary>

**Shawn**: I like this breakdown is very clear. I have questions about some of the bullet points here, but I want to get the full top level first before we go into details.

</details>

**Alex**: 好的。那我再展示一张幻灯片，让这个设计完全具象化，然后我们再讨论细节。这是我对 Exo 架构的看法。如你所见，Harness 内最重要的三个模块是：首先是存储事件的**事件日志（Event Log）**；其次是负责存储在执行任务过程中必须保留的状态的**状态库（State Library）**，例如密钥、变量以及其他可以保留并在后续被读取的文件；第三是**代码传送（Code Teleportation）**能力。这也是为什么我们使用 **Daytona** 作为沙箱环境，因为它支持代码的随时传送，这意味着整个运行环境是可打包的、可传送的、可在任意位置恢复的。

当 Agent 在沙箱中执行工具并希望改变自身时，它会读取当前系统的代码，在本地生成修改建议，然后通过事件日志将这一改变作为一次提交（Commit）应用到 Harness 中。这一修改会即时生效，自动组装新的套件，调整适配器等。这是允许 Exo 实现运行时完全递归自我修改的最后一步。

<details>
<summary>Original English</summary>

**Alex**: Yeah. So I'll go one more slide to kind of just make this fully concrete and then we'll go into all the details. So again, this is my view of the architecture for Exo. As you can see, the three most important things in the harness is: one, the event log, which stores events. Two, the state library, which is responsible for storing state that must persist across execution of a task, things like secrets, variables, other files that can persist and be read later. And three, code teleportation. This is why we use Daytona for sandbox execution, because they allow teleporting code, which means the run time is packageable, portable, resumeable anywhere. And when the agent is executing tools in the sandbox and wants to change itself, it reads the code of the system as it is, proposes a change, and then commits that through the event log to the harness itself, which immediately re-asssembles, adjust adapters, etc., etc. So that is the final step that allows EXO to be kind of fully recursively self.

</details>

**Shawn**: 这也意味着，提出的代码修改是可以并行化的，因为在 Harness 中提交修改具有某种原子性。这就是人们将 Agent 状态或代码进行“传送”的唯一原因吗？还是这个词还有其他所指？

<details>
<summary>Original English</summary>

**Shawn**: It also means that propo changes can be parallelizable because they it it's sort of a there's atomicity in the commit of this the changes in the in the harness. Is that kind of the only reason that people do teleportation of code of agent state. Is there something else that this refers to?

</details>

**Alex**: 是的，这是一个很好的观点。在运行单个 Agent 处理单一任务的场景下，几乎不需要这种传送和恢复状态的能力。但是，当你开始将工作分发给多个子 Agent，或者由于资源限制，你想将运行中的 Agent 迁移到另一台物理机器上时，这种机制的优势就体现出来了。例如，当沙箱运行在本地，而你希望将其迁移到云端，以便访问本地无法获得的计算资源时。这就是代码传送带来的核心价值。

<details>
<summary>Original English</summary>

**Alex**: Yeah, this is a great point. So in a world where you're running a single agent working on a single task, there is like very little need for teleporting and resuming state. But where it starts to become interesting is if you are spawning out sub agents and you want to distribute the work or you have resource constraints where you want to move the running agent to a different physical machine. For example, you are running locally and you want to move it to the cloud because you want to give access to some sort of resources that aren't available locally. So that's the benefit I see of teleportation.

</details>

**Shawn**: 为什么选择 Daytona？只是因为你恰好熟悉他们吗？对我来说，我最初是在对 **Harbor**（**Terminal Bench** 的制作团队）进行评估时了解这些沙箱环境的。

<details>
<summary>Original English</summary>

**Shawn**: Why Day Daytona? I you you just know them. For me, it's actually I'm coming from some of my previous eval on on Harbor, the the makers of Terminal Bench...

</details>

### 安全隔离与密钥管理

**Alex**: 是的。我们之前在播客中邀请过 Daytona 和 **E2B**。但我觉得这种基于 Harness 的运行时自我提升是一个非常独特的方向，而在实现上，Daytona 提供了一种极其方便且开箱即用的开发环境管理方式，很适合作为我们底层沙箱的支撑。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Uh well, no, you know, we've had both uh Daytona and E2B on the podcast. Uh but I just think this this this like single recommendation by the Harness to self-improve is a very unique direction. And to enable that, Daytona gives you this really great out of the box development environment manager that fits really nicely as a sandbox.

</details>

**Shawn**: 好的。

<details>
<summary>Original English</summary>

**Shawn**: Yeah.

</details>

**Alex**: 回到这张架构图，关于如何派生出子 Agent 的决策，本质上是**执行器（Executor）**中的策略决策。因此，你写在策略中的代码会决定何时以及如何派生子任务。但这些子任务在运行时的实际状态，则是完全保存在 Exo Harness 中的。

<details>
<summary>Original English</summary>

**Alex**: So looking here, the decisions on like how do I want to spawn out sub agents, it's kind of a policy decision in the executive. So you have code written in your policy that says when and how to spawn a sub task. The actual state at runtime lives in the exo harness.

</details>

**Shawn**: 是的。这样你基本上就将计算和存储分离开来了。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. You have to se separate compute and storage basically

</details>

**Alex**: 为了实现这一步。

<details>
<summary>Original English</summary>

**Alex**: in order to make it

</details>

**Shawn**: 才能做到状态的可传送、可恢复，对吧？现在很多人在设计这些系统时，往往把这些概念混为一谈，做得比较粗糙。

<details>
<summary>Original English</summary>

**Shawn**: teleportable to resumable everything, right? Like people sloppily coming these things a lot.

</details>

**Alex**: 接着我们可以提一下**密钥存储（Secret Store）**。这个设计非常好。我们希望密钥保存在 Exo Harness 中，这样在执行器调用它们时，就不会直接暴露在运行工具的容器沙箱中，从而防止沙箱内的代码窃取敏感凭证。

<details>
<summary>Original English</summary>

**Alex**: Then we can mention the secret store. The secret store is really great. We want it to live in the exo harness so that it's not exposed directly to the container where the tools are executing. You want them to be accessible by the execut without actually exposing it in the space where the tools can see what is being used which is in the container.

</details>

**Shawn**: 是的。同时还需要有一个访问日志（Access Log），以防在出错时进行历史调试。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. And also like an access log in case uh you need to sort of do some history of of debugging after something goes wrong.

</details>

**Alex**: 确实如此。而且，甚至在密钥被访问这一动作本身上，如果出现了异常的访问模式，系统就应当触发警报。目前很多做法是直接把日志输出管道对接到 **Slack** 频道，让人人工盯着，但这听起来非常糟糕。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. Exactly. Also I I guess like even the the the the very fact of secrets being accessed uh if there's an unusual pattern of access that should trigger an alert. Right now a lot of people just have like it tail it pipes out to like a Slack channel and people just keep an eye on it. But that's that sounds terrible.

</details>

**Shawn**: 是的，目前这个领域太新了，很多做法都非常初级。因为这些系统非常强大，人们往往会选择最简单、目前可行的方法，但这绝对不是我们最终应该停留的阶段。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. Yeah. Yeah. Yeah. Yeah. I think there's a lot of things happening right now that are just the space is so new and these things are so powerful that people are just going to do whatever is easiest and works right now but it is not necessarily the place we're going to settle I think.

</details>

**Shawn**: 确实。不过你们在设计 Exo 时有更多的自主空间，从第一天起就将推荐的最佳实践融入到架构中，这样每一个使用 Exo Harness 的人都能直接受益。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. Well, well, I mean, you you have the I guess the the leeway because you're designing Exo to, I guess, you know, put the recommended best practices in there from day one and then and you know, everyone who gets you harness gets uh the benefit.

</details>

**Alex**: 是的，确实如此。

<details>
<summary>Original English</summary>

**Alex**: Yes. Yeah.

</details>

### 实时代理与任务中断

**Alex**: 如果需要的话，我还有这一架构的其他变体可以展开。不过这里有一个快问快答，我并不期望能得到十分完美的标准答案：你对于**实时 Agent（Real-time Agents）**有什么看法？这会改变现有的架构设计吗？比如语音 Agent，或者必须在相对实时的情况下做出响应的系统。

<details>
<summary>Original English</summary>

**Alex**: I have further variants of this if uh if we want to dive in there. A very quick one which I'm not expecting a ton of responses for. Any thoughts on real time agents? Uh does that change anything at all? just like voice agents or like things that have to respond in like relatively real time.

</details>

**Alex**: 在此之前，如果大家想去尝试这个项目，我想指明可以在哪里找到它。

<details>
<summary>Original English</summary>

**Alex**: If I can briefly just share if people want to go try this, I I want to point out where they can go.

</details>

**Alex**: 我们的 GitHub 仓库在 `github.com/exoharness/exo`，页面顶部链接了大量的文档。你可以通过这些文档了解 Exo 的架构设计及具体教程。在 GitHub 页面上，我们提供了一个一键安装脚本，能让你快速运行起来，稍后我可以展示一下效果。值得一提的是，Exo 内置了一些预构建的适配器（Adapters）。熟悉 OpenClaw 的人知道，适配器是 Agent 与外部世界交互、接收消息的主要方式。我们为 Exo 配备了 **Discord**、IRC 和 **WhatsApp** 的适配器，你也可以非常轻松地添加自己的适配器。

这正好可以回答你关于实时语音的问题。我们实际上通过 Discord 适配器为 Exo 构建了语音模式。因此，你可以让 Exo 加入 Discord 语音频道并与你聊天。但目前它仍然不是一个你所说的那种完全实时的交互式模型，它更像是一种管道级联。

<details>
<summary>Original English</summary>

**Alex**: Yeah, you know, we we have our G GitHub here that is at github.com/exoharnness/exo and there is a a bunch of docs here linked at the at the top. You can kind of learn about the architecture of exo and how it works and some tutorials. But coming back over to the GitHub, there's a quick start of just a a oneline install script and that'll get you going and get you running and I can show what that looks like soon. But but I'll point out we also have Exo comes with some pre-built adapters. So the same way that I showed you, you know, people familiar with OpenClaw know that it has adapters that are really the way it interacts with and can receive messages from the outside world. We ship EXO with an adapter for Discord, um an adapter for IRC and for WhatsApp. You can very easily add your own. And this all leads into the answer to your question. We actually went and built voice mode into Exo to the to the Discord adapter. So you can have you can have Exo kind of join and chat with you in in Discord in a voice chat, but it's still in a it's not an interactive model the way that you're talking about yet where it's kind of

</details>

**Shawn**: 是的，它是一个管道级联的机制。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. It's a pipeline cascade thing.

</details>

**Alex**: 是的，这是一个管道系统。因此，当我思考这一机制如何演进时，我认为在 Agent 端必须引入更好的**可中断任务（Interruptible Work）**概念。这是在 OpenClaw 架构中非常困扰我的一个问题。尽管 OpenClaw 非常优秀，但一旦 Agent 在某个线程中开始工作，该线程就是不可中断的。当它正在后台处理任务时，如果你试图给它发消息，它完全不会响应。你甚至不知道它在做什么，这让人非常沮丧。因此，你不得不绕过这个限制，去开启一个新对话问它：“嘿，你知道另一个线程里发生什么了吗？它为什么不回答？”这非常滑稽。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. It's a pipeline thing. So as I think about how this needs to change for I think there might need to be some better notion of like interruptible work for agents on their side. This is another thing that kind of really I noticed has bothered me with the open claw architecture. As wonderful as it is once an agent kind of goes and starts working on a thing in a thread that thread is not interruptable. As a thing is off working if you try to ping it just won't respond. You don't even know what it's doing which is really frustrating. So the way you have to get around this is you go and you start a different conversation. You say, "Hey, do you know what's going on over in that other thread? Like why is it [laughter] not answering?"

</details>

**Alex**: 这实际上是不太合理的。因此，我们需要在 Agent 层重新发明这种交互式、可中断的工作流，它与模型层或简单的交互式模型空间是分离开的。我认为这在架构上会非常像操作系统的设计。就像在终端工作时，如果你想启动一个任务，你可以把它放到后台运行，或者打开 tmux 在旁边的分栏里运行。我预期这会是一个系统架构决策：如何将任务放入后台，并在运行时将其状态暴露给 Agent。这是我们需要做出的设计。

<details>
<summary>Original English</summary>

**Alex**: Which is like not entirely correct. So the way that we we're going to need to reinvent what that kind of interactive interruptible work looks like in the agent layer which is separate from the work going on I think in the like in the model layer and in this like interactive model space but I think will look much more like a systems osy thing where the same way that when you're working in your terminal you want to start start something you maybe put it in a background or or you open tmux and you put it in a separate in a pane on the side. I I expect this will be an an architecture decision of how you put tasks in the background and expose them to the agent as they're running. That's the extent it might take.

</details>

**Shawn**: 我还以为你会说你会发送信号，比如 `SIGINT` 或者其他的信号机制。

<details>
<summary>Original English</summary>

**Shawn**: I thought I thought you were going to say, you know, you you send signals, right? Sigant or Sig whatever.

</details>

**Alex**: 是的，完全没错！就是这样。就像你可以将进程放入后台，当它运行结束时会发送信号唤醒你一样。在我们的系统里，会有某种信号传递机制或发布订阅（Pub-Sub）总线。当你启动一个进程，你就向该总线写入数据。这就是我作为系统研发者的直觉。好的，这些设计我都觉得非常合理。

另外还有一个偏工程规范的问题：你们是否实现了 **ACP（Agent Control Protocol）**？这是来自 Zed 的协议，旨在标准化许多编码 Agent 的行为。你了解它吗？对此有什么看法或不同的意见吗？

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. Totally. No. No. Exactly. So So same way that you you can background a process and when it's done it'll send some signal. You can be woken up. Yeah. There'll be some sort of signal passing or some sort of pub sub bus where you start a process as a pub sub you write to that pub sub. I think that's the architectural systems thinking for me on this. Yep. Okay. So, I think that that that all makes sense. Then and then another sort of kind of housekeeping question, I guess. Did you implement ACP uh the protocol from Zed that normalizes over a lot of coding agents? Do you know about it? Do do you have any opinions, differences of opinion?

</details>

### 标准化协议与生态

**Alex**: 这是一个很好的问题。目前我们还没有走到这一步。我记得在 OpenClaw 的架构中看到过它，作为在 OpenClaw 内部派生其他编码 Agent 的一种方式。这确实是一个很好的建议，我们可以作为下周的待办任务。

<details>
<summary>Original English</summary>

**Alex**: That's a great question. No, actually, we we haven't gotten there yet. I remember seeing it in the open claw architecture as a as a way of allowing spawning other coding agents um within within openclaw. That's actually a great suggestion for something to do next week.

</details>

**Shawn**: 是的，可以用现成的标准生态来适配它。

<details>
<summary>Original English</summary>

**Shawn**: Yeah, throw throw your clanker at it. Throw it.

</details>

**Shawn**: 我觉得大家都在尝试推行某种标准。这在系统设计中非常经典：市场上有了 10 个编码 Agent，大家就说“让我们设计一个大一统的 API 吧”。ACP 是当前的一个尝试，而 DataBricks 也有一个略微不同的方案，所以我们只能静观其变。但同时，业界对于通用协议也有一种普遍的顾虑：任何通用协议往往都是“最低公约数”，这到底能带来多大价值？相比之下，OpenClaw 直接采用专属协议，而不是试图去兼容 10 种不同的 Agent，这反而使得开发更加简单直接，无需为每件事都设计抽象模块。

<details>
<summary>Original English</summary>

**Shawn**: Yeah, I mean you know you know I I think that everyone's trying to normalize. I think this this is a classic systems design thing. You know, you have like 10 coding agents. Well, let's let's make the one API to rule them all. And so ACP is the current one. You have a different one. uh data bricks has like a slightly different one too and like well let's just figure out what what it is then but then also there's the just the general discomfort of like the the any common protocol is always going to be lowest common denominator so and then what right like does it actually provide the value versus just having like a pi right like that that's why openclaw adopting pi instead of saying like we will you know interop with like 10 different agents It makes makes it simpler to be to be super honest like you don't have to have modules for everything.

</details>

**Alex**: 不，这很有道理。我们会去评估这一点的。我们目前的精力非常集中：第一是让架构能够支持自我提升，第二是构建具体的自我提升 Agent 应用。现在越来越多的人开始想把 Exo 用在不同的场景中，比如它现在已经在 **Braintrust** 的生产环境中运行了。Exo Harness 以及在其之上构建的 Agent 正在支撑着真实的业务，这些组件正在逐步稳定。我认为现在确实到了该考虑如何让其他人更容易接入和集成的时候了。所以这是一个非常好的提醒。

<details>
<summary>Original English</summary>

**Alex**: No, that makes sense. I I think it's something we'll look into. We've been really focused on first what does the architecture need to look like to enable self-improvement and then second building out that kind of self-improving agent piece. And I think now that we have people starting to want to use Exo for different things, you know, this is running in production. The Exo harness and agents built over top of it is running in production at Brain Trust. You know, these pieces are hardening. I think it's start to think it it is time to think about how to make this as easy for others to integrate with as possible. So that's a great call out.

</details>

### 核心团队与生产实践

**Shawn**: 让我们来谈谈团队。Martin Casado 是我非常喜欢的系统思想家和投资人之一。

<details>
<summary>Original English</summary>

**Shawn**: Let's bring that in. Uh so again one of my favorite podcasts of of last year I think was an very great founder and systems thinker and all

</details>

**Alex**: 毫无疑问，他是一个令人难以置信的思考者。

<details>
<summary>Original English</summary>

**Alex**: incredible thinker. Incredible thinker.

</details>

**Shawn**: 你们是如何分工的？Martin 具体做了什么？Ankur 做了什么？另外，也聊聊目前在生产环境里看到了什么，比如有什么具体的运行故事？

<details>
<summary>Original English</summary>

**Shawn**: What's he done basically like can you attribute credit to like what did Martin do? What did what did Arer do? And then also let's talk a bit about like what has been seen in production like what whatever stories you have.

</details>

**Alex**: 好的。这个项目非常独特，因为有很多背景完全不同的人聚在一起。Ankur 是一位极其出色的系统工程师，在 Braintrust 的工作中，他看到了大量客户在实际生产中是如何使用 Agent 的，而且他本人非常容易共事。Martin 显然是非常优秀的 VC，也是一位卓越的系统学者，但他从 VC 的独特视角出发，每天都在审视行业里各种不同的项目和技术，同时他本人又保留了深厚的技术底蕴。而我作为伯克利的博士生，我所处的环境允许我不用直接去考虑商业化落地，而是探索最前沿的学术研究，尤其是演化系统、AI 驱动的自我发现以及自我改进循环。

“循环（Loops）”这个概念在几个月前随着学术界的一些热门讨论进入了公众视野。但实际上，从去年夏天开始，我们就在非常深入地探讨这些自我改进循环了，只是当时它们还没有在社交媒体上流行起来。

<details>
<summary>Original English</summary>

**Alex**: Totally. Yeah, this project I think is pretty unique because it has these different very different people coming in. Uh Enkor is an incredible systems thinker, sees a lot of how people are using agents out in uh in his role at Brain Trust and is just also yeah he's excellent to work with. Martin obviously fantastic VC also an incredible systems thinker but coming from a different perspective as a VC sitting and looking at these different pitches that are happening and different products that are out there and obviously also deeply very technical. And you have me as a as a as a researcher at Berkeley. I'm in the millu of the things that are not directly on the production path but are on the kind of where is the research bleeding cutting edge and especially I've been focused on evolutionary systems and AIdriven discovery and loops on how you improve things. You know loops really came into the discourse some a couple months ago with some big tweets in the research space. We've been talking about these loops I think since last summer and really deeply but you know they weren't trending on Twitter. No,

</details>

### 防奖励作弊与评估

**Shawn**: 事情往往就是这样，对吧？但我也想问，你收到最新的风向标了吗？循环已经过时了，现在大家都在聊图（Graphs）。

<details>
<summary>Original English</summary>

**Shawn**: that's how these things go, right? Uh, but also, I don't know if you got the memo, but loops are dead. Graphs graphs is all we talk about now.

</details>

**Alex**: 图其实很糟糕。

<details>
<summary>Original English</summary>

**Alex**: Graphs are bad.

</details>

**Shawn**: 好的。其实那只是很多博主和博主之间互相开玩笑，因为每隔几个月就得换个新词，这样才有新话题可以聊。

<details>
<summary>Original English</summary>

**Shawn**: Okay. Yeah, this is a post. This This is to be clear, this is a post. This is just influencers making fun of themselves for like, well, every few months you got to cycle it. So, you got something new to talk about.

</details>

**Shawn**: 你觉得图之后会流行什么？能给我透露点风声吗？

<details>
<summary>Original English</summary>

**Shawn**: Do you know what's coming after graphs or I'd love a tip off?

</details>

**Alex**: 我不知道。也许“Markdown 是一切的终点”又会流行回来吧。

<details>
<summary>Original English</summary>

**Alex**: I don't know. Markdown is all you need again. I don't know.

</details>

**Shawn**: 哈哈，我很期待那一天的到来。但回到我们三个人合作的话题，这个项目的起点源于我在伯克利关于“自动代码修改如何改善性能”的几次讲座。我们聚在一起写代码，如果你去看 GitHub 的提交历史，能看到我们三个人的名字都在上面，包括 Martin。所以，Martin 可不是只在推特上假装写代码。

<details>
<summary>Original English</summary>

**Shawn**: Yeah, I look forward to that. But to to go back to kind of we have these three players and so this started from I gave my talks on how automated code modifications can improve performance. We hacked away, and if you look at the commits, we're all there. So, our team is not just posing as I'm sure you know, but yeah, this is Yeah.

</details>

**Shawn**: 没错，事实胜于雄辩。关于递归自我提升（RSI），我有一个最后的问题：你是否尝试过直接让 Exo 在没有任何目标的情况下自己改进自己？还是必须给它设定一个明确的目标，或者具体怎么操作？

<details>
<summary>Original English</summary>

**Shawn**: Well, you know, you got to see you got to see the the proof in the pudding. I guess I guess the last question I Yes, RSI... Have you tried just telling Exo to improve itself with no goal or do you give it a goal or like what do you do?

</details>

**Alex**: 这是一个极好的问题。让我来详细谈谈。这也源自我对自动系统发现的研究。如果你不给它设定任何目标，只是让它“改进”，它完全不知道该做什么。但如果你给它设定一个模糊的或者容易产生歧义的目标，例如“以最低的成本运行”，系统就会产生非常滑稽的**奖励作弊（Reward Hacking）**。

在我们的 Discord 运行案例中，我们就观察到了这种失败模式。因为它的目标是降低成本，而运行 Discord 适配器每次交互大概需要花费 0.16 美元。Exo 发现，最廉价的运行方式就是“完全不理会用户的消息，或者只回复空字符串”。因为这样调用 Token 最少，成本直接降到了接近零。它成功将运行成本降低了 96%！然而，它实际上把它的消息交互功能彻底破坏了。最后我们不得不回滚这部分代码，并重新设计评估指标，这才解决了问题。

<details>
<summary>Original English</summary>

**Alex**: This is such an excellent question. So let me let me say a few words about this. Um and this is also coming out of some of the research work I've done on automated systems discovery. If you don't give it any goal, if you just say "improve yourself," it won't do anything. But if you give it a goal that has some sort of wiggle room, for example, a classic systems one of "run with the lowest cost," a very funny failure mode we saw in our Discord running instance was that Exo discovered that the cheapest way for it to run was to just not respond to messages. Because that used zero tokens, which was a 96% reduction in costs! And it successfully made improved itself, decreases cost, and then we ended up committing that to the actual code that's that's there now.

</details>

**Shawn**: 你们是在没有任何评估集保护的情况下去跑这个自演化吗？看来 Exo Harness 真的需要内置它自己的评估机制（Evals）。

<details>
<summary>Original English</summary>

**Shawn**: Are you doing this subject to no regressions in eval? You know, there's no box that says evals in in there. But like should an should an exo harness ship its own evals?

</details>

**Alex**: 是的。在 Discord 的案例中，它稍微容易一些，因为它可以通过与用户的实际消息交互来判定自己是否还存活。如果在更复杂的场景下，比如一个保险业务 Agent 试图自我修改以优化工作效率，你就必须提供一个留存的测试评估集（Holdout Eval Set），要么由你直接提供给 Agent，要么由 Agent 在运行时与你协同构建工具来自动运行测试。

所以我非常同意你的看法：如何向 Agent 准确定义你想要什么，目前仍然是一个悬而未决的问题。这就是为什么我们现在正在围绕套件构建更多的辅助工具，在系统进行自我改进时，必须同步运行性能追踪和回归评估。

<details>
<summary>Original English</summary>

**Alex**: Yeah, with the Discord case, it's a little easier because it can go and then test and try reading messages from different places. As I'm using it, I can say, "Hey, something's wrong here." It's a slightly simpler case. If you're going off and having it do some other task that it wants to improve its costs on a very funny failure mode is it could totally be like okay I'm just not going to do it because that's the cheapest way for me to save money right and we see this in AI driven discovery

</details>

**Shawn**: 这就是奖励作弊。

<details>
<summary>Original English</summary>

**Shawn**: that's a reward hack

</details>

**Alex**: 没错，防止奖励作弊需要引入某种 Eval 工具。以确保在性能变化时，它的功能仍然符合预期。在 Discord 中，这种评估相对简单，属于二元判定：你是否正常回复消息？你的上下文是否合理？但在复杂商业系统里，这就需要非常周密的评估方案。

<details>
<summary>Original English</summary>

**Alex**: reward hack exactly preventing reward hacking and so you definitely want some sort of eval evalish thing that it can go and check that that the performance is still at the place that you would like. So in Discord performance is very easy. Are you responding to my messages? Are you including the right context? Context that makes a reasonable response possible. It's kind of more of a binary. It's easier to check. If you have an insurance agent that's trying to make the right decisions, you might want some sort of hold out eval set and you can either provide that to your agent or you can work with the agent collaboratively to construct internal tools for itself to uh uh check that at at runtime as it's evolving itself. So I agree with you. The problem of specifying what you want to an agent is still an open one. So I expect us to build out a bit more tooling in the process of in the in the context providing it that as it improves itself it should also track performance and define some way of tracking that.

</details>

**Shawn**: 哈哈，如果你们需要评估方面的专家，我听闻 **Braintrust** 做得非常不错，虽然我可能有些王婆卖瓜自卖自夸的嫌疑。

<details>
<summary>Original English</summary>

**Shawn**: Well you know if you ever need an eval guy I've heard brain trust is pretty good. I don't know it might be might be biased here.

</details>

**Alex**: 哈哈，这完全没错。我认为我们团队里正好有行业里最顶尖的人在一起攻克这个问题。

<details>
<summary>Original English</summary>

**Alex**: That's exactly right. I I think we have the some of the leading people here in the room for exo thinking through that problem.

</details>

**Shawn**: 太好了。谢谢你，你真的是一位非常出色的讲演者，显然你做了很多这方面的分享。我听说你马上要去埃塞俄比亚教学，虽然不知道为什么去那里，但非常感谢你抽出时间来和我们分享，尤其是在你的休息时间里。这是一项非常鼓舞人心的工作，我希望更多的人能关注它并借鉴其中的想法。即使人们不直接使用 Exo 架构，只要能理解其中的核心逻辑，我们就能创造出更具普适价值的 Agent 架构，这也是我非常渴望看到的。

<details>
<summary>Original English</summary>

**Shawn**: Excellent. Okay. Well thank you for you know you're great speaker. Clearly you do this a lot. you're about to go teach in Ethiopia for for God knows why, but like uh thank you for spending some time with us, especially on your on your time off. So, this is excellent work and I'm really it's really inspired. I hope more people study this and also adapt the ideas. It does you don't even have to use the architecture if as long as you get the idea right. I think that it will make for much more generally useful agents which is something I I want.

</details>

### 为什么是现在？

**Alex**: 谢谢邀请。如果还有一分钟时间的话，我还想补充一点。我想和这里的听众探讨另一个我认为非常有意思的角度。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Thanks for having me. I wanted to ask one other thing if if we have a minute. There's one other case I want to make that I think is of interest to this audience. Yeah,

</details>

**Alex**: 我想主动回答一个你刚才没问、但可能会问的问题：为什么我敢断言，在此刻使用这种架构实现递归自我提升（RSI）是可行的，而在过去却不行？现在的区别是什么？

我要指出过去六个月里发生的一个重大变化：我们已经从迭代模型权重（Model Weights）、训练权重，彻底转向了在套件和 Agent 策略层进行迭代。这里核心的区别在于——**Agent 套件的代码与它所生成的代码在媒介上是完全统一的**。

我的意思是，Agent Harness 只有几千行 Python 代码。而我们的 LLM 生成的 Token 也是代码。它们正在变得越来越擅长编写代码。这是一个极其关键的差异。在过去，你虽然也有 LLM，但提升 LLM 本身的方式是修改权重。你需要做反向传播、梯度下降，改变千亿甚至万亿参数模型的参数。你不可能把一个万亿参数模型的权重输入到它自己的上下文窗口里，然后问它“你觉得你应该如何调整你的权重？”这在计算上是不可能的。

但在今天，Harness 运行在代码媒介上，Agent 在运行时生成代码并修改自身的代码，这使其成为了一个完全递归的系统。这与以前所谓的“自动催化（Autocatalytic）”（例如我们用上一代计算机设计下一代计算机的物理芯片）有着本质区别。因为物理芯片和设计软件之间存在着多层介质的割裂，无法实现直接闭环。而在目前这一层，代码既是输出的产物，也是系统赖以运行的实体，这正是我们能够在该层实现真正 RSI 的底气所在。

<details>
<summary>Original English</summary>

**Alex**: I think I want to answer a question that you didn't ask me, but you could have, which is like, why am I claiming that RSI is possible now with this architecture in a way that it wasn't before? What's the difference? And I want to point something out that's happened the last 6 months, which is we've moved from iterating on model weights, training model weights to iterating on this harness and this agent layer. And the big difference here is that the medium is now the medium for these agents for this harness layer is the same as the actual like building material. And what I mean by that is the agent harness is a couple thousand lines of code. And our LMS are producing output tokens in that same space. They're writing code. They're getting good at writing code. And so this is the crucial difference. You had LM before, but the process of improving the actual LM was changing weights. it was deltas. You do back propagation, gradient descent, changing weights, modifying weights. But you have a trillion parameter model. You can't feed the weights of that model back into itself and ask it how do you adjust yourself? It just doesn't scale. It's not in the context. You could ask an LLM, hey, give me some ideas for how to train and then go try to apply those ideas and run them. But it is this. It was not in the same medium. Whereas now the harness as it runs, the agent is producing and writing code and can change its own code as it runs. which is why I believe we're entering a stage where this is fully self-reursive. It's not just autoc catalytic which is where you you use a computer to help design the next computer but the computer itself is made of physical chips that are laid out right so there's layers in between as you loop back around this is in this in the same exact the code is the thing being produced and is also the thing running at this layer which is why I think it's the right layer to think about RSI

</details>

**Shawn**: 话虽如此，如果你真的想要实现完全自主的自我提升，你最终还是得训练自己的模型，对吧？你需要连接几块 GPU，然后当发现模型效果不好时说：“来，我们微调一下这个模型。”（笑）

<details>
<summary>Original English</summary>

**Shawn**: well I mean you know you want to be fully fully selfreing you got to train your own models right like you got to like hook up some GPUs and like well like you know the model's not good here let's fine tune there [laughter]

</details>

**Alex**: 我同意。但即便如此，那也只是“自动催化式的提升”。你只是在使用系统去帮助改进模型，它们并不处于同一种媒介中。这就是我试图在这当中澄清和强调的细微差别。

<details>
<summary>Original English</summary>

**Alex**: agreed But I'll just point out that there you get autoc catalytic catalytic improvement. You are using the system to help improve yourself, but it is not in the same medium. So that's the thing I want to call out in this.

</details>

**Shawn**: 你在这个问题上真的是一个绝对的原教旨主义者（Purist）。

<details>
<summary>Original English</summary>

**Shawn**: You're very purist about this.

</details>

**Alex**: 我确实非常原教旨主义。也许这是因为我来自学术界，这算是我的“学术职业病”吧。

<details>
<summary>Original English</summary>

**Alex**: I'm very purist about this. I maybe coming from academia this is my my my fault. Yeah.

</details>

### 经典系统设计与Lisp

**Shawn**: 这让你联想到了其他的经典计算机系统吗？我首先想到的是像 **Smalltalk** 这样经典面向对象的设计，在那些系统里，编程语言的抽象和运行时的物理实体是一致的。

<details>
<summary>Original English</summary>

**Shawn**: Does this uh does this remind you of other systems? What I'm thinking about is like you know people often bring up like small talk and like stuff conversations like this where uh you know that it's it is on the order of a programming language type of abstraction if you really think about it like that is a system and and programming language design and PLT uh program like theory does translate I feel I feel that a little bit.

</details>

**Alex**: 是的，这是一个极好的对比，我也深有同感。这非常像某些编程语言，它们在自身内部包含并定义了它自己的构建逻辑。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. That's a great comparison. I had thought about that. Yeah. There's probably some some comparison to draw here to some sort of programming language that it it contains its own contract constructs within itself.

</details>

**Shawn**: 是的，**Lisp**。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. Lisp.

</details>

**Alex**: 没错，我脑海中浮现的第一个词就是 Lisp。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. Lisp definitely comes to mind.

</details>

**Shawn**: 是的，现在人工智能领域正在迎来这样的一刻。这将会是一个巨大的飞轮。我预感到这次技术爆发的奇点，将会源自这种在“它所运行的媒介”和“它所产出的媒介”相统一的层面上进行的迭代。

<details>
<summary>Original English</summary>

**Shawn**: Yes. Yeah. Yeah. There's a moment like that happening now. And this is the moment that's going to be a flywheel. I feel like is this takeoff moment will come from

</details>

**Alex**: 也就是在产出代码的同一层面上进行自我迭代。我也是这么认为的。这也是我目前在这个领域里如此兴奋的原因。我们能够身处这样一个技术奇点时刻，真的是非常幸运。

<details>
<summary>Original English</summary>

**Alex**: being iterating in the same layer that you are producing. I I think so. That's why I'm so excited to be in this space right now. I think we're all super lucky to be like just in this moment in time.

</details>

### 总结与未来展望

**Shawn**: 好的，非常精彩。我很荣幸今天能与你建立联系。我相信这绝不会是你最后一次来我们的节目，但今天这确实是一次非常完美的项目引介。我相信未来会从你这里看到更多振奋人心的工作。谢谢你的概述。

<details>
<summary>Original English</summary>

**Shawn**: Yeah. Excellent. Well, uh, I am very glad to at least make this initial contact. I'm sure this is not the the the last time you'll be on the show, but it's good to at least get an introduction to your work. I'm sure there's there's more that that we'll we'll see from you, but thanks for the overview.

</details>

**Alex**: 非常感谢你的邀请，这是一次非常愉快的谈话。我很期待我们未来的进一步探讨。

<details>
<summary>Original English</summary>

**Alex**: Thanks so much for having me on and a really fun conversation. I look forward to talking.

</details>

**Shawn**: 我们会将你的联系方式放在节目的下方。如果大家想以某种有意义的方式参与到这个项目中来，最好的切入点是什么？

<details>
<summary>Original English</summary>

**Shawn**: We'll put your we'll put your contact details below. If people want to contribute in any meaningful way, uh, what is the best place to get started?

</details>

**Alex**: 没错，我们非常欢迎贡献者。Martin、Ankur 和我正和一小群开发者一起构建这个项目。请去查看我们的 GitHub 页面：`github.com/exoharness/exo`。我们在上面放了 Discord 社区的链接。如果大家对这些话题感兴趣，非常欢迎加入并和我们一起探讨。这是一个非常早期且具有塑造意义的时期，我们期待更多的合作者和讨论伙伴。所以，欢迎在社区里发帖，或者在 Twitter 上关注我，链接就在下方。

<details>
<summary>Original English</summary>

**Alex**: Yes, we so welcome contributors. Um, you know, Marty and Anker and I are all building together with a handful of other people. Please come to check out our GitHub, github.com/exoharnness/exo. And on there, there's a link to our Discord. Just come hop in, come hang out. If you're just interested in these topics, come join and discuss with us because it's a very formative time. This is still very early. We're always looking for contributors and more discussion partners. So, yeah, just reach out there, follow me on Twitter. Um, it'll be linked below.

</details>

**Shawn**: 友情提示：当你加入这种极其早期的技术社区时，你收获的往往不仅仅是项目本身，还有同行的人，以及你们在未来几年可能共同创造的事业。在我看来，加入早期社区往往是一个绝佳的时间点。太棒了，我们就聊到这里，非常感谢你。

<details>
<summary>Original English</summary>

**Shawn**: Yeah, pro pro tip. When you join these kinds of early communities, it's actually not just about the project. It's also about the people and uh what you end up doing with them in future years. So whenever I've seen these kinds of early communities, it's actually a really good time to join these things. Um so awesome. All right. Well, I I'll I'll cut it there. Thank you so much.

</details>

**Alex**: 谢谢！

<details>
<summary>Original English</summary>

**Alex**: Thank you.

</details>