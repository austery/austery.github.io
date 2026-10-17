---
author: How I AI
date: '2026-09-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AniiF8rOu9c
speaker: How I AI
tags:
  - computer-use
  - generative-ai
  - autonomous-agents
  - benchmarking
  - software-engineering
title: GPT-6 Astra 实测：计算机操作与前沿能力的一击破局
summary: 本期内容深度评测了 OpenAI 最新发布的旗舰模型 GPT-6 Astra。演讲者通过大量真实严苛的实测任务，展示了该模型在计算机直接操作（Computer Use）、自动化流程搭建、代码构建与硬件逆向工程、3D游戏生成以及复杂产品知识图谱提炼上的跨越式突破。Astra 不仅在基准测试中大幅领先，更展现了将以往难以攻克的复杂任务实现'One-shot'直接落地的强大实用能力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - GPT-6 Astra
media_books: []
status: evergreen
---
### 迈向星辰：GPT-6 Astra 的震撼发布与雄心重塑

今天我们将探索科技的新高度，因为 **GPT-6 Astra** 正式上线了。目前它已向 Daybreak 客户开放，并将很快面向更多用户推出。在过去六个月中，我有幸获得了早期测试权限。或许这听起来有些陈词滥调，但这确实是过去半年来真正让我感到个人雄心被彻底激发的模型。

在长期的技术攻关中，我积累了许多此前各代模型无法攻克的常驻测试任务。不论是此前的 Fable 架构，还是备受赞誉的 **56 Soul**，都曾在这些硬骨头面前败下阵来。然而，GPT-6 Astra 却以令人惊叹的 **单次生成**（One-shot: 无需多轮试错或人工干预即一次性成功输出）搞定了其中的绝大多数。本期内容将深入拆解这款模型的本质特性、OpenAI 官方宣称的核心优势，并展示我基于它构建的一系列不可思议的项目——包括再次逆向破解那些看似无解的硬件设备。

<details>
<summary>Original English Source</summary>
We are going to the stars today because yes, today GPT-6 Astra is live. Well, it's live for Daybreak customers. It will be live for the rest of us very soon. I was lucky enough to get some early access to test the model and this has been the model in the last 6 months and you know, maybe I sound like a broken record, but this is the one that has made me actually feel more ambitious. It has crushed some of my standing tasks that Fable couldn't figure out. Even my beloved 56 soul can figure out. This model GPT-6 one shot a bunch of them. I'm going to tell you what this model is, what OpenAI says it's great at and I'm going to show you some pretty incredible things I built with it including yes, hacking this dumb computer again. Let's get to it.
</details>

### 全维领跑：官方定位与计算机操作能力的范式转移

抛开官方博客中常规的宣传细节（其核心总结就是：在几乎所有维度上均达到 **最先进水平** SOTA），OpenAI 将 Astra 定位为其迄今为止最高智能且对齐程度最好的模型。它在科学、前沿数学能力（Frontier Math）上取得了巨大跃升，同时保持了极高的推理速度与更低的行为侵扰性。然而，官方重点突出的核心杀手锏是**计算机操作**（Computer Use: AI 直接识别屏幕界面并模拟鼠标、键盘操作软件的能力）。

Astra 在软件操作上的表现极为强悍，不仅限于常规的网页浏览器，还涵盖了 **Excel**、**Unity**、**Power BI**、**Blender**、**Jupyter** 以及各类专业文档编辑器。这标志着软件形态的一次重大回潮——**SaaS**（Software as a Service: 软件即服务）与图形界面（UI）重新获得了生命力。过去整个行业都在鼓吹“无 UI 才是未来”以及纯命令行（CLI）与 MCP 协议，但如今由于 Astra 能够像人类一样自如点击按钮、操作软件，传统图形界面的价值被彻底重塑。同时，模型在生成符合个人风格、品牌调性与语调的工作交付物（Work Artifacts）以及自主引导控制方面，也做到了显著的提效。

<details>
<summary>Original English Source</summary>
Okay, I don't want to spend too much time on the blog post. We can link to it in the show notes. You all can go read it. TLDR state of the art on basically everything. We got the science map, coding, knowledge work, not being annoying, being fast, computer use, all the things. So, OpenAI is positioning it as it's most intelligent and aligned model. Huge jumps particularly on frontier math, big jump there in mathematical ability. The big thing that they're calling out is computer use and the use of software. So, you're going to see this in today's episode, but it is so good at computer use. Not just browsers, but Excel, Unity, Power BI, Blender, Jupiter, document editors, like kind of everything. So, we're back. SAS is back. Product back. Buttons are back because now Astra can use it. It's really good at producing work artifacts. They've done a lot of work to make work artifacts match your style, match your brand, match your voice, etc. And then again, autonomy, steering, all that kind of stuff is is very good. They've really focused a lot on kind of time saving on common tasks again because of computer use.
</details>

