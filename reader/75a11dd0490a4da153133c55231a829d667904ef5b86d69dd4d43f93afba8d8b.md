---
author: How I AI
date: '2026-03-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=diy3kmUl8mY
speaker: How I AI
tags:
  - micro-agents
  - terminal-automation
  - workflow-optimization
  - cli-tools
  - developer-productivity
title: 微软 AI 副总裁谈 Warp 自动化：如何利用微型代理消灭低效琐事
summary: 微软核心 AI 产品副总裁 Marco Casalaina 展示了如何利用 AI 终端 Warp 构建“即时代理”（ad-hoc agents），将 Azure 权限管理、扫描仪控制及 FFmpeg 视频重编码等复杂的 CLI 操作转化为简单的自然语言交互。他强调了微型代理在提升效率、减少摩擦及实现工作流自动化中的巨大潜力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Marco Casalaina
companies_orgs:
  - Microsoft
  - OpenAI
  - Atlassian
products_models:
  - Warp
  - Azure
  - Copilot
  - ChatGPT
  - FFmpeg
  - Jira
  - Rovo
media_books: []
status: evergreen
---
### 微型代理的“魔法”：让终端工作更顺滑

**Marco Casalaina**: **Warp** 真的很神奇，但你可以为这种魔法锦上添花，让它运行得更加顺滑。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Warp is pretty magical, but you can add to the magic and make it work more smoothly.

</details>

**Clarvo**: 你是指建立一些**微型代理 (micro agents)** 来帮你处理各种小任务，不管是像我们在 Warp 中看到的那种一次性的，还是那种周期性或触发式的任务。这确实能让生活变得更轻松。

<details>
<summary>Original English</summary>

**Clarvo**: You're talking about setting up little micro agents that do little tasks for you, either one off ones like we saw in warp or recurring and triggered ones. And then this is making your life just easier.

</details>

**Marco Casalaina**: 没错。我一开始用它来处理某些特定的事情，比如**管理 Azure**、分配 Azure 订阅之类的，然后我就彻底迷上了。我当时想：天哪，这真是一个非常强大的工具。除非你开始和这些代理一起工作，否则你不会真正发现用**命令行 (command lines)** 能做这么多事。但我认为一旦你开始尝试，它就会打开你的思路，让你意识到什么是真正可能的。

<details>
<summary>Original English</summary>

**Marco Casalaina**: As soon as I started using it for certain things like managing Azure, giving Azure subscriptions and stuff like that, then I was hooked. I was like, man, alive this is a really capable tool. until you start working with these agents, you don't really discover all the things that you can do with command lines. But I think once you start to test those, then it kind of opens up your mind to what is really possible.

</details>

**Clarvo**: 欢迎回到《How I AI》。我是 **Clarvo**，一名产品负责人，也是 AI 痴迷者，我的使命是帮助你利用这些新工具构建更好的产品。今天，我邀请到了 **Marco Casalaina**，他是微软核心 AI 产品副总裁及 AI 未来学家。Marco 将快速演示五个 AI 使用案例，展示微型代理如何减少处理繁琐小任务的摩擦，无论这些任务是否涉及技术细节。

在此之前，先认识一下 **Rovo**，你的 AI 队友。它由 **Atlassian** 提供支持，能连接知识、人员和工作流，帮助团队更明智地工作并快速推进。Rovo 已经内置于 Jira、Confluence 等付费订阅中，助你找寻答案、做出决策并自动化工作。

Marco，感谢参加节目。我很兴奋，因为我们要看的是 **Warp**，这个工具还没在播客上出现过。而且我们将看到你如何用它来处理一些辅助性的支持案例，这可能不是它的主要宣传用途，但你发现非常有用。在深入探讨之前，你为什么会如此深度地迷上 Warp？

<details>
<summary>Original English</summary>

**Clarvo**: Welcome back to how I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Marco Castellania, VP of core AI products and AI futurist at Microsoft. Marco is going to speedrun through five AI use cases where microaggents can reduce the friction of getting little tasks done, whether they're technical or not so technical. Let's get to it. Meet Rovo, your AI teammate. Connecting knowledge, people, and workflows so teams can work smarter and move faster... Marco, thanks for joining How I AI. I am excited because we're going to see a tool, Warp, that we haven't yet seen on the podcast, and we're going to see you use it for maybe not its primary pitched use case, which is kind of a coding, but for some sort of more ancillary support use cases that you found to be really useful. So before we get into them, like why have you hooked so deeply into Warp in particular?

