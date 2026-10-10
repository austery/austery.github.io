---
author: 课代表立正
date: '2026-05-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-s9Oj3koBTc
speaker: 课代表立正
tags:
  - ai-workflow
  - automation
  - cli-development
  - speech-to-text
  - pipeline-architecture
title: 构建自动化 AI 技能管线：Intake Skill 的架构设计与工程实践
summary: 本内容详细探讨了构建一个自动化 AI 技能管线（Intake Skill）的构思与实施规划。核心在于利用 Mac 的 Voice Memo 实现 100% 音频录制，通过 ASR 生成文本，并结合 Codex 实现自动化的 HTML 格式化与会议记录分解。文中明确了开发该 CLI 工具的七个阶段，涵盖了从调研、原型 scaffolding、Cron Tab 配置到隐私检查的全流程。
insight: ''
draft: true
series: ''
category: ai-workflow
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - GPT-4o
  - Whisper
  - Codex
  - Gemini
media_books: []
status: evergreen
---
### AI 实时模型升级与 Intake Skill 的构思

在工作流中，我们对 AI 的交互能力进行了升级，系统现在能够实现 **实时语音处理**（Real-time Processing）。这得益于 **OpenAI** 最近升级的 **Whisper** 模型（GPT Real-time Whisper）。尽管目前该模型尚未全面推送，但未来通过设置切换，即可在 **Whisper** 与其他模型间无缝切换，且保持原有功能不变。

基于这一能力，我计划将日常记录流程提炼为一个自动化的 **Intake Skill**。该技能的核心设计目标是实现完全脱离人工干预的自动化处理。

### 自动化音频管线与系统架构

为了实现 100% 的录音自动化，我们将录音源直接锁定在 **Voice Memo**，并采用 `rsync` 进行同步。整体自动化音频处理管线设计如下：

1.  **自动化调度**：通过 **Cron Tab** 设置定时任务（例如每日 24:00），触发 **ASR**（自动语音识别）管线，将音频转换为 **CSV** 文件，跳过复杂的 Speaker Recognition，以提高处理效率。
2.  **Codex 深度处理**：利用 **Codex** 的命令行界面对 CSV 数据进行二次处理。目标是生成格式化的 **HTML** 文件，其中包含每日核心总结（Summary）及行动项（Action Items）。
3.  **会议分解**：针对涉及会议的内容，系统会自动将其从主文档中分解，并在 `meetings` 文件夹中生成对应的记录。所有这些处理过程将不再通过程序直接调用 **Gemini**，而是转为通过 **Codex** 执行特定的 **Prompt** 来完成。

### Intake Skill 的开发与工程落地

这个技能将被打造为一个 **AI-oriented skill**，其核心组成部分是一个包含完整安装指南的 `README` 文件。未来该技能将发布为公共 **GitHub** 仓库，用户只需将仓库地址提供给 AI，即可自动完成配置。安装过程将涵盖 Python 环境搭建、ASR 配置及关键命令行工具的验证，AI 将全程引导用户进行配置，甚至包括对 **Cron Tab** 的增量更新，以确保原有配置不被覆盖。

为了实现这一目标，我们需要遵循以下七个工程阶段：

1.  **相关调研**：深入分析核心需求与技术选型。
2.  **项目 Scaffolding**：构建文件夹结构，并完善 **PRD**（产品需求文档）与 **RFC**（意见征求稿）。文档须严格使用英文编写，对原有的中文字幕 Prompt 进行精确的英文翻译，避免缩写。
3.  **CLI 开发与测试**：完成 CLI 的核心设计，确保测试通过，并更新 `working.md`。
4.  **初始验证流程**：利用 TTS 工具生成一个 10 秒钟的示例音频文件，自行跑通初始验证流程。
5.  **文档完善**：完成 `README` 及相关说明文档的编写。
6.  **安全性检查**：进行严格的 **Privacy Check**，清除可能涉及隐私及安全性的内容。
7.  **GitHub 初始化**：初始化 Git 仓库，完成 `master` 分支的提交并推送。

整个过程将由 AI 作为主要执行者，确保该 CLI 工具的开发过程高效、可落地且符合工程标准。