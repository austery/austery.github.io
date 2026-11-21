---
author: AI Engineer
date: '2026-10-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mMw3arwQsL0
speaker: AI Engineer
tags:
  - ai-safety
  - system-evaluation
  - risk-management
  - failure-mode
  - stress-testing
title: 1368起AI事故的启示：如何构建系统级与风险导向的评估体系
summary: 来自纽约人寿的Vishal Srivastava和Tanmay Shah基于公开的AI事故数据库分析了大量失败案例。他们提出，不能仅评估模型的技术强度，而应从技术、部署控制和业务影响三个维度（共13个子维度）进行系统级评估，并倡导采用证伪主义的'构建-击穿-修复'循环进行风险驱动测试。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Peter Wason
companies_orgs:
  - New York Life
products_models: []
media_books: []
status: evergreen
---
### AI失败案例激增与三维调查框架

**Vishal**: 我研究的很大一部分就是审视AI的失败案例、进行调查并从中吸取教训。坐在我身旁的是Tanmay Shah。

<details>
<summary>Original English</summary>

**Vishal**: A big part of my research is looking into AI failures, investigating it, and then learning from it. And joining me is Tanmay Shah.

</details>

**Tanmay Shah**: 大家好。我是Tanmay Shah，一名高级量化建模师兼AI研究员。这是我第二次来这里，非常高兴能再次回来。接下来我把时间交给Vishal来开启我们的演讲。

<details>
<summary>Original English</summary>

**Tanmay Shah**: Yeah, hi everyone. I'm Tanmay Shah. I'm a senior quantitative modeler and an AI researcher. This is my second time here, so it's great to be back. So, I will hand it over to Vishal to get us a started.

</details>

**Vishal**: 我们研究了AI事故数据库（AI Incident Database），这是一个公开的AI事故数据库。我们查阅了其中的AI失败案例，并提出了一个简单的问题：这些失败案例对于应该如何评估AI系统给我们带来了什么启示？我们能否将这些经验教训应用到系统级的评估中？

首先我们看到的是，AI失败案例正呈指数级增长。如果你看过去四年的AI失败案例，特别是在基础模型时代，你会发现这种增长几乎是垂直跃升的。

我们许多人都觉得，企业中拥有的AI用例数量远远超出了我们逐一进行人工审查的能力。因此，我们的观点是，我们需要一种结构化的方法来调查这些AI失败。为了做到这一点，我们主要从三个维度来审视AI的失败：

第一个维度是开发阶段，即开发模型和/或AI系统的时候。这可能是与数据质量、工具架构或系统设计相关的问题。在开发阶段中的任何这些环节都可能出问题，一旦发生，这些错误就会传播到下一个维度，即部署阶段。

现在，即使模型或系统存在某些设计缺陷问题，但如果你在部署中拥有充分的控制措施，这些错误就可以被遏制住。这就是为什么去了解我们在部署中有哪些控制措施、以及我们能否遏制这些失败不让其从部署生产平台渗透到最终阶段非常重要的原因。而最终阶段，就是从商业角度来看AI系统被使用的情境。

它可能导致声誉风险，可能导致法律或财务风险，而所有这些业务情境对于使用AI系统的环境而言都至关重要。我们所主张、所提出的是：单凭模型或模型的技术强度仅仅是整个系统的一部分，我们必须全局、整体地看待这个系统。

<details>
<summary>Original English</summary>

**Vishal**: So, we looked at AI incident database. It's a publicly available AI incident database, and we looked at the AI failures and asked one simple question, what these failures teach us about how this is how the AI system should be evaluated, and if we can apply those learnings to system level evaluation.

So, the first thing that we see is that AI failures have been increasing exponentially. And if you look at the last four years of AI failures, particularly in the foundational model era, you see that the jump is almost vertical.

And many of us feel that the number of AI use cases that we have in enterprises, they they are much larger than our capacity to review them each one by one. So, what we argue is that we need a structured way to investigate these AI failures.

And to do that, we look at the AI failures essentially into three dimensions. The first dimension is the development stage, when the model and or the AI system is developed. So, it could be issues with respect to data quality or tool architecture or system design. Any of these things during the development phase can can break and once it happens, then those errors can be propagated to the next dimension, which is the deployment phase.

