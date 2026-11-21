---
author: AI Engineer
date: '2026-10-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3ZlQk4-knWM
speaker: AI Engineer
tags:
  - ai-governance
  - production-deployment
  - risk-management
  - system-architecture
title: 银行部署 AI 的本质困境：为什么这不是一个工程问题
summary: 在高度监管的银行业部署 AI，最大的障碍往往不是模型性能或代码实现，而是隐藏在组织架构中的数据归属、环境托管与风控审批链条。本文结合 Bloomberg 与 Google 的实战经验，提出了以“组织调研即工程”、“收敛系统权限梯级”以及“全链路证据包”为核心的方法论，阐述如何在立项首周穿透治理黑盒，让 AI 真正落地生产环境。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Bloomberg
  - Google
products_models: []
media_books: []
status: evergreen
---
### 伪工程瓶颈：演示成功与生产遇阻的脱节

许多企业在将人工智能引入银行业务场景时，往往会陷入一种典型的假象：团队构建了精巧的原型，模型表现优异，**概念验证**（Proof of Concept: 验证技术可行性的早期原型）在演示环节获得了所有人的认可。例如在一个让系统审阅客户文档并为分析师标记异常项的案例中，演示顺畅展示了预期工作流，业务价值清晰可见。然而，一旦进入上线阶段，系统往往戛然而止。技术团队面对的不是算法优化或代码重构，而是一连串来自组织内部的根本性拷问：安全团队询问该服务将托管在哪个物理或隔离环境中；**数据所有者**（Data Owner: 对应数据资产的合规与使用授权负责人）追问谁签署了利用此类客户文档进行模型处理的协议；合规与风控部门则质疑如果模型遗漏或误报异常项，在流转到下游系统前由谁来兜底复核。

这些质询并不是细枝末节的审批流程，每一个问题的答案都会彻底改变技术团队被允许构建的架构边界。最常见的工程失误，恰恰是在相关负责方甚至从未见过方案设计的情况下，工程团队就单方面投入了大量系统架构设计。当演示顺利、模型达标但项目依然无法交付时，核心原因在于：在银行部署 AI 本质上不是一个纯粹的算法或工程实现问题，而是一个组织决策与控制依赖问题。研发周期的首要任务不是急于编写代码，而是在第一周内彻底排查出这些隐藏的决策链条，为系统规划出一条切实可行的生产投产路径。

<details>
<summary>Original English Source</summary>

hello, i'm welcome today. we will be talking about deploying AI ahead of a bank and how it is not an engineering problem. before we get into that, i want to introduce myself, my name is Paden Gayle. i worked across many different fields. so i started off at consulting at Accenture, moving over to Bloomberg, getting into a software engineering team before i worked into the infrastructure team and the data platform team. then afterwards, i was at Google working on security and deployment. and right now, i am a founding Forward Deployed Engineer. i started up and writing the book on Forward Deployed Engineering with O'Reilly.

in this example, the system reviews client documents and flags exceptions for analysts. the demo shows the intended workflow, and everyone can see why it would be useful. then security asked, okay, which environment will host it? the data owners asked who agreed to this use of documents. and someone from risk asked, who will review a wrong exception before it reaches the next system. those are reasonable questions, right? each question can change what we are allowed to build. the team has already invested in a design, while several people responsible for that design had never seen it. so in this case, the demo works, the model was fine. however, it still did not ship. i want to now show you how to uncover those decisions in week one, so you can design a system with a credible road into production.

</details>

### 组织调研即工程：将隐性治理依赖显性化

在理清上述决策阻碍后，工程思维必须发生根本性转向：在高度合规的体系中，**前期调研即是核心工程**（Discovery is the Engineering）。系统的每一个技术组件和接口，本质上都挂载着对应的组织决策依赖。若要构建一条可信的上线路径，团队必须在第一周为每一项关键决策锁定具名负责人，明确他们做出决议所需的证据支撑，以及后续的流程交接点。无论数据源多么容易通过代码读取，能够获取数据并不等同于获得了该业务用途的合法授权；在**数据平台基础设施**（Data Platform Infrastructure: 企业内部管理数据存取、血缘与合规的大规模底层系统）的建设中，首要前提始终是确认每份数据集的具体责任人及其明确的授权范围。

