---
author: Latent Space
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3nAV2s4GYbs
speaker: Latent Space
tags:
  - virtual-cell
  - systems-biology
  - perturbation-biology
  - single-cell
  - lab-in-the-loop
title: Fabian Theis 谈虚拟细胞、类器官扰动与闭环实验设计
summary: Fabian Theis 探讨了计算生物学与虚拟细胞的发展演进。内容涵盖单细胞转录组学、类器官扰动建模、基础模型与流式匹配的应用，以及学术界与初创企业如何通过闭环系统指导下一步湿实验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Fabian Theis
companies_orgs:
  - Helmholtz Munich
products_models:
  - Scanpy
  - AnnData
  - scverse
  - scGen
  - CellFlow
media_books: []
status: evergreen
---
### 虚拟细胞与闭环实验

>> 我们现在确实可以开始指导实验了。以前在构建这些人类细胞图谱时，我们做的是类似于测绘的工作。我们讨论过世界模型的预测问题。从测绘，我们走向了预测。但是现在，

<details><summary>Original English</summary>
>> We can really now start guiding the experimentation. So, where before you we built these human cell atlases, we had sort of this mapping aspect. And we talked about the world model prediction problem. From mapping we went to prediction. But now,
</details>

>> [音乐]

<details><summary>Original English</summary>
>> [music]
</details>

>> 我们可以转向实际指导下一步实验。但坦白讲，过去的论文往往就以某个模型告终，对吧？也许展示一张概念图，也许做了一点点验证。但通常接着就去开展下一个项目了，对吧？当然你能学到一点东西，但这并不像是一种持续学习的过程。而我们开发了一个叫做 Lab Compass 的新工具，它是一个逆向生成模型，一旦你拥有了前向世界模型之类的东西，它能告诉你为了达到某种特定状态，你需要去进行什么样的操作。显然，最终的愿景是希望将强化学习应用于一切，我们希望在这个闭环中也引入强化学习。这听起来有点遥远，但我觉得我们正在一步步靠近。

<details><summary>Original English</summary>
>> we can go to actually steering the next experiment. But quite frankly, very often the papers ended with some model, right? Maybe some sort of concept figure, maybe had a little bit validation. But then typically you start the next project, right? And of course you learn a bit, but there's not like not like a continual learning type of thing. And new thing which we call lab compass, which is an inverse generative model that actually allows you once you have a forward world model whatever to tell [music] you what you need to do in order to reach a certain state. Obviously there the ultimate vision being that we want to RL everything, we want to do RL also in in this loop. It's a bit out there, but you know, I think we're we're slowly getting there.
</details>

### 播客开场与嘉宾介绍

>> 欢迎收听 Latent Space 的 AI for Science 播客。我是 Miro Omics 的首席技术官 RJ Honicky。与我一同主持的是 Atomic AI 开发 RNA 疗法的 Brandon Anderson。我无论怎么强调都不为过：Fabian Theis 以及他的实验室和创立的企业，对系统生物学的发展以及虚拟细胞概念的多次迭代做出了多么巨大的贡献。他们实验室发表的论文和模型的速度快得我都读不过来，并且该实验室一直在持续推动我们在观察和建模细胞行为及相互作用方面的认知。

同样重要的是，他的工作经常专注于打造研究人员和科学家在日常工作中真正使用的工具。大多数计算生物学家在某些阶段可能都用过 Scanpy 和 AnnData。这些工作催生了 SCverse，这是一个令人惊叹的开源工具集合，吸引了非常多的贡献者。

当然，Fabian 获得的荣誉多到数不胜数，但简而言之，他在慕尼黑亥姆霍兹中心及相关机构领导了多项人工智能和计算生物学项目，并且还深度参与了许多产业界的合作。

Fabian，非常高兴见到你。非常感谢你能加入我们的节目。

<details><summary>Original English</summary>
>> Welcome to the Latent Space AI for Science podcast. I'm RJ Honicky, CTO of Miro Omics. I'm joined by my co-host Brandon Anderson, who develops RNA therapeutics at Atomic AI. I can't emphasize enough how much Fabian Theis and his labs and companies have contributed to the development of systems biology and various iterations of the virtual cell concept. Papers and models come out of his lab faster than I can read them, and the lab is consistently moving the ball forward on our understanding of how to observe and model the behaviors and the interactions of cells.

Just as importantly, his work often focuses on creating the tools that researchers and scientists actually use in their day-to-day work. Most computational biologists have probably used Scanpy and AnnData at some point. And this work has led to the creation of SCverse, which is an amazing collection of open tools that's attracted many many contributors.

Of course, Fabian is one of those academics who has way more honors than you can possibly list, but suffice it to say that he leads a bunch of the AI and computational biology efforts at Helmholtz Munich and related institutions, and participates also in many other industry efforts.

Fabian, it's really great to meet you. Thanks a lot for joining us.
</details>

>> 感谢你们的邀请。我非常期待这次讨论。

<details><summary>Original English</summary>
>> Thanks for having me. I'm really looking forward to the discussion, man.
</details>

### 制药行业对虚拟细胞的关注度

>> 是的，我关注你的研究很长时间了，所以非常荣幸终于能请你来到节目中进行交流。让我们从当前正在发生的一些行业热点开始吧。现在结构生物学领域引起了极大的关注，Anthropic 和 OpenAI 的生物医药计划目前都高度聚焦于分子设计。而在另一方面，虚拟细胞和系统生物学方法最近并没有受到同等的关注。也许 Zera 和 Noetik 是很好的反例，而且 Biohub 刚刚宣布了一项与美国能源部（DOE）、美国国立卫生研究院（NIH）、Meta 和 Google 达成的 18 亿美元合作项目，旨在收集并开源多尺度生物学数据，用于开发新一代虚拟细胞。所以我想问的是，根据我们目前在学术界看到的活跃度，你是否认为制药行业即将对虚拟细胞重新产生浓厚的兴趣？

<details><summary>Original English</summary>
>> Yeah, I've been tracking your work for a long time, and so it's a great honor to finally get you on the show and talk to you. Let's kick things off with some of the hype happening right now. There's a ton of interest right now in structural biology, Anthropic and OpenAI biopharma initiatives focus heavily on designing molecules right now. On the other hand, virtual cell and systems biology approaches really haven't gotten as much attention recently. Maybe Zera and Noetik are good counterexamples there, but Biohub just announced a $1.8 billion collaboration with the DOE, NIH, Meta, and Google to collect and open-source multiscale biological data that can be used to develop a new generation of virtual cells. So, my question, do you think that we're about to see renewed interest from the pharma industry in virtual cells based on the activity that we're seeing in academia right now?
</details>

>> 在回答之前我应该先声明，显然我的观点偏向学术界视角。当我与那些日常在初创企业工作的同行朋友交谈时，他们对各个初创公司的动态一清二楚，就像我对各个学术研究实验室的动向拥有全局概览和直觉一样。他们知道眼下的风口是什么、哪些领域正在获得投资。我并没有涉足那么大的规模。但话虽如此，例如你提到的 Biohub 倡议，顺便说一句，它也与人类细胞图谱（Human Cell Atlas）紧密相连，后者是一个推动生成下一代数据集的全球国际财团。

我确实认为有一系列的原因表明，我们会看到这种技术规模化扩展。这不仅是因为所有这些模型在生成能力上表现优异，也是因为在分子层面的“在环实验室”（lab-in-the-loop）模式现在正在向上一层级输出，真正扩展到了细胞层面。

我认为这背后有一系列原因。第一个，也可能是最重要的一个，正如你刚才指出的，就是数据生成。

我们对虚拟细胞的概念探讨已有一段时间，我的实验室在 2019 年发表了一篇名为 scGen 的论文，开始利用机器学习进行扰动预测建模。那是一个非线性模型，但本质上在潜在空间中执行了某种线性变换。其实它的效果相当不错，甚至放到今天，许多类似的伪线性方法表现依然可圈可点。但之所以会这样，我认为是因为我们当时的数据集以及基于其上提出的问题仍然偏简单。这也是它当时没有全面兴起的原因。因此，每当人们谈论虚拟细胞时，也许正对应你的问题，我认为你实际上在问的是：

你是否能够预测细胞在各种扰动下的行为表现？

我认为这是一个非常深刻的问题。深入思考的话，它甚至可以说是计算生物学和系统生物学领域的一大终极追求。细胞是一个具有记忆、具有特定分化状态、包含各种不同分子层级（不仅是 RNA）的输入输出系统。能够描绘出这一系统的全貌——甚至说“理解”到底意味着什么？这稍微带一点元问题（meta-problem）的性质，但只要你能根据不同的输入去预测其输出行为，你就已经能非常好地理解或者至少能够建模这个系统了。因此我认为这是一个非常好的问题。

这也是为什么如今人们经常将虚拟细胞等同于扰动预测。我认为这种理解略显简单化，但这类扰动预测模型——也就是你所说的虚拟细胞——在初创生态中正在迅猛发展。那里的发展甚至可以说是呈爆炸式态势，在美国和欧洲有大量动态，在中国生态系统中现在也涌现了许多此类努力。我希望这不仅是人人给项目贴上 AI 标签而掀起的热潮，而是因为制药界目前在其筛选中急切需要具备细胞类型和背景特异性，而他们目前的技术手段在这些筛选中尚无法做到这一点。

<details><summary>Original English</summary>
>> I I I should disclose before I sort of go to to the answer that obviously my my opinion is quite academic in the sense that whenever I talk to to my my friends and colleagues that really sort of day-by-day sit in in the startups, they have like like what I sort of have as an overview and sort of a bit of intuition what the different research labs do, they have the same thing for the startups. And they know this is sort of the the hot big thing that, you know, this and this investments are happening. I don't really have that on on that scale. But having said that, for example, you you you you may you mentioned a Biohub's initiative, which by the way is also heavily coupled to human cell atlas, which is sort of this international really worldwide consortium that sort of pushes this next uh level of data set generation. I do think that there's a whole bunch of reasons why we going to see that sort of scale up from all these models working well in terms of being generative, but also sort of lap in the loop on the molecule level now being exported and sort of really working one level up on on on the cell level.

And I I think there's a bunch of reasons for that. And the first one I think it maybe the most important one, which you really hit here, is the data generation. I think we had that concept of a virtual cell for a while, but my my lab we started this perturbation prediction modeling and and using machine learning in 2019 with a paper we called SEGAN at the time, which was like it was a non-linear model, but essentially sort of in the latent space did some linear transformation. And it was actually quite okay, and even nowadays many of these sort of pseudo-linear type of things are still doing a good job, but the reason for that being that I think the data sets and the questions that we asked on top were just sort of still on the simplistic side. That's why also sort of it didn't yet take up. So whenever people talk about virtual cells, maybe also your question, I think what you actually ask is

