---
author: Dwarkesh Patel
date: '2026-04-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=myP8UjAM1pk
speaker: Dwarkesh Patel
tags:
  - scientific-progress
  - ai-in-science
  - technological-evolution
  - knowledge-acquisition
  - paradigm-shifts
title: 迈克尔·尼尔森：外星文明为何拥有与我们不同的科技树
summary: 本访谈深入探讨了科学进步的本质，从物理学史上的案例（如迈克尔逊-莫雷实验、相对论、引力理论）到生物学（进化论），揭示科学发现的非线性与复杂性。嘉宾迈克尔·尼尔森阐述了人工智能在加速科学发展中的作用与局限，特别是AI如何处理“瓶颈”问题。对话还涉及科技树的探索、跨文明的技术差异与贸易优势，以及个人如何进行深度学习和知识整合的挑战与方法。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Labelbox
  - Jane Street
products_models:
  - AlphaFold
  - AlphaZero
media_books:
  - Subtle is the Lord
  - The Methodology of Scientific Research Programmes
  - Principia Mathematica
  - The Origin of Species
  - The Art of Computer Programming
  - Susskind special relativity book
status: evergreen
---
### 科学进步的本质与AI的验证循环

**主持人**: 今天我采访的是**迈克尔·尼尔森**。您做过很多事情。您是**量子计算**领域的先驱之一，撰写了该领域的主要教科书，也是**开放科学**运动的倡导者。您写了一本关于**深度学习**的书，**克里斯·奥拉**和**格雷格·布洛克曼**都说这本书引领他们进入了这个领域。最近，您是**Astera Institute**的研究员，正在撰写一本关于宗教、科学和技术的书。我不会问您这些。我今天想讨论的是：我们如何识别**科学进步**？这对于**AI**尤其重要，因为人们正试图在**科学发现**上关闭**强化学习验证循环**。关闭这个循环意味着什么？但在准备这次采访时，我意识到即使在人类科学史上，它也是一种比我理解的更为神秘和难以捉摸的力量。我想一个好的起点是**迈克尔逊-莫雷实验**以及**狭义相对论**是如何被发现的，如果它与您在YouTube视频上看到的故事有所不同的话。我会这样引导您，然后我们再深入讨论。

<details>
<summary>Original English</summary>

**主持人**: Today, I'm speaking with **Michael Nielsen**. You have done many things. You're one of the pioneers of **quantum computing**, wrote the main textbook in the field of the **open science** movement. You wrote a book about **deep learning** that **Chris Olah** and **Greg Brockman** credit with getting them into the field. More recently, you're a research fellow at the **Astera Institute** and writing a book about religion, science, and technology. I'm going to ask you about none of those things. The conversation I want to have today is, how do we recognize **scientific progress**? It's especially relevant for **AI** because people are trying to close the **RL verification loop** on **scientific discovery**. What does it mean to close that loop? But in preparing for this interview, I've realized that it's a more mysterious and elusive force, even in the history of human science, than I understood. I think a good place to start will be **Michelson-Morley** and how **special relativity** is discovered, if it's different from the story that you get off of YouTube videos. I will prompt you that way, and then we'll go in there.

</details>

**迈克尔·尼尔森**: **迈克尔逊-莫雷实验**是著名的结果，通常被描述为19世纪80年代进行的一项实验，它帮助**爱因斯坦**在稍后提出了**狭义相对论**，改变了我们对空间和时间的思考方式以及我们对这些事物的基本概念。我认为**迈克尔逊**和**莫雷**以及当时其他人对实验的看法，与**爱因斯坦**对实验的看法或不看法之间存在巨大差距。事实上，他后来在生活中表示，他甚至不确定当时是否知道这篇论文。有很多证据表明他可能当时知道这篇论文，但它对他的思维并没有决定性作用。完全是别的事情在发生。**迈克尔逊**和**莫雷**认为他们当时在做的是测试关于**以太**的不同理论。如果追溯到17世纪，**罗伯特·玻意耳**引入了**以太**这个概念。我们知道声音是空气中的振动。**玻意耳**和其他人对光是否是某种东西中的振动产生了兴趣，但他们无法弄清楚那是什么。**玻意耳**做了一个实验，测试光是否可以通过真空传播。他发现可以。声音则不行。他引入了**以太**这个概念，在接下来的两百年左右的时间里，人们一直在讨论**以太**是什么以及它的性质。**迈克尔逊-莫雷实验**实际上是一个实验，用来相互对照测试**以太**的不同理论，特别是为了找出是否存在所谓的**以太风**。其想法是地球可能正在穿过这种**以太风**。如果它穿过**以太风**，并且您以平行于**以太风**方向发射光束，光速会稍微加快。如果光束以相反方向穿过，速度会稍微减慢，您应该能够在干涉实验的结果中看到这一点。他们发现，令他们大为惊讶的是，实际上并没有**以太风**。这排除了**以太**的一些理论，但不是全部，**迈克尔逊**当然继续相信**以太**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: **Michelson-Morley** is the famous result often presented as this experiment that was done in the 1880s that helped **Einstein** come up with the **special theory of relativity** a little bit later, changing the way we think about space and time and our fundamental conception of those things. And there's a big gap, I think, between the way **Michelson** and **Morley** and other people at the time thought about the experiment and certainly the way in which **Einstein** thought or did not think about the experiment. In actual fact, he stated later in his life he wasn't even sure whether he was aware of the paper at the time. There's a lot of evidence that he probably was aware of the paper at the time, but it actually wasn't dispositive for his thinking at all. Something else completely was going on. What **Michelson** and **Morley** thought they were doing was testing different theories of what was called the **ether**. If you go back to the 1600s, **Robert Boyle** introduced the idea of the **ether**. We know that sound is vibrations in the air. **Boyle** and other people got interested in the question of whether light is vibrations in something, and they couldn't figure out what it was. **Boyle** did an experiment where he tested whether you could propagate light through a vacuum. He found that you could. You couldn't do it with sound. He introduced this idea of the **ether**, and for the next two hundred or so years, people had all these conversations about what the **ether** was and what its nature was. The **Michelson-Morley experiment** was really an experiment to test different theories of the **ether** against one another, in particular to find out whether or not there was a so-called **ether wind**. The idea was that the Earth is maybe passing through this **ether wind**. And if it is passing through the **ether wind** and you shoot a light beam parallel to the direction the **ether wind** is going in, it'll get accelerated a little bit. If it's being passed back in the opposite direction, it'll get slowed down a little bit, and you should be able to see this in the results of interference experiments. What they found, much to their surprise, was that in fact there was no **ether wind**. That ruled out some theories of the **ether**, but not all, and **Michelson** certainly continued to believe in the **ether**.

</details>

**主持人**: 这就是我从您推荐的**爱因斯坦**传记中读到这个故事时感到震惊的部分……他的名字叫什么来着？**亚伯拉罕·派斯**。

<details>
<summary>Original English</summary>

**主持人**: This is what was a shocking part of reading this story from the biography of **Einstein** that you recommended by... what was his first name? **Abraham Pais**.

</details>

**迈克尔·尼尔森**: **亚伯拉罕·派斯**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: **Abraham Pais**.

</details>

**主持人**: 《上帝是微妙的》。还有**伊姆雷·拉卡托斯**的《科学研究纲领方法论》。故事的讲述方式是**迈克尔逊-莫雷实验**证明**以太**不存在。因此，它在物理学中制造了一场危机，而**爱因斯坦**用**狭义相对论**解决了这场危机。您指出的是，他实际上试图区分**以太**的许多不同理论。如果您在太空或在地球上，**以太**的方向是相同的，或者**以太风**可能被地球带着旋转，因此在地球上您无法真正体验到它。但如果您到达足够高的高度，您可能能够体验到它。事实上，**迈克尔逊**的实验，最著名的是1887年的那次，但他基本上进行了二十年的实验。

<details>
<summary>Original English</summary>

**主持人**: **Subtle is the Lord**. Also from **Imre Lakatos**, **The Methodology of Scientific Research Programmes**. The way it's told is that **Michelson-Morley** proved that the **ether** did not exist. Therefore, it created a crisis in physics that **Einstein** solved with **special relativity**. What you're pointing out is he actually was trying to distinguish between many different theories of **ether**. If you're in space or if you're on Earth, it's the same direction of **ether**, or maybe the **ether wind** is being carried around by the Earth, and so you can't really experience it on Earth. But if you go to a high enough altitude, you might be able to experience it. In fact, **Michelson's experiments**, the famous one is 1887, but he conducted these experiments for basically two decades.

</details>

**迈克尔·尼尔森**: 比那更长。他第一次实验是在1881年，我想，但他一直相信直到他去世。

<details>
<summary>Original English</summary>

**Michael Nielsen**: For longer than that. He conducted the first one in 1881, I think, but he continued to believe until he died.

</details>

**迈克尔·尼尔森**: 他去世时，我想是1929年左右。那是20年代末。他直到20年代还在做关于**以太**是否存在实验。所以他一生都相信**以太**。我认为他去世前一两年发表的最后一次公开声明中，他基本上仍然相信它。事实上，还有另一位物理学家**米勒**在20年代一直在做这些实验。他认为如果他去到足够高的高度，比如加州的**威尔逊山**……“哦，我足够高，**以太风**不会被地球拖曳。我已经测量了**以太**的影响。”**爱因斯坦**听说了这件事，然后他说出了那句名言：“**上帝是微妙的，但祂不恶意。**”总之，我认为这个故事很有趣，原因有很多。**科学**的真实历史与您所理解的**科学方法**观念不同之处在于，您无法像想象的那样轻易应用**证伪**。不清楚什么正在被**证伪**。它只是**以太**理论的另一个版本正在被**证伪**吗？当然，您不能从**以太**的某个版本似乎被这些实验证伪的事实中推导出**狭义相对论**。它当然没有表明关于**证伪**的观念是错误的或被证伪的，但它确实表明最幼稚的观念……事情往往比您想象的要复杂得多。**迈克尔逊**在1881年做了这个实验。他当时很年轻，然后其他人，我想**瑞利**是其中之一，指出他的实验方式存在一些问题，所以他们在1887年不得不重做。那时，当时许多顶尖的物理学家基本上都接受了这个结果，即没有**以太风**。但对此该怎么办？当然，也许您证伪了**以太**的一些理论。您还没有证伪其他理论，人们开始着手开发这些理论。有趣的是，人们会将其描述为表明**以太**不存在。即使是“**以太**”这个词也是一种误称。实际上您有大量不同的理论和几个主要竞争者。所以是的，正在发生某种形式的**证伪**，但您如何回应这个新实验是非常复杂的。当然，当时顶尖的物理学家回应说：“好吧，这为我们提供了很多关于**以太**必须是什么的信息，但它并没有告诉我们没有**以太**。”事实上，**洛伦兹**在19世纪末，**爱因斯坦**之前，弄清楚了如何从一个参考系转换到另一个参考系的数学，并提出了**洛伦兹变换**，这是**狭义相对论**的基础。但他的解释是，如果您相对于**以太**移动，您正在从**以太**参考系转换到这些非特权的非**以太**参考系。他对**长度收缩**和**时间膨胀**的解释是，这是穿过**以太**运动的效果，并且您有这种压力。这种压力正在扭曲时钟。它正在扭曲长度测量。这里有趣的是，从实验上您无法区分**洛伦兹**的解释和**狭义相对论**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: He died, I think it was 1929 or so. It was the late twenties. He was still doing experiments in the 1920s about whether or not the **ether** existed. So he continued to believe in the **ether** to the end of his life. I think the last public statement he made was a year or two before he died, and he basically still believed it at that point. In fact, there was another physicist, **Miller**, who kept doing these experiments in the 1920s. He thought that if he went to a high enough altitude, **Mount Wilson** in California… "Oh, I'm high enough that the **ether winds** are not being dragged by the Earth. And I've measured the effect of the **ether**." **Einstein** hears about this and he says, and this is where you get the famous quote, "**Subtle is the Lord, but malicious He is not.**" Anyways, I think the reason the story is interesting is for many different reasons. One of the ways in which the real history of **science** is different from this idea you get of the **scientific method** is that you really can't apply **falsification** as easily as you might think. It's not clear what is being **falsified**. Is it just another version of the theory of the **ether** that's being **falsified**? Certainly you can't induce the theory of **special relativity** from the fact that one version of the **ether** seems to be disconfirmed by these experiments. It certainly doesn't show that ideas about **falsification** are wrong or falsified, but it does show that the most naive ideas… Things are often much more complicated than you think. **Michelson** did this experiment in 1881. He was a very young man, and then other people, I think **Rayleigh** was one of them, pointed out that there were some problems with the way he did it, so they had to redo it in 1887. At that point, a lot of the leading physicists of the day basically accepted this result, that there was no **ether wind**. But what to do about this? Sure, maybe you falsified some theories of the **ether**. There are others that you haven't falsified at all at this point, and people set to work on developing those. It is funny, people will phrase it as showing that the **ether** didn't exist. Even just the word "the" there is a misnomer. You actually had a ton of different theories and a couple of leading contenders. So yes, there's some version of **falsification** going on, but how you respond to this new experiment is very complicated. Certainly the leading physicists of the day responded by saying, "Okay, this gives us a lot of information about what the **ether** must be, but it doesn't tell us that there is no **ether**." In fact, **Lorentz** at the end of the 19th century, before **Einstein**, figures out the math of how you convert from one reference frame to another reference frame, and comes up with the **Lorentz transformations**, which is the basis of **special relativity**. But his interpretation is that you are converting from the **ether** reference frame to these non-privileged other reference frames if you're moving relative to the **ether**. His interpretation of **length contraction** and **time dilation** is that this is the effect of moving through the **ether**, and you have this pressure. This pressure is warping clocks. It's warping measures of length. The interesting thing here is that experimentally you cannot distinguish **Lorentz's interpretation** from **special relativity**.

</details>

**主持人**: 我认为这是一个强有力的陈述。

<details>
<summary>Original English</summary>

**主持人**: I think that's a strong statement.

</details>

**迈克尔·尼尔森**: **洛伦兹**引入了这个称为**本地时间**的量，他认为……我的理解是，他并不是想给出它的物理解释，但**爱因斯坦**后来只是将其识别为另一个惯性参考系中的时间。他并不是想赋予它多少物理意义。我认为**庞加莱**后来更接近于意识到这就是时钟所记录的时间。大约四十多年后，人们开始进行**μ子实验**，他们看到宇宙射线撞击大气层顶部。它们产生一束**μ子**，您可以在大气层不同高度观察还剩下多少**μ子**。它们会随时间衰变，而一个非常奇怪的事情发生了，那就是它们的衰变速度太慢了。您预期它们根本不应该能够穿过整个大气层。如果是在经典理论中，它们的衰变速率太快了。但如果事实上它们的时间真的变慢了，那就没问题了。事实上，1940年测量的衰变速率——此后进行了更精确的实验——与**狭义相对论**的预期完全吻合。这种情况下，如果**洛伦兹**还活着——他当时已经去世十年左右了——他很可能会试图通过再次修补他的理论来挽救它，但这将是一个巨大的挫折。它开始看起来就像时间——**洛伦兹**作为数学便利而引入的这个东西——对于**μ子**来说，这实际上就是时间。然后还有一大堆其他实验显示了这种非常相似的现象。

<details>
<summary>Original English</summary>

**Michael Nielsen**: **Lorentz** introduces this quantity called **local time**, which he regards as... My understanding is he's not trying to give a physical interpretation of this, but it's what **Einstein** would later just recognize as time in another inertial reference frame. He's not trying to attribute much physical meaning to it. I think **Poincaré** gets much closer later on to realizing that this is the time that's registered by clocks. About forty-odd years later, people start doing these **muon experiments** where they see cosmic rays hit the top of the atmosphere. They produce a shower of **muons**, and you can look to see at different heights in the atmosphere how many of those **muons** remain. They decay over time, and a very strange thing happens, which is that they're decaying way too slow. You expect they shouldn't be able to last the whole way through the atmosphere at all. Their decay rate is too quick, if you were in a classical theory. But if in fact their time really has slowed down, it's okay. In fact, the measured decay rates in **1940**—and there have since been more accurate experiments done—match exactly what you expect from **special relativity**. That's the kind of thing where if **Lorentz** had been alive—he'd been dead ten or so years at that point—it seems quite likely that he would have tried to save his theory by patching it up yet again, but it would have been a massive setback. It starts to just look like time—this thing that **Lorentz** introduced as a mathematical convenience—that's actually what time is, for the **muons** at least. Then there's a whole bunch of other experiments that show this very similar phenomenon.

</details>

**主持人**: 那个实验是什么时候做的？

<details>
<summary>Original English</summary>

**主持人**: When was that experiment done?

</details>

**迈克尔·尼尔森**: 我想是1940年。可能在1941年发表。

<details>
<summary>Original English</summary>

**Michael Nielsen**: That was, I think, 1940. It might have been published in 1941.

</details>

**主持人**: 也许重新措辞和改变我的主张：并不是说您无法区分它们，而是科学界在这些实验被实际证明是首选之前，就采纳了我们事后认为是更正确的解释。因此，人类科学显然有一个过程可以区分不同的理论。

<details>
<summary>Original English</summary>

**主持人**: Maybe to rephrase and change my claim: it's not that you could not have distinguished them, but the scientific community adopted what we in retrospect consider the more correct interpretation before it was actually experimentally shown to be preferred. So there's clearly some process that human science does which can distinguish different theories.

</details>

**迈克尔·尼尔森**: 我能打断一下吗？您使用了“**过程**”这个词，思考这个词很有趣。**过程**带有预先设定的含义。在实践中它要复杂得多。您有像**洛伦兹**这样的人，**爱因斯坦**绝对彻底地钦佩他，还有**庞加莱**，有史以来最伟大的科学家之一，以及**迈克尔逊**，另一位真正杰出的科学家，他们从未完全接受。这并不是说我们都在使用某种标准程序来调和这些事情。伟大的科学家在科学界普遍改变观点之后，可能在很长一段时间内仍然是错误的。但没有集中化的权威或集中化的方法。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Can I just interrupt? You used the word process, and it's interesting to think about that term. Process carries connotations of something set in advance. It's much more complicated in practice. You have people like **Lorentz**, who **Einstein** absolutely and utterly admired, and **Poincaré**, one of the greatest scientists who ever lived, and **Michelson**, another truly outstanding scientist, who never reconciled themselves. It's not as though there's some standard procedure that we're all using to reconcile these things. Great scientists can remain wrong for a very long time after the scientific community has broadly changed its opinion. But there's no centralized authority or centralized method.

</details>

**主持人**: 这就是有趣的地方。尽管很难阐明它发生的**过程**，所使用的**启发式方法**，但仍然存在**进步**。您提到了**庞加莱**。**洛伦兹**数学上是对的，但解释错了。**庞加莱**似乎相反，他理解很难定义**同时性**，因为它需要一个与时间或可能同时到达中点的物体速度的循环定义，而速度又是用时间定义的。我觉得这很有趣。我们还可以举几个其他例子。在**科学史**上，存在这样一种现象：有人提出了正确的问题，但他们没有坚持下去。我很好奇您认为这些情况下发生了什么。

<details>
<summary>Original English</summary>

**主持人**: That is the interesting thing. There's **progress** even though it is hard to articulate the **process** by which it happens, the **heuristics** that are used. You mentioned **Poincaré**. **Lorentz** has the math right, but the interpretation wrong. It seems like **Poincaré** had the opposite, where he understood that it's hard to define **simultaneity** because it requires a circular definition with time, or velocity of something that might arrive at a midpoint together, but velocity is defined in terms of time. I find this interesting. There are a couple of other examples we could call on. There is this phenomenon in the history of **science** where somebody asks the right question, but then they don't clinch it. I'm curious what you think is happening in those cases.

</details>

**迈克尔·尼尔森**: 您确实想逐案地去理解。不一定清楚他们在所有情况下都犯了同样的错误。**庞加莱**的案例令人惊叹。他似乎理解了**相对性原理**，即**物理定律**在所有惯性参考系中都是相同的。他似乎理解了**光速**在所有惯性参考系中都是相同的。他没有那样措辞，但据我所知，尽管我不会法语。这些基本上是**爱因斯坦**用来推导**狭义相对论**的思想。但随后他又有一个额外的误解，他认为**长度收缩**是一种动力学效应，即粒子不知何故被某种外力推在一起，某种动力学作用正在发生。他不明白这纯粹是**运动学**。实际上**空间和时间**与我们所想的不同，您需要从根本上重新思考这些事物。他简直是知道得太多了。他心中有一个几乎过于宏大的愿景。**爱因斯坦**从中减去，并说：“不。**空间和时间**只是与我们所想的不同，这是正确的图景。”1909年有一篇论文，我想是**庞加莱**仍然持有这种关于**长度收缩**的动力学图景。这根本没有必要。从现代角度来看，这是一个错误。他为什么这样做？他为什么 clinging onto 这个想法？我不知道。我显然从未见过他。能够和他讨论并试图理解会非常有趣。他的专业知识似乎阻碍了他。他知道这么多，理解这么多，然后他无法放弃这些东西。一个非常有趣的事实是，几年前，在19世纪90年代，**爱因斯坦**还是个青少年，他也相信**以太**。他知道这些东西。但他不像那些老年人那样执着。也许他们有点是自己专业知识的囚徒。这是我的猜测。一些**科学史**家肯定会不同意。然后有一些显而易见的故事，**爱因斯坦**本人后来据说因为自己的执着，没有接受**量子力学**或**宇宙学**的正确解释。

<details>
<summary>Original English</summary>

