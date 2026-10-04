---
author: Latent Space
date: '2026-07-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2AdS-2uuH80
speaker: Latent Space
tags:
  - model-prediction
  - data-generation
  - virtual-cell-modeling
  - protein-sequencing
title: 人工智能驱动的药物发现平台与虚拟细胞建模的未来
summary: 文章介绍了利用人工智能构建药物发现平台的最新进展，特别是通过整合多轮扰动实验数据来提高预测准确性。同时探讨了在单细胞基础模型训练中，如何从自回归到扩散语言模型的架构演进，以及对蛋白质测序和时间动态建模的终极愿景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Xaira Therapeutics
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

### 第一部分：基因表达预测的震撼瞬间

**Xi Chu**: 真正让我感到震撼的是，当我看到模型做出预测，不仅打印出基因表达变化的直方图，而且将实际的原始数据与线性基线预测、真实基准（ground truth）以及 X-Cell 的预测结果并排放在一起。

<details>
<summary>Original English</summary>

**Xi Chu**: And what really blew my mind away is when I saw the model make prediction, just printing out the heat map of the gene expression changes, look at actual raw data and line up the linear baseline prediction, the ground truth and the X-Cell prediction altogether.
</details>

**Xi Chu**: 我们可以非常直观地看到，X-Cell 的预测结果比起线性基线要更加接近真实的基准数据。

<details>
<summary>Original English</summary>

**Xi Chu**: It's visually very clear to see that X-Cell prediction is much more similar to ground truth than the linear baseline.
</details>

**Bo Wang**: 这正是我在一开始提到的“惊叹时刻（wow moment）”。

<details>
<summary>Original English</summary>

**Bo Wang**: This is a wow moment I was talking about in the beginning.
</details>

**Xi Chu**: 这是有史以来第一次，有人能将不仅是一个扰动测序（perturb-seq），而是七个全基因组范围的扰动实验结果结合在一起。

<details>
<summary>Original English</summary>

**Xi Chu**: This is the first time that someone can put together not just one perturb-seq, but seven genome-wide perturbs campaigns together.
</details>

**Xi Chu**: 对于我们这些生物学家来说，立刻就能注意到的一点是，其中一些扰动在不同的背景下具有普遍性。

<details>
<summary>Original English</summary>

**Xi Chu**: Something that jumped out to us biologists right away is that some of the perturbations are context universal.
</details>

### 介绍与访谈背景

**RJ**: 大家好，我是 RJ Honicky，MiraOmics 的首席技术官（CTO）。

<details>
<summary>Original English</summary>

**RJ**: Hi, I'm RJ Honicky, CTO of MiraOmics.
</details>

**RJ**: 这位是 Brandon Anderson，他在 Atomic AI 开发 RNA 疗法。

<details>
<summary>Original English</summary>

**RJ**: This is Brandon Anderson who builds RNA therapeutics at Atomic AI.
</details>

**RJ**: 这里是 Latent Space 面向科学的 AI（AI for Science）播客。

<details>
<summary>Original English</summary>

**RJ**: And this is the Latent Space AI for Science podcast.
</details>

**RJ**: 贯穿我们播客的一个主题是，实验室、实验以及现实世界如何产生最大的影响，而且它们对于某个事物究竟是“面向科学的 AI”还是类似于 B2B SaaS 而言，有着最密切的关联。

<details>
<summary>Original English</summary>

**RJ**: One of the themes that has run through the podcast is how the lab and the experimentation and the real world have probably the biggest impact and have the most relevance to whether something is AI for Science or something like B2B SaaS.
</details>

**RJ**: 今天，我们非常高兴能邀请到来自 Xaira Therapeutics 的 Bo Wang 和 Xi Chu 来到演播室。

<details>
<summary>Original English</summary>

**RJ**: We're really happy to have in the studio with us today, Bo Wang and Xi Chu from Xaira Therapeutics.
</details>

**RJ**: 在 Xaira，他们正和许多其他人一起，构建一个 AI 药物发现平台。

<details>
<summary>Original English</summary>

**RJ**: At Xaira, they're building with a bunch of other people, a AI drug discovery platform.
</details>

**RJ**: 他们正利用高通量实验系统来收集极其庞大的数据集，随后训练出可以预测你体内细胞将如何对药物和疗法做出反应的 AI 模型。

<details>
<summary>Original English</summary>

**RJ**: They're using high throughput experimentation system to collect very large data sets and then training AI models that can predict the way that your cells in your body will respond to drugs and therapeutics.
</details>

**RJ**: 很高兴你们能来，我是你们工作的超级粉丝。你们两位不如先向听众们做个自我介绍吧？

<details>
<summary>Original English</summary>

**RJ**: Really happy to have you, big fan of your work. Why don't you two introduce yourselves to the listeners?
</details>

**Bo Wang**: 大家好，我叫 Bo Wang。

<details>
<summary>Original English</summary>

**Bo Wang**: Hello everyone. My name is Bo Wang.
</details>

**Bo Wang**: 我是 Xaira Therapeutics 生物医学 AI 部门的高级副总裁（SVP）兼负责人。

<details>
<summary>Original English</summary>

**Bo Wang**: I'm SVP and Head of Biomedical AI at Xaira Therapeutics.
</details>

**Bo Wang**: 大约八个月前加入了 Xaira。

<details>
<summary>Original English</summary>

**Bo Wang**: Joined Xaira about eight months ago.
</details>

**Bo Wang**: 在此之前，我在加拿大的多伦多大学担任副教授。

<details>
<summary>Original English</summary>

**Bo Wang**: And before that, I was Associate Professor at the University of Toronto in Canada.
</details>

**Xi Chu**: 我是 Xi Chu。

<details>
<summary>Original English</summary>

**Xi Chu**: And I'm Xi Chu.
</details>

**Xi Chu**: 除非你说普通话，否则我的名字极其难发音，所以你可以叫我 Chu，就像楚巴卡（Chewbacca）或者皮卡丘（Pikachu）里的发音一样。

<details>
<summary>Original English</summary>

**Xi Chu**: My first name is incredibly difficult to pronounce unless you speak Mandarin, so I go by Chu as in Chewbacca or Pikachu.
</details>

**Xi Chu**: 那是我最喜欢的虚构角色。我是 Xaira AI 驱动发现部门的 SVP。

<details>
<summary>Original English</summary>

**Xi Chu**: Favorite fictional character. I'm the SVP of AI enabled discovery at Xaira.
</details>

**Xi Chu**: 大约两年多前，当公司还处于隐匿模式（stealth mode）时我就加入了。

<details>
<summary>Original English</summary>

**Xi Chu**: I joined about more than two years ago when I was still in stealth mode.
</details>

**Xi Chu**: 在这里，我领导着高通量生物学团队，负责生成那些将用于提供给我们的 AI 模型的数据，并思考这些模型的应用场景。

<details>
<summary>Original English</summary>

**Xi Chu**: And here I lead the high throughput biology group generating the kind of data that will feed our AI models and also think about their applications.
</details>

**Xi Chu**: 在此之前，我花了大约十年时间在 AI、大数据以及生物学的交叉领域工作。

<details>
<summary>Original English</summary>

**Xi Chu**: Before this, I spent about a decade at the intersection of AI and big data and biology.
</details>

**Xi Chu**: 我之前曾在 Insitro 工作，领导那里的体外发现平台。

<details>
<summary>Original English</summary>

**Xi Chu**: As I previously worked at Insitro, leading the in vitro discovery platform there.
</details>

**Xi Chu**: 在那之前，我任职于 Verily，那是一家从 Google X 拆分出来的公司。

<details>
<summary>Original English</summary>

**Xi Chu**: And before that, I was at Verily, which spun out of Google X.
</details>

### Xaira Therapeutics 的愿景与平台

**Brandon**: 好的。那么，你在 Xaira 公司，这是一家在“令人困惑的名字”和“巨额融资”方面处于帕累托前沿（Pareto frontier）的公司。

<details>
<summary>Original English</summary>

**Brandon**: Okay. So you, you're at Xaira, the company, which is on the Pareto frontier of confusing names and mega rounds.
</details>

**Brandon**: Xaira 大约是在几年前结束隐匿模式的，发展得非常庞大，或者可以说是横空出世。

<details>
<summary>Original English</summary>

**Brandon**: So Xaira is, I think kind of came out of stealth like a few years ago and just really big or kind of out of nothing.
</details>

**Brandon**: 所以我很好奇，你们能否稍微解释一下 Xaira 的使命是什么？你们的核心理念（thesis statement）是怎样的？Xaira 有什么特别之处，以及你们未来的发展方向是什么？

<details>
<summary>Original English</summary>

**Brandon**: So I'm curious if you can explain a little bit about what is Xaira's mission? What is their thesis statement? Like what is, you know, special about Xaira and you know, kind of where you're going in the future.
</details>

**Xi Chu**: 是的，Xaira 是一家由 AI 驱动的药物发现公司。

<details>
<summary>Original English</summary>

**Xi Chu**: Yeah, Xaira is a AI enabled drug discovery company.
</details>

**Xi Chu**: 我们使命的核心在于，我们正利用 AI 平台来创造更好的疗法，以推进患者的护理。

<details>
<summary>Original English</summary>

**Xi Chu**: And at the core of our mission, we're using AI platforms to generate better therapeutics to advance patient care.
</details>

**Xi Chu**: 所以我们将利用不同的 AI 能力来制造药物。我们目前正在这里构建三大主要的 AI 平台。

<details>
<summary>Original English</summary>

**Xi Chu**: And so we will be making drugs using different AI capabilities. There are three main AI platforms that we're building here.
</details>

**Xi Chu**: 第一个是蛋白质设计工作，它脱胎于我们的联合创始人，来自华盛顿大学的 David Baker 博士的团队。

<details>
<summary>Original English</summary>

**Xi Chu**: The first one is protein design work that spun out of our co-founder, Dr. David Baker's group from UW.
</details>

**Xi Chu**: 当前这一代许多蛋白质设计领域的专家都在我们公司。在那里的思路是，利用先进的 AI 技术，针对以前认为无法成药的靶点来开发分子。

<details>
<summary>Original English</summary>

**Xi Chu**: A lot of the current generation of protein designers are here in the company. So there the thinking is to use advanced AI technology to develop molecules against previously undrawable targets.
</details>

**Xi Chu**: 第二个 AI 平台，我想也就是我们今天会花很多时间来探讨的，是我和 Billy 一直在致力于研究，并且刚刚发布了一篇预印本论文的平台。

<details>
<summary>Original English</summary>

**Xi Chu**: The second AI platform, I guess we'll spend a lot of time talking about today is the one that Billy and I have been working on for quite some time and just released a pre-print on.
</details>

**Xi Chu**: 那就是虚拟细胞，或者说生物学基础模型工作。其希望是构建一个像你刚才提到的那样预测生物学的模型，并预测哪些基因和药物分子会影响细胞生物学。

<details>
<summary>Original English</summary>

**Xi Chu**: That's the virtual cell or foundation model of biology work. There are the hope is to build a model to predict biology exactly like you said and predict what genes and drug molecules will affect cell biology.
</details>

**Xi Chu**: 第三个部分，也是我们现在正开始构建的，是患者表征模型。

<details>
<summary>Original English</summary>

**Xi Chu**: And the third piece, which we're beginning to build now is patient representation models.
</details>

**Xi Chu**: 那个目标是拥有能够理解哪些患者会对哪些疗法产生反应的 AI 模型。

<details>
<summary>Original English</summary>

**Xi Chu**: And the goal there is to have AI models that can understand which patients will respond to which therapeutics.
</details>

**Xi Chu**: 所以我们希望，这些平台技术结合在一起，将帮助我们比以往的技术更快、成功率更高地制造出更好的药物，将过去那种工匠式的反复试错，越来越转变为一门工程学科。

<details>
<summary>Original English</summary>

**Xi Chu**: So hopefully together, these platform technology will help us make better drugs faster and with a higher success rate than previous technologies to transform what is used to be artisanal trial and error in the past into more and more into an engineering discipline.
</details>

**Bo Wang**: 我认为让 Xaira 与众不同的，不仅是 10 亿美元的融资，还在于 Xaira 是极少数真正实现端到端，覆盖药物研发所有阶段的原生 AI 药物研发公司之一，从早期的靶点识别、蛋白质设计、小分子，一直到第一、二、三期临床试验。

<details>
<summary>Original English</summary>

**Bo Wang**: I think what sets Xaira different is not just the 1 billion around, but also I think Xaira is one of the very few AI native companies for drug discovery that works from end to end of all sections of drug discovery from as early as, you know, target ID and the protein design, small molecules, and to face one, two, three clinical trials,
</details>

**Bo Wang**: 我们的目标是利用 AI 来加速药物发现的每一个环节。

<details>
<summary>Original English</summary>

**Bo Wang**: we aim to use AI to accelerate every part of the drug discovery.
</details>

**Bo Wang**: 这样一来，我们不仅能提高开发药物的成功率，还能大幅缩短研发周期。与其每十年、二十年才研发出新药，我们希望能缩短这个周期。

<details>
<summary>Original English</summary>

**Bo Wang**: So that not only we increase the success rate of developing drugs, but also greatly, you know, reduce the cycle time so that we can have new drugs instead of every 10, 20 years. So hopefully we can have the cycle time.
</details>

**Bo Wang**: 这样我们就能为患者提供更多有效的药物。

<details>
<summary>Original English</summary>

**Bo Wang**: So we have more useful drugs for patients.
</details>

### 连接各个 AI 平台与转化挑战

**RJ**: 这非常有趣。我知道目前人们对第三件事，或许可以称为从实验室到临床的转化，非常感兴趣。

<details>
<summary>Original English</summary>

**RJ**: That's really interesting. I know there's a lot of interest right now in that third thing, maybe called translation from the lab to the clinic.
</details>

**RJ**: 你们面临的瓶颈在哪里？你们有这三个模型。你们正在解决哪些瓶颈，具体是如何去做的呢？你们为什么要选择那种方式？

<details>
<summary>Original English</summary>

**RJ**: Where are the bottlenecks? You have these three models. What are the bottlenecks that you're addressing and sort of like, how are you doing that? Why are you doing it that way?
</details>

**Bo Wang**: 作为一个 AI 原生公司。几乎在药物发现的每一个环节，我们都在努力利用 AI 来颠覆我们开发药物的方式。

<details>
<summary>Original English</summary>

**Bo Wang**: There is a AI native company. Almost every parts of the sections of drug discovery, trying to use AI to revolutionize how we develop drugs.
</details>

**Bo Wang**: 因此在早期阶段，我们构建因果基础模型，或者有时我们称之为虚拟细胞蛋白质。我们拥有最先进的蛋白质工程模型，我们也拥有患者表征学习模型。

<details>
<summary>Original English</summary>

**Bo Wang**: So the early part, we build causal foundation models, or sometimes we call it virtual cell proteins. We have, you know, state of arts, protein engineering models, and we have also patient representation learning models.
</details>

**Bo Wang**: 我认为 Xaira 正在努力做的是，我们不仅开发 AI 模型，我们还创建正确的数据集来赋能这些模型。

<details>
<summary>Original English</summary>

**Bo Wang**: And I think what Xaira is trying to do is not only we develop AI models, but also we create the right data sets to empower these models.
</details>

**Bo Wang**: 真正让我对在 Xaira 工作感到兴奋的是，我们始终致力于将三个 AI 模型连接在一起，而不是让它们各自孤立地工作。

<details>
<summary>Original English</summary>

**Bo Wang**: And I think what's really make me excited to work at Xaira is we always aim to connect three AI models together instead of letting them work individually by their own.
</details>

**Bo Wang**: 当我们设计虚拟细胞模型时，我们会寻找其中的关联：我们能否找到那些更容易应用蛋白质工程模型的靶点？

<details>
<summary>Original English</summary>

**Bo Wang**: So when we design virtual cell models, we look for connections to that, can we find targets that is easier to apply the protein engineering models?
</details>

**Bo Wang**: 甚至当我们设计细胞因果模型时，我们能否将其与患者表征联系起来？什么是连接到细胞模型的合适患者数据，从而让我们能展示出临床实用性？

<details>
<summary>Original English</summary>

**Bo Wang**: And then even when we design the cellular causal models, can we connect to patient representations? What are the right patient data to connect to the cellular models so that we have something to show clinical utilities?
</details>

**Bo Wang**: 所以，真正让我感到兴奋的是，在加入 Xaira 之前，我是计算生物学系或计算机科学系的教授，我们主要是在计算机上工作。

<details>
<summary>Original English</summary>

**Bo Wang**: So I think what really makes me excited is before I joined Xaira, I'm kind of a professor in computational biology department or computer science department, where we mostly working on computers.
</details>

**Bo Wang**: 我们看数据，看微阵列等等。但是一旦来到 Xaira，真正让我兴奋的是，我能和像 Chu 这样的人，还有许多药物猎人，极其经验丰富的药物猎人交流，去真正了解他们的痛点。

<details>
<summary>Original English</summary>

**Bo Wang**: We look at the data, we look at arrays, et cetera. But once coming to Xaira, what really excites me is that I get to talk to people like Chu, lots of drug hunters, you know, extremely experienced drug hunters to really understand their pinpoint.
</details>

**Bo Wang**: 这样我们在设计 AI 模型时，就会思考那些真正能让生物学家兴奋的问题。

<details>
<summary>Original English</summary>

**Bo Wang**: So when we design AI models, we think about questions that really excites biologists.
</details>

**Bo Wang**: 也许稍后我们可以谈谈，在我们开发出 X-Cell 之后，我收到的一个正向反馈是来自生物学家的“惊叹时刻”，这是生物学家第一次真正发现模型能够精准预测这些未曾见过的细胞系对不同扰动会作何反应。

<details>
<summary>Original English</summary>

**Bo Wang**: So later maybe we can talk about how one of the rewarding signals I receive after we develop X-Cell is that like the wow moments from biologists that this is the first time biologists actually find the model can predict exactly how these unseen cell lines kind of respond to different perturbations.
</details>

**Bo Wang**: 所以那正是我真正感到兴奋的部分，也就是将干实验室（dry lab）或 AI 模型与湿实验室（wet lab）、或者生物学，甚至最终将其与临床应用整合在一起。

<details>
<summary>Original English</summary>

**Bo Wang**: So that's kind of the part really excites me is the integration of kind of dry lab or AI models to wet lab or the biology or even eventually to the clinical side.
</details>

**RJ**: 谈到这个临床模型，我知道你们的目标是将一种药物一路推进直到获得 FDA 批准及以后。我们目前进展到哪一步了？

