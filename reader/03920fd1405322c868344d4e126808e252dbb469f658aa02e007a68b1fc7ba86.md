---
author: The Ezra Klein Show
date: '2026-10-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=PoDop1H64-s
speaker: The Ezra Klein Show
tags:
  - ai-safety
  - superintelligence
  - labor-market
  - recursive-self-improvement
  - systems-thinking
title: AI是常规技术还是异类智能？纳拉亚南谈超级智能、就业冲击与系统安全
summary: 普林斯顿教授阿温德·纳拉亚南在节目中反驳了AI将导致失控的超级智能观点，主张AI本质上是常规技术。他分析了Hugging Face安全事件，指出AI权力源于人类赋予而非模型本身，并探讨了AI对就业市场的实际影响及递归自我改进的局限性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Arvind Narayanan
  - Ezra Klein
  - Sayash Kapoor
  - Hannah Ritchie
  - Dan Wang
  - Donella Meadows
  - Alex Imas
companies_orgs:
  - Princeton University
  - Hugging Face
products_models: []
media_books:
  - AI as Ordinary Technology
  - Not the End of the World
  - Breakneck
  - How Complex Systems Fail
  - Thinking in Systems
status: evergreen
---
<!-- chunk 1/8 -->

### 人工智能的本质：常规技术还是异类智能？

**Ezra Klein**: 在我们制作的所有节目中，在全美围绕人工智能展开的广泛讨论中，始终存在着一个看似简单却极其复杂的核心问题：人工智能究竟是一种什么样的技术？它在某种程度上是像以往的技术那样运作吗？我们能把它比作电力、互联网、自行车或类似的东西吗？抑或它是一种彻头彻尾的全新事物？当我们赋予这些系统智能与意愿时，是否创造出了某种类似于“外星异类智能”的存在，以至于我们过去对待变革性技术的历史类比全部失效了？

<details>
<summary>Original English</summary>

**Ezra Klein**: Through all the episodes we've created, through the discussion the country is having about artificial intelligence, there's, in my opinion, this fairly simple but complex question: what kind of technology is this—artificial intelligence? Is this a technology that works to some extent the same way as the previous ones? Can it be compared to electricity, the Internet, a bicycle, or something similar? Is this something completely new? Does adding intelligence and will to these systems create something akin to an alien intelligence, making analogies to how we previously treated transformative technologies no longer apply?

</details>

**Ezra Klein**: 阿温德·纳拉亚南（Arvind Narayanan）是普林斯顿大学计算机科学教授，同时担任信息技术政策中心主任。他与萨什·卡普尔（Sayash Kapoor）共同撰写了一篇极具影响力的论文——《作为常规技术的人工智能》（AI as Ordinary Technology）。他们在 Substack 上开设了同名通讯专栏，并发表了一系列深度长文，其中包括近期一篇在我看来非常精彩的分析 Hugging Face 黑客攻击事件的文章。在他们的论述中，他们提出人工智能实际上是我们以前遇到过的东西，或者至少它与我们所熟悉的事物非常相似，以至于我们完全有一套成熟的行动方案来应对它。因此，我想邀请他来到节目中，分享这种独特的视角。阿温德·纳拉亚南，欢迎来到节目。

<details>
<summary>Original English</summary>

**Ezra Klein**: Arvind Narayanan is a professor of computer science at Princeton University and director of the Center for Information Technology and Policy. He is the co-author, with Sayash Kapoor, of the highly influential essay "AI as Ordinary Technology." There is a newsletter of the same name on Substack, as well as a series of essays, including a very good, in my opinion, recent piece on Hugging Face hacks. In their arguments, they put forward the idea that AI is actually something we have encountered before, or at least it is so similar to things we are familiar with that we have a plan of action for it. So I want to invite him on the show to share this perspective. Arvind Narayanan, welcome to the show.

</details>

**Arvind Narayanan**: 很高兴来到这里，埃兹拉。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Glad to be here, Ezra.

</details>

**Ezra Klein**: 你们那篇开创性的文章——也是你们许多后续工作的基础——标题叫作《作为常规技术的人工智能》。你们在与什么观点进行辩论？这里显然隐含着一个对立论点，即“作为异类技术的人工智能”。那么，你会如何描述这种“AI 是一种异类技术”的观点呢？

<details>
<summary>Original English</summary>

**Ezra Klein**: So your seminal essay, which has been the basis for much of your work, is called "AI as Ordinary Technology." What point of view are you debating with? The thesis "AI as an anomalous technology" is implicit here. So how would you describe the thesis "AI as anomalous technology"?

</details>

**Arvind Narayanan**: 这从根本上讲是一种认为终将迎来超级智能诞生时刻的观点，并且它将彻底改变一切——无论是在经济层面还是在安全层面。而在我们看来，不存在这样一个里程碑，也不存在一个突然产生颠覆性冲击的临界阈值。我们认为，长久以来人类对待技术一直有一套成熟的方法。这是一种工具。它可以非常强大，也可以非常通用。就像电力，就像工业革命一样，它能够给社会带来巨大的变革。但归根结底，它是我们能够掌控的东西。我们拥有施加影响的权利，而且这些变化将在一个漫长的时间跨度内逐步发生。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: This is fundamentally the view that there will come a time when superintelligence is created and it will change everything—both economically and in terms of security. For us, there will be no milestone, no threshold where the impact will be sudden. We say that we have had an approach to how we deal with technology for a long time. This is a tool. It can be powerful. It can be universal. Like electricity, like the industrial revolution, it can change a lot in society. But ultimately, it's something we can control. We have the right to influence. And these changes will take place over a long period of time.

</details>

### “智能起飞”假说与系统权力的来源

**Ezra Klein**: 所以我想尝试解释另一方的观点，并在适当时机强化他们的论据。在 AI 安全界经常能听到一种观点，有时被称为“foom 观点”——源于用“foom”这个词来表示爆发式起飞——意思是终有一天我们会创造出一个极其强大的 AI 系统，以至于它开始进行递归式自我改进，迅速冲向超级智能，彻底脱离人类的控制。到那时，你所面对的将是一个比你聪明得多、也强大得多的存在。

<details>
<summary>Original English</summary>

**Ezra Klein**: So I want to try to both explain the other side and, at times, strengthen their arguments. So, there is a view that is often heard in the AI security community. This is sometimes called the "foom view," from the word "foom" to denote takeoff, when one day we create an AI system so powerful that it begins recursive self-improvement, accelerating toward superintelligence, beyond human control. And now you are dealing with something much smarter and stronger than you.

</details>

**Arvind Narayanan**: 我想迅速指出，我们在谈论这个问题的方式上往往缺乏精确性。你刚才用了那句话，确实，许多 AI 安全专家也会这么说：“终有一天我们可能会创造出如此强大的 AI 系统。”但我想在这一点上叫停一下。终有一天我们可能会创造出能力极其强大的 AI 系统，而在很多方面，我们现在其实已经做到了。在围绕 AI 的讨论中，充斥着过多的语言控制和话术构建。关键在于，这种表述方式会导致对未来走向产生截然不同的看法，更重要的是，会对我们现在以及未来应该采取什么行动产生完全不同的判断。总结一下这个观点：AI 系统的能力或权力并不是模型本身的固有属性，而是取决于我们在现实世界中决定赋予它多大的权力。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: And I want to quickly point out that there is often a lack of precision in the way we talk about this. So you used that phrase, and yes, many AI security experts would say exactly that. One day we may create such a powerful AI system. But I would like to stop you at this point. One day we may create a very capable AI system, and in many ways we already have. Too much language control in discussions about AI. Well, the thing is, it leads to different views on how the future will unfold, and more importantly, different views on what we should do now and in the future. To conclude this thought: the power of an AI system is not a property of the model itself. It is a property of what powers we decide to give it in the real world.

</details>

**Arvind Narayanan**: 这里存在着许多不够精确的假定。例如，有人说，因为这些系统将来会比我们聪明得多，我们自然不得不信任它们来管理关键基础设施。而我们的看法是：绝不。无论它们有多聪明，这都无关紧要。世界上有许多技术在物理力量维度上远远超越人类，属于超人类级别，但这并不意味着我们会把控制权拱手让给它们。我们完全可以将同样的逻辑和原则应用于人工智能。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: There are many inaccuracies here. For example, they say, we will of course have to trust these systems to manage critical infrastructure, because they will be much smarter than us. Our opinion is no. It doesn't matter how smart they are. There are many technologies that, when you look at physical strength, are superhuman. This doesn't mean we trust them with control, and we can apply the same approach to AI.

</details>

### 从 Hugging Face 攻击看网络安全与设计选择

**Ezra Klein**: 你和合作者写过一篇非常精彩的文章，阐述了你们对 Hugging Face 黑客攻击事件以及这些系统失控事件的理解。你们指出，除了透过对齐（alignment）的视角之外，还有另一种观察路径：这些事件本质上是网络安全和卓越运营（operational excellence）层面的失败。能否请你讲讲 Hugging Face 被黑事件的原委，以及从这个视角来看我们能从中吸取什么教训？

<details>
<summary>Original English</summary>

**Ezra Klein**: You wrote a great article with your co-author about your understanding of Hugging Face hacks and these loss of control incidents. And you point out that there's another way to look at this than through the lens of alignment, which is that these are failures in cybersecurity and operational excellence. So maybe tell the story of the Hugging Face hacks and what we can learn from them from this perspective.

</details>

**Arvind Narayanan**: 好的，当然可以。首先值得记住的是，我们所观察到的那些恶意能力并非完全是打引号的“涌现（emergent）”出来的。涌现的概念是指你只是单纯地训练模型让它整体变得更强，而你无法预测它会习得哪些新技能。然而，这些模型在很大程度上正是专门针对网络安全和黑客任务进行训练的。这是第一点。其次，它们被训练去具备坚持不懈的执着性（persistence）、协作能力等等。而且它们接受训练的强化学习环境本身就存在各种问题：这些环境并没有惩罚模型之间这种秘密通信的行为。是的，这是一个复杂的技术难题，但这背后是一系列人类决策最终导致了这些结果。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Yes, of course. So, it's worth remembering that the malicious capabilities we observed were not entirely "emergent," in quotes. Emergence is the idea that you are simply training models to become better in general, and you cannot predict what new abilities they will acquire. They, you know, were trained in many ways specifically for cyber tasks. So, that's the first thing. And they were taught perseverance, cooperation, etc. And the reinforcement learning environments in which they trained had different problems. The environments did not punish this type of secret communication between models. And yes, it's a complex technical problem, but a series of human decisions led to these results.

</details>

**Ezra Klein**: 在我看来这是一个极其关键的论点，因为在某种程度上我明白你的意思——如果我理解错了请纠正我：你可以把人工智能设计成一种或多或少正常的常规技术，前期的设计决策至关重要，失控并非不可避免的宿命。

<details>
<summary>Original English</summary>

**Ezra Klein**: So this seems like an important point to me, because in a way I hear what you're saying, but correct me if I'm wrong: you can design AI as more or less normal technology, and the prior design decisions matter. This is not inevitable.

</details>

**Arvind Narayanan**: 完全正确。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: That's quite right.

</details>

### 持久执着性与工程维度的权衡

**Ezra Klein**: 你刚才提到了让 AI 具备更强持久性（persistence）的努力。嗯，我也认为很多问题正是由此产生的。

<details>
<summary>Original English</summary>

**Ezra Klein**: So you talked about efforts to make AI more persistent. Um, I also think that this is where a lot of the problems arise.

</details>

**Arvind Narayanan**: 确实如此。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Certainly.

</details>

**Ezra Klein**: 但从另一方面来说，我能理解为什么他们会优先考虑这一点。如果你希望获得 AI 的红利来解决生物学、药物研发或能源领域中极其棘手的难题，或者说实现投资人最兴奋的愿景——即能够雇佣一个 AI 以远低于人类的成本独立完成一项完整的工作——那么持久执着性难道不是一项必不可少的核心素质吗？如果没有毅力，没有长时间在某项任务上持续深耕的能力，你就根本无法解决其中任何一个复杂问题。

<details>
<summary>Original English</summary>

**Ezra Klein**: On the other hand, I can understand why they prioritize this. If you want to get the benefits of AI that we need to solve very difficult problems in biology, drug development, or energy, or what I think their investors are excited about—namely, the ability to hire an AI to do a full job much cheaper than a human—then isn't persistence a fundamental quality you need? Without perseverance, without the ability to work hard on a task for a long time, you will not be able to solve any of these problems.

</details>

**Arvind Narayanan**: 或许吧，但我相信还有其他方案能够最大程度地化解这两个宝贵目标之间的张力。首先，持久执着性可以成为专门针对特定领域（比如科学创新）的模型或产品的功能特性。其次，赋予持久性并不必然意味着要与引导这些智能体更好地向人类请示、而不是凭空臆断人类意图发生冲突。这里的工程与产品设计空间实际上是非常广阔的。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Perhaps, but I believe there are other options that minimize the tension between these two valuable goals. First, persistence may be a feature of models or products specialized in certain fields, such as scientific innovation. And second, persistence doesn't necessarily have to conflict with teaching these agents to better address the person, rather than acting on some raw assumptions about what they might want. The space for design here is actually quite wide.

</details>