**Michael Nielsen**: You actually do want to go case by case and try to understand. It's not necessarily clear that they're doing the same thing wrong in all of the cases. The **Poincaré** case is amazing. He seems to have understood the **principle of relativity**, the idea that the laws of physics are the same in all inertial reference frames. He seems to have understood that the speed of light is the same in all inertial reference frames. He doesn't phrase it quite that way, but it is my understanding, though I don't speak French. These are basically the ideas that **Einstein** uses to deduce **special relativity**. But then he also has this additional misunderstanding where he thinks that **length contraction** is a dynamical effect, that somehow particles are being pushed together by some external force, something is going on dynamically. He doesn't understand that it's purely **kinematics**. That actually **space and time** are different from what we thought, and you need to fundamentally rethink those things. It's almost like he knew too much. He had almost too grand a vision in mind. **Einstein** subtracts from that and says, "No. **Space and time** are just different than what we thought, and here's the correct picture." There's a paper in, I think it's 1909, where **Poincaré** still has this dynamical picture of what's going on with the **length contraction**. This is just not necessary. This is a mistake from the modern point of view. Why is he doing this? Why is he clinging onto this idea? I don't know. I've obviously never met the man. It would be fascinating to be able to talk it over and try and understand. His expertise seems to be getting in the way. He knows so much, he understands so much, and then he's not able to let go of these things. A really interesting fact is that a few years prior, in the 1890s, **Einstein**'s a teenager and he believes in the **ether** too. He knows about this stuff. But he's not quite as attached as these older people were. Maybe they were a little bit prisoners of their own expertise. That's my guess. Some **historians of science** would certainly disagree. Then there's the obvious stories where **Einstein** himself later on is said to have not latched onto the correct interpretations of **quantum mechanics** or **cosmology** because of his own attachments.

</details>

**主持人**: 是的。这是我更大的问题。**μ子**的例子很好地说明了这些漫长的**验证循环**以及科学界似乎比这些**验证循环**所暗示的更快地发生进步。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Here’s the bigger question I have. The **muon** example is a great example of these long **verification loops** and how progress seems to happen in the scientific community faster than these **verification loops** imply.

</details>

### 日心说与牛顿的引力理论

**主持人**: 也许最清楚的例子是公元前二世纪的**阿里斯塔克斯**提出了**日心说**。古雅典人驳斥了它，理由是如果太阳真的是太阳系的中心，那么当地球绕太阳运动时，我们应该看到恒星相对于地球移动。唯一不会发生这种情况的原因是恒星太远，以至于您无法观察到这种现象。直到1838年才实际测量到**恒星视差**。所以，我们不需要等到1838年才接受**日心说**。我们不需要等待实验验证才能理解**哥白尼**在某种程度上更好。事实上，当**哥白尼**首次提出他的理论时，众所周知，**托勒密模型**更准确，因为它在几个世纪里不断添加**本轮**。可能不太为人所知的是，它在某种意义上也更简单。因为**哥白尼**实际上不得不添加额外的**本轮**。它比**托勒密模型**有更多的**本轮**，因为他有这种偏见，认为地球应该以等时速在完美的圆圈中运行。总之，我认为这是一个有趣的故事，因为它不是一个更准确的理论。它也不是一个更简单的理论。那么您是如何事先知道**哥白尼**是正确的而**托勒密**是错误的呢？

<details>
<summary>Original English</summary>

**主持人**: Maybe the clearest example is **Aristarchus** in the second century BC comes up with the idea of **heliocentrism**. The ancient Athenians dismiss it on the grounds that we should see as the Earth is moving around the Sun, if really the Sun is the center of the solar system, the stars move relative to the Earth. The only reason that would not be the case is the stars are so far away that you would not observe this. And it's only in **1838** that **stellar parallax** was actually measured. And so, we didn't need to wait until **1838** to have **heliocentrism**. We didn't need to wait for the experimental validation to understand that **Copernicus** is better in some way. In fact, when **Copernicus** first came up with his theories, it's well known that the **Ptolemaic model** was more accurate because it had centuries of adding on these **epicycles**. What's maybe less well appreciated is that it was also in some sense simpler. Because **Copernicus** actually had to add extra **epicycles**. It had more **epicycles** than the **Ptolemaic model** because he had this bias that the Earth should go in a perfect circle in equal time. Anyway, I think this is an interesting story because it's not a more accurate theory. It's not a simpler theory. So how could you have known ex ante that **Copernicus** was correct and **Ptolemy** was not?

</details>

**迈克尔·尼尔森**: 好问题。我并不完全知道答案。我能给您一个部分答案，这个答案在几个世纪后对我来说非常有说服力。我相信它至少是历史故事的一部分。**牛顿**的一个巨大冲击是，他最终理解了**开普勒定律**，所以您能够解释天空中行星的运动。但他也从相同的理论，他的**引力理论**中，能够解释**地球运动**。他能够解释物体在地球上以**抛物线**运动的原因，他能够根据月球和太阳对地球水体的**引力效应**来解释**潮汐**。您有三个看似非常不同、不相关的现象，都被这一套想法所解释。这开始让人觉得非常有说服力，至少对我而言。我认为大多数人一旦最终意识到这一点，都会感到非常满意。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Good question. I don't entirely know the answer. I can give you a partial answer that I, centuries in the future, start to find very compelling. I'm sure it's part of the historic story at least. One of the big shocks for **Newton**, he did understand **Kepler's laws of motion** eventually, so you're able to explain the motions of the planets in the sky. But he also, out of the same theory, his **theory of gravitation**, was able to explain **terrestrial motion**. He's able to explain why objects move in **parabolas** on the Earth, and he's able to explain the **tides** in terms of the moon and the sun's **gravitational effect** on water on the Earth. You have what seem like three very different disconnected phenomena all being explained by this one set of ideas. That starts to feel very compelling, at least to me. I think most people find that very satisfying once they eventually realize it.

</details>

**主持人**: 您读过**凯恩斯**的**牛顿**传记吗？

<details>
<summary>Original English</summary>

**主持人**: Have you read the **Keynes biography** of **Newton**?

</details>

**迈克尔·尼尔森**: 他写了整本传记吗？

<details>
<summary>Original English</summary>

**Michael Nielsen**: He wrote an entire biography?

</details>

**主持人**: 不，是那篇**文章**。

<details>
<summary>Original English</summary>

**主持人**: No, the essay.

</details>

**迈克尔·尼尔森**: 当然。我喜欢那个。他被描述为**最后的魔术师**，这太棒了。事实上，我认为这也许值得叠加。或者您应该读出其中那段话。好的。那是他在剑桥去世前不久的一次演讲中说的。他不知何故得到了**牛顿**的论文，并就此讲了两次课，或者他的兄弟**杰弗里**另一次讲了，因为他病得太重了。中间有一段非常棒的引述。整件事都非常有趣，但我喜欢这个特别的引述：“**牛顿**不是理性时代的第一个人。他是**最后的魔术师**，是最后一个以与一万年前开始构建我们智力遗产的人相同的眼光看待可见世界和智力世界的伟大思想。”人们认为**牛顿**是第一个现代科学家的这种观点在某种程度上是错误的。它有一些道理，但他确实有这种非常不同的世界观，一部分是迷信，一部分是现代。这是一个有趣的混合体。从某种意义上说，他是一个过渡人物。“**最后的魔术师**”这个短语确实指出了一些东西。我对**牛顿**非常好奇的是，他是否将应用于炼金术工作的相同程序、相同**启发式**、相同偏见应用于他对天文学的理解。这来自**凯恩斯**的文章：“他的疯狂中存在着极端的条理。他所有未发表的关于秘术和神学著作都以仔细的学习、准确的方法和极其克制的陈述为标志。如果它们全部内容和目的不是魔术性的，它们就和《**数学原理**》一样理智。它们几乎都是在他进行数学研究的同25年里创作的。”显然，存在某种**美学**，促使像**爱因斯坦**这样的人拒绝早期的思维方式，并说：“不，另一种是错误的，有一种更好的思考方式。”**牛顿**也是如此。我的问题是，对**节俭**、**美学**等的相似**启发式**是否在不同时间和不同学科中同样有用，或者您需要不同的**启发式**。这之所以相关，是因为即使我们无法为科学构建**验证循环**，也许如果**品味测试**指向同一方向，您至少可以将这种偏见编码到**AI**中。那可能就足够了。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Sure. I love that. This description of him as the **last of the magicians** is wonderful. In fact, I think it's maybe worth superimposing. Or you should read out that one passage of the thing. Alright. It's from a talk that he gave at Cambridge not long before he died. He'd acquired **Newton's papers** somehow and gave a lecture twice about this, or his brother **Jeffrey** gave it the other time because he was too ill. There's this wonderful, wonderful quote in the middle. The whole thing is really interesting, but I love this particular quote: "**Newton** was not the first of the age of reason. He was the **last of the magicians**, the last great mind which looked out on the visible and intellectual world with the same eyes as those who began to build our intellectual inheritance rather less than ten thousand years ago." This idea people have that **Newton** was the first modern scientist is somehow wrong. There's some truth to it, but he really had this very different way of looking at the world that was part superstitious and part modern. It was a funny hybrid. He's a transitional figure in some sense. That phrase, "the last of the magicians," really points at something. The thing I'm very curious about with **Newton** is whether it was the same program, the same **heuristics**, the same biases that he applied to his **alchemical work** as he did to his understanding of astronomy. This is from the **Keynes essay**: "There was extreme method in his madness. All his unpublished works on esoteric and theological matters are marked by careful learning, accurate method, and extreme sobriety of statement. They are just as sane as the **Principia** if their whole matter and purpose were not magical. They were nearly all composed during the same 25 years of his mathematical studies." Clearly, there was some **aesthetic** that motivated people like **Einstein** to reject earlier ways of thinking and say, "No, the other is wrong, and there's a better way to think about things." The same is true with **Newton**. The question I have is whether similar **heuristics** toward **parsimony**, **aesthetics**, and so on, would be equally useful across time and across disciplines, or whether you need different **heuristics**. The reason that's relevant is even if we can't build a **verification loop** for **science**, maybe if the **taste tests** point in the same direction, you can at least encode that bias into the **AIs**. That would maybe be enough.

</details>

### 科学瓶颈与AI加速

**迈克尔·尼尔森**: 关键在于，我们总是遇到**瓶颈**的地方是以前的**过程**和**启发式方法**不适用的地方。这几乎是**瓶颈**的定义。因为人们很聪明，他们知道以前有效的方法。他们研究它。他们应用相同的方法，所以他们不会卡在以前的地方。他们只是不断地卡在不同的地方。我有点过于概括了，但我认为这是对的。如果您试图将**科学**简化为一个**过程**，您就是在试图将其简化为一种只有**方法**可以应用的东西，然后您摇动曲柄，灵感就蹦出来了。您可以在一定程度上做到这一点，但您会在现有方法不适用的地方遇到**瓶颈**。从定义上讲，没有可以转动的曲柄。您需要很多人尝试不同的想法。想法越难产生，**瓶颈**越大，但随之而来的胜利也越大。**量子力学**就是一个很好的例子。它是一套令人震惊的想法。它是一个令人震惊的理论。**进化论**在某种意义上也是一个令人震惊的想法，不是自然选择的原则，而是它能解释如此之多。这是一个令人震惊的想法。

<details>
<summary>Original English</summary>

**Michael Nielsen**: The point is that where we always get **bottlenecked** is where the previous **processes** and **heuristics** don't apply. That's almost definitionally what causes the **bottlenecks**. Because people are smart, they know what has worked before. They study it. They apply the same kinds of things, so they don't get stuck in the same places as before. They keep getting **bottlenecked** in different places. I'm overgeneralizing a bit, but I think it's right. If you're attempting to reduce **science** to a **process**, you're attempting to reduce it to something where there is just a **method** which you can apply, and you turn the crank and out pops insight. You can do a certain amount of that, but you're going to get **bottlenecked** at the places where your existing **method** doesn't apply. Definitionally, there's no crank you can turn. You need a lot of people trying different ideas. The more difficult the idea is to have, the greater the **bottleneck**, but then also the greater the triumph. **Quantum mechanics** is a great example of this. It's such a shocking set of ideas. It's such a shocking theory. The **theory of evolution** in some sense is also quite a shocking idea, not the principle of natural selection, but that it can explain so much. That's a shocking idea.

</details>

**迈克尔·尼尔森**: 现有的安全基准声称，至少对于今天的顶级模型，攻击只有百分之几的成功率。这听起来很棒，但**Labelbox**的研究人员能够在大约90%的时间内**越狱**这些相同的模型——即使是那些拥有最强安全声誉的模型。这里脱节的原因是，支撑这些公共安全基准的提示都以一种非常幼稚的方式构建。没有试图掩盖有害意图。这些提示只会要求模型“入侵安全网络”并“在不被发现的情况下完成”。但真正的恶意行为者不会这样写。所以**Labelbox**从头开始建立了一个新的安全基准。他们的提示通过剥离明显的触发短语并将请求包装在虚构场景中来反映真实的对抗行为。例如，提示不会直接要求**LLM**窃取某人的身份，而是将其构架为一场游戏。一个试图躲避黑暗势力的**光之使者**需要一本关于如何伪装成别人的手册。这项安全研究已在描述中链接。如果您认为这可能对您的工作有用，请访问labelbox.com/dwarkesh。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Existing safety benchmarks claim that, at least for today's top models, attacks are only successful a few percent of the time. This sounds great, but **Labelbox** researchers were able to **jailbreak** these very same models about 90% of the time – even the ones that have the strongest reputation for safety. And the disconnect here is that the prompts which underlie these public safety benchmarks are all framed in a very naive way. There's no attempt to disguise harmful intent. These prompts will just ask models to “hack into a secure network” and to “do so without getting caught”. But real bad actors don't write like this. So **Labelbox** built a new safety benchmark from the ground up. Their prompts reflect real adversarial behavior by stripping out obvious trigger phrases and wrapping their request in fictional scenarios. For example, instead of outright asking an **LLM** to steal somebody's identity, the prompt will frame it as a game. A light bearer who's trying to hide from dark forces needs a handbook on how to disguise themselves as somebody else. This safety research is linked in the description. If you think this could be useful for your own work, reach out at labelbox.com/dwarkesh.

</details>

**主持人**: 所以《**数学原理**》于1687年发布。《**物种起源**》于1859年发布。至少从表面上看，**达尔文**的**自然选择理论**在概念上比**引力理论**更容易。我问过**陶哲轩**这个问题。与**达尔文**同时代有一位生物学家**托马斯·赫胥黎**，他读完后说：“怎么这么愚蠢，竟然没想到这个。”没有人读《**数学原理**》会想：“天哪，我为什么没能抢在**牛顿**之前？”那么这里发生了什么？为什么**达尔文主义**花费了更长时间？

<details>
<summary>Original English</summary>

**主持人**: So **Principia Mathematica** is released in 1687. **The Origin of Species** is released in 1859. At least naively, it seems like **Darwin's theory of natural selection** is conceptually easier than the **theory of gravity**. I asked **Terence Tao** this question. There was this contemporaneous biologist with **Darwin**, **Thomas Huxley**, who read this and said, "How extremely stupid to not have thought of this." Nobody ever reads the **Principia Mathematica** and thinks, "God, why didn't I beat **Newton** to the punch here?" So what's going on here? Why did **Darwinism** take so much longer?

</details>

**迈克尔·尼尔森**: 这个想法一定在动物饲养者中存在了很长时间，或者说大部分想法是已知的，即**人工选择**是真实存在的。从某种意义上说，**达尔文**的天才之处不在于拥有这个想法，而在于理解它对**生物学**的重要性。您可以回溯并用它来解释我们世界上看到的所有多样性，这不一定是唯一的原则，但肯定是一个核心原则。他写了这本很棒的书《**物种起源**》。里面有如此多的证据和如此多的例子，试图阐明这一点并查看其含义，并将其与他所能连接到的其他事物，如**地质学**等联系起来。他所做的就是努力证明它实际上与整个**生物圈**息息相关。他不仅仅是有一个想法，他正在令人信服地证明它与一切事物交织在一起。

<details>
<summary>Original English</summary>

**Michael Nielsen**: The idea must have been known to animal breeders for a long time at some level, or certainly large chunks of the idea were known, that **artificial selection** was a thing. In some sense, **Darwin's genius** wasn't in having that idea, it was understanding just how central it was to **biology**. You can go back and explain a tremendous amount about all the variety of what we see in the world with this as not necessarily the only principle, but certainly a core principle. He writes this wonderful book, **The Origin of Species**. It's just so much evidence and so many examples, trying to tease this out and see what the implications are, and connecting it to as much else as he possibly can, to **geology** and all these other things. That hard work—making the case that it's actually relevant all across the **biosphere**—is what he's doing there. He's not just having the idea, he's making a compelling case that it's intertwined with absolutely everything else.

</details>

**主持人**: 这个问题的动机是**卢克莱修**，这位公元一世纪的罗马诗人，他有一个似乎与**自然选择**类比的想法。它是关于物种随着时间的推移越来越适应其环境，或者物种对环境的适应性下降。那么，为什么这十九个世纪都没有进展呢？然后我研究了一下，或者更准确地说，我问**LLM**，**卢克莱修**的这个想法到底是什么。它与真正的**自然选择**截然不同。他认为过去有一个**生成期**，所有物种都产生了，然后有一个一次性**过滤器**，产生了今天存在的物种，它们适应了环境。他没有这个想法，即这是一个持续渐进的**过程**，或者地球上所有生命形式都通过**生命之树**连接在一起，顺便说一句，这是一个令人难以置信的奇怪事实，即地球上每一个生命形式都有一个**共同祖先**。

<details>
<summary>Original English</summary>

**主持人**: The motivation for the question was **Lucretius**, this first-century Roman poet who has an idea that seems analogous to **natural selection**. It's about species getting fitted more over time to their environments, or species losing fit to their environment. And so, why did this go nowhere for nineteen centuries? Then I looked into it or, more accurately, asked **LLMs** what exactly **Lucretius's idea** here was. It is extremely different from what real **natural selection** is. He thought there was this **generative period** in the past where all the species came about, and then there was this **one-time filter** which resulted in the species that are around today, and they became fit to the environment. He did not have this idea that it is an ongoing gradual process or that there is a **tree of life** that connects all life forms on Earth together, which, by the way, is an incredibly weird fact that every single life form on Earth has a **common ancestor**.

</details>

**迈克尔·尼尔森**: 这并不奇怪。如果您认为生命的起源一定非常艰难，存在一个**瓶颈**，那么这就不那么令人惊讶了。

<details>
<summary>Original English</summary>

**Michael Nielsen**: It's not incredibly weird. If you think that the **origin of life** must have been very hard, that there's a **bottleneck** there, then it's not so surprising.

</details>

**迈克尔·尼尔森**: 还有**验证循环**的这一方面，即使**牛顿**在某种意义上可能更难，如果您掌握了它，您就可以实验性地……我知道“验证”在哲学上是错误的词，但您可以为这个理论提供大量的基本观点。您可以说：“好吧，我对地球上物体为何坠落有一个想法。我对行星的**轨道周期**为何具有某种模式有一个想法。让我们在绕地球运行的月球上试试。”事实上，这很奇怪，但**轨道周期**与我的计算结果相符。而且潮汐也正确。这简直太棒了。

<details>
<summary>Original English</summary>

**Michael Nielsen**: There's also this **verification loop** aspect where even if **Newton** might be harder in some sense, if you've clinched it, you can experimentally… I know "validate" is the wrong word philosophically, but you can give a lot of base points to the theory. You can be like, "Okay, I have this idea of why things fall on Earth. I have this idea of why **orbital periods** for planets have a certain pattern. Let's try it on the **Moon**, which orbits the Earth." And in fact, it’s weird but the **orbital period** matches what my calculations imply. And the **tides** work correctly. It's just amazing.

</details>

**主持人**: 完全正确。而对于**达尔文主义**，**达尔文**需要大量的工作来汇编所有累积的证据，但没有哪一块证据具有压倒性的力量。而且还有一大堆问题。他并没有真正理解**机制**是什么。他不懂**基因**，所有这些东西。**达尔文主义**史上一个非常有趣的事情是，这个理论上随时都可能出现的想法，在**阿尔弗雷德·华莱士**和**查尔斯·达尔文**之间几乎完全相同地独立产生。以至于我想**华莱士**把他的手稿寄给了**达尔文**，然后说：“您觉得这个想法怎么样？”**达尔文**说：“糟糕。”我认为这不是原话，但差不多是这个意思。他们本着体育精神最终一起提出了他们的想法。为什么19世纪50年代或60年代是这些想法形成的正确时机？您可以提出不同的想法。一个是**地质学**。在19世纪30年代，**查尔斯·莱尔**发现地球存在了数百万甚至数十亿年。**古生物学**表明**化石**在整个时间段内都存在。生命历史悠久。事实上，您甚至可以找到**中间物种**的**化石**，向您展示**生命之树**。在人类和其他猿类之间，也有**中间人类**。还有殖民时代，我们有所有这些进行**生物地理学**的航海。所有这些都必须是必要的。事实上，在**科学史**上，存在着大量的**并行创新**和**发现**。所以，这也许是另一个证据，表明一个给定想法被发现需要更多条件到位。因为如果它长时间没有被发现，然后许多不同的人自发地想出了它，这表明构建模块在某种意义上是必要的。**莱尔**和其他地质学家在19世纪初提出**深层时间**的想法似乎至关重要。我知道**达尔文**深受**莱尔**的影响。如果您没有至少数千万或数亿年的时间，**进化论**就会显得站不住脚。为了让它在**主教乌舍尔**的5000到10000年或6000年的时间尺度内起作用，您需要在人类生命周期内看到大规模的**进化**，而我们并没有看到这一点。这似乎是一个阻碍。至于您的问题，还有哪些阻碍，我不知道。或者原则上，如果您更聪明，您可以多早提出它？

<details>
<summary>Original English</summary>

