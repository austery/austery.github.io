---
author: AI Engineer
date: '2026-10-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=WOszaC1WWbQ
speaker: AI Engineer
tags:
  - distressed-debt
  - credit-analysis
  - large-language-model
  - structured-reasoning
  - probabilistic-forecasting
title: AI 能否理解困境信用？大模型在不良资产投资中的推理与预测收敛
summary: Axon Intelligence 创始人 Harneet 探讨了 AI 在困境信用投资中的理解与预测能力。针对 iHeartMedia 案例，初始状态下 Astra 6 与 Opus 5.5 预测结果分歧明显；通过引入分层结构化推理流程，两款模型对未来重组路径的概率评估最终实现收敛。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Harneet Kaur
companies_orgs:
  - Axon Intelligence
  - iHeartMedia
products_models:
  - Astra 6
  - Opus 5.5
media_books: []
status: evergreen
---
### 困境信用的定义与成因

>> 感谢大家的到来。我非常高兴能在这里做这次分享。

<details>
<summary>Original English</summary>
[music]

>> Um thanks to everyone for being here. I'm so excited to be doing this talk.
</details>

先做个简短的自我介绍。我叫 Harneet，是 Axon Intelligence 的创始人兼首席执行官。在 Axon，我们正在为困境信用（distressed credit）投资构建智能化层。这也正是我们今天要探讨的主题。这次演讲的题目是：AI 能理解困境信用吗？

<details>
<summary>Original English</summary>
So, um kind of quick intro on me. So, my name is Harneet. Um I'm the founder and CEO of Axon Intelligence. And in Axon, we're building the intelligence layer for distressed credit investing. So, also what we're going to be talking about today. Um and the title of this talk is can AI understand a distressed credit?
</details>

对于不熟悉信用领域的人来说，大家脑海中的第一个问题可能是：困境信用到底意味着什么？信用其实很简单，它就是公司发行的债券或贷款。比如，可口可乐发行的债券就是一种信用。

<details>
<summary>Original English</summary>
I think the first question um on everyone's minds, if you're not you know, in the world of credit, is what does distressed credit really mean? Um credit is pretty simple. So, credit is just a bond or loan um you know, of a of a of a corporation. The bond of Coca-Cola is a credit.
</details>

那么，承压（stressed）或陷入困境（distressed）又是什么意思呢？当公司存在某种潜在风险，可能导致其出现两种情况之一时，压力就会产生：**第一，资金耗尽**；**第二，无法偿还债务**。

<details>
<summary>Original English</summary>
Um now, what does it mean to be stressed or distressed? Right? So, stress really happens if there is any sort of underlying risk in the company that would lead them to either one run out of money, two, not be able to pay back their debt.
</details>

因此，每年信贷市场中总会有一部分面临某种程度的承压或困境。这可能是由周期性问题引起的，例如建筑业或房地产市场低迷；可能是由运营问题引起的，比如餐饮企业遭遇大规模食品召回；也可能是由长期性颠覆引起的，例如当下的软件企业可能正在面临 AI 的冲击。有些企业在面临挑战后能迅速恢复，而有些企业则会陷入真正的困境。

<details>
<summary>Original English</summary>
So, every portion uh every year some portion of the credit market faces some level of dis- uh stress or distress. Can caused by cyclical issues. So, let's say construction you know, the construction market is down, housing market is down. Um it can be caused by operational issues. If you're a restaurant business, there's a big food recall. Um it can also be caused by um secular disruption. So, if you're a software business today, and maybe seeing some AI disruption, right? Um some businesses face challenges and then come right back up. Some businesses face challenges and then get to a place of distress.
</details>

困境究竟意味着什么？这实际上并不简单。破产只是困境的一种结果；你还可以进行负债管理操作（这些术语我稍后可以展开，但先了解有这种情况），或者采取庭外重组、协商置换等，这些都是其中的几种可能路径。

<details>
<summary>Original English</summary>
What does distress mean? It's actually not straightforward. Bankruptcy is one outcome of distress. You can also have a liability management exercise and these are terms I can get into them, but just know that's another uh thing that could happen and then or you can have an out-of-court restructuring negotiated exchange um are a couple of the options. Um
</details>

### 传统分析方法的局限与定性挑战

翻到下一张幻灯片。如你所见，这并不简单。历史上，针对困境的工程预测问题非常二元化：你要么预测它会违约，要么预测它不会违约。但在今天，情况变得复杂得多。许多传统的机器学习方法已经跟不上步伐，而诸如 Altman Z-score 这样在 10 年、15 年或 20 年前非常关键的评分系统，在面对这种可能每月、每季度甚至每年都在动态变化的情境时，已经显得过于静态。此外，当前的市场也更加不透明——如果你一直关注信贷领域，就会发现私募信贷（private credit）及相关领域的崛起导致了市场缺乏透明的公开定价。

