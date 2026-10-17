---
author: a16z
date: '2026-09-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ut3LOjKNJaE
speaker: a16z
tags:
  - software-architecture
  - software-automation
  - probabilistic-programming
  - system-reliability
  - deterministic-systems
title: 超越代码生成：Jev 如何将 AI 转化为可信赖的软件系统原语
summary: TypeSafe 创始人 Diogo 深入剖析了为何当前代码生成 Agent 无法解决真正的软件自动化难题。他指出，真正的革命不在于用 AI 替代工程师写样板代码，而是将智能作为一种连接自然语言意图与状态机的新型软件原语嵌入系统内部，通过极致的可靠性保障，彻底重塑软件与 SaaS 行业的未来。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - TypeSafe
  - OpenAI
  - Google Brain
products_models:
  - Jev
  - ChatGPT
  - Claude Code
  - Codex
media_books: []
status: evergreen
---
### 自动化的失焦与困境

**Speaker 0**: 我们到底把焦点放在哪里了？现在所有的自动化 AI 都聪明得不可思议，但在其他所有实际事务上却又如此无用。

<details>
<summary>Original English</summary>

**Speaker 0**: Where are the focus? All the automation AI is so unbelievably smart, and yet it's so useless at all other stuff.

</details>

**Speaker 1**: 确实关系不大。无论你用多少 AI 编码助手，软件本身其实并没有真正变好。也许你交付的速度变快了，但软件质量往往变得更差。

<details>
<summary>Original English</summary>

**Speaker 1**: It doesn't matter much. AI coding agents, you suffer, and software isn't getting better. So maybe you get faster, but it's usually getting worse.

</details>

**Speaker 0**: 自从 2020 年以来，大家就一直在尝试把客户服务自动化。但我真正想要的不是那种东西，而是**智能软件**（Smart Software）。我希望拓展软件本身的能力边界，让那些本该被自动化的事情真正变得可自动化。

<details>
<summary>Original English</summary>

**Speaker 0**: AI has been trying to automate customer services since 2020. What I want instead is smart software. I want to expand what software itself can do, such that things that should be automatable can then be automatable.

</details>

**Speaker 2**: 我最喜欢你们常说的一句话：“**我们造的是产品，不是神**（We build PRD, not God）”。因为如果换作其他任何大模型实验室的领导者，即便他们心怀喜悦，也会表现得遮遮掩掩。但你的视角截然不同，你觉得我们要为更细致、务实的理由去创造一个更美好的世界。

<details>
<summary>Original English</summary>

**Speaker 2**: My favorite thing that you guys say: we build PRD, not God. Because if we had any other kind of like big lab leader, even if they had joy, they would cover. And then your view is so different. You're like: no, we're going to create a way better world for nuanced reasons.

</details>

**Speaker 0**: 没搞错，我完全不认为我们正处于那种所谓“SaaS 大溃败”（SaaS-pocalypse）的悲观叙事轨道上。

<details>
<summary>Original English</summary>

**Speaker 0**: Exactly, I don't think we're on the path of our side in the SaaS-pocalypse story.

</details>

**Speaker 2**: 今天，我们邀请到了 **TypeSafe** 的创始人兼负责人 **Diogo**。对于我们和许多开发者来说，他都是一位领军人物。他不仅在打造一款极其有趣的产品，而且还在引领一场我们认为至关重要的行业运动。我们对今天的对话感到非常兴奋。

<details>
<summary>Original English</summary>

**Speaker 2**: Today, we have the founder and leader of TypeSafe, Diogo, with us, who is a bit of a hero to both Martin and me. He is not only building a really interesting product, but creating what we think is a very important movement. So we're super excited about today.

</details>

**Speaker 0**: 太棒了，谢谢你们的邀请！

<details>
<summary>Original English</summary>

**Speaker 0**: Rock and roll, yeah. Thank you.

</details>

**Speaker 2**: 或许你可以先给我们简要介绍一下，到底什么是 **Jev**？什么是 TypeSafe？为什么它如此重要？

<details>
<summary>Original English</summary>

**Speaker 2**: Yeah. And maybe you can give us kind of a brief on just, you know, what is Jev? What is TypeSafe? Why is it important?

</details>

**Speaker 0**: 这是一个轻松随意的电梯演讲时间吗？如果是的话，我平时其实不太擅长做简短推介，经常容易漫谈。但我最近越来越意识到，我对 Jev 最喜欢的电梯演讲切入点就是：自动化到底都去哪儿了？

这真的太不可思议、太令人遗憾了。有那么多智能，AI 明明聪明得难以置信，但我并不是要贬低聊天机器人或者编程 Agent，我自己也经常使用它们，非常喜欢它们。然而悲哀的是，它在其他所有正经任务上几乎都毫无用处。

我们手里捧着一块未经雕琢的璞玉，却没有真正打磨好用于生产实践。这就是 TypeSafe 的使命所在——**为软件打造 AI**。我们不是仅仅为了把人类保留在循环中（Human-in-the-loop）而让 AI 变得强大，而是为了真正去构建现实世界里的软件。对我们而言，Jev 是我们在这个领域的第一个模型，旨在让自动化变得真正可行、真正可靠。

<details>
<summary>Original English</summary>

**Speaker 0**: Is this a quick friendly one? Cool. So my favorite elevator pitch for Jev is: where the fuck is all the automation? This is so unbelievably tragic, you know. So much intelligence, AI is so unbelievably smart, and yet—not that I hate on chatbots or coding agents, I love them myself, but it's like it's so useless at all other stuff, and it's tragic.

It's tragic that we have so much like diamond in the rough, but not polished for work. But TypeSafe is making AI for software, you know, to make AI powerful not just for humans in the loop, but to actually build real software. And Jev to us is our first model in this whole space to make a way better world to make automation real.

</details>

### 智能软件与代码生成

**Speaker 2**: 确实，这在整个软件界引起了巨大的反响和轰动。让我们意识到这里正在发生大事的信号之一是，我们认识的每一个开发者都打电话过来说：“这东西太震撼了，速度极快，效果极好，一切都变得更顺畅了。”

大家都知道现在已经有了 **Claude Code**、**Codex** 这一类工具，市面上已经有代码生成了。那么 Jev 与它们的核心区别到底是什么？它是如何引领真正意义上的自动化的？

<details>
<summary>Original English</summary>

**Speaker 2**: Yeah, it's been interesting because it's kind of caught fire in the software world. One of things that made us go, what else is going on here, is like every developer we know is calling us and going: this is fricking awesome. It's fast, it's great, everything's better. And then how does that—because everybody thinks, oh, we've got Claude Code, we've got Codex, we already have that. What's the difference? And then how does that lead to real automation?

</details>

**Speaker 0**: 真希望我手头有些可视化的图表，因为我对这个问题有一个非常形象的比喻。对于 Claude Code 和 Codex，我非常认同来自行业内的一个评价：它们是“**即时软件**”（Just-in-Time Software）。这是描述它们所作所为的一个绝妙方式。它们可以在运行时根据自然语言飞速生成软件代码，但在表达能力上，它本质上依然处于传统软件的同一范畴内。

