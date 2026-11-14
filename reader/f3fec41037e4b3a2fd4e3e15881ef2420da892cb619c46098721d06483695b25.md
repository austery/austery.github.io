---
author: AI Engineer
date: '2026-11-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-uBABM2AuFg
speaker: AI Engineer
tags:
  - ai-agent
  - llm-evaluation
  - model-guardrails
  - production-ai
title: 不要审批 AI 模型，要审批应用程序：Langfuse 的金融级评测与准入实践
summary: Langfuse 工程师分享了帮助排名前五的银行落地生产级 AI 智能体的经验。受监管行业更看重基于专有数据的内部应用表现而非公开基准。通过构建黄金数据集、结合代码工具与多维度评测（包含确定性规则与 LLM 评审），并由领域专家设定合规与风险准入门槛，团队将模型数值计算准确率由 60% 提升至 95%，成功建立应用级准入机制并大幅缩短合规评测周期。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Langfuse
  - ClickHouse
products_models: []
media_books: []
status: evergreen
---
### 金融等受监管行业为何不在意公开基准

我在 ClickHouse 旗下的 Langfuse 负责 AI 工程解决方案。我们是一个智能体可观测性和评测平台，很多用户都在使用我们的开源版本。今天我在这里想和大家分享我们与一家排名前五的银行合作的经历，帮助他们弄清楚在将 AI 应用程序发布到生产环境时，应该如何设置安全护栏，并确保在上线时运行恰当的评测。

<details>
<summary>Original English</summary>
[music]

>> Uh I'm leading AI engineering solutions at LangFuse uh by ClickHouse. And uh we are an a agent observability and e-boss platform that a lot of users use open source. And uh I'm here to talk to you about an experience that we had with one of a top five bank helping them getting through how they can put a safety uh guardrails whenever they were shipping AI applications into production. And uh to make sure that they are running with the e-proper e-vals on that.
</details>

我想首先分享从这个客户身上学到的一点：受监管行业并不一定在意公开基准。我知道每周只要有新模型发布，我们就会看到各种各样的跑分，比如 Opus 5 现在在多个维度上领跑基准，这当然很棒。这能告诉我们模型在技术能力层面到底擅长什么，而且有时这些测试使用的是公开数据集。但有时候，这并不意味着它能有效地转化为贵机构内部的数据和用例。特别是在金融服务领域，银行对他们的数据和用例非常敏感；而且在大多数情况下，他们倾向于认为那是他们的“独门秘诀”——包括他们构建自己模型和数据集的方式，以及不向公众暴露大量这些数据。

<details>
<summary>Original English</summary>
I I like to start with uh you know, something that we learned with the experience with this customer is that regulated industries they don't necessarily care about the public benchmarks. I know that every week uh when anytime a new model comes out um we see all the benchmarks, you know, uh Opus 5 is now leading the benchmarks in a in a multitude of dimensions and that's great. Um that tells us what the models are really good at in terms of like the technical capabilities and maybe using sometimes like open data sets that are out there. But sometimes that doesn't mean that it will translate effectively to internal data and use cases that you have in in your organization. Specifically around you know, financial services where banks are very very sensitive to the their data, their use cases and for the most part they like to believe that that's part of their secret sauce, the way that they you know, build their own models, build their own uh data sets and also not exposing a lot of that data to uh to the public.
</details>

### 审批应用程序，而非模型本身

所以这就是为什么我们需要找到一种方法，让金融服务机构、特别是这家银行能够表示：“听着，我们不一定在乎这个模型能做什么。我们真正关心的是，我们试图构建的这个应用程序到底能不能发布到生产环境中。”一个很好的例子就是他们当时想为投资银行家构建的 10-K 分析工具。每当财报电话会议发布时，他们希望确保自己的团队能够加速工作并利用好所有公开信息；一旦财报电话会议结束，他们就能对所有会议纪要等内容完成分析。然而，这并不是简单地拿过电话会议记录做个摘要就完事了，因为分析师拥有大量专业知识，对银行和公司的运作方式也有大量背景理解，而这些内容并不一定开箱即用地融入或训练在模型中。那么，你该如何将这些知识和背景融入到模型中呢？