<details>
<summary>Original English</summary>

**RJ**: With this clinical model, I know you guys are aiming to take a drug all the way to FDA approval and beyond. Where do we stand now?
</details>

**RJ**: 我不知道你们是否方便谈论这个，但是，你们现在能够收集临床试验数据并将其联系起来了吗？

<details>
<summary>Original English</summary>

**RJ**: I don't know if you're able to talk about this, but like, are you able to collect data from clinical trials and tie that back yet?
</details>

**Xi Chu**: 正如 Bo 所说，如果你思考药物发现的过程，这听起来很简单，对吧？你只需要找到正确的靶点，制造出正确的分子，然后找到正确的患者用药。

<details>
<summary>Original English</summary>

**Xi Chu**: As Bo said, I think if you think about drug discovery process, it's easy, right? You just need to find the right target, make the right molecule, and find the right patients to give them to.
</details>

**Xi Chu**: 当然，其中的每一个步骤要想做对都极其困难。而到目前为止，就像我刚才说的，它严重依赖大量的反复试错和猜测。

<details>
<summary>Original English</summary>

**Xi Chu**: Of course, each of those steps are incredibly difficult to get right. And so far, like I said, just now, it realized a lot of untraddling and erring guesswork.
</details>

### 数据瓶颈与生成因果数据

**Xi Chu**: 我认为主要的问题是，我们没有合适的生物数据，真正能够用来训练预测模型。

<details>
<summary>Original English</summary>

**Xi Chu**: And the main issue, I think, is that we don't have the right biological data, really the power, the training of a predictive model.
</details>

**Xi Chu**: 在蛋白质设计领域，我认为那是我们迄今为止看到进展最快的地方。部分原因是我们拥有大量高质量的数据，这些数据是由整个社区历经70多年整理而成的。

<details>
<summary>Original English</summary>

**Xi Chu**: And in protein design space, I think that's where we have seen the most rapid progress so far. That's partially because we have a lot of data, high quality data, over 70 years curated by the entire community,
</details>

**Xi Chu**: 人们将蛋白质结构存入一个名为 PDB 的数据库中，对吧。

<details>
<summary>Original English</summary>

**Xi Chu**: people deposit protein structures into a database, right, called PDB.
</details>

**Xi Chu**: 我们也有大量的序列数据，这些是多年来从不同基因组中收集的，它们同样可以帮助指导模型。

<details>
<summary>Original English</summary>

**Xi Chu**: We also have a lot of sequence data, right, collected over the years from different genomes that can help inform the model as well.
</details>

**Xi Chu**: 正是这些收集和积累下来的高质量数据，迎来了蛋白质设计、AlphaFold 以及其他折叠模型的革命。

<details>
<summary>Original English</summary>

**Xi Chu**: And it's these high quality data that are collected and accumulated that usher in this revolution in a protein design and alpha fold and other folding models.
</details>

**Xi Chu**: 在其他领域，比如临床模型预测，比如虚拟细胞，我们距离拥有同等规模的高质量海量数据还差得很远。

<details>
<summary>Original English</summary>

**Xi Chu**: In the other domains, such as clinical model prediction, such as virtual cell, we are nowhere near the same kind of massive data that are high quality.
</details>

**Xi Chu**: 所以我认为这主要是一个数据限制问题。

<details>
<summary>Original English</summary>

**Xi Chu**: And I think it's mainly a data limitation issue.
</details>

**Xi Chu**: 回答你的问题，这正是为什么我们在生成这些数据方面投入巨大的原因，特别是在实验室中生成细胞生物学的因果数据。

<details>
<summary>Original English</summary>

**Xi Chu**: So to your question, that's why we're very invested in generating these data, particularly causal data in cell biology in a lab.
</details>

**Xi Chu**: 我认为，这使得在算法端进行创新成为了可能，并迎来了虚拟细胞模型。

<details>
<summary>Original English</summary>

**Xi Chu**: And that's, I think, what made it possible to innovate on the algorithm side as well to usher in virtual cell models.
</details>

**Xi Chu**: 在患者方面，这是一个非常有趣的问题。这或许是最难获取的数据之一，因为仅仅是获取高质量的患者样本本身就很困难。

<details>
<summary>Original English</summary>

**Xi Chu**: On the patient side, it's a very interesting question. Perhaps that's one of the hardest data to get because getting access to high quality patient samples is difficult in itself.
</details>

**Xi Chu**: 将其与正确的临床注释相匹配，以便你实际上能够学习到其中的差异，也就是分子数据与临床反应之间的桥梁，这甚至更难。

<details>
<summary>Original English</summary>

**Xi Chu**: Getting it matched to the right clinical annotation so that you can actually learn the difference, the bridge between molecular data and clinical response, that's even harder.
</details>

**Xi Chu**: 你也许能够在不同的疾病严重程度之间做到这一点，但要收集正确的数据，用来预测某种药物治疗在特定患者身上是否会产生反应，将会更加困难。

<details>
<summary>Original English</summary>

**Xi Chu**: And you might be able to do that across different disease severities, but it will be harder to collect the right data to predict which drug treatment will or would not respond in a particular patient or not.
</details>

**Xi Chu**: 因此，这需要大量的思考和极其谨慎的整理，才能从中产生有用的数据。

<details>
<summary>Original English</summary>

**Xi Chu**: And so that takes a lot of thought and a lot of careful curation to generate data out of.
</details>

**Xi Chu**: 所以我们正开始进入这个领域，希望不久之后能分享更多进展。

<details>
<summary>Original English</summary>

**Xi Chu**: And so we're beginning to go into the area, but hopefully we'll be able to share more soon.
</details>

### X-Cell 介绍

**RJ**: 太棒了。也许我们现在该换个话题了。你们刚刚发布了 X-Cell。不如你们来描述一下，我来说可能说不好。

<details>
<summary>Original English</summary>

**RJ**: Awesome. Maybe we should switch gears now. You just released Xcel. Why don't you guys describe, I'll butcher it.
</details>

**Bo Wang**: X-Cell 是 Xaira 的第一个虚拟细胞模型。它是一个能够预测——

<details>
<summary>Original English</summary>

**Bo Wang**: Xcel is Xaira's first virtual cell models. It is an AI model that can predict
</details>

<!-- chunk 2/9 -->

### 什么是基因扰动与计算模拟？

**Bo Wang**: ……以及细胞对基因扰动的反应。当然，我们可以将其扩展到其他类型的干预措施，比如药物扰动、化学扰动等等。

<details>
<summary>Original English</summary>

**Bo Wang**: the response to genetic perturbations. Certainly we can extend it to other type of interventions such as drug perturbations, chemical perturbations, et cetera.

</details>

**RJ**: 那么，您能为正在收听的非生物学背景的听众解释一下，什么是扰动？您的具体意思是什么？

<details>
<summary>Original English</summary>

**RJ**: So can you just describe for the non biologists that are listening, what is a perturbation? What do you mean by that?

</details>

**Xi Chu**: 就我们人体而言，当 Bo 谈到基因扰动时，我们的人体细胞通常拥有 20,000 个基因。并不是所有细胞都会同等程度地表达每一个基因。这就是为什么你的眼部细胞、皮肤细胞、心脏细胞，尽管它们共享着相同的基因组，但它们的功能却大相径庭。这在很大程度上是由选择性的基因表达决定的，它决定了细胞的类型和状态。所以我们所做的，就是建立一个模型，让你可以在计算机里（in silico）从细胞中消除某些基因。这就是一种计算机模拟的扰动。也就是说，如果我降低某个基因在细胞中的表达，那对细胞的其他部分意味着什么？会产生怎样的生物学后果？

<details>
<summary>Original English</summary>

**Xi Chu**: In ourselves, when Bo talked about genetic perturbations, our human cell typically have 20,000 genes. Not all cells express every gene equally. That's why your eye cell, your skin cell, your heart cell, even though they share the same genome, they function very differently. A lot of that is determined by selective gene expression that determine the type and the state of the cell. So what we do is to build a model that you can in silico ablate certain genes from the cell. That is a in silico perturbation. That's to say, if I reduce the expression of this gene in a cell, what is the implication for the rest of the cells? What's the biological consequence?

</details>

**RJ**: 您基本上就是把某个基因的“旋钮”调低了。这就对了。然后细胞里所有其他的基因会发生什么变化？

<details>
<summary>Original English</summary>

**RJ**: You basically turned the knob down on one gene. That's right. And then what happens to all the other genes in that cell?

</details>

**Xi Chu**: 正确。我们的希望当然是预测对所有其他基因的影响，但也许还能预测基因表达之外的更多事情，比如细胞的功能。这一点很重要，因为它在治疗上具有现实意义，因为很多药物都是抑制剂，而它们正是通过这种方式发挥作用的，即降低某种蛋白质或基因的活性。因此，我们可以从基因扰动预测开始。我们的希望是，我们也可以进一步进行通路抑制预测，诸如此类。

<details>
<summary>Original English</summary>

**Xi Chu**: Correct. And the hope is of course to predict the effect on all the other genes, but maybe even more things than gene expression, such as the function of the cell. And that's important that that's therapeutically relevant because a lot of drugs are inhibitors and they function through exactly that, turning down the activity of a protein or gene. And so we can start with gene perturbation prediction. The hope is that we can also go to pathway inhibition prediction, so on and so forth.

</details>

**RJ**: 所以，一个通路就是一个基因集合，它们之间彼此交流的方式是：这个基因表达一种蛋白质，而那种蛋白质又对另一个基因产生影响。依此类推。这就形成了一条由基因和蛋白质组成的漫长连锁反应。这就被称为一个通路。因此，如果你打断了它，或者以某种方式改变了它，那么这就会对细胞的更宏观表型产生影响，比如细胞看起来像什么、它能做什么等等。完全正确。

<details>
<summary>Original English</summary>

**RJ**: So a pathway is just a set of genes that all kind of talk to each other by this gene expresses a protein. That protein has some impact on another gene. And so forth and so on. There's this long chain reaction of genes and proteins. And then so that that's called a pathway. And so if you interrupt that or somehow change it, then that has an impact on the larger phenotype of the cell, what the cell looks like, does, et cetera. That's exactly right.

</details>

### 虚拟细胞的概念与发展

**Brandon**: 是的。所以，你们拥有你们所说的“虚拟细胞”，或者说你们正在创建一个虚拟细胞。而虚拟细胞是一个非常热门的概念。很多人对这个概念都很感兴趣，但我认为你们的方法在某种程度上是独一无二的，或者区别于其他人正在做的事情。您能解释一下人们在说“虚拟细胞”时，大致上指的是什么吗？还有哪些其他截然不同的策略？那么，你们正在追求的具体策略又是什么呢？

<details>
<summary>Original English</summary>

**Brandon**: Yeah. So you have what you call the virtual cell or you're creating a virtual cell and virtual cells are very popular. It's a lot of people are interested in this concept, but I think your approach is somewhat unique or separate from other people are doing. Can you explain what do broadly people mean when they say virtual cells? What are some of the distinct other strategies? And then like, what is your specific strategy that you're going for?

</details>

**Bo Wang**: 当然，“虚拟细胞”是一个非常宏观的术语，用来描述一种能够预测或描述细胞外观，或者在某些干预后预测细胞功能的 AI 模型。这是一个非常高阶的概念。首先，这并不是一个新颖的想法。我们大约在 20 年前就有了虚拟细胞项目。但在那个时候，我们有时称之为“虚拟细胞 1.0”，人们试图推导微分方程，试图利用数学来描述正如你刚才提到的某种通路干预的反应，并通过将这些方程拟合到不同的观测结果中来实现。大体而言，那是一次失败的尝试，因为生物学实在是太复杂了，无法用少数几个预定义的微分方程组来编写。向前推进，随着语言模型的崛起，我认为通过数据驱动的方法，利用 AI 模型来模拟细胞对不同干预的反应，这种想法开始流行起来。我想大约在三年前，几乎就在 ChatGPT 发布仅仅四个月之后，我们在多伦多大学的实验室发表了单细胞基因组学领域早期的基础模型之一，我们称之为 SCGPT。你多少可以把它理解为一个面向单细胞的类似 GPT 的模型。它很快变得非常受欢迎，因为这是第一次，我们拥有了一个基础模型，能够使用同一个模型处理不同的下游任务，例如，我们可以使用同一个模型来整合不同批次的单细胞 RNA 测序数据。我们可以使用同一个模型来预测多组学整合。

<details>
<summary>Original English</summary>

**Bo Wang**: Certainly, virtual cell is a very high level term to describe an AI model that is able to predict or describe what cell looks like or predict the cell functions after certain interventions. It's a very high level concept. It was first of all, it was not a novel idea. We had virtual cell project almost 20 years ago. But back then, sometimes we call it virtual cell 1.0 is that people are trying to derive differential equations to trying to use mathematics to describe what's the response for certain pathway intervention, as you just mentioned, and by feeding these equations to different observations. And largely speaking, that was a failed attempt in the sense that the biology is just way too complicated to write in a few predefined set of differential equations. Moving forward, with the rise of language models, I think the idea of using AI models to mimic how cell responds to different interventions by data-dreaming approach start to get popular. And I think three years ago, almost just four months after Chagibee was released, our lab at University of Toronto published one of the early foundation model of single cell genomics, call it SCGPT. It can kind of interpret it as a GPT-like model for single cells. And it quickly become very popular in the sense that for the first time, we have a foundation model that is able to tackle different downstream tasks using the same model, such as we can use the same model to integrate different batches of single cell RNA-seq. We can use the same model to predict multi-omic integrations.

</details>

**RJ**: 让我们来定义一下这些概念。比如“批次”，整合不同批次的 RNA 测序。所以，你有不同的设备，你们都在收集数据。或者你们可能在相同的实验室收集。是的，不同的实验室，一天中的不同时间，不同的月相，随便什么都行。而这些实际上对你收集的数据有很大的影响。所以这就产生了一个大问题：我该如何将这个数据集与那个数据集进行比较，当存在所有这些与基因表达毫无关系、仅仅与我如何测量它有关的其他差异时？

<details>
<summary>Original English</summary>

**RJ**: Let's define those things. So batches, integrate different batches of RNA-seq. So you have different equipment, you're all collecting. So maybe you're collecting the same labs. Yeah, different labs, different time of day, different phase of the moon, whatever. And those actually have a big impact on the data that you collect. And so there's a big problem of how do I even compare this dataset to that dataset when there's all this other differences that have nothing to do with the gene expression and just how I measured it.

</details>

**Bo Wang**: 我们称之为“批次效应”。我们当然想要消除批次效应，同时保留细胞类型，这是我们希望保留的重要生物学特征。

<details>
<summary>Original English</summary>

**Bo Wang**: We call that batch effect. We certainly want to remove the batch effect while preserving the cell types, which are important biology we want to reserve.

</details>

**Brandon**: 所以这有点类似于图像分类器中的“坦克问题”，例如，模型捕捉到了这些疯狂的、虚假的特征，而这些特征与你真正关心的底层生物学毫无关系。

<details>
<summary>Original English</summary>

**Brandon**: So this is sort of analogous to the tank problem in image classifiers, for example, as the models pick up on these crazy, spurious features, which have nothing to do with what you actually care about, the underlying biology.

</details>

**Bo Wang**: 完全正确。当然，整合不同批次的核心理念在于保留生物学信号，同时消除批次效应。在这些基础模型出现之前，单细胞领域的情况是，对于每一个任务，生物学家都必须选择所谓的专家级最先进（state-of-the-art）的方法。而借助基础模型，比如 SCGPT 或 Geneformer，我们希望带来的是一个能够解决单细胞中所有任务的模型。随着基础模型的普及，许多研究人员在 CZI（陈·扎克伯格倡议）大脑研究所的号召下聚集在一起，我们在《细胞》（Cell）期刊上发表了一篇前瞻性论文，首次创造了“虚拟细胞”这个术语，几乎可以说是“虚拟细胞 2.0”。它的含义是：如果我们无法用数学来描述它，那就让我们利用数据驱动的方法，让模型去学习它。这就是虚拟细胞的理念，以便我们能够构建语言模型或类似语言的模型，来预测细胞类型是什么样的，以及细胞如何对不同的干预做出反应。最终，我们可以通过在计算机上运行模拟来取代所有的细胞实验，甚至无需进行实际的实验操作。

<details>
<summary>Original English</summary>

**Bo Wang**: Exactly. Certainly the core idea of integrating different batches is to keep the biological signals while removing the batch effect. And before these foundation models, what happens in single cell domain is that for every task, biologists have to choose the so-called specialist state of arts approaches. And with foundation models such as SGV or Geneformer, what we hope to bring is that one model that solve all the tasks in single cells. And with the popularity of foundation model, lots of researchers come together under CZI, Chanzaku Brain Institute, and we published a perspective paper as journal cell to coin, for the first time, coin the term virtual cell, almost virtual cell 2.0, in the sense that let's use data-driven approaches if we cannot describe, let's learn it. So that's the idea of virtual cell so that Genesee can build language model or language type of model to predict what the cell types looks like, how the cell respond to different interventions. And eventually we can replace all the cellular experiments by simply running simulations on computer without even running the actual experiments.

</details>

**Brandon**: 也许为了提供更多的背景信息，你可以这样理解：所以，虚拟细胞只是一个通用概念。但你要想到，细胞中包含两万个基因。而在大多数人体细胞中，我想大约有 4000 到 5000 个基因通常在任何给定的时间处于活跃状态，或者以合理的水平表达。所以你观察一个正常的细胞，里面可能有 4000 到 5000 个基因在运作。因此，你的问题是，在很多情况下，医学的作用方式是你去靶向一种蛋白质，或者你靶向某种能让蛋白质变得更常见或更少见的东西，或者它们能阻止蛋白质发挥某种作用。而你的目标是：考虑到细胞中存在一定数量的基因，每个细胞具有不同的基因组成，那么将会发生什么变化？某个通路会消亡吗？某个通路会生长吗？借此，你就能预测药物将如何发挥作用，仅仅通过理解改变一个特定的基因或某组基因，可能怎样改变一切。这样的理解正确吗？

<details>
<summary>Original English</summary>

