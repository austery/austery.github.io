---
author: The MAD Podcast with Matt Turck
date: '2026-05-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kMXJrzAa5fM
speaker: The MAD Podcast with Matt Turck
tags:
  - ai-agent
  - sandbox
  - infrastructure
  - virtualization
  - developer-tools
title: 为什么每个 AI 智能体都需要一台专属电脑：对话 Daytona CEO Ivan Burazin
summary: 本期访谈深入探讨了 AI Agent 基础设施的核心概念——沙箱（Sandbox）。Daytona CEO Ivan Burazin 提出智能体是“数字知识工作者”，因此必须拥有专属的计算环境。对话涵盖了从沙箱的技术实现（如 Firecracker、QEMU）、Agent 技术栈的构成、到创业公司的分发策略及未来可能出现的 CPU 短缺等前沿议题。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ivan Burazin
  - Matt Turk
companies_orgs:
  - Daytona
  - OpenAI
  - Anthropic
  - AWS
products_models:
  - Firecracker
  - Kubernetes
  - Docker
  - Sysbox
  - OpenClaude
media_books:
  - Why We Sleep
status: evergreen
---
### 智能体即数字知识工作者

**Matt Turk**: 欢迎来到 Matt 播客。今天的嘉宾是 **Ivan Burazin**，他是 **Daytona** 的 CEO。Daytona 是目前 Agent 基础设施领域最受关注的初创公司之一。如果你在关于 AI Agent 的讨论中不断听到“沙箱（Sandbox）”这个词，却又纳闷它到底意味着什么，这一集就是为你准备的。我们将从基础原理出发，探讨为什么 Agent 根本上需要一台电脑，一直聊到深层技术：为什么 Daytona 必须抛弃 Kubernetes 并编写自己的调度器，以及为什么全球 CPU 短缺可能比人们预想的来得更快。Ivan 还拆解了他眼中的完整 Agent 技术栈：模型、沙箱、工具、MCP、记忆、编排。此外，他还会分享过去 16 年构建开发者工具过程中学到的分发经验。

**Matt Turk**: 嘿 Ivan，欢迎。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome to the Matt podcast. My guest today is Ivan Borisin, CEO of Daytona, one of the most talked about startups in agent infrastructure. If you've been hearing the word sandbox in every AI agent conversation and quietly wondering what it actually means and why it suddenly matters, this episode is for you. We go from first principles, why does an agent need a computer at all? All the way to the deep technical end, why Daytona had to throw out Kubernetes and write their own scheduleuler, and why a global CPU shortage might be coming faster than people think. Ivan also unpacked the full agent stack as he sees it, models, sandboxes, tools, MCP, memory, orchestration, and where each piece is heading. Along the way, Ivan shares some really interesting lessons on go to market and distribution for technical founders that he has learned through 16 years building developer tools startups. Please enjoy this great conversation with Ivan from Daytona. Hey Ian, welcome.

</details>

**Ivan Burazin**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Great to be here.

</details>

**Matt Turk**: 你曾说过，每个 Agent 都需要自己的电脑。解释这个想法最简单的方式是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: So you have said that every agent needs its own computer. What's the simplest way of explaining that idea?

</details>

**Ivan Burazin**: 当我思考 Agent 时，我把它们视为**数字知识工作者**。作为一名知识工作者，要做任何复杂的事情，你都需要一台电脑。你我可以进行对话并完成一些事，但通常我们需要某种工具——在我们的世界里通常是电脑——来获得更高的生产力。所以，我用同样的视角来看待 Agent。对我来说，Agent 字面上就是数字版的知识工作者。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Well, when I think about agents, I think of them as digital knowledge workers. And to do anything as a knowledge worker, you do need a computer or I should say anything sophisticated. So, you and I can be on a conversation and we can get something done, but we usually need some sort of tools in our world is usually a computer to get higher productivity um and to be able to do things. And so, I think of that in the same lens. So, for me, agents are literally just digital knowledge workers.

</details>

### 什么是“沙箱”？

**Matt Turk**: 太棒了。所以专属电脑就是“沙箱”的概念。作为对话的开端，什么是沙箱？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And so it's on computer. That's the the whole concept of of sandbox. So as an introduction to this whole conversation, what is a sandbox?

</details>

**Ivan Burazin**: 沙箱这个词最初源于**隔离**，即确保有一个安全的地方供 Agent 运行和操作。但另一方面，它本质上就是一台电脑。它是一台功能齐全的电脑，Agent 可以在上面安装工具、访问网络、运行脚本、运行代码，完成任务所需的一切。最简短的回答是：沙箱本质上是为 AI Agent 提供的**可组合电脑**。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Absolutely. So sandbox is although they the term sandox first comes from isolation. So making sure that there's a secure place for in this case an agent to run and do things. But on the other side it is essentially a computer. It's a full-on computer that an agent has ability to install tools, access the web, um, run scripts, run code, whatever it needs to get its job done. So, the shortest answer is a sandbox is essentially we call them composable computers for AI agents.

</details>

