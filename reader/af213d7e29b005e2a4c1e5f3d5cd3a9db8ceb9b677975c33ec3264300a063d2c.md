---
author: TechButMakeItReal
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=NxB45uB_bmE
speaker: TechButMakeItReal
tags:
  - artificial-intelligence
  - economics
  - tokenomics
  - financial-modeling
  - cloud-infrastructure
title: 1%客户支撑的AI泡沫：Token贬值与万亿美元债务账单
summary: 视频探讨AI行业买方市场与财务模型。当前Token单位价格迅速走低，80%的OpenAI与Anthropic利润仅依赖1%的头部客户，而企业中位数员工月度AI支出仅16美元且缺乏模型忠诚度。面对数据中心到2032年需达9.6万亿美元收入方能打平的债务压力，行业正处于剧烈动荡期。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - Nvidia
  - Google
  - MacPaw
  - Ramp
  - McKinsey
  - Gartner
products_models:
  - GPT-4
  - Grok
  - Opus
  - Qwen
media_books:
  - Brookings Papers on Economic Activity
status: evergreen
---
### 依赖1%客户的AI繁荣

OpenAI 和 Anthropic 赚到的钱中，有 **80%** 来自 **1%** 的客户。

1%。我们正在经历美国历史上规模最大的基础设施建设之一，却指望着这 1% 的客户——而他们明天就可能转向更便宜的模型，很可能是中国模型。我们之前制作了两期关于 AI 行业经济学的热门视频，探讨了在同一批参与者之间来回流动的循环经济，以及养老基金和人寿保险如何参与数据中心的开发。今天我们要讲的是这个故事的下半部分：买方市场，也就是我们这些为 AI 买单的人。看完本期视频，你将学会如何看懂当今 AI 市场的真实状态，看清它的本来面目。为此，我将向你展示如何追踪资金、Token、买家以及债务。

让我们深入探讨。

<details>
<summary>Original English</summary>
80% of money that OpenAI and Anthropic make comes from 1% of customers.

1%. We've got one of the biggest build-outs in American history [music] counting on 1% of customers who may switch to a cheaper model, probably Chinese, tomorrow. We made two viral videos about the economics of the AI industry, the circular economy that moves money back and forth between the same players, and how pension funds and life insurance participate in development of data centers. Today is the second half of that story, the market of buyers, those of us who pay for AI. By the end of the video, you will understand how to read the state of the AI market today and see it for what it is. To do that, I'll show you how to follow the money, the tokens, the buyers, and the debts.

Let's dive in.
</details>

### Token定价与任务完成成本

大家都在讨论 Token 是如何变得越来越便宜的。为什么这是件大事？首先，根本不存在所谓的“通用 Token 价格”。Token 不是像一桶原油那样的标准化大宗商品。一个 Token 的成本取决于具体模型。现在，打开任何一款付费 AI 应用并查看其定价页面。基础计划包含的 Token 数量：20,000、10,000、30,000。你能告诉我这大概是多少内容吗？说实话，我也说不上来。是的，我可以做一些非常基础的算术。一个 Token 大约相当于 4 到 5 个字母，所以一个相对较短的单词大约就是一个 Token。但这又如何呢？有时候你会得到那种冗长至极的回答，大语言模型拼命夸赞你有多聪明，并在这些毫无必要的句子上白白消耗 Token。而另一些时候，你只需一条提示词就能获得完美的输出。

此外，针对某项任务，也不存在一个放之四海而皆准的“正确 Token 消耗量”。如果你查看基准测试，Artificial Analysis 给每个模型提供了完全相同的任务：GPT-4 Astra 消耗了 6,000 万个 Token；Grok 4.7 消耗了 2.4 亿；Opus 5.5 消耗了 2.6 亿。

而且在运行提示词之前，你根本无法预测这一点。因此，你获得多少 Token 并不真正重要。真正重要的单一数字，是**成功运行并完成一项任务需要付出什么代价**。这包括所有失败的尝试、重新提示、必须新开的对话、Agent 步骤、工具调用、人工审查，所有这些结合在一起以达成一个目标。这才是关键所在。所以，完成一项任务需要花费多少 Token 你就得花多少，如果是一大堆，那也只能接受。但是，Token 的成本正在暴跌。

