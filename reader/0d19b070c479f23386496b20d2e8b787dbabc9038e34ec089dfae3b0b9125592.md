---
author: AI Engineer
date: '2026-07-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZyIoTOAbRfs
speaker: AI Engineer
tags:
  - data-market
  - reinforcement-learning
  - benchmark-evaluation
  - model-decoupling
title: 大模型暗战：解密AI数据市场流变、基准幻觉与企业自主化
summary: 本文基于独立研究员Sean Cai在数据市场会议上的演讲，深入分析了AI数据供应链解耦、过程导向数据的核心价值，并提出了“验证者定律”三维评估框架。演讲揭示了行业基准测试失效的深层原因，预测了企业级小模型路由及“安提基特拉机械”等新型基础设施的崛起趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - Scale AI
  - Surge AI
  - Remarque
products_models:
  - GPT-4
  - GPT-5.5
  - Opus 4.7
  - Opus 4.8
  - GLM 5.2
media_books: []
status: evergreen
---
### 数据供应链解耦：从规模扩张转向专业化分工

在白领工作革命的浪潮中，**数据之于智能时代**，正如煤炭与钢铁之于维多利亚时代的工业革命。我们必须认识到，数据市场的潜在市场规模（Total Addressable Market: 整个行业可实现的销售额上限）并非仅仅局限于某个单一的技术垂直领域，而是涵盖了**整个人类劳动力市场**。

随着行业的成熟，AI数据供应链正在经历从“垂直一体化”向“解耦与专业化分工”的根本性转变。在2019年前后，人们对**数据市场**（Data Markets: 交易与处理机器学习训练数据的产业生态）的印象，还停留在位于马尼拉等地的万人标注工厂里，成群的初级标注员对图像进行基础分类与打标。这种传统的粗放型数据标注虽然仍占据着数百亿美元的年市场规模，但已经是含金量最低的部分。如今，随着大模型基础能力的完善，真正稀缺且价格被严重低估的，是能够让模型从“泛化能力”跃升为“行业专家”的**高专业度数据**。

在这种需求驱动下，原本被 Scale AI、Surge AI 或 Remarque 等垂直整合巨头垄断的生态正被迅速瓦解。专业化的第三方供应商在人员招募、环境构建、奖励函数设计以及基准评估等各个细分环节上，全面击败了全能型的巨头。这种碎片化趋势并非过渡阶段，而是长期的结构性常态。由于**数据质量**无法随着**数据数量**呈线性规模化扩展，各大前沿实验室出于对单一供应商质量瓶颈的担忧，甚至强制推行多元化采购策略，同时对接20至30家细分供应商。这使得整个数据产业变成了一个繁荣的“手工作坊式”行当，也催生了专门将复杂商业场景翻译为评估指标的定制化系统——**安提基特拉机械**（Antikythera Mechanisms: 翻译复杂业务上下文并将其转化为强化学习反馈及评估指标的定制系统）。

段落之间必须包含逻辑衔接句：在理清了数据供应链的解耦趋势后，我们必须进一步深入探究这股专业化分工的核心支柱——数据类型与质地的根本差异。

<details>
<summary>Original English</summary>

Good to give this talk and just want to say right off the bat this is probably going to be a little different from what you've seen so far at AI conference. I'm here to not deliver an agenda on any company's behalf but just to expose a lot of alpha in data markets. But also just tell you what's really going on behind the scenes in a in a very murky landscape where nobody seems to know how Remarque handshake and a lot of these folks actually produce data.
So you know, quick reframe before we start when people hear data markets they picture scale around 2019. They picture these rooms of annotators in like Manila labeling images and that's that's real and it's maybe you know, 10 to 15 billion dollars a year per lab but it's kind of the least interesting part. The models work now what scares and badly priced is the sort of data that takes some from generalist competence into real expertise. We knew this since 2024 when Scale got acquired and we were spamming a lot of GPQA data sets.
So look, let me start with this framing. Data is to the white collar revolution what coal and iron basically is to the Victorian age and the information age right now. I have this piece called the TAM is in a vertical it's all of labor.
And so the supply chain is basically just doing what every sort of industrializing supply chain does it unbundles two years ago when vertically integrated giant like a Remarque or Surge or Scale AI if you if you guys are unfamiliar they're massive data companies. They had to do all of it but that was because that's the only way that unit economics worked in an immature market today.
That's increasingly not the case. Specialists outcompete the giants at a lot of steps sourcing the people, building environments, designing rewards, running evals. The fragmentation I would say, is pretty permanent. It's not transitional. And uh quality increasingly does not scale linearly with quantity, which leads to a sort of cottage industry in data land right now, where you have labs literally mandates uh vendor diversification on the scale of like 20 to 30 different vendors because they inherently distrust their ability to scale quality with quantity.
So, to orient you, you know, here's here's the sort of argument as it developed through this year. Um January, we saw a lot of industrialization and unbundling. You'll hear me come back to this mechanism I call the Antikythera mechanisms, which is this sort of bespoke systems that translate messy business context into Evals. Uh increasingly important in labs' hungry quest for real-world seed data to set at seed ends.