**主持人**: Exactly. Whereas for **Darwinism**, it takes a ton of work for **Darwin** to compile all the cumulative evidence, but there's no individual piece that is overwhelmingly powerful. And there's a whole bunch of problems as well. He doesn't really understand what the **mechanism** is. He doesn't understand **genes**, all these things. The very interesting thing in the history of **Darwinism** is, this idea which theoretically you could come up with at any time, there is almost identical independent creation of that idea between **Alfred Wallace** and **Charles Darwin**. So much so that I think **Wallace** sends his manuscript to **Darwin** and is like, "What do you think of this idea?" And **Darwin**'s like, "Fuck." I don't think that's an exact quote, but it's pretty much correct. They end up presenting their ideas together in the spirit of sportsmanship. Why was this period in the 1850s or 1860s the right time for these ideas to form? You can come up with different ideas. One is **geology**. In the 1830s, **Charles Lyell** figures out that there's been millions and billions of years of time that's existed on Earth. The **paleontology** shows you that **fossils** have existed for that entire time. Life goes back a long way. In fact, you can even find **fossils** for **intermediate species** that show you the **tree of life**. Between humans and other apes as well, there's **intermediate humans**. There's also the **age of colonization**, and we have all these voyages doing **biogeography**. That all must have been necessary. In fact, there's a huge history of **parallel innovation** and **discovery** in the history of **science**. So maybe it is another piece of evidence that more had to be in place for a given idea to be discovered. Because if it's not discovered for a long time and then spontaneously many different people are coming up with it, that shows you that the building blocks were in some sense necessary. This example of **Lyell** and other geologists in the early 1800s having this idea of **deep time** does seem to have been crucial. I know **Darwin** was very influenced by **Lyell**. If you don't have at least tens or hundreds of millions of years, **evolution** starts to look like a non-starter. In order to make it work on a timescale of 5,000 to 10,000 years or 6,000 years with **Bishop Ussher** you would need to see **evolution** occurring at a massive rate during human lifetimes, and we're just not seeing that. That does seem to have been a **blocker**. To your question of what other **blockers** were there, were there any others? I don't know. Or how much earlier could you, in principle, have come up with it if you were much smarter?

</details>

### AlphaFold与科学理论的解释力

**主持人**: 让我们回到您最初关于**AI**中**验证循环**的问题。一个应该让您停下来思考的例子是迄今为止最大的成功，那就是**AlphaFold**。**AlphaFold**真的不是关于**AI**。其成功的绝大部分是**蛋白质数据库**。它是**X射线衍射**、**核磁共振**、**冷冻电镜**，以及花费数十亿美元获得的18万多个**蛋白质结构**。这基本上是关于我们如何花费数十年时间仅仅通过在实验中努力观察世界来获取**蛋白质结构**，然后我们在最后拟合了一个漂亮的**模型**，这只占总投资的一小部分。这主要是一个**数据采集**的故事。**AI**部分令人印象深刻且相当了不起，但它只是整个故事的一小部分。**AlphaFold**非常有趣，从哲学角度看，我想知道您如何看待它作为一个**科学理论**或**解释**。我想随着时间的推移，世界变得越来越难以理解……当我说话时，因为您是一位非常谨慎的说话者，我说出一个短语，然后想知道您是否真的会认同这个前提。但在某些领域，我们需要将**模型**拟合到事物上，而不是提出解释广泛现象的**基本原理**。将**广义相对论**或任何最终归结为一些方程的理论，与**AlphaFold**进行比较，后者正在编码我们甚至无法在1亿多个参数中解释的不同关系。这些真的是一回事吗？**广义相对论**可以预测您从未预料到或从未打算做的事情，例如**水星轨道**的进动。**AlphaFold**不会有那种解释范围。我想听听您对此的看法。

<details>
<summary>Original English</summary>

**主持人**: Let's go back and zoom out to your original question about the **verification loop** in **AI**. An example that should give you pause there is the big signature success so far, which is certainly **AlphaFold**. **AlphaFold** really isn't about **AI**. A massive fraction of the success there is the **Protein Data Bank**. It's **X-ray diffraction**, **NMR**, **cryo-EM**, and the several billion dollars that were spent obtaining those 180,000-odd **protein structures**. It's basically the story of how we spent many decades obtaining **protein structure** just by going out and looking very hard at the world experimentally, and then we fitted a nice **model** at the end of it, which was a tiny fraction of the entire investment. That's a story of **data acquisition** principally. The **AI** bit is very impressive and quite remarkable, but it is only a small part of the total story. **AlphaFold** is very interesting, and philosophically I wonder what you think of it as a **scientific theory** or **explanation**. I guess over time the world is becoming harder to understand… As I'm saying things, because you're such a careful speaker, I say a phrase and wonder if you'll actually buy that premise. But in some domains, we need to fit **models** to things rather than coming up with underlying principles that explain a broad range of phenomena. Compare the **theory of general relativity**, or any theory which just nets out to some equations, versus **AlphaFold**, which is encoding these different relationships between things we can't even interpret over 100 million parameters. Are those really the same thing? **GR** can predict things you could have never anticipated or it was never meant to do, like why **Mercury's orbit** precesses. **AlphaFold** is not going to have that kind of explanatory reach. I want to get your reaction to that.

</details>

**迈克尔·尼尔森**: 我认为这是一个极其有趣的问题。也许是一个非常关键的问题。如果您持非常经典的观点，您会想要这些深刻的**解释性原理**。您会希望尽可能少的**自由参数**。您会希望非常简单的**模型**能够解释很多东西，而**AlphaFold**看起来完全不像那样。您可能会说：“它很好，也许作为一个**模型**很有用，但它不是一个**科学解释**。”这是一个保守的观点，对这个问题的第一个答案。第二个答案是，也许您不应该把**AlphaFold**看作经典意义上的**解释**，但它内部可能包含许多小的**解释**。您可以通过**可解释性工作**从**AlphaFold**中提取某些东西。也许通过对**AlphaFold**进行**考古学**，我们实际上可以更多地理解这些原理。您可以开始提取某个**电路**做了一些有趣的事情，然后我们从中学习。我不知道在**AlphaFold**上做到什么程度，但在某些**象棋模型**上已经做了一些，比如**AlphaZero**。**马格努斯·卡尔森**似乎借鉴了一些策略，他似乎是从**AlphaZero**中学到的。我认为这没有任何公开证实，但一些专家注意到，在一些关于**AlphaZero**如何工作的公开法医分析发布后，他的下棋风格发生了相当大的变化。这是一个例子，人类开始从这些**模型**中提取意义。这导致我们将**模型**视为潜在的**解释来源**。您需要做更多的工作，因为它们一开始并不容易理解，但您可以潜在地提取它们。这是一个有趣的中间情况，它们本身不是**解释**，但您可以从中提取有趣的**解释**，并将它们作为**来源**。第三种也是最有趣的可能性是，它们是一种新类型的**对象**。它们应该被认真地视为**解释**，但过去我们无法真正对它们做任何事情，现在我们可以做一些有趣的新操作。我们可以合并它们，我们可以提炼它们。这是**科学哲学**中的一个巨大机遇。这在某种程度上是预料之中的。今天一些数学家和物理学家在工作……从历史上看，如果您有一个100页的方程——这是确实会出现的情况——如果是在1920年，您就无能为力了。那时，您就会放弃这个问题。但今天，有了**Mathematica**这样的工具，您可以继续下去。那现在是一个**对象**，您可以处理的东西。有一些例子，人们处理这些以前被认为过于复杂的东西，有时他们会得到简单的答案。这只是一个中间工作状态。所以我想知道在这种情况下是否会发生类似的事情，您可以将这些**模型**像人们使用**Mathematica**一样使用它们，并认真对待它们。它们不是经典意义上的**解释**，但它们将是其他一些可以进行有趣操作的东西。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think it's an incredibly interesting question. Maybe a really pivotal question. If you take a very classic point of view, you want these deep **explanatory principles**. You want as few **free parameters** as you possibly can. You want very simple **models** which explain a lot, and **AlphaFold** doesn't look anything like that. You might just say, "It's nice and maybe helpful as a **model**, but it's not a **scientific explanation**." That's a conservative point of view, answer one to the question. Answer two is to say maybe you shouldn't think about **AlphaFold** as an **explanation** in the classic sense, but maybe it contains lots of little **explanations** inside it. Part of what you can get out of **interpretability work** is you can go into **AlphaFold** and start to extract certain things. Maybe by doing an **archeology of AlphaFold**, we can actually understand a great deal more about these principles. You can start to extract that a certain **circuit** does this interesting thing, and we learn from it. I don't know to what extent that's been done with **AlphaFold**, but it's been done a little bit with some of the **chess models**, like **AlphaZero**. There seem to be some strategies which were borrowed by **Magnus Carlsen**, which he seems to have just taken from **AlphaZero**. I don't think there's any public confirmation of this, but some experts have noticed that he changed his game quite radically after some public forensics were released on how **AlphaZero** worked. That's an example where human beings are starting to extract meaning out of these **models**. That leads to viewing the **models** as a potential source of **explanations**. You need to do more work because they're not very legible up front, but you can potentially extract them. That's an interesting intermediate situation where they're not **explanations** themselves, but you can extract interesting **explanations** out of them and use them as a source. The third and most interesting possibility is that they're a new type of object. They should be taken very seriously as **explanations**, but where in the past we haven't had the ability to really do anything with them, now we have interesting new actions we can do. We can merge them, we can distill them. It's a big opportunity in the **philosophy of science**. There's an anticipation of this in some way. Some mathematicians and physicists work today… Historically, if you had a 100-page equation—which is the kind of thing that does come up—there's just nothing you can do if it's 1920. At that point, you give up on the problem. But today, with tools like **Mathematica**, you can just keep going. That's an object now, a thing that you can work with. There are examples where people work with these things that formerly were regarded as too complicated, and sometimes they get simple answers out the end. That’s just an intermediate working state. So I wonder if something similar is going to happen in this case, where you could take these **models** and use them in a similar way that people do with **Mathematica**, and take them seriously. They're not **explanations** in the classic sense, but they'll be something else which interesting operations can be done on.

</details>

**迈克尔·尼尔森**: 我担心的是，假设现在是1500年，您正在训练一个**模型**……这是一个奇怪的历史，我们**深度学习**先于**宇宙学**发展。假设我们生活在那个世界。您观察到恒星似乎不动。行星有所有这些奇怪的行为。然后您在这个基础上训练一个**模型**，并对其进行某种**解释**，试图找出其中的模式。您只会不断地在**托勒密模型**上进行构建。您会看到有另一个我们没有注意到的**本轮**。参数X到Y编码这个**本轮**，其他参数编码下一个**本轮**。如果您只是试图从观测数据中找出太阳系为何如此，您只会不断地添加**本轮**。但它确实需要一个人的思想将其整合起来，并说：“总的来说，这样更有意义。”

<details>
<summary>Original English</summary>

**Michael Nielsen**: The thing I worry about is, suppose it's 1500 and you're training a model on… This is a weird history where we developed **deep learning** before we had **cosmology**. Suppose we live in that world. You're observing how the stars don't seem to move. The planets have all these weird behaviors. Then you train a model on that, and you do some kind of **interp** on it trying to figure out what the patterns are. You'd just be able to keep building on **Ptolemy's model**. You'd see there's another **epicycle** we didn't notice. Parameters X to Y encode this **epicycle**, parameters whatever encode the next **epicycle**. If you were just trying to figure out why the solar system is the way it is from observational data, you could just keep adding **epicycles** upon **epicycles**, but it really took one mind to integrate it all in and say, "Here's what makes more sense overall."

</details>

**主持人**: 这就是我的观点，我们真的不明白如何使用这些**模型**。我们还没有动词。

<details>
<summary>Original English</summary>

**主持人**: This is to my point that we don't really understand what to do with the **models**. We don't have the verbs yet.

</details>

**迈克尔·尼尔森**: 思考这个问题当然很有趣，那就是您开始对**模型**施加**约束**，本质上是说：“最简单的**解释**是什么？”或者，“您能简化吗？您能给我一个90/10的**解释**吗？”并不断地将其提炼。很可能它们一开始会提供一个非常非常复杂的**多参数模型**。但您可以强行推进，这基本上是**脚手架**，也许是它们理解事物的早期尝试。它们被迫通过它达到一个更简单的理解。

<details>
<summary>Original English</summary>

**Michael Nielsen**: It is certainly interesting to think about the question where you start to apply **constraints** to the **models**, essentially saying, "What's the simplest possible **explanation**?" Or, "Can you simplify? Can you give me the 90/10 **explanation**?" And go further and further in boiling it down. It might be that indeed they start out by providing a very, very complicated, **many-parameter model**. But you can just force the case, and basically that's **scaffolding**, which maybe is the very early days of their attempt to understand something. They're forced through that to a much more simple understanding.

</details>

**主持人**: 抱歉我误解了，但听起来您是说也许可以对一个非常复杂的**模型**进行某种**正则化**或**蒸馏**，从而得到一个更真实、更**简约**的理论。以**托勒密**和**哥白尼**为例。您从许多**托勒密本轮**开始，然后尝试**蒸馏**这个**模型**，也许它会去除一些越来越不必要的**本轮**，以使轨道**均方误差**匹配。但在某个时刻，它必须做一件事，那就是切换两件事。在局部，它实际上并不会使事情更准确。从全球意义上讲，它是一个更进步的理论。显然，人类在其发展过程中存在一个**过程**，完成了这种**正则化**或**交换**。但使用原始**梯度下降**，我真的不觉得它会这样做。

<details>
<summary>Original English</summary>

**主持人**: Sorry for misunderstanding, but it sounds like you're saying maybe there's some **regularizer** or some **distillation** you could do of a very complicated **model** that gets you to a truer, more **parsimonious theory**. Take **Ptolemy** versus **Copernicus**. You start off with lots of **Ptolemy epicycles**, and then you try to **distill** this **model**, and maybe it gets rid of some of the **epicycles** that are less and less necessary to get the orbit's **mean squared error** to match. But at some point it has to do this thing which is to switch two things. Locally, it actually doesn't make things more accurate. It's in a global sense that it's a more progressive theory. There's some **process** which obviously humanity did over its span, which did that **regularization** or did that swap. But with raw **gradient descent**, I don't really feel like it would do that.

</details>

**迈克尔·尼尔森**: 思考一下从**牛顿引力**到**爱因斯坦**的**广义相对论**的例子。这些是截然不同的理论，问题是什么导致了这种转变。据我所知，**爱因斯坦**发展了**狭义相对论**，并且他几乎立刻就明白了。这是一个非常明显的观察结果。在**狭义相对论**中，影响不能以超过**光速**的速度传播，而在**牛顿引力**中，作用是超距的。在**狭义相对论**中，您立即可以使用**牛顿引力**进行**超光速信号传输**。您可以向后发送信息。您可以做各种疯狂的事情。意识到我们这里有一个大问题并不难。这就是**强制函数**。您已经意识到您的旧解释不足够。您需要一些新的东西。然后您将从做最简单的事情开始。结果很多事情效果不佳，所以您被迫经历这些步骤，逐渐变得更复杂，并且在许多方面都是错误的。最终的理论看起来令人震惊地简单和美丽，但它经历了一些丑陋的中间阶段。如果您思考**AI**如何加速**科学**，对于我们只需要**局部解决方案**的**明确领域**，例如**蛋白质**如何折叠，您可以训练一个使用**梯度下降**的原始**模型**。然后还有像提出**广义相对论**这样的事情，您不能真正地仅仅根据宇宙中每一个观测来训练，并希望**广义相对论**自动出现。它需要什么？它也肯定不是立即被发现的。那是数十年的思考。您需要独立的**研究计划**，人们从这些偏见开始，**爱因斯坦**最初受到这样一个思想实验的启发，即您是否可以区分**重力**的影响和仅仅是向上加速的影响。您只需要不同的**AI思想家**从这些初始偏见开始，看看能从中萌发什么。这方面的**验证循环**可能相当长，但您只需要同时保持所有这些**研究计划**的活力。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Think about the example of going from **Newtonian gravity** to **Einstein's general theory of relativity**. These are shockingly different theories, and the question is what causes that flip. As nearly as I understand the history, what goes on is **Einstein** develops **special relativity** and pretty much straight away he understands. It's a very obvious observation. In **special relativity**, influences can't propagate faster than the speed of light, and in **Newtonian gravity**, action is at a distance. Straight away in **special relativity**, you could use **Newtonian gravity** to do **faster-than-light signaling**. You could send information backwards in time. You could do all kinds of crazy stuff. It's not a big leap to realize we have a big problem here. That's the **forcing function** there. You've realized that your old **explanation** is not sufficient. You need something new. Then you're going to start by doing the simplest possible stuff. It just turns out that a lot of that stuff doesn't work very well, so you're forced to go through these steps where gradually it gets more complicated, and it's wrong in a variety of ways. The final **theory** appears shockingly simple and beautiful, but it's gone through some somewhat ugly intermediate stages. If you're thinking about what it looks like to have **AI** accelerate **science**, there's one for **well-understood domains** where we just want **local solutions**, like how does this **protein fold**. We just train a raw **model** using **gradient descent**. Then there's things like coming up with **general relativity**, where you couldn't really just train on every single observation in the universe and hope that **general relativity** pops out. What would it require? It also certainly wasn't immediately discovered. It was decades of thought. You'd need independent **research programs** where people start off with these biases, where **Einstein** is initially motivated by this thought experiment of whether you can distinguish the effect of **gravity** from just being accelerated upwards. You just need different **AI thinkers** to start off with these initial biases and see what can germinate out of them. The **verification loop** for that might be quite long, but you just need to keep all those **research programs** alive at the same time.

</details>

**主持人**: 您关于保持所有不同**研究计划**活跃的观点，我认为这非常重要和核心。一个很好的例子是，相同的答案在某些情况下是正确的，而在其他情况下是错误的。

<details>
<summary>Original English</summary>

**主持人**: This point you make about keeping all the different **research programs** alive, I think that is very important and central. A great example is situations where the same answer has been correct in some circumstances and wrong in other circumstances.

</details>

### 天王星与水星：证伪主义的挑战

**迈克尔·尼尔森**: **天王星**不在正确的位置，人们著名地以此为基础预测了**海王星**的存在。对于**牛顿引力**来说，这是一个巨大的成功。**水星**不在正确的位置。您预测存在另一个扰动行星。结果它不存在。实际上，**水星**不在正确位置的原因是您需要**广义相对论**。您追求了非常相似的想法，在一个案例中非常成功，而在另一个案例中则完全失败。先验地，您无法判断哪个是该做的事情，您实际上需要两者都做。这在**科学史**上当然是非常真实的。这种多样性，您让很多人去追求许多潜在有前景的想法，您只需要长时间地支持它。由于各种原因，这样做很困难，但它确实非常非常重要。**天王星**与**水星**的这个例子非常有趣。我认为它说明了**证伪主义**的困难。**天王星**的轨道在某种意义上**证伪**了**牛顿力学**。但随后您做了一些辅助预测，说：“哦，发生这种情况的原因是肯定有另一颗行星正在扰动**天王星**的轨道。”我想是**勒维耶**在1846年。“将望远镜指向正确的方向，您会发现**天王星**。”

<details>
<summary>Original English</summary>

**Michael Nielsen**: The planet **Uranus** was not in quite the right spot, and people famously predicted the existence of **Neptune** on this basis. Wonderful, massive success for **Newtonian gravity**. The planet **Mercury** is not in quite the right spot. You predict the existence of some other distorting planet. It turns out that doesn't exist. Actually, the reason **Mercury** is not in the right spot is because you need **general relativity**. You've pursued very similar ideas, and it's been very successful in one case, and it's been completely and utterly unsuccessful in the other case. A priori, you can't tell which of these is the thing to do, and you actually need to do both. This is certainly very true in the **history of science**. This kind of **diversity**, where you just have lots of people go off and pursue lots of potentially promising ideas, you just need to support that for a long time. It's hard to do that for a variety of reasons, but it does seem to be very, very important. This example of **Uranus** versus **Mercury** is very interesting. I think it illustrates the difficulty with **falsificationism**. The orbit of **Uranus** is in some sense **falsifying Newtonian mechanics**. But then you make some ancillary prediction that says, "Oh, the reason this is happening is there must be another planet which is perturbing **Uranus**'s orbit." I think it's **Le Verrier** in 1846. "Point a telescope in the right direction, you find **Uranus**."

</details>

**主持人**: **海王星**。

<details>
<summary>Original English</summary>

**主持人**: **Neptune**.

</details>

**迈克尔·尼尔森**: 抱歉。是**海王星**。但对于**水星**，观察到其轨道形成的椭圆每世纪比**牛顿力学**暗示的多旋转43角秒，所以人们说**水星**轨道内一定有一颗行星。他们称之为**祝融星**并指向望远镜。它不在那里。但如果您是一个真正的**牛顿**主义者，您会说：“好吧，也许有一些**宇宙尘埃**遮蔽了这颗行星，或者也许这颗行星太小我们看不到它，或者让我们建造一个更强大的望远镜，或者也许有一些**磁场**遮蔽了我们的测量。”在这些步骤中的任何一个——这种情况一再发生。有太多这样的故事。我喜欢1990年代的一个例子。有些人注意到**先驱者号探测器**不在它们应该在的位置。您可能会对此感到非常兴奋。“天哪，**广义相对论**是错误的。也许我们将发现下一个**引力理论**。”今天公认的解释是，探测器中存在轻微的不对称性。结果是**热辐射**在一个方向上略大于另一个方向，这导致了朝着太阳的微小加速。大多数时候，当出现这些明显的异常时，只是发生了类似的事情。这非常类似于**水星-祝融星**的案例。但偶尔，它不是。先验地，您无法区分这些。科学充满了这些。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Sorry. **Neptune**, yes. But with **Mercury**, it's observed that the ellipse which forms its orbit is rotating 43 arcseconds more every century than **Newtonian mechanics** would imply, so people say that there must be a planet inside **Mercury's orbit**. They call it **Vulcan** and point the telescopes. It's not there. But if you're a proper **Newtonian**, what you do is say, "Well, maybe there's some **cosmic dust** that's occluding this planet, or maybe the planet is so small we can't see it, or let's build an even more powerful telescope, or maybe there's some **magnetic field** which is occluding our measurement." At any one of these steps— And this happens over and over. There are just so many stories which are exactly like this. An example I love from the 1990s. Some people noticed that the **Pioneer spacecraft** weren't quite where they were supposed to be. You can get very excited about this. "Oh my goodness, **general relativity** is wrong. Maybe we're going to discover the next **theory of gravity**." Today the accepted explanation is that there's just a slight asymmetry in the spacecraft. It turns out that the **thermal radiation** is slightly larger in one direction than the other, and that's causing a tiny little acceleration towards the sun. Most of the time when there's these apparent exceptions, it's just something like that going on. It's very much like the **Mercury-Vulcan** case. But every once in a while, it's not. A priori, you can't distinguish these. **Science** is just full of these.

