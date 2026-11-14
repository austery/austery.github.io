---
author: House of El - AI
date: '2026-05-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=WeKAjZU-JsE
speaker: House of El - AI
tags:
  - formal-verification
  - ai-reasoning
  - mathematical-proof
  - transfer-learning
  - ai-development
title: 超越非正式AI：Carina Hong与Axiom Math的验证式AI愿景
summary: 本期播客对话Axiom Math CEO兼创始人Carina Hong，深入探讨了其公司在形式化验证和AI数学领域的愿景与实践。Carina阐述了验证式AI如何通过形式化数学证明来提升AI模型的性能和推理能力，而非仅仅解决幻觉问题。她分享了Axiom Math在Pudnam竞赛中取得的卓越成就，并讨论了形式化验证在软件、硬件甚至未来通用人工智能中的巨大潜力，强调了协作与专注对于突破技术瓶颈的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Carina Hong
companies_orgs:
  - Axiom Math
  - Anthropic
  - OpenAI
  - Google DeepMind
  - AWS
  - Meta
products_models:
  - Lean
  - AXL
  - GPT
  - AlphaProof
media_books: []
status: evergreen
---
### 验证式AI的开放性与协作
**Carina Hong**: 但现在，我认为验证式AI首次开辟了协作——无论是人与AI的协作，还是在蓝图规划之前的人与人的协作。**Lean** 是一种基础，是一种形式化语言的验证。然后是人与AI的协作，就像我们现在看到的。未来是AI代理与代理之间的协作。我认为验证式AI旨在实现开放性，而非满足封闭行业的需求。我认为，验证不应该仅仅关注错误。对我而言，验证关乎扩展卓越，复合卓越。就像回到协作这一点，它让像**拉马努金**这样一位已经非常强大的数学家变得更强，验证帮助他扩展了卓越，使其能够向上和向外发展。

<details>
<summary>Original English</summary>

**Carina Hong**: But it's for the first time now I think verified AI is to [music] open up collaboration either it's human AI collaboration well before blueprinting that's human human collaboration and lyn was a grounding was a verification formal language and then human [music] AI collaboration like we're seeing now future AI agent agent agent like collaboration like I [music] think verified AI is for openness it's not for meeting the requirements of closed industries and I think just like I think verification should not be about oh I remember like you know there's this article like chatbots It's mixed up of is math solution to hallucination. Verification to me is not about lousiness. Verification to me is about scaling brilliance, compounding brilliance. It's like just kind of going back to the collaboration point. It's about Rammenujin being a much stronger mathematician. He was already a really strong one, but verification helps him extend the brilliance like both kind of like scale up and [music] scale out.

</details>

**Brandon Anderson**: 欢迎收听**Leen Space AR for Science**播客。我是**Brandon Anderson**。我在**Atomic AI**从事RNA疗法研究。今天我的搭档是**Mirror Omix**的CTO **R.J. Haneki**，他致力于空间转录组学。我们非常荣幸邀请到**Axiom Math**的CEO兼创始人**Carina Hong**。**Axiom** 在多个领域都引起了轰动。首先，他们在去年12月的**Putnam竞赛**中获得了满分。我认为他们还声称是第一个利用形式化验证来证明研究猜想的AI。而且，非常令人兴奋的是，就在昨天，他们宣布了一笔相当大的**A轮融资**。欢迎来到节目。

<details>
<summary>Original English</summary>

**Brandon Anderson**: Welcome to the **Leen Space AR for science podcast**. I'm **Brandon Anderson**. I build uh RNA therapeutics at **Atomic AI** and I'm joined by **R.J. Haneki** uh the CTO of **Mirror Omix** uh working on spatial transcrytoics. It's a pleasure to have **Karina Hong** from CEO and founder of **Axiom Math**. Um **Axiom** has made a splash [music] in several different areas. First they were they got a perfect score in the **Putinome** uh last uh December. I think they also had the claim of the first AI to prove research conjectures using formal verification and um very exciting they just yesterday [music] announced quite a large uh **series A**. Um yeah, welcome to the show. Thank you for having me.

</details>

**主持人**: 你们刚刚筹集了**2亿美元**，正如你的一位同事所说，这笔钱基本上相当于美国每年用于数学研究的全部预算。

<details>
<summary>Original English</summary>

**Host**: You just raised $200 million, which as one of your colleagues said, this is like basically the entire like US math budget for math research each year.

</details>

**Carina Hong**: 真的吗？

<details>
<summary>Original English</summary>

**Carina Hong**: Is that true? Actually,

</details>

**主持人**: 根据他的**LinkedIn**帖子，是的。

<details>
<summary>Original English</summary>

**Host**: according to his LinkedIn post, yeah.

</details>

**Carina Hong**: 哇。

<details>
<summary>Original English</summary>

**Carina Hong**: Wow.

</details>

**主持人**: 嗯，**2.5亿美元**是他们声称的年度数学预算。

<details>
<summary>Original English</summary>

**Host**: Uh 250 million is our apparently the annual uh math budget.

</details>

**Carina Hong**: 我们应该在数学研究上投入更多资金。

<details>
<summary>Original English</summary>

**Carina Hong**: We should spend more on math research. [laughter]

</details>

**主持人**: 是啊，有点悲哀，但是。

<details>
<summary>Original English</summary>

**Host**: Yeah, it's kind of sad, but

</details>

**Carina Hong**: 是啊，我知道。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I know.

</details>

**主持人**: 但无论如何，作为一个热爱数学的书呆子，这真的很酷。但我的意思是，当我听到这个消息时，我简直惊呆了，**2亿美元**，估值**16亿美元**。

<details>
<summary>Original English</summary>

**Host**: But anyway, like you know, as a you know, as a nerd who loves math, that's like really cool. But I mean I'm just like that kind of blew my mind like what [laughter] I heard that like okay so like yeah how is it 200 200 million I guess 1.6 billion valuation. Yeah I don't know.

</details>

**Carina Hong**: 是的。嗯，非常非常高兴能来到这里。此外，我认为这是一轮**A轮融资**，所以这是一个非常有趣且及时的播客。我们是一家成立七八个月的公司，所以这笔融资对我们意义重大。这是一个非常酷的里程碑。我们目前大约有30人。所以我想这笔资金将为我们提供所需的动力，以加速我们迄今为止强大的执行势头。我认为人们看待我们，有多种方式。人们认为我们是一家数学初创公司。数学初创公司，**Lean**初创公司。我们还做其他的事情，即形式化验证。我们认为验证是数学领域一个非常好的首选市场。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Um well super super excited to be here. Um also I think like you know this is a series A so it's very very interesting timely timely podcast. Uh we are like a seven eight months old company so it definitely means a lot to us. It's a really cool milestone. Um we're currently about like 30 people now. So kind of going into I think this amount of funding will like give us a fuel that we it needs to to to accelerate um the strong execution momentum that we have so far. Um I think like people think of us like there are many kind of ways to think about people think of as us as a math startup. So math startup lin startup the other obviously things that we do um that are formal verification. We think verification is a really good best first market for math

</details>

**Carina Hong**: 因此，我认为这笔融资将让我们能够探索一些应用领域，就像我的同事CTO **Shubo**在**A轮融资**发布视频中所说的那样，它让我们能够拓宽梦想。

<details>
<summary>Original English</summary>

**Carina Hong**: and so I think this fundra is going to like let us explore some of the applied domains uh as my colleague CTO **Shubo** said in the the little launch video um of the series A we had is it it lets us broaden our dreams. So yeah

</details>

**主持人**: 但**2亿美元**，以及**16亿美元**的估值。这有市场吗？我的意思是，你们显然不只是为了证明事情的乐趣而做这些，尽管我确信其中有很多乐趣。

<details>
<summary>Original English</summary>

**Host**: but still like $200 million and I guess a 1.6 billion valuation. How is there a market for that? I mean I was like obviously you're not doing this just for the fun of proving things although I'm sure there's a lot of that but

</details>

### AI与代码生成：从垂直领域到通用推理
**Carina Hong**: 让我们回到**2024年**，当时像**01**这样的模型刚刚出现。

<details>
<summary>Original English</summary>

**Carina Hong**: so let's let's bring us back to 2024 so when you know 01 recently models like just came out

</details>

**Carina Hong**: 当时**Anthropic**秘密地在做什么？是**代码生成**。

<details>
<summary>Original English</summary>

**Carina Hong**: what is what was **anthropic** kind of like secretly working on back then it was coding

</details>

**Carina Hong**: 每个人都知道他们在做**代码生成**，像**OpenAI**、**Meta**、**Ax**，每个人都完全知道**Anthropic**在做**代码生成**，但他们都忽略了。他们认为哦，他们是在**B2B**领域，他们只想要一个垂直领域。人们把**代码生成**看作一个垂直领域。但现在看看我们今天，**代码生成**从**代码生成**到**推理**，再到未来的**垄断性推理**，拥有强大的**迁移学习**能力。我认为这非常非常令人震惊。那些当时从事**代码生成**的人，我认为他们相信我们现在对数学和**Lean**的信念，即如果你有更结构化和形式化的数据，它将比我们正在解决的特定垂直领域更具通用性。所以，如果你今天以非形式化的方式进行数学研究，比如基于人类偏好的标准训练数学模型，那么我会说，我们可能只是一家数学初创公司。但是，当我们追求数学的同时，我们也在做一些对其他领域具有**迁移学习**意义的事情。因此，我认为这是一种更广阔的图景，即虽然公司的**DNA**仍然是数学，我们都是数学狂人，这是一个非常强烈的文化声明。每个人都有一个伟大的使命，让AI成为超人数学家，就像我们在**Putnam竞赛**中看到的，在一批研究猜想中。事实上，我们还有一批即将到来。我们也认为这将是**验证式推理**的基础。我们已经谈论了一些**验证式AI**。我接下来想谈谈**验证式AI**，因为我认为你还有其他问题。

<details>
<summary>Original English</summary>

**Carina Hong**: and everyone knows they're working on coding like **open AI Meta Ax** everyone has full knowledge that **anthropic** was working on coding and they just like overlooked it they thought oh there are at **B2B** place they just want one vertical people think of coding as one vertical and now look at where we are today coding kind of like strong **transfer learning** from coding to reasoning to basically you know a monopoly in the in the future of reasoning and I think that's that's really really shocking the people who are working on coding I think back then believe in something that we believe you know similarly with math and le now which is that if you have more structured and formal data it's going to be a lot more horizontal than the specific vertical we are tackling. So you know if today we are doing you know math informal way like the standard train of thought data train a math model based on human preference then I would say well perhaps we are just a math startup right but you know while we are pursuing math we are also doing things that do have **transfer learning** to other to other domains um so I think that's kind of like the broader broader picture is that while the **DNA** of the company remains math and all of us are math nerds and this is a very strong culture statement. Everyone has a great mission of having **AI** be a superhuman mathematician like we are seeing on **punan** on a batch of research conjectures. In fact, we have another batch coming. Um we're also thinking that this is going to be fundamental to **verified reasoning** and we kind of talk a little bit about **verified AI**. I want to talk a little bit about **verified AI** next because I think you have another

</details>

**主持人**: 是的。是的。我有一些问题想问，所以我想听听关于**验证式AI**的。我确实想深入了解一下。那么，我们知道**Anthropic**和**OpenAI**等公司没有进行形式化验证并将其用于他们的产品发布吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. I have several things I want like uh so I want to hear about the **verified AI**. I do want to dig in a little bit. So, do we know that you know **Anthropic** and **OpenAI** and everyone they're not doing formal verification and using that for their rollouts and whatever?

</details>

**Carina Hong**: 我有很多传闻，可能不应该记录下来。我想，研究人员会交流，他们会玩纸牌游戏。

<details>
<summary>Original English</summary>

**Carina Hong**: I think I have a lot of like rumor mill that I probably shouldn't like put it on the record like I think you know like researchers talk they play card games. Yeah.

</details>

**Carina Hong**: 但他们做或不做有非常有趣的原因。我认为这就是我得到的启示，如果你在一家前沿实验室，由于各种超出你控制范围的原因，方向确实会发生很大变化。

<details>
<summary>Original English</summary>

**Carina Hong**: But there there really interesting reasons if they are or not doing it. I think that's like kind of the takeaway I have which is that if you're like at a frontier lab and the direction [clears throat] actually does change a lot for a lot of reasons beyond your control.

</details>

**Carina Hong**: 所以我想回到**AlphaProof**的时刻。**AlphaProof**是如此令人惊叹，**2024年**的**42分**中**28分**的表现对我来说是**IMO**时刻。**2025年**没有获得金牌，因为在**2024年**和**2025年**，**AI**模型可以解决所有非组合学问题。唯一的区别是，如果你解决了所有非组合学问题，你在**2024年**获得**28分**，在**2025年**获得**35分**，因为**2025年**只有一个组合学问题。在**AlphaProof**之后，我们没有看到**Google DeepMind**在形式化数学方面取得很多成果或进展，这实际上是因为一些不一定是技术性的原因。但是，如果你在一家初创公司，并且你非常专注于形式化数学和**验证式AI**，那么你就可以长期从事非常酷的问题，并且在实现进展和突破方面有很高的可能性。

<details>
<summary>Original English</summary>

**Carina Hong**: So I want to kind of like bring us back to the **alpha proof** moment right like **alpha proof** was such an amazing that really the **2024** um **28 out of 42** performance was the **IMO** moment for me. It was not gold in **2025** because across **2024** and **2025 AI** models could solve all the problem that are not combinatorics. The only difference is that you know if you get all the problems that are not combinotaurics you get **28 in 2024** and **35 in 2025** because there's only one combinatorics question in **2025**. um after **alpha proof** kind of like we didn't see a lot of the formal math uh you know results or kind of progress from **Google deep mind** and that's actually because of reasons that are not necessarily technical but if you're at a startup and you have very singular focus that is formal math and **verified AI** then um you know you get to work on really cool problem for a long time and you have like a lot a lot higher likelihood to get to where you want to be in terms of like progress and breakthrough unlock.

</details>

**主持人**: 是的，请为我们定义一下。

<details>
<summary>Original English</summary>

**Host**: So yeah, just define that for us.

</details>

### 形式化验证的历史与应用
**Carina Hong**: 是的，很多人认为形式化验证是一个古老的话题。它存在的时间很长，远在深度学习之前。它在基于规则的计算机科学时代就已经存在。自**1980年代**以来，形式化验证得到了大力推动。有一些非常有趣的历史轶事，例如，**巴黎工会**要求**地铁系统**的自动切换必须经过形式化验证以确保安全。这是针对技术而言非常有趣的工会。而且，在**挑战者号**事件前后，**欧洲航天局**使用形式化验证来验证**阿丽亚娜号**飞船。**波音**和**空中客车**也使用形式化验证。近年来，**AWS**也大力推动自动化推理，因为他们有很多企业客户确实需要**100%**验证，不能错过任何边缘情况，而一般的测试无法满足需求。所以很多人认为验证很烦人，因为它像是税务和合规，确保我们一切正常。但我们谈论验证时，我认为我们的竞争对手在推出时，他们谈论的是预推理的形式化验证，他们在**幻觉**时代谈论它。也许对他们来说，形式化验证是为了解决**幻觉**的缺陷。对我们来说，不，对我们来说，验证式AI是为了卓越。它关乎**扩展**和**复合超智能**。这是一个相当深刻的观点，有时需要一些解释。如果你想想卓越之处，例如**拉马努金**，他是一位杰出的数学家，在学会证明之前，他就能凭直觉发现许多有趣的公式。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, like a lot of people think about **formal verification** as an ancient you know subject. Um it it existed like as long as you know way before like like deep learning and it existed in the time of rule-based computer science. uh there's this really strong push of like **formal verification** around like since ever since **1980s** uh really interesting historic anecdotes such as uh I think the **Paris trade union** demanded that the automatic switching of the subway system needs to be formally verified for safety purpose. So quite interesting trade union for for technology um and like I think around the time of **challenger** both before and after **European space agency** was using **formal verification** for the **Arian spacecraft**. Uh it's also interesting **Boeing Airbus** for verification and then more recent years right like I think like there's a lot of push about automated reasoning at **AWS** because they have a lot of enterprise customers that really requires things to be to be **100%** you know verified and there's no edge cases mi uh like missed and like just general like testing doesn't satisfy the need. So a lot of people think about verification as something that's like annoying because it's like tax and compliance like it's making sure that we are good to go right and like that's really not the and and so we we talked about like verification I think our competitor when they launched they talk about um **formal verification** pre-reasoning they talked about it uh in the time of **hallucination** and and maybe for them like **formal verification** is about the lousiness the the **hallucination** for us. No, like for us **verified AI** is about the brilliance. It's about **scaling** and **compounding super intelligence**. So this is quite a deep point and sometimes it takes a little bit of explanation. So if you think about like you know the the place of brilliance for example **ramen** like he's a brilliant mathematician he was able to find a lot of like interesting formulas just by intuition before he know how to do p... [truncated]

</details>

**主持人**: 社区中的规则。

<details>
<summary>Original English</summary>

**Host**: the law well [laughter] rules in the community.

</details>

**Carina Hong**: 所以，这很有趣，因为这是一种人类数学家强制执行的，对吧？所以，这是一个**同行评审**过程。一篇论文的**同行评审**目前需要两年时间。

<details>
<summary>Original English</summary>

**Carina Hong**: So, so it's interesting right because that is kind of human mathematician enforced right and so uh it's a peerreview process peer review of a paper currently takes two years

</details>

**主持人**: 好的，但是像**Lean**这样的证明助手和形式化证明跟踪器仍然找到了自己的位置，对吧？为什么？如果我是一个数学家，我的工作可以由其他人类进行**同行评审**，那我们为什么还需要**Lean**呢？为什么我们甚至要谈论基于**Lean**的辅助证明呢？那是因为**Lean**可以处理低层次的问题。例如，我们甚至没有谈论**AI**，我们谈论的是**Lean**中的**grind**策略，它目前可以在非常低层次上处理大量的数学证明，这相当令人震惊，因为我看到过一些在同一领域工作的其他公司的演示，我看到演示时，它实际上可以完全由**grind**处理，**grind**是**Lean**中的一种策略。你能向非专业人士解释一下**Lean**是什么吗？

<details>
<summary>Original English</summary>

**Host**: okay so but **proof assistant** and you know **formal proof trackers** like **lean** still found its place right and why like if you if I'm a mathematician and you know any like my work can be **peer reviewed** by other humans like why do we even why do mathematicians even play with **lean** right and why do we even like talk about kind of like you know **lean based** um assisted like ser improving it's it's because like it handles a low level for example we're not even talking about **AI** we're talking about for example the **grind tactic** in **lane** it can currently handle a lot of mass proofs like at a very low level and and this is pretty shocking because I have seen you know actually another uh company working in the same space like you know some of their demo and I look at the demo like it can actually completely be handled by **grind** uh which is a tactic in **lean** Can you explain what **lean** is to non experts?

</details>

**Carina Hong**: 好的，是的。我想我们的顺序有点不对。是的，所以**Lean**是一个计算机程序，有点像用于数学证明。它是一种形式化语言，就像它的表亲**Isabelle CoQ**或**Rock**，以及其他一些更远的表亲，比如**Daphne Agda**，这些形式化语言占据了整个领域。

<details>
<summary>Original English</summary>

**Carina Hong**: Okay. Yeah. I think our order is like a little little wrong. Yeah. So **LIN** is a computer program uh a bit like for mass proofs. It is a **formal language** um just like its cousin **Isabel CoQ** or **rock** um and um some other further cousins like **Daphne Agda** like these **formal languages** whole sector. Yeah.

</details>

**主持人**: 它有什么作用？它基本上是，如果你用**Lean**程序编写了一个证明，并且假设没有发生任何奇怪的事情，比如你使用了**sorry**（这是一种策略，让你把事情视为理所当然），假设一切都是安全的，因此人们有像**Comparator Safe Verify**这样的工具，而**Axiom**最近推出了**Verify Proof**，比**Comparator**快**100倍**，那么一旦你执行了这个程序，一旦它编译并通过，告诉你它是正确的，那么这个证明实际上就是正确的。

