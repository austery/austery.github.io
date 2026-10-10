---
author: AI Engineer
date: '2026-04-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=cVzf49yg0D8
speaker: AI Engineer
tags:
  - api-design
  - conversational-ai
  - agent-frameworks
  - real-time-interaction
  - developer-experience
title: 构建对话代理：Google Gemini API与AI Studio实践
summary: 本访谈记录了Google DeepMind团队关于Gemini API和Google AI Studio的开发者研讨会内容。重点介绍了Gemini Interactions API（一个用于模型和代理的统一API）及其服务器端状态管理、异步执行和隐式缓存等特性。演示了如何构建一个包含文件读写和Bash命令执行的编码代理，并探讨了Gemini 3.1 Flash Life API在实时音视频交互、多语言支持及实际商业应用（如Shopify Sidekick和为老年人提供陪伴服务）中的潜力与挑战，包括延迟、上下文窗口限制和幻觉问题。强调了通过系统指令和合作伙伴集成来优化代理性能的重要性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
  - Google
  - OpenAI
  - Shopify
  - Whimo
  - Hey Ado
  - Lifekit
  - Pipecat
  - Software Mentioners
  - Vox Implant
  - Nvidia
products_models:
  - Gemini API
  - Google AI Studio
  - Gemini Interactions API
  - Gemini 3.1 Flash Life
  - Gemini 1.5
  - Nano Banana
  - LIA 3
  - ChatGPT
  - Meta Rayban
  - Parakeet
media_books:
  - Harry Potter
  - BBC Radio One
status: evergreen
---
### 欢迎与多语言介绍

**Thor**: 大家好。

<details>
<summary>Original English</summary>

**Thor**: Hello everyone.

</details>

**提问者**: 你好。

<details>
<summary>Original English</summary>

**提问者**: Hello.

</details>

**Thor**: 很好。

<details>
<summary>Original English</summary>

**Thor**: Perfect.

</details>

**Thor**: 只是菲利普和我都是德国人，我们觉得这很有趣。也许我们可以在德语中做到这一点。实际上，看起来那里有一个德国团队，这很好。嗯，不用担心。我们会在英语中做到这一点。我们会在几种不同的语言中做到这一点。也许我们会发现。房间里还有其他语言吗？

<details>
<summary>Original English</summary>

**Thor**: It's just that Philip and I were both Germans and we thought it was funny. Maybe we we can do it in German. Actually, looks like there's a there's a German crew there, which is nice. Uh, no, no worries. We'll we'll we'll do it in English. We'll do it in a couple different languages. Maybe we'll find out. Do we have other languages in the room?

</details>

**提问者**: 其他国籍吗？是的。我们有什么？

<details>
<summary>Original English</summary>

**提问者**: Other nationalities? Yeah. What do we have?

</details>

**Thor**: 大声说出来。

<details>
<summary>Original English</summary>

**Thor**: Shout it out.

</details>

**提问者**: 那么，西班牙语。

<details>
<summary>Original English</summary>

**提问者**: So, Spanish.

</details>

**提问者**: 有冰岛语吗？

<details>
<summary>Original English</summary>

**提问者**: Any Icelandic?

</details>

**提问者**: 没有。

<details>
<summary>Original English</summary>

**提问者**: No.

</details>

**提问者**: 德语。好吧。接近。接近。罗马尼亚语。

<details>
<summary>Original English</summary>

**提问者**: D. Okay. Close. Close. Romanian.

</details>

**提问者**: 罗马尼亚语。不错。

<details>
<summary>Original English</summary>

**提问者**: Romanian. Nice.

</details>

**提问者**: 荷兰语。嗯，荷兰。

<details>
<summary>Original English</summary>

**提问者**: Dutch. Pña. Netherlands.

</details>

**提问者**: 好的。

<details>
<summary>Original English</summary>

**提问者**: Okay.

</details>

**提问者**: 哪个？

<details>
<summary>Original English</summary>

**提问者**: Which?

</details>

**提问者**: 印地语。

<details>
<summary>Original English</summary>

**提質問者**: Hindu.

</details>

**提问者**: 是的。但是印地语。好的。加拿大。不。好的。班加罗尔。不。

<details>
<summary>Original English</summary>

**提问者**: Yeah. But Hindu. Okay. Canada. No. Okay. Bangalore. No.

</details>

**提问者**: 嗯。

<details>
<summary>Original English</summary>

**提问者**: Uh,

</details>

**提问者**: 波斯语。很好。不错。

<details>
<summary>Original English</summary>

**提问者**: Farsy. All right. Nice.

</details>

**提问者**: 捷克语。

<details>
<summary>Original English</summary>

**提问者**: Czech.

</details>

**提问者**: 捷克语。是的。太棒了。好的。这真是太棒了。谢谢大家带着你们所有的语言来到这里。真的非常感谢。我们今天可以真正考验一下模型，这很棒。嗯，大家好，我是 Thor，或者对你们这些德国人来说是 Thor。嗯。

<details>
<summary>Original English</summary>

**提问者**: Czech. Yeah. Brilliant. Okay. This is uh fantastic. Well, thanks everyone for making your way over here with with all your languages. Really appreciate it. we can we can really put the model to the test today which is great. Um yeah, hi I'm Thor or to for the German speakers amongst you. Um

</details>

**Philip**: 大家好，我是 Philip，就叫 Philip。

<details>
<summary>Original English</summary>

**Philip**: hi I'm Philip um only Philillip so

</details>

**Thor**: 对于德国和英语使用者来说。是的，这很好。我们，我们都在 Google DeepMind 致力于**开发者体验**，广泛涵盖了 **Gemini API**，并且也致力于 **Google AI Studio**，作为一个工具，让开发者快速试用模型，然后还有 **API** 接口来使用 API。你需要一个 **API key**。实际上，谁已经有了 **API key**？**Gemini API**。好的，几个人。谁以前用过 **AI Studio**？**Google AI Studio**。好的，几个人。很棒。嗯，也许我们可以很快地，抱歉。

<details>
<summary>Original English</summary>

**Thor**: for German and English speakers. Yeah, it's nice. We so we work on the developer experience at Google DeepMind broadly covering kind of Gemini API and also uh working on Google AI Studio as a tool for you know developers to try out the models quickly uh and then also the the API um interfaces to use the API. You do need an API key. Uh actually who has an API key already? Gemini API. Okay, couple folks. Uh, who has used AI Studio before? Google AI Studio. Okay, couple folks. Great. Um, maybe we can quickly Sorry,

</details>

**提问者**: **anti-gravity**。

<details>
<summary>Original English</summary>

**提问者**: anti-gravity.

</details>

**Thor**: 是的，这很好。嗯，实际上你不需要 **API key** 来使用 **anti-gravity**，但是，嗯，所以如果你还没有 **API key**，如果你带着你的电脑，我希望你带了。嗯，这是一个动手实践的研讨会。我道歉，他们把你们的桌子拿走了。嗯，所以这是一个非常笔记本电脑的情况。嗯，字面上就是笔记本电脑。嗯，我希望你没有带你的 Mac Mini 或其他什么。嗯，所以是的，如果你去 **AI.dev**。嗯，我的意思是你可以去 **AI Studio**。你可以去 aistudio.com，但是我们为 **AI.dev** 花了很多钱，所以请使用它。嗯，它只是重定向到 **AI Studio**。但是嗯。

<details>
<summary>Original English</summary>

**Thor**: Yeah, that's good. Uh, you actually don't need an API key for anti-gravity, but um, so if you don't have an API key yet, uh, if you have your machine on you, I hope you do. Uh, it's it's it's a hands-on workshop. I do apologize. They took away your tables. Um, so it's a very laptop situation. Uh, like literally, uh, laptop. Um, I hope you didn't bring your Mac Mini or whatever. Uh, but so yes, if you just go to ai.dev. Um, and I mean there's you can also go to ai.studio. You can go to aistudio.com, but we paid a lot of money for AI.dev, so please use that. Uh it just it just redirects to AI studio. But um

</details>

**提问者**: 让我。

<details>
<summary>Original English</summary>

**提问者**: let me

</details>

**提问者**: 所以 **AI.dev**，**API key**。

<details>
<summary>Original English</summary>

**提问者**: so AI.dev API key.

</details>

**Thor**: 嗯，是的，或者在左下角有一个“获取 **API key**”，然后 **API Keys** 就是你。

<details>
<summary>Original English</summary>

**Thor**: Uh yes or on the corner left side there's a get API key and then API- keys is where you

</details>

**提问者**: 德语。

<details>
<summary>Original English</summary>

**提問者**: German.

</details>

**Thor**: 嗯，是的，这是我的个人账户，我们无法更改语言。所以，嗯，你只需要一个 Google 账户。所以不需要信用卡，什么都不需要。我们要做的一切都属于免费套餐。所以如果你去 **AI Studio** 或 **AI.dev**，那里有一些登录表格，你可以像使用你的 **Gmail** 一样。不用担心，我们不会向你收费。然后，在 **API Keys** 上，你通常会在右上角找到一个叫做“创建 **API key**”或“创建 **API key**”的东西，当你第一次做的时候，你可能需要，对我来说也类似，我可以导入我的项目，或者我可以创建我的项目。我可以直接点击创建，给它任何名字。我的意思是，我们可以称之为 AI Workshop，然后创建项目。我可以把它翻译成英语。好的，需要几秒钟，然后你应该能够创建密钥，这个密钥将用于我们稍后要做或使用的演示或动手操作。等等，它显示了 **API key**。

<details>
<summary>Original English</summary>

**Thor**: Uh yeah it's it's my personal account and we cannot change language. So uh you need only a Google account. So no credit card, no nothing. All of the things we are going to do is part of the free tier. So if you go to AI studio or AI.dev and there's some like signin form you can like just use your Gmail. No worries we will not charge you. Uh and then on API keys uh you find at the top right corner normally something called API key create or create API key uh and when you do it for the first time you uh might need so similar for me uh I can import my projects or I can create my projects. I can just click create give it any name. I mean we can call it uh I I workshop uh and then create project I can translate it to English. Okay, takes a few seconds and then you should be able to create key and this key will be used for the demos or the hands-on things we are going to do use later. Wait, it shows the API key.

</details>

**Philip**: 是的，我会删除它。所以不要复制它。但是你可以。

<details>
<summary>Original English</summary>

**Philip**: Yeah, I will delete it. So don't don't copy it. But you can like

</details>

**提问者**: 复制得很快。

<details>
<summary>Original English</summary>

**提问者**: copy very fast.

</details>

**Thor**: 你可以使用那个密钥。你可以把它放到你的 bash RC 或 set HRC 文件中，或者稍后你可以直接内联它。随你喜欢。如果你有，你可以使用这个。既然我们还有几分钟时间，我们真的想确保所有想跟着做的人，慢慢来，创建你的 **API key**。如果出现错误或有其他问题，请随时举手，我们会过来帮助你。然后。

<details>
<summary>Original English</summary>

**Thor**: You can use that key. You can like put it into your bash RC or set HRC file or later you can like directly inline it. Whatever you prefer. If you have one, you can use this one. And since we have a few more minutes time, we really want to make sure everyone who wants to follow along, take your time, create your API key. If there's an error appearing or something else is not working, feel free to raise your hand to will come to you and we'll help you. And

</details>

**Philip**: 是的，只是提醒一下，这是一个秘密的 **API key**。

<details>
<summary>Original English</summary>

**Philip**: and yeah, just a reminder, it is a secret API key.

</details>

**提问者**: 所以不要做 Philip 在那里做的事情。

<details>
<summary>Original English</summary>

**提问者**: So don't do what Philip is doing there.

</details>

**Philip**: 这就是我再次删除我的密钥的原因。

<details>
<summary>Original English</summary>

**Philip**: This is why I delete my key again.

</details>

**Thor**: 是的。所以我们经常遇到人们泄露他们的 **API key**。通常是 Claude code 正在将他们的 **API key** 推送到 **GitHub**。所以我建议你不要这样做。不，开玩笑的。记住这是一个秘密的 **API key**。嗯，所以把它当成秘密。嗯，不要和你的邻居分享，你知道。

<details>
<summary>Original English</summary>

**Thor**: Yes. So we do get that a lot that people um leak their API keys. Mostly it's clock code that is like pushing their API keys to to to GitHub. So I recommend you don't do that. No, just just kidding. Just remember it is a secret API key. Um, so treat it like a secret. Uh, don't share it with your neighbor, you know.

</details>

**Philip**: 嗯，但是是的，现在就创建那个 **API key**。我们会给你几分钟时间来做。在你做的时候，或者，你知道，一旦你完成了 **API key** 的创建，我很乐意让你，你知道，简单介绍一下自己，如果你愿意的话，然后告诉我们你希望从研讨会中得到什么。也许你正在处理一个特定的用例。嗯，是的，我们很乐意了解你们所有人。所以当你们创建 **API key** 的时候，嗯，如果你愿意，请随意说出你的名字或昵称，嗯，以及你正在做什么，你希望从研讨会中得到什么。是的，和 **Raol** 一起，来自周四播客，为 **Koreas** 工作。

<details>
<summary>Original English</summary>

**Philip**: Um, but yeah, do create that API key now. And we'll give you a couple minutes to do that. And while you do that or, you know, once you finished creating your API key, I'd love for you, you know, to just briefly introduce yourself if you want to and just sort of, you know, let us know what you would like to get out of the workshop. Maybe there's a specific use case you're working on. Um, yeah, we'd love to kind of get to know you all a little bit as well. So while you create your API keys uh if you want to feel free to just you know shout out uh your name or nickname uh and sort of what you're working on what you would like to get out of the workshop. Yeah, with Raol from the Thursday podcast working for Koreas

</details>

**Raol**: 我是 **Gemma 4** 和 **Gemini** 的忠实粉丝。我是少数几个将其用于编码等方面的人，嗯，我还在课堂上运行它。

<details>
<summary>Original English</summary>

**Raol**: and big fan of Gemma. Yeah, Gemma 4 and Gemini. I'm one of the few who are using it for coding and stuff as well by H& um I'm also running it on the classes actually.

</details>

**Thor**: 哦，不错。

<details>
<summary>Original English</summary>

**Thor**: Oh, nice.

</details>

**Raol**: 我想看到更多这样的东西，你知道。

<details>
<summary>Original English</summary>

**Raol**: And I want to see more of this, you know.

</details>

**Thor**: 好的。

<details>
<summary>Original English</summary>

**Thor**: Okay.

</details>

**Raol**: 我想要 Google 课堂。

<details>
<summary>Original English</summary>

**Raol**: And I want Google classes.

</details>

**Thor**: 好的。是的。我们，我们看看能否在研讨会结束时拿到眼镜。抱歉。是的。如果你右边有座位，你能跳进来吗？这样我们就可以填满这边。这样更容易被留下。

<details>
<summary>Original English</summary>

**Thor**: Okay. Yeah. We'll we'll see if we can get to the glasses by the end of the workshop. Sorry. Yeah. If you have a seat to your right, can you jump in so we can fill up on the side here? Makes it easier to be left.

</details>

**Philip**: 当我们等待的时候，嗯，我们在 **Chrome** 上推出了一些很酷的东西，我还没有激活它，但是当你进入你的标签栏，点击右键，你现在可以将标签移动到侧面。我们现在有**垂直标签**。所以。

<details>
<summary>Original English</summary>

**Philip**: And while we are waiting, uh, we launched something cool on Chrome, which I haven't activated it, but when you go on your tap bar, click right, you can now move tabs to the side. And we have vertical tabs now. So,

</details>

**Thor**: 太棒了。所以，更多的屏幕。这很好。

<details>
<summary>Original English</summary>

**Thor**: yay. So, more screen. That's good.

</details>

**Philip**: 不错。好的，酷。所以。

<details>
<summary>Original English</summary>

**Philip**: Nice. Okay, cool. So

</details>

**Thor**: 眼镜。你在，你在，你在运行什么？你在眼镜上运行什么？嗯，技术上是在手机上，对吧？你使用哪种软件进行开放式的**抓取**。

<details>
<summary>Original English</summary>

**Thor**: glasses are you are you are you running what are you running on the glasses well technically on the phone right software where you use which calls open clawization for

</details>

**Raol**: 两个。

<details>
<summary>Original English</summary>

**Raol**: two

</details>

**Thor**: 然后它只是通过手机上的 websocket 使用 **Gemini live**，对吧？是的，不错，是的，那很酷。是的，**vision claw**，如果你没听说过的话，嗯，一个非常有趣的开源项目。嗯，我想你可以在，嗯，现在 Meta 已经为 **Meta Rayban** 打开了 SDK，你可以将 **Gemini Life API** 这样的东西连接到眼镜上。嗯，眼镜连接到你的手机，然后手机实际上连接到 **Gemini Life**，这很酷。

<details>
<summary>Original English</summary>

**Thor**: and then that's just using Gemini live kind of through the websocket on the phone right yeah nice yeah that's cool yeah vision claw if you haven't heard of that uh pretty pretty fun open source project um and I think you can run it uh sort of on the well now that Meta has opened up the SDK for the the Meta Rayban uh you can actually hook in something like Gemini Life API uh into the glasses. Well, the glasses connect to your phone and then the phone actually connects to Gemini Life which is cool

</details>

**Philip**: 但是嗯，它显示了什么将是可能的。

<details>
<summary>Original English</summary>

**Philip**: but uh it shows what will be possible.

</details>

**Thor**: 是的。不错。创建 **API key** 有问题吗？

<details>
<summary>Original English</summary>

**Thor**: Yeah. Nice. Any problems creating API keys?

</details>

**Thor**: 每个人都有 **API key** 吗？我们需要检查一下吗？

<details>
<summary>Original English</summary>

**Thor**: Everyone has an API key. Should we check?

</details>

**Thor**: 好的。嗯，还有其他人吗？有什么具体的吗？是的。

<details>
<summary>Original English</summary>

**Thor**: Okay. Uh, anyone else? Anything specific that Yeah,

</details>

**Michael**: **Michael** 在苏黎世为 **Get Your Guide** 工作。嗯，我们正在构建我们的第一个 **AI** 客户支持代理。所以。

<details>
<summary>Original English</summary>

**Michael**: Michael work for Get Your Guide in Zurich. Um, we're building like our first kind of AI customer support agent. So,

</details>

**Thor**: 酷。

<details>
<summary>Original English</summary>

**Thor**: cool.

</details>

**Michael**: 只是有兴趣了解你们通常是怎么做的，进行比较。

<details>
<summary>Original English</summary>

**Michael**: Just interested to think in the general how you guys are doing it, comparing.

</details>

**Thor**: 好的，酷。

<details>
<summary>Original English</summary>

**Thor**: Okay, cool.

</details>

**Philip**: 不错。

<details>
<summary>Original English</summary>

**Philip**: Nice.

</details>

**Thor**: 最后一次机会。还有其他人吗？

<details>
<summary>Original English</summary>

**Thor**: Last chance. Anyone else?

</details>

**提问者**: 好的。

<details>
<summary>Original English</summary>

**提问者**: Okay.

</details>

**Thor**: 好的。所以。

<details>
<summary>Original English</summary>

**Thor**: All right. So

</details>

### Gemini Interactions API 介绍

**Thor**: 在我们进入动手环节之前，我们可以开始。我大概有 10-15 分钟的幻灯片，嗯，来介绍一下我们接下来要用什么来构建第一个会话，我将更多地关注如何构建一个没有任何实时音频输入的代理，之后 Thor 会接手，然后我们将构建一些非常棒的**对话代理**。那么，你们中有谁以前用过 **Gemini API** 来调用 **Gemini** 呢？有一些人。你们中有谁用过 **Interactions API** 呢？

<details>
<summary>Original English</summary>

**Thor**: we can start before we go into the hands-on session. We I have like 10 15 minutes slides um to give a bit of a background what we are going to use to build the first session which I'm going to do is more on like the building an agent without any live audio input that's where to take over later and then we are going to building some very nice conversational agents. So um who of you has used the Gemini API to make an API call to Gemini before? That's a few. Have anyone of you used the Interactions API?

</details>

**Thor**: 一个。好的。两个。好的。至少有一些人。所以 **Interactions API** 是我们在 12 月份推出的一个新 API，目前还在测试版，希望很快就能成功生成内容。它是一个统一的 API，可以与模型和代理一起使用，而且它更符合我所说的行业标准。所以它更接近你们从开放模型（例如 **chat completions API**）或 **Entropic** 或 **OpenAI** 熟悉的东西。嗯，我们要做的是幻灯片，然后我们构建一个**编码代理**，就像一个小的 Claude code 一样，可以读取文件、写入文件、运行 Bash 命令，然后我们最后有一些时间可以提问，然后我们短暂休息一下，上厕所、喝水，然后 Thor 会继续。我们都有一个 **API key**。

<details>
<summary>Original English</summary>

**Thor**: One. Okay. Two. Okay. At least some person. So the Interactions API is a new API we launched in December and beta which hopefully will succeed generate content soon. It's a unified API to use with models uh with agents and is much more aligned with I would say the industry. So much closer to what you are familiar with from open models with the chat completions API or from entropic or from open AI. Um and what we are going to do the slides then we build a coding agent like a small little clot code with reading running uh reading files writing files running bash commands and then we have some time at the end if you have questions around it and then we do a short break toilet drinks and then tour will continue. We all have an API key.

</details>

