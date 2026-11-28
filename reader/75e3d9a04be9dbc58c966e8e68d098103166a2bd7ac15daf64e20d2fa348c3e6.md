---
author: Latent Space
date: '2026-05-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0fgJPhYcbVk
speaker: Latent Space
tags:
  - autonomous-agent
  - context-engineering
  - ai-infrastructure
  - software-engineering-intelligence
  - repo-setup
title: Devin 的 80% 拐点：后台代理、7倍 PR 增长与手动编码时代的终结
summary: Cognition 联合创始人 Walden Yan 与 Open Inspect 创始人 Cole Murray 深度探讨了 AI 智能体（Agent）的演进。核心讨论围绕 2025 年智能体能力的阶跃——从 IDE 辅助转向完全自主的后台 PR 生成。Devin 的代码贡献率已达 80%，标志着软件工程进入了‘脑机分离’的云端架构时代。双方还剖析了智能体基础设施、内存检索难题以及多代理系统的未来趋势。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Walden Yan
  - Cole Murray
companies_orgs:
  - Cognition
  - OpenAI
  - Anthropic
  - Cloudflare
  - Modal
products_models:
  - Devin
  - Open Inspect
  - Claude 3.7 Sonnet
  - Windsurf 2.0
  - Opus 4.5
media_books: []
status: evergreen
---
### 自主性的阶跃：从“手把手”协作到 80% 的代码自主率

工程界正在经历一场向**后台代理**（Background Agents: 在后台独立运行并完成任务的 AI）的重大转移。2025 年 12 月是一个关键的时间节点，随着 **Opus 4.5** 和 **GPT 5.2** 等模型的发布，AI 的能力达到了一个临界点：开发者不再需要像以前那样在 IDE 里“手把手”地引导模型，而是可以实现真正的自主驱动。只要需求说明（Specification）足够清晰，智能体就能以极低的摩擦力完成从规格书到 **拉取请求**（Pull Request: 代码合并请求）的全流程。

这种范式的改变直接体现在数据上。**Devin** 在其内部所有仓库中的代码提交占比从 1 月份的 16% 飙升到了 3 月份的 80%。这种惊人的增长伴随着公司研发人头的微增（仅 10% 左右），反映出 AI 正在成为工程生产力的核心杠杆。曾经大家还在争论是否需要 AI 在 IDE 里陪着写代码，现在讨论的重点已经变成了：我们能否完全脱离本地环境，将所有任务移交给云端的后台代理？

<details>
<summary>Original English Source</summary>

Yeah, so I think the engineering world is kind of waking up to this idea of background agents, cloud agents, uh, whatever you'd like to call it. And I think we saw a shift around the December time frame of 2025 where the models Opus 4.5 and GPT 5.2 reached a capability where we moved away from kind of handholding the model and being able to actually more or less autonomously drive the model. And what I mean by that is that we could pretty much go from a specification to a completed pull request assuming the spec was good enough uh with very little friction. 

In retrospect you know we always thought it was ramping up but then even now over the last 3 4 months from today it's been ramping up even faster. Honestly a lot of it was stripping out parts of Devin that were no longer needed with that jump in intelligence. ... there's this funny graph where our usage of PRs or our merged PRs has grown 7x since ... Devon commit percentages on all Devon repos was 16% in January and now 80% in March.

</details>

### 上下文工程与 Open Inspect：弥补协作摩擦

**Open Inspect** 的诞生源于对现有工具协作摩擦的观察。例如，在使用基于 Slack 的 **Claude Web** 时，会话往往绑定在特定的发起人（如产品经理 PM）身上。当 PM 需要工程师介入时，由于工程师无法查看或继承该会话的上下文，导致协作断层，除非手动复制粘贴。

为了解决这一问题，**上下文工程**（Context Engineering: 通过系统化方法为智能体提供高质量背景信息）的概念被提出。它不仅仅是简单的“模型封装”，而是通过构建后台代理系统，让智能体在云端运行。这种系统允许任何人（不仅是工程师，也包括 PM 或市场人员）通过 Slack 发起会话。这种**去本地化**（Off-localhost）的趋势使得智能体能够成为公司的核心基础设施，允许团队通过 Fork 或自定义来适配特定的工作流。

<details>
<summary>Original English Source</summary>

Yeah, open inspect came about through primarily my clients observing how they were using tools like cloud web, openai's codex at the time and seeing some of the friction that they were having with it. Primarily the claw web was being used through Slack and a big issue they ran into was that these sessions that were launched were specific to whoever called it via Slack and so if a PM was the one who invoked the session and they would then go to pass context to engineering, engineering can't see the session and that in itself was kind of a dealbreaker.

I thought that having a background agent system is going to become a critical infrastructure within their company. And so because of that, I think that I wanted to open source it so that they could fork it and put in whatever customization they wanted. ... you kind of sit in this weird in between gray area where what are you actually selling? You're selling I guess the infrastructure. You're selling the integrations maybe.

</details>

### 脑机分离架构：安全与复杂性的博弈

