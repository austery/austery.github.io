---
author: AI Engineer
date: '2026-07-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xIt_mTQp6mY
speaker: AI Engineer
tags:
  - control-loop
  - agentic-workflow
  - software-maintenance
  - feedback-system
title: 控制理论下的智能体循环：构建面向现实世界的软件工程闭环
summary: 来自 HumanLayer 的 Kyle Mistele 探讨了如何将控制理论应用于 AI 智能体编码循环。他指出盲目的“Ralph 循环”会导致代码库失控，并分享了如何利用 ast-grep、遥测数据监控和 CI/CD 流程构建具备自适应流控及人机协同的增量迁移与代码维护机制。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - HumanLayer
products_models:
  - Claude Code
  - ast-grep
  - React Doctor
media_books: []
status: evergreen
---
### 突破AI幻觉：构建面向现实世界的智能体循环

在当前AI辅助编程的风口下，业界充斥着大量关于智能体的过度炒作，这种声音往往无助于解决实际工程问题。许多人抱有一种天真的想法，认为只要将提示词和循环简单地对接给**智能体编码器**（Coding Agent: 能够自主执行编写、测试和调试代码任务的 AI 系统），就能自动构建出复杂的软件系统。然而在实际开发中，如果我们过度依赖这种盲目的自动化，最终只会产生多达数万行的**拉取请求**（Pull Request: 开发者提交代码变更以供团队审查和合并的机制），而团队中根本没有人愿意去阅读和审查这些庞大且杂乱的代码。

这种粗放的开发模式可能适用于个人玩具项目或非关键系统，但对于绝大多数在团队中工作的专业工程师来说，我们所面对的是包含真实用户、严格监管义务、以及**服务等级协议**（Service Level Agreement: 服务提供商向客户承诺的服务性能与可靠性标准）的复杂系统。因此，我们需要将目光转向如何在大型复杂代码库中构建真正可用的闭环系统。

业界已经开始意识到这一点。例如，**Peter Steinberger** 曾指出我们不应该再直接编写提示词来驱动编码智能体，而是应该设计能够自动生成提示词并引导智能体运行的“循环”（Loops）。目前，诸如 **OpenHands**（前身为 OpenDevin）等开源项目和 **Claude Code** 的创造者 **Boris Cherny** 都在强调这种“循环”机制的重要性。然而，当这些循环源源不断地产生代码时，代码的阅读成本也随之飙升，甚至出现了“只写不读”的极端倾向。此外，如果没有合理的预算控制，这种高频的智能体循环在实际运行中会消耗极其高昂的 Token 费用。因此，我们必须探索一种能够在现实世界中落地、且能让开发团队保持代码可读性和掌控力的智能体循环工程方案。

<details><summary>Original English Source</summary>

