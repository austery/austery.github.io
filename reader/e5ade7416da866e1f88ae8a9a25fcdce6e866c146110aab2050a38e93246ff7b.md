---
author: How I AI
date: '2026-03-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tidINuXB7PA
speaker: How I AI
tags:
  - ai-adoption
  - engineering-efficiency
  - developer-tools
  - organizational-transformation
  - feedback-loop
title: Coinbase如何赋能千名工程师，实现AI规模化部署
summary: Coinbase工程总监**Chintan Turakhia**分享了在千人工程团队中推动AI工具大规模应用并提升开发效率的经验。他强调了领导者亲身示范的重要性，通过**Cursor**等工具简化重复性工作（如单元测试、代码检查、PR草稿），并创新性地引入“PR加速跑”活动，显著提升了代码提交速度。此外，团队还开发了内部AI代理**Cloudbot**，实现了从用户实时反馈到PR生成的秒级响应，大幅缩短了开发周期，减少了协调开销。访谈还探讨了AI时代下工程师的职业发展机遇，以及AI在个人生活中的应用，如智能整理日程和葡萄酒品鉴偏好分析。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Coinbase
  - Work OS
  - Cursor
  - Atlassian
  - Microsoft
  - OpenAI
  - Perplexity
products_models:
  - GitHub Copilot
  - Cursor
  - Rovo
  - Jira
  - Confluence
  - Jira Service Management
  - ChatGPT
  - Claude Opus 4.5 High
  - Gemini
  - Linear
  - Cloudbot
  - React Native
media_books: []
status: evergreen
---
### AI在大型工程组织的部署挑战

**Claire Bell**: 人们对大型、成熟、技术精湛、能力超强的工程组织能否大规模部署AI并取得任何效果持怀疑态度。但我认为你已经证明这是可能的。

<details>
<summary>Original English</summary>

**Claire Bell**: People are skeptical that large established, highly technical, highly capable engineering organizations can deploy AI at scale and get any effect. But I think you've proven it's possible.

</details>

**Chintan Turakhia**: 这不仅是可能的，更是“不适应就灭亡”的局面。它对团队来说是一个巨大的超能力。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: It's not only possible, it's adapt or die. It's just been such a huge superpower for the team.

</details>

**Claire Bell**: 我们这里谈论的是多少工程师？

<details>
<summary>Original English</summary>

**Claire Bell**: How many engineers are we talking about here?

</details>

**Chintan Turakhia**: 一千多人。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: A thousand plus.

</details>

**Claire Bell**: 所以我们不是在开玩笑。

<details>
<summary>Original English</summary>

**Claire Bell**: So we're not messing around here.

</details>

**Chintan Turakhia**: 公司曾尝试采用其他AI工具，我们看到了采用率的上升。人们打开它，勾选了选项，做了一些类似“Hello World”的尝试，但它并没有真正留存下来。我最关心的问题是，我如何让这个该死的东西真正“粘住”？因为这里面确实有些东西。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: The company tried to adopt other AI tools and we saw this uptick in adoption. People opened it up, checked the box, did kind of like a hello world thing, but it didn't stick. My biggest thing is, how do I make this damn thing stick? Because there's something here.

</details>

**Claire Bell**: 我确实认为，在进行这种组织转型时，领导层需要有一个对技术有坚定信念、并且亲力亲为的人，这非常重要。

<details>
<summary>Original English</summary>

**Claire Bell**: I do think that it's really important when you're doing this organizational transformation that you have a single person with incredible conviction at the leadership level who is also hands on the metal.

</details>

**Chintan Turakhia**: 要向工程师展示，而不仅仅是告诉他们。任何领导者最糟糕的做法就是发号施令：“我命令你们必须使用AI。”拜托，没人会听你的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Show the engineers, not just tell. And the worst thing any leader could do is just be like, I decree you must use AI. Come on, no one's going to listen to you.

</details>

### Coinbase的AI落地实践

**Claire Bell**: 欢迎回到《我如何AI》。我是**Claire Bell**，产品负责人，也是AI的狂热爱好者，我的使命是帮助大家更好地利用这些新工具进行构建。今天我们邀请到了**Coinbase**的工程高级总监**Chintan Turakhia**。他将向我们展示，是的，在拥有数千名工程师的工程组织中，推动AI的采用并提高开发速度是可能的。他还将向我们展示对工程经理和工程领导者的新期望，那就是减少会议，增加代码编写。让我们开始吧。本期节目由**Work OS**赞助。AI已经改变了我们的工作方式。工具正在帮助团队编写更好的代码，分析客户数据，甚至自动处理支持工单。但有一个问题：这些工具只有在深度访问公司系统时才能很好地工作。你的副驾驶需要看到你的整个代码库。你的聊天机器人需要搜索内部文档。对于企业买家来说，这引发了严重的安全问题。这就是为什么这些应用程序从第一天起就面临严格的IT审查。要通过审查，它们需要安全的身份验证、访问控制、审计日志以及全套的企业级功能。从头开始构建所有这些，这是一项巨大的工程。这就是**Work OS**发挥作用的地方。**Work OS**为你提供了企业级功能的即插即用API，让你的应用程序能够具备企业级能力，并更快地向上市场扩展。可以把它想象成企业级功能的**Stripe**。**OpenAI**、**Perplexity**和**Cursor**已经在使用**Work OS**来更快地行动并满足企业需求。加入他们以及数百家其他行业领导者，访问workos.com。今天就开始构建吧。**Chintan**，非常感谢你的加入。我喜欢我们今天将要讨论的内容，我们花了很多时间讨论个人开发者或非技术人员如何成为软件工程师，但人们仍然怀疑大型、成熟、高度技术化、能力超强的工程组织能否大规模部署AI并取得任何效果。仍然存在很多怀疑，但我认为你已经证明这是可能的，你也将有望为我们指明方向。

<details>
<summary>Original English</summary>

**Claire Bell**: Welcome back to How I AI. I'm **Claire Bell**, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have **Chinten Therakia**, senior director of engineering at **Coinbase**. And he's going to show us, yes, it is possible to drive AI adoption and higher velocity in an engineering organization of thousands of engineers. He's also going to show us the new expectations for engineering managers and engineering leaders, which is less meetings and more code. Let's get to it. This episode is brought to you by **Work OS**. AI has already changed how we work. Tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features. Building all that from scratch, it's a massive lift. That's where **Work OS** comes in. **Work OS** gives you drop-in APIs for enterprise features so your app can become enterprise ready and scale up market faster. Think of it like **Stripe** for enterprise features. **OpenAI**, **Perplexity**, and **Cursor** are already using **Work OS** to move faster and meet enterprise demands. Join them and hundreds of other industry leaders at workos.com. Start building today. **Chinton**, thank you so much for joining. What I love about what we're going to talk about today is we spend so much time talking about the individual vibe coder or the non-technical person becoming a software engineer and still people are skeptical that large established highly technical, highly capable engineering organizations can deploy AI at scale and get any effect. There's still so much skepticism, but I think you've proven it's possible and you're hopefully going to show us the way.

</details>

**Chintan Turakhia**: 我认为这不仅是可能的，更是“不适应就灭亡”的局面。它对团队来说是一个巨大的超能力，我们从中获得了极高的效率，而且有很多方法可以实现。我昨天读到一条推文，是关于**Microsoft**的一个很长的故事，或者说有人将**Copilot**引入他们的组织，那条推文很有趣，就是说“是的，我们要让图表向上向右增长”，但实际的采用情况并不好。所以，我过去一年一直在为此着迷，而且你可以做到，人们可以做到。那么，你们是如何做到的呢？因为我们这里谈论的是多少工程师？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I I think it's uh not only possible, it's, you know, adapt or die. Um like it it's uh it's just been such a huge superpower for the team and we've gotten so much efficiency out it and and there's just like ways to approach it. Um, I was I think I was reading a tweet yesterday uh just about a very very long story at **Microsoft** and or someone like pulling **co-pilot** in to their organization and it was like just a fun tweet of just like yep we're going to make graph go up and to the right but like the actual adoption wasn't good and and so like I've been spending the last year just absolutely obsessing about it and you can do it people can do it. So, how how can you do it? Because, you know, how many engineers are we we talking about here?

</details>

**Claire Bell**: 一千多人。

<details>
<summary>Original English</summary>

**Claire Bell**: A thousand plus.

</details>

**Chintan Turakhia**: 是的。所以，我们不是在开玩笑。这不是在开玩笑。这是一个真正的团队，正在开发真正的产品，他们知道自己在做什么，他们构建了出色的软件。那么，你们是从哪里开始的？是从文化、产品还是工具的角度？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yeah. So, we're not we're not messing around here. This is messing around. This is a real this is a real team working on real products who know what they're doing, who have built great software. And so, where did you start either culturally, from a product perspective, from a tools perspective?

</details>

**Chintan Turakhia**: 我认为很多事情实际上都是从去年这个时候开始的。我们进行了一些调整，以调整我负责的产品，其中很大一部分实际上是彻底重写整个产品，从一个自托管钱包转变为一个恰好使用加密货币的社交消费应用。我们正在使用**React Native**，但我们为自托管钱包做了很多决定，而要成为一个消费应用，你必须重新思考一切。这是第一点。第二点，我们需要在6到9个月内完成。所以我们正在与那些拥有数千人团队、领先10年的大型社交平台竞争。我们真的想做一些宏大、新颖、疯狂的事情，绝对是疯狂的。其中很大一部分是，我们如何重写这个应用，使其成为市面上最好的应用，达到消费级水平，并在如此疯狂的时间线内完成。团队非常出色，他们很棒。但由于这些变化，我们团队规模变小了。所以我开始寻找加速的方法，你知道，我的团队很了解我，如果你了解我，我痴迷于效率，我认为这对于让团队加速提升速度至关重要，但要以一种对工具和使用工具都有意义的方式。所以大约在这个时候，我想**Cursor**发布了他们的初始版本，大约是去年11月，我们都尝试了它，2024年，它有点糟糕。并不是说我不喜欢**Cursor**，我喜欢**Cursor**。模型当时还不行。模型当时就是不行。它们甚至不能真正编写单元测试。对吧。你知道你是一名工程师。你明白，一旦工程师尝试了一个工具，然后觉得“嗯，这个不太好”，他们很快就会把它放弃，对吧？这种情况经常发生。所以我们经历了一段“悲伤的低谷”，觉得“天哪，AI工具还没准备好，模型还没准备好，我们该怎么办？”你知道，甚至在这件事发生前一年，公司就尝试过采用其他AI工具，比如**GitHub Copilot**，我们也看到了采用率的上升，人们打开它，勾选了选项，做了一些类似“Hello World”的尝试，但它并没有真正留存下来，对吧？我最关心的问题是，我如何让这个该死的东西真正“粘住”？对吧？因为这里面确实有些东西，对吧？我的思维模型一直都是，基础的**LLM**会越来越好，这就像去健身房一样。你需要去锻炼，尝试它，这没关系。而且这样做的成本几乎为零。只是浪费一点时间。我们现在不担心计算成本，因为它还处于早期阶段。所以从基本上是1月一直到2025年的3月或4月，我只是改变了心态和思维方式。我每天、每时每刻都在使用**Cursor**。我当时想，我怎么才能让它发挥作用呢？对吧？你知道，这很棒，因为我又开始写代码了。这很棒，因为它解锁了所有这些用例，比如我们当时在进行面试，面试候选人，我不想非得把所有笔记都写下来，那需要很长时间，但我直觉上知道我已经评估过了，所以我会用它来处理日常的战术性文书工作，以加速我的工作，但从编码的角度来看，我也会用它来解决bug，然后说“嘿，我们试试这个，对吧？会发生什么？我能学到什么？有哪些技巧可以向工程师展示，而不仅仅是告诉他们。”任何领导者最糟糕的做法就是发号施令：“我命令你们必须使用AI。”拜托，没人会听你的。我必须对此感同身受，因为我也管理着一个大型的、拥有数百人的工程组织，你知道，我甚至在这些工具的早期版本中就体验过，并且有着如此内在的信念。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: So, I think a lot of it actually just started around this time last year. um we had some changes uh to align like the product I'm responsible for and a big part of that was effectively like rewriting the entire product from scratch uh from uh turning it from a self-custody wallet to actually a social consumer app that just happens to use crypto and you know we're using **React Native** um but we made a lot of decisions for a self-custody wallet but to become a consumer app you got to like rethink everything that was one, two, we needed to do it in like 6 to9 months. So, we were going headto-head with like the big social players out there that have multi,000 person teams uh that have a 10-year head start. And we were really trying to just do something big and new and crazy, like absolutely just crazy. And and uh a big part of this is like how do we rewrite the app so that it is the best possible app out there like consumer grade and do it in this insane timeline. And the team is cracked. They're amazing. But like you know we we be we became a smaller team as a result of of some of these changes. And so I started just looking at like ways to accelerate and and you know like I don't know my my team knows me well and if if you know me like I obsess about efficiency uh and I think that's like so critical to like make teams accelerate their velocity um but in in in ways that make sense uh for tool and using the tool so around this time I think **cursor** had come out with their sort of initial release it was around like November of last year we we all tried it right 2020 24 and it kind of sucked. And it it's not like I love **cursor**. I love **cursor**. Uh the models weren't there. The just the models weren't there. Like they the models couldn't even you know really write a unit test. Right. Well, and you know you're an engineer. Um and you understand like once once an engineer tries a tool and and they're like h this is not so good like it's very quickly and very easy to write it off, right? It happens. And so we we kind of went through this like trough of sorrow of just like okay god damn it AI tools are not here the models aren't ready what are we going to do and you know for even a year prior to this event like the company tried to adopt other AI tools like **GitHub copilot** and we saw this like uptick in adoption like people opened it up checked the box did kind of like a hello world thing but it didn't stick, right? And and like my my biggest thing is how do I make this damn thing stick, right? Because there's something here, right? And my mental model was just always the models will the foundational **LLM** will always get better and it's like going to the gym. You need to go and build your reps and try it and that's okay. And the cost of doing it is like nothing. It's just a little bit of waste of time. We're not worried about compute right now because it's so early. And so like from basically January all the way to like March or April of 2025, I just changed the the mindset and the mentality. I I was like in **cursor** every single day, every single hour of the day. And I was like, how do I make this work, right? Like you know, it was great because I was writing code again. It was great because you know it was unlocking all these like use cases like we were doing interviews like interviewing candidates and and just like I don't want to necessarily write up all the notes right that takes a long time but I intuitively I like I know I've assessed right so I would use it for like tactical day-to-day paperwork kind of things to accelerate me uh but also from like a coding perspective just pick up bugs and be like hey let's try this right what's going to happen what can I learn what are the tips and tricks to like show the engineers, not just tell. And the worst thing any leader could do is just be like, I decree you must use AI. Like come on, no one's going to listen to you. I have to empathize with this because I also running a large like multiund person engineering organization you know was experiencing even early versions of these tools and had such innate conviction

