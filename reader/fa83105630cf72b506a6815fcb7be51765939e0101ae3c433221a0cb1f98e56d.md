---
author: Latent Space
date: '2026-10-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=NufiHZfMwaw
speaker: Latent Space
tags:
  - protein-folding
  - scaling-law
  - structural-biology
  - inductive-bias
  - translational-medicine
title: AlphaFold 远未彻底解决蛋白质折叠：DeepMind 与 Biohub 纵论生物 AI 的数据扩展律与本质挑战
summary: Google DeepMind 副总裁 Pushmeet Kohli 与 CZ Biohub 数据科学副总裁 Sal Candido 围绕生物大模型的建模与数据展开深度对话。他们探讨了生物学领域的“苦涩教训”、数据扩展律的真实边界、从手工归纳偏置到通用架构的演进，并澄清了 AlphaFold 对蛋白质静态结构的预测与理解真实分子动态之间的本质区别。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
  - CZ Biohub
products_models:
  - AlphaFold
media_books: []
status: evergreen
---
### 序言：蛋白质折叠问题真的被解决了吗？

**Pushmeet Kohli**: 当人们说**蛋白质折叠问题**（protein folding problem）在概念层面上已经被解决时，确实可能取得了一些进展。但事实上，我们并不知道蛋白质实际采取的真正基态（ground state）究竟是什么，也不知道蛋白质所呈现的实际结构分布（distribution of structure）到底如何。我们所做的，基本上只是因为有人通过实验解析出了某个结构并将其存入了 **PDB**（Protein Data Bank，蛋白质数据库），然后我们尝试去复制并获得完全相同的结构。这就是我们所做的事情，对吧？碰巧的是，这确实非常有用。但这绝不意味着我们已经理解了蛋白质动力学（protein dynamics）的全部。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: So when people sort of say the protein folding problem has been solved like at at a conceptual level yes there might be sort of yes there has been there have been some advances we we are we don't know what is the actual true ground state that proteins take and what is the actual distribution of structure that proteins take. What we are trying to do is basically someone got a structure, deposited it in the PDB and we are trying to replicate and get the same structure. That's what we did, right? And it just so happens that it's useful. But that does not mean that we have understood all of protein dynamics.

</details>

### 数据扩展律与生物学中的“苦涩教训”

**主持人**: 大家好。非常高兴能来到这里。今天上午真是令人振奋，有太多精彩的成果发布了。我认为生物科学的未来正在这里被揭示。这是建模分论坛，我们都是建模研究者，因此很自然地要聊一聊数据。

首先，关于数据，我常常思考的一个问题是：是否存在一种针对数据的扩展法则？换句话说，如何才能正确地扩展数据？这让我联想到了从数据角度重新审视的**“苦涩教训”**（The Bitter Lesson）。对于那些非 AI 领域的听众来说，所谓“苦涩教训”的核心论断就是：从长远来看，能够利用计算扩展的方法最终一定会胜出。只要能够持续扩展规模，它就能赢。所以我想先问 Sal：对于数据而言，是否存在一个类似的“苦涩教训”？

<details>
<summary>Original English</summary>

**Host**: Yeah. So, great to be here. What an exciting morning. So many cool announcements. I think the future of bio science is being like announced right here. So this is the modeling session. We are all modelers. So of course it's natural for us to talk about data. So to start out with I think one of the things that I like to think about when it comes to data is like is there a scaling like how do you scale data properly? And this has brought me to this question about the bitter lesson but recast in the frame of data. So the bitter lesson for those of you who are not AI people is the statement that methods that scale win eventually. If you can just scale enough it wins. And so my question I'll start with Sal here is is there a better lesson for data?

</details>

**Sal Candido**: 当然，我认为毫无疑问，为了让模型发挥作用，你显然需要正确的数据。人们对**扩展律**（scaling laws）的一个普遍误解是，以为扩展律无处不在且始终成立。但其实大量的研究工作本质上是在寻找那个能够成立的扩展律。

我们真正在做的很多事情，是努力去探索一种场景：在这种场景下，当你投入更多算力、投入更多数据时，你确实能够得到更好的结果。这种场景之所以极具吸引力，是因为一旦建立起来，你就可以像转动摇臂一样直接推进，它就变成了一个纯粹的工程问题，而这正是我所喜欢的。但这不仅与模型架构有关，更与数据深度绑定。如果你没有具备正确信息统计特征的数据去解决你想要解决的问题——仔细一想这是显而易见的——你就绝不可能得到一个具备你所期望的能力与理解力的模型。你只能从现有数据中提取信息，并在此基础上尝试向外泛化。

<details>
<summary>Original English</summary>

