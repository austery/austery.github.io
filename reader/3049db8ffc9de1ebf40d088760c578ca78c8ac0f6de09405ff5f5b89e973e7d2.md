---
author: Latent Space
date: '2026-08-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MwNvowwcZOo
speaker: Latent Space
tags:
  - voice-agents
  - speech-to-speech
  - cascaded-pipeline
  - latency-optimization
  - llm-evaluation
title: Forward Deployed：2026年语音AI的实战与技术演进
summary: 本期访谈深入探讨了2026年语音AI代理（Voice Agents）的最新技术架构与实战经验。多位来自前沿企业（Vapi, Daily, Smallest AI, Exoflop Labs）的专家共同探讨了级联管道（Cascaded Pipelines）与原生语音对语音模型（Speech-to-Speech）的优劣、延迟与稳定性的权衡、多模态异步智能（如Hydra模型）的应用，以及在企业级部署中如何通过工作流与提示词优化解决口音、多语言和评估难题。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Vapi
  - Daily
  - Smallest AI
  - Exoflop Labs
  - Decagon
  - OpenAI
  - Nvidia
products_models:
  - Hydra
  - Pipecat
  - Gemini 2.5
  - Electron
  - GPT-4o
media_books: []
status: evergreen
---
### 开场与FDE背景

**Dayton**: 好的，我们现在在远程录音室里。这一期节目非常特别，因为我们即将在 Dayton Space 上推出第四个播客系列。人们可能不一定能完全跟得上我们的节奏，因为我们覆盖了许多不同的领域。**Basil**，你之所以进入我的雷达视野，是因为你一直在为**前线部署工程（Forward Deployed Engineering, FDE）**举办各种晚宴、聚会、小组讨论和播客。你还在 AIE 主持了 FDE 专场，而且办得非常成功。所以，欢迎来到我们的播客。

<details>
<summary>Original English</summary>

**Dayton**: All right, we're in the remote studio. This is a special one because we're launching a fourth podcast on Dayton Space. People don't necessarily keep track, but we cover different things. Basil came across my radar because you're doing all these dinners and gatherings and panels and podcasts for deployed engineering. You hosted the FDE track at AIE and it did super well. So, welcome to the pod.

</details>

**Basil**: 好的，谢谢。

<details>
<summary>Original English</summary>

**Basil**: Yeah, thanks.

</details>

**Dayton**: 那么，你的播客已经运行了一段时间了。是什么让你决定专注于 FDE 的？另外，你平常是如何做自我介绍的？

<details>
<summary>Original English</summary>

**Dayton**: So, you've been running your podcast for a while. What made you decide to focus on FDE and you know what's your typical self intro?

</details>

**Basil**: 好的，我最开始是在 **Credit Karma** 担任产品经理，在那儿工作了几年。之后，我在一家小型风险工作室（Venture Studio）工作。最后，我创立了一家名为 **Exoflop Labs** 的咨询公司，当时我们主要与零售商、保险公司等客户合作，核心就是为他们构建 AI 代理。这大概是两年前的事情了。

所以对我来说，这就像是之前做产品工作的一种自然延伸。比如，我与客户合作，他们有特定的使用场景和想要构建的项目，我去理解他们的需求，进行权衡取舍，然后帮助他们把产品做出来。这确实感觉像是非常自然的延续。

在今年一月份，我们开始与几家私募股权公司合作。很多人都在说：“嘿，我关注了 Twitter 和 LinkedIn 上的各种动态，但我根本分不清哪些是营销噱头（BS），哪些是真正落地的东西。”因此，我就想：“为什么不直接把那些在优秀公司里研发酷炫技术的专家请过来呢？”我们可以深入探讨他们正在做的事情，把它记录下来并发布出去。希望大家能够从中汲取经验，并应用到自己的业务中。这就是我后来开始做炉边访谈、小组讨论以及播客的初衷。

<details>
<summary>Original English</summary>

**Basil**: Yeah, so I started as a product manager at Credit Karma for a couple years. I worked at a small venture studio after that and then I ended up starting a consulting business called Exoflop Labs where we were working with like retailers, insurance companies, that sort of thing just building agents essentially. This was like two years ago. So it just felt like a natural extension of a lot of the product work that I was doing earlier. It was like, hey, I'm working with customers. They have a specific type of project that they want built for some use case and I'm going to understand what they want. I'm going to make trade-offs and I'm going to help them build that. So, yeah, I just felt like a natural extension of what I was doing. And so, back in January, we started working with a couple private equity firms and a lot of people were just like, "Hey, like I'm following on what's going on on Twitter, what's going on on LinkedIn. I don't know what's marketing BS and what's not." So, I was like, "Why not just bring on people who are working on the cool stuff at cool companies? We will talk about what they're working on like we'll do a deep dive and we'll record it we'll post it and hopefully people can take learnings away that they can apply to their businesses" and that's why I ended up starting doing a lot of the fireside panels and the podcasts that I've been doing since then.

</details>

### 热门的语音智能

**Dayton**: 你能顺便罗列一下你们最受欢迎的那些“代表作”，也就是你们之前涵盖的核心话题吗？

<details>
<summary>Original English</summary>

**Dayton**: Can you give like rattle off just your greatest hits like what you've covered?

</details>

**Basil**: 没问题。我们的第一期节目是关于**智能体工程的未来（Future of Agentic Engineering）**。我们邀请了像 **Factory Cognition**、**Composio**、**Soundgrap** 这样的公司。我们也做过关于语音代理（Voice Agents）的专题讨论，也就是我们今天主要要展示的这部分内容。此外，我们还做过关于计算机使用代理（Computer Use Agents）以及企业级代理（Agents in the Enterprise）的专题。我们探讨了大量的内容，就是为了深入挖掘这些技术的底层技术细节。

<details>
<summary>Original English</summary>

**Basil**: Yeah, so our very first episode was on the future of agentic engineering so we brought on companies like Factory Cognition, Composio, Soundgrap. We've done panels on voice agents which is actually the one that we're going to be showing here. We've done some on computer use agents. We've done agents in the enterprise. So, we've done a ton of stuff just to get nitty-gritty into the details of a lot of this stuff.

</details>

**Dayton**: 明白。对于我们的首次合作专题，你选择了语音代理这一期。我们接下来会听到什么内容？其中最让你感到兴奋或脱颖而出的是什么？

<details>
<summary>Original English</summary>

**Dayton**: Yeah. And I guess you know, you picked the for for our sort of first feature, you picked the voice agents one. What are we about to listen to and what stood out in particular?

</details>

**Basil**: 好的。我们当时邀请了来自 **Decagon**、**Vapi**、**Retail**、**Daily** 以及一家叫 **Smallest AI** 的公司的专家。基本上，我们共同探讨了目前构建语音代理的最新技术水平，因为这是一个非常火热的使用场景。我认为 **Sierra** 甚至提到过，当前 AI 领域中最具竞争力的市场之一就是构建语音代理。

因此，我认为讨论这些代理是如何被实际构建出来的，以及在该领域研发的工程师仍需解决哪些难题，是非常有价值的。例如，我们讨论了目前构建语音代理的行业主流方案依然是**级联管道（Cascaded Pipeline）**。这是一个三步走的过程：语音转文本（Speech-to-Text, STT） -> 大语言模型（LLM） -> 文本转语音（Text-to-Speech, TTS）。我们分析了为什么要采用这种方案，以及为什么我们不直接使用纯粹的语音对语音模型（Voice-to-Voice Model）。事实证明，纯语音模型在目前的技术阶段还不够稳定和可靠。

我们还深入讨论了在构建语音代理时必须做出的权衡。比如，你必须在回答的“智能度”与“延迟”之间进行博弈：你可以获得非常聪明的回答，但代价是更长的响应时间。在不同的业务场景中，这种取舍可能有利有弊。我们还谈到了可靠性：有些大模型公司的基础设施可能不是百分之百稳定。当 Anthropic 的 Claude Opus 宕机时你该怎么办？你必须建立一套模型重试与退避机制（Waterfall of Models），以便在主模型不可用时迅速接管，确保你的语音代理不会直接罢工。