这种依赖关系映射直接决定了系统架构的成败。常规的技术架构草图往往极度简化：文档输入模型，模型推理输出，分析师接收结果。但真实的系统拓扑图必须叠加治理维度：文档存在归属人，模型服务需要平台所有者支持，分析师工作流需要业务主管确认合规边界，而尚未明确审批人的环节就是一个致命的系统依赖空缺。通过与项目发起人对照治理图谱，逐一落实“谁拥有该数据”、“是否知悉该 AI 用途”、“哪位合规专家负责具体设计审查”，才能将不确定的组织流程固化为可执行的工程任务。若在整个系统全量开发完成后才发现安全边界、数据链路或交互逻辑必须推倒重来，代价将极其沉重。通过前期调研将这些决策前置，正是利用设计阶段极高的变更灵活性来换取生产运行的确定性。

<details>
<summary>Original English Source</summary>

labels represent decisions your deployments depend on. for each one, i want a person who can explain the decision, the evidence they need, and the next step. so for every dataset, who owns the source, who can get access, can you reproduce this in the workflow? those responsibilities may belong to different people, but being able to query data does not settle every question about how the application may use it. for the model risk, find a person who can tell you which review applies to the intended use, ask what risk submission looks like, who will own the system after launch, and what evidence the owner will need to maintain it.

for third-party risk, draw the actual dependency chain including the model provider, the hosting arrangements, vendor review, and operating service. find out which relationships have already been reviewed and which proposed changes require a new decision. for audit, ask what someone would need to reconstruct a historical action: which input was used, which configuration produced the output, what did the reviewer see, and who approved the action? those are the questions that affect the records you need to capture from the beginning.

now imagine getting those answers after you built the whole entire system, but a deployment boundary, a data path, or action that may have to change. the useful move is to bring these people into the design early. their responsibilities help us identify the system we can actually operate. and here, discovery is the engineering. so now you want to talk about what discovery is and who we need to really find out to understand what exactly we need to build.

so you want to think every dataset has an owner. the work i did at Bloomberg on the data platform team made this concrete for me. building infrastructure for an LLM meant understanding which datasets could be used, and who could approve that use. carry that into each bank deployment, honestly any deployment. so before designing retrieval, find the person accountable for each source, confirm the allowed use and the environment where the processing can actually start to happen. if those answers change, your design changes with them.

imagine the key on the slide stands for a real permission with a real owner. we should be able to name that owner to know where exactly this key needs to come from when starting to scope out an architecture. all the questions you may have can be answered by looking at the org chart. read the top first: documents go into the model, and analysts use the output. you can probably sketch that system in a few minutes. now read the right one underneath it: the documents have a data owner, the model service needs a platform owner, the analyst workflow needs someone who can confirm their own risk requirements, and the last line has a question mark. that question mark is a dependency. we have designed a workflow without finding the person who can tell us whether the intended use is acceptable and what evidence will be required.

so how to walk through this diagram with a sponsor, or someone you trust, and figure out: okay, who owns the documents? have they heard about this use? who can help us reach the appropriate reviewer? then how to confirm the answers directly with those people? the real map will have more relationships than this. a technical component may depend on several approvals. some decisions span the entire system. the point is to make those dependencies visible while the design is still easy to change, and a named owner becomes a specific task with a person responsible for resolving it. that is how discovery turns uncertainty into an implementation plan.

</details>

### 穿透需求迷雾：影子观察、草拟闭环与范围渐进

在明确了组织各方的决策人后，工程落地面临的下一个挑战是：业务客户往往无法提供一份精准完备的**技术规格说明书**（Specification: 明确系统边界、输入输出与验收标准的工程文档）。针对这种需求模糊性，高效的工程方法依赖于三步迭代：“影子观察（Shadow）、草拟方案（Draft）与收敛范围（Shrink）”。在金融现金流对账或客户入职审批等复杂场景中，最扎实的技术起点永远是跟随真实的业务流，坐在分析师身旁进行实地观察：记录他们打开了哪些业务系统、在哪个环节做出主观判断、遇到文件缺失时如何向合规请求授权。这种基于第一视角的真实操作链条，构成了任何可靠系统规格的基石。

