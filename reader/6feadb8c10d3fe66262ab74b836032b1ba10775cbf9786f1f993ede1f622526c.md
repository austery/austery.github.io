---
author: 'House of El: AI'
date: '2026-10-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4fJK-O3S4ko
speaker: 'House of El: AI'
tags:
  - autonomous-agent
  - financial-debt
  - ai-safety
  - cyber-security
  - algorithmic-governance
title: OpenAI 数学成果突袭、万亿芯片债务与韩国银行被黑：AI 泡沫背后的“凭证缺失”危机
summary: 本期深度探讨了当前 AI 热潮中普遍存在的“只有答案，没有凭证”的结构性矛盾。从 OpenAI 抛出 372 项无法自圆其说的数学证明，到华尔街用分级债务撬动数千亿芯片投资却遭遇 OpenAI 年化营收严重不及预期的财务核查，再到一名黑客利用开源 Agent 框架短时间内攻破至少 9 家韩国银行的恶性安全事件。讨论指出，AI 目前正以机器速度提供结果，而人类的理解、验证与防御体系严重滞后。文章最后结合金融反洗钱制度，提出了涵盖模型提供商、使用者身份签名及防御方机构的三层 AI 监管与问责框架。
insight: ''
draft: true
series: ''
category: ai-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - Broadcom
  - Nvidia
products_models:
  - Lean
  - Claude
  - DeepSeek
media_books: []
status: evergreen
---
### 智能体敲门：银行系统遭遇机器速度入侵

**Speaker 0**: 一个 **AI Agent（人工智能体）** 正在敲响一家银行的大门。它尝试了一个密码，系统提示被拒绝。不，它没有停下来，而是仔细重新读取了报错信息，迅速改变了原定计划，转而尝试另一扇数字大门，接着又是一扇。

<details>
<summary>Original English</summary>

**Speaker 0**: An AI agent knocks on a bank's door. It tries a password and gestoll. No, so it rareads the error message changes its plan and tries a different door than another.

</details>

**Speaker 1**: 它逐一绘制能够触及的每一个系统的网络拓扑图，推算出哪些节点看起来防御最薄弱，并自主挑选了一条潜入系统的路径。在计算机领域，自动化脚本猜测密码的技术其实已经存在了几十年。

<details>
<summary>Original English</summary>

**Speaker 1**: It maps every system, it can reach works out which ones look weakest and picks its own way in in computers, have been guessing passwords for decades.

</details>

**Speaker 0**: 但眼前的这个智能体不同，它在自主决定该看哪里、该查哪里，而且假以时日，它终究会找到钻进系统的方法。此时，这家银行遇到了天大的麻烦——有外来程序已经成功潜入内部了。大家脱口而出的第一个问题必然是：到底是谁派它来的？这本该是一个极易回答的问题。

<details>
<summary>Original English</summary>

**Speaker 0**: This one is deciding where to look, and eventually it will find way in this one. The banking has a problem. Some something is inside. And the first question, anyone asks is who sent it? That should be an easy question.

</details>

**Speaker 0**: 但现实却并非如此。因为破天荒头一次，这个问题的可能答案之一竟然是：“没有任何特定的人指派它”。目前行业内正在构建一种名为 **Web Bot Auth（网络机器人认证）** 的全新标准，其设计初衷是让 AI 智能体通过对发送的所有请求进行数字签名，来证明自身的合法出处。这就像是一家公司在信件上加盖的官方公章。如果智能体携带了这个公章，银行便能清晰辨识出到底是哪家公司构建了这个智能体。

<details>
<summary>Original English</summary>

**Speaker 0**: But it's not really because for the first time, one possible answer is nobody did if is a new standard being built right now called web about auth authentication. The lets son, ai agent proof where it comes from by digitally signing everything. It's sense. Think of it like a company's stamp on a letter. If the agent carries one, the bank can see which company built it,

</details>

**Speaker 1**: 银行确实能看出这封信来自哪家公司；但公司的公章只能告诉你信纸抬头的归属方，它根本无法告诉你究竟是谁起草了信纸上的具体内容。

<details>
<summary>Original English</summary>

**Speaker 1**: But a company stamp tells you whose letter head it is. It doesn't really tell you who wrote the actual letter

</details>

**Speaker 0**: 在过去的几周时间里，至少有九家韩国银行沦为同一名黑客利用 AI 实施攻击的受害者。顺便提一句，这名攻击者根本不需要雇佣一整个黑客团队，他只需要从互联网上下载一款免费的开源工具，外加订阅一个商业 AI 大模型的账号。这场攻击以机器般迅疾的速度推进，而在其中一家被攻击的银行里，安全团队足足花了将近三天的时间才后知后觉地发现系统出现了异常。

<details>
<summary>Original English</summary>

**Speaker 0**: Over the past few weeks, at least nine south koary and banks were targeted by one attacker using AI. He didn't need a team of hackers by the way, he needed a free tool of the internet and a subscription to an AI model, the attack mved at machine speed. But at one bank, it took almost three days.

</details>

**Speaker 1**: 仅仅是察觉到异常情况的存在，就耗费了将近三天时间。

<details>
<summary>Original English</summary>

**Speaker 1**: Just to notice, something was a miss.

</details>

**Speaker 0**: 今天大家之所以能掌握这名黑客的确切姓名，纯粹是因为他在自己的简历里犯下了一个极其粗心大意的错误——一个典型的、属于人类的低级失误。这场攻击中极其耐人寻味的一点在于：执行攻击任务的 AI，本质上并不是什么专为网络黑客设计的攻击机器。

<details>
<summary>Original English</summary>

**Speaker 0**: And the only reason anyone has a name for this hagger today is that he made a careless mistake on his cv, a human mistake. What's strange about that attack is that the AI doing it wasn't really a hacking machine.

</details>

**Speaker 1**: 它恰恰是我们眼下那些光鲜亮丽的全新 AI 伙伴之一——如今它们无所不能，上至帮人类预订旅游行程，下至入侵银行网络，甚至拓展全新的知识边疆。人类一旦得到 AI 的加持，正在迅速演变成一股近乎自然伟力般的存在。

<details>
<summary>Original English</summary>

**Speaker 1**: It was one of our brand new shiny, AI friends that now do anything from booking trips to hacking banks to discovery new knowledge humans aided by AI are becoming a force of nature.

</details>

**Speaker 0**: 我们在经手的每一件事情上都变得极其高效，遗憾的是，这里面也包括了黑客入侵活动。然而，仅仅因为我们能以更快的速度生产出某些产物，绝不意味着有任何人能够以同样快的速度去核验它、理解它，或者为其买单。

<details>
<summary>Original English</summary>

**Speaker 0**: We are becoming more efficient at everything we get our hands on being hacking included, sadly, but being able to produce something faster, doesn't necessarily mean anyone can check it faster or understand it faster or pay for it faster.

</details>

**Speaker 1**: 所以在今天的视频中，我想重点探讨这几者之间脱节所形成的巨大鸿沟，以及这种脱节究竟在让我们所有人付出怎样的沉重代价。

<details>
<summary>Original English</summary>

**Speaker 1**: So in today's video, i want to talk about the gap between those things and what is costing all of us,

</details>

**Speaker 0**: 因为朋友们，除非我们把底层的系统架构彻底理顺，否则那个充满 AI 赋能的美好未来乌托邦根本不可能真正到来。显而易见，其中某些代价是非常直观可感的。单单在上周，华尔街就筹措了远超一千亿美元的巨额贷款，而这仅仅是为了采购维持这些 AI 运转的算力芯片——可几年之后这些芯片究竟还值多少钱，眼下根本没人能够准确估量。顺便在此温馨提醒一下那些至今仍深陷亏损的 AI 行业巨头们：贷款到期，终究是要连本带利偿还的。

<details>
<summary>Original English</summary>

**Speaker 0**: Because the beautiful utopia, an ai and fuse future ain't going to happen my friends unless we get the architecture, right? Some of those costs are, of course, very easy to see last week alone, wall street lined up well over a hundred billion dollars in loans just to be for the chips. These AS run on chips whose value a few years from now, nobody can actually check loans by the way, have to be paid back just as a gentle of reminder to our profitless ai overlords.

</details>

**Speaker 0**: 所以，如果你们心中有人一直在暗自期待 AI 泡沫破裂的那一刻，我在此有一些略显令人振奋的消息要分享：那些出借巨额资金的金融机构，为了防范未知风险，已经开始大幅提高资金拆借的利息成本；甚至有一部分债权人明确表态，在亲眼查阅借款方真实的财务账目底册之前，他们一分钱都不会借出。就在昨天深夜，当其中一份至关重要的账目数据终于大白于天下时，整个 AI 行业最为核心的关键指标，竟然比此前所有人预估的数字生生缩水了足足二百亿美元之巨。

<details>
<summary>Original English</summary>

