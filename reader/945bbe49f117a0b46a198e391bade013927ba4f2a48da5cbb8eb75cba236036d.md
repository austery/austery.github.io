---
author: AI Engineer
date: '2026-09-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xxfMT-bPEmU
speaker: AI Engineer
tags:
  - agent-infrastructure
  - knowledge-work
  - governance
  - reversibility
  - verification
title: 从编程到知识工作智能体：缺失的六项基础能力
summary: Composio 联合创始人兼 CTO Karan Vaidya 称，编程智能体进展迅速，是因为代码周边已有集中化、历史记录、上下文、验证、治理和可逆性这六项基础设施，而知识工作缺少这些；他介绍了 Composio 正在构建的对应方案。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 开场：为什么智能体只在编程领域起飞
大家好，我是 Karan Vaidya，Composio 的联合创始人兼 CTO。

如今大多数智能体的工具调用仍然发生在一个领域。不用猜，就是软件工程。其他各类工作都远远落在后面。

如果模型一直在变好，那我们为什么还只局限于智能体编程？这就是我要来回答的万亿美元问题。

<details>
<summary>Original English</summary>

>> Uh hey folks. Uh I'm Karan Vedya, co-founder and CTO of Composio. Most agentic tool calls today are still happening in one field. No guesses, it's software engineering. Every other kind of work is trailing far behind. If models keep getting better, then why are we still limited to just agentic coding? That's the trillion-dollar question I'm here to answer.

</details>

三年前，编程智能体还只是自动补全。今天，软件工程已经完全自主。我们从一路按 tab、tab、tab，变成了"让 Claude 去做就行"。简直是魔法。

为什么在编程领域发展得这么快？大多数人会觉得是模型。没错，过去两三年模型确实变得好多了，harness 也是，比如 Claude Code、Codex、Cursor。

但光靠它们自己是不够的。之所以行得通，是因为围绕编程的所有基础设施和系统，本来就是适合智能体使用的。代码自带智能体所需要的支撑：代码仓库、提交历史、测试、CI/CD、评审、linter，出了问题还能回滚。正是这些东西，让你信任智能体和代码周围的系统。

现在，我们把同样出色的智能体指向其他一切：客服、财务、销售。但在编程中表现出色的智能体，在这里却是在盲干。因为编程周边的基础设施，在其他领域根本不存在。

<details>
<summary>Original English</summary>

Three years ago, coding agents were just auto complete. Today, software engineering is fully autonomous. We went from pressing tab tab tab to let just Claude cook. That's just magic. And why did it happen so fast in coding? Most people would think it's models. Yeah, models got really better over time over the last two to three years. And so did the harnesses. Claude code, Codex, Cursor. But on their own, it wouldn't have been enough. It only worked because all the infrastructure and systems around coding were literally meant for agents. Code came with the support that agents needed. You have got the repo, the commit history, tests, CI/CD, review, linters, revert if anything goes wrong. The kind of stuff that makes you trust the agents, the systems around code. Now, we're pointing these same amazing agents at everything else. Support, finance, sales. But the agents that were doing phenomenally well in coding, are just working blind. Because the infrastructure around coding doesn't even exist in other fields. >> [snorts]

</details>

>> 那么，我们如何在编程智能体和知识工作智能体之间架起桥梁？我们认为核心是六项基础能力：编程把这六项都具备了，而知识工作一项都没有，这就是我们需要去构建的。

<details>
<summary>Original English</summary>

>> So, how do we close the bridge between coding agents and knowledge work agents? We think it's core six primitives and coding had all six of them while knowledge work doesn't have any and that's what we need to build.

</details>

### 第一项：集中化
第一是集中化。编程智能体之所以表现不错，部分原因是它们离事实来源非常近。它们知道是什么、为什么、怎么做。你把代码仓库和基础设施即代码交给它们，闭合回路，让模型去做。智能体开工时需要的一切都在同一个地方，也就是代码库。

这恰恰是知识工作今天所缺少的。比如，一笔交易分散在五个不同的平台上：记录在 Salesforce，文档在 Notion，邮件在 Gmail，对话在 Slack，客服历史在 Zendesk。没有单一的事实来源，没有一个地方能获得所有信息。一切都是分开的，每个应用都有自己的登录。

