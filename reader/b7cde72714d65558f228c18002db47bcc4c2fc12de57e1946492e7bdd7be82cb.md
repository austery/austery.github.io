---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3Krz7Rdd4JI
speaker: AI Engineer
tags:
  - agent-standard
  - agent-runtime
  - interoperability
  - typescript
title: Justin Schroeder 发布 Standard Agent 规范：构建互操作的领域专用智能体生态
summary: Justin Schroeder 指出当前企业自建 Agent 难以互通且存在失控风险，提出 Standard Agent 规范与首个公共运行时 Standard Agent Builder，主张将智能体定义为代码并绑定特定模型，以实现跨环境复用与高效组合。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Justin Schroeder
companies_orgs: []
products_models:
  - Standard Agent Builder
  - DeepSeek V 4.1 Flash
media_books: []
status: evergreen
---
### 企业自建智能体现状与当下主流认知的偏差

嗨，我叫 Justin Schrader。我今天想和大家聊聊标准智能体（standard agents），特别是智能体的标准化。但在开始之前，我想先提一个有趣的观察。现在我注意到每个人都在构建智能体。如果你今天走在街上，很可能会遇到正在构建智能体来助力自己业务的人。这其实挺奇怪的，因为这与当下普遍的认知相悖。

<details>
<summary>Original English</summary>
Hey, my name's Justin Schrader. I'm going to talk to you about standard agents and specifically standardizing agents. But before I do, I want to mention an interesting observation. Um, right now I'm noticing that everybody's building agents. Um, if you walk down your street today, you're probably going to run into people who are building agents to help power their business. And this is actually weird because it goes against the prevailing wisdom of the day.
</details>

现在，大多数深耕 AI 领域的人都会告诉你，将 AI 引入并赋能你的业务的正确方式，是构建一个 MCP 服务器来暴露你业务的各个组成部分，然后写一些 Markdown 文件、技能（skill）文件，或者 agents.md 文件，对吧？你写一些 Markdown 文件，本质上就是写文档，然后把它交给一个足够聪明的模型，比如 Claude 或 Grok bot agent 之类的，然后就大功告成了。这就足够了，也能把事情做好。

<details>
<summary>Original English</summary>
Right now, most people who are deep in AI are going to tell you that the right way to put your business and and enable your business with AI is to build an MCP server that exposes the pieces and parts of your business and then write some markdown files, skill files or uh agents MD files, right? You You write some markdown files, basically documentation, and then you give it to a sufficiently smart uh model. So something like, you know, a Claude or a Grok bot agent, something like that. And then you call it a day. This is sufficient and this is going to do the job.
</details>

有趣的是，大家并没有这么做。我的意思是，人们确实在做 MCP，但他们依然在构建智能体。我们可以将这视作他们可能只是在犯错。也许这些人只是用错了方法，我们需要给他们更好的建议。这也许说得通。但我实际上认为，市场展现给我们的现象背后是有智慧的。这里面还有更深层的原因我想聊一聊。

<details>
<summary>Original English</summary>
And what's interesting is people just aren't doing this. Well, I mean, people are building MCP, but they're still building agents. So we could view this potentially as they're just making a mistake. Maybe these people are just doing the wrong thing and we need to advise them better. And that might be true. But I actually think that there's some wisdom in what the market is showing us. There's something more there that I want to talk about.
</details>

### 人们依然构建独立智能体的三大核心原因

我认为这可以归结为三个因素。我认为人们依然在构建智能体有三个主要原因。在讲到标准之前，我想先逐一梳理一下。

<details>
<summary>Original English</summary>
And I think it comes down to three factors. I think there's three primary reasons why people are still building agents. I want to walk through them before we get into standard.
</details>

首先是**集成（Integration）**。

企业需要将其深深嵌入在业务内部的流程妥善处理好。对企业来说，这些绝非细枝末节。例如以暖通空调（HVAC）维修公司为例，构成该组织的业务流程各种各样。比如管理保修索赔。当一份保修索赔提交进来时，你怎么知道它是否在适用的期限内，或者是否属于保修承诺的范围？再比如人员排班。工程人员在大城市里到处跑，处理各种作业，你怎么确保正确的人员被派往了正确的地点？这对他们的业务良性运转至关重要，而且他们已经拥有大量软件来协助处理这些了。那从州政府调取许可证呢？营销活动管理、客户扩增，或者是工单物料管理呢？一家企业为了有效运作，需要处理非常多重要的业务流程。

<details>
<summary>Original English</summary>
First is integration. Businesses need their processes that are deeply embedded inside of their business to be handled properly. These are not small factors for the business. For example, take something like an HVAC repair company. You have all kinds of business processes that make up that organization. Things like, you know, managing warranty claims. How do you know when a warranty claim comes in that it's within the appropriate period or that it's one of the things that was guaranteed? How about crew scheduling? Crews are running all over a big city trying to perform various operations. How do you know that the right people are going to the right places? This is critical their business to function well, and they already have lots of software to help handle this. How about pulling permits from the state? How about campaign management or account expansion or job materials? There are so many important processes that a given business needs for it to operate effectively.
</details>

而且不仅限于暖通维修。暖通维修有一大堆流程，大学也是如此。助学金怎么发？我们如何确保助学金发放得当，还有科研基金管理，或者宿舍分配？如果是云服务商呢？确保没有滥用或计费争议。所有这些目前正在被处理的重要流程，如果你想集成 AI，都必须妥善处理。这不仅限于三家，而是适用于任何组织。还有各种更高阶的事情，比如薪资核算或合同审查。所有这些都是重要的流程。事实证明，企业本质上就是其流程的总和。

<details>
<summary>Original English</summary>
And it's not just HVAC repair. HVAC repair has a bunch, but universities. How about financial aid? How do we make sure that financial aid is properly given out or grant administration or housing assignments? How about something like a cloud provider? Making sure that um we aren't having abuse or billing disputes. There are all kinds of important processes that are currently being handled that if you want to integrate AI, need to be handled properly. And it's not just three, it's really any organization. There's all kinds of other higher order things like payroll or contract review. All of these are important processes. It turns out that a business
</details>

那是它的根基与核心。实际上，让一家特定企业产生价值的一切，本质上都是流程良好运转的结果。像人际关系、网络效应和专有数据，所有这些都是流程出色运转的结果，无论具体流程是什么、有多少，对吧？所以，用像 Grokbot 这样的通用大模型来运行所有这些流程的想法，坦白讲是让人难以接受的。大家不想要这样。即便它能运行得很好——在一些超大模型上很可能会运行得不错——这也太冒险了。把企业最关键的业务流程、把让他们成为这家企业的核心交付出去，风险太高了。

<details>
<summary>Original English</summary>
is really just its processes. That is its foundation, its core. In fact, everything that makes a given business valuable is really the result of the processes that got there. So things like relationships and network effects and proprietary data, all of those come as a result of the process working really well, whatever that is and however many that is, right? So the idea that we're going to use something like Grokbot to start running all of those processes, honestly, it is it's just not palatable. People do not want this. Even if it works well, which it probably will with some of these really big models, it's too risky. It's too risky to take their business critical process, the thing that makes them who they are as a business and hand that over.
</details>

