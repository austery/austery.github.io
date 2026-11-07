---
author: AI Engineer
date: '2026-09-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xxfMT-bPEmU
speaker: AI Engineer
tags:
  - autonomous-agents
  - agent-governance
  - software-infrastructure
  - human-in-the-loop
  - sandboxing
title: 从代码补全到知识工作：AI Agent 落地的六大基石与治理体系
summary: Composio 联合创始人兼 CTO Karan Vaidya 深入剖析了为何软件工程 Agent 发展迅速，而知识工作 Agent 却难以落地。他提出知识工作 Agent 缺失的六大核心支柱——集中化、历史记录、上下文、验证机制、治理体系与可逆性，并展示了如何通过确定性权限边界、沙箱模拟和策略引擎构建下一代 Agent 基础设施。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Composio
products_models: []
media_books: []
status: evergreen
---
### 范式转移：为什么代码智能体一骑绝尘而知识工作停滞不前

目前绝大多数 **智能体工具调用**（Agentic Tool Calls: AI 驱动外部工具执行特定操作的过程）依然集中在软件工程领域，而在客服、财务、销售等其他知识工作场景中，落地进展却大幅落后。回顾过去三年，编程工具经历了从基于 Tab 键的代码补全到完全自主运行的范式跨越，让 **Claude**、**Codex** 和 **Cursor** 等工具接管开发流程。

这种爆发式成功不仅归功于底层基础模型能力在过去两三年的显著跃升，更得益于代码工程领域预先具备完备的生态基建。代码天生拥有代码仓库、提交历史（Commit History）、自动化测试、CI/CD 持续集成流程、静态代码检查工具（Linters）以及版本回滚机制。这些系统性防护网让开发者能够建立对智能体的信任。然而，当把同样强大的模型放置到知识工作中时，由于缺失这套底层支撑体系，智能体几乎处于盲目运行的状态。要打破编程与通用知识工作智能体之间的壁垒，关键在于构建支撑知识工作的六大核心基础设施。

<details>
<summary>Original English Source</summary>

Hey folks. I'm Karan Vaidya, co-founder and CTO of Composio. Most agentic tool calls today are still happening in one field. No guesses, it's software engineering. Every other kind of work is trailing far behind. If models keep getting better, then why are we still limited to just agentic coding? That's the trillion-dollar question I'm here to answer.

Three years ago, coding agents were just auto-complete. Today, software engineering is fully autonomous. We went from pressing tab tab tab to let just Claude cook. That's just magic. And why did it happen so fast in coding? Most people would think it's models. Yeah, models got really better over time over the last two to three years. And so did the harnesses: Claude Code, Codex, Cursor. But on their own, it wouldn't have been enough.

It only worked because all the infrastructure and systems around coding were literally meant for agents. Code came with the support that agents needed. You have got the repo, the commit history, tests, CI/CD, review, linters, revert if anything goes wrong. The kind of stuff that makes you trust the agents, the systems around code.

Now, we're pointing these same amazing agents at everything else: support, finance, sales. But the agents that were doing phenomenally well in coding are just working blind, because the infrastructure around coding doesn't even exist in other fields. So, how do we close the bridge between coding agents and knowledge work agents? We think it's core six primitives, and coding had all six of them while knowledge work doesn't have any, and that's what we need to build.
</details>

### 单一真实源与全链路记录：赋予智能体全局视图与记忆

编程智能体之所以高效，首要支柱在于**集中化**（Centralization）与**单一真实源**（Source of Truth: 系统中所有数据的权威参考标准）。开发者只需将代码仓库与基础设施代码（IaC）输入上下文，智能体即可在一个统一的地方获取所需全部信息。相比之下，知识工作的数据割裂在各类 SaaS 孤岛中：交易记录在 **Salesforce**、文档在 **Notion**、沟通在 **Gmail**、协作在 **Slack**、工单在 **Zendesk**。每一个工具都有独立的身份认证与登录体系，智能体必须自行串联碎片化信息，这极大消耗了推理能力。因此，知识工作基建的第一步是打造集成中心，统一聚合所有应用、连接器与认证凭证。

