---
author: AI Engineer
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1KOdiGgMtpY
speaker: AI Engineer
tags:
  - signal-layer
  - ai-differentiation
  - product-strategy
  - trust-building
  - software-engineering
title: 信号层：当万物皆可构建时，我们该构建什么？
summary: 在AI让软件构建成本趋近于零的时代，平均化的产出已失去价值。Akamai技术专家Lena Hall提出，当工程实现被商品化后，核心竞争力转向了“信号层”：即精准定义真正值得解决的问题，并在产品研发、组织协作与市场传播全链路中抵御失真，最终建立起AI无法自动化的用户信任。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Akamai
products_models:
  - Twitch
media_books: []
status: evergreen
---
### 丰饶悖论：当构建成本归零，平庸即无价值

在过去的一年中，开发者和工程师们经历了前所未有的生产力大爆发。借助 AI 与自主智能体，我们在日常生活的各种碎片场景下都能轻松化解复杂的生产事故、并行运行数十个开发代理。我们拥有前所未有的产出速度与**杠杆率**（Leverage: 借助工具放大单人产出能力的比率），然而行业内却普遍弥漫着一种“脚下土地移动过快”的焦虑感。许多工程师甚至产生强烈的机会成本恐慌，陷入全天候的 **Token 极度消耗**（Token Maxing: 竭尽全力调用大模型上下文与算力）状态。

然而，赋予你极速交付能力的丰饶技术，同样赋予了你的竞争对手相同的速度。当任何人都能在短时间内复制并构建任何功能时，平庸与平均水准的构建成本迅速归零，其商业价值也随之归零。过去一年人们常说“熟练使用 AI 是一项超级能力”，但随着底层模型日益强大易用，当所有人都在以相同的提示词向 AI 提出相似的需求（如“告诉我用户想要什么”、“如何赚更多钱”、“让这个功能爆火”）时，**大语言模型**（Large Language Model: 基于海量历史数据训练的收敛机器）只会基于已有公域数据，极其自信且标准地给出完全同质化的平均答案。AI 是本质上的“收敛机器”，若完全依赖它做决策，所有产品都将趋于同质化。AI 唯一无法且不应代你做出的决策，正是**方向抉择**（Pointing: 决定将算力与工程杠杆指向何处）。

<details>
<summary>Original English Source</summary>

How is the conference for all of you so far? Great. Awesome. Um well, I think this was the best most productive year for so many of us. I'm Lena. A few days ago, I solved a production incident on a trail near a waterfall. My friend ran 18 agents while riding his bike. We're literally drowning in abundance. We have more output, more speed, more leverage than any of us have ever had.

So, why do we have this feeling like the ground underneath is moving too fast? One of the engineers that I met at this conference said yesterday that it feels like the opportunity cost for not working 9:00 a.m. to 9:00 p.m. 6 days a week is too high right now. So, we're all token maxing. We're all working all the time. But the same abundance that made you fast, it also made everyone else fast. So, now everyone can build everything. Your competitor can build your feature this afternoon, too. So, the cost of the average just went to zero and so did its value.

A year ago, the superpower, as we were told, was to be good at using AI. But models got so good and they got so easy and everybody now is a lot more skilled at using AI and everybody's pointing AI at the same goals. Cuz AI gives everyone the same answer because everybody is asking the same question. It on data and data is a record of what has already happened. So, when you point AI at tasks like, "Tell me what users want. Make more money. What should we build? Make this viral." It answers from the common knowledge. Very competent, very confident, but also very identical to what it tells your competitor.

To see something that data doesn't show yet, we need to have a vision, a point of view, a read on where it's going, and then use all that automation to execute it. AI is a really smart convergence machine. So, if you leave it alone, it makes everything the same. There is one decision, though, that AI can't and shouldn't make for you. It is to decide what to point at. So, the job, the new job for everyone of us is deciding what it makes, being the reason the right people choose your version over the identical-looking rest.

</details>

### 重新定义工程价值：可度量与不可度量的分水岭

在各大行业展会与技术展厅中，各类工具与产品层出不穷，但令人困惑的是，几乎所有的产品宣讲听起来都千篇一律。在任何人都能构建任何软件的当下，决定产品生死的是**信号层**（Signal Layer: 清晰定义独特价值并无损传递给目标受众的系统层级）。这个信号层包含两大核心支柱：第一是**定义信号**（Knowing your signal），在产品设计、代码实现与演进路线上明确为何该产品独一无二而非平庸均值；第二是**无损发射信号**（Emitting that signal without distortion），确保市场与用户所感知的价值与团队所构建的初衷高度一致。

