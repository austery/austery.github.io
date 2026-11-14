---
author: Latent Space
date: '2026-03-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZpZ7lFoWaT8
speaker: Latent Space
tags:
  - ai-agents
  - virtual-machine
  - human-computer-interaction
  - software-development
  - workflow-automation
title: Anthropic为何认为AI应拥有自己的电脑？——Claude Cowork/Code的Felix Rieseberg访谈
summary: 本期访谈中，Anthropic的Felix Rieseberg深入探讨了其AI产品Claude Cowork的设计理念、功能及其对未来工作的影响。他解释了Cowork如何作为Cloud Code的用户友好版本，通过虚拟机在本地电脑上高效处理非编程任务，并强调了本地计算的价值。访谈还涵盖了Cowork在自动化、技能创建和Chrome集成方面的应用，以及Anthropic对AI对劳动力市场潜在影响的担忧。讨论还触及了AI代理的未来、技能的可移植性、人机交互的演变，以及Electron和Chromium等底层技术的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Barry Mahesh
  - Fabian
companies_orgs:
  - Anthropic
  - Microsoft
  - Apple
  - Google
  - Slack
products_models:
  - Claude Cowork
  - Cloud Code
  - Electron
  - Visual Studio Code
  - Chrome
  - V86
  - WSL2
  - Tauri
media_books: []
status: evergreen
---
### AI与本地计算的未来

**Felix**: 这可能与许多AI领域的人持有的观点有些不同。我其实不认为未来会是高度个性化的软件，以至于每个人都运行自己的版本。我认为我们所有人要拥有自己的内部聊天工具会相当困难。**硅谷**总体上低估了本地电脑的价值。我对此的默认论点总是：为什么我们都使用 **MacBook** 而不是 **iPad** 或 **Chromebook**？现在，当我想到 **Claude** 作为一个应该对你非常有用的实体，一个极其有用的实体时，我认为它需要访问你所能访问的所有工具。否则，它会在所有这些复杂方面受到限制。

<details>
<summary>Original English</summary>

**Felix**: This is maybe a whole like a somewhat contrarian view to a lot of people in AI. I actually don't think that the future is going to be hyper personalized software down to the point where everyone is running their own version. Like I actually think it's going to be quite hard for all of us to have our own internal chat to wall. Silicon Valley overall is undervaluing the local computer. And my default argument for that is always how come we're all using MacBooks and not like an iPad or a Chromebook. And now when I think about Claude is this entity that is supposed to be very useful to you like tremendously useful to you. I think that entity needs to have access to all the same tools you have access to. Otherwise, it's going to be hemstrong in like all these complex ways.

</details>

### 欢迎来到Len Space播客

**Alessio**: 大家好，欢迎收听 **Len Space** 播客，这是我们在新工作室录制的第一期。我是 **Colonel Labs** 的创始人 **Alessio**，今天与我一同主持的是 **Laid in Space** 的编辑 **Swixs**。

<details>
<summary>Original English</summary>

**Alessio**: Hey everyone, welcome to the Len Space podcast, our first one in the new studio. Uh this is Allesio, founder of Colonel Labs, and I'm joined by Swixs, editor of Laid in Space.

</details>

**Swixs**: 是的，很高兴来到这里。感谢 **TJ**、**Alessio** 和 **Ellen** 帮助我们搭建好了一切。这里看起来很漂亮，我们甚至把Logo都放在外面了。是的，当你作为嘉宾走进这里时，感觉真的很好，你会觉得：“啊，这是一个严肃的制作。”你立刻就能感受到。

<details>
<summary>Original English</summary>

**Swixs**: Yeah, so nice to be here. Thanks to uh TJ, Allesio, Ellen helping to set everything up. It looks beautiful. We even have the logo outside. Yeah. It's like really nice when you walk in here as a guest, you're like, "Ah, this is a serious production." You like feel it immediately.

</details>

**Alessio**: 是的，**Felix**，你现在是 **Cowork** 的产品经理，或者说……

<details>
<summary>Original English</summary>

**Alessio**: Yeah. Felix, you've been you're you're currently product manager of cowork or

</details>

**Felix**: 嗯，非常技术化。

<details>
<summary>Original English</summary>

**Felix**: uh really technical

</details>

**Alessio**: ……和主管。是的，这些身份有点模糊。技术人员。

<details>
<summary>Original English</summary>

**Alessio**: and lead. Yeah. The the identities are kind of vague. Member technical staff.

</details>

**Felix**: 我知道“技术人员”是我们将永远沿用的官方头衔。

<details>
<summary>Original English</summary>

**Felix**: I know member technical staff is like the official title we'll carry around forever.

</details>

### Claude Cowork的独特用例

**Swixs**: 是的，我最近有点想，我们一直很着迷。我一直在大量使用它，甚至用于管理 **Latent Space**，比如 **Cowork** 帮助我上传视频、添加标题、编辑等等。它真的很棒。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. I recently kind of wanted like we've been kind of obsessed. I've been using it a lot even for managing latent space like uh co-work helps me upload videos and like title things and like edit and everything. It's it's like really amazing.

</details>

**Alessio**: 酷。他在群聊里多次提到 **Cowork** 可能是 **AGI**。

<details>
<summary>Original English</summary>

**Alessio**: Cool. He said multiple times co-work as a GI in the group chat.

</details>

**Felix**: 是的，是的，是的。所以，我们有第二个频道，用于 **Inspace TV**。我们基本上把这当作我们的 **Discord** 聚会。我们有像“云端同事可能是 **AGI**”这样的内容。我不知道我们是否已经上传了，但其中一个会话就是关于“云端同事”的。我很想看看，我很好奇。我工作中一个最有趣的部分就是不断看到人们如何以奇特的方式使用 **Cowork**，因为我们很难真正为特定的用例进行设计。我们确实会这样做，但每个最惊讶的人通常都是对我们甚至没想过 **Cowork** 会擅长的事情感到惊讶。我们有一个新设计师，我给他的第一个小任务之一就是：“嘿，我们需要为我们内部的堆栈设计一个新的 **Cowork** 表情符号。”这只是一个小事。我说：“你能做一下吗？”他画了一个 **SVG**，然后直接把它交给了 **Cowork**，说：“你能把这个表情符号动画化吗？”现在它有了一个漂亮的循环动画。我的意思是，我认为这显然归结为：事实证明，你可以用代码做比你预期更多的事情，但正是这类事情让我觉得非常有趣。所以长话短说，我很想看看你在做什么。

<details>
<summary>Original English</summary>

**Felix**: Yeah. Yeah. Yeah. So, so we have a second uh we have a second channel uh for the inspace TV. Uh and I uh and uh we basically this is our discord meetup. Um and I I we have like cloud co-workers might be AGI. I don't know if we we have uploaded it yet, but one of the sessions was like a like a cloud co-work thing. I would have to see I would love to see it. Like I'm so curious. Like one of the most fun parts of my job is to like constantly see the weird things people use co-work for because it's obviously like very hard for us to actually design for specific use cases. We do, but like every single person who's like most amazed is usually amazed about a thing that I didn't even expect coowork would be good at. Um we have a new designer and it's one of the first small tasks I was like, "Hey, we need like a new emoji for coowork for our internal stack." It's like a pretty small thing. I was like, "Can you please do it?" and he drew an SVG and just gave it to co-orker was like, "Can you animate this emoji?" And now it has like this beautiful loopy animation. Um, and I mean I think obviously this goes down to like it turns out you can do more things with code than you expected, but it it's like that kind of stuff that is really fun to me. So long story short, I would love to see like the kind of things you're doing.

</details>

**Swixs**: 我会把它拿出来，我会把它拿出来。是的。但在我们深入探讨之前，我想总是先从一个高层次的问题开始：对于那些没听说过、没试过 **Cloud Cowork** 的人来说，它到底是什么？好的，简单来说，**Cloud Cowork** 是 **Cloud Code** 的用户友好版本。它的基本工作方式是，我们有 **Cloud Code**，对我们来说，它是一个相当令人印象深刻的代理工具，在去年12月，我们注意到越来越多的人在使用它，即使他们不是技术人员，不熟悉终端，或者他们熟悉终端，但开始将 **Cloud Code** 用于非编码工作负载，比如管理开支、填写收据或组织知识库，就像很多人喜欢的 **Obsidian** 时刻一样。我们想利用这一点，但也想把这种能力带给那些不熟悉终端、可能不知道如何安装某些东西的人。所以 **Cowork** 是在虚拟机中运行的 **Cloud Code**，增加了一些填充和更多的防护措施，使其更安全、更方便那些不想在工作时首先打开终端的人。它以这种更用户友好的方式推出很有趣，因为我总觉得对我来说，我把它当作更强大的用户工具，因为它可以更好地与 **Claude** 和 **Chrome** 以及所有其他工具集成。但这可能只是一个认知问题，对吧？

<details>
<summary>Original English</summary>

**Swixs**: I'll pull it up. I'll pull it up. Yeah. Uh but before we get into it, I I think always want to start with like a top level what is cloud co-work for people who haven't heard of it, haven't tried it out. Okay. Uh real quick, cloud co-work is a userfriendly version of cloud code. So the way it basically works is we have cloud code and for us fairly impressive agent harness that over December we noticed more and more people are using either even though they're not technical they they're not at home in the terminal or they are at home in the terminal but they started using cloud code for non-coding workloads right like managing expenses or like filling out receipts or organizing a knowledge base like there was a big obsidian moment that a lot of people liked and we wanted to capitalize on that but also bring bring this capability to people who are not terminal native and who might not know how to like brew install something. So co-work is cloud code running in a virtual machine with a little bit of padding a little bit more guardrails making a little safer a little bit more convenient for people who don't want to first open up the terminal when they go to work. It's interesting uh that it's kind of pitched that way as a more user friendly thing because I always feel like it it to me I I treat it as like well I'm familiar with cloud code like we we did a cloud code episode a year ago but this one is like even more power user tools because it it kind of integrates much better with like cloud and chrome and uh in all the all the other tooling but like may maybe that's like a perception thing right like

</details>

### 用户友好性与可扩展性

**Felix**: 不，说实话，我不认为你错了。这是我过去两周一直在思考的问题。当人们说“用户友好”时，他们会觉得“哦，这是简化版”，但实际上，这是超集。是的，我认为大约十年前，也许是十二年前，我在 **Microsoft** 工作时也发生过类似的事情，当时我们开始开发 **Electron** 以及基于浏览器的技术和跨平台的东西。最早的用例之一是 **Visual Studio Code**，它以前是一个网站。最初的说法是“哦，**Visual Studio Code** 是 **Visual Studio** 的更用户友好版本”，但以类似的方式，我认为当时有一些声音说“哦，这不是给严肃开发者用的，我们不会用它来做任何事情”。我认为最终发生的是，人们对 **Visual Studio Code** 为什么会变得如此流行有不同的说法，但我个人认为，它的可破解性和可扩展性起到了相当大的作用，对吧？你可以将 **Visual Studio Code** 连接到几乎任何工作负载，它非常容易修改，非常容易构建扩展。我认为 **Cowork** 可能也遇到了类似的情况，它非常容易扩展，也非常容易融入你的工作流程。所以，便利性我认为有点……是的，作为开发者，这显然是我们追求的目标，但我认为人们从中找到价值的方式是将其正确地映射到他们工作中实际需要做的事情上。

<details>
<summary>Original English</summary>

**Felix**: no honestly I don't think you're wrong this is like a thing I've been thinking a lot about for like the last two weeks so people when they say user friendly is like oh it's the dumb down version but no actually this is the superset. Yeah, like I think a similar thing happened a similar thing happened to me about 10 years ago like maybe 12 years ago when I was at Microsoft and we started working on on Electron and like browser based technologies and crossplatform stuff and one of the first use cases was Visual Studio Code which used to be a website and the initial narrative was oh Visual Studio Code is is like a more userfriendly version of Visual Studio but in a similar vein I think there were some voices saying oh this is not for serious developers like we're not going to use this right for like anything and I think in the end what happened is people have different stories about why Visual Studio Code became such a big thing but my personal my personal belief is that the hackability and the extendability is like played a pretty big role right you can hook in Visual Studio Code to like almost any workload it's so easy to hack on so easy to build extensions for it and I think co-work might be hitting a similar thing where it's very easy to extend and it's very easy to bring into your workflows uh so the convenience I think is a bit of Yeah, it's obviously the thing we strive for as developers, but I think the way people find value in it then is by properly mapping it onto whatever they actually have to do in their job.

</details>

### Cowork的设计过程

**Alessio**: 所以，去年年底，你看到了 **Cloud Code** 中非技术用途的激增。那么，设计流程是怎样的，才决定我们应该让 **Cloud Code** 运行起来？因为，我的意思是，你只用了10天就把它建好了。嗯，我确信之前肯定有一些讨论，关于“更容易使用”意味着什么？你知道，比如制作一个桌面 **GUI** 显然是一种方式，但产品中有很多细微之处。也许你可以向人们解释一下……

<details>
<summary>Original English</summary>

**Alessio**: So, end of last year, you see the spike of like non-technical usage in clock code. What's the design process to say we should make clock code work? Because I mean, you built it in only 10 days. Um, I'm sure there was some discussion before on what does easier to use mean? you know, like making making like a desktop guey is obviously one way to do it, but like there's a lot of nuance in the product. Like maybe talk people through

</details>

**Felix**: 触发我们决定构建一个独立产品的因素是什么？我们不应该构建一个不同的 **Cloud Code** 产品，然后也许还有一些更有趣的设计决策，也许你没有采纳。是的，我认为在 **Anthropic**，我们一直在思考如何让那些习惯于使用 **Claude** 回答问题的人，能够更多地利用这种能力来执行任务，对吧？它能为你解决问题，能为你构建东西。我们如何将这种能力带给那些目前主要习惯于聊天中“问答”模式的人？我们围绕这一点进行了大量的原型开发，可以追溯到一年半以前。很多人都在做这方面的工作。而且，在 **Anthropic** 内部，我们有一种非常“原型优先、演示优先”的文化。我们有很多内部原型没有公开发布。而 **Cowork** 实际上就是我们从众多原型中挑选出合适的片段而成的，对吧？这可能也是一个重要的限定条件，每当人们提到这个“10天”的数字时，我确实认为有必要提及我们并非从零开始。当时已经有很多东西在进行了，对吧？我认为人们记住这一点很重要，就像你构建一个网站时会使用 **React** 和其他很多东西一样，这与我们已经拥有的许多组件的情况类似。就决策路径而言，我认为我们生活在一个有趣的新世界，执行成本实际上相当低廉。

<details>
<summary>Original English</summary>

**Felix**: what was like the trigger of like we should build a separate thing. We should not build like a different clock code thing and then maybe some of the more interesting design decisions that maybe you didn't take. Yeah, I think at anthropic we've been thinking about ways to move people who are comfortable with using Claude to answer questions and bring more the power of like this thing to now like execute tasks for you, right? Can like solve problems for you, can like build things for you. How do we bring that capability to people who are currently mostly comfortable with like a like question answer paradigm within the chat? And we've had a lot of prototypes around that going back as far as like easily a year and a half. like we had a lot of people working on that. Um, and internally anthropic is a very prototype demo first culture. We have a lot of like internal prototypes that don't reach the public. And what coowork actually became is like we sort of picked the right pieces out of the many prototypes that we had, right? And that's that's maybe also like I think an important qualifier whenever people mention this like 10day number. I do think it's important to me to mention that we didn't start with scratch. There was like a lot of stuff already happening, right? like and I think it's important for people to remember that when you build a website you use react you use like a bunch of other things and this is like a similar scenario with like a lot of pieces we already had um and in terms of decision path I think we live in like an interesting new world where execution is actually quite cheap.

</details>

**Alessio**: 嗯。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Felix**: 所以也许……听到这个真是太疯狂了，对吧？

<details>
<summary>Original English</summary>

**Felix**: So maybe maybe what you would do that's so crazy to hear it's wild right

</details>

**Alessio**: 你应该……想法是廉价的，执行才是困难的部分。

<details>
<summary>Original English</summary>

**Alessio**: you should be ideas are cheap execution is the hard part. No, but like the we we

</details>

**Felix**: 不，但是我们过去可能生活在一个这样的世界里，你会找一个产品经理，产品经理会去拜访一些潜在客户，然后以这种非常低带宽的方式，试图找出他们遇到的问题，他们愿意购买什么。然后也许你能构建什么来满足这种需求，然后你回去，起草一份规格说明，思考它，然后你进行设计并执行它。我们 **Anthropic** 内部现在可能更接近于“甚至不用写备忘录，直接构建”的程度，比如“让我们非常快速地构建所有候选方案，让我们把它们都构建出来”，然后挑选最好的。我认为目前对产品和用户都最具影响力的决策是：我们如何重视你的本地电脑。我认为这是一个重要的决策点。很多人都思考过，这个东西，无论它是什么，最终应该在你的电脑上运行，还是应该在云端运行，因为这有很大的权衡，对吧？我想，如果我们解决了 **AGI**，那么在云端实现会很容易。但我认为，我可以从任何地方下载任何文件，然后把它放到 **Cowork** 中，这是一个巨大的突破。我的意思是，你提到重用某些组件很有趣。我认为这甚至是我一直在思考 **Cloud Code** 的问题，对吧？编写代码的成本正在趋近于零，等等等等，但实际上，拥有某种平台基础的价值似乎正在增加，因为当你构建这些新事物时，你可以将它们组合起来。

<details>
<summary>Original English</summary>

**Felix**: used to live in this world maybe where you would take a product manager and the product manager would go to a number of potential customers and in this like very low bandwidth way would try to try to like tease out what are the problems they're having, what are they willing to buy. Um and then maybe what can you build to like address that need and then you go back and you like draft a spec and you think about it and then like you make a design and you execute it. We internally had anthropic up now probably much closer to the point we're like don't even write a memo just like build like let's build all the candidates very quickly like let's just build all of them and then pick the best ones. I think the the decision that is most impactful both for the product as well for the users right now is like the way we put value on your local computer. I think that's a big decision point. A lot of people have thought about should this thing, whatever it is, should it ultimately run in your computer or should it run in the cloud because they're big trade-offs, right? I guess like if we solved O, it would be easy to do in the cloud. But I think like the fact that I can just download any file from anywhere and then put it in co-work there, it's like a big unlock. Um, I mean it's interesting you mentioned reusing certain pieces. I think this is something I've been thinking about even with cloud code, right? the price of like writing code is going to zero blah blah blah but it actually seems like the value of having some sort of platform substrate is like increasing because as you build these new things you can kind of plug them together.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Alessio**: 所以我几乎觉得当人们说“哦，很多软件的价值正在归零，因为你可以重新创建它”时，对我来说几乎是相反的，那就是拥有一个现有的平台来在其之上构建，甚至更有价值，因为他们可以附加东西。

<details>
<summary>Original English</summary>

**Alessio**: So I almost feel like when people are saying oh the value of a lot of software is going to zero because you can recreate it to me it's almost like the opposite is like having an existing platform to build on top of is like even more valuable because they can kind of bolt things on.

</details>

**Felix**: 是的。你显然有 **MCPs**，你有技能，你显然有模型，这是很大一部分。所有这些东西都结合在一起。你觉得这是一种有效的思考方式吗？人们应该更多地投资于这些基础组件以进行重建，还是你每次都在重新创建很多东西，因为事情在变化，重写比重用更容易，你知道吗？

<details>
<summary>Original English</summary>

**Felix**: Yeah. You have obviously MCPS, you have skills, you have like obviously the models which is a big part. All these things kind of come together. Do you feel like that's a valid way to think about it where people should invest even more in kind of like these primitives to rebuild on or are you like recreating a lot of it each time because like things change and it's easier to rewrite than reuse,

</details>

**Felix**: 我认为你是对的。我认为你是对的，整体平台确实非常有用。这可能与许多AI领域的人持有的观点有些不同。我其实不认为未来会是高度个性化的软件，以至于每个人都运行自己的版本。我真的认为我们所有人要拥有自己的内部聊天工具会相当困难，而且如果我想和你交流，那会怎么运作呢？在 **Cowork** 的背景下以及我们如何构建它，我认为这有点像一种组合。执行成本变得低廉，并不一定意味着重建所有基础组件。我认为我们的优先级……这其中也没有太多价值。所以，就财务而言，我的团队没有考虑重建 **Cloud Code**。我们非常坚定地从核心论点出发，即这应该是 **Cloud Code**，然后我们会在它之上构建东西。执行中变得更便宜的部分是：你如何将所有这些乐高积木组合起来，以一种对用户有意义且真正有价值的方式？现在你有许多不同的方法，关于你实际上将哪些东西提升为基础组件？你是否坚信你的所有产品都应该通过简单地组合基础组件来构建，同时身体也可用？你保留一些东西在内部。嗯，我认为这仍在发展中，但我认为可能会消失的是……我不确定它是否会完全消失，但我想说，对我个人而言，我可能不会再尝试在不与人测试的情况下，想出一个真正好的产品。这不是一个新概念，但过去你必须在选择技术A还是技术B，或者我们是这样构建还是那样构建等问题上做出昂贵的决策，我现在强烈认为，你只需把它们都构建出来，然后用一个小型焦点小组进行测试，然后选择表现更好的那个，对吧？这可能与我们一年前的工作方式都大不相同，对吧？我认为这发生得非常近。

<details>
<summary>Original English</summary>

**Felix**: you know? I think I think you're right. I think you're right that the holistic platform is really useful and this is maybe a whole like a somewhat contrarian view to a lot of people in AI. I actually don't think that the future is going to be hyper personalized software down to the point where everyone is running their own version. Like I actually think it's going to be quite hard for all of us to have our own internal chat tool and like if I want to talk to you like how is that going to work right in the in the context of co and how we build it. I think it's a bit of a combination like the the execution that gets cheap is not necessarily rebuilding all the primitives. I think our priority there's also not a lot of value in it. So for inance my team did not think about rebuilding plot code. We like very much started with the with the core thesis of this should be cloud code and then we'll like build things on top of it. The part of the execution that gets a little cheaper is like how do you take all of these Lego pieces and put them together in a way that makes sense for users and is like actually valuable. You have so many different approaches now in terms of what kind of what kind of things do you actually elevate to a primitive? Do you strongly believe that all your products should be built by just combining primitives with the body also available? you keep some things internal. Um, and I think that's still evolving, but I think what's probably going to go away is like I'm not sure if it's going to fully go away, but I'm going to say I think for me personally, I will probably no longer try to come up with a really good product without testing out with people. This is not a new concept, but wherever you used to have to make costly decisions around do we pick technology A or technology B or do we like um build it this way, build it the other way, I really strongly believe now you just build all of them and try them out with a small focus group and then whatever whatever is better is what you go with, right? And that that is probably quite different even from how we maybe worked a year ago, right? Like I think I think this happened very recently.

</details>

**Swixs**: 是的。我开始在 **Electron** 上构建一些东西，既然你在这里。巧合的是，**Electron** 和 **SQLite** 之间有一些问题，在开发和构建之间。无论如何，我就想，我们干脆用 **Swift** 重建整个东西吧，然后我就用 **Swift** 重新创建了整个东西，然后它就完成了，你知道，这没花什么力气。我甚至不懂 **Swift**。但是……

