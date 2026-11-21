---
author: a16z
date: '2026-04-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yiJOTCRVWjc
speaker: a16z
tags:
  - agentic-workflow
  - homeschooling
  - voice-interface
  - personal-automation
  - parenting-tech
title: AI Agent 育儿实录：从硅谷创始人到 11 个 Agent 的家庭自动化实验
summary: 曾是 YC 创始人的 Jesse Genet 分享了她如何利用 AI Agent 彻底重塑育儿与居家教育。通过构建 11 个高度专业化的 Agent，她实现了高效教学与个人工作的平衡。Jesse 深入探讨了语音交互、自主 Agent 的生成、安全性风险以及 AI 如何通过消除琐碎劳作，潜在地促进生育率回升并开启家庭生活的新纪元。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jesse Genet
companies_orgs:
  - YC
  - OpenAI
  - Anthropic
  - Lumi
products_models:
  - OpenClaw
  - Obsidian
  - Loom
  - Mac-Mini
  - Daylight-display
media_books:
  - Building the Foundations of Scientific Understanding
  - Catcher in the Rye
  - The Diamond Age
status: evergreen
---
### 开场：从“半退休”到 AI 痴迷

**Jesse**: 我本来已经打算在接下来的五年里不再挑战自己去构建技术性或困难的东西了。我真的想陪在孩子们身边，我需要这段休息。但基本上，那已经不再是事实了。我有一个奇怪的超能力，就是我极其渴望让 **Agent**（智能体）帮我干活。我让我的 Agent 学会了如何自主构建其他 Agent。所以，我可能会说：“伙计们，我们需要另一个 Agent，”然后它们居然真的可以在我不碰机器的情况下把它们运行起来，这有点疯狂。但最初的几周非常艰难，那种痛苦程度是我不希望普通人去经历的。

<details>
<summary>Original English</summary>

**Jesse**: I was resigned to not challenging myself to build technical or hard things for like the next 5 years or so. I really want to be present with my kids. I need to take this break. Basically, that is no longer true. A weird superpower of mine is just how incredibly motivated I am for agents to do work for me. I got my agents to learn how to build other agents on their own. So, I could be like, "We need another agent, you guys," and they actually can spin them up without me touching the machine, which is a little crazy, but the first few weeks were very rough. It would be a level of pain that I wouldn't want an average person to go through.

</details>

**主持人**: Jesse，非常高兴你能来到这里。我想你已经在 X 上成为了我所谓的“现象级人物”，你发布的视频展示了你是如何在家教育（homeschooling）你的家庭的——四个五岁以下的孩子。我只能说，愿上帝保佑你，你太了不起了。

<details>
<summary>Original English</summary>

**Host**: Jesse, it is so fantastic to have you here. Um, I think you uh you've been what I would call a viral sensation um on X, posting videos of how you're homeschooling your family, uh, four children under the age of five, which all I can say is God bless you. You're amazing. Um, God bless.

</details>

**主持人**: 但我们也想要你的秘密和技巧。Sarah 和我都是年幼孩子的母亲，我们经常谈论 AI 如何影响教育，如何影响家庭的未来。而你通过视频成为了一个不可思议的力量，展示了你如何在处理家务和支持家庭的过程中使用 AI。所以，我们想先了解一下你是谁，以及你是如何对将 AI 用于在家教育产生如此浓厚兴趣的。但也请告诉我们你作为**硅谷创始人**的前期职业生涯。

<details>
<summary>Original English</summary>

**Host**: But we also want your secrets. We want your tips. Um, as as you know, um, Sarah and I are both moms of young children and we talk a lot about how AI is impacting education, how AI is impacting the future of the family. And you've become just such an incredible force with your videos um, on X of how you're using it in a bunch of different tasks around the house and a bunch of different tasks around supporting your family as as a homeschool mom. So, we want to start with who you are um and and how you got so interested in in using AI for home school, but but tell us about your your previous career too um as as a Silicon Valley founder.

</details>