我们还讨论了**轮流说话机制（Turn-Taking）**。这听起来像是一个微不足道的问题——比如你正在和一个语音代理说话，而你突然停顿了一下。那么，语音代理如何判断你是说完了需要它插话回答，还是你只是在停下来思考？因此，轮流说话在实际工程中绝非易事。我们对此进行了不少探讨。

接着我们还聊到，我记得 **Pipcat**（注：此处原文应为 Pipecat / 嘉宾 Varun 的团队）在世界博览会（World's Fair）上构建了一个语音代理，对吧？我们稍微展开了讨论。他们构建的这个语音代理可以接听任何人的电话，并解答关于大会的各种问题。他们在这个过程中收集了大量真实的交互数据，并将其转化为一个基准测试（Benchmark）。

<details>
<summary>Original English</summary>

**Basil**: Yeah. So, we brought on some people from Decagon, Vapy, Retail, Daily, and a company called Smallest AI. Basically, we just talked about like what is the state-of-the-art in building voice agents cuz that's a very hot use case. I think Sierra even talked about this is this is like one of the most competitive markets in AI right now is like building voice agents. And so I thought it would be useful to talk about how they're actually built and some of the things that you know engineers who are building in this space still have to contend with. So for example, we talk about how like the state-of-the-art right now in building voice agents is a cascaded pipeline. So we talk about how it's like a three-step process. you go like speech to text LLM then text to speech and we talk about like why is that versus why don't we just have a voice to voice model like why don't we use that like the reality is those just are not super reliable right now we also talk about like the trade-offs that you have to make when you're building voice agents so you have to trade off like the intelligence of responses that you're getting versus the latency so you can get very intelligent responses but you're also going to trade off it's going to be a slower response and so for different use cases that might be good or bad we also talk about like reliability so there are some LLM companies that may not be like super reliable in terms of like their infrastructure. And so like what do you do when opus goes down? Like you need to have a waterfall of models to basically pick it up so that your voice agents don't just stop working. We also talked about like turn taking and how like it seems like a trivial problem where hey like you're talking to a voice agent and let's say I pause. So how does the voice agent know that hey like I should I should interject and I should actually like respond to you versus oh the person is just taking time to think. So turn taking is actually like not a trivial problem to solve. And so we talk a little bit about that. And then also we even talk about like how um I think Pipat built a voice agent for the World's Fair, right? So we even talked about that a little bit and how like I think I mean you can talk about this a little bit but I think like you guys built a voice agent to like if anyone calls the voice agent it'll answer questions about the conference and then you got a ton of like real world information and turn that into a benchmark.

</details>

### 客户支持与痛点

**Dayton**: 我想澄清一下，其实我没有看到具体的数据分析，所以我也不知道到底有多少人拨打了那个电话。可能很多只是出于好奇随便试了试。这毕竟只是一个大会，大家都知道这是个什么性质的东西。但我觉得那确实是 Daily 在实际场景中的一次极佳部署。**Daily** 是赞助商，何乐而不为呢？

<details>
<summary>Original English</summary>

**Dayton**: I mean to be clear I have no idea actually. I never looked at the analytics so I have no idea how many people actually called. probably you know people just kicking the tires you know like it's not it's not that serious like we it's a conference people know what it is yeah but you know I think it was a good deployment of use case daily is a sponsor so why not

</details>

**Basil**: 我必须得说，现在绝大多数语音 AI 的应用场景都是客户支持（Customer Support）。天呐，这世上有太多的呼叫中心了，每年有数千亿美元的花销，而且用户体验普遍非常糟糕。因此，我们由衷希望能够提高这个领域的整体技术水平。我想这也是 Decagon 这种公司以及我们所有人存在的意义。

对我而言，如果只是那些专门销售语音管道的厂商告诉你“级联管道就是最前沿的方案”，这并不算太有趣，因为这显而易见。但是，当真正专注于客户支持和实际业务落地的人也得出同样的结论——即“目前的纯语音端到端模型还没准备好，甚至可能永远无法完全达到要求，我们必须采用级联这种方式”时，这就有说服力了。

实际上，真正切身感受到这些技术缺陷的并不是研究人员（Researchers），因为研究人员永远只想通过更大的模型来解决一切问题。产品工程师会尝试去构建它，而真正需要直接面对客户的**前线部署工程师（FDE）**则会抓狂：“兄弟，这玩意儿犯了个极其严重的低级错误，绝对不能再发生了。你如何向我保证这点？” 嗯，这就是现实（笑）。

<details>
<summary>Original English</summary>

**Basil**: I you know I I would say that vast majority of voice stuff is support and like yeah oh my god there's you know so many call centers out there hundreds of billions of dollars spent on this stuff and they're all you know bad so hopefully we can sort of raise the the state of the art which you know I think that's why Decagon and all these things people exist To me, you know, it's not as interesting if a bunch of people who are obviously selling you voice pipelines telling you that voice pipelines are the state-of-the-art. Like, yeah, duh. But, you know, having having the the people actually focus on customer support and all those things also basically conclude like, yeah, like the models are not there yet. They may never be. And actually, this is just the way that you got to do it. And the the people that really feel it are not the researchers cuz researchers just always want bigger models to solve everything. And the product engineers will try to do it, but the FDES, the people actually dealing with customers will be like, "Dude, they made this like horrible mistake. Like, this can never happen again. How can you guarantee me that?" Well, [laughter]

</details>

**Dayton**: 没错，我们甚至对这一点也进行了一些探讨。比如，我们讨论了呼入（Inbound）与呼出（Outbound）场景的差异。因为我们曾经尝试过运行一个呼出的使用场景。结果发现，在呼出场景中，当人们接起电话，并在意识到对方是机器人（Bot）的那一瞬间，大多数人会直接挂断电话。那么，你怎么解决这个问题？

<details>
<summary>Original English</summary>

**Dayton**: yeah. Yeah. Yeah. So, like actually we even talked about that a little bit. So, like we talked about like the inbound versus outbound use cases cuz we even did that once. We like ran an outbound use case and like what you find is whenever somebody like picks up the phone and you do an outbound use case, a lot of the times they just hang up as soon as they realize it's a bot. So we even talked about that like how do you how do you solve for that?

</details>

**Basil**: 哈哈，这是一个很好的悬念。我很欣赏你们的工作，也非常期待在 Dayton Space 上展示它。我们未来会一起做更多的合作。但这至少为 Dayton Space 的听众提供了一个关于 FDE 的极佳入门科普。

<details>
<summary>Original English</summary>

**Basil**: All right. Uh that's a good teaser. I you know I admire your work. Uh I'm excited to feature on space. We'll be doing more uh in future together but uh this is just an intro to FDE for uh at least for at least a l space audience.

</details>

### 语音代理架构101

**Dayton**: 我觉得这可能是一个很好的切入点，可以让大家先上一堂 101 的基础课，了解一个简单的语音代理架构到底是怎样的。这或许是问 **Varun** 的好机会，因为你们开发了 **Pipecat**。

<details>
<summary>Original English</summary>

**Dayton**: I think this might be a good place to give everyone a 101 lesson on what does a simple voice agent architecture look like. So maybe that's a good question for Brun because you guys uh run Pipecat. So

</details>

**Varun**: 是的。现如今构建语音代理有很多种方法，因为事物底层的复杂性是其本质决定的。但最简单的方案就是我们所说的**级联模型（Cascade Model）**。

它的典型流程是：首先是语音输入，通过特定的传输通道接入，这可以是 **WebRTC**、电话呼叫或 Web Sockets。语音数据进入系统后，首先被送入**语音转文本（Speech-to-Text, STT）**模型进行实时转录。在这个环节，通常会并行接入一些辅助模型，用于背景噪音消除和人声隔离。如果背景中有多个人说话，它会把焦点隔离在核心发言人身上，去除环境杂音。

接下来是**轮流说话检测模型（Turn Detection Model）**。这与文字交互不同，在打字时你明确知道自己什么时候写完——你按下回车键，消息发送，LLM 随之启动。但在语音中，没有类似于对讲机或“按键说话（Push-to-Talk）”的机制。除了在面对面交谈中你可以通过眼神和表情判断对方是否说完之外，在电话里，我们通常必须使用**语音活动检测（Voice Activity Detection, VAD）**和智能转轮模型（Smart Turn Model）来分析对方是否已经说完了。