Hey everybody, my name is Kyle. Hums are really powerful, don't get me wrong, but so much of the discourse around them is hype and just really not helpful, right? We I think we have this idea just kind of as an industry somehow that we can like pipe a prompt and a loop to a coding agent and that we can build software this way, right? Maybe we're investing a lot of time in verifiers. Maybe you have six different code review agents. But at the end of the day, if we're doing this, we're still building 40,000line PRs that just nobody wants to read, right? And this isn't a throw shade to Jeff Huntley, right? The Ralph loop is an innovative, sharp tool that works very well for certain types of problems. It works very well if you're not building on a team and it works very well if you're not working on critical systems. But most of us are working on teams and we don't fit in that box. So today I want to talk about how to build loops that work in large complex code bases for systems that have real customers, real users, real regulatory obligations and service level agreements and everything else that keeps us from shipping yolo 40,000 line PRs straight to production. In other words, I want to talk about how to build loops for the real world. If you're not aware, uh, this post actually dates back to July. It went viral this past January, which is when a lot of us, I think, started building loops. And of course, much more recently, I'm sure y'all are going to see this slide a lot this week. Uh, but Peter Steinberger said that we shouldn't be prompting coding agents anymore, right? We should just be designing loops that prompt our agents. Of course, OpenHands is notoriously built on loops. Loops build the code. The loops review the code. They merge and release the code. They find and fix the bugs. There's even loops for finding and fixing bugs and the loops that are merging the things, right? It's loops all the way down. Boris Cherny, the creator of Claude Code recently said that this is his entire job as an engineer now is just writing loops to prompt Claude. And eventually we might not even need loops, right? We're just gonna have like swarms of agents designing loops to prompt agents building swarms for loops and like I don't know somewhere we're like writing production code I assume and in fact all of our loops that we're building are producing so much code that we can't possibly read all of it right so we might as well just not read any of it right we're we're investing in verification and in code review but all this code is read-only. This was the thesis of a conference that was here in town last month. So, a lot of smart people at the Frontier Labs think that this is the future of software development. And if you're doing this, you're moving 10x faster and everybody else is getting left behind. Now, it's not clear how well this works yet. It took six months to fix the Claude Code terminal flicker. The open-source team wrote a renderer in a fraction of that time. And OpenHands, of course, also notoriously has stability issues. What is abundantly clear, however, is that this is really expensive if you don't work at a frontier lab and have an unlimited token budget. And all this code that we're writing is actually really expensive, right? Matt PCO talked about this recently. Bad code is much more expensive in the age of agents than it has ever been at any point in the past. So today I want to talk about what I think works in the real world and what we've started doing at HumanLayer, which to be clear is still building loops, right? I think loops are super powerful, but we can design loops and still read the code. In fact, we can design loops that make it easier to read the code because the loops are making the code better, solve hard problems in complex code bases with loops, and we can build our software factory incrementally, but to do this is going to take some real engineering, y'all.

</details>

---

### 引入控制理论：软件工程的动态平衡系统

为了构建能够应对现实世界复杂性的智能体，我们必须引入**控制理论**（Control Theory: 研究如何通过反馈机制调节系统行为以达到期望状态的工程学科）。控制理论的核心思想在于，如何将一个动态系统（例如你的代码库）引导并维持在期望的稳定或最优状态。这一理论不仅适用于航空航天中确保战斗机稳定飞行，同样适用于日常软件系统。

在具体实现上，一个完整的控制闭环包含以下核心组件：
*   **传感器**（Sensor: 测量系统当前实际状态的监测单元），用于评估代码库当前的状况；
*   **设定值**（Set Point: 系统期望达到的目标状态），即我们希望代码库达到的理想规范；
*   两者之间的偏差即为**测量误差**（Measured Error）；
*   **控制器**（Controller: 分析偏差并发出具体调整指令的决策模块），它将误差转化为控制信号，指导具体的增量修改；
*   **执行器**（Actuator: 实施具体变更并作用于系统物理实体的执行模块），在系统面临外部干扰时执行修改，并重新进行测量与计算，进入下一轮循环。

这种控制闭环在现代软件工程中随处可见，从智能温控器、**Kubernetes 自动扩缩容**（Kubernetes Autoscaling: 根据实时负载动态调整集群资源容器数量的机制）、**声明式基础设施即代码**（Infrastructure as Code: 通过配置文件自动管理和配置IT基础设施的实践），到 PostgreSQL 的自动清理（Autovacuum）和 React 的虚拟 DOM 差分算法。它们都遵循着“测量当前状态、对比目标状态、进行增量微调”的逻辑。相比于一次性进行颠覆性修改的“盲目循环”，控制闭环倡导**渐进式增量修改**，这能有效防止系统发生超调或失控，最大程度降低线上风险。

在将控制理论应用于智能体开发时，各组件之间的界限往往可以更加灵活。例如，**Aiden Bai** 开发的 **React Doctor**（React Doctor: 一款用于检测和修复 React 代码反模式的高效静态分析工具）就是一个典型的传感器与控制器的混合体，它不仅能指出 React 代码中的潜在漏洞，还能直接给出排名前三的修复方案。同样，在智能体的工作流中，控制器与执行器也可以合二为一，在同一个上下文窗口中决策并应用修改。关键在于，我们必须能够清晰地定义测量指标、实施增量变更，并能对变更结果进行有效的反馈评估。

