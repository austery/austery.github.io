---
layout: post.njk
source: https://blog.qiaomu.ai/everyone-should-have-an-opinions-md
speaker: 向阳乔木
title: 每个人都应该有一个 OPINIONS.md · 乔木博客
date: '2026-05-07'
summary: 本文介绍了工程师 Kun Chen 如何利用 AI Agent 自动化地生成并每日更新其个人观点文件 OPINIONS.md。该系统扫描其在线内容，提取持久性观点，过滤噪音，并包含“看门狗”机制以检测观点漂移和事实风险，解决了个人观点分散的问题。
area: pai
category: ai-workflow
tags:
  - ai-agents
  - personal-knowledge-management
  - workflow-automation
  - opinion-extraction
people:
  - Kun Chen
companies_orgs: []
products_models:
  - OPINIONS.md
  - AI Agents
  - Hermes Agent
media_books: []
draft: true
status: evergreen
---

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# 每个人都应该有一个 OPINIONS.md

AI教程

·

2026年5月7日

·

319 次阅读

·

约 77 分钟

> 原文：https://blog.kunchenguid.com/p/everyone-should-have-an-opinionsmd

软件工程师 Kun Chen 用 AI Agent 每天自动扫描自己在网上发布的所有内容，提炼出一份观点文件OPINIONS.md。

这个文件不仅帮他更清楚地认识自己，还让他的 AI 助手在执行任务时更像他的真实判断。

这件事在 Agent出现之前，根本不可能持续做到。

## 问题：观点散落在互联网各处，没全貌

每个活跃在网上的人，都在不同平台留下了大量观点。

X（原 Twitter）上的帖子、回复、引用转发，Substack 上的长文，GitHub 的 Issue 讨论，播客文字稿，论坛评论，内部文档……

这些内容加在一起，理论非常有价值，但问题是，它根本没法用起来。

原因有三个：

太长，没有人能通读

太杂，玩笑、实验、技术细节、情绪发泄、半成型的想法，和真正经得起推敲的观点混在一起

按时间线排列，而不是按概念组织

你想知道"我到底相信什么"，从这堆东西里找答案，几乎是不可能的事。

Kun 想要的，是一个小文件，能回答一个问题：哪些观点足以代表我？

## 解法：一份每天自动更新的观点地图

他的做法是，用 Hermes Agent 配合 GPT，每天凌晨 3 点自动跑一个 Cron job（定时任务，类似手机上的定时闹钟，到点自动执行）。

会做以下几件事：

读取他在 X 和 Substack 上发布的所有新内容

提取其中有持久性的观点

合并进已有的 OPINIONS.md 文件结构

把更新结果 commit（提交）回 GitHub（代码托管平台，他用来存放个人配置文件）

整个过程不需要他手动参与。

每天早上，文件已经更新好了。

## OPINIONS.md 长什么样

Kun 在文章里直接公开了自己当前的 OPINIONS.md 全文如下：

