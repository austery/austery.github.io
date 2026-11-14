---
author: Latent Space
date: '2026-06-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hLUGXO5DSpo
speaker: Latent Space
tags:
  - autonomous-agents
  - nano-claw
  - agent-security
  - knowledge-management
  - open-source-triage
title: 自主工作智能体的架构蓝图：专访 NanoClaw 创始人 Kovid Goyal
summary: 本期访谈深入探讨了自主智能体（Autonomous Agents）在企业落地中的两种核心路径：团队管理的工作流自动化智能体与个人助理型智能体。NanoClaw 创始人 Kovid Goyal 结合其在新加坡与外交部长互动的真实经历，分享了如何构建以隐私与安全为核心、具备沙箱隔离与凭证防泄漏机制的极简智能体运行环境，并展望了未来软件开发中 Wiki 作为知识缓冲与协同载体的新范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Kovid Goyal
companies_orgs:
  - NanoClaw
products_models:
  - NanoClaw
  - Agent SDK
media_books: []
status: evergreen
---
### 新加坡之旅与意外的部长级用户

**主持人**: 你现在来到了 AI Engineer 大会，和 **NanoClaw** 的所有者 **Kovid Goyal** 在一起。感觉怎么样？

<details>
<summary>Original English</summary>

**Host**: You're here at the AI Engineer with **Kovid Goyal**, owner of **NanoClaw**. How has it been?

</details>

**Kovid Goyal**: 感觉棒极了。这是一个非常棒的活动。是的，祝贺你们成功举办。

<details>
<summary>Original English</summary>

**Kovid Goyal**: It's been amazing. This has been such a great event. Yeah. Congrats for putting it on.

</details>

**主持人**: 是的，很高兴能亲自见到你。我之前也在网上看到过你。听起来你有一趟非常充实的新加坡之旅。你见到了新加坡的外交部长。这太不可思议了，你都做了些什么？发生了什么？能给我们讲讲这趟新加坡之旅的故事吗？

<details>
<summary>Original English</summary>

**Host**: Yeah, it's it's great to see you in person. I could see what you on online as well. And it sounds like you had a very eventful trip to Singapore. You met the Minister of Foreign Affairs. Yeah, this is like what did you do? What happened? They tell the story of like the Singapore trip.

</details>

**Kovid Goyal**: 是的，这其实要追溯到大约一个月前。当时我实际上在度假，这是我把 **NanoClaw** 发布以来第一次过周末假期。

我终于和妻子在一家很棒的酒店度了两天假。然后我记得是在周五晚上，我正在浏览 **X**（前 Twitter），看到有人转发了新加坡外交部长的 **Facebook** 帖子。

他在帖子里详细写了他如何使用 **NanoClaw**，他的整个配置、内存系统、索引、部署，以及如何在一台 **Raspberry Pi** 上运行它。他甚至直接点名提到了我。我当时心想：“好吧，这太酷了。”

我的名字甚至没在被转发的帖子里。他显然是在以一种极客的方式深入研究，而且研究得很深。

然后我去找了这个帖子，确实是一个 Facebook 帖子。他发了整个 **GitHub Gist** 来介绍他的全部配置，或者说是他的整个 **NanoClaw** 配置的完整说明。

他拥有类似“第二大脑”那样的配置，包含一个带有嵌入（embeddings）和某种内存系统的 **Karpathy LLM Wiki**。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, so this really goes back maybe about a month now. I was actually on vacation like taking my first weekend off since putting Nano Clock out there. And finally took two days off at a nice hotel with my wife and then I I think it was Friday night. I was just scrolling on X and I see this somebody reposting a Facebook post from Minister of Foreign Affairs of Singapore where he did this whole write-up of how he's using Nano Clock, his whole setup, memory system, indexing, deployment, running it on a Raspberry Pi, and he called me out by name, which is like I was like, "Okay, that's My name isn't even on the repost. He's clearly nerding out and he went deep." And then I went and I found this post and he had done a Facebook post. And he posted this whole GitHub gist of his whole setup or whole write-up of his whole Nano Clock setup. And he's got this kind of second brain type of setup where he's got a Karpathy LLM Wiki with embeddings and some memory system.

</details>

### 企业落地自主智能体的两种路径

**主持人**: 这在你最初的设计里有吗？没有，对吧？

<details>
<summary>Original English</summary>

**Host**: Which did you have that in your original design? No, right?

</details>

**Kovid Goyal**: 完全没有。那全是他自己整合进去的东西。他所使用的内存系统 **Nemon**，在他发帖之后现在也开始变得有点流行了。

<details>
<summary>Original English</summary>

**Kovid Goyal**: No, not at all. That's all stuff that he's brought in. The memory system that he's used, Nemon, which has kind of gotten a little started to get a little bit popular now that he's posted about it.

</details>

**主持人**: 发现了这个。听起来它好像有 141 个 GitHub stars。我当时心想：“让我查查看。”我心想：“这是从哪来的？”就像……

<details>
<summary>Original English</summary>

**Host**: Find that. It sounds like is the 141 GitHub stars. I was like, "Let me check it." I was like, "What's the Where is this from?" Like

</details>

**Kovid Goyal**: 当我第一次查看它时，我认为它大概只有 43 个 GitHub stars。那是在他开始使用它之后。

所以他找到了这个系统，他很喜欢，他也找到了 **NanoClaw**，然后他把它们全部自己整合在了一起。他自己写代码，他创建了这个配置。他做了一篇完整的详细说明。

显然，他当时正在从 **NanoClaw** 的第一个版本迁移到第二个版本，作为迁移工作的一部分，他撰写了这篇完整的配置说明，然后决定把它发布出来。

<details>
<summary>Original English</summary>

**Kovid Goyal**: When I first checked it, I think it had like 43 GitHub stars. So and that was after he started using it. So, he found this system, he liked it, he found Nano claw, and he put it all together himself. He he codes, um, and he he created this setup. He did a whole write-up. So, apparently he was migrating from the first version of Nano claw to the second version, and he created this whole, uh, write-up of his setup as part of the migration, and then just decided to post it.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Kovid Goyal**: 然后这篇帖子在 **X** 上开始传播开来，我进行了转发，接着他又转发了我的转发，我们就这样开始聊了起来。

