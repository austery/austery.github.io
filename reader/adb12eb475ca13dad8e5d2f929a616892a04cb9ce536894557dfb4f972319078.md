---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MQiojLnK-E0
speaker: AI Engineer
tags:
  - code-review
  - data-pipeline
  - automation
  - ai-agent
title: Robinhood 数据管道的混合 PR 审查实践：脚本验证事实，AI 负责判断
summary: Robinhood 工程师 Jas 介绍了应对机器生成 PR 激增的混合审查系统：确定性脚本验证注册事实，AI Agent 推理代码上下文与风险，人类保留敏感权限与低置信度决策，实现 60% 数据 PR 无人审查合并并减少 75% 人工审查工作量。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people: []
companies_orgs:
  - Robinhood
products_models: []
media_books: []
status: evergreen
---
### 机器速度下的 PR 与人类审查瓶颈

设想一个拉取请求（PR）。它修改了我们某个数据管道中的一个模式（schema）。它在持续集成（CI）中显示为绿色。测试通过了。代码检查工具（linter）没有报错。关于它的一切看起来都很干净。那么，合并它安全吗？

因为像这样的变更仍然可能破坏下游的某些东西。也许它会打破数据新鲜度的 SLA。或者它可能会破坏三个团队之外某个完全没预料到这一变更的消费者。又或者它暴露了本不该被访问的数据。CI 通过与这个变更实际安全之间的差距，就是我的团队每天必须弥合的差距。大家好，我是 Jas。我是 Robinhood 数据平台团队的一名工程师。我负责设计和构建我们数据湖背后的分布式数据摄取和处理框架，全公司各团队都依赖这些框架利用数据做出决策。

请注意本次演讲的标题。其中的“Bots”既是发起拉取请求的一方，而且如你所见，也是审查它们的一方。

今天我想向大家展示，当 PR 的涌入速度超过我们任何人阅读的速度时，我们是如何回答那个问题的。

一句话概括这里的问题：对我们生产数据管道的拉取请求现在正以机器的速度到来，但安全地审查它们仍然以人类的速度运行。

<details>
<summary>Original English</summary>
Picture a pull request. It changes a schema in one of our data pipelines. It goes green in CI. The tests pass. The linder is happy. And everything about it looks clean. So, is it safe to merge?

Because a change like this can still break something downstream. Maybe it blows a freshness SLA. Or maybe it breaks a consumer three teams away who never saw it coming. Or maybe it exposes data that never supposed to be reachable. That gap between CI past and this change was actually safe is the gap my team has to close every day. Hello everyone, I'm Jas. I'm an engineer on the data platform team at Robin Hood. I design and build the distributed data injection and processing frameworks behind our data lake. The ones teams across the company rely on to make decisions with data.

Notice the title of this talk. The bots in it are the ones opening the pull requests and as you will see the ones reviewing them as well.

Today I want to show you how we answer that question when the PRs are coming in faster than any of us can read them.

So here's the problem in one sentence. Pull requests to our production data pipelines now arrive at machine speed. But reviewing them safely still runs at human speed.
</details>

首先，简要说明一下本次演讲的范围，因为它决定了本次演讲中其他所有内容。

AI 编程助手使得创建 PR 的成本变得非常低。一个新的查询、一次模式变更或一次访问权限授予，现在只需要几分钟。而且助手创建拉取请求的速度，远快于任何人类团队以往所能达到的速度。

我今天谈论的 PR，是指针对我们数据管道的 PR，例如模式变更、管道代码、配置变更，以及向某人授予数据访问权限的授权。

数据平台是负责审查这类 PR 的团队。因此，当这些 PR 堆积起来时，它们就堆积在我们身上。而我即将描述的审查系统，就是我们为了处理它们而构建的。

因此，感受到这一压力的人只是一个小群体：即掌握上下文、能够判断合入生产环境是否安全的工程师，以及所有等待他们的人。

那么为什么这是个问题呢？AI 创建的 PR 不断涌入。

平心而论，我们已有的安全网是有效的。CI 检查与人工审查相结合，一直以来都能发现许多真正的缺陷，例如损坏的代码、低效的查询，以及下游损坏或敏感数据泄露等风险。但人工这一半只能以人类的速度运作，并且仅依赖于一个人脑海中碰巧掌握的上下文。谁在读取这张表？它有多大？其中的数据有多敏感？PR 正以机器的速度进入，但懂得什么内容可以安全合入生产数据管道的人数却完全没有增加。这就是失配所在。队列在少数拥有上下文的人面前积压，事情也正是从这里开始出现疏漏。

<details>
<summary>Original English</summary>
First, a quick word on the scope of this talk because it shapes everything else in this talk.

AI coding assistants have made pull requests cheap to open. A new query, a schema change, or an access grant now takes just a few minutes. And an assistant can open pull requests far faster than any team of humans ever could.

The PRs I'm talking about today are the PRs to our data pipelines like schema changes, pipeline code, configuration changes, and grants that give someone access to data.

Data platform is the team that owns reviewing that kind of PR. So when those PRs pile up, they pile up on us. And the reviewer I'm about to describe is the system we built to handle them.

