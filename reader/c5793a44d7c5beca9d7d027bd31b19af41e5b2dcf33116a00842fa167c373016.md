---
author: Latent Space
date: '2026-03-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tMflcZHo2zI
speaker: Latent Space
tags:
  - agentic-workflow
  - computer-use
  - software-engineering-automation
  - human-ai-collaboration
  - cloud-infrastructure
title: Cursor 第三纪元：云端智能体与编程的范式转移
summary: Cursor 团队核心成员 Sam Whitmore 与 Jonas Nelle 深入探讨了 Cloud Agents 的发布及其背后的技术哲学。讨论涵盖了全计算机使用（Full Computer Use）、端到端自动测试、视频演示驱动的代码评审，以及如何通过 Slack 协作和 Agent 集群重塑软件工程的未来。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Sam Whitmore
  - Jonas Nelle
  - Alexi
  - Matthew Fria
  - Rio
  - Evan
  - Andrej Karpathy
companies_orgs:
  - Cursor
  - OpenAI
  - Anthropic
  - DataDog
  - Graphite
  - Slack
  - Vercel
  - GitHub
products_models:
  - Cloud Agents
  - Opus 4.5
  - Codex 5.3
  - AutoTab
  - TanStack Router
  - Bugbot
  - MCP
media_books: []
status: evergreen
---
### 多模型协同的实验

**Sam Whitmore**: 这是我们在去年运行的另一个实验，当时没决定发布，但以后可能会回到 **LM Judge**（大模型评委）的思路上。这个实验也是**智能体化**（agentic）的，能够编写代码。它不仅仅是选择，还能从它观察的两个或多个模型中吸取经验，并编写一个新的 **diff**（代码差异）。我们发现，使用来自不同模型提供商的模型作为这个过程的基础层是有优势的。基本上，你可以获得一种协同效应的输出，这比拥有一个非常统一的底层模型层效果更好。

<details>
<summary>Original English</summary>

**Sam Whitmore**: So this is another experiment that we ran last year and didn't decide to ship at that time but may come back to LM judge but one that was also agentic and could write code. So it wasn't just picking but also like taking the learnings from two models or and models that it was looking at and writing a new diff. And what we found was that there were strengths to using models from different model providers as the base level of this process. basically you could get almost like a synergistic output that was better than having like a very unified like bottom model tier.

</details>

**Jonas Nelle**: 我们认为在接下来的几个月里，巨大的突破将不再是一个人配合一个模型完成更多工作——就像让水流得更快——我们将把管道做得更宽，从而实现更多的**并行化**。无论是**智能体集群**（swarms of agents）还是并行智能体，这两者都有助于在相同的时间内完成更多工作。

<details>
<summary>Original English</summary>

**Jonas Nelle**: We think that over the coming months the big unlock is not going to be one person with a model getting more done like the water flowing faster and we'll be making the pipe much wider and so paralyzing more whether that's swarms of agents or parallel agents both of those are things that contribute to getting much more done in the same amount of time.

</details>

### 赋予 AI 计算机权限：Cloud Agents 诞生

**访谈人**: 本周，**Cursor** 进行了有史以来规模最大的发布之一，那就是 **Cloud Agents**（云端智能体）。我的意思是，你们以前也有云端智能体，但这次就像是……你直接给了 Cursor 一台计算机，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: This week, one of the biggest launches that cursor has ever done um is cloud agents. I mean, I think you you had cloud agents before, but like this was like well, you give cursor a computer, right?

</details>

**访谈人**: 那么，这基本上是因为他们收购了 **AutoTab** 然后重新包装了一下吗？是这么回事吗？

<details>
<summary>Original English</summary>

**Interviewer**: Um so is this basically they bought autotab and then they repackaged it. Is that what's going on or

</details>

