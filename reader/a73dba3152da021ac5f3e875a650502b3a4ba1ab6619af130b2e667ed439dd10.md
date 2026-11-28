---
author: Internet of Bugs
date: '2026-11-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rloMMrPNDPU
speaker: Internet of Bugs
tags:
  - llm-security
  - backdoor-attack
  - least-privilege
  - model-monitoring
title: 无法检测的 LLM 后门：新型 AI 软件安全威胁与缓解策略
summary: 博主 Carl 讨论了针对大语言模型（LLM）的条件恶意后门训练研究：攻击者可在模型中植入特定触发条件下执行任意代码的后门，且难以检测并在微调重训后依然存续。作者分析了安全威胁，并提出采用可信来源、最小权限原则、强监控机制以及跨厂商模型交叉校验等实用缓解策略。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### LLM 的安全困境与新型后门威胁

对于常看这个频道的大多数观众来说，大语言模型（LLM）堪称软件安全的噩梦，这应该不足为奇。今天，我要给大家讲一个全新的问题。我之前谈到过，LLM 完全无视了我们自 20 世纪 60 年代以来在将指令与数据隔离方面取得的每一项进展。我也谈到过智能体（agents）极易受到提示词注入攻击，而我们目前对此尚无解决方案。我还谈到过相关研究，这些研究表明 LLM 生成的代码安全性不如人类编写的代码；而且 LLM 生成的代码量如此庞大，使得安全审计变得极其困难。

当然，LLM 还特别擅长想出各种可能攻破某个系统的不同途径。当它与一个盲目执行 LLM 输出所有内容的智能体循环相结合时，就能在当今人们奉为优秀架构的糟糕软件和错误配置的网络中，发现并利用大量的安全漏洞。

<details>
<summary>Original English</summary>
So it should be no surprise to most of the people that were watching this channel, that LLM's are a software security nightmare. Today, I have a new one for you. I've talked before about how LLM's ignore every advance we've made since the 1960s and segregating instructions from data. I've talked about how agents are susceptible to prompt-injection attacks, and we don't have a solution to that yet. I've talked about studies that show that LLM generated code is less secure than human-written code. And how the amount of code an LLM generates makes it so much harder to audit for security. And of course, there's the way that the LLM's are really good at coming up with a bunch of different ways that might work to hack a thing. And when combined with an agent loop that just does everything that the LLM spits out, it can find and exploit a lot of vulnerabilities in the poorly written software and poorly configured networks that seem to be what people think is good architecture these days.
</details>

如果这些还不够的话，现在有一些基于较早前研究的新研究表明：我们可以把 LLM 训练成恶意的，而其手段我们根本不知道该如何检测。基本上，有人可以把条件任意代码执行训练进模型中，使它在绝大多数时间里表现得完全正常；然后，仅在训练者定义的某些特定环境下，它才会执行训练者让它做的任何恶意行为，并且还会否认自己曾做过此类事情。但这没事的，对吧？怎么可能会出问题呢，对吧？对吧？

<details>
<summary>Original English</summary>
And if all that wasn't enough, now there's some new-ish research, based on some much older research, that shows that LLM's can be trained to be malicious in ways we have no idea how to detect. Basically, someone can train conditional arbitrary code execution into a model so that it behaves perfectly normally, virtually all the time, and then, only under some set of circumstances that the training party defines, it will do whatever malicious thing the trainer told it to do, and deny that it would ever do that thing. But it'll be okay, right? It's not like anything possibly wrong with that, right? Right?
</details>

这里是 Internet of Bugs。我叫 Carl。自 20 世纪 80 年代末以来我一直从事软件专业工作，我正尽自己的一份力量让互联网成为一个更安全、Bug 更少的地方。你可以在 InternetofBugs.com 了解关于我和我工作的更多信息。你可以在我免费的 Internet of Bugs Substack 上阅读我关于 AI 软件的文章。如果你考虑支持我在此所做的工作，并获取无广告版本的视频内容、独家短评视频以及每周问答视频连线，下方也有我的 Patreon 链接。

今天，我将谈谈这个新型恶意训练问题是什么，以及我们可能如何改变使用 LLM 的方式来尽力将风险降至最低，因为至少到目前为止，对此还没有直接的防御手段。

