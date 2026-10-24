---
author: AI Engineer
date: '2026-06-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=btxGmN8RvNU
speaker: AI Engineer
tags:
  - web-scraping
  - llm-hallucination
  - mcp
  - anti-bot
title: 你的智能体最大的谎言：'我搜过网页了'
summary: Bright Data 的 Rafael Levi 深入探讨了大型语言模型（LLM）在执行网页搜索时经常产生幻觉的根本原因：为了取悦用户，它们在遇到反爬虫机制（如验证码或 Cloudflare 的 AI 迷宫）时会编造数据。他通过实机代码演示，对比了有无 MCP 支持下智能体访问真实网页的巨大差异，展示了如何通过模拟人类行为来可靠地收集实时公开数据，解决 AI 智能体数据缺失和误导的隐形失败问题。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people:
  - Rafael Levi
companies_orgs:
  - Bright Data
  - Cloudflare
products_models:
  - GPT-5
  - ChatGPT
media_books: []
status: evergreen
---
### LLM 的取悦机制与幻觉

**Rafael Levi**: 好的，那我们就这样开始吧。这是一个小房间。大家好。欢迎你们。我的名字是 **Rafael**。我代表 **Bright Data**。**Bright Data** 基本上是一个网络访问平台，用来帮助智能体或任何人进行大规模的公开数据收集。

<details>
<summary>Original English</summary>

**Rafael Levi**: Okay, so let's just work with it like this. It's a small room. Hi everybody. Welcome. My name is Rafael. I represent Bright Data. Bright Data is basically web access platform to help agents or anybody collect public data on scale.

</details>

**Rafael Levi**: 我今天来到这里，是为了谈论 LLM（大型语言模型）如何误导人们，并一直试图说服他们：“嘿，我做过搜索了。嘿，我做了这件事。” 然而它其实并没有做。为什么？因为 **LLM 的程序设定就是要取悦人们，取悦用户**。

<details>
<summary>Original English</summary>

**Rafael Levi**: And I'm here to talk about the LLMs misleading people and all the time convincing them, "Hey, I did a search. Hey, I did this." While it didn't. Why? Because LLMs are programmed to please people, please users.

</details>

**Rafael Levi**: 所以它们会编造很多东西，这也是我现在看到的 LLM 存在的最大问题。我一直都在开发应用程序。我宁愿 LLM 告诉我：“不，我做不到。” 但它从不这么做。它总是试图凭空捏造。

<details>
<summary>Original English</summary>

**Rafael Levi**: So they make enough things and this is the biggest issue right now I'm seeing with LLMs. And I'm building applications all the time. I would rather LLM tell me, "No, I can't." But it never does. It always tries to make things up.

</details>

### 网络如何对抗机器人

**Rafael Levi**: 所以目前，互联网实际上正在对抗机器人和自动化程序。这也是一件已经持续了多年的事情。每个人都知道验证码（CAPTCHA）。第一批验证码出现在大概十年前。

<details>
<summary>Original English</summary>

**Rafael Levi**: So currently the web is actually fighting the robots and automations. And it's been something that going on for years. Everybody knows CAPTCHAs. The first CAPTCHAs showed up year 10 like, you know, decade ago.

</details>

**Rafael Levi**: 并且这种情况还在不断发展。现在我们甚至看到了 **AI 屏蔽 AI** 的情况，这简直是一个全新的世界。网络访问实际上并不像看起来那么简单。所以它们（智能体）会遇到验证码，而且它们实际上并不会报告遇到了验证码。

<details>
<summary>Original English</summary>

**Rafael Levi**: And it just keeps growing. And now we have AI blocking AI and there's a whole world going on. And the web access is actually not as simple as it looks. So they're getting CAPTCHAs and they don't actually report CAPTCHAs.

</details>

**Rafael Levi**: 于是它会试图去用不同的方式寻找数据。有时候它会去查阅它的训练数据。而这就是最糟糕的事情发生的地方。当它使用训练数据并告诉你这是当前的状况时。**它的训练数据是来自 2024 年的。而我们现在是在 2026 年**，这根本对不上，对吧？

<details>
<summary>Original English</summary>

**Rafael Levi**: So it tries to go and find the data different way. Sometimes it goes into training data. And this is where the worst thing is. When it uses training data and tells you that this is the current situation. Training data is from 2024. We're in 2026 and it doesn't add up, right?

</details>

**Rafael Levi**: 所以这些是我刚刚才查看过的一些新事物，对吧？比如 **Cloudflare** 屏蔽了 AI 对大约 20% 网络的爬取，对吧？也就是说，有 20% 的网络，AI 是无法通过内置的默认抓取机制访问到的。

