---
author: AI Engineer
date: '2026-11-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UCL4K36SHp0
speaker: AI Engineer
tags:
  - open-source
  - ai-agent
  - rust-lang
  - desktop-app
  - software-factory
title: 开源整个世界：利用 AI Agent 重构桌面软件生态
summary: Brandon Thomas 分享了 ArtCraft 利用 AI Agent 与 Rust 快速复刻 Photoshop 等主流商业应用并引发开源热潮的经历。他回顾了早期开放互联网向封闭平台演变的历程，提出借助 Agent 自主开发与开源协议重新夺回软件控制权，并介绍了开源软件工厂 Autocraft 的探索。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Brandon Thomas
companies_orgs:
  - ArtCraft
  - Adobe
  - Square
  - Microsoft
  - Google
products_models:
  - Photoshop
  - InDesign
  - Premiere
  - Figma
  - Autocraft
  - PDF Craft
  - Solid Craft
media_books: []
status: evergreen
---
### 项目走红与开源愿景

大家好，感谢大家来听我的演讲。这场演讲是我昨晚很晚才赶出来的。在这个项目走红、帮成千上万名开源开发者解除阻塞之后，我整个人就陷入了一场旋风之中。有风投主动找上门，会议一个接一个。自从那件事发生以来，这一个月简直是忙得不可开交、彻夜难眠。如果你还不了解情况的话，我大概就是克隆了 Adobe Photoshop 以及一堆其他应用，然后彻底在网上火了。

<details>
<summary>Original English</summary>
[music]

>> Hey everybody. Thanks for attending my talk. I had to put this together late last night. I've been in a whirlwind after this project went viral of unblocking thousands of open source developers. We've had VC's approaching us. I've been in constant meetings. Like this has been a sleepless month of activity since this happened. So if you're not familiar, I kind of cloned Adobe Photoshop and a bunch of other apps and that went super viral.
</details>

我的手机、收件箱，所有渠道全被各种消息塞爆了。所以我对这场演讲的组织结构说声抱歉，这确实是我能以最快速度凑出来的。不过，我有很多非常令人兴奋的内容想和大家聊聊，我认为这不仅关乎整个行业的未来，更关乎科技本身的未来。

我们要把整个世界都开源。为什么不呢？作为一名开发者，这一直是我想做的事情，也是我们开源社区很多人都感兴趣的事情。开源支撑了我们所熟知的许多技术，但它却从未真正站上最前沿。比如 Linux，一直以来都像是二等公民。我们被裹挟进了各种我们并不真正拥有所有权的平台中，而 AI 在某种程度上给了我们一个把网络“夺回来”的机会。

<details>
<summary>Original English</summary>
My phone, my inbox, everything has just been absolutely lit up and so I I I apologize for the structure of the the the the talk. This was thrown together as quickly as I can, but I've got a lot of really exciting stuff to talk about and I think it talks about the future of not only the industry, but just technology as a whole. So we're going to open source the entire world. Like why not? It's it's something that I've always wanted to do as a developer. That's something that a lot of us in the open source community are interested in. Open source powers a lot of the you know, technology that we're familiar with, but it's never been at the forefront. Like Linux has always been like a second class citizen. We've been pulled into a whole bunch of platforms where we don't really have ownership and AI kind of gives us a chance to take the web back, if you will. So
</details>

### 个人背景与早期互联网记忆

我可能得手动翻页了。好的，先简单介绍一下我自己。我做工程师大约有 15 年了。其中有 8 年在 Square 从事核心底层基础设施开发，比如在线支付、身份验证技术栈；基本上任何可能导致公司停摆的核心系统，我的团队都负责兜底。那 8 年里我一直随身带着传呼机待命，处理了大量极其关键的基础设施。

之后我花了 7 年时间做初创公司，那完全是另一个世界：充满了巨大的风险，需要不断了解市场需求，不断纠正自己的假设。此外，我常驻亚特兰大，这里是个电影大州。我一直很热衷于艺术领域，大学刚毕业时拍过很多电影，造过能在摩天大楼侧墙上投射并游玩电子游戏的激光投影仪，诸如此类。我们做初创公司所服务的客户，也都是创意工作者、艺术家、电影制作人等群体。