<details>
<summary>Original English</summary>
Um so that's why we needed to figure out a way that the you know, financial services and this bank in particular that they can then say, "Look, we don't necessarily care what the model can do. What we care about is really whether this application that we're trying to build can ship into production. A good example would be like a 10K analyst that they were trying to build for their investment bankers. You know, every time an earnings call is is out there, they want to make sure that their teams can accelerate and get leverage from all the information that is out there and as soon as an earnings call is done, they can get an analysis on all the transcripts and all that. However, that is not just a simple task of just taking that the call transcript and just like summarizing it and what not because there's a lot of knowledge that the analyst has and a lot of context about how the bank and the firm operates that is not necessarily ingrained or trained in the models out of the box. So, how do then you bring that knowledge and that context into the model?
</details>

不仅如此，一旦你完成了这一步，你又如何能可靠地评测它给出的输出是正确的，并且能够通过你所设立的那些关卡？所以这又是我们学到的一个重要经验，他们直接告诉我们：“听着，我们在这里不认证模型。我们认证的是应用程序，对吧？它可以是 10-K 分析工具，也可以是投资分析工具等等。”

<details>
<summary>Original English</summary>
And then furthermore, once you've done that, how do then you reliably are able to evaluate that the output that is giving you are the the the correct ones and that you can kind of clear those gates that you have put in place. So, that was that was again a kind of a a big learning for us that they and they told us directly, "Look, we don't certify models here. We certify applications, right? So, it it could be a 10K analyst, it could be an investment analysis and what not."
</details>

### 金融级解决方案的三大硬性要求

从这次经历中得到的另一个经验是，在受监管行业、尤其是金融领域，构建解决方案有三大核心要求：

第一点，绝大多数情况下他们希望保留在**本地部署（on-premises）**。这可以是在他们自己的数据中心。事情又兜兜转转回到了原点，这挺有意思的——因为我们之前一直在做向云端迁移的工作，但现在由于 AI 的出现，以及我们喂给这些模型的信息极其敏感，尤其是银行，正在重新思考并重新利用他们现有的许多数据中心，实际重新搭建起来，并部署 GPU 基础设施在本地运行模型，就是因为他们在这些模型上处理的数据具有高度敏感性。

第二个要求是它必须是**受管制的（gated）**，出于显而易见的原因不能直接连到互联网上。他们甚至不希望出现任何模型提供商会拿他们的数据进行训练的可能，即便有零数据保留等各种保证。银行对此非常敏感，他们希望确保一切都在自己的掌控之中；有时有些银行甚至设有专门的研究部门，投入时间和精力让博士们训练并微调自己的模型。

第三个方面就是**部署环境必须是物理隔离（air-gapped）的**，对吧？这样只有需要看到该数据的人才能看到，且完全在他们的基础设施内部。这是非常关键的。

<details>
<summary>Original English</summary>
The other learning from this experience is that in regulated industries and in finance in particular, there are three main requirements when it comes to building the solutions. The first one that more more often than not, they wanted to stay on their own premises. Um and this could be either their own data centers because it's it's funny how things are kind of coming back to to to center because we have done we have been doing all this movement into the cloud, but now because of AI and how sensitive the information that we're feeding these models is, then especially banks are rethinking and repurposing a lot of their data centers that they had and actually standing it up again and and kind of standing up GPU infrastructure to run models locally because of the sensitivity of the data that they are dealing with on these models. The other thing is the other requirements that it has to be gated. It cannot be just going out to the internet obvious for obvious reasons. They don't want to have even the the appearance that some model provider will train on their data even if there is like zero data retention and all and all these, you know, guarantees. But banks are very sensitive to that and they want to make sure that that stays within their control and sometimes you have even banks that actually have kind of research divisions that actually spend time and have PhDs training their own models and fine-tuning them and all that. And the third aspect is with all of this is that the deployment needs to be air-gapped, right? So that only the people that needs to see that data and it's within their infrastructure. That is very very critical.
</details>

### 评测体系与准入机制的建立

