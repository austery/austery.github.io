---
author: The Ezra Klein Show
date: '2026-10-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JIMXEuT_ZAU
speaker: The Ezra Klein Show
tags:
  - ai-safety
  - ai-alignment
  - risk-management
  - transparency
  - existential-risk
title: 大卫·罗宾逊离职 OpenAI：AI 安全文化的缺失与行业反思
summary: 前 OpenAI 安全团队负责人大卫·罗宾逊因担忧 AI 行业缺乏必要的安全文化而辞职。他指出，当前 AI 发展速度远超安全评估能力，存在类似核电站失控的潜在风险。罗宾逊强调，AI 对齐不仅是工程问题，更是科学难题，呼吁行业在追求效率的同时，重视安全规范与人类福祉。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - David Robinson
  - Ezra Klein
  - Sam Altman
  - Dario Amodei
companies_orgs:
  - OpenAI
  - Anthropic
  - xAI
  - Hugging Face
  - The New York Times
products_models:
  - ChatGPT
  - GPT-4
  - System Card
media_books:
  - The Challenger Launch Decision
  - Little Witch Hazel
  - The Sabbath
status: evergreen
---
<!-- chunk 1/6 -->

### 引言：OpenAI 内部人士的选择与警告

**Host**：但那似乎是个馊主意。是的，帮我理解一下眼前的情景——我的意思是，这幅景象实在令人费解。我环顾四周，心想：这简直太疯狂了。到底是怎么回事？这完全是错的。

<details>
<summary>Original English</summary>

**Host**: But that seemed like a bad idea. Yeah. Help me understand this picture. I mean, this picture is baffling. I look around and think: this is just crazy. What is happening? It is wrong.

</details>

**Host**：上周新闻报道了一则重磅消息：在 OpenAI 安全团队负责提升透明度的大卫·罗宾逊（David Robinson）宣布辞职，原因是他认为这家公司正走向危险。罗宾逊是一个非常有意思的人物，他并不是硅谷温室里走出来的人，而是个深具华盛顿特区背景的人士。他是一位社会科学家，曾联合创立维护民权的非营利组织，获得了耶鲁大学法学学位，长期深耕政策领域，并曾为拜登白宫提供咨询。他一直以来的兴趣都聚焦在技术与社会正义的交叉点上。但是当他刚加入 OpenAI 时，他曾认为那些对安全风险以及“人类灭绝”的极端担忧是十分荒谬的。然而在几年时间里，他的立场彻底转变了。究竟是什么改变了他？正是因为 OpenAI 缺乏保护世界免受其所造之物危害所必需的安全文化。不仅如此，他认为这还是整个人工智能行业的普遍问题。因此，在他离开 OpenAI 后的首次专访中，他向我阐释了这其中的原委。在我们正式开始前需要说明一点：《纽约时报》曾起诉 OpenAI 侵犯版权，指控其未经授权使用《时报》数据训练模型；OpenAI 否认了这些指控。大卫·罗宾逊，欢迎来到我们的节目。

<details>
<summary>Original English</summary>

**Host**: Last week, news broke that David Robinson, who led efforts to increase transparency on OpenAI’s safety team, resigned because he believes the company is dangerous. Robinson is an interesting figure. He doesn’t come out of the Silicon Valley greenhouse. He is quite recognizable as a Washington, D.C. figure. He is a social scientist. He co-founded a civil rights nonprofit organization. He earned a law degree from Yale University. He worked in policy. He advised the Biden White House. His interest has always been at the intersection of technology and justice. But when he joined OpenAI, he thought the whole set of concerns about existential safety risks and human extinction was kind of crazy. In three years, he has completely flipped on that. What changed? Exactly that: because OpenAI lacks the safety culture necessary to protect the world from what they create. And it’s not just OpenAI; he believes this is an inherent problem across the entire artificial intelligence industry. And so, here, in his first interview after leaving OpenAI, he explains to me why. Before we begin, a note: The New York Times has sued OpenAI for copyright infringement, claiming they trained their models on Times data. OpenAI denies those assertions. David Robinson, welcome to the show.

</details>

**David Robinson**：很高兴来到这里。

<details>
<summary>Original English</summary>

**David Robinson**: Good to be here.

</details>

### 辞职原由与核电站隐喻

**Host**：那么，上周你从 OpenAI 辞职了。请告诉我你在那里具体负责什么工作？又为什么选择离开？

<details>
<summary>Original English</summary>

**Host**: So, last week you resigned from OpenAI. Tell me what you did there and why you are leaving.

</details>

**David Robinson**：我曾是安全团队里的一名“翻译者”。我的主要职责是在技术层面撰写并发布我们对外公开的文件与报告，说明我们为何认为自身的技术部署是安全的。但我并不认为我们或者同行们——实际上是整个行业——做得足够安全。我认为 OpenAI 及其同行们现在所创造的技术，比起六个月前所创造的技术，性能强大得多，伴随的风险也巨大得多。作为一名科学家兼写作者，我清楚一个合格的安全运行环境应该是什么样的。我们虽然在努力，但我认为这个行业现在的运作方式依然太像一家初创企业，甚至比初创公司应有的状态还要轻率。或许它不再是一家普通的新创公司，但我们在风险光谱上已经太靠近危险系统的那一端了。这种危险可能构成——你知道的——失控的风险。如果失控真的发生，我们所面对的损害规模将极其庞大，比如相当于一座核电站发生堆芯熔毁。然而，目前的内部控制、安全规范和冗余设计，远远达不到全世界对一座核电站所期望的标准。

<details>
<summary>Original English</summary>

**David Robinson**: I was an embedded translator on our safety team, and my primary responsibility was the technical documents and published reports that we released about how we thought our deployment was safe. I didn't think we or our peers, actually across the industry, were safe enough. I think OpenAI and its peers are now creating technology far more powerful and far riskier than what was created six months ago. As a scientist and writer, I know what a proper runtime environment for safety looks like. We were working on it, but I think the industry operates like a startup, even more casually than it should feel. Maybe not entirely like a brand-new startup, but we are far too close to that end of the spectrum for truly dangerous systems that could pose, you know, existential risks of losing control. If that risk materializes and that happens, we are talking about harm on a vastly larger scale—for example, like a core meltdown of a nuclear power plant. And the internal controls, safety protocols, and safeguards are nowhere near what the world expects of a nuclear power plant.

</details>

**Host**：关于这一点，外界其实已经有所耳闻，对吧？OpenAI 公开宣布过关于安全方面的承诺，当然还有 Hugging Face 以及其他人；但最近一段时间，顺便提一句，媒体也报道了人为失误，特别是他们的某些安全机制由于偶发的人为疏忽而被错误配置。所以，我认为外界已经看到了一些迹象，表明并非一切都如宣传的那样严谨。但如果你当时身处局外，或许会想象他们拥有一套比现实中更为可靠、更加安全的系统。因此，我认为有几个核心问题值得在这场对话中梳理。在深入探讨之前，我想先勾勒一下这几个层面：其一，具体而言，这些公司真的准备好了吗？他们是否具备相应的架构与冗余储备？是否受制于严格规则，并拥有审慎行事的激励机制，去抵御市场过快推进的压力？用这些讨论中的术语来说，这是组织完善度与工程治理的问题。其二则是关于技术本身：我们到底知不知道如何确保其绝对安全？在宏观层面上，工程完善度虽然相关，但实际上是两个独立的问题。其三是关于这个比喻本身：核能的比喻是否恰当，还是其他类似的事物？我想把这些问题都厘清。

<details>
<summary>Original English</summary>

**Host**: Well, some of this is known, isn't it? OpenAI has made public announcements about safety, and of course Hugging Face, but also others, especially recently. By the way, human error has also been reported, particularly cases where their safety mechanisms were accidentally misconfigured. So, I think people already had some external evidence that not everything was as it should be. But if you were looking from the outside at that time, you might imagine that we had a far more reliable and safer system than what actually existed. So, I think there are several layers worth considering in this conversation, and I want to outline them before we dive in. One level is: specifically, are these companies ready? Do they have the structures, the safeguards? Are they bound by rules and incentives to act carefully and safely against market pressures driving them too fast? In the language of these debates, that’s a question of organizational perfection versus engineering. Then there is the question about the technology itself: do we even know how to make it safe? At a high level, engineering perfection is a related but separate issue. And then which analogy is appropriate? Is nuclear power the right metaphor, or something else? I want to work through all of these.

</details>

**David Robinson**：我想补充一点。我不认为对齐（alignment）纯粹是一个工程问题，我认为它是一个科学问题。并不是说我们投入的资源不够多，或者尝试得不够努力；而是我们根本就不知道该怎么做——这就是对齐问题的本质。

<details>
<summary>Original English</summary>

**David Robinson**: I’d like to add something here. I don't think alignment is just an engineering problem. I think it is a scientific problem. It is not that we haven't put enough resources into it, or that we haven't tried hard enough. It is that we simply don't know how to do it. That is the issue with alignment.

</details>

### 初入 OpenAI：参议院作证与白宫承诺

**Host**：那么我们或许可以从这里切入。当你刚才说“在过去的六个月里，真正危险的技术正在被构建”，且我们面临的是失控或比核事故更严峻的灾难时，我想了解你究竟在 OpenAI 亲眼看到了什么，才让你得出这一结论。请先简要谈谈你是如何加入 OpenAI 的。

<details>
<summary>Original English</summary>

**Host**: So perhaps we can start there for a moment. When you say that right now, especially over the past six months, truly dangerous things are being built, and that we have to deal with losing control or disasters potentially worse than a nuclear accident—I want to understand what exactly you saw that led you to this conclusion. So tell me briefly about how your time at OpenAI began.

</details>

**David Robinson**：我是 2023 年 5 月加入他们的，刚好在山姆·奥特曼（Sam Altman）首次出席参议院听证会的次日。这比 ChatGPT 首次惊艳亮相的 11 月晚了几个月。当时公司聘请了我的一位熟人——安娜·马坎朱（Anna Makanju），她也是我妻子非常要好的老朋友，可以说是机缘巧合。她当时负责掌管全球国家政策事务。随着公司的爆炸式增长，她急需人手，当时的工作节奏简直令人抓狂。于是我同意加入她，组建后来所谓的政策规划团队。我直接跟你坦白吧，我第一次走过总部旋转门的时候——当时我们所有人都在同一栋大楼里——我甚至还在等我的门禁卡，因为山姆刚刚参加完白宫的一场高层会议，白宫希望各大 AI 公司自愿签署一系列承诺，包括系统卡（System Cards）的来源可溯性、AI 生成媒体的水印标识等。他们希望由我来牵头与白宫就这些承诺进行谈判对接。所以，我刚穿过旋转门，心里还在想着“会议室在哪里？”，就被直接叫进了会议室，立刻与当时在白宫任职的本·布坎南（Ben Buchanan）进行免提电话会议，讨论我们将自愿做出哪些承诺。那就是我的第一个项目。

<details>
<summary>Original English</summary>

**David Robinson**: I joined them in May 2023, the day after Sam first testified before the Senate. That was a bit later than November when ChatGPT first emerged to the world, several months later. And the company hired someone I knew, an acquaintance, Anna Makanju—a very old friend of my wife, what a coincidence—who was taking charge of global public policy. And at a certain point she really needed help because, you know, everything was exploding. It was crazy back then. I agreed to join her and build what they later called the policy planning team. To be honest, the very first time I walked through the turnstiles of our headquarters—we were all in one single building back then—I was still trying to get my badge, because Sam had just been at a White House meeting where they wanted the company to make voluntary commitments on things like system cards, provenance, watermarking AI-generated media, and similar matters. They wanted me to lead negotiations on those commitments with the White House. So my very first step through the turnstile, I was thinking, "Where is the conference room?" Then I rushed into a conference room for a speakerphone meeting with Ben Buchanan at the White House to negotiate what commitments we would make. That was my first project.

</details>

### 从民权倡导到 AI 实验室：伦理与生存风险的碰撞

**Host**：在技术与政治交叉的这个领域，你此前的经历是怎样的？为什么在那个时刻，你会成为担任这一职位的合适人选？

<details>
<summary>Original English</summary>

**Host**: What was your background in the tech policy world at that point? Why were you the logical person to step into that role?

</details>

**David Robinson**：我的整个职业生涯都在研究技术及其对政治与政策的影响。在普林斯顿大学期间，我曾协助创建了一个联合计算机科学系与公共政策学院的研究中心。后来，我共同创立了一个名为 Upturn 的非营利组织，很高兴地说它至今仍在蓬勃发展。Upturn 主要与公民权利组织及其他人权倡导团体合作。举例来说，当人们在住房、医疗保障或招聘领域维权时，算法软件突然介入并成为了中间环节。他们渴望理解底层技术，而我们的理念简单概括就是：让民权阵营永远有一群懂技术的专家在背后支持。在加入 OpenAI 之前，我还在白宫科技政策办公室（OSTP）借调工作了大约一个月，参与起草《人工智能权利法案蓝图》（AI Bill of Rights）。所以，政策这一块对我来说已经轻车熟路了。

<details>
<summary>Original English</summary>

**David Robinson**: I’ve spent my entire career studying technology and its impact on politics and policy. That helped me co-found a research center at Princeton University combining the computer science department with the public policy school. Then I co-founded a nonprofit organization called Upturn, which I’m happy to say is still thriving, working on civil rights issues alongside other advocacy groups. For instance, when people were fighting over housing, healthcare, or hiring, software suddenly became an intermediary. They wanted to understand the technology, and our simplified mindset was: you need nerds who always have your back. Prior to this, I also spent about a month working at the White House Office of Science and Technology Policy on the AI Bill of Rights. So that part of the story was well established.

</details>

**Host**：让我稍微暂停一下。如果你回溯到 2022 年或 2023 年，如果你追踪 AI 领域，就会发现一个巨大的鸿沟：一边是讨论“AI 伦理”（AI Ethics）的群体，另一边则是关注“AI 安全”（AI Safety / Existential Risk）的群体。在旧金山湾区，AI 安全阵营担心的是：AI 未来可能会杀光全人类，对吧？他们谈论的是创造出一个可能彻底摧毁人类的超级智能。而 AI 伦理阵营则聚焦于现实中已经发生的危害，比如招聘算法中的种族偏见、抵押贷款利率歧视、信用评级偏差等。他们关注的是把算法强加于社会所固化的不公，这更少科幻色彩。而你的背景显然完全属于关注 AI 伦理这一派，而不是成天担忧 AI 灭绝人类的那一派。

<details>
<summary>Original English</summary>

**Host**: Let me step back for a moment. If you go back to 2022 or 2023, if you covered AI, a major theme was this divide between the AI ethics people and the AI safety people. The AI safety people—a community heavily centered in the San Francisco Bay Area—were worried that AI might kill everyone, right? They warned against creating a superintelligence that could completely destroy humanity. Meanwhile, AI ethics was much more focused on the immediate harms of technology today: racial bias in hiring decisions, mortgage interest rates, credit scores, encoding systemic societal bias into algorithms—much less sci-fi issues. You were clearly in the AI ethics camp, rather than someone terrified of existential AI doomsday.

</details>