how does Can you predict how a cell would behave under all kind of perturbations? And that's sort of I think a quite deep question. If you really think about it, it's maybe even a bit of a holy grail in computational biology systems biology. Sort of this this input-output system that is a cell with memory and like with all these specifications and with all the different sort of levels of molecules and so on, not just RNA. I I think being able to map this out, what does even understanding mean? And I've been this sort of a bit of a meta problem, but I I think you understand or at least you model a system very well when you sort of predict its output behavior given different inputs. So I think it's a very good question, and this is why often people nowadays equate a virtual cell with um perturbation prediction. I think it's a bit too simplistic, but I think these perturbation prediction type of models and that's sort of being a maybe what you mean by virtual cell is taking off a lot in the startup landscape. I think it's a bit exploding there because I think a lot about US Europe, but also in in the Chinese ecosystem there's a lot of of these these additional efforts now happening. And I I hope that these are not just sort of now a kindling of of a flame because everyone sort of adds AI to their things, but because pharma is really desperately uh needing to be cell type context-specific in their screens, which at the moment they can't do yet. on that screen.
</details>

### 转录组学与扰动概念解析

>> 也许你能更详细地解释一下这是什么概念？比如我们最近和 Zera 交流过，他们正在做这类扰动筛选。这开启了什么样的能力？你认为下一代数据在此基础上又将带来什么样的突破？

<details><summary>Original English</summary>
>> Maybe you could expound a little bit on what does this So perturbations right now that like we talked to Zara recently, they're doing these perturbation screens. What does that unlock? And then what What do you think the next generation of data is going to unlock in addition to that?
</details>

>> 对我而言，如果可以的话，如果我讲了太多过去的往事，你可以随时打断我。我作为一个长期受训的机器学习科学家，做过各种各样的事情，但我很早就开始接触单细胞 qPCR。如果说实话的话，最初可能并不是因为我对生物学本身多么感兴趣，而是因为我们可以获得极高的样本量，纯粹是出于这个原因，对吧？因为早期很明显 qPCR 的规模很可观，随后转录组数据的规模更是急剧扩大。在我职业生涯早期，我们处理的数据只有极少量的 bulk RNA，而后来我们拥有了数以千计的数据。那是早期的情况。

但如今我们进入了一个全新的阶段。当 PacBio 推出他们称之为“Giga Lab”或类似项目时，那是一个令人大开眼界的时刻。竞争对手公司现在也有类似的技术，但在单个实验中能够测量 1000 万个转录组，我觉得这完全是跨维度的突破。

从以往仅仅增加外周血单核细胞（PBMC）作为对照工具，发展到现在真正进行大规模研究，以前的一侧是细胞空间，另一侧则是扰动空间，而后者过去通常极度稀缺，往往只是对照组与疾病组的对比。因此，以前在扰动空间中所拥有的采样点数量，通常远远少于在细胞空间中所拥有的观测数量。

但现在情况正在爆发式增长。比如现在可以在 100 种不同的细胞系上做全套的 Perturb-seq（即全基因组 CRISPR 敲除），或者添加包含 1000 种药物的药物组合，这个空间瞬间变得极其丰富，对吧？然后你就可以开始做各种高阶的扰动预测任务了。这正是目前正在发生的事情，其规模非常惊人。我们自己也参与了一系列研究，正在走出单纯的细胞系，转向类器官扰动。如果有时间我们可以深入聊聊这个，因为我非常坚信我们需要走向多细胞系统才能获得真正有价值的读数。但无论如何，每个人都在扩大这些层面的规模，在未来某一刻，我们甚至可能将人类遗传学变异作为一种扰动纳入考量。

<details><summary>Original English</summary>
>> I mean for for me, if I may, you stop me when I'm sort of getting to too much into these these these old stories. Like, you know, I'm sort of I've been trained machine learning scientist for longest time doing all kinds of things, but you know, I started with single cell early on qPCR. Maybe initially, if I'm really honest, not so much because it was like the biology that I was interested in, but because we had high sample numbers, purely for that, right? Because even earlier on it was sort of clear that the number of qPCRs at scale, but then of course transcriptomes was just getting really big. And you know, when I started my career earlier on, we had like a few bug RNA, now we sort of had thousands of them or whatever, right? So, this is like early times. But now, you know, we we're going to to regime, and that was sort of one of these eye-opening moments when when Pac Bio had like I think they called it the giga lab or something like that. And you know, there's sort of similar ones from from competing companies now, but when they had like in a single experiment 10 million transcriptomes measured, right?

I felt that was like like next-level stuff, and you know, this step from just getting more PBMCs as a control tool, like let's actually do something at scale to it sort of having here the cell space, but then having here the perturbation space, which typically was very scarce. It was like control versus disease or so. So, this sort of number of points what you had here in terms of sampling on the perturbation space was typically much much more scarce than the number of observations in terms of cells that you had. But now this is exploding. Now you sort of have, I don't know, 100 different cell lines where you do sort of full perturbsic like full CRISPR, or you have like batteries of 1,000 drugs or so added, and suddenly this space gets really rich, right? And then you can sort of start doing all these fancy perturbation prediction type of things. And this is currently happening. It's crazy what scale it's happening. We are ourselves involved in a whole bunch of things where we actually go beyond cell lines and do organoid perturbations, and maybe if you have time we can can talk a bit more about that because I'm quite convinced that we need to go to multi-cellular systems to have actually really interesting readouts, but I think everyone is scaling these these these levels up, and at some point, you know, we're going to go maybe even to human genetics as a perturbation.
</details>

>> 你能给那些不熟悉的听众解释一下到底什么是扰动吗？你指的是什么？

<details><summary>Original English</summary>
>> Can you just like explain what is a perturbation? What do you mean by that? Just for the people who are not familiar.
</details>

>> 对对，你介不介意我们再退后一步？比如我们说的测量转录组学到底是什么意思？你刚才提到了基于 PCR 的方法，然后还有 Perturb-seq。

<details><summary>Original English</summary>
>> Yeah, yeah. You actually Would you mind maybe backing up even one step more than that? Like what do we even mean by like measuring transcriptomics? And you were talking about like PCR-based and then also perturb-seq.
</details>

>> 当我做公开演讲时，我通常会说：人类基因组计划让我们知道了人体的全套基因组，但全身每个细胞的基因组基本上都是一样的，对吧？那为什么我们会拥有所有这些不同的细胞类型？具体发生了什么？

最初的层级之一是，每个细胞从基因组中读取的内容是不同的，对吧？这些随后编码下游各种蛋白质的信使 RNA（mRNA），在不同细胞中的表达水平各不相同。在人类体内可能有大约 20,000 种不同类型的基因，如果加上剪接异构体数量还会多得多，但这大致是基准水平。

因此，你实际上得到的是每个细胞对应的一个 20,000 维的向量，其中包含大量的零（表示未表达），以及一系列表明测量到多少信使 RNA 分子计数的数字。因为这些分子被称为转录本，所以这被称为转录组。

在实际操作中，你面对的就是这样一个 20,000 维的空间，通常会将其编码到一个更规整的潜在空间中，这个潜在空间类似于一个子流形，也就是实际细胞群聚生存的子空间。如果这些 20,000 维向量构成的细胞点云聚集成团，我们就把这些团块称为细胞类型或类似的名称。而如果它们延伸成香肠状的连续分布，我们就称之为发育轨迹，比如细胞分化过程——受精卵随后分化生成体内所有的细胞类型。

<details><summary>Original English</summary>
>> When I give sort of public talks I typically say, you know, human genome project, we sort of have the genome for for for the body, but it's pretty much the same everywhere, right? So like why do we have all these different cell types, right? What's sort of happening specifically? And you know, so first level what one of the first levels is that, you know, per cell different stuff is being read off of the genome, right? And these messenger RNAs, which then sort of encode the various downstream proteins, well, these are sort of differently expressed, as one says, in in in different cells. And to say in a human maybe there's something like 20,000 different types of these, and with splicing many many more, but that's sort of the the rough level. So what you de facto have is per cell a 20,000 dimensional vector that has a whole bunch of zeros and stuff is not there, but then a whole bunch of sort of numbers, how many of these counts of these messenger RNAs you have. Because these things are called transcripts, right? This is called then the transcriptome. Yeah, and and and de facto then you have this sort of 20,000 dimensional space that you very often encode in a sort of nicer latent space that sort of has like an a sub-manifold, like sort of this this subspace where this actual cell cloud lives, right? And if the cell cloud then sort of like this sort of 20,000 dimensional vectors, each point then being one cell, right? If they sort of cluster up, then we call these things cell types or something like that. And if they sort of go into a sort of sausage or whatever, right? We call them into trajectories, like a cell differentiation, like the fertilized egg cell then making all the cell types in the body or something like that.
</details>

>> 所以 DNA 就像一本食谱，或者说各个基因就像不同的食材。每个细胞就像一顿饭或一道菜，由不同食材组合而成。而转录组学就像是拿到不同的菜肴后去拆解它：“哦，做成这道菜用了哪些食材？”这个类比恰当吗？

<details><summary>Original English</summary>
>> So like DNA is sort of like a recipe book, or maybe it's a bunch of genes are a bunch of ingredients. And then as you each cell is its own sort of meal or dish or something, which is a combination of different ingredients. And now the trans- transcriptomics is sort of figuring out uh taking different meals and then sort of decomposing them like, "Oh, what ingredients went into make this meal?" So as you is that a dumb analogy?
</details>

>> 我家有好几个孩子都是吃货。我以后会多用用这个比喻，我很喜欢。

<details><summary>Original English</summary>
>> I have a bunch bunch of of foodies as kids. I will use this metaphor a bit more often. I like it.
</details>

>> 谢谢，Brandon。

<details><summary>Original English</summary>
>> Thanks, Brandon.
</details>

>> 我很喜欢。接着说扰动，扰动就是你以某种方式去干扰基因组或转录组，从而改变其中的转录本。通常这是通过 CRISPR 敲除来完成的，你从基因组中移除一个基因，导致其无法表达。然后你观察由于扰动而在表型或实际物理生物学中发生的改变。大致上是这样吗？

<details><summary>Original English</summary>
>> I love it. And And then And then perturbations is when you somehow perturb the the genome or the transcriptome so that it has different transcripts in it. And then typically that's done with a CRISPR knockout where you remove a gene from from the genome and that causes it to not express that genome. You see and then from there then you see what are the phenotypic or the actual changes in the physical biology that occur because of a perturbation. Is that more or less
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 差不多对吧？

<details><summary>Original English</summary>
>> less right?
</details>

>> 或许我可以在这里退一步补充一下。你说得完全正确，但这是最硬核的一种扰动类型，对吧？比如彻底敲除一个基因。在进化过程中这种情况也会发生，但通常生理现象要更微妙一些。当然，为了理解系统，拿掉其中的某些部件是个好办法。而在正常的发育或体内平衡状态下，这些细胞始终在相互交流，它们处于复杂的多细胞状态中，对吧？细胞之间发生着各种各样的通信。

