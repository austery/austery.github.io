---
author: AI Engineer
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3osCbSufv8g
speaker: AI Engineer
tags:
  - voice-agent
  - ai-evaluation
  - llm-as-a-judge
  - fintech-compliance
  - simulation
title: 金融合规场景下的语音 AI 评测与闭环迭代
summary: Upstart 与 Coval 分享在强监管借贷场景落地语音 Agent 的实践。团队通过人工审核对齐 LLM Judge，将合规一致性从 33% 提升至 92%，并建立包含实时监控、仿真测试与人工把关的持续闭环迭代流程。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Upstart
  - Coval
products_models: []
media_books: []
status: evergreen
---
### 演讲者背景与语音 Agent 的系统相似性

**>>**: [音乐]
<details><summary>Original English</summary>
**>>**: [music]
</details>

**>>**: 嗯，我是 Brooke。我是 Coval 的创始人，我们为语音 Agent 构建评测系统。我之前在 Waymo 工作，在 Waymo 领导了评测基础设施团队，负责所有用于启动和运行仿真的开发者工具。你可能会想，这和语音 Agent 有什么关系？其实，自动驾驶汽车和自主语音 Agent 非常相似。你如何确保某个系统可靠地从 A 点到达 B 点，涵盖两者之间所有可能的路径？以及你如何架构众多模型协同工作，以构建一个能够可靠响应和应对现实世界的自主系统？

我们与企业合作，从像 Perplexity 这样快速成长的 AI 公司，到全面的财富 500 强企业，确保他们的语音 Agent 在客户支持、物流等场景中表现良好。
<details><summary>Original English</summary>
**>>**: Um so I'm Brooke. I'm the founder of Koval and we build evaluations for voice agents. My background's from Waymo, so I led our evaluation infrastructure team at Waymo and my team was responsible for all of our developer tools for launching and running simulations. You might be like, what does that have to do with with voice agents? Well, autonomous vehicles are actually very similar to autonomous voice agents. How do you make sure that something reliably gets from point A to point B, all the possible paths in between, and also how do you architect lots of models working together in order to build an autonomous system that reacts and responds to the world reliably?

Um so we work with enterprises, everyone from really fast-growing AI companies like Perplexity to Fortune 500s across the board, um to make sure that their voice agents are working well for customer support, logistics, etc.
</details>

### Upstart 贷款核验场景与合规约束

**>>**: 太棒了，我是 Shiv。我在 Upstart 负责语音 AI。对于不熟悉 Upstart 的人来说，我们是一家金融科技公司，主要从事借贷业务。

好的，很棒。那我来谈谈语音业务。Upstart 总体上每天要处理成千上万通电话。

我想我们谈到了业务领域，也就是借贷。借贷领域的独特之处显然在于它是一个受到高度监管的领域。当我们的语音 Agent 与申请人或借款人通电话时，如果出了差错，这不仅是一个客户体验问题，还可能是一个潜在的监管合规问题，而后者情况更严重。对吧？所以，每当我们上线这些 Agent 时，我们首先要确保的就是完全遵守所有的规章制度。

因此这一次，我将分享一个我们已经上线的用例。我们上线的这个 Agent 是为了实现核验电话的自动化。

实际流程是这样的：大约 90% 的 Upstart 申请人能获得即时审批结果；剩下的 10% 没有获得即时结果，他们必须拨打电话来核验一些信息。所以这个用例相当简单。

我们会问三个问题：未来三个月您的收入来源是否会持续？您打算如何使用这笔借款？您是否有任何未履行的债务义务，比如赡养费、工资扣发等？

好的，除了这三个问题之外，我们首先需要验证拨打电话的人确实是本人，以免他们询问一些不属于自己的随机申请。

接着，你可能会觉得这是一个非常简单的用例，但监管层面的问题恰恰就在这里出现了。我举几个例子。

如果有人说“我打算把这笔钱用于医疗用途”，我们就不能追问具体金额，规矩明确禁止我们这么做。如果我们追问了，就会给我们带来大麻烦。

另一方面，如果有人说“我打算用这笔钱去参加毕业典礼”，对吧？那么，这是谁的毕业典礼？是您自己的？您孩子的？还是其他人的？这直接决定了资金的用途性质，对吧？因此，根据申请人或电话另一端的人所说的话，我们必须采取特定动作。有些内容我们可以问，有些内容我们绝不能问。

