---
author: Latent Space
date: '2026-10-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zlD-CkLVKtU
speaker: Latent Space
tags:
  - ai-agent
  - saas-replacement
  - build-vs-buy
  - software-cloning
  - agent-evaluation
title: 如何干掉你的 SaaS：用 AI 智能体替代一款每年 43,000 美元的活动软件
summary: 讲者称，其团队为替代一款报价每年 43,000 美元的活动管理软件，举办了 Kill My SaaS 挑战赛，并介绍参赛者的做法、AI 评审与人工评审的差异、获奖结果，以及自有软件需要自己维护的取舍。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - InEvent Space
  - AI Engineer
products_models:
  - SessionBoard
  - Claude Code
  - Codex
  - Convex
  - Next.js
  - Firecrawl
media_books: []
status: evergreen
---
### 实验缘起
每隔几周，我的信息流里就有人声称 AI 杀死了 SaaS。然后另一个人回复说，用 vibrational code 解决真正的业务问题是不可能的。到处都是这样的说法，诸如此类。所以在 InEvent Space，我们决定不再争论，而是试着干掉一款真正的 SaaS，并在真实的商业活动中评估它。这是为这个实验专门录制的一期节目，欢迎分享你的想法。

<details>
<summary>Original English</summary>
Every few weeks, someone on my feed claims that AI killed SaaS. Then someone else replies that it is impossible to solve a real business problem using a vibrational code. Here and there, there and there, and so on. So at InEvent Space, we decided to stop arguing and try to kill real SaaS and evaluate it at real business events. This is a special episode recorded for this experiment, so share your thoughts.
</details>

你真的就是把它丢进 LLM，干上大约两三个小时，就能把一切做到像素级完美。

我通常是负责搭建 Sessionboard 的人，所以是我不得不在我们实际用的 Sessionboard 上受罪。我不能让一家资产数百万美元的公司的人去刷新缓存，只因为我们做的东西坏了。

<details>
<summary>Original English</summary>
You literally bring it into the LLM and work for about 2 hours, 3 hours. You just create everything pixel perfect.

I'm usually the one who has to set up the Sessionboard, so I was the one who had to suffer with our actual Sessionboard. I can't ask someone who works at a multi-million dollar company to refresh their cache because something we did broke.
</details>

### 背景与购买软件的问题
先简单交代背景：我经营两家公司：InEvent Space 和 AI Engineer。AI Engineer 为人工智能行业举办会议。我们当时在考虑用 Sessionboard 这类活动软件来管理我们的演讲者。我们购买一堆软件，价格从几万到几十万美元不等，以适应我们各种活动、平台和需求。就我们需要的这款软件，对方给出的报价是我们四场活动每年 43,000 美元。4.3 万美元可是很多 token。而且当我们购买现成软件并要求修改时，他们往往要花 3 到 6 个月，或者根本不会真正交付我们想要使用的东西。我们已经举办过七场 AI Engineer 活动，知道这个软件品类有多糟糕。

<details>
<summary>Original English</summary>
So, a quick context: I run two companies: InEvent Space and AI Engineer. And AI Engineer hosts conferences for the artificial intelligence industry. We were considering event software, such as Sessionboard, to manage our speakers. We buy a bunch of software ranging from tens to hundreds of thousands of dollars to suit our various events, platforms, and needs. For this particular software we needed, they gave us an estimate of $43,000 per year for our four events. 43 thousand is a lot of tokens. And when we buy software off the shelf and request changes, it often takes them 3 to 6 months or never to actually ship what we want to use. We've held seven AI Engineer events, and we know how bad this software category is.
</details>

多年来，我把这一条写进了我们的公司创立协议。我可以真的给你看：没有我的明确许可，任何人都不能在内部开发软件，因为在一般的企业管理中，很容易得“非我发明”综合征，也很容易被分心去开发本来可以直接买现成的软件。今年我改变了想法。我认为智能体终于足够好了，我们可以拥有个性化软件，我正在用自己的真金白银测试。

<details>
<summary>Original English</summary>
For years, I had this written into our literal company founding agreement. I can literally show you that no one could create in-house software without my explicit permission because it's so easy to get the "not invented here" syndrome in general business management, and it's so easy to get distracted by creating off-the-shelf software that you can just buy off the shelf. This year I changed my mind. I think agents are finally good enough that we have personalized software, and I'm testing it out with my real money.
</details>

关于购买软件，我们还发现：SaaS 通常是一堆东西的打包。这个供应商卖给我们的东西，我们只用了大约三分之一，而没用的部分没有任何折扣。于是我临时发起了一个挑战，叫 Kimai SaaS。任何人都可以报名，我会给他们该软件的规格说明和需要完成的任务。最难的部分是从真正的买家那里得到真实的评价，他们不关心你怎么实现，只想把事情做成。而这基本上就是我的活动策划团队。他们不懂技术，不在乎你用什么技术栈、什么智能体、什么模型。他们不在乎是开源还是闭源，也不在乎自己是否真的会购买和使用。最终有 72 个人或 72 个团队报名。其中大多数仍在活跃且开源，我们提供了所有这些项目的链接，你可以自己去试。

<details>
<summary>Original English</summary>
Another thing we discovered about buying software is that SaaS is usually a bundle of things. We use about a third of what this particular supplier sold us, and there is no discount for what we don't use. So, spontaneously, I created a challenge called Kimai SaaS. Anyone can sign up and I give them the specifications, the tasks to be completed for that particular software, and the hardest part is getting a real evaluation from real buyers who are not interested in how you implement something. They just want to do something. And this is, essentially, my event planning team. They are not technical, they don't care what stack you use, what agent you use, what model you use. They don't care if it's open source or closed source, they don't care if they actually buy it and use it. So, in the end, 72 people or 72 teams applied. Most of them are still active and open source, and we provide links to all of them, so try them out for yourself.
</details>