</details>

### 案例一：利用 AI 简化复杂的云端管理

**Marco Casalaina**: 说来讽刺，我开始使用 Warp 是因为微软内部的一个团队向我推荐了它。那是我们的 **PowerShell** 团队，他们说：“你应该试试 Warp，它自动化 PowerShell 的效果非常好。” 于是我试了一下，当我开始用它来管理 **Azure**、分配订阅之类的事情时，我就停不下来了。这真是一个极其强悍的工具。

<details>
<summary>Original English</summary>

**Marco Casalaina**: I started using Warp uh ironically because our own one of our own teams here at Microsoft tuned me into it. They it was our PowerShell team and they were like you should try this Warp thing. It automates PowerShell really well. And so I tried it and as soon as I started using it for certain things like uh managing Azure and you know giving Azure subscriptions and stuff like that then I was hooked. I was like man alive this is a really capable tool.

</details>

**Clarvo**: 如果你在寻找《How I AI》中最“性感”的一集，那就是这一集，因为我们要向你展示如何**用 AI 管理 Azure 资源**。虽然我在开玩笑，但这非常有意义。如果你是一名软件工程师或工程主管，你会把大量时间花在 **DevOps**、管理员配置、IAM（身份访问管理）等事情上。这些杂事占据了你所有的时间，让你没法去享受 AI 编码的乐趣。所以，请给我们展示一下那个具体案例，为什么你认为 Warp 是一个很好的选择，以及在没有这个工具之前痛苦在哪里？

<details>
<summary>Original English</summary>

**Clarvo**: And if you're looking for the sexiest episode of how I AI, it is this because we are going to show you how to manage Azure resources with AI. Which actually I'm making a joke cuz I think it's so funny. But these are the kinds of things that if you are a software engineer or an engineering leader or just building something you are spending so much time on DevOps admin configuration IAM all that kind of stuff takes all your time and you don't actually get to the fun part of coding with AI. So, you know, show us maybe that specific use case and why you think Warp was such a good fit for that and what the pain was before you had a tool like this.

</details>

**Marco Casalaina**: 好的。前几天我和同事 Goind 一起工作，我需要为他分配若干 Azure 资源的访问权限。你知道，你需要给他非常细粒度的角色。在这里，我需要给他“Azure AI User”和“Azure AI Project Manager”权限。说实话，在 Azure 中完成这个操作并不容易，尤其是如果你通过 Web 界面来做。在 Web 门户中，你必须为每个单独的角色找到角色名，然后分配给 Goind，接着是下一个角色。这效率极低。如果要把我需要给他的所有角色都分完，可能要花上一个小时。

相反，我会这样做。这是我的提示词（Prompt）：我先在这里输入 Goind 的电子邮件地址，然后说：“好的，现在在这个我正在查看的订阅上，给他 Azure AI User 和 Azure AI Project Manager 角色。” 它就能正确执行，它会调用 **Azure CLI**（命令行界面）。

这就是 Warp 的超级能力。除了作为一个许多人熟知的**编码代理 (coding agent)**，我其实更多地把它当成这样用：只要有命令行界面（CLI）可以执行操作，Warp 就极其出色。它会重复调用 CLI，直到任务彻底完成。哪怕中间出了点错，它也能立刻纠正并完成。然后我会说：“实际上，我还需要在整个订阅上给他 Contributor 角色。” 它也能毫无压力地完成。我把这用于各种事情，包括 Azure 管理。微软的朋友们请闭上耳朵——我也曾用它配合 **G-Cloud CLI** 来管理 GCP，效果同样出色。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Yeah, let's do this. So, I was working with my colleague Goind the other day and I needed to assign him access to a number of Azure resources and you know, you give them granular roles... Now to do this, it's actually not that easy to be honest to do this in in Azure, you know, and especially if I do it with a web interface... So instead, I do stuff like this. This is my prompt. I say, you know, I I found Go's email address in here to begin with. And then I'm like, okay, now uh give him Azure AI user and Azure AI project manager on this subscription that I'm looking at. And here it it does it right. So it will call a AZ this command line interface. And this is Warp's superpower... whenever there's a command line interface, a CLI that can do something, uh, warp is freaking great at that... I have also used this to administer GCP work just as well with G-Cloud the G-Cloud CLI so it's it's great at this stuff.

</details>