知识工作智能体在开始做事之前，就得先去把所有线索拉出来，自己把它们串起来。而这正是编程智能体起步时的基本点：它本来就已经拥有了一切。那你怎么能指望知识工作智能体做到与编程智能体同等水平的工作呢？

所以我们构建的第一样东西，就是缺失的中心：一个地方，容纳你所有的应用、所有的连接、所有的登录。这样智能体就不必费力地把它们拼接起来，而是在一个地方找到全部。它们拿到了和编程智能体起步时一样的基线，也就是代码仓库，即所有技术栈的信息汇集在一个地方。这是你的起点，你可以在此基础上给智能体授予恰当的权限。

<details>
<summary>Original English</summary>

First is centralization. Coding agents work so pretty well partly because they were very near the source of truth. They knew the what, the why and how. You give them the repo, the infrastructure as code and you close the loop and let the model cook. The agent starts at everything with everything they need all in a single place, that is the code base. This is exactly what knowledge work miss today. For example, a single deal is scattered across five different platforms. The records are in Salesforce, the docs in Notion, the emails in Gmail, conversations in Slack and the support history is in Zendesk. There's no single source of truth, single place to get all the information. Everything is separate and every app has its own login. Before a knowledge work agent can even start to do thing, it has to go and pull all the threads and kind of tie them together itself. And that's still the base point where coding agent had started. It already had it all. So, how can you expect knowledge work to do knowledge work agent to do the same level of work as coding agent? So, the first thing we build is the missing center. One place where all your apps, all your connections, all your logins exist. So, the agent doesn't need to do the hard work of stitching them all together. They find it all in a single place. And they get the baseline with the coding agent started with, which is the repo, the information across all the stacks in one single place. That's the foundation you start with and you can give right accesses to your agent.

</details>

### 第二项：历史记录
智能体接下来需要的是历史感，也就是回顾过去的能力。在代码中，这是免费得到的。Git 记录了进入的每一样东西、做过的每一处改动。所以智能体总能回头看某个改动是怎么做的、为什么某样东西行得通、为什么某样东西行不通。

想想你实际会让智能体做的事。我们过去因为某次失败回滚了一个改动，但要把它找回来很难。你能不能看一看，把它重新弄回来？它只要去翻历史，把它拿回来，然后去做就行。

历史不只是给智能体用的，也是让你留下智能体在做什么的记录。你可以看到智能体在做什么、做到哪一步、哪些事做成功了；与其相信智能体对你说的话，你可以直接去那些具体的应用里看它做了什么。

现在把同样的问题放到知识工作上。是什么让 CRM 变成了今天这个状态？我的同事是怎么写出那封促成成交的邮件的？升级一个客服问题、甚至关闭一个问题，实际流程是什么？答案散落在数百个应用里，没有一个保留历史。

所以智能体没有记忆，几乎每次都从空白状态开始。不知道之前试过什么、什么有效、什么无效。而你也完全没有东西可看。智能体运行之后告诉你它成功完成了，你并不知道它是否真的成功完成了。没有办法知道它对不对。这就是缺失的东西：工作的记录。

现在，因为一切最终都通过一个地方运行，也就是集中化，我们就能在它之上构建一层：记录。智能体采取的每一个动作，都可以跨所有其他应用被记录下来：它碰了什么、跳过了什么、什么有效、什么无效。

通过这一层，首先，智能体获得了记忆。它可以回头看类似的任务以前是怎么做的、什么是成功的，然后再次复现。它不必每次都从空白状态开始。

其次，你获得信任。你终于可以确切看到智能体在做什么。所以，与其希望它会做对的事，你可以回头检查，一旦它做了坏事就能抓住它。随着你越来越多地看到它做对事情，你会建立信任，并把更多任务交给它。

<details>
<summary>Original English</summary>

