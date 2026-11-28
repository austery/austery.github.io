---
author: AI Engineer
date: '2026-11-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-X3yXTwGs9A
speaker: AI Engineer
tags:
  - code-review
  - incident-response
  - developer-velocity
  - site-reliability-engineering
title: AI 生成代码激增下的代码审查瓶颈与 SRE 运维挑战
summary: Sourcegraph 的 Andrew Norrish 指出，随着 AI 编码工具的普及，代码瓶颈已从编写速度转向人工审查速度，导致未经充分审查的代码引发更多生产事故。演讲探讨了 SRE 与平台团队在面对事件激增时的排查、预防与批量修复方案。
insight: ''
draft: true
series: ''
category: debugging
area: tech-engineering
project: []
people:
  - Andrew Norrish
companies_orgs:
  - Sourcegraph
products_models: []
media_books: []
status: evergreen
---
### AI 时代开发瓶颈的转移与现场工程视角

欢迎来到面向华尔街、SRE 和平台工程的 AI 信任层分享。我叫 Andrew Norrish，是 Sourcegraph 的现场工程总监。我们的现场工程师工作在面向客户的第一线，与全球一些最大规模公司的软件工程师及其他技术团队成员紧密合作，帮助他们利用 Sourcegraph 平台更好地构建和管理代码库。

<details>
<summary>Original English</summary>
>> Um welcome to AI's trust layer for Wall Street, SRE and platform engineering. My name is Andrew Norish. I'm the director of field engineering at Sourcegraph. Our field engineers work on the front lines with our customers, collaborating closely with the software engineers, the other technical team members at some of the largest companies in the world, and helping them build and manage their code bases better using the Sourcegraph platform.
</details>

如果您之前没有听说过 Sourcegraph，我们构建的是代码搜索和代码图谱产品，帮助世界上拥有最大、最复杂代码库的管理者深入理解这些代码库。

在过去将近 13 年里我们一直在为人类开发者提供支持，而在过去一年左右的时间里，我们也开始为智能体（agents）构建支持，它们已经成为我们的主要客户。对于这些智能体而言，所有这些代码库工具、代码搜索、代码图谱和代码导航，已经演变成为一个**代码库上下文引擎**。

今天，我想少谈一些 Sourcegraph 如何直接支持开发者在键盘上敲代码构建代码库，而是更多地聚焦于 AI 驱动的软件开发变革如何影响了这些服务的一线运维支持，以及 Sourcegraph 可以在哪些方面提供帮助。

<details>
<summary>Original English</summary>
If you haven't heard of Sourcegraph before, we build code search and code graph products that help the owners of the largest code bases and the most complex code bases in the world deeply understand those code bases.

For the last year or so, on top of the humans that we've been supporting for the past almost 13 years, uh we've also been starting to build support for agents, and they've been our primary customers. Uh for those agents, uh all this code base tooling, code search, code graph, code navigation has become a code base context engine.

Uh today, I do want to talk a little bit less about how Sourcegraph directly supports the hands-on keyboard work of developers building those code bases, and focus more on how AI-driven changes in software development have impacted frontline support for those services, and where Sourcegraph can help.
</details>

### AI 编码普及带来的连锁反应：代码膨胀与审查瓶颈

我想先从一个故事讲起。这是我们从众多客户那里一次又一次听到的故事，尤其是在过去几年伴随智能体编码兴起的大背景下。这个故事的开头总是相似的：AI 驱动的开发开始增长。相信大家对此都深有体会，这也是我们今天齐聚于此的原因。

工程团队越来越依赖 AI 和智能体工具来辅助工作。这些工具不可避免地带来了开发者速度的显著提升，代码库也随之迅速膨胀。

组织为 AI 工具投入了巨额预算，并期望开发者重度使用它们，以此来证明这些采购支出的合理性。在过去几年里，基本上任何 AI 路线图上的首要问题都是：“这能帮我们节省多少人头？”

对吧？不过，在 Sourcegraph 最近一次的客户顾问委员会会议上，这个以往必问的问题破天荒地完全没有被提及。这表明大家的思维方式显然正在发生转变。

<details>
<summary>Original English</summary>
I wanted to start today with a bit of story time. Um this is a story that we have heard time and time again from so many of our customers, especially over the past couple years with the rise of agentic coding. Uh this story always starts the same, with an increase in AI-driven development. I'm sure this is something Obviously, we're all here. That's why we're here.

