---
author: How I AI
date: '2026-04-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jwGQ9CrqVdA
speaker: How I AI
tags:
  - ai-workflow
  - productivity-tool
  - ai-agent
  - personal-automation
  - skill-creation
title: Claude Co-work非工程师使用指南：如何用AI代理搭建个人操作系统
summary: 本期节目深入探讨了Anthropic的AI协作工具Claude Co-work如何赋能非技术用户构建高效的个人AI操作系统。嘉宾JJ Angler（来自10X）与主持人Claire Vo分享了Claude Co-work的项目系统、子代理、技能、连接器及权限管理等核心功能。他们详细介绍了如何利用AI自动化处理邮件、Slack消息、作为思考伙伴，并通过定期任务实现日程管理。节目强调了AI在内容创作、活动策划、招聘流程等场景的应用，并讨论了用户在授权AI访问个人数据时的信任管理，鼓励用户探索AI工具以提升日常工作和生活效率。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - 10X
  - Tines
  - Canva
  - Coinbase
  - Databricks
  - GitLab
  - Mars
  - Reddit
  - OpenAI
  - Stripe
  - Figma
products_models:
  - Claude Co-work
  - Claude Code
  - Gmail
  - Google Calendar
  - Google Drive
  - Notion
  - Slack
  - Cursor
  - Whisperflow
  - OpenClaw
  - Pencil.dev
  - Remotion
media_books: []
status: evergreen
---
### AI代理视角下的项目系统

**JJ Angler**: 拥有这个**项目**系统，你现在正在进行编排。即使你可能不是一名开发者，你现在也是一名**AI**编排者。你可以同时运行多个**代理**，并拥有这种顶层视图，能够迅速看到哪个**代理**需要你的关注，然后给它们那些权限，或者重新进入。

<details>
<summary>Original English</summary>

**JJ Angler**: One of the things I love about having this project system, you're orchestrating now. Even though you might not be a developer, you're now an AI orchestrator. You can run many agents at once and have this top level view to be able to just quickly see which agent needs your attention and just give them those permissions or to pop back in.

</details>

**Claire Vo**: 我不知道。这听起来有点悲伤。我所有的朋友都是**代理**。我是一个独立创始人。我一个人很难确保我所有的想法都很棒。当你使用**子代理**时，它会启动三个不同的**代理**，每个**代理**都可以有自己的角色，带着一个全新的语境窗口，这意味着全新的视角去客观地审视你的工作。

<details>
<summary>Original English</summary>

**Claire Vo**: I don't know. This is like very sad. All my friends are agents. I'm a solo founder. It is like very hard to just me by myself ensure that all my ideas are great. When you use sub agents, it will spin up three different agents and each of those agents can have their own persona with like a fresh contact window, meaning like fresh perspective to go and look at your work in a objective way.

</details>

**JJ Angler**: 如果你是一个产品经理，就把它搭建起来，然后把你的老板、你的工程伙伴和你的客户放进去，然后说：“每次**PRD**评审都从这三个角度给我反馈。”如果你在市场营销领域，那么你的**ICP**。我认为这种多视角反馈机制在很多地方都非常有用。

<details>
<summary>Original English</summary>

**JJ Angler**: If you're a product manager, build it and like put your boss in there, your engineering partner, and your customer and say every PRD review from these three points of view and give me feedback. If you're in marketing, your ICP, I think there's just a lot of places where this multi- view feedback mechanism is super useful.

</details>

**Claire Vo**: 100%。我们可以更进一步，说：“嘿，创建这个**子咨询技能**。也许其中三个**代理**，比如一个**代理**就是你的老板，你派一个**代理**去研究你的老板是谁，他们的角色，他们的视角，让他们模拟出他们可能会给你的反馈，甚至在你去找他们之前。”这方面是无限的。你只需告诉**Claude**做什么，它就会为你完成。

<details>
<summary>Original English</summary>

**Claire Vo**: 100%. We could take this a step further and say, "Hey, create this sub-advisory skill. Maybe three of the agents, like one agent is literally your boss, that you send an agent to go research who your boss is, their role, their perspective, and have them simulate the feedback that they might give you before you even go to them. The sky's is the limit here. You just got to tell Claude what to do and it's going to go do it for you."

</details>

**Claire Vo**: 欢迎回到《我如何**AI**》。我是**Claire Vo**，产品负责人和**AI**狂热者，致力于帮助你们用这些新工具更好地进行建设。当**Claude Co-work**首次发布时，我相当怀疑，但我越来越多地听到，**Co-work**是我认识的每个人，尤其是那些比我们工程师技术水平稍低的人，日常工作的首选方式。这就是为什么我很高兴邀请**10X**的**JJ Angler**来到这里，他是一个**Co-work**的资深用户，他将退后一步，向我们展示如何在**Anthropic**的新工作工具上实现从零到一。我们开始吧。本集由**Tines**赞助，这个智能工作流平台为世界上最重要的工作提供动力。业务发展速度快于支持它的系统。团队被重复性任务、分散的工具和难以获取的数据所困扰。**AI**有巨大的前景，但在一切都碎片化的情况下却举步维艰。**Tines**解决了这个问题。它在一个安全、灵活的平台上统一了你的工具、数据和流程，融合了**Agette AI**自动化和以人为本的干预。团队节省了时间，工作流程运行更智能，**AI**真正提供了实际价值。现在，客户每周自动化超过15亿次操作。**Tines**受到**Canva**、**Coinbase**、**Databricks**、**GitLab**、**Mars**和**Reddit**等公司的信任。请访问tines.com/howi**AI**试用**Tines**。**JJ**，欢迎来到《我如何**AI**》。

<details>
<summary>Original English</summary>

**Claire Vo**: Welcome back to How I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. When Claude Co-work first came out, I was pretty much a skeptic, but I have been hearing more and more that co-work is the way that everybody I know, especially those who are a little less technical than us engineers, get their daily work done. Which is why I'm so excited to have JJ Angler here from 10X who is a co-work power user but is going to take a step back and show us how to zero to one on Anthropic's new get work done tool. Let's get to it. This episode is brought to you by Tines the intelligent workflow platform powering the world's most important work. Business moves faster than the systems meant to support it. Teams are stuck with repetitive tasks, scattered tools, and hardto-reach data. AI has huge promise but struggles when everything underneath is fragmented. Times fixes that. It unifies your tools, data, and processes in one secure, flexible platform. Blending Agette AI automation and human-led intervention. Teams get their time back, workflows run smarter, and AI actually delivers real value. Customers now automate over 1.5 billion actions every week. Tines is trusted by companies like Canva, Coinbase, Databricks, GitLab, Mars, and Reddit. Try Tines at times.com/howi AI. JJ, welcome to How I AI.

</details>

**JJ Angler**: 很高兴来到这里。谢谢你的邀请。我很高兴你能给我们展示什么，因为当**Claude Co-work**——也就是我们要谈论的——刚发布时，我写了一篇在**Twitter**上引起轰动的文章，很多播客也谈论了它，文章标题是“**Co-work**到底为谁而生？”因为我第一次尝试时，它看起来就像是在**Claude Code**之上简单地叠加了一个UI。我看了看，然后说：“好吧，如果你不是整天在**Cloud Code**终端中编写代码的人，但你又不是超级技术人员，那么这个介于两者之间的产品是什么？”你知道，我真不该这么想，因为事实是，产品周复一周地持续进步。**Anthropic**团队，**Claude**团队，都在不停地努力。我不断从我的非技术朋友那里听到：“天哪，**Co-work**太棒了！”或者“天哪，我现在用**Co-work**来完成我工作中的一切。”然后，你知道，我在过去几周也试用了一下，它的UI确实达到了要求。它能做的事情也确实达到了要求。所以，我非常高兴你能向我们展示**Co-work**的从零到一。我只想问你，是什么让你迷上这个特定工具的？

<details>
<summary>Original English</summary>

**JJ Angler**: It is a pleasure to be here. Thank you for having me. I'm excited about what you're going to show us because when Claude Co-work, which is what we're going to talk about, first came out, I wrote this article that kind of blew up on Twitter and a bunch of podcasts talked about it, which was, "Who is Coowwork for anyway?" Because when I first tried it, it seemed like a UI that had just been slapped on top of Claude Code. And I looked at it and I said, "Okay, if you're not, you know, in cloud code all day writing in the terminal, but you're not super technical, like what is this product that's in the middle?" And, you know, shame on me because as it happens, product continues to progress week over week. The anthropic team, the Claude team is cooking non-stop. And I just kept hearing more and more from my non-technical friends, "Oh my god, co-work's amazing." or oh my god, I use co-work to do everything in my job now. And then, you know, I've given it a spin in the past couple weeks and the UI has really gotten there. What it can do really has gotten there. And so, I'm so excited for you to show us the zero to one for co-work. And I just have to ask you, what got you hooked on this particular tool?

</details>

**Claire Vo**: 是的，我想很多人都和我们一样，只是在实验，然后我很快发现连接你的业务工具是多么容易。而你知道，我用**Claude Code**做了很多东西，但如果我想连接我的**Slack**、我的**Gmail**、我的**Notion**，**Co-work**只需一键操作，然后突然间，**AI**就能处理所有这些信息，帮助你更好地完成工作，而且它非常容易。就是这样开始的，但我后来开始深入研究它，我发现它真的帮助了我日常工作，所以我使用**Co-work**来处理我所有的生产力事务，比如发邮件、处理**Slack**、构建项目和文档，然后我仍然用**Claude Code**来构建。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah, I think like many, we were just experimenting with it and then quickly I saw that how easy it was to connect your business tooling to it. uh whereas like you know I built a lot latin cloud code but if I wanted to just connect my my Slack my Gmail my notion co-work is just one click and then all of a sudden you have an AI processing all of that information helping you do your job better and it's just so easy and so like that's where it started but then I started to like really like go deep on it I'm like oh my god this is really helping me my dayto-day so I use co-work for all of like my productivity stuff of like emailing slacks building projects and documents and then cloud code I still build with.

</details>

**JJ Angler**: 我喜欢这一点，因为每个人都在说：“哦，一切都将是**CLI**或**API**或**TUI**，所有这些东西。”但我认为人们只是喜欢点击一个按钮。我不知道。他们只是……

<details>
<summary>Original English</summary>

**JJ Angler**: I love that because everybody is saying, "Oh, everything's going to be a CLI or an API or a TUI, all this stuff." And I'm like, people just love clicking a button. I don't know. They're just

</details>

**Claire Vo**: 人们想要一个按钮。所以，我从你这里听到的一部分是，它给了你一个按钮，可以连接到你所有的业务数据，然后当你在**Co-work**中工作时，你处于一种业务思维模式，个人生产力思维模式，然后当你在**Claude Code**中时，你处于构建者思维模式。是的，没错。你知道，我马上会拉出我的屏幕，但是你知道，**Anthropic**桌面应用程序有三种不同的模式。聊天、**Co-work**和**Claude**。我们现在已经使用聊天很久了，比如**ChatGPT**等等。我想大多数知识工作者也都在聊天模式中。但是切换到**Co-work**这个标签，是这些知识工作者，即使他们不擅长技术，也可以开始用**AI**做更多事情的第一个转变。它让你在非常相似的聊天界面中用**AI**做很多事情，但实际上它在为你做事情，而在聊天中，就像“酷，你告诉我怎么做，但现在我得自己去做”。**Co-work**实际上是在为你做事情。

<details>
<summary>Original English</summary>

