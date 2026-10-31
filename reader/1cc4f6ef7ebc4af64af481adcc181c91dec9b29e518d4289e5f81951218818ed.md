---
author: AI Engineer
date: '2026-10-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=W4pnzOURwHQ
speaker: AI Engineer
tags:
  - insurance-claim
  - medical-claim
  - digital-transformation
  - evals
title: 医疗保险理赔中的技术变革与AI应用挑战
summary: 演讲介绍了医疗保险理赔领域的数字化现状与技术演进，指出行业仍受未完成的云迁移、传真及纸质表单等非标数据制约。结合理赔异常、诊断冲突及诉讼成本等复杂场景，提出需结合专用分类模型与评测基准，审慎推进AI应用。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Wisdocs
  - Artificial Analysis
products_models:
  - MLCR
media_books: []
status: evergreen
---
<!-- chunk 1/6 -->

[music]

>> 好的，感谢大家来参加今天最后一场研讨会。我是 Dennis。接下来我将向大家分享一些关于保险理赔数据的内容，以及它对全企业范围的 AI 项目能够发挥多么强大的作用。

<details><summary>Original English</summary>
>> All right, thank you for joining the last workshop of the day. So, I'm Dennis. I'll be sharing a little bit about insurance claims data and how powerful it can be for enterprise-wide AI programs.
</details>

那么，我们现在开始吧。

<details><summary>Original English</summary>
So, let's get started.
</details>

现场有谁是在保险行业工作的吗？

<details><summary>Original English</summary>
So, who here works in insurance?
</details>

有几个人。有谁是想从事保险工作的吗？

<details><summary>Original English</summary>
Few people. Who here wants to work in insurance?
</details>

好的，挺有意思的。有几个人。好的。

<details><summary>Original English</summary>
Okay, interesting. Few people. All right.
</details>

保险在我们经济中是一个非常有趣的行业，人们往往是机缘巧合进入其中，但它却支撑着我们生态系统中极其重要的一个环节。所以，我们接下来会稍微聊聊保险这个整体。

<details><summary>Original English</summary>
So, insurance is a very interesting sort of sector of our economy where people sort of find their way working there, but it powers such a important part of our ecosystem. So, we're going to talk a little bit about insurance as a whole.
</details>

最终，我们本次演讲将聚焦于我们总体上该如何改善大家的生活？因此，我们将聚焦于医疗理赔，改善理赔和患者的成效将是本次演讲的核心，我也会反复回到这一点上。我认为，在很多金融科技类或金融、保险相关的讨论中，有时候内容可能会变得有点过于以商业为中心。所以我始终希望大家能把注意力放在这个方面。

<details><summary>Original English</summary>
And we're ultimately going to focus this talk on how do we improve our lives in general? So, we'll focus on medical claims, we'll improve the claim and patient outcomes as a focus of this talk, and I'll keep bringing that back. I think often times in a lot of fintech sort of finance insurance discussions, sometimes things can get a little bit too business focused. So, I always want everybody to to focus on this aspect.
</details>

接下来做个自我介绍。我是 Dennis。我在 Wisdocs 领导 AI 项目。我们协助企业处理复杂的医疗理赔流程。我担任这个职位已经有两年了，从 2024 年以来，我们见证了巨大的变革。

<details><summary>Original English</summary>
So, a little bit about myself. I'm Dennis. I lead the AI program at Wisdocs. We help companies with their complex medical claim processing. Been with the role in in the role for 2 years now, and we've seen a huge amount of transformation since 2024.
</details>

大家可能看到过一些关于医疗保障以及整体保险领域的新闻报道。

<details><summary>Original English</summary>
So, you might have seen some of the news coverage in terms of medical coverage and insurance in general.
</details>

GLP-1 在我们经济和医疗卫生环境中掀起的整体变革，也改变了保险公司的定价方式。我们还看到，随着成本上升以及其他改变保险应对方式的因素，配偶保险以及更广泛的保险保障范围一直在持续演进。

<details><summary>Original English</summary>
The whole GLP-1 transformation in our economy, in our health care environment has changed how insurance is pricing things as well. We also see that spouse insurance and broadly insurance coverage has continued to evolve with increasing costs and other factors that change the the approach of insurance.
</details>

因此，本次演讲将围绕三个主要章节展开。第一部分是关于我们正在经历的技术变革。第二部分我会稍微深入谈谈保险领域的一些具体细节，做个简要介绍。随后我还会谈谈 AI 将如何帮助进一步改善保险机制和患者体验。

<details><summary>Original English</summary>
So, the talk is going to focus on three main chapters. The first one is on the technology transformation that we have. The second is I'll go a little bit into the insurance space in terms of some of the call it nitty-gritty, but sort of a a brief introduction there. And then also I'll talk about how AI is going to help make insurance and the patient experience even better.
</details>

### 技术变革

我们来聊聊技术变革。

<details><summary>Original English</summary>
Let's talk about technology transformation.
</details>

在座的各位在自己的工作中，无论是在较小型的初创公司还是大型企业工作，可能都已经在公司内部启动了某种形式的数字化转型。但问题在于，我们从未真正完成这项转型。AI 在 2023 年和 2024 年向我们袭来，但大多数公司既没有完成云迁移，也没有充分发挥大数据的潜力，更没有搭建好一个干净的数据湖，对吧？现场有谁拥有一个自己引以为豪的数据湖吗？

<details><summary>Original English</summary>
So, we all probably in our work have started some form of digital transformation within our companies, whether we work in smaller startups or with in larger enterprises. Now, the challenge with that is that we never finished this transformation. AI hit us in 2023 and 2024, but most companies have not finished their cloud migrations, have not finished leveraging big data to its full potential, have not deployed a clean data lake, right? Who here has a data lake they're proud of?
</details>

好的，非常非常少的人。甚至说，真的有可能拥有一个让自己引以为豪的数据湖吗，对吧？

<details><summary>Original English</summary>
All right. Very very few people. Is it even possible to have a data lake you're proud of, right?
</details>

除此之外，我们现在又面临着围绕 AI 的铺天盖地的炒作，而在我们真正能够部署实际应用之前，确实需要确保已经夯实了其他的先决条件。

<details><summary>Original English</summary>
And on top of that, we're now getting all this hype about AI, and we need to really make sure that we have the other prerequisites down before we can actually deploy real applications.
</details>

在保险以及许多其他行业中，纸质材料过去是处理业务的主要方式，对吧？处理一起医疗理赔时，你会收到厚厚的一叠纸。你要去整理它。桌上堆满了这些材料，大张大张的桌子都摆满了。你会用卡片插进某些部分来做标记。

<details><summary>Original English</summary>
So, in insurance and many other industries, paper was the big way of processing things, right? You'd get a stack of papers of going through a medical claim. You'd organize it. You'd have these giant tables full of them. You'd use cards to put in certain sections.
</details>

而这其实很难从单笔理赔之外获取任何信息，因为当所有东西都是纸质的时候，你该如何做跨理赔分析呢，对吧？你想放多少个文件夹都可以，但这非常困难。

<details><summary>Original English</summary>
And this is very difficult to actually get any anything outside of the claim itself, because how do you do cross-claim analysis when everything is paper, right? You could put as many folders as you want, but it's very difficult.
</details>

现在，我们依然没有脱离纸质时代。在世界各地，仍有相当多的业务在使用纸质文件，无论是在医生诊所、法务部门，还是在保险公司内部。因此，我们仍然没有完全跨过纸质阶段，但我们正在接近。

<details><summary>Original English</summary>
Now, we still have not exited the paper era. There are still a number of practices that they use paper around the world, whether it's in the doctor's office, in in legal departments, or within insurance companies themselves. So, we're still not over paper, but we're getting close.
</details>

谈到数字化，我们也依然没有告别传真机。传真市场仍在持续增长。全球规模已超过 70 亿美元，这总是让人感到惊讶。我在去年旧金山的 An Engineer 大会上的演讲中提到过这一点，至今情况仍未改变。传真依然在使用中。我们现在所做的，是在数字系统中拼凑兼容传真，使其能以相对整洁的格式转换，但这依然没有解决我们在医疗卫生系统中实际如何进行信息交换的问题。

<details><summary>Original English</summary>
Now, in terms of digitizing, we are still also not over the fax machine. The The fax market is continuing to grow. It's over $7 billion globally, which is always surprising. I referenced this in my talk at An Engineer SF last year and it has not changed. Fax is still being used. Now, what we're doing now is we're jerry-rigging faxes into our digital systems where we can convert them in a fairly clean format, but it still does not solve the problem of how we actually exchange information in the health care system.
</details>

如果我们看看技术的采纳速度：电子健康档案（EHR），在 2008 年时采纳率仅为 8%。直到新冠疫情期间，我们才真正让 EHR 采纳率达到了 80% 多和 90% 多。而且，很多医院依然依靠纸质材料运转。

<details><summary>Original English</summary>
Now, if we think about how quickly technology has been adopted, EHRs, electronic health records, uh we're only at 8% adoption in 2008. And it only with the the COVID pandemic did we actually hit the '80s and '90s in EHR adoption. And again, many hospitals still run on paper.
</details>

所以，我们依然没有彻底走完这段数字化、数字化转型的历程，然而每个人却都想做 AI。

<details><summary>Original English</summary>
So, we're still not fully through this digitization, digital transformation era, and yet everybody wants to do AI.
</details>

如果我们看看人们在进行理赔处理时收到的表单类型，这里是来自三个大州的工伤赔偿示例表单。工伤赔偿指的是如果你在工作中受伤，你提交一份理赔申请，说明：“我在跌倒时伤到了手臂，或者我当时在开叉车，然后出了点问题。”

<details><summary>Original English</summary>
If we think about the types of forms people receive when when doing claims processing, these are some three sample forms from three large states for workers compensation. So, workers compensation is if you get hurt at work, you file a claim saying, "Hey, I hurt my arm falling down or I was driving a forklift and then something went wrong."
</details>

这些表单看起来没有一份是一样的，对吧？在美国的 50 个不同州中，通常就有 50 种不同类型的表单。它们要求填写的信息各不相同。它们并不标准化。

