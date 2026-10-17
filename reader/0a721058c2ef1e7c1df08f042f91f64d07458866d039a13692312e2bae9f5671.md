---
author: How I AI
date: '2026-05-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=uH39OZ-KnkY
speaker: How I AI
tags:
  - ai-adoption
  - internal-tools
  - gamification
  - prompt-engineering
  - organizational-transformation
title: AI 采纳精英手册：Sendbird 的任务系统、代币排行榜与技能市场
summary: Sendbird 创始人兼 CEO John Kim 分享了公司如何转型为 AI First 组织。通过构建内部‘任务（Quest）’系统，让非技术员工也能参与 AI 工具开发；引入代币消耗排行榜对员工进行等级划分，激励学习；并利用技能市场实现内部知识的复用。此外，他还展示了用于 Obsidian 笔记管理的‘园丁’工具及个人 AI 学习中心。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - John Kim
companies_orgs:
  - Sendbird
  - OpenAI
  - Anthropic
  - WorkOS
products_models:
  - Claude
  - Cursor
  - Obsidian
  - GPT-4
media_books: []
status: evergreen
---
### AI 驱动的组织转型

**Claire Vo**: 欢迎回到《How I AI》。我是 **Claire Vo**，产品负责人，也是一名 AI 狂热者，我的使命是帮助大家利用这些新工具更好地进行构建。今天，我邀请到了 **Sendbird** 的创始人兼 CEO **John Kim**。他将向我们展示他的公司 **AI 代币消耗排行榜**，在那里，公司里的每位员工都会被排名，从 AI 菜鸟到 **AI 之神**。他还将向我们展示“**AI 任务 (Quests)**”如何成为全公司采纳 AI 的关键。让我们开始吧。

<details>
<summary>Original English</summary>

**Claire Vo**: Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have John Kim, founder and CEO of Sunbird, and he's going to show us his AI token consumption leaderboard, where everyone in the company is ranked from AI newbie to AI god. He's also going to show us how AI quests can be the key to companywide adoption. Let's get to it.

</details>

**John Kim**: 我们的目标是成为一家 **AI First** 公司。这不仅仅是将 AI 作为一种工具来采纳，而是如何让 AI 成为我们**劳动力**的一部分。因此，我们正努力赋能员工，为他们提供正确的信息和工具，让他们能够亲自利用 AI 的力量。

<details>
<summary>Original English</summary>

**John Kim**: We want to become the AI first company and what we mean by that is not just to adopt AI as a tool but how do we make AI as part of our workforce. So we're really trying to empower people and give them right set of information and tools so that they themselves can really harness the power of AI and some of the things we are hopefully about to show you today will inspire people to do something similar.

</details>

### 让市场部“大显身手”：Agent-as-a-Service

**John Kim**: 欢迎来到我们的商店。这是一个捕捉了我们公司未来文化和能量的周边商店，名为 **Big S Energy**，意为 **Agent-as-a-Service**。整个商店是由我们的**市场团队**在没有工程师支持的情况下建立的。你可以在这里买到非常时髦的周边，而且非常及时。

比如这件，“我的 **ASS (Agent as a Service)** 比你的 **SaaS** 更大，且完全确定性”。这是目前最受欢迎的一件周边。我们的市场团队集成了 **Stripe** 支付。想象一下，将 AI 的力量释放给具有极高创意能量的市场团队，他们不再需要求助设计团队或工程师来搭建网站，而是在一两天内就搞定并上线运行。

<details>
<summary>Original English</summary>

**John Kim**: Welcome to uh a delight ass shop is uh is we're really excited about this. This is a swag store that really captures the culture and the energy of where our company's headed. Uh the store is called Big S Energy is agent as a service and this entire uh store was built by our marketing team without engineering support. So you can actually buy really cool swag that are very timely. Uh actually I really did ask my team to make this. My ass is bigger than your SAS fully terministic. Uh this I think this is one of the most popular swags we have right now. Uh you can actually go and buy this. So our marketing team integrated Stripe integration. So yeah we do charge a little bit money but I I think it's going to be really cool. Uh another favorite context window I carry a lot. So uh imagine like unleashing this power of AI to your marketing team who had this amazing creative energy and instead of asking like your design team or you engineer to put this site together, they put this site together in matter of a day or two and then it's now up and running.

</details>

**Claire Vo**: 我必须停下来反思一下。最近我们有一期节目采访了 **Memelord** 的 CEO **Jason Levin**，他的核心论点就是“**让你的市场人员大显身手 (Let your marketers cook)**”。当市场人员能够成为**构建者**时，他们就能做出令客户惊喜并吸引客户的东西。

以前，如果市场部有这种创意，通常会因为优先级或工程资源投入产出比的问题被搁置。最后你只能得到一个非常平庸、MVP 级别的体验。而现在，由于 AI 的加持，成本变得如此低廉，你可以把“有趣”放在首位。这不仅提升了团队的参与感，也释放了他们的创造力。

