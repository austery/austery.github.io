---
author: Latent Space
date: '2026-04-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=uqM8qjbLRHA
speaker: Latent Space
tags:
  - spatial-transcriptomics
  - drug-discovery
  - foundation-model
  - self-supervised-learning
  - precision-medicine
title: Transformers 攻克癌症临床试验：Noetik 如何利用多模态空间转录组学破解 95% 的失败率
summary: Noetik 创始人 Ron Alfa 和 Dan Bear 深入探讨了如何利用 AI 基础模型重塑癌症药物研发。通过在实验室生成海量的人类肿瘤多模态数据（包括空间转录组和蛋白质染色），他们构建了“虚拟细胞”模型。该模型能通过简单的 H&E 图像预测复杂的生物学特性，帮助制药公司精确筛选临床试验患者，从而解决癌症药物极高的临床失败率。此外，他们还分享了与 GSK 达成的 5000 万美元模型授权协议背后的战略意义。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Ron Alfa
  - Daniel Bear
companies_orgs:
  - Noetik
  - GSK
  - Recursion
products_models:
  - OctoVC
  - Tario
  - Perturb-map
media_books: []
status: evergreen
---
### Noetik 的愿景与核心假设

**Ron Alfa**: 我们开设了实验室，雇佣了团队，准备好了所有仪器，开始采购肿瘤样本。当时完全没有任何先例证明这能行——成功的概率几乎是零。我们只是开始生成数据，采购人类肿瘤，进行处理。我们建立了完整的处理流程，将肿瘤制成阵列。你可能会有长达两周的运行期，期间只处理两张载玻片。我们没日没夜地跑了几个月的数据，甚至还无法训练出一个模型。我们就这样坚持构建。大约 18 个月后，我们才开始尝试：嘿，我想知道能不能基于这些训练出一个模型？当时这并不是显而易见能成功的。

<details>
<summary>Original English</summary>

**Ron Alfa**: So we basically opened the lab, we hired a team, we got all the instruments, we started sourcing tumor samples and there was no prior here that any of this would work—like zero. We just started generating data and sourcing human tumors, processing. We built this whole processing pipeline to get the tumors into these arrays and the formats. So you've got like these two-week runs where you're processing two slides and we're just churning data for months and we couldn't even train a model. So we sort of just built all this and then like let's say 18 months later, "Hey, I wonder can we train a model off this?" And then it was not obvious.

</details>

**Dan Bear**: 是的，当时确实没有什么现成的东西可以参考。虽然当时已经有了针对单细胞数据的 **Transformers**，但并没有现成的数据集可供人们开发。我们做了大量的**定制化模型构建**。

<details>
<summary>Original English</summary>

**Dan Bear**: Yeah, there wasn't really like anything major to go off of. I mean there were like transformers developed for single cell data. There just weren't really data sets out there that people had been able to develop on. We do a lot of like custom model building.

</details>

**主持人 (R.J. Haniki)**: 大家好，我是 R.J. Haniki，这位是 Brandon Anderson。我们是 *Late Space Science* 播客的共同主持人。今天我们非常高兴能邀请到 **Noetik** 的几位核心成员。

<details>
<summary>Original English</summary>

**R.J. Haniki**: Hi there. I'm R.J. Haniki and this is Brandon Anderson. We're the co-hosts of the Late Space Science podcast and today we're really happy to be in the studio with some of the people from Noetic.

</details>

**Ron Alfa**: 我是 Ron Alfa，Noetik 的联合创始人兼 CEO。我接受过执业医师和科学家的训练。我的业余爱好是发表一些关于“AI 治愈癌症”的毒辣见解（Hot Takes）。

<details>
<summary>Original English</summary>

**Ron Alfa**: I'm Ron Alfa, co-founder and CEO of Noetic, physician-scientist by training. My hobbies are making hot takes about AI curing cancer.

</details>

**Dan Bear**: 大家好，我是 Dan Bear，Noetik 的 AI 副总裁。我原本是一名生物学家，在神经科学领域完成了博士学位，之后转向计算神经科学、计算机视觉和**自监督学习**。过去几年我一直在 Noetik 从事 AI 研究。

