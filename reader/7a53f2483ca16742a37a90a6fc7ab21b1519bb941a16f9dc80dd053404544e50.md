---
title: "重塑企业AI：从代码助手到智能体工厂与工程师角色的演变"
summary: "本次访谈深入探讨了企业级AI的采用现状与未来趋势。核心议题包括软件工程向“智能体工厂”的演进、工程师从代码作者向智能体编排者的角色转变，以及在医疗等强监管行业中如何平衡合规与创新速度。专家强调了将领域知识转化为高价值判断力的重要性。"
area: "tech-engineering"
category: "ai-application"
project:
layout: post.njk
speaker: PCC
date : "2026-04-09"
tags:
  - "agentic-factory"
  - "enterprise-ai"
  - "software-engineering"
  - "regulatory-compliance"
  - "cognitive-labor"
people:
companies_orgs:
  - "Anthropic"
  - "OpenAI"
  - "Microsoft"
  - "Zendesk"
  - "McKinsey"
  - "UKG"
  - "PCC"
products_models:
  - "ChatGPT"
  - "Claude"
  - "Cursor"
  - "Gemini"
  - "Claude Code"
  - "Codex"
media_books: []
---

**David Pessis**: 大家好。这里只有很多早起鸟，让我印象深刻。

<details>
<summary>Original English</summary>

**David Pessis**: Hey, everybody. Only a lot of early birds here, I'm impressed.

</details>

**Pirasanna Sivalingam**: 可能是因为我们刚吃午饭，Dave。

<details>
<summary>Original English</summary>

**Pirasanna Sivalingam**: Probably because we're just having lunch, Dave.

</details>

**Marie Thurston**: 是的。

<details>
<summary>Original English</summary>

**Marie Thurston**: Yeah.

</details>

**David Pessis**: 是啊。把那个给他，Sri Ping，他马上就到，所以你们还有几分钟，你知道的，还有几分钟可以安静地吃完。我在吃酸奶。

<details>
<summary>Original English</summary>

**David Pessis**: Yeah. To get that to him, Sri Ping, he'll be here in a moment, so you guys got a few more, you know, a few more minutes to eat peacefully. I'm having yogurt.

</details>

**Pirasanna Sivalingam**: 我刚喝了一碗非常辣的番茄汤。

<details>
<summary>Original English</summary>

**Pirasanna Sivalingam**: I just had a very spicy tomato soup.

</details>

**David Pessis**: 那会让你清醒的，对吧？

<details>
<summary>Original English</summary>

**David Pessis**: I'll wake you up, huh?

</details>

**Pirasanna Sivalingam**: 是的。好的。

<details>
<summary>Original English</summary>

**Pirasanna Sivalingam**: Yeah. Okay.

</details>

### 企业AI的采用现状与组织惯性

**Srinivasan, Sri**: 嗯……我已经很久没见过比这更混乱的地方、更混乱的工作场所了。然而，他们的收入刚刚突破了 300 亿美元。大约 14 个月前，他们的收入还只有 10 亿美元。他们在这么短的时间内实现了 30 倍的增长。你可以大致体会并理解他们所做的事情。另一方面，如果你看看美国公司对 AI 的采用情况，大约 47% 的公司至少拥有 10 个用户的 **ChatGPT** 许可证，这就是衡量标准。从 26% 上升到这个数字，对于一个财务人员来说，这就像是，哦，惊人的增长。但对于像我这样在企业里的人来说，这显得有些平淡。问题出在哪里？

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Um... I haven't seen a more chaotic place, workplace in a long time. And yet they've just breached north of 30 billion. About 14 months back, they were about a billion dollars in revenue. They've gone 30X in such a short period of time. You can kind of relate and understand what they've done. And on the flip side, if you look at AI adoption in US companies, it's about 47% of companies has at least a 10 user license of ChatGPT, that's the measure. up from 26% for a finance guy that is like, oh, amazing growth. But for a person like me in the enterprise, that's tepid. What's wrong?

</details>

**Srinivasan, Sri**: 模型的表现非常好。但在企业中的采用率却很低，我把这归咎于组织惯性。现在整个企业界落后的，基本上是一个在企业中普及 AI 的计划。而这基本上是我们所有人的机会空间。好的。现在，这些模型已经存在了三年半。在前三年里，它就像是自动补全和一堆其他东西。让我们以软件工程为例。它们当时并不好用。它们擅长补全你的一行代码，补全你的代码。然后突然之间，发生了一些事情。那件事发生在 12 月底，或者 11 月、12 月。结果发生的事情是……

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: The models are doing really well. The adoption in the enterprise is low, and I chalk it up to organizational inertia. What is lagging now across enterprises is basically a plan to diffuse AI in the enterprise. And that's basically opportunity space for all of us. Okay. Now, the models have been around for 3 1/2 years. And for the first three years, it was like autocomplete and a bunch of other things. So let's take software engineering as an example. They were not useful. They were good at finishing up your line, finishing up your code. And then suddenly something happened. And that something happened at the end of December, November, December. And what ended up happening was...

</details>

**Srinivasan, Sri**: 这些人创造了“脚手架”（Harness）的概念。**Claude Code** 是一个脚手架，**Codex** 是一个脚手架，**Cursor** 也是一个脚手架，这些脚手架的作用，我能想到的最好比喻是，它们是隐藏模型内部运作并在其之上完成所有脏活累活的东西，是其之上的软件层。它基本上管理重试，让你得到你想要的结果，拥有上下文和记忆以及所有这些东西。这导致了，例如，Claude Code。你知道，现在代码都在那里了。其中一些代码相当糟糕，你知道，深层的重试循环和所有那些东西。但是，尽管如此……在像 **Anthropic** 这样的地方，有“免提工程师”（hands-free engineers）。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: These guys created this concept of a harness. Claude code is a harness, codex is a harness, cursor is a harness, and what these harnesses do, the best thing, the best analogy I have is they are the thing that hides the works of the model and does all the dirty work on top of it, the software layers on top of it. that basically manages retries, gets you to the outcome you want, has the context and the memory and all those things. And it led to, for example, cloud code. You know, now the code is all out there. Some of that code is pretty crappy, you know, deep retry loops and all that stuff. But, despite all that... There are hands-free engineers at places like Anthropic.

</details>

**Srinivasan, Sri**: **Zendesk**，我们的投资组合公司之一，有 300 名免提工程师。1800 名工程师中有 300 名是免提工程师。现在，这必须非常谨慎地进行。但请记住，这些 AI 实验室是我们所有人即将面临的行为改变的领先指标。几个月前，有过一场关于怀疑论者、AI 怀疑论者的讨论。如果房间里有 AI 怀疑论者，我会请你们思考一下。这和那些认为计算器在数学课上没有用武之地的怀疑论者是同一批人。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Zendesk, one of our portfolio companies, has 300 hands-free engineers. 300 are the 1800 are hands-free engineers. Now, it has to be done very carefully. But remember, these AI labs are leading indicators to behavior change that's going to be upon all of us. So a few months back, there was this discussion of skeptics, AI skeptics. If there are AI skeptics in the room, I will ask you to kind of think about it. This is the same skeptics who basically thought that calculators had no place in a math class.

</details>

### 软件工程的演进：智能体工厂

**Srinivasan, Sri**: 所以在我们前进的过程中，请保持这种视角。但这些自动化水平，如果我展望一年后，你将拥有 20 倍的代码量。我的水晶球告诉我，其中很大一部分代码将是 AI 产生的“垃圾代码”（AI slop）。如果我们作为工程师表现出色，不是作为代码作者，而是作为审查员、智能体老板以及这些智能体舰队的指挥官，如果我们以这种方式表现，我们就能减少垃圾代码的数量，并在我们所做的事情中推动更高程度的精确性。但在我看来，没有任何一种情况是……在成功的组织中没有**智能体工厂 (Agentic Factory)**。换句话说，成功的软件商店将变成智能体工厂。这是必须的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So keep that in perspective as we go. But these automation levels, if I were to look forward a year, you're going to have 20 times the code. A large portion of that code, my crystal ball says, is going to be AI slop. And if us as engineers show up well, not as authors, but as reviewers and agent bosses and commanders of these fleets of agents, if we show up that way, we'll have lower amount of slop and drive higher degree of precision in what we do. But there is no scenario in which I see. No agentic factory in successful organizations. Put another way, successful software shops will become agentic factories. That is a, that is a must.

</details>

**Srinivasan, Sri**: 所以。所以我想展示的是一个非常非常简单的图表。你们可以猜猜哪一波是哪一波，但这基本上是达到 1 亿美元收入的竞赛。最新的一波是最快的，达到 2 亿美元的恰好是 Cursor，不是 **OpenAI** 或者 Anthropic，或者这些公司中的任何一个，而是这些家伙，他们是最新且最快达到 2 亿美元的，这基本上说明 AI 现在比任何其他浪潮都要快。你知道，当年有工业革命，作为一个概念它开始得非常好。但花了大约 150 年时间，制造工厂才实现自动化，或者说蒸汽机花了 30 年时间才从演示变成在兰开斯特和曼彻斯特之间真正可行的东西，对于你们中那些对这个领域的历史感兴趣的人来说。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So. So the thing I wanted to put is a very, very simple graph. You know, you guys can guess which wave is which, but this is basically the race to 100 million in revenue. And the latest one is the fastest, 200 million happens to be cursor, not OpenAI or. Or anthropic, or any one of these, but these guys, these are the they are the latest and the fastest 200 million, uh, and that basically AI is now. faster than any other wave. You know, you had the Industrial Revolution back then, which kind of as a concept started really well. And it took like 150 years before kind of the manufacturing plant got automated or this, you know, 30 years for the Steam engine to go from demo to actually be real and viable between Lancaster and Manchester for those of you who are kind of history buffs on this space.

