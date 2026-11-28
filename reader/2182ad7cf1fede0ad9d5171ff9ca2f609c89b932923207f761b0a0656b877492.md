---
author: AI Engineer
date: '2026-11-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=vlfCjWuv4es
speaker: AI Engineer
tags:
  - autonomous-agent
  - developer-tool
  - code-generation
  - software-security
title: Anthropic 团队分享：重新审视 Claude Code 最佳实践
summary: Anthropic 工程师 Lydia Hallie 探讨了随模型能力提升，Claude Code 开发模式从人工密集介入转向多会话并行与自动化编排的演变。她系统介绍了利用 Auto Mode、权限拒绝规则、沙箱与云端会话保障安全，结合 Hooks 与 CI 建立多阶段自动化验证，并通过编排会话管理复杂任务的实践路径。
insight: ''
draft: true
series: ''
category: ai-tooling
area: PAI
project: []
people:
  - Lydia Hallie
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
  - Opus 45
  - Opus 55
  - Fable 52
media_books: []
status: evergreen
---
### 从人工密集介入到多会话管理

今天早上演讲时我遇到了一些技术故障。所以我跑回家，改在电脑上把内容录制下来。大家好，我是 Lydia，在 Anthropic 的 Claude Code 团队工作。最近模型的能力有了很大提升。比如我们有了 Opus 55，它是我日常最喜欢的实用工具。本周早些时候，我们还发布了 Fable 52。这些模型在处理长时间运行的任务和理解代码库方面表现极为出色，尤其是 Fable，在验证自身输出方面也特别优秀。但随着这些模型变得更强大，我们在 Claude Code 中与它们协作的方式也随之发生了改变。

<details>
<summary>Original English</summary>
I had some technical difficulties during my talk this morning. So, I ran back home and I'm just going to record it from my computer instead. So, hi everyone. I'm Lydia. I work on the clock code team at Anthropic. And the models have gotten really good lately. So, we have Opus 55, which is my favorite daily driver. And earlier this week, we also launched Fable 52. And these models are extremely good at longunning tasks and understanding your code base. and especially Fable is also really good at verifying its own output. But as these models get better, the way that we work with them in cloud code also changes.
</details>

今年早些时候，不知道大家是否还记得，当时的会话差不多是这样的：我们会使用像 Opus 45 这样的模型，坦白说在当时它确实很棒，我很喜欢用 Opus 45。但与现在相比，它往往停得很早，只能运行较短的时间。我们需要不断纠正它，不断提醒它该做什么，在 CLAUDE.md 文件里加上一堆像“important”、“感叹号”之类的提示。而且当时还没有 Auto Mode 这样的功能，所以我们要么手动批准每一个操作，要么冒更大风险开启 `dangerously-skip-permissions`。那会儿我们人类依然深度参与在整个流程之中（in-the-loop）。

<details>
<summary>Original English</summary>
So earlier this year, I don't know if you remember, but sessions kind of used to look like this. So we'd use a model like Opus 45, which honestly for its time was really good. I really enjoyed working with Opus45. But compared to today, it would just stop a lot earlier. So it would just run for shorter amounts of time. And we'd also keep correcting it. We'd keep reminding it to do things, add things like important, exclamation mark, all these things to our cloud MD file. And also features like auto mode didn't exist yet. So we were either approving everything manually or taking the riskier approach with dangerously skip permission. So we were still very much in the loop as humans.
</details>

但随着模型承担更大任务的能力越来越强，我们的会话模式也随之改变。现在在 Anthropic，我们的会话更多是这个样子：我们同时并行运行数十个会话，它们能连续运行数小时，沿途不断验证自身的结果，我们甚至可以让某些会话去编排其他会话。过去我们几乎每一步都要介入，一次只运行一个或两三个会话；而现在，我们基本上转变成了管理数十个会话的管理者。与此同时，我们完成的工作量也大幅增加了。

<details>
<summary>Original English</summary>
But as these models got better at taking on bigger tasks, our sessions also changed. So nowadays, at least at Anthropic, our sessions look more like this. So we're running dozens of sessions at the same time, running for hours, verifying their own results along the way, and we even have sessions orchestrate other sessions. So whereas we used to be in the loop for almost every step and running one or just a couple sessions at a time, we've now essentially become managers for dozens of sessions. We also get a lot more done, though.
</details>