<details><summary>Original English</summary>
And none of these forms look the same, right? So, within 50 different states in the US, you have 50 different types of forms generally. They all ask for different information. They're not standardized.
</details>

它们在某种程度上算是标准化的，即收到的每一份同类表单格式一致，所以你可以在那里获得某种确定性，但即便如此，当中的信息也是不同的。因此，即便同在美国这一个国家，更不用说世界上任何其他国家了，我们记录信息的方式也不尽相同，而且这些版本有时还会变动。

<details><summary>Original English</summary>
They're fairly standardized in that every form that comes in looks the same, so you can have some determinism there, but even then the information is different. So, even as a country in the US, let alone any other country in the world, we don't capture information in the same way and these versions sometimes change as well.
</details>

谈到人们在保险领域所关心的，那就是赔付率，对吧？也就是你收取了多少保费，以及你赔付了多少金额？稍后我会进一步讲解这里的这些数字以及它们的含义，但总体而言，这就是推动机构底线业绩的因素，对吧？当你公布季度财报或年度财报时，你会着重强调你的赔付率是多少、你预测风险的能力有多强、你的核保能力有多高、你在欺诈管理方面做得如何、你在费用控制方面做得如何。

<details><summary>Original English</summary>
If we talk about what people [snorts] care about in the insurance space is a loss ratio, right? So, how many premiums are you collecting and how much money are you paying out? So, I'll talk a little bit more about the these numbers here and what they mean, but in general, this is what drives the bottom line of an organization, right? When you report a quarterly earnings or an annual earnings, you're going to be emphasizing what is your loss ratio, how well can you predict risk, how well can you underwrite, how how well are you managing fraud, how well are you managing your expenses.
</details>

因此企业都希望降低成本并赚取更多利润，对吧？这就是普遍的商业运作模式。如果看一看这里的几项统计数据，就我们在可保理赔上所需赔付的金额与所收保费的比例而言，我们通常大致徘徊在 50% 左右的赔付率。

<details><summary>Original English</summary>
And so companies want to keep costs down and make more money, right? That's just capitalism in general. Um and if we think about some of the statistics here, we we generally uh hover around the 50% um loss ratio here in terms of the amount of money we have to pay out for insurable claims uh compared to the premiums we get.
</details>

现在我介绍了所有这些背景信息，而到目前为止，在我的演讲中我只提过一次 AI。这非常重要，再次强调，要思考我们试图解决的问题，然后只在 AI 是合适方案时才选择它。

<details><summary>Original English</summary>
Now I'm I'm introducing all of these sort of pieces of context and I've only said AI once so far in my talk. And it's really important again to think about the problem that we're trying to solve and then only choose AI if it's the right solution.
</details>

如今要想获得恰当的 AI 解决方案，我们需要经历恰当程度的转型，对吧？我们脑海中需要有明确的目标。我们需要有一支能够切实说清楚我们想用 AI 做什么的团队。我们不能只是让人走上台不断空喊“AI、AI、AI”，对吧？我们需要合适的人员技能来切实完成这种转型，并且我们需要建立恰当的框架体系，无论是治理、安全、基础设施管理还是数据方面。

<details><summary>Original English</summary>
Now for AI uh to get proper AI solutions, we need to go through the right amount of transformation, right? We need to have the right goals in mind. We need to have a team that can actually articulate what we want to do with AI. We can't just have people get on stage and say AI AI AI, right? We need the right people skills to actually accomplish this transformation and we need the right frameworks in place, whether it's governance, security, infrastructure management, and data.
</details>

现在这里有一个问题。对于那些在企业环境中工作的人，如果提出申请，现场有谁能在一周内拿到一个数据库或一台虚拟机？

<details><summary>Original English</summary>
Now there's a question here. Um for those working at an enterprise context, who here could get a database or a VM within a week if they requested it?
</details>

好的。谁拿不到？

<details><summary>Original English</summary>
Okay. Who could not?
</details>

好的，这算是有进展了。现场有谁能在一周内将一个应用程序部署到生产环境？

<details><summary>Original English</summary>
Okay, that's progress. Who here could deploy an application to production in a week?
</details>

一个新的应用程序。

<details><summary>Original English</summary>
A new application.
</details>

好的。谁不能？

<details><summary>Original English</summary>
Okay. Who could not?
</details>

好的。所以我们仍然需要取得一些进展。谁能在一周内选定一家新的 AI 供应商？

<details><summary>Original English</summary>
Okay. So So we we still need some progress. Who can choose a new AI vendor in a week?
</details>

啊，看吧。没有人举手。

<details><summary>Original English</summary>
Ah, there we go. No hands.
</details>

没错。因此，我们走完所有这些不同流程依然需要时间。在数字化转型的环节上，它们固然比 10 年、20 年前要好，但许多公司依然受困于治理与安全环节。而且其中很多情况都与这里的这些因素有关。

<details><summary>Original English</summary>
Right. So it still takes time for us to go through all these different processes. Uh they're certainly better than they were 10, 20 years ago in the digital transformation component, but a lot of companies still get stuck in governance and security. And a lot of those have to do with with the factors here.
</details>

现场有谁曾被高管提出过类似这样的查询要求吗？“给我一份包含完美数据的数据集。”

<details><summary>Original English</summary>
Who here has been asked for some kind of query like this from an executive? Give me some data set that is perfect data.
</details>

对吧？有几个人 [笑声]，对吧？我们以前都见过这种情况。“嘿，你能帮我快速调出那份报告吗？”现在有了 AI 确实容易得多，但你必须假设这些数据本身是存在的，对吧？

<details><summary>Original English</summary>
Right? A [laughter] few people, right? We we we've seen this before. Hey, can you pull that report for me quickly? Um it's much easier now with AI, but you need to assume that that data exists, right?
</details>

那么，如果我们这里提出一个更复杂的查询，对吧？假设我们有一笔理赔，针对某位特定患者及其病症——在这个案例中是脚踝受伤——我们……

<details><summary>Original English</summary>
So, if we come up with a more complex query here, right? Uh let's say that we we have a claim and for a given patient and their condition, uh in this case, uh an ankle injury, we
</details>

<!-- chunk 2/6 -->

想确保我们能把他们分配给一位患者诊疗效果排在前 50% 的医生，对吧？是在某个近期的时间范围内。

现在，这个查询相当复杂，但如果你真能在自己的数据集上写出这个查询并拿到结果，对吧？我会感到非常惊叹，对吧？在企业环境中，数据是非常非常具有挑战性的。

所以，为了让我们获得这类结果并得到这些洞见，我们必须以一种非常明确的方式来构建我们的数据系统。

<details><summary>Original English</summary>want to make sure that we can assign them to a doctor who has top 50% tile uh patient outcomes, right? Within some recent time frame.

Now, this query is fairly complex, but if you could actually just write this query on your data set and get that result, right? I'd be amazed, right? Data is very very challenging in an enterprise environment.

So, for us to get these kind of outcomes and get these kinds of insights, we have to structure our data systems in a in a in a very well-defined way.</details>

### 医疗理赔与财产意外险

那么，我们来谈一谈医疗理赔。

总体上，我是根据 NAIC 的分类对保险进行了归类。我们有财产及意外伤害险，人寿、意外和健康险，以及更广泛的健康保险。我其实主要会讲财产及意外险，因为那里的理赔通常是最复杂的。

如果考虑 P&C，我主要做的是意外险方面。也就是汽车保险、各类责任险、一般责任险、产品责任险、工伤补偿险。另外还有整个财产险方面，那有它自己的一套复杂性。

但总体而言，按保费计算，这是一个 1 万亿美元的市场，对吧？而再保险又有它自己的形式。

<details><summary>Original English</summary>So, let's talk a little bit about about medical claims.

So, in general, I've grouped uh insurance based on the the NAIC uh classifications. We have property and casualty, life, accident, and health, and sort of broader health uh insurance. I'll actually be talking about property and casualty, since there the claims are typically the the most complex.

If you think about P&C, um I've mainly worked on the casualty side. So, uh auto uh insurance, uh various types of liability, general liability, product liability, workers' compensation. There's also the whole property side, uh which is its own uh set of complexities.

But, generally, this is a $1 trillion market, right? Uh based on on premiums, and reinsurance is its own kind of forms.</details>

那么，如果我们看这些蓝色的方框，其中很多都在处理复杂的医疗理赔。有人因为产品缺陷而受伤，有人遇到车祸，有人在工作中受伤。

现在，裁决一起理赔并给患者或索赔人做出答复需要很长时间。在最好的情况下，需要几周时间。在最坏的情况下，可能会拖上几年。这取决于情况有多复杂，取决于监管环境有多复杂，取决于诉讼环境的程度如何。而且哪怕医疗服务已经提供完毕，理赔流程仍可能继续没完没了地拖下去。

所以，这并不是一个简单的过程。我希望大家都能想象一下，如果我们能将这个时间缩短到十分之一，医疗系统能够变得多么高效，对吧？你在工作中受伤，提交申请，经历那个流程，一切都是数字化的，一切都很顺畅。

<details><summary>Original English</summary>So, if we We about these blue boxes, many of these handle complex medical claims. Somebody gets hurt because a product is defective, somebody gets into a car accident, uh somebody gets hurt at work.

Now, adjudicating a claim and getting a response back to a patient or a claimant takes a long time. In the best case scenario, it takes a few weeks. In the worst case scenario, it can drag on for a few years. Depending on complex the the scenario is, depending on complex the regulatory environment is, depending on how litigated the environment is. And even once you get the the medical services delivered, the claim can keep dragging on and on.

So, this is not a simple process, and I want all of us to imagine how much more effective the the healthcare system could be if we could shrink this by a factor of 10, right? You get hurt at work, you you submit the application, uh you go through that process, and everything is digital, and everything is smooth.</details>

### 理赔流程中的交接与摩擦

那么，为什么会耗费这么长时间呢？

甚至仅在医疗环节就有大量的交接点，这还没算上法律环节，以及实际的保险环节，对吧？

所以，当你在这些情形之一中受伤，并且必须针对复杂理赔进行投保理赔时，你必须获得诊断，必须去看各种专科医生。有时专科医生意见不一致，对吧？然后你必须确保自己拥有恰当的保额覆盖，无论是初级诊疗，还是这些额外形式的责任险之一。还有利用度审查，医生们必须相互认同一项治疗程序是必要的。我们有治疗，有账单。你试图弄明白你的账单是什么意思，对吧？对照着福利与保险覆盖说明。你拿到付款，然后还要进行后续治疗。