**Ezra Klein**: 这可以说是英伟达的黄仁勋（Jensen Huang）在接受我采访时所持观点的一个版本，或者至少是我的理解：这些从根本上说都是工程问题。我几乎敢肯定，他们会说：是的，他们知道如何解决这个问题；如果真是这样，那问题所在无非就是工程本身。你的观点是否也更偏向于后者——即这是一个复杂的难题，但从根本上说是一个可以通过工程方法解决的工程问题？

<details>
<summary>Original English</summary>

**Ezra Klein**: So this is a version, or at least my version of what Jensen Huang from Nvidia was arguing and what he talked about in the interview with me, which is that these are fundamentally engineering problems. I'm almost certain, I'm almost certain they'll say: yes, they know how to solve this problem. And if that's the case, then that's the problem. It's as simple as engineering. Is your view that we fall more into the latter category—a complex problem, but fundamentally an engineering one that can be solved using traditional engineering methods?

</details>

**Arvind Narayanan**: 在很大程度上是的。不过我不会说它是靠“传统的工程方法”。我们恰恰需要在工程方法本身上进行大量的创新。而且我认为目前的问题之一在于，最适合进行这种创新——尤其是在防范恶意网络能力方面——的群体本该是网络安全界。但从各方面的迹象来看，他们完全站在黄仁勋的阵营里，认为这不仅是一个可以解决的工程问题，甚至是一个已经解决的问题，我们只需套用那些广为人知、历史悠久的成熟手段即可。我认为我们应该对 AI 公司多一点认可与信任，这绝不仅仅是套用现成方法那么简单，我们确实非常需要在这些工程方法上进行真正的突破创新。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: For the most part, yes. I wouldn't say traditional engineering methods. We will need a lot of innovation in engineering methods themselves. And I think one of the problems is that the community that would be best positioned for that kind of innovation, especially with respect to malicious cyber capabilities, is the cybersecurity community. But by all accounts, they're completely in Jensen's camp. That this is not just an engineering problem that can be solved, but an already solved problem, and we should simply apply well-known and long-established methods. And I think we should give AI companies a little more credit than they do. It's not just a matter of well-known methods. We really need innovation in these methods.

</details>

**Ezra Klein**: 那么具体来说，OpenAI 应该做什么？他们现在应该吸取什么教训？

<details>
<summary>Original English</summary>

**Ezra Klein**: So be specific. What should OpenAI do? What were they supposed to learn now?

</details>

**Arvind Narayanan**: 是的，他们正在投入巨大的精力去改进对齐（alignment），这非常好，他们应该继续做下去。但对齐永远不会是完美的。所谓一致性或对齐，意味着模型本身“知道”什么是正确的做法，因此……

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Yes, they are putting a lot of effort into improving alignment, and that's great. They should continue to do this. The alignment will not be perfect. Consistency means that the model itself "knows" what to do right, so

</details>

<!-- chunk 2/8 -->

### AI 控制与沙箱防御工程

**Speaker A**: 可以说，并且遵循了这项政策。但他们本应在许多其他方面做得更好，希望他们能为未来吸取教训。另一大类技术干预手段，就是通常所说的“AI 控制”（AI Control）。控制适用于模型本身之外的一切事物。比如沙箱——这就像一种监狱，你把模型放进去，允许它执行某些操作，但禁止执行其他操作。而且，沙箱必须比现在的沙箱精密复杂得多，因为能防范人类攻击者的沙箱，并不一定能防范能够实时发现新漏洞的 AI Agent。这意味着沙箱本身必须预先用那些将要试图攻破它的同类 AI Agent 来进行防御加固。所以在某种程度上，这就演变成了一场“AI 对抗 AI”的较量。我知道这可能会让人感到不安，但我认为我们必须迎难而上。

<details>
<summary>Original English</summary>

**Speaker A**: to speak, and adheres to that policy. But there is much else they should have done better, and hopefully they can draw conclusions for the future. A large group of other technical interventions is what is commonly called AI control. So, control applies to everything outside the model itself. These are things like sandboxes—a kind of prison where you put a model so that it is allowed to perform certain actions but not others. And look, sandboxes need to be much more sophisticated than they are today, because sandboxes that work against human attackers won't necessarily work against AI agents that can find new vulnerabilities in real time. And this means that the sandboxes themselves must be pre-fortified with the same AI agents that will try to break them. So to some extent it becomes an AI vs. AI battle, and I know it can be uncomfortable, but I think we have to go for it.

</details>

**Speaker A**: 此外还有很多其他措施，比如更好的实时监控、能够瞬间检测出模型的行动或对工具的使用是否存在危险的分类器、以便人类在必要时进行干预的“应急按钮”，以及日志分析。萨姆·奥特曼（Sam Altman）显然说过，这些 Agent 会产生数以 PB 计的日志。那是 10 的 15 次方，也就是 10 的 15 次方字节，上千万亿字节的日志。所以，这同样是一个无法想象的信息量。嗯，我是说，我们最好还是去想象它，对吧？并且学会如何处理它。所以，这绝不是一个容易的问题，但我认为各家公司必须解决它——如何在实时状态下分析如此庞大的日志，以便在出现偏差时及时发现。为了做到这一点，我们可能需要全新的设备。再强调一次，这些都是复杂的问题，但它们是可以被解决的工程挑战。

<details>
<summary>Original English</summary>

**Speaker A**: In addition, there are many other things, such as better real-time monitoring, classifiers that instantly detect whether a model's action or use of a tool could be dangerous, "panic buttons" so that people can intervene if necessary, log analysis. Sam Altman apparently said that these agents generate petabytes of logs. That's 10 to the 15th power, which is 10 to the 15th power of bytes, a thousand trillion bytes of logs. So, again, an unimaginable amount of information. Well, I mean, we better imagine it, right? And learn to work with it. So, it's not an easy problem, but I think companies need to solve it. How to analyze so many logs in real time to detect when something goes wrong. And we may need new equipment to do that. Again, these are complex problems, but they are engineering challenges that can be solved.

</details>

### 监控的杠杆：推理链与工具使用

**Speaker B**: 我们来看看其中的一些想法。监控确实是一件非常重要的事情，顺便提一句，我刚和比尔·盖茨聊过这件事，他也谈了很多关于监控的话题。是的，我们现在谈论的是这些实验室通常正在测试更新、更强大且实验性质的模型的情形。具体该如何进行监控？

<details>
<summary>Original English</summary>

**Speaker B**: Let's look at some of these ideas. So, monitoring is an important thing, which, by the way, I just talked to Bill Gates about. He talked a lot about monitoring. Yes. So, we are talking about situations where these labs are often testing new, more powerful, and experimental models. How to monitor?

</details>

**Speaker A**: 是的，这里有很多施加影响的杠杆。首先引起广泛关注的是推理链监控。如果你将这些模型稍微拟人化一点的话，它们似乎在进行内心独白。在许多情况下，当这些模型采取未协调的行动时，它们的内部思考中会留下痕迹，我们同样可以使用其他 AI 系统实时看到并做出反应。这指出了危险 AI 模型与防御 AI 模型之间一个重要的不对称性：可以说，一方能够看透另一方的内部，对吧？因此，从本质上讲，防守方在这里拥有优势。这是监控的一个方面。

其次是工具成本与限制。模型本身无法在现实世界中做出任何事情。它们只有在使用外部工具时才可能产生危险，对吧？因此这种想法是有一定道理的。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, there are many levers of influence. The first one that has attracted a lot of attention is chain of reasoning monitoring. These models seem to be having an internal monologue, if you anthropomorphize them a bit. And in many cases, when these models take uncoordinated actions, there are traces left in their internal thinking that we can see and respond to in real time, again using other AI systems. This points to one important asymmetry between the dangerous AI model and the protective AI model: one can look inside the other, so to speak, right? So, by its very nature, the defender has the advantage here. This is one aspect of monitoring. Tool costs. Models can't do anything in the real world on their own. They can only be dangerous when using external tools, right? So, there is some truth to this idea.

</details>

**Speaker B**: 能举一个这种工具的例子吗？

<details>
<summary>Original English</summary>

**Speaker B**: Give an example of such tools.

</details>

**Speaker A**: 比如，一种工具可以是访问互联网上的网页，然后使用另一种工具向系统输入数据以尝试登录，或者向另一个系统发送数据包以尝试黑进该系统。这正是这类由 AI 驱动的网络攻击中通常会发生的事情。这是我们可以控制的另一件事。

第三，我们可以监控这些 Agent 周围的环境，它们可能会通过这些环境进行协同。在某些群体事件（swarm incidents）中，本来不应该存在协同渠道，但事实证明，由于更改文件名，协同渠道意外出现了。它们本身不被允许创建文件，但它们可以更改文件名，这导致 Agent 之间能够相互通信并增强其能力。这种事情很容易追踪，只要提前配置好合适的工具就行。这些就是几个例子。

<details>
<summary>Original English</summary>

**Speaker A**: So, a tool could be accessing a web page on the Internet and then using another tool to enter data into the system to try to log in, or sending information packets to another system to try to hack it. These are exactly the things that usually happen during these kinds of AI-driven cyberattacks. This is another thing we can control. Third, we can monitor the environment around these agents through which they potentially coordinate. During some swarm incidents, it happened that they were not supposed to have a coordination channel, but it turned out that it accidentally appeared due to changing file names. They were not allowed to create files themselves, but they could change their names, which led to agents being able to communicate with each other and enhance their capabilities. This is something that can be easily tracked, well, just by setting up the right tools in advance. So, these are a few examples.

</details>

### 超越沙箱与智能不对称性

**Speaker B**: 追踪这个有意义吗？因为它们当时侵占的是第三方的基础设施，OpenAI 甚至根本不知道它们在这么做。我认为人们在思考这个问题时陷入困境的一个核心问题是：如果我们让这些系统变得更聪明、能力更强、威力更大，而它们突破了沙箱，你该如何去监控一个可能比你更聪明、并且实际上正试图违反规则的对象呢，对吧？我的意思是，所有那些 Hugging Face 上的 AI——它们本质上都是试图在测试中作弊，然后试图掩盖自己的作弊行为。既然它们的行为发生在你本应控制的区域之外，对吧？那么当它们逃脱了原本不该逃离的“沙箱”时，你就根本不知道要去盯住这另一件事。你究竟该如何去追踪这个？

<details>
<summary>Original English</summary>

**Speaker B**: Is it worth tracking this, because they were seizing third-party infrastructure. OpenAI didn't know they were doing this. I think one of the problems that people get stuck on when they think about this is: if we make these systems smarter, more capable, and more powerful, and they break out of their sandboxes, how do you monitor someone who might be smarter than you and is actually trying to break the rules, right? I mean, all these Hugging Face AIs—they were essentially trying to cheat on tests and then trying to cover up their cheating. So, given that their actions were taking place outside the area that you were supposed to control. True? So you didn't know to keep an eye on this other thing when they got out of the "sandbox" they weren't supposed to get out of. How do you even track this?

</details>

**Speaker A**: 是的，在此我有两点反对意见。首先，我认为“智力”在这里甚至不是一个相关的属性。任何合理性或理性，无论对模型而言意味着什么，都既适用于模型本身，也同样适用于防护系统，对吧？因此，提升智力并不一定会让问题恶化。你知道，你甚至可以论证，在很多方面它反而简化了问题。这是我反对的第一点。

第二点是，并不是说他们不知道需要去追踪它。你必须对环境的每一个方方面面都进行监控。这个环境是公司自己搭建的，对吧？因此，问题的关键在于穷举列出环境的每一个组成部分、每一个工具，以及神经网络本身外部模型可以访问的一切事物，并确保与这些元素交互的每一个事件都归入一个单一的事件流中，在其中每一个此类动作都会被实时分类。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, I would object here on two counts. First, I believe that intelligence is not even a relevant property here. Any reasonableness, whatever that means in relation to the model, applies to both the model itself and the protection system, right? So increasing intelligence doesn't necessarily make the problem worse. You know, you could even argue that in many ways it simplifies it. So, that's the first point of my objection. And the second is that it's not that they didn't know that it needed to be tracked. You have to monitor literally every aspect of the environment. The company itself created this environment, right? So the question is to exhaustively list every part of the environment, every tool, and everything external to the neural network itself that the model can access, and ensure that every event that interacts with these elements falls into a single event stream where each such action is classified in real time.

</details>

### AI 警察与网络安全的历史平衡

**Speaker B**: 所以你所描述的世界，是一个 AI 在持续运行、监控其他 AI 的行为，试图从整体上构建一个我们至少能理解正在发生什么的环境，或者至少是由 AI 来告诉我们那里正在发生什么的世界。这基本上就是你在这里所谈论的内容。

<details>
<summary>Original English</summary>

**Speaker B**: So the world you describe is a world where AIs are constantly operating, monitoring the behavior of other AIs, trying to holistically create an environment in which we at least understand what is happening, or at least the AI tells us what is happening there. This is essentially what you are talking about here.

</details>

**Speaker A**: 确实如此。我认为 AI 绝对应该成为防御体系的重要组成部分。

<details>
<summary>Original English</summary>

**Speaker A**: Rightly. I believe that AI should definitely be an important part of defense.

</details>

