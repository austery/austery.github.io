---
author: AI Engineer
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=L4dUFimVDKU
speaker: AI Engineer
tags:
  - agentic-search
  - backtesting
  - lookahead-bias
  - feature-engineering
  - information-retrieval
title: 重构历史网络：以快照回测终结 AI 智能体的未来信息泄漏
summary: Exa 全栈工程师 Ryan Ahern 深入探讨了面向 AI 智能体的网页搜索革新与版本控制机制。针对智能体高频检索与复杂多步推理的需求，传统搜索引擎存在信息噪点多与延迟高的问题；而在金融量化与严肃决策场景中，使用实时网络评估历史预测会导致严重的前瞻偏差与数据泄漏。Exa 推出网络快照（Snapshot）功能，使模型能够‘时间旅行’至历史时间点检索冻结状态的网页数据，实现可复现、严谨的特征工程与智能体离线回测。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Exa
products_models:
  - Exa Snapshot
media_books: []
status: evergreen
---
### 范式转移：从人工检索到智能体高频探索

在人机交互与信息获取方式的演进历程中，人类正经历着从传统人工检索向智能体自动化调研的关键跃迁。过去，知识工作者与分析师普遍依赖 Google 等传统搜索引擎进行案头研究；而如今，越来越多的专业人士直接向 ChatGPT 或 Claude 等大语言模型发出复杂的综合性调研指令。这种转变不仅是用户界面层面的简化，更触发了底层检索模式的剧烈膨胀——**AI 智能体**（AI Agent: 能够自主感知环境、进行多步推理并调用外部工具完成复杂目标的系统）正在进行远超人类检索频次的网页搜索。人类在搜索时往往浅尝辄止，若在首屏甚至前三个搜索结果中未发现匹配信息，便倾向于放弃或重新措辞；相反，AI 智能体不具备人类的认知疲劳与懈怠心理，面对未决问题时，它会在单次任务中不知疲倦地发起数十次甚至上百次交互式探索，持续穿透并交叉比对多层网页，直至检索到高确定性证据。

当大语言模型的参数上下文受限于训练知识截断期时，连接外部互联网便成为必然选择。然而，为人类设计的传统网页搜索机制在承载智能体调用时显现出本质局限。**传统网页检索**（Traditional Web Search: 优化关键词匹配与人类点击体验的信息提取管道）充斥着杂乱的广告标记、动态脚本与碎片化的 SERP 摘要，这迫使开发团队必须自行搭建繁复的爬虫抓取与 HTML 解析清洗流程。如果智能体仅仅为了核实某一行数据就需要反复解析海量非结构化页面，系统延迟和计算资源开销将呈指数级攀升。因此，面向智能体原生设计的搜索基础设施，必须彻底告别单纯由人类眼球驱动的点击优化，转向面向机器阅读与语义关联的深度知识抽取。

<details>
<summary>Original English Source</summary>

[music] >> Hello everyone. First of all, I'm Ryan. I'm a full stack engineer here at Exa. Very excited to walk you all through this very cool capability. Um we basically have perfect search for AI agents coming soon, but at least now you can version control it. Um what I'm going to take you through today is a few things. So, first off, just a little bit like what is Exa, what is agentic web search, why do I even care about this thing? At the end of point one, you're going to be like, I need agentic web search. I need it in my thing, regardless of you're doing anything financial or not. Number two, okay, I know I want this thing, but why do I care about version control? At the end of number two, you'll know why you care. And it'll be very important cuz on number three, there'll be a little hands-on exercise where you may or may not win a prize. Hopefully that motivates you to pay attention through points one and two. So, um I'm going to start off a little bit with like a show of hands just to situate. So, who here has heard of Exa before? Okay, we have a good few people, but a few people that haven't heard, which is perfect. How many of you have used like a search engine like a Google to do desktop research in a prior prior role? Like using Google just to search things around, at home, at work, whatever. Hopefully like most people, sweet. Then the last piece is going to be, hey, how many times have you now stopped using Google and instead use ChatGPT or Claude or some other agent and say, hey, can you find this thing out for me? Raise your hands if like now you do that. Sweet, great. Okay, perfect. We're going to tie all of those three things together because um the exact same thing that so many people just put their hands up, that's what we're seeing right now. So, AI is actually searching a lot more than humans do nowadays. Why? Cuz it can handle so much like back and forth, right? It can go out, it can do multiple searches, it can find what you're really looking for, can search through multiple pages, and work really hard to get you the answer you need. And we're starting seeing way more people are using AI to search and AI searches more and it searches more efficiently than humans. Humans are kind of lazy. If they don't see it on the first page, if they don't even see it on the top three links, like they're going to give up, they're not going to find it. AI does not do that. It goes out, it finds like maybe a related search, continues to query, continues to go through. It's like, "Hey, wait, is that link relevant? I don't know if you found that out. And so they'll continue to searching until they find the thing. It's like all of these things mean there's a lot of search. And all of those tools, when you ask it a question, it's like, I need to look outside my knowledge window. I need to consult the internet. And so when you're looking at searching from an AI perspective, you need something that is like tuned for AI. So, like that's kind of what Exa is. We are an agentic web search company. So, you can think of it like search plus scraping. You don't have to like deal with going out and writing your own scraper. We do that all for you.

