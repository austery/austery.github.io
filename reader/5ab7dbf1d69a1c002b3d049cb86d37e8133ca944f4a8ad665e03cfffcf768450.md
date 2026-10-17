---
author: AI Engineer
date: '2026-07-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KB41dTlX1Uc
speaker: AI Engineer
tags:
  - local-ai
  - model-optimization
  - edge-computing
  - open-source-software
  - knowledge-distillation
title: 本地AI峰会圆桌讨论：为什么是本地，为什么是现在？
summary: 本篇圆桌对话围绕本地AI的爆发性拐点、多模型混合架构、模型量化调优、数据主权以及开源生态建设展开。NVIDIA、Osmantic、Roboflow和EXO Labs的专家深入探讨了企业如何利用前沿大模型微调小模型以提高Token效益，并分享了在有限边缘端算力下压榨出十倍推理性能的实战案例，指出降低体验门槛和积极倡导开源对本地AI落地的关键意义。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - NVIDIA
  - Roboflow
  - ExoLabs
products_models:
  - Llama
  - Nemotron
  - Qwen
  - DeepSeek
media_books: []
status: evergreen
---
### 行业发展拐点

**主持人**: 大家能听到我们说话吗？好的，音响检查完毕。各位，让我们为**本地AI（Local AI）**热烈鼓掌！[掌声] 我希望大家和我们一样兴奋。这是**本地AI峰会（Local AI Summit）**。今天我们将整天讨论本地AI。之所以如此，是因为我们在今年迎来了一个拐点。不仅模型变得非常好，配套的开发框架（Harnesses）也变得非常出色。这一切发生得实在太快了，我想在座的每个人都在努力跟上它的步伐。我在去年11月看到 **Andre Karpathy** 发的一条推文时感触最深。他发推说，你现在还不能完全信任这些**自主编码智能体（Coding Agents）**，你必须像鹰一样紧紧盯着它们。然而仅仅三个月后，他又发推称自己正在吃力地跟上这一切变得如此强大和出色的步伐。事实是，他这两次都说对了。这个领域的发展速度令人难以置信。你可以用它做太多的事情，说实话，唯一的办法就是今天比昨天多用一点点，这就是紧跟这个领域步伐的方法，而这正是你们在座的各位此时此刻正在做的事情。所以我对这个圆桌论坛感到非常兴奋。我们使用AI的方式也发生了改变。我们不再仅仅使用聊天机器人，不再只提一些简单的问题。当我们迎来**推理模型（Reasoning Models）**时，AI模型的响应特征改变了。它不仅是爆发式地回应我，而且在爆发之前会经历一段平缓的“平台期”。它在进行推理，在消耗我并未直接接收的思考Token（Thinking Tokens）。接着我们迎来了智能体，突然之间我甚至不想关掉这些智能体了，我希望它们能一直在线运行。如果我们把它们配置好，它们可以一直保持生产力。因此，企业希望将大量核心知识产权（IP）注入其中以使其更具实用价值；消费者也是如此，我想给它我的健康数据、我的病历、我家里摄像头的视频画面。无论是企业还是消费者，我们都不希望这些隐私泄露。此外，随着Token的持续生成，成本突然之间变得至关重要。因此，本地化对于解决这两点来说是不可思议的解决方案。它能确保你生成的Token成本是固定的，并且所有数据都留在那个房间里。今天在这些演讲之后，我们会有非常棒的演示，所有运行的内容都将保留在那些本地设备上，保留在这个房间里，这是一个非常美好的保证。那么，在切入圆桌讨论之前，大家先自我介绍一下好吗？

<details>
<summary>Original English</summary>

**Host**: Can you guys hear us? Sound check. All right, give it up for local AI, everyone. [applause] I hope you guys are excited as we are. Um, this is woo. This is the local AI summit. So, we're going to be here all day talking about local AI. And the reason why is we hit an inflection point this year. Not only did the models get really good, but the harnesses got really good. And this happened really fast. It's been, I think, a struggle for anyone here to keep up. I felt that most when I saw one of Andre Karpathy's tweets in November. He tweeted that you can't really trust these coding agents alone yet. You have to monitor them with an eye like a hawk. Three months later, he tweets that he's struggling to keep up with the capabilities of how good this all has gotten. And the thing is, both times he was right. This space is progressing really quickly. And it's wild how much you can do. And honestly, the only thing to do is just try to use it a little bit more today than you did yesterday. That's how to keep up with this space. And that's exactly what you guys are doing right here. And so I'm really excited about this panel. The way that we use AI has also changed. I'm not just using chat bots. I'm not just asking simple questions. When we got reasoning models, the profile of how the AI model responded changed. Not only is it bursty and responding to me, but before the burst, it kind of plateaus for a bit. It's reasoning. It's turning on tokens that I'm not consuming. And then we got agents. And suddenly I don't even want these agents to turn off. I want these always on agents. They can always be productive if we set them up. And so we have enterprises that want to put a lot of their IP into this because it becomes more useful. We have consumers with the same thing. I want to give it my health data, my medical records. I want to give it footage from my home camera. And both enterprises and consumers, we don't want that stuff to leak. And as you also have a profile of tokens continuously generating, suddenly costs matter. And so local is amazing for both of those things. You get to make sure that you are plateaued on the costs for the tokens that you're generating and also everything sits in that room. So we have amazing demos here after these talks where everything that's being run stays on those devices. It stays in this room and so that's a really nice guarantee. So as we turn over to the panels, first do you guys want to introduce yourselves?

</details>

**Alex**: 好的，我可以先开始吗？

<details>
<summary>Original English</summary>

**Alex**: Yeah. Should I start please?

</details>

**主持人**: 你的麦克风有声音吗？

<details>
<summary>Original English</summary>

**Host**: You got the mic?

</details>

**Alex**: 有的，已经戴好麦克风了。大家好，我是 Alex，我是 **ExoLabs** 的联合创始人兼 CEO，也是 **local.ai**（注：开源本地AI项目）的创造者。我们致力于本地 AI 领域已经超过两年了，在这个瞬息万变的技术空间里，两年感觉像是过了很久。回想起早些时候，我们还在两台 MacBook 上运行 Llama 进行测试，而现在我们已经实现了在四台 **DGX Spark** 设备上运行 **Nemotron Ultra** 的演示。我们的使命是让人工智能变得更加普惠和触手可及。看到现在能实现这样的效果，真的是太疯狂了。

<details>
<summary>Original English</summary>

**Alex**: Yeah, you're miked up. So yeah, I'm Alex. I'm the co-founder and CEO of ExoLabs and also the creator of local.ai. So we're we've been working on local AI for over two years which feels like a lot longer in this space and you know from the days of you know running Llama for AB on two MacBooks to now where we have you know demo there of Neimatron ultra running on four sparks you know our mission is to make AI more accessible and you know it's crazy to see what is possible now um

</details>

**Matt**: 大家好，我是 Matt。我主要做一些内容和视频。我们有一份专门介绍人工智能的简报。我是一个 AI 爱好者。非常感谢邀请我来参加。

<details>
<summary>Original English</summary>

**Matt**: cool hey everybody I'm Matt um I make content and videos. We have a newsletter all about artificial intelligence. I'm an AI enthusiast. Uh and yeah, thanks for having me.

</details>

**Ahmed**: 大家好，我叫 Ahmed Osman。我是 **Osmantic** 的创始人兼 CEO。之前有人在私信里问我：“嘿，OS man 代表什么意思？是代表 Open Source Man（开源侠）吗？” 于是这后来就成了我们公司的名字 [笑声]。另外，我还是 **r/LocalLlama** 子版块（Subreddit）的版主。自2022年起我就一直身处这个本地 AI 领域。让我们一起携手推动开源和本地 AI 的融合，共同取得胜利！

<details>
<summary>Original English</summary>

**Ahmed**: Hey everyone. Um my name is Ahmed Osman. Uh I am the founder and CEO of Osmantic. Uh somebody jumped into my DMs asked, "Hey, what does OS man stand for? Open source man." So that became a company. [laughter] And uh I also moderate local lamb subreddit. I have been in this local AI space since 2022. And uh yeah, let's uh let's make open source and local AI one.

</details>

**主持人**: “开源侠”赢得了全场的掌声！[笑声]

<details>
<summary>Original English</summary>

**Host**: Open source man gets the round of applause. [laughter]

</details>

**Joseph**: 这是当之无愧的。我认为今天对我们这个圆桌论坛来说是一个非常重大的日子。你知道，**Fable** 刚刚回归，但这是一个很好的提醒，提醒我们为什么必须拥有访问前沿智能（Frontier Intelligence）的权限才能去构建任何东西。我是 Joseph，**Roboflow** 的联合创始人兼 CEO。我们专注于计算机视觉领域的一切事务。我经常开玩笑说，**计算机视觉**其实是“最原始的本地 AI”，因为视觉处理必须与你的视频捕捉设备并发运行，且需要极低的延迟，在采集图像和数据的地方直接进行处理。我非常期待今天的探讨，交流为什么本地 AI 是让 AI 对每个人都真正实用的未来。

<details>
<summary>Original English</summary>

**Joseph**: That's appropriate. Today is I think a pretty momentous day for the panel. Um you know, Fable just came back, but it's a good reminder of why we need to have access to Frontier Intelligence to be able to build anything. Uh I'm Joseph. I'm co-founder CEO at Roboflow. We do all things vision. I kind of like to joke that vision is like the original local AI because like everything needs to run probably concurrent with like low latency alongside your video. Uh where the images and data is being captured. Uh looking forward to the discussion today and all things why local AI is the future of making AI useful for everyone.

</details>

**主持人**: 谢谢大家！让我们再次给 Joseph 和所有嘉宾热烈的掌声！[掌声] 有一件事让我非常兴奋，就是今天在座的各位以各自独特的方式，都极早地进入了这个领域。既然大家都深切感受到了如今的爆发式拐点，那么你们认为自己是在什么时候最早感知到这个行业拐点的呢？

<details>
<summary>Original English</summary>

**Host**: Everyone let's give Joseph and everyone a round of applause. [applause] So one thing that I'm really excited about for all the panelists is you guys were all early to the space in your own way. Uh and you know very early and I think as we all feel this inflection point now uh when do you guys feel like you felt the inflection point?

</details>