<details>
<summary>Original English</summary>

**Host**: And what what does it do? It it basically if you have a proof written in the program in **ling** and then uh assuming there's not no any like weird things happening like you know like you know use of sorry which is a tactic that let you take things for granted assuming everything is is safe um hence **P** people have tools like **comparator safe verify** and **Axium** recently rolled out **verify proof** that's like **100 times faster than comparator** um then you know once you kind of execute that program it like once it compiles and it tells you that is correct then it is the proof is actually correct.

</details>

**Carina Hong**: 就像一个**类型检查器**一样。

<details>
<summary>Original English</summary>

**Carina Hong**: So just like a **type checker**

</details>

**Carina Hong**: 是的，它基于**Curry-Howard对应**这个结果，它将证明转化为程序。所以，我想谈谈**Lean**的魔力。为什么我认为它是一种非常好的编程语言，是因为一方面，如果你根本不关心形式化部分，如果你不关心逻辑部分，你只想用**Lean**编写代码，你可以做到。我们有一些候选人，实际上，现在这位正在**Lean**社区工作的人，他在我们的面试过程中用**Lean**编写了**autograd**。

<details>
<summary>Original English</summary>

**Carina Hong**: yeah that is based on this result called u **car Howard correspondence** which turns proofs into programs. So, so I want to talk about the magic of **ling**. Why I think it's a really good **programming language** is because on one hand if you don't care about the formal part at all, if you don't care about the logic part, you just want to use **ling** to write code, you can like we have had candidates actually currently um you know the person is working at the **lin fro** um he wrote **autograd** in **lean** in our interview process.

</details>

**主持人**: 所以它是一种**图灵完备**的语言。

<details>
<summary>Original English</summary>

**Host**: So it's a it's a a **turning complete language**.

</details>

**Carina Hong**: 没错。所以，你可以用**Lean**做很多事情，它是一种**函数式编程语言**，对吧？然后你可以用它来做**代码生成**，也可以用它来做数学，二合一。

<details>
<summary>Original English</summary>

**Carina Hong**: That's right. So um you can write you can do a lot of things with **lean** you can it's a it's a **functional programming language** right and then you can you can also use it to so you use it to do coding you can use it to do math two in one

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: okay

</details>

**Carina Hong**: 回到我之前想说的，如果数学家已经坚持认为大多数证明都是正确的（也许不是所有数学家，而是学术界的人），那么我们为什么还需要**Lean**这个模型跟踪器呢？那是因为**Lean**有策略可以帮助他们处理低层次的计算或证明或推导，而不是计算。这样他们就能够在高层次的直觉空间中进行导航。所以我的观点是，对我们来说，形式化验证或验证式AI不仅仅是处理或消除缺陷、幻觉、错误。它关乎扩展卓越。它关乎**超智能**。事实上，**Terrence Tao**也有一个很棒的视频，讲述了如何使用**Lean**作为一种协作方式，因为你可以，这正是我要谈的另一点，很多人都在思考我们的市场是什么？它必须是某个非常小众的工业社会领域，具有任务关键性、安全关键性，不，这不是**总潜在市场（TAM）**，**总潜在市场**是所有代码。

<details>
<summary>Original English</summary>

**Carina Hong**: and kind of going back to what I was kind of getting at if mathematicians are already enforcing that most proofs you know say say maybe not all mathematicians but by but the ivory tower and people in academia all proofs are correct why do we even need **lean** the model tracker It's because **lean** has tactics that help them handle the low-level calculation or proof or deduction not calculation. Um then for them to be able to navigate in a high level intuition space. So this is my point that it is not about like **formal verification** or **verified AI** to us it's not just about handling or like kicking out the lousiness, the **hallucinations**, the mistakes. It's about **scaling brilliance**. It's about **super intelligence**. I actually **Terrence Ta** has a great video also about using **lean** to as a way you can collaborate because you can you exactly that's another point I want to I want to talk about right a lot of people think about you know what is our what is our market it has to be some like really niche industrial societies area that is mission critical safety critical no that's not the **TAM** the **TAM** is all code

</details>

**Carina Hong**: **总潜在市场**是对所有AI生成的代码的优先购买权，优先购买权意味着你可以选择是否验证它。所以这是我想强调的重要部分，人们谈论形式化验证时，几乎觉得它很痛苦，因为它有所有这些严格的要求。

<details>
<summary>Original English</summary>

**Carina Hong**: the **TAM** is a is a right of first refusal on all **AI** generated a code like for right the first refusal meaning you know you get to choose whether you want to verify it. So this is the important part I want to kind of come across which is that people talk about **formal verification** as almost like painful because it has all these like stringent requirements

</details>

**主持人**: 到目前为止都是这样。

<details>
<summary>Original English</summary>

**Host**: up until now it has been [laughter]

</details>

### 验证式生成：性能提升的关键
**Carina Hong**: 是的，对我们来说，**验证式生成**实际上意味着**性能提升**，意味着更高的**样本效率**，意味着像我们这样一家初创公司，尽管我们筹集了一些资金，但计算预算和数据预算都比前沿实验室少，却能够匹敌甚至超越超人任务的表现。事实上，在**2025年12月**我们参加的**Putnam竞赛**中，**Mass Arena**这个评估许多大型语言模型的组织发现，表现最好的大型语言模型**DeepSeek**在**120分**的考试中获得了**103分**。我们现在知道，表现最好的人类学生来自**麻省理工学院**或**芝加哥大学**，我们不知道是哪一所，因为他们不公布前五名获奖者的分数，他得了**110分**，而我们得了**120分**。所以这实际上是第一次，我记得我们刚开始时，人们会问，一个形式化数学系统，数据量少了几个数量级，是否有可能与一个非形式化的大型语言模型匹敌或超越？而**Putnam竞赛**是它第一次超越。所以我们不仅仅考虑它带来的痛苦和挑战，我们考虑的是**验证式生成**带来的**性能提升**、改进，以及你可以，就像你期望**RL4 Lean**会因为看到我们自己代码的证据而有所改进一样。所以这是我想说的关于如何思考验证式AI的第二点。

<details>
<summary>Original English</summary>

**Carina Hong**: yes and and to us it's actually **verified generation** means **performance gain** it means higher **sample efficiency** it means a startup like us with like you know still we we raise some money but lesser compute budget lesser data budget than **Frontier Lab** will be able to match even exceed you know performance on superhuman tasks. In fact, for the **punam exam** that we just competed **December 2025** which we did in real time **mass arena** which is this organization that evaluates a lot of **LMS** found the best **LM deepseek** got **103 points out of a 120 point exam**. The best human obviously we now know is a student from either **MIT** or **Chicago**. We don't know which one um because they don't announce the top five winner score got **110** and we got **120**. So it's the first time actually I remember when we were starting this people were like is it even possible that a formal mass you know system with so much orders of magnitude last data can can match or beat a a for an informal **LLM** and **pund** is the first time it beat right and and so we're not thinking about it just about the painfulness the challenges it pose we are thinking about the **verified generation performance gain** the improvement the the fact that you can you know just like you would expect **RL4 lean** seem to to have improvement because of seeing evidence of our own coding. So this is the second point I want to make about like how to think about verification **verified AI**.

</details>

**主持人**: 那么，也许我们可以谈谈为什么。您能描述一下您所做的工作与前沿实验室（至少在他们构建标准的**RL增强型LLM**时）有什么不同吗？

<details>
<summary>Original English</summary>

**Host**: So maybe we can talk a little bit about why. Can you describe what what is different about what you do versus what the frontier labs you know at least when they're building their standard **RL enhanced** uh **LLMs**. What what's different about what you do?

</details>

**Carina Hong**: 是的。所以我们非常依赖一种叫做**Lean**数据的数据，我们刚才谈到了**Lean**是所有数据，这些都是**Lean**证明，你知道它是正确的或不正确的，这非常重要。所以我们有一个模型系统，这些模型是经过训练的，并且使用**RL**或**SFT**。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So we heavily rely on a kind of data called **lean data** and we kind of talked about **lean** is all the all the data um that we have that's **lean proofs** you know it's correct so you you know it's correct or not and that's quite quite important so you know we have a system of models these models are post-rained and um using **RL** or **SFT**

</details>

**主持人**: 所以**LLM**就像某种基础模型，你可以直接使用，然后对其进行后训练或持续训练。

<details>
<summary>Original English</summary>

**Host**: so **LLM** found like some sort of **foundation model** that you get off the shelf and you postrain it or or continuous.

</details>

**Carina Hong**: 是的，而且显然倾向于开源基础模型。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. And there's obviously an inclination for open source, you know, base models.

</details>

**主持人**: 所以，它会说英语。

<details>
<summary>Original English</summary>

**Host**: So, it does speak English,

</details>

**主持人**: 可能会**代码生成**，但你也会对其进行微调或持续训练。

<details>
<summary>Original English</summary>

**Host**: probably knows how to code, but it also you fine-tune it or or continue

</details>

**Carina Hong**: 基础模型可能也与其他人所说的类似，对吧？如果他们没有预训练他们的模型，对吧？

<details>
<summary>Original English</summary>

**Carina Hong**: and the base model might be similar to what everyone else saying as well, right? Um if [clears throat] they're not kind of pre-training their model, right?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 然后我们基本上进行这种**RL**形式化数学，我认为有一些标准的流程或行业技巧。我们尝试尽可能地在其之上进行创新。我认为我们发现，扩展推理几乎没有障碍，递归分解证明目标为许多子目标，然后也学习回溯。是否存在这样的风险：你从你所知道的特定领域数据集等开始，然后开始递归地在一个空间中展开，但现在你所有的训练数据都局限于某个领域，它仍然只是，比如以对数方式，在一个从你初始训练数据开始的大空间中增长。所以你可能会被困住，你可能在这方面非常擅长，但你只是创造了一个巨大的锯齿状前沿，而其他一些领域则远离它们。

<details>
<summary>Original English</summary>

**Carina Hong**: And then we basically do this, you know, **RL** for formal math kind of there's I think a standard pipeline or like, you know, tricks of the trade that people use. We try to innovate really uh on top of it as much as we can. I think that we found um scaling inference to have almost no wall um recursively decomposing uh you know a proof goal into many sub goals and then learning to backtrack as well. Is there a risk that like you start out with this, you know, what you know and a certain domain of data sets and so on and then you start rolling out, you know, recursively in a space, but now all of your training data is localized in some domain that you it still is only so like maybe logarithmically um in some large space growing from your initial training data. So you could get trapped essentially in that you know you could be really good at this but you just created a big jagged frontier where some other domains are just far from them

</details>

**Carina Hong**: 我们谈论的是**分布偏移**。所以，是的，这是一个悬而未决的问题，一个在数论方面表现出色的系统能否在，给我，另一个数学领域中表现出色。是的，没错。实际上，我认为我们看待这个问题的方式是，这取决于。这取决于拓扑学是否拥有许多现有的定义，几乎就像数学基础设施一样。

<details>
<summary>Original English</summary>

**Carina Hong**: **distribution shift** we're talking about. So yes so so you know it is an open question whether a uh a system that can do really well in number theory can do well in uh give me you know another another field of math. Yeah exactly. Well, actually I think this the way we think about it is it depends. It depends on whether topology has a lot of the um existing definitions as almost like you know the the math infrastructure

</details>

**Carina Hong**: 因为过去人们发现，当人们构建数学库时，书本上的工作，他们可以做到。

<details>
<summary>Original English</summary>

**Carina Hong**: um existing because what people have found in the past is when people were building out math ligebra um you know book work um like they they can just

</details>

**主持人**: 所以**mathlib**就是**Lean**的本科生图书馆之类的东西。所以它就像你在大学数学中学到的所有证明，它们都在**Lean**中。

<details>
<summary>Original English</summary>

**Host**: so **math li** being the **lean** like undergraduate library kind of stuff. So it's like all the proofs that you learn in undergraduate math and they're all sort of in

</details>

**Carina Hong**: 是的。所以，举个例子，我的一些朋友，他们现在在**Axiom**。这是一个疯狂的完整循环。**Kenny**，我们是五六年的朋友，他第一个告诉我**Lean**。他当时和**Kevin Buzzard**一起构建**mathlib**。在**mathlib**中，代数比分析更容易编纂。嗯，所以这很有趣，因为对于分析学，围绕收敛、极限等许多定义变得很棘手。所以，我认为今天的**mathlib**中没有很多拓扑学的内容，比如微分拓扑学、微分几何学之类的东西。所以，我们的系统很可能在这些领域表现不佳，因为它甚至没有可以作为基础的定义。在定义存在的领域，我们实际上在分布多样性方面做得相当好。我们在数论、交换代数、代数几何、一些离散数学和概率论方面都取得了良好的性能，解决了开放的研究问题。

<details>
<summary>Original English</summary>

**Carina Hong**: vain. Yeah. So for example, some of my friends um who currently are **Axiom**. It's you know crazy like full circle back moment. Um **Kenny** um we're like friends for like you know five six years and he was the first one to tell me about **lane**. He was working with **Kevin Buzzard** to build out **math lib**. It's a lot easier to codify algebra in **math lib** than than for for analysis. M uh so so that's that's interesting because for analysis a lot of the definitions around convergence limits is sector becomes tricky and so I don't think there's a lot of like topology in **math lib** today um in terms of like differential topology differential geometry kind of stuff so you know our system likely will not do very well on those on those domains because it doesn't even have definitions to build off on top of for the places where the um definitions are are in we actually are doing quite okay in terms of distribution ution diver diversity we have good performance you know so having solved open research questions and um number theory commutative algebra algebraic geometry some discrete math that comes and probability

</details>

**主持人**: 所以你之前说过，在**Putnam竞赛**中，**2024年**的版本，所有**AlphaProof**没有答对的问题。

<details>
<summary>Original English</summary>

**Host**: so earlier you said that like with the **pudnum exam** you the the **2024** version when all of the questions were that were not that **alpha proof** did not get right

</details>

**Carina Hong**: **IMO国际奥林匹克数学竞赛**。

<details>
<summary>Original English</summary>

**Carina Hong**: the **IMO international**

</details>

**主持人**: 是的，对于**IMO**，我答错的所有题目都在**组合学**中，是不是在那个特定领域有弱点？

<details>
<summary>Original English</summary>

**Host**: yes for the **IMO** all of the ones I got wrong were in **cominatorics** is there is Is there like a weakness there in that specific domain?

</details>

**Carina Hong**: 我会说，对于数学奥林匹克竞赛，人们认为**组合学**有点棘手。

<details>
<summary>Original English</summary>

**Carina Hong**: I would say so for for **Olympia** in math people are seeing commonars being a little bit more um tricky.

</details>

**Carina Hong**: 似乎步骤相当有创意。所以对于我来说，我是一个人，而且我有一些非常擅长**组合学**的朋友，我从不认为自己是**组合学**的顶尖高手。我更擅长数论，但我认识一些人，他们是**IMO金牌**、**Putnam**满分获得者，一直都是这样。当他们用**组合学**技巧时，我就会想：

<details>
<summary>Original English</summary>

**Carina Hong**: Uh seems like the steps are quite creative. So I for I'm a human and you know when I have friends who are really good at commentaryics which I never consider myself really the the top of comarics. I'm kind of better at number theory but I know some people who are just they're **imo gold** perfect score put them fellow perfect score and like all the way and then when they do like tricks and comarics I'm like

</details>

**Carina Hong**: 我不知道你是怎么想出来的，但你给我那个构造之后，它实际上变得更容易追踪。我认为一个基于**Lean**的系统会在那些非常有创意的地方挣扎，这就是为什么我们**Axiom**也投资于**数学发现**。它没有被使用，我们将在未来几周内发布一些重大新闻，基本上是开源整个**数学发现**代码库。

<details>
<summary>Original English</summary>

**Carina Hong**: I don't know how you thought of that and but you know after you give me that construction actually becomes a lot more trackable I think a **leanbased system** will struggle in those very creative um places which is why we at **Axiom** actually also invest on something called **mathematical discovery**. It's not used and we have some major news in the coming weeks basically open sourcing entire code bases of **mathematical discovery** coming up.

</details>

**主持人**: 你想告诉我们一些吗？

<details>
<summary>Original English</summary>

**Host**: You want to tell us a little bit?

</details>

### 数学发现工具与开源
**Carina Hong**: 是的，当然。我们目前正在**开源**两个代码库。目标是，如果你是一名数学家或理论物理学家，并且你有一个想要解决的问题。例如，你想要找到一个非常复杂的图构造，那么我们会建议你遵循为数学家编写的非常详细的手册来运行我们编写的代码。它是一个供数学家进行**数学发现**的工具。**数学发现**的理念是，证明对于数学来说是不够的。事实上，在你开始证明之前，你不知道从哪里开始。所以你会尝试构造一些有趣的例子。这些通常可以是序列，如果你想了解一个序列的性质，你会写出前几项。这也可以是图。所以如果你想弄清楚你正在寻找的图是否应该具有某种性质，那么你会从做一些更简单的图版本开始。现在，构造不能由**Lean**完成。所以我们相信**AI**可以用于**数学发现**，我们拥有该领域的一位OG，**Chart**，**Axiom**的技术人员，他之前做过**PatternBoost**，并端到端地通过找到反例解决了**30年**的猜想。他还找到了**130年**历史问题的解决方案，即在三体问题中出现的**全球李雅普诺夫函数**（global leono function）这种数学对象。所以我们认为，**数学发现工具**应该向数学社区开放。因此，我们正在**开源**整个代码库。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah, sure. U so uh we are currently uh having two code bases um being **open sourced**. So the goal is for if you're a mathematician or you're a theoretical physicist and you have a problem that you would like to solve. For example, you want to uh find a construction that is a very complicated graph construction, then we would suggest you follow the very detailed manual supposed intended for mathematicians to run the code that we write. Uh it's a it's a tool for for mathematicians to make **mathematical discoveries**. **Mathematical discoveries** is this idea that you know proof is not enough for math. uh in fact before you kind of start proving something you don't know where you want to start. So you will try to construct some interesting examples. These can be usually say sequences right if you want to understand the property of a sequence you will write out a few of the first terms. This can also be graphs. So if you want to you know figure out what the graph that you're looking for um should I have say a certain property uh then you will start by doing some simpler version of the graph. Now constructions cannot be done by **lean**. So we believe in having **AI** for mass discovery and we have you know one of the **OGs** in that field **chart** um member of technical staff at at **Axium** and he previously have done **pattern boost** and end to end you know settle disproof a **30-year-old conjecture** by finding a counter example um found the solution to **130 year old problem** the **global leono function** that is a kind of mathematical object showing up in the **three body problem**. So we we are we are thinking that you know it's **mathematical discovery tools** should be open to the mass community. So we are **open sourcing** entire code bases for that.

</details>

**主持人**: 所以，发现意味着它会提出新的猜想，还是？

<details>
<summary>Original English</summary>

**Host**: So discovery meaning it gives it makes new conjectures or it

</details>

**Carina Hong**: 实际上，那是一个**预猜想**的步骤。哦，我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: that's a yeah it's a **preconuring step** actually. Oh I see.

</details>

**Carina Hong**: 是的。所以你开始形成直觉。如果你是一名数学家，你的目标是解决一个非常困难的猜想，**X-Prover**不能直接帮你解决。你可能想尝试提出一些引理和猜想，然后将其提供给**Axiom Prover**。如果你是一个人类数学家，你会从想要提出这个猜想开始。你不知道该去哪里。你想找到构造。现在，我们将要开源的代码有望显著地帮助你。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So you you start to form intuitions right. If you're a mathematician and your goal is to solve a really hard hard conjecture **x improver** can't just solve it for you. Um you might want to try to formulate some sort of **lemas conjectures** that you want to say then give to **axium improver**. [snorts] Um if you're a human mathematician you will start by wanting to formulate that conjecture. You don't know where to go. You want to find constructions. Now uh the code is that we're going to open source going to help you uh hopefully significantly.

