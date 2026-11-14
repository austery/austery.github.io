---
author: AI Engineer
date: '2026-11-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EaOit1mmR9g
speaker: AI Engineer
tags:
  - ai-agent
  - workflow-automation
  - wealth-management
  - financial-planning
  - no-code
title: 零代码基础的财务规划师如何构建自己的 AI Agent 与 Skill
summary: Range 的财务规划师 Matt Ragone 分享了无编程背景的规划团队如何落地 AI Agent 与 Skill。团队通过跨部门的 AI 委员会协同，建立标准化交付文档并结合内部真实客户数据，总结出挑选、示范、封装、测试与发布的五步构建法。在严格遵守 RIA 与 CFP 合规审查的前提下，将规划师日常产能从每天服务三至四人提升至目标百人，推动财务规划师向 Agent 管理者转型。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Matt Ragone
  - David Kusaydis
companies_orgs:
  - Range
products_models:
  - Claude
  - Claude Code
  - Claude Cowork
  - Slack
media_books: []
status: evergreen
---
### 零代码团队的 Agent 与 Skill 构建指南

我真正想聚焦分享的，是我们的财务规划团队最终是如何编写出我们日常使用的这些 Agent 和 Skill，从而让我们的团队变得尽可能高效且富有成效的。而且我们当中没有任何一个人具备工程或代码背景。我的意思是，在这个领域里，我们完全可以说是你能见到的最新手的人了。但这是一份构建指南，展示了我们一步步做到的过程，以便你能把这些经验带回自己的团队，或许还可以向你所在公司的非技术人员进行展示。

<details>
<summary>Original English</summary>
[music]

>> What I really wanted to focus on was how our financial planning team ended up writing the agents and skills that we use on a daily basis to make our team as efficient and effective as possible. And none of us have any engineering coding background. I mean, we are as fresh in this pool as as you'll quite get. But this is the build guide, how we did it step by step so you can take it back to your own teams and maybe present it to the non-technical folks at your

>> [clears throat]

>> companies.
</details>

正如我提到的，先简单介绍一下我自己，我是一名财务规划师，对吧？我并不是工程师。我在财富管理行业工作了大约 7 年。在疫情期间，我确实在媒体行业待过 2 年，但随后我又回到了财务规划领域。我大部分时间都在与客户讨论现金流、税务、投资、保险，说实话就是你能想象到的最引人入胜的话题。

<details>
<summary>Original English</summary>
So, as I mentioned, a little bit about me, um I'm a financial planner, right? I'm not an engineer. Um I've been in the wealth management industry for about 7 years now. I did have a 2-year stint in media during COVID, but then I found my way back uh into uh the financial planning realm. Um I spend most of my days talking with clients about cash flow, taxes, investment, insurance, really just like the most riveting topics you can imagine.
</details>

### AI 委员会：跨职能协同与合规约束

但特别的是，我在 Range 领导规划团队的 AI 应用落地，Range 是一家一站式财富管理公司。这个 AI 落地团队，我们称之为“AI 委员会”（AI Council），它是由我们的联合创始人 David Kusaydis 构想出来的，他希望公司的各个部门在这个委员会中都能有代表，对吧？所以，你可以把 AI 委员会看作是公司里最前沿的 AI 使用者的圆桌会议。我们在其中分享最佳实践，因为如果会员成功团队创建了一个营销人员也能使用的 Skill，我们可不想去重复造轮子，对吧？我们希望确保我们的运作尽可能高效。因此，值得庆幸的是，规划团队把针对规划师群体的这一职责托付给了我。而且我也很喜欢它被称为 AI 委员会这一点。你知道，每次我说出这个词时，我都感觉自己置身于《权力的游戏》中，对吧？我感觉自己要么是在临冬城，要么就是在红堡，扮演着财务规划师守护者的角色。