**Sam Whitmore**: 这是很大一部分原因。是的。云端智能体以前就在它们自己的计算机上运行，但它们某种程度上只是在“静默阅读”代码。那些计算机通常是空白的 **VM**（虚拟机），没有为智能体正在处理的任何仓库设置开发环境（**DevX**）。我们谈论的一件事是：如果你站在模型的角度，看着令牌（tokens）流过，而你唯一能做的就是阅读代码并吐出令牌，然后祈祷自己做对了。

<details>
<summary>Original English</summary>

**Sam Whitmore**: that's a big part of it. Yeah. Cloud agents already ran in their own computers but they were sort of site readading code. And those computers were not they were like blank VMs typically that were not set up for the DevX for whatever repo the agent's working on. One of the things that we talk about is if you put yourself in the model shoes and you were seeing tokens stream by and all you could do was site readad code and spit out tokens and hope that you had done the right thing.

</details>

**访谈人**: 那没戏。

<details>
<summary>Original English</summary>

**Interviewer**: No chance.

</details>

**Sam Whitmore**: 肯定会表现得很糟。你显然需要运行代码。所以我认为这可能不是一个多么特立独行的观点，但还没有人真正做到。因此，赋予模型自我引导的工具，然后使用完整的**计算机使用能力**（Computer Use）——端到端的像素输入、坐标输出——并拥有一个装有各种应用程序的云端计算机，这是我们在内部看到的巨大突破。使用场景从“哦，我们用它做点文案小改动”变成了“不，我们真的在用这种新型的智能体工作流来驱动新功能的开发”。

<details>
<summary>Original English</summary>

**Sam Whitmore**: I'd be so bad. Like you obviously you need to run the code. And so that I think also is probably not that contrarian of a take, but no one has done that yet. And so giving the model the tools to onboard itself and then use full computer use end to end pixels in coordinates out um and have sort of the cloud computer with different apps in it is the big unlock that we've seen internally in terms of use usage of this going from oh we use it for little copy changes to no no we're really like driving new features uh with this kind of new type of aentic workflow.

</details>

### 云端智能体的三大支柱

**访谈人**: 好了，让我们看看它。

<details>
<summary>Original English</summary>

**Interviewer**: All right let's see it.

</details>

**Sam Whitmore**: 酷。这就是它在 `cursor.com/agents` 里的样子。这是我前段时间启动的一个任务。左手边是聊天框，非常经典的智能体交互方式。这里最大的新事物是智能体会测试它的改动。你可以看到，它运行了半个小时。那是因为它不仅花时间编写代码令牌，还花时间进行了端到端的测试。所以，它会启动开发服务器，在需要时进行迭代。

这是其中的一部分：模型工作更久，返回的不是一个“我尝试了一些东西”的 **PR**，而是一个“我测试过了”的 PR，已经准备好供你评审。我们使用的另一个直觉判断是：如果一个人类给了你一个 PR 让你评审，但他自己都没测试过，你也会觉得挺烦的，因为你会觉得“等真的准备好了再叫我”。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Cool. So this is what it looks like in cursor.com/agents. So this is one I kicked off a while ago. So on the left hand side is the chat very classic sort of agentic thing. The big new thing here is that the agent will test its changes. So you can see here it worked for half an hour. That is because it not only took time to write the tokens of code, it also took time to test them end to end. So start at dev servers, iterate when needed. Uh, and so that's one part of it is like model works for longer and doesn't come back with a I tried some things PR but a I tested it PR that's sort of ready for your review. Uh, one of the other intuition pumps we use there is if a human gave you PR, asked you to review it and you hadn't they hadn't tested it. You'd also be kind of annoyed because you'd be like only ask me for a review once it's actually ready.

</details>

**访谈人**: 我想先问个简单的问题。有些 PR 非常小，比如只是改个文案。它总是会生成视频吗，还是有时会？

<details>
<summary>Original English</summary>

**Interviewer**: So that's what we've done with uh simple question I wanted to gather up front. Some PRs are way smaller like just copy change. Does it always do the video or is it sometimes?

</details>

**Sam Whitmore**: 有时会。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Uh sometimes.

</details>

**访谈人**: 好吧。那么判断标准是什么？

<details>
<summary>Original English</summary>