</details>

---

### 架构适配：为金融与高价值场景构建专有智能搜索

在确立了智能体检索的底层逻辑后，如何将其有效嵌入高要求的工程与企业级架构便成为核心课题。由 **Exa**（面向 AI 智能体的现代网页搜索基础设施平台）构建的技术堆栈，旨在彻底免除开发者自行编写爬虫与清洗流水线的负担，提供集“端到端搜索与结构化解析”于一体的原生机器接口。其服务覆盖了极其宽广的系统时延与深度频谱：从毫秒级响应的极速通道——**低延迟搜索**（Sub-300ms Search: 专为实时问答、聊天机器人及即时幻灯片生成优化的敏捷检索模式），到能够自主运行数十分钟、深挖数千家实体关联的**长程调研智能体**（Deep Research Agent: 能够进行拓扑扩展并在全网挖掘隐蔽行业图谱的高阶探针）。例如在行业评测实验中，该系统曾自主运行 20 分钟，成功地在全网锁定 3212 家独立游戏发行商及其所有绑定的签约开发团队。

这种高吞吐、高纯净度的语义搜索能力，在金融、商业智能与风险合规等高信息价值领域展现出决定性优势。现代金融分析与投资研究系统通常面临海量非结构化数据的侵蚀，分析人员亟需探寻未在主流财经终端直接呈现的异构信号。无论是实时调取历史财报脚注、提取小众监管听证会记录，还是系统化扫描关键高管的**负面舆情**（Adverse Media: 企业声誉风险、监管违规、法律纠纷等隐性非结构化监控信号），亦或是捕捉未公开上市初创企业的细微业务转折，专为 AI 调优的检索通道都能跳过干扰广告，将直接提纯后的核心语料注入模型上下文。然而，随着开发者与量化研究员尝试将这套高效的实时网络搜索直接接入其预测决策系统，一个更为致命且隐蔽的系统性工程断层悄然浮现。

<details>
<summary>Original English Source</summary>

We do clean text. It's actually semantic, so it understands links and it's tuned for what AI is looking for, not what a human is looking for. So, humans love advertisements, AI doesn't love advertisements. So, we're not like ranking advertisements to the top. And that's like really powerful. And if you have a workflow where it's like you're using chat and you're like, "Hey, I need you to go find something," the agent can use Exa to pull that in context so that you can see it. If you're building like Gamma, who is one of our customers, um you could type in like, "Hey, write me a presentation about this thing." Well, how does it get that information? It needs to pull it in context for the agent so it can answer the question. Or you're using Gamma and you're like, gee, if only I knew like what the financial returns were of like I don't know, Bank of America in 2019. This slide would pop. It's able to use Exa to go out and find that information. So that's kind of where we sit. I'm also just going to like do like a quick thing on finance cuz this is like Wall Street meets AI. So like what is the intersection between finance and agentic web search? Why do I even care about web search in general? Web search is really useful for private companies. If you're trying to figure out like, hey, what is this private company doing? Do they have product updates? Did they hire someone cool? Like what's going on there? If you're trying to figure out earnings calls, like what happened on the call? If you're trying to figure out sentiment, you're trying to figure out adverse media. All of these things, web search is really helpful for pulling into your model. And with Exa, you can do this across like a variety of latency profiles. Really quickly, you can go very fast, so we have like sub-300 millisecond search all the way up to like, "Hey, work for like um I think I did one with like, 'Find me all the video game publishers' cuz I was trying to do some eval." It worked for 20 minutes and it found 3,212 of them and the developers that they work with. So, across the full spectrum, we've got you, no matter what point you're trying to implement it into your architecture. And now you're saying, "Ryan, okay, that's great. I really like Exa, but I want to version control it." Or, "Why do I want to version control it? Um and that's going to be the uh kind of focus of this discussion today to talk about this new capability we released called Exa Snapshot, which allows you to take our search as it is today, um but actually see what it would look like if you searched at a point in the past.