**Clarvo**: 我想说，如果你曾经被 AWS、Azure 或 GCP 的角色分配管理界面“折磨”过，这就是你想要看到的工作流。我想特别指出一点：作为一名长期从事开发工具工作的产品人，最大的挑战之一就是如何在这些极其复杂、互动的权限和配置集合上展示 GUI（图形用户界面）。这是一个非常困难的前端设计问题。

我之所以喜欢 AI 访问 CLI 工具、API 和 **MCP (Model Context Protocol)**，是因为你可以抽象掉所有的前端界面，让用户直接查询系统。如果你是像 Azure 这样的工具的构建者，这会让为用户提供接口变得简单得多。此外，这还替代了那种“搜索-复制-粘贴”的旧模式。以前我会去搜“如何杀掉 Adobe 的所有进程”，找到命令，粘贴进去，报错，再把错误搜一遍。而这种能访问终端和命令行的**代理化流程 (agentic processes)**，让你在一个界面里就能搞定一切。

<details>
<summary>Original English</summary>

**Clarvo**: I was going to say if you have been victimized by AWS Azure or GCP admin interfaces for assigning roles tools. This is exactly the kind of workflow you want to see... And what I love about AI having access to CLI tools, APIs, MCPs, all these ways to more programmatically access these capabilities is you can actually abstract away all of that front-end stuff and just let a user kind of query the system and get what needs to get done... And what I love about these more agentic processes that have access to the terminal and the command line is you can just do that allin-one allin-one interface.

</details>

### 案例二：让硬件变乖——用命令行控制扫描仪

**Marco Casalaina**: 完全正确。不过我得告诉你，让这些东西起作用是有技巧的。Warp 的确很神奇，但你可以通过几种方式让它运行得更顺畅。比如我会连接 **Microsoft Docs 的 MCP 服务器**。有时候我清楚要给什么角色，但有时我完全不知道某人需要什么权限才能完成某事。我会说：“给这个人任何他需要的角色，以便使用 Azure Document Intelligence”，让它去搞清楚。它会去查询文档，这让效果好得多。

另一个关键点是**规则 (Rules)**。我会给它设定规则，比如：“如果我要在资源组上分配角色，我需要先激活我的 Owner 权限。” 这是我常遇到的问题，如果不激活就会失败。所以我让 Warp 提醒我，它会问：“嘿，在开始之前你激活 Owner 权限了吗？” 这种 MCP 服务器和规则能极大地辅助它的工作。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Totally. Yeah. Exactly. Now, I will tell you though that it there's a trick to making this stuff work... I do connect this to the Microsoft Docs MCP server when I'm doing like Azure administration... Another piece of this and we'll see it in a moment is is the rules... I make warp remind me and warp will be like so hey did you activate your owner access before I start doing this because otherwise it's going to fail.

</details>

**Clarvo**: 你的提示词其实非常口语化，就像在聊天。很多人会觉得提示词必须遵循特定的格式或设计得非常优雅，但实际上，只要写下你希望系统遵循的两三个步骤，就能变得非常有效。说起这种步骤化的流程，你在 Warp 上做的另一件让我印象深刻的事，就是处理你女儿的家庭作业。能带我们看看你是怎么做的吗？

<details>
<summary>Original English</summary>

**Clarvo**: Well, and what I will call out, and this is no shade, but this is not the most sophisticated prompting I've ever received in my life. It's just like, "Hey, when you're trying to do this, remind me to do that..." And I think people get like wrapped around the axle on like my prompts have to be in this specific format... So, you want to walk us through how you did how you did that with your your daughter's homework?

</details>

**Marco Casalaina**: 好的。我女儿明天有数学考试，老师给了她一份练习卷。我会把卷子扫描进来，然后喂给 **ChatGPT**，让它出一些类似的变体题目（比如不等式之类的），这样她就能得到更多练习。

我需要扫描这份卷子。我的扫描仪有进纸器，但这份练习卷是双面的。我需要先扫描奇数页，再扫描偶数页，然后把它们合并在一起。我直接在 Warp 里输入：“从进纸器扫描文档，并以这个文件名保存到这个目录。” 它就直接照做了，完美搞定。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Yeah, let's talk about that. My daughter is studying for a math test right now... I'll scan it in and then I feed it to Chat GPT and I'm like make me variance of these problems... So, I needed to scan this in. Now, my scanner has a feeder, and so it sucks in the pages, but this was a two-sided uh practice test. And so, I needed to scan the odd pages, and then I needed to scan the even pages. Then, I needed to put it together. So, what do I do? I go to warp here and I say it exactly. Scan the documents from the feeder and save it to this directory as this file name. And it does. It totally does do that.