**Alex**: 好的，我先来。说实话，当我第一次看到 **Llama** 时，我真的被彻底震撼了。能够把这种强大的智能下载到本地电脑上运行，这种想法实在太令人兴奋了。我骨子里是一个喜欢折腾和动手构建的人，我玩 PC 超频已经很多年了。所以，能让我办公室里的本地设备运行这种近乎“外星智能”的东西，传统硬件超频极客表示简直太酷了。在 Llama 出现之前，我甚至觉得这根本是不可能实现的，直到我亲眼见证了它在本地跑起来，我当时惊呼：“哦，天哪，这简直不可思议。”

<details>
<summary>Original English</summary>

**Alex**: Yeah I can go first. Sure. I mean look when I first saw Llama right I got really excited the idea that I can actually download this intelligence run it from my local computer. It was very exciting. I'm a tinkerer at heart. I'm a builder at heart. I I've overclocked PCs for years. So, this just felt like so good. So, felt so interesting to be able to have this crazy alien intelligence running on on my device in my office. Uh and that that was the first time where I didn't even think it was possible to be on till I saw Llama and I was like, "Oh, wow. This is incredible."

</details>

**Ahmed**: 我想我的经历非常类似。对我来说，那是 **Llama 2** 发布的时刻。我终于在我的 **NVIDIA RTX 4090** 显卡上跑通了模型，那一刻我心想：“天哪，我竟然能够拆解和理解这个黑盒子，还可以自定义它、调整各种参数，比如采样参数以及各种底层配置，甚至能洞察推理引擎是如何运转的。”这让我感觉像是某种开关突然被打开了。就像魔法一样，我仿佛成了手握魔法棒的巫师。我可以控制它的思考方式，让它去贴合我的逻辑。从那之后，剩下的就是历史了。基本上，我一直在大声疾呼为什么本地和开源 AI 必须与云端 AI 共存，以及我们应该如何去推动它的普及，尽一切努力去解密它，并将这些知识传播给更多的人。

<details>
<summary>Original English</summary>

**Ahmed**: I I think I um it's kind of the same for me. Uh yeah, it's Lamatu. I think that um finally on my 4090 RTX 4090, I'm like, "Wow, I can actually understand this black box and customize it and play with parameters and like you know, sampling parameters and all those uh configurations and see how inference engines work." Uh that that that made me feel like you know something clicked. It's like oh magic. I can be a wizard now with this thing. I can control how it how it plays to my ways of thinking. Um and from there it was you know the rest is history. Basically, I've been very vocal about why local and open source AI must coexist with cloud and how how we are supposed to like, you know, push for that and try to understand it as much as possible and teach people about it.

</details>

**主持人**: 完全同意。其实我也深有体会。那是在2023年的一次飞行中，我尝试在手机上运行一个本地模型。说实话，当时的体验非常糟糕，生成一句话足足花了20分钟。但因为当时飞机上没有网络，我依然可以在离线状态下向这个智能模型进行提问，这让我第一次切身感受到：这绝对是一项极其酷炫的技术。

<details>
<summary>Original English</summary>

**Host**: Totally. I actually felt this as well. I was on a plane. I think it was in 2023 and I had a model running on my phone and it was awful. It took 20 minutes to complete a sentence, but I didn't have internet and so I was able to like ask intelligence something there in the plane and that was my first feeling of like hm this is going to be something really cool.

</details>

**Alex**: 你知道现在你已经可以在你的 iPhone 上运行相当于 GPT-4o 级别的模型了吗？

<details>
<summary>Original English</summary>

**Alex**: Do you know that you can run the equivalent of GT40 on your iPhone now?

</details>

**Matt**: 真的吗？

<details>
<summary>Original English</summary>

**Matt**: Really?

</details>

**Alex**: 是的，就是 **Qwen 3.5** 的 40 亿参数（4B）版本。它的回答质量基本上与过去必须由数据中心提供服务的模型相当，而如今它就躺在你口袋里的设备中。

<details>
<summary>Original English</summary>

**Alex**: Yeah. It's quen 3.5 the four parameter for billion parameters. It it's basically the same quality as something that used to be served in data centers and it's in a device in your pocket.

</details>

**Matt**: 确实，这太疯狂了。

<details>
<summary>Original English</summary>

**Matt**: Yeah, that's crazy.

</details>

**Alex**: 是的，你想想看，当时 GPT-4o 问世的时候是多么震撼，而现在你已经可以在手机上运行它了。过去很多时候，你必须要有前瞻性的眼光，看清技术未来的走向，因为早期它就像是个玩具。对我而言，有几个非常关键的节点。第一个是在本地运行 **Llama 45B**，那是第一个真正意义上的大型开源模型。我记得它极大地缩小了开源模型与闭源前沿模型之间的差距。但当时它在本地每秒只能跑 2 个 Token，所以并没有太多实际用途。接着，另一个重大时刻是 **DeepSeek**，包括 **DeepSeek-V3** 和 **DeepSeek-R1**。DeepSeek-V3 带来了巨大的改变。之前的 Llama 4 采用稠密架构（Dense）导致运行速度非常慢，而 DeepSeek 释放了性能。这让我意识到：“哇，用我现有的设备，比如 Mac Studio 或是 DGX Spark，就可以以非常体面的速度运行如此庞大的模型，性能完全可以媲美云端。” 另外，最近对我而言，**GLM 5.2** 也是一个里程碑式的时刻，它再次缩小了差距，达到了类似 Claude 3 Opus 的水平，而且我们就把它运行在旁边那台完全可以放在桌面上的 **DGX Station** 上。这展现了清晰的发展趋势：硬件体积会越来越小、内存消耗更低、压缩和量化算法更好，我们能够在本地运行能力更强的模型，很快这就会成为默认选择。

<details>
<summary>Original English</summary>

**Alex**: Yeah, I think if you just think about like how crazy that GPT40 moment was and now you can run it on the phone, it's like I think a lot of this stuff was just, you know, you had to see the vision of like where things were going because it was a toy, right? It was like, you know, the the first I think there were a few key points for me. One was like running Llama 45b locally, right? That was like the first really big open source model. And I remember like the gap it closed the gap quite significantly with the frontier closed models and open uh but it ran at two tokens a second so it wasn't useful right um and then you know another big moment was deepseek um both v3 and r1 deepseek v3 was like a massive so like you know llama 4 was dense so it's super slow seamed to unlock the performance so it was like oh wow you know with the devices I already have like with a you know a Mac uh Mac studio or Spark, I can run, you know, this massive model at actually like decent performance which is comparable with, you know, what you can run in the cloud. And then uh I think just recently to me GLM 5.2 is a big moment as well. Uh because again it's closing the gap and it's like you know Opus level um and you know we have it running over there on a device that like literally can fit on your desk uh the DJX station. So this is to me just like you know a trend and it's going to keep increasing right like there's going to be smaller and smaller devices with less memory better compression we'll be able to run more capable models locally and you know soon it'll be the default

</details>

### 视觉本地化启示

**Joseph**: 我也想分享一个有关飞机的经历。我完全赞同刚才关于硬件和模型演进的看法。大概两三年前，我坐飞机时旁边坐着一位视障人士。如果你熟悉苹果设备，你会知道它有一个辅助功能，你拍下一张照片，它会自动向你语音描述照片的内容。当时在飞机上，那个人不停地拍照，试图了解自己坐在哪里、安全带该怎么扣上等等。我清楚地记得，他对着前排座椅靠背拍了一张照片，苹果的辅助功能将照片描述为“打印机”之类的一样东西。根据当时的机舱语境，这位乘客显然知道这不可能是打印机。当时多模态模型 **Llava** 刚发布不久，它是通过文本基底进行描述的，虽然算不上原生的多模态，但依然是个好例子。出于好奇，我也用 Llava 对着我面前的小桌板拍了一张照片，结果它非常准确地描述出了场景：“嘿，你正在一架飞机上，这是你面前的小桌板。”我把这个结果展示给旁边那位从未接触过本地模型和本地 AI 的乘客看。这给我的震撼在于，一家市值数万亿美元的科技巨头，为手机端用户提供的用于描述视觉场景的顶尖AI功能，竟然逊色于一个向所有人开放、人人皆可获取的开源本地模型。那一刻是一个极其清晰的分水岭，它表明哪怕是最大的科技巨头，也无法垄断前沿的智能技术。让这种智能变得越来越普惠，对于释放这项技术对社会的深远影响而言至关重要。

<details>
<summary>Original English</summary>

**Joseph**: I'll keep with the theme of of airplane stories. So yeah, I I agree that there's been like multiple moments over over time of what's been what's been going on. But one person... I have a presentation for that after this. So stay around, please. All right. Uh one example moment where this like came up for me was uh I was on a plane. I was sitting next to someone man this is maybe two three years ago and they were hard of sight and they were using if you on Apple you know if you take a photo of something you can use the accessibility settings and it'll describe the photo to you and we were seated on the plane together and they were taking constant photos to understand where we seated and how to get buckled in and these sorts of things and I remember they took a photo of the seat back in front of them and the Apple accessibility described the photo described it as like a printer or something and it was like oh yeah like you're seated like by a printer and of course the individual knew from the context that couldn't be right. Uh, and I was like, you know, I wonder Lava had just come out, a multimodal model that like kind of just described things with like the pivot to text base rather than like natively multimodal, but still kind of a useful example. And I was curious. I was like, well, let's see how Lava would do on the same thing. So, I took a photo of like the seat tray in front of me. And it aptly described it. It's like, hey, you're on an airplane. That's the seat tray. And I showed the person sitting next to me who had never seen local models and never experienced local AI. And what that stood out to me is I was like, man, a company that's a trillion dollar plus market cap business, shipping the latest intelligence on their phones for describing visual settings is inferior to something that's broadly accessible and available to anyone. And that was such like a watershed clear moment that like even the largest companies don't have a monopoly on the frontier of intelligence. And so increasingly making that be accessible to others um is I think going to be critical for understanding all the massive impacts the tech will have.

</details>

**主持人**: 没错，而那仅仅是第一代的 **Llava** 模型！[笑声]

<details>
<summary>Original English</summary>

**Host**: And that was lava. Yeah. [laughter]

</details>

**Alex**: 哈哈是的。那大概是在2022或2023年左右，真是一段宝贵的探索期。

<details>
<summary>Original English</summary>

**Alex**: Yeah. It's interesting to hear that's like 2022 2023, right?

</details>