<details>
<summary>Original English</summary>

**Swixs**: Yeah. I started building something in on Electron since you're here. Coincidence, but then Electron and like SQLite are like there's like some issues that like between development and like building anyway. And I was like, let's just rebuild the whole thing in Swift and just recreated the whole thing in Swift and it's like it's done, you know, that didn't take any effort. I I I don't even know Swift. But

</details>

**Felix**: 是的，没错。我就想，反正我也不会审查它。随便吧。你可以用你选择的任何语言来写。但我所做的重要事情不是编写 **Electron** 绑定。我关注的是应用程序中发生的逻辑，你知道吗？然后模型就像是，是的，我可以重新创建同样的东西，就像……

<details>
<summary>Original English</summary>

**Felix**: yeah, exactly. I was like, I'm I'm not reviewing it anyway. Whatever. You can write it whatever language you pick. But the important stuff that I did was not write the electron bindings. I was like the logic of what happens in the app you know and then the model is like yeah I can just recreate the same thing as with

</details>

**Swixs**: 是的。我认为你仍然希望，特别是对于那些正在开发高性能软件或非常复杂软件的人，你仍然希望对架构有一些了解，但你可以用 **Markdown** 来实现，对吧？是的。你实际上不必阅读代码。再说一次，我仍然处于一种定义性的状态。我们能否为 **Cloud Cowork** 建立一个良好的心智模型？这就是我所拥有的，对吧？就像你说的，它就像是基础的 **Cloud Code**，我们不想碰它。有 **Claude** 应用程序，有 **Claude** 和 **Chrome**。我想你们在规划方面做了一些不同的事情，但是，我一直在和 **Cloud Code** 团队的 **Tariq** 交流，他说：“不，我们只是暴露规划。”也许你可以澄清一下，人们应该了解 **Cowork** 中包含哪些主要部分？

<details>
<summary>Original English</summary>

**Swixs**: yeah I I think you still want especially for people who are doing like high performance software or like really complex software uh you still want like some view of the architecture uh but you can use markdown for that right yeah uh you don't actually have to read the code again I'm still like on a sort of like a definitional thing um can we build a good mental model of cloud core work um this is what I have right like you said it's like fundament cloud code we don't want to touch it there's the cloud app there's cloud and chrome I think you guys do something different in planning but uh I've been talking with Tariq who's on the cloud code team and you guys are he's like no we just expose planning maybe you can clarify like what are the major pieces that people should be aware goes into co-work

</details>

### Claude Cowork的核心组件

**Felix**: 好的，我认为你基本上都掌握了，所以你可以或多或少地把规划部分排除在外。我认为 **Cowork** 中有几样东西确实很有价值。虚拟机可能是最强大的部分。我们目前运行的是一个轻量级 **VM**，我们将 **Cloud Code** 放入 **VM** 中，这样做有几个原因。安全和保障是一个重要原因。但即使你暂时忽略安全和保障，你只是想“好吧，我希望这个东西能做任何它想做的事情”，那么给 **Claude** 自己的电脑是相当强大的，这通常是一个好主意。就我们在 **Anthropic** 一直在做的架构、用户体验以及所有其他方面而言，将 **Claude** 积极地拟人化，并把它当作一个人，通常会非常有用。

<details>
<summary>Original English</summary>

**Felix**: like okay I think you basically have them so you can you can take planning more or less out I think there's a few things that are really valuable in co-work um the virtual machine is probably the most powerful thing so we currently run like we're We currently run like a lightweight VM and we put cloud code into the VM and we do that for for um a number of reasons. Safety and security is a big one. But even if you even if you ignore for a second safety and security and you're just like okay yolo I want this thing to do whatever it is it's quite powerful to give Claude it own computer that is like generally a good idea and in terms of architecture and UX and everything else that we've been working on anthropic it often is quite useful for you to like anthropomorphize um Claude aggressively and just be like this is a person

</details>

**Alessio**: 就像你有一个人，你会怎么做？

<details>
<summary>Original English</summary>

**Alessio**: like what would you do if you give if you had a person right

</details>

**Felix**: 我今天早上给我爸爸举了一个例子，他仍然坚持使用 **ChatGPT**，即使是用于编码。我说，如果你是一个开发者，你的雇主告诉你你不需要电脑，他们只会通过电子邮件给你发送代码，然后你通过电子邮件回复代码。这可能适用于后台的 **PE** 文件，但这不是很有效。所以我们用 **VM** 能做的是，因为它是一个 **Linux** 系统，**Cloud Code** 几乎可以自由地安装它需要的任何东西。它可以安装 **Python**，可以安装 **Node.js**。我们确实有严格的网络入口和出口控制。所以你仍然可以作为一个用户，用简单的语言向整个系统明确你接受什么，不接受什么。但我们绝不需要问一个真实的人，比如一个可能在营销部门或律师。我不需要去找律师问：“你同意我安装 **Homebrew** 吗？”

<details>
<summary>Original English</summary>

**Felix**: and the analogy I've given my dad this morning who is still like quite insistent on using chat even for coding things is if you were a developer and your employer told you that you don't need a computer, they're just going to like send you emails with the code and you send emails with code back. Like that maybe work for PE files in the back, but that is not very effective. Um, so what we can do with the VM is because it's a it's a Linux system, cloud code has more or less free reign to install whatever it needs to install. You can install Python, it can install Node.js. We do have strict network ingress and egress control. So you can still as as a user in like plain human language make it clear to to the entire system what you're okay with and what you're not okay with. But in no point do we have to ask a real person like a like a person who might be in marketing or a lawyer. I don't have to go to a lawyer and be like are you okay with me installing homebrew?

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Felix**: 对吧？因为这个问题和答案的含义是复杂而微妙的，不容易理解。这给了我们很多抽象，使得 **Claude** 非常强大。现在，围绕它，我们确实有很多东西几乎每周都在增长，你可能也注意到了，这些东西使得 **Cowork** 在某些任务上可能比单独的 **Cloud Code** 更好。但其中大部分实际上都存在于系统提示中。它们是关于我们能从你所做的工作中推断出什么？我们能向系统提示中引入什么，使其更有效？

<details>
<summary>Original English</summary>

**Felix**: Right. Because the implications of the question and the answer are complex and nuanced and like not not easy to reason about. And this gives us a lot of abstraction that makes Claude very powerful. Now then around it we we do probably have a number of things that also keeps growing almost every single week that you're probably noticing that make coach maybe better for certain tasks than just cloud code on its own. But most of those actually live in the system prompt. They're about like what can we infer about the work that you do? What can we what can we introduce into the system prompt to make that more effective.

</details>

### 与Chrome的深度集成

**Felix**: 当然，它与 **Claude** 和 **Chrome** 紧密集成。你注意到很多人，特别是随着模型变得越来越好，很多人在遇到 **MCP** 连接器时会束手无策。在这个时代，我不会去浏览25个 **MCP** 连接器，到处点击，然后其中一半还不能让我做任何事情。所以 **Claude** 和 **Chrome** 非常强大，因为我们可以直接与 **Claude** 和 **Chrome** 代理对话，它就会为你完成任务。是的。所以一个例子，在 **MCP** 中，老实说，我认为 **MCP** 的现状真的很难集成。我需要将 **Figma MCP** 添加到我使用的编码代理中。

<details>
<summary>Original English</summary>

**Felix**: It's of course like very tight integration with Claude and Chrome. You're noticing that a lot of people, especially as the models get better, a lot of people throw up their hands when it comes to MCP connectors in this era. I'm not going to I'm not going to go through like 25 MCP connectors, click off everywhere, and then like half of them don't let me do things anyway. So Claude and Chrome is quite powerful because we can just talk to the Claude and Chrome agent and that'll just do things for you. Yeah. So one example right in MCP honestly I think that the state of MCP is kind kind of like really hard to integrate. Um I need to I needed to add uh Figma MCP to the coding agent that I use.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Felix**: 但是我不想阅读文档，所以我只是让 **Claude** 去做，它非常擅长阅读文档。同样地，我需要为一个正在进行的项目设置一个 **Google Cloud** 账户，并在某个地方获取 **API** 密钥，而 **Google Cloud** 以其难以导航而闻名。所以我根本不想处理这些，我直接使用了 **Cowork**。

<details>
<summary>Original English</summary>

**Felix**: Uh and but I didn't want to read the docs so I just had called to it and it's it's great at reading docs and same same way I had to set up like a Google cloud um account for some project I was working on and get some API key somewhere and Google cloud is famously super hard to navigate. So I just didn't want to deal with any of it. I just used Clockwork.

</details>

### Cowork在编码任务中的应用

**Felix**: 在开发 **Cowork** 的第一周内，这发生得非常快。我发现自己开始将 **Cowork** 用于编码任务，这并不是我们最初构建它的目的，对吧？我们不需要这样做。但我发现自己……我发现自己在使用我们内部用于收集崩溃和调试信息的工具，我发现自己会挑出那些我认为可以轻松修复的错误，而不是那些可能是内核损坏或操作系统上其他问题的错误。然后我发现自己会挑出这些错误，然后告诉 **Claude**：“去修复这个bug。”我就想：“我在这里做什么？”再往上一层，告诉 **Cowork**：“我希望你访问所有这些崩溃工具。我希望你找出所有你认为可以修复的bug，而不是操作系统崩溃。然后我希望你告诉另一个 **Claude** 去修复所有这些。”

<details>
<summary>Original English</summary>

**Felix**: Within the first week of developing on co this happened very very quickly. Um I caught myself like starting to use co-work for coding tasks which is not ostensively what we built it for right we don't need to. But I found myself um I found myself like on our internal internal tool that we have for to collect crashes and just like debugging information and I found myself like picking out the ones that I think we can easily fix versus the ones that might be like kernel corruption or something else on the operating system. And I found myself sort of picking these out and then just telling Claude, "Go fix this bug." I was like, "What am I doing here?" Go one level up. Tell a cowork I want you to go to all these crash tools. I want you to find all the bugs that you think are fixable and not like an operating system crash. And then I want you to tell another Claude to like fix all of that.

</details>

**Alessio**: 嗯，那是另一个 **Claude** 吗？所以你可以启动另一个实例，还是……

<details>
<summary>Original English</summary>

**Alessio**: Um, and that's that's that's sort of another Claude. So you can spin up another instance or

</details>

**Felix**: 嗯，我目前做的是——这有点像一个技巧——我让它使用 **Claude Remote** 来远程控制自己。

<details>
<summary>Original English</summary>

**Felix**: uh it currently what I do is um and this is a bit of a hack but I tell it to use Claude remote to itself.

</details>

**Alessio**: 是的，这很有趣。所以你基本上是……如果你想象一个有20个bug的仪表盘，这是远程控制，或者 **Claude Remote**。抱歉，我只是想确认一下。我使用它的方式是，我有一个 **Cowork**，我告诉 **Cowork**：“这是我每天早上通常去寻找最新bug的地方。去阅读整个bug列表，区分哪些是可修复的，哪些是不可修复的，然后对于可修复的bug，对于每个bug，编写一个带有提示的 **Markdown** 文件。然后对于每个作为提示的 **Markdown** 文件，启动一个 **Claude** 会话。”

<details>
<summary>Original English</summary>

**Alessio**: Yeah, that's interesting. So you basically take if you if you imagine like a dashboard with like 20 bucks you this is remote control or Claude or remote. Sorry, I just wanted to confirm what the way I'm using it is I have co-work and I'm telling co-work here's where I normally go every morning to find the latest bugs. go read the entire bug list, separate out which ones are fixable, which ones are not fixable, and then for the fixable ones for is this almost loop for each bug, write a markdown file with a prompt. And then for each markdown file that is a prompt, start of a Claude set.

</details>

**Felix**: 所以，**Cloud Code** 原生就有所谓的子代理概念。这基本上就是一个子代理，但你没有使用子代理的功能。

<details>
<summary>Original English</summary>

**Felix**: So natively, cloud code has this concept of sub aents. And this is basically a sub aent, but you're not using the sub aents functionality.

</details>

**Alessio**: 我没有使用子代理功能。我没有使用的原因是，我把它作为一个 **Cloud Code** 远程任务来触发。是的，这很好，因为它就可以直接触发。我就可以去参加下一个会议，然后 **Cloud Code Remote** 就会开始工作了。

<details>
<summary>Original English</summary>

**Alessio**: I'm not using the sub aents functionality. And the reason I'm not is because I'm firing that off as a cloud code remote task. Yeah, that's kind of nice because then it can just fire it off. I can go to my next meeting and in cloud code remote now the work is happening.

</details>

**Felix**: 是的。你看，你已经开始在本地机器上使用云了，我认为这就像是：“嗯，难道不应该一切都云优先吗？”对吧？

<details>
<summary>Original English</summary>

**Felix**: Yeah. You see like you're already starting to use the cloud over your local machine and I think this is one of those things where like well shouldn't just everything just be cloud first, right?

</details>

### 本地电脑的价值与AI的访问权限

**Alessio**: 啊，这真是个好话题。我有很多关于bug的想法。好的，我普遍认为 **硅谷** 总体上低估了本地电脑的价值，我对此的默认论点总是：为什么我们都使用 **MacBook** 而不是 **iPad** 或 **Chromebook**？嗯，拥有本地机器仍然有价值。现在，当我想到 **Claude** 作为一个应该对你非常有用的实体，一个极其有用的实体时，我认为它需要访问你所能访问的所有工具。否则，它会在所有这些复杂方面受到限制。我们有两种方法。我们可以说：“好的，我们将一点一点地削减你电脑上的所有东西，并将其转移到云端。”这是一种方法。嗯，我认为其他产品也走了这条路。我个人认为——这是一个非常个人的观点——但就我使用的工具数量而言，我只是没有耐心给另一个工具授予对每个东西的权限，并保持这些权限的最新。我仍在努力解决的第二件事，而且我目前还没有一个好的答案，但第二件事是我仍在努力解决的是，让某人吸取你所有的工作并将其放到云端会是什么样子？例如，如果你可以点击一个按钮，我就能将你的整个电脑克隆到云端，这是你想要的东西吗？我还不完全相信每个人都会想要。

<details>
<summary>Original English</summary>

**Alessio**: Ah this is such a good group. I'm like so bugs I have so many thoughts about okay so I generally believe that Silicon Valley overall is undervaluing the local computer and my default argument for that is always how come we're all using MacBooks and not like an iPad or a Chromebook. um that there's like still value in in having a local machine. And now when I think about Claude as this entity that is supposed to be very useful to you, like it tremendously useful to you. I think that entity needs to have access to all the same tools you have access to. Otherwise, it's going to be hamstrong in like all these complex ways. And there's there's sort of two approaches we could take. We could say, okay, we're going to like one by one chip away at everything that is at your computer and move it into the cloud. That's that's one way to do it. Um, and I think other products have taken that path. I personally, this is a very personal opinion, but I personally for the amount of tools that I use, just don't have the patience to give another tool like permissions to every single thing and keep those permissions up to date. The second thing that I'm still grappling with, and I don't have a good answer for anyone just yet, but the second thing I'm still grappling with is what does it look like for someone to slurp up your entire work and put that in the cloud? Like if I just as an example, like if you could click a button and I just clone your entire computer into the cloud, is that something that you would want? I'm not totally convinced yet that all everyone will.

</details>

**Felix**: 嗯。这就像我们将会遇到的所有技术问题的上游问题，因为总的来说，我认为世界还没有为这类事情做好准备。我给你举一个我们可能很容易遇到的快速例子。作为一个桌面应用程序，理论上，在你的允许下，我们可以在你的电脑上做很多事情，包括读取你的 **Chrome** cookie，如果我们真的想这样做的话。我们可以获取你的 **Chrome** cookie，你必须为我们解密它们，但如果我们真的想，我们可以把它们放到云端。这是一个非常简单的解决方案。那会非常酷。我们可以说：“哦，我们可以在云端完成你所有的任务。”现在，嗯，很多网站，包括银行，如果它们看到来自两个不同位置的相同身份验证，就会锁定你的账户，然后你必须去分行说：“好的，我带着我的护照来了。”

<details>
<summary>Original English</summary>

**Felix**: Mhm. And that is sort of like upstream of all the technical issues we're going to have because like in general I think the world is not ready for this kind of stuff. Like I'll give you one quick example that would probably be very easy for us. So as a desktop app we in theory with your permission can do a lot of things on your computer including reading your Chrome cookies if we really want to do right. We could take your Chrome cookies you would have to decrypt them for us but we could put those on the cloud if we really felt like it. Pretty easy solution. That would be super cool. we could just be like, "Oh, we can do all your tasks in the cloud." Now, um, a lot of websites, banks included, if if they see the same authentication from like two different locations, will just lock down your account and now you have to go to the branch and be like, "Okay, I'm with I'm here with my passport."

</details>

**Alessio**: 你怎么知道的？哇。

<details>
<summary>Original English</summary>

**Alessio**: How do you actually know that? Wow. You

</details>

**Felix**: 你知道，尽管我们都厌倦了“代理”这个词，但对于代理的未来，我认为有很多事情需要慢慢跟上。在此之前，我作为一个从事 **Claude** 工作的人，能让 **Claude** 最有效的方式就是把它放在你工作的地方。我们的心智模型还有别的吗？所以，基本上，我越了解它是如何工作的，我就越能充分发挥它的潜力，对吧？是的。

<details>
<summary>Original English</summary>

**Felix**: know, as tired as well are of the term agent for the agentic future, I think there's a lot of stuff that sort of slowly needs to catch up. And until that's the case, the way I as someone who's working on Claude can make Claude most effective is to like put it where you're working. Anything else with our mental model? So like basically like uh part of me also just want like the more I understand how it works, the more I can use it to its full potential, right? Yeah.

</details>

**Swixs**: 所以我从你这里听到的是，你让我删除了规划功能。你没有在 **Cloud Cowork** 独有的功能上做任何特别的事情。

<details>
<summary>Original English</summary>

**Swixs**: And so what I'm get hearing from you is you told me to delete the planning thing. You're not doing anything special on on the that's only exclusive to cloud co-work.

</details>

### Cowork与Cloud Code的评估差异

**Felix**: 我们有一些技巧，但它们每周都在变化。我们评估 **Cowork** 可能会针对不同的用例，而不是评估 **Cloud Code**，对吧？你是怎么看待这个问题的？好的，所以 **Cloud Code** 不是 **Cowork**。是的，所以 **Cloud Code** 针对编码任务进行了高度优化，我们主要根据它在典型编码任务中的表现来评估我们是否做得更好或更差。而 **Cloud Cowork** 另一方面，我们更多地针对典型的知识工作进行评估，比如你在财务或法律办公室中会遇到的那种工作。嗯，我个人的用例总是管理我的事情，比如管理我的抵押贷款之类的，对吧？或者为我和我的家人做计划。这些是我们评估 **Cowork** 的用例。你可能注意到的是我们对系统提示所做的细微改变，我们在系统提示中放入了什么，我们如何通过我们给 **Claude** 的工具来引导它。嗯，它在某个方向上会更好，或者在另一个方向上会更好，其中存在权衡。权衡无处不在。**Cloud Code** 更适合代码，而 **Cloud Cowork** 更适合非编码任务。这些差距是否会在下一代模型中继续存在，对我来说有点不清楚。是的，因为现在我们所做的这些超优化，我不确定它们还能持续多久。

<details>
<summary>Original English</summary>

**Felix**: We have some tricks but they're sort of like change week over week. We eval coowork maybe against different use cases then he would evil clock code right how do you think about it this way okay so like clock code is not clockwork yeah so cloud code is like quite optimized for coding tasks and we mostly evaluate whether or not we're getting better or worse depending on how good it is at like a typical sweet job and cloud co-work on the other hand we evaluate more against typical knowledge work the kind of stuff you would find in finance or in like maybe like in like a legal office um my personal use case is always like managing my things like managing my puzzle mortgage or something like that, right? Or like we w planning for me and my family. Those are the kinds of use cases we eval co-work on. And what you might be picking up on is like the subtle changes we make to the system prompt, what we put in the system prompt, how we steer Claude with the tools we give it. Um like either it be better in one or the other direction where there's a trade-off. Trade-offs exist a lot. Cloud code will be better for code and Claude co-work will be better for non-coding tasks. Will those gaps still exist in the next few generations of models is like a little unclear to me though. Yeah, because right now these like hyper optimizations we make I'm not sure for how long they're still relevant.

</details>

**Swixs**: 我认为我所指的是，它在定性上感觉有所不同。我可能只是把它都归结为提示，并且过度解读了，但它会提出一个九步计划。我可以编辑计划并提供反馈，然后看到它执行计划。是的。感觉比 **Cloud Code** 更具长远性。但也许这在 **Cloud Code** 中已经存在了，你只是为它构建了一个更好的用户界面。

<details>
<summary>Original English</summary>

**Swixs**: I think what I was referring to was also it it just uh qualitatively felt different when I probably it's just all prompting and I'm reading too much into it but like that the fact that it comes out with like a ninestep plan. I can edit the plan and give feedback and and and see it execute the plan. Yeah. felt more long range than in cloud code. But maybe that already existed in cloud code and you just built a nicer UI for it.

</details>

**Felix**: 两者兼而有之。嗯，如果构建规划功能的 **Cloud Code** 团队的人坐在这里，他们可能会说：“是的，我们在 **Cloud Code** 中拥有所有这些功能。”而且他们确实有。嗯，我认为人们倾向于给 **Cowork** 安排一些时间跨度更长的任务。

<details>
<summary>Original English</summary>

**Felix**: It's kind of both. Um like if the cloud code people who built the planning functionalities would sit here, they would probably say yes, we have all of those things in clock code and they do. Um I think people tend to give co-work tasks that are maybe of a longer time horizon.

</details>

**Swixs**: 我以为他这么久。是的。

<details>
<summary>Original English</summary>

**Swixs**: I thought he's so long. Yeah,

</details>

**Felix**: 这就是其中一件事，对吧？你只是觉得工作量可能稍微大一点。然后第二件事是，因为当任务变得更长时，它会变得有点模糊。我们确实会告诉 **Cowork** 大量使用规划工具，或者大量使用提问工具。对吧？我们确实希望它能提出不同的场景，比如“好的，找出用户真正想要什么。不要工作四个小时然后带着错误的东西回来。”

<details>
<summary>Original English</summary>

**Felix**: that's like one thing, right? You're just like that the the chunk of work tends to be maybe a little bigger. And then the second thing is that because the word when it gets longer it gets a little bit more ambiguous. We do tell co-work to make heavy use of the planning tool or to make heavy use of the ask user question tool. Right? We do wanted to come up with like different scenarios of okay tease out what the user actually wants. Don't go off to work for like four hours and then come back with the wrong thing

</details>

**Felix**: 你可能也注意到了这一点。嗯，我希望我能告诉你我构建了一个神奇的东西，它有什么秘密武器，不不不。我的意思是，清晰度是好的，你知道工程师们只是想知道，这样他们就可以围绕它进行规划。然后我认为对我来说，嗯，我意识到我必须切换到我的另一台机器，因为这是一台没有我会话的新机器，但是，是的，规划对我来说真的很重要，这样我才能批准或者查看它是否正确。提问功能呈现得非常漂亮。我的意思是，它也存在于 **Cursor** 和 **Cloud Code** 中，但我认为能看到它理解我，理解我想做什么，真是太好了。

