---
author: AI超元域
date: '2025-12-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=w69Y36kf3MU
speaker: AI超元域
tags:
  - os-automation
  - browser-automation
  - ai-agents
  - remote-control
  - vnc
title: AI新范式：浏览器自动化赋能操作系统控制
summary: 本视频介绍了一种创新的AI操作系统自动化方法，通过将操作系统映射到浏览器（如使用VNC/RDP），利用“Cloud in Chrome”等工具实现对电脑的精细化操控。演讲者演示了在Ubuntu系统上完成计算器操作、音量调节、命令行编程及软件安装等复杂任务，效果显著优于现有工具。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Ubuntu
products_models:
  - Cloud in Chrome
  - VNC
  - RDP
  - Python
media_books: []
status: evergreen
---
演讲者近期一直在使用各种浏览器自动化工具，例如**OpenIn Browser**、**Cloud in Chrome**以及**Cloud Code**，来处理重复性的浏览器操作。他指出，尽管浏览器自动化功能已日益成熟，能够精确地操作各种元素，甚至自动化填写谷歌表格，但能够直接操作电脑的自动化工具却寥寥无几。市面上现有的开源或闭源项目存在很大局限性：要么速度过慢，要么操作不准确，要么消耗大量token。例如，去年发布的**Computer Use**项目，虽然曾演示过，但其局限性在于操作的是沙盒中的操作系统，无法直接控制用户当前使用的电脑，并且发布后更新寥寥。因此，在实现操作系统自动化、让AI直接操作我们电脑的需求上，可选的工具和开源项目非常少。

基于这一观察，演讲者提出了一个创新的思路：既然浏览器自动化能力如此强大且精准，何不将这种能力拓展到操作系统自动化层面？他认为，从零开始开发一个电脑自动化工具是舍近求远，不如稍加变通，让现有的浏览器自动化工具直接操作我们的操作系统，即电脑，从而实现真正的电脑自动化。

### 实验验证与效果展示

为了验证这一思路，演讲者在当天早上进行了测试，结果发现该方法完全可行。他的核心构想是将操作系统（包括本地电脑、局域网电脑或云端服务器等）通过类似于 **VNC**（Virtual Network Computing: 虚拟网络计算）或 **RDP**（Remote Desktop Protocol: 远程桌面协议）的方式映射到浏览器中，然后利用 **Cloud in Chrome** 等工具在浏览器内自动化操作电脑的操作系统。

为了增加测试难度，演讲者特意选择了相对小众的 **Ubuntu** 系统，并成功将其映射到了浏览器中。测试主要使用 **Cloud in Chrome** 插件进行，虽然 **OpenIn Browser** 也支持浏览器自动化功能，但演讲者经过一早上测试，发现其效果不如 **Cloud in Chrome**。

#### 自动化计算器操作
首先，他输入了一个最简单的自动化任务：让 **Cloud in Chrome** 打开计算器并计算“10 + 20”。工具执行过程如下：截取当前屏幕截图，点击应用菜单，在搜索框中搜索“计算器”并定位到结果，成功打开计算器应用，输入数字“10”，输入“+”号，输入“20”，然后点击“=”号计算结果。整个过程相当流畅，没有出现任何操作错误，这与他早上测试 **OpenAI** 的 **Explorer Browser** 时一直执行失败的情况形成鲜明对比。

#### 自动化音量调节
接着，演讲者尝试调节 **Ubuntu** 系统的音量按钮。任务是让 **Cloud in Chrome** 将音量调到最小。工具准确识别了右上方的音量按钮，点击后，瞬间将音量调至0，操作速度非常快，超出了演讲者的预期。

#### 终端命令行操作与Python代码执行
进一步加大难度，演讲者要求打开终端命令行并最大化显示，然后在命令行中编写一段 **Python**（Python programming language）**冒泡排序**（Bubble Sort algorithm）算法并执行。**Cloud in Chrome** 立即打开了 **Ubuntu** 的终端，并成功将其最大化。随后，它在终端中输入了 **Python** 代码，并成功执行，用冒泡算法对数字进行了排序。

#### 浏览器下载与安装自动化
最后一个、也是最复杂的任务是：让 **Cloud in Chrome** 打开 **Firefox** 浏览器，从 **Firefox** 中下载 **Chrome** 浏览器，并在 **Ubuntu** 系统上完成安装。**Cloud in Chrome** 成功打开了 **Firefox**，并自动关闭了弹窗，将光标定位到地址栏，输入了 **Chrome** 浏览器的链接，并按回车进入官方网站。接着，它向下滚动页面，找到了“接受并安装”按钮并点击，随后处理了安装确认，开始下载 **Chrome** 的安装包。下载完成后，工具通过终端命令行执行了安装命令，并成功安装。最后，它在终端输入了 **Chrome** 命令以打开新安装的浏览器，并自动关闭了 **Chrome** 的初始弹窗，进入了操作界面。状态栏显示“谷歌 **Chrome** 已成功安装并启动”。演讲者确认，**Chrome** 浏览器图标已出现在左侧任务栏，**Chrome** 浏览器现在可以正常使用。

演讲者总结道，这一系列复杂的操作，包括在小众的 **Ubuntu** 系统上，由 **Cloud in Chrome** 精细化地完成，效果远超预期。他强调，之前他一直认为 **Cloud in Chrome** 及 **OpenAI** 的浏览器工具只能操作网页，但现在发现将操作系统映射到浏览器中，竟然能实现对电脑的直接操作。这种方式比使用其他一些开源的 **Computer Use** 工具效果要好得多。

最后，他提到，将操作系统映射到浏览器中的方式有很多，例如安装 **VNC** server，然后通过 **VNC** 在浏览器中访问自己的操作系统，从而实现使用 **Cloud in Chrome** 对操作系统进行自动化操作。