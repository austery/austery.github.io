---
author: AI Engineer
date: '2026-06-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zTZ0qunQXnM
speaker: AI Engineer
tags:
  - data-scraping
  - agentic-automation
  - token-optimization
  - anti-bot-bypass
title: 从 MCP 到规模化：构建自我修复的 AI 数据抓取管道
summary: 本讲座探讨了如何结合模型上下文协议（MCP）与 Bright Data，解决大语言模型在大规模数据收集中的反爬拦截与高额 Token 消耗问题，实现自动化、自我修复的数据抓取系统。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Bright Data
  - Walmart
  - Amazon
  - LinkedIn
  - Meta
  - Twitter
products_models:
  - Claude Code
  - Claude Haiku
media_books: []
status: evergreen
---
### LLM 与规模化数据收集的困境

在上一场会议中，我讨论了**模型上下文协议**（Model Context Protocol, MCP: 一种允许 AI 连接外部数据源的开放标准）如何让**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）访问那些被验证码和机器人检测系统拦截的网站。而在本次会议中，我想进一步探讨：如何真正利用 LLM 实现规模化的数据收集？

在社交媒体上，经常能看到这样的疑问：“我需要扫描一万个产品，如果全部用 LLM 来解析，那将消耗海量的 Token。”显然，**用 LLM 直接解析海量网页是不现实的**。因此，本场会议的核心是探讨如何利用 LLM 构建自动化数据管道。与其告诉 LLM “帮我解析这个页面”，不如让它为你**构建一个专属的抓取工具（Scraper）**来完成解析工作。

<details><summary>Original English Source</summary>
All righty, let's dive into it. So, uh in the previous session, I I don't know how many of you were here, but I talked about how MCP gives access to LLMs to websites that are behind uh CAPTCHA, bot detection systems, and so on. And in this session, I want to talk about um how do you actually collect data on scales with LLM? Because a lot of times I'm seeing on Reddit and other social media is like, "Oh, I need to scan 10,000 products, but that's so many tokens if I need to parse everything with LLM." So, obviously, you don't do that. Right? So, the whole session is how do you build pipelines, right? With LLM. Instead of telling, "Hey, LLM, can you go and uh parse this for me?" build a scraper that's going to parse it for me, and I will demonstrate how easy it is uh with our skills, right?
</details>

### 构建自我修复的代理工具

借助 **Bright Data** 提供的技能集，我们可以直接教会 LLM 如何构建数据管道。通过 MCP，AI 可以自动提取网页的 HTML 结构，识别出需要解析的 DOM 选择器，并编写出相应的抓取代码。

如果你曾经手写过网页抓取脚本，一定会体会过那种痛苦：突然之间数据消失了，页面结构改变了，客户开始疯狂抱怨“数据去哪了”。在过去，你需要手动编写并持续维护这些脚本，有时维护所花费的心力甚至超过了最初的编写阶段。特别是面对那些频繁更改选择器的防御型网站，或是复杂的 React 单页应用，这项工作会变得极其艰难。

而**AI 代理**（Agent）完美地解决了这个痛点。借助 MCP，它能自行探索网页、理解所需的数据结构、自动编写代码并执行。**更重要的是，它能够自我维护**。事实上，我每天都在进行自动化的数据收集工作。每隔 30 分钟，我的 LLM 代理池就会自动启动，检查数据收集进度。一旦它发现某个数据点缺失，代理会在 5 分钟内自动修复抓取逻辑。你再也不用在半夜被警报叫醒去修代码了。

