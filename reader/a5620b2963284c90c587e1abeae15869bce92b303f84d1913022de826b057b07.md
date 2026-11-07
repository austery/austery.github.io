---
author: AI Engineer
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=V2UqEUA8NjM
speaker: AI Engineer
tags:
  - ai-agent
  - autonomous-agent
  - financial-regulation
  - authorization
  - software-architecture
title: Wise：别让客户成为 AI Agent 的审批 API
summary: Wise 数据与 AI 产品负责人 Emil Chetty 探讨了如何在受监管的金融支付场景中赋予 AI Agent 自主权。针对传统交互中用户需频繁点击审批每一步骤（将人异化为 API）的痛点，Wise 提出了“意图转化为不可变协议”的架构：用户仅对完整任务目标及边界进行一次性不可变确认，Agent 自主规划与执行步骤，下游可靠服务体系负责强校验与执行，从而在保障合规与资金安全的前提下大幅降低用户复杂度。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Emil Chetty
companies_orgs:
  - Wise
  - Anthropic
products_models: []
media_books: []
status: evergreen
---
### 摆脱“审批队列”：AI Agent 的交互困境

[音乐]

在座的各位，有谁曾对给自己的代码 Agent 不断点“审批”感到厌烦？比如授权 ChatGPT 去抓取那个网站，或者允许 Hermes 读取那个你明明已经告诉过它“完全可以读取”的 MCP？现场有人觉得烦躁吗？

<details>
<summary>Original English</summary>
[music]

>> Anyone here ever get tired of clicking approve on their coding agents, giving ChatGPT the permission to be able to scrape that websites, or even just giving Hermes the ability to be able to read your the MCP that you definitely told it it's a lot to read?

Anyone in the room get annoyed?
</details>

确实如此。现在设想一下，每当你使用一个承诺为你节省时间、降低生活复杂度、并最终为你创造价值的助手时，如果体验全都是这样会怎样。在座的各位——全世界的 AI 布道者们，我们向坐在房间外的普通大众承诺了一个能减轻他们生活复杂度的助手。但当它落地现实时，我们最终给他们的却只是一堆需要审批的请求队列。

<details>
<summary>Original English</summary>
Sure. Now imagine that was the experience every time you were using an assistant that promised you to save you time, reduce the complexity in your life, and ultimately provide you value. Everyone in this room, the AI evangelists of the world, we promised our normies are sitting outside this room the an assistant, something that's going to reduce the complexity of their lives. But instead, when it hit reality, we ended up providing them with a queue of requests.
</details>

### Wise 的合规与规模挑战

大家好，我是 Emil，在 Wise 负责数据与 AI 产品。今天我想和大家聊聊，我们如何思考为用户消除这种复杂度，并尝试在不把客户变成“人类 API”的前提下，赋予 Agent 真正有用的自主性。

<details>
<summary>Original English</summary>
So, hi. I'm Emil. Um I lead um data and AI product at Wise. And I'm going to be talking you guys through about how we're thinking about removing that complexity for our users, and trying to give an agent useful autonomy without making our customer the API.
</details>

对于不太熟悉 Wise 的朋友（鉴于大部分观众来自美国，我猜有些人可能确实不太熟悉），我们是一家致力于打造全球最佳资金流转与管理方式的科技公司。我们的愿景是实现“无国界资金（money without borders）”，确保人们能够跨多个地域和币种管理他们的资金和生活。

<details>
<summary>Original English</summary>
So, for those of you who aren't familiar with Wise, um which I suspect some of you might not be given the US-based audience, um we're a technology company that's building the best way to be able to move and manage the world's money. We have this vision of achieving money without borders, and making sure that people can manage their funds and lifestyle across multiple geographies and currencies.
</details>

为此，我们构建了三款产品：第一款是 Wise 个人账户，帮助普通人打理跨国生活，像本地人一样消费与储蓄；第二款是 Wise Business，让中小企业从创立第一天起就具备全球化能力；最后一款是 Wise Platform，允许银行和其他金融机构直接接入我们自 2011 年以来构建的支付基础设施，直接为其客户提供类似 Wise 的体验。

