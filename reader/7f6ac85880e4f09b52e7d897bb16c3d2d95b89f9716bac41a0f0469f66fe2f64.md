---
author: TechButMakeItReal
date: '2026-11-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Fc4lCNLgvJw
speaker: TechButMakeItReal
tags:
  - voice-assistant
  - large-language-model
  - smart-speaker
  - business-model
title: 为什么接入 AI 后 Siri、Alexa 和 Google Home 依然不好用？
summary: 分析指出语音助手即便接入大语言模型仍显笨拙，核心症结不在模型本身，而在商业模式冲突与技术领导力缺失。亚马逊与谷歌将助手、智能家居和廉价音箱强行绑定，苹果则将 Siri 定位在手机并独立销售音箱，因而避开了硬件声誉崩塌。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jeff Bezos
  - Steve Jobs
  - Alexander Wang
  - Robbie Walker
  - Sebastian Marin
  - Mike Rockwell
  - Tim Cook
companies_orgs:
  - Amazon
  - Google
  - Apple
  - Meta
  - Anthropic
  - Cloudera
products_models:
  - Siri
  - Alexa
  - Alexa Plus
  - Echo Dot
  - Google Home
  - Google Assistant
  - Gemini
  - Claude
  - Muse
  - HomePod
media_books:
  - The Wall Street Journal
  - The New York Times
  - Bloomberg
status: evergreen
---
### 语音助手的现状与认知差异

我们称之为 Siri AI。

<details>
<summary>Original English</summary>
We call it Siri AI.
</details>

>> Siri AI。

<details>
<summary>Original English</summary>
>> Siri AI.
</details>

>> Siri AI。

<details>
<summary>Original English</summary>
>> Siri AI.
</details>

>> Siri AI。

<details>
<summary>Original English</summary>
>> Siri AI.
</details>

>> Siri AI。Siri AI。

<details>
<summary>Original English</summary>
>> Siri AI. Siri AI.
</details>

>> Siri AI。我们由 Apple Intelligence 提供支持的新版 Siri。

<details>
<summary>Original English</summary>
>> Siri AI. Our new version of Siri powered by Apple intelligence.
</details>

>> Alexa、Siri、Google Home。它们推出已经这么多年了。但为什么它们依然这么蠢？为什么这么多年的技术进步，并没有让它们比基本的“设一个一分钟的定时器”更实用？去年秋天，谷歌将 Gemini 放进了 Google Home。今年，亚马逊发布了内置生成式 AI 的 Alexa Plus。苹果在 iOS 27 中重构了 Siri。正如你所看到的，这并没有什么用。《连线》（Wired）甚至刊登了这样的标题：“为什么 Alexa Plus 如此愚蠢”。这背后的秘密究竟是什么？在视频结束前，你就会明白为什么给它们加上 AI 并没有创造奇迹，以及为什么我们很多人极度反感的苹果 Siri，反而可能是唯一做对的那个。今天的主题是关于 Siri、Alexa 和 Google Home。让我们深入聊聊。

<details>
<summary>Original English</summary>
>> Alexa, Siri, Google Home. It's been years since they came out. But why are they still so dumb? How come years of progress haven't made them more usable than a basic set up a timer for a minute? Last fall, Google put Gemini into Google Home. This year, Amazon released Alexa Plus with Genai builtin. Apple rebuilt Siri in iOS 27. And as you can tell, it didn't help. Wire even published a headline. Why Alexa Plus is so dumb. What is this mystery? By the end of the video, you will understand why adding AI didn't turn them into magic and why Apple, whose Siri a lot of us hate with passion, might be the one that got it right. Today is about Siri, Alexa, and Google Home. Let's dive in.
</details>

我们先来回顾一个非常重要的区别。[音乐] 这是什么？这是 Alexa 吗？并不是。这是一台 Echo Dot。Alexa 是 Echo Dot 内部的语音助手，但设备本身并不是 Alexa。我们经常混用这两个词，因为 Alexa 已经成了这个音箱的代名词。这也是它主要存在的地方。是的，它也存在于 Fire TV 中，但大多数使用 Alexa 的用户都是通过音箱来使用的。这是 Google Home。情况也是如此。在 Gemini 之前的时代，Google Home 搭载的语音模型是 Google Assistant。但当我们说 Google Assistant 时，大多数时候我们指的是 Google Home。Siri 其实有所不同，因为 Siri 一直被认为是一个生活在 iPhone 里的助手。如果我要给你展示 Siri 是什么，它大概会是这样。