</details>

### 过程导向数据：区分真实工作流与人造样本

在数据类型上，行业内存在着**状态导向数据**（State-based Data: 记录最终静态结果的数据）与**过程导向数据**（Process-based Data: 记录决策路径和推理轨迹的动态数据）之间的本质分水岭。2023年大模型主要依赖于状态导向数据——例如企业ERP系统中的静态数据行或已归档的文件，这对于当时基于“预测下一个Token”的传统预训练模型已经足够。然而，真正能够使模型获得专家级能力的，是记录了专业人士从空白页面到完成最终工作成果的全套决策路径、工具调用与推理链条的**过程导向数据**。

在此基础上，我们可以进一步引入**第一类数据**（Type 1 Data: 真实业务流中无污染捕获的原始轨迹数据）与**第二类数据**（Type 2 Data: 专家在模拟环境中刻意制造的人造训练数据）的分类：
* **第二类数据（人造数据）**：是通过雇佣专家在脱离实际业务场景的孤立沙盒中，凭空“制造”出来的问答对或操作样本。当模型能力还处于“一年级水平”时，这类数据能像小学三年级老师一样，快速帮助模型建立起基础认知。
* **第一类数据（真实工作流）**：则是对真实世界中发生的工程提交、系统操作或设计调试进行无干扰捕获（如真实的 GitHub 提交记录或交互录屏）。它是模型从20%的入门水平走向80%甚至更高精度的唯一通道，因为其真实性源自真实业务的复杂摩擦与系统反馈。

目前，AI行业的一个公开秘密是，大部分数据服务商在销售昂贵的**人造数据**（Type 2），却将其包装为**真实工作流数据**（Type 1）。然而，随着模型能力的提升，传统的GPQA（大模型研究生水平评估基准）模式的数据采集在面对长逻辑链、难以验证的任务时已近失效。企业必须意识到，只有通过与正在运行的实体业务深度合作，才能获取源源不断的、具有长期资产增值价值的真实工作流数据，而不是去买那些已经死去的初创公司的静态代码库。

段落之间必须包含逻辑衔接句：在明确了真实工作流数据（Type 1）的决定性价值后，摆在研究者与开发者面前的难题在于，如何建立一套量化框架来评估和选择这些复杂的任务领域。

<details>
<summary>Original English</summary>

Um I also explored this concept called type one versus type two data, uh contrived versus non-contrived for the more researcher types in the audience, and why the GPQA cell playbook that works in 2024 for data acquisition kind of falls apart on long horizon unverifiable work. Um so, you know, going through all these topics, all of which are online, uh I'll also I'll actually just skip to the more interesting part, but I'm bringing this up just here in case any of the particular topics I talk about are are particularly interesting and you want to dive in more.
So, model improvement is a function of three inputs. We all sort of see this uh commonly expressed as dodge, compute, data, and talent. I put together this very uh like rudimentary sort of chart online in one of my pieces and a very rudimentary uh equation just to express the fact that, you know, if there's any sort of imbalance in this compute, data, and talent, then you start seeing uh a sort of inefficiency in producing uh what I call like generalized AI model performance, right?
But also, uh we we see a sort of inefficiency in in CapEx spend that it that is a sort of result of this equation right now. Um exponentially increasing CapEx spend, but sort of like um AI revenues are are sort of falling far behind. Uh data is sort of the underfunded leg here. It's the one that sort of turns a generalist model into a real expert. It's the one that's uh actually I believe quite lacking in this equation and thus because of the imbalance penalty parameter concepts that I'm expressing, um presents a whole opportunity.
But you know, going back to what I said at the start, what is data actually? So, most people picture state-based data, the rows in an ERP, which is like the final output or saved file. That's kind of the 2023 like next token prediction model um and it's mostly personal data wrapped in privacy law. What is actually available nowadays is process-based data, which is the trajectory, the reasoning trade trace, the sequence of decisions. Um so, it it's kind of what gets a professional to get from a blank page to a finished work output and sort of delineates how the work gets done.
Um so, on top of that sits a quality axis. This is the vocabulary. I'll use all talk. Um type type one data is a sort of pure capture of real workflows like GitHub commits or session replays with minimal reward shaping by non-experts and type two is contrived data, where you sort of hire experts, you sit them in an arbitrary setting, you have them manufacture examples. Type two, right place to start models when they were reading at a first grade level, I think anybody in the world could teach them as a third grade teacher. But type one is what gets you from 20 to 80% so to say cuz the real the realism is inherited from the work itself and the structural reason why it matters is the data is kind of the most appreciable asset there is. Um a data set is only available in so far as frontier data markets as the frontier moves. So, the only durable supply of it technically is a live business you partner with, not a dead startup's code bases like so many data companies out there are buying today. The dirty secret of the industry though is that everybody sells um type two and bills it as type one.

