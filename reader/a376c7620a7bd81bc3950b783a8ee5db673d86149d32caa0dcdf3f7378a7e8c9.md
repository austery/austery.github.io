---
author: The Pragmatic Engineer
date: '2026-03-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=NMs8C2_3M0w
speaker: The Pragmatic Engineer
tags:
  - ai-agents
  - autonomous-systems
  - iterative-development
  - model-evaluation
  - engineering-culture
title: Ramp构建AI产品经验：从代理到文化转型
summary: 本次演讲深入探讨了Ramp在构建AI产品方面的经验，特别介绍了其如何利用AI代理实现财务自动化，如费用政策代理。演讲强调了从构建大量单一功能代理转向构建拥有千种技能的单一代理的范式转变，并分享了在迭代开发、数据标注、评估和内部工具（如Ramp Inspect）方面的实践。最后，讨论了AI对工程文化和团队生产力的深远影响，以及如何通过AI赋能实现业务增长和创新。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Ramp
  - OpenAI
products_models:
  - GPT-5.3
  - Opus
  - Gemini 3 Pro
  - Opus 4.6
  - ChatGPT
  - Ramp Inspect
media_books: []
status: evergreen
---
### Ramp的AI战略与范式转变

**Nick**: 今天我们将讨论 **Ramp** 的AI应用。我将快速介绍一下 **Ramp** 是什么。简而言之，我们将通过一个最简单的报销用例来讲解，我相信大家都会有共鸣，因为我看到大家都在喝咖啡。然后，我们将快速谈谈今年我们在构建无数代理时学到的一个教训，以及自2月6日以来正在发生的范式转变。接着，我们将深入探讨我们如何构建了最受欢迎的代理之一——**政策代理**。最后，我们将深入研究我们为此所需的基础设施建设，以及在我看来最重要的是，每个团队都需要发生的文化转变，以便能够以最快、最具影响力的方式将产品交付给客户。

<details>
<summary>Original English</summary>

**Nick**: Today we're going to talk about AI at **RAMP** and I'm going to give a quick introduction into what **RAMP** is. Briefly, we're going to walk through the simplest possible expense use case that you guys can all resonate because I see everybody's drinking coffee. And then we're going to talk quickly about a lesson that we learned this year while we were building gazillion agents and sort of the pivot in the paradigm that's happening especially after February 6. And then we're going to double click onto how we built one of our most popular agents, the **policy agent**. And then finally we'll dig in into the infrastructure build that this is requiring to do on our side and in my mind most importantly the culture shift that needs to happen on everyone's teams in order to be able to operate in a way that delivers products into the hands of your customers in the fastest and most impactful way.

</details>

**Nick**: 言归正传，快速介绍一下 **Ramp**。我们是现代企业排名第一的财务平台，拥有超过5万名客户，致力于为您节省时间和金钱。我看到这里有些名牌上写着我们客户的名字，感谢你们成为我们的客户。这真的很令人兴奋。很快，一杯咖啡通常会花费你大约15分钟的时间，因为你需要做三件简单却耗时的事情。这在公司内部会累积起来，而 **Ramp** 以最简单的方式，就是压缩时间并返还金钱。因此，一个简单的交易流程，从刷卡到撰写备忘录，到根据您的 **总账（GL）** 对交易进行分类，再到获取收据并附上收据，以及将商家标准化到您的商家库存中，所有这些都在 **Ramp** 通过代理完成。这是我们第一次尝试，大概三年前，我们开始用AI做这些一次性任务，比如标准化商家、撰写备忘录，随着模型变得越来越好，效果也非常好。

<details>
<summary>Original English</summary>

**Nick**: So without further ado, a quick intro about **RAMP**. We are number one finance platform for modern businesses. We have 50,000 plus customers and we're in the business of saving you time and money. I've seen some of those names on the name tags here. So thank you for being customers. Really exciting. Really quickly. So a cup of coffee usually takes about 15 minutes of your time because you got to do these three simple things which unfortunately take minutes. This compounds through the company and what **RAM** does in the simplest possible way we just condense time and return money back. So a simple story of a transaction from tapping the card to writing a memo to classifying the transaction according to your **GL** to sourcing the receipt attaching the receipt normalizing the merchant to your inventory of merchants is all done agentically at **Ramp** and this was our first foray, probably by now, about 3 years ago we started doing these oneshot things with AI, normalize as merchant, write a memo and it's been working really really well as the models get better.

</details>

**Nick**: 公司里还在发生什么？实际上，公司里的每个角色都在大量手动工作上浪费时间。从应付账款文员到您的财务团队，从您的采购团队，再到更多的财务工作，以及您的数据团队。在 **Ramp**，我们以前有一个名为“帮助数据”的频道，有人会请求一个CSV文件，然后一个可怜的人就会去写SQL查询。大约一年半前，我们替换了它。所以，大量时间被花费，而且复杂性呈 **Ramp** 形状，随着您完成不同的工作，复杂性只会增加。如果大家看过 **超级碗**，可能会熟悉我们的代理 **Brian**。我们为每一个需要完成的工作都编写了大量的代理，最终目标是覆盖管理员、员工和财务团队所做的所有与赚钱不直接相关的工作。我们希望大家都能赚钱，专注于客户，而不是如何结账。

<details>
<summary>Original English</summary>

**Nick**: What else is going on at the company? Well, literally every persona at the company is wasting time on a lot of manual work. So from AP clerks to your finance team, from your purchasing teams, keep going to more finance work, your data teams. At **RAMP** we used to have a channel called help data where somebody will ask for a CSV and a poor person will go and write a SQL query. We replaced it about a year and a half ago. So a lot of time being spent and the complexity has a **Ramp** shape. It only increases as you go through different jobs to be done. So if you guys watch **Super Bowl** you might familiar with **Brian** our agent. So we've been writing a lot of agents literally for every job to be done to cover the entirety in the end state the entirety of what admins employees and finance teams are doing that is not directly related to making the money. We want you all to be making money and focus on your customers not on how to close the books.

</details>

**Nick**: 但在过去几周发生的事情是，我们正在经历软件领域最激动人心的范式转变。它需要彻底的重新思考，并随之简化您的技术栈。我们学到的是，您不需要构建一千个代理。去年，我们特意允许每个团队进行实验，结果我们最终可能用四种不同的方式来做同一件事，无论是同步代理还是后台代理。但实际上，您希望将您的框架导向一个拥有千种技能的单一代理。

<details>
<summary>Original English</summary>

**Nick**: But what's been happening for the past few weeks is that we're living through the most exciting paradigm shift in software. And it requires complete rethink and with rethink simplification of your stack. So what we learned is you don't need to build a thousand agents. We intentionally last year allowed each individual team to go and experiment and we ended up maybe with four different ways of doing the same thing both for synchronous agents as well as for background agents. But instead you want to drive your framework towards a single agent with a thousand skills.

</details>

**Nick**: 那么，我们来谈谈传统软件通常关注什么。在现代AI技术栈中，每个流程都归结为拥有一个事件。例如，您收到一张发票并想支付它。还有一些提示指令，说明您想如何处理它，以及一些 **护栏（guardrails）**，比如费用政策或应付账款政策。还有上下文，即代理应该考虑的数据，最后是工具。这些是您可以执行的API和操作。传统上，软件只关注第四和第五点。在新范式中，软件正在做所有事情。因此，您需要专注于构建一个能够无需人工或只需极少人工监督就能反应、推理和行动的 **自主行动系统**。

<details>
<summary>Original English</summary>

**Nick**: So let's talk about what the software traditionally used to focus on. So every process especially in the modern AI stack boils down to having an event. So you can receive an invoice and you want to pay it. Some prompt instructions of what you want to do with it and some guardrails like a policy, like an expense policy or a payables policy. Context, what is the data that the agent should consider and then finally tools. These are APIs and actions that you can do. And traditionally software would focus on only four and five. In the new paradigm software is doing everything. So you want to focus on building an autonomous system of action that can react, reason and act without a human or with very little human supervision.

</details>

### Omnihat与政策代理的实践

