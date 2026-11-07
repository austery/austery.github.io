---
author: AI Engineer
date: '2026-09-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TRfzFJCJ7ZE
speaker: AI Engineer
tags:
  - ai-assisted-engineering
  - agentic-workflow
  - developer-productivity
  - human-ai-collaboration
title: 交响乐团而非软件工厂：打造高能效AI研发团队的六大核心法则
summary: Conductor联合创始人基于对顶尖AI工程师工作流的长期近距离观察，系统分享了成为组织中最快开发者的六项核心原则：身处前沿、避免过度优化工作流、设立无垃圾区、喂养信息怪兽、释放云端沙箱代理，以及将AI协作视作指挥交响乐而非流水线工厂。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Conductor
products_models:
  - Conductor
media_books: []
status: evergreen
---
### 身处前沿：在第一线捕获原生工作流与产品灵感

在AI工具快速演进的技术周期中，工程师若想保持顶尖的交付效率，首要法则就是**身处前沿**（Stay on the Front Lines）。这意味着必须保持极高的技术敏锐度，在最新工具发布的当天就立即上手试用——无论是新的代码模型、自动化插件还是新兴的编码代理。这种高频探索不仅能帮助你成为组织中最懂先进工作流的人，更是孵化创新产品的关键来源。例如，Conductor团队最初实际上在构建一个完全不同的产品（Chorus），但正因为在去年2月就成为了终端AI代码工具的极限重度用户，围绕其摸索出克隆5个代码库分支、并行管理工作树的独特流程，才最终孵化出了Conductor这款面向多代理并发管理的桌面应用。在今天，单纯依赖社交关系链自上而下被动获取工作流经验已经彻底失效，信息差会导致你至少落后行业3到6个月。

<details>
<summary>Original English</summary>

Greetings. I was at a wedding in New York this week, and there were a bunch of trendy people there, and, uh, I said I was talking to someone I'd never met before, and, uh, I told him I was getting ready for this presentation, and he was like, "Oh, that's cool. Like, what's this conference about?" And I said it was about artificial intelligence. And I just saw his eyes glaze over and he started looking back to find the next person to talk to. And I thought it was so cool to be in a room full of people who really want to hear about it. So, I-I, I'm really happy to be here. Um, I'm the co-founder of Conductor. Um, has anyone here used Conductor? Okay, great. Perfectly. Okay, great. So, uh, for those who don't know , uh, Conductor is a desktop application for managing a team of programmers simultaneously. So instead of having a bunch of terminal windows for your cloud codes, your code accesses, or your, um, some coding agent, you have one interface to manage them all. And one of the really cool things about building Conductor was that I got to see a lot of the best developers up close . I observed their workflow, I saw how they worked, I saw what they did and what they avoided. So I thought I'd gather a bunch of principles that I've seen the best engineers use, ahem , and share them with you all. Um, this is what Conductor looks like. Um, you see...Do you see this? Okay, great. Good. So, this is what Conductor looks like. Um, and here are my principles for becoming the fastest developer in your organization. So, let's start with number one , stay on the front lines. Being on the cutting edge means you're always trying the latest things practically the day they come out. Um, that means when Ultra Code comes out , you try it. That means when, uh , Slash Go comes out, you give it a chance. Hmm, it's really important to stay on the front lines, hmm, for a few reasons. Hmm, if you're building your own startup, being on the cutting edge means you'll, um, come up with a lot of new ideas about what you should actually be building. Hmm, and this literally happened to us. We were creating a completely different app called Chorus. Hmm, but we started using it , we were such advanced users of Cloud Code back in February of last year that, uh, we built our entire workflow around Cloud Code, and we started cloning our repository five times, and then we opened up the working trees, and then step by step we built Conductor as an internal tool, and we wouldn't have been able to figure it out if we hadn't, uh , stayed on the front lines. And unless you're building a startup, you should be the person in your company who always knows what the latest, uh , latest workflows are. It used to be possible to simply leverage your social graph and have information about the best workflows trickle down to you. Things are moving too fast now. You will always be three to six months behind if you do this. Therefore, it is very important to stay on the edge.

</details>

### 不要试图战胜市场：基于真实阿尔法权衡工作流定制成本

