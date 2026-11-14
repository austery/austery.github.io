---
author: How I AI
date: '2026-11-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wdyOjcCj2hw
speaker: How I AI
tags:
  - personal-knowledge-management
  - household-management
  - coding-agent
  - markdown
  - agency
title: 用 Claude Code 与 Obsidian 构建家庭 AI 大脑
summary: Scott Farrar 分享了如何利用 Claude Code 与 Obsidian 的本地 Markdown 文件构建家庭记忆系统，管理家电质保、汽车保险比价、维修待办与家庭协作，并探讨了 AI 在家庭管理及数学教育中保留人类能动性的方法。
insight: ''
draft: true
series: ''
category: note-taking-systems
area: knowledge-meta
project: []
people:
  - Scott Farrar
  - Claire Vo
companies_orgs:
  - WorkOS
  - Atlassian
products_models:
  - Claude Code
  - Obsidian
  - DAKboard
  - Dropbox
  - GitHub
  - Jira Product Discovery
media_books:
  - How I AI
status: evergreen
---
### 开篇介绍：家庭管理的 AI 记忆系统

>> 当你使用网页端、ChatGPT 或 Claude 时，你心里会想：它到底了解我什么？它真正记住了什么？它掌握了哪些信息？对大多数人来说，这都是非常不透明的。
<details><summary>Original English</summary>
>> When you're using like the web or chat GPT or claude, you're like, what does it really know about me? What does it really remember? What information does it have? Like that is very opaque [music] to most people.
</details>

>> 我想构建一个让我确信 AI 能基于我真实情况运行的系统。所以在 Claude Code 中，我搭建了这个可以读写 Markdown 文件的系统，这样它们就能保存我们交流内容的记忆。我把家里所有的家电以及它们的序列号都记录了下来。我可以在这里开启一段新对话说：“冰箱现在是什么情况？”它就会知道质保信息，因为我之前某个时候把这些内容放进去了。
<details><summary>Original English</summary>
>> I wanted to build a system where I was confident that AI was grounded in my truth. So in claw code, I built this system that would read and write markdown files. So they would have the memory of what we were talking about. I have all the appliances in my house and all their serial numbers. I might go start a new chat here and say, "What's going on with the fridge and it knows the warranty information because I put that in there at some other time."
</details>

>> 我打算把这个丢给 Claude。在这栋房子里我需要考虑些什么？
<details><summary>Original English</summary>
>> I'm going to drop it to Claude. What do I need to be thinking about in this house?
</details>

>> 我们实际上可以在这里向 Claude 提问，比如：“嘿，我需要为地震做准备吗？”
<details><summary>Original English</summary>
>> Let's actually go to Claude here and say like, "Hey, do I need to plan for earthquakes?"
</details>

>> 欢迎收看《How I AI》。我是 Claire Vo，一名产品负责人兼 AI 狂热爱好者，致力于帮助大家利用这些新工具更好地进行构建。我们讨论过用于工作的 Claude，讨论过用于编程的 Claude，也讨论过面向孩子的 Claude。但我们还没有聊过面向房屋业主的 Claude。如果你正在努力承担起成年人的繁重家庭责任，那么这一期节目正是为你准备的。我们采访了 Scott Farrar，他拥有一个记录家中一切信息的 Obsidian 知识库，并配备了一套 Claude 技能，不仅让家里的干腐病问题得到控制，还将保险报价压到了最低。让我们正式开始吧。本期节目由 WorkOS 赞助播出。
<details><summary>Original English</summary>
>> Welcome to How I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. We have talked about Claude for work. We have talked about Claude for coding. We have talked about Claude for kids. But we have not talked about Claude for the homeowner. If you are adulting hard, then this is the episode for you. We talked to Scott Ferrar who has a obsidian vault [music] of everything in his house and a set of clawed skills that keeps his dry route under control and his insurance quotes as cheap as they can be. Let's get to it. This episode is brought to you by work OS. [music]
</details>

>> AI 已经改变了我们的工作方式。各种工具正在帮助团队编写更优质的代码、分析客户数据，甚至自动处理支持工单。但这里有一个潜在问题：这些工具只有在能够深度访问公司系统时才能良好运行。你的代码助手需要查看你的整个代码库，你的聊天机器人需要跨内部文档检索。对于企业买家来说，这引发了严峻的安全隐患。正因如此，这些应用从第一天起就面临着严苛的 IT 审查。为了通过审查，它们需要安全认证、访问控制、审计日志以及全套企业级功能。从头构建这一切是一项巨大的工程。这就是 WorkOS 发挥作用的地方。WorkOS 为你提供即插即用的企业级功能 API，让你的应用能够具备企业就绪能力并更快迈向高端市场。可以把它想象成企业级功能领域的 Stripe。OpenAI、Perplexity 和 Cursor 都已经在使用 WorkOS 来加快进度并满足企业需求。欢迎前往 workos.com，与他们以及数百家行业领军企业一起，今天就开启构建。Scott，欢迎来到《How I AI》——家长时间、忙碌父母、忙碌奶爸兼忙碌管家特别版。
<details><summary>Original English</summary>
AI has already changed how we work. Tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a [music] catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense [music] IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features. [music] Building all that from scratch, it's a massive lift. That's where work OS comes in. Work OS gives you drop-in [music] APIs for enterprise features so your app can become enterprise ready and [music] scale up market faster. Think of it like Stripe for enterprise features. OpenAI, Perplexity, and Cursor are already using work OS to move [music] faster and meet enterprise demands. Join them and hundreds of other industry leaders at workos.com. Start building today. Scott, welcome to how I AI parent, busy parent, busy dad, busy household manager edition.
</details>

>> 忙得不可开交的成年人责任。
<details><summary>Original English</summary>
>> Busy busy adulting.
</details>

>> 繁琐的成人日常。我们有太多问题了。大家总是在问：“我们需要更多家长上节目，我们需要更多应对忙碌生活的人。”所以当我看到你做的一些事情时，我特别兴奋能让你来为我们做个演示。带我们了解一下你应对繁重成人生活的情景吧，以及你当时试图解决的问题是什么？
<details><summary>Original English</summary>
>> Busy adultting. We have so much so many questions. Everybody always asks like, "We need more parents on. We need more people handling their busy lives." And so when I saw some of the stuff that you were doing, I was so excited for you to demo it for us. So, walk us through what your busy adulting looks like and what problem you were trying to solve.
</details>

---

### 用本地 Markdown 和代码 Agent 消除不透明感