因此，细胞总是受到来自外部的刺激，从而对其产生影响。对我而言，扰动空间本质上就是一个输入空间，涵盖了作用于细胞的一切事物——可能只是因为它挨着另一个细胞并接收到了某种信号通路刺激，或者是某种浓度梯度、激素进入等等。所有这些当然都可以人为上调或下调。甚至最基础的，比如药企做药物筛选所用的体外培养系统，当把细胞放在培养皿中时，你可以使用不同的培养基条件，这些条件也会产生巨大的影响，对吧？对我来说，这在某种程度上依然由生物学驱动，甚至有点像炼金术——人们尝试配制各种鸡尾酒配方，将皮肤细胞诱导回到类似胚胎的状态，进而分化出新细胞去修复体内各处损伤；或者像山中因子（Yamanaka factors），这些都是诺贝尔奖级别的研究成果。

因此，建立一个扰动空间，本质上就是涵盖所有你能对细胞施加的操作。它可以非常丰富，包括基因层面的改动（例如完全敲除或人类遗传学中更微妙的变异）。我认为所有这些都应该被纳入到一个巨大的空间中，包含我们能做的且会影响细胞状态的所有操作。一个虚拟细胞模型应该把所有这些都作为输入，当然也包括它们的组合。此外还包括疾病发生、时间推移等因素的影响。

<details><summary>Original English</summary>
>> Maybe I can take take a step back there because I think I'll tell you you're fully right but but this is sort of one of the hardcore type of perturbations, right? Like fully knocking out a gene. Soon enough in evolution happens a bit but mostly these things are sort of a tad more subtle. But of course in order to understand the system, it's a good idea to take out between pieces. I think what happens sort of on on a normal development or normal sort of us being in homeostasis is of course that these these cells sort of talk to each other all the time, you know, they're sort of living these complex multicellular states, right? So, there's all kind of communications happening between cells. So, they always have stuff coming from the outside and then sort of doing something to them. So, for me a perturbation space in fact is just an input space to stuff that happens to a cell just maybe because it just sits to another one and there's like some signaling happening, right? Or some gradient, some hormones coming in, whatever, right? And all this stuff of course you can also sort of tune up or tune down. Maybe even something as basic as when you go these in vitro systems where pharma does drug screens, when you sort of put them in a dish, you know, you can do different what's called media conditions and they also have so much impact, right? And it's like a bit of for me still like a a bio-driven, maybe even like an alchemy, what type of cocktails people come up with to then sort of maybe take, you know, skin cells and turn them into into more or less embryo-like state cells, right? Where you can then sort of make new cells to heal different stuff in the body or these what they call the Yamanaka factors for example, you know, these were um Nobel laureate type of stuff, right? So, I think having a space of perturbations essentially of things that you can do to a cell. This can be a very rich thing. It could can go on as much as actually changes in in in the gene, which would be like a full knockout or something more subtle, right? Which is sort of human genetics. And I think all of that we need to put in a big space of stuff that we can do that has an influence of cell state. And And like a virtual cell model should take all of it, right? and also combinations thereof, of course. And maybe you know disease happening, time, whatever, right? That then impacts that.
</details>

### 类器官与多细胞系统建模

>> 这很好地引出了类器官的概念。你能谈谈类器官是什么吗？它如何与扰动空间的概念结合？除了这种环境背景之外，你还会对它做些什么？

<details><summary>Original English</summary>
>> That's a great connection to the the organoids idea. So, can you talk a little bit about Okay, so an organoid is is what? And And how does that connect to this concept of perturbation space? And what do you do to it in addition to it just this context?
</details>

>> 朋友，当我第一次了解这个概念时——我必须说明，我不是一个受过纯粹系统训练的生物学家，我通常是通过阅读或与同行朋友交谈来学习新概念的。

当我第一次看到人们能够从人体中取出细胞（比如癌细胞或其他细胞），并在体外培养成小型的多细胞系统，而且细胞之间真正开始建立连接时，我感到超级震撼。现在人们可以提取一些细胞放在培养皿中培养出微型大脑，本质上是一组真正开始相互连接、相互交流的神经元。研究人员已经证明可以让培养皿中的微型大脑进行计算。类似地，人们可以提取心脏细胞，将其培养成微型心脏类器官。我们在本地与优秀的合作伙伴开展了多项合作，这些组织甚至真的开始跳动。就像在培养皿中有一小团会跳动的心脏细胞，对吧？

一旦拥有了这些——我刚才提到了大脑，还有更简单的系统比如结肠类器官，效果也非常好，此外还有许多肿瘤类器官系统。这在研究难以获取样本的疾病时非常有用。比如你想研究某些神经退行性疾病的遗传机制，通常很难直接获取人体脑组织，对吧？于是你可以提取皮肤细胞或干细胞，将它们分化诱导成这些微型大脑，然后就能在上面开展研究。因此，我认为在培养皿中复制微型器官碎片（即类器官）的概念非常引人入胜。

当然它存在各种局限性：通常缺少免疫系统，也没有血管为其提供养分等。因此存在各种挑战，但它比起单一细胞类型的单纯细胞系要丰富得多。

<details><summary>Original English</summary>
>> Dude, when I when I first heard about learned about this concept, I should say, you know, I'm I'm an overtrained biologist, so I typically learn about things when I read a bit or when I talk to colleagues and and friends. And when I first saw that people are able to take a cell actually cells out of a body of a cancer cell or whatever, right? And let them then grow into small multicellular systems that actually cells start connecting to things. I was super super impressed. So, you know, people can now, for example, take some cells, put them a dish, and then grow little mini brains, essentially set of neurons that essentially really start connecting, talking to each other. And people have shown that they can get those sort of mini brains in a dish to compute. Similarly, people can take heart cells, grow them into little heart organoids. We have a bunch of local collaborations with fantastic partners that actually start beating. Like you have beating little heart cell clumps in a dish, right? And then of course, once you have these and you're the same thing is I spoke about brain, there's even simpler systems like the colon where this works very well. There's a whole bunch of cancer systems. But, you know, also for let's say if you want to study diseases with hard to acquire material. Let's say you want to look into the genetics of some type of of neurodegenerative diseases or so. Like typically it's very hard to get access to tissue, right? So, you take stem cells from the skin You take cells from the skin, differentiate and make turn them into these mini little brains, and then you can potentially study some some things there. So, I think this concept of replicating little bits of organs, it's what they call organoids, in a dish is very fascinating. There's all kinds of limitations, obviously. Often immune cell is immune system is missing. There's like no uh maybe feeding them or something like that. So, there's all kind of problems, right? But it's much much more than just a cell line which is like one cell type.
</details>

>> 转向建模方面，你们是如何对这些系统进行建模的？

<details><summary>Original English</summary>
>> Moving to the modeling side, how does how do you model that?
</details>

>> 这正处于研究的最前沿。我认为学界在最佳建模方式上尚未达成共识，特别是现在的数据量还没有达到人们理想的水平。RJ，如果我没理解错的话，你参与了大量的空间组学以及 H&E 病理学相关的研究，对吧？

在病理学领域有大量的样本可用，而现在我们越来越多地开始开展空间组学研究。因此，我们如何表征空间连接的数据集，并且将其拆解到类器官层面等等，人们目前还不像处理游离单细胞那样清晰明确。

为了把这个问题讲得更通俗一些，我认为：

如果我们观察游离细胞的空间及其聚类，人类创造了一个美妙的隐喻，称之为“细胞类型”。大自然本身并不在乎这种划分，这只是我们用来给事物分类的概念标签，但它有助于我们理解这种复杂性。

但对于细胞的局部微环境微生态（local niches），我们似乎还没有一个类似的隐喻。或许有一点，但在 H&E 染色病理图像中，每当我与病理学家交流并观察他们的工作时，往往都是高度定性的，可能还没达到那个量化层级。因此我认为我们需要建立一套分类语言。在计算上或许我们并不绝对需要这种语言，但从计算角度我们也需要思考如何处理它。目前我们基本上是将它们作为细胞的分布来进行处理。这是眼下的折中方案，但我认为未来可以更加精细，比如引入图结构（graphs）等形式。

<details><summary>Original English</summary>
>> So, that's I think at the research frontier. So, I don't think people have agreed on what the optimum way to model is, particularly also because there's not as much data as one wants. Jay, right? You're you're involved, if I understand correctly, in a whole bunch of spatial omic slash um also uh uh um sort of H&E sort of pathology type of um effort. So, so like pathology, there's like so much samples available, right? And now increasingly we sort of do a bit more spatial omics. So, I think how we even represent spatially connected data sets. And then you also have to break it down on an organoid level and so on. People are not as clear as as it is with dissociated cells. So, again, taking taking this a bit simpler, I think if we look at the space of dissociated cells and we look at these groups, we have this beautiful metaphor of what we humans call a cell type, which you know, nature doesn't care about. But this is just us putting categories on top of stuff. But it helps us understand this complexity. I don't think we have a similar metaphor for local niches of cells. Maybe a little bit, but also in H&E, right? Whenever I I I talk and see what pathologist do, it's often very qualitative and it's maybe not at that level yet. So, I think we need to develop a bit of a categorization language for us. Maybe computationally, maybe we don't need this so much, but computationally we also need to to sort of think a bit how we deal with this. At the moment we essentially deal with this as distributions of of of cells. So, this is sort of the solution at the moment, but I think it can be more much more subtle, like graphs or something like that.
</details>

### 归纳偏置与“苦涩的教训”

>> 一方面，你有“苦涩的教训”（Bitter Lesson）：当你去除归纳偏置后，就能够利用更大规模、适用于该问题的数据集，由于分布更宽等原因，最终能获得更准确的模型。

但另一方面，存在一种相反的趋势，或许可以称之为“反苦涩教训”或它的另一面：在数据匮乏的阶段，你必须引入大量的归纳偏置来获得足够的统计功效以做出良好推断。此外还有第二层含义，不久前 John Platt 在我们的节目中也提到过：模型有预测型模型和描述型模型之分。作为科学家，你真正想要的是一种能够进行简化提炼的描述型模型，让你能够说：“我已经测试了所有的苹果，引力在苹果上是这样起作用的；但我将其建模为一个简单的普适概念，从而知道它对行星同样适用。”

所以我想听听你的看法，有哪些正在显现的简化、洞见、数学模型或其他科学模型，能够帮助降低所有这些复杂性，从而让我们能够真正从这些超大规模数据集中获得有意义的科学理解？

<details><summary>Original English</summary>
>> So, on the one hand you have the bitter lesson and you know, sort of you you remove inductive bias and you end up being able to have a larger data set that's applicable to your problem and then that helps you to get more accurate models because your the distribution is wider and whatever. Um so that's like the one and then but then there's this like countervailing tendency which is like maybe you could call it the anti-bitter lesson or like the other the flip side of the bitter lesson where when you're in data poor regimes for one thing then you you have to induce introduce a lot of inductive bias to get enough statistical power to make good inferences. But there's also a second side of that which I think John Platt in our discussion with him not too long ago brought up was that you have these these like predictive and then descriptive models. And what you really want as a scientist is to get to a simplification a descriptive model where you can say, "Oh well, I've tested all the apples and the gravity works in such a way on apples." And then but I'm modeling this as a universal concept with simply so that we know that it works on plants as well. Right? And And so that I want to understand from you, what are the simplifications or you know, sort of maybe simplifications, maybe insights, maybe actual mathematical or otherwise scientific models that are becoming apparent that are going to help to reduce all the complexity so that we're able to actually make meaningful gain meaningful understanding from these really large data sets.
</details>

