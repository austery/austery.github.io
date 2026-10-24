---
author: AI Engineer
date: '2026-05-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4_VQBbs2iQA
speaker: AI Engineer
tags:
  - engineering-productivity
  - ai-agent
  - claude-code
  - software-development-lifecycle
  - agent-first-development
title: AI 驱动的工程效能革命：Intercom 如何在一年内实现研发吞吐量翻倍
summary: Intercom 高级首席工程师 Brian Scanlan 详细解析了公司内部的 Project 2x 计划。通过将 AI 代理（特别是 Claude Code）深度集成到软件开发生命周期（SDLC）中，Intercom 不仅实现了 PR 吞吐量翻倍，还重构了组织文化，将 AI 视为一名具备完整权限的“高级工程师”，在自动化 Code Review、安全事故处理和测试优化等方面取得了显著突破。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Brian Scanlan
companies_orgs:
  - Intercom
  - Anthropic
  - OpenAI
products_models:
  - Finn
  - Claude-Code
  - GPT-4
  - Cursor
media_books: []
status: evergreen
---
### Intercom 的 AI 转型背景：从 B2B SaaS 到 AI 原生公司

**Intercom** 是一家拥有 15 年历史的爱尔兰-美国 B2B SaaS 创业公司，在 ChatGPT 发布后的那个周末，公司果断决定全面转型为一家 AI 公司。目前公司拥有约 1400 名员工，研发中心设在都柏林。其核心 AI 产品 **Finn**（为客户支持设计的 AI 代理）已经拥有超过 8000 家客户，年收入接近 1 亿美元，是业内首个基于 **GPT-4** 发布的商业产品。Brian 指出，成为一家 AI 公司远不止是在界面上加一个“自动补全”的轻量级包装，而是要深度利用 **大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）解锁处理客户支持问题的巨大潜力，目前 Finn 每周处理约 200 万次问题解决。

<details>
<summary>Original English Source</summary>
Intercom is a 15-year-old privately held Irish-American B2B SaaS startup that has pivoted to be an AI company the weekend that ChatGPT came out. I've got about 1,400 people across Dublin, London, Berlin, SF, Chicago, Sydney. R&D is led from Dublin. Engineering is almost entirely across Europe. Our AI agent for customer support, Finn, has over 8,000 customers, industry-leading average resolution rates, revenues like approaching 100 million, launched the day GPT-4 came out, first product actually released on GPT-4. And companies like Anthropic, Snowflake, Linear, Glean, LaunchDarkly use Finn for their customer support. So maybe SaaS isn't dead. And it works well for all size businesses. Also, we recently announced that we have our own model serving 100% of Finn... cheaper, faster, better. And we're at like about 2 million resolutions a week.
</details>

### Project 2x：通过 AI 实现工程吞吐量翻倍的野心

在成功推出面向客户的 AI 产品后，Intercom 将目光投向了内部。去年年中，公司设立了一个简单但极具挑战的目标：**Project 2x**，即在不增加团队规模的情况下，将工程吞吐量翻倍。他们选择**每人平均代码变更量**（Code changes per R&D person）作为核心衡量指标。Brian 承认，任何单一指标都有局限性，但如果公司真正采用了新的工作方式并在各环节集成 AI，吞吐量的显著提升是必然的结果。这一目标的设定既被视为“疯狂的野心”，也被认为在 AI 模型和编程工具链（Coding harnesses）飞速进化的背景下是理所当然的。

<details>
<summary>Original English Source</summary>
So last year, middle of last year, we set a simple goal. Let's double the throughput of engineering in a year. We picked code changes per R&D person as the primary way we're measuring productivity. Every measure is bad. Once you start measuring it, it's not a measure and all this. But also like we expect the overall throughput to increase. If we're like actually adopting new ways of working, putting AI into all of the different places, then we should expect a large throughput increase. And so 2x, what we call this, Project 2x. This is like wildly ambitious... but also kind of wildly unambitious as well if you like connect the dots and see where the models and coding harnesses are going.
</details>

### 组织变革与决策：将 AI 集成纳入员工考核

实现 2x 目标的关键不在于工具本身，而在于**组织变革**。Intercom 采取了果断的行政指引：更新职位描述，明确规定如果员工（无论是设计师、产品经理还是工程师）不采用 AI，将被视为“不符合预期”。公司通过各种渠道上百次地重复这一信息，强调紧迫性。同时，公司设立了专门的奖励机制，在 Slack 频道中公开表彰那些利用 AI 实现自动化的案例，并举办黑客松和 AI 沉浸日（AI Immersion Days）。最重要的是，Intercom 投入了核心人才组建全职的 **2x 团队**，负责带领数百名工程师进行转型，因为中大型组织必须有顶尖人才全职负责此类变革。

<details>
<summary>Original English Source</summary>
This is the kind of engineering leadership-y part of the talk. You need to be decisive and give clear executive guidance and do organizational change. We updated job descriptions. If you're not adopting AI in Intercom, whether you're a designer, product manager, engineer, whatever, you are not meeting expectations. Binary. And yeah, you have to say the same message over and over and over 100 times... constantly talk about the urgency of us doing this. You got to reward us as well... all the Slack channels showing like automating... We celebrate stuff. We've done hackathons. We've done AI immersion days. And you know, all of these things are necessary to kind of bring people along. Like also, we staffed this full-time. We have a team 2x.
</details>

### 平台化战略：为何全面投身 Claude Code