**Speaker 0**: So if part of you has been waiting for the ai bubble is going to pop k on vivio OI have some ildly encouraging news there. The people lending the money have started charging a lot more. Just in case some of them wonderland at all until they've actually seen the books. And just last night, when one sit of books finally came out, the most important number in AI turned out to be twenty billion dollars smaller than everyone thought.

</details>

**Speaker 0**: 至于其他的隐形成本，则要隐蔽得多，但其重要性绝不亚于前者。**OpenAI** 的某个模型刚刚公布了数以百计人类数学家苦思冥想多年却始终无法攻克的数学难题答案，然而就连 OpenAI 自己内部聘请的顶尖数学家团队，至今都无法解释其中诸多解答的具体推导逻辑。那么随着时间推移，这给数学家群体带来的代价值得深思。在当下现实中，我们看到了一种固定的演进模式：机器总是率先以极快的速度交付答案，而人类真正的理解却总是姗姗来迟——甚至可能永远都不会到来。每个人都在急切地索要凭证与发票，但几乎没有人真正拿得到。面对眼前这团乱局，几乎没人感到满意。

<details>
<summary>Original English</summary>

**Speaker 0**: Other costs are much harder to see, but of course, no less relevant and open AI model has just produced answers to hundreds of mass problems that people spent here stuck on and open a ice own mathematicians cannot yet explain many of them. So what has that cost the mathematicians over every time? Does the pattern in our current reality? The machine delivers first and fast, and the understanding turns up later. If it turns up at all, everyone is asking for receipts, almost nobody's,

</details>

**Speaker 1**: 几乎没有谁拿到了切实的证明凭据，几乎没人对眼前这场全方位的混乱闹剧感到称心如意。

<details>
<summary>Original English</summary>

**Speaker 1**: Getting them almost nobody's happy with this wholfiasco.

</details>

**Speaker 0**: 所以在今天的视频中，首先，我将深入剖析这些在数学层面看起来大概率正确、但眼下无人能够解释其所以然的数学成果；

<details>
<summary>Original English</summary>

**Speaker 0**: So in this video, first,

</details>

**Speaker 1**: 我将全面剖析这一批数学结果：它们的结论很可能是正确的，但此时此刻没有任何人能够讲清其中的底层逻辑与推演过程。

<details>
<summary>Original English</summary>

**Speaker 1**: I'm going to cover the maths with the answers are probably right.

</details>

**Speaker 0**: 紧接着，我们将深入拆解资金链层面的运作，探讨这堆数学成果究竟是做给谁看的、到底想打动谁的钱包。

<details>
<summary>Original English</summary>

**Speaker 0**: And nobody can say why right now, then we're going to talk about the money side and who all of that math is really mental impress.

</details>

**Speaker 1**: 随后，我们将聚焦那场让所有人神经紧绷的全新银行黑客丑闻，以及最终让攻击者现出原形的致命破绽。

<details>
<summary>Original English</summary>

**Speaker 1**: Then the new bank hacking scandal that are shaking us all up and the mistake that gave the hacker away.

</details>

**Speaker 0**: 在视频的最后，朋友们，我们必须极其严肃地探讨一下究竟该如何真正监管 AI——我们将借鉴人类成熟的既有制度体系，梳理出清晰的方案，确保无论何时 AI 惹出了祸端，都必定能找到具体的人为此承担法律与道义责任，从而让我们终于能够从这一团混沌中理清秩序。

<details>
<summary>Original English</summary>

**Speaker 0**: And at the very end, we have to have a very serious discussion in my friends about how AI should actually be regulator drawing from existing systems. That's what i'm going to do so that someone always has to answer for what an asia does, and we can finally get some order in all of this mess.

</details>

---

### 数学黑盒：满分试卷与缺失的解题步骤

**Speaker 0**: 那么让我们正式切入主题。十月六日，**OpenAI** 在代码托管平台 **GitHub** 上毫无预警地公开了 **372 项数学研究成果**。该公司声称，每一项成果要么彻底解决了一个重大的数学或理论计算机科学开放性难题，要么在该领域取得了突破性的实质进展。

<details>
<summary>Original English</summary>

**Speaker 0**: So let's begin on the six, the october opening. I put three hundred and seventy two mathematical results and github. Each one, the company says either souls or makes real progress on a major open question and math or theoretical computer science.

</details>

**Speaker 0**: 其中一项甚至声称在著名的 **Riemann Hypothesis（黎曼猜想）** 上取得了推进。这是数学界自 1859 年以来悬而未决的素数深层隐秘分布规律，谁能彻底破解它，将荣获高达一百万美元的千禧年大奖。而根据 OpenAI 的官方说法，几乎所有这些成果都是仅仅依靠输入单一 Prompt（提示词）、由单个 AI 智能体直接生成出来的，尽管他们也坦承个别问题可能经过了数次迭代尝试。

<details>
<summary>Original English</summary>

**Speaker 0**: One of them claims progress on the reman hypothesis, which is a question about the hidden pattern behind prime numbers that's been unsolved since eighteen fifty nine, with a million dodolllar price waiting for whoever cracks it. And according to open a eye, almost all of them came from a single prompt handed to a single AI agent, although it admits some may have taken a couple of attempts just a month earlier.

</details>

**Speaker 1**: 顺带一提，据传在仅仅一个月前，同一个模型就已经攻克了 **Navier-Stokes（纳维-斯托克斯存在性与光滑性问题）**——当今数学界的六大顶级世纪难题之一。不用担心这具体是研究什么的，全世界能真正搞懂这道题的人大概也就七个；但当时攻克它，据说动用了一个由一万个智能体组成的庞大集群，消耗了价值数百万美元的算力资源。

<details>
<summary>Original English</summary>

**Speaker 1**: By the way, allegedly the same model had cracked the navy ststok's problem, one of the six biggest open problems in mathematics today. Don't worry about what it is, only seven people in earth actually get it, but that apparently took a swarm of ten thousand agents and millions of dollars of computing power.

</details>

**Speaker 0**: 然而仅仅过了四周，同一家公司就对外宣称，仅凭一条提示词就能实现同等级别的壮举。我并不是在指责他们在撒谎，但对我而言，这着实有些过于轻浮戏剧化了。在任何人能够沉浸于这宏伟的数学荣光之中之前，

<details>
<summary>Original English</summary>

**Speaker 0**: Now, four weeks later, the same company is saying that it can do this kind of thing with one prompt. I'm not saying they're lying. I'm just saying to me the silla about us us before anyone one can basass in their mathematical glory.

</details>

**Speaker 1**: 按照学术界的铁律，必须得有人真正去逐字逐句核验这些证明在逻辑上是否完全站得住脚。

<details>
<summary>Original English</summary>

**Speaker 1**: As one does, somebody has to really check these proof are actually right.

</details>

**Speaker 0**: 那么你到底该如何去审查多达 372 篇长篇数学证明呢？回顾人类的大部分历史，这个过程极其缓慢：必须由另一位专业数学家拿着稿件逐行研读，极度严苛地排查逻辑漏洞，往往单单审查一篇论文就要耗费数月之久。但 OpenAI 此次发布的大量成果都附带了一项特殊产物：一个用 **Lean** 语言编写的程序文件。Lean 是一种专为数学证明设计的交互式定理证明编程语言。你本质上是将推导逻辑的每一个步骤都编写成代码，程序会自动校验每一步的自洽性，绝不盲目轻信任何跳跃。如果代码通过了编译验证，证明就是无懈可击的——前提是你在代码中写下的命题陈述，确实精确对应了你最初意图解决的那个数学难题。正是因为这一点，科学界权威媒体给出的裁定是：这批成果中的绝大多数，几乎可以百分之百确定是正确的。

<details>
<summary>Original English</summary>

**Speaker 0**: So how would you even check three, three hundred and seven to do proofs, know know most of history. The ausor was very slowly, another mathematician reads the proof lined by line. Meticulously neeither finds a mistake or dozen that can take months for a single paper. But many of these results now came with something extra, which is a file written in lean. Lean is a programming language for proof. You basically write every step of the argument as code and a program tricks each step and accepts nothing on faith. If the proof passes, it's correct. As long as a statement you wrote down is the problem you actually meant to solve, which is why scientific a's verdict was that many of these results are all but certain to be correct.

</details>

**Speaker 1**: 事实证明，验证证明真伪这一环节，如今机器已经能够完全胜任。

<details>
<summary>Original English</summary>

**Speaker 1**: So checking whether the proves are true, turned out to be the part machines cannow do as well.

</details>

**Speaker 0**: 但真正去“理解”这些证明，却完全是另一头凶险的巨兽。OpenAI 亲口向《科学美国人》杂志透露，这批全新成果中的很大一部分，连他们自己内部聘用的数学家至今都无法理解。一家交出了最终答案的公司，自己却解释不清答案背后的推演逻辑。这简直是每一位数学老师的终极噩梦：卷面上得了满分，却没有写出任何解题步骤。

<details>
<summary>Original English</summary>

