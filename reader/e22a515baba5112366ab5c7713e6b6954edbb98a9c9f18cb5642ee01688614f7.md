---
author: AI Engineer
date: '2026-10-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=gDRCpTMCqEU
speaker: AI Engineer
tags:
  - technical-due-diligence
  - straight-through-processing
  - ai-evaluation
  - unit-economics
title: 技术尽职调查真相：当商业计划书声称“70%自动化”时，我们该查验什么？
summary: 在AI技术尽职调查中，亮眼的效率数据往往掩盖了实际的人力成本与质量缺陷。演讲者结合买方与模型评测经验，提出针对“AI自动化”宣称的三大核心检验关卡：算术核验、概念定义穿透与评测成熟度审查，并给出基于真实端到端单位经济模型的评估框架。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Uber
  - Builder.ai
products_models: []
media_books: []
status: evergreen
---
### 算术核验：警惕吞吐量增长背后的全口径人力激增

在技术尽职调查中，投资人经常面对诸如“开发速度提升55.8%”或“70%自动化”等极具诱惑力的数据。然而，危险的数字往往并非凭空伪造，而是从真实测量中推导出的**失真结论**。以一项涵盖10,000多名开发者、1,255个团队的遥测观察数据为例：高AI采用率的团队合并的拉取请求（Pull Request）数量增加了98%，但拉取请求的代码审查时间却激增了91%，且平均每个拉取请求的体积膨胀了154%。这揭示了一个关键机制：**生成速度加快导致更多工作量涌入系统，下游的人工审查负担随之同步暴涨**。因此，第一道检验是纯粹的算术核验——要求公司提供过去18个月的完整时间序列数据，将工作负载总量（Workload Volume）与**全口径人力成本**（Fully Loaded Human Labor Count，包括操作员、代码审查员、模型训练师、异常升级处理人员及返工人员）放在一起对比。如果人工规模随着负载线性增长，这仅仅是AI辅助工具（Assistance），绝非劳动力替代（Labor Removal）。

<details>
<summary>Original English Source</summary>

my name is skcanina，and i'm i'm AA tack lead。and today，i'm here to talk about what technical dudiligence finds。when the this says，seventy percent automated someone has probably shown you number number like this fifty five point eight percent faster。and you've been wondering whether to believe it or not。well，this one comes from a control experiment and ninety five professional developers today。the task was one javscript ACTP server built from a ten played against twelve visible tests today。i'll give you three checks for what technical do dlusions finds in the AI error。i've actually spend more than eight years on both sides of the question。on the front side，i build AI system that investment professional used on a build side。i now lead ad a eevaluation produproduction and help create the numbers that reach executives。the dangerous number is not always fabricated。it's often a gengenumeasasument。it carried into conclusion。it cannot support tchunchonong describe the buyer side in a nice way，build for the memmo，not for the demo。i want to extend that standard to operational metrics in the first check requires no knowledge of models。it's pure air medics in far as observational data，high AI adoption teams merge in ninety eight percent，more poll requests poll requests review time increasase by ninety one percent，and the average pool request began one hundred fifty four percent larger。and a simple covered more than inten thousand developers across one thousand two hundred fifty five teams。this is not prove that a increased headcount。it's an observational teometry，not a controlled labor study，but it still give us a warning more work into the system，and the downstream review burden grew with it as well。so inteiligence ask for the companies 's eighteen months theory，put work cloud volume next to the fuoobebeaded human labor count，everyone whose work exists because of vi，for example，perators revieviewers trainerers escalation，and we work if human labor trucks burkloadad volume，dick has described assistance，not labor removal，

</details>

### 定义穿透：解构“AI归因”与端到端直通式处理的边界

即便在算术层面上说得通，指标的**定义阶梯**（Automation Ladder）依然存在巨大的模糊空间。例如，企业对外宣称“70%的代码提交归因于AI（AI-attributed）”，但这并不能等同于自主运行率。所谓自动化，处于不同层级的阶梯上：由AI起草草稿、由人类进行编辑、由人类进行审批，或是完全无需人类介入。金融领域对此有一个非常精准的概念——**直通式处理**（Straight-Through Processing: 在特定边界内实现无需任何人工干预的端到端全流程处理）。在技术尽职调查中，必须界定该自动化宣称的边界终点究竟在哪里：是代码草稿生成完毕？是拉取请求被合并？还是变更成功部署至生产环境？“AI归因”与“自主完成”属于完全不同维度的两类主张，必须穿透模糊修辞，要求对方披露具体的统计周期、总样本基数以及在既定业务流中的端到端直通率。

<details>
<summary>Original English Source</summary>

