---
author: Latent Space
date: '2026-06-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YQWXxnkK4dw
speaker: Latent Space
tags:
  - generative-models
  - diffusion-models
  - protein-structure-prediction
  - drug-discovery
title: 生成对抗网络与扩散模型在3D结构预测中的演进及其在药物研发领域的应用
summary: 文章探讨了生成对抗网络（GAN）向扩散模型的演进，指出扩散模型已成为处理蛋白质和蛋白质配体系统等领域的重要基元。同时介绍了AI研究人员如何利用物理学背景改进分子建模算法，并讨论了在药物研发中，通过对真实项目失败模式的分析来确定关键科学目标的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/13 -->

### 生成对抗网络与扩散模型的演进

**Speaker A**: 我非常清楚地记得，大概在2017或2018年，大家都在讨论GAN（生成对抗网络），认为它们显然是图像生成的未来。显然，它们在处理蛋白质或蛋白质配体系统时效果并不好，我们不得平等待合适的基元出现，结果发现那就是扩散模型，它在这一领域是一个有用得多的基元。很酷的是，对于那些真正对核心基础AI研究感兴趣的人来说，现在最前沿的一些扩散模型创新研究实际上正发生在我们的领域，也就是3D结构预测领域。当时没有人能预测到这一点，但现在，我敢说这已经成为了扩散模型的一个重要支柱。

<details>
<summary>Original English</summary>

**Speaker A**: I remember very clearly in like 2017 2018 talking about GANs and how generative adversarial networks and how uh they're clearly the future of image generation. Obviously, they didn't work very well for for proteins or protein legging systems and we sort of had to wait for the right primitive to get created and that turned out to be diffusion which turned out to be a much more useful primitive for the space. What's kind of cool is right now for people that are are interested in really core fundamental AI research actually some of the most innovative diffusion research is happening in our field is happening in 3D structure prediction right now. No one would have predicted that then but now like that's a pillar of diffusion I'd say.

</details>

### 嘉宾介绍：Sergey Udov与Evan Fineberg

**R.J. Haniki**: 大家好。欢迎来到 Latent Space 科学AI播客。我是 Mirmix 的首席技术官 R.J. Haniki。今天和我一起的还有我的联合主持人 Brandon Anderson，我们非常荣幸能邀请到 Genesis Molecular AI 的创始人和首席执行官 Evan Fineberg，以及在加入 Genesis 担任首席技术官之前曾领导 Llama 2 和 Llama 3 预训练的 Sergey Udov。

<details>
<summary>Original English</summary>

**R.J. Haniki**: Hi there. Welcome to the laten space AI for science podcast. I'm R.J. Haniki CTO of Mirmix. I'm joined by my co-host Brandon Anderson and we're privileged to have Evan Fineberg, a founder and CEO of Genesis Molecular AI and Sergey Udov who led Llama 2 and Llama 3 pre-training before he joined Genesis as CTO.

</details>

**Sergey Udov**: 大家好，我是 Sergey。我在学校里学的是物理。那是很久以前的事了。嗯，毕业后，我碰巧在软件工程领域工作。我原以为我再也用不上物理了。当机器学习（ML）兴起并成为一种潮流时，我发现原来在机器学习中做的很多事情，实际上和你会在物理中做的非常相似。所以我加入了机器学习的浪潮，并在 Facebook 的 FAIR 团队做了一段时间的大量 AI 研究。后来我领导了 Llama 团队，负责 Llama 2 和 Llama 3 模型。最近，我决定再次转换我的职业轨道，稍微回归一下我在物理学方面的老本行，所以我加入了 Genesis 担任首席技术官。

<details>
<summary>Original English</summary>

**Sergey Udov**: Hi, I'm Sergey. I studied physics at school. This is a long time ago. Um, and after graduation, I happened to work in software engineering. Thought I will never need physics again. when ML came up and became a thing and turns out that a lot of things you're doing in ML were actually very similar to what you would do in physics. So I jumped in on ML band and I did a lot of AI research being a part of fair team in in Facebook uh for quite a while. I later on led lama team um llama 2 and llama 3 models and then recently I decided to pivot my career again and um recover my roots in physics a little bit and I joined Genesis as my CTO.

</details>

**Evan Fineberg**: 大家好，我是 Evan。我是 Genesis Molecular AI 的创始人和首席执行官，而且像 Sergey 一样，我也是物理专业出身。在成长的过程中，我跟我家里的所有人都有些不同。几乎每个人都是某种类型的医疗专业人士，而我姐姐成了一名有成就的电视编剧、剧作家和小说家，但我热爱的是物理学和计算机科学。不过我心目中一个成年人该有的样子，是应该去帮助别人，理想情况下是去帮助患者。所以，我一直在寻找合适的途径来实现这一点。来到斯坦福，在 VJ Pande 的实验室攻读博士学位期间，在2010年代中期，我们被机器学习中发生的那些奇妙事情——用一个老派的词来说——深深吸引了，无论是图像还是语言领域。几乎在 Sergey 在 FAIR 研究各种大型图（graph）的同时，我在斯坦福研究的是许多小型图。分子本质上就是由原子、化学键和空间相互作用构成的网络。如果在合适的时间身处合适的地点，你就能利用我们在物理学上的背景去改进用于观察分子的 AI 算法。我们在图机器学习领域发表了几篇论文。有点像 Sergey 那样，我也觉得，哎，我再也用不上这些物理知识了，因为你知道，现在有了机器学习。但事实证明，随着 Genesis 的发展，我们在 GPU 上运行的大量蛋白质模拟也派上了大用场，过去几年我们非常兴奋，一直在探索如何为一个全新的领域构建基础模型，并让它们真正能为患者带来帮助。

<details>
<summary>Original English</summary>

**Evan Fineberg**: Hey, I'm Evan. I'm the founder and CEO of Genesis Molecular AI and uh like Sergey also also a physics major. I was a bit different from everyone in my family growing up. Almost everyone was a medical professional of some kind and uh my sister became an accomplished TV writer, playwright, novelist and my love was physics and computer science. Uh but my mental model of an adult was well you should help people and help patients ideally. So um I was always searching for the right the right way to do that and um after you arriving at Stanford doing my PhD in VJ Pond's lab we were cited in the mid2010s of everything amazing going on in machine learning to use a dated term uh for for images and and for language. Um and around the same time that that Sergey was at fair working on a lot of big graphs I was at Stanford working on many small graphs. Molecules are really networks of atoms and bonds and spatial interactions. And if you're at the right place in the right time to bring to bear our backgrounds in in physics to improve AI algorithms for looking at molecules, uh we published a few papers in the area of graph machine learning. And sort of like Sergey, I thought, well, I won't need this physics again because you know there's machine learning. But turns out the massive amounts of simulations on GPUs of proteins that we ran also came in quite quite handy as Genesis evolved and we've been really excited the past few years to figure out how to build foundation models for a totally new domain and make them useful for patients.

</details>

### AI与药物研发的十年演进

**Brandon Anderson**: 是的，这就很自然地引出了我的第一个问题，那就是，我们都在机器学习、分子和生物这个交叉领域待了大约十年的时间。自那时起，科技生物学的一整代可以说经历了兴起与衰落。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Yeah, that's a really nice lead into my first question which is I you we've both been in this domain of sort of machine learning force molecules and bio for roughly 10 years. It's kind of a entire generation of tech bio has you know come and gone since then.

</details>

**Evan Fineberg**: 是的。

<details>
<summary>Original English</summary>

**Evan Fineberg**: Yeah.

</details>

**Brandon Anderson**: 尽管我认为很多针对分子的机器学习方法一直都相当有效，但有一个领域它的效果一直不佳，或者说在历史上一直对机器学习建模有很强的抗拒，那就是蛋白质与小分子相互作用的领域。随着 Genesis 推出的一些最新进展，似乎你们可能已经开始在这个问题上取得了实质性的进步，这种程度的进步我们已经很长时间没有见过了。你能谈谈你们做了什么吗？Genesis 做了什么，是哪些进展带来了这种改进？以及，为什么你认为这确实是对过去那些效果模棱两可的传统机器学习策略的一种真正的超越？

<details>
<summary>Original English</summary>

**Brandon Anderson**: While a lot of machine learning for molecules has been I think quite effective one domain where it's been not effective has or historically really resisted uh machine learning modeling has been the world of protein small molecule interactions and with some of recent advances that Genesis has put out it seems like you might have actually started to make real improvement on this in a way that we haven't seen for a long time. Can you talk about what you have done, what Genesis has done, the developments which led to improvement and why you think this is actually a real improvement over kind of some of the traditional uh machine learning strategies which were ambiguously helpful.

</details>

**Evan Fineberg**: 我完全同意，Brandon。而且令人惊叹的事情在于，或者说真正了不起的事情之一是，当我们最初作为斯坦福 AI 研究的衍生项目创立这家公司时，我们还曾担心自己可能会太迟了。我的意思是，你还记得你和我第一次见面大约是在那个时候吧？正如你敏锐指出的，七年多前在这个领域里几乎感觉像是上一代的事情了。在当时，当我们还是一家小小的种子期公司时，这个领域里就已经有了那些筹集了比我们多出几个数量级资金的现存巨头，也已经有一些非常激动人心的学术论文发表了出来，而我们不得不不断回答这样一个问题：“在这个领域，还有空间容纳另一家用 AI 做药物研发的公司吗？”现在回过头来看，用马后炮的眼光说，这种担忧简直太疯狂了，而且我想现在事后诸葛亮地看，我们在那时做出的论断和我们今天做出的论断是一样的，那就是：人体有两万个编码蛋白质的基因，它们每一个都可能引发疾病；就像在 AI 的其他领域一样，它并不是从零到一，然后突然问题就解决了，现实情况是，从来没有单一的“iPhone 时刻”，甚至连手机也是随着时间的推移不断迭代发展，才变成了今天的样子。人们喜欢回顾过去的“ChatGPT 时刻”，但最初被广泛使用的那批 ChatGPT 模型，比起现在的版本，有用程度要低得多。我认为我们应该用同样的方式来看待 AI 背景下的药物研发。随着我们不断前行，我们应该期待能解决越来越多的问题，会有巨大的飞跃，也会有迭代式的改进，但随着时间推移，它们会产生复利效应。这就是为什么我认为，如同十年前还处于非常早期的阶段一样，但从 AI 的视角来看，当时显然就已经开始为药物研发创造价值了；快进十年，我们今天讨论的这些技术，已经比那个时候有用得多了。在接下来的十年里，我们还将看到又一次指数级的提升。同样的道理，就拿你汽车的自动驾驶能力来说，今天它能做的事情，如果你几年前看到（顺便说一句，我们现在是在旧金山录制这期播客，你往外看就能看到 Waymo 自动驾驶汽车），你绝对会被那些技术所震撼。所以，我认为我们都应该这样看待它：每隔几个月，每过一年，利用人工智能发现新药的技术就会变得越来越有用，并且这在未来的许多年里都会成为现实。

<details>
<summary>Original English</summary>

**Evan Fineberg**: I totally agree, Brandon. It's and the amazing thing is or one of the one of the really remarkable things is that when we were founding the company initially as a spin out of the research we were doing in AI at Stanford, um we were afraid that we could be too late. I mean, you remember that you and I first met around that time, right? seven plus years ago as you rightly point out almost a different generation in the area and at the time when we were a little seed company there were already incumbents in the space who had raised orders of magnitude more more money than us there were already some really exciting academic papers that were out and we had to constantly answer the question sort of like is there room for another company doing AI in drug discovery which is a crazy thing to say uh looking with with a backward-f facing light and you know hindsight's 2020 I suppose and the claim that we made then is the same that we made we're making now which is that there's 20,000 protein coding genes and each of them can can cause a disease and in the same way that in other domains of AI it's not like they were zero to one and then suddenly that problem was solved the reality has been there's been no single iPhone moment um even the phone required iterative development over time to become what is today. And people love to talk retrospectively about the chat GPT moment, but the first chat GBT models that became widely used were vastly less useful than than they are now. And I think we should look at drug discovery from an AI context in the same way that as we go we should expect to solve more and more problems and there will be large epithes there will be iterative improvements but they'll compound over time and that's why I think in the same way that 10 years ago was very early but clearly value was starting to be created for drug development then from a from an AI perspective fast forward 10 years, our technologies, which we'll talk about in this discussion, are vastly more useful than they were then. In the next 10 years, we'll see another exponential improvement as well. In the same way that your car in terms of autonomy can do things today, we're we're recording this in San Francisco. You look outside and and see see Whimos, we'd be blown away, you know, a few years ago by by those technologies. So I think we should both be looking at it as every few months, every year the technology gets more and more useful for discovering new medicines with artificial intelligence and that will continue to to be true for years to come.

</details>

**Brandon Anderson**: 也许我们可以稍微回顾一下历史，解释一下大概十年前蛋白质-小分子药物研发的状况是怎样的。比如，我们当时实际上期望用机器学习模型做到什么？从实践的角度来看，当时人们有哪些没有真正预见到的失败模式？

<details>
<summary>Original English</summary>

**Brandon Anderson**: Maybe we can go back in time a little bit and explain like what was the state of protein small molecule drug discovery let's say about a decade ago like what could we actually expect to do with machine learning models and what were some of the failure modes that people I think didn't really see coming from a practical standpoint back then.

</details>

**Evan Fineberg**: 说起来挺有趣的，我稍微打破一下第四面墙哈。其实我在参加播客时完全不知道会有这些问题，但 Brandon 真的知道怎么切中我的“爱之语”。因为就像房间里的其他人一样，你知道的，虽然我的背景更多地是在物理学和计算机科学方面，但在过去十多年里，我一直以一种充满激情的方式非常非常专注于“我们如何利用 AI 来制造药物”这个领域。我见过太多太多结构性的巨变了，为了给你们一个具体的例子，我先给那些生物学背景不太深的人介绍点背景知识：药物发现就像是为一把锁寻找一把钥匙，这里的“锁”通常是一种蛋白质，有时候是核酸；而“药物”就是“钥匙”，它通常是某种小分子、多肽，或者是抗体等其他想要与那把“锁”（也就是蛋白质受体）结合并改变其某种状态的模式。如果它是一种酶，你通常想要阻止其发挥功能；有时你又想激活那种内源性蛋白质，但总的来说就是引入一种外部的分子、外源性的分子来改变某些东西。

<details>
<summary>Original English</summary>

**Evan Fineberg**: It's funny just I mean breaking the fourth wall a little bit. I I I came in not not really knowing any of these questions but Brandon really is knowing how to speak my love language because because like like the other people in this room you know though my my background is much more in the the physics and CS side I've been very very focused in a deeply passionate way about the area of how can we make medicines with AI for over a decade. though I've seen so so many tectonic shifts as a view to give you one concrete example and and I'll give a little background for those who don't have as much biological background drug discovery is akin to finding a key for a lock where the lock is usually a protein some cases a nucleic acid right um and where the drug is the key and it's usually some some small molecule or a peptide or or or an antibbody or some other modality that wants to bind to that lock, that protein, the receptor and change something about it. If it's an enzyme, you want to usually stop it from functioning. Sometimes you want to activate that indogenous protein, but it's is to introduce an external molecule, an exogenous molecule to change something

</details>

<!-- chunk 2/13 -->

### 蛋白质与配体的相互作用 (Protein-Ligand Interactions)

**Speaker A**: 关于那个生物学路径（biological pathway）。那个过程的一个必要但不充分条件是，找到一种能够很好地结合到那个受体或那个蛋白质上的分子。当然，这还不够。我们还需要确保它不会结合到某些反靶标（anti-targets），即你想要避开的某些蛋白质。这通常会介导毒性。你需要关注毒性特性，这通常包含大约 30 多个属性，以确保你的分子除了有效并且能够到达正确的组织之外，还是安全的。嗯，这些都是至关重要的，都是必要的，但没有一个是充分的。不过，为了回答你关于蛋白质与配体相互作用的问题，一个具体的例子是，很长一段时间以来，我们一直有一个假设，即如果我们能够预测其 3D 结构，这些 3D 坐标——对于计算机科学领域的人来说，可以想象成一个点云（point cloud）——也就是你的药物的 3D 位置和蛋白质的 3D 位置。而且如果你能以高精度对其进行建模，那将自然而然地引导我们去测量结合亲和力（binding affinity），或者更准确地预测其效力（potency）。这在当时是一个根本无法验证的假设，因为用于预测那些 3D 姿态（poses），即复合物 3D 结构的模型实在是太差了。

<details>
<summary>Original English</summary>

**Speaker A**: about that biological pathway. A necessary but not sufficient part of that process is finding a molecule that binds well to that receptor or that protein. Of course, that's not sufficient. We also need to make sure it does not bind to certain anti-targets, certain proteins you want to avoid. That often mediates toxicity. You need ad toxicity, which is typically like 30-ish properties to make sure your molecule is safe in addition to being effective and gets to the right tissue. uh these are all critical and all are necessary and none are sufficient. But one concrete example to answer your question about protein liend interactions is that we had a hypothesis for a long time that if we can predict the 3D structure, the 3D coordinates can imagine for the CS people like a point cloud um the 3D positions of your drug and the 3D positions of the protein. And if you could model that with high accuracy, that will lead naturally to measuring binding affinity or or predicting potency more accurately. That was a hypothesis that fundamentally could not be tested because models for predicting those 3D poses, the 3D structures of complexes were so bad
</details>

**Speaker B**: 或者，如果你能预测它，它需要如此庞大的计算技术资源，以至于你倒不如直接去解决这个问题。

<details>
<summary>Original English</summary>

**Speaker B**: or if you can predict this, it requires so much computational tech resources that you might as well just solve the problem,
</details>

**Speaker B**: 对吧？就像你倒不如直接去解析出 3D 晶体结构（crystal structure）或者冷冻电镜结构（cryo-EM structure），你的意思就是这样。这可能会花费数万美元，嗯，可能需要数月或数年的时间，对吧？作为整篇博士论文，或者博士后有时候真的会 24/7 全天候工作，就是为了试图解析出一个 3D 结构。而当时的假设是，如果我们能把这个过程的速度提高几个数量级，有时候还能变得更准确——我们可以讨论一下通过人工智能，或者在此之前通过分子动力学（molecular dynamics）来实现——那么你不仅会加速药物的发现，还能使那些以前被认为是不可成药（undruggable）的靶标的药物发现成为可能。那当时仅仅是一个假设。而且它一直花到了最近几年才证明，如果我们系统地提高这些预测的准确性，如果我们能够证明蛋白质-配体 3D 复合物预测的准确性，我们就能让效力（potency）预测也变得更加准确。这是一件让我个人感到极其欣慰的事情，因为当我们几年前创办公司时，那还仅仅是个假设，而现在它已经变成了现实，这要归功于许多不同想法的融合，这些想法使得 Pearl 以及与之类似的其他基础模型成为可能。

<details>
<summary>Original English</summary>

**Speaker B**: right? like you might as well solve the 3D crystal structure or cryium structure is what you're saying which is can cost tens of thousands of dollars um it can be months or years right entire PhD thesis posttos can sometimes work literally 24/7 trying to solve one 3D structure and the hypothesis was that if we make this orders of magnitude faster sometimes more accurate which we can talk about with artificial intelligence or before that with with molecular dynamics that you would thereby not only accelerate drug discovery but enable the discovery of medicines for targets that were previously thought to be undruggable. And that was just a hypothesis. And it and it took until the last few years to show that if we systematically improve those the accuracy of those those predictions, if we can prove the accuracy of a protein lian 3D complex, we can make potency prediction more accurate as well. And that's something that I am personally extremely gratified to feel like we've been showing because that was just a hypothesis when we started a company a few years ago and and now it's become a reality thanks to the convergence of a lot of different ideas that were able to to to enable Pearl and other foundation models like it.
</details>

### 关于 Pearl 基础模型 (About Pearl Foundation Model)

**Speaker C**: 是的。你能稍微谈谈 Pearl 吗？嗯，所以我觉得关于 Pearl 最有趣的事情之一，在我看来，就是它试图扩展那些在我看来无法扩展的东西。嗯，RNA、小分子，你知道的，通常如果你去扩展它们，模型出来的结果就像是纯粹的模式匹配器（pattern matchers）。这些东西喜欢告诉你你已经知道的事情，而且有时候它们在告诉你你不知道的事情时可能表现得不那么好。所以，也许看起来有迹象表明 Pearl 实际上已经超越了这一点。嗯，比如，促成这个结果的关键洞见是什么？

<details>
<summary>Original English</summary>

**Speaker C**: Yeah. Can you talk about Pearl a bit? Um, so the I think one of the interesting things about Pearl in my mind is it was an attempt to kind of scale what seems unscalable to me. Uh, RNA small molecules, you know, normally if you scale them, models just come out as just like pure pattern matchers. These things love to tell you what you already know and sometimes they're maybe not so great at telling you something you don't know. So maybe it seems like there's hints that Pearl has actually moved beyond this. Um, like what were the key insights which went into this?
</details>

**Speaker A**: 当然。顺便说一句，布兰登（Brandon），就像你描述的那样，那不应该让在场的任何纯机器学习从业者感到惊讶，仅仅是因为机器学习最初就是为了模式识别而构建的。而且当你启动 Claude、ChatGPT 或其他任何大模型时也是一样，当它最接近训练数据时，它的表现会最好，并且它会基于此进行模式匹配。所以我认为，这也是人工智能遇到物理世界时产生巨大紧迫感的原因，即如何进行外推，如何制造可泛化的模型，而这一直是我们非常努力在解决的问题。也许……也许 Sergey 想就此给出更多背景信息，或者退后一步，讨论一下 Pearl 是什么。它是一个结构预测模型，这基本上意味着，它接受一个蛋白质序列和一个你试图附着在这个蛋白质上的配体表征作为输入，然后它会预测这个蛋白质和配体在 3D 空间中结合成一个结构时会是什么样子。

<details>
<summary>Original English</summary>

**Speaker A**: Sure. And by the way, Brandon, like what you describe, that shouldn't surprise any like pure ML practitioners in the audience, just because machine learning is initially constructed for pattern recognition. And it's the same with when you fire up claude or catchb or what have you, it's going to do best when it's closest to the train data and it's going to pattern match off it. So I think that has been the big sense of urgency in AI meeting the physical world is how to extrapolate how to make generalizable models and that's we've been really hard to work on. Maybe maybe Sergey wants to give some more more color on that maybe to step back a little bit and discuss what Pearl is. It's a structure prediction model which basically means it takes as an input a protein sequence and a liant representation that you try to attach to this protein and it predicts how this protein and liant are going to look together uh as a structure in the 3D space.
</details>

**Speaker C (Brandon)**: 所以人们有时用于这个过程的一个术语像是共同折叠（co-folding）。这是多重折叠，比如 AlphaFold 3，然后是一些……然后是 RoseTTAFold，嗯，OpenFold 3 等等，它们也以自己的方式实现了一些这些想法。嗯。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: So like a term for this people sometimes I've used is like co-folding. It's multiple folding alpha fold three and then some of the and then bolts and um open fold 3 and so on have also implemented some of these ideas in their own way. Um
</details>

