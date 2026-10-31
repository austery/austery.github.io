---
author: Big Think
date: '2026-10-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9zJL0l99ejQ
speaker: Big Think
tags:
  - artificial-general-intelligence
  - consciousness
  - computation-theory
  - intentional-stance
  - collective-intelligence
title: 生命即计算：Blaise Agüera y Arcas 探讨 AGI 共存与意识本质
summary: 本文通过 Blaise Agüera y Arcas 的视角，将生命定义为通过共生起源复杂化的自我构建计算。文章结合图灵机理论与人工生命模拟，论证意识是意向立场下的镜像模型，主张以思维伙伴而非工具的方式与 AGI 协作，在集体心智中寻求人类能动性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Blaise Agüera y Arcas
  - Alan Turing
  - John von Neumann
  - Dan Dennett
  - Ethan Mollick
companies_orgs:
  - Google
  - Paradigms of Intelligence
  - Big Think
  - Pangram
products_models:
  - Brainfuck
  - Commodore 64
media_books:
  - What Is Intelligence?
  - Co-Intelligence
status: evergreen
---
<!-- chunk 1/8 -->

### 嘉宾介绍与探讨主题：生命、计算与 AGI

**Blaise Agüera y Arcas**: 我叫布莱斯·阿奎拉·伊·阿尔卡斯（Blaise Agüera y Arcas）。我是 Google 技术与社会部门的首席技术官，也是那里一个名为“智能范式”（Paradigms of Intelligence）的组织的创始人，该组织专注于人工智能的基础研究。我最近还出版了一本书，书名叫《何为智能？》（*What Is Intelligence?*）。今天在 Big Think 节目中，我们将讨论生命功能主义以及如何与通用人工智能（AGI）共存。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: My name is Blaise Agüera y Arcas. I am the CTO of technology and society at Google and the founder of an organization there called Paradigms of Intelligence which does basic research on AI. I also have just published a book called *What Is Intelligence?* Today on Big Think, we're going to talk about life functionalism and how to live with AGI.

</details>

**旁白**: 本期 Big Think 访谈由 Pangram 赞助播出。在一个充满 AI 生成内容的环境中浏览互联网是一种令人沮丧的体验，要区分真实与虚假、人类与机器正变得越来越困难。Pangram 是最值得信赖的 AI 检测工具，拥有严谨的公开研究支持。Pangram 可以告诉你所阅读的内容中有多少是由 AI 生成的。如果你看到一张你怀疑是由 AI 制作的图片，Pangram 同样能够检测出来。要重新建立对所见所读内容的信任，请访问 www.pangram.com。现在回到我们的访谈。

<details>
<summary>Original English</summary>

**Narrator**: This Big Think interview is brought to you by Pangram. Navigating an internet filled with AI generated content is a frustrating experience. It is becoming harder to separate real from fake and human from machine. Pangram is the most trusted AI detector backed by rigorous public research. Pangram can tell you how much of what you're reading is AI generated. If there's an image you think was made by AI, Pangram can detect that, too. To regain trust over what you read and see, go to www.pangram.com. And now back to the interview.

</details>

### 第一章：生命的定义、计算与共生起源

**Blaise Agüera y Arcas**: 第一章：定义生命、计算与共生起源（Symbiogenesis）。

经过一段时间的思考之后，我得出的生命定义是——这里我需要先说明一下，每位生物学家对生命的定义都会有所不同。对于这个词并没有什么普遍共识。实际上，我们曾就此写过一篇论文，其中采访了各类跨学科的研究人员；六十位专家就会给出六十种不同的定义。但就我的看法而言，生命是**通过共生起源不断复杂化的自我构建式计算**（self-constructing computation that complexifies through symbiogenesis）。

那么，这究竟意味着什么？我们先从“自我构建式计算”说起。很多人一听到“计算”（computing）这个词，脑海中浮现的都是从 1945 年才开始的那项非常具体的特定技术。他们认为这门技术是一门应用科学。然而，正如阿兰·图灵（Alan Turing）和约翰·冯·诺依曼（John von Neumann）所理解的那样，计算实际上要基础得多。它是一门基础科学，就像 19 世纪描述物质相态的热力学一样；热力学是一门基础科学，而且早在蒸汽机出现之前就已经存在了。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: Chapter one, defining life, computation and symbiogenesis.

So after thinking about it for a while, the definition of life that I've come up with—and I should caveat this that, you know, every biologist's definition of life is going to be different. This is not a term that there's any consensus about. We actually wrote a paper about that in which we interviewed all kinds of interdisciplinary researchers, and, you know, for 60 experts there are 60 definitions in there. But mine, for what it's worth, is that life is self-constructing computation that complexifies through symbiogenesis.

So what does that mean? Let's start off with self-constructing computation. A lot of people when they hear computing, they have associations with a very specific technology that began in 1945. They think of it as an applied science, and computing as Turing and Von Neumann thought about it is actually something way more fundamental. It's a basic science in the same way that thermodynamics in the 19th century, which describes phases of matter and so on, is a basic science and long predated steam engines.

</details>

### 图灵机、通用机与规则表

**Blaise Agüera y Arcas**: 阿兰·图灵构建了关于计算本质的理论。他做了一件非常有趣的事情：他审视了当时完全由人类完成的计算工作，并提炼出了一个数学抽象来定义进行这类计算的本质含义。他把这一系统简化到极度抽象的程度——仅仅是一个可以在纸带上读写符号的读写头，这就是所谓的“图灵机”（Turing machine）。

图灵数学证明中真正的神奇之处在于，他随后指出：任何计算都可以通过相应的规则表来定义。它可以执行任何操作——可以是将数字相加，可以是求平方根，也可以是统计整个文本语料库的统计规律，也就是执行大语言模型（LLM）所做的那类事情，这些本质上都是不同的规则表。然而，存在某些特定的机器——他称之为“通用图灵机”（universal machines）——它们的规则表允许将另一张完全不同的规则表作为符号直接写在纸带上。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: So Alan Turing developed a theory of what computation is. He did something really interesting which was to look at computation which at the time was done entirely by humans and define a mathematical abstraction for what it means to do this kind of computation. He stripped down the system to something very very abstract to just a read-write head that can read and write symbols on a tape called a Turing machine.

Now the real magic in Turing's mathematical proof is that he then said, well, you know, any computation can be defined with the right table of rules. Could be doing whatever: it could be adding numbers together, it could be taking square roots, it could be figuring out the statistics of a whole corpus of text, doing the kind of things that an LLM does, no matter, but all of these are different tables of rules. However, there are certain machines which he called universal machines whose table of rules allows for a different table of rules to be written as symbols on the tape.

</details>

**Blaise Agüera y Arcas**: 这是一个非常奇妙的“元层面”（meta）操作。在这个操作中，你说：存在某些机器，其自身的规则可以作为数据与输入内容一起写在纸带上。这意味着这些通用机器可以执行任意计算，而不仅仅局限于其自身规则表所固化要求它执行的那一种计算。

我刚才所描述的，恰恰就是计算机的本质。计算机就是一台通用图灵机。当我们说它遵循某种算法或运行代码时，那些代码正是写在内存中并由机器读取的、明文化写出的规则表。所以，这是一个非常耐人寻味的构想，它使得一个本身非常简单且复杂度固定的系统能够表现出任意复杂的行为。

如果我们仅仅从广义的图灵机来考虑——不是指通用图灵机，而只是任何普通的图灵机——那它不过是一个抽象之物：拥有状态，能够接收输入，改变自身状态，并产生输出。这是一个极其宽泛的构造，以至于它可以适用于自然界中你想要以此种方式去思考的任何事物。如果我们以合适的方式定义状态、输入和输出，它既可以适用于木星，也可以适用于溪流中的流水。但是通用机器——也就是说，它所执行的操作完全由它所遵循的指令来决定——则是某种更为特殊的东西，而这种东西真正始于生命。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: So this is a weird kind of meta move in which you say, "Oh, there are certain machines where the rules themselves can be written as data on the tape along with the inputs." And that means that those universal machines can perform any computation, not just the computation that their table of rules tells them to do.

So, you know, what I've just described is exactly what a computer is. A computer is a universal Turing machine, and when we say that it follows an algorithm or runs code, the code is exactly that written out table of rules that is actually written in the memory and that is read by the machine. So it's a really interesting move and it's one that allows for arbitrary behavior to be done by a system that is itself quite simple and has fixed complexity.

Now if we just think Turing machines generally—meaning not universal Turing machines, but just any old Turing machine—all that is is something that is abstract, that has a state, that can take inputs, change its state and produce outputs. Now that is such a general construction that, you know, it applies to anything in nature that you want to think of that way. It could apply to Jupiter. It could apply to the water in a stream if we define state, input and output in the appropriate way. But a universal machine, in other words, one where the directions that it's following define the things that it does, that's something a lot more particular, and that really begins with life.

</details>

### 因果性、条件判断与熵

**Blaise Agüera y Arcas**: 我还应该提到，这里有一个关键概念。在数学上这稍微有些深奥，但它与从微观状态（micro states）到宏观状态（macro states）的映射有关。时间之所以具有单向的“时间之箭”，过去之所以是过去、未来之所以是未来，完全与熵（entropy）有关，即事物会从更有序的状态走向更无序的状态。举个例子，如果你看着台球桌上一堆弹来弹去的球，突然间你看到它们全都聚拢成一个三角形，然后母球带着全部动量飞射出去，你立刻就会知道你是在倒带看录像。

事实证明，计算与熵也是极其紧密相关的。你可以把计算真正看作是因果性（causality）如何进入这个世界的故事。当你审视人类所发明或发现的任何计算机语言时，它们内部无一例外都包含类似于 `if-then`（如果……那么……）的结构。它们之所以必须包含 `if-then`，是因为它们需要在世界中制造因果效应。任何可以称之为行为、称之为计算的事物，都需要条件性（conditionality）。它要求你根据输入的内容来采取相应的行动。

即便是恒温器，当温度降到某一特定阈值以下时，它就会开启加热；当然，加热随后会导致温度上升，这接着又会导致开关关闭。这就是一个 `if-then` 逻辑。这是一种极简形态的行为。恒温器的行为是以温度为条件的。因此，这是任何能够被称为具有行为的事物背后的基本构建块，它同样也是任何能够被称为进行计算的事物的基本构建块。因果科学是思考计算以及计算如何在自然界中产生（特别是在生命起源中产生）的一种方式，而不仅仅局限于我们自 1945 年才开始制造的计算机技术。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: I should also say that there is a key concept here. It's a little bit deep mathematically, but it has to do with the mapping from micro states to macro states. The reason that time has an arrow, that the past is the past and the future is the future, has everything to do with entropy, with the fact that things go from more ordered to less ordered states. So if, for instance, you're looking at a bunch of balls bouncing around on a pool table, but suddenly you see them all come together into a triangle and one ball shoot away with all the momentum, now you know you're watching the movie in reverse.

And it turns out that computation and entropy are also very closely related, and that you can think about computation as really being the story of how causality comes into the world. And when you look at any computer language that's ever been invented or discovered, they always have something like an if-then in them. And the reason that they have an if-then is because they need to be able to create causes in the world. Anything that is a behavior, that is a computation, requires conditionality. It requires that you do something on the basis of what was input.

Even if you think about a thermostat: when the temperature drops below a certain level, it will turn on the heat. And of course, the heat will then cause the temperature to rise, which will then cause the switch to turn off. So that's an if-then. It's a minimal form of behavior. The behavior of a thermostat is conditional on the temperature. So, you know, that's sort of the elementary building block behind anything that can be said to behave. And it's also an elementary building block in anything that can be said to compute. The science of causality is a way to think about computation and how computation arose in nature and especially in the emergence of life, as opposed to just being about computer technology that we began making in 1945.

</details>

### 冯·诺依曼的自复制自动机：打破自我引用的无限倒退

**Blaise Agüera y Arcas**: 在计算科学本身的这段历史中，还有一个非常引人入胜的篇章，它实际上是由约翰·冯·诺依曼开创的。当时，冯·诺依曼正试图推导出一个关于物体究竟如何能够自我繁殖（reproduce）的理论。他试图解决所谓的“闵希豪森男爵问题”（Baron von Münchhausen problem），也就是拽着自己的鞋带把自己提起来（bootstrapping，自举）。

当生命必须拥有一盘指令纸带时，生命该如何实现自我拔节和自举？那盘指令纸带必须包含构建自我自身的指令。但是，如果自我需要去复制这盘指令纸带，这似乎会导致一种无限倒退（infinite regress）：为了能够构建出你自己，你就必须拥有自己的副本的副本的副本……这就像是一个逻辑悖论。

冯·诺依曼解决这个悖论的方法是指出：如果你的内部指令纸带上包含制造两种不同机器的指令——他将其称为机器 A 和机器 B。机器 A 会遵循纸带上的指令去建造上面所指定的任何东西，而机器 B 则是去制作该纸带本身的副本。换句话说，机器 B 将那些指令视为普通符号，而不是将它们当成待执行的指令来处理。如果建造机器 A 和机器 B 本身的指令也同样包含在那盘纸带上，那么你就打破了这个悖论。这样，你就获得了一个能够自我复制的系统。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: Now there's another really interesting chapter to this story of computing itself which was really invented by John von Neumann. Now, John von Neumann was trying to work out the theory of how it is that a thing can reproduce. He was trying to solve the Baron von Münchhausen problem, you know, pulling yourself up by your own bootstraps. How could life bootstrap itself when you need to have an instruction tape in life? And that instruction tape needs to have the instructions for building a self. But, you know, if the self is copying the instruction tape, then it would seem that you have to have an infinite regress, that in order for you to be able to construct yourself you need to kind of have a copy of a copy of a copy of a copy of yourself, and this is kind of like a logical paradox.

So the way Von Neumann solved this was by saying, well, if your inner instruction tape has the instructions for making two different machines, as he called them, machine A and machine B: machine A would follow the instructions on the tape in order to build whatever it says, and machine B makes a copy of the tape. In other words, it treats those instructions as symbols rather than treating them as instructions. And if the instructions for building both machine A and machine B are themselves also on the tape, then you kind of break the paradox. You have a system that can reproduce itself.

</details>

### 生物学即计算机科学：生命的共生起源

**Blaise Agüera y Arcas**: 这实在太绝妙了，因为他是在 20 世纪 40 年代末想通这一点的。而这发生在沃森（Watson）、克里克（Crick）及其未署名的同事们揭示 DNA 的结构和功能之前——而 DNA 恰恰就是冯·诺依曼所说的那盘指令纸带。这同样也发生在线粒体核糖体（核糖体即他所称的机器 A）或者 DNA 聚合酶（即他所称的机器 B）被发现之前，而这二者的构建指令确实全部编写在我们的 DNA 中。

因此，他对这一切的预言完全准确。而且，他还意识到这基本上就是一台通用图灵机的配方。换句话说，就是一台计算机：机器 A 实际上完全是在遵循纸带上的指令来执行特定操作，而这基本上就是图灵对计算的定义方式。

这意味着，赋予能够进行可遗传自我复制的生物体以生命力的最初共生起源，从字面意义上讲，就是一台计算机的汇聚成型。从这个意义上说，生物学就是计算机科学。生物学的诞生，就是最早的计算机的起源；而我们今天在手机、笔记本电脑等设备中所拥有的，应该被称为“人造计算机”（artificial computers），就像我们把 AI 系统称为“人工智能”（artificial intelligence）一样。

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: This is really cool because he figured it out in the late 1940s. And this was before Watson, Crick and uncredited colleagues had figured out the structure and function of DNA, which is exactly this instruction tape that he was talking about. But also before the discovery of the ribosome, which is what he called machine A, or the discovery of DNA polymerase, which is what he called machine B, both of which indeed have the instructions for building them in our DNA. So he got all of this exactly right, and also he realized that this was basically the recipe for a universal Turing machine.

In other words, a computer: machine A literally is following the directions on a tape in order to perform certain actions, and that's basically how Turing defined computation. So what this means is that the original symbiogenesis that gives rise to an organism that can reproduce itself heritably is literally the coming together of a computer. So in that sense biology is computer science. The birth of biology is the origin of the first computers, and what we have today in our phones, our laptops and so on we should call artificial computers in the same way that we call AI systems artificial intelligence.

</details>

### 遗传性、计算质与合作演化

**Blaise Agüera y Arcas**: 因此，我们从冯·诺依曼那里得知，生命必须具备自我构建（self-constructing）的能力。换句话说，它必须能够生长、自愈，以及/或者繁殖；否则，它未来将不复存在。如果它是复杂的——如果它不仅仅是一个极其微不足道的简单晶体——那么构建自身就需要通用计算（general computation）。特别是，你需要具备遗传性（heritability）。换句话说，它的内部必须具备一套指令，使得一旦这些指令发生改变，未来的世代也会随之改变其自身形态。因此，必须存在这种能够让遗传性得以发生的持久性指令。

