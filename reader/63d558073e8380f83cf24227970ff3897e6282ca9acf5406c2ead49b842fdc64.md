---
author: The Knowledge Project Podcast
date: '2026-04-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=6JoUcQ1qmAc
speaker: The Knowledge Project Podcast
tags:
  - agi-alignment
  - scaling-laws
  - iterative-deployment
  - compute-economy
  - p-p-o
title: OpenAI 联合创始人 Greg Brockman 深度专访：从初创风云到算力指数级的未来展望
summary: OpenAI 联合创始人 Greg Brockman 回顾了公司的起源、从非营利转向营利实体的底层逻辑，以及 2023 年 11 月内部动荡的始末。他深入探讨了算力（Compute）作为未来经济基石的重要性，阐述了“迭代部署”的策略，并描绘了一个每个人都能通过 AI 成为“建设者”的未来愿景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Greg Brockman
  - Sam Altman
  - Ilya Sutskever
companies_orgs:
  - OpenAI
  - Stripe
  - DeepMind
  - Microsoft
products_models:
  - GPT-4
  - AlphaGo
  - Dota
  - Cerebras
media_books: []
status: evergreen
---
### 缘起与使命：挑战“不可逾越”的 DeepMind 

Greg Brockman 的创业旅程始于对“本质问题”的探寻。尽管当时他身处硅谷明星初创公司 **Stripe**，但他感到那里的问题即使没有他也会被解决。在与 **Sam Altman** 进行了一次深夜长谈后，两人发现彼此都对 **人工智能**（AI: Artificial Intelligence）有着极高的热情。2015 年，DeepMind 在该领域拥有绝对的统治地位——掌握着顶尖的人才、海量的资本和数据。当时业内普遍认为，想要建立一个新的实验室并与之竞争几乎是“不可能的任务”。

然而，在纳帕谷（Napa）的一次晚宴后，Greg 和 Sam 意识到，虽然困难重重，但并没有任何逻辑证明这是绝对做不到的。于是，OpenAI 的愿景诞生了：构建**人类级别的人工智能**（Human-level AI），确保其造福全人类，并将利益广泛分配。最初的创始团队包括 **Ilya Sutskever**、**Dario Amodei** 等人，虽然早期由于愿景和个人声望的考量，团队曾出现过分歧，但最终通过一次非正式的团建和对**强化学习**（Reinforcement Learning: 通过试错和奖励机制让 AI 学习复杂策略的方法）等技术路线的共识，OpenAI 正式扬帆起航。

<details><summary>Original English Source</summary>

>> I knew I wanted to do a startup because I felt like that was something. But you were just in a startup. Stripe was a startup. It's true. But I never I I felt like Stripe, the problem that we were solving was not my problem, right? It wasn't the problem I had grown up thinking about. It was an important problem that I I dedicated myself to that mission for a number of years, but I felt like it was going to succeed with or without me. And so then I had a first moment to really think about what is a mission that I want to dedicate myself to where I would spend the rest of my life working on this problem just to see it play out in a slightly better way. And it was very clear to me that top of the list was AI, right? If you could actually make a difference in how AI will play out in the world, like that would be a life well-lived.

>> Patrick had said, "Sam has seen lots of young people in your situation." And Patrick, I think really hoped that Sam would convince me to stay. A few minutes of talking to Sam, he's like, "Okay, you clearly have already decided. It is very obvious." And so he asked, "Well, what are you planning on doing next?" And I said, "Well, I'm thinking about doing an AI company." And he said, "I'm also thinking about doing something in AI. We should keep in touch."

>> And so the thing that I remember was a topic was, is it too late to start a lab with many of the best researchers? Is it possible? And this is what year? 2015, right? Because you think about just the degree to which Deep Mind had all the researchers, all the capital, all the data. It just felt like is it even possible to get something off the ground still? People came up with all sorts of reasons. It was hard. No one could come up with the reason it was actually impossible. And so Sam and I driving back to the city that night, I remember we looked at each other and we said, "We got to do this, right? Like we just have to." And so next day I was full-time on putting this together. 