这就像是你雇了一个十几岁的年轻人帮你清理车道上的积雪，他说：“我按每小时 50 美元收费。”你看看车道心想：“好吧，我觉得这大概需要 15 分钟的活儿。所以行吧，我接受。”接着你会发现自己琢磨：“那我为什么不干脆自己动手呢？”所以，当作为整个行业度量尺度的单位——Token 的成本在下降时，同样的资金可以买到更多东西。从一方面看，这很棒。但是，那些投入到 AI 基础设施建设中的数万亿美元呢？那些债务、贷款和特殊目的实体（SPV）怎么办？如果成本正在崩盘，那么支撑整个 AI 行业的所有假设背后的财务建模将会发生什么？

所有对利润的预测，都是建立在部分依赖于 Token 价格的财务建模之上的，然而 Token 的成本却在不断下降。

这就引出了我的第一个观点。

<details>
<summary>Original English</summary>
Everyone talks about how tokens are becoming cheaper. Why is this a big deal? First of all, there is no such thing as a universal token price. Token is not a commodity like a barrel of oil. The cost of a token depends on the model. Now, open any paid AI app and look at the pricing page. Tokens included in the basic plan, 20,000, 10,000, 30,000. Can you tell me roughly how much that is? Well, I can't tell you either. Yeah, I can do pretty basic math. One token is about 45 letters, so a fairly short word is about one token. But so what? [music] Sometimes you get one of those long-ass answers when the LLM is praising you for how brilliant you are and burning tokens on those unnecessary sentences. And another time you get a perfect output in one prompt.

Also, there is no such thing as a universally correct number of tokens for a task. If you look at the benchmarks, artificial analysis gave every model identical tasks. And GPT-4 Astra used 60 million tokens. Grok 4.7 used 240. Opus 5.5, 260 [music].

And you can't predict this before you run a prompt. Therefore, how many tokens you get doesn't really matter. The single number that really matters is what it takes to run a successful task. Counting all the failed attempts, re-prompting, new chats that you have to spin up, agent steps, tools, review, all of that combined to achieve a goal. That's what matters. So, you're going to spend however many tokens it takes to complete a task, and if it's a ton, so be it. But, the cost of tokens is collapsing. It's almost like when you hire a teenager to shovel snow from your driveway, and the teenager says, "I'll do it for $50 an hour." You look at your driveway and go, "Okay, I think this is about 15 minutes of work. So, yeah, I'll take it." And you find yourself thinking, "Why didn't I just do it myself?" So, when the cost of the unit, of the token [music], that is the measuring stick of the whole industry, is going down, the same money buys more.

Well, on one hand, that's great. But, what about those trillions of dollars spent on the AI buildout? What about those debts and loans and special purpose vehicles? If the cost is collapsing, what's going to happen to the financial modeling behind the AI industry that all the assumptions were built upon?

All the predictions of profits were based on the financial modeling that was partially based on the price of tokens, but the cost of tokens is going down.

Which brings me to my first point.
</details>

### Token贬值与应用体验

**Token 的贬值。**

我已经大概 6 个月没有在任何应用里点击过菜单了，我很喜欢这种方式。在过去一年的某个时刻，我使用的每一个应用都长出了一个 AI 聊天框。我的电子邮件、Notion、数据分析，我在工作中所做的一切，我已经完全不再去点菜单了。我打开应用，寻找能直奔主题的最快途径。所以我直接告诉它该做什么：找到这个、把它链接到那个、发送给他们、明早回复。而且你知道更严重的是什么吗？懒惰会滋生懒惰。当我关闭这些应用看着我的个人 Mac 时，它就只是愣愣地回看着我。

我的电脑——也就是运行所有这些应用的载体——仍然让我手动处理每一件事。我不想因为记不清文件名而到处找文件。我也不想因为存储空间满了而到处找文件来删除。我的手机也是一样。

