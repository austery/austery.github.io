---
author: AI Engineer
date: '2026-05-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0jeZfjJMfmo
speaker: AI Engineer
tags:
  - open-source-robotics
  - voice-ai
  - speech-to-speech
  - model-optimization
title: Reachy Mini：打破高昂壁垒，重构开源机器人的语音交互范式
summary: Hugging Face 的 Andres 探讨了当前机器人领域高昂的成本壁垒，并推出了仅售300美元的开源机器人 Reachy Mini。该项目结合了成熟的开源语音AI与端到端架构优化（如深度加速Coqui TTS），旨在将机器人开发权交还给开发者、学生与创客，探索非拟人化的全新交互可能。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Hugging Face
  - Waymo
  - Mistral
products_models:
  - Reachy Mini
  - Coqui TTS
  - Parakeet
  - Raspberry Pi
media_books: []
status: evergreen
---
### 机器人技术的现状与昂贵的壁垒

当前，我们在机器人技术上正在取得巨大进展。虽然在日常生活中可能还不明显，但机器人正在以惊人的速度进入我们的视野。如今我们拥有了非常优秀的**人形机器人**（Humanoid robots），甚至已经能看到它们在机器人俱乐部里进行拳击比赛。同时，也有几家公司试图向你推销家用机器人来浇花或是漫无目的地刷 TikTok；当然，还有像 **Waymo** 这样的自动驾驶汽车。

然而，在这些进步背后，我看到了几个明显的问题。首先，这些设备都极其昂贵。人形机器人的起步价至少在五位数中段（5万美元以上），而且价格似乎并没有下降的趋势。Waymo 的成本更是高达六位数。其次，它们往往被设计成模仿现实中的人类。这不是生物学问题，而是硬件限制。如果我们把人形机器人设计成蜘蛛的形状，它可能会移动得更快、更敏捷、更稳定。但我们执意要让它像人，只是为了让我们觉得“哦，这是个机器人，它像人，所以我懂它能干嘛”。我认为这是一个错误。而且，它们通常看起来并不太友好。

总结来说，目前的机器人技术虽然取得了长足进步，但原型开发的成本太高，很难让全世界的高中订购十台 5 万美元的机器人供学生把玩；它们适配起来非常复杂，主要面向企业，且很难让人与之产生真正的情感连接。

<details>
<summary>Original English Source</summary>
So, first, very quickly, the state of robotics. Um we are actually making strides in robotics. I think for the day-to-day life, it's not very clear, but robots are just coming and they're coming at neck-breaking speed. We have really, really good humanoids nowadays. Um a couple of weekends ago, I was at the robotics club in Zurich, Switzerland, and we had a little boxing match between humanoid robots. Uh it was incredi- incredible and a little bit disturbing. Um there are also several companies today trying to sell you robots to put in your homes to do things like water your plants and scroll Tik Tok aimlessly. Um and of course, we have self-driving cars. I think Waymo is now in London, I heard. I haven't seen them, but pretty cool.

Um now, something here that I always see with these strides that we're making with robotics is A, these things are really, really expensive. They're all at least in mid five-figure range, so 50K up. Um and they don't seem to really be coming down. They seem to be targeting that price range for now. Um That's to say the humanoids. The Waymo, I think they're like six figures mid. Uh and they also they kind of look like something that you know. So, it's not very much about being creative. It's very much about trying to imitate reality. And this is not biology. This is really hardware, and we're really constraining the robots to do this. Uh if you take a humanoid robot, it could look like a spider uh and just move around way faster, be more agile, be more stable, but we're actually making it be a humanoid such we look at it and we think like, "Oh, yeah, robot, human, it's the same sort of. Like, I understand what it can do."

Uh that to me is a mistake. They also don't look very friendly in general. Uh so, I see a few problems with the current state of robotics. All of these robots, which they are making strides and they're becoming really, really good, they're still too expensive to prototype. I don't see any high school anywhere in the world ordering 10 of these 50K humanoid robots to let their students play with. Um they're very complex to adapt. They're really like targeting companies. And they You cannot really connect with them.
</details>

### 语音AI的成熟与交互范式的重构

为了打破这种局面，我们需要思考新的交互方式。正如你所见，如今我们已经可以构建非常出色的**语音代理**（Voice agents）。语音 AI 的发展已经相当成熟，市面上有很多优秀的商业解决方案，比如巴黎的 Rhodium，以及大家可能都玩过的 GPT 实时语音（GPT real time），你可以和它自然流畅地对话。还有虽然有一些问题但普及率极高的 Siri。