所以企业真正想要的——我们甚至在自己的经验中也发现了这一点——是他们真正需要掌控力。然后他们需要信任流程。他们需要长久可靠的执行。它必须是可复现的。对于同一笔索赔，它必须以相同的方式运作。最后，它不能是泛化的通用方案。你不能只用完全通用的工具来执行这些，对吧？每家企业都有自己想要保持的特定声音和基调。以上就是集成。

<details>
<summary>Original English</summary>
So what businesses really want, and we've found this even in our own experience, is they really want control. And then they need to trust the process. They need to have reliable execution over time. And it needs to be repeatable. It needs to work the same way for the same claim, okay? And finally, it can't be generic. just can't use completely generic tools to perform this, right? There's a voice, there's a tone that a given business has that they want to preserve. So that's integration.
</details>

我认为企业真正需要的第二个部分，是必须能够**信任（Trust）**智能体的所作所为。

我们常说的一句话是：如果一个智能体什么都能做，那它就可能做出任何事。这是一种隐患。事实上，这是一种巨大的隐患，是无法接受的。

<details>
<summary>Original English</summary>
The second part I think that businesses really need is they need to be able to trust what the agent does. And what we like to say around here is that if an agent can do anything, it might do anything. And that is a liability. In fact, that's a really big liability and something that is untenable.
</details>

所以你真的需要限制 Grokbot 能做的事情，将其严格限制在非常精细的范围内，对吧？我的意思是——这里我显然是在开玩笑——“嘿，你收到保修索赔了吗？”“收到了，但登不进保修门户，所以我顺便注册了个新账号。”像 Grokbot 做出这种事并非不可能。或者“我顺手回了几封邮件”、“我去查了查选举结果”等等。原因当然只是因为它拥有这些工具，它有能力做这些事。现在，这些聪明的模型通常不会犯这类错误，但这绝对是有可能发生的，对吧？Grokbot 完全有能力在执行某项业务操作的过程中，跑去刷一下 X 账号。企业可不希望发生这种事，完全不希望。

<details>
<summary>Original English</summary>
So you really need to restrict what Grokbot can do down to something really, really fine tuned, right? You know, I mean, here this I'm obviously in jest, but you know, hey, did you get the warranty claim? Yeah, couldn't sign into the warranty portal, so I made a new account, right? I mean, it is not out of the question that Grokbot would do something like that. Or I replied to some emails while I was at it. I read up on the election results, so on and so forth. And the reason of course is just because it has those tools. It has the ability to do that. Now usually these smart models don't make those result those errors those those kinds of mistakes, but it absolutely can happen, right? So Grokbot has the ability to go check an X account while it's in the middle of performing some other operation. And businesses don't want that. They don't want that.
</details>

相反，他们想要的是非常明确的工作流：某个保修索赔触发特定的智能体去处理任务。该智能体配备了非常具体的工具，比如查询设备信息、附上照片、提交索赔。这些是完整的智能体，支持多轮交互，能执行实际工作，能进行评估，也有自己的上下文，但它们能做的事情在范围上是受限的。我们不能仅凭信任假设模型不会越界行事。因此，第二点——信任，绝对至关重要。

<details>
<summary>Original English</summary>
Now instead what they want is a very clear workflow where some claim is, you know, warranty claim is triggering a given agent to pick up some work. And that agent has very specific tools like looking up equipment, attaching photos, submitting a claim. Now these are full agents. They have multi turns. They can perform real work. They can do evaluation. They have their own context, but they are limited in their scope to what they can actually perform. We're not just trusting that a model's not going to go do that. So trust, number two, absolutely critical.
</details>

第三点是**功效（Efficacy）**。

不是效率（efficiency），而是功效。这可能是三者中最重要的。我们必须确保任务被完成了，而且完成得很漂亮。单说“我的模型够不够聪明”是不够的，关键在于：它能否完成所交付的任务？能否高效完成？总体而言，与我们之前的做法相比，它是否提升了业务或该流程的成效？

<details>
<summary>Original English</summary>
Number three is efficacy. Not efficiency, efficacy. This is the most important of the three perhaps. We need to make sure that the job is done and it's done well. You know, it's it's not enough to say like is my model smart enough, but can it do the task it's been given? Can it do it efficiently? And the in the totality, does it improve the performance of the business or of that process over what we were previously doing?
</details>

这至关重要。想想我们的暖通空调保修索赔。保修索赔本身对智能体来说是一个较小的任务，但我们认为这恰恰能做成一个极好的智能体。那一整个环节，仅保修索赔这一件事，就是一个智能体。它不是一条简单的工作流，它有多轮交互，是一个货真价实的智能体。这么做非常棒的一点在于，你可以对所有的业务流程进行评测（eval）。当你尝试对一个超大型语言模型做评测时，它在受测的项目五花八门。你看到的实际上是某种形式的随时间推移的“刷榜”（bench maxing），它试图在被观察的指标上表现优异。这本身不是坏事，但如果你想要的东西不包含在其中，那就糟糕了。然而对于一个针对特定任务精调的智能体而言，这种针对性优化其实是积极的。如果一个独立模型配合独立的提示词、独立的工具，只需做好被要求的唯一任务，从而获得极高的有效率和评测通过率，这是一件好事。

<details>
<summary>Original English</summary>
That is absolutely important. So think about, you know, our HVAC warranty claim. Our warranty claim itself, that's a small task for an agent, but what we're saying is that would actually make a great agent. That entire thing, just the warranty claim would be an agent. It's not a workflow. It has multiple turns. It is a legitimate agent. And what's really cool about this is you can take all of your business processes and then you can eval them, right? When you try to eval a really large language model, it's being evaled on so many different things. And what you see is effectively a form of bench maxing over time where it tries to get really good at the things that are being observed. That's not a bad thing. It's just bad if what you are wanting out of it is not one of those things. But with an agent that is fine tuned for a very specific task, that bench maxing is actually a positive. It's a good thing for an individual model with an individual prompt, with an with individual tools to have a very high efficacy rate and a very high eval pass rate if that's all that they're being asked to do.
</details>

### 小型领域专用智能体与大型全能模型的对比

因此，现状是我们使用的是像 Opus 55 这样极其聪明的模型，这是一个了不起的模型。然后我们就不停地给它塞更多的工具和技能。我不想说这行不通，因为我们已经建立了一个这种方式运行极好的生态。然而，它非常庞大；相比之下，你完全可以用像 DeepSeek V 4.1 Flash 这样只执行单一操作的模型来构建，比如只做保修索赔智能体。

<details>
<summary>Original English</summary>
So the current state of affairs is that we use super super smart models like, you know, Opus 55 which is a spectacular model. And And then we just give it more tools and more skills. And I don't want to say that this doesn't work because we have created an ecosystem where this works tremendously well. However, it can It is also very very large as opposed to creating something with, you know, DeepSeek V V 4.1 Flash that is only performing one operation, something something like the warranty claims agent.
</details>

因此从根本上说，一个 Gmail 智能体胜过一个 Gmail 技能。这并不是说两者不能同时奏效。当然，Claude 可以很轻松地借助技能去查看 Gmail，甚至不借助技能也可能办到。但 DeepSeek V 4.1 Flash 在这件事上其实也能完成得出类拔萃。