**Nick**: 那么，这对于我们正在构建的东西意味着什么呢？首先，我们决定将与代理的交互——即口头交互——整合到一个单一的**对话式用户体验（conversational UX）**中。去年年底，我们实际上有大约五种不同的对话式用户体验。现在，我们已将其整合到我们称之为 **Omnihat** 的产品中。**Omni** 意指无处不在。它现在正部署到产品的每一个界面。它与传统用户体验配合良好，因为您仍然需要表格和按钮，而且您不总是想与软件对话。

<details>
<summary>Original English</summary>

**Nick**: So what does it mean in terms of what we're building? So first we decided we're going to consolidate the interactions, verbal interactions with the agents to a single conversational UX. We literally at the end of last year we had about five different conversational UXs. We now have consolidated it into what we call an **omnihat**. **Omni** meaning for omniresent. It is now being deployed to every surface of the product. And it works well with the traditional UX because you still need tables and buttons and you don't always want to be talking to your software.

</details>

**Nick**: 这是一个 **Omnihat** 的良好示例：请入职一名新员工。**Omnihat** 可以将员工解析为员工ID，并通过 **人力资源系统（HS）** 工具查找他们的公司结构。它发现了一个我们之前创建的名为“新员工手册”的 **代理工作流（agentic workflow）**。代理会询问：“您希望我使用此手册来为该员工办理入职吗？”这如何实现呢？我们构建了一个内部轻量级代理框架，它能与工程师快速构建的工具进行编排。最近，我们有一位产品经理 **vibe-code** 了大约20个工具。因此，工程师不再需要构建这些工具。有时您的工作流很复杂，例如员工入职包括四个步骤。您可以在 **Ramp** 上描述当新员工加入时您希望发生什么：给他们一张卡；确保他们每笔交易都有收据；在 **Slack** 上祝贺他们，并在两周后与他们进行一次检查。我们现在能够将这些编译成一个可运行的、确定性的工作流，然后交给代理执行。**Playbook** 利用工具，这就是这一切如何协同工作。

<details>
<summary>Original English</summary>

**Nick**: But this is a good example of what **omnihat** looks like. Please on board a new employee. **Omnihat** can resolve an employee to an employee ID and look up through an **HS** tool their corporate structure. And it found a workflow, a genic workflow that we created previously called the new hire playbook. And the agent is asking would you like me to onboard the person using this playbook? How is this possible? We built an in-house lightweight agent framework that provides orchestration with tools that engineers are very quickly building and most recently we have one product manager **vibe-code** about 20 tools. So engineers are no longer needed to build those tools. And sometimes your workflows are involved such as employment boarding consists of four steps. So you can just go on **Ramp** and describe what do you want to happen when a new employee joins. Give them a card. Make sure they get receipts for every transaction. Congratulate them on **Slack** and check in with them in two weeks. We now are able to compile this into a runnable deterministic workflow and then give it to the agent to execute. **Playbooks** make use of tools and how this all comes together.

</details>

**Nick**: 接下来，**Viral** 将详细介绍一个例子：刷卡后，软件中会实时进行政策审查，**政策代理** 会强制执行您公司在支出方面的要求。因此，将 **Ramp** 卡发放给公司中的每一位员工都是非常安全的。并且，还有一个与**会计编码代理**之间的交接，该代理会根据您的后台团队和财务团队的规则对交易进行分类。作为雇主，我们不知道某些交易应该如何与我们的 **总账（GL）** 匹配，而这正是典型的传统产品会做的事情——它们会将其暴露给您。因此，代理在这方面做得更好，因为它拥有您的 **会计科目表（chart of accounts）** 的完整上下文，它了解您的 **企业资源规划（ERP）** 系统，然后它可以自动批准，或者在最坏的情况下，它会让人工介入，审查重要性或通知存在超政策支出。接下来，请欢迎 **Viral**，他将深入探讨 **政策代理**。

<details>
<summary>Original English</summary>

**Nick**: This is an example which **Viral** is going to double click. Next is upon swiping the card there's a real-time policy review that's happening directly in the software and **policy agent** enforces your company requirements with regard to spend. Therefore it's very safe to give **RAM** cards to literally every employee in your company. And there's a handoff happening with an accounting coding agent that classifies this transaction applies the rules of your back office team of your finance team as an employer have no idea how certain transaction should match to our **GL** and that's what typical traditional products would do. They will expose it to you. So the agent is much better at doing it because it has the full context of your **chart of accounts**. It understands your **ERP** and then it can either auto approve or in the worst case scenario it will involve the human in the loop to review materiality or notify that there is an out of policy spend. With that, please welcome **Viral** who'll dive deeper into the **policy agent**.

</details>

**Viral**: **Nick** 谢谢。太棒了。很多财务团队基本上每天都要看这样的收据，他们可能有成百上千张。如果你让我看这张收据，并决定是否批准或拒绝这笔交易，我可能会犯错。

<details>
<summary>Original English</summary>

**Viral**: Thanks **Nick**. Awesome. So, a lot of finance teams are looking at receipts like this basically every day and maybe they might have hundreds or thousands of these. If you told me to look at this and decide if I should approve or reject this transaction, I'm probably going to make a mistake.

</details>

**Viral**: 所以，**政策代理** 会根据这张图片和我们所有的交易数据进行推理，并告诉我收据上有八位客人。我当时看的时候几乎没注意到。它低于我们内部每人80美元的上限。他们是去吃团队欢迎晚餐的，所以因为金额也经过了验证，并且商家信息也符合，**政策代理** 告诉我批准这笔交易。同样地，对于这笔 **OpenAI** 交易，**Anand** 正在测试一些 **ChatGPT** 功能，所以 **政策代理** 告诉我这是一笔有效的商务支出，并指示我批准。然后，这笔3美元的面包店费用被拒绝了，因为它不是加班采购的一部分，也没有发生在周末。

<details>
<summary>Original English</summary>

**Viral**: So, **policy agent** basically reasons on this image and all the transaction data that we have and told me that there were eight guests in the receipt. I could barely see that when I was looking at it. It was below the $80 a person cap that we have internally. They were going for a team welcome dinner and so because the amount was verified as well and the merchant **policy agent** told me to approve this transaction. Similarly for this **OpenAI** transaction, **Anand** was testing out some **ChatGPT** features and so **policy agent** told me this was a valid business expense and told me to approve it and then this $3 bakery charge was rejected because it wasn't part of an overtime purchase and it didn't happen on the weekend.

</details>

**Viral**: 所以我们真的把这看作是重新思考 **Ramp** 设置方式的一个机会。财务总监和财务团队每天都在查看这些交易并做出决策。我们的一家 **财富500强** 客户来找我们说：“嘿，你们能确保批准这类费用，拒绝这类费用吗？”他们基本上列出了 **Ramp** 应该遵循的所有规则。我们把这看作一个机会，而不是增加更多定义我们产品的增量确定性规则。我参与了这些规则的早期版本开发，但实际上我们借鉴了 **Andre Karpathy** 的观点，他说 **英语是新的编程语言**，并将费用政策本身变成了规则。

<details>
<summary>Original English</summary>

**Viral**: So really we looked at this as an opportunity to rethink how **Ramp** was set up. Controllers and finance teams are looking at transactions like these and making these decisions every day. And a **Fortune 500** company that is one of our customers was coming to us and saying, "Hey, can you make sure that you approve these types of expenses and reject these types of expenses?" And they basically had a list of all the rules that **RAMP** should follow. And we kind of saw this as an opportunity not to kind of add more incremental deterministic rules that kind of defined our product. And I worked on some of the first versions of these, but actually kind of take out a page from **Andre Karpathy** saying that **English is the new programming language** and kind of turn the expense policy into the rules themselves.

</details>

**Viral**: 您可以在左侧看到 **Ramp** 的费用政策，这是我们生产环境的截图，但我们看到我们的 **政策代理** 产品取得了非常好的应用效果，而且它需要真正有机地启动。所以我们像早期创业公司一样运作。我们在 **Ramp** 已经非常注重增量和快速迭代，但我们找到了一些设计合作伙伴，比如那家 **财富500强** 公司。我们迭代得非常快，每周都与他们开会，以确切了解我们想要听到的反馈以及我们可以改进的地方。

<details>
<summary>Original English</summary>