**主持人**: 围绕那个时间点，确实发生了不少事情。听到你谈论这种可达性（Accessibility）真的很有趣。让前沿智能变得真正有用的关键，是为它配备“外设”——在那个案例中就是一个摄像头，使它能够获取面前的真实数据。我认为今年我们迎来的拐点，远不止于模型本身的提升，更在于外围框架（Harnesses）以及你可以向模型开放何种访问权限。例如命令行界面（CLI），能让你直接将企业业务系统与智能体对接。比如在 GPT-4 时代，我们写代码时通常是把代码片段复制出来，粘贴到 ChatGPT 中，尽量提供能想到的上下文，然后再把生成的代码黏贴回我们的编辑器。而像 **Cursor** 这样的开发工具之所以令人兴奋，是因为它扮演了强大的外围框架角色：它让模型能够直接访问整个本地文件系统，允许智能体自主判断并加载所需的上下文文件。因此，要让本地模型和本地系统发挥出更大的价值，核心就在于它们如何与真实世界进行无缝交互。

<details>
<summary>Original English</summary>

**Host**: Around there. Yeah. Yeah. That was a while ago. It's interesting to hear you say about the accessibility of that, right? The uh taking this Frontier intelligence, what made it useful was giving it peripherals, in this case, a camera so that it could access the data in front of you. And I think that's where the inflection point this year was so much more than just models, but also these harnesses and what you can give it access to. It was CLI so that you can give business systems uh and plug those right into your agent. It was uh you know 40 was really exciting because I was coding with it, right? I was taking code snippets from my codebase and then I'd go to chatgpt and I'd paste it. I'd give it as much context as I thought I should and then I would take the result and I'd go back to my codebase and paste it. And what was really great about tools like cursor was it essentially was this harness that said what if I just had the full file system and I can let these agents reason on what files they needed and so on. And so the way that you know you get more use out of all of these local uh out of all of these local models and systems is how does it how can it interact with the real world.

</details>

### 混合模型与预算控制

**主持人**: 我很好奇，Joseph，你们在计算机视觉领域起步很早。视觉领域其实很早就吃过语言模型如今正在面对的苦头。你认为现在语言模型世界正在发现的、我们可以借鉴计算机视觉的重大经验是什么？

<details>
<summary>Original English</summary>

**Host**: I'm curious um Joseph so you guys got the start in vision and it seems like vision had to learn the hard way what a lot of LLM are dealing uh discovering right now. What do you think is like a big lesson that the language world is discovering right now that uh we could look to vision for?

</details>

**Joseph**: 我觉得语言的一个天然优势是，它本身是人类的社会化产物。因此，只要有人类存在的地方，语言信息就天然存在，这也意味着你可以直接在数据中心里使用近乎无限的算力来处理它。然而，在计算机视觉中，你往往需要在没有网络连接、或者算力极为受限的边缘端设备上运行模型，比如在一个机器人上，你能支配的算力就是设备本身的物理算力。这种情况促使视觉领域很早就将重心放在了“专用模型”（Specialized Models）上，追求小而快。因为我们必须在受限的物理上下文中运行模型，不可能强求一个模型具备包揽一切的大一统能力，而是专注于特定领域的上下文。有趣的是，如今语言模型也在走向类似的道路。正如你刚才提到的各种特定上下文的外围框架。对于自主编码等特定任务，我们不再强求一个通用大模型解决所有问题，而是使用针对该任务深度优化的专用智能体。我们甚至在税务申报、法律文书准备等领域看到了类似的微调和专用化趋势。我认为，钟摆正在重新荡回“专用模型”这一端，无论是语言还是视觉，都在发生这样的变化。另一个方面则是关于如何在边缘设备和垂直应用设备上，通过极致的算法优化来压榨算力性能。不过，关于这一点，我想 ExoLabs 的朋友们应该更有发言权。

<details>
<summary>Original English</summary>

**Joseph**: I think um one of the things that language has an advantage of is it's inherently a human construct. So language generally exists where people exist and that also means usually you can use uh infinite amounts of of computer what is available in in a data center whereas a lot of vision uh you're computed. You're running maybe where there's low internet connectivity. You're running on a device. You're running on a robot and the amount of compute you have available to you is is what um is what you get. And so what did that do? So that created I think an emphasis on specialized learners faster because it's like okay I need this model to run in a limited context um and I'm not going to prioritize full world scale generalizability instead I'm going to have specialized in domain context work and what's interesting is I think you're actually seeing language follow a similar thing you're describing in the context of like harnesses for a given context um but you know tools like uh any sort of coding agent where you have a really good harness and it's specialized for doing those sorts of tasks but you're also seeing that even in like you know tax preparation or legal preparation of last mile fine-tuning adaptation specialized learners and so in some ways I feel like the pendulum swinging back to actually having specialized models even in language just as much as vision I think is one thing um and then you know there's a whole different thing around how you get the most out of compute optimization running on on a niche device um but I know that probably the exo folks can talk speak more

</details>

**Alex**: 确实如此。

<details>
<summary>Original English</summary>

**Alex**: absolutely

</details>

**Joseph**: 没错。在过去，人们普遍认为未来会是一个通用大模型统治一切（One model to rule them all）的世界。但现在钟摆显然又荡了回来，大家意识到专用模型的价值。

<details>
<summary>Original English</summary>

**Joseph**: um but yeah I think specialized models I mean, you remember there was like one model will rule them all world was kind of thought and I feel like the pendulum is swung back to people realizing special

</details>

**主持人**: 在 **NVIDIA**，我们非常确信未来会是一个“多模型共存”的世界，我们对这一点深表认同。事实上，今天下午 3:20 还有一个专门探讨“模型路由”（Model Routing）的圆桌，这非常令人期待。Matt，作为一名AI内容创作者和深度爱好者，你的实际日常使用模式是怎样的？你是否会同时调动多个模型？这具体是如何运作的？

<details>
<summary>Original English</summary>

**Host**: specialized models. I think we definitely at NVIDIA we see that it's going to be a multimodel world. We definitely agree with that. Um there's actually one of the panels that's coming on later I think at 3:20 p.m. is all about model routing and so that's that's really exciting. I guess as an enthusiast uh and as you use some of this is that uh how your usage pattern looks? Are you using many models? What does that kind of look like?

</details>

**Matt**: 确实如此。从最顶尖的前沿模型（如 Fable）到像 **Claude 3.5 Sonnet** 这样高效能的“主力模型”，再到不那么依赖极低延迟任务下的各种本地模型，我都广泛使用。在这个时间节点上，多模型混合架构显然已经是行业共识。特别是对于企业而言，一方面他们消耗的 Token 总量在爆发式增长，另一方面他们又必须严控预算。前几天，**Coinbase** 及其 CEO **Brian Armstrong** 发表了一篇非常精彩的文章，提到他们的 Token 消耗量呈现出指数级增长，但他们的整体资金开销却保持平稳。这正是因为他们采用了混合模型架构。你完全不需要在每一个细分场景都去使用最贵、最庞大的模型，实际上绝大多数场景都不需要。最典型的范式是：让最聪明的大模型去制定顶层的架构规划，而具体的代码编写和常规执行任务，则下放给性价比高得多的中小型模型去执行。

<details>
<summary>Original English</summary>

**Matt**: Yeah, absolutely. everything from obviously like the top models Fable uh to kind of the more workhorse models with Sonnet local models for things that maybe don't depend as much on low latency. Um yeah, like the multimodel world seems like a no-brainer at this point. uh especially as you're seeing all these enterprise companies come out and look at their budgets and and think, okay, well, I I need to continue to increase the the total number of tokens that I'm consuming as a company, but I also don't want to just completely blow out my budget. I know Coinbase and Brian Armstrong just came out with that just great post the other day talking about uh how their tokens are are exploding yet their costs are staying flat. And and that is because they're using a mixture of different models. You don't need the top model for every single use case and in fact most use cases you don't uh I think the most obvious application is let the top model plan uh the the architecture whatever the kind of top level plan is and then the actual execution of the code can go to uh a more reasonably priced smaller model.

</details>

### 自主迭代与本地算力

**主持人**: 让最聪明的模型来负责全局规划，再将具体的子任务分派给更小、更快速的“执行者模型”——这毫无疑问代表了未来的发展方向。

<details>
<summary>Original English</summary>

**Host**: Your most intelligent should provide you with the overall plan and then subtasks for your smaller executioner like executioner models and that's exactly the future.

</details>

**Matt**: 没错。特别是在本地场景下，本地模型在辅助编写具体代码方面表现出色，但我们可以把顶层的复杂系统设计交给云端的前沿大模型。这不仅能帮你节省巨额成本，还能让你更好地掌控整个工作流。这是一个非常优美且实用的设计模式。

<details>
<summary>Original English</summary>

**Matt**: Yeah. And especially like you know we're talking about local um local models are great at writing code but maybe we offload the actual top level planning to one of the frontier models and you you save a bunch you control more of the workflow. It's it's a it's a nice pattern.

</details>

**Alex**: 是的，我认为市场和客户非常渴望这样的方案。几年前这项技术刚萌芽时，前景还不太明朗，大家当时都在猜未来是不是只会剩下一个垄断性的大模型。但很明显，这并不是用户想要的，更不是企业客户想要的。企业不希望被任何闭源巨头牵着鼻子走，被动接受其规则。他们也不想在所有的工作负载上都使用每百万 Token 售价高达 50 美元的庞然大物，因为很多基础任务根本不配使用这么昂贵的算力。企业需要的是自主权、技术主权，以及自由切换不同模型的能力。他们不希望因为突如其来的安全策略调整或接口下线而在一天内被无情地中断业务。这种对自主权的强烈需求，正是推动目前本地化和开源化快速发展的主要动力。因此，我对本地 AI 的发展比以往任何时候都更加乐观。市场正在强力拉动这方面的技术演进，无数初创公司和大型企业都在围绕这个生态构建自己的解决方案，这场变革正在实实在在地发生。

<details>
<summary>Original English</summary>

**Alex**: Yeah. I I think the market wants this. So it wasn't clear like a few years ago when this stuff was just starting to play out, you know, would there just be one big model that everyone is using? But clearly that is not what people want. That is not what enterprises want. They don't want to be told what they can do by Dario. They don't want to be paying for the same model for all their workloads when some some workloads don't actually need, you know, a giant gigantic model that costs $50 per million tokens. Um, they want control, they want sovereignty, they want the ability to switch out models, they don't want to get rugpulled, you know, uh, from one day to the other, uh, because of some safety risk or whatever. Um, and you know, that's really what's driving a lot of this progress. So, you know, I'm more optimistic than ever, I think, about sort of, you know, where things are going with local. I think that, you know, the market is basically pulling a lot of this stuff um out of, you know, startups, out of enterprises are building solutions around this and, you know, it's it's yeah, it's it's happening, right?

