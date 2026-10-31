---
author: How I AI
date: '2026-06-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Idjt53tTv2U
speaker: How I AI
tags:
  - ai-agent
  - software-security
  - vulnerability-detection
  - test-harness
title: Mozilla通过自研Harness与AI模型修复近500个Firefox安全Bug
summary: Mozilla工程师介绍团队利用Anthropic模型Mythos与自研测试Harness，建立清晰的任务验证信号与假设循环，在Firefox中发现并修复近500个安全Bug的实践经验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Brian Grinstead
companies_orgs:
  - Mozilla
  - Anthropic
products_models:
  - Firefox
  - Mythos
media_books:
  - How I AI
status: evergreen
---
<!-- chunk 1/7 -->

Firefox 有数万个源代码文件和数千万行代码。不可能直接让它单次搞定，说“去把这个项目里的所有潜在 Bug 都找出来”。对模型来说上下文实在太多了。

<details><summary>Original English</summary>Firefox has tens of thousands of source code files and tens of millions of lines of code. It's not possible to say one shot, go find all the potential bugs in this project. It's way too much context for the model.</details>

>> 我觉得人们真的大大低估了 Agent 所能承受的那种永无止境的枯燥与乏味。

<details><summary>Original English</summary>>> I think people really underappreciate the relentless tedium that an agent will go through.</details>

>> 任何做过这种我称之为“考古”工作的人都知道，这真的很难做。而这恰恰是编程 Agent 所擅长的。我让 Claude Code 去从语义上搞清楚这个 Bug 是什么时候引入的。我看着它执行那些我甚至都不知道存在的 Git 命令。

<details><summary>Original English</summary>>> Anybody who's done this kind of what I call archaeology, it's really hard to do. And this is something that the coding agents are great at. I asked Cloud Code, go figure out semantically when this bug was introduced. I was like watching it do get commands. that I didn't even know existed.</details>

>> 能够拿出一个 Agent，给它一个在范围和接触面上都极其受限的问题，然后对它说“穷尽所有方法去尝试解决这个”，这真的很强大。再说一遍，并不是因为人类的智力无法发现类似的问题，而是我们的认知精力会随着时间推移而下降，但 Agent 不会。

<details><summary>Original English</summary>>> And the ability to take an agent, give it a very constrained problem in surface area and say exhaust every attempt at this is really powerful. Again, not because human intelligence couldn't identify similar issues, but actually our like cognitive energy declines over time in a way that agents don't.</details>

>> 我们的目标不是留下一堆难以发现的 Bug。我们的目标是零 Bug。因此我认为，随着我们和其他防御方开始应用这些工具，实际上正让我们离那个世界更近一步。

<details><summary>Original English</summary>>> Our goal is not to have a bunch of bugs that are hard to find. Our goal is to have zero bugs. And so I think that these tools as us and other defenders are starting to apply them actually get us closer to that world.</details>

### 开场与背景介绍

>> 欢迎回到《How I AI》。我是 Clarvo，产品负责人兼 AI 痴迷者，这里的使命是帮助大家用这些新工具更好地进行构建。今天我请来了 Brian Grinstead，Mozilla Firefox 的杰出工程师。他将带我们走进幕后，分享他们使用 Anthropic 全新但尚未完全公开发布的模型 Mythos 的体验，以及他们如何通过自研一套其实并不像你想象的那么复杂的 Harness，解决了近 500 个安全 Bug。让我们直奔主题。本期节目由 WorkOS 赞助播出。AI 已经改变了我们的工作方式。各种工具正在帮助团队编写更好的代码、分析客户数据，甚至自动处理支持工单。但这里有个问题：这些工具只有在能够深度访问公司系统时才能发挥良好作用。你的 Copilot 需要查看你的整个代码库，你的聊天机器人需要跨内部文档进行搜索。而对于企业采购方来说，这引发了严重的安全担忧。这就是为什么这些应用从第一天起就面临极其严格的 IT 审查。为了通过审查，它们需要安全认证、访问控制、审计日志以及整套企业级功能。从头构建所有这些是一项巨大的工程。这就是 WorkOS 的用武之地。WorkOS 为你提供用于企业功能的即插即用 API，让你的应用能够具备企业级就绪能力，并更快地向高端市场拓展。可以把它想象成企业功能的 Stripe。OpenAI、Perplexity 和 Cursor 都已经在利用 WorkOS 来加速行动并满足企业需求。欢迎前往 workos.com，加入他们以及数百家其他行业领军者的行列。

<details><summary>Original English</summary>>> Welcome back to how I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Brian Ginstead, distinguished engineer at Mozilla Firefox, who's going to take us behind the scenes with their experience with Anthropic's new but not yet fully released model Mythos and how they solved almost 500 security bugs by rolling their own harness, which isn't as complicated as you think. Let's get to it. This episode is brought to you by Work OS. AI has already changed how we work. tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features. Building all that from scratch, it's a massive lift. That's where work OS comes in. Work OS gives you drop-in APIs for enterprise features so your app can become enterprise ready and scale up market faster. Think of it like Stripe for enterprise features. OpenAI, Perplexity, and Cursor are already using WorkOS to move faster and meet enterprise demands. Join them and hundreds of other industry leaders at workos.com.</details>

今天就开始构建吧。Brian，欢迎来到《How I AI》。我对这期节目感到非常兴奋，因为我认为你拥有当下 AI 工程领域最具影响力的故事之一。那么，先跟我说说，我们先为听众把视野拉远一点：你所负责的产品范围有多大，而你们做成的事情难度有多高？

<details><summary>Original English</summary>Start building today. Brian, welcome to How I AI. I'm really excited about this episode because I think you have one of the most impactful stories in AI engineering right now. So, tell me first, let's take a step back for people. what is the scope of the product you're working on and how challenging is what you pulled off?</details>

>> 好的，谢谢，感谢邀请我。我是……我在 Firefox 工作，它是一个生产环境的 Web 浏览器。它规模非常大，也非常复杂。呃，我们必须渲染整个 Web，不论这个网站是 2000 年建的，还是昨天才刚刚推送上线的。因此，我们要应对各种各样的性能、安全以及……以及复杂性问题。于是，在最近几个月里，我们一直在使用新的 Agent 化扫描技术来发现产品内部涌现出的大量安全 Bug，许多团队也在这么做，因为我们开始拥有更好的 Harness、模型和技术来切实修复这些 Bug。

<details><summary>Original English</summary>>> Yeah, thank thanks for having me. So, I I work on Firefox, which is a production web browser. It's very large and very complex. Um, we have to render the entire web, whether the site was built in 2000 or just pushed up yesterday. And so, there's all sorts of performance, security, and and complexity um that we deal with. And so we recently in the last few months have been using new agentic uh scanning techniques to find a a deluge of security bugs inside of the the product as have many teams as we've started to uh get better harnesses, models and techniques for actually getting those bugs fixed.</details>

>> 是的。促使我联系你并邀请你来播客的，正是这张图表。大家可能都在 X 上或者信息流里看到了：Firefox 每月的安全 Bug 修复量在 4 月份成倍激增。很多围绕此事的帖子的大标题都是：Mythos——那个其他人有权限使用、唯独我们普通人没有的货真价实的模型——解锁了对边缘情况或复杂安全 Bug 的惊人发现和修复能力。但我认为这背后的故事其实有些不同。你能跟我们讲讲你们是怎么走到这一步的吗？其中有多少是模型的作用，又有多少是你们在内部完成的工作？

<details><summary>Original English</summary>>> Yeah. And what what caused me to reach out and ask you to be on the podcast was this chart. Everybody saw this maybe on X or on the timeline where the Firefox security bug fixes by month just spiked in multiples in in April. And the headline of a lot of post around this was Mythos the definitely real M that other people have access to just not not not us normies has unlocked a incredible amount of discovery and fixes on edge case or complex security bugs. But I think the story behind the story is actually a little bit different. Can you tell us about kind of how you got here and how much of this was model and how much of this was work you did internally?</details>

### 垃圾报告的困境与 Harness 的突破

>> 是的，没错。我认为就像许多开源项目在整个 2025 年所经历的那样，我们一直在应对几乎像是没人想要的 AI Bug 报告。你知道那种形式的——如果你见过的话，收到一份文档，你一眼就能看出它是 AI 生成的。你知道的，它看起来非常精美、专业，但你看到一半，工程师看着这个就会说“这是错的”，对吧？所以这对项目维护者来说产生了一种不对称的成本：直接把一段 C++ 代码粘贴到聊天机器人里然后得到一个错误的结果是很廉价的，但之前根本没有办法去实际验证那到底是不是真的。而这一切，我认为在 2026 年 2 月左右彻底改变了。我认为这个故事很大一部分原因在于 Harness 本身变得更好了。升级和改进模型无疑在几个方面有所帮助，比如它在从哪里着手排查 Bug 方面有更好的假设，在编写测试用例方面做得更出色。但我认为 Harness 本身，以及将它接入一个把 Bug 修复好的流水线中，其实才是背后鲜为人知的故事。

<details><summary>Original English</summary>>> Yeah, that's right. So I think like a lot of open source projects through 2025, we had been dealing with almost like unwanted AI bug reports and you know the shape you've seen it if you see you get a doc and you can just tell it's from an AI. you know, it looks very nice and professional, but you would get halfway through and the engineer is looking at this and saying that's wrong, right? And so there's a it's sort of asymmetric cost on project maintainers to receive a thing. It's cheap to just paste in some C++ code into a chatbot and get back something that's wrong, but there was no way to actually verify whether that was true. And that all changed like I would say in February of of 2026. And I think a big part of that story is the harnesses themselves just getting better. Definitely improving and upgrading the model helps in a couple ways. Like it it has better hypotheses about where to start with the bug. It does a better job of making test cases. But I think the harness itself and plugging it into a pipeline of getting the bugs fixed is actually a little bit the story behind the story.</details>

>> 没错。那么对于那些反复听到这个词的人——我知道正在看的工程师们可能明白你在说什么，但还是请为我们定义一下，或者展示一下你所说的 Harness 到底是什么意思，以及你们是如何针对自己的产品和团队构建出定制方案，从而解锁了真正落实安全 Bug 修复的吞吐能力，而不仅仅是产生一堆无法付诸行动的垃圾报告或你们无法验证的东西。

<details><summary>Original English</summary>>> Yep. So for folks that have heard this word over and over again. I know the engineers that are watching probably know what you're talking about, but just define for us or show us what you mean by harness and how you built something custom to your product, your team that unlocked your ability to get actual throughput on security bug fixes, not just a bunch of unactionable kind of slop reports or things you couldn't validate.</details>

