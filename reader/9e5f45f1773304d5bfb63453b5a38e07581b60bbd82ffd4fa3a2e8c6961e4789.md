---
author: All-In Podcast
date: '2026-10-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yzk44lz-RGI
speaker: All-In Podcast
tags:
  - quantum-computing
  - post-quantum-cryptography
  - cybersecurity
  - open-source-ai
  - vertical-integration
title: 量子威胁逼近、开源与前沿模型之争、AI网络攻防战与SaaS软件大整合：IBM与Palo Alto Networks掌门人深度对话
summary: IBM董事长兼CEO Arvind Krishna与Palo Alto Networks董事长兼CEO Nikesh Arora展开深度对话，探讨量子计算对现有密码体系的现实威胁与时间表、前沿闭源模型与开源权重模型的经济学账本、AI时代网络攻防的不对称博弈与军备竞赛，以及企业级垂直整合与SaaS行业即将迎来颠覆性整合的底层逻辑。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - IBM
  - Palo Alto Networks
  - OpenAI
  - DARPA
products_models: []
media_books: []
status: evergreen
---
### 量子计算的发展里程碑与对现代加密体系的破译威胁

**[主持人]**: 我知道你们两位过去一两天在对话中经常提到“T”开头的那个词——Token（代币/标记）。但也许我们可以稍微把话题从 AI 挪开一点。我想这在某种程度上其实还是根植于 AI 的，但过去几天有一场关于密码学以及密码学面临的一些风险的大讨论。我认为这在 OpenAI 发布数学成果后开始发酵，但现在关于这项大型量子倡议以及它可能如何把我们带入一个必须开始考虑采用抗量子密码学时代的讨论越来越多了。不过，Arvind，也许我们先从你谈起，聊聊在你看来现状究竟如何。

<details>
<summary>Original English</summary>

I know that you guys have been using the T-word a lot the last day or two in your conversations, the tokens. But maybe we could kind of pivot a little bit away from AI. I guess it's a little bit rooted in AI, but there's been this big conversation set in the last couple days about cryptography and some of the risks to cryptography. I think it it took root after the OpenAI math drop, but there's more conversations now about this big quantum initiative and how that might kind of take us into an era where we need to kind of start to think about adopting quantum cryptography, but Arvin, maybe we could start and talk a little bit about where things stand today from your view.

</details>

**>>**: 当然。稍微补充一下 David 刚才提到的，DARPA 一直在举办一项名为 QBI（量子基准测试计划，Quantum Benchmarking Initiative）的竞赛。几年前有几百家公司加入了这项竞赛。我想现在大概只剩下 13 家了，所以这能告诉你什么是可能真实的。我称之为可能还不完全真实，其中一部分是真实的。他们的目标是：谁能制造出真正能工作的量子计算机？我们先抛开纯技术细节不谈。目前的争论是：这个时间点究竟是 2028 年、2029 年，还是 2033 年？如果你取中间点，就叫它 2030 年吧，它将会破译今天的密码学体系。这绝非推测，而是板上钉钉的现实。如果这件事注定会发生，那么你必须使用什么密码学来保护自己免受其害呢？对你们中的某些人来说不幸的是，更糟糕的情况在于：如果你今天有一个被盗的加密硬盘，别人完全可以把它保存 5 年，到时候直接破解它。好消息是，后量子密码学（Post-quantum cryptography）已经被理解透彻了，人尽皆知，代码也写出来了，但大家之前都太懒了，一直拖着没去推进。但我认为，现在的这一刻就是当头棒喝的警醒时刻。

<details>
<summary>Original English</summary>

>> Sure. So, um a little bit of what David just touched on is uh DARPA's been running a competition called QBI or Quantum Benchmarking Initiative. Um a couple of hundred companies joined it a couple of years ago. I think it's down to maybe 13 are left, so that tells you kind of what's maybe real. I'm calling it maybe not quite real. Some of it is real. And so their goal is who can build a quantum computer that works? Let's sort of put the technology side out of it. And the debates are is it 2028, 2029, 2033? And sort of if you pick the middle point, let's call it 2030, well, it will break today's cryptography. That's not a supposition, that's just a reality. And if that's going to happen, then what's the cryptography that you got to use to uh protect yourself against that? Unfortunately for some of you, what's even worse, if you have an encrypted hard disk today that gets stolen, somebody could keep it for 5 years and break it at that point. The good news is post-quantum cryptography is understood, it's well-known, the code is written, but people have been too lazy to get to it. But I think the wake-up moment is now.

</details>

**>>**: 我们目前理解的解决方案是防量子的（quantum-proof），还是抗量子的（quantum-resistant）？因为这在某种程度上是基于我们今天对量子未来可能模样的基础理解。

<details>
<summary>Original English</summary>

>> Are the solutions that we understand quantum-proof or quantum-resistant? Because it's sort of based on our basic understanding today of what quantum probably looks like.

</details>

**>>**: 确实，不，它是建立在理论层面理解量子能做什么的基础之上的。所以，它们之所以是防量子的，其严密程度等同于今天的传统计算机无法破解今天的密码学。这其实并不是一个严格定理证明层面的答案，它更多是建立在计算机科学的计算复杂性理论之上，而这归根结底是建立在一些假设之上的，而不是建立在——

<details>
<summary>Original English</summary>

>> Yeah. Um, no. It is based on understanding at a theoretical level of what quantum could do. So, they are quantum proof in the same level of rigor that today's cryptography cannot be broken by today's classical computers. That's actually not a theorem proof level answer. It's more based on complexity theory in computer science, which is grounded at the end on some assumptions, not on

</details>

**>>**: 那么，看看我们今天的现状，以及 2030 年这个中间节点，你能给我们梳理一下你需要看到的演进节点吗？也就是我们大家必须开始引起重视并说“好吧，我们该如何行动”的时刻？

<details>
<summary>Original English</summary>

>> So, if you look at where we are today, and that 2030 midpoint, can you just walk us through the evolutionary moments that you need to see, where we all have to start paying attention and say, "Okay, how do we move?"

</details>

**>>**: 好的。今天我们手里的都是玩具级的量子计算机。我称之为“玩具”，是因为它们虽然能解决某些特定问题，但却充满了错误。它们目前根本没有任何实现完全扩展的途径。所以，第一个问题将是：谁能第一个在运行中的真实量子计算机上展示出一定水平的纠错（error correction）或减错（mitigation）能力，而不是在模拟器上，也不是在场外推演？这是第一步。因此，我的预测是，到明年你就会看到有人提出这样的宣称。然后，你应该让第三方去评估这些宣称是否属实。你会发现到 2027 年，会有一两家取得进展。是纠错进展，虽然还不是大规模的，但确实是纠错。

<details>
<summary>Original English</summary>

>> Yes. So, today you got toy quantum computers. I'll call I'll call them toys because they can do certain problems, but they're rife with errors. They have no way to scale fully yet. So, question one will be, who's the first one who can demonstrate, not a simulation, not on the side, but some level of error correction or mitigation on a running quantum computer. Step one. And so, I'll predict you'll see somebody make claims by next year. Then, you should get third parties to evaluate are those claims real. You'll find one or two will make progress by 2027. Error correction. Not at scale, but error correction.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 第二个问题将是：你能否在某种规模上运行这些设备？还不是完全的规模。由于找不到更好的词，我暂且称之为门计算量（gate computations）。如今，大多数人能达到的水平大概都在 1 万次左右。如果对比普通计算机，这根本算不了什么。你的 iPhone 每分钟都能做几十亿次运算。

<details>
<summary>Original English</summary>

>> Question two will be, can you run these things at some level of scale? Not yet complete scale. I call it gate computations for the lack of a better word. Today, most people are somewhere around 10,000. Which if you think of a normal computer is not very much. When your iPhone does a couple of billion uh, per minute.

</details>

**>>**: 确实。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 那么对于门计算量，是否有人正在从 1 万次往上扩缩？他们是否每年能增加一个数量级（添一个零）？这是我设定的第二个里程碑。把这两个步骤结合起来，如果每年增加一个零，那就意味着到 2029 年你可能会达到 1000 万次。那将是非常了不起的成就，那已经可以完成一些让所有人都大吃一惊的事情了。

<details>
<summary>Original English</summary>

>> So, gate computations, is somebody scaling from 10,000? Are they adding a zero each year? That's the second milestone I would put. You put those two steps together and now if you put a zero per year, that means you could be at 10 million by 2029. That's remarkable. That can do some things that will surprise the hell out of everybody.

</details>

**>>**: 这是不是指所谓的“逻辑量子比特”（logical qubit）概念，即某种经过纠错的可运行量子比特？这是——

<details>
<summary>Original English</summary>

>> Does this reference kind of this notion of a logical qubit being kind of an error corrected operating qubit? Is that

</details>

**>>**: 这是一个——这是否是一个——

<details>
<summary>Original English</summary>

>> It's a Is Is that a Is that a a term

</details>

**>>**: 你们都采用了的术语？每个人是否都有相同的里程碑和相同的度量标准？

<details>
<summary>Original English</summary>

>> you've adopted qubits and that everyone kind of has the same milestone, the same metric?

</details>

**>>**: 我其实不太喜欢这个术语，但我认为用它来向人们做解释还是合理的。比如告诉别人：“嘿，如果我说我正在造一台拥有 1 万个量子比特的计算机”，别人会说：“对，但它们全都是带噪声的。”别人说得没错。因此，一旦我开始进行纠错，在某种意义上它会降低这台机器的有效容量。所以，逻辑量子比特表达的意思是：“好吧，这台机器的有效容量是多少？”我认为这是一个合理的看待方式。所以，虽然我不太喜欢这个术语，因为这并不是说我把这四个东西拿过来，像 DRAM 存储单元那样放着就算完事了。实际上整台机器都是经过纠错的，但它内部存在某种比例关系。比如 10,000 个物理量子比特，可能对应大约 200 个逻辑量子比特。

<details>
<summary>Original English</summary>

>> I don't love the term, but I think it's a fair term to just explain to people to say, "Hey, if I say I'm building a computer that's got 10,000 qubits and they say, "Yeah, but they're all noisy." You're right. So, if I begin to error correct, it in some sense decreases the effective capacity of the machine. So, a logical then says, "Okay, what's the effective capacity of this machine?" is I think a reasonable way to look at it. So, that's uh that's a term that I while I don't love because it's not like I've taken these four things and it's like a DRAM cell and that's it. It's actually the whole machine is error corrected, but it's got some divide. So, 10,000 physical, maybe 200 logical.

</details>

### 企业IT基础设施升级防量子风险的紧迫性

**>>**: Nikesh，你们拥有专门思考前沿威胁并探索技术极限的红队（Red Teams）。假设你开始看到这些数量级（OOMs, orders of magnitude）不断复合增长，如果你来推测，你的红队会指出哪些是最显眼的蜜罐目标？如果你是一个恶意攻击者，你会把矛头指向哪里？

<details>
<summary>Original English</summary>