这里还可以添加非常多额外的气泡和分叉路径，取决于具体步骤，但总体而言，这绝非一个简单的过程。

<details><summary>Original English</summary>So, why does it take so long?

There's a lot of handoff points with getting even the medical side, not accounting for the for legal side, the actual insurance side as well, right?

So, when you when you get hurt uh in one of these scenarios and have to be insured for a complex claim, you have to get the the diagnosis, you have to go to various specialists. Sometimes specialists disagree, right? Then you have to make sure that you have the right coverage, uh whether it's primary care or one of these uh additional forms of liability. You have utilization reviews where doctors have to agree with one another that a procedure is necessary. Uh we have treatments, we have billing. You try to figure out what your bill means, right? With the explanation of benefits and coverage. You get the payments, and you have continued treatments.

Uh there's so many additional bubbles here that can be added and forks in the road, um depending on the steps, but in general, it it is not a simple process.</details>

在整个过程中，很多事情都可能出差错。我只是列出了脑海中立即浮现的大约 15 项，但这与保险公司的人力资源状况有关，理赔理算员的人员流动率高、退休率高；与技术有关，人们一遍又一遍地重复处理相同的数据；还与我们最终面临的这类局面有关，索赔人承受着压力，有时会犯错，处于无法理性行事的处境，对吧？因为如果你刚经历了一场创伤性的车祸，你不会是最理性的人。

所以，我们来谈谈技术如何能够帮助我们。

<details><summary>Original English</summary>And along the way, lots of things can go wrong. Uh I just listed around 15 that that come to mind immediately, but this has to do with the HR situations and insurance companies with claim adjusters having high turnover, high retirement rates, has to do with technology of people reprocessing the same data over and over again. Has to do with the types of situations we end up with where claimants are are stressed and sometimes make mistakes and are in the position where they're not acting rationally, right? Cuz if you're you've gone through a traumatic car accident, you're not going to be the most rational person.

So, let's talk about how technology can help us.</details>

### 工伤理赔案例与非结构化数据

那么，我们来看一个工伤补偿理赔的例子。之前有人见过工伤理赔案吗？

有几个人，好的。

通常当有人受伤时，他们必须在工作场所内报告，然后对此进行备案申报。我展示的那三份表格，德克萨斯州、纽约州和加利福尼亚州的那些，就是典型的受理表格。然后你会经历实际拜访各类人员的过程，无论是急诊室，还是接受额外治疗等等。而且在后期收到理赔申请之前，你的理赔并不总会得到审查。

随着你走完这个过程，会有各种类型的理赔。这里我生成了一些合成数据作为示例，但它们与实际生产中的情况相当接近。你会经历所有这些类型的治疗，接受不同类型的医疗程序，你可能在网络内，也可能在网络外，可能为了这些治疗而来回奔波，有时还会遇到相互矛盾的信息。

<details><summary>Original English</summary>So, let's go through a workers' compensation claim. Has anybody seen a workers' comp claim before?

Few people, okay.

So, typically when somebody gets injured, they have to report it within the workplace and then make a filing of that as well. Those three forms I showed, the Texas, New York, and California ones, those are typical intake forms. And you go through this process of actually visiting various people, whether it's an emergency room, whether you have additional treatments, and so forth. And you don't always have your claim reviewed until you get claims later on.

Now, as you go through that, there's various types of claims. Here I generated some synthetic ones as an example, but they're they're fairly close to what you have in in production. So, you go through you go through all these types of treatments, you get different types of procedures, you might be in network, you might be out of network, you might be traveling for these, and sometimes you have conflicting information as well.</details>

在我们经历每一个流程时，所有文档看起来都不一样。每家医院都有自己构建账单的方式，对吧？每位医生写病程记录的方式都不一样。它在任何形式、形态或外观上都不是统一的。因此，这就是为什么数据是非结构化的，而且很多时候并不是电子数据流。它是一份 PDF，一封电子邮件，一份传真。所以，在底层所有的业务复杂性之上，你又叠加上了所有这些技术复杂性。

然后你还会遇到类似这样的情况，对吧？有人做了一项评估，得出了三种不同的结果，对吧？比方说针对某人的活动度。

你打算如何解决这个问题以便对理赔进行裁决？

<details><summary>Original English</summary>And as we go through each of these processes, all the documents look different. Every hospital has its own way of structuring a bill, right? Every doctor has a different way to write a progress note. It it's not consistent in any way, shape, or form. So, this is why the data is unstructured and many times it's not in an electronic feed. It's a PDF, it's an email, it's a fax. So, you have all these technology complexities that layer on top of all the business complexity that lies underneath.

Then you have something like this, right? Somebody does an assessment and there's three different results, right? For let's say the range of motion that somebody has.

How are you going to resolve this in order to adjudicate the claim?</details>

### 诉讼激励与欺诈风险

现在我们甚至还没把另一部分叠加在上面。在这些医疗流程推进的同时，还存在诉讼风险。所以在保险中，通常在诉讼理赔中保险公司处于被告方，而你面对的是原告方。

原告方有动力去处理尽可能多的案件量，并获取尽可能大额的和解金。所以你实际上陷入了一种具有两种不同激励机制的局面。在原告方，行动要尽可能快，提出尽可能最大的索赔主张，到处张贴巨大的广告牌。大家飞过来的时候大概都见过那些广告牌吧？到处都是。

而且与保险方或被告方相比，原告方采用 AI 的速度其实要快得多。因为你能拿到多少比例的分成，取决于你行动有多快以及你的索赔金额有多大。

就律师费用的实际补偿比例而言，取决于你所在的司法管辖区，如果你在加利福尼亚州，工伤补偿费用比例可以在 9% 到 15% 之间。在其他司法管辖区，会进入三分之一甚至 40% 的区间。

所以现在，在医疗挑战之上、在保险挑战之上、在技术挑战之上、在行政管理挑战之上，你现在又有了诉讼，保险公司为诉讼理赔预留了大量资金。

<details><summary>Original English</summary>Now we haven't even layered the the other portion on top of this. While these medical processes are going through, there's also the risk of litigation. So with an insurance, typically insurance is on the the defendant side of a litigated claim and you have the plaintiff side.

Now the plaintiff side is incentivized to handle as much volume as possible and to get as big of a settlement as possible. So you actually get into a situation where you have two different incentive structures. So on the plaintiff side, go as quickly as possible, make the most the biggest claims possible, put up giant billboards everywhere. We saw those when we were flying in probably, right? all over the place.

And the plaintiff side has actually adopted AI a lot more quickly compared to the insurance or defendant side. Because you get a percentage of how fast you move and how big your claim is.

Now the range of the actual percentage of compensation for for lawyers depending on your jurisdiction can range from 9 to 15% if you're in California for workers comp fees. In other jurisdictions, you get into that 1/3 territory or even 40%.

So now on top of healthcare, on top of insurance, on top of technology challenges, on top of administration, you now have litigation and insurance companies settle aside a lot of money for for litigated claims.</details>

这里的挑战在于，如果你没有经历适当的数字化转型，你就会特别容易受到不良行为者的侵害，对吧？你会收到重复的索赔申请，会收到欺诈性的索赔申请，因为现在做这些事情变得更容易了。因此，如果你没有能力切实应对这些并高效地处理事务，系统中的欺诈行为就会越来越多，对吧？这就像如果你的网站很容易受到 DDoS 攻击，对吧？人们就会不断地对你发起 DDoS 攻击。

而随着我们开始解决所有这些子问题，我们忘却了最重要的事情，对吧？这些才是最重要的事项：某个人的医疗质量、降低成本、确保流程迅速、并且体验良好。

<details><summary>Original English</summary>Now the challenge here is that if you have not gone through a proper digital transformation, you are especially vulnerable to to bad actors, right? So you can be sent repeated claims, you can be sent fraudulent claims as making that even easier to do right now. So if you don't have the ability to actually handle those and process things efficiently, you get more and more fraud in the system, right? It's similar to if your website is easy to DDoS, right? People are going to keep DDoS-ing you.

And we forget about what matters most as we start solving all these sub-problems, right? So, these are the things that matter most in terms of the quality of somebody's care, reducing costs, making sure it's a quick process, and it's a good experience.</details>

### 数据解决方案的三阶段

那么，让我们来逐一解决其中的一些问题。我将讨论三个不同的阶段以及它们能起到什么作用。

第一，我们谈谈干净数据，以及我们如何实现这一点。第二，我们谈论文档内分析，然后我们谈论跨理赔因素。

好的，干净数据。那么，在座有人以前处理过理赔数据或任何类型的保险数据吗？

有几位，好的。

你们处理过或者见过大概多少重复记录？

很多？是的，数以百万计，对吧？取决于你共事的司法管辖区，重复记录可能高达 50% 甚至更高，对吧？所以，你有如此

<details><summary>Original English</summary>So, let's go through and and solve some of these problems. I'll talk about three different phases and how they can help.

So, number one, let's talk about clean data, how we can accomplish that. Number two, let's talk about within document analysis, and then let's talk about cross-claim factors.

Okay, clean data. So, has anybody here worked with claims data before or any kind of insurance data?

Few folks. Okay.

How many duplicate records sort of have have you processed or have you seen?

Many? Yeah, millions, right? Uh depending on the jurisdiction that you work with, they can be as much as 50% or even higher, right? So, you have so</details>

<!-- chunk 3/6 -->

有很多重复件进来，有时这是故意的，对吧？有时候为了让理赔得到处理，你实际上必须不断去催人，对吧？“跟进一下我的理赔，跟进一下我的理赔”，对吧？呃所以，因为大家动作慢，就会陷入我们在技术领域看到的那种级联失效效应。

<details><summary>Original English</summary>
many duplicates coming in, and sometimes this is intentional, right? Sometimes to get a claims processed, you actually have to keep pinging people, right? Following up with my claim, following up with my claim, right? Uh so, because people are slow, you get into this sort of cascading failure effect that we see in technology.
</details>

