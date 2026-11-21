---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yH7_SIIgI-Y
speaker: AI Engineer
tags:
  - agent
  - self-improvement
  - llm-evaluation
  - prompt-engineering
title: LinkedIn的递归自我改进系统：面向用户理解Agent的自动化闭环
summary: LinkedIn工程师介绍了其针对用户理解Agent搭建的递归自我改进（RSI）系统。该系统包含生产轨迹记录、评测裁决、归因反思、Prompt编辑提议、验证更新及留出集检验等七步闭环，并探讨了评测基准建设与减少方差的关键实践。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 递归自我改进系统概览与核心理念

大家好。我叫 Zui，今天我和 Saloni 一起来介绍我们在 LinkedIn 正在做的递归自我改进（Recursive Self-Improvement，简称 RSI）项目。在这项 RSI 工作中，我们重点关注用户理解（user understanding），非常高兴能分享我们在 LinkedIn 所做的 RSI 实践。首先，先高层次概括一下什么是递归自我改进。

<details>
<summary>Original English</summary>
Uh hello everyone. Uh so my name is uh Zui and today uh together with uh Saloni so we are going to present the recursive self-improvement uh project that we are doing at linking and for this RSI work we focus on the user understanding and yeah super excited to share the uh RSI work we did at linking. So first uh just a high level or overview on what is a recursive self-improvement.
</details>

递归自我改进是围绕某种 AI 系统构建的，这样做的目的是我们希望得到一个能够自我改进的系统，让它能够从生产环境轨迹（production trace）及运行中出现的问题中学习。这个 AI 系统可以是 LinkedIn 的某种 Agent，比如我们的职业 Agent，用来帮助 LinkedIn 用户和会员实现他们的职业目标。在日常开发工作中，我们会发现许多想要解决的问题；同时我们也会获取生产环境的追踪日志，记录生产流量中发现的问题。一旦有了这些信息，我们就会通过评测引擎（比如 AI Judge）来检查轨迹、识别问题并给出反馈。基于这些反馈，我们会持续迭代系统，从而构建出这样一个不断改进 AI 系统的闭环。我们想强调的关键一点是：在这个递归自我改进过程中，评测极其关键，它必须客观且与用户反馈高度对齐，因为这是找出瓶颈所在并指导 AI 系统下一步改进的关键。

<details>
<summary>Original English</summary>
So the recursive self-improvement is a build around some uh AI system and uh this is the purpose of doing this is we want to get a system that self-improvements uh self-improves. So it can learns from issues in production trace and that work. So the AI system can be some uh agent and I linking. So one example is uh our career uh agent to help uh our uh linking users members to achieve their career goals and from the agent so uh and there's uh many daily development work that we discover the issues we want to address and also we will get the production traces and that we can uh so they like we can log the issues we found during the production traffic and once we have this informations So we will have some evaluation engine for example the ar judge and to uh check our uh traces and to identify the issues and gives feedbacks and based on the feedbacks and we will uh use those feedback to keep uh continuously uh iterate our system. So we build this kind of like a loop to keep uh improve our um AI system. And uh one key thing we want to uh call out is uh during this uh recursive self improvement process the evaluation is very critical and it must be objective and well aligned with the user feedback because this is a key to uh like identify where the bottleneck is and guide the next step for the uh system AI system improvement.
</details>

### AI 系统组件与优化梯阶

接下来我们想说明一下 AI 系统中有哪些组件可以通过 RSI 进行优化。这里以 Harness（或者说调度器 Orchestrator）为例。我们可以通过 RSI 优化不同的组件：
- **规划与逻辑（Planning and Logics）**：用于调度执行并制定决策路径。
- **上下文与记忆（Context and Memory）**：保存和管理会话状态。
- **工具接口（Tool Interface）**：与外部和内部的 API 及数据集进行交互。
- **产物存储（Artifact Storage）**：存储输出内容和生成日志。

在这些组件之上，我们必然具备评测逻辑，用来评估各个组件并帮助我们持续改进 AI 系统。另外需要注意的是，所有这些 Harness 都由基础 LLM 模型驱动，但在当前的 RSI 范畴内，优化基础模型本身并不在范围之内，我们现阶段首先专注于 Harness 的优化。

<details>
<summary>Original English</summary>
And uh next we want to uh uh like describe like show uh what kind of like uh which component of the AI system we can uh optimize. Uh so here take the harness uh as as an example or like as orchestrator. So there are different components we can uh use we can uh optimize by using the RSI. So for example the first is a planning and logics which is used to orchestrator orchestrates execution and make a decision uh past and the second is a context and the memory where we preserve and manage the session state and the third one is a two interface that interacts with external and internal APIs and data sets. The last uh last but not least is artifact storage uh that where we stores outputs and the generation logs and so they like uh and we are on top of those we definitely have some like evaluation uh logic and uh so that to help us to evaluate uh each um component and help us to keep uh improve the uh AI system and we want to uh like uh uh and another thing to uh keep in mind that all those uh like harness is a powered by the base uh iron model but for the RSI uh so it's currently the optimize of this base model uh itself is not in uh scope but we focus on the uh harness optimization uh first
</details>

这里我们展示利用 RSI 优化 AI 系统时可以攀登的优化阶梯。通常这是一个从简单流程开始的过程：
- **L0 / 起步阶段**：我们可以专注于 **Prompt 更新**，因为这是持续迭代 AI 系统最简单、最直接的方式。
- **L1 阶梯**：在 Prompt 之后，我们可以继续优化 AI 系统的**结构化上下文（Structured Context）**。
- **L2 阶梯**：在结构化上下文优化之后，我们可以扩大范围，去**自动设计整个工作流**，这类似于一种元信息设计。
- **更高级别**：之后我们可以优化 **Harness 自身代码**，最终甚至可以深入优化**优化器自身的代码（Optimizer Code）**。