<details><summary>Original English Source</summary>

So let's talk about control theory. Control theory is all about how we drive a dynamic system which would be your codebase towards some desired stable or optimal end state. Right? You have a sensor that measures the current state of the world. You have your set point, right? The desired state of the world. And the difference between those two things is your measured error. You have a controller that reads that measured error and turns it into a control signal about an incremental change to apply to the system. We have an actuator that applies that change to the system which is undergoing disturbances in the meantime and then we reme-measure recompute our measured error and we're back where we started. Now this sounds really complicated and it can be. I have a twin brother actually who's an aerospace engineer. This is how they keep fighter jets from falling out of the sky. Uh but uh it's probably a little bit simpler than most of you all think. Does anyone have one of these? Uh a thermostat uses a control loop, right? Uh for for any of our European friends in the audience, it's part of something we have uh here in the states, it's called air conditioning. And uh most of us probably use control loops on a daily basis, right? Kubernetes autoscaling systems are built on control loops. Infrastructure as Code uses a desired state, current state, iterative change like control loop pattern. Postgres's autovacuum and React's virtual DOM both use or approximate control loops. Control loops are ideal when we have a system that we want to change a problem we can measure and a way to get feedback on the result of that change. Like good software engineers have always been taught to do. Control loops change a system incrementally instead of just trying to get straight to the end state immediately all at once and risk blowing everything up, right? They help us to avoid over steering and destabilizing the system and it minimizes risk. So control loops are the opposite of what I'm going to call a blind Ralph loop. They're how we avoid PRs that look like this because nobody wants to review this, right? Which is not to say that all Ralph loops are blind loops. The best Ralphs are actually applying control theory. I know Jeff Huntley is out in the hall somewhere wandering around. If you go talk to him, he's going to tell you the same thing, right? that Ralph is a a teaching device and I think some of us read it a little too literally but this is how we should have always been building loops but the other issue with Ralph loops is they're not incremental right it's just a bash loop so we have to build agentic control loops and to do that we start by defining a set point which is the desired end state of our codebase with respect to some property of it and we add a sensor there's a lot of ways to build a sensor it can be strictly deterministic your eslint rules your ast-grep, your packwork, or it can be non-deterministic. You can have an agent and a skill and a bunch of natural language rules. And you could also just have a pipeline, like a combination of the two. So, how do we build agentic? Whoops, there we go. Now, uh this is all theory, right? Practically speaking, and because we're using agents, we can blur the lines a little bit between system components. So, Aiden Bai's React Doctor, for example, is fantastic. It is uh it's a great way to catch all of the React slop that Claude snuck into your codebase last week, but uh it's a hybrid sensor and controller. It tells you what are all the problems with your React code and also by the way, what are the top three things you should fix and how do you fix them. Similarly, our controller and actuator might actually just be a single agent deciding on an incremental change to make and then applying it in the same context window. But I want to zoom in on the controller a little bit because without one or without a welltuned one, we might make too large of a change all at once or we might make the wrong change entirely. And if you put that in a loop, you're in trouble pretty quickly. So we can use control loops to root out bad patterns and to clean up our code, but we can actually use them for all sorts of things, right? We could make sure that our API is compliant with someone else's open API spec. We can make sure that our MCP server is compliant with whatever version of the MCP specification that we're currently on. Haven't checked. You could mirror a project from Python into TypeScript or vice versa. You could even maintain your Vite-based fork of Next.js against the upstream. The key questions are can we find something we can measure? Can we apply changes incrementally? And can we get feedback on the quality of those changes?

</details>

---

### 落地实操：基于ast-grep与遥测数据的增量迁移

为了让这套控制理论落地，Kyle 分享了 **HumanLayer** 内部正在运行的一个真实案例：将他们的 RPC API 逐步增量迁移到 **Effect 框架**（Effect Framework: 一个用于构建类型安全、高并发及强容错应用的 TypeScript 函数式编程库）。