</details>

### 验证之盾：以可验证性预测大模型演进路线

要预测哪些大模型应用领域会率先成熟，其核心决策维度在于**任务的可验证性**。研究员 Jason Wei 曾提出知名的**验证者定律**（Verifier's Law: 训练模型完成某项任务的难度，与其结果可被验证的难易程度成正比）。为了更具实操性，我们可以将“可验证性”拆解为三个轴线：
1. **验证的不对称性**（Asymmetry of Verification: 将一项复杂任务分解为可逐项核对的子步骤的难度）。
2. **验证的确定性**（Veracity of Verification: 行业内对于“正确”的标准是否存在广泛共识）。
3. **验证的丰沛度**（Proliferation of Verification: 现实世界在日常运行中能够源源不断提供多少个已被验证的真实样本）。

以**软件工程（Coding）**为例，这之所以能成为第一个成熟的 AI 应用市场，正是因为它在 Web 2.0 时代就通过 GitHub 完美解决了这三个维度：**单元测试**提供了客观且易于拆解的正确性验证；程序员对代码是否可运行有高度的确定性共识；而数以亿计的 Commit 历史和 Commit Message 则提供了天然且免费的推理步骤。

相比之下，当下的热钱试图涌入的**生物制药、网络安全、金融分析、医疗和法律**等高价值领域，其评估指标通常面临确定性偏低、验证极为困难的问题，且极具价值的验证轨迹数据被深锁在企业的 Slack 或 Jira 沟通日志中，无法公开获取。通过这三个可验证性维度对不同职业的日常工作任务进行分类，我们可以清晰地画出应用市场的演进路线图：从代码生成，到搜索引擎，再到金融建模，进而迈向医疗法律，最终才触及高度依赖复杂验证的安全防护、生物科学发现以及主观性极强的“审美与品味”。

段落之间必须包含逻辑衔接句：在建立起这套验证体系后，我们便能够拨开市场上层层包裹的虚假基准迷雾，看清模型在真实场景下的短板与底细。

<details>
<summary>Original English</summary>

So, now let me talk about the central axis of how you can think about the sort of verification and deciding which application layer domains are are like maturing first and why. Uh you know, there's a reason why cloud science came out so far um you know, now in the future after models got good before a lot of other application layer advances.
So, Jason Wei is a researcher online whose blog is great. You should read him. He has this law. It's called Verifier's Law. The ease of training a model to do a task is proportional to how verifiable the task is. So, I break verifiability to three axes here. And once you have them, a huge amount of this market stops being mysterious.
First, asymmetry of verification. How hard is it to decompose a task into checkable steps? Veracity of verification. How much consensus is there about what correct even means? And then thirdly, proliferation of verification. How often does the real world sort of hand you fresh examples of verified work?
If you think about like coding as the first mature AI app layer market, that's really no accident because we were blessed to have something called GitHub from web 2.0 which solved all three of these at once. Unit tests, they sort of give you objective decomposable correctness. The community agrees on what working code means generally. And there are effectively infinite public examples with these commit messages as basically free reasoning traces. So, they score high, high, and high on these three axes.
Now, look where the money is trying to go now. Biology, security, taste, finance, health care, law. These sit pretty low on veracity, pretty low on verification, and the verification examples are sort of like locked all in these enterprise workflows. No web 2.0 system ever captured really or very sparingly few. Uh that's why, you know, probably maybe you've been approached by Mercari to buy your Slack logs or your Jira logs as of late if you work at an AI company. And that's the whole game, right? It's it's predictive. It's not just descriptive. Classify any professions like tasks on these three axes, and you can sort of tell which markets mature most. So, it no surprise that after code, we went to search, and after search, we went to finance, and after finance, we went to healthcare and law. And after healthcare and a law, well, I'd say cyber, biological, uh and scientific discovery. And maybe even taste, which is probably the most unverifiable out of all these.

