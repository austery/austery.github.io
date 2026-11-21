---
author: AI Engineer
date: '2026-06-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_B4Pv9ttFgY
speaker: AI Engineer
tags:
  - agent-interfaces
  - mcp-server
  - context-window
  - error-recovery
  - security-model
title: 构建智能体交互界面：来自 Chrome DevTools 的四大工程范式
summary: 探讨如何为AI智能体设计交互界面（以Chrome DevTools MCP为例）。文章解析了解决大模型上下文溢出的语义摘要法、基于“单次成功耗损比”的效能评估基准，以及在工具颗粒度、容错自愈和多层级信任边界间的核心工程权衡。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
products_models:
  - Chrome DevTools
  - MCP
media_books: []
status: evergreen
---
### 语义降维：跨越上下文认知陷阱

在为开发主体构建基于 **MCP**（Model Context Protocol: 赋予 AI 模型访问外部工具和数据源能力的标准协议）的专属版 **Chrome DevTools** 时，首要的工程挑战在于信息处理架构的错位。回顾过去一年半，生成式代码智能体在生成代码时表现优异，但它们完全处于“盲飞”状态，无法验证其操作的结果。为了解决这个问题，工程师最初假设“机器就该处理海量数据”，直接将包含数百兆字节、高达 50,000 行 JSON 代码的完整性能追踪（Trace）文件直接“喂”给模型，试图让其自行推演。结果毫无意外：如此庞大的数据量瞬间击穿了**大语言模型**（Large Language Model）的上下文窗口限制，导致智能体陷入了无效处理的“垃圾场区”（Dump Zone）。

这揭示了机器协同的底层逻辑转向：即使是机器，也不该被强迫“读完一整本书”。系统必须从被动的数据直出转向主动的语义后处理机制。通过将庞杂的 JSON 性能剖析转化为高度提炼的 Markdown 文本与**语义摘要**（Semantic Summaries），仅反馈最大内容绘制（LCP）或交互到下一次绘制（INP）等核心指标，系统等于将智能体的注意力精准锚定在具有直接执行价值的单句信息上，成功化解了上下文超载的危机。

<details><summary>Original English Source</summary>
[music]

>> Let's get started in in in interest of time, right?

So, hi. Welcome. Let's talk about building agent interfaces today. So, let me start with a question first. Who in here is already using MCP servers or CLI tools on your uh agent Okay, everybody? That is unsurprising, to be honest.

Um who in here have already built MCP servers and deployed them for effect?

Okay, it's approximately half of the people.

Well, today I'm going to share four engineering lessons from the Chrome uh DevTools team on how we build Chrome DevTools for agents and how we deployed it for effect.

Quick context setting.

Chrome DevTools for humans is used by millions of web developers on a daily basis to debug web pages. It's directly built into Chrome and developers use it to debug web pages. Find errors, audit it, performance profile it, and so on and so on.

Uh right. So, now let's talk a little bit more about Chrome DevTools for agents.

So, this is a purpose-built Chrome DevTools, but for agents. How surprising.

Um yeah, let me briefly show you how it works.

So, you can see on the left side Gemini CLI and the prompt is being entered, and now uh Gemini CLI has the MCP server being configured, and that opens Chrome on the right side, and then does debugging. I think yes, this is about performance tracing. So, it does a performance trace, analyzes the trace that comes back or the performance insight, acts on it, and then makes the web page faster, uh validates that it's actually faster afterwards, and it's done. You should be done now.

It's nearly done.

Sorry, it's the video.

Whatever. What I wanted to tell you is like, yeah, this is going to work in any MCP client and uh agent harness that is MCP capable. Doesn't really matter. That was Gemini CLI, also works in Cloud Code, Codex, Open Claw, doesn't matter.

If you want to have more information, go to this QR code because that QR code is going to uh bring you to a web page, and that's going to tell you everything about how you can install it, configure it for your agent harness.

Question again. Who in here has already tried it out?

Okay, so 10%?

Thank you.

I love you. I also love everybody else, but I love the others more.

So, I was rude. I didn't introduce myself. Uh my name is Michael Hablich. I am the product manager for Chrome developer tools uh at Google. And I'm also a guest lecturer at the university near nearby where I'm living.

I have 20 years of experience in tech, developer, tester, QA engineer, project manager, product manager, program manager, and so on.

If you have questions afterwards, please talk with me in the hallway track or uh connect with me over LinkedIn. Uh the QR code will bring you to my LinkedIn page. Both is fine.

Uh please do that. I would be super interested to talk with you about MCP servers, browser automation tools, and stuff like that.