>> Nikesh, you have red teams that think about what is at the frontier and pushing it. Let's say that you start to see these ooms, these orders of magnitude start to compound. If you had to guess, where would your red team say are the obvious honey pots? Where do you point that if you were a bad actor?

</details>

**>>**: 如果你从这个角度去想：在座的各位几乎在整个 IT 基础设施中都运行着加密密钥。这绝不是单一的事情。所有东西都依赖于处于加密状态的密钥在运行。我们所在领域的每一个供应商在通信两端都持有密钥。所以，最先会发生的事情是：任何非防量子的东西都将变得可被破译。因此，我们的观点是，你绝不能干等到 2029 年或 2030 年，因为我们不可能到了某一天突然集体跑出去说：“噢，让我们直接烧掉 50 亿美元的 IT 基础设施，然后花 1 年时间重新搭建一套，因为我们现在需要抗量子安全的基础设施了。”所以，你现在就应该开始行动，当下就应该用抗量子或防量子安全的基础设施来替换你的 IT 技术栈。现在市场上已经有一些技术和能力，比如你可以开始通过给传输流量包裹抗量子就绪（post-quantum ready）密钥来作为过渡方案。你可以这样做，但时间窗口方面——如果他说是 2029 到 2030 年，那我们现在就已经落后了。

<details>
<summary>Original English</summary>

>> If you think from the perspective of everybody here has pretty much crypto keys running across the entire IT infrastructure. It's not one thing. Everything is running with crypto keys which are encrypted. Every vendor in our space has keys at each end. So, the first thing that's going to happen is whatever's not quantum proof is going to be breakable. So, our view is you can't wait for 2029 or 2030 because it's not like one day all of us are going to go out and say, "Oh, Let's go burn $5 of IT infrastructure and let's go build it again in 1 year because now we need quantum-safe infrastructure." So, you should be built you should be replacing your IT stack today with quantum-safe or quantum-proof infrastructure right now. Now, there are technologies there are capabilities which are already out in the market where you can start, you know, wrapping uh post-quantum ready through keys around traffic as a stopgap. So, you can do that, but the time to if he says it's 2029-30, we're already late.

</details>

**>>**: 距离现在只有 3 年时间了。

<details>
<summary>Original English</summary>

>> We're 3 years away.

</details>

**>>**: 我们离它只有 3 年时间了，而我敢肯定在座的各位今年都留出了数亿美元的 IT 支出预算，而我估计你们支出的 50% 都花在了非量子安全的基础设施上。

<details>
<summary>Original English</summary>

>> We're 3 years away and I'm pretty sure everybody in this room has got a few hundred million dollars of IT spend that is earmarked for this year and I'm guessing 50% of your spend is on infrastructure that is not quantum-safe.

</details>

### AI与经典计算能否先于量子计算机破解加密？

**>>**: 之前有一位相当资深的 AI 研究员曾表示，我们根本不需要等到——

<details>
<summary>Original English</summary>

>> There was a pretty senior AI researcher that said we don't need to pay

</details>

**>>**: 嗯？

<details>
<summary>Original English</summary>

>> Hm?

</details>

**>>**: 2029 年？

<details>
<summary>Original English</summary>

>> 2029?

</details>

**>>**: 我的意思是，他的观点其实是：今天的 AI 模型在量子计算机实现突破之前，就能先一步带我们达成目标。你对此有何看法？而且我想，你知道，这种想法的根源在于：在数论的前沿领域，你可以看到 AI 开始推导出人类目前尚未参透的模型和数学证明，从而让我们重新思考如何才能高效地破解密码。也许本周 OpenAI 发布的数学成果，正是表明他做出的这一预测可能是准确的早期迹象。

<details>
<summary>Original English</summary>

>> Well, I mean, his view was actually models AI models today can get us there before quantum computers get us there. Do you have a view on this? And I guess, you know, and and I guess it's rooted in this idea that on the frontiers of number theory, you can see AI start to develop models and proofs that are not apparent to humans today that allow us to rethink how we can effectively do code-breaking. And perhaps the OpenAI math dump this week is an early indication that this might actually be a good prediction that he made.

</details>

**>>**: 既然你在往这个方向深挖时展现了技术极客的一面，那请原谅我也要极客一把了。这是不可能的。归根结底，这要追溯到理查德·费曼（Richard Feynman）等人所做出的研究成果。你无法在完全不同的硬件架构上进行模拟，却还期望获得更高效的结果。对吧？所以，如果你以此为论点前提：量子计算机根本不是在做算术运算，对吧，而包括 GPU 在内的所有传统经典计算机做的全都是算术运算。AI 算法有可能发现一种全新的量子算法吗？绝对有可能。但它能在今天的硬件上高效且经济地运行该算法吗？不，这是不可能的。因此，你必须依赖量子硬件来运行这些算法，才能获得该量子算法所具备的积极优势。否则，它的运行速度会慢上整整一个数量级，慢上一千倍甚至一万倍。所以，你能证明这是一种可行的算法吗？可以。但你能从中获得现实算力收益吗？不太可能。

<details>
<summary>Original English</summary>

>> Since you geeked a little bit by going down that direction, you'll excuse me if I just geek a little bit. It's not going to be possible. At the end of the day, this goes back to stuff that people like Richard Feynman did. You cannot simulate something on a different architecture and expect a more efficient result. Right. So, if you take that as a thesis, quantum computers do not operate in arithmetic, right, which is what all of classical computers, including GPUs, do. Could you have an AI algorithm discover a new quantum algorithm? Absolutely. Could it run it effectively and efficiently on today's hardware? Yes, it's not possible. So, you need quantum hardware to run these things to get the positive advantage that the quantum algorithm has. Otherwise, it'll be slower or by an order of a thousand or ten thousand. So, could you prove that it's a workable algorithm? Yes. Could you get that benefit? Unlikely.

</details>

**>>**: 我想对方的论点是说，仅仅利用——我知道我们现在是在技术探讨——但仅仅利用经典计算，你实际上可以找到一条不同的算术路径。例如，如果你能更好地预测质数的分布，比如处于数论前沿那些我们尚未真正攻克的难题，我们就可以开始利用经典计算模型来着手破解密码学。

<details>
<summary>Original English</summary>

>> I think the argument is using, and I know we're geeking for a minute, but just using classical computing, you can actually have a different path, arithmetic path. For example, if you had a better predictor of the distribution of prime numbers, you know, like at the frontiers of number theory that we've not really resolved, we can start to have classical models that can start to break cryptography.

</details>

**>>**: 这确实有可能。问题是这需要耗费多长时间，因为耗时永远是关键所在。是的。所以，我认为这确实是可能的，但如果破解一个密钥要花上 10 年时间，大多数人都可以高枕无忧了。这在工程上并不是一个具备实际操作性的方案。这就是我认为争议的焦点所在，但在真正做出来之前，一切都无法得到证实。

<details>
<summary>Original English</summary>

>> It is possible. The question is how long will it take because that's always the question. Yeah. So, I think it it is going to be possible, but if it takes 10 years to break one key, most people are going to rest in peace. That's not a practical answer. That's the That's I think where the debate is going to lie, but it won't prove out until it's done.

</details>

### 开源权重 vs 前沿闭源模型的经济学账本与企业采用路径

**>>**: 让我把对话转移到目前正在发生的事情上。我很想听听你们两位对以下概念的看法：市场上存在开源，存在闭源；有最前沿的 Frontier 模型，有紧随前沿步伐的模型；现在实际上还有非常合理的替代方案，至少是具备相当实力的开源权重（open weight）模型。你们对这整个光谱的哲学思考是什么？请告诉我们，在未来几年内，我们应该如何看待模型与能力的发展？Nikesh，由你先开始吗？

<details>
<summary>Original English</summary>

>> Let me move the conversation to something that's happening currently. I would love to get both of your takes on the following concept. There's open source, there's closed source, there's frontier, there's pacing the frontier, there's now effectively very reasonable alternatives that are open weight at a minimum. Your philosophy around the entire spectrum, and just give us a sense of how we should think about models and capabilities over the next couple of years. Nikesh, do to start?

</details>

**>>**: 好的。听着，我认为今天早些时候有人说过：“在实验阶段，不要在能力层面去限制你的团队。不要在这个阶段就开始尝试成本优化，不要在那个阶段就尝试自己去生搬硬套拼接模型。”因为我们手下工作的团队，两万甚至两万多人，在过去的 12 到 18 个月里才刚刚接触 AI，而且它并没有在整个组织内部充分渗透普及。因此，如果你给他们的采用制造障碍，如果你让他们的理解变得更困难，我们做好准备所需的时间就会更长。所以现在，我们的态度是：“去用你能找到的最好的模型，用最简单的交互方式去使用它，这样你才能理解并验证这些工具到底能做什么，无论这是从效率的角度、营收的角度，还是产品研发的角度。”这算是所谓的“第一阶段”。

但是在第一阶段，我们发现的情况是：尺有所短，寸有所长，对吧？人们不明白的是——曾经有那么一个时刻，大家都以为网络安全整个行业都要被 AI 模型吞噬了，你知道的，我们的职业生涯就要完蛋了，因为某个神话模型（mythos）能解决所有问题。嗯，你猜怎么着？

我们检查终端上的所有流量，每年的成本仅为 20 美元。对吧？每个终端数百兆的流量，一年的成本只需 20 到 30 美元，因为机器学习直接运行在你的终端本地、利用你自己的算力运行，我们只需在 20、30、40 MB 的有效负载上运行它。

现在，如果你想把所有这些流量提取出来，通过 OpenAI 为公司里的每一个员工按 Token 付费跑一遍——听起来这简直是源源不断的营收轰鸣声。OpenAI 大概光从这一家公司身上，就能赚出他们全年的营收。

<details>
<summary>Original English</summary>

>> Sure. Look, I think earlier in the day somebody said, "Don't restrict your teams in terms of capability in the experimentation phase. Don't start trying to cost optimize. Don't start trying to stitch your own in that phase because the teams who work for us, 20,000 to 20,000 people, have just discovered AI in the last 12 to 18 months, and it's not fully diffused across the organization. So, if you make it harder for them to adopt, if you make it harder for them to understand, it's going to take longer for us to be ready. So, right now, we're saying, "Go use the best model you can find, the easiest way to use it, so you can understand and can be validate the things that these things can do, whether it's from an efficiency perspective, a revenue perspective, or product development perspective." That's kind of I'll call it phase one. But, in phase one, what we've discovered is there's different horses for different courses, right? What people don't understand, you know, there was a moment when everybody thought the cybersecurity was going to get consumed by AI models and, you know, our lives are over because mythos is going to solve every problem. Well, guess what? We inspect all traffic at an endpoint with the cost of $20 a year. Right? Hundreds of megabytes of traffic per endpoint at the cost of $20 to $30 a year because machine learning is running on your endpoint, your compute, and we run it on a 20, 30, 40-MB payload. Now, if you want to take all that traffic, run that through OpenAI using tokens for every employee in your company, sounds like the sound of revenue. Like, OpenAI would probably generate all their revenue in 1 year from one company.

