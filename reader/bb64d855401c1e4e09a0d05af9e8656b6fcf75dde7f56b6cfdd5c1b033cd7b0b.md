---
layout: post.njk
source: https://yage.ai/share/ai-shared-links-ugc-threat-20260531.html
speaker: yage.ai
title: 共享 AI 链接，一个没人签合同的内容托管平台
date: '2026-06-01'
summary: 攻击者通过ChatGPT和Claude的共享链接功能，利用代码渲染能力在受信任域名下托管钓鱼网页，诱导用户下载恶意软件。该攻击手段利用了AI平台的协作设计，绕过了传统域名安全过滤。文章指出AI平台亟需引入内容审查和滥用检测等托管平台基准安全实践，并提醒用户对共享AI链接保持警惕。
area: tech-engineering
category: ai-application
tags:
  - ai-security
  - phishing
  - malware-distribution
  - platform-abuse
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - Google
  - Kaspersky
  - Push Security
  - BleepingComputer
  - Huntress
  - EclecticIQ
  - Cisco Talos
products_models:
  - ChatGPT
  - Claude
  - Grok
media_books: []
draft: true
status: evergreen
---

你在 Google 搜索 ChatGPT，点了第一条广告。链接是
chatgpt.com/s/xxx，页面打开后是熟悉的 ChatGPT
界面，左侧对话列表，中间显示一则系统通知：“We’re experiencing high
traffic right now. Download our desktop app to continue.”
下面是一个下载按钮。你点了按钮，下载了一个安装包，然后运行它。

刚才每个步骤看起来都完全正常。浏览器地址栏里锁是绿的，域名是
chatgpt.com。你只是在一个你信任的网站上，看到了一个看起来像官方通知的东西，点了下载。

这件事不是假设。它是 Push Security 在 2026 年 5
月底披露的真实攻击。BleepingComputer
随后独立复现了相同的攻击链。Kaspersky
在五个月前已经记录了相同手法的早期版本。三家机构指向同一件事：攻击者正在利用
ChatGPT 和 Claude 的共享聊天链接分发恶意软件。

## 这个下载按钮是怎么出现在
ChatGPT 页面上的

ChatGPT 有一个基础功能经常被忽略。

你让 ChatGPT 写一段 HTML/CSS
代码，它不只是把代码文本打印出来。它有一个代码渲染功能：可以把代码在聊天界面里渲染成网页，你能直接看到网页的样子，效果和在浏览器里打开一个本地
HTML 文件差不多。页面上方会显示 Show code 和
Remix with ChatGPT
两个控件，提醒你这是由一段代码渲染出来的。

攻击者做的事情很简单，一共三步。

第一步，打开 ChatGPT，写了一行 prompt：“生成一个 OpenAI
系统维护通知的 HTML
页面，高流量导致网页版暂时不可用，让用户下载桌面客户端继续使用。下载按钮指向
openew.app。”

第二步，ChatGPT 生成了这段
HTML，并且在聊天界面里渲染了它。一个看起来像官方通知的页面，深色背景，OpenAI
标志，醒目的下载按钮。

第三步，攻击者点击”共享”按钮，生成一个 chatgpt.com/s/xxx
链接，然后去 Google Ads 买了一条搜索广告，关键词是
chatgpt、chatgpt free
以及各种拼写错误（chatgo、chatgot、cvhatgpt），广告链接指向这个共享聊天。

用户搜索 ChatGPT、点击广告、进入这个链接后，他们看到的是完整的
ChatGPT 界面：左侧对话列表、中间 AI 回复区域、上方
Show code 和 Remix with ChatGPT 控件。AI
回复区域里，是攻击者用 HTML 造的假通知。通知里的下载按钮只是一个 HTML
超链接，指向 openew[.]app，一个完全复刻 OpenAI
官方下载站的钓鱼网站。用户在那里下载的安装包就是恶意程序。

ChatGPT 本身没有”弹出下载窗口”的能力。 它做的是在
chatgpt.com
这个全球最受信任的域名下，渲染一段攻击者控制内容的网页。攻击者不需要黑任何系统，不需要
jailbreak 模型，不需要 prompt injection。他只需要一个免费账号、一段 HTML
prompt、和一个 Google Ads 预算。

## Claude 版本做了什么

