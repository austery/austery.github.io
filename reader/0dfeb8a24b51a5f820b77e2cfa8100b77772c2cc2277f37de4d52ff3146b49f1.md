---
author: How I AI
date: '2026-05-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2wLJl9A2CnA
speaker: How I AI
tags:
  - autonomous-ai
  - goal-setting
  - ai-workflow
  - product-management
  - software-development
title: Codex的`Goal`功能：实现AI长时间自主任务的实践与影响
summary: 本期节目深入探讨了Codex中的`Goal`功能，展示了它如何让AI从简单的回合制交互转变为能够自主规划、执行、验证并完成复杂、长时间任务的强大工具。通过对比`Prompt`与`Goal`的差异，阐述了构建有效`Goal`的六大核心要素，并提供了技术（如零误差策略）与非技术（如邮件清理、任务管理）领域的实际应用案例。文章还讨论了`Goal`功能对软件质量、产品管理以及人机协作模式的深远影响，强调了从“构建者”向“管理者”角色转变的趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Mercury
  - Sentry
  - Vercel
  - Linear
products_models:
  - Codex
  - GPT
media_books: []
status: evergreen
---
### AI自主任务的新范式：从指令到目标

欢迎回到“我如何AI”。我是Claravo，一位产品负责人和AI狂热者，致力于帮助大家更好地利用这些新兴工具进行构建。今天，我将向大家详细介绍我近期最喜爱的AI产品——Codex中的一项顶级功能：“目标”（Goals）。如果你一直在疑惑时间线上的那些人是如何让他们的AI实现“通宵运行”或处理极其复杂的长时间任务，那么“目标”就是答案。我们将深入探讨它是什么、我如何使用它，以及一些技术和非技术场景的应用案例，即使你不是程序员也能从中获益。

<details>
<summary>Original English Source</summary>

Welcome back to How I AI. I'm Claravo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today, I'm going to walk through my favorite feature in my most recent favorite AI product, goals in codecs. If you've been wondering how all these people on the timeline are getting their AI to run quote unquote overnight or handle very complex longunning tasks, I'm going to show you goals is the answer. We're going to walk through what it is, how I might use it, and a technical use case along with some non-technical examples of how goals can help you even if you're not coding. Let's get to it.

</details>

### AI与传统编程的金融支持

（广告）本期节目由Mercury赞助。作为一名AI领域的创始人，我需要持续追踪运营成本、关注营收增长、按时支付供应商并确保款项及时入账。Mercury让这一切变得轻而易举。它的应用程序设计精美，界面和功能都达到了现代软件的标准——这听起来理所当然，但在银行业务领域却并非如此。我最常用的是其账单支付功能，对于供应商款项的处理既清晰又便捷。无论是电汇、转账，还是接收客户付款、资金流转，Mercury都使其操作变得异常简单。你需要的一切都触手可及，无需电话沟通，无需在复杂的菜单中摸索，也无需担忧交易是否成功。我深知自己对工具栈中的其他部分进行了大量优化，而Mercury是那个我完全无需费心的工具，它就是好用。访问mercury.com了解更多详情，并可在几分钟内在线申请。Mercury是一家金融科技公司，而非FDIC承保银行。银行服务由Choice Financial Group通过Column NA（FDIC成员）提供。

<details>
<summary>Original English Source</summary>

This episode is brought to you by Mercury. As an AI founder, I'm constantly tracking run rate, watching revenue growth, paying vendors, and making sure I'm getting paid on time. Mercury makes all of it feel effortless. The app is genuinely beautiful. It actually looks and works like modern software, which sounds obvious, but apparently isn't when it comes to banking. What I use it for the most, bill pay for my vendors is just clean and easy. And wires and transfers, getting paid from clients, moving money. Mercury makes it so simple. Everything you need is right there. No phone calls, no hunting through menus, no wondering if something went through. I think about how much I've optimized every other tool in my stack. Mercury is the one where I don't have to think about it at all. It just works. Visit mercury.com to learn more and apply online in minutes. Mercury is a fintech company, not an FDIC insured bank. Banking services provided through Choice Financial Group in column NA members FDIC.

</details>

### “目标”与“提示”：AI交互模式的根本转变

在我深入讲解如何使用“目标”功能之前，我想先解释一下“目标”究竟是什么，以及何时适合使用它，何时不适合。我正在参考OpenAI开发者团队的一篇博客文章，题为《在Codex中使用目标》。这篇文章中首先展示了一个非常棒的图表，清晰阐述了**提示**（Prompt）和**基于目标的循环**（Goal-based Loop）之间的区别。

你们都熟悉**提示**（Prompt），它是一种回合制的请求模式。你向**大型语言模型**（Large Language Model: 基于海量文本训练的AI系统，简称LLM）、AI模型或其驱动框架发出指令，它执行任务，返回结果，然后等待你再次发出提示。如果你像我一样，在编码工具中最常说的一句话就是：“好的，下一步是什么？”然后它告诉你，你再回复：“太棒了，去执行吧。”如果你发现自己正处于这种反复微管理AI的过程中，那么Codex中的`/goal`命令可能是一个值得添加到你工具箱中的利器。

那么，回合制的一问一答模式与“目标”有何不同？当你在Codex中设定一个**目标**（Goal）时，它实际上拥有了一个可以持续努力实现的方向。它会不断地循环执行下一步、验证，直到能够衡量出目标已达成。因此，如果你观察这个过程，“目标”是模型希望达成的结果的总体描述，它会执行任务，检查其工作，决定下一步，并持续这个三步过程，直到收集到证明目标已达成的证据。一旦证据确凿，它会将该目标标记为完成，并通知你任务已结束。

如果你在线上看到人们讨论如何让Codex、Claude Code等工具实现长时间的自主任务，他们实际上都在使用某种“目标”框架。还有一种被称为“Ralph循环”的版本，其功能框架是相同的：即“持续执行，直到某个行为或结果得到验证。否则，就重新提示自己，不断循环，直到达成目标。”

<details>
<summary>Original English Source</summary>

