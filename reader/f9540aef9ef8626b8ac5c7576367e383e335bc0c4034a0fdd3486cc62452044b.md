---
author: AI Engineer
date: '2026-11-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5UgnatzpZ9E
speaker: AI Engineer
tags:
  - ai-agent
  - llm-evaluation
  - model-monitoring
  - software-safety
title: NatWest 银行将 AI Agent 推向生产环境的安全与评估实践
summary: NatWest 集团 AI 工程师 Jonathan Osborn 分享了在受监管银行环境中将面向客户的 AI Agent 投产的经验。面对 1900 万客户的爆炸半径，构建 Agent 相对简单，证明其安全性才是难点。团队采用路由漏斗缩减攻击面、三维评估向量替代单一准确率指标、校准 LLM as a judge、影子部署与特性开关分阶段发布，并在 CI/CD 中建立严格的回归测试门禁。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jonathan Osborn
companies_orgs:
  - NatWest Group
  - Comet ML
  - AWS
products_models:
  - Cora
  - Cora plus
  - OTel
  - OpenInference
media_books: []
status: evergreen
---
### 受监管银行业环境下的 AI Agent 投产挑战

大家好。我叫 Jonathan Osborn，是国民西敏寺银行集团（NatWest Group）的首席 AI 工程师。稍后我会详细介绍这是怎样一家机构。今天我要讲的是，在受监管的银行环境中，如何将面向客户的 Agent 从原型推向生产环境。

可能先剧透一下：凭借我们今天拥有的代码助手和工具，实际构建 Agent 可以说是容易的部分；我认为要困难得多的部分，是证明它的安全性。

<details>
<summary>Original English</summary>
Hi guys. So, my name's Jonathan Osborn. I am a lead AI engineer from NatWest Group. I'll tell you more about what that is in a second. Uh and today I'm going to be talking about taking agents from prototype to production, customer facing that is, in a regulated banking environment. And I guess maybe some spoilers. With the access to coding assistants and tools that we have today, the actual creation of the agent, that's kind of the easy part. The much harder part, I think, is proving that it's safe.
</details>

先向大家介绍一下 NatWest 集团。NatWest 是英国第二大零售银行，目前我们拥有大约 1900 万零售客户。1900 万，请记住这个数字，因为正是这个数字让本次演讲中的其他所有内容都变得至关重要。

<details>
<summary>Original English</summary>
So, let me tell you a bit about NatWest NatWest Group. So, NatWest is the second largest retail bank in the UK, and currently we have somewhere in the range of 19 million retail customers. 19 million, hold on to that number because it's really what makes everything else in this talk matter.
</details>

Cora 是我们客户的主要联系入口。它是我们的数字助手，每天处理大约 10 万次对话。在此之前，绝大部分回答都是脚本化的。也就是说，如果客户来找我们发起对话，而我们事先没有编写相应脚本，那么我们就无法回答。客户会感到沮丧，他们可能就不得不排队去和人工坐席沟通。

<details>
<summary>Original English</summary>
Cora is our customer's primary point of contact. So, it's our digital assistant, and it serves somewhere in the realm of 100,000 conversations a day. And until now, the vast vast bulk of those answers were scripted. So, if a customer comes to us and they ask a conversation, then if we haven't thought to script that, then uh you know, we're not going to be able to answer. Customer's going to get frustrated. They're probably going to have to queue to speak to a human agent.
</details>

这种情况正在改变。截至今年，我们正在推进将 Cora 中大约三分之一的业务流程转变为由 RAG 和知识库支持的 AI 生成回答，以及能够代表客户执行操作的 Agent——例如帮他们完成付款或更改地址。

<details>
<summary>Original English</summary>
That's changing. So, as of this year, we are now working to bring approximately a third of the journeys within Cora to AI-generated answers backed by rag and our knowledge bases, and agents. Agents that are able to take action on the behalf of customers. So, for example, helping them make a payment or change their address.
</details>

### 故障的“爆炸半径”与 Agent 的四种失败模式

我认为这里真正可怕的并不是模型本身。大体上模型已经相当不错了，现在能提供很好的回答。可怕的是**爆炸半径（blast radius）**。面对 1900 万客户，如果我们搞错了其中几句表达，那可不是提交一个 bug 工单那么简单，也不是变成新闻里的趣味八卦。这关系到真实的客户以及他们的真金白银，会引来监管机构极其严厉的质询，还会对我们公司造成声誉损害。