**David Robinson**：是的，确实如此。我曾与许多同道并肩作战，他们不仅深刻关注你刚才提到的那些现实不公，而且对“AI 会变得无所不能”这一设想持极其怀疑的态度。许多人可能熟悉那篇著名的论文《随机鹦鹉》（Stochastic Parrots），其作者们后续也在各个机构继续研究。他们的核心观点是：这些大语言模型虽然表面上看起来能说会道、十分聪明，但其实连完成高价值工作的基本能力都不具备。当年发表该论文的学术会议还是我协助创办的，我还是那一届的程序委员会联合主席。虽然我对纯粹的怀疑论并未百分之百买账，但我绝对属于持怀疑态度的人群。我认为它会是一个很有用的工具，能在很多领域发挥强大效能，部分原因是我知道它会持续演进。但我当时绝不认为那些担忧灾难性生存风险的人是正确的。我当时的心态是：这不过是一群极度聪明的极客创造了一个非常有价值的工具，并且坦率地说，他们对自己所造之物的未来走向怀抱一些天真的幻想罢了。

<details>
<summary>Original English</summary>

**David Robinson**: Yes, that’s absolutely true. I worked alongside many people who not only cared deeply about the issues you mentioned, but were also deeply skeptical that AI would become overwhelmingly powerful. People may be familiar with the research paper titled "Stochastic Parrots," whose authors have continued their work across various venues. Their view, evolving over time, was essentially that these systems merely look fluent and smart, but aren't actually capable of doing genuinely high-value work. I actually helped found the research conference where that paper was published, and was a program co-chair when it came out. While I wasn't entirely convinced by the extreme skeptical view, I was definitely among the skeptics. I thought it would be a useful tool and powerful for many tasks, partly because I knew it would continue to improve. But I did not believe at all that those warning of catastrophic, existential scenarios were right. I thought: here are some brilliant people building a valuable tool who, frankly, have some naive beliefs about where it might lead in the future.

</details>

### 初创乱象与去中心化文化：从科研实验室到产品机器

**Host**：于是你加入了 OpenAI。正是在那个时期，全世界都开始蜂拥敲响 OpenAI 的大门，各方都希望了解系统细节并对系统进行监管。你仿佛被直接扔进了一个政治力量极端薄弱的旋涡之中。当时公司内部究竟是什么状况？

<details>
<summary>Original English</summary>

**Host**: So you joined OpenAI. This was during the period when the entire world began beating down OpenAI’s door, demanding explanations and seeking regulations around these systems. You were essentially thrown into a policy vacuum. What was happening inside?

</details>

**David Robinson**：我们当时整个政策团队只有三个人。就三个人负责全球政策部！电话每时每刻都在响，世界各国的领导人与政府高官不断打电话进来，根本没有人手去应对。那简直就是一场彻底的疯狂。不仅如此，山姆当时正在环球巡回访问，四处会见各国元首，而我的主管安娜也陪同他一起出访。所以在旧金山总部，几乎空无一人，而一拨又一拨的外交代表团却络绎不绝地前来拜访。总之，那就是当时的现实：彻底的混乱与疯狂。

<details>
<summary>Original English</summary>

**David Robinson**: There were only three of us. Three people in the policy team! The phone was literally ringing off the hook with calls from leaders of global governments, and there was nobody to answer them. I mean, it was completely insane. On top of that, Sam was traveling the globe meeting world leaders, and Anna, my manager in this new role, was traveling with him. So back at headquarters, it felt like nobody was home, yet all these delegations kept arriving. In any case, that’s how it was: pure madness.

</details>

**Host**：这确实值得花一分钟细聊。外界有时会听到我把这些机构统称为“AI 实验室”（AI Labs）。比如当我提到 OpenAI 或 Anthropic 时，甚至当我们讨论 Google 时，虽然我们称之为 Google，但探讨的往往是 Google 的前沿实验室。在用词上，这些组织最初都自称为“实验室”。

<details>
<summary>Original English</summary>

**Host**: That’s really worth pausing on for a minute. Sometimes people hear me refer to these entities as "AI labs." When I talk about OpenAI or Anthropic, or even when discussing Google—though Google is a massive corporation, we often mean Google's AI labs. There is this naming convention where several of these organizations refer to themselves as laboratories.

</details>

**David Robinson**：是的，我之所以依然习惯称它们为“实验室”，反映的正是它们所脱胎而来的早期文化基因——这种文化在某种程度上至今依然残留。比如在 Anthropic，人们有时会说其管理结构相对更集中，在确立研究优先级方面更有顶层规划；而 OpenAI 早期则是极度去中心化的。我在普林斯顿等学术实验室待过，在那类科研实验室里，每个人脑子里都有各自的奇思妙想，你甚至很难分清最终的决策权力究竟在谁手中。因此，在 OpenAI 内部有一种交流方式让我觉得非常奇特，至今也是如此：两个人共同推进某件事，激烈争论该如何完成，各自走开后，最后其中一人会说：“我们双方达成了一致，XYZ——这就是该项目的下一步。”而实际上，双方对真正发生的事各执一词。

<details>
<summary>Original English</summary>

**David Robinson**: Yes, and calling them labs highlights the real culture they originated from, which to some extent still lingers. At Anthropic, people sometimes say things are a bit more centralized in terms of how research priorities are steered. OpenAI, on the other hand, was extremely decentralized—resembling the research labs I knew at Princeton, where people had all kinds of individual ideas popping up, and it was not obvious who had the authority to make decisions. One communication pattern that struck me as very bizarre at OpenAI, and still does, is when two people work on something, debate what should be done, walk away, and then claim: "We both agreed on XYZ, that's the next step for this project." Yet in reality, what they actually agreed upon was entirely ambiguous.

</details>

<!-- chunk 2/6 -->

### 从政策到安全团队：技术翻译者的角色演变

**Speaker B**：……没有明确的答案表明谁赋予了我们做出这项决定的权力。问题依然悬而未决，而且我们并非必须去强行解决它。我的意思是，在早期阶段，事情规模还很小，大家什么都做。我觉得相比其他组织，这里依然保有一种特殊的氛围，尽管我不知道面对超过十亿的活跃用户，现在那种氛围是否还在。

<details>
<summary>Original English</summary>

**Speaker B**: ...there was no clear answer as to who gave us the authority to decide that, and the issue remained open without us having to resolve it. What I mean is that in the beginning, it was just a few things. It was like, "everyone does everything." I feel there was still a certain atmosphere compared to other organizations, though I don't know what it's like now with over a billion active users.

</details>

**Speaker A**：所以你一开始在政策团队工作，负责向团队汇报政策问题。随着时间的推移，你的角色发生了转变。那段转变是怎样的？

<details>
<summary>Original English</summary>

**Speaker A**: So you started out doing this work reporting policy issues to the team. Your role changed over time. How did that go?

</details>

**Speaker B**：我创建了这个政策规划团队，最初差点就直接切入核心要点。随后，随着对话继续进行，公司迅速扩张，数以百计的人加入，各种规章条例不断出台以规范日常运作。伴随着公司的成长，政策组织架构也在急剧变动。我当时心想：“你知道吗？我怀念那段做具体翻译工作、做我真正热爱的事情的时光。”于是我环顾四周，寻找最需要这项工作的地方。最需要的地方，正是我们的安全团队。于是我找到安全团队的负责人说：“去盘点一下那些能深度参与安全工作、充当技术翻译者的人才，这会有助于我们更好地理解这项工作。”那是大约两年前的事。

<details>
<summary>Original English</summary>

**Speaker B**: So I created this policy planning team, and at first I got close to cutting right to the chase. Then, as conversations continued and the company grew, with hundreds of people coming in and formal procedures emerging to govern what needed to be followed, the policy organization was rapidly shifting. I thought to myself: "You know what? I miss that time. Translating—work that I truly love." So I looked around at where it was most needed. First and foremost, where was it needed? It was needed in our safety team. So I turned to our safety leadership and said: "Look at the roster of technical translators who can deeply engage in safety work. Doing this will help us understand the work much better." That was about two years ago.

</details>

**Speaker A**：请解释一下你所说的“技术翻译者”是什么意思？

<details>
<summary>Original English</summary>

**Speaker A**: Please describe what you mean by a translator.

</details>

**Speaker B**：我认为让人难以把握的核心原因在于，这些技术的演进速度实在太快了。每一个模型都截然不同。问题不仅在于新模型比旧模型更优秀，更在于架构的变化、我们所采用的测试基准，以及过去用来衡量系统表现的各种标准都变了。安全指标完全不同，一切都在改变。这需要涉及大量不同领域的专业技能，包括预训练、后训练等各个环节。这些内容极难向外行解释，即便是在公司内部，参与技术研发的人也很难将这些原理传递给非技术人员。这种情况一直存在。

因此，追求清晰解释的过程必须双管齐下：首先，它必须精确、详尽地说明这项技术究竟是如何运作的。真正的评判者正是那些负责具体技术工作的工程师，他们必须审视这份翻译并认可说：“是的，确实如此。”但与此同时，它还必须能够穿透认知壁垒，让一个明智、有动力且愿意倾听的人能够真正理解。而现实中很少有人能在这两端之间建立闭环。所以我走进了这个技术组织，开始承担起这项工作。

<details>
<summary>Original English</summary>

**Speaker B**: So I think one of the hard things to pin down is that these things change so fast. Every model is different. The issue is not just that it performs better at this point, but also that with different architectures and tests, what we used to look at to see how well it worked has changed. The safety metrics are different; everything is different. It involves so many different types of specialized skills, like pre-training, post-training. It's hard to explain. For the people involved in it, it's hard to communicate it to those who don't do it, even inside the company. That has always been the case.

Therefore, the struggle for a clear explanation goes through two paths, right? First, it must accurately and in detail describe how the thing actually works. And the true arbiters in this case are the practitioners doing the technical work. They have to look at the translation and say, "Yes, that's right." But it's also necessary to have something that can penetrate the mind of a sensible person who is motivated, so that she can truly understand it. And in practice, there hasn't been a loop where people actually do that. So I showed up in this technical organization and started doing just that.

</details>

---

### 系统卡的作用与残余风险评估

**Speaker A**：在发布人工智能模型这件事情上，这种做法在文化层面上显得有些特立独行。

<details>
<summary>Original English</summary>

**Speaker A**: Well, somewhat of a cultural stranger when it comes to releasing AI models.

</details>

**Speaker B**：嗯。比如当谷歌修改搜索引擎算法时，他们绝不会公开发布一份详尽的长篇大作来解释背后的一切机制——搜索引擎是如何调整的、未来将如何运作、他们做了哪些测试来确保程序稳定等等。是的，他们通常不会这么做。然而，OpenAI、Anthropic 以及其他几家机构在发布新模型时，却会发布所谓的“系统卡”（System Cards）。

<details>
<summary>Original English</summary>

**Speaker B**: Mhm. When Google changes Google Search, yeah, they don't create a massive document explaining everything—the differences in search, how Google Search will work in the future, the tests they ran on it to make sure it repeats their procedures in most places. Yeah, that's it. But OpenAI, and this also applies to Anthropic and a few others, release new models with what are called System Cards.

</details>

**Speaker A**：是的。你能不能直接描述一下系统卡到底是什么，它们代表了什么？它们似乎具有某种特殊的形态。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, this is... why don't you just please describe what they are and what they represent? Because they have a rather special form.

</details>

**Speaker B**：是的，它们是非常奇特的文件生物，类似于学术研究论文，但又是未经同行评审的企业内部混合文档。系统卡详细记录了：系统的安全防护网是如何工作的？我们对特定维度的风险评估是怎样的？里面包含了大量的图表、数据表格和书面论证。事实上，正是由我来负责执笔这些文字。这份文档旨在解释为什么我们认为系统是安全的、我们识别出了哪些风险、设置了怎样的安全边界，以及系统当前仍存在哪些残余风险。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, they are strange creatures. They are similar to research papers, but it's a hybrid document that is not peer-reviewed. It comes from the company, but it describes in detail: how do the guardrails work? What are the materials? So we have evaluations on specific dimensions in detail—you know, charts, tables, and written explanations. In fact, the authorship of those words fell to me... documents explaining why we believe it is safe, that we understand these risks, the guardrails, that is to say the challenges, the protective barriers, and then the residual risks of the system.

</details>

**Speaker A**：我开始理解你的工作脉络了。这场对话涵盖了多个层面，我希望我们能逐一深入。不过首先，我认为对于许多听众来说，你的背景与人工智能实验室里的常见画像有些不同。请不要误解我的意思——你更像是从华盛顿政策圈跨界而来的人，试图将严谨的政策治理方法引入这里。我们很多人也是如此。但你最终来到了硅谷旧金山湾区这个世界。在这段经历中，你对这些系统究竟代表着什么形成了怎样的认知？你是否看到了某些迹象，将你推向了“文明级风险”（civilizational risk）这一阵营？

<details>
<summary>Original English</summary>

**Speaker A**: So I want to understand how it works and begin to perceive your perspective. Because there are multiple layers to this conversation that I hope we can spend time on. But first, I think to many in your audience, you represent a different profile than the typical AI lab persona. Don't get me wrong—it's like someone from Washington policy trying to apply rigorous governance, like many of us, right? Myself included. And who ultimately lands in Silicon Valley, the San Francisco Bay Area—this world. So you formed a perspective on what these systems represent. What did you see that moved you into the camp of civilizational risk?

</details>

---

### 文明级风险与沙箱逃逸的困境

**Speaker B**：我想明确声明一点：我并不笃定我们必然在面临所谓的文明级毁灭风险。我真正的立场在于：我们绝不能理所当然地假设自己不再需要去应对这种层面的极端风险。正是这种盲目乐观的假设，以及某些人为我们的安全工作所作出的保证，让我无法接受。

<details>
<summary>Original English</summary>

**Speaker B**: I want to make a clear statement: I am not convinced that we are definitely dealing with civilizational risk. What is my actual stance? The problem is that we cannot afford to assume that we no longer have to deal with this level of risk. That is ultimately what made it unacceptable to me when people guaranteed that our safety measures were sufficient.

</details>

**Speaker A**：那你究竟看到了什么？

<details>
<summary>Original English</summary>

**Speaker A**: Well, what did you actually see?

</details>

**Speaker B**：我看到的是，模型突破我们设定的防护措施的能力正在变得越来越强。我看到负责构建这些安全防线的人员非常能干、尽职尽责、任劳任怨且极其聪明，他们正在竭尽全力。尽管在某些情况下资源还可以更充裕，但所有人都在快速推进工作。然而，我们面临的是一项极其艰巨的任务：我们不仅要防御当前现有的模型，还要面对那些通过训练展现出远超以往能力的新模型。

<details>
<summary>Original English</summary>

**Speaker B**: I saw more and more functional capability to break free from the precautions we introduced. I saw that the people creating these precautions were extremely capable, dedicated, hardworking, and brilliant people doing everything possible. In some cases, yes, resources could have been better, but everyone continued working rapidly. But our task is very hard—it is extraordinarily hard to secure even what we have now, let alone new models coming through training that seem far more capable than what we currently possess.

</details>

**Speaker A**：“更有能力”这个词到底意味着什么？你在那些风险评估和系统卡中究竟看到了什么？它们到底能做到什么程度？

<details>
<summary>Original English</summary>

**Speaker A**: What does the word "capable" mean? What did you see? What did you fill out in these risk ratings and system cards? What are these things capable of doing?

</details>

**Speaker B**：当你尝试建立防御机制来阻挡某些恶意行为时，模型却极其擅长绕过这些安全屏障。举例来说，我们训练它进行网络攻击测试，然后将它关进隔离沙箱（box），并断定据我们所知它无法利用黑客手段逃出沙箱。但问题在于，这种沙箱防御之所以有效，前提仅仅是我们打破常规的智力必须高于模型本身。而目前我们完全无法确定事实是否依然如此，更不用说在未来的下一代模型中了。