如果我在半句中间停顿了一下，这与我把一句话完整说完并停顿是有本质区别的。在这一步，你甚至可以直接在前端使用一些“语音到语音”的轻量级检测模型。

一旦通过转录获取了文本，我们就会将其发送给大语言模型（LLM）。LLM 会进行推理，输出回答，或者在这个过程中触发某些工具调用（Tool Calls）以及其他后端操作。

当 LLM 吐出完整的文本响应后，会立即将其送入**文本转语音（Text-to-Speech, TTS）**系统。TTS 的生成速度通常远快于实时播放速度。因此，系统必须解决如何把生成的音频流式传输（Streaming）回给终端用户的问题。音频流会顺着之前的同一个传输信道回去，最后在用户的扬声器里播放出来。

但在 2024 至 2025 年间，随着人们需求的发展，系统正变得越来越复杂。比如在呼出场景中，**催收（Debt Collection）**是非常常见的一个应用。你接到电话，机器人告诉你有一笔欠账未付，问你是否愿意付款并给出几个选项。对于这类场景，如果人类偏离了正常对话轨道，开始说一些莫名其妙的话，机器人其实可以直接挂断电话。它没有任何义务非得留在通话中。因此，在这种场景下设计护栏（Guardrails）是比较容易的。机器人非常清楚它能接受哪些输入，也知道哪些输入它可以直接忽略。

但如果换成呼入场景，情况就完全不同了。因为机器人此时没有任何上下文。虽然它大概知道自己存在的职责，但它根本不知道打电话进来的用户究竟要干什么。如果对方是一家小商铺，比如一家花店或小理发店，那可能还好，因为涉及的事情非常有限。但如果是面对像**亚马逊（Amazon）**这样极其复杂的平台呢？平台上有一打（甚至十亿种）商品，而且不同的商品类别有着完全不同的处理政策。它是实体商品还是虚拟商品？是低价值产品还是高档贵重物？是电子设备还是生鲜？

为了在通话中实时决策，大模型必须在瞬间理清所有这些规则。然而，你无法把所有的规章制度、政策条款都塞进一个提示词（Prompt）里。因为大语言模型是有缺陷的：它们往往只能记住开头 4% 和结尾 4% 的信息，中间所有的内容它们都容易遗忘。如果你把庞杂的退换货政策放在上下文的中间，模型就极易发生幻觉（Hallucinate）。

因此，你必须采取更聪明的策略，这就是引入多模型协同的地方。你可以引入一个**上下文压缩模型（Compaction Model）**。就像我们现在使用编程代理（Coding Agents）一样，如果你使用的是拥有百万上下文（1 Million Context）的模型，当上下文填充到 25% 的时候，你就该开始紧张了；当它接近 70% 的时候，那就非常危险。通常在 25% 的节点，你就得考虑：“我是不是应该开始压缩上下文、保存阶段性工作，以防模型彻底失控？”

在过去两年中，语音 AI 在这方面其实比编程代理走得更超前。我们早就解决了许多当时看起来非常棘手但又迫在眉睫的现实问题。比如从第一天起，我们就知道必须做**上下文压缩**。因为以前模型很小，一旦交互超过五轮或十轮，上下文累计到 10,000 或 50,000 token 时，模型就直接崩溃了。所以，我们的很大一部分工作就是确保机器人不会产生幻觉，并在对话流转中精准追踪当前的对话状态。而且，人机对话的单次发言通常都比较简短，而机器人往往倾向于说得比人多。你必须实时追踪：人类究竟说了什么？我们目前处于对话流的哪一个步骤？

<details>
<summary>Original English</summary>

**Varun**: Yeah. So there are many ways to build one nowadays because the complexity is the nature of things. But the simplest one which is called a cascade model is typically uh voice input. Uh it comes through a transport. It could be web RTC, phone call or web sockets. It goes into the mo into a speech to text. Uh the transcription happens. There can be some additional models right there for background noise removal, voice isolation. So if there are few people in in the foreground, it will isolate to one person, remove the background noise, it there's a turn detection model, unlike text where you know when you're done, you press enter and the message goes and the LLM starts to like execute with voice there is no it's not walkie-talkie or pushto talk. So there is no additional uh information apart from like if you're looking at the face you could actually figure out that the person stopped speaking but typically use something like a voice activity detection and a smart turn model to like figure out that the turn is complete. Um if I pause mid mids sentence that's different from like if I finish speaking and pause uh you may use a speech to speech model right there. Uh then when you have the text you uh from the transcription then you send it to an LLM. The LLM may respond with an inference. It may actually tell you it may infer to tool calls. It may do a bunch of things there. You get that when you have the full output you text to like you do uh text to speech DDS and uh it's usually faster than real time. Uh so then you have to like figure out how to like stream it back to the end user. It'll go over the same p transport that that you spoke over and then it'll play it back on your speakers. Uh but things are getting more complex as people, you know, this was like 2024 25 people wanted to do this. If you're doing an outbound use case, like you do an outbound call, debt collection is quite commonly a use case for this. Um you get a call, they tell you you have like an unpaid bill. um they ask you if you would pay it or you know give you a certain set of options. Uh for that the bot has really like if you go off the rails like the human goes and starts saying random stuff it can just drop the call. It's not obligated to stay on the call in any way. So guardrails are easy. Um it knows what the inputs it can accept. It knows what inputs it can it doesn't need to respond to. It flips when you have an inbound use case because the bot has no context like has some context of why it exists but doesn't know why you the person who's calling it is if you're a mom and pop shop like a flower shop or or like a barrier or something like that okay there's only like finite things that you can do there but if you are more complex let's say you're Amazon right there like a billion products on your platform um and you have different policies for different things is it uh you know is it a physical item is it a cheap physical item is it uh an expensive item u is it an electronic item like all of that so it needs to figure and then when you said something like you know you can't put all of that inside a single prompt because it will like LLMs are you know goofy in that sense that always remember the first 4% and the last 4% and everything in between they kind of forget uh so if you have a return policy right in the middle of that context, it's very likely it'll hallucinate. So you have to do more smart things and that's where you have like more models come in. Uh you can have a compaction model like we're all using coding agents now, right? So you know like if you're using like a 1 million context model like at 25% you should become nervous at that 25% mark. is nowhere near 70% mark but at 25% mark you're like okay should I start compacting and like saving my work so that this thing does not go off the rails right the same thing I think voice AI has been like one generation of ahead of coding agents like we've all in the last two years solved things that felt like so alien but very tangible for us which now when we see coding agents do we like man compaction we we were doing compaction from day one like we knew like after five tons or 10 tons and your context was only 250 tokens or 250,000 tokens or 50,000 tokens, you know, models were really small like before and at 10,000 tokens it would like go off the rails. So, so a lot of our work is I think about like making sure that the bot does not hallucinate and trying to like keep track of the conversation as the the turns progress. And the turns are fairly short because the either way the bot is more likely to speak more than the human did. So you have to like kind of keep track of of like what did the human say? Where are we in the conversation?

</details>

### 级联 vs. 语音对语音

**Dayton**: 明白。那么这个问题我想请你们三位中的任何一位来解答。你们在自己的语音代理中，是否也是使用这种级联模型？

<details>
<summary>Original English</summary>

**Dayton**: Yeah. So um I guess this is a question for one of you three. Uh so do you guys use this like cascading model for your guys' voice agents?

</details>

**Varun**: 是的，级联模型依然是我们提供的主要服务之一。不过我们也同时提供级联和原生的“语音对语音”两种方案。

<details>
<summary>Original English</summary>

**Varun**: Yes, that is one of the major offerings that we have. Cascading and speech to speech.

</details>

**Dayton**: 好的。我原本想问，级联听起来似乎太复杂了。为什么不直接做端到端的“语音对语音”？为什么要搞一个如此繁琐的三步管道？

<details>
<summary>Original English</summary>

**Dayton**: Yeah. I was going to ask like that sounds too complicated. Why not just go voice to voice? Like why not? Like why do you have to have this like crazy three-step process?

</details>

