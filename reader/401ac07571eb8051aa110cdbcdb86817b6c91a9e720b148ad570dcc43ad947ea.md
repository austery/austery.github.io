---
author: AI Engineer
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4VmugsE-iP0
speaker: AI Engineer
tags:
  - ai-agent
  - agent-evaluation
  - price-monitoring
  - browser-use
  - prompt-engineering
title: Brainbase 如何将 Domino's 竞品比价 Agent 准确率从 41% 提升至 97%
summary: Brainbase 的 Milind 分享了为 Domino's CMO 办公室构建后勤比价 Agent 的六步迭代框架（Kickoff、Anthology、Benchmarks、First Agent、Iterating、Handing Off），通过规则细化与评测驱动，将准确率从 41% 提升至 97%，单源成本从 2 美元降至 1 美元。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Milind
companies_orgs:
  - Brainbase
  - Domino's
products_models: []
media_books: []
status: evergreen
---
### 项目背景与 Domino's 竞品比价需求

大家好，我是 Brainbase 的技术人员 Milind。我们帮助企业大规模部署并管理内部 Agent。今天我将分享如何对后勤业务 Agent 进行“爬山法”持续迭代优化，以及我们是如何与客户成功实现这一过程的。

<details>
<summary>Original English</summary>
[music]

>> Hey, so I'm Milind, MTS at Brainbase. We help enterprises deploy internal agents at scale and manage them. Today I'm going to be talking about hill climbing back office agents and how we did that successfully with a customer.
</details>

我们贯穿始终要讨论的客户，就像我们反复展示的著名本地视频那样，是 Domino's。众所周知，他们拥有 2 万多家门店，覆盖 90 多个市场。我们最初是从他们 CMO 办公室管辖的一个区域开始合作的。

<details>
<summary>Original English</summary>
So yeah, our customer in this case I'm going going to be talking about throughout and like the famous local video we use repeatedly is is is Domino's. As you all know, they have 20 plus thousand stores, 90 plus markets. We started off with a single region with their CMO office.
</details>

我们想要解答他们一直提出的一个问题：街角竞争对手的披萨到底卖多少钱？在他们的外送 App 上卖多少钱？在他们的官方网站上加上优惠券、不加优惠券又是多少钱？诸如此类。他们本质上希望最后拿到一张电子表格，里面列出各类不同单品的最低可能价格。

<details>
<summary>Original English</summary>
We wanted to answer this question that they kept asking. What does a pizza cost at the competitor down the street? What what does it cost in their delivery app? What does it cost on their actual website with promos, without promos, things like that. They essentially wanted a spreadsheet at the end with the lowest price possible for a bunch of different items.
</details>

### 人工流程痛点与 Agent 迭代成效

在我们为他们构建 Agent 之前，他们有一名分析师手动执行这些步骤。孤立来看，每一步似乎都很简单：打开竞对网站，选好对应的门店，对比外卖送餐和自提的价格，找到适用的优惠活动，计算出最便宜的价格，然后把它们全部填入表格中。这看起来都足够简单，但只要做错其中一步，最终得到的单元格虽然看似填好了，结果却是错的。我们需要构建一个执行相同流程的 Agent：读取一系列单品，找到对应网站，解析价格，填写电子表格，移交给人工或上层流程，并标记出任何不确定的项目。

<details>
<summary>Original English</summary>
Before we built the agent for them, they had an analyst manually doing these steps. They all look easy in isolation. You open a competitor's website, pick the right store, compare prices with delivery, takeaway, find the right promos, find the cheapest price and write it all down into a spreadsheet. It it all looks easy enough, but if you get one of these steps wrong, you look like you you you get a cell at the end that looks finished, but it's just wrong. We had to build an agent that does the same. Reads a bunch of items, finds the website, interprets prices, fills the spreadsheets, hands it off to an agent, and flags anything that it thinks it's not sure of.
</details>

当我们为他们创建该 Agent 的第 1 版时，准确率只有 41%。而到了最后的第 11 版，准确率达到了 97%。我们每个数据源的成本——每个数据源是指每个单品、每个竞对、每个网站——从每个来源 2 美元降到了 1 美元。单次运行所需的时长也从 129 分钟降到了 71 分钟。而这一切仅仅是通过调整指令（instructions）、技能（skills）和操作手册（playbooks）实现的。

