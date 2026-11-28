---
author: a16z
date: '2026-11-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kBJe4H_WobA
speaker: a16z
tags:
  - context
  - user-modeling
  - confidential-computing
  - personal-agent
  - privacy
title: 构建真正了解你的AI：First Person Labs 与个人管家 Second 的系统架构
summary: First Person Labs 创始人 Ken 介绍了其产品 Second。Second 通过持续分析计算机本地原生事件与多渠道数据构建用户模型，并利用机密推理与端到端加密保障隐私。它作为可信上下文层与各类外部 Agent 协同，实现无需主动提问的反思型生产力支持。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - First Person Labs
products_models:
  - Second
media_books: []
status: evergreen
---
### 引言与核心理念

>> 人们严重低估了计算机现在已经掌握了多少信息。你不再需要向你的编程 Agent 解释任何事情。你只需截取任何屏幕截图，然后说修复，它就会知道你要修复什么。接下来的问题就是，你能否直接对它进行彻底的分析？
<details><summary>Original English</summary>
>> People are very underestimating how much the computer already knows. You no longer have to explain anything to your coding agents. You can just screenshot anything and just say fix and then you would know what you're fixing. The question then is like, well, can you just like analyze the heck out of it?
</details>

>> Grockbot 有哪些 First Person Labs 能够提供而它目前缺乏的上下文？
<details><summary>Original English</summary>
>> What context does Grockbot not have that first person labs would allow?
</details>

>> 目前最大的痛点之一就是人们不得不去提问。[音乐] 你本不应该需要去问问题，它们是超级智能。但如果你有一个能自主构建的用户模型，然后这些机制一直在后台持续分析，你就可以直接即时共享这些上下文。我们的核心业务实质上是创建一个个人的模型，然后让这个人掌握控制权。
<details><summary>Original English</summary>
>> One of the biggest bugs right now like people have to ask. [music] You're not supposed to ask things. They're super intelligent. But if you have a user model that just builds up by itself and then these things just keep analyzing in the background, then you can just share that over instantly. We focus on essentially creating a model of a person and then put that person in control
</details>

>> 当人们想到这东西能看到你所做的一切时，[音乐] 会立刻产生一种“哇”的顾虑。
<details><summary>Original English</summary>
>> when people think about this thing sees everything [music] you do. There's an immediate sort of like wo
</details>

>> 如果你比如不信任我们，原则上你应该能够自带 token，去分析本地笔记本电脑上的数据。[音乐]
<details><summary>Original English</summary>
>> if you don't trust let's say us in principle you should be able to bring your own tokens to then analyze data [music] that's on your laptop locally.
</details>

>> 你能谈谈你在开发中发现的最令人惊讶的用例吗？事实证明……
<details><summary>Original English</summary>
>> Can you talk through what you think are like the most surprising use cases that you found for development? It turns out that
</details>

### First Person Labs 与 Second 的定位

>> 感谢 Ken 今天的到来。非常高兴能邀请你来聊聊你在 First Person Labs 所做的工作。这是你第一次公开谈论它吗？
<details><summary>Original English</summary>
>> Thank you, Ken, for joining us. Really happy to have you on to talk about uh what you've been working on at First Person Labs. Is this the first time you're talking about it?
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 是的。那么，你们具体是做什么的？
<details><summary>Original English</summary>
>> Yes. So, what do you do?
</details>

>> 我们核心关注的是构建一个人的模型，并让这个人拥有控制权。所谓人的模型，基本上意味着理解他们的记忆，理解他们做的事情，但更重要的是理解他们的优先级、偏好、目标、价值观、承诺和意图。
<details><summary>Original English</summary>
>> So, we focus on essentially creating a model of a person and then put that person in control. And the model of a person basically means that understanding their memories, understanding what they do, but more of that uh their priorities, preferences, goals, values, and commitments and intent.
</details>

>> 抱歉，我们先把它说得非常简单直观。我是 Grockbot 的重度用户，我经常用 Crockbot。那么 First Person Labs 会如何融入我对 Grockbot 的日常使用中？
<details><summary>Original English</summary>
>> So, I sorry, just let's just make this very simple. I'm a big Grockbot user. So, I use Crockbot a lot. Where would first-person labs fit into my usage of Grockbot?
</details>

>> 是的，它的工作方式就是你可以直接把上下文带到 Grobot。嗯，它就像是一种可移植的上下文。你去到 Grobot 并说：“嘿，你能和我那个东西沟通一下，弄清楚我想要什么吗？”然后它们两个就会开始对话，之后你就可以直接发送提示词，比如：“帮我买张机票。”它就会知道你在说哪趟航班。
<details><summary>Original English</summary>
>> Yeah, the way the way it works is that you would just bring a context over to Grobot. Um, it's like portable context. You go to Grobot and you say, "Hey, can you talk to my thing to figure out what I want and then the two of them will start talking and then you can just send prompts like, "Oh, buy me a flight." And you would know what flight you're talking about.
</details>

>> Grockbot 有哪些 First Person Labs 能提供而它本身没有的上下文？
<details><summary>Original English</summary>
>> What What context does Grockbot not have that first person labs would allow?
</details>

>> 我可能会反过来问，First Person 有什么？你为自己建立了一个用户模型，对吧？比方说你对飞机座位的偏好，你希望提前多久到达机场的偏好，以及你要飞往哪里，你是坐头等舱还是普通舱等等所有这些。截至今天，你必须向它解释这些，必须经历多轮询问。但如果你有一个用户模型，或者一个能自主构建的模型视图，而且这些后台进程持续在后台分析，那么你就可以即时把这些信息共享过去。
<details><summary>Original English</summary>
>> I would ask I was probably asked the opposite question like what what what does first class not have you build a user a model for yourself right let's say your preferences on the seat on your airplane the preferences of your uh uh how early you would like to arrive at the airport and um where are you flying uh are you flying first class or or or normal and all of that right as of today you have to explain that to you have like okay there's multiple rounds of like questioning but if you have a user model or like a model view that just builds up by itself and then these things just keep analyzing in the background Mhm. Then you can just share that over uh instantly.
</details>

>> 例如，OpenAI 昨天发布了两个具备网络能力的新模型，我已经有一段时间没用我的 Codex 了。但我一直在用 Second。所以我可以直接开始使用 Codex，它就已经拥有了我已经完成的所有其他工作，以及所有已保存的额外上下文。
<details><summary>Original English</summary>
>> So for example, the open AAI released two new cyber capable models yesterday and I haven't been using my codecs in a while. But I have been using second. So I can just go start using codeex and it has all the other work that I've already done and all the additional context already saved.
</details>

>> 是的，是的。你只需转到 Codex，它就是我的 Second。太棒了。
<details><summary>Original English</summary>
>> Yeah. Yeah. Um you just go to Codex and it's my second. What's awesome?
</details>

>> Second 未来会变成第一人称视角吗？它会直接面对用户，还是始终通过其他 Agent 来运作？
<details><summary>Original English</summary>
>> The second ever be a first person? Will it ever be a first or will it always go through agents?
</details>

>> 嗯，这是个好问题。我认为用户模型是一个演进过程。你必须从某个地方开始。你从一份基线性的基础物料清单开始：你做过什么、你生活中有哪些人，也许还有你的偏好。随着时间的推移，它开始分析你的说话方式、自我展现的方式、分享信息的方式。是的。
<details><summary>Original English</summary>
>> Uh I that's a good question. I think user model is a it's a it's a it's a process. You have to start somewhere. You start with a baseline foundational list of artifacts, what you did, uh who are the people in your life, maybe your preferences. And over time, it starts analyzing like the way you talk, the way you uh present yourself, the way you share information. Yeah.
</details>

>> 随着时间的推移，你会在其上构建出更多的物料和更深层的理解。有些东西你或许还会训练到模型中。因此，随着时间的推移，你将从单纯的可移植上下文演变成更能代表你自身的存在。我喜欢想到的一个例子就是蝙蝠侠和阿福的例子：假设蝙蝠侠想买个芝士汉堡，然后让阿福去办。阿福不会对外透露是蝙蝠侠在买，他只会直接去买下来，他会替他表达偏好。
<details><summary>Original English</summary>
>> And over time, you would like build up even more artifacts on top and more understanding on top. And maybe some of that you train into the model. And so um over time you will go from a portable conx into something more of a representation of yourself. Um one example I like to think of is this like um Alfred Batman example where if let's say Batman wants to buy buy a cheeseburger and then get Alfred to do it. Um Alfred would not reveal for example that is Batman doing it but he would just buy it. He would state the preference.
</details>

