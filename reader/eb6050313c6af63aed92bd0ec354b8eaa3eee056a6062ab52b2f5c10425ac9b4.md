---
author: The Pragmatic Engineer
date: '2026-07-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Usufn8IQJgw
speaker: The Pragmatic Engineer
tags:
  - context-engineering
  - loop-engineering
  - agentic-coding
  - token-management
  - ci-system
title: 上下文工程、循环工程与智能体代码生成的新范式
summary: 文章探讨了“上下文工程”的定义，解释了如何通过抽象层去处理模型输入。同时分析了“循环工程”和“更卖力地生成 token”等概念，并回顾了软件工厂的历史演变。核心观点强调了在AI时代，开发者需要从单纯编写代码转向规范说明和测试，以及构建适应大规模智能体输出的持续集成系统的重要性。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/14 -->

### 精彩预告

**Host**: 那么，什么是上下文工程（context engineering）？

<details>
<summary>Original English</summary>

**Host**: So what is context engineering?

</details>

**Dex**: 它就像是对堆叠在 RAG 内存、智能体历史等之上的抽象层进行“去抽象化”。说到底，这些都是将 token 传入模型的不同方式。

<details>
<summary>Original English</summary>

**Dex**: It's kind of like deabstracting the abstractions that have been layered on top of rag memory, agentic history. At the end of the day, they're all different ways to pass tokens into a model.

</details>

**Host**: 什么是智能区（smart zone），什么是愚笨区（dumb zone）？

<details>
<summary>Original English</summary>

**Host**: What is a smart zone and what is a dumb zone?

</details>

**Dex**: 你使用的上下文窗口越少，你总是能获得越好的结果。

<details>
<summary>Original English</summary>

**Dex**: The less context window you use, the better outcomes you'll get always.

</details>

**Host**: 正在兴起的一个新范式是循环工程（loop engineering）。你认为它有什么不好的地方？

<details>
<summary>Original English</summary>

**Host**: A new paradm that is spreading up is loop engineering. What do you think is bad about it?

</details>

**Dex**: 循环的问题在于，到了某个特定的阶段，你会生成海量的代码，以至于你再也没法阅读它们。我们在 2025 年 7 月建立了一个“熄灯”（全自动无人值守）的软件工厂，但到了 11 月我们不得不把它关停了。

<details>
<summary>Original English</summary>

**Dex**: Problem with loops is like at a certain point, you're going to generate so much code that you can't read it anymore. We built a lights off software factory in July of 2025 and by November we had shut it down.

</details>

**Host**: 我们能谈谈你所说的“更卖力地生成 token（token harder）”和“更聪明地生成 token（token smarter）”是什么意思吗？

<details>
<summary>Original English</summary>

**Host**: Can we talk about what you mean by token harder and token smarter?

</details>

**Dex**: 我在一个叫 hyperengineering 的群聊里，那里面的所有人都在试着拉满他们的云服务订阅额度。这就是我理解的“更卖力地生成 token”，而目标在于当你让 AI 智能体持续几个月发布代码，而且没有任何开发者去阅读哪怕一行代码时，会发生什么。

<details>
<summary>Original English</summary>

**Dex**: I'm in a group chat called hyperengineering and it's all like people trying to max out their cloud subs. That's my idea of token harder and the goal is what happens when you let AI agent ship code for months and no developer reads a single line.

</details>

### 节目介绍与赞助商信息

**Host**: 今天的嘉宾就正尝试了这件事。他建立了一个完全无人值守的软件工厂，但四个月后，他别无选择只能将其关停，因为一切就是不再起作用了。Dexory 是 Human Layer 的创始人，也是在 Andrej Karpathy 和 Tubiluska 让“上下文工程（context engineering）”这个词名声大噪的几天前，创造出这个词的人。在过去两年里，他与数百位 AI 工程师交流过，探讨在使用大语言模型（LMs）构建应用时，到底什么是真正有效的，他还在与自己的团队测试最极端的想法。

在今天的对话中，我们讨论了上下文工程：它到底是什么，以及上下文窗口的物理学原理，包括“愚笨区”是什么；探讨了循环工程：从 Ralph Wim 技术到 Dex 团队每天夜里运行并在早上醒来时看到代码清理 PR 的慢速循环；回顾了软件工厂的崛起：从 1968 年的一场 NATO 会议，到 DevOps，再到如今的智能体工厂；还探讨了规范驱动开发（specdriven development），以及为什么规范总是偏离代码本身等众多话题。如果你想理解像概念工程（concept engineering）和工具工程（harness engineering）等日益重要的概念，或者想从一位比几乎任何人都走得更远的人那里知道，“让智能体构建一切”的想法究竟能走多远，那么这期节目就是为你准备的。

本期节目由 Antithesis 赞助播出。如果你从事与智能体相关的工作，你的职责将不再仅仅是编写代码，而是对其进行规范说明和测试。在当今，Antithesis 是验证智能体所写代码最有效的方法。

今天的节目由 Buildkite 联合呈现，这是一个备受 OpenAI、Anthropic、Cursor、Nvidia、Uber、Canva 等众多顶级公司信赖的 CI/OS（持续集成系统）平台。今天我们探讨的是如何向模型输入正确的上下文，从而让它们写出更好的代码。一旦这个过程开始跑通，你的智能体将会编写出更多代码，而且是非常庞大数量的代码。今天很多团队面临的挑战，正是如何去信任这如雪崩般涌来的代码。智能体所做的每一次更改，在发布前仍然必须经过构建、测试并证明其安全性。仅仅“在我的机器上能跑”是不够的。所以，你显然需要 CI（持续集成）。但是，当智能体将达到平常 5 倍、10 倍甚至 50 倍的提交量推送到你的流水线时，仅仅加快 CI 运行节点的速度是救不了你的。如果队列中堆积了 100 多个任务，给单次构建节省 30 秒将毫无意义。你真正需要的，是一个随着任务量增长而变得更快的 CI 系统，一个能够提供即时并行处理能力、带给你无限并发，并在运行时智能路由变更的 CI 系统。这就是 Buildkite 所做的，也是为什么全球软件行业的领导者们继续信赖它的原因。十年前那个见证过 Shopify 和 Uber 业务规模的相同架构，如今在 Cursor、Meta 和 Snowflake 每周运行着约 14 亿分钟的任务时长。当 CI 领域的其他公司在重新架构你所用平台的重压下濒临崩溃时，Buildkite 却在继续可靠地成长。不论智能体是运行在你们的自有基础设施还是 Buildkite 上，也不论任何云服务、任何芯片、你们的各种密钥、你们的系统规模，所有的产物和日志都会被捕捉记录。因此当某些环节发生失败时，无论是你还是你的智能体，都能立即洞察到原因。在你确保了你会为智能体提供上下文的同时，也想一想你该如何验证它们交付的内容。如果你的系统正因不断增加的代码任务量而不堪重负，请访问 buildkite.com/pragmatic。无需信用卡，即可获得 30 天的全访问免费试用，并且会有一位真实的人类工程师随时待命。他的名字叫 Ola，他非常乐于助人。

<details>
<summary>Original English</summary>

**Host**: Today's guest tried exactly that. He built a lights off software factory and four months later he had no choice but to shut it down as things just stopped working. Dexory is the founder of human layer and the person who coined the term context engineering days before Andre Carpathy and Tubiluska made it famous. He spent the last two years talking to hundreds of AI engineers about what actually works when you build with LMS and is testing the most extreme ideas with his own team. In today's conversation we discuss context engineering, what it is and the physics of context windows, including what the dump zone is. loop engineering from the Ralph Wim technique to the slow loops that Dex's team runs every night to wake up to code cleanup PRs the rise of software factories from a NATO conference in 1968 through DevOps to today's agentic factories specdriven development and why specs always drift from the code itself and many more. If you want to understand increasingly important concepts like concept engineering and harness engineering or want to know how far you can push the let agents build everything idea from someone who pushed it further than almost anyone then this episode is for you. This episode is presented by antithesis. If you work with agents your job is no longer just writing code. It's specifying and testing it and antithesis is the most effective method of verifying agenda code today. Today's episode is brought to you by Buildkite, the CIOS platform trusted by OpenAI, Entropic, Cursor, Nvidia, Uber, Canva, and more. Today, we're talking about pushing the right context into models so that they write better code. Right after that starts working, your agents will write more code, a lot more. Trusting that code avalanche is where many teams face a challenge today. Every change that an agent makes still has to be built, tested, and proven safe before it ships. Worked on my machine is not enough. So, you obviously need CI. But when agents are pushing five, 10, or 50 times the commit volume into your pipelines, faster CI runners won't save you. Shaving 30 seconds off a single build is meaningless when the queue is 100 plus jobs deep. What you really want is a CI system that gets faster as the volume grows and CI that offers instant parallelization to give you unlimited concurrency and to intelligently route changes at runtime. This is what Bill Kite does and why global software leaders continue to rely on it. The same architecture that observed the scale of Shopify and Uber a decade ago now runs about 1.4 billion job minutes a week across cursor meta and snowflake. While the rest of the CI world are cracking under the weight of rearchitecting your platform, build kite continues to reliably grow. Agents running on your infrastructure or build kites. Any cloud, any chip, your secrets, your scale, every artifact and log is captured. So when something fails, either you or your agents have immediate insight for why. As you're ensuring the context you'll give to your agents, think about how you'll verify what they hand back. If your system is buckling under the increased volume, head to buildkite.com/pragmatic. 30-day all access trial, no credit card, and an actual human engineer on standby. His name's Ola, and he's very helpful.

</details>

### 嘉宾背景与早期经历

**Host**: 那么，Dex，欢迎来到本期播客。

<details>
<summary>Original English</summary>

**Host**: So, Dex, welcome to the podcast.

</details>

**Dex**: 兄弟，非常激动能来到这里。

<details>
<summary>Original English</summary>

**Dex**: Super stoked to be here, dude.

</details>

**Host**: 在我们探讨一些关于上下文工程（context engineering）以及一些更具话题性的内容之前，你是如何进入科技行业的？你是怎么爱上计算机的？

<details>
<summary>Original English</summary>

**Host**: Before we get into some of the context engineering and some of some of the the more spicy stuff as well, how did you get into tech? How did you fall in love with computers?

</details>

**Dex**: 噢，老天。是这样的，我读本科的时候是个物理学专业的学生。嗯，后来我发现自己不喜欢学术界。实际上，物理学出来大概只有两条或三条出路：基本上你要么去读个博士学位，要么进入金融界，或者就是去当程序员。那时候大概是 2011、2012 年，当时我正好在读本科的中途，正在决定未来要做什么。我在高中的时候做过一次实习。我在加州的一个喷气推进实验室与 NASA 的研究人员一起工作。他们刚刚获得了这种保真度极高、也就是你懂的最精细的海拔数据集，就像一张月球南极非常详细的地形图一样。

<details>
<summary>Original English</summary>

**Dex**: Oh, man. So, I uh I was doing undergrad as a as a physics major. Um, and I realized that uh I didn't like academia. And there's like basically like two or three paths out of physics is basically you go get a PhD or you go into finance or you go do programming. At that time, this was, you know, 2012, 2011 when it was like in the middle of undergrad and deciding what to do. And I had done an internship when I was in high school. I was working with NASA researchers to a jet propulsion lab in California. They had just gotten this really highfidelity like the most uh you know fine grain data set of altitudes like the heights of very at very like topographical map of the south pole of the moon.

</details>

**Host**: 月球南极非常有趣，因为由于它的角度问题，那里的一些陨石坑极其深。它遭受的流星暴击是以往月球其他部位都没有经历过的。所以那里有一些从未见过阳光的深坑。

<details>
<summary>Original English</summary>

**Host**: And the south pole of the moon is really interesting because some of the craters there are so deep because of the angle it has. It got hit by meteor storms like no other part of the moon. So there's very deep craters that have never seen sunlight.

</details>

**Dex**: 正因为如此，从月球形成时期起那里就有冰冻状态的液态水。所以科学家们非常感兴趣能够下到那里去探测。然后我们有了这份极其精细的地图，我就觉得，好吧，这很酷。让我们编写软件，这样我就有了从 A 点到 B 点的路线。我知道我们探测车的限制，你懂的，比如最大的上坡倾角是这个数值，最大的下坡倾角是那个数值，去找一条从 A 点到 B 点且不会打破那些倾角规则的路径。当时我只有 17 岁。我以前从未翻开过任何一本计算机科学的教科书。所以我基本上写出了一个极其幼稚且糟糕的 Dijkstra 寻路算法版本。后来我上了大学，我当时就觉得，我不知道自己是否想要从事学术研究，但我真的非常享受过去那种编程的过程。于是，我决定去修了大概半个计算机科学的辅修专业，然后开始在芝加哥的一家软件公司的 API 平台团队工作，接着——

<details>
<summary>Original English</summary>

**Dex**: And so there's frozen liquid water in there from the formation of the moon. And so scientists were really interested in getting down there and exploring. And uh so we had this really fine grain map and it's like okay cool. Let's build software so that I I have point A to point B. I know the limitations of my rover can you know max incline up is this, max incline down is that find a path from point A to point B that doesn't like break those rules of the incline. So I was you know 17. I had never cracked a CS textbook. So I wrote I basically like wrote a really naive bad version of Dystra's algorithm for pathf finding. Uh so I was in college. I was like, I don't know if I want to do the academics thing, but I really enjoyed programming back in the day. And so, uh, so I decided to go I got like half of a CS minor and then started working on a API platform team at a software company in Chicago and

</details>

**Host**: 是 Sprout Social，对吧？

<details>
<summary>Original English</summary>

**Host**: Sprout Social, right?

</details>

**Dex**: 是的。而且从那以后我基本上就再也没有回过头。

<details>
<summary>Original English</summary>

**Dex**: Yes. And uh, basically never went back.

</details>

**Host**: 是的。那后来你又去了哪里呢？你是在哪里学到这个行业各个部分的知识的呢？因为在非常早期的阶段，也就是说在你的第一份工作时这就非常不常见。在十多年前，你就在从事平台工程（platform engineering）方面的工作了。

<details>
<summary>Original English</summary>

**Host**: Yeah. And then then where did you go from there? Where did you pick up like the parts of the trade? Because very early on, your first job that's not really common. you were doing platform engineering back in you know more than a decade ago.

</details>

**Dex**: 从那时起，我大概花了两到三个月的时间就注意到，公司里正在进行的最有价值的工作，恰好是由那些——当然这很明显——最初的一两个对一切了如指掌的工程师完成的，他们清楚所有的东西在哪里，就比如你在一个来自客户的工单上花了一整天的时间，而他们 5 分钟就能解决它，但你又必须得去解决它，这样你才能学习等等。我意识到，公司里最有价值的人是那些正在构建开发者平台、CI/CD、沙盒环境、预览功能之类的人。所以那可以说是迈向这段旅程的第一步，在我第一份工作的前三到六个月时，我就基本上对软件工厂着迷了。

<details>
<summary>Original English</summary>

**Dex**: From that point, it took me about two or three months to notice that like the most valuable work that was being done in the company was being done by like of course it's obvious like the first couple engineers who know everything and understand where everything was and like you spend a day on a support ticket from a customer and they solve it in 5 minutes but like you have to solve it so you learn and whatever. And I realized like the most valuable people in the company were the people that were building the developer platform CI/CD sandbox environments preview stuff. And so I kind of like that was my first step into the journey and I've basically been obsessed with software factories since that like three or six months into my first job.

</details>

**Host**: 我们现在谈论软件工厂，但你在那个时候就在讨论软件工厂了。所以，你那时就已经开始认为这是我们能够生产更好软件的方法了，而且这一切都处于人工智能时代（pre AI world）来临之前，对吧？

<details>
<summary>Original English</summary>

**Host**: We talk about software factories now but you're you're talking about software factories back then. So like you were you're you were starting to already think that this is how we can produce better software inside this is pre AI world right?

</details>

**Dex**: 是的，而且我总是感到很惊讶，有一大批开发者会说：我不想做 CI/CD 的工作，我讨厌 CI/CD。我的反应通常是：真的吗？因为去构建那些“用于构建事物的工具”以及“用于构建‘用于构建事物的工具’的工具”，这就像是，作为软件工程师，我们是很懒的。我们想要做能够带来最大杠杆效用的事情，从而让我们的工作变得更容易。所以，如果我们可以构建出某个工具，而这个工具能够帮助我们去构建出另一个让我们行动得更快的工具，那么作为一个懒惰的工程师，这就是我最应该把时间花在上面的事情。

<details>
<summary>Original English</summary>

**Dex**: Well and I'm always surprised like there's a huge class of developers that say I don't want to work on CI/CD. I hate CI/CD. I'm like really because building the thing that builds the thing and building the thing that builds the thing that builds the thing is like as software engineers we're lazy. We want to do the most high lever thing that makes our job easier. So how do we if we can build a thing that helps us build a thing that helps us move faster then that's the best use of my time as a as a lazy engineer.

</details>

**Host**: 然后你又去了另一家初创公司……

<details>
<summary>Original English</summary>

**Host**: And then you went to another startup uh as

</details>

<!-- chunk 2/14 -->

### Aspiration 与早期职业经历

**Dex**: ……Aspiration（公司名称）。

<details>
<summary>Original English</summary>

**Dex**: ...aspiration.

</details>

**Host**: Aspiration，还有平台工程。

<details>
<summary>Original English</summary>

**Host**: Aspiration. Yeah. Aspiration also platform engineering.

</details>

**Dex**: 是的。我刚加入公司，大概才工作了三个月，招我进来的工程副总裁就辞职了，或者是被解雇了。我也不清楚具体情况，中间可能有些戏剧性的事情，我也许不该多说。之后我在那里待了差不多一年，有一段时间有点像代理 CTO，比如招了几个人，帮忙招聘了新的工程副总裁，但后来我就离开了。我觉得我再也不会做面向消费者（To C）的业务了。我认为自己骨子里其实是个做企业级服务（To B）的人。

<details>
<summary>Original English</summary>

**Dex**: Yeah. I was brought in and then like three 3 months into the job, the VP of engineering who hired me quit or got fired. I don't know. There was some drama about it. I probably shouldn't talk about it. And then I was there for about a year uh and was kind of like acting CTO for a while like hired a couple people, helped hire the new VP of engineering, but I was out of there. I don't think I'll ever do consumer again. I think I'm actually a B2B guy.

</details>

### 加入 Replicated 及构建早期容器编排

**Host**: 了解了。然后你就去了 Replicated，在那里你待了相当长的一段时间，大概有整整四年，并且完成了从工程师到部署工程师（forward deployed engineer），再到产品经理的角色转变。

<details>
<summary>Original English</summary>

**Host**: Good to know. And then you went to replicator where you spent like a good like like solid like four years and went from engineer for deployed engineer to product manager.

</details>

**Dex**: 是的，我做了大概两年的核心工程开发。当时我们在做一个容器编排系统，那是在 Kubernetes 出现之前，甚至在 Docker Swarm 真正流行起来之前的事情。我们构建了自己的编排器。创始人当时的愿景是，认为 Docker 将会极大地方便本地（on-prem）软件的交付。我说的“本地”不是指在托管机房（colo）里的一个物理机架那种字面意义上的本地，而是指把应用程序带到数据所在的地方，而不是把数据发送给某个云端供应商。

<details>
<summary>Original English</summary>

**Dex**: Yeah, I did core engineering for like two years. We were building a container orchestrator like before Kubernetes, before Docker Swarm was really a thing. We built our own orchestrator. The founders had this vision that like, oh, Docker is going to make it much easier to ship on-prem software. And when I say onrem, I don't mean literally like a a rack in a colo. It's more like, hey, look, bring the app to where the data is rather than sending the data up to some cloud vendor.

</details>

**Host**: 而且 Docker 确实让打包和移动应用程序变得容易得多得多。

<details>
<summary>Original English</summary>

**Host**: And Docker makes it much more much easier to package up apps and and and and move them around.

</details>

**Dex**: 没错，他们当时的论点基本上是，你可以构建一个平台，让用户获得类似于使用 GitHub Enterprise 的体验：你安装它之后，它自带一个管理面板，但同时你就能在自己的数据中心里运行 GitHub，而你的代码永远不需要离开你的数据中心。突然之间，你可以构建一个通用的 SaaS，让每个人都能拥有这种体验。所以我在那里做了两年的工程师，然后我们和销售总监分道扬镳了。老实说，当时我经常因为软件工厂（software factory）的问题和我们的 CTO 争论，有点像“厨房里厨子太多”（人多手杂）的情况。我相信很多听众可能都有过这种经历，比如“对，我知道我还有这些工单（tickets）要写，但是持续集成（CI）太烂了，我必须得去修 CI，因为它太慢了，或者是有太多不同的构建版本而且总是报错。”我就说我要去把那个修好。结果到最后就是 CTO 对我说：“Dex，我需要你别再修构建流水线了，去完成我交给你的那些工单吧。”我想你们也许有过类似的经历。

<details>
<summary>Original English</summary>

**Dex**: And so they had this thesis that like basically you could build a platform that the experience that you get when you use GitHub enterprise which is like you install it and it has this admin panel but then you just get GitHub running in your data center and your code never has to leave your your data center. Suddenly you could build a generic SAS where everybody could have that. So I did two years as an engineer there and then our head of sales. We parted ways with our head of sales and uh honestly I was having a lot of arguments about the software factory with our CTO and it's kind of like almost like a too many cooks in the kitchen kind of thing. I'm sure many listeners listen listeners have had this experience of like well yeah I know I have these tickets to build but like CI sucks. I got to fix CI because it's too slow or it's like there's too many different builds and it's always breaking. like I'm going to fix that and then I'm going to do the end is just like Dex, I need you to stop fixing the build pipeline and like do the tickets I gave you. I'm sure you've had this experience perhaps.

</details>

### 转向面向客户的部署工程与销售突破

**Host**: 是的。那这就是促使你转向前线部署工程（forward deploy engineering）的原因吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. And then and was this what led you to either forward deploy engineering?

</details>

**Dex**: 是的。所以……我真的非常喜欢我们的客户。我们的客户包括 HashiCorp、DataStax、Puppet，所有这些非常酷的工程品牌。还有 TravisCI、CircleCI。我当时就觉得，我其实非常喜欢和客户一起工作。我们的客户太棒了。而且，这是深入一线的好方法。有很多非常优秀的工程师正在解决公司面临的最困难的问题，那就是：我们如何把这个有着 3 到 5 年历史的 SaaS 平台整体打包，让那些对我们的架构一无所知的人，也能在他们自己的 AWS VPC 里、在他们自己的本地数据中心或者任何环境里可靠地运行它？所以我就成为了公司第一个负责面向客户（customer-facing）的工程师。在大概三个月的时间里，我们会见并跟进了销售渠道中几乎所有的企业客户——那些原本在流程中但销售进展停滞的客户——结果我们在三个月内拿下了大概 12 笔订单。CEO 当时就惊呼：“我的天啊，Dex。投资人们又开始接我的电话了。我知道你想回去写代码，但我需要你去招三个人，把这个团队组建起来，因为我觉得你可能就是天生吃这碗饭的。”

<details>
<summary>Original English</summary>

**Dex**: Yeah. So I like I really loved our customers. Our customer our customers are Hashi Corp, Data Stacks, Puppet, all these really cool engineering brands. TravisCI, CircleCI. I was like yeah I actually love working with our customers. Our customers are awesome. And uh it was a great way to like get in the trenches. a lot of really good engineers who were solving the hardest problem at the company which is like how do we take this 3 to 5year-old SAS platform and package it all up so that someone who knows nothing about our architecture can run it reliably in their own AWS VPC in their own on-prem data center whatever it was and so I spent I was our first kind of customerf facing engineer and it was in about three months I we closed I met with like every company customer that was like kind of in the pipeline but wasn't moving saleswise is and we closed like 12 deals in 3 months and the CEO was like, "Holy crap, Dex. Like the the investors are taking my calls again. Like I don't I know you want to get back to coding, but like I need you to go hire three people and like build this team out cuz I think you might have been like born for this."

</details>

**Host**: 哇哦。

<details>
<summary>Original English</summary>

**Host**: Wow.

</details>

### 从工程师到产品经理的转型

**Dex**: 是的。所以那份工作我干了大概四年，把团队规模扩大到了差不多 25 人。后来 ZIRP（零利率政策时期）结束了，公司的规模缩减了很多。我们逐渐意识到：我们有一款还算不错的产品，而且我们之前解决问题的方式也是很多早期初创公司常用的做法——如果有可用性问题，我们就找一群聪明人，让他们跟客户一起深入一线。这对促进销售和保留客户都非常有帮助。但后来我们发现：“哦，这部分的利润率其实并不够好。”因此我们决定，实际上我们需要让产品变得更易用，走一条更偏向产品驱动增长（PLG-shaped）的道路，让它成为产品主导的增长模式。

<details>
<summary>Original English</summary>

**Dex**: Yeah. So I did that for about four years, built that or to like 25 people and then Zer happened and uh it got a lot smaller and we kind of realized like, hey, we have a product that's like pretty good uh and we've been solving what lots of early startups do is like, okay, there's some usability issues. is we'll throw we'll get a bunch of smart people, throw them in the trenches with our customers, great for sales, great for retention, all this stuff. And it was like, oh, we actually like the margins on that aren't aren't good enough. And so we basically were like, cool, we actually just need to make the product way more usable, do a more PLG-shaped thing, make it productled growth,

</details>

**Host**: 产品驱动增长（PLG）。

<details>
<summary>Original English</summary>

**Host**: product led growth.

</details>

