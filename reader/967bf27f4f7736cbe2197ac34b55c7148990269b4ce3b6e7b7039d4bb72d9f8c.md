---
layout: post.njk
source: https://yage.ai/share/gemini-os-android-intent-20260512.html
speaker: yage.ai
title: |-
  他们建 Connector，Google 调系统：为什么 AI
  时代的操作系统优势，模型质量追不平
date: '2026-05-12'
summary: 文章对比了 Google Gemini 在 Android 操作系统层面与 OpenAI、Anthropic 独立的 Connector 方式在 AI 应用集成上的差异。作者认为，Google 的核心优势并非模型质量，而是其对操作系统的控制力，这使得 Gemini 能够通过系统级权限直接调用应用功能，从而提供远高于 Connector 方式的效率和用户体验。这种平台层面的控制力，以及对开发者生态的驱动能力，才是未来 AI 操作系统竞争的关键，而非模型性能的军备竞赛。
area: tech-engineering
category: architecture
tags:
  - ai-os
  - platform-advantage
  - system-integration
  - operating-system-control
  - developer-ecosystem
people: []
companies_orgs:
  - google
  - openai
  - anthropic
products_models:
  - gemini
  - chatgpt
  - claude
  - android
media_books: []
draft: true
status: evergreen
---

上个月，Google 发布了一项更新。现在你可以在手机上长按电源键，对
Gemini 说一句话——“帮我看一下 Gmail
里那封课程邮件，把里面列的书加到购物车”——然后看着它自己打开邮件、提取书单、找到对应的商品、逐一加入购物车。

这篇文章想讨论的不是这个功能本身。我想讲一个更底层的对比：为什么这件事
OpenAI 做不了，Anthropic 做不了，只有 Google
能做。答案和模型质量没什么关系。

## 让 AI
操作另一个应用，有三种办法

任何一个 AI 系统想要跨应用干活，本质上都要解决同一个问题：怎么让 AI
碰到另一个应用里的数据？

有三种办法。从上往下，效果越来越差，代价越来越高。

办法一：操作系统层的直接调用。 Gemini 是 Android
的一部分，就像通知系统或相机一样。它不需要你额外授权就能读写你的
Gmail，不需要单独登录就能查你的
Calendar。这些权限在系统设计的时候就留好了。

办法二：给每个服务单独建一个 Connector。 这是 OpenAI
和 Anthropic 的做法。Slack 建一个，GitHub 建一个，Google Drive
再建一个。每个 Connector 都是一条独立的工程管线：注册开发者账号、配
OAuth、管 token 过期、处理 rate
limit。每接一个新服务，几百行代码，一套独立的认证体系。

办法三：模拟人类操作 GUI。
当服务既不给系统权限，也不给 API
的时候，你只能截屏、识别按钮在哪里、模拟点击、再截屏确认做对了没有。每一步都是一轮截图加推理，速度慢；界面布局一改位置就错；每多一步操作就多烧一轮
token。

这三个办法的效率差得很大。办法三比办法二慢一个数量级，办法二比办法一慢一个数量级。而办法一的接入成本接近于零——不需要每个服务单独去申请权限。

Google 能走办法一。OpenAI 和 Anthropic 困在办法二和办法三。

## 建 Connector 的真实代价

OpenAI Codex 和 Claude Code 有丰富的 Connector 生态。但每个 Connector
是互相独立的。AI 想同时查 Gmail、读 Calendar、在 Slack
发消息——它要分别调三个 Connector，每个都要单独确认登录没过期。

这不是谁实现得不好。任何不运行在操作系统里的
AI，都必须一个一个服务地去敲门。

而且敲门有两个前提，都不由敲门的人控制。

第一个前提：门后有锁孔。很多服务根本不暴露 API。Concur
不让你写入费用报告，你就没法自动报销。Bloomberg 有
API，年费两万五千美元起。你能做的只剩下逆向工程，有法律风险，对方一更新你的方案就失效。

第二个前提：有人得去配钥匙。大多数老牌公司不会为了 AI agent 专门建
Connector。微软自己的 Copilot connector 做了很久，而且 personal account
的用户根本不能用——必须 enterprise。

你能让 AI 操作多少服务，不取决于你的 AI
多聪明。取决于两个你说了不算的条件：对方有没有留接口，以及有没有人去适配。

