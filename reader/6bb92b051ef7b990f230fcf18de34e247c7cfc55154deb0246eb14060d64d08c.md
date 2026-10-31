---
author: AI Engineer
date: '2026-06-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zTZ0qunQXnM
speaker: AI Engineer
tags:
  - web-scraping
  - data-pipeline
  - bot-detection
  - token-optimization
title: 利用大语言模型与 MCP 构建数据抓取流水线
summary: 分享者探讨了利用大语言模型与 MCP 构建爬虫流水线而非逐页解析的方法。通过 Bright Data 的技能集与 MCP，智能体可提取网页内容并编写和维护爬虫脚本，从而降低 token 消耗并应对反爬机制。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Bright Data
  - Walmart
products_models:
  - Claude Code
  - Claude Haiku
media_books: []
status: evergreen
---
<!-- chunk 1/3 -->

### 为什么用大模型构建抓取流水线，而不是逐页解析？

好了，我们直接切入正题。

<details><summary>Original English</summary>
All righty, let's dive into it.
</details>

在上一场分享中——我不知道你们当中有多少人在场——我谈到了 MCP 如何让大语言模型能够访问那些处于验证码、防爬虫检测系统等保护之下的网站。

<details><summary>Original English</summary>
So, uh in the previous session, I I don't know how many of you were here, but I talked about how MCP gives access to LLMs to websites that are behind uh CAPTCHA, bot detection systems, and so on.
</details>

而在这一场分享中，我想聊聊究竟该如何利用大语言模型来进行规模化的数据采集。因为我经常在 Reddit 和其他社交媒体上看到有人说：“哎呀，我需要扫描 10,000 个商品，但如果要用大模型解析所有东西，会消耗太多 token 了。”显然，你不能那么干。

<details><summary>Original English</summary>
And in this session, I want to talk about um how do you actually collect data on scales with LLM? Because a lot of times I'm seeing on Reddit and other social media is like, "Oh, I need to scan 10,000 products, but that's so many tokens if I need to parse everything with LLM." So, obviously, you don't do that.
</details>

对吧？所以，整场分享的核心就是：如何利用大语言模型来构建数据流水线？而不是去对大模型说：“嘿，大模型，你能帮我去解析这个吗？”而是让它构建一个能帮我解析数据的爬虫。我将向大家展示，借助我们的技能集（skills），这件事情会有多么简单。Bright Data 提供了专门的技能集，可以教会你的大模型如何构建流水线。配合我们的 MCP，它能够实际提取 HTML，从而搞清楚需要解析哪些选择器等等。

<details><summary>Original English</summary>
Right? So, the whole session is how do you build pipelines, right? With LLM. Instead of telling, "Hey, LLM, can you go and uh parse this for me?" build a scraper that's going to parse it for me, and I will demonstrate how easy it is uh with our skills, right? So, Bright Data has skill sets that actually teaches your LLM on how to build a pipeline. With our MCP, it can actually extract HTML so that it knows what are the selectors that it needs to parse, and so on.
</details>

写抓取代码，对吧？写出爬虫。我不知道你们当中有多少人以前真正写过爬虫。好吧，那你们肯定体会过那种头疼——突然之间东西不见了，数据缺失了，你不得不半夜爬起来。我不知道你们有没有为客户做过这个，客户就会抱怨：“天呐，没有数据了。”所以，过去基本上就是那样：你写一个爬虫，然后去维护它。事实上，有时候维护它花的时间比写它花的时间还要多，对吧？尤其是如果那个网站在不断变动它的选择器，或者是一个 React 网站，事情就会变得非常复杂，对吧？

<details><summary>Original English</summary>
So, um the scrape tags, right? Write the scraper. Uh I don't know how many of you actually wrote scrapers before. Okay, so you know the headache when all of a sudden things are missing, data is missing, you got to wake up. I don't know if you guys did it for clients, and clients are like, "Oh my god, there's no So, basically, that's what used to be. You write a scraper, and you maintain it. As a matter of fact, sometimes you maintain it more than it it it takes you to write it, right? So, everything, especially if the website is constantly changing uh its selectors, or if it's a React website, it gets really complicated, right?
</details>

因此，一个智能体就能解决所有这些令人头疼的问题。它可以通过我们的 MCP 进行探索，理解需要什么数据，编写爬虫，并实际运行、执行和维护它。事实上，我每天都会进行数据采集，每隔 30 分钟我就会启动一个大模型类池。它会检查采集到了什么数据，确保一切正常。如果一切正常，它就关闭。举个例子，数据总要设置校验规则，对吧？假设某个数据项缺失了某些内容，你的智能体 5 分钟就能修好它，你根本不需要半夜醒来。

<details><summary>Original English</summary>
So, an agent it it it solves all that headache, right? It can explore with our MCP, it understands what the data is needed. It writes the scraper and it actually runs it and executes it and maintains it. As a matter of fact, I do collections on the daily basis and I have every 30 minutes I have an LLM class pool spools up. It checks what the data is collected, make sure that everything is fine. Everything is fine, it shuts down. If for this example, there's a always set a validation for data, right? Let's say the data point is uh missing some something. Your agent fix it. 5 minutes. You don't have to wake up in the middle of the night. Uh
</details>

### 现场演示与技能集集成