**Speaker D (Sergey)**: 是的，有……有几个模型，有些是开源的，有些是闭源的，它们正在追求相似的……相似的方向。我们的根本区别在于，我们专注于小分子空间，呃，很多模型做的是蛋白质-蛋白质相互作用，并且在小分子空间上也表现得很好。乍一看，它听起来似乎是一个更简单的任务，因为，比如，毕竟，这是一个小分子事件，对吧？所以，像为什么这会具有挑战性呢？但现实是，小分子的搜索空间是如此广阔。宇宙中大约有 $10^{60}$ 种类似药物的小分子。呃，所以祝你好运，去搜索这个空间。而且此外，这也存在各种变化，比如你可以旋转它。呃，你可以有这些分子的不同构象（conformations）。所以……

<details>
<summary>Original English</summary>

**Speaker D (Sergey)**: yes there are there are several models some are open source some are closed source that are pursuing similar similar direction our fundamental difference is that we're focusing on small molecular space uh a lot of models that are doing protein protein interaction interactions and it works well for small molecular space on the first glance it may sound like it's an easier task because like well it's a small molecular invent right so like why would it be challenging But the reality is the search space is so vast all for small molecules. There are 10 to the 60 drug like small molecules in the universe. Uh so good luck searching for the space and there are also all of all variations like you can rotate it. Uh you can have different confirmation of those molecules. So
</details>

**Speaker C (Brandon)**: 也许那里的直觉是，你有，比如当你输入一个 Google 搜索时，如果你只输入几个词，你会得到一个庞大的匹配列表。但是如果你有一个非常具体的查询，那么你会，你知道的，你将会得到较少的几个匹配项，而且它们更有可能是匹配的。所以同样地，对于一个小分子，如果你有一个非常小范围的查询，那就是你的分子，那么你很可能将不得不在一个庞大的可能匹配空间中进行搜索。然而，如果你有一个非常复杂的对象，那么就很容易在那里排除掉一个不匹配的项。这是一种思考这个问题的正确方式吗？

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: maybe the intuition there is that you have like when you type in a Google search if you just do a few words you're going to get a huge list of masters. But if you have a very specific query then you're going to be you know you're going to have a few matches and they're more likely to match. So similarly with a small molecule if you have a very small query which is your molecule then it's likely that you're going to have to search a huge space of of possible matches. Whereas if you have something very complex then there's it's easy to rule out a a match at that. Is that a good way to think about it?
</details>

**Speaker D (Sergey)**: 那绝对是思考这个问题的一种方式。呃，对我来说，仅仅是因为在弄清楚哪个小分子会附着到这个蛋白质上的过程中存在的计算复杂性。

<details>
<summary>Original English</summary>

**Speaker D (Sergey)**: That's one way to think about it. Definitely. Uh for me it's just the the computational complexity on figuring out which small molecule will attach to this protein.
</details>

**Speaker A**: 这是一个如此庞大的……要解决的问题，如果没有好的模型，这是不可能完成的。

<details>
<summary>Original English</summary>

**Speaker A**: It's such a vast um problem to solve that is impossible to do without good models.
</details>

**Speaker C (Brandon)**: 嗯。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: Mhm.
</details>

**Speaker A**: 这就像是大海捞针。

<details>
<summary>Original English</summary>

**Speaker A**: It's like finding a needle in a hay stack.
</details>

**Speaker C (Brandon)**: 是的。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: Yeah.
</details>

**Speaker A**: 在那里，除了你的针之外的所有东西都是非常非常危险的，或者，或者，或者就是不会结合。

<details>
<summary>Original English</summary>

**Speaker A**: Where everything except your needle is very very dangerous or or or just doesn't bind
</details>

**Speaker C (Brandon)**: 或者它们也是针。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: or they are needles.
</details>

**Speaker A**: 是的，对的。对的。我们是在针海里找干草，这可能是个更恰当的比喻。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Right. Right. We're finding hay in a needle stack might be a more analogy.
</details>

**Speaker C (Brandon)**: 是的。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: Yeah.
</details>

### 模型训练与数据瓶颈 (Model Training and Data Bottleneck)

**Speaker D (Sergey)**: 是的，所以……所以现在，现在我们可以去思考我们如何训练那些模型，对吧？那么，人们所使用的大量训练数据来自于所谓的 PDB（蛋白质数据库），呃，这是一个公共数据库，里面有类似所有的历史晶体结构，但它并没有那么大。它只有大约 20 万个晶体结构，并且它很难进行扩展。呃，创建新的晶体结构需要花费大量的时间、精力和资金。尽管有一些项目正在推进这方面的工作，但它的扩张速度仍然像冰川移动一样缓慢。嗯，所以扩展这个数据库是相当困难的。但是我们弄清楚了一点可能做到的事情，而且这与我们的小分子空间非常相关，那就是在小分子空间中，你实际上可以用物理学方法来对你的小分子进行建模。呃，你可以对它们的行为进行建模，这能让你创造更多的数据，所以你可以用一些未必适用于蛋白质-蛋白质之间相互作用的东西来训练模型。呃……

<details>
<summary>Original English</summary>

**Speaker D (Sergey)**: Yeah. So, so now now we can go and think about how we train those models, right? So, a lot of training data that people are used is so-called PGB uh which is a public database of like all of historical crystal structures and it's not that big. It's like 200,000 crystal structures and it's very hard to expand. It takes a lot of uh time and energy and money uh to create new crystal structures. Although there are some projects that are pursuing this, it's still expanding at a glacial pace. Um, so expanding this database is pretty hard. But what we figured out is possible to do and it's very relevant to our small molecular space is that in small molecular space you can actually model your small molecules with physics. uh you can model their behavior and that allows you to create more data but you can train model on something which is not necessarily possible in protein to protein uh
</details>

**Speaker C (Brandon)**: 因为它们对于蛋白质来说太复杂了。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: because they're too complex to for a protein.
</details>

**Speaker D (Sergey)**: 是的，那些是非常大的分子。所以很难用物理学去对它们进行建模。并不是不可能，只是在计算上非常、非常困难。

<details>
<summary>Original English</summary>

**Speaker D (Sergey)**: Yeah, those are very big molecules. So it's very hard to model them with physics. Not impossible. It's just computationally very very hard.
</details>

**Speaker C (Brandon)**: 对。所以，所以我猜你的意思是，你在使用分子动力学（MD）或类似的方法，在对这些小分子进行建模方面做得非常好。因此，你可以以更低的成本将那些结构拼凑到你的训练集中，这样你就可以用它来作为你的合成训练集。

<details>
<summary>Original English</summary>

**Speaker C (Brandon)**: Right. So So I guess what you're saying is you do a really good job of modeling these small molecules using ND or something like that. And so you can kind of put together those structures in your training set at a much lower cost and so that you can use that as your synthetic training set.
</details>

**Speaker D (Sergey)**: 也许，也许稍微退后一步，讲讲我们的……谈谈我们的路线图。嗯，所以这在本质上，与大型语言模型（LLM）的缩放路线图并没有什么根本的不同，比如……回想一下在 LLMs 中我们拥有的所有阶段，你有预训练的缩放（pre-training scaling），然后你有后训练的缩放（post-training scaling），在后训练阶段你做比如微调或者是现在的强化学习（RL），现在大家都在做 RL。然后你做推理时缩放（inference time scaling），所以所有这三个概念，它们是连接在一起的，而正是这引领我们走向了如今最先进的 LLMs。我们在我们这边的做法，在根本上并不是不一样的，呃，我们也有预训练缩放，在这一阶段我们会创建大量的合成数据来训练出更好的模型。嗯，我们确实在做这个。嗯，然后我们开始做的第二件事，也就是这实际上在 LLM 中对应的第三个步骤……

<details>
<summary>Original English</summary>

**Speaker D (Sergey)**: May maybe to step back a little bit about our and talk about our road map. Um so it's not fundamentally different from the road map for LLM scaling like remember in LLMs we have all of the stages you have pre-training scaling then you have post- training scaling where you do like either pine tuning or RL now everybody's doing RL and then you do inference time scaling so all of those three concepts they connect and that that's what led us to state-of-the-art LLMs these days it's not fundamentally different on our side uh we also have pre-training scaling where we create a lot of synthetic data to train better models. Um we do that. Um then the second thing we we started doing is actually the third step in LLM
</details>

<!-- chunk 3/13 -->

### 推理时期的模型扩展与物理约束 (Inference Time Scaling and Physics Constraints)

**Speaker B (Sergey)**:
在模型扩展方面，我们开始进行推理期的扩展（inference time scaling）。这在根本上与大语言模型（LLM）非常相似。当我们谈论 LLM 的推理期扩展时，我们指的是“思考 token”（thinking tokens），即 LLM 不是直接给你答案，而是先去思考一段时间，然后再给出一个回答。我们在自己的模型上也在做非常类似的事情，迫使模型去思考，只不过它不是在用语言 token 进行思考，而是在用晶体结构（crystal structures）进行思考。这些并不是完全实体化的晶体结构，而是内存中某种晶体结构的表征。模型会在这些表征之间来回推导。在这个过程中，我们会使用基于物理规律的引导（physics-based guidance）来将模型的输出引导到正确的方向。我们发现这样做能够大幅度提升模型的性能。

<details>
<summary>Original English</summary>

**Speaker B (Sergey)**: scaling we started doing inference time scaling. And it's fundamentally very similar like in LLM when we talk about inference time scaling we're talking about thinking tokens where LLM instead of giving you the answer right away it kind of goes and thinks for a while and then comes up with a response right well we are doing very similar thing with our models where a model is forced to think except it's not thinking in language tokens it's thinking in terms of crystal structures not fully materialized crystal structures but some sort of a crystal structure representation in memory. Uh, and model kind of goes back and forth with those. Um, and we use physics based guidance during this process to steer the model output in the right direction. And what we found is that it improves model performance by a lot.

</details>

**Speaker A (Interviewer)**:
很容易理解“思考 token”是如何运作的，因为它们基本上就是你看不见的转录文本部分。但我认为至少对于其他模型而言，你们是否有某种循环机制？这是否类似于你们正在做的循环 Transformer 架构之类的事情？还是说还有其他的机制？我知道你提到过在循环中有一些基于物理规律的验证，除了这些还有别的吗？

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: It's easy to understand how thinking tokens work because it's just basically parts of the transcript that you don't see. But I think that at least for other models, do you have like sort of some sort of loop in is that similar to what you're doing like a loop transformer or something like that or is there there's I know you mentioned that there's some physics based verification as part of that in the loop. Is there more to it than that?

</details>

**Speaker B (Sergey)**:
我们模型的一个基础模块是基于扩散机制的预测头（diffusion-based head）。所以，这就像是人们用于图像和视频生成的扩散模型一样。只不过，我们是将它们用于晶体结构的生成。扩散头本质上是迭代的，就像是需要多个步骤，你在这个过程中不断优化你预测的结构。而在执行这个过程的时候，你可以将模型引导到正确的方向。

<details>
<summary>Original English</summary>

**Speaker B (Sergey)**: One fundamental block of our models is diffusion based head. So it's like the same diffusion models what people are using for image and video generation. Well, we use them for crystal structure generation, right? And diffusion head is by nature iterative. It's like multiple steps. Uh you're refining your predicted structure. Um and as you're doing this process, you can steer the model in the right direction.

</details>

**Speaker A (Interviewer)**:
所以这就好像在循环中有一个引导模拟或者类似的东西。你经历一个被动的扩散过程，看看输出的是什么，然后运行某种验证器，用它来判断“我喜欢这个”或“我不喜欢这个”，或者给出一个趋向的向量方向。大概是这个思路吗？

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: So there's like you have like a steering simulation or something that in the in the loop in that. So you you go through a passive diffusion. You look at the what comes out. you run some verifier and use that to say I like this or I don't like this or give a vector to go towards. Is that kind of the idea?

</details>

**Speaker B (Sergey)**:
是的。

<details>
<summary>Original English</summary>

**Speaker B (Sergey)**: Yeah.

</details>

**Speaker A (Interviewer)**:
所以，这就好像你的扩散头基本上在学习类似力场（force field）的东西，而你则是在基于扩散的力场和基于物理的力场之间进行某种平衡。可以这样理解吗，或者……

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: So, so it's like your diffusion head is basically learning something like a force field and that you're kind of balancing out between a diffusion based force field and like a physics based force field or is that a way of thinking about it or

</details>

**Speaker B (Sergey)**:
我很难去理解这些模型在底层真正学到了什么，我认为可解释性（explanability）的整个理念本身就是一个巨大的研究挑战。是的，你可以识别出一个神经元和一个 Transformer 潜在地在思考什么，但这是一个非常、非常困难的问题。所以，我们确实有一些内部表征，但它在输出端呈现出来的是一个晶体结构，我们很难说清楚里面究竟发生了什么。

<details>
<summary>Original English</summary>

**Speaker B (Sergey)**: I struggle to understand like what those models are really learning underneath and I think the whole idea of explanability is a big research challenge. Yeah, you can identify what a neuron and a transformer potentially thinking about, but it's really really difficult problem. So we we have some internal representation, but at the output comes out as a crystal structure, but it's really hard to tell what exactly is happening inside.

</details>

**Speaker A (Interviewer)**:
在这种语境下，有没有可能做一些类似于标准机制可解释性（mechanistic interpretability）的研究，比如使用稀疏自编码器（sparse autoencoders）之类更复杂的技术？还是说做这类事情会遇到什么问题？

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: Is it possible to do something to the effect of the standard mechanistic interpretability things like sparse autoenccoders and the more complicated things in this context or is there a problem with doing that kind of thing?

</details>

**Speaker B (Sergey)**:
我认为作为一个研究方向，这在学术上会很有趣。但这并不是我们目前正在追求的东西。我想我们以后也许可以探索一下。

<details>
<summary>Original English</summary>

**Speaker B (Sergey)**: I think it would be interesting in the research as a research direction. That's not something we are pursuing. I guess potentially we could explore this.

</details>

**Speaker A (Interviewer)**:
好的。明白。

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: Okay. Yeah.

</details>

### 模型输入、物理先验与药物研发应用 (Model Inputs, Physical Priors, and Drug Discovery)

**Speaker C**:
关于大语言模型在咱们这个领域的适用性问题，Sergey 谈论起来要比我有说服力得多。Sergey 很谦虚，但他当时在 Meta 还没离职的时候，是主导了 Llama 2 研究团队的。所以，他训练出了这个星球上被使用最广泛的语言模型之一。不过，关于物理学特性和可解释性方面，我想我可以补充一点，我喜欢从输入、模型本身以及输出这三个维度来看待 AI 模型。而且，回答你的问题，我们发现当你能在不带入人类偏见的情况下，尽可能多地引入物理先验（physical priors）时，它真的能极大改善结果和可解释性。我一直持有这样的观点：AI 本质上就是表征学习（representation learning）。对我来说，这实际上与语言和视觉领域发生的事情没有太大区别，在那些领域，当我们开始使用卷积神经网络（CNN）时，我们就已经把真实的人类先验强加在了图像上，因为我们相当于在说：“嗯，图片就是像素的网格”。这是某种固有的东西。那是一个人类构建的概念，然后我们在这个基础上构建了卷积神经网络；再比如，将语言视为一维的 token 序列，我们首先构建了循环神经网络（RNN），然后构建了 Transformer，但这仍然是在对“如何看待这些数据”植入了一个非常非常严重的先验。在这里，我们的看法也没有太大不同。在我们的情况下，从输入的角度来看，我们这个领域相对于 AI 传统领域的一个劣势是，我们没有整个互联网的数据可以使用。我们不能只是去下载 Reddit 的帖子，或者买一些《华尔街日报》的订阅服务，然后训练一个模型，接着就惊呼：“瞧，预训练模型运行得相当不错！”正如 Sergey 提到的，最接近的等价物是 RCSB 蛋白质数据库（Protein Data Bank），里面大概有几十万个晶体结构或者其他结构，尽管实际上有更多的数据——每个结构包含大量的 token，所以那个数字背后隐藏的潜在信息要多得多。因此，我们必须在输入端表现得非常聪明，这涉及到生成更多的预训练数据，正如 RJ 所提到的那样；在模型架构本身尽可能多地使用物理知识，其理念是不要让模型去重新学习物理规律，要尽可能地少学，这样它就更不容易过拟合。然后在输出阶段，强制执行物理合理性。我认为这也契合了我们作为一家公司的主要关注点之一，也就是我们从一开始就专注于小分子和中等分子（small and medium-sized molecule）药物发现。这是什么意思呢？小分子药物通常是你可以作为药片服用的药物。因此它们具有口服生物利用度。这是大多数人对药物的认知。而中等分子，你可以想想大环化合物（macro cycles）、多肽（peptides），也就是那些打破了传统“五原则”（rule of five）但仍在医学领域不断增长的治疗手段。尽管如此，小分子仍然占据了 FDA 批准药物的 65%。所以我们谈论的仍然是这块蛋糕中最大的一部分。我们从第一天起就带着审慎的重点来构建这一切：药物猎手（drug hunters）需要什么？药物化学家需要什么？计算机辅助药物设计（CAD）科学家需要什么？他们需要什么才能比以前更快、更好地发现药物？因此，我们想要从一开始就建立那种不仅仅是人类可解释的，而且是可用（usability）的系统，并且还要具备物理上的可用性。我们希望这些模型输出的结果能够被那些需要 3D 坐标才能真正产生意义的物理方法所使用。刚才用到了“力场”（force field）这个词。我们希望我们模型的输出能够作为力场的有效输入。去年在《细胞》（Cell）杂志上发表过几篇论文。其中有一篇表明，尽管关于 AlphaFold 解决药物发现问题的呼声很高，但当人们试图拿 AlphaFold 生成的蛋白质结构用于传统的分子对接（docking）时，发现它毫无价值。那些结合口袋（pockets）的清晰度根本不够。它们无法被物理筛选方法所使用。因此，我们希望能够构建出让我们的系统一开始就能被人类使用，能被物理和计算化学界许多相邻的强大工具所使用，以实现这种互操作性。这就是其中的道理。

<details>
<summary>Original English</summary>

**Speaker C**: Sergey is a lot more credible than I am talking about LLM translatability to our space. Sergey is being humble, but Sergey led the Llama 2 research team at at at Meta when when when he was still there. So, he's trained one of the most widely used language models in the planet. But I guess what I can add on the on more the the physical and interpretability side is I like to look at at AI models in terms of the inputs, the model themselves and the output. And um we find it really improves outcomes as well as interpretability to your question when you could include as many physical priors as possible without of course you know biasing the model to what we puny humans believe. But I've always had the view that AI fundamentally is representation learning. And to me, that's actually not that different than what's happened in the language and the vision domains where we're enforcing a real human prior on images when we started using convolutional neural nets is we're saying well pictures are grids of pixels. There's something inherent about that. That's that's a human construct and we constructed comnets on top of that and language as sequences of tokens in one dimension. We first built RNNs. then build transformers, but it's still that's baking in a pretty pretty serious prior on how to to look at that data. And we don't view it very differently here. In our case, from the input perspective, the disadvantage that we have in our field over the more traditional domains of AI is that we don't have the internet to work with. like we can't just download Reddit posts and you know buy some subscriptions to the Wall Street Journal and like train a model and voila the pre-trained model works fairly well. The closest equivalent that Sergey mentioned is the RCSB protein data bank which has more like a couple hundred thousand crystal structures or structures and others although there's a lot more there's a lot of tokens per structure so there's a lot more latent information that that figure would describe. So we have to be clever on the input side which is generating more pre-training data as was RJ's mentioning um using physics as much as possible in terms of the model architecture itself the idea is to not have the model have to relearn as little physics as possible so is less likely to overfit and then at the output stage um enforcing enforcing physicality I think that also goes to one of our main uh focuses as a company which is we've been focused from the beginning on small and mediumsiz molecule discovery. What does that mean? So small molecules tend to be uh drugs that you can take as a pill. So it's orally bioavailable. It's how most people think of medicine and medium-sized molecules. So think about macro cycles, peptides, um modalities that break the traditional rule of five but are still growing uh growing modalities in medicine. That said, of course, small molecules are still 65% of FDA approved drugs. So we're talking about the biggest part of the pie. We're building this with a judicious focus from day one on what do drug hunters, what do medicinal chemists, what do CAD scientists, what do they need to to discover drugs faster and better than they could before. And so we wanted to to build that sort of um human not only interpretability but usability from the beginning and also physical usability. We want outputs from these models to be used by physical methods that require 3D coordinates to actually make sense. Use the term force field. We want the outputs of our model to be useful as inputs to a force field. There was this a few papers that came out. One was in cell I think last year which showed that for all the claims about alpha fold solving drug discovery people try to take alpha fold produced protein structures use them for traditional docking and found no value in it. Those pockets just weren't high resolution enough. They couldn't be used by physical screening method. And so we wanted to be able to build our systems they'd be useful by humans, useful by all the many adjacent and powerful tools from the physics and computational chemistry communities from day one for to have that interoperability. Sense.

</details>

### 模型在药物研发流程中的定位 (Positioning Models in the Drug Discovery Process)

**Speaker A (Interviewer)**:
对。所以这可能是一个稍微往后退一步的好时机。当你研发一种药物时，涉及到很多步骤，从发现、毒性评估到生物利用度。所有的这些东西都有它们各自的名字，我等下让你们来陈述。然后是临床相关的事情，最后是希望能获得批准。你们的模型到底处于这个流程的哪个位置？或者说它们参与了流程的哪些部分？还有这些步骤都有哪些，简单来说，我读到过大概有 12 个步骤，也许我记错了，药物发现有 12 个步骤，获得批准是最后一个。

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: Yeah. So this might be a good time to just step back for a minute. When you develop a drug, there are many steps to that from discovery and toxicity and availability. And so there's names for all these things which I'll let you you state and then there's the clinical stuff and finally uh eventually approval hopefully where do do your models sit in that or which parts of that process do they say and what what are the steps just like briefly I've read that there's 12 steps maybe I don't 12 steps in drug discovery acceptance is the last one

</details>

**Speaker B (Sergey)**:
除非你的三期临床试验失败了。

<details>
<summary>Original English</summary>

**Speaker B (Sergey)**: except that your phase three trial failed

</details>

**Speaker A (Interviewer)**:
没错。是的。所以，你们的模型在哪里、到底是如何帮助人们在药物发现或开发过程中开展工作的？

<details>
<summary>Original English</summary>

**Speaker A (Interviewer)**: Exactly. Yeah. So where do where do you do your models help people to do their jobs in the discovery or in the development process?

</details>

**Speaker C**:
正如你正确指出的，如果我们从最开始一直走到最后。首先我们需要确定是哪个靶点（target）引起了疾病，哪个信号级联反应（signaling cascade）出了问题，是什么导致了患者的这种表型（phenotype）。这并不是一项轻松的任务，但是，当然不是所有疾病，但确实有许多疾病的原因实际上是非常清楚的。

<details>
<summary>Original English</summary>