Um engineering teams increasingly rely on AI and agentic tools to support their work. These tools inevitably lead to significant increases in developer velocity, and code bases inevitably start ballooning.

Um organizations dedicate huge budgets to AI tooling and expect developers to use them heavily and just to justify those purchases that they're making. Uh and for the the past couple of years, the first question on basically any AI roadmap was how many heads can this save us,

right? Um in Sourcegraph's most recent customer advisory board though, that question for maybe the first time ever just didn't come up. So, the mindset is clearly shifting.
</details>

这就引出了新的瓶颈——**代码审查（Code Review）**。

我们开始从众多客户那里反复听到这一点。随着开发速度加快、企业内部面临使用已购工具的压力，以及期望产品发布节奏能与 AI 工具的使用成比例提升，开发者的工作重心不可避免地开始转移。

以往的瓶颈在于软件开发本身，受限于开发者的带宽以及人类敲代码的速度；而现在的瓶颈非常明确地转移到了**人类审查 AI 编写代码的速度**上。

<details>
<summary>Original English</summary>
That brings in code review as a bottleneck.

We have started to hearing this time and time again from so many of our customers. Between the increase in developer velocity, the pressure to use tools purchased by the business and the expectation that product releases should increase proportionally to the use of these AI tools, the developer priorities have never inevitably started shifting. Where the bottleneck used to be software development and in software development used to be developer bandwidth and how quickly a human can just type code, that bottleneck is now very clearly with how quickly humans can review the code that the AI is now writing.
</details>

### AI 诱发事故激增与 SRE 面临的重负

随之而来的，是 AI 引发的生产事故激增。

AI 不仅写代码更快，写的量也庞大得多。PR 数量增加的同时，PR 的体积也在急剧膨胀。至于开发者是否真正信任他们提交的代码，相比于疲于应付眼前堆积如山、亟待审查的 PR 列表，已经变得次要得多。

AI 编写的 PR 通常缺乏在更大代码库和组织层面上达到生产级质量所需的上下文，如今越来越常见的情况是，这些代码未经人工审阅就被合并到了生产环境中。

代码审查者遗漏破坏性变更（breaking changes）并将其合入，只是时间问题。随着 AI 使用量的增加，AI 造成的生产事故也同步增加。

<details>
<summary>Original English</summary>
As part of that, comes the rise of AI-initiated incidents.

AI isn't just writing code faster, it's writing so much more of it. PR counts have increased as PR sizes have ballooned. Uh and whether or not developers actually trust the code that they're pushing now matters a whole lot less than just getting ahead of an ever-growing list of PRs that they need to review.

AI-written PRs often lacking the organizational and in larger code base context needed to actually be production-quality gets merged into production without a human ever seeing it more often than not now.

It matters it's only a matter of time before breaking changes are missed and merged by code reviewers. And AI as you AI usage increases, so do AI-caused incidents.
</details>

这就导致了 SRE 团队疲于奔命。越来越多的 SRE 需要在缺乏操作手册（runbooks）且代码可能从未有人类看查过的情况下，去处理更大批量的生产事故。

解决这些事故所需的上下文同样极为匮乏，正因为此前从未有人类接触过这部分代码，追踪排查变得比以往更加困难。这些事故发生得愈加频繁，解决耗时更长，且反复出现。故障成本不断上升，而解决问题的重担持续落在一线支持团队身上。

管理层开始尝试通过招聘更多 SRE 来作为权宜之计，但这岗位的市场需求正变得越来越大，招聘成本不断走高，而事故增长的速度正迅速超过企业通过招人来解决问题的能力。

这同样是我们从客户那里屡见不鲜的现象。如果各位对此感同身受，可以举手示意一下。是的，确实如此。

<details>
<summary>Original English</summary>
Enter the SREs becoming stretched. More and more SREs are required to resolve larger volumes of incidents without runbooks and code that maybe a human has never even looked at before.

Uh the context were required to resolve these incidents is lacking again because a human has never seen it and it's even harder to track down than it was before. These incidents are becoming more frequent. They take longer to resolve. They pop up on a recurring basis. They're costlier and the burden just continues to fall to our front-line support to resolve them.