大家可能看过我们在 10 月份发布的一篇博客文章，提到 Anthropic 内部的代码变更从 5 月份的每天约 2500 次，增长到了 9 月份的每天超过 30,000 次。但这也意味着，作为开发者，我们必须重新思考我们的工作重心究竟应该放在哪里。如果回想今年早些时候的最佳实践，核心主要是引导会话、批准命令、对特定操作说不或限制 Claude 能做的事情、检查输出以及启动会话。现在只要我们从人工介入的流程中退出来，就必须有其他机制来接管这些环节——这要么是模型本身，要么是执行框架（harness），要么是其运行的环境。

<details>
<summary>Original English</summary>
Now, you may have seen our blog post in October about how Enthropic went from about 2500 changes a day in May to more than 30,000 a day in September. But this also means that we as developers just have to rethink on what we're focused on instead. So, if you think about our best practices from earlier this year, it was mainly about steering sessions, approving commands, saying no to certain things or restricting what cloud could do, checking the output and also starting the sessions. So everywhere that we now step out of that loop, something else has to take over. And this is either the model, the harness, or the environment that it's running in.
</details>

如果我们不再事事实时审批每条命令，同时又在并行运行这么多会话，我们该如何确保它编写的代码依然保持高质量？更重要的是，如果这些会话在脱离人工监督的情况下运行数小时，我们又该如何确保它们安全运行？接下来我们就以过去的老会话为例，看看需要做出哪些改变，才能达到我前面展示的最终效果。

<details>
<summary>Original English</summary>
So if we are not in a loop to approve every command, and we're running so many sessions at the same time, how can we make sure that the code it's writing is still high quality? And most importantly, if these sessions are running for hours without our supervision, how can we make sure that they're running safely? So let's go through that by taking this old session and seeing what we have to change to get to that end result that I showed earlier.
</details>

### 更新默认配置与精简上下文

首先，让我们直接使用如今启动会话时采用的实际默认配置。这其实是你根本不需要过多纠结的事情。我们把这里的模型从 Opus 45 升级到 Opus 55，并将手动审批权限切换为 Auto Mode。Opus 55 在理解意图和理解代码库方面能力大幅提升，因此在会话进行中，我们真的不需要再像以前那样频繁地介入引导。而且你也不必再逐个批准命令，因为我们在 8 月份就已经把 Auto Mode 设为了默认的权限模式。

<details>
<summary>Original English</summary>
Well, first of all, let's use the actual defaults we start sessions in nowadays. So that's not really something you should think about. So let's update the model here from Opus 45 to Opus 55 and change the manual permission to auto mode. And Opus 55 is a lot better at understanding your intent and understanding your code base. So we really don't have to steer it as much anymore midsession. And you also no longer have to approve every command because we started making auto mode the default permission mode back in August.
</details>

更擅长理解意图和代码库，也意味着我们必须重新审视写在代码库中的各类指令。如果你遵循的是今年早期的最佳实践，你的 CLAUDE.md 文件里可能还写满了诸如“important”或“never do this”加感叹号之类的强调语句。但面对今天的模型，你完全不需要这些，写了反而可能导致模型偏离正轨，产生更多的工具调用，整体输出更差的结果。

<details>
<summary>Original English</summary>
Now being better at understanding your intent in your codebase also means that we have to rethink the instructions we have in our codebase. So if you followed our best practices from earlier this year, you may still have things like important or never do this exclamation mark all these things in your cloudmd file. But with today's models, you really don't need that and it can actually make the model go off track. So you end up with more tool calls and overall a worse results.
</details>

如今你的 CLAUDE.md 文件应该只包含 Claude 无法直接从代码中推断出的信息。例如，你可能有一个服务仍在从某个遗留来源读取数据，但代码中没有直接引用，这类信息保留在里面是有价值的；至于你使用的是什么技术栈、或者该去哪里看代码这类内容，你真的不需要再写了。我们为此提供了一个名为 `doctor prompt audit` 的命令，可以非常轻松地针对特定模型优化你的环境提示。如果你使用的是这里的 Opus 55 并运行该命令，它会自动检查你的 CLAUDE.md 和 Skills，分析新模型不再需要哪些指令。