Now, even if the model or the system has some faulty design issues, but if you have sufficient controls in deployment, those errors can be contained. And that is why it is very important to kind of understand what kind of controls do we have in deployment and whether we can contain those failures from reaching from deployment production platform to the final stage, which is the context in which the AI system is being used from a business standpoint.

It could lead to reputational risk. It could lead to legal or financial risk and all those business context really matters for the AI system in which it is being used. And what we say what we propose is that the model alone or the technical strength of the model is just one part of the system. We have to look at the system holistically.

</details>

### 13个子维度与危害关联度分析

**Vishal**: 在定义了这三个核心维度之后——即系统应该具备强度或反过来说系统可能崩溃的“技术强度”；第二个维度，我们如何确保“部署控制”到位；第三个，AI系统所被使用的“业务情境”——我们将每个核心维度细分成了若干子维度。

从技术强度的角度来看，有六个主要子维度可能会影响AI系统的技术强度：
首先可能与我们用来构建AI系统的**数据质量**有关；
系统是否针对其理应完成的任务进行了合理的**系统设计**；
AI系统的**预测有效性**或输出结果分析如何，该系统的表现是否符合我们的预期；
可能包含相关的**公平性**检查；
**故障模式**本质上是审视系统在何时、何地、以何种方式以及对谁会发生故障，基本上是绘制出系统的所有故障模式；
最后，我们是否能向监管机构或其他机构解释其决策，即**可解释性**，以便我们知道系统是如何得出其决策的。这六个子维度构成了AI系统技术强度的核心部分。

接下来的四个子维度主要是看我们如何使用该模型：
我们赋予了AI什么样的权限？AI只是为了向我们提供信息，还是由它代表我们采取行动？我们赋予了AI怎样的**决策权限**？
第二点，**人工介入**（Human Mediation）。人在回路（Human in the loop）过程的有效性如何？这非常重要；
第三点，**暴露控制**（Exposure Control）。究竟是谁在使用这个系统？是内部员工使用，以便他们能发现错误并遏制住它；还是把它直接暴露在真实环境中的外部客户面前，导致任何微小问题都会迅速扩散？
最后，我们拥有什么样的**监控**控制手段，以便在生产环境中看到问题时能及时发现并予以遏制。

最后，在财务或业务影响阶段，我们看到了这三个核心子维度：
如果出现错误，会造成什么样的**财务影响**？
可能带来哪些**法律后果**？
以及会有多少用户受到波及？也就是最后一个——**受影响规模**（Scale）子维度。

我们将这套体系视为一个由13个维度和3个核心问题组成的框架。

一旦我们定义了这13个子维度，并对AI事故进行回顾性分析，我们发现利用这13个子维度几乎可以覆盖98%的AI失败案例。这意味着AI失败与这些维度中的某些维度相关联，有些情况下涉及多个维度，有些情况下涉及少数几个维度，但这些维度都参与其中。所以，AI失败是有结构规律的，我们需要绘制出它，并根据这些子维度采取相应行动。

正如我所提到的，这些故障子维度有些会在故障中同时出现。也就是说，当某个具体的失败发生时，可能会有多个环节同时出错。我们发现，在调查过的每个AI事故案例中，平均会存在六个故障子维度。

现在我们脑海中会浮现一个问题：是否所有的子维度都是同等重要的，还是其中一些比另一些更重要？答案是，某些子维度确实比其他子维度更为关键。

在图表中，Y轴表示当这些子维度出现时与造成危害的关联度；X轴是这些子维度出现的频率。我们在图表的左上方看到的是像人工介入（或人在回路的有效性）、危害检测（即我们是否具备到位的监控控制）等子维度。而在X轴方向上，我们看到像受影响规模和系统设计这样的维度，虽然它们在许多案例中都有出现，但它们与危害的关联度并没有前面提到的那些子维度那么高。

因此，当我们真正审视AI系统时，其中的一些子维度可能是极其关键的。我们需要根据造成危害的潜在严重性来优先排列这些子维度，然后为这些子维度的排查分配适当的资源，而不是把所有故障子维度都同等地看待。

当我们将这些子维度归类组合在一起时，我们发现：我们在部署环节中的控制措施与危害的关联最为紧密，其次是业务影响，最后才是技术层面的故障。

这张图表本质上告诉我们，一旦我们为高风险系统做好了部署控制，相比仅仅关注单一的技术故障，这能在更大程度上确保我们提前防范失败。因此，所有这些子维度固然都重要，但部署控制要重要得多。