Leadership has started looking to hiring more SREs as as a band-aid solution, but the role is increasingly in more and more high demand. It's getting more expensive and the rise of incidents is quickly starting to outpace the ability to hire people to resolve them.

Again, this is something that we have started hearing time and time again from our customers. Uh raise raise your hand if if this is something you guys are feeling. Yeah.
</details>

### 上下文缺失与跨服务治理困境

我们观察到的一些规律：显而易见，正如我刚才提到的，审查成为了新的瓶颈。

我们从许多客户那里都听到了这种反馈。不仅是因为 AI 承担了更多代码编写工作，更因为大家对 AI 生成代码的不信任，导致开发者被要求花费更多时间进行审查。组织越来越期望开发者花时间做代码审查，以验证这些由 AI 编写的不可信代码是否符合组织的规范、监管合规要求。

话虽如此，AI 当然依然存在幻觉。它确实在变得越来越好，大家都喜欢它，这也是我们在这里的原因，但它并不完美。在非常庞大、复杂的组织中尤为如此，这类组织往往存在大量遗留代码，AI 根本不具备按组织预期构建产品所需的全部上下文。

如果无法在本地克隆整个代码库，AI 就只能靠推断和猜测。有时这些猜测是有根据的，但很多时候意味着它对自己所处的构建环境仅有局部视野。

结果就是，越来越多的故障源头最终追溯到了未经充分审查的 AI 代码。

<details>
<summary>Original English</summary>
So, a couple of patterns that we've started to seeing. Obviously, I mentioned review as the new bottleneck. Um we've started to hearing this a lot from from a lot of our customers. Not only is AI responsible for writing more of the code, but because of a lack of trust in that AI written code, the developers are expected to spend more time reviewing it. Um organizations more and more expect developers to spend their time performing code review to verify that this untrusted code written by the AI meets their standards, the regulations, the requirements of their organization.

That being said, I mean of course AI still hallucinates. It's getting a whole lot better. We all love it. That's why we're here, but it's not perfect. And um this is particularly true in really large, really complex organizations maybe with a whole lot of of legacy code where the AI just doesn't have all of the context needed to actually build the product in the way that your organization might need it to. If you can't clone the entire codebase locally, the AI just needs to make judgment calls and make guesses. Sometimes they're informed, but often it just means they uh only have a partial view of the environment that they're building in.

As a result, incidents increasingly have started tracing back to unreviewed AI code.
</details>

这一重担再次落在了应急响应人员肩上，而他们在处理事故时，往往对涉事代码缺乏了解。

不仅是智能体，人类工程师在面对跨服务问题时同样容易受挫。如果难以排查跨服务故障的根因，组织就会退回到缓慢且易出错的传统人工排查方式，比如逐个扫描 commit。

因此，修复的速度根本跟不上事故的产生。在一个仓库中找到的修复方案，往往同样适用于其他成百上千个仓库。如果依赖分散的各个团队各自去仓库里应用这些修复，往往来不及快速发布，漏洞和问题就会被遗漏。

在各位所在的行业中，这一情况尤为突出。在金融机构工作，各方面的要求都要高得多，并且承担着满足所有法规与合规要求的责任。

我不想在接下来的几张幻灯片上的数据上花太多时间，但展示这些是为了让大家了解行业同行是如何看待这个问题的，以及他们做的一些数据分析。我调出几张看看。

<details>
<summary>Original English</summary>
And that burden again falls to the responders uh who often at times have a lack of context in the code that they're responding to the incident for. Uh agents and engineers alike fail on things like cross-service problems. If it's difficult to track down the root cause of the these cross-service issues, organizations start falling back to slow and air-prone manual solutions to resolve them like commit scanning.

And as a result of that, remediation just simply cannot keep pace anymore. A fix found in one repo often applies to hundreds if not thousands of others. It If disparate teams are relied upon to apply those fixes within the repos, the fix can't go out quick enough more often than not um and things start getting missed.

All of this is even more true in the industries that you all are working in. Um when you're working in a financial institution, the stakes are just a whole lot higher and you have the responsibility for meeting all of those regulatory and compliance requirements. Uh I don't want to spend too much time on these next numbers that I have on the next few slides, but just to kind of show you how some of our our industry peers are thinking about this and some of the analytics that they've they've done. Um I'll pull up a few.
</details>

### 行业调研数据：质量、信任与理解力的下滑

