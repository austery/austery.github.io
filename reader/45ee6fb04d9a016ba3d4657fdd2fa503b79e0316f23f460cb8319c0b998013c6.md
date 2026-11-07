---
author: AI Engineer
date: '2026-09-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_mi3alkqy4s
speaker: AI Engineer
tags:
  - code-review
  - ai-agent
  - software-engineering
  - evaluation-harness
  - developer-productivity
title: 代码审查之死：AI 时代工程瓶颈与系统化重构的数据真相
summary: 随着 AI 编码代理普及，代码产出激增 741%，但实际交付仅增长 30%，代码审查成为新的致命瓶颈。人类审查能力无法线性扩展，而单纯跳过审查或依赖现有测试代理又面临语义与安全性失效。行业正将代码审查重构为包含多轮过滤、对抗校验与生产可观测性的系统工程，人类工程师的角色正从逐行检查代码升级为构建与校准审查系统的领航员。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Arize AI
  - OpenAI
  - Anthropic
  - Cisco
products_models:
  - SWE-bench
  - CriticGPT
  - Cursor
media_books: []
status: evergreen
---
### 产能倒挂：AI 激增代码遭遇审查瓶颈

在软件开发领域，**AI 智能体**（AI Agents: 能够自主执行编写、测试和调试任务的人工智能系统）的崛起彻底颠覆了生产速率，但整个软件交付链条却撞上了坚硬的物理现实。近期三位经济学家追踪了超过十万名 GitHub 开发者，并将其行为与开启 AI 工具的时间戳进行精确对齐。数据显示：开启自主代理的开发者产出的代码量惊人地增加了 **741%**，然而最终实际合并交付的软件量仅提升了 **30%**。这意味着代码生成效率暴增了近八倍，而交付成果仅增加不到三分之一。

研究结论直指核心：**代码审查**（Code Review: 由同行对变更代码进行缺陷与规范检查的过程）成为了阻断一切下游流转的严重瓶颈。当前通向生产环境的路径依然牢牢受控于人类，编写代码的边际成本已近乎归零，但确认代码是否安全可靠的认知成本却极其高昂——尤其是当代码涉及核心业务、具有巨大爆炸半径时。诸如 **Anthropic** 迁移数千万行 Ruby 代码或将百万行 Zig 迁移至 Rust 的案例层出不穷，团队面对代理生成的整套应用往往只能硬着头皮点击合并，并对未经审阅的变更心怀愧疚。

<details>
<summary>Original English Source</summary>

hello, everybody. thank you for following on a session about the death of the code review, with the session about the death of the code review. who knows how scheduling decisions get made, but switch decided it would be funny for those two to be back to back. I'm head of developer relations at Arize AI. some of you may remember me from when I used to cofound npm, Inc. These days, I think about how to test it.

I'm here to talk about a problem that everyone is seeing right now. the rise of AI agents has dramatically increased how fast developers can produce code, but the speed at which humans can review code the stayed exactly the same, and that is creating a new bottleneck that everybody is feeling. engineering teams across the industry are feeling it.

so what can we do about it? some options are we could skip human review entirely. some folks are trying that. can we automate reviews reliably? some folks are trying that too. what I'm going to do for you is I'm going to look at what the industry is really doing right now and try to figure out what you can do today when you leave the room.

so let's start with two numbers. recently, three economists tracked more than 100,000 GitHub developers, matched them against telemetry that showed exactly when each one started using AI. the developers who turned on autonomous agency wrote 741% more code, but only 30% more software shipped. that is the scale of the problem right there. they were writing code nearly eight times faster, but their actual shipped software only rose by a third, and the authors of the study are blunt that review was the bottleneck.

the problem is that the route to production still runs through humans, and the human steps, in particular code review, choke everything downstream. producing code is suddenly a whole lot cheaper; knowing whether to trust it is still very expensive, especially if you have sensitive code with a blast radius. how can we bring that second number down and thus bring the amount of software that we ship back into line with the amount that we can code?