尽管保持在技术边界至关重要，但紧跟前沿也伴随着陷入**中智迷因**（Midwit-meming）的风险——即把全部精力消耗在打磨工作流工具本身，而非产出实际业务成果。为了平衡这种倾向，团队总结出一条核心启发式准则：**不要试图战胜市场**（Don't Beat the Market）。当你评估一个复杂的定制化工作流时，应当反问自己：“为什么这个流程目前不是行业的默认标准？”如果某种流程对所有场景都普遍有效，底层的模型提供商（如 Anthropic 或 OpenAI）迟早会将其标准化并直接内置于产品中。这类似于金融领域的**有效市场假说**（Efficient Market Hypothesis: 资产价格已充分反映所有可得信息），除非你掌握了模型并不知晓的**真正阿尔法**（True Alpha: 专属业务特异性认知或代码库特殊约束），否则不应过度工程化你的本地流程。例如在 Conductor 内部，团队需要极速渲染长上下文聊天，React Query 的性能调优直接决定了核心体验，这种特异性信息才是值得投入时间深入优化的关键资产。不要成为配置了极其复杂的编辑器环境却无法交付代码的极客。

<details>
<summary>Original English</summary>

And there is one important word here - close. There is a danger that if you are on the edge, you can do what I call "midwig- meming," where you spend all your time working on your workflow rather than actually doing the work. So we internally developed a heuristic for this . We call this "don't beat the market." Don't try to beat the market. Um , uh, the concept here, as a heuristic to use when you're trying to decide whether you're on the edge or on the edge and, uh, too deeply immersed in, uh, the latest trends, is that you should ask yourself, "Why is n't this workflow the default workflow ?" For example, when, uh, Ralph loops became more and more popular, uh, you have to ask yourself, "Is it worth spending a bunch of time optimizing my workflow to work with Ralph loops?" Because if Ralph's cycles work for everyone, if they're the default workflow , then you should probably just wait until Anthropic or OpenAI or someone else builds that workflow into the standard housoner. Um, you can think of it as something like the efficient market hypothesis, where , um, if you don't have real alpha, uh, you shouldn't optimize your workflow too much. Um, by true alpha I mean some information about your users or your codebase that the models may not know about. So, an example for us: we... We are a chat application. We need to render very long chats very quickly, and performance is important to us. Therefore, we need to spend a lot of time optimizing our React queries to render chats quickly, and we are willing to make sacrifices in other parts of our codebase to make this happen. So, if you have some alpha, for example, some information about the app you're building that the models might not know about, then you should take the time to work through it. Otherwise, don't make memes about midwigs. Don't be the person who has a great Emacs setup but doesn't actually get the job done.

</details>

### 设立无垃圾区：守卫代码死角与高杠杆提示词上下文

在拥抱AI生成代码的同时，绝不能沦为无脑合入海量代码的极端代币主义者。高产出团队的第三项法则是划分出**无垃圾区**（Junk-free Zone）——即对代码库与文档的关键区域设立极其严苛的人工审查标准。若缺乏对代码盲区的防守，系统将迅速恶化并被迫多次推倒重构。在工程落地层面，数据库迁移文件（migrations）等核心链路在持续集成（CI）阶段必须强制执行人工审查。更为关键的是作为全局指令枢纽的**上下文规范文档**（如 `CLAUDE.md` 或技能设定文件）。这些文件类似于每天向刚入职的顶级实习生耳边低语的核心准则，每次代理启动都会被完整加载进上下文窗口中。顶尖工程师会花费大量时间手工打磨这些高杠杆文档，确保其精确、凝练且绝对由人类把控，从而从源头校准AI代理的执行质量。

<details>
<summary>Original English</summary>

Okay , thirdly. Create clutter-free zones. So, at Conductor, we have a term—a junk-free zone. A junk-free zone is a part of the codebase or part of an application that requires very strict human review. And we're actually, I think, a little unusual in that sense. I think a lot of people think that we're, uh, pure token maximalists and we're just wading through 30,000 lines of PR, but that's not really the case. We're actually quite careful with certain parts of our codebase, and then very liberal with others. This is important because if you are not careful about blind spots , your code can get into a very tricky spot. And this actually happened to us. We had to rewrite our entire app several times because we weren't careful about blind spots. Specifically, we have a migrations file, and, uh, in our CI, any change to the migrations file requires human review. We also believe that not everything written in Slack is Slack-free. This was not written by artificial intelligence, it was written by a human. All of our documentation, uh , all of our cloud MDs, like all of our skills, we spend a ton of time making them good. Um, and that's also what I've seen from all the best builders up close . They spend an inordinate amount of time on Cloud MD or their skill files. Um, and I think another way I looked at it is if you had a new intern joining your company and you had the opportunity to whisper something in his ear every time he started working. Every day, every time he sat down, you could whisper something in his ear. You would probably think a lot about what you are whispering in their ear. And that's what Cloud MD or Agent MD is. It's like information that is loaded into the agent's context every time it starts working. Um , and so you probably want to think a lot about this, um, about this.

</details>

### 喂养信息怪兽：构建全组织上下文沉淀的中心化数据库

