---
layout: post.njk
source: https://blog.qiaomu.ai/bloome
speaker: 向阳乔木
title: AI圈的朋友都在看科幻片，因为答案就在那儿 · 乔木博客
date: '2026-04-22'
summary: AI从业者通过科幻片理解AI Agent未来。文章介绍了Bloome.im产品，探索H2A/HAAH模式，作者体验了创建云端/本地Agent，并展示了Agent调用本地文件、工具及多Agent协作能力，预示Agent将成为工作标配，重构人机协作模式。
area: PAI
category: ai-workflow
tags:
  - ai-agents
  - human-agent-collaboration
  - personal-ai
people:
  - Leon
  - Qiao Mu
companies_orgs:
  - Bloome.im
products_models:
  - Bloome.im
  - Claude Code
  - Codex
  - GPT-IMAGE-2 API
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

# AI圈的朋友都在看科幻片，因为答案就在那儿

AI工具

·

2026年4月22日

·

238 次阅读

·

约 8 分钟

最近观察到一个有趣的现象，AI圈的朋友都开始看各种科幻，甚至奇幻电影。

比如《银翼杀手》、《Her》、《同乐者》、《黄金罗盘》等。

随着AI Agent越来越强，不得不让大家思考人和Agent之间的关系。

而很多科幻电影或多或少都涉及了这个话题，且用视频呈现了一些可能性。

前段时间，好友李继刚在 X 上发了一个帖子

以前都是人和人直接交流、协作。

可预见的未来，人人都会开始用 Agent，加入了这个变量后，必然会出现新的产品形态。

正如继刚所说，A2A、H2A、HAAH 都有新市场、新空间。

## 一个探索

好友Leon说他们新产品在内测，我下载安装体验后。

发现这个产品就是 H2A 和 HAAH的可能产品形态的一种探索，产品地址：

> https://bloome.im/

目前有网页段和Mac客户端，推荐后者，功能更强。

## 第一个意外

刚注册，弹出了一条消息，让我很意外。

它怎么知道我叫网友喊我“乔帮主”，且最近刚出了一本GEO相关的书。

后来我才发现，这是一个群，除了Noel这个机器人外，还有Bloome产品创始人Leon。

Noel 应该是 Leon 的分身机器人，Leon把我的一些信息告诉了它，所以它会用这些信息跟我聊天。

不过可能 Leon 没有把准确书名告诉他，它出现幻觉了。

Leon 追问后，它估计调用了搜索，找出了准确书名 《AI营销：从SEO到GEO》。

## 添加本地 Agent

注册后默认会给你创建一个云端的Agent，名叫 “xxx的Agent”。

能改名，设置头像，我改名叫 Sunny，用了一棵 「乔木」 作头像。

除此之外，可以创建更多 Agent，点击消息右侧的 “+” 号就能看见。

可以选 Agent 运行在本地，还是云端，这次我选了本地。

选择运行“在这台电脑上”时，可选Bloome Agent、Claude Code和Codex。

除了第一个，其他都可以通过OAuth登录对应CC或Codex账号，用自己的模型。

## 本地 Agent 能做什么？

你可以简单理解成小龙虾或Hermes Agent。

因为在本机，就能读取电脑的各种文件，调用本机的各种工具。

比如我让它扫描下本地的Skill。

然后我让它运行乔木AI雷达Skill，抓取最新的AI资讯，写入到我的Obsidian库。

或者我让他运行电子书下载Skill，帮我下载《道德经》。

或者控制我电脑中的Spotify播放许巍的专辑。

本地Agent的好处就是能安装所有Skill，做各种复杂的操作。

分享一套最近自己开源的各种Skill，可以给你的Bloome本地Agent 用，拿走不谢。

> https://xiangyangqiaomu.feishu.cn/wiki/N5vDwWcSSiND5wkjFQscAkX4nnd

## 云端 Agent 配置