</details>

**Srinivasan, Sri**: 挑战依然存在，就像我说的，普及缺乏能力。而这种普及必须是你们所有人首要考虑的问题。它必须是，你知道，慈善始于家庭，在你们每天所做的每一件事中。你需要确保 AI 发挥着相关的作用。这事在我家里发生过。我有两个女儿。其中一个是 **Microsoft** 的软件工程师。而且，你知道，她是一个……她是一个 AI 怀疑论者。更确切地说，她曾经是一个 AI 怀疑论者。我看到她的一个挑战是，她觉得“我真的不想这么做。我喜欢编程这门艺术。我不想放弃它。”

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And the challenge remains, like I said, diffusion lacks capability. And that diffusion is something that has to be top of mind for all of you. It has to be, you know, charity begins at home in what you do every single day. You need to make sure AI. is playing a relevant role. I've had this happen to me at home. I have two daughters. One of them is a software engineer at Microsoft. And, you know, she's a... She's an AI skeptic. Rather, she was an AI skeptic. And one of the challenges I saw with her was, I don't really want to do this. I love the art form of coding. I don't want to give that up.

</details>

**Srinivasan, Sri**: 我发现的是，你知道，在她的团队里，他们开始衡量有多少人在使用什么 AI，人们使用 AI 贡献的比例是多少。他们把它变成了一个游戏化的练习。我女儿，我跟她说的每一句话都没有产生共鸣。在把她转变为 AI 用户这件事上，我可以说是一个彻底的失败者。但改变这一切的是游戏化。她是一个极具竞争心的人，她基本上会说，让我看看这是怎么运作的。现在她已经忘记了自己曾经是个怀疑论者。她告诉我 AI 的所有优点以及所有那些东西。所以这种普及是你们每个人每天都需要思考的事情。去尝试吧。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And what I found is, you know, in her groups, they started measuring how many people are using what AI, what percentage of AI contributions are people making. And they made it a gamification exercise. My daughter, everything I talked to her did not resonate. Let me call myself an abject failure on converting her to an AI user. But what changed was the gamification. She's a highly competitive person who basically said, let me see how this works. And now she's forgotten that she was a skeptic. And she tells me all the virtues of AI and all that stuff. So that diffusion is something each of you needs to think about every single day. Try it.

</details>

**Srinivasan, Sri**: 最初的尝试将会是失败的，坚持下去，然后你会看到更多的成果。因为在你真正做对之前，需要尝试六七次。一旦你做对了，一旦你给了它更多的上下文，记住，这就像训练一个中学生，最终把他们培养到大学水平，并基本上让他们为你高效工作。花点时间，这样你现在就可以说你在使用 AI，而要看到可能性的艺术，则需要更多的工作。所以普及是你在做事方式上的责任。当你这样做时，你为终端客户（护理机构、门诊护理机构）构建的产品，将会看到这样做的巨大好处。你所要做的就是，它是否有效？我问你们所有人，我恳请你们看看去年和今年的 API 数量。比较一下两者。在你们的环境中，它几乎增长了 20 倍，而且这不是因为客户对你们的查询变多了。这是因为 AI 初创公司在使用你们的数据。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: The first tries are going to be a failure, persevere, and then you will get to see more outcomes. Because it takes six or seven tries before you actually can get it right. And once you get it right, and once you give it a lot more context, remember, it's like training a middle schooler, eventually growing them into college, and basically making them effective for you. Spend that time so that. You can now say you're using AI and it takes even more work to see the art of the possible. So diffusion is your responsibility in how you do things. And when you do that, the products you build for your end customers, the nursing facilities, the ambulator care facilities, will see the benefit of doing so. All you have to do is, is it effective or not? I ask you all, I implore you to look at the API volumes last year and this year. Compare the two. It's nearly 20x in your environments, and it's not from customers querying you more. It's from AI startups using your data.

</details>

**Heather Addyson**: 是的。

<details>
<summary>Original English</summary>

**Heather Addyson**: Yep.

</details>

**Srinivasan, Sri**: 什么才是理所应当属于你的？Kate。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: What is rightfully yours? Kate.

</details>

### 现有企业的优势与确定性结果

**Srinivasan, Sri**: 其中一些已经展示了如何获得收入增长，你会看到更多，但这很大程度上是碰运气，就成功的初创公司而言，几率更接近买彩票。但对于每一个现有的业务类别，至少有 20 家初创公司在你们周围盘旋。至少 20 家，甚至更多。产品团队和你们的工程团队应该做的一个思维练习是，写下在你们周围盘旋的初创公司的地图，以及他们想从你们这里得到什么？他们想吃掉你们身体的哪一部分？所以，如果你借用 Pirasanna 的知识类比，对你来说，快速绘制出这个地图将非常有用，这样你就知道可以处理哪些生存威胁。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: A few of them have shown how to gain revenue traction, and you'll see many more, but it's a massive hit and miss, closer to like lottery ticket odds in terms of successful startups. But for every incumbent category, there's at least 20 startups hovering over you. At least 20, if not more. One of the thought exercises for the product team and your engineering team should be writing down the map of startups that are hovering around you and what is it that they want from you? What part of your body is it that they want to eat? So, if you kind of use the Pirasanna knowledge analogy, it will be very useful for you to basically map this out very quickly, so that you know the existential threats can be handled.

</details>

**Srinivasan, Sri**: 现有企业，我要谈的第三个类别，他们拥有所有的优势。今天成功的现有企业已经明白了 2 件事：如何使用他们的专有数据，如何使用他们的分销渠道，而他们学到的第三件事是进入市场的速度。这 3 件事是唯一重要的。专有数据。你们的分销渠道，也就是你们接触客户和网络的途径，最后是速度。速度是初创公司的盟友，而不是现有企业的盟友。对于这个房间里的每一个人，你们必须弄清楚如何提高你们做事的效率。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Incumbents, the third category I'm going to talk about, they have all the advantage. Successful incumbents today have understood 2 things. how to use their proprietary data, how to use their distribution, and a third thing they've learned is speed in the market. Those 3 are the only things that matter. Proprietary data. your distribution, that is your access to your customers and your network, and finally, speed. Speed is an ally for startups, not for incumbents. And for each one of you in this room, you've got to figure out how you increase velocity in what you do.

</details>

**Srinivasan, Sri**: 所以从消费者和企业 AI 中有一些经验教训。到目前为止，我们大多数人，我想说大多数，除非你是某个地方的穴居人，你现在已经把你谷歌搜索的一个词变成了 8 到 10 个词，不管你喜不喜欢，你都在和一个 LLM 对话。无论是谷歌搜索和 AI 机器人，还是 ChatGPT 或 Claude，我们所有人都已经习惯了。作为一个消费者，概率性的结果是行得通的。风险完全是你自己的。这是个人的。你可以接受幻觉，因为你某种程度上能识别它。如果你识别不出来，你就会有点生气。而且它使用的是公共数据，谁在乎呢？

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So there's some learnings from consumer and enterprise AI. Up until now, most of us, I would say most, unless you're a cave dweller somewhere, you're now changed your Google search one word to like 8 to 10 words, and you're talking to an LLM whether you like it or not. Whether it's Google search and AI board or ChatGPT or Clark, all of us have got used to it. As a consumer, probabilistic works. The risk is like completely yours. It's personal. And you can take hallucinations because you kind of recognize it. And if you don't recognize it, you get kind of miffed. And it uses public data, who cares?

</details>

**Srinivasan, Sri**: 在企业内部，有两种参与形式。一种是你的内部业务流程，渐进式的生产力提升。在那里，不准确是可以接受的。无论你是在工程中使用它，我确信每个使用过它的工程师都看到过 AI 会生成糟糕的代码。我遇到过这种情况，我实际上想让它实现一个信号量来管理 2 个会发生冲突的线程。它基本上放了一个 sleep 函数。拜托。所以我们都知道我们必须设法管理这些不准确之处。所以这是一个内部和外部上下文的明智混合，我们必须在中间的桶里进行管理。第三种，对于你自己的关键任务业务，作为你自己，**确定性结果 (Deterministic outcomes)** 是不可协商的。你绝对必须朝着那个方向前进。不准确是不可接受的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Within the enterprise, there are two forms of engagement. One is your internal business processes, incremental productivity. Inaccuracies are okay there. Whether you're using it in engineering, I'm sure every engineer who's used it has seen that AI will make up crappy code. I've had this situation where I actually wanted it to implement a semaphore instead to manage like 2 threads that were going to conflict. It basically put a sleep function. Come on. So we all know that we have to kind of manage these inaccuracies. So it's a judicious mix of context, internal and external, that we have to manage in the middle bucket. The third one, for a mission critical business yourself, as yourself, deterministic outcomes are non-negotiable. You absolutely have to head there. Inaccuracies are unacceptable.

</details>

**Srinivasan, Sri**: 现在有工具可以让你转向确定性，但这需要在脚手架开发、上下文图、反馈循环以及更多方面做大量工作。你的画布和你的直觉需要彻底改变，才能在企业 AI 上取得成功。这是一个完全不同的话题。如果你们感兴趣，我可以在这个话题上和你们聊上几个小时。实际上，我早些时候主持了一场会议，也许你们中有些人参加了。那场会议更深入地探讨了确定性结果的话题，最大化专有数据的潜力。我将在结束时的幻灯片中讨论一个不同的话题。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And there are tools now available for you to move to deterministic, but it requires a lot of work in terms of harness development, context graphs, feedback loops, and so much more. And your canvas and your instincts need to completely change for you to be successful with enterprise AI. Completely different topic. I can spend hours on that topic with you guys if you're interested. And I actually ran a session earlier that maybe some of you attended. That goes deeper into the topic of deterministic outcomes, maximizing the potential of proprietary data. I'm going to address a different topic in the slides that ends you.