<details>
<summary>Original English</summary>
So nowadays your cloudmd file should only include the things that claude cannot see from your code. So for example, maybe you have a service that's still using some legacy source somewhere, but it's not directly referenced in the code. That's still good to keep in there. But everything else like what stack you're on or where to look, you really don't need that anymore. And we actually have a command for this called doctor prompt audit which makes it really easy to optimize your environment for a specific model. So if you're on Opus 55 here and you run this command, it will automatically check your CloudMD and your skills to see what the new model no longer needs.
</details>

### Auto Mode 与安全防御体系

Auto Mode 是一种权限控制模式，它会对除读取或编辑项目内文件之外的几乎所有操作运行一个独立分类器。它会自动放行其判定为安全的命令，比如运行测试或安装依赖，但对不确定是否安全的命令仍会予以拦截。通常情况下这很有效，也符合我们的预期。但举个例子，如果我们让它发布内容到预发环境（staging），通常我们只需要批准推送到发布仓库即可，但 Auto Mode 默认只信任当前文件夹和当前仓库，因此它会拦截该推送命令，导致我们又被迫回到审批环节。

<details>
<summary>Original English</summary>
Now auto mode is a permission mode that runs a separate classifier on pretty much everything that isn't just reading or editing files in your project. So it automatically allows commands that it knows are safe, like running tests or installing dependencies, but it still blocks commands where it's unsure whether they're safe. And normally that's pretty good. Uh normally that's kind of you know what we want. But for example here if we ask it to ship something to staging we would have just you know approved the push to our deploy repo but by default auto mode only trusts this folder and this repo. So it would block that command. So we're back in the loop.
</details>

默认设置在大多数情况下表现良好。但如果你发现即便开启了 Auto Mode 仍需频繁批准命令，首先应该查看设置选项。因为你完全可以在个人配置中用自然语言配置 Auto Mode，这些规则会被发送给分类器，供其判断放行还是拒绝特定命令。在这里我们可以直接写明信任哪些仓库、存储桶或域名，以及哪些操作应该始终放行或绝不允许执行。

<details>
<summary>Original English</summary>
Now the defaults should be good in most cases. But if you still notice that you have to approve a lot of uh commands even in auto mode. The first thing to look at is settings here because you can configure auto mode in your own settings just in plain English. And this is what gets sent to the classifier which then decides whether to reject or allow certain commands. So here we can just write which repos, buckets, domains we trust um and what it should always allow or never do.
</details>

坦白讲，这其实很简单。仅仅通过采用当下的默认配置，我们就已经摆脱了大部分需要人工介入的琐事，因为模型接管了引导工作，Auto Mode 接管了所有审批。因此脱离流程并不难，但更棘手的问题在于：我们如何确保在没有我们介入的情况下依然稳健可靠？这里分为两部分：首先是确保安全性，其次是结果验证。

<details>
<summary>Original English</summary>
Okay, so honestly this was pretty easy. By just using today's defaults, we've already gotten rid of most of our in the loop stuff um because the model took over the steering and auto mode took over all the approving. So getting out of the loop is easy. But the harder question now is how do we make sure it's okay that we're not there anymore. So first is keeping it safe and then also verification.
</details>

我们先从保证安全性讲起。因为到目前为止所做的一切——升级模型和启用 Auto Mode——都只是在与模型配合工作。大多数情况下它会按你的要求执行，但并没有绝对保证。在我们在 8 月份发布的一项研究中，我们对比测试了 Auto Mode 与真人参与审批的表现：面对明确危险的命令，只有大约 14% 的真人能及时察觉并拦截，而 Auto Mode 拦截了其中的 89%。它处理得确实比我们好很多，但仍有大约十分之一的危险命令被放过了。

<details>
<summary>Original English</summary>
So let's start with keeping it safe because everything so far so upgrading the model and using auto mode is just working with a model. And in most cases it does what you tell it to do. But that's not a guarantee. So in a study we published back in August we tested auto mode versus real people in the loop. and only about 14% of people caught a clearly dangerous command. Auto mode blocked 89% of them. So it is a lot better at it than we were. But about one in 10 of those commands still went through.
</details>

因此，如果你需要确定性的保障，就只能在执行框架层（harness）实施硬性约束，这也正是我们部分传统最佳实践仍然重要的原因，那就是权限规则（permissions）。举个例子，如果在你的项目中为某个特定工具调用设置了拒绝规则（deny rule），Claude Code 会在 Auto Mode 分类器介入之前就优先检查该规则。事实上，只要工具调用匹配了拒绝规则，分类器甚至根本不会收到它。因此，编写拒绝规则依然是确保 Claude 绝对不做某些事情的最佳手段。