另一件事是，当我们和他们沟通时，情况就像是：“好的，现在你们有了所有这些平台，我们有了所有这些模型，但接下来我们需要证明：第一，这个应用程序确实按我们期望的方式运行；第二，它切实符合我们作为受监管行业所面临的合规要求；第三，我们的用户不会跑来抱怨它不好用。”因为如果不好用，就会出现没人愿意采用的局面，进而产生不满，对使用 AI 解决方案产生负面情绪。因此，我们需要找到一种方法，帮助他们建立一套框架和方法论，以便在应用程序或 AI 智能体的配置发生任何更改时，能够给出一个通过/失败（pass/fail）的认可印章。这些更改可能是系统提示词，可能是他们使用的模型，或者是一个新工具；但是，如何基于我们给他们带来的这些变更，判断“好的，这已经准备好投入生产了，还是没有准备好”？

<details>
<summary>Original English</summary>
The The other thing is when when we were talking to them it's like, "Okay, now you have all these platform, we have all these models, but then we need to prove that the application is actually working to the way that we want. One, second, that is actually meeting the compliance requirements that we have as a regulated industry. And third, that our users are not going to come to us complaining that is not usable because then, you know, it becomes a situation where you don't get user adoption and then there's a dissatisfaction and a bad sentiment about using AI-enabled solutions. So we needed to find a way to help them come up with a framework and a methodology for them to have like a stamp of approval pass fail if an application or an AI agent had any change on their configuration. That could be the system prompt, that could be the model that they're using, a new tool, but then how do I give that, "Okay, this is ready to go into production or not based on on these changes that we have given them?"
</details>

从极高层次来看，这在机制上是如何运作的呢？首先，我们需要构建一个**黄金数据集（golden data set）**。这是最基础的一步，相当于锚点。好消息是，许多这类银行通常已经拥有了他们想要用来测试的黄金数据集；但有时缺少的是，他们该如何将针对该数据集的测试用例真正工程化落地。但在我看来，这通常就是基石。如果你有软件工程背景，我喜欢这样理解：这些就是你的测试用例。你绝不可能在没有通过 QA 的情况下把任何东西推向生产环境，对吧？这里也是同样的原则。

一旦你运行并落地了这套流程，你就会生成一堆调用追踪（traces）。这些 traces 就是模型根据该数据集进行评测——抱歉，是模型评测的依据证据。你的 trace 中包含了这些证据。最后，以 trace 作为这种凭据，你就可以生成评分，从而在选定的各个不同维度上给出通过/失败的结果。

<details>
<summary>Original English</summary>
And then if we go like very high-level, how does that work mechanically? Right? The first thing that we need is to build a golden data set. That's the first thing. That's kind of the anchor. Um a lot of this good good news is a lot of these banks they typically already have a golden data set that they want to test against. But sometimes what is missing is how they can operationalize the testing of the test cases against that data set. But that's to me typically is the anchor. The way that I like to think about this if you're coming from a software engineering background is is these are your test cases, right? You will never push anything into production without passing it through QA, right? So this is the same principle. Then once you run this um and and you operationalize it, you're going to generate a bunch of traces. And the traces are the evidence of what the model was trained on. Or sorry, what the model was evaluated on, right? Against this data set. So you have that evidence on the trace. And then at the end with the trace as the as the as the kind of the uh as that, you know, evidence that you have, you can then generate the scores that are going to give you the pass fail across different dimensions that you uh select.
</details>

### 引入确定性工具化解大模型数学短板

当我们与这位客户刚开始这段历程时，我们首先找了一堆模型进行测试——具备不同智能水平的大小模型。我们注意到一件很有趣的事情。这是一个特别突出的两组数字的例子：

第一个数字是 **97% 的依据性（groundedness）**。这意味着该模型非常擅长从内部来源提取信息，并将回答建立在银行现有的真实数据之上。非常好，97% 达到了及格线，表现惊人。但紧接着，当涉及到给出精确数字时，模型就开始掉链子了。因为归根结底，大语言模型本身并不擅长数学，它们本质上只是下一个词元的预测器。结果就是，尽管回答建立在来自银行的真实信息之上，但每当需要提供财务数据或进行简单的数学计算时，模型就会失败。我马上会向大家展示我们是如何解决这一问题的。