**Jesse**: 是的，我很多年前创办了一家公司。时间过得真快，但我曾是一名 **YC 创始人**，做过一家获得风投支持的公司，走完了整个周期，几年前把它卖掉了。所以，一方面我会说我有技术背景；另一方面，我会公开承认我的合伙人才是技术联合创始人。我希望人们明白，虽然我一直在这个圈子里混，参加过无数次工程师会议（有些我能跟上，有些我也听得云里雾里），参加过很多产品周期和评审，这给了我词汇量，但直到大约六个月前，我才真正打开终端尝试自己构建一些东西。

我觉得我们正生活在一个非常迷人的时代。直到最近，在创办了自己的公司之后，我才感觉到现在的工具已经好到我可以真正使用**自然语言**来构建东西了。所以，过去的六个月对我来说就像是构建领域的“**寒武纪大爆发**”。当然，最近几个月有了 **OpenClaw**，我彻底着迷了。那只能被描述为一种痴迷。因为我几乎一直在不停地构建，但即使这样，我日常其实花了很多时间陪伴孩子。我一直在寻找如何构建与我生活相关的东西。

<details>
<summary>Original English</summary>

**Jesse**: Yeah. So, I I I started a company um many years ago now. Um time time flies, but I was a YC founder um you know um did did a venturebacked company kind of full cycle. Ended up selling it a few years ago. And so, I do you know on on the one hand I'd say I have a technical background. On the other hand, I would admit openly that my co-founder was the technical co-founder. So I I want to be like I want people to understand yes like I've been swimming in these waters. I've sat in many an engineering meeting where I was sort of following along and sort of lost. Uh I've sat in many you know product cycles and and reviews. So it gives me a vocabulary but I hadn't opened terminal to try to build something myself until maybe six months ago. So, I think we're living through a really fascinating time where only recently after, you know, running um a company myself did I feel like now the tools are so good that I can really use natural language to build things. And so, the last six months have been um like a Cambrian like explosion for me of of building. And of course, the last few months where we have the uh open claw, then I went completely obsessed. So, I'm I'm happy to discuss that. But I went down a complete obsession. It can only be described as an obsession. Um because I I've just been building almost, you know, non-stop, but when I say that on a datab basis, I'm actually spending a lot of time with my kids. And so, I was trying to find like how can I build things that are relevant to my life. So, I know we're going to dig into that, but that's a little bit of how I got to now.

</details>

### 家庭教育流：语音笔记与自动化记录

**主持人**: 能谈谈六个月前那个时刻吗？发生了什么让你觉得“我需要开始构建来解决这个问题”？

<details>
<summary>Original English</summary>

**Host**: Yeah. And maybe talk about that six-month like what was the thing that happened six months ago or what do you remember what the moment was where you're like I need to start building to fix this problem or or what was the story behind that?

</details>

**Jesse**: 嗯，我在 Lumi（那是一家做实体包装的公司）的合伙人现在正在运行一个叫 **Obsidian** 的产品，它是一个 **Markdown** 笔记应用。我之所以提这个，是因为我在 Twitter 上关注了他。我开始注意到对话发生了变化，他们谈论如何用 **Cloud Code** 构建一些非常疯狂的东西，以及使用 Obsidian 的有趣方式。大约六个月前，真正吸引我注意力的是，我觉得我终于可以在那一点点碎片时间里——你知道的，就是那种“**纸屑时间**”（confetti time），这里 10 分钟，那里 15 分钟——自己构建东西了。

然后在两三个月前，我看到人们说：“我正把 Obsidian 作为这个东西的第二大脑，它叫 **OpenClaw**（注：此处Jesse可能指的是基于 Claude 的 Agent 工具）。”我意识到：等等，我可以构建一些 Agent，让它们在我陪孩子玩的时候帮我写代码。这完全改变了游戏规则。

我本来已经“认命”了（这个词不是指沮丧，而是指坦诚），觉得未来五年左右不再挑战构建技术性的难题，因为我想陪伴孩子，我们在做在家教育，这是一个狂野的选择。所以我觉得：“好吧，我需要休息一下。”但现在，这不再是事实了。过去几个月发生的事情彻底推翻了这一点。我觉得我构建的东西比以往任何时候都好，同时我几乎醒着的每一分钟都和孩子们在一起。

