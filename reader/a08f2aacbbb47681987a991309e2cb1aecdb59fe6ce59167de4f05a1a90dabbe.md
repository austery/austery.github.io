---
author: AI Engineer
date: '2026-11-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JxNCuXkSWyQ
speaker: AI Engineer
tags:
  - ai-agent
  - authorization
  - access-control
  - observability
title: 有效凭据不等于合规意图：AI Agent 行为授权与控制平面
summary: Speakeasy 联合创始人 Sagar 结合真实案例阐述 AI Agent 治理风险：Agent 拥有基础设施有效凭据却误删生产数据库，核心漏洞在于缺乏制衡意图与 API 之间的控制层。他提出了涵盖连接、身份、决策和审计记录的四步治理框架，主张通过控制平面在关键路径上结合主体身份、意图评估与日志签名，实现对 Agent 行为的主动授权与风控。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Speakeasy
  - Tailscale
products_models: []
media_books: []
status: evergreen
---
### 引言与背景

大家好，感谢大家今天到来。

我是 Sagar，Speakeasy 的首席执行官兼联合创始人。我们是一个 AI 控制平面，帮助大家在企业内部安全地扩展 AI。这意味着我们帮助将你现有的所有 AI 纳入治理轨道，并对它采取的所有操作进行授权。

<details>
<summary>Original English</summary>
Hey everyone. Thanks for coming today.

My name is Sagar. I'm CEO and co-founder of Speakeasy.

We are an AI control plane that helps you securely scale AI within your business. So what this means is we we help take all the AI you have, put it on a governed path, and help you authorize all the actions it's taking.
</details>

我今天来这里是想和大家谈谈我们如何真正有意识地对 Agent 的操作进行授权。我将重现几个月前新闻报道中的一个小事故，并以此来讨论如何授权操作以防止此类事故发生。在今天，Agent 是否具备完成任务的能力早已不再是疑问。大多数企业真正关注的焦点是：当其中一个 Agent 执行了某种操作时会发生什么？在大多数受监管的行业中，每一项操作都必须归属于某个人或某个事物，归属于某种身份。所以这正是我在这里想讲的核心内容。

<details>
<summary>Original English</summary>
I'm I'm here today to talk to you about how we can actually intentionally authorize agent actions.

I'm going to recreate a little incident that was in the news a couple months ago, use that to talk to kind of the scenario of how you can authorize actions and prevent prevent such an incident. The question of whether agents are capable at a task is long gone today. The real focus in most businesses is what happens when one of them does something. In most regulated industries, every action has to be has to be attributed to someone or something and and some identity. So that's really the the core of what I wanted to talk here.
</details>

### 事故复盘：误删生产数据库

首先让我放一段我制作的简短小动画，回顾一下我提到的那起事故。如果你还记得 4 月份那件事，我就不提名字了，但有一家初创公司的创始人以为自己在修复暂存环境（staging），却意外删除了生产数据库。我准备了这个漏斗动画来帮大家回忆那个故事。

<details>
<summary>Original English</summary>
Let me first do a quick little animation I put together of the incident that I was talking about. If you remember back in April, I won't name names, but there was a startup founder at the startup who thought he was fixing a staging environment but accidentally deleted his production database. I've got this funnel animation to kind of remind you of that story.
</details>

故事的梗概正如我所说：开发者让一个编码 Agent 修复暂存环境中的凭据问题。这是一个相当普通的请求，发生在一个平常的下午。Agent 首先读取工作区，并在一份不相关的文件中找到了一个数据库访问令牌。这是一个拥有完全访问权限的基础设施令牌。它判定修复方法是删除该卷并重新创建它。然而，它有权访问的卷并不是暂存环境，而且在那个猜测和 API 之间没有任何屏障。调用上没有身份，没有策略，没有审批，也根本没有任何记录。

<details>
<summary>Original English</summary>
The summary of the story goes as I said, the developer asks a coding agent to fix a credential issue in staging. This is a pretty ordinary request, ordinary afternoon. The agent starts by reading the workspace and in an unrelated file, it finds a database access token. This is an infrastructure token with full access. It decides the fix is to delete the volume and recreate it. Except the volume it has access to is not staging and nothing is standing between that guess and the API. There's no identity on the call, no policy, no approval and really no record at all.
</details>

