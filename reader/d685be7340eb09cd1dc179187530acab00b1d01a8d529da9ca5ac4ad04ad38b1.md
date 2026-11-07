---
author: AI超元域
date: '2025-11-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=i1WotgP_VSI
speaker: AI超元域
tags:
  - browser-automation
  - ai-agents
  - large-language-models
  - chrome-extension
  - ai-performance
title: 🚀Opus 4.5+Claude for Chrome彻底改写浏览器自动化！效果碾压ChatGPT Atlas，一个插件取代整个浏览器！让AI自动操作网页、填表格、生成图像，效率倍增！
summary: 本文介绍了Anthropic最新发布的旗舰模型Cloud Ops 4.5及其Chrome扩展插件Cloud for Chrome。该模型拥有200K上下文窗口，效率提升76%，并支持浏览器自动化。视频详细测试了该插件在总结文章、解读图像、翻译文本、发布内容到X平台、模拟多Agent对话、下国际象棋、使用Google AI Studio开发游戏（出现内存泄露）、抓取股票数据填表以及通过Gemini生成图像等方面的能力。结果表明，该插件功能强大，操作流畅，能显著提升浏览器自动化效率，并可能取代ChatGPT的Atlas浏览器，提供更无缝的Chrome集成体验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
products_models:
  - Cloud Ops 4.5
  - Cloud for Chrome
  - ChatGPT
  - Atlas browser
  - Gemini
  - Nano Banana Pro
  - GPT 5.1
  - Gemini 3
media_books: []
status: evergreen
---
今天凌晨，Anthropic发布了其最新的旗舰模型Cloud Ops 4.5。这款模型拥有高达200K的上下文窗口，并在执行相同任务时，相比其他模型效率提升了76%。此次发布不仅包括Ops 4.5模型本身，Anthropic还对Cloud Code进行了更新，默认模型已改为Ops 4.5。更重要的是，他们推出了一项名为Cloud for Chrome的重要功能——一个专门针对Chrome浏览器的扩展插件。这款插件能够实现真正的浏览器自动化，甚至有望替代ChatGPT的Atlas浏览器。

本期视频将重点测试这款模型的浏览器自动化能力。首先，我们来询问一下这款模型的知识库截止日期。直接输入：“你的知识库截止日期是什么时候？”，然后发送。模型回答其知识库截止日期为2025年5月底，这相比Cloud系列的其他模型是最新的，甚至比GPT 5.1以及Gemini 3的知识库还要新。

接下来，我们开始测试这款模型的浏览器自动化能力，以评估其能否取代OpenAI的Atlas浏览器。不同于Atlas浏览器基于Chromium的二次开发，Anthropic直接开发了一款Chrome浏览器插件。我们可以通过点击按钮跳转到扩展插件的安装页面并进行安装。安装完成后，点击插件图标即可打开Cloud的扩展插件侧边栏，这与OpenAI的Atlas浏览器侧边栏非常相似。

插件界面包含一个输入框用于对话，以及两个执行选项：一是执行任务前先询问，二是让模型全自动执行任务。在此，我们选择第二个选项，让模型全自动执行任务。插件还提供了截图、添加/上传图像的功能。

### 内容总结与图像解读
首先，我们让模型总结Anthropic官方发布的关于CloudOps 4.5的文章。输入提示词：“总结这篇文章”。模型开始输出总结，内容包括标题、简介、核心亮点，如定价、效率提升、技术评估和安全性等方面，总结得相当不错。

接着，我们测试其视觉能力，看它能否直接读取网页上的图像。输入提示词：“解读当前图中的内容”。模型立即出现了图像的图标，并开始解读：“这是软件工程性能基准测试的柱状图”。它还给出了图中的排名参数，显示OPS4.5排名第一，并进行了详细解读，说明该模型明显领先，并与竞品进行了对比。这表明模型能轻松获取网页上的图像信息。

### 内容抓取与翻译
我们进一步测试其获取选中内容的能力。选中一段文字后，输入提示词：“将选中的内容翻译为中文”。模型通过截图的方式获取了选中的内容，并提供了中文翻译。这对于AI驱动的浏览器来说，是一个非常重要的功能。

### 自动化发布到X平台
接下来，我们测试其浏览器自动化能力，让它改写这篇文章并发布到X平台。输入提示词：“将这篇文章改写并发布到X平台”，然后点击发送。模型很快给出了改写结果，并询问是否发布。我们输入“希望发布”，模型便直接打开了X平台，定位到文章输入框，并输入了文章内容及标签。与Atlas浏览器不同的是，Cloud Ops 4.5插件能自动点击发布按钮，这大大简化了浏览器自动化操作的流程，提高了便利性。

