---
author: a16z
date: '2026-08-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=n34CIw3gk1k
speaker: a16z
tags:
  - agentic-architecture
  - ai-transformation
  - eval-driven-development
  - organizational-design
  - creative-destruction
title: Kavak的AI原生转型：从二手车市场到智能体驱动公司
summary: Kavak AI负责人Ali Masa分享如何将公司彻底重构为智能体驱动组织：从每客户专属智能体架构、评估体系设计，到Jedi Academy全员培训计划。他提出'创造性破坏'理论，认为新创公司将取代仅表面采用AI的现有企业，并给出创始人建议：深度拥抱AI而非浅层应用。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ali Masa
companies_orgs:
  - Kavak
products_models:
  - Opus 4.5
media_books: []
status: evergreen
---
### 开场与背景

**主持人**: 欢迎回到ACC播客。今天我们邀请到了Kavak的AI负责人Ali Masa。我们将讨论Ali在Kavak内部领导的转型，将其转变为一家AI原生公司。Ali，感谢你今天与我们同在。

<details>
<summary>Original English</summary>

**[Host]**: Welcome back to the ACC podcast. Uh today we have Ali Masa the head of AI at Kavak. We're going to discuss today the transformation that Ali led within Kavak to turn it into an AI native company. Thank you Ali for being with us today.

</details>

**Ali Masa**: 感谢邀请我。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Thanks for having me.

</details>

**主持人**: 在加入Kavak之前，你经营着一家名为Oppy Analytics的公司。

<details>
<summary>Original English</summary>

**[Host]**: Before starting at Kavak uh you were running a company called Oppy Analytics.

</details>

**Ali Masa**: 没错。

<details>
<summary>Original English</summary>

**[Ali Masa]**: That's right.

</details>

**主持人**: 而且你在ChatGPT出现之前就非常投入AI领域。你能跟我们谈谈那段旅程吗？

<details>
<summary>Original English</summary>

**[Host]**: And you were very much into AI before ChatGPT. You want to tell us a little bit about that journey?

</details>

**Ali Masa**: 是的，当然。嗯，我们当时称之为机器学习。那是另一类算法家族。我们创立这家公司时怀揣着一个非常宏大的愿景：新的机器学习模型将强大到足以解决任何复杂问题。那是在Transformer出现之前，对吧？大概是2013年。所以我们以那样的方式开始建设公司，我认为我们领先了时代大约10年。但我们建立了一家很棒的公司。我们服务了财富500强企业，涉及风险算法、物流、预测、营销等领域。但真正重要的是，Transformer的力量，以及后来ChatGPT时刻的到来，让我们清楚地看到，我们现在可以建立一家全新的公司，一种全新的公司建设方式。于是我们加入了Kavak，与Carlos一起建设这一切。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. Yes, of course. Well, we called it machine learning back then. It was a different family of algorithms and we founded a company with this very ambitious vision there that new machine learning models would be so powerful that they could solve any complex problem. This was pre-transformers, right? This was like 2013. So, we started building the company that way and I think we were like 10 years ahead of time. Uh but we built a great company. We served like Fortune 500 companies uh around like risk algorithms, logistics, forecasting, marketing and but like really the power of what Transformers and then like the ChatGPT moment uh when it arrived make things like very clearly that we could now build a whole new uh company and way of building companies and we joined Kavak to and Carlos to build that.

</details>

**主持人**: 太棒了。好的，我们将花大部分时间讨论你如何改造Kavak。但也许先简单介绍一下，Kavak是做什么的，你在那里的角色是什么？

<details>
<summary>Original English</summary>

**[Host]**: Amazing. All right. So, we're going to spend the bulk of this podcast talking about exactly how you've identified Kavak. But maybe just to start, what does Kavak do and what is your role there?

</details>

**Ali Masa**: Kavak最初是一个用例，一个二手车市场。我们买车、翻新车，然后出售并提供融资。但要做到这一点，我们还必须建立一家金融科技公司和一家物流公司，以及Carfax。基本上，在拉美，让这一切运转所需的所有基础设施都不存在。所以我们不得不垂直地构建一切，以便以正确的方式服务我们的客户。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Kavak started out as a use case as a used car marketplace. So, we buy cars, we refurbish them, and then we sell them and finance them. But to do that, we also had to build a fintech and a logistics company and the Carfax and like basically all the infrastructure for this to work didn't exist in Latam. So we had to build everything vertically so we could serve our customers the right way.

</details>

### 智能体架构设计

**主持人**: 我想先从架构的框架开始。一个消费者进来说"我想卖我的车"，他们会接触到多少个智能体？这个"harness"（控制框架）是什么样的？请让我们了解你们是如何设计这个的。

<details>
<summary>Original English</summary>

**[Host]**: I'm going to sort of start with the framing of what the architecture looks like. So a consumer comes in and says I want to sell my car like how many agents do they touch? Like what's the harness look like? Like ground us in how you design this.

</details>

**Ali Masa**: 对。我们押注公司将转型为由智能体运营的公司。我们问自己的问题是：如果拥有Fable 10或GPT 10级别的智能，我们会如何在2035年建设Kavak？实际上，那家公司与我们当时所建的或所拥有的非常不同。所以现在当客户进来时，会有一个专门为该客户生成的智能体，拥有自己的虚拟机。它会记住这个客户与Kavak多年来的互动——他们访问过哪些网页，或者两年前打过的一通电话。它会在记忆中记住一切。它会制定策略，设定长期目标，以最大化这个客户的终身价值，并尽一切努力让客户满意，将他们转化为我们所有不同产品的用户，并且是跨时间的。这是一个全新的、开创性的大规模架构。我认为，因为人们仍在构建带有专家的多智能体系统，而我们意识到，押注于具有硬性目标的长期运行智能体——而不仅仅是工作流——可以最大化我们客户的满意度，显然还有他们的终身价值。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Right. So, so, so we bet the company in transforming to a company run by agents. The questions we ask ourselves is how would we build Kavak in 2035 with Fable 10 or GPT 10 level intelligence and actually that company looks very different than what we had built or what we had back then. So when a customer comes in right now um agent will get spawned specifically for this customer with its own virtual machine. It'll remember years of interaction of this customers with Kavak what they visited in the web page or a call they had two years ago. Remember everything like in its memory. Come up with a strategy and set a long-term goal to maximize the lifetime value of this customer and do whatever it takes to make the customer happy and convert them into like all our different products and like across time and this is a completely new and groundbreaking architecture at scale. Uh I think because like people are still building multi-agent system with with experts and and we realized to bet that long-running agents with hard goals not just workflows uh could could maximize our our customers uh satisfaction and obviously their their lifetime value.

