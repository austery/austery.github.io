---
author: AI Engineer
date: '2026-11-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JGtkTjn4120
speaker: AI Engineer
tags:
  - agent-architecture
  - enterprise-ai
  - process-automation
  - evaluation-metric
title: 为什么 AI 提升了个人百倍效率却难以改变企业：构建生产级可靠 Agent
summary: Basis 联合创始人 Mitch 探讨了个体 AI 提效无法直接扩展至企业整体的原因，指出开放式 Agent 存在能力鸿沟与流程鸿沟。企业规模化依赖自上而下的确定流程与信任，因此生产级 Agent 必须具备明确的“主见”，并通过行为规范、分叉调试与模拟手段监督执行过程，以实现可靠交付。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mitch
companies_orgs:
  - Basis
products_models: []
media_books: []
status: evergreen
---
### 生产级 Agent 的核心挑战与企业效率困境

[music]

>> 我是 Mitch，Basis 的两位联合创始人之一。我们公司就在纽约市，而我们专注的核心问题是：如何让 Agent 能够足够可靠地在生产规模上完成工作，从而获得全美会计师事务所的信任并在端到端业务中投入使用。

我们的许多研究真正聚焦的正是这一点：怎样才能让这些 Agent 在实体经济中承担实际工作？

<details>
<summary>Original English</summary>
[music]

>> I'm Mitch. I'm one of the two co-founders of Basis. We are based right here in New York City and the thing that we focus on is how can we get agents to do production-scale work reliably enough so that we are trusted and used end-to-end by accounting firms across the country. So, a lot of our research really focuses on this. How can you get these agents to do real work in the real economy?
</details>

我想先从一个问题开始：如果你参加了这次大会，坦白说，如果你正在观看这场演讲，你大概已经大幅提升了自己的生产力。你可能正在使用 Co-work、Codex 或是 Cloud Code 等等。然而，如果你去观察普通公司、普通企业或事务所，他们的生产力并没有提升 10 倍或 100 倍。我知道我个人的生产力可能提升了 100 倍，但如果我是在一家公司内部工作，整体提升绝不可能达到这种数量级。那么，这是为什么呢？

在 Basis，我们的看法之一是：人类其实早已习惯与非确定性系统共事，只不过那些系统通常是人类同事，而不是计算机。

因此，我认为要回答这个问题，不妨回顾一下我们目前组织智能系统（也就是企业）的既有方式。

<details>
<summary>Original English</summary>
So, I want to maybe start with a question, which is if you're in the at this conference, honestly, if you're watching this talk, you've probably increased your own productivity a lot. You're using co-work or uh Codex or cloud code, whatever it is. And yet, if you go and look at the average company, the average enterprise, the average firm, their productivity hasn't gone up 10x, 100x. I know my productivity has gone up maybe 100x. But, if I were working inside of a company, it wouldn't be anywhere near that order of magnitude. And so, why is that?

At Basis, one of the things we have is that humans are already used to working with non-deterministic systems. It's just those systems are normally their co-workers, not their computers.

And so, I actually think to answer this question, it's useful to maybe look at the existing way we organize intelligent systems, which are companies.
</details>

### 组织如何通过流程实现规模化与信任

那么，组织究竟是如何扩展自身的生产力的呢？

组织需要信任各个层级负责执行工作的人员，相信他们执行任务的方式能够在规模化运作中持续产出良好结果。看这里的这张图，我展示的是一家会计师事务所，但老实说，这可以适用于任何传统公司。事务所的负责人对最底层员工的具体日常工作细节实际上毫不知情，但他们不知何故却坚信工作能够被顺利完成。

这是如何做到的？这并不是通过确定性系统实现的。人并不是确定性的，人是具备智能的实体。

相反，这是通过建立起流程来实现的。如果制定这些流程的人认为流程能够泛化出良好的结果，那么他们就能感到安心：哪怕执行流程的人本身是非确定性的，只要遵循流程，通常也能获得良好的成果。

<details>
<summary>Original English</summary>
So, how do organizations scale their own productivity, right?

Organizations need to trust that the people doing the work at every level are doing it in a way that is going to produce good outputs consistently at scale, right? If look at this image here, the uh here I'm showing an accounting firm, but this could honestly be any company, traditional company. The person who is the head of the firm, they have literally no idea about the exact day-to-day of the people at the very bottom. And yet somehow they trust the work is going to be done.