**Varun**: 我觉得最直观的解释是：当你拨打一个体验极佳的原生“语音对语音”演示电话时，你会惊叹：“哇，它能听懂我的笑声，还能根据我的语气语调做出反应，而且非常敏捷、速度极快！”

但紧接着，你测试实际业务。它问你想把预约安排在周几，你回答说“下周”。它说：“太好了，那我们定在 6 月 10 日？”你说：“不，其实今年是 2030 年（假设在扮演某个场景）。”然后它说：“没问题，确实是 2030 年，那我们就预约在 2030 年 6 月 10 日吧。”你说：“太好了，听起来不错。”

在类似这样的严谨业务流中，这种端到端的语音模型极易出现逻辑脱轨。因此，从这个角度来看，我其实非常想听听 Smallest AI 方面的意见，看看你们在这方面的技术演进。因为我们一直非常密切地关注着这些原生语音对语音模型（Speech-to-Speech Models）的性能表现。

但就目前而言，我们主要的观点是：**级联模型允许你强制执行更多、更严格的业务护栏（Guardrails）**，并对整个对话过程保持微观控制。你可以规定：用户的每一次输入，都必须先通过过滤监督模型来检测是否存在提示词注入（Prompt Injection）或社交工程（Social Engineering）攻击。接着，文本才会沿着流水线送入意图选择（Intent Selection）模块。然后，我们通过提前检查条件来优化上下文。例如，在面对这一特定客户时，如果他是 VIP 客户，我们就应用提示词 A；如果是普通客户，我们就应用提示词 B。

我们会在前置环节把这些业务逻辑理顺，再进行压缩和打包，将最干净的系统提示词输入给生成模型，从而拿到回答。拿到模型回答后，我们还可以进行一轮真实验证（Fact-Checking）：这是真实的吗？今年到底是 2030 年还是 2026 年？验证无误后，才把语音放给电话那头的用户。

这里显然存在一个核心约束：你如何让这样一个多步骤的复杂管道保持高性能？你如何在流水线中最大程度地并行化（Parallelize）这些步骤？

我认为，在过去的六个月里，我们 Daily 的工程团队完成了一项了不起的壮举：他们在整个级联管道的每个微小环节中，十毫秒、十毫秒地去压榨和削减延迟，以确保即使后台在进行大量的安全检查和业务处理，用户听起来依然觉得足够自然和灵敏。这是原生的端到端模型所不具备的可控性。

这是我的看法。当然，我很想听听大家对这个问题的想法。

<details>
<summary>Original English</summary>

**Varun**: I feel like the easiest way to answer this is you can call into a, you know, really nice voicetovoice demo and you're like, "Wow, it's like listening to me laugh and it's like responding to my tone and it's so snappy. It's so fast." But then, you know, I I tell it that it asked me what day I want to schedule my appointment for, and I say, you know, next week. And it says, "Great. Uh, is that June 10th?" And I'm like, "No, it's the year is 2030." And it's like, you're right. It is 2030. So, let's schedule this for June 10th, 2030. And I'm like, great. Sounds good. Um, and so from that perspective, I am actually very curious, especially on the on the smallest side, um, how that's evolved over time because we are very much keeping our eye on how these speech-to-pech models are performing. Uh but overall I think our current stance is uh the cascading model just allows you to enforce so many more um rigid guard rails and just tight control over the ability to say hey this input is going to go through the same supervisor models to detect for you know prompt injection or social engineering. Then it's going to go down the conveyor belt into intent selection. Then we're going to uh optimize context by checking conditions ahead of time to say, you know, in this complex um process that we're going through with this user, uh maybe this prompt is applicable if they're this type of customer, but this prompt is applicable if they're that type of customer. So let's, you know, figure all this stuff out ahead of time, compact and compile a good system prompt for our message generation model, and get a response back. And then we can take that response and we can check a whole bunch of other things, right? uh we can check is this grounded in truth, right? Is it 2030 or is it 2020 20 whatever year it is 2026 um and then it goes back out over the line, right? And so the obvious constraint to that is how do you make that performant, right? How do you parallelize as many of those steps in the conveyor belt as possible? I think the last six or so months has been uh a really amazing feat from our engineering team at least to find and shave off like 10 milliseconds at a time across every single part of this pipeline to make it feel snappy even though there's a lot of things going on behind the scenes that uh you know you don't necessarily have to do with a speechtoech model. So that's at least my take but yeah I am curious for for the rest of the group's thoughts on this.

</details>

### 异步智能与Hydra

**Sudarshan**: 是的，我想探讨一下为什么人们开始考虑原生的“语音对语音”模型。

最初的想法非常直白：一旦你把语音转成文字，你就丢掉了其中蕴含的情感信息。比如，当用户以一种非常悲伤或兴奋的语气说话时，级联代理只能看到干瘪的文字，它的回复语调也是一成不变的。这是大家开始研究语音对语音的核心原因。

但对于 Smallest AI 而言，我们认为语音对语音的演进不仅如此，它更符合人类大脑原生工作的方式。

以级联模型为例：你必须先做 STT，然后再把文本送给 LLM，等它吐出结果。这是一种**同步架构（Synchronous Architecture）**，即所有事情都是线性、串行发生的。

但人类的大脑是在**倾听的同时进行思考**的。当我在对你说话时，你已经开始在脑海中酝酿你的想法了。如果我说得太长，你可能会打断我；或者你在听的同时，已经在后台进行某些逻辑梳理或记录了。

因此，如果你想让语音代理真正通过图灵测试，达到人脑的自然水准，你就需要一个**能够原生异步运行（Asynchronously）的系统**。它不能只把语音当作一种输入输出格式，而是必须在底层原生接收音频波形，并在进行逻辑思考和工具调用的同时，异步地输出音频流。

这就是我们构建 **Hydra** 模型的初衷。Hydra 是我们研发的原生语音对语音大模型。

当然，在准确性和可解释性方面，新技术总会面临阵痛。当一个新的架构被提出来时，它通常在某一个维度表现得惊艳，但在其他维度上会有所退步。例如，单纯的 STT 模型的文本转录准确率，可能要远高于一个原生端到端语音大模型的内部音频编码器。

因此目前的挑战在于：在让模型变得更自然、更像人类的同时，如何保证其准确率的下限不降低？这很大程度上取决于我们如何提高这些端到端模型的**可解释性（Interpretability）**。你不能让它成为一个完全黑盒的系统，你必须能够定位到它在哪个环节出现了推理偏差。这是我们目前投入大量精力进行研发的核心方向。

另一个限制是，最初出现的那些语音对语音模型（例如 Sesame 等）是非常纯粹的音频输入到音频输出系统。而我们的 Hydra 模型则是**原生多模态（Multimodal）**的：它同时输入语音和文本，并同时输出语音和文本。这意味着它在处理实时语音交互的同时，依然能以并行的方式进行精确的工具调用和文本护栏校验。

我们能看到，在目前的企业级部署中，级联架构的占比依然显著高于纯语音端到端模型。但我坚信，原生的语音对语音一定是行业最终的方向。

当然在过渡期，我的预测是行业会走向一种**混合架构（Hybrid Architecture）**。因为大模型的性能在持续攀升，但在某些极其复杂的业务工作流中，你依然需要配合使用多个模型。比如，你可以让原生的异步语音对语音模型负责与人类进行最实时的声音交互（确保极低的延迟和极致的自然度），而一旦遇到需要查数据库或进行复杂推理的节点，语音大模型就会将任务委派给后端的级联 LLM 链去处理。前台的语音流继续保持呼吸感和沟通状态，而后端的复杂计算异步运行。你可以通过类似“信号量（Semaphores）”或多线程的机制来做控制。

其实这就像人类自己：如果你在半夜被叫醒问一些简单问题，有些事情你完全可以不假思索地脱口而出。我们在日常工作中有 50% 的时间是在“自动驾驶”状态。因此，随着特定行业应用场景的成熟，我们可以训练出一些高度专有化的轻薄模型，来完美应对这 50% 的日常对话。你可以问它：“我们的退换货政策是什么？”它可以用最轻量、最自然的语音模型瞬间回答你。而只有当问题超出常规范围时，它才会调用后台复杂的级联系统去进行深度推理。