So the people who feel this are a small group. The engineers who carry the context to say what is safe to merge into production and everyone who is waiting on them.

So why is this a problem? AI open PRs just keep arriving.

And to be fair, the safety net we already had works. CI checks together with a human review have always caught a lot of real bugs like broken code, inefficient queries and risks like downstream breakage or sensitive data leaks. But the human half only works at the human speed and only with the context a person happens to carry in their head. Who reads this table? How big is it? And how sensitive is the data in it? The PRs are coming in at the machine speed, but the number of people who understand what is safe to merge into a production data pipeline did not grow at all. That's the mismatch. The queue builds up in front of the few people with the context and that's where things start to slip.
</details>

### 三层混合审查架构

因此，我们着手解决的问题是：使用 AI 构建一个 PR 审查器，使其能够跟上创建 PR 的速度。

在深入细节之前，先给出完整的答案。三项职责，三个责任方：

脚本证明可以被证明的事实。Agent 判断需要上下文的内容。而人类则执掌只有他们才该做出的裁决。我们采用了混合方法：用脚本处理事实，用 AI 处理判断。当某些问题已经拥有权威答案时，我们不希望让 AI 去审查每一处变更。

这就是第一层。确定性脚本会检查真相来源（source of truth），比如模式注册表（schema registry）或元数据目录（catalog）。未通过的检查会使 CI 变红并阻断该 PR，直到它被修复。

第二层是 Agent。Agent 的规则会告诉它第一层已经检查了什么，因此它专注于这些检查无法捕获的风险。它审查 PR，评估风险评分，并决定批准还是升级给人类。这两层都会审查同一个 PR。合并既需要通过各项检查，也需要获得批准审查。

这同时也控制了 AI 的成本。我们将 AI 用于判断，而不是让它重新去发现脚本就能查到的事实。

<details>
<summary>Original English</summary>
So the problem we set out to solve was this. Build a PR reviewer using AI that can keep up with the speed at which PRs are being opened.

So here's the whole answer before we get into the details. Three duties, three owners.

Scripts prove what can be proven. An agent judges what needs context and people own the calls only they should make. We took a hybrid approach. Scripts for the facts and AI for judgment. We did not want AI reviewing every change when some questions already have an authoritative answer.

And that's layer one. Deterministic scripts check a source of truth like the schema registry or a catalog. A failed check turns CI red and blocks the PR until it is fixed.

Layer two is the agent. The agents rules tell it what layer 1 already checks. So it focuses on the risks those checks cannot catch. It reviews the PR, scores the risk and approves or escalates to a person. Both these layers review the same PR. Merge requires passing checks and an approving review.

And this also keeps AI costs down. We use AI for judgment, not to rediscover facts a script can look up.
</details>

这就是我们今天的演讲路线。我们已经介绍了问题和方法。接下来我将带大家了解我们构建的混合审查器，以及我们特意保留由人类做出的决定。之后介绍该审查器如何从人类反馈中学习，以及我们目前看到的成效。最后，我们将以想分享给大家的经验教训来结束。

随着我们的推进，请留意这三点：**用于事实的脚本**、**用于判断的 Agent**，以及**用于受保护裁决的人类**。我会在最后回到这三点。

为了让这一点具体化，让我向你们展示一个贯穿本次演讲剩余部分的 PR。

这个 PR 对我们数据湖中的一张表做了两处修改。它添加了一个新列，并将一个现有列从整数（integer）扩大为大整数（big integer）。这是我们经常见到的那种 PR。左边是一个上游源表。我们的摄取管道从中读取数据并写入数据湖中的一张表——姑且称之为我们的表。

第一处变更：源表增加了一个新列，这个 PR 使摄取管道将该新列引入到我们湖中的表里。

第二处变更是针对表中已有的一个列，它的类型从 integer 扩大为 big integer，以便能够容纳更大的数值。单看这一点，听起来完全无害。扩大类型差不多是你所能做的最安全的模式变更了，对吧？

然而，每当一个列发生变化时，真正的问题在于：下游谁在读取它？其中一些读取者已在我们血缘工具（lineage tool）中登记，所以我们知道它们的存在。

但请在脑海深处保留第二个问题：**那些就是全部的读取者吗？**

请记住这张图。每次 PR 在审查器中向前推进时，我们都会回到这张完全相同的图。

<details>
<summary>Original English</summary>
So here is where we are going today. We have covered the problem and the approach. Now I'll walk you through the hybrid reviewer we built and the decisions we deliberately keep with the people. After that how the reviewer learns from the human feedback and what results we have seen so far. And we'll finish with the lessons we would pass on to you.

Three things to listen for as we go. Scripts for facts and agent for the judgment and people for the protected calls. I'll come back to all three at the end.

So to make this concrete, let me show you the one PR will follow through the rest of this talk.

This PR makes two changes to a table in our data lake. It adds a new column and widens an existing column from integer to big integer. It's the kind of PR we see all the time. On the left is an upstream source table. Our injection pipeline reads from it and writes into a table in the data lake. call it our table.

The first change, the source has gained a new column and this PR makes injection bring that new column into our lake table.

The second change is to a column of a table already has its type gets widened from integer to big integer so it can hold bigger values on its own. That sounds completely harmless. Widening a type is about the safest schema change you can make, right?