</details>

**Srinivasan, Sri**: 那么，让我们谈谈……总结一下，总结一下企业采用方面正在发生的事情。首先，几乎所有的财富 500 强都在使用 AI 工具。每个人都在用。有模型公司。AI 前沿实验室、基础设施提供商从去年到今年已经将投资额增加了两倍，而且这种趋势还在增长。这不再是泡沫或虚假繁荣了。他们的收入在增长，数据中心满负荷运行。这不像互联网革命时期，康宁公司……

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So, let's talk about... you know, netting it out, netting out what is going on in terms of enterprise adoption. Firstly, nearly all of Fortune 500 are using AI tools. Everybody is. There is the model companies. The AI Frontier Labs, the infrastructure providers have tripled the amount of investment last year to this year, and that trend is only growing. This is not frothy or a bubble anymore. Their revenues are growing, and the data centers are running at capacity. This is not like the internet revolution where Corning

</details>

**Heather Addyson**: 啊哈。

<details>
<summary>Original English</summary>

**Heather Addyson**: Aha.

</details>

**Srinivasan, Sri**: 铺设了一堆没人用的管道。那种情况并没有发生。嗯……我的幻灯片过时了，Anthropic 现在估值 300 亿了。大约在二月中旬，他们达到了 200 亿。所以请想想正在发生什么。有人在大概 45 天内增加了 50%，不是几百万，是几十亿。想想那种规模。而且他们才刚刚触及企业市场的绝对冰山一角。那是一家专注于企业的公司。想想看……这会走向何方。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: laid out a bunch of pipe that nobody was using. That is not happening. Um... My slides are dated and tropic is at 30 billion now. About middle of February, they hit 20 billion. So please think about what is going on. Somebody added 50% in like 45 days, not in millions, in billions. Kind of think about that scale. And they're only touching the absolute. tip of the iceberg of the enterprise. That's an enterprise-focused company. Just think about... where this is headed.

</details>

**Srinivasan, Sri**: 我想 **GitHub** 发布了这个数据。你可以去看看。GitHub 上全球所有代码提交的 4%……是通过 Claude Code 完成的。百分之四，那是数百万，就像全球有 1 亿工程师一样。而且……这个数字正朝着 20% 以上迈进。到今年年底，智能体提交的代码将达到 20% 到 25%，甚至更高。不是辅助性的，我说的是智能体主导的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: I think GitHub publishes this data. You can look at it. 4% of all global code commits on GitHub. Game via Cloud Code. Four percent, that's millions, like you've got 100 million engineers worldwide. And... That number is headed to north of 20%. Agentic commits at the end of the year are 20 to 25%, if not higher. Not assistive, I'm talking agentic.

</details>

**Srinivasan, Sri**: 现在，智能体 AI 的三个阶段，我想我们都在经历。智能体已经存在了，但带有合适人类参与的自主编排智能体，才是我们前进的方向。我们已经开始看到它了。工程师，部分工程工作是自主的。Claude Code 的共同工作是 100% 由智能体构建的。人类没有写一行代码。我很惊讶它竟然这么糟糕。显然，它会改进的。但基本上，今天已经有……100% 智能体主导的工作软件了。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Now, the three stages of agentic AI, I think we are all living it. The agent is there, but the autonomous orchestrated agent with obviously the right human in the loop is where we are headed. And we were starting to see it. Engineers, parts of engineering is autonomous. Cloud code co-work was 100% agent built. A human did not put a line of code. I'm surprised how crappy it is. Obviously, it will improve. But basically, there is... Working software today. That is 100% agentic.

</details>

**Srinivasan, Sri**: 而且这种趋势只会加速。我不是想吓唬你们。我认为这就是现实。你必须基本上把它塑造成你所在类别想要的样子。我不是建议，请转向智能体并避开代码中的所有人类。那不是我的建议。在有适当护栏的情况下，最大化这些工具的潜力。并准备好迎接 10 倍的成果，这些工具将为你提供这些成果。你能够以比以前想象的快得多的速度编写代码并创建不仅是演示，而是真正能工作的软件。但这需要做大量的工作来设置上下文，正确设置这些工具，最重要的是，改变你们的文化。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And that trend is only going to accelerate. I don't mean to be 1 to scare you all. I think this is reality. You have to basically morph it to what you want for your category. I'm not suggesting, please go to agents and shun all humans in your code. That's not what I'm suggesting. With the right guardrails, maximize the potential of these tools. and be ready for 10x outcomes, which these tools are going to provide to you. You're able to code up and create not only demos, but working software at a much faster clip than ever thought of before. But it requires a bunch of work to set context, to set these tools right, and to most importantly, change your culture.

</details>

### 工程师角色的转变：从作者到编排者

**Srinivasan, Sri**: 那么，让我们谈谈工程。我想我谈到了那 4%，另一件正在发生的事情是……工程师现在是一个编排者，我会谈谈这个。全球范围内的人数影响更多是持平而不是增长，工程师的角色正在发生转变。所以在我们深入之前，我们每个人都需要基本上明确我们在这条曲线上处于什么位置，以及沿途的成熟度阶段。顺便说一句，如果你们有问题请打断我。我很乐意让这变成双向交流。David，如果有人提问我没看到，请提问并打断我。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So, let's talk about engineering. I think I talked about the 4%, the other thing that basically is happening is... The engineer is now an orchestrator, and I'll kind of talk about it. The headcount implications the world over is much more flat than growing, and the role of an engineer is shifting. So before we go there, Each of us needs to basically say where we are on this curve and the stage of maturity along the way. And by the way, please stop me if you have questions. I'm happy to make it bidirectional. David, if anybody has questions I can't see, please ask. and stop me.

</details>

**David Pessis**: 是的，大家，我只是想让你们举手，嗯，你知道的，尽管提问，我可以来主持。

<details>
<summary>Original English</summary>

**David Pessis**: Yeah, just, you guys, I just want to raise your hands, um, you know, go for it and I can uh, MC it.

</details>

**Srinivasan, Sri**: 好的，所以我认为这里的关键是你在成熟度曲线上处于什么位置？我对你们所有人的要求是，要进行深刻的自我反省和保持怀疑。我相信你们都遇到过那种打分最严的教授或学校老师。你们都记得那个时刻吗？在这条曲线上，请对自己扮演那个角色。放点好听的音乐，说，嘿，我是变革性的，而你却在代码里做自动补全，这毫无意义。这行不通。了解市场的发展方向。如果你在硅谷的泡沫里待过，那会有所不同，但他们是世界其他地方正在发生的事情的领先指标。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Okay, so I think the key thing here is where are you in the maturity curve? My ask of all of you is be deeply self-reflective and skeptical. I'm sure you all had this professor or school teacher who was like the worst grader. You all remember that moment? Please be that on yourself on this curve. There's no point in kind of playing nice music and saying, hey, I'm transformative and you're like doing autocomplete in your code. Don't work. understand where the market is headed. If you spend time in the Silicon Valley bubble, that's kind of different, but they are a leading indicator to what's happening in the rest of the world.

</details>

**Srinivasan, Sri**: 所以，正在发生且在很大程度上已经发生的一个巨大转变是，工程师不再是作者，工程师是编排者，是你的智能体指挥官、智能体老板，流程正在改变。我会说敏捷开发，你知道的，瀑布流以及我们拥有的所有这些其他方法论和方法，正在让位于智能体工厂。智能体工厂是未来的方向。技术不再是障碍。想法才是障碍。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So, one of the big shifts that has that is happening and has happened in large part is engineers are no longer authors, engineers are orchestrators, your agent commanders, agent bosses, and the process is changing. I would... say Agile and you know waterfall and all these other methodologies and methods we had are giving way to agentic factories. Agent tech factories are the way to go. Technology is no longer the impediment. Ideas are the impediment.

</details>

**David Pessis**: 你能说说，是的，你能详细解释一下什么是智能体工厂吗？

<details>
<summary>Original English</summary>

**David Pessis**: Can you say, yeah, can you explain more what an agentic factory is?

</details>

**Srinivasan, Sri**: David，这是一个问题吗？是的，智能体工厂就是我刚才展示的那种表现形式。这些脚手架的作用是，例如，Cursor 构建了一个浏览器。他们创建了一群智能体，这些智能体负责规划工作。他们唯一的重点就是规划并将工作分解成一个计划。然后有编码智能体，它们基本上获取计划的各个部分并进行架构设计或编写代码。有设计智能体负责评估可行性。有裁判智能体负责进行代码审查。有安全智能体负责检查提示词注入以及其他方法和机制。所以在这个过程中有测试智能体。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: David, is there a question? Yeah, agentic factory is kind of the representation I've laid out. What these harnesses do is, for example, Cursive built a browser. They created a swarm of agents, agents that were that did that planned the work. Their only focus was. planning and breaking up the work into a plan. Then there were coding agents that basically took pieces of the plan and architected it or wrote down the code. There were design agents that basically looked at viability. There were judge agents that basically did code reviews. There were security agents that basically looked at... prompt injection and other methods and mechanisms. So there were testing agents along the way.

</details>