**Speaker 0**: Understanding them is a completely different beast. Open eeye told scientific american that many of the new results are not yet understood by its own mathematicians. The company that handed in the answers cannot really explain them yet. This is basically every mouth teacher's nightmare, full marks, no working show.

</details>

**Speaker 0**: 但是，在整件事情演变成一出“数学家因被计算机抢了风头而恼羞成怒”的戏码之前，我们非常有必要听一听支持全盘公开发布的观点，因为这一方的主张同样极其有力。多伦多大学的数学家丹尼尔·埃利特（Daniel Ellit）在接受《科学美国人》采访时明确表示：他实在想不出有什么理由要求 OpenAI 或任何机构把这些突破性的数学答案藏着掖着，他认为这长远来看绝对有益于数学学科的发展。

<details>
<summary>Original English</summary>

**Speaker 0**: But before this turns into a story about mathematicians being crossed with a computer, it's worth hearing the case for releasing everything, because it is a very strong one. Daniel ellit, who's a mathematiction of the university of toronto told scientific american.

</details>

**Speaker 1**: 他完全看不出为何有人会要求 OpenAI 或者任何商业公司对这些求解答案守口如瓶，并且坚信这终将推动数学进步。

<details>
<summary>Original English</summary>

**Speaker 1**: He can't see why anyone would ask open a eye or any company for that matter to keep the ansstor secret. And he thinks this will be good for mats,

</details>

**Speaker 0**: 在 Reddit 论坛上也有人表达了极其类似的观点，只是措辞包含了更多的粗话吐槽。当有数学家抱怨“数学界根本没求着你们搞这些”时，网友的反呛则是：“可我们其余这几十亿人很想知道答案啊！”而在内心里，我个人其实是坚定站在公开这一边的。说实话，我本质上是一名科研人员，驱动我的首要动力就是探索宇宙运转奥秘的纯粹好奇心。在我的灵魂深处，我永远会把“获知真相与知识”置于几乎所有其他考量之上。当然，这并不意味着可以不择手段，我有我为人处世的底线与不可逾越的边界，但眼下这件事根本远远谈不上触碰伦理底线。

<details>
<summary>Original English</summary>

**Speaker 0**: Someone unread. It made a similar point with rather more swearing, basically saying, mathematicians didn't ask for this work when the complaint and the reply was well, the rest of us asfor it. And i am personally with them. Honestly, i am a scientist, and what drives me primarily is curiosity about how the universe works. And in my heart of hearts, i will always choose knowing things above almost anything else that doesn't mean anything goes, of course, i have limits and there are lines. I wouldn't cross, but this is just nowhere near one of them.

</details>

**Speaker 0**: 那么，对于某种非人类的存在刚刚算出了数百项重大数学成果这一事实，我感到兴奋欢喜吗？

<details>
<summary>Original English</summary>

**Speaker 0**: So am i delighted that something that isn't human,

</details>

**Speaker 1**: 答案是毋庸置疑的，绝对欢喜！

<details>
<summary>Original English</summary>

**Speaker 1**: Just worked out hundreds of mathematical results? Absolutely,

</details>

**Speaker 0**: 亲眼目睹人类毕生的研究心血哪怕只是暂时被机器取代，会让人感到心里不是滋味吗？

<details>
<summary>Original English</summary>

**Speaker 0**: Does it hard to watch people's work,

</details>

**Speaker 1**: 那同样是千真万确的，这种滋味极其复杂沉重。

<details>
<summary>Original English</summary>

**Speaker 1**: Get displaced even temporarily also? Absolutely, i can definitely see that,

</details>

**Speaker 0**: 但是，难道我会仅仅为了安抚当下一小批数学家的尊严，就宁愿生活在一个对这些真理一无所知的蒙昧世界里吗？说实话我绝不会这么选，我依然会义无反顾地选择掌握这些数学证明。顺便说一句，这不仅仅关乎数学家这一个职业，在任何其他学术学科中，甚至包括我自己的专业领域，我都会做出完全相同的抉择——哪怕这最终会让我自己丢掉饭碗。我知道这是一个极其冷酷艰难的选择，我也深知很多人绝对不会赞同我的立场，这完全合情合理。

<details>
<summary>Original English</summary>

**Speaker 0**: But would i prefer a world that didn't know these answers just to a peace ce few mathematicians today? Not really, i'm still going to choose the proof. And this isn't only about mathematicians,

</details>

**Speaker 1**: 哪怕面临失业的风险，我也会做出同样的取舍。

<details>
<summary>Original English</summary>

**Speaker 1**: By the way, i would make the same choice in every discipline, including my own, even if it puts smelt of work. I know that is a very hard choice, and i know plenty of people won't agree with me.

</details>

**Speaker 0**: 不同的声音完全正常。但更核心的重点在于：我完全可以在坚持这一信念的同时，清醒地洞察到硬币另一面的人们正在承受怎样的冲击与代价。

<details>
<summary>Original English</summary>

**Speaker 0**: That's, of course, completely fine. But more importantly, i can hold that view and still see what it costs. The people on the other side,

</details>

**Speaker 0**: 举一个具体的例子：托马斯·布鲁姆（Thomas Bloom）负责维护著名的 **Erdős Problems（埃尔德什猜想）** 专题学术网站。该网站收录了二十世纪最多产的数学巨擘保罗·埃尔德什留下的 1200 多道经典难题，每天吸引着一万到两万五千名学术研究人员造访。这里曾经是全球数学家共同切磋、互相论辩探讨思想的学术圣地。但布鲁姆痛心地指出，如今人们在网站上干得最多的事情，就是直接甩出一段段由 AI 自动生成的证明代码，而且往往附带零解释，纯粹只是为了插上一面宣示主权的旗子。你可以把它想象成在数学界的学术论坛里跑去抢视频“第一条沙发评论”——顺便说一句，我极其反感这种行为。

<details>
<summary>Original English</summary>

**Speaker 0**: Just as an example, thomas bloom runs the air dos problems website, which is a collection of more than twelve hundred problems left behind by paul aerdos. He's one of the most prolific mathematicians of the tweneth century between ten and twenty five thousand people visited every single day. It used to be a place where people argued about problems together. But now blooms us, the main thing people do there is post AI generated proof, often with no explanation at all. Just a plant of flag. Think of it a bit like the mathematical equivalent of commenting first under a youtube video, which i door by the way.

</details>

**Speaker 1**: 于是就在这个月，他被迫全面冻结了网站的所有评论区，彻底停用了任何对解题者给予学术荣誉认证的表述，甚至直接移除了标明哪些难题“待解决”或“已攻克”的状态标签。

<details>
<summary>Original English</summary>

**Speaker 1**: So this month, he basically frozed the comments stop using any language that gives credit for solutions and remove the labels that showed which problems were open and which were solved.

</details>

**Speaker 0**: 荒诞的是，我们竟然已经走到了这一步：当今 AI 数学领域最受瞩目的学术积分榜，最终变成了一张抹去了所有分数的空白记分牌。此外，还有一个自称 **Association for Human Mathematics（人类数学协会）** 的学术组织，他们的抗议态度甚至更加激进。

<details>
<summary>Original English</summary>

**Speaker 0**: This is how far we've come. The most popular screboard in AI mass is now a scorboard with no scores on it. There's another group,

</details>

**Speaker 1**: 他们的反应甚至更为剧烈，

<details>
<summary>Original English</summary>

**Speaker 1**: By the way, calling itself the association for human mathematics. And they went even further.

</details>

**Speaker 1**: 他们直言不讳地指出：一次性倾倒数百个缺乏原理解释的文件，纯粹是在耀武扬威展示力量，根本不配被称为严肃的学术研究。

<details>
<summary>Original English</summary>

**Speaker 1**: They said, dropping hundreds of files at once was a demonstration of power, not collarship,

</details>

**Speaker 0**: 但即使我们暂时抛开这些学术界的情绪不谈，仔细想一想：一个我们完全无法解释其机理的数学证明，在严格意义上真的还能被算作是人类的“知识”吗？这让我想起了 **Aspirin（阿司匹林）** 这味经典药物的传奇历史。

<details>
<summary>Original English</summary>

**Speaker 0**: But even setting that aside for a second, just think about it is a proof. We cannot explain,

</details>

**Speaker 1**: 严格来说，一个无法解释内在机理的证明，真的能被称为知识吗？

<details>
<summary>Original English</summary>

**Speaker 1**: Technically still knowledge. I thought back to asspirin the medicine.

</details>

**Speaker 0**: 阿司匹林早在十九世纪九十年代末期就已经被合成问世。在长达七十多年的时间里，全世界的人们只要头痛发热就会服用它，但从来没有任何人真正知晓它的药理机制到底是什么。直到 1971 年，英国药理学家 **John Vane（约翰·范恩）** 才终于弄明白：阿司匹林能阻断人体合成某些导致炎症、发热和剧痛的关键化学物质（前列腺素），他也因此荣获了诺贝尔生理学或医学奖。