显然这样会便宜得多，Flash 极度便宜。而且你还可以对那个极其轻量的智能体进行评测。大家如果记得几个月前那篇 Jeppa 的论文，里面提到微调智能体——微调智能体的提示词——实际上比微调模型更有效。这千真万确。我们可以让 DeepSeek V 4.1 Flash 在仅作为 Gmail 智能体这件事上表现得惊人出色。这非常简单，只有当你要求它做超出这个范围的事情时，它才会崩溃。最终，你还可以把它组合进一个更大的系统里。你可以将 Gmail 智能体作为一个 MCP 服务器暴露给 Opus 55，也可以构建层级结构，让这些小型智能体在一个同样具有明确任务的更大智能体下协同工作。

<details>
<summary>Original English</summary>
So fundamentally, a Gmail agent beats a Gmail skill. It's not that both of them don't work. Of course, Claude can very easily use a skill to go check Gmail or probably do it without a skill. But DeepSeek V 4.1 Flash can actually do a tremendous job of this. So it's definitely going to be cheaper, obviously. Flash is incredibly cheap. Um, but you can actually eval that tiny little agent. And if you guys remember the Jeppa paper from uh several months ago, it said that fine tuning an agent is actually more effective, fine tuning the prompt of an agent than fine tuning a model. And that is absolutely true. We can get DeepSeek V you know, 4.1 Flash to do a tremendous job, an incredible job of just being a Gmail agent. That's very simple. It only falls apart when you ask it to be way more than that. And then finally, you can compose it into a larger system. You could even expose the Gmail agent as an MCP server to Opus 55 or you could create an hierarchy of these smaller agents all working together under some larger agent that has a defined task as well.
</details>

### 当前智能体生态的碎片化与缺乏运行时的困境

如果这些小型领域专用智能体这么好，为什么没有随处可见？为什么大家没有随处使用它们？嗯，其实某种程度上是有的，对吧？因为现在每个人差不多都在构建智能体。问题在于它们太杂乱了。大家用各种不同的语言编写它们，写各种各样的工具，设计五花八门的智能体循环。这有点混乱。而且事实是，构建智能体其实很难。基础概念确实简单：一个模型，某种系统提示词，塞进一些工具，然后加上消息历史记录。但在现实中这其实非常困难。有太多需要操心的事情：循环的实际编排；在报错前可以走多少步；你需要异步系统来处理的并行工具执行；为了能在出错后继续恢复运行的持久化机制。构建一个智能体需要投入很多东西。实际上，要构建一个智能体，你真正做的是构建一个测试运行底座（harness）。

<details>
<summary>Original English</summary>
So, if these smaller domain specific agents are so great, why aren't they everywhere? Why isn't everybody using them everywhere? Well, they sort of are, right? Because everybody kind of is building agents right now. The problem is that they're just a mess. Everybody's writing them in all kinds of different languages, writing all kinds of different tools, all kinds of different uh agentic loops. It's it's a bit of a mess. And the truth is that agents are actually hard. The base is really simple, right? You just have a model, then you've got a system prompt of some kind, you put some tools in there, then you have a message histories. Uh but in reality, of course, it's actually very hard. There are so many things to worry about. Um there's you know, the actual orchestration of the loops, how many steps it can take before there's a problem. You have parallel tool execution where you need some sort of async system to handle those. You need durability so we can pick up after errors. There is a lot that goes into building an agent. And really in order to build an agent, what you're really doing is you're building a harness.
</details>

哪怕你走 MCP 路线，只做 MCP，许多和我们交流的企业常发现它们也需要推理。工具本身需要推理才能变得更有价值。但如果你开始在那里提供推理，很快你就需要多步推理，不知不觉中，你就在 MCP 内部又重新造了另一套智能体系统。

退一步说，即便你构建了自定义底座，仍有一些重要问题需要解决。例如，我构建了一个自定义底座，你构建了一个自定义底座，我们之间无法轻易共享。它可能无法在我的托管环境中运行。关于如何将其共享给他人，存在各种各样的问题。还有组合性：如何把两个底座拼装在一起并让它们高效协同？如果我的构建方式与你的不同，它们从根本上就不兼容。而且我们无法规模化构建它们。比如我不想手工打造几百个这样的定制智能体，这太疯狂了。我不想这么做，结果折腾到最后还是回到了 Grokbot。一定有更好的办法。

<details>
<summary>Original English</summary>
And even if you did go down the MCP path and all you were doing was MCP, well often you're going to find and a lot of businesses that we talk to are finding that they also need inference. The tools themselves need inference to become more more valuable. But if you're going to start providing inference there, then pretty soon you need multiple steps of inference, and all of a sudden you've recreated another agent system just within MCP. But even if you did build a custom harness, there are still important problems that have to be solved. For example, I can't build a custom harness and you build a custom harness and then we just easily share with each other. It might not run in my hosting environment. There's all kinds of questions about how you would actually share that with someone else. Or how about composition? How do you actually put two of these things together and have them work efficiently together? If I built mine in a different way than yours, then they're they're fundamentally incompatible. And we're not building them at scale. Like I don't want to build hundreds of these custom agents. That's insane. I don't want to do that and then ultimately just end up with Grokbot at the end of the day. There has to be something better than that.
</details>

我们能看到这种趋势，因为即便是技能也不是完全由单个人写的，背后有一个庞大的人群在编写技能生态。同样，这些只是 Markdown 文件。因此，一个人或一家企业凭一己之力创建数百或数千个互操作的自有智能体的想法有些荒谬。相反，我们需要一个可共享智能体的生态系统。

<details>
<summary>Original English</summary>
And we see this because even skills aren't being written entirely by one person. There's an entire ecosystem of people's people writing skills. Again, these are just markdown files. So the idea that one person is or one business is going to create hundreds or thousands of their own agents that are interoperable is a little bit silly. We need an ecosystem of shareable agents instead.
</details>

### Standard Agent Specification 规范发布与核心原则

所以解决方案显然是标准，对吧？这就是我整场演讲的重点。我们正在探讨标准智能体。有趣的是，我们在很大程度上已经对智能体进行了标准化，我们标准化了它周围的东西，对吧？对于工具，我们有 MCP，这基本上是一种工具分发标准。

技能基本上是我们决定可以标准化的一种提示词形式。我们有 Agents.md，这是另一种提示词形式。我们有用于跨智能体交互的 A2A；我们有 ACP；如果你想进行支付，还有 X402。智能体生态系统周围已经开始演化出各种各样的标准。

但截至今天，底座（harness）本身却没有任何标准。还没有智能体运行时（agent runtime）。

<details>
<summary>Original English</summary>
So the solution is obviously standards, right? That's the whole point of my talk. We're talking about standard agents. And what's interesting is that we have standardized agents to a large degree. We've standardized the things around them, right? So for tools, we have MCP, a basically tool distribution standards. Skills are basically a form of prompts that we have decided we can standardize. We have Agents MD, another form of prompts. We have A2A for for inter communication. We have ACP and we've got, you know, X402 if you want to do payments. There's all kinds of standards that are starting to evolve around the agent ecosystem. But as of today, there is nothing for the harness itself. There is no agent runtime.
</details>