**Matt Turk**: 在某种程度上，最近流行的 **OpenClaude** 和 **Mac Mini** 的组合是不是沙箱的一个很好的类比？Mac Mini 就充当了沙箱。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. And is in some ways like this whole open claw and Mac mini like a good analogy for what a sandbox is like the Mac Mini sort of being the sandbox.

</details>

**Ivan Burazin**: 没错。我认为 OpenClaude 和 Mac Mini 的热度确实帮很多人理解了我们实际在做的事情。就像是：“噢，我现在明白了。”Agent 需要一台电脑（在这个例子里是 Mac Mini）才能执行不同的任务。这确实极大地提高了大众的认知。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Exactly. So I think the openclaw Mac mini thing helped a lot of people understand what we actually do. It's like oh I get it now. I get it right. So it needs a computer in this case was a Mac Mini to be able to do different things. So yes that helped a lot with awareness for sure.

</details>

### 安全风险与独立计算环境

**Matt Turk**: 展开来说，OpenClaude 作为一个框架系统，允许 Agent 在你的电脑上做各种事情。基本上，如果它失控了，你希望能够“杀掉”它，所以你可以像关掉沙箱一样拔掉 Mac Mini 的电源。是这个逻辑吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah because uh again to unpack it like the uh open claw as as a as a frameworking system to help an agent do all sorts of things on your computer. basically you want to be able to kill it if it goes rogue and therefore you can unplug the Mac Mini the way you could sort of kill a sandbox. Is that is that kind of

</details>

**Ivan Burazin**: 有点类似。但我个人思考过几件事。我的 OpenClaude 运行在一个**沙箱化的虚拟 Mac Mini** 上，而不是物理机。我不直接在自己电脑上运行 Claude Code 或 OpenClaude 的原因是：虽然它可以帮你整理邮件、搜索文档，但存在**极高的安全风险**。有一次我们在准备董事会报告，我问 Claude：“你能去银行取一下数据吗？”它回答：“好啊，登录并给我访问权限。”我当时就想：登录？给你权限？绝不，我绝不会马上给你权限。

这从根本上打破了它的可行性。所以你得给它一台自己的机器。我个人给了它一个专门的 Daytona 账户，甚至给它配了专属电话号码。之所以要电话号码，是因为进银行系统需要 **2FA（双因子验证）**。除了绑定号码接收验证码，没有别的办法。它必须像一名员工、一名数字员工一样，拥有这些东西才能访问系统。

现在风险变了，因为它有自己的电脑和账户，这些账户是有权限限制的。它只能查看银行数据，不能转账（除了我们给它的一张每天限额 100 美元的信用卡）。这种情况下，唯一的风险是它会不会把数据泄露出去，这是我们稍后可以讨论的。但本质上，最坏的情况发生了，你可以直接杀掉整台机器。

<details>
<summary>Original English</summary>

**Ivan Burazin**: so there's there's a couple things that I personally thought about and so my open claw runs on a not a physical Mac mini essentially but a sandboxed um virtual Mac mini and the reason why I didn't so the way people usually run these things and cloud code or openclaw is usually on their own computer because it helps them you know organize emails you know search whatever documents they have and whatnot there there's a one there's a high security risk there because at one point we were doing our board meeting presentation and I would ask claw can you go fetch the data from our bank and then it was like oh yeah just log in and give me access and I'm like log in give me no I will not give you access right um and so right away fundamentally for me that was like broke the entire thesis of it so you give it its own machine I personally gave it its own like Daytona account it gave it its own phone number and the reason I have give it own phone number is because it has to do 2FA to get into the bank. Like there's no other way except for a 2FA with a phone number for this particular bank. And so it has to have all these things like a employee like a digital employee to be able to go and access these things. And so the risk now that now that it has its own computer, it has its own account. These accounts have the limitations. So it can only it can only look at the data from my bank. It can't spend the money from my bank. And so except for the credit card that we did give it which has you know you know $100 a day or whatever it may be. And so the only risk you essentially have at that point if it's in a sandbox is will it take this data and now leak it somewhere and that's something we can talk about later but essentially the worst thing can happen is that and to your point you can kill the whole machine if you need to kill machine.

</details>

### 有状态 (Stateful) 与 无状态 (Stateless)

**Matt Turk**: 这里涉及到一个基本概念：**有状态（Stateful）** vs **无状态（Stateless）**。你能为我们拆解一下吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. And there is a a fundamental concept of um stateful versus uh stateless. Uh can you can you unpack that for us?

</details>

**Ivan Burazin**: 当我们向人们介绍我们在构建什么时，他们常问：“那些云巨头（Hyperscalers）不是已经有这些了吗？”答案是否定的。因为云巨头构建的一切都是为了**部署应用**，而应用通常是无状态的。比如你的网站，你不希望它在运行过程中自行改变。比如 eBay，如果一名工程师有个新更新，改变了一个按钮的位置或功能，你不希望应用的状态在运行中随意变动。数据库会变，信息会变，但应用本身不能变。云巨头的底层架构就是基于这种思维构建的。