>> 我有孩子，有自己的事业，要兼顾所有事情确实很难。如果我冒出一个问题，比如：“哎，我的车险买对了吗？我需要调整吗？”你知道，就像很多人一样，我也许会求助于 AI，会去打开聊天界面让它帮我解决。但我当时遇到的问题是，如果我开始用聊天界面处理一个复杂问题，就会纠结：我是该把自己的信息一股脑倒进去吗？我要把所有的上下文都喂给这个对话框吗？而且，随着对话推进，它会不会产生偏差？它到底真正记住了关于我的什么？所以我想构建一个系统，让我能确信 AI 是立足于我的真实情况，清楚它知道我的哪些信息，从而让我对它给出的建议抱有信心。因此，我没有继续使用普通的聊天界面，而是转向了代码 Agent。在 Claude Code 中，我构建了这个系统，它可以读写文件，读写 Markdown 文件，这样就能保留我们所讨论内容的记忆，并且它保存在我的电脑本地。这样我以后回过头开启一个新的聊天会话、一个 Claude Code 会话时，它就能引用这些相同的文件。比如这里有一个正在处理的车险问题样本，就像“哦，我一直在弄这个，第三方报价送到了吗？”比如我们在找各方拿报价，它总结了一些报价在这里，然后就像“那我是不是该更新车险了？我的保障里存在哪些缺口？”它读取了我放进文件夹里的文档。这对我来说是一个巨大的突破，不仅提升了我对它掌握自己情况的信心，而且只要它能为我生成一份行动清单，就能推动我不断向前推进。
<details><summary>Original English</summary>
>> I have kids. I've got a career and it's like hard to juggle everything. And if I come up with a question like, "Oh, should I do I have the right car insurance? Do I need to change that?" You know, lots like lots of people I might come to AI, I might go to the chat and have it help me out. But the problem I was having there is if I start doing a complex problem with chat, it's like, well, do I dump my information in there? Do I give it all the context into this chat here? Um, and as the conversation goes, is it drifting? What is it really remembering about me? And so I I wanted to build a system where I was confident that AI was grounded in my truth and and knowing what it knows about me so that I could be confident in what advice it was giving me back. So what I did instead of just going with the chat interface uh switching over to a coding agent um so in cloud code I built this system that would read and write files read and write markdown files so they would have the memory of what we were talking about and it would be living on my computer so that if I come back later and start a new chat session a cloud code session it can reference those same files. So, if I uh here's kind of a sample of of the car insurance question in progress where like oh I've been working on this uh has that third quote come in like we were getting quotes from people like oh it's summarized u it has some quotes here on here it's like oh well should I update that car insurance what gaps do I have in the coverage so it's read the documents that I put in the full file folder I this has been a huge unlock of like both my confidence and what it knows about me but also just when it can uh build me um like a checklist of what to do then it keeps me moving forward.
</details>

>> 所以你在这里真正想要解决的问题是：当你使用网页端 ChatGPT 或 Claude 时，你总会想：它到底了解我什么？它真正记住了什么？它掌握了哪些信息？这种黑盒状态对大多数人来说是非常不透明的。但是一旦你下载了这些桌面应用——无论是 Claude Code、Claude Co-work，还是 ChatGPT、ChatGPT Codex 等等，它们都可以写入你的电脑。正如你所说的，你只需要让它使用 Markdown 文件作为一种非常透明的单一事实来源、知识来源，来回答关于你家庭的任何问题。接着你用它（如果你展示一下那个 Claude 会话的话）来处理诸如更新保险的事情，检查你的保险是否是最新的、你需要什么并获取报价。你能带我们看一下通过代码办理车险和报价的实际过程吗？哪些地方做得很好，
<details><summary>Original English</summary>
>> So the problem that you're trying to solve here really is when you're using like the web you know chat GPT or claude you're like what does it really know about me? What does it really remember? What information does it have? like that is very opaque to most people. But once you download these desktop apps, whether it's Claude Code, Claude Co-work, um ChatGBT, Chat GBT codeex, whatever you're working with, they can write, it can write to your desktop or to your desktop, to your computer. And what you're saying is then you just tell it to use markdown files as kind of like your very transparent source of truth, source of knowledge. um that any question about your household can answer. And then you're using that if you just show us the kind of like claude session, you're using that to do things like update your insurance like check are you up to date on your insurance, what do you need and get quotes. Can you walk us through just that like experience of getting car insurance and quotes and what did well with,
</details>

>> 比如通过代码处理与传统方式相比有什么不同？哪些地方没走通？
<details><summary>Original English</summary>
>> you know, using that through code versus what kind of failed?
</details>

>> 我一开始只是问：“那我该更新这个吗？”在讨论更新另一份保单的过程中，它说：
<details><summary>Original English</summary>
What I started with was um just saying well should I should I update this and um in the conversation around updating another insurance says well
</details>

>> “给你提供报价的其中一个人说你需要更新车辆信息，而且你还想要另一份保单。”在往年我可能会觉得：“哇，这太让人头疼了，我以后再处理吧。”但我现在可以说：“在这个项目上我接下来该做什么？”这是一个非常宽泛的问题，但因为它基于我正在处理的具体事项，它返回了一个答复：“你的下一步是给 Dana Whitfield 发邮件（这是一个虚构的名字），这是目前的阻塞项，你应该发邮件询问这个问题，比如‘我这里到底需要什么’。”在你能就车险做出明智决定之前，这些是你需要得到解答的问题。
<details><summary>Original English</summary>
>> one of these per people giving you a quote said you need to update the cars and you also wanted this other policy and in the previous years I might have been like wow this is a headache I might come back to this but um I might say like well what should I do next uh uh on this project and because I I it's a very loose question but because I'm grounded on on what I'm working on here it comes back with a response says oh your next step is email uh Dana Whifffield is a fake person but uh that's the blocker and say like you should email ask this question of like you know uh what is it that I really need here uh and these are the these are the questions that you need to to have answered before you can make an informed decision on car insurance.
</details>

>> 换作以前你会怎么做？因为我完全可以告诉你我以前会怎么做——我根本就不会去管它。
<details><summary>Original English</summary>
>> And I mean, how would you have done this before? Because I'll tell you exactly how I would have done it before. I wouldn't have done it.
</details>

>> 是的。我觉得我以前的做法其实需要对保险代理人给予极大的信任。
<details><summary>Original English</summary>
>> Yeah. I think what I would have done is actually it requires maybe a lot more trust in your insurance agent.
</details>

>> 并不是说我完全不信任他们，而是这意味着我不会去详细通读那些文件。借助 AI 的能力，你可以通过 AI 去阅读。然后我想引入我自己的家庭上下文，让这个系统与保险代理人给我的信息相融合。这样我就能提出详细得多的问题，与保险代理人通邮件往来，清楚地知道我问的是什么，也确切明白对方告诉我的是什么。
<details><summary>Original English</summary>
>> Not that I don't necessarily trust them, but it meant that like I wouldn't have read those documents in detail. Um, and so with the power of AI, you you can read it via the AIS. And then I wanted to bring in my own home context and have that system uh mesh with what the insurance agent was giving me. And then I was able to ask way more detailed questions and email back and forth with the insurance agent and know exactly what I was asking and know exactly what they were telling me.
</details>