Before I go into how to use goal, I want to talk about what goal is and when it's appropriate and when it's not the right tool for the job. So, I'm looking at this blog post by the OpenAI developers team. It's called using goals in codecs. And the first thing that they have in this blog post is this awesome diagram that talks about the difference between a prompt and a goal-based loop. And a prompt, you all are used to this. It's sort of the turnbased request that we're all used to. You ask the LLM, the model, the harness to do something. It works. It returns to you its result and then it waits for you to prompt it again. If you're like me, the number one thing that you're saying in your coding tool is okay, what's next? And then it tells you and you say, great, do it. If you find yourself in that process, using /goal in codeex might be a tool that you want to add to your toolkit. So what's the difference between this turnbased one response weight and goal? Well, with goal, when you give codeex a goal, it actually has something that it can work towards and it will continue to loop to the next step and verify until it can measure that it has met that goal. And so if you look at this, the goal is the overarching kind of description of the outcome that the model wants to get towards and that will work. It will check its work. it will decide the next step and it will continue that three-step process until it can gather evidence that it has met the goal. Once it gathers evidence that it has met the goal, it will mark the goal as complete and then it will tell you it is done. Now, if you've been watching and people online talk about how they get these longunning autonomous tasks out of codeex, claude code, etc. you're really talking about people who are using some framework of this goal. There's also a version of this called a Ralph loop that people were talking about, but functionally the the framework is the same. It's saying keep going until X behavior or Y outcome is validated. Otherwise, I want you to reprompt yourself and reprompt yourself until you're there.

</details>

### 实现长时自主任务：`/goal` 的核心价值与管理

令人着迷的是，我使用AI编码代理已有多年，但在Codex和“目标”功能出现之前，我从未能实现这种**多小时长时间自主任务**（Multi-hour Long-running Autonomous Tasks）。当然，我的编码任务并非世上最复杂的，我没有在构建操作系统，也没有进行复杂的数学运算。因此，我的问题范围相对受限。但我确实有一些我认为长时间运行的AI驱动框架能真正帮助我的任务。然而，在`/goal`成为Codex工具的一部分之前，我真的无法让我的AI充分自我管理以长时间自主地完成这些任务。但当我第一次使用“目标”时，我实际上能够让一个编码任务运行大约5小时45分钟，这是我之前从未有过的长时间运行记录。

接下来快速介绍如何使用“目标”功能。管理“目标”生命周期大致有四种方式：
1.  **`/goal [你的目标]`**：这是我最常用的方式，输入目标后我就走开。它会开始工作。
2.  **`/goal`**：再次查看当前目标。
3.  **`/pause goal`**：暂停目标。
4.  **`/resume goal`**：恢复目标。
5.  **`/remove goal`**：移除目标。

所以，你不需要让AI运行6小时、12小时甚至24小时，如果它偏离了轨道，你完全可以管理它的生命周期。这是一个非常有用的工具。我非常喜欢他们在此处提供的例子，因为它百分之百符合我大部分时间的工作状态。他们说，当你发现自己每次交互后都在重复相同的话，比如“继续”、“尝试下一个”、“再运行一次”、“现在运行测试”、“继续直到完成”时，你就应该使用“目标”功能。如果你在微管理AI，不断地拍拍它肩膀说：“请你继续下一步好吗？”那么“目标”就是为你准备的。

<details>
<summary>Original English Source</summary>

And what's really fascinating about goals, I've been using, you know, AI coding agents for many years now and until codeex and goal, I was not able to get these multi-hour longunning autonomous tasks. Now, I don't have the most complex coding tasks in the world. I'm not building an operating system. I'm not doing complex mathematics. And so, part of that was my problems were pretty well constrained. But I did have things that I thought a longunning harness could really help me with. But until slashgoal was part of the codeex tool, I really just wasn't able to get my AI to self-manage enough to do that autonomously over time. But the first time I used Goal, I was actually able to get a coding task running for about 5 hours and 45 minutes, which is longer than I've ever had anything run before. Now, quick introduction on how to use goal. There are four sort of ways to manage the life cycle of goal. The one that I use is slashgoal and then I walk away. So if you write write slashgoal and then prompt it with your goal, it will start working. You can use slashgoal to see what the current goal is again. Uh you can pause the goal, you can resume the goal, and then you can remove the goal. So you know, you don't have to let your AI run for 6, 12, 24 hours, whatever. If it gets off the wrong track, you can absolutely manage the life cycle. But it's a really useful tool. And I love that they give the example here because this is 100% what I spend most of my time going. They say you really want to use goals when you would otherwise find yourself saying the same thing after turn like keep going, try the next thing, run it again, now run the test, continue until it's actually done. So if you're micromanaging your AI and having to tap it on the shoulder and say, can you pretty please go to the next step? Goal is for you.

</details>

### 精准定义目标：构建强大的AI任务的关键

那么，如何提示和设计一个真正的“目标”呢？产品经理们请注意，撰写**成功标准**（Success Criteria）的工程师们也请注意。这正是制定可衡量、明确目标的核心技能发挥作用的地方。当你提供一个**提示**（Prompt）时，你通常只是说“做这个任务”，比如“重写这段代码”、“重新设计这个页面”等等。但当你谈论一个**目标**（Goal）时，你希望描述的是如果该任务成功，会达成什么样的**结果**（Outcome）。

OpenAI在这篇博客文章中提供了一个技术示例：**降低P95结账延迟**（Reducing P95 Checkout Latency）。如果你知道某个页面加载速度较慢，并且你想将其降低到某个阈值以下，而且这个过程是可衡量的（因为你可以反复加载结账页面进行测试），并且你为它设定了**防护栏**（Guard Rail），比如“保持正确性套件通过”，那么这是一个非常棒的目标。它**可衡量**（Measurable），**可测试**（Testable），拥有**防护栏**（Guard Rail），并且存在AI可以成功执行的**可执行表面区域**（Executable Surface Area）。

