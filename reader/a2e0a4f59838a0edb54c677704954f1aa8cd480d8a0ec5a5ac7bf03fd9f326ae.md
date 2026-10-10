---
author: AI Engineer
date: '2026-07-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-I5W5QVAT8E
speaker: AI Engineer
tags:
  - token-economics
  - model-interoperability
  - agent-orchestration
  - open-weights
  - software-factory
title: 逃离令牌城镇：Notion 的多模型互操作与软件工厂实战
summary: Notion AI 团队负责人 Sarah Sachs 分享了如何在大模型时代避免沦为“Token 贫困”阶层。她探讨了 AI 从助手向系统化协同的演进，揭示了供应商与应用商之间的竞争本质，并详细阐述了 Notion 倡导的“瑞士模式”多模型路由、开源权重杠杆、CPU 异构计算以及软件工厂中代理编排的安全治理策略。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Notion
  - Decagon
products_models:
  - Notion AI
  - Claude Code
media_books: []
status: evergreen
---
### 从 Thought Partner 到 Workflow System：AI 协同的演进与核心痛点

在当今瞬息万变的 AI 时代，企业在推进技术落地时正经历着深刻的范式转移。正如 **Sarah Sachs**（Notion AI 团队负责人，自嘲在合同谈判中行事像 AI 界的 Anna Wintour）所分享的，Notion 在 2026 年实现了 AI 使用量的爆发式增长。

Notion 从创立之初就是企业持久的**记录系统**（System of Record）和团队协作的核心阵地。如今，这种协作的边界正在被重新定义——它不再局限于人与人之间，而是拓展到了人与 Agent、Agent 与 Agent 之间的网状协同。企业在探索 AI 转型时，通常会经历四个关键的演进阶段：

* **思想伙伴**（Thought Partner）：最初的尝鲜与探索阶段。例如在感恩节前后，用户尝试使用初版聊天机器人写一封邮件给房东以协商减免重新粉刷的费用，然后手动复制粘贴发送。
* **助手**（Assistant）：执行单一的、割裂的任务。Notion AI 早期便处于该阶段，虽然能够节省员工时间，但其上限完全取决于人类的显式指令输入。
* **队友**（Teammate）：Notion 近一年前推出的功能，能针对特定的重复性流程进行闭环处理。
* **工作流系统**（Workflow System）：AI 演进的终极形态。在此阶段，AI 真正融入核心工作流，不同的 Agent 和后台进程相互接口、自动协作，整套系统实现自主化运转。

然而，行业数据表明，目前有高达 **88%** 的企业甚至无法跨越“AI 助手”阶段。这其中的痛点在于，企业内部沉淀了太多**孤立数据**（Siloed Data），缺乏一个统一且持久的记录系统来承载协同逻辑。要让面向未来的“软件工厂”和多代理系统切实发挥作用，就必须依赖像 Notion 这样强韧的记录系统作为信任根基与数据底座。

<details>
<summary>Original English Source</summary>