**Thor**: 所以正如我所说，我们想要构建一个适用于模型和代理的 API。当我们推出 **Interactions API** 时，我们也推出了 **Deep Research**。所以也许你已经在 **ChatGPT** 或 **Gemini** 应用程序中使用了 **Deep Research**，你基本上是发起一个查询，然后你得到一个计划，然后模型会进行 10-15 分钟的深入研究，访问数百个网站，嗯，API 支持模型和代理，而且在它们之间切换非常简单。你基本上要么定义一个模型，可以是 Gemini free flash，要么定义你的代理，可以是 **Deep Research**，我们正在努力让你带来自己的代理或定义你自己的代理，你可以自定义所有这些行为，而且界面是相同的。所以我们稍后会看到，但是当你向 **Nano Banana** 发送请求以生成图像时，你可以将这些交互链接到一个 flash 模型来做其他事情，链接到 **Lura** 来生成音频，嗯，或者甚至希望很快能链接到 **Vo** 来生成视频，而且界面与你从 **OpenI** 看到的非常相似。所以我们现在有这些内容块。所以你提供的每个输入和输出都是相同的类型。它有一个类型字段，可以是函数调用、思维签名、文本、音频、视频、图像，这有望让你更容易使用 **Gemini API** 进行构建，而且它不那么**谷歌品牌化**，不那么**协议特定**，不那么 **gRPC**，以便让开发者更容易构建。

<details>
<summary>Original English</summary>

**Thor**: So as I said, we want to build an API which works for both models and agents. And when we launch the Interactions API, we also launch Deep Research. So maybe you have used Deep Research in chat GPT or in the Gemini app where you basically start off a query and then you get back a plan and then the model goes on and like does deep research for 10 15 minutes visiting hundreds of sites and um the API um supports both models and agents and it's very simple to switch between those. You basically either define a model which could be Gemini free flash flesh or you define your agents which could be deep research and we are working on it to for you to bring your own agent or to define your own agent that you can customize all of these behaviors and it's the same surface. So we'll see later, but when you send a request to Nano Banana to generate an image, you can like basically chain those interactions to a flash model to do something else to Lura to have you like generate audio and uh or even to hopefully soon uh vo to generate you u video and the interface is very similar to what you see from OpenI. So we now have like those uh content blocks basically. So every input you provide and output you provide is the same type. It has a type field which could be a function call, a thought signature, a text, audio, video, image which hopefully makes it for you easier to build with the Gemini API and it is less I would say Google branded, less protospaccific, less gRPC to make it easier for developers to build.

</details>

**Thor**: 嗯，**Interactions API** 的核心原语，除了使其更简单之外，我们还在服务器上引入了状态，我们将用它来构建我们的代理。所以我们不需要管理我们的循环并总是发送整个历史记录。非常类似于响应 API，你现在可以提供一个**之前的交互 ID**，它基本上会附加到现有的历史记录中。所以你可以发送一个新的输入。嗯，如前所述，我们有一个带有 **Deep Research** 和背景真实的代理。所以你可以开始你的研究，可以拉取它，或者嗯，很快可以使用**网络钩子**在你的研究完成后得到通知。所以你不需要保持连接开放。我们有类型块，然后我们还有与 Web 开发非常典型的**流式模式**，使用 **SSE**，这也有望让你更容易构建。我们都支持内置工具，但我们现在也支持**远程 MCP**，而且我想两周前我们推出了**工具组合**，所以你现在可以将 **Google 搜索**与你自己的自定义函数结合起来，这是人们多年来一直要求的一大功能，我想，现在你可以做到这一点。嗯，再总结一下差异，所以**生成内容**是我们今天拥有的，**Interactions API** 是我们明天将拥有的，我们将拥有**服务器端状态管理**，但你不需要使用它，所以如果你说，嘿，我想管理我的回合，我想管理我的上下文，我不信任你，或者我需要进行上下文工程，我需要删除某些部分，你可以这样做，嗯，你可以发送，它更容易发送新输入，基本上我们有内置代理，我们也有后台支持。所以你将获得**异步执行**。我们都看到，当代理发送一个提示时，可能需要 1 2 3 4 分钟才能完成，而保持 HTTP 请求或连接开放超过我所说的 10 秒并不是一个很好的做法。所以你想要使用**异步调用**来获得通知或进行**轮询**，嗯，当它完成时，它不那么**面向协议**，我真的很喜欢这一点。嗯，它更接近人们从开发者生态系统了解的东西，而且状态管理的一个副作用是 **API** 的**隐式缓存**要好得多。所以对于那些不知道什么是**隐式缓存**的人。当你向模型发送请求时，模型需要编码你所有的输入令牌。你可以缓存这些编码，以便后续请求节省成本。缓存请求我想可以为输入令牌节省 90% 的成本。当你必须自己管理状态或上下文时，你可能会删除换行符，删除某些部分，这会破坏缓存。而使用**服务器端状态**，服务器会保留上下文。因此，你的缓存命中率会高得多。我们看到今天使用 **Interactions API** 的初创公司缓存率提高了两到三倍。

<details>
<summary>Original English</summary>

**Thor**: Um, the core primitives of the Interactions API in addition to making it easier, we also introduced state on the server which will which we will use for building our agents. So we don't need to manage our loop and always send back the whole history. Very similar to uh responses API, you now have a previous interaction ID you can provide which basically attaches to the existing history. So you can like just send a new input. Um as mentioned we have an agent with Deep Research and background true. So you can start your research can pull it or um soon use web hooks to get notified when your research is done. So you don't need to keep the connection open. We have the type blocks and then also we have the same like streaming pattern very typical for web development using SSE which also makes it hopefully easier for you to build. We all support the built-in tools but we also now have support for remote MCP and I think two weeks ago we launched tool combination so you can now combine Google search with your own custom function which was one of the big features people were asking for years I think and now you can do this. Um and to summarize again the differences between so generate content is what we have today Interactions API is what we will have tomorrow we will have um serverside state management but you don't need to use it so if you say hey I want to manage my turns I want to manage my context I don't trust you or I need to do like context engineering I need to remove certain parts you can do this um you send can it's way easier to send new input basically we have the built-in agents we have also background support. So you will get asynchronous execution. We all see with agents when you send a prompt that might take 1 2 3 4 minutes to complete and keeping HTTP requests or connections open for I would say more than like 10 seconds is not a very good practice. So you want to like use asynchronous calls to either get notified or like do polling uh when it is done and it is less proto oriented which I really prefer. um it's much closer to what people know from like the the developer ecosystem and also a side effect of the state management is that the implicit caching for the API is much better. So for the one of you who don't know what is implicit caching. So when you send a request to the model, the model needs to encode all of your input tokens. And you can cach those encodings for a follow-up request to save cost. And cache requests I think are 90% cheaper for the input tokens. And when you have to manage your state or context yourself, you maybe strip out line breaks, remove um certain parts, this breaks the cache. And using the serverside state, the server keeps the context. So the chances for your cache hit rate is much higher. And we see like two to three times better cache rates from like the the startups using Interactions API today.

</details>

### 构建编码代理实践

**Thor**: 快速代码示例说明我们如何使其更简单。所以左边是**协议特定**的一次性输入部分，带有内联数据或文本，其中字段基本上描述了类型，而右边看起来几乎与其他 API 相似，我想说，所以如果你在研讨会后决定尝试一下，应该会容易得多。嗯，我想你们都知道代理大致是什么。我们有一个大脑或我们的模型，它决定要做什么。调用工具、生成文本、做其他事情。我们有工具，它基本上给我们的**大脑**提供了手和眼睛，使其能够与所处的环境互动。我们有**上下文**。它基本上是模型所知道的一切，它必须做什么，它能做什么。如果有某些偏好，如果有某些约束，然后我们有**循环**，它基本上将我们的模型与手和工具结合起来，并运行它，直到模型不再调用工具并生成文本。

<details>
<summary>Original English</summary>

**Thor**: Quick code example on what we mean with making it simpler. So on the left side you have like the very protospecific oneoff input parts with inline data or text where the the field basically describes the type and on the right side almost looks similar to other APIs. I would say so should be much easier if you decide after the workshop to give it a try. Um then I guess all of you know roughly what an agent is. We have a brain or our model which decides what it wants to do. Calling a tool generating text doing something else. We have tools which basically gives our brain hands and eyes to interact with the environment where it is in. We have the context. It's basically all of the all the model knows uh what it has to do, what it can do. if there are certain preferences, if there are certain constraints and then we have the loop which basically combines our model with hands and tools and runs it until the model no longer calls the tools and generates a text.

</details>

**Thor**: 所以，一些关于如何使用 API 的快速示例，然后我们进入有趣的动手部分。所以使用**服务器端状态**的基本聊天变得非常容易，因为我们有我们的 `interactions.create` 调用。所以我们定义我们的模型，我们定义我们的输入。“法国的首都是什么？”，我们得到输出，然后我们可以继续提供**之前的交互 ID**，然后幕后的模型或者说服务器基本上拥有我们的用户输入、我们的模型输出，然后附加新的用户输入，这样你就不需要有一个客户端的历史对象，在那里你附加用户的回合、模型的回答，然后又是用户的回合。当你构建代理时，这变得非常有用，你有一个循环，并且总是需要附加新的用户输入，嗯，如前所述，这也适用于代理和模型。所以我们真的想构建这个统一的界面，无论你使用什么模型，你都可以继续你的对话。在这个例子中，我们基本上对 2026 年的 **AI 代理**研究运行了一个 **Deep Research** 请求。然后我们获取研究输出，并继续使用 **Nano Banana** 模型为其生成视觉效果。这基本上是四行代码，无需你了解上下文，如何提供输入，有望使其容易得多。但正如所说，你不需要这样做。所以输入字段也接受相同的数组，其中包含用户、模型和所有输入。

<details>
<summary>Original English</summary>

**Thor**: So some quick examples on how to use the API and then we go into like the the nice hands-on part. So basic chat usage with serverside state becomes very easy because we have our interactions create call. So we define our model, we define our input. What's the capital of France, we get back the output and then we can just continue providing the previous ID and the model behind the scenes or like the server behind the scenes basically has our user input, our model output and then appends the new user input that you don't need to have like a client side history object where you append the user turns, the model turns and then the user turn again. This becomes very helpful when you build agents where you have a loop and always need to append new user input and um as mentioned before that also works for agents and models. So we really want to build this unified interface where you can continue your conversations no matter what model you use. And in this example, we basically run a Deep Research request on research AI agents in 2026. And then we take the research output and just continue with the Nano Banana model to generate a visual for it. And it's like four lines of code basically without for you to what's the context, how do I provide the input and hopefully makes it a lot easier. But as said, you don't have to do it. So like the input field also accepts the same array with ro user ro model model and all of the inputs.

</details>

**Thor**: 嗯，对于两个用途，现在也希望能容易得多。我们有一个类型函数，我们的函数名称，我们想要使用描述，然后我们有模型需要生成的参数，然后这里大致是我们将要构建的内容。所以我们使用工具进行 **API** 调用，然后我们检查交互的输出是什么。`Requires action` 基本上意味着你作为客户端需要做一些事情。所以生成的输出是一些函数调用或一些对象，你需要对其做出反应。我们遍历我们的输出类型。检查函数调用。执行函数。附加结果。发送新的交互，直到模型不再决定调用函数并生成文本或其他内容。

<details>
<summary>Original English</summary>

**Thor**: Um for two use it's also hopefully now much easier. We have a type function our name for our function which we want to use describe and then we have the parameters the model needs to generate and then here's roughly what we are going to build. So we make our API call with the tools and then we check what the the output of the interaction is. Requires action basically means you as a client you need to do something. So the output generated some function call or some object which you need to react to. We iterate over our um output types. Check for the function call. Execute the function. Append the result. send a new interaction until the model no longer decides it wants to call a function and generates a text or something else.

</details>

**Thor**: 好的。嗯，上次我做研讨会时，我们都还在手动编码。所以这是我第一次做动手研讨会，至少我不再手动编写太多代码了。我不知道你是怎么做的。所以我们今天要做的是，我们不手动编码。我们将使用你喜欢的 IDE 代理 CLI。我不确定你们中有多少人正在关注，但是为了更容易，我们为我们的代理创建了代理技能。所以如果你去 **Gemini**，你可以搜索 **Gemini API Docs coding agents**。

<details>
<summary>Original English</summary>

**Thor**: Okay. Um the last time I did a workshop, we were all still coding manually. So that's my first time doing a hands-on workshop where at least I don't code much manually anymore. I'm not sure how you do it. So what we are going to do today is we don't code manually. We are going to use your preferred IDE agent CLI of choice. I'm not sure how many of you are following, but um to make it easier, we created agent skills for our agents to use. So if you go to the Gemini, you can search for Gemini API Docs coding agents.

</details>

**提问者**: 放大。

<details>
<summary>Original English</summary>

**提问者**: You zoom in.

</details>

**Thor**: 啊，是的，抱歉。当然。嗯，我也可以。你能看到吗？

<details>
<summary>Original English</summary>

**Thor**: Ah yes, sorry. Of course. Um I can also Can you see it?

</details>

**提问者**: 是的，我想你也可以直接谷歌。

<details>
<summary>Original English</summary>

**提问者**: Yeah, I think you can also just Google

</details>

**Thor**: 我的意思是，我可以。

<details>
<summary>Original English</summary>

**Thor**: I mean I can

</details>

**提问者**: 技能。

<details>
<summary>Original English</summary>

**提問者**: skills

</details>

**提问者**: **Gemini**。代理技能。

<details>
<summary>Original English</summary>

**提问者**: Gemini agent skills.

</details>

**Thor**: 好的。嗯，是的，这个应该设置为“使用 **Gemini MCPN skills** 设置你的**编码代理**”。我想那应该会把我们带到这里。

<details>
<summary>Original English</summary>

**Thor**: Okay. Um yes this one it should be des set up your coding agent with Gemini MCPN skills. I think that should bring us here

</details>

**提问者**: 结果非常不同。

<details>
<summary>Original English</summary>

**提问者**: and very different results

</details>

**Thor**: 真的吗？

<details>
<summary>Original English</summary>

**Thor**: really.

</details>

**提问者**: 是的。或者如果没有，你可以去文档，然后在“入门”部分左侧有一个“**编码代理**设置”。你成功了吗？

<details>
<summary>Original English</summary>

**提问者**: Yes. Or if not you can go to the documentation and then on the left side in the getting started section there's a coding agent setup. Are you are we successful?

</details>

**Thor**: 好的。嗯。

<details>
<summary>Original English</summary>

**Thor**: Okay. Um

</details>

**提问者**: 所以一个问题是，我们应该全局安装这个技能还是只为项目安装？

<details>
<summary>Original English</summary>

**提问者**: so one question should we install this skill globally or just for the project?

</details>

**Thor**: 你不需要全局安装它。这是一个好问题。那么你是如何安装的呢？我们有多个技能。我们有 **Gemini API** 开发技能。我们不打算使用这个。那是用于**生成内容 API**。如果你想使用那个 API，或者你熟悉它，那就用吧。但是我们有 **Gemini live API**。这就是 Thor 稍后要使用的。所以我们也不安装这个。但是我们有 **Gemini Interactions API**。在这里你可以选择第一个命令或第二个命令，这取决于你想要什么。然后像复制它，嗯，打开你的工作区，嗯，你在哪里工作。然后我已经做了，但是你可以添加命令 `npx install`，然后你应该会看到一个向导，要求你安装它。有很多预选的。

<details>
<summary>Original English</summary>

**Thor**: You can you don't need to install it globally. And that's a good question. So how do you install? So we have multiple skills. We have the Gemini API dev skill. We not going to use this one. That's for the generate content API. If you want to use that API or if you are familiar with it, go for it. But we have the the Gemini live API. That's what tour is going to use later. So we also don't install this. But then we have the Gemini Interactions API. And here you can either pick the the first command or the second command depending on what you want. And then like just copy it uh open your workspace um where you're working in. And then I already did it, but you can like add the command npx install and then you should get a wizard asking you to install it. There are many pre-selected.

</details>

**Thor**: 不要被它迷惑。这只是意味着所有这些代理都与代理文件夹兼容。所以你可能有 `agents/kills/gemini interactions API`，在那里我们有我们的技能。

<details>
<summary>Original English</summary>

**Thor**: Don't get confused by it. This just means that all of those agents are compatible with the agents folder. So you might have agents/kills/gemini interactions API and in there we have our skill.

</details>

**Thor**: 是的。我也可以。嗯，等等。所以我在 Cursor 和 **anti-gravity** 以及 **Gemini CLI** 上都测试过。所以如果你使用其中任何一个，你都可以。如果你使用 Claude code，我想它也应该可以工作。我不确定他们是否遵循代理最佳实践。如果不是，我的意思是，我相信你可以。

<details>
<summary>Original English</summary>

**Thor**: Yep. I let me also uh wait. So I tested with cursor and anti-gravity and also Gemini CLI. So if you are using one of those three, you're good. If you're using cloud code, I think it should work as well. I'm not sure if they follow agents best practice. If not, I mean I'm sure you can.

</details>

**提问者**: 他们发明了它，对吧？就像这些技能。

<details>
<summary>Original English</summary>

**提问者**: They invent invented it, right? Like the skills.

</details>

**Thor**: 是的，技能，但我想他们只看 Claude。我想。

<details>
<summary>Original English</summary>

**Thor**: Yeah, the skills, but I think they only look at claude. Uh I think

</details>

**提问者**: 看代理。

<details>
<summary>Original English</summary>

**提問者**: look at agent

</details>

**Thor**: 但我想它会安装到技能中。

<details>
<summary>Original English</summary>

**Thor**: but I think it installs into skills.

</details>

**提问者**: 我不知道。好的。所以。

<details>
<summary>Original English</summary>

**提問者**: I don't know. Okay. So

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提问者**: yeah.

</details>

**Thor**: 好的。是的。问题。

<details>
<summary>Original English</summary>

**Thor**: Okay. Yeah. Question.

</details>

**提问者**: 嗯，你展示了两个不同的命令。一个是技能，另一个是上下文 7 或。

<details>
<summary>Original English</summary>

**提问者**: Uh you show two different commands. One skills and the other one context 7 or

</details>

**Thor**: 是的，它们都一样。

<details>
<summary>Original English</summary>

**Thor**: Yeah, they both both work the same.

</details>

**提问者**: 但那是什么？上下文 7 是什么？

<details>
<summary>Original English</summary>

**提問者**: What but what's what is context 7?

</details>

**Thor**: 嗯，所以 **context 7** 我认为是基于 upstach 的产品。所以 **context 7** 有一个 **MCP 服务器**和一个现在可以用来访问技能的 **skills CLI**。它就像一个公共存储库。所以 `skills.sh` 和 vercel 团队的是一样的。

<details>
<summary>Original English</summary>

**Thor**: Uh so context 7 is I think a product based out of upstach. So context 7 is has an MCP server and now a skills CLI which you can use to get access to like skills. It's like a public repository. So and skills.sh is the same from the versel team.

</details>

**提问者**: 好的。

<details>
<summary>Original English</summary>

**提問者**: Okay.

</details>

**Thor**: 所以它就像，它在 **GitHub** 上都起作用。所以 Google-gemini-gemini-skills 是一个 **GitHub** 存储库，而且这个 **GitHub** 存储库包含了我们记录的所有技能。所以你也可以去那里找到它。那里也有实例命令，它比克隆它并确保你在正确的目录中要容易得多。然后我们可以做的是，嗯，为了确保我们的技能有效，我们可以像询问我们的代理，“你可以使用什么技能？”然后它应该，如果你正确安装了它，你应该会看到，是的，我们有我们的专业 **Interactions API** 技能。所以 **anti-gravity** 在 `agents/skill` 文件夹中找到了我们的技能。好的。我们做得怎么样？

<details>
<summary>Original English</summary>

**Thor**: So it's like and it it works both works on GitHub. So the Google-gemini-gemini-skills is a GitHub repository and the GitHub repository includes all of the skills we we documented. So you can also go there and find it there. There are also the the deal in instance commands and it makes it much easier than cloning it and making sure you have it in the right directory. And then what we can do is um to make sure our skill works we can just like ask our agent uh what skills can you use and then it should if it if you have installed it correctly you should see yes we have our specialized Interactions API skill. So anti-gravity here picked up our skill in the agents/skill folder. Okay. How are we doing?

</details>

**提问者**: 能放大一点吗？

<details>
<summary>Original English</summary>

**提問者**: Can you zoom in just a bit?

</details>

**Thor**: 再放大一点。

<details>
<summary>Original English</summary>

**Thor**: Zoom in more.

</details>

**提问者**: 好的。

<details>
<summary>Original English</summary>

**提問者**: Okay.

</details>

**提问者**: 更好。

<details>
<summary>Original English</summary>

**提問者**: Better.

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提问者**: Yeah.

</details>

**提问者**: 嗯，我正在用 Telegram，结果是它在系统上运行了。所以。

<details>
<summary>Original English</summary>

**提问者**: Um I was using telegram with my result of this being run on the system. So

</details>

**提问者**: 我必须让它运行吗？

<details>
<summary>Original English</summary>

**提問者**: would I have to have it run?

</details>

**Thor**: 不，你可以，你应该能够在你的开放式抓取类型的东西上做，如果你告诉它安装 **Interactions API**，然后。

<details>
<summary>Original English</summary>

**Thor**: No, you can like you should be able to do it on like your open claw kind of stuff if you tell it install the Interactions API and then

</details>

**提问者**: 只是研讨会的最终产品。它会运行吗？

<details>
<summary>Original English</summary>

**提问者**: just the final product of the workshop. Will it run?

</details>

**Thor**: 是的，它应该会运行。这是一个 **Python** 脚本。我们稍后会执行它。

<details>
<summary>Original English</summary>

**Thor**: Yeah, it should run. It's a Python script. We are going to execute it later.

</details>

**提问者**: 所以因为我只运行应该工作。

<details>
<summary>Original English</summary>

**提问者**: So because I'm only running should work.

</details>