<details>
<summary>Original English</summary>

**Felix**: and you're probably picking up on that. Um I wish I could tell you I like built this magical thing and it's like there's some secret sauce on No, no, no. I mean it's just clarity is good that you know engineers just want to know so they can they can plan around it and then I think also for me um I'm realizing I have to switch to my my other machine because this is a new machine that doesn't have my session but uh yeah the the the planning is really important for for me to like approve or like to see whether it's like it's right the ask user question is so beautifully presented I mean it al also available in like cursor and and in cloud code but like I I think like it's so nice to see that it like It's kind of for me like to understand that it gets me. It gets what I want to do.

</details>

**Swixs**: 是的。是的。先前的艺术。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Yeah. Prior art.

</details>

### 评估与模型能力

**Alessio**: 仅仅就评估这个话题来说，当你说“评估”时，我认为人们对此非常模糊。它仅仅是凭感觉测试，还是你们有 **Cloud Cowork** 的自动化程序化评估？当我们说“评估”时，我们真正的意思是，我们基本上会获取整个对话记录，包括所有最终声称属于它的工具，然后我们根据我们所做的调整来衡量输出是什么。对吧？所以我们确实经常运行这个。我们在训练中使用它。嗯，我们在……如果你将后期训练与围绕它的脚手架分开来看。**Cowork** 存在于脚手架领域，但显然我们也会对其进行一些训练。所以当我们说“评估”时，我们的意思是，给定某个对话记录，输出会是什么样子？包括文件输出以及实际的token输出，就像你在聊天窗口中看到的那样。我很好奇，模型智能与终端工具的使用在多大程度上导致了失败模式？比如，规划就是一个很好的例子，对吧？一件事是提出一个计划。另一件事是制作一个漂亮的电子表格，让你能够执行这个计划。你看到它是如何演变的？我经常纠结的一点是，无论你提出什么样的脚手架，我认为我们仍然存在一些模型过剩，即模型的能力远超用户最终使用它的目的。我认为部分原因是，我们只是没有给模型提供所有它理论上能够做到的工具，对吧？这是一件事。嗯，然而，每当你放置脚手架时，你就会想，这个脚手架会在什么时候消失？以及你投入多少精力来找出正确的脚手架，这有点像一场赌博，对吧？作为一名工程师，我非常享受的一点是，在 **Anthropic** 工作，在一家前沿实验室工作，我可能对即将发生的事情有更多的洞察力，比如下一个模型是什么，模型能做什么，擅长什么，不擅长什么。我越来越想知道，我们是否应该投入过多精力在这些脚手架修正上，因为模型可能本来不会出错，只是没有做你想要的事情。

<details>
<summary>Original English</summary>

**Alessio**: Just on the topic of evals, when you say eval, I think people are very vague about what it means. Is it just like vibe testing or do you have like automated programmatic evals of cloud cowwork? When we say eval uh what we really mean is that we essentially take the entire transcript including all the tools that claim ultimately to it and we then measure what are the outputs depending on what we tweak. Right? So we do run that a lot. We use that in training. Um we use that in in like if you sort of separate out post training from like the scaffolding around it. Co-work sort of exists in the scaffolding space but obviously we also train on it a little bit. And so when we say eval, we mean given the certain transcript, what do the outputs look like? Including the file outputs as well as like the actual token outputs like the ones that you see in the chat window. I'm curious um how much of the failure modes are the model intelligence versus like the usage of the end tool to put the intelligence in. Like the wall planning is like a good example, right? It's like one thing is to come up with a plan. The other thing is like make a nice spreadsheet that kind of runs you through the plan. Like how have you seen that evolve? The thing that I grapple with a lot is that whatever scaffolding you come up with, I think we still have a bit of sort of like model overhang where the model is dramatically more capable than what users end up using it for. And I think part of that is that we're just not getting the model all the tools to do all the things it's theory capable of, right? That's like one thing. Um, however, whenever you do put the scaffolding, that's sort of wondering at what point at what point will that scaffolding go away and like how much you invest in figuring out what the right scaffolding is, it's kind of up to it's a little bit of a bet, right? And one thing that I as an engineer quite enjoy is that like working in the topic and working at a frontier lab, I maybe have a little bit more insight into what's coming coming down the chute in terms of like what's the next model, what is the model capable of, what it's good at, what is it bad at. And I'm I'm increasingly wondering is the right thing for us to like really invest too much in sort of these like scaffolding corrections where the model might otherwise not misbehave but just not do the thing that you want

</details>

**Felix**: 还是说，我们应该尽可能地赋予它能力，并确保这些能力是安全的，这样最坏的情况就不会像原本那样糟糕，然后简单地等待下一个模型发布。我个人目前更倾向于后者。我认为我们将看到很多应用程序和公司利用AI做一些非常令人印象深刻的事情，这些事情在短期内可能看起来非常有效，因为它们非常专注于个别用例。但我认为一旦模型在泛化方面做得更好，并且在那些特定用例中表现更好，而不需要过多的引导，我不确定这种情况会持续多久。你已经可以在技能和 **NTP** 服务器中看到这一点，对吧？我们已经看到了从 **MCP** 服务到技能的这种缓慢转变。也许一个很好的例子是 **Barry**，他创建了技能。他最初在捣鼓一些东西，老实说，它看起来很像 **Cowork** 今天所做的事情。他当时在思考，如果 **Cowork** 是为那些不想编写代码的人设计的，那会怎么样？

<details>
<summary>Original English</summary>

**Felix**: or is it to just like give it as many capabilities as possible try to make those safe so that the worst case scenarios like not as bad as it might be otherwise and then just simply wait a second for the next model drop. I'm personally currently more leaning into the ladder. I think we're going to see a lot of like applications and companies that do very impressive things with AI that in the short term might seem very effective because they're very specialized to individual use cases. But I think once models get better at generalization and get better at like those specific use cases without being super guided on those. I'm not sure how long that's going to stick around. And you can kind of kind of already see this in like skills and NTP servers, right? We we've already seen sort of this like slow shift from MCP service to skills and like maybe a good example is Barry who made skills. He was initially hacking on something that honestly looked a lot looked looked a lot like what co-work does today. It was sort of thinking about what if co-work but for like people who don't want to build code

</details>

**Felix**: 嗯，他也把这个作为桌面应用程序中的一个原型。我们想到的第一个用例是：哪些编码用例可以真正从图形界面中受益，并且可以与实际的底层代码稍微分离？每个人都得出了相同的答案：数据分析。而现在我们有多少用户？有多少……它总是数据分析。

<details>
<summary>Original English</summary>

**Felix**: and um he too did that as a prototype inside the desktop app. One of the first use cases we thought of were okay what what are like coding like use cases that could really benefit from graphical interfaces and like from being a little separated from the actual underlying code and everyone comes up with the same answer is data analysis whereas like how many users do we have today how many like it's always data analysis

</details>

**Felix**: 我认为最终促成技能的是，我们想把这个小原型连接到我们的数据仓库，团队很快发现，与其为这个东西构建一个自定义工具来与我们的数据仓库对话，他们不如直接制作一个 **Markdown** 文件，就像：“亲爱的 **Claude**，如果你想获取数据，这是端点。这是 **API** 的样子。你自己搞定。”

<details>
<summary>Original English</summary>

**Felix**: and I think the thing that ultimately led to skills is that we wanted to connect this little prototype to our data warehouse and the team very quickly We discovered that like instead of building a custom tool for the thing to talk to our data warehouse, they just like made a markdown file like dear Claude, if you want to get data, here's the end point. Here's what the API looks like. You figure it out

</details>

**Alessio**: 然后交出控制权。

<details>
<summary>Original English</summary>

**Alessio**: and then hand over control.

</details>

**Felix**: 是的。是的。也只是在抽象层面上再提升一步，对吧？就是说，与其告诉它：“这是一个 **CLI**，请调用这个 **CLI**，”或者“这是一个 **MCP**，请调用这个接口形状，”不如直接说：“这是端点。如果你想知道什么，如果你在这里发布，也许你可以发布 **SQL**，那就可以了。”结果非常有效，他们开始尝试同样的模式，即只给模型一个描述它需要做什么的 **Markdown** 文件。

<details>
<summary>Original English</summary>

**Felix**: Yeah. Yeah. Also just like maybe go one step up in the layer of abstractions, right? Just like instead of instead of telling the thing here's a CLI, please call this CLI or here's an MCP, please call this interface shape, just like this is the endpoint. if you want to know something if you post here maybe you can do post SQL it's going to be okay and that ended up being so effective that they started trying the same pattern of like just giving the model a markdown file that describes whatever it needs to do

</details>

**Felix**: 整个事情最终变成了技能，我们觉得：“我们应该把它打包起来，这是个好主意。”是的。嗯，我们请过 **Barry Mahesh** 参加我们的会议，他确实有一个好主意。

<details>
<summary>Original English</summary>

**Felix**: that the whole thing eventually became skills and we're like we should package this up this is a good idea yeah um we've had Barry Mahesh uh on on our conference and uh he's definitely got a good idea there

</details>

### Cowork的个人应用案例

**Swixs**: 是的，我想向你展示我一直在如何使用 **Cloud Cowork**。这是我最喜欢的部分。

<details>
<summary>Original English</summary>

**Swixs**: yeah I wanted to show you that how I've been using cloud co-work This is was my favorite part.

</details>

**Swixs**: 这就是我。嗯，这就是我们运营 **Discord** 的方式。嗯，我们最初不信任 **Cloud Cowork**。这是我第一次使用它。

<details>
<summary>Original English</summary>

**Swixs**: This is so this is like me. Uh this is how we run the discord. Uh we literally uh at first I didn't trust cloud core. This is my very first usage.

</details>

**Felix**: 好的。

<details>
<summary>Original English</summary>

**Felix**: Okay.

</details>

**Swixs**: 对。所以当时我想，好吧，我将手动从 **Zoom** 下载我所有的录音，然后上传到 **YouTube**，因为这是一个非常费力的过程。我必须点击点击点击，**YouTube** 并不是超级用户友好。嗯，然后它就完成了。然后我就想，实际上，你知道，即使是从 **Zoom** 下载的部分，我也应该把它放到 **Cloud Cowork** 中。然后我就这样做了。这里有很多，它开始在这里压缩，然后它甚至能够做一些事情，比如查看视频的单个帧来命名视频，这样我就可以自动上传，这取代了我作为 **YouTuber** 的工作。

<details>
<summary>Original English</summary>

**Swixs**: Right. So then I was like okay I will just try to manually download from zoom all my recordings and upload it to YouTube because this is a very laborious process. I got to click click click YouTube um isn't super user friendly. uh and it just did it and then I was like actually you know even the download from zoom part I should also put into cloud co-work and then I did it right here's a bunch of and it starts compacting here and and it it starts to even be able to do things like look through the individual frames of the video to name the video so I can upload it automatically and this replaces my job as a YouTuber

</details>

**Felix**: 我们将永远感激你的创造力。

<details>
<summary>Original English</summary>

**Felix**: we will forever appreciate your creativ

</details>

**Swixs**: 但随后它会压缩并生成一个新的东西。对。所以我没有最初的东西，但我让它创建自己的技能，这样重复的、一次性的、人工引导的任务就能变得更自动化，我也可以独立使用和重用这些技能。嗯，它显然可以编写技能，这些技能会进入这里的上下文和技能底部，这真是太棒了。嗯，所以我现在每周都会做所有这些技能。我知道你发布了计划中的 **Cowork**，我还没做过，但是……

<details>
<summary>Original English</summary>

**Swixs**: but then by the way it compacts and makes makes like a new thing Right. So I I don't I don't have the initial initial thing, but then I asked it to make its own skills so that it so that something that's repetitive and one-off and human-guided becomes more automated and I can use the skills independently and reuse them. Uh and it obviously can write skills and that goes into context and skills at the bottom here which is which is so nice. Um so I have all these skills that I now sort of do on a weekly basis. I know you've released scheduled co-works which I haven't done yet but

</details>

**Felix**: 当然，他们应该尝试一下。我认为这对我来说太棒了，也很有趣，因为我认为技能特别有趣的一点是它们非常容易制作。任何人都可以制作一个技能。一条短信就可以是一个技能，它们可以高度个性化地为你服务，这就像是抽象层，对吧？嗯，我只是猜测，但我认为你非常擅长你的工作。你可能已经给了它一些关于如何做的指导，对吧？

<details>
<summary>Original English</summary>

**Felix**: of course they should try them. I I think this is like so wonderful and fun for me to see because I think one thing that is very fun for me about skills in particular is that they're so easy to make. Like anyone can make a skill. Like a text message could be a skill and they can be so hyperpersonalized to you and this is like sort of the substraction layer, right? Like um I I'm just guessing but I assume you're very good at your job. You've probably given this thing some guidance about how to do it,

</details>

**Swixs**: 对。我只是说把所有东西都打包成一个技能，对吧？

<details>
<summary>Original English</summary>

**Swixs**: right? I I just said wrap everything up into into a skill, right?

</details>

**Felix**: 是的。然后，然后我想，实际上有时我可能需要把事情分开，因为有些部分会失败，或者有些部分可能需要单独处理。所以我让它把一个技能分成三个技能。所以它就像一个技能拆分器，然后有一个父技能，如果我想用它，它会协调所有这些。但是，嗯，我认为这真的很好。嗯，还有一个部分是 **Google Chrome** 的事情，我告诉过你，我想：“好吧，你知道用 **Cloud Cowork** 上传到 **YouTube** 有什么更好的方法吗？那就是实际查看文档，以编程方式上传到 **YouTube**，然后把它放到一个技能中。”我以前从未这样做过。我不想处理 **Google Cloud**，所以 **Cloud Cowork** 为我做了。

<details>
<summary>Original English</summary>

**Felix**: Yeah. And then and then I was like actually sometimes I might need to break uh things apart because some parts fail or some parts might be needed in individually. So I told it to split one skill into three skills. So it's like a skill splitting thing and then there's like a parent skill that just orchestrates all of them if I want to use that. But like um I think that's that's like really good. Uh and uh there's there's one more part which is the uh Google Chrome thing that I told you about where I'm like okay you know what's better than uploading using cloud coork to YouTube like actually looking at the docs to like programmatically upload to YouTube and then putting that in a skill and I've never done that before. I don't want to deal with Google cloud so cloud coork does it for me.

</details>

**Alessio**: 这真的很酷。

<details>
<summary>Original English</summary>

**Alessio**: That is really cool.

</details>

**Swixs**: 所以我只是，我不在乎。我只是让它做它的事情。我不在乎，这真的不重要。

<details>
<summary>Original English</summary>

**Swixs**: So so I I just I don't care. I just like let it do it thing. I don't it doesn't really matter.

</details>

**Alessio**: 这真的很酷。然后你，我猜，只是将技能与它构建的脚本配对。

<details>
<summary>Original English</summary>

**Alessio**: That is really cool. And then you I assume paired the skill just with the script that it's built.

</details>

**Swixs**: 是的。然后我只是更新技能。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. And then I just update update the skill.

</details>

**Alessio**: 啊，这太棒了。是的，太棒了。

<details>
<summary>Original English</summary>

**Alessio**: A that is beautiful. Yeah, that's wonderful.

</details>

**Swixs**: 这有点像一个技能，基本上我认为人们进入 **Cloud Cowork** 的方式是：拿一个你通常需要点击操作的知识工作任务，然后尝试把它变成……然后你就会想：“好吧，如果我更进一步呢？”“好吧，如果我再更进一步呢？”然后你就会随着你对 **Cowork** 的信任增加，不断扩展它的范围，并教它如何取代你。是的，这有点像玩 **Factorio**，但却是为了你自己的生活。就像你说的，你从非常小的事情开始。是的。你开始自动化一些非常微小的事情，一旦它奏效，你就会不断地在这个自动化帝国上添加东西。只是让你的生活变得越来越容易。我最喜欢的技能是，每天早上 **Cowork** 都会查看我的日历，确保没有冲突，因为人们有时会临时安排很多会议，或者有时会错过。这通常很痛苦。

<details>
<summary>Original English</summary>

**Swixs**: It's kind of like a skill like basically I think like the way that people ease into cloud co-work is like take a knowledge work task that you would normally be clicking around for and then uh try to turn turn that and then you do the okay well what if you went further okay and then what if you went further what and you sort of expand the scope of co-work as you gain trust with it and and also teach it how to replace you. Yeah, it's like a little bit like playing Factorio but for your own life. Like you say, you start really small. Yeah. You start automating something really tiny and like once it clicks, you keep adding onto this like automation empire. Just like make your life easier and easier. My favorite skill has been um every single morning Cobberg starts looking at my calendar and make sure that there's no conflicts because people tend to schedule a lot of meetings sometimes last minute or sometimes miss it. often painful

</details>

**Felix**: 很多产品都存在过很多类似的情况。我在自定义提示中写了它。我还没有把它做成一个技能。嗯，老实说，应该做成技能。是的。

<details>
<summary>Original English</summary>

**Felix**: and a lot of products have existed like that a lot. I've written in the custom prompt there. I haven't made it a skill. Um honestly should. Yeah.

</details>

**Felix**: 但我给了它非常明确的指示，比如：“好的，如果这些人预订了其他会议，我可能会去参加他们的会议，比如如果 **Daario** 安排了一个会议，对吧？”

<details>
<summary>Original English</summary>

**Felix**: But I've given it like pretty clear instructions about okay here are some people if they book over other meetings I'm probably going to go to their meeting like if Daario schedules a meeting, right?

</details>

**Alessio**: 不要试图重新安排 **Daario** 的日程，对吧？

<details>
<summary>Original English</summary>

**Alessio**: Not try to reschedule Dario, right? Um,

</details>

**Felix**: 嗯，我认为还有一些其他规则，关于我更关心哪种会议，不那么关心哪种会议，什么可以推迟，比如我想工作的时候，不想工作的时候。正是这些非常小的事情，我认为能与人们产生共鸣。对，当我们推出 **Cowork** 时，我认为在 **Twitter X** 上最火的用户短语之一是“清理你的桌面”，这当然很傻。这真是个事，对吧？你不需要一个模型来清理你的桌面。不完全是。嗯……

<details>
<summary>Original English</summary>

**Felix**: and I think there's some other rules in there about like what kind of meetings I care more about, what kind of meetings I care less about, what is okay to like maybe punt like when I want to be when I want to be working, when I don't want to be working. And it's those really small things that I think kind of click with people. Right when we launched co-work, I think one of the user phrases that went most viral on Twitter X was clean up your desktop, which is of course silly. That's such a thing, right? Like you don't need a model to clean up your desktop. Not really. Um

</details>

**Swixs**: 就像这样，清理我的桌面。

<details>
<summary>Original English</summary>

**Swixs**: like this like clean out my desktop.

</details>

**Felix**: 是的，没错。是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah, exactly. Yeah,

</details>

**Swixs**: 我需要，我需要选择我的桌面，对吧？我想，给它访问我的桌面的权限。

<details>
<summary>Original English</summary>

**Swixs**: I need to I need to choose my desktop, right? I guess give it access to my desktop.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 好的。嗯，好的。这很吓人。去做吧。

<details>
<summary>Original English</summary>

**Swixs**: Okay. Uh okay. This is very scary. Go do it.

</details>

**Felix**: 我用我的下载文件夹做了。它说：“你有这么多条款清单，还有你办公室租赁合同的八份副本。”我就想：“好吧，别冲我吼。”

<details>
<summary>Original English</summary>

**Felix**: I did I did it with my downloads folder. It was like you have so many term sheets and there's like eight copies of your rental lease for your office. I was like all right, like don't yell at me.

</details>

**Felix**: 这就像一个很小的任务，我通常不会出去告诉别人我开发了一个产品，可以帮你整理照片。嗯，因为它感觉很小，但我想就你说的，就像……

<details>
<summary>Original English</summary>

**Felix**: It's like it's such a small task and like I I would never go out there normally otherwise and tell people I've built a product. they can organize your photo for you. Um because it feels small, but I think to your point like

</details>

**Swixs**: 哦，这是“提问用户”的功能。

<details>
<summary>Original English</summary>

**Swixs**: Oh, here's here's the here's the ask user questions.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 嗯……

<details>
<summary>Original English</summary>

**Swixs**: Uh

</details>

**Felix**: 很漂亮，对吧？它是明显的垃圾吗？你可能不应该点击那个。

<details>
<summary>Original English</summary>

**Felix**: beautiful, right? Is it obvious junk? You probably shouldn't click that.

</details>

**Swixs**: 不，如果没做完……

<details>
<summary>Original English</summary>

**Swixs**: No, if it's not done,

</details>

**Felix**: 只要可逆，我就不……

<details>
<summary>Original English</summary>

**Felix**: as long as it's reversible, I don't

</details>

**Swixs**: 也许吧。是的。

<details>
<summary>Original English</summary>

**Swixs**: maybe. Yeah.

</details>

**Swixs**: 嗯，是的。不，我有一个典型的所有东西都超级混乱的文件夹。所以，是的，我认为这非常有帮助。所以，这是一个相当简单的任务，但我……好的，在这里。对。这是进度。我在这里看不到这个。我就想，这肯定和 **Cloud Code** 有什么不同，因为我想……

<details>
<summary>Original English</summary>

**Swixs**: Uh yeah. No, I have a I have a typical everything is super messy folder. So, yes, I think this this is super helpful. So, this is a pretty simple task, but I Okay, here it is. Right. Here's the progress. I don't see this in this. I'm like, this got to be something different than uh than cloud code because I'm like

</details>

**Felix**: 我们确实是。是的。我们确实是系统提示的。我们就像：“好的，我们希望你思考这个任务和方法。”是的。

<details>
<summary>Original English</summary>

**Felix**: we do Yeah. That's we do system prompted. We're like, all right, we want you to think about like this task and method. Yeah.

</details>

**Swixs**: 然后我就可以，我就可以做一些小小的建议，针对这些事情。太棒了。看看这个。我，我可以说：“哦，不要那样做。不要这样做。”太神奇了。

<details>
<summary>Original English</summary>

**Swixs**: And then I can I can I can do like little suggestions for for for these things. It's beautiful. Look at this. I I can I can like say like, oh, don't do that. Don't do this. It's amazing.

</details>

**Felix**: 我很高兴你喜欢它。嗯，我的意思是，反过来说，我们是 **Cloud Code** 团队的一部分。如果你想在 **Cloud Code** 中使用这个。是的。是的。是的。嗯，所以，是的，我的意思是，嗯，这真的很好。显然我有点狂热。嗯，你知道我还有其他事情，比如注册 **PG&E**。

<details>
<summary>Original English</summary>

**Felix**: I'm so happy you like it. Um I mean the other way around like we're part of the cloud code team. If you would like this in cloud code. Yeah. Yeah. Yeah. Uh so so yeah, I mean uh this is really good. Obviously I'm like kind of raving about it. Uh you know I have other things like sign up for PG&E.

</details>

**Swixs**: 所以如果你能替我打电话，那会很棒。嗯，我，我确实……

<details>
<summary>Original English</summary>

**Swixs**: So if you can do phone calls for me that would be great. Um I I do

</details>