这就是为什么 MacPaw 开发了 An A。An A 是一款自主 AI 助手，它常驻在 Mac 和 iPhone 上，并且可以跨你的所有应用协同工作。它可以找到我上周看牙医的收据，重命名该文件，将其保存到我的云盘，并一次性提交给我的保险公司。它只触碰我授权它触碰的内容，因此在发出任何内容之前我仍然可以进行检查。An A 在搭载 M 系列芯片的 Mac 和 iPhone 上提供 14 天免费试用，附带 10,000 点 AI 积分。链接在简介中。最后但同样重要的一点是，它是由一个极具品味的团队打造的。它简洁、雅致、无比流畅，使用起来纯粹是一种愉悦。请 MacPaw 团队继续打造美妙的科技产品，这样我就可以永远偷懒下去了。

<details>
<summary>Original English</summary>
The devaluation of tokens.

I haven't clicked through any menu in any app in about 6 months, and I love it. Somewhere in the last year, every app I use grew an AI chat. My email, my notion, my analytics, everything I do at work, I've completely stopped clicking through menus. I open apps and I find the quickest possible way to get to the point. So, I just tell it what to do. Find this, link it to that, send it to them, respond in the morning. And you know what's even worse? Laziness breeds laziness. When I close the apps and look at my personal Mac, it just stares back at me.

My computer, the thing all those apps live on, still makes me do everything by hand. I don't want to be looking for a file cuz I don't remember what I named it. I don't want to look for files to delete cuz my storage is full. Same with my phone.

That is why MacPaw built an A. An A is an autonomous AI assistant that lives on the Mac and the iPhone [music] and works across all of your apps. It can find last week's receipt for my dental appointment, rename it, save [music] it to my drive, and submit it to my insurance company all in one go. It only touches what I give it permission to touch. So, I can still check before anything gets sent. An A is free for 14 days with 10,000 AI credits on M-series Macs and iPhone. The link is in the description. Last but not least, it was built by the team with exceptional taste. [music] It is simple, sleek, incredibly smooth, and a pure joy to use. [music] Please keep making beautiful tech, the MacPaw team, so I can be lazy forever.
</details>

### 消耗激增与收益走平

在过去的 2 个月里，Token 的使用量一直在上升，但为这些 Token 支付的价格却保持平稳。这一数据来自 **Ramp AI 指数**。该指数是根据使用 Ramp 的约 70,000 家公司的交易数据构建的。当然，我承认这并不代表整个科技行业，但它是涵盖各种规模公司的集合，因此是一个相当有代表性的信号。看看这些数字。

这是 8 月份 Token 的使用量，以及花费的金额。现在看这里，这是 9 月份，Token 的使用量显著增加。

但是为这些 Token 支付的金额却保持平稳。

这就是 **Token 通胀** 的含义。假设在 8 月份花 10 美元可以买到 1,000 个 Token，现在同样的 10 美元能买到 10,000 个 Token。然而模型正在变得越来越好。实验室投入了巨额资金来研发新模型，但这些支出并没有换来回报。你知道这像什么吗？就像你的手机套餐。10 年前，你的套餐只提供几 GB 的流量；现在花同样的价钱，你可以获得无限流量。运营商花费数百亿美元建设 5G，网络变得更快、更好、更可靠，而且更便宜了，但你开始支付更多费用了吗？

没有。

你的账单还是差不多。这就是我所说的贬值。这就是问题所在，因为整个 AI 行业的预期，都是建立在假定 Token 价格保持不变的财务模型之上的。但是一旦你亲眼看到这些数据，你就会开始注意到各家实验室对外表述方式中的一些端倪。Google 最近表示，他们从每月约 10 万亿个 Token，在 2 年内增加到了超过 3,000 万亿（3 千万亿）。相差了 330 倍。

但是请注意他们夸耀的是什么：是 **Token 的数量**，而不是每个 Token 产生的收入。因为当单位价格暴跌时，你唯一能夸耀的就是该单位的数量规模，因为这在舞台上展示时看起来很亮眼。这里还有另一件事。

是谁决定了 Token 的价格？

这个价格里包含了大量的利润空间。

你知道这是谁的利润率吗？

英伟达（Nvidia）的。

我是怎么知道这一点的？

DeepSeek 的竞争对手提供了 30% 到 40% 的折扣。如果他们能给出 40% 的折扣并且依然盈利，这就能让你大致估计出利润率是多少。Cloud Code 和 Codex 的转售商更是以大约 **90% 的折扣** 出售 Token。当你的产品可以按一折转售时，标价显然不再是制造它的成本。