The next thing agent needs is a sense of history. The ability to look back in the past. In code, you get it for free. Git keeps a record of every single thing that went in, every single change that was made. So, the agent can always look back and see how a certain change was made, why something worked, why something didn't work. Think about the kind of thing you actually ask your agent to do. We had to revert a change in the past because of some failure, but that was pretty hard to pull off. Can you look at it and get it back again? It just reach to the history and get it back and cook it. The [snorts] history isn't just for agent. It's also for you to keep a record what the agent is doing. You can see what the agent is doing, where it is up, where it is doing successful things, and like instead of trusting what the agent is saying you, you can just go to those particular apps and look at what it has done. Now, ask those same questions about knowledge work. What led to the CRM being in a state where it is today? How did the How did my colleague craft that amazing mail that led to the closing of the deal? What's the actual process to escalate a support issue or even close one? The answers are smeared across hundreds of apps and none of them keep the history. So, the agent has no memory. It starts from blank state almost every time. No idea what was tried before, what worked, what didn't work. And you you have nothing to look at all as well. Once the agent runs, it tells you it has done successfully, you don't know if it has actually done successfully. There's no way to know if it is right or not. And that's what's missing, a record of work. Now, because everything finally runs through one single place, that centralization, we can build a layer on top of it, the record. Every single like action that agent takes can be logged across every other app. Whatever it touched, whatever it skipped, what worked, what didn't. Via this, firstly, the agent gets memory. It can look back at how similar tasks were done before, what was successful, and replicate it again. It doesn't start with a blank state all the time. Second, you get trust. You can finally see exactly what the agent is doing. So, instead of hoping it will do the right thing, you can just go back and check and catch it if it does something bad. And as you kind of see it more and more doing the right things, you'll develop the trust and offload more tasks to it.

</details>

### 第三项：上下文
智能体接下来需要的是上下文。仔细想想，上下文其实有两种。第一种是平台的形态，即架构：事物如何相互流动、如何关联、数据如何流转。就像资深工程师脑子里装着的一张地图，而初级工程师大概要花三个月才能建立起来。

第二种是风格。这不是客观上的对错，而更像是在你的公司里"好"是什么样子。也就是你们做事的方式，比如 linter、类型检查等等。也许你用了一个别人都不会用的 TypeScript 装饰器。这并不一定写在某本手册里，更多是在你的代码库里。这一切都能在代码库中找到，所以智能体只需要去看一看，就能弄清规范、你喜欢什么、linter、格式化工具等等。

再来看知识工作，情况一样。假设你要给客户写一份文档。要开始写，我得先打开数据库拉取他们的使用情况，去 PostHog 查看他们实际是怎么使用产品的，还要去 Salesforce 看他们的交易详情。这之后我才能写下文档的第一行。答案并不是孤立在其中某一个工具里。我之所以能写这份文档，是因为我把所有这些工具里的线索，拉到了我脑子里的同一个上下文中。

所以，把历史和上下文放在一起，你就能描绘出组织是如何运作的。而这一部分，智能体并不能轻易获得。

因此，在我们做了集中化和日志记录之后，刚刚构建的这份记录，既让智能体有了记忆，也让你能检查它做了什么，还做了另一件有意思的事。如果你把每个智能体所做的事记录得足够多，你就会开始看到模式，开始看到组织是如何运作的。你开始形成技能，它是对组织一直以来如何工作的某种提炼：哪些做法有效、哪些无效、过去是什么导致了失败，等等。

这份记录不再只是发生过什么的历史，而是你的公司如何运转的一幅图景。它实际上在三个不同层面起作用：一个工具总体上如何工作（适用于每个人）、一家公司如何做事、以及你个人偏好如何做事，也就是在你看来"好"是什么样子。

这正是知识工作智能体所缺失的上下文：工作实际上是怎么完成的，可以说是真正的手册，以及公司和个人用户的偏好。现在智能体可以查询它，不必再猜公司是如何运作的。

<details>
<summary>Original English</summary>

The next thing an agent needs is context. And there are really two kinds of context, if you think about it. The first the shape of shape of the platform, the architecture. How things flow into each other, how things are tied, the data flows. Like kind of like a map which a senior engineer carries in their head, and a junior engineer takes probably 3 months to develop. The second is style. This isn't what's objectively correct, but more like what good looks like in your company. So, how you do things, things like linter, type checks, etc. And maybe you use a TypeScript decorator which nobody else would. This is not exactly somewhere in a playbook, it's more in your code base. It's all available in your code base, so the agent can just go and look and figure out the specs, what you like, the like linters, the formatters, etc. Now, coming to knowledge work, the same thing. Say you're writing a doc to a customer. To even start, I would have to open the database to pull their usage, check PostHog of how they have been actually using things. And Salesforce to look at their deal details. Only then I can even start writing the first line of the doc. The answer wasn't isolated in just one of those tools. I'm able to write this is doc because I'm pulling the threads across all these tools into one single context in my head. So, putting history and context together, that's how you map how the organization works. And that part is not available to agent handily. So, as we did centralization and logging, the record we just built, the one that gives the agent memory and lets you check what it did, also does one more interesting thing. It If you log enough of what every agent is doing, you start to see patterns. You start to see how the organization works. And you start to form skills, which is some sort of distillation of how the organization has been working. Which approaches work, which don't, which what led to failures in the past, etc. The The record isn't just history of what happened anymore. It's a picture of how your company operates. And it actually works at three different levels. How a tool works in general, which is applicable to every person, how a company does things, and how you prefer to do things, what good like looks like to you. And that's the context that context that was missing for a knowledge work agent. How the work actually gets done, the real playbook of sorts, and the preference of a company of a personal user. And now the agent can query it and stop guessing how the company operates.