**Brandon**: Maybe for a bit more context, you can think about this as, so a virtual cell is just a general concept, but you think cells have 20,000 genes in them. And in most human cells, I think what roughly four to 5,000 are usually active at any given time or expressed at reasonable levels. So you look at a normal cell, you might have four to 5,000 genes doing things. And so your question is, in many cases, the way medicine works is you target a protein, or you target some sort of something which makes proteins more common or less common, or they stop the protein from doing something. And your goal is, given some number of genes which are in a cell, every cell has a different composition of genes, what is going to change? Will some pathway die off? Will some pathway grow? And from this, you could predict how medicine is going to work by just understanding how changing one specific gene or some cluster of genes could change everything.

</details>

**Bo Wang**: 是的，对于虚拟细胞来说，这是一个正确的高层次理解。这个领域正在发生的事情是，我们缺乏一个对虚拟细胞的明确定义，人们几乎把基础模型和虚拟细胞画上了等号。但在我看来，虚拟细胞可能是一个比基础模型宽泛得多的概念。基础模型主要提供了一种可靠的、具有语义意义的细胞表征。但我认为，虚拟细胞在本质上更具动态性：我们能否构建 AI 模型，甚至能够预测细胞状态跨越不同时间的发展？或者我们甚至能否在不同的细胞分辨率下，描述细胞的空间变化？在我的理解中，我们在开发这种综合性的虚拟细胞模型方面，实际上还处于非常早期的阶段，而基础模型真的仅仅只是一个起点。

<details>
<summary>Original English</summary>

**Bo Wang**: Is that a correct understanding? Yeah, that's a correct high-level understanding about virtual cell. What's happening for this field is that we are lacking a concrete definition of virtual cells, and people almost equate foundation model with virtual cell. But in my view, virtual cell is probably a much broader concept than just foundation models. Foundation models mostly provide a reliable, semantic, meaningful representation of cells. But I think virtual cell is more dynamic in the sense that, can we build AI models, even predict the development of the cell states across different times? Or can we even describe the spatial changes at the cells, different cellular resolutions? In my understanding, we are really at the early stage to develop such comprehensive virtual cell models, and the foundation model is really just a starting point.

</details>

### 从描述性数据到因果预测

**RJ**: AI 模型总是始于数据。你们正在构建一种高通量的实验，或者说已经构建好并正在继续开发一个高通量的实验系统。那听起来非常酷，也非常复杂。您能告诉我们那涉及到些什么吗？比如，你们具体在做什么？你们正在进行哪些实验？这如何为建立 AI 模型提供信息？以及，为什么要做这个，而不是直接拿来 CellxGene 数据库，那是一个聚合了公共数据集中的基因表达数据的集合？

<details>
<summary>Original English</summary>

**RJ**: AI models always begin with the data. You are building a high-throughput experiment or have built and are continuing to develop a high-throughput experimentation system. That sounds really cool and really complicated. Can you tell us what that entails? Like, what are you doing? What are the experiments that you're running? How does that inform the building of an AI model? And why do this rather than pick up the Cell X-Gene database, which is a collection of gene expression data that has been aggregated over the public data sets?

</details>

**Xi Chu**: 这是一个极好的问题。我想顺着 Bo 刚才停下的地方继续说。我认为 Bo 说了一些非常深刻的观点：从一个表征模型、生物学的基础模型，走向一个虚拟细胞。这两者之间的关键区别，在于扰动预测或是生物学中的动态过程。那是一个关于因果关系的概念。为了达到这个目的，我认为我们需要因果数据。如果你看看 CellxGene，那是一个奇妙的数据集，起初它整理了超过 3300 万个细胞的数据，现在则远远超过这个数字了。在当时，当 SCGPT 这个多伦多大学 Bo 实验室出来的模型在那个数据集上进行训练的时候，那主要是一个观测性质的分析数据集。它是描述性的数据，而不是因果数据，主要分析的是健康人类捐赠者的特征。所以在这个数据集上训练出来的模型非常、非常擅长处理描述性任务，比如在批次效应间进行数据协调，消除来自不同实验室、不同技术的偏差影响。但我认为，Bo、我们，以及该领域中的其他许多人都发现，这些在描述性数据上训练出来的模型，在因果任务、扰动任务，或者我们所说的反事实任务（counterfactual tasks）上，表现还无法超越线性模型。即“如果我对细胞采取了这种操作，那么将会发生什么？”这在生物学家看来是符合直觉的，因为描述性数据集中的相关性数据，可以被拟合成许许多多种可能的因果结构。在一个非常简单的例子里，假设你在描述性数据集中观察到基因 A、B、C 都是同升同降的。你可以推断出 A 调节了 B 和 C，这就是为什么当 A 升高时，B 和 C 也随之升高。你也完全可以说 B 调节了 A 和 C，那在逻辑上也会说得通——

<details>
<summary>Original English</summary>

**Xi Chu**: Yeah, great question. I want to pick up where Bo left off. I think Bo said something pretty profound, going from a representation model, the foundation model of biology, to a virtual cell. And the key difference there is perturbation prediction or dynamic processes in biology. That's a causal concept. For that, I think we need causal data. And if you look at Cell X-Gene, that's a fantastic dataset that curated, in the beginning, more than 33 million cells, now a lot more than that. And at the time when SGP-T was trained on that dataset coming out of Bo's lab in Toronto, that was mostly an observational profiling dataset. It's a descriptive data, not causal, and mostly profiling healthy human donors. And so the model that was trained on this dataset is very, very good at doing descriptive tasks, such as harmonizing across batch effects, removing effects from different labs, different technologies. But I think Bo, us, and many others in the field have found that these models that are trained on descriptive data do not yet outperform linear models on causal tasks, perturbational tasks, or what we call counterfactual tasks. If I did this to the cell, then what would happen? That makes intuitive sense to a biologist because the correlation data in the descriptive dataset can be fit with many, many possible causal structures. In a very simplistic case, let's say you observe gene A, B, C, all go up and down together in your descriptive dataset. You can infer that A regularly B and C, that's why when A goes up, B and C also go up. You might also say that B regulates A and C, and that would be perfectly

</details>

<!-- chunk 3/9 -->

### 构建用于因果模型的二维数据集

**Xi Chu**: 这也说得通。你也可以说 A 调节 B，而 C 完全由不同的东西调节。你看到其中的问题了吧。有很多种方法可以将因果调节网络拟合到描述性数据中。从根本上说，我们认为原始数据不足以真正学习因果关系。这就是为什么我们很早就意识到，我们需要真正开始构建因果数据集，以训练因果模型。有什么方法可以做到这一点？我认为该领域已经成熟，可以大规模采用我们称之为高通量生物学的技术。有许多方法可以大规模生成这些因果数据。我们关注的技术被称为 perturb-seq（扰动测序）。对于不熟悉这项技术的听众来说，它结合了高通量混合 CRISPR 扰动（pooled CRISPR perturbation）和单细胞 RNA 测序技术来构建二维数据集。让我来分解一下。我们刚才谈到在一个细胞中，至少有 20,000 种分析物要测量。这些就是基因。这些既是要测量的特征，也是用来扰动细胞的杠杆（lever）。为了清楚起见，我们称它们为扰动和基因表达。扰动在一个轴上，而你测量到的描述细胞的特征在另一个轴上。

<details>
<summary>Original English</summary>

**Xi Chu**: reasonable as well.
You could also say that A regulates B and C is completely regulated by something different.
You see the problem there.
There's N number of ways to fit a causal regulatory network into descriptive data.
Fundamentally, we believe that the original data are underpowered to learn causality truly.
This is why we realized pretty early on that we need to really start building causal dataset to train a causal model.
What are the ways to do that?
I think the field has come of age to do these at scale technique that we call high-throughput biology.
There are many ways to generate these causal data at scale.
The technique that we have focused on is something called perturb-seq.
For the listeners who are not familiar with that technology, it combines high-throughput pulled crystal perturbation together with single-cell RNA-seq technology to build 2D datasets.
Let me break that down.
We just talked about in a cell, there are at least 20,000 analytes to measure.
These are the genes. These are both the features to measure.
These are also the liver to perturb the cells with.
For clarity, let's call them perturbations and gene expressions.
Perturbation on one axis and the features that you measure that describe the cell on the other axis.
</details>

**Xi Chu**: Perturb-seq 是一项利用生命科学最新突破 CRISPR-Cas9 的技术。这些是源自细菌的酶，允许你破坏哺乳动物细胞（例如人类细胞）中的基因表达。我们可以一次一个地进行。我可以一次敲除一个基因。当然，如果我想在一个实验中把所有 20,000 个基因表达都测出来，这在规模上将是极其困难的。可能需要一个巨大的工厂和大量的机器人来完成。或者你可以以混合（pooled）的方式进行。我喜欢混合实验。它们是超可扩展的。我们有一些实验室技巧，允许我们破坏每个细胞的一个基因，但在一个单一的混合实验中跨越许许多多的细胞去完成所有 20,000 个基因的操作。它们被完美地打乱，所以没有批次效应，也没有板间（plate-to-plate）差异。这是在扰动通量方面。

<details>
<summary>Original English</summary>

**Xi Chu**: Perturb-seq is a technique that leverages the latest breakthrough in live biology, CRISPR-Cas9.
These are bacterially derived enzymes that allow you to disrupt gene expression in mammalian cells, in human cells, for example.
We can do so in one at a time fashion. I can take out one gene at a time.
Of course, that would be incredibly difficult to scale if I want to do all 20,000 gene expression back out in one single experiment.
Probably need a huge factory, a lot of robots to do that.
Or you can do them in a pooled fashion. I love pooled experiments.
These are hyperscalable.
We have lab tricks that allow us to disrupt one gene per cell, but do all 20,000 genes across many, many cells in one single pooled experiment.
Perfectly scrambled so there's no batch effects, there's no play-to-play differences.
That's off the perturbation throughput.
</details>

**RJ**: 基本上，使用某种组合（combinatorial）技巧，首先以不同的组合扰动所有不同的基因，然后你可以读取它们并进行一些数学计算。你基本上是在一个实验中完成了整个一大批不同的实验。

<details>
<summary>Original English</summary>

**RJ**: Basically, use some sort of commutatorial trick to first perturb all the different genes in different combinations, and then you can read them out and do some math on it.
And you basically pull out a whole bunch of different experiments in one experiment.
</details>

**Xi Chu**: 正确。这需要条形码技术。而该条形码实际上是通过直接读出哪个细胞中存在哪种 CRISPR 引导 RNA（guide RNA）来实现的。因此，要让 CRISPR-Cas9 这种源自细菌的机器在哺乳动物细胞中发挥作用，你只需向每个细胞递送两样东西。你必须递送蛋白质，即执行任务的 Cas9 蛋白。你还必须递送一个由一段称为引导 RNA 的短 RNA 编码的地址条形码。引导 RNA 纯粹通过沃森-克里克（Watson-Crick）碱基配对（ATCG），告诉蛋白质在细胞中该去哪里。

<details>
<summary>Original English</summary>

**Xi Chu**: Correct. It requires barcoding technology.
And that barcode is actually achieved by directly reading out what kind of CRISPR guide RNA is present in which cell.
So for CRISPR-Cas9, this bacterially derived machinery to work in mammalian cells, you just have to deliver two things to each cell.
You have to deliver the protein, the Cas9 protein, that does the job.
And you have to deliver an address barcode encoded by a short piece of RNA called a guide RNA.
The guide RNA tells the protein where to go in the cell, purely via Watson-Quake base pairing, ATCG.
</details>

**RJ**: 所以它与基因的一部分相匹配。它足够长，可以确保它将匹配正确的基因，然后引导它连接到正确的位置，并降低该特定基因在细胞中的表达。

<details>
<summary>Original English</summary>

**RJ**: So it matches a part of the gene.
It's sufficiently long to say this will match the correct gene, and then that guides it to connect to the right and reduce the expression of that particular gene in the cell.
</details>

**Xi Chu**: 正确。我们设计这个引导 RNA 去基因的启动子部分。那是每个基因在转录开始前的起始片段。如果我们把 Cas9 蛋白带到那里，装备上正确的效应器——沉默子，那个启动子就会被关闭，该基因就再也不会被转录了。所以实际上，我们调低了该基因的表达水平。因此，你需要知道的只是弄清楚哪个引导 RNA 在哪个细胞中，这可以使用基因组读段来完成。那就是条形码。然后你就可以推断出哪个基因在哪个细胞中被沉默了。所以这就是你在扰动端扩大通量的方法。

<details>
<summary>Original English</summary>

**Xi Chu**: Correct. We designed this guide to go to the promoter part of the gene.
That's the beginning stretch of every gene before the transcription starts.
And if we bring the Cas9 protein to there, armed with the right effector, the silencer, that promoter will get shut off, and that gene will never be transcribed out of again.
So effectively, we tune down the expression level of that gene.
And so all you have to know is figure out which guide RNA is in which cell, and that can be done using genomic readouts.
That's the barcode.
And you can then infer which gene is being silenced in which cell.
So that's the way you scale throughput on the perturbation side.
</details>

### 利用单细胞技术捕捉基因调控

**Xi Chu**: 在读出端，这是一个二维数据集，对吧？我们刚才讨论了其中一个维度。在读出端，我们利用单细胞 RNA 测序（scRNA-seq）技术。这也是过去十年中实现规模化的最新技术，它可以让你同时从每个细胞中读出所有 20,000 个基因的表达水平。因此，凭借高通量 CRISPR 扰动和高通量单细胞 RNA 测序技术，突然之间，我们可以生成这些二维数据集。在这些数据集中，我们系统地在细胞类型中扰动、敲除或敲低人类基因组中的每一个基因，并读出其对相同细胞中所有其他基因的影响。所以我们生成了这些丰富的二维数据集，这与训练 AlphaFold 模型的 PDB 数据类型没有太大不同，对吧？如果你想一想，那是数十万个蛋白质条目。如果那些是行，列就是每一个氨基酸的 XYZ 坐标。那也是一个二维数据集。我认为正是这些丰富的二维数据集，推动了生物学基础模型的训练。

<details>
<summary>Original English</summary>

**Xi Chu**: On the readout side, it's a 2D dataset, right?
So we just talked about one of the dimensions.
On the readout side, we leverage single-cell RNA-seq technologies.
So these are also recent technologies in the last decade that have been scaled that can let you read out the expression level of all 20,000 genes simultaneously from each cell.
So armed with both high-throughput CRISPR perturbation and high-throughput single-cell RNA-seq technologies, all of a sudden, we can generate these 2D datasets where we systematically perturb or knock out, knock down every single gene in the human genome in the cell type, and we read out this impact on every other genes in the same cells.
So we generate these 2D-rich datasets, not that different than the type of PDB data that trained alphaphone models, right?
If you think about that, that's hundreds of thousands of protein entries.
If those are the rows, columns are the XYZ coordinated of every single amino acid.
That's also a 2D dataset.
And I think it's these type of rich 2D datasets that power the training of foundation models of biology.
</details>

**Brandon**: 我觉得非常有趣的是，你是如何把一个相当直接的分析实验变成……这是 NGS（下一代测序），对吧？下一代测序，非常高通量。你利用它扩大了一个简单的扰动响应实验，在如此大规模下进行，简直是一项壮举。基本上，是一个任意数量的细胞。我想你们做了 2500 万或类似的规模。

<details>
<summary>Original English</summary>

**Brandon**: I find it really fun how you have turned a fairly straightforward assay in using...
This is NGS sequencing, right?
Next generation sequencing, very high-throughput.
You've used this to scale a simple perturbation response, which is inevitably maybe not all that interesting to this massive scale of over a...
Basically, an arbitrary number of cells.
I think you did 25 million or something.
</details>

### 数据规模化背后的工程挑战

**Xi Chu**: 其实比那要多得多。2500 万是经过最严格质量过滤后得出的数据。弄清楚如何进行 CRISPR 和单细胞 RNA 测序，实际上既是一项工程挑战，也是一项科学挑战。在实验的第一部分，我们通常必须收获数千万甚至数亿个细胞，它们必须经过各种质量漏斗过滤，最终才能为团队提供最高质量的数据。这做起来极其困难，因为你可以想象，所有这些技术以前都在学术界发表过，而且在小规模实验中效果很好。但当你考虑将它们扩展到全基因组扰动时，我们谈论的是处理数亿个细胞。学术界发表的技术过去都是围绕着处理新鲜细胞展开的。细胞还是活的。如果你的整个实验只需要一两个小时，那可能没问题。但在长达 14 小时的一天里处理这些细胞就不那么容易了。那是数亿个细胞。所以到了这一天结束时，就像基因组学团队那样，你可以很容易地检测到来自细胞以及实验室科学家的压力信号。我们很快意识到，这不是生成这些数据的方式。机器学习非常依赖质量，我们希望为我们的 AI 团队提供最高质量的数据。因此，我们投入了大量的工程思维，逐步将整个工作流程工业化，引入了化学固定机制，以便我们在实验开始时锁定细胞的状态，但又找出了不破坏后续所有分子生物学步骤的方法。它不会影响数据质量，因此我们可以以一种跨越时间的操作方式来进行所有这些数据的生成，这种方式非常不容易产生批次效应。

<details>
<summary>Original English</summary>

**Xi Chu**: So it's actually a lot more than that.
So 25 million is what came out of the most stringent quality filtering.
It's actually as much of a scientific challenge to figure out how to do CRISPR and scRNA-seq as it is an engineering challenge.
In the first part of the experiment, oftentimes we have to harvest tens, if not hundreds of millions of cells, and they go through various quality funnels to arrive to give the Bowen team the highest quality data at the end.
That's incredibly difficult to do because, as you can imagine, all of these techniques have been published by academia before, and they work very well in small-scale experiments.
But when you think about scaling them to a genome-wide perturbation, we're talking about handling hundreds of millions of cells.
Techniques that are published in academia used to be all about handling fresh cells.
Cells are still alive.
And that may be okay if your entire experiment takes only an hour or two.
It's not quite easy to handle cells across a 14-hour day.
That's hundreds of millions of cells.
And so by the end of the day, is the Jokumet team, you can easily detect stress signals from the cells and from your scientists in the lab.
And quickly we realized that's not the way to do these data generation.
Machine learning is very quality dependent, and we want to make it the highest quality data to our AI teams.
So we're putting a lot of engineering thought in, industrialized the whole workflow step by step, introduced chemical fixations so that we lock the state of the cells in at the beginning of this experiment, but figure out ways that it doesn't disrupt all of the molecular biology steps afterwards.
It doesn't impact data quality so that we can do all of these data generation in a time-shifted operational manner that's very not prone to batch effects.
</details>