<details>
<summary>Original English</summary>
So, next slide. So, as you saw, it's not that simple, right? Historically, the engineering question for distress was pretty binary. So, you can predict a bankruptcy e- either you predict it goes to a default or it doesn't. Today, that's become a lot more complex. Um so, a lot of these traditional machine learning method methodologies just haven't kept up and a lot of the scoring that was pretty important um maybe 10, 15, 20 years ago. Um uh the big one is the Altman Z-score um has become now very static um in terms of a situation that changes, you know, sometimes monthly, quarterly, yearly, um and also is in a much more opaque market. So, if you've ever been following credit, the rise of private credit and some of these other areas have caused, you know, a lack of pricing.
</details>

另一方面，理解和分析困境信用的方法通常高度定性。作为困境信用投资者，你需要分析财务报表、了解债权人层面的动态、阅读信用合同文档——基本上就是一个普通对冲基金或私募股权投资者为了弄清信用状况所做的一切工作。这个过程非常依赖人工，显然极难规模化。

<details>
<summary>Original English</summary>
On the other hand, you have a very qualitative method of understanding and analyzing distressed credit, um which is as a distressed credit investor, you can you know, analyze financials, understand what's going on in the lender side, read the credit docs. Basically, you know, all the things a normal, you know, hedge fund investor or private private equity investor would do um to understand a credit. This process is super manual, very hard to scale, obviously. Right?
</details>

现在的问题在于，也是我创立 Axium（Axon）时思考的一个问题：AI 在理解困境信用及其可能走向的路径方面，究竟能走多远？你能否将这样一个极其复杂的流程系统化？

<details>
<summary>Original English</summary>
Now, the question is, um you know, part of starting Axium and a question I thought about is what can how far can AI get at understanding a distressed um a distressed credit and the type of paths you can take. Um and can you systematize what is effectively a pretty complex process, right? Um
</details>

### AI 模型在 iHeartMedia 案例上的分歧

那么，理解困境信用意味着什么？作为投资者，我们试图回答许多问题。从财务角度需要考虑：流动性状况如何？资本结构是怎样的？从法律角度也有问题：债务的结构性偿付优先级如何，是居于较高优先级还是较低优先级？此外还有运营层面的考量：如何理解这项业务？营业收入如何？基于对业务的基本面分析，明天的收入会上升还是下降？

<details>
<summary>Original English</summary>
So, now what does it mean to understand a distressed credit, right? Like as an investor, we have a lot of questions we're trying to answer. Um the the things that you think about um from a financial side, right? What is um you know, what is liquidity? What is the capital structure? And then you have questions from the legal side. How, you know, what's the structural priority of the debt? Right? Like do you have higher priority or lower priority? And then you have operational issues, like okay, how do you understand the business? What are the revenues? Are the revenues going to go up or down tomorrow based on fundamental you know, fundamental analysis of the business. Right?
</details>

目前我们在市场上看到的情况是，如果你关注 Pro Go、Harvey 或其他大型 AI 公司，他们所做的主要是针对这些具体问题进行基准评测。比如测试 AI 在回答“债务的哪一部分在结构上具有优先权”这类问题上表现如何，然后进行严格的基准测试，打造出所谓的金融大基准。但我希望换个角度来思考：我认为对信用、尤其是困境信用的真正理解，在于你能否预测接下来的走向。我能否厘清并得出其未来走向各种路径的概率分布？

<details>
<summary>Original English</summary>
Um his- Right now, what we've seen in the market, you know, if you're following Pro Go or Harvey or some of these, you know, big AI companies, what they've done is really think about benchmarking all these different questions, right? Like how good is AI answer answering um what part of the debt is structurally senior? Um and then kind of do rigorous benchmarking and make that um you know, call it the big finance bench. But I wanted to think about it slightly differently, right? Because the way I thought about it is the true understanding, right, of credit, and particularly distressed credit, is can you predict what happens next? Right? Can I figure out and have a probability distribution of what path this takes in the future?
</details>

因此，我认为第一步要做的是一个有趣的实验：选定一家公司。我挑选了 iHeartMedia，这家公司曾在 2018 年申请过破产，可谓历经坎坷；而且它在 2024 年又进行了一笔承压交易。这是一个正在发生的真实实时案例，目前没有人知道确切的未来答案，没有既定的客观真相事实（ground truth）。