>> 是的，这是一个非常重要且深刻的观点。我认为它在某种程度上将该领域分成了持有两种不同答案的群体：我们究竟应该在模型中注入多少归纳偏置或先验知识，以提高模型的可解释性，同时可能使其在分布外泛化（OOD）时更具鲁棒性？还是说我们应该全盘依赖海量数据来使模型具备更强的表现力？

在深入哲学探讨之前，我想先明确一点：过去几十年的文献在非常多的数据集上已经明确表明，如果我们构建过强的先验归纳偏置，可能会牺牲预测能力，对吧？这是有代价的。比如，假设你是一名医生，或者作为可能患有癌症的患者，你可能最希望拥有一个具备最强预测能力的模型；而在制定治疗方案时，你或许愿意接受一个预测性稍弱但更容易理解的模型。但在预测本身上，我认为人们始终追求最优表现。

在我们这个扰动空间尺度的领域中，虽然细胞维度的规模很大，但扰动空间的规模（即我们能施加的干预）目前还不够大，我认为我们目前尚未完全进入极度数据丰富的状态。因此在现阶段，这种混合模型可能仍然是最佳选择。

但随着时间推移，大规模机器学习带来了一个残酷但真实的认知：在某个阶段，海量数据必然会击败模型中人为加入的人工概念。我常举的一个简单例子是 AlphaFold：第一代模型费尽心思将分子的旋转不变性直接构建到学习过程中；而在后来的版本中，仅通过更多数据，模型就自动学会了旋转对称性，并且表现得更为灵活。因为无论你强加什么样的物理约束，现实并不总是绝对刚性的，如果让模型自行学习，你反而能获得提升。

因此我认为未来被广泛使用的核心模型，绝大多数将是那些更具灵活性、高度基于数据的模型，然后你再在事后对其进行解释分析。

<details><summary>Original English</summary>
>> Yeah, that's that's a that that's a very important very I think kind of deep point which I think sort of breaks the field into maybe sort of a bit two different groups of people with answers, right? So how much do we need to put inductive biases, maybe priors into a model to maybe make it better explainable, right? But potentially also more robust in going out of distribution. Or how much are we going to just rely on bigger data to sort of have the model be more expressive and so on. And I think And there I I I I need to be very clear before we may go into the full philosophy. I think literature has really clearly shown over um I think now decades at least for of us all very many data sets that if we build an a priori inductive biases too strongly, that we might lose predictive power, right? So, it comes at a cost. So, and if you know, let's say you're a physician and you just want to or maybe even if you're a patient and you you you maybe you might have cancer or not, maybe you want to have the best model as a predictor. Maybe she getting treated, you want to have a model that is maybe a bit less good, but you understand it a bit more. But for the prediction, at least I think you you want to have the best. And this is I think I think not not entirely clear. And I think in our field with this perturbation space scale, the cell scale I think is big, but the perturbation space scale, like the stuff that we do to it not being as big, I don't think we're yet in the super data rich regime. So, I think in our case these hybrid models might be still the thing to go for, but more and more of course, and this is I think this I don't know if you can call it sad, but the honest learning from from big scale machine learning is that at some point data beats human-made additional concepts in these models. And I know at least one simple example I often put is AlphaFold, where you know, the first model sort of made this extraordinary effort to to make, you know, the molecules rotation invariant, they sort of built it into the learning process, and only in later versions, you know, sort of rotation symmetry was automatically found by the model just with more data and was a bit more flexible because whatever physical constraint you put in, it's not always as rigid, and then you sort of you gain something if you let the model learn from this.

So, I think in the future the bigger part at least of the sort of more used models will be those more flexible, very much database ones, where you then a posteriori put the interpretation on top.
</details>

### 虚拟细胞模型的演进与 Scaling Law

>> 这也引出了我的一个疑问。你最近合著了一篇关于当前一代虚拟细胞统计功效的论文，探讨了额外数据给当前虚拟细胞模型带来的收益提升。你指出目标函数或训练方法可能是问题所在，并不一定是数据中缺乏信息。你能展开谈谈这一点吗？为什么你认为数据中仍有大量未被发掘的信息？这将把我们引向何方？我们需要怎么做才能进一步突破？

<details><summary>Original English</summary>
>> This also brings up the the question for me. So, you actually I think recently wrote a or co-authored a paper on the statistical power that the current generation of virtual cells have in terms of the data that the the lift that you get from additional data in those current generation of virtual cell models. And I think you had said basically that the objective function or the training methodology is potentially the problem there and not necessarily that the information is not in the data. So, like what can you explain that a little bit and why you think that maybe there's plenty of untapped information in the information and then like what where does that get us and what what do we need to do to get further?
</details>

>> 是的，客观来说，早期我们只有一些非常小规模、能力相对有限的预测模型，首先学习潜在空间，然后在上面预测扰动。当超大规模的基础模型表征问世时，所有人都蜂拥而上，甚至可能有些过度追捧。随后自然就进入了所谓的“幻灭低谷期”。接着涌现出大量论文，指出甚至普通的线性模型在基准测试中都表现良好。实际上早年在我们的 scGen 论文中，我们做的一些基准测试就已经表明，想要大幅超越简单的线性基线绝非易事。

我认为这在当前的数据现状下确实具有一定事实基础。对于某些任务，比如预测 CRISPR 在细胞中的效果，或者预测细胞类型，通常逻辑回归就足够了，你可能并不需要最复杂花哨的模型。

但如果你想预测更复杂的生物学现象——例如在我们关于 Nicheformer（一种针对空间组学的基础模型）的论文中，我们引入了一项新任务：给定单细胞的基因表达或潜在空间状态，能否预测其邻近细胞的基因表达状态？因为细胞之间始终存在通信，它们相互交流会在彼此的细胞状态中留下印迹。这项任务难度大得多，面对这类复杂任务，你就需要更强大、非线性的模型，并且必须挖掘更细微的数据特征。

因此，能否挖掘出更多信息，很大程度上取决于你在下游提出的是什么问题。当然，在自监督学习阶段，我认为我们远未找到最佳的表征方式和学习策略。目前很多做法都是直接照搬自然语言处理中大语言模型那一套，掩码自动编码器（MAE）是常规手段，但损失函数的形式与表征形式仍在广泛争论中。由于生物学数据通常具有表格化特性，人们正在尝试各种表格基础模型。同时现在也有很多类似 JEPA 的方法，比如我们的一项工作中采用了对比学习。大家都在尝试不同的损失函数和表征方法。

我认为现在的审稿人（这也是我长期倡导的）开始更严格地审视你是否真正证明了 Scaling Law（缩放定律）。这是早期生物基础模型论文中所欠缺的，人们未能真正证明必须具备如此的模型复杂度才能实现扩展提升。但如果你能跨样本、跨场景真正展示出这种 Scaling 行为，人们就会真正信服这些模型。在这些模型中，使用的归纳偏置通常较少。

我认为我们很快就会迎来这个阶段，最近的几篇论文中已经可以看到这种趋势。例如在我们的对比学习论文（我们称之为 scConcept）中，就已经展示出相当强劲的 Scaling 行为。在论文中为了与 Geneformer 对比，我们测试了大约 3000 万个细胞的规模；而目前我们在 Hugging Face 上发布了一个覆盖 3.5 亿个细胞的模型，参数量达到约 1 亿，这对我们来说已经是一个相当大的规模了。我们已经观察到良好的 Scaling 行为开始涌现。

<details><summary>Original English</summary>
>> Yeah, I I I think it's fair to say that you know, early on we had some sort of very small sort of more limited prediction models of learning let's say latent spaces first and then also sort of perturbations on top. And then, you know, when like this really large-scale foundation model representations came out everyone was sort of buying into the hype and maybe potentially sort of bit bit over buying then, you know, obviously after this you know, comes what's it called the the sobering up value or something like that. And then there were a whole bunch of papers coming up where they were basically saying, you know, hey, maybe even more or less linear model were doing good job. And actually now I see gen paper early on we had already some of these benchmarks showing that it's not so not so super easy and simple task is just to improve on that.

Um I think I think there's a truth to it that the particular in the current data state for some things let's say you want to predict the effect of a crisper in a cell and you might not need the most fancy model. Whereas if you ask a bit or if you want to predict a cell type or something like that, you know, for that mostly logistic regression is fine. But if you want to predict something a bit more difficult, for example, in our niche former paper which is a foundation model for spatial omics, we showed we had a new task which we introduced where you say you have a you have the gene expression you have sort of the state in latent space of a single cell, can you predict the gene expression state of its neighboring cells? Because you know, they're always in communication or maybe the other way around. So, like they're always in communication, so because you know, they talk to each other you sort of see a remnant of that sort of cell state in this one. And then actually this is harder to do and if you sort of have these harder tasks you need the stronger more linear things and you particularly need to look for more subtle data. So, your question, can you sort of find out more sort of information which type of things I think very much depends on what you sort of ask at the end of it. Of course, like in the self-supervised learning phase, I think we're definitely not there yet with the best way how we represent how how we learn these things. There's a lot of copying of what happens in NLP type of LLMs, right? And like masked autoencoders are always the typical way to go, but the type of losses, the type of representations, I think people are still debating. Maybe because you know, this is sort of often kind of tabular data, so you can just like tabular foundation models and all sorts of being tried out. There's a lot of JEPA type of approaches now because it's like we have one thing where we use contrastive learning. So it's just people playing around with the losses, but also with the representations. And I think nowadays reviewers, and at least I've been advocating this for a long time, are really much more closer looking that you really properly show scaling laws. This was what has missed from the early papers of the foundation models, and so people haven't really shown that you need this complexity to actually sort of really scale up. But if you go really if you can really demonstrate at scale like across examples and and samples that you have this sort of scaling behavior, then I think you have this buying into these models. And for these, of course, there's not so much at least inductive biases used. And so I do think we're going to going to hit this regime actually quite soon, and we do see this also in a few papers. So for example, in our contrastive learning paper, we call it SE concept, we do show already quite quite quite strong scaling behavior. In the paper, we had something for going because we compared to Gene Former going to maybe 30 million cells, but on on Hugging Face now, we have a 350 million cell model with I think going up to maybe 100 million parameters, so really going to the big scale for us. And we do see nice scaling behavior already starting to emerge.
</details>

>> 明确一下，在 1 亿参数和 3 亿或 3.5 亿个细胞的规模下，你在哪些应用中看到了提升？是在类似 Nicheformer 那种“根据我的转录组预测我所处的微环境”的任务中吗？

<details><summary>Original English</summary>
>> Just to be clear, then at 100 million parameters and three you said I think 300 million cells or something like that, that you you get a lift in what kinds of applications? In these these sort of the niche former kinds of questions where you're saying, "What is my environment?" based on the my transcriptome?
</details>