</details>

### 图灵完备性与验证边界
**Carina Hong**: 所以，可能有很多计算机科学家在听，当谈到**形式化验证**等等时，**Rice定理**、**可判定性**和**不完备定理**，以及一些关于**计算复杂性**和**大型语言模型**的论点会立即浮现。所以，我很想听听，**Rice定理**说你不能证明所有程序的非平凡属性，对吧？那么，你如何在这个领域中航行？显然，**形式化验证**能够做一些事情。

<details>
<summary>Original English</summary>

**Carina Hong**: So, one thing that maybe there's a lot of computer scientists listening and one of the things that will immediately kind of come up in especially when you're talking about **formal verification** and so forth is **RI's theorem** and **decidability** and **incompleteness theorem** and and maybe um some arguments about **computational complexity** and **LLMs**. So I I'm curious to hear **Rice of Serum** says you cannot prove non-trivial things about programs for all programs, right? So h how are you navigating this space? Obviously **formal verification**, you know, does is able to do some things.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 是的，我认为很清楚，就像有理论结果告诉你你不能形式化验证所有程序，对吧？但是我认为形式化验证大多数有用的程序是好的，对吧？所以你知道，我记得**麻省理工学院**有一个小纪录片，或者不是纪录片，而是一个广告，是为被录取的学生准备的，其中有**Tim**，**麻省理工学院**的吉祥物**海狸**，他说了一句名言：理论给你带来了什么？这有点像，它并没有阻止我们尽可能地推进它。所以我们对未来的目标是，假设你正在进行**代码生成**，你想要为一个非常复杂的任务编写代码。所以现在是前端网站，但未来我们可能想要编写更复杂的东西，甚至是整个分布式系统，那么我们希望能够将其分解。可能有一个高层次的草图计划，这我们可以做，其他人也可以做，但是你说，**Claude**给你，把它分解成10件事，然后在某个时候，它会决定调用**Axiom**，**Axiom**会给你一个你知道是经过形式化验证的计算机程序，或者它会说这仍然对我们来说太难了。

<details>
<summary>Original English</summary>

**Carina Hong**: So yeah, I think like it's it's very clear that you just like there's theoretical result telling you you cannot formally verify all programs, right? But you you I think it it's good to formally verify majority of the useful programs, right? So you know like I remember uh there's this **MIT** uh like little like documentary or not a documentary like an advertisement for you know uh people who are admitted students and then there's this famous line by **Tim** the the **beaver** the mascot of **MIT** saying that what aory give you which is which is kind of like it doesn't stop us from trying to push it as much as possible. So the goal that we have for the future is suppose you are you know doing doing the the coding you want to v code a really complex task. So you know currently it's front end websites but in the future we might want to vibe code much more complicated things whole distributed systems even then we want to be able to say decompose it there's maybe a highle kind of like sketch plan this we can make other people can make but say you know you have claw give you like you know kind of break it down into 10 things and at one point it will decide to call **axiom** and **axiom** will give you a computer program that you know is ** formally verified** or it will say this is still too hard for us.

</details>

**主持人**: 所以你编写程序，把它交给**Axiom**，它可能会对其进行修改。

<details>
<summary>Original English</summary>

**Host**: So you you write the program, you give it to **Axium**, it makes changes to it maybe.

</details>

**Carina Hong**: 所以我们谈论的是两个阶段。

<details>
<summary>Original English</summary>

**Carina Hong**: So so we're talking about kind of two um sort of phases.

</details>

**Carina Hong**: 我们有可能是验证伙伴。所以你已经有一个计算机程序，你希望我们验证它。事实上，**GPT**发现了一个未解决的**Erdos问题**的证明，我们的竞争对手**Harmonic**的**Aristotle**验证了它。但我们想要做**验证式生成**，对吧？我们可能会说，嘿，这个小组件，我们生成并提供给你的一切，都是经过形式化验证的。

<details>
<summary>Original English</summary>

**Carina Hong**: Um it is possible that we are the **verification partner**. So you already have a computer program and you want us to verify it. In fact, like you know, **GPT** found a proof to an unsolved **Erdos problem** and our competitor **Harmonic**, you know, **Aristotle** um you know, verified it. But we we can do we want to do **verify generation**, right? We might want to say, hey, you know, this little component everything that we generate and provide for you um is is **formally verified**.

</details>

**主持人**: 我明白了。所以，这个想法是，你同时生成两者，这样我就可以想象这符合**promise**或**sorry**的理念，然后是一个**sorry**。

<details>
<summary>Original English</summary>

**Host**: I see. So, so the idea would be you you generate you co generate bo both and so that and I can imagine this fitting into um you know the idea of a promise or a sorry sorry and then a sorry [laughter]

</details>

**Carina Hong**: **Lean**中的**sorry**。

<details>
<summary>Original English</summary>

**Carina Hong**: **lean sorry**

</details>

**主持人**: 一个**Lean sorry**意味着它是一个未经证明的引理，但你暂时将其视为既定事实，直到你有时间证明它。这是思考**sorry**的好方法吗？

<details>
<summary>Original English</summary>

**Host**: a **lean sorry** meaning it's a **lema** that is unproven but you're just taking it as given until you can take have the time to prove it right is that a good way to think about a sorry

</details>

**Carina Hong**: 这是一个思考**sorry**的好方法，但不必在**代码生成**的语境下。

<details>
<summary>Original English</summary>

**Carina Hong**: that is a good way to think about a **sorry** but not necessarily in the coding context

</details>

**Carina Hong**: 我可以想象你可以说，假设这个模块已经验证，那么这个模块是正确的。

<details>
<summary>Original English</summary>

**Carina Hong**: it's So I can imagine you're you can say assuming that this module is verified then this module is correct

</details>

**主持人**: 这样你就可以把问题分解得足够小，可以验证它。这是这样的吗？

<details>
<summary>Original English</summary>

**Host**: and and so that that you can decompose a problem small enough that you can verify is this kind of

</details>

**Carina Hong**: 所以，假设我们想用**代码生成**来控制流程。

<details>
<summary>Original English</summary>

**Carina Hong**: so so let's say we want to you know like web code **control flows**.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 对。那相当困难。你很可能会把它分解成多个步骤。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. That's quite hard. you will likely, you know, break that down into multiple steps

</details>

**Carina Hong**: 然后它会继续将这些步骤分解成更细粒度的步骤。

<details>
<summary>Original English</summary>

**Carina Hong**: and then it will continue to break down these steps into more fine grain steps

</details>

**Carina Hong**: 在某个时候，你想要绝对正确的东西。

<details>
<summary>Original English</summary>

**Carina Hong**: and at one point you want something that is absolutely correct. Y

</details>

**Carina Hong**: 而且这也可能在可实现的范围内。那么我们想生成，我们想生成一段计算机程序，其底层有一个保证，即也生成了证明，这告诉你你所指定的东西，这个程序员可以为你解决。所以，我们设想的是，任何可以定义的东西（虽然有点营销，因为正如你所说，有理论限制，但大部分情况下，几乎可以肯定）都可以执行，任何可以指定的东西都可以被证明。所以我的想法是，如果你有一个程序，乘以一个陈述或问题，它就映射到可验证性条件乘以一个证明。所以，虽然程序验证社区已经为你提供了可验证性条件，我们正试图招募一个非常强大的团队来帮助我们做到这一点，但**Axiom Prover**会给你证明。

<details>
<summary>Original English</summary>

**Carina Hong**: and then this is also something that is likely within reach. Then we want to generate you know both uh we want to generate a piece of computer program and underlying is a guarantee that there is also the uh proof that has been generated which tells you that the thing that you specify this you know programmer can solve for you. So, so, so the vision we have is anything that can be which anything is you know and it's a little bit marketing because because as you said theoretical bound but but mostly um well almost surely hopefully um anything that can be defined can be executed anything that can be specified can be proven. So the way I think about it is if you have a uh program um times a a you know a program times a times a statement or problem it maps to **verifiability conditions** times a proof. So while the **programming ver program verification community** has given you say the **verifiability conditions** and we're trying to kind of recruit a really strong team to help us do that. **action prover** is gonna give you the proof.

</details>

**主持人**: 那么，请帮我把程序映射到证明。因为我可以说，这个两行的**Lean**程序验证了我声称它解决的任何问题。我怎么知道它真的验证了我认为它验证的东西？

<details>
<summary>Original English</summary>

**Host**: So just help me map from the program to the proof because like I could say you know this **twoline lean program** verifies you know sort of like whatever whatever I claim it solves. How do I know that it actually verifies the thing that I think it

</details>

**Carina Hong**: 是的。举例来说，现在有一个叫做**Code Arena**的基准测试，它是一个**代码验证**基准测试，应该是**Lean**友好的。所以每个问题都是一个编码问题，目标是生成代码和证明，是两个不同的计算机程序。是的。然后目标是生成带有证明的代码。所以，你有所谓的解决这个问题的代码，然后有这个程序确实解决了这个问题的证明。

<details>
<summary>Original English</summary>

**Carina Hong**: verifies? Yeah. So so for example there's this currently there's this benchmark called **code marina**. It's a uh **code verification benchmark** um that's supposed to be **limb friendly** and so you know every problem is a coding problem and the goal is to generate there's a code part and there's a proof part two two different computer programs. Yeah. And then the goal is to generate code with proof. So you know the code that supposedly solves this problem and then the proof that this program indeed does solve the problem.

</details>

**主持人**: 我明白了。那么，人们在这个基准测试中表现如何？我想谈谈这个，因为它很有趣。它是由**伯克利**和**Meta**的研究人员在**2025年**推出的，他们发现，他们评估的**GPT**版本在**Pass@1**上表现为**3.6%**，迭代后大约**22%**。那么，形式化数学系统模型表现如何呢？**Copra**是一个系统，因为在系统中你会迭代和定义，所以**Pass@1**并不完全适用，但他们仍然评估了该系统在**Pass@1**上的表现，大约**11-12%**。然后**DeepSea Prover**和**GoTo Prover**模型也表现为**11-12%**。我认为我们的竞争对手去年在仅证明部分发布了**96%**的成绩。而我们最近在不修改**Putnam**系统的情况下，在**189个问题**中解决了**187个**，只错失了两个，达到了**99%**的带有证明的代码。所以，如果你想训练一些东西来做带有证明的代码，并且你想做**强化学习**，那实际上很烦人，因为如果你想让证明是非形式化的数学，那它会很烦人，因为它只是一个混合目标函数。你的代码可能是**Python**，你的证明可能是自然语言的数学证明，你的**RL**性能不会很强。但如果你的证明是**Lean**，并且你选择**Rust**这种强类型语言编写代码，那么它的转换性更强。所以你会获得更好的性能。

<details>
<summary>Original English</summary>

**Host**: I see. Now now how do people do on this benchmark? I kind of want to like talk about this a little bit because it's interesting. It was um rolled out I think by um **Berkeley** and **Meta** researchers in **2025** and they found I think whatever version of **GPT** they evaluated does like **pass one** like **3.6%** iterative something like **22%**. Now you know how does the **formal mass systems models** do um **copra** which is a a system because in a system you iterate and define so **pass one** doesn't quite work but still they evaluated **pass one** of the system about like I think **11 12%**. And then also **deep sea prover** and **go to prover model** **11 12%**. And I think our competitor has released last year on the only proof part **96%** um and we actually recently with no modification to the **pandm system** we saw a **99% out of the 189 problems** we solved **187** we missed only two um code with proof. So if you if you want to train something to do code with proof and you want to do **reinforcement learning** it's actually quite annoying because look it's it's mix if you want proof to be informal math it's it's very annoying because then that's like just mix objective function um your code is something like **Python** your proof is say natural language mass proof um you will not have very strong **RL** kind of performance right but if you have proof as **lane** and you have you know code you can choose **roster** which is a strongly typed language. It's more it's more conversion. So you're going to have much better performance. I can't... [truncated]

</details>

**主持人**: 但它在**Lean**中只有两行，显然不是，那么我怎么知道我编写的程序与我生成的证明相匹配呢？

<details>
<summary>Original English</summary>

**Host**: but it's two lines in **lean** obviously it doesn't so how do I know that the program that I wrote matches the proof that I generated

</details>

**Carina Hong**: 你基本上会查看编码问题，然后查看程序，然后你会尝试查看它是否满足可验证性条件。

<details>
<summary>Original English</summary>

**Carina Hong**: you will basically look at the coding problem and you look at the the program and then you um like try to see if it satisfies the **verifiability conditions**

</details>

**主持人**: 但我怎么知道呢？如果我读它，对吧？

<details>
<summary>Original English</summary>

**Host**: But like how do I know, right? Like if I read it, right?

</details>

**Carina Hong**: 嗯，你知道，我可以直接目测，然后我说，传统上数学家是如何做到这一点的，他们拿来论文阅读，然后说我同意这个证明解决了问题，然后另一个人说，不，等等，它没有解决，因为你看这个，然后人们意见不合，最终达成共识，这个证明解决了这个问题。

<details>
<summary>Original English</summary>

**Carina Hong**: Um you know like I can I can just like eyeball it and I can say and then like traditionally how mathematicians have done this is they they you know they take the paper and they read it and they say I agree that this proof solves the problem and then this other person says no wait it doesn't for you know like look at this and then people disagree and eventually there's consensus that that like this proof solves this problem.

</details>

**主持人**: 但你一步一步地检查它。对。

<details>
<summary>Original English</summary>

**Host**: So like how do how are you but you check it step by step. Right.

</details>

**Carina Hong**: 是的，对，对。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Right. Right.

</details>

**Carina Hong**: 是的，是的。所以你基本上会查看可验证性条件，看看它是否确实满足了。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. So you basically will look at the **verifiability conditions** and see if it does actually satisfy that.

</details>

**Carina Hong**: 那么，假设我们正在看一段计算机程序。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: So so suppose like we're looking at like you know a piece of computer program. Yeah.

</details>

**主持人**: 对。那么它是否确实解决了编码问题。你对此会有一个判断。对。是的。

<details>
<summary>Original English</summary>

**Host**: Right. And then whether it does actually solve the coding problem. You will have a judgment about that. Right. Yeah.

</details>

**Carina Hong**: 所以你不会仅仅依赖测试，尽管那是一种方式。

<details>
<summary>Original English</summary>

**Carina Hong**: So you will not solely rely on testing even though that is a way. That's what

</details>

**主持人**: 所以有人看到证明，然后说，是的，它确实解决了我们认为它应该解决的问题。

<details>
<summary>Original English</summary>

**Host**: so somebody looks at the proof and says, "Yeah, that actually solves the problem that we think it's supposed to some."

</details>

**Carina Hong**: 但现在你基本上是在生成一个满足可验证性条件的**形式化验证**程序。

<details>
<summary>Original English</summary>

**Carina Hong**: But then but then now you're you're basically producing a you know **formal verification program** that satisfy the **verifiability conditions**

</details>

**Carina Hong**: 关于这个程序和这个陈述。所以，函数是将程序和陈述映射到可验证性条件和证明。

<details>
<summary>Original English</summary>

**Carina Hong**: about this program and this statement. So again the function is taking you from the program and the statement to **verifiability conditions** and proof.

</details>

### 规范问题与未来编码
**主持人**: 好的。所以我可以看到这在基准测试中是如何工作的。那么，如果我有一个**飞行控制系统**，它非常。

<details>
<summary>Original English</summary>

**Host**: Okay. So I can see how this works in a benchmark. Then if I have let's say I have a a **flight control system** that is like very

</details>

**Carina Hong**: 那么问题就变得非常恼人了。规范，我认为这个词会，即使我们说成功，就像任何我们都会遇到规范问题一样。

<details>
<summary>Original English</summary>

**Carina Hong**: then the the problem becomes very annoyingly uh you know this the like specification I think the word is going to you know even if we say successful like like anything that you know that we will have a specification problem.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 所以，如果银行说，请给我一个非常安全的**财务审计**？对不起。为我证明**财务审计**，对吧？

<details>
<summary>Original English</summary>

**Carina Hong**: So like here comes a bank saying that like please do I have a really safe **financial audit**? Sorry. Like prove the **financial audit** for me, right?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 那是什么意思？我们无法指定。人类不擅长指定我们想要的一切。

<details>
<summary>Original English</summary>

**Carina Hong**: Like what does that mean? Like we we can't specify. Humans are bad at specifying everything that we want. [snorts]

</details>

**Carina Hong**: 总是会有一些没有被指定的东西，如果它没有被指定，它就没有被证明。

<details>
<summary>Original English</summary>

**Carina Hong**: There's always like some sort of saying that we are not specified and if it's not specified, it's not proven.

</details>

**主持人**: 好的。那你们怎么解决这个问题？

<details>
<summary>Original English</summary>

**Host**: Okay. So what do you do about that?

</details>

**Carina Hong**: 是的。我们还没有做到。好的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So we're not there yet. Okay.

</details>

**Carina Hong**: 目前，我们目前的愿景是，任何可以指定的东西都可以被证明。好的。现在显然有些人在这方面做得很好，那就是非形式化推理者可以介入的地方。

<details>
<summary>Original English</summary>

**Carina Hong**: Currently uh you know like again the the the vision as of currently is anything that can be specified can be proven. Okay. Now obviously there are people have been really good at you know that's where maybe where that's informal kind of reasoner come in

</details>

**Carina Hong**: 对，非形式化推理者可以。我希望引用测试文献，测试很棒，因为测试就像，嘿，你有没有考虑过这个？我想强调我们CTO **Shou**关于基于变异的**LM**单元测试生成的工作，他曾是**Facebook**广告研究的总监。你思考它的方式是，AI会问你，嘿，你有没有考虑过这个案例？这有点像**猜想**。

<details>
<summary>Original English</summary>

**Carina Hong**: right the informal reasoner can and this is I want to kind of you know call the literature of testing like testing are great because testing is like hey have you thought about that right like like I want to highlight the work mutation based you know **LM unit test generation** by accident CTO **Shou** and he was a director of **Facebook ad research** like the way you kind of think about it is like the **AI** will be like hey have you thought about have you thought about this this this case like and so this is a little bit like **conjecture**

</details>

**主持人**: 所以**猜想**有助于规范。

<details>
<summary>Original English</summary>

**Host**: so the **conjecture** is going to help with the specification

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**Host**: I see

</details>

**主持人**: 然后证明者进行证明。

<details>
<summary>Original English</summary>

**Host**: and then the prover does the proof

</details>

**主持人**: 所以这是一个互动过程，也许那个人，这样我们才能给出好的具体规范。

<details>
<summary>Original English</summary>

**Host**: and so this is an interactive process maybe that the person so that when we're actually giving good specific

</details>

**Carina Hong**: 我认为这是**代码生成**的未来，是的，我认为这是**代码生成**的未来。我认为这就是，即使我们假设一切都可以形式化验证，研究自动任务生成仍然很有趣，因为它基本上提供了规范建议。

<details>
<summary>Original English</summary>

**Carina Hong**: I think this is the future of coding yes I think this is the future of coding and I think this is where you know this is where I think even if we are suppose like given the assumption that everything can be **formally verified** you know like studying sort of like you know **automatic task generation** is still interesting because it it is basically giving you the **specification proposal**. Yeah.

</details>

**主持人**: 对。然后另一件事是，让我们谈谈所有的**形式化**，也就是定义它的能力。它是一种将更非形式化的东西转化为更形式化的东西，或者说**形式化**。所以假设我有一个为**ICPC**编写的编码问题，这个问题是用英语写的，比如**Alice**和**Bob**等等。好的。现在我想把它转换成一个形式化陈述，一个形式化规范。我如何进行自动形式化步骤？现在这将会很困难，因为我还没有解决这个问题。所以我没有任何信号。我没有任何基础。测试用例的输入输出对将会成为我的基础。

<details>
<summary>Original English</summary>