**Viral**: So you can see **Ramp**'s expense policy on the left and this is a screenshot from our production environment but we are seeing really great use out of our **policy agent** product and it kind of needed to start really organically. So we kind of operated like an early stage startup. We're already very incremental and fast at **Ramp** but we found some design partners like that **Fortune 500** company. We iterated really quickly and we had weekly meetings with all of them to kind of understand exactly what feedback we wanted to hear and what we could improve.

</details>

### AI产品开发的关键经验

**Viral**: 我认为我们在 **Ramp** 内部意识到一个主要且重要的事情是，我们真的需要接受 **AI产品不能一次性完成** 的事实。你需要从简单的事情开始。所以，只要你的团队中的每个人，包括产品经理、设计师、工程师，都达成共识，即第一天不会有完美的产品，我认为这实际上是主要的文化学习之一。

<details>
<summary>Original English</summary>

**Viral**: I think one of the main important things that we realized across **Ramp** is that we really needed to lean into the fact that **AI products cannot be oneshotted**. You need to start with something simple. And so as long as everyone on your team, PMs, designers, engineers are aligned, that you're not going to have perfection on day one. I think that was actually one of the main cultural learnings.

</details>

**Viral**: 因此，我们在内部 **“狗食”（dogfooded）** 了很多这项工作，从一个更受限制的问题开始：决定我们与同事的咖啡交易是否应该被批准或拒绝。根据我们财务团队的说法，这些是单笔小额、低风险的交易。所以我们从这些交易开始，而早期的一个经验，尤其是在我们将其发布到生产环境时，是 **政策代理** 出错的原因，很大程度上不是模型本身的问题，而是我们提供给 **大型语言模型（LLMs）** 的上下文不足。我们本可以在开始任何工程工作之前就坐下来思考所有上下文，但我们意识到最好的方法是学习我们的一些实时内部数据。例如，我们了解到在查看费用政策文件时，员工的角色和头衔非常重要，某些级别的员工（例如高管）可能有更高的限额，也许他们可以在某些航班上乘坐头等舱。因此，我们开始从收据中提取更多信息，并从 **Ramp** 上已有的 **人力资源系统（HRS）** 字段中提取信息。接下来，**Will** 将向大家详细介绍我们为实施 **政策代理** 所经历的迭代过程以及沿途的一些经验教训。

<details>
<summary>Original English</summary>

**Viral**: And so we **dog fooded** a lot of this work internally and started with an even more constrained problem of trying to decide whether our coffee with a colleague transaction should be approved or rejected. These are single dollar amount transactions that are low risk according to our finance team. And so we started with these transactions and one of the early learnings especially as we kind of released this into production was that a lot of the reason that **policy agent** would be wrong would be less on the models themselves and more about the context that we were giving to **LLMs** themselves. So we could have sat down and thought about all the context in the beginning before we even kicked off any engineering work. But we realized actually the best thing would be to learn from some of our live internal data. And so for example we learned that the role and the title of an employee is super important when looking at expense policy docs certain levels, for example, might have higher limits, maybe they can fly on first class for certain flights and so we started extracting more information from receipts, started pulling in information from **HRS** fields that are already on **Ramp** and so **Will** is going to kind of talk you through exactly the iterations that we went through to implement **policy agent** and some of the learnings along the down.

</details>

**Will**: 是的。好的，太棒了。所以，当我们最初在内部构建 **政策代理** 时，我们梦想宏大。我们想，“嘿，让我们自动化所有财务工作。让我们自动化所有审查。”但实际上，我们必须从小处着手。比如，那杯咖啡，它在你的费用政策中吗？我们这样做的原因是，尽管自动化这个问题听起来很简单，比如“这是否符合政策？”这个问题很简单。但它会变得复杂。就像 **Viral** 说的，我们本可以一开始就弄清楚我们有什么上下文，如何添加它，如何以 **LLM** 能理解的方式将其整合起来。但我们知道，即使我们第一次就做对了所有事情，一旦你将其应用并推广到其他业务，它很可能还是会出错。

<details>
<summary>Original English</summary>

**Will**: Yeah. All right. Cool. Awesome. So when we first started building the **policy agent** internally, we dream, we went big. We're like, hey, let's automate all of finance. Let's automate all reviews. But when it came down to it, we actually had to start small. Is that cup of coffee, you know, in your expense policy? And the reason that we did that was because even though the problem sounds simple to automate, you know, is this a simple question. Is this in policy or not? It was going to grow to be complex. Kind of like **Viral** said, we could have gone down and we could have figured out what context do we have, how can we add it, how can we put it all together in a way that **LLM** can understand and, you know, put it all together from the get-go. But we knew that even if we aimed and got everything right the first time, it was probably going to be wrong once you applied and generalized it and went to another business.

</details>

**Will**: 所以，我认为系统越简单，就越容易在其基础上进行迭代。一旦你迭代，你就会知道什么有效，什么无效，然后你就可以在此基础上增加复杂性。我认为这对于构建 **大型语言模型（LLM）** 或代理启动器来说非常重要。因此，我们从非常简单的方式开始，这是一种经典模式：当有费用进来时，我们检索其相关上下文，然后通过一系列定义明确的 **LLM** 调用，例如“这是否符合政策？为什么符合政策？我们如何向用户展示它符合政策？”然后给出一个对用户有意义的输出。最终我们了解到，每种费用都有所不同，我们可以根据它是差旅、餐饮还是娱乐来对费用进行分类，然后进行 **条件提示（conditional prompting）**，并根据这些检索上下文，并在这里传递 **LLM** 调用，并给它一些工具，以便它也能自主决定，“嘿，我实际上需要航班信息”，或者“我需要这个员工的级别”，然后将这些层层叠加。

<details>
<summary>Original English</summary>

**Will**: So the simpler the system, I think the easier it is to iterate on top of it. And once you iterate, you know what's going to work, you know what's not, and you can kind of layer complexity on top of that. And I think that's pretty important to keep in mind when you're building an **LLM** or an agent starter. So for us we started really simple, very, kind of the classic, you know, we have an expense come in, retrieve the context around it, we pass it through a series of **LLM** calls that are very well defined of like, hey, is this in policy, why is it in policy, how can we show the user that's in policy and then give an output that makes sense in this way to the user. Eventually we learned that each expense is kind of different, we can classify an expense based on is it travel, is it a meal, is it entertainment, do **conditional prompting** and then retrieve context based on that and passages, here's **LLM** calls and give it some tools so that it can also autonomously decide, hey, I need flight information actually or I need this employee's level and kind of layer that on top.

</details>

**Will**: 经过几次迭代，我们形成了一个完整的 **代理工作流**。我们最终拥有了复杂的工具，可以读取我们所有平台的数据，这些工具在我们所有的代理之间共享，不仅仅是 **政策代理**。我们有一个公司内部的 **工具箱**，我们所有的代理都可以轻松地使用。我们还赋予了它写入的能力。所以它现在可以编写决策，编写推理，代表用户自动批准费用。而且它会循环执行。所以，现在它更像一个 **黑箱**。这就是你所得到的权衡。当你从简单系统转向复杂系统时，你的能力会提高，你的自主性会提高，你的代理能做更多事情，你的AI能做更多事情，你的AI看起来更智能。但作为交换，你将失去 **可追溯性（traceability）** 和 **可解释性（explainability）**。我们现在看它，可以看到 **LLM** 给出的推理令牌，但最终，我们无法控制它。它会做它认为正确的事情。它会进行工具调用。它会告诉你它是对是错。所以，随着系统变得更复杂，一个较小的黑箱会变成一个较大的黑箱。

<details>
<summary>Original English</summary>

**Will**: And a few iterations later we came to a full on **agentic workflow**. We ended up with complex tools to read across all of our platform and these tools are shared across all of our agents, it's not just for **policy agent**, we have a company internal **toolbox** that all of our agents are easily can, you know, reach into. And we gave it the capability to write as well. So it's now writing decisions. It's writing reasoning. It's writing autoproving expenses on users' behalf. And it goes in a loop. So, you know, now it's more of a **black box**. And that's kind of the trade-off you get. As you go from simple to complex systems, your capability goes up, your autonomy goes up, your agents are able to do more, your AI can do more, your AI seems smarter. But in exchange, you're losing **traceability** and **explainability**. We look at it now, we can kind of look at the reasoning tokens that the **LLM** gives us, but in the end, we have no control over it. It's going to do what it thinks it's right. It's going to make the tool calls. It's going to tell you it's right or wrong. So a smaller **black box** becomes a bigger **black box** as the system becomes more complex.