</details>

**>>**: 没错。

<details>
<summary>Original English</summary>

>> Right.

</details>

**>>**: 所以，那根本不是实际使用模型的可行方式。因此你的做法是：拿一个小型语言模型（SLM），进行压缩，让它针对特定任务专门化，持续不断地训练它，直到它的准确率达到 99.9%，然后说：“我们不再使用传统机器学习算法，而是改用生成式 AI 小型语言模型，它们将通过这种方式去执行任务。”所以，核心点在于：

我们正在做的是搞清楚究竟什么任务需要多高水平的智能，以及该特定任务获得该智能的成本是多少；接着你会突然发现，你并不需要在每一个任务上都开一辆法拉利。

而且顺便说一句，客户也不想为每一个任务都去支付一辆法拉利的费用。我再给你举一个反面例子。反面的情况是：假设你正在遭遇安全入侵。

你正遭受攻击，并且你确切知道自己正在被黑客入侵。在那个时刻，场内的每一位客户都会说：“别管成本了，只要能阻止入侵，不管什么模型你随便用。”因为他们清楚，那次入侵带来的业务损失会高达数十亿美元。在那样的时刻，我可以调动智能体蜂群（agent swarms），我可以采取任何你在防御视角下想采用的手段。因此在那种场景下，我可能会想要使用最新、最顶尖的前沿大语言模型并下达指令：“去深入思考，彻底推理清楚，找出如何阻止这次入侵、如何化解危机。”

所以我们发现的是：你最终只会在业务价值受损程度足以证明其合理性的独特场景下去使用前沿 LLM。如果你愿意，你可以拿它去做药物研发。我认为在企业的大多数实际用例中，我们最终都会去训练某种版本的开源模型。而且我认为，即使在和平时期，对我们而言，比如运行一个防御模型，我们绝大概率会采用开源权重模型，利用我们自己的私有专有数据进行训练，掌控这些权重——因为只有这样才能为我们提供可审计性、可解释性，以及一个我们能够真正解释整个事件是如何发生的开放系统。

<details>
<summary>Original English</summary>

>> So, that's not a practical example of how models are used. So, what you do is you take a small language model, you compress it, you make it task specific, you keep keep training it until it gets to 99.9% accuracy and say, "Instead of using it using machine learning algorithms, we're going to use generative AI small language models, and they're going to do that via So, the point is what we're doing is we're trying to figure out what task requires what level of intelligence, and what is the cost of that intelligence for that particular task and you'll suddenly discover you don't need a Ferrari for every task. And by the way, the customers don't want to pay for a Ferrari for every task. I'll give you the flip side. Flip side is let's assume you're undergoing a breach. You're being attacked, you know you're being attacked. At that point in time every customer in the room says, "Don't worry. Use whichever model you need to to stop the breach." Because they know the business impact of that breach is in the billions of dollars. At that point in time I can run agent swarms, I can do all kinds of stuff that you want from a defensive perspective. So there I may want to use the most up-to-date frontier LLM and say, "Go think about it, reason the hell out of it and figure out how to stop this breach, how to make this happen." So what we're discovering is you're going to end up using frontier LLMs in unique cases where the business value that is going to get disrupted justifies it. You can do drug discovery if you want. I think for most practical use cases in enterprises we're going to end up training some version of an open source model and I think when it comes to even in peacetime for us, for example, running a defender model, we're most more than likely going to take an open weight model, use our own proprietary data, train it, manage the weights because that's what gives us the auditability, the explainability, and the the open system where we can actually explain how that happened.

</details>

**>>**: 我完全同意，不过我要从一个略微不同的视角切入，但最终得出的结论是完全一致的。我们来看看经济学账本。

在今天，上一代模型的每百万 Token 费用大约是 20 美元，如果你想用最极致的前沿模型，可能要 50 美元。我们可以选用中国的一个开源权重模型，比如 Kimi k1.5 之类的，拥有几千亿参数；如果你在自己的 GPU 上运行，再加上一点点优化——我说的仅仅是一周左右的工程工作量——你就能把每百万 Token 的成本降到大约 1 到 2 美元。

世界上有哪家企业会拒绝一个成本便宜 10 倍、在当前案例中甚至便宜 40 倍，却能有效完成 95% 工作的解决方案呢？因此，我认为经济性至关重要。

第二个考量因素归根结底将是——你刚才提到了思维链（Chain of Thought），而不仅仅是最终输出的 Token。那么，如果这段思维链可以被其他第三方捕获、记录和审计，你实际上就是在拱手送出自己的核心知识产权（IP）。因此，品牌和 IP 保护将促使人们下定决心：“我必须在自己的可控环境下独立运行模型。”然而，你根本无法独立运行前沿模型，因为没有任何一家闭源前沿厂商会把模型权重直接交给你。因此，你又只能退回到开源权重模型上。

第三个因素则是地缘政治。目前最好的开源权重模型很多来自中国。顺便提一句，如果你把它们放在沙箱里完全由自己本地运行，我认为几乎不存在任何危险。当然，如果你直接通过公有云服务去调用它们，那就是另一码事了。但我认为，在未来一到两年内，西方也极大概率会出现同样优秀的开源权重模型，并且具备与中国模型相当的能力。这些技术之间的代差最多也就 6 到 12 个月而已。

结合以上三点，促使我得出这样的结论：我不敢确切保证具体是 75% 还是 90%，但我划定的区间是：由于我刚才提到的这些原因，再加上 Nikesh 提到的理由，未来所有 Token 使用量的 75% 到 90% 都将流向开源权重模型。

<details>
<summary>Original English</summary>

>> I completely agree, but I'm going to take a slightly different lens to get to the same exact end conclusions. Let's take economics. So today $20 for a million tokens for probably generation minus one, 50 if you want to go to the most extreme. Uh we could take uh one of the Chinese open weight models, take a Kimikay3, something 800 billion parameters, and if you run your own GPUs with a little bit of optimization, but I'm talking like a week of engineering work, you could drop the cost to about a dollar to two dollars for a million tokens. Which enterprise in the world will not accept a 10 times or in this case a 40 times cheaper answer for effectively what can do 95% of the work. So, I think economics is important. The second is going to be at the end of the day um you just talked previously about chain of thought, not just the end tokens. Well, effectively then you're giving away your IP if that chain of thought can be captured and logged and audited by somebody else. So, so brand and IP is going to drive people to say, "I need to run the models on my own." Well, you can't run a frontier model on your own because none of them will give it to you. So, then you're back to open weight. And the third is geopolitics. The best open weight models today are Chinese. By the way, I think there's very little danger if you're putting them in a sandbox and running them by yourself. Sure, if you use them from a cloud, that's different. But I think that over the next year or two, I'm very doubtful that there will not be great models that come up in the west that are also open weight and that are as capable as the Chinese. The gap in these things is 6 to 12 months at the most. And so, all those three drive me to conclude I don't know whether it'll be 75% to 90%, but that's the range I would put of all token usage will go to open weight models for the reasons I mentioned added to the reasons that Nikesh mentioned.

</details>

**>>**: 那么剩下的那部分 Token 消耗量呢？那是因为企业确实不可或缺地需要它，还是因为这只是一种默认的惯性行为，纯粹因为人们太懒了而不愿去做出改变？

<details>
<summary>Original English</summary>

>> And the token consumption that's left over, is that because you actually need it or is that because it's a default behavior and people are too lazy to change?

</details>

**>>**: 好吧，那我来谈谈开发者的行为习惯。因为我曾经也是名开发者，我在这里先自嘲一下年轻时的自己。开发者都是懒惰的。除非你设立管控机制，否则他们一定会倾向于去用那个最贵、最顶级的现成方案。

<details>
<summary>Original English</summary>

>> Okay. So, I'm going to talk about developer behavior and since I was one, I'm making fun of myself in a younger age. Developers are lazy. They're going to use the most expensive the most expensive answer unless you put a control on it.

</details>

**>>**: 没错。

<details>
<summary>Original English</summary>

>> Right.

</details>

**>>**: 因为这样最省事、最容易。

<details>
<summary>Original English</summary>

>> Because it it's easy.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 所以，这种惯性会把用量推向那里。因此我要说的是：如果在实验探索阶段，你允许这样做来证明方案可行，而随后我必须把它迁移到一个更廉价的解决方案上，只要它能让我更快地达成目标，那通常没什么问题。但是在生产环境的规模化使用中，我非常怀疑除了极少数极其特殊的用例外，继续依赖它究竟还有什么价值。

<details>
<summary>Original English</summary>

>> And so, that is going to do take it there. So, I would say if experimentation phase you allow that to prove it works and now I got to put it on a cheaper answer, it's probably fine if it gets me there a lot faster. But doing it for production usage is where I am skeptical that it's of value except for a tiny number of use cases.

</details>

### AI与代码安全：攻击者与防御者的不对称战场

**>>**: Nikesh，你们当初被拉进了那个小圈子，成为早期预览并体验 Mythos 模型的合作伙伴之一。我相信你们现在和 OpenAI 也有类似的合作。当你和这些顶尖实验室的人坐在一起时，你心里会不会隐约觉得他们在盯着你的业务看，心里琢磨着：“哇，这可是一门绝妙的好生意”？我［笑］——你认为他们会这样想吗？他们究竟会怎么看？而且你预期他们会尊重怎样的实际技术边界？我之所以问这个问题，是因为我们之前和其他几位 CEO 聊过。我认为 Marc Benioff 在这方面树立了最好的典范，我们探讨过零数据保留（ZVR, Zero Data Retention），他在代表客户利益坚决落实数据不留存方面表现得极其激进强势。关于 ZVR 以及所有这些协议，非常有意思的一点是：没有任何一个模型厂商在协议里明确承诺他们不会利用数据生成合成数据（Synthetic Data）。协议里字面上压根没写这一条。你们大家都应该去翻翻条款看一看。里面全是退路和免责漏洞，到处都是隐藏后门。所以，我只是很好奇，当你坐在那间会议室里时，你脑子里在想什么？

<details>
<summary>Original English</summary>

>> Nikesh, so were brought in as one of the small circle of people for mythos kind of preview it, be it their partner. I'm sure you're now doing that with OpenAI as well. When you're sitting with these guys, is part of you thinking they're looking at my business and they're like, "Wow, this is a great business." I [laughter] do Do you think that they're Like And and and what is the What is the actual technical boundaries that you expect to be respected? And the reason I ask this is we've talked to a couple of other CEOs. I think Marc Benioff does the best example of this where, you know, we've talked about ZVR and he's been incredibly aggressive about making sure there's zero data retention and doing that on behalf of his customers. What's so interesting about the ZVR and all of this stuff is like none of the models say that they won't generate synthetic data. It's literally not in there. You guys should look. There's all these outs. There's all these trapdoors. So, I'm just wondering like when you're in the room, what are you thinking?