**Srinivasan, Sri**: 所以把它想象成过去不同人类原型的集合，而这些是永远不知疲倦的智能体，它们 24/7 全天候工作，它们不抱怨。它们只管工作。它们听从你的指挥。所以把它想象成一个智能体工厂。你知道，其中之一，我确信你们见过这些表情包，机器人包揽了一切。这和那个非常相似，只不过是数字化的。而你则是那个通过六个不同驾驶舱的镜头观察它们在做什么的人。这现在已经成为现实。如果你在一个沙盒里使用 OpenClaw（可能是 OpenDevin/Claude 的口误），我就这么做过，我不建议在你的生产环境中使用它。目前还不建议。但我在沙盒环境中使用 OpenClaw，它太神奇了。它，我很高兴它是一个沙盒环境。它做了一些我无法控制的事情。它基本上跑遍了我桌面的每一个角落和缝隙，找到了我不知道存在的各种东西。这是因为有专门构建的智能体在做不同的事情，协同工作。这就是它们成为工厂的原因。David。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So think of it as... different past human archetypes where these are agents that basically never tire, they work 24-7, they don't complain. and all they do is work. They act on your command. So think of it as a factory of agents. You know, one of these, you know, I'm sure you've seen these memes where, you know, robots take care of everything. It's very similar to that, only digital. And you are the one watching through the lens of six different cockpits as to what they're doing. And that's real now. If you sit with OpenClaw, which I do, in a sandbox, I don't suggest using it in your production environment. Not yet. But I use OpenClaw in a sandbox environment, and it is amazing. It is, I'm so happy it's a sandbox environment. It does things that I can't control. And it's basically running into every nook and cranny of my desktop and finding things that I did not know existed. It's because there are purpose-built agents doing different things, working in unison. That's what makes them a factory. David.

</details>

**David Pessis**: 谢谢。

<details>
<summary>Original English</summary>

**David Pessis**: Thank you.

</details>

**Srinivasan, Sri**: 团队的形状和规模正在改变。它正在变成，你知道，基本上你的敏捷团队正在变成两到四个人。记住我说过技术不再是障碍。如果你有很多技术债务，它才是障碍。你必须基本上把那些削减掉。而想法是一个很大的阻碍。你需要更多的产品经理来思考想法，可行的想法。我对产品经理的另一个建议是，我见过一大批产品经理使用 Claude、**Gemini** 和 ChatGPT 来创建规范和其他东西。我想说那里有更多的 AI 垃圾。产品经理们，对你们的工作保持怀疑。工程师们，对那些工作要更加怀疑。找出特定规范中使用 AI 比例的最好方法是把它放进 **Quill Bot** 里，你就能弄清楚它是 100% 生成的，还是其中包含判断力。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And the shape and size of the team is changing. It's going, you know, basically your scrum team is basically becoming two to four people. Remember I said technology is no longer the impediment. It is the impediment if you have a lot of tech debt. You got to basically whittle that down. And ideas are a big blocker. You need more product managers to kind of think about ideas, viable ideas. The other thing I would recommend with product managers, I've seen a whole bunch of product managers use Claude and Gemini and ChatGPT to create specs and other things. I'd say there is more AI slot there. Product managers, be skeptical of your work. Engineers, be even more skeptical of that work. The best way to find out the percentage of use of AI in a particular spec is to put it through Quill Bot and you'll figure out whether it's like 100% generated or is there judgment in it.

</details>

**Srinivasan, Sri**: 所以我还会使用许多其他技术。我会，你知道，我对你们所有人的大问题和巨大要求是，怀疑精神，健康的怀疑精神，逆向思维将使我们在弄清楚如何在这个新世界中工作时变得更好。内部生产力的提升，哦，有个问题。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So there is many other techniques I would use. I would, you know, my big question to all of you and the big ask of all of you is, skepticism, healthy skepticism, contrarian thinking will make us better as we all figure out how to work in this new world. The gains in productivity within, oh, there is a question.

</details>

**David Pessis**: 哦，是的，请讲，Lucas。

<details>
<summary>Original English</summary>

**David Pessis**: Oh yeah, go ahead, Lucas.

</details>

**Lucas Westervelt**: 嘿，我只是想跟进一下关于智能体工厂的想法。这与我们在软件工程、DevOps 和 SRE 之间存在的一些传统孤岛如何共存？你是否设想这些角色也会被整合在一起？

<details>
<summary>Original English</summary>

**Lucas Westervelt**: Hey, just wanted to kind of follow up on that idea of the agentic factory. How does that sit with the traditional silos we have a little bit around like software engineering versus DevOps and SREs? Like do you envision those roles also being rolled up together?

</details>

**Srinivasan, Sri**: 是的。我认为这是因地制宜的，Lucas。答案可能是……专门构建的，我预计。你的 CI 部分是一个工厂，你的 CD 部分是另一个工厂。如果你让我来设计，我会这样设计。但你可以以任何方式设计它。如果它是一个管理一堆微服务的小团队，我会把它设计成一个工厂。但如果你在管理多个数据管道，多个代码库，它可能就是内部专门构建的工厂，Lucas。但请记住，你是在为你的客户成果设计工厂，而不是为你自己。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah. I think it's idiosyncratic, Lucas. The answer can be... purpose-built, I would expect. your CI portion of it to be a factory, your CD portion of it to be another factory. If you were asking me to design it, I would design it that way. But you can design it any which way. If it's a small team with a bunch of microservices, I would kind of design it as one factory. But if you're managing multiple data pipelines, multiple... code bases, it could be purpose-built factories within Lucas. But remember, you are designing the factory for your customer outcomes, not for yourself.

</details>

### 生产力提升与上下文构建

**Srinivasan, Sri**: 好的。工程领域的生产力提升是不均衡的。所以在这张图表中，我基本上要说现有代码库、新代码在 x 轴上，复杂性在 y 轴上。具有高复杂性的现有代码库需要，基本上是最大的瓶颈。因为部落知识都在你们的脑子里。所以我不知道你们有多少次会说，只有这个工程师知道这个。我不想碰这部分代码，因为它很脆弱。而懂它的工程师离开了，我不想碰它。你知道，同样的事情。你不想让 AI 碰某些东西。请不要相信这种说法，嘿，我可以阅读代码并弄清楚。它不能。它无法弄清楚数据的排列组合。你必须给它上下文。所以在高复杂性现有代码库的那个象限中，收益是最低的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: OK. The productivity gains in engineering are uneven. So in this chart, I'm going to basically say existing code bases, new code on the x-axis, complexity on the y-axis. Existing code bases with high complexity require basically are the biggest bottleneck. Because tribal knowledge is in your heads. So I don't know how many times you all will say, only this engineer knows this. I don't want to touch this area of code because it's brittle. And the engineer who knew it left, and I don't want to touch it. You know, the same thing. You don't want AI to touch something. Please don't fall for this thing saying, hey, I can read the code and figure it out. It cannot. It cannot figure out permutation combinations with data. You have to give it the context. So the benefits are the lowest in that quadrant of high complexity existing code base.

</details>

**Srinivasan, Sri**: 在构建新东西时，现有企业拥有与初创公司相同的优势。如果你在现有代码库的基础上构建新东西，上下文再次变得重要。所以我在许多地方看到的最佳实践是，有一些工程师团队，他们生活中的唯一目的就是将上下文构建到这些工具中。我的一个建议是，请不要让每个工程师自己去弄清楚上下文。那本身就是一种损失。集中进行上下文构建的工作。好的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Incumbents have the same benefits that startups do when building new stuff. If you're building new stuff with existing code bases, context matters again. So what I have seen as best practice in many places is there are teams of engineers that basically their sole purpose in life is to build context into these tools. The one recommendation I have is please don't have every engineer figure out context by themselves. That is a loss by itself. Centralize the act of context building. Okay.

</details>

**David Pessis**: 所以，Tri，我其实有个问题，因为我们非常强调卓越运营。这实际上意味着清理技术债务。因为正如你听到我们谈论的那样，我们需要在成为一个高绩效的 AI 优先组织之前，先实现卓越运营。那些低复杂性的东西。

<details>
<summary>Original English</summary>

**David Pessis**: So, Tri, I actually have a question because we have such an emphasis on operational excellence. It really means like cleaning up the tech debt. Because like, as you've heard us talk about, like we need to become operational excellent before we become a high performing AI first organization. The low complexity stuff.

</details>

**Srinivasan, Sri**: 是的。嗯。是的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah. Mm. Yeah.

</details>

**David Pessis**: 我想，那会是右下角的低复杂性吗？当我想到修复遗留代码时，那会是右下角使用 AI 达到 20 到 40% 有效性的地方吗？

<details>
<summary>Original English</summary>

**David Pessis**: I guess like, would that be like the bottom right little complex? Like when I think about fixing the legacy code, would that be that bottom right 20 to 30, 20 to 40% effectiveness using AI?

</details>

**Srinivasan, Sri**: 我会说既有 20 到 40% 的部分，也有低复杂性新代码的部分，因为当你在重新思考一些东西时，比如单元测试覆盖率，我认为那是低复杂性的新代码。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: I would say both 20 to 40% as well as on the low complexity new code side because when you're rethinking stuff, for example, unit test coverage, I think of that as new code low complexity.

</details>

**David Pessis**: 是的。

<details>
<summary>Original English</summary>

**David Pessis**: Yeah.

</details>

**Srinivasan, Sri**: 假设你正在重构一个单体应用并创建一个新服务。我认为那介于这两者之间。嗯……并且缓慢但肯定地将其进一步向左而不是向右移动。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Let's assume you're re-carving A monolith and creating a new service. I think of that as somewhere in the middle of those two. Um... And slowly but surely moving it further left than right.

</details>

**David Pessis**: 是的，好的。