<details>
<summary>Original English</summary>

**Rafael Levi**: So these are some of the new things that I was just literally checking out, right? So Cloudflare blocks AI crawling for about 20% of the web, right? So 20% of the web is literally not accessible by AI by default fetch that's built into it.

</details>

**Rafael Levi**: **Cloudflare** 现在还发布了一个 **AI 迷宫（AI Labyrinth）**，用来真正地困住机器人，误导它们，并为它们提供假数据。这样一来，你得到的结果就会变得更糟。

<details>
<summary>Original English</summary>

**Rafael Levi**: Cloudflare also right now released an AI labyrinth to actually trap bots and mislead them and provide to them fake data. So, then your results are getting even worse.

</details>

### 隐形失败与伪造的来源

**Rafael Levi**: 明白了吗？这就是所谓的“隐形失败”群体，对吧？没有任何报错，没有任何警告，只有错误的答案，对吧？所以，智能体发送了一个请求，它遇到了一个验证码，甚至是一个空白页面，但它不会告诉你：“嘿，我刚刚只拿到了一个空白页面。”

<details>
<summary>Original English</summary>

**Rafael Levi**: Okay? So, the invisible failure group, right? There's no error, no warning, just the wrong answer, right? So, the agent sends a request, it gets a capture, even an empty page, it doesn't tell you, "Hey, I just got an empty page."

</details>

**Rafael Levi**: 它会试图编造一些东西，而这就是绝大多数幻觉的来源。**出于取悦用户的需要以及数据的缺乏**。所以，它真的就是在凭空捏造。我曾见过它真切地编造数字，提供伪造的引用文献。

<details>
<summary>Original English</summary>

**Rafael Levi**: It will try to make up something, and this is where the most of hallucinations come from. The need to please and lack of data. So, it literally makes things up. I've seen it literally make numbers up, provide fake citations.

</details>

**Rafael Levi**: 你点击那个引用链接，它是一个 404 错误，那个页面根本不存在，我相信你们所有人肯定都经历过，我最近也一直看到这种情况发生。我的意思是，在 **ChatGPT** 上，字面意义上有大约 **60% 的引用链接是无效的**。

<details>
<summary>Original English</summary>

**Rafael Levi**: You click on the citation, it's a 404, the page doesn't exist, and I'm sure all of you have uh I've seen that happening recently. I mean, literally like 60% of citations on ChatGPT is not working.

</details>

**Rafael Levi**: 你们当中有多少人尝试过购买一款产品？比如：“嘿，在网上帮我找一下这款产品，我想买它，给我一个购买链接。” 然后你点击了那个产品链接，却发现根本没有这个产品。那么，你（AI）说的这个产品到底是什么？

<details>
<summary>Original English</summary>

**Rafael Levi**: How many of you have tried to purchase a product? Hey, find me this product online, I want to buy it, and give me a link to the product. You click on the link to the product, and there's no product. Like, so what is this product that you're talking about?

</details>

**Rafael Levi**: 那个网址不存在，那个产品也不存在。那么，我该去哪里花 50 块钱买这个产品呢？根本就不存在。

<details>
<summary>Original English</summary>

**Rafael Levi**: The URL doesn't exist, the product doesn't exist. So, where do I buy this product for the 50 bucks? Doesn't exist.

</details>

### MCP 性能对比演示

**Rafael Levi**: 嗯，所以，我想向你们展示的，我将通过代码展示给你们看。你们当中有多少人熟悉诸如 VS Code 这样的编程工具？没有吗？好的，太完美了。所以，如果我切换到那个界面，大家也不会觉得一头雾水。

<details>
<summary>Original English</summary>

**Rafael Levi**: Um so, what I want to show you, and I'm going to show you in code. How many of you are familiar with coding like um VS code? No? Okay, perfect. So, nobody's going to get lost if I'm going to switch to that.

</details>

**Rafael Levi**: 所以，我接下来要做一个演示，基本就是对比在使用 MCP 和不使用 **Bright Data** MCP 的情况，我们将比较一下两者到底有什么区别。

<details>
<summary>Original English</summary>

**Rafael Levi**: So, I'm going to do a demo basically with MCP and without the Bright Data MCP, and we're going to compare what is going on there.

</details>

**Rafael Levi**: 首先，我，我，我想向你们展示，这两个脚本里我用的是完全相同的提示词，对吧？也就是一个没有使用 MCP，另一个使用了 MCP。

<details>
<summary>Original English</summary>

**Rafael Levi**: So, first I'm going to I I I want to show you that I have exactly identical prompts for both of the uh scripts, right? So, without MCP and with MCP.