和其他病人的记录混在一起，对吧？比如有个 Bob Joe，还有一个 Bob Joe Jr.。

<details><summary>Original English</summary>
Commingled records with other patients, right? You have Bob Joe and you have Bob Joe Jr.
</details>

对吧？那些病历混在一起的情况相当频繁地发生。这违反了 HIPAA。为此有一大堆监管风险，但是系统和数字化转型并不是为此而搭建的。而且当混入其他人的病历时，实际上可能会据此做出决定。

<details><summary>Original English</summary>
Right? Those medical records get mixed in a at a at a fairly often occurrence. It violates HIPAA. There's a whole bunch of regulatory risk for that, but the system and the digital transformation is not set up for that. And decisions can actually be made when other people's medical records are are mixed in.
</details>

对吧？所以，当遇到高度复杂的理赔案件时，这一点尤其敏感，里面可能会漏掉东西。某个人的记录被上游的医生或管理人员混了进去，突然之间整个理赔就瓦解了。

<details><summary>Original English</summary>
Right? So, this is especially sensitive when there's a high uh complexity claim where things can be missed. Somebody's record gets mixed in by a doctor upstream or administrator and suddenly the whole claim falls apart.
</details>

然后我们还有更预料之中的情况，就是扫描质量差或未数字化好的数据。对吧？会有一些你看不懂的手写字，更不用说医生的手写字了，对吧？有些东西是以纸质形式进来的。

<details><summary>Original English</summary>
Then we have the the more expected items of poorly scanned or undigitized data. Right? You have some some handwriting that you can't understand, let alone doctor's handwriting, right? Some things come in on paper.
</details>

所以，我们不断收到这些不太干净的数据范例，它们的发生有很多原因，对吧？其中部分原因在于，医疗系统中存在大量的复制粘贴，对吧？你看医生或护士在更新病历时，对吧？他们会在不同病人之间复制粘贴。他们会一路在不同就诊记录之间复制粘贴。呃你个人可能亲眼见过这种情况，但在该领域这经常发生。

<details><summary>Original English</summary>
So, we we keep getting these poorly uh clean data examples and they happen for many reasons, right? So, some of this happens because uh you have a lot of copy pasting that happens in the medical system, right? You go through uh doctors or nurses as as they're updating the medical records, right? They'll copy paste between patients. They'll go through and they'll copy paste between visits. Uh you might have seen that personally, but it happens a lot uh in the space.
</details>

呃 EMR 的设置其实并不一致。现场有人以前见过 EMR 吗？

<details><summary>Original English</summary>
Uh EMRs are actually not set up consistently. So, has anybody here seen an EMR before?
</details>

他们自己的病历，对吧？

<details><summary>Original English</summary>
Their own medical record, right?
</details>

现场有人换过不同的医疗机构或医疗网络吗？

<details><summary>Original English</summary>
Anybody here moved across providers or networks?
</details>

是的。它们看起来一样吗？

<details><summary>Original English</summary>
Yeah. Do they look the same?
</details>

不，它们看起来不一样。嗯，我来自加拿大多伦多，我们的很多医院每次搭建 EMR 时都会重新做一套实施。这往往既是因为医院内部存在的初始流程，[哧笑] 在整个网络之间也同样如此。关于它为什么会按某种特定方式搭建，存在着非常微妙的动态关系。如果你想谈论数据干净度的话，人们在 EMR 里利用嵌套字段搞出了一些非常奇怪的操作。

<details><summary>Original English</summary>
No, they don't look the same. Um I'm from Toronto, Canada and many of our hospitals do fresh implementations every time they set up an EMR. And this often happens both due to the initial processes that exist within a hospital, [snorts] it happens across the network as well. There's very interesting dynamics that happen on why it's set up a certain way. And if you want to talk about data cleanliness, people do some very strange stuff in EMRs with nested fields.
</details>

所以，尽管我们确实拥有电子健康档案和医疗系统，但它们互不相同，结构古怪，因此你确实也必须对其进行一些转换处理。而且通常把数据提取出来很困难，所以大家到头来还是选择发传真或 PDF。

<details><summary>Original English</summary>
So, even though we do have electronic health records and medical systems, they're all different, they're structured weirdly, so you do have to do some some transformations on it as well. And often times it's it's difficult to pull data out, so people just choose to to send faxes or PDFs at the end of the day.
</details>

所以，解决干净数据并不是一个容易的问题。呃人工智能可以帮助我们，数字化转型也可以帮助我们，但上游有很多因素交织在里面。

<details><summary>Original English</summary>
So, solving clean data is not an easy problem. Uh AI can help us, digital transformation can help us, but upstream there's a lot of factors that go into it.
</details>

### 重复记录与数据清洗

呃这是一些示意性数据的例子，呃关于重复记录的。呃真实数据看起来也挺相似的，某些网络中存在大量的重复件。如果你是被动接收这些重复记录的一方，这实际上会非常令人沮丧，对吧？我们有一些客户就会抱怨说：“这家机构能不能别再给我们发这么多重复件了，对吧？”除非你有良好的系统来检测这一点，否则你只会不断收到同样质量糟糕的数据。所以，拥有这些技术实施和检测系统以切实保障你自己的数据池呃数据嗯干净度，是非常重要的。

<details><summary>Original English</summary>
So, uh this is an example of some illustrative data. Uh of duplicate records. Uh real data looks quite similar, as well, with a high number of duplicates across certain networks. And this is actually very frustrating if you are on the receiving end of these duplicate records, right? So, we have a number of customers who are like, "Can this organization stop sending us so many duplicates, right?" And unless you have good systems to detect this, you got you just keep getting the same bad quality data. So, it's really important to have those technical implementations and detection systems to actually make sure that you can safeguard your your own data pool uh data um cleanliness.
</details>

现在，一旦你掌握了这些数据，就存在实际修复问题的机制，对吧？出于监管或呃人际层面的原因，对吧？但作为基准，这种混乱的数据依然存在。而一旦你能检测出像重复这样的问题，呃再次强调，这看似是一个已解决的问题，呃你就不会再鼓励诸如带着不同日期多次提交理赔、或提交同一份理赔呃的情况，其他人也不得不清理他们的数据。

<details><summary>Original English</summary>
Now, once you have this data, there there's mechanisms of of actually fixing things, right? For regulatory or uh interpersonal reasons, right? But you still have this messy data that exists as a baseline. And once you can detect things like duplications, uh again, seems like a solved problem, uh you no longer incentivize things like sending claims multiple times with with different dates or the same claim uh or just other folks have to clean up their data, as well.
</details>

除了数据本身的干净度之外，另一部分在于这些理赔案件的体积非常庞大。呃当我刚开始工作并在我们的数据库里看到一个大小为 8 GB 的 PDF 时，感到非常惊讶。嗯所以，这些理赔文件里什么都有。里面有呃图像，对吧？呃想想车祸，对吧？里面会有伤情部位、碰撞等等的图像。还有 X 光报告、呃超声波，以及介于两者之间的所有东西。

<details><summary>Original English</summary>
The other part that, beyond just the cleanliness of the data, is that these claims are are really large. Uh when I first started working and saw within our database that there was a PDF that was 8 GB in size, that was very surprising. Um so, it these claims have anything and everything within them. They have uh images, right? Uh if you think about auto accidents, right? There are their images uh within the site of the injury, collisions, and such. There's x-ray reports, uh ultrasounds, everything in between.
</details>

有时这会让很多 PDF 阅读器直接崩溃。呃如果你想想自己可能拥有的一些旧电脑，试图打开一个 8 GB 字节的 PDF 会是相当困难的。

<details><summary>Original English</summary>
And sometimes this just crashes a lot of PDF viewers. Uh if you think about some of the old computers that you might have, trying to open up an 8 GB uh byte PDF will be will be quite challenging.
</details>

呃甚至在技术系统层面，对吧？我们整天都在讨论上下文窗口。你怎么把一份 8 GB 的 PDF 塞进上下文呃上下文窗口里呢，对吧？这可不是像说一句“嘿 Claude，帮我看一下呃这份 10 页的 PDF 并并给我一个回复”，或者“嘿 ChatGPT 或 Gemini”，对吧？

<details><summary>Original English</summary>
Uh and even on the technology systems, right? We talk about context windows all the time. How are you going to fit a context uh into a context window in 8 GB PDF, right? It's it's not as easy as saying, "Hey Claude, take a look uh at my 10-page PDF and and give me a response or hey chat GPT or Gemini, right?
</details>

没那么容易。

<details><summary>Original English</summary>
Not that easy.
</details>

嗯除此以外，真正去通读和审查一个案件需要耗费大量的时间。因此，无论是技术挑战还是业务挑战，都会导致非常复杂的技术挑战。

<details><summary>Original English</summary>
Um and on top of that, actually going through and working through a case requires a significant amount of time. So, either the technical challenges or the business challenges that result in very complex technical challenges.
</details>

### 理赔异常与诊断冲突

现在，如果我们继续梳理，并在这里引入越来越多的复杂性，这其中的很多理赔还存在异常情况。举个例子，你可能会看到早期病患报告的一些病程记录，上面写着：“看，这里预约了该日期的这次 X 光检查。”你收到了理赔人材料包，而那张 X 光片却不在里面。对吧？如果不用某种方式把它标出来，就非常容易漏掉。嗯而要是缺少了它，同样地，关于是否给予了充分的治疗、呃当事人是否真的去接受了所提供的治疗、呃以及你实际上该如何将此与计费端进行交叉比对，整个案件的走向都可能发生改变。

<details><summary>Original English</summary>
Now, if we work through and we're adding more and more complexity into here, a lot of these claims also have irregularities. So, you might have some progress notes, for example, of a earlier patient report that says, "Hey, here is this x-ray that was booked for this date." You receive the claimant package and that x-ray is not there. Right? And it's very easy to miss that without actually having this highlighted in some sort of way. Um and without that, again, the whole trajectory of a case can change whether there was adequate care given, uh whether the person actually went to the the the care provided, uh and how do you actually cross-reference this with the billing side of things?
</details>