在接下来的阶段中，我们设计了一个严重度等级（Materiality Scale）。也就是说，如果我们能够了解哪些AI用例相较于其他用例具有更高的风险，我们就可以根据重要性/严重度对这些AI用例进行优先级排序，因为严重度与这些AI用例相关的危害直接呈序数排列。这意味着，如果我们知道哪些AI用例的重大风险更高，我们就可以将更多资源分配给那些高严重度的AI用例，而不是同等分配给那些可能并不那么重大的用例。

说到这里，我把时间交给Tanmay，由他来解释我们如何利用这些经验教训来构建系统级评估。

<details>
<summary>Original English</summary>

**Vishal**: So, after defining those three core dimensions, the technical strength where the system should be strong or in opposite way where the system can break, the second dimension is how do we ensure that the deployment controls are in place? And third, the business context the AI system is being used. We divide each of these core dimensions into several sub dimensions.

So, in the from the technical strength point, right? There could be six major sub dimensions which could be affecting the technical strength of the AI system. It could be first related with the data quality that we use for to build the AI system. How the system has been designed for the appropriate task that it is supposed to accomplish. How is the predictive validity or outcome analysis of the out of of the AI system? Does that system perform as we intend?

Um there could be fairness related um checks.

Um failure modes essentially looks at where when, how, and for whom the uh system can break. Uh so, basically mapping out all the failure modes of the system. And finally, can we explain for uh explain the decisions for the regulators or other bodies uh so that we know how the system is arriving at its decision. So, these six sub dimensions are essentially part of the technical strength of the AI system.

The next four are essentially looking at how we are using the model. Um what kind of authorities we have given to the AI, right? Is the AI for informing us or it it is out there to act on our behalf. What kind of decision authority are we associating with respect to AI? Uh second one, human mediation. Um how effective is human in the loop process is, right?

That's really important. The third one, exposure control. Who's actually using the uh system? Is it internal employees so that they see the error and they can contain it or it is exposed to the out there in the wild external customers so that any small issue can really propagate fast. And finally, what kind of monitoring uh controls that we have so that we see some uh issues in production and we detect it and we can contain it.

Finally, in the financial or the business impact phase, we see these three core sub-dimensions. What kind of financial impact it would make if there is an error? There could be legal consequences and how many users would get affected? That's the the last one, the scale sub-dimension.

So, we we we look at this this as one framework which has 13 dimensions and three core questions as we explained.

Once we define these 13 sub-dimensions and look back at AI incident retrospectively, we find that using these 13 sub-dimensions, almost 98% of AI failures can be covered. Meaning that AI failures are are associated with some of these dimensions, in some cases multiple of these dimensions, and in some cases few of these dimensions. But, these dimensions are involved. So, failure AI failures have structures. We need to map it and we need to act accordingly according to these sub-dimensions.

Now, as I mentioned that some of these failure sub-dimensions can be present in these failures simultaneously. Meaning that when something goes wrong with respect to a particular failure, there may be multiple things going wrong. What we find is that on average, there are six failure sub-dimensions that can be present in each of these AI incident failures that we we we have investigated.

Now, the question comes to our mind is that are all of these sub-dimensions are equal or some are more important than others. And the answer is that some of the sub-dimensions can be more critical than others. And what I'm showing you here in the in the plot on the Y-axis is the association to harm when these sub-dimensions are present. And on X-axis, we have the frequency of these sub-dimensions being present. What we see on the left upper side of the plot, sub-dimensions like human mediations or effectiveness of human in the loop, harm detection, meaning that whether we have monitoring control in place. On on X-axis, we see things like scale and system design. Although they are present in many cases, but they are not associated so much with harm as some of the some of some of the earlier sub-dimensions that I have mentioned.

So, when we are really looking at the AI systems, some of these sub-dimensions can be really critical. So, we need to prioritize these sub-dimensions by the potential of making harm, and then allocate appropriate resources to the to the investigation of these sub-dimensions rather than looking at all the failure sub-dimensions equally.

And when we club the when we group these sub-dimensions together, we see that controls that we have in deployment are more critically associated with harm, followed by the business impact, and followed by the technical failure. So, this plot is essentially telling us that once once we have deployment controls taken care of for the high-risk system, that gives us some level of assurance that we can take care of the failures in in advance in contrast to just looking at the technical failure alone. So, all these sub-dimensions are important, but deployment controls are far more important.

