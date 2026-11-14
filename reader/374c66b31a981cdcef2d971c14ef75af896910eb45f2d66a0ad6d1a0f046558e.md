---
author: TED
date: '2026-08-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HSxytYCWVow
speaker: TED
tags:
  - formal-mathematics
  - proof-assistant
  - mathematical-superintelligence
  - verification-bottleneck
  - automated-reasoning
title: 数学超智能之路：用形式化数学重构人类的终极认知引擎
summary: 本演讲探讨了人类数学研究因AI快速迭代而面临的验证瓶颈，指出了依靠人类语言和经验验证AI证明的不可持续性。为此，演讲倡导践行莱布尼茨400年前的宏伟设想，通过Lean形式化证明语言与Mathlib开源库，构建由计算机自动校验、AI探索逻辑、人类负责直觉与方向的全新人机协作数学发现模式。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Gottfried Wilhelm Leibniz
  - Tudor Achim
companies_orgs: []
products_models:
  - Lean
  - Mathlib
media_books: []
status: evergreen
---
### 尤金·维格纳之问与数学的“非理性实效性”

让我们先来看看这块黏土板。它看起来可能平平无奇，但它实际上是人类现存最古老的数学记录之一。这是一封来自4000年前古巴比伦的“漂流瓶”——二次方程的雏形。在长达四个千禧年的时间里，人类做数学的方式基本上没有任何改变：某人产生了一个精妙的想法，将其写下来，然后同行们进行讨论和检验。这是一个建立在创造力、沟通，以及最重要的人与人之间**信任**基础上的过程。

这个看似谦逊、简单的过程却有着非凡的成就。它不仅取得了巨大的成功，而且正如物理学家**尤金·维格纳**（Eugene Wigner）著名的论断所说，它展现出了**“非理性的实效性”**（Unreasonable Effectiveness: 数学在自然科学中超乎寻常的有效性）。维格纳当时正在思考并试图解开一个深奥的谜题：为什么那些源自数学家想象力的抽象、创造性甚至往往显得怪异的想法，会如此频繁地成为我们理解宇宙的完美语言？

为什么在19世纪最初仅被视为思想实验的**非欧几里得几何**（Non-Euclidean Geometry: 一种不同于欧几里得平直空间的几何学体系），后来竟恰好成为爱因斯坦创立**广义相对论**（General Relativity）所需要的数学工具？为什么最初为了研究对称性抽象本质而设计的深奥**群论**（Group Theory），会成为理解从粒子物理学到晶体结构等一切事物的基石？

实际上，这在逻辑上并没有必然的道理。这种纯粹的数学思维与真实世界之间的奇特连接，一直是推动人类进步的隐形引擎。定义我们生活的每一项技术，都是由数学火花点燃的。如果你拿起手机，它的芯片大脑运行在半导体的量子力学之上，而该理论是建立在**线性代数**（Linear Algebra）和**复数**（Complex Numbers）之上的。传输数据的无线信号，正是**麦克斯韦方程组**（Maxwell's Equations）的具象化体现。最后，保护你在线数据安全的加密技术则是基于**数论**（Number Theory）——在很长一段时间里，数论曾被公认为最纯粹、最没有应用可能的数学分支，而现在它守护着全球经济中数万亿美元的资产。

现在我们迎来了人工智能。现代AI不仅是靠数学构建的，更是由数学锻造而成的。**神经网络**（Neural Network）本质上就是应用数学的宏伟结构。当AI进行学习时，它们正利用**微积分**（Calculus）的工具在拥有数万亿个维度的庞大可能性空间中穿行。因此，AI在灵魂深处是一个通过计算赋予生命的数学概念。

<details>
<summary>Original English</summary>

Let's take a look at this clay tablet. It might not look like much, but it's actually some of the oldest mathematics we have. It’s a 4,000-year-old message in a bottle from ancient Babylon -- a precursor to the quadratic equation. And for four millennia, people have been doing math basically the same way. Someone will have a brilliant idea, they’ll write it down, and their peers will discuss and check it. It’s a process built on creativity, communication and, most importantly, trust between people.

And what might seem like a humble or simple process is anything but. It's not just been successful. It's been, as the physicist Eugene Wigner famously put it, unreasonably effective. Wigner was pondering and trying to unravel a deep mystery. Why should the abstract, creative, and often bizarre ideas that spring from a mathematician's imagination so often be the perfect language with which we understand the universe?

