---
author: AI Engineer
date: '2026-10-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=obfPzbapMIM
speaker: AI Engineer
tags:
  - ai-agent-evaluation
  - observability
  - llm-as-a-judge
  - human-in-the-loop
  - error-analysis
title: 构建高可靠性高风险 AI Agent：基于 Langfuse 的全生命周期评测与可观测性实战
summary: 来自 Langfuse 的 Annabell Schäfer 与 Doneyli De Jesus 深入拆解了高风险场景下 AI Agent 的评测体系与工程闭环。内容涵盖错误分析、黄金数据集构建、多模态 Tracing 与 PII 脱敏、自动化 CI/CD 评测流水线门禁，以及人机协同（HITL）渐进式自动化落地上线的全套落地方法论。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Langfuse
products_models:
  - Langfuse
media_books: []
status: evergreen
---
### 高风险场景下的 Agent 评测挑战

**Annabell Schäfer**: 好的，我们正式开始。欢迎各位来到我们关于使用 **Langfuse** 评估 AI 应用的工作坊！我叫 **Annabell Schäfer**，是 Langfuse 的 AI 解决方案工程师。今天和我一起登台的还有我的同事 **Doneyli De Jesus**，他在 Langfuse 负责领导 AI 解决方案架构团队，专门与我们最大规模的客户合作，确保他们能够真正将可靠的 **AI Agent** 推向生产环境。

在我个人的“上一段职业生涯”中——之所以这么说，是因为那感觉就像过了整整一辈子——我曾在一辈子专门为医疗器械合规性开发 AI Agent 的公司工作。在医疗合规这种行业中，确保系统稳定运行是重中之重。我们必须确保拥有经客户严格验证的**基准数据集**（Ground Truth Dataset），并且大量采用了人机协同系统（Human-in-the-Loop）。当时我工作的大部分时间其实都在使用 Langfuse。在某个时刻我想：为什么不换个角色，去帮助更多正在将 Agent 推向生产环境的团队呢？尤其是在强监管行业中。所以我在大约七个月前加入了 Langfuse 团队。

但在我们深入正题之前，想先了解一下今天现场听众的背景。请问在座各位中，有多少人曾经参与过将 AI Agent 真正推向生产环境的过程？我指的是亲自作为团队的一员参与落地，而不仅仅是公司里有其他人做过。

<details>
<summary>Original English</summary>

**Annabell Schäfer**: All right, let's get started. Welcome everybody to our workshop on evaluating AI applications with Langfuse. My name is Annabell. I'm an AI solutions engineer at Langfuse. And I'm today joined by my colleague Doneyli who is leading AI solution architecture at Langfuse. So working with our biggest customers on making sure they actually shipping reliable agents to production.

I myself was in my previous life, how I like to call it because it feels like a lifetime, in a company building AI agents for medical device compliance. And in this industry it was super important to make sure we have ground truth data set that is validated by our customers and we also ran a lot of human in the loop systems and a lot of my time I actually spent in Langfuse and at some point I decided okay why not swap sides and also help other teams that are shipping agents especially also in regulated industries and joined the Langfuse team roughly seven months ago.

So before we dive right into it we wanted to get a little bit of a feeling of who is here today and who we are coming together with. So we were wondering who of you has brought AI agents to production before and with that I mean been part of a team doing it, not necessarily just someone in the company did it, so actually been part of a process to bring it to production?

</details>

**Annabell Schäfer**: 太棒了，举手的人非常多，这正是我们期望看到的！那么，又有多少人之前使用过 Langfuse 呢？好的，也有相当一部分。那其他类型的可观测性（Observability）或评测（Evals）工具呢？也有不少人，太好了。

最后再问一个问题：谁觉得自己已经彻底解决了 AI 应用的**评测难题**（Solved Evals）？

对于那些自信举手的朋友，活动结束后我非常欢迎你们来我们的展台，给我们讲讲你们是怎么做到的。因为在现实中，这确实非常困难。我想在座只要开发过 AI 应用，甚至只是日常和 ChatGPT 或 Claude 聊天的人，都深有体会。这之所以非常棘手，是因为 AI Agent 在底层系统指标（比如 HTTP 状态码 200、网络通信、响应延迟）完全正常的情况下，依然可能彻底失败。系统指标毫无异常，但模型输出的内容可能完全是错误的、出现严重幻觉，或者根本没有执行用户的意图。

不仅如此，随着模型能力的提升，测试的难度反而在加大。对于简单的任务，我们一眼就能看出对错；但当你在构建极其复杂、高风险领域的专业 Agent 时，评估 Agent 的表现往往需要深度的领域专业知识。判断它的回答是否优质变得非常昂贵且耗时。

<details>
<summary>Original English</summary>

**Annabell Schäfer**: Okay, that's good, amazing, it's a lot of people and we hoped to have this also. And who of you has worked with Langfuse before? Okay, quite some. And any other kind of observability and evals tool? Okay, yeah, also a few, amazing. And then finally, who has solved evals for AI applications?

For the confident hands, I would love you to come by at our booth and explain to us how. Because actually it is quite hard and I think all of you have experienced it if you're working with AI or also just chatting with ChatGPT or Claude. It is quite tough because AI agents can fail while the system metrics are completely fine. A 200 status code doesn't mean your agent did what it was supposed to do. It might have hallucinated, it might have answered completely off-topic, or it might have violated some critical compliance rules.

And on top of that, as models get smarter, evaluation gets harder. For simple tasks, it's easy to see if it's right or wrong. But when you are building agents for high-stakes, complex domains, evaluating agent performance requires deep domain expertise. Judging whether an answer is good or bad becomes very expensive and time-consuming.

</details>

### 经典软件测试与 AI Agent 评测的范式转移

