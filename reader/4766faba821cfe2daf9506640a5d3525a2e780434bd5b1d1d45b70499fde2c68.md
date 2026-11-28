---
layout: post.njk
source: https://blog.qiaomu.ai/trae-personal-agent-free-trial
web_feed:
  articleId: cmvzw5pyl001g9eye6ruan3iw
  feedSourceId: cmoynk2ty0000yeud307bv9ji
  guid: https://blog.qiaomu.ai/trae-personal-agent-free-trial
  sourceUrl: https://blog.qiaomu.ai/trae-personal-agent-free-trial
speaker: 向阳乔木
title: TRAE 个人助理限免一周，实测感觉编程PA时代来了！ · 乔木博客
date: '2026-11-02'
summary: 文章介绍了 TRAE 个人助理（Personal Agent）推出的新功能，旨在解决 AI Agent 在单次会话中的局限性，使其能够长期运行、跨平台保持上下文并并行推进任务。该助理具备全局助理和项目专属助理两种模式，能够理解用户对项目的需求，支持跨项目并行开发，并能通过智能调度和任务拆分，让用户从忙碌的调度员转变为做判断的人。作者认为，这标志着编程PA（Personal Agent）时代到来，解决了AI Coding中“会不会写”到“持续理解开发工作”的瓶颈。
area: tech-engineering
category: ai-application
tags:
  - personal-agent
  - ai-tooling
  - ai-workflow
  - software-development
  - ai-coding
people:
  - 向阳乔木
companies_orgs:
  - OpenAI
  - DeepSeek
products_models:
  - TRAE
media_books: []
draft: true
status: evergreen
---

TRAE 个人助理限免一周，实测感觉编程PA时代来了！ · 乔木博客

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# TRAE 个人助理限免一周，实测感觉编程PA时代来了！

AI工具

·

2026年11月2日

·

69 次阅读

·

约 7 分钟

© 2026

·

向阳乔木

AI Agent 的下一个瓶颈，就是人类自己。

AI 能够同时完成的任务越来越多，人类管理这些任务的注意力却没有同步增长。

给大家看下我的 Codex 项目，每次想找到某个项目迭代，都要翻好久。

OpenAI 推出 Dots 后可缓解这个问题，但目前优化的不好，项目会话能轻松搞定的事，Dots 反而搞不定。

为啥不能通过一个主 Agent 实现所有项目的管理开发？

DeepSeek 团队最近提出Super-agent 构架，也是来源于类似观察。

人注意力相当有限，通常只能跟进 3~5 个活跃 Session 。

> https://mp.weixin.qq.com/s/zoS7GlReWPhfCjENGxXCdg

其实，大家都意识到了类似问题。

所以 Grok bot 添加了主 Bot，OpenAI Codex 推出了 Dots，Claude Code 推出了 Duet。

这类工具一般叫 Personal Agent。

最近 TRAE 也推出了专属于开发者的个人助理（Personal Agent）- TRAE 宝。

个人觉得名字不重要，但大家想解决的问题高度一致：

让 Agent 从单次会话中解放出来，成为一个能够长期运行、跨平台保持上下文、并行推进任务的连续实体。

以国内最容易访问的 TRAE 为例，讲讲有了编程 PA 后的新开发体验。

> 官网下载：https://www.trae.cn/

## 全局助理

下载或更新最新版 TRAE 后，“新建任务”下面有个图标叫 “TRAE 宝” 。

这是一个全局 AI 助理，能自定义名字，比如我改名叫“狂暴气息”，点击 2，会展示一个卡片。

可绑定飞书或微信，哪怕不用打开 TRAE ，也可以发起任务。

比如在微信，让它查下我的 Github 仓库的用户反馈。

查询我开发的 Obsidian 插件的下载量。

## 全局助理开发体验

任何任务，只需要跟全局助理说就行，再也不用费劲找项目 Session 对话了。