>> 是的。当然，终极目标是希望能够更好地进行扰动预测，因为这是大众目前对虚拟细胞的共识理解，对吧？对此，我并不认为单纯的表征学习是解决问题的完整路径。请原谅我再次强调这个技术细节：通常你用这些基础模型学习状态空间，但关于系统在动作（扰动）下的演化行为，你需要引入更类似“世界模型”的方法。

“世界模型”如今是一个非常时髦的词汇，过去一年在各大机器学习顶级会议上随处可见。但本质上，转录组或其他组学空间中的扰动预测模型（如虚拟细胞）就是一种世界模型。它不仅是一个计算 $f(x)$ 的函数，而是一个接收状态 $x$ 和动作 $a$、预测下一个状态 $x'$ 的模型 $f(x, a)$。对于这种架构，需要不同的技术组合。

我们通常的做法是用 scConcept 等模型来学习表征，然后引入一个生成模型来沿动作方向进行前推演化。在此我们采用了流式匹配（flow matching）等方法。我们刚刚被 *Nature Methods* 接收的 CellFlow 论文中明确证明，这些方法在生成扰动效应方面表现出色，但高度依赖高质量的潜在空间。在基于 scConcept 针对 3.5 亿个细胞训练的潜在空间中，我们整合了 16 个不同物种的数据以探索相似性。这使得研究跨物种、跨组织的潜在空间成为可能，甚至可以探索一些以前无法研究的进化生物学问题。

<details><summary>Original English</summary>
>> Yeah, I mean you know, the the ultimate thing of course you want to do is you want to be doing this perturbation prediction better cuz that's sort of what people now at least understand by virtual cell, right? And for this, I would not claim that pure representation learning is the right way to go. Sorry for making the subtlety again, but I think typically you learn the state space with these foundation models, but then sort of the way how they behave under an action under perturbation, this is where you need this more world model like type of approaches. World model being the very hip term, I'm sure you had this already at some point in your podcast. So, it's been on all of them machine learning conferences in last year, but de facto a perturbation prediction model like a virtual cell is kind of a world model in terms of transcriptome or other type of omic space, right? So, it's it's not just a model that is sort of f of x, but f of x {comma} a, right? So, the state x plus the action, right? And then sort of predicting the next state x prime or something like that. And I think for this you might need other combinations. So, what we typically do we learn the representations with for example as a concept, but then we put a generative model for the push forward along the action. So, for this we use something like flow matching or something like that. And in our self flow paper, this is not just uh got accepted for nature methods. We actually really show that these approaches are much better generating the effect of of of a perturbation, but they're very much dependent on a good latent space. And you're on this SE concept latent space. In this case, for these 350 million cells, we actually went into multi-species. So, you have now like 16 different species where you can potentially look for similarities. Suddenly, here you can maybe ask some evolutionary questions that you couldn't before. Not that we can do this so well, it's not our core expertise, but you know, sort of you can start doing these fancy um sort of cross species cross tissue type of latent spaces.
</details>

### 基准测试与非线性模型的必要性

>> 我对这些模型的发展历史很感兴趣。在计算生物学社区中，线性模型曾在某次公开竞赛中击败复杂模型，给许多人泼了一盆冷水。在经典机器学习中，充分理解 baseline 至关重要，否则很容易做无用功或自我蒙蔽。你能讲讲那次竞赛的背景，以及为什么它促使我们调整了方向吗？

<details><summary>Original English</summary>
>> I'm kind of curious at the history of some of these different models. I think you just gave us a sort of a rapid version of them. The one of the things that like I think was like somewhat famous in the community was this thing about linear models being kind of a a big point. Can you explain specifically what was the like key point here? Cuz I think this is like one of those things in classic machine learning, make sure you always understand your baselines well, you know, otherwise you you spend a lot of time spinning your wheels and fool yourself. I think there was a specifically a famous open competition on with the through the Arkin's the two that was a sort of a class of like cold water on everyone's uh you know, faces. Can you maybe give a little bit of history about that and like why we thought this was exciting and then where why this had us pivoting a bit. Yeah.
</details>

>> “做好你的 baseline”，这听起来是理所当然的经验，对吧？但在一个争相追求“虚拟细胞”这一圣杯的领域中，大家有时在评估 baseline 时不够严谨，在数据集留出（holdout）等方面存在诸多此前未被完全注意到的细微问题，导致了这些现象的发生。

最早的观察之一出现在基础的细胞类型预测任务中。给你一个新的转录组，预测它来自哪种细胞类型，甚至来自哪个器官。事实证明，直到今天，一些接近顶尖水平的模型其实就是逻辑回归。对于这种基础分类任务，逻辑回归的效果并不差。例如 CellTypist 工具就表现优秀。我们在大约五六年前发表过一篇论文，题目非常直接，就叫《细胞类型预测不需要深度学习》（*Deep learning is not needed for cell type prediction*）。

在单个器官内部，这个结论是成立的。但如果进行跨器官预测，情况就会复杂得多，因为相同的细胞类型会出现在不同器官中，免疫细胞也会根据所在组织的不同而表现出细微变化。此时就需要更高级的方法了。我们在关于 scTab（一种表格基础模型）的论文中证明，这种非线性建模能力确实显著超越了基础 baseline。

至于 Brandon 刚才问到的扰动模型，早期的许多分析可以在 Seurat 等经典工具包中运行简单的线性模型。2019 年左右我们在 scGen 中开始在潜在空间中引入线性平移（即非线性编码后进行潜在位移），并始终与简单的线性位移进行对比基准测试。

随着领域变得复杂以及新数据集的涌现，大家提出的扰动问题越来越丰富。此前举办过多场竞赛，比如 MIT 组织的常规竞赛，以及我们在 NeurIPS 组织的单细胞预测竞赛（涵盖数据整合与扰动预测等任务），参与度都非常高。

其中最具代表性的是 ARC 竞赛，他们为了吸引关注，将其命名为“虚拟细胞挑战赛”（Virtual Cell Challenge），吸引了大量目光。但在设计稳健的评估指标上其实非常具有挑战性。

我们在由众多实验室参与构建的“Open Problems”联盟中的解决方案，是让研究人员提交各自设计的指标与补充评估，以覆盖此前可能被忽略的微妙细节。ARC 竞赛最初确立的一些指标并没有完全针对单细胞特性进行定制，导致模型可以通过指标漏洞进行取巧利用（metric exploitation）。

最终真正获胜并被官方认可的模型，本质上正是基于流式匹配（flow matching）构建的，沿用了类似 CellFlow 的思想。这证明了在这种复杂任务下，非线性建模是必不可少的。一旦排除了对评估指标漏洞的恶意利用，真正拔得头筹的模型确实充分利用了非线性能力。

现在我们清楚地看到，单纯的线性或可加性模型在更复杂的任务中已经不够用了。但在简单的细胞系基因敲除实验中，特别是表型效应非常微弱时，复杂的深度学习模型往往容易过拟合，这也是为什么线性基线始终是一个强有力的基准。我总是告诫我的学生们：我知道大家都想用最前沿的花哨深度学习模型，但请务必先跑通 baseline。在药物扰动预测中，甚至一个预测均值（mean baseline）的基线都很难被击败，因为生物学数据中包含着巨大的噪声。

<details><summary>Original English</summary>
>> It sounds such an like such an obvious learning, right? Do your baselines properly. But in a field that is rushing towards the gold pot of the virtual cell, people sometimes maybe were not as careful with the baselines and there's a whole bunch of subtleties with respect to holdout and so on that, you know, wasn't always fully observed and why some of these things happen.

So, one of the first observations there was in a thing as basic as cell type prediction, okay? So, nothing super fancy, okay? Basically, you you give me a new transcriptome, you tell me from which cell type it is, right? Maybe even from which organ or something like that. And it turns out that even nowadays, I think some close to state-of-the-art models are really just logistic regression, right? So, for such a simple categorization, you know, this is actually not not so bad. There's one thing called cell type is for example, which is doing a good job and I think we had a paper maybe 5 or 6 years ago where we had the title very plain, "Deep learning is not needed for cell type prediction." This is true if it's within an organ. If you sort of go cross organ, suddenly gets a bit more subtle because, you know, sort of cell types reoccur in different organs and immune cells are a little subtle change depending which tissue they are. Suddenly, you know, there you need to do a bit more and we like for us, we published on a paper called SC tab, like a tabular foundation model, predictive model type of thing. We actually showed that this nonlinearity was really adding beyond the the baseline. So, that was sort of for that class.

For the perturbation models, which then you were asking Brennan similarly like early on, many analyses particular perturbation could run with classical linear models in Suda pack. We had then our our SCGen that was like something around 2019 where we started introducing linear shifts but in the latent space, so sort of non-linear encoding and we always compared with subtle sort of simpler linear shifts. But then, the field getting complex and you know, sort of data sets popping up, people started asking more and more perturbation type of questions. There have been a whole bunch of these early on competition for like a regular one run for example by MIT. We've been running a regular NeurIPS competition on uh prediction problems in single cell data, sometimes for integration data, also for perturbation prediction. Um that was very well attended. The cherry in the on on on on the cake was most definitely that that that arc competition which called the thing not just perturbation prediction challenge, but virtual cell challenge. To sound a bit cooler, right? We picked up very well. And but of with metrics that are robust were maybe but maybe not not that easy. So far actually our solution in in this this this consortium where a lot of labs contributed called open problems was actually that people need to submit their own metrics and additions so in order to really maybe subtle things that you might not have thought before. Dark one is also fixed a bunch of metrics that weren't even so so single cell specific and they could be just just exploited. So actually I think the winning model that was then in the end actually sort of crowned as the actual winning model, but essentially is a flow matching best thing. So based on on this idea that you know people fought with this flow with this cell flow type of idea. I think shows you that some non-linear things are in this case needed. So that the actual real winners or if you sort of remove the the exploitation was actually something that is this is taking some some non-linearities and I think nowadays we do see that just linear or additive type of models are not cutting the the the cake for more complex things, but for I think even nowadays if you go in a simple if you cell lines and you have sort of gene knockouts then particularly when the effects are a bit subtle all these sort of more complex models are sometimes a bit overfitting and that's why a linear baseline is always very good. So I always tell my students, guys I know we we have guys I mean guys and girls. We always need to do I know you want to do the most fancy deep learning thing, but please please you know have the baseline and like say for drugs you know a baseline as simple as just predicting getting better at the mean. You know, like that's the like the hottest base. That's not even a linear model like better than the mean is sometimes not as hard if there are so much noise in the data and this stuff is super noisy.
</details>

>> 我想补充一点，Bo Wang 及其合作者刚在 *Nature* 上发表了一篇论文，阐述了在其中一些线性基线击败复杂模型的情况中，问题其实出在评估指标本身。这不仅是指标被取巧利用的问题，而是提出错误的问题必然导致错误的答案。

<details><summary>Original English</summary>
>> I just wanted to add one point that Bo Wang and some of his collaborators actually just had a nature paper on on how the metric was actually the problem in some of the those linear baselines beating some of the models as well. So it's clearly it's not only metric hacking, but also just that asking the wrong question leads to the wrong answer.
</details>

