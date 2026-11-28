---
author: How I AI
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tvD1LY4InIk
speaker: How I AI
tags:
  - ai-productivity
  - custom-software-development
  - prompt-engineering
  - ai-orchestration
  - saas-future
title: 利用AI工具定制Slack收件箱与提升个人生产力
summary: 本期访谈中，**Claire Vo**和**Yash Tucker**深入探讨了如何利用AI工具，特别是**Perplexity Computer**，管理海量**Slack**通知并提升个人生产力。Yash分享了他如何通过**OpenClaw**和**Perplexity Computer**构建定制化的**Slack**消息摘要工具和仪表板，有效地分类和优先处理信息。讨论还涵盖了AI在定制软件开发中的潜力，以及其在日常生活（如社交活动组织）中的应用。最后，Yash分享了与AI协作的独特策略，包括如何有效提示和“威胁”模型以获得更佳结果。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Clay
  - Guru
  - Thought Spot
  - OpenAI
products_models:
  - Perplexity Computer
  - OpenClaw
  - Jarvis
  - Sonnet
  - Gemini
  - Opus
  - Notion AI
  - Chat GPT
  - Figma Make
media_books: []
status: evergreen
---
### AI赋能的Slack通知管理

**Yash Tucker**: 每天醒来，我真的会收到大约100到150条新的**Slack**通知。甚至不是说“哦，这些是未读频道”，而是真的有人@了我。其中60%到80%属于“仅供参考”（FYI）类别。所以，那100到150条让我焦虑的通知，实际上我真正需要处理的只有30到40条。你可以用AI为你完成任务，比如分类、总结，或者你可以用AI来构建一个工具，这个工具以前很难构建，现在通过非常直接的API和结构化数据就能实现。

<details>
<summary>Original English</summary>

**Yash Tucker**: I truly wake up to maybe 100 to 150 new **Slack** notifications. Not even just like, oh, these are unread channels. Truly, someone has tagged me. 60 to 80% are more in the FYI category. So, my 100 to 150 that's giving me anxiety is actually more like 30 to 40 that I really need to be on top of. You can use AI to do a task for you like categorize things, summarize things, or you can use AI just to build a tool that would have been much harder to build before with very straightforward APIs and structured data.

</details>

**Claire Vo**: 完全正确。想想看，就像一个**看板**风格的面板。左侧是红色的“需要行动，紧急，Yash需要尽快处理”；中间是黄色的“需要阅读”列；右侧是绿色的“简单轻松”——我有一堆FYI信息，我可以点击“全部存档”按钮，它们就会从仪表板上消失，**Slack**上的通知也会随之消失。

<details>
<summary>Original English</summary>

**Claire Vo**: Exactly. Think about like a **kanban** style board. You have in red on the left action required, urgent. Yash needs to get back to it. In the middle, we've got a yellow need to read column and then on the right in green much more easy. I have a bunch of FYIs. I can just go ahead and click this archive all button. They'll disappear from the dash. And then those notifications will also disappear on my **Slack**.

</details>

**Claire Vo**: 哇，这太神奇了。这是处理待办事项的绝佳方式。

<details>
<summary>Original English</summary>

**Claire Vo**: H that's magic. And this is such a better way to just get through your queue.

</details>

**Yash Tucker**: 我的梦想是有人看到这个视频后说：“我想在**Slack**之上构建那个应用。”然后我就可以每月支付那个人15美元，让这个应用得到维护和使用。这样我就可以向他们提交bug报告，而不必自己修复，因为我很乐意付钱给他们。

<details>
<summary>Original English</summary>

**Yash Tucker**: My dream is for someone else to watch this video and say, "I want to build that app on top of **Slack**." And then I can go pay that person $15 a month for this app to be maintained and used. And then I can file bug reports with them instead of having to fix it myself because I would happily pay them.

</details>

**Claire Vo**: 欢迎回到《How I AI》。我是**Claire Vo**，产品负责人兼AI狂热者，致力于帮助大家利用这些新工具更好地进行开发。今天我们邀请到了**Clay**公司的教育主管**Yash Tucker**，他是一位超级优化者，将向我们展示他是如何使用**Perplexity Computer**来处理每天收到的数百条**Slack**消息的。我们还将讨论**SaaS**是否真的已经消亡。让我们开始吧。本期节目由**Guru**赞助，它是您公司知识的AI真相层。问题在于：您的AI的效果只取决于您输入的信息质量。大多数公司从AI那里得到的答案自信但却是错误的，因为他们底层知识是过时的、不完整的，或者根本不正确。错误的信息不仅会拖慢您的速度，还会让您付出金钱，并使您面临风险。**Guru**通过在您公司的知识和AI工具之间添加一个验证层来解决这个问题。**Guru**不会让您仅仅希望AI能给出正确答案，它会自动对内容进行准确性评分，标记过时信息，并确保您的团队每次都能获得可靠的答案。它能与您已经使用的工具协同工作，因此您无需改变工作方式。成千上万的公司信任**Guru**来确保他们的AI准确无误且合规。准备好不再用公司的知识玩俄罗斯轮盘了吗？请访问getguru.com了解更多。欢迎来到《How I AI》。Yosh，我太激动了。我们几个月来一直试图促成这次访谈，而且几个月来一直试图通过**Slack**来促成。我喜欢的是，我们这次节目的开场将从你如何从每日如潮水般涌来的**Slack**消息、邮件和待办工作中脱身开始。

<details>
<summary>Original English</summary>

**Claire Vo**: Welcome back to How I AI. I'm **Claire Vo**, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have **Yash Tucker**, head of education at **Clay** and he is a hyper optimizer showing us how he uses **Perplexity Computer** to work through the hundreds of **Slack** messages he gets every day. We're also going to debate is **SAS** really dead. Let's get to it. This episode is brought to you by **Guru**, the AI layer of truth for your company's knowledge. Here's the problem. Your AI is only as good as the information you feed it. Most companies are getting confident but wrong answers from AI because their underlying knowledge is outdated, incomplete, or just plain incorrect. Bad information doesn't just slow you down. It costs you money and puts you at risk. **Guru** solves this by adding a verification layer between your company's knowledge and AI tools. Instead of just hoping your AI gets it right, **Guru** automatically scores content for accuracy, flags outdated information, and ensures your team gets trustworthy answers every time. It works with the tools you already use, so you don't have to change how you work. Thousands of companies trust **Guru** to keep their AI accurate and compliant. Ready to stop playing Russian roulette with your company's knowledge? Visit getguru.com to learn more. Welcome to How I AI. Yosh, I'm so excited. We've been trying to make this happen for months and we've been trying to make it happen over **Slack** for months. And what I love about that is what we're going to start this episode off with is how you get yourself unburied from the deluge of **Slack** messages and emails and work you have to do on a daily basis.

</details>

**Yash Tucker**: 是的。我真希望我们组织访谈的时候我就已经构建了这个工具，但这也许能让你更理解我为什么老是跟丢**Slack**上的对话。就上下文而言，你现在可以看到我的**Slack**屏幕。就在现在，我两小时前刚清空了它，但已经又收到了40多条消息，其中有8条以上是私信。而且这个数字还会继续上涨。我每天醒来真的会收到大约100到150条新的**Slack**通知。这甚至不是说“哦，这些是未读频道”。是真的有人@了我。这是一条私信，他们@了我。或者是一个群组私信或其他什么，所有这些都感觉非常重要，但在**Slack**中，并非所有通知都是平等的。例如，我更关心回复你关于安排播客录制的事情，而不是我同事在“有趣的狗狗”频道里分享的关于他们狗狗的有趣评论。但我会收到两者的平等通知。所以，大约一个月前，当**Perplexity Computer**发布时，我开始思考，如果我真的可以自己设计任何软件或范式，我会怎么做，为什么，以及如何做？所以**Perplexity Computer**实际上并非我们最初解决**Slack**问题的方式。我们稍后会回到那个话题。但我认为框架也是最重要的，我需要能够设想一个更好的世界是什么样子，而不是仅仅询问**Claude**或**Perplexity**或**OpenClaw**来让我的**Slack**更轻松。所以，我设想的那个更好的世界是：如果并非所有通知都是平等的，那我能否更好地根据私信、群组私信、话题讨论和群组@提及来分类我的通知，因为我对这些的处理方式都不同。我试图尽快清理我的私信，因为我告诉所有人，如果我24小时内没有回复，就给我发私信。所以那种紧迫性是必需的。但除此之外，当然，人们也会给我发私信，讨论一些随机的事情，比如这周末谁想去跳舞，这周谁想去吃火锅之类的各种有趣的事情。所以，即使在这四个类别中，即私信、群组、话题讨论、应用@提及，我还想进一步细分：哪些需要我实际行动？哪些我需要阅读但可能不需要回复？以及哪些是“仅供参考”的通知？你可能已经猜到了，我先透露一下：我每天60%到80%的通知都属于“仅供参考”类别。所以那100到150条让我焦虑的通知，实际上我真正需要处理的只有30到40条。这让事情变得容易得多。但我需要建立一个系统才能实现。所以，如果我能复述一下你的问题，你在工作中非常重要，而且也非常有趣和受欢迎，这给你带来了大量的@提及，你将向我们展示你如何使用**Perplexity Computer**。尽管我想你最初是用其他方式开始解决这个问题并进行原型开发的。

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah. So, I wish I could say I had built this back when we were organizing it, but maybe that gives you a little bit more leeway for understanding me losing **Slack** threads all the time. For context, you can see my **Slack** screen right here. Right. Right now, I cleared this truly 2 hours ago, and I already have like another 40 plus messages of which you can see like eight or more are DMs. Uh, and it's just going to keep going up right now. I truly wake up to maybe 100 to 150 new **Slack** notifications. It's not even just like, oh, these are unread channels. Truly, someone has tagged me. It's a DM, they've tagged me. It's a group DM or something else, which all feel very important, but not all notifications are created equal in **Slack**. For example, I care much more about getting back to you on scheduling our podcast recording than I do about my colleagues really fun comment on their dog that they posted a photo of in the fun dog channel. But I get an equal notification for both. And so what I sort of started doing with **Perplexity Computer** when it came out about a month ago is thinking if I could truly just design any software or like paradigm myself, what would I do, how, and why? And so **Perplexity Computer** is actually not exactly how we initially solved the **Slack** problem. We'll come back to that in just a second. But I think the framework is also what matters most is I needed to be able to envision what does a better world look like instead of just asking **Claude** or **Perplexity** or **OpenClaw** make my slack easier. And so that better world that I thought of is if not all notifications are created equal then what if I could better categorize my notifications by DMs versus group DMs versus threads versus group at mentions because I treat all of those differently. I try to clear my DMs ASAP because I tell everyone if I'm not responding within 24 hours, DM me. So that urgency needs to be there. But then on top of that, of course, people are DMing me about random things like who wants to go dancing this weekend, who wants to go to dinner for hot pot this week, and all sorts of other fun things. So even within each of those four categories, right, the DMs, the groups, the threads, the app mentions, I also want to subcategorize by what requires real action from me. What do I need to read but maybe doesn't need a response from me? And what are more of the like FYI for your information notifications? And as you might guess, a little precursor that I'll give you is like 60 to 80% of my notifications every day are more in the FYI category. So my 100 to 150 that's giving me anxiety is actually more like 30 to 40 that I really need to be on top of. And that makes things a lot easier. But I need to build a system to get there. So, if I could repeat your problem back to you, you're very important at work and also super fun and popular and this is just causing you tons of adventions and you're going to show us how you use **Perplexity Computer**. Although I think you started with something else to kind of solve this problem and prototype your way out of it.