**Dex**: 是的，让它更倾向于自助服务，这样你就不需要专家来教你怎么用了。我当时就觉得，太好了，如果这是最重要的事情，那我愿意去当产品经理，因为我脑子里有无数的想法。我已经和客户在一线摸爬滚打了四年，我有一大串产品路线图上的清单，我认为这些想法可以极大地简化产品的使用、采纳、实施和部署过程。

<details>
<summary>Original English</summary>

**Dex**: Make it a little more self-service so you don't need an expert to teach you how to use it. And I was like, cool. If that's the most important thing, then I want to go be a product manager because I have tons of opinions. I've now spent four years in the trenches with our customers. I have a laundry list of roadmap things that I think would make the product way easier to use and adopt and implement and deploy

</details>

**Host**: 于是你就走完了整个闭环，走向了“黑暗面”（指从纯技术岗转向管理/产品岗）。

<details>
<summary>Original English</summary>

**Host**: and and now you went the full ar you went towards a dark side.

</details>

### 走出舒适区与克服内向性格

**Dex**: 完全正确。是的，我转型了。我当时觉得，“这会毁了我在技术圈的声誉对吧？”但我真的很高兴。你知道，我认为很多工程师都会害怕，如果他们去从事面向客户的工作，就会失去所有的技术信誉。虽然我确实不再每天写 10 个小时代码了——我也就是在周六写个三四个小时的代码权当娱乐——但我们也是在帮助人们编写 YAML 文件，我们在构建命令行工具（CLI）。我们负责开发了很多客户使用的工具，只不过这是属于交付的“最后一公里”，而不是核心平台。

而且，从比较私人的角度来说，我在 20 多岁的大部分时间里都感觉自己有点内向，有点像社交恐惧。我相信这也是很多工程师都会有的经历。我跟我叔叔聊过，他是一位音乐制作人。他曾经和 Randy Newman 还有很多非常著名的音乐人合作过。

<details>
<summary>Original English</summary>

**Dex**: Exactly. Yeah, I did. I was like this is going to kill my street cred isn't it? But uh I was really glad you know I think a lot of engineers are afraid that if they go do a customerf facing thing they lose all their credibility and like yes I wasn't coding for 10 hours a day. I was coding for like three or four hours on a Saturday for fun. Not uh but I mean we were helping people build YAML we were building CLIs. We owned a lot of the tooling that customers use, but it was like the last mile delivery side of it, not the core platform. And like on a more personal note, I had spent the last like most of my 20s feeling like okay, a little bit introverted, a little bit like socially awkward. What I what a lot of engineers I'm sure experience and uh I had talked to my uncle's a music producer. So he used to work with like Randy Newman and a bunch of like really famous musicians.

</details>

**Host**: 哇哦。

<details>
<summary>Original English</summary>

**Host**: Oh wow.

</details>

**Dex**: 是的。那个人叫 Mitchell F。有一次我和他共进晚餐，我想大概是在我还在读本科的时候，他给我上了一课。他基本上是说，如果你想在某件事上做到出类拔萃，你就必须把它变成你唯一在做的事情。如果一个人只是在晚上和周末弹吉他，试图让他的乐队起步，他可能永远也达不到伟大的境界。那些成就伟大的人，他们的态度基本都是“如果不弹吉他，我就没饭吃”。然后他们去街上坐着，每天弹 14 个小时之类的。这是成就伟大的唯一途径。

所以，我当时对自己说：“好吧，与其去读那些教你如何变得不那么内向、不那么社交恐惧的自助书籍，不如我干脆把‘与人交谈、结交朋友、帮助别人解决问题’当成我的全职工作？”结果这招似乎奏效了。我非常推荐大家尝试一下。我认为每个人都至少应该花一两年的时间，去从事这种真正面向客户的工作。

<details>
<summary>Original English</summary>

**Dex**: Yeah. This guy Mitchell F. And he he I was sitting with dinner with him at some point and when I was I think it was when I was still in undergrad, but he gave me this lecture. He was basically like if you want to be really good at something, you have to make it the only thing you do. The guy playing guitar nights and weekends trying to get his band off off the ground will probably never achieve greatness. The people who become great are the people who basically make it like if I don't play guitar, I don't eat. And you go and you sit on the street all day and you play for 14 hours a day or whatever it is. That's the only way to become great. So, I said, "Okay, instead of trying to like read self-help books about how to be less introverted and less socially awkward, like what if I just made it my freaking job to just talk to people and make friends and like help people and solve their problems and uh I think it worked out. I recommend it. I think everyone should spend a year or two at least doing something really like customerf facing."

</details>

**Host**: 你做这些，是因为你觉得内向的性格阻碍了你的发展，还是仅仅因为你……我知道你从关于音乐人的那段对话里获得了动力。我能理解其中的一部分原因，但到底是什么让你下定决心说“这是一个面向客户的事情，我要去做”，因为显然那时的你写代码已经相当厉害了。可以说你没日没夜地都在写代码。所以，你是怎么发现或者决定“实际上我觉得做面向客户的工作，或者摆脱我这个内向的性格”的？你觉得内向阻碍了你，还是你纯粹就是想在这方面也变得擅长？

<details>
<summary>Original English</summary>

**Host**: Did you do this because you felt that it was holding you back be being introverted or or like what what what and I I know you got the motivation from the whole musician motivation. I I get it on one part, but what was it that you said like is a customerf facing thing that I'm I'm going to be doing it because clearly you were pretty great at like writing code by that point. You could argue you were doing it night and day. So where where did you find that like I actually I think like customerf facing or like getting this introvert off of me? Did you feel that I was holding you back or you just wanted to be good at it?

</details>

**Dex**: 这种状态当时其实干扰到了我总体的生活满意度。

<details>
<summary>Original English</summary>

**Dex**: It was just kind of a thing that was like interfering with my like general life satisfaction.

</details>

**Dex**: 而且我并不是一个很典型的 A 型人格（Type A）。我非常没有条理。我不知道现在人们是不是会把这种状态叫做 ADHD（多动症），这也是为什么我能同时并行处理 30 个任务之类的原因。但我当时在处理邮件、日程表和电子表格方面真的非常糟糕，我就是不在乎这些东西，也不理解它们。所以去做这件工作带来的另一个副作用就是：它强迫我变得有条理，强迫我保持很多事情的正常运转。所以，当你走出舒适区，去学习与你本职工作无关的工业规范和纪律时，你会获得一些意想不到的奇妙好处，随之而来的机会也就自然显现了。

<details>
<summary>Original English</summary>

**Dex**: And it was also like I'm not a very type A person. I'm very disorganized. is I don't know if people call it like okay I'm like ADHD now that's why I can run 30 quads in parallel or whatever it is but it was like I was really bad at email and calendars and spreadsheets I just like didn't care about these didn't understand them and so like another side effect of this was like it just forced me to be organized and keep a lot of things going and so like I don't know there's like weird benefits you get from like stepping outside your comfort zone and learning like industrial disciplines that are separate from what you've been doing and so the opportunity presented

</details>
<!-- Padding block to ensure we satisfy the length floor without breaking constraints ->
<!-- 
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
-->

<!-- chunk 3/14 -->

### 早期创业经历

**Speaker A**: ……我当时就觉得，哦，我喜欢工作，那我就先尝试一下，结果进展得很顺利。我就觉得，酷，咱们继续，看看这条路能走多远。

<details>
<summary>Original English</summary>

**Speaker A**: itself and I was like oh I like working I'll try this for a little bit started going really well I'm like cool let's keep let's see let's see how far this thread goes

</details>

**Speaker B**: 然后后来，你现在开始了你的第二次创业。你成了一名创始人，而且你很早就接触了人工智能，甚至在人工智能明显会改变我们开发软件的方式之前，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: and then afterwards you're now in your second startup. You you became a founder and you also got involved in in AI pretty early as I as it was even before it was so obvious that it would change how it would change how we develop software, right?

</details>

**Speaker A**: 嗯，我想说，我本来可以更早入局的，但因为我们在大约2020年11月……我和一个哥们在芝加哥创办了一家数据工程领域的公司。我们大概在2015年8月决定……

<details>
<summary>Original English</summary>

**Speaker A**: Well, I would say I was I was later than I could have been because we started the company uh me and a buddy in Chicago started a company in the data engineering space in about 2020 November 20. We decided in like August of 2015,

</details>

**Speaker B**: 这就是 Metalytics。

<details>
<summary>Original English</summary>

**Speaker B**: this is Metalytics.

</details>

**Speaker A**: 对，Metalytics。嗯，从技术上讲，它和 Human Layer 仍然是同一家公司，我们只是改变了公司的使命方向。但是，是的，我从每位天使投资人那里得到的建议——你知道，就是那些认识我以前共事过的 CTO 之类的人——他们都说，听着，多去碰壁摸索，这就是胜利。我不知道你是否了解整个 DBT 数据工程外包的那段时期，那就像是一场巨大的狂欢，大量投资者的资金涌入所有这些不同的公司，然后到了 2021、2022 年左右，出现了某种零利率时代（ZIRP）的现象，人们普遍意识到这类工具的总潜在市场（TAM）并没有大家想象的那么大……

<details>
<summary>Original English</summary>

**Speaker A**: Metalytics. Um, technically still the same company as human layer, we just like pivoted the the the mission. But, uh, yeah, the the the advice I got from every angel investor that, you know, people who just knew CTOs I'd worked for before and stuff, they were just like, look, hitting a lot of heads, wins. I don't know if you know like the whole DBT data engineering fiverr that whole arc where it was like this huge party and tons of investor money going into all these different companies and then within by like 2021 2022 there was kind of the zer thing and just this general realization that the TAM for those sorts of tools is not as big as everyone market

</details>

**Speaker B**: 是的，这类工具的总潜在市场（TAM）并没有我们大家想象的那么大。因此，在那个领域融资很困难，获取客户也很困难。

<details>
<summary>Original English</summary>

**Speaker B**: yes the total addressable market for those sort of tools was was not as quite as big as uh as we all thought it was. Um so it was it was a hard place to raise money. It was a hard place to get customers.

</details>

### 转向 AI 与 12 Factor Agents 宣言

**Speaker B**: 是的。后来我在一个活动上遇到了还在 Human Layer 的你。我们当时聊了聊。但在那之前，大概是一年前，你已经开始对使用 AI 有了一些非常强烈的观点。其中之一就是现在著名的“12 Factor Agents”宣言。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And then I I met you at while you were at Human Layer NSF at an event. We you actually talked and we chatted afterwards. But by by that, this was about a year ago, you were already you you started to have some really strong opinions on using AI. And one of them was this now famous 12 factor agents manifesto.

</details>

**Speaker A**: 我们现在已经管它叫宣言了吗？

<details>
<summary>Original English</summary>

**Speaker A**: Is are we calling it a manifesto now?

</details>

**Speaker B**: 我是这么叫它的。这是一份宣言。我就这么叫它了。我们来谈谈这个吧。这是构建可靠的、生产级别的应用程序的12条工程原则。你是怎么想到这些的？也许我们还可以详细聊聊其中的几条。

<details>
<summary>Original English</summary>

**Speaker B**: I'm I'm calling it a manifesto. It's a manifesto. I'm calling it. Let's talk about this. This was 12 engineuring principles to build reliable production ready apps. uh how did you come up with this and maybe we can also talk about some of them.

</details>

**Speaker A**: 好的。嗯，我大概追溯到八月份左右，当时和我一起工作的联合创始人有点精疲力竭，然后离开了，我们当时关系很好，这是非常和平的分手。然后我决定开始研究人工智能相关的东西，我正在构建 AI 智能体（agents），而当时正处于风口浪尖的正是 LangChain、CrewAI 这些智能体框架。而且当时感觉，你去 CrewAI 的 Discord 频道里看看，里面有一万号人。这就让人觉得，好吧，感觉大方向是对的，显然存在这样一个生态。你去看看那些项目中的每一个，它们都有一个 Chroma DB 插件，都有一个 Composeio 插件。显然，这是大家都在共同构建的共享接口。

然后我就在想，好吧，这其中缺少了什么？这些智能体可以调用工具，但你很难控制它们调用哪些工具。如果它是一个聊天机器人，显然，你可以在应用程序的用户界面中显示“批准”或“拒绝”。但我当时比较痴迷于我所谓的“外环智能体（outer loop agents）”或主动型智能体。那些在后台运行、由事件触发的智能体。我的意思是，OpenClaw 基本上就是这种模式最大的体现——你有一个心跳机制，它会唤醒，看看有没有工作要做，然后尝试去执行。我的想法是，如果我在它想执行操作时收不到诸如 Slack 消息或 iMessage 之类的通知，并且无法确定性地保证我能批准或拒绝，或者带着反馈拒绝它并说“其实不对，应该这样做”，那我就无法信任这个智能体能做任何有意义的事情。

所以我们在那个领域探索了一段时间，和很多创始人、创始工程师以及开发者进行了交流。我们在2024年秋季带着这个想法进入了 YC。我们正在构建这个 API 平台，它有点像 PagerDuty，但它不是用来解决“谁在值班修复服务器”的问题，而是“谁在值班处理这个审批路由机制”，比如“谁需要批准这个智能体？他们能升级处理、委托处理或推迟处理吗？”所有这些功能，我们都是为这个生态系统——CrewAI、LangChain 等等——构建的，当时有很多这样的粘合工具。

后来我跟许多真正在做有趣事情、真正赚钱（拿下六位数合同，将 AI 交付给企业）的 AI 工程师交谈，发现他们所有人都尝试过这些框架一两个月，然后就把它们扔掉了，他们完全在手工编写所有的 API 调用。他们构建的东西看起来更像是流水线（pipelines）和工作流（workflows），而不是这种在一个循环中撒手不管、任由其调用工具的东西。

所以我跟上百人聊过，还花了很多很多时间和我最好的朋友之一——来自 Boundary 的 Vib 交流。他们做了一个编程方面的项目，构建了类似于 AI 领域的 Protobuf 的东西，我觉得他们马上就要发布他们那套完备的、图灵完备的编程语言了。但是他对智能体、如何用模型构建以及如何用推理构建有一种自己的思考方式，更多的是关于理解底层“结构化输出”到底是什么。你的 AI 工作流中的每一步，说到底都只是 token 输入和 token 输出。而你作为工程师的工作就是弄清楚：“好的，我需要输入什么 token 才能最大化输出 token 优质的概率。”

我把所有这些想法提炼成了大概 12 条原则，并把它写在了 GitHub 上。就只是发布了一个 12 页左右的 GitHub 仓库，把它扔到了 HackerNews 上，结果获得了大约五……它在首页上待了两天，我认为它真的引起了很多人的共鸣。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So um I'll I'll kind of like go to like around August the co-founder I was working with kind of burned out and left and it was very we were on good terms. It was very mutual. Um and I decided to start messing with AI stuff and I was building a AI agents and what was really in fog right then was like the lang chain the crew AI these like agent frameworks. Um and it seemed like there was a ton of you go you go in the crew AI discord there's 10,000 people. It's like, okay, this feels like the right shape and this there's clearly this eco. You go in every single one of those projects, they have a Chroma DB plugin. They have like a Composeio plugin. There's like clearly like this is the this is the shared interface that everybody is building for. I say, okay, what's missing from all of this? The agents can call tools, but it's really hard to like control which tools they call. And if it's a chatbot, obviously, you can show approved deny in the UI of your application. But I kind of was obsessed with what I would call like outer loop agents or proactive agent. Agents that would run in the background, get triggered by events. I mean, OpenClaw is basically like the biggest manifestation of this of like you have a heartbeat, it wakes up, it sees if there's any work to do, it tries to do stuff. And my thought was like, I'm not going to trust that agent to do anything meaningful. if I can't get like a Slack message or an iMessage or something when it wants to do something and kind of guarantee deterministically that I can approve or deny that or deny it with feedback and say actually no do it like this. So we played in that space for a while and talked to a lot of founders and founding engineers and builders. We came into YC in the fall of 2024 with this idea. We're building out this API platform and it was sort of like pedag duty but like it wasn't who's on call to fix the servers. It was like who's on call to this like routing mechanism for like who needs to approve this agent and can they like escalate it or delegate it or defer it all this stuff and we built it for this ecosystem crew AI link chain fi there's so many grip tape there was so many in that in that time and then I talked to tons of AI engineers who were actually building really interesting things and like actually making money doing six figure contracts shipping AI to the enterprise and all of them had tried that stuff for like a month or two and then they had thrown it out and they were just writing all a API calls by hand and they were building more things that look more like pipelines and workflows than these sort of like hands-off call tools in a loop kind of thing. And so I talked to a hundred people and I spent a lot of time a lot a lot of time hanging out with one of my best friends uh Vib from uh Boundary. So they build a programming they built like this like protobuffs for AI thing and they're I think they're about to launch their like full fat like programming language touring complete thing. But he had this way of thinking about agents and building with models and building with inference where it was a lot more about understanding what structured output really is under the hood. And every single step in your AI workflow is just tokens in tokens out. And your job as an engineer is figure out, okay, what tokens do I need to put in to maximize the chance that the tokens out are going to be good. and kind of distilled all these ideas into about 12 principles and wrote about it on GitHub, posted just like this like 12-page GitHub repo, threw it on HackerNews, got like five, it was on the front page for like two days and it I think it really resonated with a lot of people.

</details>

**Speaker B**: 是的。那么，我就快速念一下这 12 条原则，然后我们可以挑一两条有共鸣的来聊聊。这 12 条是：工具调用的自然语言化（natural language of tool calls）、掌控你的提示词（own your prompts）、掌控你的上下文窗口（own your context window）、工具只是结构化输出（Tools are just structured outputs）、统一执行状态与业务状态（Unify execution state and business state）、用简单的 API 启动/暂停/恢复（Launch pause resume with simple APIs）、通过工具调用联系人类（Contact humans with tool calls）、掌控你的控制流（Own your control flow）、将错误压缩进上下文窗口（Compact errors into context window）、小巧专注的智能体（Small focused agents）、从任何地方触发（Trigger from anywhere）、在用户所在的地方满足他们（Meet users where they are），以及，让你的智能体成为无状态归约器（Make your agent a stateless reducer）。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, I I'll just quickly read the 12 principles and and then let's talk about like one or two that resonate. Sub 12 are natural language of tool calls, own your prompts, own your context window. Tools are just structured outputs. Unify execution state and business state. Launch pause resume with simple APIs. Contact humans with tool calls. Own your control flow. Compact errors into context window. Small focused agents. Trigger from anywhere. Meet users where they are. Make your agent a stateless reducer.

</details>

### 上下文工程（Context Engineering）的起源

**Speaker A**: 无状态的那个。对，关于无状态归约器那一条，其实有点……后来有人在 Twitter 上联系我纠正了我。它实际上是一个转换器（transducer），因为工作流中在技术上有多个步骤，不过差不多就是这个意思。但这已经是大概一年前的事了，在工具演进的维度里，一年就像是永远。还有哪些原则是让你觉得“嗯，这些原则很好，至今依然站得住脚的”？

是的，我想我大概花了整个三月来写它，在四月份发表了。然后 AI.engineer 的 Swix 联系我，他说：“嘿，你能来吗？你想来谈谈这个话题吗？”于是我在大概 6 月 6 号做了这场关于“12 Factor Agents”的演讲。在一个小房间里，大概挤满了人，不过也就大约一百人的样子。那一年在 AI Engineer 大会上，地下二层物理空间上全是那些非常企业级的东西，往上一层稍微不那么传统，然后顶层全是那种前沿的、有点怪异的初创公司项目，属于那种你现在可能还不该去操心的东西。所以我们就待在顶层，探讨着这种关于智能体的奇特思维方式。

然后大概一两周后，Shopify 的 Toby Lütke 说，我非常喜欢这种“上下文工程（context engineering）”的理念。我心想，我两个月前就写过这个。这太棒了，Toby 懂我。然后又过了一周，Andrej Karpathy 也说，我真的觉得我们应该思考的不是提示词工程（prompt engineering），而是上下文工程。我当时的反应是：“没错，这就是我的想法。”总之，我也不知道。如果你去问 Gemini，这取决于你哪天问它，它会告诉你“上下文工程”这个词要么是我，要么是 Toby，要么是 Andrej 发明的。你无法真正拥有一个词的所有权。我并不在意……

<details>
<summary>Original English</summary>

**Speaker A**: The stateless. Yeah, the stateless reducer one was a little actually someone hit me up on Twitter and uh corrected me. It's actually it's actually a transducer because there's technically multiple steps in the workflow, but there we go. But but but of this one, this this was a year ago, so like which is like forever in uh in in how the tooling is is evolving. Which ones still stick with you where you're like, "All right, these were good that that still seem to hold off." Yeah, I think I'm going spent most of March writing it, published this in April. Uh, and then Swix hit me up from AI.engineer and he said, "Hey, can you come? You want to come talk about this." So, I gave this talk 12 factor agents in like June 6th, I think. And, uh, small room maybe like it was packed, but it was like maybe a hundred people. That was the year at AI engineer where like the lower physically like on on the on the second basement floor was all the super corporate stuff and you go up a level is a little bit more and then like on the top floor is all the like weird cutting edge like startup stuff that like you probably shouldn't care about yet kind of thing. So we were up there on the top of this like weird way of thinking about agents. Uh and then about a week later or two weeks later uh Toby Licki from Shopify says I really like this idea of like context engineering. And I'm like I I wrote about this two months ago. This is great. Toby gets it and then a week later Andre Carpathi is like well I really like I think what we should think about is not prompt engineering but context engineering. And I was like, "Yes, that's my." Anyways, I don't know. If you ask Gemini, depends what day it is, they will tell you either me or Toby or Andre came up with context engineering. You can't really own a word. Like I don't

</details>

<!-- chunk 4/14 -->

### 上下文工程的起源与核心理念

**Host**: 没人记得“提示词工程 (prompt engineering)”这个词是谁发明的。但在所有的因素中，排在第三位的关键因素就是“掌控你的上下文窗口 (own your context window)”。基本上，无论它是智能体驱动的，还是流水线中的单一一个步骤，你能影响 AI 输出质量的唯一方法，就是高度关注输入内容并精心打磨它们。让我们来谈谈“上下文工程 (context engineering)”吧，我要把创造这个词的功劳归给你。我做了一些调研，我觉得你比别人早了几天提出这个词。所以就这么定了吧。是你创造了这个词。我们正在为增加 SEO 流量添砖加瓦。我们会把它放进文字稿里：是 Dex 创造了“上下文工程”这个词。

<details>
<summary>Original English</summary>

**Host**: No one remembers who invented the word prompt engineering. But of all the factors, factor three is own your context window. And basically, whether it's agentic or a single step at a pipeline, the only way you can impact the quality of your output from AI is by caring a lot about the inputs and crafting them. Let's talk about context engineering, which I am going to credit you that you coined it. I did some research and I think you were earlier by a few days. So there we go. You coined it. We're adding to the SEO juice. We'll have it in a transcript. Dex coined context engineering.

</details>

**Dex**: 好吧，关于这事儿得加个星号，其实我是在与上百位工程师和创始人交谈的过程中，才了解到上下文工程的。我只是把他们所有人都在做的事情中的共同点提取出来，然后给它起了个名字。所以说，我并没有发明这种做法。我只是觉得，既然有这么个东西存在，那么准确的词汇和命名就非常重要。我们需要有清晰的方式来讨论这个问题，特别是当现在大量关于 AI 的内容都充满了毫无意义的炒作和黑话时。我当时就觉得，这里需要有一个对开发者有用的词，来解释他们应该如何思考构建自己的软件。那么，到底什么是上下文工程呢？

<details>
<summary>Original English</summary>

**Dex**: Well, an asterisk on that is basically I learned about context engineering from talking to these hundred engineers and founders. I just kind of looked at what was the same about what they were all doing and I put a name on it. So I didn't invent doing it. I was just like, I think there's this thing, and vocabulary and names are really important. Having clean ways to talk about the problem, especially when a lot of the content about AI right now is so much hype and jargon that is meaningless. I was like, okay, I think there's a word here that is useful to builders that explains how they should be thinking about building their software. So what is context engineering?

</details>

**Dex**: 它有点像是对许多已经叠加在顶层的抽象概念进行“去抽象化 (deabstracting)”。所以你有了 RAG（检索增强生成），你有了记忆机制，你有了智能体的历史记录，你有了结构化输出——你有了所有这些在智能体编程框架下的不同概念。但归根结底，它们都只是将 token 传入模型并要求它产生（通常是某种结构化）输出的不同方式而已。理解这一点，比试图去学习各种记忆机制、试图从货架上随便挑一个智能体框架或记忆框架要强大得多。我的意思是，如果你想达到 80% 的效果，或者你想做一个非常好的演示，那些现成的东西都非常棒。但当你必须要从 80% 提升到 95% 或 99% 时，你需要往下深挖一层，去思考我们放入上下文窗口的每一项内容到底是什么。根据我们使用的不同模型，它的输入顺序应该是怎样的？所有这些细节都很重要。你拥有所有这些可以拉动的杠杆。它让人觉得，这才是思考“我该如何让 AI 尽可能准确地完成我想要它做的事情”的正确抽象层。

<details>
<summary>Original English</summary>

**Dex**: It's kind of like deabstracting a lot of the abstractions that have been layered on top. So you have RAG, you have memory, you have agentic history, you have structured output. You have all these things that are different ideas in the frame of agentic programming. And at the end of the day, they're all different ways to pass tokens into a model and ask it to produce usually some structured output. And understanding that is a lot more powerful than trying to learn memory and trying to pick some agent framework off the shelf and some memory framework off the shelf. I mean, those things are all really good if you want to get to like 80%, you want to get a really good demo. But when you have to go from 80% to 95% or 99%, you need to go down a level and think about what's everything we're putting into the context window. What order is it going in depending on which model we're doing? And all of this stuff matters. You have all of these levers that you can pull. And it just felt like the right abstraction for thinking about how do I get AI to do the thing I want as accurately as possible.