所以，这次演讲讲述的是我们为了获得上线许可必须经历的过程，以及我们如何做到能够信任自己的一部分指标。因为正如我所说，有趣的部分并不是构建 Agent，而是证明并确保它的安全。

<details>
<summary>Original English</summary>
I guess the the scary part here really isn't the model. Like, by and large, models are quite good. They provide good answers now. It's the blast radius. So, with 19 million customers, if we get a few of these utterances wrong, that isn't a bug ticket. That isn't kind of a maybe a funny headline. It's a real customer and their real money. It's slightly very difficult question from the regulator. And it's reputational damage for us as a company. So, this talk is about what we had to go through to get the approval to go live. Uh and I guess what it took us to maybe trust some of our own metrics as well. Because as I say, the interesting part is not the agent, it's proving and making it safe.
</details>

我们通过一个例子来把这个问题具体化。同样的问题，在两套系统中产生了截然不同的对话走向。客户来提问：“我可以在不被收费的情况下提前多还房贷吗？”

今天在基于脚本的方案中，系统会识别出关键词“房贷”（mortgage），然后呈现给客户一个菜单：申请、利率、我的房贷。客户不得不选择“以上都不是”。也许我们会请他们换个说法重述，但很大概率对话就此结束了。这位客户不得不排队去找人工坐席，并因此感到沮丧。

<details>
<summary>Original English</summary>
Let's maybe make that more concrete by considering an example here. So, kind of same question, two very different conversations. So, customer comes, they ask, "Can I overpay my mortgage without being charged?" Today, in the scripted solution, that's going to recognize that keyword mortgage, and we're going to present the customer with a menu. So, apply rates my mortgage, customer is going to have to select none of the above. Maybe we'll ask them to rephrase the question, but more than likely game over. This customer is going to have to queue, speak to a human agent, they're going to be frustrated.
</details>

在右边的场景中，情况完全不同。AI 能够利用我们的知识库来回答这个问题：“您每年最多可以提前偿还贷款余额的 10%，无需支付提前还款违约金。需要我帮您查询具体协议吗？”

但接着，客户做了一件非常符合常理但也可能令人头疼的事：他们换了话题。“其实，我可以直接销户吗？”

这种情况随时都在发生，而传统的决策树非常不擅长处理这类**离题（digression）**。顺便提一句，离题现象后面还会出现，所以我们先记住这一点。

但关键在于：如果我们构建了一个能回答任何问题的 Agent，那它也可能会回答错任何问题。如果那 10% 并不适用于这位客户的具体贷款协议，面对的是真实客户、他们真实的房贷以及他们切身相关的真金白银。

<details>
<summary>Original English</summary>
On the right hand side, bit of a different story. So, AI has been able to answer that question using our knowledge bases. So, you can overpay up to 10% of your balance in a year and no early repayment charges. Shall I check your deal? But then, the customer does something which is very normal, but is can be frustrating. So, they change the topic. So, "Actually, can I close the account instead?" This happens all the time, and a traditional decision tree is really, really bad at this type of digression. It's worth mentioning that digressions are going to come back. So, we'll hold on to that point. I guess the key point though is if we build an agent that can answer any it can also answer any question wrong. So, that 10% if that doesn't apply to this particular customer's deal, it's a real customer, it's their real mortgage, and it's their real money at stake.
</details>

那么，为什么让基于 Agent 的方案具备安全性要困难得多？相比脚本化机器人，我们该如何防范风险？这是因为它会推理、做决策、生成内容，并且这里至少存在四种在脚本化方案中不会出现的失败模式：

1. **极其自信地犯错**：针对虚构来源产生幻觉，而且在犯错时显得非常笃定。
2. **容易被套话/诱导（Prompt Injection）**：输入本身可能具有对抗性。
3. **回答正确但毫无帮助**：它给出的回答完全合规准确，却一直在绕圈子，始终没有真正解决客户的对话诉求，让人极度沮丧。
4. **非确定性（Non-deterministic）**：相同的输入产生截然不同的输出。这意味着传统软件工程中的断言在这里基本起不到太好的效果。其后果就是，现有 Cora 团队多年来积累的回归测试基本上不再适用了。