Harness 是一种赋予大语言模型工具以实现某种目标的方法。所以如果你回想一下聊天机器人拥有任何自定义工具或类似东西之前的时代，它几乎就像是一个装在罐子里的脑子。你知道的，你只是在跟它聊天，它也在跟你聊回来。那周围几乎没有任何 Harness。如今，聊天机器人能够做的事情在一定程度上正与编程 CLI 逐渐融合。这是在赋予它们使用工具的权限，比如运行 Bash 脚本、打开浏览器、衡量你是否成功制造了一个安全问题，等等。这就是我们用来——并且进行了定制以在 Firefox 中寻找问题的实际机制。这在很大程度上，你几乎可以把 Claude Code 就想象成一个 Harness，对吧？所以你在它周围构建自定义的 Prompt 和一些自定义的编排，以便接入你的特定系统，但呃它实际上是一个相当简单的外层包装。你只需要给它提供适合这项工作的正确工具。

<details><summary>Original English</summary>The harvest is a way to give an LLM tools to achieve some goal. And so if you think back to chat bots before they had any custom tools or anything like this, it's almost a brain in a jar. You know, you're just chatting with it and it's chatting back. That has almost there's no furnace around that. These days, the chatbots are sort of blurring in a little bit with the coding CLI in terms of what they can do. This is giving access to tools like running bash scripts, opening a browser, measuring whether you were able to create a security issue and so on. And so this is the actual uh mechanism that we use uh and have customized to find issues in Firefox. This is largely like you could almost imagine just cloud code is a harness, right? And so you build custom prompting and some custom orchestration around it to plug in with your particular systems, but um it's it's actually a reasonably simple uh wrapper around it. You just need to give it access to the right tools for the job.</details>

### 自定义 Harness 的架构与工作流程

>> 那么展示一下你们认定 Harness 中必不可少的工具有哪些，并带我们了解一下，在构建定制方案与直接使用现成的 Claude Code 或现成的 Codex 之间，你觉得真正的杠杆作用体现在哪里。

<details><summary>Original English</summary>>> So show us what what tools you decided were necessary in your harness and walk us through where you felt there was real leverage in building something custom versus using off-the-shelf cloud code or off-the-shelf codecs.</details>

这里有一个例子，算是一个流程图，大致展示了我们的自定义 Harness 是如何工作的。我先开门见山地说，通常当我看到这些流程图时——在学术论文里你也会看到它们——它会让事情看起来非常复杂。里面有所有这些方框和箭头，而我认为它实际上比看起来要简单。我想说 Firefox 拥有数万个源代码文件和数千万行代码。因此不可能说：“噢，单次搞定，去把这个项目里的所有潜在 Bug 都找出来。对模型来说这上下文实在太多了。”所以我们必须先进行某种初步的评分，以指出我们到底想让这个东西对准哪些文件。我们稍后可以详细讨论这个，但它最终会生成一份关于以哪些文件为目标、排定好优先级的列表。在某些情况下甚至细化到函数。然后这就进入到了我们所谓的某种主 Agent 循环中，但你几乎可以把它想象成一个 Claude Code 会话或 Codex 会话，在其中你有一个自定义的 Prompt，内容写着：这是一份检出的 Firefox 代码；这里有一些工具可以在代码库中四处查看；这是你在该文件内的目标文件。我们……我们有点算是在撒谎，我们说：我们知道这个文件里有一个安全 Bug，基本上你必须去找到它。然后它就会

<details><summary>Original English</summary>So, here's an example that's sort of a a flowchart, a little bit of how our custom harness works. And I'll say up front, like often when I see these flowcharts, you see them in academic papers, too. It makes it look really complicated. There's all of these boxes and arrows and and I think really it's it's simpler than it looks. I would say Firefox has tens of thousands of source code files and tens of millions of lines of code. And so it's not possible to say, "Oh, one shot, go find all the potential bugs in this project. It's way too much context for the model." And so we have to do some initial sort of scoring to indicate which files do we want to actually point this thing at. We can talk more about that later, but it it eventually kind of comes up with some prioritized list of which files to target. There are even functions in certain cases. And so that goes into this what we sort of a main agentic loop, but you can almost think about this as like a a cloud code session or a codeex session where you have some custom prompt that says here's a check out of Firefox. Here's some tools to kind of look around the codebase. Here's your target file within that file. We we kind of lie and we say we know there's a security bug in this file. You have to go find it basically. and it will</details>

<!-- chunk 2/7 -->

### 漏洞挖掘与验证机制

就从代码入手，去推导如何从一个网页进入到这段代码中。也就是说，存在某个恶意网页，它究竟如何能实际调用到这行代码？看着这个过程挺有意思的。它会一边思考一边摸索推进，但归根结底，它基本上会生成一些 HTML 测试用例。接着我们把这些测试用例接入到现有的工具基础设施中——这套用于模糊测试（fuzzing）的基础设施我们已经用了几十年了——比如，你可以传入一个测试用例，然后拿到一份报告，说明是否存在潜在的内存安全问题。之后……嗯，它会从该工具获取反馈，判断是否成功了。如果没成功，它就退回去重新开始。

<details><summary>Original English</summary>
just start working its way from the code to reason about how do I get into this code from a web page. So it's some evil web page. How could it actually call this line of code? And it's interesting to watch. It'll kind of think and move its way around, but ultimately it will come up with HTML test cases basically. And we plug this in to our existing tooling infrastructure that we've had for for decades to do fuzzing, for example, where you can pass a test case and get back a report as to whether there's a potential memory safety issue. That will then um get feedback from that tool whether it succeeded or not. And if it didn't, it goes back and starts again.
</details>

而且它可以重新开始很多很多次，运行很长时间。有时最终它会说：“不行，什么都没找到。”嗯，其他时候它会报告说找到了某些东西，而我们要求它以非常结构化的格式输出，以便我们能将其传递给下一阶段，也就是验证阶段。这样一来，我们其实已经大致验证了确实存在崩溃，因为我们从模糊测试构建中拿到了信号。但有时智能体就是会做一些很离谱的事情。比如，它可能会去设置某个仅用于测试、没有任何普通用户会去设置的首选项（pref）。或者我甚至见过这样的情况：智能体为了能利用漏洞并达成目标，自己去修改代码引入了一个漏洞。

<details><summary>Original English</summary>
And it can start many, many times and run for a very long time. Sometimes it will end up and say, "Nope, couldn't find anything." Um, other times it will say that it found something and we ask for it to come out in a very structured format so that we can pass it on to the next phase which is verification. And so we've already kind of verified that there is a crash because we got the signal out of our fuzzing build. But sometimes the agents do just wonky things. For example, it might set a pref that was only ever meant for testing and no user ever sets. Or I've even seen cases where the agent changes the code to introduce a vulnerability so that it can exploit it and achieve its goal.
</details>

所以我们有另一个智能体在旁边审视它，去判断“这看起来合理吗？”嗯，通常它会批准通过。有时它确实会拒绝，并且会打回去让它做更多工作。但到了这个环节，我们系统上的误报基本上就接近于零了，这就解决了我们在开头谈到的那种“扇耳光”式的问题。而且它已经准备得非常充分，可以直接进入我们其余的 bug 处理流水线。随着我们继续做下去，我们又添加了一个补丁智能体（patching agent），它的职责是生成一个看似合理的修复方案，并验证该修复方案……嗯，确实解决了安全问题。所有这些只要写入一个相当简单的云端编排系统中，由它写入存储桶（storage bucket），以便后续在我们流水线的其余部分中使用。

<details><summary>Original English</summary>
And so we have another agent that's kind of looking at it and saying like does this look right? Um that usually approves it. Sometimes it does reject it and it kind of sends it back to do more work. But by the time that this happens, we have almost no false positives on this system which is fixing that kind of slap problem that we talked about um at the start. and it's very well prepared to go into the rest of our bug pipeline. As we had continued to work, we added a patching agent which is meant to kind of generate a plausible fix, verify that that fix has um resolved the security issue. And all of that it just gets written into a pretty simple cloud orchestration system that writes it out to a storage bucket for consuming later in the rest of our pipeline.
</details>

所以我想先退一步讲，因为我最近刚做了一期关于……嗯，`/goal` 的节目，也就是这种可以放进测试运行框架（harnesses）里的目标与结果循环，我当时做了一个使用 Codex 的例子，但它们到处都有，比如 Ralph 循环等等。我觉得大家真的有些低估了一个智能体所能承受的那种不知疲倦的枯燥过程，对吧？能够把一个智能体放进去，给它一个范围和表面积非常受限的问题，并对它说“穷尽在这上面的每一次尝试”，这真的非常强大。再次说明，这并不是因为人类智慧发现不了类似的问题，而是我们的认知精力实际上会随着时间而衰减，而智能体却不会，对吧？如果你让人去针对某个东西尝试 150 种不同的方式，并且每一次都要去观察、做出评估，那在时间上会非常低效，人也会精疲力竭。所以我非常喜欢智能体身上这种不知疲倦的循环机制。

<details><summary>Original English</summary>
And so I just want to take a step back because I very recently did an episode on um slashgoal these sort of like goal and outcome loops that you can put um harnesses and I was I did an example using codecs but they're available all over the place you know Ralph loops all this sort of thing and I think people really underappreciate the relentless tedium that an a an agent will go through right and the ability to take an agent give it a very constrained problem in surface area and say exhaust lost every attempt at this is really powerful. Again, not because human intelligence couldn't identify similar issues, but actually our like cognitive energy declines over time in a way that that agents don't, right? If you asked a human to say like try 150 different things against this um and look at it every single time and make an evaluation, it would be very both very time inefficient and exhausting. And so I just love these ideas of these like relentless loops on agents.
</details>

我想指出的另一件事是——同样，我在最近这期关于 goal 的节目里也提到了——设置护栏，不管是通过验证器子智能体（verifier sub agent），还是对这些 goal 风格的循环施加某种约束，都至关重要，原因正如你所说的。我举过这样一个例子：假设你试图降低一个页面上的 P95 延迟。好吧，你完全可以把该页面上所有引入延迟的特性都删光。你确实可以直接拿掉它们，然后智能体就会说：“看，我达成目标了，现在快多了。”但如果你没有设置那样的护栏，比如“从产品角度看任何东西都不能改变”、“你不能引入新代码”。所以我就很好奇，当你们经历这个验证器子智能体循环时，你们事后有没有把这些情况反馈到分析器智能体（analyzer agent）的提示词中，用来对你们观察到的常见模式做防范呢？