这些优化阶梯的复杂度逐步提升。目前在我们的项目中，重点是 Prompt 优化；但未来显然会把范围扩展到越来越复杂的优化层级。

<details>
<summary>Original English</summary>
and uh here we want to uh like show uh like this is the ladders that we can climb to optimize the uh AI system by using the uh RSI. So uh at the beginning so typically so this is a start from simple uh process at the beginning we can focus on the prompts uh updates because this is a most uh this is the easiest and the most straightforward way to uh keep iterate our AI system and after that uh we can uh continue to optimize the structured context of the AI system and uh uh the and the for the this is the L1 uh ladder and for the L2 tool ladder and which is after the structure context optimization. We can uh expand our scope to design the auto automatically design the entire uh workflow and uh uh so this is kind of like uh like a meta information uh design and uh after that and we can automize the harness code uh itself and as at the end we can uh go very compactly to optimize the optimizer code uh itself. So this is kind of the different optimization ladders uh with increasing complexity and uh uh for our project. So currently uh our active focus is a prompt uh optimization but uh uh definitely like moving forward we are extend our scope to uh more and more complicated uh optimization uh in future
</details>

### RSI 的七步循环策略

这里展示我们的 RSI 策略。我们将 RSI 流程拆分为七个步骤：
1. **运行 Agent 并生成样本**：针对我们要优化的职业 Agent，给定 Query 生成输出，并记录追踪轨迹（例如使用 Lastmile 追踪），获取 Agent 的执行轨迹和 Trace。
2. **通过评测引擎评估**：运行评测引擎（如 Judge）并获取评测输出，指出表现好与不足的地方，为后续迭代提供依据。
3. **Agent 反思（归因，Root Causing）**：进入 RSI 闭环内部，根据 Judge 输出分析导致不佳表现的根因是什么，判断究竟是 Agent 问题、模型问题、Prompt 问题、工具问题，甚至可能是 Judge 或评分细则（Rubric）本身的问题。
4. **生成编辑提议（Edits Proposal）**：根据识别出的根因生成修改建议。目前主要是 Prompt 建议，未来随着阶梯攀升也可以是工作流设计、Harness 代码甚至优化器代码的修改。
5. **验证修改**：有些修改可能带来正面效果，有些则可能是负面的，因此使用相同的评测引擎（相同 Rubric 的 Judge）对提议的修改进行验证。
6. **演化并更新 Prompt**：筛选出优质候选修改后，顺理成章地更新 Prompt，使其适应提议的修改。
7. **留出集评测验证（Holdout Evaluation）**：在留出数据集上再次运行评测，确认优化后的新系统确实优于旧系统。通过验证后正式更新 Prompt，使其成为新的基准，后续按一定节奏持续进行 RSI 迭代。

<details>
<summary>Original English</summary>
and uh here we want to show our uh uh RSI uh strategy. So we break down our uh RSI uh uh process uh into seven uh steps. So the first step is to uh run the agent and uh generate some uh samples. So basically like for our career agent uh that we are optimizing for. So given a query we'll generate some uh output and we will lock those uh process in the uh traces for example the last miss traces and uh once so this is basically just the uh like the uh kind of the agent uh trajectories and the traces that we can uh uh use to uh optimize and once we got those information the next step step two is we uh runs through the evation uh engine for example the judge and to uh get some judge uh output to tell us uh where we are uh good at and we are where we are not good at. So to get the uh uh future iteration and then uh once we get the uh um judge output then we go uh we we are going to the RSI components and uh starting from the uh step three. So this is a kind of the RSI in the inside the RSI loop and the first step is we will uh we will do the agent reflection uh sometime we also call it a root causing so they like based on the judge uh output we want to understand what is a root cause uh that we don't have a good uh output for example is this is a agent issue a model issue u prompt issue or like a two uh two two issue or some other issues or sometimes it's Even it can even be a judge issue or rubric issue. And uh once we got the root cause and uh uh we will uh the next step is to uh based on the root cause uh we identified we want uh we can generate some uh addits proposal. So uh currently the addits proposal are just uh prompt but as we are climbing the climbing the ladder uh for the SI loop. So in future this uh additis can also be some like a new design of the workflow the harness code or even the optimizer optimizer code and uh uh so yeah that's uh step four to generate the edits proposal and the next step is to uh validate our edits because uh some edits can be uh good some can be bad uh so we will use the same uh evaluation engine for example the same judge with the same rubrics to uh to uh evaluate uh our addit validation and uh uh once we found some like a good candidates and we will uh naturally the next step is to uh evolve our uh prompt to adapt the uh the uh the proposed edits uh we have and uh uh once we uh once the prompt is uh updated. So the very last step which is a step seven here is we run the evaluation uh again on a hold up side and to confirm uh our uh this kind of the uh new system is indeed performs better uh than the old system after the SI optimization and uh uh this will and also like uh after this hold out validation uh like we will make the uh prompt updates and this will become our uh new baseline and uh and we are uh in future we will like continue to do this uh RSI uh iteration to keep improving uh our system uh with some uh cadence.
</details>

### 用户理解 Agent 的输入输出与 Judge 评分机制

