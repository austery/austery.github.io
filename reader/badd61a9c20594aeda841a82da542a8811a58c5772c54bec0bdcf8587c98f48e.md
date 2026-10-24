---
author: AI Engineer
date: '2026-05-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tDArkCqjA-c
speaker: AI Engineer
tags:
  - ai-agents
  - workflow-automation
  - human-in-the-loop
  - low-code
  - integration-platform
title: n8n 中人机协作自动化与 AI Agent 应用
summary: 本次研讨会由 Liam 主讲，重点介绍了如何使用可视化集成平台 n8n 搭建 AI Agent，以管理 Gmail 和 Google Calendar。核心内容包括 n8n 的低代码特性、AI Agent 的记忆功能、如何通过工具描述进行 Prompt Engineering、以及关键的“人机协作”（Human-in-the-Loop）审批流程。此外，还讨论了 n8n 的企业级特性，如项目隔离、Git 集成和 API 发布能力，并探讨了在团队协作和无 UI 场景下人机协作的实现方式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - n8n
  - Google
  - Salesforce
  - Microsoft Teams
  - GitHub
  - Open Router
  - Slack
products_models:
  - ChatGPT
  - Claopus
  - Sonnet 4.6
media_books: []
status: evergreen
---
### 研讨会开场与 n8n 介绍

**Liam**: 大家好吗？

<details>
<summary>Original English</summary>

**Liam**: How's everybody doing?

</details>

**观众**: 很好。

<details>
<summary>Original English</summary>

**观众**: Good.

</details>

**Liam**: 这是大家今天的第一场研讨会吗？你们之前参加过吗？

<details>
<summary>Original English</summary>

**Liam**: Is this everyone's first workshop of the day? You guys did one before?

</details>

**观众**: 你们比我忙多了。

<details>
<summary>Original English</summary>

**观众**: You guys have been busier than me.

</details>

**Liam**: 好的，太棒了。我是 **Liam**，是 **n8n** 的开发者倡导者。这意味着我可以飞到世界各地，做一些像这样很酷的事情，并向那些可能比我聪明得多的人介绍一些非常酷的技术。

<details>
<summary>Original English</summary>

**Liam**: All right, great. Well, I'm Liam. I'm a uh developer advocate at NAN, which means I get to fly around the world and do really cool stuff like this and speak into people what probably way smarter than I am uh about some some really cool stuff.

</details>

**Liam**: 今天我们的研讨会时间很短。这是大家第一次接触 **n8n** 吗？以前有人用过 **n8n** 吗？请举手。大家都用过。

<details>
<summary>Original English</summary>

**Liam**: Today we have a pretty short workshop. Uh is this is this everyone's first time with NAD? Has everyone used NAN before? Raise it. Everyone has used it before.

</details>

**观众**: 我没用过。

<details>
<summary>Original English</summary>

**观众**: Haven't used it.

</details>

**Liam**: 好的。那些用过的人，比如入门级高级用户，你们会怎么说？

<details>
<summary>Original English</summary>

**Liam**: Okay. of those people who used it like entry level power users like what what would you guys say in terms of

</details>

**观众**: 永远是初学者。

<details>
<summary>Original English</summary>

**观众**: always a beginner always be

</details>

**Liam**: 好的，我们将从基础开始。本质上，我们会像这是你的第一个工作流一样来构建它，我们会从那里开始一个 Agent。然后，我们会在其中添加一些**人机协作**（human in the loop），你就可以基于此进行扩展，让它为你做更多的事情。你基本上会创建一个非常简单的 **Google Gmail** 和 **Calendar** 管理 Agent，它可以为你管理日程。

<details>
<summary>Original English</summary>

**Liam**: okay well we'll be starting from the basics here essentially we're going to build as if it was your first workflow we're going to start from there agent and then we're going to add some human in the loop to it and you'll be set up to take that and expand it to do much more for you'll essentially be making a really simple Google uh Gmail and calendar management agent that can go and and manage your schedule for you.

</details>

**Liam**: 嗯，在这个房间里，因为我不确定这次会议会怎么样，大家的**技术水平**大概是什么样的？从很高（你会编程）到这里（你不知道如何编写 **JavaScript**）的经验都有吗？

<details>
<summary>Original English</summary>

**Liam**: Um and out of the room here because I'm not sure what to expect with this conference. Is there like uh what's everyone's like technical level just from like a really high you can code down here? You don't know how to code like JavaScript experience from this room?

</details>

**观众**: 是。不是。也许。是。

<details>
<summary>Original English</summary>

**观众**: Yes. No. Maybe. Yes.

</details>

**Liam**: 好的。

<details>
<summary>Original English</summary>

**Liam**: Okay.

</details>

**观众**: JavaScript。

<details>
<summary>Original English</summary>

**观众**: JavaScript.

</details>

**Liam**: 好的，**n8n** 的一大优点是，你不需要会编程也能使用它。它是一个**可视化工具**，但你可以在任何需要的地方**插入代码**。甚至可以直接在每个字段中编写一行 **JavaScript** 方法，比如 `toUppercase`，它就能正常工作。所以，你甚至不需要创建一个完整的代码节点或打开一个单独的文件，你可以完全可视化操作，如果你需要一点额外的功能，就可以直接在代码中实现。

<details>
<summary>Original English</summary>

**Liam**: Well, one of the great things about NADN is you don't need to know how to code for it. It's a visual tool, but you can break out into code wherever you need it. even directly in each field you can write one JavaScript method you can write like two uppercase and it just works right so like you don't even need to do a whole code node or open a separate file you can do everything visual and if you need a little bit of extra power right there you just do it right in code

</details>

### AI Agent 构建与编排

**Liam**: 所以现在，我相信我们都能看到这样的情景：既然你在这里，你就可以去任何地方构建一个 Agent，构建 Agent 真是太容易了，对吧？我们看到的一个问题，以及未来的赢家将会是：能够看到你的 Agent 能做什么，知道它正在做什么，看到哪里出了问题，并能够调整和修复它。我认为这才是我们脱颖而出的地方，也是我们最初的起点。作为 Agent 的构建者和**编排者**，你可以看到和控制正在发生的一切。我保证我讨厌幻灯片。我几乎从幻灯片模板中删除了所有内容。这些基本上是我们仅有的几张。所以，如果有人可以在自己的电脑上访问这个链接，如果你跟不上了，或者如果你想再做一次，或者对于看视频的人来说，这是一个 **Notion** 页面，里面包含了整个研讨会内容，甚至还提供了课后作业。所以，如果你想继续，那里有如何继续你的 Agent 的提示，让它不断运行，因为我们这里只有一个小时，时间并不多。

<details>
<summary>Original English</summary>

**Liam**: so right now I'm sure we all can see the landscape since you're here you can go anywhere and build an agent it's so easy to build agents right One of the problems we're seeing and where the winners are going to lie is seeing what your agent can do, knowing what it's doing, seeing what went wrong and being able to tweak it and fix it. I think that's really where we stand out and it's kind of where we started off at which gives us a really strong starting point here as being the agent builder and orchestrator that you can see and control what's happening. And I promise I hate slides. I removed almost all of them from the slide template. These are the only ones we have pretty much. So if anyone can go to this this link on your computer if you fall behind or if you want to do it again or for the people on video this is a notion page that has the entire workshop and it actually goes and gives you homework after. So if you want to continue there's prompts there of how to continue your agent afterwards to keep it moving because we only have an hour here which isn't a ton of time.

</details>

**Liam**: 好了。嗯，还有人还在等这个链接吗？好的，如果需要的话，我随时可以再回到这个页面。在那个页面里，你会看到这个页面。你们开始需要做一点工作，这样才能真正使用 **n8n**。

<details>
<summary>Original English</summary>

**Liam**: All right. And uh is anyone still waiting on this link here? Okay. I can always come right back to this if we need it. And in there you'll have this page. And you guys have a little bit of work to do starting off so that you can actually use NAD.

</details>

### n8n 账户设置与版本要求

**Liam**: 所以你可以点击这个链接，注册一个 **n8n Cloud** 账户。你会自动获得 14 天的免费试用。现在这已经足够了。你不需要现在升级。但是，请务必今天或明天去完成这个步骤，因为之后我会移除这些代码。我为你们争取到了一年的 **Cloud Pro**，价值 600 美元。嗯，我们不常这样做。我喜欢大方一点。所以你们可以去使用它。你们可以免费使用一年。

<details>
<summary>Original English</summary>

**Liam**: So you can go in to this link right here, register for an NAD cloud account. You'll automatically get a 14-day free trial there. That's enough for now. You don't have to upgrade now. But then make sure you go and do this, you know, today or tomorrow because I'll remove these codes after. I uh I I got you guys a year of Cloud Pro, which is $600 value. Uh which we don't do very often. I uh I like to be generous. So you guys can go in and use that. You get it a year for free.

</details>

**Liam**: 所以我给你们一分钟。如果你已经有自己的 **n8n** 实例，比如你已经在使用它，如果你使用自托管版本，并且已经设置好凭证等，那就太好了。请确保你的版本是 **214.2** 最新稳定版。如果你有自己的云版本，请确保你已升级到该版本。如果你有一个新的自托管实例，并且你还没有怎么使用它，那么请注意，如果你遇到与配置相关的问题，不幸的是，我在此次会议中真的帮不了你。这有点超出范围了。我们必须确保快速推进。所以，我给大家几分钟时间来完成设置。我知道有一个问卷，需要一分钟才能加载。

<details>
<summary>Original English</summary_content>

**Liam**: So I'll just give you guys a minute. If you already have your own NAD um instance, like if you use it already, if you use self-hosted and like you have credentials set up and everything, that's great. Just make sure you're on 214.2 latest stable version. If you have your own cloud version, make sure you're upgraded to that. If you have like a new self-hosted thing and you haven't used it much, just know if you run into issues related to your configuration, I unfortunately can't really help you uh in this session. It's a little out of scope. We have to make sure we keep moving fast. So, I'll just give everyone a few minutes to get this set up. I know there's a questionnaire and it takes a minute to load.

</details>

**Liam**: 在座使用 **n8n** 的人，你们是在工作中用，还是仅仅是个人爱好？

<details>
<summary>Original English</summary>

**Liam**: And the people here who use NAN, do you use it at work? Just personally, for fun?

</details>

**观众**: 都有。

<details>
<summary>Original English</summary>

**观众**: Both.

</details>

**观众**: 这通常是共识吗？你们是把这个带到工作中的人吗？

<details>
<summary>Original English</summary>

**观众**: Is that usually the consensus? Are you guys the ones who are bringing it to your job at work?

</details>

**观众**: 是的，那太棒了。

<details>
<summary>Original English</summary>

**观众**: Yeah, that's great.

</details>

**观众**: 比如，

<details>
<summary>Original English</summary>

**观众**: for example,

</details>

**观众**: 比如，

<details>
<summary>Original English</summary>

**观众**: for example,

</details>

**Liam**: 太棒了，太棒了。如果你们在工作中需要使用它，需要帮助说服老板，我们这里有两个人，他们就是专门做这个的。所以你可以找他们问那些关于无聊的问题，而把技术问题问我。

<details>
<summary>Original English</summary>

**Liam**: that's great. That's great. If you guys need help using it at work, need help convincing your bosses, we got two guys over here who uh that's what they specialize in. So you can find them asking me the nerdy questions. You can ask them uh uh you know the boring questions.

</details>

**Liam**: 哦，当然。所以，我还要确保我们没有落下任何人。这里有一个我们将要构建的工作流的屏幕截图。然后这里是工作流的 **JSON**，你可以直接点击这个按钮复制它。**n8n** 的一大优点（许多优点之一）是，你可以直接复制粘贴内容到其中。所以你可以复制这个，直接粘贴到你的画布上，你就会得到一个完成的工作流。尽量跟着我做，但是你也可以回去看看这个，比较一下，看看我做了什么。我确信我在这里构建得比当着你们面实时构建的要好。嗯，如果你有问题，即使与内容不直接相关，也请举手或大声说出来，我会停下来。我真的希望这次会议能专注于打好基础，确保每个人都能顺利进行，并在之后自己扩展它。

<details>
<summary>Original English</summary>

**Liam**: Oh, for sure. So uh another thing I want to make sure we're not really leaving anybody behind. Down here there is um there's a screenshot of kind of what it looks like we're going to be building. And then right here is the workflow JSON that you can just press this button right here to copy. And the great thing, one of the many great things about NADN is you can just copy and paste stuff into it. So you can copy this, paste it right into your canvas and you'll have the completed thing. Try to follow along, but uh you can go back and look at this, compare, see what I did. I'm sure I built it better here than I will live in front of you. Uh, and if you have a question, whether it's like even if it's not really directly related, raise your hand or shout it out and I'll stop. I really want to focus this session on getting the foundations right, making sure everybody is good to move on and, you know, expand this yourself afterwards.

</details>

### n8n 界面与工作流基础

**Liam**: 设置进展如何？我们快完成了吗？谁还没设置好 **n8n**？大家都设置好了。我的本地版本，例如 260。

<details>
<summary>Original English</summary>

**Liam**: How's progress on on setting this up? Are we getting closer for uh Can I get a show of hands of who still isn't set up in NAM? Everybody is. my local for example 260

</details>

**观众**: 应该没问题。

<details>
<summary>Original English</summary>

**观众**: it you should you should be okay I just

</details>

**Liam**: 嗯，以前有人在研讨会上落后 60 个版本。但如果你是自托管的，你可能不需要那些。