在这个迁移过程中，团队按照以下步骤构建了控制闭环：
1.  **构建传感器**：他们放弃了使用大模型进行全文扫描，而是选择了 **ast-grep**（ast-grep: 一种基于抽象语法树的快速、轻量级代码搜索与重构工具）。它比简单的正则搜索更精准，且不受 TypeScript 编译器或 ESLint 规则的约束（AI 经常会通过添加行内注释来规避 linter 规则）。通过编写 ast-grep 规则，团队能够精确找出所有尚未迁移的 RPC 方法。
2.  **引入干扰防护机制**：为了防止在进行迁移的同时，其他团队成员在合并代码时引入新的未迁移方法（这在控制理论中被称为“外部干扰”），他们在主分支上运行一次全量扫描，将所有的违规项记录在版本控制中。在后续的 PR 流水线中，如果发现有新增的未迁移方法，则直接拦截。这种方法可以被形象地称为**干扰阻尼器**。
3.  **设计智能控制器**：最简单的控制器可以直接选取违规列表中的第一项进行迁移。但为了降低风险，可以使用 ast-grep 找出体积最小的未迁移方法优先处理。更进一步，还可以结合生产环境的**遥测数据**（Telemetry: 自动收集并传输远程设备或系统运行状态指标的技术），优先迁移那些报错频次最高、或者监控盲区最大的接口。在将这些遥测数据作为控制信号传递给执行器时，智能体不仅能完成“一对一”的代码重构，还能顺便补充日志 and 监控，真正提升代码质量。

<details><summary>Original English Source</summary>

To illustrate that, I'm going to walk through a control loop that we use internally at human layer. Uh for our loop, we are incrementally migrating our RPC API to effect. We adopted it for some of our raceprone code. We like it, so we're adopting it across the rest of our codebase. If you've never seen effects code before, the code on the right is just the kind of trivial procedure on the left rewritten in effect. Uh the syntax is really weird. We're psychos. We really like it. It's not for everybody. That's okay. Uh this isn't a talk about effect, so we'll keep moving. Clicker's not working. Cool. So, step one, we have to build our sensor to find unmigrated procedures. We can have an agent do this or we could use GP or RIP Grep, but instead we're going to use ast-grep because it's really powerful. It's a great tool to have in your toolbox for building loops. It's language agnostic. It's out of band from your TypeScript config or ESLint rules, which if you're a TypeScript developer, you have watched Claude disable those with inline comments. Uh but so we can just write a simple rule that finds unmigrated procedures based on the pattern above and we over time we can even layer on more rules that describe other patterns we want to get rid of with granular include and exclude paths. If you have a multilingual monor repo like we do uh it'll work for any language you could possibly imagine. And we can just scan our codebase and it'll produce a long list of violations. Uh way too long in fact it'll give you about 50 keys per violation. So, we're just going to filter it down to four and we're going to sort it deterministically. Why are we doing that? At the beginning, I said this was going to be practical. And so, we're going to step outside of our control loop paradigm for a second because before we start incrementally migrating procedures one at a time, we need to enforce that all new procedures are using effect, right? So, we're going to run a full scan once on main, sort all the violations deterministically, and track it in our version control. And then on every new PR we can see if the branch added any unmigrated procedures. Right? So this is our control loop and our system is undergoing disturbances. In this case uh all of our teammates shipping cloud slot and this is how we make sure that they're not undoing our loop's work. This doesn't map directly to a part of the control loop but we can kind of like squint at it a little bit and call it a disturbance dampener. So now that we've stopped the bleeding we can actually design our controller. For a simple controller, we could just deterministically pick the first violation from the list. You can use bash and jq. Or we could get a little cleverer and use ast-grep to find the smallest unmigrated procedure and always pick the smallest one to reduce the risk. Uh we could have an agent make the decision if we really want to. I don't think you should ever send an agent to do deterministic code's job, but you certainly can. In fact, depending on the complexity, we could have the agent pick the procedure to migrate and just do it at the same time like we just talked about. But we can make this even more powerful, right? Because we're not just migrating to effect for the sake of it. We're doing it because it's helpful for handling errors and for helping us instrument our code better. And so what we could do if we want to get really clever is we can look at our telemetry and figure out which procedures have the most errors or the least instrumentation or has a gap in our APM, right? And when we send a control signal to our actuator agent, we can include not just the procedure to migrate, but also all the data about the things that we're trying to fix with this migration so that the actuator agent can actually make the code better instead of just doing a onetoone migration.