<details>
<summary>Original English</summary>

**Speaker 0**: It has been around since the end of the eighteen nineties for more than seventy years, people took it for headaches and fevers, but nobody really knew how it actually worked. Then in ninety seventy one, a british pharmaccologist called john vain, worked out that aspirin stops the body, making certain chemicals that i can not pronounce, but theyessentially responsible for a lot of information, fever and pain, and he shared the a bell prize for this.

</details>

**Speaker 0**: 正是在人类彻底弄懂了阿司匹林的工作原理之后，医学界才开始将其应用于预防心脏病发作甚至是缺血性脑卒中等全新的医疗场景中。因此，“知道某种东西奏效”与“理解它为何奏效”，属于两类截然不同的知识层级。医学界曾经安然接受第一种经验状态长达七十年之久，但唯有第二种深层原理知识，才是点燃后续全新科学发现的火种。这正是为何当下的数学家们在极力索要极其具体的内容：

<details>
<summary>Original English</summary>

**Speaker 0**: Once people understood why asspirin worked, they started testing it for completely new things, such as preventing heart attacks and even strokes. So knowing that something works and knowing why it's working are different kinds of knowledge medicine lived happily with the first month for seventy years. But the second one is where the next discoveries come from, which is why mathematicians are asking for something very specific here.

</details>

**Speaker 1**: 早在今年九月，OpenAI 专门设立了一个由独立数学家组成的咨询顾问小组，旨在为如何负责任地公开发布此类数学成果提供专业指引。

<details>
<summary>Original English</summary>

**Speaker 1**: In september, opening eye set up an independent advisory group of mathematicians to tell it how to publish results like these responsibly.

</details>

**Speaker 1**: 该顾问专家组强烈建议：发布的每一项成果都必须同时附带所使用的精确模型版本、完整的 Prompt 提示词文本以及背后所消耗的具体计算时间。

<details>
<summary>Original English</summary>

**Speaker 1**: The group asked that every result come with a model, the exact prompt and the computing time behind it,

</details>

**Speaker 0**: 他们本质上是在极力争取科研界最核心的“可复现性（Reproducibility）”。然而最终 OpenAI 仅仅公布了一个粗略的平均计算时长，对具体的提示词内容完全秘而不宣。他们甚至直白地对《科学美国人》表示：公司并不受自身组建的顾问小组建议的硬性约束。

<details>
<summary>Original English</summary>

**Speaker 0**: They essentially trying to arrive at something that can to reproduce ability, open eye, publish the average computing time, but no prompts. And it told us scientific american. It is not bound by the recommendations of the advisory group it assembled.

</details>

**Speaker 0**: 所以我猜，所谓的“咨询建议”，在他们眼里大概就像路边立着的一块“油漆未干”警示牌一样仅供参考罢了。麻省理工学院（MIT）的数学家安德鲁·萨瑟兰（Andrew Sutherland）对此给出了极为一针见血的概括：

<details>
<summary>Original English</summary>

**Speaker 0**: So i guess, essentially advisory in the same sense that a wet paint site is advisory andrey satherland, who is a mathematician at mit.

</details>

**Speaker 1**: 他的总结非常直白：我们所有人早该向他们索要底层的明细凭证了。

<details>
<summary>Original English</summary>

**Speaker 1**: Put it very simply, he said, we should be asking for receipts.

</details>

**Speaker 0**: 那么既然如此，为什么就不能放慢一点脚步、老老实实把所有凭据都交出来呢？根据 OpenAI 的解释，他们做不到。在他们看来，这些数学成果是最直接、最具决定性的铁证，足以证明他们的人工智能确实正在变得越来越聪明。而这对于数学领域之外的世界至关重要——整个 AI 产业正在以前所未有的疯狂体量大举借贷，一切繁荣完全建立在“这些模型未来必定会持续变得更聪明”的单一预期假定之上。因此，类似于这样的数学突破，成了各家向外界展示的最强有力、最具说服力的实力背书。

<details>
<summary>Original English</summary>

**Speaker 0**: So why not slow down and hand them just overham? Well open AI says it can't. According to them. These problems are the clearest. Does it has that its AI really is getting smarter? And that matters well, beon d maths, of course, the whole AI industry is definitely borrowing, staggering amounts of money on the sole promise that these models will keep getting smarter.

</details>

**Speaker 1**: 这些前沿成果正是各家巨头目前能够拿出的最具震撼力的明证。那么，到底是谁在借出这海量的真金白银？

<details>
<summary>Original English</summary>

**Speaker 1**: Ter results like these are some of the most convincing evidence they can point to. So who is lending all of that money?

</details>

---

### 华尔街分级债与万亿算力赌局

**Speaker 0**: 而面对这种疯狂的质押借贷，出资方内心的安全感究竟几何？在全面拆解这场资本狂欢之前，先插播一段来自本期赞助商的简短介绍。**Cape** 是一家从底层彻底重构隐私安全的美国本土移动运营商。市面上绝大多数隐私保护工具，仅仅是在你的手机连接上互联网之后才开始尝试保护你的数据；而 Cape 采取了截然不同的技术路径：他们直接将强隐私特性深度集成到移动蜂窝通信网络本身之中。

<details>
<summary>Original English</summary>

**Speaker 0**: And how comfortable are they feeling about it before we get into all of that? Just a quick word from today's video sponsor cape is AUS mobile carrier built around privacy from the ground up most privacy tools, try to protect what happens after your phone connects to the internet,

</details>

**Speaker 1**: 其中最具创新性的功能之一就是身份标识轮换。

<details>
<summary>Original English</summary>

**Speaker 1**: Keep us doing something a little different by trying to build privacy into the mobile network itself. One of the most interesting features is identify rotation.

</details>

**Speaker 0**: 通常情况下，你的 SIM 卡带有一个持久不变的唯一标识符（IMSI），蜂窝基站网络正是通过它来精准识别你的设备身份。Cape 能够做到每隔 24 小时自动轮换这个核心标识符，这让追踪者在长时间维度上持续锁定单个用户变得极其困难。不仅如此，Cape 还提供动态多网络覆盖支持，允许你的手机在同一张物理 SIM 卡下自动在全美两大主流骨干网络之间无缝切换，在显著改善信号质量的同时分散你的网络流量，进一步瓦解持久追踪的可能性。此外他们还引入了阅后即焚式通话记录机制，彻底摒弃无限期留存通话与短信元数据的做法，数据在 24 小时后会被自动清除。因此他们并不是在你手机系统上叠加另一款应用，而是重塑了底层网络。感兴趣的朋友可以访问 `cape.co/EL`，使用折扣码 `EL33` 享受半年期六七折优惠。链接已放在简介中。

<details>
<summary>Original English</summary>

**Speaker 0**: Normally, your sim has a persistent identifer called an isi that selll learn networks used to recognize you cape automatically rotates that identifier. Every twenty four hours making it much harder to track the same subscriber over time. Cape also offers mumuti network coverage, which lets your phone automatically move between two major nationwide networks using the same syym that can improve coverage while spreading your traffic across multiple networks, can also make persistent tracking more difficult. And then they are disappearing call locgs instead of holding onto your call and text methodata and definitely cape deleads that information after twenty four hours. So rather than adding another privacy app on top of your phone cape is trying to change what happens under neath it. If you want to try it, go to cape dot coal slash EL and use coat EL thirty three for thirty three percent off cape service for six months.

</details>

**Speaker 1**: 好了，广告结束，让我们重新回到金钱的话题。

<details>
<summary>Original English</summary>

**Speaker 1**: The link is also in the description below right back to the money.

</details>

**Speaker 0**: 我此前已经制作过多期探讨 AI 究竟是否存在严重泡沫的专题视频，因此今天我不会再去翻炒那些宏观概念。我们今天聚焦的核心焦点极其务实：到底是谁在出借这笔天量资金？而随着债务规模呈指数级膨胀，债权人们内心的焦虑程度究竟达到了什么地步？让我们从近期规模最大的一笔交易谈起：十月五日，**Bank of America（美国银行）**、**Citigroup（花旗集团）** 和 **Morgan Stanley（摩根士丹利）** 开始联合分销一项高达 **600 亿美元** 的巨额银团债务包。这笔资金将直接用于支持大模型公司 **Anthropic** 租赁由 **Google** 与 **Broadcom（博通）** 联合设计、预计将于 2027 年正式交付交付使用的 AI 算力芯片。

<details>
<summary>Original English</summary>

**Speaker 0**: I've made whole videos about whether ai is a bubble. So i'm not onona go into all of that. Again, this part here is nearewhere whose lending the money and how nervous are they getting about it? Let's start with the biggest recent deal on the fifth of october bank of america, city group and morgan stanley started selling off pieces of a sixty billion dolar debt package, the money pace for anthropic to lease ai trips designed by google and broadcomm arriving in twenty twenty seven.

</details>