**Host**: Right. And then another thing is let's talk about all the **formalization** right which is the ability to to define it. It is kind of conver uh converting something that is more more informal uh into a into something that is more formal or the **formalization**. Um so suppose I have a coding problem that is written for **ICPC** and this problem is written in English like **Alice** and **Bob** blah blah blah. Okay. Now I want to convert that into a **formal statement** like a **formal spec**. How do I do the **auto formalization step** right now? This is going to be how because I have not solved the problem yet. So I don't have any signal. I don't have any grounding. The **test cases input output pair** is going to ground my formost.

</details>

**主持人**: 所以我知道我必须知道我将给出这个输入。我将给出这个输出。它必须具有这些特性。所以我会编写测试用例，我会编写一个，那么**Lean**中有没有类似的机制，你只需要知道你期望的结果是什么，然后证明是完全的，这很烦人，因为很多时候都是证明。

<details>
<summary>Original English</summary>

**Host**: So I know I have to know I'm going to give this input. I'm going to give this output. It has to have these characteristics. And so and so I write **test cases** and I write a so is there equivalent in **lean** of this right where the specification where you just know the sort of like outcomes that you are expecting so that like you the statement of the the result and then the but the proof is completely un quite annoying because it's like a lot of the times it's proof

</details>

**Carina Hong**: 所以你实际上没有数值答案来作为基础。

<details>
<summary>Original English</summary>

**Carina Hong**: so you don't actually have the numerical answers to ground it.

</details>

**主持人**: 好的。所以自动形式化是一件相当困难的事情。

<details>
<summary>Original English</summary>

**Host**: Okay. So **autoformmization** is a quite quite a hard thing to do.

</details>

**Carina Hong**: 嗯，因为你知道通常发生的情况是，你无法，只是很难将一个陈述的自动形式化作为基础。你显然可以将一个证明的自动形式化作为基础。

<details>
<summary>Original English</summary>

**Carina Hong**: Um because you know what's generally happened is um you can't you just it's hard to ground the **auto formalization** of a statement. You can obviously ground the **automization** of a proof

</details>

**主持人**: 但因为你可以直接运行它。

<details>
<summary>Original English</summary>

**Host**: but because you can then just run it

</details>

**Carina Hong**: 但你需要人工检查。

<details>
<summary>Original English</summary>

**Carina Hong**: but you need human to eyeball it.

</details>

**主持人**: 一个具有相当规模的形式化程序的**Lean**证明有多大？我的意思是，它们会随着程序的大小而增长，还是会超线性增长？

<details>
<summary>Original English</summary>

**Host**: How big is a **lean proof** of like a **formalized** you know of a **formalized program** of significant size? I mean do they grow with the size of the program or do they grow super linearly?

</details>

**Carina Hong**: 是的，目前实际上，每编写一行代码，就可能需要**20行证明**。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, currently actually you know for each line of code written there could be like **20 lines of proof**.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: Okay,

</details>

**Carina Hong**: 看起来不太好。

<details>
<summary>Original English</summary>

**Carina Hong**: it's not looking that great.

</details>

**主持人**: 但这是一种线性关系，还是随着程序的复杂性增加，它也会随之增长？

<details>
<summary>Original English</summary>

**Host**: But but is that like a linear relationship or is it as the complexity of the program gets greater then it like it you know sort of also grows so that it's

</details>

**Carina Hong**: 我对它的**扩展定律**没有很好的答案。

<details>
<summary>Original English</summary>

**Carina Hong**: a good I don't have a good answer to the **scaling law** of that.

</details>

**主持人**: 好的。是的。因为我知道这是**形式化验证**中的一个问题，对吧？你需要为即使是简单的程序提供非常非常长的证明。

<details>
<summary>Original English</summary>

**Host**: Okay. Yeah. Because I know that that's a problem in **formal verification**, right? Where you have these huge pro like you have to have these very very long proofs for even simple.

</details>

**Carina Hong**: 是的。那么，当您开始处理更大规模的**LLM**时，您是否会遇到**LLM**能力的局限性？

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So then then do are you going to run into sort of like limitations in in the capabilities of **LLMs** when you start to get to large larger um

</details>

**Carina Hong**: 我们坚信我们正在构建一个**推理引擎**。

<details>
<summary>Original English</summary>

**Carina Hong**: what what we believe fundamentally is we are building a **reasoning engine**.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Mhm. [clears throat]

</details>

**Carina Hong**: 我们看到一个证明者处理非常巨大的证明树，就像一个证明的树。

<details>
<summary>Original English</summary>

**Carina Hong**: And we have seen a prover deal with really huge trees that are like you know tree of a proof.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: Okay.

</details>

**Carina Hong**: 我们看到它从**40个节点**扩展到**4000个节点**。

<details>
<summary>Original English</summary>

**Carina Hong**: Uh we have seen it scale from **40 notes** to **4,000 notes**.

</details>

**主持人**: 等等，抱歉。**X Prover**是**LLM**吗？

<details>
<summary>Original English</summary>

**Host**: So wait, sorry. Actually **improver** is the is the **LLM**.

</details>

**Carina Hong**: **Axiom Prover**是一个由多个模型组成的集成系统，我们对其进行**后训练**。

<details>
<summary>Original English</summary>

**Carina Hong**: **Action improver** is a **ensemble system** of multiple models that we do **post training**.

</details>

**主持人**: 我明白了。好的。

<details>
<summary>Original English</summary>

**Host**: I see. Okay.

</details>

**Carina Hong**: 而且它还包括**AXO**发布的工具。抱歉。

<details>
<summary>Original English</summary>

**Carina Hong**: And also it also includes obviously the tools that **AXO** that we have um open released. Sorry.

</details>

**Carina Hong**: 换句话说，是的。所以我们看到它能够处理越来越复杂的任务。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. In other words, yeah. So so we have seen it being able to deal with more and more complex task.

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**Host**: I see.

</details>

**Carina Hong**: 我们不认为它部分受限。你可以问，它是否在预训练基础模型上受到某个点的限制？

<details>
<summary>Original English</summary>

**Carina Hong**: We don't think it's partially bound. You could ask, you know, is it bounded at one point on the pre-trained base model?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah,

</details>

**Carina Hong**: 我认为这是一个好问题。我认为，中期训练可能非常有趣，因为它确实，很多能力提升都来自于那一部分，对吧？如果你可以争辩说，即使你尝试**强化学习**一个不太有天赋的人，那个人表现也可能比未经后训练的**拉马努金**差很多，你可以争辩说，这是非常悲哀的现实，但是，所以在某个时候我们可能会考虑这样做。

<details>
<summary>Original English</summary>

**Carina Hong**: I think that's a good question. I think, you know, **mid-training** could be very interesting because it does actually, you know, a lot of the sort of capability gain does come from that part, right? If you could argue that even if you uh try to **reinforcement learn** some uh person who is not very talented uh that person might behave you be be perform a lot less well than an un unpost trained **Raman** you can you can you can argue that very very sad reality of things but um so at one point we might consider doing doing that

</details>

**Carina Hong**: 但我们认为还有很多可以推动的地方。

<details>
<summary>Original English</summary>

**Carina Hong**: then but we think there's so much to push

</details>

**主持人**: 所以你觉得现在有很多开销，或者说有很多。

<details>
<summary>Original English</summary>

**Host**: so you just feel like there's so much overhead right now or so so much um

</details>

**Carina Hong**: 增长空间，以至于你目前没有遇到理论限制。我只是想知道，因为**LLM**可以解决的问题的计算复杂性最近有了一些结果，我认为这些结果并不是**Claude Code**编写代码时的担忧，但我可以想象在这个系统中，问题会变得足够大，以至于你有无数行的**Lean**，你无法将它们放入上下文窗口，所以你必须聪明地处理，然后你必须总结，然后你不断地总结，很快你就会失去对正在发生的事情的追踪，而且像这样一个非常大的系统，你似乎会遇到。

<details>
<summary>Original English</summary>

**Carina Hong**: space taste to glow that that you're not running into theoretical constraints at this point. I I just wonder because you know there's been recent results in the **computational complexity** of the problems that **LLMs** can solve fundamentally and I don't think that they're really a concern for you know when I'm writing code with **cloud code** but I can imagine problems becoming big enough in a system like this where you have a gazillion lines of **lean** you can't get them get them into the context window so you have to like be smart about that and then you have to summarize and then you're summarizing and summarizing and pretty soon are like kind of losing track of what's going on and it just seems like with a large very large system like that you might run into.

</details>

**Carina Hong**: 是的，我认为这很有趣。这总是关于丰富的问题。所以简单地讲，数学发现的复兴已经到来，**Axiom Prover**确实尝试证明一切，最终你会得到数万行的**Lean**证明。所以首先，自动非形式化比自动形式化容易得多，因为没有基础的问题。你知道，每个模型都看到了大量的文本和大量的**Lean**。所以，你总是可以把**Lean**转换回非形式化的东西，然后就出现了一个问题，你如何知道自己是否正确？你可以依靠循环一致性。所以，你再次形式化，然后证明程序等效性之类的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think this is this is interesting. It's always a problem of abundance. So simple you just like keep really the the **mathematical discovery renaissance** has come **action prover** does try to prove everything you end up with like tens of thousand lines of **limp proof**. So first of all it's auto informalization is a lot easier than auto formalization minus a problem of no grounding right. you know, every every model has seen a lot of text and a lot of **lean**. So, you can always, you know, convert that lane back into back into informal and then there's the problem of well, how do you know if you're correct or not? You can rely on cyclic like consistency. So, you then formalize again and like prove like **program equivalent** something like that. So, that's

</details>

**主持人**: 哦，所以你先非形式化，然后形式化，你可以用它来确保你仍然使用。是的，是的。虽然非形式化显然是一个不那么困难的问题，所以你总是可以做到。所以对于我们输出的很多**Lean**代码，我们可以有一个非形式化的摘要器，它实际上做得很好。所以这是一个事情。还有另一个问题，我认为这很有趣，我想去年在**温哥华ICML**的AI数学研讨会上有一个小组讨论，有**Leo Deora**和**Java Jere Jeremy Aigod**，还有**Shoubo**和CTO在场，他们讨论的是，人类或数学家是否会在某个时候停止尝试理解正在发生的事情？

<details>
<summary>Original English</summary>

**Host**: Oh, so you you like informalize and then formalize you can use it to make sure that you still use Yeah. Yeah. like and although informalization is you know obviously less hard a problem so you can always do that. So for a lot of the you know the the link code that we output we can have an informal summarizer of of like big chunks of l is actually doing okay so you know that's that's a that's a thing and there's have another question of like which I think is very interesting is I think there's a panel at um **ICML Vancouver** last year um at **AI for mass workshop** there's like **Leo Deora** and **Java Jere Jeremy Aigod** and um **Shoubo** and CTO was there and they were talking about like will will humans or mathematicians at some point stop trying to understand what's going on there right because like

</details>

**Carina Hong**: 假设你是一个非常有抱负的数学家，你希望证明你的假设，然后突然出现了一个**Lean**证明，而且它确实是正确的，只是有**100万行**。嗯，是的，这难道不是对社区的一个巨大负面影响吗？因为我的意思是，通常当有人提出了一个重要的证明时，通常它会开始，我正要说到那里，对吧？就像，那种负面结果是否会发生，这是小组讨论的问题。这完全是假设性的，没有人，没有模型系统可以证明我的假设，所以请注意，请不要剪掉那部分。但是，人们仍然会尝试理解正在发生的事情，我认为答案通常是肯定的。我认为好奇心和理解数学或其他领域正在发生的事情的渴望，是人类的基本需求。我认为这是一种乐观情绪，在一个我所认为的验证式**超智能**时代，假设我们达到了那个阶段，即使所有输出都将以更快、指数级增长的速度产生，超出人类可能消化的范围，他们仍然会尝试消化它，他们仍然会尝试消化他们认为重要的那些。所以，注意力是瓶颈，如果注意力是瓶颈，那么直觉和品味，也就是哪句话可能值得人类消化，以及在有限的计算机资源下，哪句话值得消耗，值得投入计算资源，这些都将由人类数学家的品味来引导，我认为这非常美妙。

<details>
<summary>Original English</summary>

**Carina Hong**: suppose you're a really ambitious mathematician you're like I want to proof read my hypothesis and bang here's a **limp proof** and like it's actually correct and it's just like you know problem **1 million lines**. Um yeah, isn't that like a big negative for the community because I mean usually when someone comes up with a big proof of something um often times it process I was about to get there right it's like well will will that negative outcome happen was a question the panel was discussing it's completely hypothetical no one's no one's like you know model system can can prove my hypothesis right so the disclaimer please please don't cut that part [laughter] just stand alone um but like you know um well people still trying to try to understand what's going on and I I think the answer is usually is is always yes. I think curiosity and the the desire to understand what is going on you know um mathematically or in other domains as well. It's a basic human need and I think that is like I think a dose of optimism in an era of I think **verified super intelligence** suppose we get there is that even even if all the outputs are going to be produced and at a much you know faster pace and much more exponential volume compared to what humans could possibly consume they're still going to try to consume it and they're still going to try to consume the ones that they deem important. So then basically attention is the bottleneck and if attention is a bottleneck then really intuition and taste uh you know of which statement is probably worth worth the consumption of human and also maybe in a finite computer resource worth worth the consumption worth the the sort of spending of compute resources that's where human mathematicians taste will always guide us and I think that's incredibly beautiful

</details>

**主持人**: 那么，内部地获取结果，然后尝试通过许多不同的途径发送您的系统，以获得概念上正交的证明，这样您就可以获得一组多样化的推理方式来解决同一个问题，因为我认为这可能非常有价值，如果您给它一个问题，它会说，哦，这是一种粗暴的自然方式，可能有些人会这样做。然后还有一种更短、更优雅的方式。那么您有没有考虑过训练您的模型以某种方式变得优雅？

<details>
<summary>Original English</summary>

**Host**: is it worth like internally taking like results So you can prove one way and then trying to send your system at many different routes to get like or like orthogonal conceptually orthogonal proofs and so you kind of get a diverse set of different ways of you reasoning about the same thing because you know I think it could be very valuable if you give it a problem to say oh well like here's kind of the brute force natural way that like maybe some humans would do it. Um and then the uh there's like a really much shorter elegant way of doing it. So have you essentially thought about training your models to be elegant in some ways?

</details>

**Carina Hong**: 是的，我们迟早会做到这一点，因为我认为这个猜想可能取决于我们对**品味**的定义，**优雅**对我来说感觉像是一个对齐问题，你知道，谁来决定什么是**优雅**？人类来决定什么是**优雅**，对吧？这就是人类的特点。勤奋工作是很重要的，你努力工作的东西，你就会擅长。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, at one point we're going to get to there because you know I think the conjecture uh will probably depend on what what you know will probably depend on what we mean by taste elegance feels like an alignment problem to me you know like you know who who gets to say what is elegant humans get to say what is elegant right that's what makes human right there's something about hard work right that what what you work on hard is what you're going to be good at

</details>

**主持人**: 是的，是的，我们会在很多领域遇到这个问题，对吧？不只是数学。如何成为一名拥有真正良好高层次理解的资深程序员？嗯，我想是**全栈**理解，高层次和低层次。

<details>
<summary>Original English</summary>

**Host**: yeah yeah and we're going to have a problem about that I think like pretty much in a lot of the domains as well, right? Not just math. Like how do you be that senior um programmer with you know really good high level understanding? Well, I guess **full stack** understanding high level and low level

</details>

**主持人**: 如果你没有经过一年的培训。

<details>
<summary>Original English</summary>

**Host**: if you haven't spent the year of training.

</details>

**Carina Hong**: 我的意思是，我会争辩说，这很哲学，但你知道，我不需要擅长**汇编语言编程**，对吧？没有多少人擅长那个。少数人擅长，因为这对于他们的工作很重要。

<details>
<summary>Original English</summary>

**Carina Hong**: I mean I would argue that you don't this is very philosophical but like you know I I don't need to be good at **assembly language programming** right like no not many people are good at that. A few people are because it's important for their job.

</details>

**Carina Hong**: 这不是经验，而是好奇心。

<details>
<summary>Original English</summary>

**Carina Hong**: It's not experience but curiosity.

</details>

**主持人**: 是的。但是对我来说感觉有点不同，因为不擅长证明之类的东西，对吧？这似乎是一个根本性的差距，也许我的思维方式不会以同样的方式发展，如果我不这样做的话。而如果我不擅长**汇编语言编程**，但我擅长更高级别的编程，那么这可能无关紧要。

<details>
<summary>Original English</summary>

**Host**: Yeah. So, but but it feels to me a little different because not being good at like proving things for example, right? That seems like a fundamental gap in like that maybe my mind doesn't develop in the same way if I am not doing that. Whereas if I'm just not good at **assembly language program** well, but I'm good at like higher level programming. So maybe that doesn't matter.

</details>

**Carina Hong**: 我想这可能是因为教育系统或流程的工作方式，如果你没有表现出早期的才华，有时你就不会经历**预训练**的过程。

<details>
<summary>Original English</summary>

**Carina Hong**: I think that's probably because how the maybe how the education system the pipeline works which is that if you do not show early signs of brilliance you don't sometimes go through the process of **pre-training**

</details>

**主持人**: 在数学方面。

<details>
<summary>Original English</summary>

**Host**: in math.

</details>

**Carina Hong**: 是的。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. [laughter]

</details>

**Carina Hong**: 对。所以你可能会争辩说，你不需要学习所有东西来培养品味，但你需要达到一个门槛。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. Like so so that maybe you can argue that you don't need to say you know learn everything to develop a sense of taste but there's like a threshold you kind of need to meet.

</details>

**主持人**: 是的。所以举例来说，你可能需要能够**代码生成**，即使你不需要理解**汇编语言**，而且这可能会**迁移**我的直觉，或者你知道我的直觉可能会从我试图追求的奥林匹克竞赛中**迁移**，而漫画的**迁移**更直接。它非常相似，数论可能会更远，但仍然可以。然后当它变得与奥林匹克竞赛的**迁移**完全不同时，它的强度就没有那么高了，但你知道，你需要像你说的勤奋，你需要勤奋地进行一定量的训练。

<details>
<summary>Original English</summary>

**Host**: Yeah. So for example, you probably need to be able to code even if you don't need to understand **assembly language** and that thing might transfer my intuition or you know my my [clears throat] intuition might transfer from the Olymp I tried to pursue and comics transfer is more direct. um it's very similar and number theory could be further but still okay and then when it gets to like something that's a lot more different than **Olympian mass transfer** is that strong but kind of like you know you need to diligent as you said right like you need to diligently go through some amount of training [snorts]

</details>

**主持人**: 如果人们过度依赖强大的**AI**，那将不会发生。

<details>
<summary>Original English</summary>

**Host**: and if people over rely on strong **AI** and that doesn't happen

</details>

**主持人**: 我想换个话题。

<details>
<summary>Original English</summary>

**Host**: I want to switch gears

</details>

### Axiom Math的商业愿景：验证驱动的未来
**主持人**: 你提到了**软件验证**，有哪些领域？你们如何赚到足够的钱来证明这种估值是合理的？顺便说一句，恭喜你们。

<details>
<summary>Original English</summary>

**Host**: you mentioned uh **software verification** what are the domains how are you going to make uh enough money to justify the valuation that like and congratulations by the way.

</details>

**Carina Hong**: 谢谢。

<details>
<summary>Original English</summary>

**Carina Hong**: Thank you.

</details>

**主持人**: 那么，你们向投资者展示的，为什么这真的能赚大钱的高层次总结是什么？

<details>
<summary>Original English</summary>

**Host**: How so what what's the give us the the high level summary of like what is the what is the vision that you show you put in front of investors about why does this actually make a lot of money?

</details>

**Carina Hong**: 是的。首先，这一轮是有点先发制人的。所以我想很多投资者对**Axiom**非常感兴趣。就我们所相信的而言，我们认为未来的**代码生成**将受到验证能力的限制。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So um first of all this round is kind of preemptive. So it's uh I think a lot of the investors have pretty high interest about about **Axium**. Um in terms of kind of what we believe in, we believe the future of coding is going to be somewhat constrained by **verification capability**

