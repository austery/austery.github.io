---
author: Best Partners TV
date: '2026-03-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qua6FfJmydo
speaker: Best Partners TV
tags:
  - agent-harness
  - harness-engineering
  - long-term-tasks
  - ai-engineering
  - system-centric-ai
title: Agent Harness 与 Harness Engineering：AI长时任务的驾驭之道
summary: 本次内容深入探讨了AI领域的新革命——Agent Harness与Harness Engineering。文章指出，当前AI模型在长时复杂任务中的可靠性是巨大挑战，静态排行榜无法反映模型漂移问题。Agent Harness被类比为计算机的操作系统，是管理AI Agent长时运行的基础设施，而Harness Engineering是实现这一基础设施落地的工程实践。内容详细阐述了Agent Harness的定义、价值、发展阶段、趋势，并结合OpenAI的实践，提出了上下文工程、架构约束、垃圾回收等核心组件，强调了AI开发正从模型论转向系统论，标志着AI工程化新时代的开启。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - 菲尔·施密德
  - 比尔吉塔·伯克尔
  - 米切尔·桥本
companies_orgs:
  - OpenAI
  - LangChain
products_models:
  - Claude Code
  - Codex Agent
media_books: []
status: evergreen
---
大家好，这里是最佳拍档。

2026年的AI领域正经历一场静悄悄的革命，焦点正转向一个全新的赛道：如何让AI模型在真实世界的长时复杂任务中稳定、可靠、高效地运行。过去几年，我们过度关注AI模型的“智商”和排行榜上的数值提升，却忽略了一个关键问题：一个能在单轮测试中解出难题的模型，在执行数百次工具调用、持续几天的工作流时，可能会在第五十步就出错。这种被称为**模型漂移**（Model Drift: 模型在执行长时任务时出现错误或能力下降的现象）的现象，正成为AI落地的最大障碍。解决这个问题的核心答案，可能就在于**Agent Harness**和**Harness Engineering**。

### Agent Harness：AI的长时运行操作系统
“Harness”一词本意是给马套上的工具，中文可译为“驾驭”或“管控”。**Agent Harness**（Agent Harness: 包裹在AI模型外围，用于管理长时运行任务的软件基础设施）并非Agent本身或单纯的开发框架，而是负责规范、引导、管控Agent运行全生命周期的系统，核心目标是保证Agent在长时任务中始终保持可靠、高效、可调控的状态。

这个概念可以用经典的计算机架构来类比：AI模型如同计算机的CPU，提供原始处理能力；模型的上下文窗口则像RAM，是有限的工作内存；而**Agent Harness**，便是计算机的**操作系统**（Operating System: 管理和调度算力资源、优化内存使用、提供标准驱动和运行环境），它管理算力、优化内存、提供运行环境，让上层AI Agent（作为具体应用）能在稳定基础上运行。Agent Harness为AI Agent提供了标准化、稳定化的运行环境，使开发者能专注于业务逻辑设计，而非重复构建基础能力。

相较于传统的**Agent Framework**（Agent Framework: 提供构建Agent的基础积木，如工具接口、推理循环模板），Agent Harness更像一个成品系统，整合了预设能力和最佳实践，如提示预设、工具调用的确定性处理、生命周期钩子、规划、文件系统访问、子Agent管理等。例如，构建编程Agent时，开发者无需自行编写文件读写、代码编辑、终端执行的整合逻辑，因为Harness已提供标准化工具调用流程。

### 发展阶段与趋势
目前，通用型Agent Harness依然稀缺，但垂直领域的专用型Harness开始萌芽。**Claude Code**是通用型Agent Harness的典型代表，它依托Claude Agent SDK，集成了生产级工具，能管控Agent的行为边界。**LangChain DeepAgents**也是通用型Harness的重要探索，增加了长时任务状态管理、异常重试等能力。而各种编码CLI工具，本质上是为编程Agent打造的专用型Harness。行业趋势是通用型Harness的标准化和垂直型Harness的精细化。

Agent Harness的必要性凸显，是因为传统基准测试与真实世界需求的错位。它通过三个维度搭建了基准测试与用户体验之间的桥梁：
1.  **验证真实世界的技术进步**：将新模型接入实际用例，快速测试其真实工作流表现。
2.  **赋能用户体验**：通过整合成熟工具和最佳实践，构建体验一致、性能稳定的Agent。
3.  **通过真实反馈实现持续优化**：将工作流转化为结构化运行数据，进行记录、评分、分析，形成正向循环。

Agent Harness让AI系统的优化从经验驱动转向数据驱动，这是AI工程化的核心标志。

### 理论支撑：《苦涩的教训》与轻量化原则
在Agent Harness开发中，**Rich Sutton**提出的**“苦涩的教训”**（The Bitter Lesson: 通用计算方法的技术最终总会击败那些依赖手工编码人类知识的技术）理论尤为重要。该理论指出，通用计算方法最终会胜过依赖人类知识的手工编码技术。

Manus、LangChain和Vercel团队的案例均表明：
*   移除Harness中的刚性假设和手工设定，以适应模型快速发展。
*   避免过度设计的控制流，适配模型能力提升。
*   精简手工工具，实现更少的执行步骤、更低的token消耗和更快的响应。