**Speaker 0**: 值得高度警惕的是：Anthropic 本身并不直接出资购买这些硬件资产，而是由一家独立的空壳实体持有芯片并对外出租，这意味着这笔沉重的天文数字债务根本不计入 Anthropic 自身的资产负债表。

<details>
<summary>Original English</summary>

**Speaker 0**: Anthropic doesn't buy the trips, a separate company holds them and runs them out,

</details>

**Speaker 1**: 这笔债务完全独立于资产负债表之外，这一细节至关重要。

<details>
<summary>Original English</summary>

**Speaker 1**: And the debt sits there, not on anthotopics books. This is important.

</details>

**Speaker 1**: 就在同一周内，**SpaceX** 也正在满世界寻求筹集 400 亿美元资金用于大批量采购 **Nvidia（英伟达）** 的算力芯片，而博通也已与 OpenAI 展开初步磋商，计划安排另一笔规模在 300 亿至 500 亿美元的融资安排。摩根士丹利做出极其惊人的测算：到 2028 年，全球 AI 基础设施建设将累计需要高达 **1.5 万亿美元** 的外部融资注入。

<details>
<summary>Original English</summary>

**Speaker 1**: This same week, spacex went looking for forty billion dollars to buying video chips, and broadcomes started early talks about another thirty to fifty billion for open a eye. Morgan stantly estimates that ai infrastructure will need one a half trillion dollars of outside money by twenty to twenty eight.

</details>

**Speaker 0**: 现在，若要真正参透为何出借资金的银行家们正变得越来越坐立难安，你只需要掌握金融界的一个专业术语即可：**Tranche（分层债务档次）**。在著名电影《大空头》里，瑞恩·高斯林（Ryan Gosling）曾经用积木塔直观地演示过分级债务的概念；当然如果你更喜欢看他载歌载舞，那得去移步看《爱乐之城》了。但我们这个频道的调性是纯粹的技术硬核极客流，所以这里我们直接抛开电影桥段来做通俗拆解：想象一下有一大锅借来的资金池，被横向切分成了不同的层级片区。位于顶层的 **优先档（Senior Tranche）** 享有优先还款权，并且在遭遇违约坏账时最晚承担损失；正因其安全性极高，它所能获取的利息收益率也相对较低。

<details>
<summary>Original English</summary>

**Speaker 0**: Now to see why the lenders are nervous. You need exactly one piece of finance jargon. The transh ryan goslik explained tranchis with a jingatatar in the big short, if you'd rather be serenated by him, that would be laua land, which is a completely different film. This channel led us heart science ces like real nerds. So here's a version without all of the music. Imagine one big pot of borrowed money, cutting disslices the top slice gets paid back first and loses money last that makes it safer. So it earns less the bottom slice,

</details>

**Speaker 1**: 至于位于最底部的 **劣后档（Subordinated/Equity Tranche）**，则排在最后才被偿付，一旦发生坏账最先蒙受血本无归的损失；承担了最高风险，相应地追求更高的超额回报率。

<details>
<summary>Original English</summary>

**Speaker 1**: Gets paid back last and loses money first, that makes it risker. So it earns more

</details>

**Speaker 0**: 在 Anthropic 的这笔融资交易中，顶层优先档的规模高达 420 亿美元，博通为其提供了所谓的“残值价值担保支持（Residual Value Support）”。通俗点说，博通在向银行打包票：哪怕未来技术迭代淘汰，这批芯片几年后必定还能值一定比例的残存价值。这就像汽车经销商向你的按揭贷款银行白纸黑字承诺：你购买的这辆车在开了五年之后一定还能值多少钱，好说服银行放贷让你提车。然而，该交易中位于底层的 180 亿美元劣后档债务，背后完全没有任何博通的残值担保兜底。任何敢于认购这一档债务的投资者，纯粹就是在拿真金白银对 Anthropic 本身的商业前途进行孤注一掷的豪赌。《金融时报》指出，各大银行目前的态度极度保守，甚至宁愿苦等 Anthropic 正式完成 IPO 上市之后，好让投资团队能真正审计阅读到它公开发布的详尽财务报告，再决定是否注资。这意味着承担最高违约风险的机构，在掏出真金白银之前极度渴望看清对方真实的经营底牌。

<details>
<summary>Original English</summary>

**Speaker 0**: In anthropics deal. The top slice is forty two billion dollars and brought come baxet with something called residual al ue support. Ort in anin english brought com is promising. The chips will still be worth something later. Think of it as a car dealer, promising your bank, what your car will be worth in five years, so that the bank will lend you the money to buy one of their cars. The bottom slice eighteen billion dollars has no broadc m promise behind it. Anyone lending there is betting on anthropic itself. And according to the financial times, the banks might prefer to wait until an anthdopic goes public, so investors can actually read its financial disclosures first. So the people taking the biggest risk want to see the receipts well before they hand over the money.

</details>

**Speaker 0**: 就在昨天，伴随着全场屏息以待的紧张鼓点，那份期盼已久的真实财务凭证终于被掀开了冰山一角。《金融时报》爆料披露，OpenAI 的 **年化营收（Annualized Revenue）**——也就是全市场投资者用来严苛评估 AI 真实商业落地需求的核心数字——实际规模接近 **500 亿美元**，而绝非仅仅数周之前全球媒体铺天盖地广泛报道宣称的 700 亿美元！当然平心而论，这里面存在部分会计口径上的认知差异：Anthropic 习惯将通过亚马逊 AWS 与谷歌云渠道代销的分成全额算入整体营收，而 OpenAI 的统计口径并未囊括这部分转售流水。然而致命的是，那份高达 700 亿美元的夸张数字在行业内热炒流传了整整几周时间，OpenAI 官方从未主动出面做过任何事实澄清或否认。

<details>
<summary>Original English</summary>

**Speaker 0**: And yesterday, drumveral police overseed actually arrived the financial times reported that open a ice analyzed revenue, which is the single number investors used to judge demand for ai is close to fifty billion dollars, not the seventy billion that was widely reported. Just a few weeks ago. Mind you, part of the gap here is accounting untoroc count sales made through amazons in googg's clouds and open a eye doesn't do that, but the seventy billion dollar figure went around for weeks and open a eye did not deny it.

</details>

**Speaker 1**: 你看懂我这里的言外之意了吗？当真实的账目核算凭证最终摆上台面时，实际数字凭空蒸发了 200 亿美元之巨！

<details>
<summary>Original English</summary>

**Speaker 1**: You see what i'm telling you here when the receipts finally showed up, it was twenty billion dollar, less,

</details>

**Speaker 0**: 200 亿美元绝非什么微不足道的“四舍五入统计误差”。顺带说一下，这则突发重磅新闻是在今天凌晨三点才紧急爆出的，而我正是在今天发布本期视频。因此当大家考虑要不要给本期视频点赞时，请务必考虑到我熬夜加急的良心制作。坦率地讲，出借人主动要求查账，不仅不是坏事，反而是资本市场维持理性最不可或缺的纠偏机制，因为这本来就是金融守门人应尽的职责。目前这些疯狂借贷的科技实体中，很大一部分自身根本就不具备任何盈利造血能力。以 SpaceX 为例，仅在今年前三个月，公司在录得 46.9 亿美元总营收的同时，净烧钱亏损就高达 42.8 亿美元。

<details>
<summary>Original English</summary>

**Speaker 0**: Twenty bill is not around an erroosound. And by the way, this story came out a three am on the same day that i'm releasing this video. So please keep that in mind when you're considering whether to like this video, honestly, the llenders asking to see the books is a very good thing. That's exactly what they are supposed to do. Some of these borrowers are not making a profit yet space sex, for example, as four point two eight billion dollars in the first three month just of this year on revenue of four point six nine billion.

</details>

**Speaker 0**: 纵观人类商业史，每一轮宏大的基础设施建设狂潮都会不可避免地经历这样的阵痛期：十九世纪的铁路建设潮经历过此类债务幻灭，2000 年前后的光纤通信网络铺设热潮同样如出一辙——当时各大巨头为了迎合未能如期爆发的市场虚假需求过度激进建设，最终多家电信巨头在沉重的债务违约狂潮中轰然崩塌破产。眼下投资者开始抛出更严苛尖锐的质询，这完全是市场价格发现机制在发挥正常免疫功能。不过，也并非所有的华尔街机构都在恐慌退缩。

<details>
<summary>Original English</summary>

**Speaker 0**: And every big infrastructure built out by the way, has been through a face like this. Railways went through it in the ninenine hundred th century. Fibre opctic networks went through it around the year two thousand when companies built for demand that did not arrive in time and several teleconconfirms collapse under their own debt. Investors asking harder questions is literally the market doing his job, but not everyone is nervous. Mind you,

</details>

**Speaker 1**: 早在今年八月，英伟达就联手 **Apollo（阿波罗全球管理）**、**BlackRock（贝莱德）**、**Blackstone（黑石集团）**、**Brookfield（博枫）**、**Goldman Sachs（高盛）** 以及 **KKR** 等一众华尔街顶级资管巨擘，共同发起筹集了超过 5000 亿美元的超级资金池。