>> 指标的选择至关重要。未来我们甚至会让 AI Agent 去尝试算法构件的各种排列组合，我们目前确实在与一些 AutoML 实验室合作探索这一方向。或许我们人类研究者最大的价值，正是在于如何设计和构建这些评估指标。

<details><summary>Original English</summary>
>> Our choice of the metric and I I think that they could you can discuss it. At some point we're going to have agents sort of trying out all kind of combinations of whatever algorithmic thing you can come up with. In fact, we actually do have some collaborations with some of of those sort of auto ML type of labs try this out. So, maybe what is left sounds a bit too harsh, right? But like what maybe our biggest ideas go into is actually this metric formulation, RJ, right?
</details>

### 学术科研机制与欧洲创业生态

>> 我非常感兴趣的一点是学术科研的资助模式。德国的体制结构与美国截然不同。你的研究所是如何构建的？与美国的科研模式相比，它带来了哪些独特的机会？

<details><summary>Original English</summary>
>> So, one thing I've been really interested in is the different models of funding in research academia. I think Germany has a different structure fundamentally from the US. How is your institution set up and like how does this give like distinct opportunities versus like a US-based research model?
</details>

>> 我非常赞同，资助模式对科研灵活性、团队组建以及长期愿景的设定起着决定性作用。

亥姆霍兹联合会是德国乃至欧洲科研经费规模最大的科研机构之一，业务涵盖健康、材料、信息科学和物理等重点领域。它由联邦资金全额支持，专注于攻克重大前沿科研难题。

我在慕尼黑亥姆霍兹中心建立了计算健康中心（Computational Health Center），目前拥有约 45 位课题组长和教授，团队规模达 500 到 600 人。这是欧洲规模最大的医疗人工智能学术研究基地，研究覆盖各个尺度。我本人专注于细胞层面，但中心也有学者在做 DNA 基础模型、蛋白质设计、患者队列临床表征和遗传学等。我们正将这些不同维度的研究拼接整合，宏伟愿景之一就是构建“虚拟人类”。

与传统大学不同的是，尽管我们与慕尼黑工业大学和慕尼黑大学（两所欧盟顶尖高校）均有双聘任职，但我们不承担本科教学任务，主要由博士生和博士后组成。我们与大学尤其是附属医院深度互动，以确保强有力的临床转化通道。它有点类似于美国的 NIH 模式，但并非集中在单一园区，而是分布在全德各地。

德国政府现在越来越意识到，必须建立更强的成果转化机制，不仅是向大学转化，更要面向学术界之外创造商业价值，走向初创企业。波士顿地区一直是这方面的典型代表，而湾区如今也高度活跃。最近我访问 Genentech 期间在餐厅用餐，服务员甚至主动问我们：“你们在聊 AI 和生物学吗？我也很感兴趣。”这种全民关注创业的氛围非常好。我们的博士生现在也越来越多地走上创业道路。在风险投资和硬科技（尤其是生物医药与国防科技）领域，慕尼黑目前已成为欧洲大陆最具吸引力的核心枢纽，产业生态正在迅速起步。

<details><summary>Original English</summary>
>> I I very much agree that these funding models very much matter for the flexibility, but also the set of teams that you can set up and like the long-term vision that you can have. So, um Helmholtz, this is not just Germany, but I would say maybe Europe's largest what's called research organization in terms of funding. It has different set of areas that it focuses on. Health being one of the big ones, but then it has sort of material, information sciences, physics, and so on. And it's essentially getting fed federal money to put into a deep research question. I've been building up what's called the computational health center at Helmholtz Munich, which I think we has now something like maybe 45 group leaders and professors and maybe 500 to 600 people now. So, we are I think the largest academic place for health AI type of research in Europe where we have people really working on all scales. Like, you know, I'm sort of focusing on the cellular scale, but you know, there's people doing DNA foundation models. There's people sort of doing interesting things on protein design. There's people doing like, you know, patient cohort type of representation, genetics, and so on. And now you sort of can start putting them together, and one of our big visions is sort of to to intersect and sort of go virtual human, and so on. But having said that, the key thing is in contrast to universities that even though we all have affiliation to universities, mostly to the Technical University or the University of Munich, the two top-ranked universities interestingly in the European Union. So, we have this sort of place where we have these affiliations at universities, right? But, we don't have undergraduate teaching. We essentially just have PhD students and postdocs, but we interact very much with the universities and in particular also the clinics because we want to have sort of this translational thing in there.

And increasingly, that's maybe an interesting link to So, this is maybe a bit similar to NIH type of models like in US, but sort of distributed all over the country, not just sort of in one place. And maybe the one interesting um um um link is that increasingly the government and this sort of realization also in in in Germany is is sort of dawning that there needs to be much stronger transfer component, not just by going into translation to universities, but also in into sort of value creation outside of the academic realm, which is obviously going so more more into startups and so on, which I think the Boston environment has always been one of the key examples, but now of course more so now also the the the Bay Area when, you know, recently I was was visiting uh I believe maybe Genentech or colleagues, and we went to a restaurant, and then one of the waiters was asking us, "Hey, are you guys talking about AI and bio? You know, I have been also interested." So, like everyone sort of thinking about this startup ideas and so on. And I I kind of felt that's a it's a good environment, and this is something I think our PhDs are now more and more doing, and and we we are sort of learning there, and I think also in terms of sort of value creation, Munich in particular is actually at least in continental or maybe the prime place now for VC capital, but also sort of deep tech and particularly the bio and and defense area and sort of really exploding. So, this stuff starts to work.
</details>

>> 谈到创业公司，我听说德国在初创企业生态方面面临一些挑战，与欧洲其他地区相比在德国创立初创企业存在一定困难。目前德国初创企业的竞争格局如何？德国如何在更广泛的层面上提升竞争力？我对这个问题有切身利益，因为我可能很快就要获得德国国籍了。

<details><summary>Original English</summary>
>> One thing one thing we're talking about startup, I think is really fascinating. I've heard that Germany has had some issues with their startup ecosystem. It's it's try It's difficult to create a startup there compared to in other places in Europe. How like what is the competitive landscape for startups right now in Germany, and specific and how does Germany become more competitive broadly? Um I I have [clears throat] a vested interest in this because I'm um probably going to get my German citizenship soon.
</details>

>> 欢迎你！来慕尼黑时请务必联系我。

传统上，欧洲特别是德国的官僚流程确实较为繁琐，数字化程度不及预期。虽然美国的数字化流程也并非完美无瑕，但做事节奏确实更快。

然而大家现在已经意识到了这一点。在初创企业的创建与早期落地方面，德国在欧洲极具竞争力，慕尼黑更是创业密度最高的中心之一。目前在欧盟范围内新成立的初创企业数量甚至已经可以与美国平分秋色。

欧洲和德国真正落后的地方在于后期的业务规模化扩展（scaling）。早期风险投资以及非稀释性政府资助在本地相当充裕，但在需要大规模扩张、要求风投承担更高风险的 Series A、Series B 及更大规模融资轮次时，欧洲的资本规模远无法相提并论。我屡屡看到，许多企业为了募集大额资金，最终还是不得不转向美国市场。

<details><summary>Original English</summary>
>> Welcome. Let me know if you come come by Munich. So, um I think traditionally Europe but I would say definitely Germany is is quite bureaucratic and processes are far from as digital as you would expect them in different places. Not that I'm saying that the US is maybe the best example for fully digitized processes, but stuff is definitely faster. The thing is people have realized that now and I think the the particular startup creation and implementation is I think more than competitive in Germany versus Europe. It's actually sort of the the the the prime number and in particular like some hotspots burning, but in particular Munich sort of the I think is is the capital for for um um highest number of startups and I think even nowadays if you look into European Union, there's equally as many startups being created as in US. The thing is where Europe and particular also Germany drops off is at the scaling part. So, you know, early VC and also sort of um non-diluted type of money, this is there. But then when you go into scaling, these big VCs that sort of take these bigger risks are I I think not not closely as present. So, I have I have I saw I saw this again and again that, you know, if you want to sort of really go into the um the sort of bigger tickets sort of series A and so on series B, that you people start going more into US also for that. But maybe I'm over simplifying here, but this is at least my current learning burner.
</details>

>> 你在多家本地初创企业担任董事或顾问。在德国，从一个想法走向真正成立一家初创企业，需要经历什么？

<details><summary>Original English</summary>
>> Okay, you are on the board or I guess part of several local startups, right? What what does it take to go from, you know, idea to creating a you know, to creating a new startup in Germany?
</details>

>> 欧盟试图在各个层面推进监管，这有时具有积极作用，比如统一使用 USB-C 接口等举措极大地方便了生活。但另一方面，诸如《人工智能法案》（AI Act）等规范也让许多事务的推进变得更加繁琐复杂。所幸目前对基础科学研究的影响尚不严重，但跨医院的数据流动仍面临诸多限制。

在医疗深度科技领域，欧洲拥有极具优势的基础设施，比如芬兰的 FinnGen 以及丹麦的全民健康队列，在人群样本采集和医疗记录互联方面表现极其出色。相比之下，美国和德国在跨州或跨地区病历打通方面都面临类似的数据壁垒问题。欧盟目前正在推行“欧洲健康数据空间”（European Health Data Space），计划在未来几年内打破边界壁垒，实现跨国医疗数据的互联互通。这一愿景非常宏大，只是落实节奏相对较慢。

对于科技初创企业而言，我认为核心始终是组建顶尖的团队。我们课题组长和教授们正积极推动这一方向。例如，在我们协调的部门中，我曾向每位课题组长提出期望：“我希望每位 PI 在未来三年内至少孵化一家衍生初创公司，看看效果如何。”但如今更强大的驱动力来自于自下而上的学生群体，年轻学子们深刻意识到当前的时代机遇，特别是在计算科学正走向最前沿的当下。

借助计算模型，我们现在能够真正开始指导实验进程。一旦拥有了这些扰动世界模型，我们就能反向驱动湿实验设计。因此，计算驱动的初创企业在数据生成层面大有可为。未来的初创企业不仅停留在发表优质学术论文，更将把“在环实验室”（lab-in-the-loop）模式真正落地推向产业化。

<details><summary>Original English</summary>
>> I I don't know if if if you heard that the European Union tries to regulate a whole bunch of stuff. And that can be sometimes an advantage. You know, it's kind of cool like, you know, all across Europe we can now go with a mobile phone. And you might have heard that everyone needs to have USB-C things now for their mobile phones. This is kind of kind of cool stuff. So, there's some some good stuff coming. But then of course there's something like things like the AI Act and so on that make things a tad more complicated. Luckily not yet for research, but you know, for data access across hospitals and so on, there's some and you know, and maybe we're talking about about health deep tech type of stuff, right? So, there's some um systems that I think fantastic in Europe. And I'm thinking about Finland, you know, FinnGen um Denmark and so on with this sort of very detailed description of the population terms of sampling, getting medical records connected far better than I mean US is also similar to a mess like like Germany in terms of sort of getting all the systems sort of to talk to each other. Like when patients, you know, sort of go to to different states in US is similar as in Germany when they go to different places. It's like very hard to build patient directories, right? But there are some places that know how to do this and there's a thing like the European Union tells you it's called the European health data space where in like maybe next 2 years these things need to be sort of going across boundaries. You need to sort of start building these these health record type of combination.