</details>

### 第四项：验证
编程智能体表现这么好的另一个原因是，它们会自我测试，工作会自我检查。这就是验证。智能体一写完代码，一连串检查随之而来。单元测试能抓住小错误。集成测试能抓住那些只影响三个模块之外的组件的错误。如果有任何问题，类型系统甚至不会通过运行，编译器甚至不会构建。在这之上还有更"软"的检查：linter、格式化工具、bugboard.md、评审技能等等。这些确保代码符合你们团队喜欢的方式，符合团队的标准。这一切都不需要你。智能体自己完成闭环，确保它遵循标准，并能让代码跑起来。

现在想想看。前阵子我把我的 open claw 指向了一次招聘外联：给候选人群发邮件。它运行了，发出了大量邮件。你们中有些人可能也从我的 open claw 收到了。它完全按我说的做了，但这也是一场灾难，那种会带着我的名字登上 Twitter 的灾难。是的，你们可以看到，Karan Vaidya。事情发生时我并不开心。

而且关键是，上一页幻灯片里的每一项检查本来都会通过。邮件是有效的，地址是真实的，真的送到了发过帖的真人手里。世界上没有任何最佳工具能去质疑真正重要的那个问题：这封邮件到底该不该发出去？这就是代码里的那个缺口。那些测试告诉你什么错、什么对。而这里，是互联网告诉我我错了。

所以，我们构建缺失的检查。上面那个事件的问题，不在于外联本身有错，而在于它在我还没察觉之前就发出去了。所以解决办法很简单：在它成真之前就拦住。

我们有两种做法。其一，在智能体发送任何东西之前，它会检查我以前发过的邮件草稿，看是否符合我的风格、是否符合我喜欢的好的标准。其二，在真实世界里做任何破坏性的事之前，我们给智能体提供模拟真实工具的沙箱，它们可以在这些沙箱上执行动作。这样，爆炸半径打到的就不是真实世界，而是沙箱，然后我可以在智能体做真事之前进行审查。

把这两者结合起来，你就拥有了知识工作从未有过的东西：让智能体在事情成真之前检查自己的工作。它终于可以自己闭合回路，而不必停下来等你。有了这一切，你就可以信任它所采取的行动，而不会像我一样被推文轰炸。

<details>
<summary>Original English</summary>

The other reason coding agents work so well, they test themselves. The work checks itself. Verification. The moment the agent writes a code, a stack of checks follow. The unit tests can catch small mistakes. The integration tests catch the ones that only affect components three blocks away. The type system would not even work and run if anything is going wrong. The compiler will not even build. On top of it sits the softer checks, linters, formatters, bugboard.md review skills, etc. And these ensure that the code matches the way your time team likes to follow the standards of your team. None of it needs you. The agent completes the loop on its own and makes sure that it follows the standard and is able to make the code run. Now, think about like so, there's an a while back I pointed my open claw at a hiring outreach. Mass emails to candidates. It ran. It sent tons of emails. Uh some of you might have also gotten it from my open claw. It did exactly what I told it to do. It was also a disaster. The kind that ends up on Twitter with my name on top of it. Uh yeah, I think you can see a you Karan Vaidya. Uh I was not the happiest when it happened. And here's the thing, every check from the past slide would have passed. The emails were valid, their addresses were real. It actually got to real people who posted. Uh there was no best tool in the world to actually uh question what really mattered. Should this have gone at all? That's the gap in code. These tests tell you what's wrong and right. Here, the internet told me that I was wrong. So, we build the checks that are missing. The problem in the above thread was wasn't the outreach was wrong. It was that it went out before even I getting to know. So, the fix is simple. Catch before it's even real. So, we have two ways in which we do that. One, before the agent senses anything, it checks the draft emails that I've sent before. If it matches my style, if it matches the goodness that I like. The second, before doing anything destructive in the real world scenario, we provide the agents and boxes, which mock the real tools, and they can send they can do action on top of these sandboxes. So, instead of the blast radius hitting the real world, it will hit a sandbox, and then I can review it before the agent does the real thing. Put those two together, and you've got something knowledge work never had. A way for agent to check its own work before it's even real. It can finally close its own loop instead of stopping to wait for you. And with all that, you can trust the action it is taking without you getting bombarded with the tweets that I shoot.