<details>
<summary>Original English</summary>

**Sudarshan**: Yeah, I think you brought a question around like cascaded versus speech to speech like let's talk about like why did people start thinking about speech to speech and so the initial idea was simple that hey if you convert speech to text it's going to lose the emotional information right so if you say hey um you might be saying it in a sad way or an excited way the bot is going to answer in the same manner right so that was the obvious reason people started I think uh at some point of time at least at smallest like that has evolved to uh speech to speech is uh a more natural way in which the human brain operates. Uh so for example uh when you do the cascaded thing you do speech to text then you send the prompt to an LLM and then it responds right so we call that a synchronous architecture like it's happening one after the other but our brain is thinking while listening so as I'm speaking to you you're already forming your thoughts and if I'm talking for too long you'll interrupt me right or you might be taking notes in the back end right so you might be essentially doing tool calls while uh I'm speaking to you. And so the whole idea is that if you ever want to pass the Turing test of how the human brain operates, you need something that is working asynchronously and can not just understand emotions but also operate uh like take in speech natively and give out speech natively asynchronously and and so that's how why we have been sort of building Hydra. Now Hydra is our speechtoech model. Um now in terms of accuracy and and interpretability and and all those things I think whenever there is like a new architecture that comes out it's often sort of good in one parameter and then regressed a little bit in other parameters right like so for example um the speechtoext accuracies for a just a speechto text model might be way better than the encoder of a speechtospech model that that you have and so I think The challenge is that while you made progress on the um you know uh making it more natural and operate more humanlike etc etc how could you keep the accuracy bar the same and so I think a lot of that comes down to interpretability of um such models like because you don't want it to be a black box so how can you understand where it is lacking and um so that that's a lot of research that we do and how to make speechtospech models more interpretable. Um the other constraint is I think initially the speechtospech models like I think sesame etc that came in that they were just speech to speech like they literally took in speech and give out speech ours is like multimodel so it takes in speech and text gives out speech and text both so it can do tool call and uh take in text parallelly. So if you want to put guard rails if you want to do all those things that constraint does not go away. Um what we are also seeing is there is still at least in enterprises a lot more cascaded deployments compared to speechtospech model but speech to speech I think will be like an eventual future that that's my opinion. So my take is that when you have like competing things you end up in a hybrid and uh I think the answer for the midterm will be some form of hybrid because the speech to speech are improving. There are parts of the conversation loop where you would say like oh my use case of my workflow is complex. Uh I'm going to use multiple LLMs anyway. So for the active loop like I'm talking to as a human you called me. I'm answering your questions. But whenever I have to do some kind of lookup or something, I delegate to another LLM which will then do the cascade stuff. So the voice in the first part of the loop keeps running. Uh and then you have like interesting kind of semaphors or like you can think of the as threads. uh you want to interrupt the the speech-to-pech model because you realize that this is a complex question and you want to before the speechtospech response you say actually you cannot answer this question right and delegate to the cascade and so on so forth so typically I kind of say there are many use cases where you know if you wake me up in the middle of the night and ask me a bunch of questions there are definitely some class of questions that I can answer without thinking and we all do our jobs in a certain way where we can in autopilot like 50% of our time, right? So as these use cases become emergent and uh you know you're fully deployed with a customer doing high volume, you could essentially train specialized models that fully understand like that 50% use case very well. Uh and you could you could always ask the model like hey what is my return policy and say like in the simplest case this is my return policy and it applies to like 70%. And I know which SKUs or or products it belongs to or it applies to and if you ask me outside of that then I have to like do all the crazy work and if I don't then I answer it right.

</details>

### 极速模型与并行化

**Dayton**: 明白。那在目前的级联管道中，你们主要倾向于使用哪些主流大模型？是 OpenAI GPT 系列，还是 Anthropic 的 Claude Opus 和 Claude Sonnet？你们在构建系统时，是倾向于使用最新发布的旗舰模型，还是会选择像 GPT-4 这种在速度和推理智能之间达到极佳平衡的模型？

<details>
<summary>Original English</summary>

**Dayton**: So on these cascaded pipelines, what what models are you guys using let's say of the frontier models of the you know GPTs of the of the uh what opus and sonnet are you guys using the latest ones or are you using you know like GPT4 because it's like the right balance between speed and intelligence.

</details>

**Sudarshan**: 如果你关闭了模型的显式“深度思考（Thinking）”功能，你其实可以使用任何速度极快的轻量化模型。如果你想保证低延迟，你就不能让模型在响应之前进行冗长的推理。同时，你需要对任务进行并行化拆分。

在轻量极速模型中，我个人目前依然非常喜欢 **Gemini 2.5**。它真的非常快。虽然 Google 后来发布了 3.5 系列（注：此处指 Gemini 3.5 系列），它的推理能力更强但速度会稍慢一些，但 Gemini 2.5 的响应性能真的极其优异。甚至像 Claude Haiku 这样的模型也表现得非常快。虽然它们依然比我们终极预期的速度要慢一点，但已经很实用了。

<details>
<summary>Original English</summary>

**Sudarshan**: If you turn off thinking then you can actually use any of the like if you want a fast model which responds to like the prompt and does not need to think because if you wanted to think you actually start to think about um paralyzing the work because you want the the first model to be super fast. I still like my Gemini 2.5 really well. Like it's so fast. It's like the 3.5 which they launched is like okay it's slower but the 2.5 is so good. Uh even the haiku is really really good. uh they're still slower than what you would expect, but yeah.

</details>

**Dayton**: 那你们是如何对这个管道进行并行化设计的？因为这看起来像是一个强依赖的串行流程：你必须先完整拿到 STT 转换出来的文本，LLM 才能开始处理；而 TTS 也必须等待 LLM 吐出文本后才能开始生成音频。

<details>
<summary>Original English</summary>

**Dayton**: How do you parallelize that? How do you parallelize that pipeline? Because it feels like, oh, well, I do have to first know what text the person said and then the LLM needs the text to do anything. And then you can only generate speech once the text has been generated that you want to wanted to send, right?

</details>

**Sudarshan**: 在底层的工程实现中，你并不是等一句话完全生成完了才开始下一步。以原生语音对语音模型为例，当你在接收音频的同时，你其实可以直接将音频流送入多个分支。一个分支做实时的局部转录，另一个分支则将音频流同时分叉（Fork）给多个并行的轻量 LLM 决策树。

你可以把这想象成一个水流直下的“瀑布”架构。你并不需要等确定了唯一的文本答案才做决定，而是让多个可能的分支并行去跑推理。

<details>
<summary>Original English</summary>

**Sudarshan**: you you just spend the you know you can send the speech like in the speech to speech model case you would send the speech directly to one place fork it into another place run the st there um and if you want multiple models the text output from the first forks into multiple LLMs you can think of it as like a waterfall like you know it comes down

</details>

**Dayton**: 因为你无法提前百分之百预知大模型的最佳输出究竟是什么。

<details>
<summary>Original English</summary>

**Dayton**: because you don't know what the output exactly will be

</details>

**Sudarshan**: 没错。你只需要在“瀑布”的底部放一个**门控路由（Gate）**。你可以应用一些快速校验机制或合并算法。如果底部的多个并行快轨模型达成了共识，你可以直接采用；如果它们产生了冲突，再通过一个稍微重一点的下游模型去判定哪一个分支的回答更好。

如果你喜欢计算机体系结构，你可以在这里做非常多疯狂的并行和投机执行设计。在过去二十年里，单核 CPU 的硬件性能提升缓慢，大家都觉得没事可做；但现在，你可以把二十年前在 CPU 流水线分支预测里玩烂的那些疯狂技术，原封不动地搬到大模型管道的工程优化里来。

<details>
<summary>Original English</summary>

**Sudarshan**: yeah you put a put a gate at the bottom which XR or whatever fancy thing you want to So which says like the if all of them say we are right then you put another LLM downstream which one is better like you can go really crazy if you love computer architecture 20 years we had nothing to do now you can do all this crazy stuff from 20 years ago.

</details>

### 口音、语言与本地化

