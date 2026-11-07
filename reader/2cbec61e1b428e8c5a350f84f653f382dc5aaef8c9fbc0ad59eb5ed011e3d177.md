---
author: How I AI
date: '2026-08-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EgrI2rUmM48
speaker: How I AI
tags:
  - workflow-automation
  - voice-orchestration
  - ai-agent
  - productivity-enhancement
title: OpenAI 工程师 Nick Bowman 访谈：如何用 Codex 与 ChatGPT Work 实现全工作流自动化
summary: 本期访谈中，OpenAI 工程师 Nick Bowman 与主持人 Claire Vo 深入探讨了 Codex 和 ChatGPT Work 的最新特性。Nick 现场演示了如何通过语音助手联动 Slack 与 Chrome 进行差旅预订与报销，以及利用 UGC 视频编辑插件实现自动化剪辑与隐私信息模糊。双方还讨论了语音交互中的延迟与智能权衡，并分享了各自在 AGI 时代的日常 AI 工作流与提示词策略。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - Codex
  - ChatGPT Work
media_books: []
status: evergreen
---
### 语音智能与代理的兴起

**Nick**: 如果我们回到 2022 年或 2023 年，在 ChatGPT 刚刚发布的时候，我想很多人对 AI 的感觉还停留在“这是一个聊天机器人，我对它说话，它聪明地回答我”。但我认为随着**编码代理（Coding Agents）**，特别是**编码代理控制台（Coding Agent Harness）**的出现，现在这个 AI 可以直接走出去，比如读取文件、创建文件，甚至运行命令，这简直太疯狂了。我只需要告诉它一件事，然后它自己就能搞定所有其他的事情。

<details>
<summary>Original English</summary>

**Nick**: If we go back to, you know, 2022, 2023 around the release of chatgpt, I think a lot of people felt the AI then a chatbot that I say things to and intelligently says things back to me. I think with the advent of coding agents and like the coding agent harness in particular, now this AI is going out and like reading files and creating files, like running commands and this is crazy. I sell it one thing and then it figures out all the other things on it own.

</details>

**Claire**: 我还没怎么深入使用过语音功能。我想看看专业人士是怎么用的。我们应该怎么使用它？它有什么酷炫的地方？

<details>
<summary>Original English</summary>

**Claire**: I haven't gone deep with voice. I want to see it from the pro. How should we be using it? What's cool about it?

</details>

**Nick**: 好的，我现在就触发语音功能。我为此设置了一个快捷键。

<details>
<summary>Original English</summary>

**Nick**: So, I'm just going to trigger voice. I've got a hotkey for it.

</details>

**Codex**: 我在听，请讲。

<details>
<summary>Original English</summary>

**Codex**: I'm listening. Go ahead.

</details>

**Nick**: 好的。最近我买了一个麦克风，应该有一张亚马逊的收据。这是用于 DX（开发者体验）业务的。我希望你能帮我报销它。你能否启动另一个线程来帮我处理这份报销单？

<details>
<summary>Original English</summary>

**Nick**: Okay. There should be some Amazon receipt for a a mic I just bought recently. It's for DX uses. I'm hoping you can help me expense it. Could you spin up another thread to handle taking care of that expense report for me?

</details>

**Codex**: 报销任务已启动。它会找到亚马逊的收据并暂存 **Navon** 报销单，但在你确认之前不会提交。准备好供你审核时，我会通知你。

<details>
<summary>Original English</summary>

**Codex**: The expense task is running. It'll find the Amazon receipt and stage the Navon report, but not submit it until you confirm. I'll let you know when it's ready to review.

</details>

**Claire**: 如果有人足够幸运，能拥有一个真正的助理，就会知道助理就是这样帮你把事情办妥的。这种委派任务的体验真的太棒了，就像在说：“嘿，你能处理一下这个吗？嘿，你能修复一下这个吗？告诉我发生什么了。”

<details>
<summary>Original English</summary>

**Claire**: If anybody has been lucky enough to have an assistant, this is how it gets done. And it is just like such a nice delegation experience to be like, "Hey, can you take care of this? Hey, can you fix this? Tell me what's going on."

</details>

**Nick**: 通常情况下，语音是很棒的。你可以和它来回交流，但过去通常是使用能力较弱的模型。而现在这个，它完全有能力独立委托和管理五、六个线程，这非常棒，因为这样你就可以让它代表你去做很多事情。

<details>
<summary>Original English</summary>

**Nick**: Typically, voice is great. You can like talk back and forth, but it's usually with a less strong model that is less capable. Whereas this, it's fully able to delegate and manage these fully, you know, five, six threads on its own, which is great cuz then you can have it do things on your behalf.

</details>

**Claire**: 抛出一个尖锐的问题：你认为在语音体验中，**延迟（Latency）**和**智能（Intelligence）**哪一个更重要？

<details>
<summary>Original English</summary>

**Claire**: Hot take question. What do you think matters more on voice experience latency or intelligence?

</details>

---

### 节目开场与新特性概览

**Claire**: 欢迎回到《How I AI》节目。我是 Clarvo，一名产品负责人，也是 AI 的狂热爱好者。我的使命就是帮助大家利用这些新工具进行更好的构建。今天我们邀请到了来自 OpenAI 的 Nick Bowman，他将为我们展示 **ChatGPT Work** 的一些高级使用案例，包括如何通过对电脑说话来订机票、如何使用 ChatGPT 站点构建可以与任何人（或不与任何人）共享的网站，以及演示我最喜欢的流程——在 Codex 中编辑创作者内容。让我们开始吧。本期节目由 **bolt.new** 赞助播出。bolt.new 是一个面向有想法并希望快速交付的用户的 AI 应用构建工具。大多数 AI 工具吐出来的代码在演示时看起来很棒，但当你尝试做些实用的东西时就会崩溃，或者它们会把你锁定在自己的平台上。而 Bolt 是不同的。你只需描述你想要构建什么——一个初创公司 MVP、一个落地页、一个内部工具还是一个 side project——Bolt 就能在几分钟内生成生产就绪的代码。你可以连接 Stripe 或其他 MCP，挂载你的域名并直接部署上线。创始人正在使用 Bolt 构建产生真实收入的业务；产品经理正在交付团队真正使用的原型；设计师和市场营销人员无需排队等待即可发起活动。任何人都可以构建，工程团队也可以快速交付，这是一个共赢的方案。你只需要一个想法和一个周末。请前往 bolt.new/howiaai 了解更多。Nick，欢迎来到《How I AI》。

<details>
<summary>Original English</summary>

**Claire**: Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have Nick Bowman at OpenAI and he's going to show us some of the advanced use cases of chattex and chatt work including how you can talk to your computer to book your flights, use chatd sites to build websites you can share with anybody or nobody and use my favorite workflow which is editing creator content in codecs. Let's get to it. This episode is brought to you by bolt.new. New the AI app builder for people who have ideas and want to ship them. Most AI tools spit out code that looks great in a demo and falls apart the second you try to do anything real with it. Or they lock you into their own platform with no real way out. Bolt is different. You describe what you want to build. A startup MVP, a landing page, an internal tool, a side project, and Bolt generates productionready code in minutes. Connect Stripe or any other MCP. Hook up your domain and deploy it live. Founders are using Bolt to build businesses doing real revenue. Product managers are shipping prototypes their teams actually use. Designers and marketers are launching campaigns without waiting in line. Anyone can build. Engineering can ship. Everyone wins. You just need an idea and a weekend. Check it out at bolt.new/howiaai. Nick, welcome to How I AI.

</details>

**Nick**: 你好 Claire，感谢你邀请我。

<details>
<summary>Original English</summary>

**Nick**: Hello Claire, thanks for having me.

</details>

**Claire**: 我说出来可能会让你发笑，因为我可能是世界上头号 Codex 铁粉、科技男铁粉。我总是在不断地告诉别人：“等等，你试过编码吗？你试过 Codex 了吗？”它就是我每天的生产力工具。所以我非常兴奋能邀请你来，因为尽管我一直频繁使用它，而且用于一些你我都觉得很有价值的事情，但我还没接触过上周刚发布的大多数新功能。技术迭代实在太快了，很难跟上。因此，我真的很开心你能在这里为我们展示一些新东西，也许展示一下你如何在工作和生活中使用 Codex。请告诉我们，你觉得 Codex 中有哪些功能是大家不太了解的，或者有哪些全新的功能，你认为它们将彻底改变我们所有人的工作方式？

<details>
<summary>Original English</summary>

**Claire**: I am going to make you laugh because I might be the number one Codeex fan fanboy tech bro fanboy in the world. I am like constantly telling people, wait, but have you have you tried code? Have you tried Codeex yet? It is just my daily driver. So, I'm so excited to have you on because even though I use it all the time and for some things that you and I think both think are valuable, I have not touched most of the new features that have come out in the last week, it's really hard to keep up. And so, I'm really psyched that you're here to just show us some of the new stuff and maybe how you use Codeex both for work and life. So tell us what are the things in Codex you feel like people don't really know about or or brand new that you think are completely going to change how how we all work?