</details>

**>>**: 当你坐在那间会议室里，走出来时你心里会笃定地说：这帮家伙是进不来我的业务领域的。

<details>
<summary>Original English</summary>

>> When you're in the room, you come out and say this These guys are not going to get into my business.

</details>

**>>**: 他们进不来。

<details>
<summary>Original English</summary>

>> They're not going to

</details>

**>>**: 他们绝对没有能力切入我的核心业务。

<details>
<summary>Original English</summary>

>> They're not going to be able to get into my business.

</details>

**>>**: 好，愿闻其详。

<details>
<summary>Original English</summary>

>> Okay.

</details>

**>>**: 因为你想一想当初 Mythos 刚出来时的情形，对吧？我们一直在编程智能体领域投入数十亿美元。你猜怎么着？我们本质上——并不是每个人在写代码时都有 ZVR 保护。外界有成千上万的人在使用云端代码工具（Cloud Code），他们对于这些代码数据被拿去训练模型完全无所谓。所以，我们实际上正在借助终端用户的日常编码来训练这些模型。这些模型在编程方面的能力变得越来越强大。那么你猜接下来会怎样？如果你教会了一个模型什么是优秀的优质代码，它自然也就能识别出什么是劣质、糟糕的代码。所以 Mythos 所做的第一件事，就是弄清楚了糟糕的代码到底长什么样。接着，如果你把它放出去扫描你的代码库，它就会精准指出哪里存在缺陷。而真正引人深思的是，即便在它做到这一点的时候，它仍然有大约 30% 的时间在产生幻觉。

对吧？但问题在于，为什么说这对攻击者而言是完美的利器：因为攻击者只需要找到一个漏洞就够了，他们根本不需要 10 个漏洞。但如果你是一名防御者，你就必须找出每一个漏洞并完成修补。因此，我认为在过去的 12 个月里，在座的所有人都经历了这样一段历程：这里的每个人都跑去测试了它们，无论是用 Mythos、Mythos 的衍生版本，还是他们发现的某种开源恶意软件。

其中的每一个漏洞都必须经过二次测试、理解并彻底搞清楚。我敢断定在这间屋子里，如果大家举手表决，人们会说大概有 60% 到 80% 的漏洞是真实存在的，而另外 20% 则是模型的凭空幻觉。所以从这个角度来看，模型非常擅长告诉你系统中存在哪些漏洞；但我甚至认为，如果你让在座的各位举手，没人敢说他们会直接用 Cloud Code 生成的代码去修补漏洞而不再进行重新测试验证。

<details>
<summary>Original English</summary>

>> Because if you think about what when mythos came out, right? The We We've been paying billions of dollars in coding agents. Well, guess what? We're fundamentally every Not everybody's got ZVR in coding. There's tons of people out there using cloud code who have no issue about that data training the models. So, we are training these models with end users doing coding. These models are getting better and better doing coding. Well, guess what? If you teach a model what model good looks like, it also can figure out what bad code looks like. So, the first thing that mythos did, it figured out what bad code looks like. And then if you let it loose against your code, it'll tell you what is bad. What was fascinating is when it did that, even then it was fine It was hallucinating 30% of the time. Right, but the problem is the reason it's perfect for attackers is they just need one vulnerability. They don't need 10 vulnerabilities. If you're a defender, you need to find every vulnerability and patch it. So, all the people in this room, I think, have been through this journey in the last 12 months is that everybody here has gone, tested them, whether with Methos or with some cousin of Methos or some open source malware they discovered. Every one of them has to be has to then be tested, understood, you know, figured out. And I would guess in this room, if I show of hands, people say that number is roughly 60 to 80% have been been have been real and 20% have been hallucinations. So, from that perspective, the models are great to be able to tell you what the vulnerabilities but I don't even think anybody in this room, if you ask them to raise their hand, will tell you that they're not going to even use Cloud Code to patch the vulnerability without having to test it again.

</details>

### 网络安全即战争：协同防御、不对称性与技术代差

**>>**: 我有一个看似天马行空但引发我深思的问题。你们的职责是保卫各大企业，但现在这看起来基本上就像是一场真正的战争。你们两位面对的局面就像是一场交锋战争。那么，在战争打响或交火的过程中，是否有某些经验教训是可以汲取的？你们是否真的会利用这些军事战争规律来指导底层技术应该如何运行？我不知道这个问题是否说得通，但是——

<details>
<summary>Original English</summary>

>> I have a very random question, but it makes me think. So, you're engaged to defend companies, but it now looks basically like warfare. Like both of you guys, you know, it's like warfare. And so, is there something that you can learn from how war has been fought or how war is being fought? And do you do that to actually inform how the technology should behave? I don't know if this question makes sense, but

</details>

**>>**: 我认为，关键在于只要大家能够团结协作，就能变得更加强大。比如 Arvind 负责推进的一个项目，我们现在倡导：既然大家都在发现漏洞，我们为什么不把各自发现的漏洞集中汇聚起来，统一找出防御对策，而不是让在座的每家公司各自为战，分别跑去排查测试自己所有的开源代码漏洞、自己研究怎么打补丁、再自己单独去修补。因此，你可以借助值得信赖的中立第三方：把你们的漏洞交给我们，由我们统一打好补丁并分发这些补丁，这样所有人就能在同一时间获得安全防护。这非常契合当下网络安全的运行逻辑。如果在世界另一个角落发现了某种新型攻击手段，我们可以捕获该攻击技术，编写机器学习代码，将其整合进我们的产品中，确保每一位客户都能立刻获得免疫能力。

<details>
<summary>Original English</summary>

>> I think to the extent that you can be better together, you can collaborate. Like Arvind runs a program, we're now saying we're all finding vulnerabilities, why don't we pool our vulnerabilities and find the defense ones as opposed to every company in the room trying to go, test all the open source vulnerabilities they have, figure out how to patch them, go patch them individually. So, then you take some trusted parties, give us your vulnerabilities, we'll patch them, we'll distribute the patches so you can all be safe at the same time. It's kind of like how cybersecurity works today. If you find an attack technique in a different part of the world, we can take that attack technique, write machine learning code, ingest that into our product and make sure it gets available to every customer.

</details>

**>>**: 智能体自主生成的代码是零缺陷的吗？

<details>
<summary>Original English</summary>

>> Is a genetically written code error-free?

</details>

**>>**: 不是。

<details>
<summary>Original English</summary>

>> No.

</details>

**>>**: 不是。好，请解释一下背后的原因。

<details>
<summary>Original English</summary>

>> No. Okay, explain that.

</details>

**>>**: 听着，但首先针对你刚才关于战争的提问。

<details>
<summary>Original English</summary>

>> So, look, but first on your war question.

</details>

**>>**: 好的。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: Nikesh 刚才所谈到的是：你可以建立起强大的防御联盟，在这个联盟中，防御同盟的力量实质上可以超越单一攻击者。这是第一种战术手段。战争中的第二种机制，也是历史上最行之有效的手段，是不对称性（asymmetry）。在绝大多数情况下，进攻者的成本远远低于防守者，这导致防守方常常因为耗尽资金而最终不得不妥协认输。那么，你是否能让防御变得同等廉价？如果是这样，你基本上就能拉平为对称战争，从而拥有大得多的胜算。

而第三种机制，也是历史上所有战争得以决胜的终极方式——就是单方取得压倒性的技术代差优势（technological superiority）。回想一下第二次世界大战，回想一下朝鲜战争，回想一下伊拉克战争，回想历史上任何一场战役。只要一方掌握了技术代差优势，往往就能稳操胜券。

因此，我们的终极目标是：我们能否在技术上占据压倒性优势？这也正是 Nikesh 所指的核心。我们能否先一步发现漏洞？能否快速修补它们？能否在系统周围筑起坚不可摧的壁垒，让对手试图寻找突破口的成本变得极其高昂？这就是我对战争类比的回答。

至于你问的：智能体生成的代码最终会优于人类编写的代码吗？绝对会。我们已经看到了这一趋势。目前在我们公司内部，大概有一半的代码都是由智能体和编程 Agent 编写的，而且质量确实优于过去人类所写出的代码。但之所以能更优越，是因为这些智能体在编写的同时还能做自动评估（evals），基本能确保在代码正式发布之前，把它们能够发现的所有缺陷统统修复完毕。

尽管如此，我们目前也仅仅只能发现那些“我们已知如何去排查”的缺陷漏洞而已。于是，我们在计算机科学中就陷入了这样一个奇怪的循环死结：好吧，我是否能——

<details>
<summary>Original English</summary>

>> So, what Nikesh talked about is you can have powerful alliances where the alliance effectively can become more powerful than the attacker. That's technique one. Technique two in warfare what has been the most effective is asymmetry. And so often an attacker is cheaper than the defender, so the defender runs out of money and at some point then concedes. Or can you make defense equally cheap? In which case you can basically have symmetric warfare and then you have a much better chance of success. And the third which has been the way all wars have been won is when you get technological superiority on one side. So go back to World War II, go back to Korea, go back to Iraq, go back to anyone. If you get technological superiority on one side, you tend to win. And so our goal is can we get technological superiority and that's what Nick is referring to. Can we find vulnerabilities, can we patch them, can we put boundaries around them that makes it really expensive for the other side to now try to find a way through? So that's what I would answer there. Look, at the end will agentic code be superior to human written code? Absolutely. We can find that. We use agents and coding agents now for probably half the code that is written inside our place and it is superior to what was being written before. But the reason it's superior is the agents can also do evals and basically make sure that everything they can find is actually fixed before it ever goes out. All that said, we're only finding all the flaws that we know how to find. And so we get into this weird loop in computer science. Okay, do I

</details>

**>>**: 做到完全且规范的形式化验证（fully properly verifiable）？

<details>
<summary>Original English</summary>

>> fully properly verifiable?

</details>

**>>**: 目前还无法做到完全形式化验证，因为这项任务在目前的计算能力下几乎是不可行的。当然，我也不会彻底否定未来它能演化出你在数论探讨中所说的那种可能性。在这一领域，也许未来某一天我们会找到一种新方法来真正验证这些系统的绝对正确性。至少在输入条件受限的场景下是可行的。但如果输入是任意无边界的，那我认为这极其困难。

<details>
<summary>Original English</summary>

>> It's not fully verifiable because that is a task that is going to be almost computationally infeasible right now. Now, I'm not going to hold out hope that it's doesn't become what you were talking about in number theory and all that. This is a task in which maybe we'll find a way to actually get to be able to verify the correctness of these things. At least in where the inputs are limited. If the input can be anything then I think it's really hard.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

>> Right.

</details>

**>>**: 这能讲得通吗？

<details>
<summary>Original English</summary>

>> Does that make sense?

</details>

**>>**: 完全明白。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

### AI军备竞赛的不可逆性与数据中心监管的政治博弈