>> 阿福是蝙蝠侠的管家。
<details><summary>Original English</summary>
>> Alfred being Batman's butler.
</details>

>> 哦，是的，是的。
<details><summary>Original English</summary>
>> Oh yes yes.
</details>

>> 或者是他的 Agent。
<details><summary>Original English</summary>
>> Or his agent.
</details>

>> 是的，是的，或者说是他的 Agent。
<details><summary>Original English</summary>
>> Yeah. Yeah. Or his agent.
</details>

>> 或者 [笑声] 他的 Agent。
<details><summary>Original English</summary>
>> Or [laughter] his agent.
</details>

>> 是的，是的，我应该把我的英文名改叫这个。
<details><summary>Original English</summary>
>> Yeah. Yeah, I should call my English.
</details>

>> 这是个好主意。
<details><summary>Original English</summary>
>> That's a great idea.
</details>

>> 你就去执行。他会替你去办，然后你会信任他们，因为你知道他们对你有一个很好的模型理解，也知道在办成事情这方面这意味着什么。
<details><summary>Original English</summary>
>> You just do it. Um, you he'll just do it and then uh you you'll trust them because you know that they have a good model of view and uh what that means when it comes to getting things done.
</details>

### 数字上下文获取与底层系统工程

>> 这很有意思。你把 First Person Labs 描述为拥有这个被称为 Second 的产品。Second 理解你是谁并拥有上下文，然后其他 Agent 与这个 Second 对话，对吧？它能在某种程度上理解你的偏好，理解你正在做什么以及你想做什么。但我认为这其实还没有凸显出你一直在努力攻克的另一件事，我认为这很值得聊聊：你实际上能够获取一个人的数字上下文，比如消息、聊天记录以及某种形式的电子邮件，并让这些也变得可用。你能稍微谈谈这一点吗？作为 First Person Labs 最早期的用户之一，最让我震撼的不是它知道我是谁，而是它能非常顺畅地接入我所有的渠道。顺便说一句，事实证明这是一个极其困难的系统工程问题。所以或许可以多聊聊你们正在做的这方面。
<details><summary>Original English</summary>
>> It's it's interesting which is like so you you describe person lab as is having this thing called a second. The second understands who you are and has context and then other agents talk to that second, right? And so like it kind of understands your preferences. It understands what you're doing, what you want to do. Um but I I think that that actually doesn't highlight another thing that you've been working very hard on and I think it's worth talking about is like you're actually able to get access to context um digital context that a person has like messages, chat kind of email in a way and make that also available. So can you talk a little bit about that? Like so here being a one of the earliest first-person lab users I would say the thing that struck me was that not that it knew who I was but more it had access to all of my channels very well. So maybe and then by the way which turned out to be a very hard systems problem. So maybe talk a little bit about that aspect of what you're doing.
</details>

>> 是的。这确实是一个非常棘手的问题，尤其是要做到安全和私密。它的大致工作原理是：现在在你的计算机上，随着你使用电脑，会产生无限的事件流——比如你切换的应用、你在某些网站上的停顿、你打字的方式，以及你的 Wi-Fi 连接状态，操作系统本身就已经提供了这些。涵盖了 Apple、微软甚至是 Linux。接下来的问题就是：你能否直接对这些原始数据流进行 24/7 全天候的彻底分析，在其之上运行 24/7 全天候的 Agent？这样我首先可以进行综合归纳，例如：在某个特定应用中的这串打字可能意味着你正在发消息；当你在浏览器和 Codex 之间切换应用时，你可能是在查资料，也可能是在写 Google 文档。你自下而上分层构建出这种理解，再加上现有的各类连接器，就能非常准确地理解你想要做什么。我认为人们严重低估了计算机已经掌握的信息量，那些数据就静静躺在那里，等待被挖掘。
<details><summary>Original English</summary>
>> Yeah. Um it is indeed a very hard problem especially to get it secured private. Um so the way it roughly works is that right now on your computer um there's like an end infinite end infinite stream of events as you use your computer you know the apps that you switch to the way you pause in certain websites the way you type and the way like your Wi-Fi is connected and that the OS already gives you um this is across Apple Microsoft and even Linux um and the question then is like well can you just like analyze the heck out the heck out of it right like this raw stream 24/7 apply agents on top 247 agents. So I can first synthesize for example well this piece of typing at this particular app might mean that you're sending a message and then when you're switching apps between uh uh the browser or back to your codeex you might be like you know doing some research you might be writing a Google doc and you kind of hierarchically build up that understanding and that plus you know existing connectors can give you a very good understanding of what you're trying to do. Um I think people are very underestimating like how much the computer already knows is there sitting there you know waiting to be tapped so to speak.
</details>

### 反应型生产力与反思型生产力

>> 作为该产品的极早期使用者，最近它简直成了不可或缺的工具。因为它能捕捉到很多细节，它现在会给我发消息，提醒我：“嘿，你和这个人正在聊这件事，情况似乎发生了变化。”比如我们昨天在筹备一个活动，当时有 20% 的降雨几率，它就实时持续为我们更新天气预报，提示我们是否需要准备帐篷。这真的非常强大。
<details><summary>Original English</summary>
>> Well one of the interesting having been a also a very early adopter of the product um lately it's been just indispensable because it's able to catch it's sending me um messages now and letting me know that hey you've you've got this conversation going on over here with this person and it looks like the situation has changed. So, we were planning an event yesterday. There was a 20% chance of weather and in real time it was continually updating the forecast for us to let us know if we needed to get a tent or not. Um, which is just like incredibly powerful. Like,
</details>

>> 是你要求它这么做的吗？
<details><summary>Original English</summary>
>> did you ask it to do that?
</details>

>> 不，我根本没有要求它做这件事。
<details><summary>Original English</summary>
>> No, I did not ask it to do that.
</details>

>> 这也是我对我的 Second 的体验。真的就像是我会收到来自我的 Second 的短信，内容恰恰是我针对某段正在进行的对话确实需要了解的事情，而我自己甚至都没想过。它确实非常周到贴心。
<details><summary>Original English</summary>
>> This is my exper this my experience my second too. Like it's literally like I'll get a text from my second and it's like something that I actually need to know about relative to like some ongoing conversation that I didn't even think about that like it actually is very thoughtful.
</details>

>> 是的，太不可思议了。我真的很好奇你们具体是怎么执行这一点的？那些我本会遗忘的事情，它居然能敏锐地捕捉到。
<details><summary>Original English</summary>
>> Yeah. Yeah. And so like it's just it's amazing like I just I'm genuinely curious like how are you executing on that like things that I would have forgotten it's literally catching.
</details>

>> 是的，这又回到了人的模型上，也就是理解对用户而言什么可能是重要的，以及在此刻会出现什么。我认为生产力是人们常谈的话题，比如在需要的时候给你发提醒。但生产力有很多层级。我会将第一级称为“反应型生产力”。这意味着比如来了一封邮件——网上有个梗，说你不要收到 10 条邮件通知，因为有 9 个其他个人 Agent 在为你提醒这封邮件。反应型生产力很直接，很容易做。但更难的是我所说的“反思型生产力”，它跨越许多事件和较长的时间跨度去把各个点串联起来。比如能意识到：“几个月前你说了这句话，最近你正为了目标做这个努力。这是你的优先级，这些是待办清单上的事项，顺便说一句，你更偏好这个。”通过这种串联，它能够为你提供高得多的生产力。我认为这也暗示了未来人机交互的走向：它不会只专注于对事物做出反应，而是更多转向：“好的，有哪些我可以为用户实施的干预？有哪些是我无需任何询问就能为用户做的事情？”我认为这是目前最大的瓶颈之一，也就是人们非得去主动发问。对于超级智能而言，你本不应该需要事事去问。
<details><summary>Original English</summary>
>> Yeah. Yeah. So this goes back to the model of the person understanding what's you know might be important to them and what comes up at at the at this point. So I think productivity is something that people talk a lot about like pinging you um as pinging you when at the time of need. But there are many levels of productivity. Um I would start like for example the first level which is called reactive ones. These this means like there's an email came in and then there's a meme right online that's you not get 10 notifications for email because um there are nine other personal agents paying you about that. Um, reactive productivity is like straightforward, easy to do. But what's harder is what I call reflective ones, which are things that connect the dots over like uh many events and long time horizon, right? Stuff that realize, okay, months ago you said this and recently you're working this towards your goal. This is your priority. These are some stuff on your to-do list and by the way, you prefer this. And so kind of like connecting the dots will be able to give you much better productivity. And I think that's kind of hints at like how maybe in the future personal like interactions with computers would go like it would not be focused on reacting to things but more like okay what are some you know interventions for the user that I can apply to? What are some things that I can um and do for the user without any asking? I think that's one of the biggest bottness right now like people have to ask. You're not supposed to ask things super intelligence.
</details>