**Interviewer**: Okay. So, so what's the judgment?

</details>

**Sam Whitmore**: 模型自己决定。我们会进行一些默认提示，关于哪些类型的改动需要测试。人们可以使用一个斜杠命令叫 `/no-test`，用了这个模型就不会测试，但默认是测试。

<details>
<summary>Original English</summary>

**Sam Whitmore**: The model does it. So, we uh we do some default prompting with sort of what types of changes to test. There's a slash command that people can do called slashn no test where if you do that the model will not test but the default is test.

</details>

**Jonas Nelle**: 默认是经过**校准**的。我们告诉它简单的文案修改不要测试，但要测试复杂的改动。用户还可以编写自己的 `agents.mmd` 配置文件，指定比如“如果你正在编辑这个 **Monorepo** 的子部分，永远不要测试，因为那行不通”之类的内容。

所以，第一支柱是模型进行实际测试。第二支柱是模型返回一段关于它做了什么的视频。我们发现在这个智能体可以端到端编写更多代码的新世界里，评审代码成了新的瓶颈。评审视频并不能替代评审代码，但它是一个入门点，比瞥一眼巨大的 diff 要容易得多。通常你启动一个任务，完成后你回来做的第一件事就是看视频。这是一个视频示例，在这个案例中，我想要一个按钮上的工具提示（tool tip）。它就去演示了视频里看起来是什么样。有时它会构建类似 **Storybook** 的画廊，你可以看到组件的实际运行效果。

第三支柱是我拥有对这个 VM 的完整远程控制权限。我可以进去悬停、打字，拥有完全的控制权。终端也是一样。这非常有用，因为有时视频就是你需要看到的全部，但通常视频并不完美。视频会显示这是否值得立即合并，或者通常是否值得通过迭代来达到最终可以合并的阶段。我可以举出其他一些例子，虽然第一个视频并不完美，但它让我确信我们在正确的轨道上。两三个后续操作后，它就搞定了。而且我还有完全的访问权限，有些东西你就是想亲自把玩一下，感受一下。实时预览是无可替代的，**VNC** 类型的虚拟机远程访问赋予了这种能力。

<details>
<summary>Original English</summary>

**Jonas Nelle**: The default is to be calibrated. So, we tell it don't test very simple copy changes but test like more complex things. And then users can also write their agents.mmd and specify like this type of you know if you're editing this sub part of my monor repo never tested because that won't work or whatever. Okay. So pillar one is the model actually testing. Pillar two is the model coming back with a video of what it did. We have found that in this new world where agents can end to end write much more code reviewing the code is one of these new bottlenecks that that crop up. And so reviewing a video is not a substitute for reviewing code, but it is an entry point that is much much easier to start with than glancing at some giant diff. And so typically you kick one off, you it's done. You you come back and the first thing that you would do is watch this video. So this is sort of a you know video of it. Um, in this case, I wanted a tool tip over this button. And so, it went and uh showed me what that what that looks like in in this video that I think here it actually used a gallery. So, sometimes it will build storybook type galleries where you can see sort of like that component in action. Uh, and so that's pillar two is like these demo videos of what it built. Uh, and then pillar number three is I have full remote control access to this VM. So I can go here in here, I can hover things, I can type, I have full full control. Uh and same thing for the for the terminal. Um so you know I have full access and so that is also really useful because sometimes the video is like all you need to see and often times by the way the video is not perfect. The video will show you is this worth either merging immediately or often times is this worth iterating with to get it to that final stage where I am ready to merge it. And so I can go through some other examples where the first video wasn't perfect, but it gave me confidence that we were on the right track. And two or three follow-ups later, it was good to go. And then I also have full access here where some things you just want to play around with. You want to get a feel for what is this like? And there's no substitute to a live preview. And the VNC kind of VM remote access gives you that.

</details>

### 后端与元能力：不仅仅是前端

**访谈人**: 太棒了。等等，什么是 VNC？

<details>
<summary>Original English</summary>

