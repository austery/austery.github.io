---
author: How I AI
date: '2026-03-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=o5Mi5SYSDnY
speaker: How I AI
tags:
  - agentic-workflow
  - developer-productivity
  - machine-payments
  - automated-code-review
  - cloud-development
title: Stripe 的 AI 进化：每周 1300 个机器人生成的 PR 与‘小黄人’代理体系
summary: 本期访谈深入探讨了 Stripe 如何通过名为“Minions”的 AI 代理系统，实现每周处理超过 1300 个无需人工干预（仅需审核）的拉取请求。Stripe 工程师 Steve Koliski 展示了如何通过 Slack 激活代理、利用云端环境释放开发效率，并前瞻性地演示了“机器支付协议”，让 AI 代理能够自主调用第三方服务并支付费用，将 AI 视为真正的经济主体。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Stripe
  - Tempo
products_models:
  - Goose
  - Claude
  - MCP
  - Browserbase
  - Postalform
media_books: []
status: evergreen
---
### Stripe 的 AI 自动化现状

**Steve Koliski**: 在 **Stripe**，我们每周大约有 **1,300 个 PR** 是在没有人工协助（除了最后的代码审查）的情况下落地的。我们的很多工作始于 Google 文档中的功能规划，或者是一个 **Jira** 工单，又或者是在 **Slack** 中的讨论。我只需要点击一个表情符号，菜单就会尝试通过调用 Stripe 内部的所有可用工具，一键解决该提示词提出的任务。

<details>
<summary>Original English</summary>

**Steve Koliski**: At Stripe, we're landing about 1,300 PRs that have no human assistance besides review per week. A lot of where our work begins is it could be in a Google doc as we're planning a new feature or maybe a Jira ticket comes in or we're talking about something in Slack. I can click an emoji and then the menu will sort of attempt to oneshot resolving that prompt using all the tools that are available at Stripe.

</details>

**Claravel**: 在大型组织中，好主意与将其转化为现实之间往往存在巨大的阻力。现在我不但能拥有一个这样的代理，还能让很多个代理在隔离的环境中并行运行，同时进行不同的更改。

<details>
<summary>Original English</summary>

**Claravel**: When you're in larger organizations, there's so much friction that can come between a good idea and getting it into the world. Not only can I have one of these, but I could have many, many of these running in parallel in isolated environments making isolated changes all at the same time.

</details>

**Claravel**: 你们是怎么完成所有这些代码审查的？

<details>
<summary>Original English</summary>

**Claravel**: How are you getting all this code review done?

</details>

**Steve Koliski**: 无论代码是 Steve 写的还是 Steve 的机器人写的，你仍然需要 **CI (持续集成)** 环境来提供信心，确保被修改的代码是安全的。随着代码的发布，我们采用**蓝绿部署**，以便你可以随时回滚。独立于作者的身份，这些流程都至关重要。无论你的笔记本电脑性能多么强劲，一旦你运行三四个工作树，它听起来就像飞机起飞一样，体验很糟。因此，我认为在这种多线程的**代理工程 (Agentic Engineering)** 工作中，云环境和虚拟环境对于释放开发速度至关重要。

<details>
<summary>Original English</summary>

**Steve Koliski**: Whether the text has been written by Steve or the text has been written by Steve's robot, you still want that CI environment that's providing confidence that the code that's being changed is safe and that as it rolls out, we're having blue green deployment so you can roll back too. All of that is super critical independent of the nature of the authoring of it. No matter how juiced these laptops are, you get three or four work trees in and like it starts to sound like an airplane taking off, it's no good. And so I do think on this multi-threading agentic engineering work, cloud environments and virtual environments are so important to unlock velocity.

</details>

### 什么是 Stripe Minions？

**Claravel**: 欢迎回到《How I AI》。我是 **Claravel**。今天我们邀请到了 Stripe 的软件工程师 **Steve Koliski**，他将向我们展示 Stripe 团队如何部署一群“**小黄人 (Minions)**”来完成他们的工程工作。

<details>
<summary>Original English</summary>

**Claravel**: Welcome back to How I AI. I'm Claravel. Today we have Steve Khaliski, a software engineer at Stripe, and he's going to show us how the Stripe team deploys a bunch of minions to do their engineering work.