**>>**: 让我追问一下你刚才所谈论观点的深层意涵。在我看来显而易见的是：世界上绝不可能出现中国与美国、西方世界或其他国际社会各方能够手拉手围坐在一起说“让我们全部停下 AI 研发”的局面。既然如此，这就不可避免地演变成一场军备竞赛：对攻防技术优势的绝对刚需、对算力基础设施规模的绝对刚需，以及为保护产业、保护经济体、保护就业岗位而衍生出的全套需求。

面对政界探讨以及社会舆论中那些试图阻挠 AI 发展、叫嚣“必须叫停 AI、我们必须停止推进”的人群，这种现实逻辑能否在辩论中占据上风？“由于一方拥有该技术已成必然，因而倒逼另一方必须拥有同等防御手段”这一铁律，是否正在扭转舆论风向？我很想听听你们两位分享一些经历：你们与那些如今或许尚未掌权、但未来可能入主政坛的高级政界人士交流时，他们是否因看清了这一点而发生了立场转变？

<details>
<summary>Original English</summary>

>> Let me ask the implications of the points that you just made. It seems obvious to me that there isn't a world where China and the United States or the West or whomever, a bunch of international countries all hold hands and say let's all stop AI development. That being the case, it becomes a necessity that there's an arms race, that there's a defensive or offensive superiority requisite, that there's a compute capacity requisite, that there are all of these needs that arise to protect industry, to protect our economy, to protect our jobs. Does that argument win the day with everyone that's trying to stop AI in the political conversations and the social stuff about AI needs to stop and we need to stop doing this. Does this point about the inevitability of one side having it requiring the other side to defend it change the the the conversation? I'd love for you guys to share any anecdotes you've had with senior party officials who might not be in power today but might be coming into power and whether they're going to kind of have a view change around this because of that point.

</details>

**>>**: 我想极其显而易见的是，没有任何人正在停下脚步。所有人似乎都在以令人抓狂的疯狂节奏全力以赴，试图确保自己能打造出更强大、更聪明、更快速的模型。

这其实很有意思。你可以从宽容的一面来看待：世界上没有任何一项技术在最初被创造出来的时候，人们会同时把安全机制和动力引擎一起造好。我不认为当年人类在制造飞机的时候，就已经存在运输安全管理局（TSA）了。就好像莱特兄弟当年造出飞机时说：“太棒了，我们把飞机造出来了。接下来让我们想想怎么——”

<details>
<summary>Original English</summary>

>> I think it's abundantly clear that nobody's stopping. Everybody seems to be working at a frenetic pace to try and make sure that they get a better, smarter, faster model. Um it's kind of interesting. You can take the charitable side and say there's no technology in the world that was built where people were building security and power. I don't think TSA existed when they built planes. It's just like Wright brothers say, "Great, we have planes. Let's figure out how we're going to

</details>

**>>**: 怎么脱掉鞋子安检。

<details>
<summary>Original English</summary>

>> Take your shoes off.

</details>

**>>**: “让我们在每个人登机前先把他们全身搜个遍。”那绝对不是他们当时脑子里会去想的事情。

<details>
<summary>Original English</summary>

>> Let's frisk everybody before they get on the plane." That was not what they were thinking about.

</details>

**>>**: ［笑声］

<details>
<summary>Original English</summary>

>> [laughter]

</details>

**>>**: 防止炸药——

<details>
<summary>Original English</summary>

>> Keep explosives

</details>

**>>**: 防止有人把炸药藏在鞋子里。

<details>
<summary>Original English</summary>

>> keeping explosives out of the shoes.

</details>

**>>**: 没错，正是这样。这根本不是他们当时会去思考的。但不幸的是，我们早早被展示了这些模型的阴暗面，并且我们在模型的黑暗面上过度反应了，以至于现在的整场讨论全都在围绕 AI 的阴暗面和危害打转，而完全忽略了 AI 的巨大利益。我认为这在舆论叙事上出现了偏差。

尽管如此，我认为没有任何人正在放慢研发脚步。我认为最可能出现的结果——我也希望这是一个正确的结果——就是在这个世界上，正如你说的以及 Arvind 早先强调的：如果你制造了某样东西，你就必须对其全权负责。如果你打造了一样工具并把它释放到社会中，你不能在闯祸后两手一摊说：“哎呀，我不知道该怎么控制它。”这种推脱借口在现实中根本行不通。

<details>
<summary>Original English</summary>

>> Yes, that's right. That's not what they were thinking about. So, unfortunately, we've been shown the dark side of these models and we've over-rotated on the dark side of the model, where now the entire conversation is about the dark side and the perils of AI and not on the benefits of AI. I think there's a narrative problem. That notwithstanding, I don't think anybody's slowing down. I think the most likely outcome, which I think hopefully is the right outcome, is that in the world uh you said it and Arvin said it earlier, if you build something, you're accountable for it. If you build something and unleash it, you can't unleash and say, "Oops, I don't know how to control it." That argument doesn't work.

</details>

**>>**: 没错，因为软件是你写的。

<details>
<summary>Original English</summary>

>> Yeah. Cuz you wrote the software.

</details>

**>>**: 确实。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 是的，还有那种狡辩说“软件不是你写的，是软件自己写了自己”。

<details>
<summary>Original English</summary>

>> Yeah, and this whole argument that you didn't write the software, that the software was wrote itself.

</details>

**>>**: 工程师会推诿说：“哎呀，是我测试框架里的 74565 号智能体写的。”大家只会回应：“行了，那就是你写的。”

<details>
<summary>Original English</summary>

>> because the engineer is going to say, "Well, agent 74565 from my harness wrote it." And it's like, "No, you wrote it."

</details>

**>>**: 但无论如何，也是公司作为主体写出来的，因此企业必须承担产品责任。

<details>
<summary>Original English</summary>

>> Well, but the company still wrote it, so there's product liability with the company.

</details>

**>>**: 你是一家商业企业——

<details>
<summary>Original English</summary>

>> you're a commercial enterprise,

</details>

**>>**: 一点没错。

<details>
<summary>Original English</summary>

>> Exactly.

</details>

**>>**: 你拿出了某种产品来换取经济价值，你就必须承担你白纸黑字承诺的那份责任。所以我认为，在我看来，事情就是这么简单直接。而且这世界上已经有足够多的监管法规——或许甚至有些过度了——完全足以对人们投放进公开市场的产物进行问责，绝不容许他们逃避应负的责任。

<details>
<summary>Original English</summary>

>> you're taking economic value in return for giving me something, you're required to abide by the responsibility the responsibility that you signed up for. So, I think that's In my mind, it's as simple as that. And there's enough regulation in the world, perhaps too much, to hold people accountable for stuff that they put out in the open market, where they don't take responsibility they don't take responsibility.

</details>

**>>**: 但是，David，现实中要想控制住它是根本不可能的，除非我们天真地认为全世界都会手挽手齐唱《Kumbaya》然后一致同意放慢脚步，而正如刚才所言这绝无可能。既然如此，好吧，假设你在这边踩了刹车放慢脚步；那么，这是否意味着日本会放慢？是否意味着中国会放慢？是否意味着印度会放慢？绝无可能。他们只会拍手称快：“太好了，你们慢下来了，这正好给了我迎头赶上甚至实现反超的历史机遇。”因此，数字技术是根本无法被人为踩刹车的。欧洲的先例已经告诉了我们答案——在那里，人们对一切潜在的可能性感到恐慌；对，我指的还不是真实存在的危险，而是对所有潜在臆想的风险都感到极度恐惧，于是率先针对原本如此充满活力的科技生态痛下监管重手，对吧？

<details>
<summary>Original English</summary>

>> Well, but David, it's actually impossible to control it, unless we think the entire world is going to sing Kumbaya and say let's slow down, which Archi said is unlikely. So, if that's the case, fine. You put a slow down here, maybe. Well, okay, does it mean Japan slows down? Does that mean China slows down? Does that mean India slows down? No chance. They'll say, "Great, you're slowing down. Gives me a chance to catch up and get ahead." So, a digital technology is impossible to actually slow down, and the European example tells us So, there you get afraid of all the possibilities. Yeah, I'm not saying the real dangers. You get afraid of all of them and you impose regulations first against such a vibrant tech economy there, right?

</details>

**>>**: 确实。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 不过话说回来，你们两位刚才其实都没正面回答我关于私下交流的提问。因为我跟你们透露一下我上周在华盛顿特区经历的一场对话。我跟一位国会议员喝了几杯，那是位级别相当资深的重要人物，那场对话包含了两个核心层面：

第一点是，他提到全球规模最大的某家公司的 CEO 如今对网络安全感到了彻底的恐慌，整个人几乎要精神崩溃了，完全不知该如何应对，那位议员刚跟他吃过晚饭，转述了他当时说的那堆惊慌失措的话。第二点则是，他认为到今年第四季度，我们可能会见证全美 50 个州联手对数据中心下达禁令。虽然这听起来不太可能发生，但他亲口这么说——

<details>
<summary>Original English</summary>

>> Well, I mean, neither of you actually answered my question about conversations you've had which uh cuz I'll tell you a conversation I had last week in DC. I had drinks with a member of Congress, pretty senior ranking guy, and the conversation had two parts to it. One is I think one of the CEOs of the biggest companies in the world is completely freaked out about cyber and he's losing his mind and he doesn't know what to do and I just had dinner with him and here's all the stuff he said. And then, I also think that by Q4, we might see a 50-state ban on data centers. Which isn't likely, but he says

</details>

**>>**: 50 个州可是一个庞大的数字，太夸张了。

<details>
<summary>Original English</summary>

>> 50's a big number. Big number.

</details>

**>>**: 在这个国家，50 个州何曾在任何事情上达成过一致？

<details>
<summary>Original English</summary>

>> Have 50 states ever agreed on anything in this country?

</details>

**>>**: 从来没有。好吧，大概六件吧——

<details>
<summary>Original English</summary>

>> No. Well, a few things about six

</details>

**>>**: 那可真是奇迹了。

<details>
<summary>Original English</summary>

>> be amazing.

</details>

**>>**: ［笑声］

<details>
<summary>Original English</summary>

>> [laughter]

</details>

**>>**: 好吧，把大家都召集起来。在任何时候只要所有人在某件事上全部达成一致，你就知道这肯定不是真的。但是，我认为——

<details>
<summary>Original English</summary>

>> Okay, get everyone together. Well, whenever anyone agrees on something, you know it's not true. But, I think um

</details>

**>>**: 那简直就像神迹降临一样。

<details>
<summary>Original English</summary>

>> It'd be like a miracle.

</details>

**>>**: 关键在于，这两句话居然都是出自同一个政界要员之口。那么，在你们看来这件事最终会如何演变？我们该如何在这条前行道路上破局？

<details>
<summary>Original English</summary>

>> And and it's that it's it's the fact that both of those statements are being being said by someone. So, where do you think this resolves? Like, how do we resolve this path forward?

</details>

**>>**: 他确实很擅长抛出这种尖锐问题。

<details>
<summary>Original English</summary>

>> He's good at this.