</details>

**主持人**: 太棒了。好的，我们要深入探讨那些细节。但也许与许多说"嘿，我们要成为智能体化"并尝试一些工作流的公司相比，你们采取了彻底的方式——我们不得不让这个运转起来，你们不得不大幅缩减规模，有一年时间它并不奏效。

<details>
<summary>Original English</summary>

**[Host]**: Awesome. Okay. So we're going to jump to the nuances that but maybe versus many companies that say hey we want to be agentic and they try some workflows you guys took the just rip like we had to make this work you had to downsize dramatically it didn't work for a year

</details>

**Ali Masa**: 对。

<details>
<summary>Original English</summary>

**[Ali Masa]**: right

</details>

**主持人**: 所以你想谈谈吗？显然你必须调整很多事情才能让它运转。描述一下当时的harness，你们使用了什么模型，具体说说。

<details>
<summary>Original English</summary>

**[Host]**: so do you want to talk through obviously you had to tune a lot of things to make that work like describe the harness at that time and like what models you were using and sort of specifically yeah

</details>

**Ali Masa**: 所以我们当时必须做出三个主要决策。第一个——我认为许多公司现在就卡在这里——第一反应是"好吧，让我们采用AI"，你基本上保持你的结构不变，只是把ChatGPT给你的团队，然后没有效率提升，你的客户有同样的问题，什么都不会发生，对吧？所以你需要围绕智能体和未来能力重新设计你的整个公司。这意味着真正重建你的大部分API，重建你的系统，以便智能体可以使用它们来执行任务。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So so there there were like three main decisions that that we had to make. The first and this is where I think many companies are stuck right now is the first instinct is okay let's adopt AI and you you basically leave your structure as it is and just give ChatGPT to your team and then there's no efficiencies your customers have the same problems and nothing happens right and so so you need to redesign your whole company around the agents and around the future capabilities and this means really like rebuilding most of your APIs, rebuilding your system so the agents can use them to to perform.

</details>

**Ali Masa**: 然后你需要开始生成数据和反馈循环来微调这些智能体。让它们真正运转的唯一方法就是教它们。你怎么教它们？你把它们放到开放环境中。你把它们放在客户面前。你获得那些数据。你获得那些评估，然后你训练你的智能体。这是我们做的第二个赌注：我们可以构建超人智能体。这意味着在每个重要的维度上——转化率、终身价值、客户体验——我们的智能体将超越我们曾经雇佣过的最优秀的人类。我们把它们放在最困难的问题面前。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Then you need to start generating the data and the feedback loops to fine-tune these agents. The only way to really make them work is if you teach them. And how do you teach them? You put them out in the open. You put them in front of customers. You get that data. You get those evals and then you train your agents. And this is the second bet that we made that we could build superhuman agents. This means that by every dimension that matters like conversion, lifetime value, uh customer experience, our agents would outperform the best human we had ever hired and we put them in front of the hardest problems.

</details>

**Ali Masa**: 最后，你开始改变衡量公司成功的方式。Kavak曾经是一家交易型公司。我们过去衡量我们买了多少辆车，卖了多少辆车，我们需要买多少刹车片。我们转向了一家关系型公司——现在我的数据库里有1000万客户，其中大多数都分配了智能体，任务是最大化他们的终身价值。现在，我们在销售汽车、个人贷款和非常高客单价的产品。所以仅仅激活这个客户群的1%，就是数亿美元，如果我们做对了的话。所以这对我们来说是一个合理的赌注，因为我们的行业、因为客单价、因为归根结底，客户需要与公司建立信任，因为他们买的是二手车。而建立信任的方式是了解他们，规划并培育一种长期关系。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Um and finally you start to change how you measure the success of the company. Kavak was a transactional company. We used to measure how many cars we bought, how many cars we sold, how many brake pads we needed to buy. And we moved to a relational company where now I have 10 million customers in my database and I have agents assigned to most of them with the task of maximizing their lifetime value. Now, we're selling cars and personal loans and very high ticket items. So just activating 1% of this customer base, it's like hundreds of millions of dollars uh if we do it the right way. So it's a bet that made sense for us because of our industry, because of the ticket, and because at the end of the day, customers need to build trust with a company because they're buying a used car. And the way to build trust is to know them and to plan and nurture a long-term relationship.

</details>

### 评估体系与规模

**主持人**: Ali，我想深入探讨一下。你知道，评估优于智能体演示。你可能收到很多新智能体的推销，你知道，现在比以往任何时候都更容易构建东西。但其中一个问题是，你们如何进行评估？因为不是每个人都会在90%的客户互动中测试它们，看看它们是否真的有效。而且你们，我相信，大约98%的互动现在是由智能体处理的，对吗？

<details>
<summary>Original English</summary>

**[Host]**: Ali, I just wanted to double click on something. You know, evals over agent demos. Yeah. Um you probably get pitched a lot of new agents and you know, it's never been easier to build things like before. But um one of the questions is like how do you guys go about evaluating this? Because not everybody test them across 90% of the customer interactions to see if they're really working. And you know you guys I believe is it about 98% of the interactions or something yes like that are now handled by agents.

</details>

**Ali Masa**: 是的，完全正确。让我给你一个规模的概念：大约96%的所有互动由智能体处理，那里没有人类。大约95%的所有交易完全由智能体处理。显然，当你提车时会见到人类，有人在那里给你钥匙。但体验和旅程的其余部分都由智能体处理。每天有10万到20万个智能体被实例化。它们醒来，工作——有时三分钟，有时八小时，有时三天——然后它们为下一个任务设定闹钟，然后回去睡觉。这个规模真是太惊人了，而且它正在运转。那么，你如何让它在规模上运转呢？答案就是你提到的——评估。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. Totally. So to give you a sense of the scale: like 96% of all interactions uh are handled by agents. So no humans there. Um like 95% of all transactions are completely handled by agents. Obviously, you meet a human when you pick up your car, like there's someone physically there to give you the keys. But the rest of the experience of the journey is handled by an agent. Every day between 100 and 200,000 agents get instantiated in a day. They wake up, they work sometimes for three minutes, sometimes for eight hours, sometimes for three days, and they set an alarm clock for their next task and they go back to sleep. So the scale of this is just amazing and it's working. Now, how do you get this to work at scale? And the answer you mentioned it is evals.

</details>