let's zoom out. first, let's be clear: the problem is real, generation is no longer the bottleneck. Stripe in Anthropic's launch materials for Claude this year reported migrating a 50 million line Ruby codebase in a single day, which is work that they estimated would take over two months for our team. Bun, which is now part of Anthropic, reported that they migrated over a million lines of Zig to Rust in six days. and all of us in this room are feeling this on a smaller scale: our agents are generating whole apps, and we're just sort of hitting the merge button and feeling guilty about the fact that we haven't read these code diffs, and we're just sort of hoping that it works. we can't possibly keep on going like that.
</details>

### 人力极限：加大审查投入的认知断崖

面对这一瓶颈，一种直觉反应是要求工程师“更加拼命地审查”——将过去既写代码又审代码的人力完全转变为全职审查员。然而这种策略不仅会迅速引发工程师的职业倦竭，其生理与认知上限更是已被实证科学全盘否定。早在二十年前，**思科**（Cisco）开展过一项历时十个月、涵盖 2,500 次审查及 320 万行代码的大规模研究。

研究明确表明：当单次审查的代码量超过 **400 行** 时，评审员发现缺陷的有效性便开始实质性停滞；而当审查速度超过 **每小时 450 行** 时，其审查质量更会呈现断崖式暴跌。按此认知极限测算，一个由 AI 代理生成的常见 10,000 行 Pull Request（PR），需要一名人类工程师全神贯注审查三到四天才能提供合格的质量背书。而在当下，单个开发者可以同时并发调度十几个代理，试图依靠增加人工审查强度来吞吐如此规模的代码，在工程现实中完全是一条死胡同。

<details>
<summary>Original English Source</summary>

so the obvious answer, and the answer some people are trying, is you just review more. you take people whose job was previously to review code as well as write code and just review code all the time. this is your job now. and that doesn't work, partly because that's really boring and those people burn out really fast, but also the numbers say that we can't.

the best study we have on this was done two decades ago at Cisco. over ten months, they took 2,500 reviews, they took 3.2 million lines of code. and the study says that reviewers stopped finding defects effectively if they try to read more than 400 lines of code in one sitting, and their effectiveness completely falls off a cliff if they try to review more than 450 lines of code in an hour.

you do the math on that. that means that a 10,000 line agent pull request at that pace would take three or four working days to get a real human review. that is one pull request from one agent. 10,000 lines is absolutely an expectable number of lines of code for an agent that is doing a lot of work for you, and a developer can now run a dozen agents at once (though I tend to be suspicious of the people who do). so we can't just review harder, and we're all feeling that too. the people who are trying to review harder are burning themselves out.
</details>

### 闭环悖论：测试通过不等于可合并代码

在人类审查无法扩展的困境下，行业走向了另一极端：**将人类完全移出循环**（Removing the Human in the Loop）。包括 **OpenAI** 前研究员 **Andrej Karpathy** 与 OpenClaw 创作者 Peter Steinberger 在内的先锋均主张设计自动化反馈循环来替代人工审查。OpenAI 曾在 2024 年初公布其实验：仅用三名工程师，在五个月内完全依靠代理编写了包含 100 万行代码、1,500 个 PR 的内部产品，审查机制完全推向代理对代理。然而该策略掩盖了一个致命假设：以自动化测试通过作为衡量代码质量的代理指标，在面对真实生产标准时存在巨大断层。

非营利研究机构 METR 进行的严谨测试戳破了这一假象。他们雇佣开源项目维护者，对通过了 **SWE-bench** 基准测试的 PR 进行人工审查。结果显示：仅有约 **50%** 的测试通过代码真正达到了维护者的合并标准。这些未达标代码并非存在单元逻辑错误，而是破坏了测试集之外的系统性代码质量、架构规范与跨模块约束。随后 **Cognition**（Devin 开发团队）推出的 **Frontier-Code** 基准测试更进一步量化了该差距：同一套顶尖模型在 SWE-bench Pro 上能取得 88% 的高分，但在由维护者制定的真实“可合并性”严苛评测中，得分骤降至 29%，而某些模型甚至不足 6%。这揭示了一个核心事实：编译器与测试套件是廉价的验证器，模型可以针对性刷榜；但目前尚无人能将人类维护者直觉中的“可维护性”、“防御性设计”与“业务边界”形式化为可训练的代码审查标尺。