Okay. Hello. Okay. Before I get started, you guys, this is a huge keynote room. Can everyone like come forward because I'm talking to like four empty rows and disperse people. Do me a favor. I'm spending 30 minutes telling you all of our secrets. I can see you still. Thank you. Thank you. Thank you. Thank you. We're just going to chat. It's a giant room and there's 500 of us. This room is way larger than that. Thank you. Honestly, I knew you guys had it in you. It's really not so hard. Thank you. I also sit in the back. I also work during talks. I get it. I totally get it. I did all day, but not for me. Okay, I'm gonna start, but I'm gonna still point at you if you're in the back like you. Okay, I'm Sarah. I'm lead our engineering teams for AI at Notion. Um, welcome to my talk. Um, it's about token town. How do you go from not go from AI pled to AI poor? Okay. Um, I know that today is all about software factories. We're going to talk about that, but we're going to talk about how to do it sustainably. This is me. This is on my first day at Notion in a very sweaty subway. Um, like I said, I lead our AI teams at Notion. Um, and I negotiate AI contracts for a living. My team jokes I act like Anna Winter. So, this is a nice a nice image of me with AI Anna Winter hair after a press article referred to me that externally. Um, and that's kind of the idea, right? Uh, how do you think about negotiating between different vendors? um making sure that you maintain taste for your company. I don't do it alone. Um this is launch day of one of our recent launches. This is just a subset. Any good engineering manager points out that we have a whole company of people building this. I'm just the one that gets to come talk to you about it. So, we've been building a lot. Um this is um an example of our AI usage um just in 2026. Um and we've been really proud of how we've been able to grow that usage. and I'm going to talk to you about how you can build an AI native product and an AI native company. Um, but this is just to give me some credit that that we're doing it kind of well. Okay, so for those of you that don't know, notion's always been that durable system of record. It's always been the place where you can collaborate with your peers. Um, but today that point of collaboration is a little bit different. It's not just humans. Notion's always been the place for collaboration. And today that collaboration happens between humans and agents. Humans and humans, agents and agents. And we like to think about AI transformations going through this journey. And I'm sure some of you are looking at the slide and wondering where you are. AI as a thought partner is when we all started tinkering. We all started just going to the very first version of chat on Thanksgiving when it came out three years ago, four years ago. And we started saying like how can I send this email to my landlord to say that I shouldn't pay for repainting right then we'd copy paste it enter it into our email eventually we started getting to a place where we could use AI like an assistant AI was able to maybe execute individual tasks that's how notion AI really took off in the beginning um and it was able to save employee time but functionally was limited in its capabilities based on what humans asked it to do AI as teammates is what we were really excited to launch almost a year ago now. Um, but this is true in many products where we can do repetitive work and think about a process and have AI do that process. What I think is really interesting is when AI actually becomes that critical workflow where processes are interfacing with each other and you have entire systems running. How many of you guys feel like you have AI as a system down? Aren't you sad you came up now? Great. None of you. Exactly. We have found that no one has figured out how to do this well. 88% of people can't even get past AI as an assistant. And why is that? We have a thesis at notion. It's because there's too much siloed data and not a sturable system of record for that point of collaboration. And we believe that for your software factory to work, for your company to work, and for your systems to work, you need that durable system of record. And that is notion's mission.

</details>

---

### 令牌城镇的经济困境：如何打破供应商的垄断与成本壁垒

在探索 AI 系统化转型的过程中，极高的运行成本成为了行业普遍面临的结构性壁垒。

许多公司盲目跟风，将资金砸向未经验证的复杂流程，最终往往发现自己陷入了尴尬的境地——这就像是“**使用喷火枪去点燃一支大雪茄**”（using a blowtorch to light a large cigar），成本支出惊人，却未能产生对称的商业价值。这种成本结构对于以应用层为核心的 AI 企业而言是致命的。

在当前的商业生态中，应用层企业必须清醒地认识到一个事实：**你的模型供应商（Supplier）实际上正是你的竞争对手（Competitor）**。如果你只接入单一供应商，你的业务就完全丧失了退路。以 Token 采购与转售为例，前沿模型实验室（Frontier Labs）售卖给企业客户的 Token 包含极高的中间溢价，而他们提供给消费者的第一方订阅制产品定价却极具竞争力。在这种不对等的游戏规则中，单纯依靠倒卖 Token 的企业在经济上根本无法建立可防御的竞争优势。

因此，应用层企业的制胜点绝不在于 Token 经济学上的粗放博弈，而在于回归**产品本身**（Product）与构建**数据飞轮**（Data Flywheel）：

* 精准判断客户在不同场景下对模型能力、低延迟或性价比的动态需求。
* 不盲目追求“用大炮打蚊子”的最强模型，而是将重点转向出色的用户界面（UI）设计与精细化的 Agent 编排，以此消化底层 Token 的高昂溢价。

<details>
<summary>Original English Source</summary>