最后一点，对于我的合规团队来说非常重要的一点是：当我们处理这个用例时，就必须严格限定在这个用例之内。很多申请人都非常渴望了解自己的审批状态，或者什么时候能拿到钱，因为我们不能随口说“最多需要三个工作日”之类的话，我们只能以礼貌得体的方式避开这个问题。

以上就是我们上线的这个用例的大致情况。
<details><summary>Original English</summary>
**>>**: Cool, and I'm Shiv. Uh I lead our voice AI at Upstart. Uh for those not familiar with Upstart, we are a fintech company and we primarily do lending.

Okay, cool. So, let me talk about voice a little bit. So, Upstart in general does uh thousands of calls, well, every day. Um

I think um we talked about domain, which is lending. So, what is unique about lending is obviously it's a highly regulated space, um you know. And when when we have voice agents doing these calls with with applicants or borrowers, um if things go wrong, it's not just a uh you know, customer experience issue. It is It could be a potential regulatory issue, which is worse. Right? So, um whenever we we launch these agents, we want to make sure that uh you know, we are we are first and foremost compliant with all the rules and regulations.

So for this one, I'm going to talk about a use case that you know, we we launched. The process the the agent that we launched was automating verification calls.

So what happens is about 90% of people who apply to Upstart are instantly decisioned. The 10% that are not, they have to call in and they have to verify some information. So use case is fairly simple.

We ask three questions. Will your income sources continue for the next three months? How do you plan to use the funds? And do you have any outstanding obligations such as you know, alimony, wage garnishments, etc.

Okay, so those three questions aside, you know, we we first need to verify that the person calling in is actually the person. So they don't ask like, "Hey, can you tell me about some random application that they don't own?"

Um then sort of you may think that this is a very simple use case, but this is where sort of regulatory things come into the picture. So I'll give a couple of examples.

If someone says that I plan to use the funds for medical purposes, we can't ask the amount. We just prevented from doing that. If we do ask it, it creates a big issue for us.

Um on the other hand, if someone says, "I plan to use the funds to travel to graduation." Right? Well, whose graduation is it? Your graduation? Your kids' graduation? Someone else's? That really determines the use of funds, right? So depending on on sort of what the applicant or the human at the other end says, we have to do specific things. We can ask or cannot ask things.

And lastly, I think the it was very important for my compliance team that when we handle this use case, we just handle this use case, right? A lot of applicants are very eager to know what their status is or when they'll get the money because we can't just say like it'll be up to three business days. We just sort of sidestep the question in a nice and polite way.

Um so that's that's sort of the use case that we launched.
</details>

### 从表格审计到 LLM Judge 与人工对齐

**>>**: 好的。这就是通话流程。显然，当我们上线这个系统时，我们希望确保 Agent 能够很好地完成既定目标。所以审计工作非常重要，每一通电话都必须经过人工复核。

刚开始的时候，你该如何复核所有这些电话呢？我们是从简陋的 Google 表格开始的。我们维护着表格，负责复核这些通话的运营团队开始往里面录入数据。几周内，表格从 5 列增加到 10 列，接着又到 15 列，大家开始随意添加列、随意填入内容，把整个流程搞得一团糟。但归根结底，我们需要数据来改进我们的 Agent，同时也需要数据来改进我们衡量性能的指标。

正因如此，我们需要一个更好、更结构化的人工复核流程。这时 Coval 介入并帮助我们构建了这个人工复核流程。在深入细节之前，我先简单谈谈评测指标。我在这里所说的指标，指的是通话结束之后运行的 LLM as a judge。例如，一个重要的评判标准是：是否满足了合规要求？这是一个带有解释说明的简单“是/否”问题。所以我们做的事情之一就是：在通话结束后运行这个评委模型，它会给出一个结果并附带解释。现在，我们希望确保评委模型的判断是准确的。于是我们引入人工来复核 LLM 评委模型的输出结果。

刚开始的时候，我们有一堆指标并追踪很多内容，比如通话时长、准确性、清晰度等等。随着时间推移，我们将列表逐步精简为最重要的几项核心指标，正如你在屏幕上看到的这些：准确性、清晰度、完整性、政策合规性、转人工升级是否正确，以及最终的 CSAT 得分。