---

### Obsidian 知识库：家电、质保与序列号记录

>> 明白。所以对你来说秘诀在于上下文。我们之前见过一些类似的做法，我看到你用的是 Obsidian。我们见过不少这种“个人大脑”。我喜欢你这个个人大脑的地方在于，你放进里面的家庭信息类型要全面得多。你在 Obsidian 里放了些什么？你认为放进哪些上下文，能让你在处理家务时比其他人做得更多？
<details><summary>Original English</summary>
>> Okay. So I you know for you the secret sauce is context and we've seen a couple of these. I I see that you have Obsidian. We've seen a bunch of these like personal brains. What I loved about your personal brain is you're a lot more comprehensive in the type of household information you put in that personal brain. So like what are you putting putting into your Obsidian? What do you think goes into that context that you think lets you do more stuff within the household um than other folks?
</details>

>> 好，我们先来看看保险项目本身的图景。这是一个 Markdown 文件。这就是 Claude 工作时所依赖的记忆全貌。它会不断回溯并参考这里的已知信息，并在处理过程中更新信息。这里有一份清单，比如“对，这是阻塞步骤，我需要给数据人员发邮件”。从更宽泛的视角看，这只是其中的一个项目文件。如果我切换到 Obsidian 查看图谱视图，就能看到输入给 Claude 的所有上下文，或者说 Claude 能参考的所有上下文。我把家里所有的家电和它们的序列号都放了进去。比如这里有一张虚构的炉灶照片，记录了冰箱的序列号，还有“我孩子的 iPad 什么时候会失去 iOS 系统支持和软件更新”，我就会把这些信息存进去，比如它们运行的是某某系统，或者是 2019 年款之类的。其实当我最初搭建这个系统时，我曾问过 Claude：“我应该收集关于我房子的哪些信息？”我问它：“比如冰箱呢？”它说：“事实上，你应该把房子里的每台家电都拍张照片。”这些黄色文件其实就是那些照片，它们汇总在另一份家电清单的 Markdown 文件里。Claude 在某种程度上规范了它的组织规则。虽然我可以直接在 Markdown 文件里检查这些记忆，但我经常直接使用 Claude 本身。我可能会开启一个新会话问：“冰箱怎么了？”它就会去读取数据库，精确检索我提到的冰箱是指什么，我也许会接着说：“因为制冰机……”
<details><summary>Original English</summary>
>> Yeah. So actually let's start just a picture of the insurance project itself. This is a markdown file. This is like the picture of the memory that Claude was working with. uh it go it's going constantly referencing back what it knows here and it will update information as it goes and there's the checklist of like oh yeah that is the blocking step I needed to email the data person but it also is going to you know at a wider view like what this is one of the project files in here but if I go over to obsidian see the graph view of all the context that I put into claude or all the context that claude can can reference uh I have kind of all the appliances is in my house and all their serial numbers. Uh or like here's a picture a fake picture of the of the the range um for the the serial number of the um refrigerator and like oh when is the uh when is my kid's iPad going to lose iOS support uh software updates um and so I might just put that information in like they're on OS such and such um or it's this this model from 2019 or something. So, actually when I set this this system up, I said to Claude like, "What information should I gather about my house?" I asked it and I said, "Uh, you know, perhaps what about like the refrigerator?" And said, "Well, actually, you go around and take pictures of of every appliance in your house." And so, that's actually what all these yellow files are, the the pictures, they are summed up on this appliances list, another markdown file. And, um, Claude is kind of enforcing the rules of how it's organized. And while I can inspect the memory here in the markdown file itself, I often am actually just using claw itself, uh, I might go start a new chat here and say what's going on with the bridge and it's going to go read the the database, look for exactly what's what am I talking about with the fridge and maybe I'll say like because the ice maker in
</details>

>> 等等，暂停一下。天底下的房子都一样吗？你知道我现在家里排在第一位的问题是什么吗？
<details><summary>Original English</summary>
>> Wait, hold on. I I have to pause because are all houses the same? Because do you know what the number one problem in my house right now is?
</details>

>> 我家冰箱里坏掉的制冰机。
<details><summary>Original English</summary>
>> My broken ice machine
</details>

>> 在我的冰箱里。我真的一点都没开玩笑。我们专门用了一个 Grok 机器人来对接我们的冰箱维修人员。年轻人，这期节目不是给你们看的，这期节目是给那些
<details><summary>Original English</summary>
>> in my refrigerator. I am like not even kidding. We have a Grock bot that is like dealing with our refrigerator repair people. Young young people just This episode is not for you. This episode is for people
</details>

>> 需要维修老式不锈钢冰箱自带制冰机的人看的，不是 TikTok 上放在台面上的那种花哨小巧的碎冰机，那种老式冰箱的制冰机总是坏。
<details><summary>Original English</summary>
>> who need their not one of those fancy little nugget ice makers that you put on the on the countertop on Tik Tok. We're talking a good old stainless steel refrigerator ice maker always broken.
</details>

>> 确实是这样。当你遇到那种问题时，你用的是 Grok 机器人。我们可以顺便对比讨论一下这类机器人以及 Dot、Muse、Instinct 等工具。但在我这里，我可能会去查看家电清单那个 Markdown 文件本身，如果我想看的话随时能看，所有记忆都在那。但我通常是直接去 Claude Code 开一个新会话，非常随意地说：“啊，我该怎么办？帮我制定一个计划。”它可能回复说：“坏消息，这要花钱了，质保期到 2027 年截止。”它之所以知道质保信息，是因为我之前某一刻录入进去了。这真的非常强大。其实这在很大程度上是受了我父亲的影响，因为在 AI 出现之前，我父亲和他的文件柜其实就像 AI 一样，他保留了所有的收据和所有的质保信息。我现在依然可以问他：“嘿，你当年解决这个问题时是怎么弄的？”他会说：“哦对，我有一份 1978 年的文件，我看看，当时的冰箱遇到了某某情况。”所以每次我向 Claude 提问时，我都会想：“啊，这完全就是我父亲当年做的事。”自然而然就成了这样。
<details><summary>Original English</summary>
>> Yeah. Yeah. Um so yeah, when you have that problem, you're using Grockbot. Actually, it's it'll be interesting. We can talk about the contrast with with bots and and dots and muse and instinct and those types of things too. Um, but here what I will do is like I'm not I might go into the appliances and look at that list that markdown file itself. I could if I wanted to. I see all the memory there. But really I'm going to cloud code often and just starting a new chat and saying like ah what do I do? It's very loose. And I'm like make help me make a plan. And so it might come back and say h you know what oh bad news it's going to cost you the warranty is going to run out in 2027. and it knows the warranty information because I put that in there at some other time. [snorts] Um, so that's been super powerful. You know, actually a lot of this is influenced by my dad because in a preAI era, my dad and his file cabinet are actually just like AI cuz he he'll have all the receipts and all the warranty information and he still I can still ask him like, "Hey, how did you do this when you were solving this?" And he's like, "Oh yeah, I have this file from 1978. Uh let's see. Um yeah, the fridge then did such and such." So, uh every time I I ask Claude this, I'm like, "Ah, this is just this is just what my dad did." Uh um naturally,
</details>