**Ali Masa**: 我喜欢极速前进，但为了快速前进，你需要有刹车，对吧？想象一辆车。只有有了好的刹车，你才敢踩油门。AI非常强大。我看到许多公司在这方面犯错，因为他们试图放慢速度，因为他们没有好的刹车。所以我的思考方式是反过来的：我们能跑多快？嗯，这取决于我们评估的质量。这里一个好的经验法则是，我们花费大约相同的时间、工程师时间、token和金钱来构建评估，就像构建智能体一样。这就是你如何变得越来越好，而不是把评估当作事后诸葛亮。

<details>
<summary>Original English</summary>

**[Ali Masa]**: I like to move extremely fast, but in order to move fast, you need to have brakes, right? Imagine a car. You'll hit on the gas just if you have the right brakes. And AI is super powerful. And I've seen many companies get this wrong because they try to go slow because they don't have the right brakes. So I thought about it the other way around, like how fast can we go? Well, it depends on the quality of our evals. So, a good rule of thumb here is we spend about the same amount of time, engineer time, tokens, and money on building the evals than building the agents. And this is how you get better and better and better, not letting evals as an afterthought.

</details>

**Ali Masa**: 那么，我们首先衡量什么？最重要的是业务结果。如果我的客户满意，他们会买车，他们的贷款会获批，他们会把车卖给我们。这是第一个检查点：它转化了吗？大多数事情就是在那里崩溃的。我看到公司衡量通话次数或通话分钟数，或者一些肤浅的KPI，这些能给你一些信息，但并不真正有效。重要的是：这个客户转化了吗？它是否为客户带来了价值？客户在一段时间后是否愿意再次与我们互动？一旦你把这些评估连接起来，剩下的就是优化正确的智能体架构，并赋予智能体技能来扩展这个规模，服务数百万客户。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So, what do we measure first and foremost? Like the results for the business. Like if my customer is happy, they'll buy a car, they'll get their loan approved. Uh they'll sell a car to us and that's the first check like did it convert? And that's where most things break. Like I see companies like measuring number of calls or minutes during the call or some superficial KPIs that give you some information but that doesn't really work. Like the important thing is did this customer convert? Is it bringing value to the customer and is the customer happy to re-engage with us after a while? And once you get those evals connected, then it's just optimizing the right agentic architecture and giving the agent skills to scale this and cater to millions of customers.

</details>

### 销售智能体

**主持人**: 这真的很了不起。与此相关的是，好吧，你创建了正确的评估，它正在运转。你知道，有些公司仍然有点风险规避，不敢把它们放在客户面前，让它们执行最高杠杆的任务——在你们的情况下就是销售。你们的智能体真的向客户销售吗？

<details>
<summary>Original English</summary>

**[Host]**: It's really really amazing and you know related to this is like okay so you create the right evals it's working you know some people some companies still feel a little bit risk averse and putting them in front of the customers and being able to perform the highest leverage task which in your case would be selling. Do do your agents really sell to customers?

</details>

**Ali Masa**: 是的。我们从未构建过客户支持或客户服务智能体。我们构建的是销售智能体。在拉丁美洲卖车极其困难。想象一下有人想买车。他们可以在大约2万个SKU中选择。然后他们需要选择融资方案，经历融资流程、保险和保障。然后他们可能还要置换他们的车。所以我们需要给那辆车估价。所以这是一个过程，如果一个人来做，或者Kavak在2020、2021年做的方式，是你需要在15件不同的事情上极其出色，有15个不同团队的15个不同专家。通常这个人会去和融资专家、汽车咨询专家、购车专家、保险专家交谈，他们会打包一个方案然后买车。这极其困难。但我们做的第一件事是：好吧，我们能不能让一个智能体在每个方面都比专家更好？然后把它组合起来，成为一个超级专家——一个在保险、融资等方面都是专家的智能体。这就是我们放在客户面前的东西。所以客户的体验是惊人的。通过把智能体放在客户面前，我们的NPS和客户满意度评分翻了三倍。起初它的转化率比我们的人类团队高50%，现在它的转化率是2.1倍以上。所以这是一个完全不同的概念。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. So we never built customer support or customer service agents. We built like sales agents. It's extremely hard to sell a car in Latin America. So imagine someone wanting to buy a car. They can choose amongst like 20,000 SKUs. Then they need to pick like financing and go through the financing process, insurance and coverage. And then they're probably trading in their car. So we need to quote that car. So, it's a process that if someone does it or the way Kavak did it back in 2020 2021 was you need to be extremely good at 15 different things and have 15 different experts in 15 different teams. And usually the person would go and speak with the expert in financing, the expert in car advisory, the expert in buying, the expert in insurance, and they'll build a package and buy a car. That's extremely hard to do. But like the first thing we did was okay, can we get an agent to be better than the expert in each of these things and then put it together and have like a mega expert that's an expert in insurance, financing, etc. And that's who we put in front of the customer. So the experience for the customer is amazing. We tripled uh NPS and customer satisfaction score by putting the agent in front of the customer. And it at first it converted like 50% more than our human team and now it's converting over that like 2.1 uh x more. So it's a completely different concept.

</details>

**主持人**: 你们的智能体是更好的销售员。

<details>
<summary>Original English</summary>

**[Host]**: Your agents are better sellers.

</details>

**Ali Masa**: 完全更好。你之所以能做到这一点，是因为它们是专家，它们无限耐心，它们知道你所有的历史，它们可以做长期规划，而且它们永远不会疲倦。而且，如果它们犯了错误，它们会学习，第二天，不仅仅是它们，其他20万个智能体也会从那个错误中学习。这就是我们参与的反馈循环，这体现在我们客户的增长、结果和满意度上。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Totally better. And you get this right because they're experts and they're infinitely patient and they know all your history and they can plan for the long term and they never get tired. So, and if they make a mistake, they learn it and the next day, not just them, but the other 200,000 agents will have learned from that mistake. So, that's the feedback loop that we engaged and that's showing in the growth and results and satisfaction of our customers.

</details>

### 金融服务的AI化

**主持人**: 是的。关于Kavak，我认为有两件很酷的事情。我认为世界已经习惯了AI可以做客户服务。虽然做好仍然很难。但正如Gabe所说，仍然有一种观点认为，客户不会想从AI那里购买昂贵的东西，而你们正在证明他们是错的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah. One of the well, one of two of the very cool things I think about Kavak is I think the world has gotten comfortable with AI can do customer service. It's still very hard to do well. But you know, as Gabe said, there's still a view that well, customers aren't going to want to buy expensive things from AI, and you are proving them wrong.

</details>