<details>
<summary>Original English</summary>
When we started out this journey with this customer, it was we first started with a couple of with a bunch of models, um a small large models with different levels of intelligence. And we noticed something interesting, right? So this one is is a particular example of two numbers that stood out for us. The The first one, 97% in groundness, is that this model was really good at extracting information from, you know, internal sources and grounding the responses on actual data that the bank had. Perfect. 97% That is a passing bar. Amazing. But then when it came down to give, you know, a accurate numbers, then the number was trip the model was tripping up. Because again, LLMs inherently are not great at math. They're just next token predictors. And then what happened was that even though it was grounded the responses on actual information from the bank, whenever it needed to give financial numbers or just do simple math, the model was failing. And then, I'll show you in a minute how we were able to go about that.
</details>

这又把我们引回了我前面说过的那句话：他们不审批模型，他们审批的是应用程序。那么，他们该如何围绕这个模型建立测试脚手架（harness）或控制机制，从而确保即便明天更换了模型，应用程序的质量依然能保持一致？

现在我们展开来看看帮他们建立的具体流程：从左侧的黄金数据集开始，接着进入智能体内部。智能体将执行一系列任务：它包含规划阶段，会从官方权威数据源检索数据；然后大家看用蓝圈圈出来的那个小框，它要去执行计算。

在这种情况下我们所做的，是针对模型能力不足的领域为它提供了一个工具。针对它表现不佳、只有 60% 得分的部分，我们当时认为：“模型其实不需要独立完成这项任务。我们可以直接给它一个工具，因为数学计算是确定性的，结果始终如一。这样我们就能提高模型的准确性。”

<details>
<summary>Original English</summary>
And this leads us to then, again, what I said before, that they don't approve models. They approve applications. So, how they can put a harness or controls around this model, so irrespective of if tomorrow I swap a model, then the quality of my application will still remain the same. Now, we're expanding into kind of the process that we help them establish. You're starting from the left with the golden data set, then you go into the inside of the agent. The agent is going to do a bunch of tasks. It's going to have a planning phase. It's going to retrieve data from your official official sources. And then, you see the little box that is is circled in blue, he's going to calculate. In this case, what we did, we gave the model a tool for those areas where the model was com- coming up short, right? The 60% where it was not scoring well, then we said, "You know what? This is a task that the model doesn't need to do on its own. We can just give it a tool because math, you know, is deterministic. It's it's going to be the same all the time. And then, we can improve the the accuracy of the model."
</details>

### 多维度评测与单票否决门槛

但与此同时，如果你注意看我们设定的所有维度，我们是在多个维度上对应用程序进行评测，而绝非单一维度。我们不会说“因为平均值都在 90% 以上，所以它就算通过了”。实际情况并非如此。在准确性、监管合规性等各个不同类别上，你可能会设立不同程度的等级或阈值。最后，才是你定义准入关卡的地方。正如大家所见，任何根据设定的阈值未能通过关卡的内容，都不得晋级推入生产环境。

<details>
<summary>Original English</summary>
But at the same time, if you notice all the dimensions that we have, we are evaluating the application against a multitude of dimensions, not just one. We're not going to say, "Well, because everything in the average is giving me above 90%, then it's going to pass." That might not be the case. You might have different degrees or thresholds for the different categories that you have here in terms of the accuracy, regulatory compliance, and whatnot. And then, at the end is where you define your gate. You see, not anything that doesn't clear the gate based on your thresholds, doesn't get promoted into production.
</details>

这只是一段代码片段，最后我会附上代码仓库和博客文章链接，以便大家深入了解我们在这里完成的具体工作。但本质上，你必须构建属于自己的基准，而不是依赖市面上的公开基准。正如我之前所讲，实现这一目标的第一件事就是构建数据集。这是一个典型数据集结构的例子：它们是键值对形式，包含输入、预期输出以及一些元数据，用于评测智能体在质量、行为以及返回给你的响应方面的整体表现。