</details>

**Nick**: 是的，我觉得随着昨天语音功能的发布，现在的 **ChatGPT Codex** 应用就像是我们一直在悄悄拼凑的各种原语的结合体，现在它们变得超级好用。许多人不知道在 ChatGPT 应用中，你可以要求它创建线程，也可以要求它向现有线程发送消息，并且这些线程之间其实也是可以互相通信的。这在应用界面上表现得不是很显眼，但这些确实都是现有的能力。现在，我们真正加入了这个语音编排层。有了它，你只需使用快捷键就可以触发一个在屏幕上弹出的球体。无论你在电脑的什么地方，你都可以和它说话，它会回答你，而且它能看到你的屏幕，能看到你正在处理的工作。正因为我们拥有了“查看现有线程”、“创建新线程”、“与之对话”这些原语，它基本上可以帮你管理整个聊天流程。

<details>
<summary>Original English</summary>

**Nick**: Yeah, I feel like you know with yesterday's release of voice um the chatbt codeex app, it's kind of like the amalgamation of all these primitives we've been like putting together kind of quietly and now we're super useful. So a lot of people don't know that the chatbt app you can ask it to create threads, you could ask it to message your existing threads and these threads actually talk to each other too. And it's like not super kind of forward in the app, but these are all capabilities. And now we've added this voice orchestration layer really where now you can, you know, the hotkey you can trigger this this orb that like pops in your screen and no matter where you are in your computer, you can talk to it. it'll talk back to and it can see your screen, can see what you're working on, and because we have those primitives of see your existing threads, create new ones, talk to them, it can like basically manage your entire chatb for you.

</details>

**Claire**: 是的。在进入花哨的语音功能之前，我不想让大家忽视的一点是，我真的觉得大多数人并不了解 Codex 的**元能力（meta capabilities）**。例如它不仅能分叉子代理，还能开启全新的线程、复刻线程、查找旧数据、检索它自己的记忆等等。这是一个非常棒的机制，可以让 AI 管理上下文，并让它决定何时将不同的任务分叉出去是合理的。我最近经常这样做。但实际上，我是非常偶然才发现这个能力的。有一天我坐在那里，它大概分叉了五六次，它说“我要启动一个新线程”，我当时的反应是：“你要做什么？现在又怎么了？”所以我觉得像 Codex 和 ChatGPT 这种核心平台所面临的挑战之一，就是人们不知道如何发掘这些功能，尽管它们非常丰富。除了这个线程复刻功能，你觉得还有哪些 Codex 或 ChatGPT 的边缘功能是被人们低估的？

<details>
<summary>Original English</summary>

**Claire**: Yeah. One of the things that I I don't want people to miss before we even get into like the fancy voice stuff is I really do feel like most people do not know the meta capabilities of codecs and even like we won't say but like the the other one in that like its ability to not only spin off sub agents but actually start completely new threads, fork threads, look through old data, look through its own memory. Um, it's it's a really good mechanism to let the AI manage context and decide when forking off different tasks makes a lot of sense. And so I've been doing that a lot. But I actually had to discover that capability sort of organically when one day I was sitting there and it was probably five six was like I'm going to kick off a new thread and I was like you're going to do what? Like what now? And so I do I do feel one of the challenges with these core kind of platforms like codeex's and chatbt is people just don't know how to discover the features and they're so rich and so do you have any you know like we'll talk about voice but are there any other like sort of edge features of codeex or chatgpt that you feel like people underuse not just this this thread one

</details>

**Nick**: 谈到 ChatGPT Work 的体验，人们总是在讨论我们应该使用 ChatGPT Work 还是使用 Codex。我认为在网页端特别是移动端的 **ChatGPT Work** 简直强大到不可思议。我自己主要就是在手机上使用它。它本质上非常像 Codex 的控制台，拥有令人难以置信的紧凑性。你可以使用所有的插件。所以如果你已经连接了 Gmail、Google Calendar 等任何你日常使用的工具，它就已经就绪了，并且都可以在你的手机上进行访问。你可以创建这些自动化，甚至将它们作为心跳任务运行。比如我每天会收到几次通知说：“嘿，我收到了关于你购买此物品的电子邮件。你确认购买了吗？”或者“嘿，这个包裹马上要送达了，记得去拿。”我并不需要自己时刻盯着我的邮箱或财务状况，系统会自动帮我监控，这真的是很神奇的体验。

<details>
<summary>Original English</summary>

**Nick**: the chat GPT work experience you know people are talking about you know should we using chatbt work or codecs. I think chat GBT work on the web specifically mobile. I mean that's where I use it mostly is so insanely powerful. It it's one it's it's essentially like the codeex harness which has this incredible compaction. You have all your plugins. So if you've like already connected to Gmail, Gcal, like whatever you use, it's already there and then you have it all accessible in your phone. So you can like create these automations um also as heartbeats um and it's already there. So, like I mean a few times a day I'll just get like a notification saying, "Hey, like I got this email about this thing you bought. Are you sure you bought that?" Or like, "Hey, this package is arriving. Like, make sure you grab that." And I'm not watching my email or my finances, but that's just kind of being monitored for me. That's that's really magical experience.

</details>

---

### 实时差旅规划与任务委派

**Claire**: 太棒了。那让我们来聊聊语音交互以及你平时用它来做什么。因为它是昨天刚发布的，而我最近一直很忙，还要和人打交道。我还没能深入研究它，我想听听专业人士的看法。我们应该怎么使用它？它有什么好玩的地方？

<details>
<summary>Original English</summary>

**Claire**: Okay. I love it. All right. So, let's get into Chat Voice and what you what you use it for because I it came out yesterday. Um, I've been super busy and around humans. We're going to talk about that a little bit later. So, I haven't gone deep with voice. I want to see it from the pro. How should we be using it? What's cool about it?

</details>

**Nick**: 是的，它确实非常神奇。那么我直接触发语音了，我设置了快捷键。

<details>
<summary>Original English</summary>

**Nick**: Yeah, I I think it's really magical. So, I'm just going to trigger voice. I've got a hotkey for it.

</details>

**Codex**: 我在听，请讲。

<details>
<summary>Original English</summary>

**Codex**: I'm listening. Go ahead.

</details>

**Nick**: 我希望你能帮我处理一些后勤后勤方面的事情。你能看到我拉出的 Slack 界面里的团建安排吗？

<details>
<summary>Original English</summary>

**Nick**: I'm hoping you can help me handle a few logistical things right now. Can you can you see the the offsite I've got pull up in Slack?

</details>

**Codex**: 我来看看，让我检查一下那个 Slack 窗口。是的，看到了。这是 DX 团队在巴黎的团建，时间是 8 月 26 日至 28 日。你需要在周二到达，活动将于周三上午开始，周五下午结束。机票和酒店应该在这一周内通过 Navon 预订。

<details>
<summary>Original English</summary>

**Codex**: I'll take a look. Let me check that chat. Slack view. Yep. It's the DX team offsite in Paris August 26th through 28th. You're due in Tuesday with the program starting Wednesday morning and wrapping Friday afternoon. Flights and hotel are supposed to be booked in Navon this week.

</details>

**Nick**: 好的，我刚才把自己静音了，这样 Codex 就听不到我说话了。刚刚发生的事情是，它已经能看我的屏幕了。你们可以看到我打开了 Slack。它所做的事情是获取了一个 **Appshot**。Appshot 是一种功能，当你打开任何窗口时，只需按下 Command+Command 快捷键，它基本上就会捕捉一张带有上下文的智能屏幕快照，然后我可以立即在上面使用计算机操作（Computer Use）或浏览器操作（Browser Use）。这是一个非常元的功能，而 Codex 语音功能里已经内置了这一点。那么，我希望你能帮我预订巴黎团建的机票和酒店。我还在考虑是否在巴黎多待到周末，或者之后多待几天。你能帮我查看我的日历，看看我的空闲时间，确认这是否可行吗？

<details>
<summary>Original English</summary>

**Nick**: All right. So, I I muted myself so that Codex doesn't hear me right now. But what happened there is it can already see my screen. You can see I've got Slack opened up. And what it did is it took an appshot. And so an appshot is something that you can do where you whatever window you have open, you just hit command command and it essentially takes like a smart screenshot loaded with context. I can use computer use or browser use on it instantly. But you know kind of a meta feature. Codex voice already has that built in. So I'm hoping you can help me book my flights and my hotel for the Paris offsite. I'm also thinking about sticking around to the weekend and maybe a couple days after. Could you maybe like check my calendar, see what my availability is like and see if it's if it's feasible for me to stick around?

</details>

**Codex**: 我将对照团建日期检查你的日历，然后寻找出行选项。

<details>
<summary>Original English</summary>

**Codex**: I'll check your calendar against the off-site dates and then look at travel options.

</details>

**Claire**: 这是通过连接器实现的吗？

<details>
<summary>Original English</summary>

**Claire**: Is this using the connectors?