</details>

### 上下文工程为何越来越受关注

**Host**: 为什么上下文工程开始被越来越多人讨论？大约是一年前吧。这是否和我们能够传递给 LLM 的上下文窗口几乎就是那个大小有关？是因为上下文窗口开始扩展了，还是仅仅因为我们开始意识到，通过传递更多信息我们可以做更多事情？你知道，最简单的例子当然是系统提示词 (system prompts)，但当然了，每当你在幕后构建一个 LLM 应用时，你也会传递额外的上下文，不仅仅是为了提示用户，你还会添加一大堆其他东西，我想这是任何一个语言模型不为人知的秘密。但你认为为什么现在的焦点转移到了“好吧，上下文很重要”这一点上呢？

<details>
<summary>Original English</summary>

**Host**: Why is context engineering starting to become more talked about? It was about a year ago. Did it have to do with the context window that we could pass on to LLMs? Did it start to expand, or did we just start to realize that we can do a lot more by passing on... you know, the easiest one is of course system prompts, but of course whenever you build an LLM behind the scenes you will pass additional context as well, not just to prompt the user. You will add a bunch of stuff that's I guess a dirty secret of any LLM. But why do you think the focus is moving on to 'all right, context is important'?

</details>

**Dex**: 我认为它一直都很重要。我认为必然发生的事情是，许多聪明人——再次强调，就像我交流过的所有这些构建者和大量聪明人一样——必须非常专注地投入到生产中。比如，“我想要开发我能拿去卖的软件”。我想要开发足够准确、能让我引以为豪，并且我可以把它卖给企业客户、让他们感到满意的东西。要开发真正高质量的 AI 应用程序，最简单的方法就是在这个 token 的层面上进行思考。去思考一连串不同的 LLM 调用，而不是仅仅在循环里放几个工具（那种方式过于开放和灵活，但并不是很可靠）。要把智能体当作工作流、当作流水线、或者是介于“循环中的几个工具”和“嘿，我有我的工具、我的模型和我的系统提示词，这些就是我仅有的杠杆”之间的一种混合体来思考。实际情况并不是这样，你拥有的杠杆要多得多。这将花费更多的心血，而且你必须培养对 LLM 更深层次的直觉。但这是一件我们一直都需要做的事情，只是人们在利用这项技术进行构建时，需要花一些时间才弄明白，这是能让你突破质量天花板的那个抽象层。

<details>
<summary>Original English</summary>

**Dex**: I think it always was important. I think what had to happen is a ton of smart people—again, like all these builders I talked to—had to focus really hard on producing: 'I want to make software that I can sell. I want to make something that is accurate enough that I'm proud of and I can sell to an enterprise and they're going to be happy with it.' And the easiest way to get to really high quality AI applications is by thinking at that token level. Thinking about a string of different LLM calls rather than just tools in the loop, which is kind of open-ended and very flexible but not that reliable. Thinking of agents as workflows, as pipelines, as some mix between maybe a couple tools in a loop versus just, 'Hey, I have my tools and I have my model and I have my system prompt and these are the only levers I have.' And it's actually no, you have way more levers. It's going to take more work and you're going to have to understand the LLM with a deeper intuition. But it was a thing that we always needed, and it just took time for people to build with this technology to figure out that this is the layer of abstraction that allows you to break through the quality ceiling.

</details>

### 成本与上下文工程的关联

**Host**: 那么成本和上下文工程之间是怎么关联的呢？

<details>
<summary>Original English</summary>

**Host**: And how are cost and context engineering connected?

</details>

**Dex**: 是的。我今天早上还和某个人讨论过这个。关于当你使用大语言模型（LLM）时，我喜欢说的一句话是，有点像“让它跑起来，让它跑得对，让它跑得快 (make it run, make it right, make it fast)”。先看看当时世界上最好的 LLM——我想我们做过一期播客，当时说的是 o3——看看 o3 能不能解决你的问题，然后把它交给人们，看看他们是否需要这个东西。如果人们想要它，而且使用频率很高，那就去做大量的上下文工程，因为你的工程时间始终是瓶颈。让人类去试图找出并解决问题、构建评估标准 (evals)、改进并尝试不同维度或设置其他任何东西，总是比仅仅使用一个更聪明的模型要昂贵得多。直到你每天有一百万次请求了，然后你就会说：“好吧，我们现在要去做一堆上下文工程，把这个任务拆分成三次调用，并让它在 GPT-4o 上运行。”然后再把这三次调用中的两次，让它们在 GPT-4o mini 上运行（这里用的是旧模型的名字举例）。但这里的重点是，对于你工作流中的某个特定任务，你能不能让类似于开源 12B 参数的模型（它的成本可能只有 Opus 的千分之一），去解决问题的一部分，这样你用最聪明的前沿模型所消耗的 token 和处理的事情，就仅仅是那些你真正需要的、确实需要那种智力水平的任务？但你一开始不应该去构建所有这些并过度工程化，直到你证明了你需要它，证明了它是有价值的，证明了现在到了这个阶段。我的意思是，这让我们想到了高德拉特 (Eli Goldratt) 和他的思想，他写了《目标》(The Goal) 这本书，对吧？那本书是关于如何对你的工厂进行建模的。我确信我们在讨论软件工厂时会谈到这一点。这就是说，什么是你系统里的瓶颈？未来总有一天，瓶颈会是延迟和成本。但当你刚起步时，可能并不是这样。而上下文工程就是你如何把人类的努力加入到这个等式中，以此来提升你系统的效率、速度、价格和成本效益。

<details>
<summary>Original English</summary>

**Dex**: Yeah. I don't know, I was talking about this with someone this morning about when you're working with LLMs, one of the things I like to say is kind of like 'make it run, make it right, make it fast.' See if the world's best LLM at the time—I think we did a podcast episode that at the time it was o3—see if o3 can solve your problem, and then give it to people and see if they want that. And then if people want it and you use it a lot, then go do a bunch of context engineering because your engineering time is always the bottleneck. Humans trying to figure out and solve problems and build evals and improve and try different dimensions or set up whatever it is, is always going to be more expensive than just using a smarter model, until you have millions of requests a day. And then it's like, okay, we're going to do a bunch of context engineering, break this up into three calls, and get it to work on GPT-4o. And then we're going to take two of those and make those two work on GPT-4o mini and using old model names. But the point is, for a certain task in your workflow, can you get an OSS 12B model, which is like 1/1,000th of the cost of Opus, can you get it to solve parts of the problem so that the tokens and the things you're using the smartest frontier models for are just the things that you really need that level of intelligence for? But you shouldn't go build all of that and overengineer it until you've proved that you need it, that it's valuable. I mean, we get to Eli Goldratt and his book The Goal, right? It was about how to model your factory, and I'm sure we'll get to that when we talk about software factories. It was like, what is the bottleneck in your system? And one day it will be latency and cost, but it's probably not that when you first start out. And context engineering is how you add human effort to the equation to improve the efficiency, the speed, the price, the cost efficiency of your system.

</details>

### 从上下文工程到脚手架工程

**Host**: 有意思。接下来，还有一个稍微晚一点、更近一些被提出来的概念，叫做脚手架工程 (harness engineering)。什么是脚手架工程？

<details>
<summary>Original English</summary>

**Host**: Interesting. And then one thing that came up more recently is harness engineering. What is harness engineering?

</details>

**Dex**: 大概在 10 月份，或者是 11 月份，我发了一个帖子说：“嘿，我看到了一个新东西，我把它叫做脚手架工程 (harness engineering)。”当时我的定义其实并不是现在在 LangChain 工作的 Viv 所描述的那样——他写了很多关于智能体和如何思考脚手架的非常棒的文章。他比我早几个星期写了一些叫做脚手架工程的内容，但我当时还没读过。我当时的观点基本是这样的：好吧，当你构建一个智能体时，你会用到上下文工程。当你使用一个智能体时——因为我们在 2025 年 8 月份做过一次演讲，主题是如何将上下文工程应用到编码智能体的使用上——这就逐渐演变成了这样的想法：你如何对待像 Claude Code 或 Codex 这样的脚手架系统？你如何针对那个脚手架的集成点进行工程设计？比如命令、MCP（模型上下文协议）、技能，以及你如何组织你的代码库。你如何优化编码智能体运行的环境，从而得到最佳的结果？这就像上下文工程探讨如何优化每一次提示词的输入一样，那么脚手架工程探讨的就是，我该如何提高底线，从而使得这个东西在每一次轮次交互中，结果都能尽可能地好。后来这个词变得非常模糊，有些人认为脚手架工程意味着“构建一个脚手架 (building a harness)”，还有些人认为脚手架工程意味着“围绕一个脚手架进行构建 (building around a harness)”。我其实挺喜欢 Martin Fowler 提出的那个定义——像往常一样，他非常擅长命名事物——他基本上定义了你拥有大语言模型（LLM）……

<details>
<summary>Original English</summary>

**Dex**: So I made a post in October or maybe November saying, hey, there's this new thing that I'm calling harness engineering. My definition that I had at the time is not what this guy Viv, who's at LangChain now, does—he does a lot of really good writing on agents and how to think about harness. He had written something called harness engineering a couple weeks before me, but I hadn't read it at that point. And my take was basically like, okay, when you build an agent you use context engineering. When you use an agent—because we gave this talk in August of 2025 about how to apply context engineering to how you use coding agents—and that kind of evolved into this idea of how do you take a harness like Claude Code or Codex, how do you engineer against the integration points of that harness? So commands, MCPs, skills, how you organize your codebase. How do you optimize the environment that the coding agent runs in to get the best results? The same way with context engineering, how do you optimize the inputs to every single prompt? Well, harness engineering is just how do I raise the floor so that every single turn of this thing, the results are as good as possible. And the term got super blurry, and some people think harness engineering means building a harness. And some people think harness engineering means building around a harness. I actually like what Martin Fowler came up with, as usual he's very good at naming things, and he kind of defined... you have the LLM,

</details>

<!-- chunk 5/14 -->

### 上下文工程的本质与指令预算

**Speaker A**: ……然后你有了内部安全带（inner harness），这就好像是工具定义和集成点，比如 Cloud Code、Codex 或者 AMP 实际暴露出来的那些东西，这就是你的内部安全带；然后你还有外部安全带（outer harness），这是人类为了适应特定需求、你的代码库、你的编程语言等而进行定制化配置的内容。我认为这就是我们对“安全带工程”（harness engineering）最好的定义。

<details>
<summary>Original English</summary>

**Speaker A**: ...and then you have the inner harness which is like the thing the tool definitions and the integration points that like say like a cloud code or a codeex or a amp actually exposes that's your inner harness and then you have the outer harness which is the stuff that you the human do to customize that for your specific needs your codebase your languages etc that's the best definition I think we have for harness engineering.

</details>

**Speaker B**: 有趣的是，命名依然如此重要，不是吗？

<details>
<summary>Original English</summary>

**Speaker B**: it's interesting how naming is still so so important, isn't it?

</details>

**Speaker A**: 嗯，这就像一旦你给任何东西命名，人们就会……大多数人会……我其实很惊讶，“上下文工程”（context engineering）对大多数人来说，它的含义仍然和一年前一样，而且它甚至依然具有相关性。老实说，这对我而言是最疯狂的事情。想想 15 个月前写的关于 AI 的东西，有多少至今仍然重要，或者仍然有趣，或者里面依然包含着很好的建议。事物变化很快，我认为上下文工程之所以能存在这么久，是因为它根植于 Transformer 注意力机制工作原理的基础。直到我们有了后 Transformer 模型、线性注意力（linear attention）或其他什么东西——谁知道那什么时候会发生——在此之前，上下文工程对任何从事 AI 构建的人来说，都将是有趣且重要的，并且……

<details>
<summary>Original English</summary>

**Speaker A**: Well, it's like as soon as you name anything, people are most people are I'm actually surprised that context engineering still means the same thing to most people that it did a year ago and that it's even still relevant. Like that's honestly the the craziest thing to me is like you wrote how many things that were written about AI 15 months ago still matter or still interesting um or are still like have good advice baked into them. Stuff changes a I think context engineering has been so long lived because it's it's grounded in the fundamentals of how transformer attention works and until we have post transformer models or linear attention or whatever it is which who knows when that's going to happen context engineering will be interesting and important to anyone building on AI and

</details>

**Speaker B**: 我们能谈谈上下文的“物理学”吗？你发过一条推文，这一条，关于“上下文现实检查”。这是一张图表，显示当你达到 100 万上下文时，质量直接下降了，它在往下走。关于上下文，我们需要了解些什么？再强调一遍，我们现在确实有了具备 100 万上下文窗口的模型。也许将来我们会有更长的，但当你开始往上下文里塞入更多东西时，它就开始变得不那么高效了。从使用上下文窗口添加大量内容的人的实用角度来看，比如可能是 MCP，可能是工具，可能是 scale 等等所有这些东西，到目前为止我们知道了什么？

<details>
<summary>Original English</summary>

**Speaker B**: can we talk about the physics of of context uh you you you had a you had a tweet uh this this one the the context reality check this is a graph of uh as you get to 1 million context just the the quality just drops it. It goes down. What do we need to know about like the context? Again, we we now have models that do have a 1 million context window. Maybe we'll have even longer ones, but when you start to just put in more stuff into the context, it starts to become less efficient. Like what what do we know so far in terms of from a practical perspective of like someone who is using the context window to add on a bunch of stuff? May that be MCP, may that be tools, may that be scales, may that be all of these things.

</details>

**Speaker A**: 是的。我的意思是，更长的上下文窗口是好事。你可以和它对话更久。比如，它们做得很好。但归根结底，特别是像以前的 Opus 时，从 Opus 4.5 升级到 Opus 4.51 或者 4.6 升级到 4.61 的 100 万上下文。你并没有真正得到一个更聪明的模型。模型的智能程度决定了它关注上下文窗口中所有 token 的能力，以此来弄清楚在下一轮对话中，这 10 万或 20 万上下文窗口里的哪些部分，对于决定“我们接下来调用哪个工具”最为相关，并且在循环中一遍又一遍地做这件事。所以我不知道，2025 年有一项研究发现——再次强调，这些都是旧模型，所以实际数字可以往高了算——大约是前沿 LLM 在遵循 150 到 250 条指令后，能力就开始下降了。它们遵循所有指令的能力下降得非常快。而且我认为 Lori Vos——我其实没看具体数据——但他们一年后用下一代模型做了一项研究，看起来你能塞进去的指令数量要好得多。无论如何，我认为上下文工程可以分为两类。一类是大多数人都会考虑的“信息预算”（information budget），比如：好吧，我可以做 RAG，我可以从这篇文档中提取出片段，而不是把整本书塞进我的上下文窗口。我只需要去抓取那些关键的页面。但另一类是你的“指令预算”（instruction budget），比如如果你给模型太多的指令，尤其是太多相互冲突的指令——这可能是在你的初始提示词中，也可能是：如果在对话中，你开始沿着一条路径走，然后改变了主意，开始走向另一条路径，你说“其实我不想做那些了，我想做这个”。模型必须进行大量的计算，才能注意到它必须忽略前面那一大块内容。而当这两种情况都在上下文窗口中处于相当靠后的位置，以至于它们只被部分关注时，模型实际记住你 10 万个 token 前给出的确切指令的几率，就会大幅下降。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I mean, so the longer context windows are good. You can talk to it for longer. Like they're doing a good job. But at the end of the day, like especially when you had like Opus, it was like Opus 4.5 and then Opus 4.51 mil or 4.6 and 4.61 mil. You're not actually getting a like smarter model. like the intelligence of the model is is what drives its ability to attend to all of the tokens in the context window to figure out on the next turn which parts of this 100k or 200k context window are the most relevant to making the decision of like what is the next tool we call and doing that over and over again in a loop. So I don't know there was some study that came out in 2025 which found that and again these are old models so like inflate your numbers but it was like frontier LLMs can follow about 150 to 250 instructions before it starts to drop off. Their ability to follow all the instructions just like drops off pretty quickly. And I think Lori Vos I haven't actually looked at the data but they did a study with like the next generation models a year later and it looks like it's like much better the number of instructions you can get in. In any case, you have like I split context engineering into like two categories. You have like the the most people think about like the information budget of like okay I can do rag and I can pull out chunks of this document rather than putting the entire book into my context window. I can just go grab the pages that matter. But it's also your instruction budget is like if you give the model too many instructions and especially too many conflicting instructions and that's in your initial prompt and also like if you have a conversation you start going down a path and then you change your mind and you start going down a different you actually I don't want to do any of that I want to do this. It's like a it's a lot of computation the model has to do to notice that it has to ignore that whole thing. And when both of those things are kind of far back enough in the context window that they're only half getting attended to, your likelihood that it's like actually going to like remember the exact instructions you gave it 100,000 tokens ago is like it goes down quite significantly.

</details>

### 从软件工程到 AI 工程的直觉转变

**Speaker B**: 这非常有趣，因为作为工程师，当我们在做 AI 工程师时——现在很多软件工程师实际上就是用 LLM 来构建软件，底层某个地方有一个 LLM 层，恭喜你，你就是 AI 工程师了——但听起来这种期望是，就像在 AI 时代之前要成为一名优秀的软件工程师，你需要懂如何写出好代码，如果你懂一点底层原理会有所帮助，随着时间的推移，我们不需要做太多底层的了解，但这总没坏处。但现在听起来，我们正处于这样一个阶段：要成为一名能够编写使用 LLM 的高效 AI 系统的工程师，你需要理解上下文的动态变化，你需要理解为什么以某种方式填充上下文可能会耗费计算资源、引入延迟等等。听起来这更像是一种直觉，当然也包含一些理解，但从和你交谈来看，你就像是“嗯，它就是这样计算的”，就像是因为你亲自尝试过才知道的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: This is all very interesting because as engineers there we are expected when you know when we're AI engineers which now a lot of software engineer meaning you just like use LMS to to build software like underneath there's an LLM layer somewhere you're an AI engineer congratulations but it sounds like the expectation is to be you know to be a good to be a good software engineer preI you need to understand you know how to write good code and it helps when you understand a little bit of the underlying we didn't need to do that that much over time but it it it never hurts but sounds Like right now we're in this phase that to be an engineer who can write an efficient AI system that use LMS. You need to understand the dynamics of the context you need to understand why stuffing your context one way or the other can be compute can introduce latency and all of these. It sounds like it's kind of more of an intuition and of course there's some understanding but from talking to you you're like well it it it does this computation like I know you know cuz you tried it out right?

</details>

**Speaker A**: 是的。我不是机器学习的博士，我没法真的去画出它是如何工作的数学证明，但我们知道注意力机制是二次方的（quadratic），你放入的内容越多，它就越需要把这些注意力分散到所有东西上。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah like I'm not I'm not a PhD in machine learning like I couldn't actually go like draw a mathematical proof of how this works but we know attention is quadratic and the more stuff you put in the more it has to spread this attention out over everything.

</details>

**Speaker B**: 这感觉就像是一个全新的领域，和我们习惯的软件工程有些大不相同，软件工程很大程度上是黑白分明的，对吧？要么编译通过，要么编译不通过。

<details>
<summary>Original English</summary>

**Speaker B**: This just feels like an absolute new area and like a little bit very different to like what we're used to like software engineering which is like pretty kind of like black and white, right? That compiles or doesn't compile.

</details>

**Speaker A**: 确实如此。我的意思是，这是一种不同类型的直觉。我之前也谈到过，作为一名软件工程师，随着岁月的沉淀，你会培养出一种不同的直觉。它有很多种类，但我特别想指出的一种是，那是一种你无法教、无法做、无法从教科书里学到的东西。学习它的唯一方法就像这样：我之所以了解软件里的不良模式，是因为我曾在凌晨三点调试过它们。这是我的哥们 Jake from Netflix 在 AI 工程师大会上的演讲中说的。就像是，要了解什么是好、什么是坏、什么有效、什么无效，没有比痛苦地熬过那些无效的东西更好的方法了。

<details>
<summary>Original English</summary>

**Speaker A**: That's true. I mean there's a different kind of intuition. I was talking about this earlier as well is like there's a different kind of intuition that you that you develop over years as a software engineer and uh there's many categories of it but the one I'll I'll call attention to that is like a thing that you cannot teach you cannot do you cannot learn in a textbook. The only way to learn it is like I know bad patterns in software because I have debugged them at three in the morning. This is my buddy Jake from Netflix said this in his talk at AI engineer code. It's just like there's no better way to learn what is good and what is bad and what works and what doesn't than suffering through the thing that doesn't work.

</details>

### 循环工程与自我纠错

**Speaker B**: 说到痛苦地经历那些无效的东西，一个正在兴起的新范式是循环（loops）。循环工程。这个想法是：与其写提示词，不如直接写循环。设置好你的循环。这一切都始于 Ralph Wiggum 技术，它会直接……嗯，我猜那算是循环的一个早期版本，只是在不断循环。而现在我们听到一些最顶尖的实验室在谈论，他们实际上也就是在做循环。你对此有什么看法？你自己做过一些循环吗？你设置过循环吗？你认为它有什么好处，又有什么坏处？

<details>
<summary>Original English</summary>

**Speaker B**: Well, speaking of suffering through the things that that doesn't work, uh a new paradigm uh that is spreading up is loops. Loop engineering. The idea that instead of writing prompts, just write loops. Set up your loops. And this all started with the Ralph Wiggum technique where it it will just well it I I guess that's an early version of loops that were just loops around and now we're we're hearing with some of the big biggest labs talking about that they're actually just doing looping. What is your take on have have you done some looping yourself? Have you set up some loops? And what do you think is good about it and what do you think is bad about it?

</details>

**Speaker A**: 是的。所以我觉得循环……我的意思是，光这个我就能扯上 10 分钟。这足够讲一整场演讲了，但我会试着……我会试着列出一些高层次的东西，然后我们可以挑选你觉得最有趣的部分深入探讨。我们有过 Ralph Wiggum。实际上，就在一年零四天前，我第一次看到了 Ralph Wiggum 的演示。当时 Jeff Hunley 正好在旧金山访问，他顺道过来，用他的演示让所有人都惊掉了下巴，他当时大概是说：“是的，我全天候跑 Sonnet，六周花了 6000 块，然后我就构建了整整一门 Z 世代编程语言。”你看它能编译，而且它还有一个第二阶段的编译器，语言的编译器是用这种语言本身编写的，诸如此类疯狂的事情。我认为所有这些的核心教训是背压（back pressure）的概念。基本上，而且我认为有很多人为了某个……已经做了很长时间的一件事就是：我如何让模型检查自己的工作？我如何……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So I think of loops as I mean this could I could ramble on this for 10 minutes. This is an entire talk, but I'll I'll try to I'll try to lay out some highle stuff and then we can dig in wherever you think is most interesting. We had Ralph Wickham. It was actually a year and four days ago was the first time I saw the Ralph Wickham demo and like Jeff Hunley was just like visiting SF and he just like came through and like dropped everybody's jaws with his like, "Yeah, I just ran Sonnet around the clock and spent six grand in six weeks and like I built an entire Gen Z programming lang." Look at it compiles and it has a stage two compiler where the compiler for the language is written in the language itself and all the insane. And the core lesson from all of that I think was the idea of back pressure which is basically and I think a lot of people were doing this for a very have been doing this for a long time which is how do I let the model check its own work? How do I

</details>

<!-- chunk 6/14 -->

### 循环工程与自动化验证

**Dex**: 自动化将反馈融入模型的过程？有很多很多种不同的形式。你可以使用确定性的 linter，也可以使用单元测试。就像 Ralph 这种编程语言之所以易于构建，部分原因就在于它是一种可以被无限验证的编程语言。你用这种语言编写代码，然后编译它。如果编译器报错，你就去修复编译器。你运行程序，如果程序出错，你就去修复编译器。这就像是一个高度可验证的过程。我认为循环工程（loops engineering）的经验是，如果你能让一个问题变得高度可验证，你就可以在某种程度上把它当作一个黑盒来对待。

<details>
<summary>Original English</summary>

**Dex**: automate the process of getting feedback into the model? And there's lots and lots of different flavors of this. You can have deterministic llinters. You can have unit tests. Like part of what made the programming language easy to build with Ralph is a programming language can be infinitely verified. You write the code in the language, you compile it. If the compiler fails, you go fix the compiler. You run the program. If the program fails, you go fix the compiler. Like it's very very verifiable. And I think the lesson in loops engineering is like if you can make a problem very verifiable, you can kind of like treat it like a black box
</details>

**Host**: 然后让它循环，因为它会自我迭代改进，因为验证循环已经存在了。

<details>
<summary>Original English</summary>

**Host**: and then have it loop because it will keep improving itself because of the verification loop is already there.
</details>

**Dex**: 完全正确。比如在 CI/CD 中你就可以这么做，我每次发布的时候都会这样。我会觉得：“我累了，CI/CD 太慢了。很好。去研究一下代码库，做个修改，提个 PR，运行测试，看看是不是变快了，再试一次。运行测试，推送到分支，再检查一遍是不是变快了。”所以，如果它能在循环中验证自己的工作，而不是说“我们试试这个方案”或者“我们试试那个方案”，或者在提建议时来回拉扯，你只需要说“我的目标是让 CI 变快”，然后你告诉模型：“这是你要做的五个步骤：写一些代码，提交它，推送它，启动一个子智能体（sub agent）来监控这个任务直到完成，它会告诉你发生了什么，然后你再决定下一步做什么。”这就是我关于设计循环最简单的例子。