---

### A 型与 B 型思维：非结构化输入与 Linter 约束

>> 我有一个假说，世界上有两种人：一种是“Notion 男孩”型，你甚至不需要真正用 Notion 才算这一类，但骨子里必须有那种特质——“我要把这些归档，我要把它整理好，我要给它打上标签”。而我不是，我恰恰相反。我是一个 B 型大语言模型人格：直接倾倒非结构化的上下文，然后坐等输出下一个 token。不过我觉得很有趣的是，看到人们对世界的思维模型如何投射到他们设计 AI 系统的方式中：从高度组织化的 Obsidian 节点和架构，到像“我不知道，相册里某处有个我冰箱的视频，去找到它，然后告诉我它到底怎么了”。
<details><summary>Original English</summary>
>> I I have this kind of like hypothesis that there are two types in the world. There are like notion boys and notion boys. And like you you don't even have to use notion to be a notion boy, but like you have to have that like thing in you that's like I'm going to file this stuff. I'm going to organize it. I'm going to tag it. I am not. I'm the opposite. I am a typeB large language model. You just dump in unstructured context and you're going to get the next token out. But I do think it's funny when you see people's kind of like mental model of the world go into how they design their AI systems. Everything from like hyper organized obsidian nodes and structure to like I don't know I have a video of my refrigerator somewhere in photos. Go find it. And then tell me what's what's going on with it.
</details>

>> 我觉得这正是我非常喜欢的地方——游走在 A 型与 B 型之间的弹性光谱：我可以倾倒大量非结构化的信息，依靠代码 Agent 来将其结构化并维持该结构。实际上这个系统的一部分就包含一个 linting 脚本，用来巡检并确保啰嗦的聊天 Agent 没有过度扩充内容、没有让我的待办清单变得冗长不堪。但我认为真正的灵感来自于这些 Agent 如何直接盘活长期躺在我电脑里的文件。我一直都知道数据就在那里，就在某个角落，只是我当时没有时间逐一整理；我也很希望能手动过一遍去整理，但一直没做。有了 Claude Code 和 Codex，你给它一个目录，它就能进去把所有这些东西梳理提取出来，组织得井井有条。在这些文件中，我经常手动回看的是那份待办清单，那份庞大的待办事项清单。我让它创建了这个文件，我和我太太进行了一次头脑风暴，列出我们脑海中大大小小的每一项待办：是孩子浴室里喷水不太对劲的浴缸出水口？还是可能会有干腐病、我们面临着高达数千美元的干腐病问题，或者我们该如何核实这到底是真是假？把这些汇总归纳，给出优先级，给出预估成本，给出优先级和参考信息。这个待办文件是我经常回看的文件。
<details><summary>Original English</summary>
>> Well, I think that's actually the what I really like is the loose kind of spectrum between the type A, type B here where I was able to dump in a lot of unstructured information and rely on the coding agent to structure it and maintain that structure. Actually, part of the system here is like there's a linting script that goes through and make sure that uh you know verbose chat agents haven't over haven't expanded too uh too much that making my to-do list too verbose or something. But I think actually that was really I was really inspired by kind of how these agents can just unlock files that's been on my computer forever and just I've always known the data's in there. It's somewhere in there. I I don't have time to sort through it right now. Uh I would love it to manually go through and sort this but uh I never have. But with with cloud code with codeex you know you give it a directory and it can go through there and pull out and organize uh all this stuff uh in an amazing way. One of the files actually that that I really come back to a lot in the in a manual way is the to-do list the massive to-do list. So I said I I had it create this. I'm like you know me and my wife we had a brainstorming session of like what is every single to-do item in our brain big and small. Is it fixing the the tub spout in the kids' bathroom that's doesn't spray quite right? Uh is it uh oh, there's going to be dry rot. We have a multi,000 dry rot problem or do we or like how do we find out if that's true or not? Uh and so like uh compile those into things. Give me a priority level. Give me a a t a cost estimate. Give me a a priority and and reference. So this this is the file I come back to a lot. The the to-do file.
</details>

---

### 家庭协作：Dropbox 同步与墙面看板 DAKboard

>> 我太喜欢这个了，因为我们的家庭情况非常相似：“我遇到了干腐病问题，我被防腐工人坑了吗？那个做防腐的尽责了吗？”而且我也想知道，你和你太太在这上面是如何协作的？这是我想问的。我们在企业里经常谈论多人协作模式，跟我讲讲家庭里的多人协作吧。
<details><summary>Original English</summary>
I I love that because it we we very similar household. It's like I have a dry rot problem. Am I getting scammed by my dry rock guy? Did the dry rock guy do his do his job? And I I do think, you know, how do you and your your wife collaborate on this? That's my question on we talk a lot about multiplayer in the enterprise. Tell me about multiplayer in the home.
</details>

>> 是的，这是我在搭建这个系统时最早探讨的问题之一。搭建本身其实超级容易，因为我提出了自己的约束条件：“我想在这件事上和我太太协作。我想了解家里的各种情况，范围限定在家庭内部。我不打算用它处理财务，也不打算录入医疗信息。”但是在谈到我和我太太之间的共享与协作时，我设想的场景是：好吧，我的电脑上有这套系统，我可以和 Claude 对话并且它清楚这些情况；但我同时也希望我太太能跟她的 Claude 对话，并且她的 Claude 也能了解同样的信息。
<details><summary>Original English</summary>
>> Yeah. Yeah, that was one of the earliest things that I uh talked about as I was setting this up. Um, so setting this up was super easy. Uh, because I I said, "Here are my constraints. I want to collaborate with my wife on this. I want to know things about the household, kind of scope it to the household. I'm not going to do finances with this. I'm not doing medical information." Um, and but when it was when we were talking about sharing and working with me and my wife, I was like I was imagining that like, okay, I'll have this with my computer. I can talk to Claude and it will know the stuff, but I also want my wife to talk to her claude and have it know the same things. And so
</details>

>> 我尝试了几种不同的方案。第一种纯粹是使用 Dropbox：那是一个我们两人都能访问的 Dropbox 文件夹，同步在我们两台笔记本电脑上，这样我们都能操作。当时系统给过一点提示，警告说：
<details><summary>Original English</summary>
>> I've been trying out a couple different variations on this. And the first one was just purely Dropbox where it was a Dropbox folder that we both had access to copied on both our laptops and so we could do it. And there was a little bit of like it warned me that saying,
</details>