</details>

**Claire Bell**: 它当然会改变我们的工作方式，这对我来说非常明显。我不知道是因为经验还是仅仅因为显而易见，但……

<details>
<summary>Original English</summary>

**Claire Bell**: that it would of course transform how we did work like that was very obvious to me I don't know it's obvious because of experience or obvious because it was just obvious but

</details>

**Chintan Turakhia**: 但你知道，作为领导者，你就是有过这些经历，尤其是在大约12个月前，一个工程师尝试了它，但没成功。不仅仅是那个工程师把它扔掉了，而是其他人都会说：“嗯，我想，你知道，我相信他们的看法，如果他们说它行不通，那对我来说也行不通。”

<details>
<summary>Original English</summary>

**Chintan Turakhia**: but then you know you just had these experiences as leaders especially in the you know maybe 12 months ago, one engineer tries it, doesn't work. It's not just that engineer throws it away. It's everybody else says, "Well, I think, you know, I trust their opinion and if they say it's not going to work,

</details>

**Claire Bell**: 对我来说也行不通。我确实认为，在进行这种组织转型时，领导层需要有一个对技术有坚定信念、并且亲力亲为的人，这非常重要。因为除非你能说：“好吧，我明白它对那个没用，但它对这三件事有用。”或者我实际上已经弄清楚了如何让它对那个有用，因为我们尝试了A、B和C。我认为这是唯一的办法。你不能停留在哲学层面。你不能停留在“未来某天你会弄清楚”的层面。你必须真正地回归到实践中。然后我认为，加分项是，我们工程领导层中的很多人都已经被推离了编码工作。

<details>
<summary>Original English</summary>

**Claire Bell**: it's not going to work for me." And I do think that it's really important when you're doing this organizational transformation that you have a single person with incredible conviction at the leadership level who is also hands on the metal. Because until you can say, "Well, I understand it didn't work for that, but it worked for these three things." Or I actually figured out how to make it work for that because we tried A, B, and C. I think it's just the only way. You cannot be in philosophy. You cannot be in, you know, someday in the future you figure it out. You have to actually get back to it. And then I think like bonus points, so many of us in engineering leadership have like been pushed away from from coding.

</details>

**Chintan Turakhia**: 我知道。我必须重新投入其中。我当时想，我只是想再次写代码。给我一些乐趣。给我一些时间。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I know. I have to get back in it. And I'm like, I just want to code again. Like, give me some joy. Give me some time.

</details>

**Claire Bell**: 是的。所以我想这也是一个好处。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah. And so I think that's a benefit as well.

</details>

### 利用Cursor提升开发效率

**Chintan Turakhia**: 而且你必须展示，而不是仅仅告诉。所以我做到了。我很快就明白了，这里面有些东西。这里面确实有些东西，对吧？然后我们开始挑选一两个用例。让工程师接受工具的最好方法就是给他们工具，这样他们就可以停止做那些繁琐的工作，转而去构建他们喜欢的东西。对吧。对吧。所以我们就会挑选单元测试。我们会挑选代码检查（**linting**），所有这些小事情，它们就像纸割一样，会吸走你作为一个构建者的灵魂，但工程师和团队只想更快地前进。团队想构建更好的东西。所以我们开始倾向于使用**Cursor rules**来处理这些事情。即使是最简单的事情，我记得我的“顿悟时刻”是，我输入了一些bug报告，处理完之后，我没有多想，就直接做了。我当时想，直接创建一个PR草稿。这是工单。这是PR，你知道，这是我想要的PR描述。我只是做了，然后我想，我再也不需要记住`git status`、`git rebase`了。为什么还有人要做这些？我们在做什么？有趣的是，我花了一些时间才说服团队，伙计们，只要输入“创建PR草稿”，它就会为你完成。他们会说：“嗯，你知道，我有点自己的工作流程。”我说：“酷，酷，我明白你的工作流程，你可以修改，你可以使用**Cursor rules**，没关系。”

<details>
<summary>Original English</summary>

**Chintan Turakhia**: And you you have to show not tell. And and so I did. And like I think what I learned very quickly is like, okay, there's something here. There's there's a there, right? And then we just started picking off like one or two use cases and and the best way to get to an engineer is just give them the tools so they stop doing the work and so that they can build the stuff they love. Right. Right. And so like we would just like pick off unit tests. We'd pick off like **linting**, all these like little things that just like paper cut and suck the soul out of you as a builder, but the engineers and you know like the team just wants to move faster. The team wants to build better things. And so we started leaning into like **cursor rules** for some of these things. Even the simplest thing I I remember like I think I remember my aha moment which was like popping in some bug report working through it and then I didn't think about it. I just did it. I was like just create a draft PR. Here's the ticket. Here's kind of the PR like and you know here's the PR description I want. And I just did it and I was like I never need to remember get status get rebase. Like why is anyone doing this anymore? like what are we doing? And it took the funny thing is it took some convincing of me to the the team like guys just type create draft a PR like create a draft PR and it'll be done for you and like like well you know I kind of have my workflow. It's like cool cool I get your workflow you can modify you can use **cursor rules** it's okay.

</details>

**Claire Bell**: 没人会因为记住Git命令而获得奖励积分。

<details>
<summary>Original English</summary>

**Claire Bell**: Like no one's getting bonus points for memorizing git commands.

</details>

**Chintan Turakhia**: 完全正确。完全正确。所以我们一点点地改进，我们设置了很多规则，比如**Cursor rules**，这帮助很大。然后，我当时感觉：“好吧，团队里有足够多的人觉得这确实能解锁一些东西。”他们会在团队频道里发帖，比如“看，我们真的有一个叫做‘**Cursor**胜利’的频道。”每个人都在频道里发帖，比如“我刚刚做了20个单元测试，然后去喝了杯咖啡。这太棒了。”我喜欢它。所以人们开始看到它的实际效果。然后我们达到了一个点，我当时想：“好吧，现在我怎么才能让整个团队都快速行动起来？这里面有点说服力了。”所以我当时就，我记得我当时降落了，我正要去东海岸。我下了飞机，坐上了一辆**Uber**，然后就参加了一个全团队的“加速跑”会议，我们称之为“**Cursor**加速跑”。我当时在**Uber**里用**Cursor**提交了一个PR。这个加速跑的目标是每个人都挑选最微不足道的事情。它可以是修改文案、修复bug，或者任何东西，然后提交PR。我们最终，我想在15分钟内，大约有100人参加。在15分钟内，我们提交了大约70个PR。我们甚至把**GitHub**搞崩溃了，这也很酷，因为我们了解到我们的基础设施需要改进。所以我想暂停一下，因为《我如何AI》也涉及一些战术技巧，而你用了一些我也用过的技巧，比如一个有高度信念的领导者亲力亲为，他只是说：“我们必须这样做。”访问工具，专注于繁琐的工作，这非常重要。你提到了**linting**，你提到了测试。另一个我想提的是设计债务，你知道，前端工程师或设计师不得不忍受应用程序中他们讨厌的部分。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Exactly. Exactly. And and so like we chipped away and we put in a bunch of rules like **cursor rules** and that that helps so much. And then like we had I I was like sensing I was like okay I have I have enough like folks on the team that are like yep this is unlocking stuff. And they would post in the team channel like look what we had literally a channel called **cursor wins**. And like everyone was just posting in the channel like I just did like you know 20 unit tests and then went and had a coffee. This was great. like I love it. And so people started seeing it in action and then we hit this like point. I was like, "Okay, how do I speedrun now the whole team? There's a there's a little bit of conviction here." So I just and I remember this like I think I had landed I was going to the east coast. I landed um for my flight, got into an **Uber**, hopped on like an entire team all hands like speedrun we call it. It was like basically **cursor speedrun**. And I was in the **Uber** using **cursor** putting up a PR. And the goal of the speedrun was every single person would just pick up the most trivial thing. It could be like copy change, a bug, whatever, and just put up the PR. And we ended up, I think in 15 minutes, I think a 100 people had joined. In 15 minutes, we ended up putting up like 70 PRs. And we broke **GitHub**, too, which was cool because we learned like our infrastructure needed improvement. So I want to I want to pause real quick because again how I AI a little bit about tactical techniques and you've used a couple that I have used which is like one high conviction leader with hands on the metal that just says like we just got to do this access to tools focus on toil and is very important. You called out **linting** you called out tests. Another one I would call out is like design debt where you know front end engineers or designers have just lived with parts of the app they hate.

</details>

**Chintan Turakhia**: 是的。嗯，那也是一个非常棒的例子。然后，还有一个共享的**Slack**频道。我会在你的“**Cursor**胜利”频道的基础上做一点修改，我们把我们的频道叫做“胜利与失败”。所以我们非常清楚地说明，只要发布你做了什么，什么时候成功了，什么时候失败了。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yes. Um, that is another really great one. But and then and then a a shared **Slack** channel. And one like, you know, riff I would make on your **cursor wins** channel is we made ours wins and losses. And so we were very clear like just post what you did and when it worked and when it didn't

</details>

**Claire Bell**: 因为当它失败时，人们会说：“哦，是的，但你可以尝试XYZ，或者我有一个**Cursor rule**可以帮你，或者别的什么。”但我还没听过，我想让大家竖起耳朵注意的，是这种“PR加速跑”的想法，就像是设定一个时间，大家启动任何工具，然后快速修复一些问题。因为一个组织需要多大的信念才能从那种“看，我经历过季度规划的低谷，这要四个月后才能实现，等等等等”的状态，一下子变成“我们刚刚在30分钟内提交了70个PR”。我只是觉得，这对一个边缘团队来说，那肯定是一个变革性的时刻。