</details>

**Will**: 所以，在做这类事情时，有一点非常重要，那就是从一开始就需要非常好的 **可审计性（auditability）**。即使你知道它是如何工作的，也要假设你只知道它的输入和输出，并确保它是正确的。所以，如果它是一个黑箱系统，你只看到输入和输出，你能验证它做了正确的事情吗？即使黑箱发生变化，你也应该能够推断输出是否正确。

<details>
<summary>Original English</summary>

**Will**: So one thing that is really important when doing something like this is from the beginning you need really good **auditability**. Assume even if you know how it works, assume that your inputs and outputs are all you know and make sure that it's correct. So if it was a **blackbox** system and you only saw the input output, can you verify that it did the right thing? And even if that **blackbox** changes, you should be able to reason about whether the output is correct.

</details>

**Will**: 像我们在 **Ramp** 和其他公司开发的许多产品一样，我们曾认为用户是正确的。也就是说，如果用户说批准，代理就应该批准；如果用户说拒绝，代理就应该拒绝。但事实证明，用户实际上是错误的。他们错了。他们有时不了解费用政策。他们信任自己的员工。他们懒惰。今天是周日。谁知道呢？所以事实证明，我们不能总是按照用户的做法来，因为有时财务团队会回来找你，说：“嘿，这是错的。这不应该用公司卡支付。”因此，我们必须定义自己的正确性。为了做到这一点，我们每周都会与负责该产品的跨职能团队进行 **标注会议（labeling session）**。这带来了两个非常好的结果。一是我们有了一个 **真实数据（ground truth data）** 集，我们可以始终以此进行测试，并且我们知道这是正确的。二是每个人都达成了共识。如果我们的代理出了错，每个人都知道它错了。或者，如果我们的代理缺少上下文，每个人都知道它缺少该上下文。因此，沟通减少了，每个人都在同一页面上，他们可以专注于真正优先的事情，并就此达成一致。

<details>
<summary>Original English</summary>

**Will**: As with many products that we built at **RAMP** and across, you know, other companies, we thought that the users would be correct. You know, if the user says approve, the agent should approve. If the user says reject, the agent should reject. But turns out the users are actually incorrect. They're wrong. They are sometimes, you know, they don't know the expense policy. You know, they trust their employees. They're lazy. It's a Sunday. Who knows? So turns out we can't always do what the users are doing because sometimes that's where finance teams come back to you and are like, "Hey, this is wrong. This shouldn't be on the company card." So, we had to define our own definition of correctness. And to do that we had a weekly **labeling session** with across functions that are working on this product. And that had two really good outcomes. One was that we had a **ground truth data set** that we could always test against and we knew that this was correct. And two was that everyone was on the same page. If our agent got something wrong, everyone knew that it got it wrong. Or, you know, our agent is missing context, everyone knew that it's missing that context. So there was less communication. Everyone's on the same page and they could focus on what's really priority and kind of have alignment on that.

</details>

**Will**: 最初，每周把所有这些人召集到一个房间里，给他们布置作业，让他们标注100个数据点，这很昂贵。你知道，每个人都有自己的事情要做，有时他们没有完成作业就回来了，这几乎变得很乏味，尽管它非常重要。所以我们想让它尽可能简单。我们这样做的方法是寻找第三方供应商，他们可以为我们提供标注数据和收集数据的工具，但事实证明，有些工具过于特定于某个用例，有些工具又过于通用，我们可能会花几周时间尝试不同的工具，但我们决定自己构建。所以，我们使用 **Streamlit** 进行了 **快速编码（clock code）**。我们基本上是一次性完成了所有这些。最棒的是，它的维护成本低，风险低。它位于代码库的一部分，如果它坏了，我们可以立即修复。部署在几秒钟内就能完成。而且非工程师也可以去个性化它。他们可以 **vibe-code** 它。他们可以 **clock code**。这还是在 **Opus 4** 的时候。所以现在有了 **Opus 4.6**，我预计它会更好。有了这样的东西，有时做这种一次性的事情肯定会更容易、更便宜。

<details>
<summary>Original English</summary>

**Will**: Initially getting all those people together in a room every week giving them homework to label a 100 data points it's expensive, you know, everyone has things to do and it's sometimes they don't come back with their homework done it's just kind of like almost becomes tedious even though it's so important so we wanted to make it as simple as possible and the way we did that was that we looked for third party vendors that could provide us the tools to label data and collect the data but turns out some tools are too specific to a use case, some tools are too general and we could have spent weeks trying out different tools, but we decided let's just build our own. So we used **clock code** using **Streamlit**. We basically oneshotted all of this. And the greatest part of it all is that it's low maintenance, low risk. It's in a part of the codebase that if it breaks, we can fix it right away. Deploys happen in like instant seconds. And non-engineers can go and personalize it. They can **vibe-code** it. They can **clock code**. And this was in **Opus 4**. So now with **Opus 4.6**, I expect it's even better. And with something like that, it's definitely easier and cheaper sometimes to do something one-off like this.

</details>

**Will**: 有了这个 **真实数据（ground truth data）** 集，我们能够进行快速迭代。我们能够发现，嘿，我们需要员工级别信息，那就添加它。这如何运作？针对这个数据集运行它。它真的能捕捉到吗？现在是接受还是批准？我们能够进行非常快速的迭代，这实际上是开发过程中的一个关键点。我们很早就确信这确实可行，并且能够获得很多支持，吸引了很多客户作为设计合作伙伴进行试用。

<details>
<summary>Original English</summary>

**Will**: And with that, with the **ground truth data set**, we were able to make quick iterations. We were able to find out, hey, we need employee levels, add that. How does that work? Run it against this data set. Does it actually catch it? And now say accept or approve. And we were able to make really quick iterations and that was kind of the key, that was actually kind of a key point in developing this. We had really early confidence that this could actually work and we were able to actually get a lot of buy in, get a lot of customers on boarded and kind of try it out as a design partner.

</details>

**Will**: 在与数据集进行迭代的过程中，你会有 **评估（evals）**。我觉得 **评估** 正在被大家所熟知，我想在座的每个人现在都知道 **评估** 及其含义，但尽早进行 **评估** 非常重要。我不会说不要让完美主义阻碍你。你不需要一个包含一千个数据点的完整数据集来测试每次迭代。我们从五个数据点开始，我们知道这五个数据点不会失败。我们不断添加，并确保它易于运行。任何人都可以运行该命令，然后确保结果非常容易理解。他们能够查看并立即获得输出，并理解模型正在做什么，什么是好的，什么是坏的。如果你将其作为 **持续集成（CI）** 的一部分运行，现在每个人都可以安全地合并代码。因为每当你认为你为 **大型语言模型（LLM）** 或代理做对了什么，提供了更多上下文，提供了工具，很可能它会产生一些你没有预料到的不良后果。例如 **上下文腐烂（context rot）**。无论是工具指令错误，还是文档字符串有点令人困惑和冲突。所以它可能会产生后果。你只是想确保你能捕捉到这些。

<details>
<summary>Original English</summary>

**Will**: And as part of like doing that iteration with the data set you had **evals** and I feel like **evals** are being, you know, obviously everyone I think in this room now knows about **evals** and what they mean but it's pretty important to have them early on. I wouldn't say that, you know, don't let perfectionism, you know, get in the way. You don't need a full data set of a thousand data points. So you're testing against every iteration. We started with five, you know, and we knew that those five we were not going to fail. We kept adding and adding and adding and, you know, make sure it's easy to run. Anyone could go and just run that command and then make sure that the results are really easy to understand. They are able to look at it, get instant, you know, output like and understand like, hey, this is what the model's doing. This is like good, this is bad and like if you run it as part of your **CI** everyone now can safely merge in code. Because whenever, whenever you think you're doing something right for the **LLMs** or agent, giving more context, giving tools, more likely than not, it's probably gonna have some kind of bad, you know, consequence that you didn't see happening. **Context rot**. Whether it be the tool instructions are wrong or maybe the dock string was like a little confusing and conflicting. So it might have consequences. You just want to, you just want to make sure you're catching against those.