<details>
<summary>Original English</summary>
When we created version one of this agent for them, we had 41% accuracy. By the end at version 11, we had 97% accuracy. Our cost per source per source means per item per per competitor per website went from $2 per source to $1 per source. And the amount of minutes it took per run went from 129 to 71. All of this went just with just just instructions and and skills and playbooks changing.
</details>

### Agent 交付六步法框架

以下是我们不仅在 Domino's、也在其他客户身上使用的六个步骤：首先是启动（Kickoff），随后是术语词表（Anthology）、基准评测（Benchmarks）、构建首个 Agent（First agent）、持续迭代（Iterating）以及最终交付（Handing off）。我将详细讲解这些步骤的含义以及我们在 Domino's 案例中具体做的工作，希望这是一个大家在内部也能复用的框架。

<details>
<summary>Original English</summary>
Here is like the six steps that we use, not just with Domino's, but with other customers as well. We start off with kickoff, followed by anthology, benchmarks, first agent, iterating, and handing off. I'll talk about what these steps mean in detail and what we did for Domino's in each of these and hopefully it's a repeatable framework that y'all can use internally as well.
</details>

### 第一步：启动（Kickoff）

第一步是**启动（Kickoff）**。理想情况下，你应该与客户或最终用户沟通，并在“怎样才算成功”上达成共识：当前的工作流程是怎样的？人工最终核准并签字确认的是什么？需要花费多长时间？成本是多少？你的 Agent 需要达到多高的准确率？由谁来评判输出结果？Agent 绝不能独自做什么？绝不能做出哪些假设？

<details>
<summary>Original English</summary>
So, step one is kickoff. You should ideally talk to your customer or end user and agree on what the win looks like. As of today, what what is the job? What did the human sign off on at the end of it? How long does it take? How much does it cost? How accurate does your agent need to be? Who judges the output? And what must the agent never do alone? What assumptions should it never make?
</details>

对于 Domino's，我们最终制定了这份非常奏效的需求简报。我们的最终目标必须是一种更快、可重复的方法来收集本地竞对价格，同时不丢失边缘用例所需要的判断力。因此，我们向他们询问了所有这些问题：目前，分析师制作电子表格，定价团队最终对其进行分析；一名分析师每天要花 2 个小时主动手动制作该表格；随后每个单元格都会被检查和确认；而最终的 Agent 只需提请分析师核准，并标记出它需要人工确认的任何事项。我们在量化指标上的胜利标准是：达到最高准确率、尽可能降低每个来源的数据成本、运行时间尽可能短；而在我们开始之前，他们甚至不确定我们是否真的能完成这种折扣搜索。

<details>
<summary>Original English</summary>
For Domino's, we ended up creating this brief that worked really well for us. Our outcome at the end had to be a faster, repeatable way to collect local competitor pricing without losing the judgment edge cases need. So, we asked them uh all of these questions. As of today, the analysts create a spreadsheet and the pricing team uh find finally analyzes it. An analyst spent 2 hours daily manually actively working on creating the spreadsheet. Every cell was then checked and and just confirmed and the agent at the end just had to ask for the analyst for sign off and flag anything else it had to. Our win in numbers looked like just having the highest accuracy, the lowest cost of sources possible, run time to be as low as possible, and before we even started, they weren't even sure if we can do this discount search at all.
</details>

>> [发出嗤笑声]

<details>
<summary>Original English</summary>
>> [snorts]
</details>

### 第二步：术语词表与规则库（Anthology）

第二步是**术语词表（Anthology）**。这到底是什么意思？我们尝试写下 Agent 需要知道的所有术语，以确保它绝不做出无端假设。这意味着我们需要精确告诉 Agent：它应该收集什么、每个答案来自哪里、输出到哪里、各个术语对于实际手动执行工作的分析师意味着什么，以及当 Agent 无法解决某个问题时应该怎么做。如果这里有一条核心经验，那就是：理想情况下每个术语都应该有定义。如果你不写下来，Agent 就会去猜测，很可能会弄错。

