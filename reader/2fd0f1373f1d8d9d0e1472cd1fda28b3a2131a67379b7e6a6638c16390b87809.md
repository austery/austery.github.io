---
layout: post.njk
source: https://blog.qiaomu.ai/raycast-2-technical-deep-dive
speaker: 向阳乔木
title: 用Web写出“比原生还原生“的桌面App，Raycast是怎么做到的？ · 乔木博客
date: '2026-05-15'
summary: 本文解析了 Raycast 2.0 如何通过构建混合架构，实现桌面应用的跨平台与原生性能。文章详细阐述了其“原生壳子+Web前端+Node后端+Rust核心”的四层架构设计，以及团队在优化 WebView 渲染、处理平台差异和管理内存占用方面的工程实践，展示了如何用 Web 技术打造极致的“原生感”。
area: tech-engineering
category: software-development
tags:
  - desktop-app
  - cross-platform
  - performance-optimization
  - hybrid-architecture
  - native-integration
people: []
companies_orgs:
  - Raycast
products_models:
  - Raycast 2.0
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

# 用Web写出“比原生还原生“的桌面App，Raycast是怎么做到的？

AI资讯

·

2026年5月15日

·

163 次阅读

·

约 16 分钟

用 Web 技术做"原生感"最强的 Mac 应用，Raycast 做到了。

Raycast 2.0 的公测版刚刚上线。

> 下载Beta版 https://www.raycast.com/new

这是他们自 2020 年创立以来最大的一次发布，也是第一个同时运行在 macOS 和 Windows 上的版本。

更让工程师感兴趣的是它的技术路线：一个以"比 Spotlight 还快"著称的原生启动器，选择了用 Web 技术重写。

他们在博客里把整个架构拆开讲了一遍。

读完，会对"Web 与原生"这个争论有新的理解。

Raycast 2.0 同时运行在 macOS 和 Windows 上

## 六年的积累，为什么决定推倒重来

Raycast v1 的核心是纯 Swift + AppKit，从列表行到快捷键到每一个默认行为，全都自己写。

SwiftUI 太慢，不符合他们对性能和控制权的要求。

Raycast v1 的原生 macOS 界面

扩展生态走的是另一套技术栈：React、TypeScript、Node.js。

UI 用声明式描述，由原生 app 渲染。

这个选择带来了一个意外收获，因为技术栈对开发者友好，商店里现在有几千个扩展，覆盖了几乎所有主流工具。

Raycast Notes 是他们第一次在主 app 里用 WebView 做重要功能。

编辑器是一个 React app，挂在原生窗口的 WebView 里。

那是一次测试：能不能用 Web 技术做一个完整的功能模块，同时不破坏整体的原生感？结果成了。

到了 2023 年底，几个问题叠在一起：

想要支持 Windows，但原生 macOS 代码没法直接移植

编译时间越来越长，AppKit 越来越碍事

能做深度 macOS 开发的工程师越来越难招

值得注意的是，就算 Windows 计划不存在，他们也需要重新设计架构了。

招人的困境是压垮骆驼的最后一根稻草。

深度 AppKit 工程师在全球都是稀缺资源，做 macOS 原生应用的团队也普遍面临同样的困境。

越来越多的产品选择 Electron，正是因为 Web 工程师的供给量根本不在同一个数量级上。

这个重写项目有个内部代号，叫"X-Ray"，cross-platform Raycast 的缩写。

## 别人放弃的方案，他们为什么选了

做桌面端跨平台，绕不开三条路。

Electron 是最显眼的选项。

VS Code、Linear、Superhuman 都用它，可以做出很好的产品。

但 Raycast 需要的东西太底层了：全局热键、剪贴板管理、辅助功能 API、悬浮在其他窗口上方但不抢焦点的面板，还有窗口半透明效果。

Electron 能做一部分，但 Web 和原生代码之间的边界很难控制。

而且在 macOS 上打包一个完整的 Chromium，当系统自带 WebKit 的时候，感觉说不过去。

Tauri 控制权更少，而且当时还太年轻，他们不想把整个公司押在上面。

Flutter、Qt、React Native for Desktop 也看过，要么原生控制权不够，要么成熟度不足。

最后他们选了第三条路：自己造混合架构的壳子。

macOS：Xcode 项目，Swift + AppKit，调用系统 WKWebView

Windows：Visual Studio 项目，C# + .NET 8 + WPF，调用 WebView2

这样既有完整的平台 API 访问权限，又有跨平台的 Web UI 层，还能用系统 WebView 而不是打包 Chromium。

代价是：Electron 帮你做好的那些基础设施，都得自己建。

这是一个典型的"控制权换便利性"的选择。

大多数团队做不到，因为他们没有足够的工程资源去填这个坑。

Raycast 赌的是，这个坑填完之后，护城河就在里面。

## 四层架构：每一层都有它必须存在的理由

Raycast 2.0 的整体结构分四层：

层

技术

职责

Host App

Swift（Mac）/ C#（Win）