**Felix**: 人们已经做到了。显然你不能原生做到，但人们已经通过各种其他提供商做到了。

<details>
<summary>Original English</summary>

**Felix**: people have done that. Obviously you can't do that natively but people have done that with like various other providers.

</details>

**Swixs**: 是的。嗯，然后这就像注册 **Figma MCP**。嗯，我真的在尝试做所有事情，嗯，数据分析也是。我确实认为，嗯，哦，设计到代码，嗯，非常好，对吧？所以就像，这是一个 **Figma** 文件，我会拿过来，然后这里就像很多其他任务一样，是知识工作，比如取代我的手动点击，但这不……我通常会为此使用 **Cloud Code** 或 **Claude Code**，但因为我感觉你拥有更好的 **Chrome** 集成……

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Uh and then this is like signing up for the Figma MCP. Um I I really am trying to do like everything um data analysis as well. I do think um oh design to code uh very very good right so like here's a Figma file I'll take it and then this is where like a lot of other tasks is like knowledge work like replace my manual clicking but this is no I would normally use cloud code or cloud code for this but because I perceive that you have better chrome integration

</details>

**Felix**: 我认为你实际上可以做得更好，而且这，这，这，这让我一次性完成了我的会议网站。

<details>
<summary>Original English</summary>

**Felix**: I I think you can actually do a better job of this and I this this is oneshotted my uh conference website

</details>

**Alessio**: 这很酷，在某个时候我很想听听你对桌面应用程序中代码的看法，我从不使用它，它是同一个团队，同一个团队。

<details>
<summary>Original English</summary>

**Alessio**: that's pretty cool like at some point I would love to like hear how you feel about code in in the desktop app which is like I never use which is the the same team same team

</details>

**Swixs**: 所以我使用终端中的 **Cloud Code**，我认为这是 **Cloud Code** 的默认方式。

<details>
<summary>Original English</summary>

**Swixs**: so I use the cloud cod in terminal which I I perceive to be the default way of

</details>

**Felix**: **Cloud Code**。

<details>
<summary>Original English</summary>

**Felix**: cloud coding

</details>

**Felix**: 所以这有一点，抱歉，我只是，我不是来推销所有这些产品的，所以我可以谈谈其他事情吗？我不知道外面的人是否想听我宣传我的东西一个小时。

<details>
<summary>Original English</summary>

**Felix**: so one thing this has sorry I'm just like I'm not I'm not here to wrap all these products so can I talk about other stuff like I'm not sure if people out there want to like hear me advertise my stuff for like an hour

</details>

**Felix**: 但是，嗯，这个东西内置了一个浏览器，很多产品都有内置浏览器。我认为让 **Claude** 看到你实际正在处理的东西，会使其效率大大提高，这可能就是你在 **Cowork** 中看到的情况，因为它可以看到 **Chrome**，它可以调试 **DOM**，它可以看到东西。嗯，这确实使其更强大。

<details>
<summary>Original English</summary>

**Felix**: but um this thing has like a built-in browser which is a thing a lot of products have a built-in browser and I think giving Claude eyes into like what you're actually working on makes it so much more effective and that's probably what you've seen in co because it can see Chrome, it can like debug the DOM, it can like see things. Um, that does make it more powerful.

</details>

**Swixs**: 是的。所以，所以我想，嗯，我的心智模型有点破裂了，因为我只使用 **Cowork**，因为我以为它内置了浏览器功能，但我明白 **Cloud Code** 应用程序或 **Cloud Code** 的应用程序版本确实内置了浏览器。我见过这个预览功能。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. So, so I think uh my mental model was kind of broken because I only use cowork because I thought it had a a browser thing in it, but I understand that the cloud code app or the app version of cloud code does have a built-in browser. I've seen I've seen this preview thing.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 我只是从没用过它。

<details>
<summary>Original English</summary>

**Swixs**: I just I've never used it.

</details>

**Felix**: 但最终，最终你还是会死守。

<details>
<summary>Original English</summary>

**Felix**: But in the end, in the end, you sort of die by hard.

</details>

**Swixs**: 是的。你基本上得到的是同样的东西，对吧？就像你描述的额外技能是，如果 **Claude** 能看到它正在处理的东西，它会表现得更好，对吧？这就是这里的总结。而且，无论是使用你的 **Chrome** 还是它只是创建自己的小浏览器，并没有太大区别，因为无论哪种方式，它都能看到它正在处理的东西，这只会让它变得更好，然后你就不必为你的 **Claude** 运行 **QA** 了。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. You basically get the same thing, right? like the the the additional skill that you're describing is Claude is better if it can see what it's working on, right? That's that's sort of like the summary here. And like whether it's using your Chrome or it's just like making up its own little like browser, it doesn't really make a bit difference because either way it's going to see what it's working on and that just makes it much better and then you don't have to run QA for your Claude.

</details>

**Alessio**: 为什么它不选择我现有的 **Cloud Code** 会话？因为我，我的意思是，我显然用过 **Cloud Code**，但是……

<details>
<summary>Original English</summary>

**Alessio**: Why doesn't it pick up my existing cloud code sessions? Because I I mean obviously I've used cloud code but

</details>

**Felix**: 很好的问题。嗯，除了“我们很诚实”之外，我没有一个好的答案。是的。是的。好的。这就是开放团队所做的，对吧？嗯，酷。我，我，我没有其他，我只是，我确实想拓展人们的思维，也想向那些还没真正尝试过的人展示，但我认为我有时使用这个比使用 **DIA** 更有趣，对吧？嗯，我，我使用，嗯，我用过所有其他代理浏览器，而 **Anthropic** 不必构建代理浏览器，因为你只需要……

<details>
<summary>Original English</summary>

**Felix**: excellent question. Um don't have a good answer other than like we're honest. Yeah. Yeah. Okay. This is what the open team does, right? Uh, cool. I I I don't have other like I I just I I do want to expand people's minds and also maybe show people if they haven't really done it, but like I I think it's very interesting how I sometimes use this more than I use I mean I use DIA, right? Um I and I use uh I've used like all the other agentic browsers and Enthropic didn't have to build an agentic browser because you just had

</details>

**Alessio**: **Cloud Cowork** 就足够了。

<details>
<summary>Original English</summary>

**Alessio**: cloud co-work and that's enough.

</details>

**Felix**: 是的。我还认为，也许与许多优秀的浏览器集成，目前在我的个人优先级列表中稍微高于从头开始重建一个浏览器。

<details>
<summary>Original English</summary>

**Felix**: Yeah. I also think like maybe integrating with number of excellent browsers out there is like currently on my personal priority list a little higher than like trying to rebuild a browser from scratch.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 你知道，永远不要说永远。但我认为回到这个想法，即我们希望将其整合到你现有的整个工作流程中。我认为我们的目标实际上不是取代你电脑上的任何应用程序，而是更好地与新的工作流程协同工作。

<details>
<summary>Original English</summary>

**Felix**: You know, never say never. But I think going back to this idea of like we want to plug this into your entire existing workflow. I think our goal is actually to not replace any of the applications you have on your computer, but instead like work really well with a new workflow,

</details>

**Alessio**: 创造新的。是的。

<details>
<summary>Original English</summary>

**Alessio**: make the new one. Yeah.

</details>

**Felix**: 是的。现在看来，尤其是在浏览器方面，大部分创新都集中在用户体验上，而不是底层的浏览器引擎。所以我觉得，无论是通过 **Edge** 还是 **Chrome** 还是 **Alice**，都没什么关系。

<details>
<summary>Original English</summary>

**Felix**: Yeah. It seems that nowadays especially on the browser most of the innovation is like user ergonomics. It's not really like the underlying browser engine. So I feel like to call it doesn't really matter if it's like via or Chrome or Alice whatever.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 我们想在你所在的地方与你相遇，这就像……

<details>
<summary>Original English</summary>

**Felix**: We want to we want to meet you wherever you are, which is like

</details>

**Felix**: 显然我会这么说，但这也是真的，因为我不想通过说“好吧，我将开始为那些愿意切换浏览器的人构建产品”来人为地限制我的潜在用户群。

<details>
<summary>Original English</summary>

**Felix**: like obviously I would say that but it's also just genuinely true because I don't want to restrict my potential user base artificially by saying okay like I'm going to start building for the people who are willing to switch browsers

</details>

**Alessio**: 对。

<details>
<summary>Original English</summary>

**Alessio**: right

</details>

**Felix**: 这就像，你知道，很多诉讼都是因为谁能进入浏览器，以及哪个浏览器是默认的，哪个搜索引擎在浏览器中是默认的问题而引发的，很多钱都因此易手。嗯，我只是想为 **Swixs** 这样的人构建产品。我希望为那些有很多烦人任务，并且觉得 **Claude** 可以替他们完成的人构建产品。

<details>
<summary>Original English</summary>

**Felix**: that's such a like you know like many lawsuits have been filed over who gets to the browser and like a lot of money has switched hands over the question of like which browser is default and which search engine is default within the browser. other um I just want to build for Yeah. I want to build for Swixs essentially. Like I want to want to I want to build for people who have a number of annoying tasks that they feel like maybe Claude could do it for them.

</details>

### 技能的可移植性与多代理协作

**Swixs**: 是的。你认为技能的可移植性怎么样？我认为我使用过另一个叫做 **Zo** 的东西，它有点像一个云电脑加代理，我有一个添加访客到办公室的技能。是的。所以每当有人在下班后需要进来时，他们需要在一楼签到。嗯，但我想给这个东西发短信。所以，它在 **Cowork** 中不起作用。但现在这个技能在 **Zo** 的工具中，而不在我的 **Cowork** 中，如果我做了一个更改，我就必须同步它们。你认为这会如何发展？我认为记忆就像 **Claude** 的个人记忆，我并不一定希望我的记忆是跨越不同事物的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. What do you think about skills portability? I think there's been one thing I use another thing called Zo which is kind of like a cloud computer plus agent and I have a skill to add visitors to the office. Yeah. So whenever somebody has to come in after hours they need to check in downstairs. Um, but I want to like text the thing. So, it doesn't really work in in co-work. But now that skill is in the Zo harness and it's not in my co-work thing and then if I make a change is I got to I got to sync them. How do you see that going? Like I see memory as like Claude personal kind of like I don't necessarily want my memories to be cross thing.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 但我确实希望我的技能能够跨越我使用的代理。我认为对于 **MTPs**，人们也做了同样的事情。就像：“哦，**MTP** 网关，**MTP** 注册表。”我真的不知道那是否算一门生意。所以，我很好奇你在这方面有什么想法。

<details>
<summary>Original English</summary>

**Swixs**: But I do want my skills to be cross agent that I use. I think with MTPs people did the same thing. It's like, oh, MTP gateway, MTP registry. I don't really know if that's like a business. So, I'm curious like if you've had any thoughts in the area.

</details>

**Felix**: 我认为对我来说，这又回到了我们最基本的基础组件。技能是基于文件的，而不是像某个地方存在的、超级专有的复杂东西。我真的倾向于这样的想法：所有东西都只是文件和文件夹，这本身就使其非常便携。我们确实将技能作为容器格式的一部分，我们称之为插件。

<details>
<summary>Original English</summary>

**Felix**: I think for me, this is sort of where I go back to the really basic primitives for us. Skills are file-based instead of like this complicated thing that exists inside a bliss somewhere that is like super proprietary. I'm really leaning into the idea of like it's all just files and folders and that makes it very portable in its own right. We do have skills as part of this container format which we just call plugins

</details>

**Felix**: 插件在 **Cloud Code** 和 **Cloud Cowork** 中都可用，格式相同，你可以安装插件。这在今天的代码中是可行的，你基本上可以说：“我要添加一个完整的 **GitHub** 仓库作为技能市场或插件市场。”这就是我们实现可移植性的方式。我认为我们在如何让人们更容易知道他们可以编写技能，如何让他们更容易与他人分享技能方面还有很大的成长空间，因为显然我刚才说的所有这些话，对吧？我正在失去大部分知识工作者群体。我一开始就说：“哦，你可以连接到 **GitHub** 仓库。”这并不是大多数人在一般的知识工作领域最终会工作的方式。嗯，但我认为那里有一些东西。另一个我认为尚未被充分探索的东西是，技能的哪一部分非常便携，以及技能的哪一部分对你来说非常个人化，对吧？我认为这是我们作为一个行业尚未真正解决的问题。

<details>
<summary>Original English</summary>

**Felix**: and plugins are available both for cloud code and cloud code work the same format and you can install plugins this works in code today you can basically say I'm going to add a whole like just a GitHub repo as a skills marketplace or like a plug-in marketplace and that's how we're doing pability I think we have a lot of room left to grow in how do we make it easy for people to know that they can write skills how do we make it easy for them to just like share a skill with because obviously all the words I just said, right? Like I'm losing most of the knowledge worker base out there. I start with saying, "Oh, you can connect to GitHub repo." It's not exactly how most people will end up working in like a general knowledge worker space. Um, but I think there's something there. And another thing that's there that I think has not really been properly explored is the the the combination of which part of the skill is very portable and then which part of the skill is like very personal to you, right? And I think that's something we haven't really saw here as an industry.

</details>

**Swixs**: 这就像你希望给技能引入更多结构，或者总是拥有公共技能和私人技能，你知道，成对的。

<details>
<summary>Original English</summary>

**Swixs**: It's like which you want to introduce more structure to the skill or have always have like public skill private skill, you know, pairs.

</details>

**Felix**: 是的。是的。有点像。我认为有一种最简单的方法可以做到这一点，那就是我们使用字符串插值之类的东西，对吧？

<details>
<summary>Original English</summary>

**Felix**: Yeah. Yeah. Kind of. I think there's like a like easiest way to do this would just we do like use string interpolation or something, right?

</details>

**Felix**: 在这里插入用户名。插入电话号码。插入已知的文件夹位置。这类东西。嗯，那可能很笨拙。这就是我们没有构建它的原因。嗯，但我确实认为会有人想出一种有趣的方式来保留我们喜欢技能的所有优点。可移植性只是一个文件。它只是 **Markdown**。老实说，它只是文本，对吧？就像文字的文本。完全没有结构，这意味着你不需要任何教程来编写技能。就像……

<details>
<summary>Original English</summary>

**Felix**: Insert username here. Insert like phone number. Insert like known folder locations. That kind of stuff. Um that's probably clunky. That's why we haven't built it. Um, but I do think someone is going to come up with like an interesting way to keep everything we like about skills. The portability is just a file. It's just markdown. It's just text honestly, right? Like a text for words. The complete lack of structure, which means you don't need any kind of tutorial to write a skill. Just like

</details>

**Felix**: 就像你向我解释一样向 **Claude** 解释，**Claude** 可能比我更快理解，对吧？就像预订航班一样，告诉 **Claude** 如何预订航班，就像我们今天早些时候告诉它一样，但要结合非常个性化的东西。嗯，也许我们还是以预订航班为例。我其实不认为 **AI** 应该预订航班。我认为我们拥有的工具是……

<details>
<summary>Original English</summary>

**Felix**: explain it to Claude the way you would explain it to me and Claude will probably get it before I will get it, right? just like for booking a flight, tell Claude how to book a flight the same way we're telling him somewhere I just started about today, but combine that with a very like personal thing. Um maybe we'll stick with the booking a flight example. I don't actually think AI should be booking flights. I think the tools we have is

</details>

**Swixs**: 是的，终于有人说了。这是每个人都在做的默认演示。我讨厌预订演示。这不是一个好的展示。

<details>
<summary>Original English</summary>

**Swixs**: yeah finally somebody says it it's the default demo that everyone was making. I'm like I hating against like booking demos. It was not a good showcase.

</details>

**Felix**: 是的。我就想，我只想自己预订航班。嗯，我认为很多事情都有个人和非个人的组成部分，这也许就是为什么人们会选择预订航班，因为有些事情非常普遍，对吧？

<details>
<summary>Original English</summary>

**Felix**: Yeah. I'm like I just want to book my flight myself. Um, I think there's a lot of things that have a personal and a non-personal component and that's maybe why people reach for flight booking because some things are very universal,

</details>

**Felix**: 更便宜的航班通常更好，对吧？很少有人会尝试预订最贵的航班。然后有些事情是相当个人化的，比如你喜欢什么时间，你喜欢什么座位，你喜欢哪个机场。将这些结合在一个实际上可移植、兼容、易于人们理解的技能格式中，我认为那会非常令人兴奋。我们只是还没有弄清楚。是的，我认为文本部分，我认为现在每个人都有某种云文件存储，无论是 **Dropbox**、**Google Drive** 还是其他什么。

<details>
<summary>Original English</summary>

**Felix**: cheaper flight is usually better, right? Like few people try to book the most expensive flight and then some things are quite personal about like what times you prefer, which seat you prefer, which airports you prefer. Combining that in like a skill format that is actually portable, compatible, easy to understand for people, I think that would be very exciting. We just haven't figured it out yet. Yeah, I think the text part ever I think everybody by now has some sort of like cloud file thing either Dropbox, Google Drive, whatever.

</details>

**Swixs**: 所以感觉上，它应该基本上像 **simlink** 我的技能到我所有的代理工具中，只是保持它们同步。就像我们内部有一个“有价值的token仓库”，里面有所有的命令和子代理。好的。嗯，然后我构建了一个 **TUI**，你可以在其中启动并说：“你知道，将这个命令和这三个子代理安装到这个文件夹中的这个代理中，然后复制粘贴这个。”它什么也没做。字面上就是将文件复制到那里。但我感觉应该有类似的东西，比如每当我进入一个新的东西时，它就会说：“嘿，这是到云文件夹的链接，把这些技能下载到这里。”现在，它还不能完全这样工作。比如，如果我安装一个新的代理，我不能……我必须复制粘贴所有的技能，我甚至不知道它们在哪里。这是个大问题。就像，我在哪里找到它们？

<details>
<summary>Original English</summary>

**Swixs**: So it feels like in a way it should basically like sim link my skills into all my agent harnesses just keep those in sync like we have internally this like valuable tokens repo which is like all the commands and sub agents. Good. Uh, and then I built like a TUI where you can start and be like, you know, install this command and the three sub agents into this agent in this folder and just copy paste this. It doesn't do anything. Literally like CP the file into that. But I feel like there should be something similar where like whenever I go into a new thing, it's like, hey, here's like the link to exactly the cloud folder and just bring down these skills into this. Like today, it doesn't quite work like that. Like if I install a new agent, I cannot I have to like copy paste all the skills and I don't even know where they are. That's like the big problem. It's like where do I find them?

</details>

**Swixs**: 嗯，所以我很好奇，未来，这几乎感觉我的个人生产力就是我的技能。

<details>
<summary>Original English</summary>

**Swixs**: Um so I'm curious like in the future like that that almost feels like my personal productivity thing will be my skills.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 它不是我使用的产品，因为每个人都可以访问相同的产品。

<details>
<summary>Original English</summary>

**Swixs**: It's not really the product that I use because everybody has access to the same product.

</details>

**Felix**: 但今天，那看起来就像复制粘贴 **MBA** 文件。

<details>
<summary>Original English</summary>

**Felix**: But today there that just looks like copy pasting MBA files.

</details>

**Felix**: 我认为有很多事情。我真的很喜欢把代理和 **LLM** 看作是另一个同事。很多尝试都致力于构建文档公司，它们会说：“哦，我们将解决你所有的文档问题。”嗯，我自己花了一些时间在 **Notion** 上工作，对吧？我非常熟悉“让我们让每个人都在同一页面上”的概念，对吧？

<details>
<summary>Original English</summary>

**Felix**: I think so many things. I I really like thinking about agents and LLM just as like another coworker. So many attempts have made to build documentation companies that are like, "Oh, we're going to solve all your documentation problems." Um, I myself like spend a little bit of time working in Notion, right? I'm like deeply familiar with the concept of let's get everyone on the same page, right?

</details>

**Felix**: 你在这里基本上是说，你希望你所有的代理都能在你的偏好、技能以及它们应该如何工作和执行方面达成一致。我不知道正确的做法会是什么。如果它是一家公司，可以说：“好的，我们作为一个独立的机构。我们不试图推销任何特定产品。我们的工作是成为技能的权威，我们提供……我不知道，我们将成为技能的 **Dropbox**，我们可以将我们 **simlink** 到他们想使用的所有产品中。”我不确定这是否会是一个可行的业务，但作为一个想法，那会很酷，对吧？

<details>
<summary>Original English</summary>

**Felix**: And what you're basically saying here is you want all your agents to be on the same page about your preferences, about the skills, about the way they ought to work and like how they ought to execute. And I'm not sure what the right thing is going to be. If it's going to be some some company that can say, "All right, we're as an independent body. We're not trying to like push into any particular product. It's our job to be like the skill authority and we provide I don't know, we're going to be the Dropbox of skills and we can just sim link us into all the products they want to use. I'm not sure that's going to be viable business, but as as an idea, it would be cool, right?"

</details>

**Swixs**: 是的。是的。我认为很多东西都将作为业务消失。就像我该怎么做？我甚至没有要求别人为此开发产品。是的，我想亲自知道，而且有些事情就像你说的，你几乎想要一个技能，然后将其在个人和工作之间进行插值。所以如果我为工作预订航班，那与我个人预订航班是不同的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Yeah. I think so many things are just going away as businesses. It's like how am I supposed to do it? I'm not even asking somebody to make a product about it like yeah I want to personally know and there's things like you said it's like you almost want a skill and then interpolate it between personal and work. So if I'm booking a flight for work is different than I'm booking of flight personally.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 在某些方面是这样，但很多脚手架是相同的，你知道。

<details>
<summary>Original English</summary>

**Swixs**: In some ways but like a lot of the scaffolding is the same you know

</details>

**Felix**: 我的意思是，作为一名工程师，我会告诉你，你知道，从技术人员的角度来说，我只会说“兄弟姐妹”。

<details>
<summary>Original English</summary>

**Felix**: I mean as an engineer I will tell you like you know technical person to technical person I will just be like siblings.

</details>

**Swixs**: 嗯，这就是我用 **cloud.MD** 和 **agents.mmd** 所做的。它们只是同样的 **simlink**，所以它能工作，但感觉就像，是的，我不知道，也许……

<details>
<summary>Original English</summary>

**Swixs**: Well that's what that's what I do with cloud.MD and agents.mmd. It's just the same as fellow sim length and so it's like that works but it feels like yeah I don't know maybe

</details>

**Felix**: 我们总是可以更进一步，你总是可以告诉 **Cowork** 一个问题，然后 **Cowork** 会为你解决它，它会创建 **simlink**，这是一种方法。

<details>
<summary>Original English</summary>

**Felix**: we could always go one level up you can always tell co-work a problem and then co-work will solve it for you does make the simlings that's like one way to do it

</details>

**Swixs**: 没错，没错，好吧，所有东西都叫 **Cowork**。

<details>
<summary>Original English</summary>

**Swixs**: that's true that's true all right everything is called coowork

</details>

### AI对劳动力市场的影响

**Alessio**: 嗯，一个可能有点敏感的问题，对你们两位来说，这些行业中哪些会消失？

<details>
<summary>Original English</summary>

**Alessio**: uh potentially spicy question for both of you uh which of these industries will go away

</details>

