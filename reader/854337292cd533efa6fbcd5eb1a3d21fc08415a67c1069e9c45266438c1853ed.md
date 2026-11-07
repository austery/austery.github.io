---
author: The MAD Podcast with Matt Turck
date: '2026-04-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hDgF-ynV4Co
speaker: The MAD Podcast with Matt Turck
tags:
  - voice-ai
  - real-time-processing
  - voice-cloning
  - on-device-ai
  - speech-translation
title: 语音AI的未来：实时语音克隆、端侧部署与即时翻译的革新
summary: Gradium公司（源自QI实验室）展示了其在实时语音AI领域的突破性进展，包括PocketTTS端侧模型、Radbot语音代理框架及Hibiki实时翻译系统。这些技术实现了高质量语音克隆、低延迟互动和跨语言沟通，预示着游戏、直播、无障碍通信等领域的全新可能性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Gradium
  - QI lab
products_models:
  - PocketTTS
  - Radbot
  - Hibiki
  - Bridger clone
media_books: []
status: evergreen
---
### Gradium：赋能实时语音交互新纪元

Gradium是一家新近成立的公司，于去年九月创立，其核心使命是赋能实时语音应用。公司专注于语音交互的技术基础设施层面，而非开发面向特定垂直行业的终端产品或语音助手。Gradium致力于构建先进的模型与基础设施，以实现高质量的语音转录、合成与翻译，并支持其大规模、高效率的运行，从而赋能开发者围绕这些核心能力创造出创新的产品。

<details>
<summary>Original English</summary>

So, Gradium is a is a new company we created back in September and basically it's about powering uh real-time uh voice applications. What we mean by that is we focus on the technological layer for voice interaction. We don't make voice product for specific verticals. We don't make voice agents. We make models and infrastructure to create transcription, synthesis, translation, operate them at scale and help people create products around them.

</details>

### QI Lab的传承与技术基石

Gradium的成立，是源自QI lab——一个由我和Lauren以及其他几位伙伴在两年前共同创立的非盈利性实验室——的一次商业化衍生。QI lab在语音技术领域拥有深厚的研发底蕴，曾率先推出业界首批语音到语音（speech-to-speech）模型、先进的语音翻译系统，以及实现实时效果的文本转语音（TTS）与语音转文本技术。我们所开发的模型，已成为当前市场上众多主流音频生成模型的技术基石。基于这些强大的技术积累与市场洞察，我们决定成立Gradium，旨在自主研发并推出面向生产环境（production-ready）的尖端语音模型。公司的核心团队主要由经验丰富的工程与科学背景专家构成，其中不少成员曾效力于DeepMind、Meta及量化金融等顶尖机构，他们共同专注于构建语音AI的关键基础设施。

<details>
<summary>Original English</summary>

A bit of backstory about this company. It's a commercial spin-off from QI lab. So, it's a nonprofit lab Lauren, myself and a few others created two years ago. So, in particular, we introduced the first speech-to-pech models. Uh the first speech translation systems, uh realtime TTS, realtime speech to text. Our models uh have been used as the backbone for uh quantities uh sizes and pretty much all the current audio generating models out there. So we decided to create uh a company to you know make actual production ready models ourselves. Our team is mostly uh focused on engineering and uh science. So as Matt said most of the people are from deep mind meta and quantitative finance. So it's a small team really focused on the infrastructure part.

</details>

### 语音AI的范式迁移：从离线内容到实时交互

当前，语音AI的发展格局正经历一场深刻的演变。曾几何时，语音AI主要局限于离线内容的生成，例如为新闻文章配音或制作有声读物。然而，语音AI真正令人激动的未来，在于其能够赋能更加个性化、更具交互性的内容体验，其潜力和规模远超以往。

游戏行业是这一趋势的典型代表，越来越多的视频游戏工作室正积极寻求集成交互式NPC（非玩家角色）以及围绕语音构建的深度沉浸式体验。直播领域同样面临着巨大的技术挑战与机遇；尽管已有解决方案如视频配音技术，但它们大多仍运行在离线模式下。例如，在YouTube等平台上，有时会自动启用的实时配音功能，其效果往往无法忠实还原原始声音的细微之处。因此，将语音无缝集成到实时内容流中，提供了广阔的发展空间。此外，机器人技术的发展也清晰地指向了对能够进行自然、实时、可扩展且高度个性化交互的需求。

这种范式转变带来了根本性的技术与经济考量：过去，生成一次性的离线内容（如一本有声读物），可以通过被大量用户重复消费来分摊成本，即使过程缓慢且昂贵也是可以接受的。而如今，当音频仅是作为一种个性化体验或实时交互的组成部分时，它通常是为单个用户生成后即时消费并丢弃。这意味着，语音生成技术必须具备极高的处理速度和极低的成本效益。

