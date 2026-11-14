---
author: AI Engineer
date: '2026-07-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hacEQHHhu2Q
speaker: AI Engineer
tags:
  - edge-ai
  - quantization
  - fine-tuning
  - on-device-llm
  - function-calling
title: 端侧智能重构：从 Gemma 2B 极致压缩到百M级极小模型的微调实战
summary: 谷歌端侧 AI 团队技术主管 Cormac Brick 深度解析了端侧大模型的最新技术进展。文章对比了 1-4B 小模型与 50M-500M 极小模型的适用场景，探讨了 2.9-bit 混合量化等内存压缩技术，分享了树莓派、Jetson Nano 和高通等硬件的端侧跑分，并给出了通过合成数据微调极小模型以实现高精度端侧语音函数调用的完整实操指南。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Cormac Brick
companies_orgs:
  - Google
products_models:
  - Gemma
  - LiteRT
media_books: []
status: evergreen
---
### 端侧 AI 的崛起与边缘计算的核心约束

在将智能引入成千上万种设备（而非仅仅局限于昂贵的机器人）的过程中，**端侧 AI**（Edge AI：在本地设备而非云端运行人工智能算法的技术）正迎来爆发。相比于完全依赖云端，将模型部署在设备本地具有显著优势：首先是**延迟**，本地运行能够提供快速且一致的响应速度；其次是**隐私**，所有数据都保留在设备本地；第三是**离线可用性**，即使在没有网络信号的区域，用户依赖的功能依然能够可靠运行；最后是**成本节省**，对于大规模出货的移动端或浏览器应用，即便单次云端调用的 Token 费用极其低廉，乘以海量用户基准后，累积的云端带宽和算力成本也会迅速飙升。

然而，在边缘端部署人工智能面临着非常严苛的物理限制，其中最核心的瓶颈是 **DRAM 内存成本**。在当今的供应链中，内存成本是一项极为敏感的硬件账单（BOM）支出。不仅许多智能手机厂商今年开始减少设备中的 DRAM 配置，自发布以来，树莓派（Raspberry Pi）3 6GB 版本的基础价格甚至上涨了约 2.5 倍。此外，端侧还面临着目标设备极度碎片化、硬件异构严重的问题。同时，当前的行业研究重心大多向超大规模的云端模型倾斜，而处于 LLM 频谱底端的超轻量级模型的技术和优化方法仍然较少被深入研究。

<details>
<summary>Original English Source</summary>

Yeah. So, yeah, a bit of a change of speed from the last two talks. So, we're looking at kind of higher-end robots. If we want uh for intelligence to get into lots and lots and lots of devices and not just really expensive robots, we are going to need tiny models. And this talk is about what is the state-of-the-art of tiny models at the moment. What are the things they're good at? Um, and what are the things you can go start building today.

Okay. So, yeah, firstly a bit of background like briefly on me and and the team I work on. Then we're going to take a look at small models that you may be kind of more familiar with. Just kind of explore what they can do, what they can't do um yet. Um, and then kind of see, hey, why do we need even smaller models? Uh and then just looking at the state-of-the-art of uh tiny models today and what you need to do to get them into a form and you can deploy them in production to do useful things. And yeah, lastly, we've got a couple of examples uh that we can look at uh from work from our team.

Okay. Um so me I work I've worked in um Edi for a while. Um uh um these days I work as a tech lead um on the AI edge team at Google. Within the team the types of things we do um are we develop kind of open source projects called like LiteRT, MediaPipe, and these make it easy to deploy AI to edge devices. We also do a lot of work delivering kind of edge AI core technology to Google's own products um some of which would be via tiny models um and then we also work with the Gemma team to ensure their models work well on um and run well on lots of devices. And then we have a significant focus on small and tiny models because that's what um that's what's useful uh for a lot of kind of mobile phone applications or if we want to be able to ship a model in browser uh that also has to be really really small. And generally our kind of playbook is we develop things for first party like for in-house use first and then if we can figure out a way to share that via an open source package or make those tools available to the wider world we do so, and that helps kind of lots of other people um build similar types of things using open source technology.

Okay, so why do edge AI? This is probably like um uh rel as opposed to just doing everything in the cloud. Um you know it's kind of obvious but I'll kind of go through it anyway. There's like kind of latency you fast consistent speed, privacy data stays on the device, offline use it's kind of reliably available. So that kind of um that that feature that you rely rely on in your mobile device will still work even when you don't have reception. That can be very helpful. And then savings um especially these days if the alternative is to call a um even a faster model on the cloud that will come at a cost. Uh particularly if you're kind of shipping an app or like a mobile phone app or something in browser where you know the user interaction is at kind of very very large scale. Then even though those tokens are relatively cheap, you're multiplying it by a large number and it'll add up quickly.