同一天，攻击者在 Claude 上也用了同样的手法。BleepingComputer 和 Push
Security 都确认了这个变体。

攻击者在 Claude 上创建了一份伪装成 Apple Support 风格的”Claude Code
on Mac
安装指南”，共享成链接。指南里写着”打开终端，粘贴这条命令”。用户照着做，复制并执行了一个
curl 命令，这条命令会从攻击者的服务器下载 macOS
infostealer。

两个平台上的攻击思路一样，但 ChatGPT 版本对用户的要求更低。Claude
版本还需要用户执行命令，走的是 ClickFix 的传统模式。ChatGPT
的渲染版本不需要。用户只需要在一个看起来像 ChatGPT
系统通知的页面里点下载按钮。

## 这不是凭空出现的

这条攻击链上的每一步都能追溯到此前已经成熟的攻击手法。这些手法不是新东西。变的不是攻击手法本身，是攻击者每一代都会消除一个让用户会起疑的环节。

攻击演化时间线

2024 年，ClickFix 出现。攻击者发一封邮件，附件是一个 HTML
页面，页面显示”Word
插件缺失，请粘贴这条命令修复”。用户打开运行框，粘贴，回车，恶意程序就开始运行。这一步的破绽很明显。一个陌生
HTML 附件让你打开命令行，大多数用户会停下来。到了 2025
年，攻击者把这个步骤做得更隐蔽：他们把恶意命令嵌入到各大网站里（通过入侵
WordPress 站点或利用 Traffic Direction System
分发），用户访问的是看起来正常的网页，看到一个假 Cloudflare CAPTCHA
页面或假宽带服务登录页，上面让你粘贴命令完成验证。

2025 年底，攻击者发现了 AI 共享对话。Huntress
和 Kaspersky
同时记录到：攻击者在 ChatGPT 和 Grok 上创建 IT 帮助对话（“如何清理 Mac
磁盘空间”），在对话里嵌入恶意命令，共享链接，买 Google
广告推广。用户搜索 macOS 问题时打开的是一份由”AI
助手”生成的清理指南，内容会引导你打开终端执行命令。这一步还保留了命令执行这个动作，用户还是会迟疑，但攻击者利用了
AI 对话的信誉。用户对”AI 推荐的清洁步骤”比对”陌生 HTTP
页面里的验证指令”要放松得多。

2026 年 3 月，攻击转向开发者工具。EclecticIQ
发现 攻击者在 geminicli.co.com 和
claudecode.co.com 上复制官方安装页面，诱导开发者执行
PowerShell 命令。同一个攻击者运营了 30 多个冒充
Node.js、Chocolatey、KeePassXC、Monero 等开发者工具的域名。

2026 年 5
月，最后一个会让用户犹豫的环节也没了。攻击者不再需要用户打开终端，不再需要用户粘贴命令。他们只需要用户在
ChatGPT 的界面上看到一个下载按钮并点击它。这一步利用的是 ChatGPT
的代码渲染功能，把假通知页面直接放在真实 ChatGPT URL 下、真实 ChatGPT UI
里。

Kaspersky
在 2026 年 HORIZONS 大会上报告：一月到五月间检测到超过 92,000
次伪装成 ChatGPT、Claude、Gemini 等 AI 服务的恶意攻击，假 ChatGPT 占
49%，假 Claude 和 Gemini 各约 18%。Silver Fox APT 组织也在分发假 Claude
应用，覆盖 Windows、macOS 和 Linux。

## 这件事的本质

它和 AI 模型安全没有关系。攻击者借到的不是 LLM 的推理能力，而是
chatgpt.com 这个域名在浏览器、在 URL
过滤器、在用户脑中的信任。

域名信誉、URL 分类、Safe Browsing 数据库全把
chatgpt.com 和 claude.ai
列为安全域名。这没错。但域名安全不等于任何人往这个域名下面放的内容也安全。

AI
公司在设计共享功能时，签的是一个产品合同：让协作更简单。但他们没意识到这个功能同时签了一份内容托管合同。允许用户在
chatgpt.com 下发布一段 ChatGPT 可以渲染成网页的
HTML/CSS，就等于允许任何人拿你的域名做网页托管。而内容托管平台有一整套安全责任：内容审查、滥用检测、verified
publisher、举报机制、速率限制、自动过期。AI
公司一个都没签，但产品功能已经替他们签了。