</details>

**Will**: 我还会简要提及 **在线评估（online evals）** 也非常棒。离线评估是你有一个数据集，它是历史性的，你正在测试它。但如果你能进行 **在线评估**，它可能会有点令人困惑，更难衡量，但如果你的用户与系统交互时能衡量任何东西，我肯定会将其设置为一个领先指标。对我们来说，其中一部分就是决策的“不确定”率，这意味着代理没有足够的信息，所以我们可以在线衡量，这是一个非常简单的评估，但也为我们系统运行时提供了一个很好的健康检查。

<details>
<summary>Original English</summary>

**Will**: And then I'll touch on it briefly, but **online evals** are also great. So these are offline. You have a data set. It's historical. You're testing it. But if you can **online evals** can be a little more confusing and harder to kind of measure but if you can measure anything that as your users are interacting with the system definitely as a leading metric I'll set them up and for us part of that was hey how many our rates of like decisions we had an unsure decision which is which just meant that the agent didn't have enough information so we could measure that online know it's much simple eval but that also gave us a pretty good health check as our system was running.

</details>

**Will**: 酷，关于 **评估（evals）** 的另一个很棒的地方是，通过 **评估**，你可以自信地进行模型更改。每当有新模型发布时，比如 **Opus 4.6** 或 **GPT-5.3**，你都希望能够利用这些新模型，因为有时这可能意味着你的系统在解决问题时从对到错的差异。但它也可能意味着相反的情况。它可能在没有任何问题变化或改变系统工作方式的情况下，实际上表现不佳。所以，真正建立好 **评估** 并能够进行基准测试，确实有助于自信地进行模型更改。

<details>
<summary>Original English</summary>

**Will**: Cool and another great part about **eval** is with **evals** you can make confident model changes. Whenever a new model comes out **Opus 4.6**, **GPT-5.3**, you want to make sure that you can leverage those new models because sometimes that could mean the difference between, you know, your system getting one part of the problem right to wrong. But it could also mean the opposite. It could have, it could actually be not good without any problem changes or changing how your system works. So having **evals** really set up and being able to benchmark really helps make confident model changes.

</details>

**Will**: 好的。现在，**政策代理** 我们已经开发了一段时间，它已在 **Ramp** 平台上向所有人开放。我们在此过程中学到的一些事情是，作为工程师，**快速编码（clock code）** 非常令人兴奋。我们拥有完全的控制权。我们可以修改我们的云MD。我们可以确保它不留下评论，希望它不会留下评论。但事实证明，不仅仅是我们。财务人员也真的很喜欢修改他们的云MD，也就是他们的费用政策。所以，如果决策出了问题，我们就会告诉他们：“嘿，去更新你的政策文档。”对他们来说，这在开始时是一个有点可怕的概念，就像“这是一份文档，你不能乱动它”，如果你想动它，你必须经过很多繁琐的程序。但事实证明，如果你让他们对反馈循环感到非常兴奋，说：“嘿，改一下，你马上就能看到效果”，他们就会非常乐意这样做。然后信任会随着时间建立起来。

<details>
<summary>Original English</summary>

**Will**: Cool. So now that **policy agent** we've been developing this for a while it's available for everyone on the **RAM** platform. Some of the things that we learned along the way is that **clock code** as engineers is very exciting. We have full control. We get to modify our cloud MD. We get to make sure, you know, tell it to not leave comments. It won't leave comments hopefully. Turns out it's not just us. Finance people also really like to have, you know, modify their cloud MD which is their expense policy. So if something went wrong with the decision then we just like tell them, hey, go update your policy doc which to them it's a little scary concept to begin like this is a document like, you know, you don't mess with that. You have to go through a lot of hoops if you want to mess with that. But it turns out if you get them really excited about the feedback loop, hey, change that, you'll see it right away, turns out they'll be like really excited to do this. And then trust builds over time.

</details>

**Will**: 我们早期的一些客户是 **财富500强** 公司，我们实际上是从那些真正大型的企业客户开始的，因为我们认为他们会获得最大的价值。他们有最多的费用进来。他们花费最多的时间来审查咖啡费用。所以，你知道，向他们推广，让他们建立信任。我们没有做任何自主行动。我们只是说：“嘿，我们会给你一个建议。”我们就是这样说的，建议。最终他们来找我们说：“好吧，你知道吗？我想从建议转向自动批准。比如20美元以下的任何东西，你们大部分都是对的。我不在乎这个。让我直接自动批准它。”所以我们给了他们一个 **自主性滑块（autonomy slider）**，给了他们一个开启它的方式，然后他们就可以自己操作了。

<details>
<summary>Original English</summary>

**Will**: So some of the earlier customers that we had were some of the **Fortune 500s**. We actually started with the really big, you know, enterprise customers that we had because we that they would have the most value. They have the most expenses coming in. They have the most time spent on reviewing coffee expenses. So, you know, roll out to them, let them have the trust. Don't, we didn't do any autonomous action. We're just like, hey, we're going to give you a suggestion. That's, that's how, that's kind of how we phrased it, suggestions. And eventually they came to us and we're like, okay, you know what? I want to go from suggestions to auto approvals. Like anything under $20, you guys are mostly right. I don't care about this. Let me just go auto approve it. So we gave them the **autonomy slider**, we gave them a way to like turn it on and then they actually could do it themselves.

</details>

**Will**: 最后但同样重要的是，类似于 **大型语言模型（LLMs）**，用户在产品反馈循环中蓬勃发展。所以，当你构建一个AI产品，并且有一个完整的方式，比如 **LLM** 可以测试它的代码是否正确并能够迭代时，用户也是一样的。我们为他们提供了产品内改进费用政策文档、改进代理及其运作方式的方法，他们非常乐意自己接管，并改进和个性化它。接下来，我将把时间交给 **Ian**，他将谈谈 **Ramp** 的基础设施和文化，这些促使我们构建了 **政策代理**。

<details>
<summary>Original English</summary>

**Will**: And then last but not least, similar to **LLMs**, users thrive, you know, in product feedback loops. So, you know, when you're building an AI product and you have a full way of like **LLMs** can test if it's code was right and it's able to iterate, users are the same way. Gave them in product ways to improve the expense policy doc, improve the agent and how it operates and they're more than excited to kind of take it over themselves and kind of improve it and personalize it for them. So from here I'll pass it on to **Ian** who's going to kind of talk about the infrastructure and the culture that we have at **RAMP** that kind of it led us to building the **policy agent**.

</details>

### AI基础设施与工程文化

**Ian**: 大家好。你们已经听了一些关于我们如何在他们的财务基础设施之上运作，并真正为我们的客户争取杠杆作用，从而为所有不同的财务团队带来杠杆作用。但我认为我们花很多时间思考的另一件大事是，我们如何为 **Ramp** 本身、工程师、我们的 **跨职能组织（XFN orgs）** 以及我们每天合作的所有人争取杠杆作用。这部分内容被有意命名为“AI基础设施与文化”，因为我们认为这既是一个极具挑战性的基础设施问题，也是一个极具挑战性的文化问题，改变你的工作方式也是故事的重要组成部分。

<details>
<summary>Original English</summary>

**Ian**: Hey everybody. So you've heard a little bit about like how we're kind of getting leverage to all of the different finance teams as we operate on top of their financial infrastructure and really try to get leverage for our customers. But I think a big thing that we also spend a lot of time thinking about is how can we get leverage for **Ramp** itself, the engineers, our **XFN orgs**, all the people that we work with every single day. And this slide is this section is pretty intentionally named AI infrastructure and culture because we think that this is both like a really challenging infrastructure problem but it's also really challenging culture problem and changing how you work as well is a big part of the story.

</details>

