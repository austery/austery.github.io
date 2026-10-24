---
author: AI Engineer
date: '2026-10-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Bz1HFxQA1o8
speaker: AI Engineer
tags:
  - ai-observability
  - compliance-engineering
  - vulnerability-remediation
  - disaster-recovery
  - data-privacy
title: 破局银行AI合规困境：从12个月等待缩短至数周的工程实践
summary: 在高度监管的银行业部署生产级AI，往往面临极其冗长的合规周期。演讲者分享了如何通过三大核心支柱破局：利用自动化沙箱任务验证CVE真实可利用性、基于ClickHouse与Altinity构建跨区域灾备与数据正确性校验、以及设计双重LLM-as-a-Judge流水线防止PII与MNPI反向泄漏。通过“展示完整证明过程”而非盲目打勾，成功将银行AI上线周期从一年压缩至数周。
insight: ''
draft: true
series: ''
category: deployment
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cisco
  - ClickHouse
  - Altinity
products_models: []
media_books: []
status: evergreen
---
### 像严苛的数学老师一样：银行AI合规的“解题证明”逻辑

在高一时，我遇到过一位以严苛闻名的数学老师**赫夫先生**（Mr. Huff）。在数学测验中，他要求我们将所有计算结果精确记录到小数点后第四位，以彻底排除任何靠运气蒙对答案的可能。更关键的是，整道题目的绝大部分分值其实来自证明过程——你必须完整展示自己是如何推导出最终答案的。当我开始涉足**AI可观测性**（AI Observability: 对AI应用运行状态、调用链路与输出质量的系统性监控分析）软件领域时，我发现日常打交道的银行合规与风控团队几乎就是赫夫先生的翻版，只不过他们手握数百万美元的合规预算。

必须明确的是，在银行内部部署**智能体AI**（Agentic AI: 具备自主规划、工具调用与多步决策能力的AI系统）通常需要耗费极其漫长的时间。这里的核心痛点在于**生产环境**（Production）。我们讨论的绝非开发（Dev）环境、预发（Staging）环境中的原型试验，甚至不是旨在提升内部员工效率的内部RAG（检索增强生成）工具，而是数以百万计的银行真实客户每天都在使用的系统——也就是你每次登录网上银行或手机应用时所交互的核心业务。我和我的团队长期处在向全球顶尖银行交付软件与工程流程的第一线。今天我想分享客户向我们提出的关键问题，以及我们如何运用系统化工程策略，将AI进入生产环境的时间从一年大幅压缩到短短数周。

首先来看标准的SaaS形态AI在银行是如何落地的——剧透一下：根本行不通。公有云SaaS天然存在向互联网的**出站流量**（Outbound Egress），极易导致敏感信息外泄。而在银行完全物理隔离的**气隙网络**（Air-gapped Network: 与外部公共互联网实现物理隔离的专有网络）环境中私有化部署AI，整体数据流向与架构要复杂得多。围绕这一场景，今天我将重点阐述三大核心支柱：
1. **构建流水线**：银行如何安全地从我们的软件仓库拉取镜像到其专属集群；
2. **数据韧性方案**：当某个云区域在请求处理途中突发故障时的灾备机制；
3. **数据隐私防线**：如何确保零敏感信息泄漏给银行内部未授权员工或溢出银行专属VPC。

<details>
<summary>Original English Source</summary>

When I was in the 10th grade, I had a math teacher, Mr. Huff, who was notoriously brutal on our math tests. He would make us write our answers down to the fourth decimal place in case you happen to get to the answer by luck or by chance. And most of the credit for the question was actually from the proof that you wrote to show how you got to the answer.

And when I first started playing AI observability software, I realized that most of these compliance and risk teams that I work with every day, they're kind of like Mr. Huff, but with a multi-million dollar compliance budget.

And I would let you know that playing agents AI within banks takes a long, long time. And the reason is because that keyword production. I'm not talking about prototypes in dev or staging or even like internal rag agents to increase internal employee productivity. I'm talking about the applications that these banks' millions of customers use every single day. The same ones you use when you log into your bank's website or mobile app. And those are the use cases that matter.

In my team, we're on the front lines of deploying not only our software, but also engineering processes into the largest banks in the world. And I want to share some of the issues that our customers bring to us and the strategies we use to help reduce the time to production from a year down to a couple weeks.