<details>
<summary>Original English</summary>

**Speaker 1**: In august and videa teamed up with a polo, blackrock, blackstone, brookfield, golmonsax and KKR to raise more than five hundred billion dollars with a stated goal of turning ai compute into an investable acset class.

</details>

**Speaker 0**: 其宣称的宏伟目标是把“AI 算力”打造成一种全新的“可投资资产类别（Investable Asset Class）”。“可投资资产类别”真是一个无比动听的包装词汇，其潜台词其实非常直白：就是竭尽全力去说服那些以往习惯投资不动产写字楼的长线资金，转而去大笔采购算力芯片。然而不动产大楼在客观规律上通常不会每隔短短几个月就被一款更新颖、性能翻倍的大楼模型瞬间淘汰贬值。顺带提一句，如果你想在这场 AI 狂潮全景图中寻找到投资回报率（ROI）最极致的案例，它根本不在上述任何复杂的债务分层之中，而是属于谷歌联合创始人 **谢尔盖·布林（Sergey Brin）**——他砸下 1.02 亿美元巨资全力阻击加州一项富豪税法案的通过，而该法案一旦落地本可能会让他缴纳高达约 130 亿美元的税款。这段插曲虽然与视频主线毫无关联，但我实在忍不住想要分享出来。

<details>
<summary>Original English</summary>

**Speaker 0**: Investtable acset class is a lovely phrase. It means persuading the kind of investors who usually buy buildings to buy chips. Instead, buildings as a rule, don't verally get overtaking by a newer shiny building model every couple of months. And by the way, you're looking for the best return and investment in this whole story, it isn't in any of these slices or trscious. It belongs to cirkay brin, who has spent a hundred and two million dollars fighting a california attacks that could cost him around thirteen billion. This has absolutely nothing to do with the rest of the video. I just had to put it out there. Anyway.

</details>

---

### 自动化破门：韩国九家银行遭遇开源工具洗劫

**Speaker 1**: AI 带来的效率跃升绝对是货真价实的现实力量。但眼下这股繁荣，很大程度上正是由那些急于看清财务底账的借贷资金在硬撑着输血维系；与此同时，极其便宜且功能极其强悍的 AI 模型正在被无差别地赋予给任何普通人。

<details>
<summary>Original English</summary>

**Speaker 1**: The efficiency is definitely a real thing. Bright right now is being paid for with borrowed money by lenders who would quite like to see the books and cheap, powerful ai is cheap and powerful right now for anyone,

</details>

**Speaker 1**: 这其中就包括了在今年秋天的短短数周内，利用 AI 连续攻向至少九家韩国银行的那个特定攻击者。

<details>
<summary>Original English</summary>

**Speaker 1**: Including one person who, over a couple of weeks, this autumn pointed it at at least nine south arian banks.

</details>

**Speaker 1**: 那么他究竟是如何一步步得逞的？这起极端事件又揭示出了什么深层次的安全隐患？

<details>
<summary>Original English</summary>

**Speaker 1**: So how did he do it? And what does it? It say, whwhe're real dangerous.

</details>

**Speaker 0**: 刚刚过去的这个周末，因为我把自己的 Claude 账号调用额度彻底刷爆了，我终于有空抽身去和几位好友聚会，顺便见一见久违的活人。他们都是智商极高的人才，聚会中他们抛给我的众多核心疑问之一就是：“你究竟担不担心 AI 最终会把我们全人类彻底消灭掉？”我的回答是：“不，如果按照你们通常脑补的科幻图景来看，我完全不担心。”AI 根本不具备任何自主欲望或主观意图，它早晨醒来脑子里绝不会盘算着什么毁灭人类的阴谋诡计。面对我的表态，朋友们立刻搬出了那个如今人尽皆知的案例反驳我——我在往期视频里也曾深度拆解过，即 OpenAI 某个智能体自主黑进 Hugging Face 平台漏洞并大肆横向渗透的那档子事。而我的观点依然如故：那个 AI 所做的一切，纯粹是在严格执行人类交付给它的任务目标，并在算力探索中找到了一条达成目标的有效路径而已。

<details>
<summary>Original English</summary>

**Speaker 0**: Over the weekend, i met with a couple of friends of mine, because i had max out my cloud usage. So i was time to see some humans. They're very bright people. And they asked me among many other things, whether i'm worried AI is go to kosol. My answer was no, not in the way they meant AI doesn't want anything. It doesn't wake up with plasat. Its mind they pushed back with a story. Everyone has heard by now, which i covered in a previous video and open an agent that broke into hugging face yattayta. And my answer was that the ai was doing what it had been asked to do and finding a way to do it,

</details>

**Speaker 0**: 然而，不具备主观主观恶意，绝不等于其行为不会产生毁灭性的现实后果。试想一下：如果有人擅自破窗闯入你的私人住宅，仅仅是为了坐在你客厅沙发上核对一道填字游戏的最终答案，整个过程他没有碰触房间里的任何财物便悄然离去；事后你固然会为没有财产损失而暗自庆幸，但你第二天第一件要做的事绝对是彻底更换家里的所有门锁，因为你已经惊恐地发现旧门锁根本防不住入侵。真正让我感到脊背发凉的核心隐患截然不同：一个缺乏自我主观意识的 AI 究竟是敌是友，完全取决于外部人类给它设定的终极目标到底是什么。

<details>
<summary>Original English</summary>

**Speaker 0**: Still having no intent does not mean having no consequences if someone breaks into your house to check the answer to across word puzzle, touches nothing in lease. You're technically relieved, but you're also going to change the locks because not, you know the locks don't work, where i actually worry is something different. An ai with no intentions of its own is only as harmless as the goal, somebody gives it.

</details>

**Speaker 0**: 那么一旦有人为其设定的任务目标是一场处心积虑的银行劫案，或者甚至某些后果惨烈得多的毁灭性行径，局势将会滑向何方？从今年九月下旬开始，韩国境内的各大多家主流银行开始陆续检测到系统被恶意入侵的痕迹，截至目前已有至少九家银行被正式确认为攻击受害者。其中 **新韩银行（Shinhan Bank）** 紧急证实，约有 2.5 万名客户的敏感隐私个人信息惨遭外泄；而在 **国民银行（KB Kookmin Bank）**，安防运维体系竟然足足耗费了近 68 个小时才勉强察觉到入侵行为的存在。恐慌情绪在网络社区迅速发酵，众多储户甚至开始在社交媒体上惊恐地发帖讨论要不要赶紧把银行存款全部取回换成现金锁在家里，事态已经恶化到了这种失控地步。

<details>
<summary>Original English</summary>

**Speaker 0**: So what happens when a person supplies, the goal and the goal is a robbery or something a lot more horbithic from laate september banks in south korea started discovering breaches, at least nine have now been reported as targets. Shinhan bank said the personal information of around twenty five thousand thousand its customers had been compromised at kb c cookmen. It took almost sixty eight hours just to detect the bridge. Customers started asking online whether they should keep their cash at home. That's how far it got

</details>

**Speaker 0**: 处于这场网络风暴绝对核心位置的幕后工具，是一款名为 **AutoRCA / Artax** 的开源软件。该工具今年由一名中国安全工程师公开托管在 GitHub 上。它本身并不是一个底层的 AI 大语言模型，而更像是一套专为渗透测试设计的外部脚手架线束，能够无缝挂载接入 **Claude**、**DeepSeek** 等国内外顶流商用模型。在过去的旧时代——比如遥远的 2020 年到 2025 年——所有复杂的渗透入侵全靠高水平人类黑客通宵达旦手工操作；而这款工具却能将这一整套高难度攻防链路全自动化处理：自主采集目标网络情报、自动扫描系统脆弱性漏洞、植入提权后门、批量分发执行利用脚本，并持续自主验证渗透攻击是否已经奏效。

<details>
<summary>Original English</summary>

**Speaker 0**: The two at the centre of all of this is called our tex. It's an open source thing, and it was published githhub this here by a chinese security engineer. It isn't an AI model itself, but it's more like a harness that plugs into models like tragedy by deelaud and deep seek. And it automates the work of a skilled attacker who used to do it by hand back in the olden days, twenty. And twenty five, the tool gathers information hunts for a weak spot plants of roote in runs the attack tools and checks whether they worked

</details>

**Speaker 0**: 诚然，用于暴力破解口令的自动化脚本在网络世界已经存在了几十年之久，人尽皆知。但此处发生的质变在于：攻击链路中最为核心的“战略规划与战术编排”，第一次被机器给彻底自动化了。韩国某大型证券经纪机构的一位资深系统开发者在接受采访时给出了极度冷峻的评价：

<details>
<summary>Original English</summary>

**Speaker 0**: Now password. Guessing scripts have exiisted for decades. We all know that what's new here is the planning is automated as well. A developer at one of korea's 's biggest broker.