**Speaker C**: As you rightly point out if we go from from the very beginning to the very end. First we need to identify what target is causing the disease what signaling cascade what's going wrong what's causing the phenotype of the patient. And that's not a trivial exercise, but um there are many certainly not all but many diseases where the cause is actually very clear. The

</details>

<!-- chunk 4/13 -->

### 人工智能在药物发现中的杠杆效应

**Speaker A**: 最清楚的是单基因遗传病，但即使在其他疾病中，从各种检测组合中也能清楚地看到，这种过度表达、过度活跃或缺失的基因或蛋白质就是导致疾病的原因。因此，在疾病成因的整个宇宙中，我们已经了解了很多，但并不是全部。然后，一旦确定了靶点，我们就进入了为该靶点寻找药物的过程，理想情况下，这种药物要具有选择性，且非常强效。嗯，它能到达正确的组织。有些疾病是多系统的，有些则非常针对某个特定的器官或组织。你必须确保药物能到达那个组织。接着还有 GLP 毒理学实验和 IND 启用的过程。IND，即新药临床研究申请，你有……

<details>
<summary>Original English</summary>

**Speaker A**: most clear are the monogenetic diseases but even in others it's from various panels it's clear that this overexpressed or overactive or deleted gene or protein is causing the disease. So we know many but not all of the universe of causes of diseases. Then once a target is identified, we have the process of finding a drug for that target that's ideally selective, very potent. Um, it gets the right tissue. Some diseases are multi-system. Some are very specific to a certain organ or tissue. You want to make sure that drug can get that tissue. And then there is the process of GLP talks and IND enablement. IND investigational new drug you have

</details>

**Speaker B**: 这里的 GLP 指的不是好，不是……
我们说的不是良好实验室规范 (Good Laboratory Practices)。

<details>
<summary>Original English</summary>

**Speaker B**: >> GLP in this case is not good not not
>> we're not good lab practices

</details>

**Speaker A**: 谢谢。我们现在谈论的不是代谢领域。嗯，临床试验的规模通常是逐渐扩大的，一期临床通常更侧重于安全性，然后是二期和三期，就像你指出的，理想情况下是在任何监管机构，无论是 FDA 还是 EMA（欧洲药品管理局）等处获得批准。嗯，我们的观点是，人工智能杠杆率最高的应用领域是药物发现和药物设计过程。原因在于，尽管其他环节也都很有价值，我也为所有同行欢呼，其中很多人我都认识，他们活跃在这个技术栈的各个不同环节，但我认为首先要明确一点，就像视觉模型会与代码模型截然不同一样。它们在底层可能有一些相似之处，但要在任何一个领域做到正确，都需要真正的专注。嗯，对于你需要的不同模型来说，无论是用于靶点发现（即生物学），还是药物发现，或是为监管文件做准备，再到帮助为临床试验对患者进行细分，它们之间的差异即使不是更大，也是类似的。这些都是非常重要且互补的，但归根结底是不同的问题。嗯，我经常想到这样的场景：患者去看医生，被告知他们有一个非常明确的诊断。此外，医生还会告诉他们，我们在这个领域已经取得了突破，我们理解了这种疾病发生的原因。我们甚至已经对你的基因组进行了测序，或者对你的肿瘤进行了测序。我们知道是什么导致了你的病情，但我们没有选择性的靶向治疗方法。对于你的病情，目前没有精准医学疗法。虽然这给了人们一些希望，“至少他们知道我到底怎么了”，但他们确实不知道该怎么治疗。我们的目标是，尽可能多地创造这样的时刻：患者被告知他们有一种非常具体的疾病，而且有一种专门针对他们的治疗方法。这将需要降低发现和开发新药的成本曲线，但同样重要的是，要解决那些存在某些所谓的“不可成药”靶点、“不可成药”蛋白质的案例，我们需要弄清楚如何对这些靶点成药，这些靶点已经被证明对传统方法具有抗性，在某些情况下甚至是棘手的。

<details>
<summary>Original English</summary>

**Speaker A**: >> thank you we're not talking about the metabolic space right now um there's there's clinical trials usually ascending size phase one starts typically more more with safety um then phase two and phase three and and as you point out ideally approval at whatever regulatory body the FDA or EMDA or or what have you Um our contention is that the highest leveraged application of artificial intelligence is the drug discovery and drug design process. And the reasons are that even though they're they're all valuable and I cheer on all the peers, many of whom I know who are working at all the different parts of the stack, but I think the first thing to make clear is just like a a vision model is going to be very different than a coding model. They might share some similarities under the hood but requires real focus to do any one area correctly. Um there's a similar if not greater difference from the sort of models you need for target identification i.e. biology to drug discovery to preparing for regulatory filings to helping segment patients for clinical trials. These are all very important complimentary but ultimately distinct problems. Um, I think about all of the times where a patient goes to a doctor, gets told that they have a very clear diagnosis. And in addition, the physician will tell them there's been breakthroughs where we understand why this disease happens. We've sequenced your genome even. We we know or sequenced your tumor. We know it's causing your condition, but we do not have a selective therapy. There is no precision medicine for your condition and it has the hope that sol at least they know what's wrong with with me but they don't really know how to treat it and our aim is to um have as many moments as possible where patients are told they have a very specific condition and there's a specific treatment for them. That's going to require bending the cost curve of develop discovering developing new medicine, but also importantly solving those cases where there's certain quote undruggable targets, undruggable proteins that we need to figure out how to drug where those targets have have proven resistant to traditional methods or even intractable in some cases.

</details>

### 从药物发现到临床的断层

**Speaker B**: 为了澄清我的理解，有药物发现部分，然后有临床部分。因此，在这个过程中会有很多努力，比如：“好吧，我想找到对这种疾病影响最大的靶点是什么”，或者“也许我应该为了解决某个医疗问题而去寻找什么目标”。然后就是临床阶段，你需要回答“这个东西真的有效吗？”的问题。也许两者之间甚至还有一个反馈循环。但是，如果你中间缺失了那一环，即“好吧，我们到底要怎么把这个药造出来”，导致我无法击中我的靶点，或者它的选择性不够好，以至于它杀死了细胞，或者对细胞产生了我不希望它产生的作用。那前面的发现就不重要了，对吧？就像是我可能找到了答案，“这种药物应该针对这个靶点”，但是如果我不知道如何有效地、强效地做到这一点，那么这个答案就毫无意义了。你大概是这个意思吗？

<details>
<summary>Original English</summary>

**Speaker B**: Just to clarify my understanding, there's the discovery part and then there's the clinical part where and and so there's there can be effort there where okay, I want to find what's the target that is impacting this disease the most or how do I maybe what's the thing that I want to go after in order to solve a medical problem. And then there's the clinic where you're answering does this thing actually work? And maybe there's a feedback loop between them even. But if you don't have the thing in the middle that's like, "Okay, here's how we actually build this drug. It so that I can't hit my target. It's not selective enough so it like kills cells or does things to cells that I don't want it to do. So then it doesn't matter, right? Like I can have the answer, this drug should go after this target, but then if I don't know how to do that effectively, potently, etc., then then the answer doesn't matter. Is that kind of what you're saying?"

</details>

**Speaker A**: 是的，R.J.。因为人们喜欢争论临床试验中的成功率，但现实情况是，如果专注于那些靶向与疾病有密切遗传联系的蛋白质的候选药物，或者至少是生物学机制已经被充分理解、动物模型能很好地转化为人类疾病、分子被预测具有良好的药代动力学特性，且患者血液（血清）中的药物浓度足以达到标准的候选药物。这些分子在 FDA 的批准率其实是相当高的。从一期临床到三期临床结束的成功率要大大高于平均水平。人们喜欢引用 10% 的成功率，但这真的是被低估了。嗯，因为我们通常知道是哪些基因、哪些蛋白质、哪些靶点导致了疾病，它们只是真的很难成药，或者我们用于患者的分子，不如它们应有的目标产品特征 (Target Product Profile) 那般出色。在某些情况下，如果你只看临床前数据，专注于具有良好生物学特性的好靶点，这些靶点被预测会有良好的分布和良好的安全性，那么这些分子很有可能会获得批准，并为患者创造巨大的价值。所以我们的观点是，我一想到那些负责运行试验、迫切需要这类分子的医生，我一想到那些正在寻找更具选择性疗法的患者。我们的观点就是，这是人工智能在更广泛的医疗保健医学领域杠杆率最高的应用。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. R.J. if you because people love to debate about success rates in in clinical trials, but the reality is if one focuses on those drug candidates that are aimed at proteins that have a close genetic linkage to a disease andor at least where the biology is well understood, where the animal models translate well to the disease, where the molecule is predicted to have good phicinetics as and the levels in the blood in patients are in serum are going to be high enough. Those molecules have fairly high FDA approval rates. The success rate from fa phase 1 to end of phase 3 is substantially higher than average. People love to cite the 10% success rate, but that's really a low ball. Um because we often know what genes, what proteins, what targets are causing the disease. they're just really hard to drug or the molecules we put into in patients are inferior to the the the target product profile that that they deserve. In the cases where if you just look at the pre-clinical data, you focus on good targets with good biology that are predicted to be distributed well and have good safety profiles, those molecules are very likely to get approved and it create tremendous value for patients. And so our view is I think about the physicians that run trials that are clamoring for those kinds of molecules. I think about the patients that looking for more selective therapies. And so our view is that is the highest leverage application of AI in healthcare medicine more broadly.

</details>

### 容易靶点与困难靶点的辩证

**Speaker C**: 问一个商业问题。如果靶点是生物学机制已经弄清楚了，结构也理解了，你知道你真正需要做的就是找到合适的锁，这样的目标空间有多大？这听起来就像你们可能已经在某种程度上筛选过那一类靶点了，那些可以说是“容易的靶点”，对吧？那么，这里面到底还有多大的机会呢？

<details>
<summary>Original English</summary>

**Speaker C**: >> Just a business question here. What is the space of things which are that the target is the biology is understood, the structure is understood and that you know the only thing you really needed to do is find the right lock that seems like you probably would have already picked over that class of targets in some sense those are easy targets right so how how much is opportunity is there for that

</details>

**Speaker A**: 这其实是两个正交的概念：已知的生物学机制，与针对该靶点成药的难易程度是正交的。有时不幸的是，它们似乎是负相关的。因为通常从验证的角度来看，最吸引人的靶点往往真的很难成药。

<details>
<summary>Original English</summary>

**Speaker A**: >> so there's two orthogonal concepts known biology is orthogonal to the ease with which one can drug that target. Sometimes unfortunately it seems they anti-correlate in that often it seems that the most appealing targets from a a a validation perspective seem to be really hard to draw.

</details>

**Speaker C**: 不，但它们是真的负相关，还是仅仅因为我们已经摘光了所有同时满足这两个条件的“低垂的果实”？

<details>
<summary>Original English</summary>

**Speaker C**: >> No, but do they anti-correlate or is it just that we have picked all the low hanging fruit which do solve both those?

</details>

**Speaker A**: 我认为很可能是这种情况，许多所谓的“更容易的靶点”，由于种种原因，它们中的很多已经被开发成药了。并非全部，但即便在这些情况下，嗯，人们还是喜欢建立这种“容易靶点与困难靶点”的虚假二分法，认为“好吧，这个已经被成药了”，或者“它已经被筛选过了，因此不值得做了”。我们在 Genesis 的大部分工作是通过大型制药公司进行的，就像我们所做的大部分工作，基本上是为像吉利德 (Gilead) 这样的大型制药公司提供人工智能服务。我们最近宣布扩大了与 Incyte 的合作，对此我们感到非常兴奋。我无法透露他们正在研究的具体靶点的细节，但我可以说的是，从“首创 (first-in-class)”化学物质开始，这其中有很大范围的工作空间。这意味着，我们相信这个靶点会导致某种疾病，但目前没有已知的分子能与该靶点结合。我们需要找到有史以来的第一批结合物，这是真正的从 0 到 1 的案例。但是，嗯，我们研究的靶点种类繁多，我更愿意说那是从 1 到 10 的案例：有时那里已经有一种获批的药物，或者有时，嗯，那里只有临床前分子，但它们并不理想。如果你能改进这些临床前分子，并将它们推进到开发候选药物阶段，它们就准备好进入患者体内了；或者如果你能改进现有的临床或获批药物，你就能为患者创造很多价值。我举一个公开的例子。我们根本没有在研究这个靶点，但你只要看看 ALK 抑制剂的发展历程。为了让它非常具体，你可以看看患者生存率的图表。你可能会说，好吧，当第一个 ALK 抑制剂问世时，我们为什么还需要另一个？我们已经把 ALK 给拿下了。我们完事了。但这是一种定性的，而不仅仅是定量的差异。当你对比第一代 ALK 抑制剂和后代 ALK 抑制剂的患者生存曲线时，你会发现这些患者活得更长了，有更多的人从中受益。因此，我认为不仅在“首创 (first-in-class)”药物中有价值，“同类最佳 (best-in-class)”药物也能为患者带来巨大的价值。所以，我认为……

<details>
<summary>Original English</summary>

**Speaker A**: I I think it is likely the case that many of the quote easier targets >> for a variety of reasons have been sort of many of them have been drugged not all but even in those cases um people love to to sort of um have this this false dichotomy of easy versus hard targets and well this one's drugged versus it's picked over therefore it's not. We at at Genesis do most of our work through large pharma >> like most of what we do is providing AI services basically to to to to major pharma companies like like Gilead and we recently announced our our expansion of of our collaboration with insights which we're excited about and I can't give details of specific targets that they're working on but what I can say is there there's a real range from first-in-class chemical matter What that means is we believe this target causes a disease. There's no known molecules that bind to that target. We need to find the first binders ever, the true 0ero to one cases. But there's a um a wide variety of targets we work on that are more I'd say 1 to 10 cases where sometimes there's there is an approved agent or sometimes there um uh there's molecules that are only pre-clinical but they're not optimal where if you can improve upon those preclinical molecules and get them to development candidates they're ready to get into patients or if you can improve upon the existing clinical or approved agents you can create a lot of value for patients. I'll give an a public example. We're not working on this target at all, but you just look at the the progression of ALK inhibitors, ALK inhibitors, and you look at, to make it very concrete, charts of patient survival. You might have said, well, when the first ALK inhibitor came out, why do we need another? We've drugged ALC. We're done. But it is a qualitative, not just a quantitative difference. when you when you compare patient survival curves from first generation elk inhibitors to later generation elk inhibitors of how much longer those patients live, how many more get benefit from it. And so I think there's not only value in first in class, there's enormous value for patients in best-in-class too. And and I think

</details>

<!-- chunk 5/13 -->

### Genesis Modeling & Drug Discovery

**Speaker A**: 如果这说得通的话，这两个都是我们密切关注的核心领域。

<details>
<summary>Original English</summary>

**Speaker A**: both are areas that that we focus on if that makes sense.

</details>

**Speaker B**: 好的。是的。到目前为止，我们已经讨论了创世建模（genesis modeling），比如说蛋白质与配体结合（protein ligand binding）这个具体的科学问题。在开发这个技术的过程中，你们整体的运作模式是怎样的？我的意思是，我假设你们一定……我是说，我知道你们还在持续研究其他一些东西，以努力解决更广泛的早期药物发现（early phase drug discovery）面临的各种问题。我经常开玩笑说，当诺贝尔奖颁发给 AlphaFold 3 的时候，很多不明所以的人都认为药物发现这个难题已经被彻底解决了。

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Yeah. So we so far have talked about genesis modeling in terms of uh let's say this one specific problem of protein lian binding. How does your overall world work in terms of developing this? I mean I assume that you must I mean I do know that you have other things that you've worked on in solving the broader early phase drug discovery um problem. I keep joking about that when Nobel Prize was given for Alpha Fold 3, a lot of people thought that like drug discovery is soul

</details>

**Speaker A**: 而这距离真正的现实还差得很远，非常非常遥远。

<details>
<summary>Original English</summary>

**Speaker A**: and it's very far from the true um very far.

</details>

**Speaker B**: 是的，也许你们确实能够预测出晶体结构，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, you can maybe maybe so maybe you can predict crystal structure, right?

</details>

**Speaker A**: 仅仅是在较低的分辨率下。

<details>
<summary>Original English</summary>

**Speaker A**: At low resolution

</details>

**Speaker B**: 在较低的分辨率下。不过我认为我们现在显然做得更好了。

<details>
<summary>Original English</summary>

**Speaker B**: at low resolution. Well, we're we're doing better, I think.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yes.

</details>

**Speaker B**: 假设你真的能预测晶体结构，这是否就意味着药物发现的难题已经被彻底攻克了？不，显然没有。是的，更广泛的科学界，比如蛋白质折叠社区和药物发现社区，立刻就站出来说还有很多其他你需要去密切关心的事情，比如分子的动力学问题，仅仅拥有一个单一的静态结构是远远不足以理解相互作用中究竟正在发生什么复杂变化的。是的，所以除了仅仅获得一个静态结构之外，还有非常多其他需要深入考量的因素。我认为很多人理所当然地认为这些成果非常有用，它们确实也极大地加速了科学的整体发展，但非常明显的是，这仅仅只是一个全新的起点，而远非最终的终点状态。

<details>
<summary>Original English</summary>

**Speaker B**: Um assume you can predict crystal structure. Does it mean the drug discovery is solved? No, obviously not. Yeah, the broader community like protein folding community and drug discovery community immediately said there's other things you care about like dynamics like just a single static structure is not enough to understand what's going on interactions. Um yeah so there's lots of things there in addition to just like having a static structure I think many people thought those were very useful like they've really accelerated science but it was very clearly a starting point and not a in condition

</details>

**Speaker A**: 没错，但如果你去看看那些在这个专业领域之外的人，比如普通的大众群体，他们普遍都有一种非常狂野而广泛的信念，认为这个问题已经被完美解决了。

<details>
<summary>Original English</summary>

**Speaker A**: right but if you look outside of like people working in the field like general popular community it was a pretty wild wide belief that the problem is solved

</details>

**Speaker B**: 而在现实情况中，除了……

<details>
<summary>Original English</summary>

**Speaker B**: now in reality besides

</details>

**Speaker A**: 我必须马上澄清这一点，否则整个机器学习（ML）结构生物学社区都会立刻跳出来指责我们，大声说：“不，不，这根本不是一个已经被解决的问题。”

<details>
<summary>Original English</summary>

**Speaker A**: I just have to clarify that otherwise like there's an entire ML structure biology community will just jump on us and say like, "No, no, it's not a solve problem."

</details>

**Speaker B**: 确实必须要把这些严谨的注意事项（caveats）补充进去。

<details>
<summary>Original English</summary>

**Speaker B**: Got to got to throw those caveats in.

</details>

**Speaker A**: 绝对不是一个已经彻底解决的问题。

<details>
<summary>Original English</summary>

**Speaker A**: Absolutely not a solved problem.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 在残酷的现实中，你需要预测非常多其他的药物特性，比如我刚才还没有提到的 ADME（吸收、分布、代谢和排泄）等属性。基本上，这就好像是你正在为一把特定的锁精心设计一把钥匙，也就是那个在你的体内能够精准附着到你的目标蛋白质上的小分子。但是你绝对不希望这个小分子与你体内的所有东西都产生非特异性的结合，因为那很可能会引发各种严重的副作用问题。你还需要确保那个小分子是可溶的，这样你才能把它当成一种口服药丸顺利吞下去。这些也同样是极其重要的药物特性。你要确保它不会产生任何其他不良的副作用。所以，精准预测所有这些复杂的特性，与预测晶体结构本身同样重要，甚至可能比预测结构更加重要。当然，作为一家专注于此的公司——而且我们对此感到非常自豪——我们不仅仅是在构建用于预测晶体结构的单一模型。我们正在全力构建能够预测所有这些关键特性的综合模型，并且基本上旨在让药物研发人员（drug hunters）在他们的日常工作中能够将效率大幅度提升 100 倍。

<details>
<summary>Original English</summary>

**Speaker A**: In reality, you need to predict so many other properties uh like ad properties that I haven't mentioned. Like basically, you're designing a key for a log uh like that small molecule that sticks to your protein in the body. But you don't want this small molecule to stick to everything in your body cuz that's probably going to cause issues. You also want to make sure that small molecule can be sol like is soluble uh so that you can ingest it as a peel. Uh those are important properties too. You want to make sure it doesn't have any other side effects. Um and predicting all of those properties is also just as important as or maybe even more important than predicting the crystal structure itself. Um and of course as a company and we're very proud of it. Um we're not just building models for predicting crystal structure. we're building models for predicting all of those properties and basically enable drug hunters to kind of become 100x more effective uh in in their daily job.

</details>

### Pipeline & Pharma Partnerships

**Speaker B**: 我对你们所拥有的这种研发流程（pipeline）非常好奇。你刚才提到你们有许多不同的制药合作伙伴，比如 GSK（葛兰素史克）或者其他正与你们开展合作的公司。他们手中是否有一些由你们所设计的、目前已经顺利进入临床试验或者甚至已经获批的药物靶点？我们在这些方面的实际进展究竟已经到了什么程度？

<details>
<summary>Original English</summary>

**Speaker B**: I'm curious about this the pipeline that you have. You mentioned you have different pharma partners GSK or whomever you're working with. Do they have targets that were sort of drugs that were designed by you that are in like clinical trials approved? like where where do we stand with all that?

</details>

**Speaker A**: 由于制药公司向来以高度保密著称（这也是完全合乎商业逻辑的），我们在可以对外透露的具体内容上受到了极其严格的限制。我目前能够分享的一个最近已经公开披露的具体例子是，我们刚刚扩大了与 Incyte 公司的战略合作关系。我们最初的初步合作大约始于一年多以前，而且这在某种程度上跨越了药物发现漫长过程的首尾两端。因此，我们双方共同合作推进的项目之一是针对一个极具挑战性的高难度靶点。这个靶点已经存在一些已知的化学物质（chemical matter），但要实现从已知化合物到 DC（即开发候选物，Development Candidate）的艰难转化，是一个极其关键的二元事件。开发候选物是指一种极其特殊的分子，或者在最理想的情况下是一组分子，它们都有巨大的潜力成为第一期临床试验（phase one clinical trial）的有效活性药物。我们需要在一起开展大量深度的合作工作，利用我们强大的基础模型（foundational models），在 Incyte 公司独有的私有数据上对它们进行精心微调（fine-tune），并在极其紧密的协作中使用这些模型，共同努力以更快的速度获得开发候选物。在那个特定的高难度案例中，我们正在大幅度地接近最终的成功目标，这也是我们双方对进一步扩大合作关系感到无比兴奋的核心原因之一。