Well, whenever a column changes, the real question is who reads it downstream? Some of those readers are registered in our lineage tool. So, we know about them.

But keep a second question in the back of your mind. Are those all of them?

Hold on to this picture. We will come back to this exact diagram each time the PR moves forward through the reviewer.
</details>

### 第一层：确定性脚本的检查与局限

那么让我们从第一层开始。第一层是脚本，它们的全部职责就是在运行系统中检查事实，那些仅凭代码本身无法告诉你的事情。

以下是其中的两项检查，以及它们对我们正在处理的 PR 给出的结论。

第一项是数据契约（data contracts）。当 PR 更改模式时，脚本会将模式和键与真相来源——模式注册表进行比较。对于我们的 PR 而言，问题很简单：那个新列是否确实像注册表中登记的那样存在于上游？它确实存在。所以该项检查通过。

第二项是必需标签（required tags）。每张表都需要有一个负责人（owner），任何个人身份信息（PII）都必须在元数据目录中打上标签。脚本直接检查元数据目录：我们的表有 owner 吗？有。它的 PII 打上标签了吗？打了。再次通过。

如果这两项中有任何一项失败，没有任何争论的余地，也不涉及任何模型。CI 会像处理其他任何失败检查一样变红，PR 将被阻断直到修复。

契约和标签是第一层检查中的两项。接下来是考量下游影响和性能的两项。

这是第一层的另外两项检查。它们超越表本身，关注下游会发生什么，以及作业是否仍能按时运行。

首先是血缘爆炸半径（lineage blast radius）。当一个列发生变化时，例如我们 PR 中扩大的那个列，脚本会遍历血缘工具有记录的该列的每个下游作业，并提出一个简单的问题：它们中是否有任何一个会崩溃？这是针对真实系统的真实检查。但请注意我划定的边界：它只能看到血缘工具中记录的内容。它对下游的视野，严格取决于该记录的完整程度，仅此而已。

其次是性能。一个正确的变更仍可能过慢或成本过高。因此，CI 性能测试会在预发环境（staging）中使用模拟数据，以与生产环境相同的数据量运行该变更。

这在 PR 合并之前告诉了我们两件事：集群规模对于该作业是否合适，以及该作业是否仍能满足其新鲜度 SLA。那些问题若非如此，往往会在数周后以故障（incident）的形式暴露出来。这就是第一层检查的完整集合。让我们看看它们对我们的 PR 给出了什么结论。

<details>
<summary>Original English</summary>
So let's start with layer one. Layer one is the scripts and their whole job is checking facts in the live systems. Things the code alone cannot tell you.

Here are the two of those checks and what they said about our running PR.

First data contracts. When a PR changes a schema, a script compares the schema and keys against a source of truth, the schema registry. for our PR. The question is simple. Does that new column actually exist upstream as registered in the registry? It does. So that check passes.

Second require tags. Every table needs an owner and any PII has to be labeled in the catalog. The script checks the catalog directly. Does our table have an owner? Yes. Is its PII labeled? Yes. pass again.

And if either of those had failed, there is no debate and no model involved. CI goes red like any other failing checks and the PR is blocked until it is fixed.

Contracts and tags are two of the layer 1 checks. Next, the two that look at downstream impact and performance. So these are the other two layer 1 checks. They look past the table itself, what happens downstream and whether the job will still run in time.

First, the lineage blast radius. When a column changes, like the one our PR widens, a script walks every downstream job the lineage tool has on record for that column and asks a simple question. Does any of them break? It's a real check against a real system. But notice the boundary I have drawn. It can only see what is recorded in lineage. Its view of downstream is exactly as complete as that record. No more.

Second, the performance. A correct change can still be too slow or too expensive. So the CI performance test runs the change in staging at the same data volume as production using mock data.

So that tells us two things before the PR merges. whether the cluster is sized right for the job and whether the job will still make its freshness SLA. Those are the kind of problems that otherwise show up weeks later as an incident. So that's the full set of layer 1 checks. Let's see what they said about our PR.
</details>

回到我们正在处理的 PR。还是之前的图。以下是第一层检查对它的结论：

数据契约检查访问了模式注册表，询问新列是否确实像注册的那样存在于上游。确实存在，检查通过。

血缘爆炸半径检查遍历了扩大列的每一个已注册消费者——即血缘工具有记录的作业。当该列从 integer 变为 big integer 时，没有任何作业损坏。它们看起来都没问题。与此同时，标签检查通过，性能测试通过。每一项检查都是绿色的。

就脚本所能看到的而言，这个 PR 是安全的。但我仔细推敲了这些措辞。就脚本所能看到的而言，幻灯片上的所有内容都是关于已注册情况的陈述——即我们的系统存有记录的作业和列。请记住这一点：这并不是事情的全貌。

<details>
<summary>Original English</summary>
So back to our running PR. Same picture as before. Here's what the layer one said about it.

The data contract check went to the schema registry and asked whether the new column really exists upstream as register. It does and the check passes.

The leanage blast radius check walked every registered consumer of the widen column. The jobs the lenage tool has on record. None of them break when the column goes from integer to big integer. They all look fine. Along with that tags pass, performance passes. Every check is green.

