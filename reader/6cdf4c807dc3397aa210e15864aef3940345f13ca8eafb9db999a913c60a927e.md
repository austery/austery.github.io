---
author: How I AI
date: '2026-06-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Idjt53tTv2U
speaker: How I AI
tags:
  - agentic-testing
  - vulnerability-scanning
  - automated-bug-fixing
  - developer-tooling
title: 智能体安全防御：Mozilla 如何利用 Claude Mythos 自动修复数百个 Firefox 漏洞
summary: 本文深入探讨了 Mozilla 团队如何构建定制化的智能体扫描套件，结合 Anthropic 未公开的 Mythos 模型，自动发现并验证了 Firefox 浏览器中近 500 个安全漏洞。文章详细阐述了基于 LLM 的文件优先级评分、智能体自主生成测试用例与模糊测试闭环验证、以及自动化补丁生成的实操方法，揭示了智能体时代下软件防御与人机协作的全新范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Mozilla
products_models:
  - Firefox
  - Claude
  - Mythos
media_books: []
status: evergreen
---
### 规模化挑战与优先级评分

Firefox 浏览器拥有数万个源文件和数千万行代码，如果让 **大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）无差别地全量扫描，其上下文窗口（Context Window）和计算成本都将面临无法承受的上限。为了打破这种算力与维度的瓶颈，Mozilla 引入了一个极其精简的“LLM 裁判”（LLM Judge）评分机制进行预过滤。通过编写简洁的提示词，让智能体扮演安全专家，从“代码中出现**内存安全漏洞**（Memory Safety Vulnerability: 由于内存管理错误导致的系统安全漏洞）的概率”以及“从外部网页访问该代码的难易度”两个维度对所有文件（如 C++ 文件、XML 文件等）进行打分。例如，直接暴露在前端的 `document.cpp` 会获得极高的优先级评分，从而使团队能精准把控计算预算，在最关键的漏洞暴露面上分配算力，这也彻底改变了传统安全工具对整个代码库漫无目的地进行静态分析的低效局面。

在建立这种智能过滤机制后，具体的漏洞定位与模拟攻击便交由智能体在高度隔离的环境中自主进行，其核心的自主验证逻辑如下：

<details>
<summary>Original English</summary>

Firefox has tens of thousands of source code files and tens of millions of lines of code. It's not possible to say one shot, go find all the potential bugs in this project. It's way too much context for the model. 

And so we have to do some initial sort of scoring to indicate which files do we want to actually point this thing at. We can talk more about that later, but it eventually kind of comes up with some prioritized list of which files to target. There are even functions in certain cases.

So what we are doing is a really simple sort of LLM judge here where we sort of say you're a security expert. Here's the different kinds of files we're looking at. C++ files, IPL files, web IDL files, a little bit of detail about each. We've sort of copied out some of the details that we have on our existing security bug classification program and basically give me two scores. So one score is how likely do you think there's a memory safety issue and another is how easy could you access this from a web page? Because we have a lot of code that is not running ever in the content process at all. It's doing operating system integration things. And so we can just run that very simply. You could come up with something yourself on your own project very easily. We just go and run that out. That's going to generate basically like a scores report and then that will we have that write of markdown thing and it'll say okay like document.cpp that is a huge file. That is directly accessible by web content. That is like a very high score. You should definitely run that. We'll then like plug it in with different signals like how many times have we run this file before? Has it found duplicates? Was it able to find issues? But really, really simple heuristics, and this is an area where we're actually actively working to improve this, but it's enough to get you kind of started.

I think the ability to go through your codebase and prioritize areas for an agent to triage and fix, whether that is security, whether that is performance. Honestly, when I was thinking this, I was thinking for product managers and designers, you could build a very similar heuristic scoring mechanism where you say, "Go take all my components, my front-end components in my web app and my product analytics and give me a prioritized list of components to improve from a user experience or conversion rate perspective and then go apply best practices on design on conversion rate." So, like there's just so many ways you can take this like LLM scoring of a prioritization of your code and then apply a very specific level of fix to it versus saying like go all over my codebase and make it convert better. And so I want folks to really think about how to come up with a score to prioritize things, especially if you're working with a large monorepo because there's so many ways that this just very specific tactic is useful for folks.

