---
author: AI超元域
date: '2026-01-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=daXOXSSyudM
speaker: AI超元域
tags:
  - prompt-engineering
  - self-hosted-ai
  - ai-agent
  - automation
  - code-generation
title: Cloud Bo：您的个人AI员工，全面提升工作与学习效率
summary: 本文详述了开源AI助手Cloud Bo，一个实用的自托管AI员工框架。它通过长期聊天实现自我进化，具备无限记忆与多平台部署能力，并支持WhatsApp等工具交互。视频演示了其部署、浏览器自动化、定时任务（如博客监控）及AI辅助编程（如开发登录页）等核心功能，展示了Cloud Bo如何大幅提升工作效率。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - WhatsApp
products_models:
  - Cloud Bo
media_books: []
status: evergreen
---
### Cloud Bo：AI员工的黎明

最近，开源项目 **Cloud Bo** 凭借其作为首个真正实用的自托管AI员工而爆火。本质上，它是一个本地运行的 **AI 智能体框架**（AI Agent Framework: A system that enables AI agents to perceive, reason, and act）。经过几天的测试，Cloud Bo展现出强大的功能和广泛的应用场景，甚至能通过长期聊天实现自我进化，记住用户偏好并主动提供建议，其能力可通过安装不同的 **Skills**（Skills: Installable modules that give Cloud Bo specific capabilities）来扩展。合理运用Cloud Bo，可以极大地提升工作与学习效率。

其部署极其简单，仅需一条命令，5到10分钟即可完成安装，并支持macOS、云服务器、甚至旧电脑（安装Linux系统）等多种平台。Cloud Bo具备主动执行任务、无限记忆的能力，远超普通聊天AI。更关键的是，它支持通过 **WhatsApp**（WhatsApp: A popular messaging application used for interaction）等即时通讯工具进行交互，让AI成为真正的执行者，无论是控制电脑、实现自动化工作流还是开发应用。本期视频将首先演示Cloud Bo的部署方式，随后结合几个实用案例测试其综合能力。

### 系统架构：智能体之心

Cloud Bo的系统架构分为几个关键层次：
1.  **用户层**：用户通过WhatsApp等即时通讯工具与Cloud Bo进行交互。
2.  **渠道层**：负责协议适配、消息解析、格式转换、媒体处理及分块传输。
3.  **网关核心**：实现对话管理、消息路由、工具调用自动化。

其核心功能包括：多渠道统一登录、**浏览器自动化**（Browser Automation: Cloud Bo's ability to control a web browser to perform tasks）、系统级完整访问、语音唤醒与对话、可视化工作区、**定时任务**（Scheduled Tasks: Automating tasks to run at specific times）及自动化功能。此外，Cloud Bo拥有成熟的Skills生态，并支持多智能体协作。

### 部署与交互：从零到一

本地部署Cloud Bo非常便捷。首先，复制官方文档提供的部署命令到终端执行。
1.  **同意协议**：按提示同意用户协议。
2.  **模型提供商设置**：可选择使用OpenAI（Code Ex订阅或API Key）或Anthropic的API Key。
3.  **聊天工具选择**：选择WhatsApp作为交互工具。终端会显示一个二维码，需用手机WhatsApp扫描以完成设备连接。
4.  **Skills安装**：根据需求选择安装Skills，或跳过此步骤。
5.  **API设置**：此处可选择暂时略过。
6.  **启用Session记忆**：选择启用Session记忆功能，以增强AI的连续性。
7.  **重新运行与默认选择**：设置完成后，重新运行命令并默认选择第一项。

这将自动在浏览器中打开Cloud Bo的后台管理页面，提供一个类似ChatGPT的对话框。

### 实战演练：自动化与编程

**1. 基础对话与多渠道交互**
在网页后台输入“讲个故事”，Cloud Bo会生成一个故事。同样，在WhatsApp中输入相同指令，它也能快速响应并提供完整故事。它还能记录过往任务，如自动抓取网站或博客内容，并推送到WhatsApp。

**2. 浏览器自动化**
测试场景：通过WhatsApp输入提示词，要求Cloud Bo调用浏览器打开Cloud Bo官方仓库并提供安装命令。
结果：Cloud Bo成功自动打开浏览器，定位至官方仓库，并清晰列出了推荐的NPM全局安装及启动命令。这表明，即使不在电脑旁，也能通过手机WhatsApp操控Cloud Bo执行复杂的浏览器自动化任务。

**3. Skills安装与定时任务**
*   **Skills安装**：在网页后台可根据需求安装对应Skills，如“blog watch”用于监控博客更新。
*   **定时任务设置**：
    *   可通过后台或命令行创建定时任务。
    *   演示使用`blog watch`命令添加需监控的博客，并设置每天9点（可修改时区）检查更新，将与AI大模型、Agent或编程工具相关的内容推送到指定的WhatsApp号码。
    *   命令执行成功后，可在后台刷新查看任务，并可手动运行以立即测试。
    *   测试结果：Cloud Bo将抓取到的文章更新（本例中因已读，显示无更新）推送到WhatsApp。

**4. AI辅助编程**
*   **Coding.AI Skill**：利用此Skill（运行XCodeCop）进行编程。
*   测试场景：通过WhatsApp提示，要求Cloud Bo调用Coding.AI开发一个后台登录页，并通过浏览器查看效果。
*   结果：等待约2分钟后，Cloud Bo自动在浏览器中打开了开发的后台登录页面，效果相当不错。
*   价值：即使不在电脑前，也能通过WhatsApp远程操控Cloud Bo进行编程开发。

Cloud Bo支持的Skills极为丰富。本次视频仅展示了基础用法，后续将深入探讨高级用法。视频所用代码和指令可在描述栏、评论区或博主博客中查找。