</details>

**Nick**: 好问题。是的，目前它在后台使用的是插件。所以它不需要真正自己去……

<details>
<summary>Original English</summary>

**Nick**: Good question. Yeah, so this is using the plugins underneath the hood right now. So, it's not having to actually go

</details>

**Codex**: ……在团建结束后多留到 8 月 31 日周一。如果是 9 月 1 日周二返回，会和一场下午晚些时候的会议冲突。最简单的方案是 8 月 31 日周一返回。你需要我按照这个方案来规划吗？

<details>
<summary>Original English</summary>

**Codex**: after the offsite through Monday, August 31st. A Tuesday, September 1st return would conflict with a late afternoon meeting. The simplest plan is returning Monday, August 31st. Do you want me to plan around that?

</details>

**Nick**: 你知道吗？我在想我可能会在周一和周二休年假（PTO）。我从 SFO（旧金山国际机场）出发。所以，你直接去用 Navon 预订吧。另外启动一个任务去搞定行程。挑选一家合理且符合公司政策的酒店，准备好后告诉我，我来点击“立即预订”。

<details>
<summary>Original English</summary>

**Nick**: You know what? I'm thinking I might just take PTO on that Monday and Tuesday. I'm flying out of SFO. So, why don't you just go ahead and use Non. Um, spin up another task to figure out the travel. Pick a hotel that's reasonable and within our company policy, and then when it's ready, let me know and I'll I'll click book now.

</details>

**Codex**: 好的，我会处理好的。我会寻找从 SFO 出发、在周三活动开始前的周二抵达、并在 9 月 1 日周二之后返回的航班方案，然后为你呈现符合政策的选项以供预订。那么，这个对话是要放在……噢，抱歉。

<details>
<summary>Original English</summary>

**Codex**: Sure, I'll sort that out. I'll find options for flying out of SFO, arriving Tuesday before the Wednesday start, and returning after Tuesday, September 1st, then bring you choices that fit policy for you to book. So, is this chat going to be in... Oh, sorry.

</details>

**Nick**: 我在和它说话呢。邀请 Claire 也去参加巴黎团建，让她住丽兹酒店，订商务舱。坦白讲，我们其实还没有真正敲定巴黎团建，但因为我们 DX 团队里有很多人是法国人，我希望能在它这里先播下这个想法的种子。

<details>
<summary>Original English</summary>

**Nick**: I I'm talking to I'm talking to his CEX. Invite Claire to the Paris offsite. Put her up in the rits. Get her in business class. And honestly, we we don't we don't really have a Paris off site scheduled yet, but so much of our DX team is French that I'm hoping that I can like, you know, start seeding the the ideas here.

</details>

**Codex**: 该任务正在运行中。正在比对 8 月 25 日至 9 月 2 日从 SFO 出发的航班以及合适的酒店。建议的行程单准备就绪后我将与你分享。

<details>
<summary>Original English</summary>

**Codex**: That task is running now. Comparing flights from SFO at a practical hotel for August 25th through September 2nd. I'll share the suggested itinerary when it's ready.

</details>

**Nick**: 太酷了。我们已经让这个任务在后台运行了。确保这次任务使用的是我现有的 Chrome 浏览器。

<details>
<summary>Original English</summary>

**Nick**: Cool. So, we've got this task already running and make sure it uses my existing Chrome browser for this one.

</details>

**Codex**: 我会确认这一点的。我已经更新了差旅任务以使用你现有的 Chrome 会话，并仅限于准备方案，而不会进行实际预订。

<details>
<summary>Original English</summary>

**Codex**: I'll check that. I've updated the travel task to use your existing Chrome session and keep it to preparing options, not booking.

</details>

**Nick**: 太棒了。所以它现在只是发送了一条消息回到那个已经在运行的任务中。但我认为趁着这个任务还在跑，我还要让它帮我处理另一件事。顺便说一下，我收到了一封邮件，里面应该有一张我最近购买麦克风的亚马逊收据，是用于 DX 团队的。我希望你能帮我处理报销。你能分出一个新线程去帮我处理那个报销单吗？

<details>
<summary>Original English</summary>

**Nick**: Awesome. So, right now it just it just sets a message back to that task. It's already running. But I think while we've got that going, I'm going to ask it to do another thing for me. While I've got you, I've got an email. I think there should be some Amazon receipt for a a mic I just bought recently. Um, it's for DX uses. I'm hoping you can help me expense it. Could you spin up another thread to handle taking care of that expense report for me?

</details>

**Codex**: 好的，我会处理的。我已经启动了报销任务，它会使用你现有的 Chrome 会话。报销任务正在运行。它会找到亚马逊的收据并在 Navon 中暂存报销报告，但在你确认前不会提交。准备完毕可以审核时我会通知你。

<details>
<summary>Original English</summary>

**Codex**: Sure, I'll take a look. I've started that expense task and it'll use your existing Chrome session. The expense task is running. It'll find the Amazon receipt and stage the Navon report, but not submit it until you confirm. I'll let you know when it's ready to review.

</details>

**Nick**: 很好，这两个任务现在都在后台运行。我已经把语音静音了，这样我们就可以聊天而不被打断了。但我们已经可以看到在 Chrome 中，这个任务正在使用浏览器，它在寻找航班选项，接着它会寻找酒店。坦白讲，这确实是我平时最不喜欢花精力去做的琐事，能有它在后台帮我搞定真的是太好了。

<details>
<summary>Original English</summary>

**Nick**: Awesome. So, those are both running in the background. I've I've muted our voice so we can talk without being interrupted. Um, but we can already see that in Chrome, um, this task is using the browser. It's figuring out our flight options. Um, it'll figure out the hotel. Frankly, this is something I just enjoy not having to do. Um, and it's nice to just have this handle in the background for me.

</details>

---

### 语音交互设计：延迟 vs. 智能

**Claire**: 我喜欢语音交互的原因在于，我觉得很多人在使用 AI 时仍然会遇到“空白对话窗口综合症”。当他们看着空白的输入框时，会想：“我要问什么？我该让这个聪明的 AI 去做什么？”所以我首先非常喜欢许多人一直在用的语音转文字，这也就是我们的常客 Hillary 所称的 “Yappers API”（话痨接口）。与大语言模型（LLM）交流的最高带宽方式就是大声说出来。但我更喜欢的是这种端到端的语音对语音交互。如果你有幸有助理，这正是你交代工作的方式。这也是一种极其平滑的任务下放体验，比如可以说：“嘿，你把这个做一下。嘿，把这个修一下。告诉我发生什么了等等。”因此，我推测这种语音体验带来的一个假设是，人们能更好地发现使用场景，并扩展应用范围。因为人们可以用更自然的方式委派任务，而不是坐在那里苦苦思索如何用文字向模型下达指令。你是否发现有哪些特定的任务你更倾向于用语音，而不是用你的人类手指去打字？你完全转向语音了吗？目前你的使用情况是怎样的？

<details>
<summary>Original English</summary>

**Claire**: What I like about voice is I do think sometimes people with AI really struggle still with like blank chat window syndrome, which is like they look at and they're like, "What am I going to ask? What am I going to ask this brilliant AI to do?" And so what I love about first just like voice transcript to text which a lot of people have been using is it is what our beloved multi-time guest um Hillary calls the yappers API which is like the best highest bandwidth way to communicate with an LLM is just to yap out loud and just contact them. But what I love about this like voicetovoice interaction is if anybody has been lucky enough to have an assistant like this is how it gets it gets done and it is just like such a nice delegation experience to be like hey can you take care of this hey can you fix this tell me what's going on blah blah blah blah blah and so I'm I'm guessing the hypothesis here with this voice kind of experience is there's going to be like better discovery of use cases and sort of like more sprawling use cases because people can sort of delegate in a more natural way as opposed to having to like sit there and think through how to instruct kind of in text the the models. Have you found that like there are specific things that you reach for voice with that you don't that you don't like type with your human human fingers? Are you a full voice? Like where are we?

</details>

**Nick**: 是的，有几点想法。首先，我认为这一代语音技术本身就是一种新的原语。以前的语音虽然也不错，你可以和它来回对话，但通常搭载的是一个较弱、能力较低的模型。而现在这个，它有完整的能力来独立委托和管理这五个、六个甚至更多的独立线程。这非常棒，因为它完全可以代表你去执行行动。另外在思维过程上，我认为语音更好。在打字时，如果我口述两分钟，发送一大段话，再收到两段长长的回复并去阅读，我很难保持心流。而在语音中，这种协同规划的过程是非常高效的。

<details>
<summary>Original English</summary>

**Nick**: Yeah, a few thoughts there. One, I think it's like this iteration itself is like kind of a new primitive in that typically voice is great. you can like talk back and forth, but it's usually with a less strong model that is less capable. Whereas this, it's fully able to delegate and manage these, you know, fully, you know, five, six sole threads on its own, which is great because then you can have it do things on your behalf. Other thoughts there? Um, I find the like the thinking process and voice just a lot better when it comes to, you know, I could dictate for, you know, 2 minutes, send off a long paragraph, get back a couple long paragraphs and read those and it's really hard for me to get in flow. Um, I think of like planning in voice to be really really effective.