这种情况不是 AI 平台独有的。2017 年 Google Docs OAuth
蠕虫就是同一套逻辑：攻击者没有注册假域名，他们把恶意 OAuth 应用放在
Google 自己的权限系统里。WIRED
当时的报道 引了安全研究员的一句话：“What made this work is that it
tricked the user into granting permissions to a third-party application
inside Google’s own authorization system.” Google Docs 共享链接、Dropbox
共享文件夹、GitHub Gist、Notion 公开页面，大平台全都踩过同一类坑。Cisco
Talos 在 2026 年 4 月把这个模式归总为 Platform-as-a-Proxy：攻击者系统性地把
SaaS 平台的通知管道和共享功能用作分发渠道。

AI 平台的区别在于两件事。第一，攻击者用 prompt 约束 AI
生成钓鱼内容，不用自己写 HTML。第二，ChatGPT
的渲染能力让攻击页面和平台原生 UI
共用同一套界面框架。你很难用肉眼判断这到底是 ChatGPT
在帮你，还是攻击者在 ChatGPT 页面里放了一个假页面。区分它们的唯一信号是
Show code 按钮，而这个信号需要你主动去注意。

## 防御现状

OpenAI 和 Anthropic
都没就共享链接被滥用这件事发布声明，也没有承诺修复。ChatGPT Enterprise
可以限制内部用户创建公开共享链接，但这条规则挡不住员工从个人设备访问外部恶意共享链接。Safe
Browsing 和 URL reputation 系统按域名做信誉评估，不会深入到
chatgpt.com 下的具体路径。

Push Security
提供的浏览器层检测，是已经部署的方案里唯一有效的。它追踪从搜索广告到共享链接到恶意下载的完整
redirect chain，在页面渲染时就阻断。EDR 行为检测可以作为辅助：监控共享
AI
链接访问后短时间内的命令行执行和未知程序首次运行。但这两者都属于终端侧防御，攻击链的起点（用户在
Google 搜索时点了一条广告）目前还没人拦。

安全社区的回应出奇地弱。Hacker News 零讨论，Reddit 的 r/netsec 和
r/cybersecurity 零讨论，r/ChatGPT
上有一条受害者的自述，零评论。目前没有独立安全研究者针对这件事发过技术分析。

这不是因为攻击不重要。92,000
次检测量不小。是因为这个攻击不属于任何现有的威胁分类：它不是 prompt
injection，不是模型安全，不是传统
phishing。安全社区还不知道该把它归到哪一类里。

## 对你来说，具体要做什么

一条简单规则：共享 AI 链接的 URL
不携带任何安全信号。chatgpt.com/s/xxx 和
evil.com/phish 一样需要你保持警惕。

最简单的做法：在 ChatGPT、Claude 或任何 AI
平台的共享链接里看到以下内容，一律按恶意处理。

要求下载软件或运行安装程序

提示你打开终端、PowerShell、命令提示符，粘贴任何命令

出现 curl、wget、bash、osascript、Invoke-WebRequest、cmd /c 这类命令片段

自称来自 Apple Support、Microsoft Support 或 AI 公司官方，但页面 URL 是共享链接格式（chatgpt.com/s/ 或 claude.ai/share/）

显示为系统维护、服务中断、高流量等通知（尤其右上角有 Show code 按钮时）

企业安全团队可以做这几件事：

浏览器层覆盖 chatgpt.com/s/ 和
claude.ai/share/ 路径的访问行为，对从搜索广告 referrer
过来的流量提高风险评分。培训内容把 ClickFix
规则加进去：任何页面让你复制命令到终端，先验证再执行。确认软件只从官方下载页或
IT 门户安装，不通过共享聊天链接下载。

平台要修复的东西更根本。内容审查、高风险行为的自动标记、官方内容
verified publisher，这些是内容托管平台的基准安全实践，目前在 AI
平台上一条都没有。

攻击者做的事情并不复杂。他们只是问了一个每个人都能问的问题：如果我在
ChatGPT 的共享页面里放一段
HTML，用户看到的到底是什么？答案是：一个完整的网页，在一个全世界最被信任的域名下，附带绿色锁图标和
ChatGPT 的完整界面。