**RJ**: 你没有提到的一件事是，你们在使用某种干细胞。所以很明显，你们没有真正的脑细胞或血细胞。或者如果你们有，那么在它们身上会有很大的组合效应。那么，你们为什么确信研究干细胞是个好选择呢？据我了解，它们实际上是干细胞行为被解锁后的血细胞。那也会对细胞造成某种压力。所以你们得到了这些不完全是血细胞的受压细胞。那么，我们为什么相信那能很好地替代脑细胞或者你们研究的任何细胞呢？

<details>
<summary>Original English</summary>

**RJ**: One thing that you didn't mention is that you're using some sort of stem cells.
And so obviously you don't have brain cells or blood cells.
Or if you did, then you would have a big combinatorial effect on that.
So why are you convinced that working on stem cells, which my understanding is that there are actually blood cells that have been sort of the stem cell behavior has been unlocked on them.
And that causes some sort of stress on the cell as well.
So you have these like sort of not quite blood cells that are stressed.
And then how, why are we convinced that that is a good proxy for a brain cell or whatever your study?
</details>

**Xi Chu**: 是的，不完全是这样。所以我们实际上并不是从干细胞开始的。那更多是后来的发展。当我们开始数据生成时，我们发布了我刚才提到的方法，以及前两个数据集，这是当时世界上最大规模的 Perturb-seq 数据发布。去年 6 月在预印本中，我们称之为数据集 XLS Orion。那实际上是由两种细胞系生成的。这个领域的许多早期工作都是从细胞系开始的。这些就是细胞。癌细胞系。其中一个是癌细胞系。另一个只是普通的细胞系。这些是永生化细胞。其中一些源自癌症，因此被称为癌细胞系。另一些只源自原代细胞，但已经被永生化处理。很多时候它们在各个实验室里培养了许许多多年。你可以想象，人们一开始使用这些细胞系，因为它们很容易操作。它们很容易规模化，很容易从中培养出大量的细胞。事实证明，培养数百万个细胞的能力对于进行这些大型实验至关重要。

<details>
<summary>Original English</summary>

**Xi Chu**: Yeah, not quite. So we didn't actually start with stem cells. That was more of a later development.
When we started data generation, so we put out the method that I talked about, as well as the first two datasets, which is the world's largest perturbsic data release at the time.
Last June in the preprint, we call it dataset XLS Orion.
That was actually generated from two cell lines.
A lot of this field's early work started with cell lines. These are cells.
Cancer cell lines. One of them is a cancer cell line.
The other is just a cell line. These are immortalized cells.
Some of them are derived from cancers. Hence cancer cell lines.
Others are just derived from primary cells but have been immortalized.
Many times grown for many, many years in various labs.
People start with these cell lines in the beginning, as you can imagine, because those are easy to do.
It's easy to scale, easy to grow a lot of cells out of.
Turns out the ability to grow millions of cells is actually critical for doing these large experiments.
</details>

**Xi Chu**: 所以我们首先从那里开始。而且它们实际上仍然能捕获它们所来源的细胞类型的特征——结直肠癌细胞以及造血细胞。但在后来最新的预印本中，我们实际上把它扩展到了更多的细胞类型。现在其中一些仍然是细胞系或 T 细胞。我们选择使用细胞系，但其中一些现在已经进入了原代细胞阶段。所以我们在 iPSC 中做了一个实验。这些是诱导多能干细胞。另外一个实验，我们认为这是我们迄今为止做过的最雄心勃勃、最酷的筛选实验。这是一个泛分化（pan-differentiation）多细胞类型的干细胞项目。所以实际上，我们在一个单一的实验中无限制地将 iPSC 分化为 10 种不同的细胞类型。我们在它们之间进行了基因组规模的扰动。你可以想象，我们没有仅仅生成 10,000 个不同的生物学实验，而是做了 10,000 乘以 10 种细胞类型的实验。所以这几乎是一个文库基于文库的（library on library）实验。我们为什么要这样做呢？我们认为，正如 Bo 所说，在数据收集的初始阶段，我认为我们正处于构建虚拟细胞的早期，背景环境、多样性以及数据的丰富性是至关重要的。

<details>
<summary>Original English</summary>

**Xi Chu**: So we started there first.
And they actually still capture the characteristics of the cell types that you're derived from, colorectal cancer, as well as hematopoietic cells.
But later on, in the most recent preprint, we actually explained it to many more cell types.
Now some of these are still cell lines or T cells.
We chose to use cell lines, but some of these have now gone into primary cells.
So we did one experiment in iPSC.
These are induced pluripotent stem cells.
And another experiment in, and we think this is the most ambitious and coolest screen that we've done to date.
This is a pen differentiation multi-cell type stem cell project.
So effectively, we differentiate iPSC into 10 different cell types in one single experiment without restriction.
And we did a genome scale perturbation across them.
So you can imagine, instead of just generating 10,000 different biological experiments, we did 10,000 by 10 cell types.
So it's almost a library on library experiment. Why are we doing this?
We think that in the beginning phase of data collection, as Bo said, I think we're just in the early days of virtual cell building, context and diversity and richness of the data matters.
</details>

<!-- chunk 4/9 -->

### 数据的多维度拓展与空间组学的引入

**Xi Chu**：这不仅关乎细胞的总数或测序读数的总量。这更关乎每一美元能够产出的信息量。所以我们不仅想在基因扰动领域进行规模化扩展，还想在各种生物学背景下进行拓展，这样我们才能为我们的 AI 团队提供最丰富的数据集，以此来构建一个具备通用性的模型。

<details>
<summary>Original English</summary>

**Xi Chu**: It's not just the total number of cells or total number of sequencing reads. It's about bits per dollar in information content. So we want to scale not only in the genetic perturbation landscape, but we also want to scale across biological contexts so that we can give our AI teams the best rich dataset to build a generalizable model on.

</details>

**RJ**：那关于这一点，你们提到“背景（context）”，但很显然，这些细胞和这些实验其实已经与它们原本的“队列”分离了，对吧（我可能忘了具体术语）？你们有没有考虑过利用空间转录组学（spatial transcriptomics）或者其他类似的技术，在扰动的情况下构建模型，同时也将细胞及其周围环境的背景考虑进去？

<details>
<summary>Original English</summary>

**RJ**: Is there any thinking about, so you say context, but obviously these cells and these experiments have been sort of D, I forget the term, but they've been separated from their cohorts, right? Is there thinking about using spatial transcriptomics or other sort of technologies, to build models with perturbations, but in the context of the cells that it lives near?

</details>

**Xi Chu**：问得好。在这个问题上我们有几个层面的考量。第一，这其实正是我们当初想要构建虚拟细胞模型（virtual cell model）的根本原因。你可能会想，既然已经可以在这些细胞系里做详尽的筛选实验了，为什么还需要一个模型？你大可以直接做实验生成数据就行。确实，如果你的研究问题仅限于细胞系中的细胞生物学，那你是对的。我们不需要模型，对吧？至少如果是为了基因筛选，我们直接做实验就好了。但你也说得很对，通常好的靶点、真正有价值的生物学洞察并不存在于细胞系中。它们往往来自于原代细胞，来自于这些细胞在器官内原生的生理环境中，甚至来自于多个器官协同作用时产生的涌现属性。很多免疫学疾病就是这样的。你无法在动物系统、器官或所有这些复杂的转化模型中进行穷尽的、高通量的实验。你可以做一些实验，但它们成本高昂且风险极大。而如果我们有能力构建一个模型，在可行的情况下利用海量数据进行大规模训练，然后对它进行微调并迁移应用，从而在这些复杂模型中做出高质量的因果预测，我们就可以带着尽可能最高质量的假说进入实验室进行验证。我认为，这就是构建虚拟细胞模型的全部意义所在。

<details>
<summary>Original English</summary>

**Xi Chu**: Great question. So we're thinking about that in a couple of ways. Number one, that's actually exactly why we want to build a virtual cell model in the first place. You might think that, well, you can already do exhaustive screening in these cell lines. Why do you still need a model? You can just do the experiment and generate the data. Certainly, if your query is just about cell biology in cell lines, you're right. We don't need a model, right? At least if for genetic screening, we can just do this experiment. But you're also correct that oftentimes good targets, biological insights are not about cell lines. These are about primary cells, about cells in their native physiological context in organs or even multi-organ coming together and have some emergent properties. A lot of immunological disease are that way. You cannot do exhaustive, highly put experimentation in animal systems or in organs or in all of these complex translational models. You can do some experiments, and these are expensive and high-stake. The ability to build a model that can be trained on massive data where it is possible to scale and be trained in a way that can be fine-tuned and transferred to make high-quality causal predictions in these complex models so that we can go into the lab and have the highest quality hypothesis possible to validate. I think that's the whole point about building a virtual cell model.

</details>

**Bo Wang**：但从 AI 的角度来看，我认为你是完全正确的。我相信未来的虚拟细胞模型应该能够整合多种数据模态，而不仅仅是 RNA 表达数据。空间单细胞 RNA 测序已经是一项很受欢迎的技术。即便是对于 scGPT（转录录音为 SEGBT），我们实际上也有一个扩展版本，我们称之为 scGPT-spatial。那是专门针对空间单细胞组学设计的。我们也有论文在早期尝试利用 H&E 染色图像来预测基因表达。你们已经可以从中发现一些信号了。最终，我的预测是虚拟细胞模型不仅能够整合 RNA 测序数据，还能整合更多与功能相关的组学，例如蛋白质组学或者调控端的组学（比如 ATAC-seq），来综合你所有的描述性组学数据集，以预测细胞功能的未来状态。我认为这很可能就是虚拟细胞模型的未来。

<details>
<summary>Original English</summary>

**Bo Wang**: But from AI side, I think you're absolutely right that I believe the future virtual cell model should be able to incorporate multiple modalities, not just RNA expressions. Spatial single cell RNA-seq is already a popular technology. Even for SEGBT, we actually have an extended version. We call it SEGBT spatial. That is specifically designed for spatial single cell omics. We also have papers on early attempts to try to take the HNE images, trying to predict the gene expressions. There's already some signals you can find. Eventually, what I predict is that a virtual cell model will be able to integrate not only RNA-seq, but can integrate more functionally related, for example, pruning omics or other regulatory side of omics such as ATAC-seq to overall combine all your descriptive omics data sets to predict the future states of the cellular functions. I think that's probably the future for virtual cell model.

</details>

**Brandon**：我们最近邀请了来自 Noetic 的 Ron Alfa 和 Dan Baer 作为嘉宾。如果观众想了解更多关于这方面的内容，我觉得我们在那期节目里讨论得相当深入，大家可以去作为背景资料参考一下。你能稍微解释一下空间转录组学（spatial transcriptomics）和空间蛋白质组学（spatial proteomics）是什么吗？

<details>
<summary>Original English</summary>

**Brandon**: We had Ron Alfa and Dan Baer from Noetic as guests recently. Viewers who want to hear a little bit more about that, I think we go quite in depth there. It's a background, you can go to that. Can you explain a little bit about what spatial transcript omics and spatial proteomics are?

</details>

**Xi Chu**：这可能需要讲一点历史。在以前，我们有单细胞 RNA 测序，有常规的 RNA 测序，而在那之前我们有微阵列（microarray）技术。RNA 测序和微阵列过去的做法是取一块组织，把它完全磨碎，你可以想象就像把它放进搅拌机里做成冰沙一样，然后提取那块组织中各种细胞里的所有 RNA 并测量它们的表达水平。这很棒，因为那是人们第一次能够一次性测量所有 20,000 个基因的表达。我们以前只能一次测一个。但这也有个缺陷，那就是我们不知道哪些 RNA 来自哪个细胞。如果你处理的是多细胞的组织块，这就尤其成问题了。你想要将 RNA 归属到免疫细胞、皮肤细胞或成纤维细胞上，但你做不到，因为你把所有东西都打碎成了一杯“冰沙”。单细胞技术能让你做到的是逐个细胞地进行分析。所以现在，我可以将 RNA 基因表达归属到它们各自来源的细胞上。但问题仍然存在——我不知道这些信号在空间上是从哪里来的。这对于许多疾病来说是至关重要的，对吧？例如在免疫肿瘤学中，你想知道 T 细胞什么时候靠近了肿瘤细胞，或者当 T 细胞无法穿透实体瘤时，它们之间有什么区别？再或者，当一个 T 细胞正在攻击肿瘤细胞时，而另一个没有，这其中的区别又是什么？为了弄清楚这些，你需要空间信息。你需要在细胞原本的环境中原位（in situ）观察它们。所以现在有各种不同的技术来解决这个问题。基本上就是，取下那块组织，我不需要再把它磨碎了。我只需要切片，把它铺在载玻片上，我就可以使用标准技术（比如 H&E 染色）来测量它的形态学特征。然后，我还可以使用多重免疫荧光（IF）分析来测量多种蛋白质的表达。最终，我也能够使用最新的空间组学检测技术，在全基因组范围内观察所有这些细胞在其原生空间坐标中的基因表达情况。所以你不仅能拥有每个细胞的 x-y 坐标，还能掌握我们前面提到的所有分子分析物的数据。这对基因组学领域来说是一个令人兴奋的新方向。

<details>
<summary>Original English</summary>

**Xi Chu**: So maybe a bit of a history lesson here. Before, we had single-cell RNA-seq. We had RNA-seq. And before that, we have microarray technologies. What RNA-seq and microarray used to do is take a chunk of my tissue, grind it all up, put in a blender, imagine, make a smoothie out of it, and take all of the RNA from different cells in that piece of tissue and measure all of their expression levels. It is great. For the first time, you can measure gene expression all 20,000 at a time. And we used to do them, we used to have to do them one at a time. But it is not great in that we don't know which RNA came from which cell. And this is particularly a problem if you're dealing with a multicellular piece of tissue. You want to attribute RNA to the immune cell, to the skin cell, to the fibroblasts, but you can't because you want everything up in a smoothie. What single-cell technology allow you to do is analyze them cell by cell. So now, I can attribute RNA gene expression to the cell that they originate from. But there's still a problem. I don't know spatially where these signals come from. And for many disease, it matters, right? In immuno-oncology, for example, you want to know when T cells are close to a tumor cells or when a T cell is not able to penetrate the solid tumor, what is the difference between them? Or when a T cell is attacking the tumor cell, when a T cell is not, what is the difference about that? For that, you need spatial information. You need to observe cell in situ in their context. And so now there are different technologies that solve that problem. Essentially, take that chunk of tissue. I don't have to grind it up anymore. I just make a cross-section, lay it down in a piece of slide, and I can measure its morphology using standard techniques like H and E staining. I can then also measure many protein expression using multiplex IF assays, immuno-forsense assays. Ultimately, I can also look at the gene expression up to genome-wide in all of these cells in their native spatial coordinates by using some of the latest spatial omics assays. So you have the x-y coordinates of every cell, but also all of the molecular analytes that we talked about earlier. And that's an exciting new direction for genomics field.

</details>

**Bo Wang**：就个人而言，你能想象空间组学给 AI 建模增加了多大的难度吗？因为现在你不能只看单个细胞，你必须去观察周围的微环境（niche）细胞，以更好地学习具有空间连贯性的表征。这也是当前空间基础模型所面临的挑战。

<details>
<summary>Original English</summary>

**Bo Wang**: Personally, can you imagine that the spatial omics adds more difficulty to AI modeling? Because instead of looking at the individual cells, you have to look at the neighboring niche cells to better kind of learn the representation that is spatially cohesive. That is the challenge the current spatial foundation model is facing.

</details>

**Brandon**：但这种背景信息对于理解——比如说——癌症将是至关重要的，因为其中包含了免疫细胞、癌细胞以及非免疫（或非癌）细胞之间的相互作用。是的，这绝对是正确的。

<details>
<summary>Original English</summary>

**Brandon**: But that context is going to be crucial for understanding, let's say, cancer where the interaction of immune cells and cancer cells and non-immune or cancer cells. Yeah, that is absolutely right.

</details>

**Bo Wang**：这对于获得一个完整的概貌（profile of zero/完整视图）绝对是至关重要的。你可以提取出具备空间感知的生物标志物来预测一些临床反应。我认为构建这样的模型将是极其重要的。

<details>
<summary>Original English</summary>

**Bo Wang**: It's absolutely crucial for getting a complete file of zero. You can extract spatial-aware biomarkers to predict some of the clinical response. I think that would be extremely important to build such models.

</details>

### 从数据收集到模型架构 (From Data Collection to Model Architecture)

**RJ**：回到 Excel（实际上可能是 xCell 等术语），想必这也是可以为空间模型提供信息的，对吧？因为你有一个位于特定位置的细胞。你可以设想，好，我可以先扔掉坐标，只对一次一个细胞进行推断。然后我现在可以创建一个更复杂的模型，它不仅做这些推断，还能知道它的邻居是谁，诸如此类的。

<details>
<summary>Original English</summary>

**RJ**: Getting back to Excel, this presumably can inform a spatial model as well, right? Because you have one cell in one place. You can imagine, OK, I can just throw away the coordinates and just do inferences on one cell at a time. And now I can create a more complicated model that does that, but it also knows who its neighbors are or something.

</details>

**Bo Wang**：你完全正确。但我们目前发布的版本，还没有处理空间组学数据。然而，毫无疑问，我们正在进行的工作以及 Excel（xCell）的下一个版本，将能够推断不同细胞的空间感知表征。

<details>
<summary>Original English</summary>

**Bo Wang**: You're absolutely right. But the current version we were releasing, we're not dealing with spatial omics. However, definitely our ongoing work and the next version of Excel will be able to infer the spatial-aware representations for different cells.

</details>

**RJ**：我们已经讨论了一些关于数据收集的内容。那我们来谈谈架构吧，给正在听播客的 AI 工程师们来点“硬菜”。

<details>
<summary>Original English</summary>

**RJ**: We've talked about the data collection a bit. Let's talk about the architecture, get some red meat for the AI engineers listening in.

</details>

**Bo Wang**：当然。我们来回顾一下虚拟细胞建模的历史，尤其是虚拟细胞 2.0（virtual cell 2.0）。我认为我们的 scGPT（转录中的 SDGB）为大部分单细胞基础模型奠定了基础，那就是我们采用了自回归训练（autoregressive training），这与 ChatGPT（转录为 chargeability）在语言上训练的方式极其相似。它做的是下一个 Token 的预测。所以我们模仿 ChatGPT 在语言上的训练方式，将单细胞基础模型训练在细胞上。这样做的话，你必须假设基因存在内在顺序。我们假设基因顺序的方式是通过注意力机制（attention mechanism）。还有许多其他方法采用了不同的基因排序，有些很简单，比如仅仅根据表达值对基因进行排名。也有些更复杂的方法来为不同的基因排序。但归根结底，你都必须先假设一个基因的顺序。