接下来我们深入各个步骤的细节。首先来看第一步：我们正在优化的具体 Agent 是 LinkedIn 的**用户理解 Agent（User Understanding Agent）**。它的输入非常简单，就是一个 Member ID（即 User ID）。通过该 ID，我们可以拉取该用户的搜索历史、个人资料数据（Profile Data）、地理位置数据及偏好数据等。用户理解 Agent 接收这些历史行为和资料数据作为输入，执行一系列 Agent 合成步骤，并生成用户理解输出。

该输出的高层结构包括多个描述该用户的字段。例如“偏好职位名称（Preferred Job Title）”字段：
- **偏好职位**：如网络经理（Network Manager）、客户经理（Account Manager）等。
- **置信度（Confidence）**：反映 Agent 认为该职位确实是其偏好职位的确信程度。
- **引用数据（Citation Data）**：给出依据，例如在用户的保存搜索历史中该职位高频出现，从而成为强有力的支撑证据。
- **推理过程（Reasoning）**：输出 Agent 认定这些职位的推理逻辑（如明确偏好锚点、主要职位、保存搜索关联等）。

<details>
<summary>Original English</summary>
Uh okay. Yeah. Next uh like uh we are we can uh like dig deeper into uh each step so that we can get uh so so to help you to understand more details on what we are uh doing here. for example, what is the agent we are optimizing and what is like a steps uh like a detail steps uh in each uh this high level steps to uh help us uh to help you to understand more of of our uh SI work here. So the first step I I want to show uh so this is the first uh the step we generated the output and the generated trace and uh so first we want to I want to uh help you to understand the agent uh we are optimizing here. So this is a uh user uh understanding uh agent uh at linking. So uh so like you can see we uh in this slide we are showing the input and the output of this uh agent. So the input is just a simply member ID also it's just a user ID and uh uh by uh given user ID we can fetch uh some information uh of this user for example this user search history uh profile data uh and also some like a location data and the preference data those kind of things and we have this user understanding agent to uh like take those users uh history or behavior data profile data as a input and uh do the uh do a lot like this kind of um uh agentic uh synthesize steps and we generate the uh output. So for this output we call it is a uh memor sending or the user understanding uh output. So here is a high level uh structure of the uh this output is so given a member. So we will generate some uh fields to describe uh this uh member based on our agent understanding. For example, what is the preferred uh job title uh of this member? This is just one uh field of this uh this user understanding uh output. So for this one, this is just a example of the preferred job titles. So it can be some like a network manager, account manager those kind of things and we'll give a confidence on like how confidence this uh agent think uh like this is indeed the preferred job titles for this user and uh also uh we'll get uh generate some uh citation data. So they like this is the uh like why the this is where we can tell why the agent think those uh titles is a preferred job title for this particular uh member. Uh for example it could be uh the reason could be like uh in the users uh save the search history like those job titles uh appears very frequently. So the agent think oh this is a strong evidence uh that to support that the preferred job title is a network uh manager uh for this uh for this uh user and uh uh as a uh and uh finally this agent can also output the reasoning on like why like just a reasoning like why the agent think those are preferred job titles like for example the state preference anchors the primary title save search agent uh adjacent one those kind of So this is a kind of uh uh one example of the user understanding agent that we are optimizing.
</details>

第二步，在拿到 Agent 轨迹后，运行 Judge 对输出质量进行打分。对于该 Agent，Judge 依据产品定义的 Rubric 在超过 15 个任务维度上打分。Judge 的输出示例如下：针对某个用户生成总体评分（例如 2.31 分），并展示各维度的得分明细（如目标总结维度、偏好职位名称维度等），同时附带评分理由（Notes / Verdict），说明为什么给出该分数。Judge 采用 1 到 3 分的量表：1 分表示质量不佳，2 分表示尚可，3 分表示质量优秀。

<details>
<summary>Original English</summary>
So the step two is once we uh got this uh agents trace and we'll run the judge and to uh get a quality readings of this uh of the agent uh output and uh for this particular user agent uh the score is over uh 15 uh task of the dimensions by judge where are some um product uh defender uh rubrics. So here is one example of the uh judge uh output. So you can say for particular um member the user and we will generate a judge uh score which is 2.31 and uh we will show and it will also tell like this score is for uh which um and [clears throat] it'll show the breakdowns uh of the you know the each dimensions score for example the go summary dimensions and we also have some other dimension for the the second one is a prefer job title dimensions and for each this kind of dimensions we give a detailed uh score uh for each dimension and also the notes. So the notes is uh just the rationale also the uh vertx like why uh we give this score uh to this uh to this particular uh dimension and for this particular uh judge is the agent. So the uh judge score is one to three uh scale. So the score one means uh this is not a high uh good is not a good yeah the quality is not good and the two is a fair uh quality and the three means this is a very good quality. Yeah. And uh uh so yeah that's our uh um judge and uh
</details>

### 反思阶段与提议生命周期

获取每个维度的得分后，第三步是运行 Agent 反思流程。如果得分较低，我们需要找出导致低分的根本原因。反思步骤内部细分为四个微步骤：
1. **聚类（Clustering）**：根据出错维度将失败的数据行进行分组。因为生产日志中包含大量用户样本，这一步是纯聚类，不产生额外开销。
2. **L2 Judge 诊断**：在每个类别内部，调用模型对每行进行诊断，为每行分配根因和标签，判断低分究竟是由 Prompt、Agent、Harness、代码，还是由 Judge 或 Rubric 自身引起的。
3. **合并去重（Deduplicating / Merge Issues）**：由于第二步生成的根因是自由文本，表述不同但实际指的是同一问题（例如一行表述为“缺少用户资料数据”，另一行表述为“资料数据未展现浏览历史全貌”，两者本质相同），因此需要合并相似问题，提取规范化的根因标签。
4. **分组与排序**：根据提取出的规范化问题，按频次进行分组和排序（此步无需 LLM 调用），生成供人工审阅的计分卡，明确系统的主瓶颈；同时将这些根因缓存/保存下来，反哺给后续轮次的 L2 Judge 作为先验诊断参考。