我想分享的一个重要经验是：不要对你的评测指标过度执念。一开始先选用那些看似合乎逻辑的指标；如果随着时间推移情况发生了变化，就要舍弃这些指标，转而追踪那些真正会对你的具体业务场景产生实际影响的指标。

好的，我们刚才谈到了 LLM as a judge 和评测指标。同样，所有这些都是在通话结束后自动运行的。

现在我来专门讲讲其中一个具体指标，也就是合规遵循或合规违规。基本流程是我们对通话进行评分，然后进入审核队列。由人工复核该指标的输出，并录入反馈意见。这之所以重要，是因为我们想确保评委模型的输出与该领域的专业人员或专家保持对齐。正如你在这里看到的，在我们早先刚上线时，合规一致性指标只有 33%。这意味着人工审核员和 LLM 评委在 33% 的时间里才能达成一致。我们不可能做到 100%，但我们可以做到非常接近。于是我们开始深入排查差距到底在哪里，而专家提供反馈的流程在这方面起到了很大帮助。最终问题归结为几个方面：

首先，在我们上线 Agent 时，存在大量的未编码为 Agent 规则的内部隐性经验（tribal knowledge）。我们对此进行了修改，随着时间推移，该指标数据有所上升。随后我们发现，在负责复核通话的人员之间本身也存在分歧，因为有很多内容未被写成文档，或者属于隐性经验。因此我们努力将这些经验编码化。

再之后，随着我们开始覆盖更多用例，迎来了下一次大幅提升。我们开始发现评委模型本身也需要改进。最终，我们的一致率从一开始的 33% 攀升到了如今的 92%。
<details><summary>Original English</summary>
**>>**: Cool. So um So that's the call. Now obviously when we launched this we want to make sure that the agent was doing well what it set out to do. Uh you know, so when we start audit auditing was very important. So every call had to be reviewed by a human.

Um now obviously when this started out well how do you review all these calls? So we started with the humble Google sheet. You know, we start maintaining it. Our operations team that were reviewing these calls started putting in data there.

In a few weeks five columns went to 10 then like 15 people started adding columns randomly putting stuff in columns creating things that you know, just just sort of messed up the whole process, right? So ultimately like what we need is data to improve both our agent as well as you know, the uh the things that we look in terms of performance, right?

So that's where we sort of uh needed to have a better and more structured process for human review, right? And that's where Kowal came in and helped us build this human review process. Um but before I go there let me just talk a little bit about metrics, right? So when I talk about metrics here think about LM as a judge running once a call is complete. Right? So one important like criteria is were the compliance requirements met? So I it's a simple like yes no question with an explanation, right? So, uh one of the things we did is post post run, we run this judge and it produces an output with an explanation. Now, we want to make sure that the judge is working. So, we we put it and and we get a human to review the output of the LLM judge.

Yeah, so when we started off, you know, we had metrics and we were tracking like a whole bunch of things like call time, you know, obviously accuracy, clarity, etc.

I think over time we sort of whittled down the list to the metrics that were sort of the most important, right? And you can see some of the ones here like accuracy, clarity, completeness, policy alignment, whether it was escalated correctly, and ultimately CSAT score.

One important thing I'd say is don't be too attached to your metrics. Start off with the ones that seem logical. If things change over time, you know, discard those metrics and track the other ones that really like impact your use case.

Um Cool. So, we talked about LLM as judge and metrics a little bit. So, again, all these are run automatically once a call is complete.

Now, I'll talk about one specific one here which was, you know, adherence to compliance, right? Or compliance violation. So, basically we we score the call. It goes into a queue. A human reviews the output of the of the metric. And then puts in their feedback, right? Why this is important is because we want to make sure that whatever the judge is outputting aligns with humans or experts in that particular area, right? And as you can see here like when we launched a while back, the compliance sort of agreement metric was 33%. That means a human reviewer and a LLM agent or a LLM judge agreed only 33% of the time. Now, well, we don't we we can't get to 100% but we can get like very close, right? So, we really start looking into like what is the gap there and that's where this process of providing feedback by experts sort of really helped, right? And ultimately it came down to a couple of things, right? There was a lot of tribal knowledge when we launched the agent that was not coded as part of the agent. So, we changed that and over time the the metric seems number went up. Then we realized that amongst humans in who are reviewing this call there was disagreement as well, right? Because there was a lot of stuff that was not written or or like tribal knowledge. So, we tried to like encode that.