**主持人**: 下一层是，你实际上无法用AI端到端地做受监管的金融服务。

<details>
<summary>Original English</summary>

**[Host]**: The next layer on that is, well, you're not actually going to be able to do regulated financial services end to end with AI.

</details>

**主持人**: 但如果看看你们在做什么，你们在为薄文件或无文件客户承保。

<details>
<summary>Original English</summary>

**[Host]**: But if you walk through what you're doing, you are underwriting a thin or no file customer.

</details>

**Ali Masa**: 是的。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes.

</details>

**主持人**: 正确地为他们定价，提供服务。所以也许谈谈你们是如何编写评估来对此感到放心的，然后与去银行分行甚至金融科技公司相比，那种体验如何？

<details>
<summary>Original English</summary>

**[Host]**: Pricing them correctly, doing servicing. So, so maybe talk through how did you write the evals to get comfortable with that and then versus I don't know going to a bank branch or even a fintech sort of how how is that experience?

</details>

**Ali Masa**: 好得多。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. So much better.

</details>

**Ali Masa**: 我们推出的第一个金融产品是汽车贷款。通常在墨西哥和一些新兴市场，获得汽车贷款批准需要两个月或更长时间。我们通常在3分钟内批准。这挺酷的，因为我们拥有关于客户和汽车的所有数据。而且如果客户再也付不起车款，他们可以直接把车还给我们，我们可以给他们一辆更便宜的车，然后他们每月支付更少的金额，他们就能摆脱困境。这是业务垂直整合的美妙之处。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So the first financial product that we launched was a car loan and usually in Mexico and in some emerging markets it'll get like two months or more to get a car loan approved. Um, we usually approve it in under three minutes. Uh, which is like pretty cool because we have all this data around the customer and the car. And if the customer can't pay for the car anymore, they'll just return it to us and we can give them a cheaper car and then they pay a smaller amount each month and they like get out of the water, which is amazing about the vertical integration of the business.

</details>

**Ali Masa**: 但后来当我们开始推出其他金融产品时，我们意识到这对客户来说是一个非常重大的决定，对吧？他们通常需要三到四个月才能下定决心买车、获得贷款或获得个人贷款——我们也提供大额个人贷款。所以如果你在这个过程中了解你的客户，让这个过程对他们变得容易，那么你的转化率和留存率指标就会开始飙升。这不仅仅是交易，而是个性化地理解每个客户，并在他们准备好时促成转化，对利率、风险、贷款最高额度进行非常深度的个性化——以对整个投资组合有意义的方式，显然是针对风险水平优化的，可能还要考虑客户正在获得的其他报价。

<details>
<summary>Original English</summary>

**[Ali Masa]**: But then like when we started launching other financial products, we realized that this is a very important decision for the customer, right? Like they usually take three to four months to make up their mind and buying a car and getting a loan or getting a personal loan like a large personal loan that we also um do. So if you get to know your customer throughout this process and make the process easy for them, then just your conversion and retention metrics start going through the roof. It's not just the transaction is understanding each customer personally and get them to convert when they're ready with a very deep personalization of the interest rate, the risk, the max amount of the loan. In a way that makes sense for the portfolio as a whole obviously but that's optimized to the risk level and probably the other offers that the customer is getting.

</details>

### AI CEO实验

**主持人**: 然后也许给我们举个例子——你知道，评估一直是一个非常热门的话题。你一开始就提到了。有没有一个很难设计的评估领域，或者一个你不得不花费额外时间的领域，考虑到有真实的资金和个人身份信息（PII）风险？

<details>
<summary>Original English</summary>

**[Host]**: And then maybe give us just to be um you know evals are always a very hot topic. You kind of led with that. What is a like what is an example of maybe a hard to design area for evals or one where you had to spend extra amount of time with just given the fact that like there's real money PII at risk.

</details>

**Ali Masa**: 是的。当我们决定围绕AI重新设计公司时，你会问这个问题：好吧，AI能做这份工作吗？甚至是CEO的工作，或者领导层的工作？诚实的回答可能是能。在2035年，按照改进的速度，它将能够做到。所以我们说，好吧，让我们现在就试试。让我们尝试构建一个AI CEO。于是我们在墨西哥划出了一个城市。那就是Guavaka。我们把一个智能体放在我们的一个harness中作为CEO，它开始学习，开始做决策，并对这些决策进行评估。它现在才运行了六周。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yeah. So when we decided to redesign the company around AI, you ask the question, okay, is AI going to be able to do this job like even the CEO job or jobs where the leadership is? And the answer honestly is probably yes. Like in 2035 with a rate of improvement, it will be able to do. So we said, okay, let's try it now. Let's try and build an AI CEO. So we carved out a city in Mexico. It's Guavaka. And we put like an agent in one of our harnesses as a CEO and it starts learning and it starts making decisions and evaluating on those decisions and it's only been running for six weeks now.

</details>

**主持人**: 第一个月的目标是将Guavaka的利润翻倍。

<details>
<summary>Original English</summary>

**[Host]**: The goal of the first month was to double the profits of Guavaka.

</details>

**Ali Masa**: 它没有达到，但达到了1.5倍——利润增加了50%。仅仅通过管理这个城市，这太疯狂了，太惊人了。而且它是CEO——人们说那是AI最后应该取代的工作，但实际上并非如此。这是怎么发生的？它就像一个非常聪明的人——像菲尔兹奖得主级别的聪明——深入每一个数字、每一个客户，做出完美的预测，并微观管理每天需要执行的每一件事以达到计划。所以它真的会给Guavaka的所有体力劳动者发送消息，告诉他们当天的计划，并要求他们发回语音笔记以了解他们的进展。结果客户满意度增长了。我们的库存更好了。我们周转得更好，融资渗透率更高。每一个KPI都开始改善。所以这非常酷，非常令人兴奋。

<details>
<summary>Original English</summary>

**[Ali Masa]**: It didn't reach it but it was 1.5x like 50% more profits. Just like managing the city which is crazy right it's amazing and it's the CEO like people were like that was the last job AI was supposed to take and no it isn't really. And how did this happen and it's like uh very smart person like Fields Medal level smart like going into every single number every single customer making the perfect forecast and going to micromanage every single things that needs to be executed every day to reach a plan. So he'll literally send messages to all the physical workers in Guavaka with their plans for the day and ask them to send voice notes back to know their progress. So customer satisfaction grew. Uh we got a better inventory. We rotated better, better financing penetration. Like every KPI started to improve. So, it's super cool. It's super exciting.

</details>

