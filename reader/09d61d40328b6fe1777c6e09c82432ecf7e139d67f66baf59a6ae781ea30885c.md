---
author: 课代表立正
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=nCBIotZzPEM
speaker: 课代表立正
tags:
  - hypothesis-testing
  - ab-testing
  - statistical-power
  - sample-size
  - minimum-detectable-effect
title: 拆解假设检验的第一性原理：Alpha、Beta、检验力与最小可检测效应（MDE）深度解析
summary: 本文从第一性原理和可视化视角，系统厘清了数据科学中最核心却常被误解的假设检验框架。深入解析了零假设与备择假设的本质、标准差与标准误的区别、第一类与第二类错误（Alpha/Beta）、统计功效（Power）的三重含义，以及样本量如何动态决定最小可检测效应（MDE），为工业级A/B测试设计提供了清晰的底层逻辑支撑。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 假设检验的认知困境与第一性原理重构

在数据科学领域，**假设检验**（Hypothesis Testing: 利用样本统计量对总体参数假设进行概率推断的统计方法）是最基础、最通用的核心课题，但同时也是最容易令人产生混淆和误解的概念。这种理解障碍普遍到甚至可以作为一项“套利赌局”——由于该主题被默认是数据科学家的基本功，大多数人都会欣然接受挑战，但最终往往会因为概念体系的模糊而败下阵来。造成这种普遍困惑的根本原因在于，主流教科书通常将两种本质不同的框架（基于 p 值的显著性检验与 Neyman-Pearson 假设检验框架）进行了不一致的混合拼凑，而网上的碎片化文章进一步加剧了认知混乱。即便是具备深厚实验背景的资深专家或博士，往往也需要反复翻阅教材寻找技术定义，这恰恰证明大家尚未在**第一性原理**（First Principles: 回归事物最底层本质与公理的思考方式）层面对其建立直觉理解。

为了打破教科书的解释困境，有必要结合长期的客户实验咨询实践，在理论与工业界实操之间找到平衡点。通过提炼数百次与业务方的沟通经验并经过多轮重构打磨，我们剥离了繁复的数学公式推导，转而完全基于第一性原理与直观可视化，将假设检验拆解为 10 个层层递进的核心概念：从原假设、第一类错误、Alpha 与临界值，到备择假设、第二类错误、Beta 与检验力（Power），再到检验力与样本量的动态关系，最终引出**最小可检测效应**（Minimum Detectable Effect, MDE）及其在实验规模下的变化机制。这种渐进式的知识架构不仅能让业务层利益相关者（Stakeholders）迅速建立共识，更能为工程师在后续的实验设计中节省大量沟通成本。

<details>
<summary>Original English</summary>

I have created over 500 videos as a data scientist content creator, but this video is the first one that I would call a must watch for all data scientists. It is hypothesis testing. Hypothesis testing is one of the most fundamental and universal topic for data scientist, but it is one of the most confusing and misunderstood topic as well. So much so that you can actually create an arbitrage by betting with a data scientist and make profits because most data scientists would take the bet since the topic is expected to be well understood, but they would lose the bet because it is so confusing. The reason for it being so confusing is because our textbook is an inconsistent blend of two frameworks, the p value and significance test, and the hypothesis testing framework. Of course, online articles only exacerbate this problem.

I can tell you as a PhD and as an experienced data scientist specialized in the domain of experiment, I didn't understand this concept until recently. When I shared that on LinkedIn, many data scientists resonated with my feeling because we always need to go to the textbook for the technical definitions, which, is a signal that we didn't understand the concept at a first principle level. Why are we uniquely qualified to answer this question when textbook failed to do so? We have an experienced data science team that has worked for years with customers on their experimentation challenges and understanding. we've done this from very inexperienced to very experienced and we've had to walk the fine line between the theory and the practical aspects of experimentation We distilled our years of experiences and our hundreds of conversations explaining this concept to our customers and we remade this video six times. Finally, we got to a tutorial without any formulas based on first principles with the help of a lot of visualizations that everyone, including middle school students, can understand and is technically correct and consistent.

There are 10 concepts in this video and we'll introduce them incrementally. First, I'll introduce the concept of the null hypothesis, type one error, alpha, and the critical value. Second, I'll introduce the alternative hypothesis, type two error, beta, and power. Then, I will visualize how power change with sample size. And finally, I will introduce the concept of the minimum detectable effect or MDE, and how that change with sample size. if you don't fully understand hypothesis testing, If you feel like you have to go to the textbook definition, every time you talk about alpha, beta, and power, this is your chance to understand. And if you do, this is a great video to help you explain it to your stakeholders to save you hours of time down the road.