<details>
<summary>Original English</summary>

**Claire Bell**: because when it didn't, people would be like, "Oh yeah, but you could try XYZ or I have a **cursor rule** for you or whatever." But what I haven't heard that I want people to just like perk their ears on and pay attention to is this like idea of a **PR speedrun** which is like do a time down time everybody boot up whatever tool and just speedrun some fixes because how much conviction does an or have to get going from look I've been there like the the doldrums of like quarterly planning and this will be in four months and blah blah blah blah blah to just like we just got 70 PRs that we've sitting on out out the door in in 30 minutes. I just that has to be such a transformational moment for an edge team.

</details>

**Chintan Turakhia**: 你知道，那些PR的合并成功率很高，就像是“这真的可能！”每个人的眼睛都亮了起来。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: You know, there was a success rate on those on uh merging those PRs and like it was just like this is possible there like everyone's eyes lit up

</details>

**Claire Bell**: 这确实是一种“状态更新已死，构建万岁”的时刻，对吧？

<details>
<summary>Original English</summary>

**Claire Bell**: and it was really sort of a death to status updates long live building moment,

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: right?

</details>

### PR加速跑：突破开发瓶颈

**Claire Bell**: 是的。我想指出另一点，因为我认为你们那里有一种非常特殊的文化。但在产品、工程、设计组织中，我们常常会因为“参与规则”而陷入困境，比如“除非产品经理说它很重要，否则我不能构建它”，或者“我不能真正决定那个按钮的颜色，因为设计部门还没有给出意见”。我认为在这些时刻，你打破所有规则，然后说：“猜猜看，记住，你可以直接……”

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah. And and this is the other thing I want to call out because I think you all have a really special culture there. But so often we in product engineering design orgs get like really wrapped around the axle on like the rules of engagement like well I'm not allowed to build it unless the product manager says it's important or like I can't really make that decision about what color that button is because design hasn't weighed in. And like I do think these moments where you just break all the rules and you're like guess what remember you can just

</details>

**Chintan Turakhia**: 提交代码。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: ship code. who can just

</details>

**Claire Bell**: 你可以同时提交它们，把AI放在一边。AI也许能实现它，并使其成本大大降低，但仅仅这样做对于速度和质量来说都非常强大，因为人们会更积极地承担所有权。所以我要百分之百地借鉴这个做法。

<details>
<summary>Original English</summary>

**Claire Bell**: you can just ship them both like put AI aside. AI maybe enables it and makes it like a much less costly you know um expense but like just doing that is so powerful for velocity and for I also think for quality like people just take more radical ownership of things. Um so I'm going to 100% steal this.

</details>

**Chintan Turakhia**: 我是说，我希望每个人都借鉴它，你知道，我真的很喜欢你刚才的说法。这是一个我们应该打破规则的时刻，因为AI正在为我们打破规则，如果我们不适应如何使用它，我们就会完蛋，对吧？而“我们”是一个非常集体的概念，不适应的人都会落后，对吧？所有这些最终解锁的是协调开销的减少。所以，我一直在思考的一件事是：“好吧，酷，太棒了，加速跑做得很好。是的，我们完成了大量工作。”然后我们开始看到更多的胜利，越来越多的人采用了它。然后**Brian**，你知道，你当时正在和**Brian**分享一些关于采用情况的信息，然后我们进行了一次全公司范围的加速跑。在那一刻，大约有800名工程师在电话会议上，我们在30分钟内提交了大约300到400个PR。是的，我们再次搞崩溃了**GitHub**，这没关系，这很好。这是一种压力测试。我们应该设计自己去打破规则，对吧？但我一直在思考的是，你如何衡量所有这些的产出？对吧？这里有一种紧张关系，就是“好吧，我们使用更多的AI，这是否算作取代了人？”我绝对不这么认为。AI是一种加速器，对吧？AI是一种加速器，因为总会有更多的工作要做，对吧？所以，至少对于我的团队和我正在全面推动的事情，我的想法是：从工单到变更落地到用户的时间。这实际上涵盖了你需要的每一个环节，对吧？今天，即使你从工单积压等情况来看，也会有“哦，我应该优先处理这个吗？这重要吗？让我问问我的产品经理，或者让我问问项目经理，或者其他什么人。”而现在整个团队，从那时到现在，我们只是看到有人给我们反馈，然后几乎在几秒钟内，我们就像时钟一样，我们构建了这个内部机器人。我很兴奋能向你展示。在几秒钟内，PR就被编写出来了，对吧？一个代理会接手它，在几秒钟内，这个反馈就被处理了。所以我们压缩了行动时间，然后从工单到PR准备好进行审查的时间。然后是审查时间，我所有的下属都抱怨审查时间太长。我们实际上找到了一些解决方案。我想我们之前PR审查的平均周期时间大约是150小时，因为工作量太大了。我们将其减少了10倍，降到了大约15小时左右。然后最后一部分是，从合并之后，你如何进行OTA更新，然后你再次压缩整个周期，然后团队就像被纯粹的速度彻底解锁了一样。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: You I mean I want everyone to steal it like you know I I really like the way you just put it right. This is a moment where we should be breaking the rules because AI is breaking the rules for us and if we don't adapt to how like we can use it, we're toast, right? And and we is like a very collective like whoever's not adapting is going to fall behind kind of thing, right? And what all of this like ends up unlocking is is like the reduction in coordination overhead. So like one thing I've been obsessing about a lot, it's like, okay, cool, great, good job on the **speedrun**. Yes, we got a lot of stuff done. We started then seeing those wins more and more people adopted. **Brian** then, you know, you were sharing some information with **Brian** like how adoption is going and then we just did a companywide **speedrun**. And at that moment, like there were like 800 engineers on the call and we ended up pushing up for like 3 400 PRs in 30 minutes. And yes, again, we broke **GitHub** and that's fine. That's good. Like this is pressure testing. We should be designing ourselves to break the rules, right? But the thing I've been obsessing about is like how do you how do you measure any of this like in terms of output, right? There's there's this like tension where okay the more AI we use well does that count as a replacement for people and like I'm in the camp of absolutely not. AI is an accelerant, right? AI is an accelerant because there will always be more work to like to do, right? And so the way I think about it, at least for for my team and and what I'm pushing across the board is really like time from ticket to when the change lands to the user. Like that actually encompasses every single piece you need, right? And today like even if you go from like ticket backlogs and stuff like that, like there's oh do I should I like like you said, should I prioritize this? Is this important? Let me ask my PM or let me ask the pro the pro program product manager, project manager, whatever. And now the whole team like fast forward from back then to now, we just see someone give us feedback and literally within like seconds we're like clock like we built this internal bot. I'm excited to show you. And within seconds like the PR is being authored, right? an agent picks it up and within seconds that feedback is like acted on. And so we crunch the time to action, the time then from ticket to the the PR being ready for review. Then the review time like all my dubs complain review times take too long. We found some solutions actually. I think we were doing average of like 150 hours like was the cycle time for a PR review because there was so much. We reduced it by 10x down to like 15 hours or so roughly. And then the last piece is like from that merge, how do you do like that OTAA update and you squeeze that whole cycle again and then the team is like just literally unlocked with sheer velocity.

</details>

**Claire Bell**: 是的。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah.

</details>

**Chintan Turakhia**: 然后你就能把东西呈现在客户面前。是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: And then you get stuff in front of customers. Yes.

</details>

**Claire Bell**: 然后你就能获得实际市场创意的速度。

<details>
<summary>Original English</summary>

**Claire Bell**: And then you have the velocity of like actual market ideas.

</details>

**Chintan Turakhia**: 是的。你能获得反馈，我们也在思考如何能以最快的速度获取实时反馈。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yes. And you get that feedback and like the the we're obsessing also about how fast can we take like in real life feedback.

</details>

**Claire Bell**: 是的。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah.

</details>

**Chintan Turakhia**: 然后立刻就修复它。我想，我当时又有一个“顿悟时刻”。我当时正在和一个产品用户通电话，对吧？他们说：“嘿，如果你能改变X、Y和Z，那就太酷了。”然后我几乎就在通话中提交了一个PR并推送了它。他们说，在通话结束前，也就是30分钟内，我当时说：“你知道，重新加载一下，它就修复了。”

<details>
<summary>Original English</summary>

**Chintan Turakhia**: And then actually just fix it right then and there. I think I think there was another aha moment. I was on a call with with like a user of our product, right? And they're like, "Hey, it'd be cool if you like changed X, Y, and Z." And like literally while I was on the call, I just put up a PR and pushed it. And they're like before the call ended, it was 30 minutes. I was like just you know reload it's fixed.

</details>

### 衡量AI的产出与效率

**Claire Bell**: 好的，在我们把这个话题变成两个产品负责人都在说“赶紧发货”的一个小时的讨论之前，我们先来谈谈减少PR周期时间的所有好处。让我们实际展示一些你构建的东西，因为我认为关于“你可以在工程组织中做到这一点”的元评论。它有步骤，你可以采取措施，我认为这些都是每个人都可以学习的。但你也在构建。所以让我们谈谈你实际上是如何使用**Cursor**来推动它进入组织并理解AI的采用情况的。

<details>
<summary>Original English</summary>

**Claire Bell**: Okay before we quer this into an hour of you know like two two end product leaders being like just ship really fast we'll go into the merits of reducing PR cycle time all that fun stuff. Let's actually show a couple things you built because I think the kind of meta commentary on like you can do this in engineering organizations. There are steps to it. There are measures you can take I think are things that everyone can learn from but you also have been building. So let's talk about how you used actually **cursor** to drive how you drove this into the organization and understand adoption of AI.

</details>

**Chintan Turakhia**: 是的，当然。嗯，我认为很多都来自于真诚的好奇心，以及找出瓶颈在哪里，比如为什么人们不采用，人们如何使用它等等。我想向你展示，我想我将要向你展示的这种疯狂的想法是，我刚刚有了一个异想天开的主意。**Cursor**有很棒的分析功能，对吧？所以你进入管理面板，查看分析数据，他们很棒地让你下载成CSV文件。我当时想，如果我只是用**Cursor**来了解我的团队在使用**Cursor**方面做了什么，但不仅仅是从“AI提交了多少行代码”这种虚荣指标的角度。我认为这有点误导，实际上是更深入地挖掘他们如何使用**Cursor**，以及我们如何复制“高级用户”。所以我们来看看，我们有一些数据。它在这个文件里。嗯，它只是**Cursor**的标准CSV文件，你可以从他们的网站下载。嗯，就像你的管理面板一样。然后这里还有很多不同的字段。嗯，比如接受的行数、聊天行数、删除的聊天行数，各种数据元素。但你知道，我开始思考的一件事是，我想了解**Cursor**的使用情况，对吧？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yeah, for sure. Um, I think a lot of it just comes like from honest curiosity and figuring out um, where the bottlenecks are like why aren't folks adopting, how are people using it, etc., etc. I want to show you like I think the the kind of crazy thing I'm about to walk you through is like I just got this hairbrained idea. **Cursor** has like great analytics, right? And so you go to the admin panel, you look at the analytics and a you know awesomely they let you download it into CSV. I was like, what if I just use **cursor** to figure out what my team is doing in terms of using **cursor** but not in just like from a vanity metric point of view of like lines of code committed by AI. I think that's like kind of misleading actually digging more into um how they're using **cursor** and how do we sort of like replicate power users. So let's see uh we have some some data. It's in this file here. Uh, and it's just like a standard CSV from **Cursor** that you can like download from their their site. Um, like your admin panel. And then there's also here a bunch of different sort of fields. Um, so like accepted lines, chat lines, chat lines deleted, um, various like data elements. But you know, one thing like I just sort of started with I want to understand the usage of **cursor**, right?

</details>

**Chintan Turakhia**: 我已经知道我们有从轻度用户到高级用户。我真正想弄清楚的一件事是，使用模式的自然集群是什么？你能在团队中找到它们吗？如何最好地对他们进行分组？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: And I already know um we have like light users all the way to power users. And one of the things I really wanted to figure out was like what are the natural clusters of usage? Can you find them across the team? What is the best way to cohort them?

</details>