**Claire Vo**: people want a button. So, part of what I hear for you is like it gave you a button to click to get connected to all your business data and then when you're working in co-work, you're in sort of like business mindset, personal productivity mindset, and then when you're in cloud code, you're in builder mindset. Yeah, exactly. And you know, I'll pull up my screen in a second here, but you know, the anthropic desktop app has three different modes. Chat, co-work, and claude. We've been in chat for a while now with chatbt, etc. Like I think most of the knowledge workers are like in chat mode, too. But the co-work switch over to that tab is like the first kind of switch where these knowledge workers, even if they're not technical, can start doing more with AI. And it enables you to just do so much with AI in a very similar chat interface, but where like it's actually doing stuff for you where like in chat it's like cool, you told me what to do, but now I got to go do it. Co-work is literally doing it for you.

</details>

**JJ Angler**: 你为什么不开始展示你的屏幕呢？你将向我们展示，如果你是**Co-work**的全新用户，如果你把所有时间都花在那个聊天标签上，并且你准备好点击**Claude**桌面应用程序中那个中间标签**Co-work**，你会怎么做？我只想提醒大家，**Co-work**在**Claude**桌面应用程序中可用。所以我想你必须在桌面版上，而不是网页版。它再次显示为顶部这三个标签中的一个。中间那个写着**Co-work**。你必须点击那个。然后你将向我们展示我们到了那里之后该怎么做。

<details>
<summary>Original English</summary>

**JJ Angler**: Why don't you get your screen started and you're going to show us if you were completely brand new to co-work if you had spent all your time in that chat tab and you ready to click that middle tab co-work in the cloud desktop app what you would do. And I just want to call out for folks, uh, co-work is available in the clawed desktop app. So I think you have to be on desktop, not web. And it shows up again as one of these three tabs across the top. The middle one says co-work. And you have to click that. And then you're going to show us what to do once we're there.

</details>

### Claude Co-work项目与情境管理

**Claire Vo**: 好的，我在这里打开了**Co-work**。这是在桌面应用程序上。他们也有移动应用程序。移动应用程序与**Co-work**的配合不如桌面版好。呃，这正是**Claude Code**仍然非常强大的地方。但是**Co-work**，让我给你解释一下。所以**Co-work**实际上可以访问你的桌面。很多人在早期会说：“嘿，**Co-work**，去给我整理文件夹”或者“去给我整理这些收据”。是的，**Co-work**可以做到这一点，但是**Co-work**也能做更多。**Co-work**可以访问你的电脑。它可以访问你的浏览器。它可以代表你执行操作。呃，如果你需要点餐或预订晚餐，它会去你的浏览器上为你查找餐馆，然后联系它们等等。现在，当你开始使用**Co-work**时，你会进入一个新任务，它会要求你打开一个**项目**。

<details>
<summary>Original English</summary>

**Claire Vo**: So I have co-work pulled up here. This is on the desktop app. And they also have a mobile app as well. Mobile app does not work as well with co-work. Uh, that's where kind of cloud code continues to be really powerful. But co-work, let me give you the lowdown here. So co-work can actually access your desktop. And a lot of people in the beginning days of like, hey co-work, go and like organize folders for me or go and like organize these receipts for me. And yes, co-work can do that, but co-work can do so much more as well. Co-work accesses your computer. It can access your browser. It can perform actions on your behalf. uh if you need to order or you know book reservations for dinner, it will go find you know restaurants looking for you on your browser you know contact contact them etc. Right now when you get started with co-work you'll go to a new task and it's going to ask you to open up a project.

</details>

**Claire Vo**: 好的，现在这是一个非常重要的概念，呃，很多人会在这上面犯难，就是什么是**项目**？好吧，最简单的形式，一个**项目**就是你电脑上的一个文件夹。这是我们工作的地点，也是我们存储这个**项目**所有文件的地方。所以，如果我看一下我的电脑，我有一个叫做**JJ**的位置，在**JJ**这个位置里，我有**项目**，这是我构建所有**项目**的地方。现在，其中一些是**Claude Code****项目**，另一些是**Co-work****项目**。**Co-work**是一个非常好的**Claude Code**入门工具，它教你一些基本的技能，比如如何在**Claude Code**中操作，而无需完全进入终端模式，所有这些东西。所以在这个里面，我有一个常用的工作区，我称之为**Claude****协作工作区**，它是一个通用的高层工作区，我用我称之为“我的大脑”来启动这个工作区。好的，所以我的大脑会非常详细地说明我的工作偏好是什么？我合作的团队成员是谁？如果我真的打开这个，我只会按空格键。它只是一个**MD**文件，本质上就像一个文档文件，一个文本文件。这是一系列非常具体的指令，你知道，也称为**提示**，**Claude**可以阅读这些**提示**，从而非常迅速地了解你是谁，你喜欢如何工作，你与谁合作，以及你所有的不同偏好。这样，一旦我在**Co-work**中触发一个**提示**，它就会获得所有这些信息，并且对我了解更多。有时我们在**ChatGPT**中，我们有这样一个线程，比如“哦，这是我所有产品营销的线程”，这是我用来思考这个或那个的线程。你有一个包含很多良好上下文的线程，这对你来说非常重要，但你无法将其转移到任何地方。如果你花时间设置你的文件夹，你就可以构建这些线程，但以一种非常可转移的方式，让你每次在**Co-work**中做任何事情时，都可以带上那个上下文。这才是真正的突破。有了**Co-work**，你不是从头开始。如果你构建这些**项目**，你从一个非常好的起点开始，**Co-work**已经了解你，你的偏好，所有这些东西，然后它就像一个伙伴一样开始和你一起工作。好的。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay now this is a very important concept that uh a lot of people kind of get stumbled on is like what is a project? Well in the simplest form a project is a folder on your computer. This is where we are going to work out of and store our files for this project within that area. So if I look at my computer, I have a location called JJ and within location JJ, I have projects and this is where I build all of my projects. Now some of these are cloud code projects and some of these are co-work projects. Co-work is a really great like on-ramp to cloud code, teaching you some of the basic skills of like how to operate in cloud code without going full terminal mode, all that kind of stuff. So within this I have a popular workspace that I use called claude co-workspace that is like a generic highle workspace and I start off this workspace with what I call is my brain. Okay, so my brain goes into very detail of like what are my working preferences? Who are the team members that I work with? And if I were actually to open this up, I'm just going to hit spacebar. It's just an MD file, which is essentially like a doc file, a text file. This is a very specific series of instructions that we, you know, also known as a prompt that Claude can read to get up to speed very quickly of who you are, how you like to work, who you work with, and all of your different preferences. This way, once I trigger a prompt within co-work, it gets all of this this information with it and just knows so much more about me. And sometimes we had like in uh you know chatbt we had like that one thread of like oh this is my thread for like all my product marketing and this is my thread for like uh brainstorming about this or whatever. You had like that one thread with a lot of good context that was like very important to you but you couldn't transfer it anywhere. If you set up the time with your folders, you'll be able to build those threads, but in a very transferable uh way that allows you to take that context and bring it with you every single time you want to do anything in co-work. And that is the big unlock here. With co-work, you're not starting over from the start. If you build up these projects, you're starting from a really good place where co-work already knows about you, your preferences, all that kind of stuff, and then it just starts doing stuff with you as a a as a partner here. All right.

</details>

**JJ Angler**: 是的。在你向我们展示如何在这里创建一个新**项目**之前，我只想向大家指出一些事情，因为你知道，如果你对这些**AI**概念，我姑且说是2011年水平的**AI**概念，从聊天到**项目**会感到非常困惑。我记得**Anthropic**推出**技能**时，人们都在问“什么是**技能**？”我当时想，**技能**实际上就是一个描述你想要做什么的文件。让我把它说得非常简单。它就是一个文件。那么**项目**又是什么？一个**项目**实际上就是一个包含文件的文件夹。所以，你知道，你不需要被这些概念吓倒。它只是——我正在做一些事情。我要为此创建一个文件夹，一个驱动器。我将把所有我的上下文都放在那个文件夹中。所以，无论何时我回来处理那个工作，我都有我正在处理的文件。这就是我们每天在业务中工作的方式，对吗？你通过文件夹来组织你的**G Drive**或你的**Notion**。完全相同的概念，只是这次**Claude**可以进入并实际上在那个工作区中与你一起完成一些工作。

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah. Before you show us how you'd create maybe a new project here, I just want to call out some some things for folks because you know if you're new to some of these like I would say 2011 level AI concepts going from chat to projects you get really confused. I remembered when Anthrobit came out with skills and people were like what's a skill? I'm so and I was like skill is literally like a file that describes what you want to do. Like let me just make it very simple for you. It's a file and then what's a what's a project? A project is just literally a folder with files in it. And so, you know, you don't have to be intimidated by these concepts. It's just I'm working on something. I'm gonna spin up a folder, a drive for this. I'm going to put all my context and capture all my context in that one folder. So, anytime I come back to work on that, I have the files that I'm working for. And this is how we work in business every day, right? You organize your G Drive or your notion by folders. exact same concept except this time Claude can go in and actually do some work in in that workspace alongside you.

</details>

**Claire Vo**: 说得好。正是如此。实际上，在今天的会议中，我们将构建一个日常操作系统，我将在节目结束时提供给大家下载。所以一定要坚持到最后。我只是想继续总体解释一下我们将要做什么，然后我们就会动手操作，一起开始做。

<details>
<summary>Original English</summary>

**Claire Vo**: Great call out. That's exactly it. And actually in this session today we are going to be building like a daily operating system that I will make downloadable for you all to get at the end of the show. So definitely stick with us for that. I do just want to continue like overall explaining like what we're going to do and then we're going to get hands- on keyboard and start doing it together.

</details>

**JJ Angler**: 好的。

<details>
<summary>Original English</summary>

**JJ Angler**: Great.

</details>

**Claire Vo**: 是的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah.

</details>

**Claire Vo**: 好的。嗯，这就是我的通用架构，在顶层我有一个**工作区地图**。所以这本质上就是我说的：“嘿，**Claude**，查看这个文件夹中的所有文件夹或文件，并生成一个**工作区地图**来帮助你更好地导航。”这样，无论何时我在这个工作区中，我发送一个**提示**，**Claude**都会查看那个**工作区地图**，然后说：“哦，嘿，他需要一篇**Twitter**帖子的帮助。我要进入他的**Twitter**文件夹，使用他已经准备好的那个**技能**，然后以那种方式写出来。”如果没有那个**工作区地图**，有时**Claude**必须摄取所有这些东西，这会消耗更多的**tokens**，并且会有点混乱，因为你给**Claude**发送了大量的上下文，而它可能只需要知道你喜欢如何在**Twitter**上写作，仅此而已。所以，**工作区地图**帮助**Claude**更好地导航你的文件夹结构。而且，同样，它就像连接**Claude**到任何文件夹一样简单，然后说：“嘿，**Claude**，给我创建一个**工作区地图**。”它会映射出所有内容并为你创建。

<details>
<summary>Original English</summary>

**Claire Vo**: Cool. Um, so this is my general architecture here and at the top level I have this workspace map. And so this is essentially something I said, "Hey Claude, look through all of the folders in this or files in this folder and generate a workspace map to help you navigate this better." So that way whenever I'm in this workspace, Claude and I send a prompt, Claude will look at that workspace map and say, "Oh, hey, he needs help with a Twitter post. I'm going to go into his Twitter folder, use that skill that he's already prepared, and then write it that way. Without that workspace map, sometimes Claude has to ingest all of that stuff, which takes up more tokens, and it kind of makes it a little bit muddy because you're sending a lot of context to Claude where maybe it just needs to know how you'd like to write on Twitter, and that's it. So, the workspace map helps Claude navigate your folder structure in a better way. And again, it's as simple as connecting to Claude to any folder and just saying, "Hey, Claude, create a workspace map for me." It's going to map everything out and create it for you.

</details>

