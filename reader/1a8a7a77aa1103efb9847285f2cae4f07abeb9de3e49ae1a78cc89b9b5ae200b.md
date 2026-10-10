---
author: AI Engineer
date: '2026-04-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=XNtkiQJ49Ps
speaker: AI Engineer
tags:
  - vertical-ai
  - complex-agents
  - human-ai-collaboration
  - agent-workflows
  - interface-design
title: 复杂AI代理的局限与突破：从“聊天”到“高带宽协作”的演进
summary: 本次演讲深入剖析了当前复杂AI代理在处理长期、高难度任务时所面临的困境，尤其指出计划和审查阶段已成为新的瓶颈。演讲者Jacob Lauritzen通过“验证者规则”阐述了任务可验证性在AI赋能中的核心作用，并提出了通过增强AI的“信任”与“控制”来优化人机协作的策略。最终，文章强调了未来AI协作应超越单一的聊天界面，转向文档、表格等高带宽交互形式，以释放AI代理的全部潜力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Legora
products_models:
  - Claude Code
media_books: []
status: evergreen
---
### 复杂AI代理的挑战：低效的自动化与新的瓶颈

在自动化日益普及的今天，我们期望AI代理能够独立完成越来越复杂的工作。然而，当面对一项需要深度研究、合同起草等耗时任务时，我们往往会遇到一个令人沮丧的循环：AI代理启动，执行一系列子任务，如网络搜索、文件读写，耗费大量时间后交出成果。用户检查后，发现合同中的某个条款存在错误或不符合要求，要求AI修正。AI接受指令后，可能会进行“压缩”操作，但这往往意味着它会丢失之前的上下文，导致遗忘关键信息。经过漫长的修复过程，最终获得的可能是修改有限或引入新问题的新合同，用户陷入了低效的迭代泥潭。

这种低效体验揭示了当前AI代理工作模式的一个关键问题：**计划（Planning）**和**审查（Reviewing）**阶段已成为新的瓶颈。与过去强调“执行工作”（Doing the work）的成本高昂不同，现在实际执行任务本身变得异常廉价，反而是如何精确地规划任务、理解非功能性需求、制定规范，以及对AI生成的结果进行细致审查，耗费了大量人力和时间。对于大型代码审查（如GitHub上的大PR）而言，其痛苦程度不言而喻。

<details>
<summary>Original English</summary>

Right. It's 5:00 p.m. on a Friday. There's just me and two more people behind you and Friday beer, so I'll try to be a little bit quick here. I'm here to talk to you guys today about vertical AI and and complex agents and why I think they need more than just the chat. If you've ever worked with a long-running complex agent, you've probably tried something like this. Sorry that it's all white. I can see the flash banging your guys' face. Um you're told to research something, draft a contract, make no mistakes, and um it starts thinking, it starts reading, launches a bunch of sub-agents, does web search, writes files, launches more sub-agents, does more reading, writes more files, keeps going, takes forever, after 30 minutes, it gives you your contract. You take a look. Clause three doesn't look right. What Did you make a mistake here? Could you, you know, look at another document? You're absolutely right. Then you see this, compaction. That's when you know you can give up. It's going to forget everything. It's in the the the context rot state. Anyway, it continues, it keeps on going, and uh you get a new contract. Does it look Was it only clause three that was changed? Probably not. And so you end up in this state. Not the greatest experience. My name is Jacob. I'm the CTO of Legora. We are a collaborative AI workspace for law firms, so we're a vertical AI company. We have more than 1,000 customers, more than 50 markets. We've raised a bunch of money. Uh we're growing extremely fast. Um I'm being told maybe the fastest in history. Um we are also hiring engineers in London. So in case anyone's interested and wants to be on this growth journey, please talk to me after my talk. Um our goal and the goal of most vertical AI companies is to make agents complete more and more complex work end-to-end. That's sort of doing that has changed a lot in the past 6 to 12 months because there are new economics of production. So it used to be if you wanted to complete end-to-end work, that you would be focused on doing the work. Right? That would be sort of the main thing is actually just getting it done. But today things look a little bit different cuz right now planning work and reviewing work is the new bottleneck. So doing the actual work is extremely cheap. It's very easy to do. But now you have to spend time planning, you have to get the non-functional requirements, you have to get the specs, and you have to spend a lot of time reviewing the work. And if anyone's reviewed big PRs on GitHub, it really sucks. It's extremely painful. Um maybe if you're super AI pilled, you just get your AI agents to review their own work. No humans involved. Maybe it works, maybe it doesn't.