### 为什么比看起来复杂
那为什么它比看上去更复杂？我想用我们自己作为例子，说明这种面向中型企业的日常软件。它不是 Salesforce，也不是一天就能写完的东西，而是介于两者之间，有价值数十亿美元的糟糕软件，被普通人使用。我们的软件仍然相对复杂。我想，对不在这个行业或没有相关经验的人来说，很容易理解为什么它难以替换。比如，这里有一些需要完成的任务：演讲者提交报告，评审人评估报告，评审委员会接受报告。接着我们需要一个演讲者门户来上传肖像和幻灯片。演讲者如果有任务没完成，会收到提醒。我们把他们安排进日程中的会议室，我们调整日程，他们更改姓名，还得在公开议程上正确显示，诸如此类。他们应该能添加联合演讲者。他们是赞助商。呃，我们还得为特邀演讲者、赞助商、与会者等等全部再来一遍。而且一个人可以同时有一个、两个或三个角色。他可以既是演讲者、赞助商又是参与者，或者你可以是组织者、志愿者、供应商，天知道还有什么。有时我们只是因为那个特定情况就临时编规则。

<details>
<summary>Original English</summary>
So why is it more complicated than it seems? I want to use us as an example of just such routine software for mid-level businesses. You know, it's not Salesforce, it's not something you write in a day, it's something in between, where there are billions of dollars of just terrible software that ordinary people use. Hmm, our software is still relatively complex. I think it's easy for people who aren't in or have no experience in this type of business to understand why it's hard to replace. Hmm, for example, here are some tasks that need to be completed. The speaker submits the report, the reviewers evaluate the report, and the review committee accepts the report. Now we need a presenter portal to upload a portrait and slides. Presenters receive reminders if they have not completed some tasks. We place them in the room on the schedule, we move the schedule, they change their name, they have to appear correctly on the public agenda, all sorts of things. They should add co-speakers. They are sponsors. Uh, we'll have to do it all over again for guest speakers, sponsors, attendees, and all that. And one individual can have one, two, or three roles at the same time. He can be a speaker, sponsor, and participant, or you can be an organizer, volunteer, vendor, God knows what. Sometimes we just make up rules on the fly, just because of that particular situation.
</details>

活动组织者非常厌恶风险，这是有道理的。如果软件让我们比截止日期晚了一周，人们就会出现在错误的地方，或者会议干脆办不成。这一切以前都在我们身上发生过。我们得支付 term fees、union dues，或者一些在底层看起来非常糟糕的东西，而成员只是把它当作理所当然，就好像只是因为他们买了票才发生的一样。而且我认识的人里，没有谁喜欢自己的会议应用。

<details>
<summary>Original English</summary>
Event organizers are very risk-averse, and for good reason. If the software delays us a week past the deadline, people show up in the wrong place, or the conference simply doesn't happen. All of this has happened to us before. We have to pay term fees, union dues, or something that just looks super nasty under the hood, and members just take it for granted, like it's just happening because they're paying for a ticket. And no one I know loves their conference app.
</details>

### 比赛如何进行
下面是我们如何办这场比赛。开发者收到我写的说明、对实际产品的视频概览，以及我在说明中附上的 42 张截图。我为获胜者拿出 10,000 美元；而且由于没有人会在 20 美元的云计划上构建这个东西，我们对任何认真尝试的人最高提供 500 美元的 token 报销，因为确实有几次失败的尝试。最终决定基本上由我真实的活动团队做出，所以不是我在选，而且是一种半盲评估。

<details>
<summary>Original English</summary>
So, here's how we ran the contest. The developers received the brief I wrote, a video overview of the actual product, and the 42 screenshots I sent inside that brief. And I put up $10,000 for the winner, and since nobody builds this on a $20 cloud plan, we actually offered up to $500 in token reimbursement to anyone who would make a serious attempt, because there were a few, um, failed attempts. The final decision is essentially made by my real-life event team, so it's not me choosing, and it's, um, a half-blind evaluation.
</details>

### 参赛者反复栽跟头的地方
A. 那是他们一直被绊倒的地方。大约有三件事。第一是门户。演讲者、特邀演讲者和赞助商需要各自的门户，而大多数应用只创建了一种门户，不太灵活。所以我马上注意到生活质量上有不少改进，对此我很欣赏。嗯，你是少数真正能分辨表单和门户区别的人之一，我很喜欢。嗯，我要说最大的批评之一，别误会，再说一遍，你做的一切都很棒。我们有好几个门户。例如，我们有 Call for Proposals（CFP）门户、赞助商门户和特邀演讲者门户。能够为这些不同的门户设置一个管理员并分别配置它们，也是 SessionBoard 里有的功能，但这是我在你的门户里没注意到的少数几件事之一，不像其他人那样。

<details>
<summary>Original English</summary>
A. That's what they kept tripping over. There were about three things. The first is portals. Speakers, guest speakers, and sponsors needed their own portal, and most applications created only one type of portal, which was not very flexible. So, right away I noticed a bunch of improvements in my quality of life, so I appreciated that. Hmm, you were one of the few who could actually make out the difference between a form and a portal, which I really liked. Hmm, one of the biggest things I would say is a critic, and don't get me wrong, again, that's great for anything you've done. We had several portals. For example, we have a Call for Proposals (CFP) portal, a sponsor portal, and a guest speaker portal. The ability to have an administrator for these multiple different portals and configure them differently is also a feature that is available in SessionBoard, but it is one of the few things that I didn't notice in your portal, unlike others.
</details>

人们绊倒的第二件事，实际上是拖拽，这是最复杂的界面元素之一，模型很难做到。所以我们基本上测试的是：拖动时会话会移动吗？你能告诉我它是已确认还是已更新，是模棱两可，还是以任何形式可行？因为显然你不能让一个人同时出现在两个会话里，也不能在同一个时段为多个会话预订同一个房间。但我喜欢那些提示。它们告诉我如何设置、如何操作。问题是，呃，没有提示，嗯，似乎是叠加在上面的东西应该做你被告知要做的事。比如“哦，点这里来添加会话，或者点上面来添加会话。”我想：“为什么我不能直接点一个按钮在那里添加会话？”呃，我真的很喜欢你清晰的日程拖放。呃，我的标准之一是：你能拖放日程吗？因为这让我疑惑：“嘿，他们真的遵循了说明吗？”