**JJ Angler**: 是的。我喜欢使用像**Claude**这样的工具，尽管其他工具也可以在桌面文件夹中做到这一点，但它在浏览文件和了解其中内容方面比我快得多。所以你实际上可以，你知道，我认为这是一个任何人都可以使用的技巧，那就是每当你试图让自己适应某个工作时，无论是**repo**，还是你的同事与你分享的文件夹，你都可以在**Claude**中打开它，然后说：“这里面有什么？甚至给我建一个地图，告诉我一切在哪里。”这会非常有帮助。但我们来谈谈你实际是如何开始的，因为你给我们展示的有点像最终状态。我想人们会说：“好的，这很棒。我可以拥有一个包含我‘大脑’的**项目**。”

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah. What I love about working with a tool like Claude, although other tools also do this in a desktop folder of files, is it is much faster at browsing files and figuring out what's going on in there than I am. And so you can actually, you know, I think this is a trick that anybody can use, which is whenever you're trying to orient yourself to something, some work, whether that's a repo, whether that's a folder that somebody your colleague shared with you, you can open it in Claude and then just say what's going on in here and build even build me a map to where to where everything is is and that can be very helpful. But let's talk about how you actually kind of get started because you're showing us kind of a little bit of the end point. And I think people are saying, "Okay, this is great. I can I can end up with this project that has my brain in it."

</details>

**Claire Vo**: 嗯，但是你是怎么开始的？

<details>
<summary>Original English</summary>

**Claire Vo**: Um, but but how do you get started?

</details>

**JJ Angler**: 当然。所以，我将进入这里的**项目**，然后我将创建一个新文件夹。好的。这个文件夹将被称为“日常操作系统”。好的。我将把它放回我的**项目**中。好的。这是所有事情的开始。然后它是一个空文件夹。现在我将回到这里的工作代码中。我将在这里打开它。我将转到不同的文件夹**项目**“日常操作系统”。就是这样。我们将允许**Claude**在其中操作。它会问：“嘿，你想要使用这两个还是只使用这个？”我将取消选中这个，因为我现在只想使用这个文件夹。好的。所以，我可以对它说任何我想说的话。但通常，我会说：“嘿，**Claude**，我想构建一个日常操作系统。这个操作系统将帮助我管理日常工作，并在我的工作场所成为超级英雄。所以，我希望这个操作系统在很多方面帮助我。首先，我将让它帮助我处理我的电子邮件，不仅帮助我理解我的收件箱，还帮助我写出更好的电子邮件。我还会用它来帮助我查看我的**Slack**，并弄清楚我需要如何回应我的队友，然后帮助我写一些**Slack**消息。然后我还想要一个思考伙伴，一个可以像导师一样帮助我做出艰难决定的人。所以我将逐步要求你做一些事情来帮助构建一些**技能**，但首先要为这个**项目**奠定基础。”

<details>
<summary>Original English</summary>

**JJ Angler**: Sure. So, I'm going to go into projects here and I'm going to create a new folder. Okay. And this folder is going to be called daily operating system. Okay. And I'm just going to bring it back into my projects there. All right. This is the start of everything. And then it's an empty folder. Now I'm going to go back into codework here. I'm going to open that up here. I'm going to go to different folder projects daily operating system. There we go. We're going to allow claude to operate within that. And it's saying, hey, do you want to use both of these or just this? And I'm going to uncheck this cuz I only want to use this folder right now. Okay. So, I can say anything I want to this. But generally, what I'm going to say is, hey Claude, I want to build a daily operating system. This operating system is going to help me manage my day-to-day and become a superhero within my workplace. So, I want this operating system to help me in a variety of ways. First, I'm going to have it help me work through my emails and and help me not only understand my inbox, but help me write better emails. I'm also going to use it to help me look through my Slack and figure out how I need to uh respond to some of my teammates and then help me write some of those Slack messages. And then I also want a thinking partner, someone that can act as like a mentor to me and help me through tough decisions. So I'm going to go through and ask you some things to help build some skills but start to lay the foundation for what this project is together.

</details>

**JJ Angler**: 所以那里有很多东西，我想说，这不像你希望的那么多。这主要是一个以聊天为中心**体验**。你可以直接开始，它甚至可能不像那样。它只是像你可以直接开始一个任务。它完全取决于你想要什么。当你越来越适应它时，**Claude**会适应这一点。嗯，但我认为关键是不要让那个大**提示**吓到你。有很多不同的方式可以进入。好的。现在，第一部分是，**Claude**看了我的**提示**，然后说：“好的，我有一些问题要问你。”现在，它将开始问我一些问题。所以，你想把这些文件存储在哪里？我想把它存储在我的日常操作系统文件夹中，就像它推荐的那样。你希望如何与日常操作系统互动？我目前将按需进行，这本质上意味着，无论何时我想与它互动，我都会进入**Co-work**并与它互动，但我也将向你展示如何自动化一些事情。呃，对于思考伙伴，呃，哪种支持对你来说最重要？嗯，我真的很喜欢职业指导和决策框架。好的。所以，我们现在正在进行这个事情，让我解释一下**Co-work****项目**，因为这是一个全新的功能，我非常喜欢它。所以，现在我们正在聊天。好的。我们也可以开始一个新的聊天，你可以看到我这里有正在进行的任务。所以，这个视图有点像一个很好的编排视图，可以看到正在为我工作的**代理**。但是**项目**允许你将它提升到一个新的水平。所以，我可以通过进入这里的**项目**来创建一个新**项目**。我将从现有文件夹创建一个新**项目**。这与我们已经创建的日常操作系统文件夹是同一个文件夹。所以，我将进入那里，**项目**，日常操作系统，打开。它将打开这个新文件夹。这个**项目**的指令是什么？我将使用这个文件夹和操作系统来帮助我应对一个忙碌专业人士的日常生活。你将通过应用一些**AI**魔法来帮助我获得一些**超能力**。好的。我暂时就放在那里。所以，我们现在处于一个**项目**界面。好的。如果我想回到那里，我点击**项目**，查看我所有不同的**项目**，然后进入**项目**界面。现在，它的重要性是什么，为什么我们是在一个**项目**而不是一个任务中？好吧，这些任务，它们都有效，但是**项目**允许你开始将任务串联起来，这意味着共享记忆。好的，所以我可以找到这里的这个任务，这个我刚才聊天的任务，我可以去把它移到这个**项目**中。好的，现在这个**项目**，这个聊天，以及我拥有的任何其他聊天，它们都共享相同的上下文，并且**Claude**知道你正在做什么，并且可以将所有新事物整合在一起。好的。所以，如果你做任何新事情，它会非常具体地知道你之前关于这个话题的聊天，并从你上次中断的地方继续。

<details>
<summary>Original English</summary>

**JJ Angler**: So there's a lot there and I'd say like this isn't much as you want it to be. Like this is very a chat focused experience. You could just start this off and it couldn't even look like any of that. It's just like you could just start in a task. It's however you want it to be. And as you grow more comfortable with it, uh, Claude will adapt to that. Um, but I think the general point is like don't let that big prompt like scare you. There's a lot of different ways to enter this. All right. Now, the first part is, okay, Claude looked at my prompt and it says, "Okay, I have some questions for you." Now, it's going to start asking me some questions. So, where do you want to store these files? I want to store it in my daily operation systems folder like it recommended. How do you want to interact with the daily operating system? I'm going to be doing it um on demand at the moment which essentially means like whenever I want to interact with it I will go into co-work and interact with it but I will also show you how to automate some of the stuff too. Uh for the thinking partner uh what kind of support matters most to you? Um I really like like career coaching and decision frameworks frameworks there. All right. So, we have this thing going here right now and let me explain co-work projects because this is a brand new feature and I absolutely love it. So, right now we are in a chat here. Okay. And we can start a new chat as well and you could see that I have active tasks going on here. And so, this view is kind of like a good orchestrator view of like seeing the agents that I have working for me. But projects allows you to take that to the next level. So, what I could do is I can go into a project here and I can create a new project. And I'm going to create a new project from an existing folder. That's the same folder that we've already created with the daily operating system. So, I'm going to go in there, projects, daily operating system, open. And it's going to open this new folder. And what is the instructions for this project? I'm going to use this folder and operating system to help me navigate the day-to-day life of a busy professional. you're going to help me with some superpowers by play applying some AI magic to it all. All right. And I'm just going to keep it there for now. So, we are now in a project interface. All right. And if I ever wanted to get back to that, I click on projects, see all my different projects, and then go into the project interface. Now, what is the importance of like why are we in a project rather than a task? Well, these tasks, they all kind of work, but projects allow you to start chaining tasks together, which means shared memory. Okay, so I can find this task right here, this this uh chat that I just had, and I can go and I can move it into this project. Okay, now this this project, this chat right here and if any other chat that I have, they all share the same context and they all and Claude knows what you're working on and can bring that with all the new stuff together. Okay. So, if you do anything new, it is very specifically knowing like what other chats you've had about this and picking up where you've left off.

</details>

**JJ Angler**: 是的。所以，人们需要知道两件事，从组织的角度来看，一是我们将选择你电脑上的一个文件夹，它包含你正在处理的特定领域的所有文件和上下文等等。然后，二，你将把那个文件夹附加到称为“**项目**”的东西上，它在左侧导航栏中可用，以确保每次你在这个文件夹或这个主题中工作时，你不仅在使用那些文件，还在使用你正在积极处理或过去处理过的所有其他事情的记忆。然后你可以给它，呃，如果你看右上角，你可以给它一些通用指令，这对于指导你在这个特定**项目**中做的任何工作都很有帮助。

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah. So, there are two things that people need to know about from an organization perspective, which is one, we're going to pick a folder on your computer that contains all the files and context and all that stuff for a specific area you're working on. And then two, you're going to attach that folder to something called projects, which is available in the lefthand nav, to make sure that every time you're working in that folder or in that topic, um you're not only working with those files, but you're working with the memory of all the other things that you're either actively working on or have worked on in the past. And then you can give it um if you see in the top right you can give it just general instructions which is helpful for um guiding any work you do in that in that specific

</details>

**Claire Vo**: 并且这是特定的**项目**指令，所以每个**项目**的指令可以有所不同，对吧？这也提供了很好的上下文。是的。说到上下文，如果你看右侧，有一个名为“上下文”的部分。那里正是我们讨论过的，也就是文件夹的上下文，以及为这个**项目**生成的记忆上下文。

<details>
<summary>Original English</summary>

**Claire Vo**: and this is specific project instructions and so each project can vary for different kinds of instructions right which is also really good context to have. Yeah. And speaking of context, if you look along the right hand side, there is a section that says context. And there's exactly what we talked about, which is the context of the folder and then the context of the memory that's been generated about this project,

</details>

**JJ Angler**: 对吧？所以这就像你所做的每个**项目**的**总部**，对吧？它对我来说真的很有帮助，因为当你开始有更多的任务时，那个**项目**的所有不同**代理**都会列在这里。你可以看到一个高层编排视图，了解哪个**代理**正在工作，哪个**代理**需要你的帮助。呃，所有这些任务和对话都为了共享记忆而共享在一起。再次强调，我们希望**Co-work**为我们做事情，我们希望它做好，并给我们良好一致的结果。有时，当我们在这种高层次上操作时，它会获取关于我们正在做的所有不同事情的大量信息，结果可能会变得混乱或模糊。但是，如果你在一个**项目**中操作，它会有关于特定**项目**和你要求的非常具体的上下文。它帮助你更快地获得结果。就像**提示**实际上更快，因为你发送的联系更少。你节省了**tokens**，因为你更专注和有条理，并且你只是以更一致的方式获得更好的结果。好的。

<details>
<summary>Original English</summary>