</details>

**>>**: 试着回答一下这个——

<details>
<summary>Original English</summary>

>> Try to answer the

</details>

**>>**: 直接回答这个问题。听着，在我们之间，以及你们小组的所有成员之间，我们大家都与现任政府、上届政府的不同成员进行过各种形式的对话交流。参议院的任期比单一届政府要长得多，而众议院的更迭则要快得多。

这个问题从 2022 年起就一直摆在桌面上。参议院在 2022 年举行了闭门听证会，在 2023 年举行了公开听证会；众议院召开过，白宫在前后两届政府任内也都组织过，他们就这个问题反复打转争论不休。关于 AI 和数据中心的监管博弈——请原谅我在这里要说一句抱歉且愤世嫉俗的实话——纯粹是被民粹主义所绑架驱动的，根本不是基于任何客观现实。全都是出于“如果我这么表态能赚取更多选票，我是不是应该装出一副要推进这些限制的姿态”。

政治终究是政治。我不会否认它的存在，它是客观现实。即便如此，依然有足够多具有远见的人深刻关切着国家的长期经济优势，而这正是当下正在上演的艰难平衡之术。我确实认为我们目前总体上处在相对正确的平衡点上，但我不得不承认，一场大选就可能彻底打破平衡木的倾斜方向。至于数据中心，我认为 50 个州全部下达禁令的概率为零。有没有可能其中 30 个州出台禁令？完全有可能。但到那个时候，剩下的那 20 个州只会兴奋地坐地数钱、拍手称快。

<details>
<summary>Original English</summary>

>> say a direct question. So, look, amongst us, we have all and all the members of your group have we all had different conversations with different members of this administration, the previous administration, the Senate runs longer than just one admin. Congress tends to change a lot faster. This question has been in there since 2022. The Senate had closed hearings in '22, they had open hearings in '23, Congress had them, the White House had them in both admins, and they go round and round this question. The regulation question on AI and data centers is driven I'm going to be sorry and cynical is driven by populism, not by any reality. If I can get more votes, should I look like I'm trying to do those things. Politics is politics. I'm not going to say that's not real. It is real. That said, enough people also care deeply about the long-term economic advantage, and so that's the balancing act that is happening. I do think we're on the correct balance right now, but I'll acknowledge an election can change where we fall on that balancing act. On data centers, I think there's no chance all 50 will ban. Is it possible 30 will ban? Yes. The remaining 20 will rub their hands in glee at that point.

</details>

### 全球算力鸿沟与历史周期：资本密集 vs 劳工保护的终局分野

**>>**: 如果我们从地缘政治的维度观察片刻，我们似乎正在滑向一个充斥着“拥有者与匮乏者”（haves and have-nots）的世界。在座的各位全都是拥有者。你们立足于西方主流市场企业，你们享有与像你们这样的顶尖行业领袖合作的特权与红利。

但是这里存在着极高的准入门槛成本，对于世界其他地方任意抽选的一家普通企业来说可能毫无经济可行性。

当这些模型变得如此无所不能、且在边际成本上几乎趋于免费时，未来究竟会发生什么？现实的具体表现形态会是怎样的？我相信你们肯定思考过这个关于如何应对的战略问题。那么，你们是如何看待这个难题的？这种“拥有者与匮乏者”之间的割裂断层。

<details>
<summary>Original English</summary>

>> If you look geopolitically for a second, it seems like we're trending to a place of haves and have-nots. So, I can everybody in this room is a have. You know, you're a Western market company. You have the benefit of being able to work with guys like you. But there's a certain price of entry that may not make sense for the random pick your company anywhere else around the world. What happens then when these models are so capable and effectively free? What is the actual manifestation? I'm sure you've had to think about this in terms of how you want to respond. So, how do you how do you think about that problem? This separation of haves and have-nots.

</details>

**>>**: 听着，我认为 Arvind 刚才说过，你必须把技术成本打得足够低，让所有人都能轻松获取。我认为我们拥有实现这一目标的历史机遇。我不认为它的使用成本会高昂到让任何一家正常运转的商业组织无法在自身财务预算内找到自保防御的手段。［清嗓子］

因此，我不认为我们最终会沦入拥有者与匮乏者对立的极端绝境。我认为更大的挑战——也是与在座各位切身利益更为相关的议题在于：我深切担忧全球算力基础设施的飞速突破将被死死局限在全球两个超级大国之内。我们在世界其他地方恐怕很难看到如此均衡的算力分布。而算力在当下是极度昂贵且稀缺的资产，目前在全球范围内要想获取足以进行大规模运算的算力极其艰难。而接下来的严峻挑战将在于：你距离核心算力震中越遥远，你就越不可能获得充足的计算资源。这并不是出于经济层面的原因，而纯粹是由于物理层面的供应链产能瓶颈。

我认为这才是更严峻的挑战，对吧？你完全可以是一家位于欧洲的企业，怀揣着卓越的抱负和强烈的内驱力去拥抱创新、去优化业务并全力狂奔；但你可能会突然惊愕地发现，仅仅因为你远离全球核心技术震中，你根本无法获得像欧美西方世界或中国企业所能唾手可得的那种充沛算力支撑。

<details>
<summary>Original English</summary>

>> Look, I think Arvind said that you have to make technology so cheap that it can be easily accessible by everyone. And I think we have the opportunity of making that happen. I don't think that it's going to be so expensive that if you can run an economic enterprise, it should be possible in the envelope to be able to find a way to protect yourself. [clears throat] So, I don't think we're going to end up in a have have-not scenario. I think the bigger challenge which is more pertinent to people in the room is I fear that we will see fast advances in compute development in two large countries in the world. We may not see that as evenly distributed across the rest of the world. And compute is very dear right now. It's very hard to get compute to run anything at scale. at the current moment. And the challenge is going to be that the further way you are from the epicenter, the less likely you will have access to this computer. It's not because of economic reasons, it's purely because of supply constraints. I think that's the bigger challenge, right? You could be a company in Europe and you have the right intentions and motivations to go and sort of innovate, optimize, and run with it. And you may just suddenly discover that because you're far away from the epicenter, you don't get access as much as companies in the Western world and in the US or perhaps in China going to get.

</details>

**>>**: 听着，我喜欢回溯历史，因为历史总能为我们揭示这些技术是如何铺开演进的规律。我认为这正是经典的“劳动力 vs 资本”（Labor vs. Capital）之间的权衡博弈再次上演。

这一幕在 18 世纪发生过，在 19 世纪再次上演，在 20 世纪又重新演进了一遍。在历史上过去的七八个类似周期中，那些在资本端倾注更多资源而不是一味担忧劳动力成本的主体，往往在每一个周期中都成为了最终的胜出者。因此，这一次历史周期同样会上演相同的剧情。

正如 Nikesh 刚才所指出的，这里的两个大国同样极度乐意且坚定地走高度资本密集的路线。

<details>
<summary>Original English</summary>

>> I think look, I I to look at history because it gives us some information on how these things roll out. I think this is the classic labor versus capital trade-off that is happening. It happened in the 1700s, it happened again in the 1800s, it happened again in the 1900s. People who spend more on capital than worried about labor tended to win every previous one of the seven or eight cycles like this. So, this is what is going to happen this time. What Nikesh pointed out is the two nations here are also quite willing to be capital intensive.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 现实根本没有那么简单，而且这两个国家归根结底都愿意接受劳动力在某些环节变得不再那么核心的现实。

历史的演进轨迹向来如此。那些死死受困于社会舆论偏见以及左倾意识形态、坚信必须“不惜一切代价捍卫现有劳动力岗位”的国家最终将一败涂地。这里强调的不是说社会不该为劳工创造新机会，而是盲目要求“必须全盘保住每一个现存的旧岗位”。因为回到 Nikesh 的观点，技术的成本最终会足够便宜，其他国家的人完全可以利用这种先进能力；但羁绊在那些保守国家人们脑海里的执念却是：“天哪，这是否意味着我们会面临失业或岗位替代？”事实上，你理应拥抱这种岗位转移与替代，因为阵痛之后换来的往往是生产力更优越的高质量岗位。我认为正是这种社会哲学底层认知的差异，将最终决定这场大潮中的胜者与输家。

<details>
<summary>Original English</summary>

>> It's not as simple as this, and they're willing at the end of the day to concede that labor is going to be less important. That's the way it goes it's going to play out. Nations that get very hung up on social and left-leaning philosophies that labor has to be protected at all costs. Not that there has to be opportunity for labor, but every existing job has to be protected, or the ones are going to lose. Because I think the ones there, to Nikesh's point, it's cheap enough. Somebody in one country can use the capability, but what's going to be in their head is, "Hey, but does it mean there's a job loss or a job displacement?" Job displacement you should take because it may result in a better job. I think that's the social philosophy that's going to determine winners and losers here.

</details>

### 从IBM大型机到英伟达：垂直整合的技术壁垒与利润转移

**>>**: 在把提问权交给你们作最后总结之前，我想问最后一个问题，但这也是抛给你们二位的压轴问题，你刚才在这里提到了这一点，非常棒。你能讲讲那个故事吗？

我是垂直整合（Vertical Integration）的铁杆拥趸，超级狂热的粉丝。我认为市场向来像钟摆一样周期性摆动。曾经有过这样一个时代，哪怕是在上世纪 60 年代、70 年代和 80 年代，当时跨行业企业巨头（Conglomerate，企业联合大集团）横行，那曾经是极其有价值的企业形态；在充满动荡的时代，它是资本最坚实的避风港。因为企业联合体本身就是组织运转的最高效机制。而随后，当迎来和平与繁荣时期，人们便开始将其肢解拆分。而我认为，我们现在正重新回归企业巨头整合的世界。你刚才在后台跟我讲了 IBM 在巅峰时期垂直整合的故事。我只想让你分享一下，然后想听听 Nikesh 对这里的垂直整合有什么看法。

<details>
<summary>Original English</summary>

>> I have a final question before I give it to you for the final question, but the my final question to both of you, you mentioned this here, which was great. Can you tell the story about I'm a huge fan of vertical integration, huge fan. I I think like, you know, markets swing in pendulums. You know, there was a world, like even in the '60s, '70s, and '80s where there was the conglomerate, and it was a an incredibly valuable enterprise, and it was in a time of turbulence, it was a safe harbor for capital. Because the conglomerate was the mechanism by which you organized. And then when you had peace and prosperity, then people disaggregated. And I think we're moving back to the world of the conglomerate, and you told me that you just back there about vertical integration of IBM at its peak. I just wanted you to and then Nick asked what your thoughts on vertical integration over here.

</details>

**>>**: Jim 和我过去经常讨论的主题之一就是 IBM 大型机（IBM Mainframe）。顺便提一句，在座的不少人其实至今都在极好且大规模地使用着它。IBM 大型机历经了 65 年的岁月洗礼依然屹立不倒。为什么？