**Thor**: 好的。安装技能有任何困难吗？对技能有什么疑问吗？每个人都熟悉技能吗？好的。我们能做的是，也许，嗯，给你一些关于我们创建了什么技能或者它包含什么技能的见解，对吧？创建技能时重要的是，它要么是模型无法可靠完成的事情，要么是你对如何做某个工作流有一些个人偏好，或者我不知道你总是需要使用 bun 运行测试或类似的东西，我们用我们的技能做的是，我们确保代理知道哪些 **Gemini 模型**可用。我们之前看到的一个常见问题是 **Gemini** 总是使用 **Gemini 1.5**，它不再是最新模型了。嗯，我们还在这里包含了代理。嗯，我们有一些关于它是如何工作的高级信息，但我们没有包含所有文档。我们所做的是，你应该看到，是的，一个指向我们文档的链接，它是以 Markdown 形式提供的。所以，我们不需要总是更新我们的技能，例如，我们向 **Interactions API** 添加了一个新功能来组合工具，我们将需要更新我们的技能，然后你们每个人也需要更新你们的技能才能使用它，然后我们在知识截止方面就不会取得太大进展。相反，我们提供信息作为技能的一部分。所以现在所有的代理都有**网络抓取工具**。所以他们可以根据技能查询信息，然后我们只需要维护文档，这些文档大部分都是最新的。是的。

<details>
<summary>Original English</summary>

**Thor**: Okay. Any any difficulties installing the skill? Any questions what a skill is? Everyone familiar with skills? Okay. What we can do maybe uh to give you some uh insights on what skill we created or what it contains. Right? The importance when creating skills is it should be either something the model cannot do reliably or if you have some personal preferences on like how to do a certain workflow or I don't know you always need to run tests using bun or something like this and what we did with our skill is we made sure that the agent is aware of which Gemini models are available. A common issue we saw before that is like Gemini always used Gemini 1.5 which is no longer the latest model. Um we also included the agents here. uh we have some like very high level information on how it works but we did not include like all of the documentation. What we did instead is you should see yes uh a link to our documentation which is available as markdown. So instead of the need to always update our skill with like for example we added a new feature to Interactions API to combine tools we would have needed to update our skill and then every one of you also need to update your skill to be able to use it and then we are not making a lot of progress in terms of like knowledge cutoff. Instead we provide the the information as part of the skill. So all of the agents now have like web fetch tools. So they can query the information based on the skill and then like we only need to maintain like the documentation which is mostly up to date. Yeah.

</details>

**提问者**: 你觉得那个怎么样？效率呢？

<details>
<summary>Original English</summary>

**提問者**: How do you find that work like efficiency?

</details>

**Thor**: 抱歉。

<details>
<summary>Original English</summary>

**Thor**: Sorry.

</details>

**提问者**: 你觉得那个和工具效率以及所有类似的东西相比怎么样？你觉得它必须去获取页面吗？

<details>
<summary>Original English</summary>

**提问者**: How do you find that works with like tooling efficiency and all that sort of thing? Do you find it like it having to go and fetch the page to

</details>

**Thor**: 我的意思是，通常你会把它作为本地文件上的一个引用来提供，对吧？所以它要么需要进行文件读取调用，要么进行网络抓取调用，这在成本方面是一样的，我想说，而且它运行得非常好。好的。所以我们要做的是第一个例子，因为我们不是即时编码，嗯，我们想构建一些更实质性的东西，我们不仅仅是说构建一个代理，我们想更具体。所以我们想构建一个代理类，带有一个构造函数和一个运行方法。构造函数创建了一个 **Gen AI** 客户端。所以 **Gen AI** 客户端是我们用来调用模型的。我们还需要定义模型，我们还需要一个全局的**之前交互 ID**，然后添加主方法来运行一个示例。嗯，所有这些都在 workshop.py 中完成。好的。

<details>
<summary>Original English</summary>

**Thor**: I mean it it normally you would provide it as a reference on your local file, right? So it either needs to do a read file call or a web f call which is the same I would say in terms of like cost and it works very well. Okay. So what we are going to do as a first example since we are not wipe coding uh we want to build something more substantial we not just say build an agent we want to be more specific. So we want to build um create an agent class with a constructor and a run method. The constructor creates uh Gen AI client. So the Gen AI client is what we are going to use to call our model. We also need uh defines model and we also need uh global previous interaction ID and then add the main method to run an example. uh do all of that in uh workshop pie. Okay.

</details>

**Thor**: 所以，正如我们所见，模型在这种情况下或者说代理作为第一步读取了我们的技能，分析了我们的主文件正在实现该技能。好的，它检查。它可能会失败。是的，因为我正在使用 UV，所以我停止并告诉它使用工作区中的 UV，然后我们让它生成。我们，好的，它检查我们是否安装了库。我们已经安装了。所以也许在你的情况下，代理仍然尝试安装 Google Chenai。如果不是，你可以自己用 pip install 或 uei pip install um google-geni，然后确保。好的，所以我们有我们的启动代理类。我们有我们的 **genai 客户端**。我们有我们的**模型 ID**。它默认为 **Gemini free flash**。如果它没有读取技能，它就不会默认为 **Gemini free flash**，对吧？因为那样我们就会停留在 **Gemini 1.5**。我们有我们的运行方法，它调用我们的 `interactions.create` 调用。我们有输入文本。我们有我们的**之前的交互 ID**。我们设置了新的**之前的交互 ID**，然后我们返回文本，然后作为一个主示例，嗯，我们很快就会运行它。我们创建了我们的代理。我们有第一回合。所以我的名字是 Phil，然后代理运行它，然后我的名字是什么？然后我们可以检查我们的 **Gemini** 创建的 **Gemini 代理**是否与多回合和我们的 **Interactions API** 一起工作。你可能会看到一个警告，类似于我在这里得到的警告。嗯，交互使用是实验性的。这是因为我们仍在测试版。我们真的努力工作，让 **API** 脱离测试版，以确保你可以在生产中使用它。我们的调用成功了。嗨 Phil，很高兴见到你。

<details>
<summary>Original English</summary>

**Thor**: So, and as we can see the model in this case or the agent as a first step read our skill, analyzed our main file is implementing the skill. Okay, it checks. It should probably fail. Yes, because I'm using UV, so I stop and I tell it use UV uh from the workspace and and then we let it generate. We Okay, it checks if we have installed the library. We have. So maybe in your case, the agent still tries to install Google Chenai. If not, you can do it yourself with like pip install or uei pip install um google-geni and then make sure to okay so we have our starting agent class. We have our genai client. We have our model ID. It defaults to Gemini free flash. It would never have defaulted to Gemini free flash if it would it hadn't read the skill, right? because then we were stuck with Gemini 1.5. We have our run method which calls uh makes our interactions.create uh call. We have the input text. We have our um previous interaction ID. We set our new previous interaction ID and then we return the text and then nice as a main example um which we will run in a bit. We create our agent. We have turn one. So my name is Phil and then the agent uh runs it and then what is my name to then we can check if our Gemini created Gemini agent uh works with uh multi-turn and our Interactions API. You might see a warning similar to the one I got here. Uh interaction usage is experimental. That's as we are still in beta. We really work hard to get the API out of beta to make sure you can use it in production. And our call was successful. Hi Phil, nice to meet you.

</details>

**Thor**: 好的，也许我们没有成功。我实际上没有名字。那么我的名字是什么？

<details>
<summary>Original English</summary>

**Thor**: Okay, maybe we weren't successful. I don't actually have a name. So what is my name?

</details>

**Thor**: 也许我们应该检查一下。我们做得对吗？

<details>
<summary>Original English</summary>

**Thor**: Maybe we should check. Did we do it correctly?

</details>

**Thor**: 我的意思是，我的名字也许是。好的，那仍然是调用。抱歉，我问了。你叫什么名字？我的意思是它是一个由 Google 训练的语言模型。这很合理。我的名字是什么？你的名字是 Philip。我能帮你什么？所以是的。

<details>
<summary>Original English</summary>

**Thor**: I mean, my name is maybe a Okay, that's still the call. Sorry, I asked it. What's your name? I mean it's a language model for trained by Google. It makes sense. And what is my name? Your name is Philip. How can I help you? So yeah

</details>

**提问者**: 3 flash 作为一个**编码模型**。

<details>
<summary>Original English</summary>

**提問者**: 3 flash as a coding model.

</details>

**Thor**: 是的。

<details>
<summary>Original English</summary>

**Thor**: Yes.

</details>

**Thor**: 我的意思是，如果你提供了好的指令，好的技能和好的上下文，它确实工作得很好，不要指望它，我不知道，像治愈癌症。如果你对你要构建什么有很好的理解，**Gemini free flash** 就像非常快。我的意思是它没有花费很长时间。它不消耗信用，对吧？我们每个人目前都有一些令牌限制，而且它确实工作得很好。好的。

<details>
<summary>Original English</summary>

**Thor**: I mean it it it works really well if you are providing good instructions with good skills and good context and don't expect it to I don't know like cure cancer. Like if you have a very good understanding of what you are trying to build Gemini free flash is like very fast. I mean it didn't take much long. It didn't consumes credits, right? Every one of us is somewhat token constraints at the moment and it it works really well. Okay.

</details>

**提问者**: 将其用于代理用途。是的。但用于规划和编码。

<details>
<summary>Original English</summary>

**提問者**: Use it for agendic use. Yes. But for planning and coding.

</details>

**Thor**: 是的。不，它有效。我的意思是我们将使用免费的。我的意思是它也会问是否要运行。所以我们甚至用 **Gemini free flash** 关闭了循环。它尝试运行我们的脚本，以确保它有效。然后我们稍后会继续。我们做得怎么样？有人成功调用了吗？是的。

<details>
<summary>Original English</summary>

**Thor**: Yeah. No, it works. I mean we will going to use free well. I mean like it also asks like if it wants to run. So we are closing the loop even like with Gemini free flash. It tries to run our script to make sure it works. And then we will continue in a bit. How are we doing? Anyone making successful calls? Yes.

</details>

**提问者**: 好的。太棒了。

<details>
<summary>Original English</summary>

**提问者**: Okay. Perfect.

</details>

**提问者**: 背景。

<details>
<summary>Original English</summary>

**提問者**: Background.

</details>

**Thor**: 好的。有什么问题吗？有什么错误吗？有什么疑问吗？

<details>
<summary>Original English</summary>

**Thor**: Okay. Any any issues? Any errors? Any questions?

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提问者**: Yeah.

</details>

**提问者**: 我正在使用 **TypeScript**。

<details>
<summary>Original English</summary>

**提问者**: I'm using TypeScript.

</details>

**Thor**: 好的。

<details>
<summary>Original English</summary>

**Thor**: Okay.

</details>

**提问者**: 它有效。

<details>
<summary>Original English</summary>

**提問者**: It it works.

</details>

**Thor**: 是的。

<details>
<summary>Original English</summary>

**Thor**: Yeah.

</details>

**提问者**: 不错。很棒。

<details>
<summary>Original English</summary>

**提问者**: Nice. Great.

</details>

**提问者**: 我也有效。

<details>
<summary>Original English</summary>

**提問者**: Works for me too.

</details>

**Thor**: 嗯哼。太棒了。甚至可以在手机上编码。所以，好的。所以，通常我们代理的下一步，对吧？我们现在有了像我们这样的非常基本的运行。我们可以与模型聊天。现在我们需要向它添加工具，我们想构建某种**编码代理**。所以首先我们要添加的工具是**读写文件工具**，我们只是继续在我们的主代理线程中。它就像，好的。

<details>
<summary>Original English</summary>

**Thor**: Mhm. Awesome. Even coding on a phone. So, okay. So, normally the next step for our agent, right? We now have our like very basic run. We can chat with the model. Now we need to add tools to it and we want to build some kind of a coding agent. So first tools uh we are going to add is a read and write file tool and we just continue in our uh main agent thread. It's like okay

</details>

**Thor**: 嗯，接下来我们需要添加一个**读文件**和**写文件工具**。创建一个基本的 **Python** 实现，以及 **JSON schema** 定义。所以当你使用函数调用或工具使用时，对吧，我们需要创建一个 **JSON schema**，我们提供给模型，这样模型就能理解它需要生成什么。一旦它生成了那个 schema，我们还需要有一些代码实现，我们可以在客户端运行它。所以我们要求它创建 **Python** 实现，以及 **JSON schema**，嗯，还有一个映射，用于键和键函数 schema。

<details>
<summary>Original English</summary>

**Thor**: uh next we need to add a read file and write file tool. create the create a basic Python implementation and also the JSON schema definition. So when you use function calling or tool use right we need to create a JSON schema which we provide to the model so the model understands what it needs to generate. Once it generates that schema, we also need to have some kind of a code implementation which we can then run on the client. So we ask it to create the Python implementation and also the JSON schema uh and a map to for the key and key function schema.

</details>

**Thor**: 好的，让我们看看它会想到什么。

<details>
<summary>Original English</summary>

**Thor**: Okay, let's see what it will come up with.

</details>

**Thor**: 好的，它有点作弊了。所以，我有一个解决方案文件夹，它查找了实现。是的，我的意思是这就是为什么检查你的，等等，我可以，它，它，它找到了解决方案，然后它就像，哦，我得到了 solution.h 代理中的这个可靠的 **Python** 示例来指导我。任务是实现**读文件**和**写文件**。

<details>
<summary>Original English</summary>

**Thor**: Okay, it's cheating a little bit. So, I have like a solution folder and it looked up the implementation implement. Yeah, I mean that's why it's still important to like check your wait I can like it it it found like the solution and then it was like oh I got this solid Python example in solution.h agent to guide me. The task is implement read file and write file.

</details>

**提问者**: 是的。所以我们得到的是两个新的非常基本的**文件实现**。所以我们有一个**读文件工具**，带有一个文件路径，它使用 **Python** 语法打开它来读取它，我们有一个**写文件工具**，带有一个文件路径和内容，并写入它。然后我们有我们的**读文件模式**。嗯，它读取文件并返回内容。**写文件**，写入文件并返回内容。它对我们的代理做了一些更新。那么它改变了什么？好的，我们的输入现在是一个文本字符串和一个列表。这很合理，因为我们现在需要返回一个函数调用。我们检查我们做什么？好的，我们为我们的模型创建了一个工具定义，它是 `T schema`。所以那是我们的**工具映射模式**。

<details>
<summary>Original English</summary>

**提問者**: Yes. So what we got back is we have two new like very basic very very basic file implementation. So we have a read file tool with a file path which uses um Python syntax to open it to read it and we have a write file tool with file path and the content and writes it. And then we have our read file schema. Um, reads a file and returns the content. Write file, writes the file and returns the content. And it made some updates to our agent. So what did it change? Okay, our input is now a text uh string and a list. Makes sense since we now need to return a function call. We check what do we do? Okay, we create a tool definition for our model which is the T schema. So that's our tools map schema.

</details>

**提问者**: 然后我们有了我们的循环，你可能对我在幻灯片中展示的那个循环很熟悉。所以当我们运行请求后，我们检查交互输出。所以交互输出包括模型生成的所有事件。由于 **Gemini** 是一个推理模型，它还包括例如思维和思维签名，我们需要返回它们，因为我们正在使用**之前的交互 ID** 和**服务器端状态**，这是我们完成的，我们只需要检查，好的，我们是否有函数调用，我们有一个很好的调试，所以我们可以检查它，对于我们的输出或函数调用，我们检查我们的工具，我们是否有我们的工具，我的意思是，也许模型想要编辑一个文件，但我们没有编辑文件工具，我们会在这里捕获它，它调用我们的模型，然后它创建工具结果。所以对于函数调用，我们有一个函数结果，这也是改变的一部分。我们真的想让它变得容易。嗯，我们稍后会看到，当我们使用 **Google 搜索**时，会有一个 **Google 搜索**调用和一个 **Google 搜索结果**，它们具有非常相同的模式，然后我们使用**递归**。所以如果我们有两个结果，我们基本上会再次调用我们自己的 `selfrun` 方法。如果我们没有两个结果，我们返回交互文本，它也更新了我们的示例。将“hello from the agent”写入一个名为 `hello text` 的文件，并返回它。所以我们，我的意思是这些更改大致看起来不错。我们可以尝试运行它。所以你运行 `python workshop main`。

<details>
<summary>Original English</summary>

**提問者**: And then we have our loop which you might be familiar with from the slide I showed. So after we run our request, we check the interactions output. So the interactions outputs include all of the events generated by the model. And since Gemini is a reasoning model, it also includes for example the thoughts and the thought signatures which we need to return since we are using the previous interaction ID and the server side state that's done by us and we only need to check okay do we have a function call we have a nice debug so we can check it and for our outputs or function call we check our tools do we have our tool or not I mean maybe the model wants to edit a file but we don't have edit a file tool we would catch it here it calls our model and then it creates the tool results. So for function call we have a function result that's also part of the change. We really want to make it easy. Um we will see later when we use Google search there will be a Google search call and a Google search result to have very the same schema and then we use recursion. So if we have two results we basically call ourself the selfrun method again. If we don't have two results, we returned the interaction text and it also updated our example. Write hello from the agent to a file named hello text and return it back. So we I mean the changes roughly look good to me. We can try and run it. So u run python workshop main.

</details>

**提问者**: 我们得到了什么？我们得到了带有**写文件**的工具调用。我们得到了两个结果。我们再次得到了**读文件**调用，然后是最终的代理响应。文件 `hello agent text` 已成功创建，内容为。

<details>
<summary>Original English</summary>

**提問者**: What do we get? We get our tool call with write file. We get our two result. We get a read file call again and then the final agent response. The file hello agent text was successfully created with the content.

</details>

**提问者**: 代理不仅仅是像单例一样，对吧？也许我们想回应。所以下一步基本上是非常雄心勃勃地告诉它，我想要一个持续的，我不知道，站在实现中进行测试。

<details>
<summary>Original English</summary>

**提問者**: Agents are not only like singleton, right? Maybe we wanted to respond. So next step is basically very ambitious telling it I want to have a continuous I don't know stood in implementation to test.

</details>

**提问者**: 让我们看看。

<details>
<summary>Original English</summary>

**提問者**: Let's see it.

</details>

**提问者**: 那么让我们看看它会从哪里继续。不，我希望它至少应该更新我们的主函数，在那里我们有一个输入，一个 `while` 循环，基本上等待使用我们的代理的输入。所以，是的。所以我们有我们的用户输入，嗯，然后我们总是在我们的 `agent.run` 方法中继续，然后在代理内部在一个循环中运行它，直到不再有工具调用为止。如果有一个结果，我们基本上会得到我们的响应。

<details>
<summary>Original English</summary>

**提問者**: So let's see where it will continue. No, I hope at least it should update our main function where we have an input a while loop basically waiting for the input using our agent. So, yep. So, we have our user input uh and then we have we always continue with our agent.r run method which then inside the agent runs it in a loops until there are no tool calls anymore. And if there's a result, we basically get back our response.

</details>

**提问者**: 好的，让我们快速等待。是太快了还是我们还在轨道上？大致。

<details>
<summary>Original English</summary>

**提問者**: Okay, let's quickly wait. Is it too fast or are we still on track? Roughly

</details>

**提问者**: 很快。

<details>
<summary>Original English</summary>

**提問者**: it's fast.

</details>

**Thor**: 好的。我的意思是我们稍后会分享代码。嗯，也很乐意回答问题。嗯，我们有很多像博客文章和在线示例。所以如果你有兴趣以后不那么快地重建它，嗯，但我尽量慢一点，但我也想给你足够的时间让你说话。所以我们现在可以做的是，既然我们或者说我们的代理实现了我们的 `while` 循环来提供输入，我们可以说“hello”，对吧？通常我们现在不应该做任何工具调用，因为“hello”就像，是的，我们的代理正确地理解了，或者 **Gemini** 在这种情况下理解了，嘿，“hello”不是我需要用读或写文件来解决的问题。所以我可以说“hello”，我能帮你什么？你能写一个，或者也许你能创建一个带有**竖起大拇指**的 **CSV** 吗？

<details>
<summary>Original English</summary>

**Thor**: Okay. I mean we will share the code later. Um also very happy to answer questions. Uh we have many like blog post and examples of that online. So you can if you are interested in like rebuilding it later with less fast um but I I try to be a little bit slower but I also want to give to enough time to have you speak. So what we can do now since we or like our agent implemented our like while loop to um to to provide input we can say something like hello right normally we should now not do any tool calls because hello is like yeah our agent correctly kind of understood or Geminina in this case understood hey hello is nothing I need to solve with a read or write file to write. So I can say hello, how can I help you? Can you write or maybe can you create uh CSV with a thumbs up

</details>

**Thor**: 可能需要一段时间。所以，它会思考，然后它会进行函数调用。好的，嗯，当然，这是一个 **CSV** 文件，等等。嗯，好的，你能把它写入磁盘吗？

<details>
<summary>Original English</summary>

**Thor**: might take a while a bit. So, it does the thinking and it does the function call and okay um certainly here's a CSV file blah blah blah. Um okay, can you write it to disk?

</details>

**Thor**: 嗯，是的，我可以，如果你等等，也许我们的模型没有我们的工具。让我们检查一下。

<details>
<summary>Original English</summary>

**Thor**: Uh yes, I can if you wait maybe our model is not having our tools. Let's check.

</details>

**Thor**: 有工具映射。它有。为什么它不使用我们的工具？你能使用什么工具？

<details>
<summary>Original English</summary>

**Thor**: There's the tools map. It does. Why is it not using our tools? What tools can you use?

</details>

**提问者**: 好的。它有一个**读文件**。

<details>
<summary>Original English</summary>

**提問者**: Okay. It has a read file.

</details>

**提问者**: 是的。也许我们不够明确。

<details>
<summary>Original English</summary>

**提問者**: Yes. Maybe we are we're not explicit enough.

</details>

**提问者**: 我们可以做的是，为了在一秒钟内改进这一点，我们可以添加一个**系统指令**来告诉模型，嘿，你是一个**编码代理**。你可以使用工具来编写和交互。