**Felix**: 好的，所以 **Felix** 之前说的很有趣，基本上有短期压力，比如我们需要把这些token变成有价值的东西，那就是我应该构建最后一个产品来利用模型。然后是长期问题，哪些会仍然有价值？我认为你今天在编码领域已经看到了这一点，从某种意义上说，每个人都在堆栈中不断向上移动，因为你需要的不仅仅是将token转化为代码。

<details>
<summary>Original English</summary>

**Felix**: okay so what Felix was saying before is interesting there's basically like the short-term pressure of like we need to turn these tokens into valuable things which is I should build the last mile product that harness the model and then there's the question of like long-term which ones are going to still be valuable and I think you're kind of seeing this today with like uh you know the coding space in a way it's kind of like everybody's moving up and up in stack because you need more than just turning tokens into code

</details>

**Felix**: 我认为像企业搜索这样的搜索领域也看到了同样的情况，比如 **Glean** 和所有这些不同的公司，就像归根结底，如果 **Cowork** 正在做所有的工作，那么搜索本身只是很小的一部分，以至于我不知道我是否真的会花那么多钱只做搜索。这几乎就像所有东西都是 **Cowork** 的垂直领域。所以 **Cowork** 能支持多少第一方功能？

<details>
<summary>Original English</summary>

**Felix**: I think search like enterprise search is kind of seeing the same thing like with glean and like all these different companies is like at the end of the day if co-work is the on doing all the work. The search itself is like such a small part that like I don't know if I'm really going to pay that much money just to do search. It's almost like everything is like a co-work vertical. So like how much can co-work first party support?

</details>

**Alessio**: 嗯。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Felix**: 以及它不能支持多少？我认为对于很多这些事情，你展示的规划功能，规划，规划。

<details>
<summary>Original English</summary>

**Felix**: And how much can it not? I think for a lot of these things the planning thing that you were showing did the the planning the planning.

</details>

**Alessio**: 好的。是的。是的。就像，那是其中一件事，这些代理提供的大部分价值是它们更擅长为特定任务进行规划，并且拥有更好的工具。

<details>
<summary>Original English</summary>

**Alessio**: Okay. Yeah. Yeah. Like that's one thing where like most of the value that these agents provide is like they're better at planning for specific tasks and have better tools for it.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Alessio**: 但我认为模型现在正朝着这个方向发展，它们拥有正确的工具，并且它们在你的电脑上。所以对我来说，这几乎就像如果最终客户信任你的初创公司是该任务结果的提供者，那么我认为这会奏效。这是，嗯，我们正在努力解决的一个短期高峰。嗯，是的。

<details>
<summary>Original English</summary>

**Alessio**: But I think the models are now moving in that direction and they have the right harnesses and they're on your computer. So for me it's almost like if the end customer trusts your startup to be the provider of that task result then I think that works. This is uh something that this is a short spike that we're we're working on. Uh yeah,

</details>

**Felix**: 我认为，听着，我会告诉你，我不认为我是最适合实际估计哪个行业会受到最大冲击的人，但我确实认为，在 **Anthropic**，我们作为一个群体，深切关注这些工具将对劳动力市场产生的影响，特别是对于初级员工，因为我认为，我们谈论自动化很多工作时，我们个人觉得很烦人，我们可能认为这不是我们时间的最佳利用。在很多行业中，这类工作本来会交给初级入门级员工，对吧？我认为我们对此感到担忧是完全正确的，并且担心这会对那些进入就业市场的人产生什么影响。

<details>
<summary>Original English</summary>

**Felix**: I think look, I I'll I'll tell you this like I don't think I'm the best person to like actually estimate which industry is going to be hit the hardest, but I do think that at Anthropic as a group of people, we're deeply worried about the impact that the tools are going to have on the labor market, especially for like junior employees that because I think I think it's only honest to say that when we talk about automating a lot away a lot of the work that we personally find annoying that we maybe think it's not the best use of our time. In a lot of industries, that kind of work would have been given to a junior entry- level employee, right? And I think it's it's only it's only right to be really worried about that and like worry what that's going to do in particular to people who like enter the job market.

</details>

**Swixs**: 我有一个解决方案，那就是为他们创造模拟工作。

<details>
<summary>Original English</summary>

**Swixs**: I have a solution for that which you make them you create simulative jobs for them.

</details>

**Felix**: 好的。

<details>
<summary>Original English</summary>

**Felix**: Okay.

</details>

**Swixs**: 所以这有点半开玩笑半认真。如果你考虑软件工程，当你是一个初级工程师时，你工作一、两年、三年。在这三年里，可能只有少数几个时刻你真正学到了东西，然后很多其他日子你并没有真正进步。

<details>
<summary>Original English</summary>

**Swixs**: So this is this is like half joke half true. So if you think about software engineering, when you're like a junior engineer, you work like one, two, three years. And in those three years, there's like maybe like a handful of moments where like you really learn something and then a bunch of other days where like you're not really progressing.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 我认为现在我们可以使用 **AI** 和这些模型来实际缩短这些职业生涯，几乎可以模拟你工作的前几年，并让它们变得……

<details>
<summary>Original English</summary>

**Swixs**: I think now we can use AI and these models to actually like shortcut these careers and almost like simulate the early years of your work and like just make them like

</details>

**Swixs**: 在这些学习中变得超级密集。就像：“嘿，我们正在开发这个功能，它是一个分布式系统，你需要学习这个东西，这在公司可能需要三个月，所以你在这里花三个月。”就像我们只是在模拟整个事情。它实际上不是真实的事情，我们在一周内就快速完成了整个事情，你从中吸取了教训，然后我们在一年的时间里重复这个过程，你基本上获得了三年价值的项目和经验。

<details>
<summary>Original English</summary>

**Swixs**: super dense in like these learnings. is like, hey, we're working on this feature which is like a distributed system and you need to learn this thing that might take three months at a company and so you take three months here. It's like we're just simulating the whole thing. It's actually not a real thing and in one week we kind of speedrun through the whole thing and you kind of learn your lesson from there and we kind of repeat that in like one year you basically get like three years worth of like projects and experience.

</details>

**Felix**: 是的。我认为对于销售或营销之类的事情来说，这更难，因为你没有办法获得反馈循环。但我认为很多事情，听起来有点傻。就像你在制造一个新的“假工作”，但这几乎就像你去上大学，对吧？人们花钱学习如何做。这可能感觉类似，就像：“嘿，我们有 **Jane Street** 模拟器。”就像：“你想来 **Jane Street** 工作吗？我们把你放在模拟器里三个月。”

<details>
<summary>Original English</summary>

**Felix**: Yeah. I think it's harder for like things like sales or for things like, you know, marketing because you don't really have a way to get the feedback loop. But I think a lot of it, it sounds kind of silly. It's like you're making the new a fake job, but it's almost like you go to college, right? People pay to learn how to do it. And this might feel similar where it's like, hey, we have the Jane Street simulator. It's like, you want to come work at Jane Street? We'll just put you in the simulator for like three months

</details>

**Felix**: 然后你就会出来，就像：“你知道，我准备好了。”所以这里有一个方面。我不是专家，无法真正知道营销、法律或金融会发生什么，对吧？我不在那些行业工作，我认为我不应该谈论它们。但我是一名工程师，我认为我对工程是什么样子有一个很好的了解。我认为我们正在看到的一件事是，作为一家公司，也作为公众，我们对入门级职位深感担忧，但我们也看到更多高级工程师加速发展。我们觉得他们更高效。他们实际上增加了他们提供的价值。我一直在思考的一件事是，即使在这一切发生之前，我一直非常尊重 **滑铁卢大学**，那些从 **滑铁卢大学** 加入我团队的新毕业生总是感觉比那些在大学里度过全部时间的新毕业生更准备充分，无论他们有多优秀，但他们从未真正在一个必须交付最终会被用户使用的产品的环境中工作过。我是德国人。我最初上的是德国大学。我认为那里的信息系统项目往往非常理论化，对吧？我经常给人们举的例子是，就像想成为一名医生，但你首先必须学习四年生物学。结果是，当你得到一个新毕业生时，你必须教他们如何实际构建产品，如何在公司工作，以及如何与其他人合作。有些人会有不同的意见，以及你如何做所有这些事情？而 **滑铁卢大学**，他们似乎只花了一半时间。我不知道是不是真的，但我认为是一年，对吧？

<details>
<summary>Original English</summary>

**Felix**: and you'll come out of it. It's like, you know, I'm ready. So there there is an aspect here. I'm not an expert enough to like actually know what what is going to happen to marketing or legal or finance, right? Like I don't work in those jobs and I I don't think I should talk about them. But I am an engineer and I think I have a pretty good idea of what engineering is like. And I think one thing we're sort of seeing is that as a company and also as as the public, we're like deeply worried about entry level, but we're also seeing more senior engineers accelerate it. We feel like they're more productive. They they actually increase the value they provide. And a thing that I'm thinking about a lot is the fact that even before all of this happened um I've always had a lot of respect for the University of Wateroo and the the new grads that have joined my teams as from coming from University of Wateroo always felt like more ready than new grads who like literally spent their entire time at the university regardless of how good but never actually had to work inside an environment where you have to ship things that eventually will be used by users. And I'm I'm I'm German. I like initially went to German university. And I think the the the like information systems programs there tend to be very theoretical, right? Like I often give people the example of like trying to become a doctor, but you first have to do four years of biology. And as a result, when you get a new grad, you sort of have to teach them what it's like to actually build products and to work in a company and like work with other people. And like some people will have different opinion and like how do you do all of those things? And the University of Wateroo, it seems like they just spend half of their time. I don't know if it's true, but I think it's a year, right?

</details>

**Felix**: 他们花了很多时间，作为你课程的一部分，去实习一年。

<details>
<summary>Original English</summary>

**Felix**: They spend so much time part of your job curriculum to do spend a year in internships.

</details>

**Swixs**: 是的。他们只是从一家公司跳到另一家公司。他们出现在你的团队中，就像一个去过20家公司的初级工程师。不完全是，但我的很多新毕业生似乎也曾在 **Apple**、**Google**、**Tesla** 短暂工作过。是的。而且有一个常见的梗，他们收集所有这些Logo，就像无限宝石一样，但他们总是把它们放在 **LinkedIn** 上，而且他们是实习生这一点非常不清楚。是的。是的。没错。但这确实让他们比其他新毕业生好得多。我想知道这是否是一个有用的模型，也许对于未来，当我们也必须缩短作为初级员工的时间，因为作为初级员工的价值将受到影响。我支持年轻人的观点是，他们有更高的神经可塑性。他们可以学到更多。他们有更少的先入为主的偏见。我假设 **OpenAI** 经常说的是，实际上是那些更年轻的、刚毕业的工程师，他们使用 **Codecs** 或他们的编码工具更具创新性，而不是那些有固定和偏好工作方式的经验丰富的工程师。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. They just like go from company to company. They show up on your team is like a junior engineer who's been to like 20 companies. Not really, but like it seems like a lot of my new grads have also briefly worked at Apple, Google, Tesla. Yes. And uh there's a common meme where they like collect all these logos like infinity stones but and they always put it on LinkedIn and it's very unclear that they were an intern like Yeah. Yeah. Exactly. But it does actually make them so much better compared to other new grads. And I wonder if that's a useful model maybe for the future when we also have to like crunch down the amount of time you have as a junior employee because the value you have as a junior employee is going to like be impacted. My sort of pro- young people take is that there you're more uh you have higher neuroplasticity. You can learn more. You have less pre-existing biases. And what I is assume it's true for you what OpenAI often says is that actually it's the the younger like fresh grad engineers that use codecs or their coding stuff uh more innovatively than the uh experienced engineers who have a set and preferred way of doing things.

</details>

**Felix**: 是的。当我与人交谈时，我也有类似的经历。

<details>
<summary>Original English</summary>

**Felix**: Yeah. As I talk to people, I I had similar experience.

</details>

**Swixs**: 是的。所以也许你更具 **AI** 原生性，因此你，你，你被淘汰了。但我想问题是，你不需要那么多这样的人。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. So maybe you're more AI native and therefore you're you you get cut. But like I think the problem is you don't need that many of them.

</details>

**Felix**: 我的意思是，**Anthropic** 曾公开表示，我们确实认为对市场的影响将是巨大的，我们不认为人们总体上已经做好了准备，对吧？我们确实认为我们可能应该作为一个社会更多地讨论这个问题。是的。

<details>
<summary>Original English</summary>

**Felix**: I mean Anthropic is on the record of saying we do believe that the impact on the market is going to be sizable and we do not think that people overall are ready right and we do actually think we should probably talk about it as a society much more. Yeah,

</details>

**Felix**: 我不确定我是否是那个能在这方面提供任何有用信息的人，但我认为作为社会，与经济学家和政府一起，需要以一种可能比我纠结更有意义的方式来解决这些问题，我们可能做得还不够。

<details>
<summary>Original English</summary>

**Felix**: I'm not sure that I'm like the individual that can add like anything useful there, but I think as societies with economists and governments that need to wrestle those questions in a way that is probably more meaningful than me wrestling with them, we're probably not doing it enough.

</details>

**Swixs**: 是的。嗯，我们会努力教育。然后我认为，就像你们一样频繁发布，或者可能过于频繁发布……

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Well, we'll try to educate. And then I I think also just releasing frequently as as as you guys do or probably maybe too frequently

</details>

**Felix**: 嗯，这有助于人们随着时间的推移进行调整，对吧？与其一次性大爆炸，不如让人们经历这种渐进式的起飞，唤醒人们，对吧？

<details>
<summary>Original English</summary>

**Felix**: uh is helping people to adjust over time, right? But rather than one big bang thing, there's like sort of this gradual takeoff that people are living through that waking people up, right?

</details>

**Swixs**: 是的。而且我，但我认为我们很多人都在想，我们到底什么时候才能完全起飞，对吧？就像什么时候我们会经历这种大爆炸时刻，事情会加速得如此之快，以至于形成一个自我强化的循环。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. And I but I think a lot of us like wondering at what point do we actually have full takeoff, right? Like at what point is there we're all sort of expecting this like big bang moment where things will acceler accelerate so quickly that it becomes a self-reinforcing loop.

</details>

**Felix**: 嗯。

<details>
<summary>Original English</summary>

**Felix**: Mhm.

</details>

**Swixs**: 到那时，就像比赛开始了，不再有缓慢的追赶。你不仅仅拥有如此擅长一切的 **Claude**。

<details>
<summary>Original English</summary>

**Swixs**: And at that point it's sort of like off to the races and there will be no more like slowly catching up. You not just have Claude being so good at everything.

</details>

**Felix**: 是的。那就是 **Cowork** 训练模型的时候。那就是它查看 **TensorBoard** 和权重以及偏差值的时候。

<details>
<summary>Original English</summary>

**Felix**: Yeah. It's when co-work is training models. It's when it's looking at tensorboard and weights and bias values and

</details>

**Swixs**: 训练东西。

<details>
<summary>Original English</summary>

**Swixs**: training things.

</details>

**Felix**: 而且我们可以争论这还需要多少年，对吧？有些人会打赌说也许还需要10年，也许还需要一年。嗯，我不太确定我在这条线上站在哪里，但我不太确定它最终是否真的那么重要，无论它是在四年还是五年内发生。如果我们有相当大的确定性它会发生，那我们可能就应该去解决它。

<details>
<summary>Original English</summary>

**Felix**: And like we can all debate like how many years it's away, right? Like some people make a bet around like maybe it's 10 years away, maybe it's a year away. Um I'm not entirely sure where where I come on this line, but I'm not entirely sure that ultimately it matters all that much whether or not it happens in four or five years. If we have a decent amount of certainty that's going to happen, it's probably something we should wrestle with.

</details>

### 桌面整理与财务分析

**Swixs**: 我想谈谈。所以，顺便说一下，计划任务完成了，嗯，清理我桌面的任务完成了，它按文件类型整理了，这还行，但你知道，我当时想让它做更多主题性的整理，比如阅读文件，理解它的内容，按主题分组，而不是按文件类型，但是……

<details>
<summary>Original English</summary>

**Swixs**: I wanted to talk. So, by the way, the the scheduled task complete uh the the clean my desktop task complete and it did it organized by file type which okay, but you know, I was trying to get it to do more sort of thematic like read the file, understand what it's about, group by uh the the topic rather than the file type, but

</details>

**Felix**: 我的意思是你可以继续跟进，让它去做。

<details>
<summary>Original English</summary>

**Felix**: I mean you can just follow up and have it do that.

</details>

**Swixs**: 哦，就像它正在提议，对吧？

<details>
<summary>Original English</summary>

**Swixs**: Oh, like it it is proposing, right?

</details>

**Felix**: 是的。所以它有一些主题性的东西，但是，嗯，是的，我可能可以做得更好。是的。所以，我可能需要给它一个技能来读取视频文件，这样它就能理解我喜欢如何……

<details>
<summary>Original English</summary>

**Felix**: Yeah. So, it's got some like topical things, but uh yeah, I could probably do better like Yeah. So, like I probably need to give it a skill to read video files so that it understands here's how I like to

</details>

**Felix**: 老实说，嗯，我看到你正在使用 **Open 4.6**，对吧？我的建议是，人们越来越不需要担心它了。只要告诉它你想让它做什么，它很可能会想办法做到。

<details>
<summary>Original English</summary>

**Felix**: honestly though like um I see that you're using open 4.6, right? Like my recommendation for people is increasingly don't worry about it anymore. Just like tell it what you wanted to do and it's probably going to figure out a way to do it.

</details>

**Swixs**: 好的。

<details>
<summary>Original English</summary>

**Swixs**: Okay.

</details>

**Felix**: 它可能不是你喜欢的方式，或者你过去做的方式。

<details>
<summary>Original English</summary>

**Felix**: It might not be the way that you like necessarily or the way that you've gone about it.

</details>

**Swixs**: 视频更深入，但我们正在外包所有这些的整理工作。所以，让我们战斗吧。

<details>
<summary>Original English</summary>

**Swixs**: Videos deeper, but we're outsourcing organizing all of it. So, let's fight.

</details>

**Felix**: 是的。是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah. Yeah.

</details>

**Felix**: 我老实说很好奇 **Claude** 会想出什么。

<details>
<summary>Original English</summary>

**Felix**: I'm honestly like so curious what Claude is going to come up with.

</details>

**Swixs**: 我会启动它。我还想谈谈整体的，你知道，你谈到了数据分析，你谈到了，嗯，你的个人财务。你还说，嗯，顺便说一下，对我们来说，现在正是报税季，对吧？就像使用 **Cloud Cowork** 来报税。它不对任何错误负责，但反正也无妨，对吧？就像，这对你来说是免费的知识工作。所以我就觉得，我认为 **Claude** 在金融领域很重要。嗯，这绝对是其中的一部分。我好奇，它是否是一个独立的团队？你和他们交流吗？它有多重要？对吧？因为你现在也可以原生输出 **Excel** 文件。

<details>
<summary>Original English</summary>

**Swixs**: I'll kick that off. I wanted to also just talk about the the overall uh you know you talk about data analysis, you talk about like uh your your personal finances. You also said uh which by the way for us is very timely tax season right like use cloud core for tax season. It is not responsible for any mistakes but might as well right like it's it's free knowledge work for you. So I just like I think cloud for finance is a big deal. Um and this is definitely like in that mix. I wonder is it like do you is it a separate team? you talk to them. How important is it? Right? Like because you can also natively output Excel files now.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 只是谈谈财务方面的工作。

<details>
<summary>Original English</summary>

**Swixs**: Just talk about the finance effort.

</details>

**Felix**: 我们非常重视垂直领域。所以我们确实有一个专门的垂直团队。我们还有一个专门的企业团队。而且这是工程，不是销售。

<details>
<summary>Original English</summary>

**Felix**: We care about the verticals quite a bit. So we do have a dedicated vertical team. We also have a dedicated enterprise team. And there was this engineering not sales.

</details>

**Felix**: 是工程。是的。是的。是工程。所以我们确实有人每天都来工作，他们会问自己：“我们如何让 **Cowork** 对这些特定行业的人极其有效？我们如何让他们更容易理解？我们如何让他们更容易接入并从中获得与软件工程师相同的价值？”我认为软件工程师最终站在整个 **AI** 运动的最前沿并不奇怪，因为其中很大一部分就像一个 **鲁布·戈德堡** 机器，我们已经习惯了自动化事物，对吧？这是我们工作的一部分。

<details>
<summary>Original English</summary>

**Felix**: It's engineering. Yeah. Yeah. It's engineering. So we do have people who sort of come to work every single day and they they ask themselves how do we make co-work extremely effective for people in those specific industries? How do we make it easier for them to understand? How do we make it easier for them to plug into this and like sort of get the same value out of it that software engineers get? I think it's no real surprise that software engineers ended up being sort of at the forefront of the entire AI moment because so much of it is this like Rube Goldberg machine where like we're already used to automating things, right? Like it's part of our job.

</details>

**Felix**: 是的。所以我们非常重视它。我认为它也确实符合我们认为 **Claude** 作为模型非常擅长的领域。我认为它为这些客户提供了巨大的价值，特别是由于他们拥有的数据量，我们可以做很多事情。这些是数据密集型行业。这些是正确性非常重要的行业。

<details>
<summary>Original English</summary>

**Felix**: Yeah. So we care about it quite a bit. I think it also like really matches what we see Claude being very good in as a model. I think it provides tremendous amount of value to those customers in particular because we can do so much with the amount of data they have. Those are like data heavy industries. They're industries where correctness matters quite a bit.

</details>

**Swixs**: 所以我用它来分析我的业务。我只是不能展示它。

<details>
<summary>Original English</summary>

**Swixs**: So for I've used it to analyze my business. I just can't show it.

</details>

**Felix**: 这是两分钱。我也有一个关于税收的类似问题。我确实发了推文，我确实发了推文，说“哦，**Cowork** 正在帮我报税。这真是太不可思议了。”嗯，这有点烦人，因为这太酷了，但我不会……

<details>
<summary>Original English</summary>

**Felix**: That's two sense. I had a similar question about taxes. Like I did tweet I did tweet about the fact I did tweet about oh co is doing my taxes. This is honestly incredible. And um it's like annoying because like this is so cool but I'm not going to

</details>

**Felix**: **Twitter** 可能不是需要看到我报税表的受众。

<details>
<summary>Original English</summary>

**Felix**: Twitter is maybe not the audience that needs to like see my tax return.

</details>

**Swixs**: 是的，但它在这里。它正在读取所有视频。所以，就像，是的，它正在获取更多。

<details>
<summary>Original English</summary>

**Swixs**: Yeah, but here here it is. It's reading all the videos. So, it's like Yeah, it's getting more.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Alessio**: 它实际上是怎么做到的？我很好奇。

<details>
<summary>Original English</summary>

**Alessio**: How did it actually do it? I'm actually curious.

</details>

**Felix**: 哦，它通常只是截屏，然后通过视觉读取截屏。

<details>
<summary>Original English</summary>

**Felix**: Oh, usually it just like takes a screenshot and then it reads the screenshot by Vision.

</details>

**Swixs**: 所以，这就是我为我的 **Zoom** 上传所做的事情，对吧？因为我有一些 **Paper Club** 会议需要上传到 **Zoom**，我想让它自动命名并做会议记录等等。所以，它只是截屏并尽力而为。是的，它不会从转录中受益，它现在纯粹通过视觉操作，但这已经足够好了。