所以，这是一种非常非常常见的情形，上游再次因为数据混乱，你实际上不得不反复询问：“嘿，你能把这份记录发给我吗？”“哦，我们发传真漏掉了这份。”“哦，传真出故障了。”“哦，我们换了后端系统。”对吧？所以作为一家机构，你必须设立这些防线，以确保这些情况能被标记出来。

<details><summary>Original English</summary>
So, this is a very very common scenario where upstream, again, because the data is messy, you actually have to ask repeated times, "Hey, can you send me this record?" "Oh, we missed faxing this." "Oh, the fax glitched." "Oh, we changed our back-end system." Right? So, with as an organization, you have to have these lines of defense in in order to make sure that these get flagged.
</details>

而作为一名理赔理算员，一名理赔理算员可能一次要处理 200 起理赔。所以，他们不可能在脑子里记住所有事情，去想“哦对了，我需要跟进一下这张 X 光片还是不用”。对吧？他们可以做笔记，可以往前推进，但东西终归会遗漏。因此，技术同样可以在这类问题上提供巨大的助力。

<details><summary>Original English</summary>
And as a claims adjuster, a claims adjuster might be processing 200 claims at a time. So, they're not going to be able to keep everything within their minds saying like, "Oh yeah, I need to follow up on on this x-ray or not." Right? They can take notes, they can move forward, but things are going to get lost. So, this is again where technology can be a great lift uh to these kinds of problems.
</details>

然后你会遇到相互冲突的诊断。这种情况发生的频率也相当高。现场有谁曾为某种病症寻求过第二诊疗意见吗？

<details><summary>Original English</summary>
Then you get conflicting diagnoses. This happens fairly often as well. So, who here has sought a second opinion for a medical condition?
</details>

有几位，对吧？嗯有时我们寻求意见是为了获得另一个视角。有时你会得到截然不同的答案，对吧？而且理赔越复杂，就越有可能出现某种冲突。

<details><summary>Original English</summary>
Few folks, right? Um sometimes we we seek them out um to get another perspective. Sometimes you get completely different answers, right? And the more complex the claim is, the more likely there is to be some some kind of conflict.
</details>

所以，在这种情况下经常发生的是，当你审核一起医疗理赔并看到某些相互冲突的诊断，或者你想再次核实应该留出多少资金用于实际赔付该理赔时，你会把它送到 IME，即独立医学评估机构。然后由另一位医生对档案进行审查。接着你还得去管理那些医生、医疗机构网络以及 IME 本身。

<details><summary>Original English</summary>
So, in this case, what often happens is when you adjudicate a medical claim and you see some conflicting diagnosis or you want to double-check how much you should set aside to actually pay out for the claim, you send it to an IME or an independent independent medical evaluation. Then you have another doctor who performs their their review of the file. And then you have to manage those doctors and the provider networks and the IME themselves.
</details>

所以，现在我们又在叠加了。生态系统里涌入了更多的人，带来了更多的复杂性。

<details><summary>Original English</summary>
So, now we're stacking again. More people into the ecosystem, more complexity.
</details>

### MLCR 基准评估

现在，AI 在这里可以相当有用；而且我想，在 2026 年做一场演讲如果不谈评估（evals），未免显得有些不合时宜。

<details><summary>Original English</summary>
Now, AI can be quite useful here and it would it would be, I guess, poor taste to give a talk in 2026 without talking about evals.
</details>

不过我们确实使用了 AI 来试图在某些方面解决这些问题，比如冲突的诊断、缺失的记录以及其他一些问题。因此，我们与 Artificial Analysis 共同构建了这个名为 MLCR 的基准，用来衡量 AI 在实际回答这些问题方面的有效性。

<details><summary>Original English</summary>
But we did use AI to to try to solve these issues in some ways, the conflicting diagnosis, the missing records and a number of other ones. So, we built this benchmark called MLCR with artificial analysis to to measure the effectiveness of AI in actually answering these questions.
</details>

那么，切到我们讨论过的这篇博文，我会向下滚动到这个基准的具体内容。

<details><summary>Original English</summary>
So, flip over to our blog post that we talked about and I'll scroll down to what this benchmark looks like.
</details>

我们发布了与医疗理赔相关的六个不同层级的问题。其中有些非常简单，比如“这次伤害是什么时候发生的”以及“受了什么伤”，对吧？然后它们会变得稍微复杂一些。“总共进行了多少次手术？”

<details><summary>Original English</summary>
So, we released six different tiers of questions related to medical claims. Some of these are very simple, like when did this injury happen and what was the injury, right? Then they get a little bit more complex. How many surgeries get performed?
</details>

<!-- chunk 4/6 -->

“这位患者目前有多大能力？”最终我们会接触到越来越复杂、甚至更难解决的问题。而且通常情况下，当你作为理赔理算员、医生或管理人员提问时，你并不掌握发生情况的完整背景。所以，这就是我们看到出现幻觉的地方——人们假设病历里有某项内容，但实际上并没有。

<details><summary>Original English</summary>
How much capacity does the this patient have? And eventually we get into more and more complex questions that are even harder to to resolve. And oftentimes, the way that you ask a question as a claim adjuster, a doctor, an administrator, you don't have full context of what's happening. So, this is where we see hallucinations show up where people assume something is in a medical record, but it's not.
</details>

### 模型评测与性能基准

那么，让我们再多看看结果。这些可以在 Artificial Analysis 网站上查到。如果你想看一下的话，我们为我们拥有的前三个级别的问题——也就是简单问题——发布了一个开源数据集。而且我们还有一个私有集，托管在 Artificial Analysis 那里，在一定程度上用于防止刷榜。所以，观察模型的表现是非常有趣的。实际上，我们是在三个不同的维度上来衡量这一点的。让我翻回那张幻灯片。

<details><summary>Original English</summary>
So, let's go a little bit more to the results. So, this is available on the artificial analysis website. If you want to take a look, uh, so we released an open source, uh, data set for the first three tiers of questions that we have, the easy ones. And we have a private set that we host with artificial analysis for, um, to stop benchmarking to to a certain extent. So, it's very interesting to see how how models perform. Uh, we actually measure this on three different, uh, axes. So, let me flip back to that slide.
</details>

我们在简洁度上进行衡量。也就是回答有多简洁？我们是拿它与经过人类专家验证的答案来进行对照衡量的。

<details><summary>Original English</summary>
We measure this on conciseness. So, how concise is a response? Uh, and we measure this against a human, uh, expert validated answer.
</details>

然后我们考察准确性。答案是否正确？最后一项是完整性。问题中所有相关的信息、各条信息是否都得到了回答？

<details><summary>Original English</summary>
We then go through accuracy. Is that Is the answer correct? Uh, and the final one is completeness. Are all the relevant, uh, informations, uh, piece of information answered, uh, in the question?
</details>

回到这里。前沿模型一直在以非常、非常快的速度演进，而这正是进行评测非常重要的地方。当我们发布该评测时，我们在所设定的推理水平上看到的最高准确率是 20%。几个月后，在非常高的推理水平下，我们已经达到了 75% 这一档。对吧？所以模型进步非常快。但这很棒，因为这意味着我们可以开始将许多更复杂的问题产品化。而且我们对于有人需要在系统中对此进行复核的信心有了更多的确定性。因此在我们的系统中，始终有人员参与其中（human in the loop）。这真的非常重要。

<details><summary>Original English</summary>
So, we go back here. Um, the frontier has continued to evolve very, very quickly, and this is where having evals is really important. Uh, when we released the eval, uh, the highest accuracy that that we saw on the levels of reasoning that that we had was 20%. A few months later, we're in the 75% with with the very high reasoning levels. Right? So, models move very quickly, um, but this is great because it means that we can start productizing a number of the more complex questions. And we have more certainty of the confidence that somebody has to review this, uh, in a system. So, within our system, there's always a human in the loop. Uh, so that's really important.
</details>

你还会开始在帕累托前沿上得到这里的成本曲线，也就是实际提出这个问题并获得合适答案的成本。在过去的几个月里，这也一直在改善。

<details><summary>Original English</summary>
You also start getting the the cost curves here on the Pareto frontiers, on the cost to actually ask this question and get a suitable answer. And this has been improving through the past few months as well.
</details>

你也会看到其中存在的一些权衡。因此，当我们在文档分析上运行这些基准测试时，一个有趣的现象是，GPT 模型在准确性上表现极佳，但它们遗漏了一些关键信息。Anthropic 的模型相当不错，而且它们在信息量上要完整得多。它们在这里的准确率确实也略低一些。

<details><summary>Original English</summary>
And you get some of these tradeoffs as well. So, one of the interesting things when we were running these benchmarks on, uh, document analysis was that the GPT models were were excellent at accuracy, but they omitted some key pieces of information. Uh, Anthropic's models were were quite good, um, and they're much more complete on the amount of information. Um, they they do have slightly lower accuracy here as well.
</details>

>> 我能问个问题吗？

<details><summary>Original English</summary>
>> Can I ask a question?
</details>

>> 当然可以。

<details><summary>Original English</summary>
>> Sure.
</details>

>> 准确性，你们是如何与人为因素相比进行衡量的？

<details><summary>Original English</summary>
>> Accuracy, how do you measure it compared to the human factor?
</details>

>> 是的，与人类给出的答案进行对比，然后我们进行三重裁判验证。是的。

<details><summary>Original English</summary>
>> Yes, compared to to human answer uh and then we do the triple judge uh verification. So, yeah.
</details>

所以这里是准确性。你可以看到曲线是什么样的；而完整性在大多数模型供应商那里仍然没有得到解决。是的，针对刚才的问题，这是基于人类验证过的答案以及一组经过校准的裁判。在我们的博客文章中，我们描述了我们在这里采用的方法，并且我们还发布了一篇后续内容，说明我们是如何进行这一校准的。

<details><summary>Original English</summary>
So, we have accuracy here. You can see how uh the curve looks like and we have completeness uh which is uh is still not solved across most model providers. And yes, to to the earlier question, uh this is based on a human verified answer and on a calibrated set of judges. Uh within our blog post, we describe the the methods we have here uh and we released a follow-up as well on on how we did this calibration.
</details>

因此，即便我们在这里使用 AI 来结构化我们的数据并提取重要见解，我们也希望确保该流程中的每一步都经过良好的校准，因为如果你的上游数据是不正确的，而你又开始在下游使用它，对吧？你其实什么都没得到。