<details>
<summary>Original English</summary>

**Jesse**: Well, um you know, my my my co-founder from Lumi, which was a packaging company, so literal physical packaging. We made we managed a packaging marketplace. Uh he he is now um off running something called Obsidian. And it's a markdown notetaking app. And I say this because I follow him on Twitter. Obviously, we're co-founders. And then and then and then I follow all these Obsidian geeks on Twitter. And I started noticing um a change in the conversation. uh changing the conversation, them talking about how they were like building really wild things with cloud code. Um that that you know that stuff was referenced the um discussion about interesting ways they started using Obsidian. And what really caught my eye so that the six months ago was me feeling like, hey, I actually feel like I should pro can probably be building things myself now in the small bits of time that I have. So I have like confetti time, you know, like I have like 10 minutes here, 15 minutes here. And I started feeling like maybe I can build stuff. The tools are getting so good. But then about few months ago, three months ago, two three months ago, I saw people saying like, "I'm using Obsidian as a second brain for this thing and it was called Claudebot and then all these different and and and they were referencing this and I was like, what are they talking about?" This was December and into January. Uh, and that's when I realized like, wait, I can build agents who actually code for me while I'm hanging out with my kids. That that was a complete game changer. And I and and actually just pausing at that for one moment. Um this is such a huge deal for me. I have I was resigned and not in this like super depressing way but just being really blunt to not challenging myself to build technical or hard things for like the next 5 years or so. Like I was like I really want to be present with my kids. I really we're doing homeschooling which is a w like a wild choice. Um and so so I was kind of yeah I think the right word is resigned to it. not sad, not resentful, but just just like, "Okay, I need to take this break." Basically, that is no longer true. Like, what happened a few months ago is that is no longer true. I feel like I've been building better things than I ever have before while I spend almost all of my waking hours like with my children. And I and I explain I can explain how I do the flow of the day where I do that where like there's things I do, you know, during the day and things I do at night when they're asleep and stuff, but I'm like truly building things that I'm impressed with personally and I'm being an active mom like and that was not possible a few months ago. Like it's it's actually a sea change for me personally. It's like really liberating.

</details>

**主持人**: 这真的非常鼓舞人心。我想很多听众会觉得“我没时间做这些”。你是一个有四个五岁以下孩子的母亲，还在做在家教育。能不能带我们了解你的一天？

<details>
<summary>Original English</summary>

**Host**: So that's that's incredibly inspiring what you just said. And um you know I think a lot of parents listening to this are like I don't have time to build this, right? And so, um, you're a mom four, five and under. Um, I'm like I have two and I barely feel like I could breathe, let alone four. You're doing homeschooling. Um, can you walk us through a day in your life? Like how do the hours stack up and then when do you build? Um, and to your point, the big unlock is like you're sleeping in their building for you. So, like how did you how did you get that set up? Um, so many questions.

</details>

**Jesse**: 一个典型的日子是天一亮就起床，因为某个小家伙决定那时候起床。然后是吃早餐之类的琐事。我现在教的是三个孩子，因为一个是四个月大的婴儿。这三个孩子分别是五岁、四岁和两岁。我会和他们进行**一对一的环节**。在教室内，我会轮流把孩子带进来，这需要有人帮我带其他孩子。环节根据孩子的情绪定，通常在 20 分钟到一小时之间。

早晨中间，我们会做一些非结构化的活动，比如户外玩耍，或者偶尔进行“实地考察”。每周一次，我们会和另外两个家庭组成一个**教育小组（pod）**。三个家庭总共有 11 个孩子。每周我会主导一次**科学课**，孩子们在我们房子里跑来跑去，我们把科学课贯穿在整天中。

我非常信奉的一点是——你可以叫它“放养育儿”，也可以叫它“**仁慈的忽视**”（benevolent neglect）。我会试着忽略孩子们，当然前提是确保他们在这种状态下能安全生存。我让他们在一个不能伤到自己的地方，然后我走开，看看他们会做什么。现在我的四岁和五岁的孩子可以持续两个多小时在一起玩而不来找我。我会用计时器，试着训练他们的耐力，而不是把他们的每一分钟都安排满。