Okay, but now enough advertisement. Let's move on.

We ship Chrome DevTools because we saw that coding agents were flying blind. So, like 1 and 1/2 years ago, they were very good with generating code, but they were not able to validate what they actually were doing, right?

And that just sucked.

But we assumed they are going to be fine if we throw a lot of data at them. Because I mean, they are machines, right? The thing is, we were wrong. So, this is a uh This is the head of a trace file. A trace file it has all the data about the performance profile.

And this is a file like multiple megabytes of data, and this is like 50,000 lines of JSON, and we did throw that against common agent harness at that point, like 1 and 1/2 year ago, something like that.

And without surprise, this is too much data for an agent for a model to actually reason about, and it blew through the context window.

And if you have seen Matt's talk about the dump zone, you are moving the agent into the dump zone at that point. So, I thought, okay, we built it wrong. That's not going to work. We need to do something else. So, in that case, for example, what we did, our performance tracing endpoints, it can also return that for post-processing uh with other tools, but what it's really doing is it's returning markdown now and semantic summaries. Like, this is a example of a such a semantic summary, which just gives you information about typical performance metrics like largest contentful paint, IMP, and so on and so on. I'm not going to bore you about all the uh performance metrics. And we are going to talk about them anyway because they are a very good example of how this is uh working.

Well, essentially, we didn't force the agent to read the entire book, the trace, but instead we just pointed it at the right sentence, and this is the semantic summary.

That works quite well.
</details>

### 效能边界：单次成功耗损与工具博弈

在明确智能体作为全新独立用户群体后，系统设计的底层哲学也随之进化。人类与智能体共享着相同的任务意图（如寻找并修复响应式布局错误），但各自受限于截然不同的认知瓶颈。人类高度依赖视觉复杂度与布局色彩来获取信号，而对智能体来说，核心诉求在于能否完成用户旅程（有效性）以及在此过程中的 Token 成本、工具调用次数与持续时间（效率）。由此，工程团队引入了衡量界面“燃料效率”的黄金指标：**单次成功任务的 Token 耗损**（Tokens per successful outcome）。值得注意的是，该指标不能全局通用，因为在简单的网络抓取和深度网页调试之间，任务复杂度带来的消耗不可同日而语，必须将该指标严格锚定在具体的用户旅程中进行对比优化。

在落实控制燃料消耗的过程中，必须引入深度的工具干预。首先，系统通过将非核心（如 Chrome 扩展调试）工具隐藏至命令行参数后方，并推出仅保留“选择、导航、执行脚本”三个核心接口的“精简模式”（Slim Mode），极大限度地控制了上下文膨胀。不仅如此，利用**命令行界面**（CLI）进行的命令连缀操作（Piping）也是破局关键——例如，在宿主机上通过 `grep` 提取无障碍树的控制节点 ID，再将结果直接传输给点击操作指令。这种在本地计算机完成的数据提取后处理，避免了让底层模型盲目遍历海量中间状态 Token，从而实现了算力极简。

<details><summary>Original English Source</summary>
In the end, uh or in the beginning, agents are a different user class. So, that's where when it's kind of like it clicked for me, like, ah yeah, they are kind of like a separate user segment. So, how do we reason about that?

The thing is, agents and humans, they share the intent, they share the goal, right? In our case, for example, both want to identify errors in a page and want to fix those errors.

But they think differently.

They have different cognitive bottlenecks, more or less.

For humans, it's a lot about visual complexity.

So, humans are very typically very visual uh creatures, and we need layout, we need color in order to find a signal. And this might not be the best example for uh efficiency.

Uh sounds very happy, and maybe it is. I don't know.

Um

What is it about? So, effectiveness is about does the agent complete the entire user journey?

Is the functional intent actually fulfilled? Yes or no.

And then there's efficiency, which unsurprisingly is about token cost, tool calls, duration.

In the end, what tokens per successful outcome tell you is the fuel efficiency of your interface, right?

And there's a caveat because there's always a caveat.

Fuel efficiency is relatively worthless if you can't reach your destination. So, that's why it's called tokens per successful outcome and not token per outcome. So, make sure that you actually also measure effectiveness, right?

And there's one more caveat.

And this is you can't measure that globally. I mean, you can do that, but you maybe you want to do that because it's a nice metric, but it's going to be tremendously different between different user journeys and task classes. So, don't compare them globally, compare them within your user journey that they're measuring that.

Uh and what I mean with that is like, for example, in Chrome DevTools, we have the user journey of web scraping, right?

So, an agent going to website and extracting information.

That's relatively cheap.