**Chintan Turakhia**: 对吧？我将在这里选取标准的分析文件。也许再弹出一个。然后我喜欢**Opus High**。我也喜欢计划模式，因为它让你有机会看到它在思考什么。所以我们可以让它运行，看看它会给出什么结果。我想在这里向工程经理或工程领导者指出的是，这就是我们都曾希望能够对一系列工程指标进行的那种定量分析，对吧？比如，我们多久会被董事会或老板问到：速度是多少？周期时间是多少？我们的哪些工程师在效率曲线上处于领先地位？我们的初级工程师如何融入代码库？所有这些。而这种分析实际上非常繁琐，很难获得，因为数据结构和分析的性质。所以我喜欢**LLM**s的普遍之处，特别是使用像**Cursor**这样的工具，是你可以对人类行为和人类分析进行非常细致的分组分析，作为经理，这在以前是非常具有挑战性的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Right? And I'm just going to pick up the standard analytics file here. Maybe pop in another one here. And then I love **Opus High**. I also love plan mode because it gives you a chance to like see what it's thinking through. So we can let this cook and see what it comes back with. And what I want to call out here for engineering managers or engineering leaders is this is the kind of quantitative analysis that we would all have loved to be able to do across a bunch of engineering metrics at at some point, right? Like how often do we get asked by the board or our boss like what's velocity, what cycle time, which of our engineers are super, you know, like our are really on the far edge of the curve in terms of efficiency, how are our junior engineers ramping into the repo, all that kind of stuff. And that kind of analysis is actually really ownorous and hard to get at because of the structure of the data and the nature of the analysis. And so what I love about just **LLM**s in general and in particular using something like **cursor** is you can get to really nuanced cohorting analysis on human behavior and human analytics as a manager in a way that I think has been really challenging to do before.

</details>

**Claire Bell**: 是的，我完全同意。而且，现在有了MCPs和数据可访问性，最棒的是……

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah, I totally agree. And like the beautiful thing is now with MCPs with data accessibility

</details>

**Chintan Turakhia**: 我把**Cursor**这样的工具看作是我的日常操作系统。如果我有一个问题，无论是技术性的还是非技术性的，我都会直接在**Cursor**里提问。嗯，所以它就是如此强大。好的，它在问我想要什么输出？我确实想丰富CSV文件。嗯，这会让它更容易。我确实想要一个静态仪表板，只是为了好玩。我现在并不是真的想创建一个全新的仪表板。但我的主要目标是，说实话，就是找到自然的群体，对吧？嗯，所以它会尝试做轻度、中度、活跃、高级、超级用户。它会查看建议的行数，也就是数量、复杂性、代理模式、模型偏好、接受率和广度。他们正在使用哪些功能？它会输出一个CSV仪表板。它可能还会生成一个我可以重复使用的Python脚本。所以，我将启动构建模式。在它运行时，我想也许可以转到，它会用Python创建所有这些东西，为我创建脚本。太棒了。但我们可以在这里查看一些信息，对吧？所以，这些都是随机编造的数据。它是示例数据。但它在之前的运行中做的是，它查看了所有数据，生成了Python脚本，这很棒，非常简单。它还做了一些高级状态指标，比如AI代码百分比，同样是基于所有这些编造的数据，每周AI行数，编写器行数。这是你在**Cursor**中使用代理模式或Tab行时的情况，对吧？当你按下Tab键时。嗯，我团队中的一个成员实际上获得了很酷的**Cursor** Tab奖，这很棒。所以它会把所有这些都分解开来。然后它真正围绕着的是“代理重度用户”，也就是那些真正倾向于使用代理的人。还有“Tab重度用户”。这是一个不同的群体。他们只是倾向于使用Tab键，他们可能只是想要更多的控制，可能还没有习惯如何放手让代理来做。嗯，你还有平衡用户，他们两者都尝试。然后你可能还有对**Cursor**好奇的用户，或者可能还没有完全接受**Cursor**或**LLM**的用户。所以我生成了整个脚本。这很棒。现在让我向你展示我想在这里做的一些更深入的分析。所以我们来做这个。对一个示例用户集运行分析，并同时生成HTML文件。我们实际上，这有点像Python中生成的分析脚本的输出，它已经在并行运行了。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: like I think of tools like **cursor** as just my daily operating system. If I have a question, it doesn't matter if it's technical or not. I just go into **cursor** and ask it. Um, and so it's like super super powerful that way. Okay, so it's asking me a little bit about like what outputs do I want? I do want to enrich CSV. Um, just it makes it easier. I do want a static dashboard just for fun. Like I'm not really trying to create a brand new dashboard right now. But my main goal here is just honestly honestly like find natural cohorts, right? Um, and so it's going to kind of try to do light, moderate, active, power, super user. It's going to look at line suggested, so volume, sophistication, agent mode, model preference, acceptance rate, and breath. What features are they using? I'll spit out, you know, a CSV dashboard. It'll likely generate a Python script, too, that I can reuse. So, I'm just going to kick off build mode. While that's cooking, I do want to just maybe bop over to like it's going to create all this stuff in Python, create the scripts for me. Awesome. But we can look here at some of the the information, right? So like this is all sort of random made up data. It's like sample data. But what it did was in a previous run it looked at all the data, generated the Python script, which is great, super simple. And it sort of just did some like highlevel status metrics like AI code percentage again on all this madeup data, AI lines per week, composer lines. This is when you're using the agent mode in **cursor** or tab lines, right? When you're hitting tab. Uh one one of my team members actually got the cool **cursor** tab award, which is which is great. Great. And so it sort of breaks all this down. And then what it really segmented around was like agentheavy users, which is folks who really lean into agent usage. There's also tab heavy users. This is like a different cohort. they just lean into tab usage and they they maybe want really just a bit more control and maybe haven't gotten yet used to like how to let go with an agent. Uh you have balance users that try both and then you have sort of like maybe **cursor** curious or maybe not **cursor** pill or you know **llm** pled right now and so I generated this whole script. It's great. And now let me show you sort of a bit more analysis I want to do here. So let's do this. Run the analysis on I have um a sample user set and generate the HTML as well and let's we're actually like this is sort of the output of the analysis script that was generated in Python which is already cooking in parallel.

</details>

**Claire Bell**: 明白了。所以你在这里所做的是，你从**Cursor**获取了一些原始数据。你要求一个代理进行基于群体的分析，并生成一个基本上带有数据的丰富CSV文件。然后你启动另一个代理，实际对这些数据进行分析，并生成一个HTML视图，这样你就可以可视化数据。

<details>
<summary>Original English</summary>

**Claire Bell**: Got it. So what you've done here is you've taken some raw data from **cursor**. you've asked one kind of agent to do a cohort-based analysis and generate a enriched CSV essentially with some data and then you're kicking off another agent to actually do the analysis on that and generate sort of an HTML view of it so you can visualize the data.

</details>

**Chintan Turakhia**: 完全正确。完全正确。它所做的是，生成的Python脚本，对吧？它找到了这些自然的群体，这些超级用户、普通用户、高级用户、轻度不活跃用户的自然群体。再说一次，这只是示例数据，但它是基于真实信息、真实模式、真实**Cursor**数据字段的。它得出的结论是，在示例数据中，70%是代理重度用户，20%是极少使用用户，4%是平衡用户。我们在示例中还有一些改进空间，对吧？比如，使用它的人还不够多。嗯，所以它做了一些分解，我有点喜欢，你知道，有点像指标回顾。是的，我们在这个数据中有很多行代码。我们有520个高级用户。再说一次，都是编造的名字，但这个人表现非常出色。我想知道这个编造的人，**Gabriel Diaz**，在做什么，对吧？这里很棒的一点是，它生成了一个小小的可视化仪表板。没什么花哨的。只是一个非常简单的东西，可以查看，对吧？总行数、编写器行数、Tab完成率，一些分解，一些关于层级和使用情况的结构化数据，对吧？但我真正想了解的是，**Gabriel Diaz**在做什么，对吧？这个虚构的用户，他表现得非常出色。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: That's right. That's right. What it did was the Python script that was generated, right? It found these natural cohorts, these natural cohorts of super user, regular user, power user, light inactive. Again, this is just honestly sample data um but based on like real information, real schema, real **cursor** um data fields. And it came up with like 70% are agent heavy in the sample data, 20% are minimal, 4% are balanced. We have some room to improve here on the sample, right? Like not enough people are using it. Um, and so it does a bit of a breakdown which I kind of like, you know, kind of a recap of metrics. Yeah, we have a lot of lines of code in this data. We have 520 power users. Again, madeup names, but like this person is crushing it. I want to know what this madeup person, **Gabriel Diaz**, is doing, right? Awesome thing here. It generated a little uh visual dashboard. Nothing fancy. something just really simple to look at, right? Total lines, composer lines, tap completion, a little bit of breakdown, some structuring on the tiers and usage, right? But what I really kind of want to understand is like what is **Gabriel Diaz** doing, right? This madeup user who's just like crushing it.

</details>

**Claire Bell**: 是的。如何根据数据为每个用户群体生成指导，告诉他们应该做什么才能晋升为超级用户？我正在寻找明确的指导，实际上我想把这变成某种操作手册，对吧？所以我们让它运行，同时我还想做的是，我喜欢可视化，这里有一些直观的东西，就像我们看数据本身一样。

<details>
<summary>Original English</summary>

**Claire Bell**: Yep. How about based on the data generate guidance for each user cohort what you know they should do to advance and graduate to super user I'm looking for explicit guidance effectively like I want to turn this into some type of playbook right so let's let this cook and then in parallel what I also want to do is I like visuals and there's something intuitive here where like as we look at the data itself

</details>

**Claire Bell**: 对吧？我们知道，通往这个超级用户的路径并不是线性的，不是从不活跃到轻度到普通到高级再到超级。我们知道它不是那样的线性路径。对吧。对吧。可能有一些分支，从轻度用户直接跳到高级用户。普通用户似乎在分层上是平衡的，但我想知道的是，这些人正在做哪些特别的事情，以及我如何才能改变曲线，对吧？所以我也将并行提出另一个问题，比如创建一个美人鱼图，展示用户从轻度到高级用户可能采取的所有不同路径。我假设它不是线性的。我们来看看它会生成什么。好的。这真的在努力工作。真的在努力工作。

<details>
<summary>Original English</summary>

**Claire Bell**: right We we know that the like the path to this super user over here. It's it's not like you go inactive to light to regular to power to super. We know it's not linear like that. Right. Right. There may be like forks from light to straight to power user. Regular user seems to be like balanced on the taring, but what I want to know is like what are the special things these folks are doing and how do I sort of shift the curve, right? And so I'm also going to throw another question in parallel like create a mermaid diagram uh for all the different sort of paths a user can take from light to power. And it's I'm assuming it's not linear. And let's just see what this cooks up to. Okay. This is really working hard. Really working hard.

</details>

**Chintan Turakhia**: **Opus** 4.5。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: **Opus** 4 five.

</details>

**Claire Bell**: 是的。**Opus**真的在努力工作。但是，嗯，是的，我们看看它会走向何方。嗯，你知道什么真的很有趣吗？我给你一个更短的技巧。所以，我认为这正在生成的是一个HTML操作手册，你可以分享出去，里面有一些内容。我告诉你我会在这种情况下做什么，我做过几次，嗯，就像客户QBRs一样，我会说：“写一篇**Slack**帖子，我可以把它发到我的工程频道，里面包含一些统计数据，以及我们如何让人们从A到B。”它会为我写一篇简短的**Slack**帖子。所以，我喜欢这种想法，从CSV文件到深度分析，再到HTML可视化，再到我可以发到**Slack**的三个要点。是的。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah. **Opus** is **Opus** is really working hard on this. But um yeah, let's let's see where it goes. Well, you know what's really interesting? I'll give you a a a shorter hack on this one. So, I think what this is generating is like an HTML playbook that you could share out that has has things. I will tell you what I would do in this use case and I've done this a couple times um with c like customer QBRs is I say write a **slack** post that I can put in my engineering channel on a couple of these stats and you know how we can get people to move from A to B and it'll write me like a a short little **Slack** post. So, I I love this idea of going from something like a CSV to a really deep analysis to an HTML like visualization to like three bullet points I can send in **Slack**. Yeah.

</details>

**Chintan Turakhia**: 作为经理，这些步骤中的每一步都需要花费很长时间才能完成。而现在，你可以在**Cursor**中全部完成。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: And as a manager, each one of those steps would have taken just forever to do. And now you can get them all done in **cursor**.

