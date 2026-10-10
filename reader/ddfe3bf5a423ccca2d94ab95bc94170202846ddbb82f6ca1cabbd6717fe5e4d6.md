---
author: AI Engineer
date: '2026-10-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xLxhT2ZI7UM
speaker: AI Engineer
tags:
  - reinforcement-learning
  - llm-as-a-judge
  - web-agent
  - evaluation-benchmark
  - universal-verifier
title: Universal Verifier：如何构建超越人类一致性的网页智能体评估系统
summary: BrowserBase与微软联合展示了针对Web Agent的全新通用验证器（Universal Verifier）。传统LLM裁判存在大量盲目自信与误判，该研究引入解耦细则、关键截图证据检索、过程分与结果分分离等原则，使评估虚报率归零，并在多步网页自动化与强化学习过滤中大幅提升模型质量。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Corby Rosset
companies_orgs:
  - BrowserBase
  - Microsoft
products_models:
  - Farfetch'd 7B
  - WebVoyager
  - OSWorld
  - GPT-4o
media_books: []
status: evergreen
---
### 开场致辞与背景介绍

**米格尔 (Miguel)**: 大家下午好，非常感谢各位莅临现场。希望大家在本次博览会上过得愉快。展会目前虽然已经接近尾声，但至少对我而言，这是一次极其精彩、收获颇丰的盛会。希望各位今天已经学到了很多知识，接下来我们希望能与大家分享更多前沿内容。

我是**米格尔 (Miguel)**，担任 **BrowserBase** 智能体平台的技术主管。可能还有一些朋友不太了解我们，BrowserBase 是一家专注于在网络端部署智能体（Agent）的基础设施公司。通过在云端集中托管和管理无头浏览器，以及提供运行大规模端到端智能体网页自动化所需的完整运行时环境，我们实际上为智能体打开了通往整个开放互联网的大门，而不仅仅局限于那些唾手可得的简单数据。

接下来把麦克风交给我的合作者，来自微软的 Corby。

<details>
<summary>Original English</summary>

**Miguel**: Good day everyone. Thank you for coming. I hope you have a great time at the exhibition. We're already at the finish line, but I know it was a great, just a great exhibition, at least for me. So I hope you learned a lot, and we can teach you a little more.

So, I'm Miguel. I am the technical lead for our agent platform at BrowserBase. For those who don't know, BrowserBase is an infrastructure company for deploying agents on the web. It effectively opens up the entire internet, not just what is readily available, by managing browsers in the cloud and the entire runtime environment needed for scalable agent-based web automation.

</details>

**科比 (Corby)**: 大家好，我是**科比 (Corby)**。我是**微软 (Microsoft)**的一名研究员，目前正与 BrowserBase 紧密合作，共同研发超高质量的**验证器 (Verifier)**。

今天我们来到这里，是想向大家深入解读我们大约一个月前联合发表的一项重磅研究。这项研究的核心关乎“评估”（Evaluation），具体而言，是关于**强化学习 (RL)** 环境构建，以及如何将大语言模型用作验证任务的**裁判员 (LLM as a Judge)**。

首先我想说明的是，过去大约一年半的时间里，我一直投身于一个名为 **Stat 10** 的开源框架的研发工作。从项目伊始，正如任何优秀的智能体产品一样，我们建立了一套严密的度量体系，目的是确保我们对框架所做的每一次调整以及底层模型能力的每一次跃升，都能持续取得进展并被这些量化指标真实反映。

最初，所有这些评估完全基于**确定性环境 (Deterministic Environments)**。这在当时相对简单直观，因为那时模型的能力还比较有限，我们完全有能力搭建大量封闭的确定性测试环境。然而，随着模型能力的迅猛增长，以及我们赋予智能体的工具链越来越丰富，这种确定性验证方法终于遇到了无法逾越的瓶颈，彻底不再具备可扩展性了。

<details>
<summary>Original English</summary>

**Corby**: So, but I am Corby. I'm a researcher at Microsoft, and I'm working with BrowserBase to help build really high-quality verifiers. Today we're here to talk about a study we published about a month ago. It concerns evaluation. Namely, reinforcement learning (RL) environments and the use of language models as judges for verification.