<details>
<summary>Original English</summary>
Um so kind of an interesting exercise, I thought step one you know, you should do is take all the you know, I chose a company. So, I chose iHeartMedia, which is a company that filed for a bankruptcy in 2018. So, it's you know, it's it's been through the rigmarole rigmarole. Um it also went and did uh another stressed transaction back in 2024. So, this is a live situation. This is happening today. No one has a real, you know, answer for what's the future, right? Um there's no ground truth.
</details>

我所做的是把数据输入到最顶尖的模型中。我测试了 Max Intelligence 上的 Astra 6 以及 Opus 5.5。得出的一个非常有趣的结论是：它们得出了不同的结论。

<details>
<summary>Original English</summary>
But what I did was let's throw it into the smartest, you know, models. I did Astra 6 on Max Intelligence um and Opus 5.5. And what I what was a really interesting kind of conclusion is that they disagreed.
</details>

在给定相同数据结构和背景信息的情况下，它们对未来发生各种路径的概率判断并不一致。从图表中可以看到，对于协商重组（negotiated restructuring），Astra 认为这是最佳选项；而对于破产，Opus 认为那是概率最高的选项。

<details>
<summary>Original English</summary>
Like they disagreed on what the probabilities of the future would be um given a structure or context of the data, right? And so, uh if you look here on um negotiated restructuring, Astra thought that was the best option um for a bankruptcy, um Opus thought that that was the best option, right?
</details>

现在，你该如何判定谁对谁错呢？你无法判定，因为我也不知道确切的概率是多少，不知道接下来会发生什么。我不知道它会走向破产、庭外重组，还是进行再融资。我有我自己的最佳主观判断，我个人更倾向于 Astra 6，但我们都是人。这个结论非常耐人寻味——它们竟然产生了分歧。

<details>
<summary>Original English</summary>
Now, how do you how do you say which is right or wrong? You can't cuz I don't know what the probabilities are, right? I don't know what's going to happen. I don't know if it's going to be a bankruptcy. I don't know if it's going to be a out of court restructuring. I don't know if it's going to be a refinancing. I have my best judgment on things. I I would say I lean towards Astra 6, but you know, we're all human. And it's a kind of an interesting conclusion, right? Like, okay, wait wait they disagree. Um
</details>

### 构建分层推理基准

所以我思考的第二件事是：我该如何改进对它们推导过程的评估？我可以去检查自己是否同意它们做出的各项假设。因此，基本上就是建立这样一种基准体系，对每一个层级进行评估。显然，在每个层级上，大语言模型都可能出错。

<details>
<summary>Original English</summary>
so, the second thing I thought about is Okay, how do I improve at least an assessment of their process, right? So, I can look at um whether I agree or disagree with the different assumptions. Um and so, basically you've created this sort of benchmark um where you you know, we benchmark each layer. So, obviously these are at each layer the LLM could mess up, right?
</details>

在**信息提取层（extraction layer）**，对于上市公司，我认为这基本上已经被解决了；但对于私募贷款，以及面对 Excel 文档和 PDF 时，它仍然是一项挑战。接着是**对账或衍生计算层（reconciliation or derivation layer）**。提取层是指你提取出了息税折旧摊销前利润（EBITDA）；而衍生层则是，既然有了 EBITDA 和总负债，你就可以推导出杠杆率。然后是**判断层（judgment layer）**：既然得到了杠杆率，这到底是不是一笔困境信用？你的判断是什么——

哎呀。是不是……好吧，我直接接着讲。基本上核心问题在于……我想我的电脑可能没电关机了。

抱歉，稍等一下。虽然我有充电器，但没带在身边。没关系，我就直接讲吧。噢，好了，它又能显示了。

>> [笑声]

<details>
<summary>Original English</summary>
On the extraction layer, I would say with public companies it's it's pretty it's pretty solved. I would say with private loans and and when you have like Excel documents and PDFs, that can that can still be a challenge, right? Then you have the reconciliation or derivation layer. So, extraction would be you got EBITDA. Uh derivation would be, okay, now you have EBITDA and you have debt, now you can have leverage. Um and then you have a judgment. Okay, now you have the leverage. Is this a distressed credit or not? What's your Uh-oh. Uh Is there like a Okay, I'll just going to I'll just keep talking. So, um basically the question is is this I think my computer Died. Um Sorry, 1 second. I'll tell you the I do have a charger, but it's not here. No. Uh yeah. Okay, I'll just I'll just talk. That's fine. Oh, okay. It's working.

>> [laughter]
</details>