<details>
<summary>Original English</summary>

**Liam**: uh there's been times where people are like 60 versions behind in a workshop but if you're self-hosted you probably don't need the

</details>

**观众**: 工作。

<details>
<summary>Original English</summary>

**观众**: work

</details>

**Liam**: 哦，是的，那没关系。我只是想快速介绍一下 **n8n**。这是演示版本。对于那些刚接触 **n8n** 的人，每个人都觉得很难看清吗？我可以……这会让我很难过，但我可以打开亮色模式。

<details>
<summary>Original English</summary>

**Liam**: oh yeah that that's fine I'm just going to give a quick uh intro to naden as well so Uh this is the demo one. So for those very new to naden um is this is this very hard to see for everybody? I can it will make me very sad but I can turn on light mode.

</details>

**观众**: 太糟糕了。

<details>
<summary>Original English</summary>

**观众**: Gross.

</details>

**Liam**: 好的，抱歉那些在 **YouTube** 上观看的人。我知道你们会像我一样感受。所以这就是 **n8n**。这是它的界面。如果你是自托管的，你这里就没有这些项目。你只有自己的个人空间，这很好。在云端版和企业版等版本中，你会获得这些特定项目。这样做的好处是你可以将所有凭证分开。所以，如果你有一个项目在做一件事，另一个项目在做完全不同的事，你就不会不小心使用不同的凭证。你可以在不同的项目之间共享不同的人员，从而实现良好的访问控制。

<details>
<summary>Original English</summary>

**Liam**: Okay, sorry to the people watching on YouTube. I know you're like h at least that's how I always feel. But so this is Naden. This is the interface. If you're on self-hosted, you don't have these projects over here. You just have your personal space, which is which is fine. On cloud and enterprise and all those, you get these specific projects. Really nice thing about that is you can have all your credentials separate. So if you have one project where you're doing one thing, another project where you're doing a completely different thing, you don't use different um credentials by accident and you can share in different people between the different projects, you know, to have good access control.

</details>

**Liam**: 我们可以在这里创建一个工作流，并且我们将手动构建它。

<details>
<summary>Original English</summary>

**Liam**: We can make a workflow here and we'll build this manually.

</details>

**Liam**: **n8n** 始于 2019 年，在 **ChatGPT** 问世之前，那时的 **AI** 比现在无聊得多。那时它只是一个**集成工作流工具**。所以它只是一个**低代码**的方式来表达“如果这样，就那样做，然后再做其他事情”。

<details>
<summary>Original English</summary>

**Liam**: NAD started in 2019 before chatgvt came out back when AI was much more boring than it is today. And back then it was just like an integration workflow integration tool. So it's just a low code way to say if this then do that then do something else.

</details>

**Liam**: 所以，例如，你可以有一个表单。嗯，这里有这些**触发器**。我跳得有点快。所有事物都始于一个触发器。所以它可以是当一个表单被提交时，我们可以说“潜在客户”，然后是姓名，接着原生的 **n8n** 表单会在这里出现，并说“我的名字是 Liam”。对，所以那是一个触发器。还有像计划表之类的东西，以及成百上千的其他触发器，比如 **Webhook** 和 **API** 调用等等。所以你有一个触发器，然后是**动作**，即在其他应用程序中发生的事情，比如 **Google** 创建联系人，发送电子邮件，嗯，还有像 **Salesforce**，如果你想创建联系人，只是把东西连接起来。

<details>
<summary>Original English</summary>

**Liam**: So you can for instance have a form uh there there's these triggers right so I'm jumping ahead. Everything starts with a trigger. So it can be when a form is submitted which we can say uh lead and then that will be name and then the native NAN form will come up here and say my name is Liam right so that's a trigger there's also stuff like schedule and hundreds and hundreds of others there's web hook and uh API calls and everything like that so you have a trigger and then there's actions things that happen in other apps like Google create a contact, send an email, um, and like Salesforce if you want to create a contact just gluing stuff together.

</details>

**Liam**: 其中一个非常强大的功能是**控制流**，对吧？所以，如果这样就那样做，你可以设置不同的条件。如果这是一个个人联系人，**Google** 联系人，业务联系人，就直接进入 **Salesforce**。这就是我和许多许多其他人在 **ChatGPT** 发布之前，在 **AI Agent** 没有任何意义之前，就爱上它的原因。这是一个人们喜欢用来构建事物和构建完整**集成系统**的平台。你可以用它做比你想象的更多的事情。任何开发者或相关人员都会知道，这基本上只是一个**抽象的 API 调用**版本。你只是连接各种东西，运行逻辑。当然，现在我们做的方式有所不同。

<details>
<summary>Original English</summary>

**Liam**: And one of the really powerful things is the control flow, right? So if this then do that you can have different conditions. If you if this is a personal contact, Google contacts, business contact, go right into Salesforce. And this right here is what me and many, many others fell in love with before chat tpt was ever released, before AI agent meant anything. This was a platform that people love to use to build things and to build full integrated systems. And you can do much more than you'd expect with this. Anyone who is a developer or anything, you would know this is pretty much just an abstracted version of putting together API calls. You're just hooking stuff up, running logic with it. Of course, now we do uh it a little bit differently.

</details>

### 构建 AI Agent 工作流：聊天触发器与 Agent 节点

**Liam**: 嗯，现在我们可以开始跟着做了，如果你还没开始的话。我们要构建我们的工作流。现在，我们基本上想和所有东西聊天。它不只是在某个时间或某个计划下发生。我们的主要**接口**大部分是聊天，或者至少是某种方式让它与 **AI** 交互。所以在一个新的工作流中，我们将打开并放入一个**聊天触发器**。

<details>
<summary>Original English</summary>

**Liam**: Uh and now we can start to follow along if you weren't already. This we're going to build our workflow. Now, we pretty much want to chat with everything. It's not really when this happens around a schedule or whatever. Our primary interface a lot is a chat or at least to get it to an AI somehow. So in a new workflow we're going to open a put in a chat trigger

</details>

**Liam**: 并且使用 **n8n**，你可以集成许多不同的东西，比如你可以添加一个 **Slack** 触发器。所以，嗯，**Slack**，然后在这个触发器中，比如在“收到消息”或“消息发布到频道”时，你可以让它以这种方式启动。在那个 **Notion** 文档的末尾，有你的作业，让你去连接到你自己的消息系统。但现在，我们将使用内置的聊天功能，因为它很容易且已经内置。

<details>
<summary>Original English</summary>

**Liam**: and with naden you can integrate to many different things like for instance you can add a slack trigger. So, uh, Slack and then in the trigger, like on, uh, message received, on message posted to channel, you can have it start that way. At the end of that notion document, that's your homework to go in and connect it to your own messaging system. But for right now, we're going to use the built-in chat just because it's easy and already built in.

</details>

**Liam**: 当你将聊天功能添加到画布时，你会在下面得到这个框。我们可以输入一条消息。这对于**调试**和在你制作时进行测试非常有用，因为它会直接启动。你甚至可以启动一个没有 **AI** 的工作流。我们还会做的是，如果你点击触发器，有一个复选框写着“在聊天中心可用”。

<details>
<summary>Original English</summary>

**Liam**: When you add chat to your canvas, you get this box down here. We can type a message. This is great for debugging and just testing while you're making it because it just starts it right there. You can even just start a workflow without any AI in there. What we'll also do, if you click in the trigger, there's this check box that says make available in chatub.

</details>

**Liam**: 这是相对较新的功能，只要工作流已发布。当我们有了这个，侧边栏这里有一个小的**聊天图标**。如果我们点击它并切换到标签页，我们实际上在 **n8n** 内部就有一个完整的**聊天界面**。所以，如果你不想连接到外部工具，你就不必这样做。直接在这里使用它会更简单。我认为就是这个。所以，这就是我们放进去的聊天触发器。所以，如果我们在这里说“你好，我是 **AI** 工程师”，

<details>
<summary>Original English</summary>

**Liam**: This is relatively new and as long as the workflow is published. When we have that, there's this little chat icon right here in the sidebar. If we click this and go to the tab, we actually have a whole chat interface right inside of NAD. So, you don't have to connect it to an external tool if you don't want to. It's just easier to kind of use it right in here. I think that's this one right here. So, this is that chat chat trigger we put in there. So, if we say in here, hello from AI engineer

</details>

**Liam**: 并发送出去，它没有连接到任何东西。但是如果我们回到这个工作流，并进入执行标签页，这里就是那条消息。让我把它拖过来，这样你就能看到，或者我可以直接点击。你好，我是 **AI** 工程师。所以你可以在这里直接使用它。所以这就是我们今天在这节课中将要设置的，你可以在这里与你的 Agent 聊天。将来，在会议结束后，你可以用你自己的聊天工具来设置它。

<details>
<summary>Original English</summary>

**Liam**: and send that, it's not hooked up to anything. But if we come back to this workflow and go to the executions tab, this right here is that message. Let me pull this over so you can see it or I can just click in. Hello from AI engineer. So you can just use it right inside of here. So that's what we'll be setting up today in this session where you can chat with your agent here. In the future after the session you can set it up with your own chat tool.

</details>

**Liam**: 当然，我们需要将 **AI** 连接到它，对吧？所以你可以点击这里的小加号。你可以在键盘上按 N，或者点击这里。我们会搜索 **AI Agent**。

<details>
<summary>Original English</summary>

**Liam**: And of course we need to get AI hooked up to this, right? So you can click the little plus here. You can press N on your keyboard. or this up here. And we'll just search AI agent.

</details>

**Liam**: **AI Agent 节点**是一种特殊的节点。你可以看到它看起来非常不同，它有这些小“腿”从底部伸出，而不是从侧面。

<details>
<summary>Original English</summary_content>

**Liam**: And the AI agent node is a special kind of node. You can see it looks much different where it has these little legs coming off the bottom instead of on the side.

</details>

### 配置 AI Agent：模型与内存

**Liam**: 所以 **AI Agent** 默认需要三样东西，但只有一样是必需的。我们需要一个**聊天模型**（Chat Model）。这是一个**大型语言模型**（Large Language Model）。**n8n** 的另一个巨大优势是你可以连接你想要的任何模型。如果它不在列表中，你实际上可以选择 **OpenAI** 模型，然后更改基础 **URL** 到另一个提供商，这通常会奏效。如果你使用代理或其他类似的东西来支持大型企业，这就是你操作的方式。我将使用 **Open Router**。

<details>
<summary>Original English</summary>

**Liam**: So the AI agent is wants three things by default essentially and only one of them is required. We need a chat model. This is the large language model. Another really big benefit of NADN is you can connect any that you want. If it's not on this list, you can actually do uh pick the open AI model one and change the base URL to another provider and that will usually work. If you use a proxy or something like that for a big enterprise, that's how you do it. I'm going to use open router

</details>

**Liam**: **Open Router** 有一个很大的优势，你可以从该服务中选择你想要的任何模型。你可以使用 **ChatGPT 5.3** 或 **Claopus 4.6** 或任何你想要的模型。还有一个更大的福利，我为你们提供了一个密钥。我今天之后会移除这个密钥，但如果你复制这个密钥，在 **Notion** 中你应该已经打开了。

<details>
<summary>Original English</summary>

**Liam**: which has a really big benefit of from that service. You can pick any model you want. You can use chat GPT 5.3 or claopus 4.6 or whatever you want. And even bigger bonus, I gave you a key for it. I will remove this after today, but if you copy this key, brighten notion that you should have open.

</details>

**Liam**: 你可以点击 **Open Router** 账户中的“设置凭证”，然后粘贴进去，应该就能用了。现在，有了它，它应该会加载这些。我将使用 **Sonnet 4.6**。你可以使用任何你想要的。选择一个聪明的模型，这样它就知道如何使用你的工具。然后你将它连接进去。请记住，你使用的任何大型语言模型节点，都必须使用该特定提供商的令牌。例如，你不能在 **Open Router** 之外的其他地方使用 **Open Router** 的令牌。

<details>
<summary>Original English</summary>

**Liam**: You can click setup credential right here on the open router account and just paste it in and that should work. Now, with that in there, it should load these. I'm going to use Sonnet 4.6. You can use whatever you want. Use something smart so it knows to use your tools. And then you connect that into there. Just keep in mind any large language model node you use, you have to use the token for that specific um provider. So you can't use that open router token inside of something other than open router for instance.

</details>

**Liam**: 好了，目前有什么问题吗？我们都很好。大家都走到这一步了吗，都配置好了这个 Agent 吗？好的。

<details>
<summary>Original English</summary>

**Liam**: All right, any questions thus far? We're all good. Is everybody at this point with this agent? Okay.

</details>

**Liam**: 现在，在这一点上，我们可以和 Agent 在这里聊天。我们可以说“你好吗？”或者任何我们想说的话。我们应该会收到回复，就像这样。但是如果我们说“我的第一条消息是什么？”它会说你没有任何以前的消息。这里有人知道问题出在哪里吗？

<details>
<summary>Original English</summary>

**Liam**: Now, at this point, we can chat with the agent right here. We can say, "How are you?" or whatever we want. And we should get a response back just like that. But if we say, "What was my first message?" You don't have any previous messages. Does anyone know here know what the problem is?

</details>

**观众**: 它没有记忆。

<details>
<summary>Original English</summary>

**观众**: It has no memory.

</details>