<details>
<summary>Original English</summary>

**提問者**: And what we can do to improve this in one second is we can add a system instruction to tell the model hey you are a coding agent. You can use tools to write and interact with the

</details>

**提问者**: 好的，我们得到了带有 **CSV** 的工具调用**写文件**。酷。既然我们发现了错误，我们现在可以告诉模型，嘿，为 **Interactions API** 调用添加**系统指令**，并为**编码代理**添加一个示例提示。

<details>
<summary>Original English</summary>

**提問者**: okay there we got our tool call write file with our CSV. Cool. Since we saw our mistake, we can now tell the model, hey, add system instructions for the Interactions API call and add an example prompt for a coding agent.

</details>

**提问者**: 好的。现在很棒的是，由于我们在一开始加载了 **Interactions API** 技能，模型仍然知道如何向 **Interactions API** 添加**系统指令**，我可以向你保证，**Gemini free flash** 从未见过 **Interactions API** 的任何代码，因为该模型是在我们发布 API 之前训练的。所以到目前为止我们所做的一切都是基于技能和编码基础设施，而不是训练的一部分。好的。那么我们得到了什么？

<details>
<summary>Original English</summary>

**提問者**: Okay. And what's really nice now since we uh loaded the Interactions API skill in the beginning, the model still has the awareness of okay, how do I add a system instructions to the Interactions API and what I can guarantee you is that the Gemini free flesh has never seen any code of the Interactions API because the model was trained be before we even released the API. So all of the work we were doing so far is based on like the skills and like the the coding infrastructure and hasn't been part of the the training. Okay. So what did we get?

</details>

**提问者**: 嗯，好的，我们可以在运行命令时提供它，或者我们有一个在我们创建它时提供的。这很好。好的，**编码角色**：你是一名专业的软件工程师和乐于助人的**编码助理**。你可以访问本地文件系统。好的，让我们接受它。让我们再次启动我们的代理。让我们说“hello”。

<details>
<summary>Original English</summary>

**提問者**: Um okay we can provide it on the run command or we have one when we create it. That's good. And okay coding persona you are an expert software engineer and helpful coding assistant. You have access to the local file system. Okay let's accept it. Let's start our agent again. Let's say hello.

</details>

**提问者**: 好的。你好。我能如何帮助你完成软件工程和编码任务？我的意思是，肯定比我们目前拥有的要好。我们之前发送了什么？我们说，你能创建一个带有**竖起大拇指**的 **SVG** 吗？所以，你能创建一个带有**竖起大拇指**的 **SVG** 吗？现在让我们看看它是否调用。是的。现在这次我们得到了**写文件工具**调用。然后我们还得到了，嘿，我创建了一个带有简单线条艺术**竖起大拇指**图标的 **SVG 文件**。所以。

<details>
<summary>Original English</summary>

**提問者**: Okay. Hello. How can I help you with your software engineering and coding tasks? I mean, definitely better than what we had so far. And what did we send before? We said, can you create a SVG with a thumbs up? So, can you create an SVC with a thumbs up? And now let's see if it calls. Yes. And now at this time we got our write file tool call. And then also we got a hey, I have created a thumbs up SVG file with a simple line art thumbs icon. So

</details>

**提问者**: 嗯，我想它应该会。是的，来了。

<details>
<summary>Original English</summary>

**提問者**: um can I I think it should. Yes, there we go.

</details>

**提问者**: 我们得到了一个**竖起大拇指**图标。酷。

<details>
<summary>Original English</summary>

**提問者**: We got a thumbs up icon. Cool.

</details>

**提问者**: 嗯，当然，对于**编码代理**来说，缺少什么，对吧？我们需要一些 **Bash 工具**。那现在不是解决方案文件夹的一部分。所以，让我们看看我们如何获得我们的 **Bash 工具**。现在添加一个类似的**运行命令工具**，允许模型执行 **Bash 命令**。

<details>
<summary>Original English</summary>

**提問者**: Um, and of course, what's missing for a coding agent right? We need to get some bash tools. That's now not part of the solutions folder. So, let's see how we will get our bash tool. Now add a similar run command tool that allows the model to execute bash commands.

</details>

**提问者**: 好的。

<details>
<summary>Original English</summary>

**提問者**: Okay.

</details>

**提问者**: 创建一个实现。你在问。

<details>
<summary>Original English</summary>

**提問者**: Creates an implementation blend. You're asking

</details>

**Thor**: Phil，我想有一个问题，你能。

<details>
<summary>Original English</summary>

**Thor**: Phil I think there's a question can you

</details>

**Philip**: 我说，我只是在测试，它有点像尝试做。

<details>
<summary>Original English</summary>

**Philip**: I say like I was just testing it does a little bit like try to do like

</details>

**Thor**: 即使有。

<details>
<summary>Original English</summary>

**Thor**: even with

</details>

**Philip**: 好的，所以我们有我们的**运行命令**，它使用子进程，在这种情况下我想这没问题，我们不太关心这个示例的安全性，然后我们的输出是一个标准输出。嗯，有效。

<details>
<summary>Original English</summary>

**Philip**: okay so we have our run command which uses a subprocess which in this case I guess is okay we don't care too much about security for this example and then our output is a stood out. Um, works.

</details>

**Philip**: 编辑。我们有我们的**运行命令工具**。是的，它甚至更新了我们的**系统提示**。现在让我们停止它。让我们清除它。让我们再次运行它。嗯，有什么建议我们应该测试什么吗？

<details>
<summary>Original English</summary>

**Philip**: Edit. We have our run command tool. Yeah, it even updated our system prompt. And now let's stop that. Let's clear that. Let's run it again. Um, any suggestion on what we should test?

</details>

**提问者**: 使用 **Nano Banana** 创建图像。我不确定那是否有效，因为我们没有任何技能或任何信息。

<details>
<summary>Original English</summary>

**提问者**: Use a banana to create an image. I'm not sure that will work because we don't have any skills or any information for it.

</details>

**提问者**: 时间。

<details>
<summary>Original English</summary>

**提問者**: Time.

</details>

**提问者**: 哦。

<details>
<summary>Original English</summary>

**提問者**: Oh,

</details>

**提问者**: 获取时间。

<details>
<summary>Original English</summary>

**提問者**: get the time.

</details>

**Philip**: 工具调用。运行命令日期。周三，4 月 8 日。

<details>
<summary>Original English</summary>

**Philip**: Tool call. Run command date Wednesday, April 8th.

</details>

**提问者**: 看起来不错。

<details>
<summary>Original English</summary>

**提問者**: It looks good.

</details>

**Philip**: 嗯，是的。酷。这就是我们小小的**编码代理**。

<details>
<summary>Original English</summary>

**Philip**: Um, yeah. Cool. That's our small little coding agent.

</details>

**提问者**: 删除所有文件。不，我的意思是不要这样做。

<details>
<summary>Original English</summary>

**提問者**: Delete all files. No, I mean let's not do this.

</details>

**Philip**: 还有其他问题吗？还有其他想法吗？我们大概还有五到七分钟。是的。

<details>
<summary>Original English</summary>

**Philip**: Any more questions? Any more ideas? We have like roughly five to seven minutes. Yes.

</details>

### Interactions API 缓存与状态管理

**提问者**: 一般问题。因为状态保存在网络中。是的。有可能像历史一样吗？

<details>
<summary>Original English</summary>

**提問者**: General question. So because the state is kept in the cyber. Yeah. Is it possible to like for the history?

</details>

**Philip**: 是的。

<details>
<summary>Original English</summary>

**Philip**: Yes.

</details>

**提问者**: 是的。所以。

<details>
<summary>Original English</summary>

**提問者**: Yes. So that

</details>

**Philip**: 嗯，你总是可以做到的。所以我们在这里做的是，对吧，我们总是使用前一个回合的**之前的交互 ID**。所以我们基本上堆叠它，你总是可以回到堆栈中的任何索引并从那里分支。所以如果你会在客户端保存交互 ID，你可以总是使用它们，我不知道，分支出来，就像，我不知道，有一个像做基本**网络搜索**的第一个提示，然后像以此为基础进行五个并行请求，做一些其他工作，你总是可以获得上下文。所以我们有一个 `interactions.get` 方法。

<details>
<summary>Original English</summary>

**Philip**: um what you always can do so what we are doing here is right we always use the previous interaction ID from the previous term. So we basically stack it and you can always go back to any index in the stack and branch from there. So if you would keep the interaction ids on your client side, you can always use those to I don't know branch out and like I don't know have like a first um prompt on like do basic web search and then like use this as like a base for like five parallel requests doing some other work and you can always get the context. So we have an interactions.get method

</details>

**Philip**: 你可以用它来检索交互，然后也可以获取**之前的交互 ID**。所以你基本上可以回到开头，如果你想保存状态以供以后使用，可以获取所有状态。这些交互在免费套餐中在服务器上存储一天的默认时间，付费使用目前是 55 天。

<details>
<summary>Original English</summary>

**Philip**: which you can use to retrieve the interaction and then also get the previous interaction ID. So you can basically go back until the beginning and get all of your state if you want to save it for later. And the default for those interactions being stored on the server for free tier is one day for paid usage is 55 days at the moment.

</details>

**提问者**: 是的，你有问题。

<details>
<summary>Original English</summary>

**提問者**: Yeah, you had the question.

</details>

**提问者**: 抱歉。

<details>
<summary>Original English</summary>

**提問者**: Sorry,

</details>

**提问者**: 你回答了。

<details>
<summary>Original English</summary>

**提問者**: you answer.

</details>

**Philip**: 好的，太棒了。更多问题。是的。

<details>
<summary>Original English</summary>

**Philip**: Okay, perfect. more questions. Yeah.

</details>

**提问者**: 那是不是意味着它有无限长的**上下文窗口**？

<details>
<summary>Original English</summary>

**提問者**: Does it mean then it can have infinitely long context window?

</details>

**Philip**: 嗯，不是。所以一旦 **Gemini 模型**拥有百万令牌的上下文，如果你达到那个限制，你会得到一个错误，但我们正在研究**上下文压缩**技术，但这说起来容易做起来难，嗯，这仍然是你目前需要在客户端维护的东西。所以当你说它会保留时，服务器会保留一天。那是不是意味着每天都会重置为零，然后。

<details>
<summary>Original English</summary>

**Philip**: Uh no. So once so Gemini models have a million tokens context what would happen now if you reach that you will get an error but we are working on context compaction techniques but it's easier said as done and um it's still something you currently need to maintain on on your client side. So when you say that it will retain the server will retain for one day. So that means every day it resets to zero and then

</details>

**提问者**: 不，不，所以当你发送一个请求时，你会得到一个 ID，即**交互 ID**，嗯，**交互 ID** 在免费套餐中存储你的输入和模型的输出，输入和输出以及 ID 存储一天。所以这意味着如果你现在发送一个请求，你在 8 小时后继续，那么状态或者说上下文仍然可用。如果你明天发送一个请求，它基本上会说找不到带有旧**交互 ID** 的请求，因为它基本上会在一天后被修剪。但是如果你使用付费 **API key**，它会存储 55 天。嗯，**Interactions API** 也将来到 **Vertex**。我想在如何存储或自定义方面可能会有更多的灵活性。是的。有没有特定的 API 来奖励上下文，如果你想在客户端进行上下文处理？

<details>
<summary>Original English</summary>

**提問者**: no no so when you send a request you get an ID the interaction ID uh and the interaction ID stores your input and the output of the model in the free tier the input and output and the ID is stored for one day. So meaning if you send a request now and you continue 8 hour later from that point the state or like the context is still available. If you would send a request tomorrow, it would basically say cannot find um requests with the old interaction ID because it basically is pruned after a day. But if you use the paid API key, it's stored for 55 days. And um the Interactions API is also coming to Vert.Ex. And I think there might be a little bit more flexibility in terms of um how long you want to store or customize it. Yes. Is there a specific API to reward context if you want to do context on client side?

</details>

**Philip**: 我们还没有，但希望很快就会有。

<details>
<summary>Original English</summary>

**Philip**: We don't have one yet, but hopefully soon.

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提問者**: Yes,

</details>

**提问者**: 给个主意。你可以让 **API**笑话通过 especi 说出来。

<details>
<summary>Original English</summary>

**提問者**: give an idea. You could have the API joke being spoken out with the especi

</details>

**提问者**: especi 工具来实际讲出提到的关于 **API** 的笑话。

<details>
<summary>Original English</summary>

**提問者**: the especi tool to actually speak the joke about APIs mentioned in

</details>

**Philip**: 我们也可以使用 **Gemini**，它有一个 **TTS 模型**可以说话，但是说话和听，我的意思是会展示许多许多很酷的东西。关于 **Interactions API** 和小代理有什么问题吗？

<details>
<summary>Original English</summary>

**Philip**: and we can also use Gemini which has a TTS model which can speak to but speaking and listening I mean to will show many many cool things. Any questions regarding the Interactions API and the small little agent?

</details>

**Philip**: 没有。好的。那么你们有 8 分钟时间。

<details>
<summary>Original English</summary>

**Philip**: No. Okay. Then you get 8 minutes.

</details>

**Thor**: 我做五分钟。

<details>
<summary>Original English</summary>

**Thor**: I do five minutes.

</details>

**Philip**: 好的。五分钟。

<details>
<summary>Original English</summary>

**Philip**: Okay. Five minutes.

</details>

**Thor**: 休息一下，然后我们回到这里。

<details>
<summary>Original English</summary>

**Thor**: Break and then we'll be back here

</details>

**提问者**: 让你代理说话。

<details>
<summary>Original English</summary>

**提問者**: with to make your agent talk.

</details>

**Thor**: 是的。酷。

<details>
<summary>Original English</summary>

**Thor**: Yes. Cool.

</details>

**Philip**: 酷。谢谢。

<details>
<summary>Original English</summary>

**Philip**: Cool. Thanks.

</details>

**Thor**: 那真的很有效。

<details>
<summary>Original English</summary>

**Thor**: That worked really well.

</details>

**Philip**: 不错。是的。

<details>
<summary>Original English</summary>

**Philip**: Nice. Yeah.

</details>

**Philip**: 我用了旧的，现在有了新版本 2.5，我非常高兴。是的。是的，已经有一段时间了。

<details>
<summary>Original English</summary>

**Philip**: I used the old one and super happy that now there's a new one version was 2.5 before. Yes. Yeah, it's it's been a while.

</details>

**提问者**: 好多少？

<details>
<summary>Original English</summary>

**提問者**: How much better?

</details>

**Philip**: 是的，好多了。

<details>
<summary>Original English</summary>

**Philip**: Yeah, much better.

</details>

**Thor**: 很多。

<details>
<summary>Original English</summary>

**Thor**: Much

</details>

**Philip**: 我们甚至没有付钱给他。

<details>
<summary>Original English</summary>

**Philip**: we didn't even pay him for it.

</details>

**Thor**: 大升级。

<details>
<summary>Original English</summary>

**Thor**: Big upgrades.

</details>

**Philip**: 大升级。是的。嗯。

<details>
<summary>Original English</summary>

**Philip**: Big upgrades. Yes. Um

</details>

**Thor**: 是的，也许嗯，我知道还有几分钟，但是。

<details>
<summary>Original English</summary>

**Thor**: yeah, maybe uh I know there's a couple more minutes, but

</details>

**提问者**: 我能问个问题吗？缓存。

<details>
<summary>Original English</summary>

**提問者**: can I ask a question while Caching.

</details>

**Thor**: 缓存。

<details>
<summary>Original English</summary>

**Thor**: Caching.

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提問者**: Yeah.

</details>

**提问者**: 是的。输入令牌。

<details>
<summary>Original English</summary>

**提問者**: Yes. Input tokens.

</details>

**提问者**: 是那些。

<details>
<summary>Original English</summary>

**提問者**: Is that those conting?

</details>

**Thor**: 这是一个好问题。我们可能需要找到 Philip 来回答。我实际上，我实际上不知道。

<details>
<summary>Original English</summary>

**Thor**: That's a good question. We probably need to find Philillip to answer that. I actually I actually don't know.

</details>

**提问者**: Philip 缓存问题。嗯，输入令牌。

<details>
<summary>Original English</summary>

**提問者**: Phillip caching question. Uh the input tokens

</details>

**提问者**: 怎么了？

<details>
<summary>Original English</summary>

**提問者**: y what was it?

</details>

**Philip**: 它不是在交互级别。它更像是在对象级别。所以，

<details>
<summary>Original English</summary>

**Philip**: It is not on an interaction level. It's more on an like object level. So,

</details>

**Philip**: 例如，当你提供一个像没有**交互 ID** 的输入时，第一个输入 PDF 4000 个令牌和文本输入 10 个令牌，然后你进行一个后续交互调用，也许只有 PDF 会被缓存，而不是其他的像短文本，然后如果你再做另一个，也许 PDF 和后续的回合会被缓存。所以，它更像是在对象级别。但是，既然你，我的意思是，它是怎么回事？如果你犯了一个缓存错误，即使你的提示中最小的改变，删除空格、换行符都会破坏它。所以，让它依赖服务器来维护，更能保证它的安全，而且它可能像，嘿，我的用户说末尾有一个空行。好的，我删除了它，然后我再次使用那个历史记录，然后它就崩溃了。

<details>
<summary>Original English</summary>

**Philip**: for example, when you provide an input like no interaction ID, first input PDF 4,000 tokens and the text input with 10 tokens and you do an follow-up interaction call, maybe only the PDF will be cached and not the other like the short text and then if you do another one, maybe the PDF and like the follow-up turns will be cached. So, it's like more on like an object level. But since you I mean, how is it? It's very easy to make a mistake in caching if you like even the slightest change in your prompt removing whites space line breaks will break it. So like having this rely on the server to keep it. It's more guaranteed that it's secure and it could be as easy as hey my user says there's an empty line break at the end. Okay, I remove it and then I use that history again and then it falls apart.

</details>

**提问者**: 你做得对。理想情况下，每次对话，这部分之前的对话都会被捕获。

<details>
<summary>Original English</summary>

**提問者**: You do it right. Ideally, every conversation, this previous part of the conversation is captured.

</details>

**Philip**: 是的。嗯，最佳情况下。但是，我的意思是，这取决于你的请求命中它的位置以及你后续操作的速度，但是缓存命中率应该相当高。

<details>
<summary>Original English</summary>

**Philip**: Yes. Uh, optimally. But I mean, it depends on where your request kind of hits it and like how fast you follow up, but the cache rate should be pretty high.

</details>

### Gemini 3.1 Flash Life API 演示

**Thor**: 酷。也许嗯，为了开始，我们可以看看我们能用 **Live API**，新模型构建的其中一个示例。所以这现在是嗯 **Gemini 3.1 Flash Life**，我想是两周前发布的。嗯，非常令人兴奋。已经有一段时间了。我想之前的 2.5 原生音频模型是在 12 月份。所以已经有一段时间了。原因是我们在底层架构上做了重大工作，你知道，理想情况下可以降低延迟，你知道，在未来随着它的发展有更好的可扩展性。所以，嗯，这非常令人兴奋。然后，你知道，我们同时也在努力将 **Life API** 带到 **Interactions API**。嗯，所以这是 Philip 和我目前正在做的事情。还没有完成。所以，我们现在仍然需要使用 **Live API**，但是让我们做一个小演示。

<details>
<summary>Original English</summary>

**Thor**: Cool. Maybe uh to kick things off, we can sort of look at one of the examples that that we can build uh with the the live API, the new model. So this is now uh Gemini 3.1 Flash Life which came out two weeks ago I think. Um very exciting. It's been a while. I think the previous 2.5 native audio model was December. So it's been a while. The reason being we did kind of major underlying architecture. we work to, you know, ideally lower latency, you know, better scalability in the in the future as this REMs up. So, uh, that's very exciting. And then, you know, in parallel, we're working on bringing, uh, the life API to the Interactions API as well. Um, so that's something that Philip and I are working on at the moment. Not there yet. So, we still have to use the, uh, live API for now, but let's do a little demo.

</details>

**Thor**: 所以这个演示使用了 **Live API** 与 **LIA 3** 的组合。嗯，所以在 **Gemini API** 上，有人玩过 **LIA** 吗？所以新的 **LIIA 模型**实际上是一个**音乐生成模型**。所以 **LIA 3** 现在可以生成歌曲，嗯，你知道，包括带有歌词的歌曲。嗯，所以这是一个**剪辑模型**，它是一种 30 秒的剪辑生成。嗯，但是我们现在也有一个**完整歌曲模型**，你可以生成完整的歌曲。所以想法是，我们有一个**对话代理**，它是一种 DJ，你正在与它互动，然后那个 DJ 有一个工具调用来生成音乐，对吧？嗯，所以你知道我，我最初是德国人，但是你知道，在成长过程中，我通过**哈利·波特**和 **BBC Radio One** 学会了英语。嗯，如果你还记得以前，你可以打电话进去，然后点歌。所以这就是这里体验的想法，对吧？然后你就在**实时点唱机**上。我们今天要做什么绝对的“banger”？告诉我，我们倾向于什么流派？你想要什么样的氛围？那是。

<details>
<summary>Original English</summary>

**Thor**: And so this demo uses the life API in combination with LIA 3. Uh so on the Gemini API have have people played with LIA? So the new LIIA model is actually a music generation model. And so LIA 3 can now generate songs uh you know including songs with lyrics. Uh so this is the clip model which is kind of a 30-second uh clip generation. Uh but then also we have a full song model now where you can generate kind of full full songs. So the idea is that we have our conversational agent which is kind of the DJ that you're interacting with and then that DJ has a tool call to generate music, right? Um and so you know I so I'm originally German but you know growing up I learned kind of English through Harry Potter and BB BBC radio one. Uh, and if you remember back in the day, you could like phone in and like wish for a song. And so that's sort of the the the the idea of the experience here, right? Then you're on live jukebox. What absolute banger are we cooking up today? Tell me, what genre are we leaning into? And what sort of vibe are you going for? That's