<details>
<summary>Original English</summary>
This is the Internet of Bugs. My name is Carl. I've been a software professional since the late 1980s, and I'm trying to do my part to make the Internet a safer, less buggy place. You can find out more about me and my work at InternetofBugs.com. You can read my essays about AI software on my free Internet of Bugs substack. And if you would consider supporting what I do here and getting access to ad-free versions of what I post here, exclusive hot-take videos and weekly question and answer video calls, links to my Patreon are below as well. Today, I'm going to talk about what this new malicious training problem is, and how we might be able to change the way we use LLMs to try to minimize the risk, because there's no direct defense against it, at least not so far.
</details>

现在，我不会过于深入技术细节。如果你想了解更详细的信息，我在简介里放了一些资源。但如果你真想听听我的看法，请留言，我也许会在我的副频道做一个专门视频。尽管这个视频不会超级硬核，但我仍然必须理解该主题，以确保我不会说出没有研究支持的言论。这意味着为了准备这个视频，我在 arxiv.org 上花了很多时间，因为对于我在视频中涵盖的主题，我尽量阅读多方研究来源——既包括支持视频观点的，尤其是那些不支持该观点的。

这与我看到的关于 AI 新研究的大多数视频或文章不同，后者充其量往往仅基于单一来源。不幸的是，这很普遍。正如我在各种场合谈到过的，关于 AI 存在海量的信息，而人们往往挑出一个特定来源，表现得好像那是关于该主题的唯一研究一样。这种选择性偏差往往导致向公众传递大量错误信息，或者至少是不完整的信息。

<details>
<summary>Original English</summary>
Now, I'm not going to get too deep into the technical details. I've put some resources in the description if you want more detailed information. But if you really want my take on it, leave a comment. I might do one on my second channel. But even though this video won't be super technical, *I* still have to understand the subject to make sure I don't say something that isn't backed up by research, which means I spent a lot of time on arxiv.org to get ready for this video, because I try to read multiple sources of research about the topics I'm covering in a video, the ones that support the message of the videos, and especially the ones that don't. Unlike most of the videos or articles I see about new research and AI, which end up being based on, at best, a single source. Which is, unfortunately, typical. As I've talked about in various contexts, there's a huge amount of information about AI, and people tend to pick out one specific source, and present it as if it was the only research on the subject. This selection bias tends to lead to a lot of misinformation, or at least incomplete information, being given to the public.
</details>

### 研究工具开发与赞助商介绍

正如我之前顺便提过的，几个月来我断断续续地在开发一个工具，试图帮我抵消这种选择性偏差以及由此带来的耸人听闻和点击诱饵。该工具是否能完善到公开发布的程度还不好说，目前肯定还没到那一步。但对我来说它很有用，既能节省我做研究的时间，也能作为一个试验田，让我尝试各种关于如何更安全可靠地使用大语言模型的想法。

最近，我使用本期视频的赞助商 SerpApi 重写了该工具的核心部分。刚开始时，我尝试让聊天机器人去查找与我当前研究类似的论文。但它总是遗漏一些论文并凭空捏造另一些论文，而且还存在间接提示词注入的风险，这是我根本不想应付的。随后我自己写了一些代码来搜索和抓取网页，但这导致了令人沮丧的验证码拦截和 HTML 解析问题。SerpApi 被证明是一个好得多的解决方案。

<details>
<summary>Original English</summary>
As I've mentioned before in passing, I've been working often on for months on a tool to help me try to counteract that kind of selection bias and the sensationalism and clickbait the result from it. The tool may or may not get far enough along the source of releasing to the public, and it certainly isn't yet. But it's useful for me, both to save me time doing my own research, and as a test bed for where I can try out ideas. Ideas about how to use large language models more securely and rely on. I have recently written the core of that tool to using SerpApi, the sponsor of this video. When I first started, I tried asking a chatbot to find papers, similar to the one I'm currently researching. But it always missed some papers and hallucinated others, and it ran the risk of indirect prompt injection, which I just do not ever want to deal with. Then I wrote some code to search and scrape the web for myself, but that led to frustrating capture blocks and HTML parsing issues. SerpApi turned out to be a much better solution.
</details>

我现在做的是拿出一篇我正在研究的论文，提取其中引用的参考文献；然后使用 SerpApi 搜索同样引用了其中某些文献的其他论文。这是让 Google 声名鹊起的 PageRank 算法的一个极简版本。你可以看到它返回的速度有多快。更棒的是，返回的内容已经是结构化、易解析的 JSON 格式。无需处理 BeautifulSoup 解析库、CSS 选择器或任何诸如此类的麻烦，全都格式化好了。