**Annabell Schäfer**: 如果我们回顾传统的软件开发，事情就简单得多。在传统软件工程中，系统本质上是确定性的。我们编写确定性的单元测试：输入固定的参数 A，断言输出必然是 B。如果输出不是 B，测试失败，我们修 bug，重新跑测试，部署上线。

但在基于 **LLM** 的应用中，这种范式彻底失效了。首先，模型天然具有非确定性（Non-deterministic）。更重要的是，真实用户的输入是开放域的、充满无限种表达可能性的自然语言。你不可能为所有的输入输出穷尽单测用例。传统测试的覆盖率（Code Coverage）在概率系统面前失去了原有的防护意义。

高风险 AI Agent 的现实是：你不可能在部署前消灭 100% 的错误。即使你在离线阶段测试得再充分，上线后依然会遇到从未见过的极端边缘案例（Edge Cases）。因此，你必须建立一套持续从生产环境中挖掘问题信号的机制，确保发生过的错误能够被捕捉并转化为测试集，保证同类错误不再复发；甚至在更早的阶段防患于未然。这就是为什么我们需要在整个生命周期中将评测与可观测性紧密结合起来。

<details>
<summary>Original English</summary>

**Annabell Schäfer**: If we look back at traditional software engineering, things were much simpler. In traditional software, systems are largely deterministic. We write deterministic unit tests: given input A, we assert output B. If the output is not B, the test fails, we fix the bug, re-run the tests, and ship.

With LLM-based applications, this paradigm breaks down. First, models are inherently non-deterministic. Even more importantly, real user input is open-ended natural language with infinite variations. You cannot write exhaustive unit tests for every possibility. Traditional code coverage doesn't mean behavioral coverage for probabilistic systems.

The reality with high-stakes AI agents is that you will never eliminate 100% of errors before deployment. No matter how much you test offline, production will always surprise you with edge cases. Therefore, you need a mechanism to continuously mine for those signals where things are going wrong and make sure they don't happen again, or maybe not even at all in the first place. And this is why observability and evaluations must be intimately connected across the entire lifecycle.

</details>

### AI 工程化闭环 (The AI Engineering Loop)

**Annabell Schäfer**: 在 Langfuse，我们观察到所有成功将高可靠性 Agent 推向生产并持续迭代的团队，都遵循着一个核心工作流，我们称之为 **AI 工程化闭环**（The AI Engineering Loop）。

这个闭环包含几个紧密咬合的关键环节：

第一步是**跟踪与可观测性**（Tracing）。当一个 Agent 运行时，它不仅仅是一次单独的模型调用。它往往是一个复杂的多步骤图：路由决策、工具调用（Tool Calls）、检索增强生成（RAG）、意图分类、结构化提取等。通过 Tracing，你能够记录下每次执行的完整树状调用链，包括每次调用的延迟、Token 消耗、输入输出以及中间状态。

第二步是**构建数据集**（Datasets）。很多人试图通过拍脑袋去凭空编写测试用例，但最真实、最有价值的测试样本往往来源于生产环境中的真实调用。Tracing 帮助你筛选出那些真正值得关注的样本——既包括成功的正向范例，也包括失败的极端案例，将它们固化为可复现的黄金测试集。

第三步是**实验与评测**（Experiments & Evals）。当你修改了 Prompt、切换了底层基模（例如从 GPT-4o 切换到 Claude 3.5 Sonnet），或者重构了工具逻辑时，你怎么知道整体表现是变好了还是变差了？你必须在固化的测试集上运行自动化实验，使用确定的规则评估器（基于代码断言、正则匹配）或模型评估器（**LLM-as-a-judge**）进行打分。

最后一步是**持续监控与迭代**（Monitoring & Iteration）。评测不是跑一次就结束了，而是持续闭环的过程。通过生产监控捕捉异常，送入标注队列（Annotation Queues），由业务专家审核修正，再追加到数据集，反哺模型或 Prompt 的优化。

<details>
<summary>Original English</summary>

**Annabell Schäfer**: At Langfuse, what we see teams that successfully manage to ship reliable agents and continuously improve them follow is something we call the AI engineering loop.

This loop consists of several interconnected steps:

First is Tracing and Observability. When an agent runs, it's rarely a single LLM call. It is typically a complex, multi-step graph: routing decisions, tool calls, retrieval-augmented generation (RAG), intent classification, structured data extraction, and more. Tracing allows you to record the entire execution tree, capturing latency, token usage, cost, inputs, outputs, and intermediate states at every single step.

Second is building Datasets. People often try to come up with synthetic test cases out of thin air, but the most representative and valuable test cases come directly from real production traces. Observability lets you mine the interesting ones—both good examples and failure modes—and turn them into curated ground-truth datasets.

Third is running Experiments and Evals. When you change a prompt, switch an underlying foundation model (for instance, switching from GPT-4o to Claude 3.5 Sonnet), or tweak a tool definition, how do you know if you actually improved the system or introduced regressions? You run an offline evaluation experiment against your curated dataset using automated evaluators, whether deterministic rule-based checks or LLM-as-a-judge.

And finally, Continuous Monitoring and Iteration. Evaluation is not a one-off task. You continuously monitor production traces, route problematic runs into annotation queues for domain expert review, add newly discovered failure modes back into your evaluation suite, and continuously close the loop.

</details>

### 从低风险到高风险：不同场景的落地路径

**Annabell Schäfer**: 值得注意的是，不同的业务场景在这个闭环中的切入点完全不同。

如果你做的是一个**低风险应用**（Low-Stakes Application），比如一个公司内部使用的知识问答小助手，或者一个帮你自动回复父母繁琐提问的闲聊机器人，你的容错率其实很高。在这种场景下，你完全可以直接开发原型并迅速上线，一开始甚至不需要任何复杂的评测体系。你只需要先接入基础的 Tracing，然后在上线后慢慢观察生产日志，看用户反馈，逐步补充测试用例并改进提示词。