</details>

**Claire Vo**: 完全正确。我认为我要给出的另一个通用框架是，我确实认为我在团队中指导很多人的一点是，何时纯粹将AI用作MCP（多功能计算平台），以及何时用AI来构建确定性的东西，比如代码或API调用。举例来说，在**Slack**中，有足够多的API端点可用，我们知道我应该能够仅仅使用代码来构建信息组织系统。

<details>
<summary>Original English</summary>

**Claire Vo**: Exactly. I think the other like general framework I'll give here is that I do think something that I coach a lot of people on my team about as well is when to use AI purely like an MCP even versus when to use AI to build something deterministic like code or an API call. Uh and so for example here in **Slack** there's enough API endpoints available that we could get into that I know I should be able to build the information organization organization system just using code and so actually I did that via my little we can do a detour here **Jarvis** my **OpenClaw**.

</details>

### 使用OpenClaw构建Slack摘要

**Yash Tucker**: 我们来看看我是否能找到我的对话。这是一个非常长的对话，我们可以回到**Slack**的顶部查看。我不会全部过一遍，但你可以大致看到，它正在为我构建摘要，对吗？它会查看时间戳，我想要标记什么？例如，**Slack**有一个完整的“信息图表”，我们可以找到它并放入这里，如果我们想了解他们如何构建通知系统。这是非常有意的。它是否未读，或者它给你多少数字，都取决于消息流入的流。所以对我来说，要实际拉取（并非**Slack**中的每一条新消息，因为那会让人不堪重负），而是只拉取我关心的消息，并且只带着我关心的上下文，这需要一点系统思考。我需要查看我上次查看消息是什么时候。我只看了最近的消息，还是之前看过话题中的另一条消息？因为那样我不需要看全部，我只需要看最近的消息。所以所有这些数据都通过这些时间戳在**Slack**中被跟踪。你可以看到我在这里和**Jarvis**来回讨论了很长时间，关于什么是未读，什么不是，我如何查看这些频道。这个来回的讨论持续了数千条消息。所以我们不会全部过一遍。我花了一整天的时间来真正进行原型开发、构建和理解，以达到一个点，公平地说，现在那100多条通知会进入**Slack**中的这个**Jarvis**摘要频道。它确实会将其分组为直接@提及。你有三个子类别。然后是私信。然后是群组提及。然后是话题讨论。所以这是四个主要的类别。然后，在每个类别中，我现在可以（我花了一周时间这样做）直接点击这些，打开一个新的话题讨论，决定何时需要回复，进入，回复，然后再返回。

<details>
<summary>Original English</summary>

**Yash Tucker**: let's see if I can even find my here we go thread it's a very long thread that we can come into all the way up on **Slack**. I'm not going to go through and do all of this, but you can sort of see in here at a quick glance, it's building the digest for me, right? So, it's looking at, okay, what is the timestamp? What do I want to mark? For example, **Slack** has a whole info chart that we could find online and then put in this if we wanted to on how they've built their notification system. It's very intentional. Whether or not it's unread or gives you a number or how many numbers it gives you is all dependent on the stream in which it comes in. And so for me to actually pull not every single new message in my **Slack** because that would be overwhelming, but to only pull the ones that I care about with only the context that I care about requires a little bit of just systems thinking. I need to look at what was the last time I looked at the message. Did I look at only the most recent message or have I looked at another message in the thread before? Because then I don't need to see the whole thing. I just need to see only the most recent messages. So all of this data is tracked in **Slack** via these timestamps and you can see me going back and forth with **Jarvis** here for a long long time on what is unread, what is not, how do I look at these channels and so this back and forth which truly goes on for like thousands of messages. So we won't do all of it. Took me like a full day to really prototype and build and understand to get to a point where to be fair. Now those 100 plus notifications come in to this **Jarvis** digest channel in **Slack**. It does group it into direct at mentions. You've got those three subbuckets. Then we've got DMs. Then we've got group mentions. And then we've got threads. So those are the four overall buckets. And then within each of those buckets, I could now, and this is what I did for a week, just commandclick into each of these, open up a new thread, decide when I need to respond, come in, respond, then go back.

</details>

**Claire Vo**: 为了那些可能没有观看YouTube视频的人，我来大概描述一下我们在这里看到的内容。你基本上是说，你看，我从**Slack**收到了一个包罗万象的收件箱，里面有通知和未读消息。我收到了数百条，其中可能只有二三十条对我来说是真正有趣的。我对如何在我自己的工作流中组织和优先处理这些消息有非常清晰的认识。我将启动**OpenClaw**作为一个编码代理，在**Discord**中。我想我看到了**Discord**。为什么是**Discord**呢？快速解释一下。我选择**Discord**的一个原因是，我最初在**Telegram**上使用**OpenClaw**，就像很多人一样，但我真的很喜欢**Discord**的话题讨论性质，它可以组织我所有的聊天。例如，在**Discord**中，我最喜欢的命令，类似于**Slack**，是Command K。然后我可以快速查找、快速搜索我想要的任何话题讨论。我可以在需要时获取上下文，并且我可以打开和关闭这些话题讨论，以便在哪些需要保持活跃、哪些需要保持非活跃方面，保持得非常整洁。

<details>
<summary>Original English</summary>

**Claire Vo**: Just to kind of narrate for people that are maybe not watching the YouTube what we're seeing here. You basically said, look, I get this allpurpose inbox from **Slack** with notifications and unread. I get hundreds of them, of which maybe two dozen are actually interesting to me. I have a pretty clear sense of how I want those organized and prioritized in my own workflow. I'm going to spin up **OpenClaw** as a coding agent in **Discord**. I think I spotted spotted **Discord**. And why **Discord** real quick? So my one reason for **Discord**, I started on **Telegram** with **OpenCloud** like I think many people do, but I really like the threading nature of **Discord** for organizing all of my chats. For example, in **Discord**, my favorite command, similar to **Slack**, is command K. And then I can quickf find, quick search any thread that I want. I can pick up the context where I need to and I can open and close those threads to keep it really clean in terms of what I want to stay active and what I want to stay inactive.

</details>

**Claire Vo**: 太棒了。所以你用**OpenClaw**和**Discord**基本上是在说：“嘿，我知道我们可以逆向工程**Slack**如何确定未读消息以及如何分类它们，这对于人类来说会非常痛苦，因为我必须深入研究文档，阅读大量内容，记住所有这些代码，非常烦人。你去搞定这些。我们会来回沟通，然后我们将构建这个自动化的**Slack**摘要信息流，它每天会推送一个非常精准的未读列表，再次按以下方式分组：直接发给我的消息、发给群组的消息、我在工作中关心的频道中的消息、以及我不在工作上关心的频道中的消息。然后，即使在这些分类中，它们也是有优先级的，并且是深度链接的。所以你实际上可以点击进入那个深度链接，采取行动，然后退出，像处理一个有优先级的电子邮件收件箱或任务列表一样，处理你的收件箱。”

<details>
<summary>Original English</summary>

**Claire Vo**: Great. So you used **OpenCP** claw and **Discord** to basically say, "Hey, I know we can reverse engineer how **Slack** determines what unread messages are and how they categorize them, which would be incredibly painful as a human because I'd have to go like kneede in the docs, read a bunch of stuff, memorize all these codes, super annoying. You go figure that out. We're going to do a back and forth and then we're going to build this automated **Slack** digest feed that pushes every day a very targeted list of unreads grouped by again things that are coming directly to me, things that are coming to a group, things that are in channels I care about for work, things that are in channels I don't care about for work purposes. And then even within that, they are prioritized and then they're deeplin. So you can actually go into that dean fleek, take action, bop out and and work through your through your inbox almost like a prioritized email inbox or a task list.

</details>

**Yash Tucker**: 完全正确。我只想补充一点，你刚才描述的几乎所有内容，虽然是用AI构建的，但AI在所构建系统中的反复使用仅限于对需要我采取行动、需要阅读和仅供参考（FYI）的消息进行分类。所有其他内容都是使用AI助手构建的定制代码，但在输出到摘要中的分类方面，它仍然是确定性的。这恰好回到了你之前说的观点，即你可以用这两种方式使用AI。你可以用AI为你做任务，比如分类或总结，或者你可以用AI来构建一个工具，这个工具以前很难构建，现在通过非常直接的API和结构化数据就能实现。

<details>
<summary>Original English</summary>

**Yash Tucker**: Exactly. The only thing I would add to your great narration is that it's important to also note that pretty much all of what you just described, while built with AI, the only place in which AI is repeatedly used in the system that was constructed is in the categorization of messages that need action from me, need to be read, and are FYIs. Everything else is custom code built using an AI assistant, but is truly still deterministic in the categorization that gets put out into the digest. And that just goes to your earlier point of like you can use AI in these two ways. You can use AI to do a task for you like categorize things or summarize things and or you can use AI just to build a tool that would have been much harder to build before with very straightforward APIs and structured data.