</details>

---

### 终极闭环：人机协同与低摩擦反馈机制

在确定了要迁移的代码目标后，下一步就是构建具体的**执行器**（Actuator）。执行器由“AI 智能体”和“工具技能（Skill）”两部分组成。

在构建执行器时，Kyle 强调了以下实操经验：
*   **编写“金色模板”**：在让智能体开始大规模干活之前，人类工程师应当手动编写几个高质量的迁移示范。智能体本质上是优秀的模式复制者，如果不提供清晰的内部最佳实践，它们就只能根据网上良莠不齐的公开文档和陈旧知识来写代码。
*   **无缝集成 CI/CD 流水线**：将整个“感知-控制-执行”的过程封装在已有的 GitHub Actions 或 GitLab CI 中。智能体在独立的分支上修改代码并提交，最终生成一个以重构详情为描述的拉取请求（PR）。每天早晨，工程师一上班就能收到一个低风险的增量修改 PR。
*   **人机协同（Human-in-the-Loop）**：如果智能体改错了，传统的本地调试和重新提交会带来极高的摩擦力。为了让修改过程更平滑，团队引入了一个受版本控制的 `feedback.md` 反馈文件，并在 CI 流水线中注册了评论触发器。当开发人员在 PR 中发表类似 `/iterate` 的评论时，CI 会自动将当前的 PR 差异、审查评论和上下文重新喂给智能体，让其修复代码并更新反馈文件。这种方法不仅大幅降低了人机交互的门槛，还将智能体的调优指令和演进历史记录在了 Git 中。

<details><summary>Original English Source</summary>

Oh man, there we go. So next is building our actuator. Our actuator is just an agent plus a skill. Um, bring your CLI coding agent of choice. You should spend a lot of time on the skill. Not all of that should be up front. You'll want to iterate on it over time based on what works. At human layer, we like to build out what we call golden patterns by hand before setting the agent loose. These are just like idiomatic handwritten examples for the agent to follow because they're just pattern replicators and otherwise you're getting what's in the docs or what the agent knows from the internet. And so we pipe the skill plus our control signal into our actuator agent. And the skill of course should include a response template. And the agent's going to work and work and work and it'll produce a final response. And then we're going to deterministically commit and push and create a PR using the final message as our PR description. Now all we have to do is actually run the loop, right? Uh my recommendation is to use GitHub actions or your GitLab or your CircleCI or whatever else you're using because it has access to your code. It has access to your secrets and it has great dispatch and scheduling primitives. Right? We don't need a new cluster for this. So we can write a workflow that runs a single iteration of the loop sense control actuate and creates a PR and then we can schedule this to run once a day. And every morning we walk into the office to a small incremental PR that's low risk. And when we first did this, it was actually really frustrating and we turned the loop off and it uh because we had to constantly update the skill. We had to constantly check out the branch, change the skill, change the code, commit and push. And our loop was actually really high friction, right? But there's a better way to do this uh where we can put a human on the loop in a really low friction way to resteer it when it goes wrong. And the way to do this is to just create a feedback file that's tracked in version control just as a markdown file, right? we can deterministically load it into our actuator agents context every time that it runs after we run the controller. Then we can add a label to the PR. Right? Each workflow needs to be able to identify PRs that it created since there might be a bunch of different loops running and we only want workflows to respond to feedback from comments on their PRs. And we're going to add a comment trigger to each loop workflow so that when a user leaves a slashiterate comment on the PR, uh the loop workflow is going to pick that up. It's going to deterministically load all of the PR context, the diff, the comments, the review comments, the description into the agents context along with the skill, and it's going to instruct the agent to fix the code, but also to update that feedback file, right? Looks kind of like this. And the benefit of doing this way is that now that feedback file with instructions is tracked in your version control. You can see how you've changed it over time. You can revert it if you need to.