</details>

**提问者**: 我们能得到一些关于英国 **AI** 场景的高能量德国科技斯拉格吗？

<details>
<summary>Original English</summary>

**提問者**: Can we get some sort of high energy German um technos schlaga about the AI scene in the UK?

</details>

**Thor**: 关于英国 **AI** 的德国科技斯拉格。那真是太棒了，伙计。**Radio One** 的风格。有没有你想要塞进去的特定歌词或主题？

<details>
<summary>Original English</summary>

**Thor**: German technoslagger about UK AI. That's absolutely brilliant, mate. Proper Radio One style. Any specific lyrics or themes you want crammed in there?

</details>

**提问者**: 随便吧。开始吧。

<details>
<summary>Original English</summary>

**提問者**: Just surprise me. Let's go.

</details>

**Thor**: 好的，美人。让我们把那些扬声器摇起来。准备好迎接机器的狂潮吧。这里是关于英国 **AI** 场景的德国科技斯拉格。开始吧。

<details>
<summary>Original English</summary>

**Thor**: Right, you beauty. Let's get those speakers rattling. Prepare for a burst of machine mayhem. Here comes German technoslagger about the UK AI scene. Let's go.

</details>

**音乐**: 在伦敦城，未来光明而锐利。你见过最聪明的机器人。电脑戴着一顶合适的圆顶礼帽。安卓机器人全都喜欢愉快的聊天。他们喝着加糖的茶，带着数字的优雅。每个金属脸上都带着幸福的英式笑容。哦，奇迹，**AI** 超级华丽。是的，超级华丽。

<details>
<summary>Original English</summary>

**音乐**: In London town, the future's bright and keen. The cleverest robots that you've ever seen. The computers wear a proper bowler hat. And the androids all enjoy a lovely chat. They're drinking builder's tea with digital grace. A happy British smile on every metal face. OH, VUNDERAR, THE AI IS SUPER GORGEOUS. YEAH, SUPER GORGEOUS.

</details>

**Thor**: 是的。嗯，**TPU** 喜欢你为它们鼓掌。所以，嗯，非常感谢。嗯，有没有人对另一个有什么想法？我们可以再做一个。大声说出来。任何语言，任何流派？

<details>
<summary>Original English</summary>

**Thor**: YEAH. Um the the TPUs enjoy when you clap for them. So, um appreciate that. Uh any anyone have any idea for another one? We can we can do one more. Just shout it out. Any languages, any genres?

</details>

**提问者**: 我们有一个护士。

<details>
<summary>Original English</summary>

**提問者**: We have a nursing

</details>

**提问者**: 护士歌曲。

<details>
<summary>Original English</summary>

**提問者**: aur nursing song

</details>

**提问者**: 斯瓦希里语。

<details>
<summary>Original English</summary>

**提問者**: in Swahili.

</details>

**Thor**: 斯瓦希里语。好的。

<details>
<summary>Original English</summary>

**Thor**: Swahili. Okay.

</details>

**DJ**: 好的。欢迎来到**实时点唱机**。你正在和我一起直播。

<details>
<summary>Original English</summary>

**DJ**: Right then. Welcome to the live jukebox. You're on air with me.

</details>

**提问者**: 我们能来一首斯瓦希里语的护士歌曲吗？

<details>
<summary>Original English</summary>

**提問者**: Can we get a nursing song in Swahili, please?

</details>

**DJ**: 斯瓦希里语的护士歌曲。太棒了。这可不是我们每天都能听到的。为了让它成为一首绝对的“banger”，我们想要什么样的氛围？是欢快庆祝的，还是更轻松温和的？我们应该把护士的哪些具体内容放进去？告诉我，我会让这首歌火起来。

<details>
<summary>Original English</summary>

**DJ**: A nursing song in Swahili. Brilliant. That's something we don't hear every day. To make it an absolute banger, what sort of vibe are we going for? Upbeat and celebratory or something more relaxing and gentle? And what specific bits about nursing should we squeeze in? Let me know and I'll get this track buzzing.

</details>

**提问者**: 是的，**硬核技术**。

<details>
<summary>Original English</summary>

**提問者**: Yeah, techno hardcore about

</details>

**DJ**: **硬核技术**和关于护士的斯瓦希里语。太棒了。准备好炸裂那些扬声器。我正在拨号。准备好迎接一场彻底的“banger”吧，伙计。

<details>
<summary>Original English</summary>

**DJ**: techno hardcore and swuah about nursing. Wicked. Prepare to blast those speakers. I'm dialing that in now. Get ready for a total banger, mate.

</details>

**DJ**: 我永远不知道。好吧，我们可以把它输入 **Gemini**，嗯，你知道，获取音频。好的。

<details>
<summary>Original English</summary>

**DJ**: I never know. Well, we can feed it in Gemini to uh you know get the audio out. Okay,

</details>

**Thor**: 那就是**实时点唱机 DJ**，嗯，DJ 你，嗯，如果你想，它就在。所以这个完全是用 **Google AI Studio** 构建的，嗯，所以它有点像一个小的 vipodus 演示。我也把它发布在 **AI Studio** 中，所以你可以试用它，嗯，你需要一个付费的 **API key** 来做这个，因为音乐生成实际上需要一个计费账户，嗯，所以如果你有，你知道，一个有信用额度的账户，你可以使用它，嗯，例如。

<details>
<summary>Original English</summary>

**Thor**: that is the live jukebox. DJ uh DJ you uh if you want to it's it's on so this was built fully with Google AI studio uh so it's it's kind of a little vipodus um demo I've published it in AI studio as well so you can try it out uh you will need a paid API key for this one because the music generation actually requires a billing account um so if you have you know an account with credits you can use that uh for example

</details>

**Thor**: 嗯，酷，是的 **Gemini**，嗯 **3.1 Flash Life**。你知道，基准测试，显然，基准测试并不能真正告诉你真相，嗯，那么多。它们对于**基准测试**来说很棒。嗯，真实世界，尤其是在**实时音频**中，通常看起来有点不同。所以，嗯，你知道，理想情况下，我们自己尝试一下。所以，**Gemini 3.1 Flash Life**，它是现在你手机中 **Gemini Live** 中的模型。所以如果你在手机上使用 **Gemini 应用程序**，嗯，你也在和那个模型说话，以及我想**搜索 Life** 现在也有它。所以如果你和 **Google 搜索**说话，嗯，我想那是同一个模型，然后你可以使用这个模型在 **Live API** 上构建应用程序。所以 **Live API** 是一个有状态的**网络套接字 API**。嗯，你可以向模型发送实时文本、音频、视频流。所以音频是你以缓冲块的形式发送的，所以实时音频是你流式传输的，嗯，视频你可以以每秒一帧的最大帧率流式传输。所以这可以是，你知道，一个摄像头源，这可以是，嗯，一个画布。所以，嗯，它可能就像你的屏幕共享，对吧？所以你可以和模型共享屏幕。所以例如，嗯，**Shopify** 正在为 **Shopify Sidekick** 使用这个，嗯，它实际上有点像一个技术支持，指导你，你知道，如果你像，“哦，我如何为我的 **Shopify 商店**设置一个自定义域名？”它基本上会指导你如何做，它可以通过吸收屏幕的帧来看到你在屏幕上的位置。然后反过来，嗯，**网络套接字**会给你实时事件。所以这些基本上是流式传输回来的音频缓冲区。嗯，然后你也可以获得**音频转录**。所以那是一种文本。嗯，然后我们有内置的工具调用。所以 **Google 搜索**的**接地**是默认内置的。所以如果你需要实时天气信息，你也可以访问它。嗯，是的，一些关键功能。所以这个模型真正酷的地方是它是一种**原生音频模型**。所以这意味着我们不通过文本。所以它不像一个**级联管道**，嗯，你在转录文本，通过 **LLM** 运行文本，然后生成语音。嗯，而是模型本身，嗯，你知道，从声音令牌到声音令牌，智能被内置到这个音频模型中。嗯，所以它基于，你知道，**Gemini 3.1**，所以智能程度相当高。嗯，你有不同类型的思维水平可以启用。嗯，所以最棒的是它的多语言支持。所以我想目前有 97 种语言处于预览阶段，嗯，最棒的是因为它是一种**原生音频模型**，它实际上可以，它拥有 **Gemini** 的音频理解能力。所以，嗯，它可以理解不同语言的混合。它可以，你知道，例如理解“德语-英语混合语”，它是一种德语和英语的混合，对吧？所以它能够自然地在不同语言之间切换，这真的很棒。嗯，是的，**打断**，你知道，显然模型内置了自动语音活动检测，所以你可以打断它。你之前看到了 DJ，你有点想进行对话，但我们试图让它使用工具。**工具使用**是另一件大事，嗯，所以在这个模型中，**工具使用**和**指令遵循**方面有重大改进，嗯，所以你可以用它构建一些非常酷的东西，嗯，所以显然我们目前只提供**网络套接字 API**，所以如果你以前使用过像 **GPC 实时**这样的东西，你知道你得到了直接的 **Web RTC** 基础设施，这可能会很有用，这是一个缺点。所以我们与许多集成合作伙伴合作，例如 **Lifekit**、**Pipecat**、波兰的 **Software Mentioners**。他们构建了一个很棒的服务，叫做 **Fish Gem**、**Vision Agents**、**Vox Implant**。所以这些合作伙伴直接集成了 **Life API**，然后为你提供简单的 **Web RTC** 集成，如果你，如果你，嗯，你知道，需要它，或者你的系统需要它。

<details>
<summary>Original English</summary>

**Thor**: uh cool yeah Gemini uh 3.1 Flash Life. You know, benchmarks, obviously, benchmarks don't really tell you the truth uh as much. They are great for benchmarking things. Uh the real world, especially in kind of live audio, does often look a bit different. So, um you know, ideally, we just try it out ourselves. So, Gemini 3.1 Flash Life, it's the model that is now in Gemini Life in your phone. So if you're using Gemini app uh on your phone um you're talking to that model as well as I think search life has it now in there as well. So if you're talking to Google search uh I think that's the same model and then you can build applications using this model on the life API. So the life API is a stateful kind of websocket API. um you are able to send real time text, audio, video feeds uh to the model. So audio you're sending in kind of you know buffer chunks so of the the real-time audio you're streaming that in uh video you can stream in uh at a maximum frame rate of one frame per second. So this can be you know a camera feed, this can be uh a canvas. So uh it could be like your your your screen share, right? So you could share the screen with the model. So for example, uh Shopify is using this for uh Shopify site kick um where it's actually kind of like a tech support walking you through, you know, if you're like, "Oh, how do I set up a custom domain for like my Shopify store?" It would basically like talk you through how to do that and it can see kind of where you are on the screen by sort of ingesting the frames of the screen. And then in return uh the websocket gives you kind of real-time events back. And so these are basically streaming back audio buffers. Uh and then also you can get the audio transcription. So that's kind of the text um of it. And then we have um tool calling built in. So Google search grounding is built in by default. So if you need kind of real-time weather information, you can access that as well. Um yeah, some key features. So what's really cool about this model again it's it's kind of native audio model. So what that means is we're not going through text. So it's kind of not a cascading pipeline where um you're transcribing the text running the text through an LLM and then generating speech. Uh but rather the model itself um is you know going sound token to sound token and the intelligence is kind of baked into this audio model. Um so it's based on you know Gemini 3.1 so decently intelligent. Uh you have different kind of thinking levels that you can enable. Um and so the great thing with that is kind of the multilingual support. So it's I think 97 languages that are kind of supported in preview uh at the moment which uh and the great thing is because it is kind of a you know native audio model it can actually it has sort of the audio understanding of of Gemini built into it. So um it can understand a mix of different languages. It can you know sort of denlish for example which is like a mix of German, Deutsch and and English, right? So it would be able to sort of naturally switch between kind of different languages as well which is really great. Um yeah, barge, you know, obviously there's kind of automatic um voice activity detection sort of built into the model so you can interrupt it. you saw it earlier the DJ you kind of trying to have a conversation but we're trying to get it to to to you know use the tool tool use is the other big thing um so major improvements in kind of tool use and instruction following here with that model um and so you can build some some really cool things with that um so obviously we currently only give you uh a websocket API so that is kind of a downside if you use something like GPC real time before you know you get a direct web RTC um kind of infrastructure which which can be helpful. So we have partnered with you know a lot of uh sort of integration partners like lifekit, pipecat uh software mentioners uh in Poland. They they built a great service called fish gem uh vision agents vox implant. So these partners have integrated kind of the life API directly and then give you sort of easy web RTC integrations if you if you um you know want that or need that kind of for your system.

</details>

### Live API 交互与挑战

**Thor**: 嗯，是的，让我们试试吧。所以你可以自己试试。嗯，如果我们所有人都同时在这个房间里试试，那会很有趣。所以，嗯，我们会看看效果如何。但是，嗯，再次强调，**AI.studio** 或 **AI.dev**，然后是 `/life`。嗯，你可以试试这个模型，所以你可以，你知道，在这里输入你的网络摄像头。嗯，所以我们可以给它我们的网络摄像头 feed。嗯，这次允许。嗯，然后，你知道，我们也可以发送文本。所以我们可以发送，例如，我的衣服怎么样？

<details>
<summary>Original English</summary>

**Thor**: Um yeah let's let's try it out. So you can try it out yourself. Uh, and it's going to be interesting if we all try it out in this room at the same time. So, uh, we'll see how that works. But, uh, again, AI.studio or AI.dev and then slife. Uh, you can try out the model and so you can, you know, ingest your webcam here as well. Uh, so we we can give it our webcam feed. Um, allow this time. Uh, and then, you know, we can send text as well. So, we could send like, uh, how is my outfit?

</details>

**Thor**: 嗯，所以在这种情况下，你知道，我没有摄入任何。

<details>
<summary>Original English</summary>

**Thor**: Uh, so in this case, you know, I'm not ingesting any.

</details>

**Gemini Live**: 你穿着一件绿色夹克，里面是蓝色 T 恤，搭配一顶黑色帽子。这种组合看起来随意又舒适。你心里有什么特定的场合吗？

<details>
<summary>Original English</summary>

**Gemini Live**: You're wearing a green jacket over a blue t-shirt paired with a black cap. The combination looks casual and comfortable. Is there a specific occasion you have in mind?

</details>

**Thor**: 是的。好的。所以，嗯，你知道，那显然与我们欢快、有点英式、澳式、澳大利亚式的**现场 DJ** 有点远。所以，我们可以，嗯，你可以调整我们的声音。所以通过**系统指令**。嗯，现在就低音人声而言，我们没有那么多。大概有 30 种不同的低音人声。

<details>
<summary>Original English</summary>

**Thor**: Yeah. Okay. So, um, you know, that obviously is a bit further away from our upbeat sort of British, Australish, Australian, uh, live DJ. So, what we can do is we can, um, you kind of adjust our our voice. So through the system instructions. Um now in terms of the bass voices, we don't have that many. There's kind of 30 different bass voices.

</details>

**提问者**: 心里有一个项目。

<details>
<summary>Original English</summary>

**提問者**: Got a project in mind

</details>

**Thor**: 而且它们，你知道，相当通用，但是因为，你知道，**Gemini** 拥有非常深入的**音频理解**能力。我们可以做的是，实际上我们可以通过提示，通过**系统指令**来修改声音。所以我们可以做的是，实际上我们可以给它，嗯，一个**系统指令**，例如，我们可以说“好的，用友好的爱尔兰口音说话”，对吧？嗯，所以现在我们有了那个低音，嗯，并用友好的爱尔兰口音说话。

<details>
<summary>Original English</summary>

**Thor**: and they are you know fairly generic sort of but because you know Gemini has very deep audio understanding. What we can do is actually we can modify the voice through prompts through system instructions. So what we can do is actually we can give it um kind of a system instruction here for example and we can just say okay speak in a friendly Irish accent, right? Um and so now we have that bass voice puck and uh speak in a friendly Irish accent.

</details>

**Thor**: 嘿，你能听到我吗？

<details>
<summary>Original English</summary>

**Thor**: Hey, can you hear me?

</details>

**Gemini Live**: 喂，你好。声音洪亮清晰，所以我能听到。今天这么好的日子，我能为你做些什么？你觉得我的衣服怎么样？

<details>
<summary>Original English</summary>

**Gemini Live**: Well, hello there. Loud and clear so I can. What can I do for you on this fine day? What do you think of my outfit?

</details>

**Gemini Live**: 嗯，现在你看起来非常时髦，真的。那件绿色夹克很适合你，我必须说。非常休闲的款式。你是不是想出去走走？

<details>
<summary>Original English</summary>

**Gemini Live**: Well, now you're looking very smart, so you are. That green jacket suits you well, I must say. A grand's casual look. Were you thinking of heading out somewhere?

</details>

**Thor**: 嗯，不。我只是在这里的 **AI 工程师**。好的。不管怎么说，我意识到我没有穿。所以，我还想向你们展示的是，嗯，有 **Google 搜索接地**。所以我们可以做的是，嗯，你知道，显然模型本身是根据某个知识截止日期进行训练的，所以，嗯，你知道，如果我们需要实时信息，就像这美妙的天气，你知道没有人会真正相信我们，模型也不会相信我们，你知道，如果它没有 **Google 搜索接地**，但是现在，你知道，我们可以有 **Google 搜索接地**，我们也可以有不同的思维水平，所以，嗯，没有思维实际上是最小的思维。嗯，但这意味着，你知道，模型会更快地响应。它有点像更低的延迟，因为我们拥有的思维越多，显然涉及的思维步骤就越多，嗯，它会，你知道，增加延迟。所以你也可以在基准测试中看到，有高思维、低思维，嗯，各种不同的思维水平。嗯，但是现在如果我们打开这里的 **Google 搜索**。

<details>
<summary>Original English</summary>

**Thor**: Uh, no. I'm just here at the AI engineer. Okay. Anyway, so I I realized I didn't put on So, what I wanted to show you as well is um there's grounding with Google search. So what we can do is um you know obviously the the model itself is trained to a certain knowledge cutoff date and so um you know if we need kind of real-time information like this gorgeous weather that you know no one would actually believe us the model wouldn't believe us you know if it if it didn't have um Google search grounding but now you know we can we can have Google search grounding we can have different thinking levels as well so um no thinking is actually very minimal thinking. Um but it means you know the model will respond faster. It's kind of lower latency because the more thinking we have obviously the more thinking steps are kind of involved and um it'll you know increase the latency. So you can see in the benchmarks as well there's kind of thinking high uh thinking low uh sort of different thinking levels. Um, but so now if we turn on kind of the the Google search here.

</details>

**Gemini Live**: 哦，你好。今天我能帮你处理什么恶作剧？随便什么都可以？尽管说出来。

<details>
<summary>Original English</summary>

**Gemini Live**: Oh, hello there. What range of shenanigans can I help you with today? Anything at all? Just give a shout.

</details>

**提问者**: 嗯，是的。伦敦现在天气怎么样？

<details>
<summary>Original English</summary>

**提問者**: Uh, yeah. What's the weather right now in London, actually?

</details>

**Gemini Live**: 嗯，现在伦敦气温大约 9 度，大部分多云。可能会有点冷，所以你肯定需要一件夹克。关于那里的事情，你还需要知道些什么吗？

<details>
<summary>Original English</summary>

**Gemini Live**: Well, now it looks like it's about 9° and mostly cloudy in London right now. Might be a bit chilly, so you'd be wanting a jacket for sure. Anything else you need to know about the goings on over there?

</details>

**提问者**: 什么？你在说什么？你能再查一遍吗？今天是什么日期？

<details>
<summary>Original English</summary>

**提問者**: What? What are you talking about? Can you check again? What date is today?

</details>

**Gemini Live**: 啊，抱歉。我似乎有点得意忘形了。今天是 2026 年 4 月 8 日星期三。你今天有什么特别想知道的吗？

<details>
<summary>Original English</summary>

**Gemini Live**: Ah, apologies there. I seem to have gotten ahead of myself. Today is Wednesday, April 8th, 2026. Is there anything specific you needed to know about today?

</details>

**提问者**: 是的。现在查一下今天实际的天气。

<details>
<summary>Original English</summary>

**提問者**: Yeah. And now look up today's actual weather.

</details>

**Gemini Live**: 好的。2026 年 4 月 8 日星期三伦敦的天气。气温在 5 到 13 摄氏度之间，有很大的下雨机会，所以别忘了带伞。你还有什么想知道的吗？

<details>
<summary>Original English</summary>

**Gemini Live**: Right. for Wednesday, April 8th, 2026 in London. You're looking at temperatures between 5 and 13 degrees with a decent chance of rain, so don't forget that umbrella. Anything else on your mind?

</details>

**Thor**: 好的。嗯，我们来了。看起来我没有向演示之神祈祷。好的，看来有些问题。我想知道我们是否搞砸了用户界面。嗯，它应该比这好得多。嗯，我想 **Google 搜索接地**出于某种原因没有工作。所以但我们现在能做的是，我们显然可以在应用程序中自己尝试它。所以我们能做的最简单的方法是，你知道，像**实时点唱机 DJ**，嗯，我们可以使用 **Google AI Studio** 来，嗯，编写我们的集成。嗯，所以我们这里有一个药丸，叫做，嗯，添加，你知道，语音对话实时语音与，你知道，**Gemini Live API**，嗯，然后我们可以说，嗯，构建某种多语言面试助理，允许我，你知道，用不同语言进行面试训练，嗯，像德语、英语和西班牙语，你知道，以及其他。

<details>
<summary>Original English</summary>