但如果你的目标是**高风险应用**（High-Stakes Application）——比如金融交易风控、医疗合规审查、保险理赔处理，或者直接操作客户退款与资金账户的企业级客服 Agent——情况就完全倒过来了。在这些场景中，一个单点错误可能导致成千上万甚至数百万美元的损失，或是触犯监管法律法规。

在高风险场景下，你**绝不能**直接把未经验证的自主 Agent 暴露给最终用户。成熟团队的经典打法是采用**渐进式落地**：
1. **纯后台影子模式（Shadow Mode）**：Agent 接收与人类相同的真实数据并给出建议，但动作不生效，仅与人类专家的决策进行比对评测。
2. **人机协同（Human-in-the-Loop, HITL）**：Agent 生成草稿或行动方案，必须经过专业风控人员审核批准（Approve）后方可执行。
3. **分层切片自动化（Data Slicing & Gradual Automation）**：通过长期积累的高置信度评测数据，将业务场景进行切片。只有那些模型表现达到 99.9% 准确率的极高确定性子场景才放开全自动执行；其余复杂或模糊的边缘案例依然强制走人工审核流程。

接下来，我们将通过具体的实战演示，来看看这套体系在工程上是如何实际搭建和运行的。下面有请 Doneyli！

<details>
<summary>Original English</summary>

**Annabell Schäfer**: What we observe with many of our customers is that, depending on your use case, there are different entry points into this engineering loop.

If you are in a low-stakes environment—for example, building an internal company chat assistant or an agent that answers questions from your parents so you don't have to—your tolerance for error is relatively high. In that case, you don't necessarily need a comprehensive evaluation suite on day one. You can build the prototype, deploy it with tracing enabled, observe production traces, gather feedback over time, and incrementally add test cases.

However, if you are building in a high-stakes environment—such as financial risk assessment, medical compliance, insurance claims, or enterprise agents directly issuing customer refunds and accessing banking data—the approach must be completely inverted. In these domains, a single error can mean thousands or millions of dollars in financial loss, regulatory fines, or severe legal repercussions.

In high-stakes setups, you cannot simply let an autonomous agent loose on real users. What mature teams do is adopt a progressive deployment strategy:
First, run in Shadow Mode, where the agent processes real data in parallel with humans without taking external action, allowing you to benchmark against human decisions.
Second, adopt Human-in-the-Loop (HITL), where the agent drafts actions or responses, but a qualified human expert must explicitly review and approve them before execution.
Third, data slicing for gradual automation. Over time, as your evaluation scores demonstrate near-perfect reliability on specific slices of data, you safely automate those high-confidence slices while keeping human review mandatory for complex or uncertain edge cases.

To see how this works in practice, I'm welcoming Doneyli on stage, and we're going to look together at how to trace agent execution, build datasets, configure evaluators, and close this loop in production.

</details>

### 实战演示：金融高风险 Agent 架构与全链路 Tracing

**Doneyli De Jesus**: 大家好！正如 Annabell 介绍的，我是 Doneyli，大家叫我 Don 就行。只有在我惹麻烦的时候，我妈妈才会连名带姓叫我 Doneyli。

今天我们将通过一个具体的真实场景来拆解这套体系：假设我们正在为一家大型金融机构（比如银行或信用卡发卡行）构建一个高风险的客服风控 Agent。这个 Agent 的核心职责包括处理信用卡交易纠纷（Disputes）、协助用户挂失被盗卡片、处理退款请求，以及核查潜在的欺诈交易。在这个场景中，只要 Agent 漏掉了一笔欺诈、错误地向骗子发放了高额退款，或者泄露了客户的敏感财务数据，后果都是灾难性的。

首先，让我们看一下**可观测性**（Observability）在系统运行中的第一线表现。

在 Langfuse 的控制台里，我们可以看到实时捕获的每一次用户交互 Trace。在 Agent 架构中，一个单一的用户请求往往会衍生出一棵庞大的调用树。例如，用户说：“我昨天在一家餐厅被多刷了 50 美元，我想申请争议并退款。”

进入该 Trace 详情，我们可以看到：
1. **根 Trace（Root Trace）**：记录了全局的会话 ID、用户画像、总延迟以及整体 Token 成本。
2. **多步骤 Span & Generation**：首先是一个意图识别与安全护栏（Guardrail）检查；随后是调用路由决策模块；紧接着触发了底层工具调用，比如查询核心银行系统的数据库（`query_account_transactions`）；然后模型根据返回的交易明细，决定调用欺诈检测评分工具，最后生成回复。

大家如果在屏幕上仔细看，会注意到我们启用了内置的 **PII 敏感数据识别与脱敏**（Personally Identifiable Information Masking）。在金融场景下，客户经常在对话中说出自己的社会安全号（SSN）、信用卡卡号（PAN）、CVV 码或家庭住址。在这些敏感数据被持久化存储到 Langfuse 之前，我们的脱敏管道已经在客户端或网关层自动将其识别并打码（Masking）。这不仅满足了 PCI-DSS 和 GDPR 的严格合规要求，也确保了后续进行人工审核排查的开发人员和风控标注员不会接触到明文敏感数据。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: Hi everybody. Like Annabell said, I'm Doneyli, but you can call me Don to keep it easier for everybody. Only my mom calls me Doneyli when I'm in trouble.

Today, we're going to walk through a concrete, high-stakes scenario: imagine we are building a customer support and risk assessment agent for a financial institution, like a bank or credit card issuer. This agent is responsible for handling card disputes, lost or stolen cards, transaction refunds, and identifying potential fraud. In this kind of environment, if the agent approves an unauthorized refund, fails to flag a fraudulent charge, or mishandles private financial data, the stakes are exceptionally high.

