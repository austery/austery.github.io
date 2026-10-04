---
layout: post.njk
source: https://yage.ai/share/google-project-mariner-shutdown-20260511.html
speaker: yage.ai
title: |-
  Google 关掉 Project Mariner，Anthropic 和 OpenAI
  其实也没跑通
date: '2026-05-11'
summary: Google 关闭 Project Mariner 标志着 AI Agent 发展方向的调整。文章指出，独立的浏览器 Agent 面临严峻的反爬虫挑战，而真正的需求在于自动化桌面应用。Anthropic、OpenAI 和 Google 的经验表明，成功的 Agent 应运行在用户真实的环境中（如用户浏览器会话或桌面），以规避反爬系统，这已成为行业共识。
area: tech-engineering
category: tech-trends
tags:
  - ai-agents
  - gui-automation
  - anti-scraping-challenges
  - desktop-automation
  - user-environment-integration
people:
  - Jensen Huang
companies_orgs:
  - Google
  - Anthropic
  - OpenAI
  - Amazon
  - Perplexity
products_models:
  - Project Mariner
  - Operator
  - CUA
  - Codex Computer Use
  - Claude for Chrome
  - Chrome auto-browse
  - Bloomberg Terminal
  - Claude Cowork
media_books: []
draft: true
status: evergreen
---

5 月 4 日，Google 在没有预告的情况下关闭了 Project Mariner——去年 I/O
大会上作为 AI agent
旗舰产品登台的实验项目。官方页面只剩一行字：“Technology voyaged to other
Google products.”

这件事离 Google I/O 2026（5 月 19
日）不到两周，所以大多数报道把它读成产品失败、或者 Google 在 AI agent
竞赛中掉队。都不算错，但如果你把比较对象放对了，看到的画面不一样。

## 先把两个品类分开：browser
agent 和 computer use

Project Mariner
的工作原理是截取浏览器截图，让视觉模型识别按钮和文本框，再模拟点击和输入。它和
Anthropic 的 Computer
Use、OpenAI 的 CUA
(Computer-Using Agent) 共用同一套底层技术——screenshot → vision model
→ action planning → execute GUI
operations。但这套技术有两个不同的产品形态：

Browser agent（Mariner、Claude for
Chrome、auto-browse）跑在浏览器沙箱里，只能看到网页内容。Computer use
agent（Anthropic Computer Use、OpenAI Codex
Computer
Use）需要拿到整个桌面的截图和鼠标键盘控制权——但两者的部署方式又不同：Anthropic
的 Computer Use 通常跑在 VM 或沙箱里，Codex Computer Use 则是一个 macOS
桌面插件，直接运行在用户的真实 Mac 上，需要 Screen Recording 和
Accessibility 权限。

两个品类面对的物理环境不一样，命运也不一样。CUA 这个模型在 OSWorld（全桌面操作
benchmark）上做到 38.1%，在 WebArena（网页操作 benchmark）上做到
58.1%——但 benchmark
成绩和产品形态是两回事。比之前先分清楚你在比什么。

## 独立
browser agent 的天花板：你不是在和网页打交道，你是在和反爬系统打仗

OpenAI 的 Operator 从 2025 年 1 月上线到 8
月关停，一个经常被提到的原因是购物流程不可靠。但有一个更基本的细节：Operator
甚至连 ChatGPT.com
都访问不了——它自己公司的网站都在反爬名单里。

独立 browser agent 的部署方式天然把它变成了 bot。不管你用 headless
Chrome、云托管浏览器还是独立 VM，你都在创建一个全新的浏览器会话——没有
cookie、没有浏览历史、没有人类行为特征。网站反爬系统十几年来优化的就是探测这种会话。Amazon
今年 3 月对 Perplexity Comet 拿到的 preliminary
injunction 只是这类对抗的法律出口——法官判定 Comet 访问 Amazon
账户”有用户许可但没有 Amazon 授权”，依据是 Computer Fraud and Abuse
Act。Perplexity 已上诉，第九巡回法院 5 月 15 日听证。

这意味着做独立 browser agent
的公司有一个结构性劣势：你的工程资源不在提升模型能力或产品体验上，而在和一个你不认识的对手打军备竞赛。这个对手——Instagram、Amazon、各类电商和社交平台——有几十年的反爬经验，有直接的经济激励（保护数据、定价分层、广告模型），而且你的每一轮规避策略都会触发它的下一轮检测升级。

是一个逆风的品类。不是因为需求不成立——需求在别处成立——而是因为产品形态本身决定了你要同时做两件事：做好
agent 和打赢一场你不太可能赢的军备竞赛。

## 需求在 computer
use 这边，不在 browser agent 那边

回来看需求。独立 browser agent
瞄准的典型场景——帮你订机票、比价、购物——对可靠性要求极高。用户容忍不了偶尔买错，而”买错”和自己操作的区别只是几分钟。这个
cognitive trade-off 极差。OpenAI 关掉 Operator 后试了 Instant
Checkout（让用户在 ChatGPT 里下单而不是让 agent
去网站操作），也关了，但方向是对的——它在绕开浏览器操作本身。