```
<code># OPINIONS.md

This file is a compact map of Kun Chen's public viewpoints inferred from his public X activity and Substack posts.
It is optimized for readability and conciseness, so it consolidates repeated signals and keeps evidence links sparse.

## AI agents, orchestration, and developer tools

### Agents should be judged by useful work, not demos

Kun judges coding agents by whether they complete valuable work in messy real codebases, not by toy demos or impressive screenshots.
He prefers agents that gather evidence with search, grep, tests, and tools instead of relying on unsupported reasoning.
He accepts slower and more tool-heavy agents when they produce more trustworthy results, because wrong answers and rework cost more than latency.
He sees hallucination as an engineering and incentive problem that can be reduced by training models to admit uncertainty and by surrounding them with verification.
Evidence: x.com/kunchenguid/status/1885867478489976954, x.com/kunchenguid/status/1954225404828631469

### Agentic engineering changes the work rather than eliminating engineering

Kun thinks AI is shifting software work from hand-writing code toward steering, specification, review, orchestration, system design, and product judgment.
He expects engineers to learn agentic engineering while still understanding fundamentals well enough to control and evaluate what agents produce.
He believes AI amplifies competence and judgment, which means weak taste and weak requirements can produce more slop faster.
He expects people who keep learning and building with AI to gain leverage, while people who refuse to explore the ceiling face the highest career risk.
Evidence: x.com/kunchenguid/status/2041414813977542709, x.com/kunchenguid/status/2050720538629460407

### Requirements, tests, and review are the new bottlenecks

Kun believes code has rarely been the deepest bottleneck in software work.
The harder questions are what is worth building, what users actually need, and how to verify that the result works.
He sees tests as central to AI coding because tests encode intent and give agents a feedback loop.
He favors TDD with agents when requirements are clear, because LLMs write better tests from intent than from the implementation they just generated.
He thinks humans should review generated tests especially carefully because bad tests can bless the wrong behavior.
Evidence: x.com/kunchenguid/status/1966949744909136067, x.com/kunchenguid/status/2030858831937561041

### Human accountability must remain explicit

Kun treats AI as a tool, not a teammate or co-author.
Humans remain accountable for AI-assisted changes because they choose the goals, approve the outputs, and own the consequences.
He dislikes agents auto-adding themselves as commit co-authors because it serves vendor branding more than user trust.
He would rather source control record useful AI-assistance metadata such as model, prompt, token usage, session context, and human approval.
Evidence: x.com/kunchenguid/status/2034743250033201335, x.com/kunchenguid/status/2035453569256870288

### Good agent systems need orchestration, isolation, and fresh context

Kun thinks effective agent work requires moving from micromanaging steps to directing agents through goals, principles, measurable objectives, and review loops.
He prefers deterministic harnesses for repeated long-running loops instead of asking one context window to remember everything.
He believes agents should use fresh context windows, isolated worktrees, explicit review phases, and fix phases to reduce context rot.
He sees overnight agents as useful for measurable optimization tasks where progress can be verified and failed attempts can be discarded.
Evidence: x.com/kunchenguid/status/2040275267370041784, x.com/kunchenguid/status/2046413891857797597

### Agent-facing interfaces deserve first-class design

Kun believes tools for agents should be designed as deliberately as human UIs.
Agent interfaces should optimize token efficiency, speed, composability, compact output, reliability, and easy chaining.
He is skeptical that generic MCP surfaces or human-oriented JSON APIs are always the best interface for agents.
He sees purpose-built agent CLIs and AXI-style tools as promising because shells, pipes, and concise commands give agents efficient building blocks.
He worries that broad auto-enabled tool search can save upfront tokens while adding extra turns, search failures, and lower success rates.
Evidence: x.com/kunchenguid/status/2036175602638791047, x.com/kunchenguid/status/2041900381350117648

### CLI agents and IDE agents will coexist

Kun expects CLI coding agents and IDE-based agents to coexist because they serve different workflows.
CLI agents are scriptable, portable, composable, and useful as building blocks for automation.
IDEs provide more opinionated interactive experiences and richer visual context.
He is skeptical that GUI-only computer use is the long-term agent interface because the world can build interfaces for agents instead of forcing agents to mimic humans.
Evidence: x.com/kunchenguid/status/1944075518975857118, x.com/kunchenguid/status/1946087577192399052

### Model choice should follow task shape, not fandom

Kun is pragmatic about models and harnesses.
He sees Claude as pleasant for interactive work, while GPT or Codex can be better for non-interactive background execution, bug finding, and skill invocation.
He thinks Claude Code's popularity reflects model quality, subsidies, and lock-in more than harness quality alone.
He believes higher reasoning effort can reduce total cost on complex tasks when it avoids bad answers, correction turns, and rework.
He is wary of very large context windows and automatic memory when they add stale information, bloated context, or inefficient processes.
Evidence: x.com/kunchenguid/status/2044240037483819220, x.com/kunchenguid/status/2043771618984636593

## AI labs, markets, and openness

### Model labs should act more like infrastructure providers

Kun thinks LLM labs create the most ecosystem value by making frontier models cleaner, cheaper, faster, and more reliable.
He is skeptical when labs use model power, product bundling, or platform control to favor their own downstream apps and block competing harnesses.
He expects many downstream products to be better built by specialized ecosystem players than by model labs themselves.
He sees LLMs potentially becoming commodity infrastructure that fades into the background like power plants, internet providers, or payment rails.
Evidence: x.com/kunchenguid/status/2033999261894119844, x.com/kunchenguid/status/2050990987728798151

### AI product moats require more than a wrapper

Kun is skeptical of AI products whose moat is only a prompt over commodity models.
He thinks durable AI businesses need distribution, workflow ownership, proprietary context, customer trust, operational depth, or a superior ability to build and iterate quickly.
He believes frontier labs can temporarily make subsidy itself a moat, especially when power users receive far more compute value than their subscriptions cost.
He advises AI startups to avoid direct cash-burning competition with frontier labs and instead find narrow, defensible niches.
Evidence: x.com/kunchenguid/status/1771341403068801344, x.com/kunchenguid/status/2031173685646885335

### Open AI requires more than open weights

Kun does not equate open weights with fully open AI.
He thinks true openness also involves training data, training stack, inference stack, hardware assumptions, and reproducibility.
He sees model weights as closer to a compiled binary than source code because the training data and process are the source material compressed into the model.
He worries that centralized LLM distribution lets whoever controls the channel encode and spread a worldview.
Evidence: x.com/kunchenguid/status/1884109795176899041, x.com/kunchenguid/status/1885176573722321147

### AI evaluation needs systematic evidence

Kun distrusts screenshots and one-off anecdotes as proof of model bias, truthfulness, or coding ability.
He prefers canonical evaluation datasets, careful benchmark design, and awareness of contamination and selection bias.
He thinks telemetry from production coding tools can be misleading because users send different task types to different models.
He views harness quality as important but not a permanent moat when open alternatives can catch up.
Evidence: x.com/kunchenguid/status/1764864913573646473, x.com/kunchenguid/status/2035029157445607471

## Software engineering, craft, and process

### Great engineers create valuable outcomes

Kun defines great engineers by their ability to get valuable things built.
That requires technical depth, breadth, strategy, leadership, delivery, communication, and political skill when problems have organizational constraints.
He sees compensation as an imperfect but sometimes useful market signal of created value, not as a pure measure of greatness.
He believes senior individual contributors create leverage through technical direction, ambiguous decisions, stakeholder alignment, process repair, and helping other teams succeed.
Evidence: x.com/kunchenguid/status/1555956306875273216, x.com/kunchenguid/status/2041286279170834668

### Managers and senior engineers must create leverage

Kun believes managers earn trust because employees implicitly trust them with their careers.
Managers create value by recruiting strong people, helping existing people grow, and creating conditions where the team can do better work.
If a team needs neither hiring nor growth support, he questions whether it needs a manager.
He also believes founders and star ICs should not be forced into management or coaching roles when they create more value by playing directly.
Evidence: x.com/kunchenguid/status/1628244112796426240, x.com/kunchenguid/status/1745652997605212233

### Code quality decays without active stewardship

Kun thinks codebases naturally drift toward entropy unless senior engineers actively hold the quality bar.
He prefers review cultures that require authors to explain how changes were tested rather than making reviewers personally rediscover every bug.
He believes solo ownership can burn people out and reduce quality when collaboration, shared context, and contributor growth would be better.
He wants principal engineers to remove processes where small changes require excessive meetings and approvals.
Evidence: x.com/kunchenguid/status/1743484100516970992, x.com/kunchenguid/status/1746381160022953985

### Pull requests will evolve under agentic workflows

Kun expects pull requests to become less central as work shifts from human-written code reviewed by another human to agent-written code steered and reviewed by the human author.
He still sees PRs as useful for CI gates, release automation, metadata, and team coordination.
He does not think humans must read every line of agent-written code if they provide strong requirements, require tests and evidence, and review summaries, risks, and targeted diffs.
He believes CI remains hard to replace because local validation cannot cover every platform and environment.
Evidence: x.com/kunchenguid/status/2046369388673347633, x.com/kunchenguid/status/2046482906567295483

### Tools should make good choices easy

Kun values ergonomics because a sound architecture that is hard to use correctly still produces performance and maintainability problems.
He likes opinionated defaults when they can be centrally optimized, while preserving customization for advanced users.
He prefers terminal-centered workflows with grep, fzf, Neovim-style editing, and low visual clutter, while recognizing configuration can become a time sink.
He values reproducible environments, demos, and personal infrastructure because they turn fragile manual memory into repeatable systems.
He prefers clear ownership boundaries between tools over ideological purity about forcing everything through one layer.
He thinks frameworks and abstractions should earn their complexity by matching the actual problem shape.
He believes terminal and developer tools deserve visual craft, pacing, and polish when those details improve comprehension without stealing attention from the user's real task.
Evidence: x.com/kunchenguid/status/1946656375658160587, kunchenguid.substack.com/p/how-i-built-a-reproducible-mac-setup, kunchenguid.substack.com/p/how-i-built-a-starry-night-in-tui

## Product, startups, and organizations

### Building is easier, so judgment matters more

Kun thinks AI makes building software dramatically easier, which raises the relative importance of knowing what to build.
He wants founders to understand real problems, talk to customers, observe decisions, and seek honest feedback before validating their own idea.
He thinks good ideas start with named people who care about a real problem, not with abstract brainstorming or technology-first excitement.
He favors narrow prototypes, minimal initial scope, and assembling existing building blocks when the goal is to learn quickly.
He frames distribution as finding the people who already have the problem, not merely promoting a product.
He believes product updates often belong inside the product at the right moment rather than in generic announcement channels.
Evidence: x.com/kunchenguid/status/2045369540427890884, kunchenguid.substack.com/p/zero-to-one-handbook-for-entrepreneurial

### Idea quality depends on the builder

Kun thinks a good idea is relative to the builder's context.
The best solo-builder ideas sit at the intersection of problems the builder understands deeply, can solve with their resources, and enjoys enough to keep pursuing.
He prefers exploring multiple ideas before committing when the goal is learning and discovery.
He sees building as something he naturally does for fun and would keep doing even without financial pressure.
He also thinks large companies can give entrepreneurial engineers real zero-to-one experience, with lower financial risk and easier access to users, resources, and cross-functional partners.
Evidence: x.com/kunchenguid/status/2041234698723344451, kunchenguid.substack.com/p/zero-to-one-handbook-for-entrepreneurial

### AI enables smaller serious companies

Kun expects AI to increase individual leverage enough to make one-person and very small-team companies more viable.
He does not think every company should rebuild giant SaaS products internally just because agents can write code.
He expects many SaaS tools to remain useful, but with more interactions mediated by agents rather than direct human UI use.
He thinks future work systems need better shared context, work tracking, memory, cost control, and collaboration models for humans working with many agents.
Evidence: x.com/kunchenguid/status/2041324401166287021, x.com/kunchenguid/status/2041571735322161397

### Enterprise AI adoption needs behavior change

Kun believes many companies overestimate AI maturity because demos and casual agent usage are closer to average adoption than frontier adoption.
True adoption involves background agents, agent-built customer features, agent-run experiments, and redesigned internal review, approval, and go-to-market processes.
He thinks enterprise rollout fails when companies merely provide tools and expect usage to emerge organically.
Adoption requires education, value discovery, planning, workflow redesign, and incentive changes.
Evidence: x.com/kunchenguid/status/2046791114318086351, x.com/kunchenguid/status/2041334084648243256

### Incentives shape product quality

Kun thinks many organizational product-quality problems come from incentives that reward shipping cool things more than conversion, retention, and customer outcomes.
He believes large companies need reward systems that prioritize the main quest over internal side quests, especially when AI makes internal tool rebuilding easier.
He is skeptical of outcome-based pricing when outcomes are hard to define and attribute.
He thinks companies should optimize AI products around users, profit, and team-level customer maturity rather than token consumption alone.
Evidence: x.com/kunchenguid/status/2029243249949540363, x.com/kunchenguid/status/2034552927164244334

## Career, learning, and work

### Curiosity and compounding learning are durable advantages

Kun treats curiosity, motivation, and repeated building as more important than early specialization.
He likes the growth check of asking what a person can do this month that they could not do last month.
He thinks people should build things they find fun because enjoyment sustains effort, learning, and long-term compounding.
He thinks entrepreneurial engineers should deliberately build credibility, communication ability, customer understanding, and trust, not just technical execution skill.
He advises planning careers by identifying the end game and working backward instead of optimizing only for the next job.
Evidence: x.com/kunchenguid/status/2041276542110814628, kunchenguid.substack.com/p/zero-to-one-handbook-for-entrepreneurial

### Education should include agents and real products

Kun believes students should learn CS fundamentals but should not spend most of their time hand-writing code for its own sake.
He would rather they learn agentic engineering, system design, and how to build many real things with users.
He sees LeetCode-style preparation as something to do when target companies require it, not as the center of long-term software skill.
He thinks technical interviews need to be reimagined because current systems, especially LeetCode-heavy ones, do not work very well.
Evidence: x.com/kunchenguid/status/2041250656644964568, x.com/kunchenguid/status/2041298362000154749

### Career moves are context-dependent

Kun left big tech to build because AI timing, personal runway, family readiness, and desire for new experience aligned.
He views the move as not purely financial in expected value terms, but aligned with what he wants to do.
He warns people not to blindly copy major career moves because runway, family context, learning goals, opportunity cost, and personal preference differ.
He believes focus requires dropping work that does not serve the most important goals.
Evidence: x.com/kunchenguid/status/2041226783668994096, x.com/kunchenguid/status/2041299460941381930

### Being effective matters more than being right

Kun thinks people often overvalue being correct when the goal is to be effective.
He sees political and organizational constraints as real parts of engineering work rather than distractions from technical purity.
He prefers promotion conversations that align on a growth path rather than simply asking whether a promotion can happen immediately.
He thinks career success comes from creating value in the system as it exists while improving the system where possible.
Evidence: x.com/kunchenguid/status/1752253952740241888, x.com/kunchenguid/status/1662174745817935872

## Platforms, discourse, and trust

### Social platforms reward shallow signals

Kun believes algorithmic feeds reward hype, clickbait, mass-audience takes, and overbroad claims more easily than nuanced truth.
He thinks deep thinking is hard to distribute when shallow posts travel farther.
He prefers explainers that teach one concept at a time rather than combining multiple concepts for audiences with different background knowledge.
He expects authenticity to matter more as AI-generated content becomes common.
Evidence: x.com/kunchenguid/status/1746748560614539438, x.com/kunchenguid/status/1936848043581870085

### Platforms should compete without suppressing alternatives

Kun does not think platform fees are inherently wrong.
He objects when a platform suppresses competition by disallowing alternatives.
He sees Windows Phone as a cold-start failure in app ecosystems rather than merely a product-quality failure.
He thinks apps have abused push notifications for marketing and wants user-side intelligence to punish irrelevant senders.
Evidence: x.com/kunchenguid/status/1764936209766424674, x.com/kunchenguid/status/2048903872798925247

### Trust requires plain accountability

Kun thinks customer-impacting incidents should be answered with accountability, explanation, prevention steps, and refunds where appropriate.
He dislikes defensive minimization when users were harmed.
He is wary of exposing full agent trajectories that touched private data because they can reveal sensitive context, prompt-injected material, or internal information.
He prefers transparency when companies commercialize or significantly build on open source work.
Evidence: x.com/kunchenguid/status/2047851689697501294, x.com/kunchenguid/status/2001948072759509444

## Society and institutions

### Institutions matter because coordination creates value

Kun sees a company as a group of people creating value together that individuals could not create alone.
He thinks multi-agent systems inherit many human collaboration problems, including bottlenecks, duplicated work, diffusion of responsibility, information loss, and red tape.
He believes organizational topology and communication design can matter more than raw intelligence because smarter participants still fail under poor coordination structures.
He expects layered structures with clear roles and rich cross-tier communication to beat both bottlenecked hubs and chaotic peer meshes in many multi-agent settings.
He prefers turning intuitions about organization design into runnable simulations and comparable evidence instead of relying only on memes or stereotypes.
Evidence: x.com/kunchenguid/status/1751362665690419626, kunchenguid.substack.com/p/org-bench-lets-simulate-the-org-charts</code>
```