<details><summary>Original English</summary>
The other thing that I want to call out and again I did this this recent episode on goal is putting a guard rail whether that's a verifier sub agent or um a constraint on these goal style loops is really important because of exactly what you said. I gave this example of let's say you're trying to reduce P95 latency on a page. Well, you could remove every latency introducing feature from that page. you could actually like take it away and the agent would be like look I made I made the goal it's it's much faster now but you don't have that guardrails of like nothing from a product perspective can change you can't introduce new code and so I was curious as you went through this verifier sub agent loop did you then feed that back in into the prompting of the analyzer agent in to guard rail against common patterns that you saw
</details>

>> 百分之百是这样。我觉得你必须给它一些立足规则，告诉它不要以这种特定的方式跑偏，因为它绝对会这么干。而且我觉得我们……我想说的是，通过分析日志——既包括人工分析，比如我们团队看着日志一条条过去，也包括使用大语言模型（LLM）去分析日志，去找出“我们从这套东西里看到的一些常见模式和问题是什么”——然后我们事后会在一定程度上调整分析器智能体的提示词，以此来改进它。这些反馈既来自我们自己对智能体执行轨迹（trace）的分析，也来自工程团队的反馈，他们会说：“噢，这是一个很糟糕的 bug。我……我不喜欢这个。”我们与负责该产品的团队保持着极其紧密的循环，以确保整个威胁模型以及我们把结果反馈给团队的方式……呃，都是有用的。

<details><summary>Original English</summary>
>> and 100% like I think that you need to give it some grounding to say don't go off the rails in this particular way because it absolutely will and I think we have I would say from analyzing the logs both sort of manually as I would our team would see them go by but also using LLM to analyze the logs say what are some like common patterns and problems that we're seeing come out of this thing um and then we would tweak the prompts on the analyzer agent sort of after the fact um to improve that and that would come both from our own analysis of the agent trace but also feedback from the engineering teams and they would say, "Oh, this was a terrible bug. I I didn't like this." In a really tight loop with the team that's working on the product to make sure that all the threat model and the way that we were giving this back to the team uh was useful.
</details>

>> 是的。另外我想向大家指出来的是，因为屏幕上虽然有一堆方框，但它其实并没有那么复杂。它是一个分析器循环，它会经过一个验证……验证器子智能体。它能访问的大概有八……你知道，可能有一打工具吧，对吧？都是非常重要的关键工具：文件搜索、如何构建软件包、嗯……bug 工具，然后它进入一个非常经典的、比如 bug 修复流水线……也就是，你知道的，生成修复方案，然后放到一个验证流水线里跑一遍，再发布出去。所以，这其实没有特别复杂。在理想情况下，你们的人力系统大概也就是这么运转的。你们只不过是成功将其编码落实到了这个运行框架中。

<details><summary>Original English</summary>
>> Yeah. And then I want to call out for folks because again, while there's a bunch of boxes on the screen, it's actually not that complicated. It's a a analyzer loop. It goes through a verifi verifier sub agent. It has access to it looks like eight eight, you know, probably like a dozen tools, right? Key tools that are really important. file search, how to build the package, um, bug tools, and then it goes into a very classic like bug fix pipeline, um, which is, you know, generate the fix and then put it through a verification pipeline and and ship it. So, this actually isn't terribly complicated. And this is probably how your human system would work in an ideal world. You've just been able to encode it in in this harness.
</details>

>> 是的。是的，我们……我们算是挺幸运的，因为我们长期以来一直在运营……你知道的，一款浏览器。我们有漏洞赏金系统，我们习惯了接收外部报告。我们有一个内部的模糊测试团队，他们一直在通过人工审查或其他自动化工具寻找 bug。所以这是另一件真正起到帮助的事情：如果你已经有了现成的流水线，并且让智能体接入进来，几乎就像是由人在操作一样，你就不需要同时去凭空创造很多东西。

<details><summary>Original English</summary>
>> Yeah. Yeah, we're we're kind of fortunate because we've been running um you know a a browser for a long time. We have a bug bounty system. We're used to receiving external reports. We have an internal fuzzing team who's always finding bugs either from manual inspection or other automated tools. And so that's another thing that has really helped is if you have the existing pipeline in place and you're letting the agent plug in almost as if it was a person doing it, you're not inventing many things at once.
</details>

>> 是的。是的。

<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 而且它可以专注于你让它去做的这一件事，并且不知疲倦地做下去。

<details><summary>Original English</summary>
>> And it can focus on the one thing that you've told it to do and to do relentlessly.
</details>

### 工具链投资与架构实现

>> 对。而且我……我经常跟别人讲这点。这就像是开发者体验（DevX）团队的复仇：那些已经在开发者工具和自动化方面有所投入的团队，进度就是会遥遥领先，因为所有这些工具都可以被这些智能体以高得多的速度利用起来。所以，嗯，我走访了一家又一家公司，告诉大家：“拜托，拜托，如果你们之前还没做，现在是时候投资开发者工具了，因为对智能体有益的东西对人类同样非常有益，反之亦然。”我很好奇，这个循环又是……它是与模型无关的（model agnostic）吗？你们大家都用了某个特定的 SDK 吗？是类似于那种纯手工打造了整套东西吗？你们实际上是怎么构建它的？大家一直都很好奇。

<details><summary>Original English</summary>
>> Yeah. And I um I tell this to folks all the time. It is like the revenge of the DevX team, which is teams that have already invested in developer tooling in automations are just so much further ahead because all those tools can be leveraged at much higher velocity by these agents. And so, um, I'm going company to company and telling people like, please, please, if you haven't already, now is the time to invest in developer tooling because what's good for the agents is very good for humans as well and and vice versa. I'm curious, is this loop again like is it model agnostic? Did you all use a specific SDK? Did you like kind of like artisally craft the whole thing? How did you actually build this? People are always curious.
</details>

>> 这是一个非常开放的领域，有很多选择。所以这是一个好问题，而且我认为它发展得也非常快。最初的版本使用了 Claude Agent SDK，它……嗯，本质上是对 Claude Code CLI 的一层封装，它以一种特殊的模式运行该 CLI，流式输出 JSON，但为 Python 或 TypeScript 项目提供了良好的编程式钩子（hooks）。我们一直在探索添加 Codex 支持的最佳选择，你可以通过几种不同的方式来实现：一种是你接入 Codex CLI；一种是使用 OpenAI Agent SDK；或者你可以迁移到某种旨在做到与模型无关的第三方运行框架。而且……根据一些初步测试，我对这一切的直觉是，使用供应商提供的运行框架作为底层……呃，底层基础设施，可能是最好的路线。而且……我觉得他们可能正在利用这些框架进行后训练（post-training）等工作，从而让他们的模型在这些框架中发挥出最佳性能。

<details><summary>Original English</summary>
>> It's a very open space and there's a lot of options. So, it's a good question and I think it's also moving very quickly. So the initial version used the claude agent SDK which is um essentially it's a wrapper of the claude code CLI where it runs it in a special mode where it's streaming out JSON but it gives you nice programmatic hooks for like a Python or TypeScript project. We have been exploring the best option for adding codec support and you can do that in a couple different ways. One is you could have codec cli, you could have the open AI agent SDK, or you can move to like a third-party harness that's meant to be model agnostic. And like like my intuition on all of this based on some initial testing is that the vendor provided harnesses as the underlying uh infrastructure is probably the best way to go. and and I I like they're probably doing post-training and other things using those harnesses to make their models work best in them.
</details>

但同时你也希望确保自己针对各种各样的模……模型、框架技术以及提示策略来进行测试运行，因为作为防御方，你需要去全面审视整个局势，防范任何一个攻击者可能会尝试一些奇怪的招数，或者换用不同的模型，而那实际上就会找出不同的 bug。

<details><summary>Original English</summary>
But you also want to make sure that you're running against a variety of of mo models, harness techniques, and prompting because as defenders, you need to be sort of scanning the landscape for any one attacker might be trying to do something weird or with a different model and it's going to actually just find a different bug.
</details>

>> 对。对。太棒了。这很有帮助。所以是的，再次重复

<details><summary>Original English</summary>
>> Yep. Yep. Great. So that's that's helpful. So yes, again repeating
</details>

<!-- chunk 3/7 -->

对大家来说，这是——这也正是我凭直觉以为你会提到的，也就是 Claude Agent SDK 或者 OpenAI Agents SDK。嗯，还有一些你可以使用的第三方框架或 harness。据我所知，Pi 就是大家现在非常喜欢的一个。嗯，不过我认为你的直觉和我的直觉是一致的，那就是因为这些——嗯，模型提供商的 harness 与他们特定的模型高度调优，所以你实际上两者都得运行，尤其是在安全环境下，因为这恰恰也是攻击者会去运行的。而且他们确实——他们确实会在不同的方面发挥各自的强项，无论从模型角度还是 harness 角度来看都是如此，并且极有可能会发现并修复不同的问题。所以，好吧，你——你说服我了。我们应该——我们都应该构建我们自己的定制 harness，你知道，不仅仅是为了安全问题。再次说明，这像是一个非常特殊的用例，但在特别是大型代码库内部，存在着各种各样的用例，在这些用例中定制 harness 都会非常有效。

<details><summary>Original English</summary>
for people, this is this was my intuition of what you were going to say, which is the cloud agent SDK or the OpenAI agents SDK. Um there are some third-party frameworks or harnesses you can use. PI is one I hear people are loving a bunch right now. Um, but I I think your intuition matches my intuition, which is because these um model provider harnesses are so tuned to their particular models, you actually have to run both, especially in a security environment because that is exactly what your attackers are going to be run. And they do they do have they spike on strengths both from a model perspective and harness perspective on different things and we'll very likely identify and fix different things. So, okay, you you've sold me. we should we should all build our our custom harness, you know, not just for security issues. Again, this is like a very particular use case, but there are all sorts of use cases where a custom harness would be very effective inside um in particular large code bases.
</details>

我们来聊聊其中一个具体是如何运行的。归根结底，将所有这些东西拼接在一起的某种基础设施，在许多需求之间是非常通用的，从分类、呃、漏洞检测，到漏洞修复。你相当于——嗯，把它在自己的环境中搭建起来。你给它设定某个目标，而且它必须是某个落地的目标。它去运行，然后给你提供一些产物，以便进一步接入你的后续流程，无论那是一个问题跟踪器还是一个 Pull Request，诸如此类。因此很有意思的是，我认为这与一些——我所见过的你知道、嗯、更多是为漏洞修复而设计的项目之间，存在着大量的重合，它们看起来非常相似。所以这是你这里标准的那种氛围编程仪表盘，基本上展示了一堆运行记录，并且——请注意这主要是伪造的数据。这并不是真实的你知道 Firefox 运行记录，但我们在这里所做的是，我设定了类似于——我们批量将它们发送出去，所以设定了类似于一组组相关的文件，或者我们想要进行一些评估等等。因此我在这里所做的是，我们实际上选取了——嗯，10 个真实的漏洞，这些漏洞是我们比通常情况下更早公开的——嗯，最近刚刚发布的漏洞，而我们这样做，完全是为了我们现在正在做的事情，也就是某种程度上帮助——嗯，帮助让人们了解这是如何运作的，作为防御者你可以如何应用它，并某种程度上——嗯，帮助理解这是真实的。所以我们所做的就是，我们拿取了完全相同的那些漏洞，并在节目中提取了它们的实际 trace 来深入研究。那么有几个我认为相当有意思。我们从这个 legend 元素开始。这是一个你可以用来组织表单的 HTML 元素。

