---
author: AI Engineer
date: '2026-10-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8vDzncmzxyg
speaker: AI Engineer
tags:
  - ai-agent
  - code-verification
  - static-analysis
  - developer-tool
title: 将确定性代码验证引入智能体编程循环：Sonar Vortex 的引导与实时检查
summary: Sonar 介绍了将代码验证嵌入编程智能体工作流的插件 Sonar Vortex。它在编码前为智能体提供项目架构与规范上下文，并在生成时通过确定性静态分析实时拦截安全与质量漏洞，促使智能体自主迭代修复，减少上下文消耗与 PR 返工成本。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Killian Carlsen-Phelan
companies_orgs:
  - Sonar
products_models:
  - SonarQube
  - Sonar Vortex
media_books: []
status: evergreen
---
### AI 智能体缺乏项目上下文带来的编码困境

>> 我是来自 Sonar 的 Killian。如果你对 Sonar 还不熟悉，我们是一个独立的代码验证平台。我今天想要探讨的是，如何将验证机制引入到智能体编程循环（agentic coding loop）之中。

<details>
<summary>Original English</summary>
>> I am Killian from Sonar. And if you're unfamiliar with Sonar, we are an independent code verification platform. Um and what I'm going to be talking about today is how to move verification into the agentic coding loop.
</details>

>> 大家都知道，过去几年所有人都在这么做。它加快了开发节奏，但每次你在 IDE 中开启一个全新的智能体协作会话时，就像是完全从零开始。它就像是项目新入职的员工一样，不了解你现有的项目惯例，不知道你的编码规范，也不知道你预先为它定义的任何架构规则。这可能会引发问题。

<details>
<summary>Original English</summary>
Um I mean as we know everybody has been doing this the past couple years. It's accelerated the pace and every time you start a new agentic session in your IDE, it is like starting from scratch. It is like a new hired employee into your project. It does not know your existing project conventions. It does not know uh your coding guidelines. It does not know any architecture rules that you have predefined for it. And that can be a problem.
</details>

>> 因为接下来，当它被指派开发一个新功能时，它就必须到处寻找上下文，对吧？如果你说：“嘿，构建一个新的 API 端点。”它就必须去弄清楚你现有的代码中 API 端点是如何运作的。那个过程有点像掷骰子靠运气。它可能很快就能获取到上下文，也可能在你的整个代码仓库里到处搜寻。

<details>
<summary>Original English</summary>
Because what it has to do then is when it's assigned a feature, it has to go look around for context, right? If you say, "Hey, build out a new API endpoint." It has to go and determine how existing API endpoints work in your code. And that process can, you know, it's it's a bit of a roll of the dice. Um it can acquire that context quickly or it can search around all over your repository.
</details>

>> 这既耗费时间，又消耗 token。而且这是一个完全可以解决的问题。如果你的代码库中本来就存在缺陷，对吧？很抱歉不得不直说，每个代码库都有缺陷。不幸的是，无论你使用哪种智能体，这些缺陷极有可能被它复制，这些模式也极有可能被它重复。当智能体引入新缺陷时——不是“如果”，而是“必然”会引入——如果没能及时捕获，想要维持代码质量几乎是不可能的。

<details>
<summary>Original English</summary>
And that takes time and that takes tokens. And this is a very fixable problem. And if you have issues in your codebase, right? As I'm sorry to break it to you, every codebase does. That is uh unfortunately, it's highly likely that these issues will be replicated and these patterns repeated by whichever agent you're using. And not if, but when that agent introduces new issues, if it's not caught the ability to maintain the quality of your code is almost impossible to do.
</details>

### Sonar Vortex：确定性验证与实时闭环

>> 因此，我们的解决方案是 Sonar Vortex。稍后我会在这里展示给大家看。它是一个能够连接到你使用的任何编码智能体的插件。这样一来，智能体在开始编码之前就已经了解你的项目，并且它能够以确定性的方式自我验证，确保不会向你的代码库引入任何新的问题。