在构建端，我们需要理清软件工程演进的底层逻辑。两年前，自主代码智能体在标准基准测试中仅能完成微小比例的任务，而如今基准通过率已逼近 90%；然而，实际代码的编写与交付速率并未发生同等数量级的飞跃。正如投资人 **Sarah Guo** 所总结的规律：“凡是可度量的事物，皆可针对其进行模型训练”。编译器和自动化测试套件本质上是免费的评分器（Grader），一旦某项工程任务具备明确的自评机制，模型就能针对该评分标准不断迭代直至攻克。代码编写之所以最先被自动化，正是因为它是软件生命周期中最具可检验性的环节。然而，**最容易被构建出的东西与最具商业价值的东西，几乎从来都不是同一回事**。所有可视、可被规则度量的实现细节都能被瞬间复制，工程实现的自动化红利向全行业普惠的同时，决定“向何处进攻”的战略指向能力成为了真正不可替代的工程核心。

<details>
<summary>Original English Source</summary>

But also, I'm sure many of you uh walked around the Expo Hall at this conference, and there are so many amazing products, so many tools and vendors. They're all solving important problems. But what Why do they all sound the same? So, when anyone can build anything, what makes me different? What makes you different? Why should anyone pick your version, your product? Um I call this work uh signal layer. And there are two There's two halves to solving it, to getting this right. So, that's how we will walk through it.

The first half is knowing your signal, being able to define it very clearly. What you're building and why it's yours and not the average. So, that's the build side, the code, the product, the road map. And the second half is emitting that signal without distortion. So, making sure that your customers um making sure what your customers come to believe about you actually matches what you believe and what you've built. That's the ship side the content and go to market engineering.

And I've had an unusual vantage point in this. I've built products as an engineer. I created my own as a founder. I brought other people's products to market. So three very different jobs with one identical challenge. The signal doesn't always survive. So let's start with the build side. So what do we even work on? Everything is implementable. Two years ago the best autonomous coding agents you know solved on the fraction of the tasks on the standard software benchmark and now the best agents are in the high eighties. So we nearly tripled the amount of writing and shipping barely moved a third. The benchmark was measuring the part of software engineering that has a grader and shipping is where all the ungraded parts come back in.

So here is the rule underneath it. Anything that you can measure you can train against as Sarah Guo puts it. A compiler is a free grader. A test suite is a free grader. And the instant a task can grade itself you can grind a model against you know that grade until it wins. Automation of code was first because it's the most checkable thing that we have. So implementation is converging for free for everyone at the same time and the most buildable thing and the most valuable thing are almost never the same thing. So the model will build whatever you point it at but it will tell you nothing about where to point. Anything visible is replicatable.

</details>

### 汉明难题与非均质品味：在未发生之域寻找真正的问题

面对“一切皆可实现”的技术现实，工程师无需恐慌，因为决定将工具指向何方历来是最高价值的工作。硅谷创业孵化器导师 **Paul Graham** 曾强调，寻找真实需求最有效的方法是亲身体验痛点并为自己与身边的朋友构建解决方案。在市场尚未形成前，传统问卷调查无法捕捉前瞻信号，唯有个体真实的切肤之痛才是未被污染的原始信号。许多最终颠覆行业的产品——比如最初只是将摄像头绑在头上全天候直播自己日常生活的 **Twitch**——在起步时往往显得怪异甚至尴尬，而这正是追求通用收敛的大模型绝不会主动生成的特定构想。

然而，仅仅拥有特定奇特的想法是必要但不充分的。通常人们认为依托“品味与判断力”（Taste and Judgment）即可形成壁垒，但宽泛的品味本质上只是“在反馈机制下的偏好表达”，这恰恰是大模型通过海量范例模仿能够轻易掌握的能力。真正能够抵御模型训练与收敛的品味，存在于两类独特维度：
1. **针对未发生事件的判断力**：由于未来尚未发生，公域中不存在对应的训练数据；
2. **植根于不可观测真实人际关系的洞察力**：模型或许读过关于你客户的所有公开文字，但它从未真正与他们面对面交流，无法感知具体场景下的真实温湿度与历史信任。