<details>
<summary>Original English</summary>
Uh but uniquely, I lead the AI adoption for the planning team at Range, which is an all-in-one wealth management firm. And this AI adoption team, which we call the AI Council, um it was an idea created from our co-founder David Kusaydis, uh who wanted to have every part of the company represented um in this council, right? So, think of the AI Council like a round table for the most forward AI users at the company. And we share best practices because if a member success team creates a skill that the marketers can use, we don't want to reinvent the wheel, right? We want to make sure we are operating as effectively as possible. So, thankfully, the planning team trusted me with that responsibility for the planners. Um and I also love that it's called the AI Council. Um you know, I feel like I'm in Game of Thrones when I say that, right? So, I'm either in Winterfell or I'm at like the Red Keep uh kind of just being like the warden of the financial planners, if you will.
</details>

在这里我要提到的最后一件事是，由于我们是一家注册投资顾问公司（RIA），我们在一个受监管的行业中开展业务。因此，我们交付的产出物是给真实客户的财务建议，而审核流程绝不是可有可无的，对吧？这会切实影响到真实人们的生活。所以，这并不是什么供应商推销，这纯粹是一套对我们而言最有效的实用方法。

<details>
<summary>Original English</summary>
So, and then the last thing I'll mention here is that, you know, we work in a regulated business as an RIA. So, the output that we're delivering is financial advice to real clients and the review process, it's not optional, right? This impacts real people's lives. Um so, this isn't like a vendor pitch. It's really a method of what worked best for us.
</details>

### 从聊天机器人到多任务并发

让我们把时间倒回到今年早些时候。我的意思是，我们踏入 AI 领域的时间基本上和大家去年差不多。我们最初只是把 AI 当作聊天机器人来用，对吧？那时候 Claude Code，或者说 Co-work，其实都还没真正推出。当时我们只是用它来重新起草邮件、在某些税法变动上帮我们核对事实，或者解析大型文档。在这些方面它确实帮我们节省了大量时间。但唯一的限制在于，我们仍然必须手动完成所有的工作。当然，随着对 AI 的采用，我们的速度加快了一点点，但真正的重大变革发生在稍晚一些的时候。

<details>
<summary>Original English</summary>
So, let's rewind back to earlier this year. I mean, we started pretty much in the AI realm as much as everyone did last year. We just use AI as a chatbot, right? Claude Code, uh Co-work for that matter, wasn't really out yet. But, we were just using it to redraft our emails, um fact-check us for certain tax code changes, uh or parse through like large documents. So, it saved us a lot of time in that regard. But, the one constraint was that we still had to manually do all the work. We got a little bit faster, of course, with the AI adoption, um but the big changes really happened a little bit later.
</details>

当时的情况大致是这样的：我能服务多少客户或会员的最大瓶颈，本质上取决于我打字能有多快，对吧？这始终会是一个非常糟糕的瓶颈，因为无论我是每分钟打 300 个词还是 200 个词，我仍然必须手动完成所有工作，对吧？随之而来的另一个问题是，假设我正在和一个客户通电话，聊了 30 分钟或 45 分钟，在此期间我就无法服务其他任何客户。从我们其余客户群体的角度来看，这在某种程度上就是被耽搁的时间。对吧？所以，我们意识到了这个瓶颈。

<details>
<summary>Original English</summary>
So, here's kind of what we knew, right? The biggest constraint to how much I'm able to work with a client or member, etc., uh it had to be how fast I could essentially type, right? And that's always going to be a really bad bottleneck cuz whether I type 300 words per minute, 200 words per minute, I still have to manually do all of the work, right? And another issue that arose was say I was on a call with a client 30 minutes, 45 minutes, I can't work with any other client during that time. It's essentially time wasted in a way from the rest of our client base. Okay? So, we recognized that bottle.
</details>

随后在 1 月底、2 月初，情况发生了改变，对吧？Claude Co-work 彻底改变了游戏规则，对吧？现在，我可以正和一个客户通电话，同时让我的 Claude Co-work Agent 完整起草一份现金流分析、一份保险分析、一份税务审查，而这一切都在我服务另一个客户或会员的过程中同步完成。这样一来，当通话结束时，我不再仅仅是处理了一个客户的工作，而是能够同时服务多位客户。