<details>
<summary>Original English</summary>

**Bo Wang**: Sure. Let's get to the history of virtual cell modeling, particularly virtual cell 2.0. I think our SDGB sets the foundation for most of foundation models of single cells, is that we adopted autoregressive training, extremely similar to how chargeability is trained on languages. It's next token predictions. So we mimics the way how chargeability is trained on languages to train the single-cell foundation model on cells. By doing that, you have to assume inherent order of genes. The way we assume the order of genes is by attention mechanism. There's many other methods that are using different orders of genes, some as simple as just rank the genes based on the expression values. There's also more complicated methods to rank different genes. But in hand, you have to assume an order of genes.

</details>

**RJ**：需要明确的是，当你谈论基因时，它们在本质上是有顺序的。它们是由 ATGC 拼写出的一句话。所以基因本身带有核苷酸，是一条长链，所以给它们设定一个顺序是非常合理的。但我们在这里谈论的是不同的东西。那是表达数据（expression data），也就是表达水平。这里的表达水平意味着，对于每一个基因来说，它仅仅是一个计数，表示我在测量时看到了多少个这个基因。

<details>
<summary>Original English</summary>

**RJ**: And just to be clear, when you talk about genes, those are intrinsically ordered. They're a sentence spelled out in ATGC. So genes themselves have the nucleotides and there's a long chain, and that makes a lot of sense to have an order to them. But what we're talking about is something different. That's the expression data, the expression levels. So the expression level means how it's just a count for each gene of how many of these genes did I see when I was measuring.

</details>

**Bo Wang**：在序列中，ATGC 的顺序对我们来说完全合理。但对于表达数据，它们实际上只是矩阵。因此，真的很难去假设基因有一个内在的顺序。你甚至可以打乱基因的顺序。我认为其中的生物学意义并没有发生太大改变。然而，由于语言模型的训练方式，大家都有现成的技巧来训练这类模型。所以采用这种方式很方便。这就是所有单细胞基础模型的起步方式。然后我很快意识到，如果使用扩散语言模型（diffusion language models），我们其实根本不需要去假设基因的顺序。相反，我们可以通过一个双向扩散过程来生成这样高维度、长序列的基因表达数据集。只要想一想，自回归训练和扩散语言模型的区别是什么？你可以把自回归训练想象成打字。比如说，“我喜欢咖啡（I like coffee）”。你必须先打“我（I）”，然后打“我喜欢（I like）”，接着才是“咖啡（coffee）”。这是固有的顺序。但扩散语言模型，你可以把它当成编辑。你从一个非常模糊、粗糙的句子开始，迭代地生成一句话。然后你可以不断地去润色它。基因表达也是同样的道理。你可以生成一个基因表达的粗糙表征，然后从充满噪音的表征开始迭代，直到得到更精确的表征。所以你是通过迭代地编辑基因表达的预测，直到它将损失降至最低。因此，这是一种非常不同的预测扰动后反应的生成哲学。事实证明，它其实更适合单细胞 RNA 测序。这也是为什么我们将架构转向了——

<details>
<summary>Original English</summary>

**Bo Wang**: In sequences, the order of ATGC make total sense to us. But for expression data, they're literally just matrices. So it's really hard to assume an inherent order of genes. You might shuffle the order of genes. I think the biology doesn't change much. However, because of the way the language model is trained, everybody has preset tricks to train such models. So it's easy to adopt. That's how all the foundation models are started for single-cell. And then I quickly realized that with diffusion language models, we actually don't need to assume the order of genes. Instead, we can have a bidirectional diffusion process to generate such long, high-dimensional gene expression datasets. So just to think about it, what's the difference between autoregressive training versus diffusion language models? Is that you can think of autoregressive training as typing. For example, I like coffee. You have to type I and then I like and then coffee. That's inherent orders. But diffusion language model, you can treat it as editing. You iteratively generate a sentence from a very vague, very rough sentence. And then you can iteratively refine it. So same thing with gene expressions. You can generate a very rough representation of the gene expressions and then iteratively from noisy representation to more refined representations. So you iteratively edit the gene expression predictions until it minimizes the losses. So this is a very different philosophy to generatively predict the response after perturbation. And it turns out it actually fits more to a single-cell RNA-seq. So that's why we switched it from

</details>

<!-- chunk 5/9 -->

### 虚拟细胞模型与先验知识

**Bo Wang**：一个类似 scGPT 的模型，与目前使用的是扩散语言模型的 X-Cell 模型。

<details>
<summary>Original English</summary>

**Bo Wang**: a scGPT-like model to the current X-Cell model, which is using diffusion language models.

</details>

**Brandon**：当我想到 Transformer 时，它们本质上是对集合进行操作的对象。社区花了很多时间试图让它们成为具有某种因果顺序的事物。但如果你只是简单地使用你的 Transformer，它就是一个集合操作。鉴于此，为什么要根据扩散或自回归的大语言模型来考虑这个问题呢？为什么不让你的初始预测策略像这样：只需要获取一组基因，每个基因都有自己独特的外壳身份，然后用它作为一种预测？对我来说，这似乎是一个更自然的架构。而且这不仅仅是你的工作。很多人都在研究这样的东西。我一直有些困惑，为什么社区里会有这种偏见。

<details>
<summary>Original English</summary>

**Brandon**: When I think of transformers, they're fundamentally objects that operate on sets. The community spends a lot of time trying to make them things which have some sort of causal ordering to them. But if you just naively take your transformer, it's a set operation. So given that, why think about this in terms of diffusion or autoregressive LLMs? Why not have your initial prediction strategy be something like take just a set of genes, each of which has its own cotton-coated identity, and then use that as sort of a prediction? That seems like a much more natural architecture to me. And it's not just your work. A lot of people work on things like this. And I have been somewhat confused why there's this bias in the community about this.

</details>

**Bo Wang**：所以我认为你提到的更多是与表示学习相关的，在那里你可以提取一组基因，并尝试投影到低维隐空间。但我们在构建虚拟细胞生成模型时关心的是什么，因为你想预测细胞的动态变化。所以我们希望有一个生成模型。这就是为什么我们主要使用纯解码器架构，以便生成完整的转录组数据，而不是仅仅预测一小部分预定义的基因，因为你想要对整个基因调控网络建模，这是一种维度极其高的东西，对吧？

<details>
<summary>Original English</summary>

**Bo Wang**: So I think what you were referring to is more related to representation learning, where you can take sets of genes and try to project to low-dimensional latent space. But what we care about for building generative modeling for virtual cell, because you want to predict the dynamics of cells. So we want to have a generative model. So that's why we're mostly using decoder-only architectures in order to generate the full transcriptomics instead of just predict a predefined small set of genes, because you want to model the whole gene regulatory networks, which are extremely kind of high-dimensional, right?

</details>

**RJ**：为了说清楚一点，输入是基因加上扰动。输出是新的基因表达水平。是基因表达水平加上扰动作为输入和输出吗？加上时间细胞，正常细胞。

<details>
<summary>Original English</summary>

**RJ**: So just to be clear, input is genes plus a perturbation. Output is new gene expression levels. Is that gene expression levels plus perturbation is input output? Plus time cells, normal cells.

</details>

**Bo Wang**：比如对每个细胞来说？对。是的。那是正确的。对。

<details>
<summary>Original English</summary>

**Bo Wang**: Like for each cell? Correct. Yeah. That is correct. Right.

</details>

**RJ**：所以对于扩散语言模型，我的理解是这样的——你可以在这里纠正我，因为我对它们了解不多——但我认为它们就像 BERT，但你是一遍又一遍地运行它。这样去理解算是一个好方法吗？

<details>
<summary>Original English</summary>

**RJ**: And so the way that I think about diffusion language models, and you can correct me here because I don't know a lot about them, but the way I think about them is they're like BERT, but you do it over and over again. Is that kind of a good thing to think about?

</details>

**Bo Wang**：是的，这是对扩散语言模型工作原理的粗略理解。是的。

<details>
<summary>Original English</summary>

**Bo Wang**: Yeah, that is a rough understanding of how diffusion language model works. Yeah.

</details>

**RJ**：所以你只是应用扩散过程。扩散过程基本上就像是一遍又一遍地解除掩码或编辑。这类似于图像扩散模型一遍又一遍地完善图像的过程。在这种情况下，我使用的是 BERT。所以它本质上就是一个 Transformer。它是一个 Transformer。但就像是在当前情况下反复更新这句话，也就是一遍又一遍地更新一系列表达水平。

<details>
<summary>Original English</summary>

**RJ**: So you just apply the diffusion. The diffusion process is like basically unmasking or editing once over and over again. The similar to how like an image diffusion model kind of refines the image over and over again. In this case, I'm using BERT. So it is a transformer, basically. It is a transformer. But it is like repeatedly updating the sort of sentence in this case, which is a bunch of expression levels over and over again.

</details>

**Bo Wang**：这是正确的。实际上，在我们的论文中，我们展示了随着扩散步数的进行，损失函数持续下降，预测数据与真实情况的契合度应该持续上升。这意味着模型开始理解如何迭代地改进预测。我明白了。

<details>
<summary>Original English</summary>

**Bo Wang**: That is correct. Actually, in our paper, we show that as the number of diffusion steps goes on, the loss function keeps decreasing, the fitness of the partition to the ground should keep increasing. So this which means the model start to understand how iteratively refine the predictions. I see.

</details>

**RJ**：我们刚才在讨论扩散模型与自回归模型。我注意到论文中有一大段关于使用很多东西进行预处理的讨论。你想稍微谈谈这个吗？

<details>
<summary>Original English</summary>

**RJ**: We're talking about diffusion versus autoregressive. I noticed in the paper, there's a bunch of discussion of preconditioning using a whole bunch of stuff. Can you want to talk a little bit about that?

</details>

**Bo Wang**：我们在 X-Cell 中做的另一个重大创新是我们将先验知识整合到模型中的方式。总的来说，将生物学先验整合进来在生物学中一直是个好主意，因为生物学家们已经花了几十年的时间去理解一些生物学了。我们如何将一些先验知识，一些关于细胞的元数据告诉模型呢？在 X-Cell 之前，人们的做法是试图整合单一类型的先验，例如，使用基因调控网络作为先验来预测扰动。因此，就像之前的模型有时试图整合蛋白质-蛋白质相互作用（PPI）作为先验一样。据我所知，X-Cell 是最早尝试整合极其多样化的生物学先验的模型之一。所以在我们的预印本中，我们整合了五种类型的先验，包括文献，简单到就像你问 Chat 视频：“告诉我关于这个基因的所有信息”，然后我们将输出嵌入。所以它就像一个 GenePT。完全正确。那是一个 GenePT。我们还整合了 PPI，也就是蛋白质-蛋白质相互作用网络。我们还整合了 DepMap（癌症相关的必需基因信息）、形态学信息。我们甚至尝试整合 scGPT 嵌入，这基本上就是细胞类型。所以在有一组先验知识作为模型条件的情况下，模型在针对特定背景的预测上开始具备更高的准确度。而对我们来说更有趣的是，通过观察不同先验的权重，我们实际上可以了解哪些先验知识对这些特定的细胞类型更为重要。因此这为模型增加了更多的可解释性。所以我们发现，结合扩散语言模型以及极其多样化的先验知识，X-Cell 在泛化到未见过的背景时表现得要好得多。这就是我们在 X-Cell 方面做出的一些 AI 创新。

<details>
<summary>Original English</summary>

**Bo Wang**: Another major innovation we made in Excel is the way we incorporate prior knowledge into the model. So incorporating biological priors has always been a good idea in biology in general, because biologists spend decades to understand some of the biologists already. How do we tell the model some of the prior knowledge, some metadata about the cells? Before Excel, what people do is they try to incorporate a single type of priors, for example, gear, using gene-regular network as a prior to predict the perturbations. So, as each video sometimes trying to incorporate PBI as prior as well. Excel, to my knowledge, is one of the first models in trying to incorporate extremely diverse sets of biological priors. So in our preprint, we incorporate five types of priors, including literatures, as simple as just ask chat video, tell me everything about this gene, and then we embed the output as the embedding. So it's like a gene PT. Exactly. That's a gene PT. And we also incorporate PBI, protein-protein interaction networks. We also incorporate DevMap, which is cancer-related essential gene information, morphology information. We even try to incorporate acid-gbt embeddings, which is basically cell types. So with a set of prior knowledge as conditions to the model, the model start to have more accuracy in terms of context-specific predictions. And what's more interesting to us is that by looking at the weights of different priors, we can actually understand which prior knowledge are more important to these particular cell types. So it adds more interpretability to the models. So we find that combining diffusion language model plus a very diverse set of prior knowledges, Excel does much better in generalizing to unseen contexts. So this is some of the AI innovations we made for Excel.

</details>

**RJ**：你现在是必须提供所有那些上下文背景信息，模型才能运行，还是说这些就像是预处理，如果你想的话，模型在没有它们的情况下也能运行？

<details>
<summary>Original English</summary>

**RJ**: Do you now need to provide all of that context in order for the model to work, or those are like preconditioning that it can also do without if you want?

</details>

**Bo Wang**：我们不再需要提供这些先验知识了，因为它们已经变成了模型内部的可学习参数。不过，你建议的做法更像是针对虚拟细胞的提示工程或是上下文学习。我们同样也可以做到这一点，基本上就是通过在先验知识中加入更多条件，从而促使模型朝着特定的方向进行预测。

<details>
<summary>Original English</summary>

**Bo Wang**: We don't need to incorporate these prior knowledge anymore because these are already learnable parameters inside the models. However, what you suggest is more prompt or in-context learning for virtual cells. We can do that as well, basically by adding more conditions into the prior knowledges so that to prompt the model to predict towards certain directions.

</details>

**RJ**：换句话说，模型现在利用了基于你在训练期间提供的先验知识所进行的学习，并且不再需要它们了，但由于你在训练期间提供了它们，模型拥有了一定优势，如果你能够在推理期间提供这些先验，你甚至能获得更大的优势。

<details>
<summary>Original English</summary>

**RJ**: In other words, the model now takes advantage of the learning using the priors that you provided during training and doesn't need them, but has some advantage because you provide them during training, but you can even get more advantage if you are able to provide those priors during inference.

</details>

**Brandon**：那有多重要？每当我看到包含一大堆东西的大型机器学习论文时，我总是会想：重大的突破点在哪里？微小的改进在哪里？这些因素仅仅是增加了一点增量性的性能提升，还是所有这些对于泛化能力都是真正至关重要的？

<details>
<summary>Original English</summary>

**Brandon**: How much does that matter? Whenever I see big machine learning papers with tons of things thrown in, I'm always wondering where's the big alpha and where's the little alpha? Are these adding this little bit of incremental performance boost, or are all these actually crucial to generalization?

</details>

**Bo Wang**：我们需要考虑多个因素。数据贡献了多少？AI 架构贡献了多少？即使只针对架构，从自回归训练转换到扩散模型带来的变化量是多少？先验知识带来的变化量是多少？当然，所有这些都需要进行非常具体的消融实验。从实证实验来看，数据集的质量和规模最重要。这就是为什么我们非常兴奋能够发布 Pisces 数据集，它跨越了 2500 万个细胞的 16 种不同的细胞类型。它是全基因组规模的。如果你真的从计算机的角度去思考，那是一个巨大的张量。全基因组范围的扰动、全基因组的转录组数据，加上细胞数量再乘以条件的数量。这是非常庞大的张量。由于出色的混合筛选技术，我们没有遇到批次效应的问题。你不需要让模型费力去克服批次效应。所以我们发现，在扰动数据集，也就是高质量的扰动数据集上进行训练，就已经给模型带来了巨大的提升。我们还进行了消融实验，如果我们将现有的所有虚拟细胞模型，包括目前最好的模型以及最初的 scGPT 模型放在相同的数据集上进行训练，我们会观察到多大的差异？我们也报告了那里的结果。我们发现，从自回归训练切换到扩散语言模型在应对一些更困难的任务上取得了显著的进步，尤其是在泛化到未见过的任务时。而先验知识多少有些依赖特定条件，对于某些细胞类型，一部分先验知识带来了巨大的差异。但对于部分细胞类型，这种变化似乎微乎其微。我们正在考虑如何更好地整合先验知识。我们仍然认为，让模型了解现存的大量生物学知识应该是有帮助的。但也许是我们通过交叉注意力机制引入先验知识的方式限制了元数据的效用范围。但我认为这肯定是一个研究课题。但总体而言，如果必须要排个序，我的排序是：数据集的质量与规模第一，其次是架构，然后是先验知识。就我个人而言，这只适用于我们的架构。我确信架构可以有不同的选择，并且在贡献度上会有不同的排名。

<details>
<summary>Original English</summary>

**Bo Wang**: There's multiple factors we have to consider. How much contribution the data contributed? How much of the AI architectures contributed? Even for the architecture, what's delta from switching to autoregressive training to diffusion? What's delta from the prior knowledges? Certainly, all of these needs very specific ablation studies. From empirical experiments, the quality, the amount of the data sets matter the most. This is why we were extremely excited to publish the Pisces data sets, which has 16 different cell types across 25 million cells. It's genome-wide. It has a huge tensor, if you really think about it from a computer perspective. Genome-wide perturbation, genome-wide transcriptomics plus number of cells plus times the number of conditions. It's massive tensors. Because of the poor screening technology, we don't have batch effects. You don't need the model to climb the heel of batch effect. So we find that trained on perturbation data sets, high-quality perturbation data sets, already gives a big boost to the models. We also did ablation that if we train all the virtual cell models out there, including state cell to send us original SDG video on the same data sets, what's the delta we are observing? We reported the results there as well. We find that switching from autoregressive training to diffusion-language models give a significant improvement over some of the harder tasks, particularly generalized to on-scene tasks. And the prior knowledge, more or less condition-specific, for certain cell types, some of the prior knowledge makes a huge difference. But for certain cell types, the delta seems to be marginal. We are thinking about how to better incorporate the prior knowledge. We still believe that letting the model know a big chunk of existing biology should be helpful. But maybe it's the way we incorporate the prior knowledge through cross-attention, limited the scope of the metadata. But I think it's certainly a research topic. But overall, if we have to give an order, my order would be the quality among scale of the data sets and then the architecture and then the prior knowledge. Personally, this only applies to our architecture. I'm sure there's different choices of architecture and have different ranks of contributions.

</details>