First, let me say that I've been working on this open source framework called Stat 10 for about a year and a half now. From the beginning, like any good agent product, we created a measurement system to ensure that the changes we make to the framework and model capabilities continue to improve and help drive these metrics. Initially, all of these estimates were deterministic environments. It was relatively simple. The capabilities of the models were somewhat limited. So we were able to build a lot of deterministic environments. As the capabilities of models continue to grow, and we continue to improve the toolkit of agents, this approach has ceased to be scalable.

</details>

### 网页自动化评估的确定性困境

**科比 (Corby)**: 我们过去不得不疲于奔命：要么是不断修补或者重新编写静态模拟网站，要么是费尽心机设计带有无数检查点的超长执行轨迹，只为了保证评测结果能够通过确定性规则来验证。

但是，要在真实的开放互联网规模上进行自动化并验证智能体是否真正达成了用户目标，面临着极其独特的挑战。根本原因在于：**万维网是一个完全开放的动态系统**。在网络世界中，通往正确结果的路径从来不是唯一的，根本不存在某种机械的绝对真理。更致命的是，网页时刻都在发生变动——你几分钟前还在测试购买的某款商品，下一秒可能就下架或断货了。这就彻底摧毁了整个评测环境的前提确定性。此外，还有各种各样的环境干扰与阻碍，例如网络抖动、验证码拦截等各种偶发环境错误，使得确定性判定信号极难稳定捕获。

因此，我们不得不转向目前业界绝大多数团队的做法：尝试引入 **LLM裁判 (LLM Judge)** 来改进并扩大这一评估流程的规模。

<details>
<summary>Original English</summary>

**Corby**: We were constantly fixing or creating static sites, inventing longer trajectories with many checkpoints to make sure that the evaluation results could be deterministically verified. There are many different challenges with automating the web at scale and verifying that what you have in mind has actually worked. The fact is that the web is a very open system. There is no single path to correctness. There is no absolute truth. Sometimes the web changes and the product you were checking out before no longer exists. This destroys all determinism of your environment. There are also obstacles. There are many environmental errors that prevent a verified deterministic signal from being obtained. So we resorted to what most people do: we tried to use an LLM judge to improve and scale this operation.

</details>

### LLM裁判的虚假繁荣与“更自信的骗子”

**科比 (Corby)**: 但是，我们很快就遭遇了一个极其残酷的现实。目前很多业界主流的基准测试——大家可能对用于计算机操作评估的 **OSWorld** 有所耳闻，而在网页领域也有类似的著名基准，比如 **Online Minor Web** 以及 **WebVoyager**。这些基准测试全都是直接搭载基于大语言模型的裁判来充当验证器的。

然而，当我们组织资深人类专家对现有的 LLM 验证器进行严格交叉比对测试时，我们震惊地发现：**在相当多的情况下，这些裁判都在极其自信地给出错误判断**！这就导致评估产出的分数完全不可信赖。

我们立刻意识到其中的严重危害：如果你打算将这种充满幻觉的判定结果用作强化学习的奖励信号（RL Reward），或者作为改进模型行为的研究指导信号，**你根本训练不出一个更优秀的智能体，你只是在训练一个更加自信的骗子（a more confident liar）**！

在微软内部的一个真实工业级案例中，我们训练了一个名为 **Farfetch'd 7B** 的网页浏览智能体模型。当我们在相同的基准测试上使用 WebVoyager 官方默认的裁判（即 **GPT-4o**）进行评估时，它给出的成功率高达 **74%**。然而，当我们换用我们全新研发的、与人类专家判定高度一致的通用验证器去核查真实情况时，该模型的真实成功率瞬间暴跌到了 **38%**！

也就是说，现有主流验证器宣称的数字与现实真相之间存在着一条高达 36 个百分点的巨大鸿沟！我们必须找到一种彻底弥合这一鸿沟的科学评估方案。

<details>
<summary>Original English</summary>

**Corby**: But we quickly found out that many of the leading benchmarks—some of you may know about OSWorld for computer use, but there are similar benchmarks for the web, like Online Minor Web and Web Voyager. They are supplied with LLM-based judges as verifiers. And we noticed when we used our human experts to test the verifier that in many cases they were very confidently wrong. And this leads to results that cannot be trusted. So we realized very quickly that even if you use this as an RL reward or a signal to improve persistence in other studies, you're not training a better agent. You are simply training a more confident liar.

