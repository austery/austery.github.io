---
layout: post.njk
source: https://blog.qiaomu.ai/kimi-k3-review
speaker: 向阳乔木
title: Kimi K3实测，让我不敢相信这是国产模型 · 乔木博客
date: '2026-07-15'
summary: 本文对国产模型 Kimi K3 的实测体验进行了深度评测，作者发现其在代码开发、项目落地（如构建网站、iOS App、3D 游戏复刻）以及 AI 工具链集成方面表现超预期。Kimi K3 在处理复杂任务时展现出强大的能力，甚至在某些工程实践中超越了同类模型，为国产大模型带来了新的信心。
area: tech-engineering
category: ai-application
tags:
  - model-comparison
  - software-development
  - project-automation
  - skill-creation
people:
  - 向阳乔木
companies_orgs: []
products_models:
  - Kimi K3
media_books: []
draft: true
status: evergreen
---

Kimi K3实测，让我不敢相信这是国产模型 · 乔木博客

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# Kimi K3实测，让我不敢相信这是国产模型

AI工具

·

2026年7月15日

·

442 次阅读

·

约 12 分钟

© 2026

·

向阳乔木

一直用 Codex 和 Claude Code，测了 Kimi K3 后，竟有超预期惊喜，真的是强！

刚用时，不了解情况，只敢给一些简单任务，后面越用越牛逼。

后面直接给了 Kimi K3 服务器权限，一口气开发了 6 个完整项目，全部上线、免费开源。

项目覆盖前端、后端构架/数据库开发、AI 模型调用，本地已有项目优化迭代。

全都是一轮对话搞定 MVP，2-5 轮对话完成打磨、发布上线。

毫不夸张，Kimi K3 是国产模型巨大飞跃，能力直逼 Fable 5。

让大家有底气，再也不怕 A➗ 封号。

现在唯一担心，Kimi 是否备足了 GPU ，预计马上会有海量国内外用户涌入。

下面，乔帮主会先展示、后拆解，全部提示词、Skill、源码都会开源给大家，建议先收藏再看。

## 开发项目演示（部分）

今晚看啥：自然语言对话找片的网站，基于开源OMDB数据库，实时AI检索推荐，在线跳流媒体平台看片。

> https://imdb.qiaomu.ai/

X-follow：调用第三方 xAPI，跟踪推特 KOL 最新信息，中文对照翻译，一个人免打扰刷推。

> https://x.qiaomu.ai/

Mastermind：给女儿做的益智 3D 游戏，复刻自 Switch ，增加得分排行榜，高难模式。

> https://mastermind.qiaomu.ai/

arXiv 论文搜索下载：每日精选 AI 论文，一键下载 PDF 与在线阅读，支持 AI 解读，自然语言对话找论文。

> https://arxiv.qiaomu.ai/

初中数学公式可视化学习：给儿子开发的数学公式学习工具，秒懂勾股定理。

> https://math.qiaomu.ai/

乔木提词器 iOS App 优化：找出 App 性能和交互问题，重新编译优化。

乔木 Gif 压缩 Skill：把任意录屏 Gif 压缩到能插入公众号文章的帧率、尺寸大小。

> 安装指令：npx skills add joeseesun/qiaomu-tiny-gif

## 项目解读

### IMDB 电影 AI 搜索

一般视频网站都只支持电影名搜索，不知道名称就不好找片子。

我想能不能用 AI 帮推荐电影，实时检索 IMDB 库展示，最好还能在线看。

网上找到一个免费 IMDB 数据库叫 OMDB ，能免费申请 API，也可每月赞助 1 美元，获得每天 1w 次调用。

> http://www.omdbapi.com/

把 API key和文档发给 Kimi K3，要求调乔木 AI PRD Skill 和 LLM Skill、网站部署Skill，写产品方案并开发上线。

执行中激活了所有要求的 Skill，思考 58 次，调用了 82 次工具。

先搭后端 sqlite 数据库，后写前端页面，甚至设计了 favicon 和 OG图，让网站看起来更正式、专业。

AI 全自动测试，很像一个人在喃喃自语，比如：“首页感觉对了。看结果页和详情弹窗”。

测试通过后上线，调用了 Vercel cli 部署， Cloudflare 解析绑定了域名。

全过程我没有做任何干预，一个完整网站就开发上线了。

后续还有两轮对话，我仅补了详情页观影地址和100个轮播提示，一次性全搞定。

最后，大家注意看页面顶部背景，竟然是用 OMDB 返回的电影海报封面拼接做的背景，前端审美果然是 Kimi 传统强项。

### iOS App 乔木提词器

Kimi K3 开发前后端优秀，为了更全面测试，我直接把之前写的iOS应用Github仓库给它，让它找优化空间。

之前 Swift 代码用 GPT 5.5 开发，它觉得代码质量中上。

但依然找到 5 个高危漏洞，4个性能问题、2个构架问题和不少 UX 问题。

可能它预感工作量大，直接启动了 5 个 Subagent 修复，任务拆分合理，互不干扰。

很快修改完成，编译通过，唤起 iOS 模拟器让我体验。

### Switch 3D 游戏复刻

女儿特别喜欢 Switch 上的《世界游戏大全51》中的猜颜色游戏。

每次选四个颜色，通过反馈信息（颜色和位置是否正确），用最短轮次，给出正确的颜色和顺序排列。

好像也有实体游戏机卖，大概 150 左右，如图：

原来这个游戏叫 mastermind，谷歌搜了下，也有网页版，排名第一的产品如下：

为了视觉效果和可玩性，直接上 3D 版，顺便测模型的 Threejs 建模能力。