**Ali Masa**: 那么，哪些工作我们仍然在培训和雇佣人类？那些与物理世界相关的工作。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Now, what are the jobs where we think uh we're still like training and hiring humans? Those are related to the physical world.

</details>

**Ali Masa**: 当我们谈到机械师时，Kavak在墨西哥大约有800名机械师。有很多灵巧性和感官是极难替代的。所以在那里，我们也用完全相同的、正在扩展的harness构建了这些智能体，机械师们有一个"搭档"（sidekick）。我之前告诉过你们，这就像电影《料理鼠王》——那只实际上是厨师的老鼠与人类合作。有点像那样。所以它是一个搭档。我们叫它El Mike。它告诉他们如何检查汽车，给他们提示，向他们展示方法。检查质量再次飙升。我们检查得更快，修理得更快，成本更低。但最重要的是，我们交付了更高质量的汽车。自推出以来，保修成本下降了大约20%到26%，客户满意度再次上升。所以关键在于：你会如何从零开始设计你的组织？用丰富、廉价、超级智能的AI，然后就去构建它。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So, when we talk about mechanics, Kavak has around I think in Mexico around 800 uh mechanics. There's lots of dexterity and senses that's super hard to substitute. So there we also build these agents with the exact same harness that's scaling and the mechanics have the sidekick. Um I was telling you guys earlier it's like the movie Ratatouille like the mouse that's actually a chef collaborating with a human. It's kind of like that. So it's a sidekick. We call it El Mike. And it tells them how to inspect a car and gives them tips and shows them the way to do it. And the quality of inspections again went through the roof. We're inspecting faster. We're repairing faster. It's cheaper. But most importantly, we're delivering higher quality cars. Um warranties came down around like 20 26% since we launched and customer satisfaction again went up. So it's about this like how would you design your organization from scratch? Uh with abundant super intelligence that's cheap and just go build it.

</details>

### 未来组织与Jedi Academy

**主持人**: 现在，这是一个很好的过渡到硅谷当前的一个关键话题——你知道，有很多人担心未来的组织会是什么样子，以及人类将扮演的角色。是的，我想你稍微触及了这一点。所以很想听听你们是怎么想的。

<details>
<summary>Original English</summary>

**[Host]**: Now, this is a good segue to a key topic right now in Silicon Valley where you know there's a lot of people worried about how the organizations of the future are going to look like um and the role that humans are going to play. Yes. In this and I think you touched a little bit on that. So would love to hear yeah like how you guys are thinking about that.

</details>

**Ali Masa**: 是的，关于组织。完全正确。我们三年前非常认真地对待这个问题，事实是，每个人的工作都会改变。我们几年前做的事情，可能会被AI智能体做得更好，对吧？那么这意味着什么？我们需要培训每个人。所以我们在Kavak内部启动了一个名为"绝地学院"（Jedi Academy）的项目，Kavak的任何人——从CEO到AI工程师到机械师——都可以参加。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. And the organizations. Yeah, totally. So, um we took that question very seriously three years ago and the truth is that everyone's job will change. So, and what we were doing a couple of years ago will probably be performed better by an AI agent, right? So, what does this mean? We need to train everyone. So, we launched a program inside Kavak that's called the Jedi Academy where anyone from Kavak like from the CEO to mechanics.

</details>

**主持人**: 是的。这太棒了，从CEO到AI工程师到机械师都去学院。这非常难，我领导过。

<details>
<summary>Original English</summary>

**[Host]**: to Yeah. And it's awesome like from the CEO to like AI engineers to mechanics like going to the academy. It's super hard like I I've led

</details>

**Ali Masa**: 我自己领导过。

<details>
<summary>Original English</summary>

**[Ali Masa]**: I led them myself.

</details>

**主持人**: 你设计了项目。

<details>
<summary>Original English</summary>

**[Host]**: You designed the program.

</details>

**Ali Masa**: 我设计了项目。

<details>
<summary>Original English</summary>

**[Ali Masa]**: I designed the program.

</details>

**主持人**: 但不断在更新。

<details>
<summary>Original English</summary>

**[Host]**: but constantly

</details>

**Ali Masa**: 不断更新，因为你需要升级项目，因为一切变化太快了。而且你不能把这些人送到外面去，比如去斯坦福学习这个，因为这是新东西，对吧？所以我们培训每个人，六周后，他们就把最先进的AI智能体部署到生产环境。有机械师、财务人员、工程师——每个人都能做到。这产生的结果是，也许这个人不会成为AI工程师——有些人已经成为了——但他们知道如何与这项新技术协作，对吧？所以我们看待它的方式是：伙计们，没有回头路了。这就是Kavak前进的方向，这就是公司未来的样子。这些是对工程团队、财务团队、产品团队的改变。这就是将要改变的东西。你有选择去培训并获得在新现实中、在新世界中表现的技能。或者，如果这不适合你，也许离开Kavak，但这就是我们要走的路。

<details>
<summary>Original English</summary>

**[Ali Masa]**: constantly because you need to be upgrading the program because everything's changing so fast and there's like you can't send these people like outside to Stanford to learn this because like it's new stuff right so we train everyone and after six weeks they launch state-of-the-art AI agents to production and it's mechanics and finance guys and engineers is like everyone can do it and what this generated is maybe this person won't become an AI engineer some of them have but they know how to collaborate with this new technology right so the way we looked about it was guys there's no way back like this is the way Kavak is going this is the way the company will look like these are the changes for the engineering team the finance team the product team like this is what's going to change. You have the choice to like train and get the skills to perform in this new reality, in this new world. Um, or maybe leave Kavak if this is not for you, but this is the way we're going.

</details>

**Ali Masa**: 而且效果很好。我们加强了文化。每个人都非常兴奋。人们真的知道如何构建这些智能体系统。然后如果你现在看Kavak，任何流程实际上都是智能体和人类的协作。有时智能体是人类的老板，有时人类在设计智能体。但我认为我们真的成功地构建了这一点并改变了这一点。这是通过这样一个理念实现的：我们需要每天学习，事情将继续变化，保持相关性的唯一方法是每个月或每几个月升级你的技能。

<details>
<summary>Original English</summary>

**[Ali Masa]**: And it was great like we strengthened the culture. Everyone was super excited. Um, people really know how to build this agentic systems. And then if you look at Kavak now any process it's really a collaboration of agents and humans and sometimes like agents are the bosses of humans and sometimes humans are designing the agents but I think we managed to really build this and change this and it's through this idea that we need to be learning every day and things will continue to change and the only way to continue being relevant is to upgrade your skills uh every month or every couple of months.