<details>
<summary>Original English</summary>

**David Pessis**: Yeah, okay.

</details>

**Srinivasan, Sri**: 所以，这就是我的思考方式。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So, that's the way I think about it.

</details>

**David Pessis**: 谢谢。

<details>
<summary>Original English</summary>

**David Pessis**: Thank you.

</details>

**Srinivasan, Sri**: 顺便说一句，我没有捏造这些数字。这是来自麦肯锡等人做的一堆调查的经验数据，但我把它提炼成了这种框架。所以编码，工程是第一张多米诺骨牌。好的。从编码、软件工程本身有很多东西可以学。我认为主要要学的是，工程师是为自己构建的，但每一次击键都被用作反馈来让它变得更好。所以如果你和前沿实验室交谈，我经常觉得我在和这些人说克林贡语。你们中懂的人，就知道我在说什么。或者你可以去谷歌搜索一下克林贡语，看看我在说什么。因为他们说的是另一种语言。他们谈论**评估 (Evals)**。他们谈论原语。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And by the way, I didn't make up these numbers. This is empirical data from a bunch of surveys that McKinsey did, a bunch of other guys did, but I kind of mined it into this type of a framework. So coding, engineering is the first domino. Okay. There's a lot to learn from coding, software engineering per se. I think the main things to learn are engineers built it for themselves, but every keystroke was used as feedback to make it better. So if you talk to the Frontier Labs, I often feel that I'm talking Klingon with these guys. Those of you who know, you know what I'm talking about. Or else you can Google Klingon and find out what I'm talking. Because they speak a different language. They talk evals. They talk primitives.

</details>

**Srinivasan, Sri**: 评估在基本弄清楚你的智能体之旅是否有效方面至关重要。无论是在你的产品中还是在工程中，你都需要编写，获得正确的评估。把评估看作是你确保取得正确进展的终极测试。它们不仅是测试，它们还在定性地告诉你需要改进什么。所以把你的评估做对，我们正在举办一些关于这个话题的会议。如果感兴趣可以参加。但基本上把你的评估做对，就解决了 70 到 80% 的问题。这不仅适用于你的产品之旅，也适用于你的产品管理、AI 的使用、销售中的 AI、客户服务，所有这些部分，云运营，所有这些领域。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Eval is critical in basically figuring out whether your agentic journey is working. Whether it's in your product or in engineering, you need to write the, get the right evals. Think of evals as your ultimate test to make sure you're making the right progress. And they're not only tests, they tell you qualitatively what you need to improve. So getting your evals right, and we're running a few sessions on this topic. Join if you're interested. But basically getting your evals right is like 70 to 80% of the problem. And that applies to not only your product journeys, it applies to your product management, use of AI, AI and sales, customer service, all those parts, cloud ops, all those areas.

</details>

**Srinivasan, Sri**: 我要说的第二部分是……数据，非常非常重要。领域专家重要得多。技术不是障碍。上下文才是障碍。把那些漂浮在我们脑海中的东西带进来，这样水涨船高。你知道，这种“我对组织有价值因为我是专家”的观念，正在以非常快的速度被打破。你的价值是不同的。它不是专业知识，而是**判断力 (Judgment)**。这两者之间有很大的区别。高质量的判断力。所以在继续之前，我要稍微转到一个不同的部分，谈谈认知革命。有什么问题吗，David？希望我的时间把握得还可以。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Second part, I would say, is... Data, really, really important. Domain experts matters so much more. Technology is not the impediment. Context is the impediment. Getting, you know, the things that are floating around in our heads and bringing that in so that rising tide raises all boats. You know, this whole thing of, I'm valuable to an organization because I'm an expert. is getting debunked at a very fast pace. Your value is different. It's not expertise, it's judgment. And there's a big difference between the two. High quality judgment. So before I go any further, I'm going to flip a little bit to a different part and talk about the cognitive revolution. Any questions, David? And hopefully I'm doing okay on time.

</details>

**David Pessis**: 你讲了 30 分钟，还有 24 分钟。我现在没看到任何问题。

<details>
<summary>Original English</summary>

**David Pessis**: You're at 30, you got 24 minutes. I don't see any questions right now.

</details>

### 认知革命与服务型软件

**Srinivasan, Sri**: 第三，好的。好的，所以软件工程只是一个开始。好的。在所有类别中，你都有巨大的空白空间，你也可以看到你的类别在某个地方，实际上它属于其他类别。其他，还有后台自动化，收入周期管理 (RCM) 属于那个类别。但基本上所有其他类别，如果你看看 Anthropic 发布的 API 计数。它们都落后了。正确的脚手架还没有建立起来。那是我们的机会。不采取行动是有后果的。沉默中有一种复合效应，我会谨慎地描述这一点。我的意思是……你可能认为你所有的竞争对手都没有取得进展。但有人正在默默地取得进展，当他们带着成果出现时，你会措手不及。所以请采取行动，成为那个脱颖而出的人。嗯，在你们现在的领域。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Third, OK. Okay, so software engineering is just a start. Okay. You got huge white space in all the categories and you can see your category also somewhere actually it falls in the other category. The other and there's back office automation, RCM falls in that category per se. But basically all other categories, if you look at API counts as published by Anthropic. They're lagging behind. The right harnesses haven't been built yet. That's our opportunity. Not acting has an implication. There is a compounding effect in silence, and I'll be careful in describing that. What I mean by that is... You may think all of your competitors are not making progress. Silently, someone is making progress, and when they come out with outcomes, you're going to be caught flat-footed. So please act, be the one who breaks away from the pack. Um, in your area now.

</details>

**Srinivasan, Sri**: 很长一段时间以来，软件一直在尝试自动化。它只是虚有其表。它需要配置、集成管理、数据质量，所有你们每天都在处理的事情。然后是服务，基本上贝恩、波士顿咨询、麦肯锡，一大批人提供人类作为思考者，按小时收费。这对双胞胎正在走到一起。AI 关注的 10 万亿经济体是服务型软件。那就是成果，由智能体提供的高利润的高质量成果。这基本上是宇宙的中心。这几乎就是正在发生的事情。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: For a long period of time, software has kind of tried to automate. It's only flatter to deceive. It's required configuration, integration management, data quality, all the things that you all deal with on a daily basis. And then there has been services that basically Bain, BCG, McKinsey, a whole bunch of people have provided humans as thinkers charged by the hour. Those 2 twins are coming together. And the 10 trillion economy that's the focus of AI is services software. That is outcomes, high quality outcomes delivered by agents with high margins. That's basically the center of the universe. That is pretty much what's going on.

</details>

**Srinivasan, Sri**: 发生在编码上，也发生在销售上。如果你看看 **Gong**，例如，他们基本上是在卖给你入境线索。这就是他们在卖的东西。按市场类别划分。配置它，瞧，奇迹就发生了。所以你会看到这种情况发生。**Harvey** 在法律领域，他们卖给你的是作为服务的律师助理。所以你会看到服务型软件几乎在所有地方发生。AI 无非就是一种服务。将会发生的是，这些智能体基本上是为一个成果而专门构建的，为一项原本由市场上的真人完成的服务而构建的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: happened with coding, happening with sales. If you go through Gong, for example, they're basically selling you inbound leads. That's what they're selling. By market category. Configure it, voila, magic happens. So you're going to see this happen. Harvey in legal, they're selling you paralegal as a service. So you're going to see services software pretty much happen all over the place. AI is nothing but a service. What's going to happen is these agents are basically purpose-built for an outcome, for a service that was otherwise done by humans in the market.

</details>

**David Pessis**: 对。嘿，Sari，很快插一句，有很多关于专业知识与判断力的讨论，以及该如何思考这个问题。

<details>
<summary>Original English</summary>

**David Pessis**: Right. Hey, Sari, real quickly, there's a lot of chatter about expertise versus judgment and like how to think about that.

</details>

**Srinivasan, Sri**: 是的。是的，大量的讨论。我想我会说。判断力是在上下文中展现专业知识。这是最好的表达方式。换句话说……判断力被应用于通过智能体让你的工厂变得更好，在正确的时间、正确的地点进行良好的指导，或者你基本上允许你的护理人员或医生在你的流程中，在正确的时间、正确的地点提供判断力。如果一个医生从不使用他们的专业知识，那就不叫判断力。在正确的时间、正确的地点展现专业知识，这就是判断力。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah. Yeah, a huge amount of chat. I think I would say. Judgment is the exposition of expertise in context. That's the best way to put it. In other words... judgment is being applied to make your factory better with agents, directing well in the right places at the right times, or judgment that you basically allow your nursing staff to provide or your doctors to provide in your flow at the right time at the right place. If a doctor never uses their expertise, that's not judgment. It's exposition of expertise at the right time at the right place is judgment.

</details>

### 重新构想业务流程与未来机遇

**Srinivasan, Sri**: 你今天能做什么，必须做什么？我会说，你知道，在工程中部署 AI，保持非常怀疑的态度，采取正确的衡量标准。有两个衡量标准对我非常非常有用，那就是从想法到交付的交付周期，以及回归率。这是唯一重要的两件事。交付周期也有一个速度要素。如果你想添加一个子要素的话，这两个基本上会告诉你你的产品和工程是否做得好。我要说的另一件事是投资于你的人员。作为 AI 编排者，并不是说如果你 100% 的团队都在使用 AI，而且他们都用得很差，你就得不到好结果。但如果你让你团队中 5% 的人有效地使用 AI，你将创造出巨大的经济影响。所以我不想落下任何人，但要专注于那些真正关心的人，并以此为榜样来改变其他人。没有怀疑的余地。David，如果我说得太大声了，我道歉。没有那种余地。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: What can and must you do today? I'd say, you know, deploy AI and engineering, be very skeptical, have the right measures in place. Two measures that really, really have been useful for me, it's lead time from idea to delivery. and regression rate. Those are the only two things that matter. Lead time also has a velocity element to it. If you want to add a sub-element, those two will basically tell you whether your product and engineering is basically doing well. The other thing I would say is invest in your people. as AI orchestrators, it's not like if 100% of your team uses AI and they all use it poorly, you're not getting great outcomes. But if you get 5% of your team using AI effectively, you will create outsized economic impact. So I don't want to leave anybody behind, but focus on the people who really care and use that as example to turn the rest around. There is no room for skepticism. David, I apologize if I'm saying it's loud. There is no room for that.