于是，一瞬间生产环境就被删除了，包括它的备份，而所有这些都处于同一个网络边界内。因此在一瞬间全都没了。只用了大约 10 秒钟，就彻底毁掉了这家初创公司的整个数据库及其备份。

<details>
<summary>Original English</summary>
So in one fell swoop we've deleted production, it's back up and all of that lived within the same network boundary. So it's all gone in one instant. Took about 10 seconds to kind of completely bring down the startups whole database and and their backup.
</details>

### 有效凭据不等于合规意图

在我们继续进行接下来的演讲时，我想留给大家的思考是：**Agent 拥有有效凭据，但它没有合规的意图。** 这才是这种情况中对与错的真正区别。

<details>
<summary>Original English</summary>
Now what I want to leave you with as we kind of go on to the next part of this presentation is that the agent had valid credentials but it didn't have valid intent. That's the real difference between the kind of right and wrong in the situation.
</details>

因此我想在这里提出的论点是：不受制约的权限才是真正的漏洞所在。Agent 可能会犯错，可能会遗漏上下文。现在大家对此都理解得相当透彻了，你知道，我们以前都遇到过这种情况。但在那种场景中你没有看到的是，不存在漏洞利用，不存在越狱，也不存在提示词注入。根本没有恶意行为者。没有任何人在故意做任何危害系统或危害公司的事情。

<details>
<summary>Original English</summary>
So my argument I'm going to make to you here is that the unchecked authority is the real failure. An agent can be wrong, it can miss context. It's pretty well understood now, you know, we've all been in that situation before. But what you didn't see in that scenario is that there was no exploit, there was no jailbreak, no prompt injection. There was really no malicious actor. There was nothing that anyone was doing intentionally to kind of harm the system or harm the company.
</details>

有效的密钥完成了有效密钥该做的事，对吧？Agent 做了它认为应该做的事。因此，对于受监管的企业来说，失败之处不在于错误发生了，而在于 Agent 及其判断与 API 之间没有任何屏障。也就是说，根本没有真正的防护护栏到位。

<details>
<summary>Original English</summary>
The valid key did exactly what valid keys do, right? The agent did what it thought it should do. So the failure for regulated business is that not not that the mistake happened but nothing stood between the agent and its judgment and the API. So there were no real guardrails in place.
</details>

### 现状数据与传统治理标准

在我们深入探讨如何在此处做得更好的蓝图之前，我想向大家展示代表我们行业现状的三个数据：
- 第一，82% 的组织已经在运行 AI Agent，这对任何人来说可能都不足为奇。
- 第二，32% 的组织制定了现成的 AI 治理策略。鉴于两者之间的差距，这个数据可能更令人意外。
- 最后，当由于某种 Shadow AI 而确实发生数据泄露时，平均损失通常经计算约为 500 万美元左右。

所以，这是一组耐人寻味的数据。但本质上我们可以得出结论：AI 的普及是普遍的，但控制层并不真正存在，且绝对没有普及。

<details>
<summary>Original English</summary>
Before we get into kind of the blueprint of how we can do better here, I wanted to give you three numbers that represent how this is playing out in our industry.

The first 82% of all organizations already run AI agents, no surprise probably to anyone. 32% had an AI governance policy in place. So probably more surprising given the difference between the two. Um and then finally, when a breach does happen, thanks to Shadow AI of some kind, uh the average cost is usually calculated to be about $5 million or so. So, that that that's a fun stat. Um but essentially, we can conclude that um air adoption is universal, but the control layer doesn't really exist and it's definitely not universal.
</details>

在我们去探讨这种情况下的 Agent 控制层可以是什么样之前，实际上让我们先从我们一直以来对员工的要求谈起。自从有软件或任何形式的 SaaS 软件以来，我们就一直让人们遵守这种标准。

我们要求人们遵守的原则是：
- 你必须以自己的身份登录；
- 我们要求所有人不得共享密码或任何形式的密钥；
- 你不能批准自己的提权或修改权限；
- 我们期望系统能跟踪所有变更。