<details><summary>Original English</summary>
So, even though we're using AI here to structure our data and extract important insights, we want to make sure that each step uh of that process is well calibrated because if upstream uh your data is incorrect and you start using it downstream, right? You haven't gained anything.
</details>

所以再次强调，在处理理赔流程的过程中，校准你的裁判、建立优秀的评测是非常重要的。我认为这是大多数演讲中经常出现的一个主题。而且你要确保拥有能够真正核实这些信息的专家，因此你需要跨团队合作来实现这一点。

<details><summary>Original English</summary>
So, again, really important as you're going through the claims uh uh process to to calibrate your judges, to build good evals. Uh I think that's a recurring theme at Ed Most Talks. And you want to make sure you have those experts who can actually verify this information, so you work across teams to to get there.
</details>

### 跨理赔分析与宏观见解

好的。那么以上是在单个理赔案件内的情况。我们知道，带着一定程度的确定性，我们可以提取出某些类型的见解。我们可以标记出相互冲突的诊断，我们可以去重，我们可以查找缺失的记录。

<details><summary>Original English</summary>
Okay. So, that's within a claim. Uh we know that with some amount of certainty, we can extract some types of insights. We can flag conflicting diagnosis. We can deduplicate. We can search for missing records.
</details>

我们来看一些更有趣的事情，那就是跨理赔案件分析。对吧？如果你是一家中等规模的保险公司，在某个业务线组合中，你收取的保费可能达到 10 亿美元。而你每次每年可能要支付例如 20,000 笔赔案，甚至更多，这取决于你从事的是哪类业务。

<details><summary>Original English</summary>
Let's go to something more interesting, which is cross claims. Right? So, if you are a mid-size uh insurance company, you might be collecting $1 billion in premiums within a uh portfolio of lines of businesses. And you might be paying out, let's say, 20,000 uh claims uh at a time per year uh or even more, depending on what line of business you deal with.
</details>

现在，你想更深入地了解究竟是什么在影响你的赔付率。人们都在提出什么样的理赔？在哪些地域？涉及什么类型的伤害？以及有哪些类型的医生参与其中？

<details><summary>Original English</summary>
Now, you want more insight of where you actually like what's affecting your loss ratio. What kind of claims are people making? In which geographies? What type of injuries? and what type of doctors are being involved.
</details>

我认为这里也变得相当有趣，因为一旦从理赔案件中提取出那些数据，你就可以开始做有趣的图表可视化、回归分析以及其他相关工作。对吧？

<details><summary>Original English</summary>
This is where I think it gets quite interesting as well as actually being able to, once you have that data extracted from the claim, you can start doing interesting visualizations, regressions, and work as well. Right?
</details>

我们被问到且一直致力于解答的两个问题是：人们在网络内部的流动范围大致有多大？对吧？比方说，如果一名患者在旧金山或纽约，对吧？他们是否是在当地接受治疗？给他们治疗的人是否合适？我们还拥有这些展示究竟是谁在协同工作的网络。这是一些经过隐匿处理的数据，是来自加利福尼亚州的一个子集，你可以实际追踪看到哪些律师在一起合作，哪些医生在一起合作，哪些脊椎按摩师、物理治疗师在一起合作，实际的合作关系是怎样的，以及理赔案件本身之内的来龙去脉。这就是你从理赔案件中提取数据所能获得的更高层次的见解。

<details><summary>Original English</summary>
So, two of the questions that we we've been asked and we've worked on answering is sort of how much are people traveling within a network, right? So, if a patient is, let's say, in San Francisco or New York, right? Are they getting treatment in their local area? And is that the right person to to be giving the treatment? We also have these networks of who's actually working together. So, this is some redacted data, a subset from from California, and you can actually track to see which lawyers are working together, which doctors are working together, which chiropractors, physiotherapists, and what is the actual working relationship look like and the story within the claim itself. So, this is that sort of higher-tier insight that you can get within extracting data from your claim.
</details>

然后你会进入一些有趣的医疗结果分析，对吧？例如，哪些病症会一同并发？比如有人背部受伤，你可能会看到一系列可以映射到 ICD 编码的、共同存在的不同诊断，并且你可能会发现，好吧，为什么某个医生的书面报告中存在这种情况，而另一个医生的报告中却没有？在这种情况下，同样地，只有当你能够解决单个理赔案件内的数据提取问题，并将其汇总到更广泛的保险投资组合中时，你才会获得这些能力。

<details><summary>Original English</summary>
You then get into some interesting medical outcomes, right? So, which conditions co-occur together? So, if somebody has a back injury, as an example, right? You might have a series of different diagnoses that could be mapped to ICD codes that coexist together, and you might see, okay, why does this exist from a certain doctor's write-up versus another's? And in this case, again, you you only get these capabilities if you can solve the data extraction problem within one claim, and then roll it up into your broader insurance portfolio.
</details>

### 费用分析与异常识别

现在，我们谈到资金的部分，对吧？这里抽取了物理治疗两次疗程的一个小子集，不同的医生收取的费用数额不同，对吧？我们大概都见过这种情况。有时这没问题。如果你是一位更好的医生，你应该能够收取更高的费用，对吧？如果你能让某人尽可能快地康复，用 5 次疗程而不是 10 次疗程，你应该能够收取更高的费用，对吧？但是理解成本并专注于尽可能降低成本是非常重要的，因为一旦医疗系统的不同环节出现成本通胀，它就会不断复利累积，对吧？保费会上涨，向我们收取的费用会上涨，而我们花出去的钱换来的东西却变少了。因此在这项分析中，你可以观察跨理赔案件是否存在某种一致的因素？你应该提供的保额是多少？对于理赔案件的这些成本，你该如何进行承保？

<details><summary>Original English</summary>
Now, we get to the money portion, right? So, pulling a small subsegment here of two treatments of physiotherapy, different doctors charge different amounts, right? We've probably seen that. And sometimes that's fine. If you're a better doctor, you should be able to charge more, right? If you can get somebody to recover as quickly as possible in five treatments instead of 10, you should be able to charge more, right? So, uh but it's really important to understand costs and and focus on minimizing them because as as soon as there's cost inflation through different parts of the medical system, it keeps compounding, right? Premiums increase, uh the fees that we are charged increases, uh and we get less for our money. So, within this analysis, uh you can see across claims, is there a consistent factor? What what is the amount of coverage that you should be providing? How How you should you be underwriting these costs for claims as well.
</details>

而且你可以估计情况随着时间的推移会如何变化，对吧？举这里的例子来说，同比之下，某位医生针对这类治疗的收费上涨了 10%，对吧？那么这种情况是否会在整个管辖区域内发生？这种情况是否会在整个行业中普遍发生？

<details><summary>Original English</summary>
And you can estimate how things are going to change over time, right? So, year over year, as an example here, uh there was a 10% increase for this type of treatment for a given doctor, right? So, is that going to happen across uh the jurisdiction? Is that going to happen across the the industry in general?
</details>

然后你就可以开始做一些反事实分析或分析中的变更推演，来探讨如果我们改变我们的网络，如果我们开始将人们引导向某个方向，如果我们改变计费方式，对吧？潜在的节省空间会有多大？根据现有的医疗护理标准，人们应当接受什么样的手术流程？最近有一篇文章谈到了——有人看过那篇关于多度收费的文章吗？关于进来的 10 亿美元额外账单？你看到过吗？所以这些就是例子，同样地，如果你无法有效地处理数据，人们就会想方设法去钻空子、提交额外的记录，或者做出一些更可疑的行为。

<details><summary>Original English</summary>
So, then you can start doing some counterfactual analysis or or changes in a in analysis to say, if we change our network, if we start directing folks into a certain direction, if we change how we how we bill, right? What are the potential savings that exist? And what kind of procedures should people be having based on the standard of care that exists? Um there is there's recently an article about how as anybody see it seen at the overbilling article about $1 billion of additional billings that have come in? Have you seen that? Um so, those are examples where again, if you cannot process data effectively, people are going to find ways to to to go through and and submit additional records uh or do some some shadier behavior as well.
</details>

说了这么多，意思就是一旦你拥有了优质的数据，你就可以开始做出这些决策。然后一旦你有了这个决策、有了这些理赔信息，你就可以开始将其写入更广泛的系统中，对吧？所以，你

<details><summary>Original English</summary>
So, all this to say is that once you have good data, you can start making these decisions. And then once you have this decision, uh this claims information, you can start writing it into a broader system, right? So, you
</details>

<!-- chunk 5/6 -->

我们可以开始在其他业务线中使用这些，比如，如果你知道了车险人身伤害或工伤赔偿中的趋势，我们是否在公众责任险中也看到了同样的情况？

<details><summary>Original English</summary>
can start using this in in the other lines of business of saying, if you know these are the trends in auto injury or workers' compensation, are we seeing the same thing in general liability?
</details>

如果你知道你的核保模型遗漏了某些趋势，或者你在那里的可解释性没那么强，我们能否利用我们所看到的让模型更具可解释性？我们如何提供这种我们希望存在于数据湖中的神奇数据表？

<details><summary>Original English</summary>
If you know that your underwriting model is missing certain trends or you don't have as much explain ability there, can we make the model more explainable with what we're seeing? How do we provide this sort of magical data table that we wish that that existed within our data lake?
</details>

所以再次强调，你拥有的数据越多，你能拼凑出的图景就越完整，最终你就能更好地为消费者进行核保和产品定价。

<details><summary>Original English</summary>
So again, the more data you have, the more complete of a picture you you can make and the better you can underwrite and price the product at the end of the day for the consumer.
</details>

这些也是你实际驱动高效 AI 应用所需的信息，无论这些应用是在核保端、欺诈端，还是在理赔端。

<details><summary>Original English</summary>
And this is information you need to actually power the the effective AI applications, whether they're on on the underwriting side, on the fraud side, on the claim side as well.
</details>

所以如果你设想一个理想的世界，对吧？我们希望在更广泛的层面上减少某些东西。因此，如果我们想为每个人降低成本，对吧？把患者的体验考虑在内。如果我们想缩短理赔案保持开启的时间。如果我们想提高人们重返工作的速度并改善他们获得的治疗，我们需要确保我们拥有正确的数据和正确的数字化转型来实现这一点。