</details>

**Claravel**: 那么，告诉我“小黄人”对你个人以及整个 Stripe 团队产生了什么影响？

<details>
<summary>Original English</summary>

**Claravel**: So, tell me what has been the effect that minions have had on you personally at Stripe and at the Stripe team as a whole?

</details>

**Steve Koliski**: 对我个人而言，我不记得上次在文本编辑器里开始工作是什么时候了。当然，我最终还是会用到编辑器，但我发现工作往往始于 Google 文档、Jira 工单或 Slack。这些是更自然的工作切入点。只有在需要实际执行或进行最终调整时，你才会进入编辑器。这感觉非常自然，尤其是开始工作的“**激活能 (Activation Energy)**”降低了很多。

如果在 Slack 线程中看到用户反馈，比如需要更新文档或构建原型，我只需点击一个表情符号，工作就开始了，而且往往直接就完成了。在 Stripe，我们每周有 1300 个 PR 是在仅有人工审核的情况下落地的。至少，编写代码、查看测试通过或失败的过程在我甚至没有参与的情况下就发生了，然后我可以中途加入，利用这种“**生成式动力 (Generative Momentum)**”进行微调。

<details>
<summary>Original English</summary>

**Steve Koliski**: Sure. So, you know, for me personally, um, I think sort of anecdotally, I don't remember the last time I I started work in the text editor, right? So, I do end up there often. Um, but, you know, what I found is that, you know, a lot of where our work begins is, you know, it could be in a in a Google doc as we're planning a new feature or maybe a Jira ticket comes in or we're talking about something in Slack and those are sort of like the more natural entry points to starting work, right? And then you end up in a text editor when it's time to, you know, actually do the work or make the final tweak. Um and it's just felt very natural. Um and it's think in particular the sort of like activation energy of starting work feels a lot lower, right? So if you know you're in a Slack thread and maybe there's a a piece of user feedback and it's something simple like a you know we have to update the docs or or maybe it's something more consequential and we just want to build a prototype. I can click an emoji and like the work begins and often the work finishes too. At Stripe we're landing about 1,300 PRs that are uh have no human assistance besides review per week. Um but at the minimum the activation energy of like starting to write code, seeing tests pass, maybe a test fails occurs without me even, you know, participating and then I can jump in and I can tweak and I can kind of like have that that momentum sort of uh sort of like generative momentum, you know, that I can I can hop in halfway through.

</details>

### 开发者体验 (DX) 与 AI 的良性循环

**Claravel**: 我喜欢这种降低“激活能”的概念。在大型组织中，好想法和执行之间往往存在很多摩擦。

<details>
<summary>Original English</summary>

**Claravel**: What I think is magical about this is I love that concept of activation energy going lower because when you're in larger organizations, there's so much friction that can come between a good idea and getting it into the world.

</details>

**Steve Koliski**: 以前，当我作为工程师想要修改 Stripe 的代码时，Stripe 是一个拥有大量服务的巨大代码库，它无法仅在我的电脑上运行。所以 Stripe 长期以来一直投资于优秀的**开发者工具**，拥有托管的开发环境。

“**Minion (小黄人)**”的想法是：我可以配置一个这样的环境，植入一个提示词，然后代理会尝试通过使用 Stripe 内部的所有工具（内部文档、CI、测试数据等）来一键解决该任务。它会不断循环尝试，直到解决问题。

<details>
<summary>Original English</summary>

**Steve Koliski**: When I as an engineer sort of in pre-AI time uh you know want to make a modification to Stripe um well Stripe is a huge codebase with tons of services um it it can't run on my computer alone so Stripe already has a long history of of you investing in great developer tooling having hosted development environments that I can spin up that you know have all the code already there and services running and I can SSH in and make modifications um and we have a ton of great CI tooling around that so that's the context. The idea with a minion is that I can provision one of those environments seated with a prompt and then the minion will sort of you know attempt to oneshot resolving that prompt using all the tools that are available at Stripe, right? So uh all of our internal documentation, our internal CI, our um you know test data, so on and so forth and it will loop through that in attempt to you know solve that prompt.