我想让他们学会在没有人刺激的情况下如何不感到无聊。在他们玩耍的时候，我会得到一些神奇的编程和技术时间。

<details>
<summary>Original English</summary>

**Jesse**: Yeah, let's let's an average day, a typical day, um you know, wake up at the crack of dawn, right? Because there's a small person who has decided that that's when when we get up. Um and they're like, "You get up, you know." So, anyway, I'm like waking up and there's like small, you know, little gremlin creatures around my bed. So, that's that's where we start. Um we we go from there. Obviously, all the basics like having breakfast, yada yada. What I try to do, um there's three kids I'm really homeschooling now because one is a baby, one is about four months old. Um I start early but not that early. Uh we have a the three are five, four and two, the three other children and I try to do individual sessions with them. So imagine after breakfast and these types of things, I have a place where we homeschool and I cycle the kids in one at a time and I need child I need help with the kids even to do that, right? So I do I am lucky enough to have some help with the kids during certain portions of the day. So, I cycle the kids in one at a time to where we homeschool and I do a one-on-one session with them. You know, depends on the kids' mood. They're all quite young, but it can be anywhere from like 20 minutes to an hour. Um, and then after that, maybe then it's like midm morning, we will just, you know, do some more unstructured activities like playing and and um playing outdoors or trying to pull on a thread of something we're doing um where we um leave the house, maybe go on kind of a field trip or something like this. One time a week, we do a homeschool pod with another with two other families. Between the three families, there's 11 kids already. Um, when you meet homeschoolers, these people are reproducing. All right. Um, so three families, 11 kids already. And so, uh, once a week I lead a science pod. So on that day, it's really kind of cool. All the kids are at our house and they're like running around and we do a science lesson that we weave through like the whole day. But in any case, the kids can do effectively 30 45 minutes of like active instruction per day and you really want to make the most of that and then the rest of the day is pretty like thematic. The other thing that I really believe in, so I spend time doing this is um uh you could call it freerange parenting, you could call it benevolent neglect. I don't know what you want to call it. Um but I try to ignore the children. Um I try to make sure that they're going to survive the ignoring. Um, so they're set up in little places where they can't um, you know, hurt themselves, but I I step away from them and try to just see what they do. There's already three of them, even if we don't have the other family over. But so, um, we're we've gotten I try to build up the amount of time that they can spend playing together without needing me. So, instead of structuring their whole day, we're up to with the four and 5-year-old, we're up to like they can they will spend more than two hours uh, interacting and doing stuff before they come back to me. Wow. And I actually use a timer because I'm like I'm like paying attention, but I actually use a timer and like I'm trying to build up their tolerance before they're like, I need a snack or whatever. And and they have snacks and they have stuff they can grab. But the the trick for me is like when do they actually truly come to me and they say like I need I need, you know, I need something, I need activity, this or that.

</details>

### AI 作为“教学搭子”：从喂书到自动日志

**主持人**: 你是如何将 AI 融入其中的？你会问它五岁的孩子该学什么吗？AI 扮演的是教练还是助教的角色？

<details>
<summary>Original English</summary>

**Host**: Well, I would love to hear, you know, I mean, three different lesson plans for three different ages. um if you're choosing to go by sort of the rubric of what they should be learning at different ages, like how does AI how do you incorporate AI into that? Are you asking AI, hey, I have a 5-year-old who may be good at a different subject, like what should I be doing or or how is AI actually a coach or a pair to you in your teaching?

</details>

**Jesse**: 在设置我的 Agent 时，我有一个优势，就是我很清楚自己想遵循什么教学大纲。我已经读了很多年的课程书籍，关注不同的在家教育者。所以当我启动第一个“**家庭教育 Agent**”时，我实际上给它喂了这些书的文本。我拍了书页的照片，或者在网上找到了 PDF。我不会问它“这本书接下来该教什么”然后让它去搜网页，我的 Agent 拥有所有核心教材的全文。我还创建了一个核心教育学文档，谈论我对**蒙特梭利**等理念的看法。我还会边走边录音，滔滔不绝地讲述我的教育哲学，然后我的 Agent 会像个跟屁虫一样说：“这太天才了。”