### 基准表现与成本博弈：从算力重压到真实效用

在当前整个行业对 Token 算力开销感到巨大压力的背景下，模型厂商们迫切需要证明大模型不仅仅是烧钱的机器，而是能创造真正商业价值、完成实际工作的利器。OpenAI 特别强调了 Astra 在演示文稿、电子表格、专业文档及专业软件中的应用场景。从基准测试数据来看，Astra 在 **Automation Bench** 自动化基准上的得分达到了 56 Soul 公布分数的整整两倍，展现了其在复杂任务自动化上的绝对统治力。

在代码能力基准 **Deep Sweep** 上，Astra 相比 56 Soul 实现了稳步提升；若将其代码能力与计算机操作深度结合，将能解锁极其庞大的创新空间。而在 **Frontier Math Tier 4** 等前沿数学极限测试中，其跃升幅度更为惊人。关于获取方式与定价策略，该模型正优先向企业客户及 Daybreak 用户推送，随后逐步向大众普及。值得注意的是，其定价依然属于高端模型区间——例如输入价格约为每百万 Token 5 美元，输出则达到 25 美元。这不仅反映了高昂的算力成本，也折射出大模型在追求极致智能与商业化盈利之间的现实平衡。

<details>
<summary>Original English Source</summary>
And so, this is a little like sneak peek into I think like we're all spending a lot of money on tokens and these models are feeling pressure to be like "hey, I'm doing real work. I am not just a money burning machine." So, like lots of focus here on efficiency, real work. They really call out presentations, spreadsheets, documents, and software as great use cases for Astra. But, let's look a little bit at kind of some of the numbers. So, automation bench, again, double Soul's reported score. So, you know, a lot higher on, automating tasks. Let's look at coding. Deep Sweep, a little bump up here against Spyce 6 Soul, but again, combined with computer use, you're going to be able to do a lot more really interesting things. Math is a big story here. So, big jump in Frontier Math Tier 4. And then, let's talk about price and can you get it? So, it's rolling out. First, it's going to go to enterprise customers with daybreak access. If you're a daybreak customer, you can use it. It is coming to chat GPT soon. It's coming to other, um, customers soon. And, I think API is coming very, very soon as well. So, hang tight. It is on the more expensive side. Again, remember they're spending a lot of money to be profitable here. So, it's like $5 input, $25 output, something like that. But, um, very exciting stuff.
</details>

### 视觉化实操：从零搭建节点工作流与自动化生成

在理解了核心能力后，我们将其实战化。首先展示的是复杂的图形界面操作：在日常业务中，我们使用 **Adio** 平台内置的基于节点的 **工作流构建器**（Node-based Workflow Builder: 通过拖拽节点和连线来定义数据流向与逻辑判断的图形化开发工具）来处理客户关系管理（CRM）的线索分流。过去，人工在此类界面中反复拖拽配置极其繁琐易错，由于难以从模型响应中准确推断对象类型，我曾耗费一小时仍陷入停滞。然而借助 Astra 的计算机操作功能，整个范式被彻底颠覆。

我只需提供清晰的高级意图指令，Astra 就能接管浏览器，自主在画布上新建节点、选择大语言模型、填入提示词、配置条件分支，并将线索精准分发至指定的 Slack 频道或 CRM 属性中。随后，我又让它进入 **ComfyUI** 节点式图像工作流中处理播客相关的视觉素材：Astra 自主调取我在 Photo Booth 拍摄的头像照片，在画布上绘制新节点，将生图引擎从旧版的 Nano Banana 切换为最新的 **GPT Image 2**，精准配置画面长宽比与提示词，全自动完成高质量图像生成与后续视频渲染链条。这种对复杂 UI 的自主交互证明了图形界面的交互潜力。