</details>

**Claravel**: 我的一位朋友 Zach 曾说过：对人类开发者有益的东西，对 AI 代理也有益。如果你投资于**开发者体验 (DX)**，你的代理也会从中受益；反之亦然。如果你想让管理层支持 DX 投资，把它挂钩到 **AI 倡议**上是一个秘密武器。

<details>
<summary>Original English</summary>

**Claravel**: One thing my friend Zach from LaunchDarkly said was look, what's good for the developer is good for the agent. So, there's this virtuous loop of if you have or do invest in developer experience for your human engineers, your agents will benefit off of that. And in turn, if you invest in developer experience or agent experience for your agent engineers, your development team benefits from that. And I think if you attach it to an AI initiative, that's like the secret way to get some of that good stuff.

</details>

**Steve Koliski**: 没错。如果一个工程师第一天入职，没有文档，没有工具，即使你把 AI 代理扔给它，它也可能因为代码库太大而导致**上下文窗口 (Context Window)** 爆炸。但如果对于 90% 的常见开发活动都有非常成熟的路径（例如添加 API 字段或方法），那么代理成功的概率就会非常高。优秀的文档对开发者和代理同样重要。

<details>
<summary>Original English</summary>

**Steve Koliski**: Yeah. I mean imagine you're, you know, some code bases are small, but you know, Stripes is huge. Imagine you show up day one and there's there's no documentation and there's no tools and they say, "Good luck." Like anyone would have trouble and even if you threw the agent at it, it's very likely that the the context window would be blown by the whole codebase. Just scanning through it to understand all the intricacies would be like impossible or extremely expensive. So if there's a very blessed path for 90% of the common activities in being a engineer at Stripe that makes the propensity that the agent succeeds really high too. So good docs for developers are uh equally important for the agent.

</details>

### 技术架构：Goose 与 MCP

**Steve Koliski**: 我们现在正在启动开发环境并运行第一个代理。我们正在启动一个 **Goose** 实例，这是运行这一切的框架（Harness）。

<details>
<summary>Original English</summary>

**Steve Koliski**: So we've now transitioned from booting up the development environment to now we're in the the first agent run. So we have that prompt that I posted in Slack here. And now what it's going to do is boot up an instance of goose that's basically the harness that's you know going to run through all this.

</details>

**Claravel**: 我喜欢你的**系统提示词 (System Prompt)**，非常高级：“完全执行此任务：[任务内容]，不许出错。” 很多人觉得必须过度设计初始提示词，但如果你有一个强大的框架，即使是松散的提示词也能产生成功的结果。

<details>
<summary>Original English</summary>

**Claravel**: I love your system prompt. So sophisticated. It says implement this task completely. Colon and then just whatever you put in. No mistakes. I think people really think they have to overarchitect their initial prompt. And I think if you have a great harness, it can go a long way to extracting out a successful outcome from a pretty loose prompt.

</details>

**Steve Koliski**: 现在的趋势是，几乎所有可以拥有 **MCP (Model Context Protocol)** 服务器的东西都已经有了。我们能够与大量内部数据进行交互。为什么选择 Goose 而不是商业方案？虽然我们也广泛使用 **Claude Code** 等工具，但 Minion 非常针对 Stripe 的开发环境进行了定制。我们 fork 了 Goose 并进行了修改，将其作为基础框架，然后应用我们自己的工具。

<details>
<summary>Original English</summary>

**Steve Koliski**: I think now most things that could have an MCP server have an MCP server. So we're able to interact with a lot of the internal data we have. In the particular case of Minion um it's very specific to like the stripe developer experience and the stripe developer environment and we had been uh experimenting with goose early on and I think in this particular case we forked it to make some modifications as well and really what we were looking like sort of a base harness and loop um to apply all of our own tools and software to.

</details>

### 代理作为经济主体：机器支付协议

**Steve Koliski**: 接下来我想展示另一个工作流。我们不仅在内部使用 AI，还在思考如何支持那些在产品中使用 AI 的企业。除了代币计费，还有第三个维度：**代理作为经济参与者**。

