---
author: AI超元域
date: '2026-01-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KD2D59_XGd8
speaker: AI超元域
tags:
  - agent-skills
  - ai-programming
  - ui-ux-design
  - prompt-engineering
  - code-generation
title: 2026年AI编程新纪元：Antigravity 引入 Agent Skills，革新AI辅助开发与UI设计
summary: 本视频介绍了Google Antigravity平台对Agent Skills的支持，标志着2026年成为AI编程的‘Skills元年’。Agent Skills通过打包工作流、领域知识和最佳实践，使AI编程助手能够稳定产出代码，尤其为非专业开发者带来福音。视频演示了如何安装、管理和调用现有的Agent Skills（如用于创建咖啡店落地页并自动生成图像），以及如何手动创建简单的代码审查Skill。重点展示了强大的UI/UX Pro Max Skill，其能基于React等技术栈生成现代、美观的拟物化界面，极大地提升了UI设计效率与质量。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - OpenAI
products_models:
  - Antigravity
  - Agent Skills
  - nano-model
  - jap-ro-model
  - UI UX Pro Max
media_books: []
status: evergreen
---
2026年，AI编程领域迎来了里程碑式的变革，**Antigravity**（AI编程助手平台）正式支持 **Agent Skills**（智能体能力扩展格式）。这一举措标志着AI编程进入了“**Skills元年**”，将AI辅助开发的范式从传统的、临时的提示词（prompt）交互，升级为通过预设的、可复用的技能模块来稳定产出代码。

## Agent Skills：AI的长期资产与领域知识封装

AI虽然日益智能，但普遍缺乏开发者特定的领域知识、工作流程和最佳实践。**Agent Skills** 旨在解决这一核心问题。它允许将公司、团队或个人的工作流、最佳实践及脚本等工具，像模块一样打包。这使得AI编程助手能够按需加载、反复复用这些技能，将AI从一个只能临时发挥创意的工具，转变为一个具备特定领域能力的稳定执行者。正如一个广为流传的区分：“Prompt是临时指令，而Agent Skills才是长期资产。”

这种能力扩展不仅提高了AI的输出质量和稳定性，尤其为非专业开发者带来了巨大的福利。即使完全不懂编程，也能通过安装现成的Agent Skills，打造一个真正懂其业务的专属AI编程助手。Agent Skills的本质是AI的专用业务手册，通过组织文件夹和Markdown文件来封装知识、工作流、最佳实践和脚本。AI智能体能够自动发现并按需加载这些技能，实现能力复用、标准化，并采用渐进式加载机制，有效避免了**上下文爆炸**（AI模型因输入过多信息而导致性能下降或无法处理的情况）。

## 演示一：利用预置技能创建咖啡店落地页

在Antigravity中使用Agent Skills非常直观。首先，需要确保平台已升级至最新版本。随后，可以通过克隆官方提供的示例项目来测试现有的Agent Skills，这些示例涵盖了前端设计和项目创建等功能。

克隆项目后，需要将Agent Skills放置在指定路径下。它们可以存放在当前项目路径，仅供该项目调用；或存放在全局路径，供所有项目调用。视频演示了将其放置在官方推荐的全局路径，并通过命令行执行，成功将多个Agent Skills导入。

随后，我们测试了官方的前端设计技能。输入的提示词是：“创建一个咖啡店的落地页，并使用这个前端设计的skill。” 模型选择了对前端UX设计尤为适合的 **jap ro model**。

此次演示中最令人惊叹的一点是，Antigravity能够自动调用 **nano model** 来生成网站所需的图像。这是其他AI编程助手（如Claude Code）所不具备的独有功能。该功能为咖啡店落地页自动生成了两张高质量的图像：一张是咖啡馆内部的景象，另一张是咖啡豆的特写。

项目随后使用Next.js和TypeScript成功创建。运行该项目后，一个精美的咖啡馆落地页呈现在眼前，其中嵌入了由nano model生成的适配性极强的配图，导航栏设计专业，整体视觉效果出众，这充分展示了Antigravity的独有优势。

## 演示二：手动创建Agent Skill与高级UI/UX设计

除了使用预置技能，Antigravity也支持手动创建Agent Skills。官方文档提供了详细步骤，其中包含一个用于代码审查的简单技能示例。

在当前项目路径下，可以创建用于存放Agent Skills的目录。然后，将官方提供的代码审查示例内容复制到一个名为 `skill.md` 的文件中。当提示Antigravity“使用code review来审查当前项目”时，它能够读取 `skill.md` 文件，分析项目代码，并输出代码审查结果及性能优化建议，这展示了手动创建自定义技能的灵活性。对于更复杂的技能开发，视频中还提到了一个名为 `Seeker` 的开源项目，可用于将任何开源项目或网站转化为Agent Skills。

### 演示三：UI UX Pro Max Skill - 打造拟物化待办事项列表

视频重点演示了功能强大的 **UI UX Pro Max** Agent Skill，它专注于AI驱动的UI/UX设计，并支持多种技术栈，包括基础的HTML/CSS，以及React、Next.js、Swift、React Native和Flutter等。

首先，通过`npm`命令安装该项目，然后执行专门针对Antigravity的安装命令。在Antigravity中，通过输入斜杠`/`即可调出UI UX Pro Max技能。

本次的提示词是：“使用React构建一个待办事项列表，采用**拟物化风格**，包含添加、完成和删除任务的功能，并加入柔和的阴影和微妙的景深效果。” 同样选择了 **jap ro model**。

Antigravity利用 **UI UX Pro Max** 技能，为其带来了丰富的UI设计经验和最佳实践，旨在生成美观、现代化的UI。几分钟后，项目创建完成。运行后，一个功能齐全且视觉效果出色的拟物化待办事项列表展现在眼前。添加、完成和删除任务的交互流畅，其设计的拟物化UI效果显著，体现了Agent Skills在提升UI设计质量方面的巨大潜力。

本期视频展示了Antigravity如何通过Agent Skills革新AI编程与UI设计流程。从利用现有技能快速生成项目，到手动创建自定义技能，再到调用强大的UI UX Pro Max实现复杂设计，Agent Skills为开发者提供了前所未有的效率与可能性。未来将会有更多实用的Agent Skills及其使用技巧和最佳实践的演示。