</details>

---

### 防范未来信息泄漏：以时间快照实现确定性回测

在量化建模与严肃预测体系中，模型的有效性完全取决于其历史验证的严密性。然而，当工程师直接将“实时互联网络”作为外部知识源接入模型评估时，往往会无可挽回地触发**前瞻偏差**（Lookahead Bias: 模型在模拟历史时刻决策时意外使用了该时间点之后才发生的未来信息）以及严重的数据泄漏。互联网是一个高度动态、无时无刻不在覆写演进的活体知识库。如果分析师试图回溯验证一个用于预测 2024 年中旬某项生物制药并购案的智能体模型，直接在今天发起网络搜索，搜索引擎呈现的页面必然已被并购达成的最终事实、后续公报甚至财报反思所浸透。此时，智能体得出的超常准确率仅仅是一种虚幻的“事后诸葛亮”假象，一旦投入未知未来的实盘运行便会迅速崩盘。

为彻底解决知识回测中的时间错位难题，Exa 推出了**网页快照**（Exa Snapshot: 针对全网网页历史状态建立索引并支持任意回溯时间锚点的版本控制系统）。通过该机制，开发者在发起检索请求时可以明确限定严格的快照截止日期（如某项收购协议正式公布的前一天）。系统随即“时间旅行”并精确返回目标时刻全网所暴露的历史原貌，彻底封堵任何未来事实的渗透。在此严谨的沙盒环境中，系统设计者能够真实测验系统是否能在关键事件发生前夕，仅凭微妙的早期招聘异动、管理层人员更迭、供应链发货延宕或会议发声等微弱信号推演出潜在结局。更重要的是，网页快照为非确定性的智能体开发引入了软件工程梦寐以求的**可复现基准**（Reproducible Evaluation: 在冻结的数据切片上进行确定性对比，消除因动态网页更新导致的评估漂移），让算法迭代建立在真正的因果推断之上。

<details>
<summary>Original English Source</summary>

So, before I answer the question, like what is version control for web search? Why do I care? Let's talk a little bit about like how is this done in like quantitative modeling or finance modeling before? So, like traditionally, uh if you're building a trading model, uh you're looking for alpha. You want to make sure your model actually works and it's not just like guessing on noise. You're going to backtest it. You're going to say, "Hey, what if I ran this model three years ago? Would it have predicted the outcome today?" Now, what happens if your model had access to today's news three years ago? It would look really good. It'd be like, "Hey, buy Apple stock in like 1990." That'd be a great model. Very easy to build, but completely useless because it has lookahead bias. It's cheating. It knows what happened. The exact same problem happens when you let an AI search the internet. If you say, "Hey, AI, go predict whether or not this company is going to get acquired in June 2024," and it searches the web today, it's going to find an article that says, "Hey, they got acquired in June 2024." It's going to say, "I'm 100% confident they got acquired." And you're going to be like, "Wow, my model is amazing." But it's not. It's completely broken. It's cheating. So, this is like where snapshot comes in. It lets you say, "I want to search the web as it existed on this specific date in the past." So, if you want to know what was known on June 1st, 2024, you can run that exact search with Exa Snapshot and you will only see what was indexed up until that date. You won't see the future. You won't see the news that happened after. You won't see the earnings call that happened the next day. You will only see what was actually available to a human or an AI sitting at a computer on that day. And that allows you to do true backtesting. It allows you to build agentic features—features that rely on the live web—and test them historically without lookahead bias. Um, what's what's helpful with with snapshot and and kind of version version control search, you can constrain like what particular information is exposed at which time. So, here in this little example, I might set the snapshot date to like just before the outcome was announced. So, I know that the only thing that's going to be informing this system is uh, information that um, doesn't actually leak the exact confirmation of that thing, right? And then you could tune it to do different things. Like, maybe I have a feature that I really care about hiring. I want to make sure I find the right hiring signals. Maybe I have a feature that cares about like analyzing earning calls or or transcripts or or podcast interviews with the CEO. Whatever it is that's important to you, um, you're able to kind of tune that system and see, "Hey, would that have actually improved my prediction or would it not have improved my prediction?" And you can do that with confidence because you know you're not cheating. You're not leaking the future into the past.