So I do think the visions are starting to happen, but the scale is is not as fast. So I think what you need for a tech startup what I noticed is is always the biggest thing is you need to have the best team for that. And you know, we have professors and and PIs that really think about this. So for example, for for the department that I coordinated, I said, "Guys, every every PI every group leader, I would expect you to at least to have one one one spin-off in in in the next 3 years." And see how that works, right? But you sort of see this sort of get people a a bit a bit on that track. But I think this is happening very much from the bottom up nowadays anyway where the students are actually pushing for that. They do realize that there's a whole bunch of opportunities at the moment, particularly with with this sort of computational angle getting Yeah, I would say pushed even more in the forefront that we can now start actually guiding experiments. We haven't really spoken so much about, right? But once you have these perturbation world models, you can actually go back and drive the experiments, right? So I do think computational startups can be very good also data generation. And I think this is what will be also turned not just into nice papers, which is sort of mostly our business, but also I think it is next generation of startups. And you do see a few of these popping up where you actually get the lab in the loop really implemented.
</details>

### 虚拟细胞的商业化与平台型企业转型

>> 在这些与虚拟细胞相关的领域中，你认为最具商业化前景的切入点是什么？

<details><summary>Original English</summary>
>> What do you see as some of the the the most promising areas for commercialization of sort of these virtual cell adjacent ideas?
</details>

>> 这很有意思。回顾早期 OpenAI 等公司的发展轨迹，人们往往会联想到他们早期并不清楚具体如何盈利。有几家获得了巨额投资的初创公司宣称“我们要构建生物学的基础模型”、“我们要破译生物学密码”，但并没有明确说明最终的商业变现路径。

这种平台型的商业构想非常具有吸引力，也契合我们构建开源工具和平台（如 Scanpy 和 scverse）的经验。但要将平台直接转化为成熟的商业模式并非易事。除了技术咨询类业务外，如果你说自己在打造一个虚拟细胞平台，在欧美相对保守的风投生态中，投资人最容易理解的逻辑依然是：你最终能否自主研发出新药？

因此我目睹了大量的平台型公司在中途转型（pivot）去自主开发管线药物：他们会强调在推进虚拟细胞技术的同时，自身已经筛选出了两个候选药物资产，并在此投入重金。虽然仍有少数公司坚守纯粹的 AI 扩展路线，但直接构建规模化、可持续的纯软件商业模式仍然充满挑战，市场空间也相对有限，许多人还会担忧大型科技公司未来可能会直接覆盖这部分能力。

<details><summary>Original English</summary>
>> It's interesting, right? Like if if you look at earlier and of course this is what people always reflect to what OpenAI and so forth and so on wanted to do. Like they didn't really know how to make money and some people might argue they don't even know nowadays, right? And there's a few startups that you know, got really quite strong investment that also said we build a foundation model of biology. We decode biology and so on, without actually saying what you want to do with it. And I've been seeing this again and again that these platform type of ideas are super attractive. You know, they sort of fit into what we know. I mean, you spoke about some of the tools and platforms that we built like Scanpy and scverse and so on, right? But turning this actually into a monetary thing is not as obvious. I mean, there might be some sort of consulting business, but if you say you build a virtual cell platform, typically what investors understand, and this is maybe even more so in the more conservative VC ecosystem in Europe US is that at some point you develop a drug and then you have this clear thing. So, I saw so many of these platform companies pivoting at some point to we make a drug. And yeah, at the side, of course, we have our our sort of virtual cell, whatever business, but you know, we have two drugs that we found and now this So, we put a lot of money in.

Um Maybe you have some other counter examples. And there's a few companies that are sort of still stick with the scaling up of of the AI business, but it's not as clear uh how you would sort of directly turn this into a viable sort of really scalable business model. And there's even room for many of these. Of course, then there's also this angst that at some point like Astra 2.0 might be doing parts of this already anyway, yeah.
</details>

>> 我此前一直持有一个观点：直到最近，几乎所有构建生物模型或平台的公司，最终都会转型去做创新药研发，因为那是长久以来经过验证的变现通路。作为一家工具公司，向大药企销售软件服务难度极高，而向投资人展示“我们正在打造一款药物资产并寻求未来授权转让”则极具吸引力。

但今年我们看到了一些反向的趋势：在结构生物学领域出现了一些新公司，我们采访过的几家公司开始探索强化学习环境的商业模式。我非常希望看到结构生物学领域的这种高活跃度，也能出现在类似 Noetik 正在开展的业务中。

<details><summary>Original English</summary>
>> Yeah, I mean, I I think that it's actually this has been a thesis of mine that up until recently every single company that builds a model and builds a something ends up just building drugs because that's the path to monetization over time, right? And then like whereas you you have to like land sales with pharma that's very difficult or some other big big pocket spender. If you're a tools company, if you say I'm going to build a port like a an asset and then I can sell that off, that's really attractive to an investor. But but we've seen actually the opposite happening this year, right? So, you have like you have in structural, you have a couple, you have bolts, you have Brandon will know them better, but there's a couple of those and then Ty is one that we talked to. And then we've interviewed a few that are doing this do doing reinforcement learning environment plays as well. I would love to see the activity level in structure that that we see in structural also doing things like what No it is doing.
</details>

>> Noetik 是一个极佳的范例，他们的优势在于拥有相当规模的数据生成能力以及独特的数据获取壁垒。这就像我们此前讨论类器官扰动时提到的，我们与众多药企联合发起了一个名为“癌症类器官扰动图谱”（Cancer Organoid Perturbation Atlas）的联盟，药企愿意为此出资买单，正是为了能尽早获取这些稀缺的扰动数据集。如果能将专有数据生成与先进建模深度结合，才是击中商业核心的最佳结合点，也能获得药企的实质支持。越来越多的初创企业正在将自身的护城河建立在虚拟细胞模型与独特专有数据的紧密结合之上，从而创造更大的产业价值。

<details><summary>Original English</summary>
>> I mean I I I think No it is is is a good example in the sense that they also have I think a rather nice scale of data generation and a big part of that is also access to data. So you know we talked before about these organoid perturbation type of things and we've been setting up actually in collaboration with a whole bunch of farmer a consortium which we call the cancer organoid perturbation atlas with then farmer actually buys in because they want to get early access to some of these sort of perturbation type of data sets right and I think some of these deals sort of go in these these these directions. So I think if you couple it with data generation not just with the modeling part, I think this is where sweet spot hits where then also actually farmer gets buying. I think more more of the companies I see they sort of build their mode not just around a virtual cell model but in combination with sort of unique sort of specific data. This is then of course also more value creation.
</details>

### Y 型跨学科培养模式

>> 我读到过相关报道，你在指导学生时推行所谓的“Y 型模型”（Y model），要求学生必须同时配备一位计算方法导师和一位湿实验导师。在当前数据生成与湿实验成为诸多企业核心护城河的背景下，这个理念非常切合实际。你能深入介绍一下这个模式吗？

<details><summary>Original English</summary>
>> I don't know if this is exactly correct but I read that you said somewhere that you have your students follow what what you I think called a Y model in which you have to have a methods and a wet lab advisor. That sounds super interesting, super relevant to the conversation we're having right now about data being so important and all the attention on lab work and that being mode for a lot of companies. Can you talk a little bit about that?
</details>

>> 感谢你提到这一点。这是我们在慕尼黑数据科学学院（Munich School for Data Science）中建立的导师模式。这项计划跨越了单纯的生物学，涵盖了多个交叉学科。在该模式下，必须由两名来自不同领域的 PI 共同提出研究课题，并向研究生项目招募学生。这就是所谓的 Y 型架构：分叉的一侧偏向计算与算法方法，另一侧偏向具体实验领域，交汇处是学生；有时由两名学生共同构成联合课题，Y 加 Y 就变成了 H 型架构。

这种设计如今看起来或许并不复杂，但将其作为刚性机制固定下来至关重要。学生需要参加两个完全不同的实验室组会（lab meetings）：在一个组会中，他们需要深入学习并理解复杂的生物医学问题和临床语境；而在另一个计算组会中，他们与纯计算和数据科学背景的学者探讨前沿算法。

通过这种方式，学生能够将在生物实验室中未能完全形式化表述的现实问题提炼出来，运用自身的量化分析能力将其转化为具体的数学评估指标、构建模型并最终发表高质量学术成果。

我们推行这套机制已有大约八年时间，诞生了大量高水平论文。在这个过程中，我也了解到了许多此前从未涉足的领域，比如肺部或脑部生物学问题。当同行带来有趣的数据时，我们发现现有模型架构正好契合，于是顺理成章地立项研究。这些学生在与实验伙伴深度合作的过程中，逐渐成长为该细分交叉领域的权威专家。如今这种跨学科探索已经从早期的单细胞 RNA 测序，拓展到了我们去年发表在 *Science* 上的单细胞蛋白质组学以及空间组学等多个全新维度。

<details><summary>Original English</summary>
>> Yeah I think thanks for raising this. So I've been setting up and since then this has been sort of become quite a big thing what's called the Munich School for Data Science right? So this is beyond just just bio so we had a whole bunch of other disciplines and there we had this supervisor model that is always two PIs needed come together to make a proposal and sort of proposes to the students in a graduate student type of model which has this this Y so there's like a method e more domain one right and then there's supervisor student. And sometimes we had two students under the Y model so Y plus Y equals H. You get it?

But but I I think this idea is it's somewhat even nowadays a bit trivial right? But I I thought it was good to bake this in so hard so that students really ideally go to two lab meetings. One lab meeting where they need to really learn and understand some deeper biological problem, understand the language maybe of a medical setup or something like that. Then they go to a computation typically all computation data science type of students, right? But then they go to the computation one they sort of get pushed the method aspect of it and thereby sucking up a whole bunch of of problems that are sort of not exactly precisely as formulated in in that bio lab. They sort of can't directly put that in a function, but then because they are sort of methody, right? And they're quantitative, they can actually put this into a metric or whatever that then turns into a model and then paper and I I think this is the way how uh I mean we've been doing this now for maybe 8 years or so this this type of school. I really a whole bunch of papers came out where I I I learned about systems that I had no idea about this before, right? You know, people approaching me and could we do something like this and then you know, I learned something about the lung or the brain that you know, I had no idea about, but then uh I said, "Oh hey, cool data. I think our model types could fit. Let's build a project around it." And then those students became the experts in my lab for that sort of detailed biological thing together with a partner. And then maybe we drive this forward and this actually nowadays extends also across the data types. Earlier on a lot of things have been around just RNA, but you know, since then you know, we had a very nice paper in science last year on single cell proteomics. We've been extending things to spatial observations. You know, there's sort of all these additionalities and things that you can can can measure and I think then interesting questions come up in that particular domain where you know, these essays work very well.
</details>