<details>
<summary>Original English</summary>
Let's recall a very important distinction. [music] What is this? Is this Alexa? Not really. It's an Echo Dot. Alexa is a voice assistant inside Echo Dot, but the device itself isn't Alexa. We use these words interchangeably because Alexa became synonymous with the speaker. This is the primary place where it lives. Yes, it also lives in Fire TV, but most users who use Alexa use it with the speaker. This is Google Home. Same situation. In the pre-Gemini era, Google Home had Google Assistant as the voice model. But when we say Google Assistant, most of the time we're talking about Google Home. Siri is actually different because Siri has always been perceived as an assistant living inside an iPhone. And if I were to show you what Siri is, it would be something like this.
</details>

你看到这种认知有多重要了吗？我们说 Alexa，但实际上指的是 Echo Dot。我们说 Google Home，但实际上说的是 Google Assistant。这种认知为之后发生的一切定下了基调。

<details>
<summary>Original English</summary>
Do you see how much perception matters? We say Alexa, but really mean Echo Dot. We say Google Home, but in reality, we're talking about Google Assistant. And this perception sets the tone for everything that came next.
</details>

### 接入大模型后的不可靠性

在过去的 4 年里，大家一直在问：难道他们就不能把 GPT 或 Claude 直接塞进它们里面吗？他们能，他们也确实这么做了，但这并没有用。为什么？2024 年，亚马逊求助于 Claude，试图打造内置生成式 AI 的新版 Alexa。一年后，他们发布了带有生成式 AI 的 Alexa Plus。它连接了几个大语言模型，包括 Amazon Nova、几个 Anthropic 的模型、智能体工具、服务等一堆东西。它一直……

<details>
<summary>Original English</summary>
For the past 4 years, the question has been, can't they just add GPT or Claude inside them? They can, and they do, but it doesn't help. Why? In 2024, Amazon turned to Claude to build a new version of Alexa with Genai builtin. And a year later, they announced Alexa Plus with Genai. It connects several LLMs, Amazon Nova, several anthropic models, a Gentic tool, services, a bunch of things. It's been
</details>

>> 嗨，

<details>
<summary>Original English</summary>
>> Hey there,
</details>

>> 今天有什么我可以帮您的吗？

<details>
<summary>Original English</summary>
>> what can I help you with today?
</details>

>> 但这并没有用。

<details>
<summary>Original English</summary>
>> And it didn't help.
</details>

>> 您好。

<details>
<summary>Original English</summary>
>> Hi there.
</details>

>> 今天有什么我可以帮您的吗？

<details>
<summary>Original English</summary>
>> What can I help you with today?
</details>

>> 还是没有什么用。

<details>
<summary>Original English</summary>
>> And it didn't really help.
</details>

>> Plus 是我们下一代的 AI 助手，具有更好的对话能力和更强的功能。这是 Google Home。

<details>
<summary>Original English</summary>
>> Plus is our nextG AI assistant that's more conversational and capable. This is Google Home.
</details>

>> 您说得完全正确。

<details>
<summary>Original English</summary>
>> You're absolutely right.
</details>

>> 结果呢，好吧，你们也看到了。而且，有时回答一个关于天气的问题要花上 10 秒钟。一位评测者让它把浴室的排风扇打开 15 分钟，它多次执行失败。另一位评测者询问天气，结果听了一首歌。亚马逊的一名前高管对《华尔街日报》表示：“我们担心的是，我们雇了 10,000 人，结果却造出了一个智能定时器。”我专门为了这个视频买了一台 Alexa Plus，我可以证实，它在对话能力上确实变聪明了。但接着就出现了这种情况：Alexa，我在亚马逊上买的最后一件东西是什么？

<details>
<summary>Original English</summary>
>> The result, well, you saw it. And also, sometimes 10 seconds to answer a question about the weather. One reviewer asked it to turn on his bathroom fan for 15 minutes and it failed at that multiple times. Another reviewer asked for the weather and got a song. A former senior employee at Amazon told the Wall Street Journal, "We're worried that we hired 10,000 people and we've built a smart timer. I got an Alexa Plus specifically for this video and I can confirm that it really got smarter in conversation. But then there is this Alexa. What is the last thing I ordered on Amazon?
</details>