<details>
<summary>Original English</summary>

So basically the current setting around voice AI is the following. So until recently voice AI was mostly about offline content. So that would be just reading an article on a news website or generating audio book. The most exciting part is much bigger than that and much more about personalized and interactive content. In one big example is gaming. So more and more we see that uh video game studios want to integrate interactive NPCs and a lot of experiences around voice. Live stream is also a case where uh there is the technology is really lacking at the moment. So there are some uh solutions for dubbing for example but they mostly run offline. If you tried or were a victim of the uh dubbing uh on YouTube that sometime turns on automatically you can hear you know how uh it's not really faithful to the original voice. So there are a lot of opportunities around uh being able to integrate voice into live content. uh robotics is also an obvious one where uh an interaction will be by nature individual and needs to happen in real time and need to be scalable. So basically right now the landscape has changed because when you generate an audio book you can have a solution that is slow and expensive because you amortize it because you generate an audio one that is consumed by the lot of people. Now when the audio is just a part of a personalized experience or an interaction it's generated for a single person and just and then thrown away. So it must be very fast and it must be very affordable as well.

</details>

### 卓越语音合成与克隆：个性化声音的艺术

在个性化内容生成领域，Gradium专注于实现前所未有的语音定制能力，并提供卓越的音质表现。通过与ElevenLabs等行业领先平台进行基准测试，我们已证实其语音克隆技术在效果上表现更佳。这意味着我们不仅能精准复现使用者自然、正式语调中的声音特质，更能捕捉到极其细微、独特的语调起伏与风格。

以游戏行业为例，我们正与一家知名的移动游戏开发商紧密合作，旨在为玩家的游戏体验注入个性化的电竞解说。传统游戏中，NPC的互动往往是预设脚本的线性播放。而我们的创新方案，通过集成一个能够实时分析游戏状态的大语言模型（LLM），为两名虚拟评论员动态生成解说脚本。令人惊叹的是，仅需提供真实的评论员10秒钟的音频样本，我们便能创造出宛如真人现场播报般的解说。

此外，这项技术在无障碍沟通领域展现出巨大潜力。对于渐冻症（ALS）患者，我们能够帮助他们恢复与疾病斗争前录制的声音，并以极高的保真度进行重构。例如，我们成功地为一位名叫Olivia的法国企业家复原了其声音，这位患病前活跃于播客界的专业人士，留下了海量的音频数据，这为我们提供了进行逼真声音复现的宝贵素材。

在个性化视频创作方面，我们也提供了新颖的体验。例如，为情人节设计的趣味功能，允许用户选择心仪的伴侣姓名，并录制一段简短的语音信息。随后，系统将合成一段包含该声音、并配以静态照片的个性化视频。

<details>
<summary>Original English</summary>

One of the things that we have been working on is personalized content in particular being able to customize voices with exceptional quality. So here for example is a a benchmark we run against 11 labs and uh basically we have better voice cloning and it's not only means that uh if you take uh like someone speaking in a natural formal tone we will replicate their voice better but we can also capture kind of very specific tones and styles. One example for that I think that is a good one is a gaming uh project we are working on with a big mobile game uh developer. The main idea is to be able to get a a personalized esport commentary in your game. Uh so you know it will be like when you play FIFA or these kind of games uh you know it's everything is scripted. You have a set of MPC files in the in the directory of the game that are played one after the other. Here the idea is that every gamer will have a personal experience based on the context. You have an LLM that analyzes the state of the game in real time and creates the scripts for two fake commentators. Just with 10 seconds of voice from uh two actual commentators, we are able to create uh something that really sounds like an actual commentary.

>> Hello and welcome Brawl Stars fans. We're following Panda YT who's currently sitting in a strong second place in the Angels versus Demons event and looking to climb higher. He's queuing into Trio Showdown on the Dark Passage map, bringing out the heavyhitting Ragnarok Frank. That's a high-risisk brawler whose super can win the game. But the map's bushes can make it tricky to land. And we're in. Panda YT's team spawns on the left with a cult and a TIG, which so here basically just from a 10-second sample, the model is able to infer then from the script that it should have this very commentator style voice. Voice cloning can be used for this kind of entertainment. It can be also used for a lot of applications. So for example, now we are pouring uh a new application around restoring the voice of people with ALS. So disease that uh make people unable to speak in particular when people have access to recordings before the disease. Uh we can reconstruct their voice with exceptional fidelity. So in that context what you're going to listen to is Olivia, a French entrepreneur. And the nice thing is that he gave a lots of a lot of podcast before he got sick. And so we had access to a lot of data and we were able to to replicate his voice in a very natural way. And uh now you can also do uh personalized videos. So for example that's uh just a fun experience we are putting out there for Valentine's Day tomorrow. So here the main idea is that uh you can make uh like you can choose the partner's name. So I go with my co-ounder Lauron for the for the demo. And uh let me just check that I have the right microphone actually. And so I will record a small uh a short uh uh recording with my voice. So Lauron, this message is for you for helping me preparing all these live demos. Uh so thanks a lot for your support and uh really looking forward to do more risky demos later during this talk. So now I have my audio. So Lauron, this message is for you helping me preparing. So you can hear my accent and all the terrible aspect of my voice. And so now we're going to start generating uh with a photo like a video for that. We'll get back to it later and we'll mute this uh this music for the sake of the of the presentation.

