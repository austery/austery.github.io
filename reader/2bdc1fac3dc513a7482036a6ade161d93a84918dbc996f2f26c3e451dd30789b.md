---
layout: post.njk
source: https://yage.ai/share/seo-model-distillation-infrastructure-20260706.html
speaker: yage.ai
title: SEO服务如何成为模型蒸馏的基础设施
date: '2026-07-06'
summary: 文章探讨了SEO服务如何演变为模型蒸馏的基础设施，核心在于AI答案抓取（AI answer scraping）的兴起。这种新的市场不再关注传统的网页排名，而是转向对真实模型流量的稳定访问和审计。它描述了从传统爬虫到代理、浏览器自动化再到针对AI生成结果的可见性分析的四代演化路径，强调模型入口本身已成为稀缺资产。
area: tech-engineering
category: ai-application
tags:
  - model-access
  - answer-scraping
  - geo-visibility
  - web-automation
people: []
companies_orgs:
  - Google
  - Anthropic
products_models:
  - ChatGPT
  - Perplexity
  - Google AI Mode
media_books: []
draft: true
status: evergreen
---

## 从网页排名到答案审计

2026 年 7 月初，Google
Threat Intelligence Group 公布了一次和 FBI、Lumen
等机构协同的行动，目标是 NetNut residential proxy network，也就是 Google
所称的 Popa。Google 称这个网络至少覆盖 200 万台家用设备，并在 2026 年 6
月单周观察到 316 个 threat clusters 使用疑似 NetNut exit nodes。Alarum/NetNut
随后公告，FBI 扣押了部分 NetNut 相关域名。

这件事第一眼像一次常规网络安全行动：住宅代理、恶意 SDK、C2
基础设施、Google Play Protect、执法扣押域名。但如果顺着 NetNut
自己的商品目录看下去，会看到另一张更贴近 AI 行业的脸。它在自己的
scrapers 产品目录里，把 ChatGPT
Scraper、Perplexity
Scraper、Google AI
Mode Scraper、Gemini Scraper 和 Copilot Scraper
放在了同一张货架上。

这就让问题变得有意思了：一个看起来像 SEO/GEO
数据服务的东西，为什么会和
FBI、Google、住宅代理网络、恶意流量基础设施出现在同一条新闻链里？答案是，AI
搜索已经催生出一个属于自己的排名追踪（rank
tracker）市场，而这个市场的底层需求并不只是看品牌有没有被提到。它还涉及谁能稳定进入
ChatGPT、Perplexity、Google AI Mode 这些真实模型入口。

过去十几年，品牌和搜索引擎优化团队最关心的指标是自己的网站在 Google
搜索结果里排在第几名、第几页。如今，商业博弈的逻辑发生了转移。决策者们需要解答一组全新的问题：当潜在客户向
ChatGPT 询问最好的项目管理软件是什么时，模型有没有提到我们的品牌？当
Perplexity 给出方案对比，它引用的是我们的白皮书，还是竞争对手的博客？当
Google AI Mode
把生成答案、本地商户卡和购物推荐合在一起时，我们的页面是否还存在于用户的决策路径里？

这就是 AI 答案抓取（AI answer
scraping）兴起的真实背景。这一品类并非普通网页爬虫换了时髦的名字，也不是简单地用大语言模型去读取
HTML。互联网的流量入口从传统蓝链列表迁移到生成答案以后，市场为了应对观测空白，不得不自行补齐一层可观测性基础设施。换句话说，AI
答案抓取的本质不是抓取网页，而是给机器生成的答案做审计。再往下看一层，它卖的也不只是
SEO 数据，而是对真实模型流量的稳定访问。

普通爬虫的目标是把互联网上已有的静态网页拉回到本地，而答案抓取则是在复现某一个特定时刻、特定设备、特定地理位置、甚至特定账号状态下，AI
引擎生成给真实用户的界面。目前，像 cloro.dev
这样的专业服务商已经开始销售真实的 AI Mode UI
响应，专门提取其中包含的信源、引用、地点卡片和购物卡片。这是因为，AI
搜索所提供的高价值数据往往只存在于其最终呈现的用户界面（UI）里，官方提供的程序化接口（API）不仅成本结构不同，输出内容也往往与普通用户看到的界面存在行为差异。