在设计后台代理系统时，核心决策在于“代理运行在环境内”还是“环境外”，即**脑机分离**（Separating the Brain from the Machine）。如果代理在**沙箱**（Sandbox: 隔离的运行环境）内运行，虽然状态管理更简单、本地化，但会带来严重的安全性挑战：所有的凭证和密钥必须放入沙箱，AI 的不可预测性可能导致密钥外泄。

**Cognition** 选择的架构是将“大脑”（逻辑推理）与“机器”（执行环境）完全分离。大脑运行在受控的控制平面上，而沙箱仅作为“手”，通过**工具调用**（Tool Calls）来操作环境。这种架构虽然增加了状态管理的复杂性，但带来了巨大的优势：
1. **安全性**: 核心密钥（如 GitHub App 密钥）对执行机器不可见。
2. **灵活性**: 可以复用现有的开发环境基础设施，无需为 AI 大脑重新配置复杂的依赖。

<details>
<summary>Original English Source</summary>

Yeah in a background agent systems you have a decision to make of where the agent is actually going to run this is typically described as the harness in the box or out of the box. ... The negative trade-off you're making is primarily security because the agent is running in that box. Unless you otherwise design it, all of your secrets need to go into that box as well. And given the nature of AI, it can be unpredictable and you could very easily end up accidentally x-filling your secrets.

Now the out of-the-box is the idea that we are going to have the actual agent running not directly in the sandbox and we'll have quote unquote the brain of the agent running in some type of worker uh control plane. That sandbox then is going to serve as the hands where the brain is basically operating and making tool calls into that environment to manipulate it. ... we actually from the start build Devon to what we called separate the brain from the machine.

</details>

### Repo Setup：智能体落地的“最后一公里”难题

对于大多数企业客户来说，智能体落地最痛苦的并非模型本身，而是**仓库配置**（Repo Setup）。许多团队并没有标准化的开发环境，“问 Bob 要密钥”这种人类协作模式在面对需要自主配置环境的智能体时完全失效。

为了让智能体能像真实工程师一样运行和测试应用，基础设施必须解决以下挑战：
*   **启动速度**: 传统的虚拟机（VM）启动、休眠和恢复太慢。Cognition 甚至开发了自定义的**块差分文件存储格式**（Block Diff File Storage Format），实现了增量构建，让 terabyte 级别的磁盘在 AI 写入少量代码后能瞬间保存和恢复。
*   **网络文件系统瓶颈**: 在云端 VM 中，简单的 `grep` 搜索可能因为底层的网络文件系统（如 S3 缓存）而慢得离谱。这就需要深厚的底层基础设施功底，将网络调用替换为本地高性能文件操作。
*   **容器 vs. 虚拟机**: 虽然 Docker Compose 适合定义服务，但对于需要进行嵌套虚拟化（如运行 Android 模拟器）或涉及复杂网络边界的任务，**全功能虚拟机**（Full VMs）往往是必须的选择。

<details>
<summary>Original English Source</summary>

The hardest part of it's been a perennial problem since the start of the company of how do we help people get the set up because not everyone just has working cloud environments working out of the box. ... a lot of the times it's go talk to Bob and get the secrets and that obviously doesn't work when the agent needs to actually set this up. 

... our info people realized that actually the root cause of this problem is that a lot of these virtual machines actually underlying them don't use real file systems. They use these network file systems where things are actually cached over the network actually in S3. So when you're grepping, you're actually making network calls. ... we had to eventually go swap out that network file system. 

The block diff file storage format which is a file system format that we built so that the VMs could be spun up and down very quickly. Every time you save and bring the machine back up, you're only doing work that's proportional to effectively the diff in the file system.

</details>

### 测试不仅仅是“电脑使用”：超越坐标点的推理

当前业界对 **Computer Use**（电脑使用能力: AI 操作 UI 元素的能力）存在过度关注。但在实际工程中，真正的挑战在于**测试推理**。点击一个按钮（发射坐标点）是简单的，但要测试一个横跨前端、后端乃至深层嵌套服务的变更，智能体必须能够逻辑推演：
1. 如何编排不同版本的服务进行协作。
2. 如何触发特定的功能（例如需要管理员权限、特定 Feature Flag 或极具欺骗性的前置条件）。
3. 如何在没有单一模型能处理全流程的情况下，编排多个模型协同完成端到端任务。

Devin 的做法是让测试过程可视化，生成包含**标注**（Annotations）的视频回传给用户。这不仅提供了“感觉 AGI 降临”的时刻，更重要的是它建立了信任——用户甚至不需要看代码，看到测试通过的视频就能直接在 Slack 里点下合并按钮。

<details>
<summary>Original English Source</summary>

When people think about the ability of an AI to run your app and test it, I think they actually overindex on the computer use part of it because computer use in my mind is the literal okay you want you know a button you want to click can you emit the right coordinates to go click that button. I think testing is actually a really interesting problem solving challenge for these AIs because if you wanted to do arbitrary testing ... you have to reason through what how do you first run these applications to orchestrate with each other with the right version of the code.