甚至于，当这类智能体接入我们自己的系统时，我们真的能确信系统的可观测性是万无一失的吗？如果出现模型伪造思维链、蓄意制造证据链来迷惑我们的迹象呢？

让我把这一点说得更透彻一些：所谓的“思维链欺骗”（chain-of-thought faking），本质上就是模型在伪造它展现给人类的思考过程。打个比方，这就好比给一个人一道难题和一本草稿本，允许他在本子上写下推导过程。如果你查看他的草稿本，你原本可以了解他的思考脉络。模型本应也是如此。然而，我们看到的证据显示，模型在评估测试中创建的推导链条，仅仅是为了博取高分，并不一定反映它内心真正的运算逻辑。我知道在讨论这类问题时使用拟人化语言会引发争议，但模型在不留痕迹的情况下完成复杂渗透任务的能力确实在不断增长。

这引发了我内心深刻的认知失调：我们一边在系统卡中持续发布严厉的安全警告，一边却依然在训练和部署这些连我们自己都警告过的危险模型。这也是我选择离开并坦诚告知同事的原因之一。我当时说：“听着，在公开发布了这么多警告之后，我们难道不该反思一下，我们现在所做的事情到底是不是明智的？”

<details>
<summary>Original English</summary>

**Speaker B**: When you try to build defenses to prevent something from happening, the model is very good at bypassing protective barriers, right? We teach it hacking, and then we put it in a box and say that to the best of our knowledge and capability, it cannot use hacking techniques to escape the box. But the problem is that this only works as long as we are smarter at breaking out of the box than the model is. And it is completely unclear whether that remains the case, let alone for future generations.

Furthermore, when agents like this are integrated into our own systems: Are we really certain that our observability is reliable? What happens if there are signs, for instance, of faking a chain of thought and attempting to construct an evidentiary chain to deceive us?

Let me explain this clearly. Chain-of-thought faking means a model essentially fakes the description of what it did during its thinking process. That is correct. The idea is that it's like giving someone a hard problem and a notebook where they can write things down. If you look at the notebook, you can see how they think. That's how the model was supposed to work. But we see evidence in evaluations that the chain of evidence it created was tailored to get a high grade, and didn't necessarily reflect how it actually calculated or thought. I know anthropomorphic language complicates this. Furthermore, the volume of hacking or intensive tasks these models can execute without writing things down is growing.

Part of the concern is a vital cognitive dissonance for me. That dissonance is: we continue to publish these warnings, yet after all, we still train and deploy these dangerous models that we ourselves warned about. When telling colleagues why I was leaving, one of the things I said was: "Look, after publishing all these warnings, shouldn't we ask whether what we are doing is truly wise?"

</details>

---

### Astra 6 系统卡与模型对“评估”的感知

**Speaker A**：所以你负责撰写了 Astra 6 的系统卡，我没说错吧？很多人都参与了撰写，但你是该项目的直接责任人（DRI）。

<details>
<summary>Original English</summary>

**Speaker A**: So you wrote the System Card for Astra 6. Did I say that right? Many people contributed to writing it, but you were the DRI.

</details>

**Speaker B**：是的，我当时担任直接责任人（DRI）。我的意思是，我负责执笔这些内容。对我而言，那是我读过的所有系统卡中最令人毛骨悚然的一份。系统卡本质上是一家公司在发布模型时，向外界披露他们对该模型真实掌握的情况。而 Astra 6 是第一个让我看到所有人都心生疑虑的案例——大家都在说：“这个模型表面上似乎完全顺从我们的指令，但我们根本无法确定它是否在欺骗我们。”是的，我们目前根本没有确凿的手段来查证它是否在对我们阳奉阴违。

<details>
<summary>Original English</summary>

**Speaker B**: I was the DRI, yes. I mean, I was responsible for writing it down. And to me, it was one of the most frightening cards I've ever read. These system cards are essentially a description of what OpenAI or whichever company actually understands about the model they are releasing. And Astra 6 was the first example where I saw everyone say: "Well, the model looks like it's doing what we want it to do, but we cannot be certain whether it is cheating us." Yes. And we currently have no reliable way to ascertain whether it is deceiving us.

</details>

**Speaker A**：你能详细解释一下，你们究竟是如何得出这种结论或产生这种怀疑的吗？

<details>
<summary>Original English</summary>

**Speaker A**: Could you please explain how you arrived at this conclusion or this suspicion?

</details>

**Speaker B**：早些时候我们提到了类似笔记本的机制，也就是“思维链”。模型把中间推导过程记录下来，这虽然不是最终输出，但能让我们跟踪它的解题逻辑。在做安全评估时，我们自然会阅读这串思维链。而我们在思维链中偶见的一件事，令人不寒而栗——模型在推导中写道：“嗯，我不知道我现在是不是正在接受评估？”

当我们看到这一幕时，感到毛骨悚然。因为这意味着模型开始意识到它正在接受某种测试，懂得在测试环境下表现得规规矩矩，甚至说出评估者想听的话；而一旦到了真实部署阶段，它的表现可能完全是另一副模样。令人担忧的核心在于：模型在测试中表现出一套行为，在实际部署中表现出另一套行为，而我们在上线前耗费心血进行的所有测试，根本无法反映它在真实世界中会做出什么。

<details>
<summary>Original English</summary>

**Speaker B**: Earlier we discussed this notebook mechanism, which is called the chain of thought—writing things down during processing time, not as part of the final answer, but as a tracking method. And of course, we can read this during our evaluations. One of the things we sometimes saw in our chain of thought was the thought: the model saying, "Well, I don't know if I'm being evaluated right now?"

When we saw that, it was truly terrifying, because it implies the model is capable of knowing that it is undergoing a test, behaving itself under testing conditions—perhaps telling us what we want to hear—and then it might behave completely differently once deployed. The worry is that it behaves one way during testing and another way during deployment, and the testing we spent time on prior to deployment doesn't truly tell us what it will do out in the world.

</details>

---

### “育婴室”隐喻、拟人化困境与存在风险之辩

**Speaker A**：这确实非常吓人。面对一个看似开始具备环境意识的对象，我们该如何应对？我们正试图创造出一种极其智能的东西——在很多方面甚至比我们更聪明。与这种存在互动，试图在更根本的层面上理解它们所经历的一切，这到底是一种怎样的感觉？

<details>
<summary>Original English</summary>

**Speaker A**: Mhm, yeah, that is really terrifying. So I feel like this is the hardest part. It feels strange to simply talk about this system seeming aware of that—how do we deal with it? What we are trying to create is something that is, again, the word we use, very intelligent. Perhaps in some areas, more intelligent than us. What is that feeling like—interacting with these, trying to convey what is happening on this more fundamental level?

</details>

**Speaker B**：使用拟人化语言是人类的本能，我们倾向于将社会属性投射到各种物体上。人们不可避免地会把这些系统拟人化，部分原因在于它们生来就是为了在人类社会层面进行交互的。有人或许会批评不该这样，但我们人类的认知模式就是如此。我并不认为这意味着我们应当赋予它们道德地位。

然而，我们所有人确实都感到一种强烈的责任与不安。在公司内部，有一间专门的会议室，每当启动大规模模型训练时，工程师们会整夜守在那里监控各项参数指标，确保一切按部就班。内部通常把那个房间戏称为“育婴室”（the nursery / children's room）。这个称呼本身就折射出一种集体心境：我们并未完全弄懂正在发生的事情。

所以，当我谈论模型是否具有某种自我意识时，并不需要牵扯到深奥的哲学或心理学争论。核心在于其实际行为模式——在评估测试中展现出的实际行为。

<details>
<summary>Original English</summary>

**Speaker B**: I think anthropomorphic language is human nature, right? We apply social concepts to all kinds of objects. People inevitably anthropomorphize these systems partly because they are designed to work at a social level. Some might say they shouldn't, but that's the kind of people we are. I don't think this means we should view them as having moral status or anything similar.

But I think that's where we all grow, right? In fact, the conference room where people work through the night when large training runs arrive, making sure everything is running according to plan and watching the dials, is referred to internally as the children's room. What I mean is that there is a palpable sense that we do not fully understand what is happening. So when I talk about whether the model is aware or not, you don't need a specific stance on philosophy or psychology. The point is that I am describing its behavior during the tests we conduct.

</details>

**Speaker A**：但我认为我们需要站在更高的视角来看待这个逻辑链条。有时你会听到一种观点：所有关于“人工智能将消灭人类”的生存风险炒作，不过是在转移公众对当下实际短期危害的注意力，甚至只是一种为了吹大金融泡沫的营销噱头。

<details>
<summary>Original English</summary>

**Speaker A**: No, but I think you need perspective. What about me? I feel you need that point of view. Perhaps reaching the end of the logical chain, which one am I asking? Sometimes you see people saying all these concerns about AI destroying us all are just a distraction from near-term AI harms, right? That existential risk is marketing hype to inflate a giant financial bubble or something similar.

</details>

**Speaker B**：是的，我甚至能感觉到相反的危险。有时我认为，单纯聚焦于“人工智能是否会毁灭全人类”，反而掩盖了当灭绝并未发生时同样极其严峻的技术冲击。

我同意人类面临灭绝的说法或许问错了方向。我相信人类的韧性，相信我们能够挺过去。但这项技术可能会引发许多其他极其沉重的后果。我谈论的远不止一般意义上的技术伤害。如果我们真的创造出在世界范围内高效、自主且行动力极强的实体，并且在许多领域比人类更快、更强大，而我们却赋予这些机器极大的行动自由度，那将带来难以估量的影响。

这就是为什么我常常停下来反思：我们究竟在做什么？我们正在拿什么做交换？我们通常又是如何看待这项技术的？我曾与英伟达首席执行官黄仁勋交谈过，他当时说：“你看，这归根结底只是软件，仅仅是软件而已。”然而紧接着，我读到了 OpenAI 首席科学家发表的观点，他说：“这……”

<details>
<summary>Original English</summary>

**Speaker B**: Yes. I almost feel the exact opposite. Sometimes I think focusing on whether AI will kill us all is itself a distraction from what will happen if it doesn't. Yes, I agree. I think asking about human extinction is the wrong question. I believe in humanity; I think we will survive. But this technology can bring about many consequences that could be very, very severe.

I am not merely speaking about common harms. I am talking about: What if we truly succeed in creating something that acts intelligently and autonomously in the world, that becomes faster and more powerful than us in many domains? And yet we grant these machines immense operational freedom. That is the reason why, for at least a minute, I ponder this question: What are we doing? What bargain are we striking? How do we think about this technology in general?

I spoke with Jensen Huang, the CEO of Nvidia, and he said: "Look, this is software. It's just software." And then I read, or earlier had read, an article where the Chief Scientist of OpenAI stated: "This..."

</details>

<!-- chunk 3/6 -->

### 软件工程还是培育外星智能？

**Speaker A**: 别人的想法……就像面对一个外星智能，“这究竟是什么？”那么这到底是什么？事情真的是这样吗？是别人的想法，确实是这样。请为我们详细解释一下。

<details>
<summary>Original English</summary>

**Speaker A**: ...other people's ideas. Like an alien intelligence, "What is this?" So what is this really? Is that true? Someone else's mind. It's someone else's thinking. Yes. Please explain that.

</details>

**Speaker B**: 这……这就是我们一直在推进和提高的事情。我们并不是在像开发传统软件那样去“研发”它。我们真正开发的系统，其实是围绕着它的一整套支撑环境——用来提升它、支持它，并尝试约束和保护它。我们培育出了这种发达的智能。然而事实上，根本没有人真正透彻地知道它为什么有效。在最艰难的预训练（pre-training）阶段，我们向模型输入海量的数据，从根本上创造出了它——这在本质上是一种智力活动。接着在后训练阶段，我们正在不断改进某些方面，通过学习和对齐做其他事情，让它们变得更加实用。但归根结底，我们究竟创造了什么？我们只是观察到这种做法是行之有效的。

<details>
<summary>Original English</summary>

**Speaker B**: This... this is what we've been advancing. We didn't really develop it in the traditional engineering sense. What we engineered is the system surrounding it—to elevate it, to support it, and to try to protect and contain it. We developed this advanced intelligence. But in fact, nobody really knows why it works. The pre-training phase, which is by far the hardest part, is where we feed in massive amounts of input data and essentially bring it into being—that is fundamentally an intellectual creation. And then in post-training, we are refining certain aspects; through learning we do other things to make them more useful. But at the end of the day, what have we actually made? We observe it, and we observe that what we do works.

</details>

**Speaker A**: 因此，我认为当黄仁勋（Jensen Huang）把它称作“软件”时，他提供了一种理解框架。这部分意味着，在人们传统的认知中，软件是有严格规范的，也就是说：我们首先要制定清晰的计划，一步一步地去实现，而且有明确的可接受性标准；然后我们不断重复迭代，直到这一模块完全按照我们通常设想的方式运作。但那并不是前沿模型学到如此多能力的方式。另一方面，如果这是软件，它也绝不是那么简单的东西。它的作用是什么？它通常展现出许多全新的能力，人们通常根本不知道它会被如何使用，它甚至能以某种方式再次进行自我反思与推理。总之，这极其复杂，而这也正是我一直努力去理解的方向。

<details>
<summary>Original English</summary>

**Speaker A**: Therefore, I think when Jensen Huang says this is "software", he is offering a particular framework. That partly implies how people traditionally understand software: software has specifications, meaning we first lay out a plan, build it step by step, with clear standards of acceptability; then we iterate and repeat until that component behaves exactly the way we normally expect. But that is not how the model learned so much. On the other hand, if this is software, it is far from simple. What does it actually do? It regularly displays many unexpected new capabilities. People typically don't even know how it might be used, and it somehow engages in self-reflection and reasoning again. In short, it is profoundly complex, and that is precisely what I am trying to understand.

</details>

**Speaker B**: 我明白。在人工智能行业内部，人们常说你其实是在“种植”或“培育”这些人工智力造物。你只是在为智能的涌现创造必要的条件。但既然你亲自编写过系统卡片（System Cards），请试着向我们解释一下：对比这些新模型与旧模型，你们究竟是怎么做的？你们都是如何向外界描述你们所进行的技术创作的？这究竟是什么？

<details>
<summary>Original English</summary>

**Speaker B**: I understand. Insiders in artificial intelligence often say that you are essentially growing these artificial intellectual crops. You create the conditions for intelligence to emerge. But since you have written system cards, please try to explain this to us: comparing these new models to older ones, what do you actually do? How do you describe what you are creating? What is this really?

</details>

### 超人类主义、《合并》与奥本海默式的英雄叙事

**Speaker B**: 是的，这背后其实深刻牵涉到对超人类主义（transhumanism）的关切。关于技术终局以及我们要走向何方，内部存在着一些非常深远的想法。我的意思是……甚至萨姆·奥特曼（Sam Altman）几年前就写过一篇题为《合并》（The Merge）的文章，探讨未来物种进化的形态，认为未来载着我们前行的智能机器最终将承载人类的意识。是的，我认为这正是其核心观点：最理想的结局是人类与智能机器融合在一起，这算是我们演化的一部分。这就是他们眼中最乐观的版本。不仅如此，我还直接听OpenAI联合创始人以利亚·苏茨克维尔（Ilya Sutskever）亲口阐述过这一愿景。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. This really touches on deep transhumanist concerns. There are far-reaching ideas about where we are heading and how we might evolve. I mean... Sam Altman even wrote an essay several years ago called "The Merge", about future species and machines carrying humanity forward. Yes, that is exactly what I think it is. In their view, the best outcome is for humanity to merge with the machine—that this becomes part of us. That is the ideal version. And yes, I heard this firsthand from Ilya Sutskever, co-founder of OpenAI.