哎，这张幻灯片自己删掉了，不过没关系。

这张幻灯片原本主要是展示关于到 2027 年预计有多少新代码将由 AI 编写的预期。相信你们有些人已经看过这个数字了：普遍预期届时将有大约三分之二的代码由 AI 编写。

看，又恢复出来了。

作为其中的一部分，正是我之前提到的代码审查挑战：一些组织估计，借助智能体编码，目前合并的 PR 数量几乎是过去的两倍；这些 PR 的体积是纯人工编写 PR 的两倍以上；这意味着开发者现在花在代码审查上的时间几乎翻了一番。

<details>
<summary>Original English</summary>
Ooh. Well, this slide just deleted itself, but um yeah, this uh this slide was basically just demonstrating the expectations for how much new code is going to be written by AI come 20 27. I'm sure some of you have seen the number. It's about 2/3 of of code now um is the expectation. Oh, there it goes.

Um as part of that, the code review challenge that I mentioned earlier, um so some organizations are estimating that almost twice the number of PRs are being merged now with agentic coding. The size of those PRs are is more than double the size of just a human-written PR um and that means developers are starting to spend almost twice as much time just doing code review.
</details>

除此之外，开发者越来越常觉得 AI 编写的代码实际上更难审查，因为它并非由人类编写，也未必始终是面向人类阅读习惯而写的。

对 AI 代码的信任度依然严重滞后。几乎每位开发者都会表示，他们并不会完全相信 AI 为他们编写的所有内容。但令人惊讶的是，与此同时，近半数的开发者坦承他们并不总是会去验证 AI 为他们生成的代码。对于一家企业来说，这确实相当令人担忧。

正如我前面所说，其后果就是代码质量与安全性的下滑：每个 PR 关联的故障增加，越来越多的事故直接追溯到 AI 生成的 PR。

随着事故增加，系统稳定性出现滑坡。更多与部署相关的故障被定位到 AI 生成的代码，回滚、紧急热修复以及影响客户的生产事故均有所增加。

与此同时，Anthropic 开始报告指出，由于开发者越来越依赖 AI 代写代码，他们自身对这些代码的理解力也正在下降。

<details>
<summary>Original English</summary>
Um On top of that, the developers are feeling that more often than not AI-written code is actually more difficult to review uh because it wasn't written by or necessarily always for a human.

Trust in AI code is still lagging tremendously. Almost every developer will say that they don't trust everything that AI is writing for them. And surprisingly at the same time, almost half of developers will say they don't always verify the code that AI is writing for them. Kind of scary for an enterprise, right?

As a result, quality and security decline, like I mentioned. Um more incidents per PR, more incidents being traced back just to AI-generated PRs as well. And stability declines as those incidents rise. Um more deployment-related issues are being traced back to AI-generated code. And there's been an increase in things like rollbacks, hot fixes, customer-impacting incidents as a result of it.

All of that at the same time, Anthropic has started reporting that because developers are becoming more and more reliant on AI to write the code for them, their comprehension of that code is also at a decline.
</details>

### SRE 与平台团队破局：在确定性边界内发挥 AI 价值

这就是我今天来到这里的原因：SRE 和平台团队的繁重杂务（toil）正在激增。

AI 编写的代码变多、对代码的信任不足、代码审查速度跟不上、质量与安全性下滑，共同导致了面向客户的事故大幅增加。这全都压在了一线支持人员的头上，要求他们去修复可能此前没有任何人审阅过的代码故障。

我不想在这里一味宣扬悲观情绪，我知道自己在负面问题上讲了不少时间。但就目前而言，AI 真正展现成效的地方，并非在那些试图全面接管软件开发的大而全的宽泛自动化场景上。如果真是那样，我们大家早就失业了。

相反，当你能将 AI 的聚焦点收敛在**边界清晰的领域**，并提供满足组织合规要求的完备上下文时，AI 展现出的价值要大得多。例如：
- 漏洞修复
- 安全扫描
- 大规模代码迁移
- 非研发人员快速构建自有原型工具

在这些具有明确边界的领域和场景中，AI 才开始真正取得成功。这正是我认为 SRE 和平台团队大有可为的地方。