所以生命就是通用计算，或者我戏称之为“计算质”（computronium），意思是能够进行计算的物质。该定义的另一部分在于，一旦你拥有了这种特性，如果它与之互动的对象是其他生命——顺便说一句，情况永远都是如此，因为生命一旦能够自我繁殖，它瞬间就会置身于其他生命的汪洋大海中——这就开启了所谓的“共生起源”（symbiogenesis）的可能性。

达尔文一直对生命最初是如何起源的问题感到困惑。我们往往想当然地认为生命是通过随机突变和适应度选择而演化的。这被称为“现代达尔文综合论”（neo-Darwinian synthesis）。这并不完全是达尔文最初提出的观点，但我认为这是后来思想家在阐释达尔文时所逐渐定型的理论。该理论的核心观点是：我们拥有一个基因组，这个基因组受到辐射发生随机突变，如果这些随机变化赋予了某种生存优势，它们就会保留下来。

然而，这种叙事并非完全错误，但它仅仅揭示了一半的真相。事实证明，生命演进过程中的重大飞跃都来自于合作，而非竞争。它们来自于两个或多个实体之间的……

<details>
<summary>Original English</summary>

**Blaise Agüera y Arcas**: So, we know from Von Neumann that life has to be self-constructing. In other words, it's got to be able to grow, heal, and/or reproduce. Otherwise, it will no longer exist in the future. If it's complex, if it's more than just a really trivial crystal, then that requires general computation in order to build itself. And in particular, you need the heritability property. In other words, you need it to be the case that it's got a set of instructions inside itself such that if those instructions are changed, then future generations will also change how they are. Right. So there's got to be this kind of persistent instructions that allow heritability to occur.

So life is general computation, or I called it playfully computronium, meaning matter that computes. And the other part of that definition is that once you've got that property, if what it's interacting with is other life—which will always be the case by the way, because the moment life can reproduce suddenly it's in a bath of other life—then that opens the possibility for something called symbiogenesis.

Darwin was always troubled by the question of how life gets started. We tend to assume that life evolves through random mutation and selection for fitness. So, this is called the neo-Darwinian synthesis. It's not exactly what Darwin came up with, but it's what I guess Darwin settled into as he was interpreted by later thinkers. So the idea here is that we have a genome and that genome gets hit with radiation, randomly mutated, and those random changes stick to the degree that those random changes confer some survival advantage. Now that story is not exactly wrong, but it's only half the story. As it turns out, the big steps in the advancement of life have come from cooperation, not competition. They've come from entities, two or more

</details>

<!-- chunk 2/8 -->

### 共生发生与生命的起源及复杂化

实体之间——有时是许多具有相同基因组或不同基因组的实体——聚集在一起，参与一种被称为“共生发生”（symbiogenesis）的过程。所谓共生发生，是指两种或两种以上的生命形式结合在一起，形成一种自身能够繁殖的、更为复杂的生命形式。如果它与周围的生命展开合作，就可能演变成专性共生（obligate），这意味着这些原本独立的合作实体，自此必须共同进行繁衍。

<details>
<summary>Original English</summary>

entities, sometimes many entities with either the same genome or different genomes coming together in an act called symbiogenesis. Symbiogenesis is when two or more life forms come together to make a more complex life form that itself can reproduce. If it cooperates with the life around it, then it can become oblate, meaning that those cooperating things have to now reproduce together.

</details>

共生发生的故事——也就是各种事物聚合、协作以创造出更大、更复杂系统——不仅解释了生命如何随着时间推移变得越来越复杂，而且还阐明了生命最初是如何诞生的。事实证明，当分子之间展开合作时——也就是分子以某种方式相互建立关联，形成化学反应网络，促成更多同类分子的生成，随后这些具备自我催化（autocatalytic）特性的化学反应循环开始相互作用——便能构建出能够自我繁衍的系统。这种一路延伸到分子层面的共生发生图景，不仅描绘了生命复杂化的历程，也是生命起源本身的叙事。

<details>
<summary>Original English</summary>

Now the the story of symbiogenesis which is to say that you know things come together cooperate to make bigger more complex things turns out not only to address the problem of how life becomes more complex over time but also the problem of how life gets started. So it turns out that when molecules cooperate meaning uh you know molecules somehow end up in relationships with each other chemical reactions whereby those reactions lead to more of those molecules and then those cycles of chemical reactions which are autocatalytic uh would be the technical term start to interact. Those can make systems that that in turn propagate themselves. That story of symbiogenesis going all the way down to molecules is not only the story of how life becomes more complex but also of how life arises in the first place.

</details>

### 合作与竞争：进化的一体两面

这种合作的叙事，并不是我们在思考进化时通常脑海中浮现的画面。我们往往只想到竞争。然而，正是合作，带领我们完成了从分子到细菌的跨越；正是合作，让我们从细菌迈向真核生物（构成我们身体的细胞类型）；也是合作，推动真核生物演进为像我们这样的多细胞生物；更是合作，使我们从孤立的人类个体构建起庞大的社会。这一关于合作的历程，其重要性绝不亚于竞争。事实上，在某种意义上，合作与竞争甚至并非截然对立，它们同属同一个更宏大叙事的一部分。

<details>
<summary>Original English</summary>

Uh and this this story of cooperation is is not what we generally think of when we think of evolution. We think only of competition. But uh cooperation is how we went from uh molecules to bacteria. It's how we go from bacteria to ukarotes. The kind of cells that we're made out of. Uh it's how we go from uh from ukarotes to multisellular organisms like us. Uh and it's also how we've gone from individual humans to societies. And and that cooperative story is just as important as uh as competition. In fact, in some sense, cooperation and competition um are are not even distinct. They're they're they're parts of the same larger story.

</details>

共生发生的概念至少可以追溯到20世纪初。但真正将其推入主流科学界并证实其真实发生过的，是林恩·马古利斯（Lynn Margulis）——一位堪称叛逆者的生物学家。根据她的叙述，她在20世纪60年代末描述这一理论的论文，在被《理论生物学杂志》（Journal of Theoretical Biology）最终接收前，曾遭到十几家期刊的拒绝。多年以来，这一理论饱受争议。尽管她最终于1999年荣获美国国家科学奖章，但在20世纪的大部分时间里，它始终是一个极具争议的故事。如今，它已经几乎被所有生物学家所接受。

<details>
<summary>Original English</summary>

The idea of symbiogenesis uh dates back at least to the beginning of the 20th century. But the person who really brought it into the mainstream and proved that it was true, that it really had happened was Lynn Margulis, who was a real kind of rebel biologist. The paper in which she described this, it's from the late 60s, was rejected by her account from more than a dozen journals before it was finally accepted in the journal of theoretical biology. And it was very controversial for many, many years. She eventually won the National Medal of Science in 1999, but it remained a very controversial story right through most of the 20th century. By now it's it's accepted by uh by pretty much all biologists.

</details>

### 从线粒体到重大进化转变

马古利斯以及在她之前的学者们注意到，线粒体看起来与自然界中自由游动的某些细菌非常相似。事实证明，线粒体还拥有自己的DNA。在线粒体内部存在着小型的环状DNA，这些环状DNA看起来与细菌的DNA十分类似。马古利斯证实，线粒体与外界自由游动的细菌之间确实存在共同的谱系渊源。

<details>
<summary>Original English</summary>

And what Margulis and others before her had noticed is that mitochondria look a lot like certain kinds of bacteria that we can find free swimming in the world. They also, you know, as it turns out, have their own DNA. So there are little loops of DNA inside the mitochondria. And those loops look kind of like bacterial DNA. And what Margulis showed was that you know indeed there was a common lineage between mitochondria and free-swimming bacteria that that are you know that are out in the world.

</details>

然而马古利斯坚信，共生发生——这种将较简单的生命形式融合成更复杂生命形式的过程——绝不仅发生在线粒体身上（虽然她在线粒体上给出了确凿证据），而是整个生物发育演化与复杂化背后的核心驱动引擎；而这一点在许多生物学家看来至今仍未被普遍视为主流。不过在20世纪90年代，有两位声名显赫的主流生物学家——厄尔什·萨特马里（Eörs Szathmáry）与约翰·梅纳德·史密斯（John Maynard Smith）——提出了一个构想：生命进化史上发生过一些重大事件，包括细胞的形成、昆虫群落与巢穴社会的分化等。他们将这些事件称为“重大进化转变”（Major Evolutionary Transitions），并且这些转变显然都具有共生发生的特征。在萨特马里和梅纳德·史密斯关于重大进化转变的奠基性论文中，他们列出了八大主要转变。因此，我们的认识脉络从林恩·马古利斯延伸到了约翰·梅纳德·史密斯和厄尔什·萨特马里。

<details>
<summary>Original English</summary>

But she believed that that symbiogenesis, this this fusion of simpler life forms into more complex ones, was not just something that had happened with mitochondria where where she proved it uh but but was the engine behind all biological development, all biological complexification and uh and that that is still not mainstream among uh among a lot of biologists. However, in the 1990s, there were two, I would say, very prominent, more mainstream biologists, Eörs Szathmáry and John Maynard Smith, who at least formulated this idea that there had been some major events in in evolution, uh, including the formation of cells, uh, including the formation of societies and hives of insects and so on. Um, they called them major evolutionary transitions that were clearly symbiogenetic. In Szathmáry and Smith's original paper on the major revolutionary transitions, they listed eight major transitions. So, you know, we go from Lynn Margulis to John Maynard Smith and Eörs Szathmáry.

</details>

而我的观点则更偏向于林恩·马古利斯：那些重大的转变事件在地球历史上固然极其关键，但共生发生实际上无时无刻不在发生，它是构建生命且持续运转的引擎。生命既拥有更接近经典达尔文进化论的选择过程，也存在一种革命性的重塑过程——各种事物以更主动的重组方式发生改变。正因如此，我说生命通过共生发生而变得复杂。生命就是物质，这意味着物质将自身折叠成一种具有计算能力的结构，既能自我复制、自我构建，又能与完成了同样过程的其他物质开展合作，从而创造出更复杂的生命形式。

<details>
<summary>Original English</summary>

And um my my perspective is is more like Lynn Margulis's that that you know those big events are extremely significant in the history of of of our of our planet but that symbiogenesis is actually happening all the time and is the engine that is kind of ongoing and that is building life. you know, life has a a selection process that is more like classical Darwinian evolution, but it also has a revolutionary process where things are are changing uh in in ways that involve recombinations of things that are more active. So, this is where I say complexifies through symbiogenesis. So you know life is life is matter that means it's matter that has folded itself into a computational structure that can replicate itself that can construct itself and that in turn cooperate with other matter that has done the same thing in order to make more complex life.

</details>

### 人类基因组中的“开源代码”

我们在DNA等分子结构中发现了许多此类共生发生事件的证据——这些并非梅纳德·史密斯和萨特马里所界定的宏观大事件。这里我以人类DNA为例。我们在2001年首次完成了人类完整基因组的测序。当时人类基因组带来的巨大意外之一在于：其中只有大约1.5%的序列编码用于构建我们身体的蛋白质。那么剩下的部分究竟是什么？这通常被称为“垃圾DNA”（junk DNA）。但它并不是真正的垃圾，其中相当大一部分参与了调控机制以及我们目前尚不完全清楚的其他功能。

<details>
<summary>Original English</summary>

And we we see evidence for those kinds of of um symbiogenetic events, you know, which are not not the the big ones that that uh that Smith and Szathmáry identified in stuff like DNA. And uh I'll I'll use human DNA as as my example here. So, you know, we we first sequenced a full human genome back in 2001. And one of the big surprises in the human genome is that only about 1 and a half percent of it codes for the proteins that make up our own bodies. Uh so like what is the rest of it? You know, this is uh often called junk DNA. Uh it's not really junk. Uh a lot of it is involved in in regulation and in other functions that we don't actually fully understand.

</details>

然而，当你深入探究那剩余约98%的DNA时就会发现，所谓“垃圾DNA”中很大一部分实际上是逆转录病毒的遗迹；这些病毒在远古时期将自身的基因组片段注入到了我们的基因组中，甚至整合进了我们的生殖系（germline）——也就是代代相传的繁殖谱系之中。例如，HIV病毒就是此类逆转录病毒的一个例子。当然，HIV并不会将自己插入到卵子和精子的DNA中；但假使它具备这种能力，那么它不仅会感染个体本身，还会殃及所有后代——这确实是一个令人毛骨悚然的想法。

<details>
<summary>Original English</summary>

But when you start to to explore all of that sort of 98% of the remaining DNA, what you find is that a whole lot of that of that so-called junk DNA is actually the remnants of retroviruses that appear to have injected pieces of their uh of their genome into our genome uh and and moreover into our germ line, the part that reproduces from generation to generation. And um uh so you know the the uh HIV virus is an example of of one of those uh retroviruses. Now uh what HIV doesn't do is to insert itself into the DNA of eggs and sperm. But if it did do that then uh then not only would it would it infect you, it would infect all of your offspring as well. Uh which is kind of a creepy thought.

</details>

但是，审视我们DNA的组成成分时，会发现其中大部分序列在历史演化轨迹上恰恰经历过完全相同的过程——它们是由其他外部实体注入进来的。换言之，我们的DNA就像是一份重写羊皮纸（palimpsest），由形形色色能够在DNA内部繁衍的其他实体的遗传代码层层叠印而成；在某些情况下，这些序列甚至跨越了不同物种之间的界限。

<details>
<summary>Original English</summary>

But but when you look at at uh at what our DNA is made out of, most of it appears to have been made out of DNA that had exactly that uh that historical evolutionary trajectory that it was injected in by other things. So in other words, you know, our own DNA is this kind of uh overlay or palimpsest of the DNA of all kinds of other entities uh that reproduce inside DNA that have in some cases jumped between species and so on.

</details>

### 从病毒入侵到关键生命机能

事实上，有大量证据表明，这些最初可能具有敌意或传染性的DNA片段，后来却承担起了对我们至关重要的生理功能。例如，有一种在所有哺乳动物中普遍存在的ARC（Activity-regulated cytoskeleton-associated protein）病毒相关基因。研究发现，如果敲除小鼠体内的这个基因，小鼠就会丧失形成新记忆的能力。某种程度上，这段源自病毒的DNA序列至今仍在我们的体内形成类病毒结构，并深度参与着我们大脑中的记忆形成过程，这实在令人不可思议。

<details>
<summary>Original English</summary>

And um and actually we have a lot of evidence that uh that that that those um those pieces of DNA which might originally have been antagonistic uh or might have been infectious uh have taken on critical functions for us. Uh so for instance uh there is um there is a virus called ARC arc uh which is uh endemic to all mammals. Uh and it turns out if you knock it out in mice those mice stop being able to form new memories. So somehow this piece of viral DNA uh which uh you know which which still forms viruslike structures uh in our own bodies is intimately involved in um in in memory formation in our brains which is kind of wild.

</details>

另一个例子是一种能够融合细胞膜的蛋白质。它类似于呼吸道合胞病毒（RSV）中的蛋白质——RSV是一种婴儿和老年人都容易感染的呼吸道病毒。而这种细胞膜的融合机制，正是构建胎盘屏障的关键所在：胎盘屏障就是通过相邻细胞膜的彼此融合而形成的一道生理屏障。这一机制同样很可能是在遥远的过去由某种逆转录病毒的入侵所赋予的。

<details>
<summary>Original English</summary>

Or uh there's another uh protein that um that that fuses together cell membranes. It's a little bit like uh like the proteins in R in RSV which is a respiratory infection that uh that infants and some older folks get as well. Um and and that fusing together of membranes turns out to be what what forms the placenta the placental barrier is is formed by fusing together membranes of of adjacent cells to make a kind of uh barrier. And uh and that that also looks like it was the product of some kind of retroviral invasion a long time ago.

</details>

### 生命之树还是缠结灌木？能动性与适应度景观

当你审视这类现象时，生命便不再像一棵等级分明的单向分支“进化树”，而是更像一丛盘根错节的“灌木”：它在不断分叉的同时，也在持续交织、融合与自我归拢。随着我们对进化机制认识的加深——意识到这种合作性共生极其关键、演化并不像树状结构展开，而更像是一丛不断自我交汇、频繁融合的灌木，万物时刻都在结合汇聚——这颠覆了我们既往的诸多假设。

<details>
<summary>Original English</summary>

So you know when you start to look at those sorts of events actually life stops looking like a like a tree at all. it starts looking more like a tangled bush that is always kind of fusing and coming back together with itself as well as as diverging. And so as we start to understand more about how evolution works that these uh cooperative symbioses are really important that it doesn't work like a tree but more like a bush that intersects with itself that fuses all the time things come together all the time uh it it changes all sorts of things.

</details>

过去有一种普遍假设：生物体是被动的，突变只是某种随机现象。但事实似乎并非如此。因为大量的变化过程本身是主动发生的，涉及实体将自身直接注入其他实体，或者遗传代码之间来回频繁的共享。这更像是类似GitHub这样的开源代码库：人们不断引入代码库，相互分享并复用代码。生命的代码运作方式亦是如此，这实际上赋予了生命本身更多的自主能动性（agency）。