<details>
<summary>Original English</summary>
I might have to do this manually. Cool. So a little bit about myself. I've been an engineer for about 15 years. I spent eight years at Square doing heavy hitting infra. So online payments, the the authentication stack, basically anything that could take down the company my team was kind of in charge of and it was you know, eight years of carrying the pager, a lot of really heavy hitting infrastructure Um and then I've spent seven years doing startups, and that's a whole different world. It's a lot of risk, a lot of learning like what the market needs, a lot of correcting your own assumptions. And I've also been um I'm based in Atlanta. It's a big film film state. I've been very big in the arts. So out of college, made lots of films, built laser projectors that play video games on the side of skyscrapers, that kind of thing. And those are the sort of customers that our startups or the startups that I built have have catered to, creatives, artists, filmmakers, and so forth.
</details>

我想带大家穿梭回过去，回到网络和互联网刚刚起步的 90 年代和 2000 年代初期。对于我们千禧一代来说，可能会感叹自己老了；而对于更年轻的一代，我想以此帮大家勾勒出当时的互联网到底是什么样子的。

当时我们有一批完全开放的聊天应用。比如 IRC，它就像现在的 Discord，但你可以搭建自己拥有完全控制权的主机。你可以随意使用各种程序来实现自动化，或者不受限制地调用接口。当时所有的商业即时通讯工具基本都不在乎你是否用第三方工具接入它们。

每个网站都支持数据导出，都提供 API。你完全可以用 Reddit、Flickr 和 Twitter 构建非常酷炫的聚合应用（mashup）。在 Hacker News 出现之前，这些项目经常在 Slashdot 上引发热议。而到了现代，随着各大平台将 API 逐步关闭，这种探索的节奏大大放缓了。

<details>
<summary>Original English</summary>
Um I want to transport everybody back in time, back to the very beginnings of the web and the internet, the '90s, the the the early 2000s. So for us millennials, we're going to feel old. And for um everybody that's that's younger, this is just let me kind of set the stage for what the internet was like. Um we had a bunch of chat applications that were completely open. So IRC is like Discord, but you could spin up your own servers that you actually own. You can use whatever programs to automate them and interrogate them without rules. All of the commercial messaging apps were basically they didn't care if you used third-party tools to connect to them. Every website had data exports. They had APIs. You could literally build really cool mashups with Reddit and Flickr and Twitter. And these were like trending on slashdot before Hacker News was a thing. And then, you know, in in the more modern times, these kind of trickle down to a much slower pace because the APIs got got removed.
</details>

当时大家都在分享文件。不仅是文件共享，你还能真正买下 MP3，对你在网络上做的一切都有一种实实在在的“所有权感”。而现在，它更多变成了“许可租赁”。

当时到处都是开放的创造力，主要是因为那时候上网的大多是有技术背景的人，他们是早期采用者。玩 Flash 的孩子们制作了各种各样的动画；网络上分布着基于 phpBB、Invision 的多元社区，那个时代迸发出了难以置信的创造力。

维基百科也是在这样的时代精神中起步的，但我们在当下的技术时代和现状中，已经很难再看到类似的事物了。那时的网页具有极高的可定制性，比如当年的 MySpace，你可以直接修改 HTML 和 CSS，把它做成你想要的任何样子。与我们今天的环境相比，那完全是一个截然不同的时代。

<details>
<summary>Original English</summary>
There was a bunch of file sharing. So not not just file sharing, you could actually buy MP3s and feel a sense of ownership in in everything that you were doing on the web. And now it's more licensing. Um there was so much open creativity because largely the people on the internet were technical. They were early adopters. So Flash kids were making all kinds of animations. There were diffuse communities with PHP PHPBB and Envision and just just a ton of creativity that was happening at that time. Wikipedia got started sort of in this ethos, and we don't really see this kind of stuff anymore in the current era and incarnation of tech. Websites were highly customizable, like MySpace at the time. You could actually change the HTML and CSS and make it look however you want. So this was a totally different alien time compared to what we have today.
</details>

### Web 2.0 的异化与“平台劣质化”