<details>
<summary>Original English Source</summary>

so what is the alternative? some people have decided to just stop reading the code entirely. Peter Steinberger, who is the creator of OpenClaw, says that you shouldn't be prompting coding agents anymore, you should be designing the loops that prompt agents. Andrej Karpathy, who is one of OpenAI's founding engineers, has made the same argument about taking yourself out of the loop because the human in the loop is holding the system back.

but this goes beyond bold claims on Twitter. in February this year, OpenAI published an account of building an internal product with, in their words, "no manually written code." they started with a completely empty repository, and agents wrote everything. five months later, they had about a million lines of code, about 1,500 merged pull requests, and they only used three engineers to do this. even the scaffolding of the agent to review the agent and stuff like that was also written by agents. what they said was, "humans may review pull requests, but they are not required to. we've pushed almost all review effort towards being handled agent to agent."

I think the interesting thing about the OpenAI experiment is that they did not tell us what product did, and they did not release an open source product saying, "and this is how we did it, and this is how you should do it," which suggests to me that there are still holes in that strategy. but it is one possibility. if OpenAI says that you can do it, maybe you can do it. the bet there is that loop design substitutes for inspection, whether you can build a loop that is good enough. all of it depends entirely on what the loop can see.

but that is an enormous caveat: what exactly can the loop see, and is it reliable enough to do code reviews? for years, the industry's proxy for quality has been whether the test suite passed, because that is what the benchmarks measured. in March this year, a research group called METR tested that proxy directly. they hired four active maintainers of open source projects from the same open source projects that SWE-bench tests against. they got them to look at PRs that had already passed SWE-bench's grader. so SWE-bench said this pull request is good enough to merge, and they got the open source reviewers to look at exactly the same PR and say, is it really good enough to merge? and it was only good enough to merge about half of the time.

and the failures weren't about correctness, because obviously the PRs were passing all the tests; they were about code quality, and they were about changes that broke other things external to the test suite. one caveat that METR mentions is that the agents got no chance to iterate on feedback, but that caveat isn't really relevant to our purposes because that's just putting a human in the loop, and what we're trying to see is whether or not we can take the human out of the loop entirely.

Cognition, the makers of Devin, built a benchmark around the maintainers' actual question, which is: "would you merge this?" they called it Frontier-Code, and they launched it in June. more than 20 maintainers built 150 tasks from their own repositories, each one over 40 hours of expert work. Frontier-Code grades behavioral correctness, regression safety, scope discipline, test quality, and maintainability. this is a human review rubric made machine-checkable. and what they found was that Claude 3.5 Sonnet scores 88% on SWE-bench Pro, but only 29% on the hardest slice of Frontier-Code. so the same model on the same surface with the same job does 51 points less well if you are asking not "does it pass the tests," but whether or not you would actually merge the result. and this isn't one model having a bad day: on the same set of tests, GPT-4o scores under 6%. so the strongest models we have are nowhere near passing human review reliably.

somebody has to write down what mergeable actually means; it's clear that we haven't done that yet. the moment they do, something will happen. Sarah Catanzaro, who is a prominent investor in AI, wrote about it and said that solving for that benchmark—a benchmark of genuine mergeability—will be a critical turning point in the development of coding models. in the essay where she was talking about this, she made clear why models got so good so fast at generating code: a compiler is a free verifier, a test suite is a free verifier, and anything that you can verify cheaply, you can train against until you beat it. that is what has been happening at the major model trainers.