Yeah, it took me longer than I would have liked to put this in place where it's sort of like, well, I think these files might be good ones to do and it was like, oh, duh. We should like have these things get scored.

</details>

### 智能体闭环与漏洞验证

一旦高优先级的目标文件被锁定，主智能体循环（Agentic Loop）便会启动。系统将为智能体注入预先构建的假定上下文——“假定该文件存在安全隐患”，并配备了一系列诸如文件搜索、代码编译等数十个自动化工具。智能体会像黑客一样自主探索代码库的关联结构，试图还原出如何从一个恶意网页发起跨边界调用来触发漏洞。最关键的突破点在于，智能体不会止步于理论分析或输出格式化的报告，而是会自动生成一段高保真的 HTML 测试用例，并将其送入 Mozilla 运行数十年的**模糊测试**（Fuzzing: 一种通过输入随机或半结构化数据来发现软件漏洞的自动化测试技术）基础设施中。通过**地址消毒剂**（Address Sanitizer: 一种用于检测内存越界、释放后使用等安全问题的编译器工具）实时监控测试结果。如果系统未发生崩溃，测试反馈会立刻回传给智能体，驱使它自动调整参数重新尝试，有些极其隐蔽的漏洞甚至需要反复尝试 14 次以上才被成功捕获。这种 Relentless Loop（无情重试循环）不仅杜绝了传统 AI 工具中常见的“幻觉”和假阳性报告，还让智能体彻底告别了“空谈”，实现了基于运行时行为的闭环验证。

在成功模拟漏洞并获得崩溃报告后，如何将这些散落的崩溃数据转化为安全团队能够直接使用的资产，是打通自动化防御生命周期的关键：

<details>
<summary>Original English</summary>

I think people really underappreciate the relentless tedium that an agent will go through. Anybody who's done this kind of what I call archaeology, it's really hard to do. And this is something that the coding agents are great at. 

And the ability to take an agent, give it a very constrained problem in surface area and say exhaust every attempt at this is really powerful. Again, not because human intelligence couldn't identify similar issues, but actually our like cognitive energy declines over time in a way that agents don't.

And so that goes into this what we sort of a main agentic loop, but you can almost think about this as like a Claude session or a Codeex session where you have some custom prompt that says here's a check out of Firefox. Here's some tools to kind of look around the codebase. Here's your target file within that file. We kind of lie and we say we know there's a security bug in this file. You have to go find it basically. And it will just start working its way from the code to reason about how do I get into this code from a web page. So it's some evil web page. How could it actually call this line of code? And it's interesting to watch. It'll kind of think and move its way around, but ultimately it will come up with HTML test cases basically. And we plug this in to our existing tooling infrastructure that we've had for decades to do fuzzing, for example, where you can pass a test case and get back a report as to whether there's a potential memory safety issue. 

That will then get feedback from that tool whether it succeeded or not. And if it didn't, it goes back and starts again. And it can start many, many times and run for a very long time. Sometimes it will end up and say, "Nope, couldn't find anything." Other times it will say that it found something and we ask for it to come out in a very structured format so that we can pass it on to the next phase which is verification. And so we've already kind of verified that there is a crash because we got the signal out of our fuzzing build. But sometimes the agents do just wonky things. For example, it might set a pref that was only ever meant for testing and no user ever sets. Or I've even seen cases where the agent changes the code to introduce a vulnerability so that it can exploit it and achieve its goal. And so we have another agent that's kind of looking at it and saying like does this look right? That usually approves it. Sometimes it does reject it and it kind of sends it back to do more work. But by the time that this happens, we have almost no false positives on this system which is fixing that kind of slop problem that we talked about at the start. And it's very well prepared to go into the rest of our bug pipeline.

For our case, we'd have to what we call a very crystal clear task verification signal. And so we have this fuzzing build that uses an address sanitizer and it's like you win or you lose. You pass the file and we can tell you. Often if you have a web app, a distributed system of some kind, it may not be so crystal clear. And so you need to think really hard for your project about your threat model and then how would you like to verify whether it's true or not.

If you asked a human to say like try 150 different things against this and look at it every single time and make an evaluation, it would be both very time inefficient and exhausting. And so I just love these ideas of these like relentless loops on agents. The other thing that I want to call out is putting a guard rail whether that's a verifier sub agent or a constraint on these goal style loops is really important because of exactly what you said. I gave this example of let's say you're trying to reduce P95 latency on a page. Well, you could remove every latency introducing feature from that page. You could actually like take it away and the agent would be like look I made the goal it's much faster now but you don't have that guardrails of like nothing from a product perspective can change you can't introduce new code.