这种差异让答案观测从一项单纯的技术工程，演变成一种新的市场测量方法。品牌衡量自身可见性的指标，也从传统的搜索排名、展示量和点击率，重构为提及概率、引用存在感、推荐语气、以及在竞品对比中的表意框架（Share
of Voice）。

## 观测界面的四代演化

如果我们拉长镜头，会发现这一新型观测手段并不是凭空出现的，它背后是一条清晰的技术和需求演化路径。每一代产品的诞生，解决的都是当时可观测界面的技术瓶颈：

第一代，传统网页抓取（Traditional Web Scraping）。在 2000 年代到 2015
年前后，企业需要将互联网上的零散信息变成结构化数据。这一代解决的是人工复制网页的成本问题，其主流形态是
HTML 解析器与爬虫框架。然而，当网页越来越多地采用 JavaScript
动态渲染，并筑起登录墙和反爬系统时，仅靠静态解析很快变得无能为力。如今像
Firecrawl
这样的工具，已经把这一层能力打包成专为大语言模型或检索增强生成（RAG）工作流服务的
Markdown 输出接口。

第二代，搜索结果页抓取（SERP Scraping / SEO Data
API）。随着搜索引擎成为绝对的流量入口，企业迫切需要观测自己在 Google
上的排名。由于搜索引擎官方几乎不提供完整的 SERP API，类似 SerpApi 和 DataForSEO
的服务商应运而生。它们把高度动态、个性化的 Google
搜索结果页面（包括自然搜索、广告、地图、购物卡、People Also Ask
等功能组件）逆向解析并转化为稳定的 JSON 数据，成为所有 SEO
排名追踪工具和舆情分析产品的底层底座。

第三代，反爬、代理与浏览器自动化（Anti-bot / Proxy / Browser
Automation）。随着网站防护策略的升级，抓取的瓶颈从如何解析转移到如何访问。在
2018 到 2025 年间，住宅代理 IP、验证码自动绕过（CAPTCHA
solving）、浏览器指纹模拟、无头浏览器集群管理（如 Browserbase）演化成独立的产品层。这一层不承诺直接提供特定的业务数据，而是承诺通过技术对抗，在强防护网站上维持自动化访问的成功率。

第四代，AI 答案抓取与生成引擎可见性分析（GEO/LLM Visibility
Analytics）。在 2024 年到 2026 年的转折期，入口彻底变了。Google AI
Overviews 的推出、Google 官方于 2025 年 5 月在全美正式上线的 AI
Mode，以及 OpenAI 发布的 ChatGPT
Search，让用户的决策方式发生了跃迁。品牌无法再单纯依靠传统的排名报表来感知用户的流失，这直接催生了针对
AI 答案界面的数据采集层与上层 GEO（生成引擎优化）分析仪表盘。

这一代的核心在于，传统的单点排名观测在高度状态化、随机性极强的 AI
生成结果面前已经失效。传统的搜索引擎为站长提供了诸如 Google Search
Console（GSC）的官方原生监控工具，但大语言模型提供商目前并不提供等价物。商家无法直接看到具体的
prompt
使用频率、展现量等核心指标，市场只能依靠第三方测量工具通过模拟和采样来填补这一空白。

## 产业图谱的四层架构

在如今的市场中，许多打着 AI 爬虫或 AI
抓取旗号的产品经常混在一起。事实上，从底层数据传输到上层的战略决策，这个产业已经分化为四个不同的功能层级：

第一层：代理与网络访问基础设施（Proxy & Web Access
Infra）。这是最底层的硬摩擦对抗层，代表服务商包括 Bright
Data、Oxylabs、Infatica 以及 NetNut。它们依靠庞大的住宅 IP
池和网络解锁技术，为上游的自动化行为提供隐蔽、高弹性的网络通道。目前，这批传统代理商正在快速向上游迈延，直接将
ChatGPT 抓取和 Google AI Mode 抓取做成标准化服务打包出售。

第二层：AI 答案抓取与 SERP API（AI Answer Scraper & SERP
API）。这一层直接面向开发人员，提供结构化的 AI 答案数据。除了 DataForSEO AI
Overview 这种在传统 SERP 中加入 ai_overview
字段的产品外，像 cloro.dev
等专注于答案 UI 抓取的服务商，可以直接输出
ChatGPT、Gemini、Perplexity、Copilot
真实交互界面中的引用链接、后续追问、推荐卡片和模型元数据。