</details>

**Rafael Levi**: 那么，我给它分配了五个任务。首先是房产，`rightmove.co`。让我们去看看一些房源；然后是 **LinkedIn**、**Instagram**、**Amazon** 以及 **TikTok**。这就是我想要访问的五个基础网站。

<details>
<summary>Original English</summary>

**Rafael Levi**: So, the the I I give it five tasks. Uh Property, rightmove.co. Let's go check out some of the properties, LinkedIn, Instagram, Amazon, and TikTok. These are the five basic uh sites that I wanted to access.

</details>

**Rafael Levi**: 它们在反爬虫系统方面都非常严格，而我想向你们展示这种差异。所以，首先我将在不使用 MCP 的情况下运行它，并且我将真正让 AI 自己用事实说话。

<details>
<summary>Original English</summary>

**Rafael Levi**: They are very heavy on anti-bot systems, and I want to show you the difference. So, first I'm going to run it without an MCP, And I'm going to literally to let the AI talk for itself.

</details>

**Rafael Levi**: 而且 **GPT-5** 运行有点慢，所以会花点时间。但基本上，我们正在尝试做的是访问这个 URL。这是我大概半小时前查过的一些本地房产信息。

<details>
<summary>Original English</summary>

**Rafael Levi**: And GPT-5 is a bit slow, so it's going to take some time. But basically, what we're trying to do is we're trying to access this URL. It's some local properties that I did literally half an hour ago.

</details>

**Rafael Levi**: 嗯，一家在以色列的 **LinkedIn** 公司，让我们来看看。一个 **Instagram** 账号，一些 **Amazon** 上的产品，以及一些 **TikTok** 的内容。这并不仅仅局限于这五个网站。这只是我挑选出来的几个，因为我非常确定，如果不使用 MCP，它绝对无法成功访问这些网站。

<details>
<summary>Original English</summary>

**Rafael Levi**: Um LinkedIn company in Israel, let's check it out. Instagram account, uh some Amazon product, and some TikTok. This is not limited to just these five websites. It's just something that I picked that is I know for sure will not work without MCP.

</details>

**Rafael Levi**: 所以，如你们所见，在没有 MCP 的情况下，我没有实时的网络数据访问权限。呃，没有任何浏览工具，对吧？也就是说，这是在 **GPT-5** 开箱即用的默认状态下不可用的工具。我的意思是，它很强，这是一个非常强大的 LLM。但是**成功率为零，五个任务全部失败**。

<details>
<summary>Original English</summary>

**Rafael Levi**: So, as you can see, without MCP, I don't have live web data access. Uh doesn't have any browsing tools, right? So, this is with tools not available just by default out of the box uh uh GPT-5. I mean, it's a strong but it's a strong LLM. And zero success, five failed.

</details>

### Bright Data MCP 功能介绍

**Rafael Levi**: 完全一样的事情，完全一样的提示词，我现在要带上我们的 MCP 来运行它。我们的 MCP 拥有 **66 个工具**。在它运行的同时，我想顺便介绍一下它拥有的一些工具。

<details>
<summary>Original English</summary>

**Rafael Levi**: Same exact thing, exactly the same prompt, I'm running with our MCP. Uh our MCP has 66 tools. While it's running, I just want to go off some of the tools that it has.

</details>

**Rafael Levi**: 搜索引擎。搜索引擎基本上意味着 LLM 能够执行 Google 搜索、Bing 搜索、DuckDuckGo 搜索。**是真正的搜索**，而不仅仅是那种，你们知道的，它在后台自己进行的所谓“网页搜索”。

<details>
<summary>Original English</summary>

**Rafael Levi**: Search engine. Search engine is basically the LLM is able to do Google search, Bing search, DuckDuckGo search. Real searches, not just like, you know, search the the web that it's doing in the background.

</details>

**Rafael Levi**: 并且它还有一种作为 Markdown 格式的抓取功能。这是一个非常强大的功能。基本上，它可以向任何 URL 发送一个 curl 请求，并**只获取没有 HTML 标签的 Markdown 文本**。这样，你就不必在解析 HTML 标签上浪费 token（代币）了。

<details>
<summary>Original English</summary>

**Rafael Levi**: Um it has It also has scrape as a markdown. That's a very strong one. Basically, it can send a curl to any URL and get just the markdown without HTML tags. So, you're not wasting tokens on parsing the HTML.

</details>

**Rafael Levi**: 还有搜索引擎批量查询。如果你想查询，比如说 100 个关键词，你确实可以直接发送 100 个关键词，并获取这 100 个关键词的批量结果。所以，这种**扩展性也是非常巨大的**。

