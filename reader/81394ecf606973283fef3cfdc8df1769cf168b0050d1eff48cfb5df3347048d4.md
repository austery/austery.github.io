---
author: AI Engineer
date: '2026-10-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=7T-gldvgfpo
speaker: AI Engineer
tags:
  - declarative-programming
  - prompt-engineering
  - multi-agent-system
  - workflow-automation
title: OpenProse声明式契约与多智能体工作流设计
summary: 文章探讨了从传统提示词与上下文工程向声明式契约编写的演进。创作者介绍了以Markdown为基础的语言与框架OpenProse，主张通过组合式、声明式契约定义目标状态而非过程，由底层测试框架与子智能体执行工作流。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - OpenProse
media_books: []
status: evergreen
---
<!-- chunk 1/6 -->

[音乐]

<details><summary>Original English</summary>
[music]
</details>

>> 我叫 Dan。我是 Open Pros 的创造者。这位是 Raymond，跟我一起的还有 Raymond 和 Jose，两位非常出色的队友、同事，总的来说就是极其优秀的创作者和工程师。稍后我会再多介绍他们一点。关于我们在这里即将向大家展示的内容，先介绍一点点背景。

<details><summary>Original English</summary>
>> My name is Dan. I am the creator of Open Pros. This year is Raymond I'm joined by Raymond and Jose two fabulous teammates, co-workers, just phenomenal creators and engineers all around. I'll introduce them a little bit in a bit. Uh just a little bit of background about what we're what we're about to show you here.
</details>

5 年前的 2021 年 4 月，我被评为 EleutherAI 密室 Discord 中最好的提示词编写者（prompter）。在当时，我认为这项技能在之后的许多年里都会具有极高的价值，而实际上，我认为它的寿命大概也就持续了两三年左右。我这么说是因为显然大家都知道，在过去的 5 年里发生了很多变化。

<details><summary>Original English</summary>
Uh 5 years ago in April of 2021, I was named the best prompter in the Eleuther AI back rooms Discord, which was a skill at the time that I thought would be tremendously valuable for many years afterward and actually it lasted I think around like two or three years maybe was the lifetime of of that skill. And I say that because a lot obviously, as you all know, has changed in the last 5 years.
</details>

但有一件事没有变。我今天参加了很多工作坊，接下来我们还有很多精彩的演讲。但在我们所做的所有工作中，似乎始终存在且实际上并没有随着最新的测试框架（harness）或最新的模型而改变的一件事，就是我们仍然都需要向那个东西传达我们的意图。无论那个东西变得多么聪明，仍然存在这样的挑战：我该如何把自己想要的东西从脑海中表达出来，并输入到这个即将接管一切、为我做好所有事情的超级智能中去？

<details><summary>Original English</summary>
But one thing has not changed and I've been to a lot of workshops today. We've got a lot of amazing talks coming up. But the one thing that seems to be ever present in in all of the work that we do and and that actually doesn't change with the latest harness or the latest model is we all still need to communicate our intent to the thing and no matter how smart the thing gets, there is still this challenge of how do I get out of my brain the thing that I want and and get it into the super intelligence that is just going to carry it away and and do everything for me.
</details>

Open Pros 是一种语言，也是一个框架，它最初是一个基于我自己对语言的热爱、以及我自己对语言是一种真正强大的创造力量的坚定信念而发起的项目。我的意思是，我知道这有点陈词滥调，但以我们现在的能力而言，这确实是字面意义上的。你可以写下一句话，而这些东西就会让那句话成真。所以接下来的问题就变成了：现在既然你拥有了如此强大的机器来让它成真，你所写下的句子又该是什么？

<details><summary>Original English</summary>
Uh Open Pros is is a is a language, it's a framework, it's a started as a project based on my own love of language and my own strong belief that language is this really powerful force of creation and I mean that like I know that's a little bit cliche, but that's like in the very literal sense now with with the capabilities that we have. You can write a sentence and the things just make that sentence true. And so the question then becomes like what is the sentence that you write now that you have this tremendously powerful machine to make it true.
</details>

5 年前编写提示词的技能，与我们今天所认为的契约创建或契约组合的技能看起来截然不同。当你面对一个仅仅是在补全下一个 token 的模型时，提示词有好的模式，也有坏的模式。

<details><summary>Original English</summary>
And the skill of prompting from 5 years ago looks very different from the skill of what we like to think of as contract creation or contract composition today. And when you were dealing with a model that was just completing the the next token, there was there was good patterns and bad patterns for for prompting.
</details>

几年后，你开始手动填充上下文，获取 RAG 结果、工具调用等等以及搜索结果，并将它们塞进上下文窗口中，你称之为上下文工程。

<details><summary>Original English</summary>
A few years later, you were filling out context by hand and you were taking rag results and and tool calls and stuff and search results and stuffing them into into the context window and you call that context engineering.
</details>

然后 harness 开始为你做这件事，你开始构建一个 harness，并且你把 harness 视为为你填充上下文的这种机器。

<details><summary>Original English</summary>
And then the harness started doing that for you and you were building a harness and and and you were you were you thought of the harness as this this machine that was stuffing context for you.
</details>

而在过去的 8 到 10 个月里，我们看到涌现了许多论文，直接将所有内容又向上推了一层抽象，harness 本身也在你们脚下发生改变。我们今天早上看到了 Anthropic 关于 flow 的精彩演讲，那就是这种自我修改 harness 拓扑的想法，它以一种甚至就在一年前都无法想象的方式管理子智能体（sub agents）。所以，如果解决了，上下文现在解决了，harness 现在也解决了，那么这里的下一步会是什么？这就是我们今天想稍微谈一谈的内容，并向大家展示一些我们为此所构建的东西。

<details><summary>Original English</summary>
And and in the last 8 10 months, we've seen a number of papers come out that is just pushing everything up another layer of abstraction and and the harnesses themselves are are changing out from under you. We saw a great presentation by Anthropic this morning on on flows and that's this idea of this like self-modifying harness topology that is managing sub agents in a way that just was not thinkable even just a year ago. So, if if is solved and the context is now solved and now the harnesses are now solved, like what's kind of the next step here? And that's what we'd like to talk a little bit about today and show you some of the stuff we've been we've been building in in support of that.
</details>

我喜欢这样来看待它：一旦你能说出你想要的东西的名字，任何 harness 都可以自我塑形、展开扇出、执行任何类型的循环来带你达成目标。问题是，为你说想要的东西命名，有哪些好的最佳实践。

<details><summary>Original English</summary>
I like to think of it as as once you can name the thing that you want, any harness can self-shape, can fan out, do any sort of loop to get you there. And the question is what are the good best practices for naming the thing that you want.
</details>

我们认为这是声明式的。我们将借鉴经典软件工程的概念。我做软件工程师有 12 年了。Jose 和 Raymond 在这方面也很有经验。Jose 曾是早期 Google Cloud 的成员，他启发了我们思考这个问题的许多方式。Raymond 也是一位极其出色的人——他让我把他介绍为一位非凡的氛围编码员（vibe code extraordinaire），但这大大低估了他的才华。他是一位博士，两次创业的创始人，从事 harness 工程的时间基本上和我认识的任何人一样长。所以，这就是借鉴旧的工程模式并将其应用到这个新世界中的理念。

<details><summary>Original English</summary>
And and we think of that as as declarative. We're we're going to borrow concepts from classical software engineering. I'm a software engineer of 12 years. Jose and Raymond have been around the block with this as well. Jose was early Google Cloud and he's informed a number of the ways we think about this. Raymond is just a phenomenal uh uh He told me to He told me to introduce himself as a as a vibe code extraordinaire, but that's way underselling his his talents. He's a PhD and two-time founder and has been doing harness engineering for basically as long as anybody I know. Um and and so so it's this idea of borrowing old engineering patterns and applying them into this new world.
</details>

我们希望以组合式的方式来写提示词。我们要组合，组合优于继承。我们希望以声明式而非过程式或命令式的方式来写提示词。我们想告诉它做什么，而不是怎么做，因为 harness 凭其无限的智慧和无限的智能会搞清楚这一点。如果我们告诉它如何去做这件事，现在我们实际上在成本和智能方面留下了损失，因为我们本可以用更便宜的模型来运行它。更智能的模型可以弄清楚如何去做这件事。所以这就是写下你想要什么的理念：声明你想要什么、结果、目标、最终状态。我们将其视为一份契约。

<details><summary>Original English</summary>
We want to write our prompts compositionally. We want to compose composition over inheritance. We want to write our prompts declaratively rather than procedurally or imperatively. We want to tell it what what to do, not how to do it because the harness in its infinite wisdom and its infinite intelligence is going to figure that out. And if we tell it how to do the thing, now we're actually leaving cost and and intelligence on the table because we could run it for a cheaper model. A more intelligent model can figure out how to do the thing. So it's this idea of write what you want, declare what you want, the outcome, the goal, the end state. We think of that as a contract.
</details>

并且以一种能够让你组合它们的方式去写，因为当你构建一个系统时，当你构建一个像这样开放的框架时，当你构建一个包含许多部分的系统时（可能跨越你的公司或跨越你的团队），你希望以一种允许事物优雅地组合的方式来做事，从而让你能够以更加局部的方式来管理复杂性。

<details><summary>Original English</summary>
And and write it in a way such that you can compose these because when you build a system, when when you build an open framework like this, when you build a system that has many parts, maybe across your company or across your team, you want to do things in a way that allows things to elegantly compose and that lets you manage complexity in in a in a more local way.
</details>

说到这里，我要把麦克风交给 Raymond，他会向大家稍微讲讲它是如何工作的，之后我们会给大家展示一些演示。整个过程中我们都会开放提问。所以，如果您有疑问，请务必举手，随时插话。

<details><summary>Original English</summary>
Um with that, I'm going to hand it over to Raymond who's going to tell you a little bit about how it works and then we're going to show you some some demos after that. We'll we'll we'll open it up to questions throughout. So, and please do raise uh your hand if you have questions, interject, please.
</details>

### Open Prose 的核心概念与适用场景

>> 太棒了。谢谢你，Dan。好的，我想先帮大家理解 Open Pros，并把它归入一个象限中。

<details><summary>Original English</summary>
>> Awesome. Thank you, Dan. Okay, so there um I wanted to just help you understand Open Pros and put it in a quadrant. Um
</details>

如果你只能记住两件事，我希望你能记住的两件事是：它纯粹就是 Markdown。我们有时喜欢称它为智能体的编程语言，有时称它为一个框架，但它全都是纯文本。它就是一个巨大的提示词。第二件帮助你在脑海中理清它属于哪个分类的事就是，它是事件驱动的。它不是聊天。我们不是在和这些东西聊天。

<details><summary>Original English</summary>
so, if there's only two things that you remember, the two things that I want you to remember are it's just markdown. So, we like to sometimes call it it's a programming language for agents. We sometimes call it a framework, but all of it is just text. It's just one giant prompt. Um and then the second thing to just help you figure out in your mental bucket where this fits is it's event driven. It's not chat. We're not chatting with these things. Um
</details>

我稍后会与一个能够编写 Open Pros 程序的智能体聊天，但如果你只记住关于我们的两件事，那就是这些：它全都是文本，并且我们正在做的是这些事件驱动的多智能体工作流，而不是聊天。它是开源的，你可以通过 NPX skills 在本地运行它。

<details><summary>Original English</summary>
I'll chat with an agent that will make Open Pros programs later, but if you only remember two things about us, that's it. It's it's all text and we're doing these event-driven multi-agent workflows, not chatting. Um you can it's open source, you can run it locally with NPX skills.
</details>

稍后我将演示我构建的托管版本 run.pros.md，并且我们也可以为您提供支持。如果您想与我们联系，我们会为您提供帮助。

<details><summary>Original English</summary>
Uh I'll walk through the hosted version that I've built uh run.pros.md, and uh we also will do it for you. If you want to reach out, uh we'll help you out.
</details>