<details>
<summary>Original English</summary>
after we got the judge score uh for each dimension of our user understanding agent and the next step is we will run this uh agent reflection process. So as we mentioned earlier so this is a kind of uh uh process for us to understand okay if this is a low score then what is the root cause uh lead to the uh this low score. So uh this is a so for this uh step three so actually uh internally there are four uh like we can call it a mini steps for the agent reflection. So the first step is a clustering. So we are group the failing uh rows because like in a production trace so we are we will have a lot of like uh examples a lot of users and we will group uh the those users also the traces by the failing uh dimension. So for this uh step so this is just a pure clustering uh without uh any um cost and uh once we get the clustering and uh uh so the next step is we call it L2 uh judge so b within each uh class. So we are run the um uh cause to diagnose uh each row and uh and then for each row we are assign a root cause and plus tag. So b like this is a u uh place that we uh can like rely on the to uh let us know uh uh if we think uh this is a for example this dimension has a low score is that due to the prompt issue uh agent issue harness issue code issue or like even the judge issue or rubric issue. So they will be covered by the root cause and tag uh here. So uh the then once we get the perole level root cause and the tag so the next step is to merge the uh issues because uh in the second step uh so we it's just a we is based right so so the root cost is more like the free tax but uh uh some root cause uh even the tax is not um uh exactly the same but they may just describe very similar thing or uh so that's why like we want to do this kind of uh dduping so we merge the issues if we think uh the root cause is uh near uh duplicates so uh I can give one example here so for example uh for one row for one member uh the root cause can be uh the members uh profile data is uh missing uh and another row uh uh so the arm can the profile data is uh not showing the full picture of this users uh like a browsing history or whatever. So b like they are uh both of them are describing the same thing. So the profile data is not supporting the uh this agent output. So uh but they just use a different text. So that's we are like that's why we need this um kind like a dduplication uh step to merge the similar issues so we can get some uh canonical uh issue I say the roo uh labels and uh once we finish the step three so the next step is to based on the uh canonical issues we found we are group and rank them by the uh frequency and uh this step uh there's no am required so this is just to help us to understand uh what is the major issues bottlenecks uh in our uh AI system and uh once we uh do the group and ranking and we are generated the uh scorec card for the human to uh get uh to just uh get a human to act on to uh continue uh iterate our uh AI system and all uh and also we are uh uh like basically just a cache I say save those root cause uh somewhere and it will continue use this for the self question loop. So that's why so you can see uh like there's a arrow here like a go back to the uh L2 judge. So be like it will guide us on like what is basically the pri prior diagnose prime on the next turn. Uh so that is easier for the uh like to judge to identify the issues uh in future runs. So that's uh uh like the what we do for the agent uh reflection.
</details>

在反思明确了失败根因后，第四步自然是生成修改提议。在整个提议生命周期中：
- 结合 Judge 提供的证据和反思产物，通过特定方法生成提议。本项目中使用 GEPA（原录音中音近 JPA/Japa 的算法），在给定 Trace 样本的情况下以 Mini-batch 方式提出新的 Prompt 修改方案。
- 随后筛选出有希望的 Prompt，送入验证集进行验证。
- 一旦在验证集上确认效果良好，便将更新后的 Prompt 部署到生产环境，确立为新的基准线，以此循环往复。

<details>
<summary>Original English</summary>
Uh so the next step is a generator edits proposal because from the step three uh the previous slide we know uh we already know okay so what is the root cause right why like the agent fails so the next step is naturally like given uh those root cause those issues we want to fix so what what can we do right what is u new edits we want to propose and uh here like we have uh again like this kind of we call it the proposal uh life cycle. So based on the judge uh evidence and the reflection artifact we will propose the input and uh we will run uh some methodology. So uh for this project uh we are using the uh JPA to uh given the uh you know the uh lookout and to uh propose the new prompt change and uh and like given a trace sample we do it in a mini batch uh fashion and uh and generated the new uh prompt updates proposal and once we generate the promp uh updates proposal we'll uh select the window prompts and do the uh validation validation uh set and uh once we uh found a good prompt candidates and we run the uh you know the validation set and we think uh it is uh become uh it is a good uh prompt updates and uh we are just um updates our prompt in our system. So this will be and into the production and this will become our new uh kind of like a baseline and we will continue to uh do the uh like the future uh RSI uh iterations. So yeah that's uh kind of like the and uh yeah that's a kind of like the entire life cycle of this RSI uh iteration.
</details>

### 当前三大工作重心

我们当前在 RSI 工作上有三个主要重心：
1. **质量（Quality）**：进行了多次迭代来提升 Agent、Judge 和 RSI 循环的质量。例如开展了广泛的人工标注以提升 L1 和 L2 Judge 的质量；对评测 Judge 的方差进行研究和分析，缓解 LLM 固有的非确定性影响；基于标注和方差分析向 Judge 与反思流程推送质量更新。
2. **自动化（Automation）**：因为 RSI 包含七个步骤，我们构建了对应的工作流，可根据需求按周、双周或按月定期触发，自动运行并持续建议 Prompt 更新。
3. **生产更新（Production Updates）**：目前仍保持 Human-in-the-loop（人在回路），人工审核确认生产质量；未来随着质量足够稳定，逐步减少人工介入，达成更高程度的自动化状态。

接下来由 Saloni 分享具体成果与经验心得。