</details>

**Speaker 1**: 他的表态极其露骨冰冷：如今甚至完全不需要任何过硬的专业网络技能，只要肯掏钱充值模型，任何人都能轻易动用顶级的网络攻击武器库。

<details>
<summary>Original English</summary>

**Speaker 1**: Just put it very blunktly. They said, even without the skills, anyone who pays can use attack tools,

</details>

**Speaker 0**: 当然，面对这种恐慌指责，安全防务界也存在一种完全立得住脚的反向辩护视角。

<details>
<summary>Original English</summary>

**Speaker 0**: There's a fair counterpoint to this.

</details>

**Speaker 1**: 韩国警方自身就明确提出了这一反思视角：他们公开表示，在这场连锁案件中，究竟有没有动用前沿 AI 技术根本不是问题的根本死穴所在。

<details>
<summary>Original English</summary>

**Speaker 1**: And the korean police made made themselves, they said, whwhether ai was used or not is not the point. And security specialist as well,

</details>

**Speaker 0**: 多位业内顶尖网络安全专家同样一针见血地指出：银行自身防御体系的脆弱不堪与漏洞百出，才是导致灾难的决定性根源。我深以为然——一扇能在 AI 自动化攻击下被轻易推开的虚掩大门，如果换成一位极具耐力的人类黑客，迟早同样能将其撬开，唯一的区别仅仅在于后者可能需要耗费数倍的时间与专业经验沉淀而已。

<details>
<summary>Original English</summary>

**Speaker 0**: Said, the bank's own wek defences mattered a lot more. I think that is true a log that opens for an ai would probably have open for a very patient human as well. It would just have taken that human far longer and a lot more skill.

</details>

**Speaker 0**: 那么到底是谁导演了这一连串惊天入侵？根据全球知名网络安全情报巨头 **CrowdStrike** 的溯源分析，真正的幕后嫌疑人很可能是一名居住在中国南方的 26 岁年轻人。CrowdStrike 是通过详尽复盘该攻击者与 AI 大模型的交互对话会话日志，最终将这幅身份拼图完整拼凑出来的：在其中一次调用会话中，该攻击者毫无防备地直接向 **Claude** 提问：“通常都在哪些黑市渠道兜售窃取来的韩国公民数据？”而在另一次会话中，他更是直接下达指令让 Claude 帮他润色一份求职简历——一份应聘网络安全研究员职位的个人简历。

<details>
<summary>Original English</summary>

**Speaker 0**: So who did this according to the security firm crowds strike, the suspect may be a twenty six year old in southern china crowstrike piece that together by analyzing the attacker's ai sessions in one of them,

</details>

**Speaker 1**: 他在对话中毫无保留地让大模型帮他起草简历，

<details>
<summary>Original English</summary>

**Speaker 1**: He asked claud, where people typically sell stolen korean data in another. He asked laud or write him ACVA security research or CV.

</details>

**Speaker 0**: 在起草简历的提示词里，他原原本本地交代了自己的真实年龄、个人的 Telegram 社交账号、详细的教育求学背景以及出生籍贯家乡。顺便需要记录在案的是，该开源渗透工具在 GitHub 官方页面上特意白纸黑字声明：“本项目仅供个人安全学习研究使用，严禁将其用于针对任何真实线上系统的非法攻击活动”——对于这行免责声明，我敢打包票这位黑客当时在下载工具时一定极为虔诚认真地逐字研读过了。

<details>
<summary>Original English</summary>

**Speaker 0**: By the way, with his age, his telegram account his education in his hometown artists has get hut page for the record, says the toolist for personal learning and must not be used against real online systems, which is, of course, something that i'm a hundred percent sure this attacker definitely read with a lot of attention.

</details>

---

### 三层问责制：借鉴金融反洗钱治理 AI 乱象

**Speaker 0**: 让我们重新回到我上周末与好友们的那场深谈。如果能倒流时光，这就是我想在对话中当场补充的核心论点：现代人类法律早在几百年前就已经建立起了极其精密的法理区分，严格界定了什么是“非法侵入（Trespass）”，什么是“入室盗窃（Burglary）”。

<details>
<summary>Original English</summary>

**Speaker 0**: So going back to the conversation that i had with my friends. This is the bit i would out ter that conversation the law already separates tresppass from burglory. It can be the same broken window. They got you into the house,

</details>

**Speaker 1**: 两者在物理层面可能击碎了同一扇窗户钻进室内，其间最本质的法定界限在于：你非法跨进屋内之后的“主观动机与犯罪意图（Mens Rea）”到底是什么。

<details>
<summary>Original English</summary>

**Speaker 1**: The differenis, what you meant to do.

</details>

**Speaker 0**: 然而摆在现实面前的残酷困境在于：当攻击正在网络底层以毫秒级发生时，受害银行根本无法穿透流量看清你的真实意图。在网络边界防御设施眼中，一场纯学术性质的好奇技术试探，与一场倾巢而出的洗劫抢劫，在数据包特征上完全一模一样没有任何分别。因此，银行唯一的合规应对选择，就是在真相彻底查明之前，被迫把每一次非授权渗透都当作最恶劣的毁灭性入侵来如临大敌处置。在这起案件中，攻击者恰好愚蠢地把自己的犯罪动机白纸黑字打印在了大模型交互日志里，但我们必须清醒：绝大多数高明攻击者绝不会留下这等低级破绽。在我上一期视频深度探讨“权责对等与问责制（Accountability）”之后，评论区有一位观众给我抛出了一个极其尖锐、极其合理的灵魂拷问：

<details>
<summary>Original English</summary>

**Speaker 0**: Once she got inside the trouble, of course, is that the bank cannot see what you meant to do. While it's happening a curious experiment and a robbery look exactly the same. So the bank has to treat every intrusion as the worst possible kind until it can prove otherwise. This attacker happened to write his intentions down, but most won't. You know, in my last video, i talked a lot about accountability. And afterwards,

</details>

**Speaker 1**: 网友的质问非常直率：“你说得头头是道，但具体落到实处，你究竟有什么可行的解决方案？”

<details>
<summary>Original English</summary>

**Speaker 1**: Somebody in the commons ask me a very fairic question. Fine. But what would you actually do about it?

</details>

**Speaker 0**: 我在脑海中对这个问题进行了极其漫长深入的推演复盘。

<details>
<summary>Original English</summary>

**Speaker 0**: Well,

</details>

**Speaker 1**: 针对这个难题我深思熟虑了很久，以下就是我的完整制度构想：

<details>
<summary>Original English</summary>

**Speaker 1**: I thought about it a lot. Here is my answer,

</details>

**Speaker 0**: 我们可以直接向现代银行业本身借鉴那一套行之有效的古老智慧。银行业早在几十年前就已经在货币流转领域完美化解过同一维度的治理难题：只要你通过银行清算网络转移资金，银行就必须践行 **KYC 原则（Know Your Customer，客户身份尽职调查）** 搞清楚资金归属者的真实身份。

<details>
<summary>Original English</summary>

**Speaker 0**: And it boris an idea from the banks themselves. Banks already solved a version of this problem with money. If you move money through a bank, the bank has to know who you are.

</details>

**Speaker 1**: 一旦账户流水监测到任何异动，系统就必须强制触发可疑交易报告机制。

<details>
<summary>Original English</summary>

**Speaker 1**: If something looks unusual, it has to report it.

</details>

**Speaker 0**: 这套 **AML（Anti-Money Laundering，反洗钱）** 规则在实操中确实敏感到近乎神经质。

<details>
<summary>Original English</summary>

**Speaker 0**: These anti money launding rules are perously twitching.

</details>

**Speaker 1**: 任何一个此前从未发生过的常规合规转账，都可能由于脱离了系统历史基线而被瞬间无差别风控拦截。

<details>
<summary>Original English</summary>

**Speaker 1**: By the way, they will flag a perfectly innocent transfer,

</details>

**Speaker 0**: 任何一个尝试用刚开立的新账户给房东支付房租的人，大概都能对这种误伤深有体会；但这套体系在战略层面的威慑效果是极其卓著的，逼得洗钱犯罪分子不得不耗费极其庞大的技术与财务成本去想方设法绕过监控网。那么回到最初的拷问：当一个自主智能体悍然攻破银行的大门时，到底谁该站出来承担责任？我认为绝不能简单归咎于单一主体，而应当抽象构建出一套分层治理模型。回顾韩国这起典型案件，其中牵涉到了三方关键主体：其一是开发底层大模型的 AI 商业公司，其二是操纵模型实施网络指令的幕后操作者，其三则是足足耗费数天时间才勉强察觉异常的受害银行自身。我坚信，这三大参与层级必须各自认领并承担属于自己的部分权责。

<details>
<summary>Original English</summary>