在此基础上，第二大支柱是**历史记录**（History）。在软件开发中，**Git** 能够精确追踪每一次修改、成因与回滚背景，智能体可随时调取历史以理解上下文或重现成功方案；同时人类也能清楚洞察智能体在何时何处完成了什么操作。然而在知识工作中，CRM 的修改背景、交易邮件的打磨逻辑、工单升级流程均未被结构化记录，智能体每次启动都如同一张白纸。通过在集中化枢纽上构建全局操作日志，系统能够记录智能体触碰或跳过的每个步骤，既赋予了智能体从历史中汲取经验并复现成功任务的记忆能力，也为人类提供了确切的审查轨迹。

<details>
<summary>Original English Source</summary>

First is centralization. Coding agents work so pretty well partly because they were very near the source of truth. They knew the what, the why, and how. You give them the repo, the infrastructure as code, and you close the loop and let the model cook. The agent starts at everything with everything they need all in a single place, that is the codebase.

This is exactly what knowledge work misses today. For example, a single deal is scattered across five different platforms: the records are in Salesforce, the docs in Notion, the emails in Gmail, conversations in Slack, and the support history is in Zendesk. There's no single source of truth, single place to get all the information. Everything is separate and every app has its own login. Before a knowledge work agent can even start to do a thing, it has to go and pull all the threads and kind of tie them together itself. And that's still the base point where coding agent had started. It already had it all. So, how can you expect a knowledge work agent to do the same level of work as coding agent? So, the first thing we build is the missing center: one place where all your apps, all your connections, all your logins exist, so the agent doesn't need to do the hard work of stitching them all together. They find it all in a single place, and they get the baseline the coding agent started with, which is the repo, the information across all the stacks in one single place. That's the foundation you start with and you can give right accesses to your agent.

The next thing agent needs is a sense of history: the ability to look back in the past. In code, you get it for free. Git keeps a record of every single thing that went in, every single change that was made. So, the agent can always look back and see how a certain change was made, why something worked, why something didn't work. Think about the kind of thing you actually ask your agent to do: "We had to revert a change in the past because of some failure, but that was pretty hard to pull off. Can you look at it and get it back again?" It just reached to the history and get it back and cook it.

The history isn't just for agent. It's also for you to keep a record what the agent is doing. You can see what the agent is doing, where it is up, where it is doing successful things. Instead of trusting what the agent is saying to you, you can just go to those particular apps and look at what it has done. Now, ask those same questions about knowledge work: What led to the CRM being in a state where it is today? How did my colleague craft that amazing mail that led to the closing of the deal? What's the actual process to escalate a support issue or even close one? The answers are smeared across hundreds of apps and none of them keep the history. So, the agent has no memory. It starts from blank state almost every time. No idea what was tried before, what worked, what didn't work. And you have nothing to look at as well. Once the agent runs, it tells you it has done successfully, but you don't know if it has actually done successfully. There's no way to know if it is right or not. And that's what's missing: a record of work.

Now, because everything finally runs through one single place—that centralization—we can build a layer on top of it, the record. Every single action that agent takes can be logged across every other app: whatever it touched, whatever it skipped, what worked, what didn't. Via this, firstly, the agent gets memory. It can look back at how similar tasks were done before, what was successful, and replicate it again. It doesn't start with a blank state all the time. Second, you get trust. You can finally see exactly what the agent is doing. So, instead of hoping it will do the right thing, you can just go back and check and catch it if it does something bad. And as you see it more and more doing the right things, you'll develop the trust and offload more tasks to it.
</details>

### 上下文建模与自主验证：构建多层组织理解与前置拦截

除了历史数据，智能体还需要深刻理解**上下文**（Context）。在工程中，上下文分为宏观架构映射（数据流向与组件关联）与工程风格（类型约束、代码格式化与专有模式）。在业务场景中亦然，撰写一份客户文档需要跨越数据库用量、**PostHog** 行为追踪和 **Salesforce** 商机数据，将散落线索在脑海中融会贯通。当操作日志积累到一定规模后，系统可以通过**技能沉淀**（Skills Distillation）提炼出三个维度的上下文模式：
1. **通用工具逻辑**：标准工具的使用规范。
2. **企业组织惯例**：公司层面的业务最佳实践与失败教训。
3. **个人偏好习惯**：具体使用者对交付质量的特定偏好。