<details>
<summary>Original English</summary>
And uh next this slide uh we want to show our primary focus for this RSI work. So we so currently we have three major focuses. So the first is the quality, second is automation and the third is a production uh updates. So quality uh like we are focused on the different uh uh things uh on the quality. So um and we uh did many uh iterations to trying to improve the uh quality of our agent uh judge and this RSI loop. For example, we did extensive human annotations so that we can improve the judge both the L1 judge and the L2 judge uh quality and we did uh many study and analysis on assess agent judge uh uh variance so that we can uh make sure we can kind of mitigate the impact from the non nondeterministic nature of the LM and uh uh the third one is we push quality updates to both Asian judge and RSI reflection uh based on our annotation and the variance analysis uh mentioned uh above. So that's on the CI side and the second focus is uh automation uh because as we mentioned so there are seven steps in the RSI iteration and uh so that's why like here like I we build a uh this kind like workflow so that we can kick off this workflow with some uh cadence for weekly or bi-weekly or monthly based on the needs uh so that it can u automatically running and keep suggesting the uh like the prompt updates uh with some uh cadence and the third focus is production uh updates. So definitely like we want to uh build a uh useful uh RSI uh system that can help uh keep continuously uh improve our uh you know product. So that's why like we the third focus uh for the our our uh work is to make updates to the current agent in production with human in the loop uh like for now to uh ensure like the production uh uh quality uh is there but later like once we think uh the quality is good enough like we gradually uh uh like reduce the human effort and uh and hopefully we can achieve a higher automation uh kind of uh state. Uh cool. Yeah. Next, I will hand over uh to Saloni to uh share more details about the outcomes and uh learnings of our our work.
</details>

### 人工标注与 L1 Judge 评测对齐分析

>> 我来共享屏幕。

>> 好的。

你能看到我的屏幕吗？

>> 可以。

>> 大家好，我是 Saloni。前面介绍了 RSI 系统的设计，但在实际落地中，最有意思的部分之一在于：当我们试图让整个过程变得可靠时，实际会发生什么。特别是我们认识到，**评测器的质量与优化系统自身的质量同等重要**。

我们想强调两项主要成果：
1. **成功将初步 RSI 改进推向生产环境**：通过所介绍的闭环，合并了第一个由 GEPA 优化的 PR。这些改动在部署前经过了人工审核和量化评估，是 RSI 走出实验性工作流的重要里程碑。
2. **显著提升评测质量**：我们在用户理解 Judge 的人工标注以及判别差异分析上投入了大量精力。分析揭示了评分细则（Rubric）和反思系统中的多项顽疾，针对性的改进增强了可靠性并降低了评测方差。在信任系统自动优化 Agent 之前，必须先确保驱动优化的反馈本身是值得信赖的。

<details>
<summary>Original English</summary>
>> I will share my screen.
>> Sure. Yeah.
Um, can you see my screen?
>> Yeah. Yeah.
>> Yeah. Um, so yeah. Hi, I'm Salon. And so far we described how the RSI system is designed. Uh, but one of the most interesting aspects of this work has been understanding what happens when we actually try to make this process reliable. And in particular, we learned that the quality of the evaluator is just as important as the quality of the optimization system. So let's walk through some of those um findings. Um so there are two major outcomes we want to highlight. So the first is that we successfully like deployed our initial RSI improvements into uh production which was like um landing a first PR which was optimized by Japa and through the loop which we just described. Um so these changes went through human review and quantitative measurement before deployment and it was an important milestone in moving RSI like beyond just an experimental workflow. The second major improvement was around like um evaluation quality where we invested substantial effort and like human annotations for the user understanding judge and as well as like analyzing where its judgment sort of like disagreed with like human reviewers. And this process revealed several recurring weaknesses in both our evaluation rubrics as well as our like our reflection system. And by investigating those disagreements, we were able to like make targeted improvements which further strengthen the reliability as well as like reduce the evaluation variance which we have. And uh before we could trust a system to like improve an agent automatically, we had to understand whether the feedback driving those improvements was also itself trustworthy. And this was like a major area of our engineering work.
</details>

为了评估 L1 评测 Judge 的质量，我们分析了大约 180 到 200 份人工审核结果，重点观察 Judge 与人工审核者在不同评分区间及各维度上的对齐情况。从图表数据来看：
- 在打 1 分的输出上，完全判断对齐率约为 55%；
- 打 2 分的对齐率约为 57%；
- 打 3 分的对齐率则上升到约 80%。

这表明 Judge 在识别优质输出方面明显强于区分不同程度的较差输出，同时我们发现很多最低分往往过于严苛。各维度的对齐度也差异很大：职位偏好维度的一致性最弱，专业领域（Expertise/Domain）对齐率约为 47%，工作类型（Work Type）约为 50%。这说明各任务维度的评测质量并不均衡，某些维度需要更清晰的定义、更好的证据处理规则和更明确的打分指引。

<details>
<summary>Original English</summary>
Um to so to understand the quality of our like um L1 which was our evaluation judge. We analyzed about 180 to 200 human reviews. We were particularly interested in how the judge agreed with human reviewers both across different score categories and across the individual evaluation dimensions. Starting with the chart on the left, we see basically that um for outputs we assigned a score of like one um a full judgment alignment was approximately 55% and for score two it was around 57%. But for score three the alignment increased to approximately like 80%. Which indicates an interesting pattern which was that the judge was considerably like better at recognizing stronger outputs than it was at like distinguishing between different sort of like weaker outputs. And we found that many of its uh lowest scores were like also overly harsh. And um now looking at the chart on right agreement also varied significantly across like different dimensions where higher preferred dimensions like titles had like the weakest observed alignment as well as like uh domains or like the expertise or area of work was around like 47% and the sort of like work type was around 50%. which told us like the evaluation quality was uniform across all the tasks which we cared about and certain dimensions required more clearer definitions better evidence handling rules as well as like more explicit scoring guidance.
</details>