要让AI代理在复杂的企业协作中发挥最大威力，核心瓶颈往往在于业务上下文的缺失。因此，第四项核心法则是**喂养怪兽**（Feed the Beast）。Conductor 内部研发了一个名为 CIA（Conductor Internal Agent）的中心化代理系统，其底层是一个记录组织内部一切动态的 PostgreSQL 数据库。无论是 Slack 中的日常沟通、Discord 中的用户缺陷反馈，还是团队日常会议的转录记录，都会被实时捕获并结构化写入中心数据库。这种机制消除了各个沟通工具中的信息孤岛。赋予代理直连 SQL 的查询工具，使其能够以最低的摩擦成本调取全量组织历史和业务细节，从而在处理任务时拥有与核心团队成员对齐的深厚背景知识。

<details>
<summary>Original English</summary>

Um, okay, four. Feed the beast. Um, in Conductor we have, um, an internal tool that we call the Conductor Internal Agent. Um, and he, um, we're also known as the CIA. And the CIA is, in essence, a centralized database of everything that happens in the organization. So every time a new message is sent to Slack, the CIA intercepts it. A CIA agent will see that a new message has been sent to Slack , he will intercept it and save it in the post grass table, uh-huh. Whenever a user has a bug request in Discord, the same thing happens . Every time we have a meeting, we record it, uh, and it goes to the CIA. We call this " feeding the beast" because you want your agents to be effective at your company, you want them to have as much information and context as possible about how you operate. And the best way to do that is to have a centralized place for all the information. I think this tweet sums it up pretty well. Uh, it's very efficient to just put everything in a database and then give your agent a SQL tool and let it handle the rest.

</details>

### 自由巡回代理：云端持久沙箱、实时团队协同与自治派生

为了突破单机算力与生命周期的物理瓶颈，第五项法则是解开束缚，引入**自由巡回代理**（Free-roaming Agents）。随着底层大模型推理时长与复杂规划能力的跃升，将代理运行在个人笔记本上存在致命弱点——一旦合上电脑屏幕，执行就会被迫中断。因此，必须将代理部署至独立的云端安全沙箱（Cloud Sandbox）中，赋予其安全探索代码库、执行长任务并自我衍生子任务的能力。基于这种云端常驻架构，团队能够衍生出两项革命性的协作范式：
* **实时人机交互协作**：团队所有成员不仅能实时查阅每位工程师及其代理的运行状态，还可以跨工作区进入协作空间，直接在AI生成的代码上下文内进行实时对话与细节调整（例如就代码缩进风格发表即时评论并协同修改）。
* **基于API的自主调配**：代理能够通过暴露的开放接口互相触发或自我唤起。开发者只需在移动端（如 Telegram、Slack）向常驻个人助手发送简短指令，助手即可通过 API 在后台自动创建云端工作区、派发任务并持续推进代码交付，实现完全异步的自动化研发。

<details>
<summary>Original English</summary>

Good. Next— free-roaming agents. Give your agents plenty of room to play. Give them a sandbox where they won't die, where they can explore your codebase, where they can work on really complex tasks, where they can know they won't be shut down when you close the laptop lid. Uh-huh. Give them the opportunity to create more of themselves. Uh-huh. Give them ways to collaborate with other agents and other people. Uh-huh. I think it's really important to have free-roaming agents and that concept, and why it's important is because the models are getting better and they can work a lot longer and there will be a lot more of them. So if they are confined to your laptop, they won't be as effective as if they were free to move around. Uh, another important thing is that once you give them a sandbox to play in that's not limited to your laptop, there's a bunch of really cool things you can build off of that. Um, and we've built some of these things into Conductor, and I'll go over some of these cool things briefly. So, this is Conductor. I'm going to make it a little bigger. Um, and this is actually a new version of Conductor that's coming out this week, and it's focused on cloud collaboration. So what I said is that you need a space, a sandbox for the agents to play. You need a free access agent. And so you'll notice that each workspace has a little cloud icon at the top, and I can click on that and get information about the sandbox that the agent is running in. Um, and what's great about this is that I can close my laptop and the agents will continue to work. Until this week, every, um, every task in Conductor was built on a task tree, but now they're in a cloud sandbox. They are agents of free access. But what's also cool, um, that we can build on top of the cloud is collaboration. So as you can see, I'm going to make it even bigger. It's me. And here is a list of things I'm working on. And you can see that I am in the conductor organization. But if I scroll down, I can see what Cadence is working on. I can see what Lewis is working on. I can see what Taiwan is working on, and I can see that I can see Jackson's face there. I can click and see what he's working on in real time. Um, and I think collaboration is one of the most important new concepts in these tools that no one is really talking about right now. Um, collaboration is important because, um, not just because it's true that all great things are created by teams of people. As if they are not created by individuals. They are created by teams. Um, but also because the models are getting better, as we saw over the course of two days of Fable, you can become much more ambitious about the things you create. And if you get more ambitious, you'll need more people and more agents to work on these things. So, I'm going to go over to the workspace that Caden is working on. Uh, here's this one, and I'll say, uh, I can review the changes he made. Uh, I'll make it a little smaller and it'll look good, but I'm just asking, uh , can we actually use tabs instead of spaces? And Caden gets to see this message coming in real time, and he can also chat in the workspace. So, we see here what he's typing. So, I see what Caden is typing. Let's see what he says. He seems to be typing a lot. Okay, maybe he stopped typing. I'll give him a second to look at it, but the bottom line is that now we can have collaborative workspaces that can be shared in real time with people on our team. Uh, okay, he's typing again. Okay, back to the agents who escaped. Good. So, uh, I'm really excited about this, and we're rolling it out to all Conductor users this week. Hmm, I think collaboration will be one of the most important changes to the interface this year. Another really cool thing about the cloud is that, um, giving agents free space to work is that we can give agents an API to self-launch. So, I have here my open claw. Uh, this is my open claw called Lord Crandon. And you can see that she has, I don't know how well you can see this text, but she has access to the Conductor API. And so, from my phone, or from my Telegram, or from Slack, or wherever I am, I can say, "Hey, can you create a new workspace for me that makes all the buttons blue?" And so I'll send this to Lord Crandon, and Lord Crandon will have access to the Conductor API, and so he can get started himself. Um, so let's see what it's doing here. Okay, just created a working environment. The agent is working on it. And then I can go to my Conditor where I am, but he is still setting up the workspace and will work for me while I am gone. So I'm really excited about all the cool things that can be created based on free agents.