</details>

**主持人**: 但你们有，或者说曾经有，你知道，数千名员工，现在智能体做大部分事情。那么Kavak的组织结构是什么样的？中层管理的概念还存在吗？你们的组织看起来像什么？

<details>
<summary>Original English</summary>

**[Host]**: But you do have or did have you know thousands of people now agents do most things. So like what is the org structure of Kavak? Like does the middle management concept even exist anymore? Like what does your org look like?

</details>

**Ali Masa**: 对吧？现在看起来的样子是非常扁平化的团队，非常资深的团队，超级被授权。如果你看一个团队，你会有工程、AI、运营，一切。他们要么在构建智能体，要么在为智能体工作，要么在物理世界中面对客户。我们组织的大部分看起来都是这样。所以它真的是围绕未来组织会是什么样子的理念，围绕AI，真正利用这项新技术来构建的。显然，这需要大量的再培训，因为在2023年或2022年，没有人构建智能体，没有人帮助智能体或听从智能体的指令。而且你服务物理世界或客户的方式，与智能体告诉你做什么或帮助你更好地完成工作是不同的。所以这与我们两年前的结构完全不同。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Right? So the way it looks like now is very flat teams, very senior teams, super empowered. If you look at a team, you'll have engineering, AI, like operations, like everything. And they're either building the agents, working for the agents, or being in the physical world in front of the customer. Like most of our organization looks like that. So, so it's really built around the idea of how organizations will look like in the future and around AI and really harnessing this new technology. Obviously, this required lots of retraining because in 2023 or 2022, no one was building agents, no one was helping agents or taking orders from agents. And the way you cater to the physical world or the customers was in a different way than if an agent's telling you what to do or helping you make your job uh better. So it's a completely different structure than we had just two years ago.

</details>

**主持人**: 是的。解释一下——我们之前谈过——为智能体工作是什么样子的。我想你描述的方式是，你知道，一个智能体系统，然后有时当它失败时，就像"哦，那被踢到某种人类队列里了"，对吧？但那样就丢失了。那么你们是如何把它整合起来的？

<details>
<summary>Original English</summary>

**[Host]**: Yeah. Explain um we talked about this before what working for the agents look like. Like I think the way you described it was you know agentic system and then sometimes when it fails it's like oh that's kicked out to kind of a human queue right but then that's lost. And so how have you brought that together?

</details>

**Ali Masa**: 所以我们看到现在生产环境中大多数智能体系统——大规模智能体系统——通常如果智能体碰壁了或无法再执行，它会把这个案例或这个客户发送给二级支持，然后忘记它。这并不真正有效，因为你没有闭环。所以你无法生成数据来训练智能体做得更好。现在有效的是，我们有一个智能体，它专注于每一个客户——数以百万计的这样的智能体。它们可以访问每一个API、每一项技能。我们有智能体构建那些——人类为它们构建那些技能。然后如果智能体碰壁了或取消了某些东西，它会调用这个API说"我需要帮助"。而在另一边，不是智能体或软件，是一个人类在帮助它们。但如果你在组织架构图上映射出来，实际上是人类团队拥有一个智能体。我得到了更好的结果。这非常清晰，合情合理。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So like the we see human in the loops and most of these agentic systems in production right now like large scale agentic systems usually if an agent hits a wall or can't perform anymore it'll like send this case or this customer to a tier 2 support and forget about it. That doesn't really work because you don't close the loops. So you don't generate the data to train the agent to do this better. What works right now is we have an agent that's obsessed with each of the customers like millions of this. They have access to every single API, every single skill like and we have humans building those skills for them. And then if an agent hits a wall or cancels something, it'll call this API saying I need help. And on the other side, it's not an agent or software, it's a human helping them out. But if you map this out in an org chart, it's really human teams that have an agent. I'm getting better results. It's super clear like it makes sense.

</details>

### 给领导者的建议

**主持人**: 这实际上是一个完美的过渡。我知道你收到了很多大型机构领导者的咨询。所以也许这会为你省去很多电话，但我认为理性地讲，许多公司领导者直觉上理解这一点。但通过他们的组织部署AI仍然非常困难。模型已经足够好了，你知道这是一个组织问题，一个心理问题。你有什么建议，或者你看到了什么？

<details>
<summary>Original English</summary>

**[Host]**: That's actually a perfect segue. I know you get lots of leaders at larger institutions inbounding to you. So maybe this will save you many phone calls, but I think rationally many leaders of companies intuitively understand this. It is very hard still to deploy AI through their organization. Like the models are good enough you know that it's an org problem it's a psychology problem like what advice do you have or what have you seen?

</details>

**Ali Masa**: 我认为有两件事。第一，它必须是自上而下的，因为如果你只是获得采纳，它不会走远，因为很难为人们生成这种品味或策略，让他们自下而上地决定构建什么、不构建什么，并提出对公司有效的东西。所以转型必须是自上而下的，领导者需要采纳，领导者必须有一个非常清晰的计划，明确要构建什么。我见过太多公司，就像"哦，我们在做黑客马拉松，人们提出用例，我们赞助其中一些用例"。那行不通。而是要非常清楚公司在三到五年后会是什么样子，然后开始构建那个样子，并在引导你的队伍走向那个目标时非常垂直。一支军队如果每个人都对战略和战术提出想法，然后上战场随心所欲，是不会真正有效的。你需要一个非常清晰的战略，这就是我们现在需要的。这是一个转型阶段。

<details>
<summary>Original English</summary>

**[Ali Masa]**: I think it's two things uh the first is it has to be top down because of this like if you just get adoption it won't go anywhere because it's hard to generate this taste or strategy for people to bottom up decide what to build and what not and come up with something that works for the company. So the transformation has to be top down and leaders need to adopt and leaders have to have a very clear plan on what to build. I've seen so many companies it's just like oh like we're doing a hackathon people are coming up with use cases. We're sponsoring some of these use cases. That doesn't work. It's like be very clear on what the company will look like in three or five years and then start building that and be like very vertical in guiding your troops towards that. Like an army doesn't really work if everyone comes up with ideas on the strategy and tactics and goes to the battlefield and like does whatever they want. Like you need a very clear strategy and that's what we need now. It's a like transformation stage.

</details>