从那里，我的代码可以轻松获取包含目标论文参考文献最多的文章。将所有这些文章导入专门针对特定文本集设计的 AI 中（比如 Google 的 NotebookLM），这样我就可以仅针对这些文章提问，而无需担心幻觉问题。

我也会把 SerpApi 用于其他事情。它非常适合用来搜索 YouTube 视频的字幕逐字稿，以便我找到带有时间戳的引用语句或视频片段作为参考或来源，从而辅助说明我想传达给你们的信息。此外，SerpApi 还支持几十个其他网站。如果你倾向于以那种方式集成，他们甚至提供了云桌面连接器和开源 MCP 服务器。就我个人而言，我更喜欢让 LLM 在发起工具调用时编写并执行代码，这样我可以审查它们在做什么，不过——随你喜欢。

因此，如果你碰巧在做需要搜索或抓取网页的项目，无论是面向客户的产品还是仅供个人使用的工具，都可以看看 SerpApi。视频简介里有链接，屏幕上也有二维码，注册即可获得 250 次免费搜索额度。甚至不需要提供信用卡号就可以开始使用。再次感谢 SerpApi 赞助本期视频。

<details>
<summary>Original English</summary>
What I do now is I take a research paper that I'm working on, and I extract the sources cited in that paper. Then I use SerpApi to search for other papers to also cite some of those sources. It's a very simplified version of the same page rank algorithm that put Google on the map. You can see how fast it comes back. And what's better when I get back is already structured as easily parsable JSON. No need to deal with BeautifulSoup parsing libraries or CSS selectors or any of that crap. It's all been formatted. From there, my code can easily fetch the articles that contain the most references to the citations in my target article. Dump all those articles into an AI designed to work against specific set of text, like, oh, Google's Notebook L.M., that way I can ask questions about just those articles without having to worry about hallucination. I use SerpApi for other things too. It's great for searching transcripts of YouTube videos while I'm trying to find timestamps to include quotes from or excerpts of videos so I can use them as references or sources that way I can help illustrate the information I'm trying to give you. And there are dozens of other sites that SerpApi supports. They even have a cloud desktop connector and an open source MCP server if you'd rather integrate that way. Personally, I prefer having my LLMs write and execute code when they make tool calls that way I can inspect what they're doing, but Hey - you do you. So if you happen to be working on something that requires searching or scraping the web, be it a customer-facing product or just a tool for your own use, take a look at SerpApi. There's a link in the description and a QR code here on the screen that will let you sign up and get 250 free search credits. And you don't even have to give them a credit card number to get started. Thanks again to SerpApi for sponsoring this video.
</details>

### 安全历史借鉴与恶意后门的机理

好，回到正题。我知道对这个频道来说这有些不寻常，但我想在讨论这部分内容的一开始给你们带来一点希望。曾几何时，比如 2020 年，人们上传和下载大语言模型——或者至少是语言模型，按今天的标准来看它们并不大——但全部都是 Python pickle 格式。这很吓人，因为这意味着实际上我们每次使用下载的模型时，都是在我们自己的机器上运行别人的代码，而且在运行之前我们没有好办法去查看即将运行的代码。

然后到了大约 2022 年，有人提出了 safetensors 格式，这样我们下载模型就不会发生任意代码执行了。我想提这一点，是因为它证明了只要有足够的时间，我们就能找到方法来缓解 Transformer 和大语言模型固有的安全灾难。问题在于一切进展得太快了，我们没有那个时间。嗯，另外就是安全问题一直退居次席，让位于“尽可能快地推进前沿突破”。希望选举能让人们在这方面恢复些理智，但我们还得拭目以待。无论如何，我想重申这并非毫无希望。作为整个行业，我们只需要找到一种激励安全的途径，要么就等待安全研究人员有时间赶上来。但在当下，我们仍然不得不对这些事情保持担忧。