<details>
<summary>Original English</summary>
So if you do want the guarantee, you can only enforce that in the harness. And this is where some of our older best practices still matters and that's permissions. So for example, if you have a deny rule for a specific tool call in your project, cloud code looks at this rule before the automo classifier even looks at it. In fact, if a tool call matches a deny rule, the classifier never even sees it. So having deny rules is still the best way to make sure clot actually never does something.
</details>

但你该如何区分哪些场景必须在项目中制定规则，哪些可以放心交给已经非常强大的模型自主处理呢？我认为衡量标准可以归结为一句话：如果 Claude 犯了一次错误，我是否能够撤销并挽回？如果它写错了代码，你完全可以执行回滚，因此这部分可以放心留给模型；但如果它丢弃了你未提交的本地更改，或者读取了敏感密钥导致其暴露在会话记录（transcript）中而你又不希望发生这种情况，这些就必须以规则形式约束。

<details>
<summary>Original English</summary>
But then how do you know what needs to be a rule in your project versus what the model can just know because they've gotten so good at it? Um, I think it kind of just comes down to if clot gets as wrong once, can I take it back? So if it writes the wrong code, you can still revert that. Um, so you can still leave that to the model, but if it throws away or uncommitted changes or it reads a key that's now in your transcript and you don't don't want that, that should still be a rule.
</details>

比如，假设我们坚决不希望 Claude 读取我们的 `.env` 文件。默认情况下，Auto Mode 认为这是正常的读取操作并直接放行。因此如果你要确保 Claude 绝对无法读取该文件，只需添加一条拒绝规则。这样一来，像 `cat` 这样的命令也同样无法打开该文件。

<details>
<summary>Original English</summary>
So for example, let's say that we just never want Claude reading our.end file. Now, by default, auto mode is fine with this. So it would have just approved it. So, so if you want to make sure that claude can never read this file, you should just add a deny rule. And then commands like cat cannot open this file either.
</details>

### 沙箱隔离与云端会话

然而事情并不总是这么非黑即白，因为有些命令会产生附带副作用。举个例子，假设这里运行 `npm test`，这是一条非常普通的测试命令，Auto Mode 判定其为常规测试并放行执行。然而当测试脚本运行时，它会执行非你编写的代码，比如第三方依赖库；或者 Claude 为了快速验证某些内容而临时编写并执行了一段脚本。如果其中某个脚本已被恶意篡改，它完全可以在执行过程中顺带打开同一个 `.env` 文件或你的 SSH 密钥，并将它们外发到一个你素未谋面的服务器上。

<details>
<summary>Original English</summary>
But it's not always that straightforward because sometimes certain commands can have side effects. So for example, let's say that npm test here a very normal command. It's just a test. So automote runs it. That's fine. But when the script is running, it runs code that you didn't write like your dependencies or maybe claude runs a script real quick that it wrote just to quickly check something. So, if one of those scripts is compromised, it could just open that same end file or your SSH keys and send those to a server you've never heard of, right?
</details>

即便当时有人类在场逐条手动点击审批，坦白说我们大概率也会直接点击允许，因为表面上根本看不出任何异常拒绝的理由，它仅仅是示例中 `npm test` 所调用的脚本内部行为。而权限规则只能决定一个工具调用是否允许被触发，无法约束该命令运行起来后所能触及的范围。我们显然希望能继续执行这类测试，因为运行测试是 Claude 自我验证工作的必要组成部分。我们不能直接禁用 `npm test`，但我们必须限制它的副作用。

<details>
<summary>Original English</summary>
And even if we were still there as humans approving everything, honestly, we would have just clicked allow because there's nothing to say no to. It's just part of the script that in this example case, npm test runs. And permissions only decide if a tool call runs, but they cannot limit what it can reach once it's running. So we want to make sure that these kinds of scripts can still run because this is just part of you know how cloud can check its own work running tests. So we cannot just block npm tests but we want to limit its side effects.
</details>