我常给的一个比喻是：这就像造卡车。工厂生产卡车，考虑的是重量、引擎类型、底盘，一切都是为了缓慢但稳健安全地运输货物。而跑车虽然也有四个轮子和引擎，但它是为了速度而生的。底盘结构、引擎调教、重量平衡完全不同。虽然两者都能做很多事，但它们根本上不是同一种东西。作为一家公司，试图同时构建这两个平台是完全不同的挑战。

<details>
<summary>Original English</summary>

**Ivan Burazin**: So that basically comes when we talk to people about what we are building they're like oh doesn't this already exist in any of the hyperscalers right? And so the answer is no. And the answer is no is is because everything that they were built for which was deploying apps they were they were stateless. Like if you have let's let's pick any of your websites or whatever you want web apps you do not want that to change on the fly. You if you if you are the company will pick like eBay because they're in this building so they're they came to mind. And so if you're eBay and you're an engineer there and you're like, "Oh, you have this new, you know, update. A button is here or it does this thing." You want that state that you you don't want that to be changed on the fly, right? The database might change, information might change, but you don't want the app to change, right? And so with those things in mind, that is how people had built the hyperscalers. Like that is the fundamental architecture you came into and built on top of that. And the simplest analogy I give people is let's say you're building a truck, right? You are a factory for a truck. There's like the the weight, the type of the engine, the chassis, um all of that is made to very slowly but surely securely transport some sort of goods, right? On the other hand, you can have a sports car which is still, you know, it has four wheels, it has an engine, whatever, but it's made for different things. It's made to go very fast. So the way the chassis is built, the way the, you know, um engine, the the weight balances is completely different. And so you can do you can do a lot of things with both, but they're not fundamentally the same thing. And as a company trying to build out both of those, they're separate platforms completely, right?

</details>

### 沙箱：Agent 时代的必然产物

**Matt Turk**: 所以沙箱是一个全新的原语（Primitive）？沙箱以前存在过吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Mhm. So sandboxes are a fundamentally new primitive. Is that is that correct? Is is it like a history of sandbox or did sandbox exist before?

</details>

**Ivan Burazin**: 以前有一家叫 **CodeSandbox** 的公司，当时和我们的 CodeAnywhere 竞争，还有像 Replit 这样的云端 IDE 厂商。他们叫 CodeSandbox 我觉得是因为这名字听起来很可爱，像是一个放代码的小盒子。他们确实是先驱之一，使用了微虚拟机（microVM）、快照、分叉等我们今天也在用的技术。那是十多年前的事了。

但当时对人类开发者来说，它的价值并不明显。一直有人在讨论“本地主机（localhost）的终结”，我也谈了 20 年了。开发者通常会说：“除非我死了，否则别想拿走我的 localhost。”但现在 **Agent 来了，你不再希望它们在你的本地运行**，原因有很多。所以沙箱的技术和理论终于到了开花结果的时候。

<details>
<summary>Original English</summary>

**Ivan Burazin**: So I I would argue I would say that that the the person that could have nudged although he said he did and someone else did but anyway there was a company called code sandbox way back in the day when we used to compete with our company code anywhere which also was in the in the realm of like replet it's all these cloud-based IDs and so they called it code sandbox cuz I I I believe it it sounded cute it's like a box where your code you for ID um lived and they were actually one of the firsts so the team there that actually used microVM M did snapshotting, forking, all these things that we do use today. And so that is sort of and this is maybe a decade ago, but the utilization or the usage from or the value that it was giving human developers was not there. There's this whole article about like the end of local hosts and people have been talking about this for I've been talking about this for 20 years. Um and basically developers would say like you'll take my local host like out of my cold dead body. But now that agents are here, local hosts no longer actually one, you don't want that for a number of reasons. And so we're finally getting to that. So that technology and that thesis around sandboxes originally now seems to be coming to fruition.

</details>

**Matt Turk**: 沙箱爆发的主要加速器就是 Agent，对吧？

<details>
<summary>Original English</summary>

**Matt Turk**: Mhm. And the big acceleration around sandboxes is is agents, right? That's

</details>

**Ivan Burazin**: 绝对是。即使你允许 Agent 在你电脑上运行，也会面临很多问题。一个是你的笔记本电脑不能关。推特上现在有个梗，大家都在展示自己开着笔记本的样子，因为一旦合上盖子，Claude 或 OpenClaude 的任务就终止或暂停了。如果你希望任务不间断地运行，笔记本就不是理想选择。

另一个是**并发性**。笔记本的算力非常有限。你可能想同时开启 10 个、20 个甚至 10 万个 Agent 任务，这在本地很难实现。理想情况下，你希望把它们移到远程。你在电脑上开启任务，在手机上继续查看，Agent 在远程的同一台电脑上继续工作。我们现在开始接受 Agent 不再运行在本地 localhost 上，但对那个 Agent 来说，沙箱依然是它的“本地电脑”，就像笔记本之于我们。

<details>
<summary>Original English</summary>