而在事情的另一方面，我们合作的另一个核心领域是集中研究一种与某种极其严重的疾病有密切直接关联的蛋白质，但在该领域目前尚无任何已知的化学物质可以有效作用于它。在这种艰难的情况下，没有任何相关的专利，没有公开发表的论文，也没有配体（结合到该蛋白质上的小分子的另一种同义专业说法）的共结晶结构（co-crystal structure）。因此，我们必须迎难而上，找到有史以来第一个已知的能与该蛋白质产生结合的化学物质，然后我们将这些在业内被称为“苗头化合物”（hits）的分子继续向前推进。苗头化合物就像是首批成功与你的目标蛋白质结合的分子。我们要将它们顺利推进，发展成为在生化检测（biochemical assays，这类检测更偏向基于纯化的酶）和细胞检测（cellular assays）中都具有显著活性的高强度抑制剂（inhibitors）。细胞检测意味着在一个真实的活细胞模型环境中，你的分子同样也是极其活跃且有效的。因此，这确实是完全基于我们共同取得的一系列非常具体的实质性成就，我们才非常渴望进一步扩大这种合作。然而，非常不幸的是，除了这些已经公开的信息之外，我们能对外透露的内情版本真的非常有限。但 Genesis 存在的终极客观目标是创造出患者梦寐以求的救命药物。我们能够做到这一点的重要方法，就是通过与尽可能多的一流制药和生物技术伙伴进行深度合作，他们的比较优势（comparative advantage）在于早期的实验发现、临床开发以及后期的商业化运作，而我们的比较优势当然毫无疑问是在人工智能（AI）领域。我们可以将这两种顶尖的专业知识以高度协同（synergistic）而非仅仅是简单相加（additive）的方式深度结合起来，共同制造出原本在常规路径下根本不可能出现的伟大药物。是的。所以，这就是我们积极参与这场游戏的真正核心目的，即你所明确指出的那些能够真正落地的临床结果。随着这些令人振奋的成果在未来几年内不断涌现，我感到非常高兴且迫不及待地能够与大家分享。

<details>
<summary>Original English</summary>

**Speaker A**: We're limited in what we can say about farmer companies are are famously secretive and which makes sense. What I can say which was recently publicly disclosed as an example um is um we just expanded our partnership with insights and that started approximately uh you know a little over a year ago the initial work together and that spanned the two sort of bookends of the drug discovery process in some way. So one of the the the programs we worked on together was a case where a very challenging target where chemical matter um existed but there's a key binary event which is getting to a DC or development candidate and that is the molecule or ideally a set of molecules all of which are possible to be um uh the agent for a phase one clinical trial and um we had to to do some work together where we we take our foundational models, our base models, we fine-tune them on insights data and use them in in a close collaboration to to sort of work together to to get to a DC faster. And we're getting um substantially closer in in that case, which is um one of the reasons we're excited to expand our work together. And on the the flip side of that is one of the other areas that work together was on a protein with also very nice linkage to a very severe disease where there was no known chemical matter like no patents no papers in this case no co-crystal structure of a liand another synonym for a small molecule that bound to that protein. So we had to find the first ever known chemical matter to bind to it and then we progress those what are called hits. Hits are like the first molecules that that bind your to your protein. Progress those into um inhibitors that are active in called biochemical assays which are more enzyme based and cellular assays which means that in a actual cell living cell model um your molecule is active as well. So it was really based on on on a concrete set of accomplishments together that we want to expand the collaboration and unfortunately outside of that there's really limited any versions of what we can say but um the objective of Genesis is to create medicines that patients wish they had. And the way we'll be able to do that is by working with as many pharma and biotech partners as possible for whom their comparative advantage is discovery, clinical development, commercialization and our comparative advantage of course is in AI where where we can put those those two expertises together in in a synergistic not just an additive way and and make medicines together that otherwise would would not be possible. Yeah. Um, so that's the name of the game that we're in this for is those those clinical outcomes that you're pointing out and I'm very excited to be able to share those um as as they rise in the coming years.

</details>

### Accuracy & Downstream Impact

**Speaker B**: 所以，你们在公司网站等公共平台上经常提到的一件非常重要的事情是“一埃（1 angstrom）阈值”，只有在这个极高的精度标准下，蛋白质结构的预测以及它与小分子之间结合模式的预测才会真正变得有用。你能不能详细谈谈，为什么会这样？在其他人都彻底失败的时候，你们究竟是怎么做到这一点的？你之前也稍微提到过相关的内容，比如模型中固有的偏差、用于训练的合成数据，或许还有更多复杂的技术因素。这又是如何切实影响我们刚才讨论的那些下游实际应用环节的，比如 ADMET 分析以及所有那些极其重要的东西？

<details>
<summary>Original English</summary>

**Speaker B**: So one thing that is you guys talk about in your website and whatever is this one angstrom threshold at which a protein structure prediction and the binding between that and a small molecule becomes useful. Can you talk a little bit about like okay why is that the case? what how did you do it when others have failed and you know and you've spoken a little bit about that with the you know sort of biases in the model the synthetic data maybe there's more how does that impact you know sort of downstream the actual things that we're talking about here with um you know uh the admat and all that stuff

</details>

**Speaker A**: 当我们真正在谈论分子级别的相互作用时，人们通常习惯于测量的两埃（2 angstroms）的尺度实在是太大了。你可以想象这样一个场景，在图像生成模型（image generation model）中，你生成了一张图片，而它整体看起来是模糊不清的。

<details>
<summary>Original English</summary>

**Speaker A**: when we're talking about molecular interaction the scale of two anstrom that people typically measured is just too big So you can think about like in image generation model you would generate a picture and it's like fuzzy.

</details>

**Speaker B**: 所以，是的，大体上看起来是对的，但你完全无法分辨其中的细微细节，而细节在这里恰恰是决定成败的关键。比如，在两埃的糟糕精度下，你整个芳香环（aromatic ring）都可能发生了 180 度的翻转，但它在模型眼里仍然会被认为是一个完全有效的输出结果。最糟糕的部分在于，它不像一张肉眼可见模糊的图片那样容易识别，你甚至根本不知道它是模糊或错误的，对吧？你随便翻转了一个芳香环，它看起来依然非常正常。而且……

<details>
<summary>Original English</summary>

**Speaker B**: So yeah it's like in general right but you can't discern the details and the details really matter here like with two anstrom accuracy your entire aromatic ring can be flipped and it will still be uh a valid uh output. The worst part is that unlike an image which is blurry, uh you you know you don't even know it's blurry, right? You flip you flip around an aromatic ring and it looks just fine. And

</details>

**Speaker A**: 是的，或者情况甚至会更糟，一个杂环芳香环（heterocyclic aromatic ring）发生了翻转，那你就真的陷入大麻烦了。

<details>
<summary>Original English</summary>

**Speaker A**: yeah, or even worse, a heteroscyclic aromatic ring and then you're really in trouble.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 在这种分子层面的情况下，这真的至关重要，因为这里的各个独立的原子之间需要极其精确地建立化学连接。因此，我们所执着追求的一埃这种极高水平的精确度，真的是极其重要的。这可能就像许多主流的生成式图像模型一样，它们会凭空填补（hallucinate）一些根本不存在的细节。这就好比你在做专业的刑侦鉴定工作，你指示你的视觉 Transformer（Vision Transformer）去强行增强一张极其模糊的图片，突然它就清晰地弹出了一张脸，但这实际上根本不是那个嫌疑人的真实面貌，对吧？但你并不知道这其中存在虚构的成分，而且感觉一切都很正常。所以，如果你作为一名严谨的药物化学家，试图将这种虚假的结果用作关键的结构假设，那你就彻底完蛋了。如果你作为一名调查员正盯着一张完全错误的脸看，那是绝对行不通的……是的。

<details>
<summary>Original English</summary>

**Speaker A**: And it really matters in this case because like individual atoms need to establish connections here. Um so that level of accuracy what we're pushing for uh one anstrom is really important. So maybe it's almost like with a lot of generative image models, they will fill in a detail which just doesn't exist. So if you were to try to do like forensics and you tell, you know, your your vision transformer to to to enhance an image and suddenly it just pops up a face, but that's actually not the person's face, right? But like you don't know that and it feels just fine. And so if you're trying to use this as a structural hypothesis, as a med chemist, you're kind of screwed. If you're looking at the wrong face as an investigator, it's it's not going to take Yeah.

</details>

**Speaker B**: 是的，我非常喜欢你的这个生动的比喻。然后就像 Evan 之前所说的那样，在整个流程的下游环节，你会继续运行一大堆其他的预测模型，比如那些基于严谨物理规律的模型，所有那些上游微小的问题都会像滚雪球一样复合叠加（compound）。显然，如果你在起步阶段就做出了完全错误的预测，比如那种根本性的致命错误，那么所有的下游预测也注定将会是错得离谱的。我只是……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I really like your framing. And then as Evan said at like as a downstream, you run a bunch of other models like physics based models and all of those little issues, they compound uh and then obviously if you made the wrong prediction like fundamentally wrong, then the downstream predictions are also going to be wrong. I just

</details>

<!-- chunk 6/13 -->

### 关于分子姿态(Pose)的争议与真实性

**Speaker A**: 回答你的问题之前，我非常喜欢你提到的关于2000年代中期电视节目里增强法医图像的梗。所以，我只想说我很欣赏这一点。在回到细节之前，

<details>
<summary>Original English</summary>

**Speaker A**: wanted to say for your question, I really appreciate your mid2000s TV reference about, you know, enhancing forensic images. So, I just want to say I appreciate that. Before we get back into back into details here,

</details>

**Speaker B**: 我们讨论过分子姿态(poses)。那么，也许一种唱反调的观点是，姿态甚至不是一个定义明确的概念，而且，你知道，思考这些事情的最好方法就像，你知道，事物上的概率分布。有一个小分子，它可能存在于一个结合口袋中，就像这样。我的意思是，像这样的姿态是不是一种人类使用的抽象概念，而不是某种意义上的真实情况。所以我实际上几乎有点想听听，就像，哦，我们有这个警告阈值。这对药物化学家来说非常重要。我也会和一些化学家交流，他们会说，我的意思是，这个姿态甚至不是真实的。相比于可能只是一个最可能的构象，或者你知道你总体上如何看待这种抽象概念，以及你是否探索构象空间并将其作为工具提供，是的，你如何处理只是一个单一结构而不是一个系综，抱歉，我不知道这个问题是否有意义。

<details>
<summary>Original English</summary>

**Speaker B**: we talked about poses. So, maybe the the contrarian take is that a pose isn't even a well-definfined concept and that, you know, the best way of thinking about these things is this like, you know, probability distribution over things. And there's a small molecule which probably lives in a binding pocket something like this. I mean is is this pose like this is an abstraction that humans use and not really in some sense ground truth. So I'm actually almost kind of interested to actually hear that like oh we have this warning threshold. This is like really important for med chemists. I would also talk to some chemists would say I mean this pose isn't even real. versus just like maybe a most probable configuration or you know how do you think about that abstraction in general and do you ex do you explore confirmational space and provide that as tools and yeah how how do you interact with just like a single structure versus like an ensemble and sorry and I don't know if that question even makes sense then

</details>

**Speaker C**: 是的，它是一种抽象，但它是一种非常有用的抽象，它帮助我们建立信心，即特定的模型输出实际上是有效的。嗯。

<details>
<summary>Original English</summary>

**Speaker C**: yes it's an abstraction but it's a very useful obstruction it helps us to build up confidence that a particular model output is actually valid Mhm.

</details>

**Speaker C**: 呃，但是你并没有直接凭空捏造出一些东西。因为是的，最终重要的是结合亲和力或效力，你可以直接用你的模型预测它，并直接跳过整个姿态生成步骤。

<details>
<summary>Original English</summary>

**Speaker C**: Uh but you did not just straight up hallucinated something cuz yes ultimately what matters is binding affinity or potency and you can straight up predict that with your model and just skip the entire post generation step.

</details>

**Speaker C**: 但是那样你就只有一个单一的数字，而那个数字也可能完全是幻觉产生的，你没有任何手段来验证那个数字是否有任何意义。所以，尽管姿态并不完美，它们仍然是整个过程中非常有用的工具。

<details>
<summary>Original English</summary>

**Speaker C**: But then you only have a single number and that number might as well be completely hallucinated and you have no means to validate whether that number even makes any sense. So, as much as poses are not perfect, they're still a very useful tool uh for the entire process.

</details>

**Speaker B**: 抱歉，进入那个修正。嗯，你知道，只是我有点担心我在这里陷入了一个技术陷阱，但是，呃，但是就像，仅仅因为你有一个姿态，我的意思是，还有熵和焓的贡献，预测结合亲和力不仅仅是得到正确的能量，而且实际上是，它甚至有可能进入结合口袋吗？它喜欢长期留在那里吗？所以它不仅仅是，你知道，亲和力或效力预测，不仅仅是，这是正确的姿态吗？而且它是否具备在这种状态下成为长寿分子所需的更广泛的特性？你们又如何处理这些事情呢？

<details>
<summary>Original English</summary>

**Speaker B**: Sorry, going into that correction. Um, you know, just I'm afraid I'm jumping into a technical rabbit hole here, but um but like the just because you have a pose also, I mean, there's like entropic and anthropic contributions and predicting binding affinity is not just about getting the energy right, but actually is this even likely to make it into the binding pocket and is it like to live there long term? So it's much more than just you know affinity potency prediction is much more than just is this the right pose but does this have the broader properties it needs to be a longived molecule in this state and how do you kind of deal with those things too

</details>

### AI Agent 在药物发现中的应用与挑战

**Speaker D**: 对广泛的 AI 受众来说，有一个可能会在从业者和用户中产生共鸣的点是，嗯，你知道，显然在过去六个月里蓬勃发展的一件事是智能体(agents)。嗯，我们喜欢智能体。

<details>
<summary>Original English</summary>

**Speaker D**: a note for sort of the the wider AI audience that probably resonate both both with practitioners as well as users is um you know obviously something that's blossomed in the in the past six months is agents. Um, and we love agents.

</details>

**Speaker B**: 谁不喜欢呢？

<details>
<summary>Original English</summary>

**Speaker B**: Who doesn't?

</details>

**Speaker D**: 有很多，我要说几个必要但不充分的条件。如果你真的在问一个有深度的问题，我的回答是。我们都记得，比方说，去年年中时智能体是什么样的。只能说，有正面的价值，也有负面的价值。而智能体可以放大这两种价值。为什么会这样？嗯，智能体的有用程度仅仅取决于它们所编排的底层模型。让我们想想写代码。如果你的代码模型甚至会犯一些微妙但确实存在的错误，你的智能体只会放大这些问题，最终你得到的不仅是垃圾(slop)，甚至可能是起反作用的，可能会给用户不正确的信息。我们都记得去年年中那个时代是什么样的，当时，我想说，关于将大语言模型(LLMs)用于智能体工程的主张，让很多人失去了耐心。但是有些事情发生了改变，显然达到并跨越了一个阈值，尽管这些模型仍然不完美，但大语言模型在软件工程中的效用现在已经非常明显。我的意思是，显然这对我们来说是一股巨大的顺风，非常有用，嗯，可以取代许多枯燥的编码工作，并让注意力稍微集中在一些更具战略意义、更重要的问题上。你可以直接将其类比到我们在这里讨论的事情上，因为，嗯，我们显然，这不足为奇，但我们正在开发一个用于 24/7 药物发现的智能体平台。你可以想象，成百上千的药物化学家和计算机辅助设计(CAD)科学家组成的车队，夜以继日、周末无休地为你的药物靶点工作。嗯，那个项目的代号是 Sapphire（蓝宝石）。它的先决条件是，我们需要在姿态(pose)、3D、3D 复合物预测、效力、ADME（吸收、分布、代谢、排泄）方面的底层模型都足够好，足以让一个 24/7 使用这些模型的智能体创造出药物化学家实际上想要制造而不是嘲笑的分子。如果你的模型均方根误差(RMSD)停留在 1.8、1.9 埃，那很可能就是垃圾。让我非常直接地说，你所听到的，你从人们那里听到了关于 3D 姿态的效用及其真实性的双峰分布。现实情况是，对于一种高活性的配体，几乎可以肯定该分子的很大一部分具有非常明确的 3D 位置，甚至精确到半埃。如果你不相信我，你可以打开 PDB（蛋白质数据库）中的电子密度图。这些都在网上可以查到，你可以，你可以字面上看到在某些情况下，芳香环中间缺乏密度。所以这不仅仅是你的有机化学教授展示给你的黑板上的一个构造。它是，你可以直观地看到一个甜甜圈，一个芳香环的电子密度环面。然而，通常会有一些溶剂暴露的区域，这些区域对于结合亲和力可能不太重要，但可能对分子的溶解度或其他特性很重要。这些区域有时不太明确，因为有时在现实中，正如你所说，它们更具动态性。它们在溶剂中翻滚。但作为一个有价值的、用于预测结合自由能的上游指标，关键是让你分子中特异性与蛋白质相互作用的核心部分精确到亚埃的分辨率。为什么这很重要，只是直观地解释一下？所以氢键，听众中的每个人可能都听说过氢键。它是非共价相互作用中最关键的形式。它是核酸结合在一起的方式。它是大多数配体和蛋白质相互作用的方式。它是蛋白质形成二级结构的方式。氢键有一个非常特定的角度和距离。距离是从供体到受体重原子的距离。它是 2.7 埃到 3.3 埃。如果我数学没算错的话，那是一个 0.6 埃的差距。嗯，在这个范围之外，它就不是氢键。如果小于这个值，它就是一个空间冲突。如果大于这个值，嗯，相互作用很快就会变得非常弱。对于不知道的人来说，一埃是十分之一纳米。所以药物发现真的是一门关于分辨率的科学。如果你的，嗯，精度不够，它因此就不会对你关心的下游事情有用，这既包括效力预测，也包括前瞻性设计。我接下来该制造什么分子？嗯，所以这就是为什么我们的观点是，初创企业创新的历史表明，做得最好的初创企业是那些专注于一个明确但非常重要的问题的企业。我们认为我们能够获得更高分辨率预测的能力源于我们明智地专注于中小型分子设计，而不是试图解决所有问题（boiling the ocean）。

<details>
<summary>Original English</summary>

**Speaker D**: It's there's a lot of I'm going to say a few necessary but not sufficient conditions. I'd say in and my my sort of response if you're really a deep question there. We all remember what agents were like, let's say midl last year. And let's just say there is positive value and there's negative value. And both can be amplified by agents. And why is that? Well, agents are only as useful as the underlying models that they're orchestrating. And let's think about coding. If your coding model even makes subtle but but real bugs, your agents are just going to amplify those issues and you're going to end up with not only slop but something that that may be anti-useful that might give the user incorrect information. We all remember what that what that age was like mid last year that made a lot of people lose patience I would say with claims about LLMs for for agent engineering. something changed like clearly a threshold was was was was met and even though these models are still not perfect the utility of LMS for software engineering are so obvious now I mean obviously it's been a huge tailwind and very useful for us um for for replacing a lot of the drudgery of coding and getting it focused a little bit more on some of the the more strategic um uh issues that matter. You could draw a direct analogy from that to what we're talking about here in that um we obviously no it will be no surprise but we're working on an agentic platform for 247 drug discovery. You can imagine just fleets of hundreds of medchemists and CAD scientists working nights and weekends all the time for for your drug targets. Um the the the code name for that gem is Sapphire. The prerequisite for that was we needed the underlying models for pose 3D 3D complex prediction potency ad me to all be good enough for an agent using these models 24/7 to create molecules that medicinal chemists would actually want to make and not laugh at. And if your model is sitting at 1.8 8 1.9 RMSD that's slop most likely and let me be really direct about it what you're hearing so you're hearing biodal distribution from people of the utility of a 3D pose and how real it is the reality is that for a highly potent liant almost certainly there is a large portion of that molecule with a very well-definfined 3D position down to even half an And if you don't believe me, you can open up the electron density diagram in the PDB. It's all available online and you can you can literally see in some cases aromatic rings with missing density in the middle. So it's not just a construct on a blackboard that your organic chemistry professor showed you. It is you can literally see a donut, a Taurus of electron density for an aromatic ring. However, there's going to be solvent exposed areas often times that will be less important for binding affinity but maybe are important for solubility or or other properties of your molecule. Those sometimes are less defined because sometimes in reality to your point they're more dynamic. They're flopping around in solvent. But the critical piece as a as a upstream indicator that's valuable for predicting the free energy of binding is to get the core of your molecule that specifically interacts with the protein to be correct to subunctum resolution. And why does this matter just to use it intuitively? So a hydrogen bond everyone in the audience has probably heard about a hydrogen bond. It's the most critical forms of non-coovalent interactions. It's how nucleic acids are held together. It's how most lians and proteins interact. It's how proteins form secondary structures. Hydrogen bonds have a very specific angle and distance. And the distance is from the donor to the acceptor heavy atom. It's 2.7 anstroms to 3.3 enstros. And if I do my math right, that's a 0.6 enstrom gap. Um, and outside of that, it's not a hydrogen bond. If it's less than that, it's a clash. If it's more than that, um the interaction is is much much weaker pretty quickly. And anstrom for those who don't know is onetenth of an nimeter. So drug discovery really is a science of resolution. And if your um accuracy is not sufficient, it will therefore not be useful for the downstream things that you care about, which is both potency prediction but also prospective design. what molecule do I make next? Um, so that that's why our view is that the history of innovation in startups is that the ones that do best are ones that focus on one well-defined but very important problem. And we think our ability to get higher resolution predictions stems from our judicious focus on small mediumsiz molecule design rather than boiling the ocean.

</details>

### 如何达到亚埃级精度

**Speaker B**: 是的。所以这就是“是什么”和“为什么”。那么，“怎么做”呢？你是如何达到一埃以及亚埃级别的精度的？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So that's the what and the why. So what what about the how how did you get to one angstrom and sub one angstrom?

</details>

**Speaker D**: 我将给你一个非常无聊的答案。

<details>
<summary>Original English</summary>

**Speaker D**: I'm going to give you an extremely boring answer.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker D**: 呃，我认为这对整个 AI 领域来说其实是真的，在 AI 领域有三件事最重要。呃，那就是数据、基础设施和评估(evals)。

<details>
<summary>Original English</summary>

**Speaker D**: Uh which I think is actually true for entire AI field like where three things matter in AI. Uh it's data infrastructure and evolves.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker D**: 对吧。所以你只能改进你所测量的东西，一旦你非常仔细地衡量重要的事情，并且团队中有非常有才华的人，我们就会弄清楚如何爬坡(hill climb)提升那个指标，对吧。

<details>
<summary>Original English</summary>

**Speaker D**: Right. So you can only improve what you measure and once you are very careful about measuring what matters and you have really talented people on the team we're going to figure out how to heal climb that measure right.

</details>

**Speaker D**: 所以从一开始，我们实际上就专注于小于一埃的精度，这导致了在这个过程中许多微小决策的复合。对吧？如果你的团队根本不关注这个指标，那么你将永远不会训练出一个在这方面表现出色的模型。如果你一直在关注它，那么你就会

<details>
<summary>Original English</summary>

**Speaker D**: So from the start we actually focused on less one one anstrom precision and that led to a bunch of small decisions in the process that compound. Right? If your team never looks into this metric at all, then you will never train a model that if it's good at it. And if you're constantly looking into that, then you're going to

</details>

<!-- chunk 7/13 -->

### 确立正确的基准与制药领域的失败模式