</details>

**Carina Hong**: 我们相信解决**形式化数学**是一个非常自然的起点，然后通过扩展，你可以提高**硬件**和**软件**的验证能力。例如，对于**硬件**来说，这相当具有革命性。我的意思是，我们知道，对于一个大部分经过验证的**GPU**，没有部分信用。

<details>
<summary>Original English</summary>

**Carina Hong**: and we believe in solving **formal mass** is a very natural starting point and then by extension you can increase the **verification capability** across **hardware** and **software** and for **hardware** for example that's quite revolutionary. I mean that is there is no as we know there's no partial credit for a mostly **verified GPU**.

</details>

**主持人**: 不。

<details>
<summary>Original English</summary>

**Host**: No

</details>

**Carina Hong**: 哈哈。

<details>
<summary>Original English</summary>

**Carina Hong**: uh [laughter]

</details>

**主持人**: 要么全有，要么全无。

<details>
<summary>Original English</summary>

**Host**: it's all or nothing.

</details>

**Carina Hong**: 要么全有，要么全无。而且你确实需要一个完美的证明者。我想强调这一点，假设我是一个喜欢解决数学问题的人。我想有很多**Twitter**用户喜欢像**Pokemon**一样捕获**Erdos问题**，然后我只是尝试使用非确定性的**OM**，比如**GPT**，来尝试获得完整的证明。

<details>
<summary>Original English</summary>

**Carina Hong**: It is all or nothing and you do and you do need a perfect prover like I want to stretch that which stress this point which is that suppose I am a you know I am someone who loves solving maths. I think there are a lot of **Twitter** users who enjoy **Pokemon** like hunting um **Erdos problems** and then I just try to um you know use a non-deterministic **OM** uh like **GBT** say to try to get the full proof for that.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 现在我可以做很多次，我可能会成功，也可能不会，我可能对是否成功没有问题。这绝对不适用于**硬件验证**。所以对于那些我称之为需要**硬核验证**的领域，这是一个痛点。这是一个当前的痛点，有数百名人类和数千个许可证致力于解决一个局部**电网问题验证**。

<details>
<summary>Original English</summary>

**Carina Hong**: Now I can do that many many times and I might succeed and I might not and I might not have a problem with whether I actually succeed or not. This absolutely does not work for **hardware verification**. So for those kind of domains which I call like **hardcore verification** needed it is a painoint. It is a current painoint there there there are hundreds of humans and thousands of licenses being dedicated to solve one local **grid problem verification**.

</details>

**主持人**: 顺便说一句，我的理解是，**ASIC**项目从设计到验证的行业标准大约是**1比3**到**1比4**。

<details>
<summary>Original English</summary>

**Host**: Just as an aside, the my understanding is that the industry standard for design to verification in a **asich as project** is like **1 to three 1 to**

</details>

**Carina Hong**: **4比3**到**4比3**。是的，**团队规模**和**持续时间**都是如此。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: **four to three to four**. Correct. Both in say **Tim size** and then **duration**. Yeah.

</details>

**主持人**: 对。所以如果你乘以那个平方，那么我想，那是一个我认为是必须覆盖的领域。现在对于**软件验证**来说，这很有趣，因为你知道，我们可能都意识到，我的侄子编写了一个可爱的网站，绝对没有必要形式化验证那段代码，为什么要呢？我从**Kats**那里听到了一个故事，**纽约时报**记者**Kats**告诉了我这个故事，就是。

<details>
<summary>Original English</summary>

**Host**: Right. So if you multiply that uh yeah square and then I think so so that's that's a I would say like you know it's a it's a must cover. And now for **software verification** it is it is interesting right because you know as probably we all realize like my nephew vibe codes a lovable website there is absolutely no need to **formally verify** that piece of code like why would you now I heard of a story from **Kats** actually that **New York Times reporter** who um told me the story which is like

</details>

**Carina Hong**: 然而，如果你想想在智能体时代，我的**Open Claw**可能可以做各种事情，也可能做一些坏事。我的**Open Claw**可能会决定给我的教授打上一些坏标签，对吧？然后你可以说，这或许是形式化验证的问题吗？可能仍然不是，对吧？你可以改变**行动空间**，使其更受限制。所以你不需要依赖形式化验证。所以你可以有很多案例，但你可以想想，也许一个处理大量监管事务的企业，使用智能体，他们可能想做一些事情，这是他们的选择，但我会争辩说，验证能力的提高，无论是在**延迟**还是**准确性**方面，所有这些因素，整体性能，都将决定人们是否依赖形式化验证。

<details>
<summary>Original English</summary>

**Carina Hong**: however if you think about like you know in the time of **agents** like my **open claw** can probably do all sorts of things and probably can do some bad things. Uh like my **open claw** can decide to like tag something bad to my professor, right? Like and and and you can say that perhaps is that a problem of **formal verification**? Probably still not, right? You can change something about the **action space** and make it more limited. So you don't you don't need to rely on for verification. So you can have a lot of cases but you can think about you know maybe an enterprise that is dealing with a lot of **regulatory** kind of stuff using **agents** they might want to do something like it it's their choice but I will argue that the improvement of **verification capability** both in **latency** you know and in **accuracy** all these stuff the performance holistically is going to determine whether people rely on **formal verification** or not.

</details>

**主持人**: 当然。所以从某种意义上说，我们想把它做得很好，以至于我们基本上可以做出选择。那么，为什么投资者认为你们能做到这一点呢？因为我的意思是，人们一直在做验证工作很长时间了，我认为每个人都同意这是一个重要的问题，而且我认为，如果我能为我编写的每个程序都提供一个验证证明，比如，嘿，**Claude**，也给我证明，然后它就生成了，哦，是的，看起来不错。我绝对会这样做。但是，为什么投资者在您看来看到了什么，从而说服他们，好吧，这就是时候了，我要投入**2亿美元**或其他什么的？

<details>
<summary>Original English</summary>

**Host**: Sure. So in a way we want to make it so good that basically we can make that a choice. So, so why did the investors think that you could do this, right? Because I mean people have been working on **verification** for so long and I think everyone agrees it's an important problem and it and I think certainly if I can just have a **verification proof** for every program that I write like hey **Claude** like give me the proof also and then it just produces it and oh yep looks good to me. I would absolutely do that. But so why is it what was it that the investors saw in your opinion that persuaded them that okay this is the moment I'm gonna put in my **200 million** or whatever?

</details>

**Carina Hong**: 我认为，当涉及到信念时，要么你有，要么你没有。所以，要么你和我们一起梦想，要么你不，这没关系，因为当我们实现梦想时，公司将价值**100亿**。

<details>
<summary>Original English</summary>

**Carina Hong**: I think um when it comes to faith you either have it or you don't. So you either dream the dream with us or you don't and that's okay because when we realize the dream the company is going to be worth **10 billion**.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 所以我认为这就是我的感受，我们相信验证是**超智能**的关键部分。我们版本的**超智能**是绝对经过验证的。

<details>
<summary>Original English</summary>

**Carina Hong**: So I think that's kind of the the feeling that I have which is that we believe verification is the critical critical part to **super intelligence**. Our version of **super intelligence** is absolutely verified.

</details>

**Carina Hong**: 我们不认为有任何其他的可能性。我们不相信。

<details>
<summary>Original English</summary>

**Carina Hong**: We don't think there's any other possible future. We do not believe that

</details>

**Carina Hong**: 我要郑重声明，我们不相信一个非形式化的数学系统将是大众**AGI**解决方案。为什么不呢？

<details>
<summary>Original English</summary>

**Carina Hong**: I'm going to say on the record we do not believe that an informal mass system is going to be the mass **AGI** solution. Why not?

</details>

**Carina Hong**: 我们只是不相信。

<details>
<summary>Original English</summary>

**Carina Hong**: We just don't believe that.

</details>

**主持人**: 我的意思是，反驳的观点是，哦，你知道，我们只是做了很多好的**RL**，而且我们已经看到了**GPT**解决了某些问题等等。那么你为什么认为它会后继乏力呢？

<details>
<summary>Original English</summary>

**Host**: I mean, the counterargument is, oh, you know, like we just do a lot of good **RL** and you know, we've seen uh **GPT**, you know, solving, you know, I think some problem and like whatever. So why do you think that that runs out of gas?

</details>

**Carina Hong**: 是的。所以你可以说，如果你是一个前沿数学家，你拥有无限的资源，那么按定义就没有后继乏力。如果你认为无限意味着没有后继乏力，我不认为它会扩展到**超智能**。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So you can say that if you are a **frontier math** and you have like so sorry **frontier lab** and you have like infinite resources why does there is by definition no running out of gas right if you think like infinite means like there's no running out of gas I don't think it's going to scale to **super intelligence**.

</details>

**主持人**: 所以你认为你会耗尽，比如，耗尽资金或者耗尽力量？

<details>
<summary>Original English</summary>

**Host**: so you think that you run out like you run out of money basically or run out of power

</details>

**Carina Hong**: 当然，我们作为一家初创公司，首先做不到这一点。

<details>
<summary>Original English</summary>

**Carina Hong**: sure so we as a startup first of all cannot do that we first of all as a startup cannot do that

</details>

**Carina Hong**: 但我们普遍认为，形式化数学通过将数学证明转化为程序代码，为我们提供了更好的性能。所以，这只是你的**样本效率**论证等等，你就是，也许你就是无法充分弯曲曲线，如果你不使用形式化。问题是，非形式化的东西也可以被我们利用，如果你真的喜欢，你可以同时拥有非形式化和形式化系统，那将是非常强大的。

<details>
<summary>Original English</summary>

**Carina Hong**: but we generally think that **formal mass** then by sort of converting mass proofs to programs to code give us much better performance. So, so it's just it's your **sample efficiency** argument and so forth that you just and maybe you just can't that that you can't bend the curb enough if you don't use formal. The thing is the the thing is the informal stuff is also available to us in a way if you really like you can have a both informal and formal system and that is going to be

</details>

**主持人**: 我明白了，我明白了。

<details>
<summary>Original English</summary>

**Host**: I see I see

</details>

**Carina Hong**: 非常强大。我认为我怀疑我们是否能仅仅通过非形式化方法扩展到大众**AGI**，你会不断地拥有**LLM**裁判解决方案，或者你拥有人类专家进行评分。而人类专家的扩展性并不好。然后如果你真的争辩无限，那么当然你有无限的资金，你可以支付无限的费用。是否有真正无限数量的人能够理解并证明**朗兰兹纲领**中的非平凡结果？我想，祝你好运找到这些人。事实上，我认为前沿数学是如何走到一起的，是因为他们无法通过他们的专家库组建一个基准，所以他们不得不与**Epoch**合作来完成。我认为这正是我担心人类部分的问题。所以他们有**LLM**裁判，然后现在是**随机裁判**。问题是，某事是无法实现，还是极其昂贵，极其昂贵的实现最终会混淆在一起。

<details>
<summary>Original English</summary>

**Carina Hong**: very strong the thing that I kind of like I think my my suspicion about like you know whether we can scale to mass **AGI** just by the informal approach is you're going to keep having you know the **LMS judges solution** or you have human experts who grade And it's just human experts like doesn't scale that well. And then if you really argue infinite infinity then sure then you also have infinite money and you can pay infinite there there's so many is there really infinite number of people who can understand and prove at say like about like you know a result a nonual result in **langland's program** I think you know good luck finding those people and in fact I think how **frontier maths** came to came came together is because they couldn't assemble a a a benchmark by their expert pool so they have to you know collaborate with **epoch** to do it right and and I think that's kind of what what I worry about about qu having the human part. So they have **LMS judges** and then now **stocastic judging**. The problem is like whether something is impossible to achieve versus something is incredibly expensive and like really incredibly expensive and incredibly expensive to achieve get kind of like mixed in the end.

</details>

**主持人**: 然后投资者总是想知道为什么是你们，对吧？所以我读了一些关于你的背景，我认为如果我们不让听众了解一些你的个人故事，那将是对听众的不负责任。

<details>
<summary>Original English</summary>

**Host**: And then of course investors always want to know why you, right? So I've read a little bit about your background and I think it we would do a disservice to the audience if we didn't hear a little bit just about your personal story.

</details>

**Carina Hong**: 我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: I see.

</details>

**主持人**: 你想谈谈你做过的一些非常有趣的事情吗？所以我很想听听你和你的团队。

<details>
<summary>Original English</summary>

**Host**: Do you want to talk just a little bit about like you've you've done some really interesting stuff. So I I'd love to hear like you and then your team. Yeah.

</details>

**主持人**: 是什么让**Axiom**如此特别？

<details>
<summary>Original English</summary>

**Host**: What what what makes **Axium** special?

</details>

### Axiom Math的团队与创始人背景
**Carina Hong**: 是的，我认为**Axiom**非常特别，因为他们真的是专业的数学家。基本上，他们是我们正在开发的系统的用户，而且迭代周期非常快。它非常非常快。你们有一些非常强大的数学家，包括研究和奥林匹克竞赛，还有一些**mathlib**贡献者、维护者、开发者，真正的**Lean**爱好者，并将他们与来自**Metafair**和**Golden Age**等非常强大的组织的应用机器学习人员，以及拥有**codegen**专业知识（例如**Colonel Jan**）的编译器专家结合在一起。我认为这种跨学科的思维方式非常有帮助。我们认为AI数学传统上就是跨学科的。人们从AI科学中借鉴技术，纯技术人员从**codegen**文献中借鉴技术，人们显然也从更广泛的前沿应用机器学习中借鉴技术，试图将其应用于AI数学这个小众问题。所以我们也认为拥有这样一支非常特殊的团队是一种差异化优势。我们还认为，正如你所说，没有永久的模式。我们生成的专有数据，以及我们看到的一些飞轮效应，是一种时间模式。就我个人而言，我热爱数学。我认为，我从小就一直在学习数学，当你要解决的问题有点超出能力范围时，数学有时会变得非常困难，这有时会让人感到沮丧。有时我会想，如果我能有一个AI来帮助我，那该多好。是的，我想，为什么不自己构建这样一个东西呢？

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think **Axium** is like very special because they're really expert mathematicians. Basically they are users of the system we are developing and that iteration loop is very fast. It is extremely it is extremely fast. You have like some of the strongest you know mathematicians and both in research and **Olympia** contest and you also have people who are um you know **mass li contributors**, maintainers, developers um **lingurus** really and u combine them with people who come from like applied **ML** um really strong organizations like **Metafare** um and **golden age** um as well as people who have **codegen expertise** who work with like compiler like **Colonel Jan** um have kind of these backgrounds of people together. I think that sort of **interdisciplinary way** of thinking about things quite quite helpful. We think **AI for math** has traditionally been quite **interdisciplinary**. People are borrowing techniques from even **AI for science**. pure tech um borrowing tech techniques from from the **code gen literature** and people are borrowing techniques from obviously the broader like you know frontier like applied **ML** um to try to apply on the niche problem **AI for math**. So we also think having this sort of very special special team is a is a differentiation. Uh we also think that you know as you say there's no no permanent mode. Um the proprietary data that we generate um and a little bit of a flywheel we are seeing is a time mode. Well me personally uh I I love math. I think, you know, I I kind of have been doing math since I was very young and like math sometimes gets really hard when when the problem you are solving are are just a little bit out of reach and it gets a bit depressing and times to times I wonder if I can just have an **AI** help me. [laughter] Uh and uh and yeah, I think why I figure why not build such a thing?

</details>

**主持人**: 你在**牛津大学**获得了**神经科学**硕士学位。

<details>
<summary>Original English</summary>

**Host**: You did a master's at **Oxford** in **neuroscience**.

</details>

**Carina Hong**: 这是否影响了你的思考？这是一个很好的问题。我认为我的神经科学经验让你学到什么很难，什么不可能。我的意思是，这很有趣。我认为那一年在神经科学领域让我对什么很难有了一些感觉，但对什么可能有效几乎没有感觉。但是我认为我当时在**神经科学**的幌子下，在**UCL Gatsby研究所**活动，并有幸与一些非常棒的教员一起进行**AI**研究，所以我认为那是非常富有成效的一年**AI**学习。

<details>
<summary>Original English</summary>

**Carina Hong**: Has that informed your thinking here? That's a great question. I think like my my my you know experience with **neuroscience** is you you learn very well but what's hard? [laughter] What's impossible? I mean it's very interesting. I think that year of **neuroscience** like give me some feelings about what's hard and almost no feeling about what might work. So, but I think I was kind of under the pretense of **neuroscience** like hanging out at the **UCL Gatsby Institute** and was fortunate to do **AI** research with some really cool faculties and so I think that was a very productive year of **AI study**

</details>

**主持人**: 非神经研究。你。

<details>
<summary>Original English</summary>

**Host**: non- neural study. You

</details>

**主持人**: 所以你当时主要是研究**AI**。

<details>
<summary>Original English</summary>

**Host**: so you're it was mostly for you studying **AI**.

</details>

**Carina Hong**: 没错。没错。我认为在英国，如果你在**20世纪**，如果你把某物称为**AI**，你就不会得到捐赠，但如果你把它称为**脑科学**，你可能还有机会。所以，**UCL Gatsby**是一个顶级的AI中心，很多人从那里去了**DeepMind**，包括**Demis**本人，那是一个非常棒的研究环境。我记得那些下午茶时间的谈话非常精彩，人们基本上只是在做AI。它被称为**Gatsby计算神经科学研究所**。

<details>
<summary>Original English</summary>

**Carina Hong**: That's right. That's right. I think in the **UK** if you um back back in the you know um **20th century** if you call something **AI** you would not get the donation but if you call something **brain science** you might have a chance. So, so the **UCL Gatsby** which is a premier **AI hub** where a lot of people actually go um you know from their to **deep mind** including **Deise** himself uh it's a very wonderful research environment. Uh I remember those kind of like tea time talks were very amazing and and people were basically just doing **AI**. Uh it's called the **Gatsby computational neuroscience institute**.

</details>

**Carina Hong**: 是的。我想那是因为我当时在**神经科学**硕士项目，然后很快意识到你需要杀死老鼠，而且不太想做那个。**计算神经科学**听起来更有吸引力。当你看到项目时，你看到**Transformer**，你就会想，你绝对想做那个。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. I think how how that kind of you know happened was because so I was I was in the **master of neuroscience program** and then um quickly realized that you need to like kill rats and um kind of don't want to do that and **computational neuroscience** sounds more appealing and and when you look at the project and you see like **transformer** you're like you absolutely want to do that.

</details>

**主持人**: 是的，我们都对此感到兴奋。

<details>
<summary>Original English</summary>

**Host**: Yeah, [clears throat] we're we're all excited about that. [laughter]

</details>

**主持人**: 那么，在**Gatsby**之后，你在**斯坦福大学**开始了数学博士项目。

<details>
<summary>Original English</summary>

**Host**: So so after the **Gatsby** uh you started a math **PhD** program at **Stanford**.

</details>

**Carina Hong**: 我实际上在法学院全职学习了一年。哦。

<details>
<summary>Original English</summary>

**Carina Hong**: I started actually one year full full-time at the **law school**. Oh.

</details>

**Carina Hong**: 因为**JD PhD**项目结构要求你必须全职居住一年。所以那也是非常有趣的一年，学习一些非常引人入胜的东西，比如**刑法**，研究**杀人案件**。很令人兴奋。不。

<details>
<summary>Original English</summary>

**Carina Hong**: Because the **JD PhD program** structured in a way where you have to spend full one full residency year. So that was also a very fun year um of learning things that like are just quite fascinating like **criminal law** looking at **homicide cases**. Exciting. No. Um

</details>

**主持人**: 你是否曾觉得**法律系统**在某种程度上被**低估**或**高估**了，也许你可以接触并改进它？

<details>
<summary>Original English</summary>

**Host**: do you ever feel like the **legal system** is under or oversp specified in some way that maybe you could um you could access and improve?