So then um the main challenges then of deploying AI on the edge is the leftmost one is kind of new uh which is DRAM cost, and um it's a really significant constraint that um and you'll even see some mobile phone manufacturers are putting less DRAM into their devices this year than previously. You'll also see that since since launch, the cost of a Raspberry Pi 3 6 gigabytes has gone up by a factor of like 2.5x. Uh so DRAM cost is really really significant. Um that then has a like casts a shadow over the rest of this talk, right? where in order to be able to get AI applications running on the edge, we need to really think a lot about kind of quantization and we also really need to think about what is the smallest possible um model we can use for a given task. Um other challenges are yeah there's a wider pool of target devices and yet another challenge is um yeah it's kind of fair to say that a lot of the research uh hours that go into LLMs these days are into the much larger models um and techniques and this types of stuff um and the the lower end of the LLM spectrum is a lot less studied uh so yeah these are challenges of deploying the edge.

</details>

### 小模型的极致压缩与多硬件性能基准

在端侧部署中，一类比较常见的解决方案是使用**小模型**（Small Models：参数量通常在 10 亿至 40 亿之间的轻量级语言模型，如 1B 或 2B 模型）。这类模型如今已开始被内置于主流操作系统中，例如高配安卓手机的 AI Core，以及苹果的 Apple Intelligence。它们在不经过复杂微调的情况下，仅通过零样本提示（Zero-shot Prompting）、LoRA 适配器（LoRA Adapters）就能展现出不俗的推理与 Agent 能力。然而，为了在移动端、IoT 或机器人设备上顺利运行，1B 到 4B 参数规模的模型通常仍会强制要求设备具备 4GB 到 8GB 的 DRAM，这无形中推高了终端的生产硬件成本。

为了压缩内存占用，谷歌端侧团队以 **Gemma 2B** 为对象进行了深度的内存足迹优化。该方案混合使用了 **2位、4位和8位量化**（Quantization：通过降低模型权重精度来压缩模型尺寸的技术），并配合层级嵌入（per-layer embeddings）等技巧，最终将权重文件的平均精度压缩至惊人的 **2.9 bits/weight**。压缩后，该 2B 模型在内存中仅需占用约 841 MB 的静态权重空间，如果再加上运行时的 KV 缓存（Key-Value Cache：缓存历史上下文以加速推理的内存空间），实际运行大约需要 2 GB 的活动 RAM。算上操作系统和其他系统服务的开销，这便是端侧部署小模型要求“4GB+ 内存”经验法则的由来。

在速度表现上，基于谷歌开源的 **LiteRT**（即原 TensorFlow Lite 改名后的全新端侧推理运行时）进行测试，各平台的解码跑分表现如下：
* **树莓派（Raspberry Pi）**: Gemma 2B 能够达到 **7.6 tokens/second** 的解码速度。如果开启多Token预测（MTP/Speculative Decoding：推测解码技术），速度可以提升约 2 倍。
* **英伟达 Jetson Orin Nano**: 能够实现约 **24 tokens/second** 的解码速度（使用英伟达官方工具链加速可获得更高的跑分）。
* **高通物联网开发板（Qualcomm IoT Board）**: 借助端侧 **NPU**（Neural Processing Unit：专门加速神经网络计算的专用芯片）的硬件加速，能够达到约 **4000 tokens/second** 的 Prefill（首 Token 延迟阶段）速度，以及 **31 tokens/second** 的解码（Decode）速度。由于多模态 Gemma 4 模型的一张中等分辨率图像相当于约 500 个 Token，高分辨率图像相当于 1120 个 Token，这样的硬件性能已经能够支撑每秒 3 帧的高清实时视觉输入处理，为端侧实时视觉交互提供了可能。

<details>
<summary>Original English Source</summary>

Okay so small models and when I small. I would mean kind of typically maybe kind of one to two or one to four billion parameters. You may find that these are built into the OS. There's a version of a small model that ships um in Android high-end phones today with AI core. There's a version that ships with Apple with Apple intelligence. Um some some um app vendors will ship a models this size in their app. We certainly work with some app vendors that do this. Um, and for like IoT and robotics, you would typically require like four maybe four to eight gigs of DRAM in order to be able to ship this grade of model which then has an implied cost on the device, right? So it then kind of restricts these models to you know things like laptops, mobile phones or kind of higherend electronics and kind of puts it out of reach of maybe a lot of uh lower tier web browsers or the wider kind of IoT and consumer robotics market.