随着 Web 2.0 的到来、宽带的普及以及智能手机的出现，所有人都被带入了网络世界。技术人员因此被逐渐边缘化。这本身并不是坏事，我们确实需要让父母和祖父母也能用上这些产品。但我们把产品的棱角给磨平了，去掉了所有的技术复杂性，让一切都变得极易上手，因为普通大众无法从技术的角度参与进来。他们不愿去折腾未打包的东西，也不知道什么是 API。于是，开放的协议被中心化平台所取代。这些平台开始尽可能多地圈占用户，早期那种分散且充满实验精神的互联网逐渐消失了。

API 从我们手中被剥夺了。随后，我们看到大型平台供应商开始对分发渠道进行把守与垄断。在手机生态中，我们从未拥有过像桌面时代那样自由分发软件的环境。

随着初创公司赢得市场份额，产品价格变得越来越昂贵。它们意识到自己拥有了定价权，突然之间，当你订阅完全部流媒体服务时，你的 Netflix 花费实际上已经变成了有线电视账单的水平。

<details>
<summary>Original English</summary>
When Web 2.0 happened, broadband, smartphones, it brought everybody into the fold. So the technical people got sort of pushed to the sidelines. And it's not a bad thing. Like we needed our, you know, our parents and our grandparents to be able to use these products. But we sort of we rounded the edges on things. We took away all the technical pieces. We made everything easy for people to adapt because they couldn't contribute from a technical footing. They didn't want to unpackaged things. They didn't know what APIs were. And so the platforms and the the the protocol like protocols got replaced by platforms. And they sort of grabbed as many users as they could. And sort of the diffuse, experimental early web started to disappear. The APIs got taken away from us. And then we started seeing distribution being gatekept by the big providers. Like we never once had a phone ecosystem where we could freely distribute to like like we could on the desktop. Things started to cost more and more as as startups began to like win market share. They realized that they had pricing power and suddenly your Netflix actually became cable once you started subscribing to all the streaming services.
</details>

接着，这些平台变得极具掠夺性。对于那些可能触及增长天花板的公司，它们开始搞出各种离奇的隐性收费陷阱。最让我受不了的一个例子是 Adobe：你可以按月付费订阅，但它们藏在极小的条款细则里没有明说——如果你在 12 个月或 18 个月合同期满前取消月度订阅，退订费竟然可能高达近 200 美元。这极其恶心，比如你一年去一次电影节，拍了部短片，只是在一个周末用了用这个软件，转头就多出了一笔 200 美元的账单。这伤害了非常多人，让人感到无比挫败。那个曾经充满希望、开放自由的互联网，沦为了如今这个充满掠夺、受人掌控、不断寻租的世界。

90 年代和 2000 年代它曾是一片非常特别的净土，但后来被索取榨取得越来越多。业内常用的一个词叫“平台劣质化”（enshittification），我认为它精准概括了发生的一切。

<details>
<summary>Original English</summary>
And then they started to get very extractive. For companies that maybe maybe hit the limits of their growth, they started coming up with crazy crazy gotchas. So the one that got me is Adobe has this you can subscribe to a monthly plan and they don't tell you this. It's in like the very small print. If you cancel your monthly plan before the 12 months or 18 months, they actually charge you up to like $200 to unsubscribe, which is really inconvenient If you're going to a film festival like once a year, making a short film, and then suddenly you've got an extra $200 bill for an application that you were just using over a weekend. And that's that's hit so many people and it's really frustrating that the web that was once really really promising and open and free has turned into this extractive owned rented rent-seeking world. So it it used to be a very special place in the '90s in the 2000s and more and more has been extracted. This is a term that's commonly used in shitification. I think that aptly describes everything that happened.
</details>

### ArtCraft 的开源探索与“氛围编码”

我们公司成立之初秉持的理念就是：把一切都做成开源。我们在 AI 领域构建的应用是 100% 开源的，不仅桌面端开源，底层的实际基础设施也完全开源。ArtCraft 最初的定位有点像一个偏专业级的 Higgsfield。面对所有我认识、共同成长起来的电影制作人，我们希望为他们打造一款专用工具，而不是像 Higgsfield、OpenArt 那样走以 UGC 为中心的路线。这使我们能为他们提供一款运行在本地机器上的桌面工具，让他们生成的所有文件都能直接存放在剪辑器旁边。