<details>
<summary>Original English</summary>
To do that, we've built three products. We've built the Wise account, and that's [snorts] helping regular people manage their life across borders, helping them spend like a local, and save like a local. The second is Wise Business, which allows businesses, small and medium-sized, to be global from day one. And the last is Wise Platform, which allows banks and other financial institutions to tap directly into the payments infrastructure that we've built over the last since 2011, and provide a Wise-like experience directly to their customers.
</details>

为了实现这一点，我们建立了一个单一的全球支付网络，由全球 90 多家不同的本地银行和支付提供商支持，并直接接入各国的本地支付清算系统。这一网络已被证明非常高效。去年，我们处理了超过 2430 亿的跨境交易量，服务着近 1900 万活跃客户。因此，我们知道这个模式是可以规模化扩展的。

<details>
<summary>Original English</summary>
And to do this, we've built one single global payments network powered by over 90 different local banks and payment providers from across the world, and connecting directly into domestic payment schemes. And that network has proved really effective. Last year, we've moved over 243 billion in cross-border in cross-border volume, and we're serving over just nearly 19 million active customers. So, we know this this model scales.
</details>

为了做到这一点，我们在全球持有超过 80 张不同的牌照。这意味着不同的货币、不同的国家、不同的监管实体以及不同的产品，都会带来不同的合规要求。不幸的是，当我们把一个聊天机器人放在前端时，这些要求并不会凭空消失。我们的监管机构仍然期望我们明确知晓客户授权了什么、严格掌控其资金的流向，并能对最终结果进行解释。那么，我们怎样才能赋予 Agent 既能切实简化用户生活、又依然能对其行为承担责任的有益自主权呢？

<details>
<summary>Original English</summary>
And to be able to do that, we hold more than 80 different licenses worldwide. And that has meant that in different currencies, different countries, different regulated entities, and different products all bring different requirements. And that doesn't disappear when we put a chatbot in front of it, unfortunately. Our regulators still expect us to know what a customer is authorized, control what happens to their money, and explain the outcome. So, how can we give an agent useful autonomy that is actually going to simplify our users' life, and still answer for what it does?
</details>

### 从“监控终端”到代码 Agent 的演进

先来看一个我们可能交给 Agent 处理的典型任务。比如某位小微企业主可能会说：“处理本周已批准的供应商付款，对账结果，并把异常情况汇报给我。”企业只想要工作被妥善处理。他们不想去协调每一次信息查询，不想去协调每一次状态检查。他们希望这最终能让他们专注于对自己最重要的事情——经营自己的业务。那么，我们该如何去实现这一点呢？

<details>
<summary>Original English</summary>
So, here's what a typical job might look like that we might give to an agent. So, some small business owner might say, "Handle this week's approved payment suppliers, reconcile the results, and bring back the exceptions to me." The business wants the work handled. They don't want to coordinate every lookup. They don't want to coordinate every status check. And they want this to ultimately provide them with the ability to focus on what matters most to them, running their business. So, how do we So, how are we going to about achieving How are we going about achieving this?
</details>

如果大家最近使用过 Agent，对这种场景应该非常熟悉。你会看到一长串不同的待批准步骤：检查你是否可以查询支付账户详情、检查你是否可以扫描 PDF 来理解发票等等。为了完成一件微不足道的小事，居然要经历八个步骤，中间可能还要等待很久。

<details>
<summary>Original English</summary>
This might look very familiar to you if anyone's using agent relatively recently. You will have list of different approved steps. Checking whether or not you are can look up there the payment account details, checking whether or not you can scan a PDF in to be able to understand the the invoice, etc. etc. Took eight steps, probably some time in between to be able to get to something that was ultimately small.
</details>

在座的工程师们对此应该感触颇深。如果有人还记得早期的状态——在你还没用上“危险跳过权限确认（dangerously skip permissions）”的时代——代码 Agent 以前就是这副模样：我们必须守在终端前一步步点击批准，运行测试需要确认，从 Confluence 获取那些基础文档需要确认，全程一直在点批准。我们最终沦为了盯着终端看的人，而不是让实际工作被自动化搞定。