<details>
<summary>Original English</summary>

**Kovid Goyal**: And it started to go a bit viral on X, and I did a retweet of it, and then he retweeted my retweet, and we started to talk.

</details>

**主持人**: 现在你们成了最好的哥们了。

<details>
<summary>Original English</summary>

**Host**: Now you're best bros.

</details>

**Kovid Goyal**: 最好的哥们。他说，你知道，如果你哪天来新加坡，我们应该聚聚，我很乐意邀请你，招待你。

然后大概两三天后，你联系了我，你说：“我们正在办这个活动。”我当时觉得，这简直太完美了。我确认了他当时会在新加坡，他说“没问题”。然后你成功邀请他过来在大会上发言，这真的很棒。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Best bros, and and he said, you know, when if you're ever in, uh, Singapore, we should, uh, you know, I'd I'd love to, I don't know, have you over and and host you. And then, I think it was two, three days later you reached out, and you said, "We're doing this event." And I'm like, it just it's it's all perfect. I checked that he'd be around, and and he said, "Yes." And then you managed to get him to come down and and talk here, which is, wow.

</details>

**主持人**: 瞧，我想你在新加坡确实有所帮助，所以你也想过来。而且我认为，我们的方向很明确，就是我们只想促进新加坡的相关行业。我是新加坡人，我住在国外，我住在马里兰州（注：原文 US 听写为 US，口误或转写偏差），但我认为政府想要提供支持。

我很好奇，你们俩聊了两个小时。有什么你可以分享的吗？比如一些令人惊讶的用例，或者其他的东西？比如你们讨论了技术栈。他是怎么看待这些的，有没有让你开阔眼界，或者说你能从中学到什么？

<details>
<summary>Original English</summary>

**Host**: See, uh, I think what it did help that you were here. So, you wanted to be. And I think also, no, my orientation is a particular in the sense that we just want to promote the the industry in Singapore. I'm Singaporean. Uh, I live in I live in the US, but like, I think the government wants to support the we basically we basically we basically this. Um, I'm curious, we guys talk for 2 hours. Anything you can share about like surprising, uh, use cases of our whatever. It's like you talk about the tech stack. Like just like and how does he think about it that maybe open your mind is sort of, oh, you know, you should can you learn about?

</details>

### 个人代理与团队自动化工作流

**Kovid Goyal**: 我认为对我来说，他的用例确实帮助我理清了我们未来想要构建的方向。

回顾一个月前，当我们思考在商业环境或公司里推广 **Claw** 类型的自主智能体（Autonomous Agents）时，存在两个重合但又有所不同的方向。

第一种是团队管理智能体。也就是你在公司里构建一个**智能体工厂**（Agent Factory），或者由智能体来自动化整个工作流。我做过一次关于这方面的演讲，关于我们构建的智能体工厂，其实我们自己内部已经开始构建了，而且构建了有一段时间，虽然目前仍然处于在建状态。这是团队管理智能体的方向，也就是大家作为一个团队协同工作，共同构建并管理这些智能体。

而另一边则是商业或工作环境中的**个人智能体**（Personal Agents），即每个员工都拥有自己的智能体助手来协助他们完成工作，这更像是一对一的关系。

之前我们内部在这两个方向上都有所尝试。我们在团队中以这两种方式使用智能体，并且也开始与对这两种用例都感兴趣的设计合作伙伴（Design Partners）合作。

例如，我们正在与一个团队合作，他们希望为法律团队的每个人提供他们专属的个人助理；同时，我们也在与另一个设计合作伙伴合作，他们希望构建能够自动化法律团队工作流的智能体，例如自动起草第一版合同。

通过与新加坡外交部长的交流，这确实让我明确了一点：从我的视角来看，在公司引入智能体的第一步，是给每个人提供他们自己的智能体。

因为使用智能体是存在一定的知识、专业能力和学习曲线的。比如：你如何与智能体协作？它们擅长什么？不擅长什么？你如何提示它们？你如何构建指令技能，并随着时间的推移对其进行调整？如何管理上下文窗口？

这些都需要时间去学习。

在最初阶段，人们常犯的最大错误之一，就是直接把一些任务丢给智能体，然后转头离开，指望最后就能拿到一个完美的现成结果。

你必须投入精力，对吧？这是我们所有人都有的美好愿望，也是很自然的本能。拥有雄心壮志是件好事，但你必须在过程中持续投入。

你必须进行微调——我指的不是微调模型，而是通过调整指令、调整技能、调整输入以及与智能体进行迭代来微调输出结果。

从我现在的视角来看，尤其是看到他的用例后，今天像 **Claude** 这种自主智能体最杀手级的用例就是**第二大脑**（Second Brain）。你只需要不断地向它倾倒信息，而不需要指望它立刻给你生成现成的输出；它只是收集这些信息，构建起它的内部记忆，或者说构建起属于你个人的知识图谱或 Wiki 知识库，然后最终能够为你提供有用的输出。

<details>
<summary>Original English</summary>

