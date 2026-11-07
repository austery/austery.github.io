---
layout: post.njk
source: https://yage.ai/share/voice-assistant-wake-word-broadcast-20260609.html
speaker: yage.ai
title: Siri 的频段缺口，和一条从 Xbox 开始的工程族谱
date: '2026-06-09'
summary: 文章探讨了语音助手（如Siri、Alexa）在广播源中被误触发的问题，并追溯了从Xbox广告到Amazon Echo等一系列产品中出现的工程先见。核心在于讨论了如何通过技术手段（如Notch filter和声学指纹）来区分用户指令和背景噪音，以及随着AI应用深度增加，这种误触发的代价和防御机制的演进。
area: tech-engineering
category: ai-application
tags:
  - voice-assistant
  - false-trigger-mitigation
  - audio-fingerprinting
  - signal-filtering
people: []
companies_orgs:
  - Apple
  - Amazon
  - Google
products_models:
  - Siri
  - Alexa
  - HomePod
  - Echo Dot
media_books: []
draft: true
status: evergreen
---

开会的时候聊到某个语音助手，桌上每个人的手机和音箱都亮了。Alexa、Siri、Google，只要你说了它的名字，它就以为你在叫它。做过智能音箱的人都知道这件事。每个人也都见过。

WWDC26 刚结束。这次 Apple 把 Siri 做了一次彻底重构：独立
App、多轮对话、屏幕感知，由 Apple Intelligence 和 Gemini
联合驱动。但一些细心的观众注意到了另一个细节。直播音轨里，主持人每次说出
“Siri” 的时候，声音就闷了一点点。用频谱看，3 到 6
千赫这一段压得很低，一个 notch filter
把这段频率主动削掉了。不是音质优化的操作。它要达成的效果是：台上的主持人每说一次
Siri，观众家里的 HomePod 和 iPhone 不会跟着亮起来。

这听起来像是 Apple 的工程先见。但这条技术路线真正的起点不在
Cupertino。在 2014 年，一个 Aaron Paul 的 Xbox
广告里。而且它每一步的推进，都不是因为有人想得更远，是因为有人摔得够重。

## 第一张多米诺骨牌

2014 年 6 月，微软请《绝命毒师》里的 Aaron Paul 拍了一支 Xbox One
广告。Paul 坐在沙发上，对着电视说 “Xbox On” 和 “Xbox, play
Titanfall”，展示 Kinect 语音控制功能。这支广告推广的恰好是无 Kinect
的降价版 Xbox One，而真正拥有 Kinect
的玩家看完广告后发现，自己的游戏机自己开了机。Twitter 和 NeoGAF
上炸了锅，Kotaku
当时的报道收集了海量用户吐槽。微软没有公开回应。

Xbox
工程师设计了语音唤醒，广告团队拍了展示语音唤醒的广告，两边在各自领域都做了正确的事。问题在于没有人意识到这两件事会产生交集。

## 2017：同一张牌连倒五次

三年之后，这个交集变成了整个语音助理行业的日常。

2017 年 1 月，达拉斯一个六岁女孩对家里的 Amazon Echo Dot 说了句 “can
you play dollhouse with me and get me a dollhouse?”，Alexa
就下了单。女孩的父母捐掉了 dollhouse，同时给 Alexa
加了购买确认码。事情到这里本可以结束，但圣地亚哥 CW6
新闻把这则趣闻搬上了电视。主播 Jim Patton 说 “I love the little girl,
saying ‘Alexa, order me a dollhouse.’” 节目播出后，观众家里的 Echo
再一次触发了 dollhouse 订单。一条报道 Alexa
误购的新闻，在报道中又制造了新一轮误购。

2 月，Google 自己的 Super Bowl 广告翻车了。Google Home
的广告里，演员说 “OK Google, turn on the hall lights” 和 “OK Google,
turn off the music”，观众家里的
Google Home 亮成一片，有些设备乖乖执行了关灯指令。和 Aaron Paul
的故事一样，这是自家广告触发自家设备，同一个公司的左手打了右手。

9 月，South Park 第 21 季首映。Cartman 在剧中反复喊 “Alexa, add…to my
shopping list” 和 “OK Google”，全美观众的购物清单里出现了各种
South Park 式的脏话。Twitter 上有人发帖：“我的 Alexa
响了十五次，只能拔电源。”

## 2017 年 4 月，Burger King 登场

这些事件都是意外。Burger King 不是。

2017 年 4 月 12 日，Burger King 在全美电视上播了一支 15 秒广告。一名
BK 员工站在柜台后，凑近镜头，一字一顿地说：“OK Google, what is the
Whopper burger?” 任何在电视音箱范围内的 Google Home 和 Android
手机都会亮起指示灯，语音念出 Whopper 的维基百科条目第一段。Burger King
在广告上线前已经编辑了维基百科页面，把描述改成了广告文案。

这个计划的脆弱性在几分钟内就暴露了。互联网用户开始维基百科编辑战，配料先后被改成”氰化物”“鼠肉”“脚趾甲”，条目开头被改成
“The Whopper is the worst hamburger product sold by the international
fast-food restaurant chain Burger
King”。在维基页面锁编辑之前，确实有人让 Google Home 念出了这些版本。

Google 的反应比想象中快。广告上线不到三小时，Google
在服务端实施了声学指纹屏蔽。具体做法：获取广告中演员说 “OK Google,
what is the Whopper burger?” 的原始音频片段，在服务器端注册声学指纹。当
Google Home
收到这段特定录音触发的查询时，设备虽然仍会被唤醒、指示灯会闪烁，但随即安静休眠，不给任何语音回应。Google
屏蔽的是这段具体的音频录制本身，真人说出同样内容不受影响。