<details>
<summary>Original English</summary>

**Dan Bear**: Hi, I'm Dan Bear. I'm VP of AI at Noetic. I'm a biologist by training. I did PhD work in neuroscience and then moved into computational neuroscience, computer vision, self-supervised learning and have been doing AI research at Noetic for the past few years.

</details>

**主持人**: 也许我们应该先聊聊 Noetik 是什么？为什么要创立它？Noetik 与其他那些“虚拟细胞”公司有什么区别？

<details>
<summary>Original English</summary>

**Host**: Maybe we should start with what is Noetic? Why did you found it? What is the difference between Noetic and the other virtual cell companies?

</details>

**Ron Alfa**: 我们可以先从一个非主流的假设开始，这也是创立 Noetik 的初衷。我们都知道一组数据：90% 到 95% 的癌症药物在临床阶段都会失败。为什么？我们的假设是，失败并不是因为我们的药理学做得不好，也不是因为靶点选择有问题。事实上，我们在药物研发这个过程中的水平比历史上任何时候都要高。我们认为，大多数药物失败是因为我们**无法选对能对该药产生反应的患者**。在癌症研究中，你经常看到没有安慰剂效应的试验：有些患者产生了反应，这告诉你背后确实有一定的活跃生物学机制，但你面临的是患者筛选的问题。Noetik 的核心假设就是：我们能否构建出能从根本上理解**患者生物学**的模型，从一开始就帮助你在正确的患者群体中定位分子？

<details>
<summary>Original English</summary>

**Ron Alfa**: Maybe just start with a little bit of a contrarian thesis, which is really the reason for founding Noetic. We all know the numbers that 90% to 95% of cancer drugs fail in the clinic. Why do they fail? So our thesis is they fail not because we're bad at pharmacology, not because we're bad at target selection. We're actually better at that process than we have ever been in the history of drug development. Most of those drugs fail, we'd argue, is because we're bad at selecting which patients those drugs will work in. And often times you see trials where there is no placebo effect in cancer. Some patients respond to these drugs and if you have a patient that responds, that tells you something that there's some biology that's active there. But you have a problem in patient selection. And so really that's the thesis behind our company: can we build models that can fundamentally understand patient biology from the very beginning and help you position molecules in the right patient population?

</details>

### 逆向翻译：从患者到药物

**主持人**: 所以你们使用模型至少在某种程度上是为了选择患者队列，而不只是设计分子。

<details>
<summary>Original English</summary>

**Host**: So you're actually using the models partly at least to select the patient cohort, not just molecules.

</details>

**Ron Alfa**: 这可以双向运作。你可以说，“我认为这个分子会表现良好，因为我了解某些患者群体的特征”；你也可以说，“我认为这个患者群体是这个分子的最佳匹配”。这就是模型的威力所在——一旦你基于患者数据训练了模型，你就可以在方程式的两端都使用它。

你可以用它们从患者数据中直接**发现新靶点**，这通常被称为**逆向翻译（Reverse Translation）**。也就是说，从人类出发，通过理解该追求哪些靶点来开发药物。但你也可以直接在患者数据上使用模型。如果你有一个二期或三期临床试验，你可以使用这些模型来理解试验中哪些患者或什么样的底层生物学特征是药物反应的预测指标。我们最近在这方面做了大量工作。

<details>
<summary>Original English</summary>

**Ron Alfa**: And that's sort of the power of the models. Once you've trained these models on patient data, you can use them on both sides of the equation. So you can use them for discovering new targets directly from the patient data which people often refer to as reverse translation. So starting from humans and then trying to understand which targets to go after and then you can use that to develop molecules. But you can also use them directly on patient data. If you have, let's say, a Phase 2 or Phase 3 trial, you can use these models to understand which patients or what underlying biology of the patients in the trial is a predictor of response. And we've been doing a ton of that recently.

</details>

**主持人**: 你们是在做很多“挽救”那些效果不佳的试验的工作吗？

<details>
<summary>Original English</summary>