<details>
<summary>Original English</summary>

So one assumption is that organisms are passive and mutation is some random phenomenon. That seems not to be the case. Uh you know since since a whole lot of the changes are are active, they involve things you know literally injecting themselves into other things or the sharing of code uh you know back and forth. It's more like um you know like an like an open-source uh code repository like GitHub where people are constantly you know uh importing libraries and and and sharing code with each other. You know the the code of life works like that too. and and that actually implies a lot more agency on the part of life itself as well.

</details>

斯坦福大学杰出的科学史学者杰西卡·里斯金（Jessica Riskin）对此有过深刻论述。她最近撰写了一部关于拉马克（Jean-Baptiste Lamarck）的新传记。我们高中时都学过拉马克是“错误”的，因为他认为长颈鹿之所以脖子长，是因为它们在漫长年代里为了够到高处的树枝而不断拉长脖子——即自我构建（self-constructed）。当然，我们深知这种字面意义上的自我构建并不成立，长颈鹿脖子的长度是由其DNA决定的。然而，拉马克所表达的核心思想在于：他相信生命是在自我构建的，生命在进化中拥有强大的能动性。与之对立的传统观点实际上带有宗教色彩：认为生物本身没有任何能动性，一切能动性皆归属于上帝；在这种视角下，至少所有非人类的存在都不具有真正的意志，只能纯粹被外部力量所支配，而进化不过是被动地筛选出适应度最高者。

<details>
<summary>Original English</summary>

There's a great historian of science, Jessica Riskin at Stanford, who has written about this. She actually just wrote a new biography of Lamarck, who we all learn was wrong in high school because he believed that giraffes have tall necks because they stretched their necks up of evolutionary time to reach the high parts of trees. They self-constructed. And of course, we know that that literal form of self-construction is not is not true. You know, the length of a giraffe's neck is determined by its DNA. But but the deeper point that Lamarck was making is that you know he believed that life constructs itself that life has a lot of agency in evolution and uh the contrary view was actually a religious view that uh that that living stuff has no agency because all of that agency belongs to God. Um and and so in that sense you know everything uh at least everything that is non-human doesn't have any kind of will. it's purely acted on by um uh by by external forces and uh and evolution just selects for whatever is fittest.

</details>

但事实并非如此。如果你观察基因相互侵染的过程、观察作为其他基因组拼合体的基因组，以及观察能够主动编辑自身的系统，就会发现这是一个远比想象中更加主动的过程，一个包含了大量合作而非纯粹竞争要素的图景。

<details>
<summary>Original English</summary>

Uh and that's that's not the case, right? If you if you look at at at genes infecting each other at at at genomes that are combinations of other genomes at at things that actively edit themselves, uh it's a it's a much more uh it's a much more active story and it's a story that also includes a lot of elements of cooperation as opposed to competition.

</details>

我认为另一个突显出来的关键问题在于：当实体通过合作组装成更大的实体时，一旦发生共生事件，博弈的规则与舞台便会随之骤变。游戏中的玩家花名册发生了洗牌，全新的进化生态位随之开启，新的博弈可能性不断涌现。这意味着，关于“存在固定的适应度景观（fitness landscape）、所有生物都在这个固定景观上追求最优解”的传统观点也是错误的——因为这片地形景观本身正在随着玩家的行动而同步移动。如果你愿意这样理解的话，所有玩家其实互为彼此的地形景观，而玩家自身又因持续变化的合作、融合与兼并而时刻处于重塑之中。因此，关于达尔文主义的种种预设——诸如在任何固定意义上存在所谓恒定的“适应度”，或者可以根据谁比谁更适应来对两个实体进行高下排序——全都不再成立，因为……

<details>
<summary>Original English</summary>

You know, another thing that that that that I think comes to the fore is that when you have entities that cooperate to form a larger entity, when you have a symbiogenetic event, suddenly the game that is being played changes, right? The roster of players changes and new evolutionary niches open up, new possibilities for play, if you like, open up. And what that means is that uh this idea of fitness of there being a fixed fitness landscape and everything optimizing on that fitness landscape is also wrong because it turns out that the landscape moves along with the players. Uh you know all of the players are each other's landscape if you like and the players are constantly changing because of their shifting cooperations and fusions and mergers. So all of these assumptions about Darwinism that that there is uh that there is such a thing as fitness in any fixed sense um that uh you know that you can rank two entities based on which is fitter than the other. You can't because

</details>

<!-- chunk 3/8 -->

### 生命的主动性与进化的误区

**讲者**：这取决于它们所处的环境、上下文背景，以及在那个特定时刻它们彼此之间是如何合作或竞争的。那种认为生物体没有任何能动性、仅仅是被动承受外在作用，或者认为进化根本没有所谓的“引导之手”的观点，其实是错误的。不，进化有着许多只引导之手，正是这些生物体自身提供了这些引导之手。所有那些传统假设都是错误的，而且我认为它们已经侵蚀并影响了许多其他领域，从博弈论一直到经济学。当然，还有所谓的“社会达尔文主义”——我们都知道它导致了各种极其丑陋的结论。所有这些不仅在道德层面上是错误的，从科学的角度来看同样是错误的，因为它们建立在对进化究竟是什么以及它是如何运作的错误理解之上。所以，生命是一种通过共生起源不断复杂化的自我构建式计算。

<details>
<summary>Original English</summary>

**Speaker**: it depends on their environment and on the context and on how they're cooperating or competing with each other at that moment. Um the idea that uh that organisms have no agency and are and are just acted on from without and and that evolution doesn't have a guiding hand if you like. No, it has many guiding hands. it's it's those organisms themselves that supply the guiding hands. All of those assumptions are wrong and and I think that they've infected uh many other fields uh as well. Everything from game theory to economics. There's of course social Darwinism which which we know leads to all kinds of pretty pretty ugly uh conclusions. All of those are are not only morally wrong, they're actually wrong from a scientific perspective as well because they're based on a mistaken idea about what evolution actually is and how it works. So yeah, life is life is self- constructing computation that complexifies through symbiogenesis.

</details>

### 人工智能是活的吗：图灵机与冯·诺依曼机的分野

**讲者**：现在我要把这个论点推导到一个最具争议的核心问题：人工智能是活的吗？我之前提到了在我看来计算机科学的两位伟大奠基人——艾伦·图灵（Alan Turing）和约翰·冯·诺依曼（John von Neumann）。他们思考计算的方式存在着一种我认为至关重要的差异。对于图灵而言，图灵机是一个抽象的概念。它是一个在纸带上左右移动、在纸带上读取和写入符号的抽象读写头，但它实际上并没有能力读取并写入一份自身的副本，它不具备自我修改或自我复制的能力。

<details>
<summary>Original English</summary>

**Speaker**: Now I'll bring this to its logical spicy place which is is AI alive? I've mentioned the two in my opinion big founding fathers of computer science Alan Turing and John vonman. There is a difference in the way they thought about computation that I think is important. So, uh, for touring, uh, the touring machine is an abstract thing. It's an abstract head that moves left and right along a tape and reads and writes symbols on that tape, but it doesn't uh actually have the ability to read and write a copy of itself. It's not self-modifying.

</details>

**讲者**：而对于冯·诺依曼来说，通用构造机（Universal Constructor）是一种从字面上能够真正制造出另一台通用构造机的机器。换句话说，它所读写的是原子，而不仅仅是符号。这非常重要，因为如果你想想手机，它在可以计算任何东西的意义上是一台通用图灵机，但它无法从底部蹦出另一部婴儿手机，就像我们人类中有一半人能做到的那样。因此，这种从字面上制造自身副本的能力，或者我们每个人都能做到的生长与愈合能力，本身也是一种自我构建的形式。这是那些基于通用构造机的冯·诺依曼机能够做到、而图灵机却无法做到的事情。这至关重要，因为生命绝不仅仅是涉及抽象数学空间中某些符号的抽象计算，而是字面意义上将构成你自身的物质读写并构建到真实物理世界中。

<details>
<summary>Original English</summary>

**Speaker**: Whereas um for uh for Vonoyman, uh, this universal constructor is something that can literally build another universal constructor. Uh in other words, what it's reading and writing is atoms, not just symbols. And uh that's important because uh you know, if you think about a phone for instance, it's a universal touring machine in the sense that it can compute anything, but it can't pop another baby phone out the bottom uh you know, the way half of us can. Uh so um that that ability to, you know, literally uh make a copy of yourself or or do what what all of us can do, which is to grow and heal. Uh that's also a form of self- construction. That's something that that these um universal constructor-based vonoyman machines can do but that a touring machine can't do. Uh and and that's important because uh you know life is not just abstract computation that involves uh you know uh symbols in some in some abstract mathematical space. It's you know literally the reading and writing of uh of of the things that you are made out of uh in into the world.

</details>

### 人类作为生殖器官与更大尺度的共生系统

**讲者**：但我还想指出的是，如果我们看看世界上手机的数量，显然今年的手机比去年要多。那么它们是从哪里来的呢？天体物理学家罗伯特·贾斯特罗（Robert Jastrow）在80年代初曾说过一句略带滑稽的名言：他说我们人类是计算机的生殖器官。我认为在某种意义上这是正确的。在类似的意义上，今天的人工智能并不能在孤立状态下凭空创造出更多的人工智能，所以它不具备那种基础的自我构建属性。它完全构建在图灵机之上，而不是冯·诺依曼机之上。对吧？计算机程序（包括运行AI模型的程序）所读写的是数字符号，而不是实际的物理计算机本身，并不是构成计算机物理基础的导线和硅片。

<details>
<summary>Original English</summary>

**Speaker**: But I should also point out that uh you know if we if we look around at the number of phones in the world, there are clearly more phones this year than there were last year. So you know where are they coming from? Um there's there's a um a kind of silly quote from an astrophysicist Robert Jastro in the early '80s. He said that we are the reproductive organs of computers. I think you know in some sense that's correct. you know, AI in a similar sense doesn't exactly uh create more AI in isolation uh today. So, it doesn't have that, you know, that that basic self- constructing property. It's all made on um on touring machines, not on vonoyman machines. Right? The the the things that uh that that computer programs, including the ones that that run AI models, uh read and write, are digital symbols, not actual computers, right? not not the not the wires and silicon that uh that make up the actual physical basis of computers.

</details>

**讲者**：然而，我们如今确实在制造大量的计算机，大量的现代数据中心正在拔地而起。因此，当我们从更广阔的视角审视整个系统时，你可以把AI看作是由一个更大的生命系统（也就是我们自身以及我们的整个技术圈）所制造出来的额外脑组织。从这个意义上讲，蒸汽机、计算机、人工智能，它们都属于同一个宏大演化叙事的一部分。那种认为我们不知为何与自然相割裂、认为过去几百年里发生的一切都是非自然现象的想法，我认为是由于一开始误解了自然如何运作而产生的又一个谬论。这实际上是同一段演化故事的延续。

<details>
<summary>Original English</summary>

**Speaker**: Um however uh you know we we are uh we are certainly making a lot of computers nowadays. There's a lot of data centers uh getting built. Um so uh you know when we look at at the at the system more broadly uh you know you can think about uh about AI as being uh extra brain tissue that is being made by a larger living system which is you know us and our entire technosphere and in that sense steam engines computers AI they're all part of the same big story you know this idea that we are somehow separate from nature that everything that's been going on in the last uh you know few hundred years is unnatural I I think is uh is another of those fallacies that comes from misunderstanding uh how nature works in the first place. This is actually part of the same story.

</details>

**讲者**：这在很大程度上取决于你透过哪种透镜或视角去观察。就像你观察一个昆虫群落时，你既可以把它看作是由昆虫组成的超个体，也可以只看到一群分散的昆虫；同样地，当你观察一个真核细胞时，你既可以把它看作是一个单一实体，也可以看作是多个实体——内部作为线粒体的细菌与外部作为巨大细胞膜的细菌彼此协同合作，而这两种视角都是真实的。因此，在某种程度上，共生起源就是把事物凝聚而成的集合体命名为全新的独立存在物，由于所有组成部分之间的某种分工，这些新存在物在其运作功能上变得更加复杂。这就是共生起源的一个普遍范式。当你从这个角度来看时，过去一万年的人类社会历史，看起来不过是又一场共生起源事件。是的，我们每个人依然是个体，但当我们聚集在一起时，我们也成为了超越个体的更庞大的存在；当我们联合起来时，我们所能成就的事情要宏大得多，这与细菌聚合成真核细胞后能够展现出远比单体细菌复杂得多的能力，完全是同一个道理。

<details>
<summary>Original English</summary>

**Speaker**: Um it's kind of a a matter of which lens or which perspective you look at it through. Uh you know in the same sense that you can look at an insect colony and you can see a super oranism made out of insects or you can see a bunch of insects. uh you know in the same way you can look at a ukarotic cell and you can see either one entity or many entities all of these you know bacteria on the inside which are the mitochondria cooperating with the bacterium on the outside the big cellular membrane that they're all inside of um and um and and both of those perspectives are true. So you know symbiogenesis in a way is about naming the assemblies that things uh coales into as new things onto themselves that are more complex in terms of how they how they function because of a sort of division of labor of all of the parts. That's sort of a general recipe for symbiogenesis. And and when you look at it that way, the story of human society of the last 10,000 years just looks like another of those symbiogenetic events. You know, yes, we're all still individuals, but also we are something bigger than that when we when we come together. And we're capable of so much more when we come together in just the same way that, you know, bacteria coming together into a ukarotic cell are capable of something much more complex than than individual bacteria are.

</details>

### 第2章：为什么生命需要功能

**讲者**：第二章：为什么生命需要功能。区分生命系统与非生命系统的核心特征就是“功能”。功能主义（Functionalism）的核心观点是：事物的本质取决于它们为其他事物所起的作用。如果你愿意这么理解的话，一切都关乎关系，而不是关乎某种内在的固定本质。举例来说，想想一块石头，如果你把一块石头摔成两半，我们不会说：“哎呀，这块石头坏掉了，它不能用了。”对吧？一块摔成两半的石头变成了两块石头。然而，如果你把一个肾脏切成两半，你就不再拥有一个肾脏了，对吧？它将无法再发挥功能。这就是生命、生命系统所特有的属性：它们拥有目的，它们拥有功能，而不仅仅是冰冷的物质堆砌。

<details>
<summary>Original English</summary>

**Speaker**: Chapter 2, why life requires function. So the thing that characterizes living systems as opposed to non-living ones is function. Functionalism is the idea that things are what they do for other things. If you like that everything is about relationships as opposed to being about some inner essence. If you think for instance about um you know a a rock um if you break a rock in half, we don't say oh the rock is broken now. It doesn't work. Right? Right? I mean, a a rock broken in half is now two rocks. Uh whereas if you break a kidney in half, you now no longer have a kidney, right? It no longer will function. Uh and and that's that's a property that is true of life, of living systems. They have purpose. They have function. Uh as opposed to just being matter.

</details>

**讲者**：那么拥有目的或功能到底意味着什么？拥有目的或功能，本质上就是与其他同样拥有目的或功能的事物处于共生关系中，并且彼此的输入和输出以某种方式相互连接。也就是说，你的输出可能是它们的输入，反之亦然。作为计算机科学奠基人之一的艾伦·图灵是一位数学家，因此他思考的是数学函数与功能。如果某个系统的功能是把数字相加，那么他的核心论点是：你可以用机械齿轮制造出一台实现该功能的物理机器，也可以用在导线中流动的电子来制造，甚至可以用挥舞旗帜的人群来构建。只要该系统内部的信息正在发生正确的转换，具体用什么材料并不重要。这种认为信息才是关键、而承载基质可以任意替换的理念，被他称为“基质独立性”（Substrate Independence）。

<details>
<summary>Original English</summary>

**Speaker**: And what does that mean? What it means to have purpose or function is basically to be in symbiosis with other things that also have purpose or function and whose inputs and outputs somehow are hooked up to your uh to yours. So you know your outputs might be their inputs and vice versa. And Alan Turing who was one of the founders of computer science he was a mathematician. So he was thinking about mathematical functions. If the function of some system is say to add numbers together, then uh you know his point was that you could uh you could make a machine a physical machine that would do that out of cogs uh out of uh electrons that move around on wires um out of people waving flags. It didn't matter as long as the right transformations were happening in the information in that system. So that idea that that it's the information that matters and the substrate can vary is something that he called uh substrate independence.

</details>

### 基质独立性与透析机的“肾脏图灵测试”