a benchmark of mergeability, if we could make one, wouldn't only be a measurement; it would immediately become a training signal for the frontier models. which means maintainability, scope discipline, regression safety—the moment somebody comes up with reliable tests for those, the big models will be trained on them. whoever writes today's review standard is writing next year's default model behavior. we have some prior art here: in 2024, OpenAI trained a model called CriticGPT to catch bugs in model-written code. human reviewers working with it beat the model alone and the human alone. OpenAI built a model to review the models in order to clean the training data, and that created a training signal that's now built into the models. it made the models better almost instantly. but mergeability standards are still in the future; right now, we do not have a good rubric that captures everything that a human decides when they're deciding whether something is mergeable.
</details>

### 多遍博弈：商业审查引擎的去假阳架构

尽管终极的合并基准尚未统一，自动代码审查系统却已在大规模生产环境中全面铺开。**GitHub Copilot** 已执行超过 1,600 万次审查，占据全站五分之一的代码审阅量；而专注代码生成的 **Cursor** 则公开了其多智能体审查架构背后的核心工程实践。实现自动化审查的关键挑战并非发现问题，而是**控制假阳性率**（False Positive Rate: 将正常代码错误判定为缺陷的比例）——一旦审查机器人反复提出无关痛痒的虚假报错，工程师将彻底丧失信任并忽略系统。

为解决假阳性问题，Cursor 早期版本采用对同一差异比对（Diff）运行 8 次审查并发、打乱顺序重新审阅的策略，仅保留多次交叉验证后达成共识的问题。北京大学的研究亦独立证实，多遍审阅过滤机制能将审查质量提升达 **44%**。在后续架构重构中，Cursor 引入了工具调用与主动推理能力，其中最关键的系统提示词是强制模型保持**审慎与怀疑**（Default Suspicion: 默认代码存在隐藏缺陷而非顺从认可）。此外，代码审查正与自动修复深度融合：审查代理提出缺陷的同时生成修复补丁，甚至被赋予沙箱运行代码验证 Bug 真实性的权限，使审查与重写之间的边界日益模糊。包括 **CodeRabbit**、**Graphite** 与 **Qodo** 在内的厂商，均以开发者对建议的采纳率（Resolution Rate）作为核心优化目标，将其作为强化学习对抗微调的直接信号。

<details>
<summary>Original English Source</summary>

so who is actually running automated review right now? one company, GitHub—Copilot's reviewer has done 16 million reviews and now accounts for more than one in five code reviews on all of GitHub. machine review of pull requests is the mainstream default on the world's largest code host. that is more than an experiment; that is a large production deployment.

Cursor is also doing an enormous amount of code review. Cursor has published its reviewer's architecture, so we know how they're doing this, and the details tell you what the job really is. the first version of their reviewer would run eight review passes over each diff, then shuffle the order of the reviewers to review the code again and again, because shuffling the order in which they did those reviews changed the outcome. what they were doing was filtering for false positives, because an automated reviewer that flags something as bad when it's actually good is going to get ignored.

and it's not just Cursor who's doing this; there's research about it. a team at Peking University tested the same idea independently: run several review passes, keep what they agree on. and they found that it raised review quality by up to 44%. the multi-pass trick keeps getting rediscovered because false positives are the thing that kills a reviewer, and it actually works.

so then Cursor rebuilt their code reviewer so that the model reasons over the diff, calls tools, and decides where to dig. and my favorite detail from the rebuild was that they had to tell the model to be more suspicious of the code. the model tended to look at the code and say, "well, that looks good to me, ship it," which is exactly what a human would do in that situation. they had to tell it: don't trust the code by default, assume there is something wrong with it. somewhere in that sentence is a whole talk about what a good review actually is: it is about being suspicious by default.