</details>

### 验证者规则与行业可验证性谱系

理解AI代理在复杂任务中的表现，需要引入“验证者规则”（Verifier's Rule）。该规则指出，如果一项任务是可解决的，并且易于验证，那么它就更有可能被AI所解决。这在**基础模型（Foundational Models）**的训练中尤为明显，通过**强化学习（RL）**和**后训练（Post-training）**，AI可以在易于验证的环境中不断优化。

这一原理同样适用于**AI代理（AI Agents）**。当任务的可验证性提高时，代理就能更有效地在循环中迭代改进，例如通过“你这样做错了，请修正”这样的指令来逐步达到目标。然而，不同行业和任务在可验证性光谱上处于不同位置。

例如，在**法律领域（Legal）**：
*   **核查合同定义（Check definitions in a contract）**：这是一个**非常容易验证**且**容易完成**的任务。
*   **撰写合同（Writing a contract）**：任务本身**容易解决**，但**验证其有效性极其困难**。合同的真正效力往往只有在进入法庭，由法官最终判定时才能确认。
*   **诉讼策略（Litigation strategy）**：这几乎**无法验证**。咨询五位律师，可能会得到五种不同的策略，因为不存在唯一的“客观真相”，这使得AI难以找到解决方案。

在**软件开发（Coding）**领域：
*   **构建成功的消费级应用程序（Building a successful consumer app）**：这是一个**非常难以验证**的任务，其成功与否取决于市场接受度、用户体验等多种复杂因素。

理解这种差异至关重要：我们需要让AI处理那些我们能够有效验证的任务，同时找到让**人类（Humans）**介入那些真正需要人类判断和经验的环节的方法。

<details>
<summary>Original English</summary>

And when we think about completing complex work, both the planning stage, the doing stage, and the reviewing stage, the verifier's rule is a good way to think about work. So verifier's rule is a a term that was coined by Jason, which states that if it's a task is solvable and it's easy to verify, then it's going to get solved by AI. He was primarily talking about foundational models, so sort of if you can make something very easy to verify, then you can do RL environment, you can post-train, it's going to solve it. I think it also goes for agents. You know, if you can make a task verifiable, you can just run an agent in a loop and tell it, "Hey, you did this wrong. Please fix it." and it'll eventually get there. Different industries are different places in this spectrum. Um it's a little bit more complex than just this because verticals have tasks that are different places on the spectrum. So if you take legal, we can check definitions in a contract, super easy to verify, super easy to get done. Writing a contract is very easy to solve, but actually extremely difficult to verify cuz if you think about it, when you write a contract, the only time you can actually verify if, you know, the language you used works is if it goes to court and a judge basically verifies it, tells you if it's good or not. So that's actually quite complex. Litigation strategy is also basically impossible to verify. If you don't know what litigation is, it's when you sue someone or someone sues you. I know we're in Europe now, but the Americans really love doing this all the time. Um but essentially, if you ask five lawyers, "What should be the right strategy for this litigation case?" they're going to give you different answers. And so there's no objective truth, which means it's basically impossible to verify and it's really difficult for AI to solve. Similarly on coding, some parts of it are easy, building a successful consumer app, very difficult to verify.

</details>

### 提升AI代理的“信任”（Trust）与“控制”（Control）