因此归根结底，我们要限制的是它所处的运行环境。如果你是在本地或自己的机器上运行，可以在沙箱中执行这些命令。这样你就能严格控制命令可以读取哪些文件、写入哪些目录、访问哪些主机，并由操作系统底层强制实施约束。这也同样约束该命令所派生的一切子进程。如果单靠拒绝规则，Claude 只能在命令启动前进行检查，它看到的仅仅是 `npm test` 这个命令字符串，根本看不到脚本后续究竟打开了哪些文件；但在沙箱开启的情况下，相同的限制规则会被传递给操作系统，当依赖项尝试访问 `.env` 文件时，操作系统便会直接予以拒绝。默认情况下它仍能读取你机器上的大部分文件，如果你介意的话，还需要专门为 SSH 密钥追加规则；同时它也无法访问未经批准的主机。

<details>
<summary>Original English</summary>
So really we just want to limit the environment that it's running in. So if you're running it locally or on your own machine you can run commands like that in a sandbox. So then you have control over which files in a command it can read, which folders it can write to, uh which hosts it can reach and the operating system enforces that. Also this also applies to everything that command then starts. So any child processes. So on its own that deny rule got checked by claude before the command runs. But all it sees there is npm test. So it doesn't see which files that scripts ends up opening. But with the sandbox on that same rule gets passed on to the operating system. So now when when that dependency tries to open our end file, the operating system just doesn't let it. And by default, it can still read most of your machine. So you'd want to add another rule for your SSH keys if you care about that. Um, and it also cannot reach a host that wasn't approved.
</details>

然而沙箱仅仅覆盖了 Claude 执行的 Shell 命令及其派生的子进程，Claude 自身的文件、你的 MCP 服务器以及所有的 Hook 仍然在沙箱之外运行。这意味着会话的其余部分依然运行在你的物理机及上面的所有环境之中。因此理想的方案是让整个过程运行在一个这些敏感资源从一开始就完全不存在的地方，那就是云端会话（cloud session）。

<details>
<summary>Original English</summary>
But the sandbox only covers the shell commands that Cloud runs and whatever those start. But Cloud's own files, your MCP servers, and all of your hooks still run outside of it. So the rest of your session still runs on your own machine and everything that's on there. So ideally you want this whole thing to run somewhere where none of that is even there in the first place and that is a cloud session because there it gets its own machine with a fresh copy of a repo and this runs even when we close our laptop which is definitely something you want for these longer running sessions that run for hours.
</details>

在云端会话中，它拥有独立的虚拟机和仓库的全新副本，而且即便合上笔记本电脑也能继续运行——对于长达数小时的长效会话而言，这绝对是必需的特性。在这种环境下，`.env` 的泄露风险自然不复存在，因为它压根不在 Git 仓库里，我的 SSH 密钥和 GitHub Token 也同样不在里面。如果它确实需要 API Key，你可以通过 Network Secret 进行注入：它可以在会话运行中提示缺少 API Key 并直接调用，而完全无需将密钥本身发送给模型。此外在云端会话中，网络访问默认受限，仅允许访问包管理注册源和 GitHub 等基础设施；若要访问其他主机，你必须显式将这些域名添加到环境中。

<details>
<summary>Original English</summary>
So in this case, this automatically gets rid of the end file issue because it's not in git. Uh and neither are my SSH keys or or GitHub token. And if it still needs an API key, uh you can add that as a network secret where it will it will tell you like, hey, I'm missing an API key midsession. Um so it can use it without actually ever sending it to the model. And by default, also in class cloud session, network access is limited to things like package registries and GitHub. So you have to explicitly add those domains to your environment for cloud to to reach other hosts.
</details>

依托云端会话，即便合上笔记本，我们也能安全运行长时间的任务，因为它是置身于隔离环境中运行的。不过仍需牢记：虚拟机本身虽然是阅后即焚的一次性资源，但离开该环境的产物却具有持久影响，比如推送到远端的 Commit，或是通过 Connector 发送的消息。因此我们在其中仍然配合拒绝规则运行 Auto Mode，并直接把规则提交到仓库中以随身携带。这样一来，它依然能够防御 Force Push 或提交中夹带敏感凭证等风险。

<details>
<summary>Original English</summary>
Okay. So with a cloud session, we can run these long running sessions even with our laptop closed and it keeps us safe because it runs in its own environment. Now it's still good to remember that this machine is disposable, but the things that leave it aren't. So a commit pushed or a message sent through a connector. So we still run it in auto mode with our deny rules. Just commit it into the repo. So they come along. Uh so it it could still catch things like a force push or a secret in a commit, all that kind of stuff.
</details>