So if you notice our bug ids for these new bugs are 2,25,977. So, there's many many bugs in Bugzilla. If you find a bug that is in the six digits, it's a very old bug. And so it was kind of funny for this exact XSLT one I wanted to say like when was this bug introduced and anybody who's done this kind of what I call archaeology is it's really hard to do and this is something that the code agents are great at. So I would say when was this bug introduced? Well the file got renamed three years ago and so you can't just do a git diff and then actually this blob moved to that file. It's very annoying work. And I asked Claude, go figure out like semantically when this bug was introduced. And it I was like watching it do git commands I didn't even know existed to go kind of taking notes as it was doing it when it was doing. So really interesting. That's how we had gotten that 20-year-old number.

And so if we look at like this legend one, the tool that uses to do browser evaluator it tried 14 times. And so kind of logistically what this looks like is it says okay I'm looking at this element but oh because webidl is like a description I need to go find the C++ implementation and it just works through like you would see Claude or Codeex do and it would come up with some theory. It would look at some function and say, "Huh, I think you've told me that there's a bug in this." Similar to what you said, come up with a hundred variations of it. Maybe it's this problem or that problem. And it will try it. And it will keep trying it. And it tries 14 times or 13 times and it fails. And then finally the 14th time it hits and it found it. And the great thing is not only does it come up with this sort of analysis, which I would love to go spend a couple hours on each of these and do a deep dive on how exactly this works and why it matters, but this is like the shape of the reports that I was complaining about getting in 2025. The thing that makes this different is that we have this. And so this is like a really kind of complicated HTML page. This is what browsers have to deal with, people making pages like this. And they're like creating the element. They're setting what's called an expando property on the DOM node which is like an attribute but not an attribute. It removes the element. It does some cycle collection. And at the end it creates a heap use after free which is this is exactly the sort of shape of a bug report that we send on to our engineering team.

</details>

### 自动化打补丁与 DevX 整合

在完成漏洞的自主定位与验证后，Mozilla 的智能体架构会衔接至**自动化补丁生成**（Automated Patching: 智能体自动生成修改代码以修复缺陷的过程）阶段。补丁智能体会在安全上下文中生成代码修改方案，将其应用到 Firefox 的本地构建中，并重新运行前述的 HTML 恶意见证用例。只有当编译器和地址消毒剂确认崩溃完全消失时，该补丁才会进入 Bugzilla 漏洞跟踪系统。这一流程完美诠释了**开发者体验**（Developer Experience: 开发者在开发、维护软件过程中的整体效率与体验）工具链对智能体潜能的倍增效应。正是因为 Mozilla 长期在测试自动化和 DevX 上的重度投入，智能体才能像一位真正的工程师一样，流畅地调用 Docker 容器、构建脚本和 CI/CD 管道。这不仅仅是模型的胜利，更是深层系统工程的胜利。对于中小型团队而言，即便没有千万行代码的规模，尽早把测试与验证场景编写成机器可读的断言，也是让 AI 真正为工程提效的唯一途径。

随着自动化验证的成熟，这一链条正在重新定义开源社区的代码合并与供应链安全协作模式：

<details>
<summary>Original English</summary>

As we had continued to work, we added a patching agent which is meant to kind of generate a plausible fix, verify that that fix has resolved the security issue. And all of that it just gets written into a pretty simple cloud orchestration system that writes it out to a storage bucket for consuming later in the rest of our pipeline.

Originally it did not. And so actually many of these were early finds and they don't. But one of these is an interesting one to look at there which is this nsURLContentSync. So this is a pretty complex bug where it found we have an in-process sandbox technology called RLBox that's meant to help us wrap kind of shrink wrap around third party dependencies so that if there's a vulnerability in that code it can't leak out to Firefox and this was a really complicated find and it has tons of artifacts and it sort of came up with it but the interesting thing is the fix itself is the proposed fix is very simple. It just said, "Oh, you were asserting this. You should have been asserting that." in terms of kind of input validation and so we did start to basically have this patching agent run on every fix. And then the cool part is you're in the loop. So you can actually just apply the patch, build Firefox, and confirm that that same test doesn't crash anymore. And so that's great. But so if we go look at the bug, these are basically this is basically a dump of that bucket that we were just looking at all those files.