窗口管理、全局热键、菜单栏、加载 WebView

Web Frontend

React + TypeScript

所有 UI，Mac 和 Windows 共用同一份代码

Node Backend

Node.js

业务逻辑、数据库、扩展运行时、长驻服务

Rust Core

Rust

文件索引、数据同步、性能关键路径

四层架构：原生壳子 + Web 前端 + Node 后端 + Rust 核心

四层之间通过 IPC 通信，接口在一个地方统一声明，然后为每个运行时自动生成类型安全的客户端。

Swift、C#、Node、WebView 四边都有编译时检查。

对大多数团队成员来说，日常工作只在 Web 前端和 Node 后端里。

新功能写一次，Mac 和 Windows 都能用。

这个设计的隐含逻辑是：把变化快的部分（UI 逻辑、业务功能）和变化慢的部分（窗口系统调用、性能核心）彻底分层。

用 Rust 兜性能底线，用 React 换开发速度，这两端各取所需，中间用 Node 连起来。

### 自建文件索引器：Rust 做的事，Spotlight 做不到

v1 的文件搜索依赖 Spotlight 元数据。

这个方案勉强能用，但限制很多，而且完全无法移植到 Windows。

v2 用 Rust 从头写了一个文件索引器。

它作为独立进程运行，直接扫描文件系统，建立搜索索引，通过文件系统事件保持实时更新。

在 Windows 上，正常方式走 NTFS 文件系统太慢，达不到他们想要的扫描速度。

他们的解决方案是直接读 NTFS 的 Master File Table，这是把整个硬盘在秒级而不是分钟级完成索引的唯一实际可行方式。

对比 v1 的 Spotlight 依赖，v2 的文件搜索不再是独立命令，而是集成在根搜索里，搜索速度更快，也不受 Spotlight 索引范围限制。

## "原生感"不是视觉问题，是行为问题

什么叫"原生感"？

Raycast 的标准很简单：如果有人用 Raycast 但不知道它的技术栈，他们会不会觉得这是一个普通的 Mac app？

如果有什么感觉不对，哪怕是一个动画、一个 hover 状态、一个 popover 超出窗口边缘，他们就算没做好。

v2 的目标：用 Web 技术，但感觉像原生 app

他们的 Windows 工程师有一句话说得很准："我们不是一个加了一些原生钩子的 Web app，我们是一个用 Web 做 UI 的原生 app。"

这个区别，决定了他们把时间花在哪里。

### 平台规范的细节

让一个 Web app 在桌面上"感觉不对"最简单的方式，是在应该遵循原生规范的地方走了 Web 规范：

不用 cursor: pointer。桌面 app 不这么做，这个细节立刻暴露"这是网页"

大多数控件不加 hover 高亮。macOS 的按钮和列表项 hover 时的行为和 Web 不同

设置页在独立原生窗口里打开，不是 modal 或侧边栏

Popover 和 tooltip 作为原生窗口渲染，不是 DOM 元素。这样它们可以超出窗口边界，和真正的原生 popover 一样

macOS Tahoe 发布后，Raycast 第一时间适配了 Apple 的新 Liquid Glass 材质，跟系统视觉语言保持一致

视图切换时不闪烁。这是 Web app 常见的问题，他们做了大量工作来消除

## WebKit 不是浏览器的缩小版，是另一头野兽

WebKit 是给浏览器设计的，不是给一个每天开关几百次的启动器设计的。

Raycast 花了大量时间和它周旋。

节流（Throttling）。

WebKit 判断窗口不可见时，会降低 requestAnimationFrame 和 CSS 动画的频率。

对一个频繁显示、隐藏的启动器来说，这直接导致动画卡顿。

他们的绕过方式是让窗口保持"前台但透明"（alphaValue = 0），同时禁用 WebKit 的遮挡检测。

展开时的空白帧。

Raycast 从紧凑模式展开到全尺寸时，WebKit 会把"视口外"的区域节流，导致展开后有一两帧空白。

解决方法是把 WKWebView 始终保持在展开后的尺寸，哪怕窗口本身还是紧凑的。

窗口动画时停止绘制。

WebKit 在带动画的窗口 resize 期间会暂停渲染，画面会卡顿。

他们通过重写 NSWindow.setFrame，把动画换成 Core Animation 隐式动画，让 WebView 在 resize 过程中持续渲染。

窗口打开时的闪白。

用 _doAfterNextPresentationUpdate 确保 WebView 渲染完成后窗口才变可见，消除空内容的闪烁。

Emoji 渲染慢。

WebKit 在遍历字体链找 emoji 字形时很慢。

解法很简单：启动时预热 emoji 字体。但找到这个原因本身花了不少时间。

他们还做了一件有意思的事：在运行时切换 WebKit Feature Flags，和 Safari 开发者菜单里的开关是同一套。

这让他们可以解锁 60 FPS 上限，并启用 requestIdleCallback 来调度非关键任务。