**Interviewer**: Amazing. Well, sorry, what is VNC?

**Sam Whitmore**: Uh it just the the remote desktop. Uh remote desktop. Yeah.

</details>

**访谈人**: Sam，还有其他你想特别指出的细节吗？

<details>
<summary>Original English</summary>

**Interviewer**: Uh Sam, any other details that you always want to call out?

</details>

**Jonas Nelle**: 对我来说，视频非常有帮助。我发现之前智能体和云端智能体的一个常见问题是我的请求**规格说明不足**（underspecification）。我们的计划模式和反复深入讨论详细实现规范是降低这种风险的一种方式。但就像人类沟通随着时间推移会崩溃一样，当你费劲拉下分支在本地运行，结果发现我说这应该是个切换开关，你却做成了复选框。有了视频，这种对齐就像是与智能体共享一个非常清晰的工件，这对我非常有帮助。

<details>
<summary>Original English</summary>

**Jonas Nelle**: Yeah, I mean for me the videos have been super helpful. I would say especially in cases where a common problem for me with agents and cloud agents beforehand was almost like underspecification in my requests where our plan mode and kind of going really back forth and getting detailed implementation spec is a way to reduce the risk of underspecification. But then similar to how human communication breaks down over time, I feel like you have this risk where it's like, okay, when I pull down go to the trouble of pulling down and like running this branch locally, I'm going to see that like I said this should be be a toggle and you have a check box and like why didn't you get that detail right? And having the video up front just has that makes that alignment like you're talking about a shared artifact with the agent very very clear which has been just super helpful for me.

</details>

**Sam Whitmore**: 我可以快速演示一些其他例子。刚才那个非常侧重前端。

<details>
<summary>Original English</summary>

**Sam Whitmore**: I can quickly run through some other examples. So this is a very front-end heavy one.

</details>

**访谈人**: 我正想问，这只是为了前端吗？

<details>
<summary>Original English</summary>

**Interviewer**: I was going to say is this only for front end?

</details>

**Sam Whitmore**: 没错。你可能会问是不是仅限前端。这是另一个例子，我想实现一个更好的保存机密（secrets）的错误消息。云端智能体支持添加机密，这是它访问某些系统所需的。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Exactly. One question you might have is is this only for front end? So this is another example where the thing I wanted it to implement was a better error message for saving secrets. So the cloud agents support adding secrets. That's part of what it needs to access certain systems.

</details>

**访谈人**: 云端（团队）正在开发云端智能体。

<details>
<summary>Original English</summary>

**Interviewer**: cloud is working on cloud agents.

</details>

**Sam Whitmore**: 是的。有趣的是……

<details>
<summary>Original English</summary>

**Sam Whitmore**: Yes. So this is a fun thing is

</details>

**访谈人**: 这可以变得非常“元”（meta）。

<details>
<summary>Original English</summary>

**Interviewer**: it can get super meta.

</details>

**Sam Whitmore**: 它可以变得非常元。它可以启动它自己的云端智能体，可以与其对话。有时很难理解这一点。我们禁用了它的云端智能体启动更多云端智能体的功能，目前是不允许的。

<details>
<summary>Original English</summary>

**Sam Whitmore**: It can get super meta. It can start its own cloud agents. It can talk to its own cloud agents. Sometimes it's hard to wrap your mind around that. We have disabled its cloud agents starting more cloud agents. So we currently disallow that.

</details>

**访谈人**: 也许有一天你们会允许。

<details>
<summary>Original English</summary>

**Interviewer**: Someday you might.

</details>