结论是，Agent Harness开发必须坚持**轻量化原则**，绝不能过度工程化，要放弃用人类知识定义Agent行为的思维，转而打造灵活、可迭代、无刚性约束的基础设施。开发者应**“为删除而建”**，保持架构的高度模块化，以应对新模型带来的结构设计方式变革。

### Harness Engineering：AI基础设施的落地实践
**Harness Engineering**（Harness Engineering: 让Agent Harness落地的核心工程实践）是让Agent Harness落地的核心工程实践。OpenAI在2026年发布的内部实验报告提供了一个参考案例：以**Codex Agent**为基础，团队仅用5个月（5-7名工程师）就打造出百万行代码的实际产品，且应用逻辑、基础设施、工具链、文档全部由Codex Agent生成，人工仅参与高层架构决策。

OpenAI构建的管控框架融合了确定性方法和大语言模型方法，形成了三层核心组件：
1.  **上下文工程**（Context Engineering: 升级的上下文工程，构建知识库并提供动态上下文访问）：提供Agent对动态上下文（如可观测性数据、终端结果）的访问能力，解决“Agent知道什么”的问题。
2.  **架构约束**（Architectural Constraints: 为Agent划定行为边界，避免失控）：通过自定义代码检查器和结构测试（如**ArchUnit**，**Testcontainers**），强制Agent生成的代码遵循特定架构模式，违规立即终止并要求重新生成。
3.  **垃圾回收**（Garbage Collection: 对抗系统的熵增和衰退）：利用监控Agent定期扫描代码库和文档，找出不一致性，并自动完成修复，确保系统高质量、高一致性。

OpenAI的实践还提出了一个迭代理念：将Agent的失败视为信号，反馈到代码仓库并让Codex自己编写修复代码，形成**自驱进化体系**。然而，该实践在功能和行为验证方面存在明显缺口，未来Harness Engineering需弥补此方向。

### 未来发展与核心思考
基于OpenAI实践，**Billigta Berkner**提出了四个核心思考：
1.  **Harness成为新一代服务模板**：针对常见应用拓扑，整合代码检查器、结构测试、知识库等，但需解决分叉与同步问题。
2.  **更高的AI自主化可能以约束运行时为代价**：**LangChain**编码Agent通过优化运行环境，排名大幅跃升，证明约束运行时能释放模型潜力。
3.  **AI推动技术栈和应用拓扑向有限数量收敛**：AI友好性和Agent Harness支撑将成核心选择标准，代码库结构将趋向易于AI维护。
4.  **AI应用维护将出现“前AI时代”与“后AI时代”**：旧代码库改造成本高，新应用需从设计之初融入Harness Engineering理念，形成双轨制企业软件体系。

### Harness Engineering落地实践建议
Harness Engineering并非一蹴而就，需从小处着手，逐步搭建。
*   **反思管控体系**：检查**预提交钩子**（pre-commit hook: 用于代码格式检查、架构约束验证）等现有流程，考虑开发自定义代码检查器和结构测试框架。
*   **明确工具建设**：Harness Engineering远不止规则文件，需构建大量工具（代码检查器、测试脚本、上下文接口），清晰的代码结构本身也是重要的上下文。
*   **聚焦“设计环境、反馈环和控制系统”**：AI发展已从模型智能转向完善的运行体系，Harness Engineering是实现严谨性的关键。

### AI认知的三次升级与系统化思维
从2023年的提示词工程，到2025年的上下文工程，再到2026年的Harness Engineering，AI行业的认知完成了三次升级：
1.  **提示词工程**：关注AI“说什么”，解决单轮指令。
2.  **上下文工程**：关注AI“知道什么”，解决多步骤任务上下文。
3.  **Harness Engineering**：关注AI“在什么环境里做事”，解决长时任务运行管控。

这标志着AI开发从**面向模型的思维**（Model-Centric）转向**面向系统的思维**（System-Centric），是AI走向真实世界的核心标志。

### 总结与未来展望
Harness术语精准描述了约束和引导AI Agent的核心内涵，但需警惕其被滥用。未来AI发展的瓶颈将从模型推理能力转变为**上下文的耐久性**（Context Durability: 模型在长时任务中能否始终保持对上下文的理解和指令的遵循）。Agent Harness将是模型训练的核心反馈工具，捕捉模型漂移点，优化长时推理能力。

开发者需完成三个核心思维转变：
1.  **从简开始**：放弃手工控制流，提供健壮的原子工具，让模型自主规划，开发者侧重工具定义、边界、验证。
2.  **为删除而建**：保持Harness架构高度模块化，便于快速移除替换，跟上模型发展速度。
3.  **将Harness视为数据集**：竞争优势将转移到Harness捕捉的运行轨迹数据上，用于优化模型和Harness本身。

2026年的AI革命，革的是“唯模型论”的命，开启AI工程化的新时代。未来的竞争不再是模型智能的比拼，而是整个管控体系的工程化能力较量。开发者需完成从模型调优师到系统工程师的思维转变，关注AI的运行环境、管控体系、反馈环设计。人工智能正从实验室走向价值创造，这是2026年AI发展最珍贵的变化。

好了，以上就是今天关于Agent Harness和Harness Engineering的全部内容了。希望能对大家带来一些帮助。感谢收看本期视频，我们下期再见。