**Thor**: All right. Uh here we are. It looks like I didn't pray to the the demo gods. Okay, there seems to be something going on. I wonder if we messed up the UI there. Uh it should it should work a lot better than that. Um I think the Google search grounding for some reason isn't isn't working. So but what we can do now is we can obviously try it out ourselves in an application. So the easiest way we could do that is you know like the live jukebox life jukebox DJ um we could use Google AI studio to kind of v code our integration. Um so we have this pill here which is called uh add you know voice conversation real time voice with you know Gemini life API uh and then we could say um build kind of a multilingual interview assistant that allows me to you know train for interviews in different languages uh like German and English and Spanish and you know what have you

</details>

**Thor**: 嗯，所以我们现在可以，嗯，启动这个。所以这使用了 **Gemini 3 Flash 预览**。嗯，目前它仅限于，嗯，JavaScript 全栈环境。所以我认为你可以选择 **Next.js** 或 **Angular**。嗯，如果你正在为**眼镜**构建，还有像 **XR 构建块**，嗯，那种 **Web VR 体验**。嗯，所以，你知道，请随意启动其中一个，嗯，现在，或者你也可以克隆我之前与你分享的**实时点唱机 DJ**，你可以试用一下。嗯，这会需要一点时间，嗯，一旦准备好，你会听到一声小铃声。所以与此同时，我们可以做的是，嗯，如果你去 **Gemini Life API** 文档，**Gemini Life API**，嗯，我们来了。

<details>
<summary>Original English</summary>

**Thor**: uh And so we can now kind of fire this off. So this uses Gemini 3 flash preview. Um it is limited to uh kind of JavaScript full stack um environments at the moment. So I think you can choose between kind of next.js Angular. Um there's like XR building blocks as well if you're building for for kind of glasses um sort of web VR experiences. Um, so you know, feel free to kind of fire one of these off uh right now or you can also clone uh the live jukebox DJ that I shared with you earlier and you can try that out. Um, it'll it'll take a little time uh and you'll hear like a little chime once it is uh ready. So in the meantime, what we can do is uh so if you go to the Gemini Life API docs, Gemini Life API, uh there we are.

</details>

**Thor**: 所以，你知道，我们已经做了这个。我们尝试了 **Google AI Studio** 中的 **Live API**。嗯，我们也可以使用**编码代理技能**。所以，嗯，Phil 之前向你展示了这个。嗯，我们也有专门的**编码代理技能**用于 **Gemini Live API**。所以你可以安装它。它将帮助，你知道，你的**编码代理**更轻松、更快速地集成 **Live API**。嗯，但同时，你知道，我们也有 **GitHub** 上的好老示例应用程序，这可能会非常有帮助。所以你可以做的是，嗯，你可以克隆这些示例应用程序。嗯，所以在 **GitHub** 上，你知道，你可以，嗯，就像你在 **GitHub** 上做的那样，对吧，嗯，你可以克隆这个。所以，我们打开一个新的终端。

<details>
<summary>Original English</summary>

**Thor**: So, you know, we've done this. We tried out kind of the life API in Google AI Studio. Um, we also can use the coding agent skills. So, uh, Phil showed you this earlier. Um, we have dedicated coding agent skills also for the the Gemini Life API. So, you can install that. It'll help, you know, your coding agent integrate the life API um more easily, more quickly. Uh but then also you know we have good old example apps on on GitHub which can be very very helpful. So what you can do is um you can clone these example apps. Uh so in GitHub you know you can uh like you do in GitHub right uh you can clone this. So, we'll open kind of new terminal.

</details>

**Thor**: 是的，请随意跟着做。再大一点。

<details>
<summary>Original English</summary>

**Thor**: And yes, feel free to follow along. Do that a bit bigger.

</details>

**Thor**: 嗯，我们创建一个新目录。我们称之为 `AIG Europe`。我喜欢他们称之为 Europe，对吧？但它，嗯，我的意思是，我想，是的，英国仍然是欧洲的一部分，只是不是欧盟。公平。

<details>
<summary>Original English</summary>

**Thor**: Uh we'll make a new directory. We'll call it AIG uh Europe. I like that they call it Europe, right? But it's uh I mean, I guess, yeah, the UK is still part of Europe, just not the EU. Fair enough.

</details>

**Thor**: 嗯，然后我们进去。嗯，然后我们只进行 `git clone`，嗯，我们的应用程序。嗯，所以现在我们这里有了我们的应用程序。嗯，所以这里实际上有几个不同的示例我们可以使用。嗯，所以如果你使用 **anti-gravity**，有一个方便的 `agy` 命令可以，嗯，在 **anti-gravity** 中打开你的示例。

<details>
<summary>Original English</summary>

**Thor**: Um, and so we'll we'll go in there. Uh, and then we'll just do a git clone um of our app. Uh, and so now we have our app in here. Um, so there's actually a couple different examples that we can use in here. Uh, so if you're using anti-gravity, there's a handy agy command to uh open your examples in anti-gravity.

</details>

**Thor**: 嗯，所以我们可以，你知道，在这里查看我们不同的示例，以及我们如何设置它们。所以我们有，你知道，两种不同的场景。所以 **Gemini Life Genai Python** 示例在服务器上使用 **Gemini Life API**。所以它在你的服务器和，嗯，**Gemini Life API** 之间创建了一个**网络套接字连接**，然后在你的前端，你基本上设置了一个**代理**，嗯，将**网络套接字连接**代理到你的客户端，对吧？因为你的浏览器窗口就是你的客户端，所以这就是捕获你的音频源、你的视频源的地方，所以在这个示例中，我们只是使用 **Fast API**。好的。嗯，我们基本上只是设置了一个**网络套接字**，嗯，我们的客户端可以连接到它，嗯，然后我们基本上只是接收我们的音频提示、视频提示从客户端。嗯，或者，你知道，我们的文本输入队列也是。嗯，所以我们正在接收它。然后我们设置一个**实时会话**。所以，嗯，我们正在使用我们的 **Gemini 客户端**。所以我们有点抽象了所有的 **Life API** 的东西到这里的 `Gemini life` 文件中。嗯，你可以看到像启动会话我们基本上设置了我们的 **Life Connect Config**。也许我现在关闭这个。嗯，所以你可以看到，嗯，我们设置了一些**系统指令**。所以之前，你知道，我们说了一个乐于助人的助手。我们还说，例如，用友好的爱尔兰口音说话。嗯，你知道，这就是我们放置我们的**系统指令**、我们的**护栏**的地方。我们可以，你知道，使它相当长，以便涵盖我们想要的内容。嗯，然后我们可以在这里定义我们的工具。嗯，然后我们基本上设置了我们的会话，嗯，我们的会话，你知道，是**网络套接字会话**。嗯，然后我们只是从客户端接收我们的音频和视频提示，嗯，并将其代理过去。所以这是一种方法。这是一种**服务器到服务器**的方法。嗯，你知道，我们只是在这里使用 **UV**。

<details>
<summary>Original English</summary>

**Thor**: Uh and so we can you know look at our different examples here and how we kind of need to set that up. So we have you know two different scenarios. So the Gemini Life Genai Python example uses the Gemini Life API on the server. So it creates a websocket connection from your server to uh you know Gemini life API and then on your front end you basically set up a proxy um to proxy the websocket connection to your client side right because your your browser window is kind of your client and so that is what is capturing um your your uh audio feed your video feed and so in this example we're just using fast API Okay. Uh, and we're basically, uh, just setting up kind of a web socket here, uh, that our client can connect to, uh, and then we're basically just receiving sort of our, um, you know, audio cues, our video cues from the client site. Uh, or, you know, our text input queue as well. Uh, and so we're receiving that. We then setting up um, a live session. So um we're using our Gemini client. So we kind of abstracted sort of all the life API stuff into this Gemini life file here. Uh and you can see like starting the session we're basically setting up kind of our life connect config. Maybe I close this for now. Uh so you can see that um we're setting up some system instructions. So that was you know earlier kind of said a helpful assistant. We also said kind of speak in a friendly Irish accent for example. Um, you know, this is where we put our uh sort of system instructions, our guardrails. We can, you know, make that pretty long in terms of covering sort of what we what we want. Uh, and then we can define kind of our tools here. Um, and then we're basically setting up our um, you know, session and uh, our session sort of is, you know, the websocket session. Uh, and then we're just receiving our audio and video cues from the client side. uh and proxying that through. So that is kind of one approach. That's sort of the server to server approach. Um and you know we're just using kind of UV here.

</details>

**Thor**: 嗯，所以如果我们要第一次设置这个，嗯，我们可以进入。所以这是我们的 **Gemini Life**，嗯，Genai **Python**，嗯，这里的示例。所以我们可以设置我们的**虚拟环境**。然后我们可以，嗯，在这里激活我们的源。

<details>
<summary>Original English</summary>

**Thor**: Um so if we're setting this up for the first time, uh we can go into So this is our Gemini live um Genai Python uh example here. So we can set up uh our virtual environment. We can then um activate our source here.

</details>

**Thor**: 嗯，我们可以安装我们的依赖项。嗯，好的，我可能有了。这是谷歌笔记本电脑安全的一个有趣部分。

<details>
<summary>Original English</summary>

**Thor**: Uh we can install our dependencies. Uh okay, I might have this is a a fun part of uh uh a Google laptop security.

</details>

**Thor**: 来吧。好的。别看。别看那个。嗯，然后是的，安装我们的要求。所以我们需要一个 **API key**。嗯，所以 **API key**，你可以在这里看到配置是如何的。所以我们基本上只需要我们的 **Gemini API key**。嗯，我们需要设置一个**环境变量**。所以你可以看到我们这里有一个示例文件。里面没什么内容，因为它基本上就是那个。所以我们可以把我们的 `env.example` 复制到我们的 `v` 文件中。然后，你还记得如何获取你的 **API key** 吗？你在哪里获取你的 **API key**？

<details>
<summary>Original English</summary>

**Thor**: Come on. All right. Just look away. Don't look. Don't look at that. Um and then yeah, install our requirements. And so we'll need uh an API key. Uh so the API key, you can see kind of here uh how the config configuration is. So we basically just need our Gemini API key. Uh and we need to set up uh an environment variable for that. So you can see we have an example file here. Not a lot in there because it's basically just that. So we can copy our env.example into ourv uh file here. And then do you remember how to get your API key? Where do you get your API key?

</details>

**提问者**: 是的。**AI.dev**。我们来了。太棒了。喜欢它。嗯，好的。**AI.dev**。嗯，所以那就是你获取 **API key** 的地方。嗯，我想我有一些 **API key**。所以，它需要一点时间来加载它们。嗯，哪个是，也许我们会用这个。所以一旦你创建了你的 **API key**，嗯，你可以从这里复制 **API key**。嗯，实际上也许我应该创建一个新的，因为稍后我需要删除它。嗯，所以我们会说 `AIG Europe`。

<details>
<summary>Original English</summary>

**提問者**: Yes. AI.dev. There we are. Fantastic. Love it. Um, okay. AI.dev. Uh, so that is where you get your API key. Uh, I think I have a couple API keys. So, it takes a little while to um load them here. Uh which one is maybe we'll we'll use this one. So once you've created your API key uh you can copy the API key from here. Well actually maybe I should create a new one because later I'll need to delete it. Uh so we'll say AIG Europe.

</details>

**提问者**: 嗯，我们这里有一些项目。我们只使用。

<details>
<summary>Original English</summary>

**提問者**: Uh we'll we have a couple projects here. We'll just use

</details>

**提问者**: 我们用哪个？项目太多了。好的。我们只用这个。

<details>
<summary>Original English</summary>

**提問者**: we'll just uh which one which one we using? Too many projects. Okay. We'll just use this one.

</details>

**提问者**: 嗯，所以现在我真的不喜欢我们在这里实际返回清晰的 **API key**。我想我们今天学到了一些东西。嗯，好的，我们保存了它。嗯，所以现在我们已经设置好了 **API key**。现在我们可以做的是，嗯，我们可以运行我们的演示。那只是 `main.py`。

<details>
<summary>Original English</summary>

**提問者**: Uh, and so now I really don't like us actually returning the clear API key here. I think we learned something today. Um, okay, we save that. Uh, and so now we have sort of our API key set up. And now what we can do is, uh, we can run our demo. And that was just the main.py.

</details>

**提问者**: 所以现在我们的演示将在 `localhost:8000` 上运行。所以我们可以看到，嗯，它只是一个基本的演示。嗯，当我们连接时。

<details>
<summary>Original English</summary>

**提問者**: And so now our demo will be up and running. on localhost 8000 here. And so we can see um it's just kind of a basic sort of demo. Uh and when we connect

</details>

**Gemini Live**: 早上好，我是 **Gemini Live**。这个 **API** 能做什么的小演示。为什么不尝试一些有趣的功能，比如听我用不同的应用程序说话？可以。

<details>
<summary>Original English</summary>

**Gemini Live**: top of the morning to you, I'm Gemini live. A little demo of what this API can do. Why not try out some fun features like hearing me speak and different apps? Can

</details>

**提问者**: 你能打断我说话吗？

<details>
<summary>Original English</summary>

**提問者**: you cancel me saying?

</details>

**Gemini Live**: 啊，我能看到你。好的。你坐在那里，帅气的脸庞直视着我。

<details>
<summary>Original English</summary>

**Gemini Live**: Ah, I can see you. All right. You're sitting there with your handsome face looking straight at me.

</details>

**提问者**: 哦，那是，那是。这是我问的。

<details>
<summary>Original English</summary>

**提問者**: Oh, that was that was this uh I was asking.

</details>

**Gemini Live**: 抱歉。

<details>
<summary>Original English</summary>

**Gemini Live**: Sorry.

</details>

**提问者**: 哦，是的。是的。是的。但它没有转录。

<details>
<summary>Original English</summary>

**提問者**: Oh, yeah. Yeah. Yeah. but it didn't transcribe it.

</details>

**Thor**: 嗯，好吧。嗯，我们在这里发现了很多需要改进的地方，这很好。嗯，但是，是的，我们看到，嗯，所以这个，你实际上可能会注意到延迟有点糟糕，因为我们实际上是从客户端跳到服务器。嗯，我喜欢把责任推给 Wi-Fi，但是，嗯，使用**服务器到服务器**的设置，你只是有额外的延迟，嗯，通过你的客户端。所以我们也可以直接从客户端到服务器。嗯，所以这是我们拥有的另一个示例，嗯，这是使用**临时令牌**的那个。

<details>
<summary>Original English</summary>

**Thor**: Um, all right. Uh, we're finding out a lot of things here, uh, to improve, which is nice. Um, but yeah, so what we can see is, um, so this is, you could actually notice that the latency is a bit worse because we're actually having that jump from our client to our server. Um I would love to blame the Wi-Fi but uh so with the serverto-s server setup you just have that additional latency of sort of going through um your client. So what we can do as well is we can go directly from our client to the server. Uh and so this is the other example that we have um which is this one here using ephirmal tokens.

</details>

**Thor**: 所以，嗯，对于**临时令牌**，我们可以看看这里的设置。嗯，非常相似。我们会，嗯，回去，嗯，实际上，让我在这里打开一个新的终端。所以我们会说，嗯，**临时令牌**。所以我们的**临时令牌**基本上是短寿命的令牌，嗯，我们用我们的 **API key** 在服务器端生成，然后我们将那个**临时令牌**发送到我们的客户端。所以，你知道，我们的手机，我们的浏览器，嗯，然后直接从客户端到 **Life API** 启动**网络套接字连接**。嗯，这里再次是类似的设置。我们需要一个**虚拟环境**。嗯，然后我们，嗯，激活我们的**虚拟环境**。

<details>
<summary>Original English</summary>

**Thor**: So uh for effirmal tokens we can just kind of look into uh the setup here. Uh very similar. We'll just go uh back uh actually let me get a new terminal up here. So we'll say uh effirmal tokens. So our effirmal tokens are basically shortlift tokens uh that we generate with our API key on the server side and then we send that effirmal token to our client. So you know our phone, our browser uh to then initiate the websocket connection directly from the client to the life API. Uh again similar setup here. We want uh a virtual environment. Uh we then uh activate our virtual environment

</details>

**Thor**: 我们安装我们的依赖项。嗯，我们还需要我们的 **API key**。嗯，再次。所以我想我们可以做的就是使用同一个。所以我们会复制，也许只是复制这里这个，然后粘贴。嗯，粘贴进去。它够大吗？我不知道。人们能看到吗？也许我们会再放大一点。

<details>
<summary>Original English</summary>

**Thor**: and we install our dependencies. Uh we also need our uh API key uh again. So I think what we can do is just use the same one. So we'll copy maybe just copy this one here and then paste uh paste that in. Is it big enough? I don't know. Can people see that? Maybe we'll zoom in a little bit more.

</details>

**Thor**: 所以现在我们这里也有我们的密钥。嗯，然后。

<details>
<summary>Original English</summary>

**Thor**: So now we have our key here um as well. Uh and so

</details>

**Thor**: 现在我们已经安装了依赖项，嗯，我们可以运行我们的服务器。嗯，所以我们的服务器在这里，嗯，我们可以快速看看服务器。所以这个服务器基本上只是一个非常，你知道，精简的后端，它只有我们的 **Gemini API key**，嗯，然后它为我们生成一个**临时令牌**。所以，嗯，**临时令牌**目前在 **v1 alpha API** 上。所以你现在需要使用不同的 **API**。然后你将传入这个**过期时间**。嗯，因为理想情况下，你知道，令牌应该是短寿命的。嗯，所以如果令牌泄露了，你知道，嗯，它不应该太昂贵，因为它会很快过期。

<details>
<summary>Original English</summary>

**Thor**: now that we have our dependencies installed, uh we can run our server. Uh and so our server here, um we can look at the server real quick. So this server is basically just uh a very you know slim sort of back end that just has our Gemini API key uh and then it generates an effirmal token for us. So sort of um ephirmal token is currently on the v1 alpha API. So you'll need to use actually a different API uh at the moment for this. And then you would pass in kind of this expiration time. Uh because ideally, you know, the token should be shortlived. Uh so should the token ever leak, you know, uh it shouldn't be too costly because it'll expire um pretty soon.

</details>

**Thor**: 所以我们来了。那就是我们的令牌。然后我们将令牌返回给我们的客户端。所以，在我们的前端，我们有我们的 **Gemini Life** 集成。所以这是一个纯粹的**网络套接字集成**的示例，没有 SDK。嗯，所以，你知道，你可以使用任何类型的**网络套接字框架**，嗯，在这里，你可以看到，你知道，所有不同的原始**网络套接字事件**是如何处理的。

<details>
<summary>Original English</summary>

**Thor**: So there we are. That's our token. And then we return our token back to our client. So on our front end, we then have our Gemini Life kind of integration here. And so this is an example of just a pure websocket integration without sort of any SDK. Um so you know if you you can use kind any sort of websocket framework um here and you can see sort of you know how all the the different sort of raw websocket events um are handled.

</details>

**Thor**: 嗯，所以你可以在这里看到，嗯，这是我们的**网络套接字 API**。所以在这里我们需要使用 **v1 alpha**。嗯，然后这是双向的。嗯，你知道，我们正在双向流式传输。嗯，在这里我们传入我们的**访问令牌**，它是我们的**短寿命令牌**。

<details>
<summary>Original English</summary>

**Thor**: Uh and so you can see here we have um you know this is kind of our websocket uh API. So here we need to use kind of the v1 alpha. Um and then this is the by so birectional. Um you know we're streaming in both directions. Uh and here we we pass our access token which is our shortlift token.

</details>

**Thor**: 嗯，太棒了。所以我们现在可以做的是，现在我们的服务器已经启动并运行了。嗯，所以我们可以看到，嗯，这个漂亮的界面，它，嗯，是手工制作的。嗯，你知道，那时没有任何代理参与它的创建。所以我们现在可以看到这里所有的不同旋钮。所以我们也会尝试这种 **Google 接地**。希望能，嗯，只是我们需要在用户界面中修复的一个问题。嗯，这是我们的 **flash life 预览模型**。所以那是 **3.1 flash life**。嗯，然后我们可以在这里连接。

<details>
<summary>Original English</summary>

**Thor**: Uh great. So what we can do now is now our server is up and running. Uh so we can see um this beautiful interface here which was uh handcrafted. um you know, no agent involved in the creation of this one um back in the day. And so we can just see kind of all the different um knobs here that we have. So we'll try this kind of Google grounding as well. And hopefully it was uh just a thing we need to fix in the UI. Um here's our flash life uh preview model. So that's 3.1 flash life. Uh and then we can uh connect here.

</details>

**Thor**: 所以我们看到了服务器事件。嗯，实际上，也许我再做一次。所以我们说启用 **Google 搜索接地**，连接。所以我们能看到的是我们的**网络套接字**设置。所以如果我们查看网络，我们现在看到我们有这种**网络套接字连接**。所以我们看到我们有我们的**访问令牌**。所以我们的令牌请求到后端。实际上，让我看看。

<details>
<summary>Original English</summary>

**Thor**: And so we see kind of the the server events. Uh actually let me maybe uh do that again. So we say enable Google search grounding connect. So what we can see is kind of our websocket uh setup. So if we look into the network, we now see we have kind of this um websocket connection here. So we see we have our access token. So our token request to the back end. Actually, let me see that.

</details>

**Thor**: 好的，所以你可以看到我们只是得到了我们的令牌。所以，嗯，响应只是我们的 O 令牌，以及它何时过期，嗯，我们发送的有效载荷是什么，我们的有效载荷在哪里？

<details>
<summary>Original English</summary>

**Thor**: Okay, so you can see we're just getting our token. So, um the response was just our O token and when it expires, uh what we sent in terms of the payload, where's our payload?

</details>