这至关重要，因为一份规范能带给你的收益极为关键。首先是**速度**。每次创建智能体时，你无需重新发明轮子，对吧？你可以拥有定义明确的智能体循环，明确知晓如何编写工具，我们的智能体不需要负责构建底层生态的那部分。其次是**一致性**。每个智能体的构建方式都应该完全相同。这并不意味着每个智能体都只是一份 Markdown 文件，它需要具备深度的自定义能力，但这些自定义应当能自动运行在任何兼容的运行时中。还有**可移植性**。我需要能够编写一个智能体，把它打包，甚至只要我愿意就可以直接存到 zip 驱动器或优盘里交给你。当然还有**可组合性**。这个词可能稍微有点泛泛且被过度使用，但它的本义就是将较小的部件组装成超越其自身更大的整体。可组合性是释放领域专用智能体推向市场的关键钥匙。我们需要这个，但遗憾的是，在此之前根本不存在这样的规范。

<details>
<summary>Original English</summary>
And this is important because what a spec actually gets you is incredibly important. First of all, speed. You don't have to reinvent the world every time you create an agent, right? You can have the exact agentic loop specified. We can know exactly how to write tools. Our agents are not responsible for building that part of the ecosystem. Consistency. Every agent should be built exactly the same way. Now, that doesn't mean that every agent is just a markdown file. It needs to have deep, deep ability to customize, but those customizations should automatically work in any compatible runtime. There's also portability. I need to be able to write an agent, pack it up, and literally put it on a zip drive if I want to, or a USB stick, and give it to you. And of course, composability. This is, you know, perhaps a little bit of a vague and overused term, but all it means is that you're assembling smaller parts into something larger than itself. And composability is really a huge key to unlocking how domain-specific agents can be brought to the market. So we need this, but unfortunately, no such spec exists until today.
</details>

直到今天。我非常兴奋地向大家介绍 **Standard Agent Specification**。伴随着你们收看这个视频，我们正是今天公开发布。这是一份开源规范，今天已经在 standardagentspec.org 上线，我想带大家浏览一下。

首先，我们提出了一些主张。首先是我们对智能体的定义：**智能体是确定性的软件，它驾驭模型产生的非确定性结果以追求预期的目标。** 如果这听起来很像一个底座（harness）——甚至字面上就包含 harness 这个词——那是有意为之的。一个优秀的智能体就是一个优秀的底座。你几乎可以把智能体看作底座的一个实例。

<details>
<summary>Original English</summary>
And I am really excited to tell you about the standard agent specification. We are announcing it literally today as you are watching this. It is an open source spec. It's available today at standardagentspec.org, and I'd like to show it to you a little bit. To start with, we make some claims. First, this is our definition of agents. Agents are deterministic software that harness the non-deterministic results produced by models in pursuit of a desired objective. If that sounds a lot like a harness, it even has the word harness in it, it's intentional. A good agent is a good harness. You could almost think of an agent like an instance of a harness.
</details>

此外，该规范还建立在另外五个核心原则之上：
1. 智能体必须**与供应商无关（vendor agnostic）**；
2. 智能体应当**面向特定领域（domain-specific）**；
3. 智能体应当**与特定模型绑定（coupled to a given model）**；
4. 智能体应当**可组合（composable）**；
5. 智能体应当**可移植（portable）**。

我想讲一讲其中看起来相互矛盾的两点：“与供应商无关”和“与特定模型绑定”。“与供应商无关”意味着我不希望我的智能体只能跑在 Anthropic 的硬件上，或者只能跑在 OpenAI 的生态系统内。我需要能够把它托管在任何我想托管的地方，并能运行任何我需要运行的模型。

话虽如此，当单个智能体与特定模型配对时，效果往往是最好的。虽然在大模型层面上这可能没有那么绝对，但即便在大模型上这也是事实。不同的底座确实会产生不同的结果。

<details>
<summary>Original English</summary>
And then there are five other core principles that the spec is built on. First of all, agents need to be vendor agnostic. Agents should be domain-specific. Agents should be coupled to a given model. Agents should be composable, and agents should be portable. I want to talk about two of these that seem like they're contradictions. The vendor agnostic thing and the coupled to a model. Vendor agnostic means I don't want my agent running exclusively on Anthropic's hardware or exclusively within the OpenAI ecosystem. I need to be able to host it wherever I want to host it and I need to be able to run whatever models I need to run. That being said, an individual agent is almost always best when it's paired with a specific model. Now, this starts to be less true on the large model front, but even there it's true. Different harnesses do produce different results.
</details>

### 规范剖析：运行时、TypeScript、模型绑定与 Prompt

接下来让我带大家快速浏览一下这份规范。

首先是运行时。智能体在运行时中运行，非常类似于编程语言在运行时中运行。在这个体系里，编程语言是智能体的定义，而运行时则是规范中被极度详尽定义的部分。

但如果我们观察内部，会发现智能体实际上就是包含大量组件的包，这些都在规范中被事无巨细、极其详尽地阐述了。我们保留这张包含模型、系统提示词、工具、子智能体、智能体规则、钩子（hooks）、副作用（effects）以及线程（thread）的导图，稍后我们将逐一拆解。

<details>
<summary>Original English</summary>
So let me give you a little bit of a tour here of the specification. First, we have the runtime. An agent runs in a runtime very similar to how a language runs in a runtime. The language in this case is the definition of the agent and the runtime is what is so highly specified. But if we take a look inside, we'll see that agents are really just packages with lots of pieces and parts which are painfully and excruciatingly detailed in the specification. So we're going to keep this little map here of model, system prompt, tools, sub agents, agent rules, hooks, effects, and then the thread. All of that map and we're going to walk through some of these piece by piece.
</details>

首先，规范中的一切都被设计为**以代码形式编写**。这出于两个重要原因。第一，我们需要能够打包并分发它。我需要能够拿走一个智能体以及它所涵盖的一切信息，打包后直接拷进优盘交给你，或者发布到包注册中心。做到这一点的唯一途径就是所有东西都是代码。所以第一点，所有内容都必须是代码。其次，我们希望能够让智能体去编写智能体。我可不想坐下来手写智能体，那太疯狂了。因此，它当然必须是代码，这是一个智能体优先（agent-first）的生态系统。

<details>
<summary>Original English</summary>
So first of all, everything in the specification is intended to be written as code. Now, this is important for two reasons. One, we need to be able to pack this up and distribute it. I need to be able to take an agent and everything that that means, every piece of information that has to do with that agent. And I need to be able to pack it up, literally put it on a USB stick and hand it to you or publish it to a package registry. And the only way we're going to do that is if everything is code. So first, everything has to be code. Also, we want to be able to write agents with agents. I don't want to sit down and hand write an agent. That's crazy. So of course, it needs to be code so it is an agent first ecosystem.
</details>

我们来看看这些实际上是如何编写的。我们早期做出了一个非常有趣的决定：根据规范，所有的智能体都必须使用同一种语言编写。我们选择了 **TypeScript**。

我们选择 TypeScript 并不是因为我们是它的狂热粉丝，它还算不错。在当今时代，语言本身几乎没有价值，一种语言唯一的价值在于它最终产出的工件及其独特性。在我们看来，真正重要的语言其实只有两种——我知道有些人会反对——但这两者就是 Rust（或能写出极高性能代码的类 Rust 系统）和 TypeScript。为什么选 TypeScript？因为 TypeScript 可以在任何地方运行。它可以在边缘设备运行，在你的电脑上运行，在你妈妈的电脑上运行，在你的手机上运行，在任何地方运行。在这个具体场景中，我们希望智能体能在任何地方运行。但还有第二个原因：TypeScript 是一种解释型语言——严格来说 JavaScript 是解释型语言。我们之所以需要这点，是因为我们希望智能体能够编写智能体并立即执行，而无需构建或编译步骤。做到这一点的唯一途径就是使用解释型语言。在解释型语言中，TypeScript 在健壮性、速度、可用性和可移植性方面几乎胜过其他任何选择。