总而言之，Token 的成本正在下降，利润率也在下降。从一方面看，这听起来是一笔划算的买卖，因为去年花 20 美元你只能搭一个落地页，现在花 20 美元你可以搞出一个功能完备的应用。是的，我有夸张的成分。但当你作为一家前沿实验室时，你必须去弥补不断缩减的利润率。那么该怎么做呢？你必须扩大规模，让更多的人、更多的企业来使用你的模型，这就引出了方程式的另一面：买方，也就是购买模型访问权限的人。我们谈论对 AI 的需求时，总觉得它是无穷无尽的。但事实真的如此吗？那些尚未购买模型的人群和企业，真的构成了一片蓝海吗？或者说，可能根本就没有剩下多少潜在客户可以去推销了。

<details>
<summary>Original English</summary>
In the last 2 months, the number of tokens used is going up, but the price paid for those tokens stays flat. This data comes from the Ramp AI index. This index is built from the transactions of about 70,000 companies using Ramp. Now, I will say it's not the entire tech industry, of course, but it is a collection of companies of various sizes, so it is a pretty representative signal. Look at these numbers.

This is how many tokens were used back in August, and this is how much money was spent. Now look here. This is September, and the number of tokens going up significantly.

But the price paid for those tokens remains flat.

This is what token inflation means. If you could buy 1,000 tokens hypothetically with $10 in August, now the same $10 buys you 10,000 tokens. But models are getting better. Labs are spending enormous amount of money on building new, but the spending is not paying off. You know what this looks like? Your phone plan. 10 years ago, your plan gave you a couple of gigs of data. Now for the same price, you get unlimited data. Carriers spent billions building 5G. The data got faster, better, more reliable, it's cheaper, but did you start paying more?

No.

Your bill is about the same. That's the devaluation I'm talking about. This is the problem because the entire projection for the AI industry was based on the financial modeling that was based on the assumption that the token price stays the same. But once you see this data with your own eyes, you start noticing something about the way labs talk. Google recently said that they went from about 10 trillion tokens a month to over 3 quadrillion in 2 years. 330 times difference.

But notice what it is that they're bragging about. The number of tokens, not revenue per token. Because when the price of the unit is collapsing, [music] the only thing you can brag about is the volume of that unit. Because it looks great on stage. [music] And here's another thing.

Who dictates the price of a token?

There is a lot of margin baked into this price.

You know whose margin?

Nvidia's.

How do you I know that?

Deep Seek's competitors offer discounts of 30 to 40%. If they can offer a discount of 40% and still make profit, that gives you an estimate of what the margin is. Cloud Code and Codex resellers sell tokens at discounts of about 90%. When your product can be resold at 90% off, the price on the label clearly isn't what it cost to make it.

So, to sum it up, the cost of tokens is going down. The margin is going down, which again, on one hand sounds like a great deal cuz for $20 last year, you could build a landing page. Now for $20, you can get a full-blown app. Yes, I am exaggerating. But when you're a frontier lab, you have to offset collapsing margin. So, how do you do that? You have to grow volume and get more people, more businesses to use your model, which brings me to the opposite side of the equation [music]. The buyer, the one who buys access to the model. We talk about the demand for AI as if it's endless. But, is it? Is there a really a blue ocean of all those people and businesses who have just haven't bought the model yet? Or perhaps, there is not that many people left to sell to.
</details>

### 需求端的三大危险信号

让我们回到 Ramp 的数据，并在这里做一下归一化处理。与其分开看消耗量和支出金额，不如来看看**单个 Token 能产生多少收入**。注意这个数值是如何下降的。现在，设想你是一位刚签署了 Claude 或其他任何主流大模型采购合同的首席财务官（CFO）。当你看到这些数据时，你会发现 Token 的成本在持续走低。很自然地，你会开始追问为什么。而一旦你开始追问，就会注意到一些警示信号。

**危险信号之一：同行现状。** 麦肯锡报告称，仅有 **37%** 的公司确认 AI 提升了自身利润，这一数字与去年完全持平。如果你是 CFO，这会立即告诉你：你正在为更好的模型买单，但利润线却完全纹丝不动。Gartner 发现，只有四分之一的公司能够将其实验性 AI 试点中的 40%（即不到一半）实际落地部署到业务中。接受调研的 6,000 位高管中有 **89%** 表示，在过去的 3 年中，完全没有看到对劳动生产率产生任何影响。