</details>

**Claire Bell**: 是的。你知道，那真是太棒了，就像工作流Markdown文件的力量一样。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah. You know, that is that's like kind of the awesome thing is the power of something like a workflow markdown file.

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yeah.

</details>

**Chintan Turakhia**: 它的作用巨大。它绝对巨大。它正是你在这里描述的那种东西。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Is huge. It's absolutely huge. And it ex it's exactly like the thing you're describing here.

</details>

**Claire Bell**: 认识**Rovo**，你的AI队友，连接知识、人员和工作流，让团队更智能、更快地工作。它通过搜索、聊天、代理和工作室，帮助人们安全地、有上下文地找到答案、做出决策并自动化工作。**Rovo**运行在团队协作图上，这是**Atlassian**的智能层，它统一了你第一方和第三方应用程序的数据，因此没有知识会被遗漏。你总是能从第一天起获得个性化的AI洞察。最好的消息是，它已经内置在**Jira**、**Confluence**和**Jira Service Management**的付费订阅中。所以**Rovo**的力量已经触手可及。你知道AI从工具变成队友的感觉吗？如果你使用**Rovo**，你就会知道。探索**Rovo**。了解你业务的AI。由**Atlassian**提供支持。立即开始，访问rovo.com。那是rov，就像胜利的V，o.com。

<details>
<summary>Original English</summary>

**Claire Bell**: Meet **Rovo**, your AI teammate, connecting knowledge, people, and workflows so teams can work smarter and move faster. It helps people find answers, make decisions, and automate work securely and with context through search, chat, agents, and studio. **Rovo** runs on the teamwork graph, **Atlassian**'s intelligent layer that unifies data across your first and third party apps, so no knowledge gets left behind. And you always get personalized AI insights from day one. And the best news, it's already built into **Jira** **Confluence** and **Jira Service Management** paid subscriptions. So the power of **Robo** is already at your fingertips. Know the feeling when AI turns from tool to teammate? If you **robo**, you know. Discover **Robo**. AI that knows your business. Powered by **Atlassian**. Get started at rovo.com. That's rov as in victory o.com.

</details>

**Chintan Turakhia**: 让我们看看。让我们看看它得出了什么。对吧。而且你知道，没有人应该期望所有这些信息都是完美的。如果有人在想：“哦，天哪，如果**Cursor**能做所有这些，那我作为领导者的工作是什么？”那就像是：“好吧，你作为领导者的工作是去领导，对吧？去做出改变并产生影响，而这会加速它们。”所以不活跃的用户，是的，有点道理，你还没有安装，你还没有真正使用AI功能，最难的部分是开始。所以我有点喜欢这个，它给出了一些非常简单的提示，比如“下一次任务尝试代理模式”，非常非常简单。比如“等等，尝试一下Tab完成流程。”我有点觉得**LLM**真的想把这变成一个游戏，就像一个小小的任务或什么的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Let's see. Let's see what it came up with. Right. And like you know the the thing is like no one should expect all this information is going to be perfect. Like if anyone is thinking oh wow what is going to be my job as a leader if **cursor** can do all all of this it's like well your job as a leader is to lead right and to make change and and impact and this accelerates them so inactive users like yeah kind of true you haven't installed you haven't really used AI features yet the hardest part is getting started so I kind of like this it gives like just some very simple prompts try the agent mode for your next task something very very simple. Something like wait try a tab completion flow. I kind of feel like the the **LLM** really wanted to just turn this into a game like a little like a little quest or something.

</details>

**Claire Bell**: 是的，它有点游戏化了。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah, it's gified a little bit.

</details>

**Chintan Turakhia**: 是的，确实有点游戏化，而且很有趣。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yeah, it is. It is a bit gified and it's kind of fun.

</details>

**Claire Bell**: 好的，这很酷。它给了我一个**Slack**帖子。TLDDR（太长不读）

<details>
<summary>Original English</summary>

**Claire Bell**: All right, so this is cool. It's kind of given me like this would be my **Slack** post. TLDDR

</details>

**Chintan Turakhia**: 超级用户比其他用户多出16倍的AI代码行数。让我再放大一点。超级用户有更多的代理请求。我喜欢这个。停止打字。开始交付。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: 16x more AI line super users versus other users. Let me zoom in just a bit more. More agent requests for super users. I love this. Stop typing. Start shipping.

</details>

**Claire Bell**: 它是暗黑模式，所以工程师们会喜欢它。

<details>
<summary>Original English</summary>

**Claire Bell**: It's dark mode, so the engineers will just love it.

</details>

**Chintan Turakhia**: 是的。对。嗯，它很完美。然后你安装了**Cursor**，但你还没有使用AI。我们讨论过这个。这很酷。轻度模式。好的。你知道，这很能引起共鸣。停止说“修复这个bug”。实际上，像你对待初级工程师那样与它交流，对吧？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yes. Right. Um, it's kind of perfect. And then you installed **cursor**, but you haven't used AI yet. We talked about this. That's cool. Light mode. Okay. I, you know, this like resonates. Stop saying fix this bug. Actually like talk to it like you would maybe a junior engineer,

</details>

**Claire Bell**: 嗯，**Cursor**刚刚发布了bug机器人。我喜欢**Bugbot**。

<details>
<summary>Original English</summary>

**Claire Bell**: right?

</details>

**Chintan Turakhia**: **Cursor**。我喜欢**Bugbot**。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Um, **cursor** just did release bug bots. I love **Bugbot**.

</details>

**Claire Bell**: 代理不只是处理困难的事情，它适用于所有事情。这些现在就像励志名言一样，但我认为我们应该为它们制作海报并贴在墙上。嗯，编写单元测试，实际阅读评论。好的，酷。现在，高级用户，你们已经很棒了，要思考得更宏大，更努力地敲击键盘。

<details>
<summary>Original English</summary>

**Claire Bell**: **Cursor**. I love I love **Bugbot**.

</details>

**Chintan Turakhia**: 好的。如果**Cursor**在听，我想这会是你们新的周边产品线，伙计们。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Agent isn't for heart stuff, it's for everything. These are like motivational quotes now, but I think like we should just make posters for and put them up on the wall. Um, write unit tests, actually read the comments. Okay, cool. Now, power users, you're good to be great, think bigger, and to have harder.

</details>

**Claire Bell**: 我需要一顶写着“更努力地敲击键盘”的帽子。

<details>
<summary>Original English</summary>

**Claire Bell**: Okay, there. If **cursor** is listening, I think this is like gonna be your new merch line, guys.

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I need a hat that says tab harder.

</details>

**Claire Bell**: 好的。所以，再总结一下，我们正在为**Cursor**做免费的产品工作。我们，你知道，你的最终问题是，我如何提高这些工具的采用率？你当然会说，我将使用这个工具来理解采用情况，然后找出提高采用率的方法。我们进行了分析。我们创建了数据的可视化。你确定了用户群体和高级用户，如果手动操作，这会非常繁琐。

<details>
<summary>Original English</summary>

**Claire Bell**: Yes. Okay. So, just to just to recap again, we're doing we're doing uh free free product work for **cursor** here. We we took you know your ultimate problem was like how do I drive up adoption in these tools? And you're like of course I'm going to use the tool to understand adoption and then figure out ways to drive drive adoption. We did analysis. We created a visualization of the um the data itself. You identified cohorts and power users which would have been very tedious to do if you were going to do manually.

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yeah.

</details>

**Claire Bell**: 然后你创建了一个托管的操作手册。嗯，还有一系列励志名言，我们可以免费送给**Cursor**的朋友，或者现在就注册商标，赚点小钱。嗯，代理一切，不假思索地敲击键盘，**Bugbot**始终在线，迭代提示。我喜欢。

<details>
<summary>Original English</summary>

**Claire Bell**: And then you created a hosted playbook. Um, as well as a series of motivational statements which we can either give to our friends at **Cursor** for free or trademark right now and make a little a little money. Um, agent everything tab without thinking **bugbot** always on iterate prompts. Love it.

</details>

**Chintan Turakhia**: 而且，你知道，我认为有趣的是，让我谈谈我认为这个有趣的地方。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: And this, you know, again what I think is fun, let me talk about what I think is fun about this one.

</details>

**Chintan Turakhia**: 每一个担任工程领导职务的人都知道，这就是你被要求在董事会会议上展示的东西。你的老板会问你：“我们有多少工程师在使用**Cursor**？我们有高级用户吗？我们真的从中获得了价值吗？”我们现在谈论的是一个AI用例。但同样，在管理层中，实际上有一些可衡量的东西可以用来衡量团队的绩效和效率。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Everybody who has been in engineering leadership knows this is the kind of stuff you get asked to put in a board meeting. You get asked by your boss like what percentage of our engineers are using **cursor**? Do we have power users? Are we actually getting value? And we're talking about an AI use case right now. But again across management there are actually measurable things you can do about the performance and efficiency of your team.

</details>

**Claire Bell**: 是的。而且……

<details>
<summary>Original English</summary>

**Claire Bell**: Yes. And

</details>

**Chintan Turakhia**: 我认为这在以前是如此不可能实现。第二，如果你不能用代码来做，那就没意思了，而你现在可以用代码来做。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I think it been so impossible to get before. Two, it would be no fun if you didn't get to do it with code, which you get to you get to do with code.

</details>

**Claire Bell**: 实际上，现在可以用代码解决问题了，对吧？你可以直接做事情。我，你知道，你说得太对了。我想我低估了你现在所说的，我只想重复一遍，因为通常你会遇到这个问题，然后你不得不找一个个人贡献者来做，就像……

<details>
<summary>Original English</summary>

**Claire Bell**: Actually, that is solve problems with just code now, right? You can just do things. I I you know, you're so right. Like I I think this I underappreciated what exactly what you're saying right now and and I just want to repeat it because normally you would be asked this and then you would have to go pull an IC to do that and like what what

</details>

**Chintan Turakhia**: 拜托，不，你现在就可以做事情了。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: like come on like no you can just do things right now.

</details>

**Claire Bell**: 嗯，而且，再说一次，这就像，我想人们低估了创造一个有趣任务的速度。

<details>
<summary>Original English</summary>

**Claire Bell**: Well and and again it's like not I I I think people underappreciate the velocity creation of a fun task.

</details>

**Chintan Turakhia**: 是的。这就像，归根结底，这很傻，但它也有一些有趣的小细节，你会觉得“太棒了，我想进入下一个级别”，因为我从这个暗黑模式的操作手册中获得了一点多巴胺，这有点好笑，而且我想人们低估了这种迭代速度，它可以通过快速反馈循环来实现。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yeah. which is like at the end of the day like this is silly but also the like little fun bits of it you're like great I want to go to the next level cuz I got like a little dopamine hit from this dark mode playbook that's kind of funny and I I think people underappreciate like that iteration speed that can just come with like a fast feedback loop

</details>

**Claire Bell**: 当你构建东西时，以及当你构建具有高质量的东西时，快速反馈循环，就像这样设计的东西，看起来比Google文档有趣得多。是的。

<details>
<summary>Original English</summary>

**Claire Bell**: when you're building something and the fast feedback loop when you're building something that has high quality against it which like something designed like this does is so much more fun to look at than a Google doc. Yeah.

</details>

**Chintan Turakhia**: 或者电子表格，或者仪表板。所以，我们做到了。我们做到了。我们，再说一次，你和我，我想我们是双子星。所以，我们大概可以一整天都聊我们觉得有趣的事情。但是，让我们来看第二个用例，我想人们会看到。让我们看看我们能多快地完成这个用例，你刚才谈到了从反馈到功能的速度。你说了些激进的话，你说：“我们正在真正压缩从反馈到功能的时间。”那么，这实际上是如何运作的呢？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Or a spreadsheet or a dashboard. So, we we did it. We did it. We again, you and I are twin stars, I think, here. And so, we can probably go all day on the things that we find fun. But, let's go to a second use case that I think people are going to see. And let's see how fast we can do this use case, which is you were talking about the speed of feedback to feature. And you you said some fighting words out there. You're like, we're really compressing the time from feedback to feature. So, how does that actually work?

</details>

### 从用户反馈到功能实现