<details>
<summary>Original English</summary>

**Swixs**: So, this is what I do for my my Zoom upload thing, right? Because I I have paper club sessions that I need to upload to Zoom and I wanted to automatically uh title them and do show notes and everything. So, just take screenshots and try to try its best. Yeah, it wouldn't benefit from transcribing which it's doing by it's operating by pure vision now, but it's good enough.

</details>

**Swixs**: 然后我确实需要请 **Nano Banana** 来处理图像。所以除非你们帮我处理图像，否则我必须请其他人处理图像。

<details>
<summary>Original English</summary>

**Swixs**: And then I do have to call out to Nano Banana to do images. So unless you guys do images for me, uh I have to call other people images.

</details>

**Felix**: 我们知道，我们知道，这对我来说太有趣了，因为这正是我越来越想做的事情，越来越好奇 **Claude** 的创造力，以及如何找出它对某些问题的处理方法。

<details>
<summary>Original English</summary>

**Felix**: We're aware we're it's just like so fun for me because like this is the thing that I'm increasingly doing like increasingly curious about Claude's creativity and like figuring out what

</details>

**Swixs**: 它很棒。

<details>
<summary>Original English</summary>

**Swixs**: it's great.

</details>

**Felix**: **Claude** 的方法就像某个问题。

<details>
<summary>Original English</summary>

**Felix**: Claude's approach is like certain problem.

</details>

**Swixs**: 是的。视觉处理一切是超能力，对吧？你知道，计算机使用，你们是第一个做计算机使用的，对吧？当它推出时，我印象非常不深。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Vision for everything is is like the the superpower, right? like you know and computer use you guys were the first to do computer use right and when it was launched I was very unimpressed

</details>

**Swixs**: 我当时觉得它很慢，不可靠。

<details>
<summary>Original English</summary>

**Swixs**: I was like it's slow it's unreliable

</details>

**Felix**: 真是太神奇了，它现在好多了。

<details>
<summary>Original English</summary>

**Felix**: it's wild how much better

</details>

**Swixs**: 那是一年前。

<details>
<summary>Original English</summary>

**Swixs**: it was one year ago

</details>

**Felix**: 是的，我知道，它几乎无法使用。是的，我记得它几乎无法使用，但一年之内事情变得这么好，是不是很神奇？

<details>
<summary>Original English</summary>

**Felix**: yeah I know like it was barely usable yeah I I remember it was barely usable but isn't it wild how much better things have gotten over like one year

</details>

**Alessio**: 我们去了 **Anthropic** 办公室，因为，嗯，计算机使用的发布活动，就像有一个黑客马拉松，没有人参与计算机使用的黑客。

<details>
<summary>Original English</summary>

**Alessio**: we went to the anthropic office because uh for the launch event for computer use like there was like this hackathon and like nobody hacked on computer use

</details>

**Felix**: 但我，你看，我，我，我不知道你是否介意我这么说，但我确实短暂地看到你安装了一个 **Mac OS** 自动化 **MCP** 服务器，对吧？你用过那个吗？

<details>
<summary>Original English</summary>

**Felix**: but I See, I I I don't know if you're okay with me saying that, but I did see briefly that you do have like a like an automate Mac OS MCP server installed, right? Do you use that ever?

</details>

**Swixs**: 什么？抱歉，哪个？在哪里？

<details>
<summary>Original English</summary>

**Swixs**: What? Sorry, which one? Where?

</details>

**Felix**: 嗯，如果你去你的设置。

<details>
<summary>Original English</summary>

**Felix**: Um, if you go to your settings

</details>

**Swixs**: 哦，设置。好的。嗯，在哪里？抱歉，这个。

<details>
<summary>Original English</summary>

**Swixs**: Oh, settings. Okay. Uh, where? Sorry, this one.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 嗯，我注意到在你的连接器中。

<details>
<summary>Original English</summary>

**Felix**: Um, I noticed that in your connectors.

</details>

**Swixs**: 嗯哼。嗯，我可能设置过一次，但我没有积极使用它。

<details>
<summary>Original English</summary>

**Swixs**: Uhhuh. Uh, I probably set it up one time, but I don't use it actively.

</details>

**Felix**: 好的。**Mac** 自动化器。是的。是的。所以，所以，是的，这个我真的想自动化我所有的事情。我没有发现，我没有发现它超级可靠。

<details>
<summary>Original English</summary>

**Felix**: Okay. The a Mac automator. Yeah. Yeah. So, so I Yeah, this one I really wanted to just automate everything in my thing. I didn't find I didn't find it super reliable.

</details>

**Swixs**: 好的。

<details>
<summary>Original English</summary>

**Swixs**: Okay.

</details>

**Swixs**: 是的。为什么？

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Why?

</details>

**Felix**: 不，不，不，完全没有问题。

<details>
<summary>Original English</summary>

**Felix**: No, no, no question at all.

</details>

**Felix**: **Claude** 在编写 **AppleScript** 和执行自己的 **AppleScript** 方面比依赖这些第三方工具要好得多。

<details>
<summary>Original English</summary>

**Felix**: Claude is much better at writing Apple script and executing its own Apple script than relying on these uh third party tools.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 嗯，所以我最初安装了 **IMCP** 和所有这些其他人构建的 **FCPs**，但现在我不再使用它们了。就像，就让 **Claude** 自己编写东西吧。

<details>
<summary>Original English</summary>

**Felix**: Uh so I've increas I initially installed IMCP and like all these other FCPS that people built and but now I don't use any of them anymore. Like just just let Claude write its own thing.

</details>

**Swixs**: 它会更定制化。我们不断向上层堆栈发展，但使用计算机对我来说是一个相当有趣的领域。而且它也很有趣，因为我认为我们离 **Claude** 能够非常有效地使用你的电脑，而不仅仅是理论上的电脑，已经不远了。

<details>
<summary>Original English</summary>

**Swixs**: It's going to be more custom made. we keep going up the stack, but using computer use is like a fairly interesting area to me. And it's like also interesting in the sense that I don't think we're far away from I don't think we're far away from Claude being very effective at like using your computer and not just a theoretical computer.

</details>

### 用户与电脑的关系

**Alessio**: 嗯哼。用户和电脑之间的关系是什么？就像，有一些推文说 **Cloud Cowork** 创建的一些 **VM** 有多大，比如12-15GB，人们抱怨，但在某个时候，如果你正在使用的电脑正在执行操作，这不就是你的电脑吗？我只是看着它，你知道吗？就像我，我认为这就是为什么人们喜欢 **Mac Mini** 和上面的 **Open Claude** 之类的想法，因为就像它有了自己的家，你知道，它在做它的事情，我在做我的事情。我认为这里有一种不是像竞态条件，而是像：“好吧，如果我现在启动这个任务，我就不能真正使用电脑了。”

<details>
<summary>Original English</summary>

**Alessio**: Mhm. What's the relationship between the user and the computer? like it there were some tweets about how huge some of the VMs that cloud cowwork creates are like 12 15 gigabytes and people complain but at some point it's like if you're using the computer you're taking action on is this just your computer and I'm just looking at it you know it's like I I think that's why people like the idea of like the Mac Mini and the open Claude or whatever on it because it's like it got its own home you know it's doing its thing I'm doing my thing I think there's some kind of like not like race condition but it's like okay if I kickstart this task ask now I can't really use the computer

</details>

**Alessio**: 你知道，因为 **Cowork** 正在上面做事情。

<details>
<summary>Original English</summary>

**Alessio**: you know because co cowork is doing things on it

</details>

**Felix**: 这有点尴尬，就像，是的，我不确定。

<details>
<summary>Original English</summary>

**Felix**: and it's kind of awkward like yeah I'm not sure

</details>

**Felix**: 我确实认为这是一个非常有趣的领域，因为我或许可以告诉你我曾思考过的一些我认为实际上是坏主意的事情。所以当我们最初开始开发 **Cowork** 时，我确实有一些梦想，关于 **Claude** 拥有自己的光标会是什么样子，那可能会很酷，对吧？就像它是一台电脑，我们可以编写代码，我们可以触摸所有东西，谁说电脑只能有一个光标呢？我们可以有第二个光标。但那实际上会崩溃很多。即使你向 **Apple** 和 **Microsoft** 展示这些很酷的梦想，你也会说：“如果……”，它会崩溃很多，因为我们电脑上的许多模型都是围绕着“只有一个东西在上面工作”这个想法构建的。有一个前台应用程序，一个后台应用程序。**Claude** 和 **Chrome** 可以在后台工作，但这只是在一个应用程序内部，但在操作系统层面，这要难得多。所以，我仍在努力解决 **Claude** 实际在你的电脑上操作意味着什么？正确的格式是 **Claude** 拥有自己的电脑，你设置好它，然后也许时不时地放大并玩一下，还是正确的格式是 **Claude** 只是等你离开一会儿，然后在你不在的时候接管？还是正确的做法是 **Claude** 只是在云端拥有自己的电脑，然后你希望 **Claude** 做什么，你都必须自己设置？对吧？有很多不同的选择。嗯，这是我经常思考的问题，比如你和你的电脑之间的关系，以及你和电脑上的数据之间的关系，因为这种关系的亲密程度取决于工具和……

<details>
<summary>Original English</summary>

**Felix**: I I do think it's a super interesting area because I I can maybe tell you like some of the things I thought about that I think actually bad idea so when when we initially started working on cowork I I did have some dreams about what would it look like for Claude to have its own cursor could be cool right like it's a computer we can write code we can touch everything like who says that computers need to have one cursor we could do a second cursor But that actually breaks down quite a bit. Even if you go and like present cool dreams to both Apple and Microsoft, you're like, wouldn't it be cool if um it breaks down quite a bit because so many of our models on a computer are built around this idea of like there's only one thing working on it. There's like a foreground app, a background app. Claude and Chrome can work in the background, but that's like within one application, but the operating system layer that is a lot harder to implement. So, I'm I'm still grappling with what what does it mean for Claude to actually act on your computer? Is the right format for Claude to have its own computer that you set up and maybe every now and then you like zoom in and you play with it or is the right format for Claude to just like wait until you're stepping away for a little bit and take over while you're gone or is the right move for Claude to just like have his own computer in the cloud and like whatever you want Claude to do you have to set up yourself, right? There's like a there's like a number of different options. Um, this is a thing I think about a lot like what is the relationship between you and your computer and you and your data on the computer because how intimate that relationship is kind of depends on the tool and

</details>

**Felix**: 你正在看的东西，对吧？就像我们很乐意分享一些东西，但很不乐意分享另一些东西。

<details>
<summary>Original English</summary>

**Felix**: the thing that you're looking at, right? Like we're quite comfortable sharing some things, very uncomfortable sharing other things.

</details>

**Felix**: 我认为任何成功的产品都必须处理这些不同的事情。但你可能，即使 **Claude** 能够做出决定，你最初会希望 **Claude** 做出这个决定吗？这很棘手，**Barry**，因为它不仅仅是隐私。它几乎是亲密关系，而且以一种让每个人都感到舒适的方式来推理它很棘手。是的，我可以看到，你知道，一个虚拟机，就像一个真正的虚拟机应用程序，你运行 **VM**，然后屏幕内有一个屏幕，你知道，你可以把它放在后台，但你可以跳进屏幕，那不是一个坏主意。是的。

<details>
<summary>Original English</summary>

**Felix**: And I think whatever product is going to be successful, we'll have to deal with those like with those different things. But you probably even if Claude was capable making a determination would you want Claude to make that determination in the first place? It's tricky Barry because it's like it's more than just privacy. It's like almost intimacy and it's like tricky to reason about in a way that will make everyone comfortable. Yeah, I could see, you know, a virtual box like actual virtual box app where like you run the VM and then you have like a screen within the screen, you know, you can put it in the background, but then you can like jump in the screen and like that's not a bad idea. Yeah.

</details>

**Swixs**: 你知道，就像我用过它，你知道，人们过去常常在 **Windows** 机器中虚拟化 **Kali Linux**。

<details>
<summary>Original English</summary>

**Swixs**: You know, like I mean I used it, you know, people used to do it virtualizing like Kali Linux in a Windows machine.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 然后你跳进去，然后你跳出来，但这不像双启动。它就像在里面。问题是你需要两倍的 **RAM**，两倍的，你知道，它对机器来说有点吃力。

<details>
<summary>Original English</summary>

**Swixs**: And like you just jump in and then you jump out, but it's like it's not like a dual boot. It's like within the thing. The problem is that you need twice the amount of RAM, twice the amount of, you know, it's like it's kind of taxing on the machine.

</details>

**Felix**: 但我认为那会很酷，就像看到那个小小的四方窗口。我可以看到它的桌面。看它点击东西多可爱。

<details>
<summary>Original English</summary>

**Felix**: But I think that would be cool kind like see, you know, the little quad window. I can see his desktop. Look how cute it is clicking around things.

</details>

**Alessio**: 我本来想提他才是“机器中的机器”的创始人，因为他有 **Windows 95** 项目。**Windows 85** 项目在哪里？

<details>
<summary>Original English</summary>

**Alessio**: I was going to bring up he's the original machine in the machine guy because he has the uh Windows uh Windows 95 project. Where's Where's the Windows 85 project at?

</details>

**Felix**: 我的 **GitHub** 上可能有一些，对吧？

<details>
<summary>Original English</summary>

**Felix**: There's probably some on my GitHub, right?

</details>

**Alessio**: 不，不，不，不。我，我，就像你看到的第一件事就是这个。

<details>
<summary>Original English</summary>

**Alessio**: No, no, no, no. I I It's like the first thing you see is this one.

</details>

**Felix**: 很好。

<details>
<summary>Original English</summary>

**Felix**: Nice.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 是的，没错。

<details>
<summary>Original English</summary>

**Felix**: Yeah, exactly.

</details>

### Electron与Chromium的工程奇迹

**Felix**: 那确实是一个非常有趣的项目。当然，我没有，我应该这么说，以免有人误解。我没有编写实际的……我当然没有构建 **Windows 95**，因为我当时还是个孩子，但我也没有构建能够模拟 **x86** 处理器以及 **JavaScript** 和 **WM** 的实际引擎。嗯，那是一个叫做 **V86** 的工具，它非常酷，每个人都应该尝试一下。但这源于我们在工作中进行的一场辩论，当时人们就像他们经常那样，最终在争论 **Electron** 的优点以及我们是否应该用 **JavaScript** 构建软件。是或否。我仍然非常沮丧，我可以在 **JavaScript** 中运行整个 **Windows 95**，并在虚拟化的 **JavaScript Windows 95** 机器中启动 **Microsoft Excel**，做一些我可以用整个链条比在传统 **SaaS** 应用程序中做很多其他事情更快的事情。嗯哼。

<details>
<summary>Original English</summary>

**Felix**: That was honestly a very fun project though. Like obviously I didn't I I should say this just so that no one gets the wrong impression. I did not write the actual the actual obviously I didn't build Windows only 5 because I was a child but also I did not build the actual engine that is capable of like simulating an x86 processor and JavaScript and WM. Um that's a tool called V86 which is very cool and everyone should try. But this came out of a this came out of like a debate we had at work where people were like they often are in the end debating the merits of Electron and whether or not we should be building software in JavaScript. Yes or no. And I still am very upset that I can run all of Windows 95 in JavaScript and launch Microsoft Excel inside the virtualized JavaScript Windows 95 machine and do things that pro I can do that entire chain faster than I can do a lot of other things in like traditional SAS applications. Mhm.

</details>

**Felix**: 这有点像我当时发起的一场性能狂潮。所以我主要是为了开玩笑给我在 **Slack** 的一些同事构建了这个。这花了一晚上。嗯……

<details>
<summary>Original English</summary>

**Felix**: And this is sort of like a like a performance rampage that I went on. So I mostly built this as a joke for some of my colleagues at Slack. This took took like one night. Um

</details>

**Alessio**: 什么？

<details>
<summary>Original English</summary>

**Alessio**: what?

</details>

**Felix**: 但那，那并不难。所有的难点都在 **V86** 中。如果你去看那个仓库，它会说：“这项工作99%是由一个名叫 **Copy** 的人完成的，他叫 **Fabian**。”

<details>
<summary>Original English</summary>

**Felix**: But then that I it was it was not hard to do. It was all the hard work is in V86. Like if you go to the repo, it's going to say like 99% of this work is done by by um a guy who goes after the by the name Copy. His name is Fabian.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 嗯。

<details>
<summary>Original English</summary>

**Felix**: Um

</details>

**Alessio**: 酷。我认为你又回到了 **Windows** 的工作状态，因为你正在构建 **Windows** 支持。嗯，我认为有一些非常酷的技术故事可以讲。嗯，这让人们对“这有多难，以及你如何投资沙盒有多重要”有了更深的理解。所以也许这是一个很好的机会来谈谈一些细节。

<details>
<summary>Original English</summary>

**Alessio**: cool. I think you're you're kind of back on the Windows grind because you're building out the Windows support. Uh I thought there was some really cool technical stories to tell. Uh and it gives people an appreciation of like well here's how hard it is and here's how important how you invest in the sandbox. So maybe this is like a good opportunity to talk about some of the details.

</details>

**Felix**: 哦，是的，**VM** 老实说太酷了。我们有很多不喜欢 **VM** 的地方，对吧？有很多权衡是真实存在的，你需要知道你为什么做出这些权衡。嗯，你是对的，很多人写信给我说：“嘿，为什么 **Claude** 占用了10GB？”我可以说，那部分实际上并没有占用10GB。这只是 **Mac OS** 显示字节的方式，它是错误的。但我们实际写入磁盘的方式是通过压缩图像中的空白空间。所以，它实际上并没有占用10GB。但这是一种技术上的区别，可能不会持续太久。

<details>
<summary>Original English</summary>

**Felix**: Oh yeah, the the VM honestly is like so cool. There's a lot of things we dislike about the VM, right? Like there's a lot of things that are real tradeoffs and you want to know why you're making those trade-offs. Um, and you're right, like a lot of people write me like, "Hey, how how come Claude is taking up 10 GB?" I could say on that part, it's not actually taking up 10 GB. It's just like a way that Mac OS displays bytes. It's like wrong. But the way we actually write it to disk is by we collapse the empty space in the image. So, it's not actually taking up 10 gigs. But that's a technical differentiation that's probably not going to matter too long.

</details>

**Swixs**: 对我来说，启动时间太长了。是的。有时需要30秒。我不知道。哦，应该比那更快。无论如何。它将是10秒，但感觉像30秒。

<details>
<summary>Original English</summary>

**Swixs**: To me, the the the how come it takes too long to start. Yeah. It's like 30 seconds sometimes. I don't know. Oh, it should be faster than that. Whatever. It's going to be 10, but it feels like 30.

</details>

**Felix**: 是的。无论如何，它都会比直接在你的电脑上运行代码慢，对吧？所以权衡是真实存在的。但我们在 **Windows** 上做的是，我们使用 **Windows** 的主机计算系统。这与 **WSL2** 运行的系统相同，就像 **Windows** 的 **Linux** 子系统，我认为很多开发者都非常欣赏它。是的。嗯，这很酷，因为我们必须将这个虚拟机运行的系统空间分开，谁可以与这个虚拟机对话，因为显然你给了这个虚拟机这么大的权力。我们如何不仅优化两个系统之间的连接，还确保其他随机应用程序不会与 **Claude** 对话？

<details>
<summary>Original English</summary>

**Felix**: Yeah. Like even either way, like whatever it is, it's going to be it's going to be slower than just running code directly on your computer, right? So, the trade-offs are real. But what we're doing on Windows, we're using the Windows Windows uh host compute system. It's the same thing that WSL2 runs on, like the Windows subsystem for Linux that I think a lot of developers appreciate quite a bit. Yeah. Um, and it's it's pretty cool because we sort of like have to separate out which system space this virtual machine runs in in, who gets to talk to that virtual machine because obviously you give this virtual machine this amount of power. How do we optimize not just the connection between the two systems, but also how do we make sure that random other application doesn't get to talk to Claude

</details>

**Felix**: 我们做了一些非常有趣的事情。嗯，上周我们开始编写一个新的网络服务，一个网络驱动程序，它优化了 **Claude** 与互联网的对话方式。如果你的公司正在做一些奇怪的互联网事情，比如数据包检查，以及，你知道，在你的公司内部进行分解，

<details>
<summary>Original English</summary>

**Felix**: we do some pretty interesting things. Um, last week we started writing a new networking service, a networking driver that optimizes how Claude talks to the internet. If your company is doing like weird internet things like packet inspection and like like you know taking apart as a cell inside your company,

</details>

**Felix**: 我认为可能有一个非常小、简单的 **Cowork** 版本可以构建，它更简单，但也会在大多数用户的电脑上崩溃，而这个版本非常好，因为它在大多数用户的电脑上都能工作。嗯，我总是举的默认例子是，我真的希望它能在大多数人使用的机器上高效运行，而那台机器可能没有 **Python**。它不会有 **Node.js**。

<details>
<summary>Original English</summary>

**Felix**: I think there was probably like a very small easy version to build off cowork that is much simpler but also breaks on most most users computers and this one is quite nice because it works on most users computers. Um, and the default example I always go for is I I really want this to be highly effective on like a on like a machine that most people pick up and that machine will probably not have Python. It will not have Node.js.

</details>

**Felix**: 即使我只移除这两个东西，**Claude** 在你的电脑上也会大大降低效率。

<details>
<summary>Original English</summary>

**Felix**: And even if I just take away those two things, Claude is going to be so much less effective on your computer.

</details>

**Swixs**: 那你怎么办？你甚至不，我的意思是，也许要求人们安装 **Node** 和 **Python**。

<details>
<summary>Original English</summary>

**Swixs**: So what do you do? You don't even I mean maybe require people to install node in Python.

</details>

**Felix**: 哦，就像你说的，未来没有 **VM** 会是什么样子？

<details>
<summary>Original English</summary>

**Felix**: Oh, like you mean for like a what does the future look like without a VM?

</details>

**Swixs**: 不，不，不。所以，所以就像你说的，对吧？假设目标机器是任何一个默认配置的 **Windows** 笔记本电脑。

<details>
<summary>Original English</summary>

**Swixs**: No, no, no. So, so like like you said, right? Let's say target machine is whatever is a default spec windows laptop.

</details>

**Felix**: 我们这样做很酷。所以在 **Mac OS** 上，我们使用 **Apple** 虚拟化框架，它优化得相当好。就像它很棒，简单的 **API** 调用，对吧？

<details>
<summary>Original English</summary>

**Felix**: We do this which is quite cool. So on on uh Mac OS we use the um Apple virtualization framework which is pretty solidly optimized. Like it's good stuff simple API call right?

</details>

**Swixs**: 是的，它超级简单。

<details>
<summary>Original English</summary>

**Swixs**: Yeah it's like super simple.

</details>

**Felix**: 我最近看到了代码，我就想：“就这些？什么鬼？”

<details>
<summary>Original English</summary>

**Felix**: I I saw the code recently and I was like that's it? What the

</details>