<details><summary>Original English</summary>
Let's talk about how one of these actually runs. Ultimately, the sort of infrastructure to plug all this stuff together is very shared across many needs from like triage, uh, bug detection, bug fixing. You're sort of um, standing this thing up in its own environment. You're giving it some goal and it needs to be some grounded goal. It is going and running and then it's giving you some artifacts to plug in further down your pipeline, whether that's an issue tracker or a poll request and so on. And so it's interesting how much overlap I think there is with this and some of I I've seen you know um projects that are designed more for bug fixing that look very similar to this. So this is your standard kind of vibe coded dashboard here that shows basically a bunch of runs and and note this is mostly fabricated data. this isn't the real you know Firefox runs but what we have done here is I've set sort of we we send them off in batches and so set sort of sets of files that are related or we want to do some evaluations and so on and so what I have done here is we're actually taking um 10 real bugs and these are bugs that we we opened earlier than we normally would have um security bugs that had recently shipped and we did that like for exactly the thing that we're doing now which is to sort of help um help make people aware of how this works, how can you apply it as defenders and sort of um help understand that this is this is real. So what we've done is we've taken those exact bugs and sort of pulled the the actual traces for them to dig into here on the show. So a couple that I think were pretty interesting. We start with this legend element. So this is an HTML element that you can use for organizing forms.
</details>

### 漏洞挖掘实战与复现

>> 我得非常快速地回看一下那篇博文，因为这一个吸引了我的注意。嗯，这是那个大概有 20——15 年还是 20 年之久的漏洞吗？

<details><summary>Original English</summary>
>> And I have to go back really quickly to the blog post because this one caught my eye. Um, is this the one that was like 20 15 or 20 years old?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 我想那是——对，那是一个 XSLT 漏洞。我们发现了——

<details><summary>Original English</summary>
>> I think that was a Yeah, that was an XSLT bug. And we found
</details>

>> 不过第二号是个有 15 年历史的漏洞。

<details><summary>Original English</summary>
>> the number two though, as 15y old bug.
</details>

>> 对，没错。所以，如果你留意到我们这些新漏洞的 Bug ID 是 2,25,977。Bugzilla 里面有非常非常多的漏洞。如果你发现了一个——嗯，处于六位数的漏洞，那就是一个非常古老的漏洞了。所以，这也挺有意思的，对于——对于这个完全相同的 XSLT 漏洞，我想搞清楚比如这个漏洞是何时引入的，任何做过这种被我称作“考古”工作的人都知道这非常难做，而这正是代码 Agent 非常擅长的事情。所以我当时想知道这个漏洞是何时引入的？嗯，那个文件在三年前被重命名了，所以你不能只做一次 git diff，然后实际上这个代码块移动到了那个文件。这是非常烦人的工作。我让 Claude Code 去想办法找出比如从语义上讲这个漏洞是何时引入的。它——我当时就像是看着它执行——嗯，各种 git——我都不知道存在的 git 命令，它在执行的过程中一边做一边做记录。所以真的很有趣。我们就是这样得出那个 20 年的数字的。嗯，所以这里面很多漏洞已经存在很长时间了。我们有一个漏洞赏金计划，会付钱给发现这些漏洞的人，某种程度上它们非常难以发现，这也是使我们如此引人瞩目的部分原因。所以如果我们看看比如这个 legend 的漏洞，嗯，它用来做浏览器评估器的工具尝试了 14 次。

<details><summary>Original English</summary>
>> Yes, exactly. So, if you notice our bug ids for these new bugs are 2,25,977. So, there's many many bugs in Bugzilla. If you find a bug um that is in the six digits, it's a very old bug. And so it it was kind of funny for the for this exact XSLT one I wanted to say like when was this bug introduced and anybody who's done this kind of what I call archaeology is it's really hard to do and this is something that the code agents are great at. So I would say when was this bug introduced? Well the file got renamed three years ago and so you can't just do a get diff and then actually this blob moved to that file. It's very annoying work. And I asked Cloud Code, go figure out like semantically when this bug was introduced. And it I was like watching it do um get g get commands I didn't even know existed to go kind of taking notes as it was doing it when it was doing. So really interesting. That's how we had gotten that 20-year-old number. Um and so a lot of these have been around a long time. We have a bug bounty program that would pay people to find these bugs and sort of they're very hard to discover and that's what part of what makes us so notable. And so if we look at like this legend one um the tool that uses to do browser evaluator it tried 14 times.
</details>

因此从逻辑上讲，这看起来就像是它说：好的，嗯，我正在看这个元素，但是，噢，因为 WebIDL 就像是一份描述，我需要去找 C++ 实现，然后它就像你看到的 Claude Code 或者 Codex 那样去逐步推进，并提出某种推论。它会看——它会看某个函数并说：“呵，我想你——你跟我说过这里面有个漏洞。”类似于你所说的，提出一百种变体。也许是这个问题，或者那个问题。然后它会去尝试。它会不断尝试。它尝试了 14 次或 13 次都失败了。然后终于在第 14 次它成功命中了，它找到了漏洞。而且很棒的是，它不仅给出了这种分析——对此我很乐意，你知道，在每一个上面花上几个小时，深入探讨它是如何具体工作的以及为什么重要——但这正是我在 2025 年抱怨收到的那些报告的样式。让这件事情与众不同的是，我们有了这个。

<details><summary>Original English</summary>
And so kind of logistically what this looks like is it says okay um I'm looking at this element but oh because webidl is like a description I need to go find the C++ implementation and it just works through like you would see cloud code or the codeex do and it would come up with some theory. It would look at it would look at some function and say, "Huh, I think you you've told me that there's a bug in this." Similar to what you said, come up with a hundred variations of it. Maybe it's this problem or that problem. And it will try it. And it will keep trying it. And it tries 14 times or 13 times and it fails. And then finally the 14th time it hits and it found it. And the great thing is not only does it come up with this sort of analysis, which I would love to go spend, you know, a couple hours on each of these and do a deep dive on how exactly this works and why it matters, but this is like the shape of the reports that I was complaining about getting in 2025. The thing that makes this different is that we have this.
</details>

所以这是一个非常复杂的那种 HTML 页面。这就是浏览器必须处理的东西，人们制作出这样的页面。他们就像是在创建——呃，这个元素。他们在 DOM 节点上设置所谓的 expando 属性，这就像一个属性但又不是属性。它移除了该元素。它进行了一些循环垃圾收集等等等等。最后它创建了一个——呃，堆释放后使用（heap use after free），这完全就是我们提交给我们工程团队的那种形式的漏洞报告。我想回到最开始，当我们反思这款产品的复杂性时，我刚才正好在想，我们家里决定重温《硅谷》（Silicon Valley）。所以我正在看这些，呃，Gilfoyle 穿着一件 HTML 5 的 T 恤，我刚才就在反思你所说的话，比如无论网页是 25 年前写的，还是昨天由一个 Agent 写的，你都必须去渲染它。因此，在 HTML 页面和 JavaScript 中可能引入的漏洞广度，几乎可以说是无法逾越的。所以我想为可能没有在看视频的人总结一下，就是你拥有这个——这个 Agent，这个 harness，它不仅能够提出假设，推测是什么可能在某个文件或文件的某个子集中造成漏洞；而且你不仅得到一份关于“我认为漏洞源自这里”的文档，你实际上还得到了一个复现——一、一个测试 HTML 文件，随后它能在生产环境中复现该漏洞，你可以借此证明它确实引发了——引发了该问题。这样——我是不是把这一切都正确串联起来了？

<details><summary>Original English</summary>
And so this is like a really kind of complicated HTML page. This is what browsers have to deal with, people making pages like this. And they're like creating uh the element. They're setting what's called an expando property on the DOM node which is like an attribute but not an attribute. It removes the element. It does some cycle collection blah blah blah. And at the end it creates uh heap use after free which is this is exactly the sort of shape of a bug report that we send on to our engineering team. I want to go back to the very beginning when we were reflecting on the complexity of this product and I was just thinking we've decided to rewatch Silicon Valley in my house. So I'm watching these and uh Gilfoil had an HTML 5 shirt on and I was just reflecting on what you said like you have to render the web whether it was written 25 years ago or yesterday by an agent. And so the the breadth of vulnerabilities that can be introduced in an HTML page in JavaScript is it seems almost insurmountable. And so I want to reflect for people who are maybe not watching is you have this this agent, this harness that not only can come up with hypotheses on what could create a vulnerability in a file or a subset of a file. And you not only get a document of this is where I think the vulnerability comes from, but you actually get a rep a a test HTML file that then replicates that bug in production where you can prove it actually creates creates the issue. Is that have I tied that all together correctly?
</details>

>> 那——那完全没错，而这正是让这种方法有别于以往尝试的关键所在。

<details><summary>Original English</summary>
>> That that is exactly the thing and that is the thing that makes this approach different from previous attempts.
</details>

>> 是的。所以我只是希望，你知道，工程负责人、在座的工程师们、在座的资深工程师们能够思考一下这个过程，也就是你知道、呃、某种程度上植入你的 Agent 让它相信你的代码有问题，不管——不管是安全漏洞还是功能性漏洞，对吧，比如我知道这里有东西坏了。我知道从——从性能角度来看这并非最优，也许是这方面的另一个例子。能够针对它运行一个假设循环，然后实际创建一个测试或复——或、嗯、重现产物，这是一个非常强——强大的循环，我不希望大家在把视角拉大到——拉大到 Agent 时忽略了这一点。

<details><summary>Original English</summary>
>> Yeah. And so I just want you know engineering leaders, engineers out there, senior engineers out there to just think about this process which is you know uh kind of incepting your agent to believe that there is something wrong with your code whether whether it's a security bug or a functional bug right like I know something's broken here. I know this is suboptimal from from a performance perspective maybe is another example of this. be able to run a loop of hypothesis on it and then actually create a test or re or um recreation artifact is a really f powerful loop I don't want people to miss as they zoom out into into the agent.
</details>