而我想要的则是**智能软件**（Smart Software）。我不想去单纯自动化软件工程这个岗位，我想要扩展**软件本身所能做到的极限**，让那些原本不可能自动化的事情变得可以被软件自动化。

用更具表达力的话来说，我想在软件中表达“意图”，我想扩展我们在代码中能做事情的词汇库。编程的本质是对极其有价值的逻辑进行极致细致的规范化定义，然后以极低成本进行无限复制，这简直太酷了。我只是想让软件的这个特质变得更加强大、更有深度。

<details>
<summary>Original English</summary>

**Speaker 0**: Oh, I wish I had some visuals, because I had a favorite visual for this. With Claude Code and Codex, I love the description on them: it's just-in-time software. Incredible way to describe what they're doing. It makes software on the fly, and you can program software in natural language, but it has the same expressive power of traditional software.

What I want instead is smart software. Instead of automating software engineering, I want to expand what software itself can do, such that things that should be automatable can then be automatable. And like in more flowery language, I want to express things like intent, I want to expand the vocabulary of what we can do. Programming is like hyper-specifying valuable things, and then infinitely replicating them. It's so freaking cool, and I want to just make that more interesting.

</details>

**Speaker 2**: 所以换个角度来理解：现在的工具往往只是用一个虽然更快、但水平可能还不如真人工程师的系统去替代一部分研发人员；而你们的做法完全不同，你们是在超级赋能现有的软件工程师，让他们有能力去写出层级更高、更加强大、更加有趣的系统。

<details>
<summary>Original English</summary>

**Speaker 2**: So one way to think about it is: instead of kind of a tool that somewhat replaces a software engineer with a faster, maybe not even as good software engineer, what you're saying is we're going to super-empower the software engineers we have to write way, way better, more interesting things.

</details>

**Speaker 1**: 没错，正是这样。我觉得太多人都忽略了这一点，而这恰恰是最关键的分水岭。如果你使用 Claude Code 或 Codex，它们确实很棒，但它们生成的依然是人类工程师十年前就会写的那种代码。代码写出来，好坏暂且不论，它的基本范式没有变。

但 Jev 带来的不同之处在于，无论你是让 AI 帮你写代码还是人类自己动手，你在编程语言中获得了一个**全新的软件原语**（New Primitive）。这是一个你可以直接嵌入代码中的新模块，它从根本上扩展了软件的能力边界，而不是简单地帮你码字。

而且这个原语非常有趣，因为它彻底改变了程序员的思考方式——例如它引入了概率、置信度的概念。

<details>
<summary>Original English</summary>

**Speaker 1**: Yeah, exactly. I just think so many people miss this point, and it's such an important point to tease out. Which is, if you use something like Claude Code or Codex, which is great, they write code. But code is something a human being would have written. Maybe it's better, maybe worse, but it's basically still code just like code looked ten years ago.

And the thing with Jev is, whether or not you're Claude Code or a human, you have a new primitive. This new thing that you stick in your code that actually expands the power of software itself, instead of just generating code. It is something you include in your code. Which by the way is interesting, because it's a very powerful primitive, but it's also a little bit different than how programmers usually think. For example, it has this notion of probabilities and confidence.

</details>

**Speaker 2**: 也就是说，你可以把它当成软件内部的一个智能层，或者一个库。你可以用自然语言向它描述你的诉求，给它定义一个状态机，然后它会在一定的置信度范围内决定系统接下来该采取什么动作。

<details>
<summary>Original English</summary>

**Speaker 2**: So an intelligent layer inside the software, like a library that you can use natural language to describe what you want. And you give it kind of a state machine, and then it will choose what to do with some confidence levels, which we haven't really had before.

</details>

### 从分类器到系统状态机

**Speaker 0**: 这里面确实有很多设计细节。首先我想回到刚才说的核心痛点：“自动化到底都去哪儿了？”我深爱软件开发，虽然当 CEO 的日常事务多到让我很难整天写代码——我也绝不推荐大家都去当 CEO，但这就是现实。

让人抓狂的是，AI 技术日新月异，而软件的基础运行机制多年来却几乎停滞不前。几乎没有人能把这两者严丝合缝地融合在一起，大家最多做的事情就是在软件旁边挂一个浮动聊天窗口，偶尔让它调用一下 API。但由于模型的不可靠性，很多关键动作根本不敢放手让它做。

其次，关于这种“全新的思考方式”：是的，**机器原生**（Machine Native）的逻辑与计算机传统的二进制比特流之间确实存在摩擦，但这正是我们试图探索的艺术形式。在团队入职的第一天，我通常会在白板上画一个韦恩图，一个圆是“AI 擅长什么”，另一个圆是“代码中真正有价值的是什么”，而 Jev 就坐落在正中心。

我们不会让 AI 去做浮点数的高精度运算，因为 AI 在这方面天生不擅长。相反，像概率这样的概念在现代系统中其实并不罕见。有人经常质疑：“Jev 不就是一个高级分类器（Classifier）吗？”

我的回答是：**Jev 绝对是一个分类器，但分类器酷毙了！** 分类器从诞生起就是为了解决实际问题而设计的。我们采用这些机器学习领域的经典抽象接口，是因为它们源自那些实打实想要让复杂系统跑通的工程师经验。

根据我的观察，在软件中引入 Jev，其工程效果甚至比在 2019 年养一支专门的机器学习工程团队还要出色得多。当年哪有那么多高水平的 ML 团队去专门针对细分场景收集数据集、调优训练并部署验证？而现在，这仅仅只是个开端。

<details>
<summary>Original English</summary>

**Speaker 0**: There's a lot of tricks there. I will jump into one thing first: in the direction of where the fuck is all the automation, I love software so much, I wish I could be writing it all day. I would not recommend being a CEO to people, but whatever. AI is so cool, and software has been largely unchanged. No one can square this together. And the most we can do is add a little chatbot on the side, sometimes that can take actions, but not all actions because some are not reliable.

To the point about this being a different way to think about it: yes, I think that machine-native doesn't match bits perfectly, and that's actually the art form we are trying to do. On day one of onboarding, I draw the Venn diagram of what AI is good at and what is valuable in code. We are in the middle. We don't ask it to calculate extrapolated floats, because AI is just bad at that. But things like probabilities are not novel.

It's similar to the argument: is Jev just a classifier? Jev is absolutely a classifier, and classifiers are sick! Classifiers were designed to be used by practical people trying to make systems work. What I'm seeing now is that Jev is probably better than having an ML team from 2019 building the software for you. Back then there were not that many good ML teams to build narrow things, collect datasets, test and measure. And this is just the beginning.

</details>

**Speaker 1**: 你觉得在这个设计空间里是否存在一个滑块？一端是我们今天常见的“自然语言进，自然语言出”的纯文本模式；另一端是现有的传统程序代码。开发者可以在这两者之间自由权衡？还是说，你认为“**自然语言输入，状态机输出**”就是最终凝固软件泛化能力的黄金设计点？

<details>
<summary>Original English</summary>