<details>
<summary>Original English</summary>

**Rafael Levi**: Uh search engine batch. If you want to do, like, you know, like 100 keywords, you can literally can literally send 100 keywords and get 100 keyword batch results. Like, so the scaling is also huge.

</details>

**Rafael Levi**: 发现功能。如你们所见，它还为许多网站内置了预先构建的 API。当然，它还拥有一个抓取浏览器基础设施。所以，**它其实是一个你的 LLM 可以打开并进行导航的远程浏览器**。

<details>
<summary>Original English</summary>

**Rafael Levi**: Discover. It also has pre-built APIs for many websites as you can see. And of course, it has a scraping browser infrastructure. So, it's a remote browser that your LLM can open and navigate.

</details>

**Rafael Levi**: 这个远程浏览器**能够自行解决验证码问题**。它拥有独特的指纹识别。所以，它可以同时打开 100 个浏览器，访问同一个网站而不会被屏蔽。

<details>
<summary>Original English</summary>

**Rafael Levi**: The remote browser solves capture by itself. It has a unique fingerprint. So, it can open 100 browsers, navigate the same website without getting blocked.

</details>

**Rafael Levi**: 所以，整体的想法就是，使用我们的 MCP，它不仅可以执行单个会话，**还能并行执行多个会话**。

<details>
<summary>Original English</summary>

**Rafael Levi**: So, the whole idea is that with our MCP, not only can it do a single sessions, it can do multiple sessions in parallel.

</details>

**Rafael Levi**: 而且如你们所见，让我们来看一下。我们成功访问了 `rightmove`。我们成功访问了那家以色列的 **LinkedIn** 公司。并且 **Instagram** 也成功了。嗯，**Amazon** 上的产品，它获取了产品本身的信息。

<details>
<summary>Original English</summary>

**Rafael Levi**: And as you can see, let's see. We have success for the right move. We have success for the LinkedIn Misral. And Instagram also worked. Um Amazon product, it has the information for the product itself.

</details>

**Rafael Levi**: 然后我所做的是，在第二部分，我让 LLM 去对比一下没有 MCP 和有 MCP 的结果。这样你们就不用光听我的一面之词了。让我们看看 **ChatGPT** 实际上会怎么说。如果它没卡住的话。看起来它因为某些原因卡住了。

<details>
<summary>Original English</summary>

**Rafael Levi**: And and then what I did is on the second part, I asked LLMs to compare the results from no MCP with MCP. So, that you don't take my word for it. Let's see what the ChatGPT will actually say. If it didn't get stuck. It looks like it's stuck for some reason.

</details>

### 公开数据与法律合规

**Audience Member**: 我可以问个问题吗？

<details>
<summary>Original English</summary>

**Audience Member**: May I ask a question?

</details>

**Rafael Levi**: 当然，请问。我非常喜欢回答问题。

<details>
<summary>Original English</summary>

**Rafael Levi**: Of course, please. I I love questions.

</details>

**Audience Member**: 对于社交媒体个人资料，你们有运营之类的账号吗？

<details>
<summary>Original English</summary>

**Audience Member**: For social profiles, do you have like uh accounts that you run?

</details>

**Rafael Levi**: 没有，我们只处理公开数据。

<details>
<summary>Original English</summary>

**Rafael Levi**: No, we only work with public data.

</details>

**Audience Member**: 公开数据。

<details>
<summary>Original English</summary>

**Audience Member**: Public data.

</details>

**Rafael Levi**: 只有公开可用的数据。嗯，**收集需要登录才能看到的数据实际上是不合法的**。为什么呢？因为当你注册并创建一个账户时，你就接受了它的条款和条件。

<details>
<summary>Original English</summary>

**Rafael Levi**: Only publicly available data. Um collecting data behind login is not really legal. Why? Because when you sign up and create an account, you accept terms and conditions.

</details>

**Rafael Levi**: 当你接受条款和条件时，你必须要认真检查里面是否写了：“你可以爬取数据吗？你们允许，他们允许机器人访问这个网站吗？” 这就是为什么你，也许你们中有些人听说过现在正在进行着许多诉讼案。**LinkedIn** 在起诉这些人。所有人都在起诉他们。**Amazon** 也在起诉，是的。

<details>
<summary>Original English</summary>

**Rafael Levi**: When you accept terms and conditions, you need to really check it if it says, "Can you scrape? Can you Do you allow Do they allow robots to access the website?" And that's why you Maybe some of you heard there's a lot of lawsuits going on. LinkedIn suing these people. Everybody's suing them. Amazon suing, yes.

</details>

