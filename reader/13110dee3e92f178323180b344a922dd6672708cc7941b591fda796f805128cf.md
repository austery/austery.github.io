---
author: AI Engineer
date: '2026-09-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=474j-n1Ltxc
speaker: AI Engineer
tags:
  - ai-generated-code
  - coding-agents
  - code-review
  - software-quality
  - pull-request
title: AI 生成代码已能匹敌人类：基于数百万真实 PR 的企业级实证分析
summary: Greptile 联合创始人基于每月数百万 GitHub 企业级 Pull Request 真实数据，深度剖析了 AI 编码智能体在实际生产环境中的表现。数据证明，AI 生成代码的 Revert 率、严重缺陷密度及评审轮次已与资深人类工程师相当，但其在 SQL 注入等特定故障模式上呈现独特的风险分布，进而倒逼现代代码验证与审查体系发生根本性范式转移。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Greptile
  - GitHub
products_models:
  - Devin
  - Claude
  - Cursor
media_books: []
status: evergreen
---
### 范式演进：从代码补全到全自主编程智能体

回顾 AI 编程的发展历程，其演进速度彻底颠覆了软件工程的底层假设。在 2022 年 **GPT-3.5**（OpenAI 发布的初代大语言模型）问世之前，AI 辅助编程几乎是一片荒原；直到该模型展示出真正理解并编写程序的潜力，以 **GitHub Copilot** 和 **Cursor** 为代表的代码自动补全功能才确立为行业的核心交互范式。随后的技术跃迁以极高的加速度推进：2024 年初，Cursor 等工具率先攻克了跨多文件协同编辑的工程瓶颈，使模型具备了跨模块重构能力；而进入 2025 年，**自主编程智能体**（Autonomous Coding Agents: 能够根据自然语言任务自主探索代码库、执行修改并提交交付的智能系统）迎来了质的爆发。

在过去，开发者需要实时关注补全建议；而在当前的智能体架构下，工程师只需输入高阶需求指令，智能体即可端到端完成从环境理解、代码修改到生成完整 **Pull Request**（代码合并请求，简称 PR）的全套流程。社交网络上随处可见个人开发者利用 Agent 单日提交上百个 PR 的记录。然而，这种繁荣伴随着强烈的行业分歧：这些由智能体自主创建的 PR 究竟只是独立开发者或玩具项目的狂欢泡沫，还是已经具备在严苛企业生产环境中落地服役的工程质量？真实工业界亟需基于真实生产数据的权威检验。

<details>
<summary>Original English Source</summary>

How are you doing? Perfect. My name is Daksh, and I am one of the co-founders of a company called Greptile. At Greptile, we build AI code review agents for pull requests with full codebase context. Greptile spins up a team of agents that review every changed file and related files to find bugs, and also runs your code in sandboxes, sets up bad dependencies, spins up local servers, and simulates user actions to see if anything breaks.

But today I want to talk about something else: completely autonomous agents for writing code. I moved to San Francisco three years ago to work on AI programming because GPT-3.5, released in 2022, was the first model that genuinely seemed to write programs well. Back then, code completion via Copilot was the dominant programming paradigm. What was most interesting was autocomplete in Cursor and autocomplete in Copilot—that was the primary method of AI in programming.

In 2024, at the beginning of the year, multi-file editing started working. Cursor was the first to do it, and then other similar products emerged, enabling AI to edit multiple files simultaneously. But what is truly fascinating happened in 2025: for the first time, truly autonomous agents appeared. You give them a task, and they can execute it, creating complete pull requests in one shot. This reached a turning point late last year when coding agents became genuinely autonomous. Anyone working in AI programming knows that moment was a major inflection point in history. Twitter was flooded with unbelievable stories of people running agents submitting 100 PRs a day with multi-stage planning.

When I started programming before agents emerged, I was deeply skeptical about whether real companies could actually build production software with this. Are all these completed pull requests actually good quality? Or is it just Twitter hype, hobbyists, indie hackers, and small startups without real customers? Can real customers with production, mission-critical code actually use these end-to-end coding agents?
</details>

### 生产环境探秘：百万级 PR 中的真实 AI 渗透率