<details>
<summary>Original English</summary>
The second thing people have stumbled on is effectively dragging one of the most complex interface elements, which is difficult for models to convey. So, essentially what we tested was whether the session moves when you drag it? And can you tell me if that's confirmed or updated, or if it's ambiguous, or if it's possible in any form, because obviously you can't have one person in two sessions or book one room in one time slot, uh, for multiple sessions. But I liked the tips. They told me how to set it up and how to do it. The problem was that, uh, there were no hints, um, it seemed like overlaying on top of that was supposed to do what you were told. Like, "Oh, click here to have a session, or click above to have a session." I thought, "Why can't I just click a button to add a session there?" Uh, I really liked your clear drag and drop with the schedule. Uh, one of my criteria was, can you drag and drop the schedule? Because it made me ask, "Hey, did they actually follow the instructions?"
</details>

第三件事是添加一场演讲，而不是假装通过参与请求表单提交，而对于受邀演讲者或 VIP，这是必需的。这三件事在我们 SessionBoards 的文档里都没有写清楚，但如果你像真实的人一样使用这个产品，马上就会发现它们。

<details>
<summary>Original English</summary>
The third was adding a talk without pretending that you were sending it through the participation request form, which is required for an invited speaker or VIP. None of these three were well described in our SessionBoards documentation, but you'll find them right away if you're using the product as a real person.
</details>

### AI 评审与人工评审
比赛期间，我们还发布了自己的人工智能评审。它的目的不是挑选获胜者，只是让大家运行自己程序时的一个合理性检查。基本上就是一个没有 RL 部分的 RL 环境。呃，只是一种让人们去 conquer hills 的环境。所以我们的评估基本上是：Claude 进入每个角色，走完我们写成正常用户流程的 20 个场景。你可以在这里看到一个快速版本。而且事实上又用 Claude 来做评估。所以按钮怎么命名、放在哪里，都可以有灵活性。如果你以后也办这样的比赛，呃，我强烈推荐：录下你自己点击完整程序的过程，把它变成脚本，发布出来，让大家去 conquer the hills。

<details>
<summary>Original English</summary>
During the competition, we also released our own artificial intelligence judge. It wasn't intended to pick a winner, it was just a sanity check for people to run their programs. Essentially, an RL environment without the RL part. Uh, just a kind of environment for people to conquer hills. So essentially our assessment was that Claude went into each role and went through 20 scenarios that we wrote as normal user flows. You can see a quick version here. And, in fact, used Claude again for evaluation. So you can get flexibility in how to name the button and where to place it. If you ever run a competition like this, uh, I highly recommend it. Record yourself clicking through the full program, turn it into scripts, release them so people can conquer the hills.
</details>

呃，我觉得它挺受欢迎的。我们用这些评估跑了 56 个程序。其中 40 个有足够的覆盖度可以排名。前七名彼此相差在 2.3 分以内，基本上就是饱和了。我觉得总体非常成功。所以，爬山式优化对比自动化评估，我认为这是自我学习非常有用的第一步。例如，我们有一些例子，从 Lectern 到 Curtain Call，他们向员工具体指出得分较低的方面，然后很快就 conquer 了这些 hills。我认为这对刚接触 SAS 编程的人来说是个很好的第一个作业。

<details>
<summary>Original English</summary>
Uh, and I thought it was pretty popular. So we ran 56 programs through these assessments. 40 of them had sufficient coverage for ranking. The top seven ended up within 2.3 points of each other, which is basically saturation. And I think overall it was very successful. So, hill climbing versus automated assessment, I think that's a very useful initial step of self-learning. For example, we had some of these examples, from Lectern to Curtain Call, that pointed out to their employees specifically the areas where they were scoring lower, and just conquered the hills very quickly. I think this is a good first assignment for people getting into SAS coding.
</details>

这适用于可以独立创建的部分，但我们也发现它们需要被链接进一个共同的应用。而这正是很多人出错的地方。他们浪费了大量 token，并且重复实现了彼此没有关联的功能，因为他们并没有真正测试自己的应用，只是在交付它。所以，在 AI 评审之后，我们真正的评审是活动评估团队，由 Kelsey 带领，她是 AI engineer 的运营负责人。评分与 AI 评审的相关性相当差。例如，AI 评审前十名中有六个，实际上被我们的人类评为较弱。最后，我们的获胜者在 AI 评审排行榜上排第 19 名。所以相当弱。只是与 R-squared 有一些相关性。但它们是完美的，而这从来不是本意。所以相关性的某些方面是有意的。我们允许人们按自己的品味偏离规格。我们鼓励他们这样做，因为老实说，这也关乎雇用能带着品味编程的人。我们希望人们理解工作的本质，而不是这份特定的规格。与其机械地克隆一个产品，你实际上可以定义什么是良好的用户体验，并扮演我们真实测试者的角色。嗯，不管我们主观上是否同意他们。

<details>
<summary>Original English</summary>
And this works for parts that can be created independently, but we also found that they need to be linked into a common application. And this is where many people went wrong. They were wasting a lot of tokens and duplicating features without any connection because they weren't really testing their app, they were just shipping it. So really our real judge after the AI judge was our event evaluation team led by Kelsey, who is the head of operations at AI engineer. The ratings had a pretty poor correlation with the AI judge. For example, six of the top ten AI judges were actually rated as weak by our humans. And in the end, our winner took 19th place in the AI judges leaderboard. So it's pretty weak. There is just some correlation with R-squared. But they are perfect, and this was never intended. So some aspects of the correlation were intentional. We allowed people to deviate from the specification to their own taste. We encouraged them because, to be honest, it's also about hiring people who can program with taste. We want people to understand the essence of the work, not this particular specification. And instead of mechanically cloning a product, you can actually define what a good user experience looks like and take on the role of our real testers. Hmm, and whether we subjectively agree with them or disagree.
</details>

所以实际上这场比赛并不客观。类别定义不清。规格不清。嗯，所以，如果有清单，我们可以发布。我们发布了。它可以被克隆，但我们真正在人们身上寻找的是品味，那些操控编码器的人。呃，如果是你，我们肯定在招人。嗯，我们的一位开发者 Open Search 实际上告诉我们，他们引以为豪地构建进应用的大部分东西，AI 评审根本没有覆盖。他们是对的。我们之所以发现这一点，是因为每个应用都有人在评审。