**Host**: Are you doing a lot of like rescuing trials that had a bad effect?

</details>

**Ron Alfa**: 我们正在通过二期、三期试验的数据，使用模型对患者活检样本进行推理，以了解是否存在能帮助我们设计下一次试验的底层生物学特征。我们还没公开过这些细节。

<details>
<summary>Original English</summary>

**Ron Alfa**: We are doing a lot of looking at data from Phase 2, Phase 3 trials and then using the models essentially to run inference on patient biopsies and understand whether there's underlying biology that would help us design the next trial. We haven't shared any of that yet.

</details>

**主持人**: 癌症因其复杂性而臭名昭著。所谓的“治愈癌症”几乎是一个没有意义的虚假命题。你的观点是，即使在同一种癌症类型甚至亚型中，也存在许多不同的患者群体，每个群体对药物的反应都不同。而你们现在可以弄清楚，为什么某些特定的亚群在大部分人都没有反应的情况下，却能表现良好。

<details>
<summary>Original English</summary>

**Host**: So cancer is kind of like infamous in that there are many different types of cancers. Whenever it says like "cure cancer," that is almost a meaningless vacuous statement. So your point is even amongst cancer or a specific type and subtype, there's a bunch of different patient populations that each one of them will respond differently to drugs. And your point is you can figure this out right now—that some sub-population will do well and respond to this drug when you think generally speaking the rest of the population would not.

</details>

**Dan Bear**: 完全正确。我甚至想更进一步：实际上没有人真正知道这些“亚型”是什么。有些癌症起源于特定组织（如肺部），在一个多世纪里，病理学家一直根据肉眼观察对它们进行亚型分类。这些分类确实与某种本质（即功能性亚型）有联系。但我们的假设是，如果你查看更丰富的数据，比如我们在实验室生成的**多模态数据**，你会发现，以前人们认为的一种肺癌亚型，实际上是三种截然不同的癌症亚型。这对于确定哪些患者应该接受哪些药物至关重要。

<details>
<summary>Original English</summary>

**Dan Bear**: Yeah that's exactly right and I would maybe even go further and say like nobody actually knows what the subtypes are. There are cancers that originate in a certain tissue like the lung that have been classified into subtypes based on pathologists looking at them for more than a century. And those subtypes certainly have some connection to the real functional subtypes of disease there. But our thesis is kind of that if you look at the data—a much richer kind of data, the multimodal data that we're generating in our lab—we're going to see that actually what people thought was one subtype of lung cancer is really three distinct subtypes of cancer. And that is going to be critical for figuring out which patient should get which drugs.

</details>

### 传统模型的局限：弗兰肯斯坦式的细胞

**Ron Alfa**: 我想回到你最初的一个问题。为什么在肿瘤学领域，我们会陷入无法选对患者的困境？当你开发新药时，你会在培养皿里进行细胞培养实验。这些细胞通常是**细胞系**，已经存在了 40、50 年。它们是“永生化”的，拥有异常数量的染色体，基因表达模式已经完全不代表人类体内的任何已知细胞。这些基本上是**弗兰肯斯坦（Frankensteinian）式的细胞**。

你可以用这些培养皿里的细胞系做实验，或者转移到动物模型中。在肿瘤学中，你通常有一组不同的动物模型和癌症类型进行测试。通过这些实验，我们说服自己某些细胞系是肺癌或结肠癌，甚至在小鼠身上，我们把它们植入皮肤下等奇怪的地方，然后给小鼠用药，看它们如何反应。但最终，这中间存在巨大的鸿沟，因为它们在大多数情况下无法转化为**患者生物学**。

这些癌症细胞系，即使是源自结肠癌，在许多情况下甚至不具备人类结肠癌的突变。制药公司 20、30 年来一直在这样做：开发一种药物，然后针对数百种这样的细胞系进行测试。这不是一个前沿实验，你可以外包给任何合同研究组织（CRO）。然后你坐下来分析，哪 50 个结肠癌系有反应？这是否能映射到人类生物学？问题在于，这些细胞系作为一种抽象，与人类患者毫无关联。