</details>

**David Pessis**: 不，我认为我们正在做很多这样的事情。你知道，有很多实验正在进行，对吧？每个人都在使用 Claude，绝大多数人都在用。而且，我们每周都在分享经验教训，Sareen。所以我认为我们是，我无法指出那 5% 是谁。我认为这是一种，我们现在正处于那个旅程中。所以，你知道，这将会是，你知道，也许我们可以思考如何更有效地做到这一点，比如识别出这些属于那 5% 的超级用户，以及我们如何放大他们的作用，并在整个组织中分享这些知识。

<details>
<summary>Original English</summary>

**David Pessis**: No, I think we're doing a lot of that. You know, there's a lot of experimenting going on, right? Everybody's using Claude, like the vast majority. And like, we're sharing lessons every week, Sareen. So I think we are, I can't point to like that 5%. I think it's a, we're on that journey right now. And so, you know, it'll be, you know, Maybe we can think about how we do that more efficiently, like identify these power users who are, you know, part of that 5% and how do we multiply them and share that knowledge across the org.

</details>

**Srinivasan, Sri**: 是的，那太棒了。在生产力部分，我想留给你们的是回到同样的从渐进式到变革式的生产力。规划出你们所处的位置，什么业务流程，以及你们把什么推进到了什么程度。了解你们投资的影响以及你们正在产生的成果，这非常重要。所以几乎对于这些中的每一个，创建一个评估，描述这个评估，并定期衡量这个评估，以便在你们将 AI 引入时看到进展。AI 奏效的唯一途径是你们重新思考一个流程。记住，所有的业务流程都是在 1890 年代制定的。现在使用的那些，是由 **KPMG** 这样的公司在 80 年代和 90 年代制定的，它们是以人为中心的业务流程。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah, that's fantastic. And in the productivity piece, the thing I would leave you with is back to the same incremental to transformative productivity. Map out where you are and what business process and how far you're taking what. It's really important to understand. What is the impact of your investment and what is the outcome you're generating? So pretty much for each of these, create an eval, kind of describe the eval and measure the eval on a regular basis to see progress as you kind of bring AI into the fold. And the only way AI works is if you rethink a process. Remember, all business processes were laid out in the 1890s. The ones that are in use, they were laid out in the 80s and 90s by the KPMGs of the world, and they were human-centered workflows.

</details>

**Srinivasan, Sri**: 当你拥有一个智能体工厂时，我不确定以人为中心的工作流程是否还行得通。它行不通的。所以你几乎必须重新思考它。除非你重新思考它，否则请在设计方面花大量时间。如果你不在设计方面花时间，你就不会获得很多好处。所以不要拿着这些工具跳进来说，哦，我要应用它。仙女粉 AI (Pixie Dust AI) 会导致我所说的 AI 漂绿（AI whitewashing）。好的。这是一个长达数十年的机会。我想你们都知道这一点。我要说的一点是，进展不会是线性的。请不要因为在某个特定领域缺乏进展而感到失望。这只是 AI 的本质。需要尝试 5、6 次才能做对。然后突然之间，我的天啊，奇迹时刻发生了。在这个过程中可能会非常令人失望。作为领导者站出来，坚持度过难关。因为记住，此时此刻，在某些空间和房间里，有一群竞争对手正在密谋对付你。确保他们的突破时刻不要比你们的早。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: When you have an agentic factory, I'm not sure a human-centered workflow works. It doesn't. So you've got pretty much rethink it. And unless you rethink it, please spend a lot of time in the design side of things. If you don't spend time in the design side of things, you won't get a lot of benefits. So don't jump in with these tools and say, oh, I'm going to apply it. Pixie Dust AI leads to what I call AI whitewashing. Okay. It's A multi-decade opportunity. I think you all know this. The one part I would say is progress will not be linear. Please don't be disappointed by lack of progress in a particular area. It's just the nature of AI. Takes 5, 6 tries to get it right. And suddenly, ohh my god, magic moments happen. And it can be very disappointing along the way. Show up as leaders and persevere through it. Because remember, there's a bunch of competitors in spaces and rooms who are plotting against you at this moment. And make sure their breakaway moment is not earlier than yours.

</details>

**Srinivasan, Sri**: 我认为当你们重新构想你们的业务时，我会说思考一下你们的价值主张，重新审视你们的产品路线图。显然，思考一下定价模型等等。并思考一下这些机会。不要只想着技术债务和你们当前的模型之类的东西。想想所有将要到来的差异化优势，因为你们拥有数据，你们了解分销，而且你们有能力……从根本上自动化你们所服务的组织和业务部门中的每一项认知劳动甚至更多。请加倍巩固你们的护城河。分销，你们的客户信任。只有满意的客户才会向你们购买。只有满意的客户。监管，你们正处于最佳位置，伙计，就像令人难以置信的护城河。而数据只有在可用且真正专有的情况下才是护城河。如果别人几年内都无法重建它，那它就是专有的。如果他们能在几周内重建它，呃，那就不是专有的。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: I think as you reimagine your business, I would say think about your value proposition, revisit your product roadmap. Obviously, think about pricing models and such. And think about the opportunities. Don't just think tech debt and your current models and things like that. Think of all the differentiation that's going to come because you have the data, you have the understanding of distribution, and you have the ability to kind of... Innately automate every piece of cognitive labor and more in the organizations and business departments you serve. And please double down on your mods. Distribution, your customer trust. Only happy customers will buy from you. Only happy customers. Regulatory, you guys are in the sweet spot, man, like unbelievable mode. And data is only a mode if it's usable and if it's truly proprietary. It is proprietary if somebody can't rebuild it in years. If they can recreate it in like weeks, uh-uh, ain't proprietary.

</details>

**Srinivasan, Sri**: 所以，我想我会说……你们想成为拥抱并推动变革的领导者。我认为更精简、更强大、更敏捷的组织是当务之急，任何程度的雄心壮志，从长远来看，你们都会发现它是不够的。所以我将停在这张幻灯片上，问问题，回答你们有的任何问题，你知道，要记住的三件事是。10 万亿以上的服务型软件市场将是注意力和焦点所在。我们生活在一个不可思议的时代。我们每个人都应该为能参与这个旅程而感到兴奋，接下来的十年是 AI 转型的十年。相信我，我们正处于那个 AI 转型十年的起点。让我们确保在重新构想我们的业务、在原本不可能做到的获胜类别中进行重建时留下印记。**PCC** 就是一个非常典型的例子。你们创造了这个类别，并把它从几乎一无所有发展壮大。你们拥有什么样的市场份额，这令人难以置信。但如果你们不重新构想，别人就会这么做。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: So, I think I'd say... You want to be a leader who embraces and drives change. I think leaner, meaner, nimble organizations are the need of the hour, and any amount of raising ambition. you're going to find that it's insufficient in the long haul. So I'm going to basically stop at this slide and ask question, answer any questions you guys have in that, you know, three things to keep in mind are. The 10 trillion plus services software market is where the attention and focus is going to be. We live in amazing times. Each of us should be excited to be in this journey where the next decade is an AI transformation decade. Believe me, we're at the start of that AI transformation decade. And let's make sure we leave an imprint in reimagining our businesses, in recreating in winning categories that could have otherwise not been done. PCC is such a prime example of that. You guys created this category and grew it from nearly nothing. And it's unbelievable what kind of a market share you have. But somebody else is going to reimagine if you don't.

</details>

**Srinivasan, Sri**: 输赢取决于你们。这不仅是你们去赢的机会，也是你们去扩张和阐述的机会。记住，如果你们具备了服务型软件的思维，围绕你们软件的所有服务收入都将是你们的。最重要的是，我想说，现在是具备战时心态的时候了。现在不是放松下来说，哦，我们是一家价值十亿美元的企业，你知道，没人能碰我们的时候。这是业务，这是考虑 50 亿美元的时候，不管长期计划（LRP）意味着什么，它就是。往大了想，往宽了想，要有雄心壮志，因为技术允许你们做以前被认为不可能的事情。现在就是做这件事的时候。你们不需要依赖，你知道的，像你们领域里的一些环境转录。你们可以自己构建。这完全没问题。我不是说你们要自己构建所有的乐高积木。我只是说软件开发的成本，启动一个新功能或创建一个新模块的成本，急剧下降了。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: It's yours to lose. It's yours to not only win, but expand and expound. Remember, all the services dollar around your software will be yours if you become services software thinking. And most important, I would say, this is time for wartime mindset. This is not a time to basically relax and say, oh. We're a billion dollar business, you know, nobody can touch us. This is the business, this is the time to think $5 billion, whatever the LRP means, it is. Think big, think large, be ambitious, because the technology allows you to do things that were otherwise thought impossible. And now's the time to do it. You don't need to depend on, you know, some ambient transcription like in your space. You could build it yourself. And that's perfectly fine. I'm not saying build all the Lego blocks yourself. All I'm saying is the cost of software development, the cost of initiating a new feature or creating a new module. went down precipitously.