</details>

### 第五项：治理
智能体接下来需要的是治理。建立信任就是控制智能体能做什么，在智能体周围筑起合适的围墙。在代码中，这基本上已经解决了，而且有多个层次。智能体可以在自己的分支上随心所欲，但不能合并到 main。在它合并到 main 之间，有一位人类评审者把关。关键文件有代码所有者，所以每当它碰其中任何一个，相应的人就会介入。我们用智能体发布到预览部署，绝不让它碰生产部署，所以我们在那里做了控制。

治理不是单一的关卡，而是多道关卡，每一道的大小取决于它所暴露的爆炸半径。这些都不会在安全的路径上拖慢智能体，只是防止它把生产环境搞砸。这些界线越严，你就越能信任智能体，放手让它去大干。

你可能看到过这个例子：Meta Superintelligence Lab 的对齐负责人把一个智能体接到自己的邮箱，它开始毁掉她的邮件，删除了很多。她让它停下，它还是继续。最后她不得不跑到一台实体机器前去阻止它。但到那时，已经有 200 封邮件真的消失了。她事先在提示词里告诉过它，这类情况要先确认再行动。但那只是一条提示词，很可能已经被压缩掉了。如果一个唯一的工作就是 AI 对齐的人，都不能正确地给智能体写提示，那恐怕我们谁都做不到。这才是这些智能体如此难以信任的真正原因：不是因为它们比编程智能体更差，而是因为它们周围没有围墙。

在代码中，围墙在我们早期开发时就已经内置在系统里了。知识工作这边也零零星星有一些，比如 Gmail 有 scope，Salesforce 有权限级别。但它们散落得到处都是，很难实现真正的控制，大多数人最后只能靠提示词来做。而提示词是脆弱的。智能体会找到那些漏洞，内容会被压缩掉。到了规模化的时候，这些围栏中总有一道会破，你也会落到同样的境地，你的 200 封重要邮件消失不见。

那么，究竟什么能阻止它？不是更好的指令，而是智能体即使忘了围墙存在也无法越过的墙。所以我们分两层来构建这些墙。

第一层是确定性的，控制智能体能触及什么、能访问什么。比如，招聘智能体或许只能读邮件；客服智能体可以创建邮件草稿，但不能真正发送。这条边界存在于智能体之外，智能体无法与之争辩，也不会忘记或被压缩掉。那条指令之所以失败，是因为它存在于智能体的记忆里、存在于提示词中；这一层则不然。

但光有访问控制也救不了她，因为她当时正在构建的就是一个邮件智能体，所以它显然需要访问那个邮箱。我们做的另一件事是提供策略：你可以用自然语言定义，即便有了那些访问权限，智能体还能做什么。比如，没有我的许可，绝不删除超过 10 封邮件；绝不给某个特定域名之外的地址发邮件。这些规则即使在有访问权限的情况下，也控制着行为。

所以这两者之间，一层控制智能体能触及什么，另一层控制它在这些触及范围内能做什么行为。合在一起，就是针对智能体的真正治理。不是要求智能体守规矩，而是强制规定它能做什么。

<details>
<summary>Original English</summary>

