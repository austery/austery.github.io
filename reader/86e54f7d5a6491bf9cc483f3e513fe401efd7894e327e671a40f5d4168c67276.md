---
author: The Pragmatic Engineer
date: '2026-03-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=l_FI_80WiwU
speaker: The Pragmatic Engineer
tags:
  - agentic-workflow
  - fintech-automation
  - llm-infrastructure
  - evals-driven-development
  - ai-engineering-culture
title: Ramp 的 AI 实践之路：从原子化工具到千能智能体
summary: 金融平台 Ramp 的三位专家分享了他们在 AI 产品研发中的核心教训。重点介绍了从分散的数千个 Agent 向‘单一智能体，千种技能’的范式转变，深入探讨了 Policy Agent 的迭代过程、基础设施建设以及 AI 驱动下的工程文化变革。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Andrej Karpathy
companies_orgs:
  - Ramp
  - OpenAI
  - Anthropic
products_models:
  - Policy Agent
  - Omnihat
  - Ramp Inspect
  - Claude Opus 4.6
  - GPT-4o
media_books: []
status: evergreen
---
### Ramp：重新定义财务平台的效率

**Nick**: 今天我们要聊聊 **Ramp** 的 AI 实践。我会先简单介绍一下 Ramp 是什么，然后通过一个大家都能感同身受的简单报销案例——比如买咖啡——来展开。接着，我们会讨论今年在构建无数个 Agent 过程中学到的教训，以及在 2 月 6 日之后发生的**范式转移**。

<details>
<summary>Original English</summary>

**Nick**: Today we're going to talk about AI at RAMP. And I'm going to give a quick introduction into what RAMP is. Um really briefly we're going to walk through the simplest possible expense use case that you guys can all resonate because I see everybody's drinking coffee. And um then we're going to talk quickly about a lesson that we learned this year while we were building gazillion agents um and sort of the pivot in the paradigm that's happening especially after February 6.

</details>

**Nick**: 我们还会深入解析我们最受欢迎的智能体之一：**Policy Agent**（政策代理）。最后，我们会探讨为此所需的基础设施构建，以及最重要的——团队必须经历的**文化转变**，以便能够以最快、最有影响力的方式将产品交付给客户。简而言之，Ramp 是现代企业首选的金融平台，拥有超过 5 万名客户，我们的使命就是为您节省时间和金钱。

<details>
<summary>Original English</summary>

**Nick**: And um then we're going to double click onto how we built one of our most popular agents, the policy agent. Um and then finally we'll dig in into the infrastructure build that this is requiring to do on our side and in my mind most importantly the culture shift that needs to happen on everyone's teams in order to be able to operate in a way that delivers products into the hands of your customers in the fastest and most impactful way. Uh so without further ado uh quick intro about RAMP. Uh we are number one finance platform for modern businesses. We have 50,000 plus customers and we're in the business of saving you time and money.

</details>

### 从一千个 Agent 到一个 Agent 的千种技能

**Nick**: 过去，买杯咖啡可能要花你 15 分钟，因为你要处理三件麻烦的小事。Ramp 所做的就是压缩时间。从刷卡到写备注、分类交易、寻找并上传收据，再到匹配商家，这一切在 Ramp 都是**自动化（Agentically）**完成的。我们三年前就开始尝试 AI 单点突破，比如自动写备注，效果非常好。

<details>
<summary>Original English</summary>

**Nick**: So a cup of coffee usually takes about 15 minutes of your time because you got to do this three simple things which unfortunately take minutes. This compounds through the company and what RAM does in the simplest possible way we just condense time and return money back. Uh so a simple story of a transaction from tapping the card to writing a memo to classifying the transaction according to your GL to sourcing the receipt attaching the receipt um normalizing the merchant to your inventory of merchants is all done agentically at ramp.

</details>