**Sal Candido**: Yeah, I mean for sure I think that you you obviously need the the right data, right? Like in order for it to work. So I think like one misconception of scaling laws is that you know scaling laws are everywhere and they always exist. I think a lot of the work is actually finding that scaling law, right? Like so a lot of what we really do is trying to figure out what's a situation where if you put more compute into it, if you put more data into it, you actually get, you know, a better result out. And the reason to that's a great situation is then, you know, once that happens, you can kind of just turn the crank, right? Like becomes an engineering problem, which is something I like. But you know that it has to do with architecture, but it also very much has to do with data. So if you don't have the data with the right information statistics to solve the problem that you want, which is, you know, I think probably pretty obvious, like if you think about it for a second, like you're not going to get a model that has the capabilities and the understanding of you want. So you can only really pull the information from the data that you have and then use that to generate like to generalize beyond, right?

</details>

**主持人**: 明白。那么在数据采集方面，你如何看待哪些数据模态是最优的？还有一个相关的问题是：你是否认为建模者往往倾向于使用现成可用、易于获取的数据，而不是那些最能契合最终目标、对转化医学最具影响力的关键数据？

<details>
<summary>Original English</summary>

**Host**: Yeah. So when it comes to data collection, how do you think about what types of data modalities are best? And maybe a kind of related question is do you think that modelers have a tendency to work with data that's readily available that's easy to get data rather than maybe the data that or the problem that solves your goal most like maybe is has the most impact for translational medicine.

</details>

**Sal Candido**: 绝对是这样。虽然我不能代表所有建模者发言，但我自己就很“懒”，我肯定倾向于使用现成可用的东西。我认为这其实有一体两面的利弊。

积极的一面在于：当你在做传统机器学习时，你通常会寻找那些能够找到的最纯净、最高质量的数据样本；但如果你像我一样，实际上会跑到仓库后门去翻检别人的“破烂”，看那里到底有些什么。一个具体的例子就是：当我们训练蛋白质语言模型时，我们是在**宏基因组序列**（metagenomic sequences）上进行训练的。这些数据绝非最高质量，甚至其中很多数据我敢保证连一个真实完整的蛋白质都不是。然而，用它训练却能显著提升模型在设计真实有效蛋白质以及理解已知蛋白质方面的性能。这就是积极的一面。

但消极的一面在于，这可能会把你带入一个误区，让你觉得：“好吧，那我们就只管扩大那些容易生成的数据规模吧。”我认为这未必是正确的道路。这也正是我对今天与 **BBI**（Brodsky Bioengineering Initiative）讨论的内容感到极其兴奋的原因之一。关键在于走出去并明确发问：为了解决这个科学问题，我们究竟需要什么样的数据？这不仅需要正确的资源，还需要正确的协作群体。我们在 **CZ Biohub** 努力坚持的一点就是保持开放，与学术社区深度协同，共同推动整个领域向前演进。这是至关重要的环节。因为如果只有构建模型的人，我们就会不由自主地偏向已有数据；如果只有生成数据的人，他们就会偏向容易生成的数据。只有当整个生态在每一步都以开放的方式紧密协同，才能真正理清我们到底需要什么数据，并最终找到行之有效的扩展律。

<details>
<summary>Original English</summary>

**Sal Candido**: Oh for sure. So I think that like I won't speak for all modelers but like I'm lazy so I'm going to work with what's available and you know I think there is actually like a good side and a bad side to this and like the good side is that you know I think like when you're doing like machine learning or like conventional machine learning you're really looking for like the most pristine highquality like data examples that you can find. But when you actually, if you're like me, you're actually someone who goes and you're kind of like rooting around in the back room looking for through people's like junk like what's there. So like a concrete example of this is when we train like when we train a protein language model. We train on metagenomic sequences which are not the highest quality data. In fact, much of that data I can guarantee you isn't even like a real whole protein. And yet that makes the performance of the model go up for designing real proteins that work that make for understanding proteins that like we know are things. And so you know that can so that's like a the positive side of it but that can lead you to like a negative place where you say like well let's just scale up the data that we can generate easily. And I think that's not the necessarily the way to do it. I think that's one of the things that's really exciting to me about like what we're talking about here today with the BBI. You know, it's really going out and saying like what is the data that we need to solve the problem. It's the the right resources but also the right community. Like I think that you know one thing that we do at or we try and do at Biohub anyway is to work in the open, work with the community and move the whole community forward. And I think that's a really critical piece for this because if you just have like people who are building models, you know, we're going to we're going to lean towards the data that exists. If you just have people who generate the data, they're going to lean towards the things that can be generated. But like if you can work together as a community every step of the way in an open fashion, then you can actually figure out like what is the data that we need and then you can find that scaling law.

</details>

**主持人**: 太棒了。Pushmeet，你对数据维度的“苦涩教训”怎么看？

<details>
<summary>Original English</summary>