文件按主题分成六大板块，每个板块下有若干具体观点，每条观点后面附有来源链接作为佐证。

主题

内容方向

AI Agent、编排与开发工具

如何评价 Agent、工程师角色转变、测试与审查

AI 实验室、市场与开放性

模型厂商定位、产品护城河、开源的真实含义

软件工程、工艺与流程

优秀工程师的定义、代码质量、PR 的未来

产品、创业与组织

什么值得构建、小团队的可行性、企业 AI 落地

职业、学习与工作

好奇心的复利、教育改革、职业决策逻辑

平台、话语与信任

算法对浅层内容的奖励、平台竞争、问责机制

举几条具体的观点作为样本：

关于 AI Agent 的评判标准

Kun 认为，评价一个编程 Agent 好不好，要看它能不能在真实的、混乱的代码库里完成有价值的工作，而不是看演示视频有多好看。

他接受速度慢但工具用得多的 Agent，因为错误答案和返工的代价，比延迟更高。

关于工程师角色转变

AI 正在把软件工作从"手写代码"转向"指导、规格说明、审查、编排、系统设计和产品判断"。

AI 放大的是能力和判断力，这意味着品味差、需求模糊，只会更快地产出更多垃圾。

关于开放权重（open weights）

他不认为开放权重等于完全开放的 AI。