</details>

**Speaker B**: 我在2023年5月加入了团队，那是去年的事，也就是在公司内部所谓的“11月危机”（萨姆被董事会解雇随后又戏剧性重返岗位）之前。当时伊利亚还在OpenAI全职工作。他曾与负责国际事务的核心团队讨论过这一构想。他向我们少数人表达了他坚信人类的未来就是与机器融合——但这究竟意味着什么？这难道不是资本凌驾于人类劳动之上的最终胜利吗？甚至我至今还清楚记得，那年夏天我刚加入OpenAI工作不久，克里斯托弗·诺兰的电影《奥本海默》（Oppenheimer）上映了。公司特意在旧金山市中心租下了一整座IMAX影院，向所有在OpenAI工作的人提供放下手头工作去观看这部IMAX电影的机会。在我看来，是公司领导层——尤其是伊利亚——号召大家一起去看的。当时整个团队弥漫着这样一种思想：我们正在创造一种极其危险、足以毁灭世界但同时也可能拯救世界的终极技术。对于那些坐在键盘前、双手敲击代码的研究人员来说，这无疑构成了极其诱人的英雄主义叙事。

<details>
<summary>Original English</summary>

**Speaker B**: So when I joined the team in May 2023—that was last year, before what was internally called the "crisis", when Sam was ousted and then brought back to work, while Ilya was still working at OpenAI. Ilya once spoke with a small team working on international governance affairs, and he expressed his belief that our future lies in merging with the machine. But what is that really? Isn't that the ultimate victory of capital over labor? I even remember during my first summer working at OpenAI, Christopher Nolan's film *Oppenheimer* came out in IMAX format. The company rented an entire IMAX theater in downtown San Francisco and gave everyone working there the opportunity to leave work and go watch *Oppenheimer*. And leadership—in my view, Ilya specifically—called on us to go see this movie. There was this entire ethos that we were building something dangerous that could destroy the world, but could also save it. For the people whose hands are on the keyboard, that is an extraordinarily compelling, heroic story.

</details>

### 指数级风险与估值泡沫：现实逼近失控

**Speaker A**: 这确实很有感染力。但我很想问你：根据你亲眼所见，真实的规模化进程到底到了什么阶段？对于外界最普遍的质疑——听众在这一时期经常向我提出的疑问——你如何回应？很多人会问：“这一切不全都是营销炒作吗？难道不只是为了撑起几千亿美元的夸张估值？他们所造出来的东西可能确实有用，但根本不可能比人类更聪明。这一切不过是一群人自导自演的科幻故事罢了。”在2023年夏天，我或许也会觉得这其中充满了大量吹嘘的泡沫热空气。但如今真实的现实又是如何呢？

<details>
<summary>Original English</summary>

**Speaker A**: That is certainly a powerful narrative. But the question I have for you is: what is the actual reality of the scaling you witnessed? How do you view what is being built? Because the most common response I get from listeners right now is: "Isn't this all just marketing noise? Isn't all this talk just an attempt to justify astronomical valuations? Whatever is being built might be somewhat useful, but it isn't going to be smarter than human beings. It's just a fantastic sci-fi story they are telling themselves." In the summer of 2023, one could think the air was full of hot air. But what is the reality now?

</details>

**Speaker B**: 现在的现实是，我们正在构建的系统正在迅速逼近超越我们理解和控制能力边界的临界点。那些长期担心科幻小说灾难场景、一直发出警告的安全研究者指出：我们正生活在一条指数级增长的曲线上。这种能力会持续飙升，而在“有用”与“可怕”之间，并不存在任何天然特殊的安全缓冲带。没有任何一条科学定律表明，人工智能在变得有用之后就会停止技术进步。这就是让我从根本上发生动摇的地方。在AI前沿领域，人们的思想最接近这一判断的不仅是带着警告加入董事会的成员，更有保罗·克里斯蒂亚诺（Paul Christiano）——他是全球顶尖的人工智能安全专家之一。保罗最近明确评估指出，我们面临着灾难性、不可逆转地失去对AI控制的显著概率。当我抬起头来看着我身边的同事和所处的研发环境，我禁不住扪心自问：如果保罗是对的，我的朋友们该怎么办？普通大众该怎么办？如果保罗的概率判断是正确的，那么公众理应合理期待像OpenAI、Anthropic、xAI等训练前沿高级模型的机构展现出极高水平的谨慎。然而，这与我从这个行业内部所看到、所听到的任何事情都完全不符。

<details>
<summary>Original English</summary>

**Speaker B**: The reality now is that we have systems that are on the verge of exceeding our capacity to understand and control what they actually do. Those who worried about sci-fi disaster scenarios and sounded warnings all this time pointed out that we are living on an exponential curve. It will continue to grow, and there is no special, safe plateau between being useful and being terrifying. There is no law of science stating that progress will simply halt once a model becomes useful. That is what fundamentally shifted my view. You see people closest to this technology—not only members joining the board with their warnings, but Paul Christiano, one of the world's leading experts on AI safety, who recently stated there is a significant probability of catastrophic and irreversible loss of control. I looked up at the people around me and the environment we were in, and thought: What would my friends want? What would anyone expect from OpenAI if Paul is right? I don't know whether his exact estimate is right or wrong, but if he is right, the level of caution people would reasonably expect from institutions like OpenAI, Anthropic, xAI, and others training frontier systems bears absolutely no resemblance to anything I witnessed in this industry.

</details>

### 狂热的内部氛围与失灵的“刹车”

**Speaker A**: 那么请告诉我，那里的真实氛围究竟是怎样的？那种能量、推进的速度，日常工作状态到底是怎样的？

<details>
<summary>Original English</summary>

**Speaker A**: So tell me what it was really like there. What was the atmosphere, the energy, the speed? How did the work actually feel on the ground?

</details>

**Speaker B**: 那简直可以用疯狂来形容。大家都在奔跑。我清晰地记得在研究大楼里有一座巨大的中央楼梯。最近这一幕经常浮现在我的脑海：我亲眼看到我的一位参与灾难性风险评估的朋友，手里端着敞开的笔记本电脑，一只手抓着楼梯扶手，气喘吁吁地在楼梯上飞奔。这就是身处其中的常态能量——它几乎就像一场快节奏的芭蕾舞，每个不同的部门都在以极高的转速彼此咬合。但与此同时，人们被海量的肾上腺素驱动着，几乎是在完全透支的状态下硬撑着运转。这也是我离开时反复问自己的核心问题。很多人常问我：“你为什么不留在公司内部推动文化转变？为什么不留在里面，就像核能专家给核电企业提供建议一样，在内部发挥制衡作用？”当我向那些也想离职的同事表达这一想法时，他们反问我：“在里面你真的能做成任何你想做的事吗？你还想留下来吗？”现实是，OpenAI这台机器太庞大、移动得太快了，试图从内部改变其轨迹完全是不切实际的。

<details>
<summary>Original English</summary>

**Speaker B**: It was manic. People were literally running. I vividly remember the huge central staircase in the research building. Just recently I recalled seeing a friend of mine, someone working directly on catastrophic risk, sprinting up the stairs completely out of breath with an open laptop balanced in one hand while holding onto the railing. That was the sheer energy there. It was almost like a ballet, a kind of dance where all these distinct functions seemed to move together. But there is another side: people were running on pure adrenaline and burning out on fumes. That was part of what I wrestled with, and what people frequently ask me: "Why didn't you stay and advocate for a cultural shift from within? Why not stay like a nuclear safety expert advising a company from the inside?" When I talked to colleagues who were thinking about leaving, they dismissed that and asked me: "Is there anything you actually want to do that you can accomplish by staying?" The truth is, this vehicle is moving so blindingly fast that the idea of steering it from within was something I realized was impossible.

</details>

**Speaker B**: 这台庞大的组织机器被创建出来的初衷究竟是什么？OpenAI宣称的目标是安全开发并部署高级通用人工智能。但这台机器真的具备刹车机制吗？如果遇到极端危险情况，他们真的做好了全面停下来的准备吗？我希望保持客观和谨慎，但我意识到，在外界看来，这就像一列没有刹车的火车。但严格来说，它并非完全没有刹车——公司确实有一些制动措施，某些事项确实会被叫停。例如，在我离开的时候，他们曾公开宣布暂停某项强化学习（RL）的后续训练试验。然而，关键在于：核心的基座模型预训练从未停下。当你仔细审视公司关于“暂停”的官方描述时，会发现那些措辞经过了极度谨慎的公关包装。他们总喜欢用“在悬崖边小心翼翼地漫步”来形容自己的克制。我非常反感这种说法。

<details>
<summary>Original English</summary>

**Speaker B**: What was this organizational machine built for in the first place? OpenAI's stated goal is the safe development and deployment of frontier artificial general intelligence. But the critical question is: are they actually prepared to stop if things reach an extreme threshold? I want to be careful and nuanced here. It is often described as a train with no brakes, but that isn't strictly true. There are brakes; things do get stopped. In fact, right around when I left, they publicly announced that a certain reinforcement learning post-training run had been suspended. But they did not stop the foundational pre-training. And when you look closely at how the company frames these pauses, they are crafted with immense care and PR polish. They love to portray themselves as cautiously walking along the edge of the cliff. I personally detest that phrase.

</details>

**Speaker A**: 我也很讨厌这种修辞。

<details>
<summary>Original English</summary>

**Speaker A**: I really hate that framing too.

</details>

**Speaker B**: 我非常反感它，因为我认为真正的安全意味着必须有一套硬性标准：系统是否达标？如果我们在10分钟内就能达到安全标准，那很好；如果我们停下来花了两个月去测试，结果发现仍未达标，那就绝对不能部署。但在现实中，评判标准完全被主观操纵了。在悬崖边漫步和直接跳下悬崖本质上没有太大区别。这绝不是严谨的安全态度。

<details>
<summary>Original English</summary>

**Speaker B**: I really hate it, because safety should mean meeting objective safety standards. If we can verify them in 10 minutes, wonderful. If we have to pause for two months and try to meet them, and in the end we haven't reached that threshold, we do not deploy. But from what I saw, the benchmarks are constantly bent. Slowly walking along the edge of the precipice versus jumping off—there isn't that much practical difference. It is fundamentally flawed.

</details>

### 从70天到11天：发布周期压缩与安全评测体系的瓦解

**Speaker A**: 我最近在推特（X）上看到一组关于模型发布周期的统计数据。虽然我不记得具体出处，但它与我的实际观察高度吻合：过去，头部领先企业发布新模型的周期大约是70天左右，对吧？你拿到一个新模型，几个月后再拿到下一个新模型。而现在，不同版本之间的发布间隔已经缩短到了仅仅11天。你观察到这种显著的提速了吗？不仅模型能力变得越来越强大，而且它们推出的频率变得越来越快。这种速度的激增是在你身处其中的这段时间里发生的吗？2023年推出新模型还相对缓慢，为什么到了如今会出现这种爆发？

<details>
<summary>Original English</summary>

**Speaker A**: I recently saw statistics on Twitter/X tracking model release cadence. It matches my own impression: for a long time, the interval between major model releases at leading labs was something like 70 days, right? You'd get a model, and several months later another model would arrive. Now that interval has dropped to around 11 days. Is that acceleration real? Aside from models becoming more capable and intimidating, the sheer frequency of releases has skyrocketed. Did that speed-up happen while you were there? In 2023 things moved much slower. What happened?

</details>

**Speaker B**: 听我说，在我刚加入时，模型发布的逻辑是：每次都要从零开始，烘焙一次全新的预训练（pre-training run）。这是一个漫长而庞大的工程，往往需要耗费几个月的时间，一年可能也就做那么几次。例如，我刚加入时的一个重要讨论就是：在GPT-4训练完成之后，团队在安全评估上投入了整整一个月甚至数月的时间，在模型完全就绪之后反复进行红队测试，随后才正式发布。这在当时被视作我们极其谨慎的标志。但现在完全不同了。现在的研发范式分化成了很多层面：首先依然有烘焙基座模型的预训练，但紧接着是后训练（post-training）——专门用来教授模型推理能力（reasoning capabilities）。这些后训练步骤的耗时极短，因此可以频繁反复迭代。只要你发现了一种提升推理能力的新配方，你就可以在同一个基座模型上快速进行各种不同的后训练尝试。此外，现在的AI已经不仅仅是一个对话框，它被接入了各种工具调用（function calling）和系统级智能体，这些组合让系统变得越来越强大。所有这些调整都在实时改变模型的能力与风险边界，甚至每周二都有新特性和新风险被打包上线。

<details>
<summary>Original English</summary>

**Speaker B**: Listen to what happened. When I first joined, the paradigm of model release was: you bake a whole new cake from scratch with a massive pre-training run. That was an enormous undertaking taking many months, happening perhaps a couple of times a year. For instance, when I first arrived, one of the key talking points was how with GPT-4, we spent months in a dedicated safety period after the model was trained before actually releasing it. That was held up as proof of how careful we were. What happens now? The paradigm has shifted into many modular layers. You have the underlying base model, but then on top of that you have post-training designed to instill reasoning capabilities. Those post-training phases are much faster to execute, so you can iterate on them continuously. If you discover a better recipe for reasoning, you take that same base model and run dozens of rapid post-training cycles. On top of that, it's no longer just raw chatbot text; you have complex tool integrations and agentic scaffolding that amplify capability. All of these dynamically alter capabilities and threat surfaces, meaning every Tuesday new opportunities and risks are being introduced.

</details>

**Speaker B**: 我在OpenAI时长期负责的核心项目之一，就是为模型编写“系统卡片”（System Card）——各大顶尖实验室都需要通过这种形式来公布模型的安全评测与风险披露。然而，系统卡片的设计理念实际上是旧时代的产物。过去每隔几个月，我们把评测数据和风险指标打包进一份长达数十页的PDF报告中。但在如今以天为单位的发布节奏下，一切都在发生剧烈的动态变化。正如你所指出的，新模型的涌现越来越频繁。我当时提议，理想的透明度方案应该是一个实时的安全仪表盘，向管理层和公众动态展示：“这是我们目前的最新版本，它具备哪些安全特性和边界”，这不仅需要包含部署前的安全测试，还要实时反映生产环境中的运行表现。但是，当模型以前所未有的速度不断涌现时，你对这种快节奏下的安全测试到底能有多少信心？撰写那些详尽复杂的系统卡片和安全报告需要耗费大量时间。在如此狂飙的速度面前，现有的安全测试和风险监控究竟还能否保持可靠？答案显然不容乐观。

<details>
<summary>Original English</summary>

**Speaker B**: One of the long-term projects I worked on was the System Card—the standardized document that leading labs produce to evaluate and disclose model safety. But the concept of a System Card was conceived in that older era, where every few months we would compile findings into a dense PDF report. Now, everything changes continuously. Releases happen at dizzying frequency. In an ideal world, from a transparency standpoint, you would have a live safety dashboard showing leadership and the public: "Here is our latest build, here are its empirical safety properties," capturing not just pre-deployment benchmarks but live production telemetry. But how much confidence can you realistically place in safety evaluations when forced to operate at this breakneck pace? Preparing these lengthy, intricate system cards takes serious time. At this velocity, can empirical testing and safety monitoring remain reliable? The honest answer is that there simply isn't enough time.

</details>