<details><summary>Original English</summary>
So if you think about like a blue sky world, right? We we want to reduce something more broadly. So if we want to reduce costs for everybody, right? Taking into account that patient experience. If we want to reduce the time that a claim is open. If we want to improve how quickly people get back to work and the the treatment they get, we need to make sure we have the right data and the right digital transformation to do that.
</details>

这是我们在 WiseDocs 内部所做工作中的一个说明性例子。我们也看到了显著的成本节约。

<details><summary>Original English</summary>
So this is an illustrative example in the work that we've done within WiseDocs as well. We've seen significant savings as well.
</details>

因此，经历这个数字化转型过程并拥有正确的数据真的非常、非常重要。

<details><summary>Original English</summary>
So going through this digital transformation process and having the right data is really really important.
</details>

### 问答环节

那我就在这里结束工作坊。我确实想留出相当多的时间来提问，因为这是一个相当全面的主题。

<details><summary>Original English</summary>
So I'll wrap up the workshop here. I did want to leave quite a bit of time for questions cuz it is pretty comprehensive topic.
</details>

感谢大家的聆听，很高兴回答一些问题。

<details><summary>Original English</summary>
So thank you for listening and happy to take some questions.
</details>

>> [掌声]

<details><summary>Original English</summary>
>> [applause]
</details>

>> 是的，我会分享那篇博客文章。是的，这边有个问题。

<details><summary>Original English</summary>
>> Yes, I'll I'll share the blog post. Yes, question over here.
</details>

是的，刚才的问题是关于我们实际上是如何构建数据来构建所有这些信息的。

<details><summary>Original English</summary>
Yeah, so so the question was about how do we actually structure the data to build um all this information.
</details>

所以它会经过几个不同的层级。我也会分享一些我做过的关于这个主题的演讲。基线是，我们使用 OCR 和图像从底层记录中提取信息。算是标准的预处理。

<details><summary>Original English</summary>
So it goes through a number of different levels. I'll share some talks that I've given on the topic as well. The baseline is we we use OCR and images to to extract information from the underlying records. Sort of standard pre-processing.
</details>

如果有人处理过 PDF 的话，预处理 PDF 也不是一项容易的任务。那些 8GB 的文件里有一些非常奇特、百万分之一才会出现一次的个案。

<details><summary>Original English</summary>
Pre-processing PDFs is not an easy task as well if anybody has worked with them. Uh those 8 gigabyte ones have some some weird one in a million examples in them.
</details>

一旦你拥有了数据、文本和图像，我们在上面会有一系列模型，比如 NLP 模型、提取模型。我们有时会使用 VLM 来进行结构化，比如更标准的实体提取模型效果就很好。我们在上面构建了各种分类器。

<details><summary>Original English</summary>
So, once you have the the data, the text and images, we have a series of models on top, um NLP models, extraction models. We use VLMs uh to structure it sometimes, like a a more standard entity extraction model works well. We have various classifiers that we build on top.
</details>

然后我们在其之上有一个摘要层来对文档进行摘要。随后由人工进行核验，以确保信息准确无误。最后，我们在其之上运行那些额外的分析层。所以，我们有这种抽象模式，越往上走，信息的密度就越集中，但它在各个时间点都会经过各种模型以及人工干预的核验。这意味着一旦你到达顶层和最高价值的项目，那就是 AI 可以发挥成效的时候了。那些就是属于那种可以得出正确答案的 MLCR 类问题。在 MLCR 中，这实际上是使用干净的数据来提出这些问题的。现实世界的数据是不干净的，所以在此之前你必须经历多个步骤来清理数据以达到那个目标。

<details><summary>Original English</summary>
Um we then have a summary layer that sits on top of that to summarize the documents. Uh that is then human verified to make sure that the information is correct. And finally, we run those additional layers of analysis on top of that. So, we have this abstraction pattern that sort of concentrates the the density of information as you go up, um but it's verified at various points in time with various models and and human intervention as well. So, that means once you get to the top in the highest value items, that's when AI can be effective. And those are sort of those MLCR uh type questions that can have the right answer. So, within MLCR, this actually uses clean data to ask these questions. Real-world data is not clean, so you have to have various steps ahead of that to to clean up the data to get there.
</details>

是的，通常我们的客户——规模较大的客户内部有多个业务线，而且在不同团队之间共享方面，我想说他们有着不同的规则。

<details><summary>Original English</summary>
Yeah, so typically our our customers So, bigger customers have multiple lines of business internally and they have different uh rules I would say across sharing across different teams.
</details>

其他客户则只在一个业务线中开展业务。他们可能只做车险，可能只做伤残险，也可能只做工伤赔偿。但我们获取全面的趋势来尝试找出并标记这些问题。所以就存在这样一个问题：在某个办事处内部，对吧？你如何呈现其中的某些洞察，或者是按地理区域呈现？

<details><summary>Original English</summary>
Uh other customers just work in one line of business. So, they might just work in auto, they might just work in disability, they might just work in workers' comp. Um but we take the trends uh across the board to try to figure out and flag those. So, there's the question that within sort of an office, right? How do you surface some of those insights uh or or sort of geography?
</details>

然后你在上面还有一层，那可能是更广泛的公司层面，但保险公司内部有时也会包含一组作为独立业务运作的公司。

<details><summary>Original English</summary>
Then you have the the layer on top, which might be um the broader company, but comp- insurance companies also have a collection of companies within them sometimes uh as separate businesses.
</details>

[清嗓子]

<details><summary>Original English</summary>
[clears throat]
</details>

然后你实际上又该如何将其馈送到一个中心化的数据湖中。所以再次说明，每家公司都有些不同，但我们推进的速度完全取决于合作伙伴希望我们有多快。

<details><summary>Original English</summary>
Uh and then how do you actually feed that into a centralized data lake uh as well. So, again, every company is a a bit different, but we we go as fast as our partners want us to.
</details>

我们深耕于理赔领域。所以我们专注于理赔。理赔是我们的核心业务，特别是复杂理赔。那是我们整个 AI 管线所专注的方向。

<details><summary>Original English</summary>
We live in claims. So so we focus on claims. So claims are our our bread and butter, specifically complex claims. That's where our whole AI pipeline is focused on.
</details>

但随着我们不断演进，去解决在理赔裁决、理赔处理和提取信息方面我认为相对更容易的挑战，你就会开始看到这些更具洞察力的方面，从而帮助机构做出投资组合层面的决策。是的。

<details><summary>Original English</summary>
But as we sort of evolve and go and solve the sort of easier challenges, I would say, with adjudicating a claim, processing a claim, extracting that information, you start seeing these more sort of insightful aspects that help organizations make portfolio level decisions. Yeah.
</details>

是的，这是一个好问题。问题是在存在许多这类挑战的情况下，我们如何引导客户入门？通常我们合作时，最重要的是求变的意愿，对吧？我们大概都和想要做出改变的团队或组织合作过，相比于那些不想做出改变的团队或组织，体验非常非常不同。

<details><summary>Original English</summary>
Yeah, so that's a good question. So the question is how do we onboard somebody when there there's a lot of these challenges? So typically we work with the most important thing is a willingness to change, right? So we we've all probably worked with teams or organizations who want to change versus those who don't. Um very very different experience.
</details>

因此，假设是一个想要改变的组织，通常会有几个不同格式的样本文件供我们一起处理。通常大家会发给我们他们手头正在处理的内容，或者已经处理过的，或者基本上是他们试图用来进行回溯测试的内容。

<details><summary>Original English</summary>
So assuming it's an organization that wants to change, there'll be a few sample files typically that we'll work through in various formats. Typically people will send us either things they're immediately working on or have or are basically they're trying to back test.
</details>

然后我们会经历一个审查流程，看看你们提取出了什么，我们的系统提取出了什么，两者如何契合？是否与你们希望看到的信息相匹配？你们是否有不同类型的标准？举例来说，如果我们回到这里的不同类型的文档，我们直接回到登记表。

<details><summary>Original English</summary>
Uh and then we go through a review process to see what did you extract, what did our system extract, how does it align? Does it match the information you want to see? Do you have different types of standards? So if we go back, for example, uh to the different types of documents here, let's just go back to the intake form.
</details>

这份表格上可能会有各种日期。你想要的是受伤日期，还是提交时的报告日期，对吧？所以这些都是业务目标对齐方面的事情。

<details><summary>Original English</summary>
There might be various dates on this form. Do you want the date of injury or do you want the the report date when it was submitted, right? So these are things of alignment of business objectives.
</details>

梳理流程，处理几个标准案卷。如果一切进展顺利，我们就会启动范围更广泛的试点，然后进入到有趣的集成环节，除了人工上传文档之外，还包括与上游供应商集成、API 集成，比如处理所有这些繁杂琐碎的环节。因此，只要有明确的业务成果和转型目标，那这就是一个相当直接明了的过程。

<details><summary>Original English</summary>
Go through process a few standard cases. If things work well, then we start sort of a broader pilot and then gets into the fun integration aspect of integrating with with upstream providers apart from just like hand uploaded documents, API integrations, like dealing with all all the messiness. So as long as there's a a clear business outcome and transformation goal, then it's it's a fairly straightforward process.
</details>

再次强调，在我们经历这一历程的过程中，有时我们并不具备开箱即用的能力，有时我们具备，有时在内部系统上也会涉及多个集成。所以，是的。

<details><summary>Original English</summary>
And again, as as we go through that journey, and sometimes it's like we don't have the capabilities out of the box, sometimes we do, sometimes there's multiple integrations on internal systems as well. So, yeah.
</details>

那么，我们先从问题的第一部分开始，即应对监管以及我们如何与合作伙伴合作？

<details><summary>Original English</summary>
So, let's start with the first part of the question, which is handling regulations and how do we work with partners? So,
</details>

这取决于人们行动的速度有多快。并且也取决于监管推进的速度有多快。因此，我们目前构建系统的方式是，它始终需要有人在环中做出决策。

<details><summary>Original English</summary>
we it depends on how how quickly people are are moving. Uh and also depends how quickly regulations are moving. So, the the way we've set up the system right now is that it always requires a human in the loop to make a decision.
</details>