Um yeah and for for smaller models yep developing smaller models and we'll look in a while we do a lot of work to minimize footprints with kind of quantization. Um and the playbook here is mostly prompting, right? If you want to deliver a particular feature using a smaller model, you can just kind of use zero soft prompting and get pretty good performance. Also to use Laura adapters and it's kind of somewhat robust at doing things like kind of function calling and agent skills.

Okay, so really quick example is like our you know um working with the Gemma team, our favorite go-to example is always Gemma for these kind of things. Uh so we can see that like the E2B model is um pretty capable in terms of reasoning. It's certainly like on par like with a Gemma 3 much larger model from kind of 12 months ago. Um and yeah, so we now have like much smaller models with that were pretty capable at reasoning and we get pretty decent answers just with zero shot prompting for a given task. We've also done lots and lots of work to optimize the memory footprint of that two billion parameter model as much as we possibly can. Um, so it uses a mix of like two bit, four bit and 8 bit quantization getting it down to like I know like 2.9 bits per weight if you look at the actual weights we need to hold in memory. We do other tricks like per layer embeddings. I won't go into like all of the detail here, but end result is we can you know you need maybe one like here it's 841 megabytes for a texton model in memory just for the weights and then you know maybe by the time you add in the runtime a KV cache um footprint you you might be up to requiring like two gigs of active RAM to be able to run this model then you account for an OS and the fact that there's other things going on that's where we get the kind of four four gig plus rule of thumb uh for deploying this on a device.

Um then in terms of speed, this is using our runtime. This is just a list of devices that we run on. Uh for the purpose of this talk, we're going to look more closely at the last three rows of the table, which is if we take that two billion parameter model and run it on a Raspberry Pi. Um that is will give about 7.6 tokens per second decode. This is without MTP. If you turn on MTP, that'll get maybe 2x faster depending on the task. Um, if you go to a higher a more capable device like a Jetson RN Nano, we can get up to maybe 24 um tokens per second decode or maybe even faster if you use Nvidia's own tool chain. This is with our tool chain. Um we also have done work to port this to a Qualcomm IoT board which is pretty popular among kind of higherend uh robotics and IoT applications and there yeah you can see you can get about like almost 4,000 tokens per second uh preill uh 31 tokens per second decode and that's useful for lots of like almost real-time um uh applications uh on an NPU because um with with these uh with Gemma 4 models like One medium resolution image is like kind of 500 tokens. A high resolution image is 1120 tokens. So you could get like you know three frames per second of high resol high resolution tokens um going through this model and have pretty decent decode speed as well. So there's lots and lots of compelling applications you can build with this type of with a small model if you're kind of if you're kind of market or if you're kind of willing to have more expensive hardware and have a more expensive um uh uh DRAM kind of of uh line on your kind of bill of materials for the device you're building. Uh yeah, just like our tool chain, we also work with other models in the community that are of similar size and they each have their strengths as well, right? Um so these are some of the other models that we support here.

</details>

### 机器人交互实践与从“小模型”走向“极小模型”的动因

为了探索端侧小模型在物理世界中的实际交互能力，DeepMind 的工程师 Xavier 利用闲暇时间开发了一个名为 **OpenDocMini V2** 的开源微型双足机器人。在这个业余兴趣项目中，他制作了两个版本的机器人，一个基于英伟达 Jetson Nano 开发板，另一个基于树莓派。实验表明，该机器人能够同时接收语音和图像输入，读取物理指示牌并做出点头、摇头等反应。然而，基于 Jetson Nano 的版本展现出了极为优秀且流畅的**实时交互**（Real-time Interaction）体验，而基于树莓派的版本虽然能正常工作，但响应速度明显慢得多，存在明显的迟滞。

这种交互迟滞凸显了“小模型”（1-4B）在极低功耗场景下的尴尬境地。如果应用在对交互实时性要求极高、硬件更为廉价的边缘设备上，小模型的延迟和资源占用仍然过于沉重。很多时候，AI 推理并不是设备上运行的唯一或主要任务，它可能只是主程序后台角落里的一个辅助功能，需要与系统的其他进程并发运行。为了保证系统的整体健康度和后台进程的低占用，研究团队必须进一步下探模型的参数量，将目光投向 **极小模型**（Tiny Models：参数量通常在 5000 万至 5 亿之间的超轻量化语言模型，如 50M 或 270M 模型）。