<details>
<summary>Original English Source</summary>
All right, let's stop talking and start looking at cool stuff. The first thing I wanted to show you was this node-based workflow. Now, I have not built with Astra in subagents yet, but we're going to do it live here. So, we use this kind of built into our CRM Adio node-based workflow builder to build out the assignment logic, do things like prompt to determine Clark or Zach, and then route it to different Slack messages and different CRM attributes. And I found myself sitting here and like futzing with these buttons one off. I couldn't figure out like how to infer the right objects from the responses the AI responses. I was just getting really frustrated. I spent an hour here. And then I was like, "A computer use. Of course, computer use can do this." And so, I want to show you what that looks like. Okay, so instead of dragging and dropping all this stuff, let's tell Astra to come in here and use this tool. So, I have this branch open. It's connected via browser. I gave it a prompt. I said, "Hey, can you open up this tool? Can you go in and configure this logic so that we're passing through this form? We are deciding if we're assigning it to Clark or Zach and then we are saving it out." And so, what you can see it's doing here is it's actually dragging out these nodes and configuring them. And this is a really fascinating new way to think about interacting with your computer, interacting with websites. And I think about this. We you know, we all said no UI is the next UI, and we had all these conversations about MCPs and CLIs. And what's so fascinating is now we're at this moment where actually like UI's back, baby. Like SAS, this might be your savior because humans really do like a button. And now that you can get AI to click buttons for you and use a UI for you, you sort of don't have to think about these CLIs and MCPs necessarily if the right expression of your product is more of a UI-based thing. So, I really do think computer use is kind of incredible. I'm going to let this keep running, but let me show you another thing I did with computer use while this is going. Over here, we do a lot of node-based editing. This is our podcast ComfyUI instance. We have this running and we have this node-based workflow to generate all the art and all the video for the podcast. And so, what I said to it is, "Hey, can you navigate this app, import these images, and hopefully generate us the videos that we want that you'll see today when you come to the podcast." So, I'm going to let that run. We're going to come back to it once the nodes are being generated. Okay, so let's watch what it's doing. It took this imported photo of me that I just took in Photo Booth. It's going through and drawing a node, selecting the image generation model that's going to use. We use GPT Image 2. We used to use Nano Banana, but we actually really like GPT Image 2. It's selecting aspect ratio. It's putting in the prompt based on other prompts we have, and it's going to go ahead and generate that, and I think it's going to do it for all these other ones. It's going to be really cool.
</details>

### 自主质量保障：浏览器环境下的深度测试与竞态调试

在完成工作流配置的基础上，Astra 在软件工程质量保障（QA: Quality Assurance）领域的表现同样令人瞩目。在常规开发流程中，为复杂的前端应用编写端到端测试或进行人工界面探索往往枯燥且极易遗漏隐蔽缺陷。在一次功能分支的测试中，我直接向 Astra 发出指令：“你能直接在 Chrome 浏览器中测试这个分支吗？”

Astra 随即拉起该分支的预览环境，自主开始模拟用户点击、发送聊天消息并遍历各项功能。更关键的是，它在执行过程中全程监控浏览器开发者控制台（Console），实时捕获底层错误日志，并专门针对前端中的 **竞态条件**（Race Conditions: 多个异步操作因执行顺序不确定而引发的逻辑冲突或界面错乱）进行极端压力测试，例如反复在特定临界状态下刷新浏览器。Astra 自主持续运行了整整 1 小时 45 分钟，不仅精准定位了数个深层次的导航缺陷，更直接在代码层面完成了修复。这种兼具执行力与深度诊断能力的自动化 QA 表现，代表了智能化测试的崭新高度。

<details>
<summary>Original English Source</summary>
Let me show you another thing. While this is running, I used it to QA a whole application. So, here I had a PR open on a branch and I've been really struggling. We added this whole new chat component to this app. It had this real-time stream. It had a bunch of other stuff and I was like, "Hey, can you just like test this in Chrome?" And what was really awesome is it just pulled up the preview branch, and then it started clicking through testing, sending chats. And what was really helpful about browser use here is it was inspecting the console, checking for error logs. It was doing things like race conditions. It would like refresh Chrome. It would do all this stuff that would be very tedious and hard to execute as a human, but was super useful as a QA. You can see here it actually ran for an hour and 45 minutes basically QAing this branch. It found a couple issues when you were navigating. It fixed some things. It specifically looked at some race conditions and was really awesome. So, really, really great.
</details>

### 复杂架构攻坚：产品智能知识图谱的一击即中

除了界面交互与测试，Astra 在处理高复杂度系统工程任务时的表现同样实现了质的飞跃。以我长期研发的 **产品智能图谱**（Product Intelligence Graph: 融合多源客户反馈并自动化生成结构化知识库的系统）为例，该系统要求模型监听外部客户反馈流、确定持久化存储范围、对非结构化数据进行深度清洗、去重提炼核心洞察、构建系统化 Wiki 文档，并对外部事实源进行交叉验证。