这相当标准，对吧？这就是当今所有的软件体系，这就是我们的预期。如果你在受监管的行业接受审计，被问到的问题不会是：模型是否足够聪明？你的 Agent 是否足够智能或使用了最新版本？而只会是：谁执行了操作、谁允许了它，然后出示所发生事情的记录。

<details>
<summary>Original English</summary>
Um before we go to looking at what a control layer for agents could be in the scenario, um what let's actually just start at what we've asked people our employees to do uh for as long as we've known. We've held people to this kind of standard as long as there's been software or you know, SaaS software of any kind.

Um the the things that we hold people to are you have to sign in as yourself. Uh we ask nobody we ask everyone to you know, not share passwords or keys of any kind uh and you can't approve your own escalation or changing permissions. And we expect systems to keep track of all changes. That's pretty standard, right? That's all software today. That's what we expect. Um the question uh if you're being audited in a regulated industry, the question that will be asked is, you know, not is the model smart enough is your agent smart enough or using the latest release, but it'll just be who acted, who allowed it, and then show me the record of what happened.
</details>

### 构建治理路径：开箱即用的控制层

因此，如果要将这一点应用到 Agent 身上，我要说的第一点是我们不想阻止 Agent，对吧？我们不想制造一种阻碍，以致团队会想方设法绕过它。Agent 也会绕道而行。我们知道封堵并不真正奏效。解决办法是打造一条具有实质意义且比未经治理的路径更容易走的行动路径。因此，我们希望受治理的操作实际上比不受治理的操作更轻松。

<details>
<summary>Original English</summary>
So, if we're going to apply this to agents, the first thing I'll say is we don't want to stop agents, right? We don't want to uh create a block that teams are going to find a way to route around. Agents will work around. We know that blocks don't really work. Uh the answer is creating a path to action that is meaningful and uh much easier than the ungoverned one. So, we want the governed action to actually be easier than the ungoverned action.
</details>

让我通过另一个有趣的动画向大家展示，对于一个真正受治理的操作，端到端的路径会是什么样子。

设想你拥有一个真正的控制层，某种在你机器上和云端治理 Agent 的神奇系统。你真正关心的第一件事是它能够开箱即用。因此，你加入公司、完成入职培训，并且希望所有这些策略都已准备就绪。在这个动画的第一步中，我们展示了它是开箱即用的，在你入职第一天就安装在你的笔记本电脑上。

关于什么应该发生或不应该发生的策略是在中央统一编写一次。这不是开发者需要在其 Agent 或自己的 harness 上编写的内容；它只需编写一次，现在就可以在公司层面强制执行。

<details>
<summary>Original English</summary>
Um let me show you with another fun animation what that path end to end could look like for a truly governed action.

So, imagine you had a true control layer, you know, a magical system of some kind that governed agents on your machine and in the cloud. Um the first thing that you really care about is that it works just out of the box. So, you join the company, you onboard, and you want all of these policies in place. Um so, in this kind of first step of the animation, we're we're showing that it's something that comes out of the box installed on your laptop the first day you start at this company.

Um the policy of what should happen or not happen is written once centrally. Uh it's not something a developer needs to write on their agent or their own harness. Uh it's written once and now kind of enforced at the at the company level.
</details>

以这个为例，我们来想一个简单的场景：针对用户提示词和工具请求中的机密信息（secrets）。我们想要的操作是阻断（block）或隔离（quarantine）。

我们再次采用之前相同的场景，即开发者意外删除数据库的情况。在这种情况下，用户输入了一个 AWS 密钥，或者它甚至可能来自另一个 Agent。在模型看到它之前，hook 就触发了，而且这完全发生在 harness 运行时内部。因此它检测到正在发送一个密钥，并且提示词被控制层评估的策略捕获。策略由检测器执行，其中一个检测器匹配到了 AWS 密钥。

<details>
<summary>Original English</summary>
Uh for this one, let's think of a simple one. We'll go with secrets on user prompts and tool requests. And the action that we want is block or a quarantine.