<details>
<summary>Original English Source</summary>

Um really briefly, I won't go into this in too much detail, but we also, if I can get this to play, um we also have a an app that you can use on both iOS and Android. So if you want to take one of these small models, see how fast it works in a phone, you can uh just go straight ahead and do that. Um so it's available on AI edge gallery. Also, all of the Oh, I'm getting that buzzing. Uh all the app is also fully open source. So if you want to see how to build something similar using one of these models or to see how this is using the open source runtime that runs the models, you can see all of that. So this is a great way of just getting started and trying small models if this is what you want to do.

Okay, this is another example uh which I'm not going to play this video but you should definitely check it out. This is an example showing a um an open-source the open doc mini v2 robot. This is one um Zavier, one of the um engineers in deep mind built this as a kind of hobby project. Really really fun. Um so go check out this YouTube video. What you what you'll see is he has two robots. One is uh one uses the Jetson Nano, one uses the Raspberry Pi. And um you'll see that the robot is able to um it's it's able to kind of like read signs like um and react to things and kind of nod its head. It's also kind of able to take both voice and image input. Um yeah, and what you'll see is the Jetson Nano one performs uh has really good real-time interaction. the one based on Raspberry Pi it works but it's kind of a lot slower right so for some examples um for some types of interaction um even the kind of best models we have today are are maybe not meeting a kind of user interaction requirements but yeah this is a really fun video so definitely check it out so yes um so then small models while uh they're great right if your product can afford uh to use one of these they're Uh they're really easy to use because you just need to zero shot prompt in order to get it to work. Um Genet has done great work in having you know low footprint high capable um uh models that are ready to use and they're optimized running on all of those devices uh you saw earlier. And you know if um yeah so if if all of your constraint if you can live within those constraints uh then great right your journey would stop here and you would build a feature you would want right for lots and lots of other things that that we do in our work and other people that we talk to. You know we're still at a point where small models are too big because they can't reach like older laptops or kind of more consumer edge devices. um the user interaction needs to be more responsive. Um we also could have the reality and we do of this a lot of times where the the model you want to run isn't the main feature in the application. It's like one tiny thing in a corner that needs to run while everything else in the system is running. Um so we also need a smaller model for system health. It's a common uh common pattern.

</details>

### 极小模型（50M-500M）的微调与端侧函数调用实战

**极小模型**（参数在 50M 至 500M 之间）是解决边缘端实时交互和低算力要求的终极方案。这类模型的内存需求可以降至 2 GB 以下甚至更低，能够轻松部署到各类老旧笔记本电脑、低端消费级物联网（IoT）设备上。在一些特定、固定的垂类任务中（如语音识别 ASR、端侧轻量视觉任务），市面上已有成熟的预训练极小模型。例如苹果发布的 **FastVLM** 仅有 5 亿（0.5B）参数，在安卓设备上配合硬件加速可以实现极速的视觉 awareness 解析。

然而，如果现成的模型无法满足定制化的业务逻辑，工程师就必须采用微调方案。谷歌目前提供了一系列轻量化基座模型，包括起步仅为 2.7 亿参数的 **Gemma-3** 基础模型，以及经过函数调用预训练的 **Function Gemma**。在树莓派上运行 270M 级别的模型时，解码速度可以直接飙升到 **45 tokens/second**，这是因为极小模型的参数量少，推理时每次从 DRAM 读取权重所需的带宽和开销呈数量级减少。

在具体的端侧应用场景中，**语音函数调用**（Voice-to-Function Calling：将用户的语音输入识别为文本，再通过 LLM 输出特定 API 函数格式的技术）对没有屏幕的 IoT 边缘设备至关重要。谷歌端侧团队通过在 ASR 模块后置微调后的极小模型，开发了“移动设备动作执行”（Mobile Actions）原型：
* 该 270M 模型仅需接收自由文本或语音转写输入，就能以超过 **86% 的可靠性精度** 匹配并调用手机本地的 10 种高频核心 API（如调节 Wi-Fi 开关、创建日历日程）。
* **微调实战指南**：极小模型微调的成功，完全取决于**合成数据集**（Synthetic Dataset）的构建。谷歌团队在 Hugging Face 开源了名为 Mobile Actions 的数据集。实践表明，针对单一特定任务，准备 **10,000 到 10,000,000 条**高质量合成训练样本进行监督微调（SFT），其最终的特定任务表现和生成质量，可以比肩甚至超越参数量数倍于它的 2B 或 4B 模型。同时，由于体积急剧缩小，模型响应时间大幅缩短，设备兼容范围也大大拓宽。