<details>
<summary>Original English</summary>
Enter why I'm here today, the rise of SRE and platform team toil. More code being written by AI, lagging trust in that code, inability to keep pace with code review increases, and declining quality and security leads to a large increase in customer-facing incidents. That lands on the heads of all of our front-line support folks who are then asked to fix issues that, like I mentioned, a human may or may not have ever even looked at before.

Um I don't want to be up here just doom and gloom. I I know I've spent a whole lot of time on on negatives here. Um but yeah, at least as of today, where AI is actually winning, it's not necessarily on this like end-all be-all broad automations of developing code, right? If it were, then we would all be out of jobs. Um AI is winning a whole lot more though when you can narrow its focus to well-bounded domains with all of the necessary context to meet your organizational and compliance requirements. Things like vulnerability remediation, security scanning, large-scale migrations, non-developers prototyping their their own tools, things like that with really bounded domains and bounded ideas um are where it starts to succeed. And that's where I think SREs and platform teams come in a whole lot more.
</details>

SRE 和平台团队在这些定义清晰、边界明确的半自动化领域中工作已经有很长一段时间了，显然远在 AI 出现之前就已如此。

正因如此，他们如今成了双重角色：一方面，通过观察 AI 代码引入了多少故障，他们是衡量组织内 AI 编码有效性和可靠性的风向标；另一方面，他们也是能够从有效使用 AI 中获得最高收益的团队。他们日常本就依赖自动化修复工具、半自动应急响应手册、CVE 监控与治理。

因此，这些团队一方面在构建流程和工具以防止 AI 诱发的故障泛滥，但耐人寻味的是，他们同时也是最能将 AI 嵌入现有半自动流程以换取实实在在的生产力与安全性提升的团队。

<details>
<summary>Original English</summary>
Um SREs and platform teams have been working in these well-bounded, well-defined, semi-autonomous areas for a very, very long time at this point. Obviously, way, way before AI was even around.

And because of that, they're now both kind of the barometers for how effective AI coding is and how trustworthy it is within your organization by how many incidents that AI code is producing. Um but they're also the teams that can see some of the highest gains uh from effective AI usage. Uh they already work with automation automated remediation tooling, semi-autonomous incident response runbooks, CVE monitoring and remediation.

Um so, those teams build the processes and tooling to prevent AI-initiated incidents from becoming rampant, but ironically, they're also the teams that can leverage AI within their semi-autonomous existing processes to see real productivity and safety gains.
</details>

### Sourcegraph 能力支撑：调查、预防与批量修复

回到 Sourcegraph 以及我和我的团队所做的工作。

正如我提到的，我们是一个代码理解、代码搜索和代码导航平台。我们的大部分工具首要的出发点是**防止 AI 引入的故障发生**，这是最理想的状态。我们为开发者和智能体提供工具，使其能够高效、准确地检索代码，深入理解代码，并利用这些知识构建更健壮的服务。

同时，这套工具在定位和排查问题方面也极其高效。针对 SRE 和平台团队的场景，这也是我在接下来的演讲中想要重点探讨的内容。

简要介绍一下 Sourcegraph 的功能全景：我们的底层核心是一个完整的**代码图谱（code graph）**，它对整个组织的代码库建立完整索引，为我们所有功能提供支持。往上一层是经过十多年构建和调优的代码搜索与代码智能，使人类和智能体能够极其迅速高效地在庞大复杂的代码库中进行导航。

代码图谱、搜索和智能共同构成了我前面提到的面向智能体的上下文引擎。它们支持通过 LMTP 等方式接入，从底层驱动我们自身的 AI 和智能体功能，确保人和智能体拥有更好的上下文来编写高质量代码。

<details>
<summary>Original English</summary>
Um want to go back to Sourcegraph, what my team and I do. Um as I mentioned, we're a code intelligence code understanding, code search, code navigation platform. Um and much of our tooling is built first and foremost to prevent some of those AI-introduced incidents from occurring in the first place, cuz that would be ideal. Uh tools for developers and agents to search through code efficiently and accurately, understand that code deeply, and use that knowledge to better build and more robust services.

That same tooling is also really, really effective for issue identification and resolution as well. And in the context of SREs and in platform team, that's where I want to focus for the rest of this talk.