<details>
<summary>Original English</summary>
Then what changed is in late January, early February, right? Claude Co-work completely changed the game, right? Now, I could be on a call with one client and I can be having uh my Claude Co-work agent completely draft a cash flow analysis, an insurance analysis, a tax review, all while I am simply servicing another client, member, etc. So, now what happens is when the call ends, instead of me just working with one client, I'll be able to do multiple at once.
</details>

不过现在的最终环节是，我必须进行审核、调整，仔细查看我们 Agent 构建出的内容，以确保它在发出之前是无懈可击的。因此在这一点上，现在的规则已经发生了很大变化。那么，我们是如何在相对较短的时间内走到这一步的呢？这所需要的远不止一段好的提示词。有两个前提条件必须成立。

<details>
<summary>Original English</summary>
Um but the end product now is that I have to review, adjust, and really see what our agent built so that I can make sure it is bulletproof before it gets sent out. So now, right, the game has changed a lot in that respect. Um so how do we get here in a relatively short period of time? Um it took a lot more than just a good prompt. Two things had to be true.
</details>

### 落地的前提：数据接入与业务流程标准化

首先，Agent 必须知道工作数据存放在哪里，对吧？在我们的系统中，那是真实的客户数据，而不是放在我以前通过复制粘贴导入的独立聊天窗口里。通过我们的平台，个人用户——我们称他们为会员，这就是为什么你会一直听到我把客户、委托人和会员混着叫——会员会将他们所有的财务数据、账户等直接连接到我们的平台上。因此，从保险单据、投资、房产购置到抵押贷款，我们至少基本全面掌握了他们完全关联的财务全貌。所以 Agent 必须懂得如何正确拉取那份文件或正确提取那些数据，知道哪些是正确的数据该去拉取，哪些是错误的数据不该拉取等等。

<details>
<summary>Original English</summary>
First, the agent has to know where the work lives, right? In our systems, it's actual client data, not in a separate chat window that I'm copy and pasting it into anymore. And through our platform, individuals, we call them members, is why you'll keep hearing me interchange customers, clients, members. Members connect all of their financial data, accounts, etc. right onto our platform. So we at least pretty much know from insurance documents, investments, home, uh you know, real estate purchases, mortgages, we have their entire picture fully connected. So the agent has to know how to pull that document correctly or or that data correctly, know what's correct data to pull, incorrect data to pull, etc.
</details>

其次，它必须理解我们在 Range 是如何交付建议的，对吧？它不能只给出通用的建议，因为我们可能会比 Claude Co-work 或其他任何 Agent 倾向于给出的建议要更保守一些。幸运的是，我们实际上走在了这个趋势的前面。我们的团队大约有 20 名规划师。在 Claude Co-work 真正推出之前，我们就已经把所有的流程标准化了：我们如何给出保险建议、投资建议、退休建议。这样一来，无论我是来自大型财富管理机构的规划师，还是另一位来自小型 RIA 的规划师，大家都有一份参考文档，说明我们在全公司范围内是如何统一交付所有建议的，明白吗？

<details>
<summary>Original English</summary>
And then second, it has to understand how do we deliver advice at range, right? It can't just be delivering generic recommendations because we might be a little bit more conservative than what Claude CoWork or any sort of other agent would like to deliver. So we actually were ahead of this curve, luckily. Um you know, our team is about 20 planners. Before Claude CoWork really dropped, we standardized all of our processes. How we deliver insurance recommendations, investment recommendations, retirement recommendations, so that if I'm a planner coming from a large wealth management firm and another planner is coming from a small RIA, you have some sort of reference document on how we deliver all of our recommendations, kind of across the board, okay?
</details>

这在 Claude Co-work 面世时真正为我们节省了大量时间，因为我们不用去重新发明轮子，而是直接告诉它：“嘿，Claude，在你启动任何工作流之前，把这份文档作为你审核流程的一部分进行参考。”当时我们这些数据和标准化内容存放在 Notion 页面和 Google 文档中，但我们基本上也都把它浓缩归纳在里面了。正是这些工作，让我们在使用 Claude Co-work 时达到了非常理想的状态。

