---
layout: post.njk
source: https://yage.ai/share/cloudflare-precursor-agent-detection-20260716.html
speaker: yage.ai
title: |-
  Cloudflare Precursor：AI Agent 用上真实浏览器之后，Bot
  Detection 看什么
date: '2026-07-16'
summary: Cloudflare 发布了 Precursor，一个客户端行为检测系统，它通过持续收集和交叉验证浏览器会话中的交互信号（如指针移动、输入节奏等），来区分人类操作与 AI Agent 的行为。该系统标志着 Bot Detection 从依赖静态属性转向分析整段任务的动态行为序列，旨在提高对真实浏览器中运行的 Agent 的识别成本。
area: tech-engineering
category: ai-application
tags:
  - bot-detection
  - browser-agent
  - session-behavior
  - human-vs-agent
people: []
companies_orgs:
  - Cloudflare
products_models:
  - Precursor
media_books: []
draft: true
status: evergreen
---

Cloudflare 在 2026 年 7 月 13 日发布了 Precursor。它是 Enterprise Bot
Management 里的一套客户端行为检测系统，会沿着整段浏览 session
收集交互信号，区分人类操作与自动化或 agent 行为，并把结果送进 Cloudflare
原有的挑战、Bot Score 和安全规则。

这个产品出现的背景，比“Cloudflare 多采集了几种鼠标信号”更重要。AI
agent 已经可以用 Playwright 驱动真实的
Chrome。网站看到的浏览器是真的，JavaScript
会正常执行，网络请求也可能来自用户自己的设备。过去那条“浏览器环境正常，所以背后是人”的捷径开始失效。

我们在 5 月分析 Project
Mariner 关停时，已经看到这条变化。当时 Claude for Chrome、Codex
Computer Use 和 Chrome auto-browse 都在把 agent
移进用户的真实设备与浏览器会话，让它共享 Cookie、IP
和登录状态。这条路线确实避开了独立 VM、云浏览器和 headless 环境最显眼的
bot 特征。Precursor
接着回答了下一半问题：环境看起来完全正常以后，网站还能从哪里看出
agent？

Precursor
给出的答案，是把判断从某个静态属性拉长到整段任务：这个浏览器怎样移动指针、输入文字、切换焦点，前后行为能不能互相解释。它代表的不是
Bot Detection
从无到有的一次发明，而是检测对象发生了变化。防守方以前主要追问客户端像不像自动化工具，现在还要判断真实浏览器里正在运行的是人，还是
agent。

## Bot Detection 从来不只靠
CAPTCHA

最早的人机识别，把判断压在一个检查点上。CAPTCHA
要求访问者完成一项当时对人容易、对机器困难的任务，例如识别扭曲文字。系统不需要理解整段访问，只看这道题能不能答对。

浏览器指纹把判断往后台移了一步。屏幕分辨率、字体、时区、浏览器 API
等属性组合起来，可以描述一个客户端环境。EFF 在 2010 年发布的 Panopticlick
研究显示，这些属性的组合常有很强的辨识力。防守方于是可以检查环境是否自洽，以及它是否带着常见的自动化痕迹。

随后，风险评分逐渐取代每次都弹出的显式题目。客户端脚本、请求频率、Cookie、页面顺序和账户历史一起进入判断。学术界至少在
2010 年前后就已经按 session 聚合 Web 日志，分析访问频率、页面路径和 HTTP
错误。相关研究后来又把
Web 日志与鼠标行为放在一起检测高级 bot。

Cloudflare 自己也早有多层信号。JavaScript
Detections检查浏览器环境和脚本执行，__cf_bm
帮助平滑单个访问者的请求模式，Anomaly Detection
学习站点的正常流量基线，Sequence Rules
检查接口调用顺序。这些输入最后都可以影响每个请求的
Bot Score。

因此，Bot Detection 的历史不是 CAPTCHA、指纹、请求评分和 session
分析互相替代。新的信号不断加到旧信号上，观察时间也从一次点击延伸到多次请求、账户历史和完整访问。Precursor
进入的是一条已经存在多年的演进路线。

Bot Detection 的信号逐层叠加：从一次
CAPTCHA、浏览器指纹和单次请求评分，发展到 Session 行为与声明式 Agent
身份

这张图表示信号叠加，不是旧技术退出、新技术接班。到了 agent
时代，指纹和请求评分仍有用，只是单靠它们越来越难回答操作者是谁。

## Browser Agent 改变了问题本身

传统 Web bot 通常执行预先写好的脚本。Browser agent 多了一层 LLM
推理：它可以阅读页面、规划下一步、调用浏览器工具，遇到错误后再换一种路径。它做的也是人类会做的任务，例如订机票、购物或在论坛发帖。