所以，我们会呈现这些洞察，举个例子，对于像相互冲突的诊断这类情况，我们会显示：“嘿，在第 2 页，在第 20 页，这两位医生之间的诊断存在分歧，你应该看一看，对吧？”所以，只要有人在环中，我认为它就消除了人们所顾虑的 70% 的监管担忧。监管也仍在跟进完善中，因此有很多东西可以阅读，比如我提到的 NAIC 报告，该机构发布了许多不同的报告。针对这一块有现存的指导方针。我们也会与内部的合规治理和监管团队沟通。如果他们想查看某些信息片段，比如我们会向他们分享 AI 管线是如何工作的，对吧？所使用的是哪类数据。

<details><summary>Original English</summary>
Uh so, we surface these insights as an example for things like a conflicting diagnosis, we'll see, "Hey, on page two on page 20, there there's a difference of diagnosis between these two doctors, you should take a look, right?" So, as long as there's a human in the loop, I'd say it it removes like 70% of the the regulatory concerns that people have. Uh regulation is also still catching up, so uh there's a lot of things to read about like the NAIC reports that I mentioned, they that organization publishes a number of different reports. There's the guidelines that exist for that. We talk to the internal governments and regulatory teams as well. Uh and if they want to see some pieces of information, like we will share with them like this is how the AI pipeline works, right? This is the type of data that's being used. Um but
</details>

但归根结底，只要你不去打造黑盒，只要事务是可审计的，并且有人在环中，这就解决了很多问题。在监管方面，还有一个完全属于商业决策层面的维度，比如如何应对核弹级判决（nuclear verdicts）。针对核弹级判决是指非常大额的判决赔偿，或者金额达到 1000 万美元的理赔案件，或者是 1 亿美元的热核级案件（thermonuclear ones），这些会极大地重新分配企业的准备金。因此对于这类案件，通常大家会拿出一套方案来说明他们想要如何应对

<details><summary>Original English</summary>
at the end of the day, as long as you don't build a black box and things are auditable uh and there's a human in the loop, that take cares uh takes care of many things. The regulatory side, there's like a whole other like business decision decision aspect, like how to approach nuclear verdicts. Uh for uh nuclear verdicts are um very large uh awards or um claims that that are $10 million or thermonuclear ones which are $100 million, which really reallocate uh businesses' reserves. So, for those ones, typically people come with like an approach on how they want to handle
</details>

<!-- chunk 6/6 -->

在平台内部，你可以设定：“我要先处理最复杂的理赔案”，或者“我要先处理最先提交的理赔案”。这些都属于人们可以做出的业务决策。

<details><summary>Original English</summary>
them. And within the platform, you can say, "I'm going to handle my most complex claims first." Or I'm going to handle the one that was submitted first. Um and those are all sort of business decisions people can make.
</details>

关于问题的第二部分，也就是人们内部的、各机构的内部目标。我们希望与那些在改善患者护理、减少理赔积压、提供最佳决策方面拥有相同理念的伙伴合作。很多时候，我们的客户甚至并不太去考虑医疗本身的成本，而是它周围的一切，对吧？

<details><summary>Original English</summary>
Uh the second part of the question on like people's internal like organizations' internal goals. Um I mean, we want to work with partners that share the same sort of mindset about improving patient care, uh reducing backlogs uh for claims, providing the best decisions. A lot of times our customers are not even thinking too much about like the the cost of health care itself is everything around it, right?
</details>

所以，如果你是一家大型保险公司，实际上会在诉讼费上花费数亿美元。对吧？所以，这是一件甚至与患者体验无关的事情，但你在那里可以做大量的优化工作并加快进度。对吧？存在监管方面的顾虑，在加州等特定司法管辖区，诉讼情况非常普遍。你得想办法去应对这些问题。还有一大堆参与其中的中间方，他们同样效率低下。因此，取决于客户，每个人的目标都不同。

<details><summary>Original English</summary>
So, uh if you're a large insurance company, you actually spend hundreds of millions of dollars on legal fees. Right? So, that is something that is not even tied to the patient experience that there's a large amount of optimization you can do there and to speed things up. Right? Um there's regulatory concerns that in certain jurisdictions like California, things are very litigated. Um you want to figure out how how to deal with those. Um there's a whole bunch of middle parties that that are involved as well uh that are also inefficient. So, depending on the customer, everybody has a different goal.
</details>

但在我们的交流中，情况总是像这样：我们有一个非常明确的问题要用技术来解决，我们先解决那个问题。之后，相关的洞察才开始显现出来，让人觉得：“噢，原先我都不知道自己的业务有这方面的情况，我们接下来解决这个问题吧。”所以就是这样。

<details><summary>Original English</summary>
Um but in our conversations, it's it's always been like we have this very obvious problem to solve with technology. Let's solve that first. Um and again, the insights start surfacing afterwards of being like, "Oh, I didn't know that about my business. Let's solve that afterwards." So.
</details>

### 模型分类与决策 API

是的，这个问题是关于 Jv 里的决策 API。

我不知道大家有没有看到大会正在分发的《AI 新闻》纸质版，其实我正在为它写一篇文章。我们使用分类模型已经很长时间了，我对此通常有很明确的看法。今天它还没见报，会在后面的版本中刊出。

<details><summary>Original English</summary>
Yeah, so the question is about decision APIs in Jv. Um as part of the I don't know if anybody's seen the paper um copies of the AI news that are that the conference is handing out. There's actually an article that I'm writing for that. Um so, we we've been using classification models uh for a long time. I've generally had uh strong opinion on that. Hasn't come out today. It's coming out in a later edition.
</details>

我认为它非常有用，但大语言模型并不是解决一切问题的正确方案，对吧？所以当我们谈到这一点时，人工智能的这个细分领域也是可以进行拆分的，对吧？分类、信息抽取，对比那种更复杂的基于决策的模型。对我们来说，成本真的非常重要，这也是我们同时训练自己模型的原因。准确性非常重要，还有幻觉问题也是。所以我认为 Jv 的出现并没有那么令人意外，更令人意外的反而是它竟然花了这么长时间才出来。因为我认为那种“对每个问题都追求大语言模型 token 级别的极致推理”的现象持续了很长一段时间，直到今年我们开始更多地考虑成本问题。所以一旦 Javis 这类东西已经出现，你可以去进行测试，但我们带着同样的构想构建了自己的模型。所以就是这样。

<details><summary>Original English</summary>
Um I think it's very useful, uh but LLMs are not the right solution for everything, right? So, when we talked about this, right? This segment of AI can be split up as well, right? Classification, extractive uh versus sort of the more complex decision-based ones. Uh so, for us cost is really important. So, that's why we trained our own models as well. Accuracy is really important and hallucinations as well. So, I think Jv was not as surprised that it came out. It was more so a surprise of how long it took because I think the LLM like token max reasoning for every problem phenomenon lasted for a very long time until we started thinking about costs a lot more this year. So, uh once Javis sort of hit already, we could you can test it out. Um but we've sort of built our own models with the same paradigm in mind. So.
</details>

### 行业影响与理赔周期

>> 是的，我来回答第二部分。作为一个机构，我们还没有把更广泛的行业推动到我们所希望的程度，对吧？也就是说，能宣布我们让所有患者的理赔时间平均缩短了 5 天。我们很乐意能够这样说，但我们目前还没达到那个阶段。对于特定的机构，比如我们在官网上有一些案例研究，我也很快放了一些上去。在各业务线上，有一些在降低成本和提升速度方面的显著成果。你可以去查看那些案例，如果你们想了解这方面更具体的背景信息，我们也可以在会后交流。

<details><summary>Original English</summary>
>> Yeah, so I'll answer part two. Um so as an organization we have not moved the broader industry um to the extent we want, right? So, to say that we can say we've reduced the the claim uh time by 5 days on average for somebody across every patient. We'd love to say that. We we're not in that position yet. For specific organizations like we had some case studies on the website. I quickly put put some up as well. There's some significant ones within lines of business uh for cost reduction and speed. Um so, you can check those out and we can chat afterwards as well if you're looking for more specific sort of context on that, too.
</details>

>> 是的，初次受伤或受损通报，或者取决于具体的子领域。是的，因司法管辖区而异，处理这些事务时还有周转时间上的要求。例如在得克萨斯州，你在处理理赔时只有几个小时的时间就必须给出答复；而在其他州，你可能需要 7 天或 21 天内给出答复。现在情况变得更复杂了，因为如果你是一名在工厂工作了比方说 30 年的工人，你已经 60 岁了，你就会有很庞大的病历档案，对吧？

<details><summary>Original English</summary>
>> Yeah, so so the the first notice uh of injury or loss um or and depend depending on the on the sub domain. Yes, um so depending on the jurisdiction there's also turnaround time requirements when handling these. So, for example in Texas you only have a few hours of processing a claim to get an answer. In other states it might be 7 days, 21 days that you need to get a response. Now, it gets more complicated because if you're a worker who's been working in a factory, let's say for 30 years, you're 60 years old, you're going to have large medical record file, right?
</details>

所以这里面以及初步报告中包含大量的信息，但要做完整的理赔分析，你必须回头去尝试调取这些记录。也许你因为结婚改了名字，也许你搬迁过城市、换过医疗服务提供方，对吧？所以你必须去重建那段完整的历史。而且我认为，遗憾的是，在很多涉及诉讼的案件中，也有故意遗漏信息的情况，原因在于许多机构尚未完成数字化转型，案件处理速度不够快。因此，如果只要这些就够了的话，那就会快得多，但遗憾的是，或者说更符合现实的情况是，这背后还有一个宏大得多的背景故事。

<details><summary>Original English</summary>
So, there's a lot of information here and in the initial report, but to do a full claim analysis you have to go back and you have to try to pull those. Maybe your name changed because you got married. Maybe you moved uh cities, providers, right? So, you have to reconstruct sort of that that full uh history as well. Uh and I think unfortunately in a lot of litigated cases there's information that's left out uh as well on purpose to due to the fact that a lot of organizations have not digitally transformed and can't process cases fast enough. So, uh if this was all that's needed, this would be uh much faster, but unfortunately or more realistically, there's a much broader backstory as well.
</details>