</details>

**Claire Vo**: 完全正确。

<details>
<summary>Original English</summary>

**Claire Vo**: Exactly.

</details>

**Claire Vo**: 好的。然后，你知道这很棒。对我这个天真的人来说，它仍然让人感到非常不知所措，对吧？它就像一个非常长的清单。所以，你接下来采取了什么措施，让它在你的日常工作中变得更可用？

<details>
<summary>Original English</summary>

**Claire Vo**: Okay. And then you know this is this is great. It's still you know to my to my uh naive eye it's still pretty overwhelming, right? It's like a really long list of things. And so what was the next step you took here in terms of making this even more usable for you in your day-to-day?

</details>

### Perplexity Computer的独特优势

**Yash Tucker**: 是的。所以，就上下文而言，对于那些没有观看YouTube的人来说，这条消息很有帮助，但我必须向下滚动至少四到五个屏幕才能看到所有已经为我总结好的通知。所以你也可以想象我的真实**Slack**会糟糕多少。我用了它大约一周，它更有效，但也让人筋疲力尽。所以我的愿望变成了：如果我能拥有一个真正的软件，可以在此基础上构建一个看起来整洁、用起来像电子邮件的**Superhuman**、具有导航功能，并且能让我将这个冗长的文本和表情符号摘要分类成一个真实的界面，那该多好。这就是我们引入**Perplexity Computer**的地方。所以我会在这里打开**Perplexity Computer**。你实际上可以在这里看到，这就是我最终构建的摘要。我们首先会向你展示我构建这个摘要的话题讨论。所以这个话题讨论也有相当多的来回沟通，但你刚才看到的内容（我稍后会为没看视频的人描述）的80%是在前四条消息中构建的。我认为这实际上值得深入探讨一些细节，对吧？我要求它分析摘要频道中的消息结构，因为通过连接器和浏览器，它可以访问我正在查看的所有内容。然后，我认为**Perplexity Computer**非常出色的一点，也是**Perplexity**独有而**Claude**或**OpenAI**（因为它们是前沿模型公司）不具备的，就是它们毫不避讳地使用所有不同的AI模型，按顺序构建任务的每个部分。所以你可以在这里看到，为了获取摘要，它使用了**Sonnet 4.6**。然后你甚至可以在这里看到，我相信它开始并行运行不同的任务，你可以看到它在某个时候使用**Gemini**进行规划。你可以看到它使用**Gemini**用Python进行编码。你可以看到它正在读取它正在构建的不同技能。然后它使用**Opus**进行实际构建，因为那更复杂，它需要更好的推理层。我可以一直往下说，所有这些工作都发生在我发送第一条消息之后。所以，它有一个额外的故障排除、智能和某种测试层，用于判断我是否正在构建正确的东西，这消除了我作为人类在循环中不断回去说“呃，你做得很好，但它不起作用，它甚至没有按照我要求的去做，再试一次”的需求。那种令人沮丧的、我必须反复重新提示的循环，在**Computer**中要好得多，因为它构建了这种集成编排。所以让我们花一分钟谈谈**Perplexity Computer**，因为我们从未在播客中看到有人演示过这个工具。那么，为什么你选择它，而不是把它放到**Claude Code**或**Codeex**中（正如你所指出的，它们在模型方面是单一提供商有其局限性）？你还展示了你使用**OpenClaw**完成了类似的任务。什么吸引了你选择**Perplexity Computer**，你认为它的设置有什么独特之处？是的，这是个好问题。所以，我认为可能有三点真正吸引我使用**Perplexity Computer**，从简单到稍微复杂一些。最愚蠢但最简单的一点是并行运行任务，对吧？在**Cloud Code**和**Codeex**中，我仍然主要进行基于聊天的来回对话。所以，我一次只做一件事，但通常我可能想启动一个任务。如果我真的想在**Cloud Code**中，我可以在单独的终端窗口中做到这一点，但这很烦人。我实际上可以只启动。你甚至可以在屏幕上看到，对吧？我今天早上在10分钟内启动了大约四个不同的任务，然后让它们同时运行。所以这是我认为非常简单的一点，但并行运行和长时间运行的任务在**Perplexity Computer**中非常好用。第二点是，**Claude**、**Co-work**和**Codeex**都有这些连接器，它们可以访问你不同的应用程序，但它们主要用于代码生成。它们是为应用制作而构建的。我实际上会说，**Perplexity Computer**虽然经常用于构建这些用户界面和任务，而且那些是你可能在用例中看到的炫酷东西，比如很多人都在构建应用程序，因为每个人都用应用程序来思考，但它实际上远不止于此，就像人们发现**Cloud Code**不仅仅能编程，它还是一个非常好的本地代理。但我喜欢**Perplexity Computer**的元素，实际上是因为它在云端。因为它在云端，它与所有这些不同的工具的连接更加原生。我不需要像给**OpenClaw**那样，给它访问不同技能的权限，让它去软件中做事情。它可以直接去做，并且让我自己进行登录。而且这种与所有这些工具的原生连接帮助我能够以思维的速度更流畅地完成事情，因为所有内容都被记录下来了。所以，一个非常简单的例子（我实际上不小心删除了，但我可以快速讲一下），就是我也用**Notion AI**来记录我所有的会议笔记。**Perplexity Computer**连接到**Notion AI**。所以我在所有会议中总是做的事情就是说：“嘿，这里有很多我们可能应该做的后续工作。让我们确保把它们都做完。”我试图把我认为最重要的那些放到我的任务管理中。但因为有转录，它在**Notion**中，而且**Computer**可以访问**Notion**，我就可以进入**Computer**说：“今天一天结束后，查看我所有的会议记录。收集行动项列表。分类你认为重要的行动项，如果它们是长期行动项，就把它们放到我的**Asana**中，然后对于任何只是消息、通知或电子邮件的内容，为我起草回复。”

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah. So for context, right, for anyone that's not watching the YouTube as well, this message is helpful, but I have to scroll at least four to five screens down just to be able to even see all of the notifications that are already summarized for me. So you can also imagine just how much worse my actual **Slack** is. I used this for like a week and it was more effective, but it was also just draining. And so then my wish became, what if I just had an actual software that I could build on top of this that looked clean, felt like **Superhuman** for email, had navigability, and let me sort of categorize this long digest of just text and emojis into a real interface. So that is where we come into **Perplexity Computer**. And so I will pull up **Perplexity Computer** here. And you can actually see right here, this is the digest that I ended up building. What we'll first do is even show you the thread in which I built this digest. So this one also had a fair bit of back and forth, but 80% of what you just saw, which I'll describe for people not watching in a second, was built in like the first four messages. And I do think this is actually worth digging into some of the guts, right? I'm asking you to analyze the message structure in the digest channel because via connectors and the browser it has access to everything that I'm looking at. And then what I think is so good about **Perplexity Computer** that is unique to **Perplexity** and not **Claude** or **OpenAI** because they are frontier model companies is that they are shameless about using all of the different AI models to build each part of the task in subsequent order. So you can see here for fetching the the digest it was using **Sonnet 4.6**. Then you can even see down here I believe it starts running different tasks in parallel and you can see that it's using **Gemini** I believe for planning at some point. You can see it's using **Gemini** for coding in Python. Uh you can see it's reading different skills that it's building. It then uses **Opus** for the actual build because that's more intense and it wants a little bit of a better layer of reasoning. And I could just keep going down and down. All of this work happens from just my first message. So there's a additional layer of troubleshooting and intelligence and sort of testing for am I building the right thing that removes the need for me as a human in the loop to constantly go back and say uh you tried good job but also it doesn't work like it literally doesn't even do what I asked you to do try again. that frustrating I have to reprompt you loop over and over again is much much better with **Computer** because of how they've built this ensemble orchestration. So let's take a minute to talk about **Perplexity Computer** because we haven't actually seen anybody demonstrate this tool on on the podcast and so why you know above dropping this in quad code or codeex which as you called out has its limitations in terms of being single provider in terms of model you know you showed you used **OpenClaw** as well to do a similar task. What has drawn you to **Perplexity Computer** and what do you think is unique about the setup? Yeah, it's a good question. Right. So, I think there's probably three things that really draw me to **Perplexity Computer** ranging from like simple to a little bit more involved. The silliest but simplest one is running things in parallel, right? In **Cloud Code** and **Codeex**, I'm still having essentially a chatbased back and forth conversation. And so, I'm doing one thing at a time, but often I maybe want to kick off a task. I could do this in separate terminal windows if I really wanted to for **Cloud Code**, but it's annoying. I can actually just kick off. You can even see here in the screen, right? I kicked off like four different tasks in the span of 10 minutes of each other this morning and then had them all running at the same time. So that's one thing that I think is very simple, but concurrent runs and long running tasks are really nice in **Perplexity Computer**. Number two is that **Claude**, **Co-work**, and **Codec** sort of have these connectors so they can access your different apps, but they're primarily built for code generation. They're built for app making. I would actually say **Perplexity Computer** while used often to build these UIs and tasks and like those are the fancy things you might see if you go to use cases here like a lot of people are building apps because everyone thinks in apps it's actually far greater than that sort of in the same way that people discovered **Cloud Code** can do so much more than just coding it's a really good local agent but the reason I like the **Perplexity Computer** element is actually because it's in the cloud because it's in the cloud it is much more natively connected to all these different tools I don't have to go give it the in the way that I give **OpenClaw**, right? Like access to different skills to be able to go do things in software. It can just go do it and ask me for login on my own. And that native connection to all those tools helps me be able to do things much more fluidly at the speed of thought because everything is being recorded everywhere. So like a really easy example that I actually deleted because it was an accident, but I can just talk through real quick is I also use **Notion AI** to record all of my meeting notes. **Perplexity Computer** is connected to **Notion AI**. And so what I am always doing in all of my meetings is saying, "Hey, here's a bunch of follow-up things that we should probably do. Let's make sure we get them all done." I try and put all of those most important ones in my task management. But because that transcription exists, it's in **Notion** and **Computer** has access to **Notion**, I can then also go into **Computer** and say, "Look through all of my meeting transcripts from the end of the day today. Gather the list of action items. categorize the ones that you think are important, throw them into my **Asana** if they're longer term action items, and actually for anything that's just a message or a notification or an email, draft me the response."

</details>