深入分析人工标注后，我们发现了几个反复出现的模式：
- **职位判断标准偏颇**：Judge 往往因为返回的职位看起来合理（Plausible）就予以认可，却忽略了 Agent 漏掉了预期信号或关键意图信号。也就是说，Judge 有时评估的是“合理性”而非陈述事实的“完整性”。
- **专业领域界定不清**：Domain（领域，如软件工程）、Function/Role（职能/角色，如机器学习工程师）与 Skill（技能，如机器学习）三者之间的界限不清晰；此外，对混杂有正确与错误信息的输出缺乏一致的“部分得分（Partial Credit）”规则。
- **格式与推理假设**：Judge 有时会因无害的格式差异而扣分，或者在根据会员现有任职信息推断时做出前后不一致的假设。
- **打分过苛分布**：在被认定为过于严苛的 37 起裁决中，有 31 起集中在被打了 1 分的输出上，表明各分数等级之间的边界需要重新校准。

另一个分歧点在于：当证据未明确阐述时，推断出的会员偏好是否应被视作有效。总体教训在于，评测分歧往往不仅是模型本身的能力限制，更反映了评分细则及底层评测策略的模糊性。

<details>
<summary>Original English</summary>
Um so when we look more closely at the human annotations several recurring patterns emerged. the first involved like using job titles. We found cases where the judge would accept like a return title because it was plausible would but would miss the fact that the agent had omitted an expected um signal or like an ignored and basically an ignored and important intent signal. Um in other words, sometimes the judge was sometimes evaluating the plausibility rather than the completeness of the facts which were stated. Uh the second issue was primarily around primarily around the fields of expertise. Here the distinction between like a domain, function and a skill wasn't like always clear where um a domain could be like um say software engineering and a function or a role could be like for example a machine learning engineer while skill being uh machine learning. Um the rubric also like lack consistent partial credit rules for output containing like a mixture of like correct and incorrect information. And another issue was involving around formatting and inference. So in some cases the judge penalized harmless formatting differences. In other words, uh it made it inconsistent assumptions about what could be inferred from like a member's existing employment information too. We also examined like the distribution of overly harsh judgments. Out of like the 37 um judgments identified as too harsh, 31 of them involved outputs that had been assigned a score of one, which suggested that the boundaries between our scores needed to be like recalibrated.
</details>

### 评测 Rubric 优化与对齐效果

另一个经常导致分歧的问题是：当证据没有明确写出时，推断出的会员偏好是否应该算作有效？更广泛的启示在于，许多评测分歧并不单纯是模型问题，而是反映了评分准则以及底层评测策略中的模糊性。

基于这些发现，我们对评测细则进行了多项针对性改进：
- **修复无害格式差异**：此前像 `full-time` 这样的值可能仅仅因为大小写或格式问题就被打低分，我们更新了准则，不再将此类差异当作语义失败。
- **引入标准化指引**：针对职位等引入了规范化指引。
- **澄清推断规则**：明确了 Judge 应如何处理兼职/多重任职（如推断资历级别）以及推断用户的地理位置偏好。
- **重新校准得分界限**：调整了区分低分与部分正确输出的打分规则。

这些改进带来了可衡量的提升：**人工对齐率从 57% 提升至 64%**，同时**平均误差（Mean Error）从 96 下降到 74**。我们特别关注的是，这些改进并不仅是通过微调模型实现的，更是通过完善“正确评测应当是什么样”的规范定义（即 Rubric 设计和评测器输出证据的标准）达成的。

<details>
<summary>Original English</summary>
Um, another recurring source of disagreement was whether an inferred member's preference should be considered valid when the evidence wasn't like explicitly stated. And the broader lesson here was that many evaluation disagreements were not simply like model periods. They were reflecting ambiguities in the rubric as well as like the underlying evaluation policy. Um, based on these findings, we introduced several targeted improvements to our evaluation rubrics. One was like basically fixing harmless formatting differences. Um, previously like a value such as like you know full-time could receive an incorrect score because of like capitalization or incorrect formatting. We updated the rubrics so that these differences would not be treated as like semantic failures. Similarly, we introduced normalization guidance for like titles. Um we also clarified how the judge should handle concurrent employment like you know sort of impairing seniority as well as like impairing geographic references of the user and more broadly we recalibrated the rules uh separating low scores from like partially correct outputs and these changes resulted like resulted in like measurable improvements uh where human alignment increased from like 57% to like 64% and um at the same time the mean error decreased from like 96 to 74 What we're trying to achieve here is to get our system as high or like as highly aligning to humans as much as possible. And what we find particularly interesting here is that we didn't achieve these improvements by only like handling the model, but we also improved specifications of what like the correct evaluation should look like. That is like rubric design as well as like um evidences which our evaluator is like spitting out. Um
</details>

### L2 反思归因的挑战与陷阱

随后，我们对反思 Agent 进行了类似的人工审核分析。L2 接收评测失败信息，并尝试定位根因（例如是由 Agent 本身引起、由 Rubric 引起，还是可用上下文存在其他问题）。我们发现：**归因根因远比单纯识别失败困难得多**。
- 当 L2 将问题归因于底层模型时，人工审核者往往赞同；
- 但对其他原因（尤其是与 Rubric 相关的归因），对齐率要低得多。