>> Initially, the set of people that I narrowed down to were actually Ilia, Dario, Amadai, Chrissa, and myself. That was going to be the team. It didn't quite come together. I asked Sam, "Okay, how do we break symmetry here? How do we actually get everyone to say, 'All right, we're joining.'" And Sam's suggestion was, "Invite people out for an off-site." So we set up a thing in Napa. And I actually made t-shirts. We came up with what I would really say is almost the technical plan that we have pursued for the past 10 years. Number one, solve reinforcement learning. Number two, solve unsupervised learning. And number three was gradually learn more complicated in quotes things. 

</details>

### 从非营利转折到 AGI 的算力觉醒

随着研发的深入，Greg 团队在 2017 年迎来了一个关键的认知转折点。在研究如何实现 **通用人工智能**（AGI: Artificial General Intelligence）的过程中，他们通过严密的数学计算发现，通往 AGI 的道路必须依赖极其庞大的**算力**（Compute: 执行 AI 模型训练所需的计算资源）。当时，他们接触到了 **Cerebras** 这样的硬件公司，意识到如果能够获得海量的、独占的计算资源，构建 AGI 的成功率将大大提升。

然而，传统的非营利组织募资模式存在天然的天花板（通常能募资数亿，但很难达到数十亿美金的规模）。Greg、Sam、Ilya 和 Elon Musk 达成共识：为了实现使命，OpenAI 必须创建一个关联的营利实体，以吸引足够的资本进入。在这一时期，**Dota** 项目的成功极大地振奋了团队士气。通过将 **近端策略优化算法**（PPO: Proximal Policy Optimization）在海量算力上进行扩展，AI 击败了人类顶级选手。这证明了一个深刻的真理：**“大规模算力 + 简单算法”** 在实践中不仅可行，而且极具爆发力。这种“人类直觉”的涌现，让他们开始思考，如果将算力规模扩大到人类大脑的水平，AI 会发生怎样的蜕变。

<details><summary>Original English Source</summary>

>> At what point did you realize that like this nonprofit thing just wasn't going to work? In 2017, we started to think very hard about first of all, how do we really achieve the mission? How do we actually build an AGI? What will that look like? And we started to do the math on compute. and you start to realize that it's going to take big computer and we came across a company called Cerebras which was building a unique piece of computing hardware. you start to realize if we could buy a lot of those computers we could actually probably succeed at building an AGI if we could get exclusive access to librris that could give us an overwhelming advantage if we could buy very large data centers that could be something unique as well. And the thing about nonprofit fundraising is I think that there is essentially a cap to what is possible there. And so Elon, Sam, Ilia, and I all agreed that the only path forward for OpenAI, the only path to achieve the mission was to create a for-profit entity associated with OpenAI of some form.

>> Dota, we had our first big result, right? That really was like, "Wow, we can actually accomplish something when we put our mind to it. You can actually see all this compute coming together. You scale up the compute, you scale up the result." The ironic thing is we'd actually set out with Dota to develop new methods because the reinforcement learning at the time was clearly not going to scale, right? The the algorithm we use called PO (PPO), you plan over every single time step. There's no hierarchy, right? And we just kept scaling PO and we exceeded the performance of the best humans. And that itself was the finding right that actually massive compute with simple algorithms, it works in practice. We can really make it happen and in this incredibly messy environment.

</details>

### 预测即智能：语言模型的语义涌现

关于“预测”与“推理”的区别，Greg 提出了一个极具洞察力的观点：两者在底层逻辑上是深度统一的。尽管“预测下一个词”听起来像是一项平庸的任务，但如果你能精准预测爱因斯坦下一句会说什么，那么你至少和爱因斯坦一样聪明。预测的本质并不是简单的复述已知，而是在从未见过的新情境中推断可能的发展。

2017 年，OpenAI 发表了关于**无监督情绪神经元**（Unsupervised Sentiment Neuron）的研究，这是他们第一次看到语义（Semantics）从单纯的语言建模目标中自发涌现。通过训练模型预测下一个字符，神经网络竟然学会了分辨情绪的正负面，理解了句子的深层含义。Greg 指出，OpenAI 的技术架构始终遵循两个步骤：首先是**无监督学习**（Unsupervised Learning），通过预测静态数据让模型获得背景知识；其次是**强化学习**（Reinforcement Learning），让 AI 在自己的数据和反馈中积累经验。这种范式的极致体现便是 **GPT-4**。当你面对一个可以流利讨论任何话题的模型时，很难再用简单的“概率预测”去定义它。