**Chintan Turakhia**: 那些话确实有些激进。嗯，你知道，我想你明白这一点，对吧？你想为你的用户构建这个，对吧？你想尽可能快地创造出最好的产品。而让这个循环运作良好的方法，就是你对反馈的响应速度。好的。但我想从反馈通常是如何产生的开始，对吧？所以，你知道，正常的团队和文化上，你们会有内部测试（dogfooding）或bug修复会话，对吧？你们会开会或在一个房间里，不断使用产品，等等等等，然后有人必须在Google文档中收集bug，然后把这些Google文档中的bug输入到工单系统中，对吧？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Those were those were some fighting words. Um, and you know, I think you know this, right? You want you want to build this for your users, right? And you want to create the best damn product out there as fast as possible. And the way to like make that cycle work really well is genuinely how fast you can move on feedback. Okay. But I want to start from how does like feedback even normally come in, right? So you you know normal like teams and and culturally like you'll have dog fooding or bug bash sessions, right? You'll get on a meet or get in a room, keep using the product, blah blah blah, all that jazz and then someone has to like collect the bugs in a Google doc and then take those bugs in a Google doc and put them into a ticket system, right?

</details>

**Claire Bell**: 哦，好的。然后就会有一场关于“这重要吗？这不重要吗？我们应该在这个冲刺中处理它吗？我们应该等到下一个冲刺吗？”的讨论。到那时，你的用户已经离开了。他们会说：“你们没有修复这个问题。我有点讨厌它。我要走了。”对吧？每个人的注意力都非常非常短暂。现在，整个团队，我们都在为一个大型发布做准备。嗯，我们想聚在一起做一件叫做“激增”（surge）的事情。这就是我们把团队召集起来，使用所有这些AI，进行非常非常长时间的工作，然后发布大量的代码。嗯，有趣的是，在这些激增期间，我们最终在相同的时间内发布了三到四倍的PR量。但我们还想做另一件事，就是把人们带到办公室，我们设置了一个叫做“反馈咖啡馆”的东西。所以我们会邀请外部人员、内部人员等等。我们和他们一起进行内部测试，我们向他们展示应用程序，就像这里有几秒钟的展示，你知道，它看起来是什么样子。我们就站在那里收集信息，做所有这些实时内部测试。但最难的部分是，尤其是在现实生活中。你如何实际捕捉这些信息？因为它有声音，有视频。你如何将其转化为一个系统？好的。所以，我花了一个周末的时间，构建了一个工具来实时捕捉反馈。我们随便选一个。我将选择一个新东西。我将选择“我如何AI与**Claire**一起测试”。

<details>
<summary>Original English</summary>

**Claire Bell**: Uh okay. And then there's a whole discussion around is this important, is this not important? Okay, should we pick it up in this sprint? Should we wait for another sprint? And by that time, your user has turned out. They're like, you guys didn't fix this. I kind of hate it. Moving on, right? Everyone's attention is like so so so short. And right now, like the whole team, uh, we're all preparing for a big launch. Um and we wanted to get together and do this thing called a surge. And this is where we like just bring the team together and we do very very long days um using all this AI and just shipping like massive amounts of code. Uh and fun fact like during these surges we end up shipping like more than three to 4x more PR volume in the same time. But the other thing we wanted to do was bring people into the office and we set up this thing called like a feedback cafe. So we'd invite externals, internals, etc. And we dog food with them and we'd show them the app and like here's just like a couple seconds of, you know, what it looks like. We're just standing there collecting information doing all this like live dog fooding. And the hard part though is especially in real life. How do you actually capture that information? Because it's voice, it's video. How do you translate it into a system? Okay. So, I just spent like half a weekend and built a tool to capture feedback live. Let's just pick something. I'm gonna pick I'm gonna I'm gonna pick a new thing. How I AI testing with **Claire**.

</details>

**Chintan Turakhia**: 太棒了。所以我们来做这个。它会创建一个小会话。完美。非常简单。我们有两种模式。你可以，你可以在手机上使用这个。团队在现实生活中就是这样做的。但对于这个，我将捕捉一些音频。让我们看看实际情况是什么，也许我可以听听你有什么有趣的小bug或者你认为你想修复的产品问题。所以我们将开始捕捉音频。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Awesome. So, let's do that. It's going to create a little session. Perfect. Very simple. And we have two modes. You can like you can use this on your mobile phone. That's what the team did uh when they were in real life. But for this, I'm just going to like capture some audio. And let's see what's what's actually maybe I can just hear from you like a fun little bug or something uh of a product that you you think you want to fix. So we're going to start capturing audio.

</details>

**Claire Bell**: 我使用的一个AI聊天机器人，当我的账户切换到商业账户时，会强制我清除所有聊天记录。我认为我们应该修复这个bug，这样我就可以访问我现有的聊天记录了。

<details>
<summary>Original English</summary>

**Claire Bell**: There is a AI chatbot that I use where my account when switched to business account forces me to clear all my chats. And I think we should fix that bug so that I can access my existing chats.

</details>

**Chintan Turakhia**: 我们将开始捕捉音频。我们将，好的，酷。我们捕捉到了。它基本上是在获取音频。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: We're gonna start capturing audio. We're gonna Okay, cool. We captured it. It's basically taking the audio.

</details>

**Claire Bell**: 我做了一个系统提示。把它发送给一个**LLM**。嗯，然后我们所做的是，提示基本上是说去识别bug。是的。

<details>
<summary>Original English</summary>

**Claire Bell**: I did a system prompt. Sends it to an **LLM**. Um, and then what we do is it the prompt is basically saying go and identify the bugs. Yep.

</details>

**Chintan Turakhia**: 对。然后它就会创建。我将在它处理的时候再做一个。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Right. And then it'll create it. I'm going to do one while it's processing.

</details>

**Claire Bell**: 现在，我正在使用应用程序。我在交易标签页，我点击了“从”字段，我正在输入数字，但数字没有显示出来。所以这让我无法进行交易。所以我想在我们的第一个例子中，音频通过系统有点难捕捉。但我们来看看第二个例子。

<details>
<summary>Original English</summary>

**Claire Bell**: Right now, I'm using the app. I'm on the trade tab and I'm clicking the from field and I'm typing in numbers, but the numbers are not showing up. So that's not letting me make a trade. So I think in our first example, the audio is a little hard to capture through the system. But let's look at the second example.

</details>

**Chintan Turakhia**: 它非常清楚地指出了问题。在交易标签页，在“从”字段中输入数字不显示。用户无法发起交易。酷。非常非常清晰。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: It calls it out really clearly. On trade tab, typing into from field does not display enter numbers. User cannot initiate a trade. Cool. Really, really clean.

</details>

**Claire Bell**: 是的。

<details>
<summary>Original English</summary>

**Claire Bell**: Yep.

</details>

**Chintan Turakhia**: 我点击了“创建**Linear**工单”。它甚至给出了一个建议标题。我关心的用户旅程是交易。砰。我创建了工单本身。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I hit create **linear** ticket. It even gives like a suggested title. The user journey I care about for this is trade. Boom. I create the ticket itself.

</details>

**Chintan Turakhia**: 太棒了。我跳过去。工单都在这里。文件也在那里。**Linear**是一个令人难以置信的工具。它正在进行一些分类。但现在我想跳到的是，我们将直接创建PR。所以我们有这个我们内部构建的工具。我们称之为**Cloudbot**。它实际上使用了各种底层模型。嗯，它不是特定于**Claude**的。嗯，所以**Cloudbot**创建PR。我知道这个仓库是**wallet mobile**。这是工单。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Awesome. I hop over. The ticket is all here. The file is there. **Linear** is a incredible tool. It's doing some triaging. But the thing I want to now hop over to is we're going to just create the PR. So we have this tool we built inhouse. We call it **Cloudbot**. It's actually like using all sorts of underlying models. Uh it's not something that is specific to to to **Claude**. Um, so **Cloudbot** create PR. I know the repo for this is **wallet mobile**. And here's the ticket.

</details>

**Claire Bell**: 哦，那不是工单。

<details>
<summary>Original English</summary>

**Claire Bell**: Oh, that's not the ticket.

</details>

**Chintan Turakhia**: 工单在这里。太棒了。酷。所以，我刚刚从bug报告到工单。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: The ticket is boom. Here. Great. Cool. So, I just went from a bug report to ticket

</details>

**Claire Bell**: 到PR。

<details>
<summary>Original English</summary>

**Claire Bell**: to a PR

</details>

**Chintan Turakhia**: PR正在处理中。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: to the PR is cooking.

</details>

### 自建AI代理与工作流

**Claire Bell**: 好的。我必须暂停一下，因为如果你是《我如何AI》的新观众，你还没有看到我真正喜欢某样东西时的标志性动作，就是这个。我之所以这样做，是因为我刚刚在思考你左边这个小小的微应用，它就是实时用户反馈，完全非结构化，对吧？视频或音频。运行一个小小的**LLM**，不仅能得到问题的摘要，还能得到一个很好的修复建议。非常快速地“哔”一声就到了**Linear**。我们喜欢**Linear**的朋友们。我认为它是一个很棒的代理平台。然后你的**Slack**里有一个小的自定义代理，它可以读取那些**Linear**工单并直接执行它们。再说一次，过去可能留下了创伤，这个过程本来是有人手动总结研究会话的结果。

<details>
<summary>Original English</summary>

**Claire Bell**: Okay. So, I have to pause because if you um are new to how I AI, you have not seen my signature move when I really love something, which is this. And I was doing this because I was just thinking about this this little micro app that you have on the left side, which is, you know, live user feedback, totally unstructured, right? Video or audio. Run a little baby **LLM** on it. get not only a summary of the issue but a good recommendation on how you might fix it. Very quick beep boop to **linear**. We love our friends at **linear**. I think it's a great platform for agents. And then a little custom agent in your **Slack** that can read those **linear** tickets and just execute on them. And again so traumatized by the past maybe which is like this process would have been you know somebody manually summarizing

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yep.

</details>

**Claire Bell**: 写一份文档，有人实际做出明确的决定，包括什么，不包括什么。我想……

<details>
<summary>Original English</summary>

**Claire Bell**: what came out of a research session. Y some document being written somebody actually making explicit decisions about what to include and not include. I think

</details>

**Chintan Turakhia**: 决策过程消失了。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: the decision making is gone.

</details>

**Claire Bell**: 是的。

<details>
<summary>Original English</summary>

**Claire Bell**: Yeah.

</details>

**Chintan Turakhia**: 就像再也没有过滤器了。你不会再遇到那种“嗯，你知道，如果我写五页长，没人会读。所以我真的要专注于最重要的十件事。”现在是“让我们捕捉所有东西，然后直接处理掉。”然后我必须问你，你们为什么要构建自己的小机器人来做这个？构建这个机器人有什么优势？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Like no filter anymore. You don't get that like, well, you know, if I make this five pages long, no one's going to read it. So, I'm really going to focus on the top 10 things. It's like, let's capture everything and then just burn through it. And then I have to ask you, why did you all build your own little bot to do this? What was the advantage of of building the bot?

</details>