**危险信号之二：单员工支出。** Ramp 报告指出，每位员工在 AI 上的**中位数支出**（我强调一下，是中位数）大约是**每月 16 美元**。现在，中位数或平均数不应孤立来看，因为平均数是一个有点误导性的指标。为什么会有误导性？因为富人吃肉，穷人吃白菜，平均下来他们吃的是白菜猪肉卷。16 美元刚好是一个基础 AI 席位的价格，也就是 GPT 的入门套餐。这意味着付费应用虽然分布广泛，但对绝大多数用户而言仍然极其浮于表面。这并不意味着 AI 创造不了价值，但确实说明企业在 AI 上的财务投入力度，还远远不足以支撑模型训练所耗费的成本。与此同时，按 AI 支出排名前 10% 的公司，平均每位员工花费 640 美元，排名前 1% 的公司则高达约 8,000 美元。这传递了什么信号？这表明支出呈现出极其严重的偏斜。因此，作为一名 CFO，下次当你听到有关在 AI 上投入数百亿美元以及需求爆炸式增长的说法时，这会彻底改变你的看法。

然而，中位数仅仅是其中的一方面。另一面甚至更加令人震惊：**OpenAI 和 Anthropic 的 80% 利润集中在 1% 的客户手中。** 仔细体会一下这句话。作为 AI 行业的巨头、拥有全球最高估值的一批企业，OpenAI 和 Anthropic 却把 80% 的利润维系在仅仅 1% 的客户身上。1% 的客户意味着极其极端的集中度。直到今天，这种现象在科技行业中还从未出现过。对此你可能会反驳：“话虽如此，但大家都知道 OpenAI 的财务结构本来就非常不健康。”但我反过来问你：哪怕是对于英伟达这家在整个 AI 行业中拥有最健康资产负债表周转的公司，当你观察其真实利润时，大约 50% 的收入集中在 3% 的客户身上，70% 的利润集中在 5 家客户手中。这种集中度在过去 2 年里一直相当稳定。

最后，**危险信号之三：模型毫无忠诚度可言。** 越来越明显的是，企业在不同模型之间进行切换毫无心理压力。如果有一款中国开源模型能够胜任这项工作——别忘了这些中国模型往往是从美国版本蒸馏而来的——消费者和企业会在眨眼之间转投过去，且根本察觉不到多大差别。就连美国政府网站的聊天机器人里都在使用 Qwen。

更不用说普通的普通企业主了。

对模型的忠诚度就像汽车和加油站的关系。你会在意油箱里装的是谁家的汽油吗？

不在意。哪家加油站最便宜，你就会把车开进哪家。这就是 AI 正在走向的终局。当模型足够优秀时，唯一剩下的竞争维度就只有**价格**。细想一下，这具有颠覆性的意义，因为在过去的 4 年里，我们一直在关注模型军备竞赛。模型曾是撬动市场的关键。但我们已经走到了一个临界点：对于绝大多数应用场景而言，企业根本不需要最顶尖的前沿模型。目前的水平对于绝大多数商业任务来说已经足够了。AI 模型最强大的落地场景是编写代码。这从工程领域的普及率、辅助编程以及软件人才市场的显著停滞中显而易见。诚然，编程是一个拥有充足增长空间的庞大板块，但如果把编程从方程式中剔除，我们其实已经走到了这样一个阶段：**技术进步的速度无法转化为利润。**

总结一下，整个行业的押注和财务建模，此前完全基于这样一个逻辑：模型越好，使用量就越大，因此成本与定价也就越高。

但事实并非如此，这直接引向了我的最后一个观点。