As far as the scripts can see, this PR is safe. But I chose those words carefully. As far as the scripts can see, everything on the slide is a statement about the registered picture, the jobs and the columns our systems have a record of. And keep that in mind. It is not the whole story.
</details>

### 第二层：Agent 代码遍历与隐蔽风险挖掘

现在让我们来看看带着 diff 的 Agent。究竟改变了什么？

PR 描述和提交信息解释了作者的意图，但意图绝不能用来掩饰实际发现的问题。如果描述说它是安全的，而代码表明相反，以代码为准。

文件工具允许 Agent 读取、搜索和列出整个代码仓库中的文件。它顺着变更追踪到 diff 之外的管道定义和访问权限授予中，寻找作者可能忽略的关系。

这些仅仅是代码仓库工具。Agent 无法查询运行中的元数据目录、血缘工具或生产状态。实时事实仍然是第一层的工作。Agent 是对代码进行推理。那么，为什么要为了一个模式变更去遍历代码呢？因为已注册的血缘并非全貌。

规则定义了判断属于什么范畴。它们根据 PR 中的变更类型进行配置，并已知晓第一层已经覆盖了哪些内容。它们针对查询反模式、敏感数据索取以及血缘之外的消费者。

例如，一个未分区的交叉连接（cross join）可以正确运行，但仍会重创集群。一项访问授权可能看起来平常，但仍会开放敏感数据。

对于模式变更，Agent 会遍历仓库中的管道定义和访问授权，以寻找未被注册的消费者。这是原本需要人类手动进行的繁琐搜索。

让我们回到我们的 PR，看看那项搜索发现了什么。

<details>
<summary>Original English</summary>
Now let's look at the agent with the diff. What actually changed?

The PR description and the commit messages explain the author's intent, but intent never explains away a real finding. If the description says it is safe and the code says otherwise, the code wins.

File tools let the agent read, search, and list the files across the repository. It follows changes beyond the diff into pipeline definitions and access grants looking for the relationships the author may have missed.

These are the repository repository tools only. The agent cannot query the live catalog lineage tool or production state. Life facts stay layer 1's job. The agent reasons over the code. So why walk that code for a schema change? Because registered lineage is not the whole picture.

The rules define where the judgment belongs. They are configured by the change type in the PR knowing what layer 1 already covers. They target query anti patterns, sensitive data asks and consumers outside lineage.

For example, an unpartitioned cross join can run correctly and still hammer a cluster. A grant can look ordinary and still open sensitive data.

And for the schema changes, the agent walks the pipeline definitions and access grants in the repository to find consumers that were not registered. It's a tedious search uh a person would otherwise do by hand.

Let's return to our PR and see what that search found.
</details>

回到我们正在处理的 PR。相同的图。第一层指出，扩大列的每一个已注册消费者看起来都没问题。现在 Agent 遍历了代码，它发现了一个血缘系统从未知道的作业。它就在仓库里。它从我们的湖表中读取那个扩大的列，但它从未在血缘系统中注册过，而这正是第一层检查无法看到它的原因。

那个作业获取该值并将其写入另一张表。而在另一张表中，该列仍然是 integer。

现在顺着这个流程看：我们的列现在是 big integer。当首次传入一个超出 integer 容纳范围的值时，该写入操作就会失败。一个有效的模式变更，CI 中显示绿色，通过了每一项已注册的检查，但下游作业仍然会崩溃。

Agent 在其审查评论中指出了完全相同的链路并附带推理过程。这样人类就能看到从我们的列到失败写入的完整路径。我们稍后会讲接下来发生了什么。

那么，为什么血缘系统会漏掉那个作业呢？因为企业数据世界是复杂的。工作负载跨不同的查询引擎运行，每个引擎都必须发布自己的血缘。如果其中一个没有发布，那么该关系就会从图景中缺失。并没有单一的元数据目录能够自动看清所有东西。因此，已注册的图景很有用，但它不是全貌。

现在我不想过分吹捧代码遍历。它确实非常有用，但它不可能看到一切。

Agent 能够搜索仓库中存在的内容：管道代码、访问授权，以及其中定义的读取我们表的作业。那就是它找到我们那个未注册作业的地方。但是大量的数据使用存在于代码库之外。例如某人手动运行的临时查询（ad hoc queries）。仪表盘（dashboards），这些对于仓库搜索来说是完全隐形的。存在于外部的消费者无论 Agent 搜寻得多么仔细也绝不会显现。因此，我们让 Agent 诚实面对这一局限。如果它没有找到任何东西，它不能声言不存在下游消费者。它只能声明在它搜索过的地方没有找到。**“未找到”不等于“不存在”**，Agent 永远不能宣称彻底排除隐患。

<details>
<summary>Original English</summary>
So back to our running PR. Same picture. Layer 1 said every registered consumer of the vid column looks fine. Now the agent walks the code and it finds a job that lineage never knew about. It's right there in the repository. It reads our widen column from our late table but it was never registered in the lineage which is exactly why the layer 1 check could not see it.

And that job takes the value and writes it into another table. And in that other table, the column is still an integer.