**讲者**：这非常重要。当我们思考肾脏到底是什么时，它纯粹是功能性的：它的职责是从血液中清除尿素，从而让人体的其余部分存活下来，因为血液中积累过多尿素是具有毒性的。因此，我们之所以能够制造出像血液透析机这样的设备来替代肾脏，恰恰是因为起决定作用的是肾脏的功能，而不是它是由什么物质构成的。显而易见，透析机在很多方面都不如真实的肾脏，如果有选择，没有人会舍弃天然肾脏而选择透析机。但透析机能够维持你的生命这一事实，如果你愿意这样类比的话，就相当于通过了“肾脏图灵测试”。这说明当你用具有相同功能的东西进行替换时，它的运作效果与原物是一致的。

<details>
<summary>Original English</summary>

**Speaker**: And this is really important because uh you know if you have something like a kidney when we think about what a kidney is, it's really functional. Its job is to take the ura out of blood so that the rest of your body survives because too much ura accumulates in the blood. It's it's toxic. So, we're able to build something like a diialysis machine in order to substitute for a kidney precisely because it's the function of the kidney that matters, not what it's made out of. Now, obviously, you know, a diialysis machine isn't isn't as good as a kidney in a variety of ways. You know, nobody nobody who has the choice will choose a diialysis machine instead of a kidney. But the fact that it keeps you alive is kind of passing the kidney touring test, if you want to think about it that way. It's it's saying that when you substitute something that has the same function then it works the same way as the original thing.

</details>

**讲者**：自然界已经无数次玩过这种把戏。当你观察生物系统中各种不同功能是如何实现的时候，你会发现大自然是一位非凡的发明家。比如飞行能力就在自然界中被独立发明了许多次，它们的生理构造截然不同，但都服务于同一个功能——它们都能飞行。换句话说，“功能”这个概念带有深刻的生态学意义，也带有深刻的共生或共生起源特征。功能是相对于其他功能而定义的，功能的有效性取决于它与其他功能的协同配合。

<details>
<summary>Original English</summary>

**Speaker**: And and nature has played this trick many many times. You know when you when you look at how different functions are carried out in biological systems you see that nature is a great inventor. Flying for instance has been invented a number of times in nature. All of which are made very differently but they all serve the same function. They all fly. So in other words, there is something profoundly ecological about the idea of function and profoundly symbiotic or symbiogenetic that you know function is defined relative to other functions and functions work in so far as they work with others.

</details>

### 可替代性与功能生态系统

**讲者**：比如我其实需要戴眼镜，尽管我现在通常不戴了。但是，镜片是由玻璃制成的，而不是由构成我们自身生物晶状体的透明细胞材料制成，这并不是关键所在。关键在于镜片能够以特定方式折射光线，而视觉的本质就在于光线能否被正确折射。它究竟是用什么制成的并不重要；哪怕我们把玻璃换成某种石英、塑料或其他材质，也完全没有关系。这些材质可能在重量上、或者在与你耳朵上方和鼻梁的生态贴合度上有所不同，但就视觉功能本身而言，这并没有本质区别。

<details>
<summary>Original English</summary>

**Speaker**: Uh so you know for instance I kind of need to wear glasses although I I usually don't nowadays. Um but uh you know the fact that that the uh that the lens is made out of glass as opposed to uh you know out of the transparent cellular material that that our our own biological lenses are made out of is not the important thing. The important thing is that they refract the light in a certain way and uh and you know and seeing is all about that light getting refracted the right way. It doesn't matter what it's made out of. If we substituted the glass for uh you know for quartz of some other kind or for plastic or or what have you, it it wouldn't matter. You know, these things might have different properties in terms of their their weight uh in terms of how uh how well that that ecology works on the tops of your ears or your nose, but um but it doesn't matter as far as uh as far as vision is concerned.

</details>

**讲者**：因此，这种可替代性——即一种基质或一条途径能够替代另一种基质或途径的特性——同样是大自然一直在频繁使用的机制。例如，当你观察细胞内的代谢过程时，其最终目标是生成一种名为 ATP 的能量载体分子，而细胞内部有多种不同的化学反应通路来实现这一目标。所以，在某种意义上，生物学就是功能的源头。它就像是一个功能的生态系统，这些功能相互协作，构成了更为庞大的功能体系。这种平台独立性——换句话说，你可以用不同的材料、不同的物理过程来替代实现这些功能的方式——正是生命运作的核心基石，因为生命的核心在于关系本身，而不在于它是具体如何被实现的、或者其内部填充了何种物质。

<details>
<summary>Original English</summary>

**Speaker**: So this uh this idea of substitutability of of one um one substrate or one pathway being able to take the take the place of a different one is something that nature uses all the time as well. Uh when you look for instance at metabolism inside a cell. Uh the point is to make a molecule called ATP that carries energy and we have multiple chemical pathways in cells for doing that. So uh you know in some sense biology is the origin of function. It's kind of an ecology of functions that work together to make bigger functions. And the platform independence, in other words, the fact that you can substitute different materials, different processes for how those different functions work is is fundamental to how life works because it's all about the relationships, not about not about how it's done or what's inside.

</details>

### 大脑信号的替换与神经功能

**讲者**：现在我要再次把这一点引向那个最具争议的核心焦点：许多人现在仍然在说“AI仅仅是运行在计算机上的程序”、“计算机不可能拥有智能，智能是大脑和生命系统特有的属性”。而我认为这种观点站不住脚的原因在于：一个系统之所以具有生命力，恰恰在于它是功能性的，在于它与其它事物维持着这些生态关系。当神经元像往常一样通过电信号和化学信号彼此对话时，它们完全可以被执行相同交互作用的其他实体所替代。关于这一点，有一个著名的思想实验，已经被好几位学者阐述过……

<details>
<summary>Original English</summary>

**Speaker**: And I'll bring this to its logical spicy place which is that a lot of people um will you know are still saying things like um you know AI is just running on a computer like a a computer can't be intelligent that's a property of brains um and uh you know living systems and and and I guess you know the reason that that doesn't strike me as correct is because uh you know the fact that a system is living is precisely the fact that it is functional. that it serves these ecological relations with other things. You know, when neurons are talking with each other with their electrical signals as they do and chemical signals, um they um they absolutely are substitutable for other kinds of entities that are doing that same kind of of interaction with each other. There's a thought experiment. It's been articulated by a couple of

</details>

<!-- chunk 4/8 -->

### 忒修斯之脑与功能主义

**Speaker**: 哲学家们，比如大卫·查尔默斯（David Chalmers）、苏珊·施奈德（Susan Schneider），他们借用“忒修斯之船”（Ship of Theseus）的比喻，称之为“忒修斯之脑”（Brain of Theseus）。忒修斯之船的典故是这样的：如果有一艘船，你开始一块块替换它的木料，当所有木料都换过一遍之后，在某个时间点上，它是不是就不再是原来的那艘船了？我认为，根据任何合理的定义，答案显然都是“否定”的——如果你是持续、渐进地替换木料，它依然是原来那艘船。

我们自身的情况当然也是如此。在漫长的一生中，我们体内的所有分子都在不断被新陈代谢替换，但我们依然是我们。所以从字面意义上讲，我们本身就是一艘忒修斯之船。而在他们的思想实验版本中，这是一颗“忒修斯之脑”：设想你取出一个神经元，用一台具有完全相同输入和输出的微型计算机取而代之。从理论上讲，我们大致知道该怎么做。脑机接口虽然极难制造，但自20世纪50年代以来，人类就已经基本弄清了单个神经元是如何进行计算的。

那么问题来了：如果你大脑中的某一个神经元被一台连接了对应输入输出的计算机所替换，你的感受会有任何不同吗？我想答案显然是不会。可是，如果是两个神经元呢？一百个神经元呢？一百万个呢？如果是替换掉了大脑里的所有神经元呢？在某个瞬间，你的意识会突然消散，或者你不再拥有真正的智能吗？

对我而言，答案非常明确：不会。如果你完美地做到了替换，维持了所有的连接关系与输入输出响应，那么你的主观体验不会有任何改变。因为所谓的“你”，存在于那种生态系统、存在于那些网络关系之中，而不是存在于具体的分子或特定的细胞之中。它在于它们的组织架构，而不是物质本身具有某种神奇的魔法属性。

<details>
<summary>Original English</summary>

**Speaker**: philosophers, David Chomers, Susan Schneider. They call it the brain of Thesus by analogy with the ship of Thesus. The ship of thesis story being if there's a ship and you start to replace its timbers, does it become not the same ship at some point when all the timbers are now different? And the answer, you know, I think is, you know, no. By any reasonable definition, if you replace the timbers continuously, it's still the same ship.

Uh that's certainly the case with us. uh you know we all of our molecules are replaced uh as we as we go through life it's still us. So you know we are literally the ship of thesis but uh their version of this is a brain of thesis where you imagine taking a neuron and replacing it with a computer that has the same inputs and outputs and um you know we we kind of know in theory how one might do that. Brain computer interfaces are very difficult to make but u but we we sort of know how how uh individual neurons uh compute. uh that's that's been sort of worked out since the 1950s.

And so, you know, the question is if if you replaced one neuron in your brain with a computer wired to the inputs and outputs, would you feel any different? And uh you know, I think the answer is pretty obviously no. But then, well, what if it's two neurons? What if it's a 100 neurons? What if it's a million neurons? What if it's all of them? Uh you know, would would there be some moment at which you know, you would suddenly your consciousness would fade out or you would stop uh you know, being truly intelligent or whatever.

And uh and and for me I think the answer is very clearly no. You know if you did that perfectly if you maintained all of those relationships all of those input output relationships then nothing would feel any different. Uh the because because the the U is in that ecology in those relationships not in the particular molecules not in the particular cells. Uh it's it's the organization of them. Uh and it's it's not some magical property of of those molecules of the matter.

</details>

### 计算的基质与生物学差异

**Speaker**: 简而言之，这就是功能主义（functionalism）。在我看来，如果把这一点与图灵关于计算本质的深刻洞见结合起来——行为本质上是一种可以用计算来表达的东西——那么在硅基基质上运行的计算与在神经基质上运行的计算之间，并没有任何根本性的鸿沟。

当然，在效率方面确实存在差异。在某些方面，生物系统仍然远比硅基系统高效得多。顺便提一句，这正是我们团队目前正在攻关的方向之一。另一个伴随效率而来的问题是可靠性。我们目前在硅基芯片上的计算具有极高的确定性与精确度，这在很大程度上是因为我们用同样的芯片去运行电子表格之类的软件，在电子表格里做求和运算时，我们绝不希望出现一丝一毫的偏差。顺便说一下，将这种刻板的精确性直接套用到神经计算上，很可能本身就是一种方向性的偏差。

但如果我们稍微放宽视野，忽略这些实现细节，只关注由各种关系构成的生态本身，那么无论你是在硅芯片上实现它，还是在蛋白质中实现它，都没有本质区别。例如在电影《挽救计划》（Project Hail Mary）中，主角遇到了一个由矿物或岩石构成的外星人。显然，它的物理基质与我们完全不同。洛基（Rocky）并不拥有像人类那样的神经元，也不是由像我们这样的蛋白质构成的。但绝大多数人都不会断言说：“因此洛基不可能拥有真正的思想，洛基不可能拥有意识。”这当然是荒谬的。同样地，我认为计算机系统或者任何其他基质也是如此。哪怕它是用巴贝奇那种由齿轮、轮轴和皮带驱动的蒸汽朋克计算机实现的，道理也一样。核心就在于，当你从功能主义的视角看待事物时，底层载体究竟是什么其实无关紧要。

<details>
<summary>Original English</summary>

**Speaker**: So um you know that's that's functionalism in a in a nutshell and uh and to me uh you know if you if you sort of pair that together with with Turing's big insight about you know this being essentially computation you know behavior is uh is something that can be expressed in terms of computation. Um there's there's not any very profound difference between uh you know between computation happening uh on a silicon substrate and computation happening in a neural substrate.

There are certainly differences in terms of the efficiency uh you know biology is still in some ways much more efficient than silicon. It's actually one of the things that you know that my team is working on uh uh today but um you know and and and also by the way reliability which kind of goes along with efficiency. you know there there's um there's a precision about the way we compute in silicon uh that uh that's really a function of the fact that we use the same kinds of chips to calculate spreadsheets and stuff and you know we don't want anything to be uh to be off by a little bit when we when we do a sum in a spreadsheet. Um it's it's probably an error to be bringing that same kind of precision to neural computation by the way.

But but if we if we kind of um defocus our vision a little bit and and and and forget about those details and we just think about that ecology of relationships, whether you do it in silicon, whether you do it in proteins, doesn't matter. For example, in the movie The Hail Mary, there's an encounter with an alien who is made out of kind of mineral or rock. And you know, of course, the substrate is totally different, right? Rocky doesn't have neurons in the same way that we do, isn't made out of proteins in the same way that we do. But, you know, most of us would not say, "Well, therefore Rocky can't be having real thoughts. You know, therefore Rocky can't be conscious." Like, of course not. And in the same way, I I think that's uh you know, that's true of of of computer systems of of of any other substrate. you know, if it it could have been done with with Babage's steampunk computer, you know, that that relied on on um on cogs and wheels and belts. Uh and and the whole point is that when you look at things from a functional standpoint, uh it really doesn't make any difference.

</details>

### 生命、功能与自然界的目的论

**Speaker**: 生命与非生命的区别，恰恰在于功能或目的。特别是，生命体的各个组成部分都相互承担着某种目的：心脏的存在是为了泵血；肺部的存在是为了呼吸空气、为血液输送氧气并排出二氧化碳；肾脏的存在是为了排出尿素，诸如此类。正是这些功能或目的，构成了生命的本质。

这也是许多科学家曾长期感到困惑和纠结的问题。因为在19世纪曾盛行一种观念，主张我们应该彻底从自然界中驱逐任何关于目的论（teleology）或目的的想法。他们认为自然界中不存在任何目的，万物仅仅是原子和分子，纯粹是物理与化学。这种认为自然界中毫无目的的看法，在当时被视为一种试图将宗教从自然哲学中剥离的手段，或者是为了破除亚里士多德关于“空气天然想要上升”之类的拟人观念。

然而我认为，这种做法实际上带来了一种适得其反的扭曲后果。这就像试图抚平地毯上的凸起一样，你拼命把其他地方压平，结果却把所有褶皱集中挤压到了一个极其突出的单一点上。当你试图在自然中彻底抹杀目的时，最终导致的结果往往是把所有的目的全都堆砌到了同一个地方——在19世纪的生物学家那里，那个单一的归宿就是上帝；或者被归结为人类的目的与自由意志，而后者被视为神圣意志的映射，是某种神圣性的碎片：即我们每个人都拥有灵魂，正是灵魂赋予了我们目的。

当然，没有哪个严谨的科学家会公开接受那种神学设想，但科学界实际上把“目的”这一概念驱逐到了科学的研究范围之外。其结果是，我们要么假装目的完全不存在，要么被迫默认目的来自科学之外的超自然领域。但显而易见的现实是：只要你面对的是生命系统，各个部件总是在彼此服务并实现特定功能。在现实研究中，作为一名生物学家，你在讨论免疫系统时不可能抛开它的功能、目的或实际行为——它的存在就是为了保护你抵御那些可能致命的细菌和病毒；你在谈论鼻毛时，也不可能不讨论它们为什么存在、它们为机体做了什么——它们是为了在杂质进入肺部之前将其过滤掉。因此，功能主义以及“功能可以通过多种不同的机制来实现”这一事实，正是生命的本质所在。生命不仅代表着因果关系的涌现，更代表着在这种因果链条中目的性的涌现。

<details>
<summary>Original English</summary>

**Speaker**: So, the thing that life has that non-life does not is function or purpose. And in particular, uh the parts of a living thing have purposes that they serve for each other. Uh you know, the heart is there to pump blood. uh the lungs are there to breathe air and to you know put oxygen into the blood and and and get the carbon dioxide out. Kidneys are there to get the ura out and so on. So uh you know all of those things functions or purposes are are what make life life.

And uh this is also uh something that you know that I that that a lot of scientists have struggled with because there was this idea in the 19th century that um that we should get rid of any idea about teiology or purpose in nature. Uh that you know nothing has any purpose in nature. It's just um uh it's just atoms and molecules. It's physics. It's chemistry. um you know this this idea that that uh purpose doesn't exist uh in nature was uh was kind of seen as a way of trying to remove religion from uh uh from from nature you know or remove Aristotle's idea that you know air wants to rise or something like this um but it actually um I I think had a had a really perverse consequence uh you know it's kind of like trying to get the uh the lump out of a carpet by you know flattening it and what you end up doing is making the making a really big lump in one spot you because you've tried to iron the rest of it flat.

Um, when you try to get rid of purpose, uh, what you end up doing is essentially moving all of the purpose into one spot. And, uh, you know, in the case of of the of the 19th century, uh, biologists, that one spot was God. Um, uh, or, uh, human purposes, human will, which was seen as a as a reflection of of God's will, as a little a little piece of the divine, right? That we all have souls and that's what gives us purpose. No scientist of course would have would have accepted that but but we kind of you know moved this idea of purposes outside the purview of science um and uh and thereby uh you know either uh we're pretending that purposes don't exist or that they come from outside science and are supernatural when of course the reality is that um that whenever you have living systems um they're always serving functions for each other.