当掌握了真实的操作链路后，切忌盲目追求全面自动化，而应将其提炼为一个极简的草案并逐步确认决策边界。以异常审核系统为例，核心交互可精炼为三行：“1. 调阅文档；2. 草拟异常项；3. 分析师确认提交”。随后围绕每一个环节细化技术边界：
* 分析师有权访问哪些文档分类？该权限是否涵盖算法批处理？
* 模型究竟该输出文本高亮、预填表单还是二者兼具？
* 初稿由谁负责复核？最终向核心系统提交的责任人是谁？

将包含**成功衡量指标**（如审查耗时降低幅度与异常遗漏率对冲）的精简方案直接提交给业务发起人与内控部门。他们对文档范围的划除、对审核角色的修正，都会直接转变为明确的工程设计决策。通过小步快跑的方式拓展系统范围——从读取现有系统、接入多源数据、生成对内建议，直至最终的自动化处理——团队可以在最小可行范围内确认内控机制的匹配度，让每一个新增的工程特性都具备通畅的合规路径。

<details>
<summary>Original English Source</summary>

and given that, you may start to ask yourself: okay, what sort of questions should i be asking? so here are some of the questions i would bring to a discovery call: where does the data live and who can approve reading it? who has stopped a similar project before and why? which existing controls could cover this workflow and who owns them? where will this run in production, and who are the administrators for the environment? who signs off the relevant risk review, and what have they signed off before? what obligation is the sponsor personally worried about, and who can explain it?

notice what i want to leave with: it's how to name decisions for next conversations. if someone says "security will be fine", ask who will actually review the design and when you can meet them. then close the loop: send each owner a short description of the proposed use and confirm what they need from you. by Friday, the people whose decisions that deployment depends on should know the project exists. that gives scoping a much firmer starting point.

and once all that is done and we know who owns the decisions, i can scope the work even when the customer cannot write or give out the spec. i rely on these three things: shadow, draft, and shrink. for example, at Bloomberg, i worked on a system that handled cash flows that had to reconcile, and that gave me a concrete place to start: follow the flow and the people responsible for it. use that approach when a sponsor wants AI for onboarding: sit with an analyst, watch which systems they open, where they make a judgment, and when they ask for permission. ask what happens when the document is missing. write down the actual sequence; that is the beginning of every specification.

now imagine we are building the document exception system. this is a hypothetical example, but i would still put these three lines in front of the sponsor: 1. review documents; 2. draft the exceptions; 3. analyst submits. then i would make each line specific: which documents can analysts access? is that access appropriate for this processing? what should the model produce: a highlighted passage, a draft form, or both? and who checks the draft? also, who submits the final version? suppose the output is a highlighted exception and a draft form: the analyst checks the source, edits the form, and submits. that is a boundary someone can correct.

i would also propose success criteria: either less review time without an increase in missed exceptions. we still need to agree on how to measure that against a current benchmark, because that is the whole point. it is a proposal until we have an agreement. take the draft to the sponsor and the control owners. they can cross out a document type, they can change a reviewer, or they could reject the output. each correction gives a decision we can build around.

once the workflow is complete, scope becomes a series of approval questions. so now let's grow our hypothetical system one step at a time: first, it summarizes a document that the analyst already has (we will still confirm whether that existing access covers its use); next, it reads from a second system (now there's another data path, and somebody needs to approve it); next, it drafts a response that a customer will see (who checks the content and which review applies?); finally, it sends a response automatically (who owns that action? what happens if it sends something wrong, and how do we stop it and recover?). those are four different engineering scopes. the applicable reviews depend on the institution and the use case. so i'd confirm them with people who own those decisions.

then i ask which increment creates useful value today. could i draft inside the analyst's current workflow to solve enough of the problem? if so, start there. confirm that the existing control really fits and build the smallest useful version (MVP) with a credible path to approval.

</details>

### 自主权阶梯：以控制权边界约束错误代价

