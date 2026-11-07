---
author: INDIGO 数字镜像
date: '2026-03-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jNmqIeaQ7_c
speaker: INDIGO 数字镜像
tags:
  - ai-agent
  - vibe-coding
  - software-engineering
  - automation
  - design-system
title: AI 时代的极致加速：从 Vibe Coding 到 Agent 自动设计
summary: 本期直播深入探讨了 AI Agent 引发的软件工程范式革命。通过现场演示 Claude Code 快速构建 Telegram 机器人以及 Agent Swarm 在 Pencil 工具中自动完成网页设计，揭示了“杰文斯悖论”如何增加软件人才需求。核心观点指出，未来软件将是“模型+上下文+连接”的结合，而人类的角色将从生产者转变为业务逻辑的连接者。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Listen Wu
companies_orgs:
  - OpenAI
  - Anthropic
  - Google
products_models:
  - Claude Code
  - Pencil
  - Telegram
  - GPT-4o
media_books: []
status: evergreen
---
### 开场与设备调试

**宝玉**: 大家看看，我现在只能看到屏幕。

**Listen Wu**: 这个好，画面马上就出来了。

**宝玉**: 别着急，我调一下音，把麦带上。我们来测试一下设备，今天有两个人连线。好了，画面上了，我把声音开小一点。大家看看 YouTube 和微信直播间声音有没有问题，没问题的话直接扣 1。今天我们是突然想到要直播，所以叫“周末氛围直播”，不像我平时的月末直播或新年直播那样准备很多 PPT。

**宝玉**: 最近一两个月，大家最焦虑的就是 **Agent**。我在新年直播时详细讲过“小龙虾”（OpenDevin 相关项目），当时看深圳都在排队安装。这两个月变化非常快，有种“极致加速”的感觉。差不多两个月时间，我们感觉编程能力有了十倍的进展。在通往 **AGI** 的道路上，能写代码就意味着能做所有事情。

**宝玉**: 介绍一下我旁边的帅哥 **Listen Wu**，他是我的技术搭档。他本来是来温哥华滑雪的，结果遇到狂风暴雨。我们两年前合作过一个产品叫 **Memo**，后来被大模型的能力迭代掉了。这一次我们围绕 Agent 展开，Listen 用的 **Claude Code** 比较多，今天会让他现场演示真实的 Web Coding 和 Web Design。

### 软件工程的“杰文斯悖论”

**宝玉**: 在进入 Demo 之前，先看一张图。这是我一周前发的，关于软件工程的“**杰文斯悖论**（Jevons Paradox）”。简单来说，当某种资源（如 AI Token 或电力）变得越便宜、供给量越大时，需求反而会变高。虽然大家担心软件工程师失业，但 Indeed 上的职位招聘数据显示，开放岗位反而在变多。

**Listen Wu**: 关于这个现象，我也在思考。之前大家因为 **Anthropic** 发布新功能或者某些大厂裁员而焦虑，觉得 SaaS 和软件工程会被干掉。但这其实是一场革命。原来的高效生产方式会取代旧方式，导致旧环节的工程师被剔除。

**Listen Wu**: 但为什么需求增加了？以前的 SaaS 是标准化产品，企业因为没有技术能力而选择采购。但如果现在的 **Coding Agent** 让原本不具备编程能力的人拥有了开发能力，一家两百人的公司可能只需要招两个 AI 工程师，就能自建内部的 **CRM** 或 **ERP**。以前不需要软件工程师的中小企业，现在都敢想自建系统了，因为 Agent 比买 SaaS 更具定制化优势。

**宝玉**: 总结一下，中小企业的胆子变大了。以前雇十几个人的团队才能做的定制化需求，现在一个懂技术的员工配合 **Claude Code** 就能搞定。

### AI Harness 与 Agent 基础设施

**Listen Wu**: **AI Harness**（马具/工具集）是最近讨论很多的话题。简单说，就是在完成任务时给 Agent 配备什么样的工具、场景和流程。

**Listen Wu**: 另外一部分是 **Agent Infra**（Agent 基础设施）。未来的主要用户不再是人，而是 Agent。我们需要为 Agent 创建更多的资源，比如文件系统沙盒，让它在既定范围内发挥最大效应。