结果是，无论你在临床前做了什么，分子的临床团队都会说：由于你的数据没有提供任何关于该选择哪些患者的洞察，我们只能进行一项**开放标签（Open-label）研究**，招募所有符合条件的肿瘤患者，看看哪里能出信号。想象一下，在早期试验中，你只有 50 个病人，你还在尝试不同的剂量，甚至不知道安全边界在哪里，同时还要摸索信号在哪。统计学上，你往往看不到预期的反应者，于是这些分子就被取消了。

<details>
<summary>Original English</summary>

**Ron Alfa**: Whenever you make a new drug, you do a set of experiments in cell culture—cells in a dish. Those cells are often cell lines. These cell lines have existed for 40, 50 years and they're immortalized. So they have genomes that allow them to persist that have abnormal numbers of chromosomes. They have gene expression patterns that don't represent any known cell in like the human body really. These are sort of Frankensteinian cells. So you can do your experiments in these cell lines in a dish or then move these into animal models. But ultimately there's a big gap because they don't translate to patient biology most of the time. So what happens is ultimately no matter what you do pre-clinically, the clinical team says, "Look, we don't really know how to design this trial because none of the data that you've produced gives us any insight on which patients to run." So we're basically going to enroll an open label study—all tumors, all patients—and see where we get signal. Statisticslly, you don't see very many responders and then these molecules get canceled.

</details>

### 无偏见的 AI：刻画大自然的关节点

**主持人**: 那么在 Noetik 系统中，你们是帮助制药公司通过特定的遗传或转录组特征来刻画患者反应，然后通过测序进行匹配吗？

<details>
<summary>Original English</summary>

**Host**: So in your Noetic system, you help the pharmaceutical company to characterize patients with a certain genetic or transcriptomic profile, and then you sequence the patient to say "yes, this is a match"?

</details>

**Ron Alfa**: 我们的方式比这更加无偏见。我们让模型通过**自监督学习**，去学习比如肺癌中有多少个在治疗上相关的亚型。这些亚型可能是由大规模基因变化驱动的，也可能是由免疫系统变化驱动的。

<details>
<summary>Original English</summary>

**Ron Alfa**: I would say we are even less biased than that. We want the model to learn, let's say from lung cancers, how many different therapeutically relevant subtypes of lung cancers there are just from self-supervised learning from the data. Those subtypes could be driven by large genetic changes, they could be driven by immune changes, they could be driven by any biology that the model is learning in the process of training.

</details>

**Dan Bear**: 虽然目前的生物标志物追求简单化（比如患者是否有某个特定的突变，或者某个单一蛋白质的染色情况），但没有理由认为癌症的生物学是如此简单的。这些简单的标志物与临床成功的相关性很弱。我们的假设是，如果你能“**刻画大自然的关节点**”（Carve nature at its joints），找出真正的机制，那么药物与特定亚型之间的相关性将会强得多。

<details>
<summary>Original English</summary>

**Dan Bear**: The biomarkers that people have been using are biased towards simplicity—does the patient have this particular mutation or stain for this single protein. But there's no reason to think that biology or the biology of cancer is that simple. The hypothesis really is here: again, if you were to carve nature at its joints and figure out what's really going on, is there these five subtypes that the correlation there between which patients you give a particular drug and whether you have success is much stronger.

</details>

### 数据战略：为什么必须自己生成数据？

**主持人**: 你们在实验室里生成了大量数据。为什么不使用现有的公开数据库？

<details>
<summary>Original English</summary>

**Host**: You mentioned the lab, you do a lot of data generation in the lab. Why do you think that that versus using existing public repositories is appropriate?

</details>

**Ron Alfa**: 这是一个关于 AI 和生物学的毒辣见解：生物学的数据量级还远没有达到构建其他领域模型时的那种规模。你很难仅通过收集零散数据来强力解决这些问题。