**Kovid Goyal**: I think for me, his use case really helped for me to kind of crystallize what direction we want to build in. Going back, I would say a month ago, there were these two overlapping, but kind of distinct directions when we're thinking about adoption of claw type of agents, autonomous agents, in a business setting in a company. Uh, so there's the one where it's the team manages agents. So, it's agents that you build an agent factory or or agents that uh automate workflows. I gave a talk about that, the agent factory that we built, and we had started to build that already for ourselves. And we've been building it for a while. It's still kind of under construction. So, that's one to see factory. It's the team as a team working together to build the agents and managing them as a team. And then you've got the other side, which is personal agents in in a work setting, in a business setting, but individual people who have their agent, their assistant that's helping them do their job, and it's more one-to-one. And we were going working on both of those use cases both internally. We were using agents in both ways within our team. Uh and started to work with design partners that were interested in both use cases. So, we were working with a team where they wanted to give each person in their legal team their own personal assistant. And then we're working in with another uh design partner that wanted to give build agents that automate a workflow for their legal team. So, automate drafting first contracts. With the foreign minister or the Ministry of Foreig- Ministry of Foreign Affairs uh use case, it really helped to crystallize that from my perspective, the way to start in a business intro- introducing agents to a company is to give each person their own agent. Uh because there's a certain knowledge and expertise and learning curve on how do you work with agents. What are they good at? What are they not good at? How do you prompt them? How do you uh build the instruction skills? Adjust those over time. Manage the uh context window. And it takes some time to learn that. And initially, one of the biggest mistakes that people make is that they just want to throw something in an agent and then walk away and expect to get a finished result at the end. You got to you got to put in the effort, right? It's the dream that we all have, and and that's the natural instinct, right? It's good to be to kind of be ambitious, but you have to work on it. You have to fine-tune not fine-tune a model, but but fine-tune the output by adjusting instructions, adjusting skills, adjusting what you put in, and and also iterating with the agent. From my perspective now, especially seeing his use case, the killer use case for Claude type of agents, autonomous agents today, is the second brain use case, where you're just kind of dumping in information, and you're not expecting it to give you ready-made output, but it's just collecting that information, building up its internal memory or knowledge graph or wiki wiki LM wiki Wikipedia of you, and then able to give you useful outputs at the end.

</details>

### 内存管理与知识冗余的挑战

**主持人**: 是的，我一直用个人助手来做这件事。在我的上一次关于欧洲 AI 的演讲中，我谈到了我如何使用来自 LHR 的 **Devin**，甚至是一个个人助手，甚至还有一点 **Victor**。这些都是一些可替代的个人助手。我个人使用 OpenClaw，但我认为像知识管理这样的通用领域，你们也做出了同样的努力。而且我认为它吸引他的正是你们所关注的简单性和隐私性，对吧？他提到过他首先看的是 OpenClaw。他有谈到安全方面的事情，或者比如为什么选择你们而不是 OpenClaw 吗？

<details>
<summary>Original English</summary>

**Host**: Yeah, I've been using town assistant for that. My last in AI Europe, I talked about how I'm using Devin from LHR, a town assistant, even a little bit of uh so Victor as well. These are all like some of the the alternative personal assistants. I use open call personally, but I I think like there's this general field of like knowledge management that is being kept those that I think you guys had the very same effort. And like I think you have the simplicity and the privacy focus that that that drew him, right? Like I think that's he mentioned that he looked at over call first. Uh did he talk about the the security side or like what, you know, the something over call a person?

</details>

**Kovid Goyal**: 是的，安全侧是吸引他加入的关键因素。

有很多像他这样的人。我其实最开始也是用 OpenClaw，当时我们在业务中也使用它。我那时正在建立一个 AI 原生的营销机构，我们当时正在增加客户。我们配置了 OpenClaw，它开始管理我们的销售流程。非常快，大概在两天内，它就能完成一个员工、一个销售经理的工作，管理我们的整个销售管线。

但随后我开始深入研究，我看到了代码库的规模，依赖项的数量，以及一些其他的问题，比如以明文形式记录所有消息，这让我对在生产环境中使用它、在其上构建业务感到有些担忧。

所以我个人使用它觉得没问题，但当我准备把它连接到客户的数据，并开始构建这些运行的工作流，试图在其之上建立我整个公司时，我觉得它不够稳定。

所以在 **NanoClaw** 中，我们做出的核心改变是：首先，我们做了一个非常精简的代码库。我们没有克隆 OpenClaw 然后去修改它，而是直接从头开始重写。我们使用了更多开箱即用的组件。比如，我们使用 **Agent SDK**，而不是去自己构建智能体。

像 OpenClaw 使用的是 Pi，所以你就必须去构建大量的会话管理、上下文压缩以及许多其他功能。Pi 确实非常简陋。相反，我们使用 Agent SDK，它开箱即用地提供了很多这些功能。

我们在最开始时只支持一个模型、一个智能体，因此这方面省去了很多麻烦。我们集成了与消息通道连接的工具。比如我们集成了 Vercel 的 Chat SDK 库，它可以让你开箱即用地连接所有不同的即时通讯软件。所以，我们的代码非常精简，依赖更少。

但随后最核心的一点是**隔离模型**。

首先，你在一个虚拟机（VM）里或者在它专属的 Mac mini 上运行你的整个 NanoClaw，这很好；但你仍然需要把智能体隔离在它自己的智能体运行时（Agent Runtime）中，并将其与连接到 Slack、Discord 或其他软件的通讯网桥，以及路由器和决定哪些内容可以输入给智能体、如何处理智能体输出的其他部分分离开来。你必须对这一块进行隔离。

所以，我们在独立的容器里运行每个智能体。

然后，确保智能体的环境变量中没有任何凭证。这一点非常关键。如果智能体拥有凭证，并且它接触到了未经过滤的输入——在大多数实用的用例中，比如让它去审查一个 Pull Request，它就会接收到整个 PR 的输入。任何人都可以向一个开源仓库提交 PR。

因此，确保智能体的运行环境中没有凭证，这样即使它遭遇了提示词注入（Prompt Injection），它也无法泄露凭证或 API 密钥。

第三个关键点是分离凭证的使用。智能体可以使用凭证，但所有从智能体环境发出的请求都会通过一个保险库（Vault）进行代理，如果智能体被允许访问，保险库会为其添加凭证。

第四个方面则是访问策略、访问控制，以及包含**人工介入审核**（Human-in-the-loop approval）的机制。