<details>
<summary>Original English</summary>
So um our solution to that is Sonar Vortex. I'm going to show you that here in a little bit. Um what it is it is a plug-in that connects to whatever coding agent you use. And uh this is so the agent knows about your project before it even begins to code. And it is able to verify itself deterministically to make sure that it's introducing no new issues into your code base.
</details>

>> 不久前，我录制了一个编码智能体编写一个小型功能的过程。它在不到 2 分钟内就完成了，但遗憾的是，尽管我指示它为自己构建一套测试套件，它还是引入了一个安全问题。Sonar Vortex 成功捕获了该问题，并强制该智能体继续自我迭代，直到问题被修复。

<details>
<summary>Original English</summary>
So, um I had I recorded a coding agent writing a small feature a little bit ago and it it was able to do so in under 2 minutes, but unfortunately, even though I had instructed it to build out a test suite for itself, it introduced a security issue that Sonar Vortex was was able to catch and forced the agent to continue iterating upon itself until it was fixed.
</details>

>> 那个问题最终具体表现为——我们稍后就能看到——它的任务是将一个日志文件解压到一个临时文件中，但遗憾的是，它为该临时文件设置的权限不够明确。这种类型的问题很难通过编写测试来覆盖，很难被捕获，而且通常只有资深审查人员在特意去排查时才可能发现（如果真能发现的话）。退一步说，就算他们发现了，现在又得把它退回给开发人员或智能体去重新修改、重新提交、重新审查并重新分析，这既消耗了时间和金钱，也让所有相关人员感到非常沮丧。

<details>
<summary>Original English</summary>
So, um the issue ended up being, and we'll see this here momentarily, is that it wrote it it was to unzip a log file into a temp file, but unfortunately, the permissions that it set for that temp file um were not explicit. And that type of issue is hard to write tests for, it's hard to catch, and it's usually the type of thing that a senior reviewer would only catch if they're explicitly looking for it, if at all. And then let's say that they do catch it, now it has to be sent back for a developer or an agent to rework again and re-push and re-review and re-analyze and that burns time and money and it causes a lot of frustration for everyone involved.
</details>

### 开发者对 AI 生成代码的信任鸿沟

>> 这一过程中的挫败感并不仅仅是我个人的观点，它来自于我们收集的数据。Sonar 对 1,100 多名开发人员进行了调查，发现其中 96% 的人并不完全信任 AI 生成的代码。但你觉得这些人当中，有多少人在推送代码之前真正对其进行了充分验证呢？不到一半，只有 48%。这在我个人看来简直匪夷所思。一想到我们只是在未经验证的情况下盲目地将代码推向生产环境，就让我感到恐惧。

<details>
<summary>Original English</summary>
So, um that the frustration in that process is not just my opinion, that is uh from data that we've pulled. Sonar surveyed over 1,100 developers and found that 96% percent of them do not fully trust AI-generated code. But how many how many of those do you think actually fully verified the code before pushing it? It It was less than half. It was 48% of those. So, that that boggles my mind, personally. That terrifies me that we are just blindly setting off code into production without verifying it.
</details>

>> 不过正如我所说，智能体编写代码非常迅速。返工会拖慢你的步伐，如果你在 PR（Pull Request）阶段才发现问题，你实际上已经落后于原本应有的进度了。这里有一段简短的动画，大致展示我刚才所讲的内容：如我所提，Sonar Vortex 的目标之一就是让你的编码智能体变得更加高效，同时为它们提供防护栏。这个小球代表你的编码智能体，正如我所说，它编写大量代码的速度极其惊人，比人类能跟上的速度还要快，也快于我们人工审查的速度。

<details>
<summary>Original English</summary>
Um but um like I said, the agents write quickly. Rework slows you down, and if you catch it at the PR, um you're already behind where you need to be. But, uh a quick animation to kind of demonstrate what I'm talking about here is as I mentioned, Sonar Vortex. One of the goals that we are doing is we are making your coding agents more efficient. In addition to providing guardrails for them. But, this little ball here is your coding agent, which as I said, it writes a lot of code really really fast, faster than humans can keep up with, faster than we are able to review manually.
</details>