**Evan**: ……实现那个目标。所以，这需要正确的目标加上优秀的科学方法，而且它会贯穿到所有地方，对吧？贯穿整个技术栈。它会影响你如何审视数据，比如我们该如何过滤数据。有些数据噪音较大，所以我们可能不需要看它，或者在训练的后期你不需要再看它。它会贯穿你的建模架构，并贯穿你的损失函数。

<details>
<summary>Original English</summary>

**Evan**: achieve that. So it's the right objective plus good science and and it propagates everywhere, right, through the whole stack. It propagates to how you look at the data maybe like how do we filter out data. Some data is more noisy. So maybe we don't need to see it or maybe you don't need to see it later in the training. It propagates through your modeling architecture and propagates through your loss.

</details>

**Interviewer**: 你们朝着这个特定目标努力了多久？我很好奇，因为这并不是你在社区中常听人们说他们想要的东西。大家确实会说，决定将一埃（1 Angstrom）作为某种标准基准，但在看到 Genesis 发布的内容之前，我从未听过有人说 1 埃才是及格线。你们决定“这才是我们需要攀登的数值”有多久了？这种聚焦在公司的发展过程中有多直接？我只是很好奇，这是怎么产生的？

<details>
<summary>Original English</summary>

**Interviewer**: How long have you been working towards this specific goal? I I'm curious this is not something that you broadly hear in the the community talk about wanting. People do say to have decided to Instrom is sort of the canonical benchmark and I've never heard someone say one before is the cuto off until like reading things coming out of Genesis. How long have you decided this is the number we need to to hill climb on? How direct has this focus been and in like the evolution of the company? I'm I'm just wondering like how did this come about?

</details>

**Evan**: 我认为我们最重要的秘诀之一就是，我们在做真正的药物研发项目——无论是与合作伙伴一起还是在内部进行。当你真正去推进真实的药物研发项目时，你会看到那些失败模式，你会看到什么管用、什么不管用。当你看着真实项目的输出结果时，发生着什么样的失败模式就会变得非常明显。很显然，2 埃（2 Angstrom）在这些情况下根本就行不通，对吧？

<details>
<summary>Original English</summary>

**Evan**: I think one of our most important secret is that we are working on real drug programs either with partners or in house. And when you actually work on real drug programs, you see the failure modes, you see what works and what doesn't work. And it's pretty obvious when you see at the outputs of real programs, what what kind of failure modes are happening. And it becomes very obvious that Tongstrom is just not working out uh for those setups, right?

</details>

**Interviewer**: 但我的意思是，有很多非常聪明的药物化学家，他们同样会非常认真地思考基准测试，其中有一些我非常尊敬的人，他们也曾推进过实际的药物研发项目。所以我只是有点好奇，为什么这没有成为社区共识的一部分？这真的只是因为社区从来没能成功达成一个制胜的基准，以至于大家只能将其搁置并认为“好吧，这是我们可以向往的东西，或者我不确定”？不过说到你的观点，听起来似乎是这样的：根据我在制药行业的经验，有很多问题在某个子领域的专家中已经是心照不宣的事实了，但这些信息却没有传出制药界，或者没有得到应有的关注。因为，你知道的，不管什么原因，或者一些信息是专有的，只在公司之间传递，却从未真正向公众发布过。这是你对正在发生的事情的评估吗？

<details>
<summary>Original English</summary>

**Interviewer**: But I mean there's a lot of really smart med chemists who are also, you know, who think very carefully about benchmarks and people I I respect very much and who also have prosecuted actual drug discovery programs. So I'm I know I'm just kind of curious like why hasn't this become part of the community? Is this literally just that the community has never been able to succeed at a winning benchmark? that I kind of settled it too as a okay it's something we can aspire to or I and I I don't know just but I mean to your point it sounds like there's a in my experience with pharma there are plenty of problems for which people there's kind of these known things amongst the technical experts in a subdomain and it but that it doesn't get out of pharma or it doesn't get the attention it deserves because uh you know for whatever or some of the information is proprietary and gets kind of passed from company to company but never really released into the public. Is this your estimation of what's going on?

</details>

### 学界基准的演变与评价危机

**Sergey**: 你听说过 SWE-bench 吗？比如，Gemini 在 SWE-bench 上表现相当不错。有时 Gemini 发布的模型在某些软件基准测试上会获胜。在座的各位，如果你们现在正在使用 Gemini 来编写代码，而不是用，你知道的，其他名字显而易见的竞争对手的产品，请举手。

<details>
<summary>Original English</summary>

**Sergey**: Have you ever heard of SWEBench says so? Um, Gemini does pretty well in SweetBench. Sometimes Gemini publishes models that win on some of those software benchmarks. Raise your hand if you're using Gemini to write code right now instead of, you know, the obvious other name competitors. 

</details>

**Interviewer**: 没举手，不是我。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Not me. 

</details>

**Sergey**: 没有人。就是说，为什么你要那么做呢？在实际操作中，它显然更差一些。而且我想说，实际上在这个案例中，如果你看看它发生的过程来源，RMSD（均方根偏差）小于 2 的标准最初也来自于此。在 AI 用于姿态预测模型出现之前的很久，我就一直在这个领域做分子对接研究。当时，由于通常那些大型的专有软件开发商不想让他们的算法与其他方法进行对标基准测试，所以学术界的机构如果要用基于物理的分子对接研究，学者们必须获取许可证并进行尝试，然后他们就会引入 RMSD 小于 2 的标准。这并不奇怪，他们是学者，他们不使用这些东西来制造药物。他们使用它是为了写论文。所以起源就在于此，它不知怎么就被 AI 社区重新采纳了。但实际的趋势其实更倾向于我们所说的方向。因此，那里出现的第一个重大创新是我们会提到的 PoseBusters，它是由牛津大学的一个实验室发布的，该研究指出 RMSD 本身是不够的，我们还需要关注物理上的有效性。这就是 PoseBusters，我谈论的不是那个基准测试数据集，而是那个评估指标。所以，牛津大学改进了这一点，在 OpenBinds 的最新发布中，我们刚刚基于 OpenBinds 数据集发布了我们在 Genesis 的基准测试结果。

<details>
<summary>Original English</summary>

**Sergey**: No one. like why would you do that? It's it's obviously worse in in practice. Um and I I'd say actually that in this case if you look at the providence here of how that happened RMSD less than two came originally from again B and I've been in the space forever from docking studies long before AI models for post prediction when physics based docking studies from academic institutions because usually large you the proprietary software makers they didn't want to benchmark their methods against other methods so academics had to get licenses and try it and then they'd introduce pharmacy lesson too, which is not surprising. They're academics. They're not using these things to make drugs. They're they're using it to to to write papers. And so that got sort of the provenence is that that kind of got repurposed by the AI community. But the actual trend is much more in the direction that we're saying. So the first um uh big innovation there was was posebusters we'd say uh put out by uh a lab at University of Oxford which which pointed out that RMSD itself is insufficient and we need to look at physical validity as well. Uh so that's posebuster is I'm talking about not the benchmark but the metric. So, so Oxford improved that and in the latest release from openbind, we just published our benchmarks at Genesis on open bind set. 

</details>

**Sergey**: 我们稍后会详细谈论那个。我们计划要谈，但如果你去看看他们最初的出版物，他们的默认评估指标就是使用 RMSD、PoseBusters 的物理有效性以及 LDDT。所以，这显然已经表明了一种共识：大家已经承认 RMSD 小于 2 是不够的，而且该领域现在正在迅速演进以认可这一点。

<details>
<summary>Original English</summary>

**Sergey**: We'll talk about that in a bit. We plan on but if you look in in their you know that's their original publication their default metrics are using RMSD pose busters validity and LDDT. So there's clearly an acknowledgement that's already been made that RMSD lesson 2 is insufficient and the field is now rapidly evolving to acknowledge that.

</details>

### 从图网络到生成式模型：走向 ADMET 预测

**Interviewer**: 你认为学术文献会建立某种基准吗？也许是 1 埃，也许是某种 LDDT，或者是一些其他的指标，它最终会趋于收敛，然后希望作为整个社区，去推动这些更准确的建模策略向前发展。我会说在我们的领域曾经出现过一场评估危机，而现在正在经历过渡期，因为我们以前的领域，可以说要安静得多，但如果你年复一年地去参加 NeurIPS 和 ICML，研讨会变得越来越拥挤，既然我们意识到了以前那些东西的缺陷，那么这些评估方法现在也处于转型期了。那是一个非常有趣的观点，你知道的，选择正确的评估指标，然后就像你平时做的那样，去做好的机器学习。但是我有点留意到 Evan 早些时候说的一些话，那就是你们最初使用的是，我猜我们称之为 PotentialNet。我不认为我们早先定义过那个，但你知道的，这个基于图的网络，然后你们在那之后做了大量的计算模拟，现在随着生成式模型的起飞，你们又某种程度上重新回归到计算中。我很好奇这种演变是如何进行的，以及在一段时间内，你们是如何发现计算技术对构建在机器学习之上至关重要的？这种计算是否又导向了生成式模型，或者你们是否开始收集数据以构建一个生成式计算数据的方法？这就像是生成式模型的数据文档一样。那段历史大概是怎样的，又是什么导致了那些决定，在你可以谈论的范围内？

<details>
<summary>Original English</summary>

**Interviewer**: You think that the academic literature is going to establish some some benchmark maybe it's one instro maybe it's some LDD or some other metric that will kind of converge and then hopefully as a community drive forward these like more accurate model modeling strategies. I would say there was an eval crisis in our field that is now in transition right now as our field which was previously let's say a lot more quiet but if you go to nurips and ICML every year year after year the workshops get a lot more crowded those evals are are in transition now that we realize the um flaws of the of what came before it. That was a really interesting point about, you know, pick the right emails and then just do good machine learning like you normally would do. But I I kind of picked up on something Evan said earlier, which is that you started out with, I guess, what we call potential net. I don't think we you defined that earlier, but you know, this graph-based network and then you did a lot of computational simulations kind of after that and now you're sort of going back into now once generative modeling took off. I'm curious about how that evolution worked and how did you find computational techniques to be like really crucial to sort of building on the ML for a while and did did that that sort of computation lead back into generative or did you start collecting data to build a generative computational data is like this is a way of data documentation for generative model like what's sort of the history of that and then what led to those decisions to the extent you can talk about 

</details>

**Evan**: 我得说，我写的最后一行 PyTorch 代码在历史上要比 Sergey 提交的最近一行 PyTorch 代码久远得多。所以我希望确保他也能给出他的看法。嗯，我想确保我能直接回答你的问题。我想确保我回应了你刚才说的一点，我感觉那一点似乎有点被忽略了，那就是你问到我们是如何进行其他工作的，包括 ADME 预测。所以，我只是想对此做个评论。我可以花上一整天的时间，而且我也很乐意深入探讨关于 PR 技术的细节及其演变，我们稍后会这么做的。嗯，我只是想稍微强调一下这样一个事实：它（对接或姿态预测）是一个重要的支柱，但在药物发现活动的发展轨迹中，它并不是唯一重要的支柱。你提到了那篇关于 PotentialNet 的论文，我们很高兴看到自打你和我们在那个领域工作时起，那篇论文已经变得很有影响力，因为那时它还可以说是非常属于未来的事物，但现在它已经成为了现实的未来。所以这很棒。我们在大约同一时间发表的另一篇论文是关于用于 ADME 预测的神经网络的。实际上我们发表了两篇，ADMET，你能解释一下吗……

<details>
<summary>Original English</summary>

**Evan**: I will say that the last line of of pietorrch I've written is much further back in history than the most recent line of pietorrch that Sergey has committed. So I I want to make sure that he gives his his opinion as well. Um I want to make sure that um I'm going to directly answer your question. I want to make sure that I address something you said like a little bit of time ago that I think kind of got lost which is you asked about how we do other things including ad prediction. So, I just want to make a comment about that. Just I I can spend all day and I'm happy to diving in details about about Pearl and the evolution and and we will. Um, I just kind of want to give it a shout out to the fact that it is one important pillar but not the only pillar that matters in the trajectory of a drug discovery campaign. And you mentioned that potential net paper which we're happy to see had been become influential since you and I were working in the space when it was very much in the future let's say but now we now it is the future so it's great another paper we published around the same time um was on um neural networks for adne prediction and we published two actually admat can you 

</details>

**Sergey**: 哦，抱歉，谢谢你，是的。吸收（Absorption）、分布（Distribution）、代谢（Metabolism）、排泄（Elimination）和毒性（Toxicity），这五个方面构成了 ADMET。

<details>
<summary>Original English</summary>

**Sergey**: oh sorry thank you yeah um absorption distribution metabolism elimination and toxicity are the five prongs that comprise admit. 

</details>

**Interviewer**: 这些就是你之前谈到的所有属性，为了使一种药物获得成功，你必须把这些性质弄对。

<details>
<summary>Original English</summary>

**Interviewer**: These are all the properties you talked about before that you just have to get right in order to make a drug successful. 

</details>

**Sergey**: 没错。所以我得说大约有 30 多种检测，你可以想象一下，如果你是一个搞神经网络的人，比如训练一个多任务神经网络或者多头网络，它必须预测 30 多个，你知道的，大约三打左右的属性，如果其中任何一个在错误的范围内，那就意味着你的分子不是药物，它只是一个工具化合物。这些属性包括溶解度，这就像 Sergey 提到的那样，对制剂很重要，也就是说它能否被制成你可以口服的药片。还有你的口服生物利用度，以及你是否正在抑制某些特定的酶，比如被称为细胞色素 P450 的酶及其不同的变体。还有 hERG 钾离子通道，这是一个关键通道，如果你过度抑制它，可能会导致心脏毒性。所以这些都是字母组成的“缩写汤”，在这里的大多数人可能都没听说过。

<details>
<summary>Original English</summary>

**Sergey**: Correct. So I would say there's over 30 or so assays each of which you can imagine if if you're a neural net person like a a multitask neural network or multi head it's got to predict over 30 you know three dozenish properties each of which if it's in the wrong range means your molecule is not a drug it's just a tool and so these are things like solubility which Sergey mentioned important for formulation as in can it be um made into a pill that you can take orally. Your oral bioavailability, whether or not you're inhibiting certain enzymes called the cyocchrome um P450s and its different variants. Um her a critical channel which if you inhibit it too much can cause cardiotoxicity. So these are an alphabet soup of things that most people here haven't heard of. 

</details>

**Interviewer**: 而且其中很多都极其困难，具体是因为……

<details>
<summary>Original English</summary>

**Interviewer**: And a lot of these are extremely hard specifically because

</details>

<!-- chunk 8/13 -->

### ADMET 预测与 Pearl 模型 (ADMET Prediction and Pearl Model)

**Speaker B**: 这不像是一个单一的因果效应。定义这一个终点往往涉及到许多过程和许多路径。所以……

<details>
<summary>Original English</summary>

**Speaker B**: It's not like a single causal effect. There are often times many processes, many pathways which are involved in defining this one endpoint. So...

</details>

**Brandon**: 没错，而且数据集通常少得可怜。除非你有制药公司的帮助，否则至少在开源领域，这……

<details>
<summary>Original English</summary>

**Brandon**: Correct, and data sets are often times comically small. Unless you have, you know, I guess pharma to help you out, but at least open source it's...

</details>

**Speaker B**: 这是一个难题。公共领域的数据非常稀缺。我想说，其实存在一个范围，从可以直接预测的属性，到正如你指出的那样、实际上是其他信号事件混合体的属性。举个例子，比如你是否在抑制像 CYP3A4 这样的酶，这是非常具体的。你抑制的是一种特定的蛋白质。

<details>
<summary>Original English</summary>

**Speaker B**: A hard problem. It's sparse in the public domain. I'd say there's actually a range from really directly predictable properties to ones, let's say, that as you point out are actually amalgams of other signaling events. So like whether or not you're inhibiting like CYP3A4, that's really specific. It's a certain protein that you're inhibiting.

</details>

**Brandon**: 所以对于像 Pearl 这样的模型，这确实是它可以模拟的，并且我们期望能在这里看到一些不错的表现。是的，非常有用的预测。

<details>
<summary>Original English</summary>

**Brandon**: So that's something that Pearl, for example, could actually model and expect to see some performance here. Yeah. Useful prediction.

</details>

**Speaker B**: 我们在其他人之前就已经开始在做关于 ADMET 预测的 3D 工作了。当时有一系列的工作最终促成了我们公司的成立。早在那个 AI 研究还能发表在同行评审期刊、而不仅仅是发在 arXiv 上的随机白皮书的年代，我们就发表了 MoleculeNet，它已经被引用了几千次。同时我们还发表了一篇论文，证明了多任务图神经网络在当时是针对大型制药数据集进行 ADMET 预测的最佳方法。那篇论文现在是 AI 用于 ADMET 领域被引用次数最多的论文之一。正如你所知，很多论文就像是你写完然后就继续做别的事了，但这两项工作实际上都变得非常有影响力。

所以从一开始，我们的历史就不是只解决一个问题，而是专注于药物研发。这样一来，我们就有精力去专注于构建药物研发所需的所有机器学习模型，而不会被目标识别或临床试验等生物发现过程分散注意力，而是真正专注于药物研发和分子生成所需的所有这些任务。这些都非常重要。

我刚才在一开始就想强调这一点，正如 Brandon 你正确指出的，Pearl 是一个 3D 结构预测模型，而许多 ADMET 属性可以被转化为 3D 结构预测问题。因此，它非常有用，不仅仅适用于在靶点上的效价预测。所有这些属性都很重要，而我们不得不去解决所有这些问题。

<details>
<summary>Original English</summary>

**Speaker B**: We've been doing 3D work on ADMET prediction before anyone else was. And there was a bunch of work that ended up launching the company. Back in the day when AI could still be in peer-reviewed journals, not just sort of like random white papers on arXiv, we published MoleculeNet which has been cited a few thousands of times at some point. And we also published this paper showing that multitask graph neural networks were the best at the time for doing ADMET prediction on large pharma data sets, and that paper is one of the most cited papers on AI for ADMET ever. Now, a lot of papers, as you know, it's like you write them and you kind of move on, but both those works have become quite influential as well.

So our history from the beginning has been to work on not just one problem but to focus on drug discovery, and in so doing, being able to have the bandwidth to focus on building all of the ML models that are needed for drug discovery, and not get distracted by the biological discovery processes that are needed—the target ID side or the clinical trial side—but really focused on all those tasks that are required for drug discovery and also molecular generation. Right, these are all important.

And I just wanted to make the point at the beginning, but as you rightly point out, Brandon, Pearl is a 3D structure prediction model and many of these ADMET properties can be posed as those. So it is therefore useful, and not just on-target potency prediction as well. All of them matter and we've had to tackle all them.

</details>

**Brandon**: 你们是将 Pearl 用于所有这些测试，还是它只专注于其中一部分？

<details>
<summary>Original English</summary>

**Brandon**: Do you use Pearl for all these tests or they're focused on some of them?

</details>

**Speaker B**: 我们在接下来的一段时间里会公开分享一些东西。但我认为我们最近发布的结果已经够多了，至少到目前为止是这样。如果这说得通的话。每次你发表什么成果时，团队其实都要花大量的精力去整理。所以我们会在接下来的时期里做这些事，而我们最近一次发表的显然是 OpenFold（注：此处可能指代 OpenBind 等近期工作，根据上下文指代标准的 3D 预测任务）的结果，那是一个标准的 3D 预测任务。

<details>
<summary>Original English</summary>

**Speaker B**: We'll be sharing some things publicly in the coming period. But I think we've had enough news of results lately, I think. I think so far. If that makes sense. Every time you publish something, it's actually a lot of work for the team to put together. So we'll do that in the coming period, but the most recent thing we published was obviously the open bind results, which was a standard 3D prediction task.

</details>

### 计算方法、湿实验数据与模型泛化 (Computation, Wet Lab Data, and Model Generalization)

**Brandon**: 所以我想继续追问这一点。你刚才提到有很多合成数据，然后也有机器学习建模，这非常有现代生成模型的味道。我想谈谈你们的计算方法、机器学习模型，以及湿实验数据之间的反馈机制，它们是如何共同作用来开发这个模型的？我们讨论过先验（priors），我认为传统上，很难很好地扩展蛋白质-配体模型，并以一种有意义的方式实现泛化。而在最近的 Pearl 论文和你们稍后要讨论的其他一些最新结果中，展示了真正的泛化能力。

我很好奇的是，这些不同的方面是如何结合在一起来赋予你们这种能力的？具体来说，计算方法本身很有趣，但你必须非常小心，如果你做错了，分子动力学（MD）会有各种各样的偏差，它可能会给你带来糟糕的结果。因此，我很好奇所有这些是如何协同工作的，特别是在公司的发展历史中，你们是如何达到如今这个高度的？

<details>
<summary>Original English</summary>

**Brandon**: So one thing I want to ask about, kind of keep hitting at this. So you know, you talked about there's a lot of synthetic data and then there's ML modeling which is very kind of generative, modern generate model flavor. I want to talk about kind of the feedback between how your computation, your ML, and how wet lab data went into developing this model. And you know, we talked about priors. I think maybe one it's been typically hard to scale protein-ligand models well in a way which meaningfully generalizes, and there you know this recent Pearl paper and some of your other recent results we'll talk about shortly have shown true generalization. 

And what I'm kind of curious about is how do these different aspects feed together to give you this power? And specifically, you know, just saying computation is interesting, but like you have to be very careful about computation. MD has all sorts of biases if you're not right, it can give you poor results. And so I'm curious about how all of this worked together and especially in the history of the development of the company, how did you kind of get to this point?

</details>

**Speaker B**: 这里有一个“叙事谬误”的经典概念：事后看来，一切似乎都是显而易见的，你可以画出从 A 点到 Z 点非常线性的发展过程，但现实往往更有趣、更混乱，而且我认为更具非线性。

对于 Sergey 和我来说，我们已经训练或“驯服”神经网络十多年了。我们记得这个领域的许多不同时代。如果我们能告诉十年前的自己我们今天技术的威力，告诉我们是如何走到这一步的，我们一定会非常激动。这可能看起来有些顺理成章，但仍然有一些事情在当时是很难预见的。

举个例子，在分子领域使用生成式 AI 的概念并不新鲜，但在十年前将其付诸实践是非常困难的。举个具体的例子，我曾经共同运营过斯坦福 AI 沙龙，我们在盖茨计算机科学大楼里组织活动很有趣。我们会请一些有趣的演讲者，大概 25 个人一起喝喝红酒吃吃奶酪，他们现在有些已经是大名鼎鼎的人物了。但在当时，AI 还是一个小得多的领域。我非常清楚地记得在 2017、2018 年左右，我们讨论生成对抗网络（GANs），讨论它们如何显然是图像生成的未来。因此当时也有很多研究在探讨，我们能否将 GAN 应用于生成蛋白质构象？或者尝试用它们来生成蛋白质-配体的结合姿态？

但正如这些模型在图像训练中面临的那些众所周知的难题一样（其中最著名的问题是模式崩溃），它们在蛋白质或蛋白质-配体系统上效果并不好。我们不得不等待合适的基础原语被创造出来。结果证明，它就是扩散模型（diffusion），对于这个领域而言，这是一个有用得多的原语。