<details>
<summary>Original English</summary>
So let's take a look at how these are actually written. We made a really interesting decision early on. We decided that we needed to have all of the agents written according to the specification in the same language. And we chose TypeScript. Now, we didn't choose TypeScript because we're big TypeScript fans. It's fine. Uh, we chose TypeScript because in today's era, languages really almost have no value. The only value a language has is the artifact that it produces at the end. What's unique about it? And in our opinion, there's really only two languages that matter. I know some of you are going to disagree with this. But the two languages are Rust or Rust-like systems that write extremely fast performing code and TypeScript. Now, why TypeScript? TypeScript because it runs everywhere, absolutely everywhere. It runs on the edge, it runs on your computer, it runs on your mom's computer, it runs on your phone, it runs everywhere. And in this particular case, we want agents to run everywhere. But there is a second reason. TypeScript is an interpreted language. Well, technically JavaScript is. JavaScript is an interpreted language, and we want that because we want our agents to be able to write agents and execute them immediately without a build or a compilation step. And the only way we're going to do that is by using an interpreted language. And as far as interpreted languages go, TypeScript is about as robust, fast, available, and portable as any of them out there.
</details>

我们不想照搬 MCP 的做法，那已经存在了。MCP 需要你运行某种服务器来提供工具，我们不想这样，我们希望能够将所有内容打包在一起。这就是它的样子：如果你想定义一个模型，就在 TypeScript 中定义，全部都是强类型的。如果你想定义一个提示词，就使用 `definePrompt`。你想定义一个智能体，就使用 `defineAgent`。

<details>
<summary>Original English</summary>
We didn't want to do the MCP thing. That already exists. MCP requires you to have some sort of server in order to serve the tools. We don't want to do that. We want to be able to bundle it all together. So this is what it looks like. If you want to define a model, you do that in TypeScript. All of this is very tightly typed. If you want to define a prompt, you define the prompt using define prompt. You want to define an agent, you do it with define agent.
</details>

在代码中定义模型有一个非常重要的事实，那就是定义它运行的具体模型。我的智能体会运行在 OpenAI 的特定模型上，你也可以配置备用模型。如果主模型失败，我们建议提升一级智能水平并切换到另一个模型。这让我们能够利用 LLM 的“能力锯齿性”（jaggedness）。例如我们有个好玩的项目叫 Model Zen Garden，它会创建许多不同的 3D 禅宗花园供人游览。我们发现有一个特定的模型——腾讯的 Hunyuan 3D（10 cents Y three），在生成 3D 花园方面的表现极为出众，而成本只有其他模型的几分之一。它并不是一个非常全能的模型，但这就是锯齿性：它在某一个特征和能力上极为优秀。对于领域专用智能体而言，这其实是一种优势而非阻碍。能够将一个小型模型用于它极度擅长的小任务是非常棒的。而目前大家受到的训练往往是写完智能体后随意更换模型，然后碰运气祈祷好运。这违背了我们的基本原则之一——功效（efficacy）。我们需要高功效，因此将特定供应商的特定量化版本的特定模型精确绑定到你的智能体上，几乎总是更好的选择。

<details>
<summary>Original English</summary>
Now, one really important fact is that models, uh, models that are defined in code define the exact model that they are running on. So my agent is going to run on a specific model of OpenAI. And And you can have fallback models. if my primary model fails, then we recommend you go up a level of intelligence and switch to another one. This gives us a tremendous advantage that we can use the jaggedness of an LLM. So a good example is you know, we have this fun project called Model Zen Garden and Model Zen Garden creates lots of different 3D Zen Gardens for people to walk through. And what we found is one model in particular, 10 cents Y three was spectacular at producing 3D gardens at a fraction of the cost of all the others. It wasn't a very good model, but this is the jaggedness. It was good at that one characteristic in one trait. And for domain specific agents, that actually is a benefit, not a hindrance. So it's great to be able to use a smaller model for a small task that it's very very good at. And right now we've sort of all been trained that you write your agent and then you just swap out models willy nilly and you kind of hope for the best. That goes against one of our fundamental principles, which is efficacy. We need high efficacy. And so it is almost always better to pin a very specific model running at a specific quant by a specific provider to your agent.
</details>

接下来是提示词（prompts）。提示词就像字面意思一样，是系统提示词，但有趣的是，它们拥有对话的其中一方。对于智能体来说，对话基本上都是双向的：有助手（assistant）和用户（user）。在规范中，提示词拥有对话的其中一方。

另一件有趣的事是，你可以在提示词内部包含其他提示词，它们实际上是在运行时渲染的。因此，如果你有公开的环境变量之类的内容想要在运行时写入提示词，这完全可行。或者你可能有一个基调提示词（tone prompt），而你拥有许多不同的子智能体，所有这些子智能体都需要以特定的方式与用户交谈，这完全没问题，你只需在所有子智能体中包含一个写着“你要以这种方式交流”的单独提示词即可。

<details>
<summary>Original English</summary>
Next are prompts. Prompts are what they sound like. These are the system prompts, but interestingly, they own one side of the conversation. So conversations for agents are basically always two-sided. You have the assistant and you have the user. And in this case, the prompt is owning one side of that conversation. And another interesting thing you can do is you can include prompts inside of other prompts. They are effectively rendered at runtime. So if you have environment variables that are public or things like that that you want to get written into the prompt at runtime, that is completely possible. Or perhaps you have something like a tone prompt where you have got lots of different sub agents and all those sub agents need to speak to users in a particular way. That's not a problem. You can just make that happen by including a singular prompt in all of them that says, hey, you're going to speak this way.
</details>

### 工具、交互模式与子智能体机制

工具基本分为三类：
1. **函数（function）**：实际运行某段 TypeScript 代码；
2. **提示词（prompt）**：当你在其他地方需要少量推理时非常有用。比如我只需要调用 Nano Banana 生成一张图片，但不需要为此配置一个完整的子智能体；或者某个模型在模仿人类语气上比我的主模型更好，那么我的工具之一实际上就是一个子提示词，而非子智能体；
3. **完整的智能体（entire agent）**：也就是一个完整的子智能体。我可以把一个智能体当作工具来调用，它就能直接运作。这都是规范的一部分。

<details>
<summary>Original English</summary>
Now tools are basically one of three kinds. You either have a function where you actually run some code in TypeScript, or it's a prompt. So this is really useful when you need to perform a little bit of inference somewhere else. Like I need to just use Nano Banana to produce an image, but I don't need a full sub agent to do that. Um or this one model is actually better than my primary model at sounding like a human. So one of my tools is actually a prompt. It's just a sub prompt, not a sub agent. And then the third type of tool is an entire agent, a whole sub agent. So I can call an agent as a tool and it will just work. This is all part of the specification.
</details>