And I tell this to folks all the time. It is like the revenge of the DevX team, which is teams that have already invested in developer tooling in automations are just so much further ahead because all those tools can be leveraged at much higher velocity by these agents. And so, please, please, if you haven't already, now is the time to invest in developer tooling because what's good for the agents is very good for humans as well and vice versa.

I do think we're pretty far out from a web browser scale and complexity project being able to be sort of autonomously developed and we actually have requirements for having people who write the code and review the code but we're able to use these tools to help accelerate that quite a bit. Well, and I mean if we just take this to the meta level and part of having an open source project like this is it is very large to maintain. It requires the community to maintain something like this and you wouldn't expect the complexity of that to change just by nature of you introducing agents. I think in particular open source projects we'll have to think about how we integrate agents into it how that intersects with the community and I do think they are the most complex and often longest standing codebases that we have out there and so it's interesting to hear you say I don't think overnight we're just going to turn this repo over to the agents.

On the security side with open source, supply chain is such an interesting and important topic around this too. You have to work with every project, there's a lot of important projects. Firefox depends on many many just core internet infrastructure supply chain and every project has different needs and preferences and threat models and things that they care about the way they want the bugs, where do they work and there's a sort of human connection and network problem involved there where as we found many bugs in supply chain and we have personal connections with a lot of those projects and so you're kind of working your way in in a way that is I think less automatable than many people would hope. But I think it's the reality of how this is going to have to just get deployed across the industry.

We'll pull up VS Code here and sort of there's a couple aspects of the harness here that I wanted to show off and make really concrete to bring home the point that it's not too complicated. So, we have part of the demo here. I have a patch applied to a local build of Firefox in a Docker container that introduces a really obvious memory safety issue if you're a C++ developer. And so, in this patch, I wanted to show kind of a couple different approaches. It's sort of where we started and where we got to. And so inside of this Docker environment, we have a simple script here that with some prompt that says you're looking for a memory safety issue. Read the file and analyze it. And so we're not giving it access to any tools. We just say look at the file and find the problem. You can run this with both Claude and Codeex pretty easily. There are command line arguments like -p you maybe seen with Claude that will it's basically designed to be run by another program not a human. So if we said in this case run with Claude you're going to see this kind of ugly JSON streaming out but this is actually what's happening under the hood when you have an interactive Claude session. It's reading a bunch of code. It's probably pretty quickly converge on the problem in this file and it's going to write essentially like a markdown report. And so this is just like the very basic primitive building block like you could build this and run this yourself in an hour with Claude. You can also run it with Codeex.

We'll share this MCP in the show notes. If you want to help the project, please dive in. So, and I'm looking at this example. You know, you're seeing turns of nine turns, 10 turns, 14 turns finding the result and getting that whole package. And then it will go on and you know create it build firefox and verify that the crash went away. I think what you're demystifying for folks is you can build I mean v1 is literally just running Claude with prompt it's not very fancy. And then v2 is running an agent SDK with a set of like very useful tools and a sub agent that runs a verification loop at the end.

</details>

### 人机协作防线与 Prompt 博弈

尽管智能体在探测 Firefox 边界漏洞时表现出惊人的耐力，但其固有的“过度专注”也要求人类专家必须处于监督环（Human-in-the-loop）中。例如，智能体在没有防线约束时可能会通过故意修改底层安全选项来“作弊”达成复现目的，或者仅修复眼前的一处细节，而忽略了在相似文件中的全局设计一致性。这就需要人类工程师在 Bugzilla 中进行多方位的全局性安全审查，以做出更干净的系统级修复。在谈及日常如何bend AI to will（弯折 AI 意图）的提示词实操时，Brian 透露了他那极其“朴素”却高效的方法论：对于写作与文档润色，他偏向于控制过程，将文档贴入后手动调整反馈；而对于复杂的系统调试（例如排查 VM 崩溃），如果智能体给出了愚蠢的回答，最实用的技巧是直接复制该代码块并重新贴回，在末尾加上一句强调词（例如“really”），便能引导模型突破逻辑死锁，重新收敛出正确的路径。