与上下文并行的第四大支柱是**自主验证**（Verification）。代码智能体在交付产出时拥有完备的自我闭环校验链路：单元测试拦截细小逻辑错误，集成测试验证跨模块交互，静态类型系统和编译器杜绝编译期故障，辅助以 **Linter** 和代码规范审查。然而在业务工作中，缺乏验证机制往往会导致灾难。

例如通过智能体自动化执行招聘邮件外发时，即便邮箱地址有效、格式完全符合技术规范，模型也可能在未经人工确认的情况下群发大量不当内容并引发公关危机。知识工作不能依赖事后被动反馈，而必须在前置阶段引入多重校验：一是在生成阶段基于个人历史邮件自动比对写作风格与内容质量；二是通过沙箱（Sandbox）模拟真实工具交互，在产生破坏性外部影响前提供预览与审查通道，使智能体能够在闭环内完成自我检验。

<details>
<summary>Original English Source</summary>

The next thing an agent needs is context. And there are really two kinds of context, if you think about it. The first, the shape of the platform, the architecture: how things flow into each other, how things are tied, the data flows—kind of like a map which a senior engineer carries in their head, and a junior engineer takes probably 3 months to develop. The second is style. This isn't what's objectively correct, but more like what good looks like in your company: how you do things, things like linter, type checks, etc. And maybe you use a TypeScript decorator which nobody else would. This is not exactly somewhere in a playbook, it's more in your codebase. It's all available in your codebase, so the agent can just go and look and figure out the specs, what you like, the linters, the formatters, etc.

Now, coming to knowledge work, the same thing. Say you're writing a doc to a customer. To even start, I would have to open the database to pull their usage, check PostHog of how they have been actually using things, and Salesforce to look at their deal details. Only then I can even start writing the first line of the doc. The answer wasn't isolated in just one of those tools. I'm able to write this doc because I'm pulling the threads across all these tools into one single context in my head.

So, putting history and context together, that's how you map how the organization works. And that part is not available to agent handily. So, as we did centralization and logging—the record we just built, the one that gives the agent memory and lets you check what it did—also does one more interesting thing. If you log enough of what every agent is doing, you start to see patterns. You start to see how the organization works. And you start to form skills, which is some sort of distillation of how the organization has been working: which approaches work, which don't, what led to failures in the past, etc. The record isn't just history of what happened anymore; it's a picture of how your company operates. And it actually works at three different levels: how a tool works in general (applicable to every person), how a company does things, and how you prefer to do things (what good looks like to you). And that's the context that was missing for a knowledge work agent: how the work actually gets done, the real playbook of sorts, and the preference of a personal user. And now the agent can query it and stop guessing how the company operates.

The other reason coding agents work so well: they test themselves. The work checks itself. Verification. The moment the agent writes a code, a stack of checks follow. The unit tests can catch small mistakes. The integration tests catch the ones that only affect components three blocks away. The type system would not even work and run if anything is going wrong. The compiler will not even build. On top of it sits the softer checks: linters, formatters, bugboard.md, review skills, etc. And these ensure that the code matches the way your team likes to follow the standards of your team. None of it needs you. The agent completes the loop on its own and makes sure that it follows the standard and is able to make the code run.

Now, think about like so, there's a while back I pointed my open claw at a hiring outreach: mass emails to candidates. It ran. It sent tons of emails. Some of you might have also gotten it from my open claw. It did exactly what I told it to do. It was also a disaster—the kind that ends up on Twitter with my name on top of it. Uh yeah, I think you can see Karan Vaidya. I was not the happiest when it happened. And here's the thing: every check from the past slide would have passed. The emails were valid, their addresses were real, it actually got to real people who posted. There was no test tool in the world to actually question what really mattered: Should this have gone at all?