</details>

**主持人**: 完全如此。这确实是一个全新的前沿课题。当我们走向多模型架构时，复杂性呈指数级上升。你不仅需要智能地在模型之间进行路由，还必须弄清楚如何将必要的上下文数据分发给你路由到的特定模型。如果你制定了一个复杂的顶层规划，并将其拆解给若干个子智能体去执行，这其中的协同框架是什么？我们究竟该如何实现它？这些目前都是行业内悬而未决的开放性问题。我认为保持开放和乐于尝试的心态是现阶段最好的应对方式。但我非常赞同你刚才的措辞，即市场正在强烈呼唤并拉动这些答案的出现。大家都在朝着这个方向努力。我们非常期待有更多的初创公司来填补这一技术生态空白。这非常有道理。还有一件很有意思的事：任何企业在采购和部署软件时，版本控制都极其重要。如果你要在其上构建核心业务，你必须确切知道所运行模型的版本，以及这个版本是否发生了改变，否则你无法预测系统后续的行为变化。因此，企业需要拥有对整个技术栈的绝对控制权，明确锁死特定的模型版本，不能接受其在后台被悄悄更改——这甚至与合规监管无关，而是出于系统稳定性的底线要求。企业需要自己决定何时对整套技术栈中的哪一个组件进行升级。

<details>
<summary>Original English</summary>

**Host**: Totally. I feel like this is a new frontier where as we go multimodel, that becomes really difficult. Of course, you need to route between the models, but then you have to figure out how to provide necessary context to whichever model you're routing to. If you were making a plan and then breaking it off into sub aents, what is the framework to do? So, how should you do this? These are all open problems. And, you know, I think just being playful is uh kind of the best way to to approach this. But I like the way that you worded that of like uh the market's kind of pulling for these answers. It's reaching in this direction. We're looking for startups and companies to fill this gap. Um, makes a ton of sense. You know what's funny? Um, as any any enterprise consumes any piece of software, it matters a lot. If you're going to build a foundation, you want to know what the versions are. You want to know what your model is, which whether that version changed in order to see change behavior later. So having uh also more control over all of this so that you know exactly what version it is, it can't be changed. Uh not even because of any sort of you know regulation, but just simply if there are updates, you choose when you're opting into whatever it is on your entire stack.

</details>

**Ahmed**: 没错。当您观察我们正在见证的这一波被称为 AI 的“文明级基础设施”浪潮时，你必须考虑那些可能被剥夺的权益以及你的主权。你必须思考，如何才能全栈端到端地掌控属于你的技术资产——这涵盖了硬件、软件，以及介于两者之间的一切。这里最关键的就是**模型权重（Model Weights）**。就像刚才所说，是模型的具体版本，以及你如何微调它。结合刚才 Joseph 提到的小型专用模型，我其实在很久以前就是这一路线的坚定拥护者。我曾在 2024 年发推特明确指出：小而专的模型才是未来的主流。企业会根据不同的工作流和使用场景来挑选最适配的垂直领域模型。企业现在就需要开始着手布局，因为你需要收集真实业务运行的数据轨迹（Traces）。主持人，这就是你刚才问到我们如何实现模型路由、以及如何决定将哪个任务分发给哪个端点或模型的关键所在：你必须收集实际运行数据。企业需要分析员工在实际工作中使用智能体留下的每一次调用记录（Traces），并基于此进行持续微调。而且，你完全可以通过智能体本身来自动收集这种反馈和数据。这就是关于**递归自我提升（Recursive Self-Improvement, RSI）**在企业工作流和智能体框架中的应用。也许我们可以为现场还不太了解 RSI 的朋友简单科普一下。

<details>
<summary>Original English</summary>

**Ahmed**: Yeah. Uh so [clears throat] when you think about um this wave that we're seeing here of like this civilizational infrastructure that is called AI you have to consider the potential of you know things being taken away from you and your sovereignty and uh how can you be in charge of you know this thing full stack end to end that's hardware software and everything in between That's the model weights. That's the specific version of the model as you were saying. That's how you fine-tune it. And picking up on Jos's you know thing um statement here [clears throat] about small and specialized models. I have been like, you know, I have been a proponent of that for quite some time. I I have tweets about that in 2024 saying small and specialized models are the future and it is going to be very user by per use case per workflow for businesses you know to to decide on their niche domains and you need to start on boarding them now because you want to collect the data points that races that's what you're asking about N you're asking about how do we get there how do we decide which model gets routed to how do we decide which use case gets goes to which model or which endpoint you You need to collect data and you need to be ready to basically break down um the traces that you've collected from your employees from everybody in your organization and decide how can we make the most optimal use case of these data points to which models and collect feedback as well and you can actually automate that with agents as well. So like this is like something that it's you know the the whole thing about RSI right now recursive self-improvement it also applies to even agents and harnesses and to to workflows and to use cases and to enterprises. You want to describe that for everyone too maybe for folks who don't know RSI

</details>

**主持人**: 好的。递归自我提升（RSI）简单来说，就是模型可以自主租赁算力，在本地或云端开始训练自己的模型检查点（Checkpoints），然后自己部署升级后的下一个版本，自我修正和优化其行为。换句话说，就是模型自己训练并提升自己。

<details>
<summary>Original English</summary>

**Host**: uh recursive self-improvement it means that uh a model would basically rent its own compute and then start training its own checkpoints and then you know uh deploy it its next version so that it gets updated in certain ways change its behavior in certain ways so basically a model is training itself

</details>

**Ahmed**: 没错。针对我们的产品 **Brev**（注：GPU算力租赁平台），它的定位是让开发者能够极其便捷地获取 GPU 算力。最近我们发现，智能体本身正在成为我们的核心用户群体。我们注意到越来越多的调用来自于自主运行的智能体，它们会直接根据任务需要，自动接口调用来租用我们的 GPU 算力并进行自我迭代。

<details>
<summary>Original English</summary>

**Ahmed**: totally for our product brev which just makes it really easy to get a GPU we've been focusing more on agents as a first class audience because we're seeing this so we're seeing growing usage from agents that just want to go grab a GPU uh directly.

</details>

**主持人**: 确实如此。

<details>
<summary>Original English</summary>

**Host**: Exactly.

</details>

### 硬件性能极致优化

**主持人**: 没错。回到刚才说到的第二个关键点：除了多模型混合架构，还有在边缘端（非数据中心）算力受限情况下，如何实现极致性能优化的底层工作。Alex，这正是我们两家公司近期开展的非常有趣的一项合作。Alex 甚至把他们公司的临时第二总部直接设在了 **NVIDIA** 总部内部。我们当时在一个会议室里，一起吃晚餐时，他提到他非常渴望能够压榨出 **DGX Spark** 这款设备的每一滴性能水分。于是我们说：“嘿，那干脆在我们 NVIDIA 腾出一个专用会议室，把你的研发团队带过来。只要你们在开发过程中需要任何技术领域的专家支持，我们随时去把对应部门的人直接拉进会议室协同战斗。”

<details>
<summary>Original English</summary>

**Host**: So yeah, you know, it's funny. So the second thing you talked about was not just multimodel but then all these optimizations to actually run it performant when you have less compute than in a say data center. I think Alex this is some fun work that we did. So um Alex has actually set up a second headquarters inside of Nvidia. we got a conference room and uh we were we were having dinner and he mentioned that he really was motivated to get to squeeze out every drop of performance we could on the DGX Spark and so we said hey let's get a conference room at Nvidia come bring your team and anytime you need an expert across any pillar let's just go and pull that person into the room and yeah

</details>

**Ahmed**: 对，我也想补充一下。因为我长期参与 **r/LocalLlama** 开源社区的运营，当我观察那些硬件发烧友、折腾“家庭实验室”（Home Lab）的极客时，我深知这些人其实很多就是大企业里坐在会议室制定 AI 战略的技术骨干。家庭实验室极客们最关注的核心就是“优化”（Optimizations）——即如何在给定的硬件、软件和物理限制下，榨取最大的经济价值。行业内之所以会诞生并普及**模型量化（Quantizations）**技术，就是为了在物理内存受限的约束下强行跑起模型。对于企业级应用而言，面临的本质上是完全相同的物理与财务约束。这纯粹是一个算力约束和预算上限的问题：如何利用现有的硬件资产获得最高的 Token 吞吐量？无论你是在中小型企业内部署一台 DGX Station，还是运行一个庞大的 GPU 集群，核心命题都是如何针对最新的前沿开源大模型去调优你的软件栈，从而在经济效益的约束下获得最大回报。因此，关注家庭实验室发烧友的动向是至关重要的。本地 AI 绝仅限于你个人电脑桌面，它可以是企业私有化部署的服务器、托管硬件，也可以是租用的算力集群。它代表的是一种“端到端掌控一切”的哲学——从硬件底座、软件框架、API 端点，一直到模型权重。通过完全掌控这些，企业才能收集独有的业务运行数据，进而微调出更小、更高效的专属模型。本地化的未来极其广阔。

<details>
<summary>Original English</summary>

**Ahmed**: I I actually have a follow-up here uh so since I have been part of local llama for quite some time um when I think about home labers I think about the individuals that are actually are within enterprises on boardrooms making decisions about you know the models that we're going to host or you know where we're going to get our AI from. Uh the things that these home labers focus on are optimizations. It's basically how can I extract the most economical value out of the hardware the constraints that I have the software that I have. You know quantizations came to be because of that. When we're thinking about enterprises it's the same thing. It's constraints. It's budget limitations. It's how can I make the most use of the number of tokens that I can get under the hardware that I have. Whether that's a DGX station, you know, um centrally in a small medalsized business or, you know, a DGXP300 cluster, it's all about how can I optimize the software for the latest and greatest frontier opensource model out there and get as much value as possible out of it under the economical constraints that we have. I think it's it's crucial to see home labers and that's why you know this is local AI it's local AI but it could it could be on premises it could be colloccated hardware it could be rented clusters it could be from brev basically it's just the idea about controlling this thing end to end from hardware to software to model endpoints to model weights and you know collecting all of that data to train your specialized and smaller models that will be more efficient as as you go. Um yeah, the future is great and the future is local. [laughter]

</details>