一个关键缺陷在于，原有的反思分类体系中没有明确机制表明“L1 Judge 本身可能判错了”。结果就是，即使真实问题出在 L1 Judge 误判上，反思 Agent 有时也会退而求其次去指责 Rubric。另一个问题是反思 Agent 有时会直接采用 L1 Judge 的说辞，而没有独立对照 Agent 的输出去审视和验证。这暴露出一个重大风险：**反思系统可能会给出看似极有说服力的解释，但实际上误判了底层症结**；如果依据这些错误解释去生成 Prompt 修改，最终可能会改错系统组件。因此，改进 L2 反思成为了下一步的重点。

<details>
<summary>Original English</summary>
moving forward uh we perform like a similar human review analysis for our reflection agent which was described earlier in our pipeline. We should recall that our L2 takes an evaluation failure and then it tries to identify the root cause. For example, it basically identifies was the problem caused by the agent itself by the evaluation rubric or by some other issue with the available context. What we discovered was that root cause attribution was substantially harder than like simply identifying a failure. Human reviewers agreed more often when L2 attributed a problem to like the underlying model, but agreement was much lower for other causes, particularly like rubric related issues. Um, one important issue was that our original reflection taxonomy didn't include a way to explicitly say that or Elvin judge could have been wrong. Um, as a result, sometimes the reflection agent fell back to blaming the rubric even when the real problem was like an incorrect um, L1 judgment. Um, and like another issue was like the uh, reflection agent sometimes used the L1 judge's rationale without like independently validating or independently thinking over it against the agents output. And um we exposed an important risk here which was like a reflection system can produce convincing explanations while still like identifying misidentifying like the underlying problem and if we use those explanations to generate prompt changes we could like end up modifying like the wrong component of the system. So improving the L2 uh like reflection chart like became our next priority.
</details>

这些发现促使我们在两个评测层面上同时进行优化：
- **L1 层面**：目标是让打分更准确、与人类判断更加对齐。
- **L2 层面**：目标是提高根因诊断的可靠性。

要将评测与反思工作转化为可衡量的业务影响，需要从两个层面来看：
1. **提升 RSI 流程本身的可靠性**：通过改进 L1 让评测得分更加稳定且更符合人类预期；通过改进 L2 提高根因诊断准确率。我们还引入了多数投票（Majority Voting）和留出集评测来缓解单个 LLM 判断带来的方差。此外，采纳阈值和汇报置信区间的规范化也是重要进展。
2. **扩大 RSI 采纳范围**：包括能够通过 RSI 可靠生成和验证的 Agent Prompt 变更比例、下游响应质量的提升，以及维护这些系统的工程师的生产力收益。终极目标不是去追求自动化生成 Prompt 修改的数量，而是在确保改动真正有益的前提下，让 Agent 质量产生可衡量的提升。

<details>
<summary>Original English</summary>
Um so to talk about some of the quality improvements um these findings led us to like focus on improving both layers of evaluation. At L1 the goal was to make sure that the scoring was more accurate and more better aligned with human judgment. And at L2 the goal was to improve the reliability of the root cause diagnosis. And um the next this slide basically summarizes some of like the changes we made to the system and the impact that we observed. We introduced like several targeted changes to address the um the reflection failures um identified through like human review and um we we were basically like trying to measure the impact here in terms of like how do we translate all this evaluation and reflection work into like measurable impact. So there are two levels to consider here. The first is like improving the reliability of the RSI process itself. So by improving L1 we make the um evaluation scores more stable and like more better aligned with human expectations and by improving L2 we increase like the uh like the root cause diagnosis as we mentioned earlier. So we also use like majority voting sort of and like held out evaluations to like help mitigate um variance from like individual uh LLM judgments and together these improvements support like a more reliable optimization process. Um importantly like one of the observed improvement here was about the required adoption threshold and the reported confidence interval as well. Uh the second level of impact is where we want to measure the RSI where the RSI adoption grows. This includes the percentage of like agent prompt changes that can reliably be generated and validated through recursive self-improvements in like downstream response quality and also productivity gains for engineering for engineers like maintaining these systems. Um those broader metrics are a part of how we want to like basically think about evaluation evaluating these systems at scale because the ultimate goal isn't to like maximize the number of like automated prompt edits. It's to like produce measurable improvements in like agent quality while maintaining some sort of a confidence that those changes are like genuinely beneficial. And this brings up brings us to like the final part of our talk which is how do we scale these um capabilities um which is like through an acceleration plan.
</details>

### 规模化推进与平台化愿景

这就引出了本次分享的最后部分：如何通过加速计划在更大范围内扩展这些能力。此前我们主要聚焦于用户理解 Agent 这一特定落地场景，但更广阔的机会在于：如果能将**评测、反思与优化**标准化，就能把这个闭环复用到众多其他 Agent 团队中。

从端到端评测能力的演进层次来看：
- **基座 Agent（Base Agent）**：最底层。绝大多数团队已具备可执行有用任务的 Agent（问答、摘要、对话、工作流执行等）。
- **Agent 评测（Agent Evaluation）**：在此层面上团队间开始出现差距。部分团队有定制的评测流，有些依赖单次分析或人工检查，极少数具备标准化且可持续复用的可靠评测。
- **Agent 反思（Agentic Reflection）**：进行系统化的根因诊断。
- **RSI 闭环（RSI Loop）**：位于最顶层，将评测、反思与优化、验证连接起来。

各层级自下而上依赖，缺乏可靠的诊断就无法构建值得信赖的闭环。因此，升级评测基础设施是规模化推行 RSI 的前提。与其让各个团队各自独立重复造轮子，不如提供共享的基础设施。