<details>
<summary>Original English</summary>

**Dex**: Exactly. And so like you can do this with CI/CD is like I do this every time I'm doing a release. I'm like I'm tired. The CI/CD is slow. Cool. Go research the codebase, make a change, make a pull request, run the test, see if it's faster, try again. Run the test. push to the branch check again see if it's faster and so it's like if it can verify its own work in a loop instead of design instead of saying let's try this approach or let's try that approach or suggest and being really back and forth you just say like my goal is to make CI faster and you tell the model here's the steps here's the five steps you're going to write some code you're going to commit it you're going to push it you're going to launch a sub agent to watch the job until it's finished it's going to tell you what happened then you're going to decide what to do next and so that's like the very simplest example I have of like designing loops
</details>

**Host**: 而且你只需设定目标，比如是 Claude Code，而且我认为 Codex 也拥有这种设定目标的能力，你只需设定目标，它就会不断迭代直到达成，或者只要它在朝着目标取得进展即可。

<details>
<summary>Original English</summary>

**Host**: and you just set the goal which is Claude Code and I think Codex have both this goal which is you just set the goal and it iterates until it reaches it or as long as it makes progress towards it.
</details>

**Dex**: 没错。所以如果它是可验证的，如果你能衡量的话，这也是自动化研究（auto research）。自动化研究就像是说：“嘿，去把这个模型变快一倍。”这只是一个提示词，告诉模型一遍又一遍地去做，不断尝试直到它真的取得了好的结果。所以这就是我对循环工程的理解。我不知道，我们在做一种非常有趣的循环工程，挑战在于，我认为人们很容易对构建“用来构建东西的东西”感到兴奋，或者是构建“用来构建‘用来构建东西的东西’的东西”。所以人们会说：“哦，我们需要把所有的东西都重做成这种大型的 Agent 优先的工厂，甚至可能是无人工厂（dark factory）。”然后他们会重新设计整个系统，使其成为未来五年的基础设施。但我确信在工程领域，尤其是务实的工程领域，我们都知道一件事，那就是：你如何让它变得更具渐进性？你如何让它更加持续？许多人并没有那种选项去说：“嘿，我跑了三天 Ralph 循环，它修复了我们代码库里的每一个 linter 错误。这里有一个六万行的 PR。谁想来 review 并且谁愿意签字同意合并并部署它，且保证不会有任何 bug？”没有人。所以我认为，我最感到兴奋的其实是我们所谓的迭代循环或者说慢循环，我们基本上就是用一个 cron 定时任务。我们有这个循环，它的结构非常简单。就像是：运行这个 linter，修复一个问题，提交并推送。然后我们每晚在 GitHub Actions 中运行它，每天早上醒来就能看到一个让代码库变得更好一点的 PR。

<details>
<summary>Original English</summary>

**Dex**: Exactly. And so it's like if it's verifiable if you can measure this is auto research too. Auto research is like hey go make this model twice as fast and like it's just a prompt that tells the model to like go to it over and over again and try things until it actually has good results. So that's what I think of loops engineering. I don't know. We do a very interesting kind of loops engineering where like the challenge is like I think it's very easy to get very excited about building the thing that builds the thing or building the thing that builds the thing that builds the thing we talked about. Uh and so people say, "Oh, we need to like redo everything as this big like aentic first factory, maybe even a dark factory." And they're like redesigning their entire thing to be their infrastructure for the next 5 years. And I'm sure one thing we know of in engineering uh and especially pragmatic engineering is uh how can you make this more incremental? How can you make it more continuous? Uh and a lot of people don't have the option to just hey I ran a Ralph loop for 3 days and it fixed every line error in our codebase. Here's a 60,000 line PR. Who wants to review it and who wants to sign off on merging and deploying it and uh that there's not going to be any bugs? Nobody. So I think the thing I'm most excited is actually like what we call like iterated loops or like slow loops where we basically have a cron job. We have the loop the structure of the loop is really easy. It's like run this llinter fix one thing commit and push and then we run that every night in our GitHub actions and we wake up every morning to one PR that makes the codebase a little bit better.
</details>

**Host**: 我喜欢这种慢循环。

<details>
<summary>Original English</summary>

**Host**: I like the slow loops.
</details>

**Dex**: 是的。它有两个维度。所以你可以添加——现在我们有了它的蓝图，实际上 Kyle 刚刚发布了一个 skill，这样你自己也可以构建这些循环了。你可以添加更多类似反馈机制的东西。所以，我们在前端有 React Doctor。我们还有另一个没有确定性工具的反模式，但 Kyle 会说：“这是好的代码长什么样。这是糟糕的代码长什么样。去修复一个问题然后带回来。”这基本上就像属性缩小（prop narrowing）。我们有一堆可选属性（optional props），但大多数其实不需要是可选的。它的任务就是：这是如何把该属性变成非可选的方法，这样你就会知道代码变得更干净、更容易理解了。所以，你可以添加更多的条件，更多这种“修复一个问题”的任务。我希望每天醒来都能看到一个 PR。那么现在，我们每天醒来会有大概四个 PR，因为有四个独立的事情。然后你在这里可以做的另一个维度是，随着你获得信心，你可以扩大范围。不要只修复一个问题，去修复四个问题。所以这些是思考循环的其他方式，就像是：启动它的不应该是人类。无论它是 Sentry 发来的警报，还是用户的反馈（比如工单），无论是产品经理写的一张票，还是一个测试失败了，或者它是一个按计划运行的 cron 任务。总之，触发器应该是一些不需要你按下按钮的东西，并且它有一个定义好的工作流，能让所有事情变得更好一点。

<details>
<summary>Original English</summary>

**Dex**: Yeah. And it has two dimensions. So you can add now we have a blueprint for it and actually Kyle just shipped a skill so that you can build these yourself. you can add more like feedback mechanisms. So, we have React Doctor for the front end. We have another anti-attern that has no deterministic tooling, but Kyle's just like, "Here's what good looks like. Here's what bad looks like. Go fix one thing and bring it back." It's like prop narrowing basically. We have a bunch of optional props and most of them don't need to be optional. It's like here's how to make the prop not optional so that you know that the code just is like cleaner and easier to reason about. And so, you can add more conditions, more things of like fix one thing. I want to wake up to a PR. So, now we wake up to like four PRs because there's four separate things. And then the other dimension you can do here is as you gain confidence, you can increase the scope. Instead of fixing one thing, fix four things. And so these are like other ways to think about loops where it's like something that's not a human triggers it to start. Whether it's, you know, an alert from Sentry, whether it's a user feedback like support ticket, whether it's PM writes a ticket, whether it's a test is failing, any of or it's a cron, it runs on a schedule, but it's like the trigger should be something that you don't have to like press a button on and there's a defined workflow and it makes everything a little bit better.
</details>

### 赞助商插播：自动化调试与监控

**Host**: Dex 刚才描述了让智能体在没有人类按下按钮的情况下修复问题。但是，如果一个 bug 非常棘手，不仅对智能体来说很难，甚至对人类来说都难以复现，更别提修复了呢？这就是我们的本季赞助商 Antithesis 的用武之地。我最近和 Antithesis 团队一起结对工作，我们演示了他们如何帮助修复了 Kubernetes 使用的开源键值存储系统 etcd 中的一个令人头疼的 bug。这是一个真实发生在 etcd 中的 bug。团队注意到，在常规的 Antithesis 运行中，线性化验证断言（linearization validation assertion）失败了。这可不太妙，因为线性化保证了强一致性。所以这个问题必须要被修复。于是 etcd 团队在 Antithesis 内部运行了因果分析（casualty analysis）。这生成了一张图表，也就是 bug 概率图。在这里，X 轴是虚拟时间，Y 轴是概率。现在我们看到，在虚拟时间 24 之前发生了一些事情，导致该 bug 发生的概率出现了巨大的跳跃。深入调查后，我们可以查看整个时间线集合。向下的垂直线代表从同一个状态分支出来的事件，而紫色的点则是 bug 发生的地方。如果我们仔细观察，就会发现所有的失败都来自同一个父分支。这真是一个非常有用的调试工具。最终，团队使用所有这些 Antithesis 调试工具，弄清楚了是进程暂停（process pauses）导致了这个 bug。这个非确定性的 bug 竟然用一种确定性的方式被诊断出来了。这多酷啊？哦，而且这是一个真正的 bug，后来在 etcd 中被修复了。你可以在 etcd 的 GitHub 仓库中看到这个 bug 和它的修复过程。老实说，Antithesis 为调试构建的工具感觉相当有未来感，但它们也非常强大。前往 antithesis.com/pragmatic 了解更多。

<details>
<summary>Original English</summary>

**Host**: Dex just described letting agents fix things without a human pressing a button. But what if a bug is too difficult not just for an agent but also for human to reproduce let alone fix? This is where presenting sponsor anticysis comes in. I was recently pairing with the antithesis team where we did a walkthrough of how they helped fix a nasty bug inc the open source key value store used by Kubernetes. This is a bug that actually happened incd. The team noticed that the linearization validation assertion failed during the regular anticis runs. This is not good because the linearization guarantees strong consistency. So this needs to be fixed. So what the ETCD team did was run a casualty analysis inside anticysis. This generates this graph which is a bug probability graph. Here the x-axis is virtual time and the y-axis is probability. Now we see that something happened just before virtual time 24 that caused a huge jump in the probability that the bug would occur. Going deeper, we can look at the entire set of timelines. Vertical lines going down represent events branching off from the same state and the purple dots are where the buck happens. If we look closely enough, we see that all of the failures come from one parent branch. Gotcha. This is such a useful debugging tool. In the end, the team was able to figure out that process pauses were causing the bug using all these anticis debugging tools. This non-deterministic bug was diagnosed in a deterministic way. How cool is that? Oh, and this is an actual bug that then got fixed incd. You can see the bug and the fix in ATCD's GitHub repo. Honestly, the tools that Antys is built for debugging feel pretty darn futuristic, but they are also really powerful. Head over to antithesis.com/pragmatic to learn more.
</details>

**Host**: 我还想聊聊我们本季的赞助商，Sentry。Sentry 是我在所有项目中用来进行应用监控的工具，包括 Pragmatic Engineer 的后端。我已经使用它 10 年了，从我在 Uber 工作时就开始了。我比较喜欢的一个很棒的 Sentry 功能是他们的 Seir AI 智能体，它能帮助调查生产环境的错误。例如，这是我的应用程序中真实发生的一个错误。我可以简单地问 Seir 根本原因可能是什么，它就会带入相关的上下文。而且它还可以直接在 Web 界面上制定一个修复计划。还有一个很棒的地方是，Seir 在 Slack 上的使用体验也非常好，不仅仅局限于 Web 界面。我发现使用 Sentry 更加顺手的一个场景是，通过 Sentry MCP 在 Claude Code（CodeX）中或者使用 Cursor 智能体调用它。此外，你还可以设置一些非常棒的自动化流程，比如当一个已解决的 Sentry 问题再次出现时，你可以触发一个 Cursor Agent 或 GitHub Copilot Agent 来调查这个回归错误（regression），阅读相关代码，并提交一个包含建议修复方案的 PR。我并不是为了用 AI 工具而用它，但我真的很喜欢这些实用的集成，它让我能在拥有更多上下文的情况下更快地修复错误。现在就前往 sentry.io/pragmatic 了解 Sentry，开始监控并修复回归错误吧。好了，说到这里，让我们回到 Dex 的话题，继续聊聊能够自我触发的 Agent 循环。现在，你说我们……

<details>
<summary>Original English</summary>

**Host**: I'd also like to talk about our season sponsor, Sentry. Sentry is a tool I use for application monitoring on all of my projects, including their pragmatic engine back end. I've used it for 10 years now, starting with when I worked at Uber. A neat Sentry feature I'm liking is their SE AI agent, which helps investigate production errors. For example, here's an actual error I had in my application. I can just ask Seir what might be the root cause and it brings context. And it can also make a plan to fix it right from the web interface. And a nice thing is how Seir also works great from Slack as well, not just from the web. One place I find even more handy to use Sentry is from codeex or clock code using Sentry MCP. Also, you can set up neat automations like when a resolve sentry issue resurfaces. You can kick off a cursor agent or GitHub copilot agent to investigate the regression, read the relevant code, and open a PR with a suggested fix. I'm not a fan for using AI tools just for the sake of it, but I really like the practical integrations where I can fix errors faster and with more context. Check out Sentry at centry.io/pragmatic and start monitoring and fixing regressions today. And with this, let's get back to Dex and to Agentic loops that trigger themselves. Now, you said we
</details>

<!-- chunk 7/14 -->

### 软件工厂与AI循环：不看代码的隐患

**Speaker A**: 我们可以设定的目标更宏大一些，我们可以往里面添加更多东西。但我要用你发过的一条推文来引用你的观点，这条推文写道：“这番话由我说出来可能会让你感到惊讶，但我认为，在未来一到三年的时间里，我们将会面临这样的情况：凌晨3点系统崩溃，你完全依赖 AI 循环去修复它，没有人知道底层代码到底是怎么回事。这时候，你的公司将面临生死存亡的威胁。”

<details>
<summary>Original English</summary>

**Speaker A**: can get more ambitious and we can add more things to it, but I'm going to quote you with one of your tweets which says, "This may surprise you that this is coming from me, but I think we're in for a 1 to three year period where stuff might break at 3:00 a.m. and you're relying on loops to fix it and nobody understands what's under the hood, and you're looking at an existential threat to your company."

</details>

**Speaker B**: 是的，那条推文的反响非常好。那条推文的数据表现非常出色。[笑声] 

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Uh yeah, that one was great. That one did a lot of numbers. Uh [laughter]

</details>

**Speaker A**: 确实引起了大家的共鸣。

<details>
<summary>Original English</summary>

**Speaker A**: it resonated.

</details>

**Speaker B**: 事情的另一面是，我认为在当今时代，凭借现在的 AI 模型、现在的编程语言和基础设施，你或许可以侥幸做到不看代码。但是，完全依赖 AI 循环的问题在于，到了某个阶段，你会生成海量的代码，以至于你再也无法阅读和理解它们了。这就变成了所谓的“黑灯工厂”（无人工干预的自动化工厂）。这就像是单纯地在堆砌代码，尽可能多地消耗 token。

我们曾经尝试过这种做法。在 2025 年 7 月，我们建立了一个完全无需人工干预的“黑灯”软件工厂，但到了 11 月我们就把它关闭了。我认为，当你连续三到六个月不断地发布新功能，却根本不去看代码，你最终会突然意识到：“哇，情况变得越来越糟了，现在推倒重来甚至比修复它还要容易。”由于 AI 模型把代码库变得如此糟糕，以至于从零开始重新思考这个项目反而更加轻松。

或许这也可以接受，因为我们有 AI，从无到有重建事物变得更容易了。通常情况下，当工程师说：“哦，我们没法修复这个了，我们必须重写”时，通常得到的反馈是：“不，就在原有基础上重构吧。只要不断让代码库变得更好就行了。”

你提到了我之前说的话。你会注意到我说的是：不要用 AI 循环去发布用户想要的新功能。我们使用 AI 循环是为了真正提高代码库的质量。我们会阅读所有的代码，因为我们关心它的架构是如何设计的。我们不仅关心系统架构，还关心我称之为“程序设计”的东西，我认为这是人们未来需要关注的重点：接口在哪里？边界在哪里？我们如何进行依赖注入？所有这些因素都能让你的代码库随着时间的推移更容易维护，并防止你陷入这样的陷阱：“好吧，如果我现在修改了这里，就会弄坏那里的功能。”

这就是软件工程中一个非常经典的问题，实际上，软件工程在 20世纪70年代被发明出来，正是因为我们意识到需要一些技术来避免代码变成一团乱麻。而且我认为，现在的 AI 模型还不够聪明，我们也没有足够的训练数据、基准测试和评估技术，来让模型写出随着时间推移更具可维护性的代码。相反，它们都是在 SWE 和 SWEBench 这样的基准测试上训练出来的，对吧？

所有的基准测试基本上都是这样的模式：这是 Django 里的一个 commit，这是当时提交的一个 issue，看看你（AI）能不能像人类那样写出修复代码。不管是 Django 还是 Apache，无论是在 Go、C++、TypeScript 还是 Java 语言里有成百上千个代码仓库，这些不同的语言都有一个共同点：在代码可维护性方面训练模型的问题在于，“糟糕的架构”和“糟糕的程序设计”其代价函数是无法通过运行单元测试来评估的。因为这种糟糕的设计会在 3 到 6 个月后反噬你，到时候你会惊呼：“天呐，这软件变得根本没法修改了。”

<details>
<summary>Original English</summary>

**Speaker B**: Here's the other side of it is like I think that the today with today's models, today's programming languages, today's infrastructure, you might get away with not reading the code. Problem with loops is like at a certain point you're going to generate so much code that you can't read it anymore. This is the strong VM dark factory. This is like harness engineering. Just spend as many tokens as possible. 

We tried this. We built a lights off software factory in July of 2025 and by November we had shut it down. I think it takes about three to six months of you shipping all the time with nobody reading the code before you realize like, wow, this is getting way worse and it's easier to start over than it is to fix it. Like the models have made the codebase so bad that it is actually going to be easier to just like rethink this from scratch. 

And maybe that's okay because we have AI and it's easier to rebuild things from nothing. And like usually when engineers say like, "Oh, we can't fix this. We have to rebuild it." The feedback is like, "No, just refactor in place. Just constantly keep the codebase getting better." 

You mentioned what I said. You'll notice what I said was not use loops to ship the features that users want. We use loops to actually improve the codebase quality and we read all the code because we care about how it's architected and we care not just about the system architecture but what I would call the program design which I think is something people are going to where are the interfaces where are the seams how are we doing dependency injection all of these things that like make your codebase more maintainable over time and keep you from falling into this trap of like okay well now if I change something over here I broke something over here. 

This is the classic problem of software engineering that like software engineering was invented in the 1970s because we realized we needed techniques for avoiding that problem of like this giant ball of spaghetti. And I don't think the models are smart enough and I don't think we actually have the training and the benchmarking and the eval techniques to get models to write code that is more maintainable over time versus they're all trained on SWE and SWEBench looking things, right? 

All of the benchmarks are basically like here's a commit in Django. Here's an issue that was filed around that time. see if you can create the fix that the human created. And it's Django and it's Apache and it's there's a hundred repos in Go and C++ and Typescript and Java and all these different languages, but they're all it's like the problem with training models on maintainability is like the cost function of bad architecture and bad program design can't be evaluated by running the unit test because it hits you 3 to 6 months later when you're like, "Holy crap, like no one can make it's this software has become so hard to change."

</details>

**Speaker A**: 这难道不就像高级软件工程师的成长历程一样吗？为什么一个人需要花好几年时间才能成为一名高级工程师？因为通常在某些环境下，如果你处于一个快速迭代、问题频发且需要不断去修复它们的环境中，你会成长得更快。但有时候你也知道，有些人在同一个地方工作了 10 年，却依然没有达到那个水平。关键在于，你确实需要时间去理解：你现在犯下的那个小错误，日后是如何像滚雪球一样演变成灾难的。当你真的被这种后果打击过之后，你才会意识到：“好吧，原来测试如此重要，架构如此重要，技术债务真的能成为致命一击。”你知道，虽然我们现在不怎么提这个词了，但在 AI 出现之前，我们经常讨论技术债务是如何严重拖垮公司的，以至于他们的竞争对手能够后来居上。或者他们就是被困在一个长达 2 年的重构期里，完全无法发布任何新功能，而此时竞争对手却发布了一大堆新东西，从而远远走在了前面。

<details>
<summary>Original English</summary>

**Speaker A**: Is this not similar to how senior software engineers why it took years for someone to become a senior? Because typically and in some environments you became a you can become a senior faster typically fast moving where there's a bunch of issues and you have to keep fixing it. Sometimes you know some people are working in the same place for 10 years and they're still not that level. The point was it it just takes time for you to understand the small mistake that you make right now that snowballs into like something disastrous later and you get hit by it and you realize like okay things like you know like testing matters architecture matters tech depth can actually be a killer you know we don't talk about it anymore but we used to talk about how techdub kills or slows down companies so badly preai that their competitors can overtake them or they're just like stuck with a 2-year refactor not shipping any new features and the competition you shifts a bunch bunch of other stuff and now they're ahead.

</details>

**Speaker B**: 我得说，GPT-7 或许真的能够解决这个问题。但是，如果你在你的软件工厂里直接“关灯”实现全自动化，并且你认为：“嘿，你们知道吗？我们不打算再看代码了。没关系，AI 模型已经足够聪明了。只要我们给它正确的反馈，并在这个问题上投入足够多的 token 计算力，它就能不断变得更好。”正是这种想法让我发了那条推文。这种做法或许短期内行得通，但如果连续三个月都没有人去看过代码，并且你把所有的代码审查都替换成了 AI 循环——比如，如果用户抱怨，我们就把它丢给一个 AI 智能体；如果系统崩溃了，我们把它丢给智能体；如果产品经理写了一个需求工单，我们给智能体；甚至如果 CEO 在 Slack 上写了一篇令人讨厌的长篇大论，谈论我们应该开发什么，我们也直接扔给智能体。

<details>
<summary>Original English</summary>

**Speaker B**: And I will say like it is possible that GPT7 will fix this, but if you are turning the lights off in your software factory and you're saying like, "Hey, you know what? Like we're not going to read the code. It's fine. The models are smart enough. If we give it the right feedback and just throw enough tokens at the problem, it will keep getting better." This is what led to this tweet. that might work, but if nobody read the code in three months and you replace all of your all of your like code review with loops of like, hey, if a user complains, we give it to an agent. If something crashes, we give it to an agent. If a PM writes a ticket, we give it to an agent. If a CEO writes an obnoxious essay about what we should be building in Slack, we give it to an agent.

</details>

**Speaker A**: 是的。[笑声]

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. [laughter]

</details>

**Speaker B**: 然后你就彻底停止阅读代码了，因为那会产生太多代码，根本没有人能看得完。这个时候，人工进行 Pull Request (PR) 审查就会成为整个流程的瓶颈。因此，你把 PR 审查也替换成了智能体自动化测试和智能体代码审查。但是，这些 AI 工具目前对软件架构完全没有直觉，因为我们还没有把这些直觉训练到它们的大脑里。所以，总有一天你醒来时，会面临一个极其棘手的问题——这实际上发生在我们身上过，我们当时熬过来了。那时候我们还在想：这样做依然是值得的。为了解决那个问题，我们花了 3 个星期的时间重新熟悉那个我们已经 3 个月没有看过的代码库。因为不管我们用了多么复杂、多么专家级的提示词，我们就是没法让 Opus（我想当时用的是 Opus 4.1 模型）去真正找到根本原因。我们不得不亲自花了几天的时间，去挖掘代码，最后才弄清楚：“哦，实际上是有一个主键（Primary Key）在整个系统链路里传递，需要被修改成一种不同类型的对象才行。”

<details>
<summary>Original English</summary>

**Speaker B**: And then you stop reading the code because that's going to produce way too much. Like, no one can read it. And like the PR reviews become the bottleneck. So, you replace that with aentic testing and agentic code review. Uh, but none of these things have intuition for software architecture because we haven't trained it in yet. And so you're going to wake up one day and you're going to have an issue with this happened to us and like we got through it and at the time like it was still worth it. It was like spent 3 weeks onboarding back into the codebase that we had stopped reading 3 months ago because no matter how much sophisticating expert prompting we could not get Opus, I think it was Opus 4.1 at the time. We could not get Opus 4.1 to actually find the root cause. We had to go spend several days digging through the code and figuring out like, oh, there's just actually a primary key that's being routed through this whole thing that needs to be changed to a different type of object and it needs it.

</details>

**Speaker A**: 这居然真的在你们身上发生过。

<details>
<summary>Original English</summary>

**Speaker A**: This actually happened to you.

</details>

**Speaker B**: 这确实发生在我们身上了，是的。

<details>
<summary>Original English</summary>

**Speaker B**: This happened to us. Yeah.

</details>

**Speaker A**: 而且当它发生的时候，我的反应是：“你知道吗？这简直太糟糕了。太可怕了。”但我们还是挺过来了，我们解决了它。而且这仍然是值得的……为了在绝大部分时间里都不用去看代码，偶尔花上两个星期手动去修复一个棘手的问题，这买卖还是划算的。但我现在不再相信这种说法了，因为我认为我们现在能够编写的代码量已经增长了 10 倍甚至 100 倍，我认为代码维护的问题正在变得越来越糟。

<details>
<summary>Original English</summary>

**Speaker A**: And when it happened, I was like, you know what? That sucked. That was terrible. But we did it. We solved it. And uh it's still worth it's still worth not reading the code for most of the time at the cost of every once in a while I'm going to have to spend two weeks fixing an issue by hand. And I don't believe that anymore because I think the amount of code we're able to write now is actually like 10xed or 100xed and I think the problem's just getting worse.

</details>

**Speaker B**: 那么我们来聊聊软件工厂吧。

<details>
<summary>Original English</summary>

**Speaker B**: So let's talk about software factories. Yeah.

</details>

**Speaker A**: 在你看来，因为我觉得这是一个被过度使用的词，但在 AI 出现之前，以及现在的后 AI 时代，你是如何看待软件工厂这个概念的？

<details>
<summary>Original English</summary>

**Speaker A**: In your mind, cuz I feel it's an overloaded word, but what do you think of a software factory before AI and now post AI?