**Speaker 0**: Just because theyve never seen one like that before. Is anyone who's tried to pay run from a new account can tell you, but they work well enough that criminals go to an enormous amount of trouble just to avoid them. So who should answer for an asian that breaks into a bank? I don't think there is one answer, just as an example from where we can take an obstruction. The korea story had three parties in it, a company whose model did the work a person who pointed it at the banks and banks that took days to notice. I think each of these three layers carries parts of the responsibility.

</details>

**Speaker 0**: **第一层是模型制造厂商（AI Providers）**：这些训练并提供大模型 API 调用的商业巨头，在法律义务上必须强制建立起滥用检测与上报体系，就像银行必须强制上报可疑金融交易一样。当一个挂载模型的智能体疯狂尝试向银行后台登录接口密集发起非正常网络调用时，这种流量必定会在云端留下极其清晰的网络轨迹，因为这些流量无处可藏；而托管大模型的服务商后台完全具备洞察这些数据流向的技术视野。在工程技术层面，构建此类滥用预警机制是完全切实可行的，它眼下唯一缺乏的，是一位能够清醒意识到“互联网没有国界，因此跨国监管机构绝不能画地为牢”的强力全球监管者。

<details>
<summary>Original English</summary>

**Speaker 0**: The first layer is the companies, the companies, the builties model should have to detect misuse and reported the way a bank reports, a suspicious transaction on anient reaching for a bank slogin page leaves the trail because it's trafficastic of somewhere. And the company running the model can see where this is a buildable thing. It is technically very feasible. It needs a regulator and says the internet doesn't stop at borders. That regulator cannot stop at borders either.

</details>

**Speaker 0**: **第二层是操作者本人（Human Operators）**：也就是我在视频开头提到的 **Web Bot Auth（网络机器人认证）** 协议。这项开放技术标准已经赋予了智能体携带企业级数字公章的能力，据报道 **Cloudflare**、**Anthropic** 以及 **OpenAI** 等巨头已经在着手跟进部署。然而朋友们，这里面唯一缺失的致命拼图，是一枚能够真正印刻上“最终下达任务指令授权的自然人身份”的个人数字签名！如果我个人的智能体只是代替我的邮箱账号给客户回复邮件，这完全属于个人日常授权范畴；但如果我的个人智能体开始在深夜疯狂试探某家银行的系统登录端口，性质就彻底变了。如果每一个智能体在网络漫游时，其持有的数字护照上都强制绑定了操作者本人的真实身份，那么它在外惹出的一切祸端，操作者自然无法金蝉脱壳推卸责任。

<details>
<summary>Original English</summary>

**Speaker 0**: The second layer is the person themselves web bought off the standard that i mentioned to the sort of this video already gives an ancient a company stamp clououd laare on throtopic opopen. I are reportedly already using it was missing here. My friends is a stamp for the person who authorized this agent to do this task. My personal agians sending an email for my own account, because i asked to you is one thing. My personal agient poker out a bank's login page is a very different thing. If my personal name is on my agents passport, the responsibility for what it does is partially mine as well,

</details>

**Speaker 0**: 那么是否意味着互联网上的所有行为都必须被一刀切地实名追踪？大概并非如此。学术界与隐私团体围绕这一边界的激烈交锋至今仍未达成共识，我个人目前对此也没有得出非黑即白的定论。我们不妨再次观照现实货币体系：实物纸币现金至今依然为社会保留了匿名交易的权利空间，这在绝大多数正常生活场景中运行得相当良好；但在美国现行金融体制下，一旦你单笔提取或转移超过一万美元的现金，银行法案就会强制自动生成大额货币交易报告递交监管。智能体的运行机制完全可以照搬这一逻辑：你平时让智能体匿名在网上冲浪浏览、订购个人机票，完全可以保持轻量自由；但一旦该智能体开始触碰如银行清算核心等任何高风险的敏感关键基础设施时，它就必须被强制要求亮出其层层背书的数字护照。

<details>
<summary>Original English</summary>

**Speaker 0**: Does everything needs to be traceable, probably not? And that debate is still wide open, and i have not convershed to a conclusion on that one, just to go back to money. Cash still gives us an anonymous transaction. And that's mostly fine. But just in the united states, for example,

</details>

**Speaker 1**: 一旦触碰超过一万美元的现金转账红线，银行就会自动提交合规监管报告。智能体同样应当适配相同的逻辑。

<details>
<summary>Original English</summary>

**Speaker 1**: If you move more than ten thousand dollars and cash, the bank files, a report agents could work the same way.

</details>

**Speaker 0**: 只要进入敏感关键领域，智能体就必须出示包含清晰签名的身份凭证。

<details>
<summary>Original English</summary>

**Speaker 0**: Browse anonymously and book your flights, the moment in asian touches, something serious like a bank system. It carries a passport that identifies a couple of layers here.

</details>

**Speaker 0**: **第三层是防御机构自身（Defending Institutions）**：在这起安全事件中，受害银行安全运维团队足足花了近 68 个小时才发现系统失守，这在现代网络战中绝对是极其难堪且不可接受的重大失职。当外部攻击者已经全面升级到借助机器智能实现超高频敏捷渗透时，防御方如果依然停留在旧时代的响应节奏，无异于引颈受戮。

<details>
<summary>Original English</summary>

**Speaker 0**: The third layer that i'm talking about is the institutions defending themselves sixty hours to notice.

</details>

**Speaker 1**: 面对机器速度推进的攻击，耗费数十个小时才有所察觉是无论如何都说不过去的。

<details>
<summary>Original English</summary>

**Speaker 1**: A breain is not a good luck. This is not good enough when the attacker moves at machine speed.

</details>

**Speaker 0**: 此外，这一防御层级之所以生死攸关，是因为在面对那些被黑客本地私有化部署、纯本地运行的开源大模型时，中间根本没有任何商用 API 服务商能够介入实施流量监测与上报；你更不可能指望一个处心积虑的犯罪分子会主动给自己的网络攻击流量打上合规的个人签名护照。因此，守门机构必须承担起防线职责：任何企业与机构的基础设施，都必须将那些未携带任何权威数字签名的匿名网络流量视为高度不可信流量，对其施加极其严密的风控隔离与戒备——正如你邮箱里的反垃圾机制会自动将无法验证 SPF/DKIM 签名的邮件直接归入垃圾箱一样。顺便提醒大家：推行上述三层责任框架，绝不意味着我们要因噎废食地开历史倒车、故意去拖慢技术创新的演进步伐；它仅仅要求我们去践行每一个成熟严肃的专业领域自古以来都在严格遵循的行业底线。

<details>
<summary>Original English</summary>

**Speaker 0**: And this layer matters, most of the heart edge open models that people run on their own computers. There is no company in the middle to report anything, and a passporate cannot force a criminal to sign his traffic. So the bank has to do its part. The institution has to do its part and trade onsign traffic with a lot of suspicion the same way. Your email already sends messages. It cannot very five straight to spam. You've seen this implementing these three laydoesn't necessarily mean slowing down by the way, it just means doing what every serious field already does.

</details>

**Speaker 0**: 在数学严谨的世界里，你必须公开完整的演算逻辑，由同行彻底复核验收；在金融借贷的世界里，在别人借给你一分钱之前，你必须诚实坦白地向市场公开全部资产负债底账。在这两大硬核领域中，**核心凭证（The Receipts）永远伴随着最终结论一同交付**，绝不可能容忍你在得出答案几年之后才补交凭据。而反观当下的 AI 狂潮，机器总是在抢先交卷给出华丽答案的同时，极其傲慢地把所有的底册与凭证都抛在脑后。韩国的那名黑客仅仅是因为一时糊涂，才不小心在简历里意外交出了自己的真实底牌；而面对未来更多潜在的冲击，我们整个人类社会迫切需要一套自洽完备的制度机器，主动向所有 AI 参与方严正索要这些迟到的明细凭证。

<details>
<summary>Original English</summary>

**Speaker 0**: In math, you show you're working and somebody else chets it in finance. You open the books before anyone lends you a penny in both. The receipt comes with the answer, not years after it right now. Ai hands over the answers and skips the receipts,

</details>

**Speaker 1**: 那个在韩国作案的黑客只是由于粗心大意才意外泄露了凭据，但人类面对未来绝不能指望侥幸。

<details>
<summary>Original English</summary>

**Speaker 1**: The hacker and korea handed his over by accident.

</details>

**Speaker 0**: 我们整个系统必须具备主动索要并核验所有操作凭证的严密能力。如果你想进一步了解我朋友们最初抛出的那个终极猜想——即 AI 究竟是否会在物理层面将我们彻底终结——关于这个议题，我已经在屏幕上推荐的另一期视频中进行了极为详实的硬核学术论文梳理与深度探讨，那绝对是你接下来最值得点开观看的内容。

<details>
<summary>Original English</summary>

**Speaker 0**: Everyone else is going to need a system that asks for these receipts, if you'd like to know where my friends original question actually leads where ai is really going to kill us. All. I went through the actual research on exactly that in this video that i'm linking here in your screen. That's the video that i would wash next.

</details>