**Ali Masa**: 第二件事是，你需要衡量真正重要的东西，那就是评估，但也是正确的评估。所以我看到很多公司现在花费巨额资金，他们说"好吧，我获得了采纳，我现在只是在token上花费数亿美元"。那token的质量呢？所以我这里有一个框架也很有用。第三层token——最有价值的是那些智能体，你可以获得每个特定token的ROI，我现在就能做到。这对我来说是个好消息，因为我在增长，而且我知道每个token的ROI，因为它流向执行组织工作的智能体，对吧？这些是最好的token。第二层token是你可以间接衡量的东西。我是否看到开发者在代码库中？我至少可以间接评估这些token的价值，然后把那些推向生产。第一层——大多数公司所在的位置——是人们只是在用插件代码或ChatGPT或Copilot或其他什么。那些发生了什么？我不知道。所以这不仅仅是采纳的问题。真正重要的是有一个非常清晰的愿景，然后衡量你花费的每个token是否为你带来那些收益，然后从那里迭代、迭代、再迭代。

<details>
<summary>Original English</summary>

**[Ali Masa]**: The second one is you need to measure what really matters and it's evals but it's also the right evals. So I see a lot of companies spending now huge amounts and they say okay I got adoption I'm just spending like hundreds of millions of dollars in tokens now. What about that like there's quality in the tokens. So have a framework here that's also useful like tier three tokens the most valuable are this agents where you can get the ROI of each specific token and I can do that now. That's great news for me because I'm growing and because I know the ROI of each token because it goes to agents that are performing the job of the organization. Right? These are the best tokens. Yeah, tier two tokens are things that you can measure indirectly. Do I see devs in the codebase and I can evaluate the value of these tokens at least indirectly and then push those to productions. Tier one when most companies are is people are just using plug code or ChatGPT or Copilot or whatever. What happens with those? I have no idea. So it's not just about adoption. It's really about having a very clear vision and then measuring that each token you spend is bringing you those benefits and just iterate iterate iterate from there.

</details>

### 每客户智能体架构

**主持人**: 我想深入探讨一下我们之前稍微触及的话题，但我认为值得深入探讨，因为也许最雄心勃勃的收听此节目的公司会决定效仿，那就是你们决定为每个客户构建一个智能体，而不是为每个任务，然后在这个过程中发现每个这样的智能体都需要自己的微型虚拟机。所以也许带我们了解一下那些决策、那个架构。

<details>
<summary>Original English</summary>

**[Host]**: And I want to uh and we touched on this a little bit, but I think it's worth a dive as um maybe the most ambitious companies listening to this will decide to follow suit, which is you decided to build an agent per customer versus per task and then discovered along the way that each one of those agents needs its own micro virtual machine. So maybe kind of walk us through those decisions that architecture.

</details>

**Ali Masa**: 是的。我认为我们现在看到了这些结果，但这是一个非常冒险的赌注，因为人们通常从工作流开始。如果我能给每个人建议：不要构建智能体工作流到图或函数或目标。我们构建了那些——这些是多智能体系统，可以为复杂目标执行整个功能，就像我告诉你的那些：卖车你需要做融资、购买、推荐等等。我们在12月有成千上万、数以万计的这些智能体在规模上运行业务。但后来Opus 4.5出来了，我意识到这不再是正确的范式了。现在的智能不再需要图和多智能体协作工作和harness，因为它会约束这种智能水平。所以我们决定摧毁我们两年来一直在构建的一切——那些行之有效的、带我们走向盈利的、带给我们惊人增长的东西——然后重新开始，用一个我们认为稳健、可扩展、能利用递归自我改进或每个月出来的更新、更智能模型的harness。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. And I think we're seeing these results now but it was a really risky bet because people usually go from workflows. Like if I could advise everyone don't build agentic workflows to graphs or functions or objectives and we built that that these are multi-agent systems that can perform a whole function for a complex goals like the ones I told that to sell a car you need to do financing, purchasing like recommendations, uh, etc. And we had thousands like tens of thousands of these agents working at scale running the business back in December. But then Opus 4.5 came out and I realized like this isn't the right paradigm anymore. Like the intelligence now doesn't need like the graph and the multi-agent lattis work and harness because it will constraint this level of intelligence. So we decided to like destroy everything we had been building for two years that was working that brought us to profitability that brought us amazing growth and start over with a harness that we thought would be robust and scalable and leverage recursive self-improvement or new models more intelligent models coming out every month.

</details>

**Ali Masa**: 所以这看起来是这样的：一个虚拟机，里面有一个智能体，可以访问记忆和评估，以及CLI，在那里它们可以访问我公司里的每一个工具和每一个API，还有长期目标。我每天实例化数十万个这样的智能体，带着长期目标，比如最大化终身价值。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So the way this looks like it's a virtual machine with an agent with access to memory and evals and the CLI where they can access every tool and every API in my company and the long-term goal and I instantiate hundreds of thousands of these each day with long-term goals like maximizing the lifetime value.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Ali Masa**: 自我改进的组织。

<details>
<summary>Original English</summary>

**[Ali Masa]**: The self-improving organization.

</details>

**主持人**: 正是如此。自我改进的组织。我认为人们现在非常痴迷于RSI（递归自我改进），这将改进模型。但如果你这样看，人类过去4000年的经济价值是由组织交付的，而不是由个人。所以你想要自我改进并参与那个循环的，是能够交付更多经济价值的组织，对吧？所以这就是我认为公司将开始关注的循环，因为如果你让那个循环运转起来，它是一个真正自我改进的组织，利用我们每隔几天就得到的更新模型和更好的智能，那么你就达到了指数级——不仅在智能方面，而且在你能作为公司产生的价值方面。所以这真的很令人兴奋。这就是我们正在努力的方向。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Exactly. The self-improving organization. And I think people are super obsessed with RSI now and this will improve the models. But if you look at it this way, economic value in humanity for the past 4,000 years has been delivered by organization, not by individuals. So what you want to self-improve and to engage in that loop is the organization that can deliver more economic value. Right? So that's the loop that I think companies will start to focus on because if you get that loop working and it's an organization that is really self-improving and harnessing the newer models and the better intelligence that we're getting every couple of days now uh then like you hit the exponential not just in intelligence but in the value uh that you can generate as a company. So so that's really exciting. That's what we're working on.

</details>

### 创造性破坏

**主持人**: 你提到，由于采用AI的所有挑战，你看到了最大的机会在于新的公司以这种新方式成立，然后颠覆市场。你想谈谈这个吗？

<details>
<summary>Original English</summary>

**[Host]**: You mentioned that because of all the challenges on adopting AI, you saw the biggest opportunity on net new companies being formed working on this new way and then disrupting markets like you want to talk a little bit about that?

</details>