**Liam**: **Open Router** 不够好，不能为我们存储。我们必须自己存储。所以这里有一个**内存**标签页，里面有所有这些不同的选项，你可以使用。我总是使用**简单内存**，除非我在做一些超级花哨的事情。即使它说“为初学者设计”，也不要感到羞耻。它只是让事情变得简单。立即生效。我看到后面有人举手了吗？

<details>
<summary>Original English</summary>

**Liam**: Open router is not being nice enough to store it for us. We have to store it oursel. So there's this memory tab right here where there's these uh all these different options you can use. I just always use simple memory unless I'm doing something super fancy. Even though it says for beginners, no shame. It just makes it easy. Works right away. Did I see a hand on the back?

</details>

**观众**: 没有。

<details>
<summary>Original English</summary>

**观众**: No.

</details>

**Liam**: 是的。怎么了？

<details>
<summary>Original English</summary_content>

**Liam**: Yep. What's up?

</details>

**观众**: 不同的时间段或不同类型的内存你会用什么？以及用于什么类型的应用程序？

<details>
<summary>Original English</summary>

**观众**: What are the difference periods or different types of memory you would use and for what type of applications?

</details>

**Liam**: 当然。所以问题是不同类型的内存是什么，以及它们适用于哪些不同的应用程序？

<details>
<summary>Original English</summary>

**Liam**: For sure. So the question was what are the different types of memories and what are the different applications?

</details>

**Liam**: 所以简单内存我们自己存储在 **n8n** 中。我们为你处理所有事情。这里面有一个**上下文窗口长度**，这里是 5。这意味着它只会记住你上下文中最近的五条消息，它不会记住更早的任何消息。嗯，这个默认值可能应该更高一些。现在人们的对话时间更长。你可以把它设置为 50 或其他值。请记住，你为所有这些过去的令牌付费。但这一切都为你抽象化了。它只是工作，你不需要做任何其他事情。

<details>
<summary>Original English</summary>

**Liam**: So simple memory we store it in naden ourself. we handle it all for you. And inside of here, there's this context window length, which means this is five here. So, what that means is it will only remember five messages in your context, and it won't remember anything past there. Um, that default should probably be a bit higher. People have longer conversations these days. You can make that like 50 or something. Just know you're paying for all those past tokens. But this is all abstracted for you. It just works. You don't have to do anything else.

</details>

**Liam**: 这几乎适用于所有基于聊天的应用程序。如果你要将其集成到现有的系统中，你会使用 **Postgres** 或 **Redis** 或其他一些数据库。例如，使用 **Postgres**，你可以将其放入一个表中，然后如果你有另一个应用程序，你可以使用 **Postgres** 和你的 **ORM** 或其他方式来获取这些消息并显示它们。例如，如果你有一个聊天 **UI** 或你编写的仪表板，你可以查询 **Postgres** 并将这些消息放在那里，作为一个例子。但最大的区别是，这只是**抽象化**了。我们在 **n8n** 中为你完成所有事情。使用 **Postgres**，它只是将这些消息保存到一个表中。

<details>
<summary>Original English</summary>

**Liam**: that works for a pretty much any application where you're doing a chatbased system. You would use something like Postgress or Reddus or one of these other ones if you're integrating it into an existing existing system. For instance, with Postgress, you can put it into a table and then if you have another application, you can just use Postgress with like your OM or whatever to get that messages and display it. For instance, if you had a chat UI or some like a dashboard you vibe coded, you could just query Postgress and put those messages on there as one uh example. But the biggest difference is just that this is abstracted. We do everything in Naden for you. With Postgress, it just goes and saves those messages to a table.

</details>

**Liam**: 现在有了这里的内存，聊天节点会给你一个**会话 ID**，然后它会把这个 ID 传给简单内存来记住它。我想这是一个很好的时机来提一下**表达式**。如果你以前没有见过这个，有些人是在我们开始后才进来的。

<details>
<summary>Original English</summary>

**Liam**: And now with memory here, the chat node gives you a session ID and then it just passes that in to the simple memory to remember it. And I guess this is a good point to mention expressions. If you have not uh seen this before, some people walked in uh right be since you should get on this for anyone who walked in uh after we started.

</details>

**Liam**: 这个 **Notion** 页面是我们现在正在做的一切的中心。所以，如果你还没有看到，我还会把它展示五秒钟。请扫描或拍照。

<details>
<summary>Original English</summary>

**Liam**: This notion page is the home of everything we're doing right now. So, if you haven't gotten to this, I'll have it up for five more seconds. Please scan or take a picture of the All right.

</details>

### n8n 表达式与工具集成

**Liam**: 所以，在 **n8n** 中，你会看到这些括号和绿色的部分。我们称之为**表达式**。所以你可以直接在字段中输入内容，那只是一个**静态值**。它永远只会是那个键盘输入。但是如果你把它改为表达式，这仍然会是一个静态值。但是你在这些花括号内放的任何东西都是 **JavaScript**。你会看到一些建议。我们提供了一些方便的函数。例如，它会放置日期时间。它真的只是任何 **JavaScript** 都可以工作。你可以说 `Math.random`，它就会执行那个函数。

<details>
<summary>Original English</summary>

**Liam**: So, in NAN, you'll see these brackets and the green stuff. We call that an expression. So you can type things into fields just and then that's just a static value. It's always just going to be that keyboard mash. But if you change it to expression, this is still just going to be a static value. But anything that you put inside of these curly braces is JavaScript. And you'll see some suggestions here. We give some um convenience functions. For instance, like now it'll put the date time. It really is just anything JavaScript works here. You can say uh like math do random and it does that function.

</details>

**Liam**: 但人们最常用它来做什么呢？当然，你可以直接选择一个字段。这是来自触发器节点，你可以直接拖动一个值，然后放进去。这很棒，如果我们正在构建一些除了这个 **ID** 之外的东西，你可以进去，它会连接所有内容，将它们放入一个字段中。现在我们有了一个可以工作的 Agent。你可以和它聊天，你基本上只是在和提供商聊天。但我们特别希望它能管理我们的电子邮件和日历机器人。

<details>
<summary>Original English</summary>

**Liam**: But what people use the most for this is of course you can just take a field. This is from the trigger node and you can just drag a value and plop it right in there. Great thing about this, if we're building something other than this ID, you could go in and it concatenates everything, puts it into one one field. And now we have an agent that will work. You can go and chat with it, and you're essentially just chatting with the provider. But we want this specifically to manage our uh email and calendar bot.

</details>

**Liam**: 所以我们要做的是添加我放在那个简单画布上的相同节点。你有问题吗？抱歉，我以为你举手了。将这些相同的节点放在上面来执行这些操作。

<details>
<summary>Original English</summary>

**Liam**: So what we need to do for that is add those same nodes I put on that simple canvas that said did you have a question? Sorry I thought you raised your hand. Put those same nodes on to do those actions.

</details>

**Liam**: 但不同之处在于，对于 Agent，我们不需要将它们放在这里作为不同的节点，我们可以直接将它们作为工具提供给 Agent 自己使用。我们在常规工具中拥有的每个节点，比如 **Google** 统计联系人、**Gmail**，都可以用作工具，这会使它变成一个小的圆形节点，然后 **AI Agent** 就可以自行决定使用这个节点。所以，例如，我们可以说“发送消息”，然后这些小按钮可以让 **AI** 自动填写。

<details>
<summary>Original English</summary>

**Liam**: But the difference is with an agent instead of putting them at the end here just as a different node we can just give them as tools for the agent to use by itself. Every node that we have in the regular tool like Google count contacts, Gmail, you can use as a tool which makes it this little circle node and then the AI agent can just use this node at its discretion. So uh for instance, we can say send a message and then these little buttons right here let the AI fill it in automatically.

</details>

**Liam**: 呃，这里每个人都用 **Gmail** 工作或个人使用吗？否则，呃，**Microsoft** 设置起来就不那么容易了。但直接用 **Google** 登录就好。我不是有意闪现我所有的东西。但是，天哪，如果我拔掉电脑一秒钟，会中断录音吗？会。我可以之后再插回去吗？好的。

<details>
<summary>Original English</summary>

**Liam**: And uh does everyone here use Gmail for their uh work or for their for their personal? Otherwise, uh Microsoft isn't quite as easy to set up with. But just go go ahead sign in with Google. I did not mean to flash all of my stuff there. But oh Jesus, is it going to break the recording if I unplug my uh computer for a second? It will. Like can I plug it back in after? Okay.

</details>

**Liam**: 我要快点连接我的 **Google**。所以，当我这样做的时候，你也可以点击它，设置你的账户，这应该只是一个一键安装。我的浏览器崩溃了。

<details>
<summary>Original English</summary>

**Liam**: I'm going to connect my Google really quick. So, while I'm doing this, you can go ahead and also click that and uh get yours set up, which should just be a one-click install. And my browser crashed.

</details>

**观众**: 这是今天发生的最糟糕的事情了。我们还不错。

<details>
<summary>Original English</summary>

**观众**: That's the worst thing that happens today. We're doing okay.

</details>

**Liam**: 是的，是我。好的。大家都连接好 **Google** 了吗？这在每个人身上都奏效了。可能比我花的时间少。好的，录音没问题。好的，所以现在你们应该连接好了。哦，它连接了三次。好的，太棒了。

<details>
<summary>Original English</summary>

**Liam**: Yes, it's me. All right. Does everyone have their Google connected? That worked for everybody. Probably took you less time than me. Okay, we good on the recording. Okay, so now you should have Oh, it connected three times. Okay, great.

</details>

**Liam**: 关于 **n8n**，如果你以前没用过，很多人都会搞混的是，如果你点击它，你会编辑旧的连接。如果你想添加一个新的，你需要点击这里，然后选择“添加新凭证”。我们只需认证 **Gmail**。我们还将使用 **Google Calendar**。所以，你也要用 **Google** 登录那个。

<details>
<summary>Original English</summary>

**Liam**: What um what trips a lot of people up about NAD if you haven't used it before, if you click this, you're going to edit your old connection. If you want to add a new one, you need to click in here and say the add new credential. And we just authenticate a Gmail. We're also going to use Google Calendar. So, you have to sign in with Google with that one as well.

</details>

### n8n 工具的精细控制与 Prompting

**Liam**: 现在这些都将连接起来，并且应该能满足我们所有的需求。所以现在我们基本上只需要去设置这些工具。我们希望这个 Agent 能够读取我们的电子邮件，搜索我们的电子邮件，归档电子邮件，发送消息。所以基本上，我只是要去做这些。你们也可以去做。如果你有问题，遇到任何麻烦。嗯，当你这样做的时候，你需要知道的是，这个按钮可以让 **AI** 来设置它。

<details>
<summary>Original English</summary>

**Liam**: And now those will be connected and it should work for everything that we need. So now we essentially just want to go in and set up these these tools. So we're going to want this agent to be able to read our emails, search our emails, archive emails, um send messages. So essentially, I'm just going to go ahead and do that. You guys can go ahead and do that, too. If you have questions, hit any troubles. Uh, what you will need to know when you do that, you this button right here lets the AI set it.

</details>

**Liam**: 我觉得这个很重要，因为在很多情况下，比如 **Claude Code**，如果你给了它访问你的 **Google Calendar** 的权限，它基本上就可以随意操作。它必须去执行那些 **API** 调用。当我们在 **n8n** 中给某个东西一个工具时，它的每个字段都是独立的。

<details>
<summary>Original English</summary>

**Liam**: And I guess this is this is important to cover because in a lot of like let's say cloud code for example, if you give it access to your Google calendar, it's essentially able to go in and do whatever it wants. It has to go and make those API calls. when we're giving a something a tool in NADN, it has every single field individually.

</details>

**Liam**: 所以它只能设置我们明确告诉它设置的东西。所以我们，例如，可以设置主题，设置消息，并且只让它设置“收件人”字段。既然那是我们唯一拥有的东西，你实际上可以看到它是如何设置的。它在这里放置了这个**辅助表达式**。这是它唯一能操作的字段。所以，它永远不能改变其他的字段。

<details>
<summary>Original English</summary>

**Liam**: So it can only set the things that we tell it to specifically. So we could, for instance, have the subject set, the message set, and only let it set the two field. And since that's the only thing that we have, you can actually see how this is set up. it puts this helper expression in here. This is the only field it can do. So, it can never change the other ones.

</details>

**Liam**: 所以，这是**双刃剑**的一面。双刃剑的另一面是，这意味着我们必须设置所有字段。所以我们必须进去说“主题已定义”，“消息已定义”，“收件人已定义”，你可以点击那个按钮，但你也可以像这样使用这个表达式说“来自 **AI**”，它就会工作。你为什么不总是点击这个小魔术按钮的原因是，有时你想要混合不同的东西，对吧？所以想象一下，我将通过说一条消息来获取一个测试值，比如“我的最新邮件是什么？”你必须设置它。

<details>
<summary>Original English</summary>

**Liam**: So, that's one side of the double-edged sword. The other side of the double-edged sword is that it means we have to set up all the fields. So we have to go in and say subject defined message defined to defined which you can click that button but you can also say from AI like this using this expression and it will work. The reason why you wouldn't just always click this little magic button is because sometimes you want to mix stuff together, right? So imagine I'm going to get a test value by saying a message like what's my latest emails? You have to have that set.

</details>

**Liam**: 我的最新邮件是什么？我可以停止它。现在，我不仅可以放入“来自 **AI**”，然后放入字段名称。即使它显示“未定义”，那只是因为它没有值。现在，当它运行时，**AI** 将提供一个值。你可以在这里硬编码一些其他内容，比如你可以说“回复消息”。