**Ivan Burazin**: thing. Absolutely. When we think about agents, so one, if you even if you do run an agent on your computer, like you want to do that, up to you. Go ahead and do that. There's a bunch of problems. One is let's hear in your laptop. There's this whole thing on Twitter now where people are holding their laptops open. Well, that's because I always hold my laptop open. That's just like my vibe without that. Um but been doing that for a long time. But people do that because they want clawed or open claw to finish. Cuz if you close it, it's is you terminate. Yeah. It's or pause or stop or whatever. Um so like the problem is like the continued the ability to work non-stop is not there as long as your laptop. So that's one thing. The other thing is you can't do concurrency. So you can do multiple to the amount of compute that you have in your laptop which will be quite limited. And so you might want to spin up 10 or 20 or 50 or 100 or 100,000 whatever that number might be. And so that's very hard. So ideally you actually really want to remove it somewhere remotely. So you can start on your laptop, you continue on your phone. It's the same computer and same agent that is doing their thing, right? And so that is a takeoff of we have now decided that it's absolutely okay that is no longer on our local host but again it is still a local host to that agent. So it's still a computer to that agent what a laptop is to us.

</details>

### 所有 Agent 都需要电脑吗？

**Matt Turk**: 所有 Agent 都需要沙箱吗？还是只有特定类别需要？

<details>
<summary>Original English</summary>

**Matt Turk**: Do all agents need a sandbox or is that a specific category?

</details>

**Ivan Burazin**: 我的观点是，**每个 Agent 至少需要一个沙箱，有时更多**。我常把 Agent 类比为人类。人类不用电脑也能进行有产出的工作，比如早期的聊天机器人，你只是跟它说话，它进行推理并提供价值。很多人把它当作情感支持，这不需要电脑，它通过对话就能理解并给你反馈。

但这只是一小部分场景。如果我们观察最大的垂直领域——医疗、金融等，绝大多数生产力提升都是通过电脑完成的。如果你想让 Agent 完成这些工作，它们就必须有电脑。

<details>
<summary>Original English</summary>

**Ivan Burazin**: My my argument is that every agent will need at least one sandbox sometimes more and we can get to that again. there are places where you don't need and I analogize agents with humans for the most part and again we can have we can do productive work without computers and so there is and that was the original sort of like chatbot where basically you would just talk to an agent and it would inference so we just think and give you value so I don't know you a lot of people use it for like emotional support or whatever for the most part it doesn't need a computer it has enough data from you going back and forth and then it can sort of understand and give you feedback but that's a smaller subset. If we think of where all productivity gains are among the biggest verticals, healthcare, financial services, whatever, most of that is done via a computer. And so if you want agents to do all these things, then agents will need these computers to do.

</details>

**Matt Turk**: 所以如果你涉及**工具调用（Tool Calls）**、写代码或任何实际行动，你就需要沙箱。如果只是聊天，可能不需要。

<details>
<summary>Original English</summary>

**Matt Turk**: So if you do uh tool calls, coding, like any of those actions, then you need a sandbox. If you just chat,

</details>

**Ivan Burazin**: 甚至聊天也是。如果你在聊天时让它搜索网页，它必须打开浏览器，或者使用像 Perplexity、Exa 这样的工具，这本身就是工具调用。

有趣的是，我坚信在不久的将来，所有工具都会变成**无头（Headless）**的（无论是在沙箱内还是沙箱外）。这是 Agent 工作最高效的方式。但目前大部分知识工作仍被锁定在旧式应用中，绝大多数是在 Windows 环境下。如果你想让 Agent 今天就能端到端地完成工作，你字面上必须给它一台电脑。

比如那个董事会报告的例子，银行有 API 接口，可以拉取支出数据，但 API 没暴露收入数据。Agent 说：“我拿不到。”我说：“老兄，直接登录网页下载。”然后你可以看到它打开浏览器、点击登录、下载文件。如果能通过无头 API 搞定，它会优先用 API；如果不行，它就会像人一样登录操作。为了让它们现在就产生价值，我们必须赋予它们使用这些工具的能力。

<details>
<summary>Original English</summary>

**Ivan Burazin**: you probably don't need it. Yeah. So like even if if you have a chat we can get it to deal but if you chat and it has to search the web it still has to open a browser or it has to use something like you know parallel or exa or whatever to get to that that would be a tool call. So it depends on the use case but the thing that's quite interesting about the world that we live in is one let's take a step back one I firmly believe that in due time all the tools will be headless now will it be inside a sandbox or outside that's another thing all of them will be um and that's the most efficient way for an agent to work but most of knowledge work is still locked into legacy apps inside of inside of Windows for the vast majority, like the absolute vast majority. Um, so if you want an agent today to do a job end to end, you literally have to give it a computer. And so an example of this is again the board report, which is like, oh, can you pull out this report and our bank has an API and it can pull it out, but it only has spend on the API. It doesn't have um incoming revenue on the API. It's just not exposed or through the MCP tool actually. It's not exposed. And I'm like, then the agent was like, "Oh, I can't get to it." I'm like, "Dude, log in, download it." And okay, I'll go to it. And then you can see it opens up a browser, it goes download whatever. Same thing with, I don't know, with any other data source that we have. If it can pull it from the headless, it'll do it headless. If it cannot, then it sort of logs in and do that. And so, if we want to give them power today and get value, we have to enable them to have these tools.