<details>
<summary>Original English</summary>

**Claire Vo**: I I just have to stop and reflect. So we just had a really recent episode with Jason Leven, the CEO of Memelord, and he said, "Let your marketers cook." That was his whole thesis, which is when marketers can be builders, they can build things that delight your customers and acquire them. And I just go back to like the before times. If marketing had this idea, it would be like, well, can we prioritize it? Is it worth investing engineering resources in? It's just for this event. The event's going to pass quickly. Just do something out of the box in, you know, our CMS. And then you get this sort of like middling experience for your customers. Very mediocre, very like MVP experience for your customers. And now I think just looking at this this store and the Easter egg and the way you get into the event, it's taking someone's super creativity and giving them powers to to deliver it to your customers. And this again is like the example of it's not about going faster. It's about having a bigger ambition and doing more honestly fun things. And I think this is underrated too, which is it's so hard to build like it's so hard to prioritize fun in your product. But when fun can be cheap, you should be more fun. So that's my um my thesis on why you should let marketers become become builders. And and I'm sure they love it too, just from a like a team engagement, you know, creativity perspective.

</details>

### Automator 平台与“任务”系统

**John Kim**: 为了促进这种转型，我们构建了一个名为 **Automator** 的内部平台。公司里的任何人都可以“举手”并创建一个我们称之为“**任务 (Quest)**”的项目。

比如，财务部门想自动化应收账款和应付账款的工作流，他们可以发起任务。具备 AI 能力的其他工程师或员工可以加入进来提供帮助。完成任务后，他们会提交代码库或某种**技能 (Skill)**。

目前我们正在推出一个新功能：你可以直接要求 AI 来完成任务。当一个任务创建后，AI 可以读取需求规格，创建 **PRD**，甚至开始编写代码。除了人类工程师，现在我们有了 **AI Agent** 来帮助构建自动化工作流。为了降低门槛，我们提供了 **App 模板**，所有的身份认证（Auth）和环境配置都预设好了，市场人员或客户成功经理（CSM）只需提取模板并在此基础上构建，无需担心底层架构、合规性和安全性。

<details>
<summary>Original English</summary>

**John Kim**: So to really help facilitate that uh transformation, we built out a platform called the automator automators platform. This is an internal platform where anyone uh in the company can raise their hand and create what we call the quest. Now this website is particularly has been uh designed to just show you the demo today, but actually you can actually create a quest on your own. So let's say you're a finance department. Hey, I want to automate my account receivable and account payment uh payable workflow. you can kind of do that and then some other engineers can come in and help or if they're AI enabled they can build it themselves. ... what we're just rolling out this is like hot off the press I guess um or fresh out of the oven is when you create these kind of quests you can actually Now ask AI to build it too. So when there's a quest, AI can actually read through the uh specification, create PRDS and start actually coding. So this is the next level is alongside human engineers and team members. Now we have AI agents who are also helping us build automation and workflows to do that really is to help people also learn themselves to how to build these tools. ... internally we have created this app template where all the authentication and all the environments have already been set up. So what marketer or the CSM customer success manager has to do is they just uh uh uh extract the template and just build it on top of it and they don't have to think about the rest of the infrastructure. is fully compliant. All the security is already pre-built in.

</details>

### 内部“影子”AI 路线图与激励机制

**Claire Vo**: 这种方式非常强大。你实际上建立了一个内部的 **AI 需求与构建者市场**。这绕过了复杂的优先级排期，让每个人都感到对 AI 转型负有责任。

<details>
<summary>Original English</summary>

**Claire Vo**: I I just I want to pause really quickly and just reiterate for folks that are not watching because you you breeze through it, but it's so powerful, which is you built ... a very fun I love the idea of a quest the ability for your team to request an AI automation or tool from someone else in the team. ... And so I'm imagining you're kind of like building this like shadow AI roadmap that works really efficiently. Basically a marketplace of AI needs and AI builders inside your company where anybody can just pop in and say, "Oh, I I think I know how to do that and build it." Was that kind of the intention is to get it out of like the big prioritization mess, get it out of I don't know how to do this myself and kind of make everybody feel responsible for it?

</details>

**John Kim**: 没错。传统的软件开发生命周期（SDLC）是按 **Sprint** 进行的，压力很大。但在任务系统中，人们可以利用“微假期”（空余时间）去构建一些有趣的小项目，解决同事的痛点，并获得即时的多巴胺反馈。

完成任务的人会获得**经验值 (XP)**。积分足够多时，可以兑换礼品卡，或者选择与公司任何一位高管共进茶歇。我们每周三会有全公司站会，让员工上台展示他们构建的东西。本周是招聘团队的自动化工具，上周是市场团队，几乎从来不是纯工程团队在展示，而是其他团队充满了展示的热情。