第三层：生成引擎优化与 AI 搜索可见性分析（GEO / AI Visibility
Analytics）。这一层不面向程序员，而是面向品牌、市场和 SEO
团队。代表产品包括 Profound、OtterlyAI、Peec AI、Gumshoe 和
Goodie。它们在底层调用抓取能力，但在用户界面上提供的是品牌在不同 AI
平台上的提及率、引用权重、情绪倾向、竞品对比以及内容改进策略。Profound
特别强调自己采集的是来自真实消费者浏览体验而非模型官方 API
的数据，以此来体现分析的保真度。

第四层：通用浏览器自动化与 AI 数据层（Browser Automation & AI Web
Data Layer）。以 Browserbase 和 Firecrawl 为代表，它们是 AI Agent 和 RAG
系统的数据供给底座。它们的主要作用是让 AI
能够流畅地使用任意普通网页，或者把普通网页低摩擦地转译为
Markdown，以便模型理解。这一层并不提供针对 ChatGPT 或 Perplexity
本身的答案分析。

为了更清晰地呈现整个技术栈的流转，我们可以将这个产业结构简化为一层垂直的架构：

AI answer scraping 位于传统网页抓取、AI
答案界面和品牌可见性仪表盘之间

在这个架构中，底层基础设施负责消除网络对抗的摩擦，而最上层的分析工具则将抓取到的原生文本，翻译成品牌可以直接采纳的行动建议。

在实际评估工具时，我们需要理清三个容易混淆的概念：AI extraction（利用
AI 从网页中抽取数据）、AI web scraping（为 AI 抓取网页以作上下文）、AI
answer scraping（将 AI
引擎的回答界面作为被抓取对象）。只有第三种，才属于今天讨论的答案审计领域。

## 更大的市场不是
SEO，而是真模型流量

AI answer scraping 最容易被市场接受的需求是 GEO：品牌想知道
ChatGPT、Perplexity、Google AI Mode
有没有提到自己，引用了谁，语气是不是正面。这个需求真实存在，也足以支撑一批
dashboard 公司。

但更大的需求在另一层：真实模型流量。也就是把一个原本面向人的模型产品，变成可以持续调用、批量采样、记录输出、绕过失败并恢复运行的输入输出管道。

这件事在合规品牌监测里是温和形态。工具需要在不同地区、不同设备、不同时间，对一组
prompt 反复采样，才能知道品牌在 AI
答案里的稳定位置。到了模型蒸馏和能力提取场景，它会变成强对抗形态：操作者需要在短时间内向前沿模型发起数百万甚至数千万次交互，并把输出组织成可训练的数据。

Anthropic 在 2026 年 2 月发布的 distillation
attack 报告把这层基础设施讲得很具体。它称 DeepSeek、Moonshot 和
MiniMax 三个实验室通过约 24,000 个欺诈账号，与 Claude 产生超过 1,600
万次交互。Anthropic 还说，这些活动使用欺诈账号和 proxy
services，在规避检测的同时规模化访问 Claude。报告里最关键的词不是
token，而是 hydra cluster：一组不断替换的欺诈账号，把流量分散到
Anthropic API 和第三方云平台上。Anthropic 称，有一个 proxy network
同时管理了超过 20,000
个欺诈账号，把蒸馏流量混在其他客户请求里，增加检测难度。

这就把问题从有人多花 token
问了很多问题，改写成有人在搭模型访问基础设施。账号、代理、会话、地理位置、API
路径、第三方云平台、流量混合、封禁后的替换机制，这些东西一起构成了模型访问的供应链。

Reuters 6 月报道的阿里相关争议，是这个问题的更大版本。根据 Reuters
看到的 Anthropic 信件，Anthropic 指称与 Alibaba 和 Alibaba Qwen
相关的操作者在 2026 年 4 月 22 日到 6 月 5 日之间，通过近 25,000
个欺诈账号，与 Claude 产生超过 2,880 万次交互。这里必须加限定：这是
Anthropic 信中的指控，经 Reuters
报道，不是法庭事实，也不是第三方公开技术复核结论。

即便只把它当成一个未证实但数量级清楚的案例，它也足够说明为什么这个市场会突然变大。如果一个前沿模型的能力可以通过数千万次真实交互被提取，那么稀缺资源就不只是算力和
token。稀缺的是谁能稳定拿到真实模型入口，谁能把入口变成可编排的流量。