But there's also user journeys that are more intricate like debugging a website, finding out why the responsive layout is not working.

That thing is going to use more tokens, but that is fine because it's a much more much more intricate uh and more interactive session that's happening.

Okay, how does this look like in real life? Uh, this is what it looks like in practice and for a project from the internal project that we're working on, and you see a lot of neon bars, which is great.

I like neon bars.

But, I am not going to worry about details. The important thing is the neon bars on the left side, the longer the bar, the more effective the tool.

Right?

The shorter the bar, the less effective the tool for the particular use case.

So, each of those bars on the left side are about use cases.

Uh, which means the smaller bars are probably the ones that we should be focusing on our work next, how to improve that, how to improve the tokens per successful outcome there.

Yeah.

Uh, as you might have already guessed, measuring tokens per successful outcome is not straightforward.

The thing is, but even an imperfect measurement is better than simply doing gut-driven, um, decisions.

And with that, at least you can do data-informed decisions.

Right.

Ian, sorry. Uh, I had my audio on.

In DevTools for Agents, we're addressing, uh, token burn from three different three different angles.

First, there's tool categorization. So, very straightforward, we hide hide niche niche tools behind command line parameters. Like, for example, uh, we have tools for Chrome extension debugging.

And not everybody is developing Chrome extensions. So, why add it to the default context menu? There's no point in doing that.

Then there's a slim mode.

And this one is fun. So, what slim mode is doing is like, uh, pushing tool categorization to its limits. It's only exposing I think three different tools.

Select page, navigate page, and evaluate script.

And this is great for your context window, but there's a trade-off. I'm going to talk about a lot about trade-offs today. Um, there's a trade-off because the less tools you expose, the less tools are also at the disposal for a for your agent harness, which means your agent might do extra turns to achieve the same goal. It might not actually have the right tools at the disposal to actually do something, like for example, getting network requests.

You can't do that with evaluate script.

And stuff like that.

Yeah, and there's also a CLI interface.

Uh, sorry, there's a command line interface that we're offering. Uh, you have seen the previous talk maybe about a code model and all that stuff. We also support that. So, it is a MCP server, yes, but there's also, uh, a command line interface for the same thing, giving you nearly the same functionality.

What it enables you, you can have your agent chain commands together to do post-processing. Like in this example, I don't think you can see it. Um, the accessibility tree is extracted with a with a grep uh, command, and then the result, the ID of the control is being piped into a click command. And that is, of course, saving a lot of tokens doing that because the model doesn't need to process all the tokens. The token post-processing is happening on your computer.

Right.
</details>

### 自愈系统与架构权衡：错误恢复与发现困境

在追求效率优化的同时，系统工程师面临着无法回避的陷阱：一旦智能体卡顿报错，大量重试和推理逻辑就会急剧燃烧 Token。因此，**错误恢复**（Error Recovery）不再是锦上添花，而是智能体基础设施的核心防御机制。它表现为一个完整的光谱：首先，必须抛弃粗暴的报错，向智能体反馈附带可执行建议的有效错误信息（如在提示“未找到指定历史记录入口”后，追加说明“无法返回所选页面”），从而赋予智能体无需人类干预即刻完成系统自愈（Self-healing）的能力。其次，为了抵御底层模型训练数据中的陈旧经验偏见，系统设计了**主动绕道机制**（Proactive Detours），一旦识别出智能体试图进行过时的行为路径（例如试图触发 Lighthouse 审计来进行性能剖析），就会主动将其引流并重定向至更高效的新工具中。此外，系统针对容易出错的环境配置，专门部署了**诊断手册**（Diagnostic Playbooks）这一项底层技能，它在环境初始化配置出现问题时主动介入，引导人工与智能体协同排除故障，显著提升了代理系统的操作韧性。

然而，对工具架构的拆解重组带来了棘手的“能力发现难题”。最初的设计为了统筹全局，构建了一个庞大的“调试网页”单体工具，却导致执行意图模糊。当团队将这个单体拆解为 25 个特定领域的小型工具时，挑战转移了：系统陷入了严重的**发现困境**（Discoverability）。因为对于智能体而言，接口规范（Schema）本身就是其唯一的交互 UI，而调查发现 97% 的 MCP 工具描述存在质量瑕疵。为避免小型语言模型被混杂冗余的描述误导，开发者必须像打磨人类产品一样打磨工具接口。通过提供极度清晰的激活边界（例如在提示词中直接将性能追踪工具的用途与 LCP、INP、CLS 等具体的优化需求相绑定），帮助智能体精确锁定目标。这是平衡功能覆盖率与控制上下文膨胀必须付出的工程代价。