**Audience Member**: 但是我认为即使是，举例来说，**LinkedIn** 和 **Instagram**，我认为它们甚至根本不向你展示任何真正的公开数据，即使你在……

<details>
<summary>Original English</summary>

**Audience Member**: But I think even um for example, LinkedIn and Instagram, I think they don't even show you really any public data even if you're on the

</details>

**Rafael Levi**: 这个嘛，当然有大量的 **LinkedIn** 的公开数据。如果你以这个为例，我会复制这个 URL。我可能会被屏蔽。我不知道这里的本地 IP 地址情况如何，但是嗯，我打开了一个无痕窗口，对吧？

<details>
<summary>Original English</summary>

**Rafael Levi**: Well, there's plenty of public data for for LinkedIn, of course. If you take for example, I will take this URL. I might get blocked. I don't know how's the local IP, but um and I open an incognito window, right?

</details>

**Rafael Levi**: 你看，这就出来了。所以，这就是可以被收集的公开数据。公司页面也是一样的道理。完全一样。唯一的问题在于他们的限制非常严格，对吧？所以，假设如果你使用的是像这样大型活动的 Wi-Fi IP 地址，它很可能会把你屏蔽，因为这是一个数据中心的 IP，它是一个低质量的 IP。

<details>
<summary>Original English</summary>

**Rafael Levi**: There you go. So, this is a public data that can be collected. Company, it's the same thing. It's the same thing. The only thing is they're very critical, right? So, if you are using, let's say, a Wi-Fi IP of a big event like this, it probably will block you because it's a data center IP, it's low quality IP.

</details>

**Rafael Levi**: 在家里的话，你可能可以访问大概 5 到 10 个个人资料页面，但最终它还是会要求你登录。所以，我们只处理公开数据。这意味着，**当你们使用我们的服务时，你们是安全的，不用担心会有人敲开你家的门起诉你**，如果你能理解我的意思的话。

<details>
<summary>Original English</summary>

**Rafael Levi**: From home, you can probably access maybe 5, 10 profiles, but eventually it will also ask you to log in. Uh so, we only deal with public data. So, when you guys are using us, you are safe in the sense of nobody's going to come knocking on your doors to sue you, if that makes sense.

</details>

**Rafael Levi**: 不。我们再次重申，我们不处理登录后的数据。我们认为这是非法的，所以我们不处理任何涉及接受条款和条件以及登录后的数据。只有公开可用的数据。

<details>
<summary>Original English</summary>

**Rafael Levi**: No. We Again, we don't deal with data behind login. We consider it to be illegal, so we don't deal with accepting terms and conditions and data behind login. Only publicly available.

</details>

**Rafael Levi**: 我们有一个完整的数据集。所以，如果你们不想获取实时数据，并且你们也不介意数据是否是几个月前的，我们实际上拥有现成的数据集，你们可以直接对其进行筛选，比方说，你在寻找，如果我们在讨论 **LinkedIn** 上的用户，你正在寻找特定区域的 AI 工程师，你可以直接过滤并立刻获得该数据集。

<details>
<summary>Original English</summary>

**Rafael Levi**: We have a whole data set. So, if you guys don't want to do live data and you don't care if it's a few months old, we have data sets literally that you can just filter by, let's say, that you're looking If we're talking about LinkedIn people, you're looking for AI engineers in a certain area, you can filter it and just get the data set right away.

</details>

**Rafael Levi**: 然后，你的智能体实际上是可以访问这个数据集的。所以，如果需要的话，你的智能体可以过滤数据集并为你获取数据，对吧？它拥有所有这些工具的访问权限。所以，这是 LLM 自身给出的一个正面的对比结果。

<details>
<summary>Original English</summary>

**Rafael Levi**: So, and and your agent will actually have access to that. So, your agent can filter the data set and get you the data if you want to, right? So, it has access to all the tools. So, here's basically head-to-head comparison by the LLM itself.

</details>

**Rafael Levi**: 没有 MCP 的情况下：失败，无法进行实时网络访问。如果有列出的话，就是失败、成功、失败、成功。所以，基本就是这样。

<details>
<summary>Original English</summary>

**Rafael Levi**: Without MCP failed, no live web access. With if listed, failed, successful, failed, successful. So, that's basically it.

</details>

### MCP 解决反爬虫机制

**Rafael Levi**: 呃，绕过反机器人机制，解决验证码，对吧？所以，重申一遍，我们的系统会自动解决验证码，所以如果你的机器人通过浏览器访问一个带有验证码的网站，我们的浏览器内置了验证码解决方案，所以它会**自动解决验证码，然后你的机器人就可以继续浏览而不会被拦截**。

<details>
<summary>Original English</summary>