在这项极度考验系统工程与多步逻辑推理的严苛任务上，此前的各大顶级模型均告折戟：Fable 架构在底层逻辑设计上产生混乱，而 56 Soul 则在洞察提炼的深度与质量上止步不前。六个月来，这一直是我无法逾越的技术瓶颈。然而，当我将完整的架构需求提交给 Astra 时，它直接实现了 **One-shot 一次性完整落地**。生成的知识图谱无论是在实体关系的严密性，还是在长程逻辑的自洽性上都达到了极高水准。正是这种攻克历史遗留难题的强悍能力，彻底改变了我对当前 AI 上限的认知。

<details>
<summary>Original English Source</summary>
Let's talk about something that's not computer use, which is general intelligence. So, I built this thing, and you've probably heard me talk about this before, which is product intelligence. I built this repo. It's an autonomous loop that listens to customer feedback. It has to decide what it durably stores, it has to process it, has to deduplicate insights, it has to generate a wiki, it has to verify that wiki against external sources, and like I Fable did insane things with the architecture. 5-6 just like got stuck on quality of insights, and I am telling you all Astra one-shotted. And I was like kind of like this has been my experience this entire model, which has been like I It's been so hard to do these like very specific tasks, and I've tried them over and over and over again for 6 months. And then all of a sudden Astra started to one-shot it. So, I have been working on this product graph product intelligence forever, and finally just gave it to Astra and I'm like, "Astra, can you do this?" And Astra did it. And this is the wiki that it built. It's so clean, so good.
</details>

### 硬件逆向与桌面重构：点阵像素屏与复古聊天客户端

在纯软件开发之外，Astra 在硬件逆向与桌面客户端编程中展现了惊人的硬核实力。以 **Divoom Mini 2** 蓝牙像素音箱为例，该设备搭载封闭的私有固件，没有对外开放的 API 接口，逆向破解极其困难。在此前 GPT-5.5 仅能勉强实现基础控制的基础上，Astra 展现了质的突破：它不仅成功逆向工程了底层的点阵像素渲染算法，成功在屏幕上渲染出细腻的动态像素艺术，更通过自定义协议将其与我的 **Codex Hook**（开发代理事件监听钩子）打通。如今，当本地代码代理需要人工输入或完成任务时，像素屏会自动弹出动画通知，实现了实体硬件与 AI 编程流的物理级联动。

在此基础上，我还利用 Astra 打造了一款极具情怀的 macOS 原生桌面应用：将现代复杂的 Codex 会话流封装为 90 年代经典的 **AIM**（AOL Instant Messenger: 90年代风靡全球的即时通讯软件）复古聊天客户端。应用完美复刻了当年的拟物化 UI、像素图标与声音反馈，甚至将不同的子代理映射为好友列表中的在线联系人。这种能够无视技术代际、随心所欲将复杂系统低门槛转化为精巧实用软件的体验，正是高阶编程模型所带来的最大乐趣。

<details>
<summary>Original English Source</summary>
Okay, let's talk about coding, but make it fun. So, you all know that I have been victimized by this thing. It's a Divoom Mini 2. It is really just like a Bluetooth speaker. It comes pre-installed with proprietary software. You can't There's no API. You can't crack it. You can't hack it. And GPT 5.5 was the first one that even let me do the most basic thing on this little computer. This has been This is my my Everest. And already, I mean, the quality of what I've been able to flash onto this little device is amazing. Look, it's like Claire's Little Lab. It's figured out the pixel algorithm, which I had to to reverse engineer. It was not easy. So, it's it's already doing cute art. But, let me show you what it did for this episode because this was so cool. Okay, look at this. It's flashing the title of this episode. Look, it's got the little icon. It's going to flash up the title. "How I AI, Episode 32: Removing Agents from Open Claw 36 Minutes." A real agent tour. Find it in your podcast app today. We did it, folks. Next I got to root it. So that's next. The other really cool thing that I did with this that you all haven't seen is I hooked it into my Codex hooks. So now it can tell me when Codex needs something and that brings me to my next use case. Very fun. Again, just coding things that I could not do before that I can do now. Let's look at it. It is building me a Mac app that turns my Codex threads into a 90s style AIM messenger. For those of you who are young and beautiful and were maybe not even born when AIM was around. AOL Instant Messenger, it's how we old used to chat back in the day. And it's building this full Mac app that hooks into my Codex threads. It gives them little screen names. It makes them look like they're online or offline. It has little chat windows. It has all the little sound effects. It's so cute. Look at this. It's just like chatting with an AIM bot. And again, this is just like a fun, creative expression of what you can do when coding becomes this accessible and this powerful.
</details>