那么，让我来做个演示。这次演示我想用 Cloud Code。我不知道你们有多少人用过 Cloud，不管你们是用 Codex 还是别的什么，我个人更喜欢 Cloud Code。我喜欢它的表现，它做得很棒。现在的爬虫构建方式简直不可思议，因为想当年，要搭好一套通常得花上好几个星期。我们在 GitHub 上建了一个页面，叫 Bright Data skills。在这里，你的智能体基本能拿到它可能需要的一切。从爬虫构建的最佳实践，到各类操作，包含了它构建爬虫所需的一切。

<details><summary>Original English</summary>
So, let me demonstrate. So, for this demo, I want to use Cloud Code. I don't know how many of you use Cloud. If you're using Codex or whatever it is, I prefer Cloud Code. I like how it I like it. It does a great job. So, the way that you build scrapers now and it's ridiculous because, you know, back in the day it took weeks to set it up. We created a Bright Data like GitHub page, right? Bright Data skills. Here basically, your agent has everything that it might need, okay? Um scrape builders back practices, how to everything. Everything that it needs in order to build a scraper.
</details>

我想展示的是，首先，我们先从简单的开始。让它帮我建一个爬虫。本来我想提前录下来的，因为我以为会耗时很久，但现在只要大约 3 分钟。帮我建一个爬虫，两个输入：关键词搜索、针对 walmart.com 的最大页数限制。大家都熟悉沃尔玛。沃尔玛有非常严厉的防爬系统。如果有人试过抓取它，直接抓根本行不通。但是通过 Bright Data，它能搞定。不过……好吧，先改一下，walmart.com。搜索耳机，采集三页。

<details><summary>Original English</summary>
And what I want to show is uh first of all, let's I'm going to start simple. Go to build me a scraper and I wanted to record it because I thought it's going to take a long time, but now it takes a little like 3 minutes. Build me a scraper uh two inputs keyword search max pages for walmart.com. Everybody's familiar with Walmart. Walmart has a very aggressive anti-bot systems. If anybody tried to scrape it, um it just doesn't work. But, through Bright Data, it will figure it out, but you're you're all right. Let's just correct that. walmart.com Um run a search for headphones, collect three pages.
</details>

那么它现在要做的是：访问我们的 GitHub，获取所需的全部技能集以及如何构建爬虫的方法；然后通过已经连接到云端的 MCP，从页面提取 HTML；接着它会找到所需的全部选择器，并为你构建出一个爬虫。现在你可以看到它以 Markdown 格式呈现爬虫，基本上就是在提取文本。对于技能集而言，我们不需要 HTML，只要文本就行。这种转为 Markdown 的抓取是 Bright Data MCP 的一部分。这个 MCP 提供了 5,000 次免费请求，所以如果有人想试一试，大家可以免费体验。你只需要在 Bright Data 注册一个账户，这不会花你一分钱。

<details><summary>Original English</summary>
Uh so, what it's going to do right now is going to go to our GitHub, it's going to get all the skill set that it needs, how to build scrapers, then it's going to go uh with the MCP that's already connected to the cloud, it's going to extract the HTML from the page. Uh it's going to find all the selectors that it needs, and it's going to build you a scraper, and uh So, right now you can see a scraper as a markdown, it's basically extracting the the the the text, right? So, for the skills, we don't need the HTML, we just need the text. Uh scraper as a markdown is a part of the MCP of Bright Data MCP. Uh the MCP has 5,000 requests for free, so if anybody wants to try it, you guys can try it for free. Um You will need to just open an account with Bright Data, which doesn't cost you anything.
</details>

让它继续运行。那么，为什么这种方式比让大模型去逐页解析每个 HTML 更好呢？等会儿我真要让它算算这节省了多少 token。对于这三页，我之前测过，单单通过构建爬虫并用脚本去解析 HTML，就能节省大约一百万个 token。

<details><summary>Original English</summary>
And let it do its thing. So, why is this better than having an LLM parse every single page, every HTML? It's I'm I'm literally afterwards I'm going to ask it to tell you how many how much tokens it saves. So, for the three pages, I've done this before, it saves about a million tokens just to from building the scraper uh and using a script to parse the HTML.
</details>

而且，哪怕你不是为了生产环境做抓取，就假设你想找一款性价比最高的耳机，对吧？过去你得去 Google 搜，或者去 CNET 那种对比各类评测的网站，但在这种模式下，你可以利用电商平台的用户评价。所以我可以在这里告诉它：“嘿，扫描这 5 个页面，帮我找出评价最好的耳机。”因此，即便用于个人用途，它也同样很有用。它不会被封锁，反而能在那些处于 Cloudflare 防护下的网站上真正帮你找到你需要的东西。

<details><summary>Original English</summary>
And um even if you are not doing any scraping for production, but let's say that you want to find the best best headphones for the money, right? It used to be you go to Google, you go to some CNET where they uh compare everything, but here you can use the the marketplace reviews. So, I can tell it here like hey hey, um scan the five pages, find me the best uh review to headphones. So, it could be even useful for you as a personal in in a personal way, right? So, instead of it getting blocked, it can actually find you things that you need on websites that are behind Cloudflare.
</details>

哎呀，我忘了删掉旧的那个了。不，停下，停下，停下。稍等一下。删掉旧爬虫。爬虫。我完全……我刚才在做测试，彻底忘了清理。