真正的需求在另一头。Bloomberg Terminal 的 API
访问需要六位数美元的额外合同。医院还在跑的 legacy patient record
系统、90 年代写的保险理赔软件、政府内部系统——这些存量不会因为 AI
出现了就自动装上 API。问题在于，它们绝大多数不是网页应用。Bloomberg
Terminal 是一个 Windows 桌面程序，不是一个在 Chrome 里跑的
SPA。你要自动化的是桌面应用，不是网页——所以你需要的是 computer use
agent，不是 browser agent。

需求没错，品类错了。

## 解法：共享用户的真实会话

但 computer use
的路要怎么样才走得通？同样的技术——截图→视觉模型→操作——换一个部署方式，瓶颈就消失了。

如果你不让 agent 开一个新浏览器，而是让它直接操作用户已经在用的
Chrome——共享同一个 cookie、同一个
IP、同一个浏览行为模式——那么从网站的角度看，分不出是用户在点还是 agent
在点。Google 今年 1 月 28 日上线的 Chrome
auto-browse 就是这条路径。它不是独立产品，而是 Chrome
的内置功能，面向 Google AI Pro（$19.99/月）和
Ultra（$249.99/月）用户。它跑在用户真实的浏览器里，用着用户真实的登录状态。反爬系统看不到一个全新的可疑会话，只看到一个正常用户在做正常操作——只是点击速度有时候快了一点。

如果更进一步，走到 computer
use——直接控制用户桌面、操作所有应用而不只是浏览器——这个优势会进一步放大。用户桌面上有真实的人类操作轨迹：鼠标移动速度、打字节奏、标签切换模式、窗口切换间隔。这些信号是
bot 几乎不可能伪造的，也让 bot detection 几乎不可能准确抓出
agent。OpenAI 的 Codex
Computer Use 就是这条线的实例——它在用户的真实 Mac
上跑，共享用户的桌面环境和浏览器登录态，不会触发出现在 headless
环境下的反爬问题。

Wired 在三月报道，Google
把 Project Mariner 团队成员调去开发一个 “OpenClaw-like” agent。同月
Wired 记录了整个行业的方向调整：Jensen Huang
说”世界上每家公司现在都需要有一个 OpenClaw 策略”；OpenAI 高管希望让
Codex 成为 ChatGPT 内的通用 agent 引擎；Anthropic 推出了不需要 terminal
的 Claude Cowork。

## 三家公司的答案其实相同，只是表达不同

把品类分清楚后，三家公司的轨迹可以重新排列：

Anthropic：Computer
Use 发布 18 个月仍是 beta，OSWorld 成功率
22%（OpenAI 的 CUA benchmark 页面中将 Anthropic Computer Use
列为前一代 SOTA，22% 为该页引用的成绩；人类
72.4%）。官方建议”从低风险任务开始”。独立 computer use VM 路线没走通。但
Claude for
Chrome（跑在用户真实浏览器里的 extension）活得很好，3 月刚加上了
Quick Mode。真实浏览器的路走着。

OpenAI：CUA 模型在 benchmark 上做到 OSWorld
38.1%，WebArena 58.1%。独立 browser agent（Operator）关了，Instant
Checkout 关了。但它在另一个方向上走了跟 Google 相似的棋：Codex
Computer Use 是一个 macOS 桌面插件，直接跑在用户的真实 Mac 上，需要
Screen Recording 和 Accessibility 权限才能截屏和模拟操作。OpenAI
自己的安全指南里明确写了”如果 Codex
使用你的浏览器，它可以操作你已登录的页面”——计算机用的是用户真实的浏览器会话，开的是用户真实的桌面应用，不存在独立
VM 被反爬系统识别的问题。同时，Codex 本身正在被定位为 ChatGPT 内的通用
agent 引擎，走的是 coding agent + 系统集成路线。

Google：Mariner 关了。Proxy-browser 做进了
Chrome（共享真实会话，不会触发反爬）。团队在做 OpenClaw-like 系统级
agent（共享真实桌面）。两条线都避开了独立产品的 bot detection 陷阱。

还有一个财务背景。Alphabet 2026 Q1 财报显示 Google Cloud 同比增长 63%
至 200 亿美元，Cloud backlog 4620 亿美元。Google 从 AI
赚钱的方式是卖基础设施，不是卖 agent 产品。Anthropic 和 OpenAI
没有浏览器和搜索引擎可以变现，必须把 agent
变成收入引擎。但即便如此，它们也没在独立 browser agent 上坚持下去。

总结下来，这次关停的好故事不是”Google
掉队了”，而是”三家做同类产品的公司得出了同一个结论：独立 browser agent
跑不通，但 GUI automation 的路还在——只是不能走 headless
云端专用环境那条”。Google 把 Mariner 技术放进了
Chrome（共享真实会话），把团队转向了系统级
agent（共享真实桌面）。两条路都避开了反爬系统的匹配陷阱。