</details>

**Clarvo**: 等等，这真的激活了扫描仪吗？

<details>
<summary>Original English</summary>

**Clarvo**: Wait, can I can I pause you really quickly? Did this activate the scanner?

</details>

**Marco Casalaina**: 绝对激活了。如果我现在在家，你就能看到我的扫描仪立刻苏醒并开始工作。我只需要把纸放进进纸器，打完字，砰，它就开始了。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Absolutely it does... I would do this again and you would see my scanner would wake right up and start scanning... all I had to do was put the sheets in the feeder and as soon as I typed this thing in, boom, there it goes.

</details>

**Clarvo**: 对于正在收听的年轻人来说，作为父母，你会花大量时间摆弄扫描仪和打印机。如果你能从 AI 编码工具中远程启动扫描仪，那简直是效率的巅峰。

<details>
<summary>Original English</summary>

**Clarvo**: So for for the youths listening and watching this show, as a as a parent, you spend a lot of time with a scanner and a printer... this is peak peak efficiency if efficiency for me is being able to just uh remotely start the scanner um from from my AI coding tool.

</details>

**Marco Casalaina**: 不瞒你说，我还会扫描她的生日卡片、情人节卡片之类的。我非常担心哪天发生火灾，这些她制作的历史文献会被烧毁，所以扫描它们非常容易。

扫描完奇数页后，Warp 的优势体现出来了，它既是代理，也可以是非代理。我只需按向上键，调出刚才生成的命令行。我只需把命令里的 "odd" 改成 "even"，它就直接执行了，甚至不需要调用大模型。

最后，我说：“现在把奇数页和偶数页合并在一起，生成数学练习卷。” 它写了一段 **Python** 代码，安装了 `PyPDF2`，运行后又删除了临时文件。虽然我在这里是把 Warp 当作编码代理在用，但最终它确实创建了一个统一的文件。

<details>
<summary>Original English</summary>

**Marco Casalaina**: And I'm not going to lie, like I scan like her birthday cards... Then I type this in here and now there it is... I scanned one side. Now, uh, warp is kind of biodal... So you see the second time I did this, it had generated this command line here. Oh, and when I pressed up, it just go we'll go go straight to this command line... But then I wanted to put it together. So I said, now put together the odd pages and the even pages and just make the math practice test out of it. And so now it wrote some Python to do this... created a unified thing.

</details>

**Clarvo**: 我得给这些 AI 工具提个产品反馈：我想要一个“任务计时器”，显示“你在 112 秒内完成了这个任务”并撒花庆祝。因为如果你用传统方式：走去扫描仪，打开那个糟糕的驱动软件，下载 PDF，翻面，再扫描，下载，然后找个 PDF 编辑器手动拖拽页面排序，最后保存。那简直太烦人了。而现在你只需要坐在我们都向往的终端里，开着深色模式，直接发号施令。很多人不理解，你电脑上的很多操作其实都是可以程序化完成的。除非你开始使用这些代理，否则你不会发现命令行的无限可能。

<details>
<summary>Original English</summary>

**Clarvo**: Now I have to give um these AI coding tools and idees etc. a little product feedback which is I want like a time to task little timer here and I want it to say hey you did this in 112 seconds and give me like confetti... And instead you get to sit where we all want to live right now which is in the terminal in the terminal in dark mode and just ask it to do this thing... And until you start working with these agents, you don't really discover all the things that you can do with command lines.

</details>

**Marco Casalaina**: 没错。有趣的是，这促使我去寻找通过命令行做事的方法。扫描仪这个例子并非凭空产生的魔法。Windows 默认没有命令行调用扫描仪的方法，除非你安装了 **NAPS2**。我在 Warp 的规则里写道：“当你处于 Windows 环境且我让你扫描东西时，请使用 NAPS2。” 我告诉了它 NAPS2 的安装路径。这是一个开源的 Windows 扫描仪 CLI。我知道我经常要扫描东西，这个准备工作能帮我节省大量时间。这需要一点点前期的准备，才能让“魔术”奏效。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Well, what's interesting is it caused me to look for ways that I could do things with a command line. So this scanner thing, this wasn't magical... not a way in Windows to CLI invoke a scanner unless you install NAPS 2... and I what I said is when you're in Windows and I tell you to scan something, use Naps 2 to do it... Knowing that I scan things so frequently that this would save me a vast amount of time. Uh, so, you know, again, like it's magic, but it's not entirely magic. You do have to do a little preparation for this trick to work.