<details>
<summary>Original English</summary>

**Liam**: What's my latest emails? And I can stop that. And now, not only can I uh can I put in the from AI and then put in the field name, which this lets the AI even though it says undefined, that's just because it doesn't have a value. Now, when it runs, the AI will provide a value. You could hardcode something else in here like you can say responding to message

</details>

**Liam**: 然后你可以输入任意多的静态文本，但你也可以引用其他字段，比如这里的**聊天输入**。所以如果你想对你正在做的事情非常透明，你可以说“这是一个 **AI** 在回复这条消息”。然后你可以把它包含在你的电子邮件或任何你正在设置的东西中。所以这就是你想要将它作为模板嵌入文本时使用“来自 **AI**”的原因。对于我们现在来说，我只希望它能在这里完成所有事情。

<details>
<summary>Original English</summary>

**Liam**: And then you can type as much static text as you want, but you can also reference other fields like chat input right here. So if you want to be really um transparent about what you're doing, you can be like this is an AI responding to message this. And then you can just include that in your email or whatever you're setting up with. So that's why you would use the from AI if you want to template it into text like that. For us right now, I just want it to do everything here.

</details>

**Liam**: 让我们看看，这个设置正确吗？发送消息。

<details>
<summary>Original English</summary>

**Liam**: And let's see, is this set up correctly? Send a message.

</details>

**Liam**: 完美。设置工具时还需要知道的另一件事是**提示词**（prompting）。我发现人们在 **n8n** 中经常搞砸这一点，那就是你需要好好地给你的节点命名。所以，这个自动命名就很好：“在 **Gmail** 中发送消息”。我甚至会直接把它改名为“发送邮件”。

<details>
<summary>Original English</summary>

**Liam**: Perfect. One other thing you need to know with setting up your tools is the prompting. This is something that I see people messing up in NAN all the time is you need to name your nodes really well. So, this automatic name is pretty good. Send a message in Gmail. I would even just rename it to send a email

</details>

**Liam**: 然后是**工具描述**，它会自动设置。你总是希望手动设置它，并在这里描述工具和**提示词**。这会传递给 **LLM**，向它展示可用的工具。所以每个 **LLM** 调用本质上都是如此，这也是所有平台下工具的工作方式。**AI** 可以看到所有工具的列表，包括它们的名称和描述。节点名称是工具名称。节点描述是工具描述。所以你实际上可以在这里输入完整的提示词。

<details>
<summary>Original English</summary>

**Liam**: and then the tool description where it's set automatically. You always want to set it manually and describe the tool and prompt it here. This is passed in to the LLM to show it what tools are available to it. So every LLM call essentially and this is how tools work under the hood for every platform. The AI can see a list of all the tools with their names and descriptions. The node name is the tool name. The node description is the tool description. So you can actually put in full prompts here.

</details>

**Liam**: 所以我很多时候，与其在这个 **AI Agent** 内部添加系统提示词，不如……抱歉，我还没给你们展示那个。我很快会讲到。

<details>
<summary>Original English</summary>

**Liam**: So what I do a lot of the times instead of adding the system prompt inside of this AI agent, which sorry I I didn't show you that yet. I'm getting to it.

</details>

**Liam**: 我相信我们都熟悉**系统提示词**，因为我们正在参加 **AI** 工程师会议。在这里，在**系统消息**中，你通常会放置所有不同的内容，但我喜欢通过让它更模块化来做到这一点，我只放置我的电子邮件提示词，比如“不要使用破折号，不要做任何事情”在实际描述中，有些人可能不同意这种方法，但我真的很喜欢它，因为它很模块化，我可以从不同的工作流中复制一个工具，它就会。

<details>
<summary>Original English</summary>

**Liam**: I'm sure we're all familiar with the system prompt being that we're at AI engineer conference. uh in here the in the system message that's where you would normally put all of your different stuff but I like to make it a little bit more modular by I only put my like email prompts like oh don't use m dashes don't do whatever in the actual description which maybe some people would disagree with that approach I really like it because it's modular I can copy a tool from different workflows and it will just

</details>

**Liam**: 嗯，从添加工具的角度来看，我相信大家现在可能已经领先我了。嗯，这很好。如果你像我一样又落后了，你可以进入这个 **Notion** 页面，在里面你可以“作弊”复制，然后你只需 **Command + V** 就能粘贴所有内容。

<details>
<summary>Original English</summary>

**Liam**: Um I'm sure people are probably ahead of me now in from a tool perspective of adding them. Uh which is good. And if you fall behind like I am here again you can come into this notion page and inside of here you can cheat copy and then you just command V and it pastes everything in.

</details>

**Liam**: 当我在这里的时候，这样你们就不必坐着看我写一个巨大的提示词，并且拼错每个单词。嗯，我将在这里粘贴我昨晚写的提示词，并在你们填写这些工具的时候，大致讲解一下它的结构。

<details>
<summary>Original English</summary>

**Liam**: And while I have this here so that you guys don't have to sit through me writing a giant prompt and spell every spelling everything incorrectly. Um, I'll just paste in the prompt I wrote last night right here and kind of walk through the uh the anatomy of it a little bit while you guys fill out those tools.

</details>

**Liam**: 在 **n8n** 的所有不同框中，你都可以随时将其展开到全屏，这会使操作更简单。所以，我相信我们都知道，在**系统提示词**中，你需要告诉 **AI** 它是谁以及它的目的是什么。我喜欢保持它们非常简单，并且只在需要时添加内容。

<details>
<summary>Original English</summary>

**Liam**: And all of the different boxes in NADN, you can always expand them up to be full screen, which makes it a little easier. So, as I'm sure we're all aware, you want to tell the AI in the system prompt essentially who it is and what its purpose is. I like to keep them pretty simple and just add stuff as I need to.

</details>

**Liam**: 所以，如果一个工具没有被调用，或者某些事情没有发生，你只需进来告诉它改变。所以我给了它一个简短的行为列表，比如“提问而不是胡说八道”之类的。这真的很重要。我相信我们都经历过这种情况。你不会想把一个你知道的潜在客户名字发送给一个真正的潜在客户。那真的很尴尬。

<details>
<summary>Original English</summary>

**Liam**: So if a tool isn't being called, something's not happening, you just come in here and you tell it to change. So I gave it a brief list of how to behave, like ask instead of hallucinating, all that kind of stuff. And this is really important. I'm sure we've all experienced this. You don't want to send a uh you know two lead name to an actual uh um prospective client. That's really embarrassing

</details>

**Liam**: 我们在这里说：“不要使用**占位符**”。嗯，而且 **LLM** 通常不知道时间。所以你会说“今天的邮件是什么？”，它会说“你在 2023 年 1 月没有任何邮件。”你会想“什么？”所以如果你使用那个方便的函数，为什么它又变回去了？那需要是一个表达式。

<details>
<summary>Original English</summary>

**Liam**: which we say right here. Don't use the placeholders. Um and also LLMs usually don't know the time. So you'll say what's today's emails and it'll say you have no emails on January 2023. And it's like what? So if you use that uh convenience function here which why did that change back that needs to be an expression

</details>

**Liam**: 然后你会看到日期时间，它会显示它在侧面评估为这个。有没有人有问题？我知道我有点跳来跳去。我们还在努力放置工具吗？好的，很好，很好，很好。

<details>
<summary>Original English</summary>

**Liam**: and then you'll see date time and it'll show this evaluates to this on the side. Any questions from anyone? I know I've been jumping around a little bit. We still all working on getting tools placed. Okay, good. Good. Good.

</details>

**Liam**: 然后我就会“作弊”了。我只是要复制这些。我想我可以直接拖动它们，但还是粘贴在这里。一个很好的小技巧是，当你设置一个东西时，先设置第一个，设置好你的身份验证，然后，与其新建一个并设置值，不如直接复制粘贴它，因为那样字段就已经设置好了。嗯，这会节省一些时间，不必每次都点击那个小按钮。

<details>
<summary>Original English</summary>

**Liam**: And then I will cheat. And I'm just going to copy these. I guess I could have dragged them, but paste them here. A good tip uh when you're setting up something, set up the first one. get your authentic authentification set up and then instead of making a new one and setting the values, just copy and paste it because then that field is already set inside of it. Um, saves a little bit of time having to click the the little button every time.

</details>

**Liam**: 然后另一个小小的提示技巧是，当你在这里设置这个时，这里有一个按钮，上面写着“添加描述”。然后它会做它说的事情。它会给那个字段添加一个描述给 **AI**。你有时会注意到，可能有一个字段，它选择了错误的东西。例如，在 **Gmail** 线程 **ID** 中，它可能会放置消息 **ID** 或类似的东西。你可以在这里添加一个提示词，你可以想写多长就写多长。成吨的行都可以，没关系。所以如果出现它传递了错误的值或其他情况，这只是另一个你可以引导它走向正确方向的框。

<details>
<summary>Original English</summary>

**Liam**: And then another uh little prompting trick is inside like when you set this here you there's this button here that says add a description. And then this does what it says. It adds a description to that field with the AI. You'll notice sometimes there'll be a field that maybe it picks the wrong thing. Like for instance in Gmail thread ID, maybe it'll put the message ID or something like that. You can add in a prompt here and you can make this as long as you want. Tons and tons of lines and it's fine. So if something happens where it passes the wrong value or something, this is just yet another box where you can steer it to go into the right direction.

</details>

### n8n 工具描述与凭证管理

**Liam**: 你还可以做一些其他事情，比如，呃，让我找一个比线程 **ID** 更好的例子。也许。哦，一个很好的例子，一个很好的例子是，当在 **Google Calendar** 中创建事件时，名称，呃，让我们看看它在哪里？`summary` 实际上是标题，这对于所有使用 **Gmail** 的人来说都非常令人困惑。我们可能应该把它的名字改成标题，但我们只是遵循了 **Google** 的 **API** 名称。当你设置这个时，你应该做的是添加一个描述，并说“这是事件的标题”，因为 `summary` 当然只会放置事件的摘要，但这会告诉它这是标题。你甚至可以做得更好，点击它，你会看到这里自动生成的键。你可以将它从 `summary` 更改为仅仅是 `title`，然后 **AI** 就会进去从那里填写标题。

<details>
<summary>Original English</summary>

**Liam**: Something else you can do if something like uh let me find a better example than thread ID maybe. Oh, a great example great example is when creating an event in Google calendar, the name of the uh let's see where is it? summary is actually the title which is extremely confusing even for all the humans using Gmail. We should probably change the name of this to title, but we just followed what Google's um API names were. When you set this, what you should do is add a description and say this is the title of the event because summary, it would just put a summary of what the event is, of course, but this tells it this is the title. You could do even one better than that and click this and you see the automatically generated key right here. You can change it from summary to just a title and then AI will go in and fill title from there.

</details>

**Liam**: 现在我要测试一下。看看它是否工作。我有一些字段没有填写。

<details>
<summary>Original English</summary>

**Liam**: Now I'm going to test it. See if it's working. I have some fields that aren't filled in.

</details>

**Liam**: 无法访问凭证。好的。

<details>
<summary>Original English</summary>

**Liam**: Does not have access to the credential. Okay.

</details>

**Liam**: 有时当你在一个项目内部工作，并且你在项目内部创建了一个凭证时，记住项目是侧边栏上的这些东西，你会收到一个错误，说它没有访问权限，这真的很令人困惑，因为它看起来有。如果你遇到这种情况，你只需回到你的主页，然后在凭证中，你可以共享它们。所以选择共享，然后你将它与项目共享。

<details>
<summary>Original English</summary>

**Liam**: Sometimes when you're working inside of a project and you make a credential inside of the project, remember projects are these things on the sidebar, you'll get an error saying it doesn't have access, which is really confusing because it looks like it does. If you ever run into this, all you need to do is go to your home and then in credentials you can share them. So say share and then you share it with the project.

</details>

**Liam**: 看，又是双刃剑的一个例子。你正在保留它。嗯，好的，这个已经被它困扰了。

<details>
<summary>Original English</summary>

**Liam**: See another example of double-edged swords where you're keeping it. Um okay, this one's already hounded by it. All

</details>

**Liam**: 好了。现在我的缩放让这有点奇怪，但是当我们询问它时，我们可以问“我今天的日程表上有什么？”我们可以确切地看到它使用了哪些工具。它使用了“获取多条消息”。

<details>
<summary>Original English</summary>

**Liam**: right. And now my scaling is making this a little funny, but When we ask it, we can what's on my calendar for today. We can see exactly what tools it used. It's used get many messages.

</details>

**Liam**: 然后如果我们专门点击那个节点，我们可以看到它的确切输出。在底部，我们还有所有发生事件的详细日志。所以“获取多条消息”，搜索字段中的输入是 26408 之后和明天之前。然后在消息中，我们只是得到了这些内容的摘要，这让我很担心，因为外面排了很多人。外面排了很长的队。也许你们来得早。

<details>
<summary>Original English</summary>

**Liam**: And then if we click into that node specifically, we can see the exact output from that. And in the bottom here we have detailed logs of everything that happened as well. So get many messages. The input in the search field was after 26 408 and before tomorrow. And then in the message we just got a summary of what these are which this was me worrying because was a lot of people stuck in the line outside. There's a big line out there. Maybe you guys got in early.

</details>

**Liam**: 每个人都到了可以和它聊天的地步了吗？还是我们还在放置工具？我们都准备好了。好的，太棒了。那么现在，我测试它时已经有点紧张了，因为我的真实账户。

<details>
<summary>Original English</summary>