真正的开放还涉及训练数据、训练栈、推理栈、硬件假设和可复现性。

模型权重更接近编译后的二进制文件，而不是源代码，因为训练数据和训练过程才是被压缩进模型的"源材料"。

## 真正的难点：过滤什么，比读什么更重要

Cron job 的 prompt（给 AI 的指令）里，最关键的部分，不是"读我的帖子"，而是"忽略什么"。

对于 X 平台， 要过滤掉：随手的回复、玩笑、情绪化的吐槽、缺乏上下文的模糊表达、作者在引用或转述别人观点时的内容。

对于 Substack，因为他的文章里有大量技术细节，如果不加过滤，OPINIONS.md 就会变成一本操作手册，而不是观点地图。

所以 prompt 里有明确规则：

提取持久性的观点、原则、品味、批判、预测、权衡和反复出现的判断

把技术细节当作观点的佐证，而不是内容本身

忽略代码片段、命令、API 用法、架构说明、调试步骤、一次性技巧

技术文章要在"我对工程、工具、产品的价值判断"层面总结，而不是"怎么实现"层面

如果某条内容只是暗示某个观点，但不能确立持久性信念，不要添加进文件，最多在摘要里标注为"弱信号"

有了这个过滤器，文件才是品味。

没有它，文件只是知识库。