<details>
<summary>Original English</summary>
Let's come back to Ramp's data and let's do a normalization here. Instead of looking at the volume and spending separately, let's look at how much revenue one token produces. Notice how this is going down. Now, put yourself in the shoes of a CFO who just signed a contract with Claude as an example, or any other LLM for that matter. When you look at this data, you see that the cost of a token is going down. And logically, you start wondering why. And when you start wondering why, you start noticing some red flags. Red flag number one, look at the peers. McKinsey reports only 37% of companies confirm that AI boosted their profits. [music] The exact same number as last year. If you're the CFO, that immediately tells you you're paying for better models, but the profit line stays exactly the same. Gartner found that only one in four companies was able to deploy only 40% less than half of their AI pilots into actual business. 6,000 executives report that 89% saw no effect on labor productivity over the past 3 years. Red flag number two, spending per employee. Ramp reports that the median, and I emphasize this, the median the median spend on AI per employee is about $16 per month. Now, median or average should not be looked at in isolation because the average is a bit of a deceiving metric. Why is it deceiving? Well, because rich people eat meat, poor people eat cabbage, and on average, they eat cabbage rolls. $16 is the price of one basic AI seat. It's a starter plan on GPT. This means that paid adoption is widespread, but still extremely shallow for the vast majority of users. It does not mean that AI does not create value, but it does mean that the financial commitment of companies to use AI is not strong enough to justify the costs spent on training. At the same time [music], the top 10% of companies by AI spending spend $640 per employee and top 1% around 8K. What does the signal? It signals that the spending is remarkably skewed. So, as a CFO, this changes your perspective the next time you hear about billion spent on AI and crazy exploding demand. But, the median is only one side of it. The other side is even more mind-blowing. 80% of OpenAI and Anthropic profits are concentrated in 1% of customers. Let this sink in. 80% of OpenAI and Anthropic, the titans of the AI industry, the companies with some of the biggest valuations on the planet are concentrating their profits in 1% of customers. 1% of customers is ultra concentration. This has never been seen in the tech industry till this day. To that, you may say, "Well, yes, but everybody knows that OpenAI economics are very unhealthy." But, I will counter. Even for Nvidia, a company with the healthiest balance sheet in the whole AI industry, when you look at real profits, around 50% of revenue is concentrated in 3% of clients and 70% of profits in five. This concentration has been quite steady for the past 2 years.

And finally, red flag number three, models have no loyalty. It's becoming more and more obvious that businesses have no problem switching between models. If there is a Chinese open-source model that gets the job done, and let us not forget that Chinese models were distilled from American versions. Consumers and businesses will switch in the blinking of an eye and won't notice that much difference. Even American government website is using Qwen in their chatbot.

Let alone a regular business owner.

Model loyalty is like cars and gas stations. Do you care whose gas is in your tank?

No. You will pull into whatever station is cheapest. That's where AI is heading. When the models are good enough, the only thing left to compete on is the price. This is earth-shaking if you think about it because for the past 4 years, we have been observing the model race. Models were the key to the market. But we have reached a point when for the vast majority of cases, businesses don't need the best frontier models. [music] The current state is enough for the overwhelming majority of business tasks. [music] The strongest use case for AI models is code. This is obvious from adoption among engineering, five coding, and the significant stagnation of the software talent market. And yes, coding is a gigantic slice with plenty of room for growth, but if you take coding out of the equation, we have reached a point where the speed of progress [music] doesn't convert to profits. To sum it up, the entire industry's bet and financial modeling was based on the fact that the better models will be used more and therefore cost more.

But that's not happening, which brings me to my last point.
</details>

### 万亿美元债务谁来买单？

**谁来偿还这数万亿美元的债务？**

《布鲁金斯经济活动学刊》（宏观经济学界极具声望的学术期刊之一）刊登了一篇名为《资助 AI 基础设施建设》（Financing the AI Buildout）的新论文。它提出了一个简单的问题：AI 数据中心需要赚取多少收入才能实现盈亏平衡？第一步是建设它们的成本；第二步是资金并不是免费借来的。这就像房贷一样，你偿还的不仅仅是房子的本金，而是房价加上利息。因此，每建一座数据中心，它都必须赚到足够的钱来覆盖成本及利息。把这两者结合起来，你就会得到账单明细。而这份账单基本上是这样的：**为了实现盈亏平衡，今天建造的数据中心到 2032 年需要产生约 9.6 万亿美元的收入。**

