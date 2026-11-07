---
author: EO
date: '2026-05-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=sdN7zw_XbuU
speaker: EO
tags:
  - ai-insurance
  - regulatory-moat
  - infrastructure-rebuild
  - startup-strategy
  - fintech-disruption
title: 重构万亿级产业底座：Corgi 如何利用 AI 深度改造传统保险业
summary: 本文深度解析了 AI 保险科技公司 Corgi 的创业历程与战略思维。创始人 Nico Laqua 与 Emily Yuan 分享了他们如何从厌恶平庸工作到挑战高度监管的保险行业。核心洞察在于：与其做传统的保险分销商（Broker），不如通过 AI 原生技术成为底层的持牌承运商（Carrier）。尽管这条道路充满监管挑战且耗资巨大，但 Corgi 通过数年的硬核执行，建立了难以复制的基础设施护城河，实现了数亿美元的 ARR 增长。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Nico Laqua
  - Emily Yuan
companies_orgs:
  - Corgi
  - Y Combinator
  - Stanford
products_models: []
media_books: []
status: evergreen
---
### 创业缘起：逃离平庸与“最高杠杆”的雄心

Corgi 的两位创始人 **Nico Laqua**（CEO）与 **Emily Yuan**（COO）的相识始于斯坦福大学的创业社区。Nico 早期曾尝试开发过针对大学社团的 App，而 Emily 凭借在斯坦福创业俱乐部的敏锐洞察，为其提供了极度详尽的反馈。在此之前，Nico 曾创立过游戏公司 **Basket**，尽管公司运营良好，但他逐渐意识到，如果仅仅是做一些“有趣但缺乏社会影响力”的产品，很难吸引顶尖人才和投资。

他们的核心理念是追求 **最高杠杆**（Highest Leverage: 指以最小投入产生最大社会改变的路径）。对于年轻的创业者，Nico 给出的建议往往反直觉：与其为了提高成功率而缩小想法的规模，不如去挑战最宏大、最困难的版本。因为平庸的项目往往竞争激烈，而真正雄心勃勃的任务反而会吸引最聪明的头脑加入，并获得投资者的青睐。

<details>
<summary>Original English Source</summary>

My name is Nico. I'm the CEO of Corgi. Corgi is an AI insurance company for technology startup and we'll end this year at several hundred million in ARR. I grew up in San Diego, California. In high school, I had a couple jobs. Anyone who works jobs while they're in high school knows that they suck. You have like a boss that's like an idiot that's like telling you all sorts of like things that are just like wasting your time. I think at some point I I just kind of decided that I wanted to do something that was like big and important with my life. Emily at that time, she was really interested in startups and she was running one of Stanford's entrepreneurship clubs and I wanted her to test out this app and Emily came back with like a Figma page with like a hundred comments about the app. 

Nico is very good at identifying good opportunities and I think that actually complements my skill set. I'm very good at helping make sure that we can figure out how to like get all these different things done. Basket, they make a lot of really great games. I got that company to the destination that that I wanted to get it to. I spent over four years there, but it didn't feel like a very impactful company. It's a very different type of company than what Nico and I really wanted to spend the next like 10 years building. We want to do the most like biggest most ambitious thing possible. Often times a young startup founder try to make products that you yourself would use which is normally pretty good advice but the problem is that problems that they they try to solve are often not as big as they could be and I think a lot of people think that if they take a really big idea and kind of scale it down to something very small that that makes it more likely to succeed but actually I think that people should do the opposite and think of the most ambitious version because if you're doing that then suddenly a lot of really smart people will want to join you on your mission.
</details>

### 保险业现状：传真机时代的万亿级“遗留系统”

在创办 Corgi 的过程中，两位创始人发现了 **保险行业**（Insurance: 涉及风险评估、资金管理与理赔的金融服务）这一巨大的机会。保险市场规模占 GDP 的 12%，几乎是软件市场的两倍。然而，这个行业极其守旧且低效：大公司往往成立于 40 年前甚至更久，其运营模式极度依赖中介（Broker），内部流程甚至还在使用传真机进行沟通。

Nico 分享了他上一家公司购买保险的糟糕经历：保费高达 6 万美元，比他本人的年薪还高，却需要数周时间通过电话沟通，且理赔响应极慢。这种 **监管壁垒**（Regulatory Barriers: 政府设定的准入门槛，如牌照、资本金要求等）让传统巨头变得傲慢自满，他们只懂得将新技术零散地插在陈旧的底层架构上，而从未考虑过彻底重构。

<details>
<summary>Original English Source</summary>