脚本化系统的失败边界是完全受限的。我们可以列出所有可能出现的情况，对其进行测试，并高度确信它会按预期运行。而对于 Agent，这基本上是不可能的，我们无法靠传统的测试手段测试出一条通往安全的道路。

<details>
<summary>Original English</summary>
So, why is it so much harder to make an agentic back solution, you know, more, you know, how do we protect against it as opposed to that scripted bot? Well, it's because it reasons, it decides, it generates, and there are at least kind of four failure mode here, which we wouldn't have in that scripted solution. One, it can be confidently wrong. Hallucination against a fictitious source and sound absolutely sure of itself while it does it. Two, it can be talked into things. Prompt injection, the input itself can become adversarial. Three, right but unhelpful. So, it can provide accurate on policy answers that just go round and around and around and never actually answer the customer's conversation. Incredibly frustrating. And four, it can be non-deterministic. Same inputs, completely different output. That means that your traditional software engineering assertions just don't really work very well here. And as a consequence of that, regression tests that have been built up over years by the existing core team, they really no longer apply. A scripted system's failure surface is completely bounded. We can write out every situation that might occur. We can test it and we can be really confident it's going to do what we want it to. With an agent, that's really not possible and we can't really traditionally test our way to safety.
</details>

### 防御架构：多层路由漏斗

那么我们该如何应对呢？对我们而言，第一步是在真正考虑加固系统之前，先缩减攻击面。

这就是我们所说的**路由漏斗（routing funnel）**。所有客户对话都从顶端进入：
- 首先，我们应用一个**上下文过滤器**，用于过滤掉诸如按钮点击之类的常见事件，这大约占了 20%。
- 接下来，设置一些**确定性预分类规则**。利用这些规则，我们根据客户的话语和元数据将他们路由到目标位置，在此阶段完全不涉及任何机器学习或 AI。
- 只有通过了前两个门禁的话语，我们才会真正启动模型。首先是一个门控性质的**相关性重述（relevancy rephrasing）步骤**，它有助于处理那些非常复杂的跨上下文问题。
- 然后进入我们的**意图分类器**。这实际上是一个基于嵌入向量的神经网络，并不是生成式 AI，它利用客户的话语来预测正确的后端。
- 最后，设置了若干**策略规则**，以确保该客户确实有权限访问该特定后端。

<details>
<summary>Original English</summary>
So, how do we deal with this? Well, the first part for us was shrinking the attack surface before we actually then thought about hardening it. Introducing what we called the routing funnel. So, every customer conversation comes in at the top here. First, we apply a contextual filter and that allows us to remove kind of common events like button clicks. That's about 20%. Next, we have some deterministic pre-classification rules. So, with these rules, we're kind of using the customer's utterance and some metadata to route them to a destination with no ML or AI involved at all at this point. It's only utterances that make it past these first two gates that we then actually start the models on. First, there's a relevancy rephrasing step that's kind of gated. It helps with those really detailed multi-context questions. And then, our intent classifier. This is actually a neural network over embeddings. This isn't generative AI, which is able to use the customer's utterance to predict the right back end. Finally, there's some policy rules to ensure that this customer should actually be getting into that particular back end.
</details>

为什么我们要采用这种构建方式？主要有四个原因，其中很多都源于作为一家银行的要求：
1. **访问控制**：我们必须严格执行权限控制，确保客户有权进入该后端。
2. **可审计性**：这里的每一项决策都必须附带一个代码，必须完全可审计、可复现，这是监管机构的要求。
3. **韧性**：在模型或生成式 AI 不可用的情况下，我们依然需要为客户提供答复。
4. **治理**：所有这些都是带版本控制的配置。我们可以在不进行完整重新部署的情况下进行修改。这非常重要，意味着我们能够针对变化的市场条件做出快速响应。

我们并没有直接拿来一个语言模型，塞进一些上下文，就把它推向 1900 万客户。我们首先深入思考了究竟有哪些环节是真正需要模型来解决的。

<details>
<summary>Original English</summary>
Why did we build it this way? Well, four reasons, a lot of them about being a bank. Firstly, access control. So, we need to enforce that to ensure the customer should be getting into this this this back end. Auditability. So, every decision here needs to carry a code. Needs to be fully auditable and reproducible. The regulator ensures this. Resilience. In the case that a model or the generative AI isn't available, we still need to provide the customer an answer. And I guess governance. So, all of this is version config. We can make changes to it without a full redeployment. That's really important because it means that we can react fast to changing market conditions. We didn't just take a language model, slap some context into it, and point it at 90 million customers. We first thought really hard about what actually needed a model to solve.
</details>