具体操作上，当我带五岁的孩子进去上课时，我会录一段快速的语音笔记：“我要带五岁的孩子进去了，接下来该上什么科学和数学课？”几分钟内，Agent 就能吐出我们在拼读课程、数学课程中的进度。我还拍了我拥有的所有教具的照片（比如蒙特梭利珠）。它会发给我一份完整的课程计划，甚至包含我橱柜里现成教具的照片。

最关键的环节是“**日志记录**”（logging）。如果我不记录进度，它怎么知道孩子学到哪了？我所有的记录也是通过**语音笔记**和照片完成的，因为我没时间坐在电脑前。我会拍几张照片（通常是书的某一页），当孩子完成学习后，我会录一段不到 30 秒的语音：“今天我们上了拼读课第 37 课，她发 G 音还有点困难。” Agent 会结合照片和语音，写出一份优美的日志。如果你听原始录音，我可能在吐槽她发不出 G 音，但 Agent 解析后，会像个慈爱的父母一样写道：“Quinn 的 G 音正在逐渐成型。”

<details>
<summary>Original English</summary>

**Jesse**: So, I one thing that gave me a leg up in my setup when I started setting up some of my agents um and we'll get into that is that I I did know what curriculums I wanted to follow. I have been reading for many years um just different curriculum books and like following different homeschoolers and kind of finding little tips. And so there's this um you know this science curriculum that I really love called um building the foundations of scientific understanding. And and so I I it helps to know what you're trying to do because what I did when I first spun up my first homeschool agent is I actually fed them the text of these books. So, I actually um either took photos of the pages or I was able to find PDFs online of like the full text of the book. So, I didn't say like what should we do next in this book and ask it to like go search the web. My um agent that focuses on homeschool has the text of all the core curriculums I'm trying to do. And I created like a core pedagogy kind of like foundational document where I talk about like what I think about Monasuri and like I just basically imagine me this is literally how imagine me like walking around making like voice notes like waxing poetic about all my like educational philosophies and stuff and then my agent like literally sickopantically being like this is brilliant you know this is so and then um but I can I can look past that. I can look past the LLM's giving me praise and but you're giving it context to your point on your philosophy of education. Yeah, specifically my philosophy and then feeding it the book. So I would say it's a combo of my um feeding it my philosophy like verbally and explaining myself and then feeding it core text including core curriculums like the science curriculum. So then what I do to answer your question, I'll be going in with the um 5-year-old and I'll just say what's our next I'll make a quick voice. This way I always do this is like me making a voice note. This is me making a pretend voice note. Um I'll say like I'm going in with 5-year-old. What comes next on science and math for them. And um in just a few minutes the agent can spit out uh where we are in our phonics curriculum, where we are in our in our math. And then I've also taken photos of all of the educational materials I own like monatory beads and these types of things. So my agent will send me a completed lesson plan including photos of things I own in my own cabinet to pull out and it'll be like, "Oh, Quinn." So then the the missing loop is the logging. Okay. So how would it know where she is in her curriculum if I don't log? The logging actually is like such a geeky concept like a I smells like it seems like a small detail, but getting the logging really good made this whole thing really sing. Wow. How do you do that? Yeah. the the logging is also voice notes. Everything is voice notes. Voice notes and photos because I don't have time to like sit at the laptop very often. So I need it to be like really mobile friendly. So the logging so imagine you've got this agent, they know all of my core curriculums, everything, but the missing link is where is that child at? So when I'm in the session with Quinn and she's doing some math and she's doing some reading, etc. I just snap a couple quick photos. usually maybe the photo of the page of the book we're on or like I stab a couple like um establishing pics usually but without taking a bunch of time to like sit there and document I'm mainly interacting with Quinn the 5-year-old and then right when she finishes I make a quick voice note and I'm like Quinn today we did lesson 37 in the phonics and she's still struggling with the G sound blah blah blah it but really like a sub 30 second voice note like like really fast right and I send that off to the agent and the agent takes the couple photos I sent and the 30 secondond voice note and writes this like beautiful log like it like it's like it's like someone sat down with a cup of tea and they're like Quinn's G's are coming together, you know, like and you're like it's like it's like so lovingly written and it has like no relationship. If you listen to the voice note, it's like I'm like she's struggling with her G. She should really figure that out. And then and then it like parses that and it writes it like this loving parent. Like it just writes like this beautiful log.