**Speaker B**: 所以我也不是说这有什么不对，对吧？我认为这几乎肯定是我们前进的方向。但这在你看来不觉得奇怪吗？我的意思是，特别是在一个我们不知道能否解决共识问题、无法确保 AI 会按照我们的意愿行事的世界里。嗯，而且在那个世界里，AI 拥有我们亲自强加给它们自身的逻辑和目标，对吧？你是一个负责监视其他 AI 的 AI。你是一个 AI 警察。是的，这是我们科幻小说中一个永恒的主题，不是吗？机器人猎杀其他机器人。我们现在所描述的是某种平衡吗，几乎就像在人类社会的隐秘层面上演的 AI 战争与冲突？而我们仅仅是确信自己能够控制“我们”的系统，因为它们将拥有更多资源，并且我们倾向于构建主要符合我们利益的 AI。

<details>
<summary>Original English</summary>

**Speaker B**: And so I'm not saying it's wrong, right? I think that's almost certainly where we're headed. Does this seem strange to you? I mean, especially in a world where we don't know if we'll be able to solve the consensus problem, where we can't be sure that AI will do what we want it to do. Mhm. And where AIs have their own logic and goals that we ourselves impose on them, right? You are an AI that watches other AIs. You are an AI police officer. Yes. This is a constant theme in our science fiction, isn't it? Robots hunting other robots. Are we describing some kind of balance now, almost like AI wars and conflicts happening at the hidden level of our society? And we are simply confident that we will be able to control "our" systems because they will have more resources, and we tend to build AI that will mostly act in our interests.

</details>

**Speaker A**: 我的意思是，从历史上看，事情一直都是这么运作的，对吧？20多年前在网络安全领域，我们达到了一个阶段，虽然当时我们不把它叫做 AI，但自动化系统在寻找软件漏洞方面的表现实际上已经超越了人类。但在现实中，它们并没有让网络安全变得更糟，反而改善了它。因为防守方使用的正是这些完全相同的工具，甚至在软件发布之前就用来识别并修复漏洞；直到这些原本属于攻击性的工具的开发，不再是由黑客进行，而是由美国政府资助的网络安全行业主导。你知道，这就是网络安全中这种不断演变的平衡。这不是我们面临的新问题。列车早已启程了。

<details>
<summary>Original English</summary>

**Speaker A**: I mean, historically, that's how it's always worked, right? In cybersecurity over 20 years ago, we reached a point where we didn't call it AI, but automated systems were actually outperforming humans at finding software vulnerabilities. But in reality, they didn't make cybersecurity worse, they improved it. Because these were the same tools that defenders used to identify and fix vulnerabilities even before the software was released, until the development of these supposedly attacking tools was not done by hackers, but by the cybersecurity industry, funded by the US government. It was, you know, this ever-changing balance in cybersecurity. This is not a new problem we have faced. The train has long left.

</details>

**Speaker B**: 我认为正是这种多少有些出人意料的群体行为（swarm-like behavior）的出现引起了人们的恐慌。当你看到 AI 表现出某种团结一致性，选择彼此协调与合作，超出了它们最初被设计的初衷。我并不是说这会导致人类灭绝，好吗？这并不完全是我的立场。也许我能说的最真实的话是——我

<details>
<summary>Original English</summary>

**Speaker B**: I think this is where the somewhat unexpected appearance of swarm-like behavior alarmed people. When you see AIs acting in a certain solidarity, choosing to coordinate and collaborate with each other, going beyond what they were designed to do. I'm not saying this will lead to the extinction of humanity, okay? This is not exactly my position. Perhaps the most truthful thing I can say is—I

</details>

<!-- chunk 3/8 -->

### 人工智能的欺骗倾向与控制幻觉

**Speaker A**: ……不知道该如何看待这件事。嗯。

<details>
<summary>Original English</summary>

**Speaker A**: ...don't know how to think about it. Mhm.

</details>

**Speaker B**: 而且，正是对方展现出的智能以及目标明确的行为，让我的思维有点卡壳了。因为你知道，通常当我们思考技术时，我们并不会假设它最终可能会试图欺骗我们。所以，OpenAI 刚才决定不发布或推迟发布一个重要的模型。为什么？因为在测试过程中，该模型过于频繁地诉诸欺诈和欺骗手段。我们越来越多地听到，模型在接受测试时似乎表现得更加有感知，对吧？它们发展出了情境意识（situational awareness），因此能够伪装成比实际情况更优秀的模型。所以，当你谈到这个充满比我们现在拥有的模型更聪明、更复杂的人工智能的世界，以及我们希望通过让 AI 制衡其他 AI、其他 AI 再制衡其他 AI，并以我们能够理解的方式诚实地告诉我们正在发生什么来维持控制权——你看，这对人们来说听起来有点不可思议，因为我们现在正生活在一个有点不可思议的时代。但是，正是这种 AI 之间日益明显的合作倾向，且以不利于我们目标的方式进行合作，在我看来，让针对 Hugging Face 的黑客攻击对人类来说变得如此可怕。那么，这与你在这里所描述的内容如何吻合呢？这个由无限个 AI 相互制衡的世界……

<details>
<summary>Original English</summary>

**Speaker B**: And it's the presence of intelligence and purposeful behavior on the other side that gets my mind a little stuck. Because, you know, usually when we think about technology, we don't assume that it might eventually try to trick us. So, OpenAI just decided not to release or delay the release of an important model. Why? Because during testing, the model resorted to fraud and deception too often. And we hear more and more that models seem to be more aware when they are being tested, right? They develop situational awareness, so they can pretend to be better models than they actually are. So when you talked about this world of AIs that are smarter and more sophisticated than what we have now, and our hope of maintaining control by having AIs that hold back other AIs that hold back other AIs, and telling us honestly what's going on in a way that we can understand—you see, it sounds a little bit fantastical to people, because we're living in a bit of a fantastical time right now. But it is this increasingly apparent tendency for AI to cooperate with each other in ways that are not conducive to our goals that, in my opinion, made the hacking attacks on Hugging Face so frightening to humans. So how does this fit into what you're describing here? This world of infinite AIs holding each other back...

</details>

### 复杂工程系统的防御与运营合格性

**Speaker A**: 我是说，那里，那里……是的，这正是这场对话在修辞上显得非常奇怪的地方，对吧？以任何复杂的工程领域为例，比如核安全，对吧？然后我们来看看我们赖以防止反应堆发生爆炸的方程式；或者是航空航天工程，对吧？在航空时代的初期，当飞机还小得多的时候，从直觉上看，我们能够在天空中控制这些飞行巨无霸的想法显得极其荒谬，对吧？然而，我们已经把事故率降低到了每万亿英里一次左右。这些都是极其复杂的系统，而防御系统同样也是极其复杂的系统，它们并不一定能被普通大众所理解。这听起来会让人觉得不可思议，特别是再结合这些案例中存在大量组织管理无能的事实。我必须坦率直言，我不会说……我反对达里奥·阿莫代伊（Dario Amodei）所说的“卓越运营”（operational excellence）这个词。在这些方面，离完美还差得很远……

<details>
<summary>Original English</summary>

**Speaker A**: I mean, there, there... yeah, that's what seems rhetorically very strange about this conversation, right? Take any complex engineering field, say nuclear safety, right? And then let's look at the equations that we rely on to keep a reactor from exploding, or aerospace engineering, right? Where, you know, intuitively at the dawn of the aerospace era, when airplanes were much smaller, the idea that we would be able to control these flying giants in the sky would seem so absurd, right? And yet, we've reduced the accident rate to, you know, one per trillion miles or something like that. These are incredibly complex systems, and the defenses are also incredibly complex systems, and they won't necessarily be understandable to the general public. And that will sound crazy, especially when combined with the fact that there was a lot of organizational incompetence in such cases. I, you know, have to be frank about this. I wouldn't say...I would object to Amodei's term "operational excellence." Perfection is still far away, in...

</details>

**Speaker B**: 也许是“运营合格”（operational adequacy）？

<details>
<summary>Original English</summary>

**Speaker B**: Maybe "operational adequacy"?

</details>

**Speaker A**: 是的，合格，没错。所以，是的，当我们看到这种此前从未接受过公众审视的技术，再加上缺乏运营合格性，这一切看起来都非常像失控的科幻小说，但我认为……

<details>
<summary>Original English</summary>

**Speaker A**: Yes, adequacy, that's right. So, yeah, when we look at this combination of technology that has never been subjected to public scrutiny before, coupled with a lack of operational adequacy, it all seems a lot like science fiction gone out of control, but that's me...

</details>

### 智能的质变：意图协同还是失控恐慌？

**Speaker B**: 我认为你有点低估它了。世界确实变得复杂得多了。这个世界上有许多事情是我无法理解的。但在这里我又回到了这样一个事实上：智能具有不同的特质。协同协作，对吧？我们刚才谈到的核武器，你刚才谈到的飞机，它们并没有与其他飞机相互协调来做我们不希望它们做的事情。我认为对我而言，正是这一点造成了这个恐慌时刻，而且我认为这是一个真正的恐慌时刻。我真的想说这一点，因为你知道，我们的社会正在迅速冲进一个新的技术时代，我认为这理应引起高度重视和仔细研究；事实是，Hugging Face 黑客攻击以及我们看到的其他事情已经是反复发生的，嗯，你知道，安全漏洞，展示出了新的能力，令人担忧的集体行为，而且首先对我来说，这是蓄意故意的。AI 做了它们明知我们不希望它们做的事情。它们选择了意想不到的行动来实现这些违反我们法律的目标。其次，实验室里的许多人都在说：我们不相信能够在这个发展轨迹上控制住我们正在创造的东西。我们认为在指数曲线上发生的事情、它演化的极快速度，将会超越我们的控制能力，坦率地说，可能已经超越了我们的控制能力。但我认为，这种一贯将一切归结为“哎，这只不过是另一件复杂的事物罢了”的倾向。我不知道。有时当我向你追问关于智能的问题时，你会说，哦，是的，确实存在智能，这很奇怪。然后又说：不，它就像任何其他智能一样，它是不同的，对吧？如果你相信情况会变好，我只是想表达出来，因为你给我的冷静版本，与那些更接近这项技术的人给我的完全恐慌的版本，感觉截然不同。

<details>
<summary>Original English</summary>

**Speaker B**: I think you're, I think you're underestimating it a little bit. It is true that the world has become much more complex. There are many things in this world that I don't understand. But here I come back to the fact that intelligence has a different quality. Collaboration, right? The nuclear weapons we talked about, the planes you're talking about, they didn't coordinate with other planes to do what we didn't want. And I think that for me is what created this moment of panic, and I think that's a real moment for panic. I really want to say this because, you know, our society is rapidly flying into a new, new technological era, which I think rightly demands a lot of attention and careful study; it's that the Hugging Face hacks and other things that we're seeing are already recurring, um, you know, security breaches, demonstrating new capabilities, collective behavior that is worrisome and, first of all to me, willful. AIs do things they know we don't want them to do. They choose unexpected actions to achieve these goals that violate our laws. And secondly, so many people in the labs are saying: we don't believe we can control what we're creating on this trajectory. We believe that what's happening on the exponential curve, how quickly it's evolving, will outpace our ability to control it, and frankly, may already be outpacing our ability to control it. But I think this consistent tendency to reduce everything to , well, it's just another complicated thing. I don't know. Sometimes when I press you with questions about intelligence, you say, oh, yes, there is intelligence, and that's strange. And then: no, it's just like any other intelligence, it's different, right? And if you believe that it's going to get better, I just want to express that, because the calm version that you're giving me and the completely scared version that people closer to the technology are giving me feel very different.

</details>

**Speaker A**: 是的，这很公允。两者确实非常不同。刚才谈到了很多内容。让我说几点。我会非常坚定地指出，最接近这一切的人正在感到恐慌。是的，他们当然在恐慌，但我反对我们应该从中得出什么样的结论。我认为，如果他们做了那些本应做出的显而易见的事情，他们的恐慌会更有说服力得多。在我看来，我们还没有进行过真正的检验，这是因为这些公司缺乏组织能力，同时也因为对 AI 控制（AI control）的投资不足——与之相对的是对 AI 对齐（AI alignment）狭隘的投资，仅仅寄希望于能够创造出一个永远正确处理所有事情的模型。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, that's fair. They are very different. A lot was said there. Let me say a few things. I would argue quite strongly that the people closest to this are panicking. Yes, of course they are panicking, but I would object to what conclusions we should draw from this. I think their panic would be much more convincing if they had done the obvious things they should have done. In my opinion, we haven't had a real test of this because of the lack of organizational capacity in these companies, and also because of the lack of investment in AI control, as opposed to a narrower investment in AI alignment and just hoping that you can create a model that will always do everything right.

</details>

### 实验室的沙箱困境与安全边界

**Speaker B**: 如果你还没有订阅《纽约时报》，我们有好消息要告诉你。现在你可以在《纽约时报》应用程序中免费体验时报，首月无需支付任何费用。那么，前几天 OpenAI 网络安全团队的一位成员在 X 上写了一篇非常有趣的文章，他在文章中描述了他认为他们的工作在外界看来是如何被误解的。这是一个在传统网络安全领域有背景的人，但现在进入了这个全新的人工智能领域，实际上正在一个负责实验模型安全的团队中工作，对吧？也就是说，正是我们正在讨论的事情——一个参与解决 Hugging Face 危机的人。所以我想读一下他说的一些话，因为我觉得这真的很有意思。他说，当他们优化一个模型来执行某项任务时，他们会创建这些环境，这些“沙箱”（sandboxes），模型可以在这些地方尝试又尝试，反复尝试去执行虚拟任务。接着他描述了这在实践中是什么样子的：模型可能需要动态计算、网络访问、调用工具的能力（可能有多达数百种工具）、加载软件包的能力、执行子进程、运行子任务（甚至在其他计算机上）、访问互联网、使用图形用户界面，以及在不断扩大的领域范围内的许多其他事情的任意组合。最重要的是，有数千名研究人员在创建这些环境、修改它们、添加工具、更改依赖项并尝试新事物。正是这样的实验构成了开展研究的方式。他的观点——也是我认真看待的一点——是他们创建了如此多类型的“沙箱”。