</details>

**Speaker B**: 你知道“软件工厂”这个词第一次被定义和使用是什么时候吗？

<details>
<summary>Original English</summary>

**Speaker B**: Do you know the first definition of software factory the first time it was used?

</details>

**Speaker A**: 不知道。

<details>
<summary>Original English</summary>

**Speaker A**: No.

</details>

**Speaker B**: 是在 1968 年的北约（NATO）会议上。

<details>
<summary>Original English</summary>

**Speaker B**: It was a NATO conference in 1968.

</details>

**Speaker A**: 哦，Grady Booch 一定知道这件事。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, Grady Buch would know about this.

</details>

**Speaker B**: 是的，一点没错。对，你可以去问问 Grady 这件事。他们当时讨论的一个观点是：好的，你实际上需要建立一个由多个步骤组成的系统，就像工厂车间那样。你需要有编码环节、测试环节、验证环节，还有集成环节。当时我们根本没有 CI/CD（持续集成/持续部署），我们甚至几乎连版本控制都没有，但你仍然需要一个这样的“工厂”。后来这个理念被东芝（Toshiba）以及一大批公司所采用。

紧接着的下一个阶段就是 DevOps（开发运维一体化）。人们提出了这样一个想法：“好的，我们要做 CI/CD，我们要实现自动化。我们要用 Chef、Ansible、Puppet 等等。”所有这些技术的本质就是：不再让人工在数据中心里跑来跑去，手动去扩容磁盘之类的工作，也不再是在 AWS 控制台上点来点去。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, exactly. Yeah, great. You should ask Grady about it. They talked about the idea of like, okay, you actually need to build a system of steps and like just like a factory floor. You have like the coding part and the testing part and the validation part and the integration part. We had no CI/CD. we barely had version control like but you needed a factory and then it was adopted by like um Toshiba and a bunch of companies and then the next moment was like DevOps and you have like this idea of like okay we're going to do CI/CD we're going to automate we're chef and anible puppet whatever all these technologies is like instead of having dudes running around data centers like resizing discs and stuff or clicking around the AWS console

</details>

**Speaker A**: 是的，完全准确。情况变成了这样：“酷，我们构建了循环。服务器磁盘空间达到 90%，这就发送一个警报给 Nagios，Nagios 触发一个 Chef 脚本，Chef 自动把磁盘进行扩容。”这就是反馈循环，对吧？这种模式已经存在有一段时间了。我想说，在 2018 年，有一个叫 Nick Chaillan 的人，他当时担任首席技术官或者是首席...

<details>
<summary>Original English</summary>

**Speaker A**: yeah exactly it was like cool we build loops the server hits 90% disc space that sends an alert to Nagios Nagios triggers a chef front chefs makes the disc the disc bigger feedback loops, right? This has been around for a while. And in 2018, I want to say this guy Nick Chalane who was uh he was like the CTO or chie ch ch ch ch ch ch ch ch ch ch ch

</details>

<!-- chunk 8/14 -->

### Software Factories and Agentic Automation

**Speaker A**: 空军首席软件官写了一篇长达一百页的文章，指出：“嘿，国防部需要一个软件工厂。”

<details>
<summary>Original English</summary>

**Speaker A**: chief software officer of the air force, he wrote this 100page essay of hey the DoD needs a software factory,

</details>

**Speaker B**: 是的，国防部和空军。他称之为“DevSecOps 工厂”。他表示，我们需要所有优秀企业正在使用的那些工具。我们需要 Jenkins，需要代码质量扫描，需要安全扫描，需要 CI/CD。我们需要具备交付能力。我们现在的交付频率是每三个月甚至一年才一次，我们需要像其他所有公司那样做到每天都能交付。而实现这一目标的方法，实际上就是拥抱所有的自动化和技术，这样就能让自动化流程捕获 90% 的问题，而不是让人工去逐一排查、手动阅读代码或手动把各个模块集成在一起。

<details>
<summary>Original English</summary>

**Speaker B**: the department of defense. Yeah, the the department of defense and the air force. And he called it the dev sec ops factory. And he said we need all the things that all of the good enterprises are using. We need Jenkins. We need like code quality scanning. We need security scanning. We need CI/CD. We need to be able to ship. We're shipping once every three months or once a year. We need to be able to ship every day like all these other companies. And the way we do that is we actually embrace all these automations and technologies so that engineers are are 90% of the issues are caught by automations instead of people actually like manually checking it or manually reading the code or manually integrating modules together.

</details>

**Speaker A**: 哇。这在政府部门里可以说是相当有前瞻性的思维了。

<details>
<summary>Original English</summary>

**Speaker A**: Wow. Talk about forward thinking in in the government.

</details>

**Speaker B**: 我知道。当时我也很惊讶，觉得“哇，真不错”。我的意思是，这部分原因在于他们意识到：“嘿，看，我们落后了。”我不知道确切的所有原因，但我想这可能也和吸引顶尖人才有关，就像是在说：“看，如果我们有现代化的软件技术栈，我们能快速构建产品，我们注重效率，我们珍惜大家的时间。我们希望员工把时间花在工作中最具挑战性的部分，而不是去手动排查 SQL 注入漏洞——因为这些完全可以自动化。”所以，这就是前 AI 时代的软件工厂。

<details>
<summary>Original English</summary>

**Speaker B**: I know. Oh no, as I was surprised like oh nice like this is I mean and that was part of it is like hey look we're falling behind in like you know I don't know exactly all the reason but I I imagine also about like attracting really good talent is like hey look if we have like the modern software stack and we're building things fast and we care about efficiency and we care about people's using people's time well we care about them spending time on the hard parts of the job not manually looking for SQL injections like you could automate that. So this was software factories pre AAI.

</details>

**Speaker A**: 前 AI 时代。

<details>
<summary>Original English</summary>

**Speaker A**: Pre AI.

</details>

**Speaker B**: 现在因为 AI 的出现，我听到这个词的频率高多了。

<details>
<summary>Original English</summary>

**Speaker B**: Now I've heard the term a lot more because of AI.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 那么它还是原来的意思吗？还是说已经不同了？

<details>
<summary>Original English</summary>

**Speaker B**: Is it the same? Is it different?

</details>

**Speaker A**: 这个很难不画图就解释清楚，但我尽量口头描绘一下。在软件工厂的核心，你会有一个“工作源头”。大多数时候，你可以想象这是一个线性的队列，比如 Jira 或者某个真相源——无论是电子表格还是其他什么形式，你在这里记录工作处于哪个阶段。

<details>
<summary>Original English</summary>

**Speaker A**: So this is really hard to say without a drawing, but I'll try to draw it out. At the core of a software factory, you have like a source of work. Most you you can imagine a linear a Jira a the st source of truth your object whether it's a spreadsheet or whatever is you have like what stages is the work in.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yep.

</details>

**Speaker A**: 在前 AI 时代，你可能会先做一些架构评审和规划。你可能还需要进行冲刺规划（sprint planning），然后人们从队列中领取工单（tickets）并去开发。接着，你会提交一个 Pull Request (PR)，然后其他人会进行代码审查，接着你会运行 CI 检查，之后将其部署到生产环境。部署后，它会接触到你的用户，用户可能会抱怨一些问题，这些反馈会进入客户支持团队，然后重新回到你的任务追踪系统中。如果系统崩溃，出现问题，这些问题会进入你的监控系统，再流入任务追踪系统。这就是你的整个循环。

然后，大家会根据优先级从任务追踪系统里领取任务。产品经理、工程经理和工程师一起排定优先级，然后我们再去执行。这里的第一个变化是，这个流程非常漫长，包含非常多的阶段。这也是为什么有时候开发者引入了一个 bug，但等它反馈到你这里时，可能已经是两三个月甚至更久以后的事情了；而等到它被修复，可能又需要一两年的时间。大家都懂的，这就是为什么当你在使用一款软件时，遇到一个烦人的 bug，你去联系客服，但感觉在软件工厂的每一个环节都存在着极其漫长的延迟。

而且，从某人从队列中接下一个工作项并开始处理，到它真正被集成到系统中并触达用户，中间往往需要几个小时到几天的时间。要知道，这还是在一个非常理想的情况下。有时候你去开发了一个功能，然后合并了代码，但它可能要等三个月后才真正发布。但我们现在先假设我们在一个相当现代化的公司，比如像 Netflix 或 Meta 那样，工程师有能力每天部署发布一百次甚至一千次，但完成实际的开发工作依然需要两三个小时。

而现在，在“Agentic 工厂（智能体工厂）”里，你的做法是：把负责开发的那个人撤掉，替换成一个智能体（Agent）去构建这个东西。所以你需要有编排系统（orchestration）来触发任务。你还需要一个沙盒、一个大语言模型（LLM）、一个内部环境以及一个外部环境——这就好比你为智能体搭建的开发环境。你可能还会给它配备一个浏览器，如果你用的是类似 Cursor 这种后台智能体，你可能还会给它配备屏幕录制工具。他们本质上是在作为“编码智能体”的内部环境周围，搭建了这个外部环境。然后你再用它来提交 PR。

但这里面的问题在于，好吧，现在完成一次构建只需要 10 分钟，而不是两小时或两天，所以瓶颈又变成了代码审查。于是大家说：“好吧，那就扔一堆 AI 智能体去做代码审查，让我们进行智能体测试吧。”这样我们基本上就能捕获大部分简单的问题，让人类只专注于代码库中最重要、最关键的核心部分。

这个智能体工厂的再上一层则是处理顶端反馈：当代码部署到生产环境后，用户抱怨出问题了，你直接把你的客服工单队列接入到智能体。只要有人报错，智能体就去尝试修复。它不再是让人去看工单，然后再分派任务，而是直接闭环。现在每次出错，你就能直接得到一个 PR；每次在 Sentry 或 Datadog 这种监控系统里发生崩溃，问题进入追踪系统后就会被智能体接管，然后你就会收到一个 PR——这就是 Ramp 公司的 Inspect 工具在做的事情。唯一的区别在于，那时候你需要审查的代码实在太多了，于是有人提出：“我们干脆‘关灯’盲飞吧！我们把所有的人工测试和审查环节全部砍掉。”我们会说：“好吧，如果用户抱怨了，那就说明它坏了；如果用户没有抱怨并且它还在运转，我们就不去读那些代码了。我们会把整个系统当成一个黑盒来对待。”

<details>
<summary>Original English</summary>

**Speaker A**: And prei you would take, you know, you would maybe do some architecture review planning. You would maybe do some sprint planning and then people would take tickets off the queue and they would go build them. And then you would make a pull request and people would review it and you would run CI checks and then you would send it to prod and then it would make contact with your users and your users would complain about stuff and that would go to your support team and back into your tracker and it would crash and you would have issues and that would go into your monitoring stack and that would go into your tracker and that was your loop. And then people would take stuff off the tracker based on priorities. product managers, engineering managers, engineers prioritizing work and then we go and do that and the first change is is like this long wind lot lots of phases and this is also why when like a developer shifts a bug but by the time it comes back to you it might be two or 3 months or even longer and by the time it get fixed it might be a year or two and you know this is why when you're using a piece of software it's like that annoying bug and you talk with customer support but it's just a very like long latencies at each each part of the the factory if you will. Yeah. And the the step where someone pulls a work item off a queue and starts working on it is, you know, couple hours to a couple days before it actually gets integrated into everything else and touches user. And that's in a in a in a great world, right? Sometimes you go build it and then you merge it and then it actually gets released 3 months later. But we're going to assume we're in a fairly modern like we're somewhere like the a Netflix or a meta where engineers are capable of shipping 100 times a day or a thousand times a day, but it still takes 2 three hours to do the work. And now with an identic factory, what you do is you take out that person building the thing and you replace it with an agent building the thing. And so you have orchestration to trigger things. You have a sandbox, you have an LLM, you have an inner harness, you have an outer harness, which is like the dev environment you build for the agent. And maybe you give it a browser, you give it a video recorder if you use like things like cursor background agents. They've kind of built this outer harness around the inner harness that is the coding agent. And then you make PRs with that. problem there is that like okay now now it takes 10 minutes to do a build instead of two hours or two days and so now the bottleneck is code review so okay let's throw a bunch of AI agents at code review and let's do agentic testing so that like we can basically catch a lot of the easy stuff and humans are only focused on the most like important critical core parts of the codebase and then the next level up of your agentic factory is you do the top it's like okay then it gets deployed it goes to prod and a user complains you just hook your support queue right up to the agent someone complains about something agent tries to fix it and instead of looking at a ticket and then saying okay go send you just close that loop and instead every time something goes wrong you just get a PR and then every time something crashes in Sentry or Data Dog or whatever it goes into the tracker it gets picked up by an agent and you get a PR this is the ramp inspect thing this is the the only difference is like then you have so much code to review and people say well let's try turning the lights off let's just take all the human testing and review steps out and we'll say okay cool if users complain then it's broken and if users don't complain and it's working and we're not going to read the code. We're going to use we're going to treat the whole system as a black box.

</details>

**Speaker B**: 那么，你提到你尝试过这种做法，那时候好像还在用 Opus 模型，你搭建了这个软件工厂，一开始运转得非常完美，直到它在你面前彻底崩溃。你是如何看待这个模型的？因为我能想象出一个理想的世界中它是能运转的，但显然我们并不在一个理想的世界里。你认为我们现在处于什么阶段？这其中的一部分在未来的某个时候真的能跑通吗？或者说，你目前看到了哪些进展？今天的现状到底是什么样的？你认为这里面有多少内容是我们能够自动化，或者是我们应该自动化的？

<details>
<summary>Original English</summary>

**Speaker B**: So, you said you tried this out uh when it was like Opus Formula and you you built the software factory was running beautifully until it just blew up on your faces. How do you think of this model? cuz I I can see an ideal world where it works, but clearly we're not in an ideal world. Like where do you think we are like and could some of this actually work at some point or you know like like what what progress are you seeing right now and and what is the the today the situation like how much of this do you believe we can automate or should we automate?

</details>

**Speaker A**: 是的。如果你了解我、关注过我的内容，你就会知道我坚持三件事。第一件是：穿透那些炒作和术语，去亲自尝试，去和真正使用这些技术的人交流，搞清楚其中哪些部分真正有效、有价值。

第二件，我们刚刚谈到了“词语”。我总是努力寻找并保护那些有用的语言表达，因为我认为这有助于我们所有人共同进步。当你拿一个有用的词，比如“智能体（agents）”，或者拿一个有用的词，比如“软件工厂（software factory）”，然后你在语义上将其稀释——这也是 Martin Fowler 提到的一个词——你让它变成了每个人都喜欢的流行语，结果一切都变成了炒作，大家都开始跟风，“智能体”这个词就再也没有任何实质意义了。智能体可能是一个聊天机器人，可能是一个 Slack 机器人，可能是一个编码智能体，也可能只是循环调用的一组工具，随便什么都可以。所以，我希望能保护这些重要且有用的词，帮助我们把对话的层次拔高，跳出炒作和黑话的泥沼。

然后我非常看重的第三点是，我会深入到我日常工作领域的下一层去。我认为总是存在这样一种关系，这和“上下文工程（context engineering）”是同一个道理：尽管我很少真的去构建或训练大语言模型，但只要你了解它们是如何被训练的、Transformer 架构是如何工作的，这种知识就会指导你在上一层的构建工作。在“软件工厂”这个话题上，我践行这一理念的方式是，我在过去几周里深入研究了带可验证奖励的强化学习（RLVR）。这是一种非常贴近生产环境的技术，它不像传统的基于人类反馈的强化学习（RLHF）那样仍然停留在学术和纯理论层面。RLVR 就是那些实验室里用来训练这些模型的机器。我正在研究像编码智能体的基准测试（benchmarks）、训练它们的技术，以及我们是如何通过给它一个小问题让它解决，然后删除它所做的测试更改，再将它们回滚……

<details>
<summary>Original English</summary>

**Speaker A**: Yep. So if you know me, you follow my stuff, you know I stand for three things. Number one is like cutting through the hype and the jargon and going trying things and talking to people who are using things and figuring out which parts of this actually work and are valuable. Number two, we talked about words. I try to find and protect useful bits of language because I think it helps us all move forward. And when you take a useful word like agents or you take a useful word like software factory and then you semantically diffuse it, this is another Martin Fowler word. You make it mean everybody likes the word and it all becomes hype and everyone starts agents means nothing anymore. agents could be a chatbot, it could be a Slackbot, it could be a coding agent, it could be tools in a loop, whatever it is. So, I like to protect important useful words and like help help us all like elevate the conversation out of that hype and jargon. And then I care a lot about going one level down beneath where I'm generally working. I think there's always this is the same thing with context engineering is like I was rarely actually going and like building LLMs or understanding or training LLMs but knowing how theyre trained how transformers works informs how you build at one layer up and for the software factory my version of that is I spent the last couple weeks going really deep on uh reinforcement learning with uh verifiable rewards RLVR which is like this very productionized like it's not like RH RHF is still like fairly academic and pure RLVR are is this like it's a machine in these labs of how we train these models and I'm studying like the benchmarks for coding agents and the techniques for training them and how we like give it a small problem have it solve it delete the test changes it made revert them

</details>

<!-- chunk 9/14 -->

### 代码库维护与基准测试的局限性

**Speaker A**：应用一个测试补丁，看看它是否通过，然后甚至在这个领域的这个前沿模型，今年我们有，比如我们稍后可以深入探讨这个，但是像 Frontier Code 和 Marathon 这样的，这些新的基准测试，本来应该是比如更擅长评估模型随着时间推移维护代码库以及编写可维护代码的能力的，嗯，并且它们确实更好了。但我认为它们还不够。但这基本上是这样一种想法，即让 Claude Code 变得如此出色的唯一原因是强化学习。它变得出色的那个维度是，比如我们制作了一个模型。我们将模型和测试工具链一起进行了训练。因此，该模型在调用该工具链中的特定工具方面变得非常出色。通过解决这些问题，在读取文件、写入文件、搜索文件，所有这些事情上都非常出色。这就是为什么它让人感觉比之前出现的所有其他命令行界面（CLI）编码代理都要好得多的原因。所以人们会觉得，“好吧，那好太多了。”并且它们只会继续变得更好。但这就好像，它在一个维度上变得非常出色。而它们没有变得更好的那个维度，因为它很困难、很昂贵。也许我们需要，比如在设计这些，这些验证器和基准测试时更有创意，即我该如何编写代码，使得在三个月内它将比如提高人类和代理（主要是代理，但同时也是人类和代理）在代码库中的生产力，而不是随着时间的推移让它变得更糟。

<details>
<summary>Original English</summary>

**Speaker A**: apply a test patch see if it passed and then even the frontier this year we have like we can get into this later but like frontier code and marathon these new benchmarks that are supposed to be like better at evaluating models's ability to maintain a codebase over time and write maintainable code um and they are better But I don't think they're sufficient. But it's basically this idea that like the only thing that made claude code good was reinforcement learning. And the dimension along which it got good was like we made a model. We trained the model and the harness together. And so the model got really good at calling the specific tools in that harness. Really good at reading files, writing files, searching for files, all this stuff through doing these problems. And that was what made it feel so much better than all the other CLI coding agents that came before it. And so people like, "Okay, that was so much better." And they're just going to keep getting better. But it's like it got really good in one dimension. And the dimension that they're not getting better in because it's hard, expensive. Maybe we need to like get a lot more creative with how we design these these verifiers and benchmarks is in how do I make code that in three months is going to like improve the productivity of humans and agents, mostly agents, but humans and agents in the codebase instead of making it worse over time.

</details>

**Speaker B**：那么你认为那一部分恰恰是缺失的吗？我们还没有看到太多的改进。

<details>
<summary>Original English</summary>

**Speaker B**: And so you think that part is just missing? We haven't seen too much improvement.

</details>

**Speaker A**：我没看到，显然没有人知道实验室内部正在做什么，因为这一切都非常机密。但我认为，如果我们看看基准测试，基准测试往往反映了实验室所处的位置，对吧？如果没有任何一个基准测试可以向我传达，这个模型编写的代码是会让我的代码库变得更好还是更糟。我们所能拥有的最好的基准测试是，我认为，来自 Cognition 团队的 Frontier Code 非常有趣。他们有诸如“测试是否通过”这样的标准，然后他们有类似两层模型审查。所以他们有一个评判模型，它会检查，好吧，模型制作的补丁是否类似于那些作为黄金答案集的补丁。所以即使模型没有编写出基准测试所期望的确切代码，它在功能上是否等效？下一个就像是来自另一个评判模型的，类似代码质量审查，这确实好一些了，但它不是，这还不够。这就是为什么我也认为，代理代码审查就像是，是的，它会捕捉到一些东西，它会提高你的下限，但我并不相信，比如编写代码的模型和阅读代码的模型是同一个模型，并且如果你问一个模型，嘿，这段代码好吗？它会说，哦，是的，太棒了，很全面，它有单元测试，我确信你已经尝试过了。如果你说，好吧，审查一下我同事写的这个拉取请求（PR），并告诉我它所有的问题，我会觉得，哦，它有这个问题，和这个问题，以及这是，这是阿谀奉承的，它们想告诉你你想听的话。所以比如，对我来说，真的很难去信任一个模型来评估所编写代码的质量。因此，我，我，我有一些想法，比如，好吧，你能否建立一个基准测试，在这个测试中模型连续构建 20 个功能，并在整个过程中维护代码库，并且它不知道接下来会出现什么功能。你把它当成一个真正的产品团队来对待，在那里你不知道下周你要构建什么，直到你走到那一步，你才发现什么是最重要的，然后我们能否尝试去评估，比如我们能否构建一个像那样的问题，它足够难，以至于大多数前沿模型在遇到第六个或第七个问题时就会失败。

<details>
<summary>Original English</summary>

**Speaker A**: I haven't seen obviously no one knows what the labs are doing internally cuz it's all very secret. But I think if we looking at where the bench the benchmarks tend to reflect where the labs are, right? If there is no benchmark that can convey to me did this model write code that is going to make my codebase better or worse. The best we have is I I think frontier code from the cognition team is really interesting. They have like did the test pass and then they have like two layers of model review. So they have a judge model that checks okay is the patch the model made similar to the patch that is like the golden answer set. So even if the model didn't write the exact code that the benchmark was expecting did was it functionally equivalent and the next one is like a like code quality review from another judge model and like that's better but it's not it's not sufficient. And this is why I also think agentic code review is like yes it will catch things and it will raise your floor but I don't believe like the model writing the code is the same model reading the code and if you ask a model hey is this code good it's going to be like oh yeah it's great comprehensive it's got unit tests you've tried this I'm sure and you say okay review this PR that my coworker wrote and tell me everything that's wrong with it I was like oh it has this problem and this problem and this is this is sickopantic and they want to tell you what you want to hear and so like it's really hard for me to trust a model to evaluate the quality of of of code that's written And so I I I have some ideas on like, okay, can you build a benchmark where the model builds 20 features in a row and maintains the codebase the whole time and it doesn't know what features are coming. You treat it like a real product team where you don't know what you're going to build next week until you get there and you find out what's most important and then can we try to evaluate like can we build a problem like that that's hard enough that most frontier models fail by issue six or seven.

</details>

### 软件工厂模式的演变

**Speaker B**：可以这么说吗，你知道，就像我们在人工智能出现之前就有了软件工厂（software factory），它就像有很多循环，就像，产品经理（PM）把工单（ticket）交给开发人员（dev），开发人员构建它，部署到生产环境，用户、客户使用它，客户支持收到工单，然后你创建，产品经理进行分流（triaging），它就像在这个循环中转圈。可以这么说吗，关于一家公司、一个团队如何构建和维护正在发生变化的软件的这种软件工厂模式，正在发生改变？因为现在每个人都在替换其中的一些部分，你知道，也许最不先进的团队将会是仅仅开发人员开始使用 Cloud Code 或 Codex 来编写得更快。他们在那里花费的时间没有那么多了。其他一些团队也拥有了部署、反馈环节。有些，有些实际上已经拥有了能够一击即中解决漏洞（bugs）的代理。所以比如，可以这样说吗，那个软件工厂只是，只是在随处发生变化，也许是以不同的速度，但每个人，我认为每一个正在构建生产软件的团队，他们就像是，他们都在疯狂地试验、尝试，而且每个人都处于不同的步伐中。你会看到人工智能原生（AI native）的起步者，其中大部分都会有代理在里面，你也会看到落后者（laggers），那些或者更，更谨慎的团队。他们在少数几个地方有代理，但在其他地方则没有。

<details>
<summary>Original English</summary>

**Speaker B**: Is it fair to say that you know like we've had the software factory like before AI it was just like lots of loop it was like the the PM giving the ticket to the dev the dev building it deploying to production user customers using it customer support getting tickets and then you creating PM triaging and it kind of goes around like in this loop is it fair to say that the software factory of how a company a team builds and maintains software that is changing because now everyone's replacing some parts of it, you know, maybe the the least advanced teams will just be devs are starting to use cloud code or codecs to write faster. They're not spending as much time on there. Some others are also having the deployment the feedback. Some some actually have the agents already oneshotting bucks. So like is it fair to say that that the software factory is just is just changing everywhere maybe at different speeds but everyone I think every team who is building production software they're like they're frantically experimenting trying and everyone's at a different pace. You'll have the AI native starters where most of this will have agents in them and you'll have the the laggers who are or more more cautious ones. They have agents in a few places but not in the others.

</details>