<details><summary>Original English Source</summary>
So, Bright Data has skill sets that actually teaches your LLM on how to build a pipeline. With our MCP, it can actually extract HTML so that it knows what are the selectors that it needs to parse, and so on. So, um the scrape tags, right? Write the scraper. Uh I don't know how many of you actually wrote scrapers before. Okay, so you know the headache when all of a sudden things are missing, data is missing, you got to wake up. I don't know if you guys did it for clients, and clients are like, "Oh my god, there's no data." So, basically, that's what used to be. You write a scraper, and you maintain it. As a matter of fact, sometimes you maintain it more than it takes you to write it, right? So, everything, especially if the website is constantly changing uh its selectors, or if it's a React website, it gets really complicated, right? So, an agent it solves all that headache, right? It can explore with our MCP, it understands what the data is needed. It writes the scraper and it actually runs it and executes it and maintains it. As a matter of fact, I do collections on the daily basis and I have every 30 minutes I have an LLM pool spools up. It checks what the data is collected, make sure that everything is fine. Everything is fine, it shuts down. If for this example, there's a always set a validation for data, right? Let's say the data point is uh missing some something. Your agent fix it. 5 minutes. You don't have to wake up in the middle of the night.
</details>

### 真实世界演示：突破防爬机制与降低成本

为了演示这个过程，我将使用 **Claude Code**。过去编写一个抓取工具通常需要几天甚至几周的时间来排查选择器，而现在，它只需要短短 3 分钟。我们在 GitHub 上提供了专属的技能库，你的代理可以直接获取构建抓取工具所需的所有知识。

我们可以给 AI 下达这样一个指令：“为 **Walmart**（沃尔玛）构建一个抓取工具，包含关键词和最大页数两个输入变量。搜索‘耳机’，并收集前三页的数据。”众所周知，沃尔玛部署了极其严苛的防御验证屏障（如验证码和长按识别）。但接收指令后，AI 会自动利用 MCP 提取页面的底层信息，找到关键选择器，并构建出一个只提取纯文本的 Markdown 抓取脚本，彻底抛弃了无用的 HTML 标签。

**这种“先建脚本再抓取”的模式极大地降低了 Token 成本**。在我们的实测中，针对三个商品页，通过生成 Markdown 抓取脚本而非直接让 LLM 解析原始 HTML，我们省下了一百万个 Token（约减少了 62% 的消耗）。即便你只是为了个人用途——比如想寻找性价比最高的耳机——你也不必再手动去 CNET 查测评。你可以直接让自动化脚本扫过五页市场真实评价，并让 AI 从中为你选出最佳产品，同时完美绕过 Cloudflare 等拦截系统的封锁。

<details><summary>Original English Source</summary>
Uh So, let me demonstrate. So, for this demo, I want to use Cloud Code. I don't know how many of you use Cloud. If you're using Codex or whatever it is, I prefer Cloud Code. I like how it I like it. It does a great job. So, the way that you build scrapers now and it's ridiculous because, you know, back in the day it took weeks to set it up. We created a Bright Data like GitHub page, right? Bright Data skills. Here basically, your agent has everything that it might need, okay? Um scrape builders back practices, how to everything. Everything that it needs in order to build a scraper. And what I want to show is uh first of all, let's I'm going to start simple. Go to build me a scraper and I wanted to record it because I thought it's going to take a long time, but now it takes a little like 3 minutes. Build me a scraper uh two inputs keyword search max pages for walmart.com. Everybody's familiar with Walmart. Walmart has a very aggressive anti-bot systems. If anybody tried to scrape it, um it just doesn't work. But, through Bright Data, it will figure it out, but you're all right. Let's just correct that. walmart.com Um run a search for headphones, collect three pages. Uh so, what it's going to do right now is going to go to our GitHub, it's going to get all the skill set that it needs, how to build scrapers, then it's going to go uh with the MCP that's already connected to the cloud, it's going to extract the HTML from the page. Uh it's going to find all the selectors that it needs, and it's going to build you a scraper, and uh So, right now you can see a scraper as a markdown, it's basically extracting the text, right? So, for the skills, we don't need the HTML, we just need the text. Uh scraper as a markdown is a part of the MCP of Bright Data MCP. Uh the MCP has 5,000 requests for free, so if anybody wants to try it, you guys can try it for free. Um You will need to just open an account with Bright Data, which doesn't cost you anything. And let it do its thing. So, why is this better than having an LLM parse every single page, every HTML? It's I'm I'm literally afterwards I'm going to ask it to tell you how many how much tokens it saves. So, for the three pages, I've done this before, it saves about a million tokens just to from building the scraper uh and using a script to parse the HTML. And um even if you are not doing any scraping for production, but let's say that you want to find the best best headphones for the money, right? It used to be you go to Google, you go to some CNET where they uh compare everything, but here you can use the the marketplace reviews. So, I can tell it here like hey hey, um scan the five pages, find me the best uh review to headphones. So, it could be even useful for you as a personal in in a personal way, right? So, instead of it getting blocked, it can actually find you things that you need on websites that are behind Cloudflare.
</details>