So, let's first take a look to see how standard SaaS AI gets deployed at a bank. Spoiler alert, it doesn't work. There's outbound egress to the internet and sensitive information can potentially be leaked out. When you deploy on-prem AI at an air-gapped bank, the flow is a little more complicated.

I'm going to walk through three pillars today. Number one is the actual build pipeline: how our banks pull images from our software into their cluster. If a region fails mid-request, what is the data resiliency plan? And then finally, one of the most important parts is how do you ensure no sensitive information leaks out to internal bank employees and outside of the bank's VPC.
</details>

### 第一支柱：CVE脆弱性治理与沙箱利用验证机制

在金融工程实践中，合规推进速度与**CVE**（Common Vulnerabilities and Exposures: 通用漏洞披露体系）的处理效率紧密绑定。任何成熟的软件平台都必须建立严密的漏洞应对机制，因为这是进入银行的第一道合规门槛。然而现实远比查询**NVD**（国家漏洞数据库）、**CISA**或**MITRE**网站复杂得多。在实际架构中，平台包含大量不同组件的容器镜像，每个镜像都可能报告多个CVE。更棘手的是，我们需要同时向多家银行交付软件，而这些银行部署的镜像版本各不相同，各自引入了独特的漏洞清单。此外，各大银行采用的安全扫描工具（如**Sysdig**、**Wiz**、**Prisma**）各有差异，安全基线策略、漏洞严重性评级以及**SLA**（Service Level Agreement: 漏洞修复时限协议）也大相径庭。

另一个深层困境在于开源依赖。现代镜像高度依赖开源生态，深层的传递依赖（Transient Dependencies）往往隐藏着我们内部工程团队无法直接修复的代码缺陷。我们的团队必须持续研读海量开源项目的发布说明（Release Notes），向银行安全部门出具翔实报告，说明为何某些传递依赖漏洞短期内无法直接打补丁、以及为何必须等待上游维护者更新。针对工程团队确实能够修复的CVE，常规手段是直接升级软件包版本，或者基于更新的**Docker**基础镜像重新构建。但实际情况常常出现分歧：某家银行要求升级至特定的3.8版本，另一家银行却因更高版本引入了新的CVE而要求回退到旧版本，而在此期间业务系统必须保持稳定运行。

为了应对这种多版本混杂的治理复杂度，我们开发了自动化评估体系，统一执行繁重的研判、调研与报告输出，生成清晰的对照表，一方面告知内部工程师必须修复的漏洞，另一方面向银行安全团队提供无法自研修复的透明依据。但这里存在一个行业普遍盲区：**Sysdig**或**Prisma**等传统扫描工具仅检查软件包版本号是否上调，却根本无法证明该漏洞是否真实存在于应用代码的执行路径中。为此，我们引入了基于**Harbor**测试任务的验证框架——为自动化智能体构建隔离的**安全评估沙盒**（Sandbox Harness: 包含真实容器环境与执行逻辑的受限测试空间）。

我们在Harbor中下发指令并注入容器运行环境：以某软件包2.6.2版本声称修复了特定CVE为例，我们命令测试智能体参考历史漏洞利用逻辑编写Exploit Payload，测试新版本是否仍可被触发，并自动生成可执行的验证断言。借助Harbor结合**Daytona**或**Modal**的多容器沙盒，我们可以在后台大规模并行运行大量测试试验，量化评估利用风险。这一做法的本质跃迁在于：我们不再仅仅向合规人员宣称“版本号已升级”，而是通过端到端的沙盒实测证明漏洞在现有业务代码路径下已无法被利用，从而彻底打破因虚假漏洞报警导致的合规僵局。

<details>
<summary>Original English Source</summary>

Compliance velocity and CVEs go hand in hand. And no platform worth their salt does not have a plan for how they address this first compliance hurdle, which is common vulnerabilities and exposures. I'm going to walk you through why this process is complicated.

So, number one, you can take one CVE and you can research on the NVD, CISA, or MITRE websites. But, in reality, our platform, most platforms, you have multiple images and each image has multiple CVEs. And I'm not trying to remediate CVEs for one bank, but rather for multiple banks. So, we have to create a system and process around this. And the complication there is that our banks are on different versions of our images, each with their own unique CVEs.