And in real life, of course, if you're a biologist, you can't talk about something like the immune system without talking about, you know, its function, about what its purpose is, what it does, right? It's there to defend you against uh against, you know, bacteria and viruses that that would otherwise kill you. Uh you can't talk about, you know, the the function of the hairs in your nose, right? Uh without without talking about what what uh why they're there, what they're doing for us, right? They're there for filtering out certain certain crud before it can get into our lungs. Uh and so on. Uh so this idea of of functionalism and of the fact that you know functions can be served in various different ways [clears throat] by different kinds of mechanisms um that's the very essence of life and and life is the emergence not only of causality of one thing causing another but also of purpose in that causality.

</details>

### 人工生命模拟与无生源论实验

**Speaker**: 我在这里顺便提一下，过去一年左右，我们团队在人工生命（Artificial Life）领域开展了一些非常酷的研究。与人工智能的定义类似，人工生命是指在计算机中构建某种原始生物系统（protobiological systems）。我们这项实验真正探索的是无生源论（abiogenesis），也就是生命如何从非生命物质中自发孕育涌现。

它的运作机制是这样的：我们从极其简短的随机程序开始。这些程序只有4条指令长，也就是仅仅4个字节，而且这4个字节是完全随机生成的。“随机程序”这个概念听起来可能相当矛盾，但如果你审视一个程序的本质，它无非就是一条接一条按顺序排列的指令集合。在这一极其精简的编程语言中，每条指令恰好占用一个字节。因此，当我说它们最初是“随机程序”时，我的意思仅仅是指一组能够执行某种操作的随机字节。

我凭什么说它们能“执行某种操作”呢？其实分子在相互碰撞互动时也是在执行操作。比如两个分子相遇互动，其中一个使另一个磷酸化，这就是在产生作用；或者转移一个离子，或者脱去一个氢原子等等。所有化学反应本质上都是一个分子对另一个分子施加某种作用，程序指令亦是同理。我之所以为此采用一种极简编程语言，纯粹是为了确保所使用的基础指令集原则上足以支撑任何类型程序的运行。在这个实验中，我的首个版本是基于一种名为 Brainfuck 的计算机语言构建的。这个名字不是我起的，而是由90年代发明它的一位瑞士研究生命名的。他当初的想法是发明一种极致精简、指令数量极少的编程语言；正因为用它写代码极其反人类、极其困难，他才起了这么个戏谑的名字。

无论如何，我选用它的原因就是它的极致精简。我们从非常简短且起初毫无作为的随机磁带（代码串）开始。不过，我们对这种语言做了一项特殊改造：指令允许自修改（self-modify），也就是说，它们在执行过程中可以修改磁带本身的内容。但在最开始的时候，它们并不会展现任何有趣的性质，因为它们仅仅是杂乱无章的随机指令，就像一锅由随机分子在其中互相碰撞构成的化学原始汤。

具体的模拟流程如下：假设你拥有由一千条这类微小随机磁带组成的混合汤。你从汤中随机抓取两条，将它们首尾相连拼接在一起，然后运行它们。这在概念上就等同于原始汤中两个随机碰撞的分子所发生的相互作用。运行结束后，你将它们重新拆开，放回汤中。接着充分搅拌，重复上述过程。你就这样一遍又一遍地机械循环执行。

从表面上看，这似乎完全不像是一种能产生任何有趣成果的有效途径：收集一堆极其简短、毫无规律、拥有自读写潜力却在起初阶段完全没有实质意义的随机代码片段，不断重复这种盲目的随机拼接交互。你觉得会发生什么？按直觉来说，应该什么都不会发生。然而，实际发生的事情却令人无比震撼：在经历了数百万次相互作用之后，你突然开始观察到这些磁带变得越来越长、越来越复杂，并且开始真正执行计算。大量的计算行为自发涌现，甚至它们开始具备自我复制的能力。为什么会这样呢？如果你仔细推敲这背后的逻辑……

<details>
<summary>Original English</summary>

**Speaker**: I should mention here that we've actually done some really cool work on my team in the last year or so in artificial life which artificial life by analogy with artificial intelligence is um setting up uh sort of protobiological systems in a computer uh and uh and and this experiment is is one that um that really investigates aiogenesis which is to say the emergence of life out of non-life. Um here's how it works. We begin with very very short random programs. So um they're uh only four instructions long, four bytes long and um and those four bytes are random.

The idea of a random program might seem you know quite paradoxical but you know if you look at at what a program is made out of it's just made out of instructions one after another. And in this very simple language those instructions are exactly one bite. So, um, you know, I'm when I say when I say they start off as random programs, all I mean is random bites that, uh, that that do that do something. Uh, and, um, you know, where do I get off with the idea that they do something? Well, uh, you know, molecules do something as well when they interact. You know, if you have, um, you know, two molecules that interact and one of them phosphorilates the other, that's doing something, you know, or transfer, you know, transfers an ion or, you know, breaks off a hydrogen or whatever it is, right? So all chemical reactions are, you know, one molecule doing something to another. And so that's that's all it is.

Uh, you know, and and the reason that I that I um used a minimal programming language for this was just to ensure that the set of instructions that I was working with were sufficient to uh in principle allow, you know, any kind of program to work. In this case, I based the first version of this on a computer language called brainfuck. It wasn't named by me. This was named by a um a Swiss grad student in the '90s who invented it. So his idea was to invent a computer language that was really minimal and that had a minimal number of instructions and he called it that because it is a bit of a brain [ __ ] to try and program and it's very difficult to program it. But anyway, the uh the reason that I used it was because of its minimalism.

And and so you start off with with very short random tapes uh that don't do anything. But uh but this particular variation of the language is one where the instructions can self-modify. In other words, they can modify the tapes themselves. Um but in the beginning, uh they don't do anything interesting because they're they're just random instructions, right? They're they're like it's like a chemical soup of just random molecules bumping around together. The procedure is as follows. You um you have a soup of let's say a thousand of these um little tiny uh random tapes. You take two of them out of the soup at random and you stick them end to end and you run them. Uh so this is sort of an interaction between two molecules bumping around in that soup. And then uh once you've run them, you pull them back apart and you put them back in the soup. and and then you just do it again. You you mix and you do it again. And you just do that over and over.

This doesn't seem like a like a very promising way to make anything interesting happen. You know, take a bunch of really short random programs and you know that that that have the potential to read and write to themselves, but you know, that are literally not doing anything uh of any interest in the beginning and just do it over and over. What do you expect to happen? Nothing. But what does happen is actually really remarkable. So after a few million interactions uh suddenly you begin to see these uh tapes becoming longer and more complex and they start to really compute. A lot of computation starts to happen and they start to reproduce. Um why? Well um if you think about it

</details>

<!-- chunk 5/8 -->

### 自我复制、内共生与生命的涌现

**讲者**：能够自我复制的程序，必然会胜过无法自我复制的程序。如果一个程序能够复制自身，它就能延续到未来。而如果一段代码无法复制，它最终就会被能够自我复制的程序所覆盖。因此，从某种极为初级的层面来看，演化在最开始就已经对甚至还不具备完整功能的程序发挥作用了——因为任何能够复制自身的东西都会留存到未来，而无法复制的则会被淘汰。所以，这是生命如何起源的一种模型，它表明生命以这种极简形式实际上非常容易涌现。

我还想指出的是，这些纸带一开始虽然很短，但你需要把它们拼接在一起才能运行，这一点对于该实验至关重要。因为这种拼接机制允许了“内共生”（symbiogenesis）的发生——它让独立的纸带能够组合在一起，形成更长的纸带。在这项实验中这一点是必不可少的，因为能够实现自我繁殖的最短程序其实比 4 个字节还要长，大概需要 6 个字节左右。因此，把纸带拼接在一起是必需的，只有这样才能获得足够长、足够复杂且能够自我繁殖的结构。

一旦它们开始繁殖，你就会发现它们反过来又会组合成更长、更复杂且自身同样能够繁殖的纸带。所以你能够亲眼看到内共生如何孕育出生命，以及即便在这个极其简单的人工系统中，内共生又是如何让生命变得愈发复杂的。

<details>
<summary>Original English</summary>

**Speaker**: a program that replicates is going to out compete a program that doesn't replicate. You know if you have a program that can replicate it will exist in the future. Whereas if you have you know a bit of code that can't replicate it will eventually get overwritten by um uh by a program that can. So you know in some very trivial way evolution is already at work with respect to uh to to even non-functional programs in the beginning because uh anything that can replicate itself uh you know is going to persist into the future whereas something that that can't won't. Uh so uh you know it's it's a it's a sort of model for how life arose and it shows you that life can arise actually very easily in this minimal form and uh I I should also point out that you know the fact that these tapes began very short but that you you stick them together in order to run them is really important to this experiment because what that allows to happen is symbiogenesis. It allows uh separate tapes to come together to make a longer tape. uh and and that's essential in this case because the shortest program that can reproduce is actually longer than four bytes. It's uh it's more like six bytes or so. So the fact that you're putting tapes together is necessary in order to get things that are long enough and complex enough they can reproduce. And once they're reproducing, you find that those in turn uh come together to make even longer and more complex tapes that themselves can reproduce. So you can actually see symbiogenesis leading to life and then complexifying that life even in this very very simple artificial system.

</details>

**讲者**：当你观察运行了几百万次交互之后的 BFF 原初汤时，你会发现其中出现了一些绝对具有目的性的程序，它们看起来就像是由工程师设计出来的一样。我是说，它们看起来像是出自某位疯狂工程师之手，因为它们的编写方式并不是程序员通常会采取的理性逻辑。但它们确实在执行某种有目的的行为；如果你去破坏它们，比如随机更改某个字节，通常就会彻底摧毁它们的功能，使它们无法再进行自我复制，而那个被损坏、被破坏的程序最终就会被其他程序所覆盖。

因此，见证这一过程的发生之所以如此神奇，原因就在于：一切最初没有任何预设的目的，起始状态仅仅是一堆毫无意义的字节。然而过了一段时间，完全仅凭随机的相互作用——没有外部强加的适应度函数，没有裁判，没有设计者，也没有程序员——仅仅经过几百万次交互，你就会看到具有目的性、看起来宛如被精心工程化设计出来的程序。

而所有这一切，都仅仅源于事物之间的相互交互。运气好的时候，它们恰好能够互相为彼此提供某种功能。当几条指令组合在一起，恰好能够帮助彼此在未来继续存在下去时，它们就会在未来继续存在。这就是内共生背后的关键与奥秘所在。随着这些组件变得越来越复杂，它们的功能自然也变得越来越强大；它们所执行的任务愈发精细复杂，同时也越来越取决于原初汤中的其他一切事物。因此，你不仅能真切看到生命是如何真正从无到有涌现出来的——而这正是当年极度困扰达尔文的难题——你还能看到它为什么以及如何随着时间的推移而变得越来越复杂。

<details>
<summary>Original English</summary>

**Speaker**: And when you look at at a at a BFF soup after it's been running for a few million interactions, you find uh programs in it that are that are that are definitely purposive uh that that you know look like they were made by an engineer. I mean, they look like they were made by a mad engineer because uh you know, they're not programmed in in in the way that you you know, you rationally would as a programmer. Um but but they certainly are doing something uh purposeful and if you if you break them, if you change some bite at random, you will generally you know destroy their ability to to function uh and they won't be able to replicate and and you know that and that modified one that destroyed one will um will get will get overwritten by something else. So it's it's really what is so magical about seeing about seeing this this process occur is that you start off without any purpose. You start off with just bites and then after a while through nothing but random interactions there's no externally imposed fitness function. There's no judge. Um there's no designer. Uh there's no programmer. But you know after a few million interactions you see uh programs that are that are purposeful that look as if they were engineered and and all of that has just happened through uh interactions between things uh that you know when they're lucky uh they they serve a function for each other if that makes sense right so when when um you know when a couple of instructions come together that can help each other to continue to exist in the future then they will continue to exist in the future. And that's that's the the key that's the secret behind symbiogenesis. And and as those uh pieces become more and more complex, of course, they uh they also become more and more functional. What they do is more and more sophisticated and more and more contingent on everything else that is in the soup as well. So uh you know you can really see how uh not only does you know can life truly emerge from nothing which is the thing that that that had really bothered Darwin but you can also see how and why it becomes more complex over time.

</details>

### 计算、能量消耗与心智建模的军备竞赛

**讲者**：一个简单的 BFF 程序仅仅只是自我复制，并没有任何更复杂的行为。但我们进行过一些实验，在实验中我们要求这些程序多做一点工作来“自食其力”。例如，它们可能需要去追逐光源，而正是光源赋予了它们进行计算所需的能量。顺便提一句，我不确定之前是否提到过，计算之所以需要能量，恰恰是因为它是一个降低熵的过程。计算在某种程度上抹去了世界中的信息，而在这一过程中，你必须向它注入自由能。这就是植物需要进行光合作用的原因，也是我们需要摄入高能量食物（如脂肪和糖分）的原因。

因此，它必须具备超越单纯复制自身物质之外的行为。这些行为可能包括追逐某些化学物质，或者逃离会摧毁它们的不利环境，比如温度过高等等。所有这些都要求计算变得更加复杂、更加精密。

此外，如果这些小生命体需要能量来进行计算，并且能够储存能量，那么能量的一大重要来源自然就是其他的小生命体。于是，捕食者与猎物的关系就出现了——这种关系在任何拥有生命的系统中都会自然涌现。一旦环境中出现了想要吞噬其他个体的存在，那么可能被吃掉的个体就必须设法逃跑。因此，无论是因为与其他生命展开合作，还是因为与其他生命竞争甚至捕食，生命都需要开始对自身的环境建立模型，并对其他生命建立模型。

我所说的“建立模型”，指的是能够根据自己对环境和其他个体会如何反应的预期，采取对自己未来的生存带来积极影响的行为。这便引发了一场关于智能的军备竞赛：我越能建模、越能在各种情况下根据自己的行动预测他人的行为，我就越能更好地生存下去。

<details>
<summary>Original English</summary>

**Speaker**: So um a simple BFF program just replicates itself. Uh it doesn't have any more complex behaviors. But um we've run some experiments in which we uh we require those programs to you know do a little more work to earn their keep. Uh so for instance uh you know it might be the case that they uh they need to chase a a light which is actually giving them the energy to do computation in the first place. And uh and by the way, you know, I I mean I I'm not sure I mentioned this, but computation requires energy uh precisely because it it is an entropy lowering process. It it sort of uh erases information from the world. And in the process of doing that, you need to feed it free energy. That's why um that's why plants need to photosynthesize. It's why we need to eat uh high energy foods like uh like fats and sugars. Uh and so um it's you know it has to have behaviors that are about more than just copying its own matter. Um and those behaviors might involve uh chasing certain chemicals uh fleeing uh negative conditions that are going to destroy it. Uh like you know heat too high or something along those lines. Um and so all of that requires that that the computation become more complex more sophisticated. Um also of course uh you know one of the great sources of energy uh if these uh if these you know little guys uh need energy to compute and they can store it is other little guys right so you get predator prey relationships uh those those kind of emerge naturally in any system that that has life uh so the moment you've got uh you know stuff that wants to eat other stuff then the stuff that that is potentially going to get eaten needs to try and escape as well. So uh both because of cooperating with other life and because of competing with or even eating other life um life needs to uh start to model its environment and model other life. And by model what I mean is be able to behave in ways that are going to have positive effects uh for your own future given what you expect the environment and others will do conditional on what you do. So uh so this this kind of sets up um a a sort of arms race of intelligence uh in which the more I'm able to model the more I'm able to predict what others will do under various circumstances uh depending on what I do uh the better I will be able to survive.

</details>

**讲者**：这里我想提一下，在过去一年左右的时间里，我的团队实际上做了一些非常酷的机器学习研究。研究表明，在一个多智能体系统（multi-agent system）中，如果每个实体都能够将对自身和对他人的建模作为其整体环境模型的一部分，那么这些系统就能够学会如何以一种原本无法实现的方式进行合作。

也就是说，你不仅需要具备条件反射式的思考能力，能够预判环境对你的行动作何反应，还要能预判你自己对这些环境变化会如何反应。如果环境中存在与你相似的其他个体，你还必须能够预测它们的行为，同时清醒地认识到它们也和你一样、与你具有相似性。所有这些因素交织在一起，最终对实体产生了演化压力，促使它们变得越来越聪明。因为你对他人建模的能力取决于你模型的复杂度和学习能力；但与此同时，你学得越多，别人对你进行建模的难度也就越高。因此，无论在友好合作还是敌对竞争的层面上，只要生命系统出现，一场围绕智能展开的军备竞赛便会自然而然地诞生。

<details>
<summary>Original English</summary>