Um we'll take the same scenario again um of kind of what we did earlier, uh you know, from the developer accidentally deleting the database. Uh in this case, um the user's putting in AWS key in. Um or it might even be coming from another agent. Before the model ever sees it, a hook fires, and um this happens all in the harness runtime. So, it detects that there's a key that's being sent, um and the prompt is caught by a policy that's evaluated by the control layer. Uh the policy is enforced by a detector, and one of them matches the AWS key.
</details>

因此这里发生了拦截的概念。随着拦截的发生，也生成了一个决策。所有这一切的发生，理想情况下我们希望在 100 毫秒或更短时间内完成。我们不希望 Agent 或人类真正改变他们所处的执行路径。所以它发生得非常迅速。最后，一旦发生拦截，就会被记录下来，现在对发生的那起事件就有了审计。因此，经过检查、阻断并记录，机密实际上从未离开过机器，在这种情况下，开发者除了一个错误的提示词之外什么都没有损失。

<details>
<summary>Original English</summary>
So, there's there is a concept of like an interception that happens, um and then as that happens, there's also a decision that's created. And all of that happens in, you know, ideally we want it to be like 100 milliseconds or less. We want We don't want the agent or the human to really change the the path that they're on. Um so, it happens very quickly. And then finally, um you know, once the interception happens, that's logged, and now there's an audit of that event that's happened. So, inspected, blocked, and logged, the secret never really left the machine, and in this case the developer lost nothing but just a bad prompt.
</details>

### 企业治理架构的四个步骤

让我们从概念上将其简化为所发生的过程。我们可以将其视为企业构建治理架构所围绕的四个步骤：

1. **连接（Connect）**：这是创建一个统一的入口，而不是拥有几十个不同的集成点。Agent 在连接到外部系统时进行的所有调用都应该汇集到一个地方，比如 MCP 网关。我们很多人都使用过并对它们非常了解。
2. **身份（Identity）**：调用需要解析到具名的 Agent 或其背后的自然人。没有身份，策略评估就无法真正开展。这必须与所有企业软件分配的身份一致，以便在整个组织中保持连贯。
3. **决策（Decide）**：在此步骤中你可以允许（allow）、拒绝（deny）、隔离（quarantine）或升级（escalate）决策。有时仅仅提醒用户就足够了。
4. **记录（Record）**：在实际采取任何行动之前，该决策被记录下来。

<details>
<summary>Original English</summary>
Um let's simplify this kind of conceptually into what's happened. Um we will look at this as four steps that a company can model a governance architecture around.

Uh the first I like to call connect. Um this is creating a one creating a door instead of, [snorts] you know, having dozens of different integration points. All of the calls that an agent does when it connects to external systems should go to one place, something like an MCB gateway. A lot of us have used those and understand those well.

Um the second is that the calls need to be resolved to a named agent or a human behind it. Um policy evaluation doesn't really work without identity. Um this has to be the same identity all of the enterprise software is assigned to as well, so it's consistent across your organization.

Um Third, there's a decide step where you either allow, deny, quarantine, or you escalate the decision. Um and then sometimes even just warning a user is sufficient. And then finally that decision is recorded um before, you know, any action is actually taken.
</details>

我们来深入探讨其中的几个环节，以便为你在自己的产品或公司中实现该方案提供更好的蓝图。

第一个是**身份**：谁参与了调用，谁实际执行了该请求？如果我们看眼前的这个屏幕，它包含两个部分。左边是我们提出的那起事故，那是来自事故的日志。在文件中找到了一个密钥，但没有操作者，也没有任何人批准它。所以如果你作为审计人员来看，你会纳闷到底是谁采取了行动，谁该负责。

坦白说，这是当今大多数系统的默认状态。甚至在今年早些时候我们自己也是这样。每一个主体、每一个 Agent、每一个用户，全都是借用个人的身份。这在当今运行 Agent 的大多数公司中相当普遍。即使是后台作业也会映射到一个用户，或者只是创建一个匿名的系统角色。即使是 Slack 助手也往往以类似用户权限运行，它们不一定拥有自己的身份。

<details>
<summary>Original English</summary>
Um we're going to dive into couple of these in a little bit more detail so I can give you a better blueprint of how to do this uh for your own product or your own company. The first is uh identity. So, who was on the call, who actually executed uh this request? Um if we look at this uh kind of screen in front of us, there are two sides to it. The left side is the incident that we posed. That's the log from the incident. A key was found on the file, but no, there's no actor and there's nobody who approved it. Uh so, if you're looking at this as, you know, uh an auditor, you're wondering who actually took the action, who's responsible.