我们观察到了一个现象，而我的顾问们曾一度觉得我彻底疯了——他们认为艺术家根本不懂什么是开源，既不需要也不讨论它，开源从来不是艺术家使用的东西。但我们实际观察到的是，艺术家们正在用我们提供的软件进行“氛围编码”（vibe coding），构建他们自己的专属工作流。这对我们所有人来说都是前所未见的。比如有一些微短剧工作室负责为顶级微短剧初创公司交付订单，他们每月承接 3 到 5 万美元的制作量，团队规模很大，但市面上没有任何现有产品能满足他们的需求。没有人会专门为他们那种交付形式去设计定制软件。然而，他们的团队内部有人懂 Claude Code，他们能够调用 API，直接生成符合自己需求的界面。于是我们开始尝试彻底开源并推给客户，他们给出了非常积极的反馈。

紧接着我们便思考：如果我们把这一切逆转回去会怎样？如果所有的基础设施都是开源的，如果他们想要借助的所有应用形态都是开源的，他们所使用和构建的这些工具将会友好得多，也会赋予他们远超以往的创作空间。比如他们使用 Premiere，使用 Adobe。我们能做些什么，给他们提供一个可以彻底剥离不常用功能、完全围绕其特定工作流进行定制的工具？如果团队里负责不同工作环节的每个艺术家，都能根据自身需求重构 5 到 10 个不同的定制版本，世界会变成什么样？所以我们希望逆转 Web 2.0 时期发生的一切——打破垄断、合并与围墙花园，把应用程序真正还给大众。而 AI 正是我们实现这一目标的工具。于是，我们对 Adobe Creative Suite 下手了。

<details>
<summary>Original English</summary>
Our company started with the ethos of let's build everything open source. Like the applications that we built in the AI space were 100% open, not only the desktop apps but the actual infrastructure as well. So Artcraft originally started as sort of like a professionally minded Higuysfield. So all of the the filmmakers that I know and that I've I've I've grown up with, we were making a product for them to use rather than a UGC centered approach like like Higuysfield or or Open Art or so forth have. And that enabled us to give them a desktop tool that lived on their machine where all the files that they were generating lived right next to their editor. And one of the things that we observed and my advisors thought I was absolutely crazy that artists, you know, they don't know what open source is. They don't they don't need it. They don't talk about it. You know, isn't really used by artists. We actually observed artists vibe coding their own workflows on top of the software that we gave them. And that is something that like was brand new to all of us. Like there were micro drama studios that were doing order fulfillment for some of the top micro drama startups. They would do 30 to 50 grand of fulfillment every single month and they had big teams and no product out there fits their needs. Like nobody's going to go and workshop and build that specifically for the type of delivery that they need. Yet they in house have people that know cloud code and they can take the APIs and they can generate an interface that's like that. So we started experimenting with completely open source, giving it to our customers, and they really responded to that. And then we thought, what if we could turn back time on everything? Like all of these things that they're consuming and building would be much more friendly and and and give them way more capacity to create if all of the infrastructure was open source, if all of the application shapes that they wanted to leverage were open source. Like they use Premiere, they use Adobe. Like what could what could we do to give them something that they could actually take away all of the surface area that they don't use and constrain the apps to their specific workflow? What would it look like if they could do that, you know, five or 10 times for each different artist on their team that's doing a particular part of that workflow? And so we wanted to kind of undo what had happened during Web 2.0 and everything became owned and and consolidated and and gate kept and just give people back their applications. And AI really is the means for us to do that. So we took a stab at the Adobe Creative Suite.
</details>

### 用 Agent 复制 Adobe 生态与社区爆发

我们首先盯上了 Photoshop。我们给模型输入的 Prompt 大致是：“这是一套修图应用的基本架构。你在训练数据中已经学习了所有关于 Photoshop 的教程。”

我们设计了一个非常庞大的 Prompt，指示道：“我们来把这个应用构建出来。把 UI 和 UX 解耦分离，让一切都支持 MCP 和 CLI 兼容。针对每一个工具都制定实现方案，说明其工作机制。定义好数据结构以及文件格式导入器。”我们基本上就是靠这些大型 Prompt，在 24 小时之内，就得到了一个相当不错的 Photoshop 雏形。这把我们彻底惊呆了。

它不仅能正常工作，界面对我们来说还非常熟悉。它的启动速度比原版 Photoshop 快了 10 倍。当然，我们并没有完全复刻 Photoshop 的全部功能。还有大量工作要做，目前还没做到 100% 对齐，但我们正在对照需要完成的功能逐项评估，距离目标越来越近。我们之前做到了 50%，刚突破 60%，根据帕累托法则，假以时日我们能达到 99.99% 的对齐度。