**Claire Vo**: 你能给我们展示一下你经常使用的连接器吗？这样大家就能了解你在说什么。哦，你用了所有这些连接器。

<details>
<summary>Original English</summary>

**Claire Vo**: Can you show us what connectors you you're using regularly, just so people can have a sense of what you're talking about? Oh, you're using like all of them.

</details>

**Yash Tucker**: 太多了。我的意思是，甚至还不到全部，对吧？但对于所有听众，我只列出最基本的。我有**Google Drive**、**Gmail**和**Calendar**、**Notion**、**Asana**、**Slack**、**Forms**、**Tasks**、**TypeForm**、**Zoom**、**Spotify**（我没怎么用过，但觉得会很有趣），**AirTable**、**Google Slides**，还有很多我没在用的，比如**Linear**、**Superbase**。我还考虑过更多使用**Snowflake**、**Data Dog**，但我现在只关注我目前实际能从中获得价值的工具，而不是追逐我所谓的“闪亮物件症候群”。所以总有一天我可能会回到所有这些“闪亮物件”，但目前这些是我获取最大价值的来源。

<details>
<summary>Original English</summary>

**Yash Tucker**: So many. I mean, not even close to all of them, right? But to for everyone listening, I've got the bare basics. **Google Drive**, **Gmail** with **Calendar**, **Notion**, **Aana**, **Slack**, **Forms**, **Tasks**, **Type Form**, **Zoom**, **Spotify**, which I haven't really used, but I thought it would be fun, you know, **Air Table**, **Google Slides**, and then there are tons of other ones I'm not using like **Linear**, **Superbase**, uh, I've looked at trying to use maybe like **Snowflake** more, **Data Dog** more, but I'm focusing really just on what am I actually getting value out of today instead of chasing I have what I would call shiny object object syndrome. So one day I'll maybe get back to all the shiny objects, but for now this is what provides the lion share of the value back to me.

</details>

**Claire Vo**: 太棒了。然后，我们再把话题回到最初的讨论。你向我们展示了**Perplexity Computer**。你非常喜欢它。多模型、多线程并发、易于使用、丰富的连接器。你一开始快速展示了，但现在让我们展示一下你为**Slack**管理工具构建的东西，因为我认为它真的很酷。

<details>
<summary>Original English</summary>

**Claire Vo**: Great. And then just to kind of like loop the thread back to what we originally talking about. So you shown us **Perplexity Computer**. You really like it. Multimodel, multi-threaded concurrency, nice to use, lots of connectors. Um and then you you flashed at the beginning, but let's just show what you built for that that **Slack** management tool because I think it's really cool.

</details>

### 定制化的Slack管理界面

**Yash Tucker**: 是的。所以我会尽力为那些没有观看视频的人进行视觉描述。你可以想象一个仪表板UI。它看起来有点像你以前用过的任何任务管理工具。想象一下一个**看板**风格的面板，但不是任务的多个卡片，你只有三个主要的。左侧是红色的“需要行动，紧急，Yash需要尽快处理”；中间是黄色的“需要阅读”列，我应该确保我理解这里发生了什么，但我可能不需要回复；右侧是绿色的“简单轻松”，我有一堆FYI（仅供参考）信息。比如“这是晚餐是什么”，“这是地址在哪里”，“这是有人为我们刚刚计划的发布会做了什么”。然后我在这里定制了许多其他更小的表盘。所以我可以像我们之前讨论的那样，按操作顺序分组。我想先处理我的私信吗？我想先处理我的群组@提及吗？我左侧有一个侧边栏可以对它们进行分类。然后，对我来说，这个仪表板最棒的地方是，我一直都在使用它。右侧的FYI通知，我可以点击“全部存档”按钮。它们就会从仪表板上消失，然后那些通知也会从我的**Slack**中消失。

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah. So, I'll I'll do my best to visually describe this for those not watching. You can imagine a dashboard UI. It looks sort of like any task management tool you've had before. Think about like a **kanban** style board, but instead of multiple cards for all the sections of tasks that you've got, you've just got three main ones. You have in red on the left action required, urgent, yash needs to get back to it. In the middle, we've got a yellow need to read column. I should make sure that I'm understanding what's going on here, but I probably don't need to respond. And then on the right in green, much more easy, I have a bunch of FYIs. Hey, here's what dinner is. Here's where the address is. Here's what someone is doing for the launch that we just planned. And so then there's a bunch of other smaller dials that I've customized on here. So I can group this like we were talking about earlier by order of operations. Do I want to go through my DMs first? Do I want to go through my group mentions first? I have a sidebar on the left that I can categorize those by. And then the best thing about this dashboard for me is that I use this all the time. The FYI notifications on the right. I can just go ahead and click this archive all button. They'll disappear from the dash and then those notifications will also disappear on my **Slack**.

</details>

**Claire Vo**: 哇，这太神奇了！因为我知道在**Slack**里你可以“标记所有为已读”，但你不能说“标记我的私信为已读”或者“标记FYI为已读”，也不能多选。所以你只能面对要么一百条未读消息，要么零条。没有中间状态。这是一种更好的方式来处理你的待办事项。还有一件事我想说，就是关于“**SaaS**是否已死？”、“**SaaS**末日正在发生吗？”、“谁将构建新的、更好的**Slack**？**Slack**会是新的**Slack**吗？”这种没完没了的争论。我喜欢这个时刻，它表明**Slack**仍然很棒。

<details>
<summary>Original English</summary>

**Claire Vo**: H that's magic because I know you can in **Slack** I think you can do like mark all as red, but you can't be like mark my DMs as red or mark FYI as red or like multi select. And so you're sitting there with either like a hundred unread messages or zero. There's nowhere in between. Um, and this is such a better way to just get through get through your queue. And one thing I have to say was like there's this incessant debate of like is **SAS** dead? Is this like **SAS** apocalypse happening? Like is is who's going to build the new **Slack** that's better? Is **Slack** the new **Slack**? And what I love about this moment is like **Slack** is still great. Like it's

</details>

**Yash Tucker**: 它非常棒。

<details>
<summary>Original English</summary>

**Yash Tucker**: it's so good.

</details>

**Claire Vo**: 它非常适合发送消息。我不知道它是否非常适合阅读消息，但它非常适合发送给我。

<details>
<summary>Original English</summary>

**Claire Vo**: It's great for sending messages. I don't know if it's great for reading messages, but it's great for sending me

</details>

**Yash Tucker**: 你可以以非常低的成本说：“我公司正在使用**Slack**。我们总体上对它感到满意，打分是10分中的N分。为了让它达到10分，我将构建一个符合我思维方式的东西。”这甚至不一定是因为现有软件的不足。它只是要弥合你作为个体理想工作流与你从**SaaS**中获得的东西之间的差距。我只是觉得这是一种非常有趣的模式，当我们思考这些生产力工具将变成什么样？这些协作工具将变成什么样？是否有像**Slack**核心版，然后是**Slack**定制版，对吧？你只需在其之上构建。我非常同意。我实际上会说，也许我这里有一个非常大胆的看法。我认为我们将看到软件的爆炸式增长，因为它可以使用所有这些工具来创建和使用。我不认为普通人，甚至熟练的人，会通过构建和编码所有这些工具来开始定制。我也不认为AI的智能，至少以我们目前看到的速度，会达到一个点，让我的妈妈可以进去说“让**Slack**变得容易”，然后它就能构建出这个。我认为相反，会发生的是，你会像你所说的那样优化这些工具。我坦白地说，如果有人看到这个视频，然后说“我想在**Slack**之上构建那个应用”，那将是我的梦想。然后我可以每月支付那个人15美元，让这个应用得到维护和使用，然后我就可以向他们提交bug报告，而不必自己修复，因为我很乐意付钱给他们。

<details>
<summary>Original English</summary>

**Yash Tucker**: and you can with a very low effort say my company's is using **Slack**. We're happy with it generally n out of 10. And to get it to 10 out of 10, I'm just going to build the thing that works with my brain. And it doesn't even have to be about a deficiency of the existing software. It just has to be, you know, closing the gap between your ideal workflow as an individual and what you get out of **SAS**. And it's I just think it's such an interesting model as we think about like what are these um what are these productivity tools going to become? What are these collaboration tools going to become? Um is there like, you know, **Slack** core and then **Slack** custom, right? And you just build on top of it. I yeah I so agree. I would actually say maybe my very hot take here. I think we will see an explosion in software being created and used because of all these tools. I don't think the average person or even the proficient person is going to start custom by building and coding all these tools. I don't think the intelligence of AI at least the way we're seeing it ramp currently is getting to a point where my mom could go in and say make **Slack** easy and then it builds this. I think instead what will happen is you sort of like you were saying optimize these tools and I'll be so honest if someone else my dream is for someone else to like watch this video look at this and say I want to build that app on top of **Slack** and then I can go pay that person $15 a month for this app to be maintained and used and then I can file bug reports with them instead of having to fix it myself because I would happily pay that.

</details>

**Claire Vo**: 我同意，我觉得很有趣的是，我作为一个B2B领域的从业者，长期以来一直从事产品工作。客户总是有很多长尾需求，比如“我真的很希望这个页面左下角的按钮能为我特定行业做一些非常小众的事情，那会很棒。什么时候能加入路线图？”而一个理性的**SaaS**产品经理的回答是“永远不会”。现在你可以用这种方式替换这个概念，用一个部署好的工程师来处理，然后说“我们永远不会为你构建这个。这是你自己的问题，宝贝。但我可以告诉你如何自己实现。”然后，再次，是的，我同意你的观点。我认为会发生两件事。第一，就像你说的，会有更多创造性的软件开发机会，比如有人可能会看这个视频，然后说“是的，我要把**Slice Slack Digest**作为一个产品来构建。”第二件事是，这个产品的潜在市场（TAM）可能很大，而且因为构建成本如此之低，谁会在乎呢？有人可以把它变成每月1万美元或2万美元的项目。它不必达到风险投资的规模。它不必达到10亿美元。它不必拥有百万用户，但仍然可以很有用。

<details>
<summary>Original English</summary>