**宝玉**: 我认为逻辑层的软件会慢慢消亡，因为每个人都有自己的业务逻辑需求，用 AI 直接写就好了。

**Listen Wu**: 没错，Agent 本身变成了 UX 的一部分。比如财务或市场营销软件，每家公司的操作逻辑都不一样。Agent 的最强项是 **Dynamic**（动态化），它能按需动态生成业务逻辑，这会让固化的 SaaS 压力很大。

### AI 是人类的镜子：从写作到编程

**Listen Wu**: 我觉得 **Claude Code** 是真正意义上的第一个 Agent。它在本地运行，能访问你的文件系统和计算资源。

**Listen Wu**: 有句话叫“AI 是人类的投射”。比如有些人能用 AI 写出好文章，是因为他有自己的范式。我们做过实验，把宝玉过去几年的长文交给 AI 总结，它能精准提取出写作风格，比如开头要宏大、最后要回归个人价值等。我们现在就是把这种范式变成一种 **Skill**。

**宝玉**: 大家不要总是问提示词（Prompt），要多和它聊。不要预设路径，不要告诉它第一步、第二步干什么，否则会限制它的智商。我们要给它点“意外”，让它在磨合中发挥潜能。

### 演示一：使用 Claude Code 构建 Telegram 机器人

**Listen Wu**: 我们现在演示一个实际场景。宝玉在 Mac Mini 上跑小龙虾，但 API 太贵了。我们都订阅了 Claude 账号，所以想物尽其用。我打算花二三十分钟，用 **Claude Code** 在本地跑一个 Service，把本地的 Claude 和手机上的 **Telegram** 连起来，直接在 Telegram 里给它下任务。

**Listen Wu**: 我现在在终端里操作。我用了 **Supervised**（终端工具）和 **Typewritten**（语音输入），因为跟 Agent 交流，语音输入的速度才跟得上它的响应。

**宝玉**: 大家看，Claude Code 会自动编排，同时启动三个 Agent 协作：一个调研本地连接，一个调研 Telegram Bot API，一个调研 **Vercel AI SDK**。

**Listen Wu**: 我告诉它我是一个非技术人员，要求它给我一个简洁的 **On-boarding** 流程。它写好了计划，包括 Message Flow：用户发消息到 Telegram，SDK 转发给本地 Claude Code，处理完再回传。

### 演示二：Agent Swarm 与自动网页设计

**Listen Wu**: 在等待代码运行的同时，我们演示一下 Web Design。这个工具叫 **Pencil**，它给 Agent 提供了一个画布。

**Listen Wu**: 我们把之前设计师做的 Logo、配色和字体贴进去，让 Agent 基于这套 **Design System** 自动搭建三个网页：Landing Page、Blog Page 和产品指数页面。

**宝玉**: 大家看屏幕，现在不是我们在动，是 Claude 的三个 Agent 在画布上操作，光标都在跳动。它们在相互沟通，一个做设计，一个在校验，一个在处理移动端适配。这就是 **Agent Swarm**。

**Listen Wu**: 它的审美很在线。如果你给它足够的 **Brand Identity** 输入，它的交付程度非常高，AI 味儿很低。

### 总结：AGI 时代的生存法则

**宝玉**: 刚才演示的代码已经跑通了，Listen 在 Telegram 里问它最近 OpenAI 发生了什么，本地的 Agent 马上搜索并生成了一份三月份的简报 Markdown 文件。

**宝玉**: 我们正处于一个模型能力深不可测的阶段。虽然它们不一定有创意，但逻辑非常健壮。人反而是最大的瓶颈，因为我们在用旧的范式思考新武器。

**Listen Wu**: 就像给猴子递了一把 AK。大家不要焦虑，要放开想象力。旧的价值在新的体系里不工作了，我们应该思考如何贡献新的价值，比如为 Agent 创造更好的“画布”。

**宝玉**: 未来软件的公式是：**Model + Context + Connection**。人就是那个 **Connector**（连接者）。我们不再是写软件的人，而是像老板一样，定义 Context，协调 Agent 协作，然后自己去打高尔夫。

**宝玉**: 所有公司都会变成软件公司，因为业务都融入了 Agent 驱动的流程中。这是一个巨大的范式转移。今天的直播就到这里，感谢大家在周末陪我们聊了两个小时。