**Speaker 1**: Do you think there's a slider bar here? Where at one end is like language in and language out like we have today, and on the other end is existing program code, and you can move between the two? Or do you think this design space—language in, kind of state machine out—is going to solidify the general-purpose primitive for programming?

</details>

**Speaker 0**: 这是一个非常深刻的问题。如果说出我内心最真实的答案，我认为它确实是一个连续的滑块。

在设计 Jev 的属性时，我可能会受到个人偏好的影响。比如在当下，我极度看重“**每单位美元所能换取的智能量**”（Intelligence per Dollar）。当然短期来看，每秒的推理速度（Latency/Throughput）也非常重要。但你看我们的接口设计，我们特意将输入显式命名为“**状态**”（State），这就是有意为之的声明：这个组件生来就是要运行在程序内部的。

我所做的大量底层优化，都是为了应对程序内部越来越复杂的运行状态。你能在状态机内部注入智能吗？这是一场旷日持久的工程攻坚战。我们在系统设计上非常克制、务实。比如在工程实践中，为了在几十毫秒内完成推断，它在一段时间内表现得可能更像是一个高性能数据库，而不是传统的语言标准库。但我长远的梦想，是让它彻底成为软件运行时的标准库原语。

<details>
<summary>Original English</summary>

**Speaker 0**: That's a tricky one. The answer in my heart is that it is a slider. When I design for the properties we have, I might have made mistakes due to my personal preferences, but intelligence per dollar is my priority right now. Intelligence per second might be more valuable in the short term. But even our interface, calling the input "state", this was intentional. It's to say that it's meant to be inside programs.

A lot of the work I do is optimizing for even more complicated arrangements of the internals of program state. Can you put intelligence in there? This is going to be an ever-present battle. Pragmatically, it's easier to make an AI run in these milliseconds, so it'll be more like a database for a while than a standard library thing, but I would love it to be a standard library tool too.

</details>

### 数学、竞赛与科研反思

**Speaker 1**: 听你说话非常有意思。你既像一个 AI 研究员，又像一个高并发分布式系统专家，同时骨子里完全是一个纯粹的程序员。通常这三类人很少重叠。你正在将原本奔着“成为独立神明”方向发展的 AI，拉回到程序员日常工具的轨道上来。聊聊你个人的经历吧，你是怎么走到这一步的？

<details>
<summary>Original English</summary>

**Speaker 1**: It's so fascinating because you speak like an AI researcher, you speak like a systems person, and you speak like a programmer. Normally these things haven't been overlapping much. You're taking AI, which people have been pushing towards being a sentient being, and you're making it a programmer's tool. Tell us a bit about your personal journey.

</details>

**Speaker 0**: 我在 AI 领域的成长轨迹确实非常非主流。我最初是一名数学竞赛生（Mathlete），还得过不少奖项。我常开玩笑说，我当年的数学水平刚好高到能吸引女孩子的注意。

<details>
<summary>Original English</summary>

**Speaker 0**: My history in AI is somewhat unorthodox. I was a mathlete, an award-winning mathlete. The way I describe it is I was good enough at math to get girls. So that was good.

</details>

**Speaker 2**: 数学好到那种程度吸引到的会是什么样的女孩子？我们的观众必须知道这个秘密！

<details>
<summary>Original English</summary>

**Speaker 2**: And what kind of girls do you get when you're that good at math? Our audience needs to know.

</details>

**Speaker 0**: 哈哈，别去尝试，年轻的朋友们，千万别这么干，根本不值得！保持酷、保持从容、保持有趣就好，别过度补偿。

真说起来，虽然我是数学竞赛选手，但我其实从来没有真正喜欢过数学。我只是在小池塘里当了一条大鱼，原本人生规划就是顺着数学走下去。但我讨厌它，因为竞赛的全部意义就在于赢比赛。

后来我接触到了计算机科学，发现它虽然在逻辑底层和数学很像，但计算机科学很酷、极其有用、充满乐趣。直到今天，我还非常喜欢给人做算法面试。虽然不知道这算不算怪癖，但我确实热爱算法，它能帮我精准评估一个人的技术本质。

我始终认为自己首先是一名**计算机科学家**，其次才是一名研究员。当年真正把我带进机器学习大门的，是我赢下了一场 **Kaggle** 数据科学竞赛。而且我并不是靠什么高深的理论数学获胜的，而是靠纯粹的工程自动化——疯狂堆叠嵌套循环，用系统工程的暴力美学把整个流程自动化到极致，硬生生解出了问题。

那次夺冠之后，我被迫去 **NeurIPS** 大会上做报告。正常人会觉得那是无上的学术荣誉，但我当时特别讨厌去讲台，我只想待在机房里写代码。

<details>
<summary>Original English</summary>

**Speaker 0**: Don't do it, youth! It's not worth it. Just be cool, chill, and interesting, and don't overcompensate. Wow, I can't believe I said that.

So I was a mathlete, but I actually never really liked math. I was just a big fish in a little pond, and math was always the path I was set on. But I hated it because it was always about winning competitions. But then computer science is actually a lot like math, but cool and useful and fun and interesting. I still love giving algorithms interviews. Does it allow me to assess people really well? Yes, it does.

I consider myself to be a computer scientist much more before a researcher, despite my history. What actually got me into it was winning a Kaggle competition—not from sophisticated math, but just automating the hell out of it. More nested loops, solving it like a systems problem. Eventually that got me forced to speak at NeurIPS. Normally an honor, but I hated it because I just wanted to build things.

</details>

**Speaker 1**: 那次是 Kaggle 的专场吗？

<details>
<summary>Original English</summary>

**Speaker 1**: Was that the Kaggle thing?

</details>

**Speaker 0**: 是的。那场比赛的主办方之一是 **Bill Gates** 以及支持向量机（SVM）的联合发明人。那位学术前辈看出我完全不属于典型的象牙塔学术圈，于是收留了我，带我引荐认识了当年几乎所有的顶级 AI 学者。

我的职业生涯就这么被推向了这个方向。后来我参与了 **Jeremy Howard** 的初创公司，去了 **Google Brain** 呆了一段时间。之后我曾短暂“退休”，但闲着无聊实在难受，加上意识到 AI 实际上太有趣了，于是我加入了 **OpenAI**。那段经历非常顺遂，也让我真正看清了很多东西。

<details>
<summary>Original English</summary>

**Speaker 0**: Yes. The host was one of the co-inventors of the SVM, the first author. She basically saw that I was this person who really didn't fit into the research community, and adopted me and introduced me to all the AI people. My career was just pushed into that direction. From there, a startup with Jeremy Howard, then Google Brain for a while, then retired for a bit. Eventually I was tired of not doing anything, realizing AI is pretty damn fun, and I joined OpenAI because of that. It worked out really well.

</details>

### 拒绝造神：务实主义与产业现实

**Speaker 2**: 你刚才提到了一点在今天听来非常罕见的话：“AI 真的非常非常好玩。”