>> “如果你们两人同时在里面操作，可能会遇到 Dropbox 同步冲突。”我问：“那有什么替代方案？”它说：“你可以试试 GitHub。
<details><summary>Original English</summary>
>> well, maybe if you're both in there at the same time, you might have some Dropbox sync conflicts. Uh, and I said, 'Well, what's the alternative? And it said, 'Well, you could try you could do like GitHub. You could
</details>

>> 如果你习惯写代码的思路，你可以把 Markdown 文件提交到 GitHub 仓库里，通过它来同步。”我太太听了觉得：“我不知道值不值得费这么大劲。”这两种方式各有取舍。我们最终达成的方案其实介于两者之间：对于某些内容，我确实倾向于使用 GitHub，比如 linter 脚本和一些导出到墙面显示屏的脚本；但很多常规内容则是通过 Dropbox 处理，而且我们心里清楚彼此基本不会在同一时间段进行读写。
<details><summary>Original English</summary>
>> if you're if you're in that mindset of coding, you could like commit markdown files into a GitHub repo and, you know, sync with that. And uh my wife was like, I don't know if it's worth all that. Um there's some trade-offs for that still. And and where we've landed actually is somewhere in the middle where um I kind of do like GitHub for some of the stuff. There's a few scripts that like the llinter uh and some of the other things that export to to a a wall display, but a lot of the stuff is handled with Dropbox and we kind of just know that we're both not really in there at the same time uh reading and writing.
</details>

>> 这种实用的产品约束很有意思：你们的协作到底需要多强的实时性？如果只是弱实时协作，大概完全能够容忍偶发的冲突。我也很喜欢我们当中一些偏技术的人试图带入家庭的那种做法：“亲爱的，要不你提个 Pull Request？要是你能提个 PR，我们管理冰箱就省事多了。”我觉得这特别逗。本期节目由 Jira Product Discovery 赞助播出。有了 AI，单个产品经理就能总结调研、起草 PRD 并构建可运行的原型。但多人协作模式依然支离破碎。仅仅靠一份 Markdown 文件，你无法让所有人就真正应该发布的内容达成一致。Jira Product Discovery 为你的团队提供了一个统一的空间来收集洞察、依据证据进行优先级排序，并构建每个人都能围绕其协同推进的动态路线图。由于它由 Atlassian 的 Teamwork Graph 提供支持，它拥有你决定构建什么所需的上下文。这些决策会直接流转到 Jira 中，让你的开发人员或代码 Agent 能够带着每个决策背后的背景信息开始构建。已有超过 25,000 家公司在使用 Jira Product Discovery。欢迎前往 atlassian.com/howiai 免费试用。Jira Product Discovery，助力 AI 时代做出更好的产品决策。聊到那个家庭看板，你是在家里怎样展示和使用这些信息的？
<details><summary>Original English</summary>
Yeah, I mean I do think this like sort of practical product constraint of like how how real time is your collaboration and if it's only lightly real time, you can probably deal with some conflicts. And so I also love that some of us the the the more technically inclined are like trying to bring into our households like what if you just did a pull request, honey? Like what if you just did a pull request? that would be totally fine for us to manage the refrigerator. Uh, so I think that's really funny. This episode is brought to you by Jira product discovery. With AI, a single PM can summarize research, draft a PRD, and build a [music] working prototype. But multiplayer mode, that's broken. You can't get everyone aligned on what should actually ship with just a markdown file. [music] Jira product discovery gives your team one place to capture insights. Prioritize with evidence and build living road maps everyone can rally around. And because it's powered by Atassian's teamwork graph, it has the context you need to decide what to [music] build. Those decisions flow straight into Jira, so your developers or coding agents can start building [music] with the context behind every decision. More than 25,000 companies already use Jira product discovery. [music] Try it free at atlassian.com/howi aai. That's atlassian.com/howi aai. Jira product discovery better product decisions in the AI era. You know talking about that that household board. How are you displaying using this information inside your house?
</details>

>> 这是一种视图，因为我是一名数学老师，非常喜欢图表，但这种界面对我的家人来说并不具备可读性。
<details><summary>Original English</summary>
or so, you know, here's one view that I look at because I'm a math teacher and I really like graphs, but it's not like this is uh readable to the rest of my household.
</details>

>> 我用了一段时间的产品叫 DAKboard，它基本上就是一个挂在墙上的显示屏。你可以在上面放置信息，放很多你想要的内容。其中一个功能是你可以直接嵌入一个自定义网页。我当时就在琢磨：“我可以从数据库里提取什么内容放到墙上，既实用又能随时给我提供参考？”走过它身边时就能吸引你的注意力，提醒你：“啊，我确实得做那件事了。我确实得修一下水龙头了。我确实得买台新制冰机了。”
<details><summary>Original English</summary>
>> Um, and so what what I what I've been using for a little while is a a product called DACA board, which is kind of just a wall display. You can put information on there. You can put a lot of stuff that you want. Um, and one of the things though is you can just put a custom web page in there. And I was toying with the idea of like, well, what what can I extract out of my database and put it on the wall that might be useful so that I can kind of have that reference for me? I can, you know, you walk by it and you catches your eye that like, uh, I do need to do that. I do need to fix the faucet. I do need to get the new ice machine.
</details>

>> 这就是我想呈现出来的东西。我想把它从笔记本电脑里提取出来，让家里的每个人都能看到。因此，我让 Claude 写了一个小脚本，抓取待办事项、抓取接下来的旅行安排，并抓取一些其他信息，构建了墙面显示屏的一部分，专门呈现当下最核心的内容。它会提醒你应该记在心里的事：你在推进哪些项目？有哪些出行计划？还有一条今天可以做的小建议，比如“嘿，重新给走廊填缝只要 12 美元”。然后可能还有一些需要关注的较长期事项，以及一些给我孩子看的内容。我还专门做了一个“最近成果”板块，用来肯定自己：“干得漂亮，你确实把那个修好了；或者你查清楚了哪些 iPad 的软件版本过旧；你在一天内修好了热水器。老爸干得漂亮！”
<details><summary>Original English</summary>
>> That's what I wanted to surface. I wanted to get it out of my laptop and and available for uh for everyone. So, what I had uh Claude do is build a little script to scrape kind of the to-do items, scrape upcoming trips, and scrape um some other information and build a piece of the wall display that has just like top of- mind things. You should you should keep this in your mind like what projects are you working on? What are the trips? Uh a little a little like kind of uh suggestion of something to do today. Hey, it's only $12 if you want to reccock the the hall. Um, and then maybe some longer term stuff that's like needs attention. Uh, and just some stuff for my kids. Uh, I also put made a section of recent wins just to say like good job. You did fix that or you found out what iPads were out of date with software. You uh you fixed the water heater in one day. Great job, Dad.
</details>