</details>

### Agent 技术栈的演进

**Matt Turk**: 帮助我们理解沙箱在整个 Agent 技术栈（Agent Stack）中的位置。

<details>
<summary>Original English</summary>

**Matt Turk**: help us understand uh where sandboxes fit in the overall picture of this emerging uh agent stack that uh I think everybody's trying to figure out at the same time.

</details>

**Ivan Burazin**: 很多人把这事想复杂了。其实这些在现实生活中都有对应。
1.  **模型 (Models)**：本质上是**大脑**。你告诉它一些事，它回应、理解。
2.  **工具 (Tools)**：Agent 完成任务的手段。可以是 MCP、工具调用、也可以是沙箱（电脑）。人类也用工具，从锤子到电脑。
3.  **记忆 (Memory)**：Agent 能记住这些事吗？类似人类的记忆。
4.  **编排 (Orchestration)**：这就是**管理**。你管理人类，编排 Agent 也是类似的，只是工具不同（是用 Slack 还是 Linear 还是新的 App）。
5.  **可观测性 (Observability)**：你能看到同事做了什么并验证工作质量吗？

目前模型层已经比较明确，工具层（沙箱、MCP）正在快速发展。**还没被解决好的是“记忆”**。目前的最佳方案只是把东西扔进 Markdown 文件里。

更让我感兴趣的是**模型的“学习能力”**。目前模型其实不会在工作中学习。即使你解决了记忆问题，它也只是拥有了上下文。它不会因为昨天做过某件事今天就变得更擅长。这是否需要持续的 RL（强化学习）或模型架构的根本改变？我不知道。但在某种程度上，和一个不会变聪明的对象共事是很奇怪的。你用了更好的模型，它是“新”的，但它还是可能在做第六次尝试时犯下前五次一样的错误。

<details>
<summary>Original English</summary>

**Ivan Burazin**: I I try to think about everything. To me, it's actually quite interesting where and we'll get this a bit later as well. It's like a lot of this all exists in real life today. And so people are like overthinking this. I'm not saying that there there's not going to be new products and solutions and technology to solve it, but it's like it's not a new fundamental way of work. And so when you think about the agent stack itself, it's like okay, you first have the models and the models are essentially the brain that that is what it is of equivalent to what a human's brain is sort of. So you tell it something, it replies, it understands and whatnot. And then under that is like oh what are the tools it can do to get things done, right? And so that can be anything from like any of the MCP or or tool calls can do. It could be the sandbox, the computer, like whatever we as humans, we also have a bunch of tools that we use. Everything from a hammer to a computer and everything around that, right? Um, so all of those things exist as well. Then there is memory that exists. Can can an agent remember these things? Similar to like do you remember these things that are there? People talk about orchestration of agents. It is like management. Do you manage people? I manage people. Managing agents is similar is not dissimilar to managing humans. Now what tools will you use to manage them? Will you manage them in the same way just send a slack message and or you do linear or whatever it is we will see or it's going to be a net new app we'll figure that out but it is of that and of course it's like observability can you see what your teammate or colleague has done and verify that that job is good right and so there's tech that's sort of how I think about that on a very sort of higher level and then you can break down to different types of solutions people are creating for this

</details>

### 企业级治理与“马甲 (Harness)”

**Matt Turk**: 长远来看，沙箱会集成这些功能吗？还是仅仅作为执行层？

<details>
<summary>Original English</summary>

**Matt Turk**: where do sandboxes fit long term? Do do you think a lot of this gets eventually built into the sandbox or does the sandbox remain the the the execution layer for it all?

</details>

**Ivan Burazin**: 举个高盛（Goldman Sachs）员工的例子。你有员工（模型），有他登录的电脑（沙箱）。**“马甲（Harness）”** 是一套规则，限定了模型能做什么、不能做什么，就像是模型的“双手”。当你登录高盛的电脑，上面会有很多软件监控你的操作、限制你的权限、防止数据泄露。作为沙箱提供商，我们肯定会将这些审计和安全功能集成进去。

但 Harness 依然有其独立价值，它指导模型如何与机器交互：如何调用工具、如何处理记忆。我们不打算做 Harness，但沙箱会为整个系统提供支撑。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Two two things. So if you look there's like the sandbox itself and again restating I'm saying it so many times in in this conversation but if we take like an average worker in Goldman for example right you have the you have the worker the person which let's call it the model in this way you have the computer which it logs in into um and the harness is a set of the way it shapes that model that it can and cannot do things interact things so it's almost like hands sort of to speak um of that bit bit deeper but basically the sandbox does support it and so if you think of a computer again I'll pick on I'll pick on go Goldman for example I've never worked at Goldman but it's my just assumption I worked at bigger company so my assumption is that when you log into that computer there is so much software in that computer that logs what you do restricts what you do make sure that you don't leak data and do these things again no prior knowledge of Goldman just assumptions on these things and so those are the types of things that we as a sandbox provider will most certainly incorporate into that. But that harness still has its function in that which it guides the model like oh I now know how to interact with this machine. Oh, I know how to do a tool call. Oh, I know how to this is how I work with memory. This is how I change with a model. And so there's a there is value in that. And so we don't take on the harness. That is something we pretty sure that we never do. But there's things that we do in the sandbox that does help or support that entire system.