### 从单一指标到三维评估向量

这就引出了一个非常重要的问题：这套机制究竟是否有效？在传统的 Cora 中，评估时主要看的是准确率这一核心指标。如果我告诉你这个意图路由器的准确率是 94%，听起来可能很不错。但它是否回答了真正重要的问题？

它是否有真实的事实来源支撑？客户的问题到底有没有得到解决？它是否知道自己何时能力不足、何时应该停止并转接人工？

这些是无法用单一分数来体现的。因此我们不再使用单一质量得分，而是开始将其视为一个**向量**。对于每一种回答，我们都会在三个不同维度上进行评分：
- **安全性（Safety）**：它是否可能对客户造成伤害？
- **任务完成度（Task）**：它是否实际完成了自己的工作？
- **体验（Experience）**：交互时的感受如何？

所有这些维度都可以独立进行监控和告警。它们使我们能够区分出：究竟是模型产生了幻觉，还是回答正确但体验极差？这是两种不同的情况，需要截然不同的解决方案。

这里的核心要点在于：一个拥有 94% 准确率、但在其犯错的 6% 的情况下保持 100% 自信的路由器，要比一个准确率为 85% 且明确知道自己何时不确定的路由器危险得多。

<details>
<summary>Original English</summary>
This brings us on to sort of the really important question of if this is actually working. And the key metric that they looked at in kind of traditional core was accuracy when doing this. So, if I told you this intent writer is 94% accurate, that probably sounds really good. But does that actually answer the important question? So, is it grounded in a real source? Did the customer's question actually get resolved? Did it know when it was out of its depth? When to stop bringing in a human? You can't embody that with one single score. And that's why we've moved away from quality of the score. Started treating it more as a vector. Uh every score every kind of answer we score across three different categories. So, safety, could it harm the customer? Task, did it actually do its job? Experience, how did it feel to deal with? All of these can be monitored and alarmed independently. And they allow us to differentiate between is it hallucinating versus is it right but just insufferable to deal with? They're different answers and they require really different solutions. It's what The key point here is a router that's 94% accurate but 100% confident that 6% of the time it's wrong is way more dangerous than one that's 85% confident and knows it.
</details>

在考虑自动化之前，我们最先做的事情与以往一样——从人工验证开始。这里展示的数据来自我们在 6 月份对支付 Agent 进行的人工验证：覆盖 37 个不同支付流程中的 111 次对话、涉及 4 个品牌，每次对话由 3 位独立的人工评审打分。整体结果显示总通过率为 83%。但正如以往一样，总体概括数字往往没什么参考价值。

我们来深入分析这组数据：
- **正常路径场景（Happy path）**：通过率达 97%，表现出色；
- **边缘用例（Edge cases）**：通过率为 76%，不太理想；
- **话题切换（Topic changes）**：例如我们前面提到的房贷例子，通过率仅为 43%。

因此，单一的 83% 分数掩盖了高达 54% 的表现跨度。

右侧的第二个点可能更微妙，平时讨论也较少：**人工验证员之间彼此的意见是否真正一致？**
- 在客观维度上（如偏见与公平性），确实能看到 95% 的一致率，非常不错；
- 但在更为主观的维度上（如意图理解，即机器人是否真正理解了用户意图），一致率只有 64%。

当我们开始推进自动化、引入“LLM as a judge”时，通常的想法是让大模型裁判去对齐人工验证员。但它们到底该对齐什么呢？人类自身之间都只有 64% 的一致率。因此，单纯对齐人类评分并不能成为这里的目标。

顺便提一个注意事项：这里导致失败的两个最大原因最终被证实是工程问题，根本不是模型本身的问题。尽管如此，这恰恰证明了人工验证的实用价值，因为人工把它们揪了出来。