</details>

### 基准测试幻觉与模型层的“解耦”趋势

由于真实世界的“验证之盾”难以攻克，整个评估和基准测试行业目前充斥着严重的“基准幻觉”与利益冲突。主流的基准构建模式形成了一种“带有商业图谋的**古德哈特定律**（Goodhart's Law: 当一个指标变成目标时，它就失去了作为好指标的意义）”：供应商雇佣非真正的领域专家，在模拟环境中通过 Chat 界面生成所谓的挑战性任务，并把模型在其中表现不佳的样本挑出来打包，贴上“北极星基准”的标签，转过头再兜售专门应对该基准的训练数据。这种在沙盒中闭门造车的评测，完全无法测试模型在长期依赖的真实业务链条中维持正确推理的能力。

这导致整个市场陷入了严重的**基准狂躁症**（Benchmark Psychosis: 盲目追逐单一、充满噪声的公开发布排行榜分数的偏执心理）。事实上，因为评估框架和基础设施的微小差异，主流基准测试具有极高的假阳性和假阴性率。

通过自建的私有金融任务基准（涵盖 ARR 瀑布账 reconciliation、LBO 估值备忘录和对冲基金多空配对交易等长逻辑非可验证任务，引入确定的验证器与大模型裁判的混合机制），我们可以窥见前沿实验室在后训练阶段的决策分歧：
* 在该长逻辑金融任务中，新的 **Opus 4.8** 因其过度工程化的自我反思设计，在多项指标上反而不如旧款的 **Opus 4.7**。
* **GPT-5.5** 与 **Opus 4.8** 的总分差距极小，但失分点完全相反——GPT 擅长算术但容易在方法论上走偏，而 Opus 方法论极其精准却在计算上翻车。

这再次证明，只看单一的基准数值就像是用瑞士军刀的螺丝刀配件去切干酪，然后宣布这把刀坏了一样荒谬。同时，数据采购活动也可以作为实验室未来产品动向的**上游代理风向标**：例如 Anthropic 在1月大手笔采购网络安全数据，在3、4月大量采购生物数据，紧接着2到3个月后，市场上就迎来了 Metis、Cybor 等安全工具以及 Claude 生物与生命科学的发布。

段落之间必须包含逻辑衔接句：在洞悉了这种基准测试背后的局限性后，企业用户的决策正发生根本性转向，从而催生了基础设施层的架构重组。

<details>
<summary>Original English</summary>