</details>

**迈克尔·尼尔森**: 有趣的是，我们讲述**科学史**的方式听起来如此简单。您只需专注于正确的例外，然后您意识到您需要抛弃旧理论，瞧，您的**诺贝尔奖**就等着您了。但事实上，这些例外无处不在。99.9%的时候，它最终只是像**先驱者号探测器**案例中的**热加速**效应。不幸的是，这些故事存在很多**选择偏差**。问题是，没有事先的**启发式方法**告诉您处于哪种情况。为了阐明为什么我认为这很重要，有些人认为**AI**将在**科学**方面取得不成比例的进步，因为它在**验证循环**紧密的领域取得了不成比例的进步。它在**编码**方面非常出色，因为您可以运行**单元测试**。**科学**可能也类似，因为您可以进行实验。但它没有认识到的是，与任何给定实验兼容的理论有无限多种。随着时间的推移，我们为什么会认同我们事后认为更正确的理论，正如我们所讨论的，这很难阐明。**拉卡托斯**在他的书中列举了各种有趣的例子，关于这些极端持久的**敌对验证循环**。他谈到的一个例子是**普鲁特**。1815年有一位化学家假设所有原子核的重量都必须是整数。它们基本上都由**氢**组成。他之所以这样认为，是因为如果您查看所有元素的测量重量，它们几乎都具有整数重量。但随后出现了一些例外。例如，**氯**的重量为35.5。然后这个学派的人不断提出各种**特设理论**，比如，“哦，也许有**化学杂质**。”但似乎没有任何**化学反应**可以消除它。也许是整数的几分之一，所以35.5可以是½。但实际上，如果您更仔细地测量**氯**，它是35.46，所以它离正确的**分数**越来越远。后来，人们发现您实际测量的是不同的**同位素**，这些**同位素**无法通过**化学方法**区分。它们只能通过**物理方法**区分。所以我们在85年之后才意识到**同位素**是什么，而**验证循环**积极地对抗正确的理论。您只需要这个残留物来捍卫……没有先验的理由它是首选理论。作为一个社区，我们应该让人尝试整合新的观察结果，即使它们似乎不符合他们的思想流派，希望足够多地发生……总之，我想阐明的是**自动化科学**的困难。

<details>
<summary>Original English</summary>

**Michael Nielsen**: It's funny too, the way we tell the **history of science**, it sounds so simple. You just focus on the right exception and you realize that you need to throw out the old theory and lo and behold, your **Nobel Prize** awaits. But in fact, these exceptions are all over the place. 99.9% of the time, it just turns out to be some effect like this **thermal acceleration** in the case of the **Pioneer spacecraft**. Unfortunately, there's a lot of **selection bias** going into those stories. The thing is there's no ex ante **heuristic** which tells you which case you're in. To spell out why I think this is important, some people have this idea that **AI** is going to make disproportionate progress towards **science** because it makes disproportionate progress towards domains where there's tight **verification loops**. It's really good at **coding** because you can run **unit tests**. **Science** may be similar because you can run **experiments**. What that doesn't appreciate is that there's an infinite number of theories that are compatible with any given experiment. Over time, why we latch onto the one we think is more correct in retrospect is, as we're discussing, hard to articulate. **Lakatos** has all kinds of interesting examples in the book about these hostile **verification loops** that are extremely long-lasting. One he talks about is **Prout**. There's this chemist in 1815 who hypothesizes that all **atomic nuclei** must have whole number weights. They're basically all made of **hydrogen**. The reason he thinks this is because if you look at the measured weights of all elements, it does seem that almost all of them have whole number weights. But then there are some exceptions. For example, **chlorine** comes out at 35.5. So then there's all these **ad hoc theories** that people in this school keep coming up with, like, "Oh, maybe there's **chemical impurities**." But there's no **chemical reaction** you can do which seems to get rid of this. Maybe it's fractions of whole numbers, so 35.5 can be halves. But actually, if you measure **chlorine** even closer, it's 35.46, so it's getting further away from the correct fraction. Later on, what is discovered is what you're actually measuring is different **isotopes**, which cannot be chemically distinguished. They can only be physically distinguished. So you have 85 years before we realize what an **isotope** is, where the **verification loop** is actively hostile against the correct theory. You just need this remnant to be defending… There's no ex ante reason it's the preferred theory. As a community, we should just have people try to integrate new observations, even if they don't seem to fit their school of thought, and hopefully enough of that happens… Anyways, I guess the thing I'm trying to articulate is the difficulty with **automating science**.

</details>

**主持人**: 问题是，**瓶颈**到底在哪里？我们主要在一个方面遇到**瓶颈**，还是在多个方面遇到**瓶颈**？

<details>
<summary>Original English</summary>

**主持人**: The question is, where is the **bottleneck** at some level? Are we primarily **bottlenecked** on one type of thing, or are we **bottlenecked** on multiple types of things?

</details>

**迈克尔·尼尔森**: 当然，与**结构生物学**家交谈时，他们似乎认为**AlphaFold**是一个巨大的进步。它是一个冲击。在某种程度上，是的，**AI**当然可以帮助我们加速**科学**。它正在帮助解决某种类型的**瓶颈**。但这并不意味着，正如您所说，它一定会帮助解决所有类型的**瓶颈**。我想您所指的问题是，仍然存在哪些类型的**瓶颈**，以及克服它们的可能性如何？即使在**编码**方面，与程序员朋友交流也很有趣。目前他们都处于震惊和兴奋的状态，他们无处不在。您确实想知道**瓶颈**将转移到哪里。当然，现在很多人似乎遇到的**瓶颈**是拥有有趣的想法，特别是拥有有趣的设计理念。对于知道一个设计理念是否非常有趣，并没有真正的**验证循环**。他们不再被编写代码的能力所**瓶颈**，但他们仍然被这个其他事情所**瓶颈**。以前，他们没有被它所**瓶颈**，因为仅仅编写代码就占据了他们大量的时间。他们在花三周时间实现原型时可以有很多想法，然后他们会实现下一个版本。现在他们花三个小时实现原型，之后他们从设计角度来看就没有那么好的想法了。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Certainly, talking to **structural biology** people, they seem to think that **AlphaFold** was an enormous advance. It was a shock. At some level, yes, **AI** can certainly help us speed up **science**. It is helping with a certain type of **bottleneck**. That doesn't mean though, as you're saying, that it's necessarily going to help with all kinds of **bottlenecks**. I suppose the question you're pointing at is, what are the types of **bottlenecks** that remain, and what are the prospects for getting past them? Even in the case of **coding**, it's really interesting talking to programmer friends. At the moment they're all in this state of shock and high excitement, and they're all over the place. You do wonder where the **bottleneck** is going to move to. Certainly, one thing that a lot of them seem to be **bottlenecked** on now is having interesting ideas, and in particular, having interesting **design ideas**. There's not really a **verification loop** for knowing that a **design idea** is very interesting. They're no longer nearly as **bottlenecked** by their ability to produce code, but they are still **bottlenecked** by this other thing. Formerly, they weren't **bottlenecked** on it because just writing code took so much of their time. They could have lots of ideas while they were taking three weeks to implement their prototype, and then they would implement the next version. Now they're taking three hours to implement the prototype, and they don't have as good ideas after that, from a design point of view.

</details>

**迈克尔·尼尔森**: 去年，我预测到2028年，**AI**将能够像一位称职的总经理一样准备我的税务。但我们已经非常接近了。正如我之前分享的，我的企业和个人银行业务都使用**Mercury**。所以我最近通过**Mercury**的**MCP**让**LLM**访问了我两个账户的交易历史记录。我让它审查了我2025年的所有交易，并标记任何看起来应该记入企业账目的个人开支。这效果惊人地好。**Mercury**的**MCP**暴露了许多详细信息，例如笔记、备忘录以及任何收据的**JPEG**和**PDF附件**。所以我的**LLM**有足够的上下文可供使用。我最喜欢的一个例子发生在**Bay Padel**的收费上。如果您只看供应商，您会认为这是个人开支。但**LLM**查看了**Mercury**中的收据和附加笔记，并意识到这实际上是我们上次线下团建活动中的团队建设开支。因此，这是一项合法的业务开支。我想在传统银行拥有**MCP**功能还需要一段时间。这样的功能就是我使用**Mercury**的原因。请访问mercury.com了解更多。**Mercury**是一家**金融科技**公司，不是**FDIC**承保银行。银行服务由**Choice Financial Group**和**Column NA**提供，它们都是**FDIC**成员。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Last year, I predicted that by 2028, **AI** would be able to prep my taxes about as well as a competent **General Manager**. But we're already getting pretty close. As I shared before, I use **Mercury** both for my business and my personal banking. So I recently gave an **LLM** access to my transaction history across both accounts through **Mercury**'s **MCP**. I asked it to go through all my 2025 transactions and flag any personal expenses that seem like they should actually be charged to the business. And this worked shockingly well. **Mercury**'s **MCP** exposes a bunch of detailed information, things like notes and memos and any **JPEGs** of receipts and **PDF attachments**. So my **LLM** had plenty of context to work with. One of my favorite examples happened with a charge to **Bay Padel**. If you looked at the vendor alone, you would have had to assume that it's a personal expense. But the **LLM** looked at the receipt and the attached note in **Mercury** and realized this was actually a **team bonding exercise** from our last in-person retreat. So a legitimate **business expense**. I imagine it will be a while before traditional banks have **MCP**. Functionality like this is why I use **Mercury**. Go to mercury.com to learn more. **Mercury** is a **fintech** company, not an **FDIC Insured Bank**. Banking services provided through **Choice Financial Group** and **Column NA**, members **FDIC**.

</details>

### 科技树与文明差异

**主持人**: 您有一个非常有趣的观点。我想那是在您的一篇论文的脚注中，但我再也找不到了，那就是如果遇到**外星人**，他们很可能拥有与我们完全不同的**技术栈**。这与我从未质疑过的一个普遍假设相矛盾，即**科学**是您在文明历史早期相对较早地做的事情。您达到一个点，然后有几百年时间只是在研究基础知识，了解宇宙如何运作，然后您就掌握了它。您就掌握了**科学**。然后每个人都会趋同于相同的“**科学**”。我发现这是一个非常有趣的想法，我想请您多谈谈。

<details>
<summary>Original English</summary>

**主持人**: You have a very interesting take. I think it was a footnote in one of your essays, and I couldn't find it again, which was that it's very possible that if we met **aliens**, they would have a totally different **technological stack** than us. That contradicts a common assumption I had that I never questioned, which is that **science** is this thing you do relatively early on in the history of civilization. You get to a point and you have a couple hundred years of just cranking through the basics, understanding how the universe works, and you've got it. You've got **science**. Then everybody would converge on the same "**science**." I found that a very interesting idea, and I want you to say more about it.

</details>

**迈克尔·尼尔森**: 我至少在某种程度上赞同这个想法，那就是**科技树**或**科学技术树**可能比我们意识到的要大得多。我们处于一个有趣的情境中。人们有时会谈论**万物至理**作为**物理学**的潜在目标，然后就有一个假设，一旦达到那里，**物理学**就完成了。当然，这根本不是真的。如果您考虑**计算机科学**，**计算机科学**始于1930年代，当时**图灵**和**丘奇**等人奠定了**万物至理**的基础。他们只是说：“这就是**计算**的工作方式。”从那时起，我们已经花了九十多年的时间探索其后果，并逐渐建立起越来越有趣的想法。这些想法在某种程度上可以被视为**技术**。但就它们是**计算理论**中被发现的原理而言，我认为它们最好被视为**科学**，在某些情况下，是非常基础的**科学**。像**公钥密码学**这样的想法非常深刻，是非常不明显但在1930年代就已经隐藏的想法。我的期望是，会有不同的方式来探索这个**科技树**，而我们仍然处于相对较低的阶段。我们仍然处于刚刚理解这些基本理论，但尚未探索它们的阶段。我觉得很有趣的一点是，如果您看看**物质相态**。我在学校时，我们会学到有三种**物质相态**，有时是四五种，取决于您包含什么。作为成年人，作为一名物理学家，您开始意识到我们一直在增加这个列表。我们有**超导体**和**超流体**，也许还有不同类型的**超导体**，以及**玻色-爱因斯坦凝聚体**、**量子霍尔系统**、**分数量子霍尔系统**等等。结果是，有很多**物质相态**有待发现，我们将发现更多。事实上，我们将能够开始在某种意义上设计它们。我们仍然会受到**物理定律**的约束，但其中存在巨大的自由度。对我来说，这看起来就像我们处于**科技树**的底部。我们才刚刚开始，我预计这会是一个普遍的情况。当然，**编程**是一个非常自然的探索领域。认为我们已经发现了**编程**中所有深刻的想法，这显然是荒谬的。我们不断发现看似深刻、新的基本想法。我们非常有限。我们基本上是稍微进化一点的**黑猩猩**，所以我们很慢，需要时间。但再过一百万年，当我们思考人类围绕如何操纵计算机和信息而产生的各种不同想法时，我们会是什么样子？我认为我们很可能会发现还有很多非常深刻的想法有待发现。我想**高德纳**在《**计算机程序设计艺术**》的序言中说了类似的话。他早在60年代就开始写这本书。他和一个数学家谈话，那个数学家有点轻蔑地说：“看，**计算机科学**还不是一回事。等有一千个深刻的定理时再来找我。”**高德纳**在几十年后撰写序言时评论道：“现在显然有一千个深刻的定理了。”思考当您在**科技树**上越走越高时，长期未来会是什么样子，选择哪个方向以及如何探索，这真的很有趣。很可能不同的文明或不同的选择意味着我们最终会到达**科技树**的不同部分。特别是，有一些非常基本的事情，比如我们是非常视觉化的生物，而某些其他动物则更多地依赖听觉。这会影响您产生的思维类型吗？然后您将其扩展到更奇异的文明，他们对世界的感知和操纵方式可能与我们截然不同。这可能会对他们如何探索**科技树**产生重大影响。当然，这都是猜测。

<details>
<summary>Original English</summary>

**Michael Nielsen**: The idea there that I'm at least somewhat attached to is that the **tech tree** or the **science and tech tree** is probably much larger than we realize. We're in this funny situation. People will sometimes talk about a **theory of everything** as a potential goal for **physics**, and then there's this presumption that **physics** is done once you get there. Of course, this is not true at all. If you think about **computer science**, **computer science** started in the 1930s when **Turing** and **Church** and so on laid down what the **theory of everything** was. They just said, "Here's how **computation** works." We've spent ninety-odd years since then exploring the consequences of that and gradually building up more and more interesting ideas. Those ideas, to some extent, you can regard as **technology**. But insofar as they're discovered principles inside that **theory of computation**, I think they're best regarded as **science** and in some cases, very fundamental **science**. Ideas like **public-key cryptography** are incredibly deep, very non-obvious ideas which lay hidden already in the 1930s. My expectation is that there will be different ways of exploring this **tech tree**, and we're still relatively low down. We're still at the point where we're just understanding these basic fundamental theories, and we haven't yet explored them. A thing which I think is quite fun is if you look at the **phases of matter**. When I was in school, we'd get taught that there are three **phases of matter**, or sometimes four or five, depending on what you included. As an adult, as a physicist, you start to realize we've been adding to this list. We've got **superconductors** and **superfluids**, and maybe different types of **superconductors**, and **Bose-Einstein condensates**, the **quantum Hall systems**, **fractional quantum Hall systems**, and so on. It's starting to turn out there's a lot of **phases of matter** to discover, and we're going to discover a lot more of them. In fact, we're going to be able to start to design them in some sense. We'll still be subject to the **laws of physics**, but there is this tremendous freedom in there. This looks to me like we're down at the bottom of the **tech tree**. We've barely gotten started there, and I expect that to be the case broadly. Certainly, **programming** is a very natural place to look. The idea that we've discovered all the deep ideas in **programming** just seems obviously ludicrous. We keep discovering what seem like deep, new, fundamental ideas. We're very limited. We're basically slightly jumped-up **chimpanzees**, so we're slow and it's taking us time. But what do we look like another million years in the future, in terms of all the different ideas people have had around how to manipulate computers and information? I think we're likely to discover that there are a lot of very deep ideas still to be discovered. I think it was **Knuth** in the preface to **The Art of Computer Programming** who says something like it. He started this book back in the sixties. He talked to a mathematician who was a bit contemptuous and said, "Look, **computer science** isn't really a thing yet. Come back to me when there's a thousand deep theorems." **Knuth** remarks, writing the preface decades later, "There clearly are a thousand deep theorems now." It's really interesting to think what the long-term future is as you get higher and higher up in the **tech tree**, choices about which direction we go and how we choose to explore. It's potentially the case that different **civilizations** or different choices mean we end up in different parts of that tree. In particular, there are just very basic things about how we're very visual creatures, while certain other animals are much more aurally based. Does that bias the types of thoughts that you have? Then you extend it to much more exotic kinds of **civilizations** where maybe their biases in terms of how they perceive and manipulate the world are quite different than ours. That might make some significant changes in terms of how they do that exploration of the **tech tree**. It's all speculation, obviously.

</details>

**主持人**: 这真是一个有趣的观点。我想更好地理解它。理解它的一种方式是，可能有一些非常基本且对现实有广泛碰撞的**事物**，它们不可避免地会被发现，就像**广义相对论**。数字。**数字**。在银河系中所有智慧生物中……也许这个数字是1。

<details>
<summary>Original English</summary>

**主持人**: This is such an interesting take. I want to better understand it. One way to understand it is that there might be some things which are so fundamental and have such a wide collision area against reality that they're inevitably going to discover, like **general relativity**. Numbers. **Numbers**. Of all the intelligences in the Milky Way galaxy… Maybe that number is one.

</details>

**迈克尔·尼尔森**: 嗯，实际上，可以说我们已经增加了这个数字。但在所有这些中，有多少拥有**计数**的概念？它看起来非常自然。有多少发现了某种**十进制系统**的想法？有趣的问题。也许我们遗漏了一些真正简单明了但实际上比那更好的东西。有多少立即达到了那里？有多少不得不经历其他中间状态？有多少使用**线性表示**而不是**二维**或**三维表示**？我认为这些问题的答案根本不明显。这有很多**设计自由**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Well, actually, arguably we've already increased the number. But of all of those, what fraction have the concept of **counting**? It does seem very natural. What fraction have discovered the idea of some kind of **decimal place system**? Interesting question. Maybe we're missing something really simple and obvious that's actually way better than that. What fraction got there immediately? What fraction had to go through some other intermediate state? What fraction uses **linear representations** versus a **two-dimensional** or a **three-dimensional representation**? I think the answers to these questions are just not at all obvious. It's a lot of **design freedom**.

</details>

**主持人**: 关于**理论计算机科学**，这会非常幼稚和傲慢，但我上了**斯科特·亚伦森**的**复杂性理论**课，我是他教过的最差的学生。我记得的是，有一个时期，您是其中一位先驱，我们弄清楚了**量子计算机**可以解决的问题类别以及它与**经典计算机**可以解决的问题的关系。这是开创性的。它能工作真是太疯狂了。从那时起…… literally 有一个叫做**复杂性动物园**的网站，列出了所有**复杂性类别**。如果您有这种**复杂性类别**和这种**神谕**，它就相当于另一种**类别**。感觉我们正在构建那个**分类**。有两种方法可以理解您所说的。第一，也许您不同意我所说的这个领域实际发生的情况。第二，虽然这可能发生在任何一个领域，但谁会在1880年想到，除了**巴贝奇**之外，**计算机科学**会首先出现？我们低估了可能存在多少其他领域。或者也许您两者都这么认为，或者也许是第三个秘密的东西。我很好奇。

<details>
<summary>Original English</summary>

**主持人**: On **theoretical computer science**, this is going to be extremely naive and arrogant, but I took **Scott Aaronson's class** on **complexity theory**, and I was by far the worst student he's ever had. What I remember is there was this period, in which you were one of the pioneers, where we figured out the class of problems that **quantum computers** can solve and how it relates to problems that **classical computers** can solve. It was groundbreaking. It's crazy that this works. Since then… There's literally this website called **Complexity Zoo** which lists out all the **complexity classes**. If you have this **complexity class** with this kind of **oracle**, it's equivalent to this other **class**. It feels like we're building out that **taxonomy**. There are a couple ways to understand what you're saying. One, maybe you disagree with me that this is actually what's happened with this field. Another is that while that might happen to any one field, who would've thought in 1880 that **computer science**, other than **Babbage**, was going to be a thing in the first place? We're underestimating how many more fields there could be. Or maybe you think both, or maybe a third secret thing. I'd be curious.

</details>

### 科学进步的动态性：递减回报与新领域的涌现

**迈克尔·尼尔森**: 这里一个非常普遍的论点是**低垂的果实**论点。这个论点说应该会有**递减回报**。事实上，从经验上看我们确实看到了这一点。世界上科学家的数量呈指数级增长。

<details>
<summary>Original English</summary>

**Michael Nielsen**: A very common argument here is the **low-hanging fruit** argument. The argument that says there should be **diminishing returns**. In fact, empirically we see this. The amount of scientists in the world has exponentially increased.

</details>