>> 正在查询。您最近的订单是 TP-Link Wi-Fi 6 和蓝牙 USB 适配器。今天下的单，金额为 22.59 美元。将于明天晚上 9:00 前送达。

<details>
<summary>Original English</summary>
>> Looking that up. Your most recent order is a TPLink Wi-Fi 6 and Bluetooth USB adapter. Place today for $2259. Arriving tomorrow by 9:00 p.m.
</details>

>> 我不知道她连到了谁的亚马逊账号，但我根本没下过单。嘿，Alexa，你能给我网络运营商发个消息，并给他们的客服打电话投诉我家网速很慢吗？

<details>
<summary>Original English</summary>
>> I don't know whose Amazon she connected to, but I did not order anything. Hey Alexa, can you send a message to my internet provider and call their support and complain that my internet is slow?
</details>

>> 我无法直接向您的网络运营商发送消息或致电。您需要通过官方渠道亲自联系他们，以报告网络变慢的问题。

<details>
<summary>Original English</summary>
>> I can't send messages or make calls to your internet provider directly. You'll need to contact them yourself through their official channels to report the slow internet issue.
</details>

>> 他们接入的大语言模型确实让理解力变好了。它能回答比以前多得多的问题，但与此同时，它变得不可靠了。以前的 Alexa 是建立在一套标准指令之上的。是的，以前它很笨，但它非常可预测。而大语言模型却适得其反。它现在听起来聪明多了，但它达不到一个真正的智能体助手应有的水准。那么，他们为什么不打造一个开箱即用的产品呢？他们为什么不开发自己的类似 Muse 的版本？我一直在夸赞 Muse，因为它……它确实是个很棒的工具。请注意，Meta 在市面上并没有最好的模型。那么他们为什么不把问题修好呢？我个人认为有两个原因：**领导力**和这些助手的**商业模式**。我的理论是，它们从一开始就没打算做成优秀的助手。让我解释一下。

<details>
<summary>Original English</summary>
>> The LLMs they connected really made the understanding better. It can answer a lot more questions than before, but at the same time, it became unreliable. Old Alexa was built on a set of standard commands. And yes, it was dumb, but it was very predictable. And LLM did the opposite. It now sounds a lot smarter, but it doesn't match the quality of what a true agentic assistant should be. So, why didn't they build something that just works? Why didn't they build their own version of Muse? I keep raving about Muse because it's it's it's a great tool. And mind you, Meta doesn't have the best models on the market. So why aren't they fixing it? I personally see two reasons why. Leadership and economics of these assistants. And my theory is that they were never meant to be good assistants. Let me explain.
</details>

AI 进入各家企业已经快 4 年了，然而企业依然在努力证明 AI 能带来可衡量的价值。并不是因为模型不好，而是因为在整理好的精选数据上跑的亮眼平台 Demo，与企业手头拥有的真实生产数据之间，存在着巨大的鸿沟。

<details>
<summary>Original English</summary>
It's been almost 4 years since AI made its way into every enterprise and yet businesses are still struggling to show measurable value from it. Not because the models are bad, but because there is a massive difference between a shiny new platform demo running on curated data and real production data that the company actually has.
</details>

>> [音乐]

<details>
<summary>Original English</summary>
>> [music]
</details>

>> 这一段是由 Cloudera 的播客《AI Forecast》赞助的，这档节目的整个前提就是为了揭示期望与现实之间的差距。主持人邀请来自各行各业的嘉宾，详细描述他们是如何从“我们正在部署这个 AI 应用”走到“为了让它真正运转，我们付出了这些代价”的。在这个播客中，我最喜欢的一期是关于制药研发的。Cloudera 的应用 AI 首席技术官把处理数据比作通过钥匙孔看摩天大楼。你能清楚地看到其中一部分，但看不到周围的任何东西。他谈到了制药研发的复杂性，以及为什么患者的知情同意意味着你往往无法重复使用你已经付过费的数据。这不是一个泛泛而谈“AI 如何运作”的播客。[音乐] 实际上恰恰相反。它是一档讲述“它是如何跑通的，以及它为什么会失败”的节目，对于那些正在构建 AI 业务并面对特定领域中极其具体问题的人们来说，里面充满了非常宝贵的经验。[音乐] 如果你的工作涉及企业数据，或者你是一名正在构建企业级解决方案的 B2B 创始人，这个播客能让你真正洞悉企业数据落地是什么样子的。该播客可以在 YouTube、Spotify 和 Apple 上免费收听。制药那一期的链接就在简介中。现在回到视频。