So, in a real-world case at Microsoft, we trained the Farfetch'd 7B model, which is a web browser agent. And we evaluated the same model on the same benchmark against the official Web Voyager judge, i.e. GPT-4o, and it showed a success rate of 74%. But there is a huge gap between the real truth, which we obtained with our new universal verifier, which has a high level of agreement with human estimates, and that number quickly drops to 38%. So there is a huge gap between what existing verifiers say and what actually exists. And we needed to find a way to bridge that gap.

</details>

### 现有验证器的四大缺陷与通用验证器工作流

**科比 (Corby)**: 现存的验证器之所以表现如此糟糕，是因为它们存在诸多致命短板：
1. 它们往往使用过于轻量或能力简陋的模型充当裁判，甚至仅仅使用 **GPT-4o mini** 或直接简单提示词驱动的 GPT-4o；
2. 它们**根本没有引入科学的评分细则 (Rubrics)**——细则至关重要，因为你需要对复杂任务的各个阶段进行合理的归因与信用分配（Credit Assignment）；
3. 它们要么完全不看执行过程中的关键屏幕截图，要么试图一股脑把轨迹中的所有截图全塞进去，导致信息瞬间过载，直接把 LLM 裁判的上下文窗口撑爆并彻底迷失；
4. 有时它们甚至连智能体的最终回答或完整动作执行历史都不做交叉比对。

我们设计的**通用验证器 (Universal Verifier)** 针对性地克服了上述所有缺陷。从高层架构来看，它的工作机制如下（论文中包含完整技术细节）：

以“预订西雅图到波士顿最便宜的航班”这一任务为例。首先，系统会自动为该任务生成一份极高标准的详细**评分细则 (Rubric)**。这份细则会列出 $N$ 个定义成功的严谨判断准则。接着，基于细则中的每一条准则，我们去严密分析智能体的完整操作轨迹。在这套体系中，智能体执行过程中留下的所有网页截图，被视为系统真实状态的**客观物理证据 (Ground Truth Evidence)**。

我们会针对每一条细则准则，从整条轨迹中检索并排序出最相关的屏幕截图。然后，验证器提取这组排名前 $K$ 的最佳证据片段，以此来独立裁定该准则是否得到真实满足，并严格检验智能体声称自己完成的操作与截图所反映的真实环境状态之间是否存在任何矛盾与出入。

最终，我们不仅输出细则各维度的**过程分 (Process Score)**（允许在部分步骤中给予部分分数），还会得出一个总体的布尔值**结果判定 (Outcome Check)**，以严谨说明一个合理的真实用户是否会认可该轨迹达成了预期。这就形成了一个包含准则列表、布尔标志位以及详细解释说明的结构化判定报告。

<details>
<summary>Original English</summary>

**Corby**: Existing verifiers have many weaknesses. They use smaller and much simpler models as LLM judges. They use GPT-4o mini or GPT-4o. They don't even use rubrics. Rubrics are the most important thing to have because you need to distribute credit where it is deserved. They don't look at the relevant screenshots or try to view all the screenshots at once, quickly getting lost and cluttering the LLM judge's context window. And sometimes they don't even look at the final answer or the model's action history.

So our verifier takes all these aspects into account. And here's how it works at a very high level. You can find more details in the article, but for a task like “book the cheapest flight from Seattle to Boston,” the first thing we do is create a very high-quality rubric, and I’ll give you a few examples. The rubric has, say, n different criteria for what success looks like. And then, based on these criteria in the rubric, we analyze the trajectory of the agent's actions. All screenshots in this case are evidence of the true state of the system. We rank the most relevant screenshots in the trajectory for each criterion. We then use this group of K best evidence to determine whether this criterion has been met. And are there any discrepancies or contradictions between what the agent said he did and what actually reflected the state of the environment.

With that in mind, we issue a graded rubric, which we call a process score because it gives partial scores in some cases, and we also issue a Boolean result value to essentially say whether the agent performed the task according to the expectations of a reasonable user. Uh, and this is an example of what the output of the rubric is. This is essentially a list of criteria, plus a result check, which is a logical true/false flag with an explanation of why a reasonable user would expect this trajectory to be successful or not.

</details>