<details><summary>Original English</summary>
Oh, I forgot to delete the old one. No. No, stop. Stop. Stop. Hold on a second. Delete the old scraper. Scraper. I totally I was testing it and I totally forgot to clean up.
</details>

### 更换目标网站与个人应用场景

我们换个网站吧。挑一个网站。在英国有什么比较知名、而且封禁很厉害的电商平台？

<details><summary>Original English</summary>
Uh, let's do a different website. Pick a website. What's a popular marketplace in uh that's aggressive in blocking in UK?
</details>

>> Very。

<details><summary>Original English</summary>
>> Very.
</details>

>> Amazon？它封得没那么厉害，说出来你可能会惊讶，我用数据中心 IP 就能抓它。这里大家都常用的热门网站是什么？

<details><summary>Original English</summary>
>> Amazon? It's not that aggressive. You'll be surprised. I can scrape it with data center IPs. What's a popular website that everybody uses here?
</details>

>> Very。

<details><summary>Original English</summary>
>> Very.
</details>

Very。

<details><summary>Original English</summary>
Very.
</details>

>> V-

<details><summary>Original English</summary>
>> V-
</details>

>> v e r y.com。

<details><summary>Original English</summary>
>> v e r y.com.
</details>

>> V-

<details><summary>Original English</summary>
>> V-
</details>

Very？

<details><summary>Original English</summary>
Very?
</details>

>> Very。

<details><summary>Original English</summary>
>> Very.
</details>

>> 拼成那样吗？

<details><summary>Original English</summary>
>> Like that?
</details>

>> y

<details><summary>Original English</summary>
>> y
</details>

>> y.com？

<details><summary>Original English</summary>
>> y.com?
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 哦，那是英国的？好的，太棒了。这样我就不……我不想……停下来。开一个新会话。我们试试这个。我们试试这个。新会话在哪里？哦，在这儿。真的吗？我粘贴到底出什么问题了？好的。它是一家服装店？

<details><summary>Original English</summary>
>> Oh, that's the UK? Okay, perfect. So, this way I don't I don't want to Stop it. New session. Uh Let's do that. Let's do that. Where's the new session? Oh, there it is. Really? What is wrong with my paste? Okay. Uh, it's clothing store?
</details>

>> 呃，是综合品类。

<details><summary>Original English</summary>
>> Uh, it's category.
</details>

>> 好，那我们还是搜耳机，同样的要求，对吧？我没用过这个网站。看，全新测试，绝无作弊。

<details><summary>Original English</summary>
>> Okay, so let's do headphones again, the same thing, right? So, I don't know. I've never used this website. I've Look. Clean test. No cheating. Um
</details>

那么，这还能为你带来什么呢？再说一遍，市场研究。

<details><summary>Original English</summary>
So So, what else does this give you? So, again, market research. Um
</details>

比如，我之前在找新公寓，我想搬家。于是，通过 CloudCrawl 和 BrightData，我设置了一个监听器。其实就是告诉它：“嘿，听着，帮我建一个爬虫，每半小时跑一次，当这个区域有独立房源低于这个价格时，就通知我。”我就做了这么多。几天之内我就收到了通知，现在我就住在那里。所以，这些技术不仅在需要抓取数百万条记录的规模化场景下有用，连你个人的日常使用也用得上。现在做这些太容易了。

<details><summary>Original English</summary>
For example, I was looking for a new apartment, right? I would want to move a house. So, with a CloudCrawl, with BrightData, I set up a listener. Literally just telling Hey, listen. Build me a scraper that will run every half an hour when in this area there's a a house, private house, under this price, notify me. That's all I did. In a few days, I got a notification and now I live there. So, these things are not only useful on a scale where, you know, oh, I need to scrape millions of records, but even for your personal use. It's so easy these days.
</details>

CloudCrawl 做得非常出色，对吧？我知道 Crawlera 也做得很好，但我更倾向于 CloudCrawl，因为我说不上来，它给我的麻烦更少。Crawlera 有时会让我白忙活一场。你们有多少人用过 VibeCode？它太棒了。为什么不用呢，对吧？现在任何人都能构建任何东西。

<details><summary>Original English</summary>
CloudCrawl does an amazing job, right? I know Crawlera does a great job as well, but I prefer CloudCrawl because I don't know. It just gives me less headache. Crawlera sometimes takes me on a wild goose chase. Um how many of you use VibeCode? It's It's amazing. Why not, right? Anybody can build anything now. Um
</details>

那么，它建好了吗？我已经拿到了结构和搜索模式。我还不知道要用什么第三方库来构建。哦，好的，它正在构建爬虫。

<details><summary>Original English</summary>
So, did you build it? I've got the structure, the search patterns. I don't know what third party I'm going to build. Oh, okay. It's building a scraper. Um
</details>

这在以前要花多久？我不清楚，如果你运气好，可能要花整整一天，或者一天半，对吧？你需要去检查选择器，把它研究清楚。过去这过程挺有意思也挺好玩的，但现在你不再需要那样做了。

<details><summary>Original English</summary>
This used to take, I don't know. If you If you're having a good day, maybe a full day, maybe a day and a half, right? You need to go check out the selectors, figure it out. It used to be interesting and fun, but you don't need to do that anymore.
</details>