>> 是的。而且关于你的项目，我只想就此补充一点。我认为其中的一个区别是，我们实际上开源了我们用于 Firefox 的这类工具，嗯，我想其中的一部分就在昨天开源了。所以对于想要测试它的安全研究人员来说，在我们的情况下，我们必须拥有我们所称的非常清晰明确的任务验证信号。因此我们有这个模糊测试构建版本，嗯，它使用了 AddressSanitizer，这就好比你赢或者你输。你传入文件，我们就能告诉你 AD。通常如果你——如果你有一个 Web 应用，某种分布式系统，它可能不会那么

<details><summary>Original English</summary>
>> Yeah. And just I could add one thing on that for your projects. I think that one difference is so we we've actually open sourced the the sort of tooling that we use for Firefox um I think just yesterday for for some of this. So for security researchers who wanted to test it, for our case, we'd have to what we call a very crystal clear task verification signal. And so we have this fuzzing build um that uses an address sanitizer and it's like you win or you lose. You pass the file and we can tell you AD. Often if you if you have a web app, a distributed system of some kind, it may not be so
</details>

<!-- chunk 4/7 -->

一清二楚。所以针对你自己的项目，你真的需要深入思考你的威胁模型，然后考虑你希望如何去验证它是否属实？比如可以是一个测试用例，或者可以……我认为当你在考虑将这些应用到你自己的项目时，那确实是一个非常重要的方面。

<details><summary>Original English</summary>
crystal clear. And so you need to think really hard for your project about your threat model and then how would you like to verify whether it's true or not? like could be like a test case or it could be I think that's actually something to that as you're thinking about applying this to your own project that is a really important aspect of it
</details>

>> 而且我认为大多数人只是……我们还没有形成这种肌肉记忆，即如何如此清晰地阐述成功用例、如何阐述失败用例。你确实从以往的这些成果中获益匪浅，也就是你预先完成了这项工作，所以你已经具备了这些。而且我……我刚刚结束了与一位非工程领域、而是设计领域人员的通话，我说当下正是你实际上必须写下什么是好设计、以及你可能会如何对其进行量化评估或质性评估的时刻。因此，我认为这种能够清晰阐明、测试并衡量结果的能力——无论它们是安全层面的成果、质量层面的成果，还是更软性的成果——正成为人们必须培养的一种硬技能。

<details><summary>Original English</summary>
>> and what I think is most people just we haven't gotten in the we haven't built the muscle memory of how to articulate success cases how to articulate uh failure cases so crisply and it's you really benefiting from this this previous art here which is you've done the work up front and so you have that already and I you I just got off the call with somebody in and this is not engineering in design and I said this is the moment where you're actually going to have to write down what good design is and how you might um quantitatively evaluate evaluate that or qualitatively evaluate it. And so I think this skill of being able to crisply articulate test and measure outcomes whether they are security outcomes, quality outcomes, um softer outcomes is becoming a hard skill people have to develop.
</details>

是的。而且我认为正如你此前指出的那样，对整个项目而言，把这些定义清楚实际上非常好。

<details><summary>Original English</summary>
Yeah. And and I think to to points you've you've made previously like it's actually just great for the whole project to have that defined.
</details>

### MetaView 赞助片段

>> 是的。没错。本期节目由 MetaView 赞助播出，因为谁说招聘非得是公平的？我接触过的每一位创始人、招聘经理和猎头都能感受到同样的压力：尽快招到合适的人才。但招聘极其耗时。达成共识很难，而争夺顶尖人才的竞争也越来越激烈。正因如此，Riot Games、Brex、GitLab 和 Replit 等团队，外加另外 5000 家机构，都在使用智能体招聘平台 Metaview，它赋予了高绩效团队在招聘方面的非对称优势。它的运作方式是为你提供一套行为类似于招聘同事的 AI 智能体，它们可以根据你的确切标准寻找候选人、记录面试笔记、审核每一份投递的申请、在整个招聘流程中收集洞察，并帮助你在人才库中甄别最优秀的候选人。别让竞争对手在招聘上赶超你。Metaview 的客户定岗招聘速度提升了 30%。立即开始使用 Metaview，在 metaview.ai/howiaai 即可免费获取前 100 位候选人推荐。

<details><summary>Original English</summary>
>> Yep. Yep. This episode is brought to you by MetaView because who says hiring has to be fair. Every founder, hiring manager, recruiter I speak with feels the same pressure. Hire the right people as fast as possible. But recruiting is brutally timeconuming. Alignment is hard. And the competition for great talent keeps getting tougher. That's why teams like Riot Games, Brex, GitLab, and Replet, plus 5,000 other organizations use Metaview, the Agentic recruiting platform, giving high performance teams an unfair advantage in hiring. It works by giving you a suite of AI agents that behave like recruiting co-workers, finding candidates based on your exact criteria, taking interview notes, reviewing every inbound application, gathering insights across your hiring process, and helping you identify the best candidates in your pipeline. Don't let your competitors out hire you. Metav customers close roles 30% faster. Get started with Metaview today and get your first 100 candidates sourced for free at metaview.ai/howiaai.
</details>

### 漏洞定位与修复管线

好的，非常棒。我们会在节目说明中分享这个 MCP。如果你想为该项目做贡献，请务必参与进来。那么，我看着这个例子。你知道，你会看到 9 轮、10 轮、14 轮对话，找到了结果并得到了完整的套件。那之后是否会经过某种漏洞修复管线呢？

<details><summary>Original English</summary>
Okay, love this. We'll share this MCP in the show notes. If you want to uh help the project, please please dive in. So, and I'm looking at this example. You know, you're seeing turns of nine turns, 10 turns, 14 turns um finding the result and getting that that whole package. And then does that run through a you know sort of a bug fix pipeline?
</details>

>> 对的。最初并没有。所以实际上这里面很多都是早期的发现，它们并没有走修复流程。但这里有一个很有意思的例子可以看一看，就是这个 nsul content sync。这是一个相当复杂的漏洞，它发现……我们有一项名为 RLBox 的进程内沙箱技术，它旨在帮助我们对第三方依赖进行类似收缩包装的封装隔离，这样如果那部分代码存在漏洞，就不会泄漏到 Firefox 中。这是一个非常复杂的发现，它有大量的构件，而且它大致生成了这些，但有趣的是，提出的修复方案本身非常简单。就类似输入验证而言，它只是说：“噢，你之前在这里做了这样的断言，你应该断言的是那个。”于是我们确实开始基本上让这个补丁智能体针对每个漏洞修复运行。然后很酷的部分在于有人在环参与。所以你实际上可以直接应用该补丁，编译 Firefox，并确认同一个测试不会再崩溃。这非常好。不过，如果我们去看这个漏洞，这些基本上就是我们刚才看的所有那些文件的存储桶转储。团队收到后展开了一些讨论，然后我们大致认为：是的，这看起来像个真正的问题，修复方案看起来也不错，但实际上我们还应该检查其他几个地方。因此，你会在智能体身上看到的现象之一——而且我相信会有测试架构技术、模型也会变得更好——就是它们会对你给它们的任务保持极度聚焦。所以，如果我们去看最终合并的实际漏洞修复，基本正如他们所说。我们对这个进行了检查，但同时我们在另外大概三处地方也检查了同样的内容。这就是各个子组件（无论是 JavaScript、媒体、DOM、布局还是图形）的专家级工程师发挥作用的地方。我们有世界顶级的浏览器工程师在从事这些工作，他们会查看修复方案并说“噢，看起来相当不错”或者“噢，这完全错了”。我们当然会利用这些反馈来努力改进打补丁系统，但我认为我们距离拥有某种能直接生成可合并补丁的“魔法按钮”还相差很远。

<details><summary>Original English</summary>
>> Right. So originally it did not. And so actually many of these were early finds and they don't. But one one of these is an interesting one to look at there which is this um nsul content sync. So this is a pretty complex bug where it found we have an inprocess sandback sandbox technology called RLB box that's meant it's meant to help us wrap kind of shrink wrap around third party dependencies so that if there's a vulnerability in that code it can't leak out to Firefox and this was a really complicated find and it it has tons of artifacts and it it it sort of came up with it but the the interesting thing is the the fix itself is the proposed fix is very simple. It just said, "Oh, you were asserting this. You should have been asserting that." Um, in terms of kind of input validation and so we did start to basically have this patching agent run on every fix. And then the cool part is you're in the loop. So you can actually just apply the patch, build Firefox, and confirm that that same test doesn't crash anymore. And so that's great. But so if we go look at at the bug, you these are basically this is basically a dump of that bucket that we were just looking at all those files. And if we sort of received it by the team, there's some discussion and then we have sort of like a yep, this looks like a real issue, the fix looks good, but actually we should check in a few other places. So, one of the things you'll see with agents, and I'm sure there's harness techniques, the models will get better, is they get laser focused on the task you've given them. And so, if we go look at the actual um bug fix that landed here, it's pretty much what they said. we're we're checking sort of this you know this but also we're checking the same thing in like three other places and so that's where sort of the the expert engineers in every single subcomponent whether that's JavaScript media DOM layout graphics we have people who are like uh worldclass browser engineers who were working on this stuff and we'll look at the fix and say oh it looks pretty good or oh this is like completely wrong and we we um we of course we use that feedback to try to improve the patching system but I think we're pretty far off from having a kind of magic button that produces landable patches.
</details>

### 代码库级系统化修复

>> 是的，这是中肯的提醒。因为我使用过 CodeQL 安全产品，我其实觉得它相当不错，它能帮助你构建威胁模型。它会逐一扫描你的代码，提出问题和补丁。我发现的问题恰恰也是这个，而且我并没有数以千万计的代码行，我只有几十万行代码——它会极度聚焦于那个具体的补丁。它会针对这个漏洞指出补丁就是这个。但它做不到更深一层，比如去在整个代码库中分门别类地找出类似的问题，然后针对这一类（在当前情况下是安全漏洞）提出架构上干净的全局修复。因此我发现这是现有安全工具中所缺失的一块。这确实需要一个在某种程度上熟悉代码库、或者了解代码库结构的工程师来辨识其中的一部分。所以我也确实认为这是其中某些测试架构的下一步方向：针对任何单个修复，形成闭环并提出“我们已经定位了这个漏洞，去代码库的类似部分中识别我们是否存在系统性问题”。然后重新纵观全局，阐明整体修复方案应该是什么，而不是单点修复，接着发布它并关闭所有相关问题。这是一条我一直以来都在手动走的路，现在看到这个，就在思考如何能够更系统化地去实现。