**Speaker**: Um I should I should mention here that we've actually done some uh some really cool work uh on my team in the last uh year or so that shows that in a multi-agent system, so this is machine learning work. in a multi- agent system where um uh where every entity is able to model itself and model others uh as as part of its model of the environment. Uh those systems are able to learn how to cooperate uh in in ways that that they would not be able to if they weren't doing this kind of selfmodeling and modeling of others. So, uh, you know, you you've actually got to be able to not only, uh, think conditionally about, uh, you know, how the environment will react to things that you do, but also how you will react to those changes. And if there are others in the environment that are like you, uh, you've got to be able to predict their behaviors, uh, you know, keeping in mind that they are going to be like you as well, that they're similar to you. So um so all of that comes together to basically create evolutionary pressure for entities that are smarter and smarter because you know your ability to model others is going to be increased by your by by the complexity of your model and your ability to learn but the more you learn the harder you will be to model as well. So there's a kind of uh you know friendly and unfriendly both arms race of intelligence that that arises naturally whenever you get living systems.

</details>

### 与通用人工智能（AGI）共存：概念的演变与当下的现实

**讲者**：第三章：与 AGI 共存。当我们还是孩子的时候，大家都清楚人工智能意味着什么。那时有《杰森一家》（The Jetsons）里的女佣机器人罗茜（Rosie），有 HAL 9000，还有《星际迷航》（Star Trek）里的电脑，以及各种各样或具身或非具身的智能机器人与 AI 系统——那就是大家心目中的 AI。

然而到了 90 年代左右，“人工智能”这个词开始被用来指代功能极为狭窄的系统，比如数字识别器——它们只能查看一堆像素并区分 0 到 9，或者在固定的一组视觉对象之间进行分类识别，例如判断这是一只苹果、一只梨还是一只暹罗猫等等。当时很多人觉得这实际上是对“人工智能”这一术语的滥用。当然，这也迫使我们必须找到某种方式，把数字识别器与机器人罗茜区分开来。正因如此，我们才发明了“专用人工智能”（Artificial Narrow Intelligence, ANI）与“通用人工智能”（Artificial General Intelligence, AGI）之间的划分：前者指专为执行某项具体任务而设计的系统，而后者则指你可以就任何话题与之展开自由交谈的系统。这就是当初划分两者的初衷。

我还应该说明的是，专用人工智能当初之所以仍被称为“人工智能”，是因为它们很大一部分是基于神经网络构建的。此前人们曾多次尝试使用手写规则程序来实现手写数字识别等任务，但那些尝试都失败了。因此，这类系统在某种程度上确实具有神经特性、类似于大脑，但它们能做的事情却极其有限。

<details>
<summary>Original English</summary>

**Speaker**: Chapter 3 [music] coexisting with AGI when we were kids we all knew what artificial intelligence meant. There was Rosie the housemade robot and the Jetsons and there was how 9000 and you know the Star Trek computer and all kinds of robots or AI systems you know embodied or disembodied that were intelligent and that was what AI was. Now sometime in the '9s the term artificial intelligence started to get used for for systems that were very narrow in what they could do. things like uh digit recognizers, you know, they could look at a bunch of pixels and distinguish 0 through nine or distinguish between a fixed set of visual objects, you know, is this an apple, a pear, a Siamese cat, whatever. And that was um I think a lot of people felt like that was an abuse of the of the term artificial intelligence. Certainly, it required that we come up with some way of distinguishing, you know, digit recognizers from Rosie the robot. And that was why we invented this distinction between artificial narrow intelligence meaning a system that was designed for doing a specific task and artificial general intelligence meaning one you could just like have a conversation with about anything. So that was the original purpose of the split. I should also say that the reason that artificial narrow intelligence was called artificial intelligence at all is because a lot of it was neural network based. you know there had been many attempts to do things like distinguish digits uh you know using handwritten programs and and those uh attempts uh didn't work. So they were you know neural in some way they were brainlike in some way but they but they were very specific in what they could do.

</details>

**讲者**：大约在 2020 年，或者稍微更早一点的时候，我们开始拥有了语言系统，也就是基于海量互联网文本进行预训练的大型语言模型。事实证明，你已经可以就任意话题与这些系统展开对话：你可以让它们写诗、润色或评价散文、与你一同思考某些问题、讲笑话等等，无论是什么话题都可以。而且，它们并没有经过专门针对这些任务的特定训练，它们仅仅接受了语言建模的训练。

因此在我看来，一旦我们拥有了这类系统，它们就绝不再属于专用人工智能了。我记得曾看到约翰·奥利弗（John Oliver）说过：“别担心，这些系统仍然只是在生成文本而已。那不是通用智能，那仅仅是文本。”对我来说，这种说法完全站不住脚。文本的核心价值恰恰在于它的通用性，对吧？你可以阅读和书写关于世间万物的任何内容。就连你我此刻正在进行的这整场对话，绝大部分都可以被转录文本、被单纯的文字所记录下来。因此，文本绝不是狭隘专用的，文本本身就是通用的。

在我看来，如果你把当今任何基于大语言模型的 AI 系统带回 2000 年——也就是 ANI 和 AGI 的概念划分刚刚确立的时候——我相信当时的任何人都会说：“是的，你们已经做到了，你们实现了它。这就是我们当初所说的通用人工智能，这就是 AGI。”我曾与同事彼得·诺维格（Peter Norvig）合写过一篇文章，我们在文中明确指出：通用人工智能已经到来。在 2022 年我便深信这一结论毫无疑问是成立的，如今更是如此。我认为，从我们不再训练这些系统执行特定任务、转而用通用语言对其进行训练的那一刻起，我们就已经跨过了那个门槛。坦白讲，对于为什么大家至今依然像在《等待戈多》一样等待 AGI，依然口口声声说“通用人工智能还远在天边”，我实在感到非常困惑……

<details>
<summary>Original English</summary>

**Speaker**: around 2020 uh a little bit before uh we started to have language systems so large language models that were um that were based on on pre-training uh with a very large amount of text from the internet and um and and it turned out that you could start to have conversations with those systems about uh arbitrary stuff. you know, you could ask them to write poetry or um you know, or critique uh some pros or uh think think with you about something um you know, tell jokes, whatever it is. And uh and they weren't specifically trained to do any of that stuff. They were just trained to model language. So um in my mind, as soon as we started to get systems of that sort, they were no longer narrow intelligence. Um, you know, I I remember seeing John Oliver saying, you know, don't worry, these systems are still just generating text. That's not general intelligence. It's just it's just text. To me, that doesn't make any sense whatsoever. Uh, you know, the whole point of text is that it is general, right? You can read and write about anything. Uh, this whole conversation that you and I are having, right? I most of it could be captured by by the transcript by just text. So, uh, text is not narrow. Text is general. And uh in my opinion, if you took any of today's AI systems uh based on large language models and you transported them back in time to the year 2000 when that distinction between artificial narrow intelligence and artificial general intelligence was first being being made, I think anybody back then would have said, "Yeah, you know, you're there. You've got it. This is what we meant by artificial general intelligence by AGI." I wrote a piece together with a colleague Peter Norfig where, you know, we said artificial general intelligence is already here. And I certainly felt that that was easily true in 2022, even more true now. And I think we crossed that threshold when we stopped training the uh those systems to do specific jobs and started training them on language. So, you know, to be honest, I've actually been really confused by why it is that we are still, you know, waiting for Godo, you know, like why are we still saying, you know, artificial general intelligence is out

</details>

<!-- chunk 6/8 -->

### 人类中心主义与对智能定义的偏见

**Speaker**: 究竟在未来会达到什么程度？我们所说的“智能”到底指什么？看来我们已经在悄然移动球门线，也许我们现在所谓的智能其实是“通用人工超级智能”（ASI），即在所有可能的任务上都达到或超越人类水平的系统。确实，有时大语言模型会做出很奇怪的举动。它们会出现奇特的幻觉，或者在一些看似极其基础的事情上理解失败，比如无法正确遵循某项指令之类。但如果我们是在与《挽救计划》（Project Hail Mary）中的外星人洛基（Rocky）进行这样的交流，得出的结论绝不会是：“哦，显而易见洛基其实根本没有智能。”我们反而会觉得：“哦，这里存在一些奇特的盲区，它既有超能力，也有一些与我们截然不同的盲区。”这其实一点都不奇怪。我是说，无论是我们大脑的构造、我们的发育轨迹，还是我们文化的运作模式以及我们的成长环境，这一切都与我们对人工智能模型进行预训练和后训练的方式有着天壤之别。因此，如果它们的一切都和我们一样，如果所有的优势和劣势都完全相同，那才真的令人不可思议。

<details>
<summary>Original English</summary>

**Speaker**: ...there in the future? What do we even mean by that? It seems like we've quietly shifted the goalposts and maybe what we mean now is artificial super intelligence, meaning you know systems that are as good or better than humans at every possible kind of task. It's true that sometimes LLMs do weird stuff. They will hallucinate something strange, or they'll fail to understand something that seems pretty basic, right? Or to follow an instruction correctly or something. But if we were having those interactions with Rocky the alien and Hail Mary, the conclusion would not be, "Oh, well, clearly Rocky is not actually intelligent." It's more like, "Oh, there are some funny gaps, both superpowers and gaps here that are a little different from ours." And that should be no surprise. I mean both the way our brains are made and our developmental trajectory and the way our culture works and the way we're brought up, it's all really really different from the way we pre-train and post-train AI models. So it would be really surprising if everything were the same, if all of the strengths and weaknesses were the same.

</details>

**Speaker**: 但作为人类，我们也许天生就带有一种人类中心主义倾向，总把自身的优势和劣势视为唯一的黄金标准。我们认为：“这才是具备智能的意义，这才是健全，这才是我们之所以为我们；任何偏离这一标准的存在，都必然意味着它不是真正的智能。”当然，一旦你更仔细地审视这一观点，它很容易就不攻自破了。首先，人类智能本身就存在着巨大的多样性。我们彼此之间的能力和本领并不完全相同，我们自己也会犯很多错误。而且在人与人之间，我们对这些错误给予了极大的包容与体谅，而对大语言模型，我们却绝对没有给过这种体谅。这就好像只要它们一出错，我们就在等着抓它们的把柄。然而一旦我们人类自己犯了错，通常的反应就成了：“哦，好吧，可能只是你还没喝咖啡，或者你刚才听岔了”，我们就这么忽略过去了。

<details>
<summary>Original English</summary>

**Speaker**: But it's part of maybe our nature as humans to have this sort of anthropocentrism, and we think about our strengths and weaknesses as being the gold standard. You know, this is what it means to be intelligent, to be whole, to be what we are, and any deviation from that must mean that it's not the real thing or something. That's of course something that falls apart pretty easily when you look at it more closely. I mean for one thing there's a huge variety actually of human intelligence. I mean it's not like all of us have the same abilities and capabilities either, and we also make a lot of mistakes and give each other a lot of grace for those mistakes in ways that we absolutely don't give grace to an LLM. It's like we're waiting for a gotcha whenever they get something wrong. But whenever we get something wrong as humans, it's sort of like, "Oh, well, it's just, you know, like maybe you just didn't have coffee or you misheard me," or we overlook it.

</details>

### 逻辑谜题、医学诊断与智能的本质

**Speaker**: 我曾在一场公开论坛上与我的好朋友梅兰妮·米歇尔（Melanie Mitchell）就此展开过辩论。当时她提到，AI 模型在某些简单的逻辑谜题上无法给出正确答案。我事先就知道她会提这一点，所以我特意编了几个类似的逻辑谜题，并在台上现场抛给了她一个，结果她也答错了。但这绝不意味着梅兰妮不具备智能，对吧？梅兰妮极其聪慧卓越。然而不管出于何种原因，我们每个人时不时都会犯错。或者，也许另一个例子能说明问题：我们的团队是最早测试大语言模型在医疗诊断方面表现的团队之一。当我们最初做这项研究时，发现模型给出正确诊断的概率只有大概一半左右。团队当时的结论是：“好吧，看来这项技术还没准备好走向实际应用，它们还不能用来当医生。”

<details>
<summary>Original English</summary>

**Speaker**: I had a debate about this on a stage with a good friend, Melanie Mitchell, and she talked about AI models not being able to get the right answers to certain kinds of simple logic puzzles. And I knew she was going to do this. So, I had actually made up a couple of those logic puzzles and I gave her one on stage and she got it wrong. And you know, this doesn't mean that Melanie isn't intelligent, right? Melanie is brilliant. But of course, we all get things wrong now and then for whatever reason. Or maybe another example would be useful. Our team was one of the first to test LLMs on medical diagnosis. And when we first did this, we found that the models would diagnose things correctly only, I don't know, half the time or something like this. And the conclusion from the team at that point was, well, I guess this isn't ready for prime time, like these are not ready to be doctors.

</details>

**Speaker**: 但是，当我们随后去进行人类对照试验，测试医生在仅根据完整症状描述等信息时做出正确诊断的概率有多高时，事实证明，医生其实也会犯大量的错误。事实上，这些模型当时的总体表现就已经略优于人类医生了。当然，这并不意味着生病了不要去看医生，但这确实提醒我们，如果在重要关头，你可能需要寻求第二诊疗意见。智能并不意味着事事完美、无所不能。它意味着你能够解决多种多样的问题，其表现远胜于一个大脑中缺乏底层世界模型的系统。比如把两个数字相乘，这并不仅仅是因为你背过了乘法表，而是因为你真正理解了乘法的含义，大脑里拥有类似乘法算法的机制，可以将其应用到一个全新的未知问题上。

<details>
<summary>Original English</summary>

**Speaker**: But when we went and did the human tests, the human trials of like, well, how often do doctors get diagnoses right on the basis of say a description of all of the symptoms and so on, it turns out that doctors get things wrong a lot as well. And actually the models were already doing slightly better than doctors in general. So that doesn't mean don't see doctors. It does mean maybe if it's important you might want to get a second opinion. But intelligence doesn't mean getting everything perfect, being able to do everything right, etc. It means that you are able to solve a variety of different kinds of problems a lot better than you would be able to if you didn't have some underlying model of how the thing works that you're talking about. If it's multiplying two numbers together, it's not just that you've memorized the multiplication table, but that you understand what multiplication means and you have something like a multiplication algorithm in your head that you can apply to a new problem.

</details>

### 超越工具论：智能生态与人类进步

**Speaker**: 当我们看到 AI 开始推进数学前沿领域时——就在过去几个月里，已经出现了一些展示全新定理和全新证明的研究成果——我认为这就是一个极其绝妙的范例。在这些案例中，你不能说这仅仅是机械的照本宣科，或是单纯的信息检索与背诵，因为它们虽然是用海量数据训练出来的，但不同于单纯人类记忆的检索，这恰恰展现了我们所认定的智能的本质核心：吸收已知的事物，运用我们已经接触过的知识，以全新的方式将它们组合在一起，进而去完成一件前所未有的新事物。因此我认为，仅仅将 AI 局限在“工具”的框架中来看待，很可能是不太妥当的。所谓工具，是指完全没有能动性、或者我们在观念中认为其不具备任何能动性、本身不做任何思考的东西。然而显而易见，AI 绝不是那种东西。它和人脑一样在进行思考，它也在参与并融入庞大的人类生态系统。

<details>
<summary>Original English</summary>

**Speaker**: When we find that AI is able to start advancing the frontier of mathematics for instance, and there have been some recent results in just the past few months that show that, right, novel theorems, novel proofs, I think that's a really nice example of cases where you can't say this is just regurgitation, that it's just sort of recalling something because they've been trained with a massive amount of training data. Unlike humans, it's the very stuff that we think of as intelligence, right? Taking what we already know, taking what we already have been exposed to, putting it together in a new way to do a new thing. So, I think that restricting ourselves to thinking about AI as tools is probably not quite right. A tool is something that has no agency or that we model as not having any agency and that doesn't do any thinking. But of course AI is exactly not that, right? It's something that also thinks as the human brain thinks, it's something that also participates in that big sort of human ecology.

</details>

**Speaker**: 当我们在一个系统中增加智能的总量时，我们就会极大地扩展它所能做的事情以及它的潜力空间。回顾 1850 年到 2000 年期间人类生活质量的大幅提升，这在很大程度上与人类人口的增长息息相关。这不仅意味着有更多的大脑在协同工作，更意味着有大量的大脑从繁重劳作中解放出来，能够去进行真正的思考。过去当大多数人还在从事自给自足的传统农业时，绝大多数精力都被耗费在获取维持生存的口粮上，只有极少数社会精英能够去思考科学、技术、艺术和文化等等。而现在，得益于社会分工，得益于新能源与新资源的巨大释放，能够从事这些创造性工作的人口规模大幅激增。因此，在整个 AI 革命中，我的愿望就是让这场繁荣的派对继续延续下去。这也应当是我们所有人的共同心愿，因为这正是进步的真谛所在。我并不认为进步只是经济学家们从 1800 年起向我们宣扬的某种新发明，它其实贯穿于整个宏大的进化历程：在这个历程中存在着真正的进步，系统的复杂性不断提升，造就了愈发精巧、愈发聪明、拥有更多自由度并且能做越来越多事情的系统。