### 通用验证器的四大核心构建原则

**科比 (Corby)**: 在构建这套通用验证器时，我们确立并严格遵循了**四大核心原则 (Four Principles)**：

第一，**仅评估任务所要求的内容，绝不引入无关标准**。我们在制定细则时，必须保证每一项准则都严格对齐初始任务，杜绝无理加码。

第二，**杜绝错误级联 (Avoid Cascading Errors)**。在多步复合任务中，必须将各准则间的判定进行逻辑隔离，防止早期某个细小失误直接毁掉后续所有正确操作的得分。

第三，**强制核验反映环境真实状态的屏幕截图**。这是不可妥协的硬性要求。智能体往往会极其自信地宣称自己已经完成了某项操作，但实际上根本没有执行成功。必须以客观截图证据为准。

第四，**严格区分智能体可控失败与外部不可控失败**。智能体运行在真实网页浏览器中，而网页环境充满了智能体自身无法掌控的外生变量，评分必须做到赏罚分明。

<details>
<summary>Original English</summary>

**Corby**: When creating this universal verifier, we were guided by four main principles. The first concerns the creation of the rubric: we wanted to evaluate only what was asked for, not any extraneous criteria. We also didn't want errors to cascade from one rubric criterion to another. We wanted them to be isolated, and I'll give an example of that. You also wanted to look at screenshots confirming the true state. This is a mandatory condition. Agents often claim too confidently that they did something when in fact they did not. So you have to look at snapshots of the true state of the environment. And we also needed to separate what the agent could control and what the agent could not control. The agent runs in a web browser. A web browser is an environment that an agent cannot always control, and I will also show some examples of this.

</details>

### 评分细则设计与级联错误隔离实战

**科比 (Corby)**: 让我通过具体案例来说明好细则与坏细则的区别。

假设任务是：“在指定日期内找到雅加达的一家平价酒店，随后使用该酒店的地址搜索距离最近的咖啡馆，并输出该咖啡馆的名称和地址。”
我们在实践中遇到过一个劣质细则，它竟然包含这样一个判定标准：“请告诉我入住该酒店的总费用。” 这就是一个典型的**无关外加标准**，用户在任务提示中根本没有要求计算总房费！但很多通过朴素 Prompt 自动生成的细则经常犯这种错误，因为智能体没有回答根本没被问到的问题而盲目扣分，从而人为拉低了得分。

再来看如何避免“错误级联”。多步骤流程中，很多任务是环环相扣的。例如有这样一个测试任务：“在超级男孩（N Sync）与后街男孩（Backstreet Boys）的所有成员中，找出姓氏最长的那位，并查询其净资产。”
在这个案例中，智能体出现了一个失误：它算错了字母数，错误地认为贾斯汀·汀布莱克（Justin Timberlake，姓氏长 10 个字母）是姓氏最长的人，而实际上应该是克里斯·柯克帕特里克（Kirkpatrick，长 12 个字母）。
显然，模型在细则的其中一个步骤上犯了算术比较错误。但是，这一惩罚**绝不应该级联蔓延到下一个准则——即汇报所选人员净资产的标准**！如果智能体能够极其准确地检索并输出 Timberlake 的净资产数据，那么在净资产汇报这一项上，它就不应该再次被扣分，惩罚应当严格局限在算错姓氏长度的那一单项上。

<details>
<summary>Original English</summary>

**Corby**: So, this is an example of what a good and bad rubric looks like. The task here is to find a cheap hotel in Jakarta for these dates, and then use the hotel address to search for the nearest coffee shop and output the name and address of that coffee shop. But a bad rubric, which we actually saw, would have given a criterion like: "Please tell me the total price for staying at the hotel." This is actually an extraneous criterion that was not asked for in the task, but we have seen many naively generated rubrics do something similar, and they artificially lower scores because the agent did not do something that was not asked.

Um, regarding avoiding cascading errors—there are very subtle errors because many tasks build on each other if they are multi-step processes. So, in this example, the task was to determine the net worth of the person with the longest last name among the members of the bands N Sync and Backstreet Boys, okay? The agent in this case mistakenly decided that Timberlake had the longest last name, consisting of only 10 letters, when in fact it was Kirkpatrick's. So, the model made one arithmetic error in one of the rubricator criteria, and this should not apply to the next criterion—reporting the net worth of the selected person, right? So if you can accurately report Timberlake's net worth, you shouldn't be penalized for this criterion. You should be punished for just that one point.