数学家与计算机科学家 **Richard Hamming**（理查德·汉明）在研究杰出科学家成功轨迹时指出，卓越的研究者始终聚焦于“重要问题”。所谓重要问题，并非听起来宏大，而是**你拥有切实可行的进攻切入点**（Reasonable Attack）。汉明建议在脑海中常驻 10 到 20 个重要问题，静待新工具或新视角的出现。在汉明的时代，最稀缺的是进攻武器；而今天，AI 赋予了所有人进攻一切技术难题的算力杠杆，此时最稀缺的反而是**洞察哪一个问题真正值得进攻的判断力**。这种判断力来自深耕真实领域的实战伤疤与非理性的极致热爱，其核心价值蕴藏在“AI 已训练的公域知识”与“现实世界应有形态”之间的差值（Delta）之中。

<details>
<summary>Original English Source</summary>

So now, some people when they hear everything is implementable, they panic. Um but we can flip the question. The pointing is actually the job. It has always been the job. We just had so much implementation work in the way um that we never had to get good at it. So, how do you decide where to point that?

Paul Graham shared some wisdom on this. Where you find something that people genuinely want is by feeling the need yourself. Build something you and your friends need because the market hasn't formed yet, surveys can't see it, and your own need is the only signal that isn't a crap signal. And the best ideas may sound genuinely lame at first, like a guy uh strapped with a with a camera on his head live streaming his his life. That sounds really ridiculous, but it became Twitch. Um and the convergence machine doesn't really, you know, propose proactively these uh weird, specific, genuinely embarrassing ideas. But even with the Twitch example, it worked, but there were a thousand other similar startups I start startup ideas that didn't. So, the weird specific signal is necessary, but it is not sufficient.

It's also really tempting to say that we just need to have good judgment and good taste and call it safe. But taste is really just preference under feedback, and preference under feedback is exactly what these systems can learn. Anything you can demonstrate enough times uh with a better or worse signal attached, the machine can eventually imitate. So, broad good taste is not really a differentiator. What actually resists training is more narrow and more durable. So, two things. Taste and judgement about what hasn't happened yet. Because there's no data for an event that hasn't occurred. And then taste and judgement embedded in a relationship that the model can't observe. What this customer in this situation with this history that you share actually needs. The model has read everything ever written about your customer, but it has never actually met them.

So, if broad judgement is not safe, and the AI just handed everyone the ability to build anything, what's left to be good at? Richard Hamming uh spent his career studying why some scientists did great work and others who were just as smart didn't. He found that the great ones worked on important problems. And the problem isn't important because it just sounds impressive. It's important when you have a reasonable attack on it. For example, time travel is consequential, he would say, but it's not important because nobody has an attack on it. So, Hamming would tell you to keep 10 or 20 ideas um on important problems in the back of your mind so that when you finally have an attack, a new tool, a new angle I think that only you noticed, then you go for it. But in Hamming's world, the rarest thing was having an attack. And AI just handed everyone an attack on everything. So, the rarest thing is knowing which problem is actually worth attacking. And that judgement comes from being a real person, close to a real domain, with your own battle scars, your weirdly specific experience, the thing that you care about more than is reasonable. And you don't actually need to be first. You just need to be genuinely close to a problem you actually understand where your insight is in the delta between what AI has been trained on and what should exist.

</details>

### 信号衰减与三重失真：构建端到传播端的工程化防御

即使团队找到了极具价值的问题并打造了出色的非均质产品，若无法将核心信号从创始团队大脑精准传递至目标用户心智中，依然会面临失败。在内容传播领域，AI 同样扮演着收敛加速器的角色。过去两年互联网充斥着极其标准、遵循算法流量套路但毫无实质内容的模板化推文与博客，用户的注意力防御机制已能在半秒内识别并跳过由一句简单 Prompt 生成的 AI 垃圾内容。如果你用平庸的指令换取平庸的文本并推向市场，本质上是在高效率地“自动化你自身的无关紧要性”（Automating your own irrelevance）。正确的协作方式是：由人类提供独特的视角与亲历的真实故事，再由 AI 执行排版、草拟、算法优化等收敛性支持工作。

在实践中，核心信号在向外传递的过程中极易在三个关键节点发生断裂与失真，必须通过针对性的工程化手段加以修复：
1. **源头失真（Source Distortion）**：初创团队创始人对技术与信号过于熟悉，常将信息压缩至外界无法理解的程度。例如在向客户推介时过度沉溺于架构细节与炫酷设计，却删去了最核心的“用户痛点”。某 YC 孵化企业在将开场白重构为“直击用户痛恨的问题及产品如何根除它”后，当周即成功将商务沟通转化为付费试点；
2. **组织失真（Organization Distortion）**：在大企业内部，信号经过管理层、法务、销售等层层流转与交付，在每个环节都会因“执行合规而非出于信念”被拉回至平庸水准。多层委托链结合 AI 收敛工具，极易演变为洗白公司独特信号的自动化工厂。解决之道并非增加官僚审批流程，而是建立轻量级信号校验层，让业务终端重新绑定创始人般的责任感与初衷；
3. **机器失真（Machine Distortion）**：在 AI 自动将技术文档或发布声明重构成推文、宣传册或演示文稿的过程中，往往会为了追求数字的冲击力（如宣称“评估准确率达 94%”）而抹去原有的边界限制与适用前提，将局部测试结果扭曲为绝对承诺。

