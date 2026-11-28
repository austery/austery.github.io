---
author: AI Engineer
date: '2026-10-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=OmyqelTwpOo
speaker: AI Engineer
tags:
  - voice-agent
  - turn-detection
  - latency-budget
  - tool-calling
  - conversation-eval
title: 构建抗打断的类人语音智能体：LiveKit 的端到端工程实践
summary: LiveKit 的 Jesse Hall 探讨了如何构建类人语音智能体。他指出语音交互并非排行榜单模型评测，而是端到端对话工程。通过度量首音频/首句子延迟、异步解耦工具调用、融合音频特征的轮次检测（打断率降至4.5%），以及全对话闭环模拟基准测试，才能打造抗打断且自然的语音系统。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jesse Hall
companies_orgs:
  - LiveKit
  - OpenAI
products_models:
  - ChatGPT
  - Gemma 4 31B
media_books: []
status: evergreen
---
### 实时语音智能体的痛点与挑战

好，我们今天来谈谈**语音智能体**（voice agents）。我们日常接触的大多数智能体，都是在后台默默处理事情，对吧？它们帮我们写代码、做研究；我们给它们布置一项任务后就可以走开，等忙完回来，哪怕它们多花了 10 秒、10 分钟甚至有时是 10 个小时，我们其实并不太在乎，这是符合我们预期的。

但在过去大约一年里的某个时刻，你很可能与另一种智能体打过交道——**实时智能体**。也许是你给药房打电话时，也许是你致电航空公司时，我前几天打给一家汽车经销商时也遇到过一个。在对话的某一瞬间，你做出了最符合人类自然习惯的行为：你抢话了，打断了它，把它给搞糊涂了。于是整场对话彻底崩塌，显得极其生硬不自然。接下来你就做了我每次都会做的事——按零号键找人工坐席，大喊“转人工”，对吧？

那么，我们该如何解决这个问题？怎样才能让这些智能体尽可能像真人一样？

<details>
<summary>Original English</summary>
[music]

>> Um all right, we're going to talk about voice agents. And most of the agents that we deal with on a day-to-day basis, um they they do things in the background, right? They they write code for us, they do research, we give them something to do, a task, and we walk away, we come back, and we don't really care if they take an extra 10 seconds, an extra 10 minutes, maybe sometimes 10 hours, right? Um and we expect that. But at some point in the last year or so, you have probably interacted with another kind of agent, a real-time agent. Maybe when you called your pharmacy, maybe uh when you called the airline. I talked to one just the other day when I called a car dealership. And at some point in that conversation, you did the the most human-like thing possible. You spoke over it. You interrupted it. You confused it. And the entire conversation fell apart, it just didn't feel natural. And then you did what I do every single time, operator, hit zero, like get me to a human, right?

So, how do we fix that? How do we make these agents as human-like as possible?
</details>

比如在金融领域，如果你的用户打电话来安排一笔付款，他们中途改动了付款金额、改动了日期，而智能体却没有跟上节奏，那就会开始出问题了。特别是在金融领域，风险要高得多，对吧？所以，我们该如何解决？

今天我们就要探讨：**如何为金融服务等场景构建类人的语音智能体**。

<details>
<summary>Original English</summary>
Um and so, like in in a um a finance space, what if your caller was calling to schedule a payment, and they changed the the payment amount midway through, they changed the date, um and and the agent didn't keep up with it, right? That is where we start having issues, especially in the finance space. The the the the risk is much higher, right? So, how do we fix that?

So, we're going to talk about how can we build human-like voice agents for financial services.
</details>

### 语音是终极交互媒介

当你考虑构建一个优秀的语音智能体时，最先想到的往往是**延迟**。我们希望它越快越好，对吧？但延迟只是方程式的一部分。延迟有一个固定的预算空间，稍后我们会详谈这个数字。

但这里的核心关键词是**类人**（human-like）。我们如何让这些语音智能体尽可能像真人一样自然？这就是目标。