<details>
<summary>Original English</summary>
So that actually really saved us so much time when Claude CoWork came out because instead, again, instead of the wheel, it was "Hey Claude, just reference this document as part of your review process before you kick off any of your workflows." Now, we had this data living in in these standardizations living in Notion pages, Google Docs, but we really just had it all kind of condensed in there, too. So, that's what really it took for us to get to a really good place with Claude Co-work.
</details>

### 构建 Skill 的五个步骤

接着，我们总结出了构建 Skill 或 Agent 的五个步骤。我觉得这两者基本上是可以互换的。第一步是**挑选**（pick），第二步是**示教**（teach），然后是**封装**（pack）、**测试**（test）和**发布**（ship），明白吗？其中没有一步需要你写代码，完全零代码，而且每一步都要求对业务工作非常熟悉，对吧？这就是为什么真正在一线做这些工作的人，才应该是构建它们的人，我们在稍后的演示中也会谈到这一点。

<details>
<summary>Original English</summary>
And then, we kind of identified five steps to build the skill or agent. They're pretty much interchangeable I feel. So, one is pick, two teach, pack, test, and ship. Okay? None of them require you to write code, no code, and each one of them requires knowing the work really well, right? So, that's why the people doing should the work should be the ones building it, which we'll touch on a little bit later in the in the presentation.
</details>

**第一步：挑选一个你不断重复的工作流。** 我指的是每天或每周都在重复的工作。你的第一直觉往往会去挑那些最亮眼、最复杂的事情。根据我的经验，我告诉你，千万别那么做。选一个你认为耗费大量时间、但能非常非常简单地实现自动化的任务。而且这样做的一大好处在于，你能立即判断出产出物是好是坏，马上就能做出评估。如果是更复杂的任务，你迭代优化 Skill 或 Agent 所花的时间就会长得多。对我们来说，那就是现金流分析、保险审查，以及我所说的基本上任何需要大量手动操作的建议制定工作。

<details>
<summary>Original English</summary>
So, step one, pick a workflow you repeat constantly. Okay? I'm talking daily, weekly. Your first instinct is going to be to pick like the flashiest thing, the most complex thing. I'm telling you from experience, do not do that. Okay? Pick what you think takes a lot of time, but can be automated very very simply. Okay? And and the great part about that as well is you will immediately know if the output is good, if it's bad, you'll have that judgment right away. If it's more complex, it's going to take you a little bit longer to really reiterate with the skill or with the agent. So, for us, that was cash flow analysis, insurance reviews, and it was pretty much any recommendations I said that took a lot of manual work to do. Okay?
</details>

**第二步：给它展示一个真实案例。** 放到现在的话，我可能会给它展示两、三、四、五个真实案例。也就是最终成品到底长什么样，对吧？我之前提到的标准化文档只是说明了我们如何开展工作。随后，我会把一些真实案例添加到 Claude Skill 的参考部分中，比如遇到极端边缘情况的现金流分析，或者我不得不纠正 Agent 工作的案例。这样它就能再次进行参考，下次运行该 Skill 或执行工作流时，它就会显得更加高效，并且对那些边缘情况的理解也会好上许多。

<details>
<summary>Original English</summary>
Step two, I say show it one real case. I would end up now probably doing it two, three, four, five real cases. Like, what does the final product look like, right? So, our standardization documents that I referenced, it just tells us how we do the work. Then, I will add to the referenced part of the Claude skill, what do you real cases look like of a cash flow analysis where it's an edge case, right? Or where I had to correct the agent's work. So that he can reference that again, so the next time it runs the skill or does the workflow, it looks much more uh efficient and understands some of those edge cases cases a little bit better. Okay?
</details>

而且在构建 Skill 的过程中，我会向它口述解释我为什么要执行某些操作。可以理解为你在前期多花一点功夫，是为了在后续节省大量时间。举个例子，如果我正在为现金流分析或保险分析上传一份工资单，我会让 Skill 明白我们为什么要这么做：“嘿，在这份工资单里，看一下他们是否被扣除了 3 美元的团体定期寿险费用。”如果你只是上传工资单，你应该尽可能给 Agent 一点指引。你不需要搞得太夸张，但这种额外的口述解释同样为我们在后续节省了大量的时间。