<details><summary>Original English</summary>
>> Yeah, fair fair warning because I have used the um codec security product which I actually think is is quite good and it does uh it helps you develop a threat model. It goes through and scan your code and comes up with issues and patches. The problem that I found was exactly this and I do not have millions and millions of lines of code. I have hundreds of thousands of lines of code which is it will get laser focused on the specific patch. It'll say for this bug, this is the patch. But it doesn't do the next level of like go categorically find similar issues across the codebase and then come up with an architecturally clean global fix for this class of in this instance security bugs. And so I have found that that's a piece missing in the existing security tooling. And it does take like an engineer that kind of knows knows to some extent the codebase or knows the the structure of the codebase to identify some of those. And so I do think this is the next step in some of these harnesses which is for any one fix taking the loop and saying we've identified this issue go in um in similar parts of the codebase and identify if we have this issue systematically. then zoom back out and articulate what the fix is overall as opposed to the point fix and then ship that and then close all the all the related issues is a is a path that I've been doing manually and now as seeing this just thinking about how to do that more systematically.
</details>

>> 是的，我认为正如你之前所说，无论是在检测还是补丁方面，这些需求很多都在某种程度上走向融合。我显然也期望测试架构和模型在这方面变得更好。我确实认为，要让一个达到 Web 浏览器规模和复杂度的项目能够以某种自主的方式进行开发，我们还有很长的路要走；而且我们实际上也有关于必须由人类来编写代码和审查代码的规定，但我们能够使用这些工具来帮助大大加速这一过程。

<details><summary>Original English</summary>
>> Yeah, I think that's as you said earlier that these a lot of these are kind of converging in terms of like the the needs whether it's detection patching and I I obviously I'm expecting the the harnesses and models to get better at this. I do think we're pretty far out from a web browser scale and complexity project being able to be sort of autonomously developed and and we we actually have uh requirements for having you know people who write the code and review the code but we're you know able to use these tools to help accelerate that quite a bit.
</details>

### 开源项目的智能体集成与供应链挑战

嗯，我是说如果我们把这件事提升到元认知层面来看，维护这样一个开源项目是非常庞大的工程。维护这样的东西需要社区的参与，你不可能指望仅仅因为引入了智能体，它的复杂性就会发生改变。我认为开源项目尤其必须去思考我们如何将智能体融入其中、这如何与社区产生交集；我确实认为它们是我们现存的最复杂、且往往是历时最久的代码库。因此很有意思听到你说：在短期之内，我们不会把这个代码仓库直接全盘交给智能体，无论是在安全层面还是在产品层面，大家都皆大欢喜。对吧？

<details><summary>Original English</summary>
Well, and I mean if we just take this to the meta level and you know part of having an open source project like this is it is very large to maintain. It requires you know the community to maintain something like this and you wouldn't expect the complexity of that to change just by nature of you introducing agents. I think in particular open source projects um we'll have to think about how we integrate agents into it how that intersects with um the the community and I do think they are the most complex and often longest standing you know code bases that we have out there and so it's interesting to hear you say you know I don't think overnight we're just going to turn this this repo over to the agents and we're all we're all happy either on the security side or on the product side right
</details>

>> 是的，我认为在安全方面，涉及开源时，供应链也是围绕这一话题极其有趣且重要的一个课题。我认为你……

<details><summary>Original English</summary>
>> yeah and I think on the security side with with open source Supply chain is such an interesting and important topic around this too. I think you
</details>

>> 你……

<details><summary>Original English</summary>
>> you
</details>

>> 必须与每个项目合作，而且有很多重要项目。Firefox 依赖于许多底层的互联网核心基础设施供应链，而每个项目都有不同的需求、偏好、威胁模型以及它们关心的事项，比如它们希望如何处理漏洞、它们在哪里开展工作，这里面存在着一种人际联结和网络问题

<details><summary>Original English</summary>
>> have to work with every project in you know there's a lot of important projects. Firefox depends on many many um just core internet infrastructure supply chain and every project has different needs and preferences and threat models and things that they care about the way they went the bugs where do they work and there's a sort of human connection and network problem
</details>

<!-- chunk 5/7 -->

涉及那里，而我们在供应链中发现了许多漏洞，并且我们和很多这类项目有私交，因此你实际上是在以一种我认为自动化程度比很多人期望的要低的方式去推进。但我认为，这就是这项技术必须在全行业落地铺开的现实。

<details><summary>Original English</summary>
involved there where as we we found many bugs in in supply chain and we we have personal connections with a lot of those projects and so you're kind of working your way in in a way that is I think less automatable than many people would would hope um But I think it's the reality of how this is going to have to just get deployed across the industry.
</details>

### 本地开发环境演示与两代方案对比

>> 好的，这太棒了。我想你和我可以聊这个聊上一整天，但我们来看看在各个工程师的电脑桌面上这具体是什么样的。作为一名工程师，你实际上会如何与它进行交互？

<details><summary>Original English</summary>
>> Okay, this is this is amazing. I think you and I could talk about this all day, but let's show what this looks like at the individual engineers, you know, desktop. How how would you actually interface with this um as as an engineer?
</details>

>> 我们在这里打开 VS Code，我想展示这个测试装置（harness）的几个方面，并把它具象化，让大家切实明白它并没有那么复杂。在我们的演示部分中，我把一个补丁应用到了 Docker 容器内本地构建的 Firefox 上，如果你是一名 C++ 开发者，这个补丁引入了一个非常显而易见的内存安全问题。所以在这个补丁中，我想展示几种不同的方法。大致是我们最初的起点，以及我们后来达到的阶段。在这样的 Docker 环境内部，我们这里有一个简单的脚本，带有一些提示词，说明你正在寻找内存安全问题。读取文件并分析它。因此我们没有给它任何工具的访问权限。我们只是说看一下文件并找出问题所在。你可以很轻松地用 Claude 和 Codex 来运行这个脚本。有一些像 `-p` 这样的命令行参数，你可能在 Claude 中见过，它基本上就是设计给另一个程序运行的，而不是让人类来运行的。所以在这种情况下，如果我们说用 Claude 运行，你会看到这种略显杂乱的 JSON 流式输出，但这其实正是当你进行交互式 Claude Code 会话时底层所发生的事情。它正在读取一堆代码。它大概会相当迅速地聚焦于该文件中的问题，并且基本上会写出一份类似 Markdown 格式的报告。

<details><summary>Original English</summary>
>> We'll pull up VS Code here and sort of there's a couple aspects of the the harness here that I wanted to show off and make really concrete to to bring home the point that it's not too complicated. So, we have um part part of the demo here. I have a patch applied to a local build of Firefox in a Docker container that introduces a really obvious um memory safety issue if you're a a C++ developer. And so, in this patch, I wanted to show kind of a couple different approaches. It's sort of where we started and where we we got to. And so inside of this um Docker environment, we have a um a simple script here that with some prompt that says you're looking for a memory safety issue. Read the file and analyze it. And so we're not giving it access to any tools. We just say look at the file and find the problem. You can e you can run this with both cloud and codecs pretty easily. There are command line arguments like -p you maybe seen um with claude that will it's basically designed to be run by another program not a um not a human. So if we said in this case run with claude you're going to see this kind of ugly JSON streaming out but this is actually what's happening under the hood when you have an interactive cloud code session. It's reading a bunch of code. It's sort of it's probably pretty quickly converge on the problem in this file and it's going to write essentially like a markdown report.
</details>

这就是非常基础的原语级构件，比如你自己用 Claude 在一小时内就能构建并运行它。你也可以用 Codex 来运行它。有一个 `codex exec` 命令，同样让它输出 JSON。你可以让另一个程序来消费它。这算是使用 Agent SDK 之外的另一种替代方案。所以这只是另一种做法，这就是一种非常简单的、关于如何直接运行并找出源代码文件中问题的方法。我想，随着我们将其运行在不那么简单的安全问题上，我们发现我们需要我早前所描述的那个实际的测试装置。所以我们这里有一个运行它的例子，它基本上会执行相同的循环。它使用的是 Agent SDK，但它拥有对所有这些工具的访问权限。所以它会逐一去读取。呃，这会需要一段时间。所以我先切换到一个已经完成的任务上，但它基本流程是先读取，再做一些测试。它会把这个 HTML 页面作为测试用例来运行，然后它会说：“是的，看起来没问题。”此时实际上是验证器子 Agent 返回了一些结构化的 JSON，表明：“是的，我核准了它。以下是为什么这是一个问题。以下大致是具体如何去利用它。这是复现步骤，这是安全影响。”到那一刻，你就有了结果，有了归类，我们就可以把它放进我们的缺陷追踪系统中并交给工程师。它现在确实会派生出一个单独的 Agent 去实际修复该漏洞，所以它会继续进行，构建 Firefox 并验证崩溃问题是否消失，我——

<details><summary>Original English</summary>
And so this is just like the very basic primitive building block like you could build this and run this yourself uh in an hour with claude. You can also run it with codec. There's a codec exec command. Um similarly have it output json. You can have another program that's consuming that. um this is sort of an alternative to using an agent SDK. So just another way to to do it and so that's that's a very simple kind of how do you just run this thing and find a problem in a source code file. I think as we are running this on less trivial security issues, we found that we needed the actual harness that we I was describing earl. And so we'll have an example running that here where it will basically do the same loop. It's using an Asian SDK, but it's going to do it has access to all of these tools. And so it's going to go through and read. Uh, this will take a while. So, I'll switch over to a completed uh job here, but it'll basically read it'll do some tests. It'll run this HTML page as a as a tester, and then it'll say, "Yep, looks good. Um, this is actually the verifier sub agent has now returned some structured JSON saying, "Yep, I approved it. Here's why this is a problem. Here's sort of exactly how you would uh exploit it. here's the steps to reproduce and here's the security impact that at that point you have the results you have the bucket we could go and put this in our bug tractor system and and give it to an engineer it does spin off a separate agent now to actually go and fix the bug and so it will go on and um you know create it build firefox and verify that the crash went away I
</details>

### 代码库优先级评估与启发式打分机制

>> 我觉得这非常直截了当。我认为你再次为大家揭开了谜底，证明大家完全可以构建出来——我的意思是，v1 版本其实就是直接用提示词运行 Claude Code，对吧？它并不复杂。然后 v2 版本则是运行带有极其实用的工具集的 Agent SDK，并在最后由一个子 Agent 来运行验证循环。你知道，我的问题是，面对所有这些文件、所有这些代码行，你该如何确定将 Agent 引导向何处的优先级？因为正如你所说，你不能直接把整个代码库扔给它说“找出里面的安全问题”，我们明知问题存在。你们究竟是如何确定去哪里排查的优先级的？