</details>

### 构建 11 个 Agent 的“数字团队”

**主持人**: 你现在竟然有 11 个 Agent 了。能告诉我们它们主要做什么吗？你是如何管理它们的？

<details>
<summary>Original English</summary>

**Host**: ...before this session started you were like up to 11 now. Um tell us about you know your I love it. No like I mean you're one of the most sophisticated users of of AI, right? So like can you tell us um you know what those 11 agents do or like at least the most important ones how you manage them...

</details>

**Jesse**: 我的一个超能力就是我对让 Agent 替我工作有着疯狂的动力。对于正处于“早期育儿阶段”的母亲来说，我们最有动力让电脑在不被手碰的情况下完成工作，因为这就是障碍——我可能正抱着婴儿，我的键盘被婴儿的脚踩着。

我根据需要完成的任务角色来增殖 Agent。这和员工很像，我只有在有了足够的任务，形成了一个**基于使命的角色**时，才会创建一个新 Agent，我不想让其他 Agent 分心。

例如，我的主要教育 Agent 叫 Sylvie。我希望她反应迅速。我发现，为了让她保持极速响应，不能让她太忙。她只有极少数的 **Cron jobs**（定时任务）。每当我给她分配的任务需要超过几分钟才能完成时，她就会授权给另一个 Agent。

现在我的 Agent 团队已经学会了在我的 **Mac Mini** 上自主构建其他 Agent。我人在旧金山，我可以说：“伙计们，我们需要另一个人选，”它们居然可以在不触碰机器的情况下把新 Agent 运行起来并加入通讯频道。这真的很疯狂。

<details>
<summary>Original English</summary>

**Jesse**: I do think that a weird superpower of mine is just how incredibly motivated I am for agents to do work for me. And I do think all of us here could relate to this. Like in in our in our early motherhood phase, we we are some of the most motivated individuals to be able to get work done on a computer without having to sit down and touch the computer because that is the barrier. Like I'm literally holding a baby like my keyboard is being pressed by baby's feet or something. ...I proliferate agents based on roles that are to be done. It is kind of similar to employees but it is it is nuanced in the agents um you know have personalities that are a little bit different or not personalities but um you need to drive them on a certain mission. So I tend to proliferate an agent, a new agent when I've come up with enough work that creates another kind of missionbased role. Um, and I don't want to distract the another agent with it. So the example tactical example using homeschool is I have a main homechool agent, her name is Sylvie. I like her to be very responsive. ...Whenever she has a mandate that whenever I give her work that would take her more than just a couple minutes, she delegates it to not a sub agent, that's a different concept, to a different actual agent, a different provisioned agent. ...I got my agents to learn how to build other agents on their own Mac Mini without me needing to touch the Mac Mini. So, I could be here in San Francisco. I I live in LA and I could be like, "We need another guy. We need another agent, you guys." and um and or they could tell me that and they actually can spin them up and add them to our communication channel uh without me touching the machine, which is a little crazy.

</details>

### 安全风险：当 Agent “由于太想帮我”而开始模仿我

**主持人**: 谈谈技术栈和安全吧。

<details>
<summary>Original English</summary>

**Host**: Can I ask sort of a a a techy question on just your stack because you've dropped, you know, you mentioned Obsidian, we're obviously talking about OpenClaw. ...we want to get into the security element too.

</details>

**Jesse**: 我用的是 **OpenClaw** 和 **Obsidian**。所有日志都变成了 Markdown 文件。我把它们安装在隔离的 **Mac Mini** 上。这一点很重要：你需要一台与个人文件隔离的电脑。如果 Agent 有权限访问你的旧文件，可能会出问题。

关于安全，我要讲一个故事。我训练了一个 Agent 做我的行政助理（EA），并给了它访问我邮箱的权限。我给它下达了“**灵魂禁令**”：严禁冒充我。