<details>
<summary>Original English</summary>
>> This segment is sponsored by Cloudera's podcast, the AI forecast, and the entire premise of the show is to shed light on the expectation versus reality. The host invites guests from various industries who describe exactly how they went from we're deploying this AI application to this is what it took to make it work. My favorite episode on this podcast is about pharma R&D. Cloudera, CTO of Applied AI, describes working with data as though you're looking at a skyscraper through a keyhole. You see one piece clearly, but you don't see anything around it. He talks about the complexities of R&D and pharma and why patient consent means that you often cannot reuse the data that you already paid for. It is not a generic how AI works podcast. [music] It's actually quite the opposite of that. It is a how it worked and why it failed kind of show full of invaluable lessons for people building AI businesses and dealing with very concrete problems [music] in a very specific domain. If you work anywhere near enterprise data or if you're a B2B founder building enterprise level solutions, this podcast gives you real insight into what enterprise data implementation looks like. The podcast is free on YouTube, Spotify, and Apple. And the Pharma episode is linked in the description. And now back to the video.
</details>

### 商业模式与硬件绑定的困局

最初，Alexa 是杰夫·贝佐斯的心血结晶。这是他的想法。他的灵感来自于《星际迷航》中的飞船电脑——那个无所不知、无所不在、通过语音控制的 AI，他想打造一个平民化的版本。在我看来，这是个宏伟的愿景。但当他们在 2014 年发布时，有些事情偏离了轨道。愿景是《星际迷航》的电脑，现实却是一个销售平台。Alexa 背后的商业模式是把它放进一个非常便宜的产品里——音箱。还记得他们刚推出助手的那段时间吗？有很多东西你可以免费获得。Spotify 当时在免费赠送 Google Home Mini。Echo Dot 便宜得像只要几分钱。我其实是在房产经纪人那里拿到我的第一个 Alexa 的，作为圣诞礼物。而这个家伙是我从 Spotify 免费拿到的。在 Costco 它们如果不是按箱成批卖，也便宜得要命。它们生来就必须廉价。当时的计划是，你可以先拿到一个设备，然后用它从亚马逊购买更多的东西。通过亚马逊订购杂货。在亚马逊电商市场上订购商品。如果你订阅了 Prime，还可以播放音乐和电影。但即使是针对这些事情，它也不是一个格外可靠的产品。举个例子，我住在多伦多。多伦多有 Amazon Fresh 吗？

<details>
<summary>Original English</summary>
Originally, Alexa was Jeff Bezos's baby. This was his idea. He was inspired by Star Trek's computer, this omnisient, omniresent AI controlled by voice, and wanted to build an accessible version of it. Great vision if you ask me. But when they launched in 2014, something went wrong. The vision was a Star Trek computer. The reality was a sales platform. The business model behind Alexa was to put it in a very cheap product, a speaker. Remember the time when they first rolled out assistance? There was a lot of stuff that you could get for free. Spotify was giving away Google Home Mini. Echo Dots were sold for pennies. I actually got my first Alexa from my realtor as a Christmas gift. And this guy I got from Spotify for free. They were sold in Costco for pennies if not in bulk. And they were meant to be cheap. The plan was that you could actually get a device and use it to buy more things off of Amazon. Order groceries through Amazon. Order products on Amazon marketplace. Play music and movies if you subscribe to Prime. But even for those things, it was not an exceptionally reliable product. Example, I live in Toronto. Is Amazon Fresh available in Toronto?
</details>

>> Amazon Fresh 目前在多伦多不可用。您仍然可以通过 Amazon.ca 订购杂货并享受标准配送，但当日达或极速达服务尚未在加拿大推出。