**JJ Angler**: right? And so this is like the HQ for each project that you work on, right? And it's really become so helpful for me because as you start to have more tasks, all of the different agents for that project are listed here. And you could see like a highle orchestrator view of like which agent is working, which agent needs your help. Uh and all of those tasks and conversations are like shared together for that shared memory. Again, we want co-work to do stuff for us and we wanted to do it well and give us good consistent results. Sometimes when we operate at this high level, it's getting so much information about all the different things we're doing and the results can get confusing or fuzzy. But if you're operating within a project, it's very specific context about the specific project and your requirements for it. And it helps you get results faster. Like the prompts are literally faster because you're sending less contacts. You're saving tokens because you're more focused and organized and you just get better results in in a more consistent way. All right.

</details>

**Claire Vo**: 好的。那么，让我继续构建这个，这样我们最终就能在节目结束时提供一些你可以下载的东西，开始用于你自己的日常操作系统。听起来不错吗？

<details>
<summary>Original English</summary>

**Claire Vo**: Great. So, let me continue to build on this so we can eventually have something that you can download at the end of this show to start using for your own daily operating system. Sound cool?

</details>

**JJ Angler**: 是的，我们开始吧。

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah, let's do it.

</details>

### 连接器与AI写作技能

**Claire Vo**: 好的。所以，呃，这里有几件事我想指出，**连接器**，非常重要。所以，要添加一个**连接器**，我将在这里右键单击，然后进入**连接器**。我可以看到我已经启用了一些我的**连接器**，但我只是在这里点击，这样你就可以看到这个视图。所以，**连接器**允许你将你的系统连接到**Co-work**。好的，所以现在我已经连接了**Gmail**、**Google Calendar**、**Google Drive**、**Notion**和**Slack**。如果我想添加更多**连接器**，我可以去浏览**连接器**，我可以看到一大堆我可以使用的**连接器**。通常它只需要一键操作，你进行认证，然后它就连接好了。这本质上意味着**Co-work**可以访问那个应用程序以及那个应用程序中的许多操作。如果我想进入我的**Gmail**连接，我可以看到**Co-work**现在可以访问所有这些工具，并且实际上可以为我执行这些操作。如果我想非常具体地设置权限，我可以在这里说：“嘿，**Co-work**，呃，我不允许你创建电子邮件草稿或做某事，但我允许你做这个，或者有时我希望你做这个，但总是向我请求许可。”所以，对于每个**连接器**，你可以进入并修改那些权限，但总的来说，这为你提供了与你的工具的连接，你可以使用这些工具。现在我可以回到这里的**Co-work**，我将回到我的**项目**日常操作系统。我要做的第一件事是说：“嘿，分析我的**Gmail**，特别是过去30天我发送的电子邮件，并利用这些来创建一个专门用于我撰写电子邮件的写作**技能**，使用我的电子邮件作为我写作结构的例子。所以，无论何时我将来想让你撰写电子邮件，你都知道我确切的写作方式，并且你会使用这个**技能**。”

<details>
<summary>Original English</summary>

**Claire Vo**: Cool. So, uh, with a couple of things that I want to call out here, connectors, so important. So, to add a connector, I'm going to rightclick here and I'm going to go into connectors. And I can see that I've already enabled some of my connectors, but I'm just going to click here so you can see this view. So, connectors allow you to connect your systems to co-work. Okay, so right now I have connected Gmail, Google Calendar, Google Drive, Notion, and Slack. And if I wanted to add more connectors, I can go to browse connectors and I can see a ton of connectors that I could do. It's normally like a one-click you authenticate and it comes in and you're connected. That essentially means Co-work has access to that application and a lot of those actions within that application. If I wanted to go into like my Gmail connection here, I could see that Co-work now has access to all of these tools and can actually do these for me. And if I wanted to get very specific about the permissions, I can go in here and say, "Hey, Co-work, uh, I'm not going to allow you to create an email draft or to do something, but I am going to allow you to do this or sometimes I want you to do this, but always ask me for permission." So with each connector, you can go in and modify those permissions, but generally this gives you a connection to your tools that you can use. Now I can go back into co-work here and I'm going to go back into my projects daily operating system. And the first thing I'm going to do is say, hey, analyze my Gmail, specifically the emails that I have sent in the last 30 days and use this to create a writing skill specifically for emails that I write using uh my emails as an example of my writing structure. So whenever I want you to write an email in the future, you know exactly how I write my emails and you'll use this skill.

</details>

**Claire Vo**: 所以这将开始为我构建一个电子邮件**技能**。它将通过连接到我的**Gmail**，查看我过去30天发送的所有电子邮件发件箱，分析该写作**技能**，并完美匹配我写作中使用的语气。你知道，**AI**以许多不同的方式用于写作。当然，有很多**AI**的拙劣之处，但当你能够向**AI**提供一系列大约100条消息时，它真的可以非常接近你的确切写作风格。这就是它在这里所做的。所以，退一步说，**连接器**非常重要，因为这不仅是那些将代表你工作的工具，对吗？我认为这可能是一些人会错过的地方，那就是，是的，我们可以使用**连接器**来起草**Gmail**邮件或在**Notion**中编写文档，但还有这种摄取路径，可以让你更好地使用这些**AI**工具。我以前从未见过这种用例，所以我想向大家指出，那就是让**AI**去阅读你的邮件，然后回来构建一个**技能**，我认为这非常重要。**技能**，记住，对于大家来说，它们只是这些容器化的指令集，可以随时调用。去构建一个以我的语气撰写电子邮件的**技能**。你知道，我认为作为一个正在开发日常操作系统的人，我称之为你的“**反待办事项列表**”，你列出那些你再也不想做的事情。比如，我再也不想自己起草电子邮件了。我再也不想因为日程冲突或会议一个接一个而迟到会议了。我只希望这些事情我再也不用担心。我认为作为一个进来思考如何将**Co-work**或类似的东西用于我的日常操作系统的人，这种“消除反待办事项列表”然后围绕所有这些构建**技能**的想法非常敏锐。我认为你所展示的是，你可以使用**连接器**加上**Co-work**的“大脑”来共同实现，不仅功能上实现，而且以一种对你个人来说高质量的方式实现。

<details>
<summary>Original English</summary>

**Claire Vo**: So this is going to start building an email skill for me. And it's going to do it by connecting to my Gmail, looking at my outbox of all the emails that I've sent in the last 30 days, analyzing that writing skill, and just perfectly matching the tone that I use in my writing. You know, AI is used for writing in a lot of different ways. And of course, there's a lot of AI slop, but when you can feed AI like a series of like a 100 messages, it could really get close to your exact writing style. And that's what this is doing here. So just to to kind of take a step back, connectors are really important because this is not only the the tools that are going to do work on your behalf, right? I think this is something that people might miss, which is yes, we can do connectors so you can draft emails to Gmail or write docs in notion, but there's also this ingest path that can make your use of these AI tools a lot better. And I haven't seen this use case before, so I want to call it out for people, which is have AI go read your emails and come back and build a skill, which I think is really important. And and skills, remember, for folks are just these like containerized little sets of instructions that can be called at any time. Go build a skill that writes emails in my tone. And you know, I think as somebody who's developing a daily operating system, I call this your like anti-to-do list is you come up with these list of things that you just like never want to do again. Like I never want to have to first draft my emails again. I never want to have to like show up to a meeting late because there's a conflict on my calendar or they've been set back to back. I just want these things I never have to worry about. And I think as somebody who's coming in and trying to think about how could I use co-work or something for my daily operating system, this idea of like burning down your anti-to-do list and then building skills on all those is is really sharp. And what I think you're showing is you can use connectors plus the brains of co-work to kind of come together and not only functionally achieve that, but achieve that in a way that's high quality for you personally.

</details>

**JJ Angler**: 是的。而且结果也非常好。

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah. And the results have been really good with it, too.

</details>

**Claire Vo**: 是的。你的意思是，你真的收到了听起来像你的邮件吗？好的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. You have I mean, are you really getting emails that like sound like sound like you? Okay.

</details>

**JJ Angler**: 没错。通常我会怎么做呢，我会进入我的指令，呃，我还没有做这一步，但我会说：“永远不要替我发送邮件。只将它们写成草稿供我审阅。”对吧？现在这是一个非常清晰的指令，意思是：“嘿，它实际上永远不会替我发送任何东西，因为我还不信任它。但我要求它发送的所有东西，它都会起草并准备好在我的发件箱或草稿箱中，这样我就可以批准并发送。”

<details>
<summary>Original English</summary>

**JJ Angler**: Exactly. And normally what I'll do is I'll go into my instructions here and uh I haven't done this step yet, but I'll say never send emails on my behalf. only write them as drafts for me to review. Right? And now this is a very clear uh instructions of like, hey, it's actually never going to send anything for me because I don't trust that yet. But everything that I ask it to send, it's going to write that draft and just prepare it in my outbox or my drafts so I can approve it and then send it as well.

</details>

**Claire Vo**: 顺便说一下，你对所有语音输入的事情都非常冷静。你的语音工具选择是什么？

<details>
<summary>Original English</summary>

**Claire Vo**: By the way, you're being very chill about all your um voice entry stuff. What What is your uh voice tool of choice?

</details>

**JJ Angler**: **Whisperflow**。

<details>
<summary>Original English</summary>

**JJ Angler**: Whisper flow.

</details>

**Claire Vo**: **Whisperflow**。

<details>
<summary>Original English</summary>

**Claire Vo**: Whisper flow.

</details>

**JJ Angler**: 它只是，它俘获了我的心。我是一个独白女孩，所以你知道，我们都选我们最喜欢的。

<details>
<summary>Original English</summary>

**JJ Angler**: It's just it's captured my heart. I'm a monologue girl, so you know, we all we all pick our favorites.

</details>

**Claire Vo**: 你知道吗？它都有效。它都有效。

<details>
<summary>Original English</summary>

**Claire Vo**: You know what? It all works. It all works.

</details>

**JJ Angler**: 它都有效。本集由**Cursor**赞助。如果你一直在看《我如何**AI**》，你已经知道了。**Cursor**是我最喜欢的**AI**编码方式。无论我是使用**计划模式**来构建一个雄心勃勃的功能，在我的编辑器中审查**AI**生成的**diffs**，还是启动**Cloud Agents**来多线程处理我们的路线图，我都会选择**Cursor**作为我最喜欢的多模型编码平台。甚至比我自己用**Cursor**构建更好的是，我喜欢与**bugbot**协作修复代码安全和质量的**PRs**，并且已经开始依赖**Cursor**的自动化**代理**来保持我们的代码库整洁。不只是我。最雄心勃勃的团队也喜欢**Cursor 2**，包括**Stripe**、**OpenAI**和**Figma**的工程师。准备好构建更多了吗？我们为《我如何**AI**》的听众提供50美元的**Cursor**积分。请访问chatpd.ai/howi**AI**领取你的积分。也就是说，通过访问chatpd.ai/howi**AI**，你可以获得50美元的**Cursor**积分。好的。所以，你已经开始了，我看到了一个弹出窗口。所以告诉我发生了什么。

<details>
<summary>Original English</summary>

**JJ Angler**: It all works. This episode is brought to you by Cursor. If you all have been watching How I AI, you already know this. Cursor is my favorite way to code with AI. Whether I'm using plan mode to build out an ambitious feature, reviewing AI generated diffs right in my editor or kicking off cloud agents to multi-thread our roadmap, I reach for cursor as my favorite multimodel coding platform. Even better than building myself and cursor, I love collaborating with bugbot to fix PRs for code security and quality and have begun relying on cursor's automated agents to keep our codebase clean. It's not just me. The most ambitious teams love Cursor 2, including engineers at Stripe, OpenAI, and Figma. Ready to build more? We're giving $50 in cursor credit to How I AI listeners. Claim your credits at chatpd.ai/howi AI. That's $50 in cursor credits by going to chatpd.ai/howi AI. Okay. So, you've started I I see a a popup here. So tell me what's what's going on.

</details>

### AI代理的编排与权限管理