And then like sort of the next big bump came as we started to like look at more use cases. We started to see that well, the judge itself needed to be improved, right? So, ultimately we went up from like a 33% agreement rate to now today it's at 92%.
</details>

**>>**: [清嗓子]
<details><summary>Original English</summary>
**>>**: [clears throat]
</details>

**>>**: 我们将具体深入讨论该流程是如何运作的，接下来我交回给 Brooke。
<details><summary>Original English</summary>
**>>**: Um we'll talk a little bit about how this process works in detail. So, I'll hand it over to Brooke.
</details>

### 持续改进闭环：指标、监控与语音仿真

**>>**: 太棒了。在此基础上，我们实际落地的是一个持续迭代的完整闭环，用来持续改进这些 Agent。我认为这是 Upstart 做得非常出色的一点：建立了一个不仅支持初次上线，更支持持续改进的流程。太好了，我很高兴这对大家有用，大家都拿手机拍照。

但这套机制确实能让你不断优化自己的 Agent。我认为很多企业容易犯的一个错误是：他们设立了发布卡点以便完成一次性上线，但这导致后续更换底层模型、修改 Prompt 或做任何调整都变得极其困难。

接下来，我将逐步讲解整个流程：如何从监控对话、定义评估指标、标记异常通话，到利用这些数据不断改进 Agent。

同时，我们也沿用了 Shiv 刚才谈到的人工复核。我们坚信人工复核是评测流程中极其关键的环节。你大部分的时间应该花在思考产品定义上——评测本质上就是产品定义。因此，你应该把时间花在思考“我的产品应该做什么”上。

第一步是定义指标。评测有不同的类别，我将其划分为三类：是否达成了最终目标？是否遵循了达成目标所需的步骤流程？以及对话质量或整体体验如何？

在 Coval 中（稍后我会在 Coval 实际演示），你可以构建这些 LLM 评委模型或评测指标，使其与人工审核员最初进行标注的准则保持对齐。让这些人工审核员标注他们关心的内容是至关重要的一步，随后你可以将其转化为自动化评测；反之，如果一开始就盯着诸如词错率（WER）之类的指标，却不是你们真正能够采取行动的抓手，那就本末倒置了。

指标的类型包括 LLM as a judge、启发式规则（heuristics）以及音频处理指标。

接着，我们利用这些指标对实时通话进行监控。这样我们就能在规模化运行中检测出已知的失败模式。例如，能够准确标出我们在哪里没有核验正确的贷款信息，或者在哪里用词不够准确。这一点极其关键，因为没有哪个系统能在规模化运行时做到 100% 可靠。即便像 Google 拥有 6 个 9 的可靠性，也依然会出现故障。此外，我们还能通过聚类分析和异常检测来发现“未知的未知问题”（unknown unknowns），即那些我们事先不知道会发生的情况。

随后，我们可以将这些失败样本路由给人工复核。你可以配置复核队列，让人工审核员针对我们定义的各项指标采取行动，由出色的审核员专门审查这些故障案例。如此一来，他们无需听取每一通电话，而只需专注于最重要的通话。

从那里开始，我们将不同类型的失败案例分流给对应的团队。这是一个非常关键的环节，因为你需要建立一套运营规范，确保每一个传入的故障都能得到相应处理。要么将其路由至人工审核以确认真正的故障（比如，“脱离话术”或“回答错误”占比 34%，这些只是假设的数字），然后将这些案例交给 Agent 团队；合规违规案例则转交给合规团队，以便他们备案流程或采取策略性行动；其他问题则分派给工程团队等。

一旦我们收集到一组真实的失败案例，就可以进行重新仿真，或者由比如在场的 Steven 来找出针对 Agent 的正确修复方案。接着，我们可以针对修复方案进行重新仿真，精确查看其效果，验证它是否真正修复了该问题。

我们的仿真执行的是语音到语音（voice to voice）的评测。我们会呼叫你的 Agent 并实际运行仿真，以测试不同的背景噪音、不同的口音、实际的语音质量以及打断情况等。

这样我们就能在改进方案影响用户之前，验证它是否确实解决了问题。一旦你发现系统存在合规违规或不良用户体验等问题，你绝不会希望直接将修改发布到生产环境中去看是否修好了，因为这会给你的用户带来风险。用 DevOps 的术语来说，我们希望“左移”（shift left）。我们希望在仿真阶段检测出尽可能多的失败，而不是留到生产环境中去暴露。正如你在报告中看到的，我们改善了这些案例。