有趣的是，实际上有很多图像和视频模型正在使用扩散模型，但其中一些实际上已经转向了自回归模型。所以很酷的一点是，对于那些真正对核心基础 AI 研究感兴趣的人来说，目前一些最具创新性的扩散模型研究正是发生在我们的领域，发生在我们当下的 3D 结构预测中。当时没有人会预测到这一点，但现在我想说，这就是扩散模型的一个支柱。正如我刚说的，这些在十年前是不可预测的。

与此同时，早在于化学生成任务中应用 3D 扩散模型之前，我们就一直在为手头的药物研发问题构建各种工具。其中一些使用基于物理的方法来预测效价，甚至帮助预测某些 ADME 属性。在分子生成方面也是如此，也就是使用不同的技术来生成新的分子想法。正如 Sergey 指出的，有 10 的 60 次方种成药分子。有效地搜索那个空间是很困难的。

所以我们一直在解决这个问题，当我们想要把当时还处于萌芽阶段但显然令人兴奋的共折叠（co-folding）技术——当时它完全没有准备好走向黄金时代，也没有准备好让药物化学家在日常工作中使用——带入实用领域，并且在某些情况下成为不可替代的、明显优于非共折叠方法的技术时，碰巧这些工具都准备就绪了。我们一直在构建这些其他的原语，所以当我们需要构建合成数据管道或使用一些推理时技术时，它们就唾手可得。就像我们已经准备好迅速做这些事情一样，因为我们一直在研究正交的技术和解决问题的方法。

所以这其中有一些深思熟虑的成分，但就像几乎任何发现一样，比如青霉素的发现。我并不是说我们正在做的事情在数量级或对人类的益处上与青霉素相同，但是……

<details>
<summary>Original English</summary>

**Speaker B**: There's this classic concept of the narrative fallacy where in retrospect everything seems obvious and you can draw really linear processes of how we got from point A to point Z, but the reality is always more interesting and much messier and much more nonlinear, I think. 

And for Sergey and I who've been training or taming neural nets for over a decade, we remember a lot of different eras in the space and we would have been so excited if we could tell ourselves the capabilities of our technologies 10 years ago and if we told ourselves how we got there. It might have seemed somewhat obvious, but still there were some things that would have been really difficult to foresee. 

So one example is, you know, the concept of using generative AI for the molecular space is not a new concept, but the reduction to practice would have been very difficult a decade ago. And so as one concrete example of that, I used to co-run the Stanford AI salon. We had fun organizing, you know, it's Stanford in the Gates computer science building and we'd get some interesting speakers and like 25 people having wine and cheese, and they're all now like some very like just straight up famous people, right? But back then AI was a much smaller field and I remember very clearly in like 2017, 2018 talking about GANs and how generative adversarial networks and how they're clearly the future of image generation obviously. And so there was a lot of work then also in, well, can we just apply GANs to produce conformations of proteins or can we try to use them to produce protein-ligand poses? 

And for all the same reasons that those models were really tricky to train for images—mode collapse was the most famous sort of problem—they didn't work very well for proteins or protein-ligand systems. And we sort of had to wait for the right primitive to get created. And that turned out to be diffusion, which turned out to be a much more useful primitive for the space. 

And interestingly, is actually a lot of image and video models some are using diffusion, but some of those have actually gone autoregressive. And so what's kind of cool is right now for people that are interested in really core fundamental AI research, actually some of the most innovative diffusion research is happening in our field, is happening in 3D structure prediction right now. No one would have predicted that then, but now like that's kind of a pillar of diffusion I'd say. That was unpredictable 10 years ago, everything I just said.

And in parallel to that, long before the advent of 3D diffusion models for generative tasks in chemistry, we were building a variety of tools for the problems of drug discovery at hand. Some of which were using physics-based methods for predicting potency or even for helping predict certain ADME properties. And same with molecular generation, that is like, you know, using different techniques to generate new molecular ideas. As Sergey pointed out, there's 10 to the 60 drug-like molecules. Searching that space efficiently is hard. 

So we've been working on that problem and those things happened to be available when we wanted to take what was then the very nascent area of co-folding, which was clearly exciting but not at all ready for prime time, not at all ready for what a medicinal chemist would want to use in their day-to-day work, and take it to the realm of useful and in some cases irreplaceable, like clearly superior to a non-cofolding method. And it kind of just happened that we had been building those other primitives and so they were available to us so we could put them together to build out for example the synthetic data pipeline or to use some of the inference time techniques. Like we were ready to do those rapidly because we had been working on orthogonal techniques and ways of approaching problems. 

So there was something here that was contemplative, but like almost any discovery, like the discovery of penicillin. I'm not saying what we're doing is on the same order of magnitude or benefit to humanity as penicillin, but there's...

</details>

<!-- chunk 9/13 -->

### AI 与实验室的结合：创造运气的闭环

**Speaker A**: ……在这个过程中总是存在着这样一个要素：如果你针对某个问题保持了足够长时间的极度专注（laser focused），并且你在实验室里——或者在我们这种情况下，是在计算机面前——花费了足够多的时间去死磕这些问题、不断去碰壁（banging your head against the wall），你实际上就可以“创造”出一种所谓的运气，而这种运气最终将促成并赋能一些全新的发展与突破。

<details>
<summary>Original English</summary>

**Speaker A**: ...always this element of if you're laser focused on a problem for long enough and spent enough time in the lab or in our case on the computer banging your head against the wall in these problems, you can create the luck as it were that will enable some of the developments.

</details>

**Interviewer**: 那么，实验室在实际操作中是如何与研发过程（development process）进行互动的呢？

<details>
<summary>Original English</summary>

**Interviewer**: How is the lab interact with the development process?

</details>

**Speaker A**: 就像我之前提到过的那样，我们不仅仅训练结构预测模型，我们也会训练其他类型的模型。对于那些特定的模型来说，实验室的输出结果能够立刻派上极大的用场——比如用于效价预测（potency prediction），对吧？那些来自于实验室的输出数据可以直接用于我们的模型训练。不过，如果展望未来的话，最让我感到兴奋的其实是强化学习（reinforcement learning）。我认为强化学习即将在这个领域大规模普及，而且我们已经从自己的模型中看到了它发挥实际作用的早期迹象。基本上，你可以最初利用诸如基于物理学的反馈，通过一个典型的强化学习循环（RL loop）来改进你的模型；但最终，你可以一直向下延伸，把真实的实验室完全纳入到这个“在环（in the loop）”的设置当中。这样一来，你的模型就不仅仅是在生成预测了，而是你能够直接基于这些预测去合成（分子），接着在下游去测量这些分子的实际属性，然后再把这些真实的测量结果反馈到那个模型中。

<details>
<summary>Original English</summary>

**Speaker A**: We as I mentioned before we train other models not just structure prediction models and for those specific models lab outputs are extremely useful right away um like potency prediction right those outputs can be used directly for model training um but what I'm most excited about going forward is reinforcement learning I think that's coming in our field and we have seen early signs of it working already with our models. So where you basically put initially maybe physics based feedback to improve your models through RL typical RL loop but eventually you can go all the way down to the lab in the loop setups where your model is not only producing like predictions but you synthesize based on those predictions and then you measure downstream properties and then you feed back those predictions into that model.

</details>

**Interviewer**: 既然如此，你们是如何获得足够的数据数量（volume）的呢？我的意思是，你们是否有某种自动化系统来完成这项工作？还是说，你们会开展那些不一定全自动化、但凭借规模优势能够产生大量数据的大规模攻关项目（large campaigns）？

<details>
<summary>Original English</summary>

**Interviewer**: So, how do you get enough volume? I mean, do you have automation to do that or do you like large campaigns that aren't necessarily automated but generate a lot of data?

</details>

**Speaker A**: 有一件事情让我感到无比自豪，那就是我们与 Insight 公司的合作关系。他们是一家非常了不起的卓越公司。他们在生成数据方面表现得极其、极其出色。基本上，他们就是拿到化合物，去生成它们，在现实中把它们创造出来，然后仔细测量这些化合物的下游属性，最后把所有的测试结果发送回给我们。对于 Genesis 和 Insight 而言，这简直就像是一场天作之合（partnership born in heaven），因为我们能够专注于训练模型并给出预测，同时又可以极其迅速地从 Insight 内部获得真实的反馈结果。

<details>
<summary>Original English</summary>

**Speaker A**: One thing I'm super proud of is our partnership with Insight. They're such an amazing company. They are extremely extremely good in producing data. basically taking the compounds, generating them, creating them and then measuring the downstream properties and then sending those results back. This is such a partnership kind of born in heaven for us between Genesis and Insight where we are able to train models, give predictions and have results back from inside super quickly.

</details>

**Interviewer**: 所以，你们所谓的推广或者说实际运作，本质上确实包含了一个真实的实验室迭代环节。

<details>
<summary>Original English</summary>

**Interviewer**: So your like sort of rollouts include a lab like a lab iteration essentially.

</details>

**Speaker A**: 是的，那真是太惊人了。没错。而且你也知道扩散模型（diffusion）跑起来很慢，所以有时候它的反馈速度甚至能跟模型运行的速度差不多。大概给它一周的时间就能完成一次迭代。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, that's amazing. Yeah. And diffusion slow, so it's about the same speed of that sometimes. Give it a week.

</details>

### AI与湿实验室合作的必然性与自动化困境

**Speaker B**: 确实如此。我个人非常坚信一个理念，那就是企业通常只在一两件事情上非常擅长，而且当它们能够全身心专注于这一两件事时，表现总是最好的。同理，我们一直都在极其顽强、心无旁骛地专注于为药物发现开发最顶尖的 AI 模型，而 Insight 则在优化真实的药物发现和开发流程上，有着同等程度的“狂热级”（maniacal）专注。此外，人们最近很喜欢讨论的另一个趋势，当然是中国在生物技术领域的迅速崛起。这是一个大家都看得见的“房间里的大象”（elephant in the room），根本没必要去回避它。现在这股趋势已经成为了整个时代的思潮（zeitgeist），许多西方公司已经变得越来越依赖 CRO（合同研究组织）来代工完成他们大量的湿实验室（wet lab）工作。相比之下，Insight 在他们内部拥有的实验能力方面已经变得如此领先和先进（state-of-the-art）——他们的生产力极高，正如 Saki 所说的，对我们而言，这简直是天作之合。因为我们赖以生存和蓬勃发展的基础就是让这些模型能够持续学习。所以，我们希望能有一个尽可能快速的“设计、制造、测试、分析”（design, make, test, analyze）闭环，并且能够根据我们在实验室中看到的实际情况，不断地去微调模型，甚至在某些特定情况下直接重新训练这些模型。因此，这种合作不仅极其难得，甚至可能是史上首批能够实现这种在历史数据和前瞻性数据上进行真正的“联合基础模型训练”的合作之一。而且在座的作为机器学习从业者，我们都很清楚，在整个开发过程中，数据绝对是一个最关键的输入，是最不可或缺的要素。因此，这对我们来说极其令人兴奋。而且正如我们迄今为止的对话所反映的那样，这个影响范围极广，涵盖了从分子结构预测、效价（potency），一直到各种各样的 ADMET（吸收、分布、代谢、排泄和毒性）属性。所以，我认为这将会立刻提升我们模型的强大实力，并对全面加速药物发现产生非常强大的推动作用。

<details>
<summary>Original English</summary>

**Speaker B**: It is true. It's like I'm a big believer that companies are typically really good at one or two things and do best when they can focus on it. And in the same way we've been just really doggedly focused on developing the best AI models for drug discovery, like Insight has that level of maniacal focus on optimizing drug discovery and development. And another sort of trend people like to be talking about is sort of of course the rise of China and in biotech. Um it's the elephant in the room that there's no point avoiding it. It's so in the zeitgeist right now and where so many western companies have you know had become to rely more on CRO to do a lot of their wet lab work you know insight became like so state-of-the-art in terms of the experimental capabilities they had in house their productivity is extremely high and as Saki said it's a matchboard in heaven for us Because what we thrive on is continuous learning of the models. So we want to have design, make, test, analyze cycles that are as rapid as possible and continuously fine-tune in some cases depending retrain the models based on what we see in the lab. Um and so that partnership is one of if not the first ever that enables that sort of true joint foundation model training on historical and also perspective data and as ML practitioners we all know here the data is just such a critical input in the whole critical ingredient. So it's just extremely exciting for us and that's a range you know from reflecting our conversation so far here you from structure potency and a variety of adnet properties as well. Um so I think it immediately will improve the strength of our models and be really powerful for generally accelerating drug discovery.

</details>

**Interviewer**: 然后，我们刚才还在拿运行扩散模型所需的时间开玩笑，但我不知道……我不知道你能不能披露这些细节，但当你们发邮件给他们，说“这里有一些……”——我不知道你们一般发多少，可能是 10 个或者 100 个化合物——然后他们把这些实际合成出来的化合物的测量结果回复给你们，这个完整的周期到底需要多长时间？是一天、一周、一个月，还是一个小时？

<details>
<summary>Original English</summary>

**Interviewer**: and just we were joking around about the time that it takes to do diffusion but like I don't know if you can disclose this but how long does it take to you know you email them with here's some here's I don't know how many 10 100 compounds and then they get back to you with measurements of those realized compounds in what a day, a week, a month, a hour.

</details>

**Speaker B**: 这完全要看具体情况。有些化合物非常容易就能搞定，它们是非常已知的——比如一种特征非常明确的反应，你只需要用通常的反应条件就能顺利奏效；但有时候你也会遇到这种情况，“哦，这个偶联反应实际上并没有像文献上说的那样起作用，我们必须得尝试其他不同的条件。”所以，这真的要视情况而定。我之所以在这里指出这一点，是想让听众明白，针对外界关于“机器人实验室可以把合成过程完全自动化”的所有那些宏大说法，现实情况其实要比那复杂得多。

<details>
<summary>Original English</summary>

**Speaker B**: It depends. Like some compounds are really easy to knock out really known like a very well-characterized reaction where the usual conditions just work and sometimes it's oh this coupling actually didn't work like the literature said it would and we have to try different conditions. So it depends. I'm saying this so the audience understands that for all the claims out there about just like robotic labs automating synthesis the reality is just a lot more complicated than that.

</details>

**Interviewer**: 抱歉打断一下。那里面的复杂性到底都有哪些呢？你们的观点非常“激进”（radical）。毕竟现在他们都在做某种形式的自动化。那么（与这些乐观的说法相比），这里反向的观点是什么？我再次强调，我并不是想让你去跟他们挑起争端打口水仗，我只是想问，在“自动化实验室什么地方会出错”这个问题上，你们的具体看法到底是什么？

<details>
<summary>Original English</summary>

**Interviewer**: Sorry. What are some of the complications there? You radically radical. So they all do some sort form of automation. what like and again not trying to get you to get in some fight with them but like what was the contrary take here on okay what goes wrong with automated lab.

</details>

**Speaker C**: 好的。这就是正如 Sergey 之前提到的，我们之所以对强化学习（RL）如此兴奋的众多原因之一，因为它规避了那个为了将结果反馈给模型，而必须在实验室里进行极快的“设计-制造-测试-分析”闭环的难题。在最理想的情况下，我们可以往这个问题里投入越来越多、源源不断的 GPU，让模型像我们在 2010 年代末玩棋盘游戏（board games）或者最近在写代码时所做的那样，进行大规模的自我训练。那是我们的一个关键北极星（northstar，即终极目标）。然而，如果任何人试图告诉你，将来会在一个数据中心里出现一个“天才之国”，单纯靠待在屋子里就能解决药物发现的全部问题，我想提前告诉你，我们这个领域确实存在一些问题，它们并不那么自然地适用于 RL（强化学习），而且这些问题将不可避免地需要进行真正的实验性干预。为了深入说明其中的具体原因，我来举几个实际的例子。你知道，写代码曾经一直是我人生的北极星，是我这辈子最想做的事情。但我自己也确确实实在湿实验室（wet lab）里花过不少时间，当时我只是个非常平庸的实验科学家，直到后来在我读研究生时，我才重新找回了我真正的乐趣——因为我终于可以每天只是专注、专注于敲代码了。现实的实验室其实是相当混乱的（messy）。为了制造出一个新的分子，你必须去切实地合成它。这意味着你需要将各种不同的化学试剂、催化剂，在特定的温度和溶剂下，以绝对正确的方式和严格的方案结合在一起，才能试图制造出你的新分子。而在你完成这些反应之后，你还需要对它进行纯化（purify）。如果你不纯化它，你的阳性或阴性的检测结果（assay read）可能仅仅是一种由于杂质产生的假象（artifact）。随后，你还需要对它进行表征（characterize）。因此，你需要使用核磁共振（NMR）以及诸如质谱（mass spec）等其他技术来证明，你在试管里制造出来的那个东西，确实就是你最初想要制造的东西。而这绝不像听起来那么简单琐碎。顺便说一句，这不仅仅是对我们来说如此，对于任何将 AI 用于材料科学（material science）的人来说也是完全一样的。大家面临的都是同类的挑战，即“我究竟有没有造出我实际想造出来的东西？”这其实完全不是一个简单的问题。当然，在小分子药物发现中这比在材料科学中要容易一些，但它依然不是件小事，而且需要花费大量时间。我们见过太多这样的情况：所谓的大规模分子筛选在纸面上听起来非常棒，因为你可以一次性测试数百万甚至数十亿的化合物，所以你看起来有更多的“射门机会”（shots on goal），而且作为额外的奖励，你的模型也获得了充足的数据，对吧？你刚刚轻松拿到了数百万的数据点。可是好吧，现实情况却是，从高通量筛选（high throughput screens）——无论是 DNA 编码文库（Dell DNA coded libraries），还是更传统的筛选方式——所做出的预测，到真正在实验中重新从头合成（de novo）一个分子并进行低通量、高保真度的实验（low throughput high-fidelity experiment），这中间的决定系数（R-squared）低得令人震惊。由于各种各样的原因，其中的假阳性率（false positive rate）极其巨大。所以，这就是人们对 AI 做出这些预测感到如此兴奋的众多原因之一，因为在理论上，AI 的预测结果可以比许多湿实验室的工作（尤其是那些高通量筛选工作）干净得多，从而实现更高的富集度，并且获得更高的真阳性率。那么，为什么现实中经常不如预期呢？仅仅是因为实验本身就经常出错吗？甚至说，就算你有一种非常精密准确的机器人来为你执行这些操作，这依然是个问题吗？是的，即便如此依然是个问题，因为这里面存在的变量太多了。在整个物理系统中，存在的误差和不可控因素（slop）实在太多了。

<details>
<summary>Original English</summary>

**Speaker C**: Okay. So, this is also one of the reasons as Sergey mentioned, we're really excited about reinforcement learning because it circumvents the problems of having to do very fast design make test analyze cycles from the lab to feed back into the model. Ideally, we can throw more and more GPUs at the problem and have the model self-trained in the same way that we once did for board games in the late 2010s or most recently for coding. Like that, that's a key northstar for us. However, before anyone tells you that there will be a country of geniuses in a data room just solving drug discovery, um there are some problems in our space that don't lend themselves to RL as naturally and that will require experimental intervention. And so to drive in the specifics of why to give some examples and I so I you know coding was always my northstar what I wanted to do with my life. But I spent a fair bit of time myself in the wet lab as a very mediocre experimental scientist before I found my true joy back in you know when I got to graduate school and I can just focus on coding all day. Um the reality is quite messy. So in order to make a new molecule you have to synthesize it. And what that means is different chemical reagents and catalysts and temperatures and solvents coming together in the right way in the right protocol to try to make your new molecule. And once you do that you need to purify it. If you don't do that your positive or negative assay read could be an artifact. You need to characterize it. So you need to use NMR and other techniques like mass spec to indicate that what you made in your vial is what you actually sought to make in the first place which is not as trivial as it sounds either. That's not only true for us by the way for anyone doing material science for AI. It's the same sort of challenge where did I make what I actually made is actually not trivial question at all. It's easier in small molecular drug discovery than it is in materials but it's still non-trivial and takes time. We've seen so many cases where screenings of large molecules sounds great in paper because you can test millions billions of compounds in one go so you have more shots on goal and as a bonus you have data for your model right you just got millions of data points while okay the reality is that the translation of high throughput screens whether it's Dell DNA coded libraries or more traditional screens the R squared of those predictions to like the actual business of resynthesizing a molecule de novo and doing a low throughput high-fidelity experiment is a shockingly low R squared um that false positive rate is enormous for a variety of reasons um and so that's one of the many reasons why people are so excited about AI making those predictions because in theory they can be even cleaner than a lot of the wet lab work especially the high throughput work and yield to higher enrichment hadn't hired true positive rates. So why can it be more? Is it just because the experiments go wrong a lot and even does it matter that you have some sort of very precise robot doing it? It's still there's too many variables. There's too much slop in the system.

</details>

**Interviewer**: 这确实包含几个方面的因素。那么其中之一就是……

<details>
<summary>Original English</summary>

**Interviewer**: It's a few things. So one is

</details>

<!-- chunk 10/13 -->

### 药物发现中的多参数优化

**Speaker A**: 药物发现通常需要寻找离群值（outliers）。

<details>
<summary>Original English</summary>

**Speaker A**: that drug discovery frequently involves finding the outliers.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah.

</details>

**Speaker A**: 我们的领域有很多极其疯狂的方面，其中之一就是你希望一个分子具备的属性通常是负相关的。结合力往往随着化合物的疏水性增加而提升，你的化合物越油腻越好，因为蛋白质结合口袋本身就是油腻的。但你猜怎么着？这会让你的溶解度变差。

<details>
<summary>Original English</summary>

**Speaker A**: One of the many aspects that's so wild about our space is that the properties that one is seeking in a molecule very often anti-correlate binding tends to improve the more hydrophobic, the more greasy your compound is cuz protein binding pockets are greasy. Guess what? That makes your solubility worse.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah.

</details>

**Speaker A**: 然后你通常又想通过增加化合物的极性来改善你的溶解度。突然之间，对于那些还记得高中生物学的人来说，细胞是被脂质双分子层包围的。你的分子可能无法穿过细胞膜，因为你把分子弄得太具极性了。所以你想要的属性往往是负相关的，这就使得分子的多参数优化最终感觉就像在玩打地鼠。因此，你经常在寻找真正的离群值，而这往往需要制造出具有根本新颖性的分子。而今天能够自动化的化学反应种类是相当受限的。因此，你为了寻找那些真正的顶级帕累托最优化合物而广泛搜索化学空间的能力，实际上是非常有限的。所以，你在速度上获得的优势，往往要与你能制造的分子的实际质量和新颖性进行极其严酷的权衡。

<details>
<summary>Original English</summary>

**Speaker A**: >> And then you want to improve your solubility often by adding polarity to your compound. And suddenly, for those that remember high school biology, cells are surrounded by lipid billayers. Your molecule might not get through the cell membrane because you made your molecule too polar. So the properties you want often anti-correlate and that's where you get where multiparameter optimization of molecules ends up feeling like playing whack-a-ole. So you're often searching for real outliers and that often requires making molecules that are fundamentally novel. And the kinds of chemistries that today can be automated are fairly constrained. And so your ability to search chemical space broadly for those really top top paro optimal compounds is is actually very limited. So the benefits you get in speed have a very harsh trade-off with the actual quality and novelty of the molecules that you can make.