### 多Agent对话模拟
现在，我们加大难度，让模型与ChatGPT进行交流。输入提示词：“打开ChatGPT，探讨人类什么时候可以载人飞往半人马座阿尔法星”。模型能够直接与ChatGPT进行交互。它向ChatGPT提出了一个多角度分析的问题：“人类什么时候可以实现在人飞往半人马座α星？请从技术发展、推进系统、生命维持、能源需求等多个角度分析这个问题。”ChatGPT给出了详细的回答。

随后，我们观察Ops 4.5能否根据ChatGPT的回答继续进行探讨。Ops 4.5在输入框中继续输入内容，表示“你的分析非常全面，我需要追问下面几个问题”。ChatGPT根据追问给出了回答。Ops 4.5继续追问：“到达阿尔法星后，人类发现宜居星的概率有多大？”ChatGPT给出了回答。Ops 4.5没有继续追问，而是输出了总结，称这是一次全面深入的讨论，并给出了各轮回答的核心分析。这个过程模拟了多Agent的对话，效果相当不错。

### 自动国际象棋对弈
接下来，我们测试其自动下国际象棋的能力。输入提示词：“打开国际象棋网站，让他全自动下象棋”。模型自动打开了国际象棋网站，并开始设置棋局，然后准确地选择棋子并进行移动。为了节省时间，我们点击了“stop cloud”。下棋步骤准确，效果优于之前测试的OpenAI Atlas浏览器。

### Google AI Studio游戏开发与评估（附带问题）
我们进一步加大难度，让模型打开Google AI Studio，并根据其想法开发一个简单有趣的游戏或应用，然后进行评判和修改。模型打开了Google AI Studio，并输入了英文提示词：“Create a fun memory matching card game with a cute emoji on the back of each card. Players can flip two cards at a time to find matching pairs. Successful matches trigger celebratory effects, and completion results in a victory animation. The overall design should be colorful and engaging.” AS Studio完成了游戏开发。模型自动点击游戏进行测试，但随后发现游戏出现了内存泄漏，导致电脑温度持续飙升，不得不关闭任务。

### 表格自动化操作与数据提取
由于上一个任务中Google AI Studio开发的游戏出现了内存泄漏，我们更换题目进行测试，专注于表格操作能力。完整的提示词是：“搜索特斯拉股票，抽取这三个字段，打开谷歌表格并填入内容，最后给出汇报”。

模型新开标签页，打开谷歌浏览器搜索了特斯拉股票，并进入了Google Finance。它在同一个绘画中能够操作多个浏览器标签页。模型正在表格中自动输入内容，速度非常快，自动化操作谷歌表格的能力很强。但在此过程中，它将日期“2024年11月24号”误填为“2025年11月24号”，虽然抓取页面内容准确，但填写的表格过于简单，未设计表头。

### Gemini图像生成与评估
最后，我们加大难度，让模型打开Gemini，选择Nano Banana Pro，并生成一张素描风格的小猫晒太阳的图像，同时对图像效果进行评估。模型成功打开了Gemini，并选择了Gemini的图像创作功能（Nano Banana Pro）。它自动输入了英文提示词，并点击了发送。Gemini开始生成图像，Nano Banana生成了一张素描风格的晒太阳的小猫图像。模型自动点击图像进行放大，以便清晰查看，然后给出了对图像的分析。分析结果包括任务完成情况、图像评分（10分制打9分）、优点（如素描风格准确、主题表达到位、阳光效果出色），以及细节评判和建议。总结认为图像非常出色，完全符合要求，艺术质量高，细节丰富。

### 总结与对比
通过以上几个具有代表性的浏览器自动化测试，我们可以发现这款插件效果非常不错。它甚至可以完全取代ChatGPT的Atlas浏览器。这样一来，我们就不需要从熟悉的Chrome浏览器切换到Atlas浏览器，因为Atlas浏览器虽然是基于Chromium二次开发，但其使用方式和习惯与Chrome仍有一定区别。而Chrome浏览器中，我们只需安装一个浏览器扩展插件，即可使用Cloud进行网页总结、翻译、分析，甚至实现浏览器自动化操作。Atlas浏览器具备的功能，这款扩展插件同样拥有。