**Sam Whitmore**: 也许。这实际上主要是一个后端的错误处理改动。如果机密太大，我们不允许超过一定大小。之前的错误消息很烂，只是通用的“保存失败”。我想要个具体的错误消息。第一件酷的事是，我完全没有提示它如何测试。它没有手动输入 5000 个字符来触发限制，而是打开了 **DevTools**，编写 JavaScript 将 5000 个字母 A 粘贴进输入框，然后点击保存，关闭 DevTools，最后得到了新的错误消息。视频在这一段断开了，但你可以看到错误消息的截图。这是从前端到后端的完整功能实现。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Someday we might. Someday we might. Um so this actually was mostly a backend change in terms of the error handling here where if the secret is far too large, it would um Oh, this is actually really cool. That's the dev tools. That's the dev tools. So if the secret is far too large, we don't allow secrets above a certain size. We have a size limit on them. And the error message there was really bad. It was just some generic failed to save message. So I was like, \"Hey, we wanted an error message.\" So first cool thing it did here, zero prompting on how to test this. Instead of typing out the like a character 5,000 times to hit the limit, it opens DevTools, writes JS or to paste into the input 5,000 characters of the letter A and then hits save, closes the DevTools, hits save, and gets this new um gets the new error message. So that uh looks like the video actually cut off, but here you can see the here you can see the screenshot of the uh of the error message. So that is like front end, back end kind of end to end feature to to get that.

</details>

### 从手动编码到高阶抽象

**访谈人**: 你只需要一个完整的 VM，完整的计算机，运行一切，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: um and you just you just need a full VM, full computer, run everything, right? Okay. Yeah.

</details>

**Sam Whitmore**: 是的。我们有过不同版本。这是 **AutoTab** 的经验之一，我们在 2023 年开始做。当时是浏览器使用、DOM 之类的。我想我们最终非常倾向于 **AGI pilled**（相信通用人工智能的愿景），即直接给模型像素，给它一个盒子。你想要的是“盒子里的脑子”（brain in a box），并消除环境和能力的限制，这样瓶颈就应该是智能。鉴于今天的模型有多聪明，那个瓶颈已经非常遥远了。所以给它完整的 VM，让它像人类一样进行开发环境引导，对我们内部来说在能力上是一个巨大的台阶式飞跃。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Yeah. So we've had versions of this. This is one of the autotab lessons where uh we started that in 2022. Uh no, 2023. And at the time it was like browser use, you know, DOM, like all these different things. And I think uh we ended up very sort of AGI pilled in the sense that just give the model pixels, give it a box. Sort of a brain in a box is what you want. And you want to remove uh limitations around context and capabilities such that the bottleneck should be the intelligence. And given how smart models are today, that's a very far out bottleneck. And so giving it its full VM and having it be onboarded with DevX set up like a human would has just been for us internally a really big big step change in capability.

</details>

**访谈人**: 一年前，这些模型甚至还不够好，无法完成这些工作。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. I would say you know let's call it a year ago the the models weren't even good enough to do any of this stuff right. So

</details>

**Sam Whitmore**: 甚至六个月前也是。

<details>
<summary>Original English</summary>

**Sam Whitmore**: even six months ago. Yeah.

</details>

**访谈人**: 那么，现在的趋势是模型已经好到足以完全通过像素操作来实现自动化了。

<details>
<summary>Original English</summary>

**Interviewer**: So like yeah what what people have told me is like around about solder 45 is when this started being good enough to just automate fully by pixel.

</details>

**Sam Whitmore**: 这一直是“什么时候算足够好”的问题。我们发现，特别是 **Opus 4.5/4.6** 和 **Codex 5.3**，它们在模型的自主等级能力上带来了额外的跨越。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Yeah. I think it's always a question of when is good enough. I think we found in particular with Opus 4546 and Codeex 53 that those were additional step changes and sort of the autonomy grade capabilities of the model to just go off and figure out the details and come back when it's done.

</details>

### Slack 成为新的 IDE

**访谈人**: 还有什么变化是你注意到的？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Anything to add? One other shift that I've noticed um as our crowd agents have really taken off internally has been a shift from primarily individually driven development to almost this like collaborative nature of development.

</details>

**Jonas Nelle**: 对我们来说，**Slack** 实际上几乎成了一个开发环境，基本上就是一个 IDE。

<details>
<summary>Original English</summary>

**Jonas Nelle**: For us, Slack is actually almost like a development um an IDE basically.

</details>