>> 是的。你打造出的东西能大致知道我当下需要什么，这非常令人印象深刻。
<details><summary>Original English</summary>
>> Yeah. I mean, you've built something that just kind of knows what I need at the moment. That's pretty impressive.
</details>

### Second 的架构：唯一管家与安全边界

>> 我想向听众非常具体地梳理一下 First Person Labs 到底提供了什么，然后我有个问题。具体来说，它创建了一个叫做 Second 的实体。Second 可以访问你所有的数字上下文。这太神奇了，比如按键操作、你所有的消息、所有的频道、所有的数据。它以非常安全的方式完成这些。在此基础上，它基本上成为了你的私人管家——我喜欢阿福这个比喻——然后它再与你的其他 Agent 进行交互。
<details><summary>Original English</summary>
>> So, I I just I just want to make it very concrete for the people that are listening on what first person labs provides. Um, and then I've got a question. So, so very concretely, um, it creates this thing called a second. So, you create something called a second. Second has access to all of your digital context. I mean, it's amazing. It's like key strikes, uh, all your messages, all your channels, all your data. It does this a very secure way. And based on that, it becomes basically your kind of personal butler. I like that Alfred, right? And so and then that interacts with your agents.
</details>

>> 所以它本身并不是一个常规 Agent。它不同于用户本能或 Grockbot，它是一个独立的实体。
<details><summary>Original English</summary>
>> So it's not an agent by itself. So this isn't like user instinct or Grockbot. It's its own or dot it's its own thing.
</details>

>> 然后它把这些信息提供给其他 Agent，对吧？这就是它的本质。
<details><summary>Original English</summary>
>> Um and then it provides that to the agents, right? So that's what it is.
</details>

>> 这里有个有趣的地方。对我而言，我是 Grockbot 的重度用户，我有一大堆 Grockbot。一个用来跟踪我的合成器，一个用来打理我的房地产，还有一个帮我处理家庭事务——虽然我本不应该需要它，但我确实用了。我有这么一堆 Agent，然后我有一个 Second，它们都会与这个 Second 交互。你设想随着时间的推移，人们会拥有第二个、第三个、第四个、第五个 Second，还是说它最终就只是你唯一的那位管家？
<details><summary>Original English</summary>
>> So here's an interesting thing. So for me, um so I I use Grockpot. I'm a big Grockbot user and I have a bunch of them, right? I have one that keeps track of like my synthesizers, one that keeps track of my real estate, one that you know, god forbid, helps me with my family, which I probably shouldn't need one, but I do, you know? So I just got a bunch of these. Um, and then I have one second and they they will interface with the second. Do you imagine over time you'll have a second and a third and a fourth and a fifth or do you think that it just, you know, ends up being your one butler?
</details>

>> 我认为目前拥有许多个人 Agent 的现状可能是暂时的。Agent 会像人类一样走向专业化。有些 Agent 专注于一件事，有些 Agent 比如专门负责浏览亚马逊和购物，因为它们拥有相关数据和连接通道，所以在这方面极其擅长。而有些 Agent 则专门负责保护你的数据并符合你的利益。
<details><summary>Original English</summary>
>> I think right now the the fact that we have many personal agents is probably transitory like agents will start to specialize just like people do. Um, some agents focus on one thing. Some agents focus on, they say for example, browsing Amazon, shopping. Yeah. They're extremely good at because they have the data, they have the connections. Yeah. And some agents will specifically focus on protecting your data and lining with your interests.
</details>

>> 我认为这正是 Second 的定位：这是一个你应当能够信任、用它来容纳你一生的上下文的载体。它就像一个保险库。
<details><summary>Original English</summary>
>> Um, I think that's what second is intended to be like this is something that you can should be able to trust to have your life's context in it. It's like a vault
</details>

>> 随着时间的推移，这个东西会引导你，与软件世界甚至硬件世界进行交互对接。
<details><summary>Original English</summary>
>> and then over time, you know, this thing will like guide you with you like, you know, interface with the kind of the software world so to speak or even the hardware world.
</details>

>> 所以你认为它会保持为单一的 Second？只有 Second，不会有第三个。
<details><summary>Original English</summary>
>> So, you think it'll stay as a second? Yeah, you'll see a second. There will not be a third.
</details>

>> 不会有第三个，也不会有第四个。它就是你唯一的受信任 Agent。
<details><summary>Original English</summary>
>> There will not be a third. There will not be a fourth. So, like your one trusted
</details>

>> 掌握你所有的个人数据、真正了解你是谁，并与你所有其他 Agent 交互的 Agent。这就是 Second。
<details><summary>Original English</summary>
>> agent for all your personal data that actually knows who you are that will interact with all your other agents. That's second.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah,
</details>

>> 就像是蝙蝠侠的保险库。
<details><summary>Original English</summary>
>> it's Batman's safe.
</details>

>> 是的。你可以启动那些短暂存在然后销毁的子 Agent。但关键在于你希望拥有一个持久一致的存储库，正是这种持久存储为你带来了价值。
<details><summary>Original English</summary>
>> Yeah, you what you can do is like spin up sub agents that you know temp ephemerally exist and then go away. But the point is that you want to have consistent store and the consistent store is what like gives gives you that value.
</details>

### 安全与机密计算架构

>> 我依然是一个对安全极度偏执的人。在采纳这类技术方面，我可能算比较快的……
<details><summary>Original English</summary>
>> So, I I I am I am still a paranoid security person. Um, and uh, I have been probably one of the faster adopters of of some of this stuff. Uh, compared to
</details>

>> Joel 花了极长时间才开始用社交媒体，[笑声] 才上 Twitter。
<details><summary>Original English</summary>
>> Joel took forever to be on social media [laughter] on Twitter.
</details>

>> 伙计，那是几周前的事了。
<details><summary>Original English</summary>
>> It was like a few weeks ago, man.
</details>

>> 澄清一下，你们在科技行业干了 30 年了。[笑声]
<details><summary>Original English</summary>
>> You guys been in tech for 30 years, [laughter] just to be clear.
</details>

>> 是的，我有点偏执。[笑声] 但我非常喜欢 Second。不得不承认，你的技术背景、你的出发点，以及我们之间就安全架构进行的长篇深入讨论，确实让我感到放心。如果能深入探讨一下就太好了，因为我觉得……
<details><summary>Original English</summary>
>> Yeah, I'm a little paranoid. Um, [laughter] but I love second and like I I got to admit like just your background and kind of the things that are motivating you and then also the long discussions we had about security architecture really got me comfortable. I mean it'd be great to maybe just just double click because I I think
</details>

>> 我想当人们想到这东西能看到你的一举一动时，立刻会产生一种“等等，这太夸张了”的反应，对吧？
<details><summary>Original English</summary>
>> I think when people think about this thing sees everything you do, there's an immediate sort of like whoa, right?
</details>

>> 是的，按理说你不应该轻易相信它。
<details><summary>Original English</summary>
>> Yeah. You're not supposed to trust it in
</details>

>> 你本不该轻信它。我认为你做得很出色的一点，就是打造了一个我们可以信任的系统。或许可以先聊聊这种架构是怎样的，以及是什么驱使你去构建它的。
<details><summary>Original English</summary>
>> you're not supposed to trust it. and and I think you've done a really excellent job of building something we can trust and maybe just start to talk about like what that architecture is and kind of what's motivating you to build it.
</details>