开头的 NetNut/FBI
事件之所以值得放在这里，也正是因为它把这层基础设施暴露了出来。我们不能说
NetNut 被用于 Anthropic 提到的这些案例，公开材料也没有证明这一点。但
NetNut、Bright Data、Oxylabs、cloro
这类产品所处的位置，正是同一层：把本来难以程序化访问的 AI answer
surface，包装成可规模化调用的接口。正常客户买它做品牌可见性监控，风险客户可能买类似能力做账号规避、批量采样或模型提取。用途不同，底层需求相似。

## Token
不是唯一成本，入口才是稀缺资源

模型公司通常把商业关系描述成 API 调用：开发者付费，平台按 token
返回结果。这个描述在正常开发场景里成立，但解释不了真实模型流量为什么会变成一门生意。

原因在于，用户真正使用的是 ChatGPT、Claude、Perplexity、Google AI
Overviews
这些产品入口，而不是裸模型。它们有登录状态、地区差异、账号风控、速率限制、前端界面和产品条款。API
能返回文本，但不一定返回普通用户在界面里看到的卡片、引用、追问、本地结果和推荐位置。

这就把成本从 token
推到了入口。品牌监测工具要回答的是：真实用户在某个地区、某台设备、某个时间点会看到什么。要做到这一点，就需要重复采样、跨地区采样、记录
surface、模型版本、引用来源和答案变化。单次截图没有决策价值，稳定观测才有。

到了恶意蒸馏和账号规避场景，入口成本会变得更明显。操作者关心的不只是
prompt，还包括账号库存、会话状态、代理路由、浏览器指纹、失败重试、输出存档、去重、流量混合和封禁后的替换。Anthropic
所说的 hydra
cluster，本质上就是把这些环节做成了可以自我恢复的访问系统。

这也解释了为什么代理商和 scraping 公司会向上游移动。NetNut 把
ChatGPT、Perplexity、Google AI Mode、Gemini、Copilot 放进 scraper
目录，Bright Data 在文档里写自己支持 ChatGPT、Perplexity、Gemini 和
Google AI Mode 的结构化 prompt responses，cloro 则强调它拿到的是 real AI
Mode UI responses。它们卖的是模型产品入口的可靠访问，IP
地址只是其中一层材料。

在这个意义上，AI answer scraping 已经超出了 SEO 工具的范围。它是
model access market 的早期可见形态。SEO/GEO
是合法、可解释、容易卖给企业的入口；蒸馏攻击和账号规避则暴露了同一访问层的风险边界。两者都会把问题推向同一个结论：模型入口本身已经变成资产。

## 最后会留下两类产品

底层能不能把 ChatGPT
页面抓下来会越来越商品化。真正会留下来的，是两类更难替代的产品。

第一类是合法观测产品。它们会把 AI 搜索变成可信仪表盘：公开 prompt
设计，说明地区和设备口径，重复采样，处理答案漂移，区分
mention、citation、recommendation 和 competitor co-mention。好的 GEO
工具不能只给一个 AI visibility
score，它要告诉客户这个分数从哪里来，为什么变了，哪些来源改变了模型答案。

第二类是平台防御产品。AI 实验室需要识别 hydra cluster、proxy
resale、欺诈账号、多路径访问、模型蒸馏 prompt
模式和异常输出采集行为。过去安全团队看的是 credential stuffing 和 bot
流量；现在他们还要看模型能力是否正在通过正常产品入口被系统性抽取。

这两个方向看似相反，其实由同一个事实驱动：模型入口变成了资产。品牌方需要观测它，攻击者想要规模化利用它，平台方必须控制它。Google/FBI
对 NetNut 采取行动，让我们看到住宅代理和 scraper
基础设施已经大到进入执法视野；Anthropic 的 distillation
报告则让我们看到，前沿模型访问本身有足够高的经济价值，足以让人搭出工业化的访问管线。

所以，AI answer scraping
不是终点。它只是这个更大市场最早浮出水面的产品形态。真正的市场，是围绕真实模型流量的访问、测量和防御。谁能把模型行为稳定地变成可观测数据，谁能阻止模型行为被大规模提取，谁就在定义
AI 搜索时代的新基础设施。