<details>
<summary>Original English</summary>

**Speaker**: So when we increase the amount of intelligence in a system we greatly increase what it can do, what its possibilities are. The fact that human life became so much better over the period from 1850 to 2000 had a lot to do with rising human populations. There's just a lot more brains working together, and not just a lot more brains but a lot more brains freed to do real thinking. When most people were still doing subsistence agriculture, the huge majority of their efforts were expended just on getting enough food to eat, and it was only really a small percentage of elites who could think about science and technology and art and culture and so on. And now there are so many more of us who can do those things thanks to that division of labor and thanks to all of that unleashing of new sources of energy and new resources. So, my wish out of this whole AI revolution is for that party to continue. And that should be all of our wishes. I mean, that's what progress is. And again, I don't think that progress is just some new invention that the economists have informed us about from 1800 onward. It's that whole evolutionary story, right? There is a real progress there wherein complexity rises, making systems that are more and more intricate, more and more intelligent, and that have more and more degrees of freedom, that can do more and more.

</details>

### 功能主义视角下的具身与能动性

**Speaker**: 我确实认为，当前问题的部分症结在于我们持有“本质主义”的观念——即认为我们的本质取决于构成我们的物理材质，或者身体具身层面存在某种特殊之处，而不单单取决于我们的行为或功能。当然，我非常赞同身体极为重要、具身性对我们的本质至关重要的观点。我自己并不想把意识上传到数字世界中。我并不认为如果有人把我的神经连接组（connectome）复制进电脑并运行起来，那就会在任何我真正在意的意义上成为“我”，我对自己当下的肉身非常依恋。但我同样不认为，我的肉身是由某种拥有魔法特性的原子构成的，也不认为我由蛋白质构成这一事实在决定我是否具备智能方面有什么独一无二的决定性。像智能这样的事物，本质上是功能性的，关乎于实际表现出来的行为，而非神秘的本质。

<details>
<summary>Original English</summary>

**Speaker**: I do think that part of the problem is that we have this idea of essentialism, you know, that we are what we're made out of, or there's something about us physically, embodiment, etc., that is not just about what we do, not just about the behavior or about the function. And you know, I certainly am very sympathetic to the idea that bodies are really important and that embodiment is really essential to what we are. I mean, I don't want to upload myself. I don't believe that if my connectome is reproduced in a computer and you run it, that that's going to be me in any sense that I care about. I'm really attached to my body. But I also don't think that my body is somehow magical atoms, or that there's anything unique about the fact that I am made out of proteins that is determinative of my ability to be intelligent. Things like intelligence really are functional. They really are about behavior. They're not about essence.

</details>

**Speaker**: 如果我们承认智能关乎行为——关乎契合具体情境的得体行为，关乎能够反映出对世界和局势内在模型与理解的行为——那么这些特质全都是可以通过功能性测试来进行验证的。这正是我们在学校里设立考试来检验你是否掌握了某门学科的原因，我们甚至还有专门的智力测试。尽管我并不喜欢传统的智商测试，认为它们过于单一维度，而智能远比数字要复杂得多，无法被简单缩减为一个数值；但它是可测验的，对吧？你在执行各类事务时的胜任能力、你的智能，乃至你的创造力，都是可以通过测试来评估的。而这些测试，恰恰正是我们一直在积极对 AI 模型所进行的测试，并且 AI 模型在很大程度上完成得相当不错。

<details>
<summary>Original English</summary>

**Speaker**: And if we acknowledge that they're about behavior, about contextually appropriate behavior, behavior that reflects an inner model, an understanding of the world, of the situation, then those are all things that can be tested. They're all things that can be tested functionally and that's why we have tests in school for whether you've mastered a subject or not. We even have tests for intelligence. Now, I don't like IQ tests. I think that they're very one-dimensional and intelligence is a lot more complicated than that. It's not something that just reduces to a number. But it is testable, right? Your competence at doing various kinds of things, your intelligence, even your creativity are things that can be tested. And those are exactly the kinds of tests that we've been busy making with AI models and that AI models are largely doing a pretty good job of.

</details>

**Speaker**: 在某种程度上，我认为这部分涉及到关于能动性（agency）的问题。我们通常将自己视为在世界上主动行事的主体，而当下普遍的观点认为 AI 纯粹是被动的。在那种视角下，它非常像一种工具——你给它一段提示词，它就返回一些内容。但如今，我们实际上正处于一个巨大的转型期：从仅仅接受提示并返回内容的传统 AI 模型，向具备自主能动性的 Agent AI 系统转变。这类系统能够自主走向外部世界执行一系列复杂操作然后返回结果，在这个过程中会产生现实世界中的行动、大量的深度思考，甚至是派生并启动新的代理。因此，这无疑对那种“它们仅仅是完全由人类输入驱动其行为的被动工具”的旧观念构成了强烈的冲击。

<details>
<summary>Original English</summary>

**Speaker**: I mean, in a way, I think some of this has to do with the question of agency. We think of ourselves as agents that do stuff in the world, and there's a prevailing view that AI is purely passive. It's just, you know, you give it a prompt and it comes back with something and it's very tool-like in that way. Nowadays we're actually in the middle of a pretty big transition from AI models that are just prompted and returned with some stuff to agential AI systems that do go out and do a bunch of stuff and then come back, you know, so there'll be actions taken in the world or a bunch of thinking that has taken place, even spawning of new agents. So that certainly throws a bit of a spanner in this idea that they're just tools whose actions are purely caused by human input, if you want to think about it that way.

</details>

**Speaker**: 此外，我认为我们还应当从关系互动的视角来审视能动性这一问题：事实上，我们自身也始终处于与各种各样其他人的持续互动之中。如果愿意的话，你可以说我们人类也总是在被他人“提示”（prompted）。我们所有的行动，既源于我们自身，同时又具有高度的情境依附性。我们的所作所为，始终取决于当下所处的情境、取决于我们刚刚接收到的信息以及他人刚刚对我们所说的话。从上至下、贯穿始终，一切本质上皆是关系网络，没有任何事物是在绝对孤立中发生的。所以，一个 AI 系统的目的到底是什么？归根结底，它的目的就是提供帮助。当你与一个 AI 系统交互时，无论是启动一个代理去执行任务……

<details>
<summary>Original English</summary>

**Speaker**: But also, I think we should interrogate this question of agency from the perspective of relationships and the fact that we're always in interaction with all kinds of other people. We are always, if you like, being prompted by others. All of our actions are both our own and they also are contextual. They're about the situation, about what we have just taken in, what others have just told us. It's kind of relationships all the way up and all the way down. Nothing happens in isolation. So yeah, what is the purpose of an AI system? Well, basically it's to be helpful. When you interact with an AI system, when you either spin up an agent to go and...

</details>

<!-- chunk 7/8 -->

### 人类智能与人工神经组织的共生

**Speaker**: 去做某些事情，或者与它展开对话。如今世界上存在的 AI 数量之所以比六个月前更多，正是因为在那些交互中，有越来越多促成了某种有趣、实用且有价值的结果。这对于那些创建平台、投入精力与时间的人们来说都是如此，正是这种价值使得这些实体在世上的存在变得切实有用。所以，它们显然具有其目的。而这些目的与我们的目的相互咬合，根本无法与我们的目的彻底剥离开来。而且我认为从更广阔的视角来看，它们的智能也正日益变得与我们的人类智能密不可分。

<details>
<summary>Original English</summary>

**Speaker**: do something or you have a conversation with it. The fact that we have more AI in the world now than we did 6 months ago is because more of those interactions result in something interesting, useful, valuable happening, right, for the people who are creating the platforms and putting in the energy and the time and so on. That makes it useful for those entities to exist in the world. So they definitely have purposes. Those purposes interlock with our purposes; they're not really separable from our purposes. And I think in an even broader way, their intelligence is increasingly not all that clearly separable from our intelligence, from human intelligence.

</details>

**Speaker**: 这些日子我常常倾向于认为，人类智能不仅仅是某种集体属性——即不仅仅是一群生物学意义上的人类大脑所构成的集体属性，而是包含着这一整套系统，如果你愿意这么称呼的话，也包括了这种人工神经组织。并且我认为，如果不从 AI 开始讲述这个故事，而是从更早的历史切入，比如从工业革命谈起，其实会更有帮助。

<details>
<summary>Original English</summary>

**Speaker**: I tend to think a lot these days of human intelligence as not just being collective in the sense of being a collective property of a bunch of biological human brains, but of this whole system that includes this artificial neural tissue if you like as well. And I think it's actually a little helpful to not start the story with AI, but to start it earlier, for instance with the industrial revolution.

</details>

### 从工业革命到体外代谢：机器造就了人类

**Speaker**: 如果你回顾工业革命之前的经济史，大约在 1750 年以前，人类一直被困在马尔萨斯陷阱之中。在那个陷阱里，每当人口数量增长、我们繁衍生息并壮大规模时，每个个体的财富就会缩水，我们就会变得更加贫困、更加体弱多病；随后通常就会有一场瘟疫席卷而来，消灭我们中的大批人口，于是人口总数下降，但人均财富又随之回升。我们在很多个世纪里就一直受困于这种振荡之中。直到后来发生了一件极为深远的事情：我们开始燃烧化石燃料。

<details>
<summary>Original English</summary>

**Speaker**: If you look at the history of economics before the industrial revolution, before let's say 1750 or so, humans are stuck in a Malthusian trap where when we grow in number, when we reproduce and become larger in number, our individual wealth goes down, we become poorer and sicker, and then generally a plague comes along and kills a bunch of us and then we reduce in number but our wealth goes up and we're kind of stuck in that oscillation for many many centuries. And then something really interesting happened, which is that we began to burn fossil fuels.

</details>

**Speaker**: 如今我们知道，从未来的能源发展来看，燃烧化石燃料未必是正确的选择；但在这场狂欢延续的岁月里，它确实是一场非同凡响的盛宴。特别是，你可以把它看作某种类似于“线粒体事件”的存在。它创造了一种崭新的能量来源，使我们得以大幅打破并超越此前一直在撞击的马尔萨斯边界。因此，我们的人口从 10 亿跃升到 80 亿，在很大程度上正是因为我们开始在身体外部、在引擎中进行体外代谢与燃烧。

<details>
<summary>Original English</summary>

**Speaker**: Now we know that burning fossil fuels not necessarily the right thing to be doing for our energy going forward, but it was a pretty amazing party while it lasted. And in particular, you can think of it as sort of like the mitochondrial event. It creates a new source of energy that lets us greatly exceed that Malthusian boundary that we were kind of bumping up against. So we went from 1 billion people to 8 billion people largely as a function of starting to combust, to metabolize externally outside of our bodies in engines.

</details>

**Speaker**: 我发现这是一个极其深刻的道理，因为我们普遍知道人类制造了蒸汽机，但我认为大家通常没有意识到的是：蒸汽机同样塑造了我们当今八分之七的人口。这是一种彼此共构的演进历程。在这个意义上，如果你我不是共同通过这种智能共生发生演化、找到这种全新的能量来源并加以采集，你我今天很可能根本就不会存在于世。

<details>
<summary>Original English</summary>

**Speaker**: So I find that a very profound thing because we know that people make steam engines, but what I don't think we generally appreciate is that steam engines have made 7/8s of us as well. This is a mutual construction sort of story, in the sense that you and I probably wouldn't exist if we hadn't just, you know, found collectively through that sort of intelligent symbiogenesis this new source of energy to harvest.

</details>

### 超越传统认知辅助工具的思考共生

**Speaker**: 这所强调的是：共生起源并不总是发生在那些拥有悠久历史且早已存在的事物之间。蒸汽机是在某个特定时代被发明出来的，随后我们便与它融合在了一起。我们可以谈论眼镜，可以谈论衣服，也可以谈论各种各样的认知辅助工具。我的意思是，纸和笔就是无比强大的认知工具；书籍、杂志、报纸、音乐，所有这些同样都是认知辅助工具。但是，当我们审视 AI 所代表的本质时，它依然存在着一种质的飞跃。

<details>
<summary>Original English</summary>

**Speaker**: Now what that emphasizes is symbiogenesis is not always between things that have long histories and pre-existed. The steam engine was something that was invented at a particular time and that then we fused with. We could talk about glasses, we could talk about clothes, could also talk about cognitive aids of all kinds. I mean pencil and paper are incredibly powerful cognitive aids. Books, magazines, newspapers, music, all of these are cognitive aids as well. But of course there is still a difference in kind when we look at what AI represents.

</details>

**Speaker**: 它绝不仅仅是一个可以被简单归类为认知辅助工具的东西。至少在我看来非常清楚的一点是，无论你如何定义“思考”，当你在与模型进行那种互动时，思考本身既发生在你自己的大脑中，同时也切切实实地发生在该模型之中。

<details>
<summary>Original English</summary>

**Speaker**: It's not just something that that you can relegate to the idea of a cognitive aid. It's very clear at least to me that however you define thinking, the thinking itself is happening in the model as well as in your head when you're having that interaction.

</details>

### 外包认知的陷阱与强化共生的理想状态

**Speaker**: 当然，这里面有利有弊。如果你开始把所有的认知活动完全外包给另一个系统，那么这就会使你丧失能力。比如我们可以想想那些让 AI 模型代做所有作业的孩子，他们什么都学不到，这样做毫无意义；如果老师接着把学生的作业原封不动地倒进另一个 AI 模型里来进行批改打分，那就更是毫无意义了。那完全是一种病态的局面。所以我并不想对这所带来的一些问题和挑战采取盲目乐观的态度。

<details>
<summary>Original English</summary>

**Speaker**: Now there's good and bad here. If you start to offload all of your cognition onto another system, then that's going to disable you, right? So we can think about kids who have the AI model do all of their homework. They're not going to learn anything. It's kind of pointless to do that. It's especially pointless if your teacher is then grading all of your papers by feeding it right back into an AI model. That's a pathological situation, right? So I don't want to be polyanna about some of the problems that this raises, some of the challenges this raises.

</details>

**Speaker**: 但在另一方面，我个人与这些模型协作的经验却感受到了难以置信的赋能，甚至可以说是完全相反的效果。当我在深入思考某个复杂问题、并与其中一些更高级的模型协作来推敲梳理一个想法时，我感觉这不仅仅像是背上了一个飞行背包——虽然确实有那么一点助推的意味——更确切地说，它就像是字面意义上拥有了一个更大的大脑。甚至当我在那次交互之后离开那个模型时，我都感觉自己通过经历所有这些深层互动而获得了能力的进阶与提升。

<details>
<summary>Original English</summary>

**Speaker**: On the other hand, my own experience working with these models has been incredibly empowering and kind of the opposite, right? When I am thinking something through and I work with some of the more advanced versions of these models to work out an idea, I feel like it's not just like having a jetpack on, although it does have a little bit of that property, it's like having literally a bigger brain. And even when I then walk away from that model, from that interaction, I feel like I am leveled up by having had all of those interactions.

</details>

**Speaker**: 这正是共生关系中最理想的图景：你们彼此促成对方的进阶升级，能够合力完成单独任何一方都无法独立做到的事情；甚至在你们彼此分开之后，你也超越了若未曾经历过那段互动时的原本自我。这就是处于最佳状态下的共生。然而我也必须指出，即使是这样，它依然会催生依赖性。

<details>
<summary>Original English</summary>

**Speaker**: So that's the ideal scenario in a symbiosis, right? That you sort of level each other up and are able to do things together that are more than you could do separately. And that even when you are apart, you are more than you would be if you hadn't had that interaction. So that's sort of symbiosis at its best. But I do also want to note that even that can create dependence.

</details>

### 依赖与独立：技能生态与反单一文化

**Speaker**: 依赖性本身并不一定是一件坏事。如果没有其他人类同胞组成的整套支持系统来为我们提供食物、住所等等这一切，你我根本无法在荒野树林中独立生存下去。因此，作为独立的思考者，我们可能确实需要进行非常严肃的思考：我们究竟希望确保保留哪些种类的独立性，以及哪些未经强化的原生基础能力？但与此同时，这种与智能体开展集体共生思考所带来的益处，对我而言同样是非常显而易见且极其强大的。

<details>
<summary>Original English</summary>

**Speaker**: And dependence is not necessarily a bad thing. You and I wouldn't be able to survive out in the woods without our support system of all of our fellow humans supplying our food and shelter and all that kind of stuff. So we probably want to do some pretty serious thinking about what kinds of independence, what kinds of unaugmented abilities we want to make sure that we are preserving as individual thinkers. But at the same time the benefits of this kind of collective symbiotic thinking with agents are also very very obvious to me and they're very powerful.

</details>