How does that happen? It doesn't happen through deterministic systems, right? People are not deterministic. They're intelligent entities.

And instead there are processes that are put in place, and those processes, if we believe the people who, you know, put them in place, think that those processes will generalize to good outcomes, then they can be comfortable that even though the people executing the processes are not deterministic, you will generally get to good outcomes if you follow the process.
</details>

顺便提一下，哪怕是在最微小的步骤中也是如此。在刚才的示例中，我展示的可能是会计师事务所为客户处理月度账目核算的工作流程；但即便在该流程内部，比如你想知道该如何核对现金，你就需要获取银行数据，而连这本身都存在既定流程。这个流程可能非常基础，可能仅仅是使用经过审批的软件来提取数据，但依然会有一套既定流程存在。

你不可能指望事务所允许任何人随便 Google 搜索提取 PDF，然后随意使用他们想用的工具去提取，因为那样一来流程就不复存在了。

<details>
<summary>Original English</summary>
This is true, by the way, even in the smallest steps. So, in this example, earlier I was showing the process of maybe doing the monthly accounting work for a client at an accounting firm, but even within that process, say you wanted to see, how do I reconcile the cash? Well, I need to get the bank data, and even that has a process. The process could be really basic. It could just be use the approved software to extract the data, but there's still some process that is put in place.

You wouldn't expect the firm to just let anyone Google, you know, extract PDF and then just use whatever they want to go extract it, because now you wouldn't have process.
</details>

### 当前 Agent 的两大鸿沟：能力与流程

现在我们来谈谈 Agent。

正如我之前所言，每个人都拥有了 Co-work、ChatGPT、Codex 或 Cloud Code，但生产力究竟体现在哪里？

我们的观点是，所谓的“写代码式”Agent 产品（即你与一个 Agent 共事，只管指令它去干某件事）主要存在两大问题。

**第一个问题是存在能力鸿沟**，因为就现存形态而言，Agent 将复杂性外包给了用户。如果我是用户，我现在必须管理自己的技能和记忆，思考何时该使用 Agent，甚至需要对它建立一套“心理理论”。这极其困难。对于在座的各位来说可能觉得很简单，但我敢保证，对绝大多数知识工作者而言，他们对此完全一无所知。

<details>
<summary>Original English</summary>
Now let's talk about agents.

As I said earlier, everyone already has co-work, ChatGPT, Codex, Cloud Code, but where is that productivity?

Our opinion is there are two main problems that come with what I'll call coding-style agent products, where you're working with an agent and you just tell it to go and do something.

The first problem is that there is a competency gap, because agents, as you think of them as you think of them today, they outsource the complexity to the user. Right, if I'm the user, I now have to manage my skill and memories and think about how to when I should use the agent. I have to have like theory of mind over it. This is really hard. And for those who are here, maybe you guys find it easy, but I promise for the wide majority of knowledge workers, they have no idea how to do any of this.
</details>

**第二个问题是存在流程鸿沟**。如果你对用户说：“嘿，这是你的 Agent，想怎么用就怎么用”，那么工作完成的方式本质上就完全取决于具体用户如何去定制 Agent 的行为。

这与组织的规模化方式完全背道而驰。流程应该是由高层管理者自上而下传递的，而不是由个别员工自行决定该如何展开工作。回到我刚才的例子，哪怕倒退回 2018 年，如果每个员工都凭空发明自己提取数据的一套方法，也不会有什么好结果。

因此，我们坚信，构建能够真正端到端执行工作的生产级 Agent，关键就在于解决这两个问题。

<details>
<summary>Original English</summary>
And there's a second problem. Which is there is a process gap. Right, if you are saying, "Hey user, here's your agent, do what you want." Well, now suddenly the way the work is being done is essentially up to whoever the user is to customize the way the agent is behaving.

Which goes entirely against the way that organizations scale. The process should be coming from senior leadership down, not from any individual employee deciding how they're going to do their job. Right, if you going back to my example, if every employee just made up their own way of extracting data, you know, even back in 2018, that wouldn't be a good outcome.

And so, we believe strongly that the key [snorts] to building production agents that actually do work end-to-end is solving these two problems.
</details>

### 可靠性核心：构建“有主见”的 Agent