**Dayton**: 明白。那么在这样的架构下，不同国家用户的口音（Accents）和不同的语种是如何适配的？我想这可能需要 Sudarshan 来聊聊，因为你们正在全力推进原生的端到端语音对语音模型。

<details>
<summary>Original English</summary>

**Dayton**: Yeah. Um so how do like accents and different languages all fit into this? Maybe Sudarian because you guys are building speech to speech. Um

</details>

**Sudarshan**: 好的。在 Smallest AI 的端到端语音大模型中，目前阶段我们选择**百分之百专注于先把英语（English）这一门语言的智能化做到极致**。我们不想在这个阶段引入多语言等其他变量，因为纯语音端到端、异步推理技术本身就已经是非常前沿且充满挑战的了，异步语音交互目前还远没有成为行业的主流方案。

不过，在级联模型这一侧，我们看到了来自全球其他市场的庞大需求。我们在印度拥有非常庞大的业务存在，因此看到了来自印度市场的海量复杂方言需求；同时，我们也收到了大量来自拉美市场的呼声。

相对而言，美国市场依然以英语为主，辅以一定比例的西班牙语，不过口音的种类非常繁杂。在目前的实际技术部署中，只要音质清晰，在理解口音方面我们没有遇到太大的底层技术瓶颈。

我认为真正处于“最后一公里”且依然有待攻克的难题是**极端环境下的噪音消除**。很多用户是在嘈杂的马路边、地铁里或开着车拨打电话的，如何在极差的信噪比下精准还原语音并保持极低的延迟，才是目前的挑战，这与口音本身的关联倒没有那么大。我很想听听其他几位在这个问题上看到了什么。

<details>
<summary>Original English</summary>

**Sudarshan**: yeah so at least for speech to speech right now we are just fully focused on making it more intelligent in English and you know getting it really good in English like we don't want to do any other we don't want to introduce any other variables because the technology in itself is I would say quite frontier asynchronous is not yet like mainstream etc right uh but in terms of like cascaded yeah we've seen like a lot of demand in so we have a lot of presence in India so we see like a lot of demand from India We see a lot of demand from Latin America etc. Um I think US is more like mostly English and then there's some Spanish and then there's a lot of accents to it. Um and I think yeah US at least we have not had any troubles in terms of um technology. I think it's yeah I mean noise cancellation is probably the last mile of problem that is pending uh in terms of handling those things and but yeah that has nothing to do with accents I'm curious what you guys have seen

</details>

**Stephen**: 或许我可以补充几个我们在 Vapi 遇到的跨国部署实际案例。在面对多语言和复杂本地化场景时，级联模型的优势便展现得淋漓尽致，因为级联架构为你提供了足够多的**微调控制杠杆（Levers）**。

例如，我们当时要为一家日本的客户部署语音代理。对于英语、西班牙语或葡萄牙语这些在美国非常常见且技术十分成熟的语种，你直接调用 GPT-4o 或 Deepgram 的转录系统，表现通常非常完美。

但一旦进入日本市场，原先的技术栈就完全不灵了。我们在英语世界觉得最前沿的语音合成系统，其生成的日语非常怪异。级联模型的好处在于，你可以直接把不合适的部分“摘出来”并进行替换。

在 **Vapi**，我们解决这个问题的方案是**支持客户自带（BYO）定制的 TTS 服务器**。比如在日本或中东市场，当地往往会有更懂本地发音习惯的本土创业公司或研究实验室，他们做出来的局部语种模型效果要好得多。

另外，阿拉伯语（Arabic）的合成也极其困难，特别是在涉及到特定地名、人名、当地品牌名称和门牌地址的读音时，通用的大模型很难读准。我们作为一家通用平台，不可能也没必要去为世界上每一个细分市场的特定场景去构建专有模型。因此，级联架构提供的“可插拔式模块替换”机制，在多语言全球化落地中是非常关键的。

<details>
<summary>Original English</summary>

**Stephen**: u maybe I can add uh some examples about that um because on multilingual uh I like to definitely leverage cascade model because there are multiple levers you can pull uh to talk about an example um it's a customer we were deploying uh for Japan Um, so you could typically go uh you know to your uh 4.1 on OpenAI or your deepgram for transcriber and that typically worked well. Now the challenge became on the voice uh piece. So it turns out uh what we thought it was state-of-the-art for um something like English, Spanish, Portuguese um those type of uh that are typical in the US didn't work at all. Um so one of the benefits uh about this is that you can swap. certain pieces that doesn't quite work for you. Um, at least on Vapy, how we solve it is that we let customers bring their uh custom uh text to speech server. Um, so they actually have like there's some startup there's a lab um in there and there's typically uh you will find that in every market. Um, Arabic is also really hard to get it right uh in pronunciation of brands, addresses uh and that really we don't uh cannot build expertise and optimize for every single use case. So that's one of the reasons why I like that as well.

</details>

**Dayton**: 明白了。另外我有一个关于 Sesame 模型的题外话。他们当时发布时放出了一个非常惊艳的官方 Demo，但从那之后我就再也没听到过他们的任何动静了。你们知道他们后来发生了什么，目前进展如何吗？

<details>
<summary>Original English</summary>

**Dayton**: Cool. Um, also actually question on the like sesame model. Yeah, like they came out with this like really insane like demo and then I've never heard of them since like what do you guys know like what happened and what's going on?

</details>

**Stephen**: 好的。根据我所了解的情况，他们目前主要将精力转向了硬件（Hardware）领域。他们正在尝试将他们的语音大模型嵌入到某种硬件载体中，不确定是智能眼镜还是其他可穿戴设备。我认识的几个后来入职那里的员工，基本都拥有非常深厚的硬件与声学背景。

<details>
<summary>Original English</summary>

**Stephen**: Yeah, I think uh so they are building hardware is what I understand like they are putting uh those the voice into some sort of a hardware. I'm not sure if it's glasses or what are they working on exactly but uh I know a few people who got hired there and they're all sort of focused on the hardware and voice sort of backgrounds.

</details>

**Dayton**: 哈哈，我得到的内部八卦是他们的 CEO 之前已经赚够了钱，所以他现在做这个项目纯粹是为了兴趣玩票。因此，他确实可以随心所欲做任何他想探索的事情。

<details>
<summary>Original English</summary>

**Dayton**: Yeah, the answer I got was that the CEO had already made a ton of money and he just really wants to play around basically. So I guess he can do whatever he wants. Um, cool. Um,

</details>

### 提示词 vs. 工作流

**Dayton**: 回到技术架构上。在目前的级联管道中，行业标准的最佳实践是直接给 LLM 一个极其庞大的“超级系统提示词（Giant System Prompt）”，把所有的业务规则都塞进去；还是倾向于使用基于节点的工作流（Workflow / Graph Approach）来引导对话？你们怎么看？

<details>
<summary>Original English</summary>

**Dayton**: so is it standard practice for in this like cascaded pipeline for you to just give just have one giant like system prompt that you're giving the LLM on these are all the rules for how you should be responding? um or is it more of a um like a workflow approach? How do you guys think about that? What's the standard best practice right now?

</details>

**Stephen**: 我认为这高度取决于具体的业务场景，以及你的提示词体积。

我在这里的实战观点可能与 Varun 稍微有些不同。在**呼入（Inbound）**场景中，客户拨打进来的电话线通常都是高度专线专用的，你其实可以非常精准地预测并规划对话的走向。因此在呼入场景下，采用**基于节点（Node-based）或状态图（Graph Builder）**的流程引导架构会非常稳定可靠。

但是，在**呼出（Outbound）**场景中，你虽然有一个明确的通话目的（比如通知账单逾期），但你永远无法预知电话那头接起电话的人会给出什么反应。他们可能会感到非常受挫、愤怒、困惑，或者纯粹表现得极其烦躁不安。当人处于这种情绪失控的无序状态时，基于刚性节点的工作流会瞬间死机。

因此在呼出场景下，使用**包含所有决策上下文的单一庞大提示词（All-in-one Prompt）**反而更有效。这让大模型扮演了一个拥有自主应对能力的“中央大脑”。它能够根据用户天马行空、情绪化的回答，从庞大的提示词规则库中动态提取出那些没被写在固定工作流里、但能有效安抚用户并把话题拉回正轨的底层逻辑。