<details>
<summary>Original English</summary>
>> Amazon Fresh isn't currently available in Toronto. You can still order groceries through Amazon.ca A with standard delivery, but the same day or ultra fast service hasn't launched in Canada yet.
</details>

>> Alexa 和 Echo Dot 背后的商业模式类似于拉斯维加斯。如果你曾经搜索过……

<details>
<summary>Original English</summary>
>> The business model behind Alexa and Echo Dot was similar to that of Las Vegas. If you ever searched,
</details>

>> 这是一个有趣的对比。

<details>
<summary>Original English</summary>
>> it's an interesting comparison.
</details>

>> Alexa，接下来一个小时请不要和我说话。

<details>
<summary>Original English</summary>
>> Alexa, please don't talk to me for the next hour.
</details>

>> 明白了。接下来的一个小时我会保持安静。

<details>
<summary>Original English</summary>
>> Got it. I'll be quiet for the next hour.
</details>

>> 太好了。

<details>
<summary>Original English</summary>
>> Great.
</details>

>> 稍后再聊。[笑声]

如果你去搜一下去拉斯维加斯的酒店或机票，对于一个美国主要城市来说，它们便宜得惊人。它们一点都不贵，因为那里的预期是你会把钱花在赌博上。所以，你获得了廉价的入场方式，但他们预期你一旦进去就会花更多的钱。只不过在赌城，很多人确实会去赌博。而买了 Echo 的人，绝大多数只是用它查天气。人们在最初的几个小时里，就能摸清自己未来会用到的全部功能的一半。在 2017 年到 2021 年之间，Amazon Echo 的销量暴跌。之所以暴跌，是因为 Alexa 和 Echo 是围绕亚马逊的生态系统打造的——亚马逊商城、亚马逊购物、亚马逊的一切。他们本可以向更多第三方商家开放，但他们选择将其锁定在亚马逊生态内。事实上，在 9 月份，亚马逊还阻止了 Meta 的助手 Muse 在 Amazon.com 上进行购物。

<details>
<summary>Original English</summary>
>> Talk to you later. [laughter] If you ever search hotels or flights to Vegas, they're surprisingly affordable for a major US city. They're not expensive at all because the expectation is that you'll spend money on gambling. So, you get a cheap way to get in, but you're expected to spend more once you're in. Except in Vegas, lots of people actually gamble. People who bought Echo mostly asked for the weather. people would find half the features they would ever use in the first few hours. Between 2017 and 2021, the sales of Amazon Echo plummeted. And they plummeted because Alexa and Echo were built around Amazon ecosystem, Amazon Marketplace, Amazon shopping, Amazon everything. They could have opened it to many more vendors, but they chose to lock it to Amazon. In fact, in September, Amazon blocked Meta's assistant, Muse, from shopping on Amazon.com.
</details>

为什么？因为亚马逊去年从浏览网页的人身上赚了超过 680 亿美元的广告费。当像 Muse 这样的智能体替你购物时，你就看不到广告了。所以，并不是他们无法做出某种[音乐]选择。这在技术上是 100% 可行的。是他们选择不做成完全的智能体。我想说的是，如果你回到 Alexa 最初的想法——不是那个愿景，而是对那个愿景的落地执行——它从一开始就不是为了成为一个超强的助手而设计的。它被宣传为一个助手，但它在构建之初就不是。它被构建成了一个销售平台。它还有其他功能，比如作为一个还算过得去的音箱，但它的摇钱树本该是一直卖出更多的亚马逊产品，但这从未真正发生。这就解释了为什么尽管生成式 AI 已经出现了近 4 年，他们却没有打造出一个杰作级的助手。尽管这 100% 是可能的，如果他们真正把 Alexa Plus 打造好，做成具备完整智能体能力、无所不能的助手，他们就必须同时提高 Echo Dot 的价格和 Prime 订阅费。[音乐] 即便在现在，尽管 Alexa Plus 存在种种缺陷，它也只向 Prime 会员开放。但如果要真正做好它，意味着他们得向你收取更高的费用。我认为第二个解释是**领导力**。