**Host**: Cool. Uh what do you think sit lesson for data?

</details>

### 从第一性原理定义问题：超越教条式的规模崇拜

**Pushmeet Kohli**: 当 **Rich Sutton** 在 **DeepMind** 和我们一起工作并深入思考“苦涩教训”时，我恰好就在那里。从 Rich 最初的演讲中，我汲取到的核心思想是：你必须审视整个流程的真正瓶颈究竟在哪里。

人们很容易产生教条主义心态，认为：“哦，既然苦涩教训说通用计算会击败一切，那我们就只需要算力，别的一切都不需要关心。”但现实情况是，任何系统都有其构建模块。如果你的最终目标是解决实际问题，你就必须统筹兼顾整个过程中的各个要素。而进入这一过程的绝对不仅仅是数据或模型，它包括计算平台、建模架构、数据本身，更包括你对这个问题的严谨形式化定义（formalization of the problem）。

如果你没有把问题定义好，即便在数据生成或模型规模上推进了十倍，你也根本不知道自己究竟是在朝着目标前进还是在背道而驰。你甚至都无法评估自己的进展！这正是我们必须首先在评估体系上达成共识的原因。在没有定义好评测基准的前提下，单纯去讨论“扩展数据”或“扩展模型”，我认为是对“苦涩教训”的片面误读。

我非常赞同 Sal 的观点，这正是一项极其重要的努力：它把不同背景的专家凝聚在一起，共同聚焦于推动科学发现所面临的真正挑战，而不是盲目崇拜某一种特定的范式——无论是教条式地单抓数据生成，还是孤立地追求模型结构。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: Yeah. So I think the so I was at deep mind when Rich was with us and working and thinking about this this idea of the bitter lesson when Rich and I took my the thing that I took from Rich's original sort of lecture that he actually gave was that you have to look at what are the true bottlenecks of the whole process. And people can get quite religious about saying oh the bitter lesson says compute wins everything so we don't care about anything else let's just focus on compute. The real thing is that there are building blocks of any system. If you if your eventual sort of goal is to solve the problem then you have to be able to look at both aspects of what goes into the process and what goes into the process is not just data or modeling it's computing it's modeling it's data and it's the formalization of the problem. If you haven't formalized the problem well enough and if you make 10x progress on data generation or modeling you wouldn't know if you're making progress or going backward. You wouldn't be able to evaluate! That's why we need to sort of agree on evaluation. Talking about data or modeling scaling without defining evaluation is basically doing a disservice to the to the lesson itself, I would say. So and I completely agree with with Sal in the sense that that's why an effort like this is extremely important which just brings people together to focus on what are the actual chi challenges if you want to advance science rather than being religiously following like advances on data generation or in modeling.

</details>

**主持人**: 这个回答太精彩了。那么对此有什么可以落地的行动建议吗？我的意思是，始终坚持“问题优先”，然后再去推导解决方案。在迈向下一代转化医学的过程中，科研社区究竟应当如何思考这个问题？

<details>
<summary>Original English</summary>

**Host**: Cool. Uh that's I really like that answer. So what do you think like the actionable takeaway is from this? Like I mean always define the problem first and then you know figure out what solution you need. But like how should how should the community be thinking about this as we go forward for the next you know generation of basically trying to solve translational medicine.

</details>

**Pushmeet Kohli**: 我给所有刚进入这个领域的年轻人的建议是：首先把自己塑造成一个跨学科的复合型人才，把问题本身彻底搞清楚。为什么要解决这个问题？这个问题的具体表征是什么？然后从第一性原理（first principles）出发去推导解决方案。不要被某种特定的方法论绑架。

如果这是一个可以通过生成数据解决的问题，那就毫不犹豫地去生成数据；如果问题可以通过引入物理先验或者通过大规模计算来攻克，那就果断选择对应的路径。你需要从终局的落地成果（impact level）倒推，评估各种方案的投入产出比，去选择那些在长期来看真正可行、能够帮助你达成预期目标的有效手段。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: Yeah I think the the the advice that I give to anyone who is working who is starting in in the area is that think of yourself as a multid-disiplinary person. Understand the problem first. Why are you working on the problem? What is the representation of the problem? And work from first principles. Don't be bound to a method. If the problem can be solved by generating data, do that. If it requires physical priors or if it requires compute, do that. But work back from the actual problem and then evaluate what are the tools that are going to be feasible in the long term in getting you to that intercept the the the intercept level the impact level that you're going after.

</details>

### 从手工归纳偏置到通用扩展：算法工艺的演变

**主持人**: 很好，这正好引出了我的下一个问题。当我们观察建模技术的演化时，比如 **AlphaFold 2**，它本质上就像一件精雕细琢的艺术品——里面包含了大量极其精妙的人工设计特征，系统的每一个组成部分都经过了深思熟虑。尽管 DeepMind 的部分工作仍带有这种精巧设计的色彩，但大趋势似乎正在转向更加通用、更具可扩展性的策略。