<details>
<summary>Original English Source</summary>

So then enter kind of tiny models, right? So these are typically in the as small as kind of 50 million parameters. We've deployed models that small uh to maybe 500 million parameters. Uh they're easier to ship natively with applications. They would run on the types of things you see on the right hand side. Um uh and would require you know maybe less than 2 gigs of RAM or or even less than that. And they can also be made to run really really fast. But the playbook to deploying here it's a little more complicated. Um so you know sometimes there's off-the-shelf models that'll do what you want and we'll look at those in the next slide. um or else if that doesn't work, you're going to be left in a world of kind of fine-tuning a model to achieve a given outcome, but which works very very well.

So fixed task models um there's a bunch of things around ASR, vision and embedding models and if you have a if you have something uh yeah so like ASR and vision and embeddings these are all kind of stock features and they work really really well. This is an example of Apple fast VLM uh which is 0.5 billion parameter model running on a Android device using hardware acceleration and you can see it runs really really fast. So if you needed to kind of add a little bit of visual intelligence to a um like an edge device or an IoT device, you know, this class of model is an excellent uh is an excellent option to get that kind of first level of visual awareness or for ASR. Um yeah, there's some kind of strong models listed here as well. And and then lastly, embedding models are great at um uh yeah, like this is just a text embedding model which is yeah really good at kind of processing and match matching text which is can be relevant in some cases.

Okay. Um but then next scenario is you want to kind of fine-tune a model. Um so here you can start with uh the models I'm citing here are kind of Google developed models. Uh so there's some starting at like 270 million parameters and Gemma 3 and function Gemma. Uh Gemma 3 is a general purpose model. Function Gemma is one that has extra pre-training uh for function calling patterns. So here the performance if you remember earlier on the Raspberry Pi our performance was at uh mids single-digit tokens per second decode. So here that kind of jumps up to 45 tokens per second because we need to read less uh from memory each time. And we can fine-tune this to do pretty compelling things. So on the right hand side um this is running a uh what we call a mobile actions model. Uh so this does text in and function calling out. Um this model knows about 10 different output functions and can call them at over 86% uh reliability from a given arbitrary text input. And this is for doing common things on a mobile device like uh schedule a uh calendar or turn on and off Wi-Fi or things like this. And it can take like arbitrary free text input and convert that to appropriate function calling. And for this demo, we've taken another ASR model and put it in front of that. Um which gives kind of voice to function calling as a feature. And voice to function calling is pretty key for lots of IoT and edge devices because um yeah like smaller devices tend to have you know require settings menus and that user interface can be really really challenging for lots of people. Uh so yeah being able to just talk to something to ask for a given outcome. This is a pretty key capability and uh we can do that reasonably reliably using a fine-tuned small model.

So the playbook is generally then you pick a base model you check the performance if the performance and memory footprint are within the range that you want and then um the kind of the harder part is you uh the playbook we've found works really really well is we synthetically generate data to fine-tune that model um depending on the model like um there's a data set we've open sourced here called mobile actions it's available on hugging face that corresponds to this if you want to kind of recreate that same demo yourself and fine-tune function gemma from scratch. Um but we we've generally found that in the range of 10,000 to 10 million samples of synthetically generated um data will be sufficient to fine-tune a smaller model to a really really high degree of reliability. And so for other tasks we've done like things like summarization or proof reading. So something which you could do with a two or four billion parameter model reasonably reliably if you're willing to put the time and energy into creating a synthetic data set and fine-tuning a model you can achieve a similar like the same or greater quality with a model that is much much smaller will work on a much wider set of devices and will be much much more responsive. Um so yeah and that's that's the type of outcome we're seeing now with just fine-tuning a model for a single task and it's a really like yeah we found this is a really good playbook uh for deploying at like very wide scale.

</details>

### 端侧极小模型的生产级落地与未来展望