First, let's look at what observability looks like in practice.

Inside the Langfuse dashboard, we can inspect every execution trace as it happens in real-time. In an agentic architecture, a single user interaction triggers a complex execution tree. For example, a customer says: "I was overcharged $50 at a restaurant yesterday, and I want to dispute this charge and get a refund."

Looking into this trace, you see:
First, the root trace, which captures the overarching session ID, metadata, user context, overall latency, and total token cost.
Second, the nested spans and generations: an initial intent classification and safety guardrail check, followed by routing logic, followed by deterministic tool calls—such as querying a core banking ledger (`query_account_transactions`). The agent then takes that structured data, evaluates whether the transaction qualifies under bank policy, and formulates the response.

Notice also that we have PII identification and automated masking enabled. Any sensitive financial data—credit card numbers, Social Security numbers, bank account numbers, or CVVs—is automatically masked before being persisted into Langfuse. This is a critical prerequisite for regulated enterprises to remain compliant with standards like PCI-DSS and GDPR, ensuring that engineers and annotators reviewing traces never see unmasked customer secrets.

</details>

### 多模态音频与呼叫中心 Trace 分析

**Doneyli De Jesus**: 除了文字聊天机器人（Chatbot），现代金融客服中心很大一部分流量来自于呼叫中心（Call Center）的语音电话。

我们把多模态语音也直接整合进了追踪链路中。客户拨打热线电话，音频流进入系统，我们在此处触发一个语音转文字（Speech-to-Text）工具，同时保留原始音频的上下文引用。转录出的文本立即进入我们的 Agent 风控审查流水线。

在控制台中，我们可以直接回放音频、查看转写的实时文本对齐，并观察 Agent 是如何在各个决策分支之间流转的。比如在这个通话中，客户语气非常激动地声称自己遭遇了钓鱼诈骗，账户里的资金被转走了。系统不仅记录了语音转录，还打上了情绪分类标签，并将整个决策链路清晰地呈现在面前。

对于这种关键通话，如果在生产环境中出现了异常，比如用户中途愤怒挂机、客服系统超时，或者模型给出了模棱两可的合规答复，我们如何及时发现它？这就是为什么我们必须有一套强大的过滤和检索系统。你可以按照任意多维元数据进行切片：筛选出通话时长大于 3 分钟、意图属于“争议交易”、且包含了退款操作的所有 Trace。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: In addition to text chatbots, a huge portion of financial customer interactions happen through contact centers over voice calls.

We have integrated multimodal audio directly into the trace view. When a customer calls the support line, the raw audio comes in, triggers a speech-to-text pipeline, and the transcribed conversation is piped straight into our agentic evaluation pipeline.

Right here in the Langfuse UI, you can listen to the call recording, view the aligned transcript, and see every decision step the agent took. In one example call, a caller is distressed about an unrecognized wire transfer, indicating potential account takeover fraud. The system captures the audio, the transcript, sentiment metadata, and the underlying reasoning steps taken by the model.

If something goes wrong during one of these calls—for example, if a user hangs up frustrated, or if the agent gives a non-compliant policy answer—how do you find that needle in a haystack? That's why having flexible filtering is indispensable. You can slice your production data by tags, metadata, user ID, latency, cost, or specific business intents—like filtering for all calls involving transaction disputes over $500 where a refund was requested.

</details>

### 错误分析与人机协同标注队列 (Annotation Queues)

**Doneyli De Jesus**: 找到这些关键 Trace 后，下一步是什么？这就是构建高可靠性系统的核心秘密——**错误分析**（Error Analysis）。

在机器学习和 AI 工程中，很多人往往急于调整 Prompt 或去跑成百上千个自动评测，但他们甚至没有坐下来花几个小时亲自看一看真实的数据。**错误分析就是强迫你去直面失败**。你要看 50 个、100 个真正出错的 Trace，去弄清楚系统到底是在哪一步“翻车”的：
- 是意图分类器理解错了用户的方言？
- 是知识检索（RAG）没能召回最新的退款政策文档？
- 是模型在调用工具时给参数填错了日期格式？
- 还是模型在最后生成阶段自己编造了一条根本不存在的豁免条款？

在 Langfuse 中，我们提供了**标注队列**（Annotation Queues）来完美支持这一流程。作为架构师，我不可能一个人去给所有金融合规问题打分，因为我不是银行法务合规官。我可以在 Langfuse 里设置过滤规则：“把所有退款金额大于 200 美元且涉及争议的生产 Trace，自动抽取 10% 导入到‘风控合规审核队列’”。

然后，合规专员打开这个专门的标注界面，他们看到的不是冷冰冰的代码，而是一个直观的审核看板。合规专员可以逐项给这个 Trace 打分：
- **政策遵循度（Policy Compliance）**：是否严格遵守了发卡行退款合规章程？（是/否/部分符合）
- **事实准确性（Factuality）**：是否编造了到账周期？
- **语气专业度（Tone & Empathy）**：是否安抚了客户情绪？

如果合规专员发现模型的回答有误，他们可以直接在界面上填写“标准答案”（Ground Truth），并附上错误原因的备注标签（例如“未向用户索要刷卡凭证”）。点击保存后，这个被人类专家精细核准过的真实案例，就正式成为我们系统最宝贵的资产。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: Once you've located these critical traces, what is the next step? This brings us to what I consider the absolute cornerstone of building reliable systems: Error Analysis.