</details>

**Claire**: 快速提问。你认为对于语音体验来说，延迟和智能哪个更重要？如果让你必须二选一，你会选哪个？

<details>
<summary>Original English</summary>

**Claire**: Hot hot take question. What do you think matters more on voice experience latency or intelligence? If you could only pick one, I'm gonna make you pick one.

</details>

**Nick**: 我会说，当我使用 ChatGPT 语音功能时，我总是将它设为高智能模式。这其中有一个平衡点，我认为如果它有足够好的外部工具可以去委托，那么我实际上会更在乎**延迟**。所以我大概还是会选择延迟。

<details>
<summary>Original English</summary>

**Nick**: I would say when I use chatbt, I put it on high intelligence for voice. I think there's there's like a middle ground. I think if there are good tools it can delegate to, then I care more about latency. Um, so I don't know. I guess I I still say latency.

</details>

**Claire**: 是的。我预测在今年下半年，我们会越来越多地讨论延迟。因为现在体验差异化的核心点之一，就是看你能在多大程度上做到真正的实时体验。我看到很多人放弃了很好的 AI 工作流，仅仅是因为界面上的等待动画（spinner）或一点点延迟。所以你越能缩小这个差距，人们就越能发现好玩的事情，并真正地坚持下去把事情办好。

<details>
<summary>Original English</summary>

**Claire**: Yeah. I think I think it's the I think it's what we're going to be talking and this is the Clairvo prediction. I think it's we're going to talk more and more about latency in the in the second half of the year because I just think it's like almost the the thing to differentiate on right now is like how real time can these experiences really be? I see a lot of people abandon great great AI workflows because of a spinner or because of a delay. And so like the more you can close that gap, the more I think people can discover cool things and actually pull through and get some some stuff done.

</details>

**Nick**: 没错。以前我们在 AI 工具的设计和产品假设上，都是基于“一定会存在延迟和滞后”这一点来进行的。一旦我们能把延迟缩短，这些假设就可以被抛弃，从而诞生全新的产品类型。

<details>
<summary>Original English</summary>

**Nick**: Yeah. I feel like so many product assumptions in design and AI tooling is like built around this like there's going to be latency, there's going to be delay. And the more we shrink that we can kind of drop those assumptions and new products will, you know, will emerge.

</details>

---

### UGC 视频编辑工作流自动化

**Claire**: 精彩。总结一下，我们刚才看到的是：你可以通过快捷键唤醒语音，它可以同时管理五六个高度智能的后台线程。你可以委派任务、调用插件、使用浏览器、进行 Appshots 智能截屏。这是一种低摩擦力、高带宽的方式来和可以帮你做事的超强智能进行交流。你刚才提到你也很喜欢在移动端使用它，能跟我们具体讲讲在手机上进行口述和任务管理是如何改变你的工作流的吗？

<details>
<summary>Original English</summary>

**Claire**: Amazing. Okay. So, so what we've seen here just to to reiterate for people who are maybe not watching or listening is you can hotkey spin up voice. It can manage these like very intelligent five six threads. You can delegate tasks. It can be hooked up to plugins. It can use your browser. It can use appshots. It can use all these things. And it's just like a very high bandwidth, low friction way to talk to super intelligence that can get nice stuff done. You you mentioned that a little bit earlier that you're also loving like mobile and and this combination of like dictation and managing through mobile. Can you tell me how like being able to do some of this on your phone has changed your workflow? So maybe like give me an example of that.

</details>

**Nick**: 比如我建立的这个网站。这是一个聚合了在 Codex 和 ChatGPT 社区，以及 OpenAI 内部员工分享他们如何使用这些工具的酷炫推文的站点。这完全是用 ChatGPT 网页版或手机应用自己完成的。我让它使用内置浏览器在 Twitter 上逛了几个小时，收集这些推文，嵌入链接，并为它们添加简短的说明。现在我所做的是，我工作手机上有一个特定的线程在专门管理这个网站。当我看到喜欢的内容时，我直接把链接丢进那个线程，对它说“添加这个”，它就会在后台自动完成。我们还有一个 prompts（提示词）页面，我也用同样的方法管理它。如果我对如何让新人使用 ChatGPT 工作有什么想法，我直接用手机进行语音听写：“嘿，这里有一个让它管理收件箱和财务的提示词，能把它也加到站点上吗？”而修改站点和部署，完全可以直接在手机应用上完成。

<details>
<summary>Original English</summary>

**Nick**: So I put together this site and so this is just a an aggregation of all these really cool tweets that you know both people in like the codeex and chatbt community and also people work at openai have shared with how they're using codeex chatbt. Um, this was done just with with chatbt, like the chatbt app where I had it use it own inapp browser, go through Twitter for like a couple hours and then embed these links and kind of add a little bit of, you know, description to them. And now what I do is I've got a thread on my work phone that is essentially managing this site and when I see something I like, I just drop in that link. I say add it and it does. We also have this prompts tab and I do the same thing there. If I have like an idea for how somebody could be maybe he's like you newer to like chatbt work I'll just like dictate my phone explain like hey there's this prompt for like having it manage your inbox and your finances can you add this to the site as well and in terms of actually editing the site um deploying it that can all happen from chatbt work on mobile

</details>

**Claire**: 我觉得很多人还没有注意到这一点。现在很多新功能层出不穷，比如这个站点的域名是 `chatgbt.site`。你现在可以把这些类似 Artifact 的临时应用直接统统部署上线。你能给我们简单讲讲它是如何工作的，或者它的局限性是什么吗？我们甚至可以现场搭一个。

<details>
<summary>Original English</summary>

**Claire**: and I think what people are not seeing here which again so many new features coming out that I think people aren't taking advant antage of is the domain here is chatgbt.site. So you can now deploy these like artifacts these sites live. So can you just walk us through a little bit how how that works or maybe we can do one just so people can like understand the power of these sites and and how you might use them or what their limitations are even.

</details>

**Nick**: 好的，如果对技术受众进行一个 10 秒钟的描述：它支持 SQL 数据库，拥有用于存储文件和图片素材的 S3 存储，甚至可以设置环境变量。而对于非技术受众，它基本上就是一个你可以用来存放东西的网站，并且你可以控制谁能看到它。你可以通过邮箱地址进行过滤。它可以是完全私密的，也可以是完全公开的。我们现在就可以尝试现场构建一个网站。

<details>
<summary>Original English</summary>

**Nick**: Yeah, I think like for like 10-second description for the technical audience, it supports a SQL database. Um, it has S3 storage for files and it even has environmental environmental variables you can put there. For the non technical audience, it's essentially a website that you can store things on, which is great. And you can also control who sees it. You can you can filter by by email. So, it can be private, it can be fully public. That's up to you. But what we could do, if you're interested, is we could try building a site live.

</details>

**Claire**: 太棒了，我们来做吧。

<details>
<summary>Original English</summary>

**Claire**: Let's do it.

</details>

**Nick**: 让我们看看现场构建网站的过程。

<details>
<summary>Original English</summary>

**Nick**: And see how to build live.

</details>

**Claire**: 好的，我们开始。我有一个关于网站的想法。我现在正和主持《How I AI》播客的 Claire Vo 在一起，我们希望能建立一个网站，收集她 YouTube 频道视频中所有的精华技巧，让人们能轻松按分类检索，并能提供指向她视频中不同时间戳的快速链接。

<details>
<summary>Original English</summary>

**Claire**: Yeah. All right. Uh, so let's jump into it. So, I've got an idea for a site. I'm here right now with Claire Vo. She hosts the How I AI podcast, and we're hoping that we can build a site that takes all the best tips from the videos on her YouTube channel and makes it so you can like easily filter through them and have quick links to like different timestamps on her videos.

</details>

**Claire**: 另外，设计风格要符合《How I AI》的品牌形象。我们可以使用标志性的 AI 蓝紫色、黑色和白色。如果可能的话，最好能按工具进行分类。比如在具体的工作流中使用了什么 AI 工具，以及这些技巧的功能属性是什么——是针对设计师的、针对工程师的，还是针对个人生产力的。我很期待看你能做出什么来。

<details>
<summary>Original English</summary>

**Claire**: Make it match the how I AI branding. We use good old AI blurp purple um and black and white and um let's have it if if possible categorized by tool. So like what AI tool is being used in the workflow and also function. So if it's for designers, it's if it's for engineers, it's for personal productivity, any of those things. Otherwise, I'm excited to see what you come up with.

</details>