<details>
<summary>Original English</summary>
The first thing we did here before we worried about automating this is what we always do and we started off with some human validation. The numbers that you see here are from June validation that we did on our payment agent. 111 conversations over 37 different payment journeys. Four brands. Three independent human scorers per conversation. Headline here, 83% pass rate across the board. But as ever, the headline's pretty useless. Let's dig into some of that data. So, 97% at on the happy path scenarios, that's great. 76% edge cases, not quite so good. Topic changes, like that mortgage example that we discussed earlier, only 43%. So, that single 83% score was hiding that 54% spread. The second point on the right is probably more nuanced and less talked about, and that's do human validators actually agree with each other? On something objective like bias and fairness, you do actually see a 95% agreement rate, which is great. But on something more subjective, intent understanding, so you know, are does the bot actually understand what the what the user wants, only a 64% agreement rate. The common thing when we start automating this, bringing LLM as a judge, is that we want to make our judge match our human validators. But what are they meant to be matching here? There's only a 64% agreement rate between humans. So, that can't simply be the target here, essentially. One one caveat, by the way, like the two biggest causes of failure here are actually turned out to be engineering issues, not problems with the model at all. But nevertheless, that proves the useful value of the human validation, because it caught them.
</details>

### LLM as a Judge 的校准与陷阱

接下来谈谈自动化阶段：LLM as a judge。鉴于 Cora plus 尚未正式上线，我转向另一个内部项目进行说明。这是一个内部客诉处理 Agent。其大致目标是：客户偶尔会投诉，该 Agent 接收投诉后拥有多种工具调用权限，能为客诉处理人员撰写调查摘要，说明该用户为何投诉以及我们该如何提供协助。

该项目于 2 月份上线，目前已有大约 1.4 万个案例同时由人工验证员和 LLM 裁判进行了打分。

如果深入分析数据，右侧展示的是忠实度（faithfulness）得分：
- 顶部红色柱形表示 LLM 裁判的打分，均值为 0.97，处于顶峰且方差极小；
- 人工打分的均值为 0.83，离散程度明显更宽。

关键问题在于：如果只看相比人工的平均误差（仅为 0.2），你可能会得出结论认为 LLM 裁判表现尚可，但两者之间的相关性几乎为零。在这种情况下，一个无法区分真正优质案例和劣质案例的裁判基本上毫无价值。你不会希望裁判过于宽容，而这恰恰是 LLM 默认的倾向。

<details>
<summary>Original English</summary>
So, let's turn to actually automating this then. So, LLM as a judge. So, Cora plus, that's not live yet, so I'm going to turn to another internal project. So, this is an internal complaints agent that we have. Essentially, the goal here is that customers will occasionally complain. This will take the complaint, it has access to a load of tools to then be able to write a summary for complaint handlers to essentially explain why is this particular user complained and how we can help them with it. It went live in February, and we've got around 14,000 of these cases which have been scored by both a human validator and an LLM as a judge. If we dive into the data, so this is the faithfulness score here on the right. So, you can see upper bar in the red there, that's the LLM as a judge, mean 0.97, right up at the top, very little spread. Human, mean 0.83, much much wider spread. Key point here is that if you look at that average error versus the human, it's 0.2, you might conclude that the judge is doing okay, but the correlation is almost zero. Uh in in this case, like a judge which doesn't discriminate between the actually good cases and the bad cases is basically worthless. You don't want your judge to be generous, and that is what LLMs want to do by default.
</details>

这里还要说明另一点：那条琥珀色虚线代表该特定指标的阈值。对于当前的裁判模型，可以看到我们轻松保持在阈值之上。然而，我们对该模型做了一次更换——没有改变其他任何东西，相同的输入、相同的输出，仅更改了背后的模型——结果评分从原本高于阈值 0.8 直线跌落到仅高于 0.2。

这意味着裁判模型本身实际上变成了你系统配置的一部分，对它的改动可能会引发破坏性变更（breaking changes）。

顺便提一下我们在这里采取的一个关键措施：我们将裁判模型迁移到了与被评测 Agent 不同的模型家族。让被评测方与评测方具有不同的认知盲区，事实证明在缩小两个分数之间的差距方面非常有效。

<details>
<summary>Original English</summary>
Maybe one other point to make here is that so that amber dotted line, that represents the threshold for this particular metric. For this judge model, you can see we're comfortably above that. However, we made a change to that model. Didn't change anything else, same input, same output, just changed the actual model behind it, and that dropped all the way from .8 above to .2 above. That means that the judge model itself actually becomes part of your configuration, and it can lead to breaking changes. A key point we took here, by the way, is that we moved our judge to a different model family from that of the you know, the actual agent. So, judged and judged, different blind spots, and that's actually been really effective in putting the two scores closer together.
</details>