<details><summary>Original English Source</summary>

>> Is there a difference between reasoning and predicting? You mentioned sort of like predicting the next character, predicting the next word versus actually reasoning in first principles. I think they are connected in a deep way. So on the one hand, just predicting what comes next sounds like a pedestrian task, but if you really can predict the next word out of Einstein's mouth, you are at least as smart as Einstein. I think that those arguments fall flat because the point of prediction is not about being able to predict what is known. The point is you put yourself in a new situation you've never seen before and predict what comes next. 

>> I remember actually an early moment was the unsupervised sentiment neuron paper. 2017 and it's really the first time that we saw semantics arise from training on a language modeling objective. So you train on learn the next character, predict the next character, and then suddenly you get a neural net that understands sentiment. it can really learn the meaning of sentences. When you see something like GPD4, someone asked, "Why is this thing not an AGI?" Right? It's like actually really hard to put your finger on it because you can talk to it fluently in anything you want.

>> There's two steps to it. The first is unsupervised learning. You train a model just by having it predict what comes next. Then you do reinforcement learning, which is you basically have the AI learn on its own data, right? Fundamentally the technology we use to train during unsupervised stage and during the reinforcing stage they're exactly the same. You are just predicting but you've changed the structure of the data.

</details>

### 动荡与韧性：2023 年内部危机的始末

在谈到 OpenAI 内部的高层冲突时，Greg 坦言，当你坚信自己正在创造具有人类智力水平的机器时，所有的决定都会带上“生存重量”（Existential Weight）。这种高压环境下，普通的办公室政治往往会演变成价值观的剧烈碰撞。2023 年 11 月，Greg 在家中接到了视频邀请，屏幕对面是除了 Sam Altman 之外的所有董事会成员。他被告知 Sam 被解雇，而他自己也被移出了董事会。

Greg 在挂断电话后，第一时间与妻子沟通并决定辞职。令他意外的是，原本以为只是个人的选择，却引发了团队的大规模追随。包括 **Jakob Pachocki**、**Szymon Sidor** 等核心成员在内的员工纷纷表示愿意跟随他去开创新的事业。在那个周末，尽管竞争对手疯狂挖角，但 OpenAI 没有流失任何一个人。Greg 将这种忠诚归结为一种“战壕里的领导力”——当大家不再是为了钱，而是为了身边并肩作战的人而战时，团队就变成了牢不可破的“钻石”。最终，在 Ilya Sutskever 签署回归请愿书的那一刻，Greg 感受到了巨大的慰藉。这段经历让他深刻体会到，作为领导者，在不确定性中保持决策的果断和内心的定力（Sense of Self）至关重要。

<details><summary>Original English Source</summary>

>> Take me back to the moment you found out that Sam had been fired. I got a text saying, "Can we hop on a video call?" I noticed that it was the board minus Sam who were on there. I was told that the board has decided that Sam would be removed. Also that I had been removed from the board, but would be staying with the company. It just wasn't right. Right after I hung up the call, I talked to my wife and I said, "Got to quit." And she said, "I agree." 

>> That day when I quit, started to get all these messages, people saying, "I don't know what you and Sam are doing next, but I'm with you." I didn't really expect to get that kind of support. We all got together and we started to chart out what a new company could look like. That Sunday night the board replaced me as interim CEO with a new person and the company just rebelled. Everyone streaming out of the building and it was just like real chaos. Then this petition starts to circulate, so many people were trying to sign the petition at once it actually crashed Google Docs. 

>> I woke up and I saw that Ilia had posted and had signed a petition, and it said that he wanted the company to come back together. And that was this real moment of relief. Throughout that weekend all the competitors were circling. People are getting offers and we actually did not lose a single person through that weekend. No one accepted a competing offer. They're not playing for money, they're playing for the person beside them. 

</details>

### 算力即权力：未来经济的计算底座