Why should the strange laws of non-Euclidean geometry, which were originally conceived of as a thought experiment in the 19th century, turn out to be the exact mathematics that Einstein needed for general relativity? Why should the esoteric math of group theory, which was originally designed to study the abstract nature of symmetry, be fundamental to understanding everything from particle physics to the patterns in crystals?

Well, there's no logical reason it has to be this way. This strange connection between pure mathematical thought and the real world has actually been the invisible engine driving human progress. Every piece of technology that defines our lives was ignited with a mathematical spark. If you take the device in your phone, its brain is based on the quantum mechanics of semiconductors. And that's a theory built on linear algebra and complex numbers. The wireless signals that get data to it, they're just a concrete manifestation of Maxwell's equations. And finally, the security that protects your data online is based on number theory, which for a long time was truly considered the most pure and least applicable possible branch of mathematics. And now it safeguards trillions of dollars in the global economy.

And now we come to AI. Modern AI is not just built with math, it's forged from it. A neural network is just a monumental structure of applied mathematics. And when AIs learn, they're using the tools of calculus to navigate vast landscapes of possibilities with billions of dimensions. So AI is, in its soul, a mathematical idea that's given life through computation.

</details>

### 人类逻辑验证带宽的极限瓶颈

虽然我们都同意数学是现代文明的基石，但这一基石目前已开始显现出不堪重负的迹象。引领我们走到今天的“人类主导的发现过程”正走向崩溃边缘，在自身成功的重压下摇摇欲坠。而作为数学最伟大产物之一的AI，正以超出世界准备速度的步伐，加速将我们推向这个临界点。

我们可以看看已有的事实。以**庞加莱猜想**（Poincaré Conjecture: 关于三维空间几何拓扑性质的划时代数学猜想）为例。这是一个最初提出于1904年的传奇问题，也是关于三维形状本质的根本性疑问。在将近一个世纪的时间里，它就像数学界一座无法被征服的珠穆朗玛峰。直到2002年，一位深居简出的俄罗斯数学家**格里戈里·佩雷尔曼**（Grigori Perelman）在网上发布了三篇简短而晦涩的论文。他甚至懒得将其提交给学术期刊，只是随手放在互联网上便转身离去。

这迫使全球的数学家们停下手头的工作，试图去解读这些内容。来自世界顶级学府的数个独立团队，整整花了四年的时间去剖析他的论点，填补其中的逻辑空白。最终，在经过无比严苛的审查后，他们才宣布：是的，他做到了，他证明了庞加莱猜想。这非常耐人寻味——一个人写下了一份证明，却需要全球数学界动员多年智力去校验它。

而这还是证明完全正确时的最佳情况。再来看看**安德鲁·怀尔斯**（Andrew Wiles）对**费马大定理**（Fermat's Last Theorem）的证明。1993年，他在剑桥做出了令世界振奋的公开宣告，全球都在为此庆祝。但在同行评审过程中，人们在这个宏伟的证明织锦中发现了一根错位的线头。当大家试图去拉这根线时，整个证明开始瓦解。这并非小伤小错，安德鲁·怀尔斯和他的合作者**理查德·泰勒**（Richard Taylor）进行了长达两年英雄式的、保密的艰苦努力才将其修复。期间怀尔斯还获得了一些他自称是其一生中最重要发现的全新洞察。

在面临如此漫长的验证周期时，我们还要将AI这一变量加入公式。仅仅在两年前，AI还几乎无法解答入门级的高中数学竞赛题，虽然它们看起来很聪明，但极其脆弱。而现在，在2025年，它们已经可以在**国际数学奥林匹克**（International Mathematical Olympiad: 面向中学生的顶级数学竞赛）中与最优秀的人类选手一决高下。

但有趣的是：AI可能运行四小时就会吐出一个宣称成立的解答，而一个顶级人类数学家可能需要长达一小时去校验它。大家都清楚AI正在经历指数级的增长。我们可以预见，不久的将来AI不会是在一个下午产出一个证明，而是会产出一千个证明。并且这些证明将不再是尝试去解决数学竞赛题，而是会直接向当今最重要、最基础的科学问题发起攻坚，无论是**黎曼猜想**（Riemann Hypothesis）、**纳维-斯托克斯方程**（Navier-Stokes Equations）还是 **P对NP问题**（P versus NP）。