在开源领域，我们同样拥有大量优秀的模型。比如 **Mistral** 的模型，出色的开源模型 Box Rally，还有仅 8000 万参数的微型模型 Cocoro。我们有很好的语音理解模型，以及像 **Hugging Face** 提供的语音到语音（speech-to-speech）管道（Pipeline），让你可以将所有组件拼凑起来，自己动手制作语音代理。

可见，语音 AI 的工具已经就绪，无论是在商业端还是开源界。但仍然没有人真正致力于解决“我们该如何与这些机器人对话”的问题。我们在思考：既然机器人时代即将来临，我们该如何将这项技术交到每个人手中？我们希望未来的体验不被单一公司或少数群体垄断，而是像早期计算机那样，以一种更具“极客”（hacker）精神的方式被创造出来。

<details>
<summary>Original English Source</summary>
Now, as you saw today already, you we can actually build pretty good voice agents. The state of voice AI is quite advanced. There are really good commercial solutions. There's um Rhodium in Paris developing voice agents. There's GPT real time, which I'm sure most of you have played with. Uh you can chat with it and it will reply, and it sounds fairly natural. There's Siri, which has its problems, but it's in all iPhones. Hey, kudos. 

Uh and in the open source, we also have a lot of really good models. Uh you heard the talk from Mistral maybe if you were here before. Box Rally is a really good open source model. We also have tiny models like Cocoro at just 80 million parameters, a tongue good. We have good models to understand speech, and we have good pipelines like speech-to-speech from Hugging Face to put all together and make your voice agents yourself.

So, what I see here is that voice AI is quite mature. We have the tools. We have the tools commercially. We have the tools in the open source, but still, no one is really working on how we're going to talk with these robots. And we are thinking, "Okay, given that robots are coming, how can we manage to put this in the hands of everyone such that it's the experience of the future is not dominated by one company or one group of people, but really it's made like computers were made in a bit more of a hacker fashion."
</details>

### Reachy Mini：开源、可修复与极客友好的探索

基于上述理念，我们开发了 **Reachy Mini**——这正是我们对现状的回应。它的目标受众是极客、研究员、学生和梦想家。如果你有一台电脑，你就应该能玩转它并创造出属于你的东西。

我们的愿景是打造一个富有表现力的机器人，你可以和它对话，但它**不长得像人类**。这对我们来说非常重要，因为这会在创意思维上把你带入一个全新的空间。你会开始开发与它互动的新方式，而不是仅仅把它当作“人类的替代品”。我们希望人们能自由探索这种全新的事物。

我们让它变得负担得起（仅售300至450美元），且容易使用。更重要的是，我们让它**可修复**。实际上，我们发货时它是未组装的。你拿到它的第一件事就是自己动手组装它。一旦你完成了这一步（我们收到了非常积极的用户反馈），你就拥有了相关的知识和工具，以后机器人坏了任何零件，你只需订购配件并自己更换即可。它极具可塑性（hackable），你可以用 3D 打印为它制作新部件，比如加上万圣节南瓜装饰。它很可爱，而且我们提供了一整套软件工具供你开发。

<details>
<summary>Original English Source</summary>
And that's how we came up with Richie Mini. It's a little bit our response to that. We had We made it targeting really hackers, researchers, students, dreamers. If you have a computer, you should be able to play with it and make things. That's a little bit our target. 

Um a little bit of our vision. The idea is that it's an expressive robot that you can talk to it, but it doesn't look like a human. And that for us is very important because it already puts your mind in a different place creative-wise that you are going to start developing new ways of interacting with this, and it's not going to be just, "Okay, this is a human replacement." It's not. It's a new thing. 

Uh and we want people to be able to explore that. Uh we made it affordable. We made it easy to use. Well, we're making it easier to use. We made it repairable. Actually, we ship these robots unassembled. So, the first thing you do when you get the robot is you need to assemble it yourself. And once you're done with it, which we get super positive feedback from, you can basically repair anything that's going to break in the robot ever. You have all of the knowledge. You have all of the tools. Um it really just is ordering the the parts and changing it. 

It's very hackable. It's very cute. That's maybe a personal opinion, but I think it's cute. And we are trying to give you a set of software tools uh for you to develop with. Uh now, very quickly, we sell two of these robots. Uh they are both uh 450 and 300 USD. And the difference between both of them is the 450, which is this one that I have here, has a Raspberry Pi inside, and it has a battery. And that's it. Basically, if you don't need a battery, you don't need a Raspberry Pi, you can order the cheaper one. Uh we are selling those cheaper ones in bulk for high schools or universities to play with, to experiment to experiment, to hack with.