所以我想要向大家展示的是：借助我们的 MCP，借助我们的基础设施——我们拥有超过 1.5 亿个 IP；再加上我们的解锁技术，即使它需要运行远程浏览器……如果你需要，它实际上可以为你编写浏览器自动化脚本。那些浏览器是运行在我们的系统上的。所以我现在完全可以在这台笔记本上打开一千个运行在我们服务器上的浏览器，它们可以去执行你需要的任何操作。

<details><summary>Original English</summary>
So, what I'm trying to show you guys is that with our MCP, with our infrastructure, we have over 150 million IPs. Uh with our unlocking technology where we even though if it needs to run a remote browser, so if you want to It can actually write you a browser automation. Uh Uh the browsers are running on our system. So, I can literally right now open a thousand browsers on this laptop that are running on our servers. And they can go do things whatever you needed to.
</details>

看，它已经抓到了 90 个商品。好了，它只需要修正一下 Unicode，因为价格单位是英镑。

<details><summary>Original English</summary>
So, it already got 90 products. Okay, it just needs to fix the Unicode because it's in pounds.
</details>

<!-- chunk 2/3 -->

马上就好。

<details><summary>Original English</summary>Almost done.</details>

>> 你能详细讲讲 MCP 吗，还是说就这些了？

<details><summary>Original English</summary>>> Can you also go into details about the MCP or is that it?</details>

>> 当然可以，我上一节讲过了，不过趁着它正在加载，我来跟你们说一下。基本上，MCP 会给你的智能体提供 66 种工具。

<details><summary>Original English</summary>>> Sure, I did it in the previous session, but while it's loading, let me tell you. So, basically, the MCP gives you a agent 66 tools.</details>

其中一些基本上是……我们有一个系统，它可以向任意 URL 发送 curl 请求，然后我们的系统会实打实地把 HTML 获取回来。如果需要的话，它会破解验证码并附带 token 发送过去。它完全清楚该网站需要什么请求头和 Cookie。所以基本上，它会确保服务器认为它是一个浏览器，并把 HTML 返回来。因此，你的智能体真的可以直接发送 curl 提取数据，不会遇到任何阻碍。

<details><summary>Original English</summary>Uh some of them is basically uh we have a system where it can send a curl to any URL and our system will literally get the HTML back. It will solve a capture if needed and send it with a token. It will It knows exactly what headers and cookies the website needs. So, basically, it will make sure that the server thinks it's a browser and serve the HTML back. So, your agent can literally send curls, pull data without any questions.</details>

它可以提取完整的 HTML。它也可以直接抓取并输出为 Markdown。转成 Markdown 是为了节省 token，对吧？你只想要页面上的文本，并不关心 HTML 标签。

<details><summary>Original English</summary>It can pull a full HTML. It can pull just a scrape as a markdown. Markdown is It's to save tokens, right? You just want the text of the page. You don't care about the HTML tags.</details>

它不太喜欢那个井号。

<details><summary>Original English</summary>It doesn't like the pound.</details>

加油，你能行的。

<details><summary>Original English</summary>Come on, you can do it.</details>

那么，这是第一点。第二点，针对不同的领域，我们预建了大约 500 个不同的 API。

<details><summary>Original English</summary>Um so, that's number one. Second, we have about 500 different APIs pre-built for different domains.</details>

因此，你不必实际去获取 Markdown，而是可以直接拿到该产品的 JSON 数据。例如，针对亚马逊，我们有预建的 API。你可以……听着，当你添加你的智能体时，它可以像这样：“好的，去亚马逊上查点东西。”它甚至不需要去写个爬虫，直接发送请求就能把数据拿回来。

<details><summary>Original English</summary>So, instead of actually getting markdown, you can actually get a JSON of the product. For example, for Amazon, we have pre-built API. You can listen when you add your agent, it can be like, "Okay, go and check on Amazon something." It doesn't even need to build a scraper. It can literally just send the the request and get the data back.</details>

除此以外，还有远程浏览器基础架构，以及你的智能体访问网络所需的任何东西。

<details><summary>Original English</summary>Um on top of that, remote browser infrastructure and the anything that needs anything that your agent needs to access the web.</details>

它全都有，对吧？这样你就不会被拦截了。

<details><summary>Original English</summary>It has, right? So, you don't get blocked.</details>

趁着这个还在运行，我想给你们演示一下，比方说……告诉……一个……去沃尔玛在不用 MCP 的情况下搜耳机……

<details><summary>Original English</summary>While this is running, I want to show you for example uh tell one to Walmart do a search for headphones without MCP one</details>

所以我现在吩咐它：去沃尔玛，搜一下耳机，然后告诉我第一条搜索结果是什么。不用 Bright Data 的 MCP。

<details><summary>Original English</summary>So, I'm telling it go to Walmart, do a search for headphones, and tell me what is the first result. Without the Bright Data MCP.</details>

呃……

<details><summary>Original English</summary>Uh</details>

它要去发起一次 fetch，而这会被拦截。

<details><summary>Original English</summary>It's going to do a fetch, which is going to get blocked.</details>

产品安全验证界面，人机验证，显而易见，对吧？这就是第一种情况。

<details><summary>Original English</summary>Product security verification screen, robot or human, obviously, right? That's That's the first thing.</details>

现在，用 Bright 做同样的测试。

<details><summary>Original English</summary>Now, do the same with Bright</details>

嗯……

<details><summary>Original English</summary>Um</details>

我的天哪。

<details><summary>Original English</summary>Oh my god.</details>