Now follow it through. Our column is a big integer. Now the first time a value comes through that's bigger than an integer can hold that right fails. A valid schema change green in CI passes every registered check and a downstream job still breaks.

The agent flagged exactly this chain in its review comment with the reasoning. So a person could see the whole path from our column to the failing right. We'll get to what happened next in a moment.

So why did the lineage miss that job? Because the enterprise data world is messy. Workloads run across different query engines and each engine has to publish its own lineage. If one does not publish, that relationship is missing from the picture. There's a single catalog that automatically sees everything. So the registered picture is useful but it is not the whole picture.

Now I don't want to oversell the codewalk. It's genuinely useful but it cannot see everything.

The agent can search what is in the repo. Pipeline code access grants and the jobs defined there that read our tables. That's where it found our unregistered job. But plenty of data use lives outside the codebase. Ad hawk queries that someone runs by hand. Dashboards, those are completely invisible to a repository search. A consumer out there never shows up, no matter how carefully the agent looks. So we make the agent honest about that limit. If it does not find anything, it does not get to say no downstream consumers exist. It says it found none in the places it searched. None found is not the same as none exist and the agent never gets to claim an allcle.
</details>

那么 Agent 遍历了代码之后，它究竟产出了什么？一份与优秀人类审查者给出形式相同的审查意见：

首先，针对关键具体代码行的审查评论，每条都附带其推理。不是模糊的“看起来有风险”，而是“这一行修改了这个列，而这里是读取它的作业”。

其次，风险评分。它所发现的问题严重程度如何。这就是驱动下一步行动的依据。接着它做出裁决：如果没有严重风险，它可以批准；如果存在需要人类介入的风险，它会升级给人类，并且评论和推理过程会一同附上。这样人类就拥有了进行调查的上下文，而不必从零开始。

需要明确说明的是，合入 PR 需要满足什么条件：第一层的检查必须通过，且审查必须批准——无论是 Agent 批准，还是升级后由人类批准。双方都必须表示同意。现在让我们看看对于我们的 PR 来说具体是怎样的。

这是我们正在讨论的 PR 实际的结局。同样的图景：已注册的消费者看起来没问题，代码遍历发现了一个未注册的作业，该作业将我们扩大的列写入一张它仍为 integer 的表中。

因为 Agent 发现了一处真实的下游破坏，它将风险评为高，并升级给人类，在审查评论中详细列出了整个链路。现在人类执行 Agent 无法完成的部分。Agent 只能对仓库代码进行推理，它无法查明该作业是否真正在生产环境中运行。人工审查员进行了核查，并确认 Agent 发现的消费者在生产中处于存活且活跃状态。因此这并非理论上的风险。该 PR 暂停合入。修复的关键在于顺序，而非拒绝该变更。下游表首先被更新，使其列能够处理更宽的类型，只有在那之后，我们的 PR 才合并并部署。没有引发生产故障。第一层的脚本提示安全，Agent 发现了缝隙，而人类做出了决断。

<details>
<summary>Original English</summary>
So the agent has walked the code. What does it actually produce? A review the same shape a good human reviewer would give you.

First review comments on the specific lines that matter each with its reasoning. Not awake looks risky but this line changes this column. And here is the job that reads it.

Second, a risk score. How severe is what it found. That's what drives the next step. Then it makes a call. If there is no serious risk, it can approve. If there is a risk that needs a person, it escalates to a human and the comments and reasoning go with it. So the person has the context to investigate instead of starting from scratch.

And to be clear about what it takes to merge, layer 1's checks have to pass and the review has to approve either the agent or after an escalation a person. Both have to say yes. Now let's see what that looked like for our PR.

Here is how our running PR actually ended. Same picture. The registered consumers look fine and the core walk found an unregistered job that writes our widened column into a table where it is still an integer because the agent found a real downstream break. It scored the risk high and escalated to a human with the whole chain spelled out in its review comment. Now the human does the part the agent cannot. The agent only reasons over the repo. It cannot see whether the job is actually running in production. human reviewer checked and confirmed that the consumer the agent found was live and active. So this was not a theoretical risk. The PR waited the f the fix was about order not about rejecting the change. The downstream table was updated first so its column could handle the wider type and only then did our PR merge and deploy. No incident. The scripts in layer 1 said safe. The agent found the gap and a human made the call.
</details>

### 人类必须保留的裁决与反馈循环

而且这并非孤例。大多数变更都可以由 Agent 放行。当检查通过且 Agent 对其结论有把握时，它会自行批准。但存在一整类变更，Agent 永远无权批准，无论它听起来多么有把握：

其一，涉及敏感数据的访问授权。谁能访问敏感数据，这是一个我们希望每次都由人类亲自把关的决定。

其二，看起来改变了意图而非仅仅是执行机制的迁移。如果一个变更改变了数据的含义，而不仅仅是它的移动或存储方式，由人类做出决定。

第三，如果 Agent 本身对其结论缺乏信心。它不能仅仅因为没有明确查出问题，就四舍五入直接批准。在这全部三种情况下，它的职责仅限于揭示风险及其背后的推理，决策权始终留在人类手中。