Too often, teams jump straight to prompt tweaking or running synthetic eval benchmarks without actually reading their real failure traces. Error analysis is the deliberate practice of sitting down and inspecting dozens of failed traces to understand precisely where the failure mode occurred:
Did the intent classifier misinterpret user phrasing?
Did the retrieval step fail to fetch the updated bank dispute policy?
Did the model pass malformed parameters to the SQL database tool?
Or did the LLM hallucinate an unauthorized policy exception during the final synthesis step?

To operationalize this, Langfuse provides Annotation Queues. As an engineer, I cannot unilaterally decide whether a nuanced dispute resolution complied with banking regulations—I am not a compliance officer. With Annotation Queues, I can define a sampling rule: "Route 10% of all production interactions tagged with 'dispute' and 'refund > $200' directly into the Risk Review Queue."

A domain expert—like a risk officer or compliance specialist—opens this queue and sees an interface designed for rapid, focused human grading. They evaluate criteria such as:
Policy Adherence: Did the agent follow standard operating procedures?
Accuracy: Were the stated transaction timelines correct?
Tone and Professionalism: Did the agent maintain an appropriate demeanor?

If the agent made a mistake, the human annotator can correct the output, provide the ideal ground-truth response, and tag the root cause (e.g., "Missing mandatory identity verification step"). Once submitted, this human-verified interaction is transformed from a production bug into our most valuable engineering asset.

</details>

### 构建高质量黄金测试集 (Datasets)

**Doneyli De Jesus**: 通过标注队列审核过的数据，可以直接一键沉淀到 **Langfuse 数据集**（Datasets）中。

大家必须明白：**一个高质量的黄金测试集，是所有评测的基石**。如果你的测试集本身就是随机编造的无意义句子，那无论你跑多少次自动化评估，得出的评分也是毫无意义的“垃圾进，垃圾出”（Garbage In, Garbage Out）。

一个成熟的高风险 Agent 测试集通常由两部分组成：
1. **边界案例与历史缺陷集（Edge Cases & Regressions）**：每一个在生产环境中被真实发现并确认的 bug，都必须被转化为测试集里的一条记录。就像传统软件工程中的回归测试（Regression Testing）一样，任何一次代码或 Prompt 的提交，都必须证明它没有让过去修好的 bug 重新复发。
2. **基准业务场景覆盖集（Golden Standard Cases）**：涵盖核心业务主流程的典型正面用例，代表系统期望展现的标准能力。

在 Langfuse 数据集中，每一条数据项（Dataset Item）不仅包含输入（Input）和期望输出（Expected Output），还可以附加任意复杂的结构化元数据（Metadata），比如用户类型、所属卡种、账户风险等级、预期的工具调用序列（Expected Tool Calls）等。这为后续的细粒度自动化评测提供了充分的判定依据。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: The traces reviewed in the annotation queue can be promoted directly into Langfuse Datasets with a single click.

It is impossible to overstate this: a high-quality, curated dataset is the foundational bedrock of all AI evaluation. If your test cases are low-effort, synthetic queries that don't reflect real user behavior, running evaluations on them is pure vanity—garbage in, garbage out.

A robust dataset for a high-stakes agent typically consists of two key components:
First, Edge Cases and Regression Test Cases. Every single meaningful failure identified in production must be converted into a permanent test case in your dataset. Exactly like regression testing in classical software engineering, whenever you deploy a prompt change or agent update, you must prove that you haven't reintroduced historical bugs.
Second, Golden Benchmark Cases covering standard core flows, representing the gold standard of expected agent behavior.

Inside a Langfuse dataset, each item stores the input, the ground-truth expected output, and arbitrary structured metadata—such as customer tier, transaction risk level, or the exact sequence of deterministic tool calls the agent was expected to invoke. This gives our automated evaluators the rich context required to perform precise evaluations.

</details>

### 评测器矩阵：从规则断言到 LLM-as-a-judge

**Doneyli De Jesus**: 现在我们有了基准数据集，接下来该怎么评估 Agent 的表现？

很多人陷入的一个误区是：言必称“大模型评测大模型”（LLM-as-a-judge）。但在工业级高风险系统中，**最可靠、成本最低的往往是确定性的代码规则评测**（Deterministic Evals）。

在 Langfuse 中，我们建议建立一个分层的**评测器矩阵**（Evaluator Matrix）：

**第一层：确定性规则评测（Deterministic & Code-Based Evals）**
- **JSON Schema 校验**：Agent 调用的工具参数是否符合规范？输出的结构化字段是否完整？
- **关键词与敏感词正则匹配**：是否包含了合规声明必须包含的法律免责声明语句？是否误输出了未脱敏的卡号？
- **代码断言与状态码校验**：是否严格在调用了身份验证 API 并返回 `SUCCESS` 后才执行转账工具？
这类评测执行耗时在毫秒级，成本为零，且结果具有 100% 的确定性。

**第二层：模型作为裁判（LLM-as-a-judge Evals）**
对于语言层面的复杂逻辑，比如判断回答是否“存在诱导性推销”、“是否语气合规”、“是否根据检索到的合规条例进行了正确推理”，纯代码规则很难覆盖。这时我们引入 LLM 评测器。

但使用 LLM-as-a-judge 绝不能写一句简单的“请给这个回答打分 1-5 分”。一个合格的工业级评测 Prompt 必须包含：
1. **明确的角色定位与评分标准（Rubric）**：对每一个分数档位（如 1 到 5 分）给出极其详尽的判定标准，说明在什么情况下给 3 分，什么细微瑕疵会扣到 2 分。
2. **少样本示例（Few-Shot Examples）**：提供由人类专家标注过的典型样例，让评测模型校准判决尺度。
3. **强制思维链（Chain of Thought, CoT）**：要求裁判模型在给出最终得分之前，必须先逐条输出推理分析过程（Reasoning）。这不仅大幅提高了评分的准确性与鲁棒性，而且当评测失败时，工程师可以清晰阅读裁判的思考过程，了解扣分背后的具体原因。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: Now that we have our ground-truth dataset, how do we actually grade our agent's performance?