<details>
<summary>Original English</summary>
So in reality this competition is not objective. The categories are unclearly defined. The specification is unclear. Hmm, so, you know, if there was a checklist, we could publish it. We published it. It can be cloned, but taste is what we really look for from people manipulating coders. Uh, and if it's you, we're definitely hiring. Hmm, one of our developers, Open Search, actually told us that most of what they were proud of building into the app wasn't covered by the AI judge at all. And they were right. And we discovered this because we had people reviewing every app.
</details>

### 参赛者如何构建克隆应用
那么人们究竟是如何创建这些克隆应用的？首先，对那些要杀死 SAS 的人来说有个好消息：几乎每个人都交出了有分量的东西。公开仓库的中位数是 91,000 行代码，人们让智能体运行了好几天。Cloud Code 和 Codex 几乎不相上下。更有趣的是，66 份提交的 papers 中有 40 份两者都用了。几乎每个人都在创建模型家族。三位入围者都用了 GPT-3，但另外 66 个里也有 50 个用了。所以没有 alpha。我最感兴趣的是他们如何分工，因为我自己不这样做。我倾向于每个项目只用一个模型，让所有上下文都留在一个地方。所以我想要一个 Codex 线程涵盖一切，能够发现我过去做过的所有事情。嗯，我也想要一个 Cloud Code 线程，为我觉得最合适的任务做同样的事。结果发现，这些开发者中很多人并不这样做。他们实际上会切换角色。整个过程中有一个有趣的部分：我们要求开发者把他们的请求和过程文档提交到 GitHub。这是他们自愿做的工作。所以你可以准确读到他们是怎么做的。

<details>
<summary>Original English</summary>
So how did people actually create these cloned apps? First, good news for those who kill SAS: almost everyone sent something substantial. The median public repository was 91,000 lines of code, and people were running agents for days. Cloud Code and Codex were virtually equal. And even more interestingly, 40 of the 66 submitted papers used both. Almost everyone creates families of models. All three finalists used GPT-3, but so did 50 of the other 66. So there is no alpha. I'm most interested in how they divide the work, because I don't do that myself. I tend to keep one model for projects so that all the context stays in one place. So I want one Codex thread to cover everything, to be able to discover all the past things I've done. Um, I want one Cloud Code thread to also do the same for the task I find most suitable. It turns out that many of these developers don't. They actually switch roles. And one interesting part of this whole process is that we asked developers to commit their requests and process documentation to GitHub. And this is their voluntary work. So you can read exactly how they did it.
</details>

总体上，我们研究了他们提交的内容，以及他们如何使用这些混合模型的情形。我们发现了三种模式。第一，一个智能的模型决定做什么，然后较便宜的模型像 slot gun 一样记录指定的内容。一个例子是 Collab Board HQ。他们让 Cloud Plan 和 Review，而 Codex 写了大部分代码。第二，一个模型构建，另一个测试。通常控制浏览器或测试更好的那个负责检查。嗯，我觉得现在是 GPT Codex。第三，没有模型为自己的工作背书。Green Room HQ 在不同的工作树里运行 Cloud Team 和 Codex Team，任何一方在另一方审核通过之前都不能合并。这就是，呃，按策略验证与策略之外验证的原则。嗯，智能体往往对自己的工作比对别人的工作更宽松（原文为 economical）。我认为这也反映了人类的做法。

<details>
<summary>Original English</summary>
Overall, we studied what they sent and how they use these mixed model situations. And we discovered three patterns. First, an intelligent model decides what to do. And then the cheaper model is a slot gun that records what was specified. So, one example was Collab Board HQ. They had Cloud Plan and Review, while Codex wrote most of the code. Second, one model builds and the other tests. And usually the one who controls the browser or tests better checks. Hmm, I think it's the GPT Codex now. And thirdly, no model endorses their own work. Green Room HQ ran the Cloud Team and Codex Team in separate work trees, and neither could merge until the other had vetted it. And it's just, uh, the principle of verification according to policy versus verification outside of policy. Um, agents tend to be more economical with their own work than with the work of others. And I think that also reflects what people do.
</details>

### 三位入围者的访谈
所以，基本上这是一个克隆过程，我们分析了数据等等。我们分享了一些初步发现。嗯，但现在来谈谈入围者。我们采访了全部三位。他们很友好地来参加录制访谈并同意录制。嗯，这是定性的一面：人们如何与人谈论这个过程并理解他们。另外，在颁奖之前，我们也想确认他们是真实的。

<details>
<summary>Original English</summary>
So, basically, it's a cloning process, we analyzed the data and all that. We share some of our initial findings. Um, but now let's talk about the finalists. We interviewed all three. And they were kind enough to come to the recorded interview and agree to this recorded interview. Um, and that's the qualitative side of how people talk to people about the process and understand them. Plus, we also wanted to make sure they were real before we awarded the prizes.
</details>

他们所有人报告的第一件事，是在任何代码被提出或编写之前，他们已经做了多少工作。他们实际上做了大量前期研究和规格撰写。Marco 以前克隆过应用或客户端。他的做法是先规划一切。UX 界面准备好后，我唯一做的就是坐下来 8 到 9 个小时，尽可能详细地规划整个数据模式、业务逻辑，并把任何东西都写成伪代码。嗯，有点好笑，因为如果你把我 4 到 5 年前很喜欢的这些作业——我喜欢设计——直接丢进 LLM，干上大约两三个小时，你就能得到这整个像素级完美的东西。

<details>
<summary>Original English</summary>
The first thing they all reported was how much work they had done before any code was proposed or written. They actually did a lot of preliminary research and writing of specifications. So, Marco has cloned applications or clients before. His role is to plan everything first. Once the UX interface is ready, the only thing I do is sit down for 8-9 hours and plan the entire data schema, business logic in as much detail as possible, and literally pseudocode anything. Hmm, it's kind of funny because if you take these assignments that I loved 4-5 years ago, and I love design, and literally put them into an LLM, and you go for about 2 hours, about 3 hours, you just get this whole thing pixel perfect.
</details>