在这一层，Google 和你处境差不多。它也得建 Connector，也要处理 token
过期。Google 的优势只在于体量大，服务商更愿意主动帮它做。

但办法一完全不一样。

## 适配逃不掉，但谁来做差很多

办法一也不是零成本的。Gemini 要在 DoorDash 下单，DoorDash
也得在自己的 app 里实现对应的调用接口。Google 把这套接口叫做 AppFunctions。开发者写几行注解标记自己暴露的功能，系统自动注册，Gemini
在需要时调用。

适配这件事，谁都逃不掉。不管你是 Google 还是 OpenAI，想让 AI 操作
Uber，Uber 总得提供一个入口。

差别在于，谁能推动开发者去做这件事。

Google 可以给 Android 开发者群发邮件：“下一个 Android
版本有个平台级功能叫 Gemini Intelligence。实现这套接口，你的 app 就能被
AI 直接调用。不实现，你的竞品会实现。”开发者有动力配合——不是因为 Google
的文档写得好，而是因为 Google 决定了这个平台的准入标准。

OpenAI 发同样的邮件效果完全不同。“请接入我们的 Connector
协议。”开发者会问：“为什么？我的用户又不会因为这个多下载我的 app。”

平台持有者的要求，和第三方 AI 公司的请求，说服力差了几个数量级。

## 沙盒保护了用户，顺便也保护了
Google

这个位置还有一个副产品。

Android
的安全模型规定，普通应用不能读取其他应用的屏幕内容，不能拦截其他应用的操作。这些限制有充分的正当理由——防恶意软件偷照片、防木马读银行短信。

但同一个规则，对 Google 自己不适用。Gemini
是系统组件，不在限制范围之内。ChatGPT 是从 Play Store
下载的普通应用，必须遵守全部限制。

这就是为什么 Android
Headlines 今年 4 月报道的欧盟 DMA 裁决如此重要。欧盟正在要求 Google
允许 ChatGPT、Claude 等获得与 Gemini
相同的系统级权限，包括自定义唤醒词和应用控制能力。如果裁决通过，长按电源键这个入口可能要对
ChatGPT 开放。

目前，DMA 尚未裁决。

## 模型军备竞赛不是主战场

年初在 Manus 的分析里，我把
AI
产品的优势归为三类复利：工具、数据、智能。我当时说工具复利最容易被复制，不构成护城河。

这个判断在应用层是对的。多写一个 API connector，成本不高。

但在操作系统层，多加一个工具的壁垒不是工程，是谁拥有这个系统。你不拥有
Android，就永远拿不到那种不需要建
Connector、不需要单独授权、系统默认就通的接口。这是开关，不是多一点少一点的区别。要么有，要么没有。

所以 AI OS 的竞争里，模型质量可能不是决定性的。OpenAI 在 benchmark
上领先，Google 可以用 Gemini 3.1 追赶。但一个能用十五个系统级工具的
AI，和一个只能用浏览器加 Python 的
AI——即使后者的推理能力强一个档次，交付的体验也很难追平。

Google
首批只开放了外卖、打车和生鲜配送，不是因为技术上只能做到这些。开头那个
Gmail 提取书单加购物车的 demo
已经证明远不止于此。首批选这三个类别，是因为阻力最小——Uber 和 DoorDash
本来就需要外部流量，被 Gemini 调用不威胁它们的核心生意。Google
在一步步试。

三十年来，操作系统的职责是管硬件。未来的操作系统要多管一件事：用户接下来想做什么，哪些应用能帮忙完成。调度的东西变了，但权力的来源没变——谁控制底层，谁定规则。

Humane 的 AI Pin 和 Rabbit 的 R1 也看到了这个方向。它们失败不是因为
AI 不行——AI Pin 用了
GPT-4。它们没有的是一个已经在几十亿台设备上运行的、有几百万应用的、掌握所有底层权限的操作系统。

回到长按电源键。Google 知道用户不满——Pixel
官方论坛上 1,665
人要电源键回来。但它坚持。因为电源键是用户拿起手机后碰到的第一个东西。它在屏幕亮起之前，在应用图标出现之前。谁占了这个位置，谁就第一个知道用户要做什么。

Google 决定挨骂值得。