<details>
<summary>Original English</summary>
And as I'm building the skill, um if you will, I am narrating to it why I'm doing certain things. So think like you're going to take a little bit more work up front to save you so much time down the road. For example, if I'm uploading a pay stub for a cash flow analysis or an insurance analysis, I'm letting the skill know why we're doing that. Hey, in the pay stub, look if they have, you know, $3 deducted for groove group term insurance, right? Group life insurance for example. If I'm just uploading the pay stub, you know, you want to give the agent a little bit of direction if you can. You don't have to go crazy with it, but that additional narration has saved us so much time down the road as well. Okay?
</details>

**第三步：一旦你觉得它表现不错，就把它封装成一个 Skill。** 然后我们发现了接下来最好的两个步骤。我不知道这是否已经被普遍采用，但我们在这方面取得了很大的成功。

在对某些 Skill 或 Agent 进行提示词设计时，**我会让它向我提问。**“这项税务审查是 2025 年的还是 2026 年的？对于现金流分析，我们参考的是哪套税法？他们住在哪个州？”显然，其中一些数据它可以直接从 Range 的个人档案中提取，但还有其他方面，比如这位会员是更关注房屋所有人保险，还是我们重点看的是伤残保险？他们是否有终身寿险保单需要我们审查？所以当我们在编写提示词时，会让它提出几个问题，以便它能真正以最高效的方式开展工作。

<details>
<summary>Original English</summary>
Then three, right? Once you feel like it does a good job, pack it into a skill. And then we found two all the two best next steps to do as well. And I don't know if this is fully adopted across the board, but we've had a lot of success with it.

When I'm prompting certain skills or agents, I have it ask me questions. Is this tax review a 2025 tax review? Is it a 26 review? For the cash flow, you know, what tax code are we looking? What state do they live in? Now obviously some of this data they can pull right from um the profile on on Range, but there's some other things whereas is this member more focused on their homeowner's insurance or is it a disability focus that we're looking at? Do they have a whole life policy we want to review? So when we prompt it, we have it ask a couple questions so that it can really do work in the most effective manner.
</details>

**其次，明确它必须遵守的界限是什么，对吧？** 再次强调，我们是受监管的。我们的建议具有现实影响。因此，任何一个 Skill 都绝不允许直接向会员发送任何内容，明白吗？目前阶段，它必须经过 CFP（持证财务规划师）的审查。坦白讲，往后看，我认为情况也依然会是这样。现在，我们确实内置了一个非常酷的 AI 功能叫做 Ry，它符合 CFP 和 RIA 的合规要求，这非常棒。这是内置在其中的。但现阶段，当会员要求真人交互时，我们必须确保它经过我们的验证。所以，我认为在封装 Skill 时，这两点也许是人们不会想到、但却极大地帮助了我们的地方。

<details>
<summary>Original English</summary>
And then second, what are the limits it has to respect, right? Again, we're regulated. Our recommendations have real-life impacts. So, every single skill is not allowed to send anything to a member, okay? It has to be reviewed by a CFP at this time. And honestly, just moving forward, I feel like that's just going to be the case. Now, we do have a really cool built-in AI feature called Ry, which is CFP compliant and RIA compliant, which is very cool. That's built into it. But at this time, you know, when a member is asking for human interactions, we have to make sure that it is validated by us as well. So, those are the two, I would say, things maybe people don't think about when packaging a skill that have really helped us out tremendously.
</details>

**第四步：在将它发布给团队其他成员之前，在 5 到 10 个真实案例上进行运行。** 其中一些应该是常规的标准案例，但你确实也需要测试几个边缘案例。这样当未来出现这些情况时，Skill 或 Agent 就能真正识别出来，并知道如何处理该特定问题。此外我们的做法是，你可能会找一两个同事跟你一起对这个 Skill 进行压力测试。每次运行完之后，我都会告诉它：“把你学到的东西重新打包到 Skill 中。不断迭代你的 Skill，让它变得更好。”然后在我彻底发布它之前，你会问 Claude、Skill 或 Agent 最后一个问题：“你怎样才能让自己变得更好？具体会怎么做？”再次更新该 Skill，不断将其打包完善。