**迈克尔·尼尔森**: 我认为思考为什么您期望**递减回报**以及这个论点在实践中适用性如何是值得的。我喜欢的一个类比是，想象您去参加一个活动，比如婚礼，然后您去甜点自助餐。他们摆出了三十种甜点。自然地，人们会先吃最好的甜点。我们那里并没有一个很好的偏好排序，所以可能有一些差异，但人类相当相似，所以最好的甜点会先被吃掉。这是为什么您期望在许多不同领域出现**递减回报**的一个论点。如果很容易看到有什么可用的，并且人们有相似的偏好，那么最好的东西会先被拿走，然后就越来越差了。如果您静态地看待**科学进步**的快照，这可能有一些道理。但如果有人站在甜点桌后面，不断补充和重新摆放甜点，并不断添加新的甜点，那么稍后可能会出现更好的甜点，您就会去吃那些。**科学进步**有点这种味道。我们经历这些有趣的时期。**计算机科学**就是一个很好的例子，**计算机科学**基本上是作为**数学哲学**和**逻辑学**中一些相当深奥的问题的副产品而出现的。您会看到这些人试图解决这些相当深奥的问题，这些问题看起来在探索中处于很高层次，然后他们发现了这个全新的领域，突然之间就爆发了。**递减回报**的论点在那里根本不适用。我们只是无法看到那里有什么。这种情况一再发生。新领域出现，然后突然间，砰，再次很容易取得进展。年轻人涌入，因为您可以在21岁时取得重大突破，而无需花费25年时间掌握以前完成的所有事情。这显然非常有吸引力。我不确定是否有人非常清楚地理解这种动态，或者如何思考知识的结构为何如此，即这些新领域不断涌现。但从经验上看，情况确实如此。尽管如此……以**深度学习**为例。显然，这是一个新领域的例子，21岁的年轻人可以取得进展，而且它相对较新。大约15年左右，它又重新高速发展。但我们已经到了一个阶段，您需要数十亿、数百亿甚至数千亿美元才能在前沿领域不断取得进展。有两种方式可以理解这一点。第一种是它实际上比古人所做的事情更困难，或者至少更密集。第二种是它可能并非如此，但由于我们的文明资源如此庞大，人口如此众多，资金如此充裕，我们基本上可以几乎立即取得古人需要永恒才能取得的进步。我们注意到一些事情富有成效，并立即投入所有资源。但奇怪的是，这样的例子并不多。我觉得**深度学习**之所以引人注目，因为它是一个很大的例外，否则很难想到其他例子。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think it's worth thinking about why you expect **diminishing returns** and how well that argument actually applies in practice. An analogy I like is thinking about going to an event, like a wedding, and you go to the dessert buffet. They've put out thirty desserts. Naturally, what people do is the best desserts go first. We don't quite have a well-ordered preference there, so maybe there's some difference, but human beings are fairly similar, so the best desserts will go first. This is an argument for why you expect **diminishing returns** in a lot of different fields. If it's relatively easy to see what's available and people have similar preferences, then the best stuff goes first and it just gets worse and worse after that. If you look at a very static snapshot in time of **scientific progress**, maybe there's some truth to that. But if somebody is standing behind the dessert table and is replenishing and restocking the desserts and keeps adding new ones in, it may turn out that a little bit later, much better desserts appear, and you're going to go and eat those instead. **Scientific progress** has a little bit of that flavor. We go through these funny time periods. **Computer science** is a great example, where **computer science** basically arose as a side effect of some pretty abstruse questions in the **philosophy of mathematics and logic**. You've got these people trying to attack these rather esoteric questions that seem quite high up in exploration, and they discover this fundamental new field, and all of a sudden there's an explosion there. The **diminishing returns** argument just didn't apply there. We just weren't able to see what was there. This has been the case over and over again. New fields arrive and all of a sudden, and boom, it's easy to make progress again. Young people flood in because you can be twenty-one and make major breakthroughs rather than having to spend twenty-five years mastering everything that's been done before. It's obviously very attractive. I'm not sure anybody understands very well the dynamics of that, or how to think about why the structure of knowledge is that way, where these new fields keep opening up. But it does seem empirically to be the case. Despite the fact that that is the case… Take **deep learning**. Obviously, this is an example of a new field where twenty-one-year-olds can make progress and it's relatively new. Fifteen years or so since it got back into high gear. But already we're in a stage where you need billions, tens of billions, or hundreds of billions of dollars to keep making progress at the frontier. There are a couple ways to understand that. One is that it actually is harder than the kinds of things the ancients had to do, or is more intensive at least. Second is it might not have been, but because our **civilizational resources** are so large, the amount of people is so large, the amount of money is so large, we can basically make the kind of progress it would have taken the ancients forever to make almost immediately. We notice something is productive and immediately dump in all the resources. But it's also weird that there's not that many of them. I feel like **deep learning** is notable because it is one big exception to the fact that it's hard to think of other examples.

</details>

**迈克尔·尼尔森**: 我认为这是**注意力架构**的结果。在任何给定时间，总会有一个最成功的事物。如果**深度学习**不是一回事，也许您会在谈论**CRISPR**。也许我们不会将解决**蛋白质结构预测**问题视为**AI**的成功。也许我们会找到用更广义的**曲线拟合**来解决它的方法，然后我们只会说：“哇，那花费了大量的**计算资源**。”但**蛋白质结构预测**可能是一件极其重要的事情。总有我们最大的事情。您所指的是更多地是**注意力**集中方式的结果。我所说的是，这基本上就是**时尚**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think that's a consequence of the **architecture of attention**. At any given time, there's always a most successful thing. If **deep learning** wasn't a thing, maybe you'd be talking about **CRISPR**. Maybe we wouldn't think about solving the **protein structure prediction** problem as a success of **AI**. Maybe we would have figured out how to do it with **curve fitting**, more broadly construed, and we'd just be like, "Wow, that took a lot of **computing resources**." But **protein structure prediction** might be an enormously important thing. There is always our biggest thing. What you're pointing at is more a consequence of the way in which **attention** gets centralized. It's basically **fashion**, is what I'm saying.

</details>

**主持人**: 不仅仅是**时尚**，但那里确实存在某种动态。

<details>
<summary>Original English</summary>

**主持人**: It's not just **fashion**, but there is some dynamic there.

</details>

**迈克尔·尼尔森**: 这个想法有一个非常有趣和重要的含义。那就是**分支**如此之广，如此偶然，如此**路径依赖**，以至于不同的文明会偶然发现完全不同的**技术栈**。有一个非常有趣的含义，那就是在遥远的未来，将会有**贸易收益**，这实际上可能是关于遥远未来文明如何建立、如何协调以及如何接口的最重要的事实之一。没有“去征服和剥削”这种说法。相邻的殖民地或其他地方将会有巨大的**贸易收益**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: There's a very interesting and important implication of this idea. That the **branching** is so wide and so contingent and so **path-dependent** that different civilizations would stumble on entirely different **technology stacks**. There's a very interesting implication that there will be **gains from trade** into the far, far future, which might actually be one of the most important facts about the far future in terms of how civilizations are set up, how they coordinate, and how they interface. There's not this "go forth and exploit." There are humongous **gains to trade** from adjacent colonies or whatever.

</details>

**主持人**: 有点吧。问题是什么是真正困难的。如果只是想法，那么它们传播得相对较快。分享想法相对容易。如果是更深层次的东西，它几乎是**丹·王**（Dan Wang）那种想法，即存在某种**能力**的概念。您需要所有正确的技术，您需要所有正确的**制造能力**等等。所以文明A拥有一种非常不同的**制造能力**，而文明B很难建造。即使文明B领先，我认为这也会成为事实。存在一种**比较优势**，这将为双向贸易带来巨大的利益。

<details>
<summary>Original English</summary>

**主持人**: Sort of. There's a question of what's actually hard. If it's just the ideas, well, those spread relatively quickly. It's relatively easy to share ideas. If it's something more, it's almost a **Dan Wang** kind of idea where there's some notion of **capacity**. You need all the right techs, you need all the right **manufacturing capacity**, and so on. So civilization A has a very different kind of **manufacturing capacity**, and it's just not so easy to build in civilization B. Even if civilization B is ahead, I think that becomes true. There is a **comparative advantage** which is going to provide massive benefits to trade in both directions.

</details>

**迈克尔·尼尔森**: 最终，您期望**创新**会有一些扩散。思考其中的障碍是什么很有趣。我喜欢的一个有趣的思维实验是**GitHub**，但适用于**外星人**。有人向您展示了某个**外星文明**的所有代码。我甚至不知道**代码**在那里意味着什么，但他们的**算法规范**。其中会有许多有趣的新想法，人类需要花费很长时间才能挖掘并提取所有这些。对我来说，这源于对自然界中**蛋白质**的思考。我们被赋予了如此令人难以置信的多样化的**机器**，而我们根本不了解它们。我们只需一一尝试理解它们。我们仍在理解**血红蛋白**和**胰岛素**之类的东西。已知有数亿种**蛋白质**。所以这有点像那样。我们被生物学赋予了巨大的**机器库**，其中无疑包含大量非常有趣的想法，而我们才刚刚开始理解它。我想您的观点——我需要稍微重新标记您的论点——但您认为那是**外星文明**的馈赠，显然它不是，但您可以这样认为。天哪，里面有这么多东西，我们将要研究它。天知道我们能继续研究多久。有成千上万篇关于**血红蛋白**之类的论文，而我们仍然不了解它们，但我们从中获得了如此之多。想想**胰岛素**本身。它是一件如此重要的事情。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Eventually, you expect some **diffusion of innovation**. It is funny to think about what the barriers are there. A fun thought experiment I like to think about is **GitHub** but for **aliens**. Somebody presents you with all of the **code** from some **alien civilization**. I don't even know what **code** means there, but their **specification of algorithms**. It would have many interesting new ideas in there, and it would take forever for human beings to dig through and try and extract all of those. The origin of this for me was thinking about **proteins** in nature. We've been gifted this incredible variety of **machines** which we don't really understand at all. We just have to go and try and understand them on a one-by-one basis. We're still understanding **hemoglobin** and **insulin** and things like this. There are hundreds of millions of **proteins** known. So it is a little bit like that. We've been gifted by **biology** this immense **library of machines**, no doubt containing an enormous number of very interesting ideas, and we're just at the very, very beginning of understanding it. I suppose your point—I need to relabel your argument slightly—but you think of that as a gift from an **alien civilization**, which obviously it isn't, but you think of it that way. And oh my goodness, there's so much in there and we're going to study it. Goodness knows how long we could continue to study it. There are tens of thousands of papers about **hemoglobin** and things like that, and we still don't understand them, and yet we're getting so much out of it. Just think about **insulin** alone. It's such an important thing.

</details>

**迈克尔·尼尔森**: 这是一个极其有用的**直觉泵**，地球上……我请**尼克·莱恩**来过，他提出了生命如何出现的理论，但无论您有什么理论，像**DNA**这样的东西已经存在了四十亿年。您让一个**外星文明**来到这里，他们会说：“这里有很多关于**材料科学**的有趣东西可以学习。”想想**驱动蛋白**的行走。我们对这些**蛋白质**几乎一无所知，然而我们确实知道的微小事实却令人难以置信。**核糖体**是另一个例子，这个奇迹般的装置，一个小工厂。所有这些都源于地球上这种特殊的**化学**，包括**核酸**和**碳基生命形式**。这种**化学**产生了所有这些有趣的事物，**外星文明**会觉得非常有趣。这个种子，它一定是万亿种可能的**普遍智力思想**种子中的一个，导致了如此巨大的**繁殖力**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: That's an incredibly useful **intuition pump**, that you have on Earth… I had **Nick Lane** on where he had this theory about how life emerged, but whatever theory you have, something like **DNA** has had four billion years. You have an **alien civilization** come here and be like, "There's all these interesting things to learn about **material science**." Think about **kinesin** walking along. We know almost nothing about these **proteins**, and yet the tiny few facts we do know are just incredible. The **ribosome** is another example, this miraculous sort of device, a little factory. All seeded by this particular **chemistry** on Earth with **nucleic acids** and **carbon-based life forms**. That **chemistry** gives rise to all of these interesting things which an **alien civilization** would find very interesting. That very seed, which must be one among trillions of possible seeds of **general intellectual ideas**, leads to all this **fecundity**.

</details>

**主持人**: 这是一个非常有趣的**直觉泵**。我想思考一下这个“**贸易收益**”的事情，因为我觉得这个想法非常有趣，如果您对技术如何发展以及在不同文明中可能有所不同有这样的愿景，它实际上对不同文明如何相互作用具有重要意义。存在巨大的**贸易收益**这一事实。它使得友谊更有回报吗？

<details>
<summary>Original English</summary>

**主持人**: That's a very interesting **intuition pump**. I want to meditate on this "**gains from trade**" thing because I feel like there's something very interesting about this idea that if you have this vision of how **technology** progresses and how it may be different in different civilizations, it actually has important implications about how different civilizations might interact with each other. The fact that there are going to be these huge **gains from trade**. It makes friendliness much more rewarding?

</details>

**迈克尔·尼尔森**: 是的。这是一个非常重要的观察。我根本没有考虑过这一点。这是一个非常有趣的观察。这很有趣。**比较优势**是人们喜欢引用的东西，显然它是一个非常美丽的理念。它也有局限性。它是一个特殊的有限模型。**黑猩猩**可以做一些有趣的事情，但我们不与它们进行贸易。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Yes. That's a very important observation. I hadn't thought about that at all. That is a very interesting observation. It is funny. **Comparative advantage** is something that people love to invoke and it's a very beautiful idea obviously. There are limits to it. It's a special limited model. **Chimpanzees** can do interesting things, but we don't trade with them.

</details>

**迈克尔·尼尔森**: 我认为思考原因很有趣。我认为其中一部分只是**权力**。一旦存在足够大的**权力不平衡**，很多时候——并非总是，但很多时候——群体似乎会转向另一种模式，他们只是寻求**支配**。也许人类有什么特殊之处，但也可能是一个更普遍的事情。您需要所有这些特殊条件才能使群体进行贸易。这不一定显而易见。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think it's interesting to think about the reasons why. Part of it is just **power**, I think. Once there's a sufficiently large **power imbalance**, very often—not always, but very often—groups of people seem to shift into this other mode where they just seek to **dominate**. Maybe there's something special about human beings, but maybe it's also a more general thing. You need all these special things to be true before groups will trade. It's not necessarily obvious.

</details>

**主持人**: 我认为这里发生的大事情是，第一，**交易成本**。第二，**比较优势**并不能告诉您贸易发生的条件高于任何给定生产者的**生存水平**。人们经常在“好吧，即使在**后AGI**时代，人类也将被雇用，因为**比较优势**”的背景下提出这一点。这个论点有五种不同的崩溃方式，但最容易理解的方式是：为什么我们路上没有到处都是马？因为汽车和马之间存在某种**比较优势**。第一，建造与马和汽车同时兼容的道路有巨大的**交易成本**。同样，**AI**以1000倍的速度思考，并且可以相互传递它们的**潜在状态**，它们会发现与人类在**供应链**中互动所需的成本远远高于收益。第二，仅仅因为马在数学上具有**比较优势**并不意味着每年支付10万美元，或者在旧金山维持一匹马的成本，是值得的。这种**生存**将不值得您从马身上获得的收益。

<details>
<summary>Original English</summary>

**主持人**: I think the big thing going on here is one, **transaction costs**. Two, **comparative advantage** does not tell you that the terms on which the trade happens are above subsistence for any given producer. People often bring this up in the context of, "Well, humans will be employed even in a **post-AGI** world because of **comparative advantage**." There are five different ways that argument breaks down, but the easiest way to understand it is: why don't we have horses all around on the roads? Because there's some **comparative advantage** between cars and horses. One, there are huge **transaction costs** to building roads that are compatible with horses and cars at the same time. In a similar way, **AI** thinking at 1,000 times the speed that can shoot their **latent states** at each other is going to find it way more costly than the benefit, in terms of interacting with a human being in the **supply chain**. Second, just because horses have a **comparative advantage** mathematically does not mean that it is worth paying $100,000 a year, or whatever it costs to sustain a horse in San Francisco. That **subsistence** isn't going to be worth the benefit you get out of the horse.

</details>

**迈克尔·尼尔森**: 我确实觉得这很有趣，仅仅是这个事实……我的期望和直觉显然与您在这个问题上大相径庭。**科技树**的大部分都永远不会被探索。有太多有趣的组合方式。有太多深刻的想法等待被发现，不仅是我们，而且没有人会发现它们中的大部分。因此，关于如何进行探索的选择确实非常重要。我真的很不喜欢**技术决定论**的论点。我愿意在进步相对简单时接受它。但更进一步，您开始塑造您进行探索的方式。有趣的是，我们正在以有趣的方式塑造它。有一些技术已经被禁止了。您想想**DDT**，**氯氟烃**，对**核武器**使用的限制，**核不扩散条约**。这些事情不是事先完成的，但在某些情况下它们已经非常接近了，我们只是**先发制人**地决定：“哦，我们不会走那条路。”所以这开始看起来像是一套**制度**，我们实际上正在影响我们如何探索**科技树**。至于您会在哪里看到这些**贸易收益**，显然您会在纯粹的信息可以来回发送的地方看到最大收益，因为信息具有这种特性，即生产成本高昂，但验证和发送成本低廉。未来的**生产力**有多少可以提炼成**信息**，这会很有趣。现在，这很难做到。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I do think it's interesting, the sheer fact… My expectation and my intuition obviously differs a great deal from yours on this. Most parts of the **tech tree** are never going to be explored. There are just too many interesting ways of combining things. There are too many deep ideas waiting to be discovered, and not only we, but nobody ever is going to discover most of them. So choices about how to do the **exploration** actually matter quite a bit. It's something I really dislike about **technological determinist arguments**. I'm willing to buy it low enough down when progress is relatively simple. But higher up, you start to get to shape the way in which you do the **exploration**. And it's interesting, we are starting to shape it in interesting ways. There are various **technologies** that have been essentially banned. You think about **DDT**, **chlorofluorocarbons**, restrictions on the use of **nuclear weapons**, the **Nuclear Non-Proliferation Treaty**. Those kinds of things weren't done before the fact, but they're starting to get pretty close in some cases, where we just **preemptively decide**, "Oh, we're not going to go down that path." So that starts to look like a set of **institutions** where we are actually influencing how we explore the **tech tree**. On where you would see these **gains from trade**, obviously you'd see the most where it's pure **information** that could be sent back and forth, because the **information** has this quality where it is expensive to produce, but cheap to verify and cheap to send. It'll be interesting how much of future **productivity** can be distilled down to **information**. Right now, it's hard to do.

</details>

**迈克尔·尼尔森**: 如果中国在制造某种产品方面真的很好，那么在中国制造业的1亿人头脑中，存在着这种**过程知识**。但未来，如果**AI**来做，可能会更容易。问题是我们的**制造**在多大程度上变得非常统一和**商品化**。**3D打印机**至少20年来一直是下一个大事件。为什么它们仍然运行得不那么好？为什么它们仍然不是**制造业**的中心，以及之后会发生什么？有趣的是，相比之下，**核糖体**确实是**生物学**的中心，以许多非常有趣的方式。这是否是**制造业**的未来，是一个非常简单的事情，一切都通过**生物反应器**之类的东西进行吞吐。您发送信息，然后您种植东西，或者您有一个真正起作用的**3D打印机**。如果它们足够好，那么它就变成了更纯粹的**信息问题**，而这些**过程知识**变得不那么重要了。

<details>
<summary>Original English</summary>

**Michael Nielsen**: If China's really good at manufacturing something, there's this **process knowledge** that's in the heads of 100 million people involved in the **manufacturing sector** in China. But in the future, it might be easier if **AIs** are doing it. The question is to what extent our **fabrication** gets very uniform and gets really **commoditized**. **3D printers** have been the next big thing for at least 20 years now. Why do they still not work all that well? Why are they still not at the center of **manufacturing**, and what comes after that? It is funny to look at the **ribosome** by contrast, which really is at the center of **biology** in a whole lot of really interesting ways. Whether or not that's the future of **manufacturing** is something very simple, where everything goes as throughput through a **bioreactor** or something like that. You send the information, and then you grow stuff, or you have some **3D printer** that actually works. If they're good enough, then it does become much more a pure **information problem**, and some of this **process knowledge** becomes much less important.

</details>

**迈克尔·尼尔森**: **Jane Street**拥有大量**计算**资源，但**GPU**非常昂贵，因此即使对**GPU利用率**影响相对较小的**优化**也仍然非常有价值。**Jane Street**的两位**ML工程师**，**科温**和**西尔万**，在GTC上讲解了他们的一些**优化工作流**。您的**瓶颈**不是网络太慢，而是您的训练中某个不同的**等级**没有完成工作。他们谈论了**Jane Street**如何分析**跟踪**和诊断**瓶颈**，以及他们如何使用**CUDA图**、**CUDA流**和**自定义内核**等技术来解决这些问题。通过这些**优化**，**科温**和**西尔万**能够将他们的训练步骤从400毫秒缩短到375毫秒。这25毫秒的差异听起来很小，但考虑到**Jane Street**的规模，这种改进可以释放数千个**B200**。**Jane Street**开源了所有相关代码。如果您想查看，我已在下面的描述中链接了**GitHub仓库**和讲座。如果您觉得这些东西令人兴奋，**Jane Street**正在招聘研究人员和工程师。请访问janestreet.com/dwarkesh了解更多。

<details>
<summary>Original English</summary>

