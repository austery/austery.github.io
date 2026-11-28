---
layout: post.njk
source: https://yage.ai/share/creative-ai-automation-survey-20260428.html
speaker: yage.ai
title: |-
  创意工具的 Agent 化：从 Photoshop Action 到 Claude for
  Creative Work
date: '2026-04-28'
summary: 文章分析了 AI Agent 在创意工具演进的三代历程，从脚本集成到闭环感知。Anthropic 的 Claude for Creative Work 代表了最新一代产品，解决了执行摩擦。瓶颈在于 AI 的视觉感知和评估能力，而非智力。未来 AI 将自动化非创意任务，人类角色更侧重创意方向与审美判断。
area: tech-engineering
category: ai-application
tags:
  - agentic-workflow
  - creative-ai
  - llm-integration
  - ai-tooling
people:
  - Siddharth Ahuja
companies_orgs:
  - Anthropic
  - Blender
  - OpenAI
products_models:
  - Claude for Creative Work
  - Claude Design
  - MCP
  - BlenderMCP
  - 3D-Agent
  - CLI-Anything
media_books: []
draft: true
status: evergreen
---

2026-04-28

## 今天发生了什么

2026 年 4 月 28 日，Anthropic 发布了名为 Claude for Creative Work
的一组产品，包含 9
个创意工具 Connector，让 Claude 可以直接操控 Adobe Creative
Cloud、Blender、Autodesk Fusion、SketchUp、Ableton
等专业创意软件。用户在 Claude 界面里用自然语言下达指令，Claude 通过
Connector 调用这些软件的后端 API 执行操作。

以 Blender 为例。Blender
开发团队自己构建了一个官方 MCP connector，基于 Blender 的 Python
API，让 Claude 可以查询场景数据和对象信息、创建和修改 3D
对象、批量应用变更、运行自定义 Python 脚本、往 Blender
界面里添加新工具。据
The Verge 报道，Anthropic 同时加入了 Blender Development Fund 作为
Corporate Patron，每年出资至少 24 万欧元支持后续开发。

具体使用体验是这样的。Hacker News
上的一个 demo
展示了用户输入”创建一个小村庄，五个小屋围着篝火，左边有一条河，河上放一座木桥，周围散落一些树”，Claude
生成多对象场景并正确处理空间关系。它能理解”桥要架在河上面”这种空间约束，能设置日落光照和环绕摄像机动画，也能响应迭代修改（“把小屋换成石头房子”）。所有几何体在用户本机的
Blender 中生成，只有轻量级场景描述信息发送到 Claude 云端。

这件事不是孤立的。11 天前（4 月 17 日），Anthropic 刚发布了 Claude
Design，一个面向非设计师的 AI 设计工作空间，发布当天 Figma
股价下跌约 7%。Claude Design
面向不会设计的人（从文字到视觉产出），今天的 Connector
面向已经精通工具的专业人士（在已有工作流中嵌入 AI
辅助）。两个产品合在一起是 Anthropic 对创意领域的一次全面布局。

但这不是 Anthropic 的独创。创意工具 agent
化这条路径社区已经走了两年以上，Anthropic
做的是把分散的社区尝试整合成产品化体验，并用品牌和合作关系把它推到了更大的受众面前。

## 三代演进

### 第一代：LLM
加持已有脚本接口（2023-2024）

创意软件在 AI 时代之前就有成熟的可编程接口。Blender 从 2009 年（2.5
版本）开始暴露完整的 Python API（bpy 模块），Photoshop 有 Action 和
JSX/UXP，Maya 有 MEL/Python，Houdini 有 VEX，After Effects 有
ExtendScript。这些接口原本服务于 Technical Director 和 Pipeline
TD，需要同时精通创意工具和编程，门槛很高，高到 Springer 在 2025
年初出了一本 486
页的书专门教这件事。

GPT-4 和 Claude 发布之后，这些已有的脚本接口突然获得了新入口：让 LLM
来写脚本。门槛从”会写 Python 且会用
bpy”降到”会描述想要什么”。最早的形态是手动粘贴（ChatGPT 生成脚本，复制到
Blender 运行），也可以利用 Blender 自带的命令行参数直接执行脚本而不进
GUI。后来有人做了 Blender 内嵌的 AI 助手插件（如 Blender
AI
Assistant），在界面里直接对话和执行。两年前我自己也做过类似的事，用
Cursor 调用 Blender 的 Python API 生成 3D demo 视频。

这一代证明了 LLM 可以有效地将自然语言翻译成创意软件 API
调用。但它有一个根本性限制：LLM
只负责代码生成，不负责验证。脚本也许能跑（不报错），但渲染结果可能完全不对。Atomic
Object 的一位开发者实测发现：AI
处理几何操作时可以工作，涉及材质、光照等需要视觉判断的任务时结果不可预测。

这正是我们在分析
Agentic AI 落地困境时提出的核心问题：AI
的自我迭代循环是断裂的。程序能跑不等于结果正确。AI
看不见渲染出来的画面，没法判断好坏，也就没法自我修正。