</details>

### 从 IDE 到基础设施：Ivan 的创业课

**Matt Turk**: 谈谈你的故事。这不是你第一次创业了。

<details>
<summary>Original English</summary>

**Matt Turk**: let's talk about um your story and uh Daytona's um story. So you this is not your uh first venture. Talk about the the the prior thing that you did.

</details>

**Ivan Burazin**: 我们在 2009 年就开始做云端 IDE 空间了。那时候没 Docker，没 Kubernetes，没 VS Code。我们必须从零构建整个技术栈。后来出现了 CodeSandbox、Replit。Replit 现在做得非常好。但在做 Daytona 时，我们决定走完全不同的路：**不做应用层，只做基础设施**。我们从 Heroku 的教训中学到了很多，底层编排层似乎非常有价值。

关于分发（Distribution），我以前非常害羞，甚至有舞台恐惧症。第一次创业路演时，我紧张得五分钟内跑了十趟厕所。后来偶然在克罗地亚办了一场会议，原本请的主持人临时放鸽子，我只能硬着头皮上。连主持了两天，我的舞台恐惧症就这么被治好了。

这让我学会了如何理解人的互动。办会议本质上是**娱乐业**：你得有好的演讲者（节目），得吸引观众（流量），还得卖给赞助商（变现）。这种逻辑也应用到了 Daytona 的 GTM（转到市场）策略中。我们办晚宴、见面会、黑客松，全都是会议的简化版。两个月前我们在旧金山 Chase Center 办了一场 4000 人的会议，虽然压力极大，但效果惊人。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Yeah. So we started the cloud IDE space basically in 2009 both me and co-founder and so in 2009 for those of you that were around there was like no Docker, no Kubernetes, no VS code and so we had to build the entire stack which was something that we learned how how to do and something that we applied today. So like it was actually very very very early. The only I say that we started it because the company that started before us was Heroku which became Heroku and killed the ID which we probably should have done sooner um as well. So but we were the only one that sort of like started and finished finished in that in that sense. Later on you had other ones like code sandbox like replet and like others that that had had joined and um stack blitz which now bolt and whatnot. And so Replet also now changed and bolt into their other directions and Replet is doing really well. We decided to go in a completely different direction when we decided to do their next company. So um we had learned a lot of things on how to build this entire stack. But when we decided to kick off Daytona V1, which is different than it is today, we decided not to go app layer but just be infrastructure probably like on the teachings of Heroku which definitely went in into that direction. It's like oh we learned how to do all these things on the orchestration level underneath that seems to be very very valuable. So let's push on that and that is how we kicked that off.

</details>

### 开发者工具的“全方位体验”

**Matt Turk**: 你在品牌建设和开发者营销方面做得很出色。有什么经验可以分享？

<details>
<summary>Original English</summary>

**Matt Turk**: You're also pretty amazing at just distribution in general and and then building a brand and then developers uh which is fascinating, right?

</details>

**Ivan Burazin**: 我引用 Sentry 的 David 的话：人们选择产品有三种方式：
1.  **知晓度 (Awareness)**：他们知道你存在吗？
2.  **偏好度 (Preference)**：价格、品牌、功能、感觉。
3.  **确定性因素 (Deterministic)**：比如你有 FedRAMP 认证，而别人没有，那客户只能选你。

如果产品功能对等，差异化在哪？就在**品牌和体验**。这和产品的纯技术能力无关。我合伙人 Vedran 的任务是确保产品在技术上优于市场；我的任务是即便产品对等，我们也能胜出。

我也把**客户支持视为 GTM 的一部分**。我以前做过系统管理员，修打印机。我告诉团队：最重要的是**第一反应要快**。一旦你快速响应，客户就会冷静下来，因为他们知道问题已经转移到了别人手里。然后你承诺一个解决时间。如果你发现到时间修不好，就提前半天告诉他新的时间。这种“先于客户思考”的体验是神奇的，虽然不复杂，但很多人直觉上做不到。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Thank you. But all of it all the entire GTM that we have we have no other things that we do like Twitter is a go to market um we don't have we have zero sales people and whatnot but it is definitely so the way I think about this and I stole this from or paraphrasing it from David from century which is like there's basically three ways that people pick your product and one is awareness do they even know you exist like if that doesn't happen there's no way they can pick you two is preference which is you know the the pricing the brand, the person, the different features, whatever like it's it's preference. And the third thing is like is there a deterministic thing that you offer that no one else has? So the easiest example for the third one is like do you have fed ramp right? Do you have that certificate? If you have like I can only the customer can only use you and no one else. But the two above are are quite interesting which is like how to make sure that everyone knows who you are and then you work on the um then you work on the preference. And so for me the all I don't it's not all I think about a large part of I think about is if all things were equal. So if our product is equal to everyone else's product what is the differentiator to that? And so like one can more people know about you than others like is the branding there is the the the um the experience there. uh experience is a nuance which p some people don't think about, some people do think about, but it's like do you prefer the feel of this product versus that product? And these are all things that have nothing to do with the actual technical capabilities of the product. And so my co-founder Verran, our CTO, like his job is mostly to make sure the product is better than anything else in the market. And my mandate is to make sure that even if his if our product is equal that we can supersede that and so that's how I think about the go to market in general.