**Claire Vo**: 所以这就是我喜欢拥有这个**项目**系统的一点。你现在正在进行编排。即使你可能不是一个开发者，你现在也是一个**AI**编排者。你可以同时运行许多**代理**，并拥有这种顶层视图，能够快速查看哪个**代理**需要你的关注，然后给予它们这些权限或重新介入。所以现在我们确实看到，这个**代理**需要我们的关注。我们可以进去查看，它实际上只是在问我们是否允许它这样做。好的。所以即使不进去，我也可以直接允许它。我可以进入那个**连接器**并更改这些权限，只需说“总是允许”。所以我不需要那样做。但在这种情况下，它被设置为“请求我的许可”。好的，

<details>
<summary>Original English</summary>

**Claire Vo**: So this is one of the things I love about having this project system. You're orchestrating now. Even though you might not be a developer, you're now an AI orchestrator. You can run many agents at once and have this top level view to be able to just quickly see which agent needs your attention and just give them those permissions or to pop back in. So right now we do see that hey this uh agent needs our attention. We can go in and review that and it's ask actually just asking us if we want to allow this. Okay. So without even having to go in there, I can just allow that. I could go into that connector and change those privileges just to say always allow. So I don't have to do that. But in this case, that was set to a ask for my permission. Okay,

</details>

**JJ Angler**: 这是我与**Co-work**相处的一个问题，那就是它本来是一个非常可爱的非技术性**体验**，直到它突然在你面前抛出一个**bash**命令，然后问你：“嘿，你想允许这个吗？”是的。我只是为了所有那些非技术人员，他们可能只是说：“嘿，等等。我刚才看到了一大行代码，上面写着‘你同意运行这个吗？’”

<details>
<summary>Original English</summary>

**JJ Angler**: this is one of my one of my problems with with co-work, which is this is just like such a lovely non-technical experience until it shoves like a bash command in your face and is like, "Hey, do you want to allow this or not?" Yeah. And I just for all all the nontechnical folks out there that just were like, "Hey, hold on. I just saw a big line of code that said, "Are you okay with running this?"

</details>

**Claire Vo**: 你也可以复制粘贴那个，然后问另一个**Claude**：“这是什么意思？”你知道，我认为这些混合工具的有趣之处在于，它们面向用户，面向非技术人员，但背后却有**Claude Code**作为后端，这是一种很好的方式，让你一点一点地进入**Claude Code**的**体验**。但再说一遍，不要害怕。我认为你可以对其中一些可能看起来很技术性的警报相当不惧怕，因为你总是可以去问：“这是什么意思？我应该这样做吗？”我还会说，我认为**Co-work**尤其被调整得非常用户友好。比如，在**Co-work**上还没有危险地跳过权限的功能。所以**Claude**要求你做的任何事情可能都在安全的范围内。嗯，尽管每次你点击那个批准按钮时阅读都很重要。

<details>
<summary>Original English</summary>

**Claire Vo**: You can also like copy and paste that and ask a different cla what does this mean? You know, and I think what's kind of interesting about these hybrid tools that are kind of userfacing non-technical folks, but have this like claude code back uh back end is it's a nice way to actually step your way into the cloud code experience bit by bit. But again, don't be afraid. I think you can be pretty unafraid of some of these alerts that may look technical because you can always go ask what does this mean? Um should I do this? And I will also say that I think co-work in particular has been tuned to be pretty user friendly. Like there isn't a dangerously skip permissions on co-work quite yet. And so anything that Claude's asking you to do is probably in the realm of safe. Um although it's important to read whenever you hit that approve button.

</details>

**JJ Angler**: 我之前在犹豫要不要提这个，但人们问我**Co-work**与**OpenClaw**的区别。我知道你非常喜欢**OpenClaw**，我也很喜欢。但我对这个的看法是，**OpenClaw**适用于商业工作，你可以信任它处理更重要的连接。而**OpenClaw**非常棒，但你可能不太信任它处理你的业务工具，尤其是在最初。它是一个很棒的个人助理。它是一个很棒的**自主代理**，可以做很多事情。所以我两者都用，但**Co-work**就像我的日常业务驱动器，而**OpenClaw**更像我的个人助理。它们能帮助我处理很多事情，但对我的许多账户的访问权限有限。是的，我完全沉浸在**Claude**的世界里。嗯，但再说一遍，我的意思是，我无法度过一天而没有人给我发短信说**Co-work**正在替我完成工作。我很高兴。

<details>
<summary>Original English</summary>

**JJ Angler**: I was on the fence about calling this out, but people ask me co-workers versus open claw. And I know you're really big in open claw and I and I am too. I really really love it. But the way that I think about this is OpenClaw is for work in business where you can trust it with your more significant connections. And OpenClaw is incredible, but you maybe don't trust as much with your business tooling, especially in the first. It's a great personal assistant. It's a great autonomous agent and can do so much. And so I use both together, but co-work is like my daily business driver and OpenClaw is more like my personal assistant. Can they like just help me in a lot of things with limited access to a lot of its own accounts. Yeah, I'm I'm full claw full press claw world. Um, but again, I mean, again, I cannot go throughout through my day without somebody texting me like co-workers doing my job for me. I'm h happy as can be.

</details>

**Claire Vo**: 嗯，你展示了一个我认为普遍适用于人们的例子，那就是撰写我的电子邮件。还有什么？我的意思是，你认为像**Co-work**这样的工具可以为你做什么样的工作流，你认为它们属于你的操作系统？

<details>
<summary>Original English</summary>

**Claire Vo**: Um, so you shown a shown an example that I think is generally applicable to people, which is write write my emails. What else? I mean just kind of top hits of workflows that you think something like co-work could do for you that you think belongs in in your operating system.

</details>

### AI作为思考伙伴与多代理评审

**JJ Angler**: 是的，当然。我只是看这个**代理**，它分析了46封电子邮件，呃，它进去为我创建了一个电子邮件风格指南，呃，还有一个声音档案，并将其保存到我的记忆中。所以我要回到这里。我接下来真正喜欢使用的是**Claude**作为思考伙伴。思考伙伴可以有多种形式和大小。它可以是：我如何回复这条**Slack**消息？我如何回复我的同事并给他们好的反馈？我如何思考我的职业生涯以及接下来我应该做什么？现在你可以为其中每一个都有一个**技能**或一个思考伙伴，或者你可以有一个通用的。现在我们只是创建一个像思考伙伴/导师一样的东西，你可以触发它，然后它会帮助你思考重要的决定，它会以你希望被支持的方式与你交谈。所以我要在这里启动另一个**代理**，我要说：“帮我创建一个新的**技能**，它将成为我们的思考伙伴。”这个思考伙伴**技能**被调用时，将允许我思考如何回应某事，如何做出决定，如何在工作中以良好但有效和有益的方式批评同事，如何宏观地思考我的职业生涯，并且通常会帮助我思考手头任务中更大的事项。嗯，你可以通过说“你知道，帮我思考这个问题”或者“你知道，导航我的思考伙伴”或任何类似的话来调用它。

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah, for sure. So I just looking at this agent here, it analyzed 46 emails uh and it went in and created a email style guide for me uh and a voice profile and saved it to my memory as well. So I'm going to go back over here. The next thing that I really like to use is Claude as a thinking partner. Thinking partner can come in many shapes and sizes. It could be like how do I respond to this Slack message? How do I respond to my colleague and give them good feedback? How do I think about my career and what I should do next? Now you can have a skill or a thinking partner for each one of those or you can have a generic one. Right now we are going to just create like a thinking partner like a/mentor that you can just trigger and just like help you think through important decisions and it will kind of like talk back to you in a way that you want to be supported. And so I'm going to launch another agent here and I'm going to say, "Help me create a new uh skill that is going to be our thinking partner." This thinking partner skill when invoked is going to allow me to think about how to respond to something, how to make a decision, how to critique in a colleague that I'm working with in a good but effective and helpful way, how to think about my career at large, and just generally going to help me think through the bigger items of whatever task is at hand. Um, and you can invoke this by saying, you know, help me think through this or, you know, navigate my thinking partner or anything like that.

</details>

**JJ Angler**: 然后我最后要补充一点，请在不清楚时问我任何问题。我喜欢在不清楚时问任何问题，呃，因为通常很多时候确实如此，这只会迫使它真正获得它需要的更多上下文，以确保它正在为你构建一些特定的东西。现在，我们已经谈了很多关于**技能**的事情，我们实际上甚至已经开始创建**技能**了。**技能**非常强大。你可以把它想象成一个非常详细的**提示**，可以以许多不同的方式重复使用。所以，与其说“嘿，去给我创建这个新闻通讯”，然后告诉它你想要新闻通讯的所有内容，你可以一次性完成，并为新闻通讯中的所有内容制定一个非常清晰的模式。然后你就可以说“嘿，写新闻通讯”，它就会调用那个**技能**，并每次自动使用那些指令。

<details>
<summary>Original English</summary>

**JJ Angler**: And then one last thing I do want to add is please ask me any questions if you're unclear. I love the asking any questions if you're unclear uh because generally a lot of times it is and it just forces it to like really get the more more context that it needs to make sure that it's building something specific to you. Right now, we've talked about skills a lot and we've actually even started creating skills. Skills are really powerful. You could think about it as like a very detailed prompt that is reusable in many different ways. And so rather than saying, "Hey, go off and create this newsletter for me." And then tell it everything that you want your newsletter, you can do that once and have a very clear pattern for like everything in your newsletter. And then you can just say, "Hey, write the newsletter." and it will invoke that skill and automatically use that instructions every single time.

</details>

**Claire Vo**: 是的。对于大家，呃，我实际上在我的核心聊天**PRD**仓库中确实有这个**技能**。我通过**Claude Code**使用它。所以每个星期一我只需要输入一个`/newsletter`，它就会去查看我的更改日志。它会撰写新闻通讯。它会用我的声音撰写。它会为新闻通讯平台格式化。它会通过**API**推送。然后我只需要进去做一些编辑，然后继续我的生活。所以这是一个非常棒的用例。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. And for folks uh I do actually have literally that skill in my my core chat PRD repo. I use it through cloud code. So I just do a slashnewsletter every Monday and it goes and looks through my change log. It writes the newsletter. It does it in my voice. It formats it for the newsletter platform. It pushes it via API and then I just go in and do a couple edits and and move on with my life. So that's that's a really great great use case.

</details>

**JJ Angler**: 让我再来一个，我们继续。这已经在构建中了。

<details>
<summary>Original English</summary>

**JJ Angler**: Let me have one more that we get going here. This is already building.

</details>

**Claire Vo**: “嘿，**Claude**，我希望你构建另一个**技能**，这将是一个评审**代理**。对于这个**技能**，你将启动一系列**子代理**，每个**子代理**都有自己的角色。这可以根据任务的不同而不同。但一个例子是，如果我们要发布一个新闻通讯，我们希望有代表我们**ICP**的**子代理**。对我来说，可能是**AI**构建者、**AI**高管和对**AI**感兴趣的人。这个**技能**的目标是允许**子代理**能够审查你的工作并给你诚实的反馈，并从三个不同的角度看到你下一步迭代需要关注的重点，以提高你的工作质量。如果你有任何问题，请告诉我。”

<details>
<summary>Original English</summary>

**Claire Vo**: "Hey Claude, I want you to build another uh skill and this is going to be a review agent. For this skill, you're going to launch a series of sub agents that have each their own persona. And this can differ per the task. But an example is if we're launching a newsletter, we want to have sub agents that represent our ICP. Maybe for me it would be AI builders, AI executives and AI interested people. And the goal of this skill is to allow sub agents to be able to review your work and give you honest feedback and to see from three different perspectives where you need to focus at your next iteration to improve the quality of your work. Let me know if you have any questions."

</details>