记住我之前说过的，在 AI 中所有的对话都有 A 面和 B 面两端。根据规范，你可以通过多种不同方式来混合匹配它们。我们最熟悉的是提示词与人类对话，换句话说就是 AI 与人类交流，就像 ChatGPT 那样。

但你也可以让两个 AI 互相交谈，其中 A 面和 B 面都是 AI。A 面以为自己在和人类说话，B 面也以为自己在和人类说话，它们共同执行操作。这作为内置的评测（eval）和质量保障（QA）效果极佳。比如我让 A 面生成某种素材，它生成了一张图片，但上面有水印，A 面觉得看起来很棒，于是传给 B 面；B 面看了之后说：“嘿，上面有水印，你在搞什么？”A 面回答：“天哪，实在抱歉，你说得对”，然后重新生成。这种模式在内置评测、QA 和反思方面表现非常出色。

<details>
<summary>Original English</summary>
Now remember I said that all conversations in AI have two sides, side A and side B. And there's a bunch of different ways according to the spec that you can mix and match these. The one where the most familiar with is a prompt speaking to a human. In other words, you have an AI talking to a human. This is like ChatGPT. But you can also have two AIs speaking to each other where side A and side B are actually both AI. And side A is you know writing thinking it's speaking to a human. And side B is writing thinking it's speaking to a human and they're both performing the operation together. Now this works wonderfully as built-in eval, built-in QA. I ask, you know, side A to to generate some kind of asset. It produces an image, let's say, and and there's a watermark on it. It thinks it looks great. So it passes it to side B. Side B looks at that and says, hey, there's a watermark on there. What are you doing? Side A says, oh my goodness, I'm so sorry about that. You're absolutely right. And then it regenerates it. So those work really great for built-in uh eval and QA and reflection.
</details>

然后我们有处理程序（handler）。处理程序基本上就是代码。最简单的形式比如一段代码在某一端运行，只输出“continue”：你输入内容，它回复“continue”；你再输入，它依然回复“continue”。所以在那类场景下，你完全可以创建一个完全没有 AI 参与的智能体，由确定性的代码与人类对话，在我们的规范里这是完全允许的。

最后，你还可以让提示词和人类互相交流，其中一方实际上是一个子智能体。这听起来可能有点绕，但请放心，你的编程智能体会搞清楚你何时需要使用这些。

<details>
<summary>Original English</summary>
And then we have a handler. A handler is basically just code. So the simplest form you could imagine, a piece of code runs on one side that just says continue. And you type something to it and it says continue. You type something says continue. So in that case, you could actually create an agent with no AI involved at all where you have deterministic code speaking to a human. That's fine within our spec. And then uh ultimately you could have an a prompt and a human talking to each other where one of them is actually a sub-agent. This gets a little bit confusing, but rest assured, your coding agent will figure out when you need to use these.
</details>

关于处理程序，这里有一个示例。在这个具体案例中，处理程序确定性地回复人类甚至回复 AI。在这个例子里，我们有两个智能体在互相交谈，拥有 A 面和 B 面。这里可以看到我们在定义每一侧拥有的提示词：我们有素材制作端（asset worker）和素材审核端（asset reviewer）。

<details>
<summary>Original English</summary>
So handlers, here's an example of a handler. In this particular case, the handler is speaking deterministically back to a human or even to an AI. In this case, we have two agents speaking to each other. So you have a side A and a side B. And here you can see that we're defining which prompt each side has. So we have the asset worker and then the asset reviewer side of the conversation.
</details>

子智能体名副其实，它们是拥有各自 A 面和 B 面的完整智能体。在示例中可以看到我们定义了一个日历智能体，这里存在同一个智能体的两个实例：一个是工作日历，一个是个人日历，但底层由同一个智能体及相同的提示词支撑。

规范中一个非常引人入胜的概念是**父级钩子（parent hooks）**。它们允许将子智能体安装到父级之下。一旦安装，它们会自动暴露并修改父级的钩子。这使得组合无需额外配置，也不用在父级提示词里专门交代“顺便说一下，你有一个能做某事的子提示词”——完全不需要。例如仅仅安装 Gmail 智能体，就能自动让父级知晓如何使用它。

<details>
<summary>Original English</summary>
Now sub-agents, sub-agents are exactly what they sound like. They are entire agents with their own side A and side B. And here you can see that we have the calendar agent. And in this case, we have two instances of the same agent. A one is a work calendar and one is personal calendar, but ultimately they have the same agent backing both of them, the same prompt, the calendar agent. Now parent hooks are a fascinating concept in the specification. They allow a child sub-agent to get installed under a parent. And when they get installed, they automatically expose and modify the hooks of the parent. This allows a composition without having to do any additional configuration or telling the parent prompt, hey, by the way, you have this sub-prompt that does something. No, not necessary. Just installing the Gmail agent, for example, automatically can let the parent know how to use it.
</details>

钩子正如其字面意思，属于确定性事件，例如 `filter_messages`、`before_tool_call`、`after_update_message` 等，它们在智能体运行生命周期的特定时刻执行，规范中对这些都有统一定义。副作用（effects）本质上是计划执行的代码。你编写一段需要在未来某个时间点运行的代码块。这可以很简单，比如一个闹钟：你可以为闹钟定义一个 effect，或者定义一个发送邮件的 effect。定义好之后，你可以调度它在其他时间执行。通常你会在工具调用内部调度该副作用。比如在工具调用中安排某个副作用在未来触发。这就好比我对 Grokbot 说：“千万别让我忘了明天孩子有钢琴独奏会。”没问题，它会设置某种提醒来触发。在规范中，工具正是通过这种方式实现该功能的：先定义一个副作用，随后调度它在未来执行。

<details>
<summary>Original English</summary>
Now hooks are what they sound like. They are deterministic events, stuff like filter messages before tool call, after update message that run at very specific moments in time throughout the lifecycle of the agent running. And these are all defined in the specification. Effects are basically scheduled code. You write a chunk of code that needs to occur at some other point. This could be something simple like an alarm clock. You could have a define effect for an alarm clock or you could define an effect to uh send an email. And when you define this effect, you can then schedule it to occur at some other time. Obviously, you are often going to schedule the effect inside of a tool call. So you could have a tool call that schedules an effect to happen at some point in the future. This is effectively like if I'm talking to Grokbot and I say, hey, please, you know, don't don't let me forget my my kid's piano recital tomorrow. Okay, great. No problem. It's going to then set some sort of a reminder to to trigger. This is how a a tool would be able to do something like that within the specification. You have an effect that you define and then later you schedule it to occur at some point in the future.
</details>

### 线程模型、代码执行沙箱与运行时契约

根据规范，每个线程（thread）都是一个完整的小环境。你可以把每个线程看作一个小沙箱。它拥有并存储自己的消息历史及相关的一切、自己的工具、自己的子智能体、独立的键值存储（KV store）和文件系统。如果你赋予它权限，它甚至能够编写自己的代码并运行。

我们来看看线程的具体特性。首先是代码执行。在这里你可以看到我可以编写一些文本代码，智能体写完后存入刚刚提到的文件系统，随后读取并运行它。你可以精确指定它能访问的内容，甚至可以规定在运行时禁止访问互联网，这都在规范之内。相反，你显式指定允许导入和使用的内容。通过这种方式，智能体在其自身的生态系统内获得了巨大的操作自由度。你也可以编写智能体来使用代码模式（code mode）。规范对此类实现持非常不预设立场的态度，但我个人在使用 Standard Agent 规范时一直都在使用代码模式。