## 最意外的收获：用 AI 审视自己的观点

第一次生成 OPINIONS.md 之后，Kun 问 Agent：这些观点里，有没有客观上说错的地方？

结果，这成了整个过程里最有价值的一次对话。

Agent 没有说"你完全正确"，而是给出了具体的反馈。

以下是三个例子：

观点一："代码很少是最深层的瓶颈"

Agent 的反馈：这在很多产品工程场景下是对的，但不是普遍规律。在基础设施、编译器、分布式系统、机器人、科学计算、复杂遗留系统迁移这些领域，实现难度本身就可能是瓶颈。

建议修改为："在大多数产品软件中，代码通常不是最深层的瓶颈。"

观点二："LLM（大语言模型）可能会像电厂一样变成基础设施"

Agent 的反馈：这是一个有用的战略警示，但不是客观事实。品牌、分发渠道、生态锁定、安全政策、数据优势、产品捆绑，这些都是反向力量，可能阻止 LLM 真正商品化。

建议：保留这个类比，但标注为"预期"，而不是"事实"。

观点三："开放权重更像编译后的二进制，而不是源代码"

Agent 的反馈：类比不错，但不够精确。

权重可以被检查、微调、合并、量化、蒸馏，这些都是二进制文件做不到的。

更强的说法是："仅开放权重，不足以实现可复现性或完整的开源等价性。"这个版本更难被反驳。