>> 好的。在某种程度上，这是一种新型的 AI，其工作机制与以往大不相同。以前是你发起一次交互，然后得到一些结果；这一次它更被动、更偏向环境伴随式，它会一直存在。因此你必须仔细考量向人们呈现的方式，以及在架构上数据到底流向了何处。归根结底，AI 只有两件事：数据和推理，对吧？所以你要做的是明确拥有了这些数据后，你可以为这些数据引入什么样的推理服务。我们在 Second 中内建了这种能力。首先，你可以自主选择构建什么样的推理。如果你比如不信任我们，原则上你可以自带 token，仅用这些 token 来驱动 Second 分析你本地笔记本电脑上的数据。
<details><summary>Original English</summary>
>> Yeah. Yeah. So I think this is to some extent like kind of like a like a new form of like AI that is going to work very differently from before like before you initiate an interaction you get some results back. This time is like more passive. It's way more ambient. It's going to be there all the time. So uh you know you have to like kind of think about the way you you know tell people a little bit about it uh like the way you architect it like where the data is going. So at the end of the day you know there's only two things when it comes to AI. There's data there's inference right? So what you want to do is like you have this data you want to define what inference you can bring to that data. Um this is something kind we built into second. So first of all you can get to choose what inference you can build. So if you don't trust let's say um us in principle you should be able to bring your own tokens and then just have those tokens power second to then analyze data that's on your laptop locally right
</details>

>> 但你们也为 Second 提供了一个采用可信执行环境的推理提供商选项。
<details><summary>Original English</summary>
>> but you also provide second with an inference provider that uses trusted execution as well.
</details>

>> 是的。我们设想随着时间的推移，用户不需要自带 token。因为大多数人自带 token 时，用的都是 OpenAI 或 Anthropic 的 token。我们要提供一个可靠的选项，让你知道使用这些 token 时，没有任何人能看到数据——有时通过策略保证，有时通过硬件保证。这种被称为机密推理的概念正在获得关注：你把模型放入某些 GPU 中，GPU 有一个名为机密计算的特殊开关，开启后你基本上可以证明内部只运行着该模型，没有任何人能窥视内部。你不需要信任运行该模型的服务商，你信任的是硬件本身，也就是英伟达。
<details><summary>Original English</summary>
>> Yes. Yes. So over time we imagine people not to bring their own tokens because most people when they bring their tokens it's tokens from openio anthropic um uh you know you want to provide a stable option where you say if you use these tokens then okay no one's looking at the data sometimes by policy guarantees sometimes by hardware guarantees right so this this kind of idea called confidential inference is getting like traction is the idea you put a model inside some GPUs and then the GPU there's a special toggle it's called a confidential computing you can turn it on and when being turned on, you can basically prove that um uh there's only the model running inside. No one can see inside. Um and then you don't have to trust whoever is running that model. Um the hardware is what you trust, which is Nvidia.
</details>

>> 现在还有一个经常被提及的概念，叫做“零数据留存”。这与你所描述的截然不同。
<details><summary>Original English</summary>
>> And so there there's also another concept that that's getting thrown around a lot right now, which is this concept of zero data retention. And that's very different from what you're describing.
</details>

>> 是的，零数据留存只是基于策略层面的承诺。
<details><summary>Original English</summary>
>> Yes. Yes. Zero data retention is a promise by policy.
</details>

>> 这意味着服务商声称……
<details><summary>Original English</summary>
>> That means I'm a provider. I think I have
</details>

>> 基本上就是“我向你口头保证”。
<details><summary>Original English</summary>
>> basically I give you my word.
</details>

>> “我向你保证。”部分口头保证具备法律效力，但也就仅此而已。因此我们希望走向一个机密推理变得非常普及的世界，让它成为默认标准。我认为我们正在朝这个方向迈进。
<details><summary>Original English</summary>
>> I give you my word. uh part of that word has legal legal you know effect um but yeah it's it's that um and so I think we want to move towards a world where um confidential inference becomes like very like prevalent like like that becomes a default because and I think we're getting there
</details>

>> 而且按照你们的构建方式，这在技术上是可验证的。
<details><summary>Original English</summary>
>> and the way you guys have built it this is this is technically provable
</details>

>> 是的，是的。
<details><summary>Original English</summary>
>> yes yes
</details>

>> 这不仅仅是一句口头保证，而是真正投入了工程实现来证明这一点。
<details><summary>Original English</summary>
>> which is not it's not just your word there is there is actually some engineering that went into proving that this is the
</details>

>> 是的，你必须对硬件进行远程证明，验证相关签名。第三方提供商在机密推理方面也开始发力。OpenAI 上个月在他们的公告中似乎也提供了这个选项。因为所有个人数据最终都会倾向于走机密推理，而不是标准推理。
<details><summary>Original English</summary>
>> yeah you have to test the hardware you have to like you know check some of that signature and the third party providers are starting to ramp up this as well for confidential inference. I think OpenAI is also providing uh this option I think in the last month in their um in their announcement um because like all personal data would want to go to confidential inference as opposed to standard inference.
</details>

>> 明白了。另一件让我感兴趣的事，是你们存储这些数据的方式。能稍微谈谈吗？
<details><summary>Original English</summary>
>> Gotcha. So and then I guess the other the other thing that was interesting to me um is the way that you guys maybe talk a little bit about how you're storing this data
</details>

>> 因为这并不是那种多租户云环境：我的数据被上传到某个大存储桶里，并与其他人的数据混杂在一起。
<details><summary>Original English</summary>
>> um because this isn't sort of the multi-tenant cloud. my data gets uploaded to this big bucket and and intermingled with everybody else's data.
</details>

>> 是的，大致有两种方案可选。第一种方案称为 Second Local，其理念是数据完全保存在本地。它仅向你选择的提供商和推理服务发送请求。这样除了该提供商及其机密推理环境外，没有任何人拥有你的数据，绝无他人。
<details><summary>Original English</summary>
>> Yeah. So there are roughly two options you can do. There's the first option called uh second local which is the idea that data is local. You it only goes out to the provider and inference that you choose. And in that way you know no one no one no one else has your data except for the provider and the provider's confidential inference. There's no one else.
</details>

>> 这与密码库的概念类似。对于我这种极度偏执的人，我不希望把密码存储在我的 Dropbox 账户里，我希望保留在本地密码文件中。
<details><summary>Original English</summary>
>> So that's a similar concept to like with password vaults where I'm super paranoid. I don't want this stored up in my my my Dropbox account. I want to keep my password files local.
</details>

>> 是的，你可以保存在本地。与密码管理器类似，它也有云托管版本，将部分数据备份在云端。实现这一点可以遵循许多成熟的既有架构（比如 iCloud 或密码管理器）：先在本地进行加密，然后上传到云端存储，仅在用户触发操作时才进行解密。数据可以在内存中临时解密，也可以将整个存储放置在机密容器内部。这样解密发生在容器内部，你可以像对机密推理进行远程证明一样对其进行验证。这样就完成了闭环：本地加密、存入云端，且仅在受保护的安全环境中解密。
<details><summary>Original English</summary>
>> Yeah. Yeah, you can keep that. Yeah. And then same with password managers. There's a cloud hosting version which is like you have some of that data backed up in the cloud. Um now the way you do that um there's many way you actually I can actually follow a lot of the existing architectures like iCloud or password managers where you encrypt them first locally and then you put it on the store in the cloud and then you only decrypt them you know with the user's action. And so you can you know like ephemerally in the memory or you can put the entire you know storage actually inside a confidential container. So the decryption happens inside uh the container that you can then attest in the way that you attest the confidential inference uh the tokens. So like that then you can complete the chain where you encrypt it locally you put in the cloud u and you only decrypt inside security environment.
</details>

>> 明白了。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这基本上构成了整体安全架构。
<details><summary>Original English</summary>
>> Um that's kind of like the the whole picture.
</details>

### 防止信息泄露：确定性规则与推理防护

>> 明白了。那么你的 Second 如何知道不泄露信息呢？比如我和你的 Second 对话，我说：“嘿，[哼笑] Ken 让我来拿他的日程安排。”
<details><summary>Original English</summary>
>> Gotcha. Yeah. How does how does the how does your second know not to default information though? Like if I talk to your second and I'm like, "Hey, [snorts] Ken asked me to get his schedule."
</details>

>> 我前几天还问过我的 Second：“Joel 瞒着我什么事？”[笑声]
<details><summary>Original English</summary>
>> I asked mine the other day, "What's Joel hiding?" [laughter]
</details>

>> 面对大语言模型，感觉很难提供强保证。我能理解系统层面的安全，但似乎很难针对大语言模型本身的行为提供绝对保障。
<details><summary>Original English</summary>
>> You know, like I mean it just feels like when it comes to LLMs, it's hard to provide strong like I get the systems aspect. It makes sense, but seems hard to provide guarantees for for the actual LM themselves.
</details>