<details>
<summary>Original English</summary>
This is just a a snippet of the code and and at the end I'll link to the repo and to the blog post so you can read more in depth about the work that we did here, but it's effectively you want to build your own benchmark instead of relying on the public ones that are available there. And the the first thing you need to do that is to build the data set like I said before. This is an example of what a typical data set would look like. It's They are key pairs. You have inputs, expected outputs, and some metadata that you are then using to evaluate how the agent is performing both in terms of quality, behavior, and the responses that it's giving you as well.
</details>

这就是在我们对某次智能体运行完成打分或评测后的展示界面。大家会注意到我圈出了“calculate”工具调用，因为在这个案例中，正是通过提供这个工具，我们才能把模型在数值准确性上的得分从 60% 一路拉升到 95% 左右。只要有需要计算的数字，直接运行这小段 Python 代码即可。通过这种方式，就能改善交付给客户的最终结果。

<details>
<summary>Original English</summary>
This is how it looks after we have a scored or evaluated one agent run. And you notice that I circled the calculate tool call because in this case now, this is how we were able to get the model from 60% in numerical accuracy all the way down to like 95% because we gave it a tool. Anytime there's a number that needs to be calculated, just use this little Python code and off you go. In In that way, you can improve the the results that you're giving back to your to your customers.
</details>

流程中的另一步是关于评分：如何对我前面提到的每个维度进行打分？我们提供了几种实现方式：

你可以采用**确定性评分（deterministic scores）**。顾名思义，这非常简单，不是基于大语言模型的。你只需要运行一段代码，对于相同的输入，它始终会生成相同的输出。我们注意到，随着这些解决方案变得愈发复杂，你需要将确定性与非确定性的评分器及评测机制结合起来；如果百分之百完全依赖 LLM 裁判，是行不通的。

第二种是**路径评估（the path）**：你还需要弄清楚智能体是否采取了正确的路线或步骤来得出答案。因为有时候答案看起来或许合格、完整或半完整，但它得出答案的过程可能并不恰当，甚至遗漏了必要步骤。因此你也可以对此进行评测。

第三种则是**将 LLM 用作裁判（LLM as a judge）**，去评判答案中一些偏定性的层面。

<details>
<summary>Original English</summary>
The other step on on this is about scoring. How do you score each of the dimensions that I was telling you before? We have a couple of ways that you can do this. You can have deterministic scores that again, like the name implies, is, you know, very very simple. This is This is not LLM based. You just have a code that is running and it's for the same inputs, it's going to generate the same outputs all the time. And what we've noticed is with these solutions as they get more complicated, you need a blend of scores and evaluators that are deterministic and non-deterministic because otherwise relying 100% just on LLM judges is not going to cut it. Um and then this the second one, the path, is you also want to figure out if the agent is taking the right, you know, route or path to get to the answer. Because it might be that the answer might look okay or complete uh or semi-complete, but then maybe the route it took to get there, it might not be the appropriate one. Might be missing steps. So, you also can evaluate that. And the third one how you use an LLM as a judge to judge some of the more qualitative aspects of that answer.
</details>

通过完成所有这些工作，我们让原本表现不合格、得分只有 60% 的小模型达到了 90% 以上；并通过引入该工具以及在顶层搭建这一评测框架，跨多个不同维度测量智能体的准确性和质量，从而通过了该银行针对此特定用例设立的 85% 准入门槛。这一点非常关键，因为现在你不仅能够回溯并展示实际衡量智能体质量的证据，更重要的是，你能够将这些结果与智能体所做的更改关联起来——包括配置、系统提示词、模型以及所使用的工具变更。这样你就可以表明：“看，通过添加这个工具、更换这个模型，我们的准确率从 60% 跃升到了 95%、90% 以上。”