为了实现更有效的人机协作，我们需要关注两个关键要素：**信任（Trust）**和**控制（Control）**。

**提升信任（How to increase trust）**：
1.  **降低任务难度谱系（Bring a task down in the spectrum）**：将任务调整到更易于验证的范围。例如，在**编码（Coding）**中，提供浏览器访问权限和实施**测试驱动开发（Test-Driven Development, TDD）**，可以将任务转化为高度可验证的过程。在**金融（Finance）**和**法律（Legal）**领域，也可以采取类似策略。
2.  **寻找验证代理（Proxy for verification）**：当直接验证困难时，寻找替代方法。例如，在**法律合同（Legal contracts）**的场景中，可以比较新合同与“黄金合同”（已验证有效的旧合同），检查其相似性，以此作为一种验证代理。
3.  **分解任务（Decompose tasks）**：将复杂任务分解为多个子任务。例如，将“撰写一份合同”分解，让AI处理易于验证的部分，如应用格式、检查定义（类似**代码审查（Linting）**），而将更具判断性的部分（如选择风险偏好、谈判立场）留给人类。
4.  **添加护栏（Add guardrails）**：通过限制AI代理的能力来增加信任。例如，限制AI只能编辑特定文件、只能访问特定目录或搜索特定网站。这种限制可以防止AI执行意料之外的危险操作。**Claude Code**被提及为一个例子，当信任度低时，它会事无巨细地询问用户，这使其“极其无用”。反之，过度信任则可能导致灾难性后果，如意外删除生产数据库。

**提升控制（How to increase control）**：
1.  **理解工作流的DAG结构（Work as a DAG）**：复杂代理的工作可以看作一个**有向无环图（Directed Acyclic Graph, DAG）**。例如，写一份关于雇佣合同的报告，可以分解为研究组织、审查合同（关注特定条款）、撰写报告等步骤。
2.  **低控制的瀑布式方法（Extremely low control）**：仅在根节点（最高层级）施加判断，AI自主完成所有子任务，用户只能在最后阶段介入，这提供了极低的控制力，如同最开始的合同起草示例。
3.  **规划（Planning）**：在任务开始前，与AI对齐方法和步骤。例如，明确告知AI应采取哪些步骤、关注哪些条款。这比瀑布式方法提供了更多控制，但缺点是规划本身需要大量信息和工作，且AI可能无法预知所有特殊情况（如合同中的特殊条款）。将规划比作与一位同事沟通一次性事项，而非持续的协作。
4.  **技能（Skills）**：**技能**是编码人类判断到工作节点上的强大工具。它们允许AI在执行特定任务时，遵循预设的、经过验证的逻辑。例如，规定在审查**保密条款（Confidentiality）**时应遵循特定方式，或在处理**终止条款（Termination clauses）**时，能够应对特殊的**欧盟法律（EU law）**。这使得AI能够处理**意外情况（Contingencies）**和**渐进式发现（Progressive discovery）**。
5.  **引导（Elicitation）**：当AI遇到不确定的情况时，主动向用户提问。关键在于避免AI被阻塞，并鼓励AI在不确定时做出有根据的决定，并将这些决策记录在**决策日志（Decision log）**中，供人类后续审查和纠正。

<details>
<summary>Original English</summary>