</details>

### 零假设与第一类错误：决策阈值的概率权衡

在构建推断体系时，首先要明确的是**零假设**（Null Hypothesis: 假定实验组与对照组之间不存在真实处理效应的基准假设）。在常规实验场景中，零假设通常表述为处理组与对照组的均值差异趋近于零。依据**中心极限定理**（Central Limit Theorem: 独立随机变量之和在样本量足够大时趋近于正态分布的统计定理），只要样本量足够（通常样本容量达到 30 便已充分），样本均值差的基础分布就会呈现为正态分布。在此必须严格区分两组易混淆的统计指标：
* **标准差**（Standard Deviation: 衡量总体基础分布中各个单一样本离散程度的指标）。
* **标准误**（Standard Error: 衡量多次抽样所得样本均值离散程度与估计误差的指标）。

如果只抽取单个样本观测值，其结果可能落在总体分布 X 轴的任意位置；但如果抽取多个样本并计算样本均值，由于均值向中心集中的概率更高且正负偏差相互抵消，样本均值的误差会显著收窄。标准误在数学上等于标准差除以样本容量的平方根（$\text{SE} = \frac{\sigma}{\sqrt{n}}$）。假设零假设的基础分布均值为 0、标准差为 1，在样本量为 30 的情况下，该样本均值的标准误约为 $1 / \sqrt{30} \approx 0.18$。

在假设检验中，我们的核心目标是根据观测到的样本均值及其标准误分布，对是否存在处理效应做出决策：究竟是接受零假设，还是拒绝零假设？由于身处概率世界，X 轴上的任意取值都有可能发生，我们永远无法做到 100% 绝对正确，因此必须制定明确的决策规则，在“容忍一定概率的犯错”与“发现真实效应”之间取得平衡。如果制定过于严苛极端的决策规则，虽然能避免错误，但也无法做出任何有效发现。

为了实施决策，我们需要在零假设分布上设定一个阈值，即**临界值**（Critical Value: 决定接受或拒绝原假设的分界数值）。样本均值高于该阈值则拒绝零假设，低于该阈值则接受零假设。在仅引入零假设的场景下，我们面临的唯一风险是**第一类错误**（Type I Error: 当零假设实际上为真时，却错误地将其拒绝并判定存在效应的假阳性错误）。通过移动临界值，可以直接调节犯第一类错误的概率，这一概率被称为**显著性水平**（Alpha: 允许犯第一类错误的最大概率上限，即分布曲线尾部的拒绝域面积）。若将 Alpha 设定为标准的 5%（0.05），在上述参数下经过计算可得出对应的临界值为 0.30。此时决策规则十分清晰：抽取 30 个样本计算均值，若均值大于 0.30 则拒绝零假设；若小于 0.30 则接受零假设，此时承担的第一类错误概率恰好为 5%。

<details>
<summary>Original English</summary>

All right, let's start with the null hypothesis. Since this is the first time we introduce hypothesis testing, let's also clarify the language between standard deviation and standard error. The concept of the null hypothesis is there is no treatment effect. It is commonly expressed as the difference in means between the treatment group and the control group  going to zero. According to the central limit theorem, the underlying distribution of this difference in means is going to normal with sufficiently large sample, and by sufficiently large, 30 is enough. Pay attention to the underlying distribution. The error of the underlying distribution is called the standard deviation. The error of the sample mean is called the standard error. Following this underlying distribution, if we draw one observation, it can be anywhere on the x axis with this chart. But if we draw many observations and take the sample mean, the error of the sample mean is going to be smaller for two reasons. One, more chance of being centered, and two, the left and right cancel each other out. So standard error is the standard deviation divided by the square root of the sample size. To make things simple let's assume the underlying distribution of our null hypothesis is mean zero, standard deviation of one, and we have a sample of 30, the standard error of this sample mean is going to be one divided by the square root of 30, which is about,  0.18.

In hypothesis testing, our goal is to make judgments according to the sample we observe. So we plot the sample mean with the standard error. The judgment we want to make is, is there a treatment effect or not? Shall we accept this null hypothesis or reject this null hypothesis? If you wonder, did I make a mistake by saying, accepting the null hypothesis, instead of saying, failing to reject the null hypothesis, go to our blog to check the clarification. I'm actually correct because this is a world of only two possibilities. That is the beauty of introducing concepts incrementally because we can go to the most intuitive definitions without making mistakes.