现在它正在使用“抓取为 Markdown”功能。它正在执行搜索。它只提取文本，不提取 HTML，纯粹只拉取文本本身。

<details><summary>Original English</summary>So, now it's using Scrape as a markdown. It's doing a search. It's only pulling the text. It's not pulling the HTML, just the text itself.</details>

只要一搞现场演示，速度总是会慢下来。

<details><summary>Original English</summary>Always when you do a live, it's slows down.</details>

这个时间就像……

<details><summary>Original English</summary>The time is like</details>

哦，其实有可能……有可能它正在打开浏览器并按住那个按钮。你们知道的，沃尔玛有那种长按按钮的验证，需要按住大概 30 秒。所以它现在可能正在做这个。

<details><summary>Original English</summary>Oh, actually, it could be. It could be opening a browser and actually holding the button. You know, the Walmart has like one of those click and hold, and it needs to hold it for like 30 seconds. So, it could be doing that right now.</details>

那么，是不是……

<details><summary>Original English</summary>So, is it</details>

我们构建了验证码破解方案。比如，我们内部真真正正有一套用来破解验证码的 AI。

<details><summary>Original English</summary>We have built to capture solving solutions. Like, we literally have in-house We have a AI solving capture.</details>

还有移动、点击等等，简直绝了。

<details><summary>Original English</summary>And moving, clicking things, and like what? It's perfect.</details>

看，它已经拿到第一条结果了，蓝色耳机。基本上，看吧，它已经拿到了耳机的搜索结果，没有遇到人机验证，还附带了完整的产品名称。

<details><summary>Original English</summary>So, it already got first result, blue headphones. Oh, basically, there you go. It already has the results of the headphones without robot or human with full product listing name.</details>

呃……所以，我们这里已经拿到输出了。

<details><summary>Original English</summary>Uh so, we here already have the output.</details>

告诉我，如果你要手动来做这个，你会多用多少 token？

<details><summary>Original English</summary>Tell me if you were to do this manually, how many how much more tokens have you used?</details>

你节省了多少？我们来看一下明细，而这可能正是最大的痛点，对吧？Token 很贵。

<details><summary>Original English</summary>How many did you save? Let's just give it a breakdown, and this is probably the biggest issue, right? Tokens is expensive.</details>

我每天要消耗数以千万计的 token。

<details><summary>Original English</summary>I'm going through millions and millions of tokens a day.</details>

我以前用得更多，但我后来做过优化了。

<details><summary>Original English</summary>I used to go more, but I I optimized it.</details>

所以，大家都在琢磨：我们怎么才能在语言模型上省钱？怎么才能在网页访问时少浪费 token？而 Bright Data 就提供了解决方案。不用去解析完整的 HTML，再去写个爬虫。

<details><summary>Original English</summary>So, um all of you are looking how do we save money on LM? How do we waste less tokens of web access and um Bright Data has the solution. Instead of parsing the full HTML, create a scraper.</details>

不用像……你知道的，拉取 HTML，然后提取数据，再去构建解析器。

<details><summary>Original English</summary>Uh instead of using um you know, okay, it pulls the HTML and then it extracts the data, it builds the the parser.</details>

但是它现在跑得非常慢。我感觉大家都在写代码。

<details><summary>Original English</summary>But, it's working very slow right now. I feel like everybody's white coding.</details>

基本上，这就是明细，对吧？

<details><summary>Original English</summary>So, basically, here's the breakdown, right?</details>

我们这里有什么？

<details><summary>Original English</summary>What do we have here?</details>

### 数据与代码结构

解析 90 个产品的输出变化，包括输入 token、输出 token 和总共节省的量。

<details><summary>Original English</summary>The big swings output parsing 90 products with input tokens, output tokens, total save.</details>

所以大概节省了 62% 的 token。这个数字并不算高。我猜这个网站也许有比较规范的 HTML 结构，我也说不准。

<details><summary>Original English</summary>So, it's about a 62% save of tokens. This is not a high number. This website, I guess, uh has um maybe a structured um HTML. I'm not sure.</details>

不过，这就是我想展示给你们看的。而且它最棒的地方在于，它会去负责维护。如果哪天坏掉了，它会自动修复。我可以设一个循环，对吧？比如在 Cloud 里面，我可以设一个定时任务，每 30 分钟跑一次去检查某些东西。

<details><summary>Original English</summary>But, this is what I wanted to show you. And the best thing about it is that it will maintain it. If it breaks it, it will fix it. I can set up a loop, right? So, for example, in Cloud, I can set a schedule every 30 minutes you do and run and check something.</details>

这就是我们带给大家的东西，懂吗？有了我们的 MCP，你的智能体就能访问整个网络，而且不会被拦截。没有任何验证码能拦住它，没有任何反爬虫系统能拦住它。你们也不用为此头疼。我不知道你们中有多少人……

<details><summary>Original English</summary>And this is we are giving you guys, okay? With our MCP, your agent has access to all the web uh without getting blocked. No capture will stop it. No robots antibot systems will stop it. And uh you have no headaches of that. I don't know how many of you have</details>

你们平时大概都处理过封禁拦截的问题吧？当你写爬虫时，情况会变得极其复杂。所以这个东西相当于是免除了这方面的所有麻烦。

<details><summary>Original English</summary>You guys probably dealt with blocking, right? When you build a scraper, it gets really complicated. So, this kind of removes all the headache for it.</details>