</details>

**Speaker B**: 所以你可以很快地做很多无聊的事情。是这样吗？

<details>
<summary>Original English</summary>

**Speaker B**: >> So you can do a lot of boring stuff very quickly. Is that

</details>

**Speaker A**: 呃，如果你运气好的话？是的，那可能会是，是的，如果你运气好的话。

<details>
<summary>Original English</summary>

**Speaker A**: >> uh if you're lucky? Yeah, that would be Yeah, if you're lucky.

</details>

**Speaker B**: 但为了得到那个，为了真正解答那些前沿问题，你真的很难让一个机器人系统来做这些事情。

<details>
<summary>Original English</summary>

**Speaker B**: >> But to get to the to actually the answer to your the the sort of cutting edge questions, you really it's hard to get a robotic system to do those kinds of things.

</details>

**Speaker A**: 是的，我们很希望那能够成真。那会对我们的工作产生巨大的推动力，但是，嗯，今天那还做不到，今天还没有这个条件。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yes, we would love for that to happen. it'd be a huge tailwind for what we do, but um that's not that's not available today.

</details>

### Insight 的垂直整合与医药行业的转变

**Speaker B**: 不是我们今天的现状，对吧？所以，所以我，我的意思是，我知道，再次声明，不是要你透露任何你不能说的内容，但是 Insight 是采用了什么样的方法让他们如此快速和有效的呢？

<details>
<summary>Original English</summary>

**Speaker B**: >> Not where we're at today, right? And so and so I I mean I know again not asking you to disclose anything that you can't, but what is Insight's approach that makes them so fast and effective.

</details>

**Speaker A**: 我觉得如果，如果一个人愿意专注于一个问题，并对干扰说不，你能取得的成就是惊人的。而且我认为其中一点是他们的人才密度非常非常高，并且他们愿意去，去做现在大中型制药公司不普遍在做的事情，那就是在内部建立极其丰富的实验能力。嗯。我其实认为更多的公司有可能尝试这样做，考虑到全球药物开发的动态已经发生了如此巨大的变化，对吧，CRO 接管了一切，然后现在突然之间变得商品化了，随之而来的是，你进行前沿实验的能力却下降了。它可以，嗯，几百年来关于垂直整合优势的争论一直存在。这伴随着所有风险、挑战和前期成本等方面的因素，但也拥有端到端控制流程的所有优势。

<details>
<summary>Original English</summary>

**Speaker A**: >> I think if if one is willing to focus on one problem and say no to distractions, it's amazing what can happen. And I think one is that their talent density is very very high and they're willing to to what is not universally done now in large or mediumsized pharma which is build so many experimental capabilities in house. Mhm. And I actually think that it's possible more companies to try to do that given the global dynamic of pharmaceutical development that's changed so dramatically and right so CRO is taking over everything then now suddenly has become commoditized and then that but your also your cap capability to do the cutting edge experiments goes down. It can um it's been a debate for hundreds of years about the benefits of vertical integration. It comes in all the areas of of risk and challenges and upfront cost but has all the benefits of controlling the process end to end.

</details>

**Speaker B**: 当它起作用时，当你端到端地做事时，你可以做出惊人的事情。

<details>
<summary>Original English</summary>

**Speaker B**: >> When it works, you can do amazing things when you do things end to end.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah.

</details>

### 公司的战略支点与商业模式

**Speaker B**: 嗯，当然这也伴随着更大的挑战，我认为确实需要有胃口，嗯，呃，才能去做这件事。这让我想到我有的另一个问题，再次是更多关于行业的。但是，所以你们，所以也许现在是个好时机来谈谈你们的转型，从，比如，你们的名字从 Genesis Therapeutics 变成了 Genesis Molecular AI，而且我认为这可能与公司战略的转变密切相关，或者是，就“我们要，我们要”而言，听起来像是在说，我们要专注于 AI 部分，然后把这个卖给制药公司，而不是成为一个，你知道，同时也出售工具的制药公司。是，是差不多这样吗？

<details>
<summary>Original English</summary>

**Speaker B**: >> Um of course it comes with greater challenges and I think an appetite um uh needed to to do it. And this kind of brings me to another question I have again more industry. But so you guys so maybe now is a good time to talk about your pivot to from like so there's name change from Genesis therapeutics to Genesis Molecular AI and that that I think goes hand in hand with maybe a pivot in the strategy of the company or is that in terms of okay we're going to like what it sounds like to me is we're going to focus on the AI portion that and then sell that to pharma rather then be a you know sort of a drug company with that also sells the tool. Is that is that sort of accurate?

</details>

**Speaker A**: 当我们创立这家公司时，嗯，公司的起源是我们在斯坦福开发的底层深度学习研究方法，对吧？而我们试图解决的目标是，我们如何才能为患者带来最大的影响？当时，你知道，公司成立时的初衷纯粹是人工智能研究。在那个时候，并没有什么真正的先例表明，嗯，一家纯模型公司能在行业中立足，单纯通过为制药合作伙伴或大多传统行业的合作伙伴创造价值来生存。我认为另一个要素是，公司是建立在人工智能研究之上的。我想我们真的希望能向人们展示，我们对生物技术领域是认真的。所以，你知道，我认为这是将其命名为 Genesis Therapeutics 的部分起源。

<details>
<summary>Original English</summary>

**Speaker A**: >> When we started the company um the origin of the company was fundamental deep learning research methods that we had developed at Stanford, right? And the objective we were trying to solve for was how can we have the greatest impact for patients? And at the time, you know, the the founding of the company was purely an AI research. There was no real precedent at that time for um a pure model company really um making it in the realm of just creating value for partners in pharma or really most legacy industries. And the other I think component was the company being founded on AI research. I think we really wanted to show people that we were serious about the biotech domain. So you know I think that's part of the origin of let's call the genesis therapeutics.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah.

</details>

**Speaker A**: 我们似乎更严肃对待，对待，对待，你知道，制药行业所有那些久经考验的人，那些彻头彻尾的药物化学家和药物开发者，他们正是我们真正想要合作的人。所以我认为其中有某种尝试名副其实的意味。嗯，但，但同时我们也承认，我认为在那个时候，还没有人真正证明过你可以成为一家纯粹的 AI 模型公司。是的。并在，在这个领域取得成功。那显然，这是在 2019 年。所以，我们获得了成为该领域真正的先驱、开拓者的优势。我们也有因为起步相当早而带来的劣势。

<details>
<summary>Original English</summary>

**Speaker A**: >> We seem a lot more serious to to to the to the you know all the the triedand-rue folks in pharma the diet in the wool med chemist drug developers who we who we really wanted to work with. So I think there was an element of an attempt at nominative determinism there a bit. Um but but also an acknowledgement that I don't think anyone had really shown at that time that you could be a pure AI model company. Yeah. And really make it in in the space. And that was obviously this is 2019. So we we had the benefit of being real forebears pioneers in the space. We had the downside of being pretty early.

</details>

**Speaker B**: 是的。大家以为来晚了，但结果发现这依然是早期阶段。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. thought to be late, but turns out it was still early innings.

</details>

**Speaker A**: 随着公司的成长和发展，嗯，我们的结构实际上有点像双螺旋，因为我们拥有极其强大、专注的 AI 研究，并且我们很幸运地招募了一些最有经验、最有成就的药物猎手，比如我们管理团队和董事会中的人员，他们发现、共同发明、开发了许多 FDA 批准的药物。你跟大多数药物化学家交谈，大多数药物化学家都会觉得，如果他们在整个职业生涯中能够参与研发一款获得 FDA 批准的分子，那就非常幸运了。我们在起步时就能说服这些成绩斐然的药物猎手加入我们的管理团队和董事会并掌舵，这让我们感到非常幸运。所以结果一直是一样的。我们所讨论的一切，只有当我们最终能够帮助到患者和他们的家庭时才有意义。从一开始我们就觉得，要在规模上做到这一点，主要的方法就是与大中型制药公司和生物技术公司合作。这样他们就可以做他们最擅长的事，即新颖的生物学临床开发。我们就可以做我们最擅长的事，即 AI，并将这两者结合起来。除此之外，正如 Sergey 所说，在内部拥有湿实验室数据生成也有很多优势，显然是为了用我们自己的模型进行实战演练（dog fooding），从而直接从真正的药物化学家那里得到关于我们需要以一种极其坦诚的方式构建什么的人类反馈。当然，第三件事是，宇宙中最有价值的东西，正如我喜欢开玩笑说的，是错误镜子（mirror of error）测试。如果你问别人，什么是你最想要的东西，并且你真的深思熟虑过，大多数人会说，为他们自己或家人想要一种药物。因此，拥有自己的管线项目具有巨大的内在价值。当，当我们与制药合作伙伴互动时，平均来说，他们很喜欢我们自己在研发分子，因为这意味着我们不只是一群键盘侠，而是我们生活在自己宣扬的梦想中，并且我们也需要自己实践和使用这些模型。因此，它们也在额外的层面上经受了战斗的考验，我们算是被驯化了，因为我们，嗯，我们知道这个领域真正困难的地方在哪里。我们不是只在卖一些白日梦。

<details>
<summary>Original English</summary>

**Speaker A**: as the company grew and and evolved, um, we really were structured kind of like a double helix in that we had extremely strong, focused AI research and we were fortunate to be able to recruit some of the most experienced and accomplished drug hunters like people on our management team and board who have discovered, co-invented, developed many FDA approved drugs. You talk to most medchemists, mo most medchemists are feel very fortunate if they're able to work on one molecule that gets FDA approval in their whole career. And we're really fortunate to convince these sort of accomplished drug hunters to come join our management team and board at the beginning and steer the show. So the outcome has always been the same. Everything we're talking about, it only matters if we end up helping patients and their families at the end of the day. And we have felt from the beginning that the the way to do that at scale is to primarily partner with large medium-sized pharma companies and biotech companies. So they can do what they're best at which is novel biology clinical development. We can do what we're best at which is AI and bring those two together. In addition to that, as Sergey has said, there's numerous advantages to having in-house wet lab data generation clearly dog fooding the models getting really direct human feedback from real med chemists. what we need to build in an extremely candid way. And of course, the third thing is that the single most valuable thing in the universe what I like to joke is the the mirror of error said test. If you ask people what is what is the one thing you most want and you really thought about it, most people would say a medicine for themselves or a family member. And so there is just immense intrinsic value to having one's own pipeline programs. And when when we interact with pharmaceutical partners, on average, they love that we're working on molecules ourselves because it means that we're not just a bunch of keyboard jockeyies, but we live the dream that we are pitching and we need to use these models and practice for ourselves, too. So, they're battle tested in an in an additional way and we're sort of domesticated in that we uh we know what's really difficult about the space. we're not just sort of selling some pipe dream.

</details>

**Speaker B**: 在我看来，在过去的一到两年里，行业似乎发生了一个转变，制药公司突然开始对购买现成的工具感兴趣了，而以前，很多试图构建 AI 的初创公司遇到了困难，所以他们变成了制药公司，因为那是他们赚钱的唯一途径，对吧？也就是你筹集了一大笔钱，并希望在 10 年内你能研制出一种药物，如果那种药物成功了，那你就成功了，否则你就会倒闭，或者比如卖掉资产之类的事情。而且，而且现在这种情况似乎正在改变，最近发生了很多，嗯，AI 方面的收购，而且你知道，在药物发现、病理学以及很多不同的相关领域都有，那么你看到这种转变了吗？这是你们倾向于销售模型的原因之一吗？或者这只是一次品牌重塑，仅仅是因为，因为这种转变，比如到底发生了什么？

<details>
<summary>Original English</summary>

**Speaker B**: >> It seems to me like there's been a shift in the last I don't know year to two years where suddenly pharma has become interested in buying tools off the shelf whereas previously there are a lot of companies that started trying to build AI and then had trouble and so they became pharma companies because that's the only way they could make money, right? is you raise a bunch of money and hope that in 10 years you have a drug and if that drug is successful then you've made it and otherwise then you fold or like sell off the assets or whatever and and it seems like now that's changing you have a lot of recent um AI acquisitions and you know in drug discovery and pathology and lots of different related areas and so have you seen this shift and is that part of the are you shifting towards selling models or is this just rebranding just because because of that shift like what's going on

</details>

**Speaker A**: 为了讲完那个，那个，那个故事线索，这个名字

<details>
<summary>Original English</summary>

**Speaker A**: >> to finish that that that narrative arc there the the name

</details>

<!-- chunk 11/13 -->

### 公司的定位与愿景：不仅是工具，更要打造全栈系统

**Speaker A**：这次改变只是为了反映我们在实践中真正在做的事情，也就是，正如我们从第一天开始用 PyTorch 写代码时一样，我们是一家 AI 公司。当 Sergey 第一次在 PyTorch 上扩展 Transformer 规模时——他是第一个这么做的人——我们也在 PyTorch 上扩展图神经网络（Graph Neural Networks），我们也是最早做这件事的团队之一。所以，这反映了我们从第一天起就确立的身份。不过，这也暗示了这样一个事实：我们本身就是非常严肃的药物分子制造者（molecule makers）。在这个意义上，我们是全栈式的。而且，明确一点，我们的使命是尽可能多地创造那些原本可能无法被创造出来的药物，我认为实现这一目标的途径，就是将我们的技术直接交到尽可能多的药物开发者手中，不仅是我们内部的开发者，还包括大型制药公司、中型制药公司以及生物技术公司。这也部分解释了为什么我们一直在构建我们自己的智能体（agents），以便让我们现在变得越来越强大的模型，能够轻松地被那些可能一辈子都没写过一行代码的药物化学家或 CAD 科学家所使用和调度。

<details>
<summary>Original English</summary>

**Speaker A**: change was just to reflect what we were really doing in practice which is we are an AI company as we have been from day one when we were you know coding in PyTorch. building you know the first you know when Sergey was scaling transformers on PyTorch the first one to do that we were scaling graphinal nets in PyTorch one of the first ones to do that um so it's reflecting what what our identity has been from day one. Um but also alluding to the fact that we are very serious molecule makers ourselves. Um and we are full stack in that way. Um we are also to be clear our mission is to create as many medicines as possible as would otherwise not have been created and I think the way to get there is to put our technology directly into the hands of as many drug developers as possible. not just our own but in big pharma, midcap pharma and biotech. And that's partially why we've been building our our agents so that our models which are have become so much more powerful um can be easily used and orchestrated in the hands of med chemist CAD scientists who might have never ever written a line of code in their life.

</details>

**Speaker B**：听到你们现在开始将智能体（agents）引入到你们的开发流程中，我觉得这非常有趣。听起来从一开始，你们的理念更倾向于“这些是为科学家提供的工具，你要做出尽可能最好的工具，让他们去优化他们打算使用的任何流程”，但说到底，这还是给药物化学家用的一个工具。而现在，你们转变了方向，你说你们实际上将会拥有能够自主做出决策并推进研发的自动化系统。首先，你确实提到你们大概已经达到了某个临界点，就像去年 11 月的那个临界点一样，模型突然奇迹般地变得有用了。所以，这可能是部分原因。但是，推动你们朝着这个方向发展还有其他原因吗？为什么是现在？

<details>
<summary>Original English</summary>

**Speaker B**: I find it interesting to hear that you have now started bringing in agents into your development um process. You know, it sounds like from the very get-go you your philosophy was much more these are tools for scientists and you make the best possible tool and uh this lets them optimize whatever pipeline they're going to use but ultimately this is a tool for medkim and now you are switching and you were saying we are actually going to have automated systems which make decisions and then advance. Uh, first of all, you did allude to you've kind of hit maybe the threshold to, you know, the like last November threshold where it just magically became useful. Um, so maybe that's part of it, but are there other reasons for going in this direction and like you know why why now?

</details>

**Speaker A**：好吧，让我反问你一个问题。你觉得一个人类药物化学家或者计算辅助药物设计（CAD）科学家，在现实中能学习并精通多少种工具？

<details>
<summary>Original English</summary>

**Speaker A**: Well, let me ask you a question in return. How many tools do you think a human mad chemist or CD scientist can realistically learn and like be proficient in?

</details>

**Speaker B**：哦，我想说的是，他们能学多少种，以及他们实际使用了多少种？因为我见过他们喜欢用大量的工具，但也许他们并不一定对这些工具都很在行……

<details>
<summary>Original English</summary>

**Speaker B**: Oh, I was say how many can they learn and how many do they use? Because I've seen that they like to use lots of them, but maybe they're not necessarily good with

</details>

**Speaker A**：但这确实很难，对吧？许多工具都极其复杂。

<details>
<summary>Original English</summary>

**Speaker A**: but it's really hard, right? A lot of the tools are extremely complex.

</details>

**Speaker B**：这些工具有很多参数，你必须要正确设置和配置它们，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: They have a lot of parameters that you that you need to set properly and configure them, right?

</details>

**Speaker A**：而这正是智能体极其擅长的地方。它们实际上知道如何使用所有的工具，也知道如何去调度它们。

<details>
<summary>Original English</summary>

**Speaker A**: And this is where agents are extremely good at. uh you they they they actually know how to use all of the tools and how to orchestrate them. Well,

</details>

### 定义生物领域的 Agent

**Speaker B**：我不想打断你，但当你提到“智能体（agent）”时，有些人喜欢用这个词来仅仅指代某种自动化的东西，而另一些人则特别用它来指代一个负责调度决策的 LLM（大语言模型）。在生物技术以外的领域，几乎所有人都普遍认同后一种含义；但在生物领域，人们有时仍然用“智能体”来指代任何一种将人类排除在外的自动化决策系统，甚至有些更像是传统的基于规则的系统之类的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: so I wouldn't interrupt you when you say agent that um some people like using the term agent to just mean something automated, but other people use agent to specifically mean you have an LLM which is responsible for orchestring orchestrating decisions. Um I mean in outside of biotech it's almost it's universally the latter but sometimes in the space of bio people are still using agents to refer to any sort of decision based system which is automated out of humans and maybe some of them are even more like traditional rules based systems or something right

</details>

**Speaker A**：在我们这里，我的意思是符合 AI 定义的智能体，比如一个 LLM，它能够使用我们公司在多年发展中苦心构建的所有工具。而且，这是一个非常强大的概念，因为现在作为一个 CAD 科学家或药物化学家，你不需要去深刻理解所有的细节以及你需要设置的所有超参数，你只需要让这个东西自己去运行，去找出并解决问题就行了。这就是我们之前讨论过的所有问题再次变得非常重要的地方——比如智能体需要能够理解这些模型正在产生什么结果。为什么我们要关心晶体结构？因为智能体实际上可以查看你预测的晶体结构，并基于此做出决策。我们认为，这对迭代和改进来说极其重要。

<details>
<summary>Original English</summary>

**Speaker A**: so in in our case I mean uh AI definition of agents like an LLM which is able to use all of the tools that we have been painstakingly building over the many years of existence of this company. Um, and that's a very powerful concept because now as as a cut scientist or mat chemist, you don't need to deeply understand all of the details and all of the hyperparameters that you need to set and you can just let this thing go uh and figure out and solve the problems. Um, and this is where all of the previous questions that we discussed came up come back as very important one like agents need to be able to understand what these models are producing. Why do we care about crystal structure? Well, the agent can actually look at your predicted crystal structure and make decisions based on that. Something that we believe is super important uh to to iterate and improve.

</details>

**Speaker B**：你的意思是，你可以输入一个晶体结构，我想在这个语境下，它可以被构建为一个图（graph），或者类似于 Molstar 正在解析的三维图像，然后它实际上可以根据什么与什么结合来做出决策，并提出假设。也就是说，你们已经达到了这样的水平：你已经看到它能做出有效的决策了，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: You're saying that you can take a crystal structure uh which I guess in this case is framed as a graph or like a three-dimensional image that molestar is interpreting I mean in some way and then it it actually can make decisions upon what is binding to what and make hypotheses. like you've gotten to that point where you have seen it making effective decisions, right?

</details>

**Speaker A**：这个问题肯定包含多个层面。你可以从基础的图像理解开始；或者你可以使用额外的工具来理解晶体结构中正在发生的事情；你甚至可以训练一个能够原生理解晶体结构表征的模型。就像图像模态是 LLM 的一种模态一样，如今，晶体结构也可以成为 LLM 的一种模态。

<details>
<summary>Original English</summary>

**Speaker A**: So there are definitely multiple layers to this this question. You can start with like basic image understanding right here uh or you can use additional tools to understand what is happening in the crystal structure or you can even train a model which is which is able to natively understand um crystal structure representation and like image modality is a modality for LLMs. These days, crystal structure can be a modality for LLM as well.

</details>

**Speaker B**：你可以用那些看起来以某种方式捕捉了作为 3D 晶体结构的 token 序列来对它进行微调，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: I can fine-tune it on sequences that look like that are somehow capturing tokens that are C 3D crystal structures, right?

</details>

**Speaker A**：是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

### 重新构想人机交互与自动化的未来

**Speaker B**：所以，如果在过去，你们对待人类的态度是“你们在为人类制造工具”，而现在，你们有了智能体，那么你们打算如何重新构想人类与智能体之间的交互，以及决策流程的发展？你们是希望借此基本上把人类完全自动化掉吗？你是想要扩大规模，做更多的假设验证？另外，怀疑论者可能会问：你又怎么能确保你的智能体不会做出奇怪的决策？比如它们调错了某个超参数，然后塞给人类一大堆无用的结果。人类根本不够了解这些参数，无法察觉到错误的发生。

<details>
<summary>Original English</summary>

**Speaker B**: So, if you historically have treated humans like you were making tools for humans, so now you have agents, how do you reimagine the interaction of humans and agents and the decision-m process to go? Is this you hope to essentially automated humans out? You want to scale up and do more hypothesis or Yeah. And then also the kind of the the the skeptic would ask how do you also tell make sure that your agents are not making weird decisions where they tweaked the wrong hyperparameter and now you give you the human a bunch of Yeah. You don't you don't understand the parameters well enough to know that that happened. Yeah,

</details>

**Speaker A**：这是一个很好的问题。我认为，从代码工具的演进过程中，你就能看到这个问题的答案。你还记得 Cursor 刚出现的时候吗？那时它就像是一个顶级的自动补全工具。虽然有用，但远不及现在的程度——现在我只需打开 Cursor，它就会自己跑去为我完成所有的事情。所以，我认为我们会在这里看到一条非常相似的发展轨迹。那些智能体本来就已经很有用了，但现在，人类需要提供一致的反馈，并在整个过程中引导和掌控这个智能体。不过随着时间的推移，它们会变得越来越独立。尽管如此，我依然不相信那种“取代人类”的完全自动化。我相信，在使用这些工具的情况下，人类在他们所从事的工作中会变得高效得多。人类将负责为智能体需要做的事情提供战略方向，而智能体将能够代表人类去执行具体的任务。

<details>
<summary>Original English</summary>