以 **PDB（蛋白质数据库）** 为例，它是过去 50 年里精心设计的。有人预见到这个数据集能帮助解决蛋白质折叠问题，并花了几十年时间去收集。它不是从网上随手抓取的随机数据。在生物领域，你必须对生成什么样的数据以及如何生成这些数据有明确的**目的性**。你必须在一开始就具备前瞻性：我想训练什么样的模型？我需要从中学到什么？这就是我们采取这种方式的原因。

<details>
<summary>Original English</summary>

**Ron Alfa**: Another hot take I have in AI and bio is you're sort of not at the order of magnitude of data that you are in other spaces of building training models. And so it becomes really hard to brute force these problems just by collecting data. PDB was designed and has been built over the past 50 years. It's not an accident that that data set exists. In bio, you really need to be intentional about the data that you generate and how you generate it. You have to have some foresight around well what are the models we're going to want to train. That's why we've taken this approach.

</details>

**Dan Bear**: 一个好的对比是 **ImageNet** 数据集，它通过展示神经网络在物体分类上优于其他方法，开启了计算机视觉的深度学习革命。ImageNet 有 120 万张经过精心策展的高质量图像，而不是来自互联网的随机图像。

<details>
<summary>Original English</summary>

**Dan Bear**: A good comparison is to the ImageNet data set which kicked off the deep learning revolution in computer vision. ImageNet is at least 1.2 million images, very carefully curated. These are high quality images, not like random images from the internet.

</details>

**Ron Alfa**: 我们目前生成的数据量级大约就在这个水平（百万级）。当然，在图像和语言模型（LLM）领域，人们的数据量级已经大得多。我们认为，在算法层面看到实质性进展之前，必须先将数据提升到那个规模。

<details>
<summary>Original English</summary>

**Ron Alfa**: With the data that we're generating, we're around that scale right now. But people have gone much larger in image and language data sets for LLM. So we think that we need to get the data up to that scale before we can really see the meaningful progress on the algorithm side.

</details>

### 多模态数据的“三位一体”：H&E、蛋白质与空间转录组

**主持人**: 你们在收集什么样的数据？据说你们使用了一些非常专门的仪器。

<details>
<summary>Original English</summary>

**Host**: What is the data you're collecting? My understanding is you use some pretty specialized instruments and gathering very specific data sets.

</details>

**Ron Alfa**: 如果你想训练一个能理解人类生物学的基础模型，从第一性原理出发，你会怎么做？首先，你需要**组织层面的生物学**。
1.  **H&E 染色 (病理图)**：这是临床标准。每个被切除肿瘤的患者都会做 H&E 染色，它是紫色的病理标本。病理学家通过观察细胞结构来识别不同的肿瘤分类。
2.  **蛋白质染色 (多重免疫荧光)**：H&E 无法揭示所有细胞类型。我们需要知道哪些是免疫细胞及其亚型（如 T 细胞、B 细胞）。肿瘤的**免疫环境**是决定患者是否有反应的核心。
3.  **空间转录组学 (Spatial Transcriptomics)**：为了研发药物，我们需要基因层面的机制信息。我们将 DNA 转录成的 RNA 在同一张切片上进行空间定位。我们可以检测 1,000 到 19,000 种不同的基因，这些基因表现为空间中的亮点。

你可以把这看作是生物学的“中心法则”。我们将这三个层面堆叠在一起：组织、细胞和分子信息，用来训练模型。我们的空间转录组数据极其密集，你可以把它看作一张不仅有红绿蓝（RGB）三个通道，而是有 **20,000 个颜色通道**的图像。这是一个非常硬核的计算机视觉问题。

<details>
<summary>Original English</summary>

**Ron Alfa**: From first principles how would we do this? So you probably want tissue level biology. 1. Pathology H&E: That's what every patient gets. It's how pathologists identify different cellular structures. 2. Protein Stains (Multiplex Immunofluorescence): We want to have some layer of cell biology, knowing about immune cells and their subtypes. The immune environment of the tumor is a core constituent of whether a patient responds. 3. Spatial Transcriptomics: Spatially resolvable RNA. We get the RNA in a spatially resolved pattern for the same cells. You have between 1,000 or 19,000 different genes. It's like an image except instead of being an RGB image that has three color channels, now all of a sudden it has like 20,000 colors. It's like a very meaty computer vision problem.