<details>
<summary>Original English</summary>
And then step four, and this is this is again, this is before you're shipping it out to the rest of your team. I would run it on five to 10 real cases. Some should be like your standard cases, but you really want to test a few edge cases as well, so that when those cases arise in the future, the skill, agent, etc. can really pick it up and know how to work with that specific issue. Now, what we do as well is you might have one or two other individuals kind of working with you to kind of stress test this skill as well. And then every time after I run it, I say, "Take what you learned, repackage that into a skill. Keep iterating on your skill. Keep making it better." And then before I I fully ship it, you ask Claude or the skill, the agent, one final question is, "How could you make yourself better? What would you specifically do?" Again, update the skill, keep packaging it out.
</details>

**第五步：一旦你觉得它已经足够稳定可用，就到了发布的时候了。** 然而，工作到这里并没有结束。我希望事情能那么简单，但税法在变，整个行业在发生很大变化。你需要发布它，而且**它必须指定负责人（owner）和审核人（reviewer）**，对吧？当团队规模很小时，可能同一个人兼任这两项职责。但随着团队扩张，我们团队现在有大约 20 名规划师，并且还在增长。如果我作为负责人发布了它，我可能会让我的同事 Joe 作为审核人来把关，因为在保险领域他可能具备更出色的专业技能。

<details>
<summary>Original English</summary>
And then once you feel like it's strong enough to go, um it's time to ship it. Now, that's not where the work ends. I wish it was that easy. I wish. But, tax code's changing, a lot is changing in the industry in general, but you need to ship it and it needs to have an owner and a reviewer, right? When you're a small company, it's probably going to be the same person doing both of those things, but as we're We're our team, we have about 20 planners now in the team and growing. Um you know, if I ship it as the owner, I might have my colleague Joe review it as the reviewer because he might have a little bit better subject matter expertise in insurance, for example.

>> [snorts]
</details>

### 现状、分工与规划师的角色转变

那么，我们现在进展如何呢？这项实验大约进行了 6 个月，如果算上的话大概是 6 到 8 个月，全公司已经拥有了大约 24 个 Skill，其中仅财务规划领域就有 17 个。真正令人兴奋的是，全公司各个部门能够相互借鉴构建。大家可能会以为我们构建的很多 Skill 和 Agent 是工程师在主导推进，但工程师非常擅长他们自己的工作，是在自己的领域里去理解它。而我们作为规划师、营销人员、团队成功与会员成功团队，能够互相配合借力，创造出更多的 Skill 来让我们的工作尽可能高效。顺便提一下我们的下一步演进，我们创建了一个名为 Ranger 的 Agent。因为我们叫 Range，所以它叫 Ranger，它目前在协助公司里的每一个人处理任务。它常驻在 Slack 中，能够进入我们的管理后台协助处理其他会员任务，我们目前正在积极地构建它，这非常让人兴奋。

<details>
<summary>Original English</summary>
>> So, where are we now? You know, we're about 6 months into this uh experiment, if you will, 6 to 8 months in, and we have about 24 skills across the company, 17 just in financial planning. And the really exciting thing was we have been able to build off each other across the firm, right? A lot of the skills agents were building, um you would think it's really the engineers running with it, but they're they're so good at what they do, they understand it in their realm. We have been able as planners, marketers, team success, uh member success team, right? We have been able to work off each other and create even more skills to make our work as effective uh as possible. And our next evolution, by the way, we have a uh we created an agent named Ranger, right? We're Ranger, so this is Ranger, um that assists everyone at the company with tasks right now. It lives in Slack. Uh it can go on to our our our dashboard to assist with um kind of other member task, but we're building that out actively, which is very, very exciting.

>> [snorts]
</details>

而且我们真正发现的一点——我也在谈到负责人和审核人时略有提及——是你一定要让该领域的专家来构建对应的 Skill，对吧？如果某人是保险专家，他就应该是那个对保险 Skill 进行迭代的人，因为他们会注意到我作为通才规划师可能无法立刻发现的细节。我的理解方式是，持证财务规划师有点像四分卫。有时候你必须完成一次 50 码的长传达阵；而其他时候，你得稳扎稳打推进、消耗比赛时间。在这种情况下，有时你必须把球交接给注册会计师（CPA）或投资团队，他们可以提供更深入的协助。所以，我们的注册会计师团队和税务团队会在我们构建的 Agent 和税务 Skill 上提供很大的帮助，而我则可以作为纯粹构建 Skill 本身的领域专家介入。他们负责 Skill 需要掌握的实际业务内容，担任内容层面的领域专家。

