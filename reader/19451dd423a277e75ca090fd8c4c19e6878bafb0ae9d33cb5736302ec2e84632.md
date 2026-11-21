---
author: AI Engineer
date: '2026-08-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LZuWZRze3MU
speaker: AI Engineer
tags:
  - ai-native-software
  - ai-agent
  - human-computer-interaction
  - multimodal-interface
  - computing-history
title: 重构人机协同：从AI Agent迈向AI原生软件的新纪元
summary: Daily联合创始人Kwindla Kramer回顾了从1945年万尼瓦尔·布什的Memex设想到如今AI Agent的80年数字计算史。他指出，我们正处于“智能时代”的起点，正如从Web网页演进到移动App，AI软件也将从简单的Agent和多模型容器迈向真正的AI原生软件。他通过“知识导航仪”的演进与多人AI原生游戏《Gradient Bang》，展示了异步上下文压缩、动态UI生成等全新交互范式。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Kwindla Kramer
  - Vannevar Bush
companies_orgs:
  - Daily
products_models:
  - Pipecat
  - Gradient Bang
  - Knowledge Navigator
media_books:
  - As We May Think
status: evergreen
---
### 计算历史的演进与智能时代的开端

我们目前正站在一个全新时代的起点——**智能时代**（Intelligence Age）。为了理解我们正在构建的未来，有必要回顾数字计算约80年的发展历史。1945年，美国工程师与科学管理者**万尼瓦尔·布什**（Vannevar Bush）发表了著名论文**《诚如所思》**（As We May Think）。在这篇前瞻性论文中，布什精准预测了屏幕文档显示、OCR文字识别、语音转文字（Speech-to-Text）、超文本（Hypertext）、搜索引擎、脑机接口以及一种被称为**Memex**（记忆延伸器）的信息管理设备。Memex的设想不仅是个人电脑的雏形，更启发了后续几代计算机科学家对人机交互的探索。

回看这80年的计算演进，我们可以清晰地划分出几个关键节点：从早期的**电子管/机电计算**，到存储程序计算机，再到40年后的**个人电脑**（Personal Computer），以及如今正在共同开创的**AI Agent**时代。在20世纪50年代，计算的核心任务是构建编程语言与编译器，用数学的严谨性来传递人类意图。到了60年代，Ivan Sutherland的Sketchpad等系统开启了**图形化编程**（Graphical Programming）与人机双向交互的先河。进入70年代，**关系型数据库**（Relational Database）与**面向对象编程**（Object-Oriented Programming, 如Smalltalk）相继诞生，为处理更大规模的数据和更复杂的计算奠定了理论基础。这些底层积淀最终孕育了80年代个人电脑的爆发，带来了诸如**VisiCalc**（历史上首款电子表格软件：开创了二维交互式数值计算的新范式）这样具有变革意义的软件工具。