**主持人**: 哈哈，说得太好了。数据、权重和算力全归自己所有。在这个合作案中，我们最终成功将模型在 DGX Spark 上的推理性能提升了 **10倍**。我们随后向 Jensen（**黄仁勋**）及 NVIDIA 执行委员会和所有提供协助的团队发送了更新邮件。我在邮件中特别喜欢的一句话是：“为了实现这 10 倍的性能飞跃，我们其实并没有去攻克任何全新的计算机视觉或计算机科学难题。我们只是把 NVIDIA 内部各路技术专家早已解决并公之于众的碎片化技术成果，有机地融合在一起，编织成了一束美丽的‘花束’（Bouquet）。”我认为这恰恰说明了本地 AI 在易用性（Usability）和整合度上面临的挑战。现在大家都看到了本地 AI 的强大能力，但你认为阻碍大家真正全面落地本地 AI 的，仅仅是模型能力问题吗？还是有其他原因？

<details>
<summary>Original English</summary>

**Host**: Yeah, absolutely. Um you know, making sure it's your dates, your your weights, your compute. I think one thing that was really interesting, we did end up getting 10x performant improvements on the DGX Spark and we sent an update to Jensen, to the executive staff, to the teams that were helping. And one line I really liked in that email was that we didn't solve any new computer science to do this. We actually took things that the experts at NVIDIA had already solved and was out there. And I think what we worked together to do really nicely was assemble it in a bouquet. And I think that speaks to some of the the usability here, right? We're talking about what is capable. What what are the capabilities? But do you feel like it's just capabilities that are holding people back from adopting this?

</details>

### 用户体验与降低门槛

**Alex**: 哈哈，我来还原一下当时细节。我们周四晚上一起吃了晚饭，然后周五你就发出了这封邮件。当时提出“我们联合搞个实验室吧”的时候，我觉得这简直太疯狂了，认为根本行不通。但是 Nata 说：“没问题，我们去把 NVIDIA 内部各路大牛拉进来协助你们，咱们在 Spark 上把推理性能搞上去。”我当时心想，如果真能做到那当然太好了。那封邮件几乎是当晚就发出了，周五时 Nata 跟我说：“周一早上准时到 NVIDIA 总部报到，我们会组织各个部门的专业团队在会议室等你。”周一我们一到总部，就深刻体验到了 Jensen 经常提到的“蜂群作战”（Swarming）概念。基本上就是一旦公司确立了某个紧急目标，整家公司会立刻打破部门壁垒，全员迅速动员并合力包围它。

<details>
<summary>Original English</summary>

**Alex**: Yeah. So just to tell the story a little bit what happened here. So I think we had dinner on Thursday of the week and then you know an email got sent out on Friday. So this idea came up like why don't we do a lab, right? Why don't we like you know this to me sounded crazy at the time. I didn't think this would be possible but it was like you know let like Nata was like oh let's like get a bunch of people from Nvidia to help you guys and work with you guys to improve the performance on the spark right and I was like okay like let yeah let's I mean if we can that would be great. Email got sent out I think pretty much that night and then on Friday Nata told me be here on Monday um at NVIDIA HQ. uh we're going to have you know teams of people here that are going to work together with you on this and you know turned up on Monday and uh Jensen talks about this concept of swarming. Uh it's you know basically the idea that uh the the whole company will like mobilize around something.

</details>

**主持人**: 哈哈，你见过小孩子们踢足球吗？一旦球滚到哪里，所有孩子就会瞬间一窝蜂全部围上去抢球。NVIDIA 的蜂群机制就是这样。

<details>
<summary>Original English</summary>

**Host**: Have you ever seen little kids play soccer? There's a ball and everyone just attacks it. It's like a tackle. It's just the mit of the soccer ball.

</details>

**Alex**: 确实如此！我以前只听说过这个概念，但从未亲身经历过。那一天我们几乎是连轴转，会议室的门就没关过，各路团队的人员进进出出。比如 **Nemotron** 核心团队、数据中心底层优化团队、**VLM**（视觉语言模型）推理加速团队等等。我惊奇地发现 NVIDIA 针对每一个细分技术点都设有专门的团队。他们甚至有一个专门叫作“DGX Spark 多模态优化”的团队，这定位精准得让人不可思议。我们成功调动了这些宝贵的智力资源，在短短三周内，我们就实现了 **10倍** 的性能爆发。而在那之前，NVIDIA 自己的测试底座运行的是基于 **Hermes Agent** 的常规方案。我们引入了 **TensorRT-LLM**（VLM推理后端）做深度重构，完成了大量关于低比特量化和算子微调的工作，使其更契合本地端设备的运行特点。NVIDIA 在硬件设计上非常明智的一点是：其本地端硬件（如 DGX Spark）与数据中心级硬件共享完全相同的底层架构，那就是 **Grace Blackwell**。因为架构同源，我们得以“免费”享受到大量成熟的底层基础设施和极佳的算术内核（Kernels）。但问题在于，很多现成的配置默认是专门为数据中心的多卡节点设计的。所以我们的核心工作并非从头造轮子，而是把这些数据中心的顶尖调优参数，精准适配到 DGX Spark 这款桌上设备上。这台机器虽然小到可以放在你的办公桌上，但它拥有货真价实的数据中心级怪兽性能。我过去几年的最大感悟就是：硬件基础设施其实早已准备就绪，而且模型的算法压缩和量化技术也在以惊人的速度进步，使得我们在更小尺寸的设备上可以塞入能力极强的模型。只要有更多优秀的工程师投身于此，我们就能创造奇迹。就像我们此时此刻在展区展示的演示一样：**Nemotron-3 Ultra**，一个拥有 **5500亿参数（550B）** 的超大模型，在四台桌上型 DGX Spark 上实现了每秒 **30个Token** 的高速输出。

<details>
<summary>Original English</summary>

**Alex**: Yeah. And I had heard about this idea, but like I'd never experienced it. And I can tell you like we were just back toback that whole day. People coming in and out of the room, you know, from all various teams like the Neatron team, um, you know, people working in in on data center stuff, people working um on VLM. I I realized, you know, Nvidia has a team for everything. So there's like a VLM for Spark team which is oddly specific but like you know they have all these teams and you know we basically got to pull those resources in and you know you know in those three weeks or so as you mentioned like we basically got 10x performance versus you know what um Nvidia had running on the spark um in their existing playbook which was using Hermes agent. So we we did a bunch of optimizations there um using VLM um as the the sort of inference back end there. Uh doing a lot of work with the like tuning the models like quantizing the models uh to you know be fit for local. So what you'll find is I think one of the great things Nvidia has done with the local hardware is it's the same architecture that's running in the data center as running on the spark. So it's Grace Blackwell. Um so the hardware is like fundamentally the same meaning you actually get a lot of things for free. So for example like the kernels are already really good. However there is like a lot of tuning and a lot of like configuration that is right now designed specifically for the data center. So a lot of the work that we did was not like inventing anything new but it was actually just tweaking things to work uh more performantly on the spark. And you know the hardware is extremely capable. It's like you know it is data center level hardware that's literally can sit on your desk. Um so it's just about like you know how do we activate that and I think this has been one of my learnings from the last few years is like we already have the hardware like the hardware is already really good and you know the models are getting better. Um they're getting a lot better at compression so you can fit more on a smaller device. So like you know I think it really is just a matter of more people looking at the space and working in it and you know we will be able to do amazing things like we have you know neatron 3 ultra it's a 550 billion parameter model running on four sparks over there 30 tokens per second so like

</details>

**主持人**: 这确实是一个巨大的突破！

<details>
<summary>Original English</summary>

**Host**: that's that's huge

</details>

**Ahmed**: 我想插一句。看到开源社区展现出如此强大的主动性真的太棒了。比如 Alex 和他的 Exo 团队，他们作为社区的一员，正致力于将开源智能推向新的高度。我也非常赞赏 NVIDIA 积极携手社区开展这样的合作。在我看来，目前的本地 AI 领域非常像上世纪 90 年代初期的 **Linux 操作系统**——一切才刚刚破土动工，大量底层的生态基础设施还很不完善，我们仍有非常漫长的路要走。我之前也和 Alex 讨论过我们该如何协作。我们开发了一套名为 **ODS** 的开源部署系统，它整合了许多优秀的开源工具，开发者只需在对应硬件上运行它，它就能自动完成硬件检测、环境配置、Agent 初始化，并端到端地在本地搭建起一套完整的智能体基础设施。我们需要将这种一键式部署工具针对市面上的每一款主流硬件进行极限优化，只有这样才能降低普通用户的上手门槛，让开源和本地化生态实现爆发式增长。这正是我们今天聚在这里的初衷：让每一个人都明白，本地和开源 AI 可以运行在任何设备上——从你手中的智能手机，到 Alex 提到的桌上型 DGX Spark，再到数据中心级的大集群，并且它们完全能为你提供不亚于最强闭源大模型的前沿智能体验。

<details>
<summary>Original English</summary>

**Ahmed**: I want to say something here like it's it's so great to see the community being proactive I think of Alex Gmail right here who's exo as somebody who's member of the community who's trying to push the frontier opensource intelligence to the next level. I love how Nvidia is working with them on that. When I think about, you know, this space, I think we're in the '9s of the Linux operating system and we are like just starting. The infrastructure is not there yet. We need so much more. Uh I was even telling Alex, I want to see how we can collaborate. We have like an open source uh uh deployment system called ODS that is a bunch of open source tools that we deploy in each hardware. It configures stuff, configures agents and basically uh gets you set like you know get gets you set up with the entire infrastructure end to end that you need for your agents locally. This kind of stuff we need that optimized for every piece of hardware out there so that we can get more and more people on boarded have the open source adoption you know just go to the moon. That's what I want right now. This is why we're here. We want everybody to know that local local and open source AI can run on anything starting from your phone to your DJX Spark as you're saying Alex to DJX stations to the next level in the data centers and it will deliver you frontier level intelligence.

</details>

**主持人**: 说的太好了。Matt，对于你我有一个非常好的问题。你一直在面向主流科技受众测试各种前沿AI工具，且你自己也是深度用户。在你看来，对于普通的大众用户而言，目前的本地 AI 还有哪些最致命的短板？

<details>
<summary>Original English</summary>

**Host**: Yeah, absolutely. I think this is a really good question for you Matt. You know you test everything for a mainstream audience. You're hearing about all of this technology. You're using this aggressively. Where does it still fall short for the average user for AI?

</details>