On top of that, banks utilize different scanning tools, which output a report on what CVEs are present. Furthermore, they have specific policies around what are the actual CVEs in the images, what the severity level is, and then what the SLA is for time to remediation.

Our images rely on many open-source projects and those projects contain many transient dependencies which have CVEs that our engineering team cannot remediate. So, our team is constantly looking into the release notes for a lot of these open-source projects cuz we have to provide a detailed explanation back to the security teams at these banks on why we cannot remediate and why we're dependent on these open-source project maintainers.

So, once you've identified the CVEs that your engineering team can actually remediate there's multiple ways of remediation. You can bump the package version up to a higher version or rebuild your image against the base Docker image. But, then we also have this complication of certain banks saying we want to be on version 3.8 of the package. But, another bank might say hold wait, hold on. That version is too high. There's too many CVEs. I want to be on an older version of that package. So, given all of this your software still has to work and function.

And so, one solution that you can use is creating a scale. So, we have a scale that does a lot of the heavy lifting and reporting and the internal research as well. And the output is a nice kind of table format that tells our engineering team what CVEs we have to fix and also provides explanations back to our security teams from the bank on what we cannot fix due to these transient dependencies.

Most of these scanning tools—Sysdig, Wiz, Prisma—they just check to see if the package has been bumped to a specific version. But, it says absolutely nothing about whether or not that exploit is actually still in your application code. And so, how do you actually test for that?

So, one solution is creating a harbor task and this is kind of like creating a harness or a world for an agent to try things out. And so within this harbor task you have instructions for the agent, you have an environment which contains the actual docker images for your application, and then tests that you can run against the agent to see if they passed.

The instruction here is a CVE for this package. And the instruction I tell the agent is 2.6.2 of this package supposedly remediates the CVE. I want you to go and write an exploit based on the older version to see if this new version still has that exploit. Then write a test to see if that exploit actually passed or not.

And then with harbor you can run a bunch of docker containers or Modal or Daytona sandboxes, run these all in parallel, and you have a bunch of trials to see how the agent performed over various trials. And what I'm trying to say here is that it's not enough just to say we bumped the package version up to a specific number. We have to provide the evidence to show that the exploit is no longer actually in the application code.
</details>

### 第二支柱：跨区域ClickHouse灾难恢复与数据主权边界

构建流水线之后，第二大支柱是**灾难恢复**（Disaster Recovery: 发生区域性硬件故障、断网或基础设施瘫痪时的恢复能力）。对于银行系统而言，灾难恢复绝非可有可无的基础设施卫生习惯，而是一票否决的刚性合规指标。目前的行业技术栈在此存在明显断层：大部分主流AI可观测性工具底层普遍采用**ClickHouse**作为分布式列式数据库，但在跨区域故障转移（Cross-Region Failover）与数据复制方面，ClickHouse原生体系并没有开箱即用的官方全托管服务。相比**Redis**或**Postgres**成熟的跨区域容灾能力，ClickHouse官方文档中明确指出其跨区域托管故障转移功能尚属空白，这意味着金融机构必须自行设计并维护灾备架构。

业界通用的基础容灾范式通常包括：在主数据中心区域部署ClickHouse主集群，通过自动化定时任务将数据快照打包备份至对象存储存储桶（Bucket），再由备用任务从存储桶将数据恢复到**容灾区域**（DR Region），并在灾备集群内部配置多Pod副本来实现数据冗余。这套工作流大多高度依赖由**Altinity**维护的开源工具`clickhouse-backup`。虽然备份与还原日志能生成漂亮的运行状态表，但“任务状态显示成功”并不等同于“此时此刻业务数据完全正确”。

在分布式实际运行中，底层坏盘、坏节点、数据库迁移异常或副本同步延迟（Replication Lag），都会在日志毫无告警的情况下导致容灾端数据损坏或失效。因此，合格的金融级工程实践必须主动增加深度校验链：比对主备跨区表级**行数计数**（Row Counts），并严格校验容灾区域内各Pod副本间的数据一致性收敛情况。核心原则在于：合规追求的是数据真实正确性，绝不是在UI上简单给“备份任务已执行”打勾。