你必须通过让交互变得简单来弥合一致性鸿沟。对用户来说，你甚至都不需要察觉它是一个 Agent，或者你可能知情，但不会有明显的异样感。它应当像与同事共事一样简单：你只需告诉它你想做什么，所有理应起效的事情都能顺利完成。

其次是解决流程鸿沟。你需要 Agent 保持可靠，而不是某一天灵光乍现，另一天又丢三落四。这并不是说必须做到完美。人类本身就不完美，没有人指望尽善尽美；人们追求的是可靠性、一致性与可信赖度。

那么，这具体体现为什么呢？我们认为，要做到简单、可靠，让用户不必费心思琢磨步骤，Agent 能在用户无需理解内部原理的情况下直接搞定，并且能够持续以相同方式执行，你就必须**具备主见**。

<details>
<summary>Original English</summary>
You have to solve the consistency gap by making it simple. To the user, you shouldn't even have to know it's an agent. Or you probably know, but you don't have to really feel it. It should be as simple as just working with a co-worker. You just tell it what you want it to do and all the things you expect to work should work.

And the second is the process gap. You need agents to be reliable. Not having a stroke of genius one day and forgetting something the other day. It's not about being perfect. Humans are not perfect. Right, nobody is looking for perfect. What you're looking for is reliability and consistency and trustworthiness.

So, what does that actually look like? We think that to be simple and reliable where you know it's you don't have to think about what to do. The agent can just do it for you without the user knowing the internals. To do it the same way consistently, you have to be you have to be opinionated.
</details>

请让我翻回上一张幻灯片。我想指出的是，把事情做对其实并不是最主要的任务，因为人类自身同样是不完美的。重点在于**以相似的方式去完成**。哪怕有某件事你做不到，这也是可以接受的。

但你应当始终稳定地做不到某件事，随后像人类一样逐步改善。如果某一天你突然在某项任务上成了专家，转天却连最基础、理应做对的事都漏掉了，那你就是不可靠的。

所以，你必须具备主见。

何为主见的例子？假设我们有一个 Agent 需要去读取一份 PDF。那么在这种情况下，读取 PDF 的最佳方式是什么？方法很多：你可以把它扔给 VLM，你可以写几行 Python 代码并调用开源 OCR 库，或者可以接入众多专门提供 OCR 模型的供应商之一。你也可以先做一次 OCR，再让 VLM 核验它的工作；甚至可以让五个 VLM 交叉核验，或者运行 100 个 VLM 并取最优结果。这里的可能性可以说是无穷无尽的。

因此，如果你只是对它说：“Agent，提取 Excel、提取 PDF”，你或许能得到不错的结果，但它们绝不会是稳定可靠的。这不是因为它的处理过程很差，而是因为它的处理过程**缺乏明确的主见**。

<details>
<summary>Original English</summary>
Let me just show you actually one slide back here.

I want to point out that getting it right isn't actually the main task, because again, humans are imperfect themselves. The point is to do it in a similar way. It's okay if you you can't do something. But you should be consistently able to not do something, and then you get better, just like a person does. If you suddenly one day are an expert at something, and then you miss something very basic that would be expected, now you're not reliable.

So you have to be opinionated.

What's an example of an opinion? Let's say we have an agent, and we need to go and read a PDF. So in this case, what is the best way to read a PDF? There's many ways. You can throw it into a VLM, you can go write some Python code and use an open-source OCR library, you can work with one of the many OCR-specific model providers. You could do an OCR, and then you could have the VLM check its work. You could have five VLMs check its work. You could do 100 VLMs and take the best of them. There's literally infinite possibilities here.

And so if you just said, "Agent, extract Excel extract PDF," you might get good outcomes, but they're not going to be reliable. Right? Not because the process it did was bad, but because the process it did was not opinionated.
</details>

我们形成主见的方式是依靠初步直觉。有些主见源于专业经验，例如，如果我想让 Agent 做好税务工作，我知道如果 Agent 在回复用户之前先去查阅一手原始信源，其准确率往往更高。我不需要一套评估测试来告诉我这一点，也不需要从第一性原理中去推演，我们本身就清楚这一点。正如我知道如果让 Agent 制作 PowerPoint，若能在回复用户前给 PPT 截一张图核对，出现排版格式问题的几率就会更低，这是显而易见的。