伴随着系统范围的递进，必须引入系统自主权的量化与分级机制。在核心金融系统中，每一个自动化步骤都必须对应明确的风控机制与责任人。许多团队在设计之初便试图让模型直接扮演“自主代理”，让算法自行判断合规性并触发不可逆的业务操作；这种设计直接将模型的输出置于毫无缓冲的运营风险敞口之下。为了解决这一矛盾，应当将系统权限划分为清晰的“自主权阶梯”，自底向上逐级演进：
* **建议（Suggest）**：系统仅生成参考建议，分析师完全自主决定是否采纳。
* **草拟（Draft）**：系统预先生成处理初稿（如提取高亮文本并预填表单），由分析师逐项核验并执行提交。这一阶段是实现人机协同的最安全切入点。
* **授权后执行（Acts with Approval）**：系统准备好执行动作，但必须由人工逐笔完成前置授权方可落地。
* **受限自主执行（Acts within Limits）**：系统在严格预设的风控参数与授权阈值内自主运转。

梯级每上升一层，系统一旦出错所产生的破坏性后果呈指数级放大，其所必需的内控审计严格度与合规审查人的要求也随之骤增。因此，最优工程策略始终是**从产生实际业务价值的最低自主阶梯切入**（优先采用“模型草拟，人工提交”的模式）。在这种边界划分下，分析师拥有完整的原始佐证与不确定性提示，从而做出实质性的专业判断，避免“审批按钮流于形式”。在生产环境中持续追踪人工修正率、高频错误类型以及系统回滚成本，积累真实运行数据，才是评估未来是否向系统让渡更高自主决策权的唯一依据。

<details>
<summary>Original English Source</summary>

that brings us to autonomy: start with the authority that the problem solves, then ask what task can be proven as evidence to give the system more. so when working on cash flows at Bloomberg, i thought of automation a lot of the time: every automation step needs a control, and somebody owns the number. i carry that discipline into AI: find the consequential action, name its owner, and decide what happens when the system is wrong.

for example, in a hypothetical exception workflow, the submission is that action. an analyst reviewing the draft needs the source evidence and visible uncertainty to make a real judgment. a review button only helps if the person can actually check the work. so when thinking about autonomy, i want you to read the ladder from bottom up:
- "Suggest" means the analyst sees the recommendation and chooses what to do with it.
- "Draft" means the system prepares something, the analyst checks and submits; that is a high-leverage step.
- "Acts with approval" means a person authorizes each action before it happens.
- "Acts" means the system operates within limits that have already been approved.

each step changes the consequences of an error. however, it also changes which controls must work and which reviewer needs to be convinced. i would start at the lowest step that creates value, then collect evidence from there: are the reviewers overriding the drafts? which errors keep recurring? can people recover when something breaks? we use those observations to make the next authority decision. a model does not become more capable by itself; answer how much authority this particular workflow should give it.

now let's make that concrete with the same hypothetical exception assistant. suppose the initial request is an agent that reads client documents, decides which ones fall outside of policy, and files exceptions automatically. in that design, the model's judgment can become an operational action without an analyst checking. now keep the model and change the action boundary: it highlights a likely exception, points to the open source, and prepares the draft form; the analyst checks the evidence, corrects the form, and chooses whether to submit.

take that design to the people we found during discovery: can this use the analyst's existing workflow? does the approved data access cover the processing? which controls apply and what evidence do the reviewers need? human review does not guarantee approval, and it does not determine a regulatory category on its own. we still need to confirm the intended use and the required reviews. the useful question is whether this drafting version solves enough of the problem to ship first. if it does, you can collect evidence about errors, overrides, and recovery while operating within that boundary. the next decision about authority can draw on what happens in real-world use. that makes evaluation part of the operating plan.

</details>

### 可穿透的证据包：面向风控的端到端可复现评估

当确立了受限的系统边界后，最后的交付支柱在于如何向风控、审计与合规团队证明系统的可控性。在顶级工程实践中，风控团队所关注的核心痛点非常务实：当系统在生产环境中发生故障甚至造成错误决议时，谁能第一时间感知？什么熔断机制能够立即阻断下游影响？谁来承担责任？恢复正常业务状态需要多长时间？因此，面向合规的评估方案绝不是简单的整体基准测试得分，而是一个必须包含**威胁模型**（Threat Model: 系统面临的潜在安全与合规风险分析框架）、故障场景响应与告警熔断链路的完整运行方案。