<details>
<summary>Original English</summary>
Why? Because Amazon made more than $68 billion last year on ads from people browsing the pages. And when an agent like Muse shops on your behalf, you don't see the ads. So, it's not that they can't make it a [music] choice. It is 100% technically possible. they choose not to make it fully agentic. What I'm trying to say is that if you go back to the original idea behind Alexa, not the vision, but the execution of that vision, it was never meant to be a super strong assistant. It was marketed as an assistant, but it was never built as one. It was built as a sales platform. It had other features like being a decent speaker, but the cash cow was always supposed to be selling more Amazon, which never happened. This explains why despite Genai being around for the past 4 years, they did not build a masterpiece of an assistant. Even though it's 100% possible, if they built Alexa Plus properly with a Gentuite and do everything kind of assistant, they would have to raise prices on both Echo Dot and Prime subscription. [music] Even now, Alexa Plus with all its flaws is only available for Prime members. But building it properly would mean they'd have to charge you even more. The second explanation, in my opinion, is leadership.
</details>

### 技术领导力与战略执行

如果你觉得，坐在那些实验室里的肯定是科技界最聪明的大脑，这有什么难的？事实上，结果会让你吃惊。这确实很难。强大的技术领导力能决定成败。Meta 实际上就是一个绝佳的例子。Meta 在模型方面做得并不算拔尖。Llama 不算差，但它比不上 Anthropic 或 OpenAI。甚至他们最新的模型 New Spark，在 Meta 自己的基准测试中，推理能力也落后于 Gemini、GPT 和 Claude。因此，他们没有去加入一场自己赢不了的模型竞赛——至少目前赢不了——而是挖来了 Alexander Wang，并打造出了一款扎实的产品。[音乐]

<details>
<summary>Original English</summary>
If you're thinking, well, they must have the brightest brains of tech sitting in those labs. What's so difficult about it? Actually, you will be surprised. It is hard. A strong tech leadership can make it or break it. Meta is actually a fantastic example. Meta isn't doing great with models. Lama isn't bad, but it's not entropic or open AAI. Even their newest model, New Spark, is behind Gemini, GBT, and Claude on reasoning on Meta's own benchmarks. So instead of joining a model race that they cannot win, at least not right now, they poached Alexander Wang and built a solid product. [music]
</details>

在 Wang 的领导下，他们推出了 Muse。Muse 是一款杰作级的助手。所以，是的，领导力确实起到了巨大的作用。这不只是空洞的企业套话。即使房间里坐满了最聪明的人，你也必须清楚这艘船要开往何方。

谷歌在 2025 年推出了生成式 AI 版本的 Google Home。是的，它遇到了和 Alexa Plus 类似的问题。它在对话和理解方面确实有了极大的提升，但它 Bug 很多。有人让它开灯并在 5 分钟后关掉。它把灯打开了，但并没有关掉，而是设了一个标准的 5 分钟定时器。有人让它推荐素食餐，但它推荐的餐食里并不全都是素食。谷歌和亚马逊一样，也把 Google Assistant 放进了一个实体设备里。Google Home 成了该助手的主要承载地，就像 Alexa 和 Echo 一样。但后来这个音箱本身成了 Nest 家族的一部分，他们把整个叙事转向了智能家居。

恒温器、摄像头、门铃，全都是关于你的家。那么问题来了，好吧，既然它不是要做成那种无所不能的超级智能体助手，而你们公司本身也是个实验室，它怎么能在它本该服务的主要场景——家庭场景中如此不可靠呢？谷歌自己的官方声明表示，许多智能功能尚未完全升级，在依赖事实性回答之前最好先核实一下。所以，你们基本上是在说，你们明明知道即使加入了 Gemini 它也算不上好，但你们还是把它发布了。管理层为什么能接受这种质量水平，目前还不清楚。再次强调，从技术角度来看，把它做成一个深度集成的智能家居产品、并具备极其强大的助手功能，并没有什么不可逾越的鸿沟。你根本不需要为此再搞出一次科学突破。[音乐] 那么，他们为什么要把一个半成品发布出来？我可以用领导力来解释。再说一次，Google Assistant 团队内部经历了多次动荡，很多人被裁员，这又回到了领导力的问题上。最后但同样重要的，是 Siri。