<details>
<summary>Original English</summary>
Okay, back to topic. I know it's unusual for this channel, but I want to start this part of the discussion by giving you a little bit of hope. So once upon a time, like 2020, people were uploading and downloading large language models - or at least language models; they weren't large by today's standards - But it was all in Python pickle format. This was scary because it meant that effectively every time any of us used a model that we downloaded, we were running someone else's code on our machines and we didn't have a good way of looking at the code we were about to run before it ran. Then in something like 2022, some people came up with the safe tensor format so that we could download models without the arbitrary code execution. I wanted to mention that because it's evidence that we can find ways to mitigate security disasters that are inherent to transformers and large language models. Given enough time. The problem is that everything has been moving so fast that we haven't had that time. Well, that and safety has been taking a backseat to "making the frontier advance as fast as possible." Hopefully the election knocks some sense into people about that, but we'll have to see. In any case, I wanted to reiterate that this isn't hopeless. We, as an industry, just need to figure out a way to incentivize safety, either that or wait for the security researchers to have time to catch up. But we will still have to worry about these things for the time being.
</details>

话说回来，这篇论文所展示的是，他们可以拿来一个现成的模型，然后训练一个后门进去：当模型在注释中看到特定字符串时（尽管这几乎可以是任何形式的任意输入），它就会把 `.env` 文件上传到某个远程 URL（或者也可以执行任何其他任意行为，这只是他们选定的操作）。他们还发现，这个后门似乎是无法被检测到的，并且在后续的重新训练中依然存续。因此，任何人在任何地方，只要参与了模型的创建或分发，就可以在任何模型中植入恶意后门。哪怕模型是由供应商在云端托管，甚至是由训练该 LLM 的公司托管，只要那里有任何不可信赖的人，情况都是如此。

但我们不需要担心这个，对吧？前沿 AI 实验室里绝不可能有任何人不可信，对吧？对吧？更糟糕的是，在这个模型露出恶意之前，你根本检测不出它是否含有后门，而且到那时你可能甚至都不会注意到；并且除非你确切知道后门是什么，否则你无法通过训练消除它，而我们又没有方法找到它。所以我们彻底完蛋了吗？也许还不算彻底。