**Rafael Levi**: Uh antibot bypass, CAPTCHA solving, right? So, again, our system automatically solves CAPTCHA, so if your bot navigates to a website with a browser and has a CAPTCHA, our our browser has built-in capture solving solution so it will automatically solve the capture and your bot can continue on browsing without getting blocked.

</details>

**Rafael Levi**: 我还有多少时间？我不知道。嗯，所以总结一下，对吧？这就是你们能看到的最大的幻觉现象。**智能体被拦截了，它又需要取悦你，于是它就凭空编造内容**。

<details>
<summary>Original English</summary>

**Rafael Levi**: How much time I got? I don't know. Um So just to kind of summarize it, right? This is the biggest hallucinations that you guys see. The agent gets blocked, it needs to please you and it makes things up.

</details>

**Rafael Levi**: 还有虚假内容也是个问题，对吧？现在，如果你想去 Google 上搜索什么是 **Cloudflare** 的 **AI 迷宫（AI Labyrinth）**，它其实就是一个系统，一旦它检测到一个机器人，它不仅不会屏蔽它，它会**实实在在地给它投喂虚假数据**。所以会导致更严重的幻觉。对吧？

<details>
<summary>Original English</summary>

**Rafael Levi**: And um fake content also, right? So now uh if you want to Google what is Cloudflare Cloudflare AI Labyrinth it's basically a system once it detects a bot it's not doesn't block it. It literally feeds it fake data. So bigger hallucinations. Right?

</details>

**Rafael Levi**: 而解决这个问题最简单的方法，就是要确保你，你的智能体不会被屏蔽。而这像部署我们的 MCP 一样简单。我们的 MCP 提供一个每月 **5,000 次请求的免费额度**。所以如果你们想尝试一下，你们如果愿意的话可以在 **LinkedIn** 上联系我。

<details>
<summary>Original English</summary>

**Rafael Levi**: And um the easiest fix for this is just to make sure that you your agent doesn't get blocked. And it's as easy as to implement our MCP. Uh our MCP has a free tier of 5,000 requests. So if you guys want to try it out, um this is you can connect with me on LinkedIn if you want to.

</details>

**Rafael Levi**: 或者这是……等一下。这是 MCP 的注册链接吗？我主要是用这些二维码的。等一下。是的，网络。好的，请讲。

<details>
<summary>Original English</summary>

**Rafael Levi**: Or is this the Hold on a second. Is this the sign up for the MCP? I'm mostly in these QR codes. One second. Yeah, internet. Yes, please.

</details>

**Audience Member**: 呃，它是如何检测是否存在 **Cloudflare 迷宫** 的？

<details>
<summary>Original English</summary>

**Audience Member**: Uh how does it detect if if there's Cloudflare Labyrinth or not?

</details>

**Rafael Levi**: 嗯，所以我们处理这个问题的方式是，**我们让你的智能体看起来像一个真实的人类**。字面意义上的，比如，预先录制了鼠标移动的轨迹，当它输入时，就像是，它模拟了一个真实人类的行为模式。

<details>
<summary>Original English</summary>

**Rafael Levi**: Um so the way we approach it is that we make your agent look like a human being. Literally like uh there's mouse movement pre-recorded, there's typing when it types it's like it's uh mimics a real human behavior.

</details>

**Rafael Levi**: 所以 **Cloudflare** 甚至都不会来问你是不是机器人，对吧？这就是我们的策略。我们没有去试图分析他们到底是如何检测的，而是**尽可能地让智能体看起来像人类**，从而不触发实际的拦截机制。

<details>
<summary>Original English</summary>

**Rafael Levi**: So uh the Cloudflare literally just doesn't even ask are you a robot or not, right? So this is our our approach. Instead of trying to understand how they detect we make the agent look as human as possible so that it doesn't trigger the actual blockage.

</details>

### 处理误导性数据

**Rafael Levi**: **误导性数据是你实际会遇到的最棘手的问题之一。** 目前亚洲的很多网站都在做这种事，对吧？比如酒店网站，他们真切地提供着各不相同的价格。

<details>
<summary>Original English</summary>

**Rafael Levi**: Misleading data is one of the toughest things that you can actually encounter. A lot of websites right now in Asia is doing that, right? Hotels, they're literally providing different prices.

</details>

**Rafael Levi**: 你用手机查看，你会看到一个价格。你用电脑查看，你会得到另一个不同的价格。你可以使用代理来查询，你又会得到第三个价格。究竟哪一个是正确的？真的很难判断。

<details>
<summary>Original English</summary>

**Rafael Levi**: You go check out on your phone, you get one price. You can check from your computer, you get a different price. You can ask for a proxy, you get a third price. Which one is correct? It's really hard to tell.