>> 遗憾的是，正如我所说，当它刚启动时，这个网格就代表你的代码库，每个方格代表一个文件，它必须四处搜寻。它每移动一步，就会检查一个新文件。底部的那条进度条代表 token，也就是你在无目的搜寻上耗费的金钱和时间。当它犯了错误时，你直到 PR 环节才会发现。代码审查失败，工作又退回到智能体手中进行下一轮修改，它就这么持续迭代下去；你不得不频繁打扰资深工程师，让他感到恼火，大家都过得不顺心。

<details>
<summary>Original English</summary>
Unfortunately, as I said, when it starts out, this this grid is your code base. Every square is a file. It has to go searching around. Every time it moves, it's checking a new file. And that bar at the bottom is tokens, which is your money and time spent on just looking around. And when it gets something wrong, you get to find out at the pull request. The review fails, and the work goes back to the agent for another round, and it continues to iterate itself, and you got to keep pinging your senior engineer, and then he's mad at you, and then nobody has a good time.
</details>

### Vortex 的引导与实时检查机制

>> 现在，借助 Sonar Vortex，在编写任何内容之前，它都会获取你项目的编码规范以及代码相互连接的结构图。因此，它会拉取架构规范等内容，会拉取你的应用程序所认可的依赖库列表，以及针对特定项目的编码标准。这些规则全都可以由你自己来设定。

<details>
<summary>Original English</summary>
Before it writes anything with Sonar Vortex now, it is going to get the coding guidelines for your project and a map of how the code connects. So, it will pull in things like your architecture guidelines. It will pull in things like what the approved libraries for your applications are, what your coding standards are for uh a given project. And these are all things you get to set for yourself.
</details>

>> 所以，正如你在这里看到的，它直接定位到相关文件。它不会浪费多余的 token，也不会过度占用上下文空间。当它工作时，SonarQube 会检查它的代码。智能体利用自身工具所做的每一次编辑，都会触发一次快速检查。而在智能体结束当前轮次之前，它会被指示运行一次更深度的检查，针对跨文件数据流做更深入的安全排查。你可以看到，那个问题被反馈给了智能体，智能体修复了自己的代码，随后 Vortex 再次对其进行检查。

<details>
<summary>Original English</summary>
So, now you can see here, it goes straight to to files. It does not burn excess tokens, it does not burn excess context. And as it works SonarQube checks its code. So, your agent, the edits that it makes with its own tools, every time it uses them it triggers a quick check. And before it ends its turn, it's told to run a deeper check um for even deeper security issues for cross-file data flow. And you see here that issue goes back to the agent and the agent fixes its own code and then Vortex checks it again.
</details>

>> 这套机制完全适用于大家目前正在使用的所有主流智能体，无论是 Cloud Code、Codex 还是 Antigravity，随你选用。如果你自行设计了定制智能体，或者使用的是开源版本以及小众产品，我们提供了高度可配置的 MCP 客户端，供你根据自身需求使用。因此，归根结底我希望大家了解的是：Vortex 是一个可以轻松接入到智能体中的组件。它构建在我们提供的 CLI 和 MCP 工具之上，并将 SonarQube 的能力带入智能体中，使得智能体在编写代码前就能理解你的项目。我先暂停一下，或者往回退一点，免得错过画面。

<details>
<summary>Original English</summary>
And this all works with all of the agents that people are currently using right now, be that Cloud Code, Codex, Antigravity, whatever you want to use. And if you have any custom agents designed or using any open-source ones or any of the non-major players, uh we have MCP clients that are very configurable for you to use at your own desire for that. So, essentially what I want you to take away from this is that Vortex is something that you can just plug in easily to your agent. It it isn't built on top of the CLI and MCP tools that we provide it and it brings SonarQube into the agent so that the agent knows your project before it writes. I'm going to pause it or I'm going to move back before I miss it.
</details>