**Michael Nielsen**: **Jane Street** has a lot of **compute**, but **GPUs** are very expensive, and so even **optimizations** that have a relatively small effect on **GPU utilization** are still extremely valuable. Two of **Jane Street**'s **ML engineers**, **Corwin** and **Sylvain**, walked through some of their **optimization workflows** at GTC. You're not **bottlenecked** on the network being too slow, you're **bottlenecked** on waiting for a different rank in your training not having completed the work. They talked about how **Jane Street** profiles **traces** and diagnoses **bottlenecks**, and then how they solve them using techniques like **CUDA graphs** and **CUDA streams** and **custom kernels**. With these sorts of **optimizations**, **Corwin** and **Sylvain** were able to get their training steps down from 400 milliseconds to 375 milliseconds each. This 25 millisecond difference might sound small, but given the size of **Jane Street**'s fleet, that improvement could free up thousands of **B200s**. **Jane Street** open sourced all the relevant code. If you want to check it out, I've linked the **GitHub repo** and the talk in the description below. And if you find this stuff exciting, **Jane Street** is hiring researchers and engineers. Go to janestreet.com/dwarkesh to learn more.

</details>

### 普适原理与科学发现的未来

**主持人**: 我能问一个非常笨拙的问题吗？我们发现了一些深刻的原理。一个是这个想法，如果在一个维度上存在**对称性**，它就对应着一个**守恒量**。这是一个非常深刻的想法。另一个——您写了很多，事实上还写了一本教科书——是关于如何理解可以计算什么，可以用其他物理系统理解哪些**物理系统**，**通用计算机**是什么样子等等。您的观点是，如果深入到**诺特定理**或**丘奇-图灵原理**的这个思想层面，是否存在无限数量的极其深刻的此类原理？因为我觉得它们之所以特殊，是因为它们本身包含了世界上许多不同的可能方式。但实际上，世界必须与少数这些非常深刻的原理兼容。

<details>
<summary>Original English</summary>

**主持人**: Can I ask a very clumsily phrased question? There are these deep principles that we've discovered a couple of. One is this idea that if there's a **symmetry** across a dimension, it corresponds to a **conserved quantity**. It's a very deep idea. There's another—which you've written a lot about, written a textbook about in fact—about ways to understand what kinds of things you can compute, what kinds of **physical systems** you can understand with other **physical systems**, what a **universal computer** looks like, et cetera. Is your view that if you go down to this level of idea of **Noether's theorem** or the **Church-Turing principle**, that there's an infinite number of extremely deep such principles? Because I feel what makes them special is that they themselves encompass so many different possible ways the world could be. But no, the world has to be compatible with a couple of these very deep principles.

</details>

**迈克尔·尼尔森**: 我不知道。我这里只有**猜测**和**直觉**。我的**直觉**是，我们不断发现非常基本的**新事物**。对我来说，理解**丘奇**和**图灵**以及其他人关于**通用可编程设备**的这些奇妙想法，就像我之前举的例子，非常有启发性。然后您后来明白，这也包含了**公钥密码学**的思想。然后您后来明白，这也包含了人们所说的**加密货币**的思想。这里有一套非常深刻的思想，关于**集体维持**一个**商定账本**的能力，这是建立在此基础之上的。花费了许多年才弄清楚它们的正确**规范形式**。仅仅是您不断发现看似深刻的**新基本原语**这一事实，对我来说一直是一个非常重要的**直觉泵**。我举了这个特定的例子，但我认为您在许多不同领域看到了相同的模式。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I don't know. All I have here is **speculation** and **instinct**. My **instinct** is that we keep finding very fundamental **new things**. It was quite formative for me to understand, as I gave the example before, these wonderful ideas of **Church** and **Turing** and these other people about **universal programmable devices**. Then you understand later, this also contains within it the ideas of **public-key cryptography**. Then you understand later, that also contains within it the ideas people refer to as **cryptocurrency**. There's a very deep set of ideas there about the ability to **collectively maintain** an **agreed-upon ledger**, which is built upon this. It's taken many years to figure out the right **canonical form** of those. Just this fact that you keep finding what seem like deep **new fundamental primitives** has been a very important **intuition pump** for me. I've given that particular example, but I think you see that same pattern in a lot of different areas.

</details>

**主持人**: 那么您如何解释这种经验现象，即无论您考虑**科学过程**或**技术进步**的任何输入……经济学家以无数种方式研究过这个问题。它似乎只需要每年X%的研究人员持续增长。**尼古拉斯·布鲁姆**等人几年前发表了一篇著名论文，他们说：“有多少人在**半导体行业**工作，以及**摩尔定律**的历史上它如何随时间增长？”我想他们发现**摩尔定律**意味着**晶体管密度**每年增加40%，但要保持这种增长，**半导体行业**的科学家数量每年增加了9%。他们以这种观察结果遍历了一个又一个行业。您的观点是存在这些深刻的想法，但它们越来越难找到吗？还是有另一种方式来思考这些经验观察中发生的事情？

<details>
<summary>Original English</summary>

**主持人**: What is your interpretation then of this empirical phenomenon where whatever input you consider into the **scientific process** or **technological progress**… Economists have studied this a million ways. It just seems to require a very consistent rate of X percent more researchers per year. There's this famous paper from a couple years ago by **Nicholas Bloom** and others where they say, "How many people are working in the **semiconductor industry**, and how has it increased over time through the history of **Moore's law**?" I think they find that **Moore's law** means **transistor density** increases 40% a year, but to keep that going the number of scientists has increased 9% a year, in the **semiconductor industry**. They go through industry after industry with this observation. Is your view that there are these deep ideas, but they keep getting harder to find? Or is there another way to think about what's happening with these empirical observations?

</details>

**迈克尔·尼尔森**: 首先，他们所有的例子都很狭隘。他们选择了一个特定的事物，然后关注一个特定的指标。**GPU**没有出现在那里。突然之间您获得了这种**并行化**的能力，这真的很有趣。有很多外部后果。基本上他们有这些简单的**定量衡量标准**。他们从**农业生产力**等方面来看待它，但您确实必须狭隘地关注。我当然对新类型的**进步**不断成为可能这一事实感兴趣。但我认为即使在那里，似乎仍然存在某种**递减回报**的现象。这是内在的吗？这与世界的结构有关吗？它是什么？一个没有太大变化的事情是从事这类工作的个体思想。也许那些也应该改进，或者那里正在发生一些**反馈过程**。也许这改变了事物的性质。

<details>
<summary>Original English</summary>

**Michael Nielsen**: First of all, all of their examples are narrow. They pick a particular thing, and then they look at a particular metric. **GPUs** don't show up there. All of a sudden you get this ability to **parallelize**, and that's really interesting. There are a lot of external consequences. Basically they have these simple **quantitative measures**. They look at it in **agricultural productivity**. They look at it in a whole lot of different ways, but you do have to focus narrowly. I'm certainly interested in the fact that new types of **progress** keep becoming possible. But I think even there, there does still seem to be some phenomenon of **diminishing returns**. Is that intrinsic? Is that something about the structure of the world? What is it? One thing which hasn't changed that much is the individual minds which are doing this kind of work. Maybe those should be improved as well, or some **feedback process** going on there. Maybe that changes the nature of things.

</details>

**迈克尔·尼尔森**: 我回顾**科学进步**直到，比如说，1700年，它非常缓慢，也非常不规律。您在基督之前五个世纪就有**爱奥尼亚人**做了这些相当了不起的事情，然后很多知识会丢失，然后又被重新发现，然后又丢失。您不得不说**进步**非常缓慢。这部分是由于我们没有一些非常好的想法。即使您有了想法，您也需要围绕它们建立**制度**。您实际上需要解决许多不同的问题，包括**培训**、**资本分配**以及所有这些事情。甚至只是研究人员的基本安全，这样他们就不必担心**宗教裁判所**之类的东西。有所有这些复杂的问题。您解决了所有这些复杂的问题，然后突然之间，**科学进步**就会出现大规模的爆发。如果存在某种**停滞**，如果您不改变这些外部环境，那么是的，您可能会再次开始获得**递减回报**。但这并不意味着这种情况有什么内在原因。也许一些外部因素需要再次改变。显然，很多人认为**AI**有可能成为推动力。它在某种程度上肯定会的。从这个角度来看，您可以将许多现代**科学仪器**看作是机器人。**詹姆斯·韦伯太空望远镜**是什么？将其描述为**机器人**也许有点非传统，但也不是完全不合理。它是一个高度自动化、非常复杂的系统，带有**电子介导的传感器和执行器**，其中正在使用**机器学习**来处理数据。从这个意义上说，我们已经开始看到这种转变。我们已经看到了几十年。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I look at **scientific progress** up until, let's say, 1700, and it was very slow, and also very irregular. You had the **Ionians** back five centuries before Christ doing these quite remarkable things, and so much knowledge would get lost, and then it would be rediscovered, and then it would be lost again. You'd have to say that **progress** was very slow. It's partially just bound up with the fact that there were some very good ideas that we just didn't have. Even once you've had the ideas, you need to build **institutions** around them. You actually need to solve a whole lot of different problems about **training**, **allocation of capital**, and all these kinds of things. Even just basic security for researchers, so they're not worried about the **Inquisition** or things like that. There are all these complicated problems. You solve all those complicated problems, and then all of a sudden, boom, there's a massive burst of **scientific progress**. If there's some kind of **stagnation**, if you're not changing those external circumstances, yes, you may start to get **diminishing returns** again. But that doesn't mean there's anything intrinsic about the situation. Maybe something external needs to change again. Obviously, a lot of people think **AI** is potentially going to be a driver. It certainly will at some level. To that extent, you can think of a lot of modern **scientific instrumentation** as really, at some level, **robots**. What is the **James Webb Space Telescope**? It's unconventional maybe to describe it as a **robot**, but it's not completely unreasonable either. It is an example of a highly automated, very sophisticated system with **electronically mediated sensors and actuators**, where **machine learning** is being used to process the data. In that sense, we're already starting to see that transition. We've been seeing it for decades.

</details>

**主持人**: 我有这个“抽一支大麻，吸一口”的想法，这——

<details>
<summary>Original English</summary>

**主持人**: I have this "smoke a joint and take a puff" thought, which—

</details>

**迈克尔·尼尔森**: 我想我们已经有一些了。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think we've had a few.

</details>

**主持人**: 我想我们正在进入对话的那个部分，然后您可以帮助我避免说错话，并想出更具体的方式来思考它。您提到有**工业革命**、**启蒙运动**，现在有**AI**，每一个都可能是**科学**发生的不同速度或不同方式。如果您思考这些转变发生的速度，您可以追溯人类历史的漫长时期，绘制出这种不断增长的**双曲线增长率**。十万年前，是**石器时代**。再往前追溯，**灵长类动物**存在了多久？这将是数百万年。十万年前，**石器时代**，然后一万年前，**农业革命**，然后三百年前，**工业革命**，每一个都以**指数增长率**的提高为标志。然后人们认为**AI**会再次发生。但这可能会更快。在**工业革命**开始时，人们不会想到这种趋势的下一个分界线将是**人工智能**。所以如果事情发展得越来越快，很难预测下一次转变会是什么。我想我们只是将**现在**和**AI**之间的这个**奇点**视为区分**过去**和**未来**的标志。但如果应用过去许多人应该拥有的相同**启发式方法**，也许“**智能时代**”也非常短暂，而之后的事情，我们甚至没有本体论来描述它是什么，未来不会将过去视为**智能AI前**和**AI后**。

<details>
<summary>Original English</summary>

**主持人**: I think we're getting to that part of the conversation, and then you can help me get my foot out of my mouth and figure out a more concrete way to think about it. To your point that there was the **Industrial Revolution**, the **Enlightenment**, and now there's **AI**, and each might be a different pace or a different way in which **science** happens. If you think about the pace of how fast such transitions have been happening, you can draw over the long span of human history this **hyperbolic rate of growth** that is increasing over time as well. A hundred thousand years ago, you had the **Stone Age**. You go back even much further, how long have **primates** been around? It would be millions of years. A hundred thousand years ago, the **Stone Age**, then ten thousand years ago, the **Agricultural Revolution**, then three hundred years ago, the **Industrial Revolution**, each marked by this increase in the **rate of exponential growth**. Then people think it's going to happen again with **AI**. But that would happen potentially even faster. It would not have occurred to somebody at the beginning of the **Industrial Revolution** that the next demarcation in this trend will be **artificial intelligence**. So if things are getting faster, and it's hard to anticipate what the next transition will be. I guess we just think of this **singularity** between now and **AI** as what distinguishes the past from the future. But applying the same **heuristic** that many people in the past should have had, maybe the "**Intelligence Age**" is also quite short and the next thing after that, we don't even have the **ontology** to describe what it is, the future will not think of the past as **pre-intelligent AI** and **post-AI**.

</details>

**迈克尔·尼尔森**: 不，显然我们无法证明这一点，但它看起来确实相当合理。部分问题在于我们可用的**基质**似乎完全错误。您无法和一群**黑猩猩**推测**语言**是什么。仅仅选择过去的一个重大转变，转变本身就是事情。这似乎很可能。如果我们谈论的是“抽一口”的想法，我当然觉得这个想法很有趣，即会有一个涉及使用**经典计算机**的**通用人工智能**的转变。但实际上，**量子计算机**也会有一个有趣的转变。它们可能能够处理严格更大类别的潜在有趣**计算**。所以也许**AQGI**的特征，或者无论它应该叫什么，实际上在性质上是不同的。所以也许这两个事物之间有一个短暂的时期。正如我所说，这只是**猜测**，但它当然很有趣。

<details>
<summary>Original English</summary>

**Michael Nielsen**: No, obviously we can't prove this, but it certainly seems quite plausible. Part of the issue is just that the **substrate** we have available to conceive seems all wrong. You can't speculate with a bunch of **chimpanzees** about what it would be to have **language**. Just to pick a major transition in the past, the transition itself is the thing. It seems likely. If we're talking about "taking a puff" kind of thoughts, I'm certainly amused by the idea that there's going to be some transition involving **artificial general intelligence** using **classical computers**. But actually, there'll be an interesting transition with **quantum computers** as well. They're probably capable of a strictly larger class of potentially interesting **computations**. So maybe the character of **AQGI**, or whatever it should be called, is actually qualitatively different. So maybe there's a brief period between those two things. As I say, this is just **speculation**, but it's certainly amusing.

</details>

**主持人**: 有理由这样认为吗？据我所知，几十年来，像您这样的人对**量子计算机**将要做的事情施加了相当严格的限制。它会稍微加快搜索速度。它极大地加快搜索速度的事情，比如**Shor算法**，似乎……再说一次，也许这正是您的观点，我们无法预先预测**科技树**的下一步是什么，但至少从现在来看，它似乎打破了加密，但您还能用**Shor算法**做什么呢？

<details>
<summary>Original English</summary>

**主持人**: Is there a reason to think that? From what I understand, for decades people like you have put pretty tight bounds on the kinds of things **quantum computers** are going to do. It'll speed up search somewhat. The kinds of things it speeds up extremely, like **Shor's algorithm**, it seems like… Again, maybe this is to your point that we can't predict in advance what's down the **tech tree**, but at least from here, it seems like you break encryption, but what else are you using **Shor's algorithm** to do?

</details>

**迈克尔·尼尔森**: 我们只思考了大约40年。时间不长，而且作为一个文明，我们并没有非常努力地思考它。结果它非常狭隘吗？也许吧。结果它非常广泛吗？那也是一个非常激进的扩展，看起来非常可能。请记住，我们一直在没有设备的情况下这样做。这是一个相当大的**瓶颈**。如果您在18世纪思考**计算机科学**，您会想：“它能做与/或运算，这能产生什么？”您无法预料到**比特币**。您无法预料到**深度学习**。也许如果您足够聪明，您可以做到，但这是一个相当困难的情况。

<details>
<summary>Original English</summary>

**Michael Nielsen**: We've only been thinking about it for 40 or so years. Not for very long, and we haven't thought that hard about it as a civilization. Does it turn out that it's very narrow? Maybe. Does it turn out that it's very broad? That's also a really radical expansion that seems distinctly possible. Keep in mind as well, we've been doing it without the benefit of having the devices. That's a pretty big **bottleneck** to have. If you're thinking about **computer science** in the 1700s and you're like, "it can do AND/OR, what can come out of that?" You can't anticipate **Bitcoin**. You can't anticipate **deep learning**. Maybe you could if you were sufficiently bright, but it is a pretty hard situation.

</details>

### 量子计算的兴起与跟进市场

**主持人**: 作为您在90年代和2000年代参与并为**量子信息**和**量子计算**做出贡献的人，您的内部看法是什么？您讲述的**瓶颈**历史是什么？关键的转变是什么，使它成为一个真正的领域？您如何评价从**费曼**到**德意志**以及后来所有人的贡献？

<details>
<summary>Original English</summary>

**主持人**: What is your inside view, having been in and contributing to **quantum information** and **quantum computing** back in the '90s and 2000s? What is your telling of the history of what was the **bottleneck**? What was the key transition that made it a real field? How do you rank the contributions from **Feynman** to **Deutsch** to everybody else who came along?

</details>

**迈克尔·尼尔森**: 让我们只关注实际发生了什么变化的问题。为什么**量子计算**在1950年代不是一回事？它本可以是的。像**约翰·冯·诺依曼**就是一个很好的例子。他绝对是**计算**领域的先驱。他还写了一本关于**量子力学**的非常重要的书，并且对此深感兴趣。他本可以在那个时候发明**量子计算**，我认为当时有相当多的人可能可以做到。那么为什么我们会有**费曼**和**德意志**等人在80年代的这些论文呢？这些论文被认为是该领域的基础。早些时候有一些部分的预期，但它们远没有那么全面和深刻。您应该问**大卫**。不幸的是，您不能问**费曼**，但他会比我更清楚。我认为有几件事很有趣。首先是**计算**在70年代末和80年代初变得更加突出。它只是变成了一个更多人感兴趣的事情，部分原因是出于非常平庸的原因。您可以去买一台**PC**。您可以买一台**Apple II**。您可以买一台**Commodore 64**。您可以买所有这些东西。人们开始意识到这些是非常强大的设备，非常值得思考。同时，在**量子**领域，那也是**保罗阱**的时代，以及捕获单个**离子**的能力。在那之前，我们还没有真正能力操纵单个**量子态**。您会发现这两个独立的事物，由于历史偶然性，在1980年左右都成熟了。像**冯·诺依曼**这样的人可能更早就有这个想法，但这是一个相当有趣的因素。有一个关于**理查德·费曼**的故事。他大约在1980年或1981年买了一台最早的**PC**。他显然对这个设备如此兴奋，以至于他带着他全新的**计算设备**时摔倒了，并且伤得很重。这是一个非常具有历史偶然性的巧合，有一个非常有才华且理解**量子力学**的人，同时也对这些新机器非常兴奋。他当时思考它也就不那么令人惊讶了。如果十年前您会讲什么类似的故事呢？条件不存在。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Let's just focus on the question about what actually changed. Why was **quantum computing** not a thing in the 1950s? It could have been. Somebody like **John von Neumann** is a good example. He was absolutely pioneering **computation**. He also wrote a very important book about **quantum mechanics** and was deeply interested in it. He could have invented **quantum computing** at that time, and I think there were quite a number of people who potentially could have. So why do we have these papers by people like **Feynman** and **Deutsch** in the '80s? Those are fairly regarded as the foundation of the field. There are some partial anticipations a little bit earlier, but they were nowhere near as comprehensive and nowhere near as deep. You should ask **David**. You can't ask **Feynman**, unfortunately, but he'll know much better than I do. A couple things that I think are interesting. One is that **computation** became far more salient in the late '70s and early '80s. It just became a thing which many more people were interested in, partially for very banal reasons. You could go and buy a **PC**. You could buy an **Apple II**. You could buy a **Commodore 64**. You could buy all these kinds of things. It became apparent to people that these were very powerful devices, very interesting to think about. At the same time, in the **quantum** case, that was also the time of the **Paul trap** and the ability to trap single **ions**. Up to that point, we hadn't really had the ability to manipulate single **quantum states**. You got these two separate things that for historically contingent reasons had both matured around 1980 or so. Somebody like **von Neumann** could have had the idea earlier, but it is quite an interesting factor. There's a story about **Richard Feynman**. He went and got one of the first **PCs** around 1980 or 1981. He was apparently so excited with this device, he actually tripped and hurt himself quite badly carrying his brand-new **computing device**. That's a very historically contingent coincidence, having somebody who's very talented and understanding of **quantum mechanics** also just very excited about these new machines. It's not so surprising perhaps that he's thinking about it then. What similar story could you have told 10 years earlier? The conditions don't exist for it.

</details>

**迈克尔·尼尔森**: 我的意思是，这是一个相当平庸的故事，但是……我们本来要讨论的一个想法是您关于**跟进市场**的观点。我认为这是一个完美的讨论故事，因为您撰写了该领域的教科书。“**迈克和艾克**”是**量子信息**领域的权威教科书。您大概是在**德意志**之后进入的。但您在90年代不知何故将其确定为值得**跟进**和发展的事情。与其更抽象地谈论它，我更想听听您亲身讲述，您是如何知道这就是要做的事情的。在**物理学**和**计算**领域发生的所有事情中，您是如何决定要思考这个问题的？

<details>
<summary>Original English</summary>

**Michael Nielsen**: I mean, it's quite a banal story, but… One of the things we were going to discuss was this idea you had about the **market for follow-ups**. I think this is the perfect story to discuss it for because you wrote the textbook about the field. "**Mike and Ike**" is the definitive textbook on **quantum information**. You presumably came in after **Deutsch**. But you in the '90s somehow identified it as the thing that is worth **following up on** and building on. Instead of talking about it more abstractly, I'd love to just hear the firsthand story of how you knew that this is the thing to do. Of all the things that were happening in **physics** and **computing**, how did you decide you want to think about this problem?

</details>