比如，你可以让智能体访问邮箱，并设置一个策略：它可以无需任何审批直接读取邮件；但如果它想要发送一封邮件，你会在你连接的任何通道（比如 Slack）中收到一条消息。里面会有“同意”、“拒绝”的按钮，你可以看到它试图发送的内容，并由你决定是否允许它发送。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, the security side was the key thing that that that that brought him in. There are a lot of people like him. I actually started to use open call, and we were using it for our business at the time. I was building a AI native marketing agency. We had some customers we were ramping up, and then we set up open call, and it started to manage our sales process. And very quickly, within like two days, it was doing the work of an employee, of a sales manager, just managing a whole pipeline. But then I started to dig in, and I started to see the size of the code base, and the number of dependencies, and some other things like logging all messages in plain text, that just made me a a bit apprehensive to use it for like production use cases, to build a business on it. So I felt fine using it personally, but when I was saying I'm going to connect it to my customer's data, and I'm going to start to build all these workflows that are running, and I'm trying to build my whole company on top of it. I didn't feel like it was stable enough for me. So, the key changes, first of all, made a really minimal code base with Nano Claw. So, I didn't clone Open Claw and change it. Just started from the ground up from scratch. Used a lot more components out of the box. So, use Agent SDK instead instead of building our own agent. Like Open Claw uses Pi, so then you got to build a lot of session management and compaction and a lot of other things. It's Pi is really minimal. Instead, we use Agent SDK, which comes with a lot of that stuff out of the box. Um only supporting one model initially, one agent initially, so saved a lot on that. Used integrated with things for connections to messaging channels. Like we integrated with Vercel's Chat SDK library that just gives you all of the messaging different messaging apps out of the box. So, really minimal, fewer dependencies. Uh but then the biggest thing is the isolation model. So, first of all, you run your whole Nano Claw in a VM or on its own Mac mini, and that's great, but you still need to isolate the agent in its own agent runtime and separate that from the messaging bridge that's connecting to Slack or Discord or whatever and the router and the other pieces that decide what gets pushed into the agent and what gets done with the agent's output. So, you need to have isolation of that. So, we run each agent in its own container. And then make sure that the agent doesn't have any credentials in its environment. And that's really big. If it's got credentials and it's touching unsanitized input, which for most useful use cases, it's going to be it's going to be, you know, reviewing a PR, it's it's got the whole PR input. Anybody could open a pull request to an open source repo. So, making sure there are no credentials in the agent's environment, so even if it gets prompt injected, it can't leak credentials, it can't leak API keys. And then the third key thing is separating, so the agent can use credentials. All requests coming out of the agent's environment get proxied through a vault and the vault adds credentials if the agent is supposed to have access and then the third thing is having access policies and access control including human in the loop approval. So, you can give your agent access to emails, maybe set a policy that it can read emails without any approval process, but if it wants to send an email, you get a message in whatever channel you've connected, so in Slack and you've got buttons approve, reject, you can see what it's trying to send and you decide if you should let it

</details>

**主持人**: 是的。我觉得他可能没有你那么深入的开发理解，但你们传达的信息确实非常清晰，这就是你们的原则。事情就是这样。

除了这些，你在这次新加坡之旅中还发现了什么？比如你见到了其他的用户，有没有见到其他带来有趣对话、给你启发的主力开发者？

<details>
<summary>Original English</summary>

**Host**: Yeah. I feel like he may not have like the fine brains understanding that you have, but like it the the messaging does come across really very your your DOS. That is what it is. Um yeah, I mean like what else have you found in this trip to Singapore? Like you met other users, like have you met other builders that inspired interesting conversations?

</details>

**Kovid Goyal**: 我在这里见到了很多非常有趣的人。

在我的演讲中，我把我的智能体放了出来，让大家通过它来预订和我喝咖啡聊天的机会。

<details>
<summary>Original English</summary>

**Kovid Goyal**: I met a lot of really interesting people out here. Um you know, I I in my talk I put my agent out there to book book coffee chats with them.

</details>

**主持人**: 我想这中间可能有一些 VPN 代理之类的问题。它当时没认为我在新加坡，因为我有我的美国通道。所以它表现得有些奇怪，不让我……

<details>
<summary>Original English</summary>

**Host**: I think there's some kind of VPN proxy thing. It didn't think I was in Singapore because I I have my US hallway. Uh so it was doing something weird where like it didn't let me

</details>

### 离线环境与个人知识库的设计

**Kovid Goyal**: 而且这些演讲是在 YouTube 上直播的，对吧？

<details>
<summary>Original English</summary>

**Kovid Goyal**: And the talks are streamed live on YouTube, right?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Kovid Goyal**: 所以，是的，我只是想确保只有现场的人能够访问它，而不至于被外面海量的人同时连接导致系统崩溃。所以我确实设置了地理位置限制，只允许新加坡地区访问。

对此感到抱歉，我稍后会为你开通权限。所以，是的，我把我的智能体放了出去，大家和它聊天并预订了咖啡时间。我见到了很多非常有趣的人，尤其是这里有很多正在开发内存（memory）解决方案的学生，他们正在构建一些非常有趣的东西。

<details>
<summary>Original English</summary>

**Kovid Goyal**: So, yeah, I just wanted to make sure that people who were here would be able to access and it didn't get taken down by people, you know, massive people connecting around the set. So, I did set it that it's geo-blocked to Singapore. Uh sorry about that. I'll open it up for you later. So, yeah, so I I I put my kind of agent out there and people chatted with it and then booked coffee chats and chatted with really interesting people building in especially memory students out here who are building really interesting things.

</details>

**主持人**: 其实我想问，你有你自己正在使用的内存解决方案吗？

<details>
<summary>Original English</summary>

**Host**: Actually, I did want to ask do you have your own memory solution that you use?

</details>

**Kovid Goyal**: 就我个人而言，我目前使用的是一种类似 **LLM Wiki** 的解决方案。

我只是让我的智能体指向 Karpathy 的那篇帖子，然后我说：“阅读这个，研究一下。我们先讨论一分钟，然后……”

但是在 NanoClaw 里内置了一个简化版本。它只有一些给智能体的基础指令，比如：“创建 Markdown 文件。用户与你分享的任何实质性内容，确保把它保存在某个地方。它可以保存在你的 `cloud.md` 中，或者保存在某个 Markdown 文件里，或者保存在其他文件中，但必须保存在某个地方。”

<details>
<summary>Original English</summary>