>> 我们发现，它平均能减少 36% 的 token 消耗，尤其是在重构既有代码库这类任务中。使用它的用户，生产环境故障减少了 44%，而且我们维持了极低的误报率，以免干扰你的编程会话。

<details>
<summary>Original English</summary>
And what we found is that it spends 36% fewer tokens on average, especially on tasks like refactoring existing codebases. People who use it have a 44% reduction in production outages and we have a very low false positive rate as well so that we don't clutter up your coding sessions.
</details>

>> 这非常了不起，它加快编码周期乃至软件开发周期的速度非同寻常，我们在可验证的编程领域正处于一个全新的前沿。

<details>
<summary>Original English</summary>
So, um this is huge. This is huge. This the speed that this um accelerates the coding cycle to the software development cycle to is um it's we're on the new frontier being able to verify uh programming.
</details>

### 将 SonarQube 情报引入智能体工作流

>> 总而言之，我们要做的就是引导智能体并验证其变更。我们把 SonarQube 既有的情报能力融入了整个流程。我相信在座各位至少有人熟悉 SonarQube。我们已经存在了近二十年，传统上我们是很多人在流水线中运行的一个步骤，以确定性的方式分析各类安全隐患、可维护性问题和数据流漏洞，我们会构建图谱，并深入分析代码。如今，凭借我们服务器上已有的这些知识积累，我们能够为智能体提供上下文，让它从一开始就具备这些信息。

<details>
<summary>Original English</summary>
So, to sum it all up we want to guide the agent and verify the change. And we bring SonarQube's existing intelligence into the mix. So, I'm sure at least some of you are familiar with SonarQube. We've been around for almost two decades, and we are traditionally a a pipeline step that a lot of people run that deterministically analyzes for any security issues, maintainability issues, any data flow issues, and we build out graphs, and we dive deep into the code. Now, with this knowledge already maintained within our servers, we're able to provide that context to an agent, so now it exists from the get-go.
</details>

>> 你的智能体在动笔前就懂你的项目，并能边写边检查自己的代码。你的 CI 中本来就已经配置了 SonarQube 扫描，而 Vortex 复用了那次扫描所沉淀的信息，因此它只需对你的文件做一次快速检查，就能掌握其余代码的情况。接下来，我将向大家展示它在实际任务中的表现。这是我昨晚刚刚录制的。

<details>
<summary>Original English</summary>
Um your agent knows your project before it writes, and it checks its own code as it goes. Your CI already has a SonarQube scan, and then Vortex reuses what that scan has learned, so it's just a quick check on your file, and it knows about the rest of your code. So, here I'm going to show it to you in a real task. This I actually recorded last night.
</details>

### 实机演示：实时上下文注入与安全漏洞修复

>> 从一开始大家就能看到——我会根据需要在这里适时暂停和重播。我希望大家注意的第一点是：无需做任何额外操作，我们就能看到 SonarQube 已经在会话中启动了。对吧？我们的 CLI 被检测到了，hook 系统被检测到了，密钥泄露检测也已经开启。我今天不会过多深入探讨这个，但是密钥泄露是最容易预防的隐患之一，也是给企业造成损失最严重的问题之一。我们的插件可以防止密钥泄露到 GitHub 以及智能体的上下文记忆中。

<details>
<summary>Original English</summary>
And what you can see from the get-go, and I'll be pausing and restarting it here and there. Uh the first thing that I want you to see is that without having to do anything, we can see SonarQube has started up in the session. Right? Our CLI is detected, and the hook system is detected as well, and secrets detection is on. I'm not going to dive too much into that today, but um secrets leakage is one of the easiest things to prevent, and one of the most costly for your organization. Our plugin prevents uh secrets leaks into GitHub and into agent uh context memories.
</details>