编写目标本身就是一种技能。OpenAI提供了一个非常棒的纲要，说明了如何构建一个强大的目标。再次提醒产品经理们，请注意：如果你曾撰写过OKR（Objectives and Key Results），或者开发者们，如果你曾质疑过某个OKR是否撰写得不够好，那么这些技能现在就能派上用场。最强大的目标——适用于任何事，但对于Codex而言尤其重要——通常包含六个要素：
1.  **结果**（Outcome）：工作完成后，什么应该成为事实？我们希望实现什么结果？
2.  **验证**（Verification）：你如何测试它？你是否有测试套件？是否需要拉起浏览器？是否有一个你想要达到的数字或衡量标准？
3.  **约束**（Constraints）：在Codex工作时，什么不能退步？例如，在我们的P95结账延迟案例中，你可以删除页面，延迟就会消失，但这并非你所期望的。所以，你需要约束，你希望功能保持不变，特定的技术保持不变。
4.  **边界**（Boundaries）：为了实现这个目标，它被允许使用哪些工具、文件和资源？
5.  **迭代策略**（Iteration Policy）：它应该如何决定下一步尝试什么？你接下来会尝试什么？
6.  **停止条件**（Stop Condition）：何时它应该停止并说：“抱歉，我无法继续了。我没有好的下一步想法了。”

他们提供了一个很棒的模式：`/goal`，即“我的**终态**（End State）由特定证据验证，我需要你保留这些约束，请在迭代之间使用这些工具。通过执行X、Y和Z来决定下一步。如果遇到阻塞或没有有效路径，你下一步应该做的是：告诉我，报告，寻求我的帮助。”

<details>
<summary>Original English Source</summary>

Now, how do you prompt and design a real goal? This is where product managers tune in. Um, engineers that write success criteria tune in. These are where those skills on setting really measurable, well-defined goals come into play because when you prompt something, you're really just saying do this task, right? Like rewrite this code, redesign this page, etc. When you're talking about a goal, you want to talk about what the outcome is. if that task was successful. And the technical example that they give here in this blog post is reducing P95 checkout lat latency. So if you know that a specific page is loading kind of slow and you want to reduce that below a threshold and you know that can be measured because you can just load the checkout page over and over and over again and then you create a guard rail on it like keeping the correctness suite green. That is a really great goal. It's measurable. It's testable. It has a guard rail on it. And there's a executable surface area that you know an LLM can be successful for. Writing goals is its own skill set. But OpenAI has given a really great outline to what makes a strong goal. And again, product managers, let's pay attention. If you've written an OKR, uh developers, if you've argued that an OKR was not well written, this is where those skills come into play. The strongest goals I mean for anything but in particular for codeex kind of have six things as part of it. It has an outcome. What should be true when the work is done? So once we're done, what is the outcome we're trying to deliver? Verification. How can you test it? Do you have a test suite? Do you need to pull up the browser? Is there a number that you're trying to go to or a measure constraints? What can't regress while codeex works? For example, on our P95 checkout latency, you could delete the page. The latency goes away, but that's not what you want. So, you want constraints. You want the features to stay the same. You want particular technologies to stay the same. the boundaries, so what tools and files and things it's allowed to use in pursuit of this goal, the iteration policy, how it should decide what to try next, kind of what would you try next, and then when it should stop and say, "Sorry, I just can't continue. I don't have a good next idea." And they give this great pattern here, which is slashgoal, you know, my end state verified by specific evidence. I need you to preserve these constraints. Please use these tools between iterations. Decide the next step by doing X, Y, and Z. And if you're blocked or no valid paths remain, this is what you should do next. You should tell me. You should report. You should ask me for help.

</details>

### 结合六要素：优化P95结账延迟的AI目标范例

他们提供了一个如何更好地实现P95结账延迟目标的示例。基本上，它是通过设定一个阈值来实现（这在原始提示中已有体现），但你会通过**结账基准测试**（Checkout Benchmark）来验证它。你会**保持正确性套件通过**（Keep the Correctness Suite Green）。你将**仅使用结账系统**（Only Use the Checkout System）。在迭代之间，你会告诉我**发生了什么变化**（What Changed）、**基准测试显示了什么**（What the Benchmark Showed），以及**下一步要尝试的实验**（The Next Experiment to Try）。如果想不出其他办法，就**停止并向我提供证据、阻塞点以及你需要我做什么**（Stop and Give Me the Evidence, the Blocker, and What You Need from Me）。这是一个非常棒的目标。

<details>
<summary>Original English Source</summary>

And so they give an example of how to make this P95 checkout latency goal a lot better. It's basically by saying bring it below a threshold which was already in the original prompt, but you're going to verify it by the checkout benchmark. You're going to keep the correctness suite green. You're going to use only the checkout system. Between iterations, you're going to tell me what changed, what the benchmark showed, and the next experiment to try. And if you can't come up with something else, stop and give me the evidence, the blocker, and what you need from me. This is a really great goal.

</details>

### 错误日志清零：AI在Chat Purity中的技术实践

这是一个技术目标，但你也可以将其应用于非技术项目。我将向你展示它是如何运作的。所以，再说一次，“目标”是一种全新的提示**大型语言模型**（Large Language Model: LLM）的方式，例如Codex，使其能够自主地在一个“工作-验证-检查”的循环中运行，直到达成目标。编写“目标”与编写“提示”有很大的不同。**提示**（Prompt）是关于“做什么”的指令，而**目标**（Goal）则是对“良好结果是什么”以及“如何达到该结果”的描述。我看到Codex能够长时间运行这些目标。