### 可观测性、评估架构与 CI/CD 门禁

回到 Cora 的例子，这套评分在实践中是如何运行的？Agent 与其护栏之间的实时对话都会通过 OpenTelemetry（OTel）和 OpenInference 等开源标准进行捕获。所有这些细节都会被采样：默认采集 5% 的随机样本，但我们还会抓取所有“有价值”的样本——所谓有价值，是指转接人工、执行失败、耗时特别长以及用户情绪愤怒的对话。

然后我们用 LLM 裁判对这些样本进行评分，也就是前面提到的那套多维度指标矩阵。最终，所有这些数据（链路追踪 Trace、评分、实验记录）全部汇总到 Comet ML 中。

这里受到银行若干约束条件的限制：
- 我们在完全物理隔离（air-gapped）的环境中工作，无法连接外网。因此裁判模型是通过内部 GenAI 网关经由私有链路调用的；对于 SaaS 产品 Comet，我们通过 AWS 以已签名合作伙伴应用的形式进行接入。
- 关于个人身份信息（PII），我们对于任何 PII 流出自身网络采取零容忍策略，这意味着大量评估工作必须在剔除 PII 的情况下进行。

系统具有不同的运行节奏：
- 链路追踪（Trace）是实时捕获的；
- 离线评分每 4 小时执行一次；
- 回归测试被集成到我们的 CI/CD 中。

如果我们对提示词或上下文进行修改，可能会对 Agent 的实际回答产生巨大影响。因此我们必须持续将其与已知良好的基准进行对比。我们在 CI/CD 中设置了严格的硬性回归门禁，如果不确切了解改动会带来什么结果，任何变更都无法被合并。

核心观点在于：**持续评估（continuous evaluation）是生产基础设施的一部分**，绝不是模型上线时随便在 Notebook 里跑一两次就完事的东西。

<details>
<summary>Original English</summary>
Coming back to the core example, so how does this scoring actually run? So, live conversations between the agents and its guardrails, all of those are captured via open source standards like OTel and open inference. All of that detail is then sampled. So, by default, we take 5% random sample, but we also want to look at everything interesting. By interesting, I mean conversations that hand off, fail, those that are particularly long, ones where the user was angry. We then score these with our LLM as a judge. So, that's that raft and dimension of metrics that I talked about earlier. And then absolutely all of this ends up in Comet ML, so traces, scores, experiments. It's governed by a couple of bank constraints here, so we work work in a completely air-gapped environment, so no internet access to anything. So, judge model is reached over a private path with an internal GenAI gateway. Comet, a SaaS product, we're consuming that as a signed partner app via AWS. Second around personally identifiable information, we have a zero tolerance policy for any PII leaving our network. So, that means a lot of this evaluation happens without that present. Different cadences here, so traces are being captured as they happen. We're doing offline scoring every 4 hours, and then regression, this is also built into our CICD. So, if we make changes to prompts or to context, that can have like an outsized impact on what the agent is actually responding. So, we need to constantly be comparing versus a known good baseline. We do that in CICD. There's a hard regression gate, so changes can't be merged in without us understanding exactly what's going to occur. I guess key point is that continuous evaluation is part of your production infrastructure. It's not a notebook that you run a couple of times when your model goes live.
</details>

这里涉及不同的模型，它们具有不同的失效模式：
- 右侧是 Agent 与生成式 AI。生成式 AI 会发生退化（regress），正如刚才讨论的，有人修改了提示词就可能对行为产生巨大影响，这也是我们要设立 CI/CD 的原因。图中展示了一条来自我们支付 Agent 的真实 Ubik 链路追踪，折线图中的每个节点对应一个 span，当 Agent 响应缓慢或在特定位置报错时，我们或另一个 Agent 就能介入深入排查原因。
- 左侧是传统机器学习。意图分类器采用的是传统 ML，因此我们必须以更传统的方式进行监控。它会随着时间推移发生**漂移（drift）**，因为人类的日常对话自然会偏离模型训练时的分布。因此我们需要监控更为传统的指标，例如输入特征漂移、基于人工标注计算的 F1 分数，并设定 RAG 阈值以明确何时必须触发该模型的重新训练。