<details>
<summary>Original English</summary>
>> Step two is anthology. What does that exactly mean? We we try to write down all the terms that that the agent needs to know to never make assumptions, which means we need to tell the agent exactly what it's supposed to collect, where each answer comes from, where does it go, what does each term mean to the analysts that actually do the do the work manually, and what should the agent do when it can't figure something out. If if there's one jewel here, it is that every term should ideally have a definition. If you don't write something down, the agent's going to guess and probably get something wrong.
</details>

在 Domino's 案例中，具体做法如下：我们在 Brainbase 拥有自己的内存原语，其内存类似于一个 Postgres 数据库，Agent 可以对其进行任意操作。我们为它提供了一个目标表，其中列出了所有单品。以编号为 14 的 ID 为例：ID 14 是品牌 B 的大号披萨，取餐方式是送餐，平台是在 App B 上。Agent 理论上通过浏览器操作（browser use）在网站上查找价格，发现价格标有 24 和 19；24 是划线价，19 是促销价。我们现在还有一个规则文件，明确指示 Agent 专门记录用户在结账时实际支付的价格，而不是 24。这一规则正来自于一次真实的失败案例。最终保存时，我们创建了一个名为 `price_observations` 的表，对应 ID 存储它看到的价格、全价以及具体来源。最后，我们给它一张包含所有占位单品 ID 的电子表格，它只需查询 ID 并替换价格即可。当单元格出现错误时，它会指出确切的页面以及它为何选择该价格背后的规则。

<details>
<summary>Original English</summary>
For Domino's, here's what it looked like. We at Brainbase have a memory primitive of our own that has memory that looks like a Postgres database that the agent can do whatever it wants with. We gave it a target stable where we gave it up all the items. In this case, let's look at ID number 14. ID 14 is brand B. It's a large pizza. Uh takeaway method is Sorry, it's delivery and on app B. The agent hypothetically does browser use, finds the price on the website, finds that it's 24 and 19. 24 is the striked out price, 19 is the sale price. We also now have a rules file where we actually tell the agent to specifically mark down the price that it that a user pays at checkout, not 24. This came from like a valid failure. What it saves at the end, we created a table again called price observations where it with the corresponding ID stores what price it saw, what the full price was, and the actual source. And at the end, we give it a spreadsheet that has all placeholder item IDs, and all it has to do is look up the ID and replace the price. When a cell is wrong, it points to the exact page and the rule behind why it chose the selected price.
</details>

我们提及的其他来自实际运行轨迹的规则包括：大号披萨的定义（可以是单品本身，也可以是套餐）；外卖送餐不等于到店自提（它之前对此产生过混淆）；它需要进行促销计算（如果是打七折，必须先算好折后价再录入电子表格）；如果无法核实，就将其记录为空缺，绝不要凭空猜测。

<details>
<summary>Original English</summary>
Other rules that we mentioned that came through actual life traces were definition of what a large pizza looks like. It's anything that's actually the item itself or a bundle. Delivery is not equal to takeaway. It It got confused with that. It's supposed to do promotion math. If it's 30% off the price, it should do that before entering it in the spreadsheet. And if it can't verify it, write it down as a gap and do not guess.
</details>

### 第三步：基准与评测体系（Benchmarks & Evals）

第三步是确定**基准（Benchmarks）与评测（Evals）**。这些步骤在顺序上可以稍作互换，但本质上你是在弄清楚哪些可以用离线评测运行，哪些可以用在线评测运行。对于离线评测，理想的做法是一开始就询问客户是否保存了已有确切答案的历史用例。在本次案例中，Domino's 的分析师保留了他们曾处理过的历史表格。我们能否重新运行那些输入用例，从而得到完全相同的最终输出？接下来，你该如何为 Agent 执行的每一项操作打分？对于评测，你需要明确：哪些可以通过代码确定性地检查，哪些可以通过 LLM 作为裁判（LLM as a judge）检查，哪些可以通过 Agent 作为裁判（Agent as a judge）检查。我们认为后者是一个更独特的概念：如果存在输出产物，你可能需要一个 Agent 通过多轮对话、多次工具调用来判断该产物的正确性。最后，当出现异常或标记时会发生什么？你应该尽量用这三类手段对尽可能多的环节进行评分。