**Felix**: 一旦你开始在上面发布生产代码，你就会开始添加所有这些边缘情况，它最终会变得稍微长一点，但是，嗯，我认为 **Apple** 在虚拟化框架方面做得非常出色，它非常非常好，非常快，非常可靠。在 **Windows** 上也是如此，主机计算系统，我认为 **WSL2** 也是 **Windows** 中的一颗明珠，它是开发者普遍称赞的少数几样东西之一，非常非常酷。而且，连接到同一个子系统，使我们更容易说，我们真的不在乎你的电脑有多么锁定。也许它是你雇主的电脑，你的雇主已经决定你什么都不能安装。

<details>
<summary>Original English</summary>

**Felix**: we do you once you start like shipping production code on it you start adding like all of these edge cases you're it ends up being a little longer but um I think Apple really cooked with a virtualization framework and it's very very good it is very fast it's very reliable and same on Windows the the host compute system I think WSL2 as well is maybe one of the diamonds within Windows it's like one of the few things that developers universally rave about is very very cool and like hooking into the same subsystem makes a lot easier for us to say we don't really care how locked down your computer is. Maybe it's like your employer's computer and your employer has decided that you get to install nothing.

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Felix**: 不可信。但在很多环境中都是如此，对吧？就像即使在 **Anthropic**，我们的 **IT** 部门也控制着你可以安装什么样的软件，这在很多公司都是非常普遍的经验。嗯，这给了 **IT** 部门相当大的便利，因为我们可以说你可以将 **Claude** 的电脑与用户的电脑分开。然后对于 **Claude** 的电脑，你可能关心的是数据丢失。你关心的是潜在的恶意行为者。你可能关心数据被窃取。一旦你控制了网络和文件系统层，你就不再需要关心 **Claude** 是否正在编写超级有用的 **Python** 脚本。你担心的是，一旦你安装了 **Python**，现在任何人都可以对电脑做任何事情，但一旦你把它放到 **VM** 中，这种风险就会大大降低。

<details>
<summary>Original English</summary>

**Felix**: Not trusted. But it's true in a lot of environments, right? Like even at Anthropic, um our IT department controls what kind of software you install, which is like a pretty common experience for many companies. Um, and this gives IT departments a decent amount of like it makes their job so much easier because we can say you can separate out Claude's computer from the user's computer. And then for Claude's computer, what you probably care about is data loss. You care about like a potentially hostile actor. You care about maybe data being exfiltrated. And once you control the network and the file system layer, you don't really care necessarily anymore that Claude might be writing super useful Python scripts. What worries you about the fact is that like once you install Python now anyone can do anything on the computer but once you put that in a VM that risk really goes down.

</details>

**Felix**: 是的。所以这就是我们费尽周折的原因。

<details>
<summary>Original English</summary>

**Felix**: Yeah. So that's why we jump through all of these hoops.

</details>

### 权限疲劳与沙盒

**Swixs**: 是的。我认为你对此有不同的推文。嗯，但这几乎就像人们也有权限疲劳，就像你不能批准每一个命令，就像有时默认情况下，一些 **CLI**，我认为即使是早期的 **Cloud Code**，你都必须批准每一个命令。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. I think you you had a different uh tweet about this. Um but it's it's almost like people have also approve exhaustion like it's like you can't approve every single commands like sometimes by by default some of the the CLI I think even early cloud code uh you have to approve every single command.

</details>

**Felix**: 是的。而且，就像，所以存在这种二分法，要么批准每一步，要么危险地跳过权限。

<details>
<summary>Original English</summary>

**Felix**: Yeah. and and like it's so so there's this sort of dichotomy between either approve every step or dangerously skip permissions.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 实际上沙盒就像是一种中间地带。

<details>
<summary>Original English</summary>

**Felix**: And actually sandboxing is like kind of like the middle ground.

</details>

**Felix**: 是的。我确实认为，作为行业，我们也许有责任提出比“哦，这超级安全，只要它什么都不做”更好的东西，对吧？

<details>
<summary>Original English</summary>

**Felix**: Yeah. I do think I do think it it's maybe on us as like the industry to come up with something better than oh this is super safe as long as it doesn't do anything,

</details>

**Felix**: 如果你想让它有用，那么你必须批准每一步。就像计算机使用就是一个很好的例子。让计算机在你的主机上超级安全，真正超级安全的唯一方法，可能就是你批准每一个操作，对吧？就像模型会说：“我想输入字母L。”你就会说：“好的，这看起来没问题，因为我知道我知道哪个光标是焦点。”

<details>
<summary>Original English</summary>

**Felix**: right? If you want this to be useful then you have to like approve every single step of the way. And like computer use is a good example. The only way to make computer use on your host like super safe, like really super safe is probably if you approve every single action, right? Like models like I would like to type the word L. You're like, okay, that seems fine cuz I know I know which like cursor is focused.

</details>

**Swixs**: 是的，如果你不授权，它就无法运行。

<details>
<summary>Original English</summary>

**Swixs**: Yeah, it's not function if you don't delegate.

</details>

**Felix**: 是的，没错。你需要正确地授权。你需要能够授权然后走开，并相信这个东西不会自动搞砸。我甚至不认为我们需要构建完美的系统。我不认为我们需要等待100%的模型对齐。我们可以依赖我们行业长期使用的 **瑞士奶酪模型**，但我确实认为我们可能最终需要普遍投入更多。这就是我们正在做的。我们需要在那些我们可以说你不需要批准所有事情的系统上投入更多。

<details>
<summary>Original English</summary>

**Felix**: Yeah, exactly. You need to like properly delegate. You need to be able to like delegate and walk away and trust that this thing is not going to like mess up automatically. And I don't even think we need to build perfect systems. I don't think we need to wait for like 100% model alignment. We can rely on the same Swiss cheese model we've used in the industry for a long time, but I do think we need to like universally maybe eventually invest more. And that's what we're doing. We need to invest more in systems where we can say you do not need to approve everything.

</details>

**Swixs**: 谈到 **瑞士奶酪模型**，他刚刚写了一篇关于这个的文章。

<details>
<summary>Original English</summary>

**Swixs**: Speaking of Swiss cheese model, he just wrote a thing about this.

</details>

**Felix**: 哦，酷。是的。

<details>
<summary>Original English</summary>

**Felix**: Oh, cool. Yeah.

</details>

**Swixs**: 嗯，是的。嗯，是的，超级酷。我的意思是，是的，这很奇怪，就像我猜通常我认为安全和保障对工程师来说是一个无聊的词。他们会说：“这对我来说可能不安全。不安全。”但是，嗯，我认为实现正确的事情，就像你正在追求一个消费者/专业人士。

<details>
<summary>Original English</summary>

**Swixs**: Uh yeah. Um yeah, super cool. I mean, yeah, it's it's weird how like I guess usually I think safety and security is kind of like a boring word to to engineers. They're like this can be unsafe to me. Unsecure. But um I think achieving the right thing like you're going after a consumer/pro.

</details>

**Felix**: 是的。是的。有点像两者兼顾。我认为我也想吸引那些使用 **Cloud Code** 毫无困难的人，就像你一样，对吧？但仍然觉得它可能只是方便，更容易。你就会说：“哦，酷。右边有一个待办事项列表。我可以编辑它。”如果你需要，这些事情做起来就更容易。

<details>
<summary>Original English</summary>

**Felix**: Yeah. Yeah. Kind of like both. I think I I also want to capture people who would have no trouble using cloud code like yourself, right? But still find it maybe just convenient, easier. You're like, "Oh, cool. There's like the to-do list on the right. I can edit it. Those things are just easier to do if you have to.

</details>

**Swixs**: 是的，但这显然是知识工作方面。**Cloud Code** 将明确捕捉开发工作流程。但我确实认为你必须关注这些安全和保障细节，才能让人们信任它。而且，即使是 **Claude** 和 **Chrome**，拥有无论什么 **API** 用来做后台事情。

<details>
<summary>Original English</summary>

**Swixs**: Yeah, but this is like clearly the knowledge work side. Cloud code will clearly capture the development workflow. But like I I do think like you have to sweat this like safety and security details in order for people to trust it. And like the even Claude and chrome like having the whatever API uses to do the background thing.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 嗯，那是我使用它的唯一原因，因为否则我将不得不另外找一台机器。

<details>
<summary>Original English</summary>

**Swixs**: Um that's the only reason I use it is because otherwise I would have to just get a separate machine.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 然后运行它。

<details>
<summary>Original English</summary>

**Swixs**: And just run it run.

</details>

**Felix**: 那听起来超级烦人。

<details>
<summary>Original English</summary>

**Felix**: That sounds super annoying.

</details>

**Swixs**: 是的。我的意思是，我目前正在这样做，但是……

<details>
<summary>Original English</summary>

**Swixs**: Yeah. I mean like currently doing it but

</details>

**Felix**: 我认为，我认为作为开发者，嗯，也许我们更愿意冒险，但我们也只是接受我们更愿意冒险，但我认为我们也有，我不想说傲慢，而是那种信任，如果真正糟糕的事情发生，我们可能可以修复它。

<details>
<summary>Original English</summary>

**Felix**: and I think I think also as developers um maybe we're we are more risk tolerant but we're also just like accepting we are more risk tolerant but I think we also just have like I don't want to say arrogance but like sort of the trust that if like the really bad thing happens we can probably fix it.

</details>

**Swixs**: 我只是告诉 **Claude** 在执行任何不可逆转的操作之前，比如发送电子邮件或永久执行之前，先和我确认。这已经足够好了。但就像，甚至不是 **Claude**。我的意思是，像 **npm install** 这样简单的事情，我们都在以完整的用户权限运行 **npm install**，如果它想读取 **SSH**，它就会读取。

<details>
<summary>Original English</summary>

**Swixs**: I just tell Claude to like check with me before doing any irreversible action like sending an email or doing it permanently. It's good enough. But like not even Claude. I mean like simple things such as npm install like we're all running npm install with full user permissions and if it wants to like read SSH it will

</details>

**Felix**: 真是太疯狂了，这竟然是默认设置。是的，我知道，我同意，我同意，没关系，我显然每天都在做。不，对吧？就像，嗯，我认为显然 **npm** 和 **GitHub** 也做得很好，可能在过去几个月里清理了门户，并提出了更具体的token，但总的来说，我认为作为工程师，我们总是更愿意冒险一点。如果你做一点内省，问问自己，我们应该这样做吗？你可能不会总是得到正确的答案。我认为对于模型也是如此，我的方法是，我不会……最安全的事情就是什么都不做。我们确实想要功能强大的产品，但在可能的情况下，我不想问你是否同意一个脚本？因为我有点相信，一旦它成为你工作流程的一部分，你可能要么没有能力理解这个 **Python** 脚本是否安全，要么你根本就不会去阅读它。

<details>
<summary>Original English</summary>

**Felix**: crazy that that is the default kind of yeah I know I agree I agree it's fine like I'm obviously doing it every single day. No, right. Like, uh, and I think obviously npm and GitHub 2 have like done a pretty good job maybe over the last couple months to like clean house and come up with like more specific tokens, but generally speaking, I think as engineers, we've always been a little bit more risk tolerant. And if you do a little bit of introspection and you ask yourself, is that how we should be doing things? You might not always come up with the right answer. And I think for models too, like my approach, like I'm not going to the the safest thing is to do nothing. We do want products that are quite capable, but to the extent possible, I don't want to ask you, are you okay with a script? Because I kind of believe that once it starts becoming a part of your workflow, you're probably not either either you don't have the skill to understand whether or not this Python script is safe or you're not going to read it anyway.

</details>

### Cowork的未来展望

**Alessio**: 酷。我想问几个告别问题。嗯，**Cowork** 的未来是什么？

<details>
<summary>Original English</summary>

**Alessio**: Cool. I guess a couple parting questions. Uh what's the future of Clockwork?

</details>

**Felix**: 我认为我们仍处于早期阶段。我们将继续发布产品，我们将继续发布产品，嗯，我们将非常快速地迭代这个东西，但我的意思是，你可以继续期待每周都会有一个小的新功能，如果不是一个大的新功能的话。嗯，我可能会继续加倍投入在你的电脑上，让你的电脑更有效率，让 **Claude** 在你的电脑上更有效率。嗯，我们今天谈到，我们开始更多地思考“你的电脑”意味着什么？它必须是你面前的那个，还是你电脑上的 **VM**，还是其他地方的电脑？然后第三件让我非常兴奋的事情是，我们正在继续爬这座山，慢慢地引导那些习惯于提问并得到答案的用户，让他们慢慢地更多地放手，让 **Claude** 接管越来越大的任务和工作，无论是在时间上还是在范围上。我认为你可能会看到我们的大部分投资都体现在我们的功能发布上，以实现这两个目标：在你的电脑上做更多事情的能力，以及更独立、更长时间地做事情的能力。远程控制对 **Cloud Cowork** 有用吗？

<details>
<summary>Original English</summary>

**Felix**: I think we're still we're still such early days. We're going to keep shipping things that we're going to keep shipping things that um we're going to keep iterating on this thing like pretty quickly, but which I mean you can sort of continue to expect that every single week there's going to be like a small new feature if not a big new feature. Um I'm going to continue probably to double down on your computer and like making you effective in your computer, making Claude effective on your computer. Um we're starting grapple as we talked about today, grapple more with the question of like what does it mean? What does your computer mean? Does it have to be the one in front of you or like a VM on your computer or like a computer somewhere else? And then the third thing that I'm quite excited about is we're continuing to go up this hill climbing on slowly taking users who are used to asking questions and getting an answer to slowly teaching them to like step more and more away and let Claude take over like bigger and bigger tasks and work both in time as well as in like scope. And I think you can probably see most of our investments on our feature releases to like work on both of those things like the ability to do more on your computer and then the ability to do it more independently and for longer. Does remote control work for cloud core work yet?

</details>

**Swixs**: 不。对。

<details>
<summary>Original English</summary>

**Swixs**: No. Right.

</details>

**Felix**: 很好的问题。

<details>
<summary>Original English</summary>

**Felix**: Excellent question.

</details>

**Swixs**: 即将推出。我的意思是，如果你想继续押注在你的电脑上，那显然是理所当然的。但对我来说，你知道，我们谈论人们今年还没有准备好，就像没有一堵墙，它正在加速。对我来说，今年年底我们会做什么不同的事情，而我们今年年初甚至没有想到？对吧？就像我只是想展望未来，看看有什么好的用例是我们要努力实现的目标。所以，例如，对于机器学习科学家来说，总是：“好吧，我想要一个 **AI** 科学家，可以自动化机器学习。”但对于知识工作来说，我的意思是，我已经可以，你知道，让它注册 **Google Cloud**，对我来说就是 **AGI**。

<details>
<summary>Original English</summary>

**Swixs**: Coming soon. I mean that's an obvious thing if you want to keep betting on the on your computer. But to me like you know we we talk about like people are not ready this year like the there's there's no wall that's it's accelerating. to me like what will be we be doing differently at the end of this year that you know we maybe not even thinking about this at the start of this year right like I'm just trying to look ahead as to like what's like a good use case that you're we sort of aim towards so for example for the machine learning scientist it's always okay well I want AI scientist that can automate automate machine learning but like for for knowledge work I mean I can already you know get it to sign up for Google cloud to mean a GI

</details>

**Swixs**: 因为 **Google Cloud**，但除此之外，我不知道。

<details>
<summary>Original English</summary>

**Swixs**: because Google cloud but like what what is But beyond that, I don't know.

</details>

**Felix**: 我认为这基本上是这样的想法：你仍然需要告诉它构建你的脚本，对吧？你仍然有点参与其中。

<details>
<summary>Original English</summary>

**Felix**: I think it's basically the idea that like you still had to tell her to build your script, right? You were still kind of involved.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yes.

</details>

**Felix**: 也许以一种对你来说有点神奇的方式，但对我来说，作为构建这个产品的人，仍然觉得有点笨重。我看到了很多流程，我就想：“哦，让我帮你省去这些。”

<details>
<summary>Original English</summary>

**Felix**: In maybe a way that felt kind of magical to you, but like maybe to me on the other side as the person building this product still feels kind of heavy-handed. I see so much process that I'm like, "Oh, let me take that away from you."

</details>

**Felix**: 但我怎么才能继续向上层堆栈发展，让你的生活越来越轻松呢？

<details>
<summary>Original English</summary>

**Felix**: But like how do I just go I will continuously go will continue to go like further and further up the stack and make your life easier and easier.

</details>

**Swixs**: 哦，这里有一个。对。是的。看。嗯，你知道我不在乎我自己的隐私或其他什么，或者我信任 **Claude**，我信任 **Anthropic**，所以就观察我每天的日常活动，在一天结束时告诉我，你觉得 **Cloud Cowork** 能做什么？

<details>
<summary>Original English</summary>

**Swixs**: Oh, here's one. Right. Yeah. Watch. uh I you know I don't care about my own privacy or whatever or I trust cl I trust anthropic so just watch everything I do on a normal day-to-day basis at the end of the day tell me what you is cloud co-workable

</details>

**Felix**: 是的，我不知道。

<details>
<summary>Original English</summary>

**Felix**: yeah I don't know

</details>

**Felix**: 我认为很多这些产品有趣的地方在于，出于好理由，我并不喜欢，我整个职业生涯中从未过多地透露我正在做什么，因为我认为你应该只是……

<details>
<summary>Original English</summary>

**Felix**: I think the funny thing about a lot of these products is that like for good reason I don't enjoy I I don't throughout my entire career I've never like teased too much what I'm working on because I think you should just like

</details>

**Swixs**: 是的，发布它，是的，构建并发布它，然后谈论它。

<details>
<summary>Original English</summary>

**Swixs**: yeah to release it yeah build the release it and then talk about it like

</details>

**Felix**: 我不太喜欢那种提前模糊地发布工作内容。但对我来说总是如此引人入胜的是，你们今天多次提到了一些事情，就像：“是的，那很明显，非常明显。”

<details>
<summary>Original English</summary>

**Felix**: I'm I'm not a big fan of that like vague posting amount work ahead of time. But the thing that is like always so fascinating to me is like both of you all multiple times today you've like mentioned things and like yeah that is obvious like very obvious okay

</details>

**Felix**: 某人应该在这些事情上努力。嗯，我认为我们仍然处于这样的阶段：如果你看 **Cowork**，我们发布的东西可能不会让你们中的任何一个人感到惊讶。你们会说：“是的，那显然有价值，显然我们在做那些事情，显然那很好用。”我越是触及这些点，我们的功能越符合这个类别，我认为对我们来说就越好，因为那样我们就不会构建过于专业化或风格上过于困难的东西。

<details>
<summary>Original English</summary>

**Felix**: that someone should be working on those things. Um and I think we're still in the space where if you look at cowwork the things that we will releasing will probably not be a big surprise to either of you. You're going to be like yeah obviously that's valuable obviously that we're working on those things and obviously that's good and useful. And the more I hit those those points, the more our features fit into that category, I think the better it is for us because then we don't end up building things that are too hyper specialized or too difficult on the style.

</details>

**Swixs**: 是的。我认为高度专业化的事情非常重要。它让你保持通用性。这意味着你可能不会想得太小。我不知道那个词是什么。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. I think the hypers specialized thing is very important. It it keeps you like general purpose. It means you're not thinking too small maybe. I I don't know what the the word is.

</details>

**Felix**: 是的。是的。没错。这就像整个概念，我们从未发布过，你知道，没有 **Cloud Code** 专门用于使用 **React** 和 **Tenstack** 的 **Node.js** 应用程序，而且只有这两样东西，如果它是其他任何东西……

<details>
<summary>Original English</summary>

**Felix**: Yeah. Yeah. Exactly. It's like the whole concept that like at no point did we release you know there's no cloud code for NodeJS applications that use React and 10 stack and only those two things and like if it's anything else

</details>

**Swixs**: 我知道有几家这样的初创公司。

<details>
<summary>Original English</summary>

**Swixs**: I know several startups like that

</details>

**Felix**: 我认为可能，我不是风险投资家，我不是投资者，我很难预测市场走向，但就我感兴趣的构建模块而言，**Electron** 可能是我构建过的最受欢迎的东西。嗯，**Electron** 本身非常抽象和通用。我有很多应用程序都在上面运行，我认为我很难预测最终会有多少应用程序使用 **Electron**。

<details>
<summary>Original English</summary>

**Felix**: I think there's probably like I'm not a VC I'm not an investor it's like hard for me to predict where the markets go but in terms of the building blocks that I'm interested in the Electron is probably by far the most popular thing I ever built and um Electron itself is like very abstractable and generalizable I had like so many apps run in it and I think it would have been hard for me to predict how many apps actually end up using Electron.

</details>

**Felix**: 嗯，更没用的是预测这些应用程序会做什么。我清楚地记得 **Bloom** 问世时，我觉得那很酷。就像你是一个小圆圈里的摄像头，在角落里。那真的很聪明。

<details>
<summary>Original English</summary>

**Felix**: Um, and what would have been even less useful for me to predict this and what those apps do. I distinly remember Bloom coming out and being like that is cool. Like you were a camera in a little circle in the corner. That is really smart.

</details>

**Swixs**: 那是一个 **Electron** 应用程序。是的。是的。或者至少曾经是。我不确定现在是否还是。它曾经是。或者像 **OnePassword** 有很多有趣的东西，对吧？它，它，它是一个我非常熟悉的堆栈层面，每当我给其他工程师建议时，我认为最有价值的投资就是那个层面，因为那个层面的工具不是那么好，但那才是你未来获得最大杠杆的地方。

<details>
<summary>Original English</summary>

**Swixs**: That's an Electron app. Yeah. Yeah. Or at least was. I'm not sure if it still is. It was for a while. Or like one password has so many interesting things, right? It it's it's it's a level of the stacks that I'm quite comfortable with and whenever I give other engineers advice, it's actually that layer that I think is most valuable to invest in because the tools of the layer are not that good but that's where you get the most leverage for like the future in general.

</details>

### Electron与Tauri的比较

**Alessio**: 只是快速插一句关于 **Electron** 的话，因为我总是好奇这个，嗯，你有没有看过 **Tauri**？

<details>
<summary>Original English</summary>

**Alessio**: Just quick tangent on Electron cuz I always wonder this uh have you looked at Tori?

</details>

**Felix**: 我看过。是的。

<details>
<summary>Original English</summary>

**Felix**: I have. Yeah.

</details>

**Alessio**: 你有什么看法？你知道，我的观点是，大多数东西默认都应该是 **Tauri**，除非你真的需要 **Electron** 的全部功能。但是……

<details>
<summary>Original English</summary>

**Alessio**: What's your take? You know, my my my my view is like most things should be Tory by default unless you really need the full power of Electron. But

</details>

**Felix**: 是的，我可以谈谈我的看法。我可以谈谈我的大看法。我们为什么要在一个东西里面打包一个完整的 **Chromium** 版本，对吧？我们为什么要那样做？嗯，人们经常问我这个问题，因为它非常反直觉。使用操作系统上的 **WebViews** 不是更容易吗？不这样做不是更容易吗？答案是肯定的。而且，显然我曾经这样做过。我做过。有一个版本的 **Slack** 应用程序只使用了我们使用的操作系统。等等，你启动了 **Slack** 应用程序吗？

<details>
<summary>Original English</summary>