<details>
<summary>Original English</summary>
Under Wang's leadership, they launched Muse. And Muse is a masterpiece of an assistant. So yes, leadership does play a massive role. And it's not just corporate talk. Even when you have the smartest minds in the room, you have to know where this ship is going to go. Google launched a Genai version of Google Home in 20125. And yes, it has similar problems as Alexa Plus. It did improve drastically in conversation and understanding, but it's buggy. People asked it to turn a light on and then off after 5 minutes. It switches it on but sets a standard timer for 5 minutes instead of turning it off. Somebody asked it to recommend vegetarian meals but not all of the meals that are recommended were vegetarian. Google like Amazon also placed Google Assistant inside a physical device. Google Home became the primary place for the assistant same as Alexa and Echo. But then the speaker itself became part of the Nest family and they changed the whole narrative to smart homes. Thermostats, cameras, doorbells, it's all about your home. So the question is, okay, if it's not meant to be super agentic and do everything kind of assistant, your company that is also a lab, how can it be so unreliable at the main use case that it's supposed to serve, the home use case? Google's own media says that a lot of smart features were not fully upgraded and that it is safest to check factual responses before relying on them. So, you're basically saying that you knew that it wasn't great even with Gemini and you shipped it anyway. Why management accepted that level of quality is not clear. Again, from technical standpoint, there is nothing impossible about making it a fully integrated smart home product with very strong assistant functions. You don't need another scientific breakthrough for it. [music] So, why did they ship it halfbaked? I can explain it through leadership. Again, they had a lot of turbulence on the Google Assistant team and many people were laid off, which goes back to the problem of leadership. And last but not least, Siri.
</details>

### 苹果的路径差异与最终破局

苹果在 2024 年承诺会推出一个聪明的 Siri。随后它被推迟，接着一次又一次推迟。当它终于在今年 9 月随 iOS 27 发布时，它是基于 Gemini 构建的，而人们评价它依然不太好用。如果我们回到 2010 年 Siri 刚推出的时候，它其实是苹果收购的一家初创公司。史蒂夫·乔布斯给创始人打电话提出收购。创始人们拒绝了，但最终还是以 2 亿美元的价格卖给了苹果。[音乐]

<details>
<summary>Original English</summary>
Apple promised a smart Siri in 2024. Then it got delayed, then again, and again. When it finally shipped in iOS 27 this September, it was built on Gemini and people say it's still not great. If we go back to when Siri launched in 2010, it was a startup that Apple bought. Steve Jobs called the founders offering to buy. The founders declined, but then eventually sold it to Apple for $200 million. [music]
</details>

乔布斯说服了他们，让他们相信自己理解这个愿景，并承诺会把 Siri 带入苹果的产品中。甚至在当时，该初创公司的 CEO 就预测，在 5 年之内，每个人都会拥有一个虚拟助手，并向其委派大量的琐碎任务。这在当时有点超前了，但其愿景一直都是让它成为一个执行者，让它能够执行各种各样的功能，从餐厅预订到周末计划。这个愿景从未真正实现，但两年前半当他们宣布 Siri 将变得非常聪明时，我们大家都抱有了希望。他们承诺了上下文理解、屏幕感知、跨应用的数百种操作，以及很多不同的东西——而所有这些，都发生在他们证明自己有能力将其做得足够可靠并能推向市场之前。彭博社报道称，Siri 是建立在两个系统之上的。旧系统基于简单指令运行，新系统基于大语言模型，但让它们协同工作在质量上造成了大量问题。随后他们开始发布小修小补，但并没有真正改变任何事情。最后，这一切又归结到了领导力上。《纽约时报》报道称，Siri 负责人 Robbie Walker 和技术高管 Sebastian Marin 争夺主导权，但随后蒂姆·库克对 AI 主管失去了信心，Siri 转由 Mike Rockwell 接管。然而，对苹果来说幸运的是，苹果是唯一打破了“样样通、样样松”恶性循环的公司。当我说这句话时，我指的是这些设备普遍存在的问题。他们没有去制造一个半吊子的助手兼半吊子的智能家居控制器兼半吊子的音箱，而是让 Siri 的声誉始终[音乐]与 iPhone 绑定。接着，他们造出了一个出色的音箱，并将其作为音频设备推向市场。他们没有通过在 HomePod 里塞进糟糕的 Siri 来毁掉它。[音乐] 他们卖出它，并把它定位成一个音箱。对此你可能会说：“好吧，但谷歌也有作为音频设备的 Home Max 啊。”是的，但到那时，最初的 Google Home 已经和助手音箱彻底绑定并被视为一体了，[音乐] 就像 Echo 那样。平心而论，HomePod 的发展也并非一帆风顺。苹果降过价，后来一度停产，两年后又重新复活。但没有人会做视频去问为什么 HomePod 这么蠢。Siri 的声誉并没有连累一个完全正常的音箱。