流程类似不赘述，只需知道游戏叫 Mastermind，要求用Three.js开发， 让 AI 生成 PRD 后开发。

第一版生成后就能玩，甚至还带音效，但界面需优化。

比如盒子放右侧更直观，要能支持拖拽排序，显示小球的移动轨迹等。

为增加竞争性，要求改成云端数据库，记录每个玩家的最好成绩做排行榜，成品如下：

### Gif 压缩 Skill

个人觉得 Gif 是比视频更容易展示的格式，在公众号中，视频需要点击才能播放。

但公众号有一个限制，Gif 最大为 10M，不能超过 300 帧，帧率要控制在 12 - 20 fps。

本文很多演示 Gif 都超过限制，让 Kimi K3 帮写一个 Gif 压缩 Skill。

10分钟就开发完成，Skill 质量不错，能自动剪掉过长静态帧，在保证画质前提下，降低文件大小。

大家看到的本文 Gif 演示，都用这个 Skill 处理过。

指令安装地址：

> npx skills add joeseesun/qiaomu-tiny-gif

### Grok Build 82 万行代码分析

最近马斯克开源了 Grok Build，大概 82 万行 Rust 代码。

我同时发给 Kimi K3 和 GPT 5.6 sol Ultra 做全量代码分析、挖掘，最后生成飞书文档对比。

K3 竟然把 XOR 混淆的 System Prompt 解密了！文档信息密度极高，挖掘出不少有趣的工程设计。

GPT 5.6 sol 同样完成了任务，粗看标题很厉害，语言更流畅，但仔细读发现内容有点空洞，大家可以对比下。

Kimi K3生成的飞书文档

> https://xiangyangqiaomu.feishu.cn/docx/OAoYdiZ1eoc2HTxmmZ3clWIPnLf

GPT 5.6 sol Ultra生成的文档

> https://xiangyangqiaomu.feishu.cn/docx/WvgKdcEJxo9nJqxExLwcUUiKnPb

##

## 更多项目

AR 3D 眼睛试戴：提示词相当简单，竟然支持webcam摄像头，人脸识别等。

> Build a 3D sunglasses customizer with drag-orbit, PBR material live previews (metal、acetate frames, polarized、mirrored lenses),animated temple-arm fold/unfold, real-time lens tint & reflection adjustment, hinge hover-glow, and a webcam-AR "try on your face" mode with face tracking.

在线体验：

> https://glass.qiaomu.ai/

论文搜索下载学习：arXiv 是最流行的论文预印本发布网站，新 AI 论文一般都会发布到这里，是个学习宝藏。

网站全英文，搜索查找不方便，所以想开发一个中文简化版。

开发这个项目时，已经凌晨1点，给了下面一段提示词：

> 参考 imdb.qiaomu.ai 的代码，开发一个更好用的arxiv网站，列出一些值得看的论文或主题，也可以搜索优质论文，可以一键下载pdf或在线看论文，调用乔木llm中的Deepseek flash v4做AI解读和推荐引擎，网站域名叫 arxiv.qiaomu.ai 用乔木设计skill开发（你选最合适的风格，不要问我），代码开源到github，arXiv的api参考：https://info.arxiv.org/help/api/basics.html#using

第二天醒来，网站开发好了，Github 也上传了，感觉 Kimi K3 长程任务开发也超稳。

顺手补了 2013-2015 年的 50 篇经典 AI 论文，增加了“搜索下载”模块。

UI学习网站：学习前端开发组件名和网页风格，让你的 Vibe Coding 更专业。

一句话让 Kimi K3 生成 40 多种网页组件风格，如新拟态、苹果液态玻璃、极简主义等，每个组件都是独立的HTML + CSS，包在一个网页展示非常直观。

> https://learnui.qiaomu.ai/styles/

## 模型局限

Kimi 官方公告坦诚说了模型的一些问题，再综合一点我的感受和发现：

如果是 API 调用，模型温度 Temperture 参数默认为 1，不能修改。

因训练方式原因，与官方的 Kimi Code 匹配更好，如接入 Claude Code，效果可能会有折损。

K3 模型优化了长程、高难任务，主动性很强；遇到简单、模糊需求，反而会过度思考和发挥，如并非你想要的，需在系统提示词或AGENTS.md 中做约束。

K3 在交互、界面、视觉、空间等相关场景完全可以作为首选模型，但架构、后端等场景，仍落后于最强闭源模型 Claude Fable 5 和 GPT-5.6，感兴趣可以看官方 Benchmark。

更多官方评测图表:

> https://mp.weixin.qq.com/s/V4xhEIy8xDXSMDPrPkmUAQ

## 总结

写到这儿，其实我自己都有点不敢相信。

Kimi K3 这个模型给我的体验，竟然比 GPT 5.5 和 Claude Opus 4.8 还好。

虽然跟最顶级的 Fable、GPT 5.6 sol Ultra还有一点点差距，但体验已经非常接近，非常不可思议。

从前后端开发、数据库、AI 调用，到 iOS 优化、3D 建模、Skill 编写，没有任何一项拉胯。

怪不得 Kimi 会把版本号直接从 2.7 直接升到 3.0，看来团队也相当有信心。

「不怕封号、放心用国产」这件事，真的开始成立了。

国产自研模型，Sonnet 级价格、Opus 级体验！我怕真的买不到会员了

按惯例，本文提到的全部项目、提示词、Skill 和源码，我都会开源出来。

链接会整理在评论区，欢迎自取、欢迎折腾。

如果这篇文章对你有帮助，点个「在看」、转发给需要的朋友，就是对乔帮主最大的支持，我们下次见。