**Claire Vo**: I I agree and it's I what I think is so funny is I'm like a B2B girl. I've done product for a long time. There has always been this longtail cue of like customer requests being like, I would really just love it if that button in the bottom left of this page to this very niche thing for my specific vertical like that would be great. When's it on the road map? And the answer is a reasonable **SAS** PM is like never. And now you can kind of like replace this concept with okay point a deployed engineer at that and say like we're never going to build that for you. That's a you you problem, babe. But let me show you how you can get that on your own. And then again, yes, I agree with you. I think kind of like two things are going to happen. One, just so many more creative opportunities for software to be built just as you said, like somebody maybe will watch this and be like, "Yes, I'm going to build like **Slice Slack Digest** as a product." Um, the second thing is like there's probably like TAM of this big for that product and because the cost of building it so low, who cares? Like somebody could go turn it into a 10K a month like project or a 20k a month of project. Doesn't have to be venture scale. Doesn't have to like hit a billion dollars. Doesn't have to have a million users and can still like be useful.

</details>

**Yash Tucker**: 而且我觉得我们本可以拥有很多有用的软件，因为构建它们曾经太昂贵了。不值得人们投入时间。我完全同意你的观点。让我们做更多。

<details>
<summary>Original English</summary>

**Yash Tucker**: And I feel like there's so much useful software that we could have because it's been so expensive to build. and not worth people's time. And I am just I'm with you. Like let let's go do more.

</details>

**Claire Vo**: 同意。

<details>
<summary>Original English</summary>

**Claire Vo**: Agreed.

</details>

**Claire Vo**: 是的。然后，你知道，**Slack**就可以做那种，嗯，像这样把他们“收编”的事情。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. And then you know then **Slack** can do the thing where they just go like this and like scoop them up.

</details>

**Yash Tucker**: 完全正确。**Slack**就可以收购所有那些人。我认为你会看到一次“寒武纪大爆发”，那些没有风险投资就无法存在的企业，或者人们不想去构建的企业，现在可以自己赚钱或者被大公司收购。谁知道呢？

<details>
<summary>Original English</summary>

**Yash Tucker**: Exactly. **Slack** can then acquire all those people. I think you'll see a **Cambrian explosion** of like businesses that wouldn't have existed without venture funding or that people wouldn't have wanted to build that can make their own money or get acquired by larger companies. Who knows?

</details>

**Claire Vo**: 是的。是的。呃，我的意思是，这基本上就是我现在正在做的事情。所以，就像我正在身体力行。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. Yeah. Uh that's I mean that's basically what what I'm I'm doing right now. So, it's like I'm I'm living it.

</details>

**Claire Vo**: 嗯，我喜欢这个。这真是个天才想法。人们，思考这个想法。我经常告诉人们，

<details>
<summary>Original English</summary>

**Claire Vo**: Um, I love this. This is genius. People take this idea, think about the most or I I I often tell people

</details>

### AI与“反待办事项清单”

**Yash Tucker**: 去建立他们的“**反待办事项清单**”，然后每天花一小时来清空那个清单。比如，我再也不想以非优先顺序浏览我的**Slack**未读消息了。这将被列入我的“**反待办事项清单**”。所以，我将每天花一小时尝试找出如何解决这个问题。另一个例子是，我再也不想手动删除邮件中的垃圾邮件了。我经常需要手动勾选并删除。所以我从不想。那么我如何解决这个问题呢？我再也不想手动将会议后的行动项输入**Asana**了。所以“**反待办事项清单**”这个想法（我可以分享，我有一个包含大约一百个可以列入“**反待办事项清单**”的想法），花时间用AI自动化这些事情是非常值得的。

<details>
<summary>Original English</summary>

**Yash Tucker**: to build their anti-to-do list and then spend an hour a day burning down that list, which is like I never ever ever want to go through my **Slack** on Reds again in an unprioritized way. That's going to be on my anti-to-do list. So, I'm going to spend an hour a day trying to figure out how to like dig myself out of that problem. Another one like I have is I never ever ever want to delete spam out of my email by hand. Like I I so often have to go through and like click the check boxes and delete. So I never So like how do I solve that problem? I never ever ever want to like manually, you know, hand to a sauna enter my action items after a meeting. And so this idea of an anti-to-do list, which I can share, I have a like a list of like a hundred ideas that could go on an anti-to-do list and spending time with AI to automate those is such a worthy use of time.

</details>

**Claire Vo**: 完全同意。我认为**Computer**可能是人们用更少资源做更多事情的旅程中的又一步。

<details>
<summary>Original English</summary>

**Claire Vo**: Totally agreed. And I think **Computer** is maybe another step in the journey of people just being able to do more with less.

</details>

**Yash Tucker**: 是的，它只会越来越好。本期节目由**Thought Spot**赞助。产品负责人深知这种困境：用户需要数据洞察，但他们不想离开你的应用去寻找。**Thought Spot embedded**通过将分析直接嵌入到你的产品中来解决这个问题。你的用户可以用简单的英语搜索并即时探索数据，就在他们工作的地方。没有单独的工具，也没有上下文切换。**Thought Spot**的独特之处在于它不仅仅是另一个附加仪表板。它是一种搜索驱动的AI驱动体验，感觉与你的应用原生集成。开发者只需几行代码即可嵌入它，然后完全自定义外观和感受。结果是，用户参与度更高，决策更快，每次用户登录时，产品都能提供更多价值。如果分析正成为你产品战略的核心，请访问go.thspot.com/howi了解更多信息，并访问go.thpot.com/howi/trial试用免费版。好的。所以，你是一个专业用户。你认为**Computer**还有其他有用的用例吗？你还构建了其他以前无法实现的美观UI吗？

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah, it's just it's all getting better. This episode is brought to you by **Thought Spot**. Product leaders know the struggle. Your users want data insights, but they don't want to leave your app to find them. **Thought Spot embedded** solves this by putting analytics directly into your product. Your users can search in plain English and explore data instantly, right where they work. No separate tools and zero context switching. What sets **THS spot** apart is that it's not just another bolt-on dashboard. It's a searchdriven AI powered experience that feels native to your app. Developers can embed it with just a few lines of code and then fully customize the look and feel. The result, more engaged users, faster decisions, and a product that delivers more value every time someone logs in. If analytics is becoming core to your product strategy, visit go.thspot.com/howi for more information and try the free trial at go.thpot.com/howi. thoughtpot.com/howi/trial. Okay. So, you are a prouser. Any other use cases for **Computer** that you think are useful? Any other like beautiful UIs you've built that you wouldn't have been able to do before?

</details>

### AI驱动的信息整合与设计原型

**Yash Tucker**: 是的。所以，我实际上会展示我构建的另一个，然后我会展示我团队中有人构建的另一个，因为我认为我正试图让每个人都思考并使用这些工具，而且它们都是不同类型的用例。所以我想我的情况不出所料，也属于Yash信息太多，Yash想尽快整合信息并提供帮助的主题。所以，我在这里可以向你展示的，类似于**Slack**摘要。我首先只是想确保“好吧，我真的把正确的东西放进这个摘要了吗？”然后才花更多时间试图让它变得美观。所以我有很多**Slack**和电子邮件。我意识到我因为深陷**Slack**和电子邮件，所以停止了阅读新闻。所以我想把一些新闻放进去。我实际上可以，而且将来可能会添加其他一些通信流，但目前我只想把这三个放进去。所以，我花了两天时间让文本在这里运行。然后我心想：“好吧，文本，和**Slack**一样，也很无聊。为什么不编写一个UI呢？”我得说**Computer**似乎默认提供**看板**风格的漂亮UI。我们这里有另外三个**看板**卡片。它按照AI、新闻、电子邮件和**Slack**的顺序排列，根据什么需要我采取行动。显然，这与我的**Slack**摘要机器人有一点点**维恩图**的重叠，但如果我只想整合到真正关键的任务，这也非常好用。在向人们讲解这里的迭代过程时，我可以告诉你，第一步是将文本放进来，然后说：“哦，那实际上不是一条重要的消息。你能告诉我你是如何那样分类的吗？”然后向**Computer**解释如何重新构建它用于进行所有这些分类的后台技能。第二步是将其UI放进来。第三步是实际可用性。所以，当我最初拥有UI时，它并没有想到默认地将我链接到所有消息，以便我能回去查看它们。所以我提出了要求，现在在**Slack**通知上，我可以链接回去了。我必须回去为电子邮件添加此功能，然后为新闻添加。但这样它就成为了我所有想查看内容的真正指挥中心。我还会给你一个有趣的提示，我看到有人在X上发帖说，他们让他们的**Claude**构建了一个类似报纸风格的摘要，其中包含**Claude**（也就是**Claude Code**）所做的所有事情。所以也许你可以把这个做成一个有趣的报纸风格，你每天早上醒来阅读，或者像一本杂志一样。

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah. So, I'll actually show one other one that I've built and then I'll show one that like someone on my team has built as well because I think I'm trying to get everyone to be thinking about and using these tools and they're both sort of different use cases. So I think mine unsurprisingly falls in the same thematic form of Yash has too much information and Yash wants to consolidate the information and be really helpful as quickly as possible. So what I can show you here is similar to the **Slack** digest. I first just wanted to make sure okay am I actually getting the right things into this digest before I spend more time trying to make it pretty. And so I have a bunch of **Slacks** and emails. I realized I stopped reading the news because I've been so deep in **Slack** and email. So, I want some news in there. And I could actually and probably will add a couple of other communication streams to this long term, but I just wanted to get those three in there. And so, I got a couple of days of the text working in here. And then I was like, okay, the text similar to **Slack**, also boring. Why not code up a UI? I will say **Computer** seems to default to **Canban** style pretty UIs. We've got another three **Canban** cards here. It goes in order of AI, news, email, and **Slack** in terms of what needs my actions. Obviously, a little bit of a **ven diagram** overlap with my **Slack** digest bot, but if I want to consolidate to just like truly mission critical, this is also really good. And in terms of talking people through what the iterative process here looks like, I can tell you, right, step one was getting the text in here and then saying, "Oh, that's actually not an important message. Can you tell me why you categorized it that way?" And then explaining to **Computer** how to rebuild the background skill it's using to make all of this categorization. Step two was then getting the UI in here. And then step three is actual usability. So when I had the UI in the first place, it didn't think to default link me out to all of the messages so that I could go back and look at them. So I asked to and now on the **Slack** notification, I can link back out to it. I have to go back and add it for email and then add it for news. But that way it becomes a real command center of all the things that I want to go see. I will give you one other fun tip which is I saw somebody on X posted that they had their **Claude** build a like newspaper style digest of all the things that the **Claude** like the **Claude code** had done. So maybe you could put this in like a fun newspaper style where you like wake up every morning and you read or like a magazine something