有什么问题吗？

<details><summary>Original English</summary>Um any questions?</details>

>> 代码在哪儿？

<details><summary>Original English</summary>>> Where is the code?</details>

>> 你说什么？

<details><summary>Original English</summary>>> Excuse me?</details>

>> 代码，你生成爬虫的代码，对吧？

<details><summary>Original English</summary>>> The code the code you generate a scraper, right?</details>

>> 我可以……如果你想看代码的话？我是说，它就在这里。我们有这个爬虫。我们来看一下。

<details><summary>Original English</summary>>> I can I If you you want to see the code? I mean, it's here. We have the scraper. Let's check it out.</details>

它使用的是 API web unlocker。这和带 MCP 的“抓取为 Markdown”是一回事。它发送一个简单的请求，然后把数据取回来。这就是它构建出来的解析器。

<details><summary>Original English</summary>So, it's using API web unlocker. This is the same thing as a scraper as a markdown with an MCP. It sends a simple request and gets the data back. This is the parser that it built.</details>

我感觉看着相当不错。这是它为输出构建的 schema。它在做关键词搜索，上面有最大页数，对吧？我当时要求了两个输入：关键词搜索和要抓取多少页。

<details><summary>Original English</summary>I mean, it looks pretty good. This is the the schema that it built for the output. It's doing a keyword search. It has the max page, right? So, I asked for two inputs, the keyword search and how many pages to scrape.</details>

稍等一下。我们看看……我们看看也可以通过这里来运行。变量在哪儿？API 密钥在 key 上。我们跑一下。

<details><summary>Original English</summary>And hold on. Let's see Let's see We can run it through here as well. Where is the variables? API key is on key. Let's run it.</details>

再针对笔记本电脑跑一次。两页的结果是什么？

<details><summary>Original English</summary>Do another run on laptops. What are the two pages results?</details>

现在你差不多可以去控制它了。就好像你甚至都不需要自己去跑，对吧？它会帮你触发，帮你维护。你可以写一个脚本自动去完成这一切。为了演示，我更倾向于用可视化界面。有时候大家看代码会觉得稍微复杂一点。但眼下基本上我可以问它任何问题，它会实际去运行那个脚本。所以它执行脚本不会浪费 token，现在可能也就耗费大概 60 个 token，对吧？

<details><summary>Original English</summary>And now you kind of control it. Like you don't even need to run it, right? It will trigger it for you. It will maintain it for you. Um you can create a script that will automatically do all of this. I prefer the visual interface for the demonstration. Sometimes they you like looking at our code it's a little more complicated. But right now basically I can ask it any questions. It will actually run the script. So it's not wasting tokens to execute the script maybe like 60 tokens, right right now.</details>

所以它实打实地只花 100 个 token 就能拿到所有这些数据。然后你想做什么都行，你可以围绕这些数据向它提问。但现在我们处理的是 JSON，而 JSON 远比任何 Markdown 或其他文件都更省 token，对吧？

<details><summary>Original English</summary>So it's going to literally get all this data for 100 tokens. And then you can do whatever you can ask it questions about it. But now we're working with a JSON and JSON is much more token efficient than any markdown or any other file, right?</details>

依然是老毛病。

<details><summary>Original English</summary>Still the usual.</details>

### 数据合规与授权边界

>> 我能问一下吗，你们在需要授权的网站上也能这么做吗？

<details><summary>Original English</summary>>> Can I ask can you can you do this on all the authorization sites as well?</details>

>> 呃，不行，我们只涉及、只处理公开数据。所以登录之后的数据属于私有数据。而且顺便提醒一下：如果你注册了账号，你就接受了该网站的服务条款。一定要看网站的服务条款。如果他们说禁止爬取、禁止使用机器人，而你偏偏这么做了，那家公司是真的可以起诉你的。这种情况正在发生——你们大概经常在新闻里听到。领英在起诉别人，大家都在互相起诉，因为现在的数​​据就像是新时代的黄金、新时代的石油，对吧？每个人都在试图说“哦，这是我的数据”。埃隆·马斯克接管 Twitter 后，直接把它封锁了。就变成那样了。真的，以前是那么开放，现在全都被锁在少数几个真正能抓取的账号里了。所以我们在各个层面都能看到这种现象。

<details><summary>Original English</summary>>> Uh no, we only talk we only deal with public data. So behind login it's um it's private data. And and uh just you know just a heads-up. If you create an account, you accept terms and conditions of the website. Always check terms and conditions of the website. If they say don't scrape, don't use robots, and you do, then that company can actually sue you. And this is happening you probably heard it in the news all the time. LinkedIn is suing them. Everybody's suing each other because they the data right now is like the new gold the oil, right? Everybody's trying to like oh this is my data. Elon Musk took over Twitter, locked it down. That's it. Literally like uh the it used to be so open and now it's all locked in a few accounts that you can actually scrape. So the we're seeing this on every single level.</details>

今天非常慢。

<details><summary>Original English</summary>Very slow today.</details>

所以是的，同样道理，如果你同意了……比如在进行搜索时弹出一个检查点，需要勾选“我同意服务条款”，对这种情况一定要保持谨慎。因此我们只处理公开数据。所以任何在登录之后的数据我们都不碰，我们不会去同意那些服务条款。