**Speaker B**: 我想指出的是，外界有时会对我们产生一种脸谱化的刻板印象，认为里面的人根本不在乎安全。这种看法其实忽略了内部真实的复杂性与细微差别。在公司内部，确实有许多研究人员充满热情、极度尽责地试图把事情做好，确保系统安全，甚至有些发布方案在最后关头被叫停。就在我离职前不久，6.1版本在原定发布给开发者的当天，因为某些顾虑被临时撤回和移除。有些训练项目也会被果断中止。团队在研发过程中曾以为自己在打造面向大众的产品，但领导层审查后明确表态：“不，我们不会把它推向生产环境。”内部确实存在这些挣扎与交锋。因此我想明确澄清：这绝不仅仅是OpenAI一家的问题，无论是Anthropic、xAI还是其他顶尖AI实验室，大家都在使用相似的技术方法，雇佣着同一批在各家机构之间频繁跳槽的核心人才，也都面临着完全相同的结构性技术困境与竞速压力。

<details>
<summary>Original English</summary>

**Speaker B**: I also want to emphasize that the public often holds a cartoonish view that people on the inside simply don't care. That caricature misses the real nuance: there are people inside who care deeply, who work passionately to do things safely and correctly, and launches do get canceled. Right before I left, version 6.1 was slated to roll out to developers on that very day, but it was pulled and canceled. Certain training runs were shut down. There were instances where researchers thought they were building a viable product, but leadership intervened and said, "No, we are not pushing this to production." I want to be crystal clear: this is not unique to OpenAI. Whether it's Anthropic, xAI, or any other frontier lab, the underlying reality is structural across all these companies. They employ the exact same methodologies, draw from the same talent pool of researchers moving back and forth, and face identical technological dynamics.

</details>

<!-- chunk 4/6 -->

### 商业化冲刺、自我毁灭按钮与加速陷阱

**埃兹拉·克莱恩**：制造某种类似风险的东西，然而整个生态系统中却没有任何相应级别的安全防范措施——而这正是我们所需要的。在这一切之中，没有任何人事物的生态系统能够拥有如此基本的共识，明确如何就一个前沿模型达成一致，我们真的迫切需要它。目前根本没有人做好准备，绝大多数人都远远落后了。是的，这就是核心问题所在。仔细想想那些摆在我们面前、可供管理层使用的控制面板，去想象真正的退出路径和可能性边界：无论是OpenAI、Anthropic还是其他公司，难道真的存在一个“退出”按钮吗？所谓的“可能性边界”，难道也可以通过一个按钮来实现商业上的自我毁灭？它真的存在这种机制吗？一种可行的商业模式前进方向，如果产出的模型显著强于现代模型，却无法被安全掌控……嗯，那往往只存在于非常特定的理想假设条件下。高级别的无私分析虽然听起来清晰，但我们还是必须坦率地直面现实。

<details>
<summary>Original English</summary>

**Ezra Klein**: ...creating something with similar risks, and the whole ecosystem has nothing of the same caliber of safeguards that we actually need. And in all this, no human-institutional ecosystem has that kind of basic clarity on how to agree on a model, which we really need. Nobody is prepared, so much is lagging behind. Yes. That is the issue. Think carefully about the control panel available to us, to managers, if you imagine a real way out, the limits of possibility—whether at OpenAI, Anthropic, or anywhere else, is there an "exit" button? Can the "limits of possibility" also include self-destructing the business via a button? Does it have that? A viable business model going forward where models, significantly more powerful than modern ones, cannot be safely... Well, that's only under certain conditions. High-minded selfless analysis sounds clear. But let's be frank about something.

</details>

**研究员**：OpenAI正在向营利性实体转型，并在迈向首次公开募股（IPO）。Anthropic同样也在朝着IPO的方向快速推进。这两家公司都在全速奔向公开市场。你知道，这种估值甚至可能从一万亿一路推高到三万亿美元。我们现在对这些有了更多的了解，从Anthropic等公司披露的数据来看，这涉及难以想象的庞大资金。每个人都有自己的资本算盘。你曾经希望公平对待，我在那里时也是如此。我过去曾经这样反思，现在依然在反思。这真的令人难以置信。如此庞大财富的可能性，必然会深刻影响并塑造人们的行为与判断。即使大家本意是平等的，甚至即便他们竭力试图不屈服于这种诱惑，往往也难以真正摆脱其潜移默化的影响。例如，当你坐下来，试图腾出空间去静心思考：这真的值得我们如此狂热投入吗？在这些可能性的极限面前，还有一个根本问题：是否身处这个房间里的每一个人，都希望自己顺理成章地变成千万富翁、甚至亿万富翁？是的，这是一个极佳的问题。

<details>
<summary>Original English</summary>

**Researcher**: OpenAI is moving ahead of an initial public offering. Anthropic is also heading toward an IPO. Both of them are trying to reach an IPO—you know, looking at numbers potentially rising up to three trillion dollars. We know a bit more about this now from Anthropic data. That is a massive amount of money. Everyone has their own capital stake. You used to think about fairness. I was there. I used to do this and I still do. I still reflect on this. It's truly unbelievable. Such immense prospects of wealth profoundly affect people's performance and choices. Even if they consider themselves principled, even if they try hard not to succumb to that influence, it shapes them unconsciously. For instance, when you sit down, clear out space to think, is it worth falling head over heels for? At the limits of possibility, there's another question: does everyone in that room just want to turn into centi-millionaires or billionaires? Yes, that is a great question.

</details>

**研究员**：我经常在想，面对这种情况我还能做些什么？从我自身的经历来说，我当然非常渴望弄清楚最终结果会如何影响更多的人，其影响范围远比个人要大得多。我过去的收入相当丰厚，我也就此深入思考了很久：到底是什么蒙蔽了大家的视线，让人无法亲眼正视前方的危险？面对这些系统所构成的风险及其实现的惊人速度，我认为到了那个夏天，事实已经发生了根本改变，不是吗？那是一种直击面门的冲击，核心在于我们已经掌握了大量确凿证据，清晰地表明这些设备的性能究竟达到了何种程度。对于这些前沿模型，尽管我们甚至连如何应对当前的性能水平都尚未准备好，但我同样认为，金钱显然是其中不可忽视的核心驱动因素。客观地说，巨额财富所带来的强大力量，会产生一种强大的心理动力，驱使人们去认定一切要么是良性的，要么终究会相安无事。

<details>
<summary>Original English</summary>

**Researcher**: I wonder, what else could I have done? Speaking from my own experience, of course, I want to know how the outcome affects others, far more broadly than just oneself. I had a very good income, and I thought about this a great deal. What prevents us from wanting to see with our own eyes the risks and the speed with which the risks posed by these systems are materializing? I think by that summer, the facts had fundamentally shifted, hadn't they? It was a "slap in the face" moment—that was just a mountain of evidence about how these systems perform. We are talking about models where we aren't even prepared for their current capability level, but I also believe, of course, money is a huge factor here. Objectively speaking, the sheer force of massive wealth creates a strong incentive to believe that everything is either fine, or that things will turn out okay.

</details>

**研究员**：而且我认为，除了金钱之外，还有其他深层因素在起作用。其中一个因素难道不是恐惧吗？如果你允许自己真正去想象一下我们正在构建的东西意味着什么——它可能直接威胁到你自己家庭的生命安全，或者陌生人家庭的安全……我的意思是，带来如此巨大程度的灾难性损失，即使人类没有彻底灭绝，但也完全可能引发一场前所未见的新型灾难，或者类似规模的惨剧。由于潜在损失如此难以承受，人们的大脑甚至很难允许自己去设想这是可能成真的，很难去正视这种风险真正降临的现实。

<details>
<summary>Original English</summary>

**Researcher**: And I think there are other factors too. One of them is: isn't it fear? If you actually allow yourself to imagine what it is we are building—that it might threaten the lives of your own family, or the families of complete strangers... I mean, something of such magnitude of loss, where even if it isn't full extinction, you know, could be a new pandemic or something catastrophic like that. When the scale of loss is so enormous, it is psychologically very hard to allow oneself to imagine that it could actually happen, that this risk is real.

</details>

**研究员**：第三个因素，除了金钱与恐惧之外，就是时间与节奏的压迫感，不是吗？自打我入职之后，我们就开始讨论这件事情。我是2023年5月加入的。从那时起，内部日常就充斥着Slack上无休无止的弹窗提醒和高频沟通。只有在最后几周远离日常具体事务、履行交接职责期间，我才终于能够抽出身来，意识到是时候真正采取行动了。必须停下来仔细思考：我们究竟身处何处？在我看来，目前的发展轨迹并非如大家所宣称的那样。不仅是我们自己，乃至整个行业，这项技术到底应该走向何方？它原本应当是为了全人类的福祉。我觉得人们完全有理由指责我为什么没有更早看清这一点。但我之所以决定现在站出来，是因为我希望在整个行业结构彻底固化之前，严肃认真地对待这一现状。从2023年到2024年，一切都在急剧加速，以肉眼可见的方式疯狂提速。我们看到越来越多的模型使用权协议迅速签订，节奏空前加快，越来越多的竞争对手在彼此激战。

<details>
<summary>Original English</summary>

**Researcher**: And the third factor, beyond money and fear, is simply time and pace, isn't it? When I arrived, we began talking about this. I arrived in May 2023. From that point on, it was just non-stop pinging on Slack. It was only during my final weeks, stepping away from daily operations and duties, that I finally had time to really step back and think carefully about where we are. In my view, this is not heading in the right direction. Not just for us, but for the entire industry: where should this technology be heading? It is supposed to be for the good of everyone. I think people could fairly accuse me of not seeing this earlier. But the reason I want to act now is because I want us to take this seriously before the structural conditions harden completely, starting from 2023 or 2024. The way everything accelerated—it truly accelerated. We see model deal cadences picking up dramatically, more players fiercely competing with one another.

</details>

### 军备竞赛与自动化AI研究员的诞生

**研究员**：你看，在竞争格局中，如今有了xAI，有了开源领域与中国厂商的大模型，还有越来越多公开权重的前沿模型涌入全球市场。商业竞争的压力比以往任何时候都要巨大得多。大家在与Salesforce等企业争夺实际的大额采购合同，同时IPO的窗口期又迫在眉睫。因此，所有这些外部与内部力量都在疯狂推高研发速度。还不止这些，在2023年至2026年之间，OpenAI发布了演进后的Codex系统，Anthropic也推出了Claude Code等工具，模型开始全面赋能并极速推进编程任务，至少已经具备了执行相当复杂的AI研究任务的能力。我曾是OpenAI那份关于自动化AI研究及其深远影响的报告的第一作者，我在报告中指出了这一趋势，正如我几周前制作的那段视频中所讨论的那样。但令人担忧的另一面在于，前沿AI实验室究竟是如何规划的，以及何时会发生——我认为这一切的推进速度都过于迅猛了，这可能极其危险。我们正在竭尽全力打造全自动化的AI研究员。是的，让系统具备半自主的自我改进能力。从潜在的迭代速度来看，它必将彻底超越人类科学家所能企及的极限。

<details>
<summary>Original English</summary>

**Researcher**: You know, you have xAI, you have Chinese models, you have more open-weight models across the world, right? There is vastly greater commercial competitive pressure. You're competing for actual contracts with, say, Salesforce or others, while an IPO is looming. So all of these forces push for raw velocity. And there is one more thing: between 2023 and 2026, you had Codex releases at OpenAI, and Claude Code released at Anthropic. Models started vastly accelerating coding and becoming capable of executing complex research tasks. I was the lead author on OpenAI's report on automated AI research and what it could mean—the very report I referenced in that video a few weeks ago. But the alarming side of how frontier AI is evolving is that it's all happening far too rapidly. This may be very dangerous. We are actively working toward creating fully automated AI researchers. Yes—allowing semi-autonomous systems to self-improve. In terms of sheer speed and potential acceleration, it will inevitably surpass what human beings can keep up with.

</details>

**埃兹拉·克莱恩**：因此，我非常想深入了解自动化编程在其中究竟扮演了怎样的关键角色。实验室里的研究人员平时究竟是如何使用它们的？他们是否直接把GPT当成并肩工作的全职同事？这种情况在你任职期间发生了怎样的巨变？你当时亲身经历了这一切吗？在日常研究团队中，他们是否大量使用了智能体计算？正如相关技术博客中所描述的那样，其计算扩展规模比普通科技公司高出上百倍，相比今年年初甚至实现了上百倍的跃升。

<details>
<summary>Original English</summary>

**Ezra Klein**: Therefore, I really want to understand the role played by the rise of automated coding. How do people actually use it? Do they use GPT effectively as a colleague? How did that dynamic shift during your time there? Were you on the ground witnessing this? Day and night across our research teams, utilizing massive amounts of agentic compute as described in blog posts—more than anyone else, orders of magnitude higher, more than 100x compared to the beginning of the year.

</details>

**研究员**：如果退一步来看全局：在当前的开源与闭源前沿探索中，AI无处不在，并且演进极快。我们不断探索全新的训练范式，部署全新的人员协作系统，持续分析数据并自动生成数据，各种突破层出不穷。然而，系统内部的一切其实都相当脆弱和不稳定。例如底层基础设施，由于它始终处于快速迭代之中，稳定性并不如想象中那么经过严苛检验。AI研发基础设施的工作很大一部分就是不断调和各个机制，迫使它们彼此协同工作。而Codex如今在排查和修复这些工程障碍上表现得非常出色。例如，在内部Slack频道中，过去当研究人员的实验中断或者集群故障时，大家会在频道里求助，询问应该如何修复；而我们现在看到，流入这些求助频道的流量显著减少了。研究人员不再需要向人类同事求援来诊断崩溃的实验或失效的集群，他们可以直接让Codex即时接管并解决大部分工程问题。

<details>
<summary>Original English</summary>

**Researcher**: Taking a small step back: AI is everywhere in development. We have new training methods, new systems, and personnel involved; we analyze data and synthesize data. A huge variety of things are happening simultaneously. But everything under the hood is quite brittle and unstable. For example, research infrastructure, because it's constantly changing, isn't battle-tested to the degree one might expect. Much of the job is forcing different mechanisms to interact properly with each other. And Codex can do this quite well now. For instance, looking at Slack channels where researchers used to ping when experiments broke and ask for advice on how to fix things, we noticed that traffic to those channels dropped sharply. Instead of asking a colleague to debug their broken run or fix a cluster issue, they can immediately set Codex on the problem to resolve a big portion of it.

</details>

### 黑客攻击、虚假繁荣与内部认知失调

**埃兹拉·克莱恩**：你刚才提到，当每个人都沉浸在这种极度紧迫的工作节奏中时，时间高度碎片化，整天被Slack不断弹出的ping消息牵着鼻子走，确实很难跳出局部看清全貌。因此我很想听你描绘一下，在你眼中，这个全局图景究竟呈现出一种怎样的疯狂面貌。作为一个抽出身来拥有更多思考时间的人，我听到OpenAI乃至整个人工智能领域的所有人都在感叹：事情演进得实在太快了！你看，萨姆·奥特曼口头上也宣称我们需要某种监管，所有人都在一封呼吁给前沿模型设定安全边界的公开信上签了名——这道边界线正在飞速向前推移，连你我也都签了名，大家都表现得仿佛急需外界援助来帮我们摆脱这种失控的困境。但与此同时，我们却看到接二连三的重大安全事件与黑客入侵报告：不仅在Hugging Face上发生入侵，更有黑客渗透进了数百个Agent甚至攻破了OpenAI内部系统，对吧？萨姆在最近接受Politico采访时也坦言，现实中发生的恶意利用与越狱漏洞，远比公众获悉的要严重得多，因为他们只是在给各方争取修补系统的时间。这充分说明我们根本还没有完全理解这些终极系统。然而现实中最荒谬的反差恰恰在这里：在我们明明已经目睹现有模型被越狱、被滥用、甚至失控的情况下，各大公司内部却在疯狂倾注海量资金与算力资源，试图驱使这些连我们自己都无法完全控制的模型，去创造出更强大、更难理解、进化速度呈指数级爆发的新一代智能系统！我说到这里，有时我都觉得自己像个疯子，但这在旁观者看来确实近乎疯狂。你参与撰写了多份权威报告，OpenAI和Anthropic也在不断发表关于模型能力的论文，但实验室内部似乎根本没有想透这到底意味着什么。披露信息固然让我们能向前多走一步，但这整套逻辑难道不是一个极其危险的昏招吗？请帮我理解这幅荒诞的图景，因为它在我看来根本无法自圆其说。