<details>
<summary>Original English</summary>
And that was not a one-time thing. Most changes can be cleared by the agent. When the checks pass and the agent is confident in its verdict, it approves on its own. But there's a whole category of changes where the agent never gets to say approved. And no matter how confident it sounds,

grants touching sensitive data are one. Who can reach sensitive data is a decision we want a person to own every time.

A migration that looks like it changes intent, not just mechanics, is another. If a change alters what the data means rather than just how it is moved or stored, a person decides.

And if the agent itself is not confident in its own verdict, that's the third. It does not get to round up to approve just because nothing concrete came back wrong. In all the all the three cases, its job is only able to surface the risk and its reasoning. The decision stays with a person.
</details>

那只是一个 PR。那么，该系统在我们遇到的所有 PR 中表现如何？审查器又是如何随时间推移而变得更好的呢？

我们如何知道标记是有用的，或者规则变更是否有帮助？我们从 Agent 的裁决及其在审查评论中的推理开始。人类回复表示同意或反对，并解释原因。正是这种解释让反馈变得有用，而不仅仅是一次投票。

这些回复每天都会被收集。每周一次，值班人员（on call）阅读反馈并手动更新审查规则。这些规则塑造了下一次审查。我知道目前这还是手动的。没有任何机制会自动重新训练，也没有规则会自动改变。不过我们有个想法，让一个故障调查 Agent 来协助完成每周的梳理，但目前尚未构建。没有这些反馈，每一次规则变更都将是一次猜测。因此，让我给你们展示一个人类纠正 Agent、并且我们利用该反馈改进下一次审查的例子。

这是一个真实的案例。请注意角落里的标签：这是一个单独的例子，不是我们的模式变更 PR。源数据库中的某一列被标记为个人信息。但当它进入数据湖时，摄取管道已经对其进行了加密。因此，该 PR 提议在数据湖中将其标记为非敏感（nonsensitive），尽管上游数据仍然是 PII。

Agent 标记了这一点。从它的立场来看，上游标明是 PII，因此非敏感标签看起来是不对的。作者提出了异议，并要求 Agent 查看其他表上的类似列之前是如何分类的，而不是单纯依据上游的标记。

一位人类工程师同意了作者的意见。写入前的加密使得该列的非敏感标签在此处是合理的。而这种纠正是促使规则变得更加明智的确切信号，因为下次出现类似列时，该上下文就可以阻止一次不必要的升级。

不过有一点需要注意：这取决于具体管道在写入前进行了加密。这并不是一条“加密总是使数据变为非敏感”的通用规则。

<details>
<summary>Original English</summary>
That is one PR. Now, how does this hold up across every PR we see? And how does the reviewer get better over time?

How do we know the flags are useful or whether a rule change helps? We start with the agents verdict and its reasoning in the review comments. A person replies agreeing or disagreeing and explaining why. That explanation is what makes the feedback useful rather than just a vote.

Those replies are collected every day. Once a week, the on call reads the feedback and updates the review rules by hand. Those rules shape the next review. I know this is manual today. Nothing retrains itself and no rule changes automatically. But we have an idea to let an incident investigation agent help with that weekly pass. But it is not built. Without the feedback, every rule change would be a guess. So let me show you an example where a human corrected the agent and we use that feedback to improve its next review.

So here's a real one. And note the label in the corner. This is a separate example, not our schema change PR. A column was marked as personal information in the source database. But by the time it lands in the data lake, the injection pipeline has already encrypted it. So the PR proposed labeling it nonsensitive in the data lake even though the upstream data is still PII.

The agent flagged this. From where it stood, the upstream says PII, so a nonsensitive label looked wrong. The author pushed back and asked the agent to look at how similar columns on the other tables were already classified instead of going purely off the upstream tagging.

A human agreed with the author. The encryption before write made the nonsensitive label look okay for this column. And that kind of correction is exactly the signal that teaches the rules to get smarter because the next time a similar column comes through that context can stop a needless escalation.

One caution though, this depends on the specific pipeline encrypting before the right. It's not a blanket rule that encryption always makes data nonsensitive.
</details>

那么我们如何知道审查器是否确实表现良好呢？

我们关注两类错误：它批准的有问题的 PR，以及它不必要地发送给人类的没问题的 PR。该矩阵区分了四种可能性：
- 没问题的 PR 被批准，以及有问题的 PR 被升级，是两种正确的结果。
- 有问题的 PR 被批准是一次漏报（miss）。那是危险的，因为变更上线了。
- 没问题的 PR 被升级是一次误升级（false escalation），它消耗了人类的时间。一个把所有东西都升级的把关机制或许可以避免漏报，但它并没有减轻审查负担。

截至 2026 年 8 月 31 日，我们的漏报率约为 2%。这主要源于规则中的空白，而非判断力的失误。我们没有一个单一且明确的误升级数据，但主要原因往往是缺少上下文，就像我刚才给你们举的加密列的例子。

漏报为我们带来新规则，而误升级则向我们展示审查器所需的上下文。这里就是其中一次漏报的例子。再次注意标签：这是一个单独的例子，不是我们的模式变更 PR。

我们有一份开放权限的某些数据副本。其中部分列即将被重新打标，并且有一个下游读取者正从该开放副本中读取这些列。