**Ian**: 那么，从基础设施方面开始，**Ramp** 大部分应用AI的核心是我们的应用AI服务界面。从一万英尺的高度看，这有点像 **LLM代理（LLM proxy）** 或轻量级 **大型语言模型（LLM）**。但我们投入了三个主要的扩展，使其在许多用例中更加强大。首先是 **结构化输出（structured output）** 和跨不同模型提供商的 **一致API和SDK**。这可能很难做到，特别是考虑到API变化的速度，但我们不希望下游产品团队为此操心。所以，如果你想从 **GPT-5.3** 切换到 **Opus**，或者想尝试 **Gemini 3 Pro**，你应该能够通过更改配置来实现，并能非常快速地迭代语义相似性，并尝试进行大量的代码沙盒和结构化输出调用。

<details>
<summary>Original English</summary>

**Ian**: And so to kind of start on the infrastructure side the core of how most of applied AI happens at **RAMP** is our applied AI surface service. And at like a 10,000 foot view, this looks something kind of like an **LLM proxy** or something like light **LLM**. But there's really three kind of main extensions that we've invested in to make this a lot more powerful for a lot of our use cases. The first is like **structured output** and **consistent API and SDKs** across different model providers. This can be pretty tricky to do, especially with how quickly the APIs are changing, but it's a problem that we don't want downstream product teams to have to think about. So if you have an idea of I want to switch from **GPT-5.3** to **Opus** or I want to try **Gemini 3 Pro**, you should be able to do that with a config change and really quickly be able to iterate on semantic similarity and trying to do a bunch of different, you know, code sandboxing and structured output calls that way.

</details>

**Ian**: 我们花大量时间思考的另一件事是 **批处理（batch processing）** 和 **工作流处理（workflow handling）**。这对于 **评估（eval）** 非常有用，例如我们进行批量文档或数据分析。我们也不希望团队花费大量时间去考虑如何批处理、如何处理速率限制，以及我们是否要用 **Anthropic** 这样的模型进行离线或在线作业。我们只想为下游消费者处理这些，这样他们就可以专注于为下游客户提供价值。最后，也是非常重要的一点，是能够跟踪不同团队和产品的成本。这使我们能够识别 **帕累托曲线（Parado curve）**，例如，哪种模型性能成本效益最佳？这些模型如何随时间演变？哪些团队实际上没有构建对不同产品服务长期可持续的东西？这对于消除内部团队思考这些问题的工作量非常重要。

<details>
<summary>Original English</summary>

**Ian**: The other thing that we've spent a ton of time thinking about is kind of **batch processing** and **workflow handling**. This is really useful for **eval** if you're doing like bulk for us bulk document or data analysis. And that's something that we also don't want teams to have to spend a bunch of time on of how do you want to batch this and handle it with rate limits and do we want to do this on an offline or online job with something like **Anthropic**. We just want to handle that for downstream consumers so they can just focus on providing value for downstream customers. And then the last which is a pretty big deal is the ability to trace different costs across teams and against products as well. And this allows us to kind of identify the **Parado curve** of like what is the best kind of model performance for cost? How are these evolving over time? What teams are actually not, you know, building something that's going to be sustainable long term for different product services and this can be really really important to just remove all this work from internal teams having to think about this.

</details>

**Ian**: 最后一件我认为很有趣的事情是，我们经常开玩笑说，我们的客户实际上正在使用比他们可能知道的更前沿的模型。它使我们能够保持在前沿：当新模型发布时，只需一行配置更改，就会影响每个下游SDK。因此，团队无需学习SDK或进入12个或几十个不同的调用点，他们只需在一个地方为特定团队更改它，就能获得使用我们已经验证并集成到系统其余部分中的最新、最强大模型的好处。

<details>
<summary>Original English</summary>

**Ian**: And the last thing that's kind of I think funny to think about we often joke about that, you know, our customers are actually using the front more of a frontier model than they may even know even is out yet is it allows us to stay at the frontier when a new model comes out it's a oneline config change that impacts every single SDK downstream and so rather than teams having to learn the SDK or go into 12 or dozens of different call sites, they can just change it in one place for their specific team and they now get the benefit of being on the latest and greatest models that we've kind of vetted and built into the rest of the system.

</details>

**Ian**: 你们之前也听说了，我们的产品处理大量非常敏感的数据和工作流。我认为，我经常从这个领域的工程师那里听到关于 **幻觉（hallucination）** 和安全性的概念，以及你如何才能真正生产出许多这样的东西，从而为下游财务团队带来好处。我们坚信，这一切都归结于团队日常构建和集成的 **工具目录（catalog of tools）**。

<details>
<summary>Original English</summary>

**Ian**: Our product as you've kind of heard earlier works on a lot of like very sensitive data and very sensitive workflows. And I think often times, you know, something that I hear from engineers in the space is this kind of concept of **hallucination** and safety and how are you actually going to be able to produce a lot of these things to have benefits to downstream finance teams. And we're pretty big believers that it all comes down to the **catalog of tools** that teams are building and integrating with in a daily basis.

</details>

**Ian**: 所以，你在这里看到的是我们内部的 **工具目录**。例如，获取政策片段、PDM费率或最近的交易。这些工具是与产品团队一起构建的，以真正理解数据和用例中的许多细微差别。这真的很酷，因为你不仅可以看到我们产品中的空白，例如“哦，我们实际上没有针对这个特定用例的工具”。这些工具既可以在内部仓库中使用，也可以在我们的核心产品中使用。所以，如果你有一个很棒的报销代理的想法，这里有不同的集成工具、不同的API和系统的方式。现在你可以在一个完全新的产品中，在 **vibe-coded** 的界面上进行原型设计，而无需担心从头学习所有这些东西或自己构建工具。我们今天已经有数百个这样的工具，正如 **Nick** 之前提到的，我们认为随着时间的推移，这可能会达到数千个。

<details>
<summary>Original English</summary>

**Ian**: And so what you're seeing here is our internal **tool catalog**. So an example would be like get a policy snippet or PDM rate or recent transactions. And these are built alongside of product teams to really understand a lot of the nuances in the data and the use case. And what's really cool about this is not only can you see where there's gaps in our offering that, oh, we actually don't have a tool for this specific use case. These can be used both in internal repos and our core product. And so if you have an idea of I want to do a cool reimbursement agent idea here are the different ways to integrate the tools, the different APIs and systems that they integrate with. And now you can prototype that on a totally new product in **vibe coded** surface area without having to worry about like learning all of these things from scratch or building the tools on your own. We're up to like many hundreds of these tools today and we as **Nick** mentioned earlier thinks that this could be like multiple thousands over time.

</details>

### Ramp Inspect：内部编码代理

**Ian**: 关于上下文的话题，我们思考的另一件大事是为客户提供上下文，即我们如何真正整合财务技术栈，让他们提高生产力。但我们在内部工程团队中发现了一个非常类似的问题。我认为，一个不总是那么明显的问题是，即使你使用像 **Cloud Code** 或 **CodeX** 这样的工具，你在公司日常工作中完成任务所做的一切都存在碎片化，没有整合起来。**DataDog** 中有日志。有一个正在运行的生产数据库。有不同的警报系统。有 **Incident.IO**。有一条你需要拉取的 **Slack** 消息。有一个 **Notion** 文档。然后，这些特定的产品团队还有很多关于他们如何实际完成工作的知识。

<details>
<summary>Original English</summary>

**Ian**: On the topic of context, another big thing we think about is context for our customers of how do we actually integrate the financial stack and allow them to be a lot more productive. But we noticed like a very similar problem internally on our engineering team. And I think something that's like not as always obvious is that, you know, even if you're using something like **Cloud Code** or **CodeX** there's all this fragmentation of actually what you do on a daily basis to get work done in your company that that's not integrated too. There's logs in **DataDog**. There's a production, you know, database that has a bunch of things going on. There's different alerting systems. There's **Incident.IO**. There's a **Slack** message you have to pull in. There's a **Notion** doc. And then there's a lot of like knowledge that those actual specific product teams have of how they actually need to get work done as well.

</details>