<details><summary>Original English</summary>
>> I think this is very straightforward again I think what you're demystifying for folks is you can you know build I mean v1 is literally just running cloud code with prompt right it's Not it's not very fancy. And then you know v2 is running an agent SDK with a set of like very useful tools and a sub agent that runs a verification loop at the end. You know my question for you is with all these files with all these lines of code how are you prioritizing where you point the the agent? Because as you said you can't just go like here's my codebase find the security issues we know they're there. How are you actually prioritizing where to look?
</details>

是的，这也是我们在规模化过程中遇到的问题之一。部分预先打包的技能和工作流预先假设你可以一次性扫清整个代码仓库并找出所有问题，但你根本做不到。对于 Firefox 而言——我想说，对于小型项目，我认为那是可行的，而且可能是一个简单的起步方式。因此我们采用的是一个极其简单的大语言模型裁判机制，我们大致说明你是一名安全专家。以下是我们正在查看的不同类型的文件：C++ 文件、IPDL 文件、Web IDL 文件，以及关于每种文件的简要说明。我们大致摘录了现有安全漏洞分类程序中的一些具体细节，基本上让它给出两项评分：一个评分是你认为存在内存安全问题的可能性有多大，另一个评分是从网页访问该文件的难易程度如何？因为我们有大量代码根本就不会在内容进程中运行，它执行的是操作系统集成的功能。因此我们可以极其简单地运行它。你也可以在自己的项目上非常轻松地设计出类似的东西。我们只要运行一下，它基本上就会生成一份评分报告，接着我们会让它输出为 Markdown 内容，并且它会指出，比如 `document.cpp` 是一个巨大的文件，可以直接被网页内容访问，得分非常高，你绝对应该去跑这个文件。随后我们会接入不同的信号，比如我们之前针对这个文件运行了多少次？它是否发现了重复的问题？它是否能找到漏洞？这都是非常非常简单的启发式规则，在这个领域我们实际上正在积极改进，但它已经足以让你起步了。

<details><summary>Original English</summary>
Yeah, and that that's one of the things we've run into with scale. Some of the sort of prepackaged skills and workflows sort of assume that you can canvas the entire repository at once and find all the issues and you just can't. And so with Firefox, I would say I would say with a small project, I think that's that's plausible and probably a simple way to start. So what we are doing is a really simple sort of LLM judge here where we sort of say you're a security expert. Here's the different kinds of files we're looking at. C++ files, IPL files, web IDL files, a little bit of detail about each. We've sort of copied out some of the um the details that we have on our existing security bug classification program and basically give me two scores. So one score is how likely do you think there's a memory safety issue and another is how easy could you access this from a web page? Because we have a lot of code that is not running ever in the content process at all. It's doing operating system integration things. And so we can just run that um you know very very simply. You could uh you could come up with something yourself on your own project very easily. We just go and run that out. That's going to generate basically like a a scores report and then that will we have that right of markdown thing and it'll say okay like document.cpp that is a um huge file. that is directly accessible by uh web content that is like a very high score. You should definitely run that. We'll we'll then like plug it in with different signals like how many times have we run this file before? Has it found duplicates? Was it able to find issues? But really really um simple s uh heristics and this is an area where I'm uh we're actually actively working to improve this but it's enough to get you kind of started.
</details>

我觉得这太巧妙了，非常聪明。即使对于那些代码库规模达不到 Firefox 级别的人，或者其产品的威胁模型与漏洞受攻击面不同的人来说，我也确实认为这种思路——我总是听到有人问：如何清理我单个巨型仓库（monorepo）里的技术债？我该如何确定这些事情的优先级？我不能只笼统地说“修复技术债”。我认为，能够梳理你的代码库并为 Agent 筛选出优先排查和修复的区域，无论是出于安全还是性能考虑，都是非常有价值的。坦白讲，想到这一点时，我联想到了产品经理和设计师：你可以构建一个非常相似的启发式评分机制，对它说：“去调取我 Web 应用中的所有前端组件以及我的产品分析数据，从用户体验或转化率的角度给我一份需要改进的组件优先级清单，

<details><summary>Original English</summary>
I just think this is so so clever, very smart. And even for folks that don't have the codebase at the scale of Firefox or maybe don't have the same um threat model vulnerability surface area as your product does. I do think this idea of taking I hear all the time like how do I attack tech debt in my monor repo? How do I prioritize these things? I can't just say like fix fix tech debt. Um, I think the ability to go through your codebase and prioritize areas for an agent to triage and fix, whether that is security, whether that is performance. Honestly, when I was thinking this, I was thinking for product managers and designers, you could build a very similar heristic scoring mechanism where you say, "Go take all my components, my front-end components in my web app and my product analytics and give me a prioritized list of components to improve from a user experience or conversion rate perspective
</details>

>> 然后去应用关于设计和转化率的最佳实践。”所以，利用大语言模型对代码的优先级进行打分，然后施加非常具体维度的修复，有着极其广泛的应用方式，这远好过让它“把我的整个代码库都过一遍并提升转化率”。

<details><summary>Original English</summary>
>> and then go apply best practices on design on conversion rate." So, like there's just so many ways you can take this like LLM scoring of a prioritization of your code and then apply a very specific level of fix to it versus saying like go all over my codebase and make it convert better.
</details>

>> 所以我希望大家真正去思考如何制定出一套用于划分优先级的打分机制，尤其是当你在一个大型巨型仓库中工作时，因为这种非常具体的策略在很多方面对大家来说都非常有用。

<details><summary>Original English</summary>
>> And so I want folks to really think about how to come up with a score to prioritize things, especially if you're working with a large monor repo because there's so many ways that this just very specific tactic is is useful for folks.
</details>

是的，我花在这上面的时间比我原先预想的要长，最初有点像：“嗯，我觉得这些文件可能是值得处理的好对象”，然后突然意识到：“噢，真是笨，我们应该给这些东西打分。”我想我们还看到，你可以设想将其用于提交扫描（commit scanning），对吧？因此如果你的项目较新且代码量不大，相比扫描现有的文件结构，你实际上会想要查看单个提交并对这些提交进行打分，然后将它们送入流水线处理；或者，我们在性能方面也有正在推进的工作，当然你会有一个性能基准测试，它会给出一个分数，然后你告诉 Agent——

<details><summary>Original English</summary>
Yeah, I it took me it took sort of longer than I would have liked to to put this in place where it's sort of like, well, I think these files might be good ones to do and it was like, oh, duh. We should like have these things get scored. I think um we had uh we've also seen like you could imagine doing this with commit scanning, right? So if you have a newer project with not much code, instead of scanning the existing files structure, you actually want to look at individual commits and score those commits and then run them through a pipeline or we we have active work on performance as well where of course you have a performance benchmark. It gives you a score and you tell the agent
</details>

<!-- chunk 6/7 -->

你的任务就是让那个数字降下来，然后它就会提出各种各样的性能优化方案，这其实是同一个思路。它提出一些提议，你有一个类似验证器或裁决器的东西来生成结果，进入一个流程中供工程团队查看并排定优先级，这种模式在很多领域我都看到在被反复采用。

<details><summary>Original English</summary>
 your job is to go make that number go down and it'll go come up with all kinds of performance optimizations and it's actually the same idea. You it comes up with some proposals. you have a kind of verifier or judge that produces it that gets into a pipeline that the engineering teams can look at and prioritize and um it's it's a it's a pattern that I'm seeing kind of repeated across many domains.
</details>

>> 是的。而且我觉得人们常常会自我暗示，觉得 AI 修复 Bug、AI 生成代码几乎是无限且免费的，因此你可以用 AI 代码铺满整个世界。但首先，预算不允许；其次，交付、审查、验证 AI 代码实际上都是有时间成本的。所以你根本不可能完全不做优先级排序，尤其是当面对那些需要验证的修复方案，而且它们甚至需要运行 14 轮循环才能得出“是”或“否”的结论时。我认为这种预先排定优先级的做法是非常聪明的运用，这样你就可以适当地分配算力。

<details><summary>Original English</summary>
>> Yeah. And the other thing I think people you know kind of tell themselves that AI bug fixes AI code is almost like limitless and free and therefore you can like cover the earth with with AI code but one budgets shall not allow. too. There is actually a time cost to shipping, reviewing, um, verifying AI code. And so you cannot go completely prioritizationfree, especially when you're looking at the kinds of fixes you need to verify and they're taking 14 loops to to even get to a yes no. I do think this like pre pre- prioritization is a very clever um use so you can allocate compute appropriately.
</details>

是的，留给影响最大的事项。

<details><summary>Original English</summary>
Yes. the highest highest impact impact things.
</details>

是的，我们当时……为了让你大概感受一下，你知道，我们之前展示过那个图表。在 Mozilla 内部，这可以说是一次类似事件响应级别的行动，我们在 Slack 上建了一个将近 100 人的频道。我想作为这项举措的一部分，我们有 100 位工程师合入了修复。所以情况往往是：“嘿，我们发现了 60 个新 Bug。我们把这个团队、那个团队以及其他团队都拉进来吧。”然后就会有……我认为有大量的工作。这确实需要重新排定优先级。随着我们经历这个过程，大家都很疲倦，但同时也非常充满动力并被动员起来，尤其是因为你拿到的是这种极具可操作性的报告。

<details><summary>Original English</summary>
Yeah, we had like um just to give a sense of you, you know, we showed the graph earlier. This was a sort of incident response level event within Prozilla where we had a slack channel with you know uh almost 100 people. I think we had a 100 engineers land fixes as part of this initiative. And so it would be hey we found 60 new bugs. Let's pull in like this team and that team and the other. And then there's there's um I think a lot of work. It did require some rep prioritizing. Everybody was very tired as we've sort of gone through this, but also really motivated and and mobilized in particular because you were getting this very actionable reports.
</details>

### 总结与快问快答

>> 太不可思议了。对于坚持听到这里的听众，我只想重复一下我们到目前为止梳理过的内容。在一个月内，你们上线交付了将近 500 个安全修复。其中很大一部分可能归功于模型，也有一批归功于测试 Harness。这个 Harness 并不那么复杂，任何人都可以复制。它实际上就是一个针对预设问题的类 Goal 或 Ralph 风格的循环。一个验证子循环，一堆可以直接由工程师运行的工具。你们复用了这些模型提供商提供的大量 SDK，并且对重点攻坚的文件排定优先级，从而确保你们所关注的是优先级很高的修复项；然后你们围绕这种全新的工作方式动员起一支团队，人类并没有被排除在循环之外。人类的生活只是变得更好了。尽管数量非常庞大，但质量也更高，可操作性也更强。你们能把这些公开分享出来真是太慷慨了。我认为很多工程团队尤其是会从这项工作中受益良多。在我们放你回去处理所有这些 AI Bug 报告之前，先来一轮快速问答。我的第一个问题，好奇的人们很想知道：这到底是模型的功劳，还是 Harness 的功劳？是 Mythos，还是说……如果你必须给出划分比例，你认为这个巨大的突破、这张神奇的图表源自哪里？

