---
author: TED
date: '2026-06-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Xr9VqRawjAU
speaker: TED
tags:
  - virtual-cell-model
  - crispr-gene-perturbation
  - single-cell-rna-sequencing
  - complex-disease-biology
  - data-driven-biomedicine
title: 人类细胞极度复杂，人工智能能否成功破译其奥秘？
summary: 在这场极具启发性的 TED 访谈中，来自 Arc Institute 的西尔瓦娜·科纳曼（Silvana Konermann）教授深入探讨了如何将单细胞测序、CRISPR 基因编辑与前沿人工智能大模型结合，构建革命性的“虚拟细胞模型”。通过在四年内进行至少十亿次物理生物学扰动实验，研究团队旨在以数据驱动的全新方式，预测并逆转阿尔茨海默病、心脏病、癌症等人类复杂疾病的细胞状态，开启系统生物学与精准医疗的全新时代。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Silvana Konermann
companies_orgs:
  - Arc Institute
products_models: []
media_books: []
status: evergreen
---
### 科学启蒙与成长

**克里斯·安德森 (Chris Anderson)**: 很高兴见到你，欢迎来到 TED。西尔瓦娜，你对科学的热情其实已经持续了相当长的一段时间。能和我们聊聊这张照片背后的故事吗？

<details>
<summary>Original English</summary>

**Chris Anderson**: Great to see you, welcome to TED. Now, Silvana, you've been passionate about science for quite a long time. Tell me about this picture.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 好的，这张照片是我 15 岁的时候拍的。我出生在瑞士的一个小镇上。我的父母其实对科学并不怎么感兴趣，但不知怎么的，我就是对周围的大自然，以及我们人类的身体如何运作、我们的生物学机制产生了极其浓厚的兴趣。因此，我当时非常想方设法地进入实验室去亲自动手做一些科学研究。这对我来说实际上是相当困难和棘手的，但最终我成功说服了我的一位科学老师，让他去帮我说服他的某位同事，允许我进入他们的实验室。所以这就是我，正拿着我的第一个科学项目，后来我凭借这个项目赢得了瑞士全国性的科学竞赛，接着又赢得了欧盟青年科学家竞赛。我想正是从那个时候起，我获得了自那以后继续在科学道路上走下去的信心。

<details>
<summary>Original English</summary>

**Silvana Konermann**: So this picture is when I was 15. So I was born in a small town in Switzerland. My parents weren't into science, but somehow I got really fascinated just with nature around me and also just how we worked as humans and our biology. So I really wanted to find a way to be able to get into a lab to do some science. It was actually pretty tricky for me, but eventually I talked one of my science teachers into convincing one of his colleagues to let me go into the lab. And so this is me with that first science project where I went on to win the national competition, and then also the European Union competition. And I think that's really where, you know, I got, I think, the confidence to continue with science since then.

</details>

### 阿尔茨海默的困惑

**克里斯·安德森 (Chris Anderson)**: 但是，成为一个科学神童也是有代价的，或者说是有某种副作用的，那就是你最终会觉得，自己肩负着某种必须用这种天赋去做点什么的责任。我想这种责任感伴随了你的大半生，而且你一直在思考，自己到底能去着手解决哪些最大、最难的问题。跟我们讲讲这张图表吧。

<details>
<summary>Original English</summary>