Um these And to be honest, this is the default state of most systems today. Um it was even ours you know, until earlier this year. Every principal, every agent, every user, um it's all borrowed based on a person's identity. This is pretty common in most companies today running agents. Even a background job is mapped to a user or there's just a anonymous kind of system role that's created. Even Slack assistants or tend to be running as like user permissions. They don't necessarily have their own identity.
</details>

右边则是通过控制平面的视角重新建模的同一个提示词。Agent 本身就是一个主体（principal），因此它拥有自己的独立身份。在它下方，你可以看到有一位驱动该操作的操作员（operator），即当时实时与该 Agent 交互的人，在本例中是我。这被记录下来用于归因，绝不会用于实时扩大访问权限。最后是授权人（authorizer），即批准 Agent 最初凭据配置的人，在示例中显示为我们的首席信息安全官（CISO）Thomas。这在凭据生命周期内是固定的。所以右侧的卡片正是我们在合规方面真正想要的，这是对实际发生情况的真实记录，也是我们对其进行建模的方式。

<details>
<summary>Original English</summary>
On the right is that same prompt now modeled to the lens of a control layer. The agent is a principal in its own right, so it has its own identity. Below that you see there is an an operator who drove the action. So who is actually interacting with that with that agent in real time. In this case it's me. Um and that's recorded for attribution. It's never used to like widen access in real time. And then finally there's the authorizer. So this is the human who approved the original credential setup for the agent. In this case it says Thomas who's our CISO. This is fixed for credentials lifetime. So the right hand card is what we really want for compliance. This is a true log of what actually happened and how we could model it.
</details>

### 实时决策模型与策略求交

接下来的内容适合听众中的集合论爱好者，它是关于你如何在实时环境下判定调用是成功还是失败。这包含三个部分：
- **左侧是凭据（Credentials）**：这是人类在签发密钥时设定的上限。同样，这是永远不会被扩大的范围。它存在于凭据中，是你无法逾越的上限。
- **第二部分我们称之为 A（Agent's Policy）**：即 Agent 自身的策略。它不能拥有管理员权限或任何仅限人类的操作范围。
- **最后 O 是拥有者的实时策略（Owner's Live Policy）**：Agent 所能做的事情永远不能超出对其负责、实际驱动该 Agent 的人。在我们的例子中那个人就是我。

以这种方式建模的有趣之处在于，A 和 O 会在每次调用时被读取。如果你移除了某项权限，它在下一次请求中就会失效，因为它会被重新评估。

<details>
<summary>Original English</summary>
Um the next one is for kind of the set theory nerds in the audience, but it's how you actually decide in real time whether the call succeeds or fails. Um let's the kind of three parts to this. The first is the one on the left. Our credentials. This is the ceiling of what a human put down when they issued the key. So this again is the thing that never gets widened. It lives in the credential and it's something you can't escalate past. The second is we call it A. It's the agent's own policy. It can't hold an admin privilege or any or any kind of human only scope. And then finally O is the owner's live policy. So an agent can never do more than the person accountable for it who who's actually driving the agent. So in this case it was me.

Um what's interesting about modeling it this way is that you know, the second and third A and O are read on every call. If you remove a permission, um, it's gone on the next request. So, it's re-evaluated.
</details>

如果回到我们最初的数据库场景：即使拥有者有权删除生产数据库，一个权限仅限于暂存环境的 Agent 也做不到；如果有人给了该 Agent 更宽泛的策略，它的权限也不能超过一个从未拥有生产权限的拥有者。因此在两个方向上你都受到了保护，无论哪种情况调用都会被终止。最后还有一个重要说明，如果拥有者从公司离职，由于它与你的企业身份系统相连，你的 IDP 会注销他们，此后该 Agent 发出的每一个请求都会被拒绝。