在工具选择上，Intercom 经历了从开发者自主选择（Cursor, Augment 等）到统一使用 **Claude Code** 作为官方平台的转变。Brian 强调了**平台意识**的重要性：为了避免“模型焦虑”和碎片化，必须选择一个单一平台进行深度优化，这类似于选择单一云服务商而非多云策略，从而获得**复利效应**（Compounding benefits）。他们的愿景是让 Claude 能够像一名高级工程师一样，在 Intercom 的任何技术任务中发挥作用。这不仅意味着代码生成，还包括调试、测试和规划。通过成熟的审计和权限控制，Intercom 像信任人类工程师一样，赋予了 Claude 操作生产环境的能力。

<details>
<summary>Original English Source</summary>
And so we chose Cloud Code (Claude Code) as our platform. Prior to this, we were kind of letting people choose their favorite editor. But we're a believer in platforms in general. And it kind of doesn't matter what you choose, but choosing one is important. To a certain extent, you need to get away from model anxiety. It's like being multi-cloud. Like you don't get the compounding benefits of a well-designed platform if you're sending all your different work across different cloud providers. Our vision here was like connect Claude to everything. So anything I do on my laptop, Claude should be able to do this. And that means everything. We've got plenty of controls and permissions and audits... that gives us a lot of confidence to be able to like unleash Claude in the same way that we unleash our engineers in our environments.
</details>

### 角色演进：从代码编写者到“代理驾驶员”

Brian 将当下的工程变革类比为早年从 **Unix 系统管理员**（Sysadmin）向 **站点可靠性工程师**（Site Reliability Engineer: 负责系统的稳定性、扩展性和性能的工程学科）的转变。工作内容变得更加自动化驱动、影响力更大。在 Intercom 的新范式下，工程师的工作是“驾驶（Driving）”代理，并不断向上层移动。他们不再只是编写代码，而是编写**技能**（Skills）和指引（Guidance），将公司过去 15 年积累的 Rails 约定、架构模式和测试标准封装进 AI 代理中。这种“代理优先（Agent-first）”的方法让大量 SDLC 工作被自动化替代，工程师则负责描述问题而非具体步骤。

<details>
<summary>Original English Source</summary>
Our job is moving up the stack as engineers. A long time ago I used to be a Unix sysadmin... racking servers, cabling things. And then the cloud came along and I moved up the stack... people transition from being sysadmins to SREs. The work was more automation oriented, more impactful, higher paid. I think this is like we're kind of speed running this 100 times faster. Everything that you can do the agent must be able to do. It should just be you driving Claude and ideally driving it less and less and moving higher up the food chain. We focus on small, high-quality, durable, testable skills that do the job extremely well. Give problems to agents, not tasks.
</details>

### 突破瓶颈：自动化代码评审与 2x 吞吐量的达成

Intercom 的数据显示，他们在不到一年的时间内就提前实现了研发吞吐量翻倍的目标。目前，约 90% 的 **拉取请求**（Pull Request: 开发者提交代码变更以供评审的过程）涉及 Claude Code。为了解决“代码审查”这一瓶颈，他们引入了基于 AI 的自动审批机制，目前自动审批率达到 17.6%。这一机制并非简单的“一键批准”，而是通过大量历史数据标签和回归测试，训练出具有高度置信度的审批代理。Brian 指出，AI 在处理符合审计标准（如 SOC 2, HIPAA）的审查时表现甚至优于人类，因为它能够严格执行预定义的规则而不产生疲劳。

<details>
<summary>Original English Source</summary>
We have reached the doubling PR throughput in faster than 1 year. Number of pull requests out of our Claude code is like in the 90 somethings. Our current bottleneck is code review... but we have this like 17.6% approval rate of our automatic code approval. We've gone through a lot of detailed work to figure out again using backtesting and previous data and then getting humans to kind of label the outputs. You do not need humans in the loop to meet these certifications (SOC 2, ISO 27001, HIPAA). I think it's removing risk because humans aren't actually as good as agents like when they're well-defined.
</details>

### 效能实战：安全事故处理与测试套件的“降温”

Brian 分享了两个极具代表性的案例。首先是一次安全事故：由于不小心将 **Snowflake** 数据库的元数据发布到了公共 GitHub，Brian 开启 Claude 并将其加入相关 Slack 频道。Claude 自动识别并调用了公司内部的“数据泄露政策”技能，自主完成文件下载、分析并得出“无害”结论，整个过程仅耗时 2 分钟，而手动处理则至少需要 20 分钟。另一个案例是**测试套件优化**：他通过与 AI 的持续反馈，构建了一个专门修复 **不稳定测试**（Flaky specs: 在相同代码下有时通过、有时失败的不可靠测试）的技能。该技能利用了高级工程师的“秘籍表（Cheat codes）”，其修复质量达到了公司资深工程师的水平。

<details>
<summary>Original English Source</summary>
I was brought into a security incident. We had accidentally published some Snowflake table metadata to a public GitHub repository. I opened Claude code, told us to join a Slack channel. Claude just automatically downloaded the files, did full analysis, concluded it was innocuous, told me all next steps. Done in like 2 minutes. Another example skill... it fixes flaky specs. This scale was built in a feedback loop, gave the agent a goal... it's written this pretty decent thing with all these cheat codes. It is like fixing stuff that if our most senior rails engineers were doing this, I'd be like, well, they're amazing.
</details>