你们认为当下是否仍然存在大量需要这种“手工艺式”定制解决方案的特定问题？还是说在固定预算、人才和算力资源的前提下，我们更应该优先押注通用的规模扩展？

<details>
<summary>Original English</summary>

**Host**: Yeah. Okay. Cool. Uh so this actually leads me right into my next question which was um when I look at sort of the evolution of modeling uh let's say AlphaFold 2 was essentially a work of art like a bunch of very carefully handcrafted features uh there was a lot of thought very intentional thought done to every part of the solution uh and then uh I think you know some some of Google or Alphabet's work has been you know kind of still stays in that space but seems like the general consensus is to move to more scalable, more general strategies. Um, do you think that there's still a lot of like artisal craft solutions or problems that need that or is our resources better spent on generally speaking um, you know, fixed resources, fixed money can go to compute, it can go to talent, it can go to data, you know, should we be focusing on scale first?

</details>

**Pushmeet Kohli**: 让我们再次回到第一性原理来思考：当你试图通过构建精巧的模型架构来提升性能时，这种“艺术与工艺”绝非偶然为之。我们确实做了海量的实验，但在实验背后始终存在一个清晰的愿景——那就是源自生物物理学和生物化学的深刻科学直觉。

比如，我们知道氨基酸残基在空间中并不是孤立行动的，它们会受到相邻以及空间邻近残基的相互作用影响。既然如此，为什么不把这一规律直接编码进模型架构中呢？如果你已经从科学界汲取了成熟的认知，就应当利用这些信息，赋予模型一种**不公平的先验优势**（unfair advantage）。这种归纳偏置能极大地提高模型的**数据效率**（data efficiency），因为它无需在零先验的基础上去重新学习物理世界的每一条已知定律。

同时我还必须指出：清洗和构建高质量的数据本身也是一门精湛的艺术。这绝不是一句“灌入更多数据”那么简单。如果你只是在低效地复制同质化数据，模型根本不会获得任何质的飞跃。因此，核心从来不是单纯的“大数据”，而是“好数据”。深入理解到底需要多大广度和覆盖度的数据才能在特定科学问题上取得实质性突破，本身就是一个极其迷人、甚至远比纯架构设计更具挑战性的重大课题。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: So my again sort of let's approach it from first principles and think about when even so like when you think about like the arts and crafts of how do you construct a model to be better. I think it it was not an accidental thing right we did a lot of experimentation but there was a vision behind it that all this in scientific intuition that came from biophysics and biochemistry that those interactions that sort of amino acid sort of residues are not just doing their own thing they are being influenced by other residues. So let's bake that in like why like if you can if you have learned something from the scientific community use it use that information and try to sort of encourage the model and sort of give it that unfair advantage that that it it has um and it it does basically makes the model much more data efficient because it doesn't have to replicate everything. I also have to sort of mention that curating good data is an art in itself right it's not as if like you will say well put more data if you if you replicate the same amount of data you're not going anywhere so it's not just about big data it's about good data and actually understanding sort of the coverage of what data is necessary for making progress in the problem is in fact I would say a much interesting and much more challenging problem in itself.

</details>

**主持人**: 讲得很好。Sal，看你的表情好像有些想法，你怎么看？

<details>
<summary>Original English</summary>

**Host**: Yeah. Cool. Well, do you looks like you have a thought. So, what do you think?

</details>

**Sal Candido**: 我非常赞同。正如你们所说，这完全取决于你要解决的具体问题。如果你拥有的数据量较小，那么毫无疑问，你必须依靠精巧的模型架构和强烈的先验假设来弥补数据密度的不足。

但当你拥有海量数据时，情况就不同了。随着数据规模的持续扩张，架构设计的核心诉求会发生转移：你不再需要手工灌输微观规则，而是需要确保架构具备足够的能力去消化、拟合并表达庞大数据中蕴含的复杂规律。在这个阶段，如果你依然强行施加过去在小数据时代总结出的刚性硬编码假设，反而会人为压制模型的表征能力上限，阻碍其发现更高维的潜在规律。

所以，这绝非非黑即白的二元对立。在每一个不同的数据规模节点上，我们都必须动态权衡：为了让手头的数据释放最大价值，当前最适配的模型架构到底是什么？

<details>
<summary>Original English</summary>