### 第二代：连接协议层（2025-2026
初）

第一代的瓶颈不是 LLM
的代码生成能力，而是通信方式太原始（生成脚本、人工粘贴、运行、人工查看、再把结果告诉
LLM）。第二代通过标准化协议让 LLM 直接与软件双向通信，消除人工中转。

标志性事件有几个。Anthropic 发布 MCP（Model Context
Protocol），定义了 AI 调用外部工具的标准接口。2025 年初 Siddharth Ahuja
发布社区版 BlenderMCP（目前
v1.5.5），通过 socket 让 Claude 与 Blender 直接双向通信。3D-Agent
在此基础上引入多 agent 架构：一个模型做高层推理，另一个翻译成 bpy
代码，成功率显著提高。

稍后在 2026 年初，香港大学 HKUDS 团队发布 CLI-Anything，自动分析
GUI 软件源码，用 7 阶段流水线生成 agent-native 的 CLI
接口，已覆盖几十个应用。我们之前对它的调研提到了一个关键洞察叫”The
Rendering Gap”：agent
修改了项目文件，但渲染走简化路径时可能看不到修改效果。Agent
以为操作成功，实际什么都没发生。

这一代解决了连接问题。Agent 能直接发命令了。但 feedback loop
没有被修复，agent 仍然看不到操作产生的视觉效果。

这一代的协议层本身也在剧烈变化中。MCP
从科研导向设计出发在工程现实中反复碰壁，OpenAI 用 _meta
域绕过 context
window，飞书和钉钉在 2026 年 3 月选择发
CLI 而非 MCP 作为 Agent 接入首选。协议层竞争远未收敛。

### 第三代：闭环 Agent（2026-）

第三代的核心特征是闭合 feedback loop：agent
不只能操作软件，还能感知操作结果并据此自我修正。

这不是 Anthropic
今天才发明的。社区里已经有多个项目在做这件事。我基于梦舟的 UE MCP
构建了一个 Unreal Engine
bridge，它的核心设计就是 feedback 工具：AI agent 发出操作指令后请求
viewport
screenshot，看到视觉效果，再决定下一步。这种”操作、截图、评估、再操作”的循环就是闭合
feedback loop 的具体实现。3D-Agent 在 Blender
Developer Forum 的讨论中也有类似思路：给 agent 加视觉反馈通道。

Anthropic 今天发布的创意 Connector
是这一代的产品化版本。和社区项目相比，优势在于整合度（Connector
平台已就位、Claude 多模态能力成熟、Blender
团队官方参与构建），但底层思路一致：双向通信，agent
不只发命令，还读回状态和结果。

实际构建闭环时遇到的问题，3D-Agent 作者总结了几条：推理和代码生成分开到不同模型效果更好；对
bpy 文档做 RAG 只解决约 50% 的问题；数学密集操作仍然是弱点。Blender
Artists
社区有人指出，这些工具在学习和探索阶段（解释错误信息、分析场景）比在直接生成最终产出时更有价值。

## 一个判断框架

上面三代演进可以压缩成一个判断框架。创意工具 agent
化需要三个组件按顺序就位：

组件一：可编程接口。 软件后端可以被程序控制。Blender
的 bpy、Photoshop 的 UXP、Figma 的 Plugin API。没有这一层 AI
没有操控入口。创意软件因为 pipeline
自动化的历史需求，这个组件就位得比大多数领域更早更完整。

组件二：自然语言翻译和双向连接。 LLM 翻译自然语言为
API 调用，同时需要协议层让 AI 和软件直接通信。MCP、CLI-Anything、各类
socket bridge 都是这一层。

组件三：感知和评估闭环。 Agent
看见操作结果，判断是否符合预期，不符合则修正。需要多模态感知（看渲染图）、质量评估标准（知道什么算好）、推理能力（把评估结果转化为修正动作）。

看到任何新的创意 AI
公告时，用这个框架判断它补上了哪个组件、还缺哪个，就能快速定位它处于什么阶段。

那么，这三个组件的哪一个才是当前的真正瓶颈？组件一在创意领域早已就位。组件二在过去一年多里被
MCP
和各类社区项目基本解决。真正卡住整个领域的是组件三：感知和评估闭环。

这里面有一个容易混淆的判断。很多人以为瓶颈在模型的”设计能力”或”空间理解能力”上，觉得需要模型更聪明才能做好创意任务。但实际情况是：当前主流模型（Claude、GPT-5.5、Gemini）在空间理解、代码生成、图形理解方面的基础能力已经够用了。它们能写出正确的
bpy 脚本、能理解场景的空间关系、能根据描述生成合理的布局。瓶颈不在”AI
能不能理解你要什么”，而在”AI
能不能看到自己做出来的东西、并判断对不对”。

这也意味着 Anthropic 在这件事上并没有不可逾越的护城河。OpenAI
如果想做同样的事，底层组件完全具备：GPT-5.5
的多模态能力可以看渲染图，MCP 是开放协议谁都能用（OpenAI 已经在支持
MCP），Blender 的 Python API 对所有人开放。飞书和钉钉在选择
CLI
路径时已经证明了连接层不是什么独占资源。关键组件已经成熟到各家都能组装出类似的产品。