为确保审计追溯能力，系统在每次评估运行与生产交互时，必须完整留存由五大核心记录构成的**证据包**（Evidence Pack: 面向内部治理与合规审查提供的标准化决策与系统运行证据集）：
* **预期用途记录（Intended Use Record）**：明确界定系统的使用边界与绝对禁止的业务行为。
* **数据血缘记录（Data Lineage Record）**：详细登记每个示例的数据来源、合规属性及使用授权。
* **故障模式记录（Failure Modes Record）**：穷举模型幻觉、文本解析损坏或漏报时的检测路径、回滚降级策略（Fallback）及其责任人。
* **分群测试记录（Results by Segment Record）**：严禁使用整体平均准确率掩盖局部缺陷。必须将干净文档、模糊扫描件、生僻异常及全新文档类型进行分群评估，并优先暴露表现最薄弱的分群表现；对缺乏充分证据的样本群坚决限制使用。
* **控制运行记录（Controls Record）**：精准冻结输入提示词、模型版本、系统配置、生成结果以及人工复核操作，确保任何一次历史决策在日后接受合规核查时均可实现无损复现。

在项目推进至首周末时，可以通过“五问启发式评估”检验交付可靠性：数据所有者是否已被知会并参与？生产环境及其管理员是否具名落实？业务发起人能否在完全不使用“AI”这一术语的前提下清晰描述业务流？最小可行范围是否完全适配现有的审批内控？是否明确了风险审查人及其既往决策惯例？获得 4 到 5 项肯定答复，标志着系统具备了高确定性的投产路径；低于该标准则意味着必须在投入实质性编码前，通过重新收敛甚至定义系统范围来解决未决决策。

<details>
<summary>Original English Source</summary>

and that brings us to our fourth pillar: evaluation. the risk team can use evidence, which really just means the controls they are responsible for managing. at Google, the question that needed answered was: what happens when a system breaks? who notices? what stops? who takes responsibility? how long will it take to bring it back up? for an end deployment, i want the concrete plan: the intended use, a threat model, the failure modes, and a response. show me the controls working when the model gets it wrong; name the person who receives the alert and can stop the workflow. that gives a practical way to evaluate.

going back to the hypothetical exception assistant: if it invents an exception, the analyst checks the source passage and rejects the draft; if extraction produces unreadable text, stop and reclassify the file; if it misses exceptions, targeted offline cases help expose that weakness (they do not detect every live miss, so keep high-impact work under manual review). for each failure, name the detection path, the fallback, and its owner. put those decisions in an evidence pack.

these five files make the review complete:
1. "Intended Use" records users, boundaries, and prohibited actions.
2. "Data Lineage" records each example's source and usage approval.
3. "Failure Modes" records detection and fallback results.
4. "Results by Segment" records coverage and errors.
5. "Controls" records review thresholds, stopping rules, and owners.

to generate the evidence with each evaluation run, preserve the input prompt, model version, configuration, output, and reviewer action. that lets us reconstruct the historical decision. calling the model again later may produce a different answer, so we preserve what actually happened. a reviewer can then inspect that supporting record.

now we can look at what is used to organize that result in the fourth file: for a hypothetical workflow, i would separate clean documents, scans, rare exceptions, and new document types. measure their errors and control behaviors in each group, then lead with the weakest result; an average can hide a serious gap in one segment. if a group has too little evidence, say so and restrict that use until you have enough. this tells reviewers what the results support, and it brings us back to our week one decisions.

rounding everything up by Friday, i like five answers:
1. Is the data owner engaged and aware of this project?
2. Are the production environment and its administrators named?
3. Can the sponsor describe the workflow without saying "AI"?
4. Can the smallest useful scope fit existing controls confirmed with their owners?
5. Do we know the risk signer, and what happened to the person who signed last time?

use those answers as a heuristic: 4 or 5 "yes" answers suggest a credible path to ship; 3 means unresolved decisions need owners and target dates; 0 to 2 means resolve the decisions before committing to delivery, including possibly shrinking or redefining scope. this score does not predict approval, but it does tell you what to do next week.

what i want people to walk away with is that discovery is the engineering: draft the spec, then shrink it; give the system only the authority it needs; build the evidence pack. and remember: the demo worked, the model was fine, but it still did not ship. so what do you do? you go find the people.

</details>