我想稍微跑个题。我们团队曾讨论过是现在就进行更前沿的创新，还是先死磕功能对齐。目前的结论是，我们希望完全承接所有使用 Adobe 的艺术家的肌肉记忆。所以我们直接还原了类似 Adobe 的界面与操作质感。长期来看，我们肯定会构建带有全新 Agent 式交互界面的全新应用。但我们之所以选择现在这么做，也是为了证明一点：我们完全可以通过 Agent 真正实现某些实用且复杂的成果。

<details>
<summary>Original English</summary>
We looked at Photoshop first. We basically prompted, you know, this is the basic shape of a photo editing app. You you've consumed and trained on all of the tutorials about what Photoshop is. That's in your training data. We we laid out a large large prompt to say let's let's build out the the application. Let's separate the UI UX from that. Let's make everything MCP and CLI compatible. Let's build out plans for every single tool, how all of those work. Let's talk about the data structures, the file format importers. We basically built these large prompts and within 24 hours we were looking at a pretty good approximation of what Photoshop was. And it it kind of blew our minds away. It was functional. It was very familiar to us. It started 10 times than the original Photoshop. Now we didn't like actually cover the entire surface area of Photoshop. There's a lot of work. We're still not at 100% parity, but we're measuring ourselves against what has what needs to be done and we're getting closer and closer. We were at 50%. We've just passed 60% and in the fullness of time like Pareto principle, we could reach 99.99% parity. Um I'm going to take a little bit of a sort of a diatribe. Our team has talked about whether we take this further now or whether we just go for parity. And right now we're just we want to have we want to fulfill the muscle memory of all the artists that use Adobe. So we are going for Adobe like their sort of interface and look and feel directly. In the fullness of time we will build net new apps that have new interfaces that are more agentic. Um but we wanted to do that also as sort of like a proving function that we have actually accomplished something real completely agentically.
</details>

做完 Photoshop 之后，我们把他们全套应用基本都做了一遍，涵盖了 InDesign、Premiere 等。我真没料到这个项目会引发病毒式传播。我原本还忍着没发在 Hacker News 上，结果消息在 Reddit 上传开了。两天后，《纽约时报》就找上门要采访，我们的 Discord 社区瞬间从 3,000 人暴增。现在我们 Discord 的人数比 Jev、Suno、Higgsfield 还要多。我至今还在努力消化眼前发生的一切。这触动了大家的心弦。大家心里一直对 Adobe 及其他科技巨头心存不满，我们做出来的东西引发了强烈共鸣，也逐渐演变成了一场继续构建更多工具的运动。

那些一直抵触 AI 的反 AI 艺术家们也纷纷倒戈，他们表示：“我们真的很喜欢你们在做的事情。”他们开始使用这些应用，向我们提交功能建议和 Bug 报告，我们也在积极与他们互动。我认为我们未来能够教会他们什么是 MCP，如何利用 Agent 进行创作，并且开始剥离臃肿的界面，给他们提供更快、更流畅的工具，让他们工作得更高效。

我们没有就此止步。我们还做了各种工具，包括 CAD、Flash、一系列数字音频工作站（DAW）。这不只是我们在做，整个社区都在参与进来，可以说毫无上限。我们做完了 Microsoft Office 套件的核心应用，还有 Google Docs。各大企业、高校等各种机构都找上门来希望能使用这些软件，我们正在尽力满足各方需求。

这些应用已经被移植到了以往从未涉足的 Linux 平台上。PDF Craft 可能是最棒的一个应用，大家现在就应该去下载，你再也不用受 Acrobat 的气了。它速度极快、极其流畅。（笑声）它能在 Linux 和 NetBSD 上运行，非常出色，已经可以直接投入使用，建议大家赶紧下载体验。

我们还复刻了 Figma，甚至把它的服务端组件也做出来了。你的团队可以直接进行文档协同，底层采用了类似 Raft / Paxos 的多用户协作架构。我们现在也逐步切入基础设施领域。整个基础设施和数据模型完全开源，我们不会保留任何专有闭源内容。