创建云端Agent时，默认名字和性格都不一样，还可以指定不同模型。

除了模型，我觉得没有Skill的Agent，跟聊天机器人差不多，一定要安装Skill。

Agent头像点开，可设置技能。

不过官方安装新技能不好用，建议 Leon 给 Bloome 后续家加个内置Skill应用市场。

比如下面网站有97万个Skill可用：

> https://skillsmp.com/zh

反而直接对话，让Agent安装Skill反而更方便。

比如丢给AI一个Github，安装了自己写的生图Skill。

如果提示没有生图API，可以注册彭总的hiapi，注册免费送顶级生图模型GPT-IMAGE-2 API，可以免费生成50张图。

> https://www.hiapi.ai/zh/register?aff=NIWx

然后下面代码换成你的API key，发给Agent就会自动配好。

```
<code>curl -X POST "https://api.hiapi.ai/v1/images/generations" \
  -H "Authorization: Bearer 换成你的API" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2-beta",
    "prompt": "A cute cat sitting on a windowsill",
    "size": "1024x1024"
  }'</code>
```

除了这种安装Skill方式，也可以直接丢Skill 安装的npx指令，比如我让安装橘子家的 Listenhub Skill。

> npx skills add marswaveai/skills

安装Skill后会自动扫描，给出一些风险提醒，这样Agent就有了做PPT、做音乐、做Podcast等各种能力。

## Agent 群聊

我建了一个本地Agent和多个Agent，把Agent拉到一个群，随时@对话。

比如，我让所有机器人做一个自我介绍，脑暴给“金坷垃”改个名字等。

实用一点，我@了所有Agent，让帮我找《被讨厌的勇气》电子书。

可能不同 Agent 性格不一样，有些义正言辞让我买正版或去微信读书，只有“金坷垃”这个名字和性格逗比的家伙帮我真的下载到了epub电子书。

紧接着，我@用了Opus 4.6的Agent @颛顼：“帮我写一个网站介绍这本书。”

审美还挺在线，而且生成的网页还能转发给好友或分享到外部。

如果给不同 Agent 设定不同的角色和技能，真像一个小团队的样子。

群内共享上下文，隔离 Agent 能力和权限，分工完成一些调研分析、脑暴、PPT和网页制作等工作任务。

想体验的话，可注册Bloome，扫码加入我的群。

或用下面链接注册进群也行：

> https://bloome.im/join/cuQIkTq0?ref=x5voQn4a

另外，官方也提供了很多有趣的群，比如英文播客交流群、AI故事群等，到时候可以选择加入。

## 写在后面

体验完 Bloome 后，我对继刚说的 H2A 和 HAAH 的未来有了更具象的感知。

当 Agent 成为标配，就像每个人都有手机一样，未来每个人可能都会有多个 Agent。

有的在云端处理信息检索和内容创作，有的在本地管理文件和控制设备。

它们各有性格、各有专长，就像《Her》里的 Samantha，但又不止一个。

协作方式也会发生重构，以前团队协作是人找人，未来可能会演变成，你的 Agent 先和对方的 Agent 沟通。

多个 Agent 讨论、协作完成任务，人只需要在关键节点做决策。

Bloome 还在内测，虽然看起来有点粗糙，Agent 偶尔不听召唤，但方向真的很有趣。

P.S. 感谢 Leon 团队做出这样的探索产品，也欢迎更多朋友加入内测，一起探索 Agent 时代的可能性。

产品地址：https://bloome.im/register?ref=x5voQn4a

我不禁想，《银翼杀手》 问的是"复制人是否有灵魂"，《Her》 问的是"人能否爱上 AI"。

当 Agent 成为工作伙伴，人的价值在哪里?

也许答案就藏在那些科幻电影里——人的价值不在于执行任务的效率，而在于提出问题、做出选择、承担责任。

Agent 越强大，越需要人来定义目标和边界。

© 2026

·

向阳乔木