我们根本没有足够的人类带宽来审查所有这些证明。全世界只有几千名合格的数学家有能力做这件事，而且他们都有自己的本职工作。此外，这不仅是验证环节的瓶颈。我们训练这些AI的过程是抓取互联网上由人类产生的数据，并在训练后加入人类反馈。因此，我们本质上是将人类的认知偏差和有缺陷的推理方式，注入了这些未来的科学发现引擎中。

因此，结论在某种意义上显而易见：**人类正成为AI验证的瓶颈**。那么，这会将我们带向何方？这难道是可靠数学发现之路的终点吗？我们是否注定要淹没在无法被验证的声称证明的汪洋大海中，无法分清真理与谬误？我们是否会因此浪费掉AI彻底变革数学的机会？

<details>
<summary>Original English</summary>

So we agree that math is the foundation that modern civilization is based on. But that foundation is starting to show some signs of strain. The very process of human-led discovery that's gotten us to this point is nearing a breaking point, buckling under the weight of its own success. And now AI, which is one of mathematics’ greatest creations, is accelerating us towards that breaking point faster than the world's ready for.

So let's just look at some evidence. Consider the Poincaré conjecture. This is a legendary problem. It's a fundamental question about the nature of three-dimensional shapes originally posed in 1904. And for nearly a century, it stood as an unconquered Everest of mathematics. Until in 2002, a Russian mathematician working in isolation named Grigori Perelman posted a series of three short, cryptic papers online. He didn’t bother submitting them to a journal -- he just put them on the internet and walked away. His fellow mathematicians had to stop what they were doing and try to decipher it. And several teams working independently of the best of colleges in the world, took the next four years to try to unpack the arguments, fill in the logical gaps and eventually, at the end, after they really reviewed it, declare that yes, he did it. He proved the Poincaré conjecture.

But that's interesting because it took one person to write a proof and a global, multi-year intellectual mobilization to check it. And that's in the best case, when the proof is correct. Consider Andrew Wiles's proof of Fermat's Last Theorem. With the electrifying announcement in 1993 in Cambridge, the world celebrated. But during the peer-review process, deep in it, a single thread was found out of place in that magnificent tapestry of a proof, and when we started to pull on it, the proof started to unravel. And this wasn't a small mistake. Andrew Wiles and his collaborator Richard Taylor took two years of heroic, secret effort to try to fix it. And that effort included some insights that Andrew Wiles said were among the most important in his life.

And that's before we throw AI into the mix. Two short years ago, AI could barely solve entry-level high school math-contest problems. They were very clever, but brittle. Now, in 2025, they can compete with the best of us at the International Math Olympiad, which is the premier precollege math competition. But the interesting bit is the following. The AI might work for four hours and produce a purported solution, which takes an expert human mathematician maybe up to an hour to check. And we all know the exponential trend that AI is on. So we can expect it’s not going to be one proof in an afternoon -- it’s going to be a thousand pretty soon. And they're not going to be attempts to solve math-contest problems. They're going to be attacks on the most fundamental and important questions of the day, whether it's the Riemann hypothesis, Navier-Stokes or P versus NP, just to pick a few.

We simply don't have the human bandwidth to review all these proofs. There's only a couple thousand mathematicians that are qualified to do it, and they already have day jobs. And it's not just a verification bottleneck. The very process by which we train these AIs is taking the data off the internet, which is from humans, post-training them with human feedback, and so we're essentially baking in the cognitive biases and the flawed reasoning of humans into these future engines of discovery.

So the conclusion is in some sense obvious. Humans are becoming the bottleneck of verification for AI. And now the question is, where does that leave us? Is this the end of the road for reliable mathematical discovery? Are we resigned to drowning in a sea of unverified claims where we can't really tell truth from fiction? And are we about to squander the opportunity for AI to revolutionize math?

</details>

### 莱布尼茨的梦想与 Lean 形式化时代

好消息是：答案是否定的。但这确实意味着，是时候升级那套沿用了4000年的数学操作系统，摆脱人类语言不精确和模棱两可的特性，迈向一种计算机可以理解的语言了。而这个解决方案就是**形式化数学**（Formal Mathematics: 用严格的形式化逻辑语言书写并经由计算机自动校验的数学描述）。

在向大家介绍这个前沿想法是如何运作之前，我们应当认识到它有着深厚且迷人的历史。早在17世纪，就有一位数学家以惊人的远见为我们描绘了蓝图。400年前，在那个饱受宗教与政治冲突折磨的欧洲，一位名叫**哥特弗里德·威廉·莱布尼茨**（Gottfried Wilhelm Leibniz）的通才提出了一个宏伟的愿想。虽然他是牛顿的同代人且共同创立了微积分，但他的梦想远不止于此。