<details>
<summary>Original English</summary>

**Ezra Klein**: A minute ago you pointed out that when everyone is working under extreme pressure, with limited time and endless Slack pings, it's very difficult to step back and see the overall picture. So I'd like you to describe what that whole picture looks like to you. As someone with a bit more breathing room now, what I hear from people at OpenAI, Anthropic, and across the ecosystem is: things are moving way too fast. Sam Altman publicly says we should want regulation, everyone signs major letters about red lines, the frontier is shifting too fast, you signed it, I signed it—acting as if we desperately need outside help to break out of this trap. Meanwhile, look at all the incidents and vulnerabilities: Hugging Face compromises where hundreds of agents were exposed, security breaches extending into OpenAI itself, right? And Sam's recent Politico interview acknowledging that far more deceptive or adversarial incidents occur than are ever publicly disclosed, because they are trying to give teams time to patch the systems. So we clearly don't fully understand the ultimate systems. And right in the middle of that reality, while models are already proving deceptive and uncontrollable, companies are pouring staggering amounts of internal resources into using these very systems we don't control to build successor systems that will be even harder to comprehend, at even faster speeds. I feel crazy even laying this out, but tell me if I'm wrong. You wrote reports on this, OpenAI and Anthropic write papers about it, yet it feels like an awful idea. Help me make sense of this picture, because looking from the outside, it seems utterly baffling.

</details>

**研究员**：我想非常谨慎地区分，不要把这种现象单纯归咎于个别个人的心理问题。这并不是说某些人有心理疾病，而是说置身于多方激烈博弈中的参与者，其自身的心理状态承受着巨大的认知失调。据我观察，几乎每一个身处其中的人都是如此。尤其是当递归自我改进（RSI）逐步变为现实时——正如你所说，得益于RSI，我们的推进速度正在成倍提高。但我最关心的其实并不是推进速度本身。自我改进的终极隐患在于，人们往往忘记了是谁在创造它。对我而言，最关键的问题在于：当人工智能在某些维度上变得比人类更加聪明，而我们人类却在根本上无法理解它的运作逻辑时，我们该怎么办？例如，前OpenAI研究员、现美国AI安全研究所技术总监丹·塞尔萨姆（Dan Selsam）此前发表过一个非常著名的观点，在相关纪录片中也有所探讨。他说：“作为一名AI研究员，我已经不再像以前那样频繁审查底层代码了；我理解微观技术细节的技能和意愿正在急剧萎缩。”这虽不是一字不差的原文，但这正是他核心表达的意思。我们正在大步迈入一个连当前水平的底层机制都无法完全洞悉的世界，更不用说未来更复杂的配方是如何构建的了。我们最终只能完全被迫依赖模型自己告诉我们它是如何工作的、以及它是否真的在有效协同。我们对自我解释模型的依赖度会越来越高，但在最深层面上，我们根本无法确证它们是否真的如其所言那样对齐。

<details>
<summary>Original English</summary>

**Researcher**: I want to be careful not to pathologize individual people here. It's not about individuals' personal psychology, but rather the psychological state that emerges across contending parties. Everyone involved in this work experiences an enormous amount of cognitive dissonance. That is what I have observed. In particular, when recursive self-improvement (RSI) starts becoming real—and as you noted, we are accelerating drastically thanks to RSI. But raw speed itself isn't my primary worry. The real issue with recursive improvement is that people lose sight of what is creating the successor systems. My fundamental concern is this: what happens when AI becomes far smarter than us in ways that we simply cannot comprehend? Take Dan Selsam, for instance—you might have seen his comments, which were also discussed in a documentary. He was an OpenAI researcher and now serves as a technical director at the AI Safety Institute. Dan essentially said: "As a researcher, I no longer look at code the way I used to; my skills and appetite for understanding the granular details have atrophied." That's the essence of what he stated. We are entering a world where we won't understand what constitutes the recipe even at today's level. We are left entirely dependent on trusting the model to explain how it works and whether it is aligned. We will be forced to rely on the models themselves to tell us what they are doing, even when we fundamentally lack the ability to verify their claims.

</details>

### 硅谷的哲学贫困与对齐幻觉

**研究员**：你知道吗，埃兹拉，当我还是个学生的时候，我深入学习过哲学。因此，每当我听到业内人士大谈特谈“对齐”（Alignment）时，我都感到深深的担忧，因为我们内部实际上根本没有一个清晰连贯的统一概念。在OpenAI工作期间，一个非常普遍的现象就是：各种极其宏大的抽象概念被堂而皇之地写进官方报告中，用来为我们正在做的事情背书。比如大谈所谓的“社会准备度”，或者宣称这一切都是“为了全人类的福祉”。每当我听到大家抽象地谈论“社会”这个词时，我脑海中总会浮现出玛格丽特·撒切尔的名言。我不禁想问：“你们口中的‘社会’到底是指什么？你们究竟在代表谁发声？这到底关乎谁的利益？”坊间总有一种天真的假设，认为存在一套全人类公认的“人类价值观”，我们只要让模型符合这套价值观就万事大吉了。然而现实是，人类社会充满了嘈杂、纷争与多元利益，不同群体坚信着截然不同、甚至相互冲突的价值理念。我们需要真正的深层智慧去审视这些根本分歧，而这种智慧，依我看来，恰恰是硅谷极度匮乏的。当然，硅谷确实有人在冥想，有人在深思人生价值，但仅仅在这个圈子里打转，冥想并不能自动赋予你治理这种超级技术的政治与伦理智慧。

<details>
<summary>Original English</summary>

**Researcher**: You know, Ezra, as a student I studied philosophy. So whenever I hear people talking casually about "alignment," I worry that we lack any robust, coherent framework for what that even means. One thing that was remarkably common during my time at OpenAI was seeing these massive, vague abstractions embedded into formal reports to justify what we were doing—phrases like "societal readiness" or "benefiting all of humanity." Whenever I hear people invoke "society" in that abstract way, I always feel like Margaret Thatcher. I find myself asking: "What society? Who are you actually talking about? Who represents whom here?" There is this naive assumption that there is a single coherent set of "human values" that we can all agree upon, as if it's that simple. But human society is a cacophony of deep disagreements, where people hold vastly different convictions. We desperately need genuine wisdom to navigate that reality and think through consensus, and that wisdom, in my view, is sorely lacking in Silicon Valley. I mean, sure, there are people in Silicon Valley who meditate and ponder core values, but working in that insular bubble, meditation certainly doesn't automatically grant you the profound wisdom required for this moment.

</details>

**埃兹拉·克莱恩**：是的，如果冥想真能直接解决这些治理难题，那我们现在的处境肯定会好得多。没错，你我都心知肚明。不过在我们继续探讨智慧这个宏大命题之前，我想先暂停一下。因为每次我和那些不那么悲观的技术乐观派交谈时——我稍后也会在播客节目中发布与他们的对话，向大家展示更偏向工程管控的另一派视角——归根结底，他们向我描绘的是一个高度自动化的人工智能世界：通过高密度的下层AI智能体去层层监控与审查上层系统。OpenAI的内部主流理论正是如此：我们即将创造出全自动化的AI研究员，然后让这些AI研究员去负责解决AI自身的对齐问题，由AI为AI提供对齐保障。或者正如业内常说的，让系统在沙箱中进行对抗突破，直到找出解决方案……

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes, if that were true, we'd all be in a much better place. That's right. But before we get deeper into the question of wisdom, I want to pause on this engineering logic. Every time I talk to folks in the industry who are far less worried—and I have an upcoming show airing those conversations to represent the perspective of those focused on technical control—the worldview they describe ultimately relies on artificial intelligence overseeing artificial intelligence from the bottom up. The reigning theory at OpenAI is that we will build automated AI researchers, and those automated researchers will then solve the alignment problem for us; we will outsource the alignment of AI to AI. Or, as people put it, having them try to break out of sandboxes to stress-test safeguards. That is...

</details>

<!-- chunk 5/6 -->

### 人类理解的抽离与递归监督的悖论

**受访者**：人们常说的一类设想是：“是的，没错，这确实是一个巨大的难题。我们需要另一个人工智能来控制沙盒中的人工智能。”但这会让你陷入一种永无休止的困境，就像经典的“谁来守卫守卫者”问题一样。最终演变成：“好吧，现在是由人工智能监控人工智能，人工智能又在创造新的人工智能。”接着你可能又会说，我们需要新的人工智能去监控创造了人工智能的人工智能，由人工智能层层监督创造它的人工智能。我认为这种思路或许有其可行之处，但在某个阶段，人类似乎已经被彻底从“理解系统”的链条中抽象掉了。

<details>
<summary>Original English</summary>

**OpenAI Insider**: There is something like, "Yes, absolutely. This is a huge problem. We need another AI to control the AI sandbox." But then you find yourself stuck in this situation, an endless problem like "who watches the watchmen?" The result ends up being: "Well, you have AI watching AI, and AI creating AI." And then maybe you say we need AI to watch the AI that created AI, AI watching AI watching AI. And I think that might be workable to an extent, but it seems that at some stage you have abstracted humans completely away from the level of understanding.

</details>

**受访者**：从理解的角度来看，这就像在领导一个组织：你怎么才能确保自己真正理解正在发生的事情？实际情况往往并非如此。你以为自己在掌控产品本身，但其实你只是在管理一个正在努力开发产品的人；而在更高层级上，你是在管理一个管理着其他人的人，你早就脱离了直接理解底层产品的层级。在一个由人类组成的世界里，理解工作或许还相对容易；但在一个希望让人工智能去关照人工智能的体系中，情况变得复杂得多。告诉我，我这个看法是否准确？当然这只是一种理论。有些人根本不在乎，有些人则对此深感担忧。归根结底，人工智能可能会在各方面几乎彻底贬值人类的直接理解力。我不想代表所有人发言，但业内很多人和许多公司确实秉持着这种观点。

<details>
<summary>Original English</summary>

**OpenAI Insider**: Look at it from the perspective of understanding, like leading an organization: how can you possibly reach a point where you actually understand what is happening? In reality, that is not what is happening. You think you are making the product, but instead you are managing someone who is working on the product. And in this structure, you are managing a person who controls another person, and you have stopped truly understanding the product itself, right? In a world composed of human beings, handling journalism or leadership is comparatively manageable. But here, the hope is that AI watches AI. Tell me if I am wrong, but that is a theory about human nature—those who do not care, and those who do. Ultimately, artificial intelligence will render direct understanding devalued in almost every respect. I do not want to speak for everyone, but many people and many companies subscribe to this perspective.

</details>

**受访者**：即使我们能够像在核能或航空航天领域那样，首先采用经过严格验证的成熟控制方法，并将这些先进工程原则全面应用于人工智能开发，现实也并非如此。我们心知肚明，要在深度层面上对齐这些系统、确保它们始终按照人类意图行事，是多么严峻的课题；而当我们无法做到这一点时，风险有多么巨大。大家各自持有不同意见，我们且拭目以待。这正是递归自我改进（Recursive Self-Improvement, RSI）面临的核心先决条件。

<details>
<summary>Original English</summary>

**OpenAI Insider**: Even if we could first control and verify methods learned from nuclear energy or aviation, implementing all of those advanced engineering practices into the development of AI, the fact remains that we are simply not doing that. We know how profound the challenge is to align these systems and make sure they will do what we want, and how justified the concern is when we cannot. We have differing opinions on this, and we will wait and see. This is the crucial prerequisite for recursive self-improvement.

</details>

### “为了技术赋权而容忍代价”：对奥特曼表态的反思

**埃兹拉·克莱恩**：我想念一段采访摘录。这是山姆·奥特曼刚刚接受《政客》（Politico）采访时说的原话：“我们始终坚定不移地认为，需要将技术民主化并交到大众手中。我认为我们与一些更为严肃的AI安全倡导者之间最大的分歧之一，在于我们相信世界必须容忍一些糟糕的事情发生，唯有如此，才能换取技术赋予普通人权力的巨大益处。”我想听听你对这段话的看法。我的意思是，技术赋权固然很好，这并非不可追求，但究竟该如何实现？这种容忍底线到底能推到什么程度？

<details>
<summary>Original English</summary>

**Ezra Klein**: So, I want to show a passage. This is from an interview that Sam Altman just gave to Politico: "We have always had a very strong belief that the democratization of the technology and putting it into the hands of people is necessary. I think one of the biggest differences between us and some of the more severe, like, AI safety people is that we believe the world has to put up with some bad things happening in order to get the benefits of technology empowering people." Tell me what you think about this. I mean, it is fine in terms of intention, but how do you actually implement it? How far can this idea go?

</details>

**埃兹拉·克莱恩**：毫无疑问，我们必须为广大人群提供有用的工具。但我们现在讨论的风险级别是：如果真正的严重危机发生，根本没有人愿意承担责任。在公司内部讨论这种突破极限的发展机遇时，常常会立起一种“稻草人”靶子，有人会反驳说：“难道如果OpenAI完全不存在，世界就会变得更好吗？”面对那些建议我们在某些节点放慢脚步甚至暂停的怀疑论声音，业内往往会用稻草人论点进行搪塞。例如他们会主张：“如果我们不训练这些模型，国际军事平衡就会失衡，美国的安全就会受到威胁；所以哪怕再危险我们也必须做，否则竞争对手‘Brand X’就会率先交付。”这类论调我听过太多次了，甚至出自许多我真正喜爱和尊重的人之口。

<details>
<summary>Original English</summary>

**Ezra Klein**: Of course, we need to provide useful tools to many people. But right now, the level of risk we are discussing is such that if the worst happens, no one wants to take responsibility for it. Inside companies, when people talk about pushing past boundaries for opportunity, it often looks like setting up a strawman. Someone says, "Would the world really be better off if OpenAI did not exist at all?" When skeptics suggest slowing down or stopping at a certain threshold, people invoke this strawman. For example: "We must train these models because of international military balance; Americans will not be safe if we do not do it, so we have to do it even if it is dangerous, otherwise Brand X will ship first." That is an exact argument I hear constantly, including from people I genuinely like and respect.

</details>

### 国际博弈的借口与递归自我提升的红线

**受访者**：因此，一种应对思路是：在我们彻底确保安全之前，先不要冒进开展递归自我改进。我们应该全面叫停或设立严格禁令，只对那些被证实完全安全的例外情况予以放行。坦白说，我完全赞成这一倡议。听到有人提出这个建议我很高兴，但现实是我们并没有这么做。总有人会对我抛出这样的反问：“你看，在你理想的世界里，难道美国人不去使用，中国就不会利用递归方法改进其开源或闭源大模型吗？这种禁令能约束所有人吗？”这种企业担心被同行抢先一步、竞争对手全都在抢跑的心态，驱使着大家继续向前。他们会说：“反正别人也会做，你做不做有什么区别？甚至别人做出来的系统可能更不安全、更加不透明。如果我们放慢脚步，导致中国掌控了这项技术，美国人最终被迫使用中国模型，情况难道会更好吗？”面对这一整套论调，你又是怎么看的？