**Claire Vo**: 所以，这是我真正喜欢的另一个**技能**，我在我的很多工作中都使用它。比如我在新闻通讯中使用它。我在播客中使用它。我在社交媒体写作中使用它。它是一种**子咨询技能**，是一种通用的模式。它让你能够，**Claude**，你知道，它在这个上下文环境中与你一起工作，并生成一个输出。当你使用**子代理**时，它会启动三个不同的**代理**，每个**代理**都可以有自己的角色。所以，比如：“嘿，**代理**一，你是一个**AI**构建者。**代理**二，你是一个非常担心安全的人。**代理**三，也许你只是一个担心**AI**使用的妈妈，或者一个担心**AI**使用的爸爸，或者只是一个随意举例，但我的观点是，你可以定义三个独立的**角色**，带着一个全新的上下文窗口，这意味着全新的视角去客观地审视你的工作，然后将这些反馈带回来，它帮助你弄清楚，在发送之前，这将如何被接收，对吧？如果你在其中包含你的**ICP****角色**，它也会帮助很多。我发现这种框架在创建你的**技能**方面取得了非常好的效果。

<details>
<summary>Original English</summary>

**Claire Vo**: So, this is another skill that I really love and I use like across so much of my work. It's like I use it in my newsletter. I use it in my podcast. I use it in my social media writing. It's a subadvisory skill is the general pattern. And what it allows you to do is claude, you know, it's working with you in this context and it generates an output. When you use sub agents, it will spin up three different agents and each of those agents can have their own persona. So like, hey, agent one, you are an AI builder. Agent two, you are someone that is so worried about security. and agent three, maybe you're just uh a mom worried about AI usage or a dad worried about AI usage or just as a arbitrary example, but my point of this is you can define three individual personas with like a fresh context window, meaning like fresh perspective to go and look at your work in a objective way that then brings back that feedback and it helps you kind of figure out like how is this going to be received before I even send it, right? And if you include your ICP personas in there, it also helps with this a lot too. And I found really good results with this kind of framework for creating your skills.

</details>

**JJ Angler**: 我认为有一件事非常重要，当你想到这在你的工作中何时适用时，我们中的许多人在过去五六年里都转向了远程优先工作，从队友那里获得协作反馈实际上成本很高。你必须召开会议。每个人都很忙。同步工作非常困难，因此能够从**AI**那里获得预反馈，**AI**会给你一个全面的工作视图，这让你能够带着更高质量的预先思考过的工作去参加那些非常昂贵的会议。嗯，而且我不知道，这有点悲伤，我所有的朋友都是**代理**，这意味着独自工作真的很难，作为一个独立创始人，我一个人很难确保我所有的想法都很棒。所以我还没有听说有人给出这种关于非常具体使用**子代理**的建议，正如你所说，这就像想象一下，有一个聊天正在与其他聊天对话，这些聊天有一些但不是全部的上下文和它们自己的观点。也许这就是你如何看待那些不那么技术性的**子代理**。

<details>
<summary>Original English</summary>

**JJ Angler**: One thing the one thing I think is really important to call out as you know people think about where this is applicable in their work is so many of us in the last five six years have moved to remote first working where getting collaborative feedback from your teammates is actually highly expensive. You have to call a meeting. Everybody's busy. synchronous work is quite hard and so being able to spin up prefeedback feedback from AI which will give you sort of a roundt view of your work allows you to come to those very expensive meetings honestly with much higher quality pre-thoughtout work um and and also I don't know this is like very sad all my friends are agents which is like it's really hard to work solo like I'm a solo founder it is like very hard to just me by myself ensure that all my ideas are great. And so I haven't heard of anybody giving this advice of like very specific use of sub agents which as you said is just imagine like there's a chat that's chatting with other chats that have some but not all the context and their own point of view. Maybe that's how you think about sub agents for folks that aren't super technical

</details>

**JJ Angler**: 然后将这些聚合起来，给你一些反馈。我认为这是一个非常有用的技巧，每个人都应该在工作中使用。所以如果你是一个产品经理，建立它，然后把你的老板、你的工程伙伴和你的客户放进去，然后说：“每次**PRD**评审都从这三个角度给我反馈。”如果你在市场营销领域，再次强调，就像你的**ICP**，给出反馈。我认为这种多视角反馈机制在很多地方都非常有用。

<details>
<summary>Original English</summary>

**JJ Angler**: and then aggregate that back up and give you some feedback. I think is a a really useful just hack that everybody should have for their work. So if you're a product manager, build it and like put your boss in there, your engineering partner, and your customer and say every PRD review from the these three points of view and give me feedback. If you're in marketing again, like your ICP, give feedback. I think there's just a lot of places where this sort of multi- view feedback mechanism is is super useful.

</details>

**Claire Vo**: 100%。我们可以更进一步，说：“嘿，创建这个**子咨询技能**，并且每个，也许三个**代理**，比如一个**代理**就是你的老板，你派一个**代理**去研究你的老板是谁，他们的角色，他们的视角，并真正定义你合作的人，让他们模拟出他们可能会给你的反馈，甚至在你去找他们之前。”这方面是无限的。你只需告诉**Claude**做什么，它就会为你完成。所以你现在有很多工具可以使用，呃，可以自动化很多事情。比如，其中一个例子是，我也运营一个新闻通讯。所以我们新闻通讯的**技能**几乎是一个10步的**技能**，比如在我们开始撰写这个新闻通讯之前，我希望你采访我，这个新闻通讯应该写什么。然后一旦你采访我，我还希望你运行一个**子代理**去做互联网研究，了解这周**AI**世界有什么好的东西。我们应该谈论什么？一旦我的采访完成，一旦研究完成，我们现在就有了关于内容的想法。然后它将开始通过一系列**子技能**来工作，比如我们的主题行应该是什么，以及什么才是真正好的主题行，它会为此设置一组指令。然后我的新闻通讯有非常特定的主体部分，每个主体部分都有一个特定的**技能**，说明什么才是真正好的**AI**原生部分，或者什么才是真正好的**AI**未来部分，对吧？在所有这些步骤的最后，它有一个**技能**的评估部分，它会通过一系列的检查清单，并启动那个**子咨询委员会**。所以它会经历所有这些。我只需要说“超思维**技能**”，然后它就会开始这一系列的工作，并帮助我。到最后，它已经为我做了很多工作，我只需要回答一些问题。然后它输出一个我认为非常好的草稿。我还会把新闻通讯过去的表现结果反馈给它，比如“嘿，我们一起写的这个。表现还不错”，我把结果给它，它有一系列的反馈和评审，了解这些东西的表现如何，看看什么有效，什么无效，这是一个非常重要的步骤，因为如果你不告诉**AI**对你来说什么是成功，**AI**就不知道对你来说什么是成功。所以我总是喜欢包含好的例子和坏的例子。这对于写作来说非常清楚。如果你正在写作，并且你非常喜欢某个东西，就把它包含在一个好的例子中。但如果它返回的东西你不喜欢，就把它放在一个坏的例子中，比如“嘿，不要再那样做了。那看起来不好。”这样，你就在向**Claude**展示什么对你来说是好的，什么是不好的，因为这是主观的，对每个人都不同。**Claude**需要知道这一点。好的。所以，我们这里有多**代理**的视角，我们可以看到我们已经做了几件事。这个，思考伙伴**技能**，需要我的审阅。所以，我将进去，我将审阅它。嗯，它正在寻找一些信息，看起来它已经打开了。所以他们有这个新的界面，允许你审阅你的思考**技能**或你创建的任何**技能**，并实时测试它，看看它会如何返回并进行评估。对吧？所以如果你想使用那个，这非常有帮助。但我想做的是，我想回到我的**项目**这里，我想和你一起创建一个称为**计划任务**的东西。**计划任务**允许你创建按频率运行的东西。所以它可以每小时、每天、每周、工作日或任何时间运行。这个**计划任务**将是一个早晨汇报。我希望你每天早上查看我的电子邮件、我的**Slack**和我的日历，并检查它们，帮助我组织一天的行动计划。这样，当我进入办公室时，我就知道需要我关注的任何消息。你可以在我进入办公室之前，通过查看我的日历和活动来为我的一天做准备，如果我需要任何会议准备，帮助我完成。但总的来说，输出将是像一天计划一样，帮助我每天都以最佳状态开始。

<details>
<summary>Original English</summary>

**Claire Vo**: 100%. We could take this a step further and say, "Hey, create this sub-advisory skill and each maybe three of the agents, like one agent is literally your boss that you send an agent to go research who your boss is, their role, their perspective, and like really define like the people that you work with and have like them simulate the feedback that they might give you before you even go to them." Like the sky's is the limit here. And you just got to tell Claude what to do and it's going to go do it for you. So there's a lot of tools that you have at your disposal now uh to, you know, automate a lot of this. Like one example with this is I I also run a newsletter. And so the skill that we have for the newsletter is a almost like a 10-step skill of like before we even start writing this newsletter, I want you to interview me what this newsletter should be written about. Then once you're interviewing me, I also want want you to run a sub agent to do internet research on what is good in the AI world this week. What should we talk about in this? And once my interview is complete and once the research is complete, we now have an idea of like the content that we can do. And then it's going to start working through a series of subsklls which are like what should our subject line be and what are really good subject lines and it's going to have one set of instructions for that. And then my newsletter has like very specific body segments and each body segments has a specific skill within it saying like here's what makes a really good AI native section or what makes a really good uh AI future section, right? And at the end of all those steps, it has an evaluation part of the skill where it's going to go through a series of checklist lists and also launch that subadvisory board. And so it's going to go through all of this. And all I need to do is say ultra think skill and then it's going to start this series that it works through and just helps me. And by the end of it, it's done so much work for me and I've just had to answer some questions. And then it's outputed a draft that I think is really good. And I also feed it my past results of my newsletter of like hey we've written this together. This performed okay and I give it the results and it has a series of feedback and like you know review of like how these things are performing to see what's working and what's not which is a very important step because like if you don't tell AI what success is to you AI doesn't know what success is for you. So I always love including good examples and bad examples. This is very clear for like writing. If you're writing and you really like something, include it in a good example. But if it comes back with something that you don't like, put it in a bad example of like, "Hey, don't do that again. That doesn't look good." And this way, you're showing Claude what is good for you and what is bad for you, cuz that's subjective and different for everyone. And Claude needs to know it. All right. So, we have this multi-agent perspective here, and we can see that we've done a couple of things. This one, the thinking partner skill, needs my review. So, I'm going to go in there, and I'm just going to review it. And um it's looking for some information here and it looks like it had opened up. So they have this new interface here which allows you to review your thinking skill or whatever skill you created and see like and like test it in real time to see how it would come back and evaluate it like that. Right? So that's very helpful if you want to use that. But what I want to do is I want to go back to my project here and I want to create something called a scheduled task with you. A scheduled task allows you to create something that runs on a frequency. So it could run every hour, day, weekday, weekly, whatever. And this scheduled task is going to be a morning debrief. I want you every single morning to look at my email, my Slack, and my calendar and check it to help organize a plan of action for the day. So that way when I get into the office, I am aware of any kind of messages that need my attention. And you can start preparing me for my day by looking through my calendar and looking through my events and if I need any kind of meeting prep, helping me do that. But generally, the output is going to be like a plan for the day, helping me get started on the best foot every single day.

</details>

**Claire Vo**: 所以，这将是那个**提示**。我将每天运行它。我希望它在早上7:30运行。我可以选择我希望用什么模型来运行它，或者这些输出应该去哪里。嗯，在这种情况下，它将是，嗯，你知道，日常操作。那会很好。嗯，我只是能够保存它。

<details>
<summary>Original English</summary>

**Claire Vo**: So, that's going to be the prompt. And I'm going to run that daily. And I want it to run at like 7:30 a.m. And I could choose what model I want this to run with or where these outputs should go. Um, in this sense, it's going to be um, you know, the daily operations. That's going to be good. Um, and I'm going to just be able to save that.

</details>