Greg 认为，我们正步入一个由算力驱动的世界。OpenAI 之所以能在早期大胆投注上百亿美金建设数据中心，是因为他们比竞争对手更早地直面了现实：**计算是实现使命的唯一路径**。在未来，算力中心（Data Centers）将进化为人类建造过的最大、最精密、也最“脆弱”的机器。它们不仅仅是用来回答简单问题或生成图像，更会被专门分配去解决人类的根本痛点，例如**攻克癌症**。

社会面临的最核心问题将是：**“算力该分配给谁？”** Greg 强调，OpenAI 坚持提供免费层级的 ChatGPT，就是为了确保算力这一核心资源能被广泛触达，而不是锁在象牙塔里。随着经济向“计算经济”转型，企业和消费者之间的界限将模糊化。通过 **Codex** 等工具，任何有创意的人都可以成为开发者。Greg 预言，未来 80 亿人都将需要自己的 **个人 AGI 代理**（Agentic System: 具备自主行动能力的 AI 系统），这个代理不仅了解你的个人语境、可以代你处理事务，更会与你的长期目标保持一致（Alignment），真正将人类置于驾驶位。

<details><summary>Original English Source</summary>

>> You guys had the boldness to make that bet with a hundred billion dollars for data centers. That is the core of open AI is really encountering reality as it is. These are maybe the biggest machines that humanity creates and then you ask the question of why. It is because they have the potential to solve problems that matter for people, to solve, you know, come up with cures for cancer. But if we're computer constraint, how do you decide who to serve? This is going to be the most important question for society to answer. Where does the compute go? What problems are worthy? 

>> The aspect of consumer that we're really dialed in on is solving goals. All of those people should have a personal AI, a personal AGI that's out there that knows them well, that has their personal context that is trustworthy. That level of having an AI that knows you and can help you achieve whatever it is you want to achieve and help you flesh out what are your goals. You should still set those goals. You should be in charge. ultimately they're the same technology. 

</details>

### 安全、韧性与迭代部署的哲学

为了确保 AI 的安全性，Greg 提出了**迭代部署**（Iterative Deployment）的支柱性策略。与其在实验室里秘密构建一个强大到可能失控的系统，不如让系统以递增的能力接触现实。通过 **GPT-3** 的部署，他们发现 AI 最大的滥用竟然是医疗广告垃圾邮件，这种意料之外的反馈让他们能及时调整安全防护。他认为，安全不是实验室的闭门造车，而是社会整体**韧性**（Resilience）的构建。就像汽车需要安全带、城市需要电力标准一样，AI 也需要融入社会的防御层。

面对全球 AI 竞赛，Greg 指出，美国必须保持领先，以确保民主价值观在技术演进中得到保护。尽管外界担心工作被取代，但 Greg 认为技术本质上是人类机构（Agency）的延伸。虽然传统的职业路径可能不再稳固，但“建设者”的门槛被空前降低。他建议年轻人积极拥抱 AI 工具，从“使用者”转变为“代理管理者的 CEO”。未来的成功不再是让人类去适应机器（如长时间伏案打字导致的身体损伤），而是让机器主动承接人类的工作，让每个人都能拥有一个“口袋里的顶级专家团队”。

<details><summary>Original English Source</summary>

>> What is iterative deployment and why do you do? One is you go for kind of build it in secret, but then at some point you push a button and you say deploy. And you've never deployed anything ever before. right? That's your first contact with reality and it's a very powerful system. But instead, what about if you take an approach where this is your hundredth system? And the world has also had a chance to adapt to them, to reconfigure around them. It was medical spam. Like advertising different drugs to people. not something we ever would have thought of as a problem, but we see it in front of our eyes and we get a chance to react and learn from it.

>> It's not just about the safety of the model. It's about the resilience of society. You think about engines, right? You build cars, but you also need seat belts. The same will be true for AI. Leading an AI is very critical for America because I think that this is how you can ensure that democratic values are protected and preserved. 

>> My view of AI is it is about empowerment. It is about human agency. Instead of you doing work with your computers. Your computer actually does work for you. Everyone is going to be heading to a world where we're managers of agents and soon maybe the CEO of an autonomous AI corporation, right? Just imagine if you had the workforce of, you know, 100,000 person company all at your disposal. 

</details>