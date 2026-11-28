---
author: AI Engineer
date: '2026-04-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=h403btjldDQ
speaker: AI Engineer
tags:
  - ai-orchestration
  - multi-agent-system
  - autonomous-agents
  - open-source-software
title: Paperclip 入门指南：构建“零人力公司”的人类控制平面
summary: Paperclip 创始人 Doda 详细介绍了这一开源智能体编排器。Paperclip 并非简单的自动化工具，而是为 AI 劳动力设计的“人类控制平面”，允许用户通过组织架构管理多模型智能体。文章涵盖了从环境搭建、跨模型协作到复杂任务（如视频自动生成）的实战案例，并揭示了 QA 审核与自动化例程等核心工作流，旨在帮助人类通过掌控 AI 劳动力来实现业务的规模化扩张。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Doda
companies_orgs:
  - Paperclip
  - OpenAI
  - Anthropic
  - GitHub
products_models:
  - Paperclip
  - Claude
  - Remotion
  - OpenRouter
  - Gemini
media_books: []
status: evergreen
---
### 重新定义 AI 劳动力：Paperclip 的核心理念与定位

**Paperclip**（智能体编排器：Open-source agent orchestrator）不仅仅是一个自动生成业务的工具，它的核心定位是 **人类控制平面**（Human Control Plane: 人类对 AI 劳动力进行管理、决策和干预的操作层）。其愿景是构建 **零人力公司**（Zero-human company: 核心业务流程完全由 AI 自动化运行的企业模型），通过建立一个清晰的 **组织架构图**（Org Chart），将人类的品味、偏好和问责机制嵌入到 AI 工作流中。与那些宣称一键创建业务的工具不同，Paperclip 强调人类在更高维度设计与执行过程中的深度参与。

用户可以通过简单的命令行工具 `npx paperclip-ai onboard` 快速启动。在 Paperclip 的逻辑中，你不再是单纯的开发者，而是这家“公司”的决策者。你可以雇佣不同职能的智能体、设定目标并自动化岗位。这种架构将碎片化的 AI 任务聚合成了具有系统性逻辑的“劳动力集群”。

<details>
<summary>Original English Source</summary>

Welcome to getting started with Paperclip and I'm Doda, your host and the creator of Paperclip and I'm so excited to show you how to get started with this brand new open-source agent orchestrator. I'm going to walk you through your first steps of how to get Paperclip started, what it looks like when you have a huge organization, and some of my best advanced tips for working with AI agents and so you can create your own uh zero-human company.

Now, the tagline that we have for Paperclip is that it's for open-source orchestration for zero-human companies. Um, you can hire employees, set goals, automate jobs, your business can nearly run itself. Well, you know, maybe that's a bit of a headline. I would say that Paperclip is the human control plane for AI labor. Really, the idea behind Paperclip is that you're able to set up an org chart of agents where you can manage them all and um invoke your taste in what these agents how they work and have them complete real work.

The first thing that you do is you should just open up your terminal and run NPX Paperclip AI onboard. You can pass dash dash yes if you want the default options, but let me talk about like what is Paperclip. Paperclip is a um a a way you can accomplish real work that you are accountable for using AI agents. You maybe have seen tools um where they have you create a task and then it automatically creates a business for you. With Paperclip, um you actually are involved in the steps to have your preferences accounted for and um and you are involved in the task process from the higher-level design all the way to actually executing.

</details>

### 跨模型组织架构：自带智能体（BYOA）模式

在 Paperclip 的生态系统中，最核心的原则之一是 **自带智能体**（Bring Your Own Agent: 允许用户接入任何实验室的 AI 模型作为员工）。这意味着你可以根据任务需求，灵活调用 **Claude**、**Gemini**、**Pi** 或通过 **OpenRouter**（模型路由服务：连接数百种大模型的统一接口）接入 **Hermes** 等各类模型。Paperclip 提供了一个供应商中立的“线束”（Harness），让不同性格的模型能够在同一套内存和通信协议下协作。

以管理 Paperclip 项目自身为例，组织内可以设有 **CEO** 统筹全局，下设 **CTO** 管理多个 **编码专家**（Coders）。Doda 指出，他在实际操作中经常混合使用 **Codex** 和 **Claude**。通过这种方式，智能体可以互相协商、沟通，并将其长期记忆统一存储在系统中。这种“多模型混编”的能力，确保了组织在处理高智力服务时使用顶级模型，而在处理常规任务时则可以切换到更具成本效益的开源模型。

<details>
<summary>Original English Source</summary>

So, this is the company that I use to manage Paperclip itself. You've got here the CEO who's the man in charge. We've got a CTO and under him he has quite a lot of coders. Um, I would say that the two coders that I use the most would be the Codex coder as well as the Claude coder.

And an important thing about Paperclip is that you bring your own agent. So, you can use Gemini, you can use Pi, you can use Hermes, you can use Open Claw. A key part of Paperclip is that any agent that you want to use can be brought into Paperclip as an employee and then it can sort of negotiate and communicate and have its memory stored with the rest of Paperclip.

</details>

### 从指令到交付：基于“技能”的自动化执行实战

Paperclip 的强大之处在于其 **智能体表面**（Agentic Surface）和内置的 **技能管理器**（Skills Manager）。CEO 智能体不仅能拆解任务，还知道如何安装新技能。例如，在庆祝 GitHub 40,000 星标的案例中，CEO 智能体会自动雇佣一名 **视频写手**（Video Writer），并通过 `skills.sh` 寻找并安装 **Remotion**（基于 React 的视频生成工具：通过编程方式制作专业视频）的最佳实践技能。