<details>
<summary>Original English</summary>
Step three is finding out benchmarks and emails. Now Now, these steps can be interchangeable slightly, but essentially you're trying to figure out what you can run offline emails on and what you can run online emails on. For offline emails, you should ideally start off by asking them if they have past cases that they already have answers for. In this case, we had analysts from Domino's who had spreadsheets that they had worked on. Can we actually rerun those um input cases to get the same final output? And then at the end, how do you figure out how to score each thing that the agent is doing? For evals, you try to figure out what you can check deterministically, what you can check why an LM as a judge, and what you can check as an agent as a judge. That's a concept that we think is slightly more unique, where if there's an output artifact, you probably want an agent to take multiple turns, multiple tool calls to figure out how correct that that artifact is. And at the end, what happens when something goes wrong, and what happens when it's flagged? You should try to score as many things as you can with these three things.
</details>

在 Domino's，我们的基准最初就是基于他们已有的所有历史电子表格构建的。我们曾尝试通过 archive.org 抓取竞对网站在特定日期的快照来重建输入环境，但发现这在外送 App 上行不通，因为 App 的数据提供方式不同。因此，从 Agent 第 1 版开始，我们就把 Agent 执行的所有浏览器操作截图保存下来，以此构建了内部基准的运行环境。在评测方面，我们编写代码来执行确定性检查：例如检查每个 ID 单元格是否都被替换成了价格、折扣数学计算是否正确、当前价格与上一轮运行相比波动是否在正负 20% 以内，以及是否进行了标记。LLM 裁判则负责检查轨迹，核实是否选对了单品、是否应用了正确的促销活动。Agent 裁判会深入到每一个被标记的价格中，切实核实该标记是否有效。而分析师最终会查看被标记的结果；一旦出现问题，尝试找出背后的原因。

<details>
<summary>Original English</summary>
So, yeah, at Domino's, our benchmark essentially started off with all the spreadsheets that they had. We tried to create the input environment by going to archive.org and having snapshots of competitor websites at those given dates. What we saw that it was that it didn't work with delivery apps because they didn't serve data the same way. So, we ended up storing browser screenshots for everything the agent was doing starting from version one of the agent, and that's how we create up our environment for for the internal benchmark. For evals, we use code for things like checking if every ID cell was replaced with the price, if the discount map was computed correctly, if the price was 20% plus or minus compared to the previous run, was it flagged or not. LM as a judge just checks the trace to see if the right item was selected, and if the right promo was applied. Agent as a judge actually goes to every flagged price and actually confirms if the flag was valid or not. And the analyst at the end will go look at the final flags and try to figure out what the reason for it was if something went wrong.
</details>

### 第四步：交付首个轻量 Agent（First Agent）

第四步是真正发布某种版本的**首个 Agent（First agent）**。在你的技术栈中，理想情况下应该先交付一个范围窄小、且从第一天起就能进行评分的初代 Agent。你应该理清值得评分的最小切片是什么，弄清指标应该达到怎样的准确率，并通过这个 Agent 摸清一次运行需要多长时间、成本是多少、会在哪些地方出错等等。第 1 版的任务是接受度量，而不是做到尽善尽美。当你拿到了想要达到的基线基准分数后，再去扩大范围。

<details>
<summary>Original English</summary>
Step four is actually shipping some version of a first agent. You should ideally ship a narrow first agent in your stack that you can score from from day one. You should probably figure out what the smallest slice worth scoring is. You should figure out how accurate things should be, how long and and you should use this agent to figure out how long does it run take, what what does it cost, what does it get wrong, and things like that. Version one's job is to be measured, it's not to be good. You should widen the scope uh widen the scope after you get some baseline score they're trying to meet.
</details>

对于 Domino's，正如我之前提到的，第 1 版的准确率只有 41%，单次运行耗时超过 2 小时，每个数据源成本为 2 美元，表现确实不佳。我们发现了一系列可改动之处，进行了修复，随后改善并扩大了范围：最开始仅针对一个城市中的一款 App、一个单品；之后扩展到汉堡和自提选项；再之后增加了另一款 App，最终接入了其他网站。因此，以小而狭窄的范围起步，非常有效地帮助我们理清了修复方案。