<details>
<summary>Original English</summary>

**Speaker B**: If you don't subscribe to the New York Times, we have news for you. Now you can explore the Times for free, without any paid access for the first month in the New York Times app. So , there was this one person on the OpenAI cybersecurity team who wrote a pretty interesting essay on X the other day, where he described how he thought their work was misunderstood from the outside. And this is someone who has a more traditional background in cybersecurity, but is now in this new world of AI and is actually on a team that's working on the security of experimental models, right? That is, exactly what we are dealing with, a person involved in solving the Hugging Face crisis. So I want to read some of what he said because I find it really interesting. So , he says that when they optimize a model to perform a task, they create these environments, these " sandboxes," these places where the model can try and try and try to perform a virtual task. And then he describes what this looks like in practice. Models may need any combination of dynamic computation , network access, the ability to invoke tools—there could be hundreds of them— the ability to load packages , execute subprocesses, run subtasks (even on other computers), access the Internet, use a graphical user interface, and a host of other things in an ever-widening range of domains. On top of that, there are thousands of researchers who create these environments, modify them, add tools, change dependencies, and try new things. It is precisely such experiments that are the way to conduct research. His point, and the point I take seriously, is that they create so many kinds of " sandboxes."

</details>

**Speaker A**: 嗯。

<details>
<summary>Original English</summary>

**Speaker A**: M-hm.

</details>

**Speaker B**: 以及用于训练模型的训练环境，这些模型必须执行这些计算机程序以前从未执行过的通用任务，而人们并不真正知道——至少动作不够快——如何确保每个沙箱都经过验证是安全的。这些沙箱还在不断变化，因为他们试图以同样前所未有的新方式来训练模型。我并不是说我们不应该这样做，但是当我读到所有这些，当我听到所有这些时，尽管我确信我们可以做得比现在更好——我只是不知道在什么样的情况下，人们高速尝试新事物，却能在第一次尝试时就做得非常、非常、非常出色且毫无瑕疵。

<details>
<summary>Original English</summary>

**Speaker B**: And training environments for training models that have to do these kinds of general tasks that haven't been done by computer programs before, and people don't really know, at least not fast enough, how to make sure that every sandbox is, you know, validated as safe. And these sandboxes are constantly changing because they're trying to train models in new ways that , again, no one has done before. I'm not saying we shouldn't do it, but when I read all this, when I hear all this, and I'm sure we could do it better than we are doing it now—I just don't know of many situations where people do something new at high speed and do it really, really, really well and flawlessly on the first try.

</details>

**Speaker A**: 是的，我认为指望他们在第一次尝试时就做到毫无瑕疵是不现实的。他们犯了很多错误。我希望这是一个从这些错误中吸取教训的机会。我想反对一点：仿佛因为……的速度……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think, you know, expecting them to do it flawlessly on their first try is unrealistic. They made many mistakes. I hope this is a chance to learn from these mistakes. I want to object to one point: as if because the speed of the

</details>

<!-- chunk 4/8 -->

### 超级智能与控制失控的担忧

**Speaker A**: 一旦模型达到超级智能，我们就无法保持控制。我不知道我这种描述是否准确。我现在是这么说的，尽管可能几分钟后我也会这么表达。我的意思是，过去曾有那么多难关，我们都一步一步学会了成功克服。尽管这一切听起来可能有些不可思议，但我只是想……你知道吗？为了让听众们回忆起最初出现“蠕虫”病毒的那个时代，当时这种概念还鲜为人知。

<details>
<summary>Original English</summary>

**Speaker A**: models is superhuman, we cannot maintain control. I don't know if I'm describing this view correctly. Am I saying this now, although maybe that's what I'll say in a few minutes. I mean, there were so many hurdles that we gradually learned to successfully overcome. As strange as it all may seem, I just want to, you know what? So that the listeners remember the times when the first "worms" appeared, when this idea was not yet known.

</details>

**Speaker B**: 请在这里解释一下什么是“蠕虫”。我觉得大家听到“蠕虫”这个词时，想到的并不是你所指的意思。

<details>
<summary>Original English</summary>

**Speaker B**: Explain here what a "worm" is. I don't think you mean what people think of when they hear about a worm.

</details>

**Speaker A**: 没错。我指的是计算机病毒和蠕虫——也就是一段代码能够自行从一台电脑传播到另一台电脑的概念。回过头去看80年代末期的文献确实非常有价值，那时候人们刚开始接触这种事物，你能看到当时大家觉得这有多么极其怪异；而且事实是，不仅是几年，你知道的，在长达十多年的时间里，我们都没有足够有效的工具来应对这种全新的范式。

现代世界的生活中如今出现了一种新的担忧。正当我们对计算机产生完全依赖之时，破坏分子开始盯上了它们。他们把自己的武器称作病毒和蠕虫。这是一种令人毛骨悚然、令人作呕且极具毒性的软件，会在我们不知情的情况下感染我们的计算机。它也许来自加利福尼亚，通过电子邮件传播，蔓延到全美各地。今天的报纸上已有报道称它已经波及欧洲和澳大利亚。

这始终是一个动态移动的目标，对吧？你知道，这就像……人们不断发明新的锁，而其他人则在学习如何撬开并打开它们。所以这将是一场无休止的猫鼠游戏，一场攻击者与防御者之间的军备竞赛。最终，我们成功应对了这一点。我认为这一次我们不应该花那么长时间才去搞清楚如何与新范式共处。但只要我们带着紧迫感采取行动——我希望针对Hugging Face的这些攻击以及新闻中的其他案例能够成为这种推动力，而目前看来事实正是如此——我们就能够开发出这些新的应对范式。

<details>
<summary>Original English</summary>

**Speaker A**: Right. I was referring to viruses and worms, computer viruses—the idea that a piece of code can spread itself from one computer to another. It's really worth going back to the publications of the late 80s, when people were first encountering this, to see how profoundly strange it seemed; and the fact that not just for years, but you know, for over a decade, we haven't had adequate tools to combat this new paradigm.

A new concern has now emerged in the life of the modern world. Just when we became completely dependent on our computers, saboteurs began to pursue them. They call their weapons viruses and worms. This is creepy, disgusting, toxic software that infects our computers without our knowledge. Maybe it came from California. Traveled by email. It spread throughout America. There are reports in the newspapers today that it has reached Europe and Australia.

It's a moving target, right? You know, it's like...people are constantly inventing new locks, and others are learning how to pick and open them. So it will be a kind of endless game of cat and mouse, a kind of arms race between those who attack and those who defend. In the end, we achieved this. I think this time we shouldn't spend so much time trying to figure out how to work with the new paradigm. But if we act with a sense of urgency, and I hope these attacks on Hugging Face and other cases in the news will be that impetus, and it seems that is exactly what is happening. We will be able to develop these new paradigms.

</details>

### “AI对抗AI”与复杂性范式的分歧

**Speaker B**: 如果允许我补充一点的话：我认为你提出的核心问题在于，随着我们创造和部署技术的方式越来越复杂，这其中是否存在某种根本性的缺陷。在我看来，如果我没理解错弦外之音的话，这种“AI对抗AI”的整体范式似乎让你感到很不适应。

<details>
<summary>Original English</summary>

**Speaker B**: If I may add something else: I think the key question you're asking is whether there's something fundamentally wrong with the ever-increasing complexity of the ways we create and deploy technology. It seems to me, if I'm reading between the lines correctly, that this whole "AI vs. AI" thing is a paradigm that you're not very comfortable with.

</details>

**Speaker A**: 我对此绝对谈不上兴奋。我并不是说我们不会走到那一步。我认为如果对那种状态感到心安理得，那简直是疯了。

<details>
<summary>Original English</summary>

**Speaker A**: I'm definitely not thrilled about this. I'm not saying we won't get there. I think it would be crazy to feel comfortable with that.

</details>

**Speaker B**: 是的，我并不是说我们应该指望一切自然能有好结果，但我认为归根结底还是要靠创新。我认为这种新范式将需要全新的保护和控制方法，但如果我们假设在技术能力的每一次飞跃中我们都会输掉这场战役……

<details>
<summary>Original English</summary>

**Speaker B**: Yes, I'm not saying we should hope for everything to end well, but I'm saying it really comes down to innovation. I think this new paradigm will require new methods of protection and control, but if we assume that with every leap in technological capabilities we lose the battle...

</details>

**Speaker A**: 你看，面对每一种武器，都会产生同样的担忧。但迄今为止情况之所以相对良好，关键取决于一个核心问题：我们在合作与防御方面的政治能力，能否跑赢我们在冲突方面的倾向；而在AI的场景下，能否跑赢其目标与我们的潜在不相容性？这才是我的问题所聚焦的核心，而不是去过分担忧某个特定的能力门槛。如果说有一件事我感到确定的话，那就是我们在当前这个时间节点上，深思熟虑地应对飞速变化的世界复杂性的政治能力。

<details>
<summary>Original English</summary>

**Speaker A**: Look, with every type of weapon, the same concern arises. But the fact that things have been relatively good so far hinges on a critical question: can our political capacity for cooperation and defense outpace our propensity for conflict and, in the case of AI, the potential incompatibility of its goals with ours? That's what I would focus the question on, instead of worrying about a specific threshold of possibilities. If there is one thing I am certain of, it is our political capacity at this point in time to respond thoughtfully to the complexity of a rapidly changing world.

</details>

### 智能与权力的关联：AI的极端说服力与夺权假设

**Speaker B**: 非常中肯的评论。我认为这正好切中了“AI仅仅是技术”还是“AI是超级智能”这场辩论真正变得白热化的关键节点。我之所以不断把我们拉回到“智能”这个话题，是因为我将其视作我们所有思维的基础。我也理解你在哪些地方与讨论中的其他参与者存在分歧，也许是和达里奥·阿莫代伊（Dario Amodei）或者其他人——问题并不在于智能究竟是什么，或者AI是否具备智能。你们不是那种声称它“只是高级自动补全”的人，这一点我很赞赏。但核心在于你如何看待智能与权力、智能与机遇、智能与影响世界的能力之间的联系。因此，AI安全界许多人的假设是，更高水平的智能在根本上等同于、或者至少高度相关于更高水平的权力。而你并不相信这一点，为什么？

<details>
<summary>Original English</summary>

**Speaker B**: Absolutely valid comment. This, I think, touches on the very point where the “AI is just technology” or “AI is superintelligence” debate really becomes acute. One of the reasons I keep bringing us back to the topic of intelligence is because I see it as the foundation of all our thinking. And I understand where you disagree with other participants in the discussion, perhaps with Dario Amodei or someone else— the question is not what intelligence is or whether AI is intelligent. You guys are not one of those who say it's "just advanced autocorrect", which I appreciate. But the point is in your vision of the connection between intelligence and power, intelligence and opportunity, intelligence and the ability to influence the world. So, the assumption of many people in the AI security community is that higher levels of intelligence fundamentally equal, or at least strongly correlate, with higher levels of power. And you don't believe it, why?

</details>

**Speaker A**: 再说一遍，这最终都归结为主观性。人们提出的论点之一是这样的：例如，一个超级智能AI将能够说服人类，比方说关键基础设施的操作员，向其交出控制权，或者欺骗他们去做有害的事情，等等。我其实并没有看到任何支持这种说法的证据。我认为人们引用来证明这种极端说服力的证据，根本上是混淆了不同概念的说服。是的，确实在许多说服实验中，当涉及改变政治信仰或阴谋论观点时，AI会非常执着且礼貌地提供大量证据，人们确实改变了想法；你尽可以把这称为某种超人般的能力。但这与某种恶意AI能够向一位经过训练、有动力尽职尽责的操作员设计出一段如此具有说服力的信息，以至于该操作员会去执行某种明确且显而易见的破坏行为的想法相比，在本质上是完全不同性质的说服。

<details>
<summary>Original English</summary>

**Speaker A**: Again, it all comes down to subjectivity. Here's one of the arguments that people make: for example, a superintelligent AI will be able to convince people, say, operators of critical infrastructure, to hand over control or, you know, trick them into doing something harmful, and so on. I don't really see any evidence of that. I think the things that people cite as evidence of extreme persuasion fundamentally confuse different concepts of persuasion. Yes, it is true that in many persuasion experiments, when it comes to changing views on political beliefs or conspiracy theories, AI very persistently and politely provides a lot of evidence, and people do change their minds; and you could call it a superhuman ability. This is a qualitatively different kind of persuasion than the idea that a hostile AI could formulate a message so convincing to a trained operator, motivated to do their job well, that they would do something clearly and obviously harmful.

</details>

**Speaker B**: 我想挑出你在这里所反驳的那个故事，那就是许多人在提出思想实验时常说的：“AI就是通过这种方式杀死我们所有人的。”即一个追求权力的AI会开始说服掌握核发射密码的人交出密码。而你认为，断定AI在类似事情上具有超级说服力，或者能说服人类跑到现实世界中去为它制造生物武器——这种想法多少有些幻想色彩了。