**Thor**: 好的，实际上那是没有有效载荷的。嗯，是的，我们只是得到了一个令牌。所以一旦我们有了令牌，我们就会设置我们的**网络套接字**，所以我们可以看到我们的消息。所以基本上，在我们的**网络套接字**中，第一条消息，嗯，我们发送我们的设置配置。所以你看到我们，你知道，发送我们的模型，就像 **Gemini 3.1 flash 预览**一样。我们那里有一些实时输入。我们有工具。所以希望现在 **Google 搜索**应该可以工作了。所以现在我们可以，嗯，开始我们的音频。

<details>
<summary>Original English</summary>

**Thor**: Okay, actually that was no payload. Uh yeah, we're we're just getting a token back. So once we have our token, we then set up our um websocket and so we can see our messages here. So basically the first message in our websocket um we're sending our setup uh configuration. So you see we're you know sending our model as like Gemini 3.1 flash preview. We have some real time uh input there. We have the tools. So hopefully now the Google search uh should work. And so now what we can do is is we can um start our audio.

</details>

**Thor**: 嘿，你能听到我吗？

<details>
<summary>Original English</summary>

**Thor**: Hey, can you hear me?

</details>

**Gemini Live**: 是的，我能听到你，声音洪亮清晰。今天我能为你做些什么？

<details>
<summary>Original English</summary>

**Gemini Live**: Yep, I can hear you loud and clear. How can I help you today?

</details>

**Thor**: 嗯，我正在伦敦，我想知道我需要带伞吗？今天天气怎么样？

<details>
<summary>Original English</summary>

**Thor**: Um I'm in London right now and I'm wondering, do I need an umbrella? What's the weather today?

</details>

**Gemini Live**: 我现在无法获取伦敦的当前天气。抱歉。你最好是快速查看手机上的天气应用程序或在线搜索。那会给你最新的降雨信息。

<details>
<summary>Original English</summary>

**Gemini Live**: I'm not getting the current weather for London right now. Sorry about that. Your best bet is probably to quickly check a weather app on your phone or search online. That'll give you the latest on rain.

</details>

**Thor**: 哦，你杀了我吧。就用 **Google 搜索**。

<details>
<summary>Original English</summary>

**Thor**: Oh, you're killing me. Just use Google search.

</details>

**Gemini Live**: 我很抱歉。我似乎现在无法拉取这些信息。我知道这令人沮丧。你只需询问你的手机或在线搜索，就可以轻松获取天气预报。我会尽力解决这个问题。

<details>
<summary>Original English</summary>

**Gemini Live**: My apologies. I seem to be having some trouble pulling that up right now. I know that's frustrating. You can get the forecast easily by just asking your phone or searching online. I'll try to get this sorted on my end.

</details>

**Thor**: **Gemini**，你为什么要这样对我？那真是太可悲了。

<details>
<summary>Original English</summary>

**Thor**: Gemini, why are you doing this to me? That's just sad.

</details>

**Gemini Live**: 我理解你的沮丧。有时候科技会给我们带来小问题，我很抱歉现在无法为你获取天气。我总是在学习。所以希望下次会更顺利。我还能帮你做些什么吗？好的，那真是痛苦。嗯，我为此道歉。好的，所以。

<details>
<summary>Original English</summary>

**Gemini Live**: I understand your frustration. Sometimes technology gives us hiccups and I'm sorry I couldn't get that weather for you right now. I'm always learning. So hopefully next time will be smoother. Was there anything else I could help you with? All right, that was painful. Uh I do apologize for that. Okay, so

</details>

**Thor**: 肯定有什么问题。那不好。不好。嗯，让我们看看我们是否有更多运气使用**自定义工具**。所以，我们也传入了。我们是否传入了一些**自定义工具**，或者我们的**嗯**，是否有问题？

<details>
<summary>Original English</summary>

**Thor**: something is definitely going on. That is um not good. Not not nice. Um, let's see if we have more uh luck with the custom tools. So, we're also passing in Do we pass in some custom tools or is there actually some issue with our uh

</details>

**Thor**: 嘿，你能给我看一个 hello world 警报吗？

<details>
<summary>Original English</summary>

**Thor**: Hey, can you show me a hello world alert?

</details>

**Gemini Live**: 好了。一个 hello world 警报已经显示。我还能帮你做些什么吗？

<details>
<summary>Original English</summary>

**Gemini Live**: There you go. A hello world alert has been displayed. Anything else I can help you with?

</details>

**提问者**: 是的。你能把页面的背景颜色改成绿色吗？

<details>
<summary>Original English</summary>

**提問者**: Yeah. Can you change the background uh of the page to green, please?

</details>

**Gemini Live**: 没问题。背景颜色现在应该是绿色了。如果你还需要其他帮助，请告诉我。

<details>
<summary>Original English</summary>

**Gemini Live**: You got it. The background color should now be green. Let me know if you need anything else.

</details>

**提问者**: 是的。你能告诉我伦敦现在天气怎么样吗？

<details>
<summary>Original English</summary>

**提問者**: Yeah. Can you tell me what's the weather right now in London?

</details>

**Gemini Live**: 我知道你在问伦敦的天气，但不幸的是 **Google 接地**，但出于某种原因它。是的。所以，有了 **Google 接地**，它应该能工作。所以，我想知道我是不是搞砸了什么。

<details>
<summary>Original English</summary>

**Gemini Live**: I understand you're asking about the weather in London, but unfortunately the Google grounding, but for some reason it's Yeah. So, with the Google grounding, it should work. So, I I wonder if I messed up something.

</details>

**Gemini Live**: 没关系。天气信息不是我能立即获取的，但如果你有其他问题或需要不同功能的帮助，请随时提问。让我们再试一次。

<details>
<summary>Original English</summary>

**Gemini Live**: No worries at all. The weather information isn't something I can grab right now, but if you have any other questions or need help with different functions, feel free to ask. Let's try this again.

</details>

**Thor**: 嘿，你能听到我吗？

<details>
<summary>Original English</summary>

**Thor**: Hey, can you hear me?

</details>

**Thor**: 啊，是的。我们需要一些音频。嘿，你能把背景改回白色吗？

<details>
<summary>Original English</summary>

**Thor**: Ah, yeah. We need some audio. Hey, can you change the the background back to white, please?

</details>

**Gemini Live**: 我也希望我能，但我实际上无法控制你的显示设置。你可能需要查看你设备的设置菜单来更改它。

<details>
<summary>Original English</summary>

**Gemini Live**: I wish I could, but I don't actually have control over your display settings. You might need to look in your devices settings menu to change that.

</details>

**Gemini Live**: 我还能帮你做些什么吗？

<details>
<summary>Original English</summary>

**Gemini Live**: Anything else I can help with instead?

</details>

**Thor**: 哦，不。抱歉。页面之外。页面的背景。改回白色。

<details>
<summary>Original English</summary>

**Thor**: Oh, no. Sorry. Off the page. The the background of the page. Back to white.

</details>

**Gemini Live**: 哦，我明白了。遗憾的是，我仍然无法为你更改。这些外观设置是你正在使用的网站或应用程序的一部分。

<details>
<summary>Original English</summary>

**Gemini Live**: Oh, I see. Sadly, I still can't change that for you. Those appearance settings are part of the website or app you're using.

</details>

**Thor**: 哦，是的。你说得对。嗯，不，但我以为。好的。嗯，禁用了**自定义工具**。那不应该再是这种情况了。好的。嗯，还有很多工作要做。

<details>
<summary>Original English</summary>

**Thor**: Oh, yeah. You're right. Um, no, but I thought Okay. Well, disabled custom tools. That shouldn't be the case anymore. All right. Um lots of work to do

</details>

**Thor**: 但是，嗯，是的，这就是你如何能够，嗯，开始运行。嗯，有人成功在他们的机器上运行了吗？

<details>
<summary>Original English</summary>

**Thor**: but uh so yeah this is sort of how you can um get up and running. Uh did anyone manage to get it running on their machine?

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提問者**: Yeah.

</details>

**提问者**: **Google 搜索接地**工作正常吗？

<details>
<summary>Original English</summary>

**提問者**: Is it is Google search grounding working?

</details>

**提问者**: 没有。

<details>
<summary>Original English</summary>

**提問者**: No.

</details>

**Thor**: 好的。那，嗯，那真可惜。

<details>
<summary>Original English</summary>

**Thor**: Okay. That's uh that's a shame.

</details>

**Thor**: 好的。嗯，我们还有什么？所以，我们需要修复，嗯，很多需要从中吸取教训。嗯，是的，如果你没有得到链接，所以这是 **Live API** 示例的链接。所以，嗯。

<details>
<summary>Original English</summary>

**Thor**: All right. Um, what else did we have? So, we need to fix uh lots of takes away from this. Um, yeah, if you didn't get the link, so this is the link to the live API examples. So, um,

</details>

**Thor**: 它们也从文档中链接。所以，如果你去 **Gemini Life API** 文档，你可以从那里找到它们。

<details>
<summary>Original English</summary>

**Thor**: they also link from the docs. So, if you go to kind of the Gemini life, uh, API docs, you can find them there.

</details>

**Thor**: 嗯，那是我的幻灯片结束了吗？我想我们有，是的，代理技能也是。所以，我的意思是，如果你去 **Gemini Life** 文档，嗯，**Gemini Life API**，嗯，在主文档中，嗯，我们实际上已经从顶部链接了它，嗯，尝试 **Live API**、**Google AI Studio**、GI 应用程序示例或使用**编码技能**。

<details>
<summary>Original English</summary>

**Thor**: Um is that the end of my slides? I do think we have yeah the agent skills as well. So, I mean, if you just go to the Gemini Life, uh, docs, uh, Gemini Life API, uh, and in the on the main docs, uh, we've actually linked it from, uh, the top there, uh, try the live API, Google AI studio, uh, the GI up examples or use the coding skills. Um,

</details>

**Thor**: 所以那是，是的，这就是你如何开始的。酷。那，嗯，不是我希望的结局。嗯，是的，我们会找出哪里出了问题，但是，嗯，是的，感谢大家的参与，是的，我们会回答问题。

<details>
<summary>Original English</summary>

**Thor**: so that is, yeah, that is how you can get started. Cool. That was, uh, not how I was hoping this would go. Um, yeah, we'll we'll figure out what what went wrong there, but um, yeah, I appreciate you all joining and yeah, we we'll take questions.

</details>

### 会话管理与用例讨论

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提問者**: Yeah.

</details>

**Thor**: 是的。所以你可以看看会话管理。所以，嗯，实际上，**Live API** 有这种**上下文窗口压缩**。嗯，所以没有压缩的话，仅音频会话限制为 15 分钟。嗯，音视频会话限制为 2 分钟。嗯，所以这意味着，你将，会话将终止。它会给你这种“走开”面板。嗯，你可以做的是启用**上下文窗口压缩**。所以**上下文窗口压缩**有点像一个，你知道，滑动窗口，你基本上说，你知道，我想要在我的窗口中保留那么多上下文，然后随着对话的进行，它实际上会忘记那个窗口之前的上下文。嗯，所以是的，**上下文窗口压缩**是你能够，嗯，启用的一种方式，可以有一个滑动窗口来延长会话时间，但是，你知道，只有那么多的上下文，这取决于你输入的帧率，就图像而言，这取决于，嗯，是的，主要是图像，音频是，嗯，仅音频会话可以保留更多的上下文在窗口中，但是当你添加视频帧时，它，嗯，会压缩它。

<details>
<summary>Original English</summary>

**Thor**: Yeah. So, you can look at kind of the session management. So um there's actually sort of so the live API has kind of this context window compression. Um so without compression kind of audio only sessions are limited to 15 minutes. Um audio video sessions are limited to 2 minutes. Um so what that means is that sort of you will the session will kind of terminate. it will give you sort of this go away pane. Um, and what you can do is sort of enabling context window compression. So context window compression is kind of like a you know sliding window where you basically say you know like I want to keep that much context sort of in my window and sort of as the conversation progresses it will then actually like forget kind of the previous context before that window. Um so yeah so context window compression is something that you can uh enable kind of you know to have that sliding window to uh make the sessions longer but then you know there's only so much context depending on um the frame rate that you're feeding in in terms of images depending um yeah mostly mostly it's images audio is sort of uh audio only sessions there's more kind of context you can keep in the window but And as you're adding kind of video frames to it, uh it does yeah compress it.

</details>

**提问者**: 嗯，是的。哦，是的。是的。

<details>
<summary>Original English</summary>

**提問者**: Uh yeah. Oh yeah. Yeah.

</details>

**提问者**: 嗯，有没有任何实际的用例，这种功能被用于商业场景中非常具有创造性的？非常。

<details>
<summary>Original English</summary>

**提問者**: Um is there any real life use cases that this is being used for that's very creative from a like a business context? very

</details>

**提问者**: 看看你今天做的事情很有趣，但是把它应用到商业中呢？现在有没有公司真正做得很好？

<details>
<summary>Original English</summary>

**提問者**: see what you've done today is a lot of fun, but like applying it to business. Is there any businesses that are actually doing this really well right now?

</details>

**Thor**: 是的。嗯，我的意思是 **Shopify** 在生产环境中使用了 **Shopify Sidekick**。嗯，有一些，嗯，我真的很喜欢的一个，如果你看 **Gemini Live API** 博客，嗯，我们有一个案例研究，这是一个初创公司。是的。所以我的意思是 **Stitch** 也在使用它。你可以用你的声音进行**代码设计**和**氛围设计**，**Stitch**，但，你知道，**Stitch** 是由 Google 构建的。所以，嗯，你知道，你可能需要折扣它。嗯，**Whimo** 也在集成它。所以，嗯，你知道，我们首先摆脱了车里的司机，然后，你知道，你确实想和车里的人说话，你就可以在未来和 **Gemini** 说话。所以他们正在为此努力。嗯，我喜欢这个。所以这是一个，嗯，**Hey Ado**。嗯，它是一家来自阿根廷的很棒的初创公司。嗯，所以他们正在为老年人构建这些语音伴侣，嗯，结合一个应用程序，嗯，为护理人员或，你知道，老年人的孩子，他们可以收到通知。

<details>
<summary>Original English</summary>

**Thor**: Yeah. Um I mean so Shopify has it in production with Shopify sidekick. Um there is uh a bunch of so like uh actually one that I really enjoy if you Gemini life API blog uh we had kind of a a case study which is um this startup. Yeah. So I mean stitch is using it as well. You can like vibe code vibe design with your voice and stitch but then you know stitch is built by Google. So um you know you probably got to discount that. Um Whimo is also integrating it. So um you know we first we got rid of the drivers in the cars and then you know you do want to talk to someone in the car you can then uh talk to Gemini uh in the future. So they they are working on that. Um I like this one. So this is uh Hey Ado. Um it's a it's a great startup from Argentina. Uh so they are building these um voice sort of companions for the elderly uh in combination with uh kind of an app uh for sort of the caretakers or you know the the the the children of the elderly where you know they can get notifications

</details>

**Thor**: 你知道，如果老年人嘟囔着什么，那不是，所以它是一个非常好的互动，其中多语言性真正发挥了作用，你知道，因为在阿根廷，嗯，你知道，大部分是西班牙语。嗯，但有一个很好的例子你可以看看。嗯，这真的很甜蜜。

<details>
<summary>Original English</summary>

**Thor**: you know should the elderly mumble about something that no but so it's it's a really nice interaction where like the multilinguality um really shines, you know, because like in Argentina, uh you know, a lot of it would be Spanish. Um but there's a nice example you can kind of look at. Um which is really sweet.

</details>

**提问者**: 我来看我的奶奶玛丽亚。我想让你和她打招呼。

<details>
<summary>Original English</summary>

**提問者**: I came to visit my grandma Maria. I want you to say hi to

</details>

**Thor**: 你可以，你可以，你可以在自己的时间看看。嗯，然后我想还有另一个。所以，嗯，是的，它有点像。

<details>
<summary>Original English</summary>

**Thor**: you you can you can look at it in your in your own time. Uh and then I think there was another one. So, um, yes, it is somewhat

</details>

**Thor**: 更多的是未来的音乐用例，只是，你知道，看看一些粗糙的边缘和局限性。我想目前，如果你，你知道，在实际的商业用例中，你可能会，你知道，使用**级联管道**会更好，因为它在管道的每个步骤都为你提供了可观察性。

<details>
<summary>Original English</summary>

**Thor**: more of a future music use case, just kind of looking at, you know, some of the rough edges and limitations. And I think for now, if you're, you know, like in in a real business use case, you might be, you know, better off with kind of the cascading pipeline because it gives you sort of the observability at each step of the pipeline.

</details>

**Thor**: 嗯，这种实时，你知道，原生音频，嗯，你并没有那么精细的控制和可观察性，就插入到，比如说，在响应被说出之前重写它而言。嗯，你知道，显然这在对话的自然流畅性方面有一些好处，但对于某些商业用例来说，它可能还没有到位。所以它有点像，你知道，对未来的一种赌注，即未来的实时对话交互会是什么样子。嗯，但是，是的，取决于你今天的商业用例，它可能还不是最佳选择。

<details>
<summary>Original English</summary>

**Thor**: um which kind of with the the real- time you know native audio um you don't really have that fine grain control and observability in terms of you know plugging into say like rewriting the response before it's being said. Um you know obviously there are certain benefits with that in terms of the natural flow of the conversation but for certain business use cases it might might just not be there yet. So it is somewhat you know a bet in the future of like what uh kind of real-time conversational interactions will look like in the future. Um but yeah depending on your business use case today it might not be the best fit just yet.

</details>

**提问者**: 记录是可调用的吗？

<details>
<summary>Original English</summary>

**提問者**: Are the transcripts allable?

</details>

**Thor**: 嗯，不。所以你在会话中不能检索它们。所以你必须把它们存储在你的端。嗯，再次强调，所以这就是集成合作伙伴的作用。所以如果，嗯，是的，所以 **Lifekit**、**Pipecat** 它们都有很好的产品，可以，你知道，存储整个音频以及整个记录，并为你提供额外的可观察性工具。嗯，所以这不是一种所有可用的东西，你知道，只是从 Google 站点。嗯，所以这是我们目前依赖集成合作伙伴来为你提供额外功能的地方。

<details>
<summary>Original English</summary>

**Thor**: Uh no. So you in the session you can't uh retrieve them. So you would have to store them on your on your end. Um again so that is sort of where the um integration partners come in. So if uh yeah so lifekit pipe cat they all have like really good offerings to you know store the entire audio as well as the entire transcript and sort of give you additional observability tooling on top of that as well. Um, so it's not something that is kind of all available sort of, you know, from just the Google site. Uh, so that's something where currently we're relying on kind of the partner integrations to to sort of give you that additional functionality.

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提問者**: Yeah.

</details>

**提问者**: 哦，抱歉。嗯，你后面。是的。

<details>
<summary>Original English</summary>

**提問者**: Oh, sorry. Uh, behind you. Yeah.

</details>

**提问者**: 你想先去吗？

<details>
<summary>Original English</summary>

**提問者**: Do you want to go first?

</details>

**提问者**: 没有。

<details>
<summary>Original English</summary>

**提問者**: No.

</details>

**提问者**: 好的。嗯，你说这还没有，你知道，完全适用于更复杂的商业用例，但是你对例如用它来代替招聘面试有什么看法？

<details>
<summary>Original English</summary>

**提問者**: Okay. Um so you said that this is not you know like super business ready for more more complex use cases but what are your thoughts for example in um replacing interview interviews for recruitment using this?

</details>

**Thor**: 是的，我的意思是我不确定我是否会，你知道，用它替换你的整个面试流程，但我想这是一个很好的场景，你知道，用于面试过程中的某些步骤，或者，你知道，能够筛选更多的候选人，例如。嗯，是的。

<details>
<summary>Original English</summary>

**Thor**: Yeah, I mean I'm not sure I would, you know, replace your entire interview pipeline with that, but I think it is a great scenario, you know, for certain steps in the interview process or, you know, being able to screen more candidates, for example. Um, yeah.

</details>

**提问者**: 你认为准备好了吗？

<details>
<summary>Original English</summary>

**提問者**: Do you think is that ready?

</details>

**Thor**: 我认为准备好了吗？嗯。

<details>
<summary>Original English</summary>

**Thor**: Do I think that's ready? um

</details>

**提问者**: 因为有很多像嗯上下文你也要提供给它，对吧？尤其即使是像第一次筛选或你提到的快速筛选，你仍然想设置一些标准来指导和**护栏**来指导对话。然后第二部分是。

<details>
<summary>Original English</summary>

**提問者**: because there's a lot of like um context that you also want to give it, right? Especially even if it's like a first screen or the quick screens that you're mentioning, you still want to put some criteria that would guide and guard rails on how to guide the the conversation. And then the second part to this is also

</details>

**提问者**: 它能与例如如果我的公司在谷歌环境中使用 **Google Meet** 吗？我们现在有**自动转录**。所以你能把这些工具放在一起吗？

<details>
<summary>Original English</summary>

**提問者**: can it work for example with if my company is in a a Google environment Google meets right now we have auto transcript. So can you put these tools together?

</details>

**Thor**: 嗯，是的，所以它是一个预览版。所以它是一个你可以在生产中使用的东西。嗯，根据你的用例，我想你需要评估，你知道，你是否需要像 **SOC 2** 那样的东西，可能有很多你需要围绕它构建的东西，才能真正适合你的商业用例。嗯，所以。

<details>
<summary>Original English</summary>

**Thor**: Um yeah so it is uh a preview. So it is something you can use in production. Um depending on your use case I think you need to evaluate like you know do you need like sock 2 sort of there's potentially a bunch of things that you need to build around it for it to actually fit your business use case. Um, so

</details>

**Thor**: 是的，它已经准备好进行实验了。

<details>
<summary>Original English</summary>