因为它从诞生起就是高度垂直整合的。虽然我们现在的整合深度稍微减弱了一些，不再一直深扎到底层泥土（Dirt）了。在 60 年代，我们真的是一路垂直整合到了最底层的“泥土”。也就是说，我们自己找沙子提纯，自己做晶圆，自己建晶圆厂，自己造芯片，从头制造直至包裹在整台机器外部的金属外壳。这种极致的垂直整合彻底避免了任何 IP 技术泄漏，而且允许我们将整套软硬件技术栈的全部商业利润稳稳留在公司内部。

今天，我们唯一不亲自操刀的环节只有代工厂晶圆制造。尽管如此，芯片的架构设计、底层工程架构、系统高可用与容错冗余设计、以及绝大部分的核心软件仍然全在公司内部闭环。而针对垂直整合，企业必须做出战略抉择。

<details>
<summary>Original English</summary>

>> So, what Jim and I have often talked about is the IBM mainframe. Which, by the way, there's a few people in the room who do use it quite well and at scale. The IBM mainframe has lasted 65 years. Why? It was vertically integrated. We're a little less right now in the sense we don't go all the way to dirt. In the '60s, we went all the way to dirt. Meaning, we found sand, we made our own wafers, we built our own fabs, we built our own chips, every single thing out to the metal that surrounded the machine. What that avoided was any IP leakage, but it allowed us to keep the profit of the complete stack in the company. Today, the only piece we don't do is the actual fab. Still, the design of the chips, the design of the engineering, the resilience, the bulk of the software is inside. And that vertical integration, you got to decide.

</details>

**>>**: 是的，那是当然。

<details>
<summary>Original English</summary>

>> Yeah, of course.

</details>

**>>**: 我可不会傻到自己去炼钢打铁做金属机壳，金属直接去外部采购就行了。

<details>
<summary>Original English</summary>

>> I'm not going to make our own metal. You buy metal.

</details>

**>>**: 没错。

<details>
<summary>Original English</summary>

>> And right.

</details>

**>>**: 外包晶圆代工是出于巨大的规模效应考量。但我认为，在能够形成极其核心的压倒性竞争优势的关键领域进行垂直整合——这又重新契合了你们两位之前探讨的基础设施命题——深刻厘清你究竟想在哪个生态位立足、而在哪些被大宗商品化的环节（Commodity）坚决抽身退出，是极其重要的商业法则。

<details>
<summary>Original English</summary>

>> Fabs is because of scale. But I think that vertical integration in areas which are of incredible important advantage, which goes back to the infrastructure point the two of you were making before, is incredibly important to understand where do you want to be and where, if it's a commodity, then you should not be.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 但你完全可以在当今时代看到这一战略的现代典范：英伟达（Nvidia）。

<details>
<summary>Original English</summary>

>> But you can see that the modern-day version of that is Nvidia.

</details>

**>>**: 没错。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 如果你观察黄仁勋（Jensen）正在做的事情，他就是现代版垂直整合技术栈的集大成者。他甚至跑去投资入股了——

<details>
<summary>Original English</summary>

>> If you look at what Jensen is doing, he's a modern-day version of the vertically integrated stack. And he went and bought

</details>

**>>**: 黄仁勋本身就深扎在泥土的最底层。

<details>
<summary>Original English</summary>

>> Jensen is at the dirt.

</details>

**>>**: 他确实扎在最底层。

<details>
<summary>Original English</summary>

>> And he's at the dirt.

</details>

**>>**: Hugging Face。他心里非常清楚在前沿模型与其他多样化模型之间必然会形成动态平衡。他试图资助生态系统中的每一个关键玩家，以此确保他们绝不会偏离他亲手打造的垂直整合全栈生态。而牢牢掌控垂直全栈的最大红利在于：你可以随心所欲地决定让全栈中的哪一个层级沦为低利润的大宗商品（Commoditize）。

因此，你可以自主决定在不同层级之间肆意转移利润池。如果你发现外部竞争对手正在大举进攻某一个特定的——

<details>
<summary>Original English</summary>

>> hugging face. He wants to He understands that there's going to be balance between frontier models and other models. He's trying to fund everybody in the ecosystem to ensure that they don't stray from the vertically integrated stack that he's producing. And the good news is if you control the vertical stack, you can decide which part of the stack to commoditize. So, you can decide to move profit between layers. And if you see that there are other people attacking a certain

</details>

**>>**: 一点没错。

<details>
<summary>Original English</summary>

>> Exactly.

</details>

**>>**: 技术栈层级，并且企图摧毁那一层级的利润池，你完全可以把利润顺势转移沉淀到该技术栈的其他层级中去。你现在完全可以看到这种操盘手段正在上演。这构成了极其强大的市场支配杠杆。

<details>
<summary>Original English</summary>

>> part of the stack, you you they destroy the profit pool on that stack, you move the profit to the other part of the stack. And you can see that happening. Very powerful market leverage.

</details>

### 应用层的端到端闭环壁垒与个人智能体护城河

**>>**: 那么为了让你正面接招，如果审视当下的应用层（Application Layer），你认为 OpenAI 或 Anthropic 应该采取的最显而易见的垂直整合战略是什么？而对于那些可能正处于被颠覆波及接收端的传统软件公司而言，他们的防御反制手段又该是什么？

<details>
<summary>Original English</summary>

>> So, to put you on the spot. So, if you look at the application layer today, what's the obvious vertical integration strategy that OpenAI or Anthropic should be taking? And then what's the defensive mechanism for the companies that are maybe on the receiving end of that?

</details>

**>>**: 我认为大家已经在目睹这种趋势了。而且我认为我们把这场对话给肤浅庸俗化了。我们整天挂在嘴边谈论开源模型、开源权重；这在字面意义上其实就是“开放栈 vs 封闭栈”的较量。因为在未来的某个时刻，像 OpenRouter 这种概念的路由转发方式将变得几乎难以维系。

因为模型正在变得越来越复杂，每一个模型都需要更大的内存、更庞大的上下文窗口以及更深维度的理解能力。你根本无法将上下文和记忆与底层的核心推理彻底剥离切割开来。

现在，如果你非要把推理运算从上下文与记忆中剥离出去，那么所谓的开放路由（OpenRouter）充其量只能负责在前后来回搬运推理 Token 而已。

因此我认为随着时间的推移，大家会开始意识到：缺乏端到端闭环的全栈是毫无意义的。这就好比我们刚才闲聊时你提到的 CPA（单次行动成本，Cost Per Action）逻辑。核心在于单次行动成本。而执行该行动要求你必须自始至终贯通从 Prompt 输入直到最终结果达成的完整全套业务逻辑。随后，系统内沉淀的专属记忆将大幅降低这一过程的摩擦阻力。到那时，对于用户而言，要把自身业务任务从一个软件栈迁移到另一个软件栈所面临的迁移摩擦将极其高昂，因为当前的系统完整封存了你的全部业务上下文与交互记忆。

大家即将见证这一幕的发生。看看目前在个人智能体（Personal Agent）领域正在上演的剧变吧，对吧？如果你开始训练一个深度融合了你的全部个人上下文、连接了你的所有 API 接口与业务系统互联通道的个人 Agent，你就已经筑起了一条坚不可摧的商业护城河。因为我绝不可能每天把它打包整体迁移到下一个、再下一个完全陌生的技术栈上。因此我认为你会发现，在应用层，他们同样会构筑属于自己的垂直全栈，这将涵盖从业务软件、底层推理、长效记忆直至全量上下文的端到端完整闭环。

<details>
<summary>Original English</summary>

>> I think you're already seeing that. And I think we're we're we trivialize this conversation. We start saying open models, open weight. It's literally it's an open stack versus a closed stack. Because I don't think I I think at some point in time this notion of running something like an open router become impossible. Because models are getting more and more each model is requiring more memory, more context, more understanding. You can't separate context and memory from the reasoning. Now, if you want to separate reasoning from the context and memory, then open router is only responsible for moving the reasoning tokens back and forth. So, I think over time you start seeing it doesn't make sense that you have a effectively end-to-end stack. It'll be It's like a CPA you talked about earlier when we were chatting. So, it's a cost per action. The action will require you to go and traverse the entire logic from prompt till outcome. And then memory will require and make it easier. And there'll be too high a friction for you to move your task from one stack to the other stack because it has all your context and memory. And you're going to see that. Look Look at what's happening in the personal agent space, right? If you start training a personal agent with all your context, all your APIs, all your connectivity, now you built a moat. Cuz now I can't take that every day and move it to a next stack and the next stack. So, I think you will find in the application layer they're going to have a vertical stack as well. Which will go to the entire process of software, reasoning, memory, context.

</details>

**>>**: 顺着你的逻辑推演下去，到那时每个人都将拥有自己专属的闭环体系了。是的，因为这纯粹是出于最理性的必然选择。

<details>
<summary>Original English</summary>

>> To your logical conclusion, everybody will have their own then. Yes, because it's just the right thing to do.

</details>

**>>**: 到那时，在企业级软件赛道上，蛮力分发渠道（Brute Force Distribution）将再次成为决胜的关键，对吧？大家正在消费端看到，依靠强力分发渠道将展开残酷的生死竞逐。

在接下来的 3 个月里，每一个前沿 AI 实验室都会在类似 Muse 概念的产品形态上展开全方位的全场紧逼反扑，对吧？他们在 6 到 9 个月前尝试过但失败了；如今伴随着 Facebook 向外界展示了它行之有效的落地路径，我认为几乎所有人都跟进掌握了这一能力。届时全套 API 都会铺开。这将演变成一场围绕终端消费者控制权的最惨烈争夺战。iPhone 里的每一款现有 App，都必须彻底沦为无头化（Headless）。

<details>
<summary>Original English</summary>

>> And then brute force distribution wins again in the enterprise space, right? You're seeing that in the consumer space brute force distribution is going to compete. In the next 3 months every frontier lab is going want a full-on full court press on the Muse concept, right? They tried that 6 to 9 months ago. It didn't work. They Now, with Facebook showing us how it can work, I think pretty much everybody has it. There will be APIs. It will be the largest battle of consumer control. Every app that exists in the iPhone is has to become headless.

</details>

### 企业软件与SaaS的大溃退：平台整合与终局价值重估

**>>**: 也许我们可以在结尾时将话题从垂直整合重新拉回到横向扩张。在企业级科技公司中，通过兼并与收购（M&A）进行横向扩张、以此驱动协同效应和交叉销售一直是一项经典的商业战略。显然，你们两位在这方面的战略布局与落地执行都极其出色。

在过去一年或今年，面对估值倍数的剧烈波动以及不断攀升的资本成本，你们两位的核心并购视角受到了怎样的冲击与重塑？

<details>
<summary>Original English</summary>

>> Maybe we can wrap by going from vertical integration to horizontal expansion. It's been a common business strategy in enterprise technology companies to expand horizontally through M&A, drive synergies, cross-sells, and so on. And you've obviously both done it exceptionally well uh and executed it well. How has your view been affected in the last year, this year, let's say, in terms of valuations and multiples, cost of capital?