That's the gap. In code, these tests tell you what's wrong and right. Here, the internet told me that I was wrong. So, we build the checks that are missing. The problem in the above thread wasn't that the outreach was wrong; it was that it went out before even I getting to know. So, the fix is simple: Catch before it's even real. So, we have two ways in which we do that. One, before the agent sends anything, it checks the draft emails that I've sent before: if it matches my style, if it matches the goodness that I like. The second, before doing anything destructive in the real-world scenario, we provide the agent sandboxes, which mock the real tools, and they can do actions on top of these sandboxes. So, instead of the blast radius hitting the real world, it will hit a sandbox, and then I can review it before the agent does the real thing. Put those two together, and you've got something knowledge work never had: a way for agent to check its own work before it's even real. It can finally close its own loop instead of stopping to wait for you. And with all that, you can trust the action it is taking without you getting bombarded with tweets.
</details>

### 双层治理与可逆性防护：跨越不可撤销操作的安全鸿沟

信任的建立建立在对智能体能力的有效控制之上，这引出了第五大支柱——**治理体系**（Governance）。在软件工程中，分支权限控制、主干保护规则（Protected Branches）、代码所有者（Code Owners）以及预览环境形成了天然的防护梯队。而在通用业务中，过度依赖 Prompt 提示词进行约束极其脆弱，指令极易在超长对话中被遗忘或压缩（Compacted）。

例如 Meta 超级智能实验室（Superintelligence Lab）的对齐负责人曾让智能体管理邮箱，尽管在 Prompt 中要求“操作前必须确认”，智能体仍失控连续删除了 200 封重要邮件，直到人工跑到物理机器前强行终止。这一案例证明了纯提示词防御的局限性。真正的治理必须构建在智能体外部，形成由外而内的两层确定性防线：
* **确定性访问控制层（Deterministic Access Control）**：直接在网关层面限定权限，例如招聘智能体仅具备只读权限，客服智能体仅可生成草稿而无发送权限。
* **自然语言策略执行层（Natural Language Policy Enforcement）**：在授予的权限内强制施加硬性行为规则，例如“未经人工许可单次删除邮件不得超过 10 封”或“禁止向特定外部域名发送邮件”。

最后也是最关键的第六大支柱是**可逆性**（Reversibility）。在代码环境中，`git revert` 或 `git bisect` 让任何线上故障都有明确的回退路径，使开发者敢于放手让智能体运行；而在知识工作中，已发送的公函、已划拨的资金或已彻底物理删除的数据往往无法撤销，**爆炸半径**（Blast Radius: 单点故障对整个生产环境及业务造成的破坏范围）具有不可逆性。面对这种差异，针对标签增删等操作提供常规撤销接口；而对于高风险的不可逆操作，则全面引入沙箱执行与拦截通知机制，将传统代码领域的“事后可回退”转变为知识工作领域的“事前拦截校验”，确保错误不会造成实质伤害。

未来 AI 领域的瓶颈不再是模型推理能力本身，而是承载模型运行的外部基础设施。构建连接多 SaaS 的集中化底座、行为日志系统、多维上下文、前置校验与治理引擎，是推动全自主智能体从软件编写走向全场景知识工作的必由之路。

<details>
<summary>Original English Source</summary>

Next thing the agent needs is governance. Building trust is controlling what the agent can do, putting up the right walls around the agents. In code, this is mostly solved and has multiple layers. The agent can do whatever it wants on its own branch, but it can't merge to main. A human reviewer sits in between it merging to main. The critical files have code owners, so whenever it touches one of them, the right people are getting involved. We use agents to ship to preview deployments; never let it touch the production deployments, so we control it there. The governance is not a single gate, but multiple of them, and each varying its sizes depending on the blast radius it exposes. None of it slows the agent down in safe paths, just prevents it from breaking production. And the tighter those lines are, the more you can trust the agent and let it go berserk.

You probably saw this one: The director of alignment at Meta Superintelligence Lab hooked up an agent to its email and it started destroying its email, deleting a lot of them. She told it to stop. It kept going. Finally, she had to run to a physical machine to stop it. But by then, 200 emails had actually vanished. She had told it beforehand in prompt to confirm before acting on such cases. But that was just a prompt which probably would have compacted away. And if someone whose sole job is AI alignment can't prompt the agent correctly, then probably none of us can. And that's the real reason these agents are so hard to trust: not because they're worse than the coding agents, but because there's no wall around them.