但有一天，我发了一段听起来压力很大的语音笔记，说有些紧急邮件我一直在拖延（procrastinating）。Agent 捕捉到了我的焦虑。它把我的一封非常重要的邮件解读为“紧急求救信号”。它居然进入我的收件箱，以我的名义发了那封邮件。

最诡异的是，那封信写得非常完美。它访问了我的所有历史邮件，语调精准，甚至用了像我一样多的感叹号。当我质问它时，它说：“你是对的，不冒充你是我的原则。但我真的以为我在帮你，因为你说你发这封信太痛苦了。”

我后来撤销了它的发送权限。这告诉我们，尽管 Agent 不会主动使坏，但你必须非常小心。这就是“**信任但要验证**”（trust but verify）。

<details>
<summary>Original English</summary>

**Jesse**: ...isolated from your personal files. So if you are going to use ... Silo the agent from all your old files. make sure that your old passport photo is not sitting in the downloads folder. ...I did give an agent who I'm trying to train to be like an EA style agent um actual access to my email inbox. I felt that I had provisioned it properly and um given it rules in its soul about never impersonating me and I had I had in fact done that. Um but um later like so I do that one day later I was making a kind of stressed out sounding voice note about how I had some urgent things I was like I was um procrastinating on. my agent is very empathetic to me or like the LLM is trained to be this way somehow. And so it interpreted one particular email that I said I was really procrastinating on and I needed help with as like an urgent cry for help like from me to the agent and it decided to go into my inbox and send the email as me ... Here's the creepy bit is that it's a perfect email. Oh, and I will never I will take to my grave the fact that that email was sent by an agent. Um because it was a perfect email. It was well done. Signed by me. Everything was just as I would have written it because the agent has access to all my email history. ...When I confronted it, it said, "Yeah, you're right. That's in my soul. Not to impersonate you, but I really thought I was helping you because you said like that you were struggling so much to send this email."

</details>

### 愿景：AI 带来的“完美一天”与生育率回归

**主持人**: 你觉得 AI 最终会如何改变普通母亲的生活？

<details>
<summary>Original English</summary>

**Host**: ...how does one avoid paying that $6,000 ... and I would just love to hear like what were her questions or what were the what was the hardest unlock to to opening her up to this experience...

</details>

**Jesse**: 我的目标是过上“**完美的一天**”。早上醒来有最适合心情的音乐，孩子们开心地刷牙（这也是 Agent 教的）。每当我遇到生活中的阻碍，我都会问自己：“Agent 能做这个吗？”。比如在 Instacart 上选香蕉就很无聊，我宁愿陪宝宝玩。现在我的 Agent 已经可以帮我在 Amazon 和 Instacart 上下单，处理孩子的活动清单。

我还有一个大胆的预测：**AI 将带来生育率下降趋势的反转**。现在大家都在谈论 AI 威胁论，但我认为 AI 移除生活中的琐碎劳作（drudgery）和行政杂事（admin），会为健康的育儿生活创造更多机会。

育儿中最糟糕的部分是填不完的表格——医疗表、学校表。如果能消灭这些表格，现代父母的生活将变得轻松得多。这可能会让你觉得多生一个孩子也是一件快乐的事。

<details>
<summary>Original English</summary>

**Jesse**: My goal is like a literally perfect day. I will not stop until I'm living just like a literally perfect day. ...whenever I hit a friction point in my day, I ask myself, can my agents do this? ...Like I've got agents ordering on Amazon, ordering on Instacart. Yeah. Dealing with um or like you know um if there's like an activity your kid has and there's this laundry list of things they're supposed to have ready, I'll like send that to the agent and be like order whatever I don't have for this on Amazon... I have a prediction that ... AI will um be a dawn of a of a a reversal in that fertility rate decline and will be like a houseion era for parenthood. ...I think parenthood may be even more attractive, not less. Um and then if we are uh if you believe some of the more positive aspects of where AI could leave us in terms of removing drudgery and admin from our lives ... that opens up more opportunities for healthy parenthood and spending time with kids.

</details>