你们团队对 AI 的愿景和整个行业完全不同。你们的信条是：“**我们构建产品，不构建神祇**。”当其他前沿大模型实验室的领头人还在故弄玄虚、试图展现某种不可名状的超级力量时，你的态度却完全相反：我们要创造一个更好的世界，工作不会因此消失，反而会有更多、更好、更有趣的工作涌现出来，每个人都会过得更好。

你完全是发自内心地坚信这一点。在大家看来，TypeSafe 和 Jev 不仅仅是一家商业公司，它代表了一种对未来的积极思潮，而很多传统的 AI 圈内人似乎并不理解这一点。

<details>
<summary>Original English</summary>

**Speaker 2**: You said something that is so unusual in today's world, which is that AI is really, really fun. And the company has such a different domain and view of AI than everybody else. My favorite line you guys say is: "we build PRD, not God." If we had any other big lab leader, even if they had joy, they would cover. Your view is: we're going to create a way better world, there won't be less jobs, there will be more jobs and way better jobs, and everybody is going to have a great time.

Being around you, you clearly believe that. For us, TypeSafe and Jev is more than a company—it's a whole movement towards a positive future that most people in the AI world kind of don't get.

</details>

**Speaker 0**: 没错。那些抱怨“这不就是个分类器吗”的声音，纯粹是学术圈或者算法视角的傲慢。而所有的开发者此时正在为 Jev 狂欢，因为他们终于拿到了能够真正构建现实应用的利器。如果你不走到开发者中间去，你就很难理解究竟发生了什么。

很多人描绘的那种万物皆空的悲观未来，我完全不赞同。我认为这种恐慌很大程度上源于大家喝了“**单一超级大模型**”（Mono-model）的迷魂药，幻想着造出一个统领一切的超级无敌大脑。

<details>
<summary>Original English</summary>

**Speaker 0**: Yes! The "it's just a classifier" complaint is like an ML-level concern, while everyone else is having a Jev party because we can finally do all the things we wanted to do. If you don't talk to developers, it'll be hard to understand what's really going on.

I do think there's a pretty negative world painted that I obviously disagree with. It really comes from this mono-model Kool-Aid that everyone believes in: one big brain to rule them all.

</details>

**Speaker 2**: “一个大脑统治一切”，听起来像魔戒一样不祥。

<details>
<summary>Original English</summary>

**Speaker 2**: Yeah, one big brain to rule them all. Sounds much more ominous.

</details>

**Speaker 0**: 可是，那个所谓的“超级大脑”真的走在解决一切问题的正确道路上吗？现实中哪怕极其基础的日常事务，我们都还没能用它自动化，而这些机械繁琐的事情原本根本不该浪费人类的时间。

当看到科技行业宣传的叙事与现实严重脱节时，我感到由衷的心痛。回到那个核心问题：自动化究竟去哪儿了？AI 明明表现得如此惊艳，商业上也有巨大的财务动力去推进自动化，然而现实呢？你可能会为模型落地寻找各种借口，但我完全不买账。这种承诺与现实的巨大撕裂，正是促使我离开并创办 TypeSafe 的原因。AI 明明蕴藏着如此巨大的潜力，却迟迟无法交付真正的生产力价值，这太令人惋惜了。

所以现在，我们这边是在开开心心地用工程工具搞建设，而外面的世界仿佛分成了两派：一派是用 Jev 快乐落地的务实派，另一派则是陷入末日恐慌或空中楼阁的空想派。

<details>
<summary>Original English</summary>

**Speaker 0**: But is that one brain really on the path to rule at all? We have not automated really basic things that I don't think we want people to be doing. There's lots of really, really basic stuff.

It pains me when the world is discordant with reality. And part of the pain is: where the fuck is all the automation? How can we have AI be so freaking smart, with so much financial incentive to automate stuff, and yet the discordance with reality? The fact that AI has so much potential is what made it really tragic for me that we had not realized this. Now it's a bit of a party for me, but it's like there's the happy AI people on Jev, and the morose AI people who are not.

</details>

**Speaker 2**: 我深有感触。今早我和我们成长基金的合伙人 David 还在聊新工具。问他试了某些新玩意儿没有，他说：“试了，我终于成功把我的《纽约时报》订阅给取消了。”

退订一个报纸居然就是大家津津乐道的成就！这仅仅是冰山一角，现实中还有成千上万琐碎、痛苦但必须完成的任务等待被自动化。

<details>
<summary>Original English</summary>

**Speaker 2**: It is quite a fascinating dichotomy. I'll give you an anti-automation data point: I had a funny conversation this morning with David George from our growth fund. We were talking about new tools, and he said, "I finally cancelled my New York Times subscription." I was like, that baby is notoriously hard to do! It's the very tip of the iceberg of horrible things we need to automate.

</details>

### 从演示Demo到工程确定性

**Speaker 0**: 如果我们想要在智识上保持诚实，真正把自动化作为指引方向的北极星，我们就**绝不能重蹈过去几年 AI 行业深陷其中的反模式（Anti-patterns）——那就是把所有精力都耗费在追逐边缘个案（Outliers）和做酷炫的 Demo 上**。

经常有人兴奋地问我：“你最喜欢的 Jev 使用场景是什么？”我的回答往往让他们失望：“只要它能默默稳定工作，我都喜欢。”我希望它在后台安安静静地跑，哪怕半夜运行也不会触发报警传呼（Pager），让工程师能够闭着眼睛信任它，并在此之上搭积木。

这涉及到一种完全不同维度的“**系统安全性**”（Safety）。如果你希望 AI 能够调度真实世界的系统资源、拥有读写关键资产的权限，你必须获得确凿的系统保证，或者至少是严格的统计学确定性保证，确保它绝不会突然发狂跑偏把生产库删了。

坦白讲，在有人用软件工程的范式把它约束住之前，单纯的大模型在短期内根本不可能单凭自己做到这一点。

<details>
<summary>Original English</summary>

**Speaker 0**: If you're going to be really intellectually honest and in for the north star of automation, we cannot fall into the same anti-patterns AI has fallen into—which is really focusing on outliers and demos.

A lot of people ask me: "what are your favorite use cases?" I want them to work in the background, such that someone can trust them to run and not page them. People can build on top of it, composable. It's a different type of safety: if you want it to run with resources associated with it, with access to things, you need guarantees for that, or at least statistical guarantees so it doesn't go rogue and break things. I don't think raw models will be doing that anytime soon, unless somebody builds the software to do that.

</details>

**Speaker 1**: 这种直觉在你脑海里酝酿了多久？我记得早在 2017 年左右我们就曾交流过这个话题。

<details>
<summary>Original English</summary>

**Speaker 1**: How long has this intuition been percolating? I remember talking to you maybe back in 2017.

</details>

**Speaker 0**: 确实，那次交流时间很长。2017 年我做过一个演讲，主题与此极其相似，题目大概叫《AI 理论上是模块化的，实践中是灵活的》（AI: Modular in Theory, Flexible in Practice），那是非常偏软件工程思维的视角。

但这个思路真正形成质的突破，是在 **ChatGPT** 问世前夕。大约在 2021 年第四季度，当团队发布相关技术成果时，我最初其实并没有非常清晰的直觉。坦率地说，**RLHF**（基于人类反馈的强化学习）所展现出的泛化能力深深惊艳了我。