还有一个由工程师带头的社区正在开发 Solid Craft。他们构建了一个开源工程内核来支撑这一切，极其稳定。借由 MCP 协议，你可以用 Solid Craft 极其迅速地完成 3D 打印项目。

<details>
<summary>Original English</summary>
Uh so we did Photoshop. We did um basically all of their apps. We did InDesign. We did Premiere. Um and uh this I I did not expect this to go viral. I was withholding posting it on Hacker News. It got out on Reddit and then like two days later like the like New York Times was asking me for an interview and our Discord went from 3,000 people to It's now got more people in our Discord than Jev, Suno, Higgfield. It I I'm still struggling to bear with what has happened. This was a It struck a nerve with people. Uh they've felt sort of maligned by Adobe and other tech companies and uh what we've built has has really resonated with them and it's sort of built up sort of this mission to build more. Uh so all of the anti-AI artists who have been pushing back against AI all of this time have you know they've sort of turned around and they're like we actually love what you're doing. They've started using these apps. They've started giving us like feature requests and bug reports and we're engaging them and I think we're going to be able to teach them this is what an MCP is. This is how you agentically create things and maybe we'll start pulling away some of these bloated interfaces and giving them things that are faster and more fluid, and let them do their work faster. Um, so we didn't stop with those apps. We've done all kinds of stuff. We've done CAD, we've done um uh uh uh uh Flash, we've done uh a bunch of digital audio workstations. It's not just us, it's the community doing these things as well. And there's really no limit in terms of what can be done. Uh so we've done the entire Microsoft well the core apps within the Microsoft Office suite. There's been Google Docs. We have uh companies and universities and all sorts of people approaching us wanting to use these things. And we're we're basically trying to fulfill all of these different asks. Um they're being used on Linux where they've never been used before. Um PDF Craft is probably the best app. You should all go download it right now. You'll never have to use Acrobat again. This is like really fast, really smooth. [laughter] It works on Linux, it works on NetBSD. It's it's brilliant. Like this one's ready to go. So go ahead and get this one. Um we did Figma. We've actually done the server component for this too and you can basically have your team collaborate on on documents. It's got like the raft paxos like multi-user setup. So we're starting to go into infrastructure too. And you know I the entire infrastructure and data model all of it is open source. We're not keeping any of it proprietary. Um there's a community that's working on Solid Craft that's led by engineers. They've actually got uh an open uh engineering kernel that manages all of this. Uh and it's it's really solid. Like the MCP you can actually do 3D printing projects really quickly with Solid Craft.
</details>

### 规模化扩张与技术架构选择

发生的一切实在太多了。我们在 GitHub 上收获了超过 30 万颗星，有 4,000 人向该项目贡献了代码，整个势头还在持续上升。它其实已经演变成了一场运动。我们正在努力应对如此庞大的贡献者涌入。我得加快一点语速了，因为前面耽误了点时间。我们目前的日下载量在 170 万次左右，而且增速还在加快。我们做了一个桌面启动器应用，你基本上可以在里面管理一切，支持全平台操作系统。

有四分之一的用户使用 Linux，这非常有意思。Linux 在历史上一直严重缺乏优质软件支持，而现在他们有了针对创意和办公场景的极高品质专业级应用，这真的很棒。我们充分尊重并热爱过去在这方面所做的所有工作，但用户显然对能够用上以前无法触及的应用感到无比兴奋。

所有这些工具对 MCP 和 CLI 都是一等支持。你完全可以通过命令行操控它们，亲眼看着它们在你面前一步步构建和装配出创意项目。

它们被本地化翻译成了 Adobe 或微软官方从未支持过的语言。比如有人告诉我们 InDesign 以前不支持阿拉伯语。我们还支持了那些已经过了生命周期的旧应用。比如 Adobe Animate 已经被官方停止维护或处于维持生命体征的状态，我们接手了它。有动画工作室跑来对我们说：“我们靠这个软件谋生，这对我们非常重要，请务必支持它。”因此发生了大量不可思议的事情，我们把软件带到了前所未有的广阔天地。这绝对不是我一个人的功劳。我只是开了个头，现在我们有了一个拥有大约 4,000 名开发者的社区，它已经获得了自己的生命力。从 CI/CD 到各个环节全由社区操盘。这太不可思议了，它早已远远超出了我个人的范畴。