So, a verification is a sort of bottleneck. Um let me talk about why the industry sells a lot of snake oil here, and why most benchmarks you see are are sort of quietly fake. Um the dominant type two recipe is like let's hire domain experts. Um let's have them chat use chat to generate plausible tasks. Let's have them solve those tasks, and let's cherry-pick the ones where the model diverged, and let's package them as a hard North Star benchmark. And then, this is the perverse part, let's sell the data to hill climb that same benchmark. It's basically um and maybe some of you guys here in SF have heard this a little too much. It's Goodhart's law with a profit motive. Basically, the moment your measure like becomes a target, and then the target is set by people who aren't true domain experts, it stops sort of measuring anything real. And so, the whole market, uh I like to call it sits in a sort of fog of war.
Labs, vendors, and enterprises, they're all kind of guessing which of the data actually improves a model. Nobody can see this clearly. There's a structural tell. Contrived benchmarks, they only ever test a single isolated in-distribution question. They can't test whether a model sort of sustains like correct reasoning across a long dependent episode because these tests were all sort of meant to be solved in isolation.
Uh and may I spent a lot of time in this. Um increasingly, uh in a lot of Anthropic blog posts, but also like a lot of other researchers have noted that cross-harness differencing and cross-infrastructure differencing is the primary cause for a lot of benchmark divergences in performance. A lot of you are probably very familiar with like the frontier squeezes of the world and the deep squeezes of the world benchmarks. Um there are issues that all of these benchmarks have uh related to that specifically. In particular, just high false positive and false negative rates that are not immediately obvious when you look at the above head stats on the benchmark.
So, a single benchmark number under a single scaffold is like basically one sample from a distribution who's basically with nobody measured. And that's why there's so much what I call benchmark psychosis today. It's like a it's a pretty noisy sample.
So, um you know, really briefly on an example I took I I always have like I basically have an internal version of Val's AI and a lot of private benchmarks. Um so I I took three finance tasks from three real-world vendors. Um like an ARR waterfall reconciliation and LBO valuation memo and a sort of like long short pair trade for hedge fund uh trading. So, it's a long horizon non-verifiable finance tasks, relatively robust like deterministic verifiers paired with LLM as a judge uh applied correctly. So, um when you actually run these, I think you'll you'll notice very clearly Opus 4.8 is worse than 4.7 on a lot of these rubrics. Uh you'll you'll start noticing things if you actually do rubric analysis that the 4.7 to 4.8 sub over-engineered self-reflection. Um you'll you'll notice that uh GPT 5.5 and Opus 4.08 score within three points on the same task. They fell in like exactly opposite directions, whereas GPT nails the arithmetic um but Opus nails the the methodology but loses arithmetic, which is to say uh it's it's clear if you actually do very good agnostic benchmarking, um you you can tell where the post-training directions for a lot of these teams went. And subsequently, the it informs, I think, like a lot of the data that that comes for this. Um so, look, you know, going back to the start, a single benchmark number is a sample from a distribution nobody measured, and it's basically like taking a Swiss Army knife and using the screwdriver bit to cut cheese and like concluding the knife is broken. Um so um you know, the the receipts from the last slide, this this goes into an RL environment report that is sent to labs. Um but no single leaderboard number ever shows you this part of um you know, data, which some of the most sophisticated RL environment companies, some of which are actually here at this conference, um would would show you this.
So uh how do we read sort of which domain is next instead of chasing hype, and you can actually use this as a proxy data markets as an upstream indicator of what next application layer products that labs will come out with. In in January, uh Anthropic was spending a lot on cybersecurity data from new vendors. And in March and April, they were spending a lot on biological data um from from associated vendors, and what do you know happened like 2 to 3 months after? Well, Metis and Cybor and Claude bio / life sciences today.

</details>

### 企业自主智能与“安提基特拉机械”的崛起

从长期来看，AI应用层正在从底层大模型实验室（OpenAI、Anthropic等）中**解耦**出来。历史经验表明，任何底层基础设施技术的先驱者，在行业长期发展中都很难守住超过10%的市场份额——当年的铁路巨头收取着暴利的垄断租金，但在汽车普及后被迅速边缘化，甚至收归国有；AWS和谷歌虽然统领了云计算基础设施层，但也未曾真正吞噬应用层。大模型如今也并非像电力那样可以完全等同和通用，各家模型的效率和模态各异，并不存在坚固的用户锁定（Lock-in）。当企业开始追求拥有自主的、私有部署的智能系统，而非“租用”大厂模型的智力时，一个全新的**模型抽象层**正蓄势待发。

在这个重塑的过程中，成功的数据公司都已经悄然向**企业级服务**（Enterprise Pivot）转型，成为事实上的**新型模型实验室**（Neo-labs）。数据供应商的真正壁垒并不在于静态数据的拥有量，而是在于其是否能构建起对接真实世界业务的动态数据管道，以及在模型版本升级迭代时，自动对私有模型进行微调和重新后训练（Post-training）的能力。

在这一变革中，企业面临的核心技术真空需要由五大核心职能所构成的新型基础设施来填补：
1. **小模型路由与管理**：针对低延迟、低成本要求对小型专用模型进行高效路由；
2. **跨基座模型的RL数据管理**：在底层开源基座发生迁移时（例如更换新开源基座），无需重头开始，而是能够自动触发后训练机制。
3. **“安提基特拉机械”评测中介**：将复杂的现实业务逻辑，转化为模型可运行的、基于强化学习（RL）的动态反馈环境。

这正是演讲作者正在构建的新项目，通过提供“强化学习即服务”（RL as a Service）来帮助广大企业激活其庞大的私有数据资产，从而摆脱对单一基座大模型巨头的长期依赖。

段落之间必须包含逻辑衔接句：这一基础设施的构建，为未来的模型自主化时代奠定了最稳固的基石。

<details>
<summary>Original English</summary>