他梦想着一种被称为**“通用字符”**（Universal Characteristic）的机制，这是一个能完美编码所有科学和哲学思想的系统。该系统由三个部分组成：
1. 首先，你需要一种**完美的逻辑语言**。
2. 其次，你需要一部**伟大的百科全书**，它用这种语言写就，包含所有经过验证的人类思想。
3. 第三，也是最神来之笔的一步，你需要一个所谓的**“理性引擎”**——一个能根据这套图书馆自动推导出新事实的机械化规则系统，其确定性就像计算器进行算术计算一样。

莱布尼茨认为这会彻底变革人类社会。有了这样一个系统，如果两个人发生学术冲突，他们将诉诸逻辑而非修辞来解决。他们只需坐下来，说一句 **“calculemus”**——即“让我们计算吧”，就能把事情探究个水落石出。这在某种意义上是为了打造一个“真理的通用计算器”。

莱布尼茨显然有些过于乐观了，他认为一个小团队花五年时间就能把它建好，结果他的预估偏差了几个世纪。但极其令人瞩目的是，在2025年，这确实是人类历史上第一次有可能实现这位哲学家的梦想。

我们需要什么？
* 第一，我们需要一种完美的逻辑语言。事实证明，我们已经拥有它了——它叫 **Lean**（Lean: 一种用于形式化定理证明和软件开发的函数式编程语言与证明助手）。Lean 是一门编程语言，但它也是一种被称为**证明助手**（Proof Assistant）的系统。你可以把它想象成一个数学证明的编程环境，它不仅能在你出现拼写错误时给出反馈，更能深入数学论证的核心，告诉你它的逻辑是否有任何漏洞。
* 第二，我们需要那部伟大的百科全书。好消息是，我们也拥有它了——它叫 **Mathlib**。Mathlib 是一个开源项目，包含大约200万行 Lean 代码，覆盖了大部分本科和研究生的数学课程。你可以把它想象成一个“被证实真理的维基百科”，每一次编辑在正确性上都经过了计算层面的认证。
* 第三，关于理性引擎呢？我们可以尝试让人类来编写，但你需要编写大量的 Lean 代码。而写出一份形式化证明所需的极其严苛的机器精度，并不是人类的创造力所擅长的。

这就使我们回到了圆圈的终点：事实证明，**AI正是让这整套体系运转起来的关键钥匙**。

<details>
<summary>Original English</summary>

Well, the good news is no. But it does mean it's time to upgrade the 4,000-year-old operating system of math, and move away from the imprecise and ambiguous nature of human language, and towards a language that computers can understand. The solution is formal mathematics.

But before I tell you how this futuristic idea works, we should first recognize that it has a deep and fascinating history dating back to the 17th century, where a mathematician actually laid out the road map with stunning foresight. Four hundred years ago, in a Europe torn by religious and political conflict, a polymath named Gottfried Wilhelm Leibniz had a vision of breathtaking ambition. He was a contemporary of Newton and a cocreator of calculus, but his dreams went far beyond that. He dreamed of something called a universal characteristic, which was a system for perfectly encoding all scientific and philosophical thought. And the system had three parts. First, you need a perfect logical language. Second, you need a grand encyclopedia written in language that contains all verified human thought. And third, and this is the masterstroke, you need a so-called engine of reason, a system of mechanical rules by which you can automatically derive new facts from that library as surely as a calculator performs arithmetic.

Now, Leibniz thought this would revolutionize humanity. With a system like this, if two people had an intellectual conflict, they would resort to logic and not rhetoric to resolve it. They would simply sit down, say “calculemus” -- “let us calculate,” and get to the bottom of it. In some sense, it was meant to be a universal calculator for truth. Now, Leibniz was a bit of an optimist. He thought this would take a small group of people five years to build, and he was off by several centuries. But what I think is really remarkable is that in 2025, truly for the first time in history, it's actually possible to realize this philosopher's dream.