**Nick**: 去年我们让每个团队自由实验，结果我们可能有了四种不同的方法来做同一件事。但现在，我们学到的是：你不需要构建一千个 Agent，而是需要驱动你的框架向**“一个拥有千种技能的单一 Agent”**演进。传统的软件关注 API 和操作，但在新范式中，软件正在接管一切。你要构建的是一个可以**反应、推理并行动**的自主系统。

<details>
<summary>Original English</summary>

**Nick**: We intentionally last year allowed each individual team to go and experiment and we ended up maybe with four different ways of doing the same thing. Um but instead you want to drive your framework towards a single agent with a thousand skills. Traditionally software would focus on only APIs and actions. In the new paradigm software is doing everything. So you want to focus on building an autonomous system of action that can react, reason and act without a human or with very little human supervision.

</details>

### Policy Agent：将自然语言转化为执行标准

**Viral**: 很多财务团队每天都在看成百上千张收据。如果你让我肉眼判断是否该批准某笔交易，我肯定会出错。**Policy Agent**（政策代理）会根据收据图片和所有交易数据进行推理。比如它能发现收据上有 8 位客人，计算出人均不到 80 美元的限额，从而判断这是一次合规的团队欢迎晚餐并予以批准。

<details>
<summary>Original English</summary>

**Viral**: So, a lot of finance teams are looking at receipts like this basically every day and maybe they might have hundreds or thousands of these. If you told me to look at this and decide if I should approve or reject this transaction, I'm probably going to make a mistake. So, policy agent basically reasons on this image and all the transaction data that we have and told me that there were eight guests in the receipt. It was below the $80 a person cap that we have internally and so policy agent told me to approve this transaction.

</details>

**Viral**: 我们借用 **Andrej Karpathy** 的话：**英语是新的编程语言**。我们直接将公司的报销政策文档变成规则本身。我们发现 AI 产品无法一次性成型，你必须从简单的开始。我们最开始只是想解决“和同事喝咖啡”这种低风险的小额交易。早期的教训是：Policy Agent 报错往往不是因为模型本身，而是因为我们提供给 **LLM** 的**上下文（Context）**不够，比如员工的角色和职位在判断限额时至关重要。

<details>
<summary>Original English</summary>

**Viral**: We kind of saw this as an opportunity to actually take out a page from Andre Karpathy saying that English is the new programming language and kind of turn the expense policy into the rules themselves. One of the main things that we realized across ramp is that we really needed to lean into the fact that AI products cannot be oneshotted. You need to start with something simple. One of the early learnings was that a lot of the reason that policy agent would be wrong would be less on the models themselves and more about the context that we were giving to LLMs themselves.

</details>

### 黑盒挑战：可追溯性与正确性的权衡

**Will**: 当我们开始构建 Policy Agent 时，我们也想过自动化所有财务流程，但必须从小处着手。系统越简单，迭代就越容易。随着我们从简单系统转向复杂系统，Agent 的自主能力和智能化程度提高了，但代价是失去了**可追溯性（Traceability）**和**可解释性（Explainability）**。小黑盒变成了大黑盒。

<details>
<summary>Original English</summary>

**Will**: When we first started building the policy agent internally, we went big. Let's automate all of finance. But when it came down to it, we actually had to start small. The simpler the system, I think the easier it is to iterate on top of it. As you go from simple to complex systems, your autonomy goes up, your AI seems smarter. But in exchange, you're losing traceability and explainability. A smaller black box becomes a bigger black box as the system becomes more complex.

</details>

**Will**: 所以从一开始你就需要极佳的**可审计性（Auditability）**。有趣的是，我们发现用户并不总是对的。有时候用户会出于懒惰或信任而批准不合规的报销，所以我们必须定义自己的“正确性”。我们每周举行跨职能的**标注会议（Labeling session）**来建立基准真相。为了提高效率，我们甚至用 **Streamlit** 快速开发了自己的标注工具，让非工程师也能参与进来。

<details>
<summary>Original English</summary>

**Will**: So one thing that is really important from the beginning you need really good auditability. Turns out the users are actually incorrect. They're wrong. So, we had to define our own definition of correctness. Um and to do that we had a weekly labeling session with across functions. We decided let's just build our own [labeling tool]. We used Streamlit. Non-engineers can go and personalize it.