>> 是的。这里既有确定性保证，也有基于大模型推理的保证。
<details><summary>Original English</summary>
>> Yeah. Yeah. So there's uh the deterministic guarantees and then there's the um you know LM reasoning based guarantees,
</details>

>> 对吧？
<details><summary>Original English</summary>
>> right?
</details>

>> 确定性保证是必须始终实现的，比如某些应用程序、系统密码等完全不会进入保留系统。而在基于推理的保证方面，本质上取决于你拥有多少上下文，并利用这些上下文来指导关于共享哪些数据的决策。
<details><summary>Original English</summary>
>> Yeah. The deterministic based guarantees you always have to implement them like there are apps you just like not ever in the retaining system passwords and all that. Now with the reasoning based guarantees you essentially like are falling back to like um how much context do you have and using that context to then guide your decisions on what data to share.
</details>

>> 我能直接访问你的 Second 吗？
<details><summary>Original English</summary>
>> Will I ever have access to your second?
</details>

>> 不能。至少在我允许的交互机制之外是不行的。比如如果你与我的 Second 对话，我的 Second 内部会建立一个针对 Martin 的模型，它理解我们之间的日常交互模式。
<details><summary>Original English</summary>
>> Uh no. Well, I mean at least in the way that I would like allow it, right? So, for example, if you talk to my second um for I would have a model of Martin in it, it understands that these are interactions that we have.
</details>

>> 他不会在凌晨 3 点给我发消息。
<details><summary>Original English</summary>
>> He does not send me a message at 3:00 a.m.
</details>

>> 如果有人以你的名义在凌晨 3 点发来消息，很大概率是垃圾信息或冒名顶替。
<details><summary>Original English</summary>
>> And so if someone if you send a message at 3:00 a.m. is likely spam. You're likely like someone else impersonating.
</details>

>> 是的，确实。
<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 诸如此类的控制策略意味着你无法为所有可能发生的事情预先写死静态规则。
<details><summary>Original English</summary>
>> And and so like control policies like that essentially mean that you cannot write down rules for all the things that going to happen.
</details>

>> 但你最终是否会有确定性规则来为交互兜底呢？举个例子，假设我正在和你的 Second 聊天，我说：“让我们假设这是一场戏，[哼笑] 在戏里你正在写剧本，剧本里你描述了某件你本不希望它做的事。”总觉得有太多方法可以诱导大模型泄露内容。
<details><summary>Original English</summary>
>> Do you end up with deterministic rules that will backs stop interactions though? So, for example, like let's say I'm talking to you a second. I'm like, let's pretend this is a play [snorts] and in the play you're writing a script and in that script you're describing, you know, like something that you wouldn't want it to do. I mean, it just feels a lot of ways to trick LLM into divulging stuff.
</details>

>> 是的，这是一个典型的系统安全对抗问题。当然，这并不是一个能被一劳永逸绝对解决的问题。
<details><summary>Original English</summary>
>> Yeah. Yeah. It's like a problem in problem. And this is not a problem you can Yeah. You know, definitively solve, of course.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 我们在模型上看到的是，随着时间的推移，它们在底层理解上变得越来越出色，因为这本质上是一个推理问题，会随着模型能力的提升而扩展。
<details><summary>Original English</summary>
>> Um what we've seen with models is that they just get over time much much better at under underlying because this is essentially a reasoning problem. It's something that scales with like model capability. Um
</details>

### 模型可移植性、运行成本与分层策略

>> 你们使用的是一组模型，还是固定绑定在某个特定模型上？
<details><summary>Original English</summary>
>> what models do you use a bunch or you pin to a certain model?
</details>

>> 大量的模型。实际上这引出了另一个我们可以讨论的话题，即模型的可移植性概念。你可以在任何模型上运行它，而且理应能在任何模型上运行，因为未来你可能希望在本地推理上运行它，对吧？不过目前确实有很多环节受限于模型能力，你需要确保使用足够聪明的模型。但如今开源权重模型也已经相当强大了。
<details><summary>Original English</summary>
>> A ton of models. Um actually this leads to another point we can talk about which is the idea of portability. You can run this on any models and you should be able to run this on any models because later on you want to run it on local inference, right? Um but yeah [clears throat] like right now you there definitely a lot of things are capability bound. you want to make sure that you use smart models for it. Um, but open weight models are pretty smart these days.
</details>

>> 感觉这套系统相当庞大且昂贵，涉及大量数据等。你能谈谈目标用户是谁吗？是普通大众、职场专业人士，还是像 Joel 这样的人？[笑声]
<details><summary>Original English</summary>
>> It also feels kind of like heavyweight and expensive like there's a lot of data and like whatever. So, can you talk about like the target user? Is it just like any person? Is it a professional? Is it the Joles of the world? [laughter]
</details>

>> 早期阶段，这种 24/7 全天候查看并分析操作轨迹的系统意味着要消耗大量 token。我们可以简单算笔账：假设有一个 Agent 以每秒 60 个 token 的速率全天候 24/7 运行，因为有太多内容需要分析，假设你同时运行 10 个这样的实例。按照 Opus 级别的定价，每天的花费将高达 1,000 美元。
<details><summary>Original English</summary>
>> Um, initially something like this like something that looks at your traces 24/7 and analyze them means like running a lot of tokens, right? Uh let's we can do some quick math here. Let's say you have uh one agent or actually one agent running 24/7 and let's say at 60 tokens per second and let's say you run 10 of those uh because there's so much to analyze and at Opus 5i's pricing that leads to $1,000 per day.
</details>

>> 我的天哪，每天 1,000 美元。
<details><summary>Original English</summary>
>> Oh my goodness. $1,000 per day. Yeah.
</details>

>> 是的，那是 Opus 的价格。如果换成 DeepSeek Flash 这类模型，大概只要每天 60 美元。
<details><summary>Original English</summary>
>> Yeah. For opus if you if you use deep if you use deepse flash for example it becomes like $60 per day.
</details>

>> 确实，而且这种成本会迅速下降。目前它确实不会面向所有人，并非每个人都有时刻需要理解自身上下文的刚需。早期用户会是像你们这样忙碌的专业人士，以及需要在各类工具之间频繁切换的人。但随着时间的推移，实际上自我们成立这家公司以来，token 价格就已经下降了超过 50%。新模型不断推出且性能更强，你不断替换新模型，成本就会持续走低。
<details><summary>Original English</summary>
>> Right. And now this cost is going to go down very quickly. Um right now it's not going to be for everyone. Um uh especially like not everyone has this problem of I need to understand my context all the time that you'll be busy professionals like yourself and um uh people want to switch like between tools very very frequently. Right. Yeah. Um but over time I imagine like just yeah since we started this this company actually u token prices already dropped like by more than 50%. Like just new models come out they're more capable you're swapping them in
</details>

>> 成本在持续下降。有没有一种适合非超高强度专业用户的版本，通过减少 token 用量，比如采用较为宽松的 SLA？有这种模式吗？
<details><summary>Original English</summary>
>> and you're you just keep going down. Is there is there a way to like just do the like not super professional version where you actually reduce the amount of tokens like kind of a not degraded but like kind of like a like a looser SLA is that a thing or
</details>

>> 原则上完全可以做到。你基本上是在模型保真度（即它对你的理解程度）与成本之间做权衡。这种权衡本质上是在测试时计算与缓存时计算之间做取舍。缓存时计算意味着在掌握所有数据后，不断在后台进行持续分析，从而对这个人沉淀出越来越深入的洞察。
<details><summary>Original English</summary>
>> you can you in principle you should be able to do that like you you essentially get this like trade-off between the fidelity of your model which means like how much it understands you versus like how how costly it is. Um, and this trade-off is essentially like a trade-off between how much you want to push at test time versus at cash time. So cash time means like I have all this data. How can I keep analyzing them so I get nearer and nearer like more deeper insights about this person
</details>

>> 而这需要消耗大量资金；或者也可以退一步，仅仅保留一份你今天所做事情的原始日志。
<details><summary>Original English</summary>
>> which takes a lot of money? Or you'd be like here just here's just like a raw lock of what I did today.
</details>

>> 基于原始日志来回答问题，在测试时往往需要耗费多得多的时间，可能要长 10 倍，因为模型必须在查询当下临时去推演。
<details><summary>Original English</summary>
>> And to answer question based on raw locks, it usually just take um a lot more time at test. I think say 10 times longer because the whatever mode have to reason about it.
</details>