**Liam**: Is everyone at this point where they're able to chat chat with it or are we still putting tools? We're all right. All right. Great. Then at this point, I'm already a little nervous testing this with my real account because

</details>

### 人机协作（Human-in-the-Loop）实现

**Liam**: 我不想不小心发送邮件给任何人，或者不小心回复，对吧？我相信你们也会想，我不想说“发送邮件”就让它自动发送。这几乎是今天演示的全部重点，我们让添加**人机协作**变得如此简单，大大提高了安心程度。

<details>
<summary>Original English</summary>

**Liam**: I don't want to send an email to anyone by accident or reply by accident, right? And I'm sure you guys are like, I don't want to say send an email and just have it do it automatically. And that's pretty much the whole point of today's presentation is we made it so so easy to add uh a lot of peace of mind here.

</details>

**Liam**: 所以，我们认为任何具有**破坏性**或**敏感性**的操作，我们都可以添加一个**人工审核**步骤。让我们看看，那将是“发送电子邮件回复”。我只是把它们拖开。发送电子邮件。创建事件，然后我会说“归档电子邮件”会是界限。我将允许它归档我的电子邮件。如果我错过了一封邮件，那不是什么大问题。

<details>
<summary>Original English</summary>

**Liam**: So everything that we would consider like destructive or sensitive, we can add a human review step. And let's see, that would be send an email reply. I'll just drag them to separate them. Send an email. create event and then I would say archive email would be borderline. I'm going to let it archive my emails. If I miss an email, not that big of a deal.

</details>

**Liam**: 所以现在你只需在这个分支上，这里有一个垃圾桶和一个加号。如果你按下加号按钮，它会弹出**人工审核**，你可以使用我们正在使用的聊天平台。我们正在使用原生的 **n8n** 聊天。

<details>
<summary>Original English</summary>

**Liam**: So now all you do on this branch right here, there's a trash can and a plus. If you press the plus button, it brings up the human review and you can just use the chat platform you're we're using. We're using the native NAN chat.

</details>

**Liam**: 然后这会在这里创建一个小小的**人工审核步骤**。现在它是不可能的。它无法通过这一层。它不能不通过这个聊天就使用这个工具。

<details>
<summary>Original English</summary>

**Liam**: And then this makes this little human review step right here. And now it is not possible. It just cannot get past this layer. It can't use this tool without going through this chat.

</details>

**Liam**: 我们可以给它一些选项，比如“批准”按钮会怎么说。我们可以把它改为“发送”。嗯，我们也可以添加一个“不批准”或“不允许”按钮。然后我们可以阻止用户输入。但我喜欢让它关闭，因为这样你就可以直接回复它，回复消息就会拒绝。现在我们可以看看这个会是什么样子，然后说“发送一封测试邮件给”。

<details>
<summary>Original English</summary>

**Liam**: And we can give it options like what the approve button would say. We can change this to say send. Uh and we can also add a disprove uh disallow button. And then we can block user input. But I like to leave it off because then you can just respond to it and responding to the message will deny. And now we can see what this looks like and say uh send a test email to

</details>

**Liam**: 希望它能听懂。我们在它点击时收到了一个错误。我们可以看到它去使用了，但我们收到了一个错误。“聊天触发器中的响应模式必须设置为使用响应节点。”另一个小技巧是，很多人看到红色弹窗时会说“天哪”，如果你读一下错误信息，它通常会告诉你问题出在哪里。嗯，老实说，工程师们在编写这些消息上付出了很多辛苦的工作，或者现在 **Claude** 是怎么做的。但让我们看看。“聊天触发器中的响应模式必须设置为”。所以，在聊天触发器内部，

<details>
<summary>Original English</summary>

**Liam**: hopefully it listens. And we got an error when it hit it. We can see it went and used it, but we got an error. Response mode in the chat trigger must be set to using response nodes. Another tip, a lot of people really they see something red pop up and like, oh my gosh, if you read the error, it usually tells you what the problem is. Uh, honestly, and a lot of painstaking work goes into the engineers write these messages themselves or maybe how's Claude do it these days. But let's see. Response mode in the chat trigger must be set. So, inside of the chat trigger,

</details>

**Liam**: 让我们看看，在选项下，有一个**响应模式**。默认情况下，它设置为**流式传输**。你会看到消息在聊天屏幕中一次一个词地返回。但是为了让聊天节点工作，我们需要将它设置为**使用响应节点**。这基本上就是它所说的。它不是直接从 **LLM** 流式传输回来，而是我们使用屏幕上的节点控制哪些消息发送给它。所以那将是像这个人工审核这样的节点。

<details>
<summary>Original English</summary>

**Liam**: let's see, under options, there's this response mode. By default, it's set to streaming. And you'll see that the words come back one at a time in that chat screen. But for the chat nodes to work, we need to set it to using respond nodes. And that just essentially does what it says. Instead of it streaming back right from the LLM, we are controlling what messages go to it using nodes on the screen. So that would be a node like this human review.

</details>

**Liam**: 我们也只是在这里有这些常规的聊天节点，你可以直接发送一条消息。那错了。

<details>
<summary>Original English</summary>

**Liam**: We also just have these um regular chat nodes in here where you can just send a message. That's the wrong one.

</details>

**Liam**: 我会展示给你们看，因为它非常酷。聊天工具，你可以在聊天中直接用工具发送消息，你可以用它做一些很酷的事情。但是，当我们设置好之后，它就不会回复，除非是通过聊天节点。所以我们必须在 Agent 之后也添加一个聊天节点。

<details>
<summary>Original English</summary>

**Liam**: I'll show you this because it's very cool. chat tool where you can just send a message in the chat with a tool which you can do some cool stuff with. Uh but then now we actually when we set that we need to also it won't respond at all unless it's through a chat node. So we have to add a chat node after the agent as well.

</details>

**Liam**: 发送消息。现在你可以看到那是空白的。嗯，我想这是 **JSON** 点。嗯，消息。可能是聊天输出。我们还是测试一下。

<details>
<summary>Original English</summary>

**Liam**: Send a message. And right now you can see that's blank. Uh I think this is JSON dot uh message. It might be chat output. We'll test it though.

</details>

**Liam**: 说“你好”。它会回来。输出是什么？它现在卡住了。这是另一种演示综合症。好的，我要停用这个节点。发送消息。所以，有测试数据总是有益的。

<details>
<summary>Original English</summary>

**Liam**: Say hi. And it'll come back. And what's the output? It's hanging now. That's another demo syndrome. Okay, I'm going to deactivate this node. Send a message. So, it's always good to have test data in there.

</details>

**Liam**: 我想问题出在这里是未定义的。好的，是输出，不是消息。所以，我们只需将它拖到“发送消息”即可。

<details>
<summary>Original English</summary>

**Liam**: I think the problem was this was undefined. Okay, it's output. It's not message. So, then we can just drag this right to send a message.

</details>

**Liam**: 现在，我们可以再次测试它，确保我们收到了消息。然后我们可以看到它不会流式传输回来，它会一次性发送回来。这有点道理吗？我知道这会让人困惑。你必须始终用节点回复。

<details>
<summary>Original English</summary>

**Liam**: Now, we can test it again and make sure we get a message back. And then we can see it doesn't stream back. it sends it back in one chunk. Does that kind of make sense? I know that can trip people up. You just have to respond with nodes at all time.

</details>

**Liam**: 你还可以用它做一些很酷的事情，比如设置 **if** 分支，对吧？所以你可以在那条消息中用 **if** 分支检查一些东西，并根据不同的条件进行回复。但我们现在不需要担心这些。我们只是用它回复。现在这又会奏效了。我们可以回到测试并说“发送一封测试邮件给”。

<details>
<summary>Original English</summary>

**Liam**: Something else you can do cool with that as well is set like if branches, right? So you can check something in that message with an if branch and have different conditions of how to respond. But we don't need to worry about that right now. We're just responding with that. And now this will work again. We can go back to testing and say send a test email to.

</details>

### 人工审核流程优化与调试

**Liam**: 好了。现在我们可以在聊天中看到，如果我们能把它放大，Agent 想要调用“发送电子邮件”。如果你在手机上看到这个，你可能会说“好的”，因为显然这并不能向我们展示任何东西。

<details>
<summary>Original English</summary>

**Liam**: All right. And now we can see here in the chat if we can scale this up the agent wants to wants to call send an email. And if you're looking at on that on your phone you're probably going to say okay and because obviously that's not really showing us anything.

</details>

**Liam**: 所以我们要按下“拒绝”，因为我想看我的消息。当我们点击**人工审核节点**时，现在我们有了那个例子，我们可以看到它来自哪里。在这条消息中，Agent 想要调用 `tool.name`。在这个字段中，我们可以使用这个工具，嗯，便捷函数。

<details>
<summary>Original English</summary>

**Liam**: So we are going to press decline because I want to see my message. And when we click into the human review node, now that we have that example, we can see where that came from. In this message, the agent wants to call tool.name. In this field we can use this tool um convenience function

</details>

**Liam**: 通过说 `money sign tool.parameters`，**n8n** 中的每个字段在底层都被称为参数。如果你遇到 `object object`，在 **JavaScript** 中工作的人会知道那是什么意思。但你可以说 `toJSONString`，作为一个小技巧，来看看输出是什么。甚至只是这里也会告诉你你需要知道的信息，以进行人工审核步骤。但显然这有点难看。所以我宁愿这样做，说。

<details>
<summary>Original English</summary>

**Liam**: by saying money sign tool dot and then parameters which every field in nadn that's called the parameter under the hood. If you ever get this object object the people who work uh in JavaScript will know will know what that's about. But you can say two JSON string as a tip to see what the output is. And even just this right here would be would tell you the information that you need to know to the human review step. But obviously that's kind of ugly. So what I would rather do is say to

</details>

**Liam**: 并且这可以表示点消息或两个，对吧？我们不再需要这个 `toJSONString`。来自。嗯，不是来自主题。`tool.parameters.subject`，消息，`tool.parameters.message`。现在我们可以看到，呃，Agent 的那条消息将是我们实际上可以合理批准或拒绝的消息。我实际上会把它改名为“Agent 想要发送一封电子邮件”。太棒了。

<details>
<summary>Original English</summary>

**Liam**: and this can say dot message or two, right? And we don't need this to JSON string anymore. from. Well, not from subject tool dot parameters dot subject message tool dot parameters message. And now we can see that uh the agent that message will be something we can actually reasonably approve or deny. And I will actually just rename this to the agent wants to send an email. Great.

</details>

**Liam**: 现在我真的要发布这个，这样我就可以在聊天中心看到它。我将去那里。然后我再说一次“发送一封测试邮件给”。我实际上，呃，我无法打开我的电子邮件，不幸的是，不管怎样。

<details>
<summary>Original English</summary>

**Liam**: And now I'm actually going to publish this so that I can see it in the chat hub. I'll go over here and I'll say again send a test email to I'll actually uh I can't open my email unfortunately whatever

</details>

**Liam**: **mcg**。它返回说 Agent 想要发送一封电子邮件，并且完成了所有这些，我们可以看到它，并且我们可以发送或拒绝它。你也可以通过简单地回复来拒绝它。所以我们可以说“我宁愿消息是 Markdown 格式的”。编写一封包含不同 **Markdown** 功能的电子邮件。

<details>
<summary>Original English</summary>

**Liam**: mcg and it comes back and says the agent wants to send an email and does all of that and we can see it and we can send it or decline it. And you can also deny it by just responding. So we can say I'd rather the uh the message be markdown. Write an email that has different markdown features.

</details>

**Liam**: 然后它会拒绝，并且它基本上会再试一次。它没有听 Markdown 的指令，因为它更多地听取了工具的描述。但是你可以看到它是如何工作的。然后我可以发送这封垃圾邮件给自己。好了。

<details>
<summary>Original English</summary>

**Liam**: And then that denies it and it'll pretty much just try again. It didn't listen to the markdown because it listened to the tool uh description much more. Uh but you can see how that works. And then I can go ahead and send myself this junk email. And there we go.

</details>

**Liam**: 希望这能展示它有多么强大和酷，因为没有通过它，那个工具就无法被调用。它只是在那里挡路。我们 **n8n** 制造了那一层，以便在中间拦截它。其中一个非常酷的事情是，它甚至不知道那里有一个**人工审核步骤**。所以如果你的工具工作正常，你添加了一个人工审核步骤，它不会调用那个**人工审核步骤**。它调用的是工具，我们正在拦截它。嗯，就像 **AI** 中的很多事情一样，这也是一把双刃剑，因为 **AI** 通常会，嗯，对此有所警惕。你知道，更聪明的 **AI** 通常不会在未经询问的情况下发送电子邮件，除非你明确告诉它这样做。

<details>
<summary>Original English</summary>

**Liam**: Hope that kind of shows how powerful and and cool this is because that is not able that tool can't be called without going through that. It's just in the way. We at NAND made that layer to just intercept it in the middle. And one of the really cool things about it is it doesn't even really know that there's a human review step there. So if you have your tools working and you add a human review step, it's not calling that human review step. It's calling the tool and we're intercepting it. Uh like a lot of things in AI, that's also a double-edged sword because AIS will typically be um wary of that. You know, AIs that are a little smarter, they typically won't just send an email without asking unless you specifically tell it to.

</details>

**Liam**: 所以我发现，有时在描述中，在这些提示词中，我会说“这不会自动发送。不要害怕发送消息。消息中有**人机协作**。”这通常会解决问题，因为它会觉得“好的，它不会直接被发送出去。它会被使用，对吧？”