Anthropic
今天发布的产品有意义的地方不在于它做了别人做不到的事，而在于它把社区里分散的探索整合成了一个一致的、有品牌背书的产品体验，并且用商业合作（Blender
Patron）和产品整合（Connector
平台）降低了用户的使用摩擦。这是执行和产品化的领先，不是技术能力的领先。

## 实际边界与人的角色

从社区使用报告看，当前这些工具（不论是 Anthropic 的 Connector
还是社区的 BlenderMCP/3D-Agent）有明确的能力边界。

效果好的场景是：程序化建模、场景搭建、空间关系处理、格式转换导出、分析和调试现有场景、解释错误信息。这些任务有明确的成功标准，不依赖主观审美。

无法胜任的场景是：原创概念设计、材质光照的审美调整、复杂角色动画、叙事性构图、品牌风格一致性。

对大多数创意从业者来说，当前最实际的用法不是”让 AI
替你做创意”，而是”让 AI
帮你处理创意工作中的非创意部分”。场景搭建中大量时间花在重复性的物理布置上，渲染流水线的工作主要是参数配置和队列管理，资产管理则是格式转换和命名规范。这些环节的自动化不需要
AI 有审美能力，只需要它能正确执行指令并告诉你执行的结果。

从三代演进的模式看，每一代消除的都是执行层面的摩擦。但每一代都没有消除两样东西：决定做什么（创意方向），以及判断做出来的东西够不够好（审美品位）。这两者本质上是主观的、依赖经验的、与文化语境绑定的。在可见的技术路径内，它们不会被自动化取代。

执行摩擦消除之后，竞争力的来源会发生转移。“谁能更快地执行”这个优势被削弱，“谁的想法更好”和”谁的判断更准”变得更重要。对创意从业者来说：精通工具操作的价值会下降，品位和方向感的价值会上升。

## 来源

Anthropic Claude Creative Connectors (MLQ.ai, 2026-04-28): https://mlq.ai/news/anthropic-releases-claude-connectors-for-seamless-integration-with-photoshop-blender-and-ableton/

The Verge (Anthropic 成为 Blender Patron): https://www.theverge.com/ai-artificial-intelligence/919648/anthropic-claude-creative-connectors-adobe-blender

Blender Artists 社区讨论 (官方 Connector): https://blenderartists.org/t/from-blender-mcp-to-3d-agent-anthropic-partners-with-blender-claude-ai-connector-now-official/1639106

Glitchwire (Claude Design vs Connectors): https://glitchwire.com/news/anthropic-brings-claude-to-photoshop-blender-and-ableton-in-largest-creative-too/

Claude Design 发布: https://www.anthropic.com/news/claude-design-anthropic-labs

9to5Mac (Blender 团队自建 Connector): https://9to5mac.com/2026/04/28/anthropic-releases-9-new-claude-connectors-for-creative-tools-including-blender-and-adobe/

No Film School (Adobe 合作): https://nofilmschool.com/adobe-claude-connector-announced

Hacker News Blender MCP demo: https://news.ycombinator.com/item?id=44622374

BlenderMCP (GitHub, v1.5.5): https://github.com/ahujasid/blender-mcp

3D-Agent: 从 BlenderMCP 到多 agent 架构: https://dev.to/glglgl/from-blender-mcp-to-3d-agent-the-evolution-of-ai-powered-blender-modeling-1m7d

3D-Agent Blender Developer Forum: https://devtalk.blender.org/t/3d-agent-blender-ai-assistant-built-a-multi-agent-system-on-top-of-blenders-mcp-and-python-api-and-sharing-architecture-learnings-for-the-lab-discussion/44260

CLI-Anything (HKUDS): https://github.com/HKUDS/CLI-Anything

CLI-Anything Harness 调研 (yage.ai): https://yage.ai/share/cli-anything-harness-survey-20260316.html

UE-Bridge (基于梦舟 UE MCP): https://github.com/grapeot/ue-bridge

Blender AI Assistant (社区插件): https://blenderartists.org/t/the-blender-ai-assistant/1601597

Blender scripting with AI (Atomic Object): https://spin.atomicobject.com/blender-scripting-with-ai/

Blender Scripting with Python (Springer, 2025): https://books.google.com/books/about/Blender_Scripting_with_Python.html?id=X75HEQAAQBAJ

Claude AI Connectors 总览: https://max-productive.ai/blog/claude-ai-connectors-guide-2025/

飞书钉钉发 CLI 对 MCP-first 的否决 (yage.ai): https://yage.ai/share/feishu-dingtalk-cli-reject-mcp-first-20260329.html

MCP 技术与商业博弈 (yage.ai): https://yage.ai/mcp.html

MCP dialect 分裂 (yage.ai): https://yage.ai/mcp-revisited.html

Agentic AI 落地困境 (yage.ai): https://yage.ai/agentic-ai-crisis-en.html