Next thing the agent needs is governance. Building trust is controlling what the agent can do. Putting up the right walls around the agents. In code, this is mostly solved and like has multiple layers. The agent can do whatever it wants on its own branch, but it can't merge to main. A human reviewer sits in between it merging to main. The critical files have code owners. So, whenever it touches one of them, the right people are getting involved. Uh we use agents to ship to preview deployments. Never let it touch the production deployments, so we control it there. The governance is not a single gate, but multiple of them, and each varying its sizes depending on the blast radius it exposes. None of it slows the agent down in safe paths. Just prevents it from up production. And the tighter those lines are, the more you can trust the agent and let it go berserk. You probably saw this one. The director of alignment at Meta Superintelligence Lab hooked up an agent to its email and it started destroying its email, deleting a lot of them. She told it to stop. It kept going. Finally, she had to run to a physical machine to stop it. But by then, 200 emails had actually vanished. She had told it beforehand in prompt to confirm before acting on such cases. But that was just a prompt which probably would have compacted away. And if someone whose sole job is AI alignment can't prompt it the agent correctly, then probably none of us can. And that's the real reason these agents are so hard to trust. Not because they're worse than the coding agents, but because there's no wall around them. In code, the wall was already built into the system while we were developing earlier. Knowledge work also has some bits and pieces here and there. For example, Gmail has scopes, Salesforce has permission levels. But it's so scattered all over the place that it's very hard to have real control and mostly people end up doing it via prompting. And prompting is fragile. The agent will find those loopholes. Things will get compacted away. And at scale, uh one of these fence will break and you'll also be in the same condition where 200 of your important emails are vanishing. So, what would actually stop it? Not like a better instruction, but wall that the agent can't cross even if it forgot that wall existed. So, we build these walls in two layers. The first layer is deterministic, control over what the agent can reach, what it has access to. Um a hiring agent can probably just read the emails. A support agent can create a draft email, but not actually send it. The boundary lives outside these agents. It can't be argued with by the agent or forgotten or compacted. Use instruction failed because it lived in agent's memory in the prompt. This doesn't. Uh but access alone wouldn't have saved her because she was actually building an email agent. So it definitely needed access to that email. Um the other thing that we do is provide policies, which is you can define natural language policies of what the agent can do even with those accesses. So things like never delete more than 10 emails without my permission. Never email outside a particular domain. Rules that with even those access control the behavior. So between those two things, one layer controls the what the agent can reach and the other layer can control the behavior with what it can do with that reach. Together, it's real governance for the agent. Not asking the agent to behave, but enforcing it what it can do.

</details>

### 第六项：可逆性
最后一根支柱是可逆性。这是事情出错时我们会走到的地方：我能撤销吗？在代码中，你几乎总是可以。每一次改动都有记录，事情可以退回去。你可以 revert 上一次提交，或者用 bisect 找到搞坏生产环境的那次提交并回滚。

我不是说这样就好。我不会假装那样。如果东西上了生产并出了问题，那总是糟糕的，但它仍然不是永久的，你仍然可以退回来。这就是让你有信心让智能体去做、让它们施展一点魔法的原因，因为即使它们把事情搞坏了，你也有一条退路。

而对知识工作来说，没有撤销按钮。想想你的收件箱，那 200 封邮件没了，消失了。顺便说，那还算是正常情况。灾难情况是已经发出的邮件，你无法撤回；已经汇出的一笔汇款，你要不回那笔钱；一条被删除的记录，永远消失。知识工作中的大多数动作其实都没有撤销按钮。

这改变了整个等式，改变了爆炸半径。有了代码，你可以事后再信任智能体：让它跑，检查结果，错了就撤销。而在这里，没有回头路。你剩下的唯一办法，是在智能体行动之前就信任它。这就是这些智能体让人觉得危险的原因，是编程智能体从未有过的那种。不是它们经常失败，而是在这里，失败是永久的。所以，要么你完全把工作前置，要么就永远不让它行动。

说实话，可逆性是知识工作中最难复制的。像代码那样真正的撤销，可能并不存在于知识工作的所有场景中。但我们有一些存在撤销的场景，我们会调用它们。比如你添加了一个标签，之后可以把标签移除。

但对于完全无法撤销的动作，比如硬删除、让邮件从你的收件箱中消失，我们同样提供一个沙箱：智能体先在沙箱里做这件事，你可以审查，然后才真正进入生产环境。这一切都不会触及真实世界。这就是整个翻转：在代码中，你可以在错误发生后撤销；在这里，你在错误发生之前就抓住它。时机不同，结果相同：错误不会留下。