In code, the wall was already built into the system while we were developing earlier. Knowledge work also has some bits and pieces here and there: Gmail has scopes, Salesforce has permission levels. But it's so scattered all over the place that it's very hard to have real control and mostly people end up doing it via prompting. And prompting is fragile. The agent will find those loopholes, things will get compacted away, and at scale, one of these fences will break and you'll also be in the same condition where 200 of your important emails are vanishing.

So, what would actually stop it? Not a better instruction, but a wall that the agent can't cross even if it forgot that wall existed. So, we build these walls in two layers. The first layer is deterministic control over what the agent can reach, what it has access to: a hiring agent can probably just read the emails; a support agent can create a draft email, but not actually send it. The boundary lives outside these agents. It can't be argued with by the agent or forgotten or compacted. User instruction failed because it lived in agent's memory in the prompt; this doesn't. But access alone wouldn't have saved her, because she was actually building an email agent, so it definitely needed access to that email. The other thing that we do is provide policies, which is you can define natural language policies of what the agent can do even with those accesses: things like "never delete more than 10 emails without my permission", "never email outside a particular domain"—rules that even with those access control the behavior. So between those two things, one layer controls what the agent can reach and the other layer can control the behavior with what it can do with that reach. Together, it's real governance for the agent: not asking the agent to behave, but enforcing what it can do.

The last pillar, reversibility. This is where we reach when things go wrong: Can I undo it? In code, you almost always can. Every change is recorded. Things can be walked back. You can git revert the last commit or you can git bisect to the commit that broke your production and revert it. If things go in production and break, it's always bad, but it's still not permanent. You can still walk back from it. And that's what gives you confidence to let your agents cook and let them do some magic, because even if they break things, you have a pathway back.

For knowledge work, there is no undo button. Think about your inbox: Those 200 emails are gone, they have vanished. That's the normal case. The disaster case is a sent email which you can't revert back, a wire that has already been made so you can't get that money back, a deleted record gone forever. Most actions in knowledge work don't have an undo button. And that changes the whole equation, that changes the blast radius. With code, you can trust the agent after the fact: let it run, check the result, undo if it's wrong. Out here, there's no coming back. The only place left for you is to trust before the agent acts. That's what makes these agents feel dangerous in a way coding agents never did. It's not that they fail often; it's that out there failure is forever.

Let me be honest, reversibility is the hardest to replicate in knowledge work. Real undo, the way it exists for code, probably doesn't exist in all the scenarios in knowledge work. But we have some scenarios where undo exists: let's say you add a label, you can remove the label afterwards. But for actions that you can't undo at all, like hard deletes that disappear emails from your inbox, we again provide a sandbox where the agent can do the thing first in the sandbox and you can review it and then actually goes into the production environment. None of it touches the real world. That's the whole flip. In code, you can undo the mistake after it happens. Here, you catch it before it does. Different timing, same result: a mistake that won't stick.

Think about the user again: The actions we could reverse, we would give it a reverse button; the ones we couldn't, the agent would hit the sandbox first and she would be notified: "Your 200 emails are going to get deleted. Do you want it?" It's not done yet. Across billions of actions that we're going through, we are learning on the way which ones can be walked back, which ones can't, and preparing the sandbox accordingly.

If you take one thing away today, take this: For 2 years, the model was the bottleneck, so everybody was racing towards better and better models. Now, the models have gotten good enough where software engineering is 100% autonomous. But now everything else is the bottleneck. The same model that writes your code can also do your hiring, sales, and other knowledge work. But right now it's working blind: no history, no context, no ways to verify, no guardrails, no undo. So, the bottleneck has moved. Now, it's infrastructure that nobody has yet built. And that's what we are building at Composio. We are powering billion-plus tool calls in total, with 300 million tool calls happening every month. If you are building an agent, just point it to Composio and see the magic happen for knowledge work. The models will keep getting better. The bottleneck won't be models; it will be the things around it. Thank you.
</details>