我将举几个如何使用“目标”的例子，以及我认为它们最有用之处和我的成功案例。我将向你展示幕后发生的一切。我有Chat Purity项目。在Chat Purity中，我们的主AI写作循环中有一个**工具调用**（Tool Call）。它编辑**产品需求文档**（Product Requirements Document: PRD）的特定部分。这是一个基于差异的编辑器，非常复杂，它会在文档中查找**操作范围**（Operation Ranges），然后尝试编辑这些范围。我们收到了大量的错误。你可以看到，由于找不到正确的操作范围，在应用特定编辑时出现了大量错误。如果这让你觉得无聊，可以略过。但由于我们创建的文档很复杂，里面包含表格、项目符号、粗体、引用、图像，所以精确地从AI中获取**节点范围**（Range of Nodes）真的非常困难。我们不断看到这些错误反复出现。我们可能会找到一个特定文档中出现错误的原因，修复它，然后又出现另一个错误。这就像卡通片里那样，你堵住一个地方，另一个地方又开始喷水。这让我们抓狂。你可以看到，这些错误基本上在四月底、五月初的时候消失了。为什么消失了？我们利用“目标”解决了这个问题。

为了解决这个特定问题，我使用的目标是：我让Codex访问了**Sentry**（Sentry: 错误监控平台），并访问了这些编辑请求。我给出的指令是：`/goal`，Codex，**遍历Sentry中所有关于编辑工具上无效操作的例子和追踪记录，对问题进行分类并修复它。然后，回放所有曾出现相同问题的Sentry事件，直到你修复了所有问题，并且所有历史上的“编辑无效操作”的例子都得到解决**。

Codex就开始行动了。它会挑选一个例子，找出根本原因，然后实现针对该根本原因的修复。接着，它会运行所有其他例子，看看有多少错误被“消除”。如果仍有剩余，它会挑选下一个，进行修复，再运行所有剩余的例子，不断“消除”，直到所有错误都清零。现在，我们确实没有留下任何错误。这个过程花了几个小时。最棒的是，最后我得到的不是一堆零散的“创可贴式”的修复，而是**一个系统性的修复方案**（Systematic Fix），它将所有例子整合到一个更智能的框架中，用于如何应用编辑。最终，从我们使用“目标”功能以来，我们再也没有遇到过编辑错误。

<details>
<summary>Original English Source</summary>

And this is a technical goal, but you can also do this with nontechnical projects. And I'm going to show you a little bit of how that works. So again, a goal is a new way to prompt a LLM, in this instance, codeex, to work autonomously in a loop of work, verify, check until it hits a goal. Goals written are a lot different than prompts. Prompts are an instruction of what to do. goals as a description of what a good outcome is and how to get to that outcome. And then I've seen Codeex be able to run these goals for a very long time. So, I'm going to give a couple examples of how to use goals and what I think they're most useful for and some successes I've had with goals. And I'm going to kind of show you behind the scenes. I have chat purity. And in chat purity, we have a tool call in our main AI writing loop. and it edits specific parts of a PRD and it's this diff based editor. It's very complicated and it looks for operation ranges inside a document and then tries to edit those operation ranges. And we were getting tons of errors. You can see here tons of errors on applying specific edits because it couldn't find the right operation range. I'm just going to again, you know, tune out if this is boring to you. But because the documents we created were complex, they had tables in them, they had bullet points in them, they had bold, they had quotes, they had images, actually precisely getting a range of nodes from the AI was really, really hard. And we were just seeing a bunch of these errors over and over again. And we would like find one example of why an error showed up in a very specific document, fix that, but then another one popped up. So, it's like that cartoon where like you plug your finger over here and another spout goes off. And it was driving us crazy. You can see here. And then you can see basically the end of April, the beginning of May, they went away. Why did they go away? Well, we used goal to knock this out. So, the goal that I used to solve this particular problem is I gave Codeex access to Sentry. I gave Codeex access to these edit requests. And I said slashgoal codeex go through every example in sentry, every trace in sentry of an invalid operation on the edit tool. Categorize that issue and fix it. Then replay all of the century events that would have shared that same issue until you have fixed every issue and every historical example of an edit invalid operation is solved and it went to town. So what it would do is pluck one example. It would see what the root cause was. It would implement a fix for that root cause. It would then run through all the other examples to see how many of those it burned down. It would have some remaining. It would pluck the next one. It would do the fix. It would run through all the remaining examples. Burn it down. Burn it. Burn it. Burn it down. Burn it down. Burn it down. And then look what we have. We have literally zero errors left. Now, this took several hours. And what was really nice is at the end of it, I didn't get like these band-aid fixes all over our edit code. What I got was a systematic fix that integrated every example into a more intelligent framework for how edit should be applied. And ultimately, we've had zero edit errors from the time that we use goal here.

</details>

### 实时演示：利用Goal消除Vercel错误

这是一个非常好的例子，但我们来现场演示一下，因为这就是“我如何AI”。我将再举一个例子，说明我如何再次将这个功能用于一些更偏技术性的人群。这些是**Vercel**（Vercel: 云开发平台）的错误。它看起来比实际更可怕。我们围绕它进行了大量的重试，但这里是幕后发生的错误，我们必须在主聊天中进行恢复，并且是过去两周的错误。我想对这些错误做同样的事情。我想对Codex说：**找出这些错误，对其进行分类，部署修复方案，根据现有数据进行验证，直到基本上不再有这些错误为止**。

所以我将拉起Codex，我将使用GPT模型（这里是指“GPT 5.5 medium”），因为这并不是一个复杂的深度思考问题。我将输入目标：**消除API chat v2.2端点在Vercel日志中显示的所有错误，方法是遍历每个错误类别，识别根本原因，确定这是否是用户可见错误。如果是，确定根本原因并为修复开一个分支并提交PR。如果不是，将此错误降级为警告。一旦过去两周的所有日志都能处理完毕，请向我报告所有需要审查的PR以及无法修复的问题，或者你需要我提供什么帮助**。

这听起来像是一个糟糕的提示，但实际上效果不错。这显然比我通常写的**目标提示**（Goal Prompt）更好，因为它明确了成功状态是“我们没有用户可见错误，也没有应该降级为警告的后端错误。”