</details>

---

### 流程控制与吞吐优化：应对规模化协作

在实际的大规模团队协作中，如果不对智能体循环加以限制，它们很容易失控。例如，在团队度假或开会期间，无人审查的 PR 会迅速堆积，甚至产生冲突。为了解决这个问题，团队引入了**自适应流控**（Adaptive Flow Control: 一种根据下游人类消费能力或未决任务状态，自动限制和调节上游任务生成速率的系统调节机制）。

其核心规则非常简单：每次 CI 触发任务前，先通过标签检查该智能体循环是否已经有一个打开的 PR。如果已经有一个 PR 处于“等待人工审查”状态，那么流水线将自动中止，不再生成新分支。这样能确保任何时候每个循环最多只有一个 open 的 PR，避免了垃圾代码的堆积和冲突。

在保证了系统稳定之后，我们可以进一步通过以下机制提升**吞吐量**：
*   **多任务打包**：让控制器每次选出 3 至 5 个方法进行迁移。
*   **多上下文隔离运行**：与其在同一个上下文窗口中修改 5 个文件，不如将它们拆分到 5 个并行的 CI 实例中运行，不仅速度更快，而且模型因为上下文窗口干净，成功率也更高。
*   **并行分发审查**：通过 CI 将这 5 个 PR 分发给团队中的 5 位不同成员分别进行审查。

总而言之，通过将传统的盲目循环改造为基于控制理论的智能体循环，团队在保持代码高可读性、高透明度以及低维护成本的同时，成功实现了大型系统架构的渐进式重构。

<details><summary>Original English Source</summary>

So, the next thing we're going to do is add flow control. Because the other problem that we had when we did this was that if we were at a customer site for a week or if we were traveling or spent six days working on slides instead of writing code, uh the PRs from all of our loops would just stack up. They'd duplicate work. They'd conflict and we wouldn't get around to doing it. And like the loops work is important, but it's not that important. And so now we just had all this like junk we had to deal with that wasn't important. So this is actually a really easy problem to fix uh because each loop and its workflow has a label that gets attached to PRs. When the workflow first runs uh before we check out the code and install the dependencies and run our sense actu or sense control actuate steps, we can just check and see if the last PR that we created or any PR with the loop's label on it is open. And if so, we just shut down, right? Because this means that the last time that a human uh reviewed the code from this loop was before the loop ran, right? No human reviewed the last output. So there's no reason to stack up even more work for humans to review. This way we have exactly one PR at most open per loop at a time. No stacking, no duplication. Hopefully no conflicts. And of course once you're feeling confident in the loop, we're going to want to speed it up, right? I have 150 RPC procedures to migrate. If I do one at a time, it's going to take six months, which is way longer than I want to wait. Fortunately, there's a lot of ways to pick up the the velocity of our loop. Uh we could have our controller pick three procedures to migrate instead of one at a time or five. Uh we could have our controller pick three or five and then do each of those in a separate implementation phase, which will be both cheaper and more reliable since each migration gets its own context window. Or we could just run the workflow four times and give one PR to each of four people on the team. So let's put it all together. We built a control loop that improves our code incrementally and we're actually reading the code. It has adaptive flow control so we're not creating a bunch of loop or a bunch of work that nobody wants to review. And we can resteer it on the fly in a super low friction way. If you want to try this yourself, uh we built a skill. Please try it out. My Twitter handle is down there on the bottom. Please share it. I would love to see what you build. And if you get excited by this, uh at Human Layer, we're hiring here in San Francisco. And if you're working on mission critical systems and want to figure out how to get more out of AI, we'd love to chat. Thank you so much.

</details>