</details>

### Evals：信心的基石

**Will**: 拥有了基准数据集后，我们就能快速迭代并建立起**评估系统（Evals）**。不要让完美主义阻碍你，我们从 5 个测试点开始。将 Evals 接入 **CI**（持续集成），大家就能安全地合并代码。这还能让我们在模型更新（如从 Claude 4.6 换到 GPT-5）时保持信心。我们还引入了**在线评估（Online Evals）**作为领先指标，比如监控 Agent 回复“不确定”的频率。

<details>
<summary>Original English</summary>

**Will**: With the ground truth data set, we were able to make quick iterations. You had evals and it's pretty important to have them early on. If you run it as part of your CI, then everyone now can safely merge in code. Having evals really helps make confident model changes. Online evals are also great. For us, part of that was how many unsure decisions we had, which just meant that the agent didn't have enough information.

</details>

### AI 基础设施：让产品团队专注价值

**Ian**: 在基础设施层面，Ramp 开发了名为 **Applied AI Service** 的服务。它不仅仅是一个 LLM 代理，还提供了三个核心能力：首先是跨模型提供商的**结构化输出**和统一 SDK，让团队只需更改一行配置就能切换模型；其次是强大的**批处理**能力，用于大规模数据分析和 Evals；最后是跨团队的**成本追踪**。

<details>
<summary>Original English</summary>

**Ian**: The core of how most of applied AI happens at RAMP is our applied AI service. There's really three main extensions: the first is structured output and consistent API and SDKs across different model providers. The other thing is batch processing and workflow handling. And then the last which is a pretty big deal is the ability to trace different costs across teams.

</details>

**Ian**: 我们相信，AI 的安全性和幻觉问题最终归结为**工具目录（Tool Catalog）**。我们现在拥有数百个内部工具，未来可能会有数千个。这让任何工程师都能快速构建原型，而不必从零开始。此外，我们还构建了内部后台编码代理 **Ramp Inspect**。目前，Ramp 超过 50% 的生产环境 PR 都是由这个 Agent 负责的。

<details>
<summary>Original English</summary>

**Ian**: We're pretty big believers that it all comes down to the catalog of tools that teams are building. We're up to many hundreds of these tools today and Nick thinks that this could be multiple thousands over time. We decided to build our own internal background coding agent, which we've called ramp inspect. Currently this month, Ramp Inspect is responsible for over 50% of PRs that we merge to production.

</details>

### 文化变革：编码从来不是最难的部分

**Ian**: 我们对比了两种团队。**A 类团队**关注影响力，能处理模糊性，沉迷于用户体验，积极采用新工具。**B 类团队**纠结于库的选择，在混乱时只懂得增加流程，过度关注代码风格而非解决问题。哈佛的一项研究显示，随着 AI 工具的加速，这种分化会越来越明显。

<details>
<summary>Original English</summary>

**Ian**: Let's pretend we have two different teams. Team A care about impact, handle ambiguous problems, adopt new tools and obsess over the user experience. Team B debate libraries, bike shed the details, and focus on performative code quality. There's going to be divergence.

</details>

**Ian**: 编码从来不是这类工作中最难的部分。资深工程师的价值在于**判断力（Judgment）**、对上下文的理解和预见风险的能力。你可以用 AI 更快地构建产品，但你也可能更快地构建出错误的东西。未来，公司将追逐以前无法负担的机会，重建那些以前因为太贵而不敢碰的系统。软件永远没有“完工”的一天，AI 给了我们更高的杠杆。

<details>
<summary>Original English</summary>

**Ian**: Coding was never really the hardest part of a lot of jobs. You're really compensating [senior engineers] for the judgment that they bring to the table. You could still build the wrong thing just a lot faster. Companies are just going to chase opportunities they couldn't afford to pursue. You're going to rebuild systems that are too expensive to touch. Software is perpetually not finished.

</details>