>> 我非常认同这种跨学科整合的思路，跨领域的交融往往是诞生顶尖创意的温床。经过八年的实践，你观察到了哪些长期的积极成效？

<details><summary>Original English</summary>
>> Yeah, I mean this is my natural inclination is to like gathering cross-domain stuff. It I think it's all often ripe for good good generation of really good and interesting ideas. Have you just as a follow-up these you've been doing this eight years now, I guess. So what kinds of you know, sort of longer term outcome benefits have you seen from this?
</details>

>> 这种模式之所以能吸引优秀学生加入，在于它为学生提供了多元的探索空间。在德国和欧洲其他国家，学生进入博士阶段前通常已经完成了硕士学业，对科学研究已有一定认识，但往往还不完全明确自己的具体兴趣点所在。在研究生院的这一框架下，他们既能接触到不同的生物学领域，又能自由探索算法前沿。

这种双重训练使学生兼具出色的数据分析能力和坚实的原生建模能力。他们毕业后的去向也非常多元：有人进入了大型药企的生物医药研发部门，有人留在学术界深造，有人创立了初创企业，还有人投身于纯粹的 AI 研究。比如几个月前，英伟达在短短一个月内就录用了我们实验室的两位成员，深度参与其当前正在大力布局的生物计算业务。其他头部科技企业也有类似举措。当他们在市场上应聘面试时，他们展现出的不仅是在 NeurIPS 论文中将指标提升 2% 的建模技巧，更重要的是他们具备面向复杂、深刻的真实应用场景解决落地问题的综合素养。

<details><summary>Original English</summary>
>> I think one thing that this is also I think how we got students to even join in this maybe initially it sounds like more work, right? You kind of need to learn two things and you go to two lab meetings and so on. But I think you once your students are done in in in in in Germany or I think in general but particularly I think in Europe in general people sort of typically do a master's first before they go into a PhD, right? So not just a bachelor's in the US, right? So, you do like one or two year more of master. And and then they sort of know science a little bit, but they don't exactly know what sort of interests them. So, in this combination type of thing, you know, they can sort of sample a bit because in this grad school they just get different proposals in, so they can sample a bit what they're interested in in terms of domain, but then they can also play around a bit with the method side. So, I think that was kind of attractive. Yeah, I I think with this sort of trying out uh different things, I had the impression that this sort of turned the students into very good data analysts, but then also modeling people. And then a downstream, you know, the sort of areas where they they went into was also equally diverse, you know, so some people went like and now they're in the biomedical domain into pharma, but you know, some obviously stayed in research, some went more into some sort of startup direction, some went into the very pure AI type type of work.

I think Nvidia just a few months ago were hired in 1 month two of my people going very much into sort of the computation aspect and also a bit of a bio part that Nvidia's now building up and there's similar other of the big companies. So, I think it it gives them an an an interesting profile, but I think when you're out there when you get interviewed, you know, it's it's a good idea to say, you know, I I didn't only do like this fancy model that improved maybe 2% in a NeurIPS paper type of thing, but you also sort of had the real sort of more complex, deeper application that they're like, you know, I had to help find as a use case.
</details>

### 人工智能工具与闭环研发体系

>> 在 Atomwise 等机构中，我们看到不少实验科学家借助 AI 工具逐渐转型具备了计算能力。随着 AI 赋能每位科学家自行开展计算分析，你认为这种双导师合作机制以及湿实验与计算团队的融合模式将如何演进？许多知名 CEO 常常把“计算团队与湿实验团队的高度整合”作为核心壁垒，你认为未来应如何构建相应的团队文化来驾驭这些新技术？

<details><summary>Original English</summary>
>> There's been a movement amongst Atomwise AI like several guests we've had or we've had a blog post about how the wet lab scientists have started basically becoming computational thanks to Atomwise AI. I don't know if this is I'm kind of curious like as this evolves, as basically now Atomwise AI enables any scientist to be now become their own computational, what do you think the evolution of this sort of like co-advising strategy is and also what do you think the evolution of like integration between wet lab biologist and computational teams are? I mean, I also can think of like I've heard several you know, famous CEOs say things like our strength is integration between computational and wet lab teams. So, I'm I'm curious to see how you think that evolves and how you also like set up culture to exploit, you you these new technologies.
</details>

>> 文化层面的建设是一个非常深刻且复杂的议题。首先我想谈谈关于深度融合所带来的前沿机遇：

我们当前迎来的最令人兴奋的机遇，是真正开始通过算法指导实验。在以往构建人类细胞图谱时，我们做的是类似制图测绘的工作；接着我们探讨了世界模型的预测能力；而现在，我们迈向了真正主导并驱动下一步实验的阶段。

科学方法的核心本就是提出假说并进行闭环验证，但坦白讲，过去的很多论文仅仅止步于建立模型或绘制概念图，完成初步验证后便转向下一个课题。虽然在这个过程中有所收获，但未能形成持续学习的飞轮效应。

如今，将实验结果反哺模型的闭环机制正在快速铺开，特别是在分子设计和材料设计领域，“在环实验室”（lab-in-the-loop）正在被深入实践。然而，尽管大型药企都将其列为核心战略，但在行业内真正实现多轮“实验-建模-实验”迭代闭环的成功范例仍然屈指可数。

搭建这种闭环极具挑战：首先在建模层面，在拥有前向模型之后，如何科学决策出“最优的下一步实验问题”本身就是一个非平凡的数学与运筹难题。我们在 BioRxiv 上刚刚发布了名为 Lab Compass 的新工具，它是一个逆向生成模型，在具备前向世界模型的基础上，能够直接反推为了达到预期的细胞状态需要执行何种实验扰动。

这项成果的关键不仅在于算法本身，更在于与剑桥大学造血系统研究团队的紧密合作。借助其快速周期实验系统，我们完整跑通了三到四轮闭环迭代，逐步优化改进了模型。

这正好切中了 Brandon 的第二个问题：如何建立一种协作文化，让湿实验科学家愿意投入宝贵的时间与精力，去验证计算模型或算法预测给出的全新实验方案？这些生物学实验周期漫长，要说服他们信任算法去测试那些看似反直觉的全新细胞处理条件，并非易事。在分子设计中试错成本相对较低，而在复杂的细胞实验中，人们往往更倾向于依赖直觉经验。因此，建立这种信任与融合文化绝非朝夕之功，甚至需要具备跨界能力的同一个人来统筹推进。

有些人会联想到全面引入自动化机器人实验室，但我认为现阶段仍为时尚早，因为目前的生物检测分析周期依然较长。但这一趋势必将到来，最终的愿景是将强化学习（RL）贯穿于整个闭环，将物理实验室本身转变为强化学习环境的一部分。虽然这听起来带有科幻色彩，但我们正在稳步接近，现阶段它更偏向于主动学习（Active Learning）的形式。

<details><summary>Original English</summary>
>> Let let me maybe sort of keep the the culture part a bit out because I think it's a hard one to answer, but a very good one. So, let me first sort of talk about the I think very cool cool point that I think you asked about where where these things happen sort of goes with deep integration. I think one of the most exciting frontiers we currently face and I think maybe have as an opportunity is we can really now start guiding the experimentation. So, where before you we build these human cell atlases, we had sort of this mapping aspect. Then we talked about the world model prediction problem, right? So, from mapping we went to prediction. But now we can go to actually steering the next experiment, right? And this has always been the scientific method, you know, sort of putting our hypothesis in the loop and then doing something with it, but quite frankly, very often the papers ended with some model, right? maybe some sort of concept figure, maybe had a little bit validation. But then to be you start the next project, right? And of course you learn a bit, but there's not like not like a continual learning type of thing. But now, you know, I think we can actually really loop back more and more. This is happening very much so in uh molecule design or material design and so on. You sort of the lab in the loop is being worked on out.

And even though some big pharma have been putting this out as sort of a general general big theme, there's not many examples that where really people do multiple [clears throat] loops of this integration of you know, experiment, a computation model, then going back, whether this is now two person one, right? But like this integration is hard to set up. And it's hard to set up once because of modeling because actually sort of once you have a model, actually deciding what's an optimal next question is not trivial. And we actually brought out I think it should be on on bio archive today or tomorrow and new thing we which we call lab compass, which is an inverse generative model that actually allows you once you have a forward world model or whatever to tell you what you need to do in order to reach a certain state. So, it's super exciting for us, right? And I think a big part of the work was not just the model, but actually the work with experimental people, in this case a good friend and colleague from University of Cambridge who was doing hematopoiesis. In addition, had a sort of a rapid cycle system where we actually set up three four lab in the loops where we iteratively improved on a model. And this is I think a really hard thing. And this sort of goes into your second question, Brandon, right? Like how do you bring a culture where once your computational person or model or whatever predicts something that you actually get to convince experimental people to put their life time in because these experiments often take some time right to actually buy into it and actually measure some of these follow ups. And sometimes you know this works a bit better if it's sort of molecules because then you know also the stakes are not as high but you know if you like say now you need to do this new cell and you need to add these very strange things. Do you really want to do this? Like shouldn't we maybe not take a bit of our gut feeling and then you know these sort of disintermediate solutions come. So I think really setting this up is far from trivial. That needs culture and it might be the same person doing it. A lot of people then start throwing around robotics and so on as well but I I think this is a tad too early because the the cycle times in terms of our essays are still a bit on the long side but I do think this will come and you know obviously the the ultimate vision being that we want to RL everything. We want to do RL also in in in in this loop. It's a bit out there but you know I think we're we're slowly getting there. At the moment it's more maybe active learning.
</details>

>> 这与我们此前和 Lila 交流时的核心观点高度契合——他们认为实体实验室本身就是强化学习环境的一部分。Fabian，慕尼黑现在已经深夜了，非常感谢你在百忙之中抽出时间与我们长谈。我们非常期待继续关注你本人、你的实验室及同行未来的研究进展。

<details><summary>Original English</summary>
>> I think that very much like we talked to Lila there that is there they're kind of their core thesis is is is is that basically the lab is part of the RL environment. Kind of is what I mean. Yeah, no that's great. Fabian, it is late at night for you now. I'm I really appreciate you taking the time out of your evening to to talk to us. Look forward to to watching your research and when I say you I mean your lab and colleagues and you as well. I'm I really look forward to watching this progress and keeping careful track of the things that we talked about today.
</details>

>> 非常感谢 RJ 和 Brandon 的邀请。这类跨学科的学术交流至关重要，它能让我们跳出各自细分领域的局限。这次讨论让我受益匪浅，非常尽兴，十分感谢。

<details><summary>Original English</summary>
>> Yeah, thank thanks so much RJ Brendan for having me. I I think these links are important. This sort of looking beyond what maybe you do like in your own sort of smaller disciplines and you know these discussions helped me a lot. I really enjoyed the discussion. Had a lot of fun. Thanks.
</details>

>> 太棒了，谢谢，保重！

<details><summary>Original English</summary>
>> Great. Thanks. Take care. Thank you.
</details>