**Speaker A**: it's it's a great question and I think the answer here you can see in how coding tools have evolved, right? You remember Corser when it just appeared and it was like top top autocomplete. It was still useful but not to the extent that it is useful right now where I can fire up Corser and it just goes and does everything for me. So I think we're going to see a very similar trajectory here. Now those agents were already useful but now human need to provide a consistent feedback and basically steer and guide this this agent along the way but over time we're going to become more independent still I don't believe in a full automation like replacing humans I believe humans are going to become way more efficient in the job that they're doing using the tools so a human will be providing strategic direction to what this agent needs to do and the agent is going to be able to go and execute on behalf of a human.

</details>

**Speaker B**：我认为，现在是成为一个富有创造力的人类——或者说，生而为人的最好时代。如果你回顾历史的漫长弧线，从我们决定放弃狩猎和采集开始……说实话，我也不太确定那时候怎么想的。当时的人可能觉得：“我要安定下来，去搞这套叫农业的东西。” 我觉得那开启了长达数千年的苦役。有时候你会纳闷：我们当初为什么要去搞农业？因为从我看到的一切来看，在短期内，农业很可能是一个净损失。我能看到的唯一的长远好处是，如果你是一个狩猎采集者，一旦你生病了、生来带有遗传疾病，或者受了伤，那你就麻烦大了。我们能为你做的事情不多，因为当时根本就不存在医学。但归根结底，在我看来，人类文明的最高成就是：社会中生病的人不再被视为负担，而是我们想要去帮助的人。纵观包括人类在内的动物界的历史，这在以前是不成立的。这是一个悲惨的现实，但这是事实。而现在，因为有了医学，我们把生病的人看作是我们想要帮助、也能够帮助的人。如果我们能帮助他们，他们甚至能成为对社会更有生产力的成员——如果这是你所关心的事情的话。如果把时间快进到现在，我认为在大量的创造性工作、日常工作里——如果你把它看作一个饼图，而时间是我们最宝贵的资源——其中有很大一部分时间，曾经被那些实际上不需要太多思考或创造力的重复性任务占据了。而现在，这感觉就像是我们为深度思考腾出了额外的脑力空间。对你们来说，你们正在解决一些技术上最具挑战性、但也极其重要的问题。我们可以利用这些工具变得无比强大……

<details>
<summary>Original English</summary>

**Speaker B**: I think this is the best time ever to be a creative human being or really be any human because like the long a long arc of history starting from when we decided that hunting and gathering I don't know about that. I think I'm going to settle down and and and do this whole agriculture thing. I think that started thousands of years of drudgery. Sometimes you wonder why did we actually do agriculture because everything I've seen seems like agriculture was probably a net loss on the short term. It was the only benefit I see in the long run is that if you were a hunter gatherer and you got sick or born with a genetic illness or got injured that was like you're in trouble. Uh there's not much more we could do for you. The medicine just didn't really exist. But ultimately I think the crowning achievement in my mind to civilization is where the sick people among us in society are not seen as burdens but people who we want to help. And that isn't true in the history of the animal kingdom including humans. Um it's a sad reality but it's true. Whereas now because of medicine we we see people who are sick as people we want to help who we can help and we can help them they could become even more productive members of society if that's the thing that you care about. If to fast forward that to now, I think that so much of creative work, day-to-day work, if you look at as a pie chart, time is our most precious resource. So much of it was being taken up by repetitive tasks that actually didn't require much thought or creativity. And now it's like we've created like this additional headsp space for deep thinking. And for us, you're solving some of the most technically challenging but but important problems. We can use these tools to become wildly more

</details>

<!-- chunk 12/13 -->

### 药物发现中的 Pearl 模型评估与瓶颈

**Speaker A**: ……高效且具有创造力。这也适用于药物化学家、药物研发人员以及计算辅助设计（CAD）科学家，他们是我们的直接用户，现在他们可以成为药物发现项目的宏观战略家。当你拥有数百名药物发现科学家，在大型数据中心全天候 24/7 地工作时，你在药物发现方面获得的产出将会更大。特别是如果这些工具被掌握在知道自己在做什么的专家级科学家手中时。

<details>
<summary>Original English</summary>

**Speaker A**: ...productive and creative. And that goes to the med chemists, drug hunters, CAD scientists who are our direct users that they can be grand strategists for a drug discovery campaign. And when you have hundreds of drug discovery scientists working 24/7 on large data centers, just the output you get in terms of discovery is just going to be greater. especially if it's used in the hands of expert scientists who know what they're doing.

</details>

**Host**: 我们早些时候或许就该谈谈这个，但你们的 Pearl 模型最近基于一个开放数据集挑战（你早先提到过）取得了一些非常令人兴奋的结果。抱歉我们之前没聊到，但我想给你个机会谈谈这个。所以这个叫做 OpenBind 挑战的，是 EV A721A 蛋白酶吗？那是一个非常非常难的靶点，有很多因素使得整个社区或现有的计算方法很难在内部起作用，而你们在内部运行了它，我想你们得到了一些很有趣的结果。

<details>
<summary>Original English</summary>

**Host**: We probably should have talked about this earlier, but you have some really exciting results from your Pearl model based upon essentially a recent open data set challenge that you alluded to earlier. Um sorry we didn't talk about it before, but I would like to give you a chance to talk about this. So there's this open bind was it EV A721A protease uh which was a very very hard target had a lot of things which made it hard for the community or for co-olding methods to internally work and uh you ran this internally and I think had some you know fun results.

</details>

**Sergey**: 是的，我是说我们也可以回到刚才关于模型评估（evals）的讨论上，以及普遍意义上评估存在的问题。如果你看看开源模型以及它们在公共基准测试上的表现，你会发现它们在各方面都非常相似。当 OpenBind 提出这个新的基准测试时，令人惊讶的是，你会看到模型在上面的表现存在很大的差异。部分原因在于它只是一个单一的靶点。
（好吧，我明白了。）
但这同时也是因为这个靶点是那些模型在训练期间从未见过的。所以之前没有人针对那个特定的靶点进行过优化。没有人在上面“攀登”过。所以对我们来说，看到我们的模型在这个我们在训练或开发模型时也从未见过的特定靶点上，能“开箱即用”地表现出怎样的水平，是非常有趣的。所以当这个挑战出现时，我们显然想要去研究一下。我们在那上面运行了 Pearl 系统，我们对结果感到真切的惊讶和兴奋。我们的数据远远高于其他已发布的、公开可用的模型。对我来说，这反映了 Pearl 在真实的药物发现项目中的实际表现。因为我们以前在内部项目或合作项目中看到过这种数字上的差异和转变，但我们不能谈论它们，因为很多数据要么是合作数据，要么是内部数据，我们无法披露。而在这里，你有一个完美的例子：这是一个外部靶点，但我们事先并不知道，我们就直接在上面运行了。然后我们看到了这种惊人的差异。所以这正是让我感到兴奋的地方。这个靶点还有一些特殊之处，比如它有一个灵活的环（flexible loop），当你把配体（ligand）插入到正确位置时，这个环需要发生移动，而很多方法就是无法处理这一点。Pearl 表现极其出色的地方在于它算出了如何移动这个环，而且我们对每一个姿态的预测基本上都是正确的。我们很好地预测了这种移动。是的，所以这是令人兴奋的部分。

<details>
<summary>Original English</summary>

**Sergey**: Yeah, I mean we can also go back to our conversation of on evals um and what's wrong with evals in general. Like if you look at the open source models and their performance on public benchmarks, it's kind of very similar across the board. Um and what was surprising when open bind came up with this new benchmark is that you see a wide variety of performance of the models on that and well in part of it is because it's just a single target. Okay, I get it. But it's also because this is the target that those models haven't seen during the training. So nobody has optimized for that specific target before. Uh nobody climbed on it. Um so it was very interesting for us to see how our models is going to perform out of a box on this particular target that we also have never seen before during training or when we developed this models. Um so when it came up we obviously wanted to look into it. We run pearl system on that uh and we were genuinely surprised and excited about results. our numbers are way higher than um other published uh openly available models. And to me it reflects how Pearl actually behaves in real drug discovery programs cuz we have seen this kind of number differences shifts in internal programs or partnership programs before but we were unable to talk about them cuz a lot of this data is like it's either partnership data or internal data we cannot disclose it. Here you have a perfect example where it's an external target but we didn't know um and we just run on it. Um and we see this staggering difference. Um so that's kind of what makes me excited. And there are some specifics of this target like it has this flexible loop but needs to move uh when you insert your liant in into the right location and a lot of methods just are unable to handle it. And where Pearl was exceptionally good is figuring out how to move the slope and we are basically correct for every single pose. Uh like we're predicting really well uh this movement. Um yeah so that's the exciting part.

</details>

**Host**: 我对此很好奇。Pearl 是什么特性让它能够如此建模这种动态靶点？

<details>
<summary>Original English</summary>

**Host**: I'm curious about this. What is it about pearl that allows it to model a dynamic target like that?

</details>

**Sergey**: Pearl 模型，就其训练方式而言，它是被训练来共同预测蛋白质结构和配体的。而蛋白质结构和配体结合在一起时，它们的形状或形态并不一定与孤立状态下的蛋白质相同，所以整个训练过程有点像是在把 Pearl 往那个方向引导。

<details>
<summary>Original English</summary>

**Sergey**: Pearl model the way it's trained right it's trained to predict together protein structure and liant um and like protein structure and ligan together they're not necessarily in the same shape or form as the protein and isolation so the whole training process it kind of nudges pearl into that direction

</details>

**Host**: 所以在训练集中有很多类似的例子，在结合发生时，构象会发生改变，呈现这种动态性质？在整个训练集中存在这种诱导契合（induced fit）吗？

<details>
<summary>Original English</summary>

**Host**: so are there lots of examples in the training set like that where the there's this dynamic nature where once when during the binding embed the confirmation changes. There is induced fit throughout the training set.

</details>

**Sergey**: 是的。

<details>
<summary>Original English</summary>

**Sergey**: Yeah.

</details>

**Host**: 这可能是从你们所使用的基于物理学的模拟中继承下来的。

<details>
<summary>Original English</summary>

**Host**: this is probably inherited from the physics based simulations that you're using.

</details>

**Speaker C**: 这肯定有帮助。我认为 Sergey 提到的另一个要素是，我们并没有仅仅在相同的基准测试上追求分数最大化。我们显然也会发布测试运行和分子姿态。去年年底在 GTC 大会上与英伟达联合发布 Pearl 技术报告时，我们就公布了最先进的数据、运行情况和分子姿态。我们使用了 PoseBusters，Pearl 在那些基准测试上表现是最好的。我们确实做到了。然而，正如 Sergey 所暗示的，在我们研究的合作药物靶点上，Pearl 与次佳模型之间的差距甚至更大。部分原因反映了我们公司的目标并非是在基准测试上刷高分。公司的目标是为生物技术和制药公司创造价值，这些公司通常致力于研究那些不同于 PDB（蛋白质数据库）中已有内容的、困难的药物靶点。因此，我们必须以一种能够进行泛化外推的方式来构建模型。而 OpenBind 挑战仅仅是这一点的最新例证。

<details>
<summary>Original English</summary>

**Speaker C**: It certainly helps. I think the other component that Sergey alluded to was um we haven't just been benchmark maxing on the same we obviously publish and runs and poses. We published the state-of-the-art numbers and runs and poses last year when we published the Pearl technical report with Nvidia at GTC at the end of last year. We use runs and poses, we use pose busters. Pearl does the best on those benchmarks. We did that. Um, however, as Sergey is alluding to, the gap from Pearl to next best model is even larger on the uh partner drug targets that we work on. And um what that's in part a reflection of is the objective of our company is not maxing benchmarks. The objective of the company is creating value for biotechs and pharma companies that are usually working on hard drug targets that are different from what's in the PDB. And so we've had to build the models in a way that are able to extrapolate. And the open buy challenge was just the latest example of that.

</details>

### 行业瓶颈与未来展望

**Host**: 在我们结束之前，我们总是会问两个问题。一个是，如果你能用行政命令消除你们行业的一个瓶颈，它会是什么？我是说这不是指输入、输出或商业方面，那会是什么呢？

<details>
<summary>Original English</summary>

**Host**: Before we wrap up, we always ask two questions. One is if you could remove a bottleneck from your industry by fiat, right? So, and this is not like for inputs, outputs, uh business, what would that be?

</details>

**Sergey**: 我可以说我目前面临的主要瓶颈在于 GPU。

<details>
<summary>Original English</summary>

**Sergey**: I can say where my main bottleneck right now is is in GPUs.

</details>

**Host**: 好的。大家都这么说。

<details>
<summary>Original English</summary>

**Host**: Okay. Everyone says,

</details>

**Sergey**: 哎，是啊。你看，GPU 的价格在不断上涨，而 LLM（大型语言模型）公司几乎吸干了市场上所有的 GPU 算力。我坚信我们正在做的事情对人类来说是真正重要的，比如为你自己、为你的亲人发现新药，这是我们所有人生命中某个时刻都会需要的东西。所以，我认为消除药物发现领域的 GPU 瓶颈是非常重要的。

<details>
<summary>Original English</summary>

**Sergey**: uh, yeah, look, GPU prices are going up and up and up and LLM companies are kind of sucking up all of the GPU capacity out there. And I firmly believe that what we're doing is genuinely important for humanity like discovering new medicines for for yourself, for your loved ones is it's something that we all need at some point in our life. Um, so I think it's very important to unblock that GPU bottleneck for drug discovery.

</details>

**Host**: Anthropic 真的因为购买 GPU 阻碍了科学发展吗？

<details>
<summary>Original English</summary>

**Host**: Is Enthropic actually throttling science because of GPU purchases?

</details>

**Sergey**: 你讲话开始带刺了哦？

<details>
<summary>Original English</summary>

**Sergey**: Are you getting spicy?

</details>

**Host**: 我不知道该不该问，但你们考虑过非英伟达的选项吗？我的意思是，我猜你们是英伟达的合作伙伴之类的。但是我看有些公司正在转向多架构模型，以便利用其他供应商来应对短缺问题。

<details>
<summary>Original English</summary>

**Host**: I don't know if you can ask this, but are you looking at nonvidia? I mean, I guess you guys are Nvidia partners, whatever. So, but like there I've seen that some companies are pivoting towards a multi- architecture model so that you can take advantage of other suppliers because of the shortage.

</details>

**Sergey**: 英伟达一直非常支持我们。他们向 Genesis 投资了两次，我们合作非常密切。不仅是在资金方面，我们还共同优化内核程序。你知道，Pearl 是由 Genesis 和英伟达共同研发的。他们与我们一起公布了 OpenBind 的结果，我们对此非常感激。他们是一家非常非常大的公司，而你知道，我们的规模无法跟 Meta 这样的客户相比。所以尽管如此，他们仍然给予我们时间和关注，我们感到很感激。
但我认为其中部分原因是出于自身利益考虑：显然没人能精准把握市场的时机，但在传统的 LLM 领域，针对聊天机器人、代码生成等方面的炒作和投资数量巨大，在某个时刻，相对投资额而言，剩余的超额收益（alpha）将达不到人们的预期。我认为，无论经济如何起伏，药物始终是高需求产品。我觉得，无论是出于造福人类的愿望，还是出于寻找“下一个风口”的自利动机，包括英伟达在内的芯片制造商都会越来越希望在生命科学领域进行更多投资，因为这永远是高需求的。而在纯粹的 LLM 领域里，还能剩下多少超额收益已经变得有些可疑了。我的意思是，所有的 LLM 公司现在都已经开始涉足生命科学领域了，对吧？有 GTB Roslin，有云计划，还有很多初创公司等等。

<details>
<summary>Original English</summary>

**Sergey**: Nvidia's been a great supporter of us. They've invested twice in Genesis and we collaborate closely like you know not just in terms of the capital but we optimize kernels together. Um you know we co- pearl was co-authored by Genesis and Nvidia. they um publicized the open mind results with us. We've been very grateful for that. They're a very very very big company and you know we're we're not at the scale of a of a customer like a meta or something. So we're grateful that they've given us time and attention nonetheless. But I think part of that is is a self-s serving aspect here which is that obviously like no one can time time the market but um the amount of hype and investment in the traditional LLM space for chatbots coding sort of thing at some point the amount of alpha will not be what's desired compared to the amount of investment and I think regardless of the vicissitudes of the economy medicines will always be high in demand and I think whether it's a desire to help humanity or a self-s serving interest in looking for the next the next big thing I do think that chipmakers including Nvidia are going to want to get a lot more invested in life sciences because will always be high in demand and the amount of alpha left in pure LLM space is just getting a little questionable. I mean, all the LLM companies are starting looking into life sciences right now anyway, right? They GTB Roslin, there's a cloud initiative, there's lots of startups and whatever.

</details>

**Speaker C**: 是的。我们认为这些对我们来说都是极佳的顺风车。

<details>
<summary>Original English</summary>

**Speaker C**: Yep. We think those are all great tailwinds for us.

</details>

**Host**: 没错。那你呢？除了 GPU 之外，你认为还有什么瓶颈？

<details>
<summary>Original English</summary>

**Host**: Yeah. And then what what about you? What what's the bot on that besides GPUs?

</details>

**Speaker C**: 哦，在这个问题上，我毫无疑问和 Sergey 的答案一样。如果我能挥舞一根魔杖，我只希望能得到一个巨大的 H100 集群。那……那将会非常棒。

<details>
<summary>Original English</summary>

**Speaker C**: Oh, I had the same answer as Sergey for sure. If I could wave a magic wand, I'd love to have just a enormous H100 issue cluster. uh that that would be that would be amazing.

</details>

**Host**: 然后我们通常问的第二个问题是，你对我们的观众有什么行动号召吗？也就是说，这里的 AI 工程师、科学家们，参与到某些事情中来，或者来申请职位之类。对他们有什么行动号召吗？

<details>
<summary>Original English</summary>

**Host**: And then the second question we ask is just do you have a call to action for our audience? So meaning uh AI engineers plus scientists um get involved with something, come apply for jobs, uh do like what's the call to action for them?

</details>

**Sergey**: 我们绝对在招聘。我们绝对在寻找这个领域的顶尖人才。就我个人而言，我从 LLM 领域跨行到了药物发现领域。在加入 Genesis 之前，我从未做过药物发现。我觉得这个领域令人着迷，极具吸引力。你知道，在 LLM 公司里，你经常会看到研究科学家们对研究架构感到兴奋，但却有点被迫去干那些无聊的事情。老实说……

<details>
<summary>Original English</summary>

**Sergey**: We are definitely hiring. We're definitely looking for top talent in the space. And I personally I transitioned from LLM space to drug discovery. I've never d done drug discovery before during genesis. I find this field fascinating and extremely interesting. Um you know in LLM companies you often find research scientists excited about working on architectures but like kind of forced to work on boring stuff. And honestly

</details>

<!-- chunk 13/13 -->

### LLM 架构的同质化与 Genesis 的差异性

**Guest**: 架构相对来说比较无聊。我不知道，我大概会得罪你们一半的听众。

<details>
<summary>Original English</summary>

**Guest**: architectures are relatively boring. I don't know. I probably alenate half of your audience.

</details>

**Host**: 我想他们可能也是这么想的。但说到底，那不过就是 Transformer 层，就像2017年发表的那篇论文一样，今天你去任何一家大语言模型（LLM）实验室，你都会在他们的模型中看到非常非常相似的结构。

<details>
<summary>Original English</summary>

**Host**: I think they probably think the same thing. But it's like it's a transformer layer in the end like paper was published in 2017 and you go to any yellow lamb lab today you will see a very very similar pieces uh in their models

</details>

**Guest**: 是的，可能会有一点混合专家模型（MoE）的色彩，但在其他方面，架构从根本上来说与2017年发现的非常相似。对吧，我们的架构和模型实际上非常不同，而且做起来非常非常有趣。所以，如果有人对研究架构充满热情，那么这个领域实际上是一个非常非常有趣的工作空间。

<details>
<summary>Original English</summary>

**Guest**: yes there is a little bit of flavor of moes but otherwise architectures are fundamentally very similar to what was discovered back in 2017 right well our architectures and our models are actually very different and very very interesting to work with so if somebody is excited excited about working on architectures. Well, this space is actually very very interesting place to work.

</details>

**Host**: 是的，我想评论一下。不仅你们的架构与 LLM 领域非常不同，而且你们实际上也与许多其他生物机器学习（bio ML）领域正在做的事情非常不同。可以说，无论是在其子领域还是在更广泛的意义上，它都有点独一无二。

我们看到作为最近的嘉宾，你们请到了 ESM Fold 的其中一位创始人。

<details>
<summary>Original English</summary>

**Host**: Yeah, I like to comment. Not only are they very your architecture is very different from the LLM space, but you're actually you're also very different from what a lot of the other bio ML space is doing as well. Like it's it's uh sort of unique both in their subdomain and more broadly.

We saw as a recent guest you had one of the uh the the progenitors of ESM fold.

</details>

**Guest**: 是的。嗯，他们引用了我们几个月前开源发表的模型架构论文。因此，作为一名 AI 研究员，在 Genesis 这里做的工作有许多发表论文、开源以及影响这个领域的机会，除了通过与真正制造能改变人们生活的药物的顶级客户合作来影响这个领域这一显而易见的方式之外。所以，这不仅在智力上令人难以置信地投入，而且还有许多影响领域并打响自己名气的机会。当然，如果你愿意，你也可以只是留在大语言模型公司里做一台机器上的齿轮。而且——

<details>
<summary>Original English</summary>

**Guest**: Yeah. Um uh yeah they cite our model architecture paper that we published in open sourced a few months ago. So the work that you do here at Genesis as an AI researcher there's lots of opportunities for publication open source and influencing the field beyond the obvious ways to influence the field by working with top customers that are actually making medicines that change people's lives. So, it's both incredibly intellectually engaging and a lot of opportunities to influence the field and and get your name out there. But if you want, you could also just stay being a cog in the machine of an LLM company. And

</details>

**Host**: 没有冒犯的意思，没有冒犯的意思。是的。

好的。非常感谢你们来和我们交流。我个人非常享受这次谈话。希望观众也是如此。Evan、Sergey，谢谢你们。我们很期待看到未来的发展。嗯，希望你们能借此收到一些优秀的求职申请。

<details>
<summary>Original English</summary>

**Host**: no shade, no shade. Yeah.

All right. Well, thank you so much for for coming and speaking with us. I've personally really enjoyed this. Hopefully the audience as well. Evan, Sergey, thank you. And we look forward to seeing how things develop. Um, and hopefully you get some good job applications out of the

</details>

**Guest (Evan/Sergey)**: 是的，我们很喜欢这个节目，所以非常感谢能抽出时间来聊聊。

<details>
<summary>Original English</summary>

**Guest (Evan/Sergey)**: Yeah, we we love the show, so we really appreciate uh taking the time to to to chat.

</details>

**Guest (Evan/Sergey)**: 是的，感谢你们邀请我们。

<details>
<summary>Original English</summary>

**Guest (Evan/Sergey)**: Yeah, thank you for having us.

</details>