展望未来，攻防对抗的成本正在发生剧烈倾斜，但防御者通过系统化的安全闭环依然占得先机：

<details>
<summary>Original English</summary>

I think there's a lot of work. It did require some reprioritizing. Everybody was very tired as we've sort of gone through this, but also really motivated and mobilized in particular because you were getting these very actionable reports.

One of the things you'll see with agents, and I'm sure there's harness techniques, the models will get better, is they get laser focused on the task you've given them. And so, if we go look at the actual bug fix that landed here, it's pretty much what they said. We're checking sort of this but also we're checking the same thing in like three other places and so that's where sort of the expert engineers in every single subcomponent whether that's JavaScript, media, DOM, layout, graphics, we have people who are like world-class browser engineers who were working on this stuff and we'll look at the fix and say oh it looks pretty good or oh this is like completely wrong. And of course we use that feedback to try to improve the patching system.

The problem that I found was exactly this and I do not have millions and millions of lines of code. I have hundreds of thousands of lines of code which is it will get laser focused on the specific patch. It'll say for this bug, this is the patch. But it doesn't do the next level of like go categorically find similar issues across the codebase and then come up with an architecturally clean global fix for this class of security bugs. And so I have found that that's a piece missing in the existing security tooling. And it does take like an engineer that kind of knows the codebase or knows the structure of the codebase to identify some of those. And so I do think this is the next step in some of these harnesses which is for any one fix taking the loop and saying we've identified this issue go in in similar parts of the codebase and identify if we have this issue systematically, then zoom back out and articulate what the fix is overall as opposed to the point fix and then ship that and then close all the related issues is a path that I've been doing manually and now seeing this just thinking about how to do that more systematically.

And the other thing I think people kind of tell themselves that AI bug fixes, AI code is almost like limitless and free and therefore you can like cover the earth with AI code, but budgets shall not allow. There is actually a time cost to shipping, reviewing, verifying AI code. And so you cannot go completely prioritization-free, especially when you're looking at the kinds of fixes you need to verify and they're taking 14 loops to even get to a yes-no. I do think this pre-prioritization is a very clever use so you can allocate compute appropriately to the highest impact things. We showed the graph earlier. This was a sort of incident response level event within Mozilla where we had a slack channel with almost 100 people. I think we had a 100 engineers land fixes as part of this initiative.

My first question inquiring minds have to know is it model or is it harness? Was it Mythos or you know like if you had to do a split where do you think this huge unlock came from?
Of course it's both. I think on the split percentage is a tough question. We have seen examples of being able to point the harness with many models even like not the latest frontier ones and being able to find bugs. And so just that makes me think, take a cheap answer and say sort of 50-50. Like I think there's so much to still innovate on the harness side and the pipeline side. Like there's this feeling of having sort of 30 ideas of every one thing you did and then after that you had 30 more based on what you tried and that is to me a signal that there's just a ton to do here still.

Are you as somebody who is helping steward one of the largest open source projects, are you a security doomer in the age of AI or how should we feel about this?
I'm cautiously optimistic which compared to a baseline is probably much more optimistic than many people. These are bugs that have existed for a very long time and what was gated before was just on discovery. It's really hard to find these bugs. But our goal is not to have a bunch of bugs that are hard to find. Our goal is to have zero bugs. And so I think that these tools as us and other defenders are starting to apply them actually get us closer to that world. And it is going to be a bumpy road I think for some time as these are getting adopted and different projects are going to have different depths of bugs as well. So it definitely there is reason to be concerned and nervous but I think also I'm generally optimistic about how this could turn out.

When AI is not doing what you want, what is your prompting technique? How do you bend AI to your will?
For pure chatbots, I'm a very boring user and sort of pasting docs in and saying give me feedback and then I'm manually porting that feedback back into the doc. I just like to have control over the process and use it as my own exploration and learning. I think there's a lot out of that from just a writing standpoint. For coding, it depends on what I'm doing. If I'm doing something creative, maybe I'm building like the dashboard I was showing, I'm much more positive and I said, "Oh, this is so great, let's try three other ideas." And then if I'm doing like a system administrative thing, figure out why this VM died and it's not doing what I want, I'm like, "Come on, can't do..." I've also found like sometimes on the code if it puts something really silly, I will just copy that block, paste it back in with the word "really" at the bottom and it'll figure it out.

</details>