</details>

**Claire Vo**: 你真的醒来

<details>
<summary>Original English</summary>

**Claire Vo**: really you wake up

</details>

**Yash Tucker**: 额外，额外，Yash的一天进展如何。

<details>
<summary>Original English</summary>

**Yash Tucker**: extra extra here's how **Yasha**'s day is going.

</details>

**Claire Vo**: 完全正确。

<details>
<summary>Original English</summary>

**Claire Vo**: Exactly.

</details>

**Claire Vo**: 我非常喜欢那个想法。

<details>
<summary>Original English</summary>

**Claire Vo**: I like that idea a lot.

</details>

**Yash Tucker**: 把那个对话发给我。是的。

<details>
<summary>Original English</summary>

**Yash Tucker**: Send me that thread. Yeah.

</details>

**Claire Vo**: 是的。是的。是的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. Yeah. Yeah.

</details>

**Claire Vo**: 好的。所以我真的，我真的喜欢这个。而且，你知道，我们看到了很多这样的每日简报用例，我们看到的一切，从我通过**Cloud Code**在终端中得到非常冷冰冰的结构化**Markdown**（我把它储存在**Obsidian**中，因为我是一个神秘的、暗黑模式的思想家），到我只是使用**Chat GPT Pulse**，每天早上它都会给我发一些可爱又美好的东西，再到像这样的，我为自己构建了一个应用程序，它符合我使用它的心理模型，并为我进行了优化，我可以将其用作不仅仅是信息，而是一个互动式的工作指挥中心。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay. So, I I really I really like this. And again, you know, we've seen so many of these like daily briefing use cases and we've seen everything from like I get, you know, **markdown** very cold structured **markdown** in the terminal from **cloud code** that I like store in **Obsidian** because I'm like an esoteric, you know, dark mode thinker to, you know, I just use like **chat GBT pulse** and every morning it sends me something cute and nice to like this which is like I've built myself an app that again matches my mental model of how how I want to use this and is optimized for for me and I can actually use as not just um information but as an interactive kind of command center for my work.

</details>

**Yash Tucker**: 完全正确。我觉得你刚才提醒我的另外两点我想在这里提一下。第一点是，对于非技术出身的人来说，**Computer**的另一个好处是，即使我用**Cloud Code**或**Codeex**编写代码，我仍然需要把它放到**GitHub**仓库，仍然需要部署到**Vercel**，仍然需要确保它在某种形式下能在生产环境中运行。公平地说，这并不难做到，但它仍然是一个额外的技术层，我认为这还没有从这类软件的可用性中消除。对于**Perplexity Computer**来说，它已经部署好了。它已经在网上上线了，你可以在右上角看到这个按钮。我可以像我希望**Cloud Code**能为我构建一个可以分享的东西那样，直接分享它，就像**Cloud Artifacts**在**Cloud Chat**中做的那样。但再次强调，我的沮丧之处在于，我不想记住**Claude**的七个不同工具中的哪一个才能弄清楚我的用例是什么。而且我经常希望流畅地从一个工具开始，然后可能结束在另一个工具。

<details>
<summary>Original English</summary>

**Yash Tucker**: Exactly. And I think the thing that you just reminded me of like two other thoughts I'll mention here. Number one is the other benefit of **Computer** for the non-technically initiated is that even if I were to go code this up in **cloud code** or **codeex** I still have to go like put the **GitHub** repop. still have to deploy it to **versel** to still make sure that like it's all working in production in some way shape or form. Not that hard to do to be quite fair, but still just an extra technical layer I think that has not yet been removed from usability of that type of software. For **Perplexity Computer**, it's already deployed. It's already live on the web and you can see this button in the top right corner. I can just share it in the same way that like I wish **cloud code** built me something that I could share like **cloud artifacts** does if I go in **cloud chat**. But again, my frustration is I don't want to have to remember which one of **Claude**'s seven different tools to go into to figure out what my use case is going to be. And quite often I fluently want to start in one and then maybe end up in the other.

</details>

**Claire Vo**: 那么我的另一个问题是，因为这个应用是从电子邮件和**Slack**中提取信息的，我猜这个应用正在重用**Perplexity Computer**的连接器，还是你单独设置了那些认证令牌？

<details>
<summary>Original English</summary>

**Claire Vo**: And then my other question is because this is pulling from emails and **Slack**, I'm presuming this app is reusing the connectors from **Perplexity computer** or are you setting those authentication tokens separately?

</details>

**Yash Tucker**: 正确。所以这里所有的连接器都是**Computer**在该应用中使用的默认关闭设置。所以这真的非常酷。完全正确。它非常非常智能，因为即使我用**Codec**和**Cloud Code**中的连接器编写代码，我每次都必须设置Oauth。每次都是从头开始。

<details>
<summary>Original English</summary>

**Yash Tucker**: Correct. So all the connectors here are the default off for what **computer**'s using in that app as well. And so that's really really cool. Exactly. It's so so smart because even if I'm coding with connectors that I have in **codec** and **cloud code**, I have to set up O every single time. It's doing it all from scratch every single time.

</details>

**Claire Vo**: 嗯，关于**Computer**的另一件非常酷的事情是，它足够智能，如果Oauth不起作用，它会警告你。它会尝试重新认证，甚至会尝试在浏览器中完成，因为今天几乎所有东西都存在于网络上。所以它们仍然可以为你构建概念验证。

<details>
<summary>Original English</summary>

**Claire Vo**: Um and the other thing that's really cool about **computer** is it's intelligent enough that if the O isn't working, it'll warn you. It'll try and go reauthenticate and it'll even just try and do it in browser because almost everything exists on the web today. So they can still build you the proof of concept.

</details>

**Yash Tucker**: 那真是太好了。

<details>
<summary>Original English</summary>

**Yash Tucker**: That's good stuff. That's good stuff.

</details>

**Claire Vo**: 好的。嗯，只是为各位总结一下，我像AI专家一样敬畏地看着你，你得到了**Clairvo**两只手的体验。这意味着或者，太好了。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay. Um just to recap for folk I'm like staring in awe, you know, as as an AI person, you get like a **Clairvo** two hand experience. This means or so good.

</details>

**Yash Tucker**: 我喜欢。

<details>
<summary>Original English</summary>

**Yash Tucker**: Love it.

</details>

**Claire Vo**: 所以总结一下，你将使用**Perplexity Computer**为自己构建定制应用程序来处理工作，它具有大量开箱即用的连接器，既可以原生查询你的信息并为你提供答案，也可以作为应用程序的后端进行部署，这些个人生产力应用程序都针对你的工作流进行了优化。那么，你还想快速展示一个吗？是的，你刚才提到了我，提醒了我，我展示了很多信息整合流，因为那是我现在最关心的。但我也把**Computer**发给了我团队中一些善于钻研的人，我只是让他们去使用，问我问题，告诉我使用情况。我最喜欢的一个用例，我甚至自己都没想到，那就是我们有**Clay University**。对吗？所以给你举个例子，这样所有观看的人也能看到，对于那些没看的人，我来描述一下。我们网站上有很多关于如何学习**Clay**的内容，它的架构很好。我们的设计团队做得非常出色。向所有帮助过他们的人致敬。

<details>
<summary>Original English</summary>

**Claire Vo**: So just to recap, you are just going to build yourself custom apps for processing your work using **perplexity computer**, bunch of out of the box connectors that can be both used to just like natively query your information and give you answers as well as be deployed as the backend for apps, personal productivity apps that are optimized for your workflow. And then is there one more you want to quickly show? Yeah, you actually just reminded me as I you were talking about that that I showcased a lot of like information consolidation streams because that's what's most on my mind right now. But I've also sent **computer** to a couple of other people on my team that I know are good tinkerers and I've just been like use it, ask me questions, let me know how it goes. One of my favorite uses of this that I would never even have anticipated on my own is that we have **Clay University**. Right? So just to give you an example so that anyone watching can also see this and for anyone not watching I'll describe it to you. We have a lot of content on a website about how to learn **clay** and it's well architected. Our design team did a great job. Shout out to all of them on helping this.

</details>

**Yash Tucker**: 是的，如果我做的话，我以前确实做过，没人喜欢。

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah, if I had made it, I did make it in the past. No one liked it,

</details>

**Yash Tucker**: 对吗？但是这里有很多信息，而且它并不是真正基于角色或构建的。随着我们公司规模的扩大，现在我们正在根据我们构建的功能，扩展到不同行业和受众的更多细分市场，所以更有意义的是，如果你是**RevOps**，来到**Clay**网站学习大学课程，你从哪里开始呢？因为并非所有东西，类似于我的**Slack**通知问题，都对你来说是平等的，这取决于你在网站上的职业。这需要对这个网站进行一次重大的设计系统改造，而且需要大量的思考。我们教育团队没有人是设计师。我尝试用**Figma Make**（绝非贬低**Figma Make**）重新构建它。但问题是我必须重新描述所有内容给**Figma Make**，才能让它看起来与我们大学的设计一致。所以它无法吸收我拥有的那种视觉上下文层。我同事（向**Chris Ming**致敬）在这里做的非常酷的事情是，他进去说：“哦，**Perplexity Computer**可以在浏览器中访问它。它有所有不同的模型，所以它也应该能够在来回提示时视觉识别并理解。”所以他花了一个小时与**Computer**来回聊天。对于那些没看视频的人来说，它看起来并不那么漂亮，但它的功能性与我们试图设想的更接近。好的，现在如果我已登出，我可以看到所有这些不同基于角色的旅程。我有**SDR**、**BDR**、**RevOps**、**marketing ops**、**GTM engineer**，它甚至还在右上角构建了这个：登录后会是什么样子？所以现在**Sarah Chen**（随机姓名，不是真人），你完成了多少课程？根据你右上角显示的**RevOps**角色，你的下一门课程是什么？让我们看看你应该参加哪些研讨会。让我们看看有哪些同期班。所有这些都有助于我们的设计团队更快更好地理解我们在寻找什么。因为另一件让我一直感到沮丧的事情是设计团队和其他利益相关者之间的沟通鸿沟，因为他们知道自己需要做什么，但他们没有我们拥有的所有上下文。所以，能够在这两者之间建立一个视觉桥梁是非常有价值的。