最近谈论语音的人不少，其中有些人大家可能很面熟。比如这位 Sam，他对语音模型感到非常兴奋，他提到语音模型正在改变我们与 AI 交互的方式，难道不是吗？还有右下角这个奇怪的名字 Swyx，不知道大家有没有听过他。他说语音是“原生模态”（OG modality），要想让 AGI 契合我们的意图，正确的模态就是做好语音 AI 工程。这是个相当大胆的断言。另外还有人说，我们在学会阅读之前就已经学会了说话，对吧？语音是我们所拥有的最自然的交互界面。那么，我们该如何让它尽可能自然、尽可能像真人？

现场举手示意一下，谁曾构建过语音智能体并部署到了生产环境？好的，我看到几只手举起来了。看来你们当中有人已经知道做这件事可能面临的挑战了。

<details>
<summary>Original English</summary>
And when you think about building a good voice agent, one of the first things that comes to mind is latency. We need it to be as fast as possible, right?

Well, latency is part of the equation. Latency has a finite budget, and we'll talk about what that is.

Um but the keyword here is human-like. How do we make these voice agents as human-like as we can? That's the goal.

So, there's quite a few people that are talking about voice lately. Um some of these might look familiar. We've got this this guy Sam. Um he's excited about voice models. He says uh that they're starting to change the way they that we interface with AI. Isn't that true? And then this this um weird name here in the bottom right, Swyx. I don't know if you've heard of him. Um he says oh uh that this is the OG modality. Um the correct modality for aligning AGI to our intents is very good voice AI engineering. That's that's that's a pretty bold statement there. And then like get here says we learn to speak before we learn to read. Right? Voice is the most natural interface that we have. So, how can we make it as natural as possible and human-like as possible? Quick show of hands, who who here has ever built a voice agent and deployed it to production? All right, I see a few hands. All right, so some of you know the challenges that you might face when doing this.
</details>

至于现场其他没做过的人，也许你曾见过非常出色的例子。你是否用过 ChatGPT 的高级语音模式（Advanced Voice Mode）与 ChatGPT 对话？

这里可以顺带提一句：OpenAI 实际上正是选择了 **LiveKit** 来驱动该功能的底层运行。所以这是个很好的用例与范例。LiveKit 是为这些类人智能体提供支持的开源实时框架与基础设施，能够让智能体听到、看到并与另一端的人交谈。

实际上，我们谈论的并不仅限于语音。与智能体的交互方式有很多种：语音、视频、数据流，甚至具身物理 AI。我们也有机器人部门。但**语音是入口，是最自然的模态**，也是存在大量技术挑战的地方。所以我们今天先聚焦于语音。

<details>
<summary>Original English</summary>
Um others here who have not built one, maybe you have um seen a very good example of one. Have you ever used ChatGPT's advanced voice mode to have a conversation with ChatGPT?

Okay, so that's that's cool. Segue here that OpenAI actually chose LiveKit to power that that functionality there. So, it's a very good example of a good use case or a good uh good example of a good voice agent. Um LiveKit is the open-source real-time framework and infrastructure for these human-like agents. Um agents that can hear, see, and speak to a person on the other end. And so, we're not just talking about voice, actually. Um there's there's multiple ways to interact with with agents, voice, video, data streams, uh even physical AI. We have a robotics division as well, but voice is the entry point voice is is the most natural modality, and voice is where there's a lot of challenges. So, we're going to focus just on voice today.
</details>

### 排行榜陷阱与级联管线

在传统的语音智能体中，你拥有的是所谓的**级联管线**（cascaded pipeline）。这是由三个模型协同工作的机制：语音转文字（STT）模型、大语言模型（LLM）以及文字转语音（TTS）模型。它们三者必须步调一致。此外还有一些新型模型，即实时的语音到语音（speech-to-speech）端到端模型，它们取代了传统的这套管线。但这还是一个较新的概念，技术正在不断完善，但尚未完全适配所有业务场景。

即便如此，面对三模型传统管线以及端到端模型，可选范围如此之广、复杂度如此之高，我们到底该从何下手？

看看我们眼前面临的选择吧：成百上千个模型，数十家服务商。再举手示意一下，谁曾仅仅根据排行榜来选模型？只要哪个模型排在榜首，我们就用哪个，对吧？

接下来我们就要聊聊为什么这种方式对于实时智能体完全行不通。我们不能仅仅从排行榜前几名抓个模型来用。

因为排行榜是对这些独立的模型或组件进行打分，而我们要交付的是**一整场对话**。我们需要能够对它们协同运作的表现综合打分。