<details>
<summary>Original English</summary>
And so for the engineers in the room, this might look relatively familiar, right? In the If anyone can remember the before times and if you weren't using dangerously skip permissions, this is what coding agents used to look like. We have to go through and approve every step while watching the terminal, check your run your tests, sure, fetch that face first lady documentation from Confluence, sure, and click approve all the way through. We ended up having to watch the terminal instead of getting real work handled.
</details>

>> [嗤笑]

>> 我们最终把人类变成了 API。

<details>
<summary>Original English</summary>
>> [snorts]

>> We ultimately made the human the API.
</details>

### 支付授权的本质与代码安全的不同

那么，代码 Agent 是如何解决这个问题的呢？Anthropic 提出了 Auto Mode（自动模式）的概念，对吧？这切实减少了我们作为工程师所承受的摩擦。权限规则、分类器、沙箱机制，帮助引入了必要的控制手段，使我们能够信任 Agent 不会去随意删除生产数据库。这些控制措施非常重要。

<details>
<summary>Original English</summary>
So how did co-coding agents solve this? Anthropic came up with this idea of auto mode, right? And that meaningfully reduced the friction that we experience as engineers. Permission rules, classifiers, sandbox helped be able to introduce controls necessary for us to be able to trust the agent wasn't going to go delete our production databases. These controls matter.
</details>

但支付业务面临的是不同性质的问题，需要一种完全不同的解决方案。代码 Agent 问的是：“这个操作看起来安全吗？”而支付场景问的则是：“这位客户是否授权了以这些特定条件向该收款人支付这笔款项？”

<details>
<summary>Original English</summary>
But a payment needs a different kind of answer to a different kind of question. Well, a coding agent is asking, "Does this action look safe?" What a payment is asking is, "Did this customer authorize this payment to this recipient on these terms?"
</details>

既然这是一场 AI 大会，有人可能会说：“太酷了，那我们给它堆一些评测（evals）吧。”走在最前沿的朋友可能会说，我们可以构建一个 Harness 测试框架，并将控制逻辑嵌入其中。但不幸的是，这无法回答“客户是否真正同意了这项任务”。我们需要的是一份**协议（agreement）**。我们需要客户确认同意某种不可变（immutable）的凭据，允许 Agent 在这些明确界定的边界内开展运作。

<details>
<summary>Original English</summary>
So again, we're at an AI conference. You might say, "Cool. Let's Let's chuck some eval's at it." For those of you who are on the bleeding edge, let's say we can build a harness to be able to do this and embed the controls inside the harness. But unfortunately, it doesn't give us the answer to whether or not the customer actually agreed to this job. What we need is an agreement. We need something immutable that a customer has agreed to that allows the agent to operate from within those bounds.
</details>

我并不是说我们不需要 evals，也不是说不需要 Harness，这两者我们依然不可或缺。但我们绝不能接受由模型单方面宣称“这就是客户想要的”，并据此去执行支付授权。我们希望客户批准的是整项**任务（job）**，而不是当中的每一个细碎步骤。

<details>
<summary>Original English</summary>
I'm not saying we don't need the emails, we don't need the harness, we're still going to need both. But what we don't want is that the model said this is what the customer wanted and authorizing that payment based on that. We want them to agree to the job, not every step.
</details>

### 从意图到不可变协议

那么，我们具体是如何构思这一方案的？核心思路在于：我们要实现从“用户意图”到“不可变载体”的转化。具体流程是：获取客户给出的模糊 Prompt 并进行解析；利用我们过去 25 年构建的受信、已验证软件进行校验；向客户展示一个确切的结果预期，并由客户确认这是否就是他们希望 Agent 运作的范围边界。

<details>
<summary>Original English</summary>
So, how we how are we thinking about this? So, the idea is we want to be able to go from intent to something that is immutable. So, we want something to be able to take that take the vague customer a prompt that we have, ingest that, have trusted verified software that we've built that we spent the last 25 years building, verify it, and show the customer a particular outcome, and have them confirm whether or not that is the bounds by which they want the agent to be able to operate within.
</details>