隐私合规将这些列重新标记为个人信息。当这种情况发生时，它们被移入一个限制更严格的数据副本中，并从开放副本中移除。

这次重新打标看起来没问题并被合并了。但没有人检查的是：下游是否仍有任何东西在从旧的开放副本中读取那些列。确实有作业在读。一旦这些列被移除，那个读取者就崩溃了。这是一次漏报：一个本应被升级的 PR 被批准了。

这并不是判断力的失误，而是规则上的漏洞，一个之前没有人写下来的边界情况。因此，它变成了一条新规则：当一个列被重新标记为敏感时，搜索代码库，查看是否有人仍在从即将失去该列的副本中读取它。规则就是这样变得越来越完善的：发现漏报，并将其转化为新规则。

<details>
<summary>Original English</summary>
So how do we know whether the reviewer is actually doing a good job?

We look at two kinds of mistakes. Bad PRs it approved and fine PRs it unnecessarily send to a person. That matrix separates four possibilities. A fine PR approved and a bad PR escalated are the two correct outcomes. A bad PR approved is a miss. That's dangerous because the change ships. A fine PR escalated is a false escalation that costs a person's time. A gate that escalates everything may avoid misses, but it has not reduced the review load.

As of August 31st, 2026, our miss rate was about 2%. Mostly from the gaps in the rules rather than the failures of the judgment. We don't have a clean single false escalation number. But the dominant cause is missing context like the encrypted column example that I just gave you.

Misses give us new rules and false escalation show us context the reviewer needs. So here is one of those misses. Again know the label. This is a separate example, not our schema change PR. We have an open copy of the sum of some data. some of its columns are about to be rettagged and there is a downstream reader that reads those columns from the open copy.

Privacy retag those columns as personal information. When that happens, they move into a more restricted copy of the data and they are gone from the open copy.

The retag looked fine and it merged. But what nobody checked was whether anything downstream was still reading those columns from the old open copy. something was. And once the columns were gone, that reader broke. That's a miss. A PR that should have been escalated got approved.

It wasn't a failure of judgment. It was a gap in the rules. A coroner case nobody had written down. So, it became a new rule. When a column gets retagged as sensitive, search the codebase for anyone still reading it from the copy that's about to lose it. And that's how the rules get better. the misses get found and get turned into new rules.
</details>

### 成效数据与架构演进方向

现在让我们把所有内容串联起来。大家还记得开头的那个在 CI 中显示为绿色的拉取请求。对它进行了三件事：

首先，脚本证明了真相来源所能证明的内容：契约、标签、已注册血缘和性能测试全部通过。

其次，Agent 阅读了代码，发现了脚本无法看到的内容：一个血缘系统从未得知的作业，正在静默等待因列变宽而崩溃；它标记了整个调用链并进行了升级。

第三，人类确认了该作业是活跃运行的。下游表首先得到修复，只有在那之后，PR 才得以合并。没有引发生产故障。而在这一切背后，审查器随着人类每一次纠正转化为规则而不断改进。

这些数据截至 2026 年 8 月 31 日。你可能会问：Jas，这一切真的奏效吗？

是的。大约 **60%** 的数据管道 PR 在没有人类审查的情况下完成合并。我们看到手动审查工作量减少了大约 **75%**。Agent 具体的评论和推理有助于聚焦审查重点，而不是让人类从零开始重建每一项风险。节省的时间每月约为 **132** 个工程工时。与这些 PR 相关的故障减少了约 **30%**。

这并不意味着完全无人审查。按照设计，受保护的决策仍然会到达人类手中。目标是减少审查工作量，而不是免除责任。

这就是取得的成效。现在，让我们看看我们在架构选择上犯的错误。

<details>
<summary>Original English</summary>
So let's pull it all together. You remember the pull request from the start, the one that was green in CI. Three things happened to it.

First, scripts proved what a source of truth could prove. The contracts, the tags, the registered lineage and performance all passed.

Second, the agent read the code and found what the scripts could not see. A job that Lineage never knew about, quietly waiting to fail on a wider column, it flagged the whole chain and escalated. Third, a person confirmed the job was live. Uh, the downstream table was fixed first and only then did the PR merge. No incident. And behind all of that, the reviewer keeps getting better because every correction a person makes can become a rule. These results are as of August 31st, 2026. So you might ask, Jas, does it all work?

Yes, about 60% of the data pipeline PRs merged without a human review. We have seen about 75% less manual review effort. The agent specific comments and reasoning help focus the review rather than making a person reconstruct every risk from scratch. The time saved comes to about 132 engineering hours a month. Incidents tied to these PRs are down about 30%.

And that does not mean human free review. The protected decisions still reach a person by design. The goal is less review work, not removing accountability. And those are the results. Now, let's look at the architecture choices we got wrong.
</details>

这是我们当前设计中的不足之处：第一层和第二层是独立的系统，各自独立触发并并行运行。各自产生自己的结果。在我们构建它时，这看起来像是一个显而易见的设计；

但是，双方都看不到对方的通过、失败或故障状态。第二层知道脚本被配置用来覆盖什么，但不知道它们运行时发生了什么。合并仍然需要通过检查并获得批准审查，但没有任何单一系统拥有完整的运行时图景。