Anyway, let's go back to our judgment and the decision rule. Shall we reject or shall we accept? The decision rule is important because we are in a world of probability, anything on the x axis can happen with different chance. We can never be 100 percent correct, so we want to make certain mistakes with certain probabilities that is acceptable to our decision rule. Finding the right balance is what makes hypothesis testing useful. If we set our decision rule to be extreme, we won't make mistakes, but we won't make discoveries either. This will be clear when we talk about the alternative hypothesis, but let's just stay with the null hypothesis right now.

With the null hypothesis, we want to set a rule, we want to set a threshold, above this threshold, we reject the null hypothesis, below the threshold, we accept the null hypothesis . This threshold is called the critical value. As you see, I only have the null hypothesis, so there is only one type of mistake I can make. The type 1 error, when the null hypothesis is true, I falsely rejected the null hypothesis. If I move the threshold, if I move the critical value, I can change the probability of my type 1 error. Which is the blue area and the curve, and it's called alpha. So suppose I want my alpha to be 5 percent or 0.05. I already know the distribution of my sample means, I do some calculation and discovered the critical value in this setting corresponding to 5 percent alphais 0.30 . Our simple decision rule is, if we draw a sample of 30 observations and calculate the sample mean, if the sample mean is above 0.3, Then we reject the null hypothesis. If the sample mean is below 0.3, we accept the null hypothesis. If we check the math, the blue area, our alpha is 5%.

</details>

### 无穷备择假设与第二类错误：检验力的多维解析

在建立零假设与判定阈值之后，若要真正实现业务探索与发现，就必须引入**备择假设**（Alternative Hypothesis: 假定存在真实处理效应且效应量不为零的对立假设）。在此存在一个教科书鲜少重点强调却至关重要的事实：现实中理论上存在**无穷多个备择假设**。备择假设本质上是一个理论构建，面对任意观测数据，潜在的真实效应大小均有其对应的概率分布。为了便于解析，我们先选取一个特定的备择假设场景——假设其底层分布均值为 0.5，标准差为 1。

将该特定备择假设纳入决策框架后，原有的判断规则相应完善：在样本量为 30 时，若观测均值高于临界值 0.30，我们拒绝零假设并接受该备择假设；若均值低于 0.30，则接受零假设并拒绝该备择假设。此时系统产生了第二种潜在风险——**第二类错误**（Type II Error: 当备择假设为真即实际存在效应时，却因样本均值低于临界值而错误拒绝备择假设的假阴性错误），犯下第二类错误的概率记为 **Beta**。Beta 的大小由三个核心要素决定：
1. 备择假设分布的标准误大小；
2. 备择假设的均值设定（效应量大小）；
3. 临界值的选取位置。

当我们将 Alpha 固定在 5% 时，临界值（0.30）随之确定，此时如果设定的备择假设相对保守（均值贴近 0），Beta 就会偏大；反之若设定的备择假设效应极其显著，Beta 则会大幅缩小。

由 Beta 可以直接推导出统计推断的核心枢纽——**检验力**（Statistical Power: 在效应真实存在的前提下，实验能够正确拒绝零假设并检测出该效应的概率，定义为 $1 - \beta$）。许多学习者仅停留在公式定义层面，而缺乏实质直觉。检验力可以通过以下三种维度透彻理解：
* **几何与概率维度**：在给定的假设与决策阈值下，样本均值落在临界值右侧、使我们能够正确接受备择假设的曲线下面积。
* **业务现实类比**：检验力代表实验检测真实效应的能力强弱。例如调查最受欢迎的汽车品牌，仅观察 1 辆车几乎毫无统计功效，而观察 100 万辆车则具备极强的检测能力。
* **样本量联动机制**：当样本容量从 30 扩充到 100 时，标准误相应降低，均值分布曲线显著变窄且更集中。在保持 Alpha 为 5% 不变的情况下，更窄的分布使得临界值向左移动变小。更小的临界值叠加更小的标准误，大幅压缩了备择假设曲线落在临界值左侧的面积（Beta），从而使检验力实现几何级提升。

<details>
<summary>Original English</summary>