<details>
<summary>Original English</summary>
So, in a traditional voice uh voice agent, you have what's called a cascaded pipeline. This is three models that work together. You've got your speech-to-text model, your LLM, and your text-to-speech model. And these all have to work in unison. And there are also these other models, these real-time models, speech-to-speech models, right? And they replace that pipeline. But that's a newer concept. Um it's it's getting better, but it's not quite there for every use case yet, right? But even then, we've got the traditional pipeline with three models, we've got the speech-to-speech models. There's so many things to choose from, so much complexity. Where do we even get started? And here's what we have to choose from.

Hundreds of models, dozens of providers, and quick show of hands here, who has ever picked a model based on a leaderboard? Like you pick them whatever model's at the top of the leaderboard, that's what we're going to use, right? Well, we're going to talk about why that does not work for real-time agents. We can't just pick models off the top of a leaderboard. Um because leaderboards, they score these models, these components, but we're shipping a conversation. We need to be able to score them together. So, we're going to talk about how we can do that.
</details>

我们来看一个实际场景：假设一位来电者想要缴纳账单，他说：“我想在 3 号付款。”（I want to pay on the 3rd.）

但 STT 模型听成了 30 号（the 30th）。

于是 LLM 开始按照 30 号做计划，并把这个日期录入了系统。LLM 并不知道实情，它根本不知道前面的语音识别模型搞错了。所有的错误自此一路向下游蔓延。排行榜是无法向我们展示这一点的，它无法评判这种情况，因为它只针对单独的模型进行测试。

此外，这些排行榜通常基于干净的音频数据给模型打分。但你的真实用户呢？他们可能是在堵车的路上开着免提打过来的，后座上还有小孩子在吵闹，对吧？因此，我们需要根据现实世界的实际场景和用例，来对我们自己的智能体进行评测打分。

如果我们掉入了这个排行榜陷阱，随便挑了一个模型，人们常问的第一个问题往往是：“我该选哪个模型？”他们看着排行榜选定一个，但我们真正应该问的问题是：**针对我的业务场景，我应该交付哪一套技术栈？**

这就是我们接下来要弄清楚的。我们该如何解答这个问题？

<details>
<summary>Original English</summary>
So, let's go through a scenario here. Let's let's suppose that a caller uh wants to pay their bill. And they say, "I want to pay on the 3rd." But the speech-to-text model hears the 30th. And then the LLM is planning now for the 30th, and that goes into the system. The LLM doesn't know any better. It doesn't know that the speech detects model got it wrong. And so all of those errors flow downhill from there. And so the the the leaderboard, it can't show us this. It can't judge this because it just was looking at it individual models, right? And so also these leaderboards, they score these models based on clean audio. But your callers, they're calling on the speakerphone in traffic with kids in the backseat, right? So we need to be able to score our own agents based on real-world use cases and examples.

So let's let's say that we fall into this leaderboard trap. We just pick a model. Um then the the first question that people ask is always, you know, which model should I pick? So they use a leaderboard, they pick a model, but that the actual question that we should be asking is which stack should I ship for my use case? And so that is what we're going to figure out. How do we answer that question?
</details>

### 正确的延迟度量：首音频与首句子

在回答这个问题之前，假设你已经挑选了一些模型并开始测量它们的表现如何。

比如你在测试你的 TTS 服务商。该 TTS 提供商的仪表盘上显示着**首字节时间**（TTFB, time to first byte）。指标看起来非常快——210 毫秒首字节，简直神速。

但我们实际测试了许多主流提供商，发现在返回首字节之后，有多达四分之三秒（750 毫秒）的静音。也就是说，**返回字节并不等于播出音频**。

所以我们真正应该关注的是**首音频时间**（TTFA, time to first audio）。用户到底需要等待多久才能真正开始听到声音？我们应该测量的是首音频时间，而不是首字节时间。

试想一下，一笔转账刚扣除，你在电话里询问：“我的付款成功了吗？”接着你迎来了整整 2 秒钟的死寂。这绝不会让人感到安心，对吧？因此，我们需要能够度量来电者所感受到的这段空白间隙。