<details>
<summary>Original English</summary>
For Domino's, as like I mentioned earlier, version one for us was just 41% correct. It took more than 2 hours. It was $2 per source. And and it just wasn't working well. We found a bunch of changes, made fixes, and then improved and increased the scope. So, we started off with just one app, one item in one city. Moved on to adding burgers and takeaway options. Moved on to adding another app, and finally other websites as well. So, starting off small narrow scope worked out really well for us to figure out how we can fix things.
</details>

### 第五步：持续迭代与两个典型优化案例（Iterating）

第五步就是**持续迭代（Iterate）**：评分、修复、发布。在这个阶段，你需要反复执行第二步、第三步和第四步。不断迭代，优化你的术语词表、评测和基准，直到产出有效的结果。你应该弄清楚哪些失败代价最高昂、发生最频繁，并去修复它们；明确应该采用哪些改动来解决这些失败；如果改动导致运行时间或成本增加，你是否能够接受这种增加？以及如何利用这些失败案例来创建并扩充你的基准用例或评测标准？理想情况下，一次只改动一件事，并在彻底更换模型之前，优先通过修改指令来解决问题。

<details>
<summary>Original English</summary>
Step five is to just iterate. You should score, fix, and ship. Here is where you'll do steps two, three, and four. Keep iterating, improving your anthology, improving your emails, your benchmarks to get things that work. You should figure out which failures are most expensive, most frequent, fix them, what changes should be used to fix them. If that change results in increased run time or cost, if yes, are you okay with that increased run time and cost? And how can you use those failures to create and add to your benchmark cases or eval criteria? Ideally, change one thing at a time and fix the instructions before you want to change the model entirely.
</details>

在 Domino's 的实践中，我们重点强调两个例子。在展开之前，这里有一张展示我们演进历程的图表：第 1 版起步准确率为 41%，每个数据源成本超过 2 美元；经过多次改动后的第 11 版，成本降至每个数据源 1 美元，准确率达到 97%。

<details>
<summary>Original English</summary>
At Domino's, we highlighted two examples. Before I get to that, here is a graph of how our progression went. We one started off at 41%. Um more than $2 a source. We 11 after a bunch of changes, it's $1 a source, and and 97% accurate.
</details>

这里有一个我们所做非常简单的规则改动示例：我们给 Agent 提供了一个链接，让它在品牌 B 自己的官网上寻找大号披萨的外送价格。它跳转到该链接，页面上相应区域已经被高亮标注；它点击该区域，找到了大号披萨及其价格，随后便停止了。然而分析师在最终人工复核时发现，同一页面的下方其实有一个仅需 21 美元的优惠交易，而 Agent 错过了。所以，我们在这里所要做的仅仅是增加一条简单的规则：不要停留在链接直接定位的高亮区域，而是要查看整个页面。这样一个小改动就帮助我们捕获了此类优惠，并确保不会重蹈覆辙。

<details>
<summary>Original English</summary>
So, yeah. Here's an example of a very simple rule change that we made. We gave the agent a link of of a large pizza to find for brand B. Via delivery on its own website. It went to the link which had the section already highlighted. It clicked on it, found the large pizza, found the price, and ended there. The analyst got that somebody manually caught at the end that there was actually a deal below that website below on the same page, that was just $21 instead, and and it missed that, right? So, all we had to do there was add a simple rule to not stop at the section that it gets linked to, but actually look at the entire page. And a simple change like that helped us just like catch this and then make sure it doesn't happen again.
</details>

我们必须进行的另一项更复杂的改动，涉及到该 Agent 的具体浏览器使用行为（browser use）。在其中一次运行中，我们观察到在品牌 D 的促销页面上，所有的促销价格都嵌在图片内部，并没有作为纯文本呈现。Agent 的做法是逐一查看了全部 26 张促销图片来寻找目标单品；它通过放大 4 倍、5 倍、6 倍重新查看这些图片；在第 13 分钟时它其实已经找到了正确的卡片，但仍不断放大来反复核实，陷入了死循环，我们不得不在第 15 分钟时手动将其终止。在人工查看运行轨迹和网站之后，我们意识到 HTML DOM 实际上极为重要，本可以为 Agent 省去大量工作。因此，我们在最新的规则中指示 Agent：优先查看 HTML DOM，在调取实际图片之前先检查图片的 title、alt 等文本属性，并在达到特定缩放级别后强制停止。