**Ian**: 因此，去年年底，我们决定着手解决这个问题：我们如何真正整合所有这些上下文，并构建我们自己的内部后台编码代理，我们称之为 **Ramp Inspect**。你可能在 **LinkedIn** 或 **X** 上看到过它。我们实际上已经开源了我们构建它的蓝图，最后我可以给大家展示一个链接，告诉你们在哪里可以找到它。将它集成到一个后台代理中，使其能够在人们开会时、出现bug修复等情况下自主运行，这一进展相当惊人。目前，本月 **Ramp Inspect** 负责我们合并到生产环境的超过50%的 **拉取请求（PRs）**。我们对统计数据和数字之类的东西非常着迷。所以我们有一个仪表板，旨在创造一种有趣的、微妙的良性竞争，同时也激励人们也可以使用它。

<details>
<summary>Original English</summary>

**Ian**: And so at the end of last year, we decided to start out and try to solve this problem of how can we actually integrate all this context and build our own internal background coding agent which we've called **Ramp Inspect**. You may have seen this on **LinkedIn** or **X**. We actually have open sourced the blueprint of how we built this and at the end I can definitely show you guys a link of where to find that. And the progress has been pretty phenomenal of actually integrating this into a background agent that can run autonomously as people are in meetings if as bug fixes come up and things like that. And currently this month **Ramp Inspect** is responsible for over 50% of **PRs** that we merge to production. I have some interesting we're like really big nerds with stats and numbers and things like that. So we have this dashboard to kind of create this like interesting one like subtle healthy competition but also inspire people that they can actually use this as well.

</details>

**Ian**: 所以你可以看到工程团队在会话数量上遥遥领先，但产品、设计、风险、法务、企业财务甚至市场和客户体验团队也在使用 **Ramp Inspect**。他们正在做一些简单文案修改、逻辑修复，他们正在尝试响应事件或bug。随着时间的推移，看到这一切的发展真的很酷。

<details>
<summary>Original English</summary>

**Ian**: And so you can see engineering has a huge lead of the amount of sessions but you also have product you also have design there's risk legal corporate finance and even marketing and CX teams using **Ramp Inspect** and they're doing things like simple copy changes they're doing logic fixes they're trying to respond to incidents or bugs and what's been really cool to see as this has evolved over time.

</details>

**Ian**: 我们实际上是如何设计这些东西的，并遵循一些核心原则使其变得非常强大。你在这里看到的是一个 **Ramp Inspect** 会话。我认为这是一个我们试图修复的查询示例。它在后台快速启动一个 **模态代码沙盒（modal code sandbox）**。这使我们能够在隔离环境中恢复、启动和关闭这些容器，这个环境与你在开发 **Ramp** 时所拥有的环境相同。它有一系列任务来保持正常运行，并创建一个 **GitHub** 分支，与所有上下文文档、我们的 **DataDog**、我们的只读副本集成，这样它就可以实际编写查询以及产品团队整理的不同上下文文档。

<details>
<summary>Original English</summary>

**Ian**: Is how we've actually designed a couple of these things with some core principles to really powerful. So what you're seeing here is a **Ramp Inspect** session. I think this is an example of like a query that we were trying to fix. This spins up in the background really fast **modal code sandbox**. This allows us to like resume spin up and spin down these containers in an isolated environment which has the same environment that you would have if you're developing a **Ramp**. There's a series of tasks to keep it on track and it creates a **GitHub** branch and integrates with all of the context documents, our **DataDog**, our read replica so it can actually write queries and different context documents that product teams have put together.

</details>

**Ian**: 我认为我们设计它的一个非常微妙之处在于，我们将其设计为 **多人优先（multiplayer first）**。这意味着当你与设计师或产品经理团队的某人集成或尝试结对时，你可以帮助他们提升自己的 **提示技能（prompting skills）**。他们可以给我们反馈，比如“嘿，点击这个链接。这实际上以我没想到的方式失败了。”所以这可以成为 **跨职能协作（cross-functional collaboration）** 的一个非常好的来源。这是我们做出的一个非常微妙的设计选择，最终对公司产生了巨大的影响。然后，这些可以从 **看板用户界面（Kanban UI）**、我们的API以及 **Slack** 线程中启动。当它实际启动时，我们可以获取 **Slack** 线程的完整上下文。所以你不需要用之前发生的大量对话重新提示它。

<details>
<summary>Original English</summary>

**Ian**: And what's really, I think subtle about how we've designed this is we've designed it to be **multiplayer first**. And that means that as you integrate or you try to pair with like a designer or somebody on the PM team, they you can actually help them like level up their own **prompting skills**. They can give us feedback of, hey, click on this link. This actually failed in a way that I wasn't expecting. And so that can be a really great source of like **cross-functional collaboration**. That was a very subtle design choice that we made that ended up being a really big impact for the company. And then these can be kicked off either via the **Kanban UI**, we have an API, and then also a **Slack** thread. And we can take the full context of the **Slack** thread when it is actually kicked off. So you don't have to reprompt it with a bunch of conversation that happened earlier.

</details>

**Ian**: 你在这里看到的是，我们还有一个完整的 **VS Code** 环境。我们还在 **模态沙盒（modal sandbox）** 中运行 **VNC**。这使我们能够拥有 **Chrome开发者工具（Chrome dev tools）** 和 **MCP**。所以它实际上可以进行全栈工作，这非常酷。它还可以访问我们拥有的超过15万个测试。所以它也知道是否有东西坏了，可以在 **GitHub** 内部响应 **CI**，并在实际通知你 **拉取请求（PR）** 完成之前修补修复程序。

<details>
<summary>Original English</summary>

**Ian**: What you see here is we also have a full **VS Code** environment. We run **VNC** inside of a **modal sandbox** as well. So this allows us to have **Chrome dev tools** and **MCP**. So it can actually do full stack work which is pretty cool. And it has access to the 150 plus thousand tests that we have. So it also knows if things are broken, can respond to the **CI** inside of **GitHub** and actually patch fixes before it actually pings you that the **PR** is done.

</details>

**Ian**: 这个链接是 **builders.ramp.com**。我认为这是我们最早的博客文章之一，或者说是我们最近的博客文章之一，我们还开源了构建和整合这个系统的完整蓝图。我认为还有一个名为 **open inspect** 的 **GitHub** 仓库，它也是这个系统的开源实现。

<details>
<summary>Original English</summary>

**Ian**: The link for this is **builders.ramp.com**. I think it's like one of the first blog posts that we have or the most recent blog posts that we have and we open source like the whole blueprint of how to build this and put this together as well. I think there's also a **GitHub** repo called **open inspect** which is an open source implementation of this as well.

</details>

**Ian**: 所以，看到 **Ramp Inspect** 所产生的影响非常有趣，我们每周合并的 **拉取请求（PRs）** 中有超过50%是通过这个系统完成的。因此，所有这些没有花在思考那些低级别的救火任务，或者那些可以在公司内部普及的低级别小修复或调整上的时间，我们正在真正重新思考我们的工程团队如何运作，如何看待他们的工作，以及他们在这个新型 **AI原生未来** 中如何真正发挥影响力。

<details>
<summary>Original English</summary>

**Ian**: So it's been pretty interesting to see the impact that **Ramp Inspect** has had where over 50% of **PRs** that we merge on a weekly basis goes through the system. And so with all this time not spent on thinking about these really low-level firefighting tasks or really low-level small fixes or tweaks that can be kind of democratized across the company, we're really rethinking like how our engineering teams operate and think about their job and how they can actually be really impactful and this new kind of **AI native future**.

</details>

### AI时代工程师的未来

**Ian**: 那么，作为一个思想实验，我们假设有两个不同的团队。我相信在座的每个人都曾与一些出色的团队合作过，也许也有一些正在摸索的团队。你会注意到有几种不同的特质可能会引起共鸣。左边是 **A团队**。假设他们非常关心影响力。他们处理模糊的问题。他们理解产品、业务和数据。他们采用新工具。他们能找到创造性的解决方案，并且痴迷于用户体验。

<details>
<summary>Original English</summary>

**Ian**: And so as a thought experiment, let's pretend we have two different teams. I'm sure everyone in this room has worked with like their handful of extraordinary teams, maybe teams that are finding their footing. And you'll notice that there's like a couple of different qualities that may sound that may resonate. So we have **team A** on the left here. And let's say that they really care about impact. They handle ambiguous problems. They understand the product, business, and data. They adopt new tools. They can find creative solutions and they obsess over like the user experience.