那么，我想快速问一下，这里有多少人是从事金融领域的？好的，挺好。有多少人是 AI 工程师或开发者？好的。那么有多少人可能是偏向产品经理（PM）或者专业人士，你们在使用 AI 但不会写代码？好的，人数少一些，不过好的。

<details><summary>Original English</summary>
So, uh I guess quick question, like how many people in here are from the the finance side of things? Okay, that's good. How many are like AI engineers or developers? Okay. Then how many people um are maybe more like PMs or like professionals but and you're using AI but you don't know how to code? Okay, fewer but Okay, good.
</details>

那么，对于这三类受众，我为什么应该关心这个呢？

<details><summary>Original English</summary>
So, I've got why should I care for those three audiences?
</details>

对于受强监管的行业，我们看到一些银行和其他金融服务公司感到兴奋的事情之一，就是正如我之前所说的，它全都是文本。因此，我们不需要采购部门，我们也不需要 IT 部门。你可以使用你想要的任何编码智能体、任何你想要的推理、任何你现有的安全护栏、任何你现有的技术栈，我们实际上可以帮你创建这些多智能体工作流，而无需向你部署除了几个 Markdown 文件之外的任何东西。所以，这是它作为纯文本的一个角度或优势。

<details><summary>Original English</summary>
So, for the small regulated industries, one of the things that we've seen um some banks and uh other financial services companies be excited about is like what I said before, it's all text. So, we don't need the procurement department, we don't need the IT department. You can use whatever coding agent you want, whatever inference you want, whatever guardrails you already have, whatever stack you have, we can actually like help you um you know, create these multi-agent workflows without deploying anything to you other than some markdown files. Um so, that's one of the the angles or or benefits of it being all text.
</details>

对于那些自己不写代码的人，基本上，只要你能读懂符合逻辑的英语，你就能读懂 Open Prose。所以我们非常明确地不去深入探讨这种语言的语法。从技术上讲，它是一种编程语言，它有语法，但它真正更多是用来供人阅读和修改的，而不是让人从头手写的。我们不希望用户去费心学习它的 schema。因此，你可以大致描述这项工作，让你的智能体编写 Prose 程序，你知道，这可能会给你提供更多关于如何……的想法。

<details><summary>Original English</summary>
Um for the folks that are uh not writing code themselves, uh basically, if you can read logical English, you can read Open Prose. So, we're going to very specifically not get into the syntax of the language. Technically, it is a programming language and it has a syntax, um but it's really meant to be more um read by people and edited by people rather than like handwritten from scratch by people. Like you we don't want users concerned with like learning the schema. And so, you can kind of describe the work, have your agent write the Prose program, you know, that might give you some more ideas for how
</details>

<!-- chunk 2/6 -->

你可能会想要编辑它，或者你可能会看到某些想要更改的内容，呃，然后那个 Prose 程序就变成了可复用的工作流。

<details><summary>Original English</summary>
you might want to edit it, or you might see something you want to change, uh and then that Prose program becomes the reusable workflow.
</details>

嗯，然后对于 AI 工程师和开发者来说，呃，我认为你可能会想要使用它的切入点是——你知道的，它不是——它是一个不是框架的框架，我们稍后会聊一点这个，但甚至这个框架的编译器、甚至这个框架的虚拟机本身就只是一段巨大的提示词，你实际上就像是在植入代——代码来为你编译程序，植入 Codex 来做这件事。呃，所以，有——呃，你可以表达非常非常复杂的多智能体工作流，呃，像 Anthropic 的，嗯，呃，动态——他们叫它们什么来着？动态智能体工作流，嗯，可能就是一个类似的比喻。你可以在任何代码智能体中，仅用我们的 Markdown 契约就能做到这一点。

<details><summary>Original English</summary>
Um and then for the AI engineers and the developers, uh I think the angle where you might want to use this is it's you know, it's not it's a framework that's not a framework, and we'll talk a little bit about that in a second, but even the compiler for the framework, even the virtual machine for the framework, is itself just a giant prompt, and you're literally like incepting cod code into compiling the program for you, incepting Codex into doing that. Uh so, there's uh you can express very, very complex multi-agent workflows that uh things like the Anthropic um uh dynamic What do they call them? Dynamic agent workflows um would probably be like an analogy. You can do that in any coding agent in just our markdown contract.
</details>

呃，好的。首先关于“它仅仅是 Markdown”这个想法，嗯，这可以是一个完整的程序，仅仅作为一个例子。再次说明，我不想呃把精力太纠缠在语法上，嗯，但你基本上可以说：“嘿，这是目标，而且就像这是这——这所维护的契约。就像这里是这个契约所维护内容的定义。”嗯，再次说明，这只是一个非常简陋简单的例子。

<details><summary>Original English</summary>
Uh okay. So, first on this idea that it's just markdown, um this can be a complete program, just as an example. And again, I don't want to get uh so hung up in the syntax, um but you can basically say, "Hey, here's the goal and like here is the the contract that that the that this maintains. Like here's the definition of what this contract maintains." Um and again, that's just like a very silly simple one.
</details>

嗯，关于这里的这种想法，比如，那么你能声明什么呢？所以，我再次不想深入到模式（schema）、类型和语法中，但你或者你的智能体代表你在 CLI 中可以声明的东西被称为 prose write 函数。在我们的应用中，它基本上就是为你驱动整个应用的智能体。你可以创建子智能体。

<details><summary>Original English</summary>
Um the uh this idea here of like, well, what is it that you can declare? So, again, I don't want to get into the schema and the types and the syntax, but what you or your agent can declare on behalf of you with uh in the CLI is called the pros write function. In our app, it's basically just the agent that drives the whole app for you. You can make sub agents.
</details>

呃，你可以给那些具体的子智能体分配特定的技能。你可以拥有可用的特定工具。比如在搜索方面，我很喜欢 Exa。我觉得他们很棒，而且我不想让它进行常规的网络搜索。我总是希望它使用 Exa，因为对我来说它更快、更便宜。你可以说：“这是用于那个的技能。这是用于那个的 CLI。”如果你找不到那些东西，就干脆不要运行该程序。就像我们不会用另一种方式去做一样。所以，你可能会有一些特定于你的公司或组织的技能。然后本质上，你可以把它想象成将那个程序连接在一起，并且，如果它没有所有的依赖项，就不要编译，对吧？嗯，然后显而易见的是，这个程序的输入是什么，这个呃程序必须交付的输出是什么，这个契约必须交付的输出是什么。

<details><summary>Original English</summary>
Uh you can assign specific skills uh to those specific sub agents. You can have specific tools that are available. So, for example, for search, I love Exa. I think they're amazing and I don't want it doing regular web search. I always want it using Exa cuz it's faster and cheaper for me. You can say, "Here's the skill for that. Here's the CLI for that." If you can't find those things, just don't run the program. Like we're not doing it the other way. So, you might have skills that are specific to your company or to your org. And then essentially, you can think of it as like wiring that program together and like if it doesn't have all the dependencies, like do not compile, right? Um and then obviously that what are the inputs of this program, what are the outputs that this uh program has to deliver, this contract has to deliver.
</details>

嗯，再次说明，如果大家想要深入钻研并问 Dan 他是如何构建它的，这可能会是一个切入点。比如运行时本身也只是一个巨大的提示词。所以，嗯，你知道，在呃技能或提示词中我最喜欢的一些句子就像是“你就是编译器”。这不是一个比喻。你就是编译器。而且呃它似乎起作用了。

<details><summary>Original English</summary>
Um and again, like again, this could be something if people want to nerd out and ask Dan about how he built it. Like the runtime itself is just a giant prompt, too. So, um you know, some of my favorite sentences in the uh in the skill or the prompt is like "You are the compiler." This is not an analogy. You are the compiler. And uh it seems to work. Um
</details>

### 事件驱动与工作流任务

那么，呃，是的，然后是这种事件驱动的想法。我们希望摆脱这种“一切都是对话、一切都是聊天”的想法，嗯，去构建事件驱动的系统。

<details><summary>Original English</summary>
So, uh yeah, and then this idea of a event-driven. So, we want to get out of this idea that everything is a conversation, that everything is a chat, um and build event-driven systems.
</details>

所以，嗯，再次说明，仅仅对比一下这些不同的工作流树，就像是有事情发生了——那可能只是一个按计划执行的 cron 定时任务，那可能是 GitHub 中开了一个新的 issue，或者提交了一个新的 PR，或者你有某种 Webhook 系统，对吧？嗯，比如你的，我不知道，Stripe 出故障了之类的，然后你现在就可以，嗯，你知道，触发你所表达的那个工作流，呃，去端到端地处理整件事并履行契约。

<details><summary>Original English</summary>
So, um again, like uh just to compare these different workflow trees, it's like something something happens that might be just like a cron job on a schedule, that might be a new issue is opened in GitHub, or a new PR uh is filed, or you have some webhook system, right? Um that you're I don't know, Stripe isn't working, whatever, then you can now um you know, trigger that workflow that you've expressed uh to go handle that entire thing end to end and deliver on the contract.
</details>

嗯，所以，这种开始向作业（jobs）构建的想法，你可以用你自己的系统中的智能体自己来设置它，而我在 run.prose.md 中构建的，嗯，是这种想法：一个作业就是一个契约加上一个触发器。所以，再次说明，触发器可以是非常琐碎的事情，比如一个定时计划，所以在这里我基本上是在说：“好的，每天呃运行这个。”

<details><summary>Original English</summary>
Um and so, this idea of like starting to build towards jobs, so you can set this up yourself with your own agents in your own system, and what I built um in run.prose.md is um this idea of like a job is a contract plus a trigger. So, again, the the trigger can be something super trivial like a schedule, and so here I'm basically saying like, "Okay, every day uh run this."
</details>

嗯，但是呃目前，我们在现有的应用中实现的两个——两个主要触发器是，嗯，是 Webhook——它确实呃不可避免地覆盖了很多不同的东西，比如整个 Slack 应用就只是 Webhook，GitHub 也只是 Webhook——嗯，以及 cron 定时任务。如果你想给我们提供反馈，告诉我们可以为你把哪些触发器做得更便捷，我们很乐意添加更多。嗯，再次说明，从——从那个触发器开始，然后你去分流呃这些工作流。所以，呃，你可以开始通过创建 Prose 程序的这些常驻作业，从——嗯——去构建出这些，你知道的，代码工厂。

<details><summary>Original English</summary>
Um but uh right now, the two the two main triggers that we have implemented in the app as is are um our webhooks, which really uh inevitably cover a lot of different things, like a whole Slack app is just webhooks, GitHub just webhooks. Um and cron jobs. We're happy to add more if you want to give us feedback on ones that we can make easier for you. Um and again, from from that trigger, then you triage uh these workflows. So, uh you can start to build out these, you know, code factories from um creating these standing jobs um of the Prose programs.
</details>

呃，我想展示的、稍后会讲到的内容是，嗯，我为了确保能及时赶上这次活动而一直在构建的东西之一，是，嗯，是 Webhook，并且具体使用呃 GitHub 呃事件，而且我一直在强迫自己使用这个程序来开发这个程序。

<details><summary>Original English</summary>
Uh what I want to show and I'll get towards in a second is um one of the things that I've been building to make sure that's ready in time for this event is um is webhooks and using uh GitHub uh events specifically, and I've been forcing myself to use the program to develop the program.
</details>

因此，我们现在在系统中有的例子之一是——嗯，有两个主要的不同例子。一个是针对任何进来的 GitHub issue，你编写一个 prose 程序来定义它将如何尝试解决该 issue。所以，你可以把它做得如你所愿的那样复杂或简单。你可以运行——它可以是一个多智能体工作流。它可以具有它必须遵循的特定技能，或者使用模型。