</details>

**>>**: 我们先放在网络安全的语境下谈谈并购，然后再探讨网络安全之外更广泛的并购逻辑。

在网络安全的语境下，过去 8 年里我始终坚持一个观点：我们的客户被迫购买 40 种互不相通的碎片化单点解决方案，然后再费尽九牛二虎之力去把它们拼凑粘合在一起，这简直荒唐透顶。

我们连自己系统的底层交互都勉强才搞明白，你难道还指望能搞懂其他 10 家供应商的代码然后把它们无缝拼起来？愿上帝保佑你的灵魂吧。对吧？因此，我们正在以最快的速度推进，将行业内分散的各个孤岛环节整合起来，寻找打通机制让底层数据实现统一协同。我认为这是一场长期的跋涉。

如果你想找历史参照物的话，回想一下当年我［哧哼］——我的第一份工作是多年前在富达投资（Fidelity Investments）。当时我们内部有 23 套互相独立的业务系统，这在今天被统称为 CRM（客户关系管理系统）。我们当时有主数据表，有各种与之做关联拼接的附表，我们有 23 个不同的独立应用程序来处理交易和各种业务流程。而到了今天，你直接从货架上采购现成软件即可，虽然你会对 Salesforce、Microsoft Dynamics 或 Oracle 昂贵的软件许可报价感到肉疼。

因此在 30 年的时间跨度里，所发生的历史剧变就是：那些碎片化方案被大举整合并入了一个单一的综合平台之中。客户再也不需要自己去痛苦地拼接缝合解决方案了。因为必然的规律是：这些同质化的软件方案最终会走向高度一致，它们彼此越来越像，所做的事情大同小异，失去了任何核心差异化壁垒。

所以我认为同样的整合趋势必将在网络安全领域重演。而这也正是我们竭力推进的战略：我们努力筛选出各自细分赛道最顶尖的标的，通过深度缝合让它们协同运转，从而免去客户自行拼接的痛苦。我认为这就是网络安全领域并购的底层逻辑。出于某种原因，由于 AI Mythos 这类重大安全恐慌事件的催化，网络安全板块近期的市场估值水涨船高，这很正常；但这种狂热随着时间推移终将回归理性，因为所有这些企业最终都将不得不向网络安全领域砸进数额惊人的真金白银。

而脱离网络安全赛道放眼更宏观的企业软件，我认为这又回到了我们刚才与 Chamath 讨论的核心话题：当下极难看清传统纯软件企业的终局价值（Terminal Value）。

在当前 AI 突飞猛进的技术格局下，根本看不清究竟有哪家传统软件公司能在未来 5 到 8 年的残酷洗牌中存活下来，所有这些现有公司的产品市场契合度（PMF, Product-Market Fit）都在面临被连根拔起的系统性颠覆。我们大家心里都清楚，如果将 AI 深度且完美地融入进去，在最理想的构想形态下我们现有的软件原本应该展现出怎样的运作体验。我知道我自己采购的软件到底希望被包装成什么样子，如果我手里有一根魔法棒能随心所欲让软件自动化运转，我极其清楚在“AI 原生优先（AI-First）”的世界里软件应该如何工作——而这意味着，市场上终究会有人把它彻底做出来。

因此，我认为在接下来的几年里，整个 SaaS 行业将会迎来惊天动地的毁灭性颠覆大洗牌。

<details>
<summary>Original English</summary>

>> Let's talk about M&A in the context of cyber. Then we can talk about M&A in the context outside of cyber. In the context of cyber, I have always maintained over the last 8 years that it's silly that our customers have to buy 40 different solutions and stitch them together. We barely understand our You think you understand our 10 other vendors with that? You can stitch it. God bless your soul. Right? So, we're working as fast as we can to take disparate parts of our industry and find the way to stitch them together to have the data work together. I think that's a journey. And if you want parallels, when I started [snorts] my first job was at Fidelity Investments many years ago. We had 23 systems which collectively would be called CRM today. We had master tables. We had tables that concatenated with them. We had 23 different applications that did trading and things. Today, you go buy it off the shelf and you cringe at the cost of Salesforce or the cost of Microsoft Dynamics, Oracle, whatever you choose to do. So, in 30 years, what's happened is that's consolidated to a singular platform. The customers don't stitch the solutions anymore. Because what happens is these software solutions become consistent. They all become like each other. They all probably do the same thing and there's no differentiation. So, I think same thing's going to happen to cyber. That's what we try to do. We've tried to find things that are best in their category, stitch and make them work so our customers don't have to do the stitching. So, I think that's kind of the answer on cyber. For some reason, you know, cyber is enjoying much better valuations lately because of the the AI mythos event, which is fine, which will rationalize over time because all these guys are going to go spend unlimited amounts of money on cyber. Outside of cyber, I think it goes back to the conversation Chamath and we were having earlier about it's very hard to understand the terminal value of software. It's not clear what software is going to survive the next 5 to 8 years with where we are from an AI perspective and the notion that product market fit is getting disrupted from any of these companies. We all know with if AI was applied well, how our current software should behave in an ideal scenario. I know what I want from how to package the software that I buy. I know if if I could have my magic wand and make it do things, I know exactly how it should work in an AI first world, which means somebody's going to do it. So, I think there's going to be huge disruption in the SaaS space over the next few years.

</details>

**>>**: Arvind，你目前在看市场上的标的时，心里会不会暗自琢磨：“嗯，这估值倍数可真是诱人”？

<details>
<summary>Original English</summary>

>> Arvind, are you looking at anything thinking, "Hmm, juicy multiples."

</details>

**>>**: 这个嘛，纵观这一年，在今年初的时候估值倍数确实极具吸引力，不过一个月前就没那么诱人了。我们会静观其变，看看接下来的几个月市场如何演变。

但我其实想顺着 Nikesh 的思路进一步展开。这种现象绝不仅限于网络安全领域。

当下一个普通的中大型企业平均要使用 500 到 5000 家互不相同的独立软件供应商。

在一个你必须对所有软硬件进行全方位防御的世界里，这绝不仅仅是网络安全层面的威胁，而是一个规模极其庞大的潜在受攻击面。因此你必须扪心自问：我能否凭借轻量级的小型 AI 能力直接替代其中的 490 家供应商？我是否必须重新回归、全力依托 5 到 10 个核心主流大平台？这背后必然意味着发生大规模的系统性整合，因为庞大的资金预算流向了那里。这就是我深信必将上演的行业结局。

因此，大整合势不可挡；因为如果你想维持极低的分发成本，这些平台级巨头就能包揽全部的分发渠道；而如果单点单项软件本身的独立商业价值正在急剧贬值，你就根本无力承担为每一款细分软件都去搭建独立分发销售渠道的高昂成本了。我坚信这一格局必将彻底兑现，无论这需要经历 6 个月还是 6 年，终局都必然落在这一算式方程之内。

同时我也认为，对各类软件本身必须做出严格区分：有一类软件的价值极度依赖高频的人机交互（Interaction Value），而正如我们清晰目睹的那样，这类交互价值完全可以被大量的 AI 原生能力彻底取代并颠覆，你刚才举出的两个例子本质上都属于重度依赖交互的软件类型。

<details>
<summary>Original English</summary>

>> So, So, over the year, it was very attractive at the beginning, not so attractive a month ago. We'll wait and see how it goes over the next few. But actually, I want to build on Aneesh's thought. This is not just unique to cyber. The average enterprise uses anywhere from 500 to 5,000 distinct software vendors. In a world when you have to protect against it all, it's not just the cyber threat, that's a massive attack surface. So, you have to ask yourself, could I replace 490 of them with minor AI capabilities and do I need to go back and leverage five to 10 main platforms? That implies massive consolidation, because that's where the spend goes. That's what I believe is going to play out. So, there's going to be consolidation, because if you want to keep your cost of distribution low, then they can distribute all of it. And if the value of that software is falling, then you cannot afford independent uh distribution for each of those. I believe that's going to play out, whether it takes 6 months or 6 years. It's somewhere inside that equation. Uh I do think also software should be distinguished. There is software where there is a lot of interaction value, which as we've seen clearly can be replaced with a lot of AI. Both examples you used were things which were interaction-rich.

</details>

**>>**: 没错。

<details>
<summary>Original English</summary>

>> Right.

</details>

**>>**: 但是，如果归根结底你的底层诉求是：我需要系统达到 $10^{-15}$ 级别的极高可靠性——

<details>
<summary>Original English</summary>

>> But if in the end you go down to I need you to be reliable at 10 to the minus 15,

</details>

**>>**: 没错。

<details>
<summary>Original English</summary>

>> Right.

</details>

**>>**: 比如为零售银行日常交易或会计结账进行核心数据库检索，我认为要想轻易地用——

<details>
<summary>Original English</summary>

>> which is a database lookup for somebody doing retail banking or closing the books,

</details>

**>>**: 确实。

<details>
<summary>Original English</summary>

>> I think that's going to be hard to replace that easily

</details>

**>>**: 用 AI 生成的不可预测的代码软件去替代它，将会极其困难。所以我认为，在评估替换的容易程度上，软件类型之间将会出现泾渭分明的鸿沟。

<details>
<summary>Original English</summary>

>> Right. with uh AI-generated software. So, I think there is going to be a distinction on how easy it is going to be to do that.

</details>

**>>**: 在正式切换系统之前，你必须先让数字孪生（Digital Twin）并行跑上好几年时间。

<details>
<summary>Original English</summary>

>> digital twin for years before you cut over.

</details>

**>>**: 一点没错。

<details>
<summary>Original English</summary>

>> Correct.

</details>

**>>**: 确实如此。

<details>
<summary>Original English</summary>

>> Yeah.

</details>

**>>**: 到了那个地步，去强行替换它在经济上根本就没有任何成本优势可言了。

<details>
<summary>Original English</summary>

>> And then is there's no cost advantage to do that.

</details>

**>>**: 确实如此。

各位，非常感谢你们。Arvind Krishna，Nikesh Arora，非常感谢两位的精彩分享。

<details>
<summary>Original English</summary>

>> Yeah. Guys, thank you very much. Arvind Krishna, Nikesh Arora, thank you.

</details>

**>>**: 谢谢。

<details>
<summary>Original English</summary>

>> Thank you.

</details>

**>>**: 感谢大家，感谢在座的各位。

<details>
<summary>Original English</summary>

>> Thanks, everybody, all of you.

</details>

**>>**: ［掌声］

<details>
<summary>Original English</summary>

>> [applause]

</details>

**>>**: 我要全力以赴了（I'M GOING ALL IN）。

<details>
<summary>Original English</summary>

>> I'M GOING ALL IN.

</details>

**>>**: ［音乐］
［音乐］
［音乐］

<details>
<summary>Original English</summary>

>> [music] [music] [music]

</details>

**>>**: 我要全力以赴了（I'm going all in）。

<details>
<summary>Original English</summary>

>> I'm going all in.

</details>