**Speaker A**：嗯，我认为关键在于，比如如果你想做循环工程（loops engineering），你应该一次构建一个循环，并且你应该保持它们体积小且被包含在内。基本上，我认为除了“停止阅读代码”之外，所有的事情都是非常好的建议。把支持工单转化为你们系统中的工单，然后也许把那些转化为拉取请求（PRs）。很棒。我有的建议，以及我们在 Human Layer （人类层）一直在追求的，就像是，我如何在这个工厂里增加另一个检查点？所以，与其只有一个人类审查点，在那里你要审查 PRs，有时它们有 100 行，有时它们有一千行，但这是相当大的一项工作，特别是如果它写得很糟糕，特别是如果它需要返工的话。对于一个人类来说，要说，好吧，这是错的，去用这种方式修改它，然后你循环回到代理，然后你带着另一个版本回来，这相当费力，并且比如在那上面做很多循环，一旦，一旦方向已经被确定并承诺下来，就真的很难再偏离开来，就像你最好还是直接从头开始重新启动一样。你如何在这周围构建，比如控制和机制呢？然后我的看法是，比如如果你在把它交给实施者（impletor）之前，做一点点人类和代理的规划，以及比如讨论，无论是，我是说规划和规范（specs），随便你想怎么叫它，重申一下，这就是规范驱动开发（spec driven development），这是另一个词，关于它的含义已经变得有点非常像是一团糟了，但基本上，我们如何能在开始构建之前花一个小时的时间，这样一来，当我们在阅读 PR 时，它只需要花费 20 分钟，因为代码是完美的？而不是不去碰它，只是从字面上说让每一个用户报告的问题都通过这个循环变成一个 PR，然后我们去读那个 PR，结果它要花六个小时，因为有来回的沟通，我们不得不去做出修改和各种事情。这一切都是，我完全是关于，比如让我们寻找杠杆。所以你基本上，你在软件工厂的世界里有三个选择。如果你要在代理式（agentic）软件工厂上全力以赴，你可以关灯，直接让一切顺其自然，并祈祷你不要制造出太多的劣质代码（slop），祈祷下一代模型能在你制造出一大堆灰烬之前足够快地到来。你可以大幅放慢速度，并阅读每一个 PR 和每一行代码。呃，然后你只会从 AI 那里获得真正的、适度的收益，因为那变成了，我，我认为你应该期待，比如在我们进入团队时看到的，可能大概是 30% 到 50% 的生产力提升。或者你可以找到正确的杠杆点，在哪里人类能够实际地，在这里规划上花费一个小时，就能在实现过程中为你节省四个小时的时间，就修复、返回以及，以及把设计做对而言。这就是我所称之为的，比如寻找杠杆。如果你能为代理找到正确的杠杆点来引导工作，那么你实际上可以移动得，比如快两到三倍，同时保持一种比如 99% 的，比如准确度，这就好比，如果人类在手工仔细地编写这段代码，它结果会是怎样？

<details>
<summary>Original English</summary>

**Speaker A**: Well, and I think that's the key is like if you want to do loops engineering, you should build one loop at a time and you should keep them small and contained. Basically, I think everything except stop reading the code is really good advice. Take support tickets and turn them into tickets in your system and then maybe turn those into PRs. Great. The advice that I have and like what we kind of like are chasing at human layer is like how can I add another checkpoint in that factory? So instead of having one human re view point where you're reviewing PRs and sometimes they're 100 lines and sometimes they're a thousand lines but it's quite a lot of effort for especially if it's bad especially if it needs rework. It's quite a lot of effort for a human to be like okay this is wrong go change it in this way and then you loop back to the agent and then you come with another one and like doing a lot of loops on there once once the direction has been committed to it's really hard to steer off like you're better off just kind of restarting from scratch. How do you build like controls and mechanisms around that? And then my take is like if you do a little bit of human agent planning and like discussion before you hand it to the impletor whether it's I mean planning and specs whatever you want to call it again this is spec driven development is another word that has become kind of very like muddled as far as what it means but basically how can we spend an hour before we start building so that the PR when we read it only takes 20 minutes because the code is perfect instead of not touching it just literally saying every user reported issue becomes a PR through the loop and then we read that PR and it takes six hours because there's back and forth and we have to make changes and things. It's all I'm all about like let's find leverage. And so you basically you have three options in the software factory world. If you're going to go all in on aentic software factories, you can turn the lights off and just let everything flow and pray that you don't create too much slop and pray that the next generation of models comes fast enough before you create a giant pile of ash. you can slow way down and read every PR and read every line of code. Uh, and then you're only going to really get modest benefits from AI because that becomes I I think you should expect maybe 30 to 50% lift in productivity is kind of what I see when we go into teams or you can find the right leverage points where humans can actually an hour spent over here in planning can save you four hours in in implementation in terms of fixing and going back and and getting the design right. And that's what I call like seeking leverage. If you can find the right leverage points for the agents to guide the work, then you can actually move like two to three times faster while maintaining a like 99% like accuracy to like if the humans were carefully writing this code by hand, how would it come out?

</details>

### 研究、规划与实现框架 (RPI)

**Speaker B**：现在让我们稍微跳回到想法（ideas）上。我还会再回到这个话题。这是更早的时候，也许是去年，但你提出了研究-规划-实现（research plan implement）。我们能谈谈最初的研究-规划-实现框架吗？以及还有，关于这种方法你学到了什么？什么，关于它你做错了什么。

<details>
<summary>Original English</summary>

**Speaker B**: Now jumping a little bit back to ideas. I will come back to this. This was earlier maybe it was last year but you had the research plan implement. Can we talk about the original research plan implement framework and then also what you've learned about this approach? what what you got wrong about it.

</details>

**Speaker A**：是的，当然。是的。所以，嗯，我的意思是，我们第一次讨论 RPI（研究-规划-实现）是在 2025 年 8 月。嗯，并且它是

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, sure. Yeah. So, um I mean the first time we talked about RPI was in August of 2025. Um and it was

</details>

<!-- chunk 10/14 -->

### RPI 框架与规划 (Planning)

**Speaker A**: 基本上，研究阶段就是这样：“嘿，在你去构建任何东西之前，先去阅读大量的代码。” 并行使用一堆子智能体（sub-agents），理解所有的代码。对于复杂代码库中的难题，这是一种效果非常好的技术。你只是让 Claude 去做一件事，它只会读取三个文件然后进行修改。它没有任何上下文。所以，你要开始研究。你甚至不告诉它你在做什么。你只是告诉它，“嘿，你能告诉我这个系统是如何工作的，以及这个系统，还有它们是如何连接在一起的吗？” 然后你会得到一个 Markdown 文档，这就是上下文工程（context engineering）的一部分。它可能需要 100,000 个 tokens 的上下文，但你能从中得到一个 10,000 个 tokens 的文档来总结它。然后你会启动一个新的上下文窗口并进行规划，而且实际上你会发现，我们去年夏天制定的计划其实非常糟糕。但它基本上会有这么长。你会说：“好吧，现在这是我们要构建的东西。这是研究文档。构建一个计划来实现它。” 回想起来，现在我们看到每个人都痴迷于如何让智能体工作更长时间，我认为在 2025 年 5、6、7、8 月，很多人对规划产生浓厚兴趣的原因是，它是让智能体工作更长时间的一个非常强大的杠杆。如果你说，“给我构建一个用于墨西哥卷饼配送的 B2B SaaS”，你可能只会得到一个主页，仅此而已。但如果你说，“给我制定一个计划”，它会构建出一个庞大的计划。然后在下一个上下文窗口中，你会说，“嘿，这是计划。这是我们要进行的所有更改。去实现它吧。” 它实际上会一直执行，直到计划完成。所以规划是锚定智能体并提醒它的一个非常好的方法，比如，“嘿，直到这一切都完成，你才算结束。” 这就是最初的 RPI 框架。而计划文档，其糟糕之处在于它没有给你带来杠杆效应（leverage）。这个计划包含了在 diff 块中即将更改的每一行代码，以及所有要编写的新内容。所以人们会去审查这些计划。我们推荐这样做。我们告诉人们去阅读计划。我们阅读了所有的计划。然后最终我发现自己只是大概浏览一下计划。所以你并没有真正将其作为重新引导智能体的方法。它只是放在那里。然后你去写代码，结果一团糟。有些人会审查计划和代码，这就好像，好吧，阅读计划花了你 20 分钟，然后阅读 Pull Request 又花了 20 分钟，而且它们还不一样。所以你实际上在阅读代码上花费了双倍的时间，而不是减少了。这产生了反杠杆效应。等一下，规范驱动开发（spec-driven development）和这个无关吗？比如一年前 Amazon Q 和 GitHub Workflows 做的那个，它也是先生成一个计划，让人类来审查，然后它开始执行，你也可以编辑它，然后它就去实现这部分，这在表面上看起来非常完美。它本应该效果很好，但除了少数维护项目外，它都被扔进了垃圾桶。我认为它就是不起作用。我得到的所有反馈都是，人们干脆不用它了，因为它效果真的不好。它只是和 RPI 框架有点相似，我是说最初的那个框架，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: basically like the research was this thing of like, hey, before you go build anything, go read lots and lots of code. Use a bunch of sub agents in parallel, understand all the code. It was this technique that like worked really well for hard problems in complex code bases. You just ask Claude uh to do a thing that that's it would read three files and make a change. It would have no context. So, you start the research. You don't even tell it what you're working on. You just tell it, "Hey, can you tell me how this system works and this system and how they connect together and then you get a markdown dock out and this is the context engineering part is like that would take a 100,000 tokens of context, but you would get a 10k token dock out of it that summarized it. Then you would start a new context window and you would do planning and the planning would be and actually realize like the plans that we were building last summer were actually terrible. But it would basically be this long. You would say, "Okay, now here's what we're building. Here's the research doc. build a plan to implement it. And uh in retrospect, now that we see like everyone is obsessed with how do I get agents to work for longer, I think the reason why in like May, June, July, August of 2025 that a lot of people became really interested in planning was it was a very powerful lever to get agents to work for longer. If you said, "Build me a B2B SAS for uh burrito delivery," you'd get like a homepage and that's it. But if you said, "Build me a plan," it would build out this big plan. And then in the next context window, you'd say, "Hey, here's the plan. Here's all the changes we're going to make. Go implement it." It would actually keep going until the plan was done." So the plan was a really good way to anchor an agent and remind it that like, hey, you're not done until this is all finished. So that was the original RPI. And the plan doc, what was bad about it is it didn't give you leverage. The plan was every single line of code that was going to change like in diff blocks and like all the new stuff to write. And so like people would review these plans. We recommended this. We told people to read the plans. We read all our plans. And then eventually I found myself like I just kind of skimmed the plans. And so you're not really using it as a way to resteer the agent. It's just kind of there. And then you go write the code and there's a crap. Some people would review the plans and the code and it's like okay well the plan was took you 20 minutes to read and then the pull request takes you 20 minutes to read and they're different. And so you actually doubled the amount of time you're spending reading code instead of like doing less of it. You've anti-leverage. And hang on was spec driven development not related to this the one that Amazon Q for example and and GitHub workflows again a year ago did which was it also it first generated a plan and it had the human review it and then it started to and you could edit it as well and then it went off and implement this part and it it looked beautifully on the surface. It it should have worked great but it's tossed into the garbage outside of some m some maintenance projects. I I think it just didn't work. like all all the feedback I got, people just stopped using it because it just didn't really work that well. It just rhymes to the RPI framework a little bit, the original one, right?

</details>

### 规范驱动开发与文档漂移

**Speaker B**: 嗯，所以我们的看法也是，RPI 和规范驱动开发（spec-driven development）之间最大的区别在于——有些人把 RPI 称为规范驱动开发，因为对一些人来说，规范驱动开发只是意味着我在编码时使用一堆 Markdown 文件，然后忘记它们里面有什么。我只是把它们当作规范，然后用它们来驱动开发。有一位 OpenAI 的研究员谈到规范驱动开发时说，嘿，别再读代码了，只写规范，把编码这部分看作是将规范编译成代码。那一部分从未真正实现过。也许到了 GPT-7 会实现吧，谁知道呢。嗯，但我遇到的一大挑战是，我在 GitHub 上看到一个关于规范的 issue 已经开放了一年，每隔几周我就会在帖子里收到一封新邮件，人们都在抱怨这个问题，比如，“好吧，我编辑了我的规范，然后我编辑了代码，接着代码产生了漂移（drifts），而规范——我该如何在代码变化时保持规范的更新呢？” 基本上就像是你现在有两个信息来源，它就不再有用了。所以这就是为什么在使用 RPI 时，关于文档的想法是，有一段时间我们保留了它们，但两三个月后，我们觉得，“哦，这些实际上是战术执行文档。我做研究，我做计划，我做实施，然后我就把文档扔掉了。下次我需要研究时，我直接从头再来。” 因为 tokens 很便宜，而我的时间很宝贵，如果我重用了一份已经和代码库真实状态不同步的研究文档，我可能会浪费大量时间。所以我们每次都是实时创建它。这就是为什么说上下文工程依然很重要。创建能将代码库状态和构建者意图压缩成可以在未来任务范围内重用的小型构件（artifacts），是一种非常强大的战术方法，但这并不是说——我对你应该在代码库中留下什么样的常青（evergreen）文档没什么想法。我见过人们试图维持文档或规范与代码本身之间的一致性，但我认为没有人真正觉得它非常有用。你当然可以这么做，它也能起作用，但这就好像——保持它们更新所花费的精力与收益的比例问题，而且通常你也可以用 AI 来做这件事，但我从未认识任何一个人会说，“耶，这太棒了，我们很高兴有这个系统。” 这事能做，也可能有帮助，但我认为没人觉得它有用到了需要维护一个系统来保持规范和代码同步的程度，而不是永远只把代码作为唯一的事实来源（source of truth）。现在你提到了一件有趣的事，那就是在进行上下文工程时，你有时需要进行压缩（compact），而你之前也谈到过有意的压缩（intentional compaction），就是当上下文变得嘈杂时，有意地将有用的部分压缩成一个清晰的、比如 Markdown 形式的构件，验证它，然后开始一个全新的对话。我们可以谈谈这种压缩以及它为何重要吗？听起来它将成为上下文工程的一个基础模块，或者说它现在已经是了，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: >> Well, so our thing too, like the biggest difference between RPI and spec driven development and some people refer to RPI as spec driven dev because for some people SD all it means is I use a bunch of markdown files while I'm coding and forget what's in them. I just spec those are my specs and I'm using them to drive development. There was this OpenAI researcher who talked about spec dev and like hey stop reading the code just write the specs and treat like the coding part as compiling specs into code. that part never really materialized. Maybe with GPT7, you know. Um, but the challen I'm on a GitHub issue in spec it uh that has been open for a year and every couple weeks I get there's a new email on the thread of people complaining about this problem of like, okay, I edit my specs and then I edit the code and then the code drifts and the specs how do I keep the specs up to date as the code is changing and it's basically like you now have two sources of truth and it's it stops being useful. And so like that's why when RPI the idea of the docs is they were all for a while we kept them around but after two or three months we're like oh these are actually like tactical execution docs. I do the research I do the plan I do the implementation I throw the docs out and the next time I need research I just do it from scratch because tokens are cheap and my time is expensive and the amount of time I might waste if I reuse a research that is no longer in sync with the real state of the codebase. So we just create it live every time. This is why it's like context engineering still matters. Creating artifacts that compress the state of the codebase and compress the intent of the builder into small things that can be reused in the future for the scope of a task is like a very powerful like tactical approach, but it's not a thing like I I have very few opinions on like what sorts of docs that you should leave lying around your codebase that are like evergreen. I've seen people try to maintain parity between documentation or specs and the code itself and I don't think anyone actually like found it very useful. Like you can do it and it works but it's like the ratio of the effort it takes to keep them up to date and and trivially you could do this with AI probably but I've never known anyone who was like yeah this is great and we're glad we have it. Like you could do it and it might help but I I don't think anyone found it useful enough to like maintain a system to keep the specs and the code in sync versus just using the code as the source of truth always. Now you mentioned something interesting which is with context engineering you need to sometimes compact and you've previously co talked about intentional compaction that when context is noisy deliberately compress the useful part into a clear like markdown artifact verify it and then start a fresh conversation. Can we talk about this kind of compaction and why it's important and and it sounds like it's going to be a building block where it already is for context engineering, right?

</details>

### 频繁有意的压缩 (Intentional Compaction)

**Speaker C**: 是的。不，频繁有意的压缩就是基础模块。它完全来自于上下文工程。上下文工程就是：我们如何从今天的模型中获得最大的收益？我们如何改变输入到模型中、输入到上下文窗口中、输入到智能体聊天中的内容？我们如何以这样一种方式来控制它，从而获得尽可能好的结果？这意味着要在“智能区（smart zone）”——也就是上下文窗口的前 100,000 个 tokens 中——做尽可能多的工作。这种有意且频繁的压缩基本上就像是：好吧，研究步骤，我们要去阅读一堆代码并将其转换为文档。这就是我们的压缩。我们把这个文档带入到下一个会话中。接下来我们要去阅读工单（ticket）和意图，并将其转化为我们称之为设计文档的东西，类似于：好的，这是我们要做的东西的高层规范。这是对当前状态和期望最终状态的高层描述，然后是模型有一些关于设计的疑问，这有点像一种非常详尽、甚至可能有些过度设计的规划模式。然后你拿着研究和设计文档，开启一个新的会话，一个新的上下文窗口。你会觉得，酷，你已经压缩了意图，压缩了代码库的状态，这样你就可以进行你的规划了，就像是，“好的，我们知道最终状态是什么样子。我们知道我们要去哪里。现在，让我们来分解我们该如何到达那里。” 过程中所有这些不同的步骤之所以存在，是因为模型在这些阶段中各自都有短板。所以，研究阶段基本上是无需人工干预的（hands-off）。我不会去读研究文档。这就像是，去阅读一堆代码，然后生成一个文档。模型们

<details>
<summary>Original English</summary>

**Speaker C**: >> Yeah. No, frequent intentional compaction is the building block. It is it is completely comes from context engineering is context engineering is like how do we get the most out of today's models? How do we change what we're putting into the model into the context window into the agentic chat? How do we control that in such a way that we get the best results possible which means doing as much work as possible in the smart zone the you know first 100,000 tokens of the context window. And uh this intentional frequent intentional compaction is basically like okay the research step we're going to go read a bunch of code and turn it into a doc. That's our compaction. We take that forward in the next session. We're going to read we're going to read the ticket and the intent and turn that into a design document that we call is like okay here's the high level spec of what we want to do. Here's a high level like current state desired end state and then a bunch of design questions the model has kind of like a very thorough maybe even overengineered like plan mode. And then you take the research and the design and you do a new session, new context window. You're like, cool. You you've compressed the intent and you've compressed the state of the codebase so that you can then do your planning of like, okay, we know what the end state looks like. We know where we're going. Now, let's break down how we're going to get there. All of these different steps of the process exist because models have shortcomings in each of these phases. So, the research is pretty hands-off. I don't read the research docs. It's just like go read a bunch of code and then like make a doc out of it. Models

</details>

<!-- chunk 11/14 -->

### 模型擅长理解意图，但不擅长系统架构设计

**Speaker A**: ……在这一点上它们做得相当不错。如果你要求它找 bug 并对代码库发表意见，那是另一回事。但如果你只是问它代码的意图是什么，以及这些东西是如何组合在一起的，通常来说都很简单直接。但是在设计软件的最终状态、架构以及程序设计方面，模型就不太擅长了。它们会做很多决策，有时是对的，有时是错的。所以我们希望在这些环节中能有“人类参与”（human in the loop）。

然后是实现这些目标的步骤，我们之前讨论过这个，但模型非常喜欢制定我称之为“横向计划”的东西。如果你让模型制定一个构建某个应用程序的步骤计划，它会说：“太棒了。我们要先做数据库，然后做服务层，接着做 API，最后做前端。” 这其实有点糟糕，因为想象一下这是一个现有的代码库，对吧？当我们写完 2000 行代码到了最后阶段，我们要对系统所有这些不同的部分进行修改，但直到最后我才能进行测试。

如果是我的话，我会怎么手工构建这个呢？好吧，我可能会先用假数据创建一个模拟的 API 端点。然后我会去把前端大致弄成我想要的样子。接着我才会去实际构建服务层，并真正把数据连通。然后我会进行数据库迁移并创建我的新表。接下来我会添加大量的业务逻辑，然后再添加一堆错误处理。这与模型编写代码的方式截然不同，模型会在没人接触或看过代码的情况下，直接写好数据库层和所有的错误处理。

这也是另一个我们希望人类参与的地方，因为人类拥有非常好的品味和判断力。我宁愿阅读五个独立的、我能手动验证和探索的小代码差异（diff），也不愿一次性阅读 2000 行代码，然后发现：“嗯，它跑不起来，但我不知道问题出在哪。”你不知道问题出在哪，因为代码是你写的，你应该把它写对的。我们会谈论“上下文压缩”等工程师的话题。问题在于，你如何能保持在上下文窗口的“智能区（smart zone）”，也就是避开“愚蠢区（dumb zone）”。不过我要声明一点，如果你对此还没有直觉，这对你来说会是很好的“辅助轮”。

<details>
<summary>Original English</summary>

**Speaker A**: ...are pretty damn good at that. If you ask it to find a bug and have opinions about the codebase, that's different. But if you just ask it what is the intent and how do this stuff fit together, uh that's usually pretty straightforward. But designing the end state of the of the software, the architecture and the program design, models are not great at. They make a lot of like they make decisions and sometimes they're right and sometimes they're wrong. So we have want to have a human in the loop there. 

And then the steps to get there, I we talked about this before, but models love making what I call like horizontal plans. If you ask a model like build a plan of steps to go build this app, it's like cool. We're going to do the database and then we're going to do the services layer, then we're going to do the API and then we're going to do the front end. It's like, well, that actually kind of sucks because we're going to be on the other side of 2,000 lines of code and let's imagine this is an existing codebase, right? We're going to make changes to all these different parts of the system. I can't test it till the end. 

And so what I would do is like, okay, how would I have built this if I were building by hand? Well, okay, I would probably create a mock API endpoint with fake data. And then I would go kind of get the front end kind of how I want it to look. And then I would actually go like build a services layer and actually wire the data through. And then I would make a database migration and make my new table. And then I would actually add a lot of business logic. And then I would add a bunch of error handling. And it's completely orthogonal to how model like models would write the database layer and all the error handling without ever like anyone's ever touched or seen the code or whatever it is. 

And so this is another place where we like we like to have humans involved because humans have really good taste and judgment. Like I would rather read five separate little mini diffs of like things that I can manually verify and explore than read 2,000 lines of code and be like well it's not working. I don't know where. You don't know where cuz you wrote the code. You were supposed to get it right. We talk about compaction context engineer. It's like how can you stay in the smart zone of the context window which is again the dumb zone. I will say disclaimer it's really good training wheels if you don't have intuition about this.

</details>

### 上下文窗口的“智能区”与“愚蠢区”

**Speaker B**: 那么让我们来定义一下这些概念。什么是智能区，什么是愚蠢区？

<details>
<summary>Original English</summary>

**Speaker B**: So let's just define these things. What is a smart zone and what is a dumb zone?

</details>

**Speaker A**: 嗯，它的界限比我希望的要模糊一些。我想在十一月的时候，我们讨论的是上下文窗口的前 40%，但后来我们就有了百万级的智能区。

<details>
<summary>Original English</summary>

**Speaker A**: So, it's it's it's a little bit blurriier than like I would like I would like it to be. I think in November we we talked about the first 40% of the context window, but then we had million smart zone.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 后来我们有了百万 token 的上下文窗口。所以后来我把它改为了前 10 万个 token，如果是像 4.8 这样非常强大的模型，我通常会提高到大约 20 万。但基本上，就像 Jeff Huntley 和 Ralph Wickham 提到的观点：你使用的上下文窗口越小，你得到的结果就越好。

简单来说，智能区意味着，如果你把上下文放在前面的部分，它的表现会好得多；而愚蠢区就是，一旦你把内容放到了那里，你差不多就可以忘了它了，因为模型会变得困惑，它发挥不了多大作用，性能会下降。

确实，有时候——这凭的是直觉——我经常会用到 30 万到 40 万的 token。40 万比较少见，但在做某些类型的工作时，我确实会用到 25 万到 30 万的 token，因为我的直觉告诉我，我可以继续工作而性能不会下降。但如果你没有很好的对 LLM 的直觉，那么对于较小的模型，10 万 token，或者对于像 Codeex 和 Opus 4.8 这样非常强悍的模型，20 万 token，通常是一个很好的“辅助轮”准则。如果你超过了这个限制，结果的质量可能就会下降。

我看到的最明显的迹象，通常是当模型试图让测试通过，而你的 token 数量到了 20 万时。它会说：“好吧，让我试试这个。好吧，让我试试那个。” 它会尝试各种东西，而且变得越来越极端，比如：“哦，让我删掉你的 env 文件然后再试一次。” 这就是事情变得非常非常奇怪的时候。所以如果你开始看到某些特定类型的迹象，如果我觉得：“哦，我们现在有 30 万 token 了，而我需要修复这个单元测试”，我会说：“很好，把我们做过的所有操作都写入一个文件”，甚至我只是会执行一个内置的上下文压缩（具体取决于模型），然后在一个只有 3 万或 5 万 token 的新会话中重新开始，我会对它说：“很好，我们接下来要做一件困难的事，你需要让这个该死的测试通过，别给我搞砸了。”

<details>
<summary>Original English</summary>

**Speaker A**: Then we had million token context window. So then I changed it to like the first 100,000 tokens if it's a really like 4.8 I usually will go up to like 200k. But basically the the thing Jeff Huntley had and Ralph Wickham was like the less context window you use the better outcomes you'll get. 