更值得系统架构师深思的是，设计多区域备份还原流程的同时，你其实已经被动触发了**数据驻留**（Data Residency: 规定特定国家或司法管辖区内生成的数据必须留在本地法规限制）决策。底层的S3存储桶本身对数据位于俄勒冈还是弗吉尼亚毫无感知，但金融法规对敏感客户记录的物理存储地点有着严苛的司法管辖界限。为了平衡灾备冗余与法规约束，我们采用元数据解耦架构：跨区域仅同步Trace链路的元数据与不含敏感业务负载的唯一ID（Metadata & Trace IDs），而承载高敏感业务上下文的原始链路明细数据（Core Trace Data）则被严格锁定在主区域，物理层面杜绝跨管辖区流转。

<details>
<summary>Original English Source</summary>

The second pillar, disaster recovery, is not like optional infra hygiene for a bank. The complication here is that the main database platform most AI observability tools use, including some of the companies that are sponsoring this conference, there's no managed service for failover across regions and data replication. Anyone happen to know what database platform I'm talking about?

So, with Redis, Postgres, there's managed failover across regions, but this one database does not have a story. ClickHouse is an amazing database platform, but even in their data resiliency docs they call out that there's no managed service managed failover across regions. So this means the banks are kind of up to themselves to figure out that disaster recovery situation.

So a simple pattern that you can employ is you have ClickHouse in a primary region, a job that backs up to a bucket, and then another job that restores that bucket to a DR region. Within that region, you might have multiple pods that have replicas of that data. This whole procedure relies on ClickHouse backup, which is an open-source project maintained by Altinity, who they themselves are a competitor to ClickHouse in terms of managing this data failover across regions.

ClickHouse backup shares logs on whether or not the backup and restore happens, so you can get this nice table. But this status says nothing about your data at this point in time. A bad disk, a bad node, bad migration, replication lag, these are all issues that can cause your data to become stale, that is different from when this job actually ran. So you can go the extra step in checking the row counts between tables, running a check to see if the replicas within a region have converged to each other.

And the takeaway here is that it's about data correctness, and not necessarily just checking a box and seeing if the backup and restore job ran. Similar to the CVEs, you can't just bump the version and assume the exploit's gone. You have to do these extra checks.

And one call out for any of the architects who are creating this kind of backup and restore within your cluster is that you're also making a decision around data residency, whether you like it or not. When you're replicating to a bucket, the bucket doesn't care if it's in Oregon or Virginia. Data residency, however, cares about where those individual records are stored.

So, one solution is you can replicate just the IDs and the metadata around your traces and your data into different regions. But, then the actual core trace data, that's stored within one region and doesn't leave that region because of certain jurisdiction laws.
</details>

### 第三支柱：LLM-as-a-Judge隐性数据泄漏防范与双模型隔离流水线

第三大核心支柱关乎数据隐私泄露的防御。几乎所有银行在评估自身AI系统时，都坚信自己绝不会向内部非授权员工或专属VPC之外泄漏任何敏感信息，但现实系统中往往存在未被察觉的隐蔽侧门（Side Doors）。当前银行普遍在SDK层、API网关层以及通过各种**中间件**（Middleware）对**PII**（Personally Identifiable Information: 个人可识别信息）和**MNPI**（Material Non-Public Information: 重大非公开内幕信息）执行严格脱敏。在终端用户界面上，所有客户敏感字段确实都被妥善掩盖了。

然而，致命的隐患出在评估层——**大模型裁判**（LLM-as-a-Judge: 利用大语言模型对其他AI生成内容进行打分、合规审查与质量归因的自动化评估架构）。我建议所有工程团队认真审查自己大模型裁判的**系统提示词**（System Prompt），并逐一核查评测链路日志中的推理过程（Reasoning Steps）。在常规设计中，裁判模型不仅要输出打分，还需要写出详细的推导理由，以便人类质检员复核智能体的表现与准确率。提示词中看似极度无害的一句“请结合输入上下文详细阐述打分依据”，却赋予了裁判模型在推理思维链中反向复原（Un-redact）原始PII或MNPI的漏洞。前端UI虽然干干净净，但后端的Trace数据库却静默沉淀了包含客户真实隐私的大模型思考过程，造成事实上的合规违规。