**Chris Anderson**: But there's a drawback to being a scientific prodigy, which is that you end up feeling like you might have a responsibility to do something with that. And I think you've had that your whole life and you’ve thought about what are the biggest problems you could work on. Tell us about this graph here.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 好的，没问题。到目前为止，我已经做科学研究做了超过 20 年了。但在开始之前，我想说明一下，这其实是我第一次真正意义上的公开演讲。所以我通常情况下都是非常习惯于待在幕后工作的。（观众掌声）是的，从我本科时期起，我就一直在深入思考一个问题——我的本科是在瑞士读的，主修的是生物神经科学——在那期间我了解到了**阿尔茨海默病 (Alzheimer's Disease)**。通过学习，我得知我们的大脑中正在发生着这些巨大的、显著的病变，而且许多已知的信息都是关于这个疾病的晚期阶段，也就是它有多么的严重和可怕。然而，当时那堂课的结尾基本上是以这样一句话结束的：“但是，我们其实根本不知道它是如何开始的。而且我们目前仍然没有任何治疗方法。” 那已经是很久以前的事情了，我想大约是 17 年前。这句话深深地烙印在了我的脑海里，因为我不禁要问：为什么我们不明白它是怎么开始的？为什么我们连一种可行的治疗方法都没有？明明有那么多非常明显、可观测到的变化在发生着。这也正是让我对**疾病生物学 (Disease Biology)**，特别是复杂疾病产生浓厚兴趣的契机。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Yeah, absolutely. So I have been, you know, doing science now for more than 20 years. But I did want to say, this is actually my first real public appearance. So I am very much, usually behind the scenes. (Applause) Yeah, a problem that I’ve really been thinking a lot about since undergrad -- I did my undergrad in Switzerland in biology neuroscience -- and I learned more about Alzheimer’s disease. And through learning how there are these big changes in the brain that are happening, a lot of what is known about late stages of the disease, how severe it is, and then the lecture though ended with basically: but we have no idea really how it’s starting. We still don’t have a therapy. And that was now, a long time ago, I guess, 17 years ago or so. And that really stuck with me because why didn’t we understand how it’s starting? Why didn’t we have a therapy? There are all these very observable changes happening. And so that got me interested in disease biology and specifically complex diseases, where Alzheimer’s is a complex disease. It sounds [like] “Oh, it’s just complicated,” but that's not what it means. It means that there are multiple different risk factors. And basically every patient has a unique combination of risk factors for a disease -- that’s different from an infection where you have one cause.

</details>

### 什么是复杂疾病

**克里斯·安德森 (Chris Anderson)**: 这里列出的其他几种疾病，在根本上也具有类似的复杂性。

<details>
<summary>Original English</summary>

**Chris Anderson**: And several of these diseases here are similarly fundamentally complex.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 没错。比如心脏病、许多种癌症，显然意外事故不包括在内，但中风和阿尔茨海默病——这些都属于典型的**复杂疾病 (Complex Diseases)**。

<details>
<summary>Original English</summary>

**Silvana Konermann**: That's right. So heart disease, many cancers, obviously not accidents, but stroke and Alzheimer’s disease -- these are all complex diseases.

</details>

**克里斯·安德森 (Chris Anderson)**: 所以，这就是为什么在最近这些年里，面对现代医学科学的飞速发展，这些疾病依然能够保持如此顽固的抵抗力，让我们难以取得戏剧性的突破进展。

<details>
<summary>Original English</summary>

**Chris Anderson**: And so that's why it's been so resistant to dramatic advancements in medical science in recent years.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 从根本上说，所有这些疾病都包含着遗传变异与环境因素的相互作用。而且每个患者都是独一无二的，他们拥有一套独一无二的风险因素组合。因此，作为一个科学共同体，我们一直都在极其艰难地探索：这些千差万别的患者之间究竟有什么共同之处，是可以让我们作为靶点去进行干预，进而彻底治愈这种疾病的？

<details>
<summary>Original English</summary>

**Silvana Konermann**: Basically, all of these have a combination of genetic changes [and] environmental factors. And each patient is unique. They have a unique combination of risk factors. And so we’ve been really struggling as a scientific community understanding what do all these different patients have in common that we could target and then fix the disease?

</details>

### 测量改变与理解

**克里斯·安德森 (Chris Anderson)**: 但你现在看到了一个契机，可以对这些疾病发起一场截然不同的全新攻坚战。到底发生了什么改变？

<details>
<summary>Original English</summary>

**Chris Anderson**: But you're seeing now an opportunity to have a different kind of assault on these diseases. What has changed?

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 我认为，就在过去这一两年里，有三件事汇聚到了一起，使得理解阿尔茨海默病以及类似的其他复杂疾病成为了可能——在高层次上，如果快速总结一下，这就是三个领域：测量（measuring）、改变（changing）和理解（understanding）。所谓“测量”，对我们而言，核心技术就是**单细胞测序 (Single-Cell Sequencing)**。这是一种允许我们一次只观察一个细胞，并对细胞内关键的动态过程（也就是细胞的 RNA 表达）进行快照记录的技术。从根本上说，RNA 就像是细胞的语言，而单细胞测序能够一次针对一个细胞，对它内部正在发生的事情进行快照捕捉。

然后是第二个步骤，也就是“改变”，我们需要有能力去对细胞做出极其精准的改变——比如一次改变一个基因，去阻止它制造 RNA，或者改变它以实现 RNA 的上调表达。这是我过去 15 年来一直致力于研究的领域，也就是 **CRISPR 基因编辑技术 (CRISPR Technology)**。作为一个研究领域，我们已经取得了长足的进步。现在，我们能够在基因组的所有基因上做到这一点。我们可以以靶向、定向的方式做出这些改变。这真的是在最近非常近的时期才成为可能的。

最后，当然就是**人工智能 (AI)**，它现在处于一切事物的最前沿，尤其是今天。但我们已经看到，在过去——我想说真的是在过去两年里——AI 已经真正地开始发挥作用了。AI 能够帮助我们去理解和理解这复杂的生物学过程。

<details>
<summary>Original English</summary>

**Silvana Konermann**: I think there are now three things that have come together just in the last one or two years that make it possible to understand such a complex problem like Alzheimer’s disease and other diseases like it -- and [those are], at a high level, three areas, if you summarize it really quickly: measuring, changing and understanding. And so measuring -- what that means for us is really single-cell sequencing. So this is a technology that allows us to look at one cell at a time and take a snapshot of key dynamic processes in the cell which is the RNA expression of the cell. So basically, RNA is like the language of the cell, and this takes a snapshot one cell at a time of what's going on inside it. And then the second step, which is changing, we need to have the ability to change something very precise -- changing one gene at a time [to] stop it from making the RNA or changing it to upregulate the RNA. This is the area that I’ve been working on now for 15 years -- CRISPR technology -- and as a field, we’ve made a lot of advancements. And now we can do this across all the genes in the genome. We can make these changes in a targeted way. And it is really only possible very recently. And then finally, of course, AI is at the forefront of everything, especially today. But we’ve just seen over -- I would say really the last two years -- that ... it’s really working. AI can help us understand these kinds of processes.

</details>

### 破解细胞的语言

**克里斯·安德森 (Chris Anderson)**: 如果我理解得没错的话，就像人工智能已经破解了人类语言的理解机制一样，你也看到了这样一种可能性：我们可以利用 AI 去理解我们自己细胞的语言，也就是 RNA。

<details>
<summary>Original English</summary>

**Chris Anderson**: So if I understand right, just as AI has cracked understanding human language, you see a possibility that AI can be used to understand the language of our own cells, RNA.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 是的，完全正确，这基本上就是核心原理。为了实现这一点，你需要能够以这种靶向的方式去测量它并改变它。但作为一个类比，生物学界在当时其实对此深表怀疑。我是说，即使在六年前，人们也不确定你是否真的能够仅仅基于文本语言本身以及对语言的预测，来拓展和做大这些**大语言模型 (Large Language Models)**，从而从根本上构建出对世界的认知，并至少能够非常出色地逼近智能。所以这是过去六年里的关键洞察，即模型仅仅通过人类语言就能学到如此之多的知识。同样地，我们也可以将这一概念应用到 RNA 上，RNA 基本上就是细胞的语言——特别是细胞的动态语言——因为它每时每刻都在发生着变化。它不仅反映了细胞正在经历和发生着什么，也反映了该细胞的遗传学特征。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Yeah, exactly, that's basically the core principle. And for that, you need to be able to measure it and change it in this targeted way. But as an analogy, the field was doubting this at the time. I mean, even six years ago, people were not sure that you could really scale these large language models, just based on language and kind of predicting language, to actually build a conception of the world essentially, and at least approximate intelligence clearly pretty well. So this is the key insight for the last six years, which is that a model can learn so much just from human language. And similarly, we can apply that concept to RNA, which is basically the language of the cell -- especially the dynamic language of the cell -- because it's changing all the time. It reflects what's happening to the cell, but also it reflects the cell's genetics.

</details>

**克里斯·安德森 (Chris Anderson)**: 它的复杂程度是与人类语言大致相当，还是比人类语言要复杂得多，或者更简单一些？

<details>
<summary>Original English</summary>

**Chris Anderson**: Is it approximately the same level of complexity as human language or much more so or less?

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 这很难给出一个确切的定论。但我可以说，对我而言，其中一个关键的区别（我认为这也是为什么人工智能在生物学领域能够发挥如此巨大威力的原因）在于：人类语言是由我们人类自己创造并生成的，对吧？所以我们自然能够理解它，因为它是我们发明出来的。而 RNA 语言，或者说这种生物学的语言，是经过漫长的自然进化而来的——它绝对不是由人类设计或生成的。因此，它对我们人类来说基本上就像天书一样，是无法渗透和直接理解的。我们能够预测左边的这句：“生存还是毁灭（to be or not to be）”，我们知道这是莎士比亚的名言，我们可以轻松补全它。但是在右边，没有任何一个人类能够真正地补全那段生物代码，对吧？但人工智能根本不在乎这一点。

<details>
<summary>Original English</summary>

**Silvana Konermann**: It's hard to say, but I will say one key difference for me, and I think this is why AI can be so powerful for biology, is that human language is generated by humans, right? So we understand it, right? We came up with it. RNA language, or the biological language, has evolved -- it was not generated by humans. So it's basically impenetrable for us. We can predict the left side: “to be or not to be” we know [is] Shakespeare -- we can complete it. On the right side [though], no human really could complete that, right? But AI doesn't care.

</details>

### 十亿次物理实验

**克里斯·安德森 (Chris Anderson)**: 为了试图破解它，我认为你们必须采取同样的方法，也就是获取海量的数据。请和我们谈谈这个数据获取的过程。

<details>
<summary>Original English</summary>

**Chris Anderson**: To try and crack it, I think you have to take the same stance of just getting huge amounts of data. Talk about that process.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 好的，完全是这样。我的意思是，从大语言模型的发展中我们真正学到的一点是，它们都是非常“饥饿”的。它们对数据有着极度的饥渴。而在人类社会中，为了这些大语言模型，我们其实已经生成并积累了数千年的数据。它们使用的是人类经过数个世代和不同文明所创造出来的所有人类语言。但在生物学中，我们根本没有类似这样的现成资产，对吧？特别是当你考虑到，我们需要的是那种极其精准的、一次针对单个细胞的测量数据。我们还需要准确地知道那个细胞究竟发生了什么变化，因为我们试图构建的是一个具有预测能力的、动态的模型，能够预测当某个事件作用于细胞时，它会如何改变。因此，我们必须自己去从头生成这样一个数据集。这对于我们能够在这里构建出任何有用的模型而言，绝对是至关重要的核心。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Yeah, absolutely. I mean, really what we learn, again, for large language models, is just they're very hungry. They’re very data-hungry. And really we’ve been generating data for these language models for thousands of years. They're using all human languages that's been generated over generations and civilizations. In biology, we don't have anything similar to that, right? Especially when you're thinking about, we need these precise measurements kind of one cell at a time. And we also need to know what actually happened to that cell because we're trying to build a predictive model, a dynamic model, that can predict how a cell will change when something happens to it. And so we need to generate that data set. And that's kind of really core to being able to build any useful model here.

</details>

**克里斯·安德森 (Chris Anderson)**: 那么，给我们描述一下你们实际上是如何开展这项工作的。

<details>
<summary>Original English</summary>

**Chris Anderson**: So give a sense of how you actually do this.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 本质上，这确实是把我刚才提到的前两个元素结合了起来，也就是做出定向的、靶向的改变。在这种情况下，我们正在使用 CRISPR 技术去关闭某个基因，或者开启某个基因。我们正在对一个又一个的细胞，一次只针对其中一个基因进行这样的操作。然后，我们使用单细胞 RNA 测序来测量这个操作的输出结果，这样我们就能准确捕捉到细胞发生了什么。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Essentially, this is really combining those first two elements I was talking about, which is making a targeted change. In this case, we're using CRISPR technology to turn a gene off or to turn it on. And we're doing that one gene at a time for one cell at a time. And then we’re measuring the outcome using single-cell RNA sequencing so we’re capturing what happened to the cell.

</details>

**克里斯·安德森 (Chris Anderson)**: 所以，你们对细胞进行了一次你所说的“扰动（perturbation）”。然后测量它的输出结果。像这样的实验，你们需要做多少次？你们的计划是什么？

<details>
<summary>Original English</summary>

**Chris Anderson**: So you do what you call a perturbation of the cell. And then you measure the output. How many experiments like that do you need to do, what's your plan?

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 我们的计划是开展至少 **十亿次 (one billion)** 这样的物理实验。这真的是极其庞大的一笔实验数量。（笑）我们将会在接下来的四年时间里完成它。

<details>
<summary>Original English</summary>

**Silvana Konermann**: So our plan is to do at least a billion of these experiments. So it's a lot of experiments. (Laughs) Over the next four years.

</details>

**克里斯·安德森 (Chris Anderson)**: 而且你说的可不是软件模拟的实验，你指的是 10 亿次真实的、生物学上的物理实验——

<details>
<summary>Original English</summary>

**Chris Anderson**: And you're not talking about, like in software, you're talking about a billion actual, biological --

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 是的，它们全部都是实实在在的物理实验。我的意思是，我是一名生物学家，一名实验生物学家。我们在实验室里要处理大量的实验。但我们之所以能够做到这一点，是因为我们使用了一些巧妙的方法和技术，使其实际上具有了极高的可扩展性。我们并不是在真的去一个接一个地运行 10 亿个微小的、独立的反应容器。我们能够利用不同的条形码技术（bar-coding technologies），在更大的混合池（pools）中并行运行这些实验，然后通过数据分析反推出每个细胞里发生了什么以及我们对这些细胞做了什么。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Yeah, they're all physical experiments. I mean, I'm a biologist, an experimental biologist. We're working with a lot of experiments in the lab. And yet the way that we can do this is kind of using some tricks that make this much more scalable. We’re not actually like, running a billion little individual reactions. We're able to use kind of different bar-coding technologies to run these experiments in this bigger pools and then back out what happened [and] what we did to the cells.

</details>

### 细胞的状态设计

**克里斯·安德森 (Chris Anderson)**: 好的，如果事情能像你所希望的那样顺利进展——我猜你其实已经看到了它正在顺利推进的证据。一旦你收集到了这些海量的数据，你就能从模型中获得一些真正令人惊叹的成果。和我们谈谈这个吧。

<details>
<summary>Original English</summary>

**Chris Anderson**: OK, so if things work out as you hope -- I guess you’re already seeing evidence that it’s working out. Once you gather that data, you're able to get from the model something truly amazing. Talk about that.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 为了让大家对为什么我们有信心完成这 10 亿次实验有一个直观的感受，我想说的是，到目前为止我们已经完成了大约 6000 万次（60 million）实验。

<details>
<summary>Original English</summary>

**Silvana Konermann**: So just to give a sense of why I feel that we can do the billion experiments is we've done about 60 million experiments so far.

</details>

**克里斯·安德森 (Chris Anderson)**: 你们已经完成了 6000 万次，好吧。

<details>
<summary>Original English</summary>

**Chris Anderson**: You've done 60 million, right.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 所以我们感觉状态非常好，有信心能够继续坚持做下去。但是，是的，做这件事的整个核心意义在于我们渴望去学习：如果我手头有这样一个细胞，然后我对它做出了这道改变，那么这个细胞究竟会发生什么变化？我生成这个模型的最终和最大动力，终究是为了人类的健康事业。为了实现这一目标，我们现在可以先获取一个疾病状态的细胞。非常重要的一点是，例如，这可以是阿尔茨海默病中的某种特定细胞——比如大脑中的一种免疫细胞：**小胶质细胞 (Microglia)**。我们可以去测量这个病变细胞在微观上是什么样子的，而且这不仅仅针对某一个具体的患者，而是跨越和涵盖许多不同的患者。这种疾病数据目前在公共数据库里是现成的，所以我们甚至都不需要自己去动手生成它。

然后，我们可以向模型发问。我们能把这些病变细胞的状态以及所有正常健康细胞的状态（同样是跨越不同个体的）输入进去。接着我们问模型：“好，模型，你已经掌握了如何改变细胞的技术，对吧？那么，我究竟需要进行什么样的干预，需要做出什么基因层面的改变，或者什么化学成分的改变，才能让所有这些来自不同病人的病变细胞，全部转化并恢复到健康的细胞状态？”

<details>
<summary>Original English</summary>

**Silvana Konermann**: So we feel pretty good we can keep going. But yeah, the whole point of this is that we want to learn. If I have this cell, and I make this change, what happens to the cell? Really my motivation for generating this model is ultimately for human health. And so for that, we can now have a disease state. And importantly, this can be, for example, a certain cell in Alzheimer’s disease -- let’s say it’s an immune cell in the brain: microglia. And we can measure, what that looks like, not just for one patient, but across many patients. And this data is out there, so we don't even have to generate it. And so we can see, OK, all these diseased cells, then we can have all the healthy cells, but again across people. And then we can ask the model, OK, the model knows how to change cells, right? So what intervention, what genetic change, what chemical change do I need to make to convert all the diseased cells across all the patients with the same disease back to the healthy cells?

</details>

**克里斯·安德森 (Chris Anderson)**: 那绝对是一个令人惊叹的预测。也就是说，如果你真正理解了 DNA 的语言，该模型就可以预测出一些医学界以前从未知道的事情，因为要将那个病变细胞还原，所需的答案可能是一系列非常复杂的组合干预措施。这绝不是你简单地给它吃一片阿司匹林就能解决的。

<details>
<summary>Original English</summary>

**Chris Anderson**: So that's an amazing sort of prediction. Like, if you truly understand the language of DNA, the model can predict something that medicine has never known before, because the answer to doing that might be quite a complex series of interventions are needed for that cell. It's not like you just give it an aspirin.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 它确实有可能是一系列非常复杂的因子的组合，或者其实也可能仅仅是关于如何从中精准挑选出那一个正确因子的问题，对吧？要知道，基因组里有大约 20,000 种可能性——如果把上调和下调都算进去，那就是 40,000 种可能性。在如今的生物医学界，进行这种靶点识别（target identification）的常规操作方法，基本上就是一种“假设与验证”（guess and check）的方法。也就是说，你先提出一个科学假设，认定某个特定的基因是关键，然后你得花上几年的时间去实验验证这到底是不是正确的那一个，对吧？如果你有 40,000 个候选靶点供你挑选，即使你最终只需要在其中精准选出一个靶点，这种传统的验证方式也会耗费极其漫长的时间，对吧？而这也正是为什么直到今天我们仍然没能彻底治愈这些复杂疾病的原因。

<details>
<summary>Original English</summary>

**Silvana Konermann**: It could be that it's a complex combination of things, or it's really just a question even of picking the correct one, right? There’s, you know, 20,000 possibilities -- could be up or down to 40,000 possibilities. And normally, the way this target identification and biomedicine works today is really this kind of guess and check approach. So you have a hypothesis, one gene, then you're spending a few years on checking whether that's the right one, right? So if you have 40,000 things to pick from, even if you just have to pick a single one, that takes forever, right? And that's why we haven't cured these diseases yet.

</details>

### 开源与挑战赛

**克里斯·安德森 (Chris Anderson)**: 那么随着你逐步精炼和改进这个模型，你打算用它来做些什么？我的理解是，你们认为这在基本上就是创造出了一个**虚拟细胞 (Virtual Cell)**——这几乎不仅仅是如此。它更像是一个通用的虚拟细胞，无论其他研究人员正在研究什么细胞，他们都可以随时使用你们的这个模型。谈谈你们计划如何处置和应用这个模型吧。

<details>
<summary>Original English</summary>

**Chris Anderson**: So what are you going to do with this model as you gradually refine it? I mean, [as] I understand, you think of this as basically a virtual cell, [that] is what you’re creating -- it’s almost more than that. It's like a universal virtual cell that researchers can, whatever cell they’re working on, use your model. Talk about what you're planning to do with it.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 做这件事情的核心点在于，它必须是一个通用的虚拟细胞。这意味着它需要学会如何在没有任何针对该新细胞类型的训练数据的情况下，推广并外推（generalize）到一种全新的细胞类型、细胞的全新状态或是全新的疾病上。这是一个极具挑战性的任务。而这也正是我们目前正在非常深入地思考如何设计和开展这些实验的原因。但在归根结底，我的意思是，我们在这里看到的是，这个愿景其实正在逐步变成现实。这就是我们的状态设计器（state designer）。我们已经构建出了我们的第一个模型，它是在八个月前发布的。实事求是地说，它现在还不是特别好。虽然我想澄清的是，它在当时发表的时候已经是处于世界最前沿（state-of-the-art）的技术，是那个时候已发表的性能最好的模型。（笑声）但是，要达到我认为真正能够发挥关键作用和实用价值的精度，它还有非常漫长的一段路要走。不过，这就是一个使用了我们今天已有的这个模型的交互界面。所以你现在就可以在上面操作，你可以说：“好吧，我手头有这个起始细胞。然后，我想要改变这个细胞的这些特征。” 接下来，它就会吐出你可以对这个细胞做出的几种不同改变，这些改变是模型认为最有可能按照你期望的方向去转换细胞状态的。

<details>
<summary>Original English</summary>

**Silvana Konermann**: The whole point of it is that it is a universal virtual cell, which means that it needs to learn how to generalize to a new kind of cell or a new state of a cell, a new disease, for example, without having seen data, training data for that new cell type. So that is a very challenging task. And that's why we're really thinking hard about how to do these experiments. But ultimately, I mean, this is what we're seeing here is, you know, the vision is that this is actually real. So this is our state designer. So we have already built our first model that came out eight months ago. It's not very good. So I mean to be clear, it is state-of-the-art, it's the best model at the time that was published. (Laughter) But it has a really long way to go to be at the accuracy that I think it needs to be to be really useful. But this is an interface that uses that model that we have today. And so what you can do is you can say, “OK, I have this cell that I’m starting with. And then, you know, I want to change this about the cell.” And then it spits out these different changes that you can make to the cell that are most likely to shift it the way you want.

</details>

**克里斯·安德森 (Chris Anderson)**: 所以你们并没有把这个模型据为己有，或者独家授权给某些大型制药公司，而是将其公开发布，让所有人都能免费使用。

<details>
<summary>Original English</summary>

**Chris Anderson**: So you're not holding on to this yourself or licensing it to companies, you're making this generally available.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 是的，完全是这样。我们规划了几个途径，非常希望人们——（观众掌声）能够借此与它进行交互，并紧密跟踪我们的进展。其中一个是，我们将会在今年晚些时候发布这个工具，供所有人亲自尝试。我们当然会给出一些警告，比如，它目前的准确度还不是很完美，大概只有 20% 左右的准确率，但我们也会在接下来的四年里不断进行迭代和升级。同时，我们每年都会面向全球的整个科学共同体举办一场“**虚拟细胞挑战赛 (Virtual Cell Challenge)**”。在第一届比赛中，我们已经吸引了 1,000 支队伍报名参赛，这真的是为了推动整个生物学和 AI 领域的共同进步，最终达到我认为我们需要达到的高度。

<details>
<summary>Original English</summary>

**Silvana Konermann**: That's right, yeah. So we have a few ways that we really want people -- (Applause) People to be able to interact with it and also follow along. So one is we're going to be releasing this tool later this year for people to try. We'll give caveats like, this is not very accurate or this is going to be 20 percent accurate, but also we're going to iterate over the next four years. We’re also hosting a “Virtual Cell Challenge” every year for the whole community. We have 1,000 teams participating in the first one, and that's really to move the whole field forward, to get to where I think we need to be.

</details>

### 虚拟细胞的安全性

**克里斯·安德森 (Chris Anderson)**: 这真的太令人振奋了。你们研究所开展的这项令人惊叹的工作，因为你们主动将其开源并提供给所有人，真的将会极大地催化全球范围内的科学研究。但有些人在看到这个项目的时候可能会产生疑虑，他们会想：“等一下，这难道不是有点危险吗？” 某些接触到这个工具的人，可能并不一定心怀人类的最大利益。你对这种担忧怎么看？

<details>
<summary>Original English</summary>

**Chris Anderson**: So this is amazing. The amazing work in your institute is really going to catalyze research worldwide because you're making this tool available. Some people looking at that may go, “Well, wait a sec, isn’t that a little bit dangerous?” Some of the people playing with this may not have humanity’s best interests at heart. What do you say to that?

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 这绝对是一个非常关键的问题。正如你所知，我们在申请“Audacious Project”基金的过程中也多次被问到了这个问题。我认为需要牢记的最核心一点是，我们的这个模型纯粹是针对人类细胞构建的。在理论上，如果有人想为某种致命病毒构建类似的 AI 预测工具，那我必须站出来大声疾呼：千万不要这样做，那是一个极其糟糕的主意。因为确实，如果你针对病毒开发这种工具，你就完全可以用它来制造出一些极具杀伤力和危险性的东西。但我们的工具真的只是允许你去将人类的细胞转移和恢复到不同的状态，而这在原理上是极难被恶意滥用的。

<details>
<summary>Original English</summary>

**Silvana Konermann**: That’s definitely a question that I think, as you know, we got during the Audacious process. And I think the key thing to keep in mind is that this is really just for human cells. In theory, someone could build this kind of tool for a virus. And I would say, don't do that, that's a bad idea, because yes, then you can absolutely use it to create something that would be dangerous. But this really just allows you to shift human cells into a different state. And I think that would be pretty difficult to abuse.

</details>

**克里斯·安德森 (Chris Anderson)**: 而且从原理上讲，如果未来真的出现某种极其凶猛的新型病毒，如果你们的这个虚拟细胞模型运行良好，它实际上也能为我们提供最快速的防御手段之一——

<details>
<summary>Original English</summary>

**Chris Anderson**: And in principle, if a nasty virus did come along and this model is working properly, that's a way of giving us one of the quickest --

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 是的，没错。我的意思是，比如它会直接告诉你，该病毒目前正在靶向和攻击这个细胞里的这个特定基因。那么，我们就能立刻知道，当那个基因被病毒靶向攻击时，细胞内会发生什么连锁病变反应。所以，是的，它绝对能够有力地帮助我们去建立对未知病原体的防御体系。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Yeah, I mean, it will tell you, for example, how the virus is targeting this gene in this cell right now. OK, we know what happens to the cell when that's getting targeted. So yeah, it will absolutely help us to defend.

</details>

### 跨学科的未来

**克里斯·安德森 (Chris Anderson)**: 这就是你们的团队。和我们介绍一下他们吧。

<details>
<summary>Original English</summary>

**Chris Anderson**: So here's your team. Tell us about them.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 好的，**Arc 研究所 (Arc Institute)** 实际上是在 2022 年才刚刚成立的——那一年我们决定正式推出它。2022 年是我们真正让研究所运转和步入正轨的一年。所以虽然到目前为止只有短短的四年时间，但我们已经成长了非常多。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Yeah, so Arc was only started in 2022 -- [which was] when we decided to launch. 2022 is really when we got up and running. So it's only been four years, but we've grown a lot.

</details>

**克里斯·安德森 (Chris Anderson)**: 所以，这就是四年前和四年后的对比照片吗？

<details>
<summary>Original English</summary>

**Chris Anderson**: So that's the before and after over four years?

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 那其实只是我们仅仅一年的成长轨迹——也就是过去这一年里的巨大变化。我们现在已经拥有了超过 300 名员工。我认为，我们非常渴望通过 Arc 研究所实现的一大目标，就是将来自不同学科背景的人才紧密地聚集在一起，将人工智能与生物学这两大学科完美地融合在同一个研究所的屋檐下。我们在大约最合适的时间启动了这一尝试，那个时候我们刚好能够清晰地预见到，机器学习对于整个生物学领域的未来而言究竟意味着什么。

<details>
<summary>Original English</summary>

**Silvana Konermann**: That’s just one year of growth -- the last year. So we're over 300 people now. And I think one thing we really wanted to be able to achieve with Arc is to bring people together from different disciplines and have AI and biology under one roof in one institute. And we started this just around the right time when we could see what machine learning was going to mean for biology.

</details>

**克里斯·安德森 (Chris Anderson)**: 西尔瓦娜，我真的非常兴奋能够看到“Audacious Project”社区能够站在你们的身后，全力支持你们，帮助你们将这个伟大的愿景做大做强。真的很难想象还有比这更大胆的尝试了，它不仅切实地直面和解决了人类最迫切的医疗需求，而且在当下这个时期，也让我们所有人对人工智能的未来有了一种更好的期待和更积极的感受。对于每一个家里正有亲人遭受着阿尔茨海默病、心脏病或类似疾病折磨的观众，你有什么话想对他们说吗？

<details>
<summary>Original English</summary>

**Chris Anderson**: Silvana, I got so excited to see the Audacious community get behind this and really help you expand this vision. It's hard to imagine a bolder effort at really tackling what humanity needs and in making us all feel better about AI. So someone here who's got in their family, they've got Alzheimer's or they've got heart disease or whatever, what would you say to them?

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 我想对他们说的是，我真的坚信，针对这些复杂疾病的医学研究和治疗手段在未来将会发生根本性的翻天覆地的转变，对吧？它可能无法在短短的三个月内立刻实现，所以大家必须要保持一点耐心。但我相信，在接下来的四到五年内，我们一定能够拥有足够精准、足够成熟的虚拟细胞模型来投入实际的医疗应用。到那时，人们做生物学研究的方式将会完全不同。它绝不再是过去那种一次只针对一个单一假设去埋头苦干的低效模式，对吧？

像阿尔茨海默病这样的庞大领域，过去常常因为只聚焦于某一个占据主导地位的科学假设而陷入泥潭，甚至在那个假设最终被证明是错误的时候，导致整个领域裹足不前。而有了这些先进的虚拟细胞模型，你可以真正采取一种全面的、完全由海量数据驱动的全新视角，去审视所有可能作为药物靶点的潜在基因，去精准预测对所有这些靶点进行干预后将会发生什么，然后从中挑选出到底哪一个才是最安全、最有效的。这是一种截然不同的、攻克人类疾病难题的全新方式，它真的是太令人兴奋了。

<details>
<summary>Original English</summary>

**Silvana Konermann**: I mean, I would say that I really think the medicine is going to transform for these kinds of diseases, right? Maybe not in three months. So you have to be a little patient. But I think that within four years, five years, we will be able to have these models that are accurate enough to be useful. And then it's a totally different way of doing biology. It's not kind of, one hypothesis at a time, right? A field like Alzheimer's can get really bogged down by just focusing on one dominant hypothesis that might be wrong. And with these models, you can actually take a comprehensive data-driven look, you know, [at] all the things that we could be targeting with a drug, what's going to happen with all of them, and then which of them is going to be the most effective one? It's just a totally different way of tackling the problem that I think is so exciting.

</details>

**克里斯·安德森 (Chris Anderson)**: 西尔瓦娜，非常感谢你带来的令人难以置信的宏伟愿景，也非常感谢你今天来到这里与我们大家分享。这真的太棒了。

<details>
<summary>Original English</summary>

**Chris Anderson**: Silvana, thank you for your incredible vision, for sharing it with us. Thank you, really, just fantastic.

</details>

**西尔瓦娜·科纳曼 (Silvana Konermann)**: 非常感谢你们。

<details>
<summary>Original English</summary>

**Silvana Konermann**: Thank you so much. (Cheers and applause)

</details>