形成主见的方式有很多种。在展开讨论如何运用主见之前，我想补充的关键一点是：主见不仅仅关乎准确性。我们刚刚谈到了给 PPT 截图的例子，但这会增加延迟，你可能不希望这样；或者 Agent 每 100 次才会出现 1 次排版错误，而你完全可以容忍这种频率，那么你就不必给 PPT 截图。因此，重点并不在于主见具体是什么。在本次演讲中，我们的重点不是探讨如何形成主见，而是探讨**为什么主见很重要**，以及**在生产环境中实现规模化时如何利用这些主见**。

<details>
<summary>Original English</summary>
So the way we develop opinions is you use initial intuition, right? Some things you know what the opinions are from expertise. For example, if I'm trying to get an agent to do tax work well, I know that if the agent is going goes and reads the primary source before returning to the user, it is more likely to be accurate. I don't need a set of evals to tell me that. I don't need to divine that from first principles. We know that, right? I know that if I have an agent make a PowerPoint, if it takes a picture of the PowerPoint before it returns to user, it is less likely to have a formatting issue. That is obvious.

And so, there are lots of different ways to develop opinions. And one of the key points here, I'll just make before I move on to talking about how to use the opinions, is that the opinions are not just about accuracy, right? We just talked about the example of taking a picture of a PowerPoint. Well, that adds latency, right? You may not want that. Maybe the agent only makes formatting mistakes one out of a hundred times, and you're okay with that. And so, therefore, you don't have to take a picture of the PowerPoint. The point isn't exactly what the opinion is. And this talk, we're going to focus not on how to develop opinions, but why opinions matter, and then how to leverage those opinions as you scale in production.
</details>

### 从结果评估走向行为规范（Behavior Spec）

假设你拥有一堆基于结果的评估。我所说的基于结果的评估，是指我们传统意义上的评估测试：它有一个正确答案，我们有一套评分标准来评判 Agent 所做的事情。

你如何知道这些评估能泛化到生产环境中？你手里可能只有 100 个或 1,000 个测试用例，但在生产环境中处理真实业务时，你将面对数十万种不同情况。随着执行轨迹越来越长，这种情况只会愈演愈烈，因为随着 Agent 长程能力的增强，单条轨迹中所做的决策数量呈指数级增长。

面对这些轨迹的分布，你无法证明其中的每一条都是正确的，你不可能对每一条轨迹都掌握基准真相。但你或许可以通过观察轨迹，来判定你所设定的行为准则（即你的主见）是否被切实执行了。

进而你可以推断，如果它确实被执行了，它就更有可能泛化到生产环境。这并不完美，你无法百分之百确信，但至少你建立起了主见。

<details>
<summary>Original English</summary>
So, say that you have a bunch of outcome-based evals. And when I say outcome-based evals, I mean what we traditionally think of as evals. It has a right answer. We have some rubric we're trying to judge what the agent did.

How do you know that the evals generalize to production? Right? You might have a thousand cases or a hundred cases. But in production, if you're doing real work, you're going to have hundreds of thousands of situations. And that's only going to increase as the trajectories get much longer, because the amount of decisions that are made in a trajectory uh just grow exponentially as the like long horizon abilities of agents increase.

And so, I can't prove if I If you're looking at all these distribution of uh trajectories, you can't prove every one of them is correct. You don't have a ground truth for every trajectory. But you can potentially look at the trajectories to decide if the behavior, the opinion that you have, is actually happening.

And you can then infer that if it's actually happening, it's more likely to generalize to production. It's not perfect. You don't know for sure, but at least you are having an opinion.
</details>

我们来看一个实际的例子。

在一种行为要求中，比如这是一个会计方面的例子：在银行对账出现差错时，我不希望 Agent 随意记一笔账来把它强行配平；我希望它能够解释差异，而不是硬填一个凑数项。这同样具有主观性，你可能希望采用另一种处理方式。

但你绝对不希望客户遇到的是：这一次是这种处理方式，下一次又变成了另一种方式。

那么该怎么做呢？首先，我们需要理解究竟是什么在主导行为。行为并不仅仅是你在系统提示词里写上两句话就能直接生效的。对于非常简单狭窄的 Agent 也许管用，但当你构建大型 Agent 系统时，其行为实际上是系统提示词、渐进式信息披露、工具描述，以及模型本身训练的综合结果。有诸多因素在左右其行为。