<details>
<summary>Original English</summary>
Um we've had so so much happen. We've got over 3,000 300,000 uh GitHub stars. 4,000 different people have been contributing to this project and it's picking up. It's it's it's actually become sort of a movement if you will. And we're we're trying to adapt to how much influx of of people trying to contribute to this. I'm going to pick up the pace cuz I've been kind of lagging on this. But um uh we're We're about 1.7 million downloads a day and this is accelerating. We've got a launcher app that puts us on the desktop, and like you can you can basically manage everything here. It works on all operating systems. A quarter of our users are on Linux, which is really fascinating. Like Linux has been historically really, really underserved, and now they have super high quality professional apps for creative and and office work, which is it's really nice. So we've you know, we we love and respect all of the work that's been done there in the past, but people are really excited to use the apps that they didn't have access to. All of these things are MCP and CLI like first class. You can totally command these, and you can watch them build and assemble creative projects right in front of you. They've been localized into languages that were never like officially supported by Adobe or Microsoft. Like we were told that Arabic was not supported in InDesign. We've also supported these apps past their support lifecycle. Like Adobe Animate was being end of life or it was being like put on life support. We've we've picked that up. We've had basically animation studios come to us saying, we use this for our jobs. Like this is important. Please please support this. So a lot of a lot of really fascinating things are happening where we're getting this into more places than they've ever been before. It's it's definitely not me. Like I I started this and now we've got a community of like 4,000 developers. This is taken on a life of its own. They are doing everything from CI/CD. It's it's incredible. This this is way bigger than just me.
</details>

我得赶快加快节奏了，内容准备得实在太多。社区目前正在开发 300 款应用。我们还开发了一款工具，让非技术人员也能借助我们创建的基础资产（比如 UI/UX 库）参与贡献。我们正在把项目拆解成各种可复用的组件和底层原语，这样你就能直接调用优秀的 3D 库和 2D 库。

接下来聊聊技术部分。Rust 可能是本产品成功的关键。我们之前见过有人用 Electron 开发此类应用，但对于高品质的创意软件来说，你真的需要原生性能。Rust 具备大量极其优秀的特质：谷歌曾发表论文证明其缺陷率极低；它的启动速度飞快；它是实现这一目标的最佳语言。

它原生支持跨平台和多操作系统。我们在 NetBSD 上跑通了它，在平板设备上也跑通了它；它还能通过 Wasm 原生部署到 Web 端，从而实现无处不在。

作为一名工程师，今天想使用 Rust 是否必须精通它？绝对不用。我自己早在 Rust 1.0 之前就在用了，但我们团队里很多人以前根本没接触过这门语言。你的 AI Agent 完全能很好地驾驭它，你不会遇到任何阻碍。这是一门极具魅力的语言，唯一会让你头疼的大概就是编译耗时。

“Rust 能写 GUI 了吗？”在 Rust 社区里有这么一个著名的梗网站。它是否支持现代特性？答案是支持。你完全可以用 Rust 构建富 GUI 应用及 UI/UX。我们在权限管理、GitHub、系统扩展和 CI 等方面踩过不少坑，很多人都谈到过这些，时间有限我就快速带过了。我们的 CI 频繁被挤爆（笑声），于是我们开始自己搭建基础设施，在托管机房找到了高性价比的大内存服务器来解决这个问题。

<details>
<summary>Original English</summary>
I really got to pick up the pace here. I've made way too much content. So there are 300 apps being developed by the community. We've developed an app where non-technical people can start contributing and use the basis of the apps that we've created like the UI/UX libraries. We're decomposing this into all of the the components and primitives so that you can reuse them. So you'll have nice 3D libraries, nice 2D libraries. It's all great. I'll get into the technical stuff. So Rust was probably essential in this product's product success. We'd seen people doing it in Electron before, but for high-quality creative apps, you really need something that's native. Um, there's just a lot of really, really good quality things about Rust. Google had papers about like the low defect rate. It starts really fast. It's it's the best language for this. Uh, yeah. Um, it supports all all different platforms and operating systems. We've got this on NetBSD. We've got this on tablets. It natively deploys to the web via Wasm, so it can get anywhere and everywhere. Um, do you need to know Rust to start using Rust today as an engineer? Uh, definitely not. Uh, I've been using Rust since pre-1.0 times, but everybody on the team uh it's a mix of people that have never experienced the language before. Your agents will drive it just fine. You're not going to have any trouble. It is a fantastic language. The one big thing you're going to run into is compile times. Um, is it GUI yet? There's this famous website or series of websites in the Rust Rust world. Does it support like modern features? Yes. You can build GUI rich GUI apps in in Rust, UI UX. Uh, we've run into a lot of gotchas like permissions, GitHub, scaling, CI. A lot of people have talked about that. I'm going to just speed through this cuz I'm kind of running out of time. Uh, CI is like falling over. [laughter] We've been spinning up our own. We found a good place to get RAM on co-located servers. We're made of that.
</details>