**Ali Masa**: 是的。经济学中有一个概念叫做"创造性破坏"，来自约瑟夫·熊彼特。它说的是，创新冲击经济的方式不是通过公司采用新技术，而是通过保持原样的公司和采用新技术的现有企业摧毁旧公司。这在短期内会摧毁经济中的价值，但从长期来看对每个人都有利，因为这些新的、更高效、更有效的公司将为整个经济提供更好的产品和服务。这在过去发生过，比如工业革命，而且总是会发生。这对今天的创业者和人们来说是一个巨大的机会，因为深度采用AI很难。今天一个CEO，尤其是大公司或上市公司的CEO，真的很难去说："嘿，我把一切都押在AI上。公司必须变成这个样子。我要摧毁并重建我过去40年建立的一切，成为一家AI原生公司。"有多少CEO会在一个规模化的公司里这样做？所以当他们采用时，新的公司可以成立，围绕AI的优势构建，然后接管，为大众带来新的产品和服务。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Yes. Um there's this concept in economics about creative destruction from Joseph Schumpeter and what it says is that the way innovation hits the economy isn't by companies adopting the new technology but by companies remaining the way they were and incumbents with the new technology destroying the old companies. So this destroys value in the short term in the economy but in the long term it's better for everyone because this new more efficient more effective companies will provide better products and services for the economy as a whole and this has happened in the past like industrial revolutions and this has always happened and this a great opportunity for entrepreneurs and people today because it's hard to adopt AI deeply. It's really hard for a CEO today, especially of a large company or public company, to go and say, "Hey, like I'm betting everything on AI. The company has to look this way. I'll destroy and rebuild everything I've been building for the past 40 years to become an AI native company." Like how many CEOs will do that in a company at scale. So while they adopt, new companies can be formed that are built around the strengths of AI and take over and bring new products and services to the masses.

</details>

**Ali Masa**: 这在以前发生过，比如电力。这是我总是给我团队讲的故事。福特生产线的技术在1879年和1881年就开发出来了。爱迪生在纽约然后伦敦开始商业化电力，他发明了一种极其高效的发电机。所以你本可以在福特之前40年建造福特的工厂。技术就在那里，一切都在那里。但人们采用电力和福特发电机的方式是："好吧，我要保留我的四层工厂、传动轴和皮带，只是把我的煤发动机换成电动发动机。"这会给你带来好处，是的，但只有6%的效率提升。需要做的是摧毁那个工厂，把它建在平坦的地面上，不在纽约市中心，而是在康涅狄格州或新泽西州，围绕小型发电机和电力重新设计你的整个工厂。然后你得到的是3倍的生产力提升，这支撑了美国在20世纪的发展。计算机出现时同样的事情再次发生。今天同样的事情正在再次发生。人们想要采用它，但他们不愿意重新设计整个公司，他们只是表面地采用它。最终，那只会给你6%或10%的改进，而不是10倍的改进。这就像是工业规模的创新者困境。

<details>
<summary>Original English</summary>

**[Ali Masa]**: And um this has happened before like this happened with electricity. This is a story I always tell my team. The technologies for Ford's production line were developed in 1879 and 1881. Edison started commercializing electricity in New York and then London and he invented a dynamo that was extremely efficient. So you could have built Ford's factory 40 years before Ford. The technology was there, everything was there. But the way people adopted electricity and Ford's dynamo was okay, I'm gonna leave my factory like four floors, shafts and belts and just change my coal engine for an electric engine. And this will bring you benefits, yes, but like 6% efficiency. What needed to be done was like to destroy that factory, build it in a flat surface, not in the center of New York, but in Connecticut or New Jersey, and redesign your whole factory around small dynamos and electricity. And then you get like the 3x improvement in productivity that powered the US during the 20th century. And the same happened again with a computer. And the same is happening again today. People want to adopt it, but they're not willing to redesign the whole company and they just adopt it superficially. And in the end, that'll give you a 6% or a 10% improvement, not a 10x improvement. And it's like the innovator's dilemma at an industrial scale. Again.

</details>

### 给创始人的建议

**主持人**: 我想你刚刚为任何未来的创始人做了一个惊人的论证：是时候去构建了。

<details>
<summary>Original English</summary>

**[Host]**: I think you've just made an amazing case for any future founders out there that it's time to build.

</details>

**Ali Masa**: 是时候去构建了。也许一个很好的结束方式是，你知道，你已经建立并扩展了自己的公司，你现在已经把Kavak完全智能体化了。你对可能正在收听节目的未来创始人或首次创业者有什么建议？

<details>
<summary>Original English</summary>

**[Ali Masa]**: It's time to build. And maybe a great place to end is, you know, you've built and scaled your own company, you've now turned Kavak fully agentic, like what advice do you have to future founders or first-time founders that might be listening?

</details>

**Ali Masa**: 这是人类历史上最激动人心的时刻。我相信我们正生活在人类历史上最激动人心的时刻，这是成为创始人的最激动人心的时刻，因为这是第一次任何人都能以几乎免费或每月20美元的价格获得世界上最强大的工具和智能。所以，字面上，构建工具对人们的民主化在人类历史上从未如此。有太多问题需要解决，有一个新的现实需要围绕这个新范式来构建。所以，大胆去做吧，但要深入去做。想象一下围绕AI的未来会是什么样子。

<details>
<summary>Original English</summary>

**[Ali Masa]**: So, this is the most exciting time in human history. I believe that we're living in the most exciting time in human history and it's the most exciting time to be a founder because it's the first time that anyone has access to the most powerful tools and intelligence in the world like for almost for free or for $20 a month. So, literally the democratization of the tools for people to build has never been this way in human history and there's so much problems to be solved and a new reality to be built around this new paradigm. So say like just go for it but go for it deep like imagine what the future around AI will look like.

</details>

**主持人**: 这甚至不是指数级的。只要画一条线性趋势线。如果事情继续这样发展——AI以线性规模持续变好——就为那个未来构建，你会想出精彩的想法，为世界带来大量价值。

<details>
<summary>Original English</summary>

**[Host]**: It's just a uh it's not even an exponential. Just map a trend that's linear. If things keeps getting like AI keeps getting better at a linear scale and just build for that and you'll come up with wonderful ideas that will like bring a lot of value to the world.

</details>

**主持人**: 太棒了。Ali，感谢你加入我们。

<details>
<summary>Original English</summary>

**[Host]**: Amazing. Ali, thank you for joining us.

</details>

**Ali Masa**: 感谢邀请我。

<details>
<summary>Original English</summary>

**[Ali Masa]**: Thanks for having me.

</details>