随后，我们可以将该确认嵌入到受信技术栈中，依据客户认可的范围为 Agent 分配权限。Agent 便可以像往常一样进行规划和行动。真正执行该笔支付的底层服务会校验这笔支付是否符合执行条件，并将最终结果和异常情况反馈给用户。如果发生变更且该变更触及了根本协议，我们会将其重新呈报给用户；但如果某些变更并未影响支付条款，我们依然可以让 Agent 在既定框架内重新规划。

<details>
<summary>Original English</summary>
We can then take that, embed that into our trusted the our trusted stack, and provision the authority based on what the customer agreed to. The agent can then plan and act as usual. Our services, which are actually executing that payment, can then check whether or not the the payment should be executed on. And the results and exceptions can get surfaced back to the user. If something needs to change, and that changes that fundamental agreement, we surface back to the user. But if the if something is changing that's not going to affect the payment terms, we can still go back and have the agent re-plan.
</details>

也就是说，不同的执行计划依然可以处于同一协议的约束之下；而一旦支付条款发生改变，则必须生成新的修订提案并交由客户决策。简而言之：**客户负责同意任务，Agent 负责选择步骤，而我们的软件体系负责强制执行该协议。**

<details>
<summary>Original English</summary>
So, a different plan can still stay within side that agreement. Different terms ultimately need a revised proposal and a customer decision. So, we need the customer to agree to the job, the agent to choose the steps. And our software to enforce that agreement.
</details>

### 端到端执行案例：小企业主的批量付款

让我们看一个假设的例子。假设之前的企业主 Sarah 向 Agent 发送了这项需求。端到端落地的全貌是怎样的？首先，系统获取 Sarah 的凭据以及各项既有配置，收集拟定任务提案所需的全部上下文。Agent 会在受限的只读权限下，探索闭环业务所需的各类信息。绑定到该账户的受信软件会解析出具体的供应商、银行详情以及对应记录中的金额。在此准备阶段，Agent 实际上未被赋予执行任何实质性操作的权限。

<details>
<summary>Original English</summary>
So, let's take a hypothetical example. Let's say Sarah, our business owner from before, sends this off to an agent. What does this ultimately look like? So, first, we take Sarah's credentials, and we take the the all the setup that Sarah's had, and we go gather the context necessary to be able to propose a job. So, first, the agent explores with limited read-only access all the information necessary to be able to close that loop. The trusted software that we've attached to the account actually resolves the suppliers, the bank details, the amounts from those records. And this preparation doesn't actually give the agent permission to be able to execute anything meaningful.
</details>

接着，我们将方案呈现给 Sarah。她看到的任务草案大致是：这是我们准备执行的事项——向三家供应商付款 775 美元，外加一些可能需要支付的手续费。草案还会明确 Agent 的运作边界，即哪些决策她放心托管给 Agent 处理，哪些决策她希望保留人工审核。任何缺失或冲突的信息，都必须在任务确立为不可变记录之前得到解决。

<details>
<summary>Original English</summary>
We then surface that to Sarah. And here's the job that she'll see. She'll see this is the thing that we want to be able to do. This is like the three suppliers, $775 with around like some for the fees that she might have to pay. And this is the draft that she will see. What also gives What's also important is the balance in which the agent is able to operate in. So, the decisions that she's comfortable offsetting to the agent versus the decisions that she wants to be able to be um looped back into. Any missing or conflicting details need to be resolved before the before before the job gets um made immutable.
</details>

这意味着该任务同时存在两个视图：一个是呈现给 Sarah 的视图，用自然语言表述我们给出的承诺；另一个是底层微服务可见的机器可读承诺，使我们的后端服务能够严格校验该笔支付是否在特定边界内运作，并向 Agent 下发在边界内运作的具体指令。

<details>
<summary>Original English</summary>
And so, what this means is we have two views of that job. One is the thing that Sarah sees, which is the is the promise that we're making in human language. The second is what our services can see. And that's ultimately a machine-readable promise that we're making that allows our services to be able to verify that this payment is a is is operating within a specific set of bounds, and gives the agent very specific instructions in which to operate within those bounds.
</details>