大语言模型也是同样的道理。在文本交互中，我们测量的是**首 Token 时间**（TTFT, time to first token）。这是一个基于文本的指标，但 Token 同样不能直接等同于音频。你的 TTS 无法在只拿到一个 Token 时就开始发音，TTS 模型需要一整个完整的句子才能开始合成朗读。

因此，我们真正需要测量的实际上是**首句子时间**（time to first sentence）。因为生成 Token 很快的 LLM，并不一定就是最快输出第一个完整句子的 LLM。所以我们应该把目光放在首句子时间上。

<details>
<summary>Original English</summary>
So before we answer that question, let's say that you have picked some models and you start measuring. How are these models performing?

Let's uh say you're you're testing your TTS provider. And TTS provider on the dashboard, it's it's uh reporting time to first byte. And that looks really fast, 210 milliseconds time to first byte. That's super fast. Um but we've actually tested lots of popular providers that are shipping up to 3/4 of a second of silence after that first byte. So a byte does not equal audio. So what we're actually looking for is time to first audio. How much time does it take for our user to actually start hearing something? So time to first audio is what we should be measuring, not time to first byte. Um so imagine, you know, the payment went through and and and you you're asking, you know, um you know, did my payment go through?" And then you hear 2 seconds of silence. That's not very reassuring, right? So, we need to be able to measure this this gap that the caller hears.

Now, the same story for lang- uh large language models. So, time to first token is what we get in text. It's it's a text-based measurement, but tokens do not equate to audio, either, right? Your TTS can't start speaking on a token. A TTS model text-to-speech model actually needs an entire sentence to start speaking. Um and so, that's what we need to measure is actually time to first sentence. Um because a an LLM that is very fast at producing tokens is not always the same LLM that produces the first sentence the fastest. So, time to first sentence is what we should be looking at.
</details>

### 解耦工具调用：把麦克风还给智能体

绝大多数排行榜不测量的另一件事，是智能体需要执行后台动作。它们存在不仅是为了陪我们聊天，还需要在后端处理业务：查询某笔交易、核对付款状态、提交争议申诉等等。

这些操作都需要耗费时间——2 秒、10 秒、40 毫秒乃至数十秒。面对这种情况该怎么办？我们该如何掩盖 40 秒或更久的后端延迟？

答案是：根本掩盖不了。但你可以想想看，换作真人会怎么做？

真人会在系统执行后台任务时完全陷入沉默吗？不会的。他们会说：“请稍等一下，我正在帮您查询。系统有点慢，马上就好。”或者他们会继续往下推进，趁着后台处理的空隙先问你下一个问题。这就是人类的行为模式——多任务并行处理（multitasking）。人类做得到这一点，那智能体为什么不能这样多任务并行呢？

这是一个诱导性问题，因为智能体完全做得到，而且理应如此。它的实现形式是这样的：

这是我在本次演讲中唯一要展示的代码片段。这是一个常规的工具调用，但正是这单单一行代码带来了质的改变：

这一行更新（`async/await`，对该工具调用的异步等待）就是全部的诀窍所在。正是这一步把“麦克风”交还给了智能体。它让当前的对话流程与后端工具执行彻底解耦，不再共用同一个执行线程，它们现在彼此独立了。

这再次让智能体显得更像真人，因为当后台有任务在运行时，它依然能够维持对话不中断。

<details>
<summary>Original English</summary>
And then another thing that most leaderboards don't measure is these these agents, they need to do things. They're not just there to chat with us. They need to be able to do things on the back end. They have to look up a transaction, uh check for a payment status, submit a dispute, right? And so, these take time, 2 10 40 milliseconds. And and so, how do we handle that? How how do we hide 40 seconds or more of latency?

Well, we can't. That The answer is we can't. But ask yourself, what would a human do in the situation? So, is a human just going to go silent while the system is doing something? No, they're going to say, you know, "Give give me a second. I'm looking that up. Um system's running a little slow, almost there." Or they're going to move on and they're going to ask another question while the system is doing something in the back end. So, that's that that's the human-like behavior, multitasking, right? We can do that. So, why can't agents multitask and do that?