Depending on where the task falls in sort of the the chart, different things are important. How to increase trust. So if you want to increase trust, there's a few different things you can do. Firstly, you can bring a task down in the spectrum. So here is an example from coding. If you want to implement a feature, well, you can give it browser access, you can do test-driven development, and then suddenly it's actually a verifiable task and it's going to do much better. There are similar things you can do in finance and in legal, um you can do something similar as well. We don't have Let's take the contract example in legal. You can't really verify it, but you can look for a proxy for verification. So for contracts, what you can do is you can take a look at previous contracts. These are our golden contracts. We know they work well. Let's set up a test. Is it the new contract Is it similar to the old one? That's sort of a proxy for verification that's going to allow your agent to do much better job. You can also decompose tasks. So here's the example with writing a contract. I can turn that from one task into a bunch of other tasks, and I can leave picking a risk profile, picking the precedent documents, the negotiation stance, I can leave that to the human, but I can try to get other stuff done where it's easy to verify. So apply formatting, make it look like all my other contracts. Apply checking definition, which is essentially linting. Are all definitions used? Are all the definitions that are used to defined? This kind of stuff you can build, and then the agent can basically rip much better. You can also add guardrails. And guardrails is essentially a way to increase trust by limiting what the agent can do. So instead of being able to do all of this, you're just going to say you can only do these, you can only edit these three files, you can only read these from this directory, you can only search these websites. By limiting what it can do, you basically get more trust cuz you know they won't do all these weird things. An example of this, probably all know this one, Claude Code. If there's very low trust, it's going to basically tell you every single time it wants to do anything, which makes it extremely useless. Uh and on the high trust end of the spectrum, you just YOLO mode it, let it rip, and hope that it doesn't delete your prod database. Then there's control. So how do we increase control? Well, if you think about complex agent work, you can kind of think about it as a tree of work, as a DAG essentially. So here's an example where I wanted to write a report on a bunch of employment contracts. So the agent's going to say, "Okay, let me research the organization first. Then I want to review the contracts and I'm going to review for a few different things for each of the contracts. And then I'm going to draft a report at the end." This is extremely low control because essentially, I can only impose my judgment at the root level. So it's going to do all of this work and then it's going to get back to me and then I can try to talk to you again, and that's just basically the example I gave at the beginning. So very low control. Then there's planning. Planning essentially allows you to steer the agent up front and align on the approach. And so with planning here, it might say, "Okay, you should absolutely take these steps. These are correct. These are the clauses you should be looking for. This is what you want to review." So this is a good step. It gives you a bit more control. It's easier to impose what you want it to do. The problem is planning, you basically have to do all the work to just know what to do. I'm sure people have tried this in Claude Code. You basically have to go through the entire thing. It's really inefficient. It takes a long time and asks you a bunch of questions, and in the end, it's basically impossible for it to really know if you it has all the information it needs. Let's say for one of these contracts, there's a special clause. It wouldn't know that in the planning step. You can't really tell it what to do when it sees that because it hasn't done all the work. Essentially, you could compare planning to working with a co-worker that's uh comes up to you, tells you about the approach, you align with them, and then you never ever hear from them again until they deliver the final document. It's not a super nice way to collaborate. This is a good thing we have right now, but um I don't think planning is going to stay around. Then we have skills. Skills are really, really, really good. They are really good because the skills allow you to encode human judgment into essentially the nodes of work the that happen here. So I can say whenever you review confidentiality, you should do it in this way. And the really good thing about this is it allows for contingencies. So here at one of the termination reviewing termination clauses, there's a special EU law. But I have that in a skill, so that means whatever happens when it actually does the work, it knows how to handle that special case. You can't really do this with planning. There's also progressive discovery, which again is really awesome. Whatever happens, it it knows it'll pick it up. The problem is um you don't have skills for everything. The next step [snorts] is then uh to use elicitation, which means ask the user. Ask the the human. So you might have skills as well, but then instead of you giving all the info, it's going to come to you. It's going to say "Hey, here's the thing I don't know how to handle, and what do you want me to do?" This uh makes a lot of sense, first of all. Um what you don't want is you don't want the agent to be blocked. So ideally, if you implement this, what you do is you tell the agent "If you're unsure about something, make a decision, unblock yourself, but write this to a decision log." So then the human can review the decision log afterwards and reverse decisions if it needs to.

</details>

### 超越聊天：拥抱高带宽协作界面