<details><summary>Original English</summary>
And so, one of the examples that we now have in the issue in the system is, well, there's two different main ones. One is like any GitHub issue that comes in, you write a prose program for how it's going to try to address the issue. So, you can make that as complex or as simple as you want. You can run it could be a multi-agent workflow. It could have specific, um, skills that it has to follow or use models.
</details>

嗯，所以，基本上输入就是那个 issue 的内容，输出是一次提交。而且它必须一路进行，为你把那件事完成。呃，然后类似地，呃——并且我会更具体地展示这一个——就像用它来进行 PR 审查一样。所以，你可以进行这种事件驱动式的对抗性审查。而且我不知道你们大家是否听说了，嗯，今天早上在 Anthropic 工作坊中我觉得有趣的事情之一，他们谈到了嗯自我审查的挑战。就像是，你身处 Claude Code 中，然后你说：“好吧。给你，我准备让你推送到生产环境，但你能不能就再为我检查一次？”而且，你知道，它存在偏见，倾向于认为自己做得很好。人类也是如此，对吧？因此，嗯，我将展示一个工作流，在其中构建此内容的智能体基本上会从应用本身受到这种背压，嗯，通过——通过拉取请求（pull request）。

<details><summary>Original English</summary>
Um, and so, basically the input is whatever that issue was, the output is a commit. And it has to go all the way to getting that thing done for you. Uh, and then similarly, uh, and I'll show this one more specifically is like doing it with, uh, PR reviews. So, you can do this event-driven kind of adversarial review. And I don't know if you guys heard, um, in one of the things I thought was interesting this morning in the Anthropic workshop where they're talking about um, the challenges with self-review. So, like, you're you're in Claude Code and you're like, "All right. Here, I'm going to let you push to production, but just could you just check like one more time for me?" And like, it's it's biased to, you know, think that it did a good job. And so, so are humans, right? And so, um, I'll show a workflow where essentially the agents that are building this get this backpressure from the app itself um, through through pull requests.
</details>

### 问答与实现机制探讨

嗯，好的。那么在我们过渡到这个环节时，在我们切换到——切换到 Web 应用的过程中，现在有什么问题吗？

<details><summary>Original English</summary>
Um, okay. So, while we transition to this, are there any questions now while we switch over to the to the web app?
</details>

>> 别客气，没有问题是愚蠢的。那是举手还是拿手机？我在这里看不清灯光。

<details><summary>Original English</summary>
>> Please, no question is too silly. Is that a hand or a phone? I can't see the lights here.
</details>

>> 可能没有。

<details><summary>Original English</summary>
>> Maybe none.
</details>

>> 好的，请讲。

<details><summary>Original English</summary>
>> Yeah, go ahead.
</details>

>> 那边有一位。

<details><summary>Original English</summary>
>> One over there.
</details>

>> [清喉咙]

<details><summary>Original English</summary>
>> [clears throat]
</details>

>> 这是一个很好的问题。呃，我来回答这个。

<details><summary>Original English</summary>
>> It's a great question. Uh, I'll field this.
</details>

>> 好的，你应该来接这个。

<details><summary>Original English</summary>
>> Yeah, you should take that.
</details>

>> 好的。

呃，所以，我们实际上有这种想法，我之前提到过“做什么”和“怎么做”是两——两种不同的——两种不同的想法。声明结果，然后至于“怎么做”，是稍微——你——你把它留白，让智能体去琢磨出来。

在这个光谱上，如你所说，在特定地方你实际上确实希望对“怎么做”发表意见。事实上，我们有一个——一个特性——一种允许你固定“怎么做”的语法。所以你最初可以把它声明得很宽松。你可以让一个非常聪明的智能体去运行并琢磨出如何达到你所声明的事情。然后一旦它做到了，你可以说，这是智能体的轨迹（trace）。

让我们获取这个轨迹，我们将对它进行某种规范化，或者——或者我不知道，像热缩膜包装一样把它封装成一个“怎么做”。而这让我们能够做到的，实际上是降低完成工作流的成本。所以你从一个非常昂贵、能琢磨出方案的模型开始，然后如你所说，你把它变得更具体、更具确定性。所以你就像是在把这个光谱从完全仅仅是“做什么”，转移到——到“如何——如何去做”。而且——而且随着你这样做，成本就会降下来。

所以当我们说它全都是 Markdown 时，那是你可以开始的地方，但随后你也可以逐步转向——转向呃更具体的程序化、命令式风格的指令。

<details><summary>Original English</summary>
>> Yeah.

Uh, so, we actually have this idea of earlier I alluded to the what and the how being two two different two different ideas. Declare the outcome and then the how is a little bit you you leave it open, let the agent figure it out.

On that spectrum, you actually do, to your point, at at certain places want to weigh in on the how. And in fact, we have a a feature a syntax that lets you pin the how. And so you can initially declare it very loose. You can let a very intelligent agent run and figure out how to get to the thing that you've declared. And then once it does that, you can say here's the agent trace.

Let's take this trace and we will sort of codify it or or I don't know, shrink wrap it into a how. And what that allows us to do is actually drive down the the the cost of completing the workflow. So you you start with a very expensive model, figures it out, and then you sort of, as you say, make it more specific, more deterministic. So you're kind of like shifting the the the the the spectrum from totally at just a what to to how how to do it. And and the cost comes down as you do that.

So when we say it's all markdown, that's where you can start it, but then you can move your way to to uh more specific procedural imperative style instructions as well.
</details>

>> 是的，我想对此发表几点评论。首先，我们确实有一个系统，你可以获取诸如一段黄金会话，然后说把它变成一个可复用的工作流。比如那是“我经历过的最棒的 Claude Code 会话，像是我想要做——”因为这就是——我们一直遇到这种情况，对吧？而且我认为有——有其中的一部分是，这些东西是不确定的。我认为很多所谓的

<details><summary>Original English</summary>
>> Yeah, I guess a couple comments on that. So one, we do have a system where you can take like a golden session and like the like say make this into a reusable workflow. Like that was the best cloud code session I've ever had. Like I wanted to do cuz that's this is we get this all the time, right? And I think there's there's a part of it where like these things are non-deterministic. I think a lot of the quote-unquote
</details>

<!-- chunk 3/6 -->

固定且稳定的端点，人们已经发现它们实际上在发生变化，因为所有这些公司都面临算力限制，但我也觉得这就像是一种预期在变化的事情，对吧？就像你第一次尝试不管是什么，比如 Fable 之类的，让你大为惊艳，然后你就会觉得，随便吧，这个工作流程太神了，我每次都想要这样。然后你就像温水煮青蛙一样，抱有了不同的预期，突然之间这种惊艳就不再发生了，这里面有一部分纯粹是可靠性问题。所以你能做的一件事就是把一个非常好的会话固化下来。但另一方面，为了对 Dan 构建这个框架给予更多肯定，不仅字面上你看到的 markdown 文件只是它所看到的内容的冰山一角。上一次我查看完整的系统提示词或 skill（或者不管你怎么称呼它），我的意思是它既是一个 skill 也是一个系统提示词，接近 70,000 到 80,000 个 token……

<details><summary>Original English</summary>
pinned and stable endpoints people have shown actually are changing as all these companies are compute constrained, but I also just think there's this like changing expectations thing, right? Which is like the first time you tried like whatever it was, like Fable or whatever, like blew your blew your mind and you're like, I want whatever. This workflow is so amazing. I want this every time. And then you kind of like boil the frog and like have just different expectations and all of a sudden doesn't happen again and like some of that is just reliability. And so so one thing you can do is like take a really good session and like codify it. But then the other thing, just to give Dan a little bit more credit of like building the framework is like it's not just literally like the markdowns you see are like the tip of the iceberg of what it's seeing. So like the last time I checked the full like system prompt or skill or however you there's I mean it is a skill it is a system prompt is like close to 70,000 tokens, 80,000 tokens of like
</details>

>> 更长。我们正在试图清理它。我们正在试图……

<details><summary>Original English</summary>
>> longer. We're trying to clean it up. We're trying to
</details>

>> 是的，既然现在智能体更聪明了，我们可以把它弄得更短一点。但我们基本上拥有这套完整的类型系统，就像我们用一套非常非常清晰的类型系统和针对该智能体如何输出这个极其复杂的多智能体产品的极具针对性的提示词，来覆写 Markdown。不过，也许为了明确我们在哪些地方不去干涉……所以，比如 Claude Code 运行时，它有一套自己的子智能体系统。我们不想去干预它。我们不想让我们的提示词以任何方式特定于 Claude Code，因为 Codex 拥有一套完全不同的子智能体。所以我们就像，我不知道，一个元框架（meta harness），就像……

<details><summary>Original English</summary>
>> Yeah, well now that the agents are smarter we can make it a little bit shorter. But we basically have this full type system that's like we're overriding markdown with a very very clear type system and a very specific prompt for how the agent is going to deliver this incredibly complex multi-agent um product on the out um but maybe to be explicit about where we don't mess with it is like um So like Claude code when it runs it it has its own system for sub-agents. We don't want to mess with that. We don't want where we don't want our prompt to be um in any way like specific to Claude code cuz Codex has a totally different like set of sub-agents. So the the we're like I don't know, a meta harness, like
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 随便怎么叫吧。我们属于上层的一层，我们希望你带上你自己的 harness。我们不想成为那个 harness。我们希望成为由那个 harness 编译出来的东西。所以我猜这是关于……的几个部分。

<details><summary>Original English</summary>
>> whatever. We're one layer we want you to bring your own harness. We don't want to be the harness. We want to be this uh thing that is compiled by the harness. So I guess that's a couple pieces of
</details>

>> 这回答了你的问题吗？

<details><summary>Original English</summary>
>> Does that answer your question?
</details>

### Prose 现场演示

>> 嗯。好了。如果你想尝试它，它就在这里，二维码对应的地址是 run.prose.md，二维码就是指向它的。如果你想开始试用它的话。我在展示这个演示时想做的，是想展示几点内容。首先第一点是……这就是编辑模式下的一个 Prose 程序，对吧？它在技术上是 Markdown，Dan 覆写了比如 H3 标题，用来承载这个东西的所有类型。但是，让别人去学习这种语法并从头编写它，并不是真正的核心所在。所以，我们想要做的是……即便执行这个程序的所有内容都在这里，而且事实上，针对观众里真正的极客们，你可以看到我已经拿掉了 Markdown 文件的 front matter，那实际上就是云端正在发生的所有事情。所以我可以把这个程序导出为一个纯粹的 Markdown 文件，发送给我的朋友，它就会以完全相同的方式上传到他们的云端，以保持它的可组合性，并忠实于我们是一个纯粹 Markdown 的理念。

<details><summary>Original English</summary>
>> um All right. So if you want to try it, it's um it's here the QR code run.prose.md uh the QR code goes to that. If you want to start playing around with it. Um what I want to do in um showcasing this is to uh show off a couple of things. So, the um the first thing is that um the So, this is the This is a Prose program in the edit mode, right? It is technically Markdown and Dan's overridden like the H3 headers with all the types of this thing. But, getting someone to like learn that syntax and write it from scratch, it's kind of a not really the point. Um and so, what we um what we want to do is So, even though everything that executes this program is here, and in fact, I've for the real nerds in the audience, you can see that I've over I've taken the front matter of the Markdown file, and that is actually all of the stuff that's happening in the cloud. So, I could take this program and export it as a pure Markdown file and go send it to my friend, and they'll it'll upload in their cloud this the exact same way um to keep it like composable and keep it true to that idea of that we're pure Markdown.
</details>

不管怎样，核心理念是，即便那个东西就是本体，而且我们希望你去阅读它，但它并不是入口点。因此我构建的替代方案是一个智能体，希望它能在这里跟我说话。

<details><summary>Original English</summary>
Um anyways, the whole idea is like even though that is the thing and we'd want you to be reading this thing, it's not like the entry point. So, what I've built instead is um an agent which hopefully will talk to me here.
</details>