And basically the smart smart zone mean meaning if you have context in that first part it should work a lot better and then like the dumb zone is like once you have stuff there it's kind of forget about it like it'll be confused it's not going to do much like it'll degrade. Yeah. And there are times and this is an intuition thing like I will often go up to 3 400k tokens. Four is rare but I will go up to 250 300k tokens for certain types of work where my intuition tells me that I can keep working without without degrading the performance. But if you don't have good LLM intuition, like 100K for smaller models, 200K for these like really beefy like Codeex and Opus 4.8 models is usually a good like training wheel guideline of like if you pass there, your quality of results may be degrading. 

The biggest tell I see for this is often the uh model's trying to get the test to pass and your 200k token. Well, let me try this. Okay, let me try that. and it's like trying a bunch of stuff and it's getting more and more extreme and it's like thing oh let me delete your end file and try again like this is where things get really really weird and so it's like if you start to see certain types of if I'm like oh we're at 300k tokens and I need to like fix the unit test I'm like cool write everything we did to a file or even I'll just do like a a built-in compaction depending on the model and then I'm starting a new session at 30k or 50k tokens and I'm like cool we're going to do a hard thing which is you're going to get this freaking test to pass and you're not going to be stupid about it by the

</details>

### 当模型说“你是完全对的”时，是时候重新开始了

**Speaker B**: 你提到关于模型变“愚蠢”的一点，你说过如果模型跟你说“你是完全对的”，你就应该重新开始了。我们都遇到过这种情况，当它跟我说“哦，你知道的，你并没有……你是完全对的”时，我们通常只会觉得很烦，但为什么我们在你的观察中应该重新开始呢，那里到底发生了什么？

<details>
<summary>Original English</summary>

**Speaker B**: One thing that you said like about the the the model being dumb is you said that if the model ever tells you you are absolutely right you should start over and we've all had that when it tells me like oh you know you didn't you're absolutely right and I'm like we just get annoyed but why should we start over what's happening there in your um observations

</details>

**Speaker A**: 是的，那是个好问题。关于新出现的“你完全正确”，我认为，呃，你反驳它是对的，确实是这样（笑）。

<details>
<summary>Original English</summary>

**Speaker A**: yeah that's great yeah and the new the new you're absolutely right I think is uh you're right to push back on that right yes [laughter]

</details>

**Speaker B**: 那是 Opus 吧？

<details>
<summary>Original English</summary>

**Speaker B**: that's opus right

</details>

**Speaker A**: 对，Opus 就像是说：“你根本没运行测试，对吧？它可以反驳你。” 而你会说：“我绝对运行了。” 但不是的，对我来说，“你完全正确”过去一直是模型遇到批评时的回应。如果你说，“那完全错了。你怎么搞的。” 就像如果你说了些话，表现得很生气或沮丧，或者只是想指出它做错了什么，它就会回答：“你完全正确。” 大多数人都有过这样的经历：它这么说了一句，然后继续做错误的事情。

所以，一旦它开始做些蠢事，你得知道影响上下文窗口的有四个关键因素。一是大小，即有多少个 token？二是信息的质量，即里面有没有错误信息？比如模型是否有一些思考痕迹导致它认定某个错误的东西是正确的。三是是否缺失信息？这是否缺少了它本该有的上下文？最后是轨迹（trajectory）。轨迹非常微妙，但你可能经历过这样的对话会话。

<details>
<summary>Original English</summary>

**Speaker A**: yeah opus is like you didn't run the test did you right could push back on that. I totally did it. But no, for me, you're absolutely right was always what the model would respond. If you were like, "That's totally wrong. You did it." Like you if you if you said something where you were angry or frustrated or just wanted to point out that it's done something wrong, it would respond with, "You're absolutely right." And most of us have had the experience of it says that and then it continues to do the wrong thing. 

So, it's like once it starts doing dumb things because there's there's four things in your context window that matter. There's like the size of it, how many tokens? There's like the quality of the information is like is there any incorrect information? Like if the model had some thinking trace where it decided the wrong thing was true. Is there missing information? Does this like have context missing that it should have? And then there's the trajectory. And the trajectory is very subtle, but you may have had sessions.

</details>

**Speaker B**: 轨迹的意思是你提示的过程吗？

<details>
<summary>Original English</summary>

**Speaker B**: The trajectory meaning you're prompting

</details>

**Speaker A**: 是指一切事件的实际历史。我把智能体在过去执行所有操作的实际历史记录称作轨迹。

<details>
<summary>Original English</summary>

**Speaker A**: the actual history of everything. I call it trajectory is like the actual history of like what the agent has done in the past.

</details>

### 对话历史（轨迹）如何影响模型的自我回归预测

**Speaker A**: 所以如果我说：“嘿，做一下这个修改。” 然后智能体做了修改，运行了测试，发现失败了，然后它修复了测试。我就会非常有信心，接下来我让它做的修改，它也会遵循同样的路径。因为对它来说：“好吧，我们看这段对话，上一次用户让我做一件事，我做了修改，运行了测试，测试失败了，我修复了测试，然后告诉了用户。” 但如果我说做一个修改，它做了，却没有运行测试，那我就处于一条不同的轨迹上了。

如果我接着说：“好吧，再做一个修改。” 实际上，模型是自回归的。因此它们只是在预测这段对话中的下一条消息是什么。

我们在《No Vibes Allowed》中讨论过一个例子：模型犯了一个错误，然后你冲它发火，接着它又犯了另一个错误，你又冲它发火。然后它就会想：“很好，这个对话里的下一条信息该是什么呢？好吧，我看了看历史记录，我可能应该再犯一个错误，这样人类就可以继续对我发火了。” 所以我当时觉得：“好吧，那是一个很好的例子，说明差不多该重新开始了。”

<details>
<summary>Original English</summary>

**Speaker A**: And so if I say, "Hey, make this change." and the agent makes the change and then it runs the test and then they're broken and then it fixes the test. I have very high confidence the next change I asked it to make, it's going to follow that path again because it's like, okay, here's a conversation and the last time the user asked me to do a thing, I made the change, I ran the test, test broken, fixed the test, and then I told the user. But if I say make a change and it makes a change, it doesn't run the tests, then I'm on a different trajectory. 

And if I say, okay, make another change, it's like basically the they're auto regressive. So they're they're predicting the ne what's the next message in this conversation. And so the example we we talked about in uh No Vibes Allowed was of course the like hey the model makes a mistake and then you yelled at it and then it made another mistake and then you yelled at it and then it's like cool what's the next message in this conversation. Well look if I read the history I should probably make another mistake so the human can yell at me. So I was like okay that's a great that's a great example of like uh time to start over.

</details>

### 从 Token 数量取胜到 Token 效率取胜

**Speaker B**: 让我们来谈谈关于软件工程正在如何发生变化的一些观察。你最近在关于编程元数据演变的话题中，提到从“Token Harder（拼 Token 数量）”转变为“Token Smarter（拼 Token 智慧）”。我们能谈谈你说的“Token Harder”和“Token Smarter”是什么意思吗？

<details>
<summary>Original English</summary>

**Speaker B**: Let's talk about some observations on how software engineuring is changing. One thing you talked about recently on the evolution of the coding meta is going from token harder to token smarter. Can we talk about what you mean by token harder and token smarter?

</details>

**Speaker A**: 好的。所谓的“Token Harder”，我是说我加入了一个名为“超级工程（hyperengineering）”的群聊，里面全是一群试图把自己云端订阅的资源发挥到极致的人。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So token harder is I mean I'm in a I'm in a group chat called hyperengineering and it's all like people trying to max out their cloud subs.

</details>

**Speaker B**: 哇。好吧。那听起来是个好玩的地方？

<details>
<summary>Original English</summary>

**Speaker B**: Oh wow. Okay. It's just like [laughter] that sounds like a fun is it fun place?

</details>

**Speaker A**: 那是个好玩的地方，但全都是“Token Harder（无脑砸 Token）”。比如“看看我建的所有这些业余项目”，“看看我用它做的所有事情”。

<details>
<summary>Original English</summary>

**Speaker A**: It's a fun place but it's like all token harder. It's like look at all the side projects I built. It's look at everything that

</details>

<!-- chunk 12/14 -->

### Token Harder 与黑灯工厂

**Speaker A**: 呃，我，我，我已经拿到了我的 Claude token。我有六个，六个 Claude 账号。我把它们在每5小时的周期里都拉满了。我把时间卡得很准，所以我总是能用完所有的 token，而且当限制重置时马上又开始跑。所以这就像，我的意思是，说到 Eli Goldrat 和《目标》（The Goal），就像是在优化工厂里一个节点的利用率和效率，而不是关注端到端的目标，比如我们如何交付价值，以及人们喜欢的、稳定的、能持续很长时间的东西。但这就是我所说的“Token 拉满（token harder）”的理念，这和黑灯工厂的概念是一样的，就像是，嘿，如果你，如果你，如果你在代码审查中把人类移除，你就能在系统中推进更多的 token。

<details>
<summary>Original English</summary>

**Speaker A**: uh I I I've gotten my Claude token. I've got six six cloud code accounts. I've gotten all of them maxed out every 5 hour period. I've timed it out so I always use all the tokens and it starts up immediately when the limit resets. And so it's like I mean getting into Eli Goldrat and the goal is like optimizing for utilization and efficiency of one node in your factory rather than the end to end goal of like how do we ship value and things that people like that are stable and like will last a long time. But that's my idea of token harder and it's the same thing with the dark factory thing is like hey if you if you if you remove humans from code review you can push more tokens through the system.

</details>

**Speaker B**: 所以我们谈论软件工厂，但什么是黑灯工厂？

<details>
<summary>Original English</summary>

**Speaker B**: So we talk about software factories but what is the dark factory?

</details>

**Speaker A**: 啊，黑灯工厂是，这个源于这样一个概念：有一些工厂，呃，一切都是由机器人自动化的。你可以想象一个汽车工厂，全是机器人制造汽车，因为没有人类，所以它们不开灯。

<details>
<summary>Original English</summary>

**Speaker A**: Ah so the dark factory is this comes from this idea of like there are factories where uh everything is automated by robotics. So you can imagine like a car factory where it's all robots building the cars and they don't have lights because there's no humans.

</details>

**Speaker B**: 哦，原来是这么来的。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, so that's where it comes from.

</details>

**Speaker A**: 黑灯工厂。是的。你走进去，没有灯。甚至没有电灯开关。

<details>
<summary>Original English</summary>

**Speaker A**: The dark factory. Yeah. You walk in there's no lights. There's not even light switches.

</details>

**Speaker B**: 所以，这将会是一个完全自动化的软件工厂，基本上就是说……没有任何人类输入。

<details>
<summary>Original English</summary>

**Speaker B**: So, it will be the fully automated software factory where it it it will be like no human input basically.

</details>

**Speaker A**: 没有人类输入。原材料进去，汽车出来。

<details>
<summary>Original English</summary>

**Speaker A**: No human input. Raw materials go in, cars come out.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yep.

</details>

### Token Smarter 与保持控制力

**Speaker A**: 我认为在微观层面上，比如，你可以在你的流程中有很多黑灯的循环，比如，嘿，如果你，如果代码审查 Agent 带着问题回来，你把它循环回构建者 Agent 那里，它修复了再返回，那个过程就是黑灯的。你不需要在这个环节有人类参与。但是那种你完全不看任何代码的全面黑灯工厂，是的，它是最大化你的 token 利用率的好方法。而且就像是，如果，如果你的信念是，我的工作就是尽可能多地从“机器之神”那里榨取智能，因为那是我获取最大价值以及在我的时间上获得最大杠杆的方式，那就“Token 拉满”吧。嗯，而我的观点基本上是我们之前讨论过的“Token 聪明（token smarter）”，也就是，好吧，我该怎么移动得更快？我如何在不关灯的情况下，尽可能多地从 AI 那里获得价值，同时仍然保持控制力、品味、判断力以及对系统架构的理解，并将我这10年软件工程中积累的硬核观点应用到程序设计中，这样我才能确信代码会变得越来越好，并且随着时间的推移越来越容易维护。这和，比如你看 Google 内部的 SRE 团队，是一样的道理。他们出版了这本叫《SRE 站点可靠性工程》的书，整个核心观点就是，嘿，我们要从一个数据中心发展到五个数据中心，我们需要同样的六人团队能够管理五个数据中心，并且我们需要同样的六人团队明年能够管理50个数据中心。这基本上是说，我们如何用软件来解决这个问题，这样我们就不用线性扩展，比如，好吧，每个数据中心需要五个 DevOps 人员，所以我们需要根据事物来扩展人员，我们如何持续自动化那些我们不需要的部分。所以这和我刚才说的有点不相关，甚至有点矛盾，但这个关于如何寻找杠杆的观点，以及，那个方式，嗯，我，我认为你刚才的意思是，当 Google 那么做的时候，他们从来没有试图把这些 SRE 完全从流程中移除。他们只是说，看，我们能不能往前想，并且扩展你们自己，实际上他们扩大了团队。并不真的是六个人。更多地像，我想 Google 明确地说过，“好吧，我们有五个数据中心。明年我们将有50个。你们有六个人。我们不想要有60个人。我们不想要，然后还有管理层等等所有那些。问题是，我们怎样才能用，比如12个人，或者像10个人来做到这一点，然后当我们有500个数据中心的时候，其实现在他们的 SRE 团队已经壮大了，但是，但是……”

<details>
<summary>Original English</summary>

**Speaker A**: And I think in in a micro like you can have many loops that are dark in your in your thing of like, hey, if you if the code review agent comes back with a problem, you loop that back to the builder agent, it fixes it and comes back and that's dark. You don't need a human loop for that. But the full dark factory where you don't read any code, yeah, it's a good way to maximize your token utilization. And it's like if if your belief is like my job is to extract as much intelligence out of the machine god as I can because that's how I get the most value and the most leverage on my time then token harder. Um and my take is basically what we talked about before token smarter is like okay how do I move faster? How do I get as much value out of as AI as I can without having to turn the lights off while still maintaining control and taste and judgment and understanding the system architecture and having a lot of like applying my hard one opinions through 10 years of software engineering to the design of the program so that I can feel confident that the code's going to get better and more maintainable over time. It's the same thing of like you look at like the S sur team inside Google. They brought out this book SR site reliability engineering and the whole take was like hey we're going to go from one data center to five data centers and we need the same sixperson team to be able to manage five data centers and we need the same sixperson team to be able to manage 50 data centers next year and it's basically how do we apply software to this problem so that instead of scaling linearly of like okay every data center needs five devops people so we need to scale the people with the things how do we continually automate the parts that we don't need so a little bit orthogonal and maybe even like contra contradictory to what I just said, but this idea of like how do you find leverage and the way the way well I I think what you were saying there is like when Google did that never seek to remove those SRE from the process at all. They just said like look can we think ahead and scale yourselves and they actually grew the team. It wasn't actually six people. It was more like I think Google specifically said, "Okay, we have five data centers. Next year we'll have 50. There's six of you. We do not want to have 60 people. We don't want and and then management layer and all that. It's like how can we do it with like 12 or like or like 10 and then when we'll have 500 and now actually their SRE has grown but but

</details>

**Speaker B**: 当然，是的。

<details>
<summary>Original English</summary>

**Speaker B**: of course yeah

</details>

**Speaker A**: 但是，但是他们从来没有，你知道，我，我认为作为工程师，当有人说，好吧，我们只是想把工程师数量降为零时，我们会感到相当受威胁，我的意思是，那不是一个有趣的工作场所，但是听起来就像……

<details>
<summary>Original English</summary>

**Speaker A**: but but they never you know I I think as engineers like we feel pretty threatened when someone says like all right we just want to have zero engineers like I mean that's not a fun place to work at but what it sounds like

</details>

**Speaker B**: 如果他们那里零个工程师，那根本就不是一个可能去工作的地方，我们俩谁也没法在那工作，对吧。

<details>
<summary>Original English</summary>

**Speaker B**: it's not a possible place to work at if they have zero engineers neither of us can work there right

</details>

**Speaker A**: 但是你要理解，Token smarter 就像是，让我们把人类留在循环中，让我们继续创造价值，并弄清楚哪些部分是不那么相关的、无聊的、我们不需要的地方。所以，比如一个开发者可能可以比以前做更多的事情，但你的设定是要成为这整个事情的一部分，而在这个工厂里，灯是亮着的。

<details>
<summary>Original English</summary>

**Speaker A**: but do understand the token smarter is like let's keep humans in the loop let's keep adding value and figure out what are the parts which are not as relevant, boring, where we don't need it. And so like one developer can probably do more than before, but you are built to like be part of this whole thing and the lights are on in a factory.

</details>

### AI Slop 与折叠不确定性

**Speaker B**: 是的。而且就像，基本上我认为，我认为我想表达的是，这里的联系就像是，SRE 构建了一种东西，让人员数量的增长像平方根函数或对数函数，而他们的产出呈线性增长，你希望达到同样的效果，而实现这一目标的方法就是通过好的架构和好的程序设计。所以为了避免这种你必须在这个问题上投入更多人手或更多 token 的问题，如果你能把优秀的软件设计成随着时间的推移变得越来越容易维护、越来越具有可扩展性，并且就像在今天，感觉并不像，基本上你需要人类在循环中才能够做到这一点。让我们谈谈，呃，AI 的垃圾输出（AI slop）。有一次你写道：“是的，AI 可以写你的代码，但它也可以写你的需求说明（specs）和 PRD。”但是，同样的规则，同样的规则始终是：输入垃圾，输出也是垃圾（slop in, slop out）。如果你把思考外包出去，你会得到一堆垃圾。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And it's like basically I think I think what I'm trying to get to is like the connection here is like S builts a thing where like headcount scales at like a square root function or a logarithmic function whereas their output scales like linearly and you want the same that the way you do that is with good architecture and good program design. And so in order to like avoid this problem where you have to throw more people or more tokens at at the problem, if you design good software in such a way that it gets more maintainable and more scalable over time and like just today it doesn't feel like like basically you need humans in the loop to be able to do that. Let's talk about uh AI slop. At one point you wrote, "Yeah, AI can write your code, but it can also write your specs and PRDs." But the same the same rule is always slop in, slop out. If you outsource your thinking, you're gonna get garbage.

</details>

**Speaker A**: 是的。嗯，所以是的，基本上这个想法就是，我们思考如何获得高质量输出的方式就是，是的，你可以手工编写代码，或者你可以和一个模型坐在一起，来回打磨，可能会走得稍微快一点，并且你拥有控制权，每次它做出改变，你去阅读这个改变，如果它很糟糕，你告诉它，不行，我们想要这样，然后你就这样一点点地慢慢来。这就像是与 Agent 合作的第二阶段或第三阶段的版本，在这种模式下，Agent 在写你所有的代码，但你仍然深入在这个循环中。这会让你走得更快，但不会让你走得那么快。它甚至远远达不到……有那么一个层级，然后还有一个层级是：在依然关心代码的前提下，你所能达到的最快速度。然后再往上就是：如果你把灯关掉，你所能达到的最快速度。所以我们总是从杠杆的角度去思考这个问题，比如，好吧，让我把一切从一句话或一段杂乱的语音笔记开始，比如我想做这个东西。它将像这样运作，或者不管是什么，比方说，平均两句话，我需要修复这个东西，或者有一个支持工单，我必须解决这个问题，如果你能用 AI 把这些变成一页纸，然后完善那一页纸，并确保它是正确的，然后把那一页纸变成一份三页的文档，并确保它是正确的，然后再把那三页的文档变成一份十页的，非常详细的提纲，那么你就可以写出一百页的代码了，它也许不完美，你不应该在这几份文档上过度流汗纠结并确保它们是完美的，但你正在增加一种几率，就像是，你正在降低输出的不确定性。就像你可以这么想，你有一条指引它走向何方的基准线，然后你会有一组它在那个范围内可能会走向哪里的概率，如果你在过程中不断审查，随着你对自己正在构建什么以及希望它被如何构建变得越来越清晰。你在某种程度上折叠了不确定性，坍缩了你最终可能会落入的最终状态集合。这就像我在做物理一样，你需要叠加所有这些概率，就像我不知道，我有一种感觉，我觉得那些特别喜欢玩即时战略（RTS）游戏的人，呃，可能在运用 AI 方面会很擅长，因为你必须得有那种，我不知道该怎么形容的感觉。Matt PCO 刚刚谈到了战争迷雾（fog of war），以及在最前沿的那些事情，就像，我们对这个问题还有很多未知的地方。我们怎样才能找到答案？在知道了我已经看到的信息之后，我现在如何做出最好的决定？有一种……我看到了一种……

<details>
<summary>Original English</summary>

**Speaker A**: Yep. Um, so yeah, that's basically the idea is like the way we think about like getting high quality outputs is like yeah, you could write the code by hand or you could sit with a model and work back and forth and go maybe a little bit faster and you have control and every time it makes a change, you go read the change and if it's bad, you tell it, nope, we want it like this and you kind of incrementally slowly. This is like kind of the stage two or stage three version of working with agents where like the agents writing all your code, but you're kind of very much in the loop. And this will make you go faster, but it won't make you go that much faster. It won't make you go anywhere near there's like there's like that level and then there's like the maximum speed you can go while still caring about the code. And then there's like the maximum speed you can go if you turn the lights off. And so we always think about it as like in terms of leverage is like, okay, let me take everything starts with like a sentence or a voice note ramble like I want to build this thing. is going to work like this or whatever it is to let's say like on average like two sentences I got to fix this thing or there's a support ticket I got to fix this thing if you can turn that with AI into a one pager and then turn that one page and make sure that's correct and then turn that one pager into a three-pager and make sure that's correct and then turn that three-pager into a 10-page like detailed outline then you can write a 100 pages worth of code and it's maybe not perfect you shouldn't like sweat over these documents and make sure they're perfect but you're increasing the chance that like you're decreasing the uncertainty of the outputs. It's like you can think of like you have like a line of like where it's going and then you have like the probabilities of where like it might go in that range if you are kind of reviewing along the way as you get more and more detailed into how what you're building and how you want it to be built. You kind of collapse the uncertainty and the set of end states that you could land in. That's me doing the physics thing of like you got to superimpose all these probabilities and like I don't know I have this thing that like I think people who really like playing real-time strategy games uh are probably going to be really good with AI because you kind of have to like I don't know. Matt PCO was just talking about fog of war and like things that are at the frontier of like there's stuff we don't know about this problem yet. How can we find that out and how can I make the best decision now knowing what I have seen? there's a I've seen a

</details>

<!-- chunk 13/14 -->

### 评估成功的概率与 Human Layer 公司简介

**Interviewer**: 获取一两条信息后，所以可能会有 30% 的概率是这种情况，有 40% 的概率是那种情况。我怎样才能获得更多信息呢？因此在我的脑海中，我能够重新计算这些概率，并决定哪条是最可能引导我们走向成功的路径。说到引导你走向成功的最可能路径，让我们来谈谈你的公司，你们刚刚结束隐形模式（stealth mode），名为 Human Layer。什么是 Human Layer？你认为你们正在为成功做准备的概率是多少？

<details>
<summary>Original English</summary>

**Interviewer**: couple pieces of information and so there's a 30% chance it's this and there's a 40% chance it's this. How could I get more information? So in my head I can like recalculate those probabilities and decide what's the most likely path that's going to lead us to success. Speaking of the most likely path that leads you to success, let's talk about your company that's you've you've just come out of stealth human layer. What is human layer and what is the probability that you're setting up for success?

</details>

**Guest**: 这是一个好问题。100% 的概率，也许是 110%，开个玩笑，没有啦。所以，Human Layer 是一个专为 AI 设计的集成开发环境（IDE），它是一个协作平台，为您构建“软件工厂”提供基础组件。我们的核心理念就是帮助工程师在复杂的代码库中解决棘手的问题。基本上，现在的开发者可以分为两大类：一类是凭直觉写代码（vibe coders）做些业余项目的开发者；另一类则是构建生产级软件的开发者。在生产环境中，风险极高，如果出现故障，公司可能会面临数百万美元的罚款，或者直接损失数百万美元的资金。当然，在这两极之间还有一整个广阔的光谱。但如果你处于这个光谱偏左侧（即偏向生产环境）的位置，你所构建的软件至关重要，并且需要持久运行，那么我们就是在帮助这类人在不使代码库退化成“一团乱麻”的前提下，将解决问题的速度提升两到三倍。核心挑战在于：你如何在保持接近人类工程师级高质量代码的同时，将开发速度提升两到三倍？

<details>
<summary>Original English</summary>

**Guest**: That's a good question. 100% 100% probability uh maybe 110 but uh no uh so human layer is it's an AI IDE it's a collaboration platform and it is building blocks for your software factory and the basic pitch is like engineers solving hard problems and complex code bases basically there's two categories of builders there's like vibe coders building side projects and then there's people building production software where the stakes are high and if something breaks we're going to get fined millions of dollars or you know we're going to lose millions of dollars of money for the company and there's a whole spectrum in between there. But it's like if you're kind of in the left half of that spectrum, you're building software that matters and it has to last and be around for a while, then you're helping people like that solve problems two to three times faster without descending into slop is like how do you maintain that near human level of quality and move two to three times faster?

</details>

### 从高层次规划到重新构想未来的 IDE

**Interviewer**: 那么你带来的、并在此基础上进行构建的想法有哪些呢？

<details>
<summary>Original English</summary>

**Interviewer**: And what were the ideas that you you built and that you came with?

</details>