### 三维创想与未来展望：重构个人软件开发的天花板

在三维交互与游戏开发维度，Astra 同样展现了强大的端到端生成能力。受 90 年代经典 CD-ROM 游戏《Barbie Fashion Designer》（芭比时尚设计师）的启发，我一直渴望构建一个属于自己的“3D 时尚走秀台基准”（3D Barbie Bench）。过去半年中，尝试让各代模型生成完整可运行的 3D 渲染与走秀逻辑均以失败告终。然而，Astra 再次实现了一击即中：直接输出了具备 3D 视角转换、角色动画控制与动态走秀逻辑的完整程序。

随后，我进一步要求 Astra 为孩子们开发一款结合 **社会情感学习**（SEL: Social Emotional Learning: 培养自我认知、情绪管理与人际交往能力的教育理念）的 3D 互动应用。Astra 迅速生成了一个唯美的 3D 虚拟小镇：孩子们可以通过键盘控制角色漫步至“图书馆”打卡阅读任务并领取奖励，或是前往“月水池”（Moonwater Pond）根据天气记录和表达当天的情绪变化。整个系统包含完整的场景建模、光影渲染、碰撞体积与漫游控制，我未写一行代码便完整实现了预期。

回顾整个实测历程，GPT-6 Astra 带来的最深刻变革在于**拔高了开发者的雄心上限**：
1. **多源数据认知聚合**：打通客户反馈与内部架构，实现自主构建高保真知识体系；
2. **软硬件边界突破**：从逆向破解封闭固件到驱动实体交互，让代码真正连接物理世界；
3. **全栈创意自由落地**：无论是复古桌面客户端、三维交互空间还是浏览器全自动深度测试，均能以极低成本迅速成型。

拥抱这款模型，意味着开发者不再受限于基础语法与繁琐细节，而是能够站在更高的系统架构与创意维度，重塑人机协作的无限可能。

<details>
<summary>Original English Source</summary>
And that brings me to my last demo, which is the 3D Barbie Fashion Designer Bench. And you all again, are young beautiful people. So, you don't know this. But there is this game. It was called Barbie Fashion Designer. It came on a CD-ROM. And you had this 3D Barbie, and you could design her clothes, and like pick colors and prints, and then you could actually print out clothes on this like printable fabric, and then you could like tape it together and put it on your Barbie, and then she walked like a 3D runway. Like this. And I know all of you are out there making space games, and making race games, and making RPGs, and making all sorts of stuff. That is not for me. I am a girl. I want 3D Barbie bench. I want bench, baby. You guys, I've tried over and over and over again to get models to make this 3D runway and make this 3D Barbie walk and it has never worked. And Astra, you guessed it, one-shotted it. Look at this. Look at her walking. Look at the 3D controls. You can move the camera around. You can see her from different angles. It's so good. And then I took it a step further. We have this app in our house called Quest. It's like a habit tracker for my kids. And I said, "Hey, can you make this 3D?" And so, I asked Astra to turn this app into a 3D journey where my kids could walk to the library, for example, and say, "I read 20 minutes, collect my reward." Or go to Moonwater Pond and see what my weather is, my emotions are today. We're doing a lot of like SEL stuff in my house. So, again, like walking through this and look how beautiful all this is. How so super cute. You can use keyboard control, which I'm using right now. I'm sure Astra would be really good at controlling this as well. I mean, truly one shot. I did not code any of this. I just actually said, "Can you make this a 3D, you know, journey where you can walk through different places?" And it did this out of the box and it's so cool. So, to wrap it up, what are the three things that I think Astra is like really, really setting a new bar on? Number one, listening to your customers and building intelligence loops that actually work and help you learn from your customers about their own product. The second one was this guy, hacking hardware. Please hack your hardware, hack this. Hack your Bluetooth light bulbs. Hack, hack, hack. This guy, just being able to interact with hardware and the real world is such a fun thing. And it was this it's There's a step change in this model in my experience, and I've been working on this for a long time. Up-leveling your ambition of what kind of things you can code. So, like website by putting these over, we can all do that. Let's do 3D games. Let's do Barbie bench. I'm going to do this 3D game for my kid, or let's do desktop apps like this aim style messenger that wraps Codex and does something pretty incredible and really fun. So, that's GPT-6 Astra. It is live now for Daybreak customers. It's coming to ChatGPT and API very soon. I hope you all get access to it soon. Let me know what you build. If you enjoyed this episode, please subscribe on YouTube, Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaiipod.com. See you next time.
</details>