</details>

**Carina Hong**: 这是一个很好的问题。我认为对于很多事情来说，它绝对是**不明确**的。对于其他一些事情，我实际上对从**数学推理**到这些特定领域的**迁移学习**感到非常兴奋。我认为**上诉诉讼**，你看到一些真正优秀的**上诉学者**和律师，他们就是来自数学训练。不多，但像**Lawrence Tribe**就是一个例子，**哈佛大学法学教授**，是**民主党**中最强大的上诉诉讼和**SCOTUS**简报方面的**大脑**之一。我认为还有很多其他领域，比如**反垄断**，它非常像**流程图**；**合同法**有时也像**流程图**；**破产法**、**税法**，更多的是公司方面。我只是喜欢**诉讼**方面。

<details>
<summary>Original English</summary>

**Carina Hong**: That's a that's a great question. I think for a lot of things it's definitely underspecified. Um for some other things I was actually quite excited about sort of **transfer learning** from **mathematical reasoning** to those specific fields. I think **appella litigation** the **legal gymnastics** you see some really good **appellet scholars** and lawyers that just come from mass training. not many but like **Lawrence Tribe** for one you know **Harvard law professor** um one of the you know strongest like um you know **appallet litigation** and **SCOD's briefs** like brains on on the left uh **Democratic party** um and uh uh and I think there's a lot of other domains such as **antitrust** that's incredibly flowcharty **contract law** sometimes also flowarty **bankruptcy tax** u more on the corporate side I I I just love **litigation** side [laughter] I mean

</details>

**主持人**: 是的，所以实际上我只是因为我们正在谈论**诉讼**，这不一样，但有一个**Erdos问题**是**Axiom**发现的，我不知道是不是**Axiom Prover**，是不是这样？有一个关于它的争议，因为它声称解决了这个问题，但实际上证明已经被它发现了，然后只是形式化了。

<details>
<summary>Original English</summary>

**Host**: yeah so actually I do just just because we're talking about **litigation** it's not the same thing but there was a there was a **Erdos problem** that that **Axiom** saw I don't know if it was **Axium prover** or whatever is that right there was a controversy about it because it had represented that it had solved the problem when in fact the proof had been it had discovered the proof and then just formalized it.

</details>

**Carina Hong**: 是的。所以实际上发生的事情是，我们的竞争对手**Harmonic**决定宣传他们已经解决了未解决的问题，**Erdos数124**和**481**。我们相信他们的文献综述，认为这些问题确实没有被解决，我们当时还是一家非常年轻的公司。我们想测试我们的系统是否能尝试解决我们的竞争对手能解决的问题。我们完全没有想到它实际上解决了它们，但事实证明我们都错了，事实上这些问题之前就已经被解决了。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. So actually what happened was our competitor **Harmonic** decided to publicize that they have solved uh unsolved problems um **Erdog number** uh **124** and **481** and then we trusted their literature review believing that these problems are really truly unsolved and we were really young company at the time. We wanted to test if our system can attempt to try the problems that our competitor can. We fully did not expect that actually solved them but um turns out that we were both wrong that in fact the problem has been solved before. I see.

</details>

**Carina Hong**: 所以。

<details>
<summary>Original English</summary>

**Carina Hong**: So then

</details>

**Carina Hong**: 这不是我们唯一一次依赖他人的文献检索，我们应该承担责任。另一次是这篇名为**Dead Ends in Square-Free Walks**的论文。**Miller教授**遇到的这个问题实际上已经被解决了。但是，我们，我的意思是，我们确实应该尽到自己的责任。

<details>
<summary>Original English</summary>

**Carina Hong**: it's not the only time that we relied on others literature uh uh literature search and you know we we should own it. Um the other time was this paper called **dead ends in squaref free walks**. Um you know **professor** um uh uh **professor Miller** um have this problem that actually turns out to have been solved. But um we we I mean we really should have done our part. that is that is you know

</details>

**主持人**: 我想引出的问题是，并不是说你们做错了什么，而是。

<details>
<summary>Original English</summary>

**Host**: the point I'm trying to maybe elicit is um not not like you guys did something wrong but rather

</details>

**Carina Hong**: 你知道，就像日本的一个广告，整个公司，成千上万的人，在广告中道歉，就像，你知道，对不起，我们涨价了5美分，我当时在想，也许我应该也这样做。

<details>
<summary>Original English</summary>

**Carina Hong**: you know there's this like Japanese like um advertisement of like a whole company like hundreds and thousands of people like apologizing in the in the advertisement and it's like you know sorry we raised our price by like **5 cents** and that's the advertisement I was like thinking that maybe I should just do that [laughter]

</details>

**主持人**: 太尴尬了。

<details>
<summary>Original English</summary>

**Host**: it's so it's so embarrassing

</details>

**Carina Hong**: 不，但我认为信息来源的问题，以及如何，这又回到了我之前问的问题，我如何将答案与问题联系起来？

<details>
<summary>Original English</summary>

**Carina Hong**: no but I think that the question of providence of information and sort of like how do you it goes back to the question I was asking before about like how do I how am I connecting the answer to the question

</details>

**Carina Hong**: 是的，这是一个很好的问题。我认为在**Erdos**之后，我们变得非常非常小心。所以我们没有真正研究其他的**Erdos问题**。我相信**Harmonic**仍然声称他们解决了**Erdos问题**，这可能，我不知道。你知道，**Terrence Tao**和许多其他人都有一个包含所有**Erdos问题**及其状态的数据库。我认为，顺便说一句，这确实是一个非常容易犯的错误，因为有很多**Erdos问题**实际上已经被解决了。我认为这确实是这样。我认为搜索和检索是一个难题，你不知道那个论点或者一个等价的版本是否已经被解决了。事实上，我认为整个数据库中最有趣的部分是，有很多问题并没有直接解决，但可以仅仅是另一个已经解决的结果的扩展，几乎是微不足道的扩展。有时甚至没有解决。有时，我认为在这个**Dead Ends in Square-Free Walks**的案例中，它与**Harmonic**完全无关，我们实际上没有意识到，然后**Conander教授**实际上向我们和**Miller教授**指出，它实际上是来自**Stack Math Overflow**或**Stack Overflow**的帖子。

<details>
<summary>Original English</summary>

**Carina Hong**: yeah this is a great question I think after **Erdos** we're like extremely careful and so we kind of like you know we didn't really look at the other **Erdos problems** I believe that **harmonics** still continue to claim they have solved **Erdos problem** that might might not I don't know uh it's you know there's a I think **Terrence Tao** and a lot of other people have a database all the **Erdos problems** and the status I think you know like it is really by the way like it's a really easy mistake to make because there are so many **EDOS problems** that actually have been solved right and I think that that's kind of indeed I think like you know search and retrieval is a is a is a hard problem like you don't know if that argument or an equivalent version of that in fact I think the most interesting part about that entire database is um there are a lot of problems that are not directly solve solved but can be just an very is the extension almost a trivial extension of another result that has been solved or not sometimes not even resolved sometimes I think in this um **dead end square free walks case** which is nothing to do **harmonic complet** um that we actually didn't realize and then **professor** um **conander** actually pointed to us and to **professor Miller** is that it was actually from a **stack mass overflow** or **stack overflow post**

</details>

**Carina Hong**: 就像一个用户指出，有一个**1936年**的六个结果。这太迷人了。我认为很难弄清楚为什么搜索是一个难题。

<details>
<summary>Original English</summary>

**Carina Hong**: um like a user pointed out that there's a **1936 six results**. It's fascinating. I think it's hard to hard to find out why search is a hard problem.

</details>

**主持人**: 我猜这意味着，**猜想引擎**或其他什么，它会把搜索作为其过程的一部分吗？还是说这是你们人类做的事情，然后输入给它？

<details>
<summary>Original English</summary>

**Host**: I guess that means that you do does the the **conjecture engine** or whatever does that does that use search as part of its process or is that something that you kind of you you the human does and then feeds?

</details>

**Carina Hong**: 我认为**知识图谱**或**知识库**是任何公司的一个非常重要的组成部分。

<details>
<summary>Original English</summary>

**Carina Hong**: I think I think **knowledge graph** or **knowledge base** is a very you know important component of any any company.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 而且我认为这并没有被充分讨论。

<details>
<summary>Original English</summary>

**Carina Hong**: Uh and I think I don't think it's talked about enough.

</details>

**主持人**: 所以，你们似乎不想给我们太多细节，但是，你们有一个**知识图谱**。我的意思是，这还引出了另一个问题，我听说你们有一个非常庞大的**Lean**证明数据库，是你们生成的。所以在某种意义上是**合成数据**，但这可能是你们的竞争优势。

<details>
<summary>Original English</summary>

**Host**: And so and and you guys with that it sounds like you don't want to give us too many details but like so you guys have a **knowledge graph**. I mean that brings up also I I read somewhere that you guys have a really massive database of **lean proofs** that you've generated. So **synthetic data** in in some sense but that the and this may maybe is a **competitive advantage** for you.

</details>

**Carina Hong**: 我认为每个人都在努力积累数据，这并不是一种模式，它只是时间和时间模式。

<details>
<summary>Original English</summary>

**Carina Hong**: I think I think everyone is trying to accumulate like a data which is not a mode it's just time and **time mode**.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Carina Hong**: 是的。这完全取决于你是否能够足够快地执行，以确保你拥有一定的缓冲，因为你的数据集积累。但这只是一种缓冲。你有没有想过做一些像数学领域的**AlphaZero**那样的事情，从零开始，让它自己创造公理，然后看看会发生什么？

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. It's all it's all it's all about like you know whether you can execute fast enough um to make sure that you have like a certain buffer um because of say your data set you know accumulation but that is only just a buffer. Have you ever thought about doing something like an **alpha zero** for math where you start from nothing and let it just make up **axioms** and see what happens?

</details>

**Carina Hong**: 啊，这是一个很棒的问题。我认为这是一个非常有趣的方法，确实如此。是的，我认为我们相信这样一件事：假设**Axiom Prover**可以成为一个非常强大的数学家，那么它每天证明的东西，应该有望帮助它改进，对吧？我认为这种**自我改进**的设计非常有价值。

<details>
<summary>Original English</summary>

**Carina Hong**: Ah this is a wonderful question. I think that's a very interesting approach actually. Yeah, I think we we believe in something which is that like you know suppose um **action improver** can be a really strong mathematician and then really the the thing that it is proving every day should hopefully help it improve right I think this sort of **self-improvement design** is extremely valuable

</details>

**Carina Hong**: 而且我认为在**AI for Mass社区**中还有其他人，我认为**Gabriel Pesra教授**的工作非常有趣。我认为有一些更具猜想性的探索。假设我们只是改变，你知道，有很多你可以用某些特定方式做的事情，可以尝试看看你的系统是否能学会猜想和构建理论。我认为这个话题非常有趣和重要，因为它确实声称为了实现**超智能**。

<details>
<summary>Original English</summary>

**Carina Hong**: um and I think there are um other people in the **AI for mass community** I think uh **professor Gabriel Pesra's work** is very interesting um I think there are some of the um kind of more conjecturing type of exploration Um suppose we just kind of change um you know a lot of the there are specific things you can do in in certain in certain ways that that can try to see if your system can learn to contracture and build theories. I think that the the topic is really interesting and important because it really you're claiming that the to get to **super intelligence**.

</details>

**主持人**: 这似乎是不可能的。也许如果你有无限的资源，你可以**RL**，它可能会起作用。但现实是，你就是无法达到足够的**样本效率**或其他什么，所以你需要某种验证器在推理过程中进行循环，而不是因为你在训练过程中确实有验证器，但在推理过程中没有。

<details>
<summary>Original English</summary>

**Host**: There's sort of this like it's just not going to be possible. Maybe if you had infinite resources, you could just **RL** and it would work maybe. But the reality is is that you just can't be **sample efficient** enough or whatever it is to do that. So that you need some sort of verifier in the loop with the inference process rather than because you do have verifiers and like sort of during the training process and you just don't have them during the inference process.

</details>

**Carina Hong**: 是的，我认为他们很多人只是秘密地试图利用这一点来巩固他们的推理。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think a lot of them are just secretly like trying to use this to ground their reasoning.

</details>

**主持人**: 是的，我也是。我的意思是，当**01**出现时，我知道每个人都知道**01**要来了，但它还没有出来。我确信他们会宣布他们正在使用**Lean**进行**形式化验证**和实际生成证明，然后验证它们，以便他们能够巩固推理。我的意思是，那是我的。

<details>
<summary>Original English</summary>

**Host**: Yes. As well. I mean, I would I was surprised that that like when when **01** was, you know, everyone knew **01** was coming, but it did hadn't come out. I was sure they're going to announce that they're using **lean** to to do like **formal verification** of proofs and actually generate proofs and then verify them so that they're grounding and reasoning. I mean, that was my

</details>

**Carina Hong**: 我在那里的时候，有**3PF**，那是一项很棒的工作。还有**mini F2F**。这些都是**OpenAI**的形式化数学工作。好的。所以大概那些人正在做一些事情。

<details>
<summary>Original English</summary>

**Carina Hong**: when I was there, there was **3PF** that was a great piece of work. There's also **mini F2F**. These are all **formal mass work** at **OpenAI**. Okay. So presumably those guys are doing something.

</details>

**主持人**: 不，不，他们都走了。

<details>
<summary>Original English</summary>

**Host**: No, no, they all left.

</details>

**Carina Hong**: 哦，他们都走了。

<details>
<summary>Original English</summary>

**Carina Hong**: Oh, they all left.

</details>

**Carina Hong**: 所以我的意思是，如果你是一个实习生，我想你不能永远是实习生。所以假设你是一个初级技术人员，你想在一个问题上工作，只要能解决它。奇怪的是，人们认为初创公司就是这样一种，你的跑道可能会耗尽，然后一切都会崩溃。你可能在像**Axiom**或其他新实验室这样的初创公司，有更好的机会长时间专注于同一个问题。

<details>
<summary>Original English</summary>

**Carina Hong**: So that's my point which is that if you're like, you know, an intern, I guess you can't be an intern forever. So let's say you're like a junior, you know, like member technical staff and you want to work on something for like as long as it takes to solve it. Weirdly, people think about startup as this sort of your runway can just run out and it can just like all fall apart thing. you might have a better chance of staying focused on the same problem for as long as it takes at say a startup like **Axium** or one of the other new labs.

</details>

**主持人**: 是的。如果你与大公司的使命保持一致，而不是像有人决定你正在做的事情不再。

<details>
<summary>Original English</summary>

**Host**: Yeah. If you're aligned to the mission of the big company rather than like somebody decided that what you're doing is no longer

</details>

**Carina Hong**: 是的。是的。可能是你的副总裁输掉了一场政治斗争，所以，是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. It can be your **VP** lost some political fight and so Yeah.

</details>

**主持人**: 是的。绝对的。所以。

<details>
<summary>Original English</summary>

**Host**: Yeah. Absolutely. So

</details>

**Carina Hong**: 不，显然如果我们成功了，他们都会重新开始做。

<details>
<summary>Original English</summary>

**Carina Hong**: no obviously if we succeed then they're all going to you know start doing that again.

</details>

**主持人**: 是的。然后我想，作为人才，也会有更多的选择。

<details>
<summary>Original English</summary>

**Host**: Yes. And then like I guess as a talent then there are more like you know potential places to choose from as well.

</details>

**主持人**: 是的。那么你的工作就是快速行动。所以他们正在努力。所以实际上，你，我们还没有谈过，但你实际上也刚刚发布了一个用于**Lean**验证的**API**。

<details>
<summary>Original English</summary>

**Host**: Yeah. So then your job is to go fast. So they they they're they're struggling. So actually you um we haven't talked about it but you actually also just released an um an **API** for doing **lean verification**.

</details>

**主持人**: 我实际上用**Claude Code**试过了，因为它比设置你自己的**Lean**工具链更容易。

<details>
<summary>Original English</summary>

**Host**: And um I actually tried it with **cloud code** um because it's easier than setting up uh you know your own **lean** um tool chain. Yeah.

</details>

**主持人**: 嗯，你知道，尝试让**Lean**证明一些东西。

<details>
<summary>Original English</summary>

**Host**: Um and you know like tried to get **lean** to proof some stuff.

</details>

**主持人**: 嗯，基础设施可能并非微不足道，尤其是在大规模部署时。所以你想谈谈吗？

<details>
<summary>Original English</summary>

**Host**: Um and the infrastructure is is maybe non-trivial especially at scale. So you want to talk a little bit?

</details>

### AXL：Lean验证引擎与协作
**Carina Hong**: 是的。是的。所以我们刚刚发布了**AXL**，**AXL**代表**Axiom Lean Engine**。它实际上是一套用于**Lean**的证明验证和操作工具，用**Lean**语言编写。所以它是一堆**元编程**工具。现在**元编程**人才非常难找，我们非常感谢拥有这样一支精良的团队。我们希望免费向社区发布这些工具，因为我们认为可能还有其他人也在进行大规模**Lean**操作，这些工具将使他们的工作更加稳健、更快，并且能够大规模地做到这一点。**AXL**目前大约有**14个**这样的工具，从**Verify Proof**开始，它确保没有发生任何奇怪的事情，你知道，没有通过**Lean**代码作弊，你不会假设奇怪的事情，如果你问**n+n=n**，你可以证明**2+2=2**，你肯定知道这不是正确答案。还有很多其他**生成工具**。例如，你可以尝试不同的修复尝试。所以，损坏的**Lean**代码输入，然后是好的**Lean**代码输出。你知道，目前**LLM**还有其他的修复方法。所以希望我们提供的这个能更便宜，更直接，而且，你知道，我认为强大而更好的工程可以让你走得很远。很多**Lean**社区的人一直在使用**AXL**，即使只用了一周，他们也做了各种有趣的事情。我们看到**区块链社区**的人用它做有趣的事情，我们也听说很多人说**Claude**加上**AXL**是他们目前的“首选设置”。我们认为这些都是非常有趣的工具。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Yeah. So we just released **Axel AXL** stands for **Axium LIN engine** and uh it's really a set of kind of **proof validation** and **manipulation tools** that are built for **lin** in the language of **lin**. So uh it's a bunch of **meta programming tools**. Now **meta programming talents** are are extremely I think like you know hard to find and we're so grateful to have like a really crack team working on that and we want to kind of like release it to the community for um to use for free because we think that there are probably other people doing also like large scale **lane operations** and these tools going to make their stuff go a lot more robust and faster and do so at scale. Um and **AXO** is currently I think **14** uh like such tools starting from **verify proof** which is the sort of to make sure that there's not nothing weird um you know going on like no no sort of cheating by by **link code** you don't aim something out you know we don't you don't assume weird things if you ask **n plus n equals n** you can pro to prove **2 plus 2 equals 2** which you're you know for sure not that's not the right answer. Um there are also like you know a lot of other kind of **generation tools**. Um for example you can try like different **repair attempts**. So you know broken lane in and then good lane out. Uh and you know there are like currently you know other **repair methods** by **LM**. So hopefully this what we provide can be just a lot cheaper and uh more kind of you know straightforward and it's just you know I think strong strong and better engineering can can get you to to a place that's quite far. A lot of the people from the **link community** has been using **Axel** even if it's just been a week to do all sorts of different interesting things. We have seen uh people from the kind of **blockchain community** use it to to do interesting things as actor and we have seen also we have heard from a lot of the people that **claude plus axel** is kind of their go-to setup um for for now. Um we think that these are really interesting tools. I thi... [truncated]

</details>

**主持人**: 我的意思是，我觉得这对**Terrence Tao**所说的协作来说是一个很好的机会，一旦人们能够使用通用工具，并且变得容易操作，而且我的意思是，如果你即使是一个不那么强大的数学家，你也有直觉，你也许可以参与到证明一个更大的定理之类的努力中。

<details>
<summary>Original English</summary>