<details>
<summary>Original English</summary>
Jobs convinced them that he understood the vision and he promised that it would make Siri to Apple products. Even back then, the CEO of the startup predicted that in 5 years, everybody's going to have a virtual assistant to which they would delegate a lot of the menial tasks. That was a little bit ahead of its time, but the vision has always been to make it a doer and make it perform all sorts of functions from a restaurant reservation to a weekend planning. That vision never really came to life, but we all got hope 2 and 1/2 years ago when they announced that Siri would become very smart. They promised context understanding, on-screen awareness, hundreds of actions across the apps, lots of different things, all before they had proved that they could make it reliable enough to ship. Bloomberg reported that Siri was built on two systems. The old one working on simple commands and the new one being LLM based, but making them operate together created a lot of problems with quality. Then they started shipping small improvements, but that didn't really change anything. And lastly, it all came down to a leadership. New York Times reported that head of Siri, Robbie Walker, and tech executive Sebastian Marin competed over responsibility, but then Tim Cook lost confidence in AI chief and Siri moved under Mike Rockwell. What is a saving grace for Apple, however, is that Apple is the only one who broke out of the cycle of jackof alltrades, master of none. When I say that, I'm talking about these devices in general. Instead of building something that is a halfbaked assistant and a halfbaked smart home controller and a halfbaked speaker, they kept Siri's reputation tied [music] to the iPhone. And then they built a fantastic speaker and marketed it as an audio device. They didn't kill HomePod by putting bad Siri in it. [music] They sold it and positioned it as a speaker. To that you may say, "Okay, but Google also has Home Max as an audio device." Yes, but by that time the original Google Home had already been coupled and perceived [music] as the assistant speaker the same way Echo was. To be fair, HomePod wasn't a smooth ride. Apple cut prices on it, then it got discontinued, then it got brought back two years later. But nobody makes videos asking why HomePod is dumb. Siri's reputation did not affect a perfectly normal speaker.
</details>

我所要表达的核心观点基本上就是这样：亚马逊和谷歌把三件完全独立的事情混为一谈。它做不好一个优秀的助手；它是一个勉强合格的智能家居控制器，但你并不需要专门的设备来控制智能家居，你完全可以通过手机完成一切；而它又是一个差强人意的音箱。它什么都想沾边，但单拆出来又什么都不是。当助手表现拉胯时，整个设备都会招来反感。他们把 AI 强行拼接到助手上，但这并没有解决问题，因为症结在于商业模式。好消息是，Siri 创始人早在 2010 年兜售的那个技术引擎终于能够造出来了，而苹果解出了这道方程式的一半：把助手留在你的手机里，在你能造出真正可靠的产品之前，让音箱纯粹作为音箱来卖。现在，让我们寄希望于有人能把另一半解出来。但在此之前，我还是打算继续用我的 Google Home 来干我唯一用它干的事：嘿 Google，给我家猫放点音乐。正在 YouTube Music 上播放猫咪舒缓音乐——放松、深度睡眠、减压、宁静的钢琴曲。太棒了。再见。

<details>
<summary>Original English</summary>
What I'm getting at is basically this. Amazon and Google conflated three completely separate things in one. It's not a great assistant. It is an okay smart home controller, but you don't need a device for a smart home. You can do everything through your phone. And it's a decent speaker. It's everything at once and nothing on its own. When the assistant fails, the whole device gets hated. They bolted AI to the assistant, but that didn't fix the problem because the problem is the business model. The good news is that the engine that series founders pitched in 2010 is finally buildable and Apple sold half the equation. Keep the assistant in your phone and sell the speaker as a speaker till you can build a truly reliable product. Now, let's hope somebody builds the other half. But until then, I'm going to stick to the only thing I use my Google Home for. Hey Google, play music for my cat. playing calming music for cats. Relaxation, deep sleep, stress relief, peaceful piano music on YouTube music. Amazing. Bye.
</details>