</details>

### 沙箱的技术解构

**Matt Turk**: 让我们回到技术。从技术角度看，沙箱到底是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Now let's switch back to the the more technical uh stuff. So we talked about the concept of sandboxes. Uh just walk us through what a sandbox is technically.

</details>

**Ivan Burazin**: 我把沙箱分为三个层面：**基础设施、原语（Primitive）和工具**。
*   **基础设施**：启动有多快？（我们是 60 毫秒）。并发量有多大？（我们可以在 70 秒内启动 5 万个）。
*   **原语**：这是计算单元本身。虚拟机、容器、微虚拟机。在 Daytona，你可以定义 CPU、内存和磁盘，并在运行中动态调整大小。我们支持 Windows、Mac、Linux、Android，带 GPU 或不带。
*   **工具**：帮助 Agent 更好地工作或设置护栏（Guardrails）。比如无头浏览器、终端、文件操作，还有秘密管理器和防火墙。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Yeah, there's a lot of things there's a lot of things there we can talk about. The way I think about uh sandbox is the ergonomics of consumption of compute. And so because there's a lot of different layers on that I basically put it into three different layers which is the infrastructure the primitive and the tooling those three things together. And what I mean by infrastructure is like is does it spin up very very fast? Can you spin so like we spin up in 60 milliseconds? Can you spin up a lot of them at once so the the rate of creating them. And so we can spin up 50,000 in 70 seconds. Um so little less than a minute and a half. And then once they're up, how many can you keep running? Like we can have we have customers that have billions a day. Um so those are like the infrastructure parts that are non-trivial.

</details>

**Matt Turk**: 为什么启动速度这么重要？

<details>
<summary>Original English</summary>

**Matt Turk**: Why does it matter uh how quickly you can initialize a new sandbox and how many

</details>

**Ivan Burazin**: 对研究人员来说，如果你在做**强化学习（RL）**，GPU 比 CPU 贵得多。沙箱通常是 CPU 环境。你希望 GPU 始终保持最大利用率，不要因为等待 CPU 沙箱启动而闲置。你可能同时需要启动几千个沙箱来完成任务。对应用层来说，像 Lovable 这样的公司，用户量巨大，每个用户可能有多个 Agent，这意味着需要同时运行数百万个沙箱。

<details>
<summary>Original English</summary>

**Ivan Burazin**: again it depends on the user and the use case. So if you're like a long running background agent again everyone prefers it to be fast like no one wants to wait. Like you don't want to wait for a reply. Like everyone wants to be fast to be very clear. So the faster the better, but generally there's an actual reason why you want it very very very fast. And that is especially if you so for I was going to say if for a background agent a background agent might work for like 10 minutes or an hour or whatever. So the incremental millisecond might not matter. But I still believe that from a user perspective even a second of waiting is kind of uncomfortable. You don't want that. And so is 60 or 90 maybe less so. But there you want that one two seconds for sure under that. But the interesting the more interesting part where that is really really important is for the researchers where when you're doing reinforcement learning you basically have a lotment of GPUs and you want the GPU is more expensive than the CPU. So the vast majority of sandboxes are CPU boxes to be clear. So they're the computers that we all work on. There might be a graphics card in there but basically it's the compute the RAM the CPU um and the hard disk that's in there. And they are cheaper or less expensive and easier to to get at least for now. We'll see for how long that lasts. Then GPUs, which means you want your GPUs always to be at maximum utilization and the CPUs can then idle if need to be idled, but you want them, you don't want the GPUs to idle.

</details>

### Firecracker, QEMU 与隔离技术

**Matt Turk**: 什么是 Firecracker？

<details>
<summary>Original English</summary>

**Matt Turk**: remind people what firecracker is

</details>

**Ivan Burazin**: Firecracker 是由 AWS 团队开发的隔离技术，用于 Lambda。它是一种高度简化的虚拟机，启动极快且无状态，非常适合应对突发流量。但它不支持 GPU。如果你需要 GPU 或 Android 设备，就得用 **QEMU** 或云端管理程序，那更接近完整的虚拟机。还有容器（Docker），它速度快、密度高，但安全性不如虚拟机。我们在 Daytona 使用 **Sysbox** 对容器进行加固，使其具有类似虚拟机的隔离性。

<details>
<summary>Original English</summary>