>> 我特别喜欢这个。以前我在 Optimizely 工作时，我们有一堵巨大的墙，每周一我们都要站在它面前。它被称为“工作之墙”，我们把正在做的每一个史诗任务都打印出来（那会儿写代码像要跋山涉水一样原始），在这个实体看板上移动卡片，而且我们还有一堵“成果之墙”。我很喜欢你把你那种出色的敏捷 Scrum Master 能量带入了家庭管理。你觉得这真的有助于你把事情做成吗？它是否切实改变了你的行为？
<details><summary>Original English</summary>
>> I I really love this. When I was working at Optimize Lee, we had this huge wall um that we stood in front of every Monday. It was called the wall of work and we like actually printed out, this was like back back in the day where we had to like walk uphill both ways for our code. Like printed out every single epic that we were working on and we would like move it on this physical board and then we had like a wall of winds. Um, and I like that you are bringing that very wonderful scrub master energy to to your household household management. Um, do you find that this like helps you get stuff done? Do you Does it actually change your behavior?
</details>

---

### 从被动救火到主动推进：家庭任务的全面跟踪

>> 确实改变了。真的管用，因为当它为我生成一份清单时，
<details><summary>Original English</summary>
>> It does. It does because when it has built a checklist for me
</details>

>> 比如针对保险事项，
<details><summary>Original English</summary>
>> like on the insurance
</details>

>> 所有这些后续步骤或待处理事项都不会遗失在我的脑海中（以往只是脑子里闪过‘啊我该做那个’的想法），
<details><summary>Original English</summary>
all these next steps or open items uh they are not like lost in my memory of like ah I should do that just like a should thought in my head
</details>

>> 而是被白纸黑字记录了下来。每次我在任何对话中处理事情时，它都可能会提醒我，比如：“嘿，实际上有件事你逾期了”，提醒你从 9 月 24 日起就一直在等待某件事的处理结果。所以这确实推动了大量项目的进展，以至于我现在几乎没有待处理的紧急状况了。我当时心想：“哦，这真是一种全新的体验。”我以前总有积压的待办，而现在球都在别人的半场：我总是先发邮件的那一方，正在等待对方的答复，这种感觉非常棒。
<details><summary>Original English</summary>
>> it's recorded somewhere and it's like will come back every time I I do something in in any a chat it might remind me of was like hey actually you're overdue on something like it's going to remind me that you've been waiting since September 24th on this. And so it's really actually uh has moved me forward on so many projects that I've actually kind of like run out of of pending fires and I was like, "Oh, that's a new experience." I I used to have a backlog and now I'm now I actually it's the ball's in everyone else's court. Like I'm always sending the email and it's I'm waiting on them and uh that's been really nice.
</details>

>> 如果有人作为成年人经营自己的家，给大家列一份家庭任务清单吧，一份可以让 AI 去思考的家务清单。我看到了维修，看到了比价选购，还有什么？清单上还有哪些内容可以给大家带来启发？
<details><summary>Original English</summary>
So give me just give me the list of you know if somebody's like lives in their house as an adult give me the list of like here household tasks you should just get your AI to think about. So I saw repairs I saw like comparison shopping. What else? What's on what's on the list so people can be inspired.
</details>

>> 这份待办清单里包含这些内容：有房屋维修；有一些关于保险和财务的事项；可能有未来规划，比如遗嘱和监护权、信托、退休基金。如果你想整合自己的退休账户，这实际上是个巨大的麻烦，我一直在弄，AI 在这方面也很有帮助。我觉得还有设备管理、旅行规划。其实在昨天的地震纪念日，我想着：“让我们去问问 Claude 吧：‘嘿，我需要为地震做防范吗？’”你只需要以这样一个非常宽泛的问题开篇，由于它得到了你所有上下文的支持，它可能了解你的房屋地基情况，可能知道你身处土壤液化区。然后我就非常有信心开始着手处理：“哦，你确实应该做防震规划。好的，我们把这个记录为一个想法，我要开启一个新项目。”这套体系中的结构之一就是项目文件：我们在其中收集信息、建立清单并逐项打勾。我非常喜欢在完成一个项目时关闭该文件，我很喜欢说：“好了，我们完成了所有事项，把这个项目归入‘成果’一栏，展示在 DAKboard 上。”
<details><summary>Original English</summary>
>> So here's the here's what's in this uh to-do list. Um there's repairs. There's a little bit of like yeah insurance financial uh maybe like future planning wills guardianship. um trusts, retirement funds, like if you want to consolidate your retirement actually that's a huge headache that's I' I've been working on um that's been helpful here too. Um I think also like kind of it uh and and device management um trip planning um actually what I recently uh with the earthquake reminder day uh yesterday I think it was I was like oh um let's let's actually go to Claude here and say like hey um do I need to plan for earthquakes and then you know it's a very loose question that you just start with that and because it's empowered by all the context you have. So it might know that the foundation is such and such. It might know you're in a liquefaction zone uh liqueification zone. Um and then I'm really confident of like okay let's let's start working here. Oh you should plan for earthquakes. Uh okay. Yeah let's capture this as an idea. I'm going to start a new project. Uh so one of the one of the structures in this is like there are project files and those are going to be where we collect information and and start checklists and check things off. Uh and I really love to like close a project file when I'm done with it. I love to say like all right we finished all the we finished that project. Put it in the wins column. Put it on the dack board. Uh
</details>

>> 我太喜欢这个了。我从这里看到的像是在调用一个 skill 或插件来遵循你的流程。
<details><summary>Original English</summary>
>> I really love this. And what I'm seeing here it looks like this is invoking a skill or a plugin to just follow your little process.
</details>

>> 是的，它提取了 Claude Markdown 文件里的一些结构，并提示：“你应该先创建一个项目文件，或者先作为一个想法提出。”在尚未升级为完整项目之前，我确实有一些备选想法，比如防震准备，或者任何我能想到的事情，直接放进想法文件：我是不是该重新做庭院绿化？我是不是该重新粉刷？油漆是不是脱落了？我很喜欢把配电箱拍下来，上面全是电工潦草的手写字迹，我的备办事项里就有一项：我能不能梳理核对清楚这些电路分别控制什么并记录在这里，这样我以后就可以直接问 Claude，而不用每次都费劲去破译那些手写字。
<details><summary>Original English</summary>
>> I think yeah I think it's uh picking up some structures um from the claw markdown um and it's saying yeah you should start by creating the project file or starting as an idea first I hasn't been promoted to a full project I do have like the backlog ideas like earthquake readiness or just anything I think of of like uh just put that in the idea file should I rellandscape should I uh do I need to repaint is the paint peeling off um I I like taking a picture of the of the circuit breaker with all the like scrolled electrician handwriting and I have it on my backlog of like can I go through and actually check which circuits those are and log it here so that I can ask Claude instead of trying to decipher the handwriting every time.
</details>