顺便分享一个关于构建生产级 Agent 的心得：务必将 Agent 在运行时所看到的上下文视作**运行时训练数据**。“提示词”这个词我认为把事情轻描淡写了；归根结底，这是 Agent 在运行时接受训练的数据。虽然不是字面意义上的模型训练，但实际效果就是训练。因此，你必须重视每一个 Token，理解这些数据是如何驱动 Agent 表现出特定行为的。

<details>
<summary>Original English</summary>
Let's run through a real example. So, let's say that I uh for a behavior, this is a an accounting example where if there is a uh mistake for uh in in the bank reconciliation, um uh I don't want the agent to like post an entry to make it tie. I want it to uh it sort of explain the difference instead of putting a plug. Again, this is subjective. You might want the other way.

But, what you don't want is a customer getting one way one time and another way the other time.

And so, what would you do? Well, first, let's understand what governs the behavior. Right? The behavior's not just you write the two sentences into your system prompt and it just works. That might work for very simple narrow agents. But, when you're building these big agent systems, the behavior's actually a combination of the system prompt, your progressive disclosures, uh potentially tool descriptions, obviously the training of the model. There's a lot of things that govern the behavior.

And one tip, by the way, I have for when you think about building production agents is really think of the context the agent is going to see as it's working as runtime training data. The word prompt, I think, trivializes it a bit, right? At the end of the day, this is the data that the agent is being trained on at runtime. Not literally trained on, but effectively trained on. And so, you want to care about every single token and understand how that data causes the agent to behave in certain ways.
</details>

因此，当你在生产环境中部署行为规范时，单纯依靠某一个段落很难精准锁定某一特定行为，因为行为是由全局所有数据共同决定的，而非单一要素。

我们在 Basis 开发的核心概念之一就是**行为规范（Behavior Spec）**。

行为规范的核心逻辑是：在更新或撰写上下文之前，我们究竟想要什么？我们的意图是什么？你可以将其视作 Agent 时代的“产品规格说明书（PRD）”。你不可能、也不应该把每一处细枝末节都写下来；你应该提炼出最关键的主见并明确记录，因为如果面面俱到，就会产生大量的状态冗余。因此，只需定义最重要的主见。

随后，你可以借此从规范的视角对齐团队；同时，你也可以将它用作评估标准。你可以据此审视：在这条特定的执行轨迹中（无论是任何没有基准真相的轨迹），Agent 是否遇到了与该行为相关的场景？如果是，它是否切实展现出了该行为？

通过这种方式，你可以大幅扩展在轨迹上获取信号的规模，这远比试图不断增加基于结果的评估、基准真相和评分标准要高效得多。那些评估手段虽然十分重要，但其扩展速度绝不可能赶上监督 Agent 行为规范的扩展能力。

<details>
<summary>Original English</summary>
So, when you're putting uh behaviors into production, it it might be very difficult for one behavior to put it in exactly one, you know, paragraph that you know exactly because again, the behavior is all of the data at once, not just one thing.

And one of the things that we developed at Basis was this concept of a behavior spec. And the idea of a behavior spec is essentially saying before we update the context or write the context, uh what do we actually want? What is our intent? You can kind of think of this a little bit as like a product spec for the agent era.

And you can't write You shouldn't be writing every detail down. You should be taking the most important opinions and putting it because if you put everything, you'll be duplicating a lot of state. So, you define the ones that matter the most.

And then you can use them as a way to align your team from a spec perspective, but then you can also use them as a rubric. And you can say in this particular trajectory, whether that is in any trajectory that doesn't have a ground truth, did the agent get into a situation in which this behavior was relevant? And then if so, did it actually exhibit the behavior?

And this way you can scale the amount of signal that you get on your trajectories far larger than trying to increase the amount of outcome-based evals, ground truths, and rubrics that you have. Those are really important, but you cannot scale those anywhere near as fast as you can scale the ability to supervise what the behaviors of the agent are.
</details>

### 工具手段：分叉（Forking）与模拟（Simulations）

我们来看一个简短的示例。

这就引出了第二个概念：**分叉（Forking）**，我们可以将其与行为规范结合使用。如果你曾使用过 Cloud Code 或 Codex 的网页端应用，每条消息下方都会有一个小小的分叉图标，让你可以复制一份使用相同上下文的 Agent，这在本地计算机上运行非常顺畅。而在云端构建一个能完美复刻数据库环境、提示词等各种运行环境的系统则十分困难。但分叉确实是我们用来检验行为的另一项工具。