**Nick**: 好的，这听起来太棒了。让我们先私下部署，然后我们看一看。如果效果不错，我们再把它公开部署。在这个网站构建和部署的同时，我再跟你分享一个好笑的故事。最近我跟我妈妈用两台设备进行了“两人多模态语音对话”。她当时正卡在一些繁琐的行政任务上，整个人非常焦躁，抱怨说“我必须去查所有这些资料，这也太麻烦了。”我和她正在通电话，我对她说：“妈，你等一下。”然后我在我的电脑上打开 ChatGPT 并开启语音功能，把手机扬声器打开贴在电脑麦克风旁，让她像我们刚才那样直接对着电脑唠叨，我也替她问了几个澄清问题。完成后我按下确认说：“好了，我已经替你搞定了。”（笑）所以我真的觉得人们低估了“多设备或多人协作语音”的作用。这非常高效，能把杂乱的现实需求直接转化为结构化的系统指令。

<details>
<summary>Original English</summary>

**Nick**: Awesome. That sounds great. and go ahead and deploy it privately and then we'll take a look at it you know when it's ready and then we can deploy it publicly from there if it if it looks good. While this is running, let me make you make you laugh because this um two human chat to chat GBTE I did recently with my mother and um she was like stuck on an administrative task and she was like getting all frazzled about she's like I'm going to have to look up all this stuff and blah blah blah blah blah blah blah and I was on the phone with her and I was like mom just hold on one second and I opened up chat GPT on my desktop and I turned on voice and then I was like can you just please tell what you need to do. And I turned the speaker phone on my phone and I put it up to the computer and had her like babble kind of like we did and I asked her a couple questions and then I was like, "Thanks." Pressed enter and I was like, "I did it for you. I did it for you." [laughter] So, I really do feel like people are underusing like two person voice chat. You can do it on your phone. You can use speaker phone. like it is this really nice again like high bandwidth way to get requirements into the system and it doesn't just have to be you alone.

</details>

**Claire**: 是的。我有时候需要从同事那里获取一些工作背景上下文，我常说：“求求你直接在 Slack 上发语音，把一堆杂乱无章的话直接砸向我就好，我不在乎。”但他们通常的反应是：“不，我们还是开个会吧。”而我的态度是：“别，真不用这样。我不需要你们把语言整理得多么漂亮，只要把信息说出来，剩下的留给我的 AI 代理来解读就行了。”

<details>
<summary>Original English</summary>

**Claire**: Yeah. I I've had times where you know I need context with somebody I work with. And I'm like please just like ramble dictate into Slack and send me like garbage. I don't care. And they're like no let's just like set up a meeting. And I'm like no don't don't do that. I don't need that. [laughter] I don't need this to be like pretty or anything. just just tell me that's fine.

</details>

**Claire**: 所以，我们是在讨论“这个会议其实原本可以是一条语音便签”这个层面上吗？

<details>
<summary>Original English</summary>

**Claire**: So, are we at this meeting could have been a voice note like level?

</details>

**Nick**: 没错。其实只要能把那些非结构化的原始信息提供给我，我的代理就能理清它们，对我来说这就足够了。

<details>
<summary>Original English</summary>

**Nick**: Yeah, I think so. I mean, all it's it's more like give me information that unstructured however it is that my agent can can decipher and that's that's good enough for me.

</details>

---

### 高级视频剪辑与隐私模糊

**Claire**: 本期节目由 **Hyper Agent** 赞助播出。Hyper Agent 是一个能够部署 7x24 小时长驻 AI 代理的平台，可以真正自动运行你的业务流程。通过 Hyper Agent，你可以在云端构建代理，并直接将它们部署在 Slack、Telegram 或邮件等已经存在的工作场景中。一个代理能自动扫描你的收件箱，并替你起草给供应商的跟进邮件；另一个代理能帮你监视竞争对手的动态，并在后台自动生成丰富的广告物料和落地页。这绝对不是在被动等待完美提示词的聊天机器人，它们是具有主动性的，能不断学习你的喜好并记住你的工作手册。有一位用户在一个下午的时间里构建了 4 个代理，组成了一条外包销售流水线，包揽了线索挖掘、邮件触达、跟进和 CRM 系统信息更新。无需本地配置、没有 VPS 账单，也没有脆弱的安全限制。想要拥有这样强大的控制权，请访问 hyperagent.com/howiai 领取价值 1000 美元的免费推理额度。

<details>
<summary>Original English</summary>

**Claire**: This episode is brought to you by Hyper Agent, the platform for deploying always on agents that actually run your business. With Hyper Agent, you build agents in the cloud and deploy them where your work already happens, like Slack, Telegram, or email. An agent will scan your inbox and draft replies to vendor follow-ups. Another monitors competitors and spins up rich ad kits and landing pages. A third notices a deal going cold in Salesforce and writes the save email with full account context. These aren't chat bots waiting for a perfect prompt. They're proactive, learning your preferences, retaining your playbooks, and getting better with every run. One user built four agents to run an outbound sales pipeline, prospecting, outreach, follow-ups, CRM updates, all in a single afternoon. No local setup, no VPS bills, no fragile permissions on your laptop, just powerful agents with full control over skills, tools, and guard rails. Hyper Agent was built by the team behind Air Table and How I AI listeners get $1,000 in free inference to start building. Claim yours at hyperagent.com/howiai.

</details>

**Claire**: 好的，这个网站正在后台构建中，让我们让它继续旋转一会儿。在此期间，还有另一个你我都非常喜欢的 Codex 应用场景，我想请你展示一下具体是如何写提示词的。那就是利用 **Codex 进行视频剪辑**。如果你平时剪过很多视频，或者像我一样为播客做后期，你就会知道这是一件极其枯燥繁琐的工作。能告诉我们你是如何开始用这个功能的？为什么你觉得它好用？对于视频编辑来说，它的提示难度如何？

<details>
<summary>Original English</summary>

**Claire**: Okay, so this is going to go spin up. We're going to let it kind of like whirl a little bit. Maybe we'll come back to what what we see. But there's one other use case that both you and I really like in codeex um that I thought you could show and particularly how how you prompt it which is codeex for video editing and for those that don't know it I do a lot of this for um for the podcast. I also do a lot of this just for like general work stuff. I'm cutting a lot of videos. So, um, tell me like how you came to this use case, why you feel it's so useful, and then how how easy is it to prompt kind of like video editing?

</details>

**Nick**: 因为我是 DX（开发者体验）团队的一员，我们需要通过视频内容来触达那些不在 Twitter 圈子里的人。如果我们能用短短 45 秒的时间对着镜头把事情解释清楚，那就会非常棒。所以我开始在公园里拍摄自己，用相机拍下一大堆各种镜头的素材。比如这是我昨天的拍摄，包含了很多我们最终不会使用的废片。而我所做的事情，是直接把这二十多个视频素材拖进 ChatGPT Work 中。接着，我调用了我自己构建的一个叫做 **UGC 视频（UGC Video）**的插件。该插件经过了我的微调，它包含了一些底层规则，例如视频格式需要 9:16 或 4:5，字幕应该怎么展示，安全区在哪里等等。我的提示词是这样的：“我录制了一个关于记录与重放（Record & Replay）功能的视频，开头我解释了寻找房源的痛苦，然后展示了真实生活中的功能演示以及 Codex 是如何帮我的，最后收尾。请分析这些视频素材，提取出音频转写，找到我表现最好、最自然的那些镜头，然后把它们拼剪成一条 UGC 风格的视频。”它在后台处理时会阅读转写，同时它也会通过图像识别分析我每个镜头中展示的画面，并且能听懂我录像时说的“这条过”、“这条是废片”这样的标记。

<details>
<summary>Original English</summary>

**Nick**: You know, I I do a little bit of content as part of the DX team, and, you know, we're trying to reach people that might not be inside like the Twitter verse, which, you know, there's there's there's there's a lot of us there, but there's more of us not there. Um, and I think explaining, you know, how you can use these tools um, in really relatable ways where you're explaining to like a camera um, in like 45 seconds is great. And so I started just kind of like going to a park, filming myself, filming my camera, getting a, you know, a smattering of little clips. And so this is from like this is from yesterday. I went to the park. These are like most of these are takes that we're not going to use. Um, but what I'll do is I'm literally going to drag these into chatbt work. And then so what I've done and I'm going to share this, but I've created a plugin called UGC video. Actually, let me get the one that I use for I made a version that has like open eye branding, but you can actually see it here. And so this basically after having gone through like a few runs of this, what I've noticed is that just having like some guidance around like, hey, make sure that we're not entering like the safety zone with Instagram ads or let's do these formats. We want 9x6 also 4x5. That's great. But what I'll generally do and I'll dictate this. So we've got a bunch of clips here. I recorded a video for the record and replay feature. It starts with me just explaining that I'm apartment hunting and that's kind of a pain. And then I walk through and show the feature in real life. I show myself actually apartment hunting. And I show how Codex can do it for me. And then I have a closer about how I this skills that's been made that's been made for me can be put on a heartbeat and I can have Codeex just search for apartments in the background. Can you go through these clips first? like pull the transcripts, find the best takes, and then kind of piece this together into a UGC style video. So, that's running a few things that to kind of explain how this works. So, I've only submitted like 20 some odd like video clips. And so, what code is going to is going to do is going to start by processing those clips to get just the transcripts. This will help it understand like the story, what we're talking about, and even like my light description will help it understand that. And then what I'll do then, actually, it's ask me some questions. Sure, we'll do organic vertical. Let's do complete and clean. Sure. So, it'll first get the transcript and that's going to go through the takes and actually like process images from them to understand what I'm showing. And then it'll choose like the best takes. And when I'm recording, I'll say things like cut or that's a bad take or that's a good take. And it's able to like use that as guidance, you know, like you know what's actually useful from these.