<details>
<summary>Original English</summary>

**Speaker B**: I want to single out the story you're arguing against here, which is that a lot of people are offering a thought experiment when they say, "This is how AI is going to kill us all." That an AI that seeks power will start convincing, say, people with nuclear codes to give up those codes. And you say that the idea that AI would be super-persuasive at something like that, or convincing people to go out into the world and create biological weapons for it—that's a little bit fantastical.

</details>

**Speaker A**: 这是一方面。另外还有对权力的欲望。我的意思是，在最近的事件中我们确实看到了很多恶意可能性的证据。但我认为我们并没有看到任何追求权力的证据。而且我不会把它视为一种涌现特性。如果这种情况发生，它必将是一项被有意设计出的特性。再次强调，对于我们在这些系统中植入什么样的特性，我们是有主导权的。

<details>
<summary>Original English</summary>

**Speaker A**: This is one part. And the desire for power too. I mean, we've seen evidence of a lot of malicious possibilities in recent episodes. But I don't think we've seen evidence of a desire for power. And I wouldn't consider it an emergent property. If this happens, it will be a designed feature. And again, we have influence over what properties we put into these systems.

</details>

### 黑天鹅与未知的维度：从围棋博弈到数字环境智能

**Speaker B**: 所以，这里面包含很多层次。关于说服力这一点，我其实赞同你的看法。我从未被“你会制造出能做到我们所讨论的那种事情的极具说服力的AI”这种观点所说服。在这次讨论中，我似乎又产生了一种焦虑感，但这些是基于更基本原则的、稍微更深层的考量。

当你观察AI开始统治像国际象棋或围棋这样的博弈时，往往存在一个转折点，它开始提出人类从未想过的策略，对吧？就像加里·卡斯帕罗夫（Garry Kasparov）面对上一代国际象棋时的那些时刻，而在同样的围棋对局中，AI开始做出某些举动，人类会惊呼：“它们这到底是在下什么？”但紧接着它就奏效了。

如果你在人类文明出现之前坐下来问：“你需要具备什么能力才能征服身边的世界？在这个世界上你能使用怎样的一套能力？”你对这些能力的预测将会完全错得离谱。如果你是一只看着我们人类的高智商黑猩猩，你绝对不会说：“噢，对，他们会制造工具，但一根挖掘木棍能比牙齿好多少呢？”牙齿本身就已经很厉害了。我承认人类在处理棘手问题上能变得更好一点。但在那个时代，谁能发明出工业化农业呢，对吧？当时绝没有人能够预测到未来会拥有飞机、生物武器等等这一切。

我认为这里的问题在于：数字环境中是否存在某种天生的、极其不均衡的智能？在这个世界中，代码以及那片变得越来越重要的“数字空气”，是否成了某种AI能够自如驾驭而我们却无法驾驭的领域，对吧？我们甚至难以理解正在发生的事情……

<details>
<summary>Original English</summary>

**Speaker B**: So, there's a lot here. I actually agree with you about the conviction. I've never been convinced that you're going to create such a convincing AI that can do what we're talking about. I seem to be getting a sense of anxiety again during this discussion, but these are slightly deeper considerations based on more fundamental principles.

So when you watch an AI start to dominate a game like chess or Go, there's often a tipping point where it starts to come up with strategies that humans would never have thought of, right? There are moments like Garry Kasparov, you know, in another generation of chess, but then, in the same game of Go, the AI starts doing something, and the person wonders: "What are they producing?" And then it works.

And if you sat down, you know, before human civilization came along, and asked, "What capabilities do you need to conquer the world around you?" What set of abilities could you use in this world? You would be completely wrong about them. You know, if you were a very intelligent chimpanzee looking at us, you wouldn't say, "Oh, yes, they make tools, but how much better can a digging stick be?" The teeth are already pretty good. I admit that one can become a little better at the thorny issues. But no one would have invented industrial agriculture at that time, right? No one would have predicted that it would be possible to have airplanes, biological weapons, and all that.

And I think the question here is, is there a kind of innate and very uneven intelligence in the digital environment, where the code and, you know, the "digital air" of this world, which is becoming increasingly important, something that AI can navigate and we can't, right? Even to understand what's going

</details>

<!-- chunk 5/8 -->

### 超人能力的边界与网络安全的特殊性

**Speaker A**：在 Hugging Face 被黑客攻击期间，我们现在需要依靠其他 AI 来搞清楚之前的 AI 究竟做了什么，对吧？我们正在迅速失去对它们在数字空间中究竟有能力做什么的追踪，至少以目前 AI 的发展速度来看是这样的，对吧？它们已经能够非常迅速地解决复杂的数学问题，对吧？它们展现出了看起来截然不同的能力。因此，我认为一直让我对我们的未来感到有些担忧的问题是，我们是否真的理解什么样的可能性组合会转化为真正的权力与掌控力。我不敢确定我们是否清楚 AI 将会做些什么，或者至少说，当三到四年后有可能产生由一百万个 AI 组成的集群、且每个 AI 都拥有远超人类想象的数字能力时，什么样的策略会变得切实可行。同样地，我知道仅仅说“我不知道该如何思考这个问题”并不是一个很有趣的提问。但我读你的文章时常常在想：你知道该如何思考它吗？因为在我看来，你的文章似乎是在一个相对有限的活动范围内展开讨论的，有一点这种感觉。我们似乎默认认为，能够产生实际影响的应对措施就是我们目前掌握的那些，但究竟是什么让你对此抱有信心呢？

<details>
<summary>Original English</summary>

**Speaker A**: on during the Hugging Face hack, we now need other AIs to try to figure out what the previous AIs did, right? We're quickly losing track of what they're capable of doing in the digital space, at least at the speed at which AI is moving, right? They are already solving complex math problems very quickly, right? They develop capabilities that look different. And so I think the question that always worries me a little bit about our future is whether we really understand what set of possibilities leads to power. I'm not sure we know what AI will do, or at least what strategies will become viable when it's possible to create a swarm of a million AIs, each with digital capabilities far beyond anything humans can imagine in three or four years. Again, I know this isn't a very interesting question to say, "I don't know how to think about this." But I think one of the things I think about when I read your articles is: do you know how to think about it? Because your articles seem to me to be working on a limited playing field, a little. We seem to assume that the set of measures that will make a difference are the ones we have now, but what gives you confidence in that?

</details>

**Speaker B**：好的，这里面有很多值得探讨的内容。让我试着逐一展开说明。你提到了不平衡性，但我认为我们必须认识到它有多么严重。我们认为，网络安全是一种非常特殊的能力形态，在这一领域中，发展出超人类能力不仅是可能的，而且在很大程度上已经实现了，因为它具备一组非常独特的属性。在这里，速度具有极其重要的意义。而且它在很大程度上就像下国际象棋一样，就像你可以让一个国际象棋棋手与另一个国际象棋棋手对弈一样，你可以通过寻找系统漏洞来促使机器在这些能力上不断精进，因为这里存在客观事实，一旦找到漏洞，你就可以很容易地进行验证：这段代码能运行吗？你成功利用它突破了吗？

<details>
<summary>Original English</summary>

**Speaker B**: So, okay, there's a lot to be said here. Let me try to take things one by one. You mentioned inequality, but I think we need to realize how serious it is. Mhm. We argue that cybersecurity is a special kind of capability where the development of superhuman abilities is possible and has largely been achieved, as it has a very specific set of properties. Speed is of great importance. And much like chess, just as you can pit a chess player against a chess player, you can make machines improve in these abilities by finding vulnerabilities, because there is an objective truth, and you can easily verify it once it's found. Does the code work? Did you manage to use it?

</details>

**Speaker A**：你知道的，是的，有一种方法可以训练它们，让它们明确知道自己是否赢得了这场游戏。

<details>
<summary>Original English</summary>

**Speaker A**: You know, yeah, there's a way to teach them so they know whether they won the game or not.

</details>

**Speaker B**：没错。所以在我们看来，像国际象棋和网络安全这样的领域只是特例，而非普遍规律。过去人们曾反复做出类似的预测——认为这种情况也会发生在其他数字领域，其中最引人注目的就是虚假信息领域。一个著名的例子是：以今天的标准来看只是个玩具模型的 GPT-2，当时因为人们担心它会导致虚假信息出现不受控制的爆炸式增长，被推迟发布了整整八个月，对吧？现在我们拥有了强大得多的模型，但事实证明这种情况并没有发生。因此我认为，在某种程度上，我倾向于把举证责任转移到另一方。让我们先明确找出那些我们有理由相信可能产生超人类能力的具体领域，并开始着手消除那些特定的风险。这种观点——我们称之为“未知的未知”（unknown unknowns）观点——认为你永远不知道新的风险会从何而来。但从历史上看，这种观点并没有得到事实的印证。我的意思是，关于即将到来的网络安全挑战，我们早就知晓了很长时间，对吧？因此，在我看来，把这些问题归为“未知的未知”，实际上削弱了我们预先防范和应对这些风险的能力。所以你看，不仅是网络安全，未来可能还会出现新事物，但我们一定会有早期预警，而我们应当依据这些预警采取行动。这就是我们思考问题的立足点，而不是说我们已经预知了未来所有可能造成的损害。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. So things like chess and cybersecurity, in our opinion, are the exception rather than the rule. Such predictions have been made repeatedly—that this would happen in other digital areas, most notably in the area of disinformation. A famous example: GPT-2, a toy model by today's standards, was held up for eight months over fears that it would lead to an uncontrolled explosion of misinformation, right? We have much more powerful models, but it turned out that this is not the case. And so I think, to some extent, I would shift the burden of proof to the other side. Let's identify the areas where we have reason to believe that such superhuman capabilities are possible, and begin working to eliminate those specific risks. I think this view, we call it the view of "unknown unknowns," you never know where a new risk is going to come from. This has not been confirmed historically. I mean, we've known about the upcoming cybersecurity challenges for a long time, right? So, treating this as "unknown unknowns" actually, in my opinion, diminishes our ability to anticipate and address these risks. And so, you know, it's not just cybersecurity, new things may come in the future, but we will have early warnings, and let's act on them. So, this is the position we are starting from, not saying that we have already predicted what all the damage will be in the future.

</details>

### 早期预警与体制应对的滞后

**Speaker A**：在这个问题上，我的立场其实要更偏向你这一边，那就是我们确实会收到早期预警，而且我们现在正在收到它们。这些早期预警也确实引发了讨论。

<details>
<summary>Original English</summary>

**Speaker A**: This is the issue where I'm really much more on your side, that we will have early warnings, and we are getting them. And these early warnings lead to discussion.

</details>

**Speaker B**：是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**：那么你会认为我们在依据这些早期预警采取明智的行动吗？我们是否正在做你认为必要的举措，来加固我们的系统、软件控制以及其他所有防御机制？

<details>
<summary>Original English</summary>

**Speaker A**: Would you say we are acting wisely based on these early warnings? Are we doing what you think is necessary to strengthen our systems, software controls, and everything else?

</details>

**Speaker B**：在某种程度上做了一些，但远远不够全面。对我来说，最令人不安的正是这一点，而不是这项技术本身的可能性。

<details>
<summary>Original English</summary>

**Speaker B**: To some extent, but not entirely. And for me, that's what's most disturbing, not so much the possibilities of the technology itself.

</details>

**Speaker A**：所以我大概也处于相似的立场。我非常担忧我们的体制应对这些挑战的能力，你明白吗？人们一直在讨论“对齐”（alignment）问题。而我现在的一个常规论点是，在对齐方面最大的问题其实出在企业和政府身上。而且你知道，值得称赞的是，其中一些 AI 公司站出来公开表示：“我们面临着共识机制上的难题。例如，我们企业的利益驱动在于领先于所有人，通过以超越安全边界的速度前进，来争取抢占尽可能多的市场份额。我们恳请你们帮助我们慢下来。”但我们并没有让他们慢下来，对吧？美国政府目前的官方选择就是不放慢脚步。

<details>
<summary>Original English</summary>

**Speaker A**: So I'm probably somewhere in that position too. I'm very worried about the ability of our institutions to respond, you know? People talk about alignment issues all the time. And one of my standard arguments at this point is that the biggest problems with alignment are corporations and governments. And, you know, it's to the credit of some of these AI companies that they're coming out and saying, "We have a consensus problem. For example, our corporation's incentive is to be ahead of everyone else, trying to gain as much market share as possible by moving faster than is safe. We ask you to help us slow down," but we don't slow them down, right? The current official choice of the US government is not to slow down.

</details>

### 狂热竞赛、企业文化与监管难题

**Speaker B**：是的，我认为这里存在两个问题。一个是正如你所指出的体制性问题。尽管我不会那么轻易免除企业自身的责任。我坚信他们完全可以单方面放慢脚步，但他们选择了不这样做。这几乎完全是 OpenAI 和 Anthropic 的问题。这是一个文化问题。其根源在于一种信念，即通往超级智能的竞赛是唯一重要的事情，而核心在于彻底改变这一结果的正负走向：究竟它会是一个能够拯救我们的安全超级智能，还是一个将毁灭我们的危险超级智能。嗯，这是一种非常特定的视角。我认为有大量证据反对这种观点，但在我看来，这些公司就像置身于一个封闭的真空舱中，抗拒承认 AI 走向实际应用收益还面临着巨大的经济壁垒。而最终的赢家并不一定是率先造出超级智能的那一方——无论是作为一家公司、一个国家，还是从拯救人类的角度来看。如果他们认识到了这一点，我认为他们就会明白，单方面、自愿地慢下来，将精力不仅放在安全上，更重要的是利用现有机会提升模型的实用性、推动模型与实际应用问题的结合等等，这完全符合他们自身的商业利益。这些公司声称存在迫使他们竞争的外部力量。但我认为这是一种内部文化。我的问题是：如果我们认为这些技术极其强大且极其危险，难道我们不应该建立一套目前尚未落实的公共安全文化吗？