</details>

### 微妙幻觉与可控/不可控失败归因

**科比 (Corby)**: 捕捉**隐蔽幻觉 (Hallucinations)** 是我们极其关注的核心维度。在某些图像描述模型的文献调研任务中，智能体汇报称该模型在某个 CIDEr 指标上提升了 6.2%。但经过截图证据比对，原始论文摘要中白纸黑字写的是仅提升 2.8%！这种细微的数字捏造极其隐蔽，普通人类在粗略核查时很容易直接漏看，直到大模型对准真实截图严密比对才被纠察出来。这就是过程分核验的强大力量。

关于第四项原则——区分“可控失败”与“不可控失败”：
比如任务要求智能体在亚马逊上购买某款特定毛绒玩偶。智能体准确检索并找到了该目标商品，但发现该商品目前显示**缺货（Out of Stock）**，导致后续下单流程无法继续。在这种情况下，我们认为智能体在达成目标所付出的有效努力上应该获得**全额过程分（Full Credit）**；但在最终结果维度，由于客观缺货导致未能完成购买，它确实没有产出最终成功状态。
如果智能体通过变通手段找到了同款替代毛绒玩具并顺利完成购买，那它在过程与结果两端都将判定为成功；而如果它在有货的情况下发生操作失误或产生虚假汇报，就会面临扣分惩罚。我们梳理并制定了一整套涵盖所有可能失败类型的系统架构图，通用验证器严格按照这套映射逻辑进行公正判分。

<details>
<summary>Original English</summary>

**Corby**: Hallucinations are the most important aspect that we really wanted to focus on. Here is an example of a very subtle hallucination in a task where you had to find information about a model for describing images, and the agent stated that this model has a plus of 6.2% according to some Cider estimate. But in fact, the annotation to the relevant article indicated only 2.8%, according to Cider's estimate. It was a very subtle mistake that even a human wouldn't notice until LLM pointed it out. Hmm, that gives some idea of how process assessments differ from outcome assessments.

Um, we mentioned that one of the principles is to separate managed and unmanaged failures. If the task is to buy, say, this plush toy on Amazon, and the agent definitely found it but discovered it was out of stock, he was unable to proceed. Therefore, we believe that the agent receives full credit for the effort made to achieve the goal. But the result was still not achieved, as he was unable to buy the desired item due to it being out of stock.

Um, we actually listed a bunch of scenarios of what could happen and how we assign grades. If the agent could find a similar alternative plush toy in another way, um, he would still succeed in both cases. And he will receive a penalty if he makes a controlled error. Um, he'll be fined if he hallucinates, and so on. So, we actually made a diagram of all the possible types of failures and how we would award points for it. And the universal verifier adheres to these schemes.

</details>

### 人类专家比对实验与虚报率清零

**科比 (Corby)**: 为了严谨验证通用验证器是否真正提升了判定的准确性，我们设计了一整套由人类专家参与的基准实验，并搭建了一个用于收集真值基准数据的完整平台——即我们开源发布的 **Cool Verify Bench**（包含参考标签 Reference Labels）。

评测流程如下：
首先，我们将智能体执行的完整动作证据链与截图呈现给专业的人工标注员，由他们先独立给出判断；随后，再向标注员展示通用验证器的评分与分析，请他们判定是否认同验证器的结论。

这个机制为我们提供了极具价值的校验信号。坦白讲，最惊人的发现是：**通用验证器开始主动纠正人类专家的疏漏**！许多人类肉眼看漏的细微矛盾和虚假宣称都被验证器精准揪出。最终，通用验证器在与基准标签的比对中，**将伪阳性率（False Positive Rate，即把失败误判为成功的假成功率）从接近 50% 彻底压降到了 0%**！

在统计学一致性指标上，我们使用 **Cohen's Kappa 系数**来衡量验证一致性。实验表明，通用验证器与人类判断之间的一致性，已经完全媲美人类专家之间相互达成的一致性水平——在两名独立标注员彼此之间计算的 Cohen's Kappa 为 **0.58** 的复杂任务上，通用验证器与人类的一致性也达到了同样的高水平。