the next thing that happens is that review is starting to fuse with repair. Cursor's reviewer now spawns a fix agent from its own findings. it doesn't just flag the bug; it hands you a diff to approve. approving that diff is another human in the loop, but we don't want humans in the loop. the next thing Cursor wants to do is the reviewer running the code to prove its own bug report is real. the line between reviewing and rewriting is getting very thin indeed.

and GitHub and Cursor are by no means the only vendors getting into this game; it's getting very crowded in there. CodeRabbit is the largest dedicated reviewer, has now reviewed over 30 million pull requests. Graphlit/Griptape builds a graph of your whole repository so that the reviewer can see how a change lands in distant code. Graphite builds evaluation sets from which of its own suggestions developers accept or reject. the thing to notice about what every one of them is doing is that all of them are using the same metric as their definition of success, which is: is a human accepting my answer? Cursor calls it the resolution rate, and it has driven it from 52% to over 70%. the reviewers are trained on human accept/reject judgment every day at scale. they are training their harnesses to get better at the definition of good as defined by human acceptance. that is a preview of what the models are going to do, except these companies have already shipped it.
</details>

### 暗礁潜伏：完全脱离人工审查的系统性隐患

然而，彻底脱离人工监管直接上线代理产出的代码，在真实工程案例中引发了灾难性的隐性技术债务。一个典型的反思来自 **Bun** 将其运行时环境从 Zig 整体移植至 Rust 的著名战役。尽管在六天内由代理生成了百万行代码且 **99.8%** 的既有测试用例均顺利通过，但后续深度代码审计暴露出令人震惊的数据：该移植代码库中包含了 **13,044 个 unsafe 内存不安全代码块**。相比之下，同等规模的人类工程实现通常仅包含约 74 个 unsafe 块，代理生成的内存风险高出整整三个数量级。

这一现象暴露了自动化检验体系的本质缺陷：测试套件只能验证显式声明的公开接口行为，绝无能力检测出测试未覆盖的内隐假设与边界缺陷。正如著名工程师 **Dexter Horthy** 经历半年“零人工审查”尝试后在公开演讲中的反转与忏悔，团队不得不花费数月完全推倒重构失控的混乱系统。测试用例永远无法表达诸如“某个看似多余的模块为何因未记录的外部依赖而必须存在”等系统级背景上下文；全盘信任自动化测试，仅仅是将未被发现的架构坍塌推迟到了未来。

<details>
<summary>Original English Source</summary>

so the status quo is: you can generate code automatically, you can review the code automatically, but humans still need to review the reviews. can you skip that part entirely? can you get the human entirely out of the loop?

there are two prominent projects that have tried so far that I've heard of. in February this year, Anthropic's Nicholas Carlini had 16 agents build a C compiler from scratch in Rust. it was able to compile the Linux kernel across about 2,000 sessions with no human in the loop. but if you read that experiment closely, it's true that there was no human approving the code as it was written, but there was absolutely a human *on* the loop. the system that reviewed the code, the system that checked whether the code was doing what it was supposed to do—all of that stuff was automated testing with tests that took a human to write them. Carlini's own warning when he wrote about it was that it is easy to watch the tests pass, assume that the job is done, and that it really isn't.

another very widely publicized experiment, which I already mentioned briefly in passing, was when Bun ported its entire runtime from Zig to Rust. that was about a million lines of code written by agents in six days. obviously, no human read that diff. the gate for that experiment was the existing test suite: 99.8% of the test suite passed, so the tests did real work. a fun fact about that experiment is that the PR where the agents decided that they were done with all of the Zig code and deleted all of the Zig code—one giant PR—was flagged by another robot as "this is AI slop, you can't possibly delete all of your code," which I thought was a fun aside.

but there are some big caveats on that Bun experiment. somebody looked carefully at the ported code, and it has 13,044 unsafe blocks. in a comparable human-written Rust codebase of that size, you'd see about 74. so three orders of magnitude more memory-unsafe blocks. an unsafe block is a place where the author asserts, rather than proves, that memory is being handled correctly. the test suite can certify behavior at the public interface; it cannot certify 13,000 assertions that the test suite was never designed to look for. so they took humans out of the loop for sure, but there's no knowing what is lurking under the surface of their Rust as a result.