如果你读过我们当年的论文，会发现它和很多一味证明自己观点的论文不同：我们其实是用严格的科学证伪法，拼命去验证模型究竟是不是在“作弊”（Cheating）。比如我当时最喜欢的一个测试 Query 是：“*为什么在冥想前吃袜子很重要？*”

互联网上根本不存在这种荒谬问题的现成答案。然而模型居然能够给出逻辑严谨、符合人类语法且看似煞有介事的回应。在那一刻，我们团队的所有人都被击中了——它没有作弊，它是真具备某种泛化抽象能力的。

但随后发生的事情彻底让我破防了。我们把技术推向了世界，作为一名坚定的“能力派”（Capabilities-driven），我深度参与了发布流程。在那一刻，我甚至真诚地相信：这个模型大概率已经接近 **AGI** 了！

然而当它真正铺开之后，现实无情地击碎了我的幻想。我整个人陷入了怀疑：“等等，怎么会这样？为什么它解决不了实际工程问题？”

<details>
<summary>Original English</summary>

**Speaker 0**: Yeah, we did talk about that! A fun story about that talk from 2017: my talk had a very similar theme. I think it was called something like "AI: Modular in Theory, Flexible in Practice", which is very software-oriented.

I think this really started right before ChatGPT. Right when we released these things, I was very pleasantly surprised by the generalization capabilities of RLHF, around Q4 of 2021. If you read the paper, unlike other papers trying to prove their point, it is us using the scientific method trying to disprove: is it cheating?

My favorite query was: "why is it important to eat socks before meditating?" We made queries not on the internet, and the models were able to produce plausible human-looking answers. That was the thing that clicked: this is not cheating. Then what really burned me was when we released it, I really thought that model had a decent chance of being AGI. And when it didn't pan out, my whole world came crashing down.

</details>

### RLHF的幻象与AGI的真伪

**Speaker 1**: 原来你也曾坐上过那趟通往 AGI 的狂热列车！

<details>
<summary>Original English</summary>

**Speaker 1**: You were on that crazy train!

</details>

**Speaker 0**: 纯粹的强化学习（RL）在真实环境中并不如想象中具备良好的泛化性，反而是人类对齐（HF）让它看起来无所不能。

在 OpenAI 早期（比如 2020 年左右），大家在内部描绘 AGI 时，往往会用“外星生物般的异质智能”这类辞藻。某种程度上，OpenAI 的文化刻意把 AGI 的定义保持得非常模糊，像一个巨大的帐篷，让不同流派的人都能挤在里面。

但我这个人向来注重细节与实效。我始终认为我们走在一条并不通向通用智能的岔路上。即使按照 OpenAI 自身官方的定义——“**将世界上绝大多数具有经济价值的工作自动化**”，这也完全是可以实现的，但这听起来纯粹就是繁重、琐碎的生产力劳作。

世界上绝大部分工作本质上是高度重复和直白的。要将这些工作外包出去，你需要的是清晰简单的执行指令，是普通人都能掌握的操作流程。而在我看来，现存大模型的智能水平早就足以应对这部分工作了。

我心中一直憋着一口气：既然模型的智力早就够了，为什么我们在产业界却连最基础的自动化都拿不到？

原因就在于整个行业陷入了“**巨大过度承诺，严重交付不足**”（Giant Overpromise, Underdeliver）的恶性怪圈。回过头看，GPT-3 刚问世时其实标定得非常清醒。但由于长期以来全行业都是由人类主观去评估模型有多好，大家把所有的精力都拿去讨好人类“裁判”，拼命优化答题的口吻和聊天体验，而不是去死磕具体的自动化执行率。这就是那块遗失的拼图。

<details>
<summary>Original English</summary>

**Speaker 0**: RL is the thing that doesn't generalize well from what I've seen. In early 2020 at OpenAI, when we talked about AGI, people described it as an alien entity. Part of the culture was that it's intentionally vague—a big tent so everyone can fit inside.

I don't think we're on that path. But I do think that what OpenAI defined as AGI—automating most of the world's economically valuable work—actually sounds doable. There's a lot of work out there that is very rote and simple. To outsource work, you need simple instructions that ordinary people can follow. The intelligence for that has been available in models for quite a while now.

The chip on my shoulder is: why is this not available? The industry bifurcated into overpromising and underdelivering. Because humans evaluate how good models are, we've been optimizing for that human judge instead of the automation part. That has been the missing thing.

</details>

**Speaker 1**: 所以你认为衡量 AI 真正价值的标尺，应该是在多大程度上能够把现实生产中具体的任务自动化？

<details>
<summary>Original English</summary>

**Speaker 1**: So you think the measure we should have is: to what extent can you automate actual productive tasks, instead of overpromising and underdelivering?

</details>

**Speaker 0**: 在我心里，这是检验科幻愿景能否落地的“**煤矿里的金丝雀**”。

你们现在到处宣传前沿数学奥数题被攻克了、两年前 Google 发布的超难专业问答基准（GPQA）被刷通了，但与此同时，我们却连一个得来速（Drive-thru）汽车餐厅的点餐系统都搞不定！这两件事在认知上是严重撕裂的，而很多大模型研究员对此根本给不出合理解释。

<details>
<summary>Original English</summary>

**Speaker 0**: That is the canary in the coal mine for real capability. Are you really telling me that math is solved, GPQA is solved, but we still can't reliably handle a drive-thru order? It's a very hard thing to hold in your head at once, and a lot of people don't have good answers to that.

</details>

**Speaker 1**: 有一种观点认为，现实世界的数据分布与数字文本完全不同：现实世界存在巨大的长尾效应（Heavy Tail）和海量的意外情况，而且我们缺乏现实世界完整的数据分布。大模型之所以只能在数学或代码这种低维流形上称王，就是因为我们在真实工作流上根本没有训练数据。你觉得这个解释成立吗？

<details>
<summary>Original English</summary>

**Speaker 1**: One thought: isn't the real-world distribution different than the digital world? It's heavy-tailed, lots of exceptions, we don't have all the data. Couldn't it be that we're relegated to lower-dimensional manifolds like math or code simply because we don't train on the messy real-world distribution?

</details>

**Speaker 0**: 我并不完全认同单纯的“数据缺失论”。毫无疑问，长尾是客观存在的，否认长尾无异于自欺欺人。但在我看来，解决自动化问题根本不需要把所有极端长尾一下子全包揽下来。我们必须保持极致的务实。

软件工程向来是一门讲求权衡与投入产出比的学科。记得 Perl 语言之父 Larry Wall 总结的程序员三大美德吗？**懒惰**（Laziness）、**傲慢**（Hubris）与**急躁**（Impatience）。所谓程序员的懒惰，就是宁可花十个小时去把一个五分钟的任务彻底写成脚本自动化，只为了以后永远不用重复劳动。

构建自动化必须是一门经济账（ROI）。只要系统变得可自动化，即便很多繁琐工作被自动化了，根据**杰文斯悖论**（Jevons paradox），新的工作形态自然会大量涌现出来。