>> 我们不要本末倒置，这里确实有一些非常棒的工作流。我环顾我的房子，心想：“我的天，我应该把这些全都做一遍。”你给了我另一个灵感，我打算试一试，有效果再向你汇报：我打算录一段巡视整栋房子的视频，边走边介绍各项东西，然后直接扔给 Claude 或 ChatGPT，提问：“针对这栋房子，我需要考虑些什么？”你有了视频，有了所有的资料。
<details><summary>Original English</summary>
>> We're we're burying the lead here. There are some really good workflows. I'm like looking around my house. I'm like, "Oh my gosh, I should do all of this." And you're giving me another idea which I'm going to try and then I'll report to you if it works. I'm just going to do a video walk through my house talking about stuff and then I'm gonna drop it to Claude or to Chad GBT. I'm gonna be like, "What do I need to be thinking about in this house?" You have the video, you have all the stuff.
</details>

>> 太天才了。
<details><summary>Original English</summary>
>> Um, genius
</details>

>> 天才想法。“面向业主的 AI”将会成为这里的核心看点。Scott，我想快速切入快问快答环节，不过第一个问题可能没那么短，因为你我有一个共同的兴趣，那就是 AI、孩子以及数学学习。跟我聊聊你的看法吧，作为一名试图探索 AI、数学与孩子交汇点的人，作为家长我们应该思考些什么？
<details><summary>Original English</summary>
genius. This is going to be AI for the homeowner is is going to be the the headline here. You know, Scott, I want to I want to zip to lightning round question. Although the first question might not be so lightning because you and I have a shared interest which is AI and kids and learning math. So tell tell me a little bit about your you know what you think about as somebody who's trying to figure out the intersection of of AI and math and kids and what should we be thinking about as parents?
</details>

---

### 数学教育与反向辅导：保留学生的能动性

>> 我非常看重学生的主体能动性。我们一直在讨论各种 Agent，对吧？把这类项目与 Muse 或 Instinct 的功能进行对比会很有趣：它们之间有重叠，但并非百分之百重合。我认为这跟数学教育有些关联。容我多解释几句：比如在使用 Muse 时（我知道你也用过一段时间），Muse 往往是在前台为你做事情的那个。而在我的这个模型中，我把它往后撤了一点，把这个角色部分留给了我自己——我想知道你会给出什么建议和推荐，但我自己依然保留一定的自主能动性。我认为特别是对于正在学习数学的学生，我们希望他们保持认知努力，保持那种自主能动性，自己决定想探究什么，并通过富有成效的挣扎来达到目标。因此我们必须为 AI 找到一个能够支持这种过程的角色，而不是越俎代庖直接给出答案，或者提供过多的帮助，甚至于不重视学生提出的想法。所以我非常喜欢市面上看到的一些产品，它们能解读学生的意图并顺着推进：“哦，好主意，孩子，再多跟我讲讲。”
<details><summary>Original English</summary>
>> I am a big fan of of student agency. You know, we're talking about agents a lot, right? And it's interesting in the contrast with this kind of project with what Muse or Instinct might do. There's there's some overlap, but there's not entirely some uh not 100% overlap. And I think that's related to to math education in a little bit. So, give give me some rope here. Um the it's like if you're asking Muse, I know you've you've used Muse a little bit. Um Muse is the one out there maybe doing stuff for you. And in this model, I've kind of kept it back, kept that role for myself a little bit of like I want to know what you're going to suggest and recommend, but I'm going to be the one having some agency still. And I think when especially for students who are learning mathematics, we want to keep them doing the cognitive effort and keep them doing that agency, deciding what they want to know and struggling in in a productive struggle to get there. Uh so uh we got to find a role for AI that supports that instead of kind of short circuits and and gives them the answer or is too helpful um or kind of maybe even doesn't appreciate the ideas that the student is is giving. So I'm really I really like some of the products I see out there that are interpreting what the students say and and running with that. It's like, "Oh, good idea, kid. Uh tell me more about that."
</details>

>> 所以你强调的重点在于：第一，你个人喜欢“人机协同”（人类在回路中）。我个人倒不喜欢这样，那不适合我，我更倾向于让 Agent 全权代理。我非常偏向让 Grok 机器人或者 Muse 直接上手。但你的立场是：“我希望 AI 推动我去投入行动”，这很符合你的思维方式以及你参与其中的偏好。而从 AI 教育的视角来看，你喜欢那种能够辅助理解学生思路、但又不剥夺其自主能动性的解决方案，让他们保持“我正在学会如何解决这个问题，我正在掌握做事方法”。能举个具体的例子吗？
<details><summary>Original English</summary>
So what you're saying is important is one you personally like to be human in the loop. I I don't like to be I that's not that's not for me. I like to the agent to be in the loop. So I'm very heavy like >> Grockbot go muse go. But you're saying like I want the AI to put me to work and that's what works well for my brain and how I like to be in the loop. And from a AI education perspective, you like you know solutions where it can support interpretation of what a student is doing but not take away that agency of like I am learning how to solve this problem. I am learning how to how to do the work. Can you show me an example of what you mean?
</details>

>> 好的。我见过一些项目，我自己也琢磨过类似项目：你可以反转聊天辅导机器人的关系，辅导机器人的目标不再是教导学生，而是尝试从学生那里“抽取”知识。聊天机器人可能会说：
<details><summary>Original English</summary>
Yeah, I think like I've seen some projects I've kind of noodled on projects uh myself where uh you kind of flip the relationship of a chatbot tutor where the tutor is now the the chatbot is not aiming to teach the student but the chatbot is aiming to extract some teachings from the student. And so the chatbot might say
</details>

>> “请帮我理解如何解一元一次方程。”学生可能会说：“嗯，我大概知道，你也许应该在方程两边同时减去某些项。”机器人接着问：“啊，但你为什么必须这么做呢？”如果能这样定位聊天机器人，让它们既不烦人，
<details><summary>Original English</summary>
>> help me understand how to solve a linear equation. And and the student might say like, "Oh, well, I kind of know what you should do is maybe subtract things from both sides." And the chatbot's like, "Ah, but uh but why do you why do you have to do that?" And you know, if can the chatbot be positioned so that they are not annoying,
</details>

>> 又能捕捉到学生脑海中的想法。学生脑子里有很多绝妙的知识，但有时他们害怕与真人分享，也不敢向 AI 吐露。所以如果我们能鼓励孩子们分享他们的思考，那将会产生强大的效果。
<details><summary>Original English</summary>
>> but they can still grab the ideas that the student has. And the students have a lot of great knowledge in their heads. Uh but sometimes they're afraid to to share it out with humans and share it out with with a with AI. So I think it's going to be powerful if we can enable kids to share their thoughts.
</details>