**Thor**: yeah, it is ready for experimentation.

</details>

**提问者**: 那有帮助吗？

<details>
<summary>Original English</summary>

**提問者**: Does that help?

</details>

**Thor**: 我的意思是，我想我们正在做很多。

<details>
<summary>Original English</summary>

**Thor**: I mean, I think that's what we're doing a lot in.

</details>

**提问者**: 是的。嗯，哦，是的。

<details>
<summary>Original English</summary>

**提問者**: Yeah. Uh, oh yes.

</details>

**提问者**: 嗯，我总遇到的一个问题是，当我演示语音代理时，很多人都在说话，它无法区分说话者。

<details>
<summary>Original English</summary>

**提問者**: Um, an issue I always have is when I'm demonstrating voice agents, a lot of people are talking and it's it can't differentiate the speakers.

</details>

**提问者**: 彼此之间。那么对此有什么解决方案吗？

<details>
<summary>Original English</summary>

**提問者**: between each other. So is there a solution for this already?

</details>

**提问者**: 是在语音样本上还是在某种程度上。

<details>
<summary>Original English</summary>

**提問者**: It on a voice sample or something in

</details>

**提问者**: 识别不同的说话者。

<details>
<summary>Original English</summary>

**提問者**: terms of like identifying the different speakers.

</details>

**提问者**: 是的。所以它只听你的，如果它是你的代理，例如。

<details>
<summary>Original English</summary>

**提問者**: Yeah. And so it only listens to you if it's your agent for instance.

</details>

**Thor**: 哦，有趣。嗯，它只听你的。

<details>
<summary>Original English</summary>

**Thor**: Oh, interesting. Um it only listens to you.

</details>

**提问者**: 想象一下你有一个**编码代理**，有人恶作剧说“删除文件”或类似的话。你不想那样。

<details>
<summary>Original English</summary>

**提問者**: Imagine you have a coding agent and somebody makes a prank and says delete the file or stuff like that. You don't want that.

</details>

**Thor**: 是的。不，那很有趣。不，我想没有任何特定的能力可以说“只听我的”。嗯，所以有这种主动音频，你可以告诉它只在某些情况下响应，你知道，只对某些上下文响应。所以像忽略与对话不相关的事情。嗯，所以在某种程度上它有效。嗯，但我认为它目前还不是很可靠，你可以说“只听我的，忽略其他人”。

<details>
<summary>Original English</summary>

**Thor**: Yeah. No, that's that's interesting. No, I don't think there's any specific ability to sort of like say just listen to me. Um, so there is sort of kind of this proactive audio where you can tell it to kind of only respond in certain, you know, to certain context. So like ignore things that aren't relevant to the conversation. Um, so to some extent that works. Um, but I don't think it's super reliable at the moment where you'd say like only listen to me, ignore anyone else.

</details>

**提问者**: 我用过 **Nvidia** 的 **Parakeet**，你可以训练 10 秒钟，它就可以区分说话者。但如果能有这样的东西会很好，你和它说话，然后它识别你的声音，忽略其余的声音。

<details>
<summary>Original English</summary>

**提問者**: I've done that with parakeet from Nvidia where you can train a little 10 seconds and it can differentiates the speaker that way. But it would be nice to have something like you talk to it and then it recognizes your voice and ignores the other voices for the rest of the

</details>

**Thor**: 那很酷。那是个很棒的主意。是的。谢谢。

<details>
<summary>Original English</summary>

**Thor**: That's cool. That's a great great idea. Yeah. Thanks.

</details>

**提问者**: 嗯，是的，我想在，在，是的。

<details>
<summary>Original English</summary>

**提問者**: Uh yeah, I think in in the Yeah.

</details>

**提问者**: 思维是什么样子的？嗯，它是用文本思考还是也用语音思考？

<details>
<summary>Original English</summary>

**提問者**: What does thinking look like? Uh is it does it think in text or is also thinking in speech?

</details>

**Thor**: 是的。所以你只能用文本获取思维。所以有文本事件，嗯，在**网络套接字通道**上，嗯，所以你可以选择获取文本形式的思维。是的。它不会说出思维。是的。

<details>
<summary>Original English</summary>

**Thor**: Yeah. So you get the thinking uh only in in text. So there's uh text events uh on the websocket channel that um so you can you can opt into getting the thinking um as text. Yeah. it wouldn't speak out the thinking. Yeah.

</details>

**提问者**: 嗯，感谢演示，嗯，感谢你勇敢地对抗演示之神。嗯，我有一个关于**多模态**方面的问题。嗯，我真正希望好的文本转语音模型的一个领域是让它们以我正在看的内容为基础。就像我编码时，我只想，你知道，向 Cursor 倾泻词语，抱歉，**anti-gravity**，嗯，让它理解上下文，你知道，当我说某个特定的类名时，它应该实际使用它，嗯，这在这个框架中是如何工作的？它会是一种实际进行这种接地的万法，还是你会推荐其他 API 来实现？

<details>
<summary>Original English</summary>

**提問者**: Uh thanks for the demo and uh for being brave to go up against the demo gods. Um I had a sort of question around the multimodality side of things. Uh one of the areas that I really want uh good text to no speechtoext models is having them be grounded in what I'm looking at. like when I'm coding I want to just you know word vomit into cursor sorry anti-gravity uh and have it understand the context and you know when I say something that is a specific class name it should just actually use that um how does that work inside of this framework like would would this be a way to actually do do that grounding or would you recommend some other API for that

</details>

**Thor**: 嗯，这是为了。所以，**通用 Gemini 模型**在**音频理解**方面非常出色。所以，嗯，如果你的用例不需要完全实时的转录，我实际上会建议使用 **Gemini 3 Flash**，嗯，基本上进行转录，同时，你知道，摄取上下文，并基本上获得**上下文感知转录**。

<details>
<summary>Original English</summary>

**Thor**: um and this is for so so general Gemini models are really good at audio understanding. So, um if your use case doesn't require like fully real time transcription, I would actually recommend using like Gemini 3 Flash um to basically transcribe but also get, you know, like ingest context and sort of basically get contextually aware transcription.

</details>

**提问者**: 嗯，同时。并提供多。

<details>
<summary>Original English</summary>

**提問者**: Um at the same time. And provide mult

</details>

**提问者**: 意识。

<details>
<summary>Original English</summary>

**提問者**: awareness.

</details>

**Thor**: 是的，嗯，所以我的意思是根据你的用例，如果你需要它像完全实时的对话一样，嗯，那么是的，所以你可以使用文本来摄取额外的输入，或者，你知道，如果它有意义的话，图像，但那又会，你知道，减少上下文窗口大小，嗯，或者，你知道，如果你不需要完全实时，嗯，那么像使用 **Gemini**，你知道，只是 Flash 来，你知道，转录实际上非常好。

<details>
<summary>Original English</summary>

**Thor**: Yeah, there's uh so I mean depending on your use case if you need it to like be fully real-time conversational um then yeah so you can kind of use text to sort of ingest additional input or you know imagery if it makes sense but then again that you know reduces the context um window size um or you know if you don't need kind of the fully real time um then like using Gemini you know, just flash to, you know, transcribe is actually pretty good.

</details>

**提问者**: 每秒一帧意味着我正在说话，并且你的视觉没有改变，你可以发送输入，然后说话 5 秒钟，而不是发送额外的图像。那样你就没有使用那么多上下文。我想像一张图像大约是 1200 个令牌。所以不是太多。嗯，所以如果你在你的编辑器中，你想要实时，你基本上可以使用 **API**。第一个输入是发送实时图像，然后发送实时音频，然后你基本上停止，模型有图像输入和音频输入，可以响应它。所以你不需要持续流式传输图像，如果你不，如果它没有改变，或者如果你不需要它做出反应。是的。

<details>
<summary>Original English</summary>

**提問者**: Frame per second means I'm talkingual awareness and your visual doesn't change, you can send input, then speak for 5 seconds and not send an additional image. then you are not using so much context. I think like one image is around 1,200 thou 1,200 tokens. So not too much. Um so if you are like in your editor you want real time you basically can use the API. First input is send real time image and then send real-time audio and then you stop basically and the model has the image input and the audio input and can respond to it. So you there's no need to stream the image consistently if you don't if it doesn't change or if you don't need like it to react to it. Yeah.

</details>

**Thor**: 酷。是的。嗯，我想我们还有一点时间，嗯，后面。是的。我们怎么把麦克风给你，还是你只想大声说出来？哦，是的，我们会做的。

<details>
<summary>Original English</summary>

**Thor**: Cool. Yeah. Uh I think we have a bit more time uh there in the back. Yeah. How do we get you the microphone or do you just want to shout it out? Oh yeah, we'll do it.

</details>

**提问者**: 感谢你有趣的演讲。嗯，我有一个关于个性化或适应性的问题。它能识别说话者的水平或交互过程中的知识，然后根据说话者的知识产生结果吗？

<details>
<summary>Original English</summary>

**提問者**: Thank you for your interesting presentation. Uh I have a question about the personalization or adaptation. Can it uh recognize the speaker's level or the knowledge during the interaction and then based on the speaker's knowledge produce the results or not?

</details>

**Thor**: 抱歉，你能再说一遍吗？它能。

<details>
<summary>Original English</summary>

**Thor**: Sorry, can you repeat? Can it

</details>

**提问者**: 它能识别说话者的知识或交互过程中的背景，然后根据说话者的知识产生响应或类似的东西来自我个性化吗？所以你，你想要摄取某种初始上下文。你是这个意思吗？

<details>
<summary>Original English</summary>

**提問者**: can it recognize the speaker's knowledge or the background during the interaction to produce the response based on the speaker's knowledge or something like that to personalize itself? So you you want to ingest kind of initial context. Is that what you're saying?

</details>

**提问者**: 不是上下文。例如，假设我正在和它谈论土木工程，并且它能识别我是一名土木工程师，然后根据我的知识产生结果，使用土木工程中的高级关键词，或者不。

<details>
<summary>Original English</summary>

**提問者**: Not context. For example, suppose I'm talking to that about the civil engineering and candidate recognize I'm a civil engineer and based on my knowledge produce the result use the advanced keyword in civil engineerings or not

</details>

**Thor**: 根据我的知识。所以你必须，如果你有像专业知识，你必须让它访问。哦，那意味着它没有任何记忆来识别人类的背景，或者找到信息的主要上下文，或者交互，然后根据它产生下一个结果。

<details>
<summary>Original English</summary>

**Thor**: based on my knowledge. So you would you would have to if it's like special specialized knowledge you would have to give it away to access that. Oh, that mean doesn't have any memory to recognize the human's background or to find the main context of the information of the interaction and based on that produce the next result.

</details>

**Thor**: 所以你必须以某种方式输入这些知识。所以你可以在你设置会话之前这样做，例如，你可以将知识作为初始上下文摄入，然后它就在上下文中讨论，或者你可以在会话期间给它函数调用来访问知识，就像你交谈时一样。

<details>
<summary>Original English</summary>

**Thor**: So you have to somehow feed in that knowledge. So you could either do that sort of before you you know like as you set up the session you can ingest kind of the the knowledge as initial context for example and then it has that in context to talk about or you would give it kind of function calls to access knowledge sort of during the session as you as you converse.

</details>

**提问者**: 是的，我明白了。谢谢你。那。

<details>
<summary>Original English</summary>

**提問者**: Yeah I see. Thank you. that

</details>

**提问者**: 是的，我知道我曾经找过，嗯，例如 **GPT**，在某些回合中，它可以找到说话者或用户的知识，或信息的主要概念，然后根据它，**GPD** 可以产生一些结果，这意味着它一步一步地逐渐个性化到对话的主要上下文，所以我的问题是，它能否一步一步地自我个性化到交互的主要上下文，然后产生一个结果来指向。

<details>
<summary>Original English</summary>

**提問者**: yeah know I was to find that uh look out the GPT for example during the some turns it can find speakers or the users knowledge or the main concept of the information and based on that the GPD can produce some results that means a step by step gradually it personalize to the main context of the conversation so my question is can it a step by step personalize itself to the main context of the uh of the interaction and then produce a result to point to the uh

</details>

**Thor**: 所以只要上下文在会话期间保持在**上下文窗口**内。

<details>
<summary>Original English</summary>

**Thor**: so like as long as the the context stays within the context window during that conversation.

</details>

**Thor**: 是的。它可以识别不同的说话者，并记住对话中说了什么，如果他们也用自己的名字介绍自己，它就可以记住那个人的名字，所以，是的，那就是 **Gemini** 的**音频理解**。

<details>
<summary>Original English</summary>

**Thor**: Yeah. It it would it can like it can identify different speakers and sort of remember what was said in the conversation and like if they introduce themselves with their name as well it can remember kind of that person's name and so like yeah that's kind of the the the audio understanding sort of within Gemini.

</details>

**提问者**: 谢谢你。

<details>
<summary>Original English</summary>

**提問者**: Thank you.

</details>

**Thor**: 好的，酷。

<details>
<summary>Original English</summary>

**Thor**: Okay cool.

</details>

**Thor**: 嗯，是的，你想把麦克风传过去吗？

<details>
<summary>Original English</summary>

**Thor**: Uh yeah do you just want to pass it forward there?

</details>

**提问者**: 是的。

<details>
<summary>Original English</summary>

**提問者**: Yeah.

</details>

**提问者**: 嗯，谢谢你精彩的演讲。嗯，你能分享一下你如何评估这些实时语音应用程序的经验吗？因为我想这会比典型的应用程序复杂得多。

<details>
<summary>Original English</summary>

**提問者**: Uh thanks for the nice presentation. Uh could you share maybe some um of your experience on how to evaluate these um live uh voice apps because I can imagine that this becomes a lot more complicated than typical apps.

</details>

**Thor**: 嗯，是的，我的意思是它肯定取决于你的用例，就你的要求而言，你知道，你是否有 **HIPPA**？你是否有 **SOC 2**？函数调用的数量是多少？**护栏**的数量是多少？所以肯定有很多，你知道。

<details>
<summary>Original English</summary>

**Thor**: Um yeah I've so it definitely depends on your use case in terms of like uh you know like what are your requirements in terms of you know do you have HIPPA do you have sock 2 like what is the amount of function calls the amount of guardrails so there's definitely a lot you know

</details>

**Thor**: 这些演示很好很有趣，但是把它带到商业环境中，肯定有更多的步骤。所以这就是集成合作伙伴的作用。所以，嗯，你知道，**Lifekit** 已经围绕语音代理构建了他们的整个业务，为你提供了所有电池，所以我建议，如果你，你知道，在寻找实际的商业用例时，可以考虑合作伙伴集成。谢谢。

<details>
<summary>Original English</summary>

**Thor**: these demos are nice and and fun but like to bring that in a b business context there are definitely a lot more um steps involved and so that is kind of where the partner integrations come in. So uh you know lifekit has built kind of their entire business around sort of giving you all the batteries around sort of voice agents and so I would recommend if you know sort of looking at the partner integrations for the sort of real business use cases potentially. Thanks.

</details>

**Philip**: 酷。

<details>
<summary>Original English</summary>

**Philip**: Cool.

</details>

**Thor**: 是的。

<details>
<summary>Original English</summary>

**Thor**: Yeah.

</details>

**提问者**: 我希望你不介意我问一个关于 **Interactions API** 的简单问题。回到之前的话题。

<details>
<summary>Original English</summary>

**提問者**: I hope you don't mind if I just ask a simple question about the Interactions API. Going back to the previous talk.

</details>

**Philip**: 是的，请问。

<details>
<summary>Original English</summary>

**Philip**: Yes, please.

</details>

**提问者**: 什么时候能在 **Vertex** 上使用？

<details>
<summary>Original English</summary>

**提問者**: When's that going to be available on Vertex?

</details>

**Philip**: 嗯，希望很快。我的意思是，如果你和一些 Google Cloud 的人、一些 **Vertex** 的人说话，你告诉他们越多，“我需要在 Google Cloud 上使用它”，它就会变得越容易。

<details>
<summary>Original English</summary>

**Philip**: Um, hopefully soon. I mean, if you speak to some Google Cloud person, some Vertex person, the more you tell them, I need it on Google Cloud, the the easier it gets.

</details>

**Philip**: 我们会做的。

<details>
<summary>Original English</summary>

**Philip**: We'll do.

</details>

**Thor**: 是的，这肯定不在我们的控制范围之内。

<details>
<summary>Original English</summary>

**Thor**: Yeah, it's certainly not in our control.

</details>

**Philip**: 好的。是的，那不好。那不好。那很酷。我的意思是 **API** 会是一样的。所以你今天就可以开始在 **Gemini API** 上，嗯，开始测试。如果你需要更高的**速率限制**，其他任何东西，你都可以随时联系我们。如果你需要 **Vertex 企业版**的特定功能，那么你可能需要等待一段时间。我能问一下，就 PII 而言，在任何对话历史中，你是否知道它是如何存储的，就数据主权而言？你能指定自己的数据源吗？还是这一切都由后端处理，嗯，就像 **API** 内部一样？

<details>
<summary>Original English</summary>

**Philip**: Okay. Yeah, that's bad. That's bad. That's cool. I mean it the API will be the same. So you can start today on Gemini API uh start testing. If you need higher rate limits, anything else you can like always reach out. If you need vertex enterprise specific features, then you might need to wait a little bit. Can I ask like in terms of like PII in any like conversation history, do you know how that's like stored in terms of like like data sovereignty? Can you specify your own data sources or is that all handled like back end um with with like within the API?

</details>

**Philip**: 所以你总是可以禁用存储任何东西。所以我们有一个 `store equals false` 标志。所以我们不会存储任何东西，但**不存储**意味着没有**服务器端状态**。所以如果你想使用这个，对于其他 **Vertex** 功能来说有点困难，就**数据主权**而言，你调用模型的方式，我期望它们会类似于**生成内容**，所以如果他们今天有它，他们将来也会有它。好的，酷。那很棒。谢谢。非常感谢。

<details>
<summary>Original English</summary>

**Philip**: So you can always disable storing anything. So we have a store equals false flag. So we would not store anything but not storing means no serverside state. So if you would like to use this that's a bit difficult for other vortex features in terms of data soy where you call the model I would expect them to be like similar to generate content so if they have it today they will have it there in the future as well. Okay, cool. That's great. Thanks. Appreciate it.

</details>

**Thor**: 酷。嗯，最后一个。

<details>
<summary>Original English</summary>

**Thor**: Cool. Uh, one last one.

</details>

**提问者**: 没有。好的。啊。

<details>
<summary>Original English</summary>

**提問者**: No. Okay. Ah,

</details>

**提问者**: 抱歉。

<details>
<summary>Original English</summary>

**提問者**: sorry.

</details>

**提问者**: 不，请。

<details>
<summary>Original English</summary>

**提問者**: No, please.

</details>

**提问者**: 谢谢你。所以，我有一个关于**幻觉**的问题。所以我们。

<details>
<summary>Original English</summary>

**提問者**: Thank you. So, I have a question about u hallucinations. So, we

</details>

**Thor**: 抱歉，什么？

<details>
<summary>Original English</summary>

**Thor**: Sorry, the what?

</details>

**提问者**: **幻觉**。是的。所以你展示了一些关于天气的例子，效果不太好。嗯，但是，嗯，你的客户在生产中如何处理这些问题？因为我想对于我们在这里看到的一些例子来说，这没问题，但是，嗯，在现实生活中，这是另一回事。那么你能给出一些最佳实践或者如何处理这些问题吗？

<details>
<summary>Original English</summary>

**提問者**: Hallucinations. Yes. So you've have shown some examples uh with the weather that didn't work so well. Uh but uh how do your clients actually deal with that stuff on production? Because I can imagine that for like some examples that we've seen here this is fine but uh in real life this is a different story. So can you give some best practices or how to deal with that?

</details>

**Thor**: 是的，当然。嗯，所以我的意思是，对于演示，演示中肯定缺乏最佳实践，就**系统指令**而言，你知道，你可以通过更好的**系统指令**做很多事情，让代理实际遵循**系统指令**，而不是，你知道，偏离轨道，像**幻觉**天气。嗯，所以，是的，我想我们有，有一些最佳实践讲座。嗯，所以我建议你去看一下那些。我们也有一个示例，你知道，如何构建你的**系统提示**，并在其中设置你的**护栏**、指南和，嗯，工具定义。一旦你构建了它，嗯，代理在遵循**系统指令**和保持在这些参数范围内方面会好很多。

<details>
<summary>Original English</summary>

**Thor**: Yeah definitely. Um, so I mean on for the demos the there's definitely a lack of best practices in terms of like system instructions and you know there's a lot that you can do sort of with uh the you know better system instructions to uh have the agent actually follow um the system instructions and not you know go off and like hallucinate the weather for example. Um, so yeah, I think we we have like there's some best practices do talks. Um, so I'd recommend kind of going through through those. We have an example as well sort of, you know, how to sort of structure um your your system prompt and sort of put you know your guardrails in there, guidelines and um kind of the tool definitions as well. And so once you build that up, uh, the agent gets a lot better, you know, at following the system instructions and kind of staying within those those parameters.

</details>

**Thor**: 酷。酷。嗯，是的，非常感谢大家。我，我为这些小故障道歉，但我们学到了一些东西，我们会改进它。嗯，但是，是的，希望你们都能试用一下，嗯，你知道，在接下来的几天里告诉我你发现了什么，并告诉我你的反馈。谢谢。再见。

<details>
<summary>Original English</summary>

**Thor**: Cool. Cool. Um, yes, thanks so much everyone. I I do apologize for the hiccups, but we we learned something and we'll we'll improve upon it. Uh, but yeah, would love for you all to test it out and um, you know, let me know over the next couple days. I'll be around what you find and let me know your feedback. Thank you. Cheers.

</details>