>> 好，前面提到了**判断层**。接下来，如果你能够对每一个层级进行评估，确保在进入**预测层（prediction layer）**之前，数据点是准确的、对账推导层是合理的，并且形成了一定程度的合逻辑判断。完成这些层级的确认后，你才能进入预测层。人类分析师在思考这一整套步骤时其实正是如此运作的：如果你把判断建立在错误的数据点上，那绝对不可能得出良好的判断，整个逻辑就是这样运行的。

<details>
<summary>Original English</summary>
>> Okay. So, So, you got the judgment layer, right? And then, um then then then you can start, okay, if you can assess each layer, right? Once you get to the prediction layer, you've assured the data points are good, you've assured that um the reconciliation layer is good, you've assured that there's some sort of reasonable judgment, right? And then, once you've assured those things, then you can get to the prediction layer, which is really how, you know, as a human analyst, you think about all of these steps, right? You You If you build a judgment on a bad data point, that's not going to be a good judgment, and that's That's just the way this works, right?
</details>

### 结构化推理带来的收敛与核心启示

看这里。我们发现的结果（也许这并不令人意外，但我认为非常有趣）是：一旦我们构建了结构化的推理流程，两款大模型对该企业未来走向的概率预测实际上产生了**收敛**。

<details>
<summary>Original English</summary>
So, um Oop. Here we go. So, basically what we found, and maybe this is not surprising, but um thought it was interesting, is that once we actually created the structured reasoning process, you you actually had both the intelligence, both the models actually converge in terms of what they believed the future probabilities of the business are going to be, right?
</details>

现在，不再是 Opus 给出 62% 的破产概率而 Astra 给出 25% 的破产概率，两个模型都判定破产的概率只有四分之一（即 25%），并且双方一致认为协商重组是该企业更可能的走向。

<details>
<summary>Original English</summary>
So, now instead of saying 62% bankruptcy with Opus and 25% bankruptcy with Astra, now both these models are saying there's actually only a quarter or 25% chance of bankruptcy and both models agreed that the negotiated restructuring path is actually the more likely path of the business.
</details>

那么，这里面的核心启示是什么呢？

我认为第一个启示是：面对无法直接验证客观事实的问题，即使给予与人类相同且结构有序的上下文，这些模型是否具备预测优势？不得不说，答案是否定的。因为在某种意义上，这些智能体也类似于人（我就不深入展开相关争议了）。

<details>
<summary>Original English</summary>
So, what are kind of the big takeaways here, right? Um one I would say the first takeaway is one given non-verifiable questions, right? With the same structured context, organized context as a human. I mean, do these models have a predictive edge? And you have to say no, right? Because they are in effect, even agents are human, right? In in some sense of the word and I won't get into the controversy there.
</details>

第二个启示是：结构化的推理流程能够促使两个模型（或不同的智能系统）就未来的展望达成实质上一致的观点，并对企业的经营状况及可能走向形成高度相似的理解。

<details>
<summary>Original English</summary>
Um the second is but a structured reasoning process can get the two models to or, you know, different intelligences to converge on effectively a same view of the future and effectively a similar understanding of of a business and the path it could take.
</details>

但这是否就是正确的路径？我们无法确定。而且这确实是目前最真实的衡量方式，因为任何形式的历史回测都可能引入前瞻偏差（look-ahead bias）。

但我一直在思考的一件极其有趣的事情在于：这种**收敛性**本身非常耐人寻味。因为如果你能系统化地构建一个让不同模型对概率结果产生收敛的流程，这在本质上其实就构成了市场中的“定价”。我认为这是一个很有意思的发现。

<details>
<summary>Original English</summary>
Um but is that the correct path? We don't know, right? Um and is this is really only at the truest measure, right? Cuz otherwise any sort of historical analysis would create some sort of look ahead bias. Um but I think the the really interesting thing that I've been thinking about is um the convergence is pretty interesting, too, right? Because if you can systematically build a process that actually converges on the same probabilistic outcomes. That is effectively what is a price in a market. Um, and so I I thought that was an interesting takeaway.
</details>

这就是我要分享的最后一点。最后再简短介绍一下我自己：正如前面提到的，我叫 Harneet，正在创立 Axon。我的个人背景是在金融领域工作了 10 年，过去几年在一家专注于困境资产的私募股权及对冲基金担任困境信用与特殊机会投资人。如果你对 Axon 感兴趣，这里有二维码。这就是我今天分享的全部内容，谢谢大家。

<details>
<summary>Original English</summary>
Um, so that's the last thing. And then just a quick kind of spiel on me. So, my name's, like I said, Harini. Um, building Axon. Um, kind of background on me. I spent 10 years in finance. Um, the last few as a distressed credit and special situations investor at a um, uh, distressed PE / hedge fund. Um, and then this is the QR code if you're interested in Axon. Um, and that's all I had. Thank you.
</details>