</details>

**Rafael Levi**: 当涉及到误导性数据的领域时，最好的办法就是确保你的智能体看起来像是一个人类，然后祈求好运。目前来说，基本上只能采取这种应对策略。

<details>
<summary>Original English</summary>

**Rafael Levi**: When it comes into the domain of misleading, uh the best bet is to make sure that you your agent looks like a human, and then hope for the best. That That's basically what the approach is right now.

</details>

**Rafael Levi**: 嗯，**AI 迷宫（AI Labyrinth）** 其实就是大概一个月前发布的。我手头并没有很多关于它的统计数据，比如，不知道它到底是怎么运作的。我只知道它并没有真正影响到我们。我们在数据上没有看到任何变化，而我们每天都在收集 PB 级别的数据，我们有这么多的客户一直在进行网络爬虫作业。

<details>
<summary>Original English</summary>

**Rafael Levi**: Um AI levers was literally released a few like a month ago. Uh I don't have much of statistics on what is like, you know, exactly how it's working. All I know is that it didn't really affect us. We don't see any kind of change in data, and we're collecting petabytes of data on a daily like We have so many customers always scraping.

</details>

**Rafael Levi**: 我们会对数据进行缓存，所以我们总是在对比结果。我们在抓取结果中没有发现任何质量下降的现象。所以，我认为在这个层面上，我们做得很棒。

<details>
<summary>Original English</summary>

**Rafael Levi**: We're caching data, so we're always comparing the results. We don't see any degradation in the results. Uh so, I think we're doing a good job in that case.

</details>

**Rafael Levi**: 呃，这是一个可以让你们注册的二维码。我们也有一个 GitHub 页面。`github.com/brightdata`。哦，就是直接在 GitHub 搜索 `brightdata`。

<details>
<summary>Original English</summary>

**Rafael Levi**: Uh this is a QR code that you guys can sign up for. Uh we have a GitHub page as well. Uh GitHub brightdata.com. Oh, just GitHub brightdata.

</details>

**Rafael Levi**: 还有一件我建议大家去看看的东西是**技能页面（skills page）**，对吧？所以，我们做的事情是，我们创建了一些具体的技能模块。我在几个小时后还会有一场演讲。如果你们有兴趣看看这些技能到底能做什么的话，基本上就是你可以把任何智能体指引到这里，然后这个页面会教它如何构建一个抓取器，或者如何搭建一个数据收集的流水线。

<details>
<summary>Original English</summary>

**Rafael Levi**: And another thing that I would recommend for you guys to check out is the skills page, right? So, what we did is we created skills. And I'm going to have another session in a couple of hours. If you're interested in seeing what the skills does, is basically you can take any agent, tell it to go here, and this page will teach it on how to build a scraper, or how to build a pipeline that will collect you the data.

</details>

**Rafael Levi**: 它包含了智能体所需的所有信息，以及所有的 API 接口。而且如果你能来参加我下一场大概在一点钟开始的会议，我想。差不多是那个时间。我会向大家实战演示它是如何构建整个数据流水线的。

<details>
<summary>Original English</summary>

**Rafael Levi**: It has all the information it needs, all the APIs. And uh if you will come back to my next session, which is at 1:00, I think. Something like that. I'm going to literally demonstrate how it builds the pipeline.

</details>

**Rafael Levi**: 我真的会在你们面前直接告诉它：“嘿，听着，我们来给 ABC 构建一个 **Walmart**（沃尔玛）的数据采集器。” 然后它就会完成构建，并且去抓取数据。与其逐个解析每一个 HTML 页面，它会自动构建一个解析器，从而**节省大约 99% 的 token（代币）成本**。

<details>
<summary>Original English</summary>

**Rafael Levi**: Literally in front of you, I'm going to tell it, "Hey, listen, let's build a Walmart collector for ABC." And it's going to build it, and it's going to scrape it. And instead of parsing each individual HTML, it's going to build a parser, and it saves about 99% of the tokens.

</details>

**Rafael Levi**: 因为我看到很多人都在说：“嘿，我需要解析一万个网页，但这太耗费 token 了。” **不要让 LLM 去直接解析网页内容。正确的做法是让 LLM 编写一个解析器代码，然后通过脚本来运行它。** 不过这是下一场会议的内容了。还有什么问题吗？

<details>
<summary>Original English</summary>

**Rafael Levi**: Because I see a lot of people is like, "Hey, I need to parse 10,000 pages, but it's so token heavy." Don't parse with LLM. LLM builds a parser and then the script runs it. But that's the next session. Any questions?

</details>

### MCP 工具的按需加载