<details>
<summary>Original English</summary>
So so far we focused on like one implementation of RSI for user understanding but like the broader opportunity is like much larger. If we are able to like um kind of like standardize evaluation, reflection and optimization, we could potentially uh reuse this loop for like or the cycle for like many other agent teams. And um moving forward like um to understand the end toend evals the current state is like this diagram basically shows progression of capabilities that we believe are like necessary to support RSI at scale. At the foundation, we obviously have like the base agent where most teams already have agents that perform like useful tasks whether that's like question answering, summarizing, chat agents um or like just completing workflows as such. The next layer is agent evaluation and this is where we begin to like see gaps because some teams have built their own bespoke evaluation workflows. Other rely on like one-off analysis or like manually inspecting outputs. But only a few of them have like relatively standardized reliable evaluation processes that can be continuously reused. And above um evaluation we have agentic reflection which means being able to systematically investigate or do some sort of like root cause diagnosis. Um and finally at the top we have the RSI loop itself which connects evaluation and reflection to like optimization and validation. The the important observation here is that these layers like they depend on one another and you can't build like a trustworthy loop without like reliable diagnosis. That's why we see like leveling up evaluation infrastructure as a prerequisite to like scaling RSI and rather than asking every team to like independently build all these components, there's an opportunity over here to like provide some sort of like a shared um infrastructure.
</details>

要在企业范围内将 RSI 变成可复用的能力，我们总结了五个核心领域：
1. **标准化评测基础设施**：建设可复用的评测框架、指标和可用人类反馈校准的 Judge。
2. **自动化反馈闭环**：持续收集执行轨迹、检测重复性失败并执行根因分析。
3. **规模化自动化优化**：涵盖 Prompt 优化和 Agent 反思，以可重复的方式生成和测试候选更新，代替临时性修补。
4. **验证与信任机制**：任何自动化改动都需提供有效证据，包含稳健的留出集评测和回归测试。
5. **在各团队间推广普惠 RSI**：开发可复用组件和自服务基础设施，让各团队无需从零自建完整 RSI 管线即可接入。这是我们工程构建 AI 系统方式的一次重要转变。

<details>
<summary>Original English</summary>
So uh what would it like basically take to make RSI like a reusable capability across an enterprise is like uh we've identified like five strong areas. First is like standardizing evaluation infrastructure. So we need reusable evaluation frameworks, metrics, judges which can be calibrated with human feedback and um the second is like automating feedback loops. So we want systems that can continuously collect execution traces, detect recurring failures and perform some sort of loop case analysis. Um the third one is we need to scale um automated optimization that includes prompt optimization, agent reflection. So instead of making like ad hoc changes, we want improvement processes where candidates where candidate updates can be like generated and tested in more like a repeatable way. Um the fourth area is like validation and trust. So any automated improvement needs evidence that it actually you know works which means like having robust hold out evaluations and some sort of regression testing. And finally, we want to like obviously democratize RSI across teams where the goal is to develop reusable components and self-service infra so that teams can adopt these capabilities without having to build an entire RSI pipeline themselves which is what our broader vision is. And I think that this is an important shift in how we approach the engineering of like AI systems.
</details>

### 总结与致谢

总结来说，在递归自我改进中，我们主要有两个关键组件：**改进引擎（Improvement Engine）** 与 **目标 Agent（Target Agent）**。
- **目标 Agent** 是我们试图提升的 AI 系统；
- **改进引擎** 则负责通过评估表现、识别失败根因并提出改进来驱动变化。

但 RSI 系统的目标不仅仅是提升 Agent 在某一时刻的绝对表现，更是为了**加快 Agent 改进的速率**。如果把 Agent 的表现看作时间的函数，我们关注的是增大它的一阶导数，让性能提升曲线变得更陡峭。在我们的案例中，目标 Agent 就是用户理解 Agent，而改进引擎则是融合了评测、反思与 Prompt 优化的 RSI 管线。

在结束前，我们要感谢所有支持这项工作的核心团队、评测团队、工程合作伙伴以及领导层。从评测质量到反思再到生产落地，离不开跨领域的通力合作。最后想说的是，整个改进过程中最重要的一环，始终是**能够确信我们所做的系统优化变更切实有效且值得信赖**。这就是我们在 LinkedIn 探索递归自我改进的方向。非常感谢大家的聆听！

<details>
<summary>Original English</summary>
Um so in recursive self-improvement we basically just to summarize we have like two key components which is the improvement engine and the target agent. The target agent in the AI system is something we're trying to make better while the improvement engine is you know responsible for driving that change by evaluating performance identifying failures root causes and proposing improvements. But the objective of the RSI system isn't simply to improve the agents performance at like a given point in time. It's to like accelerate how quickly the agent gets better. And if we think of like the agent performance as a function of time, we are interested in increasing its first like its first derivative. If we think about it essentially like making the performance um improvement curve steeper and in our case like the target agent is our user understanding agent while the improvement engine is like the RSI pipeline which brings together evaluation, reflection and firmed optimization. Um before I close, we want to like acknowledge the people who helped make this work possible. This has been like an collaborative effort across the core team, our evaluation team and our engineering partners and leadership. Uh we we particularly like to thank all the team members and collaborators listed here for their contributions. Um a lot of the work we have described for evaluation quality to reflection and production required collaborations across these different areas of expertise and we're grateful for the support and um feedback we have received. Um yep so thank you and uh I guess we just want to conclude by saying that um most important part of like improvement processes is like being able to you know trust the changes we are making to make the system better. So that's some of the directions we're exploring with um recursive self-improvement here. So yeah, thank you so much for listening.
</details>