<details>
<summary>Original English</summary>

**Liam**: So, what I found is that sometimes in the descriptions uh in these prompts, I'll say this won't send automatically. Don't be afraid to send a message. Message there is a human in the loop. And that usually fixes it because it'll be like, okay, it won't just be blasted out. It will be used, right?

</details>

**Liam**: 所以如果你像我一样有时很懒，你实际上可以把多个工具放在一个**人机协作**下。所以我们可以把像草稿之类的也放在这里，然后它会拦截两者，而不需要做任何改变。只是字段不同，我们为此创建了一个自定义消息。所以我们要写，我们要添加一个不同的。但懒惰仍然盛行。所以我要尝试一些东西。我们会看看演示综合症是否在这里伤害我们。

<details>
<summary>Original English</summary>

**Liam**: So you can also if you're really lazy like I am sometimes you can actually put multiple multiple tools under one a under one human in the loop. So we could put like the draft one under here as well and then it will intercept it for both without anything having to change. It's just the fields are different and we made a custom message for it. So, we're going to write we're gonna add a different one. But laziness still prevails. So, I'm going to try something. We'll see if the demo syndrome uh hurts us here.

</details>

**Liam**: 我要说“添加**人机协作**，就像它在‘发送邮件’上一样”，这是 **n8n AI Builder**。让我确保这个提示词是好的。添加**人机协作**，就像它一样。嗯，命名参数和所有内容以匹配工具。

<details>
<summary>Original English</summary>

**Liam**: And I'm going to say add human in the loop just like it is on send an email to the and this is the NAD AI builder. Let's see. Let me make sure this prompt is good. Add human in the loop just like it is. uh name the params and everything to match the tools.

</details>

**Liam**: 我发现非常有帮助的一点是，如果你有很多重复的东西，你可以先创建一个，然后说“好的，也在那里做这个”。你就不必真的去点击。它实际上会比你更快地完成。

<details>
<summary>Original English</summary>

**Liam**: I found what helps a lot is you if you have a lot of things that repeat, you can make one and then just say, "Okay, do this over there as well." And you don't have to really click through. It'll actually do it faster than you're able to.

</details>

**Liam**: 我们在云版和企业版上都有这个功能。自托管版还没有。我们正在努力实现，但我们刚刚发布了一个 **MCP** 功能，你可以将它连接到 **Cloud Code** 或任何你拥有的 Agent，它可以通过 **CLI** 与 **MCP** 完成相同的功能。

<details>
<summary>Original English</summary>

**Liam**: And we have this on um cloud and enterprise. It's not on self-hosted yet. We're working on getting it there, but we did just release an MCP feature uh where you you can hook it up to cloud code or whatever agent you have and it can do the same functions that this has just through the CLI with the MCP.

</details>

### n8n 的企业级特性与高级应用

**Liam**: 这成功了吗？看起来可能成功了。正在验证工作流。我们可以点击进去。看起来它在工作。好的，太棒了。所以现在我要发布它。让我们说我将回到**聊天中心**，因为在那里看起来更美观。

<details>
<summary>Original English</summary>

**Liam**: And did this work? It looks like it might have. Validating the workflow. We can click in. It looks like it's working. Okay, great. So now I'm going to publish this Let's say I'll go back to chat hub because it's a little nicer to see here.

</details>

**Liam**: 嗯，为今天的午餐添加一个日历邀请，中午，并发送电子邮件。天哪，我不知道我自己的电子邮件。问他是否想去。发送。看起来不错。想要创建一个日历事件。午餐。哦，那有点难看。好的，所以我要创建它，因为它不会改变实际内容。但我们可以修复它。让我们把它做得更好。

<details>
<summary>Original English</summary>

**Liam**: Um, add a calendar invite for calendar for lunch today noon and email. Oh my gosh, I don't know my own email. asking if he wants to go. Send. Looks good to me. Wants to create a calendar event. Lunch. Oh, that's kind of ugly. Okay, so I'm going to create it because it won't change what's actually in there. But we can fix that. Let's make it better.

</details>

**Liam**: 这使得测试变得非常方便，因为你可以创建**虚拟事件**，并且实际上可以看到它是否发送给了错误的人或做了错误的事情，你只需拒绝即可。嗯，这样你就不会不小心做错任何事。

<details>
<summary>Original English</summary>

**Liam**: And this makes it so nice for testing because you can do dummy events and actually see if it's going to the wrong person or doing the wrong thing and you can just decline it. Uh so you know you won't do anything by accident.

</details>

**Liam**: 嗯，还记得我一开始说过你可以看到哪里出了问题等等吗？在这个**执行标签页**中，你将看到所有执行的次数。嗯，它用烧瓶标记了测试的那些，但我们会看到这里来自聊天的那个执行，我们可以看到它进入了**人机协作**，然后它创建了事件。如果你点击“复制到编辑器”，我们现在可以在这里处理这些数据。所以，如果我们点击工具，

<details>
<summary>Original English</summary>

**Liam**: Um remember in the beginning when I said oh you can see what goes wrong and everything. In this executions tab you will see all of the times it was executed. uh it marks the test ones with the flask, but we'll see that that execution from chat right here, we can see it went into the human in the loop and then it went down and created the event. If you click copy to editor, we can now work with this data in here. So, if we click into the tool,

</details>

**Liam**: 我们看到这些日期在这里非常难看。现在，这就是 **JavaScript** 真正派上用场的地方。如果你不懂 **JavaScript**，你可以直接让聊天帮你格式化这个日期。但我们可以直接说 `toDateTime`，然后点 `format`。呃，我想我可以做 `ddt`。不能转换。哦，为什么不行？让我们看看。

<details>
<summary>Original English</summary>

**Liam**: we see these dates that are super ugly here. And now, this is where the JavaScript really comes in handy. If you don't know JavaScript, you can just go ask a chat to tell you format this date for me. But we can just say to date time and then dot format uh and I think I can do dd t cannot convert. Oh, why not? Let's see.

</details>

**Liam**: 天哪，我试图把“午餐”转换成日期时间。我们，呃，我们不能责怪演示运气不好。好的。然后看，现在它知道这是兼容的。所以当你按下点 `to date time` 时，它就会自动出现。如果我们再次按下点，`format` 就会自动出现。**n8n** 的优秀工程师们在这里为我们添加了文档。所以我们可以看到所有这些东西的作用，你甚至可以说像 C 和减号，它们会给你展示代码示例等等。进去阅读它非常好。我知道我们现在都想问 **Claude** 所有事情，但如果你阅读屏幕上的内容，我保证它非常有帮助。但如果我们要格式化这个，并说大写 D。

<details>
<summary>Original English</summary>

**Liam**: Oh my god, I tried to convert lunch to a date time. We I we can't blame uh the demo luck for that one. Okay. And then see now it knows that this is uh compatible. So when you press the dot to date, time just already comes up. And if we press the dot again, format already comes up. And the very nice engineers at NAN went in and added docs for us in here. So we can see what all these things do and you could even say like C and minus they show you code examples and everything. It's it's very nice to go in and read it. I know we're tempted to just go ask Claude everything right now, but if you read the things on the screen, I promise it it is very helpful. But if we'll format this and say capital D,

</details>

**Liam**: 我觉得。是的，就这样。很好。如果你再加几个 D，它会变得更好。D，然后是 TT。如果你想知道这是什么，这只是 **Luxon** 日期函数。它只是我们使用的日期库。这就是这个 `ddt`。我写过很多次了，所以记得，但你只需问 **Claude** 怎么为 **n8n** 格式化，它就会告诉你。所以现在看起来好多了。这样我们批准起来就容易多了，不必阅读 **UTC**，呃，一个时间戳。所以我们会再次发布它，然后说“把晚餐放到日历 47 上”。

<details>
<summary>Original English</summary>

**Liam**: I think. Yeah, there we go. Nice. If you add a couple more D's, it just becomes even nicer. D and then T T. And this is, if you're wondering what this is, this is just uh the Luxon date functions. It's just the date library we we use is what this ddt I just have written it enough times to remember but you can just ask uh claude to format it for nad and it'll do it. So now that looks much better. That's much more much easier for us to approve without having to read a UTC uh a time stamp. So we'll publish it again and say put dinner on the cal47.

</details>

**Liam**: 好了。它修好了。我们可以看到调整和玩转所有东西是多么容易。这都说得通吗？有什么问题吗？不一定非要与主题相关。哦，我想有封邮件来了。

<details>
<summary>Original English</summary>

**Liam**: There we go. It's fixed. And we can see how easy that is to go in and tweak and play around with everything. Does this all make sense here? Any questions? It doesn't have to be specifically related. Oh, and there's an email coming through, I guess.

</details>

**观众**: 只有一个月的。

<details>
<summary>Original English</summary>

**观众**: Only a month.

</details>

**观众**: 只有一个月的。

<details>
<summary>Original English</summary>

**观众**: Only a month.

</details>

**观众**: 哦，真的吗？只有一个月的？你选择的时候是在 **Cloud Pro** 上吗？是的，当我选择它时，我只能选择月。

<details>
<summary>Original English</summary>

**观众**: Oh, really? Only a month. Are you on cloud pro when you select it? Yeah, when I select it, I can only for month

</details>

**Liam**: 我现在就去创建一个新的，或者稍后检查。我创建一个新的，这样我就不会泄露如何创建优惠券。

<details>
<summary>Original English</summary>

**Liam**: I will go and make a new one right now or check after I'll make a new one so I don't leak how to how to create coupons.

</details>

**观众**: 是的。所以，我会把它放上去，我会让它保持 24 小时。然后我再移除它。

<details>
<summary>Original English</summary>

**观众**: Yeah. So, I'll put it up I'll leave it up for 24 hours and then I'll remove it.

</details>

**观众**: 对不起。

<details>
<summary>Original English</summary>

**观众**: Sorry about that.

</details>

**Liam**: 有趣的是，我实际上在 **n8n** 中制作了整个折扣系统，就像我们 **n8n** 的**优惠券生成器**完全是在 **n8n** 中创建的。它抽象了我们所有不同的优惠券系统，涵盖了商品、企业、赠品、云等等。它都有一个单一的入口点，通过 **n8n** 的 **REST API** 运行，并且它拥有所有的，嗯，审计日志等等。这真的很有趣，我只用了大约六个小时就构建了整个系统。所以，它真的是非常强大的东西。

<details>
<summary>Original English</summary>

**Liam**: Fun thing. I actually made an entire discount system like the our coupon generator at NADEN is created entirely in NANE and it abstracts all of the different coupon systems we have across merch enterprise giveaway stuff uh cloud it all has a single entry point with a REST API that goes through Nadn and it has all the um uh audit logs and all that it's really interesting and I built the entire system in like six hours. So, it's it's really really powerful stuff.

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**观众**: Yep.

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**观众**: Yeah.

</details>

**观众**: 哦，你介意等一下麦克风吗？

<details>
<summary>Original English</summary>

**观众**: Oh, did you mind waiting for the the mic?

</details>

**观众**: 谢谢。呃，你提到了 **MCP 服务器**。呃，因为，嗯，直到最近，**GitHub** 上都有一个非官方的，我一直在用，而且它和 **Cloud Code** 运行得很好。呃，我只是想问你能不能多分享一些关于你们原生的 **MCP 服务器**的信息，以及它是否可用？

<details>
<summary>Original English</summary>

**观众**: Thank you. Uh you mentioned MCP server. Uh because um up till late there was an unofficial one on GitHub that I've actually been using so far and it's been working great with cloth code. Uh I'm just can you share a little bit more about the native MCP server that you have and if it's available?

</details>

**Liam**: 是的，绝对可以。所以，呃，这真的很令人兴奋。嗯，你应该只需进入设置，就在这里，**实例级 MCP**。如果你点击这里，你只需启用它并授予它工作流访问权限。所以，嗯，让我们看看我们这里有什么。已发布或具有 **Webhook**、表单计划或聊天触发器的工作流。所以那应该是我们的。

<details>
<summary>Original English</summary>

**Liam**: Yeah, absolutely. So, uh, this is really, really exciting. Um, you should just be able to go into settings and right here, instance level MCP. If you click in here, you can just enable it and give it access to workflows. So, um, let's see what we have here. Workflows that are published or have a web hook, form schedule, or chat trigger. So that should be ours.

</details>

**Liam**: 电子邮件和日历机器人已启用。你必须按工作流授予访问权限。嗯，你也可以在这里这样做，然后说设置，在 **MCP** 中可用。这只是为了防止你连接到你的东西时，它不会不小心更改错误的工作流。它必须被启用。

<details>
<summary>Original English</summary>

**Liam**: Email and calendarbot enable. You have to give access per workflow. Um which you can do up here as well and say settings available in in MCP. That's just so that if you connect it to your thing, it won't go and change the wrong workflow by accident. It has to be enabled.

</details>

**Liam**: 现在在那个 **MCP** 嗯，你可以说连接的客户端，呃，或者你是如何连接的，连接详情，你只需输入你的服务器 **URL** 和 **OAuth**。所以，呃，让我们看看在云端，我几乎不敢打开我的云端，但我们是云端的官方连接器。所以你可以直接说连接 **n8n**。你输入那个 **URL**。它会通过 **OAuth** 连接。你只需点击登录。或者如果你，嗯，正在使用访问令牌，你可以在这里复制它，然后你，呃，将复制这个，粘贴到你的配置文件中，并用这个替换你的访问令牌。它做的事情与那个 **MCP** 完全相同，只是我们没有必须与现有 **API** 合作的限制。我们直接构建了它。所以，它做所有相同的事情。我会说你可以两者都试试看，但我们的是会随着时间不断增加更多功能的。嗯，那回答了你的问题吗？我想我没有讲太多细节，但本质上它能够创建、读取、做所有这些。它实际上也能够执行。