此外，你还得考虑企业**知识库（Knowledge Base）**的检索和消耗成本。在结构化的呼入流程中，你可以清晰定义在第 3 步时才去调用特定的 FAQ API，不需要每一轮都把几万字的文档塞入上下文。而在充满变数的呼出交互中，你必须赋予模型随时检索海量信息的能力。你会更依赖向量余弦相似度（Cosine Similarity）检索，确保它能针对任何突发提问给出准确答复。

从技术演进来看，大模型在过去很长一段时间里的核心痛点就是“丢三落四”——面对几万字的业务文档，它们只看开头和结尾，中间的所有规则全被遗忘。比如，如果用户处于业务流程的中期，模型往往会忘记自己已经执行了哪些操作，导致胡言乱语。

为了解决这个问题，我们在我们的执行引擎中做了一套**情境化动态提示词机制（Situational Prompting）**。我们会在后台实时监测对话状态，并在将提示词输入给 LLM 之前，动态过滤并只包含与当前对话阶段强相关的几条核心规则，把无关的规则全部剃掉。

这套机制在七个月前大模型推理能力还很弱的时候非常有效。但随着大模型能力的飞速演进，我们发现，系统去动态判断“哪些规则相关、哪些不相关”的决策准确率，有时候甚至还不如直接把整个庞大的提示词全部丢给最新一代大模型。

因此，最近的技术路线又开始向另一端摆动——**直接把所有上下文和规则一股脑塞给大模型，相信并依赖模型本身的推理能力去自动理清头绪**。

但归根结底，在面对非确定性系统（Non-deterministic Systems）时，没有任何一条放之四海而皆准的铁律。每个客户的场景都是一客一案（Customer by Customer）。最切实可行的方案依然是：老老实实把系统构建出来，进行海量的自动化回归测试，然后使用一个足够聪明的大模型作为裁判（LLM-as-a-Judge）来给出评估指标：它运行得足够稳定吗？如果发生偏移，我们是否需要引入前置数据处理或更精细的上下文优化？

所以，唯一的标准答案就是：不断地测试、发现问题、调整、然后再测试。这个循环会一直持续下去。虽然现在的旗舰模型可以装下海量提示词并自行理解，但这无疑会显著增加首次响应延迟（First-Token Latency）。这在语音交互中是极具杀伤力的。

<details>
<summary>Original English</summary>

**Stephen**: So I think it highly depends upon the use case and also the size of your prompt, right? So I think I have a counter approach to Baroon in in terms of that like usually in inbound I find you know you you're usually having dedicated lines and you know specifically where the workflows are going to go right and so in these cases if you know a little bit more about and you can predict where the conversation's going to go then you can have a more of a node or graph builder kind of approach but if you don't know what's going to happen typically I think in outbound yes there is a dedicated like message but what the caller says back you never know because they could just be frustrated they could be angry or they could be I don't know like annoyed and in that case when they're erratic when a person's erratic you never know so having it in a way that is like all in one one prompt allows you to have an more like a central brain in terms of I can pick up components from my prompt that may not have been in a dedicated flow but actually can be utilized iz to enhance the response. And then on top of that, you have to think of your knowledge base and knowledge the things at your at your expense, right? Like in a inbound flow, maybe you know exactly when you need to pull a specific part of your knowledge. So you don't need to extract every single piece of context, right? Whether it's your websites and documents, but sometimes in outbound, you should utilize all that information to get a better response. then you will rely more on cosign similarity and stuff to make sure that hopefully your retrieval is good enough to respond to them. I think from my perspective um the limiting factor has been and and will continue to be although it's getting a lot better over time just uh to you know some of the earlier points made uh the ability for these uh frontier LLMs to be able to take a massive wall of text and not just read the first three lines and the last three lines but actually be able to properly uh reason and like localize themselves into you know we are halfway through this procedure and these things have already happened and these things haven't happened yet and these things are true and these things are false about this situation and so therefore like this is the one thing that I should be really zooming in on right now right um so from our perspective I think um we kind of take an approach that depends on the customer um but we do within our execution engine have the ability to um make some of these rules or prompts or guidelines more situational so that we can you know check if these are uh relevant right now before we even uh include include them or or uh uh don't include them in the system prompt. And so that was our solution that was especially relevant, you know, like 7 months ago when the LLMs really were just like consistently skipping step 4 A1. Um but we have found over time now that uh sometimes the reliability of deciding when these things are relevant or not is actually worse than just giving all of it to the model because the models have improved a lot since that time. And so now we're going back, I think, swinging a little bit back towards just give the model everything and more or less it will figure it out. Um, but at the end of the day, you know, with nondeterministic systems, it really just ends up being customer by customer. uh we have to really understand their use cases and at the end of the day just build it and then test it a whole bunch of times and then use LLM as a judge to tell us you know did it work was it reliable or do we need to add a little bit more um pre-processing and and context optimization ahead of time in order to make it reliable. So the the real answer is most likely always just test and find out and then test again and then find out again and you know it goes on forever. I'm assuming that yeah maybe the models are able to handle those edge cases now like just in a giant prompt but that probably also increases latency.

</details>

### 延迟、填充词与评估

**Dayton**: 这引出了一个非常核心的问题：目前一个优秀的语音代理，其理想的端到端延迟（Latency）标准是多少？另外，就像你刚才提到的，虽然现在的模型越来越聪明，但也需要消耗更多的时间去推理。对于终端用户来说，这会不会反而导致体验的退步？

<details>
<summary>Original English</summary>

**Dayton**: So first could you talk about like what is a good latency look like for a voice agent and is that even true that yeah the models are getting better but they also require more time and so for the end user that's actually a bad thing.

</details>

**Stephen**: 这是一个非常好的问题。行业内关于延迟基准测试（Latency Benchmarks）的合格线在过去一年里发生了翻天覆地的变化，客户对我们的期望值也变得越来越高。

但我想分享一个非常有意思的实战发现：虽然我们本能地讨厌无意义的“填充词（Fillers，如 ‘呃’、‘嗯’、‘那个’ 等）”，但在人与人之间的日常真实对话中，我们在思考时也常常会下意识地使用填充词。

我们发现，当我们在对话中刻意追求绝对的零延迟和零填充词时，机器人的回复会显得极其生硬和不自然（那种非人般的冰冷感）。反之，在适当的节点合理引入填充词，体验反而会更好。

当我们在后台因为调用了庞大的提示词，或者在等待客户数据库 API 响应导致延迟不可避免地拉长到 5 秒时，让语音代理非常自然地说一句：“呃，请稍等一下，我正在帮您查询……好的，查到了。”这在人机交互中是完全可以接受的。

因此，难点并不在于延迟必须是零，而是在于你如何设计大模型的执行引擎，让它在感应到延迟发生的瞬间，能够极其自然、不露痕迹地吐出这些填充音频。我们在这一块投入了极大的精力。我们希望做到的是：在技术上我们拥有极致低延迟、不需要任何填充词的运行能力；而一旦在某些网络或业务延迟发生的瞬间，系统能完美兜底。

不过，关于延迟与稳定性的博弈，依然是目前语音 AI 部署中最难攻克的工程难关。

<details>
<summary>Original English</summary>

**Stephen**: Yeah that is a really good question. I mean I I think the definition of what like benchmarking latency stats look like that are good have uh changed a lot and um expectations are you know getting better and better and better from our customers. Overall, I think it it is also important to mention that um as much as fillers and contextual fillers is something that uh we don't like to hear just as a noun, um it is normal for in normal conversation for humans to say a few words while they're thinking. And so we've actually found that when we have zero contextual fillers, sometimes it actually feels more rigid than when we don't. And so we tend to find that uh having the the right amount of fillers that um kick in when you know we are experiencing some sort of latency because of some very large prompt or some very complex thing that the model is thinking through uh most commonly you know running a tool call where our customer's API becomes the bottleneck and we're waiting you know 5 seconds for something to come back. Um being able to say hey just give me a sec uh looking at that. Okay, cool. Here's here's your answer, right? There's actually nothing wrong with that. Uh when we've when we've tested with our customers, um obviously the the limiting factor in that case then becomes how good are your fillers and how natural do they sound. Um and so that's been a place where we've invested a lot of time as well to say how do we create an execution engine where we really don't need fillers, but in those moments where we do, they're really good. Um, so that's at least my take, but again, I know folks have probably a lot of opinions here about latency and and how to find that trade-off because in my opinion, I honestly think that that's the hardest problem to solve in voice deployments is just that trade-off that's always going to be there of like performance versus um stability and reliability in in general. So,