Historically, it's been very difficult for tech startups to get insurance. I mean, I had to get insurance for my last company and I remember the insurance policy was $60,000 and that's a lot of money to buy anything. But, you know, my experience was terrible. I had to call these brokers. I remember it took several weeks to get the policy, not answering my emails to them for like weeks and of course they never paid out anything. And it was just shocking like how slow the process is. We just looked at how everything was set up and we were like, "Wow, this is terrible." How do you have a hundred billion dollar company that runs like this? 

If you look at it as 12% of the GDP, it's about twice as big of a market category as software. But I think that all of the regulation around it and the huge regulatory barrier to entry coupled with the fact that most of these big insurance providers started 40 years ago or more, that's led to them being very comfortable, them being very complicit, them to continually worsening their product quality. It's actually a big advantage for us because we can come in with a brand slay and we can look at things and if something doesn't make sense, we can question like why is it being done this way and is there a better way of doing it?
</details>

### 战略转型：从“转售中间商”到“AI 承运商”的豪赌

Corgi 早期在 Y Combinator 孵化时，最初的定位是 **保险经纪人**（Broker: 仅作为中间商撮合交易）。虽然这种模式很快就产生了数万美元的收入，但 Nico 很快发现了致命伤：由于底层的 **保险承运商**（Carrier: 真正持有牌照、设计保险产品并承担赔付责任的金融机构）极度低效，作为前端的 Broker 无法真正改善用户体验，甚至不得不购买传真机来配合这些百亿级巨头的流程。

于是，他们做出了一个极具争议的决定：关闭正在赚钱的 Broker 业务，全力申请保险牌照，成为一家完整的 **AI 原生保险公司**。这意味着他们要从零开始，利用 AI 重新编写所有底层逻辑。这一转型导致 Corgi 在 YC 期间的表现并不出众，甚至错过了 Demo Day，并经历了一段长达数年、几近破产的艰苦期，最终筹集了约 8000 万美元的资金。

<details>
<summary>Original English Source</summary>

We applied to YC already licensed to be an insurance brokerage. Our idea there was to embed with contract management companies. We just wanted to be a broker and do the normal thing. Um that's what we started with and actually it was working pretty well. But in reality, what was happening was because they had to rely on these like really old traditional insurance carriers, it made it really hard for them to have a good product. It was really nasty to deal with the insurance carriers like making phone calls to them for every single policy. We had to get a fax machine and we were like sending faxes to them back and forth. 

There must be like a better insurance carrier out there. And through doing that, we realized that the problem wasn't like the website. It wasn't the tech. The problem was the actual underlying product, which is the insurance policy. So then we had to figure out like how do we actually go and be the company that is creating and has like control over the product. And the only way you can really do that is to become an insurance carrier. So we decided to shut down what we were doing which was working pretty well. We're building a new type of financial institution where we actually become these highly regulated financial entities and rebuild them from the ground up using AI. It ended up being a very long multi-year process where um our company almost ended on many many occasions. We had to to raise almost pre-revenue like $80 million.
</details>

### 护城河的构建：硬核执行与监管套利

Corgi 的竞争优势来自于其 **难以复制的基础设施**。Nico 强调，简单的转售（Reselling）无法改变世界。通过投入数年时间和数千万美元，Corgi 在监管极其严格的领域拿到了所有必要的牌照，并建立了一套完全由 AI 驱动的自动化运营体系。

团队展现了惊人的执行力：Nico 甚至直接住在办公室，团队成员大多在公司附近居住，确保 110% 的精力投入。这种 **硬核文化**（Hardcore Culture）与对法律文件的深度钻研，共同构成了一道极深的 **护城河**（Moat: 竞争对手难以跨越的壁垒）。一旦基础设施搭建完成，Corgi 几乎不再需要额外的营销投入，因为对于初创公司而言，它是市场上唯一快速、透明且好用的产品。

<details>
<summary>Original English Source</summary>

Nico actually lives in the office and a lot of our like team members just like live close to the office as well. That energy is something and that time they're able to spend on these problems is something that's really hard to to compete with. Regulation it's not like some like mysterious thing like they tell you like you can do XYZ and you can't do XYZ and you just make sure you follow the directions. Overall, I think regulation is something that that's pretty difficult and pretty challenging. But once we got our first set of licenses, our revenue started growing very quickly. 

Operating in regulated industries it's very difficult and is very capital intensive but once you're able to actually get the core infrastructure set up there's a lot that you can just build on top of it. It's a big moat that it's kind of hard for someone else to make like a corgi 2.0 because we had to spend so much time and so much money like getting the infrastructure set up. I don't think you can change the world if you're reselling someone else's product. So in our case, we decided to become the infrastructure and um it took us a lot longer and a lot more money than we thought it would, but in the end um I think it ended up working out.
</details>