A common misconception is that people assume everything must be evaluated using LLM-as-a-judge. In a real-world, high-stakes production environment, the most reliable, cost-effective evaluators are actually deterministic code-based rules.

In Langfuse, we advocate for a layered Evaluator Matrix:

Tier 1: Deterministic and Code-Based Evaluators
JSON Schema Validation: Did the agent output valid JSON matching the required tool definition?
Regex & Substring Matching: Did the agent include the legally mandated compliance disclosure? Did any unmasked PII leak into the final output?
State Machine & Sequence Assertions: Did the agent strictly call the identity verification tool and receive a success status before attempting the refund transaction tool?
These checks run in milliseconds, cost zero LLM tokens, and provide 100% deterministic reproducibility.

Tier 2: LLM-as-a-Judge Evaluators
For nuanced semantic qualities—such as assessing whether a response was manipulative, checking empathy, or determining whether a policy argument correctly followed from retrieved legal clauses—code assertions fall short. Here, we deploy LLM evaluators.

However, running LLM-as-a-judge effectively requires rigorous prompt engineering. You cannot just prompt the model to "Rate this answer from 1 to 5." A production-grade judge prompt must include:
A detailed Rubric: Explicit, unambiguous definitions for each score tier, explaining exactly what qualifies as a 5 versus a 4 or a 2.
Few-Shot Examples: Ground-truth examples calibrated by human domain experts to anchor the model's judgment.
Mandatory Chain of Thought (CoT): The judge LLM must output its step-by-step reasoning before generating the final score. This drastically improves grading consistency and allows engineers to audit the evaluator's rationale whenever an unexpected score is assigned.

</details>

### 离线实验对比与 Prompt 版本管理 (Prompt Experiments)

**Doneyli De Jesus**: 当评测器和数据集准备就绪后，我们就可以在沙箱环境中进行**离线实验**（Offline Experiments）了。

在开发 Agent 的过程中，团队最常做的事情就是改 Prompt。在 Langfuse 中，我们提供了集成的 **Prompt 管理与版本控制**（Prompt Management）。大家可以看到屏幕上，这个金融客服 Agent 的 System Prompt 目前已经迭代了 5 个版本：
- 版本 1 是初始的通用系统提示词；
- 版本 2 增加了对退款额度限制的硬性约束；
- 版本 3 我们尝试重写了身份验证的指令顺序；
- 版本 4 和版本 5 则进一步细化了反欺诈声明的语气规范。

现在，假设我们编写了版本 6 的 Prompt，或者我们想把底层的推理模型从 GPT-4o 切换成另一个更具性价比的模型，我们怎么确保这个改动不会引发灾难性的线上事故？

我们直接在数据集上发起一次自动化实验运行（Run Experiment）。系统会并行运行基线版本（Prompt v5）与新候选版本（Prompt v6），将数据集中的所有测试用例输入给 Agent，捕获全部的执行链路，并由我们配置好的评测器矩阵自动打分。

在实验对比视图中，两个版本的表现以直观的并排看板（Side-by-Side Comparison）展现出来：
- **政策依从度得分**：从 88% 提升到了 97%；
- **工具调用准确率**：保持在 100%；
- **单次平均延迟**：下降了 220 毫秒；
- **总 Token 消耗与成本**：降低了 15%。

更关键的是，我们可以点击“差异视图”（Diff View），直接筛选出那些“在 v5 版本中通过、但在 v6 版本中失败”的个别用例。这让我们能够在数秒内精准定位任何微小的潜在**能力退化**（Regression）。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: With datasets and evaluators configured, we can now run offline experiments before anything touches a production user.

During agent development, teams iterate on prompts constantly. Langfuse includes native Prompt Management and Versioning. As you can see on screen, our financial agent's prompt has five recorded versions:
Version 1 was the initial baseline.
Version 2 added strict instructions around transaction dispute limits.
Version 3 restructured the sequence of authentication tool invocations.
Versions 4 and 5 refined compliance disclosures and safety guardrails.

Now, suppose we draft Version 6, or suppose we want to test whether an open-weight model or a cheaper frontier model can replace our current LLM. How do we guarantee this change won't introduce breaking behavior?

We trigger an offline experiment against our curated dataset. Langfuse takes each dataset item, feeds it into both Version 5 (baseline) and Version 6 (candidate), executes the agent flows, and runs our evaluator matrix across all runs.

In the experiment comparison dashboard, we get a clean side-by-side view:
Compliance adherence score increased from 88% to 97%.
Tool invocation accuracy stayed at 100%.
Average latency dropped by 220 milliseconds.
Total token cost decreased by 15%.

Crucially, we can filter by regressions—cases where Version 5 passed but Version 6 failed. This allows engineers to immediately isolate regressions and fix prompt nuances before shipping.

</details>

### CI/CD 流水线与自动化部署门禁 (Deployment Gates)

**Doneyli De Jesus**: 手动在控制台里看实验对比固然很好，但我们真正想要的是把这个过程彻底自动化，将其嵌入到现代软件工程的 **CI/CD 流水线** 中。

在 GitHub 仓库里，我们为这个 Agent 项目配置了 GitHub Actions 工作流。当工程师提交 Pull Request 时，流水线会自动触发运行 Langfuse 评估测试。

我们为此设定了严格的**质量门禁**（Quality Gates）：
- **安全性与合规性得分**：必须达到 100%（0 容忍）；
- **业务主流程准确率**：必须大于等于 95%；
- **回归测试集失败数**：必须严格为 0。