<details>
<summary>Original English Source</summary>
Good morning. I know a lot of you in this room. It's great to see you. Welcome to the voice track at AI Engineer Worlds Fair. Uh for those of you who don't know me, my name is Quinn Low Holman Kramer. Uh I work at a company called Daily. We make developer infrastructure for real-time audio, video, and AI. And we're the team behind Pipecat, which is the most widely used framework for building voice agents today. Pipcat is open source and vendor neutral. It's used by companies like AWS and Nvidia and Anthropic and thousands of startups and scaleups and enterprises. And today I'm going to talk about what kind of agents we're building today, including voice agents, but not just voice agents. and what I'm interested in building next. And I'm going to try to put all this in the context of the roughly 80year history of digital computing so far. So, we've got a lot to cover. We're going to go fast, but we're going to start in 1945 with an essay called As We may Think written by an engineer, an academic, a civil servant named Vanavar Bush. Bush deeply understood technologies ranging from analog computers to photography to radio to radar and as we may think is a extraordinary piece of writing. The essay predicts the development of among other things document display on a screen and document scanning and OCR and speech to text and text to speech and programming languages and hypertext and search engines and data networks. Something like the GoPro camera. something weirdly like the Amazon Kindle store and voice interfaces and brain computer interfaces. And I've been thinking a lot about as we may think lately because Bush wrote this essay right at the very beginning of the computing age. And I think it feels to most of us like we're working right at the beginning of a new age, the intelligence age. So what will we build? Well, at the moment we're building agents and we're having a lot of fun doing it. And a lot of the AI engineering work we're all talking about this week is focused on building a full coherent software stack for AI agents.
...
So let's keep going back in time to in order to think about this future. Here's a timeline Venavar Bush lays out in as we may think. He talks about the abacus which was both an immensely useful device for doing practical everyday mathematical calculations and also an incredibly important theoretical tool that led to ideas like numeric place value and the concept of zero. And Bush talks about the massive jump from the abacus to the state-of-the-art electromechanical keyboard calculating machines that he had in 1945. And then he posits that we're about or he is about to uh witness and help create uh an an equally large leap to what he calls the arithmetical machine. And then he goes a step even further than that. And he invents or designs in that essay a device he calls the mimics. And we have a little bit of an advantage over over Bush in 1945. We've seen 80 years of computing play out. So we can modify his timeline a little bit. We can go from the abacus to the stored program computer to 40 years later the personal computer and 40 years after that this AI agents era that we're all collectively helping to invent and create and bring into being. So the question for me is what did we build to go from those very first digital computers in the 1940s to the personal computer in the 1980s? Well, in the 1950s, the big job was to figure out more effective ways of transmitting human intent to these new computing machines. We built the first programming languages. We wrote the first compilers. And the the theoretical underpinnings here were figuring out how to combine the elegance of mathematical formalisms with something a little bit more like natural language. And then building on that, in the 1960s, the challenge was to make these machines interactive, make these machines capable of a two-way dialogue with humans. The 60s also saw the birth of graphical programming with systems like Ivan Sutherland's Sketchpad. And the 60s were an amazing era for science fiction. Even though almost nobody had access to a computer, the computer became a big part of the popular imagination. The idea of a computer really resonated with people and ideas matter.
...
And by the 1970s, computers had become powerful enough that the next big job was designing abstractions that could scale to much larger amounts of data and much more powerful computing substrates. We got relational databases which introduced new theoretical underpinnings for data manipulation and we got declarative languages which leveraged those new theoretical insights and programming languages in general continued to evolve in what to me at least are really amazing ways. We got Small Talk and object-oriented programming in the 70s and all of this set the stage for the personal computer in the 1980s. The Macintosh shipped in 1984. Windows 1.0 ship in 1985 and Microsoft's mission statement was a computer on every desk and in every home and incredibly Microsoft delivered on that mission statement and we got a computer on every desk and in every home because these new personal computers delivered real amazing tangible benefits. Take VisiCalc for example which was the first spreadsheet program. A truly new abstraction for doing computation numerical computing two-dimensional interactive so durable and so useful that probably most of us in this room use a direct descendant of Visical regularly Google Google Sheets or Microsoft Excel or whatever. Or put another way, this was a spreadsheet in 1957 and this was a spreadsheet in 1985. And I think a lot about VisiCalc these days too because I think VisiCalc is an example of how transformative new technologies can be in the way of delivering a capability that used to require a lot of specialized people and specialized knowledge and making it generally accessible. And I think VisiCalc is a potentially a counterargument to the argument or the fear or the concern that AI is going to lead to mass unemployment because Visical didn't put accountants out of business. Instead, it made much much much more accounting like work possible. And it made new categories of work possible that we couldn't even really conceive of when a spreadsheet or doing a screen's worth of calculations as we think about it today took a room full of people.
</details>

### 从知识导航仪到现代AI Agent栈

在2026年，微软CEO Satya Nadella指出了构建Agent面临的核心挑战：我们需要一个将“模型、数据、工具”三者有机结合的环路系统，实现工具的**渐进式披露**（Progressive Disclosure: 动态按需加载工具以节省Token并提高效率）。这种对于人机交互未来的设想，早在1987年苹果发布的经典概念视频**《知识导航仪》**（Knowledge Navigator）中就有所体现。该视频精准地描绘了折叠平板、触摸界面、具备鲜明个性的语音助手、跨越全局与私有数据的访问权限、实时视频呼叫集成，以及任务的自主代理执行。