<details>
<summary>Original English</summary>

**Liam**: And now in that MCP um thing you can say connected clients uh or how do you connection details you just put in your server URL in OOTH. So in in uh let's see in cloud I'm almost afraid to to open my cloud but we are a official connector in cloud. So you could just say connect nad. You put that URL in. It'll connect with OOTH. You just press log in. Or if you um are doing access token, you can copy that here and you uh will copy this, paste it into your configuration file and replace your access token with this. And it does all the same things that that MCP does, except we didn't have the limitation of having to work with the existing API we had. We built it right in. So, it does it does all the same stuff. I would say you can try both out and see, but ours is is going to be adding more and more over time. Um, that answer your question. I guess I didn't really go into that much detail, but essentially it's able to create, read, do all that. It's actually also able to execute.

</details>

**Liam**: 所以你可以对 **M** 说，你可以对 **Claude** 说：“运行我的电子邮件和日历机器人”，它会发送一条聊天消息给它，并且能够与它互动。所以这是 **Roman** 的 **MCP** 我认为不能做到的。

<details>
<summary>Original English</summary>

**Liam**: So you could say to M, you could say to Claude, "Run my email and calendarbot and it will send a chat message to it and it's able to interact with it." So that's something else I don't think uh Roman's MCP can do.

</details>

**观众**: 是的。所以，所以我们的 **MCP** 能够做到这一点。

<details>
<summary>Original English</summary>

**观众**: Yeah. So So that's something that our MCP is able to do.

</details>

**Liam**: 还有其他问题吗？也可以像刚才那样问一些随机问题，如果你有任何 **MCP** 相关的问题。好的。

<details>
<summary>Original English</summary>

**Liam**: Any other questions? It can just be a random question like that too if you have any MCP stuff. Yep.

</details>

**观众**: 哦，是的。对不起。谢谢。所以，嗯，假设我想构建一个公司范围内的工作流，对吧？我希望针对特定操作，从特定部门获取特定人员进行**人机协作**，如果这说得通的话。有没有办法记录和查看整个工作流的延迟情况？比如热图或日志，显示谁响应时间更长？

<details>
<summary>Original English</summary>

**观众**: Oh yes. Sorry. Thank you. So um assuming I want to build a a companywide workflow, right? And I want to have specific human in the loop from specific departments for specific actions if that makes sense. Is there a way that I can log and see where um the work work the whole workflow uh delays? So like a heat map or of logs of who takes longer to to to respond like that.

</details>

**Liam**: 谁响应时间更长？这是一个有趣的用例。嗯，我本来想说，我们的企业版方案中有很多**审计日志**功能，但这不会是内置的功能，但你可以用 **n8n** 来实现，因为会发生什么，呃，我很快就会展示给你们看。这仍然显示“等待中”，即使那不是真的。但我会说。

<details>
<summary>Original English</summary>

**Liam**: H who takes longer to respond? That's an interesting use case. Um I was going to say we have lots of we have like audit logging functionalities in our enterprise plans, but that wouldn't be something baked in, but it's something you can make with with NAD because what happens with this uh I'll I'll show you really quickly. This still says waiting even though that's not true. But I will say

</details>

**Liam**: 给同一个电子邮件地址发送一封电子邮件。做任何事，只是测试。所以如果我们。好的。所以现在发生的是这个工作流，那不是正确的东西。这个工作流进入了等待状态，你可以在这里看到它。然后一旦它恢复，它就会显示已完成。

<details>
<summary>Original English</summary>

**Liam**: send an email to that same other email. Do anything just test. So if we Okay. So now what happens is this workflow that's the wrong thing. This workflow goes into a waiting state and you can see it here. And then once it resumes it shows finished.

</details>

**Liam**: 你可以使用 **n8n** 节点来获取执行情况，它会显示何时开始等待，何时停止等待。嗯，然后如果你有 **Slack** 连接等，它会显示所有这些详细信息。所以这只是一个解析数据的问题。所以你可以用 **n8n** 独立地做这件事，将数据聚合起来。这是一个有趣的用例。我会记录下来。我会考虑一下，因为**审计日志**、**人机协作**是我们应该认真完善的东西。

<details>
<summary>Original English</summary>

**Liam**: You can use a N8 end node to get the execution and it will show when it started waiting, when it stopped waiting. Um, and then if you have your Slack connections and everything, it'll show all those details. So it would just be a matter of parsing that data. So it's something you can make separately in NAD, aggregate the data together. That's an interesting use case. I would I'll write that. I'll I'll think about that because audit logging human in the loop is is something that we should definitely really get polished.

</details>

**Liam**: 让我们看看。时间检查。现在是 11:50。我想再给你们展示一件事，特别是为了让你们做好准备，那就是将其转换为 **Slack**。对吧？所以，呃，如果我们，在做这个之前，还有没有人有其他问题？好的。所以，我只是在这里添加 **Slack**。这里所有人都使用 **Slack** 还是 **Google** 还是 **Microsoft Teams**？希望没有人使用 **Teams**。

<details>
<summary>Original English</summary>

**Liam**: Let's see. Time check. We're at uh 11:50. I want to show you guys one more thing specifically to set you guys up and that is converting this to slack. Right? So, uh if we take did anyone have any other questions that before we do that? Okay. So, I'll just add Slack here. Does everyone here use Slack or Google or Microsoft Teams? Hopefully, no one uses Teams.

</details>

**观众**: **Slack**。是的，我猜大部分是 **Slack**。

<details>
<summary>Original English</summary>

**观众**: Slack. Yeah, I figured it would be mostly Slack.

</details>

**Liam**: 所以，我个人使用的 Agent，嗯，我用的是 **Slack**。呃，它真的很棒。我甚至设置了它。所以，就在这里，我放了一个 **Slack** 节点，添加一个加载动画，那是一个跳舞的 **GIF**。然后在它回复之后，它会把那个东西移除。所以它甚至有一个加载指示器。呃，它真的很棒。你可以进去，然后用 **Slack** 替换触发器和这个响应，然后在这里做同样的事情，这些都通过 **Slack** 运行。

<details>
<summary>Original English</summary>

**Liam**: So, my personal agent I use for myself, um, I use Slack. Uh, and it's really nice. I even have it set up. So, right here, I put in a Slack node to add a loading animation, which is a GIF of a something dancing. And then at the end after it responds, it takes the thing away. So it even has like a loading indicator. Uh it's it's really nice. You can go in and just replace the trigger and this response with Slack and do the same thing here where these go through Slack.

</details>

**Liam**: 所以，这都和你在 **ChatHub** 上看到的一样。它在 **Slack** 中也能工作。不过，还有更酷的事情，或者取决于你认为什么更酷，我想，与其让它只在你发送消息时运行，想象一下如果我们只添加一个**计划触发器**。

<details>
<summary>Original English</summary>

**Liam**: So that all works the same way you saw on ChatHub. It would work in Slack. Something even cooler though, or depending on what you think is cool, I suppose instead of having this run just when you message it, imagine if we just added a schedule trigger,

</details>

**Liam**: 并让它每小时运行一次，然后在**计划触发器**中添加一个提示词，说“清理我的收件箱”，或者任何东西。然后它会每小时运行一次，执行这些操作，并且这些可以连接到 **Slack**，只是 ping 一个频道，所以它仍然是**人机协作**的，但只是在后台运行，你甚至不需要启动它。所以你可以想象所有在后台发生的事情。我用这个做什么呢？如果有一个 **GitHub** 问题或 **PR** 或其他什么，我会让它进来，我让它扫描代码，做任何事情，然后向人们发送消息，询问我阅读时想知道的细节，然后我就让消息发送给我，因为我不想在未经查看的情况下向同事或客户发送 **AI** 消息。

<details>
<summary>Original English</summary>

**Liam**: and had that run every hour, once per hour, and added a prompt there to the schedule trigger that says, "Clear my inbox," or whatever. ever then it would run once per hour do those actions and these can be connected to Slack to just ping a channel so it's still human in the looping for everything but just running in the background you don't even have to initiate it so you can imagine all the things in the background what I use this for if there's a GitHub issue or a PR or something I have it come in I I have it go through scan the scan the code do whatever and send off messages to people asking them details that I know I'll when I read through it and then I just have the message come to me because I don't want to AI message co-workers or clients or anything without seeing it first.

</details>

### 工作流的团队协作与无 UI 场景应用

**Liam**: 这说得通吗？是的。所有这些实际上都在这个 **Notion** 文档中作为下一步。我，呃，在下一步中，你可以给它**内存**，这样它就可以**持久化内存**。哦，抱歉，你几乎看不清，但如果你在 **Notion** 文档中，你可以看到你可以给它**持久化内存**，它会在不同会话中记住。嗯，我为你提供了设置这一切所需的所有东西，这是让你去操作并使其**自主化**的说明，你可以通过 **Slack** 与它聊天，但它也会每小时运行一次，并且所有都已设置好。嗯，所有这些都在这里供你实验和扩展，希望我已经很好地为你做好了准备，能够做到这一点。我们还剩下 10 分钟，嗯，与其开始下一个环节，我只想回答大家的问题，或者只是聊聊 **n8n** 的未来，你希望它变成什么样，或者任何类似的事情。所以任何问题，我都很乐意回答。是的。

<details>
<summary>Original English</summary>

**Liam**: Does that make sense? Yeah. And all of that is actually in this notion document as the next steps here. I uh in the next step you can give it memory so it can persist memory through oh sorry you can hardly see that but if you're in the notion document you can see you can give it persistent memory it will remember across sessions um I give you everything you need to set that up this is the instructions to go through and make it autonomous where you can still chat with it through Slack but it also runs hourly and has everything set up um and And that's all in here for you to experiment with and expand this past which hopefully I've set you up decently uh to be able to do that. We have 10 minutes left and um instead of starting the next thing I would just like to answer anyone's anyone's questions or just chat about what's coming next for NAN what you want it to be anything like that. So any questions I would be happy to take Yep.

</details>

**观众**: 我想问一下关于**人机协作**的执行问题。嗯，我的情况是一个自托管实例，我们对并发执行有**限制**。所以。

<details>
<summary>Original English</summary>

**观众**: I want to ask uh about the human in the loop executions. Uh my case is a self-hosted instance uh in which we have a limit on concurrent executions. So

</details>

**观众**: 我想问一下，嗯，等待中的执行是否算作正在运行的执行，因为，例如，如果你对并发执行有 10 个限制，你可能会。

<details>
<summary>Original English</summary>

**观众**: I was asking whether um waiting executions count as um running executions because for instance if you have a 10 limit on uh concurrent executions you may um

</details>

**观众**: 陷入困境，因为可能，呃，10 个用户，呃，只是不回复。是的。

<details>
<summary>Original English</summary>

**观众**: be become stuck because maybe uh 10 users um just don't respond. Yeah,

</details>

**Liam**: 我不知道这个问题的答案。我不认为会，但也有可能。我给你一些你可以做的事情，如果它确实算数，这会稍微减轻痛苦。你可以**限制等待时间**。所以，你可以说 10 分钟后，自动拒绝它，对吧？这样，如果有人错过了，它们就不会无限期地堆积起来。我知道有时就是会发生这种事。然后就不是“好吧，我们不可避免地会达到一个极限，让它耗尽”了。所以你可以设置一个时间限制。你知道答案吗？

<details>
<summary>Original English</summary>

**Liam**: I don't know the answer to that. I don't think it does, but it might. I'll give you something um you can do to if it does count, this will make it a little less painful. You can limit wait time. So, you can say after 10 minutes, automatically deny it, right? So, then you won't just have them piling up indefinitely if someone just misses it. I know like that just happens sometimes. And then it's not like okay we're inevitably going to hit a point where we have have this run out. So you can set a time limit. Do you know the answer to that?

</details>

**观众**: 我不知道。

<details>
<summary>Original English</summary>

**观众**: I don't know.

</details>

**Liam**: 是的。所以，嗯，我们肯定会和你跟进。我可以在会议结束后查清楚。

<details>
<summary>Original English</summary>

**Liam**: Yeah. So um we can follow up with you for sure. I can find out uh after the session.

</details>

**观众**: 谢谢。

<details>
<summary>Original English</summary>

**观众**: Thanks.

</details>

**Liam**: 还有其他问题吗？

<details>
<summary>Original English</summary>

**Liam**: Any other questions?

</details>

**观众**: 呃，嘿，是的，所以在**团队设置**中，你有多个可能在同一个工作流上工作的人，等等，审批流程是怎样的？你有没有类似**正常 PR 流程**的东西，有人必须进去批准更改，等等，以确保它符合上下文？

<details>
<summary>Original English</summary>

**观众**: Uh hey yeah so in a team setup where you have multiple people potentially working on the same workflow and so on what's the like approval process and do you have something similar to like a normal PR flow where you have someone who has to go in and approve the changes and so on to make sure it makes sense for the context right

</details>

**Liam**: 是的，所以你可以在触发器中设置，这正是它如此可定制的优点。所以你提到了 **Microsoft Teams**。哦。哦，如果你有团队。

<details>
<summary>Original English</summary>