>> 嗨，我是 Prose。你今天希望完成什么？

<details><summary>Original English</summary>
>> Hi, it's Prose. What are you hoping to get done today?
</details>

>> 好的，每当我有新的拉取请求（PR）时，我希望你在我的 run-prose 仓库中为我写一个 Prose 程序，以一个不喜欢 AI 生成代码的暴躁资深开发者的身份来审查它。

<details><summary>Original English</summary>
>> Okay, so uh every time I have a new pull request, I want you to um write me a Prose program in my run-prose repo that will review it as if you are a a grumpy senior developer who doesn't like AI-generated code.
</details>

>> 没问题，我可以做这个。稍等。

<details><summary>Original English</summary>
>> Sure, I can do that. Hang on.
</details>

>> 好的。那我要把自己静音了。它正在说话。它会尝试把它解决出来。整个理念就是任何……任何会产生费用或花钱的操作，你都必须确认。我认为这是一种最佳实践。哦，好的。太棒了。我刚才必须确认，因为那个操作需要花钱才能……这就是 Prose 的 write 函数。它基本上就是接收我的查询，并将据此生成一个新的程序，包括所有的连接线路。这一步会稍微花费更长一点的时间。所以在它运行的同时，我来展示一下手动完成这个操作的方法。它在 jobs 标签页里。我不知道为什么这里断断续续的。在 jobs 标签页里，我们可以来到这里，新建一个 job。“按计划执行”（on a schedule）就是一个 cron job。我们有一个开放式的 webhook。所以你可以让你自己或者你的智能体去使用我们专门的 webhook，或者把我们的东西连接去监听你的 webhook。但是对于 GitHub……

<details><summary>Original English</summary>
>> Okay. So, I'm going to mute myself. So, it's it's talking. It's going to try to figure this out. And the the whole idea is like anything So, anything that can charge money or spend money, you have to confirm. I think that's like a best practice. Um Oh, yeah. Great. So, I had to confirm cuz that that action costs money for it to So, that's the pros rate function. So, it basically takes my query and is going to generate a new program um from that including all the wiring. This step is going to take a little bit longer. So, while that's running, I'll show like the manual way of doing that. Which is in the jobs tab. I don't know why this is cutting out. Um in the jobs tab, we can go here, make a new job. The the uh on a schedule is just a cron job. We have a a web hook that's open-ended. So, like you can have yourself or your agent um either use our specific web hook or like wire our thing to listen to your web hook. But for Git GitHub, um
</details>

那我做同一个演示。针对 GitHub 的 pull request，我们让它变得很简单。我们要在 run.prose 里完成它。我们要……我已经预先连接好了这个合约。内容就是，“好的，你要来审查我的东西。”然后我可以选择它们所拥有的模型。我们稍后会添加更多模型。目前我们有来自 OpenAI 的排名前三的模型。然后我只要创建并部署它就行了。

<details><summary>Original English</summary>
so, I'll do the same one. So, for GitHub pull requests, we make that easy. Um we're going to do it in the run.pros. We're going to uh I've just pre-wired this contract. It's like, "Okay, you're going to review my thing." And then I can pick, you know, what uh model that they have. We'll we'll add more uh later. Right now, we have the the like top three from uh OpenAI. Uh and then I would just uh create that and deploy that.
</details>

### 背压与合约验证机制

在这个运行的同时，我想展示的另一件事是我实际上是如何将它作为背压（back pressure）来使用的。主要的事情是……不要太纠结于上面无论什么具体的内容。但我想在这里向你们展示的是它的量级。在不管这算多长时间里，比如这整整一屏可以追溯到 3 天前，但接着如果我点到这里，这些全都是来自 3 天前或 4 天前的。也就是在短短几天的时间跨度里，这里处理了数十个、数十个又数十个 PR，每次我提出一个新的功能请求——关于我想为这次活动准备好的这个 GitHub webhooks 功能——每一个 PR 都会触发一系列审查智能体，有的比较简单，比如“好的，这个显然立刻就起效了”，所以只进行了一轮审查；而其中有一些经历了 14 轮审查，才让审查智能体们达成一致并让这个东西通过。

<details><summary>Original English</summary>
So, then the other thing while this um this one's working that I want to show is how I've actually been using that as back pressure. So, the main thing Don't get too hung up on the um whatever, the content up here. But the thing that I want to show you here is like the the the volume. So, like in whatever that is, like this entire thing is goes back to 3 days ago, but then if I go here, like these are all still from 3 days ago or 4 days ago. Or so, like in the span of a few days, this is doing like dozens and dozens and dozens of PRs, and every time I'm asking for a new feature about this GitHub was webhooks feature that I wanted to have ready for this event, uh every single one of those is firing off like a series of review agents where it's like so some of them are simple like okay, this one clearly seems to have worked right away. So, there's only one round. Uh some of these had, you know, 14 rounds of review before uh it felt like the reviewer agents were like aligned and it let this thing pass.
</details>

甚至就在今天，我注意到关于它执行方式的一些不太满意的地方，我基本上能够说，好的，在我们的暂存（staging）服务器上——不要动生产环境，我马上要做演讲了——在暂存服务器上，我希望你们去修改它被触发的确切方式，但你们自己必须使用这个系统。因此，我们的开发版本和生产版本给出了不同的审查意见。现在运行在这里的智能体——我们可以在这里的 runs 标签页看到所有不同的任务——基本上必须把这些反馈考虑进去，我的开发者智能体不把那些反馈考虑进去，就不能认为自己的工作完成了。

<details><summary>Original English</summary>
Um and even just today, like I noticed something that I didn't love about um how it was doing it, and I was able to um you know, basically say okay, um on our staging server, you know, don't mess with production. I'm about to give a talk. On the staging server, I want you to like change the things the exact ways in which this will get triggered, but you have to use the system yourself. So, um like both our dev version of this and our prod version of this are giving different reviews. Um and now the agent that's running uh here, uh which we can see all the different jobs in the the runs tab here, essentially like cannot consider its job to be complete until it's like um a a like um like my developer agents have like have to take that feedback into account.
</details>

>> 我只想强调一下，像这样的流程与你见过的任何其他基于聊天或基于智能体的流程有什么不同，那就是所有这些都在对照着一个合约进行比对。所以你可以把它看作每次都有一个全新的会话在对照着这个以声明式方式写成的合约进行基准评估，正如 Raymond 刚才提到的，这让模型摆脱了这种自我认同的死循环，你肯定不希望由同一个模型去检查刚完成的事情。所以你在生成新的会话并将它们与合约进行比对碰撞，我觉得这对于该怎么做而言就是一个更好的模式。是的，请讲。

<details><summary>Original English</summary>
>> And just to emphasize like what's different about something like this from any other chat-based or or agent-based flow that you've seen is all of these are getting compared against a contract. So, you could think of it as a fresh session every time is getting benchmarked against this contract that you've written declaratively, which as as Raymond alluded to earlier, gets the models out of this like self-confidence loop where you don't want the same model checking the thing that was done. So, you're spawning new sessions and and bouncing them off of a contract, which is I just a better uh pattern for for how to do it. Yeah, go ahead.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但是，这难道看起来不是像 Jeff 这样的单样本分类器（one-shot classifiers）的极佳机会吗？[清喉咙]

<details><summary>Original English</summary>
>> But, doesn't [clears throat] it seem like a great opportunity for one-shot classifiers like Jeff?
</details>

>> 是的。所以他们……

<details><summary>Original English</summary>
>> Yeah. So, they um
</details>

>> 我们管线里有很多好东西。所以对照合约进行检查和验证的想法……抱歉，Raymond。

<details><summary>Original English</summary>
>> We have a lot of good stuff in the pipe. So, so the idea of checking against a contract and and verifying it. Sorry, Raymond.
</details>

>> 没事。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 在这些决策模型上非常令人兴奋，你有一个作为某种理想状态的合约，然后你有混乱的现实世界状态，你可以应用一个通用类别的决策模型，比如像 Jeff 那样的，来判断这是通过了还是没通过？

<details><summary>Original English</summary>
>> Uh it it is super exciting on these decision models where uh you you have a contract, which is some ideal state, and then you have your messy real-world state, and you can apply a general class decision model like like Jeff to say, is this is this passing or not?
</details>

>> 所以，我认为……

<details><summary>Original English</summary>
>> So, I think
</details>

>> 在这里面，但它即将到来。

<details><summary>Original English</summary>
>> in this, but it's coming.
</details>

>> 是的，而且我认为我认为

<details><summary>Original English</summary>
>> Yeah, and I think I think
</details>

<!-- chunk 4/6 -->

### OpenProse 与决策模型架构

没有……嗯，就像是，Dan，再次强调，我们有点脱离讲稿了，但这是个极好的问题，而且呃，伟大的 Jeff-ification 正在降临。所以，我们需要讲讲这个。嗯，我想我和 Dan 都在深入思考这个问题，并且意识到，像 OpenProse 本身，这种全 Markdown 的语言，我认为在 Jeff 的领域里没有任何位置，因为它们不是生成式的。也就是说，关于生成一种语言并理解一种语言的整个概念，它并不是那样。

<details><summary>Original English</summary>
 without

 um





like





Dan,

 again,

 we're

 going

 a

 lot

 off





script,

 but

 it's

 a

 great

 question,

 and





uh

 the

 great

 Jeff-ification

 is

 upon

 us.





So,

 we

 need

 to

 speak

 to

 this.

 Um





is

 uh

 I

 think

 Dan

 and

 I

 both





been

 thinking

 about

 this

 a

 lot

 and





realized

 that

 like





um





OpenPros

 itself,

 the

 language

 that's

 all





markdown,

 I

 think

 does

 not

 have

 any





place

 in





the

 Jeff

 land

 because

 they're

 not





generative.

 Like,

 so

 the

 whole

 idea

 of





the

 lang-

 like

 it

 generating

 a

 language





and

 understanding

 a

 language,

 like

 it





uh

 it's

 not

 that.
</details>

但我认为，在我们看来它能非常契合的两个地方——尤其是结合托管的 run.pros 来看——其一是在后端。OpenProse 的缺点或劣势在于，你在让智能体说：“我已经达成了契约。这就是结果。”对吧？所以我经常对人们说，OpenProse 背后的初衷类似于 DSPy 之类的东西，你希望拥有这样一个抽象层，在其上表达非常复杂的工作流。

<details><summary>Original English</summary>
But,

 I

 think

 the

 the





two

 places

 where

 we

 think

 it

 would

 fit





really

 well,

 and

 in

 particular

 with

 the





hosted

 run.pros,

 is

 one

 on

 the

 back

 end.





So,

 the

 the

 downside

 or

 the

 weakness

 of





OpenPros

 is

 it

 is

 you

 are

 letting

 the





agent

 say,

 "I

 have

 met

 the

 contract.





Here

 it

 is."

 Right?

 And

 so,

 I'll

 often





say

 to

 people





uh

 like

 the

 intent

 behind

 OpenPros

 is





similar

 to

 something

 like

 DSPy

 where

 you





want

 to

 have

 like

 this

 abstraction

 layer





over

 which

 you

 can

 express

 very

 complex





workflows.
</details>

但在实现上，它与 DSPy 完全相反。DSPy 的逻辑是每一次 LLM 调用都是一个黑盒，你把那个东西彻底隔离起来。全是确定性代码，全是有类型的接口，仅仅让那个黑盒做那一件事。Dan 在 OpenProse 上采用的方法则完全相反，那就是 AI 正变得足够聪明，足以充当编译器。让一切都留在模糊的领域里。

<details><summary>Original English</summary>
The

 implementation

 is

 the

 exact

 opposite





of

 DSPy.

 DSPy

 is

 like

 every

 LLM

 call

 is





a

 black

 box

 and

 you





you

 isolate

 the

 crap

 out

 of

 that

 thing.





It's

 all

 deterministic

 code.

 It's

 all