**JJ Angler**: 它需要一个名字。

<details>
<summary>Original English</summary>

**JJ Angler**: It needs a name.

</details>

**Claire Vo**: 啊，原来如此。谢谢。我当时在想，那是什么？早晨汇报。我想提醒大家，我们已经看到了几个这样的早晨汇报例子，比如在**How I AI**上，我们看到**Hillary**向我们展示了她如何使用**Obsidian**连接到她的**Claude Code**，再连接到她的日历。她写道“计划我的一天”。我们已经看到了几个这样的定期任务，比如在**ChatGPT**中，我们看到一些需要了解的新闻。我认为我想提醒大家的是，尤其是那些再次对使用**AI**除了在**ChatGPT**中提问之外还很陌生的人，我知道你们中的许多人确实如此，那就是我用**ChatGPT**或**Claude**问了一个一次性问题，获取了一些信息，你知道，比如给我孙子写一首歌，或者回答一个关于我医疗健康的问题，或者给我**HOA**写一份文件，无论什么。我们，你知道，人们已经使用了这种用例，但我认为你在这里展示的是以前人们无法接触到的东西，那就是你实际上可以为自己构建一个由小型软件驱动的系统，让你的日子过得更轻松。它可以为你写邮件。它可以在每天早上给你发送一条消息，告诉你你的日程安排是怎样的。假设你甚至没有一个忙碌的日程。就像我在想，你知道，我爸爸退休了。

<details>
<summary>Original English</summary>

**Claire Vo**: Ah, there it is. Thank you. I was like, what is it? Morning debrief. I want to call out for folks, we've seen a couple of these like morning debrief uh examples on how ai we've seen um Hillary has shown us she uses Obsidian hooked up to her claude code hooked up to her calendar. She writes plan my day. We've seen a couple of these scheduled sort of like news I need to know uh tasks in chat GBT. I think what I want to call out for folks, especially those who are again new to using AI beyond asking a question in chat GPT, which I know honestly you many of of you are, which is I've used chat GPT or Claude to ask a one-off question, get some info, you know, like write a song for my, you know, grandchild or answer a question about my medical health or write a document to my HOA, whatever. We, you know, people have used that use case, but what I think you're showing here is something that wasn't accessible to folks, which is you can actually build a little software powered system for yourself to make your day go easier. And it could be writing emails for you. It could be, you know, every morning send you a message about what your schedule looks like. Let's say you're not even you don't even have a busy schedule. Like I'm thinking about, you know, my dad's retired

</details>

**JJ Angler**: 就像你可能感兴趣的当日新闻。我每天都会，嗯，你知道，在技术领域，我们称之为**cron**，当你在**OpenClaw**那边时。但我每天都有一个时间表，早上我会被推送一些**AI**领域有趣的东西，晚上我会被推送一篇让我感觉良好的文章，你知道吗？哦，所以你只需想想，如果互联网能主动找到我。

<details>
<summary>Original English</summary>

**JJ Angler**: like news that you're you might be interested in for the day. I have a a daily um you know, in the in the technical world, we call it a cron and when you're on the when you're on the open claw side, but I have a daily schedule and in the morning I get pushed something kind of fun and interesting in the AI space and at night I get pushed an article that will like make me feel good, you know? Oh, and so you just think about if the internet could come to me

</details>

**Claire Vo**: 而不是我必须去互联网，我希望互联网能带来什么给我？我想这就是你关注早晨汇报的重点。所以它可以是非常注重生产力的功能。它可以是，你知道，去倒满你的水杯，不要空腹喝咖啡，出去散步并向太阳问好。它可以是任何这些事情，但它可以被**计划**并推送到你。

<details>
<summary>Original English</summary>

**Claire Vo**: as opposed to me having to go to the internet, what would I want the internet to come to come to me with? And that's what I think you focus your your morning debrief on. So it could be like highly functional from a productivity perspective. It could be, you know, go fill your water glass, don't drink coffee on an empty stomach, go for a walk and say hello to the sun. It can be any of those things, but it can be scheduled and it can be pushed to you.

</details>

### AI与个人数据：信任与赋能

**JJ Angler**: 对。现在，既然我们已经在**项目**中**计划**了它，它就拥有了你**项目**的所有上下文。这意味着**技能**、你的**连接器**和所有东西。这就是为什么在**项目**中**计划**它，比如构建那个上下文，会随着时间的推移变得非常强大，你会得到更好的结果。所以这可以是一个**项目**汇报，或者如果你是一个项目经理，每天它都会查看这个**项目**，并帮助为你的所有团队成员撰写行动计划，并作为**Slack**消息发送。所以，一旦他们进入那个**项目**，当天的计划就会非常具体地针对每个**项目**完成，对吧？所以有很多方法可以使用它。这还连接到我所有的工具。所以它会阅读我的电子邮件、我的日历和我的**Slack**，并根据所有这些上下文安全地准备一份每日计划。对我来说，这就是突破点，就是能够阅读所有这些工具，并使用**AI**来帮助我更好地完成工作。

<details>
<summary>Original English</summary>

**JJ Angler**: Right. And right now since we've scheduled this within a project, it has all the context of your project as well. Meaning the skills, your connectors and everything. And that's why having it scheduled within a project like building up that context, it gets very powerful over time and you're going to get better results. So this could be a project debrief or like if you're a project manager, every single day it's going to look at this project and just help write a plan of action for all of your team members to and send as a Slack message. So like once they enter that project plan for the day is done very specific to each project, right? So there's just so many ways you can use it. And this also connects to all of my tools. So it's going to read my email and my calendar and my Slack and just prepare a daily plan with all that context in mind in a safe way. That's like the unlock for me is like just being able to read all these tools and use an AI on top of that to like help me do my job better.

</details>

**Claire Vo**: 是的。我只想提醒大家，因为我认为这对于**Claude Co-work**的用户，那些可能刚开始以这种特定方式使用**AI**的人来说，会听到这样的问题：我希望**AI**阅读我的邮件吗？我希望**AI**阅读我的日历吗？我给每个人的建议是，再次，只需将其视为渐进式信任，也就是说，起初你可能只希望它为你起草邮件。然后你可能希望它阅读你的邮件。然后你可能希望它阅读你的日历或**Slack**或任何这些东西。然后你可能希望有一个像**影子JJ**一样的**代理**，它完全独立于你操作，而你在巴哈马群岛闲逛，你知道，**代理JJ**实际上在替你完成你的工作。只需将此视为一个信任谱系。你会达到，你知道，你会达到**Claire Vo**的水平，在某个时候你就像在**tokens**中漂浮，批准**API**访问。但我确实认为，你知道，人们对此感到紧张。这是信息与生产力的权衡。我们都站在一边或另一边，也就是说，你给**AI**一点点信息，它就能帮助你提高生产力。你必须弄清楚你在这个谱系中，在你的业务中，在你的个人生活中，感觉舒适的程度。我认为你和我都只是在展示，如果你达到更远的这一端，你将从中获得巨大的价值，这是你以前无法获得的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. And I'll just call out for folks because again I think this is sort of like a claude co-work folks that are maybe newer to using AI in this particular way and the things that you're going to hear is like do I want AI reading my email? Do I want AI reading you know my calendar? And the recommendation that I give to everybody is again just think about this as progressive trust which is at first you just may want it to draft emails for you. Then you may want it to read your emails. Then you may want it to read your calendar or your Slack or any of those things. Then you may want to have like a shadow JJ that actually just operates completely independent of you and you're in the Bahamas hanging out and you know, agent JJ is actually doing your job for you. Just think about this on like a trust spectrum. you'll get, you know, you'll get to clarvo level at some point where you're just like floating floating through the tokens um approving API access. But I I do think, you know, people get nervous about this. It's it's a trade of of of information for productivity. And it's like we're all on one side or the other, which is you give the AI a little bit of information, it can help you be very very productive. And you've got to figure out where you feel comfortable on that spectrum in your business, in your personal life. I think you and I are just showing if you get to this far further edge, you're going to get a lot of value out of it that that you couldn't before.

</details>

**JJ Angler**: 是的。尤其是有了这些**技能**，我知道每个人都说**技能****技能****技能**，但我拥有处理所有事情的**技能**。我有一个在**Twitter**上写作的**技能**。我有一个在**LinkedIn**上写作的**技能**。我有一个制作我的**YouTube**、我的播客、我的新闻通讯的**技能**。就像拥有那个内置的基础设施一样，无论何时我需要做任何事情，它都知道我喜欢的工作方式。这对我来说是一个非常大的突破。我一直在做的另一件事是，我现在通过我的公司**10X**与**Anthropic**合作。我们正在做的一件事是为**Anthropic**举办一个研讨会。所以我把**Anthropic**给我们的所有文档，比如工作计划指南和研讨会指南等等，都放了进去。所以无论何时我问这个**项目**一个问题，它都考虑到所有这些上下文。它确切地知道**Anthropic**想做什么。它想要所有那些东西。它非常清晰和容易。所以每当我开始一个新**项目**时，第一步是，好吧，我要创建一个文件夹。我要把所有我的文件都放进那个文件夹。我将在**Claude Co-work**中打开那个文件夹。为它创建一个**项目**。现在那个**项目**可以访问所有这些信息，并且非常具体地帮助我更好地完成工作，考虑到那个上下文。这对我来说是一个很大的突破。而且这是一个非常简单的方式，可以开始用**AI**做更多事情，它会教你很多**技能**，你可以将这些**技能**转移到实际用**AI**构建东西上，那就是**Claude Code**，它也非常棒。而且**Co-work**的改进速度非常非常惊人。所以它只是其中之一，如果你准备好用**AI**做更多事情，希望你已经准备好了，因为我们正在朝着那个方向前进，那些能够做到的人正在迅速崛起。所以希望你也是。如果你是，**Co-work**是你绽放一点，施展拳脚，看看你能用**AI**做些什么的好下一步。

<details>
<summary>Original English</summary>

**JJ Angler**: Yeah. And especially with the skills, like I know everyone says skill skills skills, but like I have a skill for everything. I have a skill for writing on Twitter. I have a skill for writing uh in LinkedIn. I have a skill for doing my YouTube uh my podcast, my newsletter. like just having that builtin infrastructure that whenever I need to do any of that stuff, it knows exactly the way I like to work. That is a very big unlock for me. Another thing that I've been doing is I'm working with Anthropic through my company 10X right now. And one of the things that we're doing is we're hosting a workshop for Anthropic. And so I threw in all of the documents that Anthropic gave us of like work program guidelines and workshop guidelines and everything. And so anytime I ask a question about this project, it has all of that context in mind. It knows exactly what Anthropic wants to do. It wants all that kind of stuff. And it's very clear and easy. And so whenever I start a new project, the first step is like, all right, I'm going to create a folder. I'm going to put all my files in that folder. I'm going to open up that folder in Claude called work. Create a project for it. And now that project can access all that information and be very specific about helping me do better with that context in mind. And it's just a big unlock for me. And it's it's a very easy way to get started doing more with AI that will teach you a lot of skills that you can transfer over to actually building stuff with AI, which is cloud code, which is also incredible. And the the rate at which co-work is improving is really really awesome. And so it's just one of those things where it's like if you're ready to do more with AI, which hopefully you are because that's where we're going and those that can are rising up really quickly. So hopefully you are. And if you are co-work is a really good next step for you to uh blossom a little bit, spread your wings and just see what you can do with AI doing stuff with you.

</details>

**Claire Vo**: 嗯，我再次想回到那些说：“好吧，我们有两个像播客主持人一样的人，他们正在告诉我们他们如何使用**Co-work**来计划他们的**YouTube**发布。”我想说的是，这些**项目**不一定与工作相关，对吗？它们不一定。

<details>
<summary>Original English</summary>