</details>

### 虚拟细胞与基础模型

**主持人**: 什么是“虚拟细胞”？如何将这堆海量数据转化为有用的知识？

<details>
<summary>Original English</summary>

**Host**: What is a "virtual cell"? How do you turn that big pile of data into useful knowledge?

</details>

**Ron Alfa**: “虚拟细胞”有两种理解。一种是模拟细胞内所有的生化过程，预测数百万种化学反应，这在智力上很有趣，但目前还没有足够的数据模态来解决它。

我们更倾向于**实用主义的虚拟细胞**。我们是要制造对患者有效的药物。所以，我们设计的模型是去**模拟特定环境下的细胞生物学**。输入是环境背景，输出是该背景下的转录组或蛋白质特征。这种输入/输出关系允许我们运行模拟实验。

<details>
<summary>Original English</summary>

**Ron Alfa**: One view is we want to be able to simulate all the biochemical processes in a cell. I think that's an interesting intellectual pursuit, but I don't think we have all the modalities of data you would need. I tend to see the virtual cell problem as something more practical. We're trying to make drugs that work in patients. Really what we want to do is understand cell biology in some heuristic that's useful for making drugs. The simplistic thing that we're doing is really just the model can simulate many cells in different contexts and allow you to run some simulations in that regime.

</details>

**Dan Bear**: 目前很多人所谓的虚拟细胞模型主要集中在单细胞基因表达，预测当加入一个小分子药物或进行基因扰动时，转录组会发生什么。但我们真正想解决的问题是**预测患者身上会发生什么**。模拟来自患者的数据，比模拟实验室培养皿中的数据更有可能转化为临床结果。

<details>
<summary>Original English</summary>

**Dan Bear**: I think that modeling data that comes from a patient is much more likely to translate to what happens when you give a patient a drug than something that's happening in cell culture.

</details>

### 跨越鸿沟：让小鼠说“人类语言”

**主持人**: 你们不仅有患者模型，似乎还有一个小鼠平台？

<details>
<summary>Original English</summary>

**Host**: You not only have patient models, but also a mouse platform?

</details>

**Dan Bear**: 是的，虽然我们坚持训练基于人类数据的模型，但现实是 FDA 有时仍需要动物实验数据。传统的小鼠模型无法很好地转化。我们使用了一个叫 **Perturb-map** 的平台。我们可以对癌细胞进行高度复用的基因敲除（利用 CRISPR），每个细胞都被“打码”（Barcoded），标记了哪个基因被敲除。然后将这些带有 100 种不同基因扰动的细胞注入小鼠肺部。这样，一只小鼠体内就有数百个肿瘤，每个肿瘤都有由特定基因敲除驱动的独特生物学。我们可以用这个系统来**验证我们的模型**。

<details>
<summary>Original English</summary>

**Dan Bear**: We are running in vivo perturbations using a platform based in mouse called Perturb-map. This is a platform for generating highly multiplexed knockouts of individual genes. You end up with mice that have tumors that are barcoded that have a hundred different genetic perturbations in them. We can actually use that to validate our models and ask if what the models are predicting in humans via simulation is actually borne out in a mouse system.

</details>

**Ron Alfa**: 更酷的是，我们正在开发一种方式，利用模型直接从载玻片（H&E）中**推断人类生物学**。即使输入的是小鼠的切片，模型输出的也是**人类基因的形式**。我们在“硅片上”对小鼠进行了人类化。

我们知道，如果你在人类肺癌中敲除某个免疫途径，肿瘤会变得很“冷”（没有免疫细胞浸润）。我们在小鼠系统中看到同样的现象，而模型能够准确地预测出这种人类化的表型。对于生物学家来说，看到模型能识别出即使在不同物种中也属于同一信号通路的不同基因敲除，这简直太神奇了。

<details>
<summary>Original English</summary>