**Matt**: 好的，我认为需要分两个层面来思考：个人普通用户和尝试引入开源 AI 的企业用户。核心痛点在于：它必须变得像“打开 Cursor”一样简单傻瓜。甚至可以说，它的部署复杂度应该只比“安装一个视频播放器解码器”稍微难那么一点点。但平心而论，目前的技术现状离这个理想状态还非常遥远。尽管台上的技术大牛们做出的成果极其惊人，但其底层逻辑和配置过程对于包括我在内的绝大多数人来说，依然太过繁琐和难以掌握，更别提没有专业IT背景的普通企业客户了。

<details>
<summary>Original English</summary>

**Matt**: So I I think about [clears throat] two things. The average kind of personal user then the average enterprise using uh open source. I mean it's it it needs to basically be as simple as opening cursor. It needs to be maybe slightly more complicated than that or slightly more complicated than just installing codecs and opening it up. Right now it to be fair it is quite far from that. it like the the stuff these guys are doing is incredible, but it is more sophisticated than what most people including myself are going to be capable of. Um, you know, let alone a business. Uh, I think

</details>

**Ahmed**: 确实，如果没有一键式自动化工具，仅是折腾环境和调优就足以成为一项全职工作了。这就是我们必须通过软件实现完全自动化的原因。

<details>
<summary>Original English</summary>

**Ahmed**: a full-time job to just do this kind of stuff. That's why we need to automate it.

</details>

**Matt**: 没错，它必须是“点一下就能用”的。虽然目前社区里涌现出了很多非常优秀的项目在朝这个方向努力，但我们依旧没有跨过那道门槛。此外，要想让本地 AI 走向主流，我们必须帮助用户清晰地理解：什么样的业务场景应该搭配什么规格的模型、什么样的主力框架、以及什么样的硬件算力。用户需要明确知道我家里的一块 4090 显卡能带来什么、或者从云端租用算力能解决什么，这种场景匹配逻辑对于大众用户来说极其重要。

<details>
<summary>Original English</summary>

**Matt**: And it it really does need to be point-and-click. And once it gets there, and there's there's a lot of great open source projects, there's a lot of great projects in general that are getting there, but we're still not quite there. Uh the other thing to make it widely adopted is to allow people to better understand what use cases are appropriate for what what type of model for what type of harness what type of hardware knowing exactly the use case that I can get out of my home system or something that I'm I'm you know renting from uh service center uh that that is incredibly important as well

</details>

**Ahmed**: 而且这种场景匹配和优化配置不应该仅仅写在复杂的开发者文档里。这是目前开源项目最令人头疼的地方。它应该做到开箱即用，由系统在后台自动检测硬件并匹配最优策略。这正是 ODS 系统的核心愿景，也同样是 **EXO** 项目的初衷。随着我们不断完善这套本地基础设施，我们必须将用户体验放在第一位，要考虑普通用户的感受，而不是仅服务于我们这些技术人员。虽然我们在座的都是参加 AI 开发者峰会的专业人士，大家对命令行和各种配置驾轻就熟，但广大的 ChatGPT 用户和习惯了云端服务的用户，他们需要的是一个没有任何门槛的替代方案——点一下运行，发送消息，智能体开始工作，任务搞定。

<details>
<summary>Original English</summary>

**Ahmed**: and I I think it shouldn't be just in documentation. I think that's where open source becomes so difficult for people. I think it needs to be a point and click and it figures it out on its own. That's what ODS is about. That's what I think EXO is about. That's what you know as we grow more and more and building this infrastructure, we need to be thinking about the user experience for your average everyday user, not us as technical folks here because this is AI engineering um you know summit and I'm pretty sure that we all can manage our way around this stuff. But your chat GBT users, your cloud users, whatever out there, they want this to be an alternative that is just click play, send a message, use an agent, and done.

</details>

### 知识蒸馏与场景定制

**Matt**: 没错。大部分用户真的不想知道底层的物理细节，他们只希望工具能直接运转。不管是集成在 Cursor、**Codex** 还是其他开发工具中，只要它表现得完全无缝，用户根本不需要操心它，这对绝大多数人来说就是第一诉求。

<details>
<summary>Original English</summary>

**Matt**: Yeah. Most most people really don't want to know about the details. They they just want it to work. And even if it worked seamlessly within cursor or codeex or any of these other things and it just worked and they didn't have to think about it, that is number one uh that for for the vast majority of people. So [clears throat] interesting on that in a multimodel world where we have to pick a model do you think that that's something that is a product um as we're or is that is that plumbing is that something

</details>

**主持人**: 既然我们在走向一个多模型世界，必须去选择和调度模型，那么你认为这种“路由”决策应该是作为一个上层产品功能呈现给用户，还是应该作为底层的某种“管道”（Plumbing）机制被彻底隐藏起来？

<details>
<summary>Original English</summary>

**Host**: matter you talked about the harness it's exactly that it should be some like whatever the kind of the front entry point to somebody's AI experience is that should be what is choosing which model at the right time for the right use case this is a very difficult problem there are you know open source projects closed source uh companies building routing That's only one piece of it, right? So, go ahead.

</details>

**Matt**: 它应当作为外围框架（Harness）的一部分被隐藏。当用户开启他们的 AI 体验时，前端的入口点应当在后台根据当前的具体任务，在正确的时间自动去匹配和调度最合适的模型。当然这在技术上极其困难。目前有很多开源项目和闭源商业公司在做模型路由，但这也仅是整个拼图的其中一块。

<details>
<summary>Original English</summary>

**Matt**: No, like Carter from Nvidia, he's he's going to be a moderator here. Hey, Carter. Uh, looking good, man. So, um, he I I I shared ODS with him and he told me, I love how like it immediately downloaded that two billion parameter models allowed me to start playing with it and then it started downloading the next model that would work perfectly on on my device. That's the kind of experience we need to be giving these users when they we're on boarding them. Don't make them sit down and have to think about all these quantizations and all these extensions and all these weird things. That is too much work for your average user. That's how we lose them.

</details>

**主持人**: 哈哈，确实是这样。以前在单一大模型时代，因为模型足够大且通用，用户其实不需要对业务场景有太深理解，直接提问就行。但在专用模型时代，既然是“专用”，你首先就必须清晰定义你的业务到底是什么。Alex，能结合你们的实践，聊聊企业如何过渡到专用模型？在这个微调和构建过程中，你们遇到了什么？

<details>
<summary>Original English</summary>

**Host**: Mhm. Yeah. It's interesting, right? Like the when you're not having to deal with multimodel and you have just this generally good but big model, you can kind of ask anything. You don't have to be as sophisticated or you don't have to understand your use case too well. But as we talk about specialized models, if you're going to specialize in something, you need to know what that something is. And so the amount that I mean can you guys speak to maybe what it's like to move into a specialized model or to build one or have you have you

</details>

**Ahmed**: 好的，我可以先聊聊这个问题。在云端 AI 时代，你获得的实际上是一个基于所有人反馈平均值构建的“正态分布”模型。云端巨头在训练和微调模型时，收集的是全球无数用户关于回答满意或不满意的宏观反馈。但当我们谈论企业私有的“小而专”模型时，由于训练和存储这些微调权重需要消耗大量的算力和存储资源，这就要求每一家企业必须深度聚焦于自己独特的业务模式、工作流场景，去分析员工是如何与智能体交互的。这是一件非常个性化的事情，无法被简单套用和泛化。这就是为什么目前前沿大模型公司很少提及**持续学习（Continual Learning）**这一概念，因为这是本地端设备才能真正解决的问题。未来本地 AI 不仅是将历史对话保存为 Markdown 格式，因为随着业务时间推移，不断膨胀的上下文窗口会变得极其低效。智能体演进的终点必须是直接将新知识融入模型底层的权重（Weights）中，而这种高频的权重更新必须在本地端设备上安全地完成。

说到这里很有意思，几个月前 Swix 发过一条推特，问为什么“微调即服务”（Fine-tuning as a service）一直没有真正爆发？我认为很大原因在于模型自定义（Customization）本身是一个极高门槛的硬核问题。此外，你可以随便修改的开源底座模型也并不多。这正是 NVIDIA 致力于发布 **Nemotron** 的原因——它是一个彻底开源的生态模型，不仅开源了模型权重，还把训练数据集、微调配方（Recipes）和完整的技术路径全部开放出来，就是为了让企业和开发者可以真正安全且自由地去进行定制和微调。

<details>
<summary>Original English</summary>

**Ahmed**: I can start with that. Uh on the cloud uh you're basically getting the normal distribution. So every time that they are training something they are taking the average feedback from everybody when they are being happy or sad or like you know um they are okay with the answer or hey no this is not what I meant go back or change the model and answer with a different model. That's the kind of feedback that allows you, you know, cloud providers to fine-tune the next model. But if we're talking about small and specialized models for use cases, that's a lot of compute to train models. That's a lot of um storage for these weights. Uh that does not happen without each use case or each business entity etc. focusing on their own um patterns and use cases and like how they handle agents and how their employees uh message these agents and what workflows they're interested in. So it's really you know it's per use case it's per entity it it's not something that we can just generalize and that's why you know continual learning is not being talked about by the frontier model uh as much it's coming though it will happen and it needs to be running on local hardware for it to happen. That's how you can have something that is so optimized that is not just plotted markdown files sitting in one rebel and you know you think that that agent is not going to lose track of which skill to update or what to edit or which memories to update because at some point context lens becomes inefficient and that's one issue that's the current paradigm of agents is basically just saving to markdowns the next one will be updating the weights and that needs to happen locally. Yeah, there's it's funny too because you know uh there was a tweet I think by Swix uh that was like why has fine-tuning as a service not taken off. It was like a couple months ago. Um and I think a big reason for that is that model customization itself is also a very hard problem. And then what models can you hack on? Uh that's I mean that's why Nvidia releases Neotron. It's a open source model but everything from the dates sorry the data to the weights to the uh the recipes for how to do so and then of course you know the final model everything is open sourced um just so that it is a model that you know you can safely uh use and customize

</details>

### 多模型协同与数据蒸馏

**主持人**: 这确实很有意思。我在这件事上的立场也经常摇摆不定。很多人认为通用大模型的能力已经极其强悍，只要你在 Prompt 中提供足够精准的上下文（Context），其效果是否就已经好于耗费巨大心力去训练一个微调模型？我经常在这两种路线上反复权衡。因为部署多个极其小巧且高度专用的模型并让它们协同工作，在处理特定业务时确实具有难以抗拒的成本和性能优势。对此大家怎么看？

<details>
<summary>Original English</summary>