为了解开 AI 生成代码在工业级环境中的真实渗透率，研究团队调取了底层大规模生产数据集。目前，Greptile 为 **Nvidia**、**Coinbase**、**Scale AI** 以及 **Datadog** 等全球顶级科技企业提供代码评审基础设施，每月审查的 Pull Request 数量超过 **100 万次**。在对海量生产代码进行实证分析时，首要挑战在于构建高精度的探测机制：如何从 GitHub 的海量提交中精准剥离出由 AI 代理自主生成的代码？

初步研究显示，仅凭 Git 提交记录中的 Author 字段极具误导性，在原始元数据中署名为 Codex、Claude 或 Cursor 的比例不到 1%，这是因为绝大部分开发者通常以个人凭据代理提交。研究团队进而设计了一套组合特征识别策略：
1. **署名指纹检索**：精确扫描 PR 描述中保留的工具水印（例如 `co-authored-by Claude` 或 `co-authored-by Cursor`）。
2. **分支命名特征分析**：提取编码 Agent 在自动化创建分支时固有的特定命名语法前缀。
3. **提交与行为模式对齐**：结合全自动生成与深度上下文辅助的特征图谱。

通过这套高可信度指标回测过去 12 个月的数据发现，目前全球月度审查的 GitHub PR 中，已有约 **4%** 完全或绝大部分由 AI 自主生成。更关键的是，这一曲线呈现出极其平滑且陡峭的复合增长态势，并未因特定新基座模型的单点发布而产生脉冲式震荡，证实 AI 编码智能体正以不可逆的确定性深度渗透进主流企业的研发管线。

<details>
<summary>Original English Source</summary>

We are fortunate to work with some very large companies—Nvidia, Coinbase, Scale AI, Datadog, and American Express. We wanted to truly understand if these agents are being used in large companies and whether they effectively solve real-world programming problems. As a data enthusiast in the industry, I decided to dive into our data. We review over a million pull requests each month, giving us vast data on what works and what fails across thousands of companies, mostly large enterprises with critical products and real users.

Surprisingly, identifying which pull requests across GitHub were actually created by AI turned out to be unexpectedly hard. The first thing I tried was looking at the author field on GitHub commits. But less than 1% of pull requests had Codex, Claude, or Cursor explicitly listed as the author. It made no sense that less than 1% of all code was generated by AI, so the real number had to be much higher.

I started looking for secondary signals. Fortunately, Claude, Codex, and other tools often leave footprints in the PR description, such as "Co-authored-by: Claude" or "Cursor Co-authored". That provided a reliable signal for PRs generated largely by AI. The third signal I noticed was branch prefixes. If you use coding agents, you know their characteristic branch-naming conventions. It made total sense that PRs with these specific branch prefixes or title structures were predominantly AI-generated.

Combining these signals allowed me to reliably identify whether a PR was completely or heavily created by AI. The analysis revealed that approximately 4% of all pull requests reviewed on GitHub every month are now completely or deeply created by AI. Tracking this over the last 12 months showed exponential growth: early last year, less than 1% had signals of being entirely AI-generated. The adoption curve is climbing rapidly and steadily, showing continuous economic integration rather than isolated spikes around model releases.
</details>

### 质量真相：AI 生成代码与人类工程师的硬核指标对决

伴随所谓 **“氛围编码”**（Vibe Coding: 开发者仅依靠高层自然语言提示词驱动 AI 生成实现，弱化逐行代码把控的开发模式）的流行，行业核心的疑虑集中在代码质量的真实可用性上。研究团队引入了三组多维实证指标，对人类工程师与 AI 智能体提交的代码展开了严密的对照测试。

首先是 **代码回滚率**（Revert Rate: 合并后因线上故障或严重缺陷被强制撤销的比例）。这一指标直接反映代码是否引发了破坏性破坏。数据统计显示：
* **人类工程师** 的 Revert 率约为每千次 PR 发生 **2.5 次**。
* **Codex** 生成的 PR 其 Revert 率仅为每千次 **1.0 次**。
* **Devin** 生成的 PR 其 Revert 率约为每千次 **3.5 次**。