>> 我希望大家留意的是，我不需要在提示词里粘贴任何 Sonar 的指令，所有内容都是自动加载的。我之前提到的请求就在这里，基本上就是把一个日志文件解压到一个临时文件中。提示词要求：“继续复用同一个文件，并编写测试来证明它被复用了。”

<details>
<summary>Original English</summary>
And what I want you to notice is I didn't have to paste any Sonar instructions into the prompt. It's just all automatically loaded. And so, the request that I alluded to earlier, right here, is uh it's just basically unzipping a log file into a temp file. It says, "Keep reusing that same file, and then write a test that proves it's reused."
</details>

>> 在写下一行代码之前，它先向 Sonar 询问了两件事。它会问：这个类位于哪里？针对这个项目的 Java 编码规范是什么？就显示在这里。这是 Sonar 上下文导航，我们获取到了这个模式，也就是我要求它处理的那个 GC 日志文件。这样它就获得了父级和子级的架构关系，以及围绕该文件的既有模式和规范。同时它还调用了 Sonar context guidelines 查询语言为 Java 的规范。因此，我们在构建 Java 项目时会有一套强制智能体遵守的基础规范，但如果你有任何希望团队遵循的自定义需求，也可以从一开始就注入进去。各位，我再怎么强调也不为过：除了模型本身的选择之外，智能体从一开始所获得的上下文和方向引导，是决定智能体表现的最强大杠杆。你在前期做得越多，在自己开发过程中需要进行的返工、修正和人工介入就越少。

<details>
<summary>Original English</summary>
And before it writes a single line, it's going to ask Sonar two things. It's going to say, uh where does this class live? And what are the Java coding guidelines for this project? And it's right here. It's Sonar context navigation, um and we get this pattern, this single GC log file that I told it to work on. So, it gets parent and child architecture, um as well as existing patterns, um and and uh guidelines around that. As well, it says Sonar context guidelines get language is Java. So, we have um basic guidelines that we enforce agents use when building out Java projects, but if you have any customer requirements that you want your team to follow, uh that gets injected from the get-go. And guys, I cannot emphasize enough that outside of model choice, the context and steering from the get-go that agents receive is the single greatest lever that you can manipulate for agentic performance. Um and the more you do on the front end, the less rework and steering and correcting and intervention that you have to do when you're developing for yourself.
</details>

>> 所以，它不像动画里那样逐个文件去搜寻，而是直接获取了那张映射图。这就是 Vortex 所执行的“引导”阶段。因此，它能够检查现有的测试，了解其运作方式，并迅速切入到具体实现中。刚才这只花了几秒钟，显然不同的功能耗时会有所不同，但在没有 Vortex 的情况下针对该功能运行耗时会更长，因为必须到处使用 grep 搜索才能搞清楚状况。

<details>
<summary>Original English</summary>
So, like uh instead of searching through the files one by one like in the animation, it just gets that map. This is the guide phase uh that that Vortex does. And so, it's able to inspect the existing test, see how uh that operates, and very quickly move on into implementation. Now, that just took a few seconds, and obviously this changes from feature to feature, but running against this feature without Vortex takes longer as this has to grep around and figure out what's going on.
</details>

>> 现在它正在执行具体实现，我会很快指出它究竟在哪里创建了那个临时文件。它添加了自己的测试套件。测试套件就在这里。在录像中我向上滚动了一下，这一小段代码就是临时文件。希望大家能看清，对台下观众来说字体可能有点小。总之它就在那里创建了临时文件。

<details>
<summary>Original English</summary>
So, it's running the implementation, and I will very quickly point out uh where it actually makes that temp file. Um it adds in its own test suite. So, here's the test suite. Uh in the recording, I scroll up. This a little bit right here is a temp file. And I hope you guys can see. It's probably really small for you in the audience. Um, but it creates that temp file right there.
</details>

### 确定性验证层与 AI 自查的差异