Um I here I wanted to show you a few um cool developments that we are seeing. For example, in the middle, what I mean with hackable, people can 3D print new parts for the robot. And in this case, they didn't need to really change anything. They're just taking the antennas out, putting a different type of antenna. They are putting something on top of the body. They are putting some lights, and they have suddenly a little Halloween pumpkin for to play with. Um on the right, something that we hadn't thought about, someone figured, "Oh, you can just pet the robot, and it can be fun, and it reacts." Does it purr? Um you can make it purr. Uh so, that's that's a little bit like for us, it's more about people exploring and people developing their own intuition for how this should be, and I'm making it their own.
</details>

### 语音代理的系统架构与大语言模型集成

我们坚信，与机器人交流的主要方式将是通过语音。我无法想象有人会走到人形机器人面前，掏出键盘敲字。因此，我们必须为人们提供开发语音体验的工具。

Reachy Mini 背后运行着一套完全开源的系统软件。由于我们深知开发者可能算力拮据（GPU poor），我们通过架构优化来解决服务压力。系统分为三个层级：

中间层是我们维护了两年的**语音到语音管道**（speech-to-speech pipeline）。它包含一个语音活动检测（VAD）系统，用来判断你是否在说话；随后将音频送入语音转文本（STT）系统——这里我们使用了极速的 **Parakeet** 模型，每150毫秒转录一次并传回部分结果，让机器人能对有趣的信息做出即时反应；转录完成后，数据交给大语言模型（LLM）。LLM不仅能回复对话，还能进行工具调用（Tool calling）以控制机器人移动或使用摄像头；最后，文本被送到文本到语音（TTS）系统，我们目前使用的是 **Coqui TTS**。

在更高层，机器人本体上运行着对话应用程序。它负责处理麦克风和扬声器的输入输出，执行回声消除（Echo cancellation）以避免机器人说话时听到自己的声音，并分发动作或表情的工具指令（如进行人脸追踪）。在云端基础设施层面，我们将该管道部署在 Hugging Face 推理端点上，使用负载均衡器动态管理计算节点。我们特意将 **LLM（如 Coqui 3.5 27B）** 的推理端点**剥离**出来独立扩展，因为不同用户的对话频次差异巨大，分离部署能极大地节省计算资源。

<details>
<summary>Original English Source</summary>
But I was talking to you about voice AI. We think one of the main ways to talking with robots is going to be through voice. I don't see anyone going to a humanoid robot and taking out the keyboard and typing something that that's not going to be what happens. Uh so, we need to give people the tools to develop voice uh experiences. Uh and we are doing that. We have a piece of software to you for you to to converse with the robot. 

...

And what we're trying to do is we're trying to give people the tools to actually do the conversation. So, everything that we are doing with the robot is open source. All of these models are open source. The agents are open source. Uh but we understand also that people are a little bit GPU poor maybe and they cannot run all of those models locally. We are also a little bit GPU poor and we have now shipped 7,500 of these robots, which means we have a pretty sizable fleet of people talking to the robot. It is our most used app by far. People just like putting it there and talking to it. 

Uh and because you guys are a very technical audience, I wanted to show you a little bit how we're actually serving this. Uh there are three levels to the system. In the middle, there's the speech-to-speech pipeline. That's a project that I've been maintaining with Hugging Face for the last 2 years. Uh the Mistral Some from Mistral told you a little bit how it works. You have a voice activity detection system that knows if you're talking on or not. That sends it to a speech-to-text system. In our case, we are using Parakeet because it's super fast. So, we transcribe every 150 milliseconds and we send back the partial transcriptions for the robot to react if it hears something interesting. And when the transcription is is done, we send it to an LLM. The LLM replies, can also do tool calling for movements or use the camera. And then we send it to the text-to-speech system, which we're using Coqui TTS.

Now, on the higher level, we have the actual conversation app running in the robot. That is taking the input and the output from input from microphone and output through the speakers. It's doing the echo cancellation to not hear itself when it's talking and to try to hear you. It's doing the tool dispatching to move, do emotions, and it's using the camera. It can do face tracking to follow you around. Um that sort of thing. 