**Sal Candido**: Yeah, I think um I mean I I very much agree. I think as you it really depends on you know as you're saying the the problem to be solved. So if you have kind of a smaller amount of data then certainly you know you have to lean heavily on the craft of building that model to be able to extract that out. But as you get more and more data, you know, compute and capacity of the models becomes a bigger problem, right? And you know and as Pushmeet was saying, you don't necessarily want to constrain the model because you want the model to be able to find the things that you know you don't know, right? You want to be able to let it find the rules and you don't want to constrain it. So, you know, like I think it's not either/or, but I think that as we think about where to go, you know, we should always be asking like at every scale, what are the things that these models need? But then also like at every step of the way, at every scale, what is the right architectures then to to get the most out of that data?

</details>

### AlphaFold 究竟解决了什么？冷冻电镜与分子真实动态

**主持人**: 很好。如果审视目前蛋白质结构预测的现状，媒体新闻往往大肆宣称“蛋白质结构预测已经被彻底攻克了”。但如果你去和结构生物学家交流，他们会说：“不，这充其量只是第一步。”目前我们在蛋白质动力学、构象分布以及从头设计上依然面临巨大阻碍。你认为这是因为我们尚未掌握正确的算法和数学思想，还是说这只是一个时间问题，未来会水到渠成地演进？

<details>
<summary>Original English</summary>

**Host**: Cool. So, uh if you think about the the state of protein, uh structure prediction right now, you know, the news will say protein structure prediction has been solved. Uh but then like if you talk to modelers, they're like no no no no like this is just the first step. You know, what about dynamics, what about design, right? Like do you think that that's a problem of we don't have the right data, or do we not have the right algorithms um or ideas or is this like something that we can see evolving in the future? Uh and it's just kind of a matter of time.

</details>

**Pushmeet Kohli**: 科学研究的运作方式，本质上是通过孤立变量、切分问题，然后一步一步取得渐进式的突破。

因此，当外界声称“蛋白质折叠问题已经解决”时，在特定的概念切片上，确实取得了重大突破。但是，把“蛋白质看作生命积木”的叙事本身其实是有缺陷的——蛋白质根本不是僵硬的积木！虽然我也经常在科普时用“积木”这个比喻，但我内心深处其实并不认同。蛋白质是极其精细复杂、高度柔性且动态无序的实体，其空间构象会随着微观生理环境的改变而剧烈变化。

当年我和 **John Jumper** 经常坐在一起讨论：我们到底在尝试求解什么？现实是，我们根本不知道蛋白质在体内所采取的真实基态是什么，更不知道它在热力学平衡下的真实构象分布到底如何。我们真正做的事情，仅仅是找到别人通过实验测定并上传到 PDB 中的静态晶体结构，然后训练算法去高精度复现那个特定的结构。这就是我们的全部工作。幸运的是，仅仅做到这一步就已经对下游产生了巨大的实用价值。

但这绝不意味着我们已经理解了蛋白质动力学的全貌！在科普层面，向公众传递“我们取得了重大胜利”很容易；但在座的科学家和同行心里都非常清楚，前方的未知依然是一片汪洋。我们才刚刚起步，绝不能因为暂时的成果而削减在蛋白质动态与结构预测上的科研投入。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: Yeah, I think science how it sort of operates is basically by isolating something and then making progress step by step. So when people sort of say the protein folding problem has been solved like at at a conceptual level yes there might be sort of yes there has been there have been some some advances but um I think it's to it's also like when you think about that narrative of proteins building being the building blocks proteins are not blocks and they're not sort of they don't act as as blocks right I I say proteins are the building blocks all time but actually like I I don't believe in it right proteins are extremely complex they are disordered their shape might change depending on the context and like what alphafold did and in fact like John John and I John jumper and I basically used to sort of discuss this like what are we trying to solve we we are we don't know what is the actual true ground state that proteins take and what is the actual distribution of structure that proteins take. What we are trying to do is basically someone got a structure, deposited it in the PDB and we are trying to replicate and get the same structure. That's what we did right and it just so happens that it's useful but that does not mean that we have understood all of protein dynamics. So I think the like at the at the at the top level it's easier to communicate that we have made progress but the scientists among us and in this crowd the we know right and I think that's that's the really important thing for us to understand and have that common ground that a lot of work needs to be done and we have made progress and there's a lot to celebrate but let's not stop the funding of protein structure prediction and protein dynamics because we are just getting started.

</details>

**主持人**: 那么你认为眼前最大的阻碍是什么？如果给你一根魔法棒，能够凭空变出某种目前极度匮乏的关键要素，以彻底加速蛋白质功能、动力学或从头设计，你会希望变出什么？

<details>
<summary>Original English</summary>

**Host**: So what do you think the the biggest blocker if there's one thing you could wave a magic wand and say like we have more of blank that would accelerate one of those things function dynamics or design what would the magic wand be what would you wave into existence

</details>

**Pushmeet Kohli**: 我的学术背景非常杂糅：我最初是一名安全研究人员，后来进入计算机视觉、贝叶斯理论，再进入判别式机器学习和深度学习，做过 AI 代码生成，最后才投身 AI for Science。