除了"哪里说错了"，还可以问更多问题：

这些观点里，哪些是真正可证伪的？

哪些其实是大众共识，只是被包装成了个人品味？

哪些已经过时了？

哪些说得太绝对？

哪些互相矛盾？

用这种方式了解自己，有一种奇特的乐趣。

## 文件结构本身也应该进化

一个值得注意的设计细节：OPINIONS.md 的章节结构不是静态的。

每次更新之后，Cron job 会额外问一个问题：当前的结构，还是组织这些观点最好的方式吗？如果不是，就重新组织。

这个文件不应该无限追加，它应该定期整理，变得更好。

## 加了个"看门狗"：两类自动警报

第一版跑起来之后，Kun 意识到可以给这个系统加"警报"机制，他把它叫做 watchdog（看门狗）。

第一类警报：观点漂移检测

如果今天写的东西，和 OPINIONS.md 里的某个观点产生了张力或矛盾，就触发提示。

重要的是，Agent 要区分三种不同的情况：

文件过时了，现实已变

这条帖子只是特定语境下的表达，不代表观点真的改变

真的改变了想法

这三种情况处理方式完全不同，Agent 不应该自动合并，而是把判断权留给人。

第二类警报：事实风险检测

扫描 OPINIONS.md 里的事实性支撑、市场判断、因果主张、预测、时效性声明，用网络检索验证高风险的部分。