整个流程高度自动化：CEO 接收指令 -> 拆解任务并分配给执行层 -> 调取 **品牌指南**（Branding Guide） -> 接入数据面板获取实时统计 -> 生成视频草案。Doda 强调，传统模式下可能需要一周的视频制作工作，在 Paperclip 这种具备全量上下文信息的系统中，变成了“随手一记”的琐事。更重要的是，系统会记录所有的反馈（如“镜头切换需要 2 秒而非 6 秒”），并将这些偏好转化为组织特有的 **特定技能**（Paperclip-specific skill），实现组织经验的沉淀与进化。

<details>
<summary>Original English Source</summary>

I created a new issue. And I assigned it to my CEO. The idea behind Paperclip is that you are the CEO and you are basically giving your CEO instructions and then your CEO is designed to break down the tasks to your executive branch and then down to the individual contributors. So, one of the things that I did is I asked the CEO, "Please hire a video writer and have them write a Remotion video celebrating 40,000 stars."

Every piece of the Paperclip app has an agentic surface. So, your CEO knows how to hire new agents. They know how to install new skills. There is a skills manager built into Paperclip. So, for example, I'm sure you've seen skills.sh. From there, um we would install the Remotion best practices skill. The CEO hired our video writer agent and gave her the Remotion best practices skill.

I was able to create a prompt to say, "Plan this video for the stats dashboard." I wrote this prompt and then the agent wrote this plan. Paperclip has first-class support for plans. And then after I read the plan briefly, I gave it some feedback. Within about 5 minutes we had this beautiful animation that is on brand.

With Paperclip, all of those things are built into the system. We already have a Paperclip branding guide, which the agents already know about. Something that might have taken me a week actually becomes an afterthought with Paperclip. We actually can go over the list of feedback that we've given our agents and learn how to make the skill better where we have not only a generic Remotion skill, but also a Paperclip specific skill that has our branding guides, our preferences, our style like pacing choices.

</details>

### 提升可靠性：QA 审核制与自动化例程

为了解决 AI 智能体“不听使唤”或“无法闭环”的通病，Paperclip 引入了多层级的工作流保障。**QA 智能体** 配备了 **智能体浏览器技能**（Agent Browser Skill: 允许智能体像人类一样操作网页、填写表单），专门负责验证执行层提交的成果。系统强制区分了 **审阅者**（Reviewer）和 **批准者**（Approver）的角色：QA 负责在代码提交前进行回归测试，而经理（Manager）则负责最终确认工作是否符合品牌调性。

此外，Paperclip 提供了 **自动化例程**（Routines），允许用户设定定时任务或带变量的手动任务。例如，每天定时汇总 **Twitter 书签** 提取策略报告、自动生成 Discord 更新日志、或利用 **Greptile**（代码分析工具：辅助进行首轮社区代码审查）进行初审。这种设计让 Paperclip 跨越了“编码工具”的范畴，成为了覆盖市场、销售、财务运营的通用组织管理平台。

<details>
<summary>Original English Source</summary>

Paperclip provides um a variety of kind of workflows that are important to the orchestrator in order to um actually uh complete the work successfully. So, for example, one of the main things that you will often see in a good Paperclip organization would be QA. Um the QA agent has the agent browser skill, which is a skill that lets you trigger tasks like open a website, fill out a form, click a button.

Paperclip gives you this kind of vendor-neutral harness where you can create these higher-level workflows where you can say when the assignee is finished with this task, you must have the QA agent boot and give a review on it. You also can have um an approver, right? So these are two sort of different roles because um QA might review it and then you iterate between the coder and the reviewer. And but the manager might be the one who kind of approves it.

One of the things that I use paperclip for a lot is um I I use um Twitter bookmarks to be able to track ideas. Within the routines uh section, what you're able to do is is set up things like write the release change log. For the open-source project, we use greptile in order to do code reviews. Paperclip is not a code review tool. Paperclip is designed for creating uh businesses. Um you can use paperclip to um to to run your marketing, to help deal with uh sales leads, to uh deal with finance operations.

</details>

### 未来路线图：Maximizer 模式与多用户云端协作

展望未来，Paperclip 正在从初期的单机版演进为成熟的云端平台。正在开发的核心功能包括 **Maximizer 模式**（Paperclip Maximizer: 智能体在算力预算允许下，不计代价推进任务的极限模式）、**多用户协作**（Multi-user support）以及 **云端沙箱**（Sandboxing: 在隔离的安全环境中运行智能体）。此外，针对每个智能体的 **预算管理**（Budget control）也将更加精细，允许用户设定单月或单项目的 Token 支出上限。

Doda 最后总结道，面对 AI 的冲击，人类不应担心被替代，而应学会掌控这股庞大的劳动力。Paperclip 的目标是让即使是非技术人员，也能通过引导、调试和提供上下文，指挥成千上万个智能体来构建和运营自己的事业。

<details>
<summary>Original English Source</summary>

We're adding uh features like the CEO chat. We're adding maximizer mode, which is when you've got uh a dream and tokens to burn, and you want the agents to work as hard as they can um to do whatever it takes to create your uh business, and you want them to keep going without stopping. That would be the Paperclip maximizer.

Another piece you'll notice is missing is that there's not multiple human users. That is a huge gap. We are working on this feature really this week um because you should be able to deploy it to a cloud and have your entire team work on Paperclip. We're also working on cloud and sandboxing agents, so that you'll be able to uh run agents in E2B or dev.exe or cloud agent deployments.

Paperclip is a free product that will give you the power as a human to to to have control over AI labor. Do not worry about AI taking your job. When you use a something like Paperclip, you will be in charge of thousands of agents um helping you build your business, helping you with your company.

</details>