typed

 interfaces

 to

 like

 only

 let

 the





black

 box

 do

 that

 thing.

 Dan's

 approach





with

 open

 prose

 is

 the

 exact

 opposite





which

 is

 like

 AI

 is

 getting

 smart

 enough





to

 be

 the

 compiler.

 Like

 let

 everything





be

 in

 fuzzy

 land.
</details>

不过它的弱点在于，如果你在 Haku 上运行，或者在 Fable 上运行，你会得到非常不同的结果，而且你还在让它自己声明已完成。所以我觉得对于像 Jev，或者这些新的决策模型——无论我们想怎么称呼它们，系统 1 模型——一个非常契合的位置，就像你刚才说的，是在任务末端作为验证器，非常非常快且廉价。

<details><summary>Original English</summary>
So

 the

 the

 the

 weakness

 of

 it

 though

 is





like

 if

 you

 run

 it

 on

 Haku

 or

 you

 run

 it





on

 Fable

 you're

 going

 to

 get

 a

 very





different

 result

 and

 and

 you're

 also





letting

 it

 say

 I'm

 done.

 So

 I

 think

 a





very

 natural

 place

 for

 like

 uh

 Jev

 or





these

 new

 like

 decision

 models

 or





whatever

 we

 want

 to

 call

 them

 system

 one





models

 is

 like

 you

 were

 saying

 like

 as

 a





verifier

 on

 the

 end

 of

 the

 job

 like

 very





very

 fast

 and

 cheap.
</details>

然后另一件我想构建的、与此相关的事情是一个路由器。为什么我还非得去点击按钮，区分什么 issue 进入 issue 任务、PR 进入 PR 审查任务？为什么我不能直接说，把所有进来的 GitHub 事件，比如解决 issue、审查 PR，对吧？

<details><summary>Original English</summary>
Um

 and

 then

 the





other

 thing

 that

 I

 want

 to

 build

 that's





relevant

 to

 this

 this

 is

 like

 a

 router.





So

 like

 why

 would

 I

 have

 to

 go

 click

 the





button

 that

 like

 oh

 issues

 go

 to

 the





issue

 job

 but

 PRs

 go

 to

 the

 PR

 review





job.

 Why

 don't

 I

 just

 say

 like





okay

 all

 the

 GitHub

 events

 that

 come

 in





like

 you

 know

 solve

 the

 issues

 review





the

 PRs

 right?
</details>

另一个问题。

<details><summary>Original English</summary>
Another

 question.
</details>

>> 别再给他们提供关于这个游戏的想法了。

<details><summary>Original English</summary>
>> Don't

 give

 them

 any

 more

 ideas

 about

 the





game.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 我知道，我正打算说……我正打算……

<details><summary>Original English</summary>
>> I

 know

 I

 was

 going

 to

 say

 I

 was

 going

 to
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 谢谢。

<details><summary>Original English</summary>
>> Thank

 you.
</details>

现在推特圈里正好在讨论这个热点话题：为什么不直接对其进行强化学习（RL）？如果我这里有针对契约运行的全部这些出色的运行记录，为什么我不直接对其进行 RL？

<details><summary>Original English</summary>
It

's

 just

 topical

 on

 the

 Twitter

 sphere





at

 the

 exact

 moment

 that

 like

 why





wouldn't

 you

 just

 RL

 this?

 Like

 if

 I

 got





all

 these

 beautiful

 runs

 here

 against





the

 contract

 why

 am

 I

 not

 just

 RLing





this?
</details>

>> 所以，回到语言的问题上，其中的一个想法是：我们究竟为什么要在语言中做这件事？从人类最初的角度来看，你可以把它提交到 git，可以对其进行版本控制，或者你可以在 Notion 或 Jira 中使用它，让你团队中的任何人都能使用。但从工程角度来看，它是纯文本这一事实，对于 RL 来说极其完美且出色。所以，我们现在虽然还没有这么做，但这绝对是我们正在与多家潜在客户探讨的事情，即一旦你所有的内容都以文本形式编写，这对于 RL 来说就好得多了。

<details><summary>Original English</summary>
>> So





So

 one

 of

 the

 ideas

 back

 to

 the

 language





question

 is

 one

 of

 the

 ideas

 of

 like

 why





why

 are

 we

 doing

 this

 at

 all

 in





language?

 Like

 the

 original

 human

 side





of

 this

 is

 like





you

 can

 commit

 it

 to

 get

 and

 you

 can





version

 control

 it

 or

 you

 can





you

 know

 use

 it

 in

 notion

 or

 or

 Jira

 and





and

 have

 anybody

 on

 your

 team

 using

 it.





But

 from

 from

 a

 engineering

 side

 it's





the

 fact

 that

 it's

 all

 text

 is

 like





perfect

 and

 beautiful

 for

 for

 RL.

 So,





we're

 not

 doing

 that

 right

 now,

 but

 like





that's

 absolutely

 something

 we're





talking

 with

 various

 prospects

 about

 is





like

 once

 you

 have

 all

 of

 your

 stuff





written

 as

 text,

 this

 is

 like
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对 RL 来说要好得多。

<details><summary>Original English</summary>
>> a

 whole

 lot

 better

 for

 for

 RL.
</details>

>> 是的，我们还没达到让这变得至关重要的规模，但如果你自己托管模型，并且有大约 10 万 token 的前缀，那你就可以对它进行微调（jit），或者去构建这些更高 token 效率的表示形式。所以，如果有人想在 OpenProse 里处理 1 万亿个 token，我们很乐意为你进行处理。

<details><summary>Original English</summary>
>> Yeah,

 we

 haven't

 hit

 volumes

 where

 this





is

 important,

 but

 like

 if

 you

 are





hosting

 the

 model

 and

 you

 have

 this





100,000-ish

 token

 prefix,

 then

 you

 can





like

 just

 it

 or

 you

 like,

 you

 know,





build

 these

 um





more

 token

 efficient

 representations.





So,





um





Yeah,

 if

 someone

 wants

 to

 do

 a

 trillion





tokens

 in

 Open

 Pros,

 we'll

 happily

 just





it

 for

 you.
</details>

### 演示部署与本地化架构

嗯，总之回到刚才的话题，谢谢，这些问题真的很好。我们现在有了“脾气暴躁的资深 PR 审查员”。同样，核心理念是，智能体替我们完成了所有这些工作。这里的核心理念在于，通过部署这个任务，只要我们收到新的 PR，它就会开始产生费用，所以我必须点击它。然后我要确认一下。一旦完成部署，当我返回我的任务列表时，它的界面就会……来看看。如果我们切换一下，哎呀，我确实切换了。

<details><summary>Original English</summary>
Um

 So,

 anyways,

 to

 go

 back,





thank

 you.

 Those

 are

 Those

 are

 really





good

 ones.

 We

 now

 have

 our

 grumpy

 senior





pull

 request

 review.





Um

 and

 again,

 like

 the

 key

 idea

 is

 so





the

 agent

 did

 all

 that

 for

 us.

 The

 key





idea

 here

 is

 um





uh

 like

 the

 by

 deploying

 this

 job,

 like





this

 will

 now

 start

 spending

 money

 when





whenever

 we

 get

 a

 new

 PR,

 so

 I

 have

 to





click

 that.

 So,

 then

 I

'm

 going

 to





confirm

 that.

 And

 then

 once

 this

 is





deployed,

 it'll

 go

 when

 I

 go

 back

 over





to

 my

 jobs,

 it

 will

 um





it

 will

 look

 exactly

 like

 uh

 let's

 see.





So,

 if

 we

 just

 Oops,

 I

 did





switch

 that.
</details>

等它加载完毕，我们应该就能看到，那个暴躁审查员在最顶部或者最底部。对，就在这里：“Grumpy AI skeptic PR review”。你们可以看到我之前练习过。

<details><summary>Original English</summary>
Once

 this

 loads,

 we

 should

 see





and

 the

 grumpy

 one

 is

 at

 the

 top

 or

 the





bottom.





Yeah,

 here

 we

 go.

 Grumpy

 AI

 skeptic

 PR





review.

 So,





um

 you

 can

 see

 I

 was

 practicing

 earlier.





Um
</details>

好的，来看看这一块。我认为这些就是主要的内容。是的，我负责 run.pros.md，如果你们遇到任何问题，别告诉我老板，直接发给我。我的智能体们会替你们处理好的。

<details><summary>Original English</summary>
Okay.

 So,





let's

 see

 what

 in

 terms

 of

 this.

 I

 think





those

 are

 the

 main

 things.

 Um





Yeah,

 I'm

 in

 charge

 of

 run.pros.md,

 so





if

 you

 run

 into

 any

 issues,

 don't

 tell





my

 boss,

 you

 just

 send

 it

 straight

 to





me.





Uh

 and

 my

 agents

 will

 uh

 take

 care

 of

 it





for

 you.
</details>

但我确实对这个感到非常兴奋，它就是一个简单、易用的方式，用来构建这种基于事件的系统。如果你想看到其他触发器或其他功能，那对我来说会很有意思。不过再次重申，你完全不需要使用托管版本，你也可以使用技能替代：`NPX skills add open prose prose`。不过现在，接下来 Dan 将会为我们金融界的朋友过一个具体的例子，我们将在 Codex 中展示它，然后他会借此机会多讲讲这一切在底层的运作机制。

<details><summary>Original English</summary>
Um





but

 yeah,

 I'm

 really

 excited

 about

 this





as

 just

 like

 a

 a

 simple,

 easy-to-use

 um





um

 way

 for

 having

 these

 like

 event-based





systems.

 If

 you

 want

 to

 see

 other





triggers

 or

 other

 features

 then

 that's





really

 fun

 for

 me.

 But

 again,

 you

 don't





need

 to

 use

 the

 hosted

 thing

 at

 all

 and





like

 you

 can

 uh





you

 can

 use

 the

 um

 the

 skill

 instead

 NPX





skills

 add

 open

 prose

 prose.

 Um

 but

 now





uh

 with

 that

 Dan

 is

 going

 to

 um





go

 through

 a

 specific

 example

 that

 is





for

 [clears throat]

 our

 finance

 friends





um

 and

 we're

 going

 to

 show

 that

 one





uh

 in





Codex

 and

 then

 he'll

 use

 that

 as

 an





opportunity

 to

 talk

 a

 little

 bit

 more





about

 how

 all

 this

 works

 under

 the

 hood.
</details>

>> 好的。谢谢。

<details><summary>Original English</summary>
>> Yep.

 Thank

 you.
</details>

>> 不客气。

<details><summary>Original English</summary>
>> Sure.
</details>

>> 嗯，让它在云端跑起来挺有意思的。我们一直在与各种客户和潜在客户探讨的更有趣的用例之一，是你可以把这作为一个可以在内部构建的框架、语言或模式，并且可以在本地（on-prem）运行。这里的核心理念就在于你可以在本地运行它。你不需要使用我们的云端版本。我们很乐意你在云端试用并体验一下。但如果这是你想在组织内部实施的东西，我们看到的最有趣的用例，是构建在开源模型之上、构建在你自己的测试框架（harness）之上——自带测试框架，然后把这个作为其上层的应用层，这样能让你在内部构建起这套完整的技术栈。你无需将任何数据发送给那些大模型实验室。比数据更重要的是，你无需交出你的机构……

<details><summary>Original English</summary>
>> Um

 so





getting

 that

 working

 in

 the

 cloud

 is

 is





interesting.

 One

 of

 the

 more

 interesting





use

 cases

 that

 we've

 been

 talking

 about





with

 various

 customers

 and

 prospects

 is





um





you

 can

 this

 is





this

 is

 a

 framework

 or

 a

 language

 or





pattern

 that

 you

 can

 build

 in

 house

 and





you

 can

 use

 you

 can

 run

 it

 on

 prem.

 The





whole

 idea

 here

 is

 that

 you

 can

 run

 it