<details>
<summary>Original English</summary>
Um, and if we go back to that database scenario that we started with, even if the owner could delete production, an agent scoped to just staging can't. And if someone gave the agent a broader policy, it can't exceed an owner who never had production rights. So, in kind of both directions, you're protected. Um, either way the call would stop. Uh, and then finally, an important note, you know, if an if an owner would leave a company, um, since it's connected with your enterprise identity, your IDP de-provisions them, and every request that agents make is now denied going forward.
</details>

### 审计记录与 Speakeasy 架构实践

概念流程中的最后一步是记录实际发生的事情。左侧再次展现了那个场景的发展过程；右侧是它实际留下的痕迹，因为我们现在有办法对发生的步骤进行建模。我们可以看到在这个流程中，随着经历不同的步骤，发生了一个拒绝步骤。并且存在一个声明的意图（stated intent），即 Agent 想要在暂存环境上执行操作，但实际操作却作用于生产环境。策略能同时看到这两方面。

这就是当今合规框架普遍达成的共识：每一个非只读操作都会根据策略进行评估，该策略不仅考虑实际发生的操作，还会考量 Agent 声明的意图。在大多数控制系统中，评估结果恰好属于五种决策之一，正如我们前面提到的：允许、拒绝、修改或升级给人工处理。每个经过评估的操作都会生成此类发生事件的记录，而且在很多系统中，它通常会在密码学上与 Agent 身份进行绑定。

<details>
<summary>Original English</summary>
Uh, the last step in that conceptual flow is is recording what actually happened. Um, so, on the left is again that scenario playing out. Um, on the right is what it actually leaves behind, now that we have a way to kind of model the steps that have happened. Uh, we can see kind of in this flow, as you go through the different steps, there's a denial step that happens, uh, and there's a stated intent, which was that, uh, the agent wanted to act on staging, but the action was done on production. Um, the policy sees both sides of that. So, this is where compliance frameworks have generally landed today. Um, every non-read action is evaluated against policy uh, that considers the agent's stated intent, uh, not just the action that actually happened. Um, in most control systems, there's exactly one of kind of five decisions that comes out of this, uh, like we mentioned earlier, it's either allowing, denying, modifying, or escalating up to a human.

Um, every evaluated action produces this kind of record of what's happened, and then in generally, in a lot of systems, it's cryptographically bound to the agent identity.
</details>

我只准备了一张幻灯片来向大家展示我们在 Speakeasy 是如何构建这个系统的，所以我会简要介绍。

正如我之前提到的，我们 Speakeasy 是一个 AI 控制平面。我们实际上将我们的产品放置在人们使用的或自主运行的 Agent 与它们所访问的系统之间。身份基准来自你的 IDP（例如 Okta 或其他身份提供商），而操作策略实际上是在我们的产品或控制平面上进行评估的。因此每一次调用——包括被我们拒绝的调用——都会经过我们，从而由我们为客户写出审计日志。

这种架构中有三个关键决策：
1. **处于关键路径之上而非其旁路**：记录必须反映实际发生的事情，而不是 Agent 自行汇报的内容。
2. **采用一等公民身份（first-class identity）**：而不是在所有系统中普遍使用用户登录凭据。
3. **通过 MDM 进行分发**：所有这些都是开箱即用的。用户无需在自己端重新定义这些策略，在他们入职公司或开始使用 Agent 的那一刻，它就能直接生效。

关于 Speakeasy 的内容就这一张幻灯片，稍后我很乐意与大家深入交流。

<details>
<summary>Original English</summary>
So, I have only one slide that's going to actually take you through how we built this at Speakeasy. So, I'll keep it limited to that. Um, as I mentioned earlier, we we Speakeasy were an AI control plane. Uh, we actually put our product in between agents uh, that people use or using autonomously, and the systems that they have access to. Um so the identity comes the identity baseline comes from your IDP. Uh so Okta or another identity provider. Uh and then the policies of action is actually evaluated on our product or our control plane. So every call um includes the ones including the ones that we deny all go through us. And so we write out the audit log for for our customers.

There's kind of three kind of critical decisions in this architecture. Uh the first as you can see is that we sit in the critical path not beside it. Uh the record has to be of what actually happened. Uh not what the agent reported and two we use kind of first class identity uh instead of using user logins everywhere to the system. And then finally we'd actually distribute to MDM. Uh so all of this comes working out of the box. For a user they don't have to go redefine these policies on their end. It's something that just works the moment they start uh at the company or start using an agent.