也不用反复介绍项目背景，它能准确理解你说的是哪个项目，支持跨项目并行开发，聊的越多越懂你。

比如最近，我把喜欢的播客节目都做成了网站，比如张小珺商业访谈录、42 章经、AI 炼金术等。

每个网站都对应了一个项目文件。

之前想迭代，我需要找到项目文件夹，新建会话提需求。

有了编程 Personal Agent 后，我只需跟 TRAE 宝说：

> 42 章经播客网站你觉得还可以加什么功能，让用户体验更好？

它马上就知道我指的是哪个网站项目，启动本地预览开发。

完全不用我从零解释，也不需要复杂的提示词和上下文，像跟一个真人程序员话说感觉一样。

同一个会话中，提多个不同开发任务也不会上下文污染。

比如，先说先让它修 qiaomu-reader 的 Bug，又让它写一个定时任务查 umami 流量统计。

## 项目专属助理

除了全局助理，每个项目也可以创建专属助理。

它面向本地开发任务，更了解上下文，同样支持任务自动拆分执行、跨任务分析，你只需要负责目标和决策，其他都不用操心。既省心，效果又好。

创建方法：新建项目或点击左侧项目名后，默认进入该项目专属的 TRAE 宝对话界面。

拿我的一个 Kindle 开发项目为例，背景是这样：

亚马逊离开中国后， Kindle 国内没了在线书店，下载安装图书变的很不方便。

最近让 AI 把 Kindle 越狱，基于 KOReader 和 SimpleUI 开发一套无线传书和 RSS 阅读系统。

您的浏览器不支持视频播放

越狱后的旧 Kindle 是最好的电子书阅读硬件.mp4

开源地址：https://github.com/joeseesun/qiaomu-simpleui

之前的 Kindle 是十多年前买的 PaperWhite 3，速度稍微有点慢。

所以，我又买了一个二手的 Kindle PaperWhite 5，安装了上面的定制系统后。

我还想给它加上 AI 辅助阅读功能，最好支持流式输出。

先让它搜索最佳实践，输出开发方案，然后执行开发。

为实现 AI 功能，让它参考 qiaomu-clipper ，但这是另一个项目，不在这个项目文件夹中。

它会派出一个 Agent 去执行。

我完全不用关心这个项目路径，Agent 会自动找到、读源代码，并给出学习建议。

随着你开发的产品越来越多，很多功能其实可以复用。

想借鉴时，只需知道项目名称，其他工作都能让项目专属助理去搞定。

完全不用自己拆任务、切会话、盯进度、拼结果。

在一个会话中完成所有工作，这更符合人性，因为“懒是第一生产力”。

另外，仅需关注一个会话，有效减少注意力切换，就能把更多精力放在产品体验设计上。

比如 Kindle 上输入 API key 很麻烦，我跟它讨论出的方案很巧妙：生成一个二维码，手机扫码打开网页配置。

最终实现效果如下。

上面是 TRAE 宝的实际体验，更多 TRAE 的功能介绍：

> https://mp.weixin.qq.com/s/JnGKhOVdltDATbG6o9ueMQ

不过当前版本只支持本地任务（本地设备、本地项目），希望早点开放云端任务和移动端能力。

## 写在后面

我感觉，有了 TRAE 宝后，普通用户的开发体验越来越好了。

非常有“当老板”的爽感：

你只需安排任务，哪怕提供的上下文不全，任务要求颠三倒四。

这个 Personal Agent 都能很好的理解、执行。

AI Coding 前两年解决的是“会不会写”。

现在解决的问题是如何让 AI Agent 持续理解你的开发工作。

一个会话搞定一切，而背后复杂的跨项目记忆与子 Agent 调度，你都不用操心。

让你从忙碌的调度员，变回做判断的那个人。

BTW：这个新功能从 10 月 29 日开始限免一周。

所有从 TRAE 宝入口发起的任务全免费，抓紧时间蹬啊，朋友们。