我按下回车键。它压缩了我的技能描述，但这没关系。现在，Codex已经与我的Vercel插件连接。所以，它能够访问这些日志。它正在制定一个计划。我想暂停一下，告诉大家“目标”是如何与计划一起工作的。一旦它有了一个目标，我看到它会制定一个三到五步的计划。所以，它将**盘点当前代码库**（Inventory the Current Repo），**拉取过去两周的Vercel错误并按类别分组**（Pull the Last Two Weeks of Vercel Errors and Group by Category）。它将**把它们分类为用户可见错误**（Classify Them as User-Facing Errors），然后**按类别实施并验证修复，或降级为警告**（Implement and Validate Fixes or Downgrade Warnings by Category）。最后，它将**发布PR并向我报告**（Publish the PRs and Report to Me）。

再次强调，这是非常精确的。它是可衡量的。它有一个错误列表需要消除。它是可观察的。它确实可以消除这些错误。所以，它可以部署修复。它可以消除它，或者它可以运行相同的代码，并显示错误不会再发生。然后它有一个成功标准和结束状态，那就是我想要一个PR列表，以及任何阻塞点或我需要审查的事项。所以，它将继续查找正确的日志，并持续处理这个问题。现在，我们处于一个迷你剧集。这个目标才刚开始一分钟。我估计这将需要两到三个小时才能完成。我以前也做过非常类似的事情，大约需要两到三个小时。所以，我需要在节目备注或后续内容中说明这是否非常成功。

但这只是一个例子。我喜欢“错误清零”这个概念，你可以将“目标”指向任何困扰你团队的遗留错误。开发者们都知道这些错误的存在，你可以直接说：“去把这些错误解决掉！”有了“目标”，这真的成为可能。而且我看到，使用“目标”来消除错误取得了非常高的质量成功。

<details>
<summary>Original English Source</summary>

And so, I think this is a really great example, but let's do it live because this is how I AI. I'm going to give another example of how I might use this again for some of the more technical folks. So, um, these are the Versel errors. Um, it looks scarier than it is. We have a lot of retries around this, but here are the errors that happened behind the scenes that we have to recover from in our main chat and from the last last two weeks. And I want to do the same thing with these errors. I want to say codeex find these errors classify them ship a fix validate against the existing data until basically there are none of these errors left so I'm going to pull up codeex um I'm going to use GPT this is not like a complicated deep thinking problem so I'm going to use GPT 5.5 medium and I'm going to say goal eliminate errors on the API chat v2 2 endpoint that are showing up in the forcell logs by going through each category of error, identifying root cause, determining if this is a userfacing error. If it is, determine root cause and open a branch plus PR for fix. If it is not, reduce this error to a warning. Once all logs can be handled from the last two weeks, report to me all PRs to review and issues that could not be fixed or what you need from me. This is terrible prompt. This is fine. This is obviously a better goal prompt than I usually write and say success state is we have no userfacing errors and no backend errors that should be warnings. Okay, I'm pressing enter. Um it's compressed my skill descriptions but that's fine. Now, Codeex has hooked up with my Versell plugin. So, it has access and can actually go access these logs. So, it's making this plan. And I just want to pause and tell you kind of how goal works with a plan. So, once it has a goal, it makes I've seen these like three to fivestep plan. So, it's going to inventory the current repo. It's going to pull the last two weeks of versell errors in group by category. It's going to classify them as userfacing errors and it's going to implement and validate fixes or downgrade warnings by category and then it's going to publish the PRs and report to me. Again, this is very precisely. It's measurable. It actually has a list of errors it's going to burn down. It's observable. It definitely can eliminate those errors. So, it can ship a fix. It can eliminate it or can run the same code and it can show that the error wouldn't be hit. And then it has a success criteria and an ending state to me, which is I want a list of PRs and any blockers or things that I need to review. And so it's going to go ahead and go through and try to find the right logs. It's going to continue to work on this. Now, we are in a mini episode today. It's 1 minute into this goal. I suspect that this is going to take 2 to three hours to get through. I've run something very similar on this. It's taken about 2 or 3 hours to get through. So, I will have to put in the show notes or a follow-up whether or not this was super successful, but it's just an example to you. I love this idea of just like century zero, error zero, where you can point goal at any kind of like lingering errors that have really haunted your team and developers out there. You know that these exist and you can actually say just go get rid of these. And with goal, it really is possible. And I've seen very high quality success on using goal to burn down errors.

</details>

### 非技术场景的惊喜应用：邮件与任务管理

这是一个关于如何使用“目标”的技术示例，但我想让它更适用于非开发者人群，因为坦白说，“目标”在**非编码用例**（Non-coding Use Cases）中的应用甚至更令人兴奋。

（广告）本期节目由Mercury赞助，这是我为Chapiardi项目使用的银行解决方案。我每天都在构建AI工具，谈论AI。所以，当人们问我使用什么来运营我的业务时，Mercury是一个非常简单的答案。因为一个仍然在使用笨重过时银行服务却自称AI创始人的角色，简直是自相矛盾。Mercury帮助我追踪运行率和收入增长，通过账单支付给我的供应商，并接收客户的付款。曾经感觉很麻烦的电汇和转账——发送款项、接收付款、确认到账——Mercury让这一切变得简单。整个平台干净、快速、现代化，这是大多数银行服务所不具备的。我使用他们多年了，这是一个让我从不想更换的工具，因为它从未给我带来任何困扰。访问mercury.com，在几分钟内在线申请。Mercury是一家金融科技公司，而非FDIC承保银行。银行服务由Choice Financial Group通过Column NA（FDIC成员）提供。

接下来这个例子，我想分享我最喜欢的使用`/goal`的场景。它彻底改变了我的认知，如果你看完这集什么都没记住，我希望你能去尝试这个：**使用“目标”来清理你所有未读邮件**。Codex可以访问我的Gmail插件。这意味着它有**MCP（多模态控制平台）访问权限**（Multimodal Control Platform Access），能够读取我的邮件。昨天我真的有3900封邮件。