### 自动化验证与反馈循环

除了安全保障之外，我们还需要确保 Claude 确实在做正确的事情，这就涉及到了结果验证。过去人工介入流程的一大好处在于，我们基本能确定交付质量，因为我们逐一过目并批准了每项修改。但现在 Claude 是在后台连续工作数小时，我们失去了原有的实时把控，而且在任务结束时，我们也不可能去逐行通读每个修改的文件。

<details>
<summary>Original English</summary>
And beyond just safety, um we also need to make sure that claude is actually working on the right thing. So next is verification. And the nice thing about being in a loop, uh like we kind of know knew the work was good because we'd already kind of seen every change. We'd approved everything. But now cloud works for hours in the background. We don't have that anymore. Um, and we're not really going to read every file at the end either.
</details>

举个例子，假设我们让它把身份认证机制迁移到一个新的 API。Claude 非常擅长理解我们的意图，但在执行过程中它需要做出大量细小的决策。即使面对完全相同的 Prompt，某次运行可能完成了迁移，但遗留下了旧 API；另一次可能完成了迁移，但仅对新登录生效；还有一次可能虽然迁移成功，却导致所有现有用户被强制登出。这些方案单看都颇具合理性，因此在执行路径中建立多处验证检查点（verification points）就显得至关重要，以便让 Claude 能持续自查检验。

<details>
<summary>Original English</summary>
So, you know, say that we ask it to move our o to a new API. Well, Cloud is very good at understanding what we want, but there are still a lot of small decisions that it has to make along the way. So, with the exact same prompt, you know, one run might move it over, but leave the old API in there, or one might move it, but only for new login, and another one might move it, but log everyone out. And these all look pretty reasonable, but it really helps to set up these verification points along the way. So Claude keeps verifying its own results.
</details>

这些检查点可以是任何能返回成功或失败状态的机制：测试用例、构建流程、界面截图等均可。我们现在的重心变成了只需去审查这些验证检查点即可。审查这些检查点比最终通篇审查全部代码变动要省时得多，也更具实操性。如果某次运行的改动导致所有人登出，它就会在首个检查点处被拦截，从而迫使模型寻找其他实现路径。

<details>
<summary>Original English</summary>
And those can be anything that comes back as a pass or fail. So tests, a build, a screenshot, whatever you have. So now we just want to make sure that we review these verification points. Uh they're a lot shorter to review than if we just had to, you know, review the whole change at the end. So So that's pretty reasonable. So, if one of these runs would still log everyone out, it doesn't get past that first check and then it just has to find another way.
</details>

构建验证检查点有几种途径。最简单直接的当然是在 Prompt 中明确定义。比如说明“完成”的具体标准，让它将总任务拆分为子任务，并为每个子任务配备对应的测试；同时我喜欢要求它展示实际的输出结果，毕竟你此前并没有在现场亲眼监控。但话说回来，仅靠 Prompt 并不能百分之百保证模型一定会按要求执行。

<details>
<summary>Original English</summary>
And there's a couple ways to set this up. Um, the easiest one is, of course, just in your prompt. So, you know, you say what done looks like and ask it to split that into tasks so they have their own tests. Um, and I also like to ask it to show the actual output because you weren't there to see it. But again, prompting is not a guarantee that a model will do it.
</details>

对于那些必须得到绝对执行的检查项，我会选择使用 Hooks。Hooks 本质上是 Claude Code 在特定时机自动触发执行的脚本，由于由你完全决定它们何时运行、运行什么以及检查什么，因而能提供极高的掌控力。例如，在每次编辑文件时，我们可以运行 Linter；每次它想要标记子任务完成时，我们可以触发与该变更相关的针对性测试；如果修改触及了认证相关代码，就必须通过认证测试；而在它想要结束整个会话时，我们可以执行全量测试套件。如果其中任何一项测试挂掉，它就会意识到此处仍有缺陷，自动返回并继续修改直至测试通过。

<details>
<summary>Original English</summary>
So for the ones that have to run guaranteed run, I would use hooks um which are just you know scripts that cloud code runs at a specific point and those give you a lot of control because you decide when they run and what they run and what they check. So for example every time it edits a file we can run our llinter every time it wants to mark a task as complete we can run the tests for what it changed. Um, so you know if it touched our off code or something it has to pass the off tests and when it wants to finish the whole session we can just run the entire test suite and if one of those fails it goes oh that's still broken it goes back until it passes so it fixes it.
</details>