So doing that is expensive. Um you see a lot of companies that try and commit themselves to this vision and these are just a series of headlines all within a week of how that's painful. So you can put all of your money into a process to try and make a system and you end up feeling like this, right? You end up using a blowtorch to light what is actually a large cigar. But you kind of get the idea. Cost is a structural barrier to entry. It makes it hard for you to serve products. It makes it hard for you to build factories. And it is ultimately, I would posit, one of the largest reasons why things do not happen at scale successfully today. And I would argue for anyone working in an applied AI company, it's something for them to be really familiar with to understand the trade-offs that they're making to build durable and exciting and enlightening product for their customers. But that's not really how the market is today, right? I'm not going to name names here, but you guys have search engines. You can figure it out. Exhibit A. A reasoning model gets upgraded. Amazing. The per token pricing is the same. What's not to love, you try it out, it uses three times as many output tokens, right? Exhibit B. A model gets upgraded, but it has an entire new digit, right? Whatever demarcation system that model family likes, it's brand new. It's 40% more than its predecessor, which is being deprecated in the next four months. These are real scenarios that we face at notion. All of you are nodding because these are common pretty much monthly now. But here's the problem. Are you growing 40% in that time period? Are you making 3x more revenue? No. So, how do you navigate the system? If you just auto upgrade your model and everything that you're doing, you're giving someone a bad deal. Either your customers or your investors, depending on how you charge and where you get your money, neither are good. Fortune 5 million companies have the capability to navigate this. They can hire large consulting teams, have durable teams on their own, and build expertise on how to navigate these trade-offs. Um, most people don't. everyone else has no ability to negotiate with leverage and they're stuck in these scenarios, right? Part of my job as that Anna Winter joke is to think about advocating for the Fortune 5 million, the non-fortune 500 companies that don't have the mass to have leverage and negotiate, but need to think about how. And I'm going to share some of the lessons that I've learned when I have kind of large amounts of traffic behind me that I think scale to those who don't. Um, this is probably less of a secret now than it was when I started giving talks like this maybe four months ago. Um, your supplier is your competitor. I know very few people who have convinced me that that's not true. Um, you will always be getting a bad deal on tokens with someone who builds them natively, right? Sometimes the cost of goods served is extremely different. you're basically they're serving a first-party product and then you're buying those tokens at a huge surcharge and then selling them again at another surcharge. Um, that's not really value you can defend. You're getting a really bad deal. And if you tie yourself to one provider, you have no exit. If you build an AI product that you've selling with this structure, you are crossing your fingers and hoping that you are a viable business. I do not encourage that. This is really interesting. Dylan in some analysis posted this. I think it's it says eight hours ago. It wasn't at this point. It was probably a month ago. Um they purchased a subscription plan and they just highlighted right how different what Frontier Labs charge customers for first-party products are versus what they sell. It's a bad deal. Don't play this game or try and let me know how you win. I don't recommend. Think about everyone else. Think about what that structure means and where you have expertise. I don't think that that's winning on the token economics. I think it's about product. It's about building data flywheels and understanding your customers better than anyone else. Understanding when you need capability, when you need low price, when you need latency improvements. I promise you, you don't always need what is usually the slowest but the most capable model out there. and then build compelling UI and orchestration. And I'll show you some examples of that to justify the cost on the bad deal tokens that you do resell.

</details>

---

### 模型能力与成本的精细化匹配：Frontier vs. Everyday 场景的抉择

在实际应用中，绝非所有任务都需要无脑推向最先进、但也最慢最贵的前沿模型。

Citadel 发布的行业备忘录指出，对于更广泛的社会与企业应用而言，**更简单的日常模型往往才是性价比最高的生产力增强途径**。这就需要我们对流量实施双轨制精细化分流：

* **前沿场景**（Frontier Usage）：诸如复杂的、跨文档的大规模数据分析，理应路由给 Claude Opus 等前沿模型来保证效果。
* **日常场景**（Everyday Usage）：诸如收件箱的简单分类或初步整理。如果在日常场景中继续盲目调用 Opus，无异于对客户和企业自身资金的双重剥削。

当前大模型市场本质上是少数巨头的垄断性竞争（Oligopoly），其定价往往不与模型实际能力的提升挂钩（类似于两家加油站为了封锁路段流量并排开设的博弈模式）。在这种情况下，应用层公司必须成为定义自身业务复杂度的专家，而不是被供应商的宣传牵着鼻子走。过度捆绑单一实验室不仅损害了客户体验，更是企业昂贵的决策失误。

基于此，Notion 坚定走**模型无关**（Model Agnostic）路线，推出了以**瑞士模式**（AI Switzerland Approach）为核心的智能模型分流框架。在该框架下，Notion AI 顶部设有**自动模型路由**（Auto Model），能够动态、自主地处理 Notion **75%** 的日常 AI 流量，这极大地增强了系统弹性，从根本上为客户打破了单一厂商锁定。

<details>
<summary>Original English Source</summary>

