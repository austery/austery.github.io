---
layout: post.njk
source: https://blog.qiaomu.ai/killing-software-with-ai-agents
speaker: 向阳乔木
title: 9人团队跑900个Agent，这款产品想让软件消失 · 乔木博客
date: '2026-05-12'
summary: 本文介绍9人团队Afk.Inc推出的Bridge产品，旨在成为“意念与完成的桥梁”。通过自进化Agent自主调度任务，实现跨平台操作，致力于革新现有软件交互模式，推动“软件消失”的Agent-native时代。
area: tech-engineering
category: ai-application
tags:
  - ai-agent
  - agent-native
  - autonomous-agent
  - infrastructure
people:
  - Enther
companies_orgs:
  - Afk.Inc
products_models:
  - Bridge
  - Affine
  - Willow
  - Droppass
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

# 9人团队跑900个Agent，这款产品想让软件消失

播客解读

·

2026年5月12日

·

22 次阅读

·

约 9 分钟

一个95后天体物理学家，从马普引力物理研究所出来，没去追引力波，跑去 Palo Alto 做 AI 了。

他叫 Enther，1997年生，公司叫 Afk.Inc——Away from Keyboard。9个人，跑着900个 agent。第一款产品 Bridge，今天正式发布。

在这之前，他做过 Affine，700万用户，Product Hunt 年度第四。然后在巅峰期亲手砍掉它。

他的判断只有一句话：AI 正在消灭软件。与其等着被颠覆，不如自己来。

## 从 Affine 到 Bridge，一次主动的自我颠覆

Affine 是一个协作工具，也是 AI 协同知识库里 star 最多的开源项目。Enther 在里面花了很长时

间，研究人与人、人与 AI 应该如何协作。

但他逐渐看清了一件事。

AI 本身会重新发明和定义软件。它不会跟任何现有软件好好相处。 就像 iOS 干掉塞班，不是改良，是替代。继续做一个"限制 AI 的脚手架"，迟早是死路。

于是他把 Affine 砍了，从头开始做 Bridge。

逻辑很清晰：与其做工具，不如做 AI 本身。与其做软件，不如做消灭软件的软件。

## Bridge 到底是什么

官方 slogan 是 Bridge intent and done，意念与完成之间的桥。

用更直白的话说：你想干什么，就告诉它，它就去干完。 你不需要知道用什么工具、装什么软件、配什么 API。

最让 Enther 骄傲的功能叫 Books。

你可以一句话复刻任意 AI 应用。比如，做一个动态生成剧情的游戏，或者把你读过的小说自动变成漫画，再一键部署成网站。视频模型、API、token、环境，什么都不用你配。

他们团队内部有个群叫 demos，每天看 Bridge 能整出什么活。Runway 说他们能让 AI 跟人视频开会，他们直接把链接扔给 Bridge，one-shot 复刻了一个。

另一个设计叫 Notch，给 macOS 做的灵动岛。当 agent 并发跑多个任务时，无论你切到哪个屏幕，顶部都有进度条，告诉你它每一步在干嘛。动画是一帧一帧抠出来的。

核心理念只有一个：少打扰。 AI 干活的时候，不要影响你的 vibe，你可以去跳舞。

## 内测两个月，用户整出了什么活

Bridge 4月启动了首批200位用户的内测。Enther 说，每天都被震惊。

有人让 Bridge 做了一个 AI 和自己打德州扑克的游戏，会互喷、互相 bluff。

有位半导体工程师，用某种很旧的、没有 API 的芯片仿真平台，Enther 说他一眼都看不懂那个东西，但 Bridge 就能替工程师操作那个平台干活。

最夸张的是一位设计师。他为了看 3D 狗狗，用 Bridge 做了一个 2D 转 3D 的"3D 相片"，输入一张照片，它会随人的视角运动，完全本地运行。而且 Bridge 在构建过程中，甚至给他训练了一个专门检测景深和人脸位置的模型。

还有个用户把账号密码给了 Bridge，让它去退机票。Enther 本来觉得 trip.com 很麻烦，没想到扯皮几轮之后，票真的退了。

这件事直接催生了一个新产品 Droppass——替你输密码，端到端加密，Bridge 也看不到。

## 三个技术难点，和一套叫 Willow 的基建

Bridge 背后的技术门槛，Enther 说"非常大"。