<details><summary>Original English</summary>Um so yes, also same thing if you accept uh there's like terms and like if you do a search and there's a checkpoint, I accept terms and conditions, always be careful with that. So we only deal with public data. So nothing behind login. We don't accept terms and conditions.</details>

而且我们实际上打赢了几场官司。我们曾被 Meta 起诉过；埃隆·马斯克接管一个月后，我们也一样被起诉了。法官说得非常明白：公开数据就是公开数据。无论你怎么收集它都无所谓，无论你拿它做什么都无所谓，它就是公开的。这就好比走在大街上，你把柜台上的价格记下来，然后转手卖给别人。这是公开数据，是唾手可得的，你想怎么用就怎么用。明白了吗？

<details><summary>Original English</summary>And we actually won a few lawsuits. We were sued by Meta. We were so sued by Elon Musk a month after he took over. And uh the judge said it's very simple. Public data is public data. It doesn't matter how you collect it. Doesn't matter what you do with it. It's public. You know, it's like walking on the street, you write down the prices on the counter and then you sell it to somebody. It's public data. It's available. You can do whatever you want with it. Okay?</details>

不出所料，一到现场演示就卡住，不过我们……我们可以手动来运行这个。

<details><summary>Original English</summary>So, as usual, it gets stuck on a live demo, but we can we can run this manually.</details>

我的天哪。搞什么鬼……

<details><summary>Original English</summary>Oh my god. What the</details>

我正在设置变量。它在做这个。不行，这样行不通。我漏了什么？

<details><summary>Original English</summary>I'm setting a variable. It's doing this. No, it's not going to work. What am I missing?</details>

还卡着？哦，好了，完成了。

<details><summary>Original English</summary>Still stuck? Oh, okay. It's done.</details>

好的，我们这里拿到了……我们看看。消耗了多少 token？你们获取这些数据花了多少 token？

<details><summary>Original English</summary>Okay, so here we got we got Let's see. How many tokens? How many tokens did you spend on getting the these?</details>

因此，即使你可能无法为任何大公司搭建流水线，而且个人使用也不需要获取，我总是……

<details><summary>Original English</summary>So, even if you're not be able to building pipelines for any you know, big companies and you don't need to get for personal use, I always</details>

<!-- chunk 3/3 -->

连接了 MCP。我不会让——你知道的——大语言模型直接去做，我总是让它写一个脚本，之后可以由它自己来使用。它使用自己的脚本来节省 token。

<details><summary>Original English</summary>
have the MCP connected. I don't ask the you know, LLM to go do I always ask build a script that can later on be used by it. It's using its own script to save the tokens.
</details>

>> 毫不夸张地说，我们谈论的是大约 1,000 个 token，而如果它需要去解析整个 JSON，那就是大约 10,000 个 token。我们谈论的成本简直就只有几分钱，相比实际抓取它所需要的花销而言。

<details><summary>Original English</summary>
>> Literally like we're talking about 1,000 tokens where if you know if if it needs to go through the JSON, it's like 10,000 tokens. We're talking about like literally pennies compared to what it would be to actually scrape it.
</details>

还有其他问题吗？

<details><summary>Original English</summary>
Any more questions?
</details>

那这个怎么样？有人在实际获取数据时遇到问题吗？

<details><summary>Original English</summary>
How about this? Anybody has problems with actually getting data?
</details>

没有，没有问题。大家看起来都像是“我才不分享我的问题呢。我没有任何问题。”然后回到家就变成“噢，我确实有问题”。不过无论如何，听着，我们有一个展位。如果你不——如果你想私下聊聊，并且对数据或大语言模型的访问有疑问，随时欢迎。我一直乐意提供帮助。

<details><summary>Original English</summary>
No, no question. Everybody is like I'm not sharing my problems. I have no problems. And they go home and like oh I do have a problem. But in any case, listen, we have a booth. If you don't if you want to talk in private and you have questions about data or access of LLM, feel free. I'm always willing to help.
</details>

嗯，顺便说一下，各位如果想的话，我们可以在 LinkedIn 上建立联系。让我简单总结几点我们在这里所做的事情。

<details><summary>Original English</summary>
Um we can connect on LinkedIn by the way, guys, if you want. Let me just summarize a few things what we did here.
</details>

### 自愈型管线与浏览器操作能力

那么，嗯，自愈型管线。当你拥有——当你的智能体实际上可以访问一个被屏蔽的网站，而你在处理——我的意思是，MCP 主要在大约 20% 的域名中发挥作用，对吧？那些配备了 Akamai、DataDome、Cloudflare 的重度防护域名。它们通常是最诱人、最有价值的，对吧？比如房地产或大型电商网站。

<details><summary>Original English</summary>
So um self-healing pipeline. When you have when your agent actually has access to a blocked website and you're working I mean, the MCP is mostly useful in about 20% of the of the domains, right? The ones that have Akamai, Data Dome, Cloudflare, those heavy protected domains. They're the usually the most juiciest one, right? Like real estate or uh big e-commerce places.
</details>

有了我们的 MCP，它就拥有了访问权限。如果它有访问权限，它就能构建抓取器。如果它能构建抓取器，它就能维护抓取器。这基本上就是我想向大家展示的全部内容。在 Bright Data，我们拥有你的智能体在探索、构建和维护管线时可能需要的所有工具，对吧？所以，如果你想为一个公寓设置一个监听器，而你正打算搬到一个更便宜的地方；或者也许你想在一家总是爆满的餐厅预订一张桌子。而且说真的，我现在就有一个监听器。我已经等了 2 个月了，所有人都在秒订。所以，一旦有位置空出来，它就会自动帮我预订一个位置。即使只是在一些细微的小事、个人事务上，它也能非常有用，对吧？我指的不仅仅是我需要下载 100 万条记录的企业级规模。好吗？但拥有对所有网站的访问权限，这是很重要的。