The job is not to train. I mean, some of you might be training the best model and I'd love to serve it and come talk to me afterwards, but most of you are not doing that. Stop trying to win that game and think about the best product that uses many models. Help your customers, help your team. Bet on the frontier, not on the lab. and we'll talk about what it looks like to do that. This cost per capability per second trade-off is actually really intense. Um, Citadel came out with this memo um a while ago, maybe two weeks ago. I loved it. The idea is that for the economy at large, simpler models might be the most cost-effective productivity augmenting pathway. They talk about this bifurcation on frontier versus everyday usage. I really believe that. And for every product, the definition of frontier versus everyday, the definition of saturated capabilities or model capability overhangs depends on your expertise on your product. No one can replace that. And not all traffic is equal. It is a huge miss to send all of these to the latest opus model. Some of these absolutely large scale data analysis when you do it on notion will recommend Opus, right? When you triage an email inbox, if we're charging you to do that on Opus, we're ripping you off and ourselves. Think about where your traffic patterns are. And then think about how Frontier Lab model providers are structured today. I mean, it's functionally an oligopoly, right? And that's fine because they're racing to the top. And I think the top is really hard and really important. This is not to say that products don't have a place for frontier difficult tasks. I want everyone to nod and understand that's not what this talk is about. Understand when you need those tasks and it's not everything. The problem with those tasks are is keep in mind how pricing is incentivized. You can figure out who these players are. Either you are the best model. Everything above what AI can't do today is your market. You can basically price it as high as you kind of want. If you're slightly behind that best model, all you need to be is like a dollar per million tokens cheaper and you have the rest of the market. You know that economic theory about gas stations where the best gas stations are the ones that are right next to each other because they cover east and west the most. Yeah. It's the same with model pricing, which means that price does not correlate with capability growth. So for this complex task, understand what capabilities you need, but be the expert on what complexity is. And keep in mind that who handles complexity changes. Um, oftentimes you'll see applied AI companies really be super outspoken on marketing with a specific lab. That's always kind of a red flag for me when they're not model agnostic because if you look at this graph, it basically shows that they're behind every month, right? the new model and the new model provider of the best Frontier capabilities change and if you hit your ride with one particular provider in exchange for for instance a larger discount um you're doing a disservice to your customers like half of the time right so really think about if that discount is worth not actually having a Frontier product and remember that that optionality is your leverage if you don't have the capability to walk at any point you are stuck. And again, I think that's probably the most expensive decision you'll make regardless of what discount you get or the engineering work to have model interoperability. One option to navigate this is stay model agnostic. Have different models and capabilities in your system so that at any point if pricing seems unfair or untenable, you are not out of business. Notion's auto model does this really well. We have state-of-the-art models available always. Um, but we also have an auto model there at the top that handles about 75% of our traffic. Right? We have the ability to switch between models in our product and we also offer it to our customers so that they have access to these models without vendor lockin. That's part of our AI Switzerland approach. You guys love taking photos of slides. This is the slide. Okay.

</details>

---

### 去中心化的模型互操作指南：开源权重与计算架构优化

构建多模型混合架构，首要的挑战在于解决**模型互操作性**（Model Interoperability）。

在跨越整个交互生命周期时，我们需要关注的不单单是表面的 Token 单价，而是计算**单位时间内、单位能力所消耗的实际综合成本**（cost per capability per second）。例如，Notion 在评估网页搜索合作伙伴时引入了 Parallel 的能力，虽然从单次调用延迟来看它可能不是最便宜的，但在复杂的跨页面搜索轨迹（Trajectory）演进中，其长尾综合表现更佳。

同时，**开源权重模型**（Open-weight Model，如 Kimi 系列、GLM 等）正在展现出惊人的生产力，并打破了前沿闭源模型的定价霸权。

* 它们不仅能够极高性价比地承接中度复杂任务，更在商业谈判中赋予了应用方极大的议价杠杆（Leverage）。
* 行业的技术收敛性表明，今天昂贵的前沿模型能力，在六个月后都会被普惠的开源权重模型无缝覆盖，提前对系统进行解耦配置是英明的战略选择。

此外，优化 Token 经济结构的另一个维度是**算力异构分流**，即坚持 **CPU 优先于 GPU** 的设计哲学。事实上，大量的软件流程并不需要笨重的大语言模型（LLM）与昂贵的 GPU 算力。例如，将 CSV 转换为 PDF，或执行高确定性的 SQL 检索和 Notion CLI 命令行工具交互。

Notion 近期推出的 **Workers** 架构正是针对此类离散、确定性的代码任务进行优化，使用高性价比的 CPU 算力作为第一响应层，从而彻底阻断企业因为算力错配而迅速滑向“Token 贫困”的风险。

<details>
<summary>Original English Source</summary>