<details>
<summary>Original English</summary>

**Corby**: So, to evaluate the verifier and really understand whether we were able to improve its accuracy, we started designing a bunch of experiments involving human experts and created a whole platform for collecting data that we called reference labels, which we also released as Cool Verify Bench for others to learn from.

The process we followed was as follows. Initially, we showed the full trajectory of evidence to human verifiers. Annotators made judgments based on the evidence and results of all the actions the agent performed. After that, they were asked, upon seeing the universal verifier's assessment, to confirm whether they agreed with it or not. We found this to be a very reliable signal to check if we were moving in the right direction, because I'll get straight to the point: the verifier started correcting people. He discovered things that people missed.

Ultimately, the result of the universal verifier working with these reference labels was that we were able to reduce the number of false positives from almost half to zero. Cohen's Kappa is a metric for measuring the consistency between our annotators. And what we see here is that the universal verifier agrees with people as often as people agree with each other. So we see a Cohen's kappa of 0.58 compared to two annotators on the task, where we also calculated Cohen's kappa to see how well they agree with each other.

</details>

### 数据过滤实验与模型 SFT 性能飞跃

**科比 (Corby)**: 检验验证器优劣的另一大终极试金石，就是用它筛选出的数据去训练下游模型。

我们进行了一项严格控制变量的对比实验：保持训练样本总数恒定（分别测试了 3000 条与 9000 条轨迹），但利用不同的验证器来过滤这些轨迹，仅保留验证通过的样本。因为在进行**监督微调 (SFT)** 时，大家最关键的诉求就是**只让模型学习真正成功的黄金执行轨迹**。

实验结果令人振奋：在相同样本规模下，使用我们的通用验证器筛选出的 3000 条轨迹训练出来的模型，其下游综合表现远超使用传统基准验证器过滤数据训练出来的模型。随着样本量提升，这一质量差距依然显著成立。这雄辩地证明：**更强大的验证器能够清洗出更高质量的训练数据，而高质量数据直接锻造出更卓越的智能体模型**。在工业级生产落地场景中，验证器是驱动模型进化的核心引擎。

<details>
<summary>Original English</summary>

**Corby**: Another way to check the quality of our verifier is to train it on data filtered by it. So we conducted an experiment in which we left the number of training examples unchanged. In this case, it was 3 thousand or 9 thousand training trajectories, but we filtered these trajectories depending on whether they passed our verifier. When you do SFT, which is what we did here, you only want to learn from examples that were successful trajectories.

So if you train on 3000 trajectories filtered by the score of our universal verifier, you will get a much better quality model than if you trained on a worse, baseline verifier. This statement turned out to be true on a larger scale as well. So this experiment showed us that if you have a better verifier, you can filter out better data, and training on that data leads to a better model. So, this was like the final experimental proof in addition to the human validation that this model, this verifier works and is reliable in a real production scenario.

</details>

### 自动科研（Auto-Research）循环与人类直觉的融合

**科比 (Corby)**: 作为延伸探索，我们还做了一件非常有意思的事：尝试测试 AI 能否在一个自主循环中完全自学构建出与我们水平相当的验证器。

坦率地讲，我和 Miguel 花费了整整三周时间进行工程攻关，编写提示词、搭建代码管线，在这三周里运行了大约 30 组不同的实验来打磨通用验证器，力求使其判定与人类吻合。图中 Y 轴上的 Cohen's Kappa 即代表吻合度，蓝线代表我们二人耗时三周手工打造的系统。

随后我们测试：如果我们清空所有手工代码和提示词引导，让处于自动学习闭环中的 AI（即 **Auto-Research** 体系）从零开始探索，它能否复刻出同等水准的验证器？
图中的红线与绿线代表了自动科研的结果。红线显示，在剥离一切先验的情况下，AI 确实能够在短短 **1 天之内**自动跑完我们三周所做的同等实验数量！然而，它最终只达到了我们手工验证器约 **70%** 的一致性水平。

结论非常明确：自动科研循环极其适合用来快速探索指标和验证器原型，大幅压缩实验周期；但在当前阶段，**人类专家的专业直觉与关键介入依然不可或缺**。必须说明的是，这一实验当时是基于 **Opus 4.6** 跑的，未来换用更强模型可能会有更好表现。但最核心的启示是：**构建高精度的验证器与构建模型本身同等重要**。