**Host**: you know it's interesting I keep kind of flip-flopping on this point I think people look at how good the generalized models are and you give it the right context is that going to be better than than having a fine-tuned model and all the work that comes with that And I I keep going back and forth because there is a lot of value in being able to have kind of a smaller very specialized model and and maybe a bunch of them working in unison to accomplish whatever task you have. Um but I I yeah I'm not sure what what do you what do you guys think about that?

</details>

**Alex**: 如果我能补充一点的话，我认为开源生态系统最美妙的地方在于，它可以让所有的技术路径并发地被探索，市场会最终筛选出获胜者。这非常像最近在**推测性解码（Speculative Decoding）**领域发生的故事——即利用一个小模型去预测并加速大模型的推理生成。就在上周，行业内几乎在同一时间从不同的团队涌现出了三个重大的推测性解码突破：一个来自于 DeepSeek，另一个来自于 Modal 团队和 **SGLang** 团队，他们为 **Qwen** 系列模型构建了全新的 Draft 模型，大幅提升了推理吞吐量。在开源生态里，我们可以看到各种技术创新在快速迭代，最终最优秀的那套方案会自然脱颖而出并惠及所有人。

<details>
<summary>Original English</summary>

**Alex**: Um, if I can chime in on this one, like I think the the beauty of like the open source ecosystem is that like all of these paths kind of get to be explored and then whatever wins like you know it's it it's like what happened with speculative decoding um you know there's all these like different ways of doing speculative decoding which is this idea that you can use a smaller model to basically approximate a larger model to speed it up. Um and you know you've seen like recently literally I think in the last week there's been like three different like quite you know seem to be breakthroughs in like speculative decoding that have just come from like different places. One from deepseek um there was some work that was done by like modal and uh the SG Lang team to like build uh Dlash draft models for like various Quen models that are like a big improvement on the previous ones. um there's like all this work being done and so like we kind of get to see like all of it and you know basically like whatever ends up being the best thing will just be the thing that kind of right.

</details>

**主持人**: 这是一个很好的观察。也许最终绝大多数普通用户和企业并不需要亲自去微调属于自己的模型，而是由某些面临特定痛点的团队微调出来并以开源方式贡献出来，其他人直接“拿来主义”直接采用即可。比如如果我需要为某个特定垂直场景生成图像，我直接去开源社区寻找现成的 **LoRA** 权重即可，这在早期的图像生成生态中已经非常流行。终局来看，终端用户只关心两件事：它能不能解决我的具体业务问题？以及，它的成本是否在我的预算之内？

<details>
<summary>Original English</summary>

**Host**: That's a great point where maybe it's not users and consumers actually customizing their own models and using the specialized models but someone who has a need does so and does so in an open source fashion so that someone else can just adopt it. Right? If I'm going to start to do image gen for a particular use case I can just go find a model. Actually we saw this a lot also with like early Lauras on like a lot of image gen models. I feel like that was really big as you know in the 40 era as well. I think ultimately what the end user cares about is does it solve my use case and can it do so within my budget

</details>

**Matt**: 确实是这样。如果有某种服务或者框架可以全自动帮我把整个微调和优化流程打通，让我不需要去操心那些底层的技术细节，那就太棒了。我知道我刚才一直在强调“不想操心”，虽然我平时工作中也会去思考很多复杂问题，但在这个特定场景下，我真的不想再增加额外的认知负荷了。

<details>
<summary>Original English</summary>

**Matt**: and if there's another service that can manage the entire fine-tuning process and and I don't have to think I know I keep saying I don't have to think about it sometimes I do think about things but like in this specific use case um

</details>

**Ahmed**: 哈哈，因为大家平时需要考虑的事情已经够多了，没必要再去增加负担。

<details>
<summary>Original English</summary>

**Ahmed**: thinking about too many things already to add one more thing to

</details>

**Matt**: 没错！我只需要聚焦于我自己的核心业务，我不希望每天去研究推理后端或者权重版本怎么升级。我希望这些底层细节能被完全抽象并隐藏起来，让我能够把精力百分之百放在业务上。

<details>
<summary>Original English</summary>

**Matt**: like I I care about my business I don't want to think about the uh I want it to be abstracted away from what I'm worrying about dayto-day

</details>

### 海洋探索智能应用

**Joseph**: 完全同意。这其实就是我们非常推荐的一种工程模式：通过大模型对数据进行“蒸馏”（Distillation），从而获得高精度的专用小模型。我可以做个简单的思想实验：如果你对某人说“请想一个世界上存在的物体”，以及对他说“请想一个你家冰箱里有的物体”，很显然，后者的思维难度低得多。而这就是很多模型在实际落地部署时面对的真实边界。以我们的客户——**蒙特雷湾水族馆研究所（MBARI）**为例。他们最近发现了一种全新的深海鱼类。他们使用 **Roboflow** 处理其深海潜艇采集的所有水下视频画面。在处理这些海量视频时，他们首先在后台使用像 **Segment Anything 3 (SAM 3)** 这样庞大的通用基础模型，并使用 LLM 作为裁判，对视频中出现的物体进行自动边界分割和 consensus 标记，从而建立起一套完全自动化的数据标注管线。虽然通用大模型拥有海量知识，能识别从热带鱼到建筑设计图纸再到冰箱食物的任何东西，但对于 MBARI 来说，他们百分之百只关心深海鱼类。因此，最经典的“最后一公里数据蒸馏”流程就是：利用大模型群对海量非结构化视频数据进行多轮 consensus 识别与标注，形成一个高度精准的深海视觉训练集，然后基于这个小型专业数据集去训练一个轻量级的专用模型。这个专用模型最终能以极低的算力需求部署在深海潜水器上，进行实时的高速视频检测。我想，绝大多数企业的真实痛点都属于这种形态。我经常看到一个典型的设计误区：很多工程师一提到要部署深海识别，就理所当然地把 SAM 3 搬过去并在本地直接微调。但这其实是不科学的，因为这样微调会让模型丧失 SAM 3 最宝贵的开放词表（Open-vocabulary）通用表征能力。更好的方案是，明确你的任务是一个固定类别的识别问题，丢弃大模型中昂贵而冗长的 Autoencoder 编码器部分，转而微调一个极为精简的专用视觉模型。这样你在本地部署时能同时斩获极高的计算速度和极其精准的识别精度。

<details>
<summary>Original English</summary>

**Joseph**: totally I could uh describe maybe a common flow that we see that's like distillation or uh general model specific model. So if you think about it um in a lot of cases it's like if the the challenge I like to pose that's like a thought experiment is like if you tell someone think of any object and it's like think of an object in your fridge the latter of those is actually easier and the latter of those is actually where a lot of models kind of get deployed into real world settings. So, for example, um you know, Monterey Bay and the Monterey Bay Aquarium Research Institute, Embari they're called. They discovered a new fish species recently and they build with RobFlow to process all of the underwater um footage that they capture from their deep sea um submarines. And they use large models like segmented anything 3 and LMS as judge to basically say hey let's take all this video footage and let's build a autolel pipeline to understand as many things as we can about all the video footage that we've collected but then ultimately you know Sam knows everything about uh you know things from fish to maybe architectural diagrams to um items in your fridge and everything in between. But they only care about things that are you know in this case underwater deep sea exploration. And so a very common flow that we see for like the fine-tune last mile distillation is okay let's take the large context of an array of models have those maybe all have a pass at understanding something use LMS as judge to say hey we agree with some amount of consensus and now we have a specialized data set then we can use that specific model and actually run that on the submarine in real time and also post-processing for faster video and if you think about it like a lot of problems are that shape where it's like yeah I want like general as much intelligence to understand the thing and then ultimately the problem I'm solving is specific enough even if not fully unbounded. And a mistake I see pretty frequently is people thinking like SAM 3 which is an awesome model and a great family of models. It's like okay well I should take SAM 3 and then maybe just fine-tune SAM 3. And in some ways that actually doesn't make as much sense because you lose the thing that makes SAM 3 awesome which is the open vocabulary capabilities. What might be better is like if you know you're distilling down to a specific fixed class list then you can actually drop the large expensive autoenccoder portion of SAM and use a specific maybe like DTOR or more specialized model depending on the task that you're solving and get all the benefits of you know speed up and accuracy uh while still having the general knowledge of preparing and curating your problem and I think a lot of problems are of that shape.

</details>

**主持人**: 那么你们 Roboflow 是在替客户打通和管理这套数据清洗和蒸馏的管道吗？

<details>
<summary>Original English</summary>

**Host**: Are you are you managing that pipeline for your customer?

</details>

**Joseph**: 我们提供强大的平台和工具套件，让客户能够非常低门槛地自主打通它。

<details>
<summary>Original English</summary>

**Joseph**: the yeah the tooling makes it so they can do that. Um

</details>

**主持人**: 是由你们代劳，还是仅仅向他们提供开发工具？

<details>
<summary>Original English</summary>

**Host**: do you do it on their behalf? Or do you give them the tooling to do it?

</details>

**Joseph**: 我们提供软件平台和成熟的代码 Recipes。当然，像所有健康的 SaaS 软件公司一样，如果你们预算充足，我们也提供高级技术咨询服务，由我们的技术专家进去手把手帮你们搞定。但这确实是我想分享的关于如何利用本地化数据微调、降低 Token 消耗并压榨运行效率的优秀企业级用例。

<details>
<summary>Original English</summary>

**Joseph**: Give them the platform to do that and then there's like recipes where someone can go and do that and then like any good AI company there's an FTE that if you want I can sell you get around back here and they can do it for you. That's a great example basically of the use cases and workflows that I was talking about when you're trying to find like you know collect the data as you go for your business for your enterprise and then decide how you're going to fine-tune a model a small specialized model on those use cases as you grow that's how you become more token efficient.

</details>

**Matt**: 没错。今年和明年，大家会看到大量的企业去利用那些千亿级的云端闭源巨兽模型作为“引子”去生成和清洗数据，从而去“冷启动”和微调出性价比极高的本地开源模型。

<details>
<summary>Original English</summary>

**Matt**: Yeah. Yeah. I I think this year and next year you're going to see a lot of using these like monster frontier models to bootstrap, you know, like a more efficient setup that runs on open source.

</details>

**Alex**: 是的，事实上目前社区中很多优秀的开源模型正是通过这种方法被训练出来的，这种趋势已不可阻挡。我非常鼓励大家利用云端的大模型来做冷启动数据合成与知识蒸馏，最终沉淀出属于你自己的本地模型。

<details>
<summary>Original English</summary>