<details>
<summary>Original English</summary>

**Yash Tucker**: right? But there's a lot of information here and it's not really persona based or built. And as we as a company have scaled and are now scaling into further segmentations of different industries and audiences and who we sell to based on the features that we've built, it makes more sense to say if you're in **RevOps** coming to the **Clay** website for university, where do you start? Because not all things similar to my **Slack** notification issue are created equal for you based on the profession you're coming into on the website. That's a major design system overhaul to take on top of this website and it takes a lot of thinking. We none of us on the education team are designers. I went into **Figma Make**, no shade to **Figma Make** to try and rebuild it. But the problem is that I had to like redescribe everything to **Figma Make** in order to even get it to look accurate to what we already had for designs on the university. So it's not able to ingest the sort of like visual context layer that I have. What was really cool about what my teammate shout out **Chris Ming** did here is he went in and said, "Oh, **perplexity computer** can access it in the browser. has all the different models, so it should also be able to visually recognize and then understand when I'm prompting back and forth. So, he took an hour just chatting back and forth with **computer**. It doesn't look as pretty for those not watching, but it's functionally much closer to what we're trying to envision. Okay, now if I'm logged out, I can see all these different persona based journeys. I've got **SDR**, **BDR**, **RevOps**, **marketing ops**, **GTM engineer**, and it even went ahead and built in this top right corner. What does it look like once you're logged in? So now **Sarah Chen**, random name, not a real person. Uh how many courses have you completed? What are the next courses for you based on you can see your persona on the top right being in **RevOps**? Let's look at what workshops you should go to. Let's look at what the cohorts are. And all of this helps our design team then better quickly understand what we're looking for. Because the other thing that I get frustrated with all the time is the like gap or the chasm in communication between design and any other stakeholders cuz they know what they need to do but they don't have all the context that we have. And so being able to build a visual bridge between those two is incredibly valuable.

</details>

**Claire Vo**: 我喜欢这个。好的。所以你在使用它，你也让你的团队使用它。它不仅仅是为了个人生产力。你可以用它来原型设计，引入现有网站，真正理解它们的上下文，然后构建一些东西，你可以用它来与你的跨职能合作伙伴沟通，以便更好地更快地完成工作。

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. Okay. So you're using it, you're getting your team to use it. It's not just for personal productivity. You can use it to prototype, pull in existing sites, really understand the context of them, and then build something that you can use to communicate to your cross functional partners to get work just done better and faster.

</details>

**Yash Tucker**: 完全正确。

<details>
<summary>Original English</summary>

**Yash Tucker**: Exactly.

</details>

**Claire Vo**: 我要给你一个赞美。我看了很多B2B网站，**Clay**的网站。非常漂亮。

<details>
<summary>Original English</summary>

**Claire Vo**: And I'm going to give you a compliment. I get I see a lot of B2B websites, **Clay**. Beautiful top.

</details>

**Yash Tucker**: 我一定会转达给团队。我一定会转达。

<details>
<summary>Original English</summary>

**Yash Tucker**: Definitely pass it on to the team. I would definitely pass.

</details>

**Claire Vo**: 它太美了。如果你没看过，去看看吧。如果你看过我的，嗯，我想那集是**Opus 46**与**GPT53**的设计对决，如果你仔细看，我重新设计了**chat PRD**网站，我说：“嘿，我喜欢**Clay**网站。以它为灵感。”所以，做得非常出色。好的。所以你是一个超级优化者。在进入闪电轮之前，你还想给我们展示其他用例吗？

<details>
<summary>Original English</summary>

**Claire Vo**: It's gorgeous. If you have not seen it, go go check it out. And if you have watched my um I think it was like my **Opus 46** versus **GPT53** design head-to-head episode, if you watch closely, I redesign the **chat PRD** website and I say, "Hey, I love the **Clay** website. Use that as inspiration." So, excellent work there. Okay. So, you are a hyper optimizer. Any other use cases you want to show for us before we get to our lightning round?

</details>

### AI的非工作用途与提示策略

**Yash Tucker**: 不，我们直接进入吧。让我们来闪电轮。所以我们在这里看到了很多个人生产力方面的工作。但你说，大约70%（我是这样记住的，所以这是事实）的人让你做的事情是去吃火锅，周末出去玩。你只是一个非常有趣的人。所以，你现在已经摆脱了**Slack**和电子邮件的困扰，你的摘要也处理好了，你的团队也在进行原型开发，那么AI在你的休闲娱乐方面有什么有趣的用例呢？我想我的前提是，我并不认为我像其他人那样对AI感兴趣，无论出于什么原因。我真的把AI当作一个工作工具。我有朋友沉迷于他们称之为**Chat GPT**聊天的东西，你知道，他们像是在进行个人对话。他们来回发送短信，然后把**Chat**的短信回复截图发给我，说：“看它有多棒。”出于某种原因，我在那里划清了界限，就像我不需要一个聊天治疗师。而且一半时间我都在向我的朋友指出，我不同意**Chat**所说的话。我认为它只是在那里支持你，而我在这里告诉你，那不是正确的支持。所以这是我先放在一边的一点。另一件我想说的是，我个人生活中最常使用AI来寻找乐趣，就是头脑风暴和研究。我喜欢游戏。我喜欢桌游。我喜欢活动。我喜欢运动。我和我的朋友每年都会举办冬季和夏季奥运会。我们现在还在举办春季和秋季奥运会，通常是一系列随机活动的混合。我们会玩套圈苹果，看谁能最快地从盒子里抽出所有餐巾。猜谜游戏真的很有趣。我们还会玩我从一个朋友那里学到的一个我最喜欢的游戏：一个包含10个东西的清单。你只需要猜测，它是一把剑、一条鱼，还是一碗汤？令人震惊的是，那一轮没有人得分超过40%。所以我们喜欢做这类活动，如果我有无限的时间，我只会把所有的脑力都花在思考如何让这些活动变得越来越有趣上，但大多数时候，我对自己想做的事情有一些想法。例如，上次我们和所有朋友一起举办的冬季奥运会，我知道我们想有两到三个带有讽刺意味的大学饮酒游戏的回顾。我们想有两到三个更有趣的对话游戏，也许还有两到三个真正的游戏。所以，我花了一很长时间和**Jarvis**进行头脑风暴，讨论我们以前做过哪些活动，它们的主题是什么，我们应该如何真正思考创新活动，结果几乎从来都不是我想要的完全一样，但它能让我进入思考过程，发现“哦，这已经很接近我想要的了。让我自己做最后的修改。”然后，它在组织所有这些活动的运营方面也非常出色。我们来了20个人。所以我们当时想非常刻意地分组。我让所有人两人一组，但我想让你全天都能和你的搭档之外的人互动。所以，对于每个4对4的游戏，我们轮流让哪些搭档和哪些搭档组队，形成超级搭档，然后进行比赛，这样你就能全天与其他人接触。所以我认为这真的非常有趣，我一直都在用这个。我实际上买了10个新的桌游，因为我昨天通过**Claude**发现了它们，我觉得它们看起来很有趣。所以，我觉得这很有趣。你不是我们播客中唯一的桌游玩家。我们实际上有一整集节目是关于两个朋友如何使用**Chat GPT**等工具在东湾开了一家桌游咖啡馆的。所以，呃，宅男们正在用AI玩桌游。

<details>
<summary>Original English</summary>

**Yash Tucker**: No, let's just go for it. Let's do the lightning round. So, we have seen a lot of personal productivity work here. But you said that like 70 I'm this is how I remember it. So, you know, we're gonna it's it's God's truth. Like 70% of what people are asking you to do is go get hot pot and like hang out on the weekend. You're just a very fun fun person. So, are there any fun, you know, now that you've dug yourself out of **Slack** and email and your digest and all your work's being prototyped by your team, what are your fun use cases of AI? I think my my preface to this is that I don't think I'm as fun as everyone else is with AI for whatever reason. Like I treat AI truly as like a work tool. I have friends who are like in they call **chat GPT** chat, you know, they're having like a personal conversation. They're sending text messages back and forth and then sending screenshots of chat's response to the text messages to me being like, "Look at how good it is." And for some reason, that's where I draw the line of like I don't I don't need a chat therapist. And also half of the time I'm pointing out to my friends that I would disagree with what **Chad** is saying. I think it's just there to support you and I am here to tell you that that's not the right support. So that's one thing I'll put aside. The other thing that I'll say I probably use it for the most in terms of like personal fun in my life is brainstorming and research. So I love games. I love board games. I love activities. I love sports. Me and my friends host like a winter and a summer Olympics every year. We're now doing a spring and a fall and it's typically a medley of a bunch of random activities. We'll do like apple bobbing, who can pull out all the napkins out of a box the fastest. Trivia is really fun. And we'll do like one of my favorite that I stole from a friend was a list of 10 things. You just have to guess, was it a sword, a fish, or soup? And shockingly, no one scored above a 40% on that round. Uh, so we love doing these types of activities that if I had infinite time, I would just spend all of my brain power thinking about how to make this more and more fun, but most of the time I have an inkling of the things that I want to do. So, for example, this last **Winter Olympics** that we held with all of my friends, I knew we wanted to have like two or three ironic throwbacks to college in terms of drinking games. We wanted to have two or three more fun conversational games and maybe two or three like actual games. So, I had a long brainstorming session with **Jarvis** about what are all the activities that we've done before, what are the themes on them, how should we actually think about vamping new activities, and almost never is it actually exactly what I want, but it gets me in the thought process of, oh, that is pretty much close to what I want. Let me make the final modifications myself. And then it's also really good for like the ops actually of organizing all that. We had 20 people come. So now then we wanted to be really intentional about matching people in teams. I put everyone in pairs, but I wanted you to interact with more than just your pair throughout the day. So then for each of the games that were 4v4, we were rotating which pairs were with other pairs to come form mega pairs to then compete in a game so that you got exposure to like everyone else throughout the day. And so that I thought was really really fun and I use that all the time. I actually bought 10 new board games because I found them via **Claude** yesterday and I was like these look fun. So, I think that's so fun. And you are not the only um board game gaming person that we've had on the podcast. We actually had an entire episode about how two two friends started a um a board game cafe in **East Bay** using **Chad Gybt** and and all sorts of stuff. So, uh nerds be using AI to play to play board games.