**RJ**：首先，这是一个非常引人入胜、非常酷的模型。我希望每个人都能有机会去读读这篇论文。显然你们为了做成这件事投入了大量的资源。我不知道你们能不能透露具体有多少。不管多少，肯定是一大笔钱。运营湿实验室、可能还需要进行非常复杂的模型训练。我想里面有几个四十亿参数的模型。对吧？四十九亿。是的，四五十亿参数的模型。这么大的模型可能需要很多 GPU 才能训练出来。与我们单纯把钱投入到湿实验室的工作以及一直以来作为常态的那些传统管线相比，你们从这项努力中获得了怎样的提升？

<details>
<summary>Original English</summary>

**RJ**: First of all, this is a really fascinating, very cool model. I hope everyone has a chance to look at the paper. There's obviously a lot of resources that were put into doing this. I don't know if you guys can disclose how much. It's a lot of money, whatever it was. Operating wet lab, probably very complicated training runs. I think there's a couple four billion parameter model. Is that right? Four point nine billion. Yeah, four or five billion parameter model. So much larger model probably took a lot of GPUs to train. What's the lift that you get from this effort versus let's just put the money into wet lab work and the sort of traditional pipeline that basically has been the status quo up until now.

</details>

**Xi Chu**：生物学是一门跨尺度的学科。在最基础的层面上，有细胞，有 DNA 序列。接着往上有细胞，有多细胞的组织块，以及共培养体系。你有组织，有动物系统，最后是你有着人类。我认为我们希望能够对这个图谱更偏右边（宏观）的部分进行因果预测。最终实现对人类的因果预测，去知晓哪些药物会对哪些病患起作用，但收集这些高通量数据是非常困难的。虚拟细胞的整个愿景是在有可能的地方生成数据，以便我们能够将因果预测向右边转移，向更具临床转化价值、更复杂的系统转移。当然，现在你已经可以进行数据挖掘了。正如 Bo 所说的，我们生成了大量的数据，包含 7 种筛选、16 种不同的生物学情境，以及基因组规模的扰动。这其中已经孕育了许多很好的想法。我们在预印本中放了一张图，专门看 T 细胞的失活。我们已经看到了一些东西，我们看到了已知的生物学现象，比如 TCR 复合体。我们也看到了一些起缓解作用的

<details>
<summary>Original English</summary>

**Xi Chu**: Biology is a multi-scale discipline. There are cells, there are DNA sequences on the most fundamental level. There are cells, there are multi-cellular pieces of tissues, co-cultures. You have tissues, you have animal systems and finally you have human. I think we would like to be able to do causal protection towards the right of the spectrum. Ultimately, do call the prediction in human, know what drugs will work in which patients, but that's very difficult to collect high-throughput data on. The whole vision of virtual cell is to generate data where it is possible so that we can transfer the causality protection towards the right, towards the more translational, the more complex systems. Certainly you can mine the data already. We generated a lot of data as Bo said, seven screens, 16 different biological context, genome scale perturbation. There's a lot of good ideas in that already. There is a figure that we put out in the preprint that just looking to inactivation of T cells. We already saw some, we saw known biology, TCR complex. We also saw some palliative

</details>

<!-- chunk 6/9 -->

### Identifying New Biology and Model Generalization

**Xi Chu**: 发现新的生物学机制，我们非常激动能在实验室中去验证它。其中一些机制实际上也在去年 12 月湾区 Alex Marson 实验室发表的一项最新筛选研究中被提到了。看到这个非常令人兴奋。但我们的希望不仅仅是挖掘现有数据。我们的希望是，模型能够具备泛化能力，从而使我们在未来能够进行计算机模拟 (in silico) 实验。以前没有人知道需要多少数据以及什么样的数据才能做到这一点，整个领域都在等待证明模型在扰动预测方面能够超越线性基线 (linear baseline)，并且可以泛化到未见过的上下文中，不仅是在你有训练数据的细胞系内，而是超出那个上下文。这就是为什么你需要一个模型。所以让我们非常激动的是，在这篇预印本中，我们看到了那种泛化能力。有几个证明。我们首先在 T 细胞中进行了测试。我们实际上是专门为此目的生成的数据。我们生成了静息 T 细胞的扰动筛选数据。所以这些是在其基线条件下的 T 细胞，没有被激活。然后我们现在也有一个激活的 T 细胞扰动数据集。

<details>
<summary>Original English</summary>

**Xi Chu**: new biology, which we're very excited to validate in the lab. Some of that were actually also called out in a very recent screen last December published from Alex Morrison lab, also in the Bay area. Very excited to see that. But the hope is to not just mine the existing data. The hope is that the model can generalize and we will be able to do in silical experiment into the future. Nobody knows before how much data and what kind of data are needed to do that with the whole field is waiting for the demonstration that the model can be linear baseline in perturbation prediction and it can generalize out context, not just within the cell line you have training data on, but out of that context. That's where that's why you need a model. So what's very exciting for us is that in this preprint, we saw that generalization capability. A few demonstrations. We first did in T cells. We actually generated the data expressly for this purpose. We generated the resting T cell perturbation screen. So these are T cells in their baseline condition, not activated. And now we have an activated T cell perturbs.

</details>

**RJ**: 所以激活 T 细胞意味着我要去，我试图去杀死什么东西。

<details>
<summary>Original English</summary>

**RJ**: So just T cell activation means I'm going, I'm trying to kill something.

</details>

**Xi Chu**: 这些是调节性 T 细胞 (regulatory T cells)，但没错，我们激活它们的受体，让它们开始增殖。它们变得更加活跃。它们可以执行其物理功能。而我们仅仅在静息 T 细胞上训练了模型。然后我们告诉模型，“嘿，这就是活跃 T 细胞现在的样子，现在去预测在这些活跃的 T 细胞中所有的扰动将会产生什么影响。”模型并没有见过扰动在活跃 T 细胞中是如何起作用的。我们设置了几个严格的测试。一个是线性基线，提取静息状态下的扰动差异 (delta)，然后直接线性地转置到活跃 T 细胞上。这就是我们的线性基线。从本质上讲，可以将其视为一个组合扰动预测问题。其中一个扰动是细胞的激活。另一个是所有全基因组范围的扰动。我能只是线性地将这两个效果加在一起吗？那将是一个线性基线。其次，我们应用了该领域的其他模型。最后，我们应用了 X-Cell，关键是，X-Cell 并没有见过活跃的 T 细胞。但它能够做出准确的预测，对于已知的生物学机制，比如 TCR 复合体，准确预测了它们的影响，也就是这些扰动会使 T 细胞失活，这正是我们期望看到的。但同时它也正确预测了我们在筛选中发现的推定的 T 细胞失活剂。所以这对我们来说非常令人兴奋。这表明了这样一种可能性：我们也许能够在未见过的、完全超出上下文的情境中使用这些虚拟细胞模型，并预测新的生物学。因此我们非常激动能跟进这些线索，并在实验室中验证它们。非常简短地提一下，我们看到的展示了这个模型令人兴奋的泛化能力的另外几个案例。记得我们做了一个多细胞类型的分化 iPSC (诱导多能干细胞) 实验。在那里，我们特意从训练中留出了一种细胞类型。所以模型没有见过那种细胞类型。它在其他细胞类型以及其余数据集上进行了训练。该模型在那个未见过的细胞类型中，跨越数千个基因和数千种扰动，做出了非常好的预测。所以这再次表明了模型跨细胞类型泛化的能力。最后一个实验，我认为非常激动人心的是，我们在 T 细胞系上训练了这个模型，但最近 Alex Marson 实验室发表了一篇关于原代 T 细胞的 Perturb-seq (扰动测序) 论文。那是一项令人印象深刻的工作。在原代细胞中进行这种规模的筛选并不容易。很少有实验室具备那样的能力。在 T 细胞系中做这件事要容易得多。再次，该模型能够从细胞系泛化到原代细胞，并在那里做出准确的预测。

<details>
<summary>Original English</summary>

**Xi Chu**: These are regulatory T cells, but yes, we activate their receptor so that they're starting to proliferate. They become more active. They can do their physical job. And we only train the model on the resting T cell. And we told the model, Hey, this is how the active T cell look like now go and predict what all of the part of which are going to do in this active T cell. And the model have not seen how perturbation working active T cells. And we set up a couple of rigorous tests. One linear baseline took the perturbation delta in the resting case, just transpose that linearly onto the active T cell. And that's our linear baseline. Essentially, think about this as a combinatorial perturbation prediction problem. One of the perturbation is activation of the cell. The other is all of the genome wide perturbations. Can I just linearly add the two effects together? That would be a linear baseline. And second, we apply other models from the field. And last, but we applied X-Cell critically, X-Cell has not seen active cell T cells. And it's able to make accurate prediction, known biology, the TCR complex, predicting their effect accurately that these are going to inactivate the T cells, which is exactly what we would expect to see. But also it predicted the putative T cell inactivators that we found in the screen correctly as well. So that's very exciting to us. And that suggests the possibility that one might be able to use these virtual cell models completely out of context in the unseen context and predict new biology. And so we're very excited to follow up on those heads and validate them in the lab. Just very briefly, a couple other cases that we saw exciting generalizing capability of this model. Remember, we did a multi-cell type differentiated iPSC experiment. There we specifically held out one cell type from training. So the model has not seen that cell type. Train on the other cell types, as well as the rest of the datasets. The model made very good prediction across thousands of genes, thousands of perturbations in that unseen cell type. So again, it suggests the model's ability to generalize out of cell type. And the last experiment, I think we're very excited, is that we trained this on T cell cell line, but there was just very recently a primary T cell perturb-seq published from Alex Marson's lab. That's an impressive amount of work. It's not easy to do this scale screening in primary cells. Very few labs have that kind of capabilities. It's much easier to do that in T cell lines. Again, the model is able to generalize out of cell lines into primary cells and make accurate predictions there.

</details>

**RJ**: 所以他们实际上扰动的是原代细胞，而不是细胞系？

<details>
<summary>Original English</summary>

**RJ**: So they actually perturbed primary cells, not cell lines?

</details>

**Xi Chu**: 从捐赠者那里收获的原代 T 细胞。而我们能够从多个捐赠者那里做到，并且仅仅在一个 T 细胞系上训练的 X-Cell 模型，能够跨越多个捐赠者对原代 T 细胞实验做出预测。

<details>
<summary>Original English</summary>

**Xi Chu**: Primary T cells harvested from donors. And we were able, from multiple donors, and the Excel trained on just one T cell cell line is able to make predictions across multiple donors from primary T cell experiments.

</details>

**RJ**: 这就是对整个理论的验证，对吧？也就是你可以在这些有些奇怪的细胞（指细胞系）上进行训练，并且它会表现很好，因为你已经足够好地覆盖了这个域或其他什么，从而让你能够真正在直接来自真人的真实细胞中进行预测。是的。

<details>
<summary>Original English</summary>

**RJ**: This is a validation of the whole theory, right? That you can train on these slightly weird cells, and that it will be good because you're covering the domain well enough or whatever it is, that you're able to actually predict in real cells that come directly from real people. That's right.

</details>

### Virtual Cells and Clinical Generalization

**Bo Wang**: 是的。我认为建立虚拟细胞并不是为了取代生物学实验，正如你所提到的。我们试图做什么？真的，虚拟细胞的圣杯是拥有一个模型，可以泛化到那些更难甚至不可能进行生物学实验的未见过的上下文中，对吧？到目前为止，X-Cell 专注于细胞系。而最终，我们希望扩展到更复杂的生物系统，比如动物、类器官 (organoids)。最终，在用于患者之前，用于人类生物学，对吧？记住几个数字，90% 的疾病没有治愈方法。大多数药物在针对患者的三期临床试验中失败。而三期试验的成功率低至 5% 到 10%。三期意味着什么？在患者试验中的最后阶段。

<details>
<summary>Original English</summary>

**Bo Wang**: Yeah. I think building virtual cells is not to replace biological experiments, as you mentioned. What are we trying to do? Really, the holy grail of virtual cell is to have a model to generalize to on-scene context that is harder or even impossible to conduct biological experiments on, right? So far, Excel focusing on cell lines. And eventually, we want to extend to more complicated biological systems such as animals, organoids. And eventually, before, to patients, to human biology, right? And bearing a few numbers, 90% of disease has no cure. And most of the drug failed at the phase three clinical trials on patients. And the success rate of phase three trials is as low as five to 10%. And phase three means? The final stage on the patient trials.

</details>

**RJ**: 所以那就是你从二期的毒性泛化到三期的疗效。从小样本队列。哦，抱歉。毒性是二期。到了一个大样本队列。所以这个泛化问题就是，好吧，对于这种药物，我非常仔细地挑选了我的患者，它效果很好。然后现在我得到了一大批患者，突然之间，它效果就不那么好了。这就是你们（试图解决的）大问题...

<details>
<summary>Original English</summary>

**RJ**: So that's when you generalize from toxicity in phase two to efficacy in phase three. From a small cohort. Oh, sorry. Toxicity is one. And so a lot of large cohort. So the generalization problem, okay, this drug, I've very carefully selected my patients, and it works pretty well. And now I get a bunch more patients, and suddenly, it doesn't work very well. And that's the big problem that you're...

</details>

**Bo Wang**: 虚拟细胞的承诺是，我们能否建立一个学习了所有生物学因果关系的模型，以便它能够以此为基础，最终预测患者的反应，从而对于某些药物，我们可以选择合适的患者来进行临床试验。所以这是一个长期的目标，但我们已经看到了一些早期的希望，在多样的因果数据集上训练的 X-Cell 已经能够泛化到一些未见过的细胞类型。所以肯定还有很多实验需要做来验证这个模型。甚至需要不断地微调这个模型，但我认为我们确实看到了一些早期的希望。

<details>
<summary>Original English</summary>

**Bo Wang**: The promise of virtual cell is that can we build such a model that learn all the causality of biology so that can be grounded to predict the response eventually on patients so that we can, for certain drugs, we can select the right patients to conduct the clinical trials on. So this is a long-term but we already see some early hopes that Excel trained on diverse set of causal datasets can already generalize to some unseen cell types. So certainly there's a lot of experiments to be done to validate this model. So even continuously finding this model, but I think that we certainly see some early hopes.

</details>

### Beating Linear Baselines and the Need for Causal Data

**Brandon**: 所以你刚才提到了线性模型，这就引出了这个著名或者说声名狼藉的关于扰动的 ARC 挑战。一直有一种说法，认为复杂的基石模型往往无法击败线性基线。我想听听你对此的看法，就这方面来说，首先，这次有什么不同吗？我想你们自己过去的一些模型可能也遇到过难以击败线性基线的问题。你们当前的数据策略，或者你们的发展方向、整个领域的发展方向有什么不同吗？在虚拟细胞模型中，相较于这些简单的基线，基石模型的作用到底是什么？

<details>
<summary>Original English</summary>

**Brandon**: So you were talking about linear models and this brings up this famous or infamous arc challenge about perturbation. And there's been this theme about complicated foundation models oftentimes not beating linear baselines. And I'd like to get your take about that as terms of, is this... First of all, is this different? I think some of maybe your own models might also have had trouble beating linear baselines in the past. Is there something different about your current data strategy or where you're going and where's the field going? And what is the role of foundation models versus, or in virtual cell models versus these simple baselines?

</details>

**Bo Wang**: 是的，有几点。首先，正如你提到的，那些基准测试 (benchmarks) 是在 Replogle 数据集上进行的，那是非常小的数据集。人们报告的指标大多是 MAE (平均绝对误差)。当然你可以想象，如果……因为单细胞数据集非常稀疏，细胞的平均表达谱，你当然可以想象它是一个很好的局部最优解来最小化 MAE。这就是为什么有时细胞的平均表达谱的 MAE 甚至比技术重复 (technical replicates) 还要低，而技术重复被认为是扰动实验的真实标准 (ground truth)。所以这本身就说明那个指标是不可靠的。然而，这些基准测试中的大多数仍在比较那些在静态表达数据集（例如 cellxgene）上训练的基石模型。scVI 经常被用作内部基准测试。我们也发现，在涉及 MAE 时，有时 scVI 某种程度上未能优于线性模型，仅仅是因为我刚才陈述的原因。而让 X-Cell 不同于这些静态表达模型（如 scVI 或 Geneformer）的地方在于，我们实际上，与其在基因表达数据集上训练，我们是在因果数据集上训练。我们在海量的全基因组扰动数据集上训练，这样它就能更好地学习干预的动态变化。在我们的预印本中，我们也广泛地与线性模型进行了比较。正如你提到的，线性模型完全无法扩展到未见过的细胞类型。你可以很快想象出原因。我相信基石模型或在正确数据上训练的其他更复杂的 AI 模型，在更难的任务中将优于这些线性模型，特别是在泛化任务中。这就是为什么我一直强调，正确的数据集加上正确的 AI 模型将带来巨大的进步。但我认为该领域仍然需要看到更多的生物学验证，才能更令人信服地认为虚拟细胞的方向是正确的。

<details>
<summary>Original English</summary>

**Bo Wang**: Yeah, a few things. First of all, those benchmarks, as you mentioned, are conducted on replogor datasets, which are very small datasets. And the metrics people report are mostly MAE. Certainly you can imagine if the... Because single cell data set are so sparse, the average profiles of the cells, certainly you can imagine is a great local optimum to minimize the MAEs. This is why sometimes the average profile of cells has lower MAEs even than technical replicates, which are considered off-ground truth for perturbation experiments. So that itself shows that that metric is not reliable. However, most of these benchmarks are still comparing foundation models that trained on static expression datasets, such as cell by genes. SGV is often benchmarked against internally. We also find that when it comes to MAE, sometimes SGV kind of fail to outperform linear models, just because of the reasons I just stated. And what sets Excel different from these static expression models, such as SGV or geneformers, is that we actually, instead of training on gene expression datasets, we train on causal datasets. We train on massive amount of genome-wide perturbation datasets, so that it learns better about the dynamics of the interventions. And in our preprint, we extensively compare with linear model as well. And as you mentioned, linear model totally failed to extend to unseen cell types. You can quickly imagine why. And I believe that foundation model or other more complicated AI models that train on the right data will outperform these linear models in harder tasks, particularly in generalization tasks. And that's why I keep mentioning the right dataset with the right AI model will lead to huge improvements. But I think the field still needs to see more biological validations to be more convincing than the virtual cell direction is the right one.

</details>