用客户服务来作为基准：OpenAI 从 2020 年就开始尝试全自动客服，但四年过去了，大企业内部真正跑通的端到端自动化项目屈指可数。现实依然让人大跌眼镜。

<details>
<summary>Original English</summary>

**Speaker 0**: I don't entirely buy the data argument. I believe there's a long tail, for sure. But in my canary-in-the-coal-mine situation, we don't need to automate the whole long tail on day one. We need to be pragmatic.

Building reliable software is an investment. What are the three great virtues of a programmer? Laziness, hubris, and impatience. Laziness is spending ten hours automating a five-minute task so you never have to do it again. It's an ROI decision. And people will invent new kinds of work—hence Jev and the Jevons paradox. But as a benchmark, can we actually automate the stuff that looks like it should be automatable? OpenAI has been trying to automate customer service since 2020, yet inside companies, very little is truly automated.

</details>

### 可靠性的四个层级

**Speaker 1**: 你能帮我们把现在适合自动化的任务分分类吗？

在上一波浪潮中，我们调研过很多做客户支持的公司。企业往往声称：“我们 95% 的咨询都是常规问题，比如修改密码。”但一旦你深入到数据底层，按业务唯一性去去重分析，就会发现真实场景里充满了个案例外，长尾占了 50% 以上。

现在每天都有人给我们发消息：“我又用 Jev 跑通了一个全新的用例！”你在发布之前预料到了如此广泛的使用场景吗？

<details>
<summary>Original English</summary>

**Speaker 1**: Can you classify the types of problems that are ripe to automate now? We've looked at customer support before: companies would claim 95% of incoming calls are routine, like password resets. But when you look at the unique variance, there's a 50% long tail of exceptions. Did you predict the broad range of use cases people are using Jev for today?

</details>

**Speaker 0**: 坦白讲，我完全没有预料到，我感到极其惊讶。如果有人在发布前声称自己预料到了今天的局面，那他一定在吹牛。

谁能料到会出现一个专门面向开发者的“ChatGPT 时刻”？初代 ChatGPT 是面向普通大众的，而 Jev 完全是给开发者使用的。我甚至不知道现在参与 Jev 讨论狂欢的人群里有多少是非技术人员，我都想象不出一个不会写代码的人要怎么直接用 Jev。但哪怕我那些不做技术的朋友，也都在 Twitter 上热烈讨论它的梗和应用。

这背后凝聚着我们数年的心血。我对**可靠性**（Reliability）的在乎程度超乎想象。可靠性正是 Jev 的立身之本。如果不理解这一点，任何竞争对手想要像素级抄袭我们都会举步维艰。

哪怕为系统多争取一个 9 的可靠性指标，对开发者来说都具备极高的生产力价值。它直接决定了原本不可能成立的软件架构能否跑通。我们就像是在把一台工业级的 AI 电动机直接安装到工程师的工作台上，任由他们去驱动自己的机械装置。

<details>
<summary>Original English</summary>

**Speaker 0**: I was extremely surprised; I did not assume this would happen. This launch was not something anyone could expect. ChatGPT was for normal users. I don't even know what percentage of people in the Jev party are developers themselves, but the amount I care about reliability is everything. Reliability is what this thing is.

If you don't understand that, it will be hard to make a copycat. Every 'nine' of reliability is going to be incredibly valuable because it enables completely new applications. We are really getting this electric motor of AI intelligence into people's workstations so they can figure out what to build.

</details>

**Speaker 1**: 在这个语境下，“可靠性”具体意味着什么？是模型的可用性（Uptime/SLA）？还是每次调用必须返回完全一致的结果？还是其他维度的保证？

<details>
<summary>Original English</summary>

**Speaker 1**: What does reliability mean in this context? Is it model availability, or that it returns the exact same thing every time, or something else?

</details>

**Speaker 0**: 它绝不是简单的服务器在线率（SLA），虽然那很重要。

如果对可靠性进行解构，它至少包含以下几个由浅入深的层级：

1. **可用性**（Uptime / SLA）：最基础的基础设施连通性。
2. **确定性**（Determinism）：在相同输入下产生完全一致的输出。确定性在单元测试中极其有用，但在复杂的现实工程中，如果每次生成的数据都带有一个不同的 UUID，虽然严格字面上它不是确定性的，但在**业务功能**上它是等价的。
3. **鲁棒性**（Robustness）：在每一次执行中保持**同等水准的智能**。哪怕面对微小扰动，它不会突然出现灾难性的逻辑断崖。
4. **行为的可理解性**（Predictable Semantic Intelligence）：这是我最看重的高级可靠性。它不要求每一次都输出相同的字符，但它每一次作出的决策必须是**符合人类高级工程师认知的合理推论**。只有达到这种稳定度，开发者才敢把它写入核心业务流，围绕它构建代码防御体系。

对我而言，可靠性的最高荣誉就是：**开发者在为 Jev 编写代码时，甚至不需要先在控制台里反复单条调试 Query，而是可以直接在心流状态中一气呵成完成业务架构**，就像我们今天写标准代码调用成熟的底层库一样。

<details>
<summary>Original English</summary>

**Speaker 0**: It's not just uptime. The second thing is closer to determinism, and the third is robustness—similar intelligence every time. Determinism is useful for unit tests, but think about real systems: if you add a UUID, it's not strictly deterministic, but functionally identical.

Then there is a deeper layer of reliability: it doesn't have to be the exact same tokens every time, but it needs to be *smart* every time. Is this an understandable decision for a human to think of? Because a developer can program around that.

To me, the highest honor of reliability will be when developers can program against Jev without having to test every single example query interactively first—when you're just in permanent flow state writing software, trusting the primitive to behave.

</details>

### 编码Agent与架构控制权

**Speaker 1**: 这引出了一个非常尖锐的问题：如果有了 Jev 这样强大的底层软件原语，那些专注于自动写代码的 **Coding Agent**（如 Devin、Codex 等）的相对价值是不是反而下降了？

试想，你用 Coding Agent 生成了上万行传统样板代码，但因为没有使用 Jev，这套软件在能力上依然是受限的；反之，一个人类工程师即使不用 Coding Agent，只要直接使用 Jev 这一强大原语，就能极其优雅地构建出前所未有的智能软件。

你认为未来的格局是 Coding Agent 成为调用 Jev 的工具，还是人类依然直接把控架构？

<details>
<summary>Original English</summary>

**Speaker 1**: It occurs to me that the value of coding agents might go down if you have a primitive like this. An agent like Codex might build all the software for me, but if it doesn't use Jev, the resulting software is limited. Or a human engineer writes the software without an agent, but using this generalized primitive, making powerful software easily. Do you see coding agents using Jev, or humans staying in control?

</details>

**Speaker 0**: 我现在的日常编码时间没有过去那么充裕了，但根据我的深度使用体验：**现有的 Coding Agent 在语法层面极其出色，但在语义层面表现平平，在软件架构设计上则极其糟糕**。

而架构，恰恰是整个软件工程中最具人类创造力、最核心的部分。