<details><summary>Original English Source</summary>
Um, efficiency is useless if your agent gets stuck. So, that brings us to error recovery.

And yeah, because every time your your agent encounters an error, it's going to cost you tokens because it needs to retry, it needs to understand what is happening and stuff like that. And that just sucks.

Oh, yeah.

Error recovery is a spectrum, and let's talk a little bit about that, what we are doing here. So, first, of course, you should add uh, useful error messages. That sounds obvious.

Uh, for a lot of tools, it isn't.

And it was also not obvious for all the tools that we actually offered, so we also did, uh, a few iterations on them to actually make the make the error messages good. Like here, for example, uh, an unable to navigate back in the selected page for a particular tool history entry to navigate, uh, was not found. We actually added the last sentence, and that enabled the agent to self-heal, which is super useful because then the agent doesn't need a human to actually fix the problems, but the agent can, uh, self-fix the problems.

Then there's proactive detours. So, beneath each of the agents, there's a model, and the model is being trained on certain data.

And sometimes, the, there are things where you want to counteract the training data.

And that's what you can do with proactive detours. Like in this example, um, we detour the agent for performance profiling to our start performance trace tool and not to the Lighthouse audit.

And there's diagnostic playbooks. Uh, so, we also offer, uh, skills, of course. And we have a skill that's called, uh, troubleshooting, and we see a lot of people have problems setting up the Chrome DevTools MCP server correctly, and that troubleshooting skill is then going to kick in and help the human and the agent to fix the setup issues.

Again, enabling self-healing of the agent.

And all of this increases the resilience of your product, uh, of the agent harness that you're building. And this is nice and helps you with telling the mistakes.

And now, let's talk about discoverability, which is about actually preventing them.

So, our initial design had one monolithic tool called debug webpage.

So, we only had one tool, debug webpage.

And you could the another agent could send a prompt there and tell it, "Hey, debug this webpage. There are some responsive layout that's not working."

And it was neat from an engineering perspective, but it didn't really work.

Uh, so, we decomposed it into 25 different tools. And did we solve the problem? Did we solve it? Of course, it wasn't.

Because we traded that problem off to another.

And that was agents now had 25 tools at their disposal. How are you going to find out which one to use when?

Well, let's talk about that.

According to this paper here, uh, 97% of MCP tool descriptions have quality smells.

And this matters because the schema is the UI for the agent. So, let's make the UI better.

And fixing this is a trade-off, as I said.

It's always a trade-off.

Because, of course, you can make the descriptions better, and that's going to increase your context window size. So, you probably don't want to have that. Or maybe you want.

And also, smaller models in particular are not that good with more descriptions because they get biased in using tools they shouldn't be using in the first place.

There's a trade-off space.

Uh, read the paper. Super interesting.

Uh, yeah. But, there are a few things you actually should be doing that are relatively uncontroversial, and that is, um, define purpose.

Clearly explain how what the tool core function is. Is this working? Ah, yeah.

Here it is.

Come on.

Yes. Ah, it's a Okay. Clearly explain the tool's core function, and there's usage guidelines, like provide clear activation criteria.

And how does it look like in, uh, Chrome DevTools for Agents, for example? And, uh, again, performance start trace tool.

What we have in there as a as a description is used to find performance, uh, front-end performance issues and core web vitals, LCP, INP, CLS. Why is this relevant? LCP, INP, CLS are web performance metrics, and an agent is able to make the connection, "Oh, I'm going to use that tool if I need to, uh, improve page load, for example."

We are far from finished optimizing that because models and agent harnesses also keep on, uh, changing all the time, so it's kind of like an endless quest for minimum viable description.

Yeah, but it is what it is.

You can supercharge all of that with skills. As I said, we also have skills, and that is great, uh, in particular if you have more intricate workflows.

But again, there's a trade-off.

They are not free lunch.

If you pile in too many skills, uh, you're going to to shift the problem and run into the same problem again.

Uh, agents are going to call your skills even if they shouldn't be calling them.

Uh, your context window size is going to increase and all that stuff. The trade-off is shifting, it's not disappearing.
</details>

### 信任边界防御：拒绝便利陷阱的三级安全生态

在保障效率韧性后，必须处理底层极度敏感的系统漏洞——智能体授权防御与信任机制。以 Chrome DevTools for Agents 提供的“自动连接”（Autoconnect）功能为例，这个功能允许 **Claude Code** 这类代码智能体直接共享浏览器调试界面从而完成复杂的系统纠错。在传统人类视角下，要求用户在每次操作时反复点击“允许授权”是一种反体验设计，无数用户甚至要求添加“永远记住我的选择”功能以消除使用摩擦。