on

 prem.

 You

 don't

 need

 to

 use

 our

 cloud





version

 of

 it.

 We'd

 love

 you

 to

 try

 it





out

 in

 the

 cloud

 and

 and

 and

 and

 play





with

 it

 get

 a

 get

 a

 feel

 for

 that.

 Um





but

 if

 this

 is

 something

 that

 you

 want





to

 implement

 uh

 inside

 your

 organization





the

 most

 interesting

 use

 case

 that

 we're





seeing

 is

 on

 top

 of

 open

 models

 on

 top





of

 your

 own

 harness

 bring

 your

 own





harness

 and

 then

 use

 this

 as

 kind

 of

 the





application

 layer

 on

 on

 top

 of

 that

 and





that

 lets

 you

 build

 this

 full

 stack

 in





house.

 You

 don't

 have

 to

 ship

 any

 of





your

 data

 out

 to

 the

 labs.

 More





important

 than

 your

 data,

 you

 don't

 have





to

 ship

 out

 your

 institutional
</details>

我们其实更倾向于将 OpenProse 视为以文档形式呈现的机构操作知识，对吧？可以把它理解为标准作业程序（SOP）。所以比你的数据更重要的是，你绝不想把你的标准作业程序发送给那些大实验室。

<details><summary>Original English</summary>
We

 like

 to

 think

 of

 open

 prose

 actually





as

 like

 institutional

 operational





knowledge

 as

 documentation,

 right?

 Think





of

 it

 as

 like

 standard

 operating





procedures.

 So

 even

 more

 important

 than





your

 data

 is

 you

 don't

 want

 to

 be





shipping

 your

 standard

 operating





procedure

 out

 to

 the

 big

 labs.
</details>

因此这非常契合这种开源技术栈，应用层位于其顶层。我们以开放核心（open-core）的形式发布它，采用宽松许可证。你可以把它引入内部使用。我们已经有许多大公司在这么做了。而且你可以自带测试框架，可以配合你公司已经批准的模型使用。这样你就不必觉得是在把数据或组织的知识拱手送出。

<details><summary>Original English</summary>
Um

 and

 so

 so

 this

 fits

 really

 nicely

 in





this

 stack

 of

 of

 open

 open

 source





application

 layer





sits

 on

 top.

 We

 we

 publish

 this

 open





open

 core.

 Uh

 it

 has

 a

 permissive





license.

 You

 can

 bring

 it

 in

 house

 and





and

 use

 it.

 We

 have

 a

 number

 of

 big





companies

 who

 are

 are

 already

 doing





that.

 Um

 and

 and

 you

 can

 bring

 your

 own





harness.

 You

 can

 use

 it

 with

 the





approved

 models

 that

 your

 company





already

 has.

 Uh

 so

 you

 don't

 have

 to





feel

 like

 you're

 throwing

 data

 or

 your





organization's

 knowledge

 over

 the

 wall.
</details>

### 量化模型文档工作流

这只是……我的意思是，我们可以稍微深入讲一下这个，我也想回答更多的问题。这是我们正在为一个客户构建的工作流，该客户对使用 OpenProse 记录他们的量化模型文档很感兴趣。对于熟悉这方面的各位来说，量化模型有各种监管承诺，即每 3 年、或每 1 年、或在特定事件变更时，你都需要更新这些量化模型的模型文档。根据我们的经验，这通常是一个耗费大量高智力白领人力的过程，对吧？这些人——可能你们当中有些人每年也要花一部分时间去编写文档。记录你的模型用途是什么、在什么条件下进行了测试、上游有哪些其他模型引用了它，以及一整套其他必需的内容。这些显然是监管机构、内部审计以及内部合规部门所要求的。

<details><summary>Original English</summary>
Um

 this

 is

 just

 I

 mean

 a

 a





we

 can

 get

 into

 this

 a

 little

 bit

 and

 I





want

 to

 field

 more

 questions.

 Um

 this

 is





a

 a

 workflow

 that

 we're

 building

 out

 for





a

 customer

 um

 that

 is

 interested

 in





using

 OpenProse

 to

 document

 their

 quant





models.

 So

 uh

 for

 those

 of

 you

 who

 are





familiar,





um

 quant

 models

 have

 all

 sorts

 of





regulatory

 um





um

 commitments

 whereby

 every

 every

 3





years

 or

 every

 1

 year

 or

 on

 certain





event

 changes,

 you

 need

 to

 update

 the





the

 model

 documentation

 for

 these

 quant





models.

 So

 this

 is

 normally

 a

 process





that

 we

 found

 in

 our

 experience

 that

 is





uh

 human

 white

 collar,

 very

 smart

 person





intensive,

 right?

 These

 people

 uh

 maybe





some

 of

 you

 probably

 spend

 a

 a

 share

 of





your

 your

 year

 going

 through

 and

 and





writing

 documentation.

 That

 documents





what

 your

 model's

 being

 used

 for,

 under





what

 conditions

 was

 it

 tested,

 under

 um





uh

 who

 who

 what

 other

 models

 reference





it

 upstream,

 and

 a

 whole

 slew

 of

 other





required

 These

 are

 obviously

 required

 by





the

 regulators

 and

 your

 internal





auditors

 and

 your

 internal

 compliance.
</details>

所以这是一个我们成功运行的流程。它非常完美，因为在某种程度上，监管文档就像一个 OpenProse 程序，对吧？这些都是以散文形式书写的要求。嗯，还有……

<details><summary>Original English</summary>
Um

 so

 this

 is

 this

 is

 a

 a

 flow

 that

 that





we've

 found

 success

 running.





Uh

 it's

 it's

 perfect

 because

 in

 some





ways

 the

 regulatory

 docs

 are

 like

 an





OpenProse

 program,

 right?

 And

 so

 this





these

 are

 requirements

 written

 as

 prose.





Um

 and

 and
</details>

<!-- chunk 5/6 -->

### 运行内核与程序

所以，我这就启动。

<details>
<summary>Original English</summary>
so
I'm
going
to
kick
off
</details>

你可以看到，呃，我们在 Codex 里面。你可以在 Cloud Code 中运行这个。你也可以在自己的测试框架上运行。重点在于，这与具体的测试环境完全无关。

<details>
<summary>Original English</summary>
You
can
see
here
uh
we're
in
Codex.
You
You
run
this
in
Cloud
Code.
You
could
run
this
on
your
own
harness.
The
whole
point
is
that
this
is
harness
agnostic.
</details>

呃，所以我们就是说引导内核。呃，然后是 pros 运行，接着是具体的程序。所以我要启动这个，趁着它运行的时候，我可以向你们展示一下内核是什么样的，呃，以及程序本身看起来是什么样的。

<details>
<summary>Original English</summary>
Uh
so
we
we
just
say
boot
the
kernel.
Uh
and
then
pros
run
and
then
a
specific
program.
And
so
I'm
going
to
kick
this
off
and
while
it
runs
I
can
show
you
like
what
the
kernel
looks
like
uh
and
then
what
the
program
itself
looks
like.
</details>

嗯，切回到 Chrome。然后——

<details>
<summary>Original English</summary>
Um
just
go
back
to
Chrome.
And
then
</details>

>> 就在那儿。

<details>
<summary>Original English</summary>
>> Right
there.
</details>

>> 是呃，那一个。

<details>
<summary>Original English</summary>
>> It's
uh
that
one.
</details>

这就是内核。嗯，它是 markdown 格式。它不是给你们看的，这也是为什么它排版成这样。我们最初把它做成很好看的外观，结果大家抱怨说：“这是什么？”

<details>
<summary>Original English</summary>
So
this
is
the
kernel.
Um
it's
markdown.
It's
not
intended
to
be
read
by
you
which
is
why
it's
formatted
like
this.
We
originally
had
it
in
a
nice
looking
format
and
people
complained.
They're
like,
"What
is
this?"
</details>

呃，它是给智能体读的。呃，它就是 markdown。它是预期操作的指南。你可以把它看作非常类似于引导加载程序或解析路径、索引系统、一种寻找智能体所需的其他文档的方式。

<details>
<summary>Original English</summary>
Uh
it's
meant
to
be
read
by
the
agents.
Uh
and
it's
just
markdown.
It's
operating
instructions
for
what
to
expect.
You
could
think
of
it
a
lot
like
a
a
bootloader
or
a
resolution
path,
a
an
index
uh
system,
a
way
of
finding
other
documents
that
you
that
that
the
that
the
agent
needs.
</details>

嗯，然后程序本身看起来——再次说明，这就是我在 Codex 中引用的内容——看起来非常相似。这也是 markdown。它包含了监管机构、合规部门和审计人员所要求的一整套规范。

<details>
<summary>Original English</summary>
Um
and
then
the
program
itself
looks
and
again
this
is
what
I
referenced
in
Codex
looks
very
similar.
So
this
is
again
markdown.
It
contains
a
whole
slew
of
the
requirements
that
the
regulators
and
the
compliance
and
the
auditors
are
looking
for.
</details>

呃，这规定了，你知道，呃，最终结果的理想状态将符合这一契约。

<details>
<summary>Original English</summary>
Uh
and
this
specifies,
you
know,
uh
the
ideal
state
of
of
the
end
result
is
going
to
comply
with
this
contract.
</details>

呃，所以你只需要传入这两样东西。你就传入公开发布的内核。你们现在所有人都可以直接下载，呃，试用一下，然后编写你想要的任何程序，任何需要满足一组复杂条件的契约，然后智能体就会全力运转。你知道，测试环境越好、模型越好，它们产出结果的速度就越快、成本就越低。呃，不过核心理念在于，你在声明结果，而不是在声明如何去实现它。

<details>
<summary>Original English</summary>
Uh
and
so
those
are
the
only
two
things
you
pass
in.
You
just
pass
in
the
kernel
which
is
published
publicly.
You
can
all
download
that
right
now
uh
and
and
and
try
it
out
and
then
write
any
program
that
you
want,
any
contract
that
requires
some
complex
um
set
of
conditions
to
satisfy
and
then
the
agents
are
just
going
to
chug
and
and
the
you
know,
the
better
the
harness,
the
better
the
model,
the
the
faster
and
the
cheaper
that
they
will
produce
the
output.
Uh
but
the
idea
is
that
that
you're
you're
declaring
the
the
result
rather
than
declaring
how
to
how
to
go
about
about
doing
it.
</details>

### 金融模型文档生成与评估

嗯，我们回去看看。我们这里用了一个相对便宜的模型来跑，这样能快一些。呃，但它还在处理。

<details>
<summary>Original English</summary>
Um
Let's
see
we
can
poke
back
and
see.
We
ran
this
with
a
a
relatively
cheap
model
here
so
that
it
would
run
faster.
Uh
but
it's
still
working.
</details>

嗯，看起来快完成了。这——我是说，这就是它生成的文档。在这个例子中，我们正在为 SOFR 曲线编写文档。这是一个公开的模型，所以我们这里没有展示任何银行内部数据。嗯，这个……我不知道，举个手，在场有宽客（量化分析师）吗？来审核一下？

<details>
<summary>Original English</summary>
Um
Oh,
it
looks
like
it's
finishing
up.
So,
this
is
I
mean
this
is
the
document
that
it
produced.
So,
in
this
case
we're
we're
we're
um
creating
documentation
for
the
sofa
curve.
It's
a
public
uh
model.
So,
we're
not
showing
 any
any
uh
internal
uh
bank
data
here.
Um
and
this
I
don't
know.
Raise
a
hand.
Anybody
Are
there
any
like
quants
in
the
room?
To
review
it?
</details>

这个看起来怎么样？

<details>
<summary>Original English</summary>
How
does
this
How
does
this
look?
</details>

行，[笑声] 好的。嗯，我们之后去找你。不过，你们知道，这是每个模型都必须定期生成的文档。一家大型银行大概有 4000 个左右的模型。它们每年都必须重新撰写文档，呃，对一些大银行来说，这是个每年价值 1000 万到 5000 万美元的问题，而我们在以低得多的成本为他们完成这项工作方面取得了巨大成功。