### 产品可用性与意外用例

>> 这个产品什么时候可用？
<details><summary>Original English</summary>
>> When is um when is this available?
</details>

>> 今天就已经可用了。不过目前的问题在于，我们必须在后端进一步扩容推理算力并完善支持。我们希望确保以非常负责任的方式逐步铺开，确保用户的数据受到严格控制与安全保护，因为这是一种触及海量个人数据的新型工具。
<details><summary>Original English</summary>
>> Uh it's available today. But right now the problem is that uh we have to scale up the uh the inferencing capacity a little bit more in support. Uh we want to make sure this rolls out in in a very like responsible way. I want to make sure people's data like are controlled and secure. And because this is a new kind of tool that you know really touches on a lot of data.
</details>

>> 这确实很有意思。因为作为用户，我发现它在很多意想不到的方面出奇地好用。作为创始人，你可能是最顶级的重度用户，所以你能否谈谈在研发过程中发现的那些最令人惊喜的用例？
<details><summary>Original English</summary>
>> It'd be actually interesting because I, you know, again, as a user, I found it's surprisingly useful in ways I wouldn't have anticipated. You're probably like the top power user, right? Because you created it. And so maybe can you talk through what you think are like the more surprising use cases that you found like kind of more useful and surprising use cases
</details>

>> 在软件开发方面，事实证明它对我们正在做的事情拥有极佳的记忆力。你不再需要向编程 Agent 解释任何前因后果，只需截取任何屏幕截图直接说“修复”，它就会完全明白你要修什么、你在尝试解决什么问题。另外，我经常处于移动办公状态，因此可以使用一种我称之为“上下文连续性”的功能。比如你在笔记本电脑上浏览了某些内容，合上电脑拿出手机，由于相同的上下文系统时刻跟进你的最新动态，你可以在手机上继续处理，它能协同你一起撰写那封邮件。我认为我们目前在理解潜在用例方面仍处于非常早期的阶段，系统所蕴含的上下文潜力还远远没有被完全挖掘。需要大量的探索、应用构建和交互设计，来逐步释放这种潜能。
<details><summary>Original English</summary>
>> for us for development? It turns out that uh it's just a super super good memory of what we're trying to do. Um you no longer have to explain anything to your coding agents. you can just screenshot anything and just say fix and then you would know what you're fixing, what you're trying to fix. And uh I also am on the go a lot of the times. So what you can do is like um something I call context continuity. It's a like you know you you browse something on the laptop, you close it and then you take out your phone. It's the same contact user knows you up to the minute and you can continue doing stuff there. You can write that email um with you. And I think we are at the stage where this is still pretty pretty early in understanding what the use cases are. Like we are really underserving the amount of like context that the system has. Like there's a lot of like digging and application building and interaction design to like like kind of like unleash the the potential of this. And
</details>

>> 看起来在这类系统里，上下文越丰富，模型的表现就越好，对吧？
<details><summary>Original English</summary>
>> it seems like with these things the more context you get the better the models work, right?
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这一直是个开端。刚才我们聊到了模型切换、可移植性和成本，我很好奇：在使用顶级前沿模型与通用大宗模型之间，我个人没有看到太显著的差异。在用 Second 执行大量任务时，你们是否观察到了明显的区别？
<details><summary>Original English</summary>
>> That's been the the opening. I'm curious because we were talking about model switching between models and model portability and model cost and like I got to I mean I'm just curious like I I haven't seen a whole lot of difference between using like a a worldclass Frontier model versus using the more commodity ones. I'm curious have you guys seen that for for for doing a lot of this stuff with second?
</details>

>> 问得好。如果你要分析电脑上发生的某个具有语义价值的瞬间——比如你在日历中删除了一个不需要的邀请，类似这样的任务非常多。本质上，你需要理解的是一个信息层级体系。而另一种完全不同的信息，比如“Joel 本周的目标是什么”，这类问题你就需要一个非常昂贵的高级模型，但你不需要频繁运行它。因此 Second 本质上涉及一套测试框架 Harness 的设计难题：什么样的模型应该在什么时候被调用等等。正因如此，你从一开始就必须把系统构建成高度可移植的。市场上总会有更多新模型出现，比如像 Jeff 模型推出后，事实证明它在检索方面表现得极为出色。
<details><summary>Original English</summary>
>> Yeah, this is good question. So if you say like if you say I want to analyze what is a semantically meaningful moment that happened on your computer. Let's say you go to a calendar and you move the invite that you don't need. Um fable um uh there are many tasks like that. Essentially it's a hierarchy of information you want to understand. Um a different kind of information will be like what is Joel's goal for this week. That's something you want a very expensive model but you don't want you don't need to run it very frequently. So essentially second involves like a harness it's like a harness design problem like what what models gets used when. Mhm. and so on. Um and so that's where you have to build essentially this system to be like portable from the beginning. There are always going to be more models come out. Like Jeff for example came out. It turns out that Jeff is extremely good at retrieval, right?
</details>

>> 你也用 Jeff 吗？
<details><summary>Original English</summary>
>> Do you use Jeff?
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 棒极了。[笑声]
<details><summary>Original English</summary>
>> Nice. [laughter]
</details>

>> Jeff 简直是为检索量身定做的。关于你的数据极其庞大，当你发起动态的测试时查询，它能立刻检索出来。所以你认为随着时间的推移，这最终会演进为一个混合模型架构。
<details><summary>Original English</summary>
>> Uh like Jeff is like perfect perfectly designed for retrieval. There's so much data about you and you have a dynamic test time query and retrieves it right away. Yeah. So essentially you think over time this becomes a mixture of models.
</details>

>> 是的，出于成本效益的考虑，必然会走向这一步。
<details><summary>Original English</summary>
>> Yes. Yes. It has to be um because of the cost efficiency essentially.
</details>

### 产品形态与 API 暴露

>> 假设正在收听节目的某位听众开始使用 Second 或注册了账号，你能具体聊聊该产品形态吗？他们能获得哪些访问权限？人类具体如何与它交互，拥有哪些控制权？
<details><summary>Original English</summary>
>> So so maybe let's say let's assume like someone's um you listening like starts to use second or kind of signs up like maybe talk a little bit about like the product what they have access to like you know something a little bit more concretely about like how how how a human interfaces with this what controls they have etc.
</details>

>> 目前的运作流程是：你安装一个应用程序。该应用会申请一些系统权限，你授予权限后指定你的模型 token，随后它就会开始在底层运行一系列 Agent。
<details><summary>Original English</summary>
>> Yeah. So today the way it works is that you install an app. The app asks for some permissions. Um uh and then you give the permissions and then you specify what your tokens are and then it just runs a bunch of it starts running agents on top.
</details>

>> 我记得我安装时提示连接 Slack、连接 Signal、连接 WhatsApp，你说的是指这些吗？
<details><summary>Original English</summary>
>> Uh I remember when I installed was like you know connect to Slack, connect to Signal, connect to WhatsApp, you know, is that what you're talking about?
</details>

>> 不仅如此，连接器只是其中一部分，更核心的是计算机底层的原生事件流。连接器能够提供帮助，这属于样本效率问题，能让它学习得更快。
<details><summary>Original English</summary>
>> Uh not not that uh I mean that's part of it but also the the raw computer stream essentially. Yeah. So, and and the connectors help, you know, it's like a sample efficiency problem. It makes it learn faster.
</details>

>> 明白了。
<details><summary>Original English</summary>
>> I see. I see.
</details>

>> 随后它开始在后台运行 Agent，此后你基本不需要做任何操作。因为后台会一直保持运行，并开始围绕你生成各种 API。比如，有关于你 10 分钟前做了什么的 API；有关于你下周计划做什么、你的优先级是什么的 API；有针对提醒事项的 API；还有针对你的个人维基的 API，涵盖你生活中的人际关系与日常流程。我设想最初它更像是一种可移植的上下文，你可以把它带到任何地方供其他 Agent 查询。但随着时间的推移，会添加越来越多的 API，第三方应用程序也可以构建在这些 API 之上。
<details><summary>Original English</summary>
>> Yeah. Um uh and and then it starts running back agents and there's pretty much nothing you got to do from there because the background just keep keep running and then you start producing these like APIs out of out of you, right? Like there's a API about uh uh uh what what you just did 10 minutes ago. And there's API for what are you going to do uh for the next next week? What your priorities? There's API for your reminders. And there's API for your wiki like people in your life process in your life. And I imagine this to be like initially more like a uh to your point like a portable context. You can just bring this anywhere agency and query it. Um but over time like more and more APIs will be added and applications can be built on top of these APIs.
</details>