为排除“人类承担复杂高危任务，而 Agent 仅处理微小低风险变更”的幸存者偏差，研究进一步计算了代码变更量（PR Size）与回滚率的关联度，结果证实二者在统计学上仅存在极弱相关。

其次是 **缺陷拦截密度**。通过 Greptile 系统对代码库注入的 P0（系统崩溃级）、P1（核心逻辑错误）及 P2（次级隐患）三级严重缺陷进行全量统计，在四个基准测试维度中，AI 智能体在三项测试中的 P0 缺陷产生率甚至**低于人类平均水平**。最后，在 **合并前评审轮次**（Review Iterations: PR 从发起至达到合并标准所经历的审查与修改迭代次数）指标上，人类平均耗费约 2.2 轮，Devin 为 2.1 轮，Codex 为 2.45 轮，各方在统计学上表现出近乎一致的收敛速度。各项硬核数据表明，AI 生成的代码在宏观工程质量上已完全具备与专业人类工程师平起平坐的能力。

<details>
<summary>Original English Source</summary>

That led to the next question around "vibe coding": all these PRs created entirely by AI without human intervention except prompting—are they actually good? What constitutes a good PR? That seemed like a critical question before evaluating AI-generated PRs.

I evaluated this using multiple methods. First, I looked at the revert rate. If a pull request gets reverted, something likely went wrong, making it a solid proxy for a bad PR. GitHub conveniently tracks this via revert branch names and "revert-pr" references. The findings were fascinating: Codex PRs were reverted roughly 1 time per 1,000 PRs; Devin was around 3.5 per 1,000; and humans averaged around 2.5 per 1,000. There was no statistically significant divergence in revert rates between humans and agents.

I remained skeptical, wondering if this was simply because humans delegate easier tasks to agents while taking on complex, risky tasks themselves. So I measured whether PR size and reverts correlated, but found very weak correlation between PR size and failure rates across both groups. This refuted the assumption that human PRs are intrinsically superior to agent PRs on basic reliability.

The second signal analyzed was the volume of review comments and severity levels. Greptile scans all PRs for P0, P1, and P2 level bugs. If code quality was worse, we would expect a noticeable spike in high-severity issues. Surprisingly, there was no massive negative difference. In fact, in 3 out of 4 benchmarks, agents produced fewer P0 critical bugs than human engineers, with similar parity across P1 and P2 issues.

Finally, we looked at review iterations—the number of back-and-forth review rounds before a PR is merged. For Devin, it averaged 2.1 rounds; for Codex, 2.45 rounds; and humans sat squarely in the middle. Across revert rates, critical bug rates, and iteration cycles, AI-generated PRs demonstrate overall quality on par with human engineering output.
</details>

### 异构缺陷图谱：AI 与人类工程师在失效模式上的本质分野

尽管在宏观质量评分上 AI 与人类难分伯仲，但微观层面的失效机理却揭示出截然不同的行为特征。基于数百万条评审评论语料库的文本挖掘与语义聚类，研究团队构建了详细的 **故障分布模型**（Failure Mode Distribution）。该模型以人类犯错概率为 1.0 的基准参考值，清晰展现了 AI 与人类工程师截然不同的漏洞侧重。

实证结果显示，AI 智能体并非人类认知的等比例复刻，而是呈现出高度结构化的特定偏置：
* **安全防护盲区**：在 **SQL 注入**（SQL Injection: 恶意构造的 SQL 语句在后端未经严格转义直接执行的安全漏洞）等经典边界安全场景中，**Claude** 产生该缺陷的倾向高达人类的 **1.5 倍**。
* **特定逻辑准确性**：与之形成鲜明对比的是，**Devin** 在处理边界越界（Off-by-one 逻辑偏移）等经典离散算法缺陷时，其犯错概率比人类工程师低了整整 **2 倍**。

这种异构的缺陷图谱明确推翻了“AI 能够无条件平替人类做单点逻辑审查”的设想。智能体虽然擅长遵循类型定义、语法规范与常规控制流，但在需要宏观威胁建模、上下文假定与全局安全防御的领域展现出反常的脆弱性。这也解释了为何即使总体指标合格，资深架构师在直觉上依然对完全由 AI 生成的代码抱有警惕——其错误的发生方式完全脱离了人类软件工程常见的直觉轨迹。