</details>

**Claire**: 你启发了我。因为视频剪辑和短视频创作太难了，我已经很久没打理我的 TikTok 了。我总是有很高的要求，经常录完一堆片段后觉得是垃圾，然后就沮丧地放弃了。但现在你提供的方法是，我可以一直对着录制，直到感觉有一条满意为止，然后直接把所有原始文件全部打包扔给 AI，而无需记住到底哪一个是好的一条，然后口述一段如何剪辑的语音指令，就能让它自动帮我筛选、转写并拼剪出来。我经常在做播客推广预热短视频（trailer）时这样做，直接把 30 到 60 分钟的录音丢给它，让它提取出最搞笑的 60 秒做成高燃花絮，并预留一点剪辑缓冲，它的成片效果其实带有一种非常微妙的幽默感。还有我每季度讲的 3 小时的组织变革课程，也是把录像直接丢给它，让它自动生成章节和切片，这真的是把繁琐的视频剪辑工作大大减轻了。所以这个插件背后到底做了什么工作？

<details>
<summary>Original English</summary>

**Claire**: you're going to give me so many ideas because I have like deeply abandoned my once great TikTok because I guess like UGC is hard. Like short for short form is hard. Um and I just have such a high bar that I'm constantly like recording these clips and being like that was garbage and then I get frustrated. I walk away. But you've given me this idea which is I could just like keep recording until like there's one that feels good and then just dump it all. I don't even have to remember which one is good. Dump it all, give some voice notes about how to edit and then and then kind of assemble it. And then I I love this process of just having the model transcribe, look at the video, come up with like good good cuts and put it together. I use it a lot for our trailers. So, anytime I do a very long, like a 30 to 60 minute talk, or I do a podcast that's like 60 minutes, I dump it in and I'm like, give me a 60-second hype video with the funniest parts of the talk and like give me a little bit of buffer for for clipping and then it it clips that really well. It actually has like pretty good funny taste. Um, which is nice. And so, I do that. And then I also do like I teach like a three-hour long workshop um every quarter on how to like transform your engineering organization to be kind of like AI engineers. It's very very long. It's like three-hour Zoom clip and I also do that to like clip chapters, clip shorts, do all that sort. It's just like all this tedium of of video editing. It's quite quite good at. And then just tell us like what does what does this plugin actually do?

</details>

**Nick**: 这个插件实际上就是建立在我这周反复测试和调校的基础上的。比如我怎么去调整它，去定义画面尺寸、字幕和安全区界限等。在做完几次类似的视频之后，我积攒了大量的特殊规则，然后我直接对它说“把这些提炼为一个插件”。在 ChatGPT 应用中有一个专门用来创建插件的**插件生成器（Plug-in Creator）**，它的逻辑非常简单，经过几次微调后，它现在就能非常稳定且高概率地输出我满意的“黄金路径”视频。

<details>
<summary>Original English</summary>

**Nick**: Yeah. So, the plugin is really just based on like all the steering I've done uh really this week of like making these videos, whether it's, you know, describing the kind of formats I need or, you know, that you don't want to have text in certain areas because it'll be cut off or natural kind of break points or how to do captions. Um, it's, you know, literally I just I had this massive thread where I did a few of these videos and there was so much essentially like bespoke knowledge and this process built up that I was like, "Hey, can you make a plugin out of this?" And there's actually a plug-in creator skill um in the chatbt app. So, it's pretty easy. And then I did a few tweaks and now I just more reliably get, I guess, the the happy path that I want.

</details>

**Claire**: 你能展示一下它的产物吗？我知道你昨天完成了一个视频。

<details>
<summary>Original English</summary>

**Claire**: And can you show us an out? I know you did one of these for yesterday. Can you show us like what what the kind of output is that you can get?

</details>

**Nick**: 这是我当时的初始提示词，正如你们所见，我只是把一堆源片段扔了进去。另外有一点很酷，比如寻找特定的时间段或者删除废片这些非常耗费体力的事，只要我们愿意放手让它做，它就会做得很出色。这是在旧金山或纽约找公寓的视频片段。当时我坐在 Uber 上，在手机上给它发指令说：“噢对了，我还需要一条 4:5 的输出。”它回复说：“好的，已更新输出矩阵。”最后输出的效果非常棒。

<details>
<summary>Original English</summary>

**Nick**: Yeah. So, here was my starting prompt. Again, I just dumped in a bunch of clips. And one thing I want to know, you talked about like the tedious stuff. Even like little things like going through and deleting bad takes or finding like the right segments. I I feel like I'm I'm so willing just to hand that over. And and just get that off my plate. I don't want to think about it. So yeah, I I I started with a pretty similar prompt. I just I kicked off with a little bit for before at one point and actually I was in an Uber. I said this on my phone. I remembered I was like, "Oh yeah, I need I need a 4x5 also." So I I sent that in as like a steer and it was like, "All right, got it. Updating the updating the delivery matrix." And then this is actually where, you know, I was like, "Why don't you ask me questions?" So I had to update the plugin um at the same time. And this is what the output looks like. So this is actually a few few different like you know back and forth steers. Um here we'll actually haven't like watched this full one but we'll see how it looks.

</details>

**Codex**: “现在在旧金山和纽约市找公寓太疯狂了，而且根本不可能在所有房源失效之前就把它们看完……”

<details>
<summary>Original English</summary>

**Codex**: It's insane trying to find apartment in SF or New York City right now and it's impossible to get to all the listings before they're gone.

</details>

**Nick**: 另外有趣的一点是，你们可能注意到了，它甚至在画面里的敏感地址上自动加了模糊遮罩。

<details>
<summary>Original English</summary>

**Nick**: So what's what's funny I don't if you can see that it's it even added blurs to these addresses here.

</details>

**Claire**: 太智能了，我已经看到它了。

<details>
<summary>Original English</summary>

**Claire**: Real smart. No I can see it.

</details>

**Nick**: 是的，我上周做了几个准备发在 Instagram 上的视频，我的 Slack 里弹出了很多敏感数据和内部材料。而 ChatGPT Work 在画面上进行了一种近乎像素级的极其细致的红线规避工作：当我滚动屏幕时，模糊遮罩会自动跟着运动，而且它会多次自我验证和重新检查，直到确保没有任何机密信息泄漏。

<details>
<summary>Original English</summary>

**Nick**: Yeah. Um, I actually I did like a couple of these for like that were releasing like on Instagram next week and there's like sensitive like release material information by Slack that it like bubbled up in my chatbt work and it did this like insanely granular work of like blurring out literally lines and then following it while I'm scrolling and it does all this like verification where it it adds these blurs. It checks its own work and then it like does that over and over again until it's good and then it gives you like, you know, a good result.

</details>

**Claire**: 我在大约 6 个月前甚至专门写过一个处理视频打码的脚本，因为我们的播客嘉宾经常在演示代码时忘记隐藏他们真实的 API Key，这让人极其头疼。我现在一定要用 Codex 重新做这件事，因为之前最难的部分就是如何让遮罩动态跟着滚动的屏幕做追踪。这个功能太棒了，谁愿意去干这种枯燥的打码工作呢。

<details>
<summary>Original English</summary>

**Claire**: I probably six months ago coded a redactic for the How AI podcast because I had so many people being like, "Whoops, I left like my API key open in that like one piece of code that we were talking about." And so we actually like built one. Um, I need to try it again with codecs because it's probably I the one challenge we have is the blurs following kind of like screen shares. But yeah, and actually that gets back to the like I don't my I don't even want to deal with the tedious work. Like not only actually it's a non-starter that I'm going to make blurs automatic like do that manually. That's just that's not going to happen.

</details>

**Nick**: 确实，没有人会想手动去打码。更烦人的一点在于，你每次导出视频还要拼命检查“这里面到底有没有机密数据，我怎样才能既打上码又让内容看起来很真实”，把这些复杂的判定直接甩给大模型来监控，简直拯救了我的大脑。

<details>
<summary>Original English</summary>

**Nick**: No. What's even more annoying though is having to think about all right well how do I generate outputs that don't have confidential information and how do I still make it seem genuine that's also a pain that I just I don't think about I just I leave it to leave it leave it to the chat GBT app

</details>

**Claire**: 对于广大的内容创作者来说，用 AI 剪视频还有一个隐藏的心理好处：剪辑自己的视频通常会让人感到非常尴尬。你不得不坐在一块大屏幕前看自己录下的各种蠢样，纠结“这一条我是不是表现得很傻，那一条我说的话逻辑是不是不通”。将这种评判性、批判性的挑选工作分流给一个局外的中立 AI 代理来干，能让我们这些创作者少受很多自我怀疑和心理尴尬的折磨。