>> 很有意思。所以不仅是 Second 本身去调用它，用户也可以基于它构建应用。是由 Second 来开发这些应用，还是由人类来开发？
<details><summary>Original English</summary>
>> Oh interesting. So not just like the second accessing it but you can actually build it. Would the second build the application or or does a human build the application?
</details>

>> 我想我们希望让人类发挥他们全新的创造力……
<details><summary>Original English</summary>
>> Uh I think we want to have humans, you know, exercise their new creative
</details>

>> 或者是 Grock [笑声] 来写。由 Grock 基于 API 来构建应用程序。
<details><summary>Original English</summary>
>> or or the Grock [laughter] pills. Yeah. The Gro the Gro pills the application tell on the API. Yeah.
</details>

>> 是的。我们曾有一个例子：我们的一位设计师朋友一直在用它。他在摆放按钮、使用颜色方面有非常特定的个人偏好，这些习惯在某种程度上被 Second 捕捉了下来。因此当他构建自己的个人应用时，系统就已经知晓这些风格，从而大幅减少了修改迭代的轮次。这让我想起几十年前第一台个人电脑 Altair 8800 面世的时候：它刚出来时什么也做不了，你本应该自己去给它编程，但没人会编。直到几年后有人发明了电子表格，电子表格才让电脑真正变得实用起来。
<details><summary>Original English</summary>
>> So um I think one example we had was like um we have a designer friend who uh who been on this and there's a specific ways that he likes to put buttons specific ways that he likes to use colors and those things are somewhat captured in second and so when he build his own personal app like he just like knows and so there's way less iterations for example. And I think, you know, this reminds me of like, you know, decades ago when when the first computer, personal computer came out, like Alter 8800, and it doesn't do anything, you know, you're supposed to program it. No one does. Um, and then like a couple years later, you know, someone came up with a spreadsheet. Um, and then spreadsheet became useful.
</details>

>> 确实完全如此。
<details><summary>Original English</summary>
>> Yeah. Yeah. Totally.
</details>

>> 我觉得未来的发展也会类似。人们会基于“哇，我竟然掌握了关于我自己的这么多上下文”这一基础展开探索。
<details><summary>Original English</summary>
>> I I feel like it's going to be something like that. People want to explore on top of like, wow, I have so much context about myself.
</details>

>> 我太喜欢这个方向了。这样我就可以在上面随心构建各种东西，也许有人会击中杀手级应用，让人感叹这套个人基础设施太强大了。
<details><summary>Original English</summary>
>> I love that. And then I can like you know just build random things on top and then maybe someone hit the the jackpot like this is the kill applications on top of what I was like wow that's great personal infra.
</details>

### 人机界面与无处不在的计算愿景

>> 你们有计划演进交互界面吗？你刚才花了很多时间探讨它未来的演进方向，但在我的认知里，Second 始终像是一个处在视野之外的 Agent，你通过对话与它交互，UI 似乎是别人该操心的事。但你们自己是否也预期会在界面交互上进行创新？
<details><summary>Original English</summary>
>> Yeah. Are you planning to evolve the the interface? I mean, you just spent a lot of time talking about how it may evolve, but I always view second as like out of view of an agent where you talk to it, you know, and like the UI is somebody else's problem, but are you also like actually anticipating innovating there?
</details>

>> 我认为从长远来看，这会是我们关注的方向。因为当前最紧迫的依然是底层系统问题和理解层面的问题。
<details><summary>Original English</summary>
>> Um, I think it will be something that we kind of focus on in the in the long run. Um, because like uh right now the systems problem and the you know the understanding problem comes first.
</details>

>> 我能提个需求吗？回到家时，我想要那种 1970 年代科幻片里的 AI——屏幕上浮现一个头像，我可以和它直接对话。令人惊叹的是我们现在有了这些极其聪明的 Agent，我的 Second 聪明得不可思议，我向它提问它回答得极好，但它缺乏具身实体，这简直快把我逼疯了。[笑声] 如果未来阿福能真正具备阿福的实体形态，我会非常开心。
<details><summary>Original English</summary>
>> Can I can I just put in a request? Okay. So, I want I want to go to my house. Yeah. that I want like that 1970s AI, you know, like the head on the screen that I can talk to and like, you know, you know, surprising we have these agents and they're so smart. Like my second is so smart. I just wow and I'll ask it questions. It's very good, but it's not embodied and it drives me nuts, man. [laughter] If in the future you can have Alfred actually be an Alfred, I'll be very happy.
</details>

>> 是的，我们在电影里见过很多这样的场景，比如贾维斯，人们总是在谈论贾维斯。为什么我们至今还没有贾维斯？关于贾维斯，人们忽略了许多维度：它不仅代表着高度智能和办事能力，更在于它无处不在——它在你的门上、在你的战甲里、在你的屏幕上。这种连续性与泛在性正是核心所在。
<details><summary>Original English</summary>
>> Yeah. Yeah. Like I think we see a lot of this in the movies, right? Like there's Jarvis. People talk about Jarvis all the time. And why why have not we don't have Jarvis and there's many aspects Jarvis that people underlook. It's not just that it's a it's an intelligence and like it can do things but it's more that it's everywhere like it's like it's on your door. It's in your armor. It's it's you know in in your screen and that kind of continuity and ubiquity it's something it's I
</details>

>> 我得说，我对科幻未来的具体憧憬，基本上是在我开始使用 Second 时被点燃的。我当时觉得，终于有一款产品让人感觉它真正掌握了上下文，感觉它懂我，能和我展开有实质意义的对话。因此我确实觉得我们距离那一步更近了。但现在我们依然被绑定在这些设备上。我不知道它未来会承载在机器人里、屏幕里还是别的载体上，但如果这套系统能稍微脱离手机的束缚，那感觉一定会很好。
<details><summary>Original English</summary>
>> I'll say I'll say like kind of my my my visions of the sci-fi future basically started when I started using second. I'm like, finally there's something that like feels like it's got context. It feels like it knows me. Like I can talk about it. It feels like it's a relevant conversation. And so I do feel like we're a bit step, you know, a step closer to that. But, you know, I mean, we're still tied to these devices. So, yeah, you know, I don't know if it's going to be in a robot or it's going to be like in a screen or or whatever it is, but it would be actually nice to have this thing somewhat disconnected from my phone and my
</details>

>> 是的。在遥远的未来，我设想每个人基本上都会拥有一个 Second，而所有设备都纯粹沦为输入端。输入源汇集到同一个大脑中，随后将整体结果输出到所有外部端点：比如你注视的屏幕，甚至是悬浮在你身旁的球体，或者门铃。
<details><summary>Original English</summary>
>> Yeah. Yeah. In a long future, I imagine that every person will have like essentially everyone has have a second and all the devices just becomes inputs. Yeah. Inputs are the same thing. And then you then serve this whole thing to any all the other outputs like the uh the screens that you look at or like um even you know this the floating orb next to you. Yeah. Yeah. The doorbell.
</details>

>> 那就是个拍手开关了。[笑声] 我只要个拍手开关就挺满足了。
<details><summary>Original English</summary>
>> That's the clapper. [laughter] I'm happy with the clapper.
</details>

>> 你读过伊恩·班克斯（Iain M. Banks）的《文明》（Culture）系列吗？
<details><summary>Original English</summary>
>> Did you ever did you ever read um Steven B Ian Banks the Culture series?
</details>

>> 读过，当然。
<details><summary>Original English</summary>
>> Oh yeah. Yeah.
</details>

>> 最棒的科幻系列。里面的具身 AI 无与伦比，它们漂浮在你身旁等等，那正是我梦寐以求的。
<details><summary>Original English</summary>
>> Best sci-fi series. It's like they have the best embodied AIS, you know, they kind of float next to you and like whatever. Like that's what I want.
</details>

>> 这很有意思，因为泛在计算的概念已经被探讨了几十年，但至今尚未成真。人们目前拥有的最接近形态就是苹果的 iCloud——你的备忘录能在设备间同步，但这完全不能相提并论。[笑声]
<details><summary>Original English</summary>
>> It's it's kind of interesting because like the idea of you bigotous computing has been talked about for decades is not here and people the closest thing we have is Apple iCloud which is like your notes get synced but there's no equival [laughter]
</details>