CartFueled 的 Yazin 从研究开始。他在写规格之前扫描了整个 SessionBoard 帮助站点。是的，嗯，所以第一步，甚至在直接提出建议之前，是通过大量研究完成的。嗯，我拿了一份 Google Doc，转换成 Markdown 文件，然后还运行了 Firecrawl。我是说，他们……他们扫描了全部 SessionBoards、帮助门户，以及搜索结果中出现的其他一些类似的站点。是的，我只是想尽可能多地获取信息。

<details>
<summary>Original English</summary>
Yazin from CartFueled started with research. He scanned the entire SessionBoard help site before writing the specification. Yeah, um, so the first step, even before, you know, making direct suggestions, was done with a lot of research. Hmm, I took a Google Doc, converted it to a Markdown file, and then I also ran Firecrawl. I mean, they...they scanned all of SessionBoards, the help portal, and a few other sites that were something like that that came up in the results. And yes, I was just trying to get as much information as possible.
</details>

而且，嗯，我们的第三位入围者 Valentin，把大部分精力放在了 defense 上。他把它们做成了任何人都能用的模板。所以我把它做成了模板，而不是形式化。在很多项目里，我不得不削减这些旧工作，而这是个完美的例子，说明我多么讨厌偷懒，每个人都一样，如果你必须管理这个项目，你会希望能在上面写代码，比如说。所以我花了太多时间贴链接、贴各种代码评审之类的。现在我直接把它做成了 GitHub 模板。所以每个新项目、每个新仓库，我都会克隆这个模板，这样我就不必全部砍掉。但我没有一份说“这是我做的”的 Google Doc。是的，它是完全开源的。

<details>
<summary>Original English</summary>
And, um, our third finalist, Valentin, put most of his effort into defense. And he turned them into a template that anyone can use. So I made it a template, not formalized it. In many projects I have to cut back on this old work and this was a perfect example of how I hate laziness, as does everyone, and if you have to manage this project you want to be able to write code on it, for example. So I spent so much time posting links, posting any code reviews, whatever. And now I just made it a GitHub template. So for every new project, every new repository, I'll clone this template so I don't have to cut all of it. But I don't have a Google Doc that says, here's what I did. Yes, it is completely open source.
</details>

他的智能体随后画出了产品中的每个流程，然后他才规划谁并行做什么。这是把一切搬上线的大型研究。基本上，我只是问 Codex：“嘿，伙计，你应该能给我画出这个应用每一个功能的每个流程。”令人惊讶的是，那是一堆 YouTube 视频，他一帧一帧地截图，去想“哦，好，原来是这么回事。”然后他得到一个巨大的 Markdown 文件夹，里面是每个功能的预期。他唯一说的是：“好，把它拆分成可以同时做的事情。有些功能可能重叠，所以你可能得按顺序做。但基本上创建一个计划：什么需要先开始，每一步你可以同时用多少个智能体，然后全部做完。”一切完成后，我对所有东西做了手动检查。它能用，我想：“哦，等等。这不理想。为什么？哦，为什么？因为我看到它从来没有在本地真正运行过这个应用。”好，那么下一步就是用本地的应用重复整个流程。

<details>
<summary>Original English</summary>
His agents then drew each flow in the product before he planned who would work on what in parallel. A huge study of moving everything online. And basically, I just asked Codex, "Hey, dude, you should be able to draw me every flow of every single function of this app." And what's amazing is, it was a bunch of YouTube videos, and he was taking screenshots frame by frame to think, "Oh, okay. That's what happened." And then he had a huge Markdown folder with expectations for each feature. And the only thing he said was, “Okay, break it down into things that can be done at the same time. Some features may overlap, so you may have to do this sequentially. But basically create a plan of what needs to start, how many agents you can do at once for each step, and then do it all.” Once everything was done, I did a manual process of everything. It works, and I thought, “Oh, wait. This is not ideal. Why? Oh, why? Because I see that it never actually runs the application locally." Okay, then the next step is to repeat the entire process with the application locally.
</details>

Marco 把 Session Board API 视频教程和文档直接交给了 Claude。呃，我真的就是拿了 Sean 分享的视频，拿了 Session Board 的文档和 API 帮助，放进 Claude，告诉它使用 Convex 和 Next.js，我喜欢我最爱的技术栈，因为显然速度等等相当重要。Convex 就是给你一个实时数据库。超级简单，几乎不费什么功夫就能给你非常高效、方便的东西。

<details>
<summary>Original English</summary>
So, Marco passed the Session Board API video tutorial and documentation directly to Claude. Eh, I literally took the video that Sean shared. I took the documentation, the API help from Session Board. I was, I was, I put it in Claude. I told him to use Convex and Next.js, and I liked my favorite stack because obviously speed etc. is pretty important. So, Convex simply provides you with a real-time database. It's super simple, it will literally give you something highly productive and convenient without much work. Emm.
</details>

如果你看所有这些片段，会注意到没有人说他们输入一个提示就走人了。事实上，提示几乎是最后一步，是在你积累了对问题、原型图、文档、规格等一切的完整理解之后才做的。嗯，大部分工作是弄清楚软件究竟做什么，然后他们才可以偏离它。

<details>
<summary>Original English</summary>
So, if you watch all these clips, notice that no one said they entered one invitation and left. In fact, the invitation was almost the last step you supposedly take after you accumulate a full understanding of the problem, mockups, documentation, specifications, and all that kind of stuff. Hmm, most of the work was figuring out what the software actually does, and then they can deviate from that.
</details>