这类 agent
给检测系统带来四个变化。第一，它运行在真实浏览器里，环境属性不再自动暴露其身份。第二，它能处理动态页面和意外分支，不必重复一条固定
URL 序列。第三，本地 agent 可以从用户设备和住宅网络发出流量，IP
与网络路径也可能完全正常。第四，robots.txt、User-Agent 和 Web Bot Auth都依赖
agent 主动声明；不愿声明的自动化程序仍会伪装成人。

更麻烦的是，agent
不天然等于恶意程序。它可能得到用户授权去买票，也可能未经允许抓取内容；一个合法
agent
还可能受提示注入影响，开始执行越权动作。网站真正需要分开的，是合法委托、未经许可的自动化和正在发生的危险行为。单一的
human/bot 标签装不下这些差别。

## Playwright
淘汰的是一批廉价信号

Playwright 是 Browser agent 常用的自动化框架。它可以通过 Chrome
DevTools Protocol，也就是
CDP，控制真实浏览器打开页面、点击控件和填写表单。浏览器本身并不假，自动化发生在控制它的那一层。

这会削弱一批过去成本很低的判断。navigator.webdriver
可以返回 false，无头浏览器的 User-Agent 可以改写，缺失的多媒体 API
和粗糙指纹也能补齐。DataDome 的 Galileo
研究记录了特定 Playwright 版本和路径如何隐藏
navigator.webdriver。这些信号没有彻底消失，但单独使用时不再可靠。

真实浏览器仍会留下操作痕迹。agent 可能让指针在 0
毫秒内跳到目标位置，瞬间滚过长页面，以固定节奏输入文字，或者完全跳过人类阅读和寻找控件的停留时间。CDP
也可能产生可观察的副作用。把时间窗口拉长以后，焦点、页面可见性、输入事件、请求路径、访问速率、账户状态和最终业务结果还能互相校验。

所以 Playwright
改变的不是“网站还能不能检测自动化”，而是检测需要付出多少成本。读一个属性就下结论的时代正在过去，防守方必须采集更长、更密的行为序列，并接受判断只能是概率性的。

## FP-Agent
用机器学习测试 Agent 行为是否可分

2026 年，加州大学戴维斯分校的研究者发表了预印本 FP-Agent，专门测量
Browser agent
能否与人类以及彼此区分。这个实验的重要性，不只在于它发现了几个 agent
怪动作，而在于它把问题写成了一个可训练、可比较的多分类任务。

研究团队搭建了一个带监测脚本的测试网站，让七种 Browser agent
完成订机票、购物和论坛互动三类任务。每种 agent 运行 1,000 次，另外招募
56 名学生，收集了 546 份人类操作样本。研究者提取 418 个浏览器指纹特征和
50 个行为特征，再用 XGBoost
分别训练浏览器指纹、行为指纹和混合特征分类器。

结果显示，两类信号的区分力差了一截。只看浏览器指纹时，分类器的 F1
大约是 0.8。多个 agent
共用相似浏览器配置时，模型很容易把它们混在一起。加入打字、滚动和鼠标行为后，行为与混合分类器在这组受控数据里取得接近满分的
F1。研究者的 FP-Agent 识别了全部七种 agent，而同一研究里的 Cloudflare
防护只拦下其中一种。

这并不证明一个 XGBoost 模型已经解决 Agent Detection。实验只有七种
agent、三类任务和一组学生参与者，软件版本与运行环境也固定。模型可能学到某一版
agent
的实现习惯，下一版加入拟人化轨迹后，效果就会下降。论文真正更新的判断是：浏览器属性不够时，agent
仍会暴露稳定的行为差异；防守方可以用机器学习从这些差异中分类，但必须持续采集新样本、更新特征和重训模型。

这会形成一场长期竞赛。检测模型学习 agent 的打字和移动方式，agent
开发者再让动作更像人。FP-Agent
在这组样本里测出了稳定差异，没有证明这些差异会永久存在，也没有给出生产环境的通用识别率。

## Precursor 选择持续修正信任

Cloudflare 将 Precursor定义为客户端、session
级的行为验证系统。它属于 Enterprise Bot Management，也是 Turnstile
的可选补充。Turnstile
擅长在登录、注册和结账等关键时刻做一次验证；Precursor
补的是这些检查点之间的活动。

它先在经过 Cloudflare 的 HTML
响应里动态注入脚本。脚本持续记录指针移动、键盘活动的时间与节奏、焦点变化和页面可见性，再把压缩后的事件送回边缘节点。Cloudflare
的评估器不只看某个动作快不快，还会交叉检查不同信号：页面不可见时为什么还有指针移动，文本框没有焦点时为什么出现键盘事件，整段轨迹是否前后自洽。

Precursor 也改变了做决定的时机。用户通过一次挑战后，不会因此获得整段
session 的永久通行证。Cloudflare 的更新说明写明，系统会随着行为变化重新验证
challenge clearance，并用 session 上下文更新 Bot Score。原始行为流由
Cloudflare 内部处理，客户使用的是由它推导出的 session
上下文、分数和规则结果。后续请求可能被放行、交给 Security Rules
处理，或再次接受挑战。