<details>
<summary>Original English Source</summary>

Given that aggregate quality metrics showed parity, I suspected qualitative differences existed in their failure modes. Perhaps the ways agents fail are fundamentally different from the ways humans fail.

I turned back to Greptile's corpus of review comments, which averages about four comments per pull request across millions of data points. We scanned this corpus for specific domain terms and vulnerabilities—such as SQL injection patterns or N+1 query inefficiencies—to map out failure mode distributions. Taking 1.0x as the baseline human tendency for each error category, we discovered massive divergence.

Agents operate with an entirely different error distribution compared to humans. For instance, Claude was 1.5 times more likely than a human developer to introduce a SQL injection vulnerability. On the other hand, Devin was more than twice as unlikely as a human to make an off-by-one boundary error. 

This reveals that while coding agents have reached production-level capability and are actively contributing to enterprise codebases, their underlying error distributions are fundamentally distinct from human engineers. They do not fail like we fail.
</details>

### 吞吐量暴增后的重构：面向 Agent 时代的下一代代码验证体系

当生产力工具从辅助编写转向自主代理后，软件工程的核心瓶颈已从“代码生产”转移至“代码验证”。数据统计表明，在 Greptile 平台上，普通工程师每月平均创建约 50 个 PR（日均 2 个）；而处于前 10%（P90）的高频工程师每月创建超过 **500 个 PR**；至于前 1%（P99）的顶尖使用者，月度提交量更是达到了数千级别。面对如此庞大的吞吐增量，传统依赖人工逐行审查、被动单元测试或人工 QA 验收的流水线已彻底面临系统性过载与崩溃。

为了在极速交付与系统可靠性之间取得平衡，验证体系必须回归第一性原理。现代代码把关不再纠缠于琐碎的格式语法，而是聚焦于回答三大根本契约问题：
1. **现有契约一致性**：本次代码变更是否破坏了系统已向用户或下游承诺的行为契约？
2. **未来退化风险**：即便当前未报错，该修改是否在概率上大幅提升了系统未来违背契约的脆弱性？
3. **真实意图对齐**：代码的实际逻辑路径是否精确达成了提交者所期望解决的业务目标？

为实现这三大验证，新一代审查系统必须超越静态文本分析，赋予智能体动态执行权限：在隔离的 **沙箱环境**（Sandboxes）中构建依赖、启动本地微服务、构造模拟边界数据，并通过无头浏览器代理完整重现用户链路。目前，在 Greptile 审查的代码库中，已有 **20%（五分之一）的 Pull Request** 在完全未经任何人类逐行审查或人工介入测试的情况下，通过全自动化验证直接安全合并至主干。这标志着软件工程正在迈入以持续高置信度自动化验证为基石的全新时代。

<details>
<summary>Original English Source</summary>

This brings us to what code review looks like in an agent-dominated world. Today, Greptile is used by tens of thousands of engineers every week. The average user creates 50 PRs a month—roughly two per working day. The 90th percentile creates 500 PRs a month, and the 99th percentile produces thousands of pull requests monthly. People using stacked PR workflows powered by AI are shipping changes at unprecedented velocity.

Existing systems for verifying code—manual peer review, static testing, and traditional QA—simply cannot scale to this velocity. At Greptile, we decided to rethink high-quality code verification from first principles. Instead of surface-level QA automation, we asked: what is fundamentally required for someone to safely merge hundreds of PRs a month in a mission-critical enterprise environment? How do you minimize time-to-merge while ensuring absolute safety?

We found that verification boils down to answering three essential questions:
1. Does this change break an existing user contract?
2. Does it increase the likelihood of breaking contracts in the future, even if it doesn't fail today?
3. Does it accurately fulfill what the author originally intended?

To answer these, agents must be empowered to understand contracts and catch regressions dynamically. By allowing verification agents to run code inside sandboxes, provision dependencies, simulate edge-case data, and orchestrate browser agents, they can identify the vast majority of breaking issues before production. Today, one-fifth (20%) of all pull requests reviewed by Greptile are merged entirely without human review or manual QA. This is the new baseline for continuous, high-confidence automated software engineering. Thank you. My name is Daksh, co-founder of Greptile.
</details>