With the introduction of the null hypothesis, alpha, and the critical value, let's ready to make discovery by having an alternative hypothesis. When we talk about the alternative hypothesis, there is another important concept that textbook do not talk about very much and it can cause a lot of confusions. That is, we have infinitely many alternative hypotheses. Alternative hypothesis is theoretical construct, it's not real. For example, I plotted a lot of alternative hypothesis on this graph given any observation, each of them are likely to be true given certain probability. We will clear this concept of why we can talk about only one alternative hypothesis in the world of infinitely many alternative hypotheses when we talk about MDE. Right now, pay attention to my language, for the sake of simplicity, let's just look at one particular alternative hypothesis with the underlying distribution of mean equals 0.5 and standard deviation equals 1. We show the alternative hypothesis in red on this chart.

With the introduction of this particular alternative hypothesis, we can modify our decision rule. For our sample of 30, if the observed mean is above 0.3, Then we reject the null hypothesis and accept this particular alternative hypothesis. If the observed mean is below 0.3, we accept the null hypothesis and reject the alternative hypothesis. If the alternative hypothesis is the truth, Then we made an error when we reject the alternative hypothesis and we can calculate the probability of this error. This error is called the type 2 error. It is when we falsely reject the alternative hypothesis when the alternative hypothesis is true. Beta is the probability of making type 2 error. This is a slightly confusing part, but it's important. If I move the alternative hypothesis, if I have a different alternative hypothesis, my beta would change. Beta fundamentally really speaks to the probability of rejecting a particular alternative hypothesis. And only by combining with other conditions, rejecting the alternative hypothesis implies accepting the null hypothesis.

As you see, there are three things that can impact beta, the standard error of the alternative hypothesis, the mean of the alternative hypothesis, and how we choose the critical value. We choose this critical value because we want 5 percent alpha, which corresponds to a particular beta given a particular alternative hypothesis. If we set up the alternative hypothesis to be conservative, Beta is big. If we set up the alternative hypothesis to be extreme, beta is small. We are very close to talking about the tradeoff between discovery and mistake. With that, we're ready to talk about power, which is the central topic of statistical testing.

The textbook definition of power is 1 - beta, then many people stop here, but you may wonder, why? What does 1 minus beta mean? What does power mean? We should ask this question because an intuitive understanding of power is fundamental to everything. So let's actually explain power in three different ways. From this graph, 1 minus beta is power. It is the probability of accepting this particular alternative hypothesis given our assumptions and our decision rule. The second way is let's understand with an example. Power is actually an intuitive concept. It speaks to how much power we have in detecting a true effect. Let's use a real world example of, uh, trying to determine the most popular car manufacturer. If I observe one car and one brand, my observation is not very powerful. If I observe a million different cars, my observation is very powerful. In short, a powerful test means I have a higher chance of detecting a true effect.

And the third way, let's actually combine this definition of power and the intuitive example of more sample leads to more power, and visualize them on the chart. Let's change the sample size from 30 to 100. When we do that, the standard error got smaller, so the distribution got narrower. Suppose we are okay with alpha being 5%, the 5 percent alpha now corresponds to a smaller critical value. The smaller critical value plus the smaller standard error gives us much more power, which means,  for the same alternative hypothesis. Now we have much less chance of making a type two error of falsely rejecting it. So we have a lot more power to detect this alternative hypothesis. So hopefully by now, I made the concept of the alternative hypothesis beta and power clear.

</details>

### 最小可检测效应（MDE）与工业级实验设计的底层逻辑

在明确了检验力与样本量的作用机制后，便可彻底解开“为何能在无穷备择假设中锁定单一目标”的疑问，由此引出实验设计的关键基准——**最小可检测效应**（Minimum Detectable Effect, MDE: 在给定的统计显著性水平与检验力约束下，实验能够可靠识别出的最小真实效应幅度）。在样本量为 30 的实验中，当备择假设均值为 0.5 时，对应的 Beta 仅为 14%（即检验力高达 86%）；若我们将目标检验力调整为工业标准的 80%（对应容忍 Beta 为 20%），则可以向左寻找一个更为保守的备择假设。经计算，当备择假设均值降至 0.45 时，Beta 恰好达到 20%。由于在统计检验中我们期望获得尽可能高的检验力，因此任何均值位于 0.45 右侧的备择假设，都将拥有大于 80% 的检验力与更低的 Beta。换言之，0.45 就是在当前设定下我们能够以不低于 80% 功效检测出来的效应下限，这正是 MDE 的严格定义。

