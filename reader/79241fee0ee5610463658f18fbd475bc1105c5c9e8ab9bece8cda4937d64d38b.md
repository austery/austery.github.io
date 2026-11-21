---
author: AI超元域
date: '2026-03-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bhuGrjuCM_g
speaker: AI超元域
tags:
  - prompt-engineering
  - ai-plugins
  - long-term-memory
  - automated-installation
  - local-llm
title: 🚀让OpenClaw实现真正自我进化！让龙虾越用越聪明！memory-lancedb-pro记忆插件大升级！智能提取功能实测，告别垃圾记忆！小白也能一键全自动安装配置！让AI真正记住你，龙虾保姆级教程
summary: 本视频详细介绍了 Memory LanceDB Pro 插件的重大升级，特别是其核心的“智能提取”功能。该功能通过自动识别对话中的关键信息、避免重复和无关内容，显著提升了 OpenCLoud 的记忆能力和智能化水平。视频还提供了两种更智能的安装方式，特别是基于 AI Skill 的自动化安装与配置流程，极大地降低了小白用户的门槛，并展示了如何灵活配置本地模型及 API，确保插件的最佳性能。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenCLoud
  - LanceDB
  - Grok AI
products_models:
  - Memory LanceDB Pro
  - Cloud Code
  - Codex
  - OpenCLoud
  - Gemini
  - Qianwen
  - BGE M3
media_books: []
status: evergreen
---
### 插件升级与亮点

最近我们为大家分享了多期 OpenCLoud 的高级用法视频，本期将继续深入。先前已演示过一款用于提升 OpenCLoud 记忆能力，但当时尚不完善的插件。目前，这款名为 **Memory LanceDB Pro** 的记忆插件已大幅更新，新增了包括**智能提取**在内的多项功能，相较于初次开源时已足够成熟。它赋予 OpenCLoud 真正的**自我进化**能力，使其日益智能，并已获得 LanceDB 官方的推荐与认可。本视频将演示如何使用此插件，让 OpenCLoud 更聪明。特别地，针对不熟悉复杂命令部署的小白用户，将详细讲解更智能的安装方式。

### 智能提取实测

**Memory LanceDB Pro** 插件的核心亮点在于其新增的**智能提取**功能。这一功能超越了市面上其他开源插件，并获得了 Grok AI 的主推。为了让不熟悉 Rag（Retrieval-Augmented Generation）等知识点的用户也能理解其优势，我们将用最通俗的方式深入解析。

智能提取的详细流程可视为一个“记忆秘书”：它能听取我们与 AI 的对话，自动甄别并挑出值得记忆的要点。同时，它还会检索数据库，判断是否存在类似内容，从而避免重复存储。

我们在 OpenCLoud 中进行实际测试。首先，新开一个 session，输入提示词：“我喜欢使用 Cloud Code 和 Codex 进行编程任务，偏好的编程语言是 TypeScript 和 C#，但不喜欢使用 Python。” AI 立即回应：“已记住。以后涉及编程任务，默认使用 Cloud Code 和 Codex，代码优先选择 TypeScript 和 C#，不碰 Python。”

随后，我们另开一个 session，以验证其记忆检索能力。提问：“我的技术栈是什么？” AI 精准检索并回应：“技术栈包括编程语言 TS 和 C#（无 Python），开发工具方面，喜欢用 Codex 写代码，Cloud Code 做代码审查。还检索到你维护的 OpenCLoud 插件，甚至知道你的 GitHub 下有多个私有仓库，这些是从日常交互积累的。” AI 进一步确认信息来源于 LanceDB 长期记忆。

此过程体现了与 OpenCLoud 对话、由大模型提取内容、进行向量预筛，再由大模型判断是创建新记忆、合并旧记忆还是直接跳过的完整闭环。对于不值得记忆的内容，插件不会将其写入。

例如，输入“今天天气不错，适合出门踏青”，AI 正常回应。随后新开 session，提问“今天适合做什么？”，AI 的回答是“趁周末搞项目，看这周 AI 有什么新动态，整理待办事项”，这与“出门踏青”话题完全无关，证明不适合长期记忆的内容未被存储。

进一步测试检索：“检索 LanceDB 中最新的几条记忆，是否有关于出门踏青的内容。” AI 回答：“没有关于出门踏青的记忆。” 这再次印证了插件智能过滤无关紧要内容的能力。