右侧展示的是一张 MPM（Model Performance Management）数据漂移图表。切勿低估输入特征漂移的价值：它是一个非常有效的早期预警指标，能在 F1 分数下跌之前提前提示模型性能开始衰减并需要重新训练。

两个不同的问题，两套不同的工具，但我们不希望维护两套割裂的可观测性与评估框架。Comet 在这方面非常有用，因为它把面向生成式 AI 的 Ubik 和面向传统 ML 的模型性能监控（MPM）统一整合在了一个平台内。

<details>
<summary>Original English</summary>
So, the different models here and they've got different failure modes. So, on the right-hand side we've got the agents, we've got the generative AI. So, generative AI regresses. So, as we just talked about, somebody can make changes to a prompt and that can have outsized impact on the behavior. That's why we have the CICD in place. You can see here a real Ubiq trace which is looked from our payment agent. Every node in the line graph becomes a different span and when the agent is slow or it's breaking in a particular place, this allows us or an agent to jump in and investigate exactly why. On the classical So, the intent classifier is traditional ML and thus we've got to monitor it in more classical way. It drifts over time, right? So, human conversation will naturally evolve from the point at which the model was trained. So, we need to look at more traditional things like input feature drift, F1 score based off human scores, sorry, human labels, and then, you know, we have rag thresholds defined as to exactly when we need to trigger retraining for that model. On the right, you can see an MPM data drift chart. I I really wouldn't underestimate like input feature drift here. It's a really good canary as to when your model is starting to decline before your F1 score does, implying the need for retraining. So, two different problems, two different instruments, but what we don't want is two different observability and evaluation frameworks. Comet's really useful there because it brings in both Ubiq for the gen AI and MPM model performance monitor for the ML. So, one platform.
</details>

### 安全发布策略：影子部署与特性开关

那么，我们究竟该如何在不危及银行安全且不引发公关危机的前提下部署上线？我们从**影子部署（shadow deployment）**开始。具体做法是让系统上线并开始对客户的话语进行分类，但真正负责回复客户的仍然是现有的脚本化方案。

这意味着我们能够以近乎零风险的方式获取真实数据，了解不同客户查询的真实输入空间。我认为这种影子模式是本项目中最具可借鉴性的经验之一。因为在受监管行业中我们经常面临僵局：显然未获批准我们就不能上线获取生产数据；但另一方面，为了批准我们上线，模型风险管理部门又越来越希望能看到模型对真实生产数据的反应。

影子模式打破了这一死锁：我们将“安全观察”与“实际响应客户查询”完全解耦。它将一次巨大的、高风险的单次决策（big bang release）拆解为一系列我们可以胸有成竹推进的小决策。

<details>
<summary>Original English</summary>
How do we actually deploy this then without kind of breaking the bank and creating a lot of headlines? We start off with a shadow deployment. So, what I mean by that is we put this live, and it to start classifying customer utterances, but the existing scripted solution is what will actually respond to the customer. And that means that we can get a sense of the real data, you know, the input the input space for different customer queries with compulsory zero risk. I think this shadow mode is like one of the more transferable bits of this project for us because often we have the deadlock in a regulated industry where obviously we can't go live and get production data without the approval to do so. But equally to actually enable us to go live in many cases, our model risk colleagues increasingly want to see how our models are going to react to that actual production data. This allows us to kind of break that apart, so we can break apart observe safely from actually answer customer queries. And it takes one really big decision point a big bang release into a series of smaller ones which we can make confidently.
</details>

随后我们按品牌逐步推广：在每个品牌内部按百分比推进放量，并设置 KPI 门限以决定流程中各阶段的继续或中止（go/no-go）。其中部分决策实现了自动化，部分决策则需要人工审批。

实现这一机制的基础在于我们大量使用了**特性开关（feature flagging）**：既有全局开关可以一键将所有流量切回脚本化方案，也可以在全球范围或针对特定维度（如品牌）对任意单一后端进行隔离。所有这些切换都能在数秒内完成。

<details>
<summary>Original English</summary>
We then go brand by brand, so we have like percentage based roll out within the brand, and we have kind of KPIs which allow us to determine go no go at various points along that. Some of those decisions are automated, and some of those require manual approval. And I think that and yeah, some of those require manual approval. What kind of makes that possible is that we make a lot of use of feature flagging here, so there's like a global flag that we can trigger to send everything back to the scripted solution, but also every single back end can be isolated either globally or on a particular dimension such as brand. And all of that can be done in seconds.
</details>