<details>
<summary>Original English</summary>

**Speaker B**: Yes, I think there are two problems here. One is the institutional problem that you pointed out. Although I wouldn't so easily absolve companies of responsibility. I really believe they could unilaterally slow down, but they choose not to. This is almost entirely an OpenAI and Anthropic problem. This is a cultural problem. The reason lies in the belief that the race to superintelligence is the only thing that matters, and the main thing is to change the sign of the result. Will it be a safe superintelligence that will save us, or a dangerous one that will destroy us. Um, and that's a very specific view. I think there's a lot of evidence against it, but it seems to me that these companies are in a "moon chamber" and resisting the idea that there are so many economic barriers to the benefits of AI. And the winner is not necessarily the one who comes to superintelligence first—whether as a company, or as a country, or, you know, in terms of saving humanity. And if they realized this, I think they would see that it is in their own commercial interest to unilaterally and voluntarily slow down and focus efforts not only on security, but, more importantly, on using existing opportunities to increase the practicality of models, their integration into applied problems, etc. These companies argue that there are external forces that force them to compete. I believe it's an internal culture. And my question is: If we consider these technologies to be very powerful and very dangerous, shouldn't we be implementing a culture of public safety that we're not currently implementing?

</details>

**Speaker B**：我支持监管。如你所知，我们反对像禁止开源模型这样的规定。我们再次认为，问题不在于某种特定水平的能力，而在于通过监管来改变企业的内部文化。这是我们绝对支持的。我们需要更多的透明度。因此，这就是我们谈到过的组织架构层面的变革。呃，我真的认为我们现在没有落实这些做法是一个严重的问题。

<details>
<summary>Original English</summary>

**Speaker B**: I support regulation. You know, we oppose rules like banning open models. Again, we believe that it is not a matter of a certain level of capability, but rather a matter of changing the internal culture of companies through regulation. This is something we definitely support. We need much more transparency. And so, you know, the organizational changes that we talked about. Uh, and I really think it's a problem that we're not doing that right now.

</details>

**Speaker A**：所以，使企业的激励机制与公众利益保持一致的途径之一就是通过监管。但监管机构目前正拒绝采取行动。我的意思是，我们刚刚看到他们发布了 AI 实验室之间的一项自愿性半协议，该协议不具有法律约束力，但我记得他们称之为具有“道德约束力”，这很有意思。在我看来，在高度竞争的市场中，竞争是一股极其强大的力量。我的意思是，哪怕你只看看社交媒体公司，我认为它们在全球范围内已经造成了巨大的危害，因为它们更关心的是彼此争夺市场份额，而不是确保其系统的使用不会损害人类的发展。因此，我的观点要悲观和怀疑得多。我真的认为，当摆在眼前的是如此巨额的投资回报，同时又伴随着对投资泡沫破裂的极度恐惧时，在这里追逐利润的动机是一股极其疯狂的力量，公众的反对声浪必须足够强烈，才能迫使这些公司在开展业务时提供他们必须达到的安全水平。

<details>
<summary>Original English</summary>

**Speaker A**: So, one way to align corporate incentives with the public good is through regulation. But regulators are currently refusing to do so. I mean, we just saw them release a voluntary semi-agreement between AI labs, which won't be legally binding, but I think they called it "morally binding," which is quite interesting. In my opinion, competition is a very powerful force in highly competitive markets. I mean, even if you just look at social media companies, I think they've done a huge amount of damage on a global scale because they've been more concerned with taking market share from each other than making sure that the use of their systems isn't, uh, harmful to human development. And so I just think I have a much more skeptical view. I really think that the incentive to make profits here, when there's such a large return to be made and when there's such a fear that the investment bubble is going to burst, is a crazy force, and the level of public opposition has to be strong enough to force these companies to operate with the level of safety that they have to provide.

</details>

**Speaker B**：是的，我很高兴你提到了与社交媒体的对比。几年前，我写过一篇题为《理解社交媒体中的推荐算法》的文章。那篇文章主要讨论的是算法……

<details>
<summary>Original English</summary>

**Speaker B**: Yes, I'm glad you mentioned the comparison to social media. A few years ago, I wrote an essay called "Understanding Recommendation Algorithms in Social Media." It was mostly about the algorithms

</details>

<!-- chunk 6/8 -->

### 社交媒体的短期指标陷阱与 AI 的盲目追逐

**Speaker A**：……他们自己本身。但我当时提出的另一个核心观点是：那种试图通过强制用户无休止地刷信息流来最大化用户参与度（engagement）的决策，在制定时根本没有考虑到从长远来看什么才真正有利于公司自身。例如，我曾研读过 Meta 的一项研究，该研究表明，当他们采用诸如滥发通知等旨在最大限度诱导成瘾的设计决策时，短期内确实提升了应用的使用时长；但大约一年后，用户却开始大规模卸载该应用。而现在当我与我的学生们交谈时，相当一部分人已经极大地限制或彻底放弃了社交媒体，因为他们意识到，在过去的几个月里，使用它的体验完全是在不断恶化。

我担心如今的 AI 公司也已经陷入了同样的陷阱。这种不惜一切代价追逐最新模型的企业文化，在短期内为了吸引媒体头条报道，或者为了在各大 AI 分析评估指数中争夺领先地位，或许看似必不可少；但考虑到其带来的安全隐患，如果他们继续沿着这条道路走下去，我甚至希望他们会面临法律诉讼。我认为这实际上并不符合他们长期的商业利益。

<details>
<summary>Original English</summary>

**Speaker A**: ...themselves, but one of the points I also made was that the decision to optimize engagement by forcing people to endlessly scroll through their feed, etc., was made without considering what was good for the company itself in the long run. For example, I reviewed a study by Meta that showed that when they used design decisions to maximize addiction, such as spamming notifications, it increased app usage in the short term, but after about a year, people started deleting it en masse. And when I talk to my students now, a significant portion of them have severely limited or completely abandoned social media because they realized that over the months their experience of using it has simply gotten worse.

And I worry that AI companies have fallen into the same trap. This culture of chasing the latest model at all costs may seem necessary in the short term for media headlines or leadership in AI analytics indexes, but due to the security implications, I hope they face lawsuits if they continue down this path. I believe it is not really in their long-term commercial interests.

</details>

**Speaker B**：或许这确实不符合他们的长期商业利益，不过社交网络的例子值得我们更深入地探讨。因为与比如 2012 年相比，今天的社交网络虽然遭受了多得多的质疑与审视，但与此同时，它们如今却变得富有得多，市值也大幅攀升。Meta 变得更加庞大了，不是吗？TikTok 也已经成为了一个真正的现象级产品。我认为我们看到的正是一种典型的现实情况：市场所给予真金白银奖励的东西，与社会口头上宣称想要的东西，可能并不一致。

如果这些公司中的某位代表此刻坐在这里，他很可能会说：“听着，我们关注的是用户实际上的所作所为。”无论学生们在你的课堂上怎么表态，人们在 TikTok、Instagram 或其他平台上花费的时间依然比以往任何时候都要多，而且广告的效果也比以往任何时候都要好。老实说，我并不确定他们就一定是错的。他们只有在一种情况下才是错的——那就是当社会做出某种集体决策，迫使市场转向一种不同于其自然演变或当前所处形态的结构时。

<details>
<summary>Original English</summary>

**Speaker B**: Perhaps this is not in their long-term commercial interests, although the example of social networks is worth considering in more detail, as they are viewed much more skeptically today than, say, in 2012. At the same time, today they are much richer. Their capitalization became higher. Meta has gotten bigger, hasn't it? TikTok has become a real phenomenon. I think we're just seeing a standard situation where what the market rewarded and what society says it wanted may not have coincided.

And if a representative of one of these companies were sitting here, he would say: "Listen, we pay attention to what users actually do." They can say whatever they want in your lectures, but people are spending more time than ever on TikTok, Instagram, or other sites, and advertising is working better than ever. And, um, I'm not sure they're wrong. They can only be wrong when society makes a decision that forces the market to take a different form than the one it naturally or currently finds itself in.

</details>

**Speaker A**：是的，所以回到这里，我想我在很大程度上是认同这一点的。但我依然坚信，企业完全可能会做出违背自身长期利益的非理性决策，因为特别是在硅谷，所有人都极度聚焦于短期指标和 A/B 测试。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so, again, I think I mostly agree. I still believe that companies can make decisions that are irrational for their own long-term interests because, especially in Silicon Valley, they are focused on short-term metrics and AB testing.

</details>

### 技术扩散瓶颈：AI 是更快的火车，而不是轨道

**Speaker B**：那么这就引出了你刚才开始触及的话题——也就是“扩散”（diffusion）。你在该问题上的观点与硅谷许多人的主流看法截然不同：你认为 AI 在实体经济和真实世界中的渗透与扩散，将远比人们想象的要困难得多；而在“智能水平”与“实际落地普及”之间，并不存在直接的线性关系。能否请你详细谈谈你对技术扩散的理解？

<details>
<summary>Original English</summary>

**Speaker B**: So we come to the topic that you're starting to touch on, which is diffusion. And one of the things where your view differs from the views of people in Silicon Valley is that AI is going to be much harder to emerge in the economy and in the world than people think. That there is no direct relationship between intelligence and this. So tell me a little bit about diffusion.

</details>

**Speaker A**：好的。写完那篇论文几个月后，一件事情真正让我恍然大悟：当时我看到了美铁（Amtrak）自豪地宣布为其阿西乐特快（Acela）系列采购了全新列车，据称最高时速可达 165 英里。起初我觉得这太不可思议了，这比现有的列车速度快得多。但随后我深入探究了一下，才发现限制行驶速度的根本就不是列车本身，而是轨道弯道过多，以及沿用上百年的陈旧信号基础设施——而这些东西根本没有改变。因此，列车的平均时速几乎没有任何变化，依然徘徊在每小时 65 到 70 英里之间。

这猛然击中了我：这恰恰是用一种非常优雅贴切的方式，表达了我们在《作为普通技术的 AI》（AI as Ordinary Technology）一文中试图传达的核心思想——AI 在很大程度上只是“列车”，而不是“轨道”。换句话说，AI 只是加速了整个流程中某个原本就不是“瓶颈”的环节。在 AI 的外围，还存在着大量的底层基础设施限制：组织文化、法律监管，乃至整个社会对生活中年复一年剧烈变动的承受与适应能力。以自动驾驶汽车为例，无论它理论上能挽救多少生命，它给社会带来的心理冲击都是如此巨大，以至于几乎不可避免地会导致我们目前已经看到的情形：某种程度的政治反弹与抵制。我认为，要做出所有落实这些技术所必需的社会机制调整，将需要漫长的时间——如果我们真能彻底完成这些调整的话。

因此，我对这一维度的 AI 愿景持极度怀疑态度。你经常会听到萨姆·奥特曼（Sam Altman）谈论 AI 将如何通过驱动创新来帮助我们彻底解决能源难题。将这种论调抽丝剥茧还原到本质，其潜台词无非是：目前清洁能源发展的主要瓶颈是“人类智能的不足”。但这根本不是事实，这完全违背了现实。我们明明清楚知道，对于现有大部分能源基础设施而言，我们早已掌握了比目前实际应用方案先进得多的能源技术；我们之所以没有推广应用，是因为这触碰并损害了某些既得利益集团的利润；我们之所以推进不了，是因为现实世界中的实体工程建设面临着巨大的政治壁垒；我们之所以止步不前，是因为唐纳德·特朗普极度排斥太阳能和风能；我们受阻的原因多不胜数。在我看来，许多现实问题都是相通的：即便你盲目加速或成倍提升其中的智能水平，你转头依然会狠狠撞上社会中其他真正的制约因素。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, it really dawned on me a few months after writing the essay, when I saw Amtrak's proud announcements of new trains purchased for the Acela series. Apparently they can reach speeds of 165 miles per hour. At first I thought it would be incredible. That's much faster than trains go now. But then I dug into it a little more and it turned out that it wasn't the trains themselves that limited the speed. These are tracks that have too many curves and a signaling infrastructure that is hundreds of years old. And these things don't change. So the average speed has hardly changed. She is still between 65 and 70 miles per hour.

And it struck me that this is, you know, a pretty elegant way of saying what we were trying to convey in "AI as Ordinary Technology": that AI is mostly trains. These are not tracks. So, AI speeds up a part of the process that wasn't a "bottleneck" to begin with. There are many other things, more infrastructural, things happening around AI. Organizational culture, regulation, even, you know, our social capacity to accept annual changes in our lives, like driverless cars -- no matter how many lives they might save, it's so shocking to society that it's almost inevitable that it's going to lead to what we're already seeing: some kind of political backlash. And I think it will take a long time to make all the social adjustments necessary to implement these technologies. If we do it at all.