</details>

**Srinivasan, Sri**: 你们现在可以利用它了。我不是在提倡削减成本。我基本上是在说最大化你们所拥有的潜力并扩大生产力。最大的衡量标准是每位员工的收入。像 Cursor 这样的公司，他们衡量的人均收入大约是 600 万、700 万。现在有些公司衡量的数字超过了 1000 万。这就是事情发展的方向。PCC 拥有一个令人难以置信的机会。以数十年的专有数据为后盾。能够接触到最好的护理机构和门诊护理机构，几乎是所有的。这些研究人员、医生和临床医生，你们要成长所需要的就是迅速利用它。我将停下来回答问题。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And you can now take advantage of it. I'm not espousing cost cuts. I'm basically saying maximize the potential of what you have and expand productivity. The biggest measure is revenue per employee. And companies like Cursor are measuring it at about 6 million, 7 million per headcount. There are companies that are now measuring it in north of 10 million. That's where things are headed. PCC has an unbelievable opportunity. Backed by. decades of proprietary data. access to the best nursing facilities and the ambulatory care facilities, nearly all of them. These researchers, physicians, and clinicians, the thing that you need to grow is taking advantage of it with speed. I'm going to pause and take questions.

</details>

### 问答环节：合规、敏捷开发与安全性

**David Pessis**: 一旦你得到，大家，让我们使用举手队列，我会的。Maeve，请讲。

<details>
<summary>Original English</summary>

**David Pessis**: Once you get while we everybody, let's just use the hand queue and I'll. Maeve, go ahead.

</details>

**Maeve Ruggieri**: 抱歉，我的静音键在跟我作对。非常感谢，Sri。这非常有帮助。我想知道你是否能给我们分享一下你的观点和见解，关于在尽可能快地行动（你称之为战时心态）与在一个高度受监管的行业中，监管与世界现状不匹配之间的冲突。对吧？HIPAA 是一套非常古老的规则。但我们有责任遵守它们以保护，你知道的，患者信息，最敏感的信息。那么你如何在这种围绕 HIPAA 合规、第 2 部分合规的张力中找到平衡，而且没有，我想说，你知道的，联邦层面或通常是州层面的法规或护栏，你如何平衡这一点与，你知道的，建立速度的需求？

<details>
<summary>Original English</summary>

**Maeve Ruggieri**: Sorry, my mute is fighting with me. Thanks so much, Sri. This is really helpful. I'm wondering if you could give us a little bit of your point of view and insight on the tension between moving, you know, as fast as possible. You called it kind of wartime mindset. as well as kind of the conflict between in a very highly regulated industry with regulation that does not match kind of the state of the world, right? HIPAA is a very old set of rules. but we are duty bound to follow them to protect, you know, patient information, the most sensitive information. So how do you kind of meet in the middle of that tension around HIPAA compliance, part 2 compliance, but and not having, I would say, you know, federal level or oftentimes state level regulations or in guardrails, how do you match, how do you balance that with, you know, the need to build velocity?

</details>

**Srinivasan, Sri**: 是的。是的，Maeve，谢谢你问了一个非常棒的问题。你是一名产品经理还是一名工程师？

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah. Yeah, Maeve, thank you for asking a fantastic question. Are you a product manager or an engineer?

</details>

**Mehrshad Setayesh**: 是的。

<details>
<summary>Original English</summary>

**Mehrshad Setayesh**: Yeah.

</details>

**Maeve Ruggieri**: 产品经理。

<details>
<summary>Original English</summary>

**Maeve Ruggieri**: Product Manager.

</details>

**Srinivasan, Sri**: 产品经理，好的。我认为……这本身就是一个庞大的话题。我绝不赞成在监管上放松警惕。我不赞成。我认为记录良好的受监管市场在 AI 方面具有巨大优势。因为没有怀疑的余地。你基本上必须在编写智能体代码时将所有这些牢记在心。所以这正在法律领域发生，正在医疗保健领域发生，医疗保健的主要部分。我实际上参加了摩根大通医疗保健大会。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Product manager, okay. I think the... It's a vast topic unto itself. I do not espouse lowering your guard down on regulation any bit. I do not. I think well-documented regulated markets are a massive advantage with AI. because there is no room for doubt. You basically have to code your agents with all of that in mind. So it's happening in legal, it's happening in healthcare, major portions of healthcare. I actually spent time at the GP Morgan Healthcare Conference.

</details>

**Maeve Ruggieri**: 嗯。

<details>
<summary>Original English</summary>

**Maeve Ruggieri**: Mm.

</details>

**Srinivasan, Sri**: 这里正在进行的工作量令人难以置信。他们相信这会成功的唯一原因是，它有良好的记录，受到监管，而且你知道确定性是什么样子的。所以我认为这是一个优势，Maeve，而不是劣势。但请不要认为，一旦你想到因为我们有监管所以我们不能做，你就是，这是一个问题。问题是我们如何带着它去做？我们如何构建正确的……

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: And the amount of work happening here is unbelievable. And the only reason they believe this will be successful is because it's well documented, it's regulated, and you know what determinism looks like. So I think that's an advantage, Maeve, not a disadvantage. But please don't think of the moment you think of that as a as a we cannot do because because we have regulation, you are it's a it's a problem. It's how can we do with it? How do we build the right?

</details>

**Maeve Ruggieri**: 嗯。

<details>
<summary>Original English</summary>

**Maeve Ruggieri**: Mmh.

</details>

**Srinivasan, Sri**: 这是他们在乐队里发生的事情。这就是你实际上想要在某个时间点训练或创建的模型。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: It's what happened while they were in the band. That is the model you actually want to train or create at some point in time.

</details>

**Mehrshad Setayesh**: 明白了。谢谢。

<details>
<summary>Original English</summary>

**Mehrshad Setayesh**: Got it. Thank you.

</details>

**Srinivasan, Sri**: Todd。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Todd.

</details>

**David Pessis**: Todd。好吧，让我们有请 Yogesh。

<details>
<summary>Original English</summary>

**David Pessis**: Todd. Alright, let's go to yogurt.

</details>

**Yogesh Rao**: 嘿，快速问个问题，Shaik。关于你如何思考软件开发和将软件产品推向市场的估算和完成时间，我们用于估算的很多点数和其他机制仍然非常扎根于敏捷开发。你认为在未来我们如何衡量或如何看待估算方面会有什么演变？

<details>
<summary>Original English</summary>

**Yogesh Rao**: Hey, quick question, Shaik. In terms of how you think about estimation and time to completing software development and bringing a software product to market, a lot of our pointing and other mechanisms that we use for estimations are still very grounded and agile. What do you see like evolving in terms of like how we measure or how we look at estimations?

</details>

**David Pessis**: 不管怎样。

<details>
<summary>Original English</summary>

**David Pessis**: Whatever.

</details>

**Srinivasan, Sri**: Yogesh，谢谢你的提问。首先我要说的是……David，这是他最后一次邀请我来这里了。所以我想说，如果你现在在一个智能体世界里使用敏捷开发来进行估算，你犯了一个巨大的错误，大错特错。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yogesh, thank you for asking. The first thing I would say is... David, this is the last time he's going to invite me here. So I would say if you're using Agile for... Estimating now in an agentic world, you're making a huge mistake, big mistake.

</details>

**Yogesh Rao**: 啊哈。是啊。

<details>
<summary>Original English</summary>

**Yogesh Rao**: Aha. Saah.

</details>

**Srinivasan, Sri**: 花尽可能少的时间，基本上让估算变得更科学，并问问自己，如果你实际上可以在几天内把它写出来，为什么你还需要估算。所以当我和 **UKG** 交谈时，他们采取了不同的方法。他们回到了像看板（Kanban）和一些其他方法，他们撕毁了他们的敏捷手册，他们说，不再需要它了。所以我不是说现在就去那么做。请弄清楚你们的方法和机制。但在你做估算的时间里，通常你已经可以把它写出来并准备好了。而且这不仅仅是编码，显然你还必须进行测试和其他设计元素以及所有那些东西。采用不同的视角和方法来处理这个问题，即基于使用智能体作为一种估算方法。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: spend as little time, basically make the estimation more scientific, and ask yourself why do you even need an estimate if you can actually code it in a couple of days. So when I talked to UKG, they've taken a different approach. They've gone back to like Kanban and a couple of other methods and they've ripped apart their Agile book and they said, don't need it anymore. So I'm not saying go do that now. Please figure out your method and mechanism. But in the time you do estimation, often you can actually code it up and be ready. And it's not just coding, obviously you have to do testing and other design elements and all that stuff. Take a different lens and approach to this that is ensanced on using the agent as an estimation method.

</details>

**David Pessis**: 所以，所以这个，所以我们说的是，如果它可以在一周内完成，你就不需要估算，所以一切都应该在一周内完成。是的。是的。

<details>
<summary>Original English</summary>

**David Pessis**: So, so this, so what we're saying is if it can be done in a week, you don't need to estimate, so everything should be done in a week. Yeah. Yeah.

</details>

**Yogesh Rao**: 哦。

<details>
<summary>Original English</summary>

**Yogesh Rao**: Ohh.

</details>

**Carol Lewis**: 是的。

<details>
<summary>Original English</summary>

**Carol Lewis**: Yeah.

</details>

**Srinivasan, Sri**: David 可没付钱让我说这个。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: David did not pay me for this.

</details>

**Yogesh Rao**: 伙计。

<details>
<summary>Original English</summary>

**Yogesh Rao**: Budd.

</details>