纯粹价值判断和主观意见不在扫描范围内，只有那些"可能因为世界变了而变错"的内容才会被标记。

噪音控制：

为了避免同一条警报反复出现，系统用一个 JSON 文件记录已经报告过的警报，基于警报类型、涉及的观点和来源 URL 生成稳定的哈希值（一种用于唯一标识内容的数字指纹）去重。

除非有新的证据实质性地改变了警报内容，否则不重复提示。

## 为什么 Agent 也需要这个文件

很多 Agent 工作失败，是因为 Agent 不理解你在乎什么。

Kun 在自己的 AGENTS.md（给 AI 助手的工作说明文件）里加了这样一段：

> 当你在做某件事，如果了解 Kun 的观点会有帮助，请读取 ~/OPINIONS.md，理解他相信什么。

这让 Agent 在执行任务时，能更好地和他的品味与判断对齐，而不是给出一个通用的、没有立场的答案。

## 为什么以前做不到

维护这样一个文件，如果靠人工来做，几乎不可能坚持。

读取所有来源、过滤噪音、提取持久性观点、合并进已有结构、检测矛盾、验证事实风险，每天做一遍，这是一个量级巨大的任务。

正是因为有了 Agent，这件事才第一次变得可行。

这也是 Kun 在文章标题里说"这是没有 Agent 就不可能实现的事"的原因。

## 局限性和值得注意的地方

这套方案并不是没有问题，有几点值得说清楚：

平台依赖： 目前的实现依赖 X 和 Substack 的公开内容可被抓取。如果平台收紧 API 权限或反爬策略，数据获取可能中断。

AI 提取的准确性： Agent 在判断"这条帖子是持久观点还是情绪化表达"时，并不总是准确的。过滤规则写得越细，效果越好，但边界情况仍然存在。

自我认知的局限： OPINIONS.md 反映的是你公开发布的内容，而不是你真正相信的全部。有些想法从未被写出来，有些想法在公开表达时已经被修饰过了。

工具门槛： 目前的实现需要用到 Hermes Agent、GitHub、Cron job，对非技术背景的人来说，上手成本不低。Kun 在文章末尾提供了一段完整的 prompt，可以直接发给 Hermes Agent 来自动完成搭建。

Prompt如下