第一个难点是沙箱。 AI 误删文件或改错东西时，需要一个比 Git 更适合普通人的版本控制系统。他们做了可备份、可回滚的沙箱。即便你在本地使用 Bridge、操作本地文件，也是先起沙箱、备份，然后可以回滚任意操作。

"去年看到 computer use 的时候觉得太吓人了，它可以把我电脑删干净。人类操作系统有 ctrl+z、回收站，但 agent 的 CLI 里一概没有。"

第二个难点是多环境调度。 AI 既可以用云上的浏览器访问 Gmail、Notion、Linear，也可以直接操作你的本地电脑。他们做了一个 Environment Orchestrating System，让 agent 统一调度本地和云端。

第三个难点是模型的自进化训练。 多模型已经是必选项，但不同模型各有脾气。GPT 干活很强，但跟人说话黑话连篇，体验不友好。他们的解法是反其道而行：先训练一个专门负责聊天、人格化的秘书 agent，由它去调度 GPT、Gemini、Claude、DeepSeek 做不同领域的任务。

在基础设施层面，他们自建了一套叫 Willow 的方案。比基于 k8s 的沙箱集群快两个数量级以上，而且更经济。

Enther 的判断是：Agent 访问互联网基础设施的效率与频率，将超过人类的一百万倍。但今天的 infra 还是为人类设计的。 想做 agent-native，就得自己搞。

## 比 OpenClaw 更早，但没敢发

这是 Enther 复盘时提到的一段遗憾。

去年12月，他们比 OpenClaw（龙虾）更早做出了 proactive agent，cron job 加 soul，人格化的主动任务。但当时跟别人讲，没人听得懂。

"你说「温度高了自动开空调」，大家就觉得「不就是定时发消息吗？」有劲儿使不出的感觉。"

然后2月，一个完成度只有他们50%的产品 OpenClaw 突然爆了。大厂疯狂抄，海量投广告，一夜之间大家对 agent 的观感从"好酷"变成"不过如此"。

教训只有一条：不要和同行还有投资人聊太多，大家看得多用得少，信息茧房太严重。 实际用的人和天天看的人，是脱节的。

KOL 们看 proactive agent 都腻了，但大多数人其实还配不明白这个虾那个虾。这恰恰说明 personal agent 的 killer app 还没出现。

"但这一次，我们不会等别人替我们爆了。"

## 9个人，900个 agent，怎么撑起来的

团队9人，6位工程师，其中两位是 designer engineer。核心成员来自 Deno、Vercel、字节、Google、OpenAI。

每个人 own 一个大的切面：infra、agent framework、大前端。基本上没有一个功能需要两个人。

更有意思的是他们内部的协作方式。

他们把 Codex bot 接到 Bridge 里，在 Slack 里 @ 它聊天。结果生产力暴增。Enther 发现，Agent Engineer 到了群聊里变成很好的胶水角色——它激发了人类协作。

产品设计师和研发对齐通常很难，但 AI 比任何人都能理解两边的语言，大家又很方便随时和它聊，自然形成了"两边一起喷一喷，最后 AI 做出超出两边期待的东西"。

"我经常只需要和大家脑暴时拉上 Bridge，开完会后 @ 它「照着刚刚的搞」，就结束了。真的是 vibe 口喷 working。"

## 5年后，软件会消失成什么样子

Enther 说他已经很少想象5年后了，因为 AI 的发展本身有着加速度。

在可见的一两年里，他希望 Bridge 成为构建、管理与运行 agent 的入口，一个 agent for agents。

"它不会替代操作系统，没必要。它可能有点像十年前的安卓桌面启动器。只不过这次启动的，是动态构建的任何东西。"

对于市场空间，他的判断是数量级级别的。从 web 到移动互联网，门户和电脑应用变成手机 app 商店，2000年 bubble 破灭后，20年疯狂价值创造，万亿级公司从无到有。

这一次，所有习以为常的应用入口都会变成 agent 驱动。 未来每个人有1000个 agent 替他消费10000个手机等效的屏幕时间。

"下一个占据所有人的 personal agent，会出现十万亿美元的公司。"

Bridge 今天正式发布，域名 bridge.surf。

一个天体物理学家，用研究引力波的严谨，在做一件他认为比引力波更重要的事：让人类双手离开键盘。

至于他说的"消灭软件"，听起来像是狂言。但 iOS 干掉塞班的时候，塞班的工程师们大概也觉得，这不可能。

© 2026

·

向阳乔木