And what in the next phase what we did was we we designed a materiality scale, meaning that if we can understand which AI use cases are more risky compared to some others, we can we can prioritize these AI use cases based on materiality because materiality directly rank orders with respect to the harm associated with this AI use cases. Meaning that we can spend suppose we know which AI cases are more more material then we can allocate more resources to much higher material AI use cases than compared to some other AI use cases which may not be as material.

With that, I would hand over to Tanmay who would explain how we can use those learnings to build system-level evals.

</details>

### 如何对Agent系统进行系统级评测

**Tanmay Shah**: 谢谢Vishal。

到目前为止，我们已经了解了这些失败案例带给我们的启示，现在就让我们运用这些经验来构建系统级的评估。

首先，我们把风险分解成了四个组成部分：
模型发生故障的频率有多高；
该故障是否会传递至实际决策；
故障是否未被发现；
以及后果有多严重。
在这种情况下，部署设置至关重要：系统拥有多大的权限？是否有人审核其输出？监控能否在造成危害之前捕获错误？因此，同一个模型根据部署方式的不同，可能会产生截然不同的风险。所以我们强调的是，如果风险取决于整个部署系统，那么我们的评估也必须覆盖整套部署设置。这就引出了下一个问题：

在Agent系统（Agentic System）中，我们应该测试什么？

你看，在传统机器学习中，我们已经知道如何对模型提出挑战。我们会检验它们的假设、输入数据以及压力状态下的行为。现在，当我们把这一原则扩展到整个部署系统时，就涉及诸如：检索是否返回了正确的信息？或者当工具调用失败时会发生什么？人工审核是否能发现错误？或者Agent是否保持在其权限或边界之内？系统最终能否恢复？所以，这里的底层逻辑保持不变，只是我们测试的边界变大了。

那么接下来的问题是：我们应该如何测试Agent系统？

在右边，是我们熟悉的传统机器学习。我们在保留测试集上测试模型，计算准确率（Accuracy）和AUC-ROC等指标，并利用这些证据来指导部署。但我们仍然需要检查这些指标背后的数据和假设。

而在左边，Agent系统带来了全新的复杂性。

部署系统具有许多可能的输入、工具响应和行动序列（即轨迹或rollout，随你怎么称呼）。因此，我们会测试选定的场景。有时，会由另一个AI Agent或AI裁判（AI Judge）来生成这些测试或对结果进行评判。但是，裁判本身可能会犯错，测试也可能会遗漏重要的故障。这正是我们需要检验评估器本身是否可靠、证据覆盖了哪些内容，以及它是否适用于我们实际部署的系统的地方。这就是为什么评估器本身也是我们所治理的系统的一部分。

现在我再把时间交给Vishal，由他来解释我们如何检验评估是否可靠，以及在评估不可靠时该怎么做。

<details>
<summary>Original English</summary>

**Tanmay Shah**: Thanks, Vishal.

Uh so, so far as we have seen what these failure teach us, so now let us use those lessons to build system-level evaluations.

So, first first of all, what we did is that we have decomposed risk into four components, which are how often the model fails, whether that failure reaches a real decision, whether it goes whether it goes uncaught, and how severe the consequences are. So, in this scenario, the deployment setup matters, how much authority does the system have, does someone review its output, can monitoring catch error before it causes harm? So, this same model can create different risk depending on how we deploy it. So, what we are saying is that if risk depends on the whole deployment system, our evaluation needs to cover that setup, too. So, that brings us to the next question.

What should we test in an agentic system?

So, see, in traditional machine learning, we already know how to challenge models. We test their assumptions, input data, and behavior under stress. Now, when we extend that discipline to the whole deployment system, then, like, does retrieval bring back the right information? Or what happens when a tool fails? Does human review catch mistake? Or does the agent stay within its permission or boundary? And can the system finally recover? So, here the logic stays the same. The boundary of what we test gets bigger.

So, now the question is, how should we test an agentic system?

So, on the right, we have the familiar traditional ML. We test a model on held-out data, calculate metrics like accuracy and AUC ROC, use those evidence to inform deployment. But, we still need to check the data and assumptions behind those metrics.

But, on the left-hand side, we have an agentic system which adds new complexity.