```
<code>Set up a daily Hermes cron job that maintains an OPINIONS.md file from my public writing and public activity.

Goal:
Create or update a repo-backed OPINIONS.md that captures my durable beliefs, changed views, recurring opinions, and meaningful refinements based on public sources I choose.

Before starting:
Collaborate with me to decide the input sources.

Ask me for any missing information, including:

1. Which public sources to use
   Examples: blog, newsletter, X/Twitter, Bluesky, Mastodon, LinkedIn, GitHub issues or comments, podcast transcripts, YouTube transcripts, RSS feeds, public talks, essays, or any other public archive.

2. How to access each source
   Examples: RSS feed URL, public profile URL, API access, export file, sitemap, transcript source, or local archive path.

3. The target repo URL.

4. Where to put the OPINIONS.md file inside that repo.

Setup requirements:

1. Clone or use the target repo locally under:
   ~/.hermes/workspaces/<repo-name>

2. Create source-specific helper scripts under:
   ~/.hermes/scripts/

   These scripts should fetch or ingest recent public items from the chosen sources.

3. Store durable sync state under:
   ~/.hermes/state/

   The job should only process new items since the last successful run.

4. Maintain the cron prompt as a source file at:
   ~/.hermes/scripts/opinions_cron_prompt.md

Cron job behavior:

1. Run daily at 3am.

2. Update OPINIONS.md with:
   - durable beliefs
   - changed views
   - recurring opinions
   - meaningful refinements to existing opinions

3. Ignore:
   - jokes
   - dunks
   - one-off reactions
   - weak or ambiguous signals
   - context-specific comments that should not become durable beliefs
   - content where the author is quoting, summarizing, or steelmanning someone else rather than expressing their own view

4. Preserve uncertainty.
   If a source item suggests a possible view but does not establish a durable opinion, do not add it as a belief.
   At most, mention it in the run summary as a weak signal.

5. Commit and push changes to the repo only when OPINIONS.md changed.

6. Deliver the run summary back to this chat.

OPINIONS.md watchdog:

Add a watchdog that always runs, even when there are no new source items.

The watchdog should do two things:

1. Opinion drift detection

   Compare new source items against existing and proposed OPINIONS.md.

   Flag only real tension, contradiction, or meaningful refinement of durable opinions.

   Prefer calling something a “refinement” instead of a “contradiction” unless the old and new views cannot both be true.

2. Factual-risk detection

   Scan OPINIONS.md for:
   - factual scaffolding
   - market, model, or product comparisons
   - causal claims
   - predictions
   - time-sensitive claims
   - claims that may become stale as the world changes

   Use targeted web checks for high-risk claims.

   Do not flag pure value judgments or subjective opinions.

Watchdog noise control:

1. Deduplicate watchdog warnings using:
   ~/.hermes/state/opinions-watchdog.json

2. Use a stable hash based on:
   - warning type
   - OPINIONS.md claim or section
   - source item or evidence URL

3. Do not repeat warnings already reported unless new evidence materially changes the warning.

4. Never block OPINIONS.md updates solely because watchdog warnings exist.

Cron configuration:

Create or update a Hermes cron job with:

- schedule: 0 3 * * *
- delivery: origin
- workdir: the local repo path under ~/.hermes/workspaces/
- enabled toolsets:
  - terminal
  - file
  - skills
  - code_execution
  - delegation
  - web
- relevant skills, if available, for the selected sources and git workflow

Verification:

After creating or updating the job, verify:

1. The cron job exists and is enabled.
2. The schedule is 0 3 * * *.
3. The workdir points to the local repo.
4. The web toolset is enabled.
5. The cron prompt was persisted correctly.
6. The watchdog state path is present:
   ~/.hermes/state/opinions-watchdog.json
7. The prompt requires the watchdog to run even when there are no new source items.
8. The prompt contains the final-response contract below.

Final cron output contract:

Every run summary must include:

1. Sources checked.
2. Number of new source items processed.
3. Whether OPINIONS.md changed.
4. Whether changes were committed and pushed.
5. Counts for:
   - drift warnings
   - factual-risk warnings
   - deduped or skipped repeat warnings

If warnings exist, include each warning with:

- type
- confidence
- claim or section
- source item or evidence URL checked
- suggested human action

If no warnings exist, say exactly:

No opinion drift or factual-risk warnings found.</code>
```

## 这件事的意义

OPINIONS.md 的核心，是一种对自己更诚实的方式。

我说了什么客观上错误的东西吗？

我是否暗示了一些自己并不真正相信的东西？

我的观点在悄悄改变吗？

有一个 Agent 帮你持续追踪这些问题，然后用一个可读的文件呈现出来，这件事的价值，比听起来要大得多。

原文标题： Everyone Should Have an OPINIONS.md

原文链接： kunchenguid.substack.com

作者： Kun Chen，前 Meta/Microsoft/Atlassian L8 工程师，现独立构建者

## 继续阅读

基于全文检索与主题相似度

AI教程

2026年5月1日

### GPT-5.5 提示词指南：OpenAI 在悄悄改写规则

OpenAI 最近更新了 GPT-5.5 的官方提示词指南。 读完之后有一种感觉，这份文档本身就是在告诉你，之前那套写提示词的方法，可以扔掉一大半了。 https://developers.openai.com/api/docs/guides/prompt-guidance?model=gpt-5.5 先说背景：GPT

AI教程

2026年4月29日

### 如何让 Claude 拥有完美记忆

原文链接： How to Give Claude Perfect Memory (complete guide) 说实话，Claude 默认的记忆功能基本没什么用。 它经常忘记上下文，你得不停重复解释，即使解释了，它还是记不住。 大多数人已经忍受这些问题好几个月了，却不知道其实有更好的办法。 我每天都在用 Claude

AI教程

2026年4月25日

### LLM 基准测试完全指南：哪些分数真的有用？（2026年2月版）

最近大模型扎堆发布，如昨天DeepSeek V4发布，OpenAI GPT5.5发布，还有最近的Opus 4.7、Kimi2.6等等。 每次大模型发布，大家都会都会附上一串基准测试分数，MMLU、GPQA、HumanEval、HLE……数字一个比一个高，图表一张比一张好看。 但我一直有个疑问，这些榜单代表了什么意思？到

© 2026

·

向阳乔木