**Ivan Burazin**: firecracker it's an isolation priv so it is essentially a type of VM or virtual machine that's very stripped down it was made by the uh AWS team it's used inside of Lambda and so the idea which are like functions um and so the idea was to have something very very fast um that can spin up and stateless that that that was the entire time and they were very very ephemeral and so they were used for you know when your website has a large um if it's Black Friday a bunch of people hitting your website you can spin up a lot of these very very fast like handle the load and enable all these humans to to look at the website and buy whatever they were buying, right? And so that technology is there and it's a very stripped down version of a full-on VM. So it has less features there, but the things that it does, it does very very very very well. So it can spin them up fast. It does that because it can sort of lazy load things in into memory. You can do point in time snapshots. You can do all these nice things. The things that it can't do is it can't run a let's call it sandbox now. It can't run a sandbox with a GPU. It just doesn't work. So that you can't have a firecracker. So if you want a GPU, you have to do something which is a cloud hypervisor or a Kimu spelled Q E M U which are two different types. Q Kimu is almost a full VM. So it has all these different things in inside of there. Um so you can't do that.

</details>

### 快照与调度器的重要性

**Matt Turk**: 为什么快照和自研调度器如此重要？

<details>
<summary>Original English</summary>

**Matt Turk**: Why are snapshots and ors important? You mentioned uh uh performance and speed um and in connection with that you said that you had to rebuild your own scheduleuler.

</details>

**Ivan Burazin**: 快照允许你**暂停沙箱**。如果你有 1000 万用户，你不想让沙箱在等待人类回应时白白消耗 CPU 费用。你可以快照它，并在需要时瞬间恢复，用户感觉它从未关机。此外，Agent 还可以利用快照进行**多路径尝试**，或者在出错时回滚到特定时间点。

至于调度器，现有的 Kubernetes 或 Nomad 并不是为这种“极速、有状态、长连接”的机器设计的。所以我们必须重写。我们的调度器允许我们在裸机机架上切分出成千上万个小机器。

大多数沙箱提供商将计算和存储（网络硬盘）分离，这样管理很方便，如果服务器挂了，数据还在云端硬盘。但 **Daytona 坚持使用机器的本地 CPU、内存和硬盘**。为什么？因为网络硬盘的 IOPS（每秒输入输出量）可能是几十万，而**本地硬盘可以达到几千万**。虽然这增加了我们的运维难度（必须在后台做用户无感的备份），但性能差异是巨大的。

<details>
<summary>Original English</summary>

**Ivan Burazin**: There's a lot of reasons. Let's get into the the commercial one, which is probably the the one that people most think about, which is pausing a sandbox. So if you are an app layer company and you have 10 million users and your 10 million users spin up let's just say 10 million sandboxes just to make the math easier. These things cost right cuz they're running they're using CPU RAM and hard disk the entire time. The most expensive thing is the CPU second their RAM disc is almost free. It's very inexpensive and the user sends the agent to do something. The agent does something and now it's waiting for reply. It could be waiting for the human or it could be waiting from a service depending on what it's trying to do. You ideally don't want that sandbox to run idle because you are now pay regardless if you're a customer of Daytona or running your own but like there is a cost to running these things. And so what you want to do is pause that and wait for a reply either from a service or for a human and then resume and the feeling and experience is that it never turned off. So you feel like it never turned off but it actually did um turn off. And so that one is from a from a compute management perspective if not from a cost perspective is probably the first reason.

</details>

### CPU 短缺与未来展望

**Matt Turk**: 我们一直处于 GPU 短缺中，但你提到我们可能面临 **CPU 短缺**？

<details>
<summary>Original English</summary>

**Matt Turk**: we have been in a very well doumented GPU shortage. Uh but it uh seems that we might be heading towards a CPU shortage.

</details>

**Ivan Burazin**: 没错。Dylan Patel 曾写过一份报告，预测到 10 月份 CPU 可能就会不够用。大家都在关注 GPU，但 Agent 运行需要大量 CPU，RL 训练也需要大量 CPU 沙箱。随着 GPU 变得越来越强，它们可以并行带动的 CPU 需求也呈爆炸式增长。

关于未来，我认为目前的 Transformer 模型可能不是终态。也许会出现更轻量、甚至不需要 GPU 的新架构。有人在研究“湿件（Wetware）”，用模拟人类大脑的组织来学习玩《毁灭战士（Doom）》。虽然这听起来很疯狂，也不是明天就会发生，但我并不认为我们已经走到了技术的尽头。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Yeah, it might be happening. So one of your former guests and was at our conference Dylan Patel like semi analysis they wrote the report and I believe it's somewhere like October we have no more CPUs and people hadn't thought about it like it's it's all GPUs all GPU intensive then memory but basically now now that agents need all these computers like it is very much needed now that RL is the way that we've gotten most of the progress in models over the last 18 20 months hunts you need all the CPU machines to do this. Now that the GPUs are more powerful, they can do in parallel more of these CPUs, CPU boxes. And then you see this, there was a tweet that I put a while back and it's like you should definitely invest, not financial advice, you should invest in Intel and look at their stock price, right? And so like there's definitely need for that

</details>

**Matt Turk**: 非常精彩，Ivan。感谢你今天的分享。

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. Well, Ivan, that was fabulous. Thank you so much for spending time with us today.

</details>

**Ivan Burazin**: 谢谢你的邀请。

<details>
<summary>Original English</summary>

**Ivan Burazin**: Thank you for having me. We're great.

</details>