Just to give you a high-level overview of kind of what Sourcegraph is, some of our features. Um at our core, we have a full code graph, a complete index of of your organization's entire codebase uh that really powers kind of all of our features and everything that we do. The next level up from there, as I've mentioned a few times, is code search and code intelligence. These tools that we've spent over a decade building and tuning to give human and agents the ability to navigate, especially really large and and complex codebases extremely quickly and efficiently.

Uh the graph, search, and intelligence form kind of the context engine that I mentioned for agents specifically. Uh they're accessible via our LMT P, and they really power at our core all of our own AI and agentic-enabled features uh that ensure humans and agents have the information and the context they need to build code better.
</details>

在具体思考 SRE 角色以及 Sourcegraph 如何赋能 SRE 时，我将其拆分为三个核心环节，这也正是任何 SRE 工作流的核心所在：**调查（Investigation）**、**预防（Prevention）**和**修复（Remediation）**。

- **调查（Investigation）**：借助 Sourcegraph 的工具，我们能将根因排查时间从数天缩短至数分钟。由 AI 编写的代码所引发的问题，排查起来会更加容易。经典的确定性搜索允许通过单次查询跨越每个代码仓库、每个分支和每一次提交；而基于智能体的 Deep Search 功能，让你可以直接提问“哪里出了故障”，并获得带有代码引用的可靠答案。
- **预防（Prevention）**：能够快速排查出根因固然很好，但防患于未然显然更佳。Sourcegraph 提供了内置的监控告警能力，当提交高风险代码或命中某些不合规模式时触发提醒。通过这些监控，可以确保 AI 编写的代码完全遵循组织在生产环境中要求的模式与规范。
- **修复（Remediation）**：在识别出缺陷或高风险模式后，如何确保修复补丁能快速覆盖代码中所有受影响的区域？Sourcegraph 不仅能找出所有受影响的范围，还支持跨整个组织的全部代码仓库进行**批量变更（Batch Changes）**，迅速完成修复，防止问题在其他团队或服务中蔓延。

<details>
<summary>Original English</summary>
Um So, when I'm thinking about SRE specifically and how Sourcegraph can help SREs, uh I kind of broke it down into these three areas. And obviously, these are at the core of any SRE workflow. Investigation, prevention, and remediation.

On the investigation front, with Sourcegraph, we have the tooling to find the root cause of cause of issues in minutes instead of days. Uh these issues that are being created by uh AI-written code uh are much easier to investigate, find. Uh our classic deterministic search allows you to search across every repo repo, every branch, every commit with just a single query. And then deep search, our identic search feature, allows you to easily ask what's broken, get cited answers, and be confident in the responses that that you're receiving.

On the prevention front um it's obviously great to be able to find the root cause of a lot of these issues really quickly, but it's even better to prevent them from occurring to begin with. Um at Sourcegraph, we have built-in monitoring capabilities to alert when risky code is committed, when certain patterns are matched that may be non-compliant, things of of that nature. And through these monitors, you can ensure that AI-written code follows all of those patterns and requirements that you and your organization have in production.

And then lastly, remediation. Once you've even uh identified a break or a risky pattern, how do you make sure that that fix is applied quickly and to all impacted areas of your code? Uh Sourcegraph tooling allows you to find all those impacted areas like I've mentioned, but we also have the ability to make bulk changes across all of your repos within your entire organization to remediate them and make sure that they don't occur across other services with other teams, whatnot, very, very quickly.
</details>

### 实践案例：安全分流、根因分析智能体与大规模单体评测

在剩下的时间里，我想分享几个内部实践以及客户应用这些原则的具体案例。

**案例一：安全漏洞报告分流**。这是 Sourcegraph 内部落地的实践。我们建立了大量类似的工作流来维护代码库并提高自治程度。早在 ChatGPT 出现之前，我们的安全团队就一直在使用 HackerOne，但近来收到的报告数量急剧上升，需要实时研判：这是否值得团队投入时间深入处理？

于是团队配置了 HackerOne 的 webhook，将其对接到我们的智能体搜索能力中，由其自动研判我们团队是否需要介入排查、是否需要提出修复方案、是否需要由安全人员做进一步深入审查，亦或是可以直接忽略。

<details>
<summary>Original English</summary>
Uh I With the remaining time here, wanted to walk through just a couple of examples of how we at Sourcegraph and some of our customers have applied some of these principles. Uh this first example for security triage is actually something that we've implemented internally at Sourcegraph. We have tons of these little workflows set up to help us maintain our codebase and make it more autonomous.