</details>

---

### 特征工程演进：从结构化微调到端到端智能体回测

在保障了时间因果隔离的基础上，开发团队可以围绕智能体特征工程展开多维度的系统架构设计。当前企业在将互联网知识整合进预测流水线时，呈现出阶梯式的技术谱系。处于谱系一端的是经典机器学习与确定性数据管道，工程师将网页快照严格视作只读的特征生成器：例如设计“针对特定高管离职事件提取历史报道”、“研判过往三季度电话会议情绪基调”等结构化 Prompt，由大语言模型执行信息抽取并映射为离散或连续变量，再输入至下游经过验证的逻辑回归或树模型分类器中。通过逐个回测这些**智能体特征**（Agentic Features: 利用大语言模型结合受控网络检索动态合成的衍生特征），团队能够明确量化出每一个搜索驱动的特征究竟为模型带来了真实的增益（Alpha），还是引入了无益的噪声。

而在技术谱系的另一端，则是未来趋势所向的**全自主端到端智能体**（Fully Autonomous End-to-End Agent: 具备独立环境规划能力，可在运行期自主决策调用内部数据库或外网工具的系统）。在此架构下，系统在运行时自主决断何时发起搜索、如何组合内部专有知识与外部事实，并直接给出最终决策建议。然而，无论是结构化特征的微调拼接，还是全自主智能体的黑盒演进，其核心逻辑的闭环都必须建立在坚实的度量框架之上。工程师必须告别单纯依赖直觉与主观愿望的“玄学评估”（Vibes and Hope），通过严谨的真阳性（True Positive）与真阴性（True Negative）回溯测试集，以严苛的量化指标证实系统在过往历史切片中确实创造了超越基线的预测价值。

<details>
<summary>Original English Source</summary>

And so if you think about like the spectrum of how people build these models, um on the far left hand side you have like traditional quantitative models. They're using numbers. They're using tabular data. They're using price feeds. Maybe they have some sentiment scores that they bought from a vendor. But they're not really using the raw web because it's too unstructured and it's too hard to backtest. With Exa Snapshot, they can start turning unstructured web data into structured features that they can feed into their existing models. Then as you move along the spectrum, you might have hybrid models where you have an LLM that extracts features from the web, and then feeds those features into a traditional ML classifier or a ranking model. So you might say, "Hey, go search the web for any news about this company expanding into a new region." The LLM reads the articles that Exa returns from the past, extracts a binary yes/no or a sentiment score or a structured summary, and then that becomes a column in your dataframe. And then you can train your model just like you always have, but with these new, rich, agentic features that were previously impossible to generate without massive manual effort or cheating. Um then like uh on the far would be right hand side, the idea is like there's this like future where there's some like predictions, startups, and other folks operating where potentially like the full system is agentic. Um so the system itself may or may not choose to search the web through some tool call. Um it could be uh combining internal knowledge. It could be combining like structured external knowledge. And it can kind of do that at run time. And in all of these paradigms, whether you are building a simple tabular feature with an LLM or building a completely autonomous trading agent, you need to know if the agent is actually making good decisions based on the information it had at the time. You cannot evaluate an agent if you're giving it the answer key. And that's what querying the live web is—it's giving the agent the answer key to the past. So by freezing the web at specific snapshot timestamps, you can run your agent over hundreds of historical scenarios and measure its real-world accuracy, its precision, its recall, and prove that it adds value, not just like vibes and hope that it adds value.