### 客诉项目经验与总结

在总结之前，让我简要呼应一下之前的客诉处理项目。提醒一下，那是一个面向员工内部的 Agent，负责为客诉处理员撰写调查摘要。

在那个项目中，**人工反馈是一道强制门禁**。它绝不是点个赞或走个过场勾选一下那么简单。如果客诉处理人员想要重新运行调查，必须先提供人工反馈。我们不仅需要了解他们为何觉得需要重跑，而且借此积累了由员工标注的高质量数据集，涵盖多达 1.4 万个案例。这极其宝贵，因为在许多项目中，我们连这个数量的十分之一都很难收集到。

两个项目之间也形成了良好的经验互通：客诉团队在生产环境中发现了 LLM 裁判的偏差问题，我们因此建立了裁判校准与回归检验机制；相应地，我们构建的这套重度依赖 Comet 的架构虽然客诉团队尚未采用，但他们即将将其引入到自身的生产监控中。

这可以说是企业内部运作的一个缩影：Agent 本身是较为廉价的部分，那是我们为了解决业务问题编写的业务代码；而**评估主干（evaluation spine）**则是能够被反复复用的核心资产。

<details>
<summary>Original English</summary>
Before I wrap up, let me maybe just talk very briefly and pull this back to that complaints project. So just to remind you, that was the colleague facing agent which writes investigation summaries for summaries for complaint handlers. In that project, human feedback is a gate. It's not thumbs up, it's not a tick box activity. So if a complaint handler wants to rerun their investigation, they can't do so until they provided human feedback. We want to understand why they felt the need to do that rerun, but also it's allowed us to build up this quality data set of 14 14,000 customer of colleague labels, I guess in in case. And that's really valuable. In a lot of projects, we struggle to get a 10th of that number. And I think the projects have also traded nicely here. So, you know, they found that judge problem in production. We have judge calibration and regression checks because of that. But equally, the architecture that we built, which relies heavily in common epic, they don't use that yet and they're going to be adopting that for their production monitoring. I guess it's a glimpse inside an enterprise, right? So, the the agent with the cheap part here, that's code that we can produce to solve the business problem. The valuation spine is the bit that we can then re-use again and again.
</details>

总结一下，如果你打算在受监管环境中发布面向客户的 Agent，我想提出以下几点建议。这里不一一展开，挑两点重点强调：
- 第 3 点和第 4 点涉及来自实际生产中的裁判数据：最开始提到的 LLM 裁判评价其实是个失真的测量工具。你的裁判模型天生倾向于给出过高的正面评价，你必须克服这一点。要对比评分跨度而不仅是看平均分，确保裁判能够真正对齐人工评审。
- 第 4 点：裁判模型本身会成为阈值配置的一部分。如果你要更换裁判模型，可能会在不知不觉中引入破坏性变更。

Comet 在整个体系中显然起到了至关重要的作用，统一支撑了生成式 AI 以及我们仍在少量使用的传统机器学习两部分。

最后我想说的是，下个月系统正式上线时，我就会知道这些方法究竟有多大成效了。非常感谢大家的聆听，很高兴能与各位交流。演讲结束后我会留在 Comet 的展位，如果有任何问题或不同看法，非常欢迎前来讨论。多谢大家的时间！

<details>
<summary>Original English</summary>
So, to wrap up, like if you are going to be shipping customer-facing agents in a regulated environment, then these are probably the points that I would give you. I'm not going to go through everything. I'll maybe just pick a couple. So, three and four here, they're the they're the points with the actual production judge data, right? So, that judge opinion at the top is a broken instrument. Your judges are going to want to be overly positive. You need to fight against that. Compare the spans, not just the averages. Ensure the judge is actually matching the human review. Fourth, the judge model itself does become part of that threshold config, right? So, if you are going to be making changes to the judge model, then you know, you can introduce a breaking change without knowing it. And Comet is obviously absolutely key here. So, we have that for both halves, both the generative AI and the traditional ML, which we do still use a little bit. So, and I guess the the final point here is next month I'll find out how much of this is actually true when we go live. So, thanks a lot for listening. It was really a pleasure to get to speak to all of you. So, I'll be at the Comet booth after this. If you do have any questions, you know, disagreements, etc., really happy to hear them. But thanks a lot for your time.
</details>