</details>

### PocketTTS：极致轻量化的端侧语音AI

在技术层面，我们自主研发并开源了一个名为PocketTTS的创新模型。该模型拥有高达1亿参数，却能直接在CPU上运行，无需昂贵的GPU，真正实现了设备端（on-device）的语音生成能力。PocketTTS不仅在性能上媲美甚至超越了Chatterbox等知名的开源模型，在与Koko等模型进行比较时也表现出色，同时集成了强大的语音克隆功能。

这款CPU模型允许用户以极高的保真度生成音频，并实现声音的个性化定制。这标志着一项重大的技术突破，它极大地拓宽了语音AI的应用场景。例如，目前已有基于PocketTTS的Nexus模式，被集成到Awards Legacy等游戏中，使玩家能够与纯粹由AI生成的NPC进行富有沉浸感的实时对话。虽然LLM部分可能仍需依赖API，但生成式语音部分已能在本地CPU上流畅运行，为游戏体验带来了前所未有的灵活性和成本效益。

<details>
<summary>Original English</summary>

So what we developed and open source so you can just uh use it with this single comment and is uh pocket TTS. So it's a 100 million parameter model running on a CPU. So not only it's its own device but it's running on CPU. It's competitive with a chatterbox uh and much bigger open source models. It's comparable to Koko that is quite famous but also comes with voice cloning. This uh CPU model allows you to generate highfidelity audio with voice cloning. This is a live demo of a CPUbased textto-spech model that delivers highfidelity voice cloning while running on edge devices opening up new opportunities for content creation. And so the fact that it runs on CPU now is allows for a completely new set of applications. So for example, there is already a Nexus mode life for awards legacy uh that allows people to have interactive discussion with NPCs that are purely generative. So here the LLM is still APIs based because we are far from having LLMs running on CPU but at least the generative part runs locally on the CPU.

>> The poor house elf. Did you help him? I'm afraid by the time I stopped laughing the elf had already operated away, leaving the boots to bury nothing but air. Don't look at me like that. I'm sure he's had worse days dealing with some of my more demanding housemates.

</details>

### Radbot与Hibiki：驱动智能代理与实时跨语交流

在构建更智能、更具交互性的AI代理方面，我们正迈出关键步伐。当前，文本类LLM已相当成熟，我们的目标是赋予它们强大的语音交互能力。最基础的应用是实现“LLM的声音”，即结合流式语音转文本（Speech-to-Text）和流式文本转语音（Text-to-Speech）。通过这种技术，用户可以实现近乎实时的语音输入与响应，大大降低了交互延迟。

为此，我们开发了一个即将开源的框架——Radbot。Radbot旨在让AI代理能够通过语音进行交互，并支持函数调用（function calling）等高级功能。当代理执行需要时间的工具调用时，Radbot能够通过自然的口语填充（filler）来维持对话的流畅性，而非让用户陷入沉默等待，并在获得结果后将其无缝注入对话流程。

在跨语言沟通方面，我们的Hibiki系统是目前唯一一款能够实现实时语音翻译的系统，并且它还能在iPhone等设备上离线运行。我们即将在两天后发布Hibiki 0版本，这一新版本无需对齐数据即可进行学习（learned without aligning data），实现了多语言支持和更优秀的语音克隆能力，甚至能处理更多非传统的语音风格。

以下是一些演示场景：
*   **互动式游戏NPC**：通过Radbot，AI代理能够与用户进行自然对话，即使在执行任务时也能保持流畅。
*   **旅行规划助手**：一位名为Sophie的旅行助手，能够理解用户意图，推荐目的地并提供酒店信息。
*   **实时语音翻译**：Hibiki系统能在离线模式下，将法语实时翻译成英语，并使用克隆的语音播报。
*   **体育赛事实时配音**：我们能实现葡萄牙语体育解说的实时翻译与配音，保留原始评论员的语调风格。

<details>
<summary>Original English</summary>