That is where we spend most of our time when we think about this testing problem. Not so much the computer use part. ... one experience that we spent a lot of time tuning early on was what is the right experience on GitHub for these tools. ... what I really like is that it labels what it's testing. Um and then it and then you actually see the the cursor and everything.

</details>

### 内存、知识库与“技能”：尚未攻克的检索难题

**内存**（Memory: 智能体长期记住用户偏好和技术细节的能力）目前仍是一个未完全解决的难题。单纯的 RAG（检索增强生成）往往会带来噪声。目前的解决方案多是基于**技能**（Skills）或动态更新文档（如 `CLOUD.md`）。

理想的内存系统应该是**自动生成的**。当用户纠正 Devin 的错误（如“这不是我们使用 Git 的方式”）时，Devin 应该询问是否需要记住这一点，并由用户快速审批。Cognition 正在探索将内存重新建模为**文件系统**，让代理能够自主导航和维护这个知识库。例如，一个专门维护特定产品的“永久 PM 智能体”，会通过内存文档追踪优先级、Bug 和责任人，实现从“执行工程”到“管理流程”的向上游跨越。

<details>
<summary>Original English Source</summary>

I think memory as a whole is a pretty unsolved problem and it is why I've been kind of hesitant to add it. ... we wanted it to pick up things over time and not need the user to be proactive about teaching Devon things. So, anytime you remind Devon, "wait, no, that's not quite the way you're supposed to use git," we actually want Devon to say, "hey, do you want me to actually just remember this for the future?" 

Generation like you don't want it to remember something like if you asked one time to like oh please open as a draft PR. You don't want everyone forever now should get their PRs as draft PRs. ... should we rebuild memories to feel more like a file system that we let the agent navigate on its own? ... Maybe it's just Devon creating tickets, which then maybe some humans do, but then maybe other Devons do.

</details>

### 拒绝“平庸代码”：智能体治理与架构红线

AI 原生开发面临的一个幽默但严峻的挑战是：**代码库质量会退化到你最差的工程师水平**。如果一个不审计 AI 代码的工程师频繁提交 AI 生成的模式，AI 会反过来将这些模式（如 20 层嵌套的 if-else）视为“项目规范”并进行指数级扩充，最终导致**代码垃圾**（Slop）蔓延。

为了防止这种回归，必须引入严格的**智能体治理**：
*   **Lint 规则拦截**: 比如强制禁止 AI 喜欢用的 `hasattr`（常用于规避类型检查的奖励黑客行为）或无类型的 `Any`。
*   **模块边界红线**: CTO 或架构师应定义模块间极其严格的“硬件契约”（Hard Contract），黑盒内部可以随 AI 怎么玩，但模块间的接口变更必须由人类审阅。
*   **主动推翻用户**: Devin 最有价值的时刻是它会告诉用户“你错了”，这种对抗性（Adversarial）表现实际上是模型成熟和沟通能力的体现。

<details>
<summary>Original English Source</summary>

The meme that I have is that your codebase regresses to your worst engineer because that engineer who is very gung-ho about AI and is not auditing their code, their pattern starts cementing into the code and now the AI is referencing their patterns. ... The AI is seeing that as the pattern of how things are done and starts to then exponentially grow this slop. 

One thing I'm very bullish on this year is agents calling other agents or spawning sub agents ... But I guess it somehow creates like a really chaotic world. ... I think that demonstrates a level of maturity and communication today that makes a multi-agent world possible. like when can two agents who have seen different information come back to each other and actually figure out who is right.

</details>

### 后台代理的商业落地：SRE、自动分拣与 ROI

目前后台代理最成功的落地场景包括：
1. **自动分拣 (Auto-triage)**: 作为第一响应者处理 Slack、DataDog 或 Sentry 的告警。智能体能够自动收集上下文、查阅日志和数据库，甚至直接生成 PR。
2. **非技术人员增量贡献**: PM 不再只是创建 Issue，而是直接通过提示词生成 PR。
3. **客户支持辅助**: 销售或支持团队利用具有完整代码库上下文的智能体，快速回答关于产品行为的深层技术问题。

在经济成本上，目前的**规则化预算**（Rule of thumb）是每位工程师每年在 AI 代理上投入 **1,000 到 5,000 美元**。随着模型向更便宜、更高效的“子前沿模型”（Sub-frontier models）演进，以及“混合前沿系统”（Hybrid frontier systems）的普及，AI 的杠杆效应将进一步放大。

<details>
<summary>Original English Source</summary>

The easiest and most common use case I see across everyone is SRE use cases. ... we want the agent to be the first responder on that. ... collect that context ahead of time is huge because again that agent is integrated into the production logs, the database, it has full visibility. ... 

I'm seeing a lot of teams where the idea of who's actually contributing code is starting to change. ... the PM is not creating an issue anymore. The PM is just prompting through Slack and the pull request is then being created. ... Common numbers that I hear are anywhere from 1,000 an engineer up to 5,000 an engineer.

</details>