当前AI代理与人类协作的主要模式——**聊天界面（Chat）**，被认为是**一维（One-dimensional）**且**低带宽（Low bandwidth）**的。它试图将复杂的、多分支的工作流（如前面提到的工作树）压缩成单一的线性对话，这使得用户难以提供充足的上下文信息，也无法有效处理海量问题。用户面对冗长的问答，容易感到不知所措。

演讲者提出，人类与AI应该在**高带宽的协作伪像（High bandwidth artifacts）**中进行交互。这些伪像会因行业和任务而异，但它们通常是**持久化（Persistent）**的，并提供更丰富的交互维度。

例如：
*   **文档（Document）**：这是一种耐用的交互界面，允许用户高保真地协作。用户可以高亮特定条款（如“条款三”），AI仅修改该部分。用户可以添加评论、标记AI代理或协作者，并将文档的不同部分分配给特定的AI代理。
*   **表格审查（Tabular review）**：在处理合同审查等任务时，AI可以启动一个表格视图。它会审查所有合同，并将需要用户关注的项目标记出来。用户可以快速浏览，了解AI的工作进展，并在关键点上提供判断。这种方式提供了**高控制力**，使得人类能够有效地注入专业知识，并能快速理解AI的行动。一旦用户完成审查，便可将剩余任务交给AI继续执行。

虽然**聊天框作为输入（Chat boxes as input）**具有极大的灵活性，但它不应是复杂AI代理协作的**主要模式（Main mode）**。语言本身作为一种**通用界面（Universal interface）**非常强大，但AI代理并非人类，它们不应被限制在人类的语言表达范式中。未来，AI代理应当能够利用更丰富、更直接的交互方式，如图形化界面、结构化数据等，以实现更高效、更深入的协作。

<details>
<summary>Original English</summary>

Now the right UX for this, if you imagine this work, this tree, being 10 times bigger, 100 times bigger, um you don't want this in a chat. You don't want to open up a chat and then it's infinitely long. You have to answer 50 questions. You wouldn't know what to answer. You wouldn't really be able to do it because you don't have the right context. So not chat. Chat is one-dimensional. It's a very low bandwidth interface, and it tries to collapse this work tree into a single sort of linear thing. So what's a better interface? Well, I think humans and agents should collaborate in high bandwidth artifacts. I think they need to work in things that are maybe typically persistent, um and they will look different industry to industry, vertical to vertical, depending on what task you're solving. So an example from us is um a document. That's like a durable interface where it makes sense to collaborate. That's how you collaborate with your co-workers. You can highlight clause three and it will only change clause three. You can add comments. You can tag your agents. You can tag your collaborators. You can hand off parts of the document to special agents. Another example is our tabular review, which is essentially I ask it to do um the contract review that I talked about, and it's going to say, "Okay, let me spin up a tabular review, which is like a known primitive that our users know." And it looks like this, and then it's going to say, "I'm going to review all the contracts, and I'm going to just flag a few items for you that I want your take on." And then I can go in there and I can see very quickly where the problems are. So it's high control. I it's very effective for me to instill judgment. And I can also very quickly get an idea for what the agent has actually done. So reviewing is easy. And then once I've done that, I can just kick off the rest of the agent. Right now, what we're seeing a lot is the convergence of UI, basically um this is post-hoc and linear. Uh within last 2 weeks, shipping this new UI. Um to be clear, chat boxes as input is great. I think you get a lot it's extremely flexible, allows you to do a lot of stuff, but you don't want chat to be your main mode of collaboration with a complex agent. The good thing about this is language is essentially the universal interface. It's what people use to communicate. You can do everything with the voice. Um but agents aren't humans. Just a few minutes ago, I was um talking to a potential candidate for Legal and I was describing our org chart, and um I was limited because I can only use language. I wish that I could just draw up an org chart and they could interact with it and they could use it, but I can't because I'm a human. Uh I'm limited by language, but agents are not humans, and so we should not constrain them to human language. Thank you.

</details>