</details>

**Claire Vo**: 这就是你把AI交给宅男们的结果。

<details>
<summary>Original English</summary>

**Claire Vo**: This is what happens when you give nerds AI.

</details>

**Yash Tucker**: 是的。我的意思是，我确实喜欢的一点是，能够举办大型社交活动。我喜欢围绕人们如何相遇、他们做什么以及如何让活动变得有趣来构建更多结构。我也喜欢群体活动。我最近举办了一个长达一个月的“三月忧郁”64首歌情绪摇滚淘汰赛，我们决定了所有情绪摇滚歌曲中最悲伤的一首，我用了一个像我拥有的这个气氛代码应用。它以前运行起来简直是噩梦。它运行起来非常有趣。我们有100多人参与。所以我确实认为它是一个有趣的起点。它永远不是你想要结束的地方。

<details>
<summary>Original English</summary>

**Yash Tucker**: Yeah. I mean, one of the things that I do like though is to be like to throw big social events. I love the idea of putting more structure around like how people meet each other and what they do and how to make it fun. I also love a group activity. I recently ran a month-long **March sadness** 64 song emo bracket where we decided what was the saddest emo song over all of and I used like I had like this vibe coded app. It was like a nightmare to run before. It was so fun to run. We had like over 100 people in it. And so I do think it is like a fun um kind of like jumping off point. It's never where you want to end up,

</details>

**Claire Vo**: 但它给了你足够的想法，你会觉得：“哦，我可以从中借鉴一点，从那个借鉴一点，然后和你的朋友们聚在一起。”所以我很喜欢那个。

<details>
<summary>Original English</summary>

**Claire Vo**: but it gives you enough ideas that you be like, "Oh, I can pluck a little from that, a little from this, and then and then get your friends together." So I I love that.

</details>

**Claire Vo**: 好的，我的最后一个问题，我问过每个人，你看起来是个很积极的人。你看起来也很积极主动，非常擅长使用AI，但你知道这个**OpenClaw**偶尔会有点蠢。当AI没有给你想要的结果时，你会怎么做？你的提示策略是什么？你如何扭转局面？

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, my my last question, which I ask everybody, you seem like such a positive person. and you seem like very proactive, very capable with AI, but you know this **OpenClaw** occasionally like it's real dumb. Um, what what do you do when AI is not giving you what you want? What is your prompting strategy? How do you write the ship?

</details>

### AI提示策略与协作技巧

**Yash Tucker**: 我会给你一个非常细致的答案。我认为有三件事，对吧？所以第一件事是，特别是对于**OpenClaw**，甚至只是认识到有些技能可能不应该成为MCP技能。举例来说，我的日历**OpenClaw**在处理日期方面真的很糟糕，我不知道为什么。

<details>
<summary>Original English</summary>

**Yash Tucker**: I'll give you a very nuanced answer. I think there's three things, right? So thing number one is with **OpenCloud** in particular, it's even just recognizing that some skills maybe shouldn't be MCP skills. Case in point, my calendar **OpenClaw** is really bad at dates and I don't know why.

</details>

**Claire Vo**: 它无法告诉我今天是哪一天。它无法告诉我我正在2026年谈话，因此我正在计划2026年的旅行。我为什么要计划2025年的旅行？这说不通。

<details>
<summary>Original English</summary>

**Claire Vo**: I cannot tell what today is. I cannot tell that I'm like talking in 2026 and I therefore am planning a trip for 2026. Why would I plan a trip for 2025? That makes no sense.

</details>

**Yash Tucker**: 但就像，对吧，我可以构建一个**Crown Drop**，它基本上会在我发送日期消息时，同时发送时间戳，并识别这是你回答这个问题的时刻。我的假设是这与模型训练方式或开发时间有关。所以这有帮助。但就像，方法一就是认识到有时你要求AI做的事情可能不是AI应该做的事情，或者你需要给它更好的上下文。方法二就变得非常搞笑了，那就是对它要严格。我会用全大写字母打字。我会告诉它会发生可怕的事情。我会说，我将失去我的工作。如果你们不正确地完成，我将不得不解雇我的团队。我的兄弟可能无法回家。所有这些可怕的例子，你举的例子越极端，它就越会像：“好的，这一枪，我保证我会搞定。”即使你没有给出任何理由，也完全不需要与之相关，你也能让它做得更好，但我真的会告诉它会有负面影响，有时它确实会变得更严格。然后我想我将提到的最后一件事，我认为特别适用于**OpenClaw**和**Claude**，就是我尝试为那些它重复做不好的事情构建技能。所以，例如，我有一个**Google Calendar**技能，我正在不断地改进和迭代。所以，我做的更细致的事情是，每当它反复出错时，我都会要求它向我解释为什么以及它是如何得出那个结论的。然后我要求它浏览这个技能，并告诉我，如果你只是给我正确答案，你认为这个技能缺少什么才能让它下次做得更好。通过迭代，我注意到它确实会随着时间的推移变得越来越好。警告是，这并非一蹴而就。它会需要10、12、20条消息，但你会逐渐注意到改进。

<details>
<summary>Original English</summary>

**Yash Tucker**: But right like I can build in a **crown drop** that basically then says anytime I send a date message just send the time stamp as well and recognize that this is the moment in time at which you are answering this question. And my hypothesis it has something to do with like how the models are trained or when they were developed. So that helps. But like method number one is recognize that maybe sometimes the thing you are asking the AI to do is not the thing the AI should do or that you need to give it better context. Method number two which gets much more silly is be strict with it. Like I type in all caps. I will tell it like horrible things will happen. I'll be like I'm going to lose my job. I'm going to have to fire my team if you don't do this correctly. My brother might not be able to make it back home. And like all of these horrible like the more extreme you get with the examples, the more it's like, okay, on this shot, I promise I will get it. Even if you supply no reason, it has to be nowhere close to connected for you to actually get it to do better, but I will really tell it there are negative repercussions and it does get stricter sometimes. And then I think the last thing I'll mention which is really good for I think in particular **OpenClaw** and **Claude** is I try to build skills for the things that it's not really repeatedly good at doing. So for example I have a **Google calendar** skill that I'm constantly refining and iterating. And so the more nuance thing that I do is whenever it repeatedly gets something wrong I ask it to explain to me why and how it arrived at that conclusion. And then I ask it to kind of go through the skill and tell me what do you think is missing from the skill that would maybe make it better for the next time around if I just give you the correct answer. And iteratively I have noticed it does get better and better over time. The warning is it's not a oneshot thing. It'll take 10, 12, 20 messages, but you will notice the improvement gradually.

</details>

**Claire Vo**: 我喜欢。老实说，这个问题我大概问了60多次了，没有人承认他们会像那样威胁模型。

<details>
<summary>Original English</summary>

**Claire Vo**: I I love it. And honestly, I've asked this question probably now 60s something times and no one has admitted that they are like threaten the model with threaten the model all the time.

</details>

**Yash Tucker**: 总是威胁模型。

<details>
<summary>Original English</summary>

**Yash Tucker**: All the time it's so unusually

</details>

**Yash Tucker**: 总是这样，它非常异常有效。我想数据层面的原因可能是奖励规范和参数等等。但它确实有效，你知道。我的意思是，我总是，我总是把育儿与这个问题联系起来，我告诉我的孩子们，我也会告诉AI，如果不是唯一有效的方法，我就不会冲你们大喊大叫。

<details>
<summary>Original English</summary>

**Yash Tucker**: All the time it's so unusually effective. The like data reason for it I think is the reward specification and the parameter and everything else. But like it works, you know. I mean, I always I always reference parenting when we we come with this question and I tell my kids and I will tell the AI, I wouldn't yell at you if it wasn't the only thing that worked.

</details>

**Claire Vo**: 我们明白了。好的，这太棒了。我们可以在哪里找到你，我们能提供什么帮助？

<details>
<summary>Original English</summary>

**Claire Vo**: We got it. Okay, this was so good. Where can we find you and how can we be helpful?

</details>

**Yash Tucker**: 好问题。你可以在**LinkedIn**或**Twitter**上找到我。我想就是我的名字，**Yash Takraal**，或者在**Twitter**或X上是**Yashtek**，随便人们现在怎么叫它。呃，老实说，关于如何提供帮助，我会给出一个推脱的答案，那就是告诉我我能如何帮助你。我喜欢教人们东西。我在**Clay**负责教育。我显然喜欢这些AI的东西。所以，我心里唯一想的就是如何帮助更多人更开心地使用这些东西。

<details>
<summary>Original English</summary>

**Yash Tucker**: Great questions. You can find me on **LinkedIn** or **Twitter**. I think it's just my name, **Yash Takraal** or **Yashtek** on **Twitter** or X, whatever people call it now. Uh, and honestly, the the copout answer I'll give you to how to be helpful is let me know how I can be helpful to you. I love teaching people things. I run education at **Clay**. I love this AI stuff clearly. And so, the only thing on my mind is how to help more people have more fun with these things.

</details>

**Claire Vo**: 这是一个多么美妙的结局。谢谢你，我们很快再聊。

<details>
<summary>Original English</summary>

**Claire Vo**: What a wonderful way to end. Thank you and I'll talk to you soon.

</details>

**Yash Tucker**: 很快再聊。再见，Claire。

<details>
<summary>Original English</summary>

**Yash Tucker**: Talk soon. See you, Claire.

</details>

**Claire Vo**: 各位再见。非常感谢大家的观看。如果你喜欢这个节目，请在YouTube上点赞并订阅，或者更好的是，给我们留言分享你的想法。你也可以在**Apple Podcasts**、**Spotify**或你喜欢的播客应用上找到这个播客。请考虑给我们评分和评论，这将有助于其他人找到这个节目。你可以在howiaipod.com查看我们所有的剧集并了解更多关于节目的信息。下次再见。

<details>
<summary>Original English</summary>

**Claire Vo**: Bye y'all. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on **YouTube**, or even better, leave us a comment with your thoughts. You can also find this podcast on **Apple Podcasts**, **Spotify**, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>