And then the speech-to-speech pipeline, if you don't want to tweak it and use your own, we have it deployed in Hugging Face inference endpoints. We have a load balancer that determines how many compute nodes we have at at each time depending on how many robots are connected. And we have separated the LLM inference endpoints. We're actually using now Coqui 3.5 27B cuz we managed to make it fast enough. Um but we scale that differently because each of the conversation nodes can have an amount of concurrent users without the latency spiking up too much. And it changes a lot if in one node you have eight users that are talking a lot and using a lot the LLM. And in another node you have eight users that are not talking at all. Uh so, it really helps to save on resources if you have the LLM separated.
</details>

### 优化开源TTS模型的实战与极限加速

为了让开源模型真正适用于实时语音代理，我们必须深入底层进行优化。以 **Coqui 3 TTS** 为例，这是一个几个月前刚发布、质量极佳的开源模型。但问题在于，虽然论文宣称其延迟很低，实际开源的模型速度却远未达到语音代理的要求。我花了大概两周时间深度改造它。

首先面临的问题是**流式处理**（Streaming）。原模型需要生成完整的音频片段后才返回结果——如果你需要10秒的音频，它必须先花时间把这10秒全部生成出来。我们通过实现流式传输解决了这个问题，这在实践中往往比理论上要困难得多。

其次是更底层的系统瓶颈：该模型作为一个自回归模型（Autoregressive model），为生成每一个音频包需要执行 500 个计算步骤。在每一步中，它都需要在 CPU 和 GPU 之间来回同步数据。这种频繁的通信开销是致命的。为了解决这个问题，我们需要对模型进行编译，使所有的交互直接在 GPU 内部完成。然而，由于原模型使用了**动态 KV Cache**（会随输入大小变化），这在默认情况下是无法实现的。我们将它强行改为**静态 KV Cache**——虽然这会在一开始占用更多的内存（RAM），但它让速度大幅提升。

在此基础上，我们引入了 **CUDA Graph Captures** 技术，捕获整个模型的执行图，从而大幅加速了生成过程。最终的结果令人振奋：我们将模型的生成速度从“低于实时”（生成1秒音频耗时1.2秒）提升到了“近6倍实时”（生成1秒音频仅需不到200毫秒）。我们把“首次音频响应时间”（Time to first audio）从原本的几秒钟，硬生生压缩到了几百毫秒级别。目前这个被极大加速的 Coqui 3 TTS 模型版本同样已经开源，开发者可以直接部署并享受流畅的语音交互。

<details>
<summary>Original English Source</summary>
Um and to show you a little bit of how far we're going into trying to make this work and also benefiting from the fact that you are a technical audience, I'm going to talk a little bit about Coqui 3 TTS.

So, this is a model from Coqui that came out two or three months ago. For us, it was really uh a really great moment because TTS models hadn't been as good in the open source and as fast as Coqui 3 TTS when it came out. And we were really expecting for something like that. We knew it was coming, but we didn't know when it was going to come. Uh the issue is that the model that they released actually ended up being of the quality that they showed you, but not really of the speed that they showed you. Uh the paper claimed very low latencies, but the model didn't really achieve them. So, I spent maybe 2 weeks with Coqui TTS trying to get the model trained by them to actually be fast enough for voice agents.

Um and I wanted to show you a little bit a little bit how I did that and what the main issues were. Uh first issue that I found is that the model would generate the whole output before giving it to you. So, it wasn't streaming. Uh which meant if you wanted 10 seconds of audio, it needed to generate the 10 seconds. That can be solved with streaming. Uh it's harder in practice than in theory as things usually are, but when it works, it works and it's really cool.

The next thing that I noticed was the model being an autoregressive model was doing 500 steps for each packet of audio that it was generating. And for each of those 500 steps, it needs to coordinate the CPU with the GPU. So, it needs to send data back and forth between the CPU and the GPU. That is pretty bad. The way to solve that is to compile your model so that all of those interactions happen directly in the GPU. That couldn't happen by default because it was using a dynamic KV cache. So, the KV cache was evolving depending with the size of the inputs that it was processing. We changed that for a static KV cache. We used more RAM from the get-go, but that makes it faster. And then we could use CUDA graph captures to capture the whole model and to be able to accelerate generation significantly. Uh we went on a real-time factor from being below real time, so at 0.8, which means you generate 1 second, you take 1.2 seconds, uh to being 5.8, which means for 1 second, you take 20 seconds, I guess. Uh no, for 1 second, you take 200 milliseconds. Yes.
</details>