**Xi Chu**: 是的，我认为该领域受到缺乏一致且被统一接受的基准测试的困扰。被测量的东西才能得到改进。在我们的论文中，我们测量了，我认为我们投入了大量思考并看到模型真正大放异彩的指标之一，是围绕基因表达变化的指标。也就是皮尔逊差异 (Pearson Delta)，即预测的变化与扰动后的真实变化之间的相似性。这是很难作弊的。你必须真的把变化预测对。而真正让我感到震惊的是，当我看到模型做出预测，只是把基因表达变化的热图打印出来，看实际的原始数据，并把线性基线的预测、真实数据和 X-Cell 的预测一起并排对比。视觉上非常清晰地看到，X-Cell 的预测比线性基线与真实数据的相似度高得多。

<details>
<summary>Original English</summary>

**Xi Chu**: Yeah, I think the field suffer from a lack of consistent and uniformly accepted benchmarks. What gets measured will get improved. And in our paper, we measured, I think one of the metrics that we put a lot of thought into and saw the model really shine is metrics around gene expression changes. So in Pearson Delta, the similarity between predicted changes and ground truth changes upon a perturbation. That's very hard to cheat on. You have to really get the changes right. And what really blew my mind away is when I saw the model make prediction, just print out the heat map of the gene expression changes, look at the actual raw data and line up the linear baseline prediction, the ground truth and the XR prediction altogether. It's visually very clear to see that XR prediction is very much more similar to ground truth than the linear baseline.

</details>

**Bo Wang**: 这就是我一开始谈到的“惊叹”时刻 (wow moment)。

<details>
<summary>Original English</summary>

**Bo Wang**: This is a wow moment I was talking about in the beginning.

</details>

**Xi Chu**: 也不难理解为什么，当我们把……所以这是第一次有人能够把不仅是一个 Perturb-seq 实验，而是七个全基因组范围的 Perturb-seq 实验结合在一起。立刻让我们这些生物学家注意到的一件事是，一些扰动是上下文普遍的，意思是这些基因做……

<details>
<summary>Original English</summary>

**Xi Chu**: And it's not hard to understand why when we put, so this is the first time that someone can put together not just one perturbs, but seven genome-wide perturbs campaigns together. Something that jumped out to us, biologists right away is that some of the perturbations are context universal, meaning that the genes do the

</details>

<!-- chunk 7/9 -->

### Context Specificity and Combinatorial Perturbations

**Xi Chu**: 对于你在实验中使用的细胞类型，你可能会发现这并不奇怪，这些是你的管家基因，对吧？当然，它们在每个细胞中做同样的事情。然后还有所有其他基因簇，它们具有非常特定于上下文的功能，它们在不同的细胞中做不同的事情。同样，不难想象为什么在 iPSC （我们的干细胞）中，我们看到了发育相关的基因，这对神经分化很重要。它们当然只在 iPSC 实验中亮起，对吧？这很合理。所以如果你思考生物学，它是如此复杂，以至于你必须捕捉这些，你知道，上下文普遍的扰动效应。你还必须以某种方式了解上下文相关的扰动效应。因此不难看出为什么非常复杂的非线性模型能够更好地捕捉并学习所有这些生物学。

<details>
<summary>Original English</summary>

**Xi Chu**: same thing in regards to the cell types you experiment in might not be surprising to you that these are your housekeeping genes, right? Of course, they do the same thing every cell. And then there are all of these other clusters of genes that have very context specific functions, they do different things in different cells. Again, not hard to imagine why in iPSC in our stem cells, we saw developmentally relevant genes, that are important for neural differentiation. They only light up in iPSC experiments, of course, right? That makes sense. So if you think about biology, it's so complicated that you have to capture these, you know, context universal perturbation effects. You also have to somehow learn the context dependent perturbation effects. It's not hard to then see why a very sophisticated nonlinear model is able to capture and learn all of those biology much better.

</details>

**Brandon**: 你们的扰动总是单基因扰动吗？或者你们还有更多？因为我对调控网络的理解是，通常情况下，有时候一个单基因可以做很多事情。例如，我认为雄性的分化仅仅是因为在胚胎发育的第七天左右启用了一个基因。这个基因就区分了所有东西。但有时候你有大型的基因网络，它们都非常冗余，这允许更微妙的反馈机制等。所以我可以想象许多单基因扰动可能有点无关紧要。而且你可能想在这里开始采用更多的组合策略。

<details>
<summary>Original English</summary>

**Brandon**: Are your perturbations always single gene perturbations? Or do you have more? Because my understanding of regulatory networks is oftentimes, sometimes it can be a single gene does a ton of things. For example, I think males are just differentiated due to one gene being enabled at like day seven of embryo development or something. And that differentiates everything is this one gene. But then sometimes you have large networks of genes, which all are very redundant, which allows for more subtle feedback mechanisms and so on. So I could imagine a lot of single gene perturbations as being kind of irrelevant. And that you might want to start having a more commentorial strategy here.

</details>

**Xi Chu**: 是的，这是一个很好的问题。Bo 和我思考过很多。实际上，很有趣的是你提到了生殖生物学，我研究过很多在雌性细胞中，关于补偿、剂量补偿机制的情况。雌性细胞有两条 X 染色体，雄性细胞有一条 X 染色体，为了匹配 X 染色体的剂量输出，哺乳动物细胞采用的策略是，一个基因产生一种不编码任何蛋白质的 RNA，只是一种非编码 RNA。那种 RNA 缠绕在雌性的一条 X 染色体上，并关闭该染色体的大部分基因表达，将其推到细胞核的一个角落，这被称为巴氏小体。它再也没有被听说过。所以我完全同意你的观点，一个基因可以做很多事情。但在生物学中，你也有冗余，你有补偿，你有各种各样的机制，在这些机制中，敲低一个基因并不总是足以看到表型。如果四个冗余的基因只做同样的事情呢，对吧？只拿掉那个 RNA 是不够的。所以我们首先从一次一种细胞类型、功能丧失、单基因扰动开始，并且只将 RNA 表达作为输出，我们正在沿着所有这些轴线扩展平台。这就是我们今天为了构建用于训练模型的平台架构所做的工作。我们现在开始在该平台的三个轴线上发展，超越仅仅单独的转录组学到多模态数据，超越仅仅单独的单基因扰动到研究通路的激活和失活，开启和关闭整个级联链式反应。而且还要超越仅仅单独的细胞系、单培养物，进入越来越多复杂的、具有转化相关性的系统，进入原代细胞、进入类器官，甚至进行直接的体内扰动筛选。所以我们相信通过所有的这些扩展，那些数据对于训练模型来说将会更加令人兴奋。

<details>
<summary>Original English</summary>

**Xi Chu**: Yeah, that's a great question. And Bo and I have thought about this a lot. Actually, it's interesting that you brought up reproductive biology in, I studied a lot of in female cells, the compensation, the dosage compensation mechanisms. There are female cells have two X chromosomes, male cells have one X chromosome to match the dosage output from the X chromosomes strategy that the mammalian cells employ is one gene that produce a RNA that does not encode for any protein, just a non-coding RNA. That RNA wraps around one of the female X and turns down most of the gene expression from that chromosome, shove it away in the corner of the nucleus and it's called the bar body. It is never heard from again. And so I absolutely agree with you, one gene can do a lot. But in biology, you also have redundancy, you have compensation, you have all kinds of mechanisms where knocking down one gene is not sufficient to always see a phenotype. What if four genes redone only do the same thing, right? Taking out the RNA is not going to be sufficient. So where we started with one cell type at a time, loss of function, single gene perturbation, and look at only RNA expression as the output, we're expanding the platform along all of those axes. So that's what we do today to build a scaffold of the data for training models like Excel. We are now beginning to grow in all three axes of the platform, going beyond transcriptomics alone to like a multimodal data, going beyond just one gene perturbation alone to look at also pathway activation and inactivation, turning on and off entire cascade of chain reactions. And also going beyond just cell lines, monocultures into more and more complex translationally relevant systems into primary cells, into organoids, doing even direct in vivo perturbation swings. So we believe with all of that expansion, that data will be all the more exciting to train models on.

</details>

**Bo Wang**: 这也是为什么我们将蛋白质-蛋白质相互作用网络作为先验知识纳入我们的模型中。而且虽然现在的模型是在单基因扰动上训练的，但是一旦模型被训练好，你实际上可以在纯计算环境中预测组合扰动，对吧？所以在某种意义上，我们可以同时扰动两个基因的 tokens，看看反应是什么。当然，没有训练实际的组合扰动数据集，准确度可能达不到，但至少有了这种模型的存在，我们可以开始使用计算机模拟扰动来生成假设。

<details>
<summary>Original English</summary>

**Bo Wang**: This is also why we incorporate PPI networks as the prior knowledge into our model. And although the model right now are trained on single gene perturbations, but once the model is trained, you can actually predict combinatorial perturbations just on the model in only silico, right? So in the sense that we can just perturb the tokens of two genes at the same time and see what's the response. Certainly without training the actual combinatorial perturbation data sense, the accuracy may not be there, but at least with the existence of such models, we can start to generate hypotheses using in silico perturbations.

</details>

### Academia and Industry in the Age of AI

**RJ**: 您认为在人工智能时代，科学家的角色发生了怎样的变化？因为您可能，因为您没有使用，您的重点不是语言模型本身以及智能体科学之类的事情，那么您可能会有不同，稍微不同的看法。您正在构建这些非常特定的模型，但依然有一个问题，您和您的学生是如何能够保持如此高的节奏的？我怀疑这可能部分与 AI 生成的成果有关，但同时，您又是如何看待科学家，也就是学者的角色变化的？

<details>
<summary>Original English</summary>

**RJ**: How do you see the role of the scientists changing in the age of AI? And you may, because you're not using, your focus is not language models themselves and agentic science and things like that, then you may have a different, slightly different take. You're building these very specific models, but still one, how are you and your students able to maintain such a high pace? And I suspect it may have something to do with generated by AI partly, but also, and how do you see the role of the scientists, the academic changing?

</details>

**Bo Wang**: 是的，这是一个很好的问题。所以我官方的时间分配是 80% 在公司，20% 在我的大学附属机构，但事实证明，现实是 100% 在公司，100% 在大学。

<details>
<summary>Original English</summary>

**Bo Wang**: Yeah, that's a great question. So my official split of time is 80% on the era, 20% on my university affiliations, but turns out the reality is 100% on the era, 100% on the university.

</details>

**Brandon**: 你发明了一台时间机器，这就是答案。

<details>
<summary>Original English</summary>

**Brandon**: You invented a time machine, that's the answer.

</details>

**Bo Wang**: 所以我努力跟上的方法是我们，我的实验室使用很多智能体 AI 试图每天监控所有的 AI 论文。在每周我们举行的实验室会议上，我们试图讨论人工智能在生物学、人工智能在医疗保健等领域的不同话题。而且，说句实话，即使作为一名教授，我也觉得要赶上是非常困难的。人工智能的步伐实在快得难以置信。以至于有时候我会感到焦虑，醒来说：“我的天哪，这么多人发表了论文，我们现有在这个方向的工作该怎么办？”突然间，你可以想象学生们可能会面临十倍的焦虑。所以有时候我试图鼓励学生真正去使用不同的工具，努力保持专注，并找到我们可以成为专家的利基领域。但在生成式 AI，现在是智能体 AI 的时代，我发现人们，至少是学者，做科学的方式现在非常不同。总体而言，大多数学术界的教授或学生开始在资金、发表速度方面非常挣扎。这就是为什么你可以看到许多重大突破来自工业界，例如 AlphaFold。所以在这个智能体 AI 的时代，学者如何生存甚至繁荣，无疑是每个人都在思考的事情。我们看到许多教职员工离开大学加入工业界，原因仅仅是资源。如果你在做关于 AI 的研究，你在学校有足够的 GPU 吗？当一个学生加入一个教授的实验室时，这应该是你要问的第一个问题。他们经常问的第一个问题是：“你们有多少个 GPU？”所以突然间，从这个意义上说，工业界在学术实验室面前有巨大的优势。但我认为学术实验室的优势真正是在于创新的步伐，而且这个特定的学术实验室可以在利基领域成为极具专长的专家。因此，有时拥有思考的自由也让你更容易创新那些也许工业界的人根本没有想到的想法。总体而言，我认为整个领域需要更多的创新才能赶上，希望在不同工具的帮助下，并且希望政府开始对学术界进行更多投资，因为我仍然深信学术界是整个领域创新的主要来源，特别是当涉及到生物技术时。所以希望我们能看到更多对学术界的投资，这样我们就能维持下去。

<details>
<summary>Original English</summary>

**Bo Wang**: So the way I try to keep up is something we, my lab use lots of agentic AI trying to monitor all the AI papers every day. And which every week we have lab meetings, we're trying to discuss different topics in AI for biology, AI for healthcare, et cetera. And it's, to be very frank, even as a professor, I find it's extremely hard to catch up. The pace of AI is just so incredibly fast. And to the point that sometimes I feel anxiety, waking up says, "Oh my God, so many people published and what happened to our existing on-purpose work." And suddenly, you can imagine students probably face 10X anxiety. So sometimes I try to encourage students to really kind of using different tools, trying to stay focused, and find the niche areas that we become experts on. But with the era of generative AI, now agentic AI, I find the way people, at least academics, does science are extremely different now. Overall, most of professors or students in academics start to be very struggling in terms of fundings, in terms of the pace of publications. And that's why you can see lots of major breakthroughs come from industry, like Alpha-Fold, for example. So how academics survive or even thrive at such era of agentic AI is certainly something everybody is thinking about. We see lots of faculties left university and join industry simply for the reasons of resources. If you are doing research on AI, do you have enough GPUs at your school? It's the first question you should ask when a student joined a professor's lab. The first question they often ask is, "How many GPUs do you have?" So suddenly, in that sense, industry has a major advantage over academic labs. But I think what academics labs have advantages on is really the pace of innovations and also the niche areas of this specific academic lab can be extremely expert on. So also having the freedom of thinking sometimes also makes you easier to innovate on ideas that maybe industry people didn't even think about. Overall, I think the whole field needs to be a lot more innovative to catch up and hopefully with the help of different tools and hopefully the government starts to invest more into academia because I still deeply believe that academic is the main source of innovation for the whole field, and particularly when it comes to biotech. So hopefully we see more investment into academia so that we stay afloat.

</details>

**RJ**: 我同意你的观点，但为什么呢？为什么资金应该仅仅流向工业界？为什么政府要把资金投入学术界？

<details>
<summary>Original English</summary>

**RJ**: I agree with you, but why? Why should the money just go to industry? Why should the government put any money into academia?

</details>

**Bo Wang**: 我仍然相信学术自由的力量。这其实也是我们最初的动机，大学教授之所以存在不仅仅是因为我们教学，在大学里同时进行教学和研究也是有好处的，在这个意义上，当你教授一门学科时，你实际上必须成为专家，这迫使你不断更新你的知识库，然后找到容易的方法将你的知识传达给学生。而且通过这样做，你实际上开始在不同的想法上进行创新。例如，我自己，我在多伦多大学教授一门关于深度学习和神经网络的大课。这是一门巨大的课，每年有 600 名学生。通过教授这门课，它迫使我每年更新幻灯片和讲座，而且我自己阅读大量材料，试图更新自己，以便找到方法向学生传达一些知识。所以每当有迁移时，我就是这样不断更新自己的。我清楚地记得，我们有了 GPT-2 时，我们更新了讲座，然后是不同的语言模型，如何在训练中使用多线程 GPU 通信，大规模神经网络等等。所以我强迫自己不断更新模型。通过与不同的学生交谈，我们确实产生了很多新颖的想法，将尖端的 AI 模型应用到生物学或医疗保健中非常具体的利基领域。也许这是加拿大这种学术体系所独有的。作为学术界的一名教授，我们也可以访问许多医疗保健数据集，这些数据集对于工业界来说由于许多法律原因或监管原因很难访问。这就是为什么你看到我们通过加拿大的学术医院发表的一些论文，在这些论文中我们为超声波图像开发了一些最先进的基础模型。所以这就是我的意思，有一定程度的学术思考自由，确实推动了很多创新。而且我仍然相信，也许这是偏见，但我自己仍然相信拥有一定程度的学术思考自由会导致许多在工业界中不可想象的创新。

<details>
<summary>Original English</summary>

**Bo Wang**: I still believe the power of academic freedom. This is actually the original motivation we have, the existence of academic professors who are the only we teach, and there's also benefits of teaching and research at the same time in the sense that when you teach a subject, you actually have to become the experts and that force you to keep updating your knowledge base and then find easy ways to convey your knowledge to students. And by doing that, you actually start to innovate on different ideas. And myself, for example, I teach a big class at the University of Toronto about deep learning and neural networks. It's a gigantic class with 600 students every year. And by teaching that, it forces me to update the slides, lectures every year, and myself reading lots of materials, trying to update myself so that I can find ways to convey some of the knowledge to students. So that's how I keep updating myself whenever there's transfer. I remember vividly we have GPT-2, we updated the lectures, and then different language models, how the multi-thread GPU communication is used in training, largest scale neural networks, et cetera. So I force myself just update the models. And by talking to different students, we really generate lots of novel ideas to apply the cutting-edge AI models to very specific niche areas in biology or in healthcare. Maybe it's unique to Canadian academic system. By being a professor in academic, we also have access to lots of healthcare data sets, which are very hard for industry to access due to many illegal reasons or regulatory reasons. And that's why you see some of the papers we published through academic hospitals in Canada, where we developed some of the state of arts foundation model for ultrasound images. So that's what I mean that there's certain level of freedom of academic thinking that really drives lots of innovations. And I still believe, maybe it's biased, but myself still believe that having certain level of freedom of academic thinking will lead to lots of kind of innovations that is unthinkable in industries.

</details>

**Xi Chu**: 我 100% 同意 Bo 的观点。所以仅仅想想我们所做的实验室工作流程，其中很多也是建立在同样首先由学术界首创的创新基础上的。当然，CRISPR 是在学术界发现的。将 CRISPR 应用于哺乳动物高通量筛选，也是首先在学术界展示的。单细胞 RNA 测序（scRNA-seq），这种液滴包裹的 scRNA-seq 首先是在学术界展示的。然后不同的公司尝试

<details>
<summary>Original English</summary>

**Xi Chu**: I 100% agree with Bo there. So just thinking about the lab workflow that we do, a lot of these are building upon innovations that were first pioneered in academia as well. CRISPR, of course, was discovered in academia. CRISPR applied to mammalian high-throughput screening, also demonstrating academia first. scRNA-seq, this kind of drop-up encapsulated scRNA-seq first demonstrated in academia. Then different companies tried

</details>