在计算技术走向移动化与多模态的进程中，90年代的**互联网与Web**彻底打破了文本、音频、视频与数据的界限，将它们融为一体。随后，智能手机的普及将多模态网络计算机放入了每个人的口袋。科幻电影如《少数派报告》（Minority Report，其手势界面基于MIT媒体实验室的研究）和《钢铁侠》（Iron Man，展现了人工智能助手**Jarvis**的雏形）进一步拓宽了人们对交互界面的想象空间。时至今日，我们不仅在软件开发中嵌入各种**Co-pilot**，更在构建企业级、跨越整个组织的复杂Agent控制系统。

<details>
<summary>Original English Source</summary>
Here is Satia Nadella talking a couple weeks ago on a crossover episode of the no priors and latent space pod about the challenges of building agents in 2026.
>> Some sort of
>> That's right. So, so in some sense you kind of want the harness to define the models, the the data uh and the tools and so that so that you have a loop across those three and so what we are trying to first of all make sure is each of our products that we build right whether it's GitHub copilot or the security cop the stuff we showed with mdash or even the discovery for science it doesn't matter all of them are multimodel harnesses um with tools tools access so that you can do this progressive uh disclosure of tools even so that they're token efficient uh and then you're feeding it with very rich context.
So if you were here last year at AI engineer worlds fair you could draw a through line from the things we were talking about last year to loops and tool calls and context engineering and the stuff we're focused on this year to some emerging ideas. Uh you can hear that in Nadella's clip just there. I think of this as kind of agents plus+ like multi-model harnesses and software co-pilots embedded in every single piece of software organization level harnesses. So how do we go from agents to agents plus to the next thing beyond agents?
...
So, if we were here in the Moscone Center in 1985 and these two interfaces, the Macintosh system 2 and Windows 1.0 were state-of-the-art, what would we have said the world would look like in 10 or 20 or 30 or 40 years? Well, we actually have a really great example of a prediction from that time, like as we may think, another famous document in the history of human computer interaction concept video from Apple made in 1987 called Knowledge Navigator. This is very much worth tracking down online and watching all of if you haven't seen it. I'm just going to play about 20 seconds from the middle.
...
So the video shows a foldable tablet, a touchscreen interface, a conversational voice assistant with a really strong personality, access to both global and personal information, real-time video generation, real-time computer vision, seamless video call integration, delegation of complex tasks for autonomous execution, and what we might call today continual learning. And it's really, really clearly influenced by, as we may think, but it's also quite different. It really is updated for 40 years of progress and it really does sort of preage this AI agents era we're in now in a way that Vanavar Bush's mimics didn't and maybe couldn't. The knowledge navigator video divides our timeline I think quite neatly in half. And hold that thought because we're going to come back to it.
The 1990s were about the network. First local area networks and dialup and then the internet and the web. And with the benefit of hindsight, I now think that the single most important thing about the web was that it was multimodal from the very beginning. More even than the gooies of the 1980s, the web anticipated that text and audio and video and data were not different things to be used in different programs. They belonged together. And in a real sense, the web was an attempt and a conscious attempt on the part of a lot of people building the web to make that knowledge navigator video real. Then in the first decade of the new millennium, the big job was to make all of this computing stuff mobile and continually connected to put this new multimodalorked computer in your pocket. Literally to give a supercomput to everybody in the world that they could carry around in their hand. And as with the 1960s, there was an efflloresence of like futurism on screen in the first few years of the new millennium. And I think it was because computers you could carry around with you and cameras everywhere and a kind of Moors law for pixels making screens super cheap really gave us a chance to think through what we thought the future would look like in a new way. A lot of stuff we could almost but not quite build was cohering in the minds of people working on these machines. And the best and most famous Hollywood computers from that era were created by John Undercoffler for the film's Minority Report and Iron Man.
...
I co-ounded a startup with John in 2006 to make the Minority Report interface into a commercial product. This is our demo reel from 2012, 6 years into that work. This long project to build the multimodal, multi-device, multi-screen, multiplayer, ubiquitously connected computer is still what I'm working on 15 years later in 2010s we built out the cloud which laid the groundwork for the infrastructure and data centers and data capacity we would need to scale up AI training and inference which brings us to now we're building agents and we're starting to think about agents plus
</details>