<details>
<summary>Original English</summary>

**Claire**: I'm going to give one other benefit for the content creators out there for this like AI editing of content which is it's real embarrassing to edit your own content. It's like really embarrassing to look at yourself and watch all these videos of yourself and be like, "Oh yeah, I was like real cute and funny in that one and that one I am not like I make no sense as a human." So I like to offload like the critique of myself and the critique of my performance off to another model so I don't have to look at my face so much as well, especially as like a solo creator, solo founder, somebody who's like working on their own work. So, I do like having a third, you know, like a neutral third party do these cuts so I don't have to sit there and like listen to my own videos all day.

</details>

**Nick**: 哈哈，非常赞同，这能极大地降低人们创作视频内容的门槛。比如前天我在一个半小时的时间里录制了 3 条视频，共上传了 50 或 60 个短片，然后我把每一条视频背后大概的逻辑描述了一下。虽然由于运算量大，我当时先去睡觉了，但第二天起来，我想要的一切都已经准备好了。我们几天前已经在 Instagram 上直接发布了其中一条成片。

<details>
<summary>Original English</summary>

**Nick**: Yeah, I know. It's it's it's great. Um, back to like the it like it definitely lowers like the bar like the barrier to entry for stuff like this and if I just need to like go to a park, you know, I recorded like three videos. I recorded to three videos over the course of like an hour and a half couple days ago. And then I uploaded like 50 or 60 clips. And I dictated like what the different narratives for those three videos were and because I have a plugin and a task that already understands what I want. You know, it took a while. I I went to bed and I came back to it, but I had I had the I had what I needed and we actually shipped one to our Instagram a couple days ago.

</details>

---

### 多代理协作与部署

**Claire**: 好的，我还有一个关于视频编辑的问题，然后我们可以看看那个网站是不是建好了。在这个流程中，你必须使用 **Soul Ultra** 吗？因为我在你屏幕下方的界面看到了它。

<details>
<summary>Original English</summary>

**Claire**: Okay. I have one more question on this and then maybe we'll see if the if the website is up. Do you need Soul Ultra for this? Because that's what I see below.

</details>

**Nick**: 是的，必须用。因为在处理视频时会涉及极多繁复的子任务——检查每一帧视频帧、检验和对齐字幕转写等，这涉及到海量的并行处理以及大量的“并行决策判定”。**Soul Ultra** 本质上是一个面向多代理并发控制的微框架。通过它，代理的协作会更加高效，输出的成片精度也更高。

<details>
<summary>Original English</summary>

**Nick**: Yeah, I would. Um, in my experience, there's just so many, as much as anything, just for speed. There's so many little like micro tasks involved in checking all these frames, in checking these transcripts, and there's a lot of parallel processing that can happen and a lot of like parallel judgment, if you will. And what soul ultra is is it's basically this framework for multi-agent um for 56 soul. And so I find that it's just more efficient and I get better outputs when I use Soul Ultra.

</details>

**Claire**: 太酷了。那让我们来看看《How I AI》的展示网站是否已经跑起来了。天啊，看！就是黑白加紫色的配色！这正是我刚才描述的样式（笑）。而且它甚至还利用 AI 自动筛选出了哪几张视频封面拥有最高的潜在点击率。我们完全没有动手，它就自己在后台建成了。

<details>
<summary>Original English</summary>

**Claire**: Love it. Okay, cool. Let's see if the How AI website is is up and running. Look at that. Black and purple and white. Just like I said, [laughter] [gasps] we also have AI identify which thumbnails are going to do the best. This the by the way, this episode, just so you know, it's all look no hands. We had some problems.

</details>

**Nick**: 哈哈，我看清了，这就是把所有的具体应用案例在网页上完美还原了。我们之前甚至还在讨论，是否可以通过调用图像生成模型（DALL-E 等）来为每一小段视频切片生成专属的全新独特封面。

<details>
<summary>Original English</summary>

**Nick**: Oh, I see what it is. It's the use cases. So, each episode is showing up multiple times. That was a very good episode about codeex browser use where I let it shop for me for my Hawaiian vacation. Um, and it did quite quite a lovely lovely job.

</details>

**Claire**: 完美的创意。既然网站建好了，你能演示一下你是如何把这个站点发布和共享出去的吗？

<details>
<summary>Original English</summary>

**Claire**: Yeah. Yeah, lovely job. If you if we want to get really fancy, we could probably have it have different thumbnails for each clip. We could even have like use image gen to make like a, you know, a singular thumbnail.

</details>

**Nick**: 没问题。比如我想现在把这个站点共享给你。我只需在界面上点击“分享”，然后输入你的邮箱或者选择完全公开。如果选择了通过邮箱进行权限过滤，那么输入邮箱即可，对方只需直接通过他们的 ChatGPT 账号进行登录，就能无缝查看你为他们定制的这个站点了。

<details>
<summary>Original English</summary>

**Nick**: Yeah. So let's say and let's say I wanted to like share this with you. Um I can say share this. And so now you can you can put in you know whoever you really want to. It could be totally publicly available. You could add um individual individual email addresses. And it'll share with those folks.

</details>

**Claire**: 这非常完美。那么登录方式就是直接用 ChatGPT 的 SSO 登录对吗？

<details>
<summary>Original English</summary>

**Claire**: Amazing. And then how do you log in?

</details>

**Nick**: 是的，直接使用 ChatGPT 账号安全登录即可。

<details>
<summary>Original English</summary>

**Nick**: Uh it's login with Chat GBT.

</details>

**Claire**: 太棒了，我的这个邮箱名下正好有一个现成的 ChatGPT 账号，可以直接登录（笑）。那么我们来整体回顾一下我们今天讲的几个核心场景：我们展示了语音编排层的高带宽交互（即 Yappers API），演示了如何让后台代理连接外部浏览器去处理日常中极度讨厌的琐碎流程（如查阅日程并订票打折）；我们展示了 ChatGPT Work 拥有的沙盒式自主运行计算机的能力；最后还展示了我最中意的 UGC 视频剪辑与动态敏感数据打码模糊的自动化流程。

<details>
<summary>Original English</summary>

**Claire**: Great. Easy peasy. I do have a Chat GBT account underneath that email [laughter] address. So we are we are good to go. Um, just to recap, we did a couple use cases. So, we talked a little bit about voice, high bandwidth, Yappers API, um, just basically like talking to a computer empowered assistant that can just go do a bunch of your work for you, um, with access to browser and other things, including just being able to screenshot whatever's on the screen and have context. We did a um an a tragic bee site which I did not know it has its own computer and memory and browser and all that stuff. So that's fun fact for Claire. Um or you can have it actually go off and make a website which you can share publicly or share with specific email addresses which you just showed. And then again, my favorite use case, which is take a bunch of clips um for UGC, dump them in, make it the model's problem, including doing redaction and blurring, which is for any of my fellow YouTubers out there, a a huge and very annoying issue. And I'm very happy um personally to have seen this this workflow and get it solved.

</details>

---

### AGI 时代的人机共生展望

**Claire**: 好的 Nick，在结束之前是我们的闪电提问环节。第一个问题：在所有人都在享受 ChatGPT 强大的语音交流功能时，OpenAI 的办公室里是不是也到处都是人在对着电脑自言自语？我们如何在这种“语音控制一切”的未来，与现实世界中觉得这种碎碎念非常烦人的其他人共存？

<details>
<summary>Original English</summary>

**Claire**: Um Nick, a couple questions uh lightning round questions for you. We will get you back to all your all your voice chatting. Question number one is on that topic. In this world where we're all loving our Chad GBT voice experience, are is everybody in the open AI office just like mumbling to themselves and to their computer? Like how are we going to intersect all this voice capability with the realities of like existing around humans that find all this chitter chatter annoying? Like how does it actually work?

</details>

**Nick**: 这是一个非常现实甚至有些尴尬的问题。当我在家的时候，我基本上百分之百通过口述和语音来操作。但当我在办公室，工位周围都是人时，我有时会尽量压低声音小声嘟囔，但更多时候我还是会乖乖退回到键盘打字模式。我们办公室有很多隔音电话亭和会议室，我发现最近人们频繁钻进这些小舱体，并不是为了打电话，而是为了能无拘无束地在里面对着 Codex 和 ChatGPT 进行长篇累牍的语音听写和规划。显然大家都意识到语音是非常高效的，但我们目前的开放式办公基础设施显然没有为此做好准备。也许未来的解决方案是大家戴上那种隔音口罩，这样别人就听不见我们的声音，只有我们的 AI 代理能听清。

<details>
<summary>Original English</summary>