<details>
<summary>Original English Source</summary>

So, let's say you did it. You found that sweet spot problem that the one that you had an honest attack on, that you built this thing. It's genuinely good. It's genuinely yours, not the average. You can still lose uh because knowing your signal is only half the job. The other half is getting it from your head into the head of a person that it was meant for. And it's about reaching the right people. And what do most of us do for that? We make content. So, let's talk about what uh AI convergence machine does to that.

What happened to the internet in the last 2 years? Open any feed, everything has started to sound the same. The same LinkedIn posts, the same, you know, three bullet points and a bold takeaway, and the same blog post that uh says nothing but actually looks very polished. Um your readers can now pattern match AI in just half a second. So, if a model could have written your post from a one-line prompt, your reader brain just skips it for the same reason. So, AI has really learned the algorithm. It has learned the format that performs. It has learned what gets clicks, and everyone wants to hand the machine a paragraph and say, you know, "Make it viral. Make me rich." It fills every gap that you leave with sameness. So, what do you put in and what do you let it fill in? Cuz these there there are two different ways to use this thing, and they look very identical from the outside. One is you give it an average prompt, and gives you the average output. And you ship one more indistinguishable drop into an ocean of indistinguishable drops. So, you've automated your own irrelevance very efficiently. And two, you can bring in the part that it can't have, your specific point of view, the real story that you were actually in the room for, and then let the machine do the converging work, the formatting, the drafting, the algorithm optimization, the cleanup around the core that it could have never generated.

The signal distorts on the way out. So, you can have the signal perfectly clear for you and still watch it fall apart between your brain and your users' understanding of it. And in my experience, it breaks in three places. And there are fixes for each, but they're different depending on product, the type, and the size of the company.

One of them is source distortion, which is very common in startups. Founders, actually, they usually know the signal so well that they always have this accidental gift of compressing it past legibility. They often assume the context that the audience doesn't have, and the room hears something technically very cool, but they doesn't they don't really understand why it matters. I helped this one YC company with uh this exact thing recently. Absolutely brilliant founders, genuinely new product, but every pitch that they started um was you know starting with architecture, with the clever parts, with things that they were very proud of. But it really landed as noise because the customer pain has been deleted from the whole story. So, we rewrote the opening to include the thing that the user hated, and this product actually killed. So, the same product, the same week, the next conversations converted into pilots, and then we turned that into repeatable GTM system.

Organization distortion is another type of distortion that almost every big company has. As signal travels through layers of management, through legal, through sales, through every department, at every hand handoff, it gets rewound towards the average. And this really doesn't come from incompetence, it comes from investment. So, hand a founder and the person three layers down the same task and the same AI, and you get two different things. Um the founder really sweats the unaverageable details because the outcome is really theirs and they're personally invested and affected by it. And others just ship it to spec, they close Jira tickets, they were asked for, you know, something like compliance, not as much conviction. So, a long delegation chain plus convergence machine is really a factory for automating the signal out of your own company. So, the first instinct usually is to add more process, which adds layers, bureaucracy, and slows everything down. And we don't want that. Um to fix this, we have to help take the signal back and reattach it to the outcome like a founder and add the very thin signal layer to your go-to-market engineering, where its only job is to validate and carry the original intent across the handoffs intact.

Machine distortion is another way you can lose signal. You write one careful launch, your claim, your evidence, and your scope is very clear, but then of course AI remixes it um into a tweet, into a sales deck, into a partner one-pager. For example, you might have had this one very narrow eval that scored 94% but it was repeated enough times that your customers actually heard it as a promise. So, we see the same through line. Your signal has to survive the trip undistorted. And this is something you can engineer.

</details>

### 构筑不可替代的信任资产：工程化信号层的落地法则