### 像真实用户一样反复使用
三位入围者做的另一件事是不起眼的部分。他们像真实用户一样，一遍又一遍地使用自己的产品。其中一位写道，智能体非常擅长创建，但相当不擅长发现 UX 问题。例如，他们有一个上传肖像照片的功能，会把照片保存在某处，但公开的演讲者页面甚至无法从同一个地方读取，因为它是独立编写的。Valentine 的版本是一个 5 分钟测试。如果他不能在 5 分钟内顺畅地走完产品，就说明缺了什么。所以我只是设身处地地说：“好，如果我只有 5 分钟来测试一个产品，会是什么样？”嗯，如果这 5 分钟不顺利，我会重做整个流程。嗯，也就是：“好，肯定缺了什么。”“要么是产品的上下文，要么是期望的上下文，或者也许根本不是检查产品当前状态的问题。”但我的目标再次是绝不手动做任何事，比如“哦，我不喜欢这个。”或者：“哦，我不喜欢它。”我只是，比如说：“好，这个 onboarding 太烂了。嗯，为什么？”然后我会让它检查 traces 来理解：“好，这是从哪来的？”是不是因为我们没有给出关于 adaptation 的指示？然后它会告诉我类似这样的话：“哦，嗯，有一个关于 adaptation 的小标题，adaptation 就是 adaptation，但我们不知道什么是好的 adaptation。”好，于是我知道这个过程不只是做 adaptation，还要问：“好，什么定义了 adaptation 的好路径？”什么定义了坏路径？所以我问它：“好，现在重做整个步骤、整个流程，但加入一个步骤来探索什么定义了好的 adaptation。”然后我们去做。

<details>
<summary>Original English</summary>
Another thing all three finalists did was an unglamorous part. They used their own products like real users over and over again. One of them wrote that the agent is very good at creating, but is quite bad at noticing UX issues. For example, they had a feature for uploading portrait photos that saved the photo somewhere, but then the public speaker page wasn't even readable from the same place because it was written independently. The Valentine's version of this was a 5-minute test. If he can't smoothly walk through the product in 5 minutes, something is missing. So I just put myself in your shoes and say, "Okay, if I only have 5 minutes to test a product, what would it be?" Hmm, and if those 5 minutes don't go smoothly, I'll redo the whole process. Hmm, that is: "Okay, something must be missing." "Either it's the context of the product, or it's the context of expectations, or maybe it's not about checking the current state of the product." But my goal again was to never do anything manually, like, "Oh, I don't like this." Or: "Oh, I don't like it." I just, for example, said: “Okay, this onboarding is crap. "Hmm, why even?" And I'll ask him to examine the traces to understand: "Okay, where does this come from?" Is it because we didn't give instructions on adaptation? And he'll tell me something like, "Oh, well, there was a subtitle about adaptation, and adaptation is just adaptation, but we have no idea what a good adaptation is." Okay, so I knew that the process wasn't just about doing the adaptation, but also about, "Okay, what defines a good path for adaptation?" What defines a bad path? So I ask him, "Okay, now redo the whole step, the whole process, but include a step that explores what defines a good adaptation." And then we do it.
</details>

Yazin 就是不停地点击，并记录一份修复清单。完成之后，我就收到这些视频，然后我得逐个看，那时我意识到：“好，在不同的查看模式之间切换其实真的很烦人。”所以我就这样做了：“对，实际上没有办法，你得登出再登入，然后我想：用户名和密码在哪？”然后我得把它们加上。所以，对，那时我意识到缺了一些显而易见的东西。于是，登录这些东西，然后我切换门户，然后我还加了 recent support，而且，你知道，我意识到有几个 UX 问题，嗯，对，就是些显而易见的东西，我看着它，想：“好，你知道，那我就让自己去修。”“所以我只是有一份清单，通过点击它来滚动浏览。”

<details>
<summary>Original English</summary>
Yazin just kept clicking and keeping a list of fixes. And once that was done, I just get sent these videos and then I have to go through them, and that's when I realized, "Okay, it's actually really annoying to have to switch between different viewing modes." So I did it like this: "Yeah, there was actually no way to like it, you had to log out and log in, and then I thought: where is the username and password?" And then I had to add them. So, yeah, that's when I realized that some obvious things were missing. So, the login stuff, then I switch portals, and then I also added recent support, and, you know, I realized there were a few UX issues like, um, yeah, just things that were obvious, and I was looking at it and I was like, "Okay, you know, then I'll let myself fix that." “So I just had a list that I was scrolling through by just clicking on it.
</details>

neck care 出现在我们并没有真正要求的地方。这是 Kelsey 谈 Confreres Results 页面。你的设置很棒。我给我们的内容经理看了，她说：“什么？这些都在一个页面上？你不用点进各个表单去看状态？”她只是说：“太棒了。”对，结构上做完之后看起来还行，但后来我想：“你知道，如果菜单重新组织，有图标，一切都在逻辑上契合，会更合理。”我想这是最终导致 Results 页面和 annotations 页面发生巨大变化的原因之一，因为它看起来非常像表格，然后，你知道，你试着让它看起来像真正的用户界面。

<details>
<summary>Original English</summary>
And neck care was showing up in places we didn't really ask for. Here is Kelsey on the Confreres Results page. Your settings were great. I showed it to our content manager, and she's like, “What? Is this all on one page? "You don't have to click on individual forms to see the statuses?" And she just said, "That's great." Yeah, structurally it looked okay after it was done, but then I thought, "You know, this would make a lot more sense if the menus were reorganized, and there were icons, and, you know, everything would logically fit together." And I think that was one of the things where it ultimately led to a huge change, um, in the Results page and also in the annotations page, because it looked very tabular, and then, you know, you try to make it look like a real user interface.
</details>

### 放弃“用 AI 彻底摧毁 SaaS”的想法
所以现在……是时候放弃我们能用 AI 彻底摧毁 SaaS 的想法了。克隆一个看起来能用的东西其实是容易的部分，我们已经用许多乍看之下确实是很好的克隆的应用证明了这一点。但仍然需要有人维护它、接收 bug 报告、凌晨 2 点去修。就在昨晚，我团队的 Flo 在我们的 Token Billionaires 节目开始前，往里扔了十几个 Codex 智能体，而会议当时已经在 AI engineer 上运行了。如果你弄坏了它，你就拥有它。你知道，现在很多人说相反的话：如果你拥有它，你就可以弄坏它。Kelsey 说得比我好。