### 智能安装新方法

鉴于部分用户可能因 OpenCLoud 模型能力或版本差异，难以完成复杂命令的部署，本项目提供了两种更智能的安装方式。

第一种是**脚本安装**，用户只需遵循说明文档中的几条命令即可完成。但此方法可能无法适配所有 OpenCLoud 版本。

第二种，也是更推荐的方式，是利用专为 AI 智能体开发的 **Skill**。这个 Skill 相当于 Memory LanceDB Pro 插件的使用手册和文档。一旦 OpenCLoud、Cloud Code、Codex 等 AI 智能体装载此 Skill，便能像查阅说明书一样，深入了解插件的安装、使用、配置及最佳工作流，从而实现自动化安装。这极大地便利了小白用户，无需自行查阅说明文档或执行复杂命令。此 Skill 可兼容多种 AI 编程助手，如 OpenCLoud、Cloud Code、Codex、Anti Gravity、Cursor 等。

### Skill 驱动的自动化

以下以 OpenCLoud 为例，演示 Skill 驱动的自动化安装与配置。

首先，复制插件仓库链接，在 OpenCLoud 中开启新 session，并输入提示词：“为我安装这个 Skill”，附上 Skill 的完整链接。安装 Skill 的过程极为简单，通常不会出错。

Skill 安装完成后，即可利用它来安装 Memory LanceDB Pro 插件。在 OpenCLoud 中输入：“通过这个 Skill 告诉我如何从零安装 Memory LanceDB Pro。” OpenCLoud 将检索 Skill 中固化的多种安装方式，并推荐最简单的方法，如通过 OpenCLoud 插件管理器安装。

接着是配置环节，需要设置 API 密钥，包括嵌入模型、重排模型及大语言模型的 API。提供三种方案：最简单、最省钱、功能最完善。用户可根据需求选择，并点击链接获取 API Key（例如，使用“基拿”的 API Key）。

若遇到 API Key 额度问题，如“我的基拿 API 没有额度，有没有本地模型可以替代在线的模型？”，AI 会推荐本地部署方案。例如，方案一推荐安装“欧拉玛”（Oulama），并给出安装及模型拉取方式，以及推荐的搭配。

对于完全不懂技术的用户，可以直接输入：“我是小白，什么都不懂，请按照你的理解自动帮我配置。” OpenCLoud 将依据 Skill 中的流程，实现最佳本地部署方案的自动化配置。

若用户了解 Rag 知识，可自行搭配，例如指定嵌入模型和 Gemini 大语言模型。

配置完成后，可询问：“如果都设置好了，需要开启哪些功能才能确保记忆效果最好？” AI 将列出所需功能。若用户不理解功能含义，可输入：“我完全不懂你给的核心功能是什么意思？按照你的理解为我开启有价值的功能，从而让你更智能。” AI 会根据 Skill 自动开启真正有价值的功能。

对于检索调优参数，若用户不懂，可说：“我不懂什么是检索调优参数，你为我调到最佳状态。” OpenCLoud 即会进行自动化优化。

最后，进行插件功能测试。输入：“我不确定记忆功能是否开启，请为我测试写入和检索记忆。” 初始测试因“基拿” API Key 额度不足而失败。AI 提出解决方案（如安装“欧拉玛”）。更换 API Key 后，测试成功输出“写入成功”。

### 本地模型兼容性

插件支持多种本地模型。可输入“列出这个插件所有本地模型的支持”，AI 会列出嵌入模型和语言模型相关的本地选项。

若需更新模型，可询问：“大语言模型可以用哪些新开源的千问系列模型？” AI 会列出千问三系列模型。询问嵌入模型支持的最新模型，AI 会相应列出。若不知如何选择，可请求：“给出最佳的本地嵌入模型的搭配。” AI 推荐了“BGE M3”嵌入模型。

这个 Skill 相当于为 OpenCLoud 提供了 Memory LanceDB Pro 的参考手册，能检索内容并辅助用户完成自动化安装。

本项目已托管至组织下，欢迎积极参与开发。目前已有二十多位贡献者，项目获得 2.4K Star。本期视频所用笔记将置于视频下方描述栏或评论区。感谢观看，欢迎点赞、关注和转发。