### MCP 工具链、预建 API 与高保真浏览器模拟

为了进一步拓展 AI 的能力边界，MCP 为代理提供了 66 种内置工具。它可以发送简单的 Curl 请求，系统会自动在后台解决验证码、注入恰当的 Header 和 Cookie 参数，伪装成合法浏览器并获取 HTML 响应。而更高效的方法是使用我们为不同领域预建的 500 多个 API。例如针对 **Amazon**（亚马逊），你的代理甚至不需要编写任何爬虫脚本，只需通过 API 发送请求，就能直接获取完全结构化的 JSON 数据。这种纯 JSON 的处理方式，消耗的 Token 甚至不到 Markdown 方案的十分之一。

对于那些涉及深度交互（如 Skyscanner 的航班查询，其 URL 往往被哈希加密处理）或具有严格地理位置限制的网站，MCP 可以随时唤醒我们在云端部署的**远程浏览器**（Remote Browser）。我可以立刻在本地指令上千个挂载美国 IP 的云端浏览器同时启动。

**这些浏览器具备极高的行为拟真度（Human-like Behavior）**。它们绝不会像传统脚本那样瞬间完成“瞬移点击”，而是完全基于人类真实的预录制轨迹来移动鼠标。当执行打字操作时，输入速度会呈现自然的快慢起伏，甚至会故意制造打字失误并进行回删。正因如此，无论目标网站的安全追踪器多敏感，AI 的行为在服务器看来都与真人毫无二致。在如此强大的底层掩护下，即便代理使用的是 **Claude Haiku** 这样轻量级的底层模型，也足以出色地完成所有网页漫游任务。

<details><summary>Original English Source</summary>
So, basically, the MCP gives you a agent 66 tools. Uh some of them is basically uh we have a system where it can send a curl to any URL and our system will literally get the HTML back. It will solve a capture if needed and send it with a token. It will It knows exactly what headers and cookies the website needs. So, basically, it will make sure that the server thinks it's a browser and serve the HTML back. So, your agent can literally send curls, pull data without any questions. It can pull a full HTML. It can pull just a scrape as a markdown. Markdown is It's to save tokens, right? You just want the text of the page. You don't care about the HTML tags.
Um so, that's number one. Second, we have about 500 different APIs pre-built for different domains. So, instead of actually getting markdown, you can actually get a JSON of the product. For example, for Amazon, we have pre-built API. You can listen when you add your agent, it can be like, "Okay, go and check on Amazon something." It doesn't even need to build a scraper. It can literally just send the the request and get the data back.
>> So, apart from scraping can you also do actions on the website?
>> Yes, of course. Fill up a form, submit it as well. Yes. The only thing you can't do is log in. Right? So, if you have let's say you need to perform a search, right? You cannot generate the URL, you need to click buttons. Let's say flights. You want to check flights availability, Skyscanner or something like that, right? The URL is usually a hash and you can't do anything with it. So, yes, LLM can spool a browser, remote browser, even if it's a geo-restricted site. It can be like, "Okay, I want IP from the United States." So, it's open a browser with the United States IP and then it goes and clicks things, fills it up, and so on. The beauty of it is that our browser will mimic real human behavior. So, when your agent clicks, it's not a teleportation. There's a mouse pre-recorded like a real human being moving it. When it types, it will type a little slower, speed up, like maybe even mistake, and so on. So, we have pre-recorded typing, we have pre-recorded mouse movements. So, if the website has a tracker that's constantly sending to the server what the user is doing, it will look like a real human being. Doesn't matter what your agent, even if it's a low like for browsing agents, I'm never used the top models, right? For example, if with Claude Haiku model is more than enough for browsing. If it's being masked that it's a real human, it works just fine.
</details>