**Felix**: yeah, I can give like my take on I can give my big take. Why do we ship an entire version of Chromium inside the thing, right? Like why do we do that? And um people ask me this question a lot because it's like very counterintuitive. Wouldn't it be much easier to use the web views that are on the operating system? Wouldn't it be much easier not to have to do that? And the answer is yes. And like obviously I did that once upon a time. I did that. There was a version of the Slack app that used just the operating system that we use. Wait, did you did you start the Slack app?

</details>

**Swixs**: 我会。嗯，团队合作。是的，但我在那里，我们构建了 **Slack** 应用程序。是的。

<details>
<summary>Original English</summary>

**Swixs**: I would Well, team effort in Yeah, but I was I was there and we built the Slack app. Yeah,

</details>

**Felix**: 这很疯狂。嗯，我的意思是，显然让 **Electron** 的人来做，但是……

<details>
<summary>Original English</summary>

**Felix**: it's crazy. Um I mean obviously get the Electron guy to do it, but

</details>

**Felix**: 嗯，但这很有趣。就像我加入 **Slack** 的时候，他们已经有一个用当时叫做 **Macap** 的东西构建的应用程序。它有点像移动端的应用程序。它只是使用了操作系统的 **WebViews**。嗯，那因为很多原因都行不通。嗯，他们就说：“好吧，也许我们需要更强大的武器。我们需要更多地控制渲染堆栈。”我在这里总是提到几点。嗯，我认为如果你正在构建一个小型应用程序，只使用操作系统的 **WebView** 完全没问题。如果你正在构建一个应用程序，可能没有太多用户会因为它的不工作而大声抱怨，那也没问题。选择自己的嵌入式渲染引擎的原因是，即使在2026年，操作系统的渲染引擎也不是那么好。它们就是没那么好。**Microsoft** 和 **Apple** 都试图摆脱这种情况。到目前为止，他们真的没有做到。升级它们的唯一方法是升级你的操作系统。所以，如果你是 **Slack**，并且在 **WK Webb** 和其他一些 **WebView** 选项中有一个关键的渲染bug，你唯一的办法就是告诉你的客户：“哦，抱歉，你太穷了。你没有买最新的 **MacBook**。”这是不可接受的。

<details>
<summary>Original English</summary>

**Felix**: Well, but this is an interesting point. Like by the time by the time I joined Slack, they already had an app that was built with something at the time called Macap. It was a little bit like the same app thing for mobile. it just used the operating systems web views. Um, and that didn't work for like so many reasons. Um, and they were like, "All right, maybe we need like bigger guns. We need like take more control of the rendering stack." And there's there's a few things I always mention here. Um, I think if you're building a small app, just going with the operating systems, spread view is perfectly fine. If you're building an app maybe that doesn't have too many users who will like cry bloody murder if it doesn't work, that is fine. The reason to go with your own embedded rendering engine is because, and this is still true in 2026, the operating system rendering engines are not that good. They're just not that good. Both Microsoft and Apple are trying to move away from that. They so far really haven't. The only way to upgrade those is to upgrade your operating system. So, if you're say a Slack and you have a critical rendering bug in WK Webb and some of the other web view options, your only recourse is to tell your customer, "Oh, sorry, you're too poor. You didn't buy the latest MacBook. Unacceptable.

</details>

**Felix**: 对用户来说不可接受。作为开发者来说不可接受。所以，你必须向下层堆栈发展，找到最好的渲染引擎，然后把它放到你的应用程序中。为什么是 **Chromium**？尽管它非常大，但 **Chromium** 迄今为止是最好的东西。就像我经常喜欢提醒人们 **Unreal Engine**。如果你想渲染一些文本，他们会使用 **Chromium**。**Chromium** 是 **Unreal Engine** 的一部分，出于同样的目的。**Chromium** 非常非常好。我认为它是工程奇迹之一。我们现在在旧金山录制。这个城市的大多数人都是网页开发者。我很难夸大它的神奇之处。他们可以运行，比如动态渲染 **YouTube** 视频，协商比特率，找出如何处理你极度损坏的硬件驱动程序。实际上，这很有趣。嗯，你可以输入 `chrome://gpu`。好的。如果你向下滚动一点，

<details>
<summary>Original English</summary>

**Felix**: Unacceptable to user. Unacceptable as a developer. So, you sort of need to like go down the stack and like find the best rendering engine, then put it in your app. Why Chromium? Even though it's very big, Chromium is by far the best thing. Like I I often like to remind people the Unreal Engine. You want to render some text, they use Chromium. Like Chromium is part of the Unreal Engine for same purposes. Chromium is very very good. I think it's like one of the marvels of engineering. It's very hard from we're in San Francisco right now as we're recording. Most of the people in the city are web developers. It's hard for me to like overstate how magical it is. They can run se like rendering a YouTube video dynamically negotiating a bit rate figuring out what to do about your extremely broken hardware driver. Actually, this is a fun thing. Um, you can enter Chrome colon whackwack GPU. Okay. And if you scroll down a little bit,

</details>

**Felix**: 这些都是已启用的变通方法，因为你的电脑上出了问题。如果你在 **Windows** 电脑上使用一个不是最流行的 **GPU**，它会更长。所有这些通常只是为了确保，如果我作为一个开发者说：“我希望这里出现一个红色像素”，那它确实会发生。**Chrome** 是一个奇迹，因为它可以在用户可能扔给你的所有机器上工作，并且相当可靠。如果它不工作，他们可能会在24小时内修复它。我明白了。所以这是一个超级操作系统，对吧？它无处不在。

<details>
<summary>Original English</summary>

**Felix**: these are all the enabled workarounds because something is going wrong on your computer. If you're doing this on a Windows computer with like a GPU that is not the most popular GPU, it will be much longer. And all of these are usually just there to make sure that if I say as a developer, I want a red pixel to appear here, that that actually happens. Chrome is such a marvel because it works on all the machines that a user might throw at you and it's going to work fairly reliably. And if it doesn't, they will probably fix it within 24 hours. I see. So this is the super operating system, right? That that works everywhere.

</details>

**Swixs**: 是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah.

</details>

**Felix**: 对。好的。是的。

<details>
<summary>Original English</summary>

**Felix**: Right. Okay. Yeah.

</details>

**Felix**: 所以 **Electron** 的很多魔力老实说只是在于它让你非常容易地发布 **Chromium**，以一种完全符合你和你的用例的方式。没错。

<details>
<summary>Original English</summary>

**Felix**: So a lot of the magic of Electron is honestly just that it makes it very easy for you to ship Chromium in a way that serves you exactly and your use cases. Exactly.

</details>

**Alessio**: 我们的下一次采访是与 **Maran Dre**。是的。他曾说过这样一句话：“桌面操作系统只是实际操作系统的糟糕实现，而实际的操作系统是 **Chrome**，它无处不在。”这就是你发布应用程序的平台。

<details>
<summary>Original English</summary>

**Alessio**: Our next interview is with Maran Dre. Yeah. Who had the phrase like desktop OSS are just poorly uh poor implications of the the actual OS which is Chrome which like actually works everywhere. And this is this is the platform where you ship apps.

</details>

**Felix**: 我认为最疯狂的事情是，作为工程师，我们经常假设我们下面的平台层是超级稳定的，然后你和那些人交谈，他们会说：“我们也只是在猜测。”嗯，嗯，我在 **Slack** 有一个非常清晰的时刻，当时我们在 **Slack** 的一个客户是 **Nvidia**，有一段时间我真的把 **GPU** 开发者放在我心中的一个高位，我确实认为他们可能仍然比我聪明得多，但我想：“构建芯片的硬件工程师，然后构建驱动程序的工程师，他们的工作肯定比我的难得多，他们一定非常优秀。”我们在 **Slack** 有一个bug，如果你在 **Slack** 中播放 **YouTube** 视频，它就无法正常渲染，为什么？它会出现这些奇怪的伪影。

<details>
<summary>Original English</summary>

**Felix**: I think the wild thing is that like as engineers we so often sort of assume that the platform like the layer below us is like super stable and then you talk to those people and they're like we're also just like guessing. Um uh and I had like a distinct moment at Slack where one of our customers at Sack was Nvidia and for a while I really put GPU developers on this pedestal in my head and I do think they're still probably much smarter than I am but I was like hardware engineers who built the chips who then like built the drivers their work must be so much harder than mine they must be very good and we had like one bug in Slack where like if you had a YouTube video in Slack it wouldn't quite render why like it would have these weird artifacts

</details>

**Felix**: 嗯，那最终是一个 **Chromium** bug，我最终进入了这个巨大的讨论串。所以我看到了很多源代码，他们也只是说：“通常会这样做。我们不知道这为什么奇怪，但如果你翻转这个位，事情就奏效了。”你知道，这只是发生在堆栈的每一层。也许，嗯，你知道，年底的 **AGI** 预测是 **Claude** 可以构建 **Chromium**。

<details>
<summary>Original English</summary>

**Felix**: And um that ended up being a chromium bug and I ended up on this like giant thread. So I got to see a lot of the source code and they also are just like common to do. We don't know why this is weird but if you flip this bit things work you know this is just like happening at every layer of the stack. Maybe the uh you know the the end of year AGI prediction is that Claude can build chromium.

</details>

**Swixs**: 你看，你现在笑了，但你知道，总有一天……

<details>
<summary>Original English</summary>

**Swixs**: You see you see you laugh now but like you know someday

</details>

**Felix**: 它开始变得相当不错，它以前完全没用。嗯，主要是被 **Chromium** 仓库中高度专业化的工具所淹没，就像长期以来，**Chromat** 会重新发明所有工具，因为它们都无法处理 **Chrome**。我认为我正在等待的 **AGI** 时刻是，我们什么时候会说 **Electron** 可能不再必要，因为你可以用 **Swift** 构建完全原生的应用程序。是的。就像不仅仅是 **Swift**，因为这是其中一件事，如果你……我认为我们目前的模型能够很好地将 **Electron** 应用程序复制到 **Swift** 中，它们是否能够构建一个实际上性能更好、内存占用更少的应用程序？所有这些东西，嗯，都会进入开发者长期以来所做的同样超优化。我们还没有完全达到那个阶段，我甚至不能指望我们最好的模型指向一个东西，然后说：“只需在原生代码中复制这个，不要犯任何错误，超级思考。”对，我们还没有完全达到那个阶段。嗯，**Ultra Think** 今天又回来了。是的。

<details>
<summary>Original English</summary>

**Felix**: it's it's starting to get pretty good like it used to be completely useless. um mostly just like overwhelmed both with how hyper specialized tools are inside the chromium repo like for for a long time that Chromat would like sort of reinvent all the tools because none of them were capable of handling Chrome. I think the EGI moment I'm kind of waiting for is at what point are we going to say Electron is probably no longer necessary because you can just build fully native apps in Swifty. Yeah. like not just in Swift because this is one thing like it's pretty easy if you I think our current models are quite capable of taking an Electron app and replicating it swift are they going to be capable of like building an app that is actually more performant uses less memory all of that stuff um is going to go into the same hyper optimization that developers have done for like a long time we're not quite there yet where I can like point even our best models at a thing and say just replicate this in native code make no mistakes ultra think right we're not quite day yet. Um, Ultra Think is back today is back. Yes.

</details>

**Swixs**: 好的。或者思考几天。这对 **Bor** 来说是相当长的时间，但他为 **Ultra Think** 工作了几天。

<details>
<summary>Original English</summary>

**Swixs**: Okay. Or thing for like days. This a pretty long time for Bor, but he worked on Ultra Think for days.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>

**Swixs**: 为什么？只是一个提示。

<details>
<summary>Original English</summary>

**Swixs**: Why? Just it's just a prompt.

</details>

**Felix**: 更多的是……是的。好的。

<details>
<summary>Original English</summary>

**Felix**: more goes into Yeah. Okay.

</details>

### Cowork的多人模式与Anthropic Labs

**Alessio**: 我还有另一个问题，那就是 **Cowork**。所以，如果我有我的 **Cloud Cowork**，它的多人模式是什么样的？我认为子代理就像单人游戏，分割上下文。

<details>
<summary>Original English</summary>

**Alessio**: Another question I had is like co-works. So, if I have my cloud co-work like what's kind of like the multiplayer mode? I think sub aents is like single player split up the context.

</details>

**Felix**: 是的。**Cowork** 的多人模式是，我的同事机器上有一些文件我想知道，或者我想知道他们的任务将如何更新我的东西。这有趣吗？这是否是你觉得有意义去构建的东西，或者说，这对我来说超级有趣。它几乎回到了脚手架的一些方面，我想：“好吧，我们最终会构建那些最终会消失的脚手架吗？”我这里有一个问题是，我们什么时候会给这些东西分配它们自己的 **Gmail** 账户？我们只是给它们它们的 **Slack** 句柄，然后它们就会像我们人类互动一样使用相同的工具。你提到了我们的财务人员。他们一直在努力进行非常好的办公集成。我认为有一段时间我们，我们围绕 **Claude** 构建了这么多技术，让它在 **Google Docs** 中留下有用的评论，现在它只是这样做，它只是在你的 **Google Docs** 中留下评论，这就是你与它互动的方式。也许就像类似的事情，我仍然对最佳互动模式有疑问。我们是否应该为 **Cowork** 代理相互交流构建一些超级定制的东西？还是说，我们应该直接跳到终点线，说：“我们只是给这个东西，如果你在工作中使用 **Slack**，我们只是给它一个 **Slack** 句柄，那就是它具备多人能力的方式。”

<details>
<summary>Original English</summary>

**Felix**: Yeah. And the multiplayer cowork is like my colleague has some file on their machine that I want to know about or I want to know how their task is going to then update my thing. Like is that interesting? Is that something that makes sense for you to build or for like it's like super interesting to me? It it almost goes back to like some of the scaffolding where I'm like okay are we going to be end up are we will we end up building scaffolding that will just go away? And like a question I have here is at what point do we just assign these things like their own Gmail account. We just give them their like Slack handle and then they will just like use the same tools we humans use to interact with each other. You mentioned our finance people. They've been working pretty hard on very good office integrations. And I think for a while we like we built so much tech around Claude leaving useful comments inside a Google doc and now it just does it just like leaves a comment in your Google doc and that's how you interact with it. Maybe like the similar thing where I still have open questions around what is the best interaction mode. Is it for us to build something super custom for co-work agents to talk to each other? Or is it okay, let's just jump straight to the finish line and say we we're just going to give this thing if you use Slack at work, we're just going to give this thing a Slack handle and that's going to be the way it's like multiplayer capable.

</details>

**Swixs**: 它们相互交流。是的。就像，你知道，作为一个有趣的项目，我构建了一个叫做 **Pi Q** 的东西，它基本上获取任何仓库和 **Pi** 代理编码代理，将其放入 **VPS** 中，然后有一个公共的 **webhook**，任何人都可以提交编码任务。

<details>
<summary>Original English</summary>

**Swixs**: They communicate with each other. Yeah. like you know as as a fun project I built this thing called pi q which basically takes any repo and the pi agent coding agent it puts it in a VPS and then there's a public web hook where anybody can submit a coding task

</details>

**Swixs**: 然后有一个仪表盘，你可以在其中审查任务。

<details>
<summary>Original English</summary>

**Swixs**: and then there's a dashboard in which you review the task

</details>

**Alessio**: **Pi Pi**。

<details>
<summary>Original English</summary>

**Alessio**: pi pi

</details>

**Swixs**: **Q**。

<details>
<summary>Original English</summary>

**Swixs**: q

</details>

**Swixs**: 是的，你基本上会得到所有这些任务，任何人都可以提交任务。

<details>
<summary>Original English</summary>

**Swixs**: yeah you basically get all these like tasks anybody can submit a task

</details>

**Swixs**: 对我来说，这几乎就像在未来的组织中，销售人员与工程团队对话，工程团队与营销团队对话，与产品团队对话，所有这些 **Cowork** 都将为其他人排队等待批准决策。

<details>
<summary>Original English</summary>

**Swixs**: and to me it's almost Like in the organization of the future, it's like the sales people are talking to the engineering team that is talking to the marketing team to the product team and all these co-work are going to like ceue up decisions for other people to approve in a way.

</details>

**Swixs**: 是的。你知道，我很好奇那会是什么样子，以及我如何让我的同事能够在不问我的情况下构建已批准的任务？是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. you know, and I'm kind of curious what that looks like and like how do you how do I give my coworker the ability to build approved task without asking me? Yeah.

</details>

**Swixs**: 以及如何决定我需要审查哪一个，你知道，因为对于其中一些事情，就像，你知道，你想改变颜色之类的。那有点像一个品牌决策。或者另一个是，嘿，你的东西坏了。

<details>
<summary>Original English</summary>

**Swixs**: And how to decide which one I need to review, you know, because for some of these things it's like, you know, you want to change the color or something. That's kind of like a branding decision. Or another one is like, hey, your thing is just broken.

</details>

**Swixs**: 这就像，这就是你修复它的方式。**Claude** 实际上可以审查该提示是否与它试图做的事情匹配。今天所有事情仍然非常，就像单人游戏中的多人游戏，你知道，我可以启动很多个。

<details>
<summary>Original English</summary>

**Swixs**: It's like this is like how you fix it. And Claude can actually review whether or not that prompt matches what it's trying to do. Today everything is still very it's like multiplayer within the single player you know I get spin up many of them

</details>

**Swixs**: 但我如何让多个人使用他们各自的上下文相互移交东西呢？

<details>
<summary>Original English</summary>

**Swixs**: but like how do I get multiple people to hand off to each other things using their particular context

</details>

**Felix**: 是的，让你的两个同事相互交流，对吧？

<details>
<summary>Original English</summary>

**Felix**: yeah and for both of your co-workers to like talk to each other right

</details>

**Swixs**: 对。是的。嘿，我们今天有一集，你能，你知道吗？

<details>
<summary>Original English</summary>

**Swixs**: right yeah hey we got an episode today can you like have you you know or

</details>

**Felix**: 是的，这就像，嗯，我知道我们时间不多了，但我们之前谈过分享技能，我确实有这个问题，如果你的 **Cowork** 只是问其他 **Cowork** 它们是否有完成这个任务的技能，那会怎么样？它不会，对吧？就像，好的，所以技能转移。

<details>
<summary>Original English</summary>

**Felix**: yeah this is like a uh I know we're like running out of time here but like we we previously talked about sharing skills and I did have this question of like what if your co-work would just like ask the other co-workers if they have a skill for this task. doesn't too, right? Like, okay, so skill transfer.

</details>

**Felix**: 是的。就像，嗯，再说一次，这可能又回到了构建非常强大的东西和构建令人毛骨悚然的东西常常是并行的领域。嗯，因为我从我的同事工程师的反应中可以看出，这可能不是我们要做的，但我们有 **Bluetooth LE**，对吧？就像我，这台电脑可以发现它正坐在另一台电脑旁边。所以你可能正在做同样的事情。

<details>
<summary>Original English</summary>

**Felix**: Yeah. Like, um, and again, this maybe this maybe goes back into the territory of like building something very powerful and building something creepy often goes hand in hand. Um, because I could tell from the reaction that my fellow engineers had that this is probably not what we're going to do, but like we have Bluetooth LE, right? Like I this computer can figure out that it's sitting right next to this computer. So, you're probably working on the same thing.

</details>

**Felix**: 嗯，你会在 **Cowork** 中看到吗？可能不会。但是，嗯，我认为有很多我们尚未尝试过的真正有创意的解决方案。

<details>
<summary>Original English</summary>

**Felix**: Um, will you see that in co-work? probably not. But um there's like I think really creative solutions to problems that we really haven't tried yet.

</details>

**Swixs**: 是的。是的。是的。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Yeah. Yeah.

</details>

**Alessio**: 太棒了。我想最后一点是 **Anthropic Labs**。嗯，我总是有一个模型实验室与代理实验室的心智模型。这基本上是 **Anthropic** 内部的代理实验室，**Cloud Code** 现在就在其之下，对吧？它是整个组织的一部分。

<details>
<summary>Original English</summary>

**Alessio**: Excellent. I guess the the last thing is en anthropic labs. Uh I always have this mental model of a model lab versus agent lab. And this is basically anthropics internal agent lab which cloud code uh is now under right. It's part of the whole org.

</details>

**Felix**: 我的意思是，人们是如此灵活，对吧？就像……

<details>
<summary>Original English</summary>

**Felix**: I mean people are so funible right like

</details>

**Alessio**: 好的，这只是，我不知道这有多真实。我不知道。

<details>
<summary>Original English</summary>

**Alessio**: okay this is just I don't know how I don't know how real this is. I don't know.

</details>

**Felix**: 不，这是一个真实的团队。这是一个团队。嗯，实验室团队主要致力于你尚未公开看到的东西。嗯，他们正在尝试一些非常疯狂、看起来不太可能实现的想法。嗯，疯狂的科学，但你，你，你正式属于这个东西吗？

<details>
<summary>Original English</summary>

**Felix**: No it's a real team. It's a team. Um the the last team is primarily working though on things that you don't see in public yet. Um they're trying like really wild out there ideas that seem quite improbable. Um the mad science but you you're are you officially under this thing or

</details>

**Felix**: 不，我们是 **Cloud Code**。**Cloud Code** 现在是一个相当大的团队，我实际上不知道我们有多少人。就像我记得昨天参加我们的每周同期会议时，我就想：“哇，这里有很多人。”嗯，但我们仍然有一个实验室团队，我们实际上扩大了实验室团队的规模。**Mike** 刚刚作为 **IC** 加入了实验室团队，我认为这非常酷，也很有趣，但他们正在研究你尚未看到的东西，这些东西非常超前，而且可能有一半是坏的，对吧？就像实验室团队的想法是，它应该只研究那些对其他人来说毫无意义的东西。

<details>
<summary>Original English</summary>

**Felix**: No, we're we're cloud code is now cloud code is like a fairly big group where I don't actually know how many people we are like I remember yesterday coming into our weekly cohort meeting. I was like woo this is there a lot of people here. Um, but we still have a lab team and we actually made the lab team a lot bigger. Mike just joined the labs team as a as an IC, which I think is very cool and very fun, but they're they're working on things that you have not seen yet that are extremely out there and probably half broken, right? Like the sort of the idea of a lab stream is that it should only work on things that make really no sense for anyone else to work on.

</details>

**Alessio**: 好的。那么，期待那里会有令人兴奋的事情，但非常感谢。我知道我们时间不多了，但是，嗯，感谢你的加入。我感谢 **Cloud Cowork**。大家快去使用它。嗯，它是我今年感受到的最接近 **AGI** 的东西。

<details>
<summary>Original English</summary>

**Alessio**: Okay. Well, looking for exciting things from there, but thank you so much. I know we're out of time, but uh appreciate you're joining us. I appreciate Cloud Co-work. Everyone go use it. Uh, it is the closest I've felt to hi this year.

</details>

**Felix**: 你这么说真是太好了。非常感谢。

<details>
<summary>Original English</summary>

**Felix**: That's so nice of you to say. Thank you very much.

</details>

**Swixs**: 是的。谢谢你的时间。

<details>
<summary>Original English</summary>

**Swixs**: Yeah. Thank you for your time.

</details>

**Felix**: 是的。

<details>
<summary>Original English</summary>

**Felix**: Yeah.

</details>