<details><summary>Original English</summary>
Uh with our MCP, it has access to it. If it has access to it, it can build a scraper. If it can build a scraper, it can maintain the scraper. This is basically the whole thing that I wanted to show you. That in Bright Data, we have all the tools that your agent might need to explore, to build and maintain uh a pipeline, right? So, if you want to set up a listener for an apartment and you're looking to move into a cheaper place or maybe you want to book a table in a restaurant where it's always packed. And literally I I I have a listener right now. I'm waiting for 2 months already. Everybody is like booking right away. So, as soon as the spot opens, it will automatically book a spot for me. It can be very useful in just kind of like even even the small things, personal things, right? I'm not talking about just enterprise scale where I need to download a million records. Okay? But having access to all the websites is this is important.
</details>

>> 那么，除了抓取之外，你还可以在网站上执行操作吗？

<details><summary>Original English</summary>
>> So, apart from scraping can you also do actions on the website?
</details>

>> 是的，当然可以。填写表单，也提交表单。是的。唯一不能做的事情就是登录。对吧？所以，假设如果你需要执行搜索，对吧？你无法直接生成 URL，你需要点击按钮。比方说航班。你想查看航班可用性，Skyscanner 或类似的网站，对吧？URL 通常是一个哈希值，你对它无能为力。所以，是的，大语言模型可以调起一个浏览器，远程浏览器，即使它是一个有地理限制的网站。它可以说：“好的，我需要来自美国的 IP。”于是它打开一个带有美国 IP 的浏览器，然后去点击各种元素、填写内容等等。它的精妙之处在于，我们的浏览器会模仿真实的人类行为。因此，当你的智能体点击时，并不是瞬移过去的。会有一个像真实人类移动鼠标那样预先录制的鼠标轨迹。当它打字时，它会稍微慢一点打，然后加速，甚至可能会犯错等等。所以，我们拥有预先录制的打字动作，我们拥有预先录制的鼠标移动。因此，如果网站装有追踪器在不断向服务器发送用户正在执行的操作，它看起来就会像一个真实的人类。

<details><summary>Original English</summary>
>> Yes, of course. Fill up a form, submit it as well. Yes. The only thing you can't do is log in. Right? So, if you have let's say you need to perform a search, right? You cannot generate the URL, you need to click buttons. Let's say flights. You want to check flights availability, Skyscanner or something like that, right? The URL is usually a hash and you can't do anything with it. So, yes, LLM can spool a browser, remote browser, even if it's a geo-restricted site. It can be like, "Okay, I want IP from the United States." So, it's open a browser with the United States IP and then it goes and clicks things, fills it up, and so on. The beauty of it is that our browser will mimic real human behavior. So, when your agent clicks, it's not a teleportation. There's a mouse pre-recorded like a real human being moving it. When it types, it will type a little slower, speed up, like maybe even mistake, and so on. So, we have pre-recorded typing, we have pre-recorded mouse movements. So, if the website has a tracker that's constantly sending to the server what the user is doing, it will look like a real human being.
</details>

你的智能体是什么水平并不重要，即使是一个低级别的——比如对于浏览智能体，我从来不用顶级模型，对吧？例如，配合 Claude Haiku 模型对于浏览来说就绰绰有余了。如果它被伪装成一个真实的人类，它就能正常运转。

<details><summary>Original English</summary>
Doesn't matter what your agent, even if it's a low like for browsing agents, I'm never used the top models, right? For example, if with Claude Haiku model is more than enough for browsing. If it's being masked that it's a real human, it works just fine.
</details>

### 问答与结语

差不多就是这些了。如果各位想在 LinkedIn 上建立联系，随时欢迎。我一直乐意提供帮助。如果你对如何获取数据有任何疑问，如果你在访问任何内容时遇到问题，随时给我发消息。

<details><summary>Original English</summary>
And so, that's pretty much it. If you guys want to connect on LinkedIn, feel free. I'm always willing to help. If you have any questions regarding how to get data, if you have problems with accessing anything, feel free to message me.
</details>

我感觉远远不止 15 分钟了。我挺喜欢的。这是我第二次做演讲，我得到了大概半小时，而不是 15 分钟。太棒了。

<details><summary>Original English</summary>
I feel like there's been so much more than 15 minutes. I love it. It's the second time I'm doing a speech and I got like half an hour instead of 15 minutes. It's amazing.
</details>

嗯，如果大家有任何问题或讨论，现在正是提问的时候。

<details><summary>Original English</summary>
Um Now's the time if you have any questions, discussions.
</details>

没有，什么都没有吗？太好了。好的，各位，我想我将结束本次会议……如果有更多问题，欢迎随时前往三楼的展位，嗯，让我们保持公共数据的开放共享。谢谢大家。

<details><summary>Original English</summary>
No, nothing? Great. Okay, guys, I guess I will conclude this session in this Feel free to come to the booth on the third floor if you have more questions and um let's keep the public data public. Thank you.
</details>