**Liam**: yeah so you could have in the trigger and this is what's great about it all being so customizable so you said Microsoft Teams Oh. Oh, if you have teams.

</details>

**观众**: 不，但是。

<details>
<summary>Original English</summary>

**观众**: No, but

</details>

**Liam**: 在团队内部。是的。所以，你可以这样做：触发器，假设是 **Slack**，它可以获取用户 **ID**，然后回复者回复时，它只是引用用户 **ID** 来回复。但是，假设这个工具请求休假。显然，那不应该发给提问的人，对吧？所以，那个 **Slack** 消息你可以更改“收件人”字段，改为那个决策者或任何频道，然后他们可以按下批准或拒绝。这就是你问的吗？

<details>
<summary>Original English</summary>

**Liam**: inside of a team. Yeah. So, what you can do is the trigger, let's say it's Slack, it can take the user ID and then the one that responds it responds to it just references the user ID to respond to from there. But then, let's say that this tool is requesting vacation days. Obviously, that shouldn't go to the person who asked, right? So then that Slack message you can just change the two field to whoever that decision maker is or whatever channel that is and then they can press approve or deny. Does that is that what you were asking?

</details>

**观众**: 不太像。

<details>
<summary>Original English</summary>

**观众**: Not really.

</details>

**Liam**: 哦，对不起。那是什么？

<details>
<summary>Original English</summary>

**Liam**: Oh, sorry. What was the

</details>

**观众**: 但，但那是一个很好的补充。不。呃，我的问题更多是关于如何**管理工作流**。你有一个项目，有人最初设置了它，然后你邀请其他人加入你的团队计划，呃，他们也应该提供帮助，也许添加一些节点，调整，也许你在度假等等。在 **n8n** 平台内，你是否有某种**审批流程**，表明“嘿，我做了更改，我从这个分支出来了，我做了更改，我想推送这个，谁可以接受这个”等等？

<details>
<summary>Original English</summary>

**观众**: but but it's a good good additional thing. No. Uh my question was more around like managing workflows in general. You have a you have a project, you have someone who initially sets it up and then you invite some other people onto your team plan uh who also are supposed to help out maybe adding some nodes, tweaking, maybe you're on vacation and so on. Do you have some sort of approval process within the NAD platform that says hey I made changes like I branched out from this made changes I want to push this who can accept this and so on.

</details>

**Liam**: 是的。所以答案将取决于你是否是企业用户。嗯，假设你不是企业版用户。那将只是一个**工作流设计**的问题，以及内部管理的问题。你知道，你复制它，然后负责管理它的人会用这些更改替换它。如果你是企业版用户，那有一个完整的**环境**和 **Git 功能**，这正是你想要的。它有 **Git 集成**。你可以有多个环境。所以你可以有开发、测试、生产环境，你可以让人们管理它和特定的审批人。

<details>
<summary>Original English</summary>

**Liam**: Yeah. So the answer would really depend on if you're enterprise or not. Um assuming assuming it's not an enterprise plan. That would be just a matter of workflow design to do that and then just managing that internally of you know you make a copy of it and then whoever's in charge of managing it will replace it with those those changes. If you are on enterprise there's a whole environments and git feature which is exactly that. It has git integrations. You can have multiple environments. So you can have dev staging prod and you can have people managing that and specific approvers the

</details>

**Liam**: 但是就多人使用而言，你是说多人使用同一个工作流，还是编辑它？

<details>
<summary>Original English</summary>

**Liam**: but in terms of multiple people using do you mean multiple people using the same workflow or editing it?

</details>

**观众**: 更多是编辑。

<details>
<summary>Original English</summary>

**观众**: More editing.

</details>

**Liam**: 是的。是的。那可能会有点棘手，对于分支来说。比如，如果你想有一个**功能分支**或类似的东西，那你就需要复制它，把它带回来，进行更改，或者使用企业版并使用 **Git 集成**。最近这方面有了很大的改进，因为现在还没有完全实现**双人模式**，你无法看到两个人同时在同一个工作流上工作，你无法与另一个人实时地在工作流上工作，但现在有了**自动保存**，后台会有实时更新。所以，如果你和另一个人远程合作一个工作流，你可以看到彼此在移动东西之类的。

<details>
<summary>Original English</summary>

**Liam**: Yeah. That's something that can be that can be tricky with with branches. like if you wanted to like have a feature branch or whatever, that would be something you would need to copy with to just copy it, bring it back, make the changes or um use enterprise and use the the git integrations. That did get a whole lot better recently because there's now the there's not full two player yet where you can see two people working at the on the workflow at the same where you can work on the workflow with another person live but at live updates in the background now that we have autosave. So, like if you're working on a workflow with another person remotely, you can see each other's like moving stuff around and stuff like that.

</details>

**观众**: 谢谢。

<details>
<summary>Original English</summary>

**观众**: Thanks.

</details>

**Liam**: 好的。

<details>
<summary>Original English</summary>

**Liam**: Yep.

</details>

**Liam**: 好了，最后几个问题，如果有人有的话。是的。

<details>
<summary>Original English</summary>

**Liam**: All right, last couple questions if anyone has anything. Yep.

</details>

**观众**: 嗯，**人机协作**在**没有 UI** 的情况下怎么办？因为我看到它显示了两个按钮，比如“接受”和“拒绝”。但是如果你，我猜如果你只是回复“接受”给 **LLM**，它就无法执行工具。

<details>
<summary>Original English</summary>

**观众**: Um what about uh human in the loop um for cases um in which you have no uh UI because I saw that um it shows two buttons like accept and decline. But if you I guess that if you just respond accept to the LLM, he cannot just execute the tool.

</details>

**Liam**: 完全正确。所以，嗯，在像电话呼叫这样的情况下，它没有可点击的按钮，你期望 Agent 询问确认。例如，在一个与 Agent 的电话呼叫中，Agent 为你预订约会，也许它只是在执行之前询问确认。那么，它能处理这种情况吗？在这种情况下，提示词应该建议点击哪个按钮？所以，我不确定我们是否会拥有，嗯，因为那需要 **LLM** 决定是批准还是拒绝，而这整个过程的目的是**人工审核**。否则它无法通过。所以，那是一堵砖墙。**DMZ**，什么都过不去，对吧？话虽如此，嗯，现在它只有聊天平台。我希望我们也能有能力说自定义，并且它会返回 **Webhook**，因为在底层它只是创建了一个**端点**，然后那些聊天平台会向其发送 **API** 请求。我希望我能直接拥有那两个 **API** 链接，它只是放置一个唯一的令牌，这样它就知道哪个是哪个，然后你就可以自己集成。所以希望最终会实现。

<details>
<summary>Original English</summary>

**Liam**: Exactly. So um in cases like um a phone call uh which uh provide um has no buttons to click, you expect the agent to uh ask for a confirmation. for instance, uh on a phone call with an agent that books appointments for you and maybe he just uh ask for a confirmation before doing that. So uh can it um handle such a situation in which uh the prompt should suggest which button to click? So, I'm not sure if we'll ever have um the the because that would require the LLM deciding if it's approved or denied, which the entire, you know, purpose of this is human review. It cannot get passed otherwise. So, that's a that's a brick wall. DMZ, nothing getting past it, right? That being said, um right now it's only chat platforms. I would like us to also have the ability to say custom and it gives you back web hooks because under the hood what it's doing is it's just making an endpoint that then those chat platforms send API requests to. I would love if I just had those two API links which it just puts a unique token so it knows which is which and then you can integrate it yourself. So hopefully that will come eventually.

</details>

**Liam**: 但对于你的特定用例，我会说你可以使用**子工作流**并手动执行该逻辑。所以你可以创建一个子工作流，并且你可以让它执行操作，它会实际地，你知道，提问，你得到回复，然后你只需使用一个 **if 节点**，如果它被批准，如果它没有，然后你有两个分支基于此。你可以在一个工具中通过执行子工作流来做到这一点。你可以简单地命名它为“确认”，然后它可以回复真或假或任何它需要做的事情。所以你可以像这样将它抽象成一个工具。那将只是**工作流设计**，而不是单元审核步骤。这说得通吗？

<details>
<summary>Original English</summary>

**Liam**: But for your specific use case, what I would say is you can use a subworkflow and do that logic manually. So you can make a subworkflow and you can have the action where it goes in and actually, you know, asks the question, you get it back and then you just do an if node if it's approved, if it's not, and then you have two branches based on that. And you could do that in a tool with the execute sub subworkflow. And you can just name it confirm and then it can respond true or false or whatever it needs to do. So you could do that like abstract away that into a tool. It would just be workflow design instead of the unit review step. Does that make sense?

</details>

**观众**: 太棒了。

<details>
<summary>Original English</summary>

**观众**: Great.

</details>

**观众**: 谢谢。

<details>
<summary>Original English</summary>

**观众**: Thanks.

</details>

**Liam**: 好的。最后一个问题。

<details>
<summary>Original English</summary>

**Liam**: All right. One last question.

</details>

**观众**: 是的。呃，假设你在 **n8n** 中设计了一个工作流，并且你想要将其用作 **API**，并从其他地方调用它，就像在我的公司里，我们能够部署 **Microsoft** 的东西，其他都很复杂，但将其用作引擎，然后只调用它并隐藏它，这可能吗？

<details>
<summary>Original English</summary>

**观众**: Yes. uh let's say you design a workflow in uh and and and you want to um to use it as an API and call it from someplace else like in my company we have we are able to deploy Microsoft stuff the rest is complicated but use it as an engine and then just call it and hide the is it that is that possible

</details>

**Liam**: 绝对可以。我一直在 **n8n** 中创建完整的 **REST API**，并且我创建了，你知道，花哨的 **Swagger 文档**和所有东西，就像我之前提到的优惠券生成一样。我制作了整个优惠券工具。它是一个 **REST API**，这样我们团队中的其他人就可以将其集成到他们的 **n8n 工作流**和外部工具中。我制作了所有这些，然后只是给了他们 **REST API 文档**，所有这些都在 **n8n** 内部，并且所有东西都在那里进行管理，包括所有的**人机协作**等等。所以，嗯，希望这能回答你的问题。绝对可以。你只需创建一个像这样的 **Webhook 触发器**。

<details>
<summary>Original English</summary>

**Liam**: absolutely I make um full rest APIs and n all the time and I make you know the fancy uh like swagger docs and anything like I just like I mentioned with the coupon generation. I made that whole coupon tool. It's a REST API so that other people on our team can integrate into their NAND workflows and into the external tools. And I made all of that and then just gave them REST API docs and it's all inside of NAND and everything's managed inside of there including all the human in the loop and everything. So um I hope that answers your question. Absolutely. You would just make a web hook trigger like this.

</details>

**Liam**: 然后你在这里会得到一个路径。你也可以使用**RESTful 名称**。所以你可以像 `user` 这样，然后像，我不知道，`POST` 来创建一个用户，如果这说得通的话。

<details>
<summary>Original English</summary>

**Liam**: And then you get a path right here. And you could do restful names too. So you could do like user and then like I don't know post to create a user for instance if that makes sense.

</details>

**Liam**: 好了。我想时间差不多了。我希望这有所帮助，并向你们展示了新东西，让你们学到了东西，并且你们以后会扩展它，使其不仅仅能管理 **Gmail** 和 **Google Calendar**，还能做你们内心想做的所有事情。嗯，我想说一件事，如果你要向它添加更多工具，请使用**子 Agent** 工具，呃，Agent，然后你可以有一个 Agent 调用其他**专业 Agent**。所以我们刚刚创建的这个 Agent 可以成为一个日历和电子邮件管理子 Agent。你可以根据需要构建任意多的 Agent。这个可以是你的 **GitHub** 问题 Agent。这个可以是你的，呃，天哪，**Jira 管理** Agent，依此类推。这样你就不必向主 Agent 添加太多上下文，并且可以在每个 Agent 之间更改模型。每个 Agent 都可以有不同的 **LLM**，针对其不同的任务进行优化。希望这说得通，我很高兴你们能尝试一下。如果你们在会议期间的任何其他时间看到我们中的任何一个人或我，请过来聊天。呃，别忘了去使用你的。

<details>
<summary>Original English</summary>

**Liam**: All right. And I think that's pretty much all the time we have. I hope that this was helpful and showed you new things and that you learned stuff and that you will go later and expand this to have much more than just Gmail and Google Calendar to do all of the things your heart wants. Um, one thing I would say if you're going to add a bunch more tools to this, use the sub agent tool, uh, agent, and then you can have one agent that calls other specialized agents. So this agent we just made can go to be a calendar and email management sub agent. And you can build these out as many as you want. This one could be your GitHub issues. This one could be your uh god forbid Jira management uh agent and the list goes on. That way you're not adding so much context to just the main agent and you can change the model between each one. Each one can have a different LLM optimized for its different thing. Hope that makes sense and I'm excited for you guys to try it out. If you guys see either of us or me at any other time during the conference, please come up and chat. Uh and don't forget to go and use your

</details>

**观众**: 设备。

<details>
<summary>Original English</summary>

**观众**: device.

</details>

**Liam**: 是的，我一直在推迟这个，差不多一个月了，我想它会强制更新，就在那个时候。所以它正好在 12 点弹出来。所以会议结束了。非常感谢大家。

<details>
<summary>Original English</summary>

**Liam**: Yeah, I was I've been pressing defer on this for like the last month straight and I'm like it's it's I'm like it's going to force an update during the thing. So it came up at exactly 12. So that's the session. Thank you guys so much.

</details>