这最终形成了一个完整的闭环：我们根据产品定义来定义指标（坦白说，这正是你最应该投入精力的地方——理清 Agent 应该做什么、不应该做什么）；然后监控并对每一通实时通话进行评分，检测故障，送交人工复核，从所有案例中归纳失败模式以排定工程优先级。最令人兴奋的是，你现在可以启用自愈闭环（self-healing loop）：我们既可以让 Agent 分析所有这些评测结果并识别修复方案，也可以借助强化学习管线（RL pipelines）或微调 LLM，让系统随着时间推移自动变得更加完善。

我先退回上一页。好的。从那里我们可以实现自动化修复，并通过仿真证明这确实改善了生产表现。显然，所有这些环节都有人工复核作为道闸把关，将人机协同（human-in-the-loop）融入其中。

因此，这些体系化配置既能确保我们的评测指标高度准确（正如 Shiv 刚才所讲，每当你将某个指标标记为判断错误，你就可以将指标调整得更贴合人工判断）；同时如果它确实是一个真实的系统失败，你也可以利用它来自动改进 Agent。
<details><summary>Original English</summary>
**>>**: Amazing. So, from there what we really implemented was this continuous this complete loop of how you continuously improve the agents. So, I think this is something that Upstart has done really well is actually setting up a process that doesn't allow you to just launch once but allows you Um amazing. I'm super happy this is useful. Um so, everyone taking pictures.

Um but it really allows you to like continuously improve your agent. I think this is something that enterprises get wrong is that they set up how whether the release gate so that we can launch one time but then it makes it very hard to change a model or change a prompt or anything underneath. And so, we go from like um I'll step through all of these processes of how you go from monitoring conversations, defining what your metrics look like, flagging calls, and then using that to constantly improve your agent.

Um and so we also use this human review that Shiv just talked about and really believe that human review is a super important part of the evaluation process and where you should be spending most of your time is thinking about the product like evals are really the product definition. So where should you be spending your time um is what should my product be doing?

Um so the first step is defining your metrics. So there are different types of evaluations. Like I think about it in three categories of did it get to the end? Did it adhere to the steps in order to get there? And then what was the conversation quality or the experience?

Um and so in Cobal, and I'll be showing you how this actually works in Cobal. So you can build out these LLM judge or metrics that align with this original criteria that human reviewers were going through and labeling. That's also a really important step though is to have these human reviewers labeling what do they care about and then you can take that and turn it into automated evals versus the reverse is starting with like we care about word error rate but that's not actually what we're actioning on.

Um and then the types of metrics are you know LLM as a judge, heuristics, audio processing.

Um and so what we do is we monitor then take these metrics to monitor live calls. And so we can detect known failure patterns at scale. So being able to show exactly where for example we didn't verify um the correct pieces for the loan um or maybe where it didn't have the wording correct. Um and this is really important because no system works uh 100% of the time at scale. Uh even Google you know six nines of reliability there will will be failures. Um and then we also detect unknown unknowns. So things that we didn't know were going to happen doing by doing like clustering analysis and anomaly detection.

Um and then we can route each one of these failures for human review. So you can configure review queues where they're actioning on any one of these metrics that we defined and then having these amazing human reviewers look through those failures. So now instead of looking at every call, they're only looking at the calls that matter most.

And so from there we route all of these different failures to the right teams. This is a really critical step because you want to set up an operational practice so that every failure that's coming in you're doing something with that. So either you're routing it to you're routing for human review to detect real failures. So let's say like you know off script or wrong answer is 34% of the time. These are just made up numbers. Um then like maybe we send those to the agent team versus compliance violations we send that to a compliance team so that they can file a process or you know take some like tactical action on it versus sending to an engineering team etc.

Um and so now once we have a set of real failures, we can then re-simulate or we then for example Steven who's here can figure out what is the right fix to the agent. Um and then we can re-simulate that that fix to see what exactly the result is. Like did it actually fix this issue?

Um and so our simulations do voice to voice evaluation. We will call your agent and actually run a simulation to um you know test different background noises, different accents, um the actual voice quality, interruptions, etc.