<details>
<summary>Original English</summary>
Now, every thread according to the specification is a full little environment. You can think about each one like a little sandbox. It has its own messages and and everything to do with its messages stored there. All of its own tools are stored there. Its sub agents are stored there. It has its own KV store. It has its own file system. It even has an ability to write its own code and then run that code if you choose to give it the ability to do that, of course. So let's take a little bit of a look at threads. First, there's code execution. Here you can see I can write some code. It can be just a text code. My agent can write some code, store it to the file system that I just told you exists, and then it could read that code and run it. And then you specify exactly what it has access to. You can even say you don't have access to the internet when you run it. That is all part of the specification. Instead, you say these are the things that you can import. These are the things that are allowed. And by doing this, you can allow agents to have tremendous latitude to operate within their own ecosystem. You could also write uh an agent to use code mode. The spec is very unopinionated about things like that, but personally, I use code mode all the time with the standard agent specification by doing this.
</details>

线程还可以使用决策模型。在这个案例中，我们使用 Type Safe AI 的 Jev 来判断客户当前是开心还是沮丧，情绪状态如何，是否需要转接人工。这是线程执行时运行时的一部分。

线程还可以暴露端点。这是规范的一部分，虽然非强制，但智能体应当具备暴露自身端点的能力。这能让你打造完全开源的类 Grokbot 系统，托管在自己的服务上，并对外暴露 OAuth 端点或托管 API，从而构建类似 Claude Artifacts 的功能。

此外，智能体必须是可打包的。理念在于你可以将它们打包成类似甚至就是真正的 NPM 包，发布之后任何人都可以安装、加载，并且开箱即用。

<details>
<summary>Original English</summary>
Threads can also use decision models. In this case, we're using Type Safe AI's Jev to determine if the customer is being, you know, is happy or is upset. What's their sentiment right now? Do we need to escalate this to a human? That is part of the runtime in the thread execution. Threads can also expose endpoints. This is part of the specification. It doesn't have to, but a given agent should have the ability to expose its own endpoints. This would allow you to create something like Grok bot that's completely open source where you can host it on your own service and it would expose its own OAuth endpoints, for example, or host its own API so you could create something uh like Claude artifacts. And then agents must be able to be packed. The idea is you can pack these down into something like an NPM package or literally an NPM package, publish it, and anyone can install it, anyone can load it, and it just works.
</details>

运行时正是让它开箱即用的魔法所在。一旦智能体置于运行时中，规范中就有明确的运行规则。规范本身非常中立，绝不规定具体的实现方式，而是规定如何处理不同的运行时状态。比如：如何处理智能体的一个单步执行？如何在运行代码时保障安全？如何存储文件？例如规范中有一个基本的 `threadstate.readFile`，它没有规定具体该如何读取文件。在我们的实际实现中，我们将此托管在 Cloudflare 的 Durable Objects 上，并将 `readFile` 实现为读取数据库。底层实际上并没有文件系统，但线程感知到的是一个文件系统的存在。这些都是极其关键的运行时契约的一部分。

<details>
<summary>Original English</summary>
The runtime is the magic behind it just working, of course. Once you have an agent in a runtime, there are explicit rules in the specification for how it needs to run. Now, everything is really unopinionated and it never says what kinds of implementations you need to have. What it says is how you handle the different runtime states. Like, how do you handle a step of the agent, right? How do you enforce safety across uh your run code? How do you how do you store files? So, for example, there is a a basically a threadstate.read file. Well, it doesn't say how the file should be read. In our case, we actually host this on Cloudflare in durable objects and we implement read file as reading to a database. There actually is no file system, but the thread sees there being a file system there. That is all part of the runtime contract that is really, really critical.
</details>

### Standard Agent Builder 演示：5 分钟生成保修索赔智能体

归根结底，你几乎可以构建你能想到的任何智能体系统。你可以构建极小的智能体，也可以构建完整的代码编写智能体。我们在不久前就这么做过：构建了一个完整的编码智能体，由许多协同工作的小型子智能体组成，效果非常好。更妙的是，因为它们全都是标准智能体，我们可以直接安装生态中已有的其他标准智能体，像添加技能一样添加到我们的编码智能体中，而且它们是具备自身执行能力的完整智能体。

但我还想谈一件事：我们今天还将发布 **Standard Agent Builder**。这是 Standard Agent 规范的首个公共运行时。我们已经在生产环境中实际使用了一段时间，表现非常优异。大家今天就可以把它克隆到本地机器上开始使用。然后你只需要让你的编程智能体为你创建一个新智能体，它会非常清楚该怎么做。它知道不需要重复发明底座的每个部件，而是清楚地知道如何确定性地定义需要存在的各个组件。之后你可以在任何地方运行它：可以在本地免费运行；如果你想推向生产环境，也可以推送到我们提供的云端。但再次强调，这是一份开放规范。你完全可以让你的编程智能体查阅该规范，直接说“为这个规范给我写一个运行时”。我们甚至会在规范官网上托管并链接你的运行时，因为我们真心希望这是一个开放的生态系统。

<details>
<summary>Original English</summary>
So, in the end, you can build almost any agent system you can think of. You could build really small ones or you could build entire coding agents. So, we actually did this a while ago. We built a full coding agent made up of lots of individual tiny little sub agents that were all working together. And it worked great. And what was awesome about it is because they were all standard agents, we could go and install another standard agent that was out in the ecosystem and just add them to our coding agent like you would add skills, except these are full agents with their own ability to perform execution. But there's one more thing I want to talk about. We're also releasing standard agent builder. This is the first public runtime for the standard agent specification. We have already been using this in production for some time, and it's working great. You can clone this literally today onto your machines and start using it. Then you just ask your coding agent to create some new agent for you, and it will know exactly how to do that. It knows it does not need to reinvent every part of the harness, but it knows exactly how to define deterministically the pieces and parts that need to be there. And then you can run it anywhere. You can run it for free locally, and if you push it, we have a cloud you can push it to if you want to put it in production. But again, it's an open specification. You can just point your coding agent at the spec and say, build me a runtime for this specification. We will even host and put links on the spec site to your runtime because we really do want this to be an open ecosystem.
</details>

好，说了这么多，我想做一点现场演示。

今天早些时候，我让 Claude Code 创建了一个电池保修索赔智能体，这与我们之前讲的暖通空调例子非常类似。我给了它一份描述完整业务流程的 PDF。我现在把过程快进，大家就不用干坐着看 Opus 工作了。它正在阅读那份 PDF 中定义的各项流程细节，接着它将编写特定工具并定义特定模型以完成该任务，并用代码将它们实现出来。在此过程中，它清楚底层架构已经解决好了，所以它的构建速度会比大家通常见到的快得多。

可以看到，现在切回到实时速度。快进结束，它提示已经构建完成了。按实际耗时算，生成这个智能体一共花了 5 分 21 秒。我想给大家展示一下它在 5 分 21 秒内到底生成了什么。