So basically now we have text LMS and we just want to interact with them through voice and the main idea is just to provide them with uh voice abilities. A very basic one is just uh voice of LM let's say. So you have an LLM and you add streaming speech to text and streaming text to speech. To give you an idea of how it works, let's see with the this small microphone. The main idea is that you can have real-time transcription and so as I'm speaking it's going to transcribe and this happens in real time and so I can give it that uh to the LLM and uh at the same time on the other side I will have uh the um streaming uh text to speech for the streaming text to speech at the same you're going to see the words being highlighted one after the other and it generated on the fly by consuming the text word by word.
>> Welcome to Gradium. If I could fix your problem by ordering you a pizza, I absolutely would.
So here, the fact that it consum consumes word by word, it means that as your LLM is generating the text answer, you're already generating speed. So all of this is going to save you latency. Now an LLM, what you would have seen if it had worked is just a basic LLM like with just a prompt and it just say stuff, but it completely hallucinates. What is more important is to have an agent uh that is going to have access to function calling uh to different tools. In particular, we have created this opensource framework that we will open source soon called Radbot. Basically, the main idea is that now you can power agents with voice and when they have tools that can take time instead of waiting in silence for them to get the result, it just keeps the conversation uh going and when they get the result they inject it back in the flow of the conversation. So, let's try this one.
>> Hi there, I'm Sophie from Wonderust Travel. How can I help you plan your next getaway? If you're not sure where to go, I'd love to suggest Paris, Bali, Dubai, Tokyo, Santorini, or Marrakesh. Each has something magical right now.
>> Okay. Uh, I guess I want to go to Tokyo.
>> Tokyo is an amazing choice. Right now, cherry blossoms are about to bloom. Imagine strolling through Shinjuku Guuan under pink petals. You've got two great options in Tokyo. The luxurious five-star Hikari Grand Tokyo with skyline views and a sky go or the charming three if you're excited.
>> Got it. You're leaning toward the Perfect. Just let me know if you'd like to explore one of the hotels I mentioned or if you'd like to switch cities. I'm here to help.
>> I'll go with the hotel in Hakusa. You mean Sakura House Asakusa? Great choice for that authentic cozy vibe near Senzo Gi Temple. Let me pull up the room details for you right now.
>> And so basically, you know, this was vibe coded in a few minutes with uh with code. And so with Gradbot, what you can see is that when it's looking up information, it keeps doing this natural filler and then it can pop information. We are going to open source this uh this framework so that people can can try voice agents uh you know in real time pretty easily. Another thing we can do is live translation. So, one thing that we introduced uh a year ago is uh called Hibiki. It's the only real-time speech translation system and it can run locally on a on an iPhone. So, here what you're going to to see is real time uh translation with voice cloning running in airplane mode.
Hi everyone. I'm delighted to be able to speak to you today. In France, my phone will translate what I am telling you to English. As you can see, it is an airplane mode. It doesn't have an internet connection because our machine translation model allows for real. So that was that we released last uh last year. In two days, we are releasing hibiki zero. So that's a new version. It's called zero because it's learned uh without aligning data. Now it's multilingual with better voice cloning. is that this voice cleaning also works for much less conventional types of of speaking.

>> Yes, it will enter the primary of Eloa. It is now in fourth place. Eloa passing there to cross. We are three laps from the final here in the Velo Romeo in Paris Olympic Games 2024. Portugal can
>> So you don't hear it, but basically it's a Portuguese dubbing. It's like the the actual commentator is speaking in Portuguese. And here it's a real time uh the being done by our model.
>> Win another medal in the Olympic Games, in track cycling, in the Madison race. There comes Portugal. There comes Portugal. There it comes. There.

</details>

### 结论与未来展望

Gradium的技术为语音AI的应用带来了革命性的变化。我们的API可在Gradium.ai上获取，同时，QI Lab的GitHub仓库中也提供了大量开源模型。您甚至可以使用“Bridger Clone”功能，免费为您的亲友发送一段充满个性的语音祝福。我们坚信，这些技术将开启一个全新的实时、智能、个性化语音交互时代。

<details>
<summary>Original English</summary>

And so now you can have even real time uh translation of sport commentator with all their speaking tiles and so on and so forth. I guess my video is uh is uh is ready and we can get a love message uh in video.
>> My dearest Lauron, I am profoundly grateful for your invaluable support in preparing our live demonstrations. I eagerly anticipate our future collaborations on even more daring presentations with deepest affection.
>> Yeah, you could recognize the accent, I guess. So, you can uh get our API on Gradium.ai. We also have a lot of open source models uh on the GitHub of QI labs and you can already send a love message for free to your loved ones with bridger clone. Thanks a lot.

</details>