</details>

### 案例三：FFmpeg 视频重编码——消灭 1.7GB 的庞然大物

**Clarvo**: 我们还有一个案例。作为做播客且经常处理视频的人，我觉得这个非常有用。

<details>
<summary>Original English</summary>

**Clarvo**: and then you have one more use case which is I do as somebody who who does a podcast and works with a lot of videos is really useful um that I thought maybe you could walk us through.

</details>

**Marco Casalaina**: 没错。我自己也录制很多视频，虽然我的 YouTube 频道不像你的播客那么定期更新。昨天我用 Xbox Game Bar 录了一个 10 分钟的屏幕演示。不知道它在搞什么，录出来的文件居然有 **1.7GB**。这太离谱了。

于是我问 Warp：“为什么这个文件这么大？请使用 **ffmpeg** 对它进行重编码。保持 1080p 分辨率，但让它变成正常大小。” FFmpeg 是一个功能强大的视频编辑 CLI。我经常用它来提取音频，或者调整音量。比如有一次同事发的视频中间一段声音突然变小，我直接让 Warp：“用 FFmpeg 把 7 到 17 秒的声音放大 300%。” 它完全能搞定。

在这个例子中，它分析了文件，发现是因为码率高得离谱。然后它运行了 FFmpeg，按照我的要求完成了重编码。最后文件只有 **13MB**，这才是 10 分钟屏幕分享视频该有的大小。

<details>
<summary>Original English</summary>

**Marco Casalaina**: So, I record a lot of videos myself actually... Well, for 10 minutes of video, this thing recorded a 1.7 gigabyte file. I don't know what it was doing, but I mean it was insane... As you can see in my prompt here, I say, why is this file so big? Use ffmpeg to re-encode it. Still keeping it at 1080p because I didn't want it to like nestify the resolution and make it more normal size... It ran FFmpeg with whatever the switches were to re-encode this thing. And it did re-encode this down to 13 megabytes, which is what you would expect for like a 10-minute video of a screen share.

</details>

**Clarvo**: 这再次证明，与其搜索并下载乱七八糟的视频压缩软件，不如直接使用这些技术工具，几秒钟就能搞定，还能理解根本原因。

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. And so again like I think this is one of those things that in an alternative world somebody would have like gone to search and say like video compression software... and instead in just a couple seconds you can use this more technical tool and get a lot of stuff done and also sort of understand the root cause.

</details>

### 即时代理与自动化：未来的工作流

**Marco Casalaina**: 我把这种使用 Warp 的方式称为**即时代理 (ad-hoc agent)**。因为每当我处理这些事情时，我都是在飞行中创建一个临时的、未命名的微型代理来为我服务。这正在成为一种趋势。

<details>
<summary>Original English</summary>

**Marco Casalaina**: if you think about what I'm really doing with warp the way that I'm using warp I characterize it in a certain way I call this an ad hoc agent because effectively each one of these things that I'm doing... I'm kind of creating a little mini agent, an unnamed agent on the fly to do something for me.

</details>

**Clarvo**: 我建议大家习惯这种“随用随弃”的东西。如果你需要压缩视频，不需要保存脚本，下次直接再做一遍，那时候的模型可能更强大、更便宜、更简单。不要总想着把它变成一个产品，只要能搞定当下的任务就行。

<details>
<summary>Original English</summary>

**Clarvo**: And what I would say is also what I love about AI and what I would recommend to people with AI is like just get used to ephemeral stuff... Just next time do it over do it over again. Maybe save a rule so you're not rediscovering the steps, right?

</details>

**Marco Casalaina**: 没错。比如当它第一次尝试调用 NAPS2 扫描仪失败时，因为它找不到路径。所以我才设定了规则：“当我要扫描时，NAPS2 在这里；当我要从进纸器扫描时，使用这个开关。” 有了规则后，它再也没错过。即便目录、文件名或格式变了，它每次都能做对。

<details>
<summary>Original English</summary>

**Marco Casalaina**: And that's that's exactly the right idea, right? So when it you know, for example, like it happened once that it tried to call naps 2, the scanner thingy, and failed because it couldn't figure out what the path to naps 2 was... And now that it has that rule, it has never done it wrong since then, right?