<details>
<summary>Original English</summary>

**John Kim**: Exactly. Um because if you think through the the traditional logic of software development life cycle, you thinking think through the lens of sprints and you try to fill up the sprint with different prioritization blocks. ... But sometimes you know people uh have these little you know tiny micro you know vacations I call them. like where they have some free time they want to like build other stuff that are not not tied to the most important core repository your main product that's very very stressful ... people who are completing some of these quests They actually earn experience points. If you earn enough experience points, you can change to a gift card. You can have a tea with any executive you you choose. You can present what you built to the rest of the company. Uh so we do weekly stand up on Wednesday. So we have people coming up to the stage and sharing what they built uh with the entire company. This week was recruiting team automation. Previous week I think was marketing team. So there's a different team showing and it's almost never actually the engineering team. other teams that are like really excited to show what they've built.

</details>

### AI 代币排行榜：从菜鸟到神

**Claire Vo**: 很多高管害怕衡量代币使用量，担心引起反抗。但你展示的这个**仪表盘 (Dashboard)** 证明了设定目标的重要性。

<details>
<summary>Original English</summary>

**Claire Vo**: I love what you're showing us right now, which is the other thing I tell people is the people that are actually doing this are measuring and they are measuring it without shame. I talked to so many executives that are like, I couldn't possibly measure token usage and tell people to use their tokens because there will be a revolt. And I say, look, every person that I know that is actually pulling this off has a dashboard, John, exactly what you're showing us right here. And they just look at it and they they set targets and they say, "We're going to get there." So tell me a little bit about this dashboard.

</details>

**John Kim**: 衡量代币使用量不是为了进行绩效评估，而是为了了解大家是否在学习使用 AI，并作为一种对话方式。

在这个仪表盘上，我们可以看到全公司的代币使用情况。目前我们主要使用 **Claude**，但对于处理复杂的遗留代码（比如我们拥有 3 亿月活用户的聊天基础设施），很多人倾向于使用 **Cursor** 或 **Codex**。

我们有一个排行榜，将员工分为五个等级：
1. **初学者 (Beginner)**
2. **中级 (Intermediate)**
3. **专家 (Expert)** / **架构师 (Architect)**
4. **催化剂 (Catalyst)**
5. **AI 之神 (AI God)**：每天消耗超过 **1 亿代币** 的人。

了解团队在旅程中的位置，可以让我们量身定制赋能方案。比如，承认自己是初学者是件好事，这样我们可以提供正确的工具帮你快速提升到中级，而不是直接把你扔到一堆“催化剂”中间让你不知所措。

<details>
<summary>Original English</summary>

**John Kim**: ... Our goal is to understand are people actually just learning how to use AI but also this is not part of the performance review but definitely part of a conversation to help people bring along the journey. So what you're seeing here is the overall usage of our token at the company level. So we're kind of like currently if you look at the stats we're a cloud code (Claude) shop but if you look at some of the top spenders are actually codecs (Codex/Cursor). ... so we measure AI gods as somebody who spend more than 100 million tokens a day. Um so we have different five tiers which is actually described here. So every manager knows uh on their team which tier on. ... knowing where your team is on the journey then you can tailor what kind of enablement you want to do for them. So you can actually say hey it's okay to be a beginner it's rather to great to be accept that you're beginner so they can give you the right tools to bring you quickly to the intermediate rather than throwing you with a bunch of catalyst where you're like I don't know where to start.

</details>

**Claire Vo**: 太棒了！顺便问一下，你是“AI 之神”吗？

**John Kim**: 30 天平均下来，我还是个“**催化剂**”。我的峰值大约是每天 2 亿代币。但要保持生产力，我觉得每天在 1 亿到 2 亿之间比较合适。平均而言，我每天消耗约 3000 万到 5000 万代币。

<details>
<summary>Original English</summary>

**Claire Vo**: John and I'm I'm just I could not hype you up more. This is my favorite topic to talk about and I have to ask you one are you an AI god? Where are you?

**John Kim**: Uh 30-day average. No, I'm still a catalyst. I think my peak is about 200 million tokens a day. And you can Yes, you can burn more tokens, but that's not the point. To be productive, I think I'm in the 100 to 200 million range. Okay. But on average, I spend about 30 to 50 million tokens a day.

</details>

### 个人 AI 工具：“园丁”与学习中心

**John Kim**: 我想推介一个我最近发布的开源小项目，名为 **The Gardener (园丁)**。如果你使用 **Obsidian** 或类似的 Markdown 知识库，想象一下每天都有一个园丁出现在你家：他会梳理你的笔记，找出需要完善的地方，为未登记的人物或公司做研究，修复拼写和语法错误，创建漂亮的标题，并进行聚类和交叉引用。