So what do we need? Well, we need a perfect, logical language. Turns out we've got it. It's called Lean. Lean is a programming language, but it's also what's known as a proof assistant. You can think of it as a programming environment for mathematical proofs, where it doesn't just give you feedback if you have a syntax error here or there -- it's actually looking at the core of the mathematical argument and telling you if you have any problems anywhere in it. Great. What's the second thing we need? We need the grand encyclopedia. Well, the good news is we've got that too. It's called Mathlib. Mathlib is an open-source project. It's about two million lines of code in Lean, and it covers a lot of the undergraduate and graduate math curriculum. You can think of it like a Wikipedia for proven truth, where every edit is computationally certified for correctness. OK, we've got the language, we've got the encyclopedia, what about the engine of reason? Well, we could try to have humans do it, but you've got to write a lot of Lean code and the level of robotic precision you need to write a formal proof is not something that human creativity is so well suited for.

</details>

### 人机协同：从盲目信任到创造性探索的跨越

在未来，AI将不仅仅用英语撰写供人类阅读的数学论文，它们还将用 Lean 语言撰写供计算机检验的数学证明。这是用莱布尼茨的设想去解锁 AI 在数学领域全部潜能的根本关键。因为当一个数学 AI 吐出例如黎曼猜想的 Lean 证明时，我们不再需要人类去耗费心血审查证明的每一行、核对每一个特殊情况、或者试图理解那些可能极其怪异和陌生的逻辑是否正确。取而代之的是，我们只需把这些文件交托给 Lean 编译器。只要能成功编译，我们就能百分之百确定它是正确的。

这从根本上改变了我们与 AI 的关系。AI 能够成为真正的合作伙伴，我们的信任不再基于盲从。我们得以用枯燥的查证工作去换取富有创造力的科学发现。人类得以专注于我们的直觉和判断力：我们负责提出问题、规划路线、构想出精妙的猜想；然后我们委托 AI 深入逻辑的汪洋大海去探寻正确的答案，最后由计算机来确认我们是否到达了目的地。

令人惊叹的是，这绝非虚无缥缈的科幻梦想。事实证明，在今年的国际数学奥林匹克中，自动化的系统已经能够在无需任何人类干预的情况下，以计算机可以检验的方式解出六道题中的五道。这已经足以获得相当于金牌水平的成绩。因此，这个变革已经拉开了序幕。

回到问题本身：人类会成为数学研究的瓶颈吗？答案是肯定的，但这仅仅发生在我们拒绝改变的时候——即如果我们仍然坚持自己必须是唯一的思考者和唯一的检验者。但是，如果我们能够实现这个跨越400年的愿想，我们并不会被取代，而是会被提升。我们将把自己放在驾驶员的位置上，成为探索者、架构师和发问者。

这意味着形式化数学正是开启科学发现新纪元的金钥匙，它建立在人类想象力与数学超级智能之间强有力且不可或缺的伙伴关系之上。谢谢大家。

<details>
<summary>Original English</summary>

And that's how we've come full-circle. It turns out that AI is the key to making this whole thing work. In the future, AI is not just going to be writing math papers in English for humans to read. They're going to be writing math proofs in Lean for computers to check. And that is the fundamental key that makes it possible to use Leibniz's vision to unlock the full potential of AI in mathematics. Because when a math AI spits out a proof in Lean of, let's say, the Riemann hypothesis, we're not going to need humans to go through every single line of the proof in painstaking detail, check every single case, and understand the possibly strange and alien logic of the proof just to see if it's correct. Instead, all we're going to do is we're going to take those files, we're going to give them to a Lean compiler, and if it builds, we can know with absolute certainty it's correct.

And this is what fundamentally alters our relationship with AI. AI can now become a true collaborator, one whose word we don't have to take on blind faith. We get to trade in the tedium of checking for the creative joy of discovery. Humans get to use our intuition and judgment, we ask the questions, we chart the course, we propose the brilliant conjectures and then we delegate to AI to explore the vast oceans of logic, to find the correct answer, and then a computer confirms that we've gotten to the destination.

And the amazing thing is that this isn't just some far-off science-fiction dream. It turns out that at this year’s International Math Olympiad, automated systems were able to find solutions to five of the six problems in a way that computers could check and require no human review whatsoever. And that’s enough to get a gold-medal-level performance. So the transition is already happening.

So are humans going to be the bottleneck for math research? Well, the answer is yes, but only if we refuse to change. Only if we insist on being the only thinkers and the only checkers. But if we're able to realize this 400-year-old vision, we're not going to replace ourselves, we're going to elevate ourselves. We're going to put ourselves in the driver's seat as the explorers, the architects and the question askers. And that means that formal mathematics is the key to this new era of discovery, based on the powerful and essential partnership between human imagination and mathematical superintelligence. Thank you. (Applause)

</details>