**访谈人**: 这就是为什么我觉得也许根本不需要构建自定义 UI，那只是个调试工具，实际上（开发中心）是 Slack。

<details>
<summary>Original English</summary>

**Interviewer**: That's why I'm like maybe maybe don't even build a custom UI like maybe like you know that's like a debugging thing but actually it's Slack.

</details>

**Jonas Nelle**: 还有很多值得探索的地方，但基本上 Slack 是很多开发发生的地方。我们会有这些问题频道，或者产品讨论频道，人们总是在里面 `@cursor`。这会启动一个云端智能体，我们启用了团队后续跟进，所以如果 Jonas 在线程中启动了一个任务，我可以跟进并添加更多上下文。它变成了一种讨论服务，人们可以在 UI 上进行协作。我经常会发起一个调查，甚至让它去运行 `git blame` 然后标记（tag）应该加入讨论的人，因为它可以在 Slack 中标记人。

<details>
<summary>Original English</summary>

**Jonas Nelle**: I feel like yeah there's still so much to left to explore there but basically for us like Slack is where a lot of development happens like we will have these issue channels um or just like this product discussion channels where people are always at cursoring and that kicks off a cloud agent and um for us at least we have team follow-ups enabled so if Jonas kicks off a at cursor in a thread I can follow up with it and kind of like add more context and so it turns into almost like a discussion service where people can kind of like collaborate on UI. Oftentimes I will kick off an investigation and then like um sometimes I even ask it to like get blame and then tag people who should be brought in because it can tag people in Slack and then other people will

</details>

**访谈人**: 它可以标记没参与对话的人。

<details>
<summary>Original English</summary>

**Interviewer**: can tag other people who are not involved in conversation

</details>

**Jonas Nelle**: 它可以直接 `@Jonas`。

<details>
<summary>Original English</summary>

**Jonas Nelle**: can just do at Jonas.

</details>

**访谈人**: 酷。你们应该大张旗鼓地宣传这一点。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. That's cool. You should you guys should make a bigger deal out of that.

</details>

**Jonas Nelle**: 我知道。在 Slack 界面上还有很多事要做。基本上，它可以把其他人拉进来，其他人也可以对那个线程做出贡献，最后得到一个带有可见工件的 PR，大家会觉得“好，酷，我们可以合并这个”。所以对我们来说，IDE 在某种程度上正在迁入 Slack。

<details>
<summary>Original English</summary>

**Jonas Nelle**: I know. um it's a lot to I feel like there's a lot more to do with our Slack surface area um to show people externally. But yeah, basically like it can bring other people in and then other people can also contribute to that thread and you can end up with a PR again with the artifacts visible and then people can be like okay cool we can merge this. So for us it's like the ID is almost like moving into Slack in some ways as well.

</details>

**访谈人**: 我有同样的经验，但不是开发者，而是我这个设计师和销售人员。

<details>
<summary>Original English</summary>

**Interviewer**: I have the same experience um with but it's not developers it's me designer salespeople.

</details>

**访谈人**: 我负责技术营销愿景，设计师负责设计，销售负责法律条款，然后大家一起协作，纠正智能体。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. So me on like technical marketing vision, designer on design and then sales people on like well here's the legal thirds of what we agreed on and then they all just collaborate and like correct uh the agents.

</details>

**Sam Whitmore**: 我们发现这些线程中，人类讨论剩下的工作才是真正有趣和相关的**核心**。不再是无聊的细节，比如这个 `if` 语句放在哪。而是“我们要发布这个吗？”、“这是正确的 UX 吗？”、“这是正确的形态吗？”。这些高阶问题非常容易协作，而实现细节则留给云端智能体。

<details>
<summary>Original English</summary>

**Sam Whitmore**: I think that we found these threads is the work that is left that the humans are discussing in these threads is the nugget of what is actually interesting and and relevant. It's not like you know the boring details of where does this if statement go. It's like do we want to ship this? Is this the right UX? Is this the right form factor? Uh, you know, how do we make this more obvious to the user? It's like those really interesting kind of higher order questions that are so easy to collaborate with and leave the implementation to the to the cloud agent.