**Chintan Turakhia**: 所以，这是内部构建的。嗯，我们构建它，你知道，一切都始于今年年中左右。我创建了这个，我当时只是对AI非常着迷，我想：“我如何为团队、为公司创建更好的工具，让每个人都能加速？”所以我实际上发明了，我在**Twitter**上发出了一个号召，我发明了这个叫做“**Superb Builder**”（超级构建者）的角色，而一个**Superb Builder**唯一最重要的工作就是创造更多的**Superb Builder**。所以我们雇佣了我们的第一个**Superb Builder**，他们，嗯，我们讨论了一些想法，其中最重要的一点是，因为我们公司的大多数人都使用**Slack**。我们都在**Slack**里，而**Slack**，你知道，我坚信它只是一群人类假装成系统，对吧？在**Slack**里写东西的成本是零，但回答**Slack**里问题的成本是巨大的，而且大部分都是噪音，对吧？所以其中一件事就是，我们如何把我们都习惯的工作流，嗯，我们如何捕捉它，然后在上面添加AI。所以我们有各种各样的原因，我们知道很多公司都有后台代理，**Cursor**等等。嗯，我们现在只是有不同的安全要求，我们无法用它启动，这没关系。所以我们内部构建了这个，我们有这些反馈渠道，对吧？“嘿，这里有个bug，这里有个bug。”所以现在我们所做的就是，**Cloudbot**去处理它。或者如果有人，嗯，比如：“嘿，我们刚刚开完会。这是一份总结的会议记录。”我们就会说：“太棒了，**Linear**代理，把它分解成工单。”然后就像你展示的那样，对吧？每个人都在做那个“头脑爆炸”的表情符号，对吧？因为现在我们有20张工单，然后我们做一些有趣的事情，比如这样，就像发疯一样，我们只是启动了大量的调用，对吧？所以我们构建了这个计划模式。所以，这个机器人有一个“创建PR”的功能，它正在处理中。嗯，它还有一个很酷的功能是，当它完成时，它会回复，它会显示一个指向**Cursor**分支的链接，使用**Cursor**的深层链接。然后当一次性构建准备好时，它会显示二维码。所以你只需扫描就可以开始玩修复程序了，对吧？有一个计划模式，它非常类似于**Cursor**的计划模式。它只是提出了一个计划。然后我们也有“解释”功能，比如“哦，我想调试一些东西。”比如“为什么**Chintan**的应用程序现在不工作？”嗯，**Chintan.base**。举个例子，对吧？它拥有所有的技能，所有的MCPs。所以我意识到的是，上下文是最重要的东西。所以我们捕捉所有上下文的地方是**Linear**，然后你，我们构建的这个代理，嗯，我们添加了技能和MCPs。所以如果我们能通过**Linear**捕捉上下文，那么我们就可以使用**Linear**的所有上下文来触发代理，然后它会进入所有MCPs，比如**DataDog**、**Sentry**、**Amplitude**、我们的内部**Snowflake**数据库等等，它有能力从公司其他地方提取上下文，并且它可以在多个代码库中工作，然后砰，就像……它就像一个**Superb Builder**。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: So, this this is like in-house. Um, and we built it, you know, it all started um around like middle of this year. I created this like I I was just obsessing so much about AI and I was like how do I how do I create better tooling for the team for the company so everyone can be accelerated. So I invented actually like I put a call out on **Twitter** I invented this role called **superb builder** and the single job single most important job of a **superb builder** is to create more **superb builders**. So we we hired our first **superb builder** and they um we we talked about some ideas and one of the biggest things because most of our company uses **Slack**. We're all in **Slack** and **Slack**, you know, I'm like strong believer it's just a bunch of humans pretending to be systems, right? And the cost of writing something in **Slack** is zero, but the cost of answering something in **Slack** is enormous and most of it is noise, right? And so one of the things was just like how do we bring the workflows that we are all so used to um and how do we like sort of capture that and then add AI on top of it. So we had like various reasons we know like lots of companies have background agents **cursor** etc etc. Uh we just have like different sort of security requirements right now that we just couldn't launch with it and that's fine. So we we built this in house and we have these like feedback channels, right? Hey, there's a bug here, there's a bug here. And so now all we just do is like **cloudbot** go and do something with that. Or if someone is um like, hey, we just got out of this meeting. Here's a summarized transcript. We're like, awesome at **linear** agent, go break this down into tickets. Then just like you know, you know the look you you showed like right like everyone is just doing that emoji of like the head exploding, right? Because then now we have like 20 tickets and then we do fun things like this which is just go like bonkers where we just fire off tons and tons of calls right to just and so we we built this plan mode. So, this bot has a create PR, which I'm it's cooking. Um, it has a and also the cool thing about create PR is when it's done, it will respond back, it will show you a link to like the **cursor** branch using **cursors** deep link. And when then the oneoff build is ready, it will show the QR code. So, you can just scan and start playing with the fix, right? There's a plan mode which is very much like **cursors** plan mode. It just comes up with like a plan. And then we also have um explain as well where it's like oh I want to debug something. So like um why is **Chinten**'s app not working right now? Um **Chintton.base**. As an example, right? and it has like all the skills all the MCPS and so the thing the thing I realized is context is the most important thing. So the place where we capture all of our context is **linear** and then you this agent that we built um we added skills and MCPS. So if we can capture context through **linear** then we can trigger the agent uh using all the context from **linear** and then it goes off into all the MCPS like **DataDog** **Sentry** **Amplitude** um our internal **Snowflake** databases etc and it has the ability to pull context from the rest of the company and it can work across multiple code bases and then boom like it's it's like a it's a it's it's a **superb builder**.

</details>

### AI时代下的职业发展

**Claire Bell**: 这太棒了。所以，在我们继续之前，我想在这里指出几点，我希望大家没有错过。第一点是，现在如果我能给大家一些职业建议。

<details>
<summary>Original English</summary>

**Claire Bell**: This is this is awesome. And so before we move move on, I think what I want to call it here are a couple things that I hope people didn't miss. One is right now if I can give people career advice.

</details>

**Chintan Turakhia**: 你想成为你们工程组织中AI接受度最高的三个人之一。我很抱歉，我必须这么说。你知道，每当我把一个工程领导者或其他人拉到一边，他们可能对AI有点怀疑，然后我说：“我想让你来领导这个。”我不是在做这件事。是的，我当然想做，因为我认为它对公司有很大的影响，但我觉得我是在帮人们的职业生涯一个忙，把这个角色交给他们。所以，如果你能找到正在招聘**Superb Builder**的公司，他们会让你担任在整个组织中推动AI的角色，在那里你可以学习这些技能，我告诉你，这对你的整体职业生涯来说是一个巨大的好处。而且我认为人们没有意识到这在现在仍然是多么罕见。所以如果你能找到，我建议你直接冲过去。我想另一件事，我们已经看到几次了。我们看到**Amplitude**实际上做到了。对于组织来说，构建自己的代理并非不可能。所以，如果你有安全合规、数据访问限制，你不能使用云代理，你不能使用这些东西，那么自己构建这些东西并非不可能。而且现在也有很多非常棒的SDKs可以用来做这些。然后，你知道，第三点，我认为**Linear**和**Slack**这些平台只是减少了访问AI的摩擦。所以，如果你正在考虑在你的组织中推动AI的采用，那么请找出如何部署正确的平台，这些平台可以解锁对代理的访问，因为如果你要求某人打开或学习一个新工具，那只会制造太多的摩擦，阻碍前进。我想还有一件非常重要的事情，就像这个。这是一个我们称之为**Cloudbot Playground**的频道。我快速滚动一下，只是为了向你展示人们使用了多少。这是在一个晚上。我凌晨一点还在推送这个。我们从我给你展示的这个工具中发现了大约200个bug。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: You want to be like the the top three most AI pill in your engineering organization. I'm sorry. I just have to say it like I you know I whenever I you know pulled an engineering leader aside or someone aside who's like maybe a little AI skeptical and I said like I want you to lead this. I wasn't doing it. Yes, of course I want to do it because I think it has high impact on the company, but I felt like I was doing people a career favor by giving them this role. And so, if you can find companies that are hiring **superb builders** that will put you in the role of driving AI across an organization where you can learn these skills, I tell you it is a incredible benefit to your overall career. And I don't think people appreciate how much that is pretty still rare right now. So if you can find it, I would just beline directly directly to it. I think the other thing and we've seen this a couple times. We saw this **Amplitude** actually did it. Building your own agents is not impossible for organizations. And so if you do have security compliance, data access restrictions, you can't use cloud agents, you can't use these things, it is not impossible to build these things yourself. And there are lots of like really great SDKs out there too that you can use um to do so. And then you know three like I do think some of these platforms **linear** and **slack** are just friction reducers to access to AI. And so if you are thinking about driving AI adoption in your organization like figure out how you can get the right platforms in place that can unlock access to agents because if you ask somebody to open or learn a new tool it's just going to create too much friction um to to move forward. I think there's like one super important thing like this. This is a channel where we call **Cloudbot Playground**. And I'm scrolling through fast just to show you like how much people are using. This was one night. I was up at like 1:00 a.m. just pushing this. We got like 200 bugs, right, from this tool I showed you.

</details>

**Claire Bell**: 我只是在一口气把它们都启动了，让事情开始运转。这很棒。嗯，我们看看这里有没有计划出来。是的。所以，这里有一个计划，它实际上在**Linear**工单中创建了计划。

<details>
<summary>Original English</summary>

**Claire Bell**: And I just kicked them all off in like one solid go just to get things cooking. And like it was great. Uh let's see if a plan came out here. Yeah. So like there's a there's a plan that comes it actually creates the plan in the **linear** ticket.

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yep.

</details>

**Claire Bell**: 这里的诀窍是，为什么是**Slack**？因为**Slack**是公司内部事物传播开来的方式。

<details>
<summary>Original English</summary>

**Claire Bell**: This the trick here. Why **Slack** is because **Slack** is how things go viral within your company.

</details>

**Chintan Turakhia**: 完全正确。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Totally.

</details>

**Claire Bell**: 如果你把魔法拉到一个别人看不到的独立工具里。

<details>
<summary>Original English</summary>

**Claire Bell**: If you have pulled out the magic into some separate tool that others can't see.

</details>

**Chintan Turakhia**: 是的。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Yep.

</details>

**Claire Bell**: 它就不会发生。所以通过把东西放到**Slack**里，人们就会觉得：“天哪，这真的可能！我们上！”这真的很酷。

<details>
<summary>Original English</summary>

**Claire Bell**: It doesn't happen. And so by getting things into **Slack**, people just like, "Holy this is possible. Let's go. And it's like it's really cool.

</details>

**Chintan Turakhia**: 我完全同意。好的。所以，我们已经看到了工程方面我想看到的一切。但在我们离开之前，我想让你花几分钟谈谈一个个人用例。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I I completely agree. Okay. So, we have just seen about everything I wanted to see from the engineering side. But before we get out of here, I want you to spend just a couple minutes on a personal use case.

</details>

### AI的个人生活应用

**Chintan Turakhia**: 好的，我们开始吧。我想对每个人来说都可能引起共鸣的一个是，如果你有孩子，收到学校的邮件，里面说：“哦，这里有50个活动即将到来。嗯，这是日期。”我只是开始拍一张照片，然后把它扔到**ChatGPT**里，说“创建日历邀请”。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Okay, let's go. I I think the one that resonates probably for everyone is getting if you have kids, getting the school emails that it's like, oh, here are 50 events that are about to land. Uh here are the dates. I've just started taking a picture of it and then throw it into **chat GPD** and say create the calendar invites

</details>

**Claire Bell**: 100%。

<details>
<summary>Original English</summary>

**Claire Bell**: 100%.

</details>

**Chintan Turakhia**: 对。这就像是最蠢的事情，但天哪。然后共享日历的舞蹈就开始了，这太棒了。不过还有一件事，我喜欢美食和美酒。我真的很喜欢。而且，嗯，我做过侍酒师培训等等。我意识到，你知道，我最近和我的一个朋友去了纽约。他正在学习AI，但他问：“有哪些实际用例能引起我的共鸣呢？”我当时想：“嗯，人们最大的焦虑之一是，当他们去餐厅时，服务员递上酒单，对吧？他们会想，我该选什么？万一我选错了怎么办？”所以，嗯，我和我的朋友在纽约，我们去了一些香槟品鉴会。所以，我只是做了笔记。这里有一整本笔记本，对吧？我大约一小时前刚做完。我当时想：“哦，这是一个很棒的生产商。一颗星意味着‘是的，不错’。”然后是另一个。哦，看，我写了“太棒了”，就像这是我以前从未尝试过的人，但我非常喜欢他们的香槟。让我们看看。它就是超级美味。这是另一个。对。然后我基本上就是把它放进去，我说：“这是我品尝过的一堆香槟。从我的笔记中找出我的口味偏好。”

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Right. It's like it's the dumbest thing, but oh my god. And then the shared calendar dance happens and it's like it's so great. Another thing though, like I love food and wine. I really do. And like um I've done like Somalia training, etc., etc. And I and I realized like, you know, I went to New York recently with my one of my buddies. He's uh he's learning about AI, but he's like what what are some of the real use cases that would resonate with me? And I was like, well, like one of the biggest sort of anxieties people have is when they go to a restaurant, they're handed the wine menu, right? And they're like, what do I pick? What if I pick the wrong thing? So, uh, with my friend in New York, we went to some, uh, like champagne tasting. And so, like, I just took notes. There's like this whole notebook, right? I just did this like an hour ago. And I was like, "Oh, here's a great producer. Single star means like, yeah, it's good." And then here's another one. Oh, see I wrote amazing by like this is someone I've actually never tried before, but I loved loved their champagne. Let's see. It was just super yummy. Here's another one. Right. Effectively, then I just like popped this right in and I said, "Here are a bunch of champagnes that I tasted. Figure out from my notes like what are my taste preferences."