进一步观察 MDE 与样本量之间的动态博弈：当我们将样本容量由 30 提升至 100，并固定显著性水平（Alpha = 5%）与容忍误差（Beta = 20%）时，样本均值的标准误随之下降，正态分布曲线收窄。由于 Alpha 维持 5%，临界值向左收缩；在 Beta 同样锁定在 20% 的条件下，系统所要求的备择假设均值（即 MDE）由原来的 0.45 大幅降低至 0.25。这一现象揭示了 A/B 测试中最为核心的工程定律：**样本量增大，最小可检测效应（MDE）单调递减**。
* 样本量越充裕，实验越能精准捕捉到微小的业务提升指标；
* 若业务迭代带来的实际提升幅度足够显著，则无需依赖庞大的流量样本，中小规模样本同样能可靠验证假设。这意味着即使缺乏海量用户基础的中小企业，只要策略效应足够明显，A/B 测试依然能够发挥极具统计信度的决策价值。

深刻理解统计检验力是掌握现代在线受控实验的基石。工业界中诸如 **CUPED**（Controlled-experiment Using Pre-Experiment Data: 利用实验前数据构建协变量以缩减指标方差的高级统计技术）等方差缩减手段，其本质均是通过降低标准差来间接放大统计检验力；而在连续监控实验中采用**序列检验**（Sequential Testing: 允许在数据收集过程中多次进行假设检验且严格控制总体错误率的方法），也是为了避免在低检验力状态下过早下结论而导致假阳性与错误决策。归根结底，实验迭代速度、流量规模与预期检测效应量之间的永恒权衡，全部统一在以统计功效为核心的理论体系之中。

<details>
<summary>Original English</summary>

And finally, we are ready to talk about the Minimum Detectable Effect, or MDE. And as promised, we'll explain the concept of why we talk about one particular alternative hypothesis in the world of this infinitely many alternative hypothesis. So let's add the red dotted line to represent the mean of our alternative hypothesis and when the mean is 0.5, it corresponds to a beta of 14 percent or a power of 86%. What if for the same sample we want our power to be 20%? We go to a different alternative hypothesis. Remember, all of them are theoretical construct, so I can choose anyone. I discovered when the mean of our alternative hypothesis is 0.45, it corresponds to a beta of 20%. That is a more conservative alternative hypothesis. So we have more chance of making type two error.

Now comes the concept of the minimum detectable effect. Remember, in statistical testing, we almost always want more power. More power means we have a higher chance of detecting a true effect. So any alternative hypothesis to the right of this particular one is a good alternative hypothesis. It is an alternative hypothesis with less beta and more power. So the minimum detectable effect is given our assumptions of the underlying distribution, given our null hypothesis, given an alpha, so we can determine the critical value. And given a beta, so we know how much power we need at least, what is the minimum value of the mean of the alternative hypothesis that we can detect? Any alternative hypothesis above this minimum, we can also detect with even more power. That is the definition of MDE.

While the concept is still fresh, let's see how MDE changed with sample size to tie all the concepts together one more time. So we changed our sample from 30 to 100 again. And this time, we fixed both alpha and beta. Again, when the sample size increase our standard error decrease, the distribution of sample means gets narrower, gets more accurate.Same as before, if we tolerate the same level of alpha being 5%, we get a smaller critical value. Now, if we hold beta constant at 20%, our MDE decreases as a result. When we increase our sample size from 30 to 100, our MDE decreased from 0.45 to 0.25. That is the other key takeaway from this video. When your sample size increase, your MDE decrease. That is such an important takeaway in statistical testing. More sample means we can detect a smaller effect, but if our effect is bigger, we don't require a large sample to detect such effect. So even for companies without a huge sample size, if their treatment effect is large enough, A B testing can reliably detect that.

Hope I made everything clear from the null hypothesis, the alternative hypothesis to MDE and all the concepts in below. I also elaborated two important but under discussed concepts, standard deviation versus standard error,  and the infinitely many alternative hypothesis. The reason I spent so much time in talking about power, because almost everything in A B testing is indirectly or directly related to power. For example, variance reduction techniques such as CUPED. In this video, we fix standard deviation to be one, but, in reality, standard deviation can be different and can be reduced by different techniques, which can increase power. Sequential testing, why an underpowered test can lead to false discovery and bad decisions. Not to mention the everlasting contest between speed of the experiment, scale, the sample size of the experiment, and how much effect we expect to detect from the experiment. Those are deep, important, and valuable concepts in the practical use of A B testing. Of course, I will make a lot of videos in the future to talk about these concepts one by one. But all of that builds on the foundation of a solid understanding of statistical power. So, hope this episode is useful to you. Stay tuned if you want to see more content like this. See you next time.

</details>