<details>
<summary>Original English</summary>
Yeah,
[laughter]
all
right.
Well,
we'll
come
we'll
come
we'll
come
find
you
afterwards.
Um
but
but
so
that
you
know
this
is
this
is
this
is
documentation
that
has
to
be
produced
um
regularly
for
every
model.
A
big
bank
has
4,000
or
so
models.
They
have
to
be
re
re
re-documented
yearly
and
uh
this
is
a
this
is
a
a
a
problem
that
is
worth
anywhere
between
10
to
50
million
dollars
a
year
uh
for
some
of
these
bigger
banks
and
and
we're
having
great
success
in
in
um
in
doing
it
for
them
for
for
much
cheaper.
</details>

呃，诚然，让它通过合规、审计和监管机构显然是另一场战役，我相信你们都对此很清楚，但是，嗯，我们可以将其与历史结果进行基准对比。我们可以针对团队完成它所需的时间进行基准对比，呃，我们有现场的宽客能够对这些进行评分，让我们了解这些模型在这方面的表现如何，而且我们发现它的效果——我是说，好得令人吃惊。嗯，而且比传统的呃人工方式便宜得多。

<details>
<summary>Original English</summary>
Uh
granted
there
are
some
some
um
Getting
this
through
compliance
and
the
auditors
and
the
regulators
is
is
another
part
of
the
battle
obviously
as
I'm
sure
you're
all
familiar
with
but
um
we
we
can
benchmark
this
against
historical
results.
We
can
benchmark
this
against
how
long
it
takes
the
teams
to
do
it
uh
and
we
have
quant
you
know
quants
who
are
on
the
floor
who
are
able
to
to
rate
these
and
and
give
us
a
sense
of
how
how
well
the
models
are
doing
on
this
and
we're
finding
that
it's
I
mean
quite
shocking
shockingly
good.
Um
for
for
much
cheaper
than
than
traditional
uh
manual
way
of
doing
this.
</details>

有什么问题吗？任何……

<details>
<summary>Original English</summary>
Any
questions?
Any
like
</details>

>> 让宽客去做宽客擅长的事情。

<details>
<summary>Original English</summary>
>> the
quants
do
the
stuff
that
the
quants
are
good
at.
</details>

>> 建立模型。

<details>
<summary>Original English</summary>
>> Making
the
models.
</details>

>> 而不是处理监管文书，那可能没多少乐趣。我不是宽客，但是——

<details>
<summary>Original English</summary>
>> Not
the
regulatory
paperwork
which
probably
isn't
very
fun.
I'm
not
a
quant,
but
</details>

>> [嗤笑]

<details>
<summary>Original English</summary>
>> [snorts]
</details>

>> 有问题吗？

<details>
<summary>Original English</summary>
>> Any
questions?
</details>

### 对话界面与工作流契约

问得好。呃，是的。所以，实际上，嗯，Raymond 刚才展示了聊天智能体。作为内核的一部分，在某个路径的 markdown 里面埋着我们的最佳实践。这些是你在声明结果时希望去做的事情类型。呃，这些是，嗯，还有反模式，也就是你不应该做的事情。所以，是的，确实存在一种场景，你不用自己去完整手写契约，而是进行迭代，这就是 Raymond 所展示的，呃，利用另一个遵循我们最佳实践指南的智能体，来探讨如何创建契约。但是，是的，我是说，将意图从人们的大脑中提取出来才是困难的部分，而我认为这是其中的一块。这当然不是全部——

<details>
<summary>Original English</summary>
Great
question.
Uh
yes.
And
so,
actually,
um
Raymond
showing
off
the
chat
agent
a
little
bit
as
part
of
the
kernel,
as
buried
in
the
markdown
at
a
at
a
path,
we
have
uh
best
practices.
The
These
are
the
types
of
things
you
want
to
be
doing
when
you're
declaring
out
out
outcomes.
Uh
these
are
um
and
anti-patterns,
things
that
you
shouldn't
be
doing.
And
so,
yes,
there
is
there
is
a
a
world
in
which
you're
not
typing
the
whole
contract
itself,
but
you're
iterating,
and
and
that's
what
Raymond
was
showing
uh
with
another
agent
following
our
best
practice
guide
on
how
to
on
on
how
to
create
the
contract.
But,
yeah,
I
mean,
getting
getting
intent
out
of
people's
heads
is
like
the
hard
part,
and
and
I
think
this
is
a
piece
of
it.
It's
certainly
not
like
the
whole
</details>

>> 是的。关于这个我有个稍微长一点的呃……我不想说太长。我们只有 5 分钟了。不过，关于这个可以说一点更深入的想法，那就是我确实认为这是聊天形态为什么爆发得如此之快的一个很大原因：你不需要对你要寻找的东西有任何了解，直接开始与 ChatGPT 互动，就像生成式人工智能的魔力一样，让它给你反馈，对吧？所以，如果那是——

我不知道 OpenProse 是不是处于那个阶段时的最佳选择，如果你真的甚至不知道自己在谈论的内容是什么形态，或者你甚至不确定自己要找的是什么。

<details>
<summary>Original English</summary>
>> Yeah.
I
have
a
slightly
like
longer
uh
I
don't
want
to
make
this
too
long.
We
only
have
5
minutes.
But,
like,
a
slightly
longer
rant
on
this,
which
is
that
I
do
think
that
this
is
a
big
part
of
why
chat
like
blew
up
so
fast
is
like
you
do
not
need
to
know
anything
about
what
you're
looking
for,
just
start
engaging
with
ChatGPT,
and
just
like
the
magic
of
generative
AI
and
like
having
it
like
come
back
to
you,
right?
And
so,
like,
if
that's
I
don't
I
don't
know
that
OpenProse
is
the
best
place
if
you're
at
that
stage
of
something
where
you
re
you
really
don't
even
know
the
shape
of
what
you're
talking
about,
or
you're
not
even
sure
like
what
it
is
that
you're
looking
for.
</details>

嗯，就像这走——我是个非常老派的 DSPy 用户，我关于 DSPy 的玩笑就像是：“哎呀，不行，我现在必须知道我想要什么了，对吧？”因为 DSPy 的整个核心思想就是你必须为你想要的东西创建签名（signature）。当你看到那样的事物时，你会觉得：“这太棒了。”然后你坐下来，就会发现，噢，我其实根本不知道我想做什么，对吧？

<details>
<summary>Original English</summary>
Um
and
like
this
go
I'm
like
a
very
old-school
DSPy
user,
and
like
my
my
joke
about
DSPy
was
like,
"Oh,
no,
I
have
to
know
what
I
want
now,
right?"
Because
like
the
whole
idea
of
DSPy
is
like
you
have
to
you
create
the
signature
of
the
thing
that
you
want.
And
if
you
and
you
you
you
like
see
something
like
that,
you're
like,
"This
is
so
awesome."
And
then
you
sit
down,
and
you're
like,
oh
I
I
actually
don't
know
what
I
want
to
do
I,
right?
</details>

所以，我觉得对于 Open Prose 来说，它比像 DS fire 这样的工具要宽松得多，后者你真的必须确切说出返回对象的签名，否则什么都不会发生。嗯，但是是的，我想说内置智能体有望能帮忙解决一部分，比如你可以直接开启语音，然后问它：你能做什么？它几乎能做你在应用里能做的任何事情，比如我们——你知道，针对任何涉及花钱的操作，我们都有那种硬编码的确认步骤。显然，我们希望大家通过点击按钮来完成那个。嗯，但是是的，我认为……

我不知道，我认为这也与所谓的“大任务化”（the great jobification）有关，那就是聊天并不是一个极佳的界面，而被强化学习（RLF）训练成具有说服力的聊天伙伴的智能体，对于根本不包含人际对话的工作流程来说，不一定是最理想的 AI 类型。

<details>
<summary>Original English</summary>
So,
I
think
I
think
with
the
you
know,
Open
Prose
is
a
lot
less
strict
than
something
like
DS
fire
where
you
like
you
literally
really
needed
to
say
the
signature
of
the
return
object
or
nothing
happens.
Um
but
yeah,
I
would
say
like
the
built-in
agent
hopefully
can
like
help
with
some
of
like
you
can
just
turn
on
the
voice
and
be
like,
what
can
you
do?
Like
and
it
can
do
almost
anything
you
can
do
in
the
app
like
we
you
know,
we
have
those
hard-coded
like
confirm
things
for
um
for
like
anything
that
would
cost
money.
Obviously,
we
want
people
like
click
a
button
for
that.
Um
but
yeah,
I
think
I
think
it's
um
I
don't
know,
I
think
it's
also
related
to
like
the
great
jobification
is
like
there
are
like
chat
isn't
a
great
um
interface
and
agents
that
are
like
RLF
to
be
convincing
chat
partners
are
not
necessarily
like
the
best
type
of
AI
for
workflows
that
don't
have
human
conversation
as
part
of
them
at
all.
Um
</details>

>> 让我插一句，这就是使用场景的问题，就像我们告诉大家的那样，如果你是在处理一次性任务，你不会想用这个；如果你是在……聊天工具就非常适合那种场景，如果你处于探索模式的话。

这个工具适合的是你需要频繁执行的事情。它需要可靠，必须可重复，必须可审计。

这类工作流程才是 Open Prose 所构建和面向的目标，因此这里面隐含着一个前提，那就是你确实知道自己需要什么。

<details>
<summary>Original English</summary>
>> And
let
me
let
me
interject,
which
is
just
use
cases
like
we
tell
people
you
don't
want
to
use
this
if
if
you're
doing
a
one-off,
if
you
are
like
chat
is
perfect
for
that.
You're
if
you're
in
exploratory
mode.
What
this
is
good
for
is
something
you
need
to
do
a
lot.
It
it
needs
to
be
reliable,
it
has
to
be
repeatable,
it
needs
to
be
auditable.
Those
types
of
workflows
are
what
what
we're
what
Open
Prose
is
built
for
and
meant
for
and
so
there
is
an
implicit
like
you
do
know
what
you
need
in
in
here.
</details>

>> 哦，我们有一位真正的宽客提问了。

<details>
<summary>Original English</summary>
>> Oh,
we
got
a
question
from
a
real
quant.
</details>

>> 刚才我提到了——我不会只把它称作继承，我会称之为组合。所以，事实上，框架以及模式本身的一个核心特性，就是专为组合而构建的。因此，向同一次运行中注入多个契约，使智能体必须同时满足其中的许多契约，这在这里是一个核心部分。另一半，也就是事件驱动的那一半，可能看起来有一点点像你所谓的继承。我更多觉得它像……呃，我不知道你们是否熟悉类似 React 风格的记忆化（memoization），即你拥有某些组件。这仍然是组合。你拥有某些带有上游依赖项的组件，当其中一个的数据发生变化时，它自然会向下传递到它下方的所有内容。

嗯，那也是 Jev 让人超级兴奋的另一个方面，决策模型也超级令人兴奋，因为我们之前构建了那个——

<details>
<summary>Original English</summary>
>> And
earlier
I
alluded
to
and
I
I
wouldn't
just
call
it
inheritance,
I
would
call
it
composition.
So,
we
we
in
fact
a
core
feature
of
of
the
framework
and
and
the
the
pattern
itself
is
it's
built
to
be
composed
and
so
yes,
injecting
multiple
contracts
into
the
same
uh
run
in
in
which
the
agent
now
has
to
satisfy
many
of
them
is
is
is
a
a
core
piece
here.
The
other
half
the
event-driven
half
uh
which
maybe
looks
a
little
bit
you
might
call
it
inheritance.
I
I
think
of
it
more
like
um
uh
I
don't
know
if
you're
familiar
with
like
React
React-style
memoization
where
you
have
certain
components.
It's
still
composition.
You
have
certain
components
that
have
upstream
dependencies
and
when
the
data
on
on
one
of
them
changes,
it's
of
course
going
to
trickle
down
to
everything
below
it.
Um
that
is
another
place
where
Jev
is
super
exciting
and
and
the
decision
model
super
exciting
because
we
had
built
that
</details>