>> 今天是我录制的第二期节目，早前那一期也是关于语言辅导的，可能已经上线了。我们在那期聊到，AI 是一个拥有无限耐心的私人导师，你可以向它倾倒所有最愚蠢的想法，它永远不会说“这是个愚蠢的问题”或者“你早该知道这个”。它总能以私密的方式引导你建立成长型思维，穿过我常对我家孩子说的“沮丧区”——如果你感到沮丧，说明你正在学习。你可以带着这种私密、耐心的陪练走过沮丧区来辅助你的学习。我认为这非常有力量。我经常在谈论编程时跟人说这个道理，但它同样适用于任何类型的学习活动。
<details><summary>Original English</summary>
>> Today uh is this is my second episode I've recorded today and the earlier one was also about a language tutoring episode. So it might might already be live but what we were talking about in that one is AI is this like infinitely patient private tutor you can say all your dumbest stuff to. And so it's like never going to be that's a stupid question or you should know that already. It can always kind of like help you privately go through your growth mindset, go through the like what what do I call my kids? Um the zone of frustration where it's like if you're frustrated, you're learning. And you can go through that zone of frustration with this sort of like private patient um foil for your learning. And I think that's really powerful. And I tell people this all the time about coding, but it applies to any sort of learning activity.
</details>

>> 没错，沮丧区或者叫最近发展区。而且辅导者……
<details><summary>Original English</summary>
>> Yeah. I think actually uh the zone of uh frustration or zone of proximal development. And I think like you know can the tuner
</details>

>> 你刚才提到了“无限耐心”，我觉得在聊天机器人领域探讨这个很有意思：
<details><summary>Original English</summary>
>> um I I like you also mentioned uh infinite patience and I think that's something that is interesting to to play with in the chatbot realm of like
</details>

>> 它应该拥有无限的耐心吗？或者它是否也应该……
<details><summary>Original English</summary>
>> should it be infinitely patient or should it be also kind of
</details>

>> 带着礼貌但同时……
<details><summary>Original English</summary>
>> you know politely but also uh
</details>

>> 做一个温和而坚定的要求者，说：“其实我认为你懂得这个，所以我不能直接为你代劳所有事情。我需要让你……”
<details><summary>Original English</summary>
>> be be a polite demander a warm demander of saying like you actually I think you do know this so I can't quite
</details>

>> “我需要给你留出空间。”“你能做到的，为什么不自己试一下？”
<details><summary>Original English</summary>
>> do all the work for you. I need to let you uh Yeah, I need to give you some You can do it. Let Why don't you give it a try?
</details>

>> 是的，保持极大的鼓励，去点出“我知道你其实懂得这些”，引导他们释放自己的知识储备。
<details><summary>Original English</summary>
>> Yeah, I can I can super encouraging. Uh yeah, and and say what I know you already know and and point you in the way to to unleash your own knowledge.
</details>

---

### 尾声：对齐偏差的调试与总结

>> 我太喜欢了，多么棒的表述框架。好，最后一个每次都会问大家的问题：当 AI 没有按照你的预期行事、令人恼火、无法了结那个想法文件时，你会如何给它写 Prompt？这是一个很适合向家长和老师提出的问题。
<details><summary>Original English</summary>
>> I I love it. What a great What a great framing. Okay, my last question we ask everybody. When AI is not doing what you want, when it's being frustrating, when it cannot close that idea file, how do you prompt it? This is a good question to ask parents and teachers.
</details>

>> 我坦白回答：我一般会关掉那个对话，意识到“看来可能在某个地方出现不同步了”，我通常直接开一个新会话。有时我会问它：“你为什么会那样想？你是怎么产生那个想法的？”因为在这种直接与记忆文件打交道的场景下，我得确保它没有把错误内容写入文件中。举个例子，在待办文件的早期版本中，它开始把所有更新内容都塞进待办表格里，导致待办文件充斥着海量的信息。我就质问它：“我不是在 Claude 指令里写明了要保持简短、不要包含更新内容吗？”然后它会用一种非常积极诚恳的语气回复：“你确实告诉过我，非常抱歉。”
<details><summary>Original English</summary>
>> My honest answer is I kind of close that chat and see that like I was like I just start a new session maybe and uh say like ah we must have gotten somewhere out of sync somehow. Um sometimes I I ask it of like why why would you think that why did how did you get that idea because actually in this context of working with the memory file so directly I want to be sure that it's not like it hasn't written it somewhere in there. Uh one one example is some in an earlier version of the to-do file, it just started writing all the updates in the to-do table and then the to-do was just massively a lot of information and I was like didn't didn't I put in the cloud instructions that uh it should be short and brief and not have the updates and then you know it comes back in in a very positive voice of like you did tell me that I'm sorry. [laughter]
</details>

>> 你问的是另一种“为什么”，比如“你为什么那样做？”而我会问：“你到底是怎么回事？”
<details><summary>Original English</summary>
a different you ask a different why like why did you do that? I ask why are you like this?
</details>

>> 或者我直接连打带七个 W 的“Whyyyyy”。我觉得这反映出我们与 AI 协作时的性格差异。这期节目非常精彩。把大量上下文放进去，放大量零散的上下文，让 AI 去梳理；利用 AI 让你在管理家庭责任时保持正轨；给自己积累一堆小成果；而在使用 AI 进行学习时，别让它只给答案，让它推动你，同时也挖掘出你早已掌握的知识。精彩的一期，Scott，非常感谢。大家可以在哪里找到你？我们能为你提供什么支持？
<details><summary>Original English</summary>
>> Or I just do a straight up why with seven W's. Again, I think there is just like personality differences that go that well we how we work with our AI. This has been super fun. Um AI put a bunch of context in there. Put a bunch of loose context in there. Figure let AI figure it out. Use AI to keep you on track with managing your household responsibilities. give yourself a pile of wins and then um you know when it comes to learning with AI, don't let it just give you the answer. Let it push you, but also pull out from you what you already know. Great episode, Scott. I really appreciate this. Where can we find you and how can we be helpful?
</details>

>> 我的网站是 sfxmath.com，你可以在上面看到我正在做的东西。你也可以在 LinkedIn 上通过 Scott Farrar 找到我。我随时都很乐意交流数学教育方面的话题。
<details><summary>Original English</summary>
>> I am at uh sfxmath.com. You can see kind of what I work on there. Uh, you can find me on LinkedIn at Scott for um, and yeah, I'm I'm always eager to talk about math education.
</details>

>> 太棒了，我也一样。我们将结束录制并前往交流。非常感谢你做客《How I AI》。
<details><summary>Original English</summary>
>> Amazing. Well, I am too. We're going to stop the recording and we'll go there. Thank you so much for joining How I AI.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Thank you.
</details>

>> 非常感谢大家的收看。如果你喜欢本期节目，请在 YouTube 上点赞并订阅；或者更棒的是，在评论区留下你的想法。你也可以在 Apple Podcasts、Spotify 或你喜爱的播客应用中收听本节目。请考虑为我们留下评分和评价，这能帮助其他人发现这个节目。你可以在 howiaipod.com 查看我们所有的往期节目并了解更多详情。我们下期再见！
<details><summary>Original English</summary>
>> Thanks so much for [music] watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.
</details>