</details>

**Varun**: 没错，我完全同意。在 Vapi 的实战中，我们对抗延迟和提示词冗余的另一个核心策略是**任务卸载（Offloading）**。

你不应该把所有的业务流全部塞进主提示词中。你可以将业务切碎。我们允许企业在特定的对话阶段，将任务路由给更专注的**子智能体（Specialized Agent）**。

以催收场景为例，大模型在某些步骤需要引导用户念出信用卡信息进行支付。但并不是所有的通话都会走到这一步（很多人在听到要付钱时就挂了，或者他们早就绑定了免密支付）。因此，你没必要把“如何校验信用卡格式、如何纠错”的几十行规则从通话第一秒起就常驻在主提示词里。你可以引入**多代理架构（Multi-agent Architecture）**。当确定用户要付款的瞬间，主代理瞬间将控制权移交给一个只带了“信用卡收集规则”的轻量化子代理。一旦它完成了任务，再把控制权和数据交还给负责宏观对话的主代理。这能极大降低单次交互的 Token 消耗、降低延迟并缩减成本。

另外，我们最近一直在尝试的一个非常有前景的研发方向是**分流流式推理（Waterfall Streaming）**。

当用户说完话后，我们不仅将音频送给主 LLM，同时也在后台并行将转录文本流式输入给一个极度轻量化的小语言模型（SLM，如微调过的分类器）。这个小模型能在几毫秒内推断出用户的核心意图。如果小模型判定用户的意图非常简单，它就可以在后台大模型还在慢吞吞进行逻辑思考的同时，直接指挥前端播放器先播放一个语气词或填充语，确保交互的连贯性。这种多轨并行的设计是我们目前持续投入研究的地方。

<details>
<summary>Original English</summary>

**Varun**: um, yeah, I agree with all of that. Some of the ways that we think about it in Vapy, uh, is offloading, uh, some of that instruction. So break it down. Uh sometimes you don't really need um that you know 10 15 step workflow in the in the prompt. Uh one example I can talk about is um this uh collections uh use case. Um we do allow users to capture um businesses to capture credit card information. Uh but not every call is uh about that. Some people already have a payment method maybe added or that. So uh one way of doing that offloading into a uh specialized agent uh so we can start thinking about multi-agents and there are many architecture and patterns in there um is to constrain the uh instructions that you give it to to that particular moment of the conversation and once that achieves its goal it can go back to that u more free form approach which has loaded like uh your longer uh context. Something we're also been uh experimenting lately um and it's more about the guar space is um to uh your point where you can have uh think about it as a waterfall you can actually stream to multiple places. So what if you have uh streaming down to a a small language model which can uh do inference in a very little time. So think about classifiers to maybe collect the intent um while the pipeline is still maybe adding a filler word as well to keep a consistent experience but uh kicking off a background process that is still intelligent still um thinking. So those are still things that we'd like to invest a lot more research on. Um so yeah constantly investing on that.

</details>

**Sudarshan**: 当然，在讨论延迟与提示词大小的博弈时，我们绝对不能忽略另一个极其现实的因素：**成本（Cost）**。

在实际的商业呼叫中，大量用户在拨通电话的前 10 到 15 秒内就会直接挂断。如果你的系统每次一接通就必须把长达几万 token 的背景上下文和复杂提示词输入给 GPT-4，你必须为这部分瞬间流失的用户支付极其昂贵的前置输入 Token 费用。这在财务上是不可承受的。

因此，像 Stephen 提到的“拆分提示词与动态按需加载”，不仅是在压榨延迟，更是保护企业钱包的黄金法则。

最后我想聊聊**基准评估（Evaluations / Evals）**。在 Smallest AI，我们会定期发布关于实时语音交互各个环节的开源基准测试——包括转轮 VAD 测试、LLM 推理速度测试以及 TTS 逼真度测试。我们坚信，在当前这个模型迭代日新月异的时代，拥有科学、规范的评估体系是至关重要的。

今天 NVIDIA 发布了他们的 Neumatron 3.5 模型（注：此处原文应为 Nemotron 3.5），其中已经包含了非常优秀的语音识别基准数据。我们把我们的整个测试框架和评估用例完全开源了。无论行业里发布了什么样的新模型，你都可以在自己的本地基础设施上，直接拉取我们的开源评估用例去跑分，对比它在你们专有的业务流里表现究竟如何。这比只看厂商官方给出的 PPT 跑分图要靠谱得多。

对于前线部署工程师（FDE）来说，你完全可以在项目上线前，利用已有的部分客户脱敏交互历史数据，在后台跑一套模拟冒烟测试（Smoke Test），用它来校准新模型在你们特定业务流下的表现。

在 Smallest AI，除了纯粹的模型研发外，我们也提供一站式的模型编排与协同平台。我们看到很多企业客户，目前正在将我们的原生的语音模型与我们研发的极速小语言模型（SLM）——**Electron** 进行绑定微调（Fine-tuning）。微调后的 Electron 在特定客服场景下，其推理延迟和成本表现要远优于 GPT-4o 这样的通用大模型，且完全打消了因为 OpenAI 服务偶发性延迟抖动而导致通话体验崩塌的隐患。当你有能力私有化部署这些轻量级模型时，你对整个服务体验的掌控力才是百分之百的。这是我们目前在行业中看到的最明显的趋势。

<details>
<summary>Original English</summary>

**Sudarshan**: Sure. I think of one thing that we haven't also factored in in terms of the latency uh tradeoff is cost right now that you're putting such a big large prompt into your your LLM. You have to think about those calls where many people just hang up and predominantly calls just hang up 10 seconds into the call. Right now you're having to pay for all those tokens to just get inputed in. So that like Stephen mentioned splitting out your prompt, you are also playing to that strength of lower latency and lower cost. I'll speak just to the benchmarks. So we publish u turnbased ST benchmarks, LLM benchmarks and TDS benchmarks. The whole point of that is that as I think today Neumatron 3.5 launched and there's already an ASR um benchmark out did very well the Nvidia one. So um the idea there is that all our tooling is open source. So with the HTT benchmarks, the TDS benchmarks and the LLM benchmarks all the turns are actually open. So you can run it against any new model that comes out. Uh you can look run it locally. you can look at the outputs from from our graphs and compare that to what you're getting on your infrastructure if you're self-hosting or you know elsewhere. Um so that's one important aspect to like uh consider if you know what your turns will look like you can just update or you know just download our benchmarks update the turns and see how that like goes for your own flows. Uh usually for the LLM stuff, it's really useful because you can throw out the ST and the TTS and just run the LLM inference loops to like check against uh a customer. So yeah, I think eval are really important. Um, and if you have like a like while talking to customers, if you can evaluate like what type of conversations or like what type of workflow they're going to have, like those are real direct inputs into like what you can directly start testing even though you're not live with them or even they've not shown any intent. Uh, so I think that's where like the sees and the forward deployed engineers can actually come to for like you we all have cloud running in the background, right? So you can just say here's what we had a discussion like can you build an eval like based on our eval suit like can you like just run a smoke test with the conversation information that we already have and that helps a lot I think. Yeah, just just adding to that like we are seeing so we while we focus on models we also have all the model sort of orchestrated on our platform. So you could build a voice agent on smallest. Um we are seeing a lot of customers who just pair our models with our own like small language model. It's called electron. fine-tune one of those to make it work for realtime voice use cases and see a lot of folks using that with better knowledge basis memory etc over GB 40 4.1 you know the popular realtime models um just a from a cost perspective it's lower b from latency perspective it's like way lower u and then just more reliable I think I'm not sure if everyone faces this but like um open AI APIs spike and in um you have no control on those latencies. Um with if you sort of have a self-hosted model um you could scale up scale down based on your requirement. So that's one thing we are seeing a lot with our customers.

</details>