当代理尝试解决一个提示词时，它可能需要调用第三方服务，而这些交互是需要付费的。我们必须赋予代理“消费能力”。我们正与 **Tempo** 合作设计一种“**机器支付协议 (Machine Payment Protocol)**”。

<details>
<summary>Original English</summary>

**Steve Koliski**: So, the demo we just showed is how we're thinking about using AI internally to accelerate our product development and engineering. The second way is thinking about how we're supporting all these businesses that are leveraging AI in their own products. But there's a third side which is like this sort of idea of agents as economic actors or agents that can spend money as part of their attempt to solve a prompt. We imagine a future where third party services are going to want to sell into these kinds of experiences and that those interactions will cost money. So we have to equip uh our agents with the capacity to spend so they can not only consume tokens, but so they can also pay services as part of achieving uh the prompt.

</details>

**Steve Koliski**: 在演示中，我让代理策划一个生日派对。它自主向 **Browserbase** 支付费用以创建浏览器会话，研究派对对象的喜好（发现她喜欢抹茶）；然后它找到一家抹茶咖啡馆，并向 **Postalform** 支付费用寄出一封真实的纸质邀请函；最后，它根据消耗的代币数量，向 **Stripe Climate** 捐款以抵消碳排放。

<details>
<summary>Original English</summary>

**Steve Koliski**: I told it to research Jen Lee, figure out what would be a good idea for her birthday, find a place, send invites, and then donate to Stripe Climate. The first thing we're going to do is that we've actually paid browser base to create a new browser session. It found out she's a matcha obsessed baker. Now we're interacting with this service called postal form. Postal form will take a PDF and actually send it in the mail. We actually made a $1.65 donation to Stripe Climate to erase 4.44 kilograms of carbon based off of our 70k token usage.

</details>

**Claravel**: 这个例子清晰地展示了**代理化操作的经济模型**。除了外部交易，代理运行本身也在消耗昂贵的代币，这一切都处于一个经济框架之内。

<details>
<summary>Original English</summary>

**Claravel**: What's really interesting about this particular example is it makes it very clear the economics of doing something agentically. It also just calls out like this actually does cost you in tokens whether or not your agent is doing outside transactions. So we're already operating in an economic framework, right?

</details>

### 提示词策略与个人哲学

**Claravel**: 当 AI 不听话，或者代理无法一键完成任务时，你的提示策略是什么？你会“温柔地教导”它，还是贿赂它？

<details>
<summary>Original English</summary>

**Claravel**: When AI is not listening, when your minion does not oneshot, what is your prompting strategy? Do you gentle parent your AI? Do you bribe it?

</details>

**Steve Koliski**: 听起来可能很疯，但我一直努力保持**礼貌**。谁知道未来会发生什么，我绝对不想留下我曾对它很粗鲁的记录。

更严肃的回答是：第一，要求它解释或证明自己的行为，这非常有帮助。第二，如果我知道正确的方向，我会先走几步，留下“**面包屑 (Breadcrumbs)**”（如 git status 或 diff），然后让它根据这些线索继续。如果某个任务是重复性的，我会将其转化为一种 **Skill (技能)** 或提示模板，以便以后重新注入。

<details>
<summary>Original English</summary>

**Steve Koliski**: This sounds crazy but like I have made a concerted effort to always be polite. I definitely don't want to be caught being rude even though you never know. But the more serious answer is um one, asking it to explain or justify itself um has helped quite a bit and then I think in other cases where I know the right direction to go. I will start going in the right direction and then I will ask it to look at sort of like the git status to look at the diff or like look at other sort of like breadcrumbs that I've left as like the directional thing to help guide it.

</details>

**Claravel**: 就像爸爸教孩子骑自行车，扶着后座跑几步再松手。

<details>
<summary>Original English</summary>

**Claravel**: Got it. So, you're doing like the dad teaching his kid to ride a bike move where like your hands on the back of it and then you let it go.

</details>

**Steve Koliski**: 确实。在抚养孩子的同时看着机器人诞生，这种感觉非常奇妙。

<details>
<summary>Original English</summary>

**Steve Koliski**: It didn't really hit me until you said that, but there's something really weird about raising kids at the exact same time that the the robot emerges. That hadn't really clicked with me yet.

</details>