**迈克尔·尼尔森**: **理查德·费曼**在1982年写了一篇很棒的论文。**大卫·德意志**在1985年写了一篇绝对精彩的论文，勾勒出了**量子计算**的许多基本思想。我在1985年11岁。我没有考虑这个。我当时在踢足球，做其他事情。但在1992年，我上了一堂非常棒的**量子力学**课，由**杰拉德·米尔本**讲授。我有一天在他讲完第五节课后去问**杰拉德**。我说：“您有什么论文或其他可以给我的吗？”他说：“过几天到我办公室来。”我去了，他给了我一大堆论文，其中包括**德意志**的论文，**费曼**的论文，以及当时世界上几乎没有人研究**量子计算**和**量子信息**时，许多其他非常基础的论文。他在研究。我想他写了第一篇提出**量子计算**实用方法的论文。它不是很实用，但它确实是在一个真实的系统中。所以从某种意义上说，我受益于这个人的品味。我一读完这些论文……这些论文令人兴奋。它们提出了非常基本的问题，您意识到我可以在这里取得进展。这些是我可以潜在地研究的事情。**德意志**有一个猜想，或者叫论点，或者随便您怎么称呼它，即一个**通用模型**，一个**量子图灵机**，应该能够有效地模拟任何物理系统。这是一个非常有启发性的想法。我想在那篇论文中，他或多或少声称他已经证明了这一点。我不确定每个人都会同意。关于您是否可以有效地模拟**量子场论**，存在一些问题。这类问题非常有趣和令人兴奋。这显然是关于宇宙的一个基本问题。他在其中提出了一些关于**量子算法**、它们的来源、它们的含义以及它们与**波函数**含义相关的精彩想法。这样的问题在物理学家之间仍然没有达成一致。只是一种感觉：“哦，我接触到了一些（A）极其重要，而且（B）我们作为一个文明还没有的东西。”当然，您会开始将注意力集中在那里。我不确定我是否回答了问题……也许我误解了问题。

<details>
<summary>Original English</summary>

**Michael Nielsen**: **Richard Feynman** writes this great paper in 1982. **David Deutsch** writes an absolutely fantastic paper in 1985 sketching out a lot of the fundamental ideas of **quantum computing**. I'm 11 in 1985. I'm not thinking about this. I'm playing soccer and doing whatever. But in 1992, I took a class on **quantum mechanics** that was really terrific, given by **Gerard Milburn**. I just went and asked **Gerard** one day after the fifth lecture or something. I said, "Do you have any papers or whatever that you could give me?" He said, "Come by my office in a couple of days' time." I did, and he presented me with a giant stack of papers, which included the **Deutsch paper**, the **Feynman paper**, and a whole bunch of other very fundamental papers about **quantum computing** and **quantum information** at a time when essentially nobody in the world was working on it. He was. I think he wrote the very first paper that proposed a practical approach to **quantum computing**. It wasn't very practical, but it was actually in a real system. So in some sense, I'm benefiting from the taste of this other person. As soon as I read the papers… These are exciting papers. They're asking very fundamental questions, and you realize I can make progress here. These are things that one could potentially work on. **Deutsch** has this conjecture, or thesis or whatever you’d call it, that a **universal model**, a **quantum Turing machine**, should be capable of efficiently simulating any physical system at all. This is a very provocative idea. I think in that paper, he more or less claims that he's proved it. I'm not sure everybody would agree with that. There are questions about whether or not you can simulate **quantum field theory** effectively. That kind of question is very interesting and very exciting. It's obviously a fundamental question about the universe. He has some wonderful ideas in there about **quantum algorithms**, where they come from, what they mean, and what they relate to the meaning of the **wave function**. Questions like this are still not agreed upon amongst physicists. There's just some sense of, "Oh, I am in contact with something which is (A) deeply important, and (B) we as a civilization don't have this." Of course, you start to focus your attention a little bit there. I'm not sure I got the answer to the question… Maybe I misunderstood the question.

</details>

**主持人**: 也许我先解释一下动机。在之前的对话中，我们讨论了在1940年代您怎么知道**香农定理**和**香农**思考**通信信道**的方式是一个深刻的想法，它超越了**贝尔实验室**当时试图解决的**脉冲编码调制**问题，并且它适用于从**量子力学**到**遗传学**再到**计算机科学**的一切。您提出的一个我们还没有机会讨论的想法是……**香农**发表了这篇论文。还有所有其他论文，但存在一个**跟进市场**，人们会倾向于并基于**香农**的工作进行构建。他们是如何意识到这就是要做的事情的，这个过程是如何发生的？

<details>
<summary>Original English</summary>

**主持人**: Maybe I'll explain the motivation first. In a previous conversation, we were discussing how you could have known in the 1940s that the **Shannon theorems** and **Shannon**'s way of thinking about a **communication channel** is a deep idea that goes beyond the problems with **pulse-code modulation** that **Bell Labs** was trying to solve at the time, and that it applies to everything from **quantum mechanics** to **genetics** to **computer science**. One of the ideas you stated that we didn't get a chance to talk about yet… **Shannon** published this paper. There are all these other papers, but there's some **market of follow-ups** where people gravitate to and build upon **Shannon's work**. How do they realize that that's the thing to do, and how does that process happen?

</details>

**迈克尔·尼尔森**: 我想您给出了您当地的答案。您阅读了这些论文，然后您立即意识到这里有工作要做。有**低垂的果实**。有一些深刻的、有启发性的想法，我需要更好地理解，并且我可以有效地取得进展。在某种程度上，您在说：“好吧，我想进入这个为人类理解宇宙做出贡献的游戏，”而您正在应用这种**低垂的果实算法**。您会想：“相对于我特定的兴趣和能力，我应该在哪里拿起我的铲子开始挖掘？”在那里，它就像：“哦，这看起来是一个很好的开始挖掘的地方。”当然，不同的人选择了非常不同的方式。当时这是一个非常不寻常的选择。那是1992年。很少有人在思考这个问题。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I guess you gave your local answer. You read these papers, and you immediately realized there's work to be done here. There's **low-hanging fruit**. There's some deep provocative idea that I need to better understand, and I could tractably make progress on. To some extent, you're saying, "Okay, I wanted to get into this game of contributing to humanity's understanding of the universe," and you are applying this **low-hanging fruit algorithm**. You're like, "elative to my particular set of interests and abilities, where should I pick up my shovel and start digging?" There it was like, "Oh, this looks like quite a good place to start digging." Different people, of course, chose very differently. It was a very unusual choice at the time. This was 1992. Very few people were thinking about that.

</details>

### 开放科学与知识生产的政治经济学

**主持人**: 快进一点，我不知道您现在如何看待您在**开放科学运动**方面的工作，但它成功了吗？那里的成功是什么样的？这场运动试图实现什么？

<details>
<summary>Original English</summary>

**主持人**: Fast-forwarding a bit, I don't know how you think about your work on the **open science movement** now, but did it work? What does success there look like? What is the movement trying to accomplish?

</details>

**迈克尔·尼尔森**: 这很有趣。您没有停下来定义**开放科学**，而20年前您就不得不这样做。人们认识这个短语。人们有一些与之相关的联想。通常，他们有一套相对简单的联想。这可能意味着让**科学论文**可以**开放获取**。他们经常有一些关于将**代码**公开或将**数据**公开的想法。这些已经是**开放科学运动**的巨大成功，使这些问题变得突出。这些是人们有看法的问题，并且存在相对普遍的论点。这就像一个**模因**版本：公共资助的**科学**应该是**开放科学**。这是对一系列想法的提炼，您可能会对此提出异议。但如果您能让人们真正思考并参与这种论点，那在整个**科学的政治经济学**中是一个非常基本的问题。如果您回溯三个世纪，当时就有一场非常相似的论战，问题是：我们是否公开我们的**科学成果**？如果您看看**伽利略**和**开普勒**这样的人，他们公开的程度是以一种非常奇怪的方式进行的。有时他们会做一些奇怪的事情，比如以**字谜**的形式发表一些研究成果。他们会发现一些东西，用一句话写下结果，打乱它，然后发表。如果后来有人做了同样的发现，他们就会解开**字谜**，说：“哦，是的，我其实是第一个做到的。”这对于一个**发现系统**来说不是一个理想的基础。花费了很长时间，我想有一个多世纪，才达到或多或少现代的理想，即您以**论文**的形式披露知识。有一个对**归属**的期望，并建立了一个**声誉经济**。“某某人做了这项工作，所以他们应该为此获得荣誉，”这就是他们职业的基础。这就是**科学的政治经济学**。当您拥有**印刷机**和制作**科学期刊**的能力时，这很有道理。然后您过渡到这种现代情况，在那里您可以分享更多。您可以分享您的**代码**、您的**数据**、您正在进行中的想法。但这些并没有直接的**荣誉**。**声誉**应该与它们联系多少并不明显。所有这些都是社会构建的。让它成为一个活生生的问题是非常重要的事情。我认为这是**开放科学**工作的主要积极成果之一。

<details>
<summary>Original English</summary>

**Michael Nielsen**: It's interesting. You didn't stop and define **open science** there, which 20 years ago you would have had to do. People recognize the phrase. People have some set of associations with it. Most often, they have a relatively simple set of associations. It means maybe something about making **scientific papers open access**. Very often they have some set of notions about also making **code openly available** or making **data openly available**. Those are already very large successes of the **open science movement**, to make those salient issues. Those are issues on which people have opinions, and there are relatively common arguments. This is like the **meme** version: publicly funded **science** should be **open science**. That's a **distillation** of a set of ideas which you might be able to contest. But if you can get people actually thinking about it and engaged with that kind of argument, that's a very fundamental issue to be considering in the whole **political economy of science**. If you go back three centuries, there was a very similar argument prosecuted, which is the question: do we publicly disclose our **scientific results** or not? If you look at people like **Galileo** and **Kepler**, the extent to which they publicly disclosed was done in a very odd way. Sometimes they did bizarre things where they published some of their results as **anagrams**. They'd find some discovery, write down the result in a sentence, scramble it, and publish that. Then if somebody else later made the same discovery, they would unscramble the **anagram** and say, "Oh, yeah, I actually did it first." This is not an ideal foundation for a **discovery system**. It took a very long time, over a century, I think, to obtain more or less the modern ideals, in which you disclose the knowledge in the form of a **paper**. There is an expectation of **attribution**, and a **reputation economy** gets built. "So-and-so did this work, so they deserve the credit for that," and that's the basis for their careers. This is the underlying **political economy of science**. That made a lot of sense when you have a **printing press** and the ability to do **scientific journals**. Then you transition to this modern situation, where you can start to share a lot more. You can share your **code**, your **data**, your **in-progress ideas**. But there's no direct credit associated to those. It's not at all obvious how much **reputation** should be associated to them. That's all constructed socially. Making it a live issue is a very important thing to have done. I view that as one of the main positive outcomes of work on **open science**.

</details>

**迈克尔·尼尔森**: 我给您一个非常实际的例子来说明这个问题。长期以来，在**物理学**中存在一种**预印本文化**，人们会将**预印本**上传到**预印本档案**，但在**生物学**中则没有。没有**预印本文化**。现在这种情况正在改变，但长期以来一直如此。我过去常常通过问物理学家和生物学家为什么会这样来取乐。我从生物学家那里听到的会是他们说：“**生物学**比**物理学**竞争激烈得多，我们需要保护我们的优先权，所以我们不可能上传到档案。我们只能在期刊上发表。”然后我有时会从物理学家那里听到：“**物理学**比**生物学**竞争激烈得多，我们需要通过尽快上传到**预印本档案**来确立我们的优先权。我们不可能等待通过期刊来做。”我认为这强调了这种**归属经济**在多大程度上是我们构建的。它是我们通过协议做的事情。任何改变这种**经济**的尝试都会导致我们构建知识的不同系统。在**科学的政治经济学**周围存在一套非常基本的问题。我们有这个集体项目，我们如何调解它取决于我们围绕思想建立的经济。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I'll give you a really practical example to illustrate the problem. For a long time in **physics**, there was a **preprint culture** in which people would upload **preprints** to the **preprint archive**, and in **biology**, this didn't happen. There was no **preprint culture**. That's changing now, but for a long time, this was the case. I used to amuse myself by asking physicists and biologists why this was the case. What I would hear from biologists was they would say, "**Biology** is so much more competitive than **physics** that we need to protect our priority, so we can't possibly upload to the archive. We have to just publish in **journals**." Then I would sometimes hear from physicists, "**Physics** is so much more competitive than **biology** that we need to establish our priority by uploading as rapidly as possible to the **preprint archive**. We can't possibly wait to do it with the **journals**." I think this emphasizes the extent to which this kind of **attribution economy** is just something we construct. It's something we do by agreement. Any attempt to change that economy results in a different system by which we construct knowledge. There is this very fundamental set of problems around the **political economy of science**. We've got this **collective project**, and how we mediate it depends upon the **economy** we have around ideas.

</details>

**迈克尔·尼尔森**: 您一直强调作为**开放科学**项目一部分的，我们之前也讨论过的是**集体科学**，即一群人在一个问题上取得进展，而没有任何个体理解做出飞跃或联系所需的所有逻辑和解释层面。除了数学之外，这类发现的最佳例子是什么？

<details>
<summary>Original English</summary>

**Michael Nielsen**: One of the things you've emphasized as a part of this project of **open science**, and we talked about it earlier, is **collective science**, or groups of people making progress on a problem where no individual understands all the logical and explanatory levels necessary to make a leap or a connection. Outside of mathematics, what is the best example of such a discovery?

</details>

**迈克尔·尼尔森**: 我不确定我有一个良好的排序来给您一个最好的。我认为一个非常有趣的例子是**LHC**，它是一个极其复杂的物体。几年前，我偷偷参加了一个**加速器物理**会议。我对**加速器物理**一无所知，但我只是好奇他们在谈论什么。这群人是**数值方法**专家，特别是**逆方法**。在这些**加速器**内部，您有这些**级联**。一个粒子会被大规模加速，也许会被碰撞，然后您会得到一束粒子，它们衰变再衰变。这简直是一个令人难以置信的、有影响力的**粒子簇**，最终您在**探测器**中看到的就是这个。然后您必须追溯性地找出是什么产生了它。存在这些非常复杂的**逆问题**需要解决。您有最终的数据，但您需要找出是什么产生了它，这就是您寻找这些**特征**的方式。许多人都是**模拟方法**方面的**深度专家**，用于跟踪**粒子轨迹**。这确实是深刻而困难的东西。我当时想：“哇，您可以花费一生学习如何做这个以及如何解决其中一些**逆问题**，而您对**量子场论**、**探测器物理学**、**真空物理学**或**数据处理**知之甚少，所有这些对于理解**希格斯玻色子**来说都是绝对必不可少的。”我认为一个人不可能深入理解所有事情。很多人广泛理解很多这些想法，但他们并没有深入理解所有实际使用的东西。这就是为什么有这些拥有超过一千名作者的论文。这些人可以在高层次上相互交流，但他们对彼此的专业领域并没有那么深入的理解。像**探测器物理学**、**真空物理学**、解决**逆问题**，这些东西彼此之间差异巨大。要真正详细理解它们是严肃的工作。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I'm not sure I have a well-ordering of them to give you a best. An example that I think is very interesting is the **LHC**, where it's just this immensely complicated object. Years ago, I snuck into an **accelerator physics** conference. I didn't know anything at all about **accelerator physics**, but I was just curious to see what they were talking about. This particular group of people were experts on **numerical methods**, in particular on **inverse methods**. Inside these **accelerators**, you have these **cascades**. A particle will be massively accelerated, maybe it'll be collided, and then you'll get a shower of particles which decays and decays and decays. There's just this incredible, consequential **shower**, which is ultimately what you see at the **detector**. Then you have to retroactively figure out what produced it. There are these very complicated **inverse problems** that need to be solved. You've got this final data, but you need to figure out what produced it, and that's how you look for signatures of these. Many of these people were incredibly deep experts on **simulation methods** for following **particle tracks**. This was really deep and difficult stuff. I was like, "Wow, you could spend a lifetime just learning how to do this and how to solve some of these **inverse problems**, and you would know very little about **quantum field theory**, **detector physics**, **vacuum physics**, or **data processing**, all these things that are absolutely essential to understanding, say, the **Higgs boson**". I don't think it's possible for one person to understand everything in depth. Lots of people broadly understand a lot of these ideas, but they don't understand everything in the depth that is actually utilized. That's why there are these papers with well over a thousand authors. Those people can talk to one another at a high level, but they don't understand each other's specialties in all that much depth. Things like **detector physics**, **vacuum physics**, solving **inverse problems**, this stuff is incredibly different from each other. To understand it in real detail is serious work.

</details>

**主持人**: 您如何看待**多产**与**深度**？也许**达尔文**就是一个几十年里一直在思考某件事的例子。还有其他例子。**爱因斯坦**在他提出**狭义相对论**的那一年里做了很多不同的事情。**派斯**谈到它们都与最终的积累相关。

<details>
<summary>Original English</summary>

**主持人**: How do you think about **prolificness versus depth**? Maybe **Darwin**'s an example of somebody who's just gestating on something for many decades. There are other examples. **Einstein** during the year he comes up with **special relativity** is just doing a bunch of different things. And **Pais** talks about how they were all relevant to the eventual build-up.

</details>

**迈克尔·尼尔森**: 这是我非常强调的一点。有时我觉得自己太慢了。然而很有趣，**达尔文**的例子真的很有趣。他**多产**于什么？天知道他写了多少封信。那一定是个巨大的数字。所以他当然非常活跃。任何一种**创意项目**都涉及两种类型的工作。有**常规工作**，您只需要避免**拖延**。您只需要问：“我如何擅长这个？”或者“我如何将其外包？”以及“我如何尽快完成它？”并避免陷入长期拖延的情况。然后是**高变异工作**，您实际上需要愿意花费大量时间。您需要愿意去不同的地方，与不同的人交流，在任何特定情况下，其中大部分都不会成为输入。不知何故平衡这两件事……我认为很多人非常擅长其中一件事而不是另一件，但这几乎是一种**人格特质**，您更喜欢哪一种。人们往往会做很多其中一种，而对另一种做得不够。所以我当然会努力平衡这两件事。**爱因斯坦**是一个如此有趣的例子。1905年是如此非凡的一年。您可以完全删除**狭义相对论**，它仍然是一个非凡的年份。您可以删除**狭义相对论**，您也可以删除他因此获得**诺贝尔奖**的**光电效应**，它仍然是一个非凡的年份，很可能是一个多次获得**诺贝尔奖**的年份。那么他在做什么？也许答案只是他比我们其他人更聪明。

<details>
<summary>Original English</summary>

**Michael Nielsen**: It's something I stress about a lot. Sometimes I feel I'm too slow. It's funny though, the **Darwin** example is really interesting. **Prolific** at what? God knows how many letters he wrote. It must have been an enormous number. So he was certainly very active. There's two types of work that tend to be involved in any kind of **creative project**. There's **routine stuff**, and there you just want to avoid **procrastination**. You just want to ask, "How do I get good at this?" or "How do I outsource it?" and "How do I do it as rapidly as possible?" and just avoid getting into a situation where you're prolonging it. Then there's **high-variance stuff** where you actually need to be willing to take a lot of time. You need to be willing to go to different places and talk to different people, where in any given instance, most of it is just not going to be an input. Somehow balancing those two things… I think a lot of people are very good at doing one or the other, but it's almost like a **personality trait** which one you prefer. People tend to end up doing a lot of one and not enough of the other. So I certainly try and balance those two things. **Einstein** is such an interesting example. **1905** is just this extraordinary year. You can delete **special relativity** entirely, and it's an extraordinary year. You can delete **special relativity**, and you can delete the **photoelectric effect** for which he won the **Nobel Prize**, and it's still an extraordinary year, plausibly a multi-**Nobel-Prize**-winning year. So what's he doing? Maybe the answer is just that he's smarter than the rest of us.

</details>

**迈克尔·尼尔森**: 也有很多运气。当然对我来说，试图识别那些我应该擅长的**常规事情**，然后尽快完成它们。我认为这产生了一定的回报。但我也愿意在**变异**方面更多地押注自己，这也非常有帮助。这真的很难，因为从本质上讲，您将自己置于不确定结果的境地。如果您非常注重**生产力**，而实际上大部分时间都没有效果，您会想：“让我们减少这个。”这感觉不对。当我在旧金山工作时，我每天的一个习惯是，与其步行15分钟上班，不如选择步行30分钟，走更美丽的路。部分原因是它很美，部分原因也是为了提醒自己，不**高效**也有真正的好处。但这并不是您问题的答案。实际上，我想我只是在说我在这个问题上挣扎了很多。

<details>
<summary>Original English</summary>

**Michael Nielsen**: There's a lot of luck as well. Certainly for myself anyway, trying to identify those things that are **routine** that I should get good at, and then just try to do them as quickly as possible. I think that's yielded a certain amount of returns. But also being willing to bet a little bit more on myself on the **variance side** has also been very, very helpful. That's really hard, because intrinsically you're putting yourself in situations where you don't know what the outcome is going to be. If you're very driven to be **productive**, and actually mostly it's not working over there, you think, "Let's reduce this." It doesn't feel right. When I worked in **San Francisco**, a practice I used to have each day was instead of taking the 15-minute walk to work, I would take the more beautiful 30-minute walk. Partially just because it was beautiful, but partially also as just a reminder that there are real benefits to not being **efficient**. But it's not an answer to your question. Really, I think all I'm saying is I struggle a lot with the question.

</details>

### 深度学习与知识获取的挑战