我非常喜欢使用 Coding Agent 来处理繁重的语法拼装。虽然 Jev 作为一个崭新的库，大概率还没有进入现有基础大模型的预训练分布（如果它们已经抓取了我们的私有数据那可太诡异了），但一旦 Jev 进入了它们的知识分布，让 Coding Agent 帮开发者撰写具体的接入语法是顺理成章的。

但关于架构：现在的模型在架构能力上可能也就处于人类第 50 百分位数的普通水平。如果你的项目根本不在乎架构扩展性，只想今晚赶工上线，那么让 Agent 随便搭一个 50 分水准的系统完全没问题。这是一场关于速度与技术债务的工程权衡。

<details>
<summary>Original English</summary>

**Speaker 0**: My experience with coding agents is that they are really good at syntax, really bad at semantics, and incredibly bad at architecture. To me, architecture is the most human, creative part of software.

I love using coding agents. Jev is currently not in their training distribution, but when it is, I see no problem having them write the syntax. But with architecture, models are maybe at the 50th percentile. If you need speed above all, you might accept a 50th-percentile architecture to ship overnight. These are trade-offs for companies to navigate.

</details>

**Speaker 2**: 资本市场对这两种技术路线的反应也非常耐人寻味。此前当纯代码生成 Agent 问世时，整个华尔街都在惊呼“SaaS 毁灭日”，SaaS 公司的估值被砸到谷底；而当 Jev 出现后，所有 SaaS 公司的高管都松了一口气，甚至欢欣鼓舞。

<details>
<summary>Original English</summary>

**Speaker 2**: It's a fascinating market phenomenon: when coding agents came out, people heralded the SaaS-pocalypse, and SaaS multiples dropped. When Jev came out, every SaaS company was like: this is the greatest thing ever.

</details>

**Speaker 0**: 这完全符合逻辑。所谓“SaaS 毁灭日”的底层假设是：软件开发将变得极其廉价，任何系统都可以被轻易复制克隆。

但我认为这种假设只看到了表象。说代码廉价我信，但说复杂的企业级 SaaS 可以被轻易克隆，我是绝不相信的。真正的护城河全部隐藏在底层复杂的系统架构、业务逻辑和数据状态之中。

SaaS 并没有失去对客户的价值，市场的恐慌过度了。在我看来，**现存的成熟 SaaS 企业反而会成为这轮 AI 变革的最大赢家**。

我非常渴望与那些最大、最成熟、甚至在外界看来最乏味的企业级 SaaS 合作。因为他们最清楚客户的真实痛点在哪里、哪条业务工作流最需要自动化。软件从来都是一项预先支出的资本投入（CapEx），他们愿意投入资源让软件体验产生质的飞跃，并且他们拥有直接触达海量终端用户的分发网络。

因此，这绝不是什么 SaaS 灾难日，而是一场“**逆向 SaaS 大繁荣**”（Inverse SaaS-pocalypse）。

<details>
<summary>Original English</summary>

**Speaker 0**: It's quite natural. The SaaS-pocalypse story assumed software is cheap and easy to replicate. I believe the former, but not the latter, because so much happens beneath the hood.

SaaS provides tremendous value; the markets were just scared. SaaS companies will be among the largest winners of the AI wave. I want to work with the biggest, most boring enterprise companies because they are in the best position to know what workflows to automate. Software is a CapEx investment to make customer experience radically better, and they already have distribution to massive user bases. It's going to be an inverse SaaS-pocalypse.

</details>

**Speaker 2**: 传统 SaaS 投入的最大成本，实际上就是获取并服务那些复杂的企业客户。如果他们不再仅仅是在产品侧边挂一个鸡肋的 Chatbot，而是将软件核心功能提升几个数量级，那将是一场彻底的蜕变。

<details>
<summary>Original English</summary>

**Speaker 2**: So much of a SaaS company's capital investment is in acquiring and serving customers. If you can make the software itself way better instead of just putting a chatbot on top, that's a massive transformation.

</details>

### 消灭表单与下一代系统交互

**Speaker 0**: 我有一个甚至不知道算不算不切实际的梦想：**在未来的软件世界里，所有的多选下拉表单和死板的选项框都应该彻底消失**。

今天的很多 UI 界面设计极其滑稽——系统内部明明已经接收到了用户的自然语言意图，却非逼着用户去在几层下拉菜单里点选。这完全是上世纪 80 年代第四代编程语言（4GL）留下的历史包袱。

我坚信“**懂我意图即执行**”（Do What I Mean, DWIM）的理念即将被推向全新高度。最近我看到一个社区用 Jev 构建的非常惊艳的原型：开发者用纯语音控制整台电脑，Jev 在底层毫秒级地实时判断用户当前说的一句话究竟是一个“操作系统控制指令”，还是“正在输入文本的内容”，抑或是“带有格式要求的富文本”。整个界面的交互逻辑被彻底重构了。

<details>
<summary>Original English</summary>

**Speaker 0**: I have a dream: there's a world where multiple-choice forms just disappear. Software today takes natural language and forces users to map it into rigid fields. That's literally from the 1980s 4GL era.

I think "Do What I Mean" (DWIM) is going to the absolute next tier. Someone built a voice-control system with Jev where it was constantly making decisions: is this speech a command, or text insertion, or formatted input? Interfaces are going to completely change.

</details>

**Speaker 2**: 那样的话，我们就真的迈入《星际迷航》（Star Trek）里的计算机交互时代了。

<details>
<summary>Original English</summary>

**Speaker 2**: Then you're at Star Trek.

</details>

**Speaker 1**: 这背后蕴含着极其深刻的技术哲学。

如果今天你单纯用 AI 帮开发者生成代码，大公司内部统计显示，平均一个合并请求（PR）其实也就大约 10 行关键代码。你费尽心思去优化那 10 行样板代码的编写速度，收益其实非常有限。更重要的是，它并没有为软件赋予新的能力，甚至可能因为缺少人工审计而引入隐患。

而 Jev 第一次带来的是一个能够**将自然语言意图直接绑定到确定性状态机**上的全新原生接口。

<details>
<summary>Original English</summary>

**Speaker 1**: There is such a profound intuition here. If you use AI today just to generate software, studies show the average PR in a large company is only about ten lines of code. Automating that is optimizing something minimal, and it doesn't provide new capabilities to the software. Software might actually get worse due to lack of oversight.

With Jev, you have a new primitive: it speaks natural language, it can reason, and it marries that to a deterministic state machine.

</details>

**Speaker 0**: 如果大家能真正意识到这一点，将是对我们团队最高的褒奖。我们的愿景绝不仅仅是做个小工具，而是希望在计算机现有的与非门三态逻辑之外，为整个软件工业注入一种新的“**智能逻辑门**”——就像在代码的关键节点安装微型大脑一样。

我们绝不轻易夸下海口，但我们会为实现这个愿景战斗到底。

<details>
<summary>Original English</summary>

**Speaker 0**: If people take that away, that would be the greatest compliment to what we are doing. Our vision is to expand beyond traditional logic gates into a primitive that has a little brain inside. That is a huge thing for the world. I don't want to overpromise, but I will fight for that.

</details>

### 重建基础设施与长远愿景