>> 接下来，它会去确认自己的测试结果，然后在它修改过的两个文件上运行 Sonar 检查。就在这里，显示“确认测试结果”，然后显示“正在运行 Vortex 分析”。每当有文件被编辑或新增时，Vortex 分析都会运行。你不需要强行去触发它，甚至根本不需要操心，它会自动介入，你可以放心地确保代码经过了验证。如果你搭建了自动化工作流，或者运行着复杂的工厂模式设计等等，这就是你必须加入的一层信任保障，以确保没有缺陷被引入。

<details>
<summary>Original English</summary>
And, um, it's going to go ahead and check its own test result, and then it will run the sonar check on both of the files that it changed. Right here it says confirming the test result, and it says running Vortex analysis. Every time a file is edited or added, Vortex analysis runs. You do not have to enforce it. You do not even really have to think about it. It just automatically kicks in, and you can trust your code gets verified. If you have automated workflows set up, if you run a sophisticated, you know, factory design, or you're building these out, this is a layer of trust you need to add in order to make sure that no issues are being introduced.
</details>

>> 还有一点需要说明：这并不是用另一个 AI 去检查 AI，对吧？更不是让它自己检查自己。根据我们的发现，那遗憾地是被证明最不可靠的防错方式之一。不仅是因为智能体在自身的生成与审查之间思维存在正交偏差，而且其他智能体在审查既有代码时也很容易出现遗漏和幻觉。当你拥有一层确定性的机制——我的意思是，每次对代码运行分析都会得到相同的结果——只有这样，你才能提供可靠、可治理、合规且可预测的指导与验证。

<details>
<summary>Original English</summary>
One point as well, this is not another AI checking AI, right? Um, and it's certainly not it checking itself. That is, unfortunately, we found one of the least reliable ways to ensure that issues are not being introduced. Not only do agents think orthogonally on the creation and review of themselves, um, other Asian agents are likely to miss and hallucinate when reviewing existing code. When you have a deterministic layer, and by that I mean, every time you run the analysis on the code, you get the same result back, that is how you are able to provide reliable, governable, uh, guidance and verification that is compliant and predictable.
</details>

>> 不要误解我的意思，我非常喜欢 AI 审查。我们也有一个 AI 审查工具叫作 Guitar，我今天不会讲它，本周早些时候我为此做过一场工作坊。如果大家想了解更多信息，欢迎稍后到我们的展台交流。但是，Sonar Vortex 是一层叠加在你的 AI 编码之上的确定性检查层，并且夹在另一层 AI 审查之间。

<details>
<summary>Original English</summary>
Don't get me wrong. I love AI review. We also have a, um, AI reviewing tool that I'm not going to talk about today. It's called Guitar. I ran a workshop earlier this week on that. And please come by our booth later if you'd love to hear more information. But, Sonar Vortex is a deterministic layer that stacks on top of your AI coding, and sandwiched between another AI review as well.
</details>

### 缺陷定位与强制修复循环

>> 现在我们正在运行 Vortex 分析，它将会捕获一些问题。返回的结果中有 6 个发现，Claude 指出其中 2 个发现在它刚刚编写的代码行中，还有 4 个属于预先存在的既有代码。我们设计 Vortex 并不是为了制造大量噪音，并不是为了让它说“噢，你发现了一个问题，但你必须把另外三个也修掉”。针对新生成的代码，它会强制要求修正；而对于既有代码的问题，它只是向你提示，让你心中有数，以便你将来有需要时再去修复。

<details>
<summary>Original English</summary>
So, we're running the Vortex analysis and it is going to catch something. It'll catch six findings that come back and Claude will say two of those findings are on lines that it just wrote and four on pre-existing code. Now, we did not engineer Vortex to be super noisy. We did not engineer Vortex to say, "Oh, you found one issue, but you got to fix three more." On new code that is created, it enforces correction and that just surfaces it to you so that you have it for your awareness and if in the future you'd like to fix it, you are able to.
</details>

>> 它捕获的其中一个问题属于安全漏洞，正如我开场时提到的：Claude 把日志放在了默认的临时文件夹中，却没有声明谁有权限读取它。在很多服务器上，该文件夹是共享的。于是 Claude 着手去修复该问题。