<details>
<summary>Original English</summary>
And by doing all of this, then we got to taking this little model that was failing with 60%, we got it to over 90% and then we are clearing the 85% gate that the bank had for this particular use case by adding that tool, but also by adding this evaluation framework on top that then we can measure the accuracy and the quality of the agent across many different dimensions. And this is something very important because now you can go back and show the evidence of how you actually measure the quality of the agent, but also more importantly, you can link it to the changes that were made into the agent, into the configuration, system prompt, model, tools that were used, and then you say, "Oh, but look at how by adding this tool, changing this model, we went from 60% accuracy over to 95, 90 plus percent accuracy."
</details>

现在到了开始定义准入关卡的环节，这也正是与领域专家合作变得至关重要的时刻。在这一步上，你不能只依赖技术能力。如果你要交付一个借助 AI 能力的风控用例，你必须让风控业务人员深度参与，由他们告诉你达到何种标准，他们才放心将其部署在内部或推向客户。不同的用例，该标准可能各不相同。所以，你首先必须确定评测该应用程序的维度或评分指标；接着针对每一个指标、每一个用例或应用，设定智能体必须满足的不同阈值，以便获得投入生产所需的核准印章。

<details>
<summary>Original English</summary>
And now this is where you start defining your gates, right? And this is where working with your domain experts becomes very, very critical. You don't want to just rely on technical kind of ability for this. You want to make sure that if you're delivering uh an a risk use case that is going to be in a in a enabled, that you have the risk people involved to tell you what is the bar that it needs to meet for them to feel comfortable putting this either internally or in front of customers? And that bar might be different depending on the use case. So, that is why you need to have first the dimensions or the scores uh on which you're going to evaluate this application. And then for each of those and for each use case or application, you end up with different thresholds that the agent needs to meet in order for it to have that stamp of approval uh for it to go into production.
</details>

这就是运行完整端到端测试时的实际情况。我们有一套数据集包含大约 150 个问题，另一套大约有 1500 个问题。现在你可以跨这些不同的维度和指标来衡量智能体的配置表现。大家可以看到，尽管它在依据性（groundedness）、使用完整性（completeness to use）上都合格了，你可能会说：“如果看所有维度的平均值，表现应该算合格吧。”但在监管合规性（regulatory compliance）这一项上，它得了 0 分。这一项是纯二元的指标，要么是 0 分，要么是 100 分。作为一家银行，你绝不希望上线任何会违反监管合规要求的内容，因为这可能导致罚款、招致声誉受损等等。因此，单单一项维度的不达标，就完全有可能直接关闭你推向生产的准入大门。这就是为什么在评测智能体时必须具备多维度的全局视角。

<details>
<summary>Original English</summary>
And this is what it looks like when you we have like a full end-to-end run across, you know, we had one data set that it was like 150 questions, another one was like 1,500. So, but now you can measure the configuration of the agent across these different dimensions and vertices. And you see how even though it is passing on groundness, completeness to use, you might say, "Well, if I take the average of all of these, then it should be okay." But in regulatory compliance is getting a zero. So, that is one that is just binary. It's just either zero or 100. You don't want to put anything if you're a bank out there that is going to violate any regulatory compliance requirement that you have because you might get penalties, you might incur into reputational damage, and all of that. So, it might be that one dimension actually completely shuts down the gate for you to move this into production. So, that's why it's critical to have a multi-pronged view on how you evaluate your agents.
</details>

### 人在回路与闭环迭代流程

当你开始梳理所有这些失败案例或所谓失效模式（failure modes）时，将领域专家重新引入流程就显得极其重要了。你可以为他们整理出一个我们称之为标注队列（annotation queue）的机制，明确规定：“每当在监管合规上出现失败时，我希望将这些用于评测的具体 trace 或证据归集起来，放在一个领域专家可以随时查看 trace、检查到底发生了什么并提供反馈的地方。”有了这些反馈，我就可以反哺给智能体以进行针对性改进。

<details>
<summary>Original English</summary>
And this is where when you start to kind of picking up all these failures or what we call them failure modes, this is where bringing back to the main experts is really critical. You can curate for them what we would call an annotation queue. So, then say, "Anytime that there is a failure on regulatory compliance, I want to curate those specific traces or evidence, right, for my evaluation and put it in a place that my domain expert can come in and look at the trace, look at what happened, and then give me feedback. And with that feedback, I can then go back and, you know, feedback into the agent to improve it.
</details>