</details>

**Chintan Turakhia**: 真的很简单。因为你知道，当我上侍酒师课程时，它教给你的最重要的事情就是描述你喜欢的东西的词汇，对吧？然后我只是拍了图片，它就识别出了生产商，而且这实际上非常准确。我在纽约和我的朋友做了一件有趣的事情，他实际上是**ChatGPT**的现实版本，这也是启发我做这件事的原因，他总是试图找出我的口味偏好，所以你知道，这是我最强的信号。我喜欢那些糖分很少，非常成熟、酸度高的葡萄酒。我喜欢一些陈年酒。我喜欢种植者香槟，对吧？种植者香槟，而不是那些非常甜的大酒庄。它甚至深入到某个子类别，比如粉笔风格。这是我写了“太棒了”的特定生产商。它还指出了我在现实生活中学到的一点，那就是我确实喜欢黑皮诺，但只有在具有这种特征的情况下，对吧？有点疯狂。好吧，没关系。然后它就给出了一个香槟品鉴档案。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Really simple. Because you know like when I when I did like Somalia classes the biggest thing that it teaches you is the vocabulary to describe the stuff you like right and then so I just took the images it figured out the producers and this is actually like spoton the fun thing I did with my friend while I was in New York was like we were just he was he's he actually is the real life version of **chat GPT** and it's it's what inspired me to do this which is he's always trying to figure out my taste preferences and so you know this is like my strongest signal. I I love like these wines that have very little sugar that are like really ripering acidic. I love some aging. I love growers, right? Grower champagne, not like the big houses that are like very sweet. It even went into like a certain subcategory of like, you know, the chalky style. This is specific producer that I wrote amazing by for. And it also called out something I learned in real life, which is like I do like Pinoet, but only like with this sort of characteristic, right? Kind of crazy. All right, fine. And so then it came up with like a little bit of like a champagne profile.

</details>

**Chintan Turakhia**: 酷。如果我要买东西，你知道，这就是我会买的。所有这些都很好。好的。为什么会有人做这个呢？对吧？人们肯定在听，然后会想：“好吧，也许少喝点香槟吧，老兄。”但有趣的是，假设你去了餐厅，对吧？我只是为了这个例子在这里做了这个。你只是拍了一张酒单的照片，对吧？它是一份大大的旧酒单。有些酒单像字典那么大。有些很简单，但你不想做选择，尤其你只想和面前的人聊天，而不是盯着酒圣经。你把它放进去，然后砰，它实际会给出什么。我想我问的提示是：“从这个列表中我喜欢什么？哪些是好的选择？”它根据我的偏好非常快速地浏览了这些，而且很准确，我喜欢这个。我喝过，它很棒，很有趣。它还分享了价格。绝对是不用动脑筋的选择。另一个例子。另一个例子。然后它会更详细地分类，比如：“看，如果你想要一个性价比高的，并且想要很多瓶，那就选这个。每个人都会喜欢它。”“如果你想要更奢侈一点的，试试这些，对吧？”嗯，它非常详细地解释了你为什么会喜欢它。但我最喜欢的是它会说：“这些东西就别碰了，对吧？”你知道，如果这是一个重要的夜晚，那就买这六瓶酒，然后就完事了。所以，对我来说，这就是这里有趣的地方。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Cool. And if I'm buying stuff, you know, here's here's what I would buy. All of that's fine. Okay. Like why on earth would anyone do this, right? Like like people must be listening and be like, "Okay, maybe just drink a little less champagne, dude." But like the fun thing is let's say you took you went to a restaurant, right? And I just did this for this like example here. And you just like dropped in took a picture of uh the wine menu, right? And it's like a big old menu. Some of them are like size of a dictionary. Some of them are simple, but like you don't want to make a choice, especially you just want to be with like talking to the company that's in front of you and not like staring at the wine bible. You drop it in and boom, what it actually comes out with. And and I think the prompt I asked is what would I like from this list? What are good values? And it kind of just went through this really fast based on my preferences like and it's right like I would love this. I have I have had it and it's great and it's fun. It shares the price. Absolute no-brainer. Another example. Another example. And then it kind of gets into a bit more detail like categorically like look if you want a value one and just like want a bunch of bottles go for this. Like everyone's going to love it. If you want something a bit like more splurgy, try these, right? Um and very much like it kind of talks about what why you'll like it. What I love the most though says this is the stuff just to stay away from, right? And you know if it's a big night then just go get these six bottles and and call it a day. And so like that's the fun thing here for me.

</details>

**Claire Bell**: 所以我必须向大家指出的是，我们实际上以前见过这种流程，不是这个特定的用例，而是这种流程，就是你如何逆向工程自己的品味。我们看到**Whoop**的**Hillary**展示了如何逆向工程她自己在幻灯片上的品味。嗯，我忘了是谁逆向工程了摄影风格。嗯，**Ravi**逆向工程了摄影风格，然后说：“这是一张照片，告诉我如何描述它。”但你是第一个逆向工程自己葡萄酒品味的人，我喜欢这个，现在你可以……

<details>
<summary>Original English</summary>

**Claire Bell**: So what I have to call out for folks is we've actually seen not this particular use case but this flow before which is like how do you reverse engineer your own taste. So we saw **Hillary** at **Whoop** show how to reverse engineer her own taste on slides. Um we saw I forget somebody else reverse engineered photographic styles. um **Ravi** uh reverse engineered photographic styles and said like here's a photo like tell me explain to me how to how to describe this but you are the first person that has reverse engineered their own taste in wines and I love this and now you can

</details>

**Chintan Turakhia**: 选择美味的东西，你知道，下次我出去的时候，我会带上六瓶酒。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: pick yummy stuff to get for and you know what six bottle cart I'm going out with you next time

</details>

**Claire Bell**: 我知道我们会庆祝AI的采用之类的。

<details>
<summary>Original English</summary>

**Claire Bell**: I know we'll we'll we'll celebrate AI adoption or something like that

</details>

### 与AI沟通的技巧

**Claire Bell**: 这太棒了。我有两个闪电轮问题要问你。我们会把它们说得很短，然后让你离开。我的第一个问题是，如果你回顾两年前到现在的工作，你如何以不同的方式安排时间？所有这些是如何改变你个人时间的安排的？

<details>
<summary>Original English</summary>

**Claire Bell**: this has been so great I have one uh two lightning round questions for you. We'll keep them very short and then we'll get you out of here. My first one is if you look back two years ago to now at work, how are you how are you spending your time differently? Like how has all this changed how you personally spend your time?

</details>

**Chintan Turakhia**: 我的日历是空的。几乎是空的。原因在于协调开销，比如：“嘿，我们优先处理这个，我们改变这个，我们改变路线图。”不，你直接做事情。这是一点。第二，我写了更多的代码。团队知道，如果他们的贡献低于我，那我们就需要帮助AI，但你看，我也在参与。团队正在做非常非常艰苦的工作。我花更多的时间在代码库中，修复bug，尝试新事物，提出技术方法。我并不是要取代我团队中那些才华横溢、能力超强的工程师，但我能够更快地推动事情进展，并削减……

<details>
<summary>Original English</summary>

**Chintan Turakhia**: My calendar is empty. Like almost empty. And the reason why is cuz the coordination overhead of like, hey, let's prioritize this, let's change this, let's change the road map. No, you just do things. That's one. two, I'm writing way more code. The team knows like uh if their contributions fall below mine, like that's that's we we got to like help on the AI, but like look like I'm also jumping in. The team is doing incredibly hard work. I am spending way more time in the code base, fixing bugs, trying things, coming up with like technical approaches. I am not a replacement for like the insane amount of talented cracked engineers on my team, but I'm able to move things forward much faster and cut through the

</details>

**Claire Bell**: 如果AI为我们做了什么，取消会议将是我想要的礼物。好的，我的最后一个问题是，当AI不听你的话，当它给你的工程师提供一个非常愚蠢的操作手册时，你的提示技巧是什么？这取决于我尝试说服它的次数。但通常情况下，我会说：“好的，第一，你显然没有听我的。我说了什么。第二，是的，我知道我绝对是对的，但请不要再蠢了。我需要你的帮助。”第三，我喜欢核选项，我会威胁它，我说：“嗯，**Claude**，如果我正在使用**Claude Opus 4.5 High**，我就会说：‘好的，**Claude**，我将停止使用你，转而使用**Gemini**。’”然后它就会振作起来。

<details>
<summary>Original English</summary>

**Claire Bell**: If if AI has done anything for us, cancelling meetings would be would be the gift that that I want. Okay, my last question is when AI is not listening to you, when it gives you a really dumb playbook for your engineers, what is your prompting technique? It depends on like how many tries times I've tried to convince it. But generally, it's like, okay, one, you're clearly not listening to me. This is what I said. Two, yeah, I know I'm absolutely right, but like, stop being stupid. I need your help. And three, I I like the nuclear option is I threaten it and I say, um, **Claude**, if I'm using like **Claude Opus 4.5 High**, like, okay, I'm going to stop using you, **Claude**, and going to switch to **Gemini**. And then it gets its together.

</details>

**Chintan Turakhia**: 我喜欢它。我不知道这说明了我的育儿方式还是管理风格，但我认为它是有效的。嗯，这太棒了。我们可以在哪里找到你、你的团队，以及我们如何提供帮助？

<details>
<summary>Original English</summary>

**Chintan Turakhia**: I love it. I don't know what that says about either parenting or management style, but I think that is I think it is effective. Well, this has been great. Where can we find you, your team, and how can we be helpful?

</details>

**Claire Bell**: 是的。嗯，我在**Twitter**上，**Chintanakia**。我们正在构建**Base**应用。它以前被称为**Coinbase Wallet**。我想当这期节目播出时，它将向公众开放。使用它。它是一个恰好使用加密货币的消费者社交应用，它正在赋能创作者赚取收益并获得价值。嗯，我们很高兴能发布它，我们认为它代表了加密货币消费者应用领域的一个真正巨大的范式转变。所以请给我们反馈，试一试，发布，看看魔法发生。我们正在招聘两名出色的前端、后端、设计工程师、机器学习工程师、构建者。

<details>
<summary>Original English</summary>

**Claire Bell**: Yes. Um, so I'm on **Twitter**, **Chintanakia**. We are building the **base** app. It used to be known as uh **Coinbase wallet**. And I think by the time that when this uh episode airs, it will be live to the general public. Use it. It is a consumer social app that happens to use crypto and it's enabling creators to earn and be valued. Um, and we're excited to launch it and we think it's like a real big paradigm shift in crypto consumer apps. So give us a feedback, give it a shot, post uh see the magic happen. And we are hiring two uh cracked frontend backend design engineers ML engineers builders

</details>

**Chintan Turakhia**: **Superb Builder**。我有两个**Superb Builder**，很高兴能再招一个。但在这里这个团队工作真的非常非常有趣，而且会很棒。所以来吧。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: **super builders** I have two **super builders** happy to bring in a third one but like it is it is really really fun uh to work here on this team and and it it it'll be it'll be awesome. So come

</details>

**Claire Bell**: 谢谢你的加入。

<details>
<summary>Original English</summary>

**Claire Bell**: well thanks for joining us.

</details>

**Chintan Turakhia**: 谢谢。这，嗯，这是结束本周的好方式。

<details>
<summary>Original English</summary>

**Chintan Turakhia**: Thank you. This um this was such a a great way to cap off the week.

</details>

**Claire Bell**: 非常感谢您的观看。如果您喜欢本节目，请在**YouTube**上点赞并订阅，或者更好的是，给我们留言分享您的想法。您也可以在**Apple Podcasts**、**Spotify**或您喜欢的播客应用上找到本播客。请考虑给我们评分和评论，这将帮助其他人找到本节目。您可以在howiipod.com查看我们所有的剧集并了解更多关于本节目的信息。下次再见。

<details>
<summary>Original English</summary>

**Claire Bell**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on **YouTube**, or even better, leave us a comment with your thoughts. You can also find this podcast on **Apple Podcasts**, **Spotify**, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>