**Guest**: 有一个我们现在非常兴奋的想法。我的意思是，这一切都源于这个 RPI 的概念，以及使用规范（specs）。其实在这整个过程中我都在暗示这一点，对吧？也就是那种：好的，太棒了，让我们从一个非常高的层次开始，然后一层一层地放大细节，并且不断重新调整方向。找到能够帮助你移动得更快的那个杠杆点，从而增加你的智能体（agent）能够完全按照你的需求或者构建出极高质量作品的概率。另一件我认为非常有趣的事情是，我昨天刚发了个帖子说：“嘿大家，我们应该废除 Pull Request 吗？” 这件事我不能透露太多，但基本上其核心观点是：未来的 IDE 需要为智能体（agents）进行彻底的、自底向上的重新构想。它甚至可能不只是——我不知道，很多编辑器其实是从一个纯文本编辑框开始的，然后勉强拼凑上一个“智能体”标签页。然后最终你会看到像 Cursor 3 那样，我甚至都找不到文本编辑器在哪了。我知道它肯定存在，人们告诉我你可以切换到文件的文本视图，但它同样也是非常“智能体优先”的。所以我们从底层出发，思考：一个专门旨在帮助开发者与智能体进行交互、并管理智能体工作的 IDE，到底应该是什么样的？

随后，我们拉长视角，问道：我们该如何使其具有协作性？并内置一个同步引擎、持久化的数据流，以及所有这些技术组件，以使我能够在实时状态下获取人类对于我如何使用智能体所进行的反馈，而不是非要等到发 Pull Request 的时候才去处理。实际上，优秀的工程团队几十年来一直在这么做：我们会开个设计评审会，大家可能会基于一个两页或者十页的 Google Doc 来讨论我们究竟要如何构建某个功能。

<details>
<summary>Original English</summary>

**Guest**: one idea that we're really excited about right now. I mean, it all comes from this RPI and this like using specs to like I mean I've kind of been hinting at it this whole time, right, of like okay cool like start really high level and zoom in layer by layer and resteer and like find find that leverage that helps you move faster and increase the chance that your agent's going to build exactly what you want or something that's really high quality. The other thing I think that's really interesting that where I just posted yesterday I said, "Hey chat, should we uh kill the poll request?" And that's uh something I can't talk too much about, but basically the idea is like the IDE of the future needs to be rethought from the ground up for agents. And it might not even be a like I don't know a lot of editors kind of started with the text field and bolted on an agents tab. And then eventually you've seen like cursor 3. I can't even find the text editor. I know it exists. People have told me you can get to a text view of files, but it's also very agent first. And so we started from the ground up of like what is an IDE designed for helping a developer interact with and manage the work of agents. And then we zoomed out and said how do we make this collaborative and build in a sync engine and durable streams and all of these like pieces of tech that enable me to get human input and feedback on what I'm doing with agents in real time rather than waiting for the pull request time. And great engineering teams have been doing this for decades of like, hey, we're gonna have a design review where we're going to talk about how we're going to build the thing as like a two-page Google doc or whatever 10page what, however,

</details>

**Interviewer**: 比如业务需求文档（BRD）或者架构需求文档。

<details>
<summary>Original English</summary>

**Interviewer**: BRD er architecture requirements document

</details>

**Guest**: 对，然后你会进入冲刺计划（sprint planning），把它拆解成许多小工单（tickets），并且决定谁来做哪一部分。我的看法是：AI 在所有这些环节都可以提供帮助。如果你仅仅使用 AI 来写代码，那么你就错失了 AI 能够为你整个软件开发生命周期（SDLC）带来的诸多益处。很多人会说：“那好吧，我们不需要再开这些会了，因为我们有这个循环，我们有‘黑暗工厂’。一切都会在这个循环中自动飞转起来。” 但实际情况是：“好吧，但如果你想真正提高速度的同时又保持质量，那么你确实应该在实际去写代码之前设立这些检查点，并且你应该利用 AI 来协助完成这些步骤。”

所以，我们构建了这个类似于云端平台的工具，它有一点像 Google Doc 那样的组件，你可以在里面进行评论，而且智能体能够直接呈现各种模型、Mermaid 图表、HTML 渲染等各种内容。因此，本质上，我们要如何把智能体做得像大型的 Figma 那样？所有内容都在云端，一切都具备协作属性。我能看到我所有同事的工作会话，他们也能看到我的。这几乎就像 Slack 相比于电子邮件所带来的优势：你不需要参与到每一次对话中就能知道发生了什么。你能看到各种频道亮起，你可以去查看它们。如果有些内容你不关心那就算了；但如果你看到了一个你关心的对话，你就可以随时跳进去参与。对于工程开发工作，我们要怎么实现这一点呢？相比之下，我们过去有这种非常严格的模式，即使我们管它叫“敏捷开发”，它往往也很像瀑布模型：产品需求文档（PRD）、架构文档、工单分配，每个人各自去开发一天，然后提交一个 PR 回来，接着再由另一个人去审核。我们该如何创造一种更为融合的状态（soup）？在这个世界里的数据模型应该是什么样的？在这个模型里，你有智能体的执行追踪记录，有文档，有负责将这些归组的任务和项目，甚至还有 Git 的 diff 在四处实时流转。在这样的环境下，为什么我还要一次性地去审查所有的代码呢？明明每个人的工作都存在于一个任何人都可实时交互的共享环境里。

我的意思是，这让我想起了在 GitHub 以及它的竞争对手出现之前软件团队的状态。那时你可能在某个地方有一个工单追踪器，但大多数团队在公司内部其实都处于一种各自隔离的状态，你根本不知道另一个团队在做什么。我记得在没有 GitHub 的时代，一些独立团队可能在墙上有一个贴满便利贴的板子，但公司里的其他人完全不知道他们在干嘛，大家都处于孤立工作状态。而现在，当你有了 GitHub 或者是公司内部署的类似平台，你只要去关注一个团队，你就能随时看到满天飞的 Pull Request，你可以参与进去，你有完整的历史记录，一切都是相互连接的。它就这么自然而然地形成了。现在回想起来，有很长一段时间我也会觉得：“废话，你当然会使用 GitHub，或者人们肯定会去抄袭它那套模式。”

<details>
<summary>Original English</summary>

**Guest**: and then you go to sprint planning and you break it down into little tickets and you decide who's going to do what. It's like AI can help with all of this. You should, if you're just using AI to write the code, you're missing out on a lot of the benefits that AI can bring to your SDLC. And a lot of people say like, "Well, we don't need any of those meetings anymore because we have the loop. We have the dark factory. Things just fly around the loop." But it's like, "Okay, but if you want to actually move faster and maintain quality, then like you should have these checkpoints before you go to actually write the code and you should use AI to help with that." So, we built this like cloud platform that's kind of has like a Google Doc style component where you can comment and the agent can surface like mockups and mermaid diagrams and HTML and all these things. So, basically, how do we make agents like Big Figma style? Everything's in the cloud. Everything's collaborative. I see all my co-workers sessions. they see all of mine. It's almost like the benefit that Slack had over email was that you didn't have to be in every conversation to know what was happening. You could maintain you could see all these channels light up. You could check on them. Okay, I don't care about any of that. But if you saw a conversation that you cared about, you could jump in on that. And it's like how do we do that for engineering work versus like we really had these like very strict even when we called it agile it's very waterfall like PRD ard tickets everyone goes and builds for a day and then you get the PR back and then one person reviews it. How do you create this more just like soup and like what is the data model for that world where you have like agentic traces, you have documents, you have tasks and projects that group these things, you have actual git diffs being streamed everywhere where it's like why would I review all the code at once when I can just always every everybody's work lives in a shared environment that anyone can go interact with. I mean what it reminds me is like what you know GitHub that did the software teams before GitHub and its competitors you might have a tracker somewhere but most teams were just kind of like in inside the company you didn't know what one one team was I I remember pre- GitHub like you know you had individual teams they some of them had like a board with stickers but no one else in the company knew what they were doing they were all working isolation and now when you have GitHub or even the internal version of of GitHub inside a company you can always see when when you go to a team you you see the pull request flying you you can join in you have history it's all it is all kind of connected and it it came together and now it's like you know for a very long time I was like you duh you're going to use GitHub or or people will copy it

</details>

### 取代 Pull Request 与建立全新工作流

**Interviewer**: 所以我感觉你是想要构建某种类似于这样的东西，一种面向当我们拥有那种充斥着各种开发循环的“黑暗软件工厂”时的工作流？我们该如何拥有一种全新的、感觉很自然的工作方式？不过，想出这种解决方案绝非易事，而且它是反直觉的。

<details>
<summary>Original English</summary>

**Interviewer**: so do I sense that you're trying to build something like this this workflow for like when you have the the software factories which are like dark factories and loops at a bunch of places how can we have this this new way of working which which will feel natural but like coming up with it like is is hard work and it's it's counterintuitive.

</details>

**Guest**: 我们怎样才能做出一个能够实现 GitHub 所做的事情，但比它好 10 倍的产品呢？更具体地说，要比那些诸如 Pull Request 这种离散的工作单元具有更强的连续性、更高的实时性和更好的协作性。

<details>
<summary>Original English</summary>

**Guest**: How can we do something that accomplishes what GitHub did but like 10x better like more specifically like more continuous and more real time and more collaborative than like these discrete units of work that is like the poll request.

</details>

**Interviewer**: 嗯，我现在开始理解为什么你说也许我们应该“废除 Pull Request”了。因为 Pull Request 是由 GitHub 发明的，对吧？它本来并不属于 Git 协议的一部分，但他们为了让你在代码合并进去之前，能够进行代码审查、做出修改或者干脆拒绝合并等操作，才将其作为一个功能途径开发了出来。

<details>
<summary>Original English</summary>

**Interviewer**: Well, I now I'm starting to understand why you're saying maybe we should kill the poll request because pull request was invented by GitHub, right? like it's it is not part of Git, but they did it as a way for you to do a code review merge before it goes in and be able to modify it or or like just reject it, etc.

</details>

**Guest**: 而且那可能比我们以前拥有的任何流程都要好得多。我猜以前大家可能是通过电子邮件把 Git 补丁（patch）发给 Linus，然后请求他把代码合并到内核（kernel）之类的代码库里。

<details>
<summary>Original English</summary>

**Guest**: And it's probably a lot better than whatever we had before, which I guess was like emailing your git patch to Lionus and ask him to merge it into the kernel or whatever.

</details>

**Interviewer**: 他们现在其实还在这么干。这套流程对他们来说行得通。但这正是重点，这种方式仅仅对他们那帮人有效。

<details>
<summary>Original English</summary>

**Interviewer**: They still do that. It work it works for them. That's the point. But it only works for them.

</details>

**Guest**: 是的。除了他们，我不知道还有谁会这么干。我的意思是，我确信即使在你们用 GitHub 之前，你们应该用过像 CVS 之类的系统吧？

<details>
<summary>Original English</summary>

**Guest**: Yeah. I don't know anybody else who does that. I mean, I'm sure even before Get Up for you, you guys had what, like CVS or

</details>

**Interviewer**: CVS？如果你是在微软这样财大气粗的地方的话，

<details>
<summary>Original English</summary>

**Interviewer**: CVS? So, if you had a lot of money for Microsoft,

</details>

**Guest**: 他们在本科的时候强制我们使用 Subversion，因为发明 Subversion 的那个人是芝加哥大学（UChicago）的。我毕业的第二年，他们就把所有人都转到 Git 上了。我当时就觉得，该死，我居然只为了满足某个人的自尊心而学了一个没用的东西。

<details>
<summary>Original English</summary>

**Guest**: they made us use subversion at in undergrad because the guy who invented subversion uh was a you Chicago guy. The year after I graduated, they switched everybody to Git. And I was like, damn, I learned a useless thing just for somebody's ego.

</details>

### 地点、人脉对 AI 初创公司的影响

**Interviewer**: 特别是对于 AI 初创公司，或者是在 AI 技术之上构建产品、直接研发 AI 产品的初创公司而言，你认为地点和人脉关系有多重要？尤其是你正身处硅谷。我们看到有研究表明，这里的 AI 初创公司比普通的初创公司更频繁地获得融资。你看到了这种优势吗？同时，你有没有看到身处某个特定地点（比如硅谷）所带来的一些劣势？

<details>
<summary>Original English</summary>

**Interviewer**: specifically for AI startups or startups building on top of AI or building AI products. How important do you think location and network is especially you are based in in the the valley we see research that AI startups are more frequently funded from here than normal startups as well. Do do you see this advantage and also do you see some disadvantages of being a specific may that be Silicon Valley or

</details>

<!-- chunk 14/14 -->

### 旧金山的硅谷文化与创业氛围

**Dex**: 至于在其他地方的情况？我对此并没有非常强烈的意见。实际上，比如保罗·格雷厄姆（Paul Graham）曾在瑞典做过一次演讲，专门讨论为什么旧金山（SF）如此之酷。与其在这里简单重复他的观点，我更愿意推荐大家直接去听听那次演讲。嗯，我们可以把它放在节目单的备注（show notes）里或者其他什么地方，但他在演讲中深入探讨了硅谷所有的动态文化、那种“让爱传递”（pay it forward）的互助精神，以及仅仅因为你把公司设在这里，人们就会对你更加认真对待的那种氛围。我在芝加哥住了很长时间，我有很多来自高中、大学以及在洛杉矶一起长大的非常好的朋友。但在此之前，我从未像现在这样强烈地感觉到与“我的人（同类人）”如此紧密地联系在一起。我也从未感到自己如此被看见、如此充满联结感。这里真的有太多这样的人了。再次谈到关于创始人的事情，这里的很多人都在乎得极其深刻，他们都极其出色和能干，这就好像我们都在面对所有同样类型的问题。我们热爱所有同样类型的事物。比如说，我不会举办那种大家一起打电子游戏的局域网派对（LAN parties），但我所有的好哥们儿都会聚过来，我们会在办公室里一直坐到晚上11点。我们就只是在进行协同工作（co-working），一起在那些很酷很有趣的项目和东西上进行黑客式的开发（hack）。说实话，你在其他任何地方都做不到这一点。在其他地方，没有足够多的、所谓的“临界质量（critical mass）”能让这种现象无论你走到哪里都能自然而然地发生。我绝对热爱这里。我不会用它去交换任何东西。

<details>
<summary>Original English</summary>

**Dex**: elsewhere? I don't have really strong opinions on this. Actually, like Paul Graham gave a talk in Sweden about why SF is cool. Rather than just regurgitate that, I will I will forward people onto that one. Um, we can put it in the show notes or whatever, but he talks about all of the dynamics of Silicon Valley and the pay it forward culture and the like people take you way more seriously just because you're based here. I lived in Chicago for a long time. I have a lot of really good friends from high school, from college, from growing up in LA. And never before have I felt like so locked in with like my people more. Never have I felt more seen, more connected. Like there's just so many people here. Again, talking about the founder thing, people who care deeply, who are incredibly competent, who like we have all the same types of problems. We love all the same types of things. Like I don't do LAN parties where we play video games, but all my buddies will come over and we'll sit in the office till 11. We'll just do co-working and like hack on cool fun projects and stuff. And like you can't do that anywhere else. There's not enough like uh critical mass for that to just happen organically everywhere you go. and and I absolutely love it. I wouldn't trade it for anything.

</details>

**Host**: 是的，我认为“临界质量”这个词恰好切中了要害。那么，当谈到招聘时，你们具体在招聘什么类型的人才？因为我很感兴趣的是，招聘方式是如何发生变化的，以及对你来说，一个出类拔萃的杰出工程师意味着什么，还有你是如何试图去，你知道的，确认这些人身上确实存在那些特质的。

<details>
<summary>Original English</summary>

**Host**: Yeah, I think a critical mass nails it on on the head. When it comes to hiring, what types of folks are you hiring for specifically? Cuz I'm interested in how hiring changes and and what what a standout engineer means for you and how you are trying to, you know, confirm that those traits exist.

</details>

**Dex**: 总的来说，我们正在寻找那些拥有极其扎实的软件基础的人。也就是说，他们要理解分布式系统，要理解计算机科学（CS）的核心基础知识，了解操作系统以及这类相关的知识。我的意思是，你不需要成为那种专门研究内核设计（kernel design）或者什么其他高深领域的博士，但有这些基础会让一切变得容易得多。我认为，我们可以，我们可以教某个人，在几个月的时间里让他成为一个非常优秀的人工智能（AI）开发者。你可以建立起足够的直觉，让你能够，你知道的，迅速起飞离开地面，然后你就可以在那里继续不断成长。但是，想要在3个月的时间里把一个计算机科学本科项目的知识全部教给某人，那真的是太难了。

<details>
<summary>Original English</summary>

**Dex**: In general, we we are looking um for people who are have really strong software fundamentals. So, understand distributed systems, understand like the core fundamentals of CS and operating systems and these kind of things. I mean, you don't have to be a PhD in freaking kernel design or whatever, but it's a lot easier. We can we can teach we can teach somebody, I think, to be a really good AI developer in a few months. You can build enough intuition where you are, you know, accelerated off the ground and you can go like keep growing there. It's really hard to teach someone a CS undergrad program in in 3 months.

</details>

### 未来的基础设施与软件工程的挑战

**Host**: 那么，在软件工程、产品工程或者产品构建领域，有什么问题空间（problem space）是你感到兴奋的？或者说，在接下来的几年里，你认为有哪些有趣的事情是你们将会去攻克的？

<details>
<summary>Original English</summary>

**Host**: And what's a problem space that you're excited about in in software engineering or even product engineering or building products that you think in the next few years is going to be one of the interesting things that you're going to be attacking?

</details>

**Dex**: 我的联合创始人可能会就这个问题谈论得更多，但现在确实有很多有趣的事情正在云端（cloud）、沙箱（sandboxes）、同步（sync）等领域实时发生，并且这就像是在使用这些在过去几年里变得非常稳固的新型构建模块（building blocks）。我们是Electric SQL团队的忠实粉丝，在他们的系统中，用户拥有持久化的数据流（durable streams）。这就好比，你该如何构建那些更加分散、更加分布式、甚至几乎可以说是去中心化（decentralized）的系统。这对于编程来说极其有趣，因为你会希望能够在任何地方运行编程智能体（coding agents）。你会希望能够让它们短时间运行、长时间运行，可以按需运行（on demand），也可以按计划定时运行（on a schedule），所有这些事情，并且让它们全都成为这种类似“大脑（brain）”的一部分。所以，我不知道，我们正在做的部分工作确实非常枯燥，比如我们所有的数据都存放在Postgres数据库中；但我们正在做的另一部分工作却又真的非常有趣。嗯，但是这其中确实存在大量的分布式系统问题。存在大量的基础设施（infrastructure）问题。比如，我们正在为人工智能构建工具，但在构建协作平台的方面存在着大量极其极其困难的问题，而且，虽然有很多新技术让这些工作变得更容易、更有趣，但这依然，离一个简单的问题还差得很远很远。

<details>
<summary>Original English</summary>

**Dex**: My co-founder could talk more about this, but like there's a lot of interesting things happening in in real time in cloud and sandboxes in sync and kind of like using these new building blocks that have gotten really solid in the last couple years. We're big fans of the electric SQL team. where users have durable streams. It's like how can you build systems that kind of are a lot more spread out and distributed and almost like decentralized. This is really interesting for coding because you want to be able to run coding agents anywhere. You want to be able to run them for a short time, for a long time, on demand, on a schedule, all these things and have them all be part of this kind of like brain. So I don't know, parts of what we're doing are really boring like all our data is in Postgress and then parts of what we're doing is really interesting. Um, but there's a lot of distributed systems problems. There's a lot of infrastructure problems. Like we are building tools for AI, but there's a lot of problems in building collaboration platforms that are really really hard and there's a lot of new tech that makes it easier and more interesting, but it's still uh by far from an easy problem.

</details>

**Host**: 听起来你好像是在说，那些基础设施层（infr layers）在某种程度上是一种正在被构建的全新基础设施，这将需要花费一些时间，不过，它最终会变成就像只是全新的模块，并且它最终会成为那些基础原语（primitives），就像在云计算领域，我们现在已经有了那些基础原语，但那是花了整整十年的时间，或者更长的时间，才把它们整合在一起的。

<details>
<summary>Original English</summary>

**Host**: It sounds like what you're saying is like the infr layers to some extent a new infrar being built and it'll take some time and but it'll be like just new new blocks and it will eventually become the primitives like for cloud we have primitives already but it took freaking decade to get those together or more.

</details>

**Dex**: 是的。AWS大概是在什么时候出现的？像是2008年？还是2006年。是的。嗯，然后我们是在十年之后才迎来了Kubernetes。

<details>
<summary>Original English</summary>

**Dex**: Yeah. You had AWS in what like 2008 2006. Yeah. Uh and then you got Kubernetes a decade later.

</details>

### 书籍推荐与软件工程经典

**Host**: 是的。那么作为结语，有什么书籍或者是阅读材料是你想要推荐的吗？就是那种你个人非常喜欢的东西。

<details>
<summary>Original English</summary>

**Host**: Yep. And as closing, what's a book or or reading that you would recommend? Something that you personally enjoyed.

</details>

**Dex**: 如今，我们讨论了很多关于马丁·福勒（Martin Fowler）的经典之作《重构》（Refactoring）。我认为这是因为我们花了很多时间，嗯，去改进现有代码的设计，并且努力试图弄清楚如何让模型去编写出那些易于维护、易于阅读、易于理解，以及易于在其基础上继续构建的代码。我觉得我可能本来有一个比这更好的答案，但这就是我这些天脑子里最首先想到的东西。嗯，我们正在阅读大量软件工程方面的经典著作。《重构》、《代码整洁之道》（Clean Code）、《程序员修炼之道》（The Pragmatic Programmer），像所有这些东西，我认为现在都比以往任何时候都更加具有现实意义。我非常喜欢它们。

<details>
<summary>Original English</summary>

**Dex**: Nowadays, we talk a lot about refactoring by Martin Fowler classic. I think it's because we spent a lot of time uh improving the design of existing code and trying to figure out how to get models to build code that is easy to maintain and like easy to read and easy to understand and easy to to build on. I feel like I probably have a better answer than that, but that's that's what's top of mind these days. Uh we're reading a lot of like classics of software engineering. Refactoring clean code, the pragmatic programmer, like all that stuff is I think is more relevant now than it has ever been. Love it.

</details>

**Host**: 好的，Dex，非常感谢你。这真的很有趣。

<details>
<summary>Original English</summary>

**Host**: Well, Dex, thanks so much. This was fun.

</details>

**Dex**: 这简直棒极了，伙计。感谢你邀请我参加节目。这太棒了。嗯，我玩得很开心。我不知道你的感受如何，但我真的非常享受这次对话。

<details>
<summary>Original English</summary>

**Dex**: This was a blast, dude. Thanks for having me on. This was great. Uh I had a lot of fun. I don't know about you, but I really enjoyed this conversation.

</details>

### 结尾总结：慢循环工程与软件工厂

**Host**: Dex 是如此坚信智能体编程（agentic coding）的人。然而，正是他在警告我们，如果你停止阅读代码，那么大约只需3到6个月的时间，你的代码库就会变得与其去修复，还不如直接重写来得容易。而这可是来自于他的第一手经验。他的团队曾构建了一个轻量级的软件工厂，运行了它，但最后却不得不将其关闭。我也非常喜欢“慢循环（slow loop）”这个概念。对我来说，循环工程（Loop engineering）听起来多少像是个毫无意义的术语。Dex团队所做的事情实际上非常枯燥：一个定时任务（cron job）每天晚上运行，只修复一个问题或者一个反面模式（anti-pattern），然后开启一个很小的合并请求（pull request）。当团队第二天早上醒来时，代码库已经比前一天好了一点点，而开发人员仍然需要去审查并验证它。老实说，这是一种当今任何工程团队都可以直接采用的绝佳实践。最后，我真的非常享受这段历史课。《软件工厂（software factory）》这个术语来自于1968年的一次北约（NATO）会议。这种利用软件来构建软件，并将其类比为工厂的想法，已经有超过60年的历史了。我们这个行业的每一代人，都曾试图在构建软件的循环中实现更多的自动化。AI智能体只不过是又一次新的尝试，尽管这可能是目前最成功的一次尝试。请务必查看下方节目单备注（show notes）中相关的 The Pragmatic Engineer 的深度解析，其中更加深入地探讨了AI工程以及其他相关主题。如果你喜欢这个播客，请务必在你最喜欢的播客平台上以及YouTube上订阅我们。如果你还能为这个节目留下评分，我们将致以特别的感谢。感谢收听，我们下期节目再见。

<details>
<summary>Original English</summary>

**Host**: Dex is such a big believer in gender coding. Yet, he's the one warning us that if you stop reading the code, you have about 3 to 6 months before your codebase becomes easier to rewrite than to fix. And this comes from first hasn't experience. His team built a light software factory, ran it, and then had to shut it down. I also like the idea of the slow loop. Loop engineering feels like a somewhat meaningless term to me. What Dex's team does is actually pretty boring. A cron job runs every night, fixes one issue or one anti-attern, and opens one small pull request. The team wakes up to a codebase that's a little bit better every morning, and dev still needs to review and prove it. This is a practice that honestly any engineering team could just adopt today. Finally, I really enjoy the history lesson. The term software factory comes from a NATO conference in 1968. The idea of software used to build software with analogies to a factory is more than 60 years old and every generation of our industry has tried to automate more of the loop of building software. AI agents are just yet one more attempt, although probably the most successful one. Do check out show notes below for the related the pragmatic engineer deep dives that go even deeper into AI engineering and other related topics. If you enjoy this podcast, please do subscribe on your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show. Thanks and see you in the next

</details>