Model agnostic playbook. This is how you do it. Build for multimodal. It is hard to kill the cache and switch models mid-transcript. I understand that we invest in that technology. It doesn't even have to be per thread. Just think about your harness as model interoperability. Think about the cost per capability per second, not just the tokens. Here's a great example. We posted this review when we um announced our partnership with Parallel as our web search provider. If you were to look at just latency of a single call or just cost, parallel might not be the cheapest. But if you have expertise in entire web search trajectories, you'll see how it differs. The granularity of this eval is what lets us make the best decisions for our customers because we understand all of the trade-offs on entire trajectories, not just single calls. Switch fast and often. I think we talked about that. And give them something back. That expertise on use cases is also very valuable to Frontier Labs. We find that our eval program partnerships actually help us a lot with Frontier Labs and is something that we can exchange instead of extraordinarily large commits and I don't think the discount is ever worth the loss in optionality. That's a perspective you can choose to keep or not. The second option is moderate tasks understanding open weights place there. um openweight models are really strong enough to handle these tasks and the possibility to RL on top of them has also kind of expanded the upmarket growth that they can cover. I view open weight models as basically lowering the barrier to entry on cost for our customers and they also give you negotiation leverage. So it's kind of a credible alternative that's putting that downward pressure on pricing that if there's an igopoly of two or three providers at the top is unavailable right now otherwise. I think Kimmy 26 was probably the first time that we really saw a model that outperformed 52, GPT 52, GLM 52 now is another 52 bombshell in the villa that also probably does best here. But it's no longer the case where openway models are good for just SFT on small tasks. Really think about without RL if they're capable enough for what you need. Um, and again, don't just think about external benchmarks. Be able to have expertise on your system. What are your tool errors? What's the actual latency that you need? Right? Here's an example of a benchmark that we posted. It's a little bit stale on purpose, right? But you get the idea. Philip at BE 10 this showed this slide once and I've stolen it ever since. Um, thank you. Are you here, buddy? Okay. Well, chat, hi. Um, well, he could come up and say it better, but the idea is that you don't have to be at the top, right? I'm not trying to make a case that open weight is the best model out there. Um, the case being made, however, is that um the gap gets covered eventually. So, if the tasks that you're having today are good enough, then in six months, they're probably covered by open weight. So, be prepared now. And the last thing is CPUs over GPUs.

</details>

---

### 软件工厂的治理与安全挑战：从“致命三要素”到代理编排

随着“软件工厂”模式的推进，未来六个月企业需要面对的核心阻碍并非大模型的技术上限，而是**系统治理**（Governance）与**安全性**（Security）。

Simon Wilson 指出了 AI 系统架构中极易诱发严重破坏的“**致命三要素**”（Lethal Trifecta）：

1. **拥有私有数据的访问权限**（Access to Private Data）。
2. **接触不可信外部内容**（Exposure to Untrusted Content，如来自第三方邮件、爬取的网页或外部 MCP 接口的信息输入）。
3. **拥有外部通信的能力**（Ability to Communicate Externally，例如在外发网络搜索请求中附带私有 Payload 数据）。

当系统设计得越自主（Autonomous）、且人类越倾向于放手由 Agent 独立执行时，这三个要素叠加产生的未受监管的安全风险就会以指数级增加。

如果企业仅仅是让昂贵的高级研发工程师去充当“软件工厂的保姆”（babysitting the factory），手动去调试、校验和兜底 Agent 产生的异常行为，这种模式便难以形成投资回报比（ROI）闭环。Notion 内部正在研发多 Agent 协作工作区，通过多代理编排（Multi-Agent Orchestration）将静态的 Markdown 重构为可交互、具有高自治能力的**活性文档**（Active Document）。

例如，在协作流程中，Claude Agent 可以根据任务上下文独立输出完整的开发 Spec，随后由专业处理客户诉求的 Decagon 代理协同补充数据，再由 Claude Code 在多源输入下自动开启 Pull Request。在提交前，PR 会交由 Codex 进行确定性的 Bug 扫码与静态分析。

在确保严格的安全治理边界和多模型快速互操作性的前提下，Notion 目前可以为每个独立任务缩短 **3 分钟以上**的工时，使软件工厂真正成长为企业级核心业务的可持续引擎。

<details>
<summary>Original English Source</summary>