而现在只剩下 5 年时间了。9.6 万亿美元算多吗？这是一个天文数字。为了理解它有多庞大，让我给你一个直观的参照：这笔收入相当于**整个美国经济总量的 9%**。9% 大致相当于全美所有制造业规模的总和。作为对比，整个金融和保险行业占 8.1%，房地产与租赁行业占 13.7%。也就是说，AI 需要在 5 年内成长为美国规模最大的支柱行业之一。那么，这是否意味着对基础设施的巨额投资将永远得不到回报？

不，并不意味着这个。就像你可以申请一份 10 年期的房贷，如果你还不上，你可以把它延长到 25 年。虽然你确实需要花更长时间来还清，但这并不意味着你突然之间就会失去房子。AI 也是如此。我们正在经历的是一段严重的动荡期：财务状况充满高度不确定性，Token 的价值不断下挫，企业开始理性审视 AI 支出。这就是当今 AI 市场的真实状态。但这并不意味着全盘崩溃，它最终可能会自我平衡。以往有大量的尖端技术都经历过完全相同的阵痛期。与此同时，我们不能忽视的是，整个庞大的行业如今建立在巨额债务之上——而在 4 年后的今天，这些债务和承诺看起来似乎已经难以自圆其说了。

那么，让我们回到最初的问题：谁来为这 10 万亿美元的债务买单？

当下最诚实的答案是：**投资者。** 典型的普通企业每位员工每月仅支出 16 美元；极少数的超级“巨鲸”大客户承担了几乎所有开销，而即便是他们，也可能在一天之内转向更便宜的模型。企业只有在模型能够证明投资回报合理时，才会为更好的模型买单；而截至今天，这种情况主要集中在编程领域。

因此，好的情景是，这些债务将在未来 6 年内得到清偿；坏的情景是，债务将被摊薄拉长到更多年份中。最坏的情况下，我们只能硬着头皮挨过去。我不知道整个市场状况最终将如何实现自我平衡，但我所知道的是，有竞争总归是件好事。

让我们静观事态的发展。希望本期内容对你有所启发，我们下期节目再见。

拜拜。

<details>
<summary>Original English</summary>
Who will pay the trillion dollar debts?

There's a new paper called financing the AI buildout written for the Brookings Papers on Economic Activity, a very respected academic journals in macroeconomics. It asks a simple question. How much money do AI data centers need to earn to break even? Step one is what it costs to build them. Step two is that the money isn't free. It's like a mortgage. You don't just pay back the price of the house. You pay the price of the house plus the interest. So for each data center that gets built, it has to earn enough to cover the costs plus interest. Put those two together and you get the bill. And the bill is basically this. To break even, data centers built today need to generate about 9.6 trillion dollars in revenue by 2032.

Which is 5 years left. Is 9.6 trillion a lot? It is enormous. To understand how enormous, let me put this in perspective. That revenue would be 9% of the entire US economy. 9% is roughly the size of all American manufacturing combined. For comparison, the entire finance and insurance industries is 8.1. Real estate and rentals are 13.7. So AI would need to become one of the biggest industries in America in 5 years. Now, does this mean that enormous investments in the infrastructure will never pay off.

No, it doesn't. Just like you can take a 10-year mortgage, and if you can't pay it off, you will extend it to 25 years. Yes, it will take you longer to pay it off, but it doesn't mean you're going to lose the house all of a sudden. Same with AI. [music] What we're going through is a period of severe turbulence. The financials are highly questionable. The value of tokens is going down. Businesses start to be rational about AI spendings. And this is what the real state of the AI market looks like today. It doesn't mean it's all going to It may eventually balance itself out. Plenty of frontier technologies went through the exact same turbulence before. At the same time, let us not forget that we've got a massive industry built on debts, debts and promises that don't seem to add up 4 years in.

So, let's go back to the question, who is going to pay the $10 trillion debt? Right now, the honest answer is investors. The typical company spends $16 a month per employee. A tiny group of whales pay almost for everything, and even they can switch to a cheaper model in a day. Businesses pay for better models only when those models justify the investments. And as of today, that's mostly coding.

So, good scenario, the debts will pay off in the next 6 years. Bad scenario, the debts will spread over [music] the years. Worst case, we get over it. I don't know how this whole market situation will balance itself out, but what I do know is that the competition is good.

Let's see how it unfolds. We hope this was helpful, and we'll see you in the next episode.

Bye.
</details>