<details>
<summary>Original English</summary>
Another more intricate change that we had to make was actually browser use behavior of set agent. So, in one of the runs, we saw that for brand D this is a this is a brand called brand D promotions page, where all the promotion prices were inside images, so not actually captured in text. What the agent did is it looked at all 26 promo images to find the item it was looking for. It looked them looked at them again by zooming in 4x, 5x, 6x. It found the right card at minute 13, but it still kept zooming to double-check and verify, and it it was just in a loop, and we had to manually stop it at minute 15. We realized after manually looking at the trace and the website, that the HTML DOM is actually super important and could have saved the agent a lot of work here. So, we we tell the agent in in our latest rules to go look at the HTML DOM first, look at things like image titles, all text before looking at the actual image rates, and just stopping past a certain zoom level.
</details>

这一优化的成果是：图片读取次数减少了三分之二，成本降低了 50% 以上，并让我们顺利拿到了实际答案和完整的报告。因此，尽管我们拥有自动化检查和评测标准来帮助捕获许多问题，但有些情况依然需要工程师亲自查看轨迹和浏览器工具调用，切实找出问题根源。

<details>
<summary>Original English</summary>
What that resulted in is is 1/3 the number of image rates, reducing cost by over 50%, and just us getting an actual answer and a finished report. So, while we have automated checks and eval criteria to help us catch a lot of things, some things require our engineers to actually look at traces and and browser on use tool calls and and just see what went wrong.
</details>

### 第六步：闭环交付与规模化扩展（Handing Off）

通过进行大量这类的调整，我们迭代到了 V11 版本，实现了 97% 的准确率。接下来要考虑的就是：下一步该做什么？我们的思路是探索在最后如何最好地交付给客户。我们需要确定：谁来运行这些 Agent？谁来审核输出？谁来负责将纠错反馈转化为规则和基准测试用例？谁来决定新版本何时可以发布上线？所有这些问题，都是应该在前期记录下来的。你所要交付的是一整个完整的闭环，而不仅仅是 Agent 本身。理想情况下，如果改动足够轻微，用户应该被赋予自主调整的能力。

<details>
<summary>Original English</summary>
So, yeah, we made a bunch of these changes, got to V11, got to 97% accuracy, and now it's just figuring out, hey, like like what next? So, so our our way of this is trying to figure out how best to hand off to the customer at the end. We want to figure out who's running these agents, who's reviewing the outputs, who's trying to correct who's trying to take the corrections into and converting into rules and benchmark cases, and who decides when new version is ready to ship. All these questions are things you should probably have written down. Um you're trying to hand off an entire loop and not just the agent. Ideally the the user should be empowered enough to make these changes if they're small enough themselves.
</details>

在 Domino's 的项目中，我们正是这样落地的。该 Agent 现在按照他们的既定计划自动运行——既支持每日定时多次运行，也支持通过邮件手动触发。此时，分析师只需审核出现异常的情况；他们捕获的每一次纠错，都能自动添加为基准测试用例；如果他们处理不了，我们也会随时提供支持。目前，我们正处于与他们进一步扩大合作的阶段，致力于将该方案推广到更多市场和其他业务领域。

<details>
<summary>Original English</summary>
So for for for Domino's, that's exactly what we did. The agent now runs on their schedule either multi um daily or even by email trigger manually. Analysts review only the exceptions at this point. Each correction that they catch, they're automatically able to add as a benchmark case. If they can't, then they obviously they're always available for them. And we are now at a place where we are expanding with them. Um trying to get it into multiple markets and multiple other um areas.
</details>

这就是我们如何运用自己的框架与 Domino's 合作，将一个几乎无法正常工作的 Agent 打造成近乎完美运行且成本大幅降低的系统的完整过程。我们发现，该框架对于各种其他业务场景也同样非常有效，尤其适用于面对混乱的数据源且需要找出准确答案的场景。谢谢大家。

<details>
<summary>Original English</summary>
So yeah, this is basically how we we used um our framework to work with Domino's to go from an agent that barely works to an agent that works almost perfectly while reducing the cost. We found this framework to be very effective for various other use cases, especially where you have messy sources of data where you're trying to figure out the right answer. And um thanks.
</details>