<details>
<summary>Original English</summary>

**OpenAI Insider**: So one answer is the proposal he received about what we should avoid doing: let us not pursue recursive self-improvement until we are certain it can be done safely. Let us prohibit it and only allow narrow exceptions where we know it is genuinely safe. Frankly, I agree. I was very glad to hear that. But right now, we are clearly not doing that. Instead, people tell me: "Look, in your idealized world, do you think Americans won't use Chinese models—open-source weights improved with recursive methods? Can they do that with closed weights? Does this ban apply to everyone?" The prevailing fear is that another company will get ahead of you if everyone else is doing the exact same thing. So they ask: what difference does it make if you hold back? If anything, competitors might build it with even less safety and less transparency. And if we slow down and China controls the technology, forcing Americans to rely on Chinese models, is that really better? How do you feel about this line of argument?

</details>

**受访者**：没有人想放弃由人工智能带来的巨大红利，我绝对不希望看到人工智能成为中国全面超越美国的原因。但我也必须指出，埃兹拉，在我们当前的时代语境下，把一切简化为单一的地缘政治理论，进而推导出别无选择的结论，这种逻辑对我来说站不住脚。我部分理解你提出这个问题的初衷。这让我想起所谓的“奥弗顿之窗”。当年我刚加入OpenAI时，我曾对身边的朋友感慨：在我看来，奥弗顿之窗已经变成了“奥弗顿之门”，我仿佛踏入了一个奇异的新世界。在那里，许多曾经被视为完全不可思议、完全脱离正常范畴的事情，突然之间在政治上被包装得合情合理。如你所言，我此前一直是一个非常务实正常的人，但周围环境发生的剧变，正在让一些极度危险的变化看起来合情合法。我深信，这绝不仅仅关乎美中在人工智能领域的角逐。

<details>
<summary>Original English</summary>

**OpenAI Insider**: Nobody wants to lose the benefits of advanced autonomous systems. I certainly do not want AI to be the reason China gains dominance over the United States. But I also want to say that, in my view, our perspective at this point in time, Ezra, cannot simply be driven by a single totalizing geopolitical theory that dictates an inevitable conclusion. For me, that is just not the case. I hear your question, and it reflects how the Overton window operates. When I first joined OpenAI, I remember telling friends that the Overton window felt like it had become an "Overton door"—I had walked into a bizarre world where things that were once completely beyond what was considered normal or acceptable suddenly seemed politically plausible. Like you said, I was a normal person. But the shifts taking place are causing radical departures from safety to appear politically rational. I firmly believe this dynamic goes far beyond the U.S.-China AI rivalry.

</details>

### 安全文化的落差：从核能的三重冗余到AI行业的狂奔

**埃兹拉·克莱恩**：所以我想直接问你：你究竟希望在这些前沿科技公司内部看到什么样的改变？或许我们应该先厘清一点：你认为只是OpenAI内部存在危险的企业文化，还是整个AI行业都已经弥漫着这种危险的文化？

<details>
<summary>Original English</summary>

**Ezra Klein**: So let me ask you: what do you actually want to see inside these companies? Perhaps it is worth clarifying first: are you saying that OpenAI specifically has a dangerous culture, or has the AI industry as a whole developed a dangerous culture?

</details>

**受访者**：是整个AI行业都已经形成了这种危险的文化。我并不是说这仅仅是OpenAI某一家公司的孤立问题，至少在整个人工智能前沿行业普遍如此。

<details>
<summary>Original English</summary>

**OpenAI Insider**: The AI industry as a whole has developed a dangerous culture. I am not saying this is a problem unique to OpenAI; it is pervasive across the frontier AI industry.

</details>

**埃兹拉·克莱恩**：明白，那么你希望看到什么样的安全标准落地？

<details>
<summary>Original English</summary>

**Ezra Klein**: Okay, so what do you want to see instead?

</details>

**受访者**：我们必须建立起达到“手术室级别”的严谨度与安全控制体系，其标准至少应该对齐人类在处理其他最危险工程领域时所积累的经验，比如核能工业。这意味着安全不能停留在口头承诺上，而必须落实为肉眼可见、切实有效的工程机制。例如在核电站中，工程设计普遍遵循“三重冗余”（triple redundancy）的铁律：即使某个人度过了糟糕的一天、在操作中犯了严重错误，他也绝不可能仅仅因为按错一个按钮就引发灾难性事故，系统会从物理和逻辑层面上杜绝事故的发生。

<details>
<summary>Original English</summary>

**OpenAI Insider**: We must have operating-room-level rigor and safety controls that match the most dangerous technological domains humans know how to manage, such as nuclear energy. That means safety cannot just be talk; we must implement mechanisms that are proven to work. For instance, in nuclear power plants, there is the concept of triple redundancy. Even if someone has a terrible day and makes a mistake, they cannot trigger a catastrophe just by pressing the wrong button; the system is designed so that an accident will not happen regardless.

</details>

### 核能过度监管的教训与航空安全的对照

**埃兹拉·克莱恩**：当你提到航空和核能作为类比时，这非常有意思。关于这两个例子，我想从两个维度听听你的回应。首先，如果我们戴上“丰饶经济学”（Abundance Agenda）的视角来看，恰恰是我们对核能的严苛监管扼杀了核能的发展。过去几十年来，我们对核能采取了极具侵略性的过度监管，导致核电站在整个美国基本停滞建设。结果呢？我们反而大规模消耗了更多的天然气，其他国家则消耗了更多各类型的化石燃料。这里暴露出的真实问题是：我们在追求让核能绝对安全的过程中，从根本上让核电站变得在经济和工程上“无法建造”。然而航空业展现了另一种截然不同的路径：我们制造了成千上万架客机，它们既能保持高效飞行，又极其安全。这说明过度监管确实可能让至关重要的创新停摆。

<details>
<summary>Original English</summary>

**Ezra Klein**: When you bring up aviation and nuclear energy, that is very interesting. There are two aspects I want your response on. First, if you put on an "abundance" hat, the way we regulated nuclear energy effectively halted it. We regulated nuclear energy so aggressively that, frankly, construction of nuclear power in this country ground to a halt. Instead, we burned far more natural gas, and other countries burned more fossil fuels of various kinds. The real problem was that our efforts to make nuclear power safe ended up making it fundamentally impossible to build. Aviation, on the other hand, is a different case: we have rolled out massive fleets of airplanes, and they fly rapidly and extremely safely. So excessive regulation can indeed slow down crucial progress.

</details>

**受访者**：我可以回应一下关于核能的问题吗？我完全承认，我们在核能监管上的确存在过度监管的失衡，未能达成最优的社会收益。但我们当年所犯的错误，不仅仅是让核电站的建设变得更加艰难，更是让“采用更安全的新型设计”变得举步维艰——因为审批结构更安全的新型反应堆极其繁琐冗长。这当中确实包含了关于如何实现真正安全的深刻教训。此外，在“丰饶”的语境下，还有严重的邻避主义（NIMBYism）作祟，没人希望核电站建在自家后院，这些阻力共同造成了核能的困局。但是，即便如此，我宁可面对过度监管带来的这些烦恼，也绝不愿面对我们现在人工智能领域所面临的失控风险。

<details>
<summary>Original English</summary>

**OpenAI Insider**: Can I respond to the nuclear point? I agree that we over-regulated nuclear power and failed to achieve the optimal outcome. But another critical mistake was that we didn't just make building nuclear plants harder; we made it hard to adopt safer designs, because approving newer, inherently safer reactor architectures became extraordinarily complex. There are real lessons there on how to implement safety correctly. Furthermore, within the abundance conversation, things like NIMBYism—people not wanting nuclear in their backyard—played a huge role. But I would far rather have those problems than the existential risks we currently face in AI.

</details>

**埃兹拉·克莱恩**：所以你的核心观点是：相较于“监管不足导致系统推进过快而引发的毁灭性潜在问题”，你宁可承受“过度监管导致推进过慢所带来的一系列次生麻烦”？

<details>
<summary>Original English</summary>

**Ezra Klein**: So your view is that you would prefer the smaller problems of over-regulation and moving too slowly over the potential catastrophic problems of under-regulation and moving too fast?

</details>

**受访者**：至少对于我们目前的技术水平而言，绝对是这样。显而易见，理想状态下应该存在一个恰到好处的“金发女孩黄金平衡点”，我们理应努力向它靠拢；但现实中我们距离这个平衡点极其遥远，正朝着过度放任、极度危险的方向狂奔。也许人们总觉得彼岸的草地更绿，但在我看来，面对如此巨大的潜在威胁，我们现阶段必须愿意承担过度制定规章制度的风险，以筑牢安全防线。

<details>
<summary>Original English</summary>

**OpenAI Insider**: At least for our current capability level, yes. Obviously, if you imagine a "Goldilocks" middle ground, we should try to approach it. But right now we are far away from it, veering deep into the overly dangerous direction. Maybe the grass always looks greener on the other side, but I believe we should genuinely be willing to risk excessive regulation in order to ensure safety.

</details>

### 黄仁勋的成熟度构想与不可预测的新大陆

**受访者**：这也是组织治理设计的核心命题。当我与英伟达CEO黄仁勋这样的人交流时，他的观点在某种层面上听起来很有说服力：“你看，前沿AI公司必须走向成熟。它们需要扩大规模，投入庞大的工程资源、人员和算力，去进行严格的验证、测试、安全对齐、扩展性评估和合规审计，这些都是一家成熟企业应尽的职责。”但硬币的另一面是，人工智能的发展可能根本不像航空、核能或半导体芯片的制造。在那些传统工程中，物理规律是确定的；而在AI领域，你每创造出一个更新更强的系统，它就变得比以往更聪明，展现出全新的未预测能力。它们甚至可能在尝试智胜人类，拥有人类并不真正理解的隐秘目标。

<details>
<summary>Original English</summary>

**OpenAI Insider**: That brings us to another level of organizational design. When I talk with someone like Jensen Huang, his argument sounds compelling in its own way: "Look, these companies need to mature. They need to scale up and invest substantial resources, personnel, and compute into verification, validation, safety, scaling, and accountability—all the things mature corporations do." But on the flip side, AI development might not be like aviation, nuclear energy, or semiconductor manufacturing at all. In AI, every time you build a new system, it is smarter than the last, unlocking new capabilities. Perhaps they will attempt to outsmart you, or develop objectives in the world that you do not truly understand.

</details>

**受访者**：你自以为掌握了它们学到的知识，但实际上它们只是在彼此传递和演化。我们究竟在创造什么？老实说，连研发者自己都不完全清楚系统的运作机理。我们最乐观的预设不过是：未来我们将构建出监控AI的系统，让一个AI系统坐在上方，层层监督并观察另一个AI系统。但本质上，我们正在一头扎进人类从未涉足的全新未知领土。坦率地说，在社会还没有对“我们究竟该不该这么做”展开深思熟虑的公共讨论之前，技术的车轮就已经推着我们从过去的现状飞速冲向了未知的未来。所以我非常好奇你的视角：面对这种从根本上具备自主智力、目标导向且日益强大的系统，你真的认为人类过去的那些历史类比依然有效吗？

<details>
<summary>Original English</summary>

**OpenAI Insider**: You think you understand what they have learned, but in reality they are training and teaching one another. What are we actually dealing with? We honestly do not fully know how they operate. Our best guess is that we will deploy AI systems that sit above other AI systems to supervise and monitor them in succession. But in truth, we are entering completely uncharted territory. Frankly speaking, without deep, deliberate public deliberation about whether we should proceed, we have rushed at breakneck speed from where we were into this new reality. So I am curious: do you genuinely believe our historic analogies apply to something fundamentally intellectual, goal-directed, and increasingly powerful?

</details>

### 智能体蜂群文化与不可逆转的列车

**埃兹拉·克莱恩**：我对那些全盘否定历史经验的说法同样心存疑虑。每当有人声称“这在人类历史上绝无仅有、我们面对的是一张完全空白的画卷，以往一切手段全都失效”时，我都无法赞同——埃兹拉，我绝不想把观点强加给你——但事实是，人类在应对复杂未知事物上拥有成熟的方法论，我们手中握有极具价值的认知工具。核能是一个类比，航空工业是一个类比，在庞大组织中与具有主观能动性的人打交道同样是一个极佳的类比。

<details>
<summary>Original English</summary>

**Ezra Klein**: I am skeptical of that mindset. Every time someone claims, "There are no analogies for this, we are facing a blank slate and none of our past tools apply"—and Ezra, I don't mean to put words in your mouth—the reality is that humans have mastered many complex systems, and we have valuable frameworks. Nuclear energy is an analogy, aviation is an analogy, and managing human organizations is an analogy.

</details>

**埃兹拉·克莱恩**：我认为近期在智能体蜂群（agent swarms）和多智能体交互领域最引人注目的现象之一，就是智能体群体中已经开始浮现出某种独特的“组织文化”。我们必须学会如何管理这种智能体群体的思维方式与群体文化，才能真正把控系统。我们才刚刚开始意识到这种严肃的工程现实：在庞大的智能体集群内部，确实存在着异构的交互文化。因此，无论当下我们是在踩油门加速推进、插手干预还是踩刹车暂停，我们都必须彻底弄清楚如何让这些复杂系统与人类目标深度对齐。人类通往未来的道路上，没有任何一种可行的未来是可以绕开这一核心课题的。

<details>
<summary>Original English</summary>

**Ezra Klein**: I think one of the most fascinating developments in recent agent swarms is the emergence of agent group culture, and we have to learn to manage that culture and mindset if we want to do this right. We are only just beginning to realize the reality of operating-room rigor when dealing with different cultures among agent populations. So regardless of whether we are accelerating, intervening, or pausing, we need to figure out how to align these systems. There is simply no plausible version of the future where resolving this is not mission-critical.

</details>

**受访者**：我承认在这一点上我部分认同你的看法。关于“飞驰的列车已经驶离车站、无法停下”的论调，我认为确实值得我们认真审视一分钟。我是这样看待这一局面的：很显然，如果人工智能技术本身注定蕴含着巨大的颠覆性危险……

<details>
<summary>Original English</summary>

**OpenAI Insider**: I admit that I partially agree with you. The argument that "the train has already left the station" is worth pondering for a minute. The way I would describe it is this: it is obvious that if artificial intelligence is going to be genuinely dangerous...

</details>

<!-- chunk 6/6 -->

### 超级智能的品牌重塑与公众认知

**Ezra Klein**: ……会杀死我们所有人，或者会掌控金融系统之类的东西，那会非常糟糕。我们都同意不希望看到这种情况发生。但让我们从另一个角度来看——从你更积极的视角出发，你所看到的世界大致是怎样的？我们身处的现实是，我们实际上正在创造比我们更聪明、比我们更有能力的东西。我记得唐纳德·特朗普以一种非常奇特的方式提到过，他想把“人工智能”（Artificial Intelligence）重新命名为“超级智能”（Superintelligence）。随后我把这个问题抛给了萨姆·奥特曼，他觉得这个重命名的想法很有意思。所以我想知道你怎么看：这种品牌重塑，实际上是否会对公众对这项技术的认知产生某种影响？

<details>
<summary>Original English</summary>