再想想她那个例子。我们可以撤销的动作，就给它一个撤销按钮。我们无法撤销的，智能体会先打到沙箱上，而她会收到通知：你的 1,200 封邮件将被删除，你要这样做吗？此时还没有执行。

不过，在我们处理的数十亿次动作中，我们一路在学习哪些可以退回、哪些不能，并据此准备沙箱。

<details>
<summary>Original English</summary>

The last pillar, reversibility. And this is the one of the Uh this is where we reach when things go wrong. Can I undo it? In code, you almost always can. Every change is recorded. Things can be walked back. You can get revert the last commit or you can get bisect to the commit that broke your production and revert it. Um now Like I'm not saying it's good. I I won't pretend like that. If things go in production and break, it's always bad, but it's still not permanent. You can still walk back from it. And that's what gives you confidence to let your agents cook and let them do some magic because even if they they break the things, you can you have a pathway back. For knowledge work, there is no undo button. Things Like think about use inbox. Those 200 emails are gone. They have vanished. That's the normal case, by the way. The disaster case is a sent email, which you can't revert back. A wire that has already been made. So you can't get that money back. A deleted record, gone forever. Most actions actually in knowledge work don't have an undo button. And that changes the whole equation. Uh that changes the blast radius. Uh with code, you can trust the agent after the fact. Let it run, check the result, undo if it's wrong. Out here, there's no coming back. The only place left for you is to is to trust before the agent acts. That's what makes these agents feel dangerous in a way coding agents never did. It's not that they fail often. It's that out there failure is forever. So, either you completely go up front or never let it act. Let me be honest, reversibility is the hardest to replicate in knowledge work. Real undo, the way it exists for code, probably doesn't exist in all the scenarios in knowledge work. But we have some scenarios where undo exists and we call them. So, let's say you add a label. You can remove the label afterwards. But for actions that you can't undo at all, like hard deletes that disappear the emails from your inbox, we again provide a sandbox where the agent can do the thing first in the sandbox and you can review it and then actually goes into the production environment. None of it touches the real world. That's the whole flip. In code, you can undo the mistake after it happens. Here, you catch it before it does. Different timing, same result, a mistake that won't stick. Think about you again. The actions we could reverse, we would give it a reverse button. The ones we couldn't, the agent would hit the sandbox first and she would be notified, your 1,200 emails are going to get deleted. Do you want it? It's not done yet. Uh but across billions of actions that we're going through, we are learning on the way which ones can be walked back, which ones can't, and preparing the sandbox accordingly.

</details>

### 结语：瓶颈已经转移
如果今天你只带走一件事，那就是这个：两年来，模型是瓶颈，所以大家都在竞相追求越来越好的模型。现在模型已经好到软件工程 100% 自主的程度。但现在，其他一切都成了瓶颈。

那个写你代码的同一个模型，也能做你的招聘、销售和其他知识工作。但现在它是在盲干：没有历史，没有上下文，没有验证的办法，没有护栏，没有撤销。所以瓶颈已经转移了。现在是还没有人构建出来的基础设施。这就是我们在 Composio 正在构建的东西。

我们总共支撑着十亿次以上的工具调用，每月有 3 亿次工具调用。如果你在构建智能体，只要把它指向 Composio，就能看到知识工作中魔法发生。如果你想构建 AI 智能体未来的底座，那请来找我。我们确实在招人，还有很多很多事情要做。

模型会不断变好，瓶颈不会是模型，而会是它周围的东西。谢谢。

<details>
<summary>Original English</summary>

If you take one thing away today, take this. For 2 years, the model was the bottleneck. So, everybody was racing towards better and better model. Now, the models have gotten good enough where software engineering is 100% autonomous. But, now everything else is the bottleneck. This the same model that writes your code can also do your hiring, sales, and other knowledge work. Um but, it right now it's working blind. No history, no context, no ways to verify, no guardrails, no undo. So, the bottleneck has moved. Now, it's infrastructure that nobody has yet built. And that's what we are building at Composio. Yeah. We are powering billion plus tool calls in total. Uh 300 million tool calls happening every month. And if you are building an agent, just point it to Composio and see the magic happen for knowledge work. And if you want to build the future of substrate of AI agents, then please come to me. We are definitely hiring, and there's a lot left to do. The models will keep getting better. The bottleneck won't be models. It will be the things around it. Thank you.

</details>