我将尝试找到我保存的聊天记录。所以我将输入`/goal`，看看我昨天设定的目标是什么。这是一个写得糟糕得多的提示：“**分类所有批量促销垃圾邮件。取消订阅不必要的邮件并清理你的收件箱。在需要判断时寻求帮助**。”它运行了3小时52分钟，使用了大约600万个token。所以，这并不便宜。我只是向你展示它做了什么，它就像是真的阅读了每一封邮件，对它们进行了分类，给它们贴上了漂亮的标签，然后我就可以根据这些标签进行决定，包括“需要判断”的标签，它还为我点击了取消订阅链接，并给我提供了一个我可以使用的取消订阅链接列表。一天结束时，我从大约——让我们实际问一下，我最初有多少未分类的邮件，现在还剩下多少需要过滤的邮件。所以，它会去检查自己的工作，你会监督我，以证明我没有编造。它会显示我最初有多少邮件，现在还剩下多少。我非常确定是大约4000封，我想我们处理到了1000封以下需要处理的邮件。好的，它稍微花了一点时间才回忆起它做了什么，但再说一次，我们最初有大约3900封邮件。现在我只剩下68封需要处理的。所以这是我今天的工作。它为我分类了将近4000封邮件，并把它们放进了漂亮的文件夹。它为我取消了订阅。它给了我需要回复的邮件的漂亮类别。如果你等了我几周，你现在就会收到回复了。现在我的邮件收件箱更干净了，我可以长期使用它。所以，再说一次，`/goal`，我的提示非常简单：**“只需分类我所有的邮件，取消订阅并清理我的收件箱”**。它运行了4个小时，现在我的收件箱更干净了。

<details>
<summary>Original English Source</summary>

So that is a technical example of how to use goal, but I want to make this more applicable to people who aren't developers because I honestly think goal for non-coding use cases is even more exciting. Today's episode is brought to you by Mercury, the banking solution I use for Chapiardi. I build AI tools. I talk about AI every day. So when people ask what I use to run my business, Mercury is a genuinely easy answer because an AI founder who still deals with clunky, outdated banking is kind of a walking contradiction. Mercury is how I track run rate and revenue growth, pay my vendors through bill pay, and get paid by clients. Wires and transfers that used to feel like a whole thing. sending money, accepting payments, knowing it arrived. Mercury just makes it simple. The whole platform is clean, fast, and modern in a way that most banking honestly isn't. I've banked with them for years. It's one of those tools where I don't think about switching because it's never given me a reason to. Visit mercury.com to apply online in minutes. Mercury is a fintech company, not an FDIC insured bank. banking services provided through choice financial group and column NA members FDIC. For this next example, I want to give you my favorite use case of SLGO. It has blown my mind and if you leave this episode with nothing else, I hope you go do this, which is use the goal to clean up all your unread emails. So, Codeex has access to my Gmail plugin. That means it has MCP access. It means it can go through and read my email. I had yesterday truly 3,900 emails, something like this. I'm going to see if I can find the resume the save chat. So, I'm going to type in goal and see what my goal was that I did yesterday. It is the much worse written prompt. Categorize all bulk promotion spam emails. Unsubscribe from unnecessary emails and clean up your inbox. Ask for help while needing judgment. It ran for 3 hours and 52 minutes and it had it used about 6 million tokens. So, it was not token cheap. I'm going to just show you what it did, which is it just read like literally read every email, categorize them, put nice labels on them, so then I could go decide including labels like needs judgment, clicked unsubscribe links for me, gave me a list of unsubscribe links that I could use. And at the end of the day, I went from about let's actually ask how many emails did I start with uncatategorized and how many are now left to filter. So, it's going to go ahead and check its own work and you're going to hold me accountable to show that I did not make this up. And it's going to show how many emails I started with and how many do I have left. I'm pretty sure it was about 4,000 and I think we got down to about sub 1,000 that needed to get done. Okay, it took a little prompting to remember what it did, but again, we started about 3,900 emails. Now I'm down to 68 that I need to look at. So that's my today project. So it categorized almost 4,000 emails for me. And it put it in lovely folders again. It unsubscribed for me. It gave me nice categories of emails that I needed to respond to. if you've been waiting on me for a couple weeks, you now got a response. And now I have a much cleaner email that I can run over time. So again, slashgoal um my prompt was very simple. Just categorize all my emails, unsubscribe and clean up my inbox. It ran for 4 hours and now I have a much cleaner inbox to work with.

</details>

### 项目管理优化：利用Goal清理Linear任务

好的，我再举一个非技术用例，我认为这对产品经理们会非常有用。我的**Linear**（Linear: 任务管理软件）任务管理软件已经完全脱轨了。这部分是OpenClaw的问题，因为我让我的AI代理、我的OpenClaws（指OpenClaw Bolo）访问了Linear，它们创建了一堆任务，但并非所有任务都已完成。所以，我想清理我的Linear任务，只留下我需要完成的任务。

我特别希望为我们的播客Linear清理这些任务，因为我们曾对每集节目抱有很高的期望，计划做很多事情。我们通常只完成了其中大约70%，现在我想清理它。所以我将输入`/goal`：**清理“How I AI”播客团队在Linear中的问题。任何已发布剧集中的未标记为“已完成”的任务都应标记为“不会做”。我们的目标是本周及以后只开放未来剧集的任务，而不是那些我们永远不会完成的旧任务**。

我将让它执行这项任务。它应该能够访问Linear插件。它会遍历所有任务，我再说一遍，这可是成百上千的任务。它会进行判断，决定“我能关闭这个任务吗？我能更新这些数据吗？”如果你希望拥有更好的**任务卫生**（Task Hygiene），确保所有内容都被正确标记、正确分配，那么这是一个非常好的用例。所以，它找到了Linear团队。它将从团队层面开始工作。它将识别**陈旧的剧集任务**（Stale Episode Tasks）。它将遍历并清理它们。我们想要的任务状态不是“不会做”，而是“已取消”。它将继续处理并完成这项工作。所以我预计这个任务会快一点，但可能需要30分钟到1小时才能完成高质量的判断。

任务结束后，我将拥有一个更干净的Linear工作空间。再说一次，它强调了一个明确的规则正在浮现：**保留本周及以后的未来剧集任务，在周一之前取消所有未完成的剧集发布任务**。它将**限定批量更新范围**（Scope the Bulk Update）。它将验证我想要的结果——一个干净的Linear——是否已完成，并将在一段时间内完成此任务。