Well, that was a trick question because they can. They should. They should be able to. And this is the shape of that. Um this is the only code that I'm going to show you uh in this in this talk, but this is a normal tool call and the the one line is what makes the difference here. Um, this one line, this update, this async await, this awaiting this tool call is is the whole trick here and this is what's handing the mic back to the agent. This is allowing the conversation and the tool to stop sharing a thread. They're just they're separate now. And so um, this is what again makes the agent more human like because it's able to keep the conversation going as something is going on in the back end.
</details>

空口无凭，我这里准备了一个快速演示，大家可以听听它的实际表现。

>> 感谢致电镀金玫瑰酒店（The Gilded Rose Hotel），请问有什么可以帮您？

>> 你好，我想订一间房。

>> 请问您打算哪天入住？

>> 嗯，下周，周三到周五。

>> 下周三（7月30日）到周五（8月1日），对吗？

>> 没错。

>> 请问几位入住？

>> 两位。

>> 我们有双大床房、特大双大床房、套房以及顶层豪华套房可选，您更想要城景还是海景？

>> 海景。

>> 请问预订人姓名是？

>> Jesse Hall。

>> 是 Jesse Hall 吗？

>> 对。

>> 您的电子邮箱是？

>> me@me.com

>> 请问是 me@me.com 对吗？

>> 没错。

>> 您的电话号码是？

>> 555-123-4567

>> 是 555-123-4567 吗？

>> 是的。

>> 我们需要一张信用卡来保留房间，卡号是多少？

>> 我们先听到这里。

<details>
<summary>Original English</summary>
So, don't don't take my word for it. I've got a quick demo here and we'll listen and see what it sounds like.

>> Thank you for calling The Gilded Rose Hotel. How can I help you?
>> Yeah, I'd like to book a room.
>> What dates are you looking at?
>> Uh, next week, Wednesday through Friday.
>> Next Wednesday, July 30th to Friday, August 1st?
>> That's right.
>> How many guests will be staying?
>> Two.
>> I have queen two beds, king double queen, a suite or the penthouse?
>> Would you prefer a city or ocean view?
>> Ocean.
>> May I have your name for the booking?
>> Jesse Hall.
>> Is that Jesse Hall?
>> Yes.
>> What's your email?
>> me@me.com
>> Is me@me.com correct?
>> That's right.
>> And your phone number?
>> 555-123-4567
>> Is that 555-123-4567?
>> That's right.
>> I'll need a credit card to hold the room. What's the the number?

>> We'll stop here.
</details>

大家注意到了吧，整个对话一直在顺畅推进，没有任何尴尬的停顿。我甚至打断了它，它也能够顺理成章地接下去，从未陷入崩溃或显得生硬。而且可以看到，整个过程中都在不断发生工具调用和后台处理，它实际上一直在与后端通信，并在保存我提供的每一项信息。

但它所做的是：根本不等后端返回“好的，已保存，你可以问下一项了”再继续，而是直接进入下一个环节，始终保持对话的流畅流动。如果工具调用因为某种原因报错，它也会自行纠正，比如主动说：“请允许我核对一下某某信息”；如果出现更糟糕的问题，它在那种情况下就会把通话无缝转接给人工坐席。这才是我们的智能体应该具备的运作方式。

<details>
<summary>Original English</summary>
Okay, so you notice here that the conversation kept going. There were no awkward pauses. Um I even interrupted it and it just kept rolling with it, right? It It didn't ever fall apart or feel unnatural. And we see here, you can see the the tool calls that are happening along the way and the things that it's doing. It's actually communicating with a back end and it's saving every uh piece of information that I'm giving it. But what it's doing is it's not waiting for the back end to say, "Okay, that's saved. Now you can move on to the next one." "Okay, that's saved. Move on to the next one." It's moving on to the next thing immediately. It's keeping the conversation going. And if for some reason a tool call would have come back with an error or something, it would have then corrected itself. It would have said, "Let me Let me verify this or that, whatever happened, right?" And worst case scenario, if it was having issues, it would uh it would actually uh um pass me over to a human in that in that uh scenario then, right? So, this is how our agents should operate.
</details>

### 基于多模态音频特征的轮次检测

这件事还有另一个重要维度：智能体必须知道**何时该说话，何时该闭嘴继续倾听**。这被称为**轮次检测**（turn detection）。