所以当你问我这个问题时，我内心的计算机视觉研究者立刻兴奋地指向了**冷冻电镜微相图**（Cryo-EM micrographs）。我当时的第一反应是：为什么要去摆弄那些经过人工解析和拟合的 PDB 二次数据？我们为什么不直接去源头工作？那些最终生成的静态结构一定丢失了原始实验中的海量动态信息！我们理应直接在原始的冷冻电镜显微图像上训练端到端模型。

如果我们能构建出足够规模的模型，配以海量的源头数据，直接从中解析出分子在冷冻样本中冻结的丰富动态连续分布信息，那将是一场真正的革命。我曾经尝试过去推进这个方向，但这需要极其庞大的工程与算法突破，需要更多的工作。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: Oh I I have basically when when so I I'm a machine learning I my background is like quite eclectic I started as a security researcher then went into computer vision Bayesian theory um and finally got into discriminative machine learning and deep learning and so on and AI for coding and then finally science. So when you asked me that question like my computer vision the computer vision researcher in me was super excited about Cryo-EM micrographs. I was like what is this sort of PDB data I should be working at the source right I should be looking at the Cryo-EM micrographs I I don't want those structures they must be sort of missing out all the data it's I should I should just directly operate at cryo micrographs now getting models that can scale at that level with the right amount of data and can extract all the dynamics and distributional information that is captured there would be an amazing thing. I tried I did but it requires more work right.

</details>

**主持人**: 你目前还在做这方面的探索，并且确信这是一条能通向目标的道路吗？

<details>
<summary>Original English</summary>

**Host**: Still work on it but you you believe that this is a route this this can give you

</details>

**Pushmeet Kohli**: 是的。我相信未来的某个时间节点，也许会有比我更优秀的学者在这个方向上取得突破，带领我们抵达目的地。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: Yeah I think at some point of time maybe like people better than me would take a stab at it and and we'll get somewhere.

</details>

**主持人**: Sal，你觉得呢？

<details>
<summary>Original English</summary>

**Host**: What do you think Sal?

</details>

### 理解与创造：费曼名言与可解释性的双重视角

**Sal Candido**: 这非常有意思。我认为这些模型确实非常实用，但它们往往并没有直接对应到人们最终真正渴望求解的问题上。它们服务于特定的技术环节，你可以借助它们去开展药物设计等任务。但我始终认为，折叠模型本身依然值得我们持续钻研，因为它们依然有巨大的进化空间。

关于蛋白质设计，物理学家**理查德·费曼**（Richard Feynman）有一句著名的格言：“**凡我不能创造的，我就未曾真正理解**”（What I cannot create, I do not understand）。我认为这正是当下这场 AI 革命令人心潮澎湃的本质所在。

以大语言模型为例：如果你去观察一个 Transformer，去解构其内部的注意力权重、MLP 层和激活模式，即便这个网络只是在海量文本上被动训练出来的，你依然能从中观察到某种深刻的内在规律正在涌现。

对于蛋白质模型也是完全一样的道理。虽然我们构建模型的直接目标是预测结构或设计新分子，但当你深入审视模型内部表征时，你会发现它为了完成这一任务，实际上已经在高维潜空间中自主构建出了对生物物理学相互作用的内部理解。这种能够将未知的深层知识从“机器的黑盒”中逆向提取出来的可能性，展现出极其迷人的科学前景。

<details>
<summary>Original English</summary>

**Sal Candido**: Yeah I think that um it's really interesting because I think these models are um I mean they're they're quite useful but they're not exactly the problem that most people want to solve like they serve a very specific purpose and then you can also use them to go do things like design proteins right like you know do drug discovery and design and um you know I think we should keep trying to work on folding models because I think they're going to keep getting better and better. So, uh, with regards to design, um, there's this famous Feynman quote, uh, that which I cannot create I cannot do not understand. And I think that that's like what's so cool about this revolution that we're seeing right now. You know, you can think about like if you look inside of LLM and you look at what's happening inside of the transformers, what's happening inside the MLP layers, inside the attention mechanisms, like you know there is something that's really cool happening there where it's learning something even from just being trained on on natural text. And the same thing is true of like inside of these protein models, right? Like so in addition to it being able to spit out something which is useful to us, there's certainly something to learn just by looking at what's inside. And trying to pull that knowledge out of the machine so to speak right like and so it's something that like I can understand maybe that's just like my esoteric curiosity like I think there's so many things to learn.

</details>

**主持人**: 很多科学家极度渴求底层机理的“理解”，最终终点指标对他们来说或许次于对原理的求索；但反过来，我们坐在这里也是为了解决转化医学的实际临床问题。这两者之间该如何平衡？