**Speaker 1**: 这里依然存在很多技术开放度的问题：比如在涉及真正的系统一致性（Consistency）、持久性（Durability）以及高可靠容灾等硬核系统领域，这种原语究竟能扎得有多深？

目前它处理邮件分类、日志分析、界面路由等任务游刃有余。但在未来，它会演变成一种带有智能的全新数据库体系吗？

<details>
<summary>Original English</summary>

**Speaker 1**: It's an open question: how deep can this get into serious systems problems like state consistency, durability, or strong guarantees? It works great for analyzing logs or driving UI, but over time, does this become like a smart database?

</details>

**Speaker 2**: 甚至去接管全自动空中交通管制系统（ATC）？虽然听起来有点让人害怕，但现实系统确实极其需要升级。

<details>
<summary>Original English</summary>

**Speaker 2**: Or an air traffic control system, which we really need, even if it sounds a bit scary?

</details>

**Speaker 0**: 按照工程规律，我们永远应该遵循“先自动化简单任务，再攻克高危核心任务”的节奏。

但我坚信，一整套基于**概率性编程**（Probabilistic Programming）的新型系统架构时代正在被重新开启。上世纪七十年代，概率程序设计曾经盛行一时，后来因为算力和确定性不足而没落。而今天，我们站在了完全不同的起点上。

需要明确的是，我的工程师底色决定了我是一个极端的务实主义者。我从来不迷信那些所谓的“仿生智能”或者对生物神经网络的浪漫幻想。大自然的生物进化故事往往充满了偶然与低效，真正让工程落地的，是现代系统工程师对分层解耦的极致抽象。

随着算力成本和推理速度的演进，未来的超级系统将在极致复杂的边界上进行精细化权衡：一个轻量快速的模块先给出概率猜测，关键逻辑再由确定性系统托底。这将在系统底层带来不可思议的飞跃。

<details>
<summary>Original English</summary>

**Speaker 0**: Always automate the easy work before the hard work. But I also think there's an entire era of probabilistic programming being reopened.

My brand is pragmatism. I'm not a fan of biologically inspired explanations; they rarely match engineering reality. What actually worked in deep learning was hierarchical feature extraction and solid systems engineering.

As we get lots of intelligence at different cost and speed trade-offs, systems will make incredible trade-offs: an approximate guess to optimize hot paths, backed by formal guarantees. That's going to enable extreme systems capabilities.

</details>

**Speaker 1**: 这意味着一代人终于有机会去**重新构建整套底层软件系统**了。每一次计算范式转移——从客户端到互联网，再到移动端和云，我们都会重构一次系统。

<details>
<summary>Original English</summary>

**Speaker 1**: And the genius is we get to rebuild systems again. We have a new primitive. We did this with the client-server shift, the internet, cloud.

</details>

**Speaker 2**: 尤其考虑到目前日益严峻的网络安全态势，我们可能注定要用这种现代范式把所有关键基础设施重写一遍，才能真正确保系统的内生安全性。

<details>
<summary>Original English</summary>

**Speaker 2**: And because of cybersecurity issues, we probably have to rebuild almost all critical infrastructure to make it inherently safe.

</details>

**Speaker 1**: 当你思考 Jev 的长远演进时，你更多是从应用层、SaaS 分析的视角切入，还是把它看作一种类似于 TCP/IP 的底层协议级基础设施？

<details>
<summary>Original English</summary>

**Speaker 1**: Do you think about Jev more in terms of apps, SaaS, and analytics, or as a fundamental systems foundation like TCP/IP?

</details>

**Speaker 0**: 我的思考方式更接近 **TCP/UDP** 的网络协议内核。UDP 是不可靠的尽力交付，而 TCP 通过确认重传机制构建出绝对可靠的字节流。

我是通过逆向推导得出这个结论的：如果我们相信未来会有彻底基于 AI 的经济大爆发，AI 无处不在，渗透进所有软件。那么请问——**在未来所有对 AI 模型的调用中，究竟有多大比例是直接输出给人类眼球阅读的，又有多少是深埋在系统管道内脏（Guts）中被其他机器调用的？**

答案显然是：绝大多数（甚至好几个 9 的比例）都将是机器之间的深层调用。虽然今天所有的产品创新都从最表层的人机对话开始，但如果你在一开始不把目光瞄准系统的“内脏”，你就永远无法抵达真正的产业自动化深水区。

<details>
<summary>Original English</summary>

**Speaker 0**: The way I think of it is deep into the TCP guts—UDP versus TCP, unreliable versus reliable.

I work backwards from the AI economic revolution: if software has AI all over the place, what percentage of calls to AI will be for direct human consumption, versus deep in the internal guts of software? The overwhelming majority—many nines—will be in the guts of the system. It starts at the surface layer, but if you don't aim for the guts from day one, you'll never truly get there.

</details>

**Speaker 1**: 很多人还没意识到过去 AI 和传统软件之间是多么像“黑夜中交错而过的两条船”。以前就算你想把大模型塞进系统，它也根本不听使唤。软件要求严格的类型和模式，而模型经常随意吐出破坏格式的数据，工程师只能无奈地把它再丢回给人类，或者堆砌一层又一层的 Agent 补丁。

<details>
<summary>Original English</summary>

**Speaker 1**: People don't understand to what extent AI and software were like ships in the night. Even if you tried to embed AI in software, it misbehaved. Software expects a strict schema, and the model would output whatever it wanted, forcing developers to put a human back in the loop or spin up brittle agent loops.

</details>

**Speaker 0**: 这正是为什么过去几年所谓的“Agent 循环”往往是一地鸡毛——因为大家在用混乱的自然语言在黑盒里互相调用。

而 Jev 的核心突破，就是把语言的理解力收敛到了严丝合缝的状态机约束中，让它可以被严谨、可预测地生产化使用。

我不想过度承诺，更不想交付不足。我们团队为这份可靠性付出了巨大的努力，很多本可以提早发布的半成品都被我们按下了。外界可能只看到它很好用，而底层的确定性才是我们最深的壁垒。

我心目中的 AI 乌托邦，就是实现纯粹的“**懂我意图即执行**”（Do What I Mean）。让世间所有的技术工具都像精密机械的齿轮一样顺畅咬合，默默消除摩擦，化为人类隐形的生产力延伸。

<details>
<summary>Original English</summary>

**Speaker 0**: That's why fragile agent loops were necessary before: feeding messy natural language back and forth. But Jev takes that reasoning capacity and bridges it productively into a formal state machine.

I don't want to overpromise. We care deeply about reliability. We could have released this so much sooner, but we fought for that rock-solid foundation.

My AI utopia is about world smoothness: everything moving together like interlinked gears. Imagine if all technology simply did what you meant, reliably and safely. That's the future we are building.

</details>

**Speaker 2**: “懂我意图即执行”，这是一个无比绝妙的结语。非常感谢 Diogo 今天带来的精彩对话！

<details>
<summary>Original English</summary>

**Speaker 2**: "Do What I Mean"—that is a wonderful thought to close on. Thank you so much, this was a truly great conversation!

</details>