这些坑没有一个是偶然踩到的，每一个都是"在浏览器里没问题，在启动器里就出问题"的边界场景。

这也是为什么大多数团队踩到前两个坑就放弃了。

### Windows 上的专项工作

WebView2 基于 Chromium，有自己的一套节流、渲染和进程管理逻辑。

让 acrylic 毛玻璃效果在自定义标题栏上正确工作，需要原生壳子和 WebView2 运行时之间精确协调。

他们自己控制所有初始化参数，这样可以避免 WebView2 应用启动时常见的白色矩形闪烁。

多窗口管理比 macOS 复杂很多，每个窗口都需要配置自己的 WebView2 环境，包括 acrylic 效果、自定义 chrome 和输入处理的组合。

而且还要专门确保 Chromium 在窗口失焦时不会节流 WebView，因为 Raycast 经常需要在后台更新状态。

## 内存涨了，但他们没想拿数字糊弄你

最常见的对 Web 桌面应用的批评是：慢、臃肿、吃内存。

Raycast 团队选择直接面对这个问题，把数字都摆出来了。

v1 正常使用后大约占 200 至 300 MB。v2 同等使用场景下大约占 350 至 450 MB。多了多少，取决于你装了多少扩展、用了哪些功能。

主窗口隐藏时（Raycast 大多数时间处于这个状态）的详细分解：

进程

内存占用

WebView（WebContent）

120 至 200 MB

Node.js 后端

150 至 200 MB

原生壳子（Swift）

约 40 MB

WebKit GPU 进程

约 18 MB

WebKit 网络进程

约 12 MB

他们补充说：一个空 WebView（没有任何内容）的基础成本就是约 50 MB，一个裸 Node.js 进程约 12 MB。

这些是选择这套技术栈就必须付出的固定成本，剩下的才是应用代码、加载的模块、图标和缓存资源，这部分是可以持续优化的。

关于如何理解这个数字，他们也做了几点说明：

不是所有内存都一样贵。

macOS 会压缩不活跃的内存页，空闲时 Node 后端的内存实际消耗远低于 Activity Monitor 显示的数字。

干净页（mapped 二进制代码）可以随时丢弃重读，真正有代价的是脏页（V8 堆、解码后的图片等）。

Activity Monitor 里跨进程加总的数字还会重复计算共享框架，实际系统成本更低。

真正重要的是内存压力指标，也就是 Activity Monitor 底部那个绿、黄、红的状态图。

数字高不一定代表系统有压力。

这种诚实本身就是一种产品态度。

把数字摆出来，再把为什么不用太担心这个数字也摆出来，让用户自己判断。

## 六年换来了什么，又搭进去了什么

明显变好的

热重载让 UI 改动秒级可见，v1 改一下要重编译整个 Swift 项目重启 app

一个团队同时维护两个平台，新功能写一次

React、TypeScript、Node 工程师比深度 AppKit 工程师好招得多

富文本、Markdown 渲染、复杂动画布局，WebKit 比 TextKit 更成熟

扩展不再需要单独下载 Node，因为 app 本身就跑在同一个栈上

文件搜索集成到根搜索，速度更快，不依赖 Spotlight

变难了的

内存基线更高，WebView 和 Node 进程本身就有固定开销

四个运行时的调试链路更长，一个 bug 可能要从 React 追到 IPC 再追到 Rust

Windows 的碎片化比 macOS 严重，需要处理更多硬件和系统版本的边界情况

部分原生行为（辅助功能、拖放边缘情况、输入法处理）在 WebView 里需要显式实现

窗口冷启动延迟：v2 会主动回收不活跃的窗口来控制内存，代价是从 hotkey 打开 AI Chat 或 Notes 时会有短暂延迟，他们还在调整这个平衡点

他们的判断是：这个取舍值得。

速度、跨平台、招人，这三个收益很难用别的方式获得。

内存和调试复杂度，是可以靠工程投入改善的问题。

## 真正值得借鉴的，是做选择时的那份清醒

Raycast 的这次重写，回答了一个很多团队都在纠结的问题：Web 技术到底能不能做出"原生感"的桌面 app？

他们的答案是能，但前提是你得愿意花时间去和 WebKit 的各种默认行为博弈，去建那些 Electron 帮你做好的基础设施，去在每一个细节上问自己"这感觉对吗"。

他们选择不用 Electron，原因很实际：Raycast 需要的原生控制权，Electron 的边界给不了。

这个决定不适合所有人。

对大多数桌面 app 来说，Electron 是更合理的选择。

Raycast 之所以走混合路线，是因为他们的产品特性决定了控制权比便利性更重要。

有意思的是，这个道理在技术之外也成立。

很多团队纠结的不是"哪个方案更好"，而是"我们有没有能力为更好的方案买单"。

Raycast 踩过的那些 WebKit 的坑，不是 bug，是学费。他们愿意交，因为他们知道自己要的是什么。

原文：A Technical Deep Dive Into the New Raycast · Raycast Blog

© 2026

·

向阳乔木