</details>

### 交响乐团而非流水工厂：以心流与匠心重塑人机协作的本质哲学

本次分享最根本的心智模型与哲学原则，是**将协作视为交响乐团，而非软件工厂**（Orchestras, Not Factories）。当下的技术语境中广泛充斥着“软件工厂”的比喻，但工厂的意象代表着冰冷机械的装配线与无差异的量产流水作业；工程师绝不应该退化为坐在黑暗车间里仅仅负责按按钮触发功能发布的流水线工长。人与AI协同的理想状态应当如同指挥一个声部交融的交响乐团——人类身处创作与心流的中心，手挥指挥棒协调不同声部的代理与工程师团队，在需要时深入微观细节，在常态下站在宏观视角掌控全局节奏。软件工程应当保留属于人类的匠心、温度与创造乐趣。将以上六项原则整合，便构成了成为高能效构建者的核心助记框架 **FOLLOW**：
* **F**ront lines: 身处前沿
* **O**utside the market: 避免过度对抗市场
* **L**itter-free zones: 打造无垃圾区
* **L**og the context: 喂养信息怪兽
* **O**pen range: 释放自由云端沙箱代理
* **W**hole orchestra: 构建以人为中心的交响乐体系

<details>
<summary>Original English</summary>

Good. The last principle I want to talk about today, and the title of this talk, is orchestras , not factories. Today's entire presentation is dedicated to software factories, and to be honest , I kind of hate that term. I think that's the wrong way to think about these new tools that are emerging. I think when I think of a factory, I think of automation, and I think of how there are a lot of amazing things about automation, and how it makes our lives more efficient, and we can create more of everything. But I don't want the future to be built around factories. I want the future to feel like I'm human. I want to be in the flow. I want to be in front of an orchestra, like waving my wand, and we, and I wave it this way, and this team of agents starts working, and then this intertwining of people and agents starts working when I go here, and I can, when I want, zoom in on the details, but most of the time I can zoom out. And I don't think the future should be where we're running a bunch of agents, and we're like factory managers, like the ones pushing buttons, making agents release the next feature. We tried this about 10 years ago with the term " function factories," and it just doesn't work. I want my software to feel human and crafted. I want to feel like a human being at the center of all of this, and I think that because we're all building these tools, we actually have a responsibility to make the tools great for people. I think it's really important to use words that make us excited, feel empowered, and feel like we're in the flow and enjoying ourselves . And so I don't think the future, uh, is anything like that . I don't want to be, I don't want to be in my dark factory. I don't want to be a line manager. I want to feel like this . I want to be in the flow. I want to have fun. I want to create things. I want to feel like Steve Jobs, designing the Mac with a team of amazing people and AI agents, all in one place. For example, I want to feel like I'm in an orchestra. So, here are my principles for being the best builder in your organization. Uh , stay on the edge. Don't try to beat the market. Create zones without slots. Feed the beast . Free- roaming agents. And think about orchestras, not factories. I came up with this handy abbreviation to remember it. Follow. Good. So, uh, thank you so much for inviting me. I will be there. Don't be shy about asking questions. And, uh, see you on the internet.

</details>