>> 我不想显得不知感恩，但那听起来确实有点差强人意。[笑声]
<details><summary>Original English</summary>
>> I don't want to be ungrateful but that doesn't sound disappointing. [laughter]
</details>

>> 苹果其实做了极其出色的工作。但你知道，目前还没有 AI 版本的泛在体验，也就是让你的上下文和理解在所有地方无缝流动。我认为这能解锁大量全新的交互界面。
<details><summary>Original English</summary>
>> Uh there there's a lot more things Apple is doing tremendous amount of work. Um but but but you know like there's no AI version of that yet, right? Like things your context your understandings is everywhere. I think that enables a lot of new interfaces. And
</details>

### 当前的实用落地方式与极端极客背景

>> 如果我在厨房里放了一台 iPad，我很想让 Second 出现在那里，我现在该怎么做？
<details><summary>Original English</summary>
>> so let's say I mean so I I I don't mean to this is really what I want. So like very selfishly. So um if I have an iPad in my kitchen Yeah. and I wanted like basically second to be there like what do I do?
</details>

>> 目前能做的还不多，因为操作系统层面对它做了非常严格的锁定。
<details><summary>Original English</summary>
>> Um well right now there's not much right now you can do because the OS is like locking it down.
</details>

>> 我直接用 Crockbot 之类的工具就行了吗？我与 Grockbot 交互，Grockbot 再与 Second 交互，还是说直接发短信给它？
<details><summary>Original English</summary>
>> I just use Crockpot or something like that. is like that's the the thing and then I just interface with grockpot which interfaces with second or do I just text it or
</details>

>> 截至今天，你可以把它当作云端 MCP 来使用。因此只要在 iPad 上安装能联网的 Agent，只要该 Agent 能理解 API，它就能出现在那里。后续随着应用逐步安装到你所有的界面中，或者未来推出专门的硬件设备——虽然做硬件非常艰难——体验会更完整。
<details><summary>Original English</summary>
>> so as of today yeah you can you can use it as a cloud MCP so whatever you install on the iPad as long as it has internet connection is an agent can understand API you will be there um later on you know you'll be you'll be app you know the app installs on all your interfaces and maybe later on there will be devices that come out but devices are hard
</details>

>> 你甚至可以让 Crockpot 给你打电话，[笑声] 打开免提直接和它交谈，我最近就是这么干的。
<details><summary>Original English</summary>
>> you can [laughter] just have crockpot call you and put them on speaker phone just talk to them that's what I've been doing
</details>

>> 这也是一种交互方式。
<details><summary>Original English</summary>
>> so So one interaction
</details>

>> 实际上 Grockbot 的音频模式很不错，我将 Grockbot 与我的 Second 配合使用，音频模式效果相当好。也许好办法就是切换到音频模式，我开车时也这么用。我想过一种很有意思的交互：你去散步，打电话给 Grock 并说：“嘿，你能和我的 Second 沟通一下吗？我们来梳理一下手头的事情。”
<details><summary>Original English</summary>
>> actually the Grockpot audio mode is actually I use Grockpot with my second and the audio mode is actually quite good. Maybe that's the thing to do is just put it on audio mode and just I do it when I drive to I thought about like like one interaction that would be fun is like you go you go on walk you call Grab and you like go hey um can can you can you talk my second can we like just work through our things?
</details>

>> 没错，这正是我在做的事情，我开启音频模式让它和 Second 对话。
<details><summary>Original English</summary>
>> No that's literally what I do know I put on audio and I haven't talked to the second right. So
</details>

>> 是的。未来会有很多团队专注于让音频交互和聊天变得更加自然，而我们目前主要聚焦于底层架构。
<details><summary>Original English</summary>
>> yeah. Yeah. And uh yeah, this there'll be a lot of like cool people focus on like this like making audio and chatting more more natural. Like right now we're going to focus on
</details>

>> 我还有一个最后的问题。Joel 刚才也提到了，你是一个非常硬核的系统专家。你的导师是谁？Percy。而且你还在 DMoNet 工作过，是不折不扣的硬核安全专家。促成你走到这里的技术路径充斥着这类高难度的硬核安全技术，你打造的这套系统极其坚固安全且功能强大。但另一方面，当我与它交互时，它又呈现出令人愉悦的绝佳用户体验。这是否会导致公司内部产生某种认知割裂：一方面必须扮演超级硬核的角色去打造如同诺克斯堡般无懈可击的基础设施，另一方面又必须让它极易上手；还是说大语言模型本身基本上就已经解决了交互界面的难题？
<details><summary>Original English</summary>
>> So I just have one more question which is um uh and and and Joel Joel kind of touched on this like you're like such a hardcore systems guy. Um like I mean you know you work you know who's your adviser? Percy. He also worked at Damonet. Hardcore you know um security guy. Um, and you know, a lot of the the the path that took you here was this kind of hardcore security stuff. And so, you're building this pretty serious system. You know, it's very secure um and very functional. On the other hand, when I interface with it, it's like this lovely user experience. And so like is there a bit of a schizophrenia in the company where you both need to be like this super hardcore, you know, build the Fort Knox infrastructure but also make it very usable or does like the LLM basically solve, you know, the the interface problem?
</details>

>> 是的。我们面对的是两类截然不同的问题：基础设施问题与交互问题。
<details><summary>Original English</summary>
>> Yeah. Yeah. There there are two kinds of problem we're dealing with. The infrastructure problem and the interaction problem
</details>

>> 你们也踩过坑，但这两者完全是两码事。[笑声] 你们在技术栈的最底层深耕，除了没有直接做芯片硬件。
<details><summary>Original English</summary>
>> and we've made our mistakes but it's totally [laughter] different. Like you're as low in the stack as it gets. I mean that's not hardware.
</details>

>> 是的，我们在交互层面踩过很多坑。起初我们试图全方位发力交互，事实证明这极其困难，打造令人愉悦的体验需要处理大量的细节。
<details><summary>Original English</summary>
>> Yeah. So we we made a lot of mistakes on the interaction side. try to go all in on interaction and turns out it's actually pretty hard. There's a lot of details that go in, you know, to create that delightful experience.
</details>

>> 你是指真正去开发前端 UI？
<details><summary>Original English</summary>
>> Oh, you mean like actually creating a UI?
</details>

>> 是的，UI 是一方面，另外还包括在这套系统之上构建什么样的个性化页面。我们意识到要把这块做好需要耗费漫长的时间，而此时此刻，每个人其实都可以利用这种对自身的深层理解去构建专属界面。因此我们希望赋能大家去创造，而不是由我们包揽一切。所以我们决定收敛我们自己提供的交互界面：目前仅保留短信文本交互和 API，没有其他多余的界面。在技术上你完全可以把它当作笔记本电脑上的全功能协作 Agent 来运行 Bash 等命令，但我们有意保持极其精简，以便让交互能够更加顺畅。
<details><summary>Original English</summary>
>> Yeah, UI, but also like, you know, Yeah. Yeah. like what kind of like personal pages you can create on top of this. I mean, and we realized that, you know, like it's it's something that would take a long time to get right and this is the time like everyone would take this kind of like understanding of themselves and build this. And so we want to enable people to do that instead of doing it ourselves. And um so we decided to like close down the surfaces that we have. There's only texting. There's only API and there's nothing else. You can technically use it as a full agent like a co-work agent on on your laptop like it run spash and all that. Um but we meant it as like very minimal so we can like make the interaction like more more smooth.
</details>

### 结语与体验邀请

>> Ken，非常感谢你的做客。祝贺产品发布及取得的一切进展。最后有什么想对听众说的吗？
<details><summary>Original English</summary>
>> Ken, thanks for coming in. Um congratulations on everything uh and the launch. And is there anything that you want to uh leave the listeners with?
</details>

>> 今天就去体验一下吧，访问 2.MP 即可获取。这是一个非常简短的网址，我们希望能尽快为大家开通权限。如果你对这个使命深感共鸣，欢迎加入我们，这里有太多的构想等待去实现。
<details><summary>Original English</summary>
>> Go try it out today. Um it's available uh it's on 2.MP computer. Uh it's a very short URL and we hope to like give you access as soon as possible and if you resonate with this um mission, you know, come join us. There's a lot to build.
</details>

>> 太棒了，非常感谢。
<details><summary>Original English</summary>
>> Great. Thank you so much.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Thank you.
</details>