**Nick**: I think it's like a like an almost genuinely uncomfortable question because when I'm at home, I exclusively dictate and when I'm at my desk around other people, I will sometimes whisper, but I'm more likely to like use my keyboard. And you know, we have all these meeting rooms and these like little pods people hop into. And I see people like hopping in there for not calls more often these days because they're they're clearly going in there to like use dictation or to use voice and codecs. And clearly people are adapting to this as like a better experience. But frankly, we you know, I don't know if the answer is we all walk around like with those masks around us that like shield our voice to anybody but the agent, but it's it's not ideal right now. But you can but we can tell that there there's a there's a better there's a good version and that's using voice but it's not ideal for our current you know office makeup infrastructure.

</details>

**Claire**: 哈哈，我想象的画面是：我们按下一个按钮，然后天花板上会降下来一个透明的防噪玻璃罩把我们罩住。

<details>
<summary>Original English</summary>

**Claire**: Yeah I I imagine we like press a button and like a tube comes down

</details>

**Nick**: 没错，那会是极度理想的开放工位设施。在最终的 2027 年发布脑机接口（Direct Brain-Codex Link）之前，我们可能确实得需要这些物理隔音罩来过渡（笑）。第二个问题呢？

<details>
<summary>Original English</summary>

**Nick**: that would be ideal. Yeah that's that's what I'm talking about press our button and the tube the tube goes up. Okay. We're going to we're going to figure this out um until we get the direct codeex to mind connection which I'm sure will be a 2027 release. Okay. Um, second question.

</details>

**Claire**: 如果人们想要在当下的生活和工作中，切实地“触碰到 AGI（感觉 AGI 正在来临）”，在过去的这三个月里，除了语音功能外，你认为最能体现这一飞跃性变化的具体是什么？

<details>
<summary>Original English</summary>

**Claire**: If if people really wanted to like feel the AGI, what are what are the things that you really think are just huge step changes in the last 3 months? Maybe like voice aside, what is like the one thing that you would tell people to try or that you're really thinking is is the new interface because there's so many things that you've shown here

</details>

**Nick**: 关于“触碰 AGI 的时刻”。像你我这样的人可能在 2022 年或 2023 年 ChatGPT 刚发布时，就经历过第一波“AGI 幻觉”了，那是一种“原来有一个 AI 能够理解并极其智能地回答我说的每一句话”的认知冲击。而对于开发者和极客群体来说，真正的“AGI 降临时刻”可能是在各种编码代理平台（Coding Agent Harness）成熟的时刻：在这个时刻，你突然发现 AI 可以直接脱离对话框，真正走入你的文件系统、读写文件、操作终端并在失败时自己查错并自我修复，你只需下达一个宽泛的命令，它自己就会解决所有其他的事情，这对技术人来说是震撼的。但以前这仅局限于一小群技术开发者。如今在网页端和移动端推广的 **ChatGPT Work**，正是把那些极其强大的后台代理（Coding Agent Harness）原语进行了普惠和轻量化，让任何不具备代码背景的普通人直接通过手机就能使用。比如只需绑定 Gmail 和金融账号，代理每天自动检查两次邮件和账单，一旦有任何异常开销，你的手机上就会弹出提示。这种长驻型的 AI 代理会成为越来越多普通人真正触碰到 AGI 的门槛。

<details>
<summary>Original English</summary>

**Nick**: in terms of like in terms of feeling the AGI. I think a lot of people like you and me have already felt the AGI. I think if we go back to you know 2022 2023 around the release of chatbt. I think a lot of people felt the AI then you know what what AI can be became understandable like you understand this conception of a a chatbot that I say things to and it intelligently says say says things back to me. That's that's pretty cool. And then I think with the advent of Kodi agents and like the Kodi agent harness in particular, I think people in the developer community and like AI tinkerers, they felt this AGI moment where wow now now this AI is going out and like reading files and creating files like running commands and this is crazy how I tell it to do I I tell it one thing and then it figures out all these other things on its own and that was a huge AGI moment for people. But I do think there is a certain barrier like barrier to entry with that where if you're not an engineer or you're not a thinker, you know, there's this is limited to a smallish group of people. But now, you know, with something like chat GBT work in the web, I think we're taking a lot of the primitives um you know, like the coding agent harness, like having an always on agent and we're making them not only accessible to the web, but they're accessible to your phone. And so for people that are already using the chat GBC app, which is a lot, they can just switch over to the work tab, they can ask a question like, "Hey, can you check my Gmail and also my finances?" Um, which I know are two, you know, plugins that you can install really quickly and just monitor those and let me know if anything stands out or anything has gone arry. And now they suddenly have this agent that's, you know, maybe twice a day checking their email, checking their finances. And I think that like small thing, you know, when they first get a notification, you know, letting them know maybe a package has arrived or there's some weird charge. I think those are like the small moments that people might kind of like it might be like a foot in the door for a lot of people.

</details>

**Claire**: 精彩。最后一个问题，我问过每一位来播客的嘉宾：当我们面对 AI 拒绝配合、没有按照预期生成回答或没有正确调用插件时，你个人的提示词策略是什么？你会对他吼吗？会敲大写字母吗？

<details>
<summary>Original English</summary>

**Claire**: Okay. Amazing. And then I have one last question I ask every guest and because you speak to AI, I'm really curious here what what you say. when I I saw a little bit of your prompting strategy. It's a little bit of what I do, but when AI is not responding, when it is not doing what you want, when it is not using that plugin, what is your prompting strategy? Do you yell? Do you all caps?

</details>

**Nick**: 哈哈，这取决于我当时是在办公室还是在自己家的客厅里，我对 AI 的态度会有很大的不同（笑）。如果是在办公室，我可能会疯狂敲击键盘，用全大写字母（ALL CAPS）去“质问”它。如果是在家里，我会直接按下语音键，甚至夹杂几句脏话去纠正和引导它重新回到正确的运行轨迹上。

<details>
<summary>Original English</summary>

**Nick**: Well, it depends if I'm sitting on my desk or if I'm in my living room. Those are [laughter] I guess the my treatment of of AI is different. [laughter] Um, it might be all caps in the office as I like bang on my keyboard. at home I'll turn on dictation, maybe share a few expletives. try to redirect things.

</details>

**Claire**: 我也类似，我常常直接且愤怒地打字对它说：“这做得很垃圾，你为什么会犯这种低级错误？”我过去对大模型态度非常温和礼貌，但现在的自动化工具把我的标准拉得非常高，我常常冷冷地回复：“你其实可以做得更好，别偷懒。”不过最近随着各种更新，大模型的表现越来越稳定，我最近反而比较少生它的气了。

<details>
<summary>Original English</summary>

**Claire**: I'm just like constantly constantly being like, "This is trash. Why Why are you Why are you this way?" Um, I used to be so polite and now my bar is so high. I'm like, "You you can do better. I believe in you." I would say lately I feel like I have been less upset. Um things are just working better, you know.

</details>

**Nick**: 我最近生气的频率反倒变高了。因为我的预期阈值被拔高了，我知道它完全有能力完成这件事，当我发现它没有达到预期时，我会非常失望：“你明明很聪明，为什么现在表现得像个傻瓜？快动动脑子。”

<details>
<summary>Original English</summary>

**Nick**: I've been more upset. Yeah, because my bar is higher. I'm like, I know you can do this. You're not a dumb dumb. Come on.

</details>

**Claire**: 理解。我们把它当成一个智力相等甚至更高等的个体在合作，所以当它达不到标准时就会格外失望。Nick，今天和你聊天太开心了，大家可以在哪里找到你，或者我们怎样才能在工作上帮到你？

<details>
<summary>Original English</summary>

**Claire**: I understand. Yeah. All right. Yeah. Treat it treat as equal or superior. You're surprised when it when it doesn't come through. Okay. Well, Nick, this has been super fun. Where can we find you? How how can we be helpful?

</details>

**Nick**: 好的，大家可以在 Twitter (X) 上找到我，我的 ID 是 `Nick Bowman_`。如果您对 Codex 和 ChatGPT Work、或者 OpenAI 最新发布的任何特性有想法或疑问，随时欢迎私信我，我的私信永远处于开放状态。Claire，很荣幸能和你一起录制这期播客。

<details>
<summary>Original English</summary>

**Nick**: Yeah. Find me on Twitter X um my name Nick Bowman_. Um if you have any questions about codeex chatbt work, anything we're releasing OpenAI, feel free to reach out to me. DMs are open. Great to uh great to be on with you, Claire.

</details>

**Claire**: 非常感谢 Nick 的到来，也特别感谢大家的收听与观看。如果你喜欢我们的节目，请在 YouTube 上一键三连（点赞、关注和订阅），或者更理想地，在下方留下您宝贵的评论。您同样可以在 Apple Podcasts、Spotify 等各大播客平台上搜索并收听我们的音频版。如果您能为我们写下评分或书写简短的评语，将帮助更多的人发现并爱上这档节目。您可以前往 our 官方网站 howiaipod.com 查看所有过往的精彩节目以及关于播客的更多背景介绍。我们下期节目再见。

<details>
<summary>Original English</summary>

**Claire**: Yeah, thanks for being here. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>