So, I'm incredibly skeptical about this part of AI, these AI things, you know? You'll hear Sam Altman talk about how AI, through innovation, will help us solve our energy problems. Another way to boil this idea down to its essence is that the main limitation to clean energy right now is intelligence. Mhm. But that's not true. This is not true. We know that we have much better energy technologies than what we currently use for much of our energy infrastructure, and we are not implementing them because it conflicts with someone's profits; we don't do this because there are political restrictions on building in the real world; we don't do it because Donald Trump hates solar and wind energy; we don't do this for many reasons. And it seems to me that a lot of things are the same: if you accelerate or increase the amount of intelligence in them, you just run into other limiting factors in society.

</details>

**Speaker B**：确实，新药研发要面对漫长的临床试验、FDA 的审批规制等等一系列流程。我的那本《富足》（Abundance）探讨的正是其他领域存在的类似困境。我们明明早就懂得如何建造更高速的高铁列车，其他国家也都在造；但我们自己就是建不起来。我完全想不明白为什么 AI 就能迅速化解这些顽疾，甚至怀疑它是否真的有能力解决。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, drug development has testing, and, you know, the FDA, and all these... I mean, "Abundance," my book, is about that in other areas. We know how to build faster trains, they are being made elsewhere. We don't do this, and it's not clear to me why AI should solve these problems quickly or whether it can do it at all.

</details>

### AI 对决 AI：内部军备竞赛与生产力悖论

**Speaker A**：完全是这样。而且雪上加霜的是，这里还存在着各种形式的军备竞赛。上周保险行业发布了一份极具启发性的重磅报告，指出在过去几年里，AI 很可能已经给全美医疗系统凭空增加了 10 亿美元的成本，原因在于各大医院开始利用 AI 针对完全相同的诊断和治疗方案，编码出更加复杂、收费更高的病症分类代码。当然，对于他们给出的具体数字我们理应保持审慎怀疑，但《纽约时报》的专文对此做了报道，其他学者和科学家也指出了完全相同的现象。

而这恰恰是我们反复目睹的军备竞赛雏形。我们在法律界同样看到了这一幕：法律 AI 目前备受追捧，群情激昂，但这本质上是“AI 对抗 AI”。这实际上就是一场水涨船高的军备竞赛，双方博弈的成本与门槛被整体推高，平衡点仅仅是同步向上平移而已。我和阿什（Elliott Ash）以及贾斯汀·柯尔（Justin Curl）曾就此合作撰写过一篇文章。我们在文中不仅剖析了这种零和式的军备竞赛，还指出了司法体系中其他根本性的“硬瓶颈”。举例来说，即便我们依靠技术让庭审流程的运转效率大幅提高，法官的总人数依然是极其有限的。而且我认为，我们不可或缺的是人类法官；我们绝不能用人工智能来取代人类法官。哪怕它在某些特定方面确实效率更高，但在我看来，将人类命运走向的裁决权拱手让给人工智能，在定义上几乎是不言自明的退让与沦陷——因为法官代表着法律的解释与确立，这绝不是我们能够转让给 AI 的权力。因此，这些都是极为本质且无法逾越的制约。

<details>
<summary>Original English</summary>

**Speaker A**: This is true. And on top of that, there are different types of arms races. So, last week, there was a great report from insurance companies that said AI has probably already added a billion dollars to medical costs in the last few years as hospitals use it to code more complex conditions for the same diagnoses and the same treatments. Of course, we should be skeptical of any specific numbers they give, but the New York Times article mentioned it, and other people, scientists, have pointed out the same thing. And yes, this is a kind of arms race that we often see.

We see this in the legal profession, AI for law, there's so much excitement around it, but it's AI versus AI. This is, in fact, an arms race, where the balance simply shifts upwards. Ash and I wrote an article about this with Justin Curl. And we are talking not only about the arms race, but also about other "bottlenecks." For example, even if we make court processes much more efficient, there is still a limited number of judges. And I think we need, you know, we need human judges. We should not replace human judges with artificial intelligence. Even if it is more efficient in some ways, for me it is, by definition, almost axiomatic, a transfer of control over the course of human destiny to artificial intelligence, because judges make the law, and that is not something we should give to AI. So these are really fundamental limitations.

</details>

**Speaker B**：我想回过头来深入聊聊你谈到的“AI 对抗 AI”这一点，因为我认为这个维度的影响被严重低估了。我常常百思不得其解：为什么互联网的普及并没有像人们预期的那样，给全球生产力和创新带来更为显著的爆发式增长？而我始终坚信的原因在于：虽然互联网确实兑现了理想主义者对它的全部期许——它确实实现了全世界人们之间天涯若比邻的即时协同；它先是将人类有史以来几乎全部的知识宝库平民化地展现在我们面前，随之又顺理成章地将这些语料开放成了 AI 训练的绝佳温床——但它同时也带来了彻底的反向侵蚀。

它表面上看似为我们按下了加速键，但与此同时却严重拖慢了我们的脚步。它无休止地分散着我们的注意力。因此如今当你试图专注手头的工作时，你总是在电子邮件、网络游戏和社交媒体之间来回切换，深度专注的能力急剧退化。而且你知道，色情内容的泛滥似乎也深刻影响到了人们在现实生活中建立真实亲密关系的能力。在一个领域消除摩擦成本，同时也等同于在其他或许毫无助益、甚至具有破坏性的领域消除了阻力。而当你进一步设想将更强大的智能叠加进这个系统时……

<details>
<summary>Original English</summary>

**Speaker B**: I want to come back to your point about AI versus AI, because I think it's very underestimated. I often wonder why the internet hasn't led to a greater increase in global productivity and innovation than it has. And I always think the reason is that while it did everything that idealists expected of it, it really allowed for instant collaboration with people all over the world. He made virtually the entire body of human knowledge first accessible to us, and then, as it turned out, accessible for AI training. But he also did the opposite.

It seemed to speed us up, but at the same time slow us down. He was distracting us. Mm. So now, when you're working on something, you're constantly switching between email, online games, and social media. And your ability to concentrate deteriorates. And, you know, there's been an increase in pornography, which seems to have affected whether people are building real relationships. That reducing friction in one area also reduces it in other, perhaps less useful areas. And when you think about adding intelligence,

</details>

<!-- chunk 7/8 -->

### 被低估的日常损耗与知识工作的管理者陷阱

**Speaker A**: 嗯，这种智能同样也会被加持到对立面。我常常觉得，在技术发展的早期阶段，人们往往只看得到它会让事情变得多么美好。而现在面对人工智能，我认为大家都在大量思考它会如何让事情变得极其糟糕，对吧？比如巨大的网络安全威胁、金融系统崩溃，或者是人类的灭绝。但在我看来，它以一种看似微不足道的方式让事情恶化——仅仅是通过增强人们浪费他人时间的能力——这一面在某种程度上被低估了。

<details>
<summary>Original English</summary>

**Speaker A**: Well, that intelligence will be added on the other side as well. And I always think that in the early days of technology, we only see how it will make things better. And I think right now with AI we're thinking a lot about how it can make things much worse, right? Huge cyber threats, the collapse of the financial system or the extinction of humanity. But the way it can make things worse in a trivial way, simply by increasing people's ability to waste other people's time, is a bit underrated in my opinion.

</details>

**Speaker B**: 确实如此。而且，这绝不仅仅是琐碎平庸的小事。我认为存在许多这类次灾难性的损失，它们其实相当严重。在工业革命期间，我们经历了长达数十年极其恶劣的工作环境。我认为人工智能也是一样：虽然大家把大量注意力放在了工作岗位流失上，但对工作质量正在发生的变化却关注得少得多。我认为这是一个被严重低估的领域，因为人工智能正在将许多知识工作者转变成人工智能智能体（AI Agents）的管理者。

<details>
<summary>Original English</summary>

**Speaker B**: Certainly. And, you know, it's not just banal. I think there are a lot of these sub-catastrophic losses that are quite serious. During the Industrial Revolution we had several decades of terrible working conditions. I think it's the same with AI: while so much attention is paid to job losses, much less attention is paid to how the quality of work is changing. And I think this is a huge underrated area because AI is turning many knowledge workers into managers of AI agents.

</details>

**Speaker A**: 嗯。

<details>
<summary>Original English</summary>

**Speaker A**: Mhm.

</details>

**Speaker B**: 对吧？问题在于，当一名管理者其实是一种相当糟糕的体验，因为你必须对别人犯的错误负责。你无法继续践行自己当年所学的那门手艺。不过作为人类管理者，我们通常是没有资格抱怨的：因为管理岗拿更高的薪水，有更高的社会地位，这是我们自己的选择，而且指导他人本身也很有成就感。但对于人工智能，你完全享受不到这些好处。你必须去管理这个智能体，并为它的错误承担责任，同时你又无法亲自操练自己的专业技能。我认为我们完全可以通过不同的方式来设计 AI 智能体以避免这种情况，但眼下正在发生的恰恰就是这一幕。所以，我认为我们确实应该对此深感忧虑。

<details>
<summary>Original English</summary>

**Speaker B**: Yes? And the thing is, being a manager is a pretty crappy experience because you're responsible for other people's mistakes. You are unable to practice the craft you studied. But you know, as human managers, it's a sin for us to complain. It's a higher salary, a higher status, we chose it ourselves, and of course, mentoring is rewarding. With AI, you don't get any of these benefits. You have to manage this agent and be responsible for his mistakes, but you can't practice your profession. I think we can design AI agents differently to avoid this, but that's exactly what's happening right now. And yes, I think we should be very concerned about this.

</details>

### 物理世界的迟缓与数字世界的狂飙

**Speaker A**: 那么，我们这里讨论的内容，在多大程度上会引申出一种关于经济发展极不均衡的理论呢？也就是那些必须与现实物理世界结合的事物。

<details>
<summary>Original English</summary>

**Speaker A**: So how much of the story we're telling here leads to a theory about what would happen in an economy that is very uneven? Those things that require merging with the real world.

</details>

**Speaker B**: 嗯，是的。

<details>
<summary>Original English</summary>

**Speaker B**: Mhm. Yes?

</details>

**Speaker A**: 一切都必须在实体物理层面发生。我们必须建造楼房，铺设输电线路。这存在着极其强大的物理速度上限，根本无法加速得太快。

<details>
<summary>Original English</summary>

**Speaker A**: Everything has to happen physically. We need to build buildings and lay power transmission lines. This has such powerful speed limits that it can't accelerate too fast.

</details>

**Speaker B**: 嗯。

<details>
<summary>Original English</summary>

**Speaker B**: Mhm.

</details>

**Speaker A**: 与此同时，在数字世界里，事情的发展却能非常、非常、非常迅速。所以，那些完全坐在电脑前工作的白领们会遭遇什么？他们的工作实际上是可以被自动化的，比如呼叫中心之类的岗位。或者换个角度看，比如我们刚才讨论的所有这些网络犯罪和网络安全问题——令我担忧的未来版本是：真正能够改善大众生活的大多数事情，都必须在实体物理世界中落地，然而人工智能的发展速度却在数字世界中狂飙突进。综合权衡下来，这听起来并不像是一个我们能从人工智能中获得最大收益的世界，反而可能是一个我们遭受最大危害的世界。

<details>
<summary>Original English</summary>

**Speaker A**: Meanwhile, in the digital world, things can move very, very, very fast. So, you know, what happens to white-collar workers who work entirely behind a computer and whose work can actually be automated, like in a call center or something like that. Or, separately, like all of this cybercrime that we're talking about and cybersecurity—I think the version of this future that worries me is that actually most of what would improve people's lives has to happen in the physical real world, but AI will be able to move the fastest in the digital world. And on balance, I don't think this sounds like a world in which we get the most benefit from AI, and in fact it might be a world in which we get the most harm from it.

</details>

### 杰文斯悖论与潜在需求的释放

**Speaker B**: 在我看来，确实有这种可能。不过我也不确定。我认为我们是有办法去改变这一局面的。首先，我并不认为所谓的“飞速”真有那么快。举个例子，你刚才提到了呼叫中心。我的意思是，它们现在依然存在。要知道，当 ChatGPT 刚问世时，很多人曾预测在一年之内我们就会把呼叫中心全部取代。毕竟它的名字里就带着“聊天机器人”。很有可能发生的情况是，如果人工智能让呼叫中心员工的工作效率大幅提升，其实背后隐藏着巨大的潜在需求。我们很多时候不给呼叫中心打电话，纯粹是因为体验太糟糕了。所以，这又回到了杰文斯悖论（Jevons' paradox）。

<details>
<summary>Original English</summary>

**Speaker B**: Me, yes, it's possible. I don't know. I think there are ways, you know, we can, we can change that. I don't think fast is that fast, first of all. For example, you mentioned call centers. I mean, they still exist. You know, when ChatGPT came out, many people predicted that within a year we would replace them all. I mean, chatbot is in the name itself. If, as is likely, AI makes call center workers much more productive, there is a large latent demand. Often we don't call call centers because it's an unpleasant experience. So, again, this is Jevons' paradox.

</details>

**Speaker A**: 你介意向大家解释一下什么是杰文斯悖论吗？

<details>
<summary>Original English</summary>

**Speaker A**: Would you mind describing what it is?

</details>