将其与之前的流程连接并把人类专家嵌入中间环节后，整体架构就是这个样子。大家注意看下方，这里会发生两件事：每当提示词发布或者配置发生变更时，就会触发重新运行准入核准流程或评测流程；而每当标注重写人员或人类专家接入并给出反馈时，这些数据就成为补充回黄金数据集的潜在候选对象。因为此时我们已经拥有了经过审查的智能体运行凭据，就可以认定：“实际上这一条内容是用来评测智能体在该特定维度上更好的标准基准。”这就是确保既能融入领域专家、又能确保跨越质量关卡的端到端完整闭环。

这使我们帮助他们将原本在风险和合规评测中通常需要耗费数月、甚至数周的时间，大幅缩短到了几分钟。这个过程变得高度迭代，我们可以极具针对性地聚焦在智能体需要重点关注的领域。

<details>
<summary>Original English</summary>
And this is what it would look like connecting it to the process before, but including that human expert into the middle. If you notice down below, that anytime a couple of things are happening here, anytime a prompt gets promoted or a change in the configuration, then it triggers a rerun of the gate clearance process or the evaluation process. But then, anytime a rewriter or a human expert comes in and gives me feedback, that is a potential candidate to go back into my golden data set. Because now we have evidence from runs of the agent that have been reviewed, and now we can say, "Oh, actually this one piece is a better, you know, bar to evaluate this particular dimension on the agent." And this is kind of the whole process end to end to make sure that we are including the the domain experts, but also making sure that we're clearing our our quality gates. Then this got us to a place where we were able to help them go from weeks to minutes when it comes to, you know, evaluating a applications, especially in like risk and compliance, which typically take even months sometimes. So, this process it becomes very iterative. We can be very specific and focus on the areas that we want on the agent.
</details>

### 核心总结

目前这个行业还在发展当中，并没有现成的现成模板可用。通常情况下，你需要根据对自己至关重要的指标，明确定义你到底想要评测什么。

最后我想留给大家三点思考：

第一，**必须编写属于自己的基准**。正如我之前所讲，公开跑分基准对你的数据没有实际参考意义，因为它们本质上并不是基于你的专有数据测试出来的。

第二，**必须对应用程序设立准入关卡，而不是对模型设立**。这能赋予你更大的灵活性。如果明天你想更换模型，所有的控制机制都已经内嵌在应用程序和智能体的配置当中，调整起来会容易得多。

第三，**务必确保领域专家参与进来**，由他们来设定将应用推向生产环境所需的合理基准或门槛阈值。

最后总结来说：使用你自己的数据，确立你自己的标准，设立你自己的准入关卡；尤其是在受监管行业，你希望将一切保留在本地环境中，且极可能不会依赖公开获取的信息。非常感谢大家的时间。我知道我讲得稍微超时了一点，但我想把包含本次工作详细内容的博客文章分享给大家，文章中还附有代码仓库以便大家自行复现。如果有任何问题，我随时可以在场交流。谢谢大家。

<details>
<summary>Original English</summary>
Then there's no template for this. Um, you know, this industry's been been developed right now. So, typically you need to define what is it that you want to evaluate in in in kind of the metrics that matter to you. And the three things that I like to leave you with is you need to write your own benchmark because like I said, the public ones don't really matter for your data because they were not done on your data per se. The second one, you got you have to gate the application, not the model. That gives you more flexibility if tomorrow you want to swap a model, you have already all the controls in the application and in the configuration of the agent, and then it becomes easier for you to adjust. And then the third, let me make sure that the domain experts come come in and set the bar or the thresholds that you are deem reasonable in order for you to promote this into production. And finally, you know, use your data, use your bar, use your gates, especially in regulated industries where you want to keep things in your premises and you're probably not relying on publicly available information. So, thank you for the time. I know I'm a little bit over, but I wanted to give you with the detailed blog post of this work that we did. It also links to the repo that you can reproduce this yourself, and I'm around if you have any questions. So, thank you.
</details>