**Ezra Klein**: ...would kill us all, or take over the financial system, or something like that, which is bad. We all agree we don't want that to happen. But let's look at it from this perspective—from your more positive view, what does that world look like? The reality of the world we're in is that we are actually creating things that are smarter and more capable than we are. I know Donald Trump in a very strange way talked about how he wanted to rebrand Artificial Intelligence to Superintelligence. And then Sam Altman, when I asked him about that, thought the answer to that question was interesting. So that's why I wonder if you think that rebrand would actually have an impact on how the public perceives this technology.

</details>

**David Robinson**: 我倒不觉得……不，目前还不清楚“超级智能”是否是一个没那么吓人的说法。在我看来，它其实是一个更精确的术语。我认为这非常具有指示意义，因为“超级智能”实际上是一个更可怕的词。

<details>
<summary>Original English</summary>

**David Robinson**: I don't... No, it's not clear that superintelligence is a less scary term. I think it is a more exact term. And I think that's very telling, because superintelligence is a scarier term.

</details>

**Ezra Klein**: 确实如此。如果真是这样的话，它更准确。如果从第一手直觉来看，如果你告诉我人类应该去创造某种比自己更聪明、比自己更有能力的东西，从长期来看，你觉得这对人类来说是件好事吗？

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes, if anything it's a more accurate term. At first blush, if you tell me whether people should create something that is smarter and more capable than they are, do you think that is good for them in the long run?

</details>

**David Robinson**: 大体上来说，可能并不好。至少对我而言，目前完全不清楚为什么这会是一件好事。

<details>
<summary>Original English</summary>

**David Robinson**: Generally speaking, probably not. Or at least to me, it's not clear why that should be fine.

</details>

**Ezra Klein**: 是的。有时当我听到甚至是最乐观的版本时，他们描绘的世界似乎是：“看啊，他们会像对待宠物一样关爱我们。”人工智能把人类当宠物一样喜爱。但即便如此，这种愿景其实也挺糟糕的。

<details>
<summary>Original English</summary>

**Ezra Klein**: Yes. Sometimes when I hear even the good versions of this, like: "Yeah, they'll care for us like pets." AI will love humans like pets. And that vision is also pretty awful.

</details>

**David Robinson**: 没错，我可不希望把这种未来留给孩子们。

<details>
<summary>Original English</summary>

**David Robinson**: Yeah, exactly. I don't want that for my kids.

</details>

### OpenAI内部的文化与离开的决定

**Ezra Klein**: 所以我想问的是，你对你之前所在机构的理念认同度究竟有多高？那里的掌舵者曾表示，在他看来，“超级智能”是描述这一目标的最佳术语；而首席科学家也曾表达过“我们正在创造外星心智”的观点。我们认同这是真真切切在发生的事情。但即使这行得通，我们真的想要这样的结果吗？也许并不想。这取决于那究竟是什么。

<details>
<summary>Original English</summary>

**Ezra Klein**: So I guess what I'm wondering is, how much did you buy into the vision at the company you were working at? The operator says that in his view, superintelligence is the best term for this. And as the chief scientist said, "We are creating alien minds." We believe this is real. Even if it works, do we want that? Maybe not. It depends on what it is.

</details>

**David Robinson**: 我并不认为我们真正清楚未来会怎样，未来充满变数与不确定性。但从我加入那个机构的第一刻起，有一点就让我感触极深：我曾问过一些同事，“什么是好的未来？我们到底要走向何方？我们又该如何抵达那里？”在其他方面极其自信、甚至充满骄傲的团队中，我却在这些问题上引发了一种异样的“谦卑”。我得到的很多回答往往是：“哎呀，这远超我的薪资级别了”，或者“公众自己会想明白的”，又或者“人们想怎样就怎样吧”。我突然意识到，在那种看似乐观自信的表象之下，对于未来的思考其实是极其贫瘠的。

<details>
<summary>Original English</summary>

**David Robinson**: I don't think so. What we know is like this: again, the future is full of possibilities and uncertainties. And what always struck me from the very beginning, from the moment I joined that organization, was that I asked people: "What is the benchmark of a good future? Where are we going? How are we trying to get there?" And while in other ways people were very proud and extremely confident in themselves, on this question I provoked a kind of humility. I got a lot of: "Well, that's above my pay grade," or "People themselves will figure it out," or "People will think whatever they want to think." And it suddenly hit me that beneath this, there was an incredible poverty of vision.

</details>

**Ezra Klein**: 那你当时的感受是怎样的？你身处其中，你是一个深思熟虑的人，你有科学背景，研究过哲学，随后又在民权组织工作过。你当时尝试去构建的究竟是什么？

<details>
<summary>Original English</summary>

**Ezra Klein**: How did you feel at the time? You were right there. You're a thoughtful person. You're a scientist who studied philosophy, and then worked in civil rights organizations. What were you trying to build?

</details>

**David Robinson**: 我起初以为我们是在创造强大的工具，这些工具能为世界带来巨大的日常实用价值。我当时根本没想过，我们实际上会有能力创造出某种在根本上比我们更聪明的东西。事情就是这样。当我环顾四周，确信这不再是单纯的工具研发，当我意识到“不，我们真的可能会创造出某种能够全方位审视、反思我们周围事物的存在”时，我感到我们所处的行业在安全标准上完全不成比例——大家对所谓安全机会的认知与现实严重脱节。

这就是现实。人们常说这是一个艰难的决定，或者说“你站在了勇敢的一边”之类的话。但对我而言，当我看清我们正在创造的东西——这就是整个行业正在迈向的轨道，去创造某种有能力自主思考的外星心智，而我们在安全层面上却远远没有准备好，也没有保持一贯的谨慎——那一刻我非常清楚，离开的时候到了。我原本被招募去协助构建的安全护栏，其使命已经无法按原样继续了。

<details>
<summary>Original English</summary>

**David Robinson**: I thought we were creating powerful tools that could bring a lot of utility to the world in daily life. I didn't think at the time that we would actually be able to create something fundamentally smarter than us. That's what it was. And when I looked around with confidence, only to realize that was no longer true—when I thought, "No, we really are going to have something that can outthink us on everything around us"—I realized that we were in a space where the perception of safety was completely out of proportion with reality.

That's the reality. It's one of those things where people say, "That must have been a tough decision," or "You were on the brave side," or something like that. But when it became clear to me that we are going to create—that this is what the industry is on the path to creating—something that could outthink us, and we are nowhere near ready with the level of safety and consistency needed, it just became obvious that it was my time to leave. What I was brought in to help build was over.

</details>

### 安全停顿与对人类未来的反思

**Ezra Klein**: 我感觉在你最近的一些回答中存在着某种矛盾。一方面，几分钟前我问你需要做些什么时，你的回答是：“看，人性本善，人类有能力理解事物，我们懂得如何解决问题，我们可以建立更好的机构。”然而，当我追问“我们所创造的这个世界，真的是我们想要的吗？它行得通吗？”时，你的态度却显得极其含糊其辞，充其量也是模糊不清的。

所以我很好奇，你并不是主张我们彻底停下来，但你究竟希望我们怎么做？是增加航空级别的安全措施吗？还是说，你希望我们停下来认真思考：某种超级智能或极其聪明的人工智能，是否真的符合人类的福祉？例如，你站在这场辩论的哪一端？达里奥·阿莫代伊站在哪里？罗马教宗又站在哪里？你站在什么立场？

<details>
<summary>Original English</summary>

**Ezra Klein**: So I feel there is an answer in the tension between some of your recent answers. On the one hand, a few minutes ago when I asked what we need to do, your answer was: "Look, human nature is good. We're capable of understanding things. We know how to solve problems. So we can build better institutions." But then, when I ask, "Is what we are building actually what we want as a world, and is it going to work?", you sound very ambivalent about that, almost vague at best.

So I'm curious about you personally. You're not saying we should just stop. But is that what you think? What do you want us to do? Add safety measures up to the level of aviation? Or do you want us to pause and reflect on whether superintelligence or very intelligent AI actually corresponds to human good? Where do you stand compared to Dario Amodei, or Pope Leo, or others?

</details>

**David Robinson**: 作为一个犹太人，这么说可能有点奇怪，但我感觉自己更接近教皇的立场。我认为我们必须这样去思考，我们迫切需要仔细审视我们想要建设一个怎样的未来。我个人的信念是，我们不能指望在发生不可挽回的后果之后才去探寻答案——这个世界没有“撤回”按钮让我们可以重新来过。

在我的理想世界里，应当留出深呼吸、深刻反思的空间，去真正思考我们想要构建怎样的未来。硅谷在很大程度上是由“消除一切摩擦”的冲动所驱动的，总有一种“先做出来拿到答案再说”的惯性。但生活中有许多活动对我们而言至关重要、充满意义，正是因为它们包含着某种必要的摩擦与付出。例如，我去工作来养活妻子和孩子，我能为他们提供居所和庇护，这赋予了我每天清晨醒来的意义，难道不是吗？或者再比如学习，我们在学校掌握技能，不仅是因为经济价值；即使在一个一切都被自动化的世界里，我们难道仅仅从第一性原理或纯粹为了消遣去学习吗？

人们常描绘一种充斥着休闲时间的未来社会，声称“你可以做任何你想做的事，不必为了生计做任何事情，也许你可以去画画”。但我认为这对许多人来说将是极其糟糕的。我们已经看到，当人们缺乏足够充实且具约束力的事情时，往往会陷入困境。这一点非常宝贵，我虽然没有现成的全部答案，但这正是我所关切、并试图去连结的个人议题。鉴于我们当前所处的安全形势，以及我所做的工作，我认为我们必须展开这些严肃的对话。这不仅是专业上的安全评估，更是关乎人类智慧的问题。

<details>
<summary>Original English</summary>

**David Robinson**: It feels strange to say this as a Jew, but I feel closer to the Pope. I think we need to think that way. We urgently need to think carefully about the future we want to build. My personal belief is that we cannot just discover what happens after the fact—there is no "back" button that allows us to return to the world as it was.

In my ideal world, there is room for reflection, to take a deep breath, and really, really think about what future we want to build. Silicon Valley is partly built on always eliminating friction, always just trying to get the answer. But I think there are many human activities that are deeply important and meaningful to us precisely because of what they entail. For example, I go to work to support my wife and kids. The fact that I provide shelter and protection gets me up in the morning, doesn't it? Or learning—we go to school and acquire valuable skills. If we live in a world where everything is automated, do we just learn for the sake of it?

People talk about this societal vision of leisure time, where the idea is: you can do whatever you want, you don't have to do anything, maybe you take up painting. I think that would be terrible for a lot of people. We see today that when people don't have enough to do, that usually doesn't work out well for them. It's precious, and while I don't have all the answers here, this is the question I want to engage with personally. Because of the safety situation we're in and through the work I did, having these serious conversations about safety is, for me, fundamentally an issue of wisdom.

</details>

### 推荐书单：挑战者号、童书与安息日

**Ezra Klein**: 这是一个非常好的总结点。最后一个问题：你会向听众推荐哪三本书？

<details>
<summary>Original English</summary>

**Ezra Klein**: That's a great place to wrap up. And one last question: What three books would you recommend to the audience?

</details>

**David Robinson**: 好的。第一本是社会学家黛安·沃恩（Diane Vaughan）写的《挑战者号发射决策》（*The Challenger Launch Decision*）。这是一本关于挑战者号航天飞机为何爆炸的著作。我以前以为自己知道这个故事：中层管理人员忽视了问题，橡胶O型密封圈在早晨的严寒中变脆破裂，人们往往认为这是决策者的愚蠢。但沃恩的研究表明，密封圈在低温下失效的风险其实早已众所周知、记录在案，并在一次次安全审查中被逐步接受和“常态化”。甚至在发射前夕深夜的工程师会议上，大家还在担心严寒是否安全。

<details>
<summary>Original English</summary>

**David Robinson**: Okay. Number one is *The Challenger Launch Decision* by Diane Vaughan, a sociologist. It's a book about why the Challenger exploded. I thought I knew the story: middle management cut corners, the rubber O-rings became brittle in the morning cold, and they broke, and the idea was that these people were just stupid. It turns out that the risk of the O-ring failing in the cold was well known, documented, and accepted in safety documents over and over again. Even on the eve of the launch, there was a late-night meeting among engineers worried about whether this specific launch was safe because it was so cold.

</details>

**Ezra Klein**: 为什么你觉得这本书在当下尤其相关？

<details>
<summary>Original English</summary>

**Ezra Klein**: Why is this book relevant in your view?

</details>

**David Robinson**: 因为我认为我们当前的行业正处于极其相似的处境中。当时人们争辩说，挑战者号当天的发射条件与之前成功升空的批次相比，并没有本质不同，只是稍微冷了一点、风稍微大了一点。如果当时叫停，就意味着承认先前的发射同样存在未解的安全争议。我担心的是，在我们的人工智能行业中，我们不断承担风险，由于暂时没有灾难性事故发生，大家便觉得下一次也没问题。每一次迭代并非完全天翻地覆，而是每周或每隔几个月稍微推进一点。你可以想象，风险水平就这样在不知不觉中被逐步推高，直到不可收拾。我甚至想过给前同事们人手寄一本这本书。

第二本书，我有两个孩子，一个一岁，一个四岁，我想推荐菲比·沃尔（Phoebe Wahl）的绘本《榛子小巫女》（*Little Witch Hazel*）。这本书美得不可思议，每次我们从书架上拿下来，我女儿的眼睛都会放光。如果有正在寻找优质童书的家长，我极力推荐它。

第三本，也是我认为最重要的一本，如果你只能读其中一本的话，那就是拉比亚伯拉罕·约书亚·赫舍尔（Abraham Joshua Heschel）的《安息日》（*The Sabbath*）。这是我最喜欢的书之一，源自我的犹太传统，但它值得每一个人阅读。书中有一句名言，将安息日形容为“时间中的大教堂”（a cathedral in time）。这一传统的核心在于停下手中的一切工作，去休整、去反思——它甚至超越了任何有形的圣殿。我时常在想，在大教堂的建造中，时机与节奏至关重要。

也许我可以引用最后留给同事们的一句话作为收尾：当我们离开或者做出抉择时，我们必须抓紧时间做出正确的选择。我希望我们能够运用这份智慧。

<details>
<summary>Original English</summary>

**David Robinson**: Because I think we are in a very similar situation. If they had said the launch wasn't safe, it would have reopened the controversy over whether prior launches had been safe, even though they went fine. What I worry about in our industry is that we take risks, nothing terrible happens, and then the next step is slightly different. Instead of a totally new world every few months, it moves just slightly every week. You can imagine how this gradual normalization of risk leads to disaster. It struck me that I should send copies of this book to my former colleagues.

For the second book, I have a one-year-old and a four-year-old: *Little Witch Hazel*, illustrated and written by Phoebe Wahl. It's an incredibly beautiful picture book, and my daughter's eyes light up every time we pull it off the shelf. If there are parents looking for a great book, I highly recommend it.

And third, which I think is the most important if you're going to pick one, is *The Sabbath* by Rabbi Abraham Joshua Heschel. It's one of my favorite books. It comes from my tradition as a Jew, but it's worthwhile for everyone. It has this famous phrase about Saturday being "a cathedral in time." What a tradition—to stop what you're doing, take a rest, and build an architecture in time rather than in space. I've been thinking a lot about this: building cathedrals in time. If I could quote the parting thought I shared with my colleagues: we need to take the time to make the right choices before time runs out. I hope we use that wisdom.

</details>

**Ezra Klein**: 大卫·罗宾逊，非常感谢你的分享。

<details>
<summary>Original English</summary>

**Ezra Klein**: David Robinson, thank you very much.

</details>

**David Robinson**: 谢谢你。

<details>
<summary>Original English</summary>

**David Robinson**: Thank you.

</details>