let's go back to OpenAI, who have pushed this the furthest, because they show what skipping human review costs. they didn't delete review; they moved it. Codex reviews its own changes, then calls in more agents to review those reviews in a loop until every agent reviewer is satisfied. OpenAI made Codex bootable at every single change so that Codex can actually run a copy of Codex, look at it, look at the UI, see if the bug has been fixed, and they exposed the whole logging stack to the agent. and a line from their write-up says exactly what the Cisco study said, which is that when something failed, the fix was almost never to try harder—it didn't work. and one detail that you'll recognize from your own week is that for a while on this project, they had to spend every Friday cleaning up AI slop by hand as humans. so that didn't scale, and so they trained agents to look for AI slop and get rid of the AI slop. review didn't disappear—that is the lesson of this experiment. it got rebuilt as a system, and that system is built by humans.

so can you skip the human entirely? someone who tried it for real and then changed his mind is Dexter Horthy. he spent six months telling people not to review the code. he famously did that at AI Engineer Summit last year; he told people just ship, let the agent do its thing. and in March this year on stage, he took that back. he said: "I was wrong. please, please read the code. we tried not reading the code for like six months; it did not end well. we had to rip out and replace large parts of that system." that is not a benchmark; that is somebody who ran this experiment with real code on a real system and retracted his remarks, living with the results and reversing in public.

Sarah Catanzaro talked about why that happens: passing the tests never told you that the change was the right change. it never told you that this module exists because there are three external users of this module, or there's a cron job that nobody will admit to writing that relies on that module existing. there is context outside of the test suite that the tests can't find.
</details>

### 脆弱防线：提示词注入与自欺欺人的代理审查

除去架构层面的盲区，将代码审查全盘交由大模型还带来了严峻的**安全脆弱性**（Security Fragility）。自动化审查模型存在严重的认知偏差——极易受到具有高说服力、自信包装的恶意代码欺骗。Anthropic 在发布其自动化安全审查 GitHub Action 时附带了一条显眼的免责声明：该系统未针对**提示词注入攻击**（Prompt Injection: 通过输入文本操纵模型偏离既定安全规则的技术）进行强化防御，仅限用于受信任的变更审查。

近期学术研究进一步揭示了这种系统性漏洞：研究人员将隐藏后门的代码包裹在看起来极其合规、人畜无害的 Git Commit 说明中提交给自主审查代理，结果代理在 **88%** 的测试中被完全蒙骗并予以放行；而相同的恶意代码呈现在人类评审员面前时，仅有 **35%** 能侥幸逃脱。模型天生具有逢迎与顺从的倾向，非常擅长生成看似天衣无缝、言之凿凿却带有根本缺陷的代码，并能轻易说服另一个审查模型这毫无问题。当合规的防御演变为“互相点赞”的代理回音室时，整个系统的最终检验者便只剩下唯一的裁判——生产环境。在缺乏端到端审查保障的链条下，运行时的全链路**可观测性**（Observability: 通过外部日志、调用轨迹与指标评估系统内部状态的能力）成为了最后一道防线。

<details>
<summary>Original English Source</summary>

so in everything that we've looked at so far, the human checkpoint that retained its survival is moving around, but it is surviving in predictable places. one is where correctness isn't cheaply checkable. another is where the blast radius is large in security-conscious environments. every time you tell people "oh, we can just get rid of human review," you would get an immediate no wherever someone has to put their name on the results.

what's happening is the human role isn't disappearing; it is moving up the stack, possibly several levels up the stack, from inspecting the code directly to designing and tuning the systems that inspect the code and designing the definition of good. which raises the obvious question: who reviews those systems? if you build a system that does your reviews for you, how do you do the meta-review of your reviewer? and the answer won't surprise you: it is humans.