此外，Agent 无法调用实时运行的第一层检查。它的工具只能读取、搜索和列出仓库文件。如果一项判断需要来自实时生产系统的实时事实，它无法自行获取该事实。

当一方无法完成时，我们就等待人类介入，不存在自动回退机制。这些是当前的局限性，也促成了后续的方案。在下一张幻灯片中，平台团队正在探索单一入口点。这是一个提议方案，而非当前运行的系统。左侧是当前的设计，右侧是我们的目标方向。分类器会审视整个 PR，然后决定哪些变更分开审查，哪些变更合并在一起审查。这是一个针对整个 PR 的决定，而不是对每个文件进行独立路由。

Agent 还将获得第一层的各项检查，作为与其仓库工具并列的可调用工具。当判断需要实时事实时，它可以请求执行相应的检查，而不再局限于代码本身。

这里的目标是建立一个能够纵览整个 PR 的单一系统。我们尚未构建此系统，所以这是一个方向，而非既有结果。

<details>
<summary>Original English</summary>
Here is what we got wrong today. Layer 1 and layer 2 are separate systems triggered independently and running in parallel. Each produces its own result that seemed like an obvious design when we built it,

but neither sees the others pass fail or outage state. Layer 2 knows what the scripts are configured to cover, not what happened when they ran. Merge still needs passing checks and an approving review, but no single system has a full runtime picture.

The agent also cannot call live layer 1 checks. Its tools only read, search and list the repository files. If a judgment needs a live fact from a live production system, it cannot fetch that fact itself.

When one site cannot finish, we wait for a human. There is no automatic fallback. These are current limitations and they motivate the proposal. On the next slide, platform team is exploring one entry point. This is a proposal and not what's running today. The left panel is the current design and the right is where we want to go. A classifier looks at the whole PR then decides which changes to review separately and which to review together.

This is a whole PR decision, not independent routing of each file. The agent would also get the layer 1 checks as collable tools alongside its repository tools. When judgment needs a live fact, it could request the appropriate check instead of being limited to code alone.

The aim here is one system with the whole PR in view. We haven't built this yet. So, it's a direction, not a result.
</details>

### 核心启示总结

让我以我们希望带走的经验来作结。

这就是用三句话总结的完整演讲：

1. **确定性评估**：首先，如果某件事可以通过真相来源证明，就让脚本去证明它。不要把判断力浪费在一个“是或否”的事实上。这不仅更清晰，而且更便宜。脚本证明的每一个事实，都是永远不需要 AI 介入的审查工作，因此运行成本得以维持在低位。
2. **标记绝不放行**：不是针对每个 PR，而是针对那些真正让人担忧的变更，例如敏感权限授予、迁移意图变更以及低置信度裁决。在这些情况下，Agent 的职责止步于呈现风险及其背后的推理，决策权每一次都留在人类手中。
3. **统计误升级**：一个把所有内容都升级的把关机制并没有真正为任何人节省时间，它只是把工作转嫁了出去。要像衡量漏报一样去衡量这项成本。

我开头提到了一个在 CI 中显示绿色的拉取请求，以及一个问题：PR 正以机器的速度到来，而具备上下文能安全审查它们的人却太少。我们构建了一个混合审查器：脚本负责事实，Agent 负责判断，人类负责受保护的裁决。我们带领一个 PR 走过了这三层，见证了审查负担的减轻而没有完全剔除人类，并看到了它是如何从纠正中学习的。我们告诉了大家我们的设计不足，并留给你们三条经验教训：**以低成本证明你能证明的事**；**针对令人担忧的变更进行标记且绝不放行**；以及**统计误升级**。

那么，究竟谁来审查机器人？脚本负责真相来源所能证明的一切，Agent 负责需要上下文和判断的一切，而人类负责只有他们才能做出的决定。感谢大家的聆听。

<details>
<summary>Original English</summary>
Let me close with what we would carry forward.

So, here is the whole talk in three lines.

Deterministic evaluations. First, if something can be proven against a source of truth, let a script prove it. Don't spend a judgment call on a yes or no fact. It's not just cleaner, it's cheaper, too. Every fact a script proves is review work that never needs AI. So, the cost of running this stays down.

Flag never clear. Not for every PR, but for the changes that actually scare people, like sensitive grants, migration intent, and low confidence verdicts. There, the agent's job stops at surfacing the risk and the reasoning behind it. The decision stays with the person every time.

Count the false escalations. A gate that escalates everything is not actually saving anyone any time. It's just moving the work around. measure that cost the same way you measure a miss. So I started with a pull request that was green in CI and a problem PRs arriving at machine speed and too few people with the context to review them safely. We built a hybrid reviewer scripts for the facts and agent for judgment and people for the protected calls. We walked one PR through all three saw it get lighter without going human free and saw how it learns from the corrections. We told you what we got wrong and we left you with three lessons. Prove what you can cheaply. Flag and never clear the scary changes. And count the false escalations.

So who reviews the bots? Scripts for everything a source of truth can prove, an agent for everything that needs context and judgment, and humans for the calls only they get to make. Thank you for listening.
</details>