将极小模型应用于实际生产环境，能够让许多原本极其依赖云端服务器的高阶功能转化为**完全本地化、无订阅门槛**的纯单机功能。谷歌展示的端侧免订阅实时语音听写应用（Voice Dictation App without Subscription）便是典型范例：
* 该应用将所有的语音转写及文本处理工作全部保留在设备本地进行。
* 其底层架构由两个运行于本地的极小模型构成：一个负责端侧 **ASR 语音转写引擎**，另一个负责**文本修正引擎**（Text Policing Engine）。
* 本地文本修正引擎能够自动识别并清除口语转写中夹杂的无意义语气词（如“呃”、“啊”），并且能够根据用户个人高频使用的特定人名、词汇进行个性化偏差校正（Personalization / Biasing）。
* 支撑这两大功能的本地模型，其参数量仅在 **1亿至3亿**（low single-digit hundreds of millions）级别，保证了极低的能耗与极高的响应速度。用户目前已可在 iOS 和 Android 设备上体验此类开源架构的本地应用。

此外，极小模型也正在改变 PC 端的软件生态。例如，谷歌在桌面端 Chrome 浏览器中推出了开发者预览版的内置 API 接口（Built-in APIs），为开发者直接提供端侧的“网页内容摘要”（Summarization）和“文本润色纠错”（Proofreading）功能。将这类任务委托给百 M 级别的极小模型，使得 Chrome 团队能够将人工智能功能分发给全球范围更广、硬件水平更低的普通用户，而无需担忧高昂的服务器算力与带宽成本。

展望未来，边缘端极小模型的研究将致力于进一步实现语音到函数调用的泛化，利用 Agent 自动化构建并优化针对各种特定设备的合成训练数据集。同时，在端侧视觉领域，研究人员也正加速推进运行效率更高的轻量视觉模型，以在极低的资源开销下实现端侧的目标分割等高阶视觉能力，重塑边缘端的人机交互体验。

<details>
<summary>Original English Source</summary>

So here's another example in this is one example in production where we have this is an app that we've developed for voice dictation without subscription. Um all of the voice dictation happens locally on device. Um, and as well as just doing dictation, it also does uh it also does um wow, it kind of cleans up ums and a's, right? If you see on the right hand side, it's able to clean up text. It's also able to do biasing towards kind of words and names that um uh are kind of relevant to you personally. So kind of personalization. The left hand side kind of shows how we built that application. So there's an ASR engine and a text policing engine. And both of these are fine-tuned versions of tiny Gemma models. And this allows us to take something that would have been a kind of like server only feature of, you know, where you require a subscription to do highly accurate uh voice dictation and have an app that's just able to do that completely offline with very very good quality. Uh so this is something you can try on iOS if if you want to give this a go today. But um uh yeah and it just uh the backbone of this app is kind of two fine-tuned uh small gemma based models in the low single-digit hundreds of parameter million parameters.

We also worth uh noting is there's also uh kind of features in developer preview in Chrome for example that kind of summarization and proofre APIs or feature as built-in APIs in Chrome and delivering those features via tiny models allows um the Chrome team to ship them to a much wider set of uh Chrome users than would otherwise be possible.

Um yeah, so that's uh we've probably g have like one minute for questions. Um some kind of key takeaways. It's on the last slide if I can get there. Yeah. So takeaways from consumer devices and entry-level robotics is small LLMs are easy to use. Uh and especially on NPUs, uh they're very very fast. Uh tiny models will will enable reach to a much much larger pool of devices and voiceto function calling um can now be built to to be robust using tiny models. Uh it just requires kind of investing in an appropriate synthetic data set with enough samples and then you can fine-tune a model to get really good outcomes.

Cool. So happy to take one or two questions or um if anybody has one. Yeah. Sorry. I'm going to plug this out. Yeah. Sorry. Sorry. Second. like broader ambitions of where tiny models can go. Wow. Um, I think kind of generalizing voice to function calling um is a is a is a one key goal like making that very easy for lots of people because I think that's a key use case that if we can figure like if we can figure out how to make, you know, have like an agent generate the synthetic data for you, right? Um, if we like it's certainly possible to make that journey much easier than it is today and make it available to a lot more people. Um, yeah. and and certainly the the visual input as well. Um that takes a little bit of time at the moment. There's certainly scope to have faster models there that can do a wider set of things like kind of segmentation and other things that would enable other use cases.

>> Awesome. Yeah. Do you see the time? We probably don't have uh Q&A session for today. Yeah. But Corman will stay after the session maybe and you can ask for more question about I'll stay after this session or you can come grab me downstairs at the Jeep mind booth at 4:00. I'll I'll be there 4 to 5. Okay.

</details>