<details>
<summary>Original English</summary>

**Host**: I think lots of scientists really want to understand things and the end points are maybe not as important but then you know we are here to solve translational medicine as a as a problem right

</details>

**Sal Candido**: 我认为这两者并不矛盾。你挖掘得越深，就越能找到推动应用向前发展的正确路径。

这里最核心的一点是：在传统科学研究中，我们习惯于先在脑海中提出假说，再通过实验去验证机理；但现在的现实是，我们已经拥有了这些表现极其出色的前沿模型。模型内部已经凝聚了我们尚无法完全用语言描述的高阶知识。因此，理解这些模型是如何思考与运作的，不仅满足了探索自然规律的好奇心，更构成了我们设计下一代更强系统、赋能转化医学的基础基石。

<details>
<summary>Original English</summary>

**Sal Candido**: Or I mean I think you do have to like the more you dig into things the more that you can find the right way to to keep pushing them forward. So I think like one thing that's really salient to me about this is I think we have an opportunity to like learn from the models as much as we have an opportunity to teach the models. And so I think there's a lot in there still to be unlocked even from the models that we have now right like and I think that's important for us to understand how do these models work as we move towards pushing translation into this model, right? Like so in addition to it, you know, being able to spit out something which is useful to us, there's certainly something to learn just by looking at what's inside.

</details>

**主持人**: Pushmeet，你怎么看？“面向设计”与“追求理解”之间该如何取舍？

<details>
<summary>Original English</summary>

**Host**: Yeah. What do you think Pushmeet? Design versus understand.

</details>

**Pushmeet Kohli**: 我对这个问题的视角稍有不同。我认为，某种程度的“理解”对于工程落地是绝对不可或缺的。

但这里的关键在于：我们所说的“理解”究竟指的是什么？我常常反思人类对于工具的掌握过程。想想飞机的机翼——我们今天制造飞机、乘坐飞机跨越大洋，难道是因为人类已经彻底从数学第一性原理完全推导并精确解析了流体力学中的湍流和**纳维-斯托克斯方程**（Navier-Stokes equations）吗？并没有！数学上我们至今都未能彻底解出该方程的全部解析性质。

我们之所以敢于建造客机并登机飞行，是因为我们建立了一套极其完备的**行为刻画体系**（behavioral characterization）。我们在风洞中进行了成千上万次实测，测定了升力系数、临界失速角，绘制了详尽的极限工况安全包线。换言之，即便我们未能从最底层的微观分子运动论去全盘解析气流，我们依然对机翼在宏观不同工况下的外部行为建立了绝对可预测的信任。

对于生物 AI 模型而言，情况也是一模一样的。当我们要把一个模型应用到真实药物研发或临床决策中时，真正的风险在于：如果系统缺乏这种行为边界的刻画，我们盲目使用它不仅无益，反而会带来灾难。

以 AlphaFold 2 为例，它展现出的强大泛化能力并非团队在上线前就能预先穷尽测定的。当模型权重开源后，全世界的科学家在实测中惊喜地发现：它居然能够准确预测多聚体复合物相互作用，甚至其预测置信度（pLDDT）的低分区域在生物学上竟高度对应着真实的固有无序蛋白质区域（IDR）。这种对模型在各种外部边界条件下“如何行动”的精准描绘，正是建立临床与工程信任的生命线。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: So, I have a sort of different take on this in the sense that I think when when we think about models I think some level of understanding is necessary. So I'll say what I mean by understanding. Think about how we design aeroplanes. Do we really understand Navier-Stokes? Like people do people still say Navier-Stokes is is one of the millennium prize problems, right? But that does not stop us from designing aeroplanes. Why? Because we understand the behavioral characterization of the system. We know what are the safe operating zones, what are the failure modes, what are the limits of applicability. And I think when people say interpretability or understanding, we don't necessarily need to understand how each neuron fire in that in that model. What we need to understand is what is the behavioral characterization of the model? What are its operating boundaries? When can it fail? When can it generalize? And that is the understanding that is required for us to take it to translation. When we launched AlphaFold 2 and made the weights available, people found out that it can predict complexes, people found out that low confidence regions actually correlate with intrinsically disordered proteins. That was an understanding of the behavior of the model. And that is extremely important and we can't sort of just be using these models without having that behavioral characterization because otherwise it will sort of rather than being helpful harm us right.

</details>

**主持人**: 所以你的核心观点是：狭义上的机制可解释性并不一定是硬性必需的，而关键在于建立一种确保模型绝对值得信赖的行为刻画方法，以便人类科学家能够据此作出确定性的行动决策。这才是大家应当聚焦的重点？

<details>
<summary>Original English</summary>

**Host**: So your take is that interpretability strictly speaking isn't necessary but a way of ensuring the model is trustworthy so humans can make actionable decisions is the thing that people should be focusing on?