</details>

**Ian**: 然后是 **B团队**，可能也会引起一些人的共鸣。他们会争论库的选择。当事情开始变得混乱时，他们会增加流程。他们不断抱怨人手不足。他们纠结于细节，而不是真正关注用户体验，比如“我们应该在这里使用函数式编程范式吗？”或者“我们想使用哪个版本的 **TypeScript** 库？”然后他们在理解问题之前就开始构建，他们只是说：“嘿，兄弟，别担心，我们直接 **vibe-code** 就行了。”或者他们专注于表面化的代码质量或吹毛求疵，这些可能实际上是非常主观的事实。我在这两种团队都工作过，我认为我今天要提出的论点是，我认为会根据你站在哪一边而出现分歧。

<details>
<summary>Original English</summary>

**Ian**: And then **team B** may also resonate with some people. You know, they debate libraries. They add process when things start to feel chaotic. They constantly complain about headcount. They bike shed the details instead of actually focusing on the user experience like, hey, should we use, you know, functional programming paradigm here or what version of, you know, different **TypeScript** libraries do we want to use and then they build before understanding the problem, right? They just say, hey, we're going to just **vibe-code** this bro, don't worry or they focus on, you know, performative code quality or nitpicks that may not actually that may be very much like a subjective kind of matter of fact as well. I've worked on both of these teams and I think the argument that I'm going to make today is that there's going to be divergence I think depending on what side of the aisle you land there.

</details>

**Ian**: 这是一项来自 **哈佛大学** 的研究，我认为是在去年年底发布的，它非常关注初级和高级工程师，探讨自AI工具加速发展以来，工程领域的招聘趋势实际发生了什么。我认为这项研究忽略了一点，我不认为这仅仅是经验年限的问题。我实际上认为，这很大程度上是 **A团队** 和 **B团队** 中我提到的所有不同特质，它们真正表明，长期以来，编码从来都不是很多工作中真正最困难的部分。所有这些其他的工程原则变得非常重要，远超纯粹的编码速度。

<details>
<summary>Original English</summary>

**Ian**: This is a study from **Harvard** that was out, I think, the end of last year and it was very much geared towards juniors and in seniors in terms of what's actually happening with hiring trends in engineering since AI tools have accelerated. And I think what this glosses over is I don't think it's just a years of experience problem. I actually think it's very much all of the different qualities that I said in **team A** versus **team B** that really make it apparent that like coding was never really the hardest part of a lot of jobs for a long time. There's all these other engineering principles that become really important than just raw coding speed.

</details>

**Ian**: 所以当你考虑像一名资深工程师或更高级别的工程师时，你实际上更多地是为他们带来的判断力、上下文、预见问题的能力、他们所学到的所有知识，以及实际的“伤疤组织”来支付报酬。所以，如果你让 **Opus 4.6** 做某事，他们将有知识真正知道这是否行不通，或者这实际上是一个坏主意。我认为媒体中很多关于编码代理的叙述都搞错了的一点是，他们没有真正认识到，你仍然可以更快地构建错误的东西，而且你可以制造更大的混乱。我认为拥有 **A团队** 的许多这些技能，并真正专注于这背后的上下文和原因，在AI领域只会变得更加重要。

<details>
<summary>Original English</summary>

**Ian**: So when you think about like a staff or a staff plus engineer, you're really compensating those people more for a lot of the judgment that they bring to the table, the context, the ability to see around corners, all the learning that they have, the actual like scar tissue. And so if you know you ask **Opus 4.6** to do something, they'll have the knowledge to actually know if that is not going to work or that's actually a bad idea. And I think one thing that a lot of the narratives that we see in the media gets get wrong about coding agents is they don't really identify the fact that you could still build the wrong thing just a lot faster and you can build like bigger messes. And I think that having a lot of these skills of a **team A** and really focusing on like what is the context and reason behind this will only become more important in AI.

</details>

**Ian**: 那么，这实际上是什么样子呢？我们触及了一些方面。弄清楚要构建什么以及充分理解用户。向持怀疑态度的利益相关者推销一个想法。当我们决定构建一个后台编码代理时，这仍然不是一个显而易见我们应该投入时间的事情。在信息不完整的情况下做出良好的设计决策，并在项目漫长而艰难的中期保持势头。我认为最后一点，我相信在座的每个人都痛苦地意识到，关于 **SaaS** 和股市等话题的讨论。我认为这是一个被他们忽略的重要因素，那就是，是的，**vibe-code** 某些东西很容易，但真正经历那个中间过程，才是为什么你需要真正优秀的工程师来实际部署一个具有 **产品市场契合度（product market fit）** 且人们真正兴奋的产品。我认为没有足够多的人认识到这一点。

<details>
<summary>Original English</summary>

**Ian**: And so what does that actually look like? We hit on some of these things. Figuring out what to build and understanding users well enough. Selling an idea to skeptical stakeholders. This is still something when we decided to build a background coding agent. This was not something that was obvious that we should be spending time on this. Having good design decisions with incomplete information and maintaining momentum through the long middle of this project, which can be really gnarly. And I think this last bit, you know, everyone in this room, I'm sure, is painfully aware of, you know, the conversation around **SaaS** and the stock market and things like that. And I think this is like a big element that they gloss over, which is that, yes, it's easy to **vibe-code** something, but actually going through that middle process is like why you need really good engineers to actually get something deployed that has **product market fit** that people are really excited about. And I think not enough people recognize that.

</details>

**Ian**: 那么，这给我们留下了什么？就我个人而言，我认为很多关于AI的叙述都带有一些悲观主义和恐惧，但我也认为这是一个非常激动人心的建设时期。与工厂工作或农业不同，软件永远不会完成。我们内部有一个非常像 **meme** 的说法，就是“工作还没完”。你们可能在市场营销中也看到过。我认为软件是永无止境的。

<details>
<summary>Original English</summary>

**Ian**: And so where does that leave us? Personally, I think there's a lot of kind of dumerism and scariness around a lot of the AI narratives, but I think it's also a really exciting time to be building. Unlike maybe factory work or farming, software is never done. We have this really kind of like **meme** internally where we say, you know, jobs not finished. You've probably seen in the marketing as well. And I think software is perpetually not finished.

</details>

**Ian**: 因此，有了所有这些额外的能力，人们将更少地关注这种低级别的工作，而更多地关注高杠杆的工程任务，我认为将真正发生四件事。我认为公司将追逐他们以前无力追求的机会。如果这项技术不存在，我不知道我们是否会追求这些 **代理工作流（agentic workflows）**，并真正思考财务技术栈中更大规模的问题。人们将进入邻近市场。他们将尝试为客户整合更多价值。这不会是因为每个人生产力提高了两倍，你就需要减少一半的人。你将重建那些成本过高而无法触及的系统。我认为为一家从事财务运营软件的公司构建一个内部后台编码代理，这在当时可能听起来像是一个相当疯狂的想法，但现在看来非常有意义，并且提高了“足够好”的标准。我认为，能够为用户构建更多令人惊叹的体验，提供更多价值，将是未来十年的主题。我非常高兴能够构建其中一些东西，并看到在座的每个人也将构建什么。谢谢大家。

<details>
<summary>Original English</summary>

**Ian**: And so with all this extra capacity, with people focusing less on this kind of low-level work and more on high leverage engineering tasks, I think four things are going to really happen. I think companies are just going to chase opportunities they couldn't afford to pursue. I don't know if we would be chasing these like **agentic workflows** and really thinking about bigger scale problems in the financial stack if this technology didn't exist. People are going to enter adjacent markets. They're going to try to stitch together more value for customers. It's not going to be like because everyone's 2x more productive, you need two less or half the people. You're going to rebuild systems that are too expensive to touch. I think building an internal background coding agent for a company that does financial operations software felt like probably a pretty crazy idea, but now that makes a ton of sense and raise the bar for what good enough means. I think, you know, being able to kind of build more mind-blowing experiences for users, provide a lot more value is going to be the narrative of the next decade. And I'm super excited to be able to build some of these things and see what everyone in this room is going to build, too. So, thank you.

</details>