</details>

**Clarvo**: 让我们转向一些不那么“技术”的案例。你在 **M365 Copilot** 里是如何通过构建触发式代理来处理日常行政任务的？

<details>
<summary>Original English</summary>

**Clarvo**: Well, let's switch over to maybe some less technical use cases, but ones I think are really interesting... how you're using sort of more administrative taskbased workflow based things to kind of be prepped for the work you need to do in a day.

</details>

**Marco Casalaina**: 好的。在 M365 Copilot 里，很多人只是问它“我今天要干嘛？”，它能看我的日历。但现在的趋势是，消费代理和构建代理之间的界限正在模糊。这是一个“构建代理的代理”。

我发起一个任务：“当我收到 Clarvo 要求在某个时间开会的邮件时，检查我的日历。如果那个时间有空，给她发一个 30 分钟的会议邀请。” 它会自动构建一个**触发式代理**。它能从邮件中提取时间（ISO8601 格式），调用 Outlook API 检查日历并创建邀请。一旦保存，它就成了我 Outlook 的一部分。如果你发邮件约我，只要我有空，你就会直接收到邀请。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Yeah. Well, I mean here I am in M365 Copilot... but what's happening now is that this and many general purpose agents like it are becoming agent builders. The line between consuming an agent and building an agent is blurring. So this is the new workflows agent. And this is an agent that builds an agent... What it has built is an agent. It's a triggered agent. It's an email triggered agent. And so an email comes from you and it will extract the time from it... it will check my calendar and it'll create the meeting invite.

</details>

**Clarvo**: 我太喜欢这个了。这能让你从任务的关键路径中解脱出来，让 AI 替你响应，从而保证高度的响应能力且不遗漏任何事情。

<details>
<summary>Original English</summary>

**Clarvo**: I'm not going to abuse it. But I do I do love it. Um, what I would say is really interesting here is the ability to set up synchronous response to asynchronous um, requests... Meaning, you know, if you can get yourself out of the critical path of doing a task and get AI into that path instead, you can be highly responsive and and not drop stuff.

</details>

### 闪电问答：AI 如何改变生活

**Clarvo**: 最后一个问题。当 AI 不听话时，你的策略是什么？

<details>
<summary>Original English</summary>

**Clarvo**: What is your tactic when AI is not listening? When it is not giving you the output you want, what do you do?

</details>

**Marco Casalaina**: 有时候我会很生气，直接骂它：“你这个笨蛋，我明确告诉你不要把 `.env` 文件提交上去，你还是做了！”（笑）。在 Warp 里，规则非常有用。你可能注意到了，我的规则里有一条：**永远不要提交 `.env` 文件**。

另外，我还会预设一些重复性的提示词短语。比如我有快捷键 `MB5`，它会自动扩展为：“请从微软的视角回答，字数不超过 500 字，不要使用列表或特定格式。” 我使用了 **AutoHotkey** 运行这些快捷键，将它们扩展为可重复使用的提示词。这些 snippets 都是我亲手打磨、反复测试出来的，非常有效。

<details>
<summary>Original English</summary>

**Marco Casalaina**: I mean, I sort of am in which I will often be like, "You boron. I specifically told you not to check in myv file and you did it anyway."... Now again, in Warp, there are rules. You might have noticed in my warp rules, if you look closely, there's a rule there that says never check in thev file... I also will pre-program certain types of prompts and so here let's say uh MB5... Answer from the perspective of Microsoft in 500 characters or less with no bullets or formatting... That is by the way auto hotkey that I have running there.

</details>

**Clarvo**: Marco，这太棒了。我非常喜欢利用大模型来解决这些微小摩擦点的想法。大家可以在 LinkedIn 上找到你，对吗？

<details>
<summary>Original English</summary>

**Clarvo**: Marco, this has been so great. I just I love the idea of again just solving these minor minor points of friction with our, you know, genius large language models and supporting tools. Where can we find you and how can we be helpful?

</details>

**Marco Casalaina**: 没错，在 LinkedIn 上搜 Marco Casalaina 就能找到我。我每隔几周或一个月会发布一些博客和视频，欢迎关注。

<details>
<summary>Original English</summary>

**Marco Casalaina**: Well, find me on LinkedIn. And that's probably the easiest place... you can see my new blog post and video there on my LinkedIn channel.

</details>

**Clarvo**: 非常感谢。感谢大家的收看，我们下期再见。