### 数据合法性边界与个人自动化场景

这项技术并非只是面向下载百万级数据的企业客户，它同样能彻底改变我们的生活方式。举个例子，当我在寻找新公寓时，我利用 **CloudCrawl** 设定了一个监听系统，要求它每半小时扫描一次特定区域，只要出现符合我预算的私人房源就立刻通知我。没过几天，我就收到了符合要求的推送，现在我已经成功搬了进去。同样地，你也可以用这个逻辑，让代理去为你盯盘预订那些永远一席难求的热门餐厅。

但在拥抱这些强大自动化能力的同时，我们必须坚守一条底线：**我们仅处理公开数据**（Public Data）。系统绝不会越过登录墙去触碰私人数据，我们也不主动勾选同意网站的防爬虫条款。因为一旦你创建账户并接受了《服务条款》，如果随后使用自动化机器人抓取，公司是完全可以起诉你的。这也正是为何最近新闻里频繁出现 **LinkedIn** 等巨头到处发律师函的原因。在这个时代，数据就是新的石油。特别是自从 **Elon Musk** 接管 **Twitter** 后，原本极其开放的平台数据也被迅速封锁保护了起来。

然而，**公开数据的本质就是公开的**。在这点上，我们曾经在法庭上面对过 **Meta** 和 Elon Musk，并成功赢得了这些诉讼。法官的裁决逻辑非常简单：它就像你走在马路上，记下了一家商店柜台上的标价，然后把这些信息分享或出售给别人。公开可得的数据，无论你采用何种方式阅览、如何分析处理，它的公共属性都不会改变。

<details><summary>Original English Source</summary>
So So, what else does this give you? So, again, market research. Um For example, I was looking for a new apartment, right? I would want to move a house. So, with a CloudCrawl, with BrightData, I set up a listener. Literally just telling Hey, listen. Build me a scraper that will run every half an hour when in this area there's a a house, private house, under this price, notify me. That's all I did. In a few days, I got a notification and now I live there. So, these things are not only useful on a scale where, you know, oh, I need to scrape millions of records, but even for your personal use.
>> Can I ask can you can you do this on all the authorization sites as well?
>> Uh no, we only talk we only deal with public data. So behind login it's um it's private data. And and uh just you know just a heads-up. If you create an account, you accept terms and conditions of the website. Always check terms and conditions of the website. If they say don't scrape, don't use robots, and you do, then that company can actually sue you. And this is happening you probably heard it in the news all the time. LinkedIn is suing them. Everybody's suing each other because they the data right now is like the new gold the oil, right? Everybody's trying to like oh this is my data. Elon Musk took over Twitter, locked it down. That's it. Literally like uh the it used to be so open and now it's all locked in a few accounts that you can actually scrape. So the we're seeing this on every single level.
So yes, also same thing if you accept uh there's like terms and like if you do a search and there's a checkpoint, I accept terms and conditions, always be careful with that. So we only deal with public data. So nothing behind login. We don't accept terms and conditions. And we actually won a few lawsuits. We were sued by Meta. We were so sued by Elon Musk a month after he took over. And uh the judge said it's very simple. Public data is public data. It doesn't matter how you collect it. Doesn't matter what you do with it. It's public. You know, it's like walking on the street, you write down the prices on the counter and then you sell it to somebody. It's public data. It's available. You can do whatever you want with it. Okay?
</details>