但在将机器引入核心操作链路时，这种看似累赘的交互摩擦本质上是一种通过“人为拦截”设计的安全防波堤。根据 Simon Willison 提出的**致命三要素**（Lethal Tri-factor，代表由于智能体代理目标、外部攻击面及执行能力的交织而产生的巨大安全隐患），我们绝不能用系统级的信任边界来换取表面的便捷。

由此，一套针对浏览智能体的“风险隔离三级机制”（Three Tiers）应运而生：
*   **Tier 1（本地沙盒层）**：针对本地开发环境，系统强制引入人类在环（Human-in-the-loop）验证机制，在有限的时间窗口内授权给默认的 Chrome 容器执行；
*   **Tier 2（CI 防御层）**：当代理进入到自动化的连续集成（Continuous Integration）管道中，由于摆脱了实时的人力监督，此时系统必须执行物理级的数据阻隔（如运用 Docker 容器与独立的 Chrome 预置档案文件进行完全的隔离防护）；
*   **Tier 3（全网游荡模式 / YOLO Mode）**：拥有全网自由行动权限的代理智能体处于最高级别的安全深水区，随时面临着页面上的隐藏指令进行**提示词注入攻击**（Prompt Injection）。对于这一风险敞口，必须辅以严苛的白名单与专有的防注入协议墙。

安全机制的终局结论是冰冷但坚实的：当我们迎来智能体这一全新的系统级用户并不断赋能其能力与自治性时，在最底层的信任验证领域，绝不可为图省事走捷径。唯有将底层安全架构内嵌，智能体才能真正安全地辅助人类工作流。

<details><summary>Original English Source</summary>
Okay, now we have optimized for cost, recovery, and discovery. Let's now talk a little bit about trust because you don't want to have a backdoor into the system.

Chrome DevTools for Agents has a feature called autoconnect, and it's kind of like it lets you, the human, using your coding agent, like Claude Code, share the screen with the agent, like, "Hey, I'm stuck here. Uh, please help me debugging the debug that and fix the problem that I'm seeing here."

Amazing feature. I really like it. Um, and users, of course, requested the feature, "Hey, why do I need to click allow all the time? I don't want to do that. Please remember my choice." And in a traditional user experience design, that would have been a clear win, right? Because it's just fixing the friction that you want to remove.

In a world where you are delegating away work to agents and automating away agents, you need to think about trust boundaries.

And so, that's why we actually designed it, uh, with so that friction is actually by design because we didn't want to have that. And why? Let's talk about that.

There's a blog post from, uh, Simon Willison about the lethal tri factor.

QR code. You should read it, it's great.

Uh, I'm not going to talk more about that.

And utilizing that, there is a free uh, at least three tiers that I'm thinking about in browser a browsing agents more or less. You have tier one and that is the local development environment. In the local development environment, you have the human in loop and the human wants to grant access to the default Chrome profile to the data that you already have access to uh to the agent in a time bound manner. And then you have uh tier two and tier two is uh agents running in continuous integration environment. So, it's controlled environments, but they're separated away. At that point, you should be using data separation things like containers, of course, but also other things like separate Chrome profiles and stuff like that.

Um if you want to connect to them, we also have a mechanism for that and that is called uh remote debugging port.

And third, there's agents with full internet access and that is YOLO mode essentially because every webpage out there is able to do some prompt check chain text to your agent. So, make sure that it do the same thing as in tier two, but also in tier three, uh make sure that they have the domain allow list and don't prompt injection mitigations, all that stuff together.

Going back to the leaf trajectory factor, that's what we mostly reason about uh tier one and that's where all those three things are coming together. So, that's why we actually say no, the human actually need to consent every time.

Key point being is a local agent, tier one, and a browsing agent fleet, tier three, where you're research agents maybe, might share a tool like Chrome DevTools for agents, but they shouldn't share nothing else else about your security model that you're having, right?

Okay.

Let's Let me wrap it up. User experience is evolving to incorporate agent experience.

An agent is just another type of user, segment of user, also with non-functional requirements.

Efficiency, discoverability, security, stability, and so on and so on and so on.

I shared four takeaways from Chrome DevTools for agents.

Um when we are implement while we are implementing that, that is measure fuel fuel efficiency of the interface with tokens per successful outcome.

Turn errors into recovery playbooks.

Audit descriptions for intent and never compromise trust for convenience.

Agents are our next users.

Let's help them help us.

And with that, I wish you a nice remaining conference.

>> [applause]

[music]

[music]
</details>