Um our security team built this sort of workflow organically really a while ago. Um we've been using HackerOne for a while now, even pre-ChatGPT. Uh but the volume of the reports that our security team has been receiving has been skyrocketing, frankly. Uh and they require real-time judgment to review, digest, and decide, like, is this something that the team actually needs to spend much time on? Uh so they set up uh from HackerOne webhooks that reach out to our agentic searching capabilities, and then make judgments on whether or not our team needs to dive deeper in it, maybe propose a change or remediation, if it just needs to be reviewed more deeply by our security team, or if it's something that we can ignore completely.
</details>

**案例二：超大规模企业的自动化根因分析智能体**。该客户拥有超过 5000 名研发人员。他们希望借助 Sourcegraph 的代码理解能力来实现部分事件响应的自动化。

实现方案如下：当系统记录到服务宕机或错误率突增时，他们在内部构建的根因分析智能体便会自动启动，收集所有相关的日志和链路追踪信息，并将其关联回引发故障的源头。

首先，它必须确认生产环境中实际部署的是哪个分支或 Tag（通常并不是 main 分支）；然后，对 Git 提交历史进行智能体搜索，精确定位触发故障的 commit 和作者。接下来，智能体有权限直接执行 revert 并触发重新部署，或者仅完成分流并将排查上下文共享给 SRE 团队。

<details>
<summary>Original English</summary>
Another example from one of our customers. Um this customer has over 5,000 developers within their enterprise. Uh and they wanted to leverage some of Sourcegraph's code understanding capabilities to automate some of their incident response.

Um how they did that when there's a service record downtime or significant spike in their error rates, the internal root cause analysis agent that they've built within their organization automatically spins up, takes all the logs and traces, and connects those back to the source of the fault. First, you have to identify what branch or tag was deployed in production because it's rarely main, of course. And then using a agentic search over the Git history to find the specific commit and author that triggered the incident. The agent then has the ability to revert and kick off a redeployment or simply triage and share the investigation with the SRE team SRE team.
</details>

**案例三：单体大仓库（Monorepo）中的代码审查智能体**。这家客户在内部维护了自己的代码审查智能体，供公司内数千名工程师使用。该智能体针对其特定的代码库和技术规范进行了定制开发。面对极其庞大的 monorepo，在引入 Sourcegraph 之前，他们每次审查基本上只能依赖 grep。

他们的评估测试集涵盖了该代码库历史上数百个分支。因此，他们的审查智能体需要具备以低成本、大规模且即时检索所有这些分支的能力，同时避免某些其他智能体工具存在的非确定性问题。他们采用我们提供的只读代码检索智能体（read-only code finder agent）实现了这一点。当评估通过后，系统便会触发后续的推送和发布流程。

总而言之，如果您或您的 SRE 团队、平台团队正承受着由 AI 生成代码导致的故障激增之重，或者缺乏清晰高效的手段来调查这些事故根因并制定快速的修复方案，又或者团队正在为智能体工具寻找更完善的代码理解平台和上下文引擎，欢迎到我们的展位与我们交流。感谢大家！

<details>
<summary>Original English</summary>
Last example I have, um this is another customer that had a really great internal use case. Um they maintain their own internal code review agent. It's used by thousands of their own developers, as well. Um and they custom built it to be unique and applicable to their specific code base and specifications. Uh in this case, a massive mono repo that more often than not, pre-Sourcegraph, they were having to just grep every time.

Um their eval suite is made up of hundreds of historical branches of that code base. And so their agents needed the ability to search across all of those branches um instantly, affordably, at scale without relying on the non-determinism of some of the the other agentic tools available to them. Um so they used our read-only code finder agent to make that possible. And when the evals pass, they push and publish processes are are are kicked off.

Yeah, so all in all, um if you or your SRE team or if you your SRE teams, your platform teams are really starting to see a lot of the burdens of incidents and the rise of incidents caused by AI-generated code, um if your teams don't really have a clear way and effective way for investigating uh what caused those incidents and then coming up with a very quick remediation plan to address the increasing volume of those incidents within your code base or really if your SREs, platform teams, software engineers uh are looking for better improved uh context engine code understanding platform that they use or they would like to use with all of their agentic tooling please feel free to come talk to us at our booth.

Thanks, y'all.
</details>