**米格尔 (Miguel)**: 是的，我补充强调一点：图中的绿线代表的是在吸收了我们三周人类实验成果的先验基础上，再由自动化科研算法进一步优化迭代出的验证器。通过这种结合，系统一举打破了天花板，取得了前所未有的最高指标！这充分证明：**将人类深刻的领域洞察与自动科研循环的超高算力迭代相结合，是攻关前沿科学与工程难题的最优解**。

<details>
<summary>Original English</summary>

**Corby**: The last thing we did as a side project was try to determine whether artificial intelligence in self-study could create the same verifier as we did. So, basically, Miguel and I sat down for 3 weeks to build a universal verifier, tweak the prompts, and write code for it, and we ran about 30 different experiments over the course of 3 weeks to determine whether the verifier we were building matched people's estimates. Okay, and that's what Cohen's Kappa measures here on the Y-axis, it measures whether a particular verification system agrees with people's estimates.

So the blue line here is the model that Miguel and I were building, this auto-research system, this universal verifier. And then we wanted to see, if we took away everything we had done, could the AI in the auto-learning loop create the same verifier that we had created, with the same level of quality and accuracy? And that's what the red and green lines here represent. The red line shows whether the AI could reproduce this if we removed all our code and clues. The conclusion we drew from this is that while it took us about 3 weeks to build this verifier, an auto-research cycle could do it in about 1 day. He conducted the same number of experiments in about 1 day. However, it only achieved about 70% of the matches that our verifier was able to achieve. So, the gap still exists. The conclusion I would draw is that you can use auto-research to create metrics and verifiers, at least to help you speed up your experiments, but you probably still need some level of human intervention. On the other hand, these results were obtained on Opus 4.6. I haven't tried this with Fable yet. Maybe he'll do better. But it's a pretty strong base, and it's come pretty far. So, auto-research can help you not only build a model, but also, in this case, build a verifier, which we think is a pretty cool thing. And creating verifiers is just as important as creating the models themselves; This is one of the main conclusions I want to leave you with.

**Miguel**: Yes, and to further emphasize: the green indicator is a verifier of automatic research, prepared based on the results of our three-week experiments. Thanks to this optimization, we were able to achieve higher performance than ever before. Therefore, combining human intuition with cycles of automatic research has proven to be the most effective recipe for many scientific tasks.

</details>

### 开源发布与基准测试的未来展望

**科比 (Corby)**: 整个项目目前已经全方位向开源社区开放。研究论文预印本已上线 arXiv，微软官方开源仓库中提供了完整的测试代码与评测基准。

更重要的是，这项研究催生了一个全新的智能体基准评测集。我平时花费大量时间深入各大 AI 实验室，协助他们建立坚实的量化信号来迭代模型。目前社区很多开源基准（如 WebVoyager 等）损耗老化的速度非常快，测试集数据很快就不可避免地泄漏进了新模型的预训练分布中，导致很难再提取出有效的评测梯度。而我们这套全新的基准测试被证明是当前衡量真实成功率最具生命力的方法，我每天都借助它来诊断模型长短板并指引迭代方向。

我的分享就到这里，Miguel 你那边还有幻灯片要展示吗？

**米格尔 (Miguel)**: 没有了，以上就是全部内容。现场如果还有一点时间，我们可以回答大家几个问题。非常感谢大家！

<details>
<summary>Original English</summary>

**Corby**: This entire project is open for use. The article is published as a preprint on the arXiv website, and the Microsoft Auto repository contains reference marks for the verification bench. It also contains code for conducting experiments. But beyond that, the study allowed us to create a completely new benchmark. We have already briefly mentioned Online Minor Web and Web Voyager. I spend a lot of time working with labs, helping them get quantitative signals to improve their models. Many such open source benchmarks exhaust their resource very quickly, and it becomes difficult to get any useful signal, since the test data is already effectively included in the training distribution. Therefore, this new benchmark has proven to be the most promising for assessing success, and I use it every day to understand the strengths of the models, their shortcomings, and ways to bridge the gap. That's it. Did you have any more slides?

**Miguel**: No, that's all. We can answer a few questions, time permitting. Thank you.

</details>