<details>
<summary>Original English</summary>
Okay, with all that, I want to do a little bit of demo time. So earlier today, I had Claude code create a battery warranty claim. So this is very similar to the HVAC example that we were doing. I gave it a full PDF of the process that it needed to go through. Now I'm fast-forwarding this so that way you guys don't have to sit here and watch while Opus does its work. But right now, it is reading um everything that that PDF defines as part of its process. Then it's going to write specific tools and define specific models in order to fulfill that specific task. And then it's going to write those in code. And while it's doing this, it knows that it the architecture is already solved for it, so it can do this way, way, way faster than you're traditionally used to. Um so you can see here this is in real time now. So we fast forwarded. It's now telling me it's done. Okay, so in real time it took 5 minutes and 21 seconds in order to produce this agent. And I want to show you what it actually made in 5 minutes and 21 seconds.
</details>

这是文件系统。你可以看到它生成了这些文件：电池保修智能体，包含提示词，以及特定的工具，比如检查电池、上报给主管。这里可以看到智能体本身的代码结构。A 面是提示词，B 面是人类。

这是它编写的具体提示词。这是模型定义：它创建了一个名为 `warranty` 的模型，使用的是 DeepSeek V 4.1 Flash。

这里展示的是它为了完成工作所创建的工具，包括以旧换新评估（offer trade in）、检查电池（check battery）、报告安全隐患（report safety issue）。所有这些工具都是专门针对该流程明确设立的专用工具，不是随意用来打听时事政治的工具，它们只能执行被分配的任务。

<details>
<summary>Original English</summary>
So this is the file system. Here you can see it created these files. So battery warranty agent with prompts and then specific tools, check battery, escalate to lead. And here you can see what the agent itself looks like. Now this is a side A is a prompt and side B is a human. Here's the actual prompt that it wrote. Here is the model. So it created a model called warranty, which is DeepSeek V 4.1 Flash. And in this case it's also showing the here we're looking at the tools that it created in order to do its job. Stuff like offer trade in, check battery, report safety issue. All of those tools are explicit tools just for that process. They are not tools that were created in any which way to go check on the latest, you know, politics or anything like that. These can only do the work that they've been assigned.
</details>

现在来看它在 Agent Builder 中的运行状态。我们看到了电池保修智能体，以及所有的交互线程，这是管理后台视图。

你可以在这里直接与它交互，尽管大部分最终用户不会在这里使用它。你可以获得所有发生事项的极其详尽的细节：可以看到所有被调用的工具、具体模型、具体成本、发送的 Token 数量，以及缓存命中率——本例中达到了 94%。我们可以看到发送给它的候选工具，这里提供了 6 个工具供它选择，而在我们的具体案例中它挑选了其中一个执行。你还可以查看完整的请求体，包含实际发送给 LLM 的每一个微小细节，这在构建工具时极具价值。最后可以看到它调用了补发货工具（ship replacement）。

<details>
<summary>Original English</summary>
Now here it is inside of agent builder. We have our actual battery warranty and then we can see all of the threads. And this is like the admin view into your agent. Now you can actually interact with it directly here, although most of your users are not going to be using the agent here. You get incredible detail on everything that happened. So we can see all of the tools that were called. We can see exactly the models, exactly the cost, how many tokens were sent, what our cash rate hit was, 94% in this case. We can see the tools that we sent. So in this case we sent these six tools for it to choose from. And you know, in in our particular case it chose one of those tools to call. You can also see the full request body, every little detail about what was actually sent to the LLM. This is super valuable for when you're building out your tool. And then ultimately we can see that it called the ship replacement tool.
</details>

最后，用户与该智能体的交互方式是多样的。在这个例子中，我们在网站上挂了一个小型聊天机器人。这就是后台实际运作的智能体，因为 HTTP API 和 WebSocket API 都是规范的一部分，都必须对外暴露。因此大家可以看到，我们可以非常轻松地构建一个具备该能力的在线支持机器人。而且由于符合标准，我们同样可以将这个智能体作为 MCP 服务器暴露出去。如果有人使用 ChatGPT 或类似工具访问我们的网站，他们的智能体就能自动与我们的智能体对话。这就是目前已经发布并可用的 Standard Agent Builder 的简要预览。

<details>
<summary>Original English</summary>
And then finally the way your users are actually going to interact with this is manifold. In this case we put a little chatbot on a website. Now, this is the actual agent behind the scenes because an HTTP API and a WebSocket API are both part of the specification. They both need to be exposed. So here we can see that we could very easily build an online support bot that is able to do this. But again, we could expose the same agent because it's a standard as an MCP server. So if somebody is using our website with ChatGPT or something like that, they could automatically have their agent talk to our agent. So that is a little brief preview of how the standard agent builder works that's out and available right now.
</details>

### 早期 Web 隐喻与生态共建号召

我知道刚才讲的内容非常多，信息量很大，但我希望大家能从中有所收获。我们非常期待看到大家开始构建运行时。如果你想构建运行时，可以用任何你喜欢的语言来写，只要它能执行规范中的 TypeScript 即可。你可以用 Rust 构建运行时，可以用 Go 构建，可以用任何你想要的语言构建。只要符合规范，运行时实现完全开放。

接下来就可以开始构建智能体了。我非常期待看到领域专用智能体生态的涌现。无论你想构建什么，我们都乐见其成。

欢迎大家来找找规范的破绽。我们绝不是带着最终成品而来的，我们正在寻找能够共同推动该规范发展的人。这让我想起了 Web 的早期时代，那时每个浏览器都在力推自己的专属特性：“嘿，你应该用 Mozilla，因为我们搞出了一个别人都没有的叫 JavaScript 的疯狂新玩意儿。”我们现在的处境与那时颇为相似。当年正是一群充满激情的规范爱好者让规范最终属于整个世界、属于整个生态，并真正推动了 Web 的向前发展。我们希望现在的智能体领域也能发生同样的事情。所以我希望大家能对参与这段旅程感到兴奋。

现在就启动你的编程智能体吧。启动它，给它添加技能，今天就开始编写新东西。

非常感谢大家。你可以在 X 上关注我，也可以访问 standard-agentspec.org 了解更多详情。所有这些都已经向你开放，我迫不及待想看到你们构建出的成果了。

<details>
<summary>Original English</summary>
So I know that was a lot. It was a lot of information, but I hope you were able to get something from that. We are really excited to see people start building runtimes. If you would like to build a runtime, build it in whatever language you want as long as it can execute the TypeScript that's in the spec. You could build the runtime in Rust, you could build it in Go, you could build in whatever language you want. The runtime is totally up for grabs as long as it complies with the spec. Then start building some agents. I'm super excited to see an ecosystem of domain-specific agents emerge. Whatever you want to build, we would love to see it. And then try breaking the spec a little bit. We are by no means coming with a finished solution. We're looking for people to help push the spec forward. This very much reminds me of the early days of the web, right? When each browser was trying to push its own features. Hey, you should use Mozilla because we have this crazy new thing called JavaScript or something like that that nobody else has. That's a little bit like the world we're in right now. And it took a ragtag group of spec enthusiasts [clears throat] to get a spec that was owned by the entire world, by the entire ecosystem, and really push the web forward. We want the same thing to happen right now with agents. So I hope that some people out there would be excited to help us on that journey. And then start your coding agent. Boot it up, add a skill to it, and start writing new stuff today. Okay, thank you very much. You can follow me on X. You can go to standard-agentspec.org to hear more. All of this is available to you and I cannot wait to see what you all build.
</details>