针对这一侧门漏洞，我们设计了**渐进式隔离过滤机制**：
* **解耦持久化策略**：允许裁判模型直接消费未脱敏的原始链路数据以保证评估准确度，但在存储落盘时将分数与推理过程物理拆分。评估得分始终持久化并展示在前端看板；而针对推理过程，在应用代码层必须经过合规检测断言——仅当确认文本不含敏感数据时才允许落盘并对前端可见，否则彻底抑制（Suppress）推理文本的输出。
* **双裁判双模型流水线**（Dual LLM-as-a-Judge Pipeline）：由于银行质检与审计人员往往强烈要求查看包含敏感业务场景下的完整评测思考逻辑，我们在工作流中追加了第二道解耦流程。第一道裁判负责原始高精度评分，第二道裁判则强制只读取经由网关完全脱敏后的上下文副本。由于输入源完全干净，该模型生成的推理过程天然具备零泄露保证，可安全持久化并呈现在质检UI中。

必须清醒认识到：**零泄漏与数据主权从来不是免费的**。在这套方案中，它的直接代价就是针对同一笔业务请求重复发起第二次大模型调用的计算与API成本。但这正是建立跨部门信任的底层逻辑——在合规审查面前，供应商绝不能仅抛出一句“相信我们”。你必须如同高中的证明题一样，完整公开实现逻辑与可核验的实证记录。

<details>
<summary>Original English Source</summary>

The final pillar is most banks think that they are not leaking any sensitive information to their internal employees, their users outside of their VPC, but there may be side doors that are open. And this comes in the form of PII, MNPI being redacted. And there's many different strategies for this. You can redact information at the SDK level, at the gateway level, using various middleware. And what this looks like in practice is on the UI, you might have some customer information, sensitive information is redacted.

But, what about the judges that you're using? I challenge all of you to look at the system prompts for your LLM's judges and check the traces to see if those traces with the reasoning from those judges contain any PII or MNPI.

Here's a system prompt for a simple judge. It outputs a score and explanation on how well the agent performed for a given task. But, there's one line here in the prompt, which is seemingly innocuous because you want the human reviewer to be able to verify if the agent did a good job and was accurate. This just potentially may have allowed the judge to leak and unredact PII or MNPI. So, your UI still looks good, but then on the back-end your LLM as judges reasoning may un-redact customer information and sensitive information.

So, one strategy for this is you can still have your judge read the raw trace data, but the reasoning for that judge is not persisted. The score, however, you want that score, it's for good for evals, that always persists through the UI, but then on this other branch the reasoning, as we saw, can still leak PII. But in your application code, you can have a check that tells the agent this record does not contain sensitive information and therefore can persist to the UI. So, now you have a score plus the reasoning for this record. And then if that check comes back negative, it does have sensitive information, then you just suppress that reasoning from the UI.

Most of the banks we work with, they want to see the LLM as judges reasoning on this sensitive information. And the extra upgrade you can add to this flow is you have a second LLM as a judge where the input is redacted of sensitive information and therefore you can have confidence that the output from the judge is clean and then you can have that show up in the UI.

The takeaway here is that having zero leakage and data sovereignty is not free. In this case, it's the cost of running another LLM call on the same request.
</details>

### 从技术指标到组织对齐：金融级AI交付的制胜杠杆

在面对安全与合规团队时，真正能撬动“合规推进速度”的战略杠杆，始终是**展示你的完整证明过程**（Showing Your Work）。许多软件供应商经常轻率宣称：“我们的系统只需数周即可上线生产环境。”但他们刻意回避了前提条件——这种估算从未结合银行特定的复杂底层基建、专属安全态势以及特定Kubernetes集群的定制策略进行实地测算。

根据我们的实际落地经验，能够显著压缩上线周期的正面信号，本质上取决于基础设施流程的标准化程度：从私有镜像仓库拉取镜像的机制是否规范闭环、用于推理加速的**GPU算力**是否已完成采购并就绪。反之，如果银行内部存在冗长僵化的安全评审流程、各部门自建封闭的定制LLM网关或**RBAC**（Role-Based Access Control: 基于角色的访问控制）权限配置体系，项目周期往往会被顺延数月；而一旦银行甚至尚未确立从外部向内网镜像仓库同步镜像的审批制度、且缺乏明确的GPU算力采购路径，交付周期则会直接失控。我们发现，导致工期拖延的核心瓶颈往往不是纯技术算法，而是银行内部错综复杂的组织对齐与跨部门协作成本。