**Claire Vo**: Well, and I again I want to go back to folks that are like, "Okay, we got these two like podcast hosts telling us how they planning their like YouTube releases using co-work." I want to say that again these projects do not have to be workrelated, right? They don't.

</details>

**JJ Angler**: 你可以创建一个关于家庭维护的**项目**。让我告诉你一个你可以做的**项目**。家庭维护。

<details>
<summary>Original English</summary>

**JJ Angler**: You can make a project that's house maintenance. Let me tell you a project that you make. House maintenance.

</details>

**Claire Vo**: 每隔几个月你需要更换空气过滤器。每个，你知道，就像，你知道，在冬天，你想要确保计划**XYZ**。你有一个大型的改造**项目**正在进行。把它放在**Claude Co-work****项目**中。

<details>
<summary>Original English</summary>

**Claire Vo**: Every couple months you need to change your air filters. Every, you know, like, you know, in the winter, you want to make sure to plan for XYZ. You've got a big kind of like remodel project going on. Put that in a clawed co-work project.

</details>

**Claire Vo**: 生成你需要生成的东西。把它放在一个工作区中。嗯，所以你可以对**项目**这个概念进行非常有创意的思考。我看到其他人正在招聘，他们说：“这是我的招聘工程师**项目**，它包含了他们需要做的所有工作，包括职位描述、寻源、入职、面试，所有这些都在一个**项目**中。”所以再次强调，它不一定是个人生产力。它不一定是与**Anthropic**的研讨会。它不一定是你的**YouTube**。我很高兴你展示了这个屏幕，**Co-work**有一个关于你可以用它做什么的创意列表。我认为，干得好，**Co-work**产品团队，因为人们，这正是这个播客的重点，人们听到**AI**很棒，他们想使用它，他们准备好了，然后他们坐在一个聊天框前，他们会想我该怎么办？我能做什么？

<details>
<summary>Original English</summary>

**Claire Vo**: Generate the things that you need to generate. Keep it in keep it in a workspace. Um, and so you can be really creative about what the idea of a project means. I've seen other people who are doing hiring and they're saying, "Here's my recruiting engineers project and it's all the work they need to do around job descriptions, sourcing, onboarding, interviews, all in one project. So again, it doesn't have to be personal productivity. It doesn't have to be workshops with Enthropic. It doesn't have to be your YouTube." And I love I'm glad you're showing this screen, which is co-work has this list of ideas of kind of things you can do with it. I think like good job um co-work product team because again people just this is part of the point of this podcast which is people hear that AI is awesome they want to use it they're ready to go and then they sit in front of a chat box and they're like what do I do with it like what can I possibly do

</details>

**JJ Angler**: 会不会窃取我所有的数据？

<details>
<summary>Original English</summary>

**JJ Angler**: and going to steal all of my data

</details>

**Claire Vo**: **AI**会不会窃取我的所有数据？这两个问题是：它会窃取所有东西然后和我配偶私奔吗？我到底该怎么办？所以我想这个播客是一个资源，我们实际上现在已经记录了近200个独立的工作流程，都出自这个播客，嗯，在**Chat PRD How I AI**博客上，我们只是给了你一步一步如何复制这些东西的方法。我们也会做这一集，但我认为重点是，找到你正在做的事情，然后尝试一下。嗯，**JJ**，我知道我们得让你回到你的**Co-work****项目**和你的播客，你的**Cloud Coding**和**10X**，以及所有那些事情。所以，我们来做一个非常快速的闪电问答，超级快的答案。第一，除了我们刚才看到的，你发现的**Co-work**最喜欢的一个用例是什么？

<details>
<summary>Original English</summary>

**Claire Vo**: and is AI going to those are the two questions like is it going to steal everything and run off with my spouse and like what do I actually do and so I think like pod you know this podcast is a resource we actually put we're now almost 200 individual workflows documented out of this podcast um on the chat PRD how I AI blog where we've just like given you step by step how to copy this stuff. We'll do this episode as well, but I think the point is just like find something you're working on and and give it a go. Um JJ, I know that we got to get you back to your co-work projects and your podcast, your cloud coding and 10X and all that stuff. So, let's just do really quick lightning round super super fast answers. one, outside of what we just saw, what is your number one favorite co-work use case that you've discovered?

</details>

**JJ Angler**: **内容创作**非常重要。呃，现在正在做这个**Anthropic**研讨会，这太紧张了，但是这个**项目**真的帮了我很多，因为他们给了我们一份30页的文档，说明该做什么和不该做什么。无论何时，我都可以去问他们在这里说了什么，他们在这里做了什么，它真的帮助了我。所以，呃，用**Co-work**导航大量文件非常有帮助。

<details>
<summary>Original English</summary>

**JJ Angler**: Content creation is huge. Uh, doing this anthropic workshop right now, like it's so intense, but and so this project has been really helping me because they gave us like 30page document of like what to do and what not to do. And at any time I could just go and like what do they say here, what do they do here, and it literally helps me. So, uh, navigating a lot of files with co-work is just so helpful.

</details>

**Claire Vo**: 太棒了。我听说有很多使用**Co-work**进行**活动策划**的例子，也有很多使用**Codeex**（**OpenAI**的类似版本）进行**活动策划**的例子。非常好。我，我，我想问，如果你正在用**Co-work**计划你的婚礼。

<details>
<summary>Original English</summary>

**Claire Vo**: Amazing. I've heard a lot of event planning with co-work and a lot of event planning with codeex which is open AI's kind of version of this. Very good. I'm wait I I call how I request if you are planning your wedding with co-work

</details>

**JJ Angler**: 听说过。

<details>
<summary>Original English</summary>

**JJ Angler**: heard that

</details>

**Claire Vo**: 很棒的用例，很棒的用例，它可以帮你找到供应商。它可以帮你写邮件。它可以，哦天哪。很棒的用例。

<details>
<summary>Original English</summary>

**Claire Vo**: great use case great can go find the vendors for you. It can write the emails for you. It could Oh my god. Great use case.

</details>

**JJ Angler**: 我知道。我知道。这将是我的下一个生意。我将做**AI**驱动的婚礼策划。

<details>
<summary>Original English</summary>

**JJ Angler**: I know. I know. This is going to be my next business. I'm going to do AIdriven uh wedding planning.

</details>

**Claire Vo**: 好的。我的第二个问题是，除了**Co-work**之外，你最喜欢用的工具是什么？

<details>
<summary>Original English</summary>

**Claire Vo**: Okay. My second question to you outside of co-work, what what's what's a tool that you're loving?

</details>

**JJ Angler**: 我做了很多。我现在正在为我的很多东西进行**程序化视频创作**。嗯，这真的非常有效。我也非常喜欢**pencil.dev**。它就像设计领域的**Cursor**。所以，你告诉它你想要什么，它就会为你设计。所以，这些是我在**Anthropic****Cloud Code**之外一直在研究的两个最喜欢的工具。

<details>
<summary>Original English</summary>

**JJ Angler**: I do a lot. I'm doing programmatic video creation for like so much of my stuff right now. Um, that's really working well. I really love pencil.dev, too. It's like the cursor but for design. And so, you tell it what you want and it'll design for you. So, those are some of my two favorites that I've been digging into outside of anthropic uh cloud code stuff.

</details>

**Claire Vo**: 是的，伙计。好的。如果在这期节目播出时我还没有制作**Remotion**视频，请在评论中对我大喊。我会做的。人们已经向我询问这个问题好几个月了。我也喜欢**Remotion**。再次强调，呃，**程序化视频生成**。超级酷。嗯，你也可以用**Cloud Code**来做。然后我的最后一个问题，这可能有点棘手，因为你似乎是一个**Whisperflow**用户，喜欢用人类声音与**AI**交流，我认为这让我们稍微礼貌一些，但当**AI**不听话时，你怎么办？你的**提示策略**是什么？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah, man. Okay. If I haven't done a Remotion video by the time this comes out, yell at me in the comments. I will do it. People have been asking this um from me for months and months and months. I love Remotion, too. Again, uh programmatic video generation. Super super cool. Um and you can do it with with with cloud code. And then my last question which is you're this is maybe tricky because you seem to be a whisper flow sort of talk to the AI with your human voice which I think keeps us a little bit more polite but when AI is not listening what do you do? What's your prompting strategy?

</details>

**JJ Angler**: 我通常很有礼貌。

<details>
<summary>Original English</summary>

**JJ Angler**: I'm generally polite

</details>

**Claire Vo**: 因为我，我，我通常很有礼貌，但我会，我会大写，我有时会告诉它，当我是认真的。我通常不会骂它。嗯，通常当它不听话时，它只是不知道我在问什么。这是一个很好的机会，可以更好地沟通，比如：我问的是这个。一个成功的输出会给我带来什么。帮我弄清楚。呃，问我任何问题来帮助我们回到正轨。启动一个**子代理**来弄清楚这里发生了什么。这种事情可以帮助我回到正轨。然后还会说：“嘿，我们刚才经历的不好。把那种情况添加到我的负面输出中，这样我们下次就不会再那样做了。”

<details>
<summary>Original English</summary>

**Claire Vo**: because I I I'm generally polite but I will I will put on the cap locks and I will let it know sometimes when I'm talk when I mean business. I don't normally swear at it though. Um, usually when it's it's not behaving, it just doesn't know what I'm asking. And that's a good chance to like better communicate of like, here's what I'm asking. Here's what a successful output gets me. Help me figure that out. Uh, ask me any questions to help us get back on track. Launch a sub agent to figure out what's going on here. That kind of stuff like helps me like navigate to back to being like on track. And then also saying like, hey, what we just experienced that was not good. add that like scenario to like my negative outputs so we don't do that again.

</details>

**JJ Angler**: 我喜欢这样。我发现自己不会大喊大叫。我确实有时会全部大写。我发现自己会说：“这真是太疯狂了。你刚才做的真是太傻了。改掉它。”嗯，不太礼貌，但很有效。好的，**JJ**，我们可以在哪里找到你，我们如何提供帮助？

<details>
<summary>Original English</summary>

**JJ Angler**: I I love it. I found myself I don't yell. I do sometimes all caps. I found myself being like, "This is truly insane. What you just did is cuckoo. Fix it." Um not not super polite, but but effective. Okay, JJ, where can we find you and how can we be helpful?

</details>

**Claire Vo**: 我想我无处不在。我运营一个名为**10XBuilder**的**YouTube**频道。我在**X**上是**JJing**。呃，**LinkedIn**上是**JJ England**。我在**10X**工作。我在这里领导我们的社区赋能。呃，我们正在做很多事情。所以如果你需要帮助将**AI**转型和赋能带给你的组织，请告诉我们。否则，很高兴来到这里。我们喜欢你的工作。我喜欢你的工作。谢谢你的邀请。这是一段愉快的经历。

<details>
<summary>Original English</summary>

**Claire Vo**: I think I'm pretty much everywhere. I run a YouTube channel called 10XBuilder. I'm on X for JJing. uh LinkedIn at JJ England as well. I work at 10X. I lead our community enablement here. Uh we're doing a ton of stuff. So if you need help bringing AI transformation and enablement to your org, let us know. But otherwise, it is a pleasure being here. We love your work. I love your work. Thank you for inviting me. It's been a joy.

</details>

**JJ Angler**: 感谢你的加入。

<details>
<summary>Original English</summary>

**JJ Angler**: Thanks for joining us.

</details>

**JJ Angler**: 非常感谢观看。如果你喜欢这个节目，请在这里**YouTube**上点赞和订阅，或者更好的是，留下你的评论。你也可以在**Apple Podcasts**、**Spotify**或你最喜欢的播客应用上找到这个播客。请考虑给我们留下评分和评论，这将帮助其他人找到这个节目。你可以在howiipod.com查看我们所有的剧集并了解更多关于节目的信息。下次见。

<details>
<summary>Original English</summary>

**JJ Angler**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>