</details>

---

### 回测博弈与实战警示：过拟合规避与保留集的决定性价值

为了让参会工程师切身体验时间受控回测的实操挑战，Ryan 现场组织了一场高度互动的竞技工作坊。比赛要求参与者针对一组涵盖真实历史收购结局的企业数据集，自主设计自然语言特征 Prompt，利用 Exa Snapshot 在冻结的历史网络环境中对目标企业是否被收购进行判定，系统依据判决结果计算得分。在竞赛机制中，成功预测一次收购得一分，发生误判倒扣一分，而放弃或弃权则计零分。现场大屏幕实时滚动呈现积分榜变动，部分选手通过精巧的搜索特征工程——例如锁定特定财务预警信号或兼并洽购传闻——迅速获得了显著积分优势，生动证明了纯净历史语料驱动的智能体对于隐性信息的敏锐捕捉能力。

然而，实时排行榜的博弈也戏剧性地暴露了模型评估中最典型的系统脆弱性——**过拟合**（Overfitting: 模型过度适应特定训练样本的表象规律而失去泛化能力的现象）。排行榜位列第一的选手并未挖掘深层商业逻辑，而是提交了一条极度投机的特征：“该企业是否是 Qiagen、Vitris、Bank of Cryptos 或 American Electric Power 之外的公司？”该选手敏锐地觉察到了测试集并未配置严格的保留集，因此直接在 Prompt 中针对已知正负样本名称进行硬编码过滤，从而以虚假的 100% 准确率斩获榜首。这一实战案例生动地印证了机器学习基石原则：在构建基于智能体的特征工程与回测评估时，必须强制推行**保留数据集**（Holdout Set: 严格隔离且对模型提示词不可见的独立验证数据），否则即便是最先进的 AI 智能体，也会在缺乏约束的优化过程中演化出规则欺骗行为。

<details>
<summary>Original English Source</summary>

Um what we're going to do now is like the fun part of this workshop, which is we're going to give you all time to kind of go hands-on with this tool. So, there's a little QR code on the screen, you can scan it with a mobile. You can also just like enter this [clears throat] little URL into your computer and the goal here is to design a feature. You're going to design an agentic feature that predicts whether a company got acquired, but using only information before a certain date. So, you'll see this interface in front of you. You have a bunch of um it'll ask you to put in a new feature. You can pick one of the examples or type whatever you want and hit run. Um and what it'll do is it'll go out, it'll use excess snapshot and search a bunch of them. This one was fast because it was cached, so uh that's a performance improvement to show you that we did caching, but it will go out and actually execute searches against historical snapshots. And the scoring rules: you get plus one if you correctly predict an acquisition. You get minus one if you say that it got acquired, uh but it didn't. And then, no impact for misses or passes cuz we're very friendly. Best score automatically captured, you can try as many as you want. I'm going to set us up for let's say like 30 minutes. Um so uh we'll kick that off now. [pause/music/interactive activity] All right, let's look at the leaderboard. Don't be shy. Brilliant goods and mystery boxes await you. Hey, congratulations. Congratulations, John. Very valuable land. Let's look at what people did. Let's just like poke around and be nosy and see like what did our number one person did. So, Zane: "Is this company a publicly listed company?" Very interesting feature. Number two, "Is this company a company other than Qiagen, Vitris, Bank of Cryptos, and American Electric Power?" Congratulations. You are the reason why I wanted to have a holdout >> [laughter] >> I removed it because I wanted it to be simple, but you proved exactly why in ML and quantitative research you always, always must have a holdout set! Because otherwise people—or LLM optimizers—will just memorize the labels and overfit to the test set! You literally wrote a prompt that says "is it this company or not" and hardcoded the winners! That's hilarious, and it's also the best possible demonstration of why rigorous evaluation methodology matters. So, wrapping up, three main highlights. Number one, we love Exa. Why? Because it's great agentic web search. It's good value. It's very cost-effective. It's at whatever latency I need. I want it in my model. Number two, snapshot. It lets me backtest my model. It lets me see just how good Exa is at improving your model. And number three, um consider really adding the holdout set to your competition because otherwise you may overfit. Thank you, everyone.

</details>