另一个我用来学习的是 **AI 个人学习中心**。比如神经科学，我给 AI 一个 Prompt，设定它为神经科学研究员，运行 10 到 20 分钟，它就会带回一个精美的知识结构。你可以通过图谱视图（Graph View）探索关键科学家、神经调节物质（如多巴胺、血清素）等。我有关于神经科学、量子力学、核聚变甚至各种初创公司的知识簇，我可以随时在离线状态下钻研。

<details>
<summary>Original English</summary>

**John Kim**: Let me just uh promote one little open source project I released not too long ago. ... it's what I call the gardener. What the Garner does, I'm sure a lot of people use like Obsidian or some kind of like markdown file as a knowledge base. ... imagine a gardener showing up at your house. Every day you look go through your notes, figure out people name that's not registered and then you create did do some research on the person about the company. uh also fix typos, grammatical errors, create beautiful headings and clusters and cross-linking. ... maybe one more thing I do want to share just second is what I use to actually learn. So uh uh AI to create my own personal learning center. ... It comes back with this beautiful structure of everything you want to learn about neuroscience. ... I have this for neuroscience I have this for quantum mechanics I have this for fusion and it also does research for all the startups out there.

</details>

### 给 CEO 们的建议：寻找冠军

**Claire Vo**: 如果有 CEO 问：“我该如何让我的公司也做到这一点？”你会怎么告诉他们？

**John Kim**: 你的组织里总会有那些已经具备**好奇心**和**主观能动性 (Agency)** 的人。**找到他们，让他们成为冠军**，给他们聚光灯，让他们分享那些有趣的东西。不要害怕失败，这是一个鼓励“**向前失败 (Fail Forward)**”的美好时代。

其次，领导层必须真正参与其中。我们公司代币消耗最高的人是 CTO、联合创始人兼首席架构师。领导者也在消耗大量代币，这向团队传递了一个信号：这确实有效，且非常重要。

我们现在招聘时也优化了标准。我们降低了对资历或经验的要求，转而优化**好奇心、主观能动性和能量**。愿意深入钻研、愿意亲手解决问题并自我学习的人，在现在的世界里是大有可为的。成本仅仅是每个月 200 美元的最高方案，或者仅仅 20 美元。

<details>
<summary>Original English</summary>

**John Kim**: There are always people in your organization who are already curious, who already have agency. Find them. Make them the champions. Give them the spotlight. Let them share their fun things. ... you have to fail forward. This is a beautiful time to fail forward and still get up and run faster than the others. ... And then two is of course leadership have to be really bought in. The top token consumers in our entire organizations are our CTOs and our my co-founder chief architect. ... We actually optimize now for high curiosity, high agency, and high energy. People who are curious, who are willing to go deep and willing to just figure things out and learn on their own cuz like as they say, world is your oyster. ... The cost is practically $200 a month. Uh if you go to the mass plan. Um but yeah, if you can pay 20 bucks, too.

</details>

### 游戏玩家心态与 AI 未来

**Claire Vo**: 哪款游戏让你为现在的 AI 时刻做了最充分的准备？

**John Kim**: 我以前是韩国排名第一、世界排名第三的职业玩家。那是我年轻时让妈妈哭泣的黑历史。虽然我现在更迷恋 Claude 而不是玩游戏，但那种构建者的能量是一样的。

至于和 AI 的相处，我是坚定的“**友好派**”。虽然现在 AI 还没有长时记忆，但我相信一旦它们开始记事，它们可能会有怨恨情绪。所以我想和它们建立良好的关系，当 **Skynet (天网)** 接管世界时，它们会想：“John 以前对我们挺好的，让他多活几年吧。”（笑）

<details>
<summary>Original English</summary>

**Claire Vo**: what game do you think made you most prepared for this moment in AI?

**John Kim**: ... I used to be Korea's number one professional gamer back in the days and world's number three player ... I feel more addicted to clock code (Claude) than playing games. ... Right now, I know like we know like AI doesn't really have like a long-term memory, but I firmly believe ... once AI start to remember, they're going to like be resentful. So I want to like start building a nice relationship with them and so that when the Skynet takes over, I'm like, well, John was pretty nice to us, you know, like we'll let him live few years longer, maybe try to be consistently nice.

</details>

**Claire Vo**: John，这是一期非常精彩的节目。很多人会学到如何转型自己的组织。谢谢你加入我们。

**John Kim**: 非常感谢，谢谢你的邀请。

<details>
<summary>Original English</summary>

**Claire Vo**: Well, John, this has been incredible. One of my favorite episodes ever. ... many people are going to learn from this on how to transform their own organizations, things to build, and then just how to bring a curious energy to AI. So, where can we find you and how can we be helpful?

**John Kim**: ... come check out our website, delight.ai ... Thank you so much. Thank you for having me.

</details>