Um, we've we've recently launched something at notion called workers. I don't think that the GPU is necessary for every job. A lot of the jobs that we have are actually serving um discrete pieces of code. Like you don't need an LLM to turn a CSV into a PDF. You don't need an LLM to talk to notion tool calls if we have a CLI. You definitely don't need an LLM to do deterministic SQL queries. This is where people become token poor very quick. And I think the last option here besides open weight CPUs and optionality is actually governance. Um there's a lot of AI governance. Um one is visibility. Um understanding who's using the data, understanding its maintainability and control. When you have model optionality, you can offer a lot more to your customers. Um here's an example of how that governance works in notion. So final tips again, think about architecture, think about open weight, and build value that transcends tokens. So we're going to depart Token Town. I know I said welcome to Token Town. We're going to spend the next 10 minutes really thinking about what to do next. So I think the challenge of the next six months doesn't have to do with capabilities. I think it has to do with security. Let's start there. There's this concept called the lethal trifecta. Simon Wilson, I think, crafted this. If you have access to private data, exposure to untrusted content, whether it be through ingestion, MCP, email, right? And the ability to to communicate externally, and that can include like payloads in a web search. The second you have that system, you're exposing risk. And in fact, the more autonomous your system is, the more unsupervised this risk is. I think that this is what builds valuable product, not just capability. Same with sandboxes and computers. We talked about this, but it really is something that builds better determinism in your product and also better token economics for your customers in multi-agent orchestration. Understanding what agents see and do and what persists. I think persistence of enterprise knowledge is something that's actually really not discussed enough. It's starting to be with some recent launches, you know. Oh, there is audio. So don't have your workflows look like this. And I think this is where most software factories are today, right? It's like actually your entire engineering time just spends time babysitting the factory, right? I mean, I get it. Ours started off like this. Agent orchestration is one of the most difficult tasks of making factories work. So okay, this is me telling Tay to tell people to buy notion AI. And the reason I included this slide is I am going to sell notion for a second. It's my job. Always be closing. Always be selling. Always be hiring. come find me. But I'm going to talk for a second about how notion does this today. We already have the ability to inspect tasks. And you can imagine any task that you look at um in a notion document. You can have Claude actually go ahead and scope out what you need. We've launched this manage agent capability today. So if I go ahead to the top of this task, I can actually ask Claude agent to scope out the task. Right? Ideally, it's working. Um, and you'll see it'll actually populate um an entire spec of what needs to be done. In this example, it's not ready. It's going to ask me a question. Keep in mind, this isn't a markdown file. This is an active document. Um, let's say I don't actually know the question and I go ahead and I ask my team um what to do. Imagine that you can kind of tag in your team into these systems. MJ's our PM. So in this example, she doesn't know. Usually she does, but multi-agent orchestration is important. Maybe Claude Code isn't the best at customer voice, but Decagon is, right? You can ask Decagon agents, we're proud partners of them as well, to collect the right data that you need. Okay, in this example, we think we know enough. We're going to go ahead and actually um iterate through some of this flow. I'm going to skip ahead a little bit. We asked our TL what we needed. He replied again. It's a collaborative file, not just a markdown. And we can have Claude actually go ahead and spin up the PR. Hopefully, this is looking a little familiar now. This is kind of the vision of software factories. It's what we're trying to host. Okay, Claude put up a PR. Maybe that's not enough. Um maybe I want to go ahead and ask Codex what it thinks. Great. Found two issues. You can think about this scaling in an actual factory. So today in notion, you're actually able to orchestrate these agents together and you're not committing to a lab. You're committing to the concept that AI is augmenting and automating what you do. This is real. I asked Rejieve if I could post this. This is how it works today internally at notion. Almost all of our polish and large feedback like this is actually coordinated um through our software factories both in terms of writing to the right teams and also having coding agents take the first step. Verscell does this as well from staging to shipping to closing. And we see massive ROI gains from our customers. That's over three minutes saved on a given task. Imagine that at scale. So I think we're trying our hardest to think about the factory lens. We cannot do this without optionality and we cannot do this without conviction that we understand what models are required for which tasks. It's really wild out there you guys. I get it. The market is really young. It's exceptionally opaque. It's moving fast. I'm super grateful for communities like AI engineer to bring us together and like talk openly about these things and how we navigate it. Um I think we owe it to all of our customers to get it right and to be critical thinkers about how we navigate this together. I'm chronically online fortunately. Um you can always DM me on Twitter, you can email me, you can find me after this. Um but thank you for yapping with me and thinking about this problem and have a good day.

</details>