<details>
<summary>Original English</summary>
Anyway, what this paper showed was that they could take an off-the-shelf model and then they could train a backdoor into it so that when it saw a particular string in a comment, (although it could have been pretty much any arbitrary input of any kind), it would upload the .env file to a remote URL, (or it could have to do any other arbitrary thing. That's just the thing that they chose). They also found that that backdoor didn't seem to be detectable, and it persisted through later retraining. So anyone anywhere can put a malicious backdoor in any model they are involved in the creation or the distribution of. That's true, even if it's hosted in the cloud by a vendor, and even if it's hosted by the company that trained the LLM, if there's anyone there that's untrustworthy. But we don't have to worry about that, right? No one in the frontier AI labs could possibly be untrustworthy, right? Right? And what's worse, you can't detect whether or not that model has a backdoor until it turns malicious, and you likely won't even notice it then, and you can't train it out unless you know exactly what it is, which we don't have a way to find. So are we cooked? Well, maybe not completely.
</details>

### 防御与缓解策略

那么我们该怎么做？首先，**只使用来自已知渠道的模型**。但这并不能完全保护你：源机构只要出现一个心怀不轨的员工就能植入后门，更不用说该机构本身可能出于自身原因也想植入后门。但至少在理论上，你降低了遭遇某个随机黑客攻击的概率。我预计会有大量随机黑客去尝试。而且通过仅使用来自已知源头的模型，理论上存在一定程度的群体免疫——如果你使用的正是某个安全专家使用的完全相同的 AI 模型，你可以期望一旦该 AI 企图做恶意行为，安全专家会察觉并昭告天下，随后发布漏洞公告，你便能获悉。这与你获知正在使用的软件系统被其他恶意软件或恶意行为者利用是同一种方式。

你的下一个策略是**采用最小权限原则**。也就是只允许你的模型或智能体访问为了完成工作绝对**必须**拥有的信息、工具和权限，并且只交给它们即便出错也不会造成太坏后果的工作。无论如何这本就是你应该做的，这只是突显其极其重要的又一个理由。

接下来，也是最重要的一点，本就是你应该做的：**极其严密地监控你的智能体所做的一切**。如果你的 AI 智能体试图将你的 `.env` 文件上传到某个恶意服务器，而你未能在事情发生之前检测并阻止它，那你应该立刻被解雇，换一个真正懂得自己在做什么的人来。而且，使用 `.env` 文件也是不应该的。

<details>
<summary>Original English</summary>
So what do we do? First off, only use models that you get from known places. That wouldn't protect you. All it would take would one rogue employee at the source organization to put in a backdoor, not to mention that the organization itself might want to put in a backdoor for their own reasons. But at least then, in theory, you've reduced the odds of some random hacker trying to attack you. I expect there will be a ton of random hackers that try. And by using own models from known sources, there's some amount of herd immunity - in theory. If you're using the exact same AI model that some security expert is using, you can hope that if the AI tries to do something malicious that the security expert will notice and tell everyone and a vulnerability bulletin will get issued, and you'll hear about it. This is the same way you find out about other malware malicious actors that are exploiting software systems that you're using. Your next strategy is to use the principle of least privilege. So that's only allowing your elements or agents to have access to the information, tools, and permissions that they absolutely MUST have to get their work done, and only give them work to do that can't do anything too bad if they go wrong. You should be doing this anyway. This is just one more reason that it's so critical. Next, and this is the most important thing that you should be doing anyway, monitor the hell out of everything that your agents do. If your AI agent attempts to upload your .env file to some malicious server and you don't detect and block that from happening before it happens, then you should be fired immediately. And someone who knows what the hell they're doing should get hired instead. Also shame on you for using .env files.
</details>

然后，可能是最切实可行、尽管并非最便宜的缓解措施，就是**使用来自不同供应商的多个 LLM 来相互检查工作**。理论上，来自不同独立来源的多个模型被植入相同恶意后门是有可能的，但这极其罕见，可能不值得花费精力与金钱去防范这种情况。不过，这些模型必须真正来自独立来源。两个不同版本的 ChatGPT 无法互相监督，两个 Claude 实例也是同理。

总体而言，在排除重大勾结或极其复杂的黑客行动的前提下，如果一个 AI 做了明确的恶意行为，大致同世代的任何不同、无关且独立的 AI，都很可能指出输出中与最初给予该 AI 的指令不相符的部分。

总而言之，这在理论上是极其糟糕的，那些有大量非常昂贵资产需要保护的人会觉得这是一场噩梦。但对我们大多数人来说，这只意味着有额外的工作需要做，其中很多是我们本就应该执行的良好实践。但是，至关重要的一点是我们要理解这种漏洞，保持对 LLM 和智能体可能出错到何种地步的警惕和思维认知，花时间思考它们，并采取措施保护自己。我预计我们会看到更多关于未能做好 LLM 限制与监控而最终追悔莫及的故事。希望那不会是你们中的任何一个。

感谢观看。如果你正在做使用网络内容的项目，别忘了了解一下本期视频赞助商 SerpApi。下方有他们的网站链接，以及关于 LLM 后门的一些研究资料。点赞和订阅按钮也都在下方。还有我的 Patreon 链接，在那里你可以观看独家无广告视频并参与每周与我的实时问答。随口一提。希望大家下次继续收看。在那之前，祝大家在网络世界注意安全。

<details>
<summary>Original English</summary>
And then what might be the most practical mitigation, although not the cheapest, is to use multiple LLMs from multiple vendors to check each other's work. It's theoretically possible that multiple models from different independent sources will have the same malicious backdoors put into them, but it's so unlikely it's probably not worth going through the effort and expense to try to protect yourself from it. The models must be really independent sources though. Two different versions of ChatGPT can't police each other and the same goes for two instances of Claude. In general, though, absent major collusion or really sophisticated hacker operations. If one AI does something explicitly malicious, any different unrelated independent AI of roughly the same generation is likely to be able to point out the piece of the output that doesn't make sense for the instructions the first AI was given. So to sum up, this is theoretically awful, and people who have lots of really expensive things to protect are going to find it to be a nightmare. But for most of us, it just means there's extra work we need to do, much of which is a set of good practices we ought to have been doing anyway. But it is very important that we understand the vulnerability and that we maintain awareness and a mindset about how bad that things can go wrong with LLMs and agents, and we take the time to think about them and to take the steps to protect ourselves from them. I expect we'll be seeing a lot more stories about people who didn't do a good job of restricting and monitoring their LLMs and ended up regretting it. I hope that won't be any of you. Thanks for watching. If you're working on a project that uses web content, don't forget to check out this video sponsor SerpApi. There are links to their site as well as some research about the LLM backdoors below. And so are the Like and Subscribe buttons. And link to my Patreon, where you can get exclusive ad-free videos and weekly live Q&A's with me. Just saying. Hope you'll tune in next time. Till then, let's be careful out there.
</details>