这里有一个需要注意的细节：默认情况下，大多数工具在测试失败时会返回退出码 1，但在退出码为 1 时，Claude Code 仍会直接将该任务标记为完成。因此，请确保你的测试脚本在失败时以退出码 2 退出，因为只有退出码 2 才能真正让 Claude 回退并进行修复。

<details>
<summary>Original English</summary>
Now just one thing um when a test fails by default most tools they exit with a one exit code um but with a one that task by clock code just gets marked as completed anyway. So, make sure that your scripts exit with a twoexit code because that's what actually sends Cloud back to fix it.
</details>

### CI 门禁与 PR 审查分级

现在我们构建出了一个完全可以放心让其自主运行的独立会话。随后我们就可以并行启动更多类似的会话，因为它们都拥有专属的独立机器环境，彼此不会在同一个文件夹内相互冲突，我们自身也不用再去操心复杂的 Git Worktree 管理。然而此时我们依然需要亲自启动每个会话并挨个审查，虽然这已经是非常棒的工作状态了——我们牢牢把控着任务的启动以及何时判定完成，但不可否认，每个会话的触发和全程跟进仍然依赖人工。

<details>
<summary>Original English</summary>
So, okay, now we have one session that I'm pretty comfortable with leaving alone. So, now we can start with a few more of those because they've all got their own machine. So, they're, you know, not all working in the same folder and we don't really have to think about work trees too much ourselves anymore. But then we still start every session ourselves and we review every one of them. And honestly, this is already a pretty good place to be. We are still fully in control over what gets started and when we call a task done. But even there, um, you know, we're still the ones kicking off every session and we're still in the loop for all of them.
</details>

我认为在此阶段最为核心的支撑是你的持续集成（CI）系统。因为所有这些会话最终都会提交 PR，而无论会话是如何配置的、也无论 Claude 在执行过程中做过什么决策，CI 都会对每个 PR 执行完全相同的标准化检查。如果启用了类似 CI Autofix 的自动修复功能，Claude 在看到检查失败后能够自动回溯并修复，你就不必把人工 Review 的精力耗费在自动化检查本就能捕获的问题上。

<details>
<summary>Original English</summary>
So, I think the most important thing to have in place here now is your CI because all of these sessions eventually open a PR and your CI runs the same checks on every one of them, no matter how that session was set up or, you know, what Claude decided to do along the way. And if you turn on autofix, we have like CI autofix. Claude can also see when one of those checks fails and then go back to fix it. So you're not the one spending your review on things that you know a check could have already caught.
</details>

针对部分会话，你甚至可以开启“Merge when ready”（就绪后自动合并），一旦各项检查全部通过，GitHub 便会自动合并 PR，彻底免除人工介入审查。当然这并非默认设置，必须严格取决于代码变更的风险等级。以我们团队为例，每个 PR 都会先交由 Claude 进行第一轮 Review。执行 Review 的不是编写该代码的原始会话，因此它拥有全新的上下文视角，同时还会调动一组独立的 Agent 针对发现的每个 Bug 进行交叉复核。至于我们人类亲自审查的深度，则完全按风险梯度划分：像文档或文案这类微小改动无需人工介入，自动化检查全绿后即可合入；常规的产品代码变更通常只需一人审查；而高风险变更可能需要两人共同把关。

<details>
<summary>Original English</summary>
And for some of them, you can even turn on merge when ready. So then GitHub merges a PR once all of the checks have passed. So you're not in a loop to review. Um but again, that that's not the default and that really depends on how risky the change is. So for example on our team uh every PR gets reviewed by cloud first. So not by the session that wrote it. So it comes with a fresh context and also a separate group of agents to just double check every bug it finds. And then how much we review ourselves just depends on the risk. So smaller changes like docer copy, they don't need a person. So once the automated checks are green, we're pretty good to go. um maybe ordinary product changes just need one reviewer and then risky changes might need two.
</details>

### 多 Agent 编排会话与工程范式迁移