**David Pessis**: 是的。

<details>
<summary>Original English</summary>

**David Pessis**: Yeah.

</details>

**Yogesh Rao**: Sri，你说 David 可能不会再邀请你了。就像我们，你知道，像什么？不，是我，就像我希望我能问那个问题，不。

<details>
<summary>Original English</summary>

**Yogesh Rao**: Sri, you said David might not invite you again. It's like we, you know, like what? No, it's me, like I wish I could and ask that question, no.

</details>

**David Pessis**: 这个。

<details>
<summary>Original English</summary>

**David Pessis**: The.

</details>

**Srinivasan, Sri**: 好的。好的，Bernardo。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Okay. Okay, Bernardo.

</details>

**Bernardo Sanchez**: 我很喜欢你的演讲。谢谢你。我真的有两个问题。一个是安全问题，另一个更偏向于人事或人员配备。我先从安全问题开始。从安全角度来看，在你看来，使用 AI 用自己的代码重新生成许多第三方库会更好吗？显然不是那些极其复杂的，而是很多较小的库，这样我们就不容易受到 CVE（常见漏洞和暴露）的影响。稍等，是的。

<details>
<summary>Original English</summary>

**Bernardo Sanchez**: I loved your presentation. Thank you for it. I really got two questions. One's security and the other one is more of a personnel or staffing. I'll start with the security. From a security perspective, in your opinion, would it be better to regenerate many third-party libraries with their own code using AI? obviously not the ultra complex ones, but a lot of the smaller libraries so that we're not prone to CVEs. In a second, yeah.

</details>

**Srinivasan, Sri**: 是的，这是一个非常棒的问题，Bernardo。这是一个……随着代码生成量的增加，我不确定说“让我们只生成那些”是一个可扩展的答案，因为……依赖矩阵正在进一步扩大，因为大多数生成的代码实际上都在使用某种库。所以我认为你必须对此保持谨慎。我不认为它是可扩展的，但你必须花更多的时间。所以当我们说裁判智能体时，我会说。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah, it's such a fantastic question, Bernardo. It's a... With the amount of code that's being generated, I'm not sure it's a scalable answer to say let's just generate those because. The dependency matrices are expanding even more because most of the generated code is actually using some library or the other. So I think you've got to be careful about it. I don't think it's scalable, but you have to spend a lot more time. So when we say judge agents, I would say.

</details>

**Bernardo Sanchez**: 关心。

<details>
<summary>Original English</summary>

**Bernardo Sanchez**: Care.

</details>

**Srinivasan, Sri**: 编码的行为急剧减少，审查时间大幅增加。安全审查将会是海量的，除非你为此配备人员并进行培训。否则你就是一个随时可能发生的走动的、会说话的漏洞。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: The act of coding goes down precipitously, the review time goes up immensely. And security reviews are going to be massive, and unless you staff for it and train for it. You're just a walking, talking breach waiting to happen.

</details>

**Bernardo Sanchez**: 是的，这有道理。第二个问题是，我们是否应该雇佣更多的医生、护士以及我们想要扩展的领域的专家？为了获得。太棒了，谢谢。

<details>
<summary>Original English</summary>

**Bernardo Sanchez**: Yeah, that makes sense. Second question is, should we be hiring more physicians and nurses and experts in the fields that we want to expand into? To get. Great, thank you.

</details>

**Srinivasan, Sri**: 关心。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Care.

</details>

**Carol Lewis**: 哦，你好。所以我想接着 Marshad 的问题，也许进一步探讨一下当我们谈论监管以及我们如何处理监管和训练你自己的模型时的情况。关于这一点，我们在司法管辖区方面有一个非常复杂的监管体系。我们有多个国家，它在那里细分，然后进一步细分为州或省等群体，这赋予了它比平时更多的复杂性。那么问题就变成了，如果你正在训练或微调一个基础模型，最初用来训练它的训练语料库，你能解决这些问题吗？

<details>
<summary>Original English</summary>

**Carol Lewis**: Oh, hi. So I wanted to piggyback on Marshad's question and maybe double click a moment when were talking about regulatory and how we handle regulation and training your own model. With that, we have a very complex regulatory system when it comes to jurisdiction. We have multiple countries and that It segments there, and then it further segments into cohorts of state or province, et cetera, which gives it a bit more complexity than normal. And then the question becomes, if you're training or fine tuning a base model, the training corpus that was used to train that in the 1st place, can you address those?

</details>

**Srinivasan, Sri**: 啊哈。所以我认为你问的监管和地理方面的问题。这很像建立云，Carol。这些影响将会存在。但这些影响被放大了得多，因为这也涉及到你使用什么数据进行训练，数据的供应链重要得多，所以我的建议是设计。预先为监管环境设计。以及地缘政治环境。并使之成为其中非常重要的一部分。如果你为每个功能都这么想，那你就有大麻烦了。我的一条指导意见是为智能体化（agency）而设计。也就是说，你的架构必须考虑到智能体化。这基本上意味着智能体管理、数据、模型以及类似的东西。所以我试图给你一个最简短的答案，因为这本身就是一个长达数小时的对话。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Aha. So I think the regulatory and the geo stuff that you're asking about. It's much like standing up clouds, Carol. Those implications are going to be there. But those implications are far more amplified because it's also what data you use for training, where the supply chain of data matters a lot more, so my suggestion would be design. up front for the regulatory landscape. and the geopolitical landscape. and make it very much part and parcel of it. If you think for every feature, then you have a bigger problem. One of the pieces of guidance I have is designed for agency. That is your architecture has to be thought of for agency. And that basically means like agentic management and data and models and things of that sort. So I'm trying to give you the most abbreviated answer because it's like a multi-hour conversation by itself.

</details>

**Carol Lewis**: 是的，我意识到了，而且我们没有几个小时，所以谢谢。

<details>
<summary>Original English</summary>

**Carol Lewis**: Yeah, I realize that and we don't have multi-hour, so thank you.

</details>

**Srinivasan, Sri**: 是的。Brinthan，你的最后一个问题，然后我们就挂断。显然，除了和我交谈，你们都还有工作要做。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah. Brinthan, your last question and then we'll hang up. Obviously you all have work to do beyond talking to me.

</details>

**Brinthan Yoganathan**: 对。是的，谢谢。所以，随着模型变得越来越强大，但也非常昂贵，在你的领域里，有没有其他投资组合公司能够使用那些具备推理能力和强大功能的模型，并说服客户接受其成本与价值的比例？

<details>
<summary>Original English</summary>

**Brinthan Yoganathan**: Right. Yeah, thanks. So, as models are becoming more much more capable, but also very expensive, has any other portfolio companies in your area been able to use one of those reasoning and capable models and convince customers of course to value?

</details>

**Srinivasan, Sri**: 什么的价值？

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Of what to value?

</details>

**Brinthan Yoganathan**: 成本与价值，因为昂贵的模型意味着他们必须支付更多。

<details>
<summary>Original English</summary>

**Brinthan Yoganathan**: a cost to value because an expensive model that means they had to pay a lot more.

</details>

**Srinivasan, Sri**: 是的，绝对的，毫无疑问。我认为成本方面，代币经济学（tokenomics）是一门新兴的艺术形式。优秀的做法正在实施。我会向你推荐 Game Men for Coders（可能是 Gemini for Coders 的口误）作为几天前出现的一个例子，去看看它。基本上，人们已经能够通过削减不必要的修饰并只专注于工作，将云代币使用量减少约 60%。所以这是一个很大的方面。我认为成本，就像任何其他软件项目一样。你需要管理。所以默认情况下，我们都会使用 Opus 模型。但对于我们 95% 的工作，我们只需要一个 Haiku 或一个简单的开源路由模型。所以我们只需要在我们的智能体架构中有正确的组合来管理它。这必须从第一天起就考虑到。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: Yeah, absolutely, without a doubt. I think cost is where tokenomics is something that's an emerging art form. The better ones are doing it. I'd point you to Game Men for Coders is an example that came out. like couple of days back, take a look at it. It's basically, people have been able to reduce cloud token usage by like 60% by cutting out niceties and focusing on just the work. So it's a big facet. I think cost, like any other software project. you need to manage. So by default, we'll all use the opus models. But for 95% of the work we do, we only need a haiku or a simple open source router model. So we just need to kind of have the right mix in our agentic architecture to kind of manage that. And that has to be thought of from day one.

</details>

**Brinthan Yoganathan**: 谢谢。

<details>
<summary>Original English</summary>

**Brinthan Yoganathan**: Thank you.

</details>

**David Pessis**: Sri，非常感谢你。真的非常感激，大家。感谢所有的参与和提问。如果你们有还没来得及回答的难题，发邮件给我，我们可以，你知道，如果 Sri 有时间的话，我们可以把它们转交给 Sri 来解答。但是非常感谢你，Sri。这太棒了。

<details>
<summary>Original English</summary>

**David Pessis**: Sri, thank you so much. Really appreciate it, everybody. Thanks for all the engagement and questions. And if you guys have hard questions that you weren't able to answer, email them to me and we can, you know, we can flip them over to Sri if he has time to address them. But thank you so much, Sri. That was phenomenal.

</details>

**Srinivasan, Sri**: 不客气。谢谢。我指望你们去赢。谢谢。

<details>
<summary>Original English</summary>

**Srinivasan, Sri**: You're welcome. Thank you. I'm counting on you guys to win. Thank you.

</details>

**Mehrshad Setayesh**: 谢谢，Tri。谢谢，再见。

<details>
<summary>Original English</summary>

**Mehrshad Setayesh**: Thanks, Tri. Thank you, bye bye.

</details>