<details>
<summary>Original English</summary>
>> And what we've really found as well, and I kind of touched on this a little bit with having an owner and a reviewer, you really want to have the experts in that area build out that skill, right? If someone is an insurance specialist, they should be the one iterating on the insurance skill because they will pick up on stuff that myself as kind of a general practitioner might not uh might not know right off the bat, right? Um the way I think about it, certified financial planners, we can kind of be like a quarterback. Sometimes you got to air it out 50 yards. Other times, you know, you got to ground and pound, chew the clock out. And that's where sometimes you got to hand the ball off to the CPA, to the investment team, and then they can assist even further, right? So, again, we have our CPA team, our tax team really help with the tax skills that we've built in the agents, um but then I can kind of come in as just the subject matter expert with really how to build the actual skill. They'll be the subject matter expert on the actual content the skill needs to know in that matter. Okay?
</details>

现在瓶颈已经彻底转移了，对吧？过去瓶颈在于：我打字有多快？AI 到底能帮我起草多少内容、改写多少措辞、帮我核对多少事实？现在我们开始问的问题是：当所有东西都发布之后，由谁来确保所有这些都经过测试与更新？我们如何确信每个 Skill 都是保持最新状态的？我设想未来我们甚至会让规划师转型为类似于“AI Agent 管理者”的角色，对吧？这就是我所看到的这个行业的未来发展方向。当然，你依然可以在电话沟通中找到具体的规划师，因为人与人之间的温情连接仍然存在，而且会长久存在。但我们如何确保每位规划师不再是每天只能为三到四个人提供建议，而是每天能够为 100 个人提供建议？这才是真正的目标。

<details>
<summary>Original English</summary>
And now the bottleneck has completely moved, right? The bottleneck used to be, how fast can I type? How much can AI really draft for me, rewrite my words, you know, fact check me as well? Um Now we're starting to ask the question is, you know, when everything gets shipped, uh you know, who is making sure all these get tested, updated? How do we know that every skill is fully up to date? We're almost going to start having planners, I would imagine, almost be AI agent managers, right? That's how I see the future of this industry going. Of course, you'll still be able to access certain planners on calls because the human's touch is still there. It's going to be there for a long time, but how can we make sure instead of providing advice for three to four people a day, right? We're providing advice to 100 people a day per planner. That's really the goal.
</details>

非常令人振奋的是，这一切都在飞速发展。你要么参与其中，要么就会落后——我们现在确实看到采用 AI 和未采用 AI 的机构之间正在出现巨大的分化。不过，这就是我们的落地规范，或者说是我们在 AI 应用落地上的成功指南。因此，我希望大家能把这些经验带回你们的公司。再次说明，这来自于一个完全没有工程背景、没有写代码背景的人。如果我们在全公司推行 AI 落地的成效能够像你们在自己公司所能做到的一样强，那么我认为任何人也都可以落地这套方法。非常感谢大家。我是来自 Range 的 Matt。如果你想加入一个优秀的团队，我们目前也正在招聘。再次感谢各位的参与，非常感激大家。

<details>
<summary>Original English</summary>
And what's super exciting is all this stuff is moving fast, and you know, you're either a part of it or, you know, we're seeing a big divergence right now in firms who are adopting it and who aren't. But you know, this has kind of been our adoption uh policies, if you will, or our success guide with AI adoption. So, I hope you guys can take this across your firms and and again, you know, this is coming from someone with no engineering background, no coding background. If we can get AI adoption as strongly across our company as you all can at yours, um I think anyone can can kind of implement this as well. Well, so thank you so much. My name is Matt from Range. If you want to join an awesome team, we are hiring as well. But thank you all for joining. Uh I really appreciate it.
</details>