<details>
<summary>Original English</summary>
So now…” It’s time to abandon the idea that we can completely destroy SaaS with AI. Cloning something that looks like it works is really the easy part, and we've proven this with many applications that were really good clones at first glance. But someone still has to maintain it, accept bug reports, fix it at 2:00 AM. Just last night, Flo from my team threw a dozen Codex agents into our Token Billionaires program right before it started, and the conference was already working on an AI engineer. If you break it, you own it. You know, and now many people say the opposite. If you own it, you can break it. Kelsey said it better than I could.
</details>

所以我们有几样相互关联的东西，是若干相互作用的 API 的混合。无论如何，我们想要这个通用系统，因为我们希望能够，比如说，注册数据进入赞助商门户，而赞助商门户可以直接进入我们的日程。我们在碎片化效应上遇到问题，而我们知道……足以基本上说：“嘿，我们想要更好的。”我们可以做得更好。我们需要这个更好。”“但我们没有时间。”呃，我们不能告诉智能体。我们不能允许那样，你知道，一旦出了问题，我们需要有人能修，纠正错误。所以，这就是我们有这个的原因。

<details>
<summary>Original English</summary>
So we have several things related to each other that are a mix of certain APIs that interact with each other. In any case, we want this universal system, as we want to be able to, say, registration data goes into the sponsor portal, and the sponsor portal can go straight to our schedule. We're having problems with the fragmented effect, and we know... enough to essentially say, "Hey, we want better." We could do it better. We need this better." "But we don't have time." Uh, we can't tell the agents. We can't allow that, you know, as soon as something breaks, we need someone who can fix it, correct the mistake. So, that's why we have this.
</details>

这里又是 Kelsey 讲当赞助商发现错误，而供应商的回应是清除缓存时是什么感觉。我们的赞助商来找我们说：“嘿，我们有个错误。就是，我无法取消这些申请。”我不得不回去找我们的在线聊天支持，然后，你知道，做所有那些事，然后他们又得回去找他们的工程师，做所有那些事。然后他们的工程师又回去找他们的在线聊天支持人员，那人回复我说：“嘿，你能试试刷新缓存吗？”“我就想：‘我不会为了修复前两步的一个 bug 而告诉我们的赞助商去刷新缓存。’”这是那种用户可访问性错误之一，我不能让一家资产数百万美元的公司的人去刷新缓存，只因为我们做的东西坏了。

<details>
<summary>Original English</summary>
And here's Kelsey again about what it's like when a sponsor detects an error and the provider's response is to clear the cache. Our sponsor came to us and said, “Hey, we have a mistake. "It's like, I can't cancel these applications." And I had to go back to our live chat support about it and then, you know, do all of that, and then they had to go back to their engineers and do all of that. And then their engineers went back to their live chat support agent who answered me and said, "Hey, can you try refreshing your cache?" "And I'm like, 'I'm not going to tell our sponsor to refresh the cache to fix a bug two steps before that.'" And this was one of those user accessibility mistakes where I can't ask someone who works at a multi-million dollar company to refresh the cache because something we did broke.
</details>

所以存在某种程度的责任，我不在乎你怎么修，我需要它不出问题。所以这就是责任的层级，在这个层级你可以说：“这是你所有材料的心智组成部分。”“这就是为什么我告诉 Yazin，在组建这个新的内部软件工具团队方面，我想先构建。”嗯，我们或许应该先替换我们自己的软件，因为我认为那会给每个人带来快乐，但然后，呃，我们可以谈其他事情。但你知道，我对这个团队有很多想法。呃，我只需要懂得如何与我合作的人，把这些想法变成人们真正喜欢使用的东西。所以，比如说，深入下去，然后，呃，创造的软件不是，你知道，整体中的一小块碎片，而是一个完整的整体。我想那会非常有意思。只是看看如果你以不是碎片化软件的方式开发出整个愿景，并且有软件能执行它，体验会是什么样。

<details>
<summary>Original English</summary>
So there's a certain level of responsibility that I don't care how you fix it, I need it to not break. So this is the level of responsibility where you can say: "Here is the mental component of all your material." "That's why I told Yazin that I wanted to build first in terms of building this new internal software tools team." Hmm, we should probably replace our own software first, because I think that's what will bring joy to everyone, but then, uh, we can talk about other things. But you know, I have a lot of ideas for the team. Uh, I just need people who know how to, uh, work with me to turn these ideas into things that people actually enjoy using. So, for example, to go deep and then, uh, create software that's not, you know, a small part of a whole fragment, but a whole whole. I think that would be so interesting. Just seeing what the experience would look like if you developed the whole vision in a way that wasn't, you know, fragmented software that could execute it.
</details>

### 结果与颁奖
好，你们期待已久的时刻，结果来了。五个程序通过了我们的标准，达到我们真正会采用，或认真考虑购买的程度。三位入围者再加另外两个。还有另外一个……”有 12 个项目，即使我们不使用整个应用，也很可能会借鉴它们的想法。显然，它们全都是开源的，所以祝贺他们。

<details>
<summary>Original English</summary>
Okay, the moment you've been waiting for, the results. Five programs passed our bar for something we would actually adopt, adopt, or seriously consider purchasing. And three finalists plus two more. There was another one…” 12 projects whose ideas we would probably steal even if we didn’t use the entire app. Obviously, they're all open source, so congratulations to them.
</details>

好，我们宣布第二名，奖金 1,000 美元，来自 Track Stage 的 Marco Kremer。我们发现它拥有业内最干净的体验，带有精致的拖放式日程界面，以及文档非常完善的仓库。如果你想学习如何管理一队智能体，请读一读这个，也看看 Marco 的主要作品 Cortex，它算是 ChatGPT 知识库的一种克隆。

<details>
<summary>Original English</summary>
Okay, we're announcing the second runner-up with a prize of $1,000, Marco Kremer from Track Stage. We found it to have the cleanest experience in the industry, with a sophisticated drag-and-drop scheduling interface and a very well-documented repository. If you want to learn how to manage a fleet of agents, read this and also check out Marco's main work, Cortex, which is a sort of clone of ChatGPT's knowledge base.
</details>