</details>

**Pushmeet Kohli**: 没错。而且我认为“可解释性”往往取决于解释的受众究竟是谁。

如果试图向一个人类科学家去解释包含数千亿参数和复杂注意力流的模型究竟是如何一步步推导出最终构象的，这在人类有限的认知带宽下几乎是不可能的；但如果把未来更大规模的前沿大模型接入进去，让另一个超级 AI 去分析 AlphaFold 内部的神经激活模式，也许那个 AI 能够敏锐地总结出一套全新的理论，向我们揭示 AlphaFold 到底是以何种机制解析出这些结构的。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: Exactly. And I also think that interpretability is also in the eyes of the beholder like who is interpreting it if it is a human scientist who is trying to interpret how the model is sort of going about and sort of how will it make this prediction. That might be very hard. But if you give some of these large frontier models of the future access to the activation layers and say okay tell me can you predict what AlphaFold will do? Maybe they will be able to predict and they will come up with a theory of how actually AlphaFold 2 was interpreting and producing these results.

</details>

### 临床落地的时间线：渐进渗透还是十倍范式革命？

**主持人**: 好的，现场举起了两分钟倒计时牌。最后提一个简短的问题给你们两位。未来几年，AI 极有可能对人类健康产生翻天覆地的深远影响。我喜欢量化的预测：请给出一个你们的最佳估计，大约还需要多久，我们才能在临床上普遍看到由 AI 驱动带来的实质性医疗成果？Pushmeet，你先来？

<details>
<summary>Original English</summary>

**Host**: Cool. Okay. That's the two-minute warning. So I have one last question for both of you. Quick one. There's a real chance that AI will make dramatic improvements in human health in the immediate future. I like quantitative predictions. Best guess how long until we start seeing AI results in the clinic. Pushmeet you want to start?

</details>

**Pushmeet Kohli**: 我认为这个问题在某种程度上是不太严谨的。因为现实是：AI 如今早已渗透并应用于药物研发流程的每一个细分环节之中了。

从这个角度来看，AI 的成果已经存在于临床管线之中。但如果你真正想问的是，何时能够迎来那种由于底层生物学大模型突破所带来的指数级爆发式跃迁？那我们必须承认，这完全取决于我们何时能够真正攻克复杂生命机制的硬核瓶颈。这就是为什么我们今天宣布的这一全新计划如此至关重要。临床的真正全面爆发，唯有建立在对生命底层运作模型的真正突破之上。

<details>
<summary>Original English</summary>

**Pushmeet Kohli**: I mean the point is AI results in the clinic I think it's ill-posed. AI is being used today already in every part of the drug discovery process, so from that perspective it's already there, right? But if you are sort of asking when will we see the true dramatic disruption, the larger acceleration that will be unlocked only with a better understanding of the biological models that this effort is trying to sort of create. We need to tackle some of these hard challenges of biology and only then will we be able to get these true unlocked results. Small improvements are happening in the clinic all the time. But the actual larger acceleration requires this foundational biological modeling breakthrough.

</details>

**主持人**: 好的，非常感谢。时间马上用完，Sal，请简短作答。

<details>
<summary>Original English</summary>

**Host**: Right. Thanks. So real quick question if we we're almost out of time but you Sal?

</details>

**Sal Candido**: 我很想直接戴上我作为生物学家的帽子来回答。但我认为核心在于重新审视什么叫“推动领域向前”。

正如大家所看到的，我们不能只满足于在现有流程上做 10% 的边际递增修补。如果我们要彻底攻克复杂疾病，我们必须具备更广阔的视野，去探寻能够带来 **10 倍乃至百倍飞跃**（10x approach）的根本性颠覆路径。这并不意味着它是一条更容易的路，但唯有敢于直面根本性难题、重新定义范式，我们才有可能在解决人类重大疾病的征途上实现跨越。现在正是投身这一历史性机遇的绝佳时刻。

<details>
<summary>Original English</summary>

**Sal Candido**: Yeah. I mean, I'm tempted to like literally put on my bio hat to answer this question, but you know, I think it's really important to think about this, you know, as you were saying, like what does it mean to push the field forward? What does it take to make a 10x improvement rather than a 10% improvement, right? And that's not because that's necessarily an easier path. It's because it allows you to take a broader view and see like step back and say what are the real bottlenecks to curing disease, right? And if you want to do that, you really need to go and figure out like what is the 10x approach and so I think it's a really great opportunity to be able to go do that.

</details>

**主持人**: 太棒了。感谢两位在“焦点审讯席”上的深刻分享与坦诚作答！

<details>
<summary>Original English</summary>

**Host**: Awesome. Thank you both. Thank you for being in the literal hot seat. Very interesting.

</details>