So, the deployment system, like, it has many possible inputs, tool responses, and action sequences, or trajectory, or rollout, whatever you dis- say. So, we test selected scenarios. Sometimes, another AI uh agent or AI judge generates those tests or judges the result. So, but that judge can make mistakes, and the test can miss important failures. So, this is where we need to check whether the evaluator is reliable, what the evidence covers, and whether it applies to the system we are actually deploying it. That's why the evaluator is the part of the system we govern. So, now I will hand it over to Vishal to explain how we can check whether an evaluation is reliable and what to do when it is not.

</details>

### 基于证伪主义的“构建-击穿-修复”评估循环

**Vishal**: 谢谢Tanmay。

我们已经看到了针对评估器以及整个AI系统的系统级评估。问题在于，我们到底应该如何去做？

当我回顾以往的一些研究时，尤其是在认知神经科学领域，我发现科学家Peter Wason提出了“确认偏误”（Confirmation Bias）这个术语。他做了一系列实验，就比如大家在这里看到的数字序列：2、4、6。他让人们预测下一个数字，大家绝大多数情况下都会预测8、10这样的偶数。但这些答案全错了，因为真正的规则其实是“任何递增的数字即可”。这证明了大多数人——在那个实验中有79%的受试者答错了——可能都带有某种确认偏误。

而正如我们所知，AI系统是在人类生成的数据上进行训练的。所以他提出：任何需要进行的评估都必须是去**证伪**，而不是去**证实**。这才是正确的途径。我们将这项研究中的启示应用到这里，提出评估系统必须是**故障驱动**（Failure-driven）的。

如果评估系统是故障驱动的，这意味着什么？这意味着你应该从审视你的系统主张（Claim）开始，测试它并试图打碎它（Break it），然后找出系统主张在何处被打破。接下来你该如何修复？要么不要让AI系统在出现故障的领域内运行，要么引入你有信心的配套支持系统。你反复迭代这个过程，直到达到所需的置信度水平。这本质上就是我们为任何评估系统提出的基于第一性原理的方法。

因此，你采用你的AI系统，执行这种“构建-击穿-修复”（Build-Break-Fix）循环，了解AI系统在最终产出方面在哪些区间是值得信任的；同时绘制出不确定区域和高风险区域——在这些区域你无法对系统的性能保持确信；绘制出完整的故障区域图，并根据可靠性和重要性对其进行路由。这意味着，特别是如果你将AI用于任何高风险评级系统，请确保你的AI仅用于你确信的区域。

讲到这里，我再把发言权交给Tanmay，他将把这种方法应用到一个真实的AI失败案例中。

<details>
<summary>Original English</summary>

**Vishal**: Thank you, Tanmay.

So, we have seen the system level evaluation for evaluator as well as you know, the whole AI system. The question is that how should we really

And when I was looking at some of the previous research, particularly in the area of cognitive neuroscience, what I found was the um this the scientist Peter Wason, he's the one who coined this term confirmation bias. And essentially what he did was he did a bunch of experiments, but essentially uh in this case here, the series that you see 2 4 6, right? He was asking people to predict the next number, and more often than not, they were predicting 8 10, like even numbers. But those answers was those answers were incorrect because essentially the correct number was any increasing number. Essentially proving that all humans, like most humans, um in this case it 79% of people tested wrong.

Um may have some sort of confirmation bias. And AI systems, as we know, uh are trained on human-generated data. So, what what he proposed was that any evaluation or any any evaluation that needs to be done has to falsify, not to confirm. And that that's the way to go about it. And we take that learning from his research and propose that eval system needs to be failure-driven.

So, if the eval systems are failure-driven, what would that mean? That would mean that you would start right from looking at your system claim and testing it and trying to break it and then identify where the system claims are breaking, right? And then what you do for fix? Either you uh don't let the AI system run in you know, in the in the in the territory where uh there are failures or you come up with uh supporting systems, right? Which you are confident of. And you keep doing it iteratively uh until you get um you to the to the level of confidence, right? This is essentially the first principles based approach that we propose for any evaluation system.

So, essentially you take take your AI systems, perform this build-break-fix loop, understand where the AI systems could be trusted in terms of its uh uh final outcomes, and also a map out uh the uncertain region and high-risk region where you can not be very sure of the system's performance, and you map out the entire failure region map and route it based on the reliability and materiality, meaning that particularly if you're using AI for any high-risk rated system, make sure that your AI is only being used for um the the the region that you're confident of.