**Kovid Goyal**: Personally, my what I'm using personally is is kind of LLM Wiki a of solution. I just point my agents at Karpathy's uh post and I say, "Read this. Look at this. Let's chat about it for a minute and then uh But Nano has built in kind of simplified version of that where it just has some basic instructions to the agent saying, "Create markdown files. Anything any anything substantive that the user shares with you, make sure to save it somewhere. Either it goes in your cloud.md or it goes in a markdown file or it goes in some other file, but it's got to be saved somewhere."

</details>

**主持人**: 是的，我想我的痛点在于，即使使用 Obelus，它也会创建大量重复的文件。智能体不知道它其实已经有了类似的内容，然后就会创建另一组重复的文件。现在我就有了两个事实来源，对吧？

<details>
<summary>Original English</summary>

**Host**: Yeah, I I think my my probably both days is just that even using Obelus, it would create a lot of duplicate files, which is like not know that it already has a similar thing and then you just create another duplicate set of files. And now I have like two sources of truth, right?

</details>

**Kovid Goyal**: 是的，你必须在它之上加上其他的指令，比如：“对你所有的文件创建一个索引，并将这个索引保存在你的指令中。查看你拥有哪些文件，然后再去保存它。”

此外，你确实需要一个后台进程，每天或每隔几天运行一次，检查你的内存文件，找出重复项并打上标记。

在这一块确实还有很多工作要做，我们目前还没有实现这些。我知道有些其他的智能体正在……

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, you got to have other instructions on top of that saying, "Create an index of all your files and save that index in your in your instructions. See what files you have, then go and save it." And then you do need to have like a background process that runs daily or or every few days looking over your your memory files and finding the duplicates and flagging them. Uh yeah, there's definitely a lot more to do there that we're not doing yet. I know some of the other kind of claws are

</details>

**主持人**: 有什么开箱即用的方案吗？听起来你只想用你自己的。

<details>
<summary>Original English</summary>

**Host**: Anything off the shelf, sort of say. Sounds like you just want your own.

</details>

**Kovid Goyal**: 我不认为基于检索的解决方案（Retrieval-based solutions）是个人助理的理想选择。

因为个人助理的场景非常具体，而这并不是检索真正擅长的事情。比如，如果你问你的助理：“我这周应该关注的最重要的事情是什么？”

没有任何基于检索的搜索、语义搜索或关键词匹配搜索能够为你的智能体提供这个信息。

但如果你有一个很好的 LLM Wiki，里面记录了：你正在进行的项目有哪些、时间线是什么、你这周开过的不同会议的记录，智能体就可以浏览这几个不同的文件，收集信息并为你提供那个列表。

<details>
<summary>Original English</summary>

**Kovid Goyal**: I'm not sure that like retrieval based solutions are are ideal for like personal assistant because it's very specific and it isn't necessarily uh something that retrieval is really good at. Like if you ask your assistant, "Um what are the most important things I should be focusing on this week?" There's no retrieval based search, semantic search, keyword matching search that's going to be able to give your agent that information. But if you have a good LM Wiki that has like here are the projects you're working on, here's the timeline, here are the you know, here's a log of the different calls you've had this week, it can go through a few different files and collect the things and give you that list.

</details>

### 从开源项目到商业化服务

**主持人**: 是的，太棒了。这真的很酷。我记得上一个版本是你的公司做的，对吧？当我第一次给你发消息时，你还在做营销方面的工作。但现在你创立了 Nanocloud Co.，那是什么？它的愿景是什么？它会是一个 VC 风格的初创公司吗？听起来是这样吧？

<details>
<summary>Original English</summary>

**Host**: Yeah, amazing. Um yeah, it's really cool. I I think last version is by your company, right? Uh when I first messaged you, you I still we still had a the marketing stuff. But now you've started Nanocloud Co. Uh what is Nanocloud Co? What's the vision? Uh is it going to be a VC style startup or sounds about right?

</details>

**Kovid Goyal**: 我们转向了。当我们第一次交谈时，当我刚创建 OpenClaw 的时候，我们正在建立一个 AI 原生的营销机构。我们有一些客户，业务也在增长，进展很顺利。

我最初只是在周末把 Nanocloud 作为一个个人副业来开发，供我自己使用。随后我把它发在了 **Hacker News** 上，采用的是 MIT 开源协议。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Nanocloud is we shifted gears. We were when I first spoke to you, when I first created Open Claw, we were building a AI native marketing agency. We had some customers. We were ramping up. It was going well. I built uh Nanocloud just for my own use as a side project on the weekend, launched it on uh Hacker News, MIT license.

</details>

**主持人**: 我就是在那第一次发现它的。我还发了推特。

<details>
<summary>Original English</summary>

**Host**: That's where I first found it. I tweeted about it.

</details>

**Kovid Goyal**: 是的，在它发布后的几个小时内。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, yeah, or immediately within like hours, I think after it came out, I

</details>

**主持人**: 好的。当时我觉得，我读不懂这个代码库，我读不懂 OpenClaw 的代码库。

<details>
<summary>Original English</summary>

**Host**: Okay, like I can't read this code base. I cannot read Open Claw code base.

</details>

**Kovid Goyal**: 这正是它背后的设计初衷。因为我说过，我要构建一个我认为在结构上合理、安全且可读的系统。但我不太敢完全相信自己，所以我希望让它保持可读性，让其他人可以查看并验证它。

从那以后，我邀请了很多安全专家来审查、评判它并给出反馈，指出了一些小问题。但最核心的结论是，我们的基本方法是成立的，因为没有人指出我们在总体架构方案上存在问题。

所以，我们当时在建立那个营销机构。我为自己开发了 Nanocloud。接着它开始获得大量的关注和流量。随后 Karpathy 转发了它，这直接把它带到了一个全新的高度。

有一段时间，我们内部还在争论我们应该继续做营销机构，还是全力以赴开发 Nanoclaw。在 Karpathy 转发之后，一切都变得很清晰了——这里有一个如此庞大的社区，背后有如此多的能量。

所以，我们现在全力以赴。我们成立了公司。我们现在有 10 个团队成员。

而且我们发现，不仅是 Nanocloud，包括 OpenClaw、Hermes 在内的所有类似智能体项目的早期采用者，很多都是 VC 公司的 CEO 和高管。他们自己在使用，并且对此感到非常兴奋。