### AI原生软件的下一代交互范式

正如我们当年从单纯的HTML网页（Web Pages）演进到高度互动的Web App与移动原生应用，AI软件的发展也将超越单一的Agent，向着更加系统化、**AI原生**（AI Native）的方向迈进。前不久，Tavis团队发布了利用当今已成熟的技术重新制作的“知识导航仪”视频，演示了完全由LLM驱动的实时无缝日程管理。

为了更深入地探索AI原生软件的潜能，Kramer展示了团队正在开发的一款名为**《Gradient Bang》**的多人游戏项目。该游戏将大语言模型（LLM）作为人机和机机交互的核心引擎，通过实时Agent编排展示了数个具有代表性的AI交互范式：

* **异步非阻塞上下文压缩**（Asynchronous Non-blocking Context Compression）：允许系统在后台对历史上下文进行持续的总结和归档，保证实时对话流的低延迟与高上下文效率。
* **渐进式技能加载**（Progressive Skills Loading）：根据用户当前的场景和指令，按需动态加载Agent所需的工具包和执行逻辑，而不是一次性载入全部依赖。
* **动态UI生成**（Dynamic User Interface Generation）：界面不再是硬编码的静态组件，而是由AI根据当前的任务状态与对话上下文实时渲染和调整。

这些探索表明，未来的软件将不再是人类单向输入、机器被动响应的工具，而是能够进行多模态感知、自适应界面生成、并在网络中自主协同的多智能体生态。

<details>
<summary>Original English Source</summary>
I think we can also start to think about the next thing the AI native software that is to agents what today's internet is to the web pages of 1995 and one way to think about the story is this. We went from the calculator to the computer to the personal computer to the global cloud computer and now we actually have the ability to build the mimics and Jarvis from Iron Man and knowledge navigator from that 1987 video for real completely working. And by building those things, we'll figure out what we want to build next. A couple of weeks ago, the team at Tavis released a reimagined knowledge navigator video. This time entirely built on real and available technology. I'll just play another 20 seconds of this, but like the original knowledge navigator video, this is worth tracking down and watching in full.
...
So, the full 4-minute video is one take, completely real. And when you watch it, it really does feel both like the knowledge navigator video from 1987, familiar, but built on real technology, and like something brand new. And I'll just close with a massively multiplayer game project I've been working on with some friends as a canvas to really think about what AI native software can be. This game is built from the ground up with LLMs as the core of every interaction at every moment in the game. There are hundreds of inference calls happening and we couldn't have built anything like this even a year ago. Oh, sorry. Welcome to Gradient Bang, a multiplayer game that showcases real time agent orchestration. Gradient Bang demonstrates several patterns for AI sub agents such as asynchronous non-blocking context compression.
>> Okay, make a note for later. We are going to eliminate Hilly Tatley from existence.
>> Noted.
>> Long running sub aents that share context.
>> Eagle is on five trade loops. Hawk and Raptor are on five exploration loops each. Your fleet is busy.
>> Progressive skills loading.
>> How much does your average ship cost?
>> Ships range quite a bit, Captain.
>> Dynamic user interface generation.
>> Show my task history.
>> Certainly.
>> Uh, hide the map.
>> Okay.
>> And conversational voice.
>> No, I don't want to exchange it. I just want to sell it for cold, hard cash, please.
>> I'm afraid the galaxy doesn't allow you to be shipless and hitchhike.
So, I went long. I have to wrap up. But I will say that the first version of this new draft talk was an hour. So, I have a lot more things I'm super excited to talk about with all of you. So, if you are interested in this stuff, come find me. We have a booth on the show floor. I'm online everywhere. And I'm excited to build agents because agents are awesome, but also to build the next next thing, too. Thank you.
</details>