but when the authmetics survives，the definition call still can fail。uber example says that seventy percent of its full request are AI attributed。this is impressive。it still does not tell us the full autonomous rate。the period in total account were not disclosed either。so auautomation lalaim sits somewhere in this ladtter。it's either AI drafted it or edited by humans or approved by humans or no human intervention。finance already has a useful term for the last one。it's calstraight through processing，define it as a complete and to end without human intervention inside the boundary you name。so there's the boundary here ends when the code was drafted or when the poll requests approved or when the change reaches es production。so remember air attributed in autonomous or two different claims。

</details>

### 评测成熟度与质量对齐：揭示自动化评委与领域专家的认知鸿沟

当指标定义明确后，接下来的核心挑战是测量本身的置信度。在实际基准测试中，自动化评分器与最终合并决策之间存在高达24个百分点的差距。在一项针对4位开源代码仓库维护者、跨越多个独立Issue审查296个AI生成拉取请求的双盲实验中，自动化评估工具的表现远比实际对系统稳定性负责的专家更为乐观。在真实的工业项目中，常常出现自动化校验全部通关、但领域专家现场验收时几乎无一幸免的现象。因此，**评测成熟度**（Evaluation Maturity）是判断一家AI企业技术可信度的首要信号。尽职调查必须追问：是谁在定义真值标注（Ground Truth）？领域专家是否认可该标准？自动化裁判模型是针对何种基准校准的？以及，潜在的恶性输出（Bad Output）是否会逃逸并穿透防御进入生产环境？

<details>
<summary>Original English Source</summary>

okay。now now suppose the definition is precise。can we trust the measurement metre found twenty four percent point gap between automated greater and merged decision after adjustment to the human baseline，four maintaers from from reposittories review，two hundred ninety six AI generated pool requests across different unique issues。they did not know whether the batch came from AR human。the automated greater was substantially more optimistic than the people responsible for accepting the work。not a surprise。i have seen the same thing from the other side one，if the project i worked on ten out of ten output，would bath the automated validation。once you bring，get the experts on the table，barely few survive。this is why evaluation maturity is the first credibility signal。i would look for so always asked who labels ground truth and whether the expert agrees in whether anyone measures that agreement ask what the automated judge was validated against and ask could bad output escaped。

</details>

### 决策转化与单位经济学：从技术预警到投资一票否决权

预警信号如果不能转化为投资与管理流程中的**实质准入关卡**（Decision Gate），就会导致严重的商业灾难。以曾轰动一时的初创公司**Builder.ai**为例，早在2019年《华尔街日报》就公开质疑其宣称的AI能力真实性；到了2025年5月，《金融时报》报道其2024财年营收预估从2.2亿美元断崖式下调至约5,500万美元，并于6月申请破产清算。这证明预警信号一直存在，但未能被转化为尽调决策。因此，技术主张最终必须收敛为严谨的**端到端单位经济学模型**：首先从符合条件的目标工作总量出发，乘以实际采用率、直通处理成功率与最终验收合格率；接着必须扣除AI模型推演成本、人工介入审查成本、异常升级开销以及返工成本。我们真正需要的唯一指标是**单个已验收自主任务成本**（Cost per Accepted Autonomous Task）。技术尽调的终极职责不是判断数字是否华丽，而是验证必须满足哪些严苛前提，这个数字才真正具有商业意义。

<details>
<summary>Original English Source</summary>

so when arthmetic ics definition in evaluation all fell，a warn is still has to become a decision，right？this is not a claim that weak ai position in caused buildder of AI collapse。its insolvency involve revenue financing issues beyond AI claims。the diligent lessson started way back into a dozen nineteen when the wall street journal publicly questioned the claim of the AI capability in may twenty twenty five。the financial time also reported that it's to twenty twenty twenty four revenue estimated had been revised from two hundred twenty million dollars to roughly fifty five million dollars on june seconagain，the company，five chapter seven。so the warning existed，but the process did not turn it into a gate。so even when it claims survives，those cheque still has has survive the economics。so start with eligible workload value apply actual adoption。three，through process success in accepted quality，then subct the cost of AI human review escalation，and we work the metrc gui would want is cost per accepted a tonomomous task。if the task failes escalates or need，we work，this belongs to the costs to always put those check together。and this is the god，i would probably take with me to the next meeting to some up three main checks，the authmeticics compare work，clothed volume with fully loaded human e labor，two definition identify the run and request the straight through rate inside a neighbor flow。three，the tell ask who defines quality，whether expert agrees in what bad output escapes，then translate only the surviving claims into a unit economics，and of course，believe it tested or walk away the printple card in all the source notes are in the website，and this cure code will lead you to it。so tata card scanned，print ted and take it to your next venter，meded or investment discussion。and always remember，the job of diligence is not to ask whether the number is impressive。it's to ask what must be true for the number to matter。thank you。

</details>