LiveKit 配备了一个内置的轮次检测器，它不仅像大多数检测器那样仅仅分析文字转录文本，还会分析原生音频本身的节奏、音高和语调。我们公开发布了这项指标数据：行业内领先的替代方案仍会在 **9.9%** 的时间里打断并截断用户说话；而在我们的使用场景下（例如针对酒店智能体及其他场景进行测试），我们的打断率仅为 **4.5%**。

这就是我们在测试场景中跑出的数据。这些全部是开源的，大家完全可以在自己的数据集上运行这些评测，看看能得到什么样的数据，看看是否有更显著的提升。这同样是让语音智能体更具类人特质的一块关键拼图：让它们准确判断何时该停下、何时该继续听。

举个例子，假设我要付款，我说：“我想付 500……块零 55 块 2 毛 3 分。”大多数轮次检测器在听到“500”时就会打断插话，因为它们在转录文本上看到了“500”，又检测到了 2 秒的停顿，就自以为你说完了。但我们的系统能捕捉到语调变化，知道我还没说完，从而会耐心地继续等待。

<details>
<summary>Original English</summary>
Now, there's one more um axis of this, and that is knowing the agent knowing when to speak and when to to listen, when to keep listening. And so, this is called turn detection. And so, LiveKit has a um a built-in turn detector that doesn't only listen to the transcript like most turn detectors do. It also listens to the audio. It listens to the rhythm, the pitch, the intonation. And we published the numbers on this. The the leading um um alternative still interrupts and cuts users off 9.9% of the time. And ours, 4.5% in our use case. We ran it against the our hotel agent and others. And that hap And that is what the numbers that we got for our use cases. This is all open source. You can actually run these e-vals and run this against your data set and see what numbers you get. See if you get a um uh better uh increased numbers here. And this is just one small piece of the puzzle again to make these voice agents more human-like. Them knowing when to stop talking or when to listen. For instance, if if I were trying to make a payment and I said I'd I'd like to pay 500 and $55.23, right? Most of the turn detectors would have stopped at 500 because they saw 500 on the transcript and they saw 2 second pause, I must be done, right? But ours would have heard my inflection, knew I wasn't done talking, and it would have waited for me.
</details>

### 延迟预算与全对话模拟基准

现在我们再来看看延迟预算。这个间隙是指从**来电者说出的最后一个音节**，到**智能体发出第一个可听见的声音**之间的间隔。轮次检测器判断来电者是否讲完，语言模型根据临时转录内容开始构思回答，随后 TTS 尽快生成音频并播出。

你选择的每一个模型、每一次函数调用、每一次交接，全都塞在这个固定大小的有限时间窗口内。

如果你能将延迟大致控制在 **1.5 秒**以内，通话还能维持，对话不会崩塌；但在 1.5 秒时已经开始显得有些异样了。而如果你能把两个轮次之间的延迟压到 **500 至 600 毫秒**，对话就会真正开始展现出类人的自然感。

所以回到刚才的问题：“我能跑多快？我们是不是只要越来越快就行了？”这不是核心答案。真正的答案是：**在这个延迟窗口内，我能塞进一个类人化程度多高的智能体？**

延迟是固定的预算，我们知道如何适配它，但目标始终是如何让它尽可能像真人。

<details>
<summary>Original English</summary>
So, let's look now at that latency budget, that the gap. This is the gap between the caller's last syllable and the agent's first audible response. So, the turn detector decides when the caller is done, the language model begins preparing a response based on a provisional transcript, and then the TTS starts generating that audio as soon as it can. And so, every model that you choose, every function, every handoff, all of that is right here within this window, and this window has a finite number, a fixed window, a fixed size. And so, if you can stay roughly inside 1 and 1/2 seconds, the call still holds, the conversation holds. It's starting to feel a little off at 1 and 1/2 seconds. But if you can get down to 5 or 600 milliseconds between this the two turns, that's when it really starts to feel human-like. And so, that question before, how fast can I go? We just needed to get to go faster and faster. That's not the answer. The answer is how human-like of an agent can I fit within this latency window.

So, again, latency, that's a budget, and and we know how how to fit into that, but how can we be as human-like as possible? That's the goal.
</details>

综合以上所有内容，回到最初那个问题：“我该选哪个模型？”我们过去之所以无法解答，是因为排行榜只针对单一模型打分，而我们交付的是整场对话。