**Host**: I mean I feel like this is a great opportunity for the collaborations that **Terrence Tao** was talking about as well where once people have access to the common tools and it becomes easy to do and I mean like if if you have a intuition even uh not a strong ma mathematician like myself you might be able to participate in the you know sort of like an effort to prove a larger theorem or something like that.

</details>

**Carina Hong**: 是的，我认为这是一个非常有趣的观点，如果你认为数学不像**软件工程**那样协作。你没有成千上万的人一起工作。我认为**Polymath**就是一个这样的例子，那太棒了。所以如果你有很多好的设置，确实有商品化的访问，人们都可以参与进来。事实上，我认为一些大型的形式化项目就是这样完成的。任务被分解成子任务，但**Terrence Tao**和**Alex Condorrage**编写的蓝图过程，将任务分配给不同的人，以及如何将它们组合在一起，这个蓝图编写部分极其重要。我认为在**A维度**的**球体堆积**方面，还有其他公司也有成果，但**蓝图**部分仍然很大程度上是基于**球体堆积**社区、**Lean**社区、人类的蓝图，与其他一些成果也类似，**蓝图**部分仍然是人类生成的。我认为**自动生成蓝图**将是许多人同时试图解决的技术瓶颈。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think that's that's very interesting like view which is that like if you think about like **mathematics** has been not like as **software engineering**. You don't have like hundreds and thousands of people working on something together. I think **poly mass** was an instance when when that happened that was fantastic. So if you have a lot of really good sort of setup indeed like **commoditized** kind of access and people can all participate in in fact that's how I think some of the large **formalization projects** have been done uh things are divided into subtask but really the **blueprint writing process** by say **Terren Tao** and **Alex Condonderage** of assigning the task to different people and how things kind of fit together that **blueprint writing part** is extremely important and there has been I think result about **sphere packing** I think by um one of the other companies out there and the **blueprint part** for um the **A dimension** is still pretty much built on what the **sphere packing** uh community the **link community** the humans blueprint and similar with some of their other results as well the **blueprint part** has still been human generated and I think **autogenerated blueprint** is going to be a **technical bottleneck** that many people are trying to solve around the same time

</details>

**主持人**: 那么，我作为一个**Claude Code**用户，尝试一些小的引理或其他什么，即使我对数学没有很好的理解，也许我有一个高层次的理解，这样做有价值吗？

<details>
<summary>Original English</summary>

**Host**: so is there value in me as a you know **cloud code user** trying to attempt part like some small **lema** or whatever um where I don't have a great understanding of the math maybe I have a high level understanding

</details>

**Carina Hong**: 取决于你是想形式化还是想证明。

<details>
<summary>Original English</summary>

**Carina Hong**: depends are you trying to formalize or are you trying to prove

</details>

**主持人**: 嗯，想证明新事物。这是一个好点。是的，所以也许你显然会从**形式化**开始，对吧？你知道证明，但没有人能正确地进行**形式化**。

<details>
<summary>Original English</summary>

**Host**: uh to prove new things that's a good point yeah so maybe form you would obviously probably start with **formalization** right you know the proof and you just can't get nobody has been able to get the **formalization** correct

</details>

**Carina Hong**: 我确实看到有人使用**Lean**和**形式化**，他们尝试手动完成，而不是使用**AI**来学习数学。不，它是一个自动形式化。你没有那个过程。这很有趣，因为我认为我的很多朋友之所以开始研究**Lean**和**mathlib**，是因为他们是博士生，这个问题非常困难。我们总是被困住，我们想复习一些本科课程，那时我们仍然理解数学是关于什么的，我们通过**Lean**来做到这一点，我认为这非常美妙。

<details>
<summary>Original English</summary>

**Carina Hong**: I do actually have seen people use **link** and **formalization** and they try to do it by hand you know not using and **AI** as a way to learn mathematics. No, it's you know it's **auto formalization**. You don't have that process. Well, it's interesting because I think a lot of the uh my friends who started you know working on **lyn** and **mass li** was because they are in **PhD** and this problem's really hard. we get stuck all the time and we want to kind of review some of the **undergrad classes** a time where we still understand what the math was about and we do so by you know doing **lean** and I think that's that's very beautiful

</details>

**主持人**: 材料。

<details>
<summary>Original English</summary>

**Host**: the material

</details>

**Carina Hong**: 是的，但是如果你有，比如说，访问**Axiom Prover**，它也可以形式化所有形式化的东西，你就失去了学习过程的那个部分。

<details>
<summary>Original English</summary>

**Carina Hong**: yeah but if you have for example like you know um access to **action proer** that also can formalize all the **formalized** things and you don't have you lose that part of the **learning process**

</details>

**Carina Hong**: 是的，但我确实认为，你知道，对于你和我来说，我们可以设置**AXL**，然后尝试看看我们能够证明什么结果。我认为这很有趣。而且多亏了**AXL**使速度大大加快。你不需要等很久。

<details>
<summary>Original English</summary>

**Carina Hong**: yeah but I do think that you know like for for for you and I we can set up like **Axel** and try to like see, you know, what what results we might be able to prove. And I think that's quite interesting. And thanks to **Axel** sort of making the speed a lot faster. You don't have to wait very long.

</details>

**Carina Hong**: 我记得**Putnam**考试那天。我们都在作战室里。那是星期六。我们都非常兴奋，我们刚刚从官方的，比如，**Putnam**考试的主考官那里拿到了考卷。我们只是看着**AXL**的工作量有多大。如果没有它，我们不可能在规定时间内解决那八个问题。我认为这些工具的有趣之处在于，你也可以为**RL**设置有趣的奖励。

<details>
<summary>Original English</summary>

**Carina Hong**: I remember the **pandm exam** day. We were all like in the **war room**. It was a Saturday. We're all really excited and we just got the exam paper from the official um like organization, the **proctor** of the **pandemic exam**. We just like were looking at like how like how much workout **Axel** is like getting. And without it we couldn't have solved it with um I think the **eight problems** within the time limit that definitely not not within the time limit. And I think one thing about these tools is like it's very interesting in that potentially you can have interesting reward for **RL** as well.

</details>

**主持人**: 你是什么意思？

<details>
<summary>Original English</summary>

**Host**: What do you mean by that?

</details>

**Carina Hong**: 所以，例如，**Verify Proof**可以作为奖励，因为它只是一个完全正确且经过验证的证明。我明白了。

<details>
<summary>Original English</summary>

**Carina Hong**: So for example **verify proof** can be a a reward for just basically a proof is completely correct and validated. I see.

</details>

**Carina Hong**: 我认为**形式化验证工具**可以成为**RL**的一个有趣方向。

<details>
<summary>Original English</summary>

**Carina Hong**: I think **formal verification tooling** can be interesting direction to pursue with **RL**.

</details>

**主持人**: 是的。所以你的意思是，例如，你形式化非形式化的证明，然后验证什么，然后用它作为奖励，还是你的意思是？

<details>
<summary>Original English</summary>

**Host**: Yeah. So you mean um for example you formalize auto formalize the informal proof and then verify what and then use that as a reward or do you mean?

</details>

**Carina Hong**: 不，我的意思是，你把**Lean**程序传给这些形式化工具，对吧？然后你会有某种分数。

<details>
<summary>Original English</summary>

**Carina Hong**: No, as in like you pass like **limb programs** in these formal tools, right? like and you will have some sort of score.

</details>

**主持人**: 好的。是的。我想如果我要构建**01**之类的东西，我心里会使用我刚刚描述的东西。但你说的只是学习如何使用**Lean**。所以，关于前沿实验室的价值主张很有趣，假设你是一个**TOC**公司，那么当然你可以不这样做，而且我们已经看到，例如**DeepSeek**最初有一个形式化团队，后来因为战略方向变化而解散了该团队，这完全合理。现在假设你专注于**代码生成**，而且你有希望从事我们正在做的事情的人才。

<details>
<summary>Original English</summary>

**Host**: Okay. Yeah. I think if I were to build **01** or something, I would have in my mind I would have use what I just described. But you're saying just to learn how to do **lean**. So, so the **value proposition** which is interesting about **frontier lab** is that suppose you are a **toc business** then sure you you can just not do what we are doing and we have since for example **deepseek** like originally having a formal team and then later dissolve that team because of strategic direction change that's all completely reasonable now suppose you are focused on **coding** right and you have talent who want to work on what we're doing,

</details>

**Carina Hong**: 开展**代码生成**，进一步发挥你的优势和模式，会更有意义。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: it makes a lot more sense for you to do **code generation**, further your strength and mode. Yeah,

</details>

**Carina Hong**: 你可以与**Axiom**合作。就像**前沿实验室**与像**Excel**和**Parallel**这样的搜索初创公司合作一样，对吧？只需调用**Excel API**进行搜索，如果你是**前沿实验室**，我想你应该调用**Axiom API**进行验证。

<details>
<summary>Original English</summary>

**Carina Hong**: you can partner with **Axium**. Um just like how for example, **Frontier Labs** um partner with uh startups that work on search such as **Excel** and **parallel**, right? Just call **Excel API** for search and potentially, you know, if you're **Frontier Lab**, I think you should call **Axium API** for **verification**.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Carina Hong**: 嗯，更好的提议，但是。

<details>
<summary>Original English</summary>

**Carina Hong**: Um [clears throat] better preposition, but

</details>

**Carina Hong**: 建立自己的。这没有意义。我的意思是，你懂的，潜在地，我认为人才，**Lean**的挑剔，数据代码，你知道，没有理由。

<details>
<summary>Original English</summary>

**Carina Hong**: spitting up your own. It doesn't make sense. I mean, it just, you know, potentially, um, I think the talent, the the finicky of **lean**, um, the sort of data code, like like, you know, there's there's no reason to.

</details>

**主持人**: 是的。我花了五分钟就设置好了。

<details>
<summary>Original English</summary>

**Host**: Yeah. I mean, it took me **five minutes** to set up. [laughter]

</details>

**主持人**: 你为什么决定创业？

<details>
<summary>Original English</summary>

**Host**: Why did you decide to start a

</details>

**Carina Hong**: 对。我为什么决定？

<details>
<summary>Original English</summary>

**Carina Hong**: Right. Why did I decide?

</details>

**主持人**: 你是**斯坦福大学**的数学研究生。

<details>
<summary>Original English</summary>

**Host**: You were a grad student at **Stanford** and you know, in math.

</details>

**Carina Hong**: 是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah.

</details>

**主持人**: 那么是什么让你决定？

<details>
<summary>Original English</summary>

**Host**: So, what made you decide to

</details>

**Carina Hong**: 我根本没有学数学很久。我刚开始读博士，就立刻开始**融资**了。

<details>
<summary>Original English</summary>

**Carina Hong**: I wasn't in math for a while at all. I was I was uh I think like almost as soon as I started the **PhD**, I just started **fundraising**. So it wasn't like

</details>

**主持人**: 哦，真的吗？

<details>
<summary>Original English</summary>

**Host**: Oh, really?

</details>

**Carina Hong**: 是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah.

</details>

**主持人**: 那是计划好的，还是你一开始就意识到？

<details>
<summary>Original English</summary>

**Host**: Was that the plan or did you did you start there and you're like almost immediately realized that this is

</details>

**Carina Hong**: 没错。没错。所以法学院的那一年，对我来说在智力层面非常有趣。但那也是我生命中第一次没有科学、技术、数学的一年。

<details>
<summary>Original English</summary>

**Carina Hong**: Right. Right. So So the **year of law school**, right, it was very very interesting to me like on an intellectual level. But it's also this the first year where I had no science, technology, math whatsoever in my life.

</details>

**主持人**: 那是奇怪的一年，对吧？我读了很多书。我练习。嗯，我学习如何写作。我学习如何阅读。

<details>
<summary>Original English</summary>

**Host**: It's a weird year, right? Like I'm I'm reading a lot. I'm I'm practicing. Well, I'm learning how to write. I'm learning how to read like

</details>

**Carina Hong**: 但我只是想沉迷于某个技术领域。那一年也是如此。所以，是的，法学院的那一年，对吧？对我来说非常非常有趣，因为我当时想，好吧，我只是需要沉迷于一件技术事情，否则我就会，我不会觉得无聊，因为我真的很喜欢法律的一切。我真的很喜欢它。这是一件非常有趣的研究。但我只是，我的意思是，我基本上一直非常兴奋地关注推理的进展。我看了很多**后训练**的论文。我只是自己学习所有这些。然后有一天，我到了一个点，我想，我认为这肯定会发生。而且我想，和**Shou**在**Ver**的每次周末交流也无助于平息这个想法。所以我越来越着迷。

<details>
<summary>Original English</summary>

**Carina Hong**: and but like I'm I'm just kind of I want to like be obsessed about something in technology. Like that was also what's going on that year. So yeah, the **year of law school**, right? And and it was very very interesting to me because it's like okay like I just I need to be obsessed with like a technical thing cuz otherwise I get to I don't think I'm bored because I really love like everything about about law. I really really loved it. It was it was something that's incredibly interesting to study. Um but I just I I mean I've been basically like you know very excited about like the progress of reasoning. I was looking at a lot of the **post- training** kind of papers. I was I was learning all of these like just by myself. Um and then at one point it got to a point where I'm like I think this is for sure happening. And like I think talking to **Shou** right at at **Ver** like every weekend also like it didn't help like soothing this thought. So I got more and more obsessed

</details>

**Carina Hong**: 有一次我甚至想，好吧，如果我每分钟都在做这件事，而且我无法思考其他事情，那么我需要做些什么。我的意思是，这就像你，我疯狂地爱上了**AI**将要进行数学的这个想法，然后我想，好吧，我是否要进行数学？我那时真的太疯狂了，我记得那种痴迷，我无法摆脱它，然后我去了这个**Nihennessy**活动，**Scholar Dining House**举办了各种免费午餐活动，那些活动很棒，因为你可以得到免费食物，还可以接触到有趣的知识。我记得**Julie Draw**，我想她是**Facebook**的第一位产品经理，她来演讲，在那之后，我基本上就走上前去，我说，如果我想创业，而且你真的很想进入学术界，因为你喜欢数学，你会怎么做？然后她说，好吧，你知道，你在这两件事上花了多少时间？我说，**100% 0%**。然后她说，好吧，你必须追随你的精力。

<details>
<summary>Original English</summary>

**Carina Hong**: and at a point I'm like okay if I'm doing this like literally every minute and I can't think about something else like you know I need to do something about it. I mean it's like you I fall madly in love with the idea that **AI** is going to do math and like okay now do I do I do math? like I it's really really crazy like at a time where I remember the obsession was quite I just couldn't get out of it and then um I went to this **Nihennessy event scholar dining house** like host all sorts of like **free lunch events** and those are great because you get free food and you get interesting intellectual exposure to things and I remember **Julie Draw** who was I think a **Facebook** um first **Facebook PM** came to speak and then after that I just like basically walked up to her and I said like uh like what do you do if you want to do a startup and you really wanted to do academia because you you kind of love math. And then she's like, well, you know, what's your time spent on these two different things? And I'm like, **100% 0%**. And then she's like, well, you kind of have to follow your energy.

</details>

**主持人**: 是的。我的意思是，如果你完全沉迷于它。

<details>
<summary>Original English</summary>

**Host**: Yeah. I mean, if you're if you are completely obsessed with it.

</details>

**Carina Hong**: 是的。我完全沉迷于它，但我认为它会很大。我认为它必须是一家营利性初创公司，因为它比取得数学突破要广泛得多。如果你想到递归自我改进，以及更高级别的概念，你真的想要这个AI科学家，数学推理将是其中非常重要的一部分。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. I was completely obsessed with it, but I thought [clears throat] it's going to be big. And I thought like it it just it just has to be a **for-profit startup** because like it's so much broader than making **mathematical breakthroughs**. If [clears throat] you think about like **recursive self-improvement** and like really the the kind of more high level like concept of like you really want to have this **AI AI scientist** like the mass reason is going to be is going to be a pretty big part of it. Yeah.

</details>

**Carina Hong**: 现在，我想**Cursor**和**Claude**等人的信念是，就像数学可以迁移到**代码生成**一样，**代码生成**也可以迁移到数学。我认为这是事实。只是，你知道，为什么不直接推动它呢？我不明白。你需要直接推动它。

<details>
<summary>Original English</summary>

**Carina Hong**: And now trying like I think the the sort of belief by by **cursor** and **cla** and other folks is like okay like just like mass transfer to **coding coding** transfer to mass as well. I think that's true. It's just that like you know why why not push it directly. I don't I don't get it. You need to push that directly.

</details>

### 验证式AI：开放性、性能与信任
**Carina Hong**: 然后还有另一个想法，也许回到协作这一点。验证传统上被认为，好吧，有些行业有很多防护栏。所以如果你在国防、军事领域工作，好吧，你需要基本上满足很多进入壁垒，以满足那些严格的要求。所以它是一个验证是针对封闭行业的。但现在，我认为验证式AI首次开辟了协作，无论是人与AI的协作，还是在蓝图规划之前的人与人的协作，**Lean**是一种基础，是一种形式化语言的验证，然后是人与AI的协作，就像我们现在看到的，未来是AI代理与代理之间的协作。所以我想验证式AI旨在实现开放性，而非满足封闭行业的需求。我认为，就像我认为验证不应该仅仅是关于，哦，我记得有篇文章说，聊天机器人搞混了，数学是解决幻觉的方案。对我来说，验证不是关于缺陷。对我来说，验证是关于扩展卓越，复合卓越。就像回到协作这一点，它让像**拉马努金**这样一位已经非常强大的数学家变得更强，验证帮助他扩展了卓越，使其能够向上和向外发展。所以验证。

<details>
<summary>Original English</summary>

**Carina Hong**: And then there's this other like you know thought which is that and maybe kind of going back to the collaboration point right. Um **verification** has traditionally been thought of as okay well there are some industry where there's a lot of **guard rails**. So if you're working in **defense, military use**, okay, you need to like basically satisfy a lot of **barriers to entry** to meet those stringent like requirements. So it's it's something that's **verification** is for the industries that are closed but it's for the first time now I think **verified AI** is to open up collaboration either it's **human AI collaboration** well before **blueprinting** that's **human human collaboration** and **lyn** was a grounding was a **verification formal language** and then **human AI collaboration** like we're seeing now future **AI agent agent agent like collaboration** so like I think **verified AI** is for openness it's not for meeting the requirements of closed industries And I think just like I think **verification** should not be about oh I remember like you know there's article like **chatbots** mixed stuff up is **AI** the solution to sorry it's math solution to **hallucination**. **Verification** to me is not about **lousiness**. **Verification** to me is about **scaling brilliance compounding brilliance**. It's like just kind of going back to the collaboration point. It's about **ramen** being a much stronger mathematician. He was already a really strong one but **verification** helps him extend the brilliance like both kind of like scale up and scale out. So verification

</details>

**主持人**: 严谨。

<details>
<summary>Original English</summary>

**Host**: rigorous

</details>

**Carina Hong**: 对我来说，验证不是关于消除错误和缺陷，而是关于扩展卓越。第三点是，对我来说，验证不是关于严格性，它实际上是关于性能提升，它不仅仅是关于严格的要求，你必须克服的障碍，它实际上是关于**验证式生成**将使其变得更好。我认为最后一点是，很多人认为你从事验证是因为你不信任技术。这在普通大众中很受欢迎，包括我的父母，他们会说，哦，我们为什么要进行验证？因为技术会犯错误。不，我们不认为验证是因为不信任技术。这是因为预期的快速指数级扩展，以及技术的部署和创造，以及技术进步，是推动和要求验证的。这是一个非常数学化的观点，对吧？因为你是在说证明是数学的驱动力，对吧？很多数学都是基于证明的。是的。数学驱动着世界上很多的科学和创新，而数学领域的创新驱动着世界的创新。

<details>
<summary>Original English</summary>