我们有大量的 CEO 和高管联系我们说：“嘿，我自己搭建了这套很棒的配置，我有三个不同的智能体，还有这套内存系统。”就像新加坡的外交部长一样。

他们说：“我想把这套系统推广给我团队的每个人。但我不想成为那个天天帮他们修智能体、调内存 Bug 的 IT 维护人员。你们能来帮我的团队搭建这套系统吗？”

<details>
<summary>Original English</summary>

**Kovid Goyal**: That was the idea behind it cuz I said I'm going to build something that I have an idea of the right right way to structure it to make it kind of sane and secure, but I I don't quite trust myself with it, so I want to make it readable and let other people look at it and validate it. And since then I've had a lot of security experts review it and and critique it and give feedback and point out small things, but what's come out of all of that is that the core approach seems to be sound because nobody's pointed out an issue with uh general approach. So, we were building that agency. I built Nanocloud for myself. It started to get a ton of uh traction and attention. And then Karpathy uh tweeted about it and it went to just a whole 'nother level. And for a little while we were debating if we should build the agency or build Nanocloud. And then after Karpathy, it just became clear like there's such a big community, so much energy behind this. So, we went in all in on it. Um we we have a company now. We've got 10 people on the team. Uh and what happened was the early adopters, I think not just of Nanocloud, but Open Claw, Hermes, every all the claws have been a lot of VC CEOs, executives who are using it themselves and get really excited about it. And we've had tons of CEOs and other executives approaching us and saying, "Hey, I built out this great setup for myself. I've got these three different agents, this memory system." Just like uh the the Minister of Foreign Affairs here. Uh and they say, "I want to roll this out to everybody in my team. But I don't want to become the IT guy who's now like fixing their agents and debugging the memory issues. Can you guys come and help me set this up for my team?"

</details>

### 企业级智能体的部署与维护挑战

**主持人**: 是的，所以现在你们变成了一个智能体实验室（Agent Lab），你们在托管这些配置。

<details>
<summary>Original English</summary>

**Host**: Yeah, so now you're now an agent lab like you're in willing it all of this hosted mental.

</details>

**Kovid Goyal**: 是的，我们将为很多公司提供部署服务。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, so we're going to do deployments uh and for a lot of companies

</details>

**主持人**: 我在演讲里提到过，这应该在喝啤酒时聊。

<details>
<summary>Original English</summary>

**Host**: Things I said in my talk that would be right right over beer.

</details>

**Kovid Goyal**: 我回去会补看一些演讲。

<details>
<summary>Original English</summary>

**Kovid Goyal**: I'm going to go back and catch up on some of the talks.

</details>

**主持人**: 这属于开发者路线，但更侧重于知识工作（knowledge work）而非单纯的代码编写。

<details>
<summary>Original English</summary>

**Host**: Skilled at the dev in journey but like more focused on knowledge work rather than coding.

</details>

**Kovid Goyal**: 是的，我会补看你的演讲和其他几个人的演讲。所以，对于很多公司来说，部署意味着要将系统部署在他们自己的基础设施或他们自己的云上。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, I'm going to get catch up on your talk and a few others. So, yeah, the going to do the deployments uh for a lot of companies it's going to mean deploying on their infrastructure to their cloud.

</details>

**主持人**: 记录来自我团队的笔记。这正是那些人会跟你提的要求，比如单点登录（SSO）、VPC 对接（VPC Peering）以及私有化部署（On-prem deployments）等所有这些事情。

<details>
<summary>Original English</summary>

**Host**: Taking notes from my team. It is exactly those like people are going to tell you about like SSO and like uh uh BBC peering and like on-prem deployments, all that stuff.

</details>

**Kovid Goyal**: 是的，我们必须对接他们的凭证管理系统。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah, we're going to have to hook up to their credential management system like

</details>

**主持人**: 从他们的保险库中获取凭证。在 AI 领域，很多这类工作目前还没有标准化。

<details>
<summary>Original English</summary>

**Host**: Getting their credentials from your their vault or yeah, on AI is like actually a lot of it is not yet.

</details>

**Kovid Goyal**: 的确还没有。但你必须理解 AI。我认为这是很多公司目前所缺失的。他们拥有优秀的工程师和运维团队。我和很多这些公司聊过，他们也有很棒的安全团队。

但是如果你缺少了 AI 工程（AI Engineering）这一环，你就很难把不同的碎片拼接在一起，也很难确保你构建的系统是安全的、可用的，并且架构是正确的。

所以，我认为这更多是 AI 工程师进驻并与他们的运维团队、安全团队和 IT 部门合作，帮助他们完成初始配置，并在后续帮助他们进行长期管理。

最开始，你必须把它连接到他们的凭证管理、可观测性（observability）以及其他安全系统，然后帮助他们完成与内部数据源的首次集成。

但随着时间的推移，他们的 IT 团队和安全团队可以接手这些工作。当有新的数据源集成需求时，他们完全可以自己搞定。

但在升级和维护方面，依然需要持续的管理。

智能体与传统的软件不同。传统的企业软件，你部署在服务器上，让它运行五年，只要你别去碰它，它就能一直正常工作。

智能体可不是这样。你所构建其上的核心技术在随着时间不断发生变化。你不可能在接下来的三年里一直运行 GPT-4.6（注：原文 4.6 可能是口误或泛指）然后不管它。你必须升级到 4.8、4.9、5。

而每一次升级都会带来变化。

AI 实验室也在不断推出新的功能和属性，内存功能正在被直接集成进 LLM 和智能体本身。为了保持领先，你必须不断地进行更新。

这就是我们将要开展的工作。我们已经开始进行我们的第一批部署。目前有超过 100 家公司联系我们，表示有兴趣引入这些智能体。

我们很快就会有重磅消息宣布。

<details>
<summary>Original English</summary>