<details>
<summary>Original English Source</summary>

Okay, I'm going to give one other example of a non-technical use case that I think is going to be really useful for the product managers out there, which is I have let my linear, my task management software go completely off the rails. This is partly an openclaw problem, which is I gave my agents, my open claws, bolo access to linear, and they created a bunch of tasks, not all which that they have done. And so I want to clean up my linear tasks and get them to only the ones that I need to complete. And I want this in particular for our podcast linear because we had aspirations of all the things we would do with every episode. We usually do about 70% of those and I just want to clean it up. So I'm going to say / goal clean up the how I AI podcast team issues in linear. Anything from a previously released episode that is not marked as done should be marked as will will not do. Our goal is to have open only future tasks this week and forward for episodes not old tasks we'll never get around to. So, I'm going to let that do that. It should have access to the linear plugin. It's going to go through, and again, I'm telling you, this is like hundreds and hundreds and hundreds of tasks. It's going to go through and make this judgment call of can I close this? Can I update the data? If you want to have better task hygiene where you want to make sure everything is tagged correctly, assigned correctly, this is a really good use case. And so, it's found the linear team. It's going to work at the teen level. It's going to identify stale episode tasks. It's going to go through, clean them up. Um, the task status we want is not, won't do. It's called canceled. And it's just going to process through and go ahead and do that. So, I suspect that this one will go a little bit faster, but we'll probably take 30 minutes to an hour to go through really high quality judgment. And at the end of it, I'm going to have a much cleaner linear workspace to work with. And again, it's saying a clear rule is emerging. keep current week, future episode work, cancel non-done episode release work before Monday. It's going to scope the bulk update. It's going to validate that the outcome I wanted, which is a clean linear, is done, and it will complete this over time.

</details>

### 何时避免使用Goal：目标设定的边界与原则

这些就是我关于如何使用“目标”的三个例子。其中一个是技术性的。再说一次，它仍在运行，目前已经完成了前两步。这个技术目标是查看我所有的错误日志，并基本上对其进行分类、修复，并彻底消除它们，目标是永远不再有错误。第二个是非常实用的目标：清理我的电子邮件收件箱，这样我就可以真正阅读我的邮件了。这个花了大约4个小时，我认为对每个人都很有用，而且我不需要提供非常好的提示。第三个是关于项目管理的：确保我的项目、任务和问题是干净的，我的待办事项是干净的，所有内容都按照我想要的方式进行标记，我只需要关注对我重要的事情。

我认为这是你可以在Codex中使用“目标”的三种方式。在我们结束之前，我想退一步谈谈何时不应该使用“目标”，以及我对未来的看法。所以，“目标”并非适用于所有任务的正确工具。但我再次引用这篇博客文章，因为我认为他们说得比我好。**不要将“目标”用于非常简单的单行编辑**。这对于这项任务来说太大了。你的目标不应该是“确保删除这行代码”。**你真正想要的是一个结果，而不是一个几乎输出**，这样它才能成为一个好的目标。

另外，**当终点模糊时，也不要使用“目标”**。所以你不能说——我的意思是，也许你可以，如果你说的是`/goal`，“让我的客户开心”。我认为这是一个非常模糊的目标，很难衡量，并且没有可靠的明确完成条件。所以这不太好。他们举的另一个例子是“重构这段代码”。这不是一个使用`/goal`的好例子。事实上，我正在用Codex进行一个“重构这段代码”的倡议，但我没有使用“目标”功能。

他们说，我只想再次强调这一点：**当一个目标具有三个属性时，它是最强大的**。一个**持久的目标**（Durable Objective）、一个**基于证据的终点**（Evidence-based Finish Line），以及一条可能需要**多次调查才能完成的路径**（Path that May Require Several Turns of Investigation）。所以，如果你有一个长期稳定的目标，你知道你想达到这个目标，它是基于证据的，你可以衡量它，并且你认为达到它需要多次迭代，那么“目标”就是为你准备的。

<details>
<summary>Original English Source</summary>

So, those are my three examples of how to use goal. One is a technical one. Again, it's continuing to run, so it's gotten through the first two steps here. um the technical goal of looking at all my error logs and basically classifying them, fixing them, burning them down with the goal of having no more errors ever. There is the second very practical goal of clean up my email inbox and so I can actually read my email. That one took about 4 hours, I think, useful for everyone and I did not have to have a very good prompt there. And then my third one for project management. Make sure that my projects and my tasks and issues are clean, my backlog is clean, everything is labeled the way I want, and I only have to focus on the things that matter to me. These are three ways I think you can use goals in Codeex. Before we end, I want to take a step back and talk about when you shouldn't use goals and then what I think is next. So goals are not the right tool for every job. But I'm pulling up this blog post again because I think they say it better than me. Do not use goal for something that is a very simple oneline edit. It is just too big of a tool for the job. Your goal wouldn't be like make sure this line of code is removed. You really want an outcome, not an output almost um for it to be a good goal. Also, don't use a goal when the finish line is vague. So you can't do I mean maybe you can if you're like slashgoal make my customers happy. I think that is just a very vague goal. It's very hard to measure and there's no reliable definitive completion condition. And so that's not very good. The other example they give is like refactor this code. Not a good example of when to use /goal. And in fact I'm doing a refactor this code initiative with codeex but I'm not using a goal. They say, and I just want to reiterate this for you, goals are strongest when it has three properties. A durable objective, an evidence-based finish line, and a path that may require several turns of investigation. So, if you have an objective that stays steady over time, you know you want to hit that objective, it can be evidence-based and you can measure it, and you think getting there is going to require a couple turns. Goals are for you.

</details>

### AI协作的未来：从“保姆”到“管理者”的角色转变

在我们总结之前，关于`/goal`以及为什么我对这种与AI协作的框架如此兴奋，有几点思考。