<!-- chunk 8/9 -->

### 学术界与工业界的协同创新

**Xi Chu**: 最初将所有这些结合起来进行 Perturb-seq 也是在学术界首创的，对吧？CRISPR 实验室、Jonathan Weissman 的实验室、Aviv Regev 的实验室，很多都是学术界的先驱。然后我认为，特别是在实验室方面，这些创新需要很长时间，而且发现过程可能是非常偶然的，对吧？因此，也许不适合纯工业界去承担。但是，一旦它们展现出早期的潜力，将其扩大规模并使其更加稳健，并生成不仅海量而且高质量的数据（特别是针对 AI 规模的数据），我认为这是工业界可以做得非常好的事情。无论是从思维方式，还是我们可以提供的资源支持来看，这有时是学术界实验室很难企及的。

<details>
<summary>Original English</summary>

**Xi Chu**: Putting all of these together to do Perturb-seq at first, also pioneered in academia, right? CRISPR lab Jonathan Weissman's lab, Aviv Regev's lab, many of the pioneers in academia. And then I think these, especially on the lab side, these innovations take so long, and the discovery process can be so accidental, right? That it's perhaps not ideal for a pure industry to take on. But once they show early promise, scaling them and robustifying them, and generating data that's not only massive but high quality, especially for AI scale, I think that's something that can be very well done in industry, both the mindset, as well as the kind of the resources that we can support. That sometimes can be hard for academia labs to match.

</details>

**Brandon**: Xaira 在发布数据集和模型方面非常慷慨。你们似乎非常致力于开放科学。考虑到您刚才谈到的一些内容，以及关于什么是针对虚拟细胞或理解人类生物学的最佳、最重要数据策略的讨论，您认为学术界接下来应该走向何方，现在以及未来？既然 Xaira 现在的预算可能相当于几十甚至几百个生物实验室，那么您认为如果您是一名学者、一名教授，特别是在湿实验室里，您希望关注什么？

<details>
<summary>Original English</summary>

**Brandon**: Xaira has been very generous with releasing your data sets and your models. You've been, seem to be very committed to open science. Given some of the things you were just talking about, and this discussion about what is the best, most important data strategies for virtual cells, or understanding human biology, where do you think academia should go next, now and next? Since Xaira has probably a budget comparable to probably dozens or hundreds of bio labs right now, what do you think that if you are an academic, a professor, especially in a wet lab, what would you want to be focusing on?

</details>

**Bo Wang**: 首先，我自己是开放科学的坚定信徒。这就是为什么我们在这里谈论的所有模型都是开源的。你可以从我实验室的 GitHub 上找到所有的数据权重。它非常全面。是的，谢谢。我相信开放科学的原因是，正如您所说，大多数时候在学术界实验室，我们产生一个想法并建立它的原型。它不可扩展，甚至不是一个好产品，而工业界可以接手将其规模化。这也是为什么 SDGPD 很快成为制药公司中最广泛使用的单细胞基础模型之一的原因。这对我们来说非常鼓舞人心。这也是为什么 Xaira 也开始开源一些数据集和一些模型。部分原因是，我们认为虚拟细胞是一个非常早期的领域，因为太早期了，保留某些数据集或模型并没有什么帮助。一个更好的双赢局面是，这个领域的每个人都开始共同贡献模型、交流想法，这样这个领域就能以更快的速度向前发展。因为 PDB 中开源数据集的可用性，我们在蛋白质领域看到了成功的例子。因此，我们有了诸如 AlphaFold、RosettaFold 这样的模型。而且 AlphaFold 也是开源的。因此，我们可以快速迭代不同的模型。这就是为什么你会看到蛋白质领域的蓬勃发展。我们想在虚拟细胞领域做同样的事情。让我们把所有的数据集放在一起。让我们有相同的标准协议来生成高质量的数据集。让我们把所有的资源集中起来，生成下一代虚拟细胞模型。当谈到学术实验室时，你可以评论一下湿实验室的学者如何生存。从 Joy Lab 的角度来看，我确实鼓励大学里所有的 Joy Lab AI 研究人员开始与工业界合作，这样他们就可以获得更多资源来开发自己的想法。在生成式 AI (HNT AI) 时代，现在每个人都会写代码。更重要的是对你的项目有正确的品味，这样你就不会毫无目的地消耗 token。我们希望更多的学术界学生、学术界教授具有研究品味，从而让我们能够正确地利用生成式 AI。

<details>
<summary>Original English</summary>

**Bo Wang**: First of all, myself is a deep believer of open science. That's why all the models we talk about here, that are open source. You can find all the data weights from my lab GitHub. It's very thorough. Yes, thank you. The reason I believe open science is that, as you mentioned, most of the time, academic lab, we started an idea and we prototype it. It's not scalable, it's not even a good product, and industry can take it to scale things up. This is also why SDGPD quickly becomes one of the most widely used single cell foundation model in pharma companies. That's very encouraging to us. This is why Xaira also started to open source some of the data sets, some of the models. Part of the reason is that we believe virtual cell is such an early field, and it doesn't help to withhold certain data sets or certain models because it's so early. A better win-win situation is everybody gets to in this field start to contribute models together to exchange ideas so that this field can move forward in a much faster pace. We see successful examples in protein space because of the availability of open source data sets in PDBs. Therefore, we have models such as alpha fold, rosetta fold. Again, alpha fold is also open source. Therefore, we can quickly iterate different models. That's why you see a booming situation in protein space. We want to do the same thing for virtual cells. Let's put all the data sets together. Let's have the same standard protocols to generate high-quality data sets. Let's put all the resources together to generate next generation of virtual cell models. When it comes to academic labs, then you can comment on what lab, how what lab academics can survive. From Joy Lab's perspective, I do encourage all the Joy Lab AI researchers in universities start to collaborate with industries so that they can get more resources to develop their own ideas. With the era of HNT AI, now everybody can code. It's more important to have a right taste about your project so that you don't just burn tokens without purpose. We want more academic students, academic professors to have a taste of research so that we make the right utility of HNT AIs.

</details>

**Brandon**: 作为一名教授，你的工作显然是具备这种品味，但作为一名学生，在一个很大一部分科学思维过程基本上可以外包给大语言模型 (LLM) 或其他工具的世界里，你该如何培养这种品味？你知道，现在已经不再是那个你被迫绞尽脑汁、被迫通过艰难的方式培养品味的世界了。

<details>
<summary>Original English</summary>

**Brandon**: As a professor, your job is to have taste, obviously, but as a student, how do you develop taste as in a world where so much of the thinking scientific process could be essentially outsourced to an LOM or a, you know, some there's not a world where you're forced to bang your head against something and you're forced to take a taste by the hard way.

</details>

**Bo Wang**: 这就是为什么我们需要学术训练，你进入一个你一无所知的领域，并希望在你毕业后成为世界上这个特定主题的专家，对吧？这就是为什么你必须经历不同的项目，与你的同龄人交流，与你的教授交流，以初步了解什么是好的品味。但更重要的是，我总是教导学生，学习某件事最好的方法就是去编程实现它。通过编程，你能某种程度上了解论文中所有数学方程式背后隐藏的细节，而这些细节你通常会忽略。但在智能体 AI 时代，情况略有不同，以前我们花大量时间写代码，只花很少的时间调试。但现在我们让智能体完成大部分编码工作，但我们把大部分时间花在调试上，这对我来说显然非常有趣。我们在实验室里和学生们进行了很多讨论，探讨发现 AI 生成的 bug 的最佳方法是什么。那么，你如何发现 AI 特别擅长的地方？同时，你又如何发现 AI 仍然受限的地方？你也需要大量的试错。最后，你仍然需要使用真实世界的证据来某种程度上验证你的模型，对吧？所以，这就是为什么与湿实验室合作、与临床团队合作来验证你的模型，并为你所谓的品味提供反馈信号，正如我们所讨论的那样，这肯定是一个非常重要的训练项目。

<details>
<summary>Original English</summary>

**Bo Wang**: This is why we need academic training where you get into a field you know nothing about and hopefully after you graduate become the expert about this particular topic in the world, right? This is why you have to go through different programs to talk to your peers, talk to your professors to get an idea about what's a good taste to begin with. But more importantly, I always teach students that the best way to learn something is to just program it. By programming, you kind of know what's the details hidden in all the mathematical equations in the paper, which often you omit. But in the era of agentic AI, things are slightly different in the sense that we used to spend lots of time coding, a little bit of time just debugging. But now we let the agent do most of the coding, but we spend most of the time debugging, which seems to be definitely interesting to me. And we had lots of discussion with the students in the lab what's the best way to spot bugs by by AIs. So how do you find places where AI is particularly good at? Also, how do you find places AI are still limited at? You need lots of China era as well. And in the end, you still need to kind of validate your model using real world evidence, right? So that's why collaboration with wet labs, collaboration with clinical teams to validate your model, provide feedback signals to your taste, as we discussed, is certainly a very important training program.

</details>

**Xi Chu**: 在湿实验室方面，学术界要扮演极其重要的角色。我认为我们将进入一个共生创新和思想交叉授粉的领域。就像在 AI 领域一样，我认为学术界仍然不断涌现出伟大的想法。但现在，工业界也越来越多地在架构以及所有这些方面贡献新的想法。在湿实验室方面，工业界显然似乎能够很好地扩大这类数据生成的规模。但是生物学远不止是基于细胞的 Perturb-seq。除了 RNA-seq 之外，我们还想测量许多其他分析物，对吧？蛋白质、代谢物、脂质、蛋白质-蛋白质相互作用。我们如何大规模地做到这一点？除了单个细胞之外，我们还希望能测量细胞与细胞之间的相互作用、空间信息、处于原生环境中的细胞，甚至整个动物级别的体内微扰。同样，伴随着学术界涌现出的大量伟大创新，我们如何大规模地做到这一点？实际上，上周就有一篇很棒的论文。那么我们如何将所有这些联系起来呢？我认为我们要完全破解所有生物学的数据，还有很多年的工作要做。为此，我认为我们需要扩大工业化的规模和来自工业界的创新。我们也需要来自学术界的创新。我认为我们将共同把这个领域推向新的高度。

<details>
<summary>Original English</summary>

**Xi Chu**: On the wet lab side, academic has extremely important roles to play. I think we'll enter a field of symbiotic innovation and cross-pollination of ideas. Just like in AI field, I think we have great ideas coming out of academia still all the time. But industry now increasingly are contributing new ideas on architecture, on all of that as well. In the wet lab side, certainly industry seems to be able to scale these type of data generation quite well. But biology is so much more than just cell-based perturb-seq. Beyond RNA-seq, we would like to measure many other analytes, right? Proteins, metabolites, lipids, protein-protein interactions. How do we do that at scale? Beyond individual cells, we would like to be able to measure cell-cell interaction, spatial, cell in their native context, or even whole animal level in vivo perturbations. Again, how do we do that at scale with lots of great innovation coming out of academia? Actually, just one great paper last week. And so how do we connect all of these together? I think we have many years of work ahead of us to fully crack data for all biology. And that I think we need to scale the industrialization, the innovation from industry. We also need that from academia. I think we'll together move this field to the next level.

</details>

### 突破生物学数据瓶颈的终极愿望

**RJ**: 有一个我们一直想问每个人的问题是，在你们的领域，或许你可以称之为 AI 和高通量实验领域，或者随便你怎么定义。如果你能挥舞你的魔杖，为你消除一个瓶颈，或者解决一个关键问题，那会是什么？蛋白质。

<details>
<summary>Original English</summary>

**RJ**: One question that we've been trying to ask everyone is in your field, which you could say maybe is AI and sort of high throughput experimentation, or however you wanted to find out. If you could wave your magic wand and have a bottleneck removed for you, or a key problem solved, what would that be? Protein.

</details>

**Xi Chu**: 如果有一种方法可以进行蛋白质测序或高通量蛋白质测量，达到我们进行基因组学研究的相同规模，那将是非常惊人的。我是在基因组学领域受训的，但如果我能做到这一点，我会毫不犹豫地采用这项技术。RNA 很神奇。它预示了哪些蛋白质将被制造出来。但是，大体上蛋白质才是细胞内的功能单元。不仅它们的丰度很重要，它们的翻译后修饰很重要，它们在细胞中的定位也很重要。如果你能量化所有这些东西——它们的构象状态、修饰、丰度、定位，并且是在大规模、单细胞甚至空间水平上做到这一点，我认为这样的数据集对于训练下一代初始模型将会极其有用。我知道在那个方向上有很多创新。难道我们不能见证它走向成熟吗？

<details>
<summary>Original English</summary>

**Xi Chu**: If there is a way to do protein sequencing or high throughput protein measurement, the same scale that we can do genomics, that would be amazing. I'm training genomics field, but if I can do that, I would incorporate that technology in a heart beat. RNA is amazing. It foreshadows which proteins are going to get made. But protein by and large are the functional units in a cell. Not only does their abundance matter, their post-translational modification matter, their localization in a cell matter. If you can measure all of those things, their conformational states, their modifications, their abundances, their localizations at scale, single cell, or even spatially, I think such data sets would be incredibly useful to train the next generation of initial models. I know there's a lot of innovations in that direction. Can't we just see that become a come of age?

</details>

**Bo Wang**: 我的愿望是希望能看到测序技术取得突破，不仅仅是降低成本，而是能够对同一批细胞在不同时间点进行测序的技术。我认为这正是目前非常欠缺的，因为现在，为了对细胞进行测序，你必须杀死它。我们能不能拥有一种技术，可以在不同时间点测量同一批细胞的状态？我认为这将为数据集带来一个截然不同的维度，从而使我们能够开始测量细胞的时间动态。到目前为止，我们测量的、我们建模的一切都是极其静态的。如果我们能有一种技术，去测量同一批细胞在不同时间点的不同响应，这将为细胞动态建模释放巨大的机会。对我来说，那才是真正的虚拟细胞。

<details>
<summary>Original English</summary>

**Bo Wang**: My hope is I hope to see a breakthrough in sequencing technology, not just the reduced cost, but sequencing technology that can sequence the same cells at different time points. I think this is much lacking right now because you have, in order to sequence the cell, you have to kill the cell. Can we have a technology that can measure the cell states at different time points for the same set of cells? I think that will bring a very different dimension to the data set so that we can start to measure the temporal dynamics of cells. So far, everything we measure, everything we model is extremely static. Can we have a technology that measures different cell response at different time points for the same set of cells will unlock massive opportunity to model the dynamics of cells? To me, that is a real virtual cell.

</details>

**Brandon**: 这真的是个非常有趣的想法。我以前绝对想不到这点。哇。哪怕只是部分少量的基因片段，或者只是一小部分转录本的 3' 端区域，你觉得可以接受吗？

<details>
<summary>Original English</summary>

**Brandon**: That's a really interesting idea. I never would have thought about that. Wow. Would you be okay with even just partial small snippets of genes or maybe three prime regions of a small number of transcripts?

</details>

**Bo Wang**: 是的，我们可以先从一小部分基因组合开始，对吧？但最终，既然我们在谈论“魔法”，最终如果我们能有一个系统观察细胞在不同时间点如何演变，并且我们有足够的数据来真正对这种发育过程进行建模，我认为那将是一个真正的虚拟细胞模型。

<details>
<summary>Original English</summary>

**Bo Wang**: Yeah, we can start with a small set of gene panels to begin with, right? But eventually, since we are talking about the magic, eventually, if we can have a system that observes how cells evolve at different time points and we have enough data to actually model such development, I think that would be a real virtual cell model.

</details>

**Xi Chu**: 现在有一些小型的尝试，也是早期的尝试，例如只是吸出细胞的一部分，几乎像是从细胞中进行活检，来测量一小部分细胞质。所以这可能类似于你谈到的那个想法。这个实验室也有公开的工作，让细胞分泌小囊泡，然后他们从细胞培养基中收集这些囊泡，以纵向测量细胞产生了什么。但目前还没有一种技术可以让你在测量整个细胞转录组的同时还能保留这个细胞。鱼和熊掌不可兼得。

<details>
<summary>Original English</summary>

**Xi Chu**: There are small attempts, also earlier attempts, in just, for example, sucking out portions of the cells, taking almost biopsies from the cell to do a fraction of the cytoplasm measurements. So that might be similar to the idea you talked about. There's also work from a public in this lab to have the cells secrete little vesicles and they harvest that in the cell culture media to measure what the cells are producing longitudinally. But there hasn't been technology that can let you measure the entire cell's transcriptome while still keeping the cell. You can't have the cake and eat it.

</details>

**Brandon**: 酷。是的，感谢您抽出时间与我们交流。这太棒了。我们学到了很多。这是一个……

<details>
<summary>Original English</summary>

**Brandon**: Cool. Yeah, thank you for taking the time to chat with us. It's been great. We've learned a lot. It was a

</details>

<!-- chunk 9/9 -->

### 结语

**Brandon**: 有很多非常有趣的讨论。我特别感谢你们对开放科学以及所有酷炫模型和数据的承诺。你们还有什么最后的想法，或者有什么想让观众知道的吗？

<details>
<summary>Original English</summary>

**Brandon**: lot of really interesting discussions. I especially really appreciate your commitment to open science and all of the cool models and data, if you're at least. Is there any last thoughts you have or anything you'd like the audience to know? Follow up on that.

</details>

**Bo Wang**: 总的来说，我认为虚拟细胞是一个非常新且发展迅速的领域。我们希望能有越来越多的人加入我们，我们的 Excel 论文已经发表，我们期待收到你们的评论和反馈。另外，我们正在招聘。

<details>
<summary>Original English</summary>

**Bo Wang**: Overall, I think virtual cell is such a new and fast moving field. We hope to have more and more people join us and our Excel paper is out and we look forward to receiving your comments and feedbacks. And also we're hiring.

</details>

**Xi Chu**: 是的，我们一直在寻找优秀的工程师、技术人员、生物学家、药物研发人员、AI 科学家和计算科学家。所以请访问 xaira.com，查看开放的职位。我们很乐意与您交流。

<details>
<summary>Original English</summary>

**Xi Chu**: Yeah, we are always looking for talented engineers, technologists, biologists, drug hunters, AI scientists, computational scientists. So look on xaira.com. Look for the open roles. We'll be happy to chat with you.

</details>

**RJ**: 谢谢。非常感谢。太棒了。

<details>
<summary>Original English</summary>

**RJ**: Thank you. Thank you very much. Great.

</details>

**Xi Chu**: 谢谢。

<details>
<summary>Original English</summary>

**Xi Chu**: Thank you.

</details>