Uh So if you want to use this checklist I use, classify the professional's tasks into three axes, apply to long horizon bar, the the ones real labs use, um enforced step length heterogeneous tool calls that aren't interchangeable, state transitions that genuinely constrain future actions, mandatory failure recovery. Uh you'll notice a pretty mixed bag of of how long horizon is even defined from the vendor perspective in terms of specs.
Um and then three, you want to look at the raw data for five signals. So, sequential decisions against like one entity, an inferable action expert action per step, outcomes recorded by independent parties. Um but moreover, just economically available high-wage work. So, uh so subsequently, one one counterexample to keep you honest, like robotics, the modality is not settled. Um ego versus teleop versus UMI, but moreover, I I find just generally a huge degree of unsophistication within robotics data vendors today. A huge degree of unsophistication. Yeah.
Uh I don't know. Some of you guys are probably robotics researchers in a crowd. I don't know how many times like people have come up to you and they're like, "Oh, here's like 100,000 hours of like iPhone video from my friends in India. Do you want to buy this for ego data?"
>> [laughter]
>> Um so uh in a in in that sort of domain your vendors uh choices entangled with an unsolved research question. At the end of the day, you have to realize like all environment companies if they actually succeed, they're more so research accelerators. It's a boutique industry. If it's venture scalable, it's because the infrastructure they're building agnostically in house helps an enterprise application layer use case rather than assuming that data markets today will stay as they will forever. So, don't die in a modality hill, basically.
So, so one last exhibit just for my work. This is the map under everything I just described. Look, this share of the white-collar work is sort of on the vertical axis. This task horizon is on the horizontal. Short horizon is a is very addressable right now, but you think about this long tail on the right side, this deep dependent long horizon work. That's where the real economic value and data build out sort of both lives. And this threshold line that kind of kind of moves rightward every time somebody builds a real-world data pipeline.
Um now I want to talk a bit more about the model layer. Um it changes who needs to build what.
So, historical fact, no pioneer of an infrastructure technology has actually held more than 10% of the market in the long run. Um I'm not saying that this applies to Anthropic, but you know, I'm just those who forget history are condemned to repeat it. Railroads built company towns. They charged tyrannical rents. They got nationalized as soon as the automobile moved in. AWS and Google that consolidated the infrastructure layer and still never captured the application layer. And right now, OpenAI and Anthropic are carving out these fiefdoms, but like all these pressures from anti-distillation, export appeals, enterprise exclusivity. They're basically the equivalent of real-world brands in their road. Right? Like the automobile in some cases has already arrived like GLM 5.2 surpassing GPT on a lot of real-world rubrics. Um is is is pretty hard proof that a lot of app layer companies can decouple themselves from the model layer. And because models differ on efficiency and modality, they're not fungible like electricity. So, it's not it's not exactly leading to nationalization, but it's definitely not heading to durable lock-in either. And the whole question on what to build next hinges on whether a general enterprise can decouple models from foundation model labs.
Um But luckily, you know, we for a lot of data companies, this is actually where they're headed. I came here to give a talk on data markets. I'm here to tell you that that successful data companies nowadays are all pivoting to enterprise. I maybe shouldn't say this in a public setting, but I'm recording a handshake. People don't notice an incredibly large amount of their revenues are enterprise now. Enterprise in ways you wouldn't expect a data business to do. Once enterprises stop renting out labs intelligence and starts owning their own, you need an entire abstraction layer that doesn't exist yet. There's like five jobs serve and route small models targeted by costly latency and performance profiles. Um And uh I to manage your RL data sets instead of like um across base model migration. So, when you swap to a new open source base, you rerun post training automatically instead of starting over. Three, the Antikythera mechanisms that I talked about before. Um and in in the interest of time, happy to talk more about like emerging infrastructure needs afterwards if you want to.
So, let me bring it all together. I think data companies all realize that they have to be neo labs. Data businesses do not stay data businesses because the durable value sort of accrues to the services and app layer of actual work. So, two takeaways, you know, if you're a researcher, stop outsourcing your definition of realism to the same vendors you buy your eval's and tasks from. Um, that's kind of just letting the task test writer grade the task. And if you're a builder, your moat's not the data, it's the sort of pipeline into real-world work. Plus the infra to keep retraining on it as the models improve underneath you.
I'll close on this. Uh, I'm building um, I'm working on something new. This is the first public announcement of it. I'm building a ticket through mechanisms. I'm working with a lot of real-world companies to monetize their data assets, but moreover, help implement RL as a service with a lot of the enterprises in the world, mitigating a lot of the pitfalls of a lot of the companies I mentioned. If you guys want to talk about it afterwards, I'm on Twitter. I always write a lot on Twitter and Substack and um, I'm around afterwards, too. Thank you. >> [applause] [music]

</details>