你可以设想这样一种工作流：出现了一条轨迹（可能来自评估集、测试环节或生产环境），它未能通过行为评估。此时你需要查明原因：为什么它未通过行为评估？为什么它未能展现出预期的行为？你可以深入该轨迹，直接定位到 Agent 做出背离既定行为决策之前的那个节点（前提是你的行为定义明确并能有效输出信号）。

随后你可以进行分叉。

分叉之后，你可以在它刚做出决策后追问：你为什么那么做？或者你也可以去更新 Agent 的上下文，观察这样是否能改善其行为。通过分叉机制，你能够切实捕捉到这些信号，并开始探索：该如何改进测试底座以充分利用这一信号？

相比之下，如果你只依靠基于结果的评估信号，做起来难度就要大得多。如果最终结果失败了，你如何知道原因出在哪里？在一个运行长达 5 小时的 Agent 轨迹中，可能包含了上千次模型推理调用。

<details>
<summary>Original English</summary>
Let's just take a quick example here.

Um this is so this is actually the second concept, um which is called forking, which we can combine here with behavior specs to think about. Forking, if you've ever used uh cloud code or or Codex the web apps, there's a little little fork icon uh under each message, uh where you can essentially create a copy of the agent using the same thing, which works really well on your local computer. It's hard to build a system that does this in the cloud perfectly with recreating the database environment and recreating the uh the prompts, uh all the all the different environments. But forking is another tool that we use to check the behavior.

So, a flow that you can imagine is saying we had a trajectory, could be in an eval set, it could be in testing or in production, and it failed the behavior eval. And now you're trying to understand why. Why did it fail failed the behavior eval? Why did it not exhibit the behavior? And then you can go into the trajectory, go right before the point in which the agent made the decision that was in contrast to the behavior, assuming again your behavior is good, and it's actually producing signal.

And then you can fork it. And when you fork it, you can ask the agent uh or you would fork it right after it made the decision. You could ask it why did you do that? Or you can go and update the uh context of the agent and see if that improves the behavior. And so with forking you can start to actually take the signal and start to figure out, okay, how can we then improve the harness to now uh leverage the signal?

Whereas if you're just looking at signal from an outcome-based eval, you can't do that anywhere near as easily because it failed the outcome, how do you know why? You have potentially a thousand inference calls in your 5-hour long agent trajectory run.
</details>

接下来是我想探讨的最后一种工具，这也是我个人的最爱：**模拟（Simulations）**。

这听起来可能有点不可思议，但我保证它非常行之有效：在使用编码 Agent 时，你可以让该编码 Agent 生成一个子 Agent，用来模拟你的生产级 Agent。

你必须要求它不得作弊，并向其提供完整的系统提示词、技能配置，将一切要素完整渲染。你可以向它询问在某些特定场景下会采取什么行动。你可以设定具体的场景条件，观察是否能重现在评估或生产环境中遇到的状况。如果能够复现，你就可以调整上下文，观察子 Agent 是否会根据你的调整而改变其行为。

采取这种做法的原因在于，尽管它的仿真度显然不及分叉，但它要便宜得多、快捷得多，允许 Agent 开发者极其轻松地迭代思路，而无需经历在真实环境中完整分叉的高昂成本。

你现在无需额外构建任何基础设施就能做到这一点。在我们将分叉能力集成进内部系统之前，我个人使用这种模拟方法持续了一年半以上。

其核心逻辑在于，对照先前展示的分布曲线，你需要了解 Agent 是否泛化到了该分布中。单纯依靠结果评估无法确认这一点。你可以尽量挑选最具代表性的结果评估用例，但依然难以确证。因此，通过上述方法来监督执行过程，能够为你提供补充信号，帮助你判断其是否正确实现了泛化。

<details>
<summary>Original English</summary>
And then we have the last tool that I'd like to talk about. This is actually my favorite, which is called simulations.

Uh this is going to sound silly, but I promise it's very effective, which is that you can, when working with coding agents, ask the coding agent to make a sub agent that pretends to be your production agent. And you have to tell it to not cheat, and you give it the system prompt and the skills, and you render everything perfectly. And what you can do is you can ask it what it would do in some scenario. You can give it the situation, and see if you can recreate the situation that you saw in your eval or in production. And if you can recreate it, now you can tweak your context to see if the sub agent would change its behavior based on your tweaks.