当她点击批准后，该方案便确立为不可变记录。她完成身份确认与鉴权，她的决策会被精确绑定记录到该版本中。这份草案随即转为一份经授权的正式任务。**你批准了什么，我们就严格执行什么。** 这就是我们消除复杂度的思考方式。

<details>
<summary>Original English</summary>
And so, when she clicks approve, that then becomes immutable. She confirms and authenticates, and her decision is recorded against that exact version. And that draft becomes an authorized job. What you approve is ultimately what we enforce. And that's how we're thinking about reducing the complexity.
</details>

### 权限配置与双循环架构

接下来会发生什么？我们拿到这份已确认的任务，交由受信的权限调配平台，严格根据审批内容动态下发访问权限。底层代码以确定性的方式校验三项要素：已确认的任务、Wise 允许 Agent 执行的范围、以及 Sarah 当前拥有的权限。我们提取这三者以及任务提案本身的交集，为执行 Agent 调配受限的访问权限。

<details>
<summary>Original English</summary>
So, what happens next? So, we take that we take that confirmed job, and we give a trusted provisioning platform the ability to be able to provision access purely based on what's been approved. The code deterministically checks three things: the confirmed job, what wise permits the agent to do, and Sarah's current rights. And we look at the intersection between those, as long along with what the job has proposed to be able to provision limited access rights to an execution agent.
</details>

这些权限随后被分发给两个 Worker：支付 Worker 与对账 Worker。它们将基于该任务真正执行后续操作。在此过程中，执行计划依然具备调整空间：Agent 仍然有权自行决定如何最有效地完成被指派的任务；但协议本身是不可更改的。因此，我们承诺的灵活性——让客户能够直接委托任务而非监督具体实现步骤——依然得以保留。

<details>
<summary>Original English</summary>
Those then split out into two workers. One is a payment worker and a reconciliation worker. And those are what is going to be able to actually execute based on that job. This still allows the plan to be able to change. The agent is still deciding how to best achieve the job that has been provisioned to them. What does What doesn't is the agreement. And so, the flexibility that that we promised, the ability for a customer to be able to delegate the job instead of supervising that implementation, still remains.
</details>

架构在本质上分为两个不同的循环，这为系统赋予了相当的容错韧性。举个例子，假设任务出于某种原因需要重试：Kubernetes Pod 发生重启，或者 Sarah 手机上的应用崩溃后需要重新加载该任务。由于任务记录本身不可变，且支付状态在系统中共享，服务在处理二次支付时不仅能执行支付，还能反查历史已执行的状态。因此 Worker 会直接沿用既有的支付任务，而不会重复创建新任务。

<details>
<summary>Original English</summary>
So, there's fundamentally two different loops, and this gives us some element of resilience here, right? So, let's say um the job needs to be retried for whatever reason. A Kubernetes pod needs to be restarted, and then the job or the app crashes on her phone, and she needs to be able to restart that job. Given that that job is immutable, and we're sharing that payment state, it's on a second payment. Services will share the ability to be able to um execute that payment, but also be able to look up what has already been executed. And so, the worker follows the existing payment job rather than creating another one.
</details>

然而，如果系统在后续执行中发现汇率报价发生变动或已过期，则必须重新反馈给 Sarah，因为她知情权至关重要——Sarah 当初批准的是那个特定的报价。此时 Agent 会生成一份更新后的新提案，但它自身无权擅自批准替代方案。我们会向 Sarah 明确展示变更的内容，由她确认同意新版本。在这一机制约束下，Agent 依然可以持续运作。

<details>
<summary>Original English</summary>
However, if they discover that a quote has changed later on, or quote might have expired, service that back to Sarah cuz she wants to know. Sarah approved that specific quote and the agent then will prepare an updated proposal but can't approve the replacement itself. And so we control Sarah what's changed, get her to agree to a new version. And within that arrangement, the agent still keeps working.
</details>

### 防范注入攻击与确定性校验

这是我们在白板上探索出的架构雏形：我们拥有不同的网关，用于权限调配并将不可变任务与底层校验体系进行核对；我们设立了通往 LLM 提供商的高度受控路由；同时还设有一个 Agent 网关，为工具注册和调用证据存证提供机制保障。顺着这笔支付走过网关：Worker 检查其可使用的工具集，在支付服务接口上执行，并确保运行边界始终符合我们对用户的承诺——即那份不可变的任务记录。