And with this, I will hand over to Tanmay who who who who would apply this approach to a real uh AI failure case.

</details>

### 加航案例拆解与总结

**Tanmay Shah**: 好的，没问题。

让我们把这个框架具体化，看看狭隘的评估是如何遗漏现实世界中至关重要的故障的。我会快速讲一下背后的故事：

一名乘客因家中有人去世需要出行。他向一家航空公司的聊天机器人咨询优惠票价。聊天机器人告诉他，他可以先购买普通机票，并在出行后的90天内申请折扣。于是他听信了这一建议购买了机票，但航空公司后来拒绝了退款，因为其政策不允许这样的申请。最终，仲裁庭裁定航空公司承担责任。

通过这个例子，我们看到了一条清晰无比的失败链条：不正确的建议传递给了客户，客户据此采取行动，组织承担了后果。

如果我们应用“构建、击穿、修复、再次击穿”的方法，完全可以在部署之前很久就暴露出这个故障。在理想情况下，我们会从一个明确的需求开始，例如“给出的建议必须符合经批准的政策”。然后，我们用关于旅行后退款的问题向聊天机器人发起挑战。如果这些测试暴露了不正确的建议，我们就可以添加政策合规检查或人工升级机制。接着我们会再次进行测试，看看这些控制措施是否能在错误到达客户之前将其捕获。这就是我们在实践中的框架：必须定义主张、主动对其发起挑战，并利用证据指导变更和做出部署决策。

最后，我把时间交还给Vishal来整合所有内容并做总结。

<details>
<summary>Original English</summary>

**Tanmay Shah**: Okay, I sure. So, uh so, uh let's make this framework concrete and see how a narrow evaluation can miss failures uh that matters in the real world. So, I will quickly go through the story behind it. So, a customer needed to travel after a death in the family. He asked an Airlines chatbot about a discounted fare. The chatbot said he could buy a regular ticket and claim the discount afterwards within 90 days. So, he relied on that advice, but the airline later refused because its policy uh did not allow that request. Then finally, the tribunal held the airline responsible. So, through this example, we we are seeing the failure chain. So, it's crystal clear. So, incorrect advice reaches the customer, the customer acts on it, and the organization faces the consequences.

So, if we apply our build, break, fix, and break again approach, uh that could have exposed the failure way before the deployment. So, we Ideally, we would start with a clear requirement like advice must match the approved policy. Then we would challenge the chatbot with questions about refunds after travel. If those tests exposed incorrect advice, then we could add a policy check or human escalation. Then we would test again to see whether those controls caught the errors before it reached the customer. So, that's our framework in practice. We have to define the claim, actively challenge it, and use the evidence guide changes and make a deployment decision. So, finally, I will hand it over to Vishal to bring the pieces together and conclude.

</details>

**Vishal**: 这是我们的最后一张幻灯片。归结起来，我们的核心观点是：你的评估应该是基于风险的，而不是基于频率的。

你应该审视你的整个系统，然后将其拆解为核心组件，例如技术故障、部署控制和业务情境。接着使用某种尺度来评估你的AI用例的严重度，这可以是你公司自有的尺度，风险也可能会发生变化。一旦确定了之后，对AI用例实施系统级的压力测试。只有当你对该区域充满信心时，再做出部署决定；否则，代价可能会过于高昂。

我们最终想传递的信息是：**基于风险对整个AI系统进行评估，而不仅仅只评估其中的单一组件。**

非常感谢大家的时间与关注。大家可以在会后随时与我们联系交流，我们稍后非常乐意回答大家的任何问题。

<details>
<summary>Original English</summary>

**Vishal**: Um this is our final slide. So, essentially, what we are saying is that your evals should be risk-based um rather than frequency-based. You should look at your uh entire system and then break it into the core components like technical uh failure, deployment controls, and business context. And then assess your AI use cases materiality with some uh scale, uh and that could be your company specific scale and risk should that risk could change. And then once you have that, apply the system level stress testing on the AI use case. And then once you are confident about the region, then only make the deployment decision. Otherwise, it may be too expensive.

Our final takeaway message is evaluate the full AI system based on risk, not just one component.

Thank you so much for your time and attention. You can feel free to reach out to us outside. We'd be happy to take any questions later.

</details>

**[观众]**: [掌声]

<details>
<summary>Original English</summary>

>> [applause]

</details>