那么我们该如何回答这个实际问题？到底该选哪款模型？

我们必须做到这一点：**对整个对话流程进行整体测试**。

我们拿出一个完整的、具备实际功能的智能体——就像大家刚才听到的酒店前台智能体，它连着真实的后端，不是花架子 demo，而是真实可用的开源系统。我们用**模拟来电者**（simulated callers）去对它发起交互压力测试。

这些模拟来电者拥有明确的目标，他们中途可能会改变主意、会抢话打断、会含糊不清、还可以加入背景噪音。我们可以构建出极其逼真的现实场景，让所有这些模拟用户去向该智能体发起调用。

我们可以运行基于文本的模拟来单纯测试业务逻辑；也可以运行基于音频的模拟，全面测试语音识别能力、轮次交互以及整条语音管线。我们设计测试用例，明确描述来电者的意图、智能体应采取的动作以及预期的输出结果。

随后我们对这些结果进行打分评估。比如在酒店基准测试中，正确的预订信息是否成功写入了数据库？在金融基准测试中，扣划的授权金额是否准确无误？

我们不会仅仅根据“任务是否完成”来打分，因为智能体完全可以通过投机取巧来刷完成率。我们必须确保它走对了步骤：本该两步搞定的事情它是不是花了十步？它是否幻觉出了不存在的函数调用？这些都是我们需要在整个对话中验证的细节。

然后，我们替换技术栈中的模型。保持智能体逻辑不变、测试场景不变，只更换其中的模型，然后再跑一遍闭环测试。

每个模型接收到的是完全一致、逐字节相同的输入。我们换一个模型，跑一轮测试；再换一个模型，再跑一轮；循环往复不断迭代。在这个过程中，你就在为你特定的业务场景、为你自己的智能体建立起一套专属的定制化基准评测。有多少个智能体，就该有多少套基准测试。只有在你的专属场景下运行测试，才能找出最适合你的模型搭配。

<details>
<summary>Original English</summary>
So, if we add all this up, that that question, which model should I pick? We That was never something that we could answer because these scores, again, these leaderboards, they can't answer that because they're basing it off the models, but we are shipping a conversation. So, let's answer that actual question. How can we pick the models? Which models should we pick?

So, this is what we have to do. We test the conversation. We take a complete working agent So, that hotel receptionist that you heard just a minute ago, we took that. It has a real back end. Um it's an actual It's not just a demo. It actually works. Uh and it's open source. You can check it out. So, we take that agent and we put simulated callers against it. And these callers can pursue goals. They can change their mind. They can interrupt. They can mumble. We can add background noise. We can make sure that this is a real-world scenario, and we run all of these simulated users against that agent. Um we can run text-based simulations, which just tests our business logic. Or we can also run audio-based simulations that tests the speech recognition capabilities. It tests turn-taking. The entire um the entire voice pipeline is what's tested there. And so, we take the scenarios, and the scenario should describe what the caller wants and what actions the agent should take, what the outcome should be.

And then we score that. We score those outcomes. And so, in the hotel benchmark, you know, did the correct reservation hit the database? In a financial benchmark, you know, did the correct authorized amount get charged, right? And so, we we check these agents. We make sure that every all the outcomes are met. And then we don't score it based on just the completion alone, right? Because we know that agents can game completions, right? We have to make sure that they took the right steps. Did they take 10 steps when they only should have taken two steps, right? Did they hallucinate a function call? These are the things that we have to test, the entire conversation there. And then, we swap the stack out. We We have the same agent, the same scenarios, but we change the models. And then, we run that loop again. The identical input Every model sees identical input byte for byte. We swap the models, we run the loop. We swap the models again, we run the loop continuously over and over, and we are building at that point a benchmark, a personalized benchmark, for our use case, for our agent. So, there are as many benchmarks now as there are agents. You run this against yours, and you find out which models work best for your situation. That is the only way to find out which model is best for you.
</details>

这就是你发现意外惊喜的方式：能够以最快速度为你给出正确答案的模型，才是最适合你的模型，对吧？而出人意料的是，这个模型往往并非排行榜排在第一位的那个，但它对你的场景而言就是最好的。再次强调，这些基准测试、模拟仿真以及整套方法论，全部是开源的。大家可以去查阅代码，在自己的智能体上运行，看看表现究竟如何。