Burger King 随后换了一个演员用不同语调重新配音试图绕过指纹，Google
同样屏蔽了它。广告存活总计约三小时。但 Burger King 从媒体报道中获得了约
1.35
亿美元的赚得媒体价值，并在戛纳狮子奖获了奖。广告本身失败了，争议成功了。

经此一事，“广播会触发语音助手”从一个偶发事故变成了可以被故意利用的攻击面。在这之前，各家对误触发的回应是事后修补；在这之后，防唤醒进入了工程学范畴。

## Notch、指纹、水印

防唤醒技术有一条明确的演化线：论文没有走到产品前面。每一次防御方案的上线，都是产品先挨了一巴掌。

最早社区逆向出来的方案是 notch filter。2017 年初，Reddit 用户 aspyhackr
发帖说，他注意到 Amazon 广告里的 “Alexa”
声音听起来不太一样，频谱分析后发现 3 到 6
千赫这一段严重衰减。他进一步做了实验：对普通录音中的 “Alexa” 用 Audacity
做 band-stop filter 削掉 4 到 5 千赫，结果 Echo 就不再唤醒。Amazon
从未确认过这个机制，但 Bloomberg、The Verge 和 PCMag
都引用了这个社区发现。

Notch filter
的问题也很清楚。这一段在人耳的可听范围内，削得太多语音发闷。过一遍电视扬声器、蓝牙传输、流媒体压缩后也不一定稳定。最关键的是，一旦成为固定规则，任何人都能测试和绕过。Burger
King 事件就是最好的证据。

声学指纹是更成熟的方案。Amazon 没有依赖 notch。2018 年 Super
Bowl，Amazon 自己的 Alexa 广告里反复出现 “Alexa” 和 “Alexa,
play…”，但全美 Echo 几乎无一误触发。2019 年初，Amazon
Science
发表了官方文章详细解释了技术原理：广告音频在播出前先提取指纹并存入数据库，设备端本地匹配已知广告指纹，云端同步维护更大指纹库。如果是未知媒体来源，当多个家庭同时上传相似的音频，系统会动态判定为
media event 并静默处理。

Google
的路线类似但更主动。它的多项专利描述了给包含唤醒词的音频嵌入水印：一种人耳不可闻、机器可检测的扩频信号，明确标记”这是媒体内容，不要响应”。水印相比指纹的好处是检测复杂度固定，不需要维护不断膨胀的指纹库。Amazon
在 2019 年后的音频水印研究也走了这个方向，把它当作指纹的补充。

Apple 在这条路上最沉默。它的 ML 博客详细解释过 Siri
的唤醒检测机制：16 千赫采样、mel filter
bank、深度神经网络、说话人识别、false trigger
mitigation。但没有提到广告或直播防唤醒方案，也没有像 Amazon
那样公开说明过工程实践。WWDC26 的 notch 观察如果属实，Apple
用的恰恰是这条技术族谱里最老的那一招：十年前 Amazon
广告里就已经出现过的东西。

## 同一个老问题，新的形式

WWDC26 的场景和 2014 年 Aaron Paul 的广告、2017 年 CW6
的新闻播报在本质上是一回事：一个面向大众的广播源里出现了唤醒词，大量设备同时在线。只是这一次，触发的对象从
Echo 和 Google Home 变成了 HomePod 和 iPhone。

技术栈不同。Alexa 时代是三个音节以上的唤醒词，而 WWDC23 后 Apple
已经把 “Hey Siri” 缩短为单字
“Siri”。单字唤醒的误触发率天生更高。业内公司 Sensory 当时就指出，“Siri”
的两个音节和日常语音中的 “serious” 高度重叠，比 “Alexa” 和 “Hey Google”
更容易误触发。这是 Apple 做单字唤醒时绕不过去的代价。

另一个变量是 Apple Intelligence。这次 WWDC 的核心方向是扩张。Siri
正在变成 AI 原生应用，从简单的命令执行走向上下文理解、屏幕感知、第三方
AI
引擎接入。激活频率和深度同时在上升，误激活的代价也在上升。一个只开灯的误触发损失不大，一个能读写日历和备忘录的误触发完全不同。WWDC26
上 notch 的传闻如果成立，它不是一个工程
trick，而是一个必然的安全措施。

## 语音天生是开放的

这个故事有一条主线贯穿始终：语音交互是一个天生开放的信道。视觉交互里，你的眼睛可以选择看哪里。触控交互里，你的手指决定按哪里。但语音不区分来源。只要麦克风开着，任何进入的声音都是合法输入。它不来自设计缺陷，来自物理限制。

从 Xbox One 到 Google Home 到 Echo 到
HomePod，每一家都在事后补这个漏洞。2014 年的微软没预料到。2017 年的
Amazon、Google 和 Apple，即使前一年刚看过 Aaron Paul
的笑话，也没预料到自己会踩同一类坑。每一代的防御方案在本质上是在回答同一个问题：如何让设备区分”用户在对它说话”和”电视在对它放屁”。

这个问题仍然没有完整的答案。声学指纹可以识别已知媒体，但未知直播需要动态聚类，而且需要大量同时触发才可靠。水印需要整个内容生产链路配合，从拍摄到编码到播出，每一环都不能断。设备端的
false trigger mitigation
需要持续迭代模型，攻防双向演进。这些方案解决的都只是”知道这是广播”这一层。一个更有野心的方向或许是让设备知道”谁在说话”，让麦克风从硬件层面拒绝屏幕方向的声音。

WWDC26 的 notch 传说，无论真伪，都提醒了一件事。十五年前一个 Aaron
Paul
的广告里暴露出来的问题，今天仍然在用不同的形式重演。技术每向前走一步，背后都有一个人在同一个地方摔过跤。