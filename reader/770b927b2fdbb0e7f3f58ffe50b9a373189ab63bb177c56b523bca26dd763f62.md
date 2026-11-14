---
layout: post.njk
source: https://blog.qiaomu.ai/google-opens-okf-knowledge-format-for-ai
speaker: 向阳乔木
title: Google 开源了一个知识格式标准，专门喂给 AI 吃 · 乔木博客
date: '2026-06-25'
summary: Google 开源了 Open Knowledge Format (OKF) 标准，旨在解决 AI 模型难以获取分散的内部知识（如数据库结构、API 定义等）的问题。该格式以带 YAML frontmatter 的 Markdown 文件为基础，通过定义清晰的概念边界和互操作性，使不同系统和模型能够无缝地消费和利用知识，从而推动 AI agent 开发的效率提升。
area: tech-engineering
category: ai-application
tags:
  - knowledge-format
  - okf
  - metadata-as-code
  - agentic-workflow
people: []
companies_orgs:
  - Google
products_models: []
media_books: []
draft: true
status: evergreen
---

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# Google 开源了一个知识格式标准，专门喂给 AI 吃

AI资讯

·

2026年6月25日

·

90 次阅读

·

约 8 分钟

大模型越来越聪明，但有一件事它始终做不好：它不知道你们公司的事。

你的数据库表结构、业务指标的定义、两个系统之间怎么 join、某个 API 已经废弃了，这些信息散落在各种地方，大模型根本够不着。

于是每次构建一个新的 AI agent，工程师都要重新解决同一个问题：怎么把这些上下文塞给模型。

Google 在 6 月 13 日发布了一个叫 OKF（Open Knowledge Format） 的开放规范，试图把这件事标准化。

> https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing/

## 问题出在哪里

现在一个典型组织里，AI 需要的内部知识分散在这些地方：

元数据目录，有自己的 API

各种 Wiki、第三方系统、共享云盘

代码注释、docstring、notebook 单元格

几个资深工程师的脑子里

当一个 AI agent 需要回答"怎么从事件流里计算周活跃用户？"，它得从这些互不兼容的地方拼凑答案。

每个云厂商有自己的知识图谱 schema，每个工具有自己的 SDK，知识被锁在各自的平台里，出不来。

结果就是：每个 agent 开发者都在从零解决同一个上下文组装问题。

## 一个反复出现的模式

过去一年，开发者社区里自发长出了一种模式。

有人叫它"LLM Wiki"，有人叫它"metadata as code"，形态各异，但本质相同：用一个 Markdown 文件库来承载 AI 需要的知识，让 agent 在做正式工作之前先读这些文件。

Andrej Karpathy 在他的 LLM Wiki gist 里把这件事说得很清楚："大模型不会感到无聊，不会忘记更新交叉引用，一次可以处理 15 个文件。"

人类维护个人 Wiki 最终放弃的原因，恰好是大模型最擅长的事。

类似的模式还有：接入 coding agent 的 Obsidian vault、AGENTS.md 和 CLAUDE.md 这类约定文件、数据团队里那些 agent 执行任务前会查阅的 index.md 和 log.md。

这个模式有效，但每个实例都是定制的。

Karpathy 的 Wiki 和你们团队的 Wiki 和某个厂商的目录导出，长得很像（Markdown、frontmatter、交叉链接），但没有人刻意让它们互通。

没有人约定每个文档应该带哪些字段，文件名代表什么含义。

知识还是被锁在各自的团队里。

## OKF 是什么

OKF 不是一个新服务，不是一个平台，是一个格式。

v0.1 的设计极其克制：一个目录，里面是带 YAML frontmatter 的 Markdown 文件，加上一小套约定。

目录结构长这样：

```
<code class="language-plaintext">sales/
├── index.md
├── datasets/
│   ├── index.md
│   └── orders_db.md
├── tables/
│   ├── index.md
│   ├── orders.md
│   └── customers.md
└── metrics/
    ├── index.md
    └── weekly_active_users.md
</code>
```

每个概念是一个文件，文件路径就是这个概念的身份标识。

文件头部是一小块 YAML，正文是 Markdown：

```
<code class="language-yaml">---
type: BigQuery Table
title: Orders
description: One row per completed customer order.
resource: https://console.cloud.google.com/bigquery?p=acme&d=sales&t=orders
tags: [sales, revenue]
timestamp: 2026-05-28T14:30:00Z
---

# Schema

| Column      | Type   | Description                        |
|-------------|--------|------------------------------------|
| order_id    | STRING | Globally unique order identifier.  |
| customer_id | STRING | FK to [customers](/tables/customers.md). |

# Joins

Joined with [customers](/tables/customers.md) on `customer_id`.
</code>
```

概念之间用普通 Markdown 链接互相引用，整个目录就变成了一张关系图，比文件系统的父子层级丰富得多。

完整的 v0.1 规范只有一页。

## 三个设计原则

最小约束。

OKF 对每个概念文档只强制要求一件事：有 type 字段。

其他字段、文档结构、正文格式，全部由生产者自己决定。

规范只定义互操作的边界，不定义内容模型。

生产者和消费者解耦。

人工手写的 Wiki 可以被 AI agent 消费。

元数据导出管道生成的 bundle 可以在可视化工具里浏览。

一个大模型合成的知识库可以被另一个大模型查询。

格式是契约，两端的工具可以独立替换。

格式，不是平台。

OKF 不绑定任何云厂商、数据库、模型提供商或 agent 框架。

读写这个格式不需要任何账号或 SDK。

Google 把它作为开放标准发布，因为知识格式的价值来自有多少方在用它，而不是谁拥有它。

## 随规范一起发布的东西

Google 同时开源了几个参考实现：

一个富化 agent：遍历 BigQuery 数据集，为每张表和视图起草 OKF 文档，再跑第二轮 LLM，抓取权威文档，补充引用、schema 和 join 路径。

一个静态 HTML 可视化工具：把任意 OKF bundle 渲染成交互式关系图，单个自包含文件，不需要后端，不需要安装，数据不离开页面。

三个示例 bundle：GA4 电商数据集、Stack Overflow、比特币公开数据集，由参考 agent 生成，提交到 repo 里作为活的示例。

另外，Google Cloud 的 Knowledge Catalog 已经更新，可以摄入 OKF 格式并把它提供给 agent 使用。

## 这件事值不值得关注

OKF 现在是 v0.1，是起点。

它能不能成为真正的通用格式，取决于有多少生产者和消费者愿意采用它。

但有一点值得认真对待：这个问题本身是真实的。

每个在做 AI agent 的团队，迟早都会碰到"怎么管理模型需要的上下文"这个问题。

现在大家各做各的，重复造轮子。

如果一个足够轻量的格式标准能在这里站稳，对整个生态的效率提升是实质性的。

如果你的团队正在构建 AI agent，或者在管理数据资产的元数据，OKF 的规范只有一页，读一遍的成本极低。

先看看它能不能描述你们现有的知识结构，再决定要不要往里投入。

规范、参考实现和示例 bundle 都在 GitHub 上，搜索"Open Knowledge Format"可以找到。

© 2026

·

向阳乔木