大家看我的演示：我在这个分支上提交了一处 Prompt 修改，GitHub Actions 正在自动执行评测。我们调用 Langfuse Python SDK，在云端并发运行测试集，计算综合指标。一旦某项合规指标低于预设阈值，GitHub PR 检查就会直接变红并阻断合并（Block Merge）。只有当所有门禁条件全部通过时，代码才被允许合入主干并部署到预发或生产环境。

通过将评测固化为 CI/CD 质量门禁，团队从根本上告别了“凭玄学上线”和“提心吊胆看生产”的原始状态。代码、Prompt 和模型配置的每一次流转，都有详实的量化指标提供安全担保。

现在，我把舞台重新交还给 Annabell，让她为我们总结高风险系统的闭环演进策略，随后我们将进入现场问答环节。谢谢大家！

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: Manually reviewing experiments in the UI is great, but what we really want is to embed this into automated CI/CD pipelines as automated deployment gates.

In our repository, we have configured a GitHub Actions workflow. Whenever a developer pushes a PR that touches prompts, agent logic, or tool bindings, the CI pipeline automatically triggers an evaluation run against our Langfuse dataset via the SDK.

We define hard deployment gates:
Security and compliance score must be 100%.
Business intent resolution accuracy must be at least 95%.
Zero regressions allowed on the historical edge-case dataset.

Here on screen, you see the PR checks running. The GitHub Action spins up, triggers the evaluation job in Langfuse, scores each test case against our evaluators, and aggregates the results. If a change degrades compliance adherence below our threshold, the PR check turns red and blocks the merge. Only when all deployment gates pass is the PR approved for staging and production rollout.

By turning evals into CI/CD deployment gates, teams eliminate the anxiety of "vibes-based" deployments. Every prompt tweak, model upgrade, and code refactor is verified against a quantitative safety bar.

With that, I will hand things back over to Annabell to wrap up our framework before we take questions. Thank you!

</details>

### 避免全自动陷阱：人机协同的务实闭环

**Annabell Schäfer**: 谢谢 Don 的精彩演示！

我们在接触许多企业客户时，经常看到一种极其危险的极端倾向：一些团队希望“一步登天”，对管理层许诺“我们的 Agent 将完全自主，不出任何差错，全自动处理 100% 的业务流程”。

请允许我明确地提醒大家：在真实的生产环境，尤其是在高风险行业中，**如果你试图在第一天就追求完全自动化，结果往往是灾难性的**。你会得到一个质量低下、充满不可控风险的脆弱系统；即使早期勉强上线，一旦发生严重的合规事故或资金损失，整个项目就会被法务和管理层彻底叫停。

另一个极端则是完全依赖人工，由于害怕出错而裹足不前，导致 AI 技术的巨大生产力红利根本无法释放。

真正成功的工程方法是**务实的人机协同**（Pragmatic Human-in-the-Loop）：
你可以把自动化率看作一条随着时间推移不断提升的曲线。在初期，你的 Agent 可能只承担 10% 的独立决策，剩下 90% 的复杂交互全部由人工审核把关。但随着系统不断运行、生产 Trace 不断沉淀、标注队列持续纠偏、黄金测试集日益壮大，你的评测器会对更多细分子场景建立起极高的置信度。

在这个过程中，你可以通过精细的数据切片（Data Slicing），逐步把那些置信度达到极限的场景从“人工审核”迁移到“完全自动”，同时把有限的高级专家资源集中在最具挑战性的 5% 极端案例上。这样不仅保障了 100% 的绝对合规与安全，同时也能立竿见影地为企业节省大量人力与运营成本。

相关的演示仓库代码已经在 GitHub 上完全开源，大家可以在现场或活动后自行克隆研究。此外，周三 Donelli 还会带来一场专门关于“如何为 AI Agent 构建部署门禁”的深度专题演讲，欢迎大家参加！

剩下的时间，我们非常乐意回答大家关于系统架构、评测方法和生产落地的任何具体问题。现场我们还准备了一些 Langfuse 的定制贴纸，欢迎大家前来领取并与我们交流！

<details>
<summary>Original English</summary>

**Annabell Schäfer**: Thank you, Don.

What we see some companies and teams trying to do is this: they approach the problem with a mindset of "Please fix my agent, make it make no mistakes, and fully automate everything from day one."

Let me be very clear: in a production setting, especially in regulated, high-stakes industries, if you try to achieve 100% full automation right out of the gate, it will not turn out well. You end up with a fragile, low-quality system prone to unpredictable hallucinations, and sooner or later a compliance violation will shut the whole initiative down.

On the other hand, sticking purely to manual processes means you miss out on the incredible efficiency leverage that AI agents provide.

The winning approach is pragmatic Human-in-the-Loop:
Think of automation as a progressive slider over time. On day one, your agent might only autonomously resolve the simplest 10% of cases, while 90% require human approval or shadow review. But as you continuously capture production traces, curate datasets, expand your evaluator coverage, and optimize prompts, your confidence intervals expand.

You use data slicing to systematically transition validated categories into full automation, while keeping human experts in the loop for the ambiguous, high-risk long tail. That way, you maintain bulletproof compliance while systematically driving down operational costs.

The demo repository that Donelli showcased is open source and available online for you to explore. Also, Donelli is giving a dedicated talk on Wednesday on building deployment gates for AI agents, so be sure to check that out as well.

We'd love to use the remaining time to take your questions. We also have some cool Langfuse stickers up front—please feel free to come up, grab some, and say hi!

</details>

### 现场问答：存储架构、自托管与多裁判一致性

**Audience Member**: 我想请问关于底层存储和部署的问题：Langfuse 的数据存储对于 ClickHouse 是强依赖吗？因为我们公司在数据合规上有严格的要求，必须自主托管。我们能把它完全部署在我们自己的 AWS 环境里吗？

<details>
<summary>Original English</summary>