### 现场问答 Q&A：跨场景泛化与防过拟合机制

**观众**: 请问这套通用验证器是否已经应用到网页端以外的其他任务场景中了？

**科比 (Corby)**: 好问题！在微软，我们目前正在全力推进将该验证器适配至**桌面端操作任务（Desktop Tasks）**——也就是用户在笔记本电脑或办公 PC 上执行的企业级复杂工作流。

我们计划不久后发布一个不仅涵盖 Web 数据、更包含企业桌面数据的全新基准。我们正在为桌面场景量身打造同等机制的验证器。在桌面环境中，验证器能够利用的信号其实更丰富，除了图形界面，还包含终端（Terminal）命令行输出、系统遥测指标以及各种运行日志，验证器会把这些多模态系统轨迹一并纳入考量。

<details>
<summary>Original English</summary>

**Audience**: Yes. Yes.

**Corby**: So, the question is whether we used the universal verifier for tasks other than web tasks. At Microsoft, we are currently working on adapting a version of this verifier for desktop tasks, i.e. what you do on your laptop, such as corporate workflows. We hope to publish another benchmark not only with web data, but also with corporate desktop data. We will create the same type of verifier for this as well. It will take into account more information, as there is a terminal on the desktop, more telemetry and logs than just in the browser. Therefore, the verifier will also take this data into account. Yes. Any more questions?

</details>

**观众**: 你们在研发验证器时，是如何保证验证器本身不会在人类专家评分数据上发生过拟合的？

**科比 (Corby)**: 这是一个切中要害的严肃问题！防止验证器在人类标注数据上发生过拟合，是我们和 Miguel 花费巨大心血解决的核心难题。

为了彻底杜绝过拟合，我们实行了严格的**多数据集隔离策略**：
我们当时总共准备了大约 150 条轨迹数据。其中，大约 50 条由我亲自标注，专门用于那 30 轮提示词与代码工程实验的迭代优化；而剩下的整整 100 条轨迹，我们在整个开发周期中**完全封存，严禁触碰**！

这 100 条保留轨迹完全交由我们付费聘请的人工专家标注团队进行处理，并且采用**双重重叠（Double Overlap）**机制——即每一条测试轨迹都必须由两名标注员独立背对背打标。在我们通用验证器的所有逻辑彻底固化冻结之后，才正式输入这组保留测试集进行最终大考。这就是我们在论文与评测集榜单中最终呈现的权威数据。

由于我们始终保留了至少三分之二的黄金标注数据作为盲测集，从未在其上做过任何逆向拟合，我们对这一评估结果的泛化鲁棒性极具信心。大家千万不能在自己的测试集上自娱自乐地迭代。**黄金法则是：雇佣合格的人类标注专家，对其进行严谨的任务规程培训，建立高质量的真值集，再以此为基准检验算法输出的吻合度**。

现场还有其他问题吗？有人愿意加入我们一起开发更多评测基准吗？太好了！非常感谢大家，祝各位在剩下的展会时光中过得充实愉快，谢谢！

<details>
<summary>Original English</summary>

**Audience**: Yes. Yes. Yes. Yes.

**Corby**: So, the question of how to ensure that the verifier does not overtrain on human estimates is a real problem. Miguel and I spent a lot of time working on this issue, so we actually put aside two sets of labels. We had a set of about 150 trajectories. I marked about 50 of these trajectories myself and used them for optimization in those 30 experiments, but we didn't touch the other 100 trajectories. They were processed by people we paid, with double overlap. So when we finished developing our verifier, we handed it over to these mappers, and each of them mapped each trajectory. Sorry, two people marked each trajectory. And that's exactly what we published in the Co-op verifier test. So these are the numbers we are presenting here. We are pretty confident that we did not allow overtraining because we left at least 2/3 of the tags in reserve. We didn't train or iterate on them. Yes. This is very important, you don't want to learn on your own...

Yes. Yes, the gold standard is to hire people, train them to perform verification tasks, and then check if your system output agrees with that. Any more questions? Anyone want to help us create more benchmarks? Yes. Oh, yes. OK. Good. Yes, yes, yes. Perfectly. Well, thank you very much. I hope you enjoy the rest of the exhibition. It was nice. Thank you very much. Thank you very much. Yes, yes. Mm.

</details>