### Autocraft 与全自主软件工厂

还有一个核心话题：Agent 自动开发对比人工审核。如果你在做后端开发，或者涉及数据库架构迁移、API 设计等任务，交给人类去把关；但如果是桌面应用、游戏开发以及基本具备不可变特性的领域，尽管放手交给 Agent，给予它们充分的信任。你根本不需要全程引入人类介入（human in the loop）。只要在大方向上指引好目标，直接让它跑起来去构建。我们社区里有人动用了 40 台机器，正在用 Rust 重新构建虚幻引擎（Unreal Engine），这类工作你甚至都不需要过多操心。

Autocraft 是一个完全自主的软件工厂，我们即将将其开源。它能自动摄取 Issue、完成分类评估、执行 Agent 开发，并针对所有决策进行后训练和评估。这套系统很快就会开源。简单来说，我们拥有了一整套通过代码定义的软件工厂，可以用代码来表达这一开发流程。

它能够自动接入 Issue。这相当于开源版的 CodeRabbit，把所有环节全部开源。我们在其中做了大量工作。我原本以为能留出更多时间聊技术细节，但这些成果确实非常亮眼，请大家保持关注。它将为你的所有 Agent 式开发提供支持，涵盖规划与指导项目路径的全部机制，保证工程师专注在任务上。再次强调，这是完全开源的。它所做出的所有决策都将转化为训练数据，用于评估以及决策树的后续后训练。

让我们把整个互联网夺回来，把所有软件、所有平台彻底重造一遍。我们可以把这一切都变成规范的标准协议。我们可以让整个世界开源。让我们真正拥有自己的应用、自己的基础设施、自己的协议和自己的模型，拥有这一切。

我们正在招人。如果有谁感兴趣，想投身 100% 纯开源的项目——我们的代码绝不闭源，一切都在阳光下——并且你还能有时间开发自己的个人项目，欢迎随时发邮件到 hello@storyteller.ai 跟我联系。非常感谢大家！

<details>
<summary>Original English</summary>
Um, this is a good one. So like agentic develop versus human uh review. If you're doing backend work or things that require schema migrations, API design, let your humans do that, but for like desktop apps and games and anything that's basically immutable, throw your agents at it and give them like full confidence. You don't need to be human in the loop fully. Like the upstream like directing where things go, just just let it run. Tell it to build things. Somebody in our community is is building Uh, they've got 40 machines rebuilding Unreal Engine in Rust. So you you don't even have to mind these things. Um, Autocraft is a completely autonomous software factory that we're going to open source. It ingests issues, it triages them, it does agentic development, it post-trains any vowels on all of the decisions. This will be open source soon. Um, basically we've got an entire app factory that's designed in code. You can express this. We'll open source this soon. I'm just going to have to hurry cuz I'm overtime. Uh injustice issues. This is open source code rabbit open source all the things. We're we're doing a lot here and I I thought I would save more time for the technical, but this is really good and please please look out for this. Um it will support all of your agentic development. It supports all of the sort of crafting and curating how you uh approach a project. It keeps your engineers on task. Um again fully open source. All of the decisions made by it are training data that we're going to use for evals and post training on the decision trees. Um let's take back the entire internet. Let's rebuild everything. All software, all platforms. We can we can turn all of these things into proper protocols. Um we can open source the entire world. Let's own our apps, our infra, our protocols, our models, all of it. Um we are hiring. So if anybody is interested and wants to work on 100% open source, none of our code is closed source. All of it is in the open. Um uh you get time to work on your own projects. Just reach out to me at hello at storyteller.ai and thank you so much everybody.
</details>