**Alex**: And I think, you know, that's great. Like I think this is how a lot of the open source models have been built right now. And it's it's it's proving to be like quite hard to, you know, stop that. And I would just encourage people to just you know move away potentially from like you know these uh frontier models but like you know use them use them for for for bootstrapping that right so like um

</details>

**主持人**: 我非常赞同你刚才的话。因为这正是 **AI 工程师（AI Engineer）** 这个词诞生时所代表的内涵。当 **Swix** 发表那篇奠定行业基础的博客文章时，他就指出：以前我们开发 AI 产品的流程是先有机器学习团队去训练模型，然后再拿着模型到处寻找落地场景；而如今，我们得以将这个链条彻底反转——我们先去定义和发掘最真实的业务痛点和场景，通过大模型快速验证可行性，如果证明行得通，再考虑去沉淀底层的机器学习微调。Swix 几年前就以惊人的远见洞察了这一工作流，并主导了今天这个盛大的开发者大会。

<details>
<summary>Original English</summary>

**Host**: I love that you said that actually because that's how the word AI engineer got coined right when Swix released that blog post that coined it the way that we used to build AI products was we would start with the with the machine learning we would start by training a model then we would go try to discover a use case and what these big models allowed us to do is actually flip flip it. We said we could start with discovering a use case and then get into ML if it makes sense. And that was actually uh honestly amazing foresight from Swix because he kind of defined that pattern uh for us a few years ago and gave this amazing conference as well.

</details>

**Alex**: 没错，这个峰会仅仅举办了三年，发展规模之大简直不可思议。

<details>
<summary>Original English</summary>

**Alex**: Yeah, it's crazy how far this conference has come just three years.

</details>

**主持人**: 确实如此。我们圆桌还有最后几分钟，我想把提问权交给台下的听众。如果大家有任何关于本地 AI 的问题，可以直接向台上的嘉宾提问。

<details>
<summary>Original English</summary>

**Host**: Yeah, totally. I have a question. Do you guys have questions in the in the crowd? We have a few more minutes and I know we were talking about opening this up if you guys want to ask the panelists directly. Just just shout. Yeah, please go ahead.

</details>

**听众**: 请问在座的各位，目前本地 AI 面临的最重大的、亟待解决的瓶颈是什么？

<details>
<summary>Original English</summary>

**Audience**: What are the big open problems in local? I feel like you're the luminaries of the field, you know.

</details>

### 本地AI三大核心瓶颈

**主持人**: 我来重复一下台下这位听众的问题。他问：“目前本地 AI 面临的最重大的开放性瓶颈是什么？”

<details>
<summary>Original English</summary>

**Host**: You want to repeat the question? Repeat the one. You just asked what are the open problems in local AI?

</details>

**Ahmed**: 好的，我来回答。归根结底，核心依然是推理阶段的**优化（Optimization）**。以及如何针对不同的硬件平台去轻松拉起和配置环境，正如 ODS 和 EXO 正在做的事情。还有，如何在预算和硬件资源的约束下极致提升吞吐性能。例如，我目前还在使用两年前跑 Llama 2 和 Dolphin 微调模型的 **NVIDIA RTX 3090** 显卡。而现在，通过极端的软件和推理优化，我可以在这块显卡上极其流畅地运行 **Qwen 3.5** 和 **Qwen 3.6** 的 270 亿参数（27B）模型。在我的下一场演示演讲中会详细拆解这一点。所以，底层优化依然是目前的公开瓶颈，但这也意味着该领域依然处于极其早期的阶段，有非常大的创新空间留给新来的开发者和开源贡献者。我们坚信“开源 AI 必须获胜”，而实现这一愿景的唯一方法是，为家庭发烧友、中小企业和大型企业提供一整套无缝的、高效的本地运行工具，帮助他们解决真实的业务痛点，而不是给他们带来额外的技术头痛。

<details>
<summary>Original English</summary>

**Ahmed**: I I can repeat it. It's what are the biggest open problems in local AI? Uh uh it continues to be optimizations and u for inference. It continues to be getting things easily kickstarted which is you know what ODS is XOS for specific hardware. It continues to be how can I make the most out of my budget constraints and hardware constraints and how can I squeeze the most performance out of that uh you know the the models that you know I still have the same 3090s that I used to run lama 2 and like dolphin fine tunes on and now they're running Qwen 3.5 Qwen 3.6 27 billion parameters with excellent performance you know more on that in my next presentation. So you know uh it comes down to the optimization and we are still very early that there is space for so many players for so many contributors. We need all the help we can get to make this thing the success that it needs to be that we need to make local AI the default. This has been my stance for years now. I have been saying open source AI must win for like since forever. And the way we do that is by giving the people whether that's individuals at home, medalsized businesses or enterprises an easy way to use these models in a very efficient way that doesn't give them headaches more than solve their problems.

</details>

**主持人**: 没错。如果你看我们今天峰会的议程设置，你会发现全天探讨的内容都是目前本地 AI 生态中最艰深的命题。比如关于**模型量化**的圆桌，探讨如何通过算法压缩模型体积以适应边缘侧设备的显存限制；还有关于多模型路由和通用模型调优的圆桌。我们希望在未来的本地 AI 峰会上，议题能够随着生态瓶颈的突破而不断向更前沿的领域演进。

<details>
<summary>Original English</summary>

**Host**: Totally. And if you look at the panels that are that are happening today, those are what we believe to be the biggest open-ended questions, which is why we try to assemble this panel. And so the you know we have quantization so all about talking about the footprint so that the models do fit on these uh uh on these smaller hardware footprints. Uh there's model routing there's models generally uh so those are kind of the what we feel like are the big problems now and as we do future local AI summits um I you know every time the panels should change to be the topics dour that are kind of holding the or or going to be going to usher the next chapter in.

</details>

**Joseph**: 我想补充两点。我认为当前本地 AI 面临两个最核心的开放性瓶颈：第一是刚才我们反复辩证讨论的**极简性与可定制性之间的权衡（Simplicity vs Customizability）**。本地部署意味着高度的掌控和自由度，但也带来了环境配置的复杂性；而云端托管服务虽然能开箱即用，却也彻底剥夺了定制权。我们必须找到一个中间地带。第二点，我希望在座的每一位都能引起重视：开源底座模型的合法地位与合理性正在受到越来越强烈的挑战与质疑。如果你支持本地 AI，你就必须支持开源 AI。在政策和舆论层面去积极倡导允许开发者和企业自由使用、修改、定制和折腾模型，在目前这一阶段极其关键，这关乎着我们整个开源社区的未来命运。

<details>
<summary>Original English</summary>

**Joseph**: Can I add one thing to that? One of the biggest challenge so I think there's two two big challenges One is what we've been talking about of basically the trade-off of simplicity versus customizability. It's local, it's yours, you can do different things, optimization, if it's hosted, it's built out of the box. The way that trade-off is is always difficult. The second, which I actually encourage people in this room to help solve is the importance of open models is becoming increasingly in question. And I actually think that like if you think local AI is important, then you think open source AI is important. And it's actually really important to be an advocate for being able to use, change, adapt, and toy with models. And so I think that that's a problem that um could increasingly be something that we feel less control over absent advocating.

</details>

**主持人**: 这切中了要害。现场的每一个人都对开源心怀热枕。开源创造了一个良性的、必要的竞争生态，让最好的点子得以快速脱颖而出并普及给所有人。当外界将开源 AI 抹黑为某种安全威胁时，我们更应当大力投资并去为开源正名。开源的精神内涵甚至远远超越了 AI 领域本身。正如算力本身起源于美国东海岸，但偏偏是在西海岸的**硅谷**孕育出了如今的技术大爆炸。这是因为早期的技术黑客与嬉皮士们坚定地认为：软件思想应当以自由且无成本的方式在社区内共享。我一直认为，硅谷之所以充满活力，正是源于渴望赚大钱的资本家与主张自由共享的嬉皮士之间形成的张力。这种永恒的张力塑造了我们这里不可思议的技术生态。

<details>
<summary>Original English</summary>

**Host**: That's a great point. I think everyone here feels very passionate about open source. That is why we actually have access to the space at all. That's why the space is has progressed. It's a it's a necessary competitive environment. It allows for the best ideas to make their way to everybody. Um, so definitely when there's talks about that being a threat, you know, we need to invest and advocate for open source and open source is so much bigger than AI, right? Like there's a reason why computation like compute was invented in on the east coast, but Silicon Valley happened here and it's because hippies realize that they could share ideas for free in software. I think Silicon Valley is this kind of tension between the capitalists that want to make money and hippies that want to give these ideas away for free. And that tension is what creates such an incredible environment here.

</details>

**Alex**: 事实上，这二者完全可以共存。开源和商业并不冲突，你完全可以基于开源去服务消费者并向企业客户售卖高级服务。

<details>
<summary>Original English</summary>

**Alex**: They can coexist, by the way. you can have consumers and you can sell to businesses

</details>

**主持人**: 确实，当这两者达成良性互动时，整个开源生态往往会运行得最为顺畅。

<details>
<summary>Original English</summary>

**Host**: and that's when this space works works best.

</details>

**Alex**: 没错。最后，如果大家对倡导技术主权感兴趣，即使你并不懂编程或算法，也可以积极参与其中。大家可以访问刚刚上线的 **righttointelligence.org**（智能权利组织）网站，这是一种非常直接的参与方式，去为维护开源和自由的智能空间发声。

<details>
<summary>Original English</summary>

**Alex**: Can I just say like if you care about this and you want to be more of an active participant but maybe you know you don't want to get involved in the technical side you're not technical then there are ways to get involved. So there's a website that just came out called right to intelligence.org and this is a way for you to like get involved and actually like advocate for opensource and to ensure that you know we maintain freedom of intelligence.

</details>

**主持人**: 好的，因为时间关系，我们本场圆桌讨论到此结束。再次感谢台上精彩分享的各位嘉宾！本地 AI 峰会今天的内容非常充实，接下来我们会有很多极具冲击力的本地运行展示。欢迎大家继续参与接下来的圆桌，多提问、多交流。谢谢大家！[掌声]

<details>
<summary>Original English</summary>

**Host**: Awesome. So we're out of time. I want to thank you guys so much. Locally Summit's going to be a ton of fun. Thank you guys for this incredible way to kick this off. We're gonna have amazing demos. We're running foundational intelligence models here inside of this room. we're gonna have a couple of amazing uh a few more panels. It's going to be an exciting day. Um and we're all lingering here, so ask questions and please participate. Thank you. [applause] [music] [TRANSCRIPT_END]

</details>