</details>

**访谈人**: 完全同意。不再有“是我去做这个，还是你去做？”的讨论。Cursor 正在做，你只需要决定你是否喜欢它。

<details>
<summary>Original English</summary>

**Interviewer**: Totally. And no more discussion of like am I going to do this? Are you going to do this? Curs is doing it. You just have to decide you like it. [laughter]

</details>

### 未来预测：智能体吞噬本地环境

**访谈人**: 最后一个问题。你们对今年年底有什么预测？

<details>
<summary>Original English</summary>

**Interviewer**: One more question on on just the cursor in general and then uh you know open-ended for you guys to plug whatever you want to plug. How is cursor hiring these days? Predictions for the end of the year, if you have any.

</details>

**Sam Whitmore**: 预测总是很难说准。但我预测到今年年底，云端智能体在各自盒子（VM）中工作的数量将超过本地智能体。我认为这个交叉点会在年底前发生，可能到年底时，云端运行的智能体数量将是本地智能体的 2 倍以上。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Predictions are not going to go well. Well, one other plug. Yeah. I predict that by the end of the year the volume on I think it will take longer than people think and longer than we think for cloud and agents working in their own boxes to surpass local agents. But I think that crossover will happen before the end of the year and probably by the end of the year agents running in the cloud will be a multi like more than 2x the volume of local agents.

</details>

**访谈人**: 好的。今天还有什么不尽如人意的地方吗？

<details>
<summary>Original English</summary>

**Interviewer**: Okay, you're leaving me an opening. What's not good today?

</details>

**Sam Whitmore**: 还有很多难关。比如如何让沙箱真的非常、非常好。我们花了很多时间在 `cursor.com/onboard` 上，在那里你选择一个仓库、添加机密、给它权限，智能体就去安装一切。虽然做了很多工作，但还是有很多事情要做，比如有时候设置太慢。设置不是一劳永逸的事情，依赖会变、数据库位置会变，我们需要模型能自我维护这些环境。

<details>
<summary>Original English</summary>

**Sam Whitmore**: Yeah, there's a bunch of hard things. So, one of them is just getting those sandboxes to be really, really good. And a thing that was part of this launch that we spent an inordinate amount of time on is cursor.com/onboard where you pick a repo, add secrets, give it access to things, and the agent just goes off and installs things. Yeah, we worked a lot on that. but, um there's still a lot to do there, right? like setup one two two things maybe it's too bad it's too slow um working on it uh setup is not like a unitary thing where everything is set up or not right like things will break over time you have new dependencies you need access to new systems like you change where your database lives so that's one part of it

</details>

**Jonas Nelle**: 另一个巨大的解锁将是**自我审计**（Self-Auditability）和**自我意识**（Self-Awareness）。智能体不仅要在环境上被引导，还要在设计权衡、代码库如何运作方面被引导。智能体需要能发现它自己的功能差距，并决定如何填补。

<details>
<summary>Original English</summary>

**Jonas Nelle**: And then the other part of it that starts to get really interesting is when the model starts editing its own system prompt. self-awareness to us in this context is kind of like um not like the model itself having a notion of consciousness but more like knowing like what system it's operating in and the the constraints of that system and potentially being able to have agency in like optimizing itself to operate best in the in that system.

</details>

**访谈人**: 这是一个非常深入的讨论。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, this is more abstract than I ever thought we'll get at this [laughter] tier discussion.

</details>

**Sam Whitmore**: 谢谢分享你们的操作洞见。

<details>
<summary>Original English</summary>

**Sam Whitmore**: No, I mean you guys are like my sort of needing example what an agent lab looks like and like can be successful and like I think people always hungry for insights into how you guys operate. So, thank you for taking the time to share.

</details>

**Jonas Nelle**: 谢谢你能来。

<details>
<summary>Original English</summary>

**Jonas Nelle**: Yeah, thanks for coming.

</details>