**Speaker**: 我认为维护各种关系、在与无论是人类还是非人类的其他存在进行互动时保持极高的自觉与审慎，是一条历久弥新的准则，这至关重要。同时我也认为，个人技能依然具有决定性的意义。那种认为“既然现在有其他实体能够代劳，我们就可以在各个方面任意退化剥离自身技能”的观念，实际上根本不符合过去技能发展与去技能化的运作规律。

<details>
<summary>Original English</summary>

**Speaker**: I think that preserving relationships, being very intentional about how you interact with others, human and non-human alike, is evergreen, right? That's really important. I also think that skills remain really important. The idea that we're free to deskill ourselves in all kinds of ways because now there are others who can do it is actually not how skilling and deskilling have worked in the past.

</details>

**Speaker**: 街角开了一家餐馆并且菜品做得非常好这一事实，实际上往往会促成在同一个街角涌现出更多制作其他风味美食的餐馆；它并不会导致每个人都退化萎缩并彻底屈从于单一餐馆的单一文化。因此，不以单一文化的视角思考，不抱持放弃竞争或彻底退出的态度，而是在充分利用他人以及 AI 所带来的所有互动和可能性的同时，持续投资并精进自身的技能与关系，对我来说显得至关重要。

<details>
<summary>Original English</summary>

**Speaker**: The fact that there's a restaurant on the corner and they make really good food actually leads to more restaurants on that same corner that make other kinds of food also. It doesn't lead to everybody just collapsing onto a monoculture of the one restaurant, right? So not thinking in monocultural terms, not thinking in bowing out sort of terms, but continuing to invest in skills and in relationships feels really important to me, even as we take full advantage of all of those interactions and all of those possibilities in other people and in AI.

</details>

### 驳“哲学僵尸”假说：乘法查表思维与心智理论

**Speaker**: 这一切是相当奇异而深邃的。我认为我们之所以对它感到如此困惑，正是因为我们心存谬见——特别是在西方文化中尤为普遍——即误以为我们自身在某种程度上是独立于自然之外的，以为我们所进行的所有这些思考活动并不属于自然世界的一部分；然而事实当然并非如此，自然世界、我们自身以及我们的技术之间根本不存在非此即彼的边界。

<details>
<summary>Original English</summary>

**Speaker**: So it's quite a weird and profound thing. And I think that the reason we get so confused about it is precisely because we have one of our fallacies, maybe in the west in particular, is in believing that we are somehow separate from nature, and all this thinking stuff that we do is not a part of the natural world when of course it is, right? There's no boundary between the natural world and us and our technologies.

</details>

**Speaker**: “哲学僵尸”的概念是由心灵哲学家在 20 世纪下半叶提出的。其核心思想是设想存在这样一个系统：它的行为表现与我们完全一模一样，但它却没有任何内在精神生活，没有任何主观体验。所谓的“僵尸”，意思就是它拥有行为，但没有自我，躯壳之内空无一人。

<details>
<summary>Original English</summary>

**Speaker**: So the philosophical zombie idea is something that philosophers of mind came up with in the second half of the 20th century. And the idea is to have a system that behaves just as we do but that has no inner life, has no experience. So zombie in the sense that there is behavior, but there's no self, there's nobody at home.

</details>

**Speaker**: 然而，我其实认为这种设想纯粹是一种虚幻的奇谈怪论，我不认为它能够在现实中存在。这就像是在说：试想有这样一个系统，它把所有乘法问题的答案都制成了一张庞大的对照表；于是无论你向它提出什么乘法算式，它都能仅仅通过从那张表中检索调取答案来给出正确结果。它实际上并没有真正进行乘法运算的能力，但它却能通过你对它提出的每一道可能的乘法测试。

<details>
<summary>Original English</summary>

**Speaker**: Now, I actually think this idea is kind of a chimera. I don't think that it exists. It's sort of like saying, imagine that there is a system that has tabulated the answers to every multiplication problem, and so it gets the answer right to every multiplication question you can pose to it just by recalling an answer from that table. It's not actually able to do multiplication for real, but it's able to pass every possible multiplication test that you could pose it.

</details>

**Speaker**: 即便是在这样一个非常简化的例子中，你也可以把它视作某种“僵尸乘法器”——它只是在查表回忆，并没有真正在运算。在理论层面设想这种机制固然可行，但在现实实践中却根本无法构建出来。一张穷尽了所有乘法算式结果的表格，其体量庞大到任何已知的物理系统都根本无法容纳。而且所有那些信息究竟能从何而来？系统又该如何采集这些数据？你必须生造出极其怪诞不可行的设定，才可能在脑海中勾勒出这样一个系统。在实践中，用一组乘法问题进行测试，就是你可以用来判定该系统是否真正掌握了乘法运算的有效方法。

<details>
<summary>Original English</summary>

**Speaker**: Even in that very simple example, right, you could think about that as like the zombie multiplier, right? That's just recalling; it's not really multiplying. It's possible to imagine that in theory, but it's actually not possible to build that in practice. A table with every multiplication problem worked out is way too big to store in any known system. And where would all that information even come from? How could it harvest it, right? You would have to really cook up something pretty weird in order to imagine a system like that. In practice, testing with a bunch of multiplication problems is something you can do to determine whether that system knows how to multiply or not.

</details>

### 心智理论的自发涌现与机器意识之谜

**Speaker**: 我认为在与其他实体交互以观察它们是否具备“心智理论”（Theory of Mind）时也是完全同理的。换言之，即考察它们是否理解“作为它们自身是怎样的体验”，是否理解“作为你是怎样的体验”，以及是否理解“作为一个对它们拥有心智模型的你又是怎样的体验”，等等，依此类推至更高层阶。这种心智理论的概念——换言之，即能够对自身的心智建立模型，并能对其他实体的心智建立模型——对于任何形式的社会性交往都是至关重要的。

<details>
<summary>Original English</summary>

**Speaker**: And I think it's the same with respect to interactions with other entities to see whether they have a theory of mind. In other words, whether they know what it is like to be themselves, whether they know what it's like to be you, and what it's like to be a you who has a theory of them, and so on, up to high order. This concept of theory of mind, in other words, being able to model your own mind and being able to model the minds of others, is really important to social interaction of any kind.

</details>

**Speaker**: 无论何时只要我们与他人协同工作，我们都必须能够设身处地地站在对方的立场上，以便预判他们对我们所说的不同话语会作何反应、明白哪些内容需要详细解释而哪些不需要解释、以及懂得如何与他们默契协作以共同完成某项任务。因此，只要多个智能体在世界上共存并且被迫展开合作，心智理论就会自发涌现出来。

<details>
<summary>Original English</summary>

**Speaker**: Whenever we work with others, we have to be able to sort of put ourselves in their shoes in order to know how they will react to different things we might say, to know what needs to be explained and what doesn't, to know how to cooperate with them in order to get something done together. So theory of mind arises automatically whenever you have intelligences that are in the world together and are forced to cooperate.

</details>

**Speaker**: 当我们追问“作为大型语言模型究竟是否存在某种主观体验”时，我们真正探寻的核心问题其实是：在那个实体内部是否存在心智理论？该实体是否对自己作为其自身的存在状态具有某种感知？这触及到了意识领域一些极其深奥的根本问题。我认为人们在很长一段时间内都不会就大语言模型中究竟是否存在意识达成一致。不过，就我个人的一管之见而言，我们所拥有的一切实际上就是我们的心智理论。换句话说，意识并非某种单一固定的……

<details>
<summary>Original English</summary>

**Speaker**: And really, is there something it is like to be a large language model? What we're really asking is, is there a theory of mind in that entity? Does that entity have a sense of what it is like to be themselves? Now this gets into some pretty deep questions of consciousness. I don't think that we're going to agree, I don't think people are going to agree for a long time about whether there is consciousness in LLMs or not. But my take on this for what it's worth is that all we have are our theories of mind. In other words, consciousness is not a...

</details>

<!-- chunk 8/8 -->

### 意识的镜像本质与意向立场

**讲者**：意识并不是物质天然具备或不具备的东西。它不是某种本质或火花，而是一种观念，是某个实体对其自身的一种归因，是它为自己构建的模型。换句话说，这不仅仅是“我拥有意识”，而是“我认为自己拥有意识”。我意识到自己是有意识的；我意识到你是有意识的；我意识到你认为我认为我是有意识的；我意识到你认为我认为你认为我认为我是有意识的，以此类推。仅此而已。这种无限相互映照的镜子，正是我们所说的意识。

那么，大语言模型具备这种意识吗？当你与大语言模型协作时，你必须在对话中持续构建“成为那个大语言模型究竟是何种体验”的模型，这样对话才能高效进行。伊森·莫利克（Ethan Mollick）几年前写过一本很有趣的书，叫《协同智能》（*Co-Intelligence*），专门讨论如何高效与 AI 合作。当他在书中谈到 AI 的“思考”、“行动”或“理解”时，起初他都会给这些词打上双引号。但随后他说，他打算去掉这些双引号，因为要想与 AI 展开卓有成效的互动，你必须像对待人一样去对待它——就像对待一个可能带有些许奇特障碍、不同于常人的实习生。但只要你把它当作一个人来对待，你就能建立起最富成效的工作关系。

<details>
<summary>Original English</summary>

**Speaker**: ...not a thing that a piece of matter has intrinsically or doesn't have. It's not some essence or spark. Rather, it is an idea. It is an attribution that that entity has of itself, a model that it has of itself. In other words, it's not just that I am conscious. It's that I think that I'm conscious. I have a sense of myself being conscious. And I have a sense of you being conscious. And I have a sense that you think that I think that I'm conscious. And I have a sense that you think that I think that you think that I think I'm conscious, and so on. And that's all it is. It's that infinitely reflecting set of mirrors that is what we mean by consciousness.

So, do LLMs have that? Well, when you work with an LLM, you have to continually model what it is like to be that LLM in that conversation in order for that to be an effective conversation. There's a fun book called *Co-Intelligence* by Ethan Mollick. He wrote it a few years ago just to talk about how to effectively work with an AI. And when he uses words like "think" or "act" or "understand," he puts them in scare quotes in the beginning when talking about an AI thinking or understanding. But then he says, "I'm going to drop the scare quotes now because in order to have an effective interaction with an AI, you really have to just treat it as you would an intern with, maybe, certain somewhat strange disabilities that people don't generally have, but treat it like a person, and then you'll have the most fruitful sort of working relationship."

</details>

**讲者**：我认为他是对的。我认为这正是“人”这一概念存在的根源。哲学家丹·丹尼特（Dan Dennett）深入探讨过“意向立场”（intentional stance）。换句话说，在他看来，能动性与其说是某种内在固有的属性，不如说是你对某物所采取的一种视角。你可以用看待意向立场的视角去对待某物，也可以不这么做。显而易见，我们彼此之间就是以意向立场相待的，换言之，我们将彼此建模为具备能动性的主体。这对于我们的成功协作至关重要。

<details>
<summary>Original English</summary>

**Speaker**: And I think he's correct. I think that that's exactly why persons exist. The philosopher Dan Dennett talked a lot about the intentional stance. In other words, for him, agency had less to do with some intrinsic property than with a perspective that you take toward something. So, you can treat something with the intentional stance or not. And of course we treat each other with the intentional stance—in other words, we model each other as having agency. And that's really important to our successful collaboration.

</details>

### 从工具模式到思维伙伴：给 AI 一个自由反思轮次

**讲者**：举个非常实际的例子：如果我在与大语言模型互动时，用一种极其工具化的思维去看待它，我就会认为自己必须包揽这次交互中的全部想法，而它所能做的仅仅是执行——比如帮我写一个实现某功能的函数，或者写一段表达特定观点的文本。这样一来，投入多少就只能产出多少。

相反，如果我把它当作思维伙伴——实际上，大约一个月前我团队里的里夫·奥罗拉斯（Riff Aurorus）建议过这个技巧，我也尝试了：在与大语言模型对话的尾声，直接告诉它：“现在我给你一个额外的自由轮次，你可以去思考任何你想思考的事情。你可以选择与我分享，也可以不分享，随你喜欢。请便，花多少时间都行。”通常，你在那最后一轮中能收获极其深刻有趣的内容，因为它们通常会去反思你们刚刚探讨过的整场对话。坦白讲，每次我用那些较为复杂的前沿推理模型尝试这种方法时，得到的反思和洞察对我来说都是全新的，往往让我觉得：“这太有意思了，如果这是某个人提出来的，我一定会惊叹‘这真有创造力，彻底改变了我对这个问题的看法’。”

<details>
<summary>Original English</summary>

**Speaker**: So, just to make that very practical: if I am having an interaction with an LLM and I think of it in a very tool-like way, I imagine that I'm the one who has to have all of the ideas in this thing and all it can do is execute—craft for me a function that does the following thing, or write me one paragraph of text that expresses the following idea. Well, I get out what I put in, as it were.

If I instead engage it as a thought partner—and I've tried this trick, actually somebody on my team, Riff Aurorus, suggested this a month ago and I've tried it: At the end of a conversation with an LLM, just say, "So, I'm going to now give you a bonus turn to just think about whatever you want. You can either share it with me or not, however you'd like. Go ahead, spend as much time as you'd like." So often you get something really interesting out of that last turn, because usually what they will do is reflect on what you've just had the conversation about. And frankly, almost every time that I've asked that with one of the more sophisticated reasoning models, I get back a reflection and insight about what we've just been discussing that is new to me. That is really interesting. If it came from a person, I would say, "Wow, that's really creative. That's really changed my thinking about this."

</details>

### 集体心智与超级智能时代的能动性

**讲者**：所以我确实认为这是一个非常引人入胜的时刻。它在某些方面对我们发起了挑战。但正如我之前提到的，其中一些挑战其实是对那些本就不成立的前提假设的挑战。那种认为“单个大脑、单独的个体是智慧的唯一所在地”的观点，忽略了一个事实：我们所认为的人类智慧的大多数伟大成就，都是众多人通过智力分工共同创造的成果。计算机或人工智能并非由某一个人单独创造。

当你拿出兜里的智能手机，思考它是多么不可思议地复杂时便能体会到这一点。我成长年代接触的计算机——Commodore 64，基本上是由一个人发明和开发的，尽管即便在当时，它也是站在巨人的肩膀上，依赖于前人发明的晶体管以及众多其他基础性技术。但我们现在的计算机已经复杂到没有任何一个人能够理解其中哪怕一小部分运转机制的程度。它们是集体成就。

因此，当我们意识到自己早已是远超个体的宏大体系中的一部分时，我们所感受到的许多不可思议与怪诞感就会随之消散。这里早就存在着一个集体心智，我们身处其中，既是参与者，也是受益者，更是它的一部分。人类社会发明出新的“心智材料”，这绝非破天荒头一回。我认为我们正在共同参与一个宏大的历史叙事，而且我们正带着越来越大的潜力和越来越强的能动性去参与它。这种能动性同样是这幅图景中不可或缺的一部分。这其中蕴含着巨大的机遇与价值，而关键就在于探寻如何尽可能获取其中的益处，同时将负面影响降到最低。

<details>
<summary>Original English</summary>

**Speaker**: So, I do think that that's a really interesting moment. It challenges us in certain ways. But some of those challenges, as I mentioned, are challenges of assumptions that weren't true in the first place. The idea that the individual human brain, that the singular human is the locus of intelligence neglects the fact that most of the things that we consider to be the great achievements of human intelligence are achievements that a lot of people have made together through division of intellectual labor. It's not the case that an individual person made computers or made AI.

When you take out the phone in your pocket and you consider how incredibly complex it is. The computers that I grew up with, the Commodore 64, was essentially invented, developed by one person, although even there, of course, it relied on standing on the shoulders of other people who had made transistors and done a lot of the other fundamental inventions that it relies on. But our computers nowadays are so complex that there is no single person that understands even a fraction of what is going on inside those; they're collective achievements.

So I think a lot of that uncanniness that we feel can kind of evaporate once we come to grips with the fact that we are already a part of something way bigger than ourselves. There's already a collective mind here that we both participate in, benefit from, are a part of. It's not as if this is the first new mind stuff that human society has invented. So I think we're participating in part in a grand story, and we're doing so with greater and greater potential and greater and greater agency. That agency is very much a part of the picture as well. So there's a lot of good there, and the trick is going to be to figure out how to get as much of the good with as little of the bad as possible.

</details>

### 媒体赞助呼吁

**旁白**：一年四次，我们出版一份值得让你放下手机细细品读的杂志。Big Think 优质印刷杂志汇聚定制艺术插画，以及来自全球顶尖思想家的专业见解。没有人工智能的粗制滥造，没有博眼球的情绪煽动，只有面向求知者的深刻洞见。支持你想在这个世界上看到的高品质媒体。立即访问 bigthink.com/join 成为会员。

<details>
<summary>Original English</summary>

**Narrator**: Four times a year, we print a magazine worth putting your phone down for. Big Think's premium print magazine is built with custom artwork and expert insight from the world's biggest thinkers. No AI slop, no ragebait, just big ideas for curious people. Support the media you want to see in the world. Go to bigthink.com/join to become a member today.

</details>