这是该基准测试在我们酒店前台智能体上的运行结果。在我们的酒店前台测试中，排名最高的 LLM 是运行在 LiveKit 推理服务上的 **Gemma 4 31B**。

大家可以注意到第二行：完全相同的 Gemma 4 31B 模型，放在另一家服务商上运行时明显要慢。这是因为 LiveKit 专门针对语音工作负载优化了推理服务。同时 LiveKit 是模型中立的（model-agnostic），你可以随意使用任何喜欢的模型。只要把模型插进去，就能测出哪一款最适合你的业务场景。

<details>
<summary>Original English</summary>
Now, this is how you catch surprises. Um a model that that gets the answer for you the quickest is the right model for you, right? And surprisingly, that model may not be the model that that's at the top of the leaderboard, right? But it's best for your use case. And again, these benchmarks, the simulations, all this this methodology, it's all open source. So, you can You can check it out for yourselves, you can run it against your agent, and see how yours performs.

And so, here is the results of that benchmark on our hotel agent. This is the LLM that ranked the highest for our hotel receptionist agent. That's Gemma 4 31B on LiveKit inference. You notice on the second line, the same model, Gemma 4 31B on another provider, was slower. So, LiveKit optimizes its inference serving for voice workloads. And LiveKit is model agnostic, so you can use any model that you want. So, again, you plug those models in, and you figure out which one is work it will work best for your use case.
</details>

### 构建类人智能体的实操清单

如果说这场演讲只能让你记住一件事，请记住这一点：**语音智能体绝不仅仅是一个连着扬声器的聊天机器人**。它背后蕴含着极高的复杂度，是一个必须像人一样做出实时反应的系统。我们必须让它尽可能贴近真人。只有从这个视角去评估它，我们才能真正把它构建好。

这里有一份检查清单，大家可以拍照记录一下：

- 设定来电者所感知的**延迟预算**。
- 严谨度量**首音频时间**与**首句子时间**。
- 对关键日期进行确认；涉及资金往来的任何操作，必须确保设置好完备的校验机制。
- 访问账户前必须验证身份。
- 当耗时的工具在后台运行时，**保持倾听**，维持对话继续推进。
- 通过模拟仿真，反复对完整对话流程进行闭环压测。
- 校验最终状态、隐私保护措施、是否存在多余无用的工具调用，以及轮次接管表现。

把每一次发现的错误都沉淀为回归测试场景，一次又一次地持续验证。

大家可以从自己最关心的某一个具体工作流或故障点开始，不断迭代。跑起来，仔细听对话的实际效果，检查后端发生的变化。

我希望在不久的将来，当我们打给任何一个语音智能体时，就算我们抢话打断它、把情况弄复杂，它也能从容接招、自然应对，带给我们真正如同与真人对话一般的体验。

这就是我们的目标。但我需要你们每一个人亲自动手把它造出来。非常感谢大家！

>> 哇呼！

<details>
<summary>Original English</summary>
Now, if you remember one thing from this this entire talk, remember this that a voice agent isn't just a chatbot with a speaker attached. It's There's so much more complexity there. It's a real-time system and that needs to respond like a person. We need to make it as human-like as possible. And and and when we evaluate it from that viewpoint, we will be able to to build that.

And so, here's a checklist. You can take a take a photo here. We need to set our latency budget that the caller hears. Measure time to first audio, time to first sentence. Confirm critical dates. Anything that's financial money, we need to make sure that we have those those checks in place. Verify identity before an account is accessed. Keep listening while slow tools run. Keep the conversation going. And then run the complete conversation repeatedly through simulations. Test the final state, privacy safeguards, unnecessary tool calls, turn-taking. All these things and then when you find these failures, you turn those into regression scenarios and you keep testing over and over again.

So, start with one one of those workflows or failures that you care about. Keep Keep iterating then. Run it. Listen to the conversation. Check what happened on the back end. At some point in the very near future, I hope, that we all call one of these voice agents and we talk over it. We confuse it and it just rolls with it and it's and it's a very human-like experience. That's That's our goal, but here's what I need from each and every one of you. I need you to go build that. Thank you.

>> Woo!
</details>