首先，正如我一开始所说，这是我第一次能够完成这些**自主长时任务**（Autonomous Long-running Tasks）。所以，我真的可以给LLM、AI设定一个目标，然后走开，让它在数小时内解决一个如果我来“照看”会非常烦人的问题。所以，第一，我认为我“照看”AI的日子基本结束了。并非完全结束，我现在仍在“照看”一个分支，但对AI而言，大部分都已结束。

第二，我认为“目标”对我的代码中那些一直很难追查和烦人的**生活质量问题**（Quality of Life Things）产生了影响。是的，我可能可以一个任务接一个任务地去说：“请修复问题A，然后修复问题B，然后修复问题C”，并且我可以使用不同的编码工具来解决这些问题。但是，仅仅说“**错误清零**（Error Zero），遍历我们所有的错误日志并修复它们，直到它们不复存在”的想法，对于提高质量而言是极其强大的。所以，对于希望减少**技术债务**（Tech Debt）、修复**不稳定的测试**（Flaky Tests）、处理那些可能令人烦恼且难以复现的**客户端错误**（Client Side Errors）的工程团队来说，我认为`/goal`功能非常强大。

第三，我认为产品经理会非常喜欢“目标”功能。再说一次，我们被反复灌输的是**结果而非产出**（Outcomes Not Outputs）。你不应该定义工作，而应该定义成功的样子。我认为随着越来越多的团队开始将`/goal`作为其编码工作流程的一部分，产品经理将不得不更好地使用良好的目标来提示这些AI。我们已经具备其中一些技能，但我认为`/goal`所需的**技术验证水平**（Technical Level of Validation）要求你提升这些硬技能，重新审视一个好的目标究竟是什么样子。

最后，我想说，有了`/goal`和这些长时间运行的任务，我感觉这一点在OpenClaw上有所体会，并且我认为这将变得越来越真实：与AI合作的感觉越来越像与一位人类同事合作。你给一位人类同事分配任务。你不会坐在他们旁边，拍拍他们说：“好的，下一步。好的，下一步。”你真正做的是给他们一个目标。他们会根据完成目标所需的时间去工作，然后带着完成的任务回来向你汇报，你再提供反馈。所以，这是一种工作模式。尽管AI在某些任务上可能比人类快，但它们在另一些任务上可能比人类慢，因为它们有耐心处理边缘情况。但无论如何，它们都会利用完成任务所需的时间。这真的让我感觉自己更多的是处于**管理者模式**（Manager Mode），而非**构建者模式**（Builder Mode）。老实说，我不确定我是否喜欢这种感觉。当`/goal`功能推出时，我发现自己有点无所事事，四处寻找我可以在编码工作中做些什么，因为大部分工作现在都由AI自己处理了。

总之，我强烈建议你尝试`/goal`功能。如果不在Codex中，也可以在你最喜欢的AI工具中尝试类似的循环。让它运行，让它为你解决更大、更复杂的问题，并在需要审查工作时再回来找你。这就是我如何AI的。我非常期待看到你们能构建出什么。我将回到我的日志，看看我们是否真的消除了所有这些错误。感谢大家的加入。

非常感谢您的观看。如果您喜欢本节目，请在YouTube上点赞并订阅，或者更好的是，在评论区留下您的想法。您还可以在Apple Podcasts、Spotify或您喜欢的播客应用上找到本播客。请考虑给我们评分和评论，这将有助于更多人发现本节目。您可以在howiaipod.com上查看我们所有的节目并了解更多信息。下次再见。

<details>
<summary>Original English Source</summary>

So before we wrap, a couple thoughts on SlashGole and why I'm just really excited about this framework of working with AI. One, as I said at the beginning, this has been the first time that I've been able to get these autonomous long running tasks done. And so I really can set the LLM, the AI, up with a goal, step away, and have it work over many hours on a problem that would be very annoying to babysit. So, one, I think my babysitting days are largely over with AI. Not completely over. I'm still babysitting a branch right now, but largely over with AI. I think the second thing is the impact that goal has had on quality of life things in my code that have been very hard and annoying to chase down. Yes, I probably could have gone task by task and said, "Please fix issue A, then fix issue B, then fix issue C, and I could have set different coding tools off on those problems." But this idea of just saying like error zero, go through all our error logs and fix them until they exist no more is incredibly powerful for in particular quality. So for engineering teams looking to burn down tech debt, fix flaky tests, look at really annoying like client side errors that are maybe annoying to reproduce. I feel like SLG goal is really powerful. The third thing is I think that product managers are really going to love goal. Again, we've had it drilled into us outcomes not outputs. You shouldn't be defining the work. You should be defining what success looks like. I think as more and more teams start to use slashgoal as part of their coding workflow, product managers are going to have to get a lot better at prompting these AIs with good goals. And we have some of those skills already, but I think the technical level of validation that's required by slash goal requires you to uplevel these hard skills in re writing what a good goal actually looks like. And then finally, I'd say with slash goal and these longrunning tasks, and I felt this a little bit with openclaw, and I just see this becoming more and more true, working with AI just continues to feel more and more like working with a colleague, a human colleague in that you assign a human colleague a task. You don't like sit there over their shoulder and tap and say, "Okay, next step. Okay, next step." What you really do is you give them a goal. They go away for the time required to hit that goal and then they come back to you with the completed task and you give feedback. And so again, it's this form factor. Even though the AI is maybe faster than a human would be on some tasks, they may be slower than humans because they have the patience to go to the edge cases of things. But either way, they're using the time necessary for the task to get it done. And it really feels like I'm much more in manager mode than builder mode. And honestly, I'm not sure that I love that. When Slash Gold came out, I found myself kind of like twiddling my thumbs and looking for the job that I could do in the coding work because so much of the job had now been handled itself. So, in conclusion, I really suggest you try SLGO. If not in codeex, try a similar loop in whatever your favorite AI tool is. Let it run and let it solve bigger, more complex problems for you and come back to you when it's time to review the work. This is how I AI. I'm so excited to see what you build and I'm going to get back to my logs and see if we've actually eliminated all these errors. Thanks for joining. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>