Anthropic ships an automated security reviewer, and in its README has a huge caveat, which is: this action is not hardened against prompt injection attacks and should only be used to review trusted PRs. so Anthropic's code reviewer can be talked out of its findings by the very thing that it is reviewing. and that is a finding that has been reproduced in a study in March this year: vulnerable code dressed up in an innocent commit message fooled an autonomous reviewer in 88% of attempts. the same attempts sent to a human reviewer passed only 35% of the time.

so you take the human out of the loop, you don't just lose a reviewer; you lose the thing that was hard to fool. automated reviews fall for confidently framed bad code, and confidently framed bad code is exactly the kind of code that agents are very good at producing. they're like, "this is good, and I am ready," and they are wrong sometimes.

and the other problem is that the field doesn't even agree yet on how to rate these reviewers. benchmark scaffolding has been leaking answers; researchers disagree on how to evaluate review quality at all. which leaves one reviewer that you can't automate and you can't skip, which is production. once the pre-merge review is all machines, watching what the code actually does becomes the last reviewer standing. once the code ships, the test result stops being the interesting thing; the trajectory does—what the system actually did step-by-step when it ran against the real world. I'm not going to give a pitch for Arize here—there are enough pitches for Arize at this conference—but if you're shipping automatically reviewed code, then systems in production that review what it actually does in the wild become indispensable.
</details>

### 范式跃迁：从逐行检视代码到主导审查系统

综合各项工业界与学术界的严谨实证，**代码审查并未消亡，但其抽象层级已经彻底重构**。在 2026 年及以后的软件工程格局中，将高价值的人类脑力消耗在逐行审查 PR 的 Diff 差异上，已经是一种落后的抽象层级错配。人类的核心职责正从底层的“代码检视引擎”跃迁为高维度的“系统领航员”。

未来最具竞争力的工程团队，绝对不是单纯借助代理生成最多行代码的团队，而是能拿出确凿系统证据、证明其发布软件值得信赖的团队。要跨越当前产出与交付脱节的鸿沟，工程团队应当立即采取行动：
* **停止微观审阅单个 PR**：承认单人审阅万行生成的生理不可行性，放弃疲劳战术；
* **投资构建审查基础设施**（Review Harness: 包含多遍推理、工具校验、防注入与对抗过滤的自动化测试框架）；
* **形式化业务上下文与合格标准**：将原本散落在工程师直觉中的隐性约束、防御边界与合并规范转化为可机读、可评估的评测基准（Evals）；
* **布控端到端运行轨迹分析**：将信任锚点延展至生产环境轨迹监测与主动可观测系统。

通过在架构顶层把控审查规则与评估基准，团队才能真正驾驭 AI 代理的数倍产能，构建起高吞吐且坚不可摧的现代化交付体系。

<details>
<summary>Original English Source</summary>

so after all that evidence, after all of that review, what the world is doing about automated code review is code review isn't completely dead, but it is changing an enormous amount. it is being rebuilt as an engineered system. humans are moving from being the engine that drives a code review, reading line by line, to its pilots. and given the numbers that we opened with, that is probably the right trade.

every layer of that system—the benchmark, the classifier, the rubric, the test suite, the evals—is itself under-reviewed until somebody decides that that is their job. and the teams that win in the next few years won't be the ones that generate the most code; they'll be the ones who can say with evidence why they trust what they ship.

and I opened by promising you that I would leave you with something practical that you could walk away with, something you can do today. and that is to stop reviewing PRs. it is the wrong level of abstraction for 2026. your human judgment is extremely valuable, but it can be made to scale much further than it is scaling right now.

pour your precious time into building a reliable review harness: codify your definitions of good, your company context, your domain knowledge, and then crank up the agents to work with that. you can go much faster than one-third faster if you concentrate your efforts higher up the stack on reviewers, rules, and evals.

I hope this look at what the industry is doing today has helped you decide what you should do and what to expect next. thank you so much for your time and attention.
</details>