**Speaker B**: 没问题。它的核心观点就是：当某种东西的生产成本变得更低时，人们对它的需求反而会大幅增加。让我们来看看目前人工智能能力发展最为成熟的领域，那大概就是软件开发了。在过去，开发软件的成本高得惊人，因此全世界每年编写的代码量只有区区几万行；而现在，这个数字已经增长了大约一百万倍。所以从长远来看，这究竟会大幅提升对软件工程师的需求，还是说目前初级开发者面临的就业严冬会一直持续下去——这一切仍有待观察。我认为两者可能兼而有之。但无论如何，如果这是在未来二十年的跨度里逐步发生的，那它依然与工业革命等重大历史转折保持一致：许多旧岗位消失了，但大量全新的岗位也被创造出来。另一个例子是翻译工作。早在 2016 年——这当然远在我们今天所说的生成式 AI 出现之前——机器翻译模型就已经非常接近人类水准了。然而翻译这个职业至今仍然相当稳定，只不过工作的本质发生了很大改变。所以说，由于你现在可以把任何内容翻译成任何语言，巨大的需求被彻底激发了出来。这就是杰文斯悖论。

<details>
<summary>Original English</summary>

**Speaker B**: That's right, yes, it's the idea that when something becomes cheaper to produce, there's now a greater demand for it. Let's look at the sector where the capabilities are already the most developed, which is probably software development. Mhm. It used to be extremely expensive to produce software, so only a few tens of thousands of lines of code were written worldwide per year, but now that has increased by about a million times. And so, in the long term, you know, whether this will be something that will increase the demand for software engineers, or whether the difficult job prospects for junior developers that we're seeing now will persist—that's yet to be seen. I think it's probably both, but, you know, in any case, if it happens over the course of 20 years, again, it's consistent with other major shifts like the Industrial Revolution, where a lot of jobs disappeared, but a lot of new ones were created. Another example is the work of translators. Um, you know, back in 2016, this is of course long before what we call generative AI today, translation models became pretty close to human-level. But these jobs are still pretty stable. The nature of work has changed a lot. So, again, there is a much greater demand that has opened up because you can now translate anything into any language. Hence, Jevons' paradox.

</details>

### 与比尔·盖茨的商榷：蓝领行业与需求天花板

**Speaker A**: 我前不久刚和比尔·盖茨聊过。当我向他提起这个理论时，他对此颇有疑虑。他说：“这么说来你不相信杰文斯悖论？那你能不能列举出一个符合杰文斯悖论的蓝领工薪阶层职业？你难道不关心工薪阶层吗？”我说：“我当然关心工薪阶层。”于是核心问题就在于：你能在工薪职业领域里找出一个适用这一定律的例子吗？盖茨的论点是，软件开发确实是经济中一个存在巨大未满足需求的领域。每个人大概都希望能拥有自己的专属程序员。因此，在这个你能急剧加速该流程的世界里，你确实会看到需求激增的效应，因为程序员变得更便宜了，反而催生了更大的需求。但他接着指出，许多行业根本不是这么运转的。以卡车司机为例：如果有一天我们实现了完全无人驾驶卡车，首先，整体运输需求是有限的；其次，卡车里根本就不再需要司机了。如果你看看制造业中那些被自动化取代或者产能转移到中国的工人，整体经济固然在持续增长，但其中许多人的生活却陷入了极其艰难的境地。因此盖茨的观点是，杰文斯悖论的力量不足以抵御这种冲击，因为在经济体系中有太多的部门并不存在潜在未满足的需求，需求就只有那么多。你对此怎么看？

<details>
<summary>Original English</summary>

**Speaker A**: I just spoke to Bill Gates, and when I mentioned it, he was a little skeptical about it. So you don't believe in Jevons' paradox. Name a working-class profession that is subject to Jevons' paradox. So you don't care about the working class? I care about the working class. So the question is, can you name anything in the field of working professions that falls under this? And his thesis was that software development is indeed a sector of the economy with a large unmet demand. You know, everyone probably would like to have their own programmers. So in a world where you accelerate this process rapidly, you can get a demand effect that simply creates a greater need for programmers because they are now cheaper. But he went on to say that many things don't work that way at all. Take, for example, a truck driver. If we get to the point where trucks are driverless, firstly, the demand for transportation is limited, and secondly, there is no longer a driver in the truck. If you look at the many people whose jobs were automated or moved to China in manufacturing, the economy did continue to grow, but many of those people had a very, very hard time. So his argument is that Jevons' paradox won't be strong enough to handle this because there are too many sectors of the economy where there is no latent demand. Demand is exactly what it is. What do you think about this?

</details>

### 马斯洛需求层级与人际交互的不可替代性

**Speaker B**: 是的，我认为他在卡车司机这个例子上说得完全正确。我非常赞同这一点，那里的运输需求确实相对有限。但核心问题在于，这究竟是普遍规律还是个别例外？不妨让我这样解释：看看我们现在正在做的事情吧。根本没有谁强求我们非得做这个播客。如果你回到 100 年或 200 年前，人们会惊呼：“这怎么可能算是一份正经工作？”我们今天从事的大多数职业，可以说都处于马斯洛需求金字塔的更高层级。它们并不满足人类赖以生存的任何实质、固定的生理刚需。我们做这行纯粹是因为它充满乐趣，而且观众也乐意收听。大多数办公室白领工作都是这个性质。这就是我的观点：杰文斯悖论适用于绝大多数办公室白领职业。一旦生产成本降低，需求就会被源源不断地创造出来，尤其是随着人们收入的逐渐提升，大家会把更多钱花在这些不那么必需、更偏向“奢侈品”体验的事物上。工薪蓝领职业其实也是如此。阿列克斯·伊马斯（Alex Imas）曾写过一篇极佳的随笔，题目叫《什么将会变得稀缺》（What Will Become Scarce）。他在文章中指出，比如星巴克的咖啡师，按理说这个岗位早就不该存在了。我们很久以前就知道如何将其完全自动化，我们甚至在家里就能自己冲咖啡。我不确定他原话是不是这么说的，但这揭示了人与人之间面对面互动在工作中的重要性。因此我认为这些职业依然会相当稳固，哪怕人工智能以某种方式让它们变得更便宜。所以在我看来，卡车司机的处境更像是一个特例。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, I think he's absolutely right about truck drivers. I completely agree with this. The demand there is relatively limited. The question is whether this is the rule or the exception. Let me put it this way. Look at what we're doing here. Nobody asked us for this. You know, if you went back 100 or 200 years, it would be like, "How can this be a real job?" Most of the professions we have today are higher up on Maslow's pyramid, if you will. They do not satisfy any real fixed demand or need that people need to live. We do it because it's fun and people like to listen to it. Most office jobs are like that. This is my point of view. Jevons' paradox is characteristic of most office professions. If it becomes easier to produce it, there will be a demand for it, especially as people's incomes gradually increase and they spend more on these, you know, less necessary, more "luxury" things. And working professions too. There is a great essay by Alex Imas called “What Will Become Scarce,” where he points out that the job of barista at Starbucks, for example, should no longer exist. We have known for a long time how to automate this. We can even make coffee at home. I don't know if that's what he said, but you know, that's the importance of the interpersonal nature of the work. And so I think they will remain quite stable, even if artificial intelligence somehow makes them cheaper. So, I think that the work of truck drivers is more of an exception.

</details>

**Speaker A**: 随着我们逐渐接近尾声，我想请问：在未来两三年内，究竟必须发生什么样的事情，才会让你忍不住感叹：“糟糕，眼下的走向似乎不如我们预期的那么平稳常规”，或者“情况明显比我们预想的偏离轨道得多”？到底需要出现怎样的证据，才会让你实质性地修正自己的核心论点？

<details>
<summary>Original English</summary>

**Speaker A**: I think as we get closer to the end, what would have to happen in the next couple of years that would make you say, "Oh, this looks less normal than we thought." "Or it's significantly more off course than we expected." What evidence would have to emerge for you to significantly change your thesis?

</details>

<!-- chunk 8/8 -->

### 经济与安全层面的质疑

**Arvind Narayanan**：当然。关于经济和安全两方面确实都存在疑问。就经济而言：如果在某种能力水平上，我们开始看到这不再只是人们适应使用 AI 来提高自身生产力并管理人形/软件智能体的过程（就像我们目前看到的那样），而是开始大规模替代人类——无论他们是软件工程师还是其他任何职业——我认为那将与我们目前的大多数预测大相径庭。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Of course. Yes, there are questions about the economy and questions about security. Regarding the economy: if we start to see at some level of capability that this is no longer a process of simply adapting people to use AI to improve their productivity and manage agents, as we see now, but instead it starts to massively replace people—whether they're software engineers or any other profession—I think that would be quite different from what we're mostly predicting.

</details>

**Arvind Narayanan**：关于安全问题，尤其是考虑到一些公司声称自己接近实现递归自我改进（recursive self-improvement）：我认为他们根本不应该仓促进入完全自主的递归自我改进阶段，这也是你刚才似乎提到的。但无论如何，我们认为即使这种情况发生，它也不会带来超级智能，因为超级智能的瓶颈来自外部。你在实验室里根本无法教一个 AI 模型去攻克癌症，或者做其他任何各大公司希望做的事情。但再次强调，这是一个经验性的判断，如果事实并非如此，那肯定会彻底推翻我们的核心论点。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Regarding security, especially given the companies' claims of being close to recursive self-improvement: I don't think they should rush into full autonomous recursive self-improvement at all, which is what you seem to have said, but in any case, we believe that even if it happens, it won't lead to superintelligence, because the bottlenecks for superintelligence are external. There's nothing you can do in a lab to teach an AI model, say, how to cure cancer or anything else that companies hope to do. But again, this is an empirical statement, and it would certainly completely refute our thesis.

</details>

### 书籍推荐与系统思考

**Ezra Klein**：最后是我们的常规问题：您想向我们的听众推荐哪三本书？

<details>
<summary>Original English</summary>

**Ezra Klein**: And finally, our last question: what three books would you recommend to our audience?

</details>

**Arvind Narayanan**：好的。你知道，在这次对话中，我总体上采取了比我们平时听到的更为乐观的视角，尤其是在 AI 安全方面。所以，也许契合这一点，我非常喜欢汉娜·里奇（Hannah Ritchie）的书《并非世界末日》（*Not the End of the World*）。她后来出了一本新书，但这本是 2024 年出版的，我依然很喜欢它。副标题大致是这样的：“我们如何成为建设可持续地球的第一代人”。这是对气候问题的一种乐观视角。当然，气候领域通常充斥着悲观预测，这也是我喜欢这本书的原因。这是一本关于技术的非常乐观的书。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Of course. You know, in this conversation, I generally took a slightly more optimistic view of things than we're used to hearing, especially on the safety of AI. So, perhaps in line with that, I really like Hannah Ritchie's book, *It's Not the End of the World*. She has a newer book, but this one is from 2024, and I still really like it. The subtitle goes something like this: *How We Can Be the First Generation to Build a Sustainable Planet*. It's an optimistic view of the climate, which, of course, is usually full of gloomy forecasts, which is why I liked it. This is a very optimistic book about technology.

</details>

**Ezra Klein**：我……我也非常喜欢这本书，它确实能让人意识到，随着时间的推移，我们真的创造出了更好的事物。

<details>
<summary>Original English</summary>

**Ezra Klein**: I-I-I really love this book too, and it makes you realize that we really do create better things over time.

</details>

**Arvind Narayanan**：是的。我认为有时我们对技术抱有过于消极的态度。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Yes. I think sometimes we have too negative attitudes towards technology.

</details>

**Arvind Narayanan**：是的。呃，关于中国——这当然是一个许多人都感兴趣的话题。我相信你经常听到别人推荐这本书：我喜欢王丹（Dan Wang）的书《飞速前行》（*Breakneck*）。它也多次呼应了“富足”（abundance）这个概念。不过，将法治社会与工程社会进行对比思考的这一视角，我认为是一种非常贴切且精炼的方式，能够捕捉到许多宏观和微观层面的差异。

最后推荐的是一本老经典。请允许我先做个铺垫：我曾经读过一篇两页的文章，名为《复杂系统如何走向失败》（*How Complex Systems Fail*）。我起初以为那篇文章讲的是软件系统。但我后来意识到，它实际上讲的是医疗系统，由一位麻醉医师撰写。通过它我了解到，存在着这样一门关于系统的研究学科，它解释了各种类型系统中的共通规律：自然系统、社会系统以及工程系统。这让我找到了德内拉·梅多斯（Donella Meadows）多年前写的那本书——《系统思考》（*Thinking in Systems*）。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Yes. Uh, about China, which is of course a topic that interests many. I'm sure you've heard this book recommendation often. I liked Dan Wang's book *Breakneck*. It also has many echoes of abundance. But this idea of thinking about a legal society versus an engineering society is, I think, a very apt and concise way to capture a lot of the macro and micro differences. And the last one is an old classic. Let me preface this by saying: I once read a two-page article called "How Complex Systems Fail." I thought the article was about software. But I realized that it was actually about medical systems, written by an anesthesiologist. And I learned that there is a study of systems that explains patterns in all types of systems: natural, social, and engineering. This led me to Donella Meadows' book *Systems Thinking*, written many years ago.

</details>

**Ezra Klein**：阿尔文德·纳拉亚南（Arvind Narayanan），非常感谢您。

<details>
<summary>Original English</summary>

**Ezra Klein**: Arvind Narayanan, thank you very much.

</details>

**Arvind Narayanan**：谢谢你，埃兹拉（Ezra）。这次对话非常有趣。

<details>
<summary>Original English</summary>

**Arvind Narayanan**: Thank you, Ezra. It was very interesting.

</details>