**Ron Alfa**: We're in silico humanizing the mouse. All the outputs in terms of the transcript from the mouse are in the form of the human genes. Apparently mouse H&E looks enough like human H&E that models think it's perfectly valid H&E. It makes predictions about whether this is immune hot versus cold and those predictions are accurate. It's amazing to me as a biologist that you show it some mouse histology and it's able to say these five different tumor genotypes all look like they have the same phenotype.

</details>

### 与 GSK 的 5000 万美元大单

**主持人**: 你们最近达成了一笔引人注目的大交易。这在 AI 生物公司中非常罕见，因为你们真的在赚钱。

<details>
<summary>Original English</summary>

**Host**: You did a big deal recently. I think you have the distinction of being one of the only AI for bio companies that is making money.

</details>

**Ron Alfa**: 是的，我们非常激动地宣布与 **GSK（葛兰素史克）** 达成协议，授权他们使用我们的 **OctoVC** 基础模型。这是一笔价值 **5000 万美元**的交易，包括预付款、里程碑付款，以及年度模型授权费。

GSK 拥有生物医药领域顶尖的 AI 团队。他们可以使用我们的模型进行模拟、发现新药，甚至可以基于他们自己的海量临床试验数据对模型进行微调。这笔交易的独特之处在于：交易的标的不是一个特定的药物分子，也不是某种合作研发，而是一个**模型**。这是该领域第一个宣布的基础模型授权协议。

<details>
<summary>Original English</summary>

**Ron Alfa**: We announced a deal with GSK where we licensed them OctoVC, our virtual cell foundation model. It's a $50 million deal includes an upfront payment, milestones, and an annual model licensing fee. GSK can use our models to do simulations and therapeutic discovery, but they can also fine-tune the models on their data. What's unique about this deal is the substrate is not a molecule, it's actually a model.

</details>

**主持人**: 为什么现在制药公司对此胃口大开？两年前生物科技领域似乎还一片惨淡。

<details>
<summary>Original English</summary>

**Host**: Why do you think there's appetite for this suddenly? It seems like only a year or two ago that bio was dying.

</details>

**Ron Alfa**: 我认为药企越来越多地意识到，他们不想要一次性的合作，他们想要能贯穿整个研发管线（Pipeline）的技术。像蛋白质结构预测模型的成功，让大家看到了 AI 的价值。制药公司手里攥着成堆的临床数据，但一直很难挖掘。Noetik 的优势在于我们作为初创公司，可以下注生成海量的、统一高质量的数据。

<details>
<summary>Original English</summary>

**Ron Alfa**: I think pharma increasingly want to be able to access models not just for one collaboration on one program—they want to be able to access the technology across the whole pipeline. Startups like us can make the bet that you benefit from generating all of this data in a uniformized way.

</details>

### 生物学的 ChatGPT 时刻？

**主持人**: 对于那些想要加入这个领域或者正在创业的人，你们有什么建议？

<details>
<summary>Original English</summary>

**Host**: For small biotech startups or listeners, do you have any advice?

</details>

**Dan Bear**: 如果你没有足够的数据，就不要妄想训练基础模型。这就像是在做一个小规模试验，却指望得到 GPT-3 级别的效果。这需要极强的信念。

<details>
<summary>Original English</summary>

**Dan Bear**: Imagine trying to train a foundation model on not enough data. You can't just take something off the shelf and expect that you're going to hit the threshold of GPT-3 like usefulness. It takes some conviction.

</details>

**Ron Alfa**: 我希望大家对生物学感到兴奋。目前科技圈的热情主要集中在软件和通用 AI 上，但实际上，有些实验室正在宣布“我们要攻克癌症”。这是真正能改变人类未来 10 年的问题。我们正处于生物学“**ChatGPT 时刻**”的前夕。这只是个开始，欢迎那些对硬核机器学习感兴趣、哪怕不懂生物的人加入我们。

<details>
<summary>Original English</summary>

**Ron Alfa**: Everyone should be excited about biology. We're just in the first inkling of the ChatGPT moment for bio, but it's very much just the very beginning. Would love for people to just be more stoked about learning about applications of machine learning in biological sciences because these are the problems that are going to massively impact humanity in the next 10 years.

</details>