为确保信号在传递链条中不发生蜕变，团队必须构建一个轻量级、确定性的信号保障层，确保用户最终接收到的心智认知与设计初衷严密契合。以开发一款新型**系统可观测性平台**（Observability Platform: 监控系统运行状态与故障告警的基础设施）为例：当市场上已有众多同类产品时，该产品的独特信号如果是“在无真实业务影响时保持绝对静默，从而在夜间告警时赢得工程师的百分之百信任”，那么在对外沟通与产品实现上应遵循以下工程化防护原则：
* **单句闭环且内嵌边界**：坚决摒弃“智能 AI 原生可观测性平台”这类空洞修辞，精准表述为“在无法关联到真实用户影响时保持静默，并完整展示所有被静默的告警以供随时人工推翻”——将产品承诺与适用边界焊接在一起；
* **物理锁定约束条件**：使边界无法被 AI 或下级流程删减。在软件交互中，所有被抑制的告警均保持显式可见；在宣发物料中，“减少 90% 的夜间呼叫”必须与“每一次静默均透明可逆”并列呈现；
* **闭环回测实际心智**：在规模化推广前，将产品说明书交付给从未接触过该项目的现场可靠性工程师（SRE），令其复述所理解的产品功能。用户复述与团队意图之间的鸿沟，正是即将被广播出去的失真噪音。

从研发、交付到信号校准，所有努力的终极目标，是为了在海量同质化的替代选项中赢得用户乃至未来智能体（AI Agent）的绝对依赖——即**信任**（Trust）。信任是当今技术生态中唯一无法被自动化评分器、基准测试（Benchmark）或强化学习奖励信号所度量的核心资产，它只能依托长期的真实交互与知情同意缓慢建立。制造平庸不仅毫无收益，反而在 Token 算力、基建运维以及团队工时上产生真实的负向财务消耗，更会因一次平庸的印象而永久失去客户。在工程实现全面商品化的今天，真正的价值已跃迁至“决定什么是值得构建与言说的”顶层判断。唯有建立最坚定的信念，亲自定义独特的信号并严加防御失真，同时激进地利用 AI 自动化其余全部实现细节，才能在丰饶时代构筑坚固的竞争壁垒。

<details>
<summary>Original English Source</summary>

So, we need a thin signal layer, a small deliberate function whose job is to make sure that what your users take away is still the specific thing you meant. Say you're building a monitoring tool. There are 12 other tools in this category, but yours does something different. It tells you what not to wake up for, for example. It stays quiet on the noise, so when you get paged at night, you believe it. So, that quiet, that trust earned by silence is your signal. So, first, say it in one sentence with the limit built in. Definitely don't say intelligent AI-native observability platform. Say something like uh stays quiet on anything it can't tie to a real user impact and shows you everything it silenced so you can overrule it. The promise and the scope are welded together here.

Then make sure that the limit can't be edited out. So, in the product, every suppressed alert is visible. In the launch, statements like 90% fewer pages uh live next to statements like every silence is visible and reversible. So, when AI chops your launch into a tweet, it can keep the impressive number, but also remove the part that keeps the part that uh keeps the product honest. And before you scale it, check what people actually heard. So, give a readme to an SRE who has never seen your project and ask a person to describe the product back to you. The gap between what they say and what you meant is the distortion that you were about to broadcast. And it's a very lightweight signal layer, and a lot of it is buildable, So, you can automate more of the checking and the catching and the surveying than most people realize.

So, step back and ask what all of this, the building, the shipping, the undistorted signal, is actually for. It's for one thing of getting a human or increasingly an agent to choose you and rely on you when they have an infinite identical-looking alternatives. So, that's trust. Trust is the one thing that's left with no grader. There's no benchmark for it, no reward signal. It can't be entirely automated because it's granted slowly through relationship with consent. For example, doctors who open one particular tool every morning, they didn't have that habit trained into them.

And what happens if we get this wrong? Getting your signal wrong is actually not neutral. It's negative. Producing averageness is not free. You actually pay for it in tokens, in infra, in the salaried hours of good people, you know, with with customers that take a look at your product once, decide once, and never come back. So, every generic post teaches them that your name isn't worth the click. So, you spend real money to make yourself harder to choose.

So, back to the main question. We got faster, but the speed is not where the value went. Uh the value moved up to deciding what is worth building, what is worth saying, what deserves trust. And where does the thing that you actually um that that you meant survives the trip to the people that it was for. So, you don't need to be first. You need a real problem and enough conviction to carry the signal clearly through to, you know, right people to find it. So, when you can build anything, you should build trust. Have the strongest conviction, define the signal yourself, protect it from distortion, and use AI aggressively for everything else. Thank you. Let's connect and happy to chat with you afterwards. Thank you.

</details>