<details>
<summary>Original English</summary>
So it's a rough like sketch of what we're trying of what we've done on a white so far is we have like our different gateways that ultimately allow for the provisioning of these agents and also the ability to be able to have that immutable job be it be be verified against our We have the very controlled routes to our LM providers and we have an agent gateway which ultimately provides mechanisms for our tools to be able to be registered but also be evidenced. So we follow that one payment through the gateway. The worker checks what what tools it can use. Executes that against the payment surface. And make sure that the bounds mode they're operating within still comply with the promise we made the user. That immutable job record.
</details>

但假设发生了一些恶意行为呢？比如系统在某个环节遭遇了 Prompt 注入攻击，恶意指令声称“收款账户信息已更新”，甚至假设 Agent 真的信以为真了。然而，Agent 自身的“主观信任”根本无法修改那份已经过确认的任务记录。因此，新的支付请求在下游微服务的强校验阶段就会直接报错失败。Agent 永远无法篡改自身背负的协议。

<details>
<summary>Original English</summary>
But let's say there's some nefarious actions happening, right? So suppo- suppose we get prompt we get it get it gets prompt injected somewhere and the an agent says pay our payment details is updated. And let's actually say that the agent actually believes it, right? It's belief itself can't change the confirmed job. So the new PA fails when the at the service check. And the agent can't rewrite its own agreement.
</details>

由此可见，系统的安全边界并不依赖模型能否识别出诈骗或注入，而是仰赖我们的下游服务体系既能进行合规校验、又能强制执行既定协议。我们自 2011 年以来搭建的这套软件体系，依然是我们最为倚赖的核心底座，也始终是向现场所有监管审计机构证明合规性的关键支撑。

<details>
<summary>Original English</summary>
So the boundary doesn't actually depend on the model spotting the scam. It depends on our downstream services supporting the ability to be able to check those but also enforcing on what we agreed. So the software stack that we built over the last since 2020 since 2011 is still the one that we're going to be relying on and it's still the one that's going to be remaining compliant for all of the orders in the room.
</details>

### 总结：别让人类成为 Agent 的 API

那么，我们究竟能对什么负责？
- 我们清楚知晓是谁授权了这项任务；
- 我们清楚知晓 Agent 有权执行什么；
- 我们清楚知晓支付发生时经历了什么；
- 我们清楚知晓在什么情况下可以强行拦截；
- 我们最终明确知晓谁对此负责；
- 我们也能确切掌握它的执行表现是否良好。

依靠这一条完整的证据链，我们获得了所需的一切支撑：既能让客户在借助 Agent 时降低操作复杂度，又能确保资金安全无虞。

<details>
<summary>Original English</summary>
So, what can we answer for? We know who authorized the job. We know what the agent can do. We know what happened when that payment went through. We know what we can stop. We ultimately know who who is responsible. And we know whether or not it's doing good work. And so, that one chain of evidence, we get everything we need to be able to allow for our customers to be able to reduce the complexity when using agents, but still make sure that that money is safe.
</details>

如果说今天有什么希望大家带走的核心观点，那就是：如果你想在产品中引入全新的审批流，或者想在技术栈中接入新的 Agent，**请让客户对整体任务进行确认授权并进行委托；允许 Agent 自主选择达成该任务的具体执行步骤；同时依靠后端的确定性服务体系来严格强制执行这份协议。**

这样一来，Sarah 就再也不必烦恼要逐一点过上百个繁琐的审批步骤了。所以，请别再把人类当成你家 Agent 的 API 了。谢谢大家！

<details>
<summary>Original English</summary>
So, there's one thing I want you to take away from this. If you want to introduce a new approval flow, if you want to introduce a new agent into your like into your stack, get the customer to agree to the job and delegate it out. Allow your agent to be able to choose how it wants to execute that job. Allow your services to be able to enforce that agreement. And that way, Sarah doesn't have to worry about needing to approve 100 different steps. So, please, stop making your hu- humans your agency API. Thank you.

>> [applause]
</details>