一等奖得主，我们授予 5,000 美元，是来自 Konferencer 的 Yazin。他的 click-to-go 体验是迄今最好的，让你在整个应用中直观导航，每个结果都显示在单个页面上，正如你们听到的，这让 Kelsey 很兴奋。而且在演讲者生命周期的每个阶段都有真实的电子邮件。它让事务性邮件变得令人愉快，这真的很难做到，我们对此有一些经验。嗯，我们很确定 Yazin 在设定这个水准。worries about everything。但总体而言，我们把 Kill My SaaS 获胜者的 10,000 美元奖金授予来自 Open Rostrum 的 Valentina de Matos。他构建了一个软件工厂，让工厂运转起来，并按日程发出了一些我们团队真正想用的门户，而且很可能会把它们发给你们所有人，用于 2027 年的 AI 工程大会。我的团队非常高兴。

<details>
<summary>Original English</summary>
The first prize winner, who we are awarding $5,000, is Yazin from Konferencer. By far the best click-to-go experience, allowing for intuitive navigation throughout the app, with every result displayed on a single page, which, as you can hear, was exciting for Kelsey. And also real emails at every stage of the speaker lifecycle. It made transactional email enjoyable, which is really hard to do, and we have some experience with that. Hmm, and we're pretty sure Yazin is setting this level. worries about everything. But overall, we award the winner of Kill My SaaS with a prize of $10,000 to Valentina de Matos from Open Rostrum. He built a software factory, got the factory up and running, sent out some portals on a schedule that our team actually wanted to use, and will probably send them to all of you guys for the 2027 AI engineering conferences. My team is very happy.
</details>

我们在 2027 年要做的，很可能是 Open Rostrum 与 Conferencer 的结合，再加上其他 12 个项目的想法。我的团队对此非常兴奋，因为现在我们知道 2026 年构建的活动软件可以是什么样子，而不是 2006 年构建的软件，而且我们可以拥有这个软件，并根据真实的用户反馈改进它。我团队里写代码最多的人不是工程师，而是设计师、领域专家、运营专员，也就是真正做事的人，他们汇报一切，并能对自己的 bug 报告和功能请求得到即时响应。

<details>
<summary>Original English</summary>
What we will be doing in 2027 will likely be a combination of Open Rostrum and Conferencer plus ideas from the other 12. My team is really excited about this because now we know what event software built in 2026 could look like, instead of software built in 2006, and the fact that we can own that software and improve it based on real user feedback. My people who code the most on the team are not engineers, they are designers, they are subject matter experts, they are operations specialists, the people who actually do the work, report everything, and get instant responses to their bug reports and feature requests.
</details>

### 总结与取舍
所以，总结一下，这就是我们如何摧毁自己原本打算购买的那款 43,000 美元 SaaS 的大致故事。如果你在租用一款你不喜欢、也永远不会拥有的软件，现在这其实是个明智之举，而且我们已经发布了这样做的路线图。克隆这种中型软件，大概花 1,000 美元的 token，比如说在订阅上，也许再加 10,000 美元的 AI 专业能力，所有这些报名的人里，你大概可以雇到其中一些。但取舍是，从那时起你就拥有它，这也意味着你要负责维护它。这不是一笔微不足道的交易，但严格来说也不是负面，因为智能体使得为你的团队支持和定制自己的软件，比整整 12 个月前可行得多。

<details>
<summary>Original English</summary>
So, just to summarize, that's the general story. about how we destroyed our own $43,000 SaaS that we were going to buy. If you're renting software that you don't like and will never own, it's actually a smart move now, and we've published a roadmap for doing so. Cloning this mid-level software probably costs $1,000 in tokens, let's say, in subscriptions, and maybe another $10,000 in AI expertise, which all these people who applied for could probably hire some of them for. But then the trade-off is that from then on you own it, which also means you are responsible for maintaining it. This is not a trivial deal, but it is not a negative in the strict sense either, because agents make supporting and customizing your own software for your team much more feasible than it was literally 12 months ago.
</details>

### 后记
好，所有参加 Kill My SaaS 的人，……好，所有参加 Kill My SaaS 的人，抱歉这么久没回来。事实证明你们很复杂。我们同时举办了两场会议。我是在 AI Engineering New York 写下这些的，下个月我们将举办 AI Engineering Code，而且我们是在常规工作之外做这些。所以，第一次是个非常混乱的过程，但我想我们学到了很多教训，下次我肯定会计划得好得多，不再自己一个人做，这样我们可以回到大家身边，更有条理。嗯，我们的团队已经从对 five-code AI 应用持怀疑态度，变成现在要求使用，并且乐意不惜花费。我的意思是，省钱是一部分，并且用省下的钱去资助我们永远付不起的真正的软件改进。我们喜欢这样，就像我们真的在付钱，我宁愿为 token 付费，把我的时间用来构建我所有参与者、赞助商、演讲者真正喜欢使用并且值得拥有的软件。所以如果你想赞助下一届 Kill My SaaS，可以联系我。嗯，如果你想参加，我会非常感激。嗯，所有仓库我们都会链接在这篇帖子对应的帖子里，祝贺获奖者。下次见。

<details>
<summary>Original English</summary>
Okay, everyone who ...Okay, everyone who participated in Kill My SaaS, sorry for not being back for so long. It turns out you guys are complicated. We held two simultaneous conferences. I'm writing this down at AI Engineering New York, and next month we'll have AI Engineering Code, and we've been doing this in addition to our regular work. So, the first time it was a very chaotic process, but I think we learned a lot of lessons next time, and next time I'll definitely plan it out a lot better and not do it on my own so we can go back to people and be more structured. Hmm, our team has gone from being skeptical of five-code AI applications to now demanding it and happy to spare no expense. I mean, saving money is part of it, and using the savings to fund actual software improvements that we could never pay for. We like it like we're literally paying, I'd much rather pay for tokens and use my time to build software that, um, all my participants, my sponsors, my speakers really enjoy using and deserve. So if you want to sponsor the next Kill My SaaS, you can contact me. Hmm, if you want to participate, I would really appreciate it. Hmm, all the repositories we will link to in the corresponding post to this post, and Congratulations to the winners. See you next time.
</details>