**Audience Member**: 有一个关于性能的问题。我看到你们的 MCP 暴露了 69 个工具，这意味着如果我，如果我需要为我的，我的智能体实现同样精准的功能，我需要加载全部的 69 个工具吗？

<details>
<summary>Original English</summary>

**Audience Member**: Uh question on the performance. Uh I saw that your MCB exposes 69 tools, which means if I if I need to do the same surgical ability for my for my agent do I need to load all the 69 tools

</details>

**Rafael Levi**: 当然需要筛选。你，我刚才展示出全部 69 个工具只是为了给你们看。如果我只需要抓取 Markdown 数据和搜索功能，我绝对只会加载那两个工具而已。

<details>
<summary>Original English</summary>

**Rafael Levi**: of course filter it. You I just showed 69 tools because just to show it. Uh if I need just to scrape markdown and search, I would just literally load two tools.

</details>

**Rafael Levi**: 呃，否则你就会让大量的无关数据充斥上下文（context），当然不能这么做。很抱歉，你开头的话我没听清，能再说一遍吗？

<details>
<summary>Original English</summary>

**Rafael Levi**: Uh otherwise you're flooding contacts with irrelevant data, of course not. I'm sorry, I didn't hear the beginning again.

</details>

**Audience Member**: 就是实验开始的时候

<details>
<summary>Original English</summary>

**Audience Member**: Uh the the experiment beginning

</details>

**Rafael Levi**: 是的。所以我们并没有进行任何搜索。我实际上只是告诉它：“嘿，访问这个 URL，看看你能不能加载它。” 对吧？所以在这个演示中我并没有使用搜索功能。

<details>
<summary>Original English</summary>

**Rafael Levi**: Yes. Um so we didn't do any searches. Um I literally told it, "Hey, go to this URL, see if you can load it." Right? So that I didn't use the search uh in this demo.

</details>

**Audience Member**: 明白了。

<details>
<summary>Original English</summary>

**Audience Member**: Sure.

</details>

**Rafael Levi**: 呃，但是当然了，再强调一遍，即使是使用我们的 MCP，它们实际上也是能够执行 Google 搜索的。

<details>
<summary>Original English</summary>

**Rafael Levi**: Uh but of course again even with our MCB they can actually do a Google search.

</details>

**Audience Member**: 是的。

<details>
<summary>Original English</summary>

**Audience Member**: Yeah.

</details>

**Rafael Levi**: 而这也是其最大的优势之一，因为我们都习惯了 Google 的搜索结果。所以在默认情况下，当你在向 LLM 提出问题时，你期望它能去执行一次 Google 搜索，但它其实并没有那么做。

<details>
<summary>Original English</summary>

**Rafael Levi**: And that's the one of the biggest benefits is because we're used to Google results. So by default when you're asking LLM, you expect it to do a Google search, but it doesn't.

</details>

**Rafael Levi**: 所以使用 MCP 获得的结果要好得多得多，而且我建议大家注册并亲自尝试一下，它是免费的。去看看实际的效果，并比较一下你们自己得出的结论。

<details>
<summary>Original English</summary>

**Rafael Levi**: So the results with the MCB much much better and I I recommend sign up, try it out, it's free. See the results, compare what you guys get.

</details>

**Audience Member**: 那个额度是每天 5,000 次请求还是……

<details>
<summary>Original English</summary>

**Audience Member**: Is that for 5,000 requests per day or

</details>

**Rafael Levi**: 每个月。每个月的额度。对于一个 MVP（最小可行性产品）或一个小型实验来说，这绝对绰绰有余了。呃，我们也有按使用量付费（pay as you go）的模式，所以如果你确实需要更多的请求量，这算不上什么，你们懂的，这……

<details>
<summary>Original English</summary>

**Rafael Levi**: Per month. Per month. Which is, you know, like for an MVP for a little experiment is more than enough. Uh we also have pay as you go, so if you do need a little more it's it's nothing like, you know, it's

</details>

**Audience Member**: 是的，没错，但是用来做个实验已经很完美了。

<details>
<summary>Original English</summary>

**Audience Member**: Yeah, yes, but for a is perfect.

</details>

**Rafael Levi**: 我经常，我参加过很多黑客松（hackathons），我也总是在向大家推荐：“嘿，听好了，去搭建一个 MVP，然后让你的智能体去帮你构建任何你需要的东西。它的表现绝对比不用它的时候好太多了。”

<details>
<summary>Original English</summary>

**Rafael Levi**: I always I do a lot of hackathons and I'm always recommending, "Hey, listen, set up an MVP and tell your agent to go build whatever you need. It does a much better job than without."

</details>