**Audience Member**: [Question regarding data store dependencies and hosting on AWS infrastructure].

</details>

**Doneyli De Jesus**: 这是一个非常好的架构问题！

是的，Langfuse 在存储架构上对 **ClickHouse** 确实存在强依赖。解释一下背后的演化历程：在 Langfuse 最早期的版本中，我们最初只使用了 PostgreSQL。但是随着产品的发展，客户量暴增，每天需要摄入并实时分析数十亿甚至数百亿级别的事件、Span 和 Token 日志，PostgreSQL 在这种高并发海量时序 OLAP 场景下逐渐达到了性能瓶颈。因此，我们将底层的数据平面全面迁移到了 ClickHouse，以保障极高吞吐下的秒级聚合查询性能。

关于数据导出与消费：如果你有自己的数据湖或内部审计系统，Langfuse 提供了极其灵活的数据导出能力。你可以配置将全量 Trace 数据自动流式导出到你的 Amazon S3 存储桶，或者通过我们的 REST API、CLI 工具以及 MCP（Model Context Protocol）协议直接对外消费这些数据。

关于部署模式：你完全可以 100% 部署在你们自己的 AWS 环境中！Langfuse 除了提供开箱即用的交钥匙（Turnkey）SaaS 云服务之外，本身也是完全开源的，我们提供了完整的**私有化自托管方案**（Self-Hosted Deployment）。如果你在 AWS 内部有现成的 EC2 实例或 EKS Kubernetes 集群，我们提供了预先打包好的 Docker Compose 和 Helm Chart 模板，包含 ClickHouse、Postgres、Redis 以及 Langfuse Web/API 容器，你可以一键拉起并在企业内网安全运行。

<details>
<summary>Original English</summary>

**Doneyli De Jesus**: Yeah. Well, Langfuse per se has a hard dependency for their stores with ClickHouse. That is just because in the evolution of the product, it started with Postgres. But then Postgres couldn't handle the scale that we achieved with billions and billions of events per day. That's when we moved the analytics data plane over to ClickHouse.

In terms of data integration, we also offer the ability for you to export your data: you can export it to S3, consume it via our REST API, the CLI, or via MCP if you want to pull data directly into other enterprise tools.

Regarding hosting on AWS: yes, you can host it 100% on Amazon. We offer our managed cloud offering, which is fully turnkey SaaS running on AWS, but if you want to manage the infrastructure yourself on your own EC2 instances or EKS clusters due to strict compliance policies, we have a fully packaged self-hosted deployment model ready to deploy with all components included.

</details>

**Audience Member**: 追问一下，如果在生产中大量使用 LLM-as-a-judge，你们是如何解决评估器的一致性（Consistency）以及标注者间信度（Inter-annotator Reliability）问题的？

<details>
<summary>Original English</summary>

**Audience Member**: I want to host it on... [Follow-up question on inter-annotator reliability and consistency of LLM-as-a-judge].

</details>

**Annabell Schäfer**: 这是一个极其核心且关键的专业问题！大家关心的正是：我们如何确保裁判模型（LLM-as-a-judge）的打分结果与人类专家的判断保持高度一致，而不是随性乱判。

在学术界，这个概念叫做**标注者间信度**（Inter-rater Reliability / Cohen's Kappa），即衡量多个独立打分主体之间的一致性水平。

在工业界的工程实践中，我们推荐的标准落地方法如下：
首先，抽取一批具有高度代表性的生产样本（例如 100 条涵盖各类业务场景和复杂边缘案例的真实对话）。由至少一名或多名资深人类领域专家（如合规官或风控经理）对这些样本进行严谨的人工标注，形成一份权威的黄金基准答案。

随后，我们运行待测试的 LLM 评测器，让它对这批相同的样本进行打分。我们将 LLM 评测器的输出与人类专家的打分矩阵进行对齐分析，专门计算两者的相关性与一致性得分。

如果发现分歧，我们会深入分析原因并持续优化裁判模型的 Prompt：补充更详尽的评分细则、明确扣分边界、加入引发分歧的 Few-shot 对照样本，直到 LLM 评测器与人类专家的判定一致性达到令人满意的阈值（例如 90% 以上）。

最后，在生产实际运行中还有一个非常实用的工程心得：**宁可接受前期的假阳性（False Positives），也绝不能漏掉任何假阴性（False Negatives）**。在高风险场景下，刚开始上线自动化评测器时，应该把过滤条件收得略微过严一点，宁可让评估器多报出一些疑似有问题的案例给人工审核，也坚决不要放过任何一个真实的违规行为。当系统平稳运行一段时间并积累了更多反馈后，再逐步微调阈值，降低误报率。这样才能确保系统在万无一失的前提下平稳演进。

<details>
<summary>Original English</summary>

**Annabell Schäfer**: Yeah, super important question! The question was about inter-annotator reliability and the consistency of LLM-as-a-judge evaluators to make sure they are actually catching what you want them to catch.

In essence, the entire goal is ensuring that the LLM judges evaluations in coherent alignment with how a qualified human expert would judge.

In practice, what you do is take a representative sample of interactions and have human experts label them to establish your verified ground truth. Then, you run your LLM-as-a-judge against that exact same sample and measure the correlation and alignment between the model's scores and the human annotations. If there are discrepancies, you calibrate the judge prompt by refining the rubric definitions and adding few-shot examples representing the divergent cases until the judge achieves high consistency with your human baseline.

And practically speaking, especially when evaluating live production data in high-stakes domains, a great rule of thumb is to tune your evaluators to tolerate a few too many false positives initially. You would much rather flag a few harmless cases for human review than miss a critical real-world failure mode. Once you have that safety net verified, you can fine-tune the thresholds down over time as your dataset grows.

</details>