And then we can verify that that improvement actually fixed things before it's impacting your users. So once you know that there's an issue like a compliance violation or maybe like a poor user experience, you don't want to launch that again to production to see if it fixed it because you're now risking impact to your users. So we want to shift left to use a devops term. Um we want to detect as many failures as we can in simulation instead of doing that in production. So, here you can see that, you know, we improved um those cases in the report. And so, this finally completes the loop of um we monitor we define what our metrics are based on our product definition. This is honestly where you should spend the most of your time is what does my agent do and what should it not do. Um and then we can monitor and score every live call, um detect those failures, send them for human review, find failure patterns across all of these to prioritize engineering work. And one of the most exciting things is now you can enable the self-healing loop where we can actually have agents that look at all of these evaluations and identify fixes, but we can also use RL pipelines or fine-tuned LLMs in order to make our system even better over time automatically. Um and then actually I have to go back. Okay. Um and then from there we can automate fixes and then prove that this actually is improving things in production through simulation. And all of these things obviously are gated by human review and integrating human review in the loop. Um and so, these defined setups can uh both make sure our metrics are really accurate. So, as I should have talked through, every time you label a feedback every time you label a metric as it was being as it was incorrect, now you can align your metrics to human judgment or it it actually is a true failure, in which case you can use that to automatically improve your agents.

Um
</details>

### 总结与问答收尾

**>>**: 很好。总结一下，评测至关重要，千万不要跳过评测。

评测既能帮助我们监控和评估通话，也能帮助我们判断哪些通话需要重点关注，或者哪些通话需要人工复核，因为人工不可能每天审核成千上万通电话。

人工审核员的标注非常重要，因为它们有助于改进 LLM 评委模型。

我们收集到的所有这些数据，最终也都有助于优化 Agent 本身。

所有的变更始终置于 Feature Flag（功能开关）的管控之下。所以当我们说“自愈”或“自我改进”时，并不意味着人类被完全排除在闭环之外。在金融科技领域，这些变更必须受到监控并由相关负责人签字审批。评委模型的改动通常由工程师负责；但如果涉及到合规方面的变动，则必须由合规团队参与审批 Agent 的行为规范。最后，这套方案为我们提供了一套蓝图，使我们能够在满足监管要求的同时安全地上线 Agent，并在此过程中不断提升其性能表现。
<details><summary>Original English</summary>
**>>**: Cool. Um so, yeah, in conclusion, right? Evals are important. Don't don't skip them.

Uh evals uh sort of help us uh sort of monitor and score the calls, but also determine which calls need attention or which calls need to be like reviewed by a human because humans can't review like thousands of calls a day.

Um, the human reviewer annotations are important because they help improve the LM judge.

Um, all this data that we collect ultimately helps improve the agent as well.

Um, changes are always gated behind a feature flag, right? So, we when we say self-healing or self-improving, it doesn't mean like humans are completely out of the loop.

Uh, with uh, fintech, uh, we we need these, uh, changes to be sort of monitored and and signed on by like someone, right? So, judges usually the engineers do. Uh, but if uh, there was a compliance change, then compliance is involved in approving like, uh, the behavior of the agent. Um, and lastly, like this has served like as a blueprint for us to launch agents safely meeting regulatory requirements and also improving their performance at the same time.
</details>

**>>**: 我认为这也是为什么能够建立真正健全的评测体系决定了产品的高质量。在所有场景下都是如此，但我认为在强监管行业尤为突出：如果没有健全的评测体系为你提供信心，确保你能够以高精度、高稳健性、高可靠性部署自主系统，你根本无法上线心仪的应用，无法打造出真正能够规模化扩展的出色产品。
<details><summary>Original English</summary>
**>>**: And I think that's why like actually being able to set up really robust evals defines a really high-quality product. Um, in all cases, but I think especially in regulated industries, you just can't, um, deploy the applications that you want to without having really robust evals that give you confidence that you're doing it like deploying these autonomous systems with precision and robust, reliable, um, you know, great products that can actually scale.
</details>

**>>**: 好的。我们的时间快到了。大家可以在 LinkedIn 上与我们建立联系，或者今天在现场看到我们也欢迎随时交流。以上就是我们的演讲内容。
<details><summary>Original English</summary>
**>>**: Cool. Uh, we are almost at time. So, yeah, feel free to like, uh, you know, connect with us on LinkedIn or you know, just reach out if you, uh, see us, uh, anywhere, uh, today. So, but that's, uh, that's our presentation.
</details>