这套设计的核心不是寻找一个能一锤定音的 Agent 指纹。Cloudflare
选择持续收集许多不完整的证据，让它们互相校验，再随着 session
展开修正信任。对攻击者来说，改掉一个属性还不够，整段访问都要维持合理行为。对网站来说，也不必自己部署采集服务、实时分类器和处置接口，结果可以直接进入已有的
Cloudflare 规则。

它最自然的用户，是已经把 Web 或单页应用放在 Cloudflare 后面，并需要
Enterprise Bot Management
持续覆盖页面活动的网站运营方。登录、注册、结账之外仍有大段访问需要观察，或团队希望少弹
CAPTCHA 但继续发现高级自动化，才是它最典型的使用场景。Cloudflare
同日材料对实际开放范围的描述并不一致，因此不能从这个产品位置反推出哪些账户已经能够使用。它也不负责账户身份验证，不替应用决定某个用户或
agent 有权做什么。

Cloudflare 表示，Precursor
只记录键盘活动的时间与节奏，不记录实际字符，也不把行为信号绑定到账户、登录身份或持久个人资料。这限定了它的判断基准：它观察当前
session 的行为一致性，不建立某个具体人的长期行为身份。

## 竞品在不同位置提高攻击成本

持续看行为并非 Cloudflare 独有。HUMAN和
DataDome同样强调
session 或完整访问路径，这部分与 Precursor 直接竞争。两家公司还分别提供
AgenticTrust和
Agentic
Trust，把已声明的 Agent
身份与访问政策放进相邻的控制层。行为检测和身份治理在产品组合里靠得很近，解决的仍是两个问题。

Kasada选择了另一种成本模型。它更重视客户端真实性、代码执行证明和动态代码，让攻击者不断付出逆向与维护代价。Akamai Bot
Manager和 Imperva
Advanced Bot Protection则把请求、设备、行为和威胁情报放进企业级 WAAP
套件。

Arkose
Labs主要在注册、登录、支付等高价值节点施加自适应挑战，目标是直接破坏攻击者的投入产出比。Fingerprint和
reCAPTCHA Enterprise
更像信号或升级验证组件，需要客户自己把判断接到业务处置上。

Precursor 最清楚的差异不在某一种鼠标特征，而在 Cloudflare
同时控制脚本分发、边缘评估、Bot Score、挑战和 WAF 规则。已有 Cloudflare
客户可以少接几层系统，也能让 session
信号立即影响后续请求。这是分发与集成优势，尚不足以证明它的算法比竞品更准。

## 行为检测之后，还缺身份与授权

Precursor
的第一条边界，是所有行为都可以继续模仿。攻击者可以放慢速度、加入停顿、生成鼠标轨迹、维持
Cookie 和账户状态。整段 session
比一个指纹更难伪造，却不会产生不可伪造的人类证明。检测提高的是成本，不是确定性。

第二条边界更根本：行为不像人，不代表它不合法。一个得到授权的 agent
本来就可能没有鼠标轨迹，几秒钟填完表单。反过来，一个有签名身份的 agent
也可能遭到提示注入或超出用户授权。Agent
身份、用户委托、业务许可和当前行为是四个问题，任何一层都不能替代其余部分。

网站治理 Agent
流量时需要分别判断身份、用户委托、业务权限和当前 Session 行为，Precursor
只覆盖运行时风险这一层

无感检测还会把误报藏进后台分数。只用键盘、屏幕阅读器、语音控制、开关输入或远程桌面的用户，可能产生完全不同的轨迹。W3C 对 CAPTCHA
无障碍问题的总结没有评估
Precursor，却暴露了相同的设计义务：产品需要可访问的升级验证、申诉和人工恢复。Cloudflare
尚未公开按用户群体划分的误报率，外界也缺少 Precursor
的独立准确率与性能测试。

隐私问题也不会因为“不记录实际按键”自动消失。交互时间、session
标识、保留期限、拒绝采集、模型训练复用和判断审计都需要明确规则。网站运营方至少需要知道数据留多久、谁能访问，以及错误判断如何复查。

产品状态本身还有一处官方冲突。Cloudflare 在 2026
年 7 月 13 日的新闻稿中宣布 Precursor 已经 GA；同日技术博客却仍写着
rolling out，并称产品会免费到当年稍晚的 GA
release。实际开放范围和收费状态仍要以账户与合同为准。

Browser agent 让 Bot Detection
进入了一个更难也更现实的阶段。网站不能再靠真实浏览器属性推断人类意图，也不能把所有自动化都当成攻击。Precursor
补上运行时行为这一层，却没有替网站解决身份和授权。只有把这些判断接在一起，合法
agent
才不必靠模仿人类通行，恶意自动化也不能只换一套浏览器外壳就混过去。