**Carina Hong**: rigorous **verification** to me is not about you know like erasing the mistakes the **lousiness** about **scaling brilliance** and and the third point is that like **verification** to me is um not about like the sort of you know just talking about rigor it's actually about **performance gain** right it's not just about the stringent requirements the hurdles that you need to overcome it is about like actual **verified generation** is going to make it so much better and I think like kind of these three points I think the last point is that a lot of the people think that you work on **verification** because of your distrust for technology. Like it sells really well to I think the general p public including like my parents like oh why we're doing **verification** because like you know technology make mistakes it's no we don't think **verification** is based on is because of the distrust for technology. It's because that's what like um expected **rapid exponential scale up** and and um the deployment and the creation of technology and technological progress is what that compels and demands. It's a very mathematical perspective, right? Because you're saying **proofs** are **proofs** are drive math, right? A lot of math is based is is about proofs. Yeah. And math drives a lot of science and innovation in the world and the innovations in math drive innovation in the world. So that

</details>

**Carina Hong**: 但它甚至不需要通过，就解决所有问题而言。显然我的观点是，**迁移学习**不是，**迁移学习**是关于推动数学推理。所以，我想这里有几种说法。对于某些人来说，就像你解决了数学问题，然后数学是科学的基础，所以这实际上是AI数学中从AI科学中获取激进层的说法，我们确实相信一般的**迁移学习**，我认为**Axiom**处于基础设施栈中。

<details>
<summary>Original English</summary>

**Carina Hong**: but it doesn't need to even go through like in terms of you know the solve everything like obviously stands like my point is like **transfer learning** doesn't like **transfer learning** is about like pushing math **math reasoning**. just so so there are kind of I guess like there a couple narratives here like for some people it's like you you solve math and then maths are the you know fundamentals of sciences so that's actually the from **AI for math** like take this radical layer of **AI for science** is that narrative we actually believe in just like general **transfer learning** like I think **Axiom** is **Axium** is on the **infrastructure stack**

</details>

**主持人**: 你认为这只是解锁科学和法律等许多领域能力的第一个步骤。

<details>
<summary>Original English</summary>

**Host**: and you think that this is just a first step to you know basically unlocking capabilities in many domains in science and law for example.

</details>

**Carina Hong**: 是的。我认为是这样。所以，又来了，有多种信念。一种信念是，有数学，有形式化验证的力量。假设我们真的解决了数学问题，并且拥有一个非常强大的非形式化数学推理引擎。我们不认为这个术语会像通过形式化方式解决数学问题那样广泛。

<details>
<summary>Original English</summary>

**Carina Hong**: Yes. I I think it's so so again there are like you know multiple multiple kind of like beliefs. One belief is that there's math and there is like you know formal the power **formal verification**. Suppose we actually you know solve math and have a really strong informal **math reasoning** [clears throat] engine. We do not expect that term to be as large as solving math through the formal way.

</details>

**主持人**: 为什么？

<details>
<summary>Original English</summary>

**Host**: Why?

</details>

**Carina Hong**: 我的意思是，代码作为语言，它确实更具结构性。

<details>
<summary>Original English</summary>

**Carina Hong**: I mean code as as it is language but it is indeed on the more structured end.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Carina Hong**: 它连接了非形式化和形式化。

<details>
<summary>Original English</summary>

**Carina Hong**: It bridges informal and formal.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Carina Hong**: 我们正在做的事情不是非形式化与形式化之争。我们并没有采取完全形式化的证明方法，而是连接非形式化和形式化。它连接了高层次和低层次。它是通过推理，通过迁移学习的直接改进，而且它是间接的，因为数学将解锁小的科学，而且确实如此。

<details>
<summary>Original English</summary>

**Carina Hong**: What we are doing is it's not informal versus formal right. We're not taking the sort of like completely formal of a proof approach like it's in it's bridging between informal and formal. It is bridging between high level and low level. It is a direct sort of like a direct improvement through reasoning um through trans like **transfer learning** and it's also indirect in that like okay well like math is going to unlock little science and sure um and that is really what we're seeing.

</details>

**主持人**: 所以你认为它能实现**迁移学习**？

<details>
<summary>Original English</summary>

**Host**: So you think that it enables **transfer learning**?

</details>

**Carina Hong**: 是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah,

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**Host**: I see.

</details>

**Carina Hong**: 我认为这几乎是一个共识。

<details>
<summary>Original English</summary>

**Carina Hong**: I think that is that is pretty much a consensus.

</details>

**Carina Hong**: 我认为这是一个共识，而且这是一个被其他人忽视的赌注，因为数学听起来很纯粹，听起来没有商业价值。

<details>
<summary>Original English</summary>

**Carina Hong**: I think it is a consensus and this is a bet that has been pretty much kind of overlooked by others because math sounds pure and it doesn't sound like there's any commercial value. Mhm.

</details>

**Carina Hong**: 嗯，我当然理解这个机会，比如如果你是一家前沿实验室的机会成本，解决这个问题，但我绝对认为，如果你是一家资源充足的初创公司，你应该这样做。

<details>
<summary>Original English</summary>

**Carina Hong**: Well, I do obviously understand the opportunity like the opportunity cost if you're like a really like a **frontier lab** of of solving this problem, but I definitely think this is a problem that if you're like a **well resource startup**, you should be doing.

</details>

**主持人**: 这是一个有趣的观点。

<details>
<summary>Original English</summary>

**Host**: That's an interesting Yeah. perspective.

</details>

**主持人**: 你想说的都说完了吗？

<details>
<summary>Original English</summary>

**Host**: Did you get everything out that you wanted?

</details>

**Carina Hong**: 是的，我想，你知道，关于数学还是验证的问题？公司的**DNA**是数学。我们认为验证是最好的第一市场。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, I think I think it's um like you know like the question of like is math or is verification? The **DNA** of the company is math. We think best like **verification** is the best first market.

</details>

**Carina Hong**: 是的。我们认为解决数学问题，特别是形式化数学问题，将帮助我们应对验证式AI的雄心勃勃的追求。当我们完成之后，我们可能会有第二个市场，包括我们刚才谈到的AI科学，但在理论层面，现实世界的测试很重要，我们可能可以停留在数字世界和软件方面，而其他事物则获得奖励，比如物理世界的信号。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. And we think that sort of like solving math and especially like **formal math** um is going to like help us like tackle the really ambitious quest of **verified AI**. Now when we are done with that we might have other that second markets including a for science we just talked about but but on the theoretical layer right like I think real world testing is important and potentially we can stay in the digital world and soft software stuff and for other things to be to be to be getting reward like physical word signals

</details>

**主持人**: 但你认为做强大推理的能力，一旦你拥有了强大的验证式推理引擎，那就是时候了，好吧，我们已经为软件验证和硬件或其他什么解锁了它，但是，好吧，现在生物学和化学呢？

<details>
<summary>Original English</summary>

**Host**: but do you think that that that the sort of the capability of doing really powerful reasoning once you have that powerful **verified reasoning engine** that that's the moment when okay now we've unlocked that for you know **software verification** and **hardware** or whatever but okay so now what about **biology** what about **chemistry**

</details>

**Carina Hong**: 那么，那可能是一个，另一个就是，你离**递归自我改进**还有多远？

<details>
<summary>Original English</summary>

**Carina Hong**: so that could be one then the other one is then like really how far are you to **recursive self-improvement**

</details>

**主持人**: 好的，所以就是**AGI**。

<details>
<summary>Original English</summary>

**Host**: okay so just **AGI**

</details>

**Carina Hong**: 是的，我认为确实存在这个问题，不同的人因为他们的背景不同，他们的精力投入和热情引导他们走向不同的方向。对于有些人来说，我确实听到过这样的说法，他们想研究**AGI**，因为他们相信解决了**AGI**就解决了死亡。还有一些人来自医学背景，他们真的相信他们可以解决死亡，而不是解决**AGI**然后解决死亡。

<details>
<summary>Original English</summary>

**Carina Hong**: yeah I think there is this sort of question and different people because of their probably different backgrounds have different um it's it's really where your energy and your passion leads you like for some people actually I have heard this actually you know with my friends they want to work on **AGI** because they believe solve **AGI** solve death there are other people who come from a more like medicine background they really believe they can solve death and they don't solve **AGI** and then solve death

</details>

**主持人**: 他们只是解决了**AI for Science**。

<details>
<summary>Original English</summary>

**Host**: they just solve like **AI for science**

</details>

**Carina Hong**: 现在哪种方法是正确的，我不知道。

<details>
<summary>Original English</summary>

**Carina Hong**: now which way is correct I don't know

</details>

**主持人**: 所以从**递归自我改进**的角度来看，听起来你是在说，验证加上非形式化语言的结合。正是这种结合才能实现真正的**递归**。

<details>
<summary>Original English</summary>

**Host**: and so the **recursive self-improvement angle** it sounds to me like you're saying that the combination of **verification** plus the sort of like language which is informal. It's that combination that enables really good recursive.

</details>

**Carina Hong**: 我认为**递归自我改进**无论如何都会发生。我们正在努力让**形式化验证**占有一席之地。所以我们，又来了，**形式化验证**能否受到欢迎、部署并成为共识，取决于我们执行得如何。我认为当你把这个问题简化为一个执行问题时，你就应该放手去做。展望未来，你认为**Axiom**和整个领域最大的瓶颈是什么？

<details>
<summary>Original English</summary>

**Carina Hong**: I think **recursive self-improvement** is going to happen anyways. We're trying to have like **formal verification** earnest place. [snorts] So we we like again the whether um **formal verification** can be welcomed and deployed and become a consensus depends on how well we execute [snorts] and I think when you boil down that problem into an execution problem you should just go for it. what looking forward what's the biggest bottleneck that you see in the field for both atom and maybe just the field abroad in terms of

</details>

**Carina Hong**: 碎片化。所以，我认为我们处于一个市场中，人们喜欢创建一千个团队，而不是合力做一件事。我认为这实际上是最大的泡沫指标。我认为有一些分类泡沫，还有其他一些分类是登月计划，那不是泡沫，只是看起来有点泡沫化。如果那些真正合法的人决定为了使命而不是为了自我、为了新实验室创始人的地位而加入团队工作，那么我认为这些类别我非常看好，反之亦然。所以我认为瓶颈实际上是，我认为这很恼人，因为我们处于一个，如果你相信我们处于一个研究时代，如果你相信深度技术是值得追求的有趣方向，那么市场条件目前有好有坏，好的一面是它使得这些长期、长远押注能够获得资金，坏的一面是市场噪音太多，还有一些非理性的参与者。我们努力与非常棒的风险投资公司合作，他们是我们的合作伙伴，是我们的智力伙伴，我们有很多共识，我们确实长时间地相互探讨非常酷的技术和非技术想法，而且，你知道，我们在工作之外和周末花了很多时间一起认真地建设公司。还有一些人只是想把资金停放在某个地方，你知道，虽然我们不与他们合作，但这些市场条件鼓励碎片化，当事情变得碎片化时，没有人能达到目标。我认为每个类别，无论想法多么正确，都处于一种“争取生存权”的阶段，如果情况是这样的话，那么，例如，伟大的深度科技公司**SpaceX**和人们。

<details>
<summary>Original English</summary>

**Carina Hong**: uh **fragmentation** so um I think we're in a market where people like to start like you know a thousand people they don't join force they start a thousand things I think that's actually the biggest like kind of **bubble indicator** I think there are **categorical bubble** and there are like other categories where there are **moonshots** it's not **bubble** it just looks a little bubbly in the field if people who are like really like of really legit, you know, backgrounds decides to join force and work in a team for the mission rather than for ego for kind of the status new lab founder. I think that categories I'm I'm really bullish other and vice versa. So I think the bottleneck actually is about potentially I think I think it's it's it's annoying because it's like we are in a if if you believe we are in a in an age of um research if you believe in like **deep tax** are the interesting directions to go after um [clears throat] the market sort of conditions currently is good and bad and that good it enables these sort of **long-term long horizon bets** to be funded bad because there's too much noise in the market and some other like **irrational players**. Um, you know, we we try to work with really incredible venture firms like they are the partners. They are our intellectual partners and there's a lot of alignment and we really bounce like very uh cool ideas technical and non-technical each other like for long long hours and and you know we spend like a lot of time off work and weekend together to really intensely build the company. There are also other people who just want to like park like capital somewhere and you know while we don't work with them these encourage these are market conditions that encourage **fragmentation** and when things get fragmented like no one gets there like I think every category regardless of how how right the idea is it's pretty much in a sort of earning the right to exist stage and if that is the case then um and for example great **DTAC company Space X** and people do ... [truncated]

</details>

**主持人**: 然后是大型实验室，我有没有漏掉谁？它真的支离破碎吗？

<details>
<summary>Original English</summary>

**Host**: and then you know the big labs right am I missing someone is like is that actually fragmented really?

</details>

**Carina Hong**: 我想碎片化是整个**AI**领域的瓶颈。

<details>
<summary>Original English</summary>

**Carina Hong**: I guess **fragmentation** I think is a bottleneck for the entire like **AI landscape**.

</details>

**主持人**: 好的。是的。我认为**AI**数学是一个实际上没有泡沫的类别，因为它没有碎片化，因为那些真正有才华的人确实喜欢联手。所以，例如，让**K Canuno**和**Fr Charton**在一个团队中，这太棒了。你有一个核心贡献者，前沿数学**Tier 4**，真正优秀的基准测试者，**Franis**，他在**AI**数学发现领域，他们一起工作，那么你突然成为一个既拥有证明能力又拥有构造能力的参与者，这太棒了。我相信，正如你所说，**Harmonic**可能也有一些非常优秀的人才联手。我认为**AI**数学是一个很好的类别，因为它没有碎片化。但即使从我们的角度来看，例如**RL**，我并不认为那是一个类别，但**RL**人才目前很难吸引和留住，对于每个人来说都是如此。有很多公司成立后三个月就被出售了，而你本可以花一个月的时间解决技术问题，结果却在处理交易，这是一个浪费的月份。我这么说也带着一些痛苦和磨难，因为我经历了两次融资。是的。

<details>
<summary>Original English</summary>

**Carina Hong**: Okay. Yeah. I think **AI for math** is a category that is actually not a **bubble** because it is not fragmented because people who are really amazing talents do like to join force. So for example the fact to get **K can uno** and **Fr Charton** on one team like this is fantastic like you have someone who's a core contributor **Frontier math Tier 4** really great benchmark setter **Franis** who's on the **AI for mass discovery** have proving and discovery they work together then you are suddenly a player with both proven capability and construction capability and that's fantastic and I believe you know as you said like **harmonic** probably also have some really great talents like joining force together I think **afro mass** is a is a good category because of the absence of **fragmentation** but even you know from from our perspective the sort of for example um you know **RL** right being I don't I don't think that's like a category per se but you know **RL talents** currently um it's quite hard to to attract and retain right for for literally everyone and there are a lot of um companies being started then sold like **three months later** and and just the the each month where you could have worked on a technical problem and you're instead working on deals It's a month that is wasted and I say that like you know also with some amount of pain and suffering because of having having gone through **two fundraises**. Yes. [laughter] Yes. Yes.

</details>

**主持人**: 是的。那么**AI**数学最大的瓶颈是什么？

<details>
<summary>Original English</summary>

**Host**: Yeah. So so what's the biggest bottleneck in **AI for math**

</details>

**主持人**: 对于**AI**数学？

<details>
<summary>Original English</summary>

**Host**: for for a for math?

</details>

**主持人**: 不是**Axiom**，而是整个社区。

<details>
<summary>Original English</summary>

**Host**: Not **Axium** but just the community

</details>

**Carina Hong**: **AI**数学社区。

<details>
<summary>Original English</summary>

**Carina Hong**: the [clears throat] community of **AI for math**.

</details>

**主持人**: 是的。它走向何方？大家真正想突破的是什么？

<details>
<summary>Original English</summary>

**Host**: Yeah. Where is it going? What is the thing that everyone just really wants to break?

</details>

**Carina Hong**: 我预计随着**Axiom**和**Harmonic**确立行业领导地位，碎片化将开始出现。

<details>
<summary>Original English</summary>

**Carina Hong**: I expect **fragmentation** to start to happen as **Axium** and **harmonic** establish **category leadership**.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Mhm. [clears throat]

</details>

**Carina Hong**: 所以我预计人们会，你知道，那是一件事，但我也认为另一个瓶颈可能是短期与长期的压力。我认为我们正在以非常快节奏的方式做事。但这并不意味着我们总是能够，或者说总是正确地以最快节奏的方式做事。我们之所以快速，是因为我们是在国际奥林匹克数学竞赛当天成立的，所以无论如何我们都无法参加那次比赛。下一次数学奥林匹克竞赛是**Putnam**，我们非常兴奋，因为它是一个本科生考试，而今年的**IMO25**在**MOHS**量表上是容易的，而**Putnam**可能很难，事实上它比**IMO**更难，在**MOHS**量表上，如果你看看AI在平均和最大难度问题上保留了多少分数。**Putnam**在这两个轴上都更难。所以我们想要尝试，所以只有四个月的差距，但这并不意味着我总是会设定四个月的目标。如果我只设定四个月的目标来建立公司，我可能会建立一个非常短视的公司。所以我想有更长远的问题。例如，市场力量可能会迫使其他参与者进行三重验证。虽然**共同验证**可能是一个圣杯。如果解决了这个问题，那么在一定程度上，你也可以自然地解决三重验证问题，但需要注意**分布偏移**。但我坚信，瓶颈可能是压力，但我认为**Axiom**很幸运，我们足够早，我们是一个由非常具有自主性的人组成的团队，我们的执行力通常超越预期。但我认为，整个**AI**数学领域可能存在的瓶颈是，试图证明商业价值可能会严重分散核心能力改进的注意力。

<details>
<summary>Original English</summary>

**Carina Hong**: So I expect people kind of you know that that's one thing but I also think that another bottleneck could be the pressure of **short-term versus long-term**. I think that we are doing things in a very sort of fastpaced manner. But that does not mean we can always or it does not mean it is always correct to do things in the most fast-paced manner. like we did things in a fast-paced manner because well we were founded on the day of **international mass olympia** so we couldn't have competed in that anyway the next mass **Olympia** is **punham** and we're quite excited because it's I mean it's undergraduate exam and this year's **IMO25 IMO** was easy on the **MOHS scale** and **pund** could be hard and in fact it was harder than the **IMO** and the **MOHS scale** if you look at the **AI** um you know how much how many scores the **AI** uh has has retained on average and on the max you difficulty of the problem. **Pandm** is harder in both both axis. Um so we want want to try and so there's only a gap of **four months** but it doesn't it doesn't mean I'm always going to set **four months goals**. If I build a company only setting **four months goals** I I might build a really short-sighted company. So there are like I think longer horizon problem. I think for example **market forces** could force other players into **trip verification**. Well it is possible that **co-verification** is a **holy grail**. It's possible that if you solve that then you also naturally solve **trip verification** with some amount of like epsilon caveat of like **distribution shift** but I strongly believe that like a bottleneck like could be the pressure but I think that **Axium** is fortunate that when we are early enough to we are like a team of just incredibly like um **high agency people** that our execution generally surpasses expectation but I think like what I think could be a bottleneck for the entire aformat field is that potentially trying to prove **commercial value** is going to distract significantly from the core **capability improvement**.

</details>

**主持人**: 是的，这很有道理。

<details>
<summary>Original English</summary>

**Host**: Yeah, that makes sense. Cool.

</details>

**主持人**: 谢谢你过来见我们。我知道交通很糟糕。

<details>
<summary>Original English</summary>

**Host**: Thank you for driving up and coming to see us. I know the traffic was was horrible.

</details>

**Carina Hong**: 是的，谢谢。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah, thank you

</details>

**主持人**: 而且，很高兴与您交谈，我们期待看到事情如何发展。

<details>
<summary>Original English</summary>

**Host**: and and um it's been really a pleasure speaking with you and um we look forward to to seeing how things develop.

</details>

**Carina Hong**: 是的。非常感谢。谢谢。

<details>
<summary>Original English</summary>

**Carina Hong**: Yeah. Thank you so much. Thank you. Yeah.

</details>