<details><summary>Original English</summary>
>> Amazing. Well, I just to for people that have made it this far, I just want to repeat what we've gone through so far. You, you know, shipped almost 500 security fixes in one month. A lot of that may have been modeled. A bunch of that was harnessed. The harness is not that complicated. Anybody can replicate it. It's really a goal or like Ralph style loop against a presumed problem. A verification sub loop, a bunch of tools can be run directly by an engineer. You're reusing a lot of the SDKs provided by these model providers and you're prioritizing the files you go after so that what you're looking at um is is a high priority to fix and then you are mobilizing a team around this new way to work and humans are not out of the loop. Humans lives are just a lot better. Um even though the volume was very high, the quality was also higher and the actionability was higher. Um this is so generous of you all to share. I think so many engineering teams in particular are going to get a lot out of this work. Before we let you go and do a quick lightning round question and we'll get you back to all these AI bug reports. Um my first question inquiring minds have to know is it is it model or is it harness? Was it Mythos or you know like if you had to do a split where do where do you think the this huge unlock this magic graph came from?
</details>

>> 当然，两者都有。我认为要划分比例是一个很难回答的问题。我们看到过很多例子，即便不是最新的前沿模型，只要把 Harness 对准许多其他模型，也能找出 Bug。因此光凭这一点，我就想讨个巧，说是五五开吧。我认为在 Harness 层面和工作流 Pipeline 层面，仍然有非常多的创新空间。就像是每做一件事你就会冒出 30 个想法，然后根据尝试的结果，之后又会产生 30 多个新想法，对我来说，这正是一个信号，表明这里面仍然有大量的事情可做。

<details><summary>Original English</summary>
>> Yeah of course of course it's both. I think on the split percentage is a is a tough question. We have seen um examples of being able to point the harness with with many models even like not the latest frontier ones and being able to find pugs. And so just that makes me think, you know, take a take a cheap answer and say sort of 5050. Like I think there's so much to still innovate on the harness side and the pipeline side. Like there's this feeling of having sort of 30 ideas of every one thing you did and then after that you had 30 more based on on uh what you tried and that is to me a signal that there's just a ton to do here still.
</details>

>> 太棒了。然后我的第二个问题是，考虑到我们在过去甚至仅仅三个月里在互联网供应链方面的经历，我对这方面感到相当焦虑。作为帮助管理最大开源项目之一的人，在 AI 时代你是一个安全悲观论者吗？或者说，我们应该对此抱有怎样的感受？我们应该感到害怕，还是应该抱有希望？

<details><summary>Original English</summary>
>> Amazing. And then my second question which is I feel a lot of anxiety around this um just given kind of our experience supply like internet supply chain over the last even three months. Are you as somebody who is um helping steward one of the largest open source projects? Are you a security doomer in the age of AI or how do you how should how should we feel about this? Should we be scared or should we feel hopeful?
</details>

>> 怎么说呢，我是谨慎乐观的，相比于基准线，这大概比很多人都要乐观得多。我认为现实是，这些 Bug 已经存在了很长时间，之前受限的只是发现环节。找到这些 Bug 真的非常困难。但我们的目标并不是留存一堆难以发现的 Bug，我们的目标是零 Bug。所以随着我们和其他防御者开始应用这些工具，我认为它们实际上让我们离那个世界更近了一步。我认为在这些工具逐渐被采用的过程中，未来一段时间道路会是坎坷的，而且不同项目的 Bug 深度也会有所不同。所以确实有理由感到担忧和紧张，但我想说，总体而言我对最终的结果持乐观态度。

<details><summary>Original English</summary>
>> You know I'm cautiously optimistic which compared to a baseline is probably um much more optimistic than many people. I think that the reality is the these are bugs that have existed for a very long time and what was gated before was just on discovery. It's really hard to find these bugs. But our goal is not to have a bunch of bugs that are hard to find. Our goal is to have zero bugs. And so I think that these tools as us and other defenders are starting to apply them actually get us closer to that world. And it is going to be a a bumpy road I think for for some time as um these are getting adopted and we we you know um different projects are going to have different depths of bugs as well. So it definitely uh there there is reason to be concerned and nervous but I think also I would say I'm I'm generally optimistic about how this could turn out.
</details>

>> 我太喜欢了，你给了我信心，也让我没那么紧张了。而且你还给了我更多工具，所以我感觉自己获得了赋能，能够用类似的框架亲自去解决其中的一些问题。我的最后一个问题，也是我问每个人的：当 AI 没有按你预期的去做、当它就是给不出想要的结果时，你的 Prompting 技巧是什么？你如何让 AI 顺从你的意愿？

<details><summary>Original English</summary>
>> I I love you you've given me confidence. You've made me well less nervous also. you've given me more tools. So, I feel like I am um empowered to go solve some of these problems myself with with similar frameworks. The last question I have ask everybody um when when AI is not doing what you want, when it is it is just it's it's not giving um what is your prompting technique? Um and and how do you bend bend AI to your will?
</details>

我想说，对于纯聊天机器人，我是一个非常枯燥的用户，往往就是把文档粘贴进去，说“给我反馈”，然后我手动把这些反馈移植回文档中。我只是喜欢掌控这个过程，并把它作为我自己探索和学习的途径。我认为从写作的角度来看，这样做收获颇多。至于写代码，这取决于我在做什么。我发现——我觉得这在某种程度上是潜意识的——如果我在做一些有创意的事情，比如开发我刚才展示的仪表盘，我就会更加积极正面，我会说：“噢，太棒了，咱们再尝试其他三个想法吧。”然后如果我是在做类似系统管理的事情，比如排查这台虚拟机为什么挂掉了，而它没有按我要求的做，我就会说：“拜托，连这都搞不定吗？”我还发现，有时在写代码时，如果它写出了一些非常愚蠢的东西，我就会直接复制那段代码，在末尾加上一个词“真的吗”，重新粘贴进去，它就会自己弄明白了。

<details><summary>Original English</summary>
I would say for for like pure chat bots, I'm a very boring user and sort of I I'm you know pasting docs in and saying give me feedback and then I'm manually porting that feedback back into the doc. I I just like to have control over the process and and use it as my own exploration and and learning. I think there's a lot out of that from just a writing standpoint. For coding, I am like it depends on what I'm doing. I found and I think this was somewhat subconscious but like if I'm doing something creative maybe I'm building like the dashboard I was showing I'm much more positive and I said you know oh this is so great like let's try three other ideas you know and then if I'm doing like a system administrative thing you know figure out why this VM died and it's not doing what I want I'm like come on like can't do I I've also found like sometimes on the code if it puts something really silly I will just copy that block paste it back in with the word really at the bottom and it'll figure it out.
</details>

>> 我发现自己最近在 Codex 里也经常这样引导，直接说：“不，你这么做太离谱了。求求你，赶紧打住，这根本不行。”太有意思了。好了，Brian，你和整个团队公开分享这些内容真是太慷慨了，带我们看到了幕后你们是如何把这项工作做成的。大家可以在哪里找到你，我们又能提供什么帮助呢？

<details><summary>Original English</summary>
>> I have found myself lately honestly like steering in Codeex and being like, "No, what you are doing is crazy. Like, please, please stop. This is not good." I love this. Well, Brian, you um and the whole team have been so generous sharing this publicly, you know, showing us behind the scenes how you got this work done. Where can we find you and how can we be helpful?
</details>

>> 我平时不太上网。我在 LinkedIn 上，我有一个网站，偶尔会在上面发帖。我在开源项目中做了很多工作，所以我在 GitHub 上很活跃。我认为大家应该使用 Firefox。很多人在 Chrome 推出时可能都换成了 Chrome，坦白说原因很充分，因为在当时它是一款更好的产品，而我们花了一些时间才赶上来。但我们在基本功方面做得非常出色，比如人们关心的性能。我们今天谈论的安全也是如此。我们正在做很多新功能开发，特别是对这里的听众来说，我认为大家对 AI 持有一种独立的态度，因此无论选择哪个提供商，你都不会把你的浏览器厂商与你的 AI 模型提供商捆绑在一起。我们是一个开源项目，背后有一支优秀的团队，所以我只想说，不妨试一试，我想你会满意的。

<details><summary>Original English</summary>
>> I'm not on my I'm not on much online. and I'm I'm on LinkedIn and um I I have a a website that I occasionally post to. I do a lot of work uh you know in open source projects and so I'm I'm active on GitHub. I think people should use Fireart Fox. I I think a lot of people probably switched to Chrome when it came out and honestly for good reason like it was a better product at the time and it took some time for for us to catch up. But we're doing really great on fundamentals, you know, things that people care about performance. We're talking about security today. doing a lot of new feature work and in particular for for this audience um I think have sort of an independent uh mindset around AI and so choosing whatever provider you want you're not sort of combining your browser vendor with your you know with your AI model provider you open source project we have great team behind it so I just say give it a try and I I think you'll be happy with it
</details>

>> 我来为你宣传一下，我要给收听这期播客的听众一个理由：我敢保证，收听这期播客的每十个人里有九个，他们的浏览器现在都是笔记本电脑上占用内存排在第一或第二的吞噬者，因为它不仅供人类使用，也在供智能体使用。值得多方对比体验一下，看看你的体验会有什么变化，既然……

<details><summary>Original English</summary>
>> and and I will hype you up and I'll give people who are listening to this podcast a reason why which is I guarantee you nine out of commend people listening on this podcast, their browser is their number one or number two memory suck on their laptop right now because it is being used by humans, is being used by agents. It's worth doing a little competitive shopping and seeing what your experience looks like since
</details>

<!-- chunk 7/7 -->

我们现在不仅是网络工作，连 AI 工作都如此依赖浏览器。Brian，今天聊得太棒了。感谢你做客《How I AI》。
<details><summary>Original English</summary>
we're all so dependent on the browser for um not just our our web work, but also our AI work. Brian, this has been so great. Thank you for joining How I AI.
</details>

>> 谢谢你，Claire。
<details><summary>Original English</summary>
>> Thanks, Claire.
</details>

>> 非常感谢大家收看。如果您喜欢本期节目，请在 YouTube 上点赞并订阅，或者更棒的是，留下您的想法和评论。您也可以在 Apple Podcasts、Spotify 或您最喜欢的播客应用中找到本播客。请考虑给我们评分和评价，这将帮助其他人发现这个节目。您可以在 howiipod.com 查看我们所有的剧集并了解关于本节目的更多信息。我们下次再见。
<details><summary>Original English</summary>
>> Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.
</details>