<!-- chunk 6/6 -->

系统，并且我们曾经让智能体尝试去判断状态是否发生了改变，如果上游依赖的状态发生改变，我们是否要触发下游依赖？

额，但那样运行起来非常昂贵，而 Jev 突然就成了一个非常廉价的语义分类器或语义记忆器（semantic memoizer），你可以把它看作是一个缓存，由 Jev 来决定某些东西何时过期，然后触发它下游的一切。所以，这是该框架的另一种核心组件。除去 Jev 这部分，我们目前仍在这个部分中构建。是的，这里面没有任何魔法。全都是纯英语。全都是纯语言。

额是的，不过是的，这就是组合、可组合性的体现之处。

<details><summary>Original English</summary>system and we had agents trying to determine has the state changed and if the state on upstream dependency changes, do we kick off downstream dependency?

Uh but that's very expensive to run and Jev becomes suddenly this very cheap like semantic classifier or semantic memoizer, which you could think of it as like a cache and Jev is deciding when something is out of date and now it kicks off everything downstream from that. So, that's another kind of core component of of the framework. Minus the Jev part, we're still working we're still building that part in. Yes, and there is no magic here. It's all just English. It's all just language.

Uh yeah, it's but yes, and that's where the composition composability comes in.</details>

>> 就你的观点而言，另一部分在于它不仅仅是一个模板。所以，显然即便在 LLM 出现之前，你也可以——或者说在非常，比方说并非非常早期的 LLM，甚至像编码器（encoders）就能为你填充一个模板。就像你在模板前加上前缀，然后把那东西填上。但在这里，情况就像是，“那么，你能模板化什么呢？”所以，你可以将整个多智能体工作流模板化。举个我常给的简单例子，你可以说我需要的输出是一篇文章。

你知道，也许它属于这种类型的文章，长度大概是这样，诸如此类，对吧？围绕它的一些约束。

而输入就像是主题。比如直到你为我搞定一篇好文章，并且由父级智能体来决定好不好，由它决定何时退出，所以这就是为什么用更强的模型会比弱模型得到更好的结果。我有一个研究员子智能体。那个智能体拥有我的 access CLI 以及关于如何使用 CLI 的 access skill，因为我不想让它随便用什么随意的网络搜索。我有一个写作者子智能体，它拥有我特别的……比如这里有我写的最后 10 篇非常棒的文章，我希望你像这样写。我还有一个文字编辑子智能体，而整套东西可能就……

<details><summary>Original English</summary>>> The other piece to your point is like it's not just a template. So, like you could obviously even pre-LLMs, you could have

um or very let's say not very early LLMs or even like encoders could like fill a template for you. Like you like prefix the template and like fill the thing. But here it's like, "Well, what can you template?" And so, you could template the entire multi-agent workflow. So, like this the simple example that I give is you could say like the output that I need is an article.

You know, and maybe there's it's got like this type of article, it's going to be this length, whatever, right? Some constraints around that.

And the input is like the topic. Like until you've got a good article for me, and the parent agent decides good, it decides when to exit, so that's where you're going to get a better result with a stronger model than a weaker one. I've got a researcher sub-agent. That agent has my access CLI and my access skill on how to use a CLI cuz I don't want it, you know, using any random web search. I've got a writer sub-agent that has my special like here's the last 10 articles I wrote that are really good, and you I want you to write like this. I've got a copy editor uh sub-agent, and that whole thing is just maybe</details>

>> 但这里真正需要强调的重要部分是契约的组合，大概就是 100 行 markdown，而他们可能需要花上 10 个小时去完成它。

<details><summary>Original English</summary>>> But the really important 100 lines of markdown, and it might take them 10 hours to do it.</details>

>> 强调其中的重点在于契约的组合，在这个过程中，你去找……我的意思是，这些东西早就存在了。任何、任何、任何工作流构建器，拖拽式的工作流构建器。

这是一种不同的思考方式，因为当你从契约的那个 DAG（有向无环图）的角度来思考时，你可以拥有中间步骤，你几乎可以把它们当作检查点，或者像……

这个中间步骤满足了契约，事情在推进，它达到了这个契约并达成了它，接着这又促使下一个步骤继续进行，直到完成那个契约。所以，你可以在某种程度上声明“如何到达那里”，仅仅是通过沿途组合这些中间契约，同时依然让智能体在如何达成那个中间步骤上保留一点灵活性。

<details><summary>Original English</summary>>> important parts to emphasize there is is the contract composition where so you you you go to like, I mean, these things have been around forever. Any Any Any workflow builder, drag-and-drop workflow builder.

That's a different way of thinking about this because when you think about this in terms of that like DAG directed acyclic graph of contracts, you can have intermediary steps that you almost think of them as like checkpoints or like

this intermediary step meets the contract, and the thing is going, and it hits this contract and fulfills this one, and then that causes the next one to keep going until it's fulfilled that contract. So, you can you can still in some ways declare the how to get there just by composing these intermediary contracts along the way and still letting the agents be a little bit flexible on on how to do achieve that intermediary step.</details>

### 工作流形态与执行环境

>> 是的，还有它的形态。举个例子，当 Claude 动态工作流发布时，他们写了一篇博客文章，里面列出了六种类型，对吧？其中一种类似于扇出（fan out）、扇入（fan in），就像配合子智能体进行 map reduce。其中一种类似于对抗性审查，一种类似于循环直到满足 X 条件，对吧？所有这些东西你都可以在一段散文程序（prose program）中表达出来，然后在任何智能体上运行。所以，你可以……

就像你无需任何代码就能将多智能体工作流的形态模板化。额，再次说明，这之所以成为可能，完全是因为智能体本身擅长自我管理，并且大多数 harness 都支持子智能体。所以，如果你运行的是纯原生的 pie（plain vanilla pie），它至少在我上次看的时候是没有子智能体的，你若要它处理那种更复杂的这类工作流，就会想要子智能体。不过，基本上任何具备以下要求之一的 harness……

<details><summary>Original English</summary>>> Yeah, and and the shape of it. So, like one one example like when Claude um the dynamic workflows came out, they had this blog post that's like, here's the six types, right? And it's like one of them's like fan out, fan in, and like a map reduce with sub agents. One of them's like a adversarial review, one's like a loop until X condition is met, right? And all of those things you can express in a prose program and then run them on on any agent. So, you can

like you can template the shape of the the multi-agent workflow um with no code. Um and again, the whole it's only possible because the the agents are like good at managing themselves and because most harnesses have sub agents. So, like if you're running plain vanilla pie, which has no sub agents at least last time I checked, you're going to want sub agents for it to do that more complex kind of workflow. But, like essentially any harness that has one of the requirements,</details>

>> 子智能体。

<details><summary>Original English</summary>>> Sub agents.</details>

>> 对大多数来说，子智能体几乎是唯一的……

<details><summary>Original English</summary>>> sub agents is pretty much the only one for most</details>

>> 上下文。

<details><summary>Original English</summary>>> context.</details>

>> 是的，比如 bash 和子智能体其实……你甚至都不需要 bash。我们也可以在代码模式下将这些运行在虚拟机隔离环境中。所以……

<details><summary>Original English</summary>>> Yeah, like um like bash and sub agents are actually you don't even need bash. We can run these in VM isolates in code mode, too. So,</details>

>> 还有其他问题吗？我们可以把这 10 分钟还给大家。额，这是基于我多年的工程经验，以及与人打交道的经验——有些人有时不太擅长表达需求，而另一些人则非常擅长表达需求。而且这也是，我的意思是，我们在内部对这些进行了基准测试，并针对……我们有一种类似于演化算法的机制，通过观察它们是否能符合要求来缩小内核（shrink the kernel）。所以，这是基于实践和实证结果的。额……

<details><summary>Original English</summary>>> Any other questions? We can give 10 minutes back to everyone. Uh it is based on my many years of engineering experience and dealing with people who sometimes are not very good at expressing requirements and other people who are very good at expressing requirements. And it's also, I mean, we we benchmark these internally and and run them against we we have sort of an evolutionary algorithm where we can shrink the kernel by seeing if if they can conform to that. So, it's based on practice and empirical results. Uh</details>

>> 是的，你可以直接把它当作一份规范，你也可以比如假定你喜欢 Matt Pocock 的规范，你知道，你喜欢 Matt……我专门做了一个有趣的就为了调侃他，名字叫 auto Pocock，基本上那是我用来证明自己接入技能（skills）的方式可行的一种手段。

所以，你基本上就是……他有一个类似“grill me”的工作流，你知道，然后问所有这些问题，接着是 TDD，然后是所有其他那些，你可以把整套东西放进一个散文程序里，直接要求“执行 Matt Pocock 的工作流”，并且每个子智能体在程序的每个阶段都必须加载序列中的下一个技能。额，所以是的，你完全可以像……

<details><summary>Original English</summary>>> Yeah, you can just have that as a spec and you could have like let's say you like um uh Matt Pocock's like uh spec, you know, you like Matt I built a funny one just to like troll him that was like auto Pocock and it basically it was my way of proving that my way of wiring skills in works.

So, you basically just he has a workflow that's like grill me, you know, and then you ask all these questions and then it's like TDD and then all these other ones and you can put the whole thing in one prose program and just be like do Matt Pocock's workflow and every sub-agent has to load at every stage of the program you have to load this the next skill in the sequence. Um so yeah, you can absolutely like</details>

>> 确实有人……我之前没有称它为光谱驱动开发（spectrum driven development），但由于其自身特性，它几乎就是光谱驱动开发。我很希望你能试试这个。试试看，或者散会后找我，无论你有什么光谱驱动开发的规范，我们都可以将它与引导内核散文运行（boot kernel prose run）组合起来，然后看看效果如何。我认为它实际上会表现得相当不错。

那是个很好的启发。我还没有用光谱驱动开发契约尝试过它。我很乐意坐下来试一试，看看它是会覆盖它，还是会开始产生冲突。

<details><summary>Original English</summary>>> do have people I I wasn't calling it spectrum driven development, but like almost by its very nature it is spectrum driven development. I'd love you to try this out. Try it or come find me after and like whatever spectrum driven development specification you have, we could compose with the boot kernel prose run and then we'll see how it does. I I think it would do quite well actually.

That's a good good inspiration. I haven't tried it with the spectrum driven development contracts. Like I'd love to sit down and and and try it and see if it overrides it or if it starts colliding.</details>

>> 那会很有意思，比如……

<details><summary>Original English</summary>>> That'd be interesting like um</details>

>> 这里有，这里有一个……

<details><summary>Original English</summary>>> Here's Here's one</details>

>> 看看不同的技能在多大程度上会干扰它。

<details><summary>Original English</summary>>> See how much different skills like throw it off.</details>

>> 这里有一点我们确实具备，并且有软件工程师在使用 Open Prose 来开发软件。

额，我们的用户中，更多的人是在使用 Open Prose 来做运维（ops）、产品管理、量化模型文档以及非……我不知道，非软件工程类的事情。额，我认为仅仅是因为像 markdown 文档这种融合方式，结果反而对非工程师来说更有吸引力。是的。

还有其他问题吗？

谢谢大家。

感谢各位的时间。

<details><summary>Original English</summary>>> Here's one thing we do have and software engineers using Open Prose to develop software.

Uh

more of our users are using Open Prose to do ops and product management and um quant model documentation and non I don't know software engineering stuff. Uh I think it's just the blend of like markdown documentation actually is more interesting to non-engineers um as a result. Yeah.

Any other questions?

Thank you all.

Appreciate your time.</details>

>> [掌声]

<details><summary>Original English</summary>>> [applause]</details>