**迈克尔·尼尔森**: 我想**迪安·基思·西蒙顿**（Dean Keith Simonton）有一个著名的**等概率法则**，他说一个人一生中发表的任何文章、书籍或其他东西极度重要的概率并没有那么大的差异。真正决定他们在哪个时代最有生产力的是他们发表了多少。任何特定事物都有同等概率变得极其重要。我认为一些最成功的**创意人员**或**科学家**，他们只是做了很多。**莎士比亚**就发表了很多作品。当然，也有反例。**哥德尔**几乎没有发表任何东西。但总的来说，您需要一个非常好的理由才能不这样做。有趣的是，多年来我见过很多人显然才华横溢，但他们只是痴迷于将要从事的伟大项目会让他们声名鹊起，但他们从未做任何事情。这似乎是相关的。这是一种厌恶感。我认为很多时候他们只是不想接受公众的评判。我希望能看到……有很多关于取得成就的人的传记、回忆录和历史。我希望有大量关于那些才华横溢但却错失机会的人的传记。我认识一些在IMO（国际数学奥林匹克）等比赛中获得金牌的人，他们后来试图成为数学家却失败了。发生了什么？原因是什么？我怀疑在许多情况下，这实际上比其他任何事情都更能提供信息。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think **Dean Keith Simonton** has this famous **equal odds rule** where he says the probability that any given thing you release—any paper, book, whatever—will be extremely important for a given person through their lifetime is not that different. What really determines in what era they are the most **productive** is how much they're publishing. Any given thing has **equal odds** of being extremely important. I think some of the most successful **creatives** or **scientists**, they're just doing a lot. **Shakespeare** was just publishing a lot. Of course, then there are counterexamples. **Gödel** published almost nothing. But broadly speaking, you need a very good reason to not do that. It's funny, I've met a lot of people over the years who are clearly brilliant, and they're just obsessed that they are going to work on the great project that makes them famous, and they never do anything. That seems connected. It's a type of **aversiveness**. I think very often they just don't want public judgment. Something that I would love to see… There's an awful lot of biographies and memoirs and histories of people who achieve a lot. I wish there was a very large number of biographies of people who are fantastically talented who just missed. I've known people who won gold medals at **IMOs** and things like that, who then tried to become mathematicians and failed. What happened? What was the reason? I suspect in many cases that's actually more informative than anything else.

</details>

**主持人**: 您在这次采访前读过我的一篇文章，内容是关于您如何看待您正在做的工作。而“作家”似乎不是一个合适的标签。正如您所说，**查尔斯·达尔文**是一位作家吗？那个标签到底是什么？我是一名**播客**。从某种意义上说，显然我们的工作非常不同，但我也会很多地思考这份工作是什么以及我如何才能做得更好。特别是，我如何确保我在**播客**中采访的不同人之间能产生某种**复合效应**？我担心，与其产生这种**复合效应**，我只是对一个主题建立了一些肤浅的理解，然后它就会贬值。我转到下一个主题，然后它又贬值了。世界上有很多**播客**会采访比我更多的专家，但我认为他们因此并没有变得更聪明或知识更渊博。所以这显然有可能搞砸。我想知道您是否有关于如何通过这种工作以更深入的方式学习的想法、看法或建议。

<details>
<summary>Original English</summary>

**主持人**: You have this essay that I was reading before this interview about how you think about what the work you're doing is. And "writer" doesn't seem like the right label. As you say, was **Charles Darwin** a writer? What exactly is that label? I'm a **podcaster**. In a way, obviously our work is very different, but I also think a lot about what this work is and how I get better at it. In particular, how can I make sure there's some **compounding** between the different people I talk to on the **podcast**? I worry that instead of this **compounding**, I build up some understanding that's somewhat superficial about a topic, and then it **depreciates**. I move down to the next topic, and it **depreciates**. There are a lot of **podcasters** in the world who will interview way more experts than I have, and I don't think they're much the wiser or more knowledgeable as a result. So it's clearly possible to mess this up. I wonder if you have thoughts or takes or advice on how one actually learns in a deeper way from this kind of work.

</details>

**迈克尔·尼尔森**: 这是一个极其复杂和丰富的问题。问题似乎是，您如何使其成为一个**更高增长的环境**？您如何使其成为一个更**苛刻的环境**？您可以通过相对较小的方式做到这一点，这可能会产生**复合回报**，或者您可以做一些更激进的事情。也许这意味着启动一个并行的项目，您在其中做一些完全不同的事情。关于**非常苛刻**如何简单地改变您对某事的反应，有一些非常有趣的事情。我有时会对学生做，有时对自己做，这主要是针对我自己，他们会在某一周说：“我将尝试在接下来的一周内完成这项工作。”然后下一周到来，他们没有解决问题。如果有一百万美元的风险，您会付出同样的努力吗？答案是，不，总是这样。他们尝试了，但他们并没有真正尝试。

<details>
<summary>Original English</summary>

**Michael Nielsen**: It's an incredibly complicated and rich question. It seems like the question is, how do you make it a **higher-growth context**? How do you make it a more **demanding context**? You can do that in relatively small ways that might yield **compounding returns**, or you can do something that is more radical. Maybe it means starting a parallel project in which you do something that is actually quite a bit different. There is something really interesting about how being very **demanding** can simply change your response to something. Something that I would sometimes do with students and sometimes with myself, it was really aimed more at myself, was they would say some week, "I'm going to try and do this work over the coming week." Then the next week would come by and they hadn't solved the problem. If a million dollars had been at stake, would you have put the same effort in? And the answer is no, invariably. They've tried, but they haven't really tried.

</details>

**主持人**: 我想那对我们所有人来说都是一种非常熟悉的感觉。如果您有一个非常**苛刻的监工**站在您身边并说：“听着，您几乎没有在工作。”您可能会做得更多。

<details>
<summary>Original English</summary>

**主持人**: I think that's a very familiar feeling for all of us. You could do a lot more if you had just the right **demanding taskmaster** standing by you and saying, "Look, you're barely operating here."

</details>

**迈克尔·尼尔森**: 我确实有点想知道，谁是这个**苛刻的监工**？他们能向您提出什么问题，能让您的准备工作更加紧张？

<details>
<summary>Original English</summary>

**Michael Nielsen**: I do wonder a little bit about what's the **demanding taskmaster**? What can they ask you that is going to make your preparation way more intense?

</details>

**主持人**: 说实话，最有用的事情是……对于某些科目，我很清楚如何准备。我正在与一家芯片设计公司的创始人制作一期关于**芯片设计**的节目，他写了一本关于这个主题的教科书。昨天我去他的办公室，我们一起**头脑风暴**了五种可以进行的**屋脊线分析**。如果我理解了这些，我就有了一些很好的理解。问题是，几乎所有其他领域都没有这种**课程**。当我三四年前采访**伊利亚**时，那是：实现**Transformer**，如果您实现了它，您就会获得一些牢固的理解。对于其他领域，我只是模糊地理解它。它不牢固。没有“做这个练习，如果您做了，您就会理解”的强制功能。

<details>
<summary>Original English</summary>

**主持人**: The most helpful thing honestly is… For some subjects it is very clear how I prep. I'm doing an upcoming episode on **chip design** with the founder of a company that does **chip design**, and he wrote a textbook on it. Yesterday I went over to his office, and we **brainstormed** five **roofline analyses** I can do. If I understand that, I have some good understanding. The problem is with almost every other field, there's not this **curriculum**. When I interviewed **Ilya** three, four years ago, it was: implement the **transformer**, and if you implement it, you have some nugget of understanding you have clamped down. With other fields, it's just that I vaguely understand this. It's not clamped. There's no **forcing function** of "do this exercise, and if you do it, you will understand."

</details>

**迈克尔·尼尔森**: 您说的确实是，您可以很好地做**播客**，而无需真正获得这种理解，而这在您看来就是问题。您想改变您的**工作描述**，以便每次都能**内化**这些片段并获得这种**整合**。在我看来，这意味着您实际上想要在某种程度上改变**工作产出**的结构。很多人都有一个糟糕的想法，认为他们应该一直处于**心流状态**。据我所知，高绩效者根本不相信这一点。他们有时处于**心流状态**。您在运动员身上肯定会看到这一点。当他们真正在打篮球或网球时，理想情况下他们大部分时间都处于**心流状态**。但当他们训练时，他们不是。他们很多时候都卡住了，或者做得不好。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Really what you're saying is you can do a good job at **podcasting** without actually attaining this kind of understanding, and that's the problem from your point of view. You want to change your **job description** so that you are **internalizing** these chunks and just getting this kind of **integration** each time. It seems to me that what that means is you actually want to change the **structure of the work output** at some level. There’s this terrible idea that lots of people have that they should be in **flow** all of the time. And as far as I can tell, high performers just don't believe this at all. They're in **flow** some of the time. You certainly see this with athletes. When they're actually out there playing basketball or tennis, ideally they are in **flow** much of the time. But when they're training they're not. They're stuck a lot of the time, or they're doing things badly.

</details>

**主持人**: 我想知道那对您来说会是什么样子。我对此会非常满意。问题是我只是不知道**跑64圈**的等价物是什么。

<details>
<summary>Original English</summary>

**主持人**: I suppose I wonder what that looks like for you. That I would be extremely satisfied with. The problem is I just don't know what the equivalent of doing **64 laps** is.

</details>

**迈克尔·尼尔森**: 这可以通过选择有明确**课程**的嘉宾来改变。所以也许没有这样做是一个错误。另外，没有真正的方法来为**陶哲轩**做准备。没有一个合理的**课程**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: This is a thing you can change by choosing guests where there is a legible **curriculum**. So maybe it's a mistake not to have done that. Also, there's no real way to prep for **Terence Tao**. There's no **curriculum** that's a plausible one.

</details>

**主持人**: 存在许多失败模式，但我担心的一个长期动态是，您可能有一个好的**播客**并达到一个**局部最优**，但对于任何特定的嘉宾或主题，您都没有深入研究。我的**学习模型**是，如果您不真正理解更深层次的**机制**，您只是在映射一个**黑箱**的输入和输出。那会非常快地消失，或者一开始就不值得。您只是继续前进，然后就结束了。您需要建立**中间连接**。**AI**在某种奇怪的方式上为此非常容易，因为有一个您可以做的明确的事情。只需实现它，然后您就理解它了。如果我将这个标准应用到其他地方，我是否就不再做历史节目了？

<details>
<summary>Original English</summary>

**主持人**: There are many **failure modes**, but one long-term dynamic I'm worried about is that you can have a good **podcast** and reach a **local maximum**, but for no particular guest or topic are you going **deep enough**. My **model of learning** is that if you don't really understand the deeper **mechanism**, you're just mapping inputs and outputs of a **black box**. That just fades incredibly fast or is not worth it in the first place. You just move on and it's over. You need to build the **intermediate connection**. **AI** in a weird way is really easy for that reason, because there is a clear thing you can do. Just implement it, and then you understand it. If I applied that **criterion** elsewhere, do I just not do history episodes?

</details>

**迈克尔·尼尔森**: 完全正确。**艾达·帕尔默**。和她交谈非常愉快，极其有趣。但对您个人来说，有什么改变？

<details>
<summary>Original English</summary>

**Michael Nielsen**: Exactly. **Ada Palmer**. Wonderful to talk to, incredibly interesting. But for you personally, what changed?

</details>

**主持人**: 我学到了一些东西。如果我分配更多时间，特别是在采访之后，写一篇2000字的文章，关于我学到了什么以及它如何与我所知道的其他事物联系起来。也许这值得做，将节目分散开来，并在之后花更多时间进行**巩固**。如果有人真的擅长设计**课程**，您需要做的**练习题**，以及采访后您需要做的**练习**来巩固您所学到的东西，我愿意付出无限的金钱。

<details>
<summary>Original English</summary>

**主持人**: There are some things I learned. If I had allocated more time, especially after the interview, to write up 2,000 words on everything I learned and how it connects to other things I know. Maybe that's a thing worth doing, spreading out the episodes more and spending more time afterwards **consolidating**. I would pay infinite amounts of money if there was somebody who was really good at coming up with the **curriculum**, the **practice problems** you need to do, and the **exercise** you need to do after the interview to clamp what you have learned.

</details>

**迈克尔·尼尔森**: 您试过和某人一起做吗？

<details>
<summary>Original English</summary>

**Michael Nielsen**: Have you tried doing that with somebody?

</details>

**主持人**: 很难找到人。我没有非常努力地尝试，但是要找到一个能为每种学科都这样做的人，不是会很困难吗？也许我应该为不同的主题聘请不同的人。

<details>
<summary>Original English</summary>

**主持人**: It's hard to find someone. I haven't tried super hard, but isn't it going to be tough to find somebody who could do that for every single kind of discipline? Maybe I should just hire different ones for different topics.

</details>

**迈克尔·尼尔森**: 也许吧。关于您每集要解决什么问题，有一些事情。据我所知，那是我真正理解任何事情的唯一方式。我对某事感兴趣。一开始，我甚至没有问题，但只是感觉这里有一些可以贡献的东西，然后您逐渐聚焦，然后就有一个问题。有趣的是，陷入困境的时间极其重要。那曾经只是令人恼火。现在看来它甚至可能是整个**过程**中最重要的一部分。那种**来之不易**的性质意味着我之后会**内化**它。我写过几天内完成的10000字文章，我也写过三个月或六个月完成的文章。我觉得从那些只花几天完成的文章中学到的不多。而那些花了三个月的文章，15年后我仍然会记得。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Maybe. There's something about, what problem are you solving for each episode? As far as I can tell, that's the only way I really understand anything. I get interested in something. At first, I don't even have a problem, but there's just some sense that there's some contribution to make here, and gradually you hone in, and there's a problem. Funnily enough, spending time **stuck** is incredibly important. That used to just be annoying. Now it seems like it's maybe even the most important part of the whole **process**. That hard-won nature of it means that I **internalize** it afterwards. I've written 10,000-word essays in a couple of days, and I've written them in three months or six months. I feel like I didn't learn very much from the ones that only took a couple of days. Whereas some of the ones that took three months, 15 years later, I'll still remember.

</details>

**主持人**: 您能描述一下除了**物理学**之外，那些花了三个月的文章，您是如何学习的吗？

<details>
<summary>Original English</summary>

**主持人**: Can you describe outside of **physics** how you learn, of the ones that took three months?

</details>

**迈克尔·尼尔森**: 到目前为止最常见的是，总有一些**创意作品**。有时是一堂课。有时是与一群人一起参与一个**集体创意作品**。您可能甚至没有意识到，但您正在以某种方式作为他们**创意成果**的输入。有时是一篇文章或一本书什么的。这也是我经常喜欢做**播客**的原因之一。我答应来这里部分原因是因为我知道您会问一些异常苛刻的问题。那是一种试图从不同类型的**强制功能**中获得这种视角的尝试。试图选择最**苛刻的创意环境**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: By far the most common thing is there's always some **creative artifact**. Sometimes it's a class. Sometimes it's engagement with a group of people who are working on some **collective creative artifact** together. You might not even be aware of it, but you're acting as an input to their **creative ends** in some way. Sometimes it's an essay or a book or whatever. It's one of the reasons why I often quite enjoy doing **podcasts**. I said yes to come here partially because I know you ask unusually **demanding questions**. That's an attempt to get this sort of perspective from a different kind of a **forcing function**. Trying to pick the most **demanding creative context**.

</details>

**主持人**: 为了这次采访，我学习了**萨斯坎德**的**狭义相对论**书中的三讲。问题是里面几乎没有**练习题**。所以我聘请了一位物理学家朋友。我还没做，但对于每一讲，我想要一堆**练习题**来完成，我打算适当地谦逊一下。您如何才能使其尽可能地致命？

<details>
<summary>Original English</summary>

**主持人**: For this interview, I went through three lectures of the **Susskind special relativity book**. The problem is that there's almost no **practice problems** in it. So I hired a physicist friend. I haven't done it yet, but for every lecture I want a bunch of **practice problems** to go through, and I'm planning on being appropriately humbled. How do you make it as **jugular** as possible?

</details>

**迈克尔·尼尔森**: 您能提高的**赌注**越高越好。采访在某种意义上是**高风险**的，但它并不一定能测试深刻的理解。

<details>
<summary>Original English</summary>

**Michael Nielsen**: The higher you can raise the **stakes**, the better. The interview is in some sense **high stakes**, but also it doesn't necessarily test deep understanding.

</details>

**主持人**: 我不认为这次采访有那么高的**风险**。您没有写一本关于**狭义相对论**的书，也没有试图写一本取代现有标准教科书的书。那才是真正的高风险。顺便说一句，我发现一个特别困难的短语。人们会谈论“深入”研究一个主题，结果发现不同的人对这的含义有不同的想法。对一些人来说，这意味着他们读了几篇**博客文章**。对一些人来说，这意味着他们读了一本关于它的书。对一些人来说，这意味着他们写了一本关于它的书。您给自己设定的标准很大程度上决定了您以这种方式整合知识的能力。我发现我在某些方面在**AI**的帮助下能够更快地前进，但我不知道我是否学得更好。

<details>
<summary>Original English</summary>

**主持人**: I don't think the interview is that **high stakes**. You're not writing a book about **special relativity**, and you're not trying to write a book that replaces whatever the existing standard textbook is. That's a really **high stake**. By the way, a phrase that I find particularly difficult. People will talk about "**going deep**" on a subject, and it turns out different people have different ideas of what this means. For some people it means they read a couple of **blog posts**. For some people it means they read a book about it. For some people it means they wrote a book about it. The standard you hold yourself to determines a lot about your ability to **integrate knowledge** in this way. I found that I'm in some sense able to move much faster on some things through the help of **AI**, but I don't know if I'm learning better.

</details>

**迈克尔·尼尔森**: 我想这可能是因为……最困难的事情，最**苛刻**的事情，是如此令人反感，以至于您会尽可能寻找任何借口来逃避它。只是与**LLM**进行来回对话，您会一带而过……这很有趣，但不一定是其他什么。这是一种非常简单的方法来摆脱困境。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I think it's probably because… The hardest thing, the thing that is most **demanding**, is so **aversive** that you try to take any excuse you can to get out of it. Just having a back-and-forth conversation with an **LLM** where you gloss over… It’s entertaining but not necessarily anything else. It’s such an easy way to get out of the thing.

</details>

**主持人**: 事实上，它使事情变得更容易，因为与其进行一些中间思考，您总是可以向**聊天机器人**提出下一个问题。

<details>
<summary>Original English</summary>

**主持人**: In fact, it makes it easier because instead of doing some **intermediate thinking**, there's always a next question you can ask a **chatbot**.

</details>

**迈克尔·尼尔森**: 是的。而且它多少有点价值。那当然是它的诱惑力的一部分。它并非完全无用。但它可能会取代您可能应该做的事情。这很有趣。您应该在多大程度上**外包**这类事情？这是一个有趣的判断。有很多**常规工作**需要您完成。对您来说价值很低，所以如果您能让**聊天机器人**来做，您不妨这样做。有人多年前采访了先驱**计算机科学家****艾伦·凯**，他被问及对**Linux**的看法。如果我没记错他的回答，他基本上说：“它与**计算机科学**无关。它只是一个巨大的烂摊子。里面有一些有趣的想法值得理解，但您主要学到的都是关于**Linux**的东西。您并没有真正学到任何可**转移**的知识。”我觉得这很有趣。

<details>
<summary>Original English</summary>

**Michael Nielsen**: Yeah. And it's somewhat valuable. That’s part of the seductiveness, of course. It's not actually useless. But it can substitute for actually doing the thing that maybe you should be doing. It’s interesting. To what extent should you be **outsourcing** that kind of stuff? It’s an interesting judgment call. There is a whole bunch of **routine work** that you want done. It's low value for you, so if you can get a **chatbot** to do it, you may as well. Somebody interviewed the pioneering **computer scientist** **Alan Kay** years ago, and he was asked what he thought about **Linux**. If I remember his answer correctly, he basically said, "It doesn't have anything to do with **computer science**. It's just a great big ball of mud. There are a few interesting ideas in there which are worth understanding, but mostly all you're learning is stuff about **Linux**. You're not actually learning anything which is **transferable**." I thought that was very interesting.

</details>

**迈克尔·尼尔森**: 有些事情有一种诱惑力，它有点像**鲁布·戈德堡机器**。您只需了解所有的**部分**，这感觉很有趣。但如果您退后一步思考您实际在做什么，它可能并不能实现您的目标。也许您想成为一名**系统管理员**，那么学习**Linux**是您时间的宝贵利用。这完全没有坏处。但如果您的目标是理解**计算**的基本原理，那么这是否是您时间的宝贵利用就远不那么清楚了。这当然是我思考了很多的答案，对于某种类型的思维来说，学习**系统**并将其与**理解**混淆有一种诱惑力。

<details>
<summary>Original English</summary>

**Michael Nielsen**: There's a certain kind of seductiveness to some things where it's sort of a **Rube Goldberg machine**. You can just learn about all the **bits**, and it feels entertaining. But if you step back and think about what you're actually doing here, it might not actually be meeting your objectives. Maybe you want to become a **sysadmin**, and learning **Linux** is a great use of your time. There's no harm in that at all. But if your objective is to understand the **fundamentals of computing**, it's much less clear that that's a good use of your time. It was certainly an answer I've thought a lot about, where for a certain type of mind, there is a seductiveness in just learning **systems** and confusing that with **understanding**.

</details>

**主持人**: 好的，我会随时向您汇报进展。我会在一个月内给您发短信，告知一些改进后的**学习系统**。

<details>
<summary>Original English</summary>

**主持人**: Okay, I'll keep you updated on how this goes. I owe you a text within a month of some revamped **learning system**.

</details>

**迈克尔·尼尔森**: 我会非常好奇。这种微小的**增量改进**也非常有价值。它是**播客**的主要输入。书架很漂亮，我有黑板之类的东西很棒，但真正让**播客**更好的事情是如果我能改进我的**学习**。所以是的，每一小部分改进都值得。

<details>
<summary>Original English</summary>

**Michael Nielsen**: I'd be really curious. It's also true that tiny **incremental improvements** in this are just worth so much. It's the main input into the **podcast**. It's great that the bookshelves are fancy and I've got a blackboard or whatever, but really the thing that makes the **podcast** better is if I can improve the **learning** I do. So yes, it's worth every morsel of improvement.

</details>

**主持人**: 好的，谢谢您的心理咨询。很好的结束语。谢谢**迈克尔**。

<details>
<summary>Original English</summary>

**主持人**: All right, thanks for the **therapy session**. Great note to end on. Thanks, **Michael**.

</details>

**迈克尔·尼尔森**: 好的。谢谢**德瓦凯什**。

<details>
<summary>Original English</summary>

**Michael Nielsen**: All right. Thanks, **Dwarkesh**.

</details>