And the reason to do this is obviously far worse than forking, but you do this because this is much cheaper, much faster, and allows you as an agent builder to really easily iterate on ideas without needing to go through the expensive process of actually forking an entire environment.

And you can do this today without building anything. Um I did this for literally year year and a half plus before we uh built forking into our internal systems.

And the main idea here is understanding that if you look at the the distribution from earlier, you're trying to understand is the is the uh agent generalizing to that distribution. And so you don't know purely based on the outcome eval. So you can try to choose the best outcome evals that should represent the curve, but you don't really know. And so supervising the process through some of these methods gives you some additional signal in order to understand if it's generalizing properly.
</details>

### 闭环迭代与建立信任

非常酷的一点在于，随着你获取到的信号越来越多，你就可以真正开始闭环。主见正是让你做到这一点的关键。如果你对自己的系统缺乏主见，你就无法挖掘出这些关键信号。

现在回到事务所的场景：我们谈到了监督，也谈到了如果 Agent 具有主见，它就能变得更加可靠，用起来也会更简单。

这意味着 Agent 可能最初只负责处理狭窄范围的工作，但由于人们与其共事后发现它易于上手且运行可靠，随着它不断进化，团队对它的信任也会与日俱增。这与对待人类同事是一样的。假设第一天来了一位新同事，当有人向你提交 PR（代码合并请求）时，你通常会基于两个维度去评估：PR 的改动范围有多大，以及你认为该员工的能力有多强？

如果公司里业务能力最薄弱的员工提交了一个修改核心服务的 PR，你一定会逐行严格审查；而如果能力最强的员工提交的只是修改内部文档的 PR，你可能就不会投入那么多精力去核对。人类与 Agent 协作同样遵循这一规律，正如人类之间共事一样。

<details>
<summary>Original English</summary>
And what's really cool is as you start to get more signal, you can actually start to close the loop. And an opinion is what lets you do that, right? If you don't have opinions about your system, you're not going to be able to develop that signal.

And now if we go back to the firm, we talk about talk about supervision, we talked about how the agent uh if he's our opinionated, he can be more reliable and he actually can be simpler. What that means is the agent maybe it starts doing something narrow, but because people will work with it, they see that it's easy to use, and they see that it's reliable. As it gets better and better, they will trust it more. It's just like a co-worker. You have a co-worker day one. Imagine someone sends you a PR. You're not going to if it's you're looking at two axes whenever someone sends you a PR. It's these two axes. What's the black greatest of the PR, and what is your perception of how competent that person is?

Right? If the least competent person in your company is sending you a PR that's editing a core service, you're going to look at it. If the most competent person is sending you a PR that's editing an internal document, you may not look at it as much. And so this idea is true with humans working with agents just like it is with humans working with humans.
</details>

最后我想强调一点作为结语：许多人在听到这些时会说：“等一下，如果完全放手让 Agent 自行探索，它们难道不会找到更好的办法吗？它们难道不能在工作中走出类似于‘第 37 手’（Move 37）的神来之笔吗？”

答案是：它们确实有可能做到。

但这绝不是扩大 GDP 和提高产出的途径。没有人希望 Agent 在做报税申报表时来一招“第 37 手”。人们需要的是在规模化运作下以可靠、可信、且符合团队协作习惯的方式完成工作。

因此，我想留给各位的核心结论是：**Agent 要想普及开来，必须足够简单；要赢得团队的信任，必须足够可靠。** 而实现简单与可靠的途径，在于对 Agent 的行为确立明确的主见；这些主见将帮助你建立额外的反馈信号以实现闭环，进而在生产环境中实现持续自我进化的 Agent。

非常感谢大家。

>> [掌声]

<details>
<summary>Original English</summary>
And I think I just wanted to make one last point to close here, which is that one of the things that people say when they hear this is, "Well, wait a second. If you let the agents just do what they want, won't they find a better way? Won't they move 37 your work?

And the answer is they might. But that's not how you scale GDP and scale output. Nobody wants their agent to move 37 their tax return. They want it done reliably, at scale, in a way that they can trust, and in a way that their people know how to work with.

And so the thing I will leave you with is for agents to diffuse, they need to be simple. For teams to trust them, they need to be reliable. The way you get to simple and reliable is you develop opinions on how the agent behaves, and then opinions allow you to build that additional signal that helps you start to close the loop so that you can achieve self-improving agents in production.

Thank you very much.

>> [applause]
</details>