So that's my only slide about Speakeasy but I'm happy to talk to you more about that later.
</details>

### 总结与问答环节

为了总结我们所讲的内容：在受监管行业中，执行操作的许可通常意味着针对每一个 Agent 或采取的每一项 Agent 操作，必须证明三件事：
- 操作者是谁；
- 哪些策略允许了该操作；
- 记录的签名，即确切知晓该操作确实发生了。

这正是我们在企业中一直要求员工做到的，也是我们现在要求 Agent 做到的。**有效凭据不代表合规意图**，这一点至关重要，请牢记。解决之道不是宣称我们拥有更聪明的模型或更好的 Agent，而是真正将所发生的每一项操作的身份、策略和记录整合在一起。

这就是我今天想和大家分享的所有内容。另外我想提一下，今晚我们将与 Tailscale 的朋友们在这里联合举办一场活动，推出一项关于将 MCP 网关部署在专用网络上的合作。如果大家在场，欢迎加入我们。好的，现在很乐意回答大家的问题。

>> [掌声]

<details>
<summary>Original English</summary>
Um So that's the to kind of summarize what we went through. Uh in a regulated industry permission to act usually means kind of three things have to be shown for every agent or every agent action that is taken. Um who the actor was, what policies allowed it uh and the signing of the record. So knowing for a fact that this actually happened. Um this is what we've always kind of asked employees to do at a business and it's what we ask agents to do now. Um valid credentials are not valid intent. That's something that's really important to remember and the fix is not you know just saying we have a smarter model or a better agent. Uh it's actually putting together identity policy and record of every action that's that's happening.

So that's uh kind of everything I wanted to talk to you about today. Um I'll also leave you with um we're doing an event tonight with our friends here at Tailscale um launching a partnership around private put taking your MCP gateway and putting it on a private network. Join us if if you're here. And yeah, happy to take questions.

>> [applause]
</details>

>> 请镜头前那位提问。

>> 我有一个问题，假设你正在使用一个受到我们讨论的这种机制治理的 Agent，并且你不同意它拒绝该操作的决定。你会如何设计策略？

>> 是的，这是个好问题。我认为，最重要的一点大概是你要有一种方法能够看到做出了哪些决策。在当今大多数公司中，当人们使用（比方说）来自 Anthropic 的 Claude 并连接到所有系统时，当它访问这些系统时，实际上并没有记录下所做的决策。因此，即使你不同意说“嘿，这个用户本不应该访问（比方说）CRM”，你也没法回过头去确切证明这件事已经发生了。

其次，当这种情况发生时，你确实需要一种为用户升级审批的方法，以便你可以实际决定是否希望放行该操作。所以我认为这些属于比较基础但缺失的环节。如果你具备了这些机制，你随时都可以去更新策略以允许该操作发生。请继续提问。

<details>
<summary>Original English</summary>
>> Go ahead, camera.

>> I had one question on say you're using an agent that is being governed by the ethics of the planet we're talking about and disagree with the decision that it came to to deny that that action. What would you How would you design a policy?

>> Yeah, that's a that's a good question. I think um the you know, if probably the first most important thing is that you do have a way to see what decisions were taken. So, in most companies today when people are using you know, just let's just say Claude from Anthropic and connected to all the systems, as it's accessing these systems, there's really no record of those decisions taken. And so, even if you disagree that hey, this user shouldn't have been able to access, let's say your CRM, you can't go back and actually say that has happened for sure.

Secondly, you do want a way to escalate your user when that happens so you can actually decide if you want that to be passed or not. So, those I would say they're kind of more fundamental missing pieces. If you have that in place, you can always go update a policy to actually allow that to happen.

Yeah, go ahead.
</details>

>> 在没有策略的 56% 企业中，我很好奇究竟有多少人是因为监管机构强制要求而购买解决方案，又有多少人是因为出了故障？换句话说，是什么推动了预算？