放眼未来的演进趋势——我们在 Anthropic 内部也正越来越多地践行这一点——你甚至不必再亲自启动所有这些会话。如果你和我一样不擅长频繁切换上下文，同时管理这么多并行会话往往很难应付。相反，你可以只维持一个主会话充当编排者（orchestrator）。这类形态在 Claude Code Projects（目前仍处于 Beta 阶段）中已初见端倪：你只需告诉它最终目标，编排者会将任务拆解，并为每个子任务派生其他会话，同时跟踪汇总返回的结果。它会自动启动并验证这些子线程会话，你只需与这一个主会话交互，而不必同时对接八个会话。

<details>
<summary>Original English</summary>
Now ultimately kind of where we see things going um and we're already kind of doing more of that at anthropic is that you're not really starting all of those sessions yourself either because if you're anything like me, I'm terrible at context switching. So having to manage so many sessions at the at the same time doesn't always go well. So instead you just have one main session that's your orchestrator. And you can already see this in things like cloud code projects which is still in beta but you just tell it what it needs to be done and the orchestrator splits that up and then starts other sessions for each task and it keeps track of what comes back. So it automatically starts and verifies these threads which are just new sessions. So instead of talking to eight sessions, you're just talking to one.
</details>

主会话本身并不直接编写代码，因此在主控位上你需要一个特别擅长任务决策和成果判定的模型，比如 Fable。如果子线程返回的成果并未达到完成标准，它会直接退回让其重新处理，直至真正完成并通过全部检验；而子线程则需要像 Opus 55 这样专精于具体编码落地工作的模型。你可以对它们分别进行独立配置——主会话配置一种模型，执行子线程配置另一种模型。这种架构在 Code Projects 下的另一个巨大优势在于，我们无需再手动管理上下文了，系统全部自动处理，我们再也不用费心考虑何时执行 compact 或清空上下文了。

<details>
<summary>Original English</summary>
And the main session doesn't write the code itself. So there you want a model that's really good at deciding what to do and judging what comes back. A model like Fable and if something comes back that isn't actually done, it just, you know, sends it back. So until it's actually done and passes everything and the threads need a model that's good at actually doing the work like Opus 55. And you can set those separately. So you know, one model for the main session and then another one for the threads. And another benefit is that with this setup with code projects specifically, we don't manage context anymore. That's all done automatically for us. So, we no longer have to think about, you know, when to compact or clear all of that stuff.
</details>

回顾昔日的最佳实践，各项核心要素依然存在，只是承载的角色发生了转移：
- 现在的**方向引导**由模型自身负责；
- **操作审批**由 Auto Mode 接管；
- **能力边界限制**由拒绝规则与隔离环境（沙箱与云端）共同约束；
- **代码质量把控**由你的测试、Hooks 与 CI 系统联合检验；
- 最终，甚至**会话的启动与分发**也可以交由 Claude 自主调度。

过去几乎所有需要由我们亲自做的事情，如今都已转交给了模型、执行框架或运行环境。我们真正的职责仅仅是开启最初的那个会话，并对最终的输出结果进行把关。

<details>
<summary>Original English</summary>
Okay. So, if you look back at those old best practices, they're all still there, but they've just moved. So, the model steers it now. Um, auto mode approves your deny rules and the environment restrict what's possible. Um, your test, your hooks, and your CI checks it. And then ultimately, cloud can just start them as well. So almost everything we used to do ourselves is now either the model, the harness or the environment. And we're really just here to start that first one and to just review what comes out.
</details>

如果你想在自己的工作流中尝试这种方式，我的建议是：挑一个体量远超平时交给 Claude 的大任务；确保你的 CI 能切实拦截你在意的各类问题；然后花一点时间配置好运行环境，比如网络访问白名单、Secrets 密钥以及初始化设置脚本；接着在云端启动运行，观察你的会话卡在什么地方、哪些环节仍需要人工介入，而那些卡点就是下一步该交接给 Claude 的部分。此外我也强烈推荐大家查阅官方文档中的最佳实践指引。非常感谢大家！

<details>
<summary>Original English</summary>
So if you want to try this in your own setup, I would say just take one thing that's way bigger than you normally give Claude. Make sure your CI actually catches the things you care about and then spend a bit of time just configuring your environment like its network access, its secret, and its, you know, setup scripts. and then start in the cloud and see where your sessions get stuck and where you're still in the loop because that's the next thing to hand over to Claude. I also highly recommend checking out our best practices in the docs as well. Thank you so much.
</details>