当客户带着一线生产系统的阻碍找到我们时，这些问题就直接转变为我们团队的攻坚目标。我们将客户的痛点系统拆解为三大执行工作流：工程实现工作流、业务流程工作流、以及组织机制协同工作流。我们的目标是在工程层面实现最大程度的自动化，但那些真正让人在深夜辗转反侧的深层痛点，始终是防止被竞品在工程深度与组织适应力上超越的护城河。不要做一个平庸的软件售卖商，而要成为客户真实痛点的攻坚解决者。

在金融服务业部署AI面临极高的社会责任风险——它直接连结着普通人的支票账户、房屋抵押贷款和信用卡账单。在这些场景下，确保结果精确到小数点后第四位、并拿出无可辩驳的推导证明是不可妥协的底线。这也是为什么金融机构至今仍运行着大量看似陈旧的技术资产。但在今天，在座所有致力于攻坚复杂工程的从业者，正在推动这道划分传统金融与前沿创新的技术分水岭缓慢前移。对于那些愿意直面慢节奏、枯燥繁琐、官僚体制以及金融行业复杂组织痛点的极少数工程师而言，在金融行业成功落地AI所获得的系统成就感，是任何低门槛领域都无法比拟的。

<details>
<summary>Original English Source</summary>

So, one way we're able to build trust with these security and compliance teams is that we're not just saying trust us, here's the answer. We have to show the evidence and the work on how we arrived at the answer. And many vendors will tell you, you know, our deployment time to production takes a few weeks, but what they're not saying is they didn't check that time against your infrastructure, your security posture, and the nuances about your specific cluster.

And so certain signals that we look for in terms of shortening that time to production is really just having a lot of processes set up in terms of, you know, how you pull images down from a registry, having GPUs sourced and ready to go for running inference. That timeline gets pushed out a couple months when you have formal security reviews, or you're building a custom LM gateway or RBAC configuration. And then that timeline gets pushed even further out when you don't even have an approval process for pulling images down to your registry, and not having a story around sourcing and procuring GPUs.

Now, I found that most of these signals that push the timeline out are less technical and more about internal human and organizational challenges and alignments at the banks, but still important factors to figure out.

So, the theme for today is showing your work. That is the real lever that you have on compliance velocity when working with a bank. And when one of our customers come to us and tell us, "Hey, our customers are having problems," those problems now become my team's problems. And we break those problems down into engineering, workflow, and human and organizational work streams.

The goal is to automate as much as possible, but those problems are the ones that keep me up at night. And I want to ensure that our competitors don't outwork us and don't outsmart us on any of those vectors. And I would say that you don't want to just be another vendor, you want to actually be solving your customers' problems.

And I would say the biggest lesson I've learned from working with these banks and security teams is that there's so much at stake. Checking accounts, mortgages, credit cards. Getting your answers down to the fourth decimal place matters in these situations. And there's a reason why a lot of the software within these banks is old and outdated. But the line between legacy software and old banking processes and innovation is moving a little bit every day and it's because of all of you.

So I think all of you are exploring different agent frameworks and building with new harnesses, playing with Jev. And I would say for the few of you who care about the slow, the boring, the bureaucratic, the methodical, the messy human and organizational challenges within a bank, there's nothing like deploying AI within the financial services sector because there's so much at stake.

And yeah, if you all want to score your own deployments against these pillars, just reach out. I only discussed three pillars today, but there's a whole production checklist that we use that underpins these pillars.

Going back to my 10th grade math test, one of the best parts about those tests were afterwards me and my friends, we'd go to the lunch table and we'd try to scribble down all the problems we remembered from the test. And then we use that time to talk about, "Hey, here's how we approached solving this problem and that problem." And it allowed me to kind of think about different approaches and different ways to solving these problems. And conferences like this are kind of like that lunch table back from when I was in 10th grade because I want to learn from all of you on how you're solving your problems for your customers. Thank you very much.
</details>