**Kovid Goyal**: It's not. But uh you have to understand the AI. I think that's what's missing for a lot of these companies. They have good engineers, they've got good devops. I spoke to a lot of these companies. Um they've got good security teams. But if you don't have the piece of the AI engineering, it's hard to put together the different pieces and to have confidence that what you built is secure, it works, and and it's it's the right setup. So, having I I I think of it more as a partnership between AI engineers coming in and working with the their devops, their security team, their IT department, and helping them get set up the initial setup, and then afterwards helping them manage it over time. Uh initially, you got to connect it to their credential management, observability, their other security systems, um and then help them get set up with their initial integration with their internal data sources. Um but then over time, their IT team, their security team can pick up those pieces, and when there's a new request for integrating with a new data source, they can take that on their own. But there's still management to do in terms of upgrading and maintaining it. Agents are different than normal software in that normal enterprise software, you can deploy it, put it on some server, and let it run for like 5 years, and as long as you never touch it, it just works. Uh agents don't really work that way. The core thing that you're building on is constantly changing over time. You can't just run 4.6 for the next 3 years and just leave it. You got to upgrade to 4.8, 4.9, 5. And every one of those upgrades changes things. Uh and and the labs are putting out new features, new capabilities, uh memory is getting baked into the LLM, getting baked into the agents, uh and you have to be constantly updating in order to just stay kind of at the at the front. So, that's what we're going to be doing. We started to do our first deployments. Uh we've got over 100 companies that have approached us interested in rolling out agents. Um and yeah, big announcement's coming up.

</details>

### 开源协作与 Wiki 知识库的未来

**主持人**: 两个偏哲学的问题。第一，对于你的智能体工厂，你认为 Git 和 GitHub 还能存在多久？

<details>
<summary>Original English</summary>

**Host**: Two philosophical questions. One, uh for your agent factory, do you think that Git and GitHub will last?

</details>

**Kovid Goyal**: 我认为对我们来说它们必须存在下去，因为我们是一个开源项目，有着独特的社区文化。

<details>
<summary>Original English</summary>

**Kovid Goyal**: I think it's going to have to last for us because it's we're an open source project, and you've got the culture in the community.

</details>

**主持人**: 我在试图看什么会取代 GitHub。

<details>
<summary>Original English</summary>

**Host**: Uh I'm trying to see what comes after GitHub.

</details>

**Kovid Goyal**: 我暂时也没有头绪。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah.

</details>

**主持人**: 知道吗？

<details>
<summary>Original English</summary>

**Host**: have any idea.

</details>

**Kovid Goyal**: 这中间确实存在一些冲突，对吧？因为整个智能体工厂的协作应该发生在 GitHub 上，而不是发生在 Slack 里。

但是因为这是一个开源项目，如果是闭源的，我们只需要让智能体在 GitHub 的 Pull Requests 中留下回复、进行审查、提交测试结果就行了。

但因为这是开源的，我不想把针对我们智能体底座的内部讨论，在公开的 GitHub 线程里展开。这虽然可能很有趣，但感觉有点奇怪。

但如果这是在公司内部，我确实希望它发生在 GitHub 上，但此时我们又会遇到另一个问题，即 GitHub 目前的形式似乎并不太适合这种工作流。

<details>
<summary>Original English</summary>

**Kovid Goyal**: There is a weirdness there, right? Because the whole agent factory should be on GitHub and not happening in Slack. But because it's an open source project, like if it was closed source, we would just have the agents leaving responses, doing the reviews, test results, it would just all be in the in the pull requests on GitHub. Because it's open source, I don't want to have an internal discussion back and forth, leaving feedback for my agent meta, you know, feedback on the factory itself happening in a public uh GitHub thread. It could be interesting, but it seems a bit off. Uh but if this was internal, I would want it to be on GitHub, and then I think we would be running into the issues where GitHub probably still isn't quite the right format of that.

</details>

**主持人**: 我的团队是在 Slack 里完成所有工作的，然后他们付费让我去 GitHub 上合并（stamp）PR。但是，我为什么还需要 GitHub 呢？我应该直接在 Slack 里完成所有工作。

<details>
<summary>Original English</summary>

**Host**: My my people do all their stuff in Slack, and then it's they pay me to stamp the the PR in GitHub. But like, why do I need to Why do I need GitHub at all, you know? Like, I should just be in the Slack.

</details>

**Kovid Goyal**: 好的，所以也许我们的方法是对的。等一下，所以我们把整个流程放在 Slack 里，然后……

<details>
<summary>Original English</summary>

**Kovid Goyal**: Okay, so maybe our approach is the right way. Wait. So, we have the whole thing in Slack, and then

</details>

**主持人**: 这就是我目前运行 IE 的方式。

<details>
<summary>Original English</summary>

**Host**: That's how I'm running IE.

</details>

**Kovid Goyal**: 一直进行到，比如合并阶段，然后你点击同意，它就会被合并。我认为这里有很多可以做的。Slack 拥有相当不错的 UI，你完全可以在 Slack 里构建出很好的用户体验。

<details>
<summary>Original English</summary>

**Kovid Goyal**: And all the way till, you know, merge, and then you hit approve, and it gets merged. Um and I think there's a lot to do. Slack has good pretty good UI. You can you can build out some good uh user experiences just in Slack.

</details>

**主持人**: 那在 Slack 之外呢？你可以用 WhatsApp 吗？还是你只用 Slack？目前 Telegram 和 WhatsApp 的使用量也很大。我很喜欢 Telegram。

<details>
<summary>Original English</summary>

**Host**: So, Slack over what? Can you use this WhatsApp? You use Slack. There's like a lot of Telegram. I I like I like Telegram's like there's so much usage that I'm bought to Telegram. Yeah. But you can't do you know that.

</details>

**Kovid Goyal**: 我对不同的即时通讯软件做过分类。

我认为第一梯队（S tier）是 Slack，然后是 Discord 和 Teams。

再往下是 Telegram，然后是 WhatsApp。它们能做的事情非常受限，开发起来很难。

比如，如果你想要获得体面的体验，你可能需要拥有一个独立的手机号码，把机器人挂在你自己的号码上。如果你只是想以只读方式查看消息，这可能行得通；但如果你想在自己的号码上和机器人聊天，这很容易把你的对话搞乱。