<details>
<summary>Original English</summary>
One of the findings um that that it has is a security problem, the one that I mentioned uh at the start of this, which is that Claude put the log in the default temp folder without saying who can read it. And on a lot of servers, that folder is shared. So, uh Claude goes ahead and it uh fixes uh the issue here.
</details>

>> 但遗憾的是——我们马上就能看到——Sonar Vortex 再次运行后判断：“嘿，你其实并没有修好这个问题。”提示显示：“该问题依然存在，因为临时文件仍处于共享目录中。”第一次修复依赖了 Java 的默认设置，在 Mac 和 Linux 上默认确实仅限所有者访问，但我们设定的规则标准很高，要求必须显式设置权限。在安全性上我们从不妥协，在代码质量上我们也从不妥协。

<details>
<summary>Original English</summary>
But, unfortunately, and we'll see this in a second, Sonar Vortex runs again and determines, "Hey, you actually did not fix the issue." Says, "The finding persists because the temp file is still in a shared directory." The first fix leaned on a Java default and on Mac uh and Linux, the default is already owner only, but the rule that we set in, which is a high bar that we set, is that this is the permissions must be set explicitly. We do not compromise when it comes to uh security. We do not compromise when it comes to quality.
</details>

>> 最终，Claude 成功实现了这些修复；并且同样地，它每次运行都会触发 Vortex 分析。你绝不希望把任何缺陷带入 PR，因为捕获问题的速度越快，不仅问题影响的波及面会减小，修复所需的时间、金钱和精力也会显著下降。

<details>
<summary>Original English</summary>
So, finally, Claude is able to implement these fixes and again, every time it runs, Vortex analysis is initiated. You do not want to let any issues into your PR because the quicker you can catch these, not only does the surface area of the issues get reduced, but the time and money and energy for remediation decreases.
</details>

### 总结与展望

>> 好了，终端会话的演示就到这里。我不会让大家一直盯着一段简短的预录终端演示。但本质上，我希望大家从中记住的是：它首先向 Sonar 进行了咨询；当 Sonar 标记出问题后，它进一步自我修正并完成了修复；在最后交付之前，还会执行一次深入的数据流分析。

<details>
<summary>Original English</summary>
Now, uh that's it for the terminal session. I'm not going to make everyone stare into a tiny uh pre-recorded terminal session, but essentially, what I want everyone to take away from this is that it asked Sonar first. When Sonar flagged it's fixed, it went further and continued to remediate itself. And it will eventually hand it back at the end, and a deep analysis uh for data flow will be performed.
</details>

>> 你能从中获得什么？你能获得的是更少的来回审查——我看到我还剩一分钟，我马上做个收尾。你获得的是更少来回反复的审查，问题能够当场得到修复，你获得了更安全的代码，更少用于修复缺陷的时间和金钱消耗，而且由于你能够信任自动化智能体工作流，你的开发人员得以释放出更多时间。

<details>
<summary>Original English</summary>
What do you get? What do you get out of this? You get less back and forth review, and I see I have a minute left. I'll uh finish up here in a bit. You get less back and forth forth review, you get it fixed in the moment, you get more secure code, you get less time and money spent on remediation, and um you have more time freed up for your developers because of your ability to trust uh automating agentic workflows.
</details>

>> 我们在楼下设有展台，非常希望能与大家面对面交流。演讲结束后我会在会场后方留步回答大家的提问。很希望能和大家聊聊。无论你是刚听说 Sonar，还是 Sonar 的老客户，我都非常期待听取你的意见和见解。以上就是我今天分享的全部内容，非常感谢大家。

<details>
<summary>Original English</summary>
We have a booth downstairs. I would love to talk to you guys. I'll be hanging out behind uh the room in the back uh to answer any questions. I would love to talk with you. If you're brand new to Sonar, if you're an existing Sonar customer, um you know, I'd still love to hear your input and insights. And um that's all I have for you today. Thank you very much.
</details>