>> 是的，这是个好问题，我们经常思考这个问题。我认为合规确实是促使人们考虑采用解决方案的非常好的驱动力。但我想留给大家的观点是，购买产品并不一定仅仅是为了满足合规要求，你首先需要做的是先了解企业内部究竟在发生什么。所以我认为合规是预算的一大推动力；而当事故发生时，通常会提升此类事情的优先级。请继续。

<details>
<summary>Original English</summary>
>> Out of the 56% without policies, I'm curious who's buying because regulators force them versus something broke. Like, what moves the budget?

>> Yeah, that's a good question. Something we think about a lot.

I would say compliance is a really good driver for people to think about getting a solution in place, but I think the the reason what I want to leave you with is that it you don't necessarily you know, buying a product is to fulfill compliance, but the first thing you need to do is kind of understand what is actually happening in your business first. So, I would say compliance is a great driver of budget. When there is an incident that that often, you know, raises the priority of something like this.

Go ahead.
</details>

>> 你们会对流经控制平面的日志进行 PII（个人身份信息）脱敏或掩码处理吗？

>> 会的。从阻断、掩码到编辑抹除 PII，我们全都支持。

我们在大多数企业中发现，当你开启可观测性并观察流经 Agent 的所有数据时，会有海量的 PII 穿梭其中。因此，如果你打算全面阻断 PII，很可能会让业务陷入停滞，对吧？因为人们在使用 Agent 时很难完全不接触 PII。我认为更重要的事情是观察这些 PII 的去向。也就是说，Agent 的意图是什么？它是打算将其发布在公开的 Slack 频道中、通过电子邮件发送，还是将其放回到针对另一个系统的工具调用中？这些才是我们建议大家借助可观测性去制定的策略，而不是单纯对所有 PII 一刀切地进行阻断或编辑抹除。

<details>
<summary>Original English</summary>
>> Do you mask PII or like the logs that come through your control plane?

>> We do. We do everything from kind of blocking, masking to redacting PII.

Um, what we've found in most businesses when you turn on observability and you look at everything going through the agents, there's a ton of PII going through. So, if you are going to kind of block on PII, you'll probably grind your business to a halt, right? It's just it's hard for people to not use the agents with PII. I think the more important thing to look at is what is happening to that PII. So, like what's the intent for the agent? Is it going to post it in a public Slack channel, send it by email, put it back into a tool called to another system? Those are the kind of policies we try to recommend people to, you know, use observability to define rather than just kind of blocking or redacting all PII together altogether.
</details>

>> 我问这个问题是因为，如果发生了事故，我会向控制平面索取日志以了解在授权方面发生了什么，对吧？

>> 是的。

>> 你必须把那些日志提供给我，对吧？但是，我一开始为什么要给你们数据呢？[嗤笑] 因为那是专有数据，是我们的核心秘诀。

>> 是的。

>> 那么对此的信任模型是什么样的？

>> 是的，这稍微涉及到我们部署方式的细节了，但我们的软件确实支持几种不同的部署模式。我们提供了一种数据平面选项，它可以运行在你自己的 VPC 中，因此数据始终保留在你那里。但客户更常选择的方式是自带加密密钥（BYOK），对吧？我们确实会对数据进行加密，但你提供自己的密钥，这样你就可以自己对其进行治理。

此外，客户通常会登录我们的产品界面查看所有的 PII 发生情况，至少从所有发现结果的视角去审查，哪怕他们看到的并不是被编辑抹除的数据本身。

<details>
<summary>Original English</summary>
>> I guess I'm asking that question because it's like if there is an incident, I'd ask the control plane for like our logs and to understand what happened, right? With authorization?

>> Yes.

>> You would have to like give those logs to me, right? But, why should I give you like the data [snorts] in the first place? Like because it's proprietary and it's our secret sauce.

>> Yeah.

>> So, like what's the trust model with that?

>> Yeah, I mean, that's kind of it's getting a little into the details of how we deploy, but like we do deploy our software in a few different ways. Like we do offer kind of a data plane option where it runs in your own VPC, so data stays with you. But, the more common option that customers do is they bring their own encryption keys, right? So, we do encrypt the data, but you bring your own keys for so you can govern it yourself.

And yeah, customers often will go into kind of our product and look at what is all the PII at that happened at least look at from the perspective of like all the findings even if they're not looking at the redacted data itself.
</details>