<details>
<summary>Original English</summary>

**Kovid Goyal**: I can do my uh my tiers of our messaging apps. So, I think uh S tier would be uh Slack. Uh and then Discord, Teams. And then goes like Telegram, and then WhatsApp. They're very very limited in what what you can do, and it's hard. Like, you have to have your own phone number if you want like a decent experience. Uh chatting putting the bot on your own number, it makes sense if you wanted to just see your messages read-only, but to chat with the bot on your own number, it's I mess you up.

</details>

**主持人**: 我完全没有在这方面做过尝试。

<details>
<summary>Original English</summary>

**Host**: I haven't experimented with it at all.

</details>

**Kovid Goyal**: 噢天呐，体验非常糟糕。你甚至无法给自己发消息，因为我需要一个单独的号码来接收它。所以我就直接放弃了。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Oh my god, it's uh terrible. Uh you can't I I can't message myself because I needed a separate number to to receive it. So, I I just gave up.

</details>

**主持人**: 好的，所以在那个分类榜单上，它排在 WhatsApp 之下。我们已经填满了我们的整个分类榜单。

看还能更糟到什么程度。显然，你必须购买你自己的号码，这很烦人。不过我想有一些服务提供这个。

最后一个问题。大家能怎么帮到你？你正在寻求什么帮助？你希望得到解答的问题是什么？

<details>
<summary>Original English</summary>

**Host**: Okay, so that's below WhatsApp on that tier list. We've filled out our whole tier list. See what worse it is. Obviously, you have to buy you have to buy your own number. But like, it's annoying. I I think there's some services that do that. Anyway, uh last last question. What can people help you out? What are you looking for help? What are you looking at like What is a question you want answered?

</details>

**Kovid Goyal**: 在今天，管理开源项目是一个巨大的挑战。对于 AI 工程师，我甚至不会说让他们去提交 Pull Request。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Managing open source projects today is is a huge challenge. So like I would say I won't even say for for for AI engineers, I won't even say contribute a pull request. It's like

</details>

**主持人**: 我明白你的意思。

<details>
<summary>Original English</summary>

**Host**: I mean

</details>

**Kovid Goyal**: 提交 PR 甚至就是问题的一部分。是的，主要是分类整理（Triage）。帮助我们弄清楚如何以更好的方式管理开源项目。

这是一个巨大的开放性挑战。这就像一场军备竞赛，编码智能体（Coding Agents）让人们提交 Pull Request 的门槛呈指数级降低。

但这让项目的分类、审查和理解这些 PR 是否符合项目方向变得极其困难。

<details>
<summary>Original English</summary>

**Kovid Goyal**: It's part of the problem. Yeah, it's like triage. Help us figure out how to manage a open source project in a better way. Um it's a big open challenge. It's like this it's an arms race where coding agents have just made it exponentially easier for people to open pull requests. And then it's so hard to to triage, to review, to understand that it's aligned with

</details>

**主持人**: 这就像你刚才说的，不再是 Pull Requests，而是 Prompt Requests。比如，不要给我你的代码，给我你的具体用例。

在讨论完这些后，我脑海中浮现的一个想法是：你会有比如这里有个 Bug、那里有个功能请求等等。

所有这些都应该进入到一个未来开发的 Wiki 中。然后你从 Wiki 中提取需求。所以 Wiki 就像是一个缓冲区。所有的变更以持续流的形式进来，但它们会被整理成 Wiki，然后你在需要的时候从 Wiki 里拉取任务。

<details>
<summary>Original English</summary>

**Host**: The same as what you saying saying, right? No more pull requests, only prompt requests. Like don't give me your code, give me your what what your use cases. And then something that comes to my mind after having this discussion is you have all these like oh you know, my bug here, my feature request here, whatever. It should just come in all go into a wiki of future developments. And then you pull from the wiki. So like the wiki is kind of a buffer. All the changes come in as a continuous stream stuff. But it becomes a wiki and then you pull from the wiki as you as you eat.

</details>

**Kovid Goyal**: 是的。我们已经开始为我们的智能体工厂构建一个 Wiki。

<details>
<summary>Original English</summary>

**Kovid Goyal**: Yeah. We have started to build a wiki for our agent factory.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Kovid Goyal**: 所以在开发它的过程中，我们在每次合并、每次提交时都在往 Wiki 里添加内容。我认为这会成为构建开源项目的一个标准流程。

你们用 Deep Wiki 做的事情非常棒。我认为这会成为团队实时进行开发并构建 Wiki 的标准。

未来的开发计划都记录在 Wiki 中，并连接到项目的不同相关部分，Bug 也作为该 Wiki 的一部分。

然后当你开发时，每次开始工作，你从 Wiki 中拉取信息以获取上下文；当你完成 PR、完成提交后，你再向 Wiki 回传更多的上下文。

<details>
<summary>Original English</summary>

**Kovid Goyal**: So as we're developing it, we're adding to the wiki kind of on each merge, on each commit. And then I think that is going to become a standard part of building open source project. So what you guys are doing with is it Deep Wiki? That's awesome. I think though that it's going to become a standard for teams to build out the wiki as they're doing the development in real time. And then yeah, the the the future development is in the wiki linked to the different parts of the project that it's related to and the bugs are part of that wiki. And then as you're developing it, each time you start working, you pull information from the wiki to get context and then you finish the PR, finish commit and you push back to the wiki some more context.

</details>

**主持人**: 好的，非常棒。非常感谢你能来，很高兴见到你。我相信这不会是我们的最后一次见面。祝你接下来的旅程愉快。

<details>
<summary>Original English</summary>

**Host**: Yeah, great, great. Well, thanks for coming. I'm so glad to meet you. Uh sure is not the last time but we'll see you. All right, but hopefully this has been a nice trip so far.

</details>

**Kovid Goyal**: 体验